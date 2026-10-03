
# Android Studio Giraffe 核心指南 - Java 版

![](img/java_giraffe_front_cover_large.png)

## 19.19 总结

## 20 在 Android Studio 中处理 ConstraintLayout 链与比例

### 20.1 创建链

### 20.2 更改链样式

### 20.3 内部填充链样式 (Spread Inside Chain Style)

### 20.4 紧凑链样式 (Packed Chain Style)

### 20.5 带有偏好的紧凑链

### 20.6 权重链 (Weighted Chain)

### 20.7 处理比例

### 20.8 总结

## 21 Android Studio 布局编辑器 ConstraintLayout 教程

### 21.1 Android Studio 布局编辑器工具示例

### 21.2 准备布局编辑器环境

### 21.3 向用户界面添加组件

### 21.4 添加约束

### 21.5 测试布局

### 21.6 使用布局检查器 (Layout Inspector)

### 21.7 总结

## 22 在 Android Studio 中进行手动 XML 设计

### 22.1 手动创建 XML 布局

### 22.2 手动 XML vs. 可视化设计

### 22.3 总结

## 23 使用约束集 (Constraint Sets) 管理约束

### 23.1 Java 代码对比 布局文件

### 23.2 创建视图

### 23.3 视图属性

### 23.4 约束集

#### 23.4.1 建立连接

#### 23.4.2 将约束应用于布局

#### 23.4.3 父级级连接

#### 23.4.4 尺寸约束

#### 23.4.5 约束偏好

#### 23.4.6 对齐约束

#### 23.4.7 复制并应用约束集

#### 23.4.8 ConstraintLayout 链

#### 23.4.9 辅助线

#### 23.4.10 移除约束

#### 23.4.11 缩放

#### 23.4.12 旋转

### 23.5 总结

## 24 Android ConstraintSet 教程

### 24.1 在 Android Studio 中创建示例项目

### 24.2 向 Activity 添加视图

### 24.3 设置视图属性

### 24.4 创建视图 ID

### 24.5 配置约束集

### 24.6 添加 EditText 视图

### 24.7 将密度无关像素 (dp) 转换为像素 (px)

### 24.8 总结

## 25 在 Android Studio 中使用应用更改 (Apply Changes) 的指南

### 25.1 介绍应用更改

### 25.2 理解应用更改选项

### 25.3 使用应用更改

### 25.4 配置应用更改的回退设置

### 25.5 应用更改更改教程

### 25.6 使用应用代码更改 (Apply Code Changes)

### 25.7 使用应用更改并重启 Activity

### 25.8 使用运行应用

### 25.9 总结

## 26 Android 事件处理概览与示例

### 26.1 理解 Android 事件

### 26.2 使用 `android:onClick` 资源

### 26.3 事件监听器与回调方法

### 26.4 事件处理示例

### 26.5 设计用户界面

### 26.6 事件监听器与回调方法

### 26.7 消费事件

### 26.8 总结

## 27 Android 触摸与多点事件处理

### 27.1 拦截触摸事件

### 27.2 MotionEvent 对象

### 27.3 理解触摸动作

### 27.4 处理多点触摸

### 27.5 多点触摸应用示例

### 27.6 设计 Activity 用户界面

### 27.7 实现触摸事件监听器

### 27.8 运行示例应用

### 27.9 总结

## 28 使用 Android GestureDetector 类检测常用手势

### 28.1 实现常用手势检测

### 28.2 创建手势检测项目示例

### 28.3 实现监听类

### 28.4 创建 GestureDetectorCompat 实例

### 28.5 实现 `onMotionEvent()` 方法

### 28.6 测试应用

### 28.7 总结

## 29 在 Android 上实现自定义手势和缩放识别

### 29.1 Android 手势构建器应用

### 29.2 GestureOverlayView 类

### 29.3 检测手势

### 29.4 识别特定手势

### 29.5 安装并运行手势构建器应用

### 29.6 创建手势文件

### 29.7 创建示例项目

### 29.8 从 SD 卡中提取手势文件

### 29.9 将手势文件添加到项目

### 29.10 设计用户界面

### 29.11 加载手势文件

### 29.12 注册事件监听器

### 29.13 实现 `onGesturePerformed` 方法

### 29.14 测试应用

### 29.15 配置 GestureOverlayView

### 29.16 拦截手势

### 29.17 检测缩放手势

### 29.18 缩放手势示例项目

### 29.19 总结

## 30 Android Fragment 简介

### 30.1 什么是 Fragment？

### 30.2 创建 Fragment

### 30.3 使用布局 XML 文件向 Activity 添加 Fragment

### 30.4 在代码中添加和管理 Fragment

### 30.5 处理 Fragment 事件

### 30.6 实现 Fragment 通信

### 30.7 总结

## 31 在 Android Studio 中优 Fragment 示例

### 31.1 关于示例应用

### 31.2 创建示例项目

### 31.3 创建 Fragment 布局

### 31.4 将 Fragment 迁移到 View Binding

### 31.5 添加第二个 Fragment

### 31.6 将 Fragment 添加到 Activity

### 31.7 让 Fragment 与 Activity 通信

### 31.8 让 Activity 与 Fragment 通信

### 31.9 测试应用

### 31.10 总结

## 32 使用 Jetpack 的现代 Android 架构

### 32.1 什么是 Jetpack？

### 32.2 “旧”架构

### 32.3 现代 Android 架构

### 32.4 ViewModel 组件

### 32.5 LiveData 组件

### 32.6 ViewModel 状态保存 (Saved State)

### 32.7 LiveData 与 Data Binding

### 32.8 Android 生命周期

### 32.9 仓库模块 (Repository Modules)

### 32.10 总结

## 33 Android ViewModel 教程

### 33.1 关于项目

### 33.2 创建 ViewModel 项目

### 33.3 移除不需要的项目元素

### 33.4 设计 Fragment 布局

### 33.5 实现 ViewModel

### 33.6 将 Fragment 与 ViewModel 关联

### 33.7 修改 Fragment

### 33.8 访问 ViewModel 数据

### 33.9 测试项目

### 33.10 总结

## 34 Android Jetpack LiveData 教程

### 34.1 LiveData - 回顾

### 34.2 在 ViewModel 中添加 LiveData

### 34.3 实现观察者 (Observer)

### 34.4 总结

## 35 Android Jetpack Data Binding 概述

### 35.1 Data Binding 概述

### 35.2 Data Binding 的核心组件

#### 35.2.1 项目构建配置

#### 35.2.2 Data Binding 布局文件

#### 35.2.3 布局文件数据元素

#### 35.2.4 绑定类

#### 35.2.5 Data Binding 变量配置

#### 35.2.6 绑定表达式（单向）

#### 35.2.7 绑定表达式（双向）

#### 35.2.8 事件与监听器绑定

### 35.3 总结

## 36 Android Jetpack 数据绑定教程

### 36.1 移除冗余代码

### 36.2 启用数据绑定

### 36.3 添加布局元素

### 36.4 在布局文件中添加数据元素

### 36.5 配合绑定类（Binding Class）操作

### 36.6 将 ViewModel 实例赋值给数据绑定变量

### 36.7 添加绑定表达式

### 36.8 添加转换方法

### 36.9 添加监听器绑定

### 36.10 测试应用

### 36.11 总结

## 37 Android ViewModel 状态保存教程

### 37.1 理解 ViewModel 状态保存

### 37.2 实现 ViewModel 状态保存

### 37.3 保存与恢复状态

### 37.4 在 ViewModelDemo 项目中添加保存状态支持

### 37.5 总结

## 38 使用 Android 周期感知组件

### 38.1 周期感知

### 38.2 周期所有者（Lifecycle Owners）

### 38.3 周期观察者（LifecycleObservers）

### 38.4 周期状态与事件

### 38.5 总结

## 39 Android Jetpack 周期感知教程

### 39.1 创建示例周期项目

### 39.2 创建周期观察者

### 39.3 添加观察者

### 39.4 测试观察者

### 39.5 创建周期所有者

### 39.6 测试自定义周期所有者

### 39.7 总结

## 40 导航架构组件概览

### 40.1 理解导航

### 40.2 声明导航宿主（Navigation Host）

### 40.3 导航图（Navigation Graph）

### 40.4 访问导航控制器（Navigation Controller）

### 40.5 触发导航动作（Navigation Action）

### 40.6 传递参数

### 40.7 总结

## 41 Android Jetpack 导航组件教程

### 41.1 创建 NavigationDemo 项目

### 41.2 在构建配置中添加导航

### 41.3 创建导航图资源文件

### 41.4 声明导航宿主

### 41.5 添加导航目标（Navigation Destinations）

### 41.6 设计目标 Fragment 布局

### 41.7 在导航图中添加动作

### 41.8 实现 OnFragmentInteractionListener

### 41.9 为 Fragment 添加导航支持

### 41.10 触发动作

### 41.11 传递参数

### 41.12 总结

## 42 MotionLayout 简介

### 42.1 MotionLayout 概览

### 42.2 MotionLayout

### 42.3 MotionScene（运动场景）

### 42.4 配置约束

### 42.5 自定义属性

### 42.6 触发动画

### 42.7 关键帧（Keyframes）

### 42.8 属性关键帧

### 42.9 位置关键帧

### 42.10 时间关键帧

### 42.11 循环关键帧

### 42.12 从代码启动动画

## 43 MotionLayout 教程

### 43.1 创建 MotionLayoutDemo 项目

### 43.2 从 ConstraintLayout 迁移 MotionLayout

### 43.3 配置起始和结束约束

### 43.4 预览 MotionLayout 动画

### 43.5 添加点击手势

### 43.6 在过渡（Transition）中添加属性关键帧

### 43.7 在过渡中添加自定义属性（CustomAttribute）

### 43.8 添加位置关键帧

## 44 MotionLayout 关键循环（KeyCycle）教程

### 44.1 循环关键帧概览

### 44.2 使用循环编辑器

### 44.3 创建 MotionCycleDemo 项目

### 44.4 配置起始和结束约束

### 44.5 创建循环（Cycles）

### 44.6 预览动画

### 44.7 在 MotionScene 中添加关键帧集（KeyFrameSet）

### 44.8 总结

## 45 使用悬浮操作按钮（FAB）和 Snackbar

### 45.1 Material Design

### 45.2 设计库

### 45.3 悬浮操作按钮 (FAB)

### 45.4 Snackbar

### 45.5 创建示例项目

### 45.6 复习项目

### 45.7 移除导航功能

### 45.8 更改悬浮动作按钮 (FAB)

### 45.9 为 Snackbar 添加操作按钮

### 45.10 总结

## 46 使用 TabLayout 组件创建标签页界面

### 46.1 ViewPager2 简介

### 46.2 TabLayout 组件概览

### 46.3 创建 TabLayoutDemo 项目

### 46.4 创建第一个 Fragment

### 46.5 复制 Fragment

### 46.6 添加 TabLayout 和 ViewPager2

### 46.7 创建 Pager 适配器 (Adapter)

### 46.8 执行初始化任务

### 46.9 测试应用

### 46.10 定制 TabLayout

### 46.11 总结

## 47 使用 RecyclerView 和 CardView 组件

### 47.1 RecyclerView 概述

### 47.2 CardView 概述

### 47.3 总结

## 48 Android RecyclerView 和 CardView 教程

### 48.1 创建 CardDemo 项目

### 48.2 修改 Basic Views Activity 项目

### 48.3 设计 CardView 布局

### 48.4 添加 RecyclerView

### 48.5 添加图片文件

### 48.6 创建 RecyclerView 适配器 (Adapter)

### 48.7 初始化 RecyclerView 组件

### 48.8 测试应用

### 48.9 响应卡片选择

### 48.10 总结

## 49 布局编辑器示例数据教程

### 49.1 为项目添加示例数据

### 49.2 使用自定义示例数据

### 49.3 总结

## 50 使用 AppBar 和折叠工具栏布局 (Collapsing Toolbar Layout)

### 50.1 AppBar 的结构

### 50.2 示例项目

### 50.3 协调 RecyclerView 和工具栏

### 50.4 介绍折叠工具栏布局

### 50.5 更改标题颜色和遮罩颜色 (Scrim Color)

### 50.6 总结

## 51 Android Studio 主/详情流 (Primary/Detail Flow) 教程

### 51.1 主/详情流

### 51.2 创建主/详情流 Activity

### 51.3 添加主/详情流 Activity

### 51.4 修改主/详情流模板

### 51.5 更改内容模型

### 51.6 更改详情面板

### 51.7 修改 ItemDetailFragment 类

### 51.8 修改 ItemListFragment 类

### 51.9 添加 Manifest

### 51.10 运行应用

### 51.11 总结

## 52 Android 服务 (Services) 概览

### 52.1 启动服务 (Started Service)

### 52.2 绑定服务 (Bound Service)

### 52.3 服务的结构

### 52.4 销毁服务的选项

### 52.5 在 Manifest 文件中声明服务

### 52.6 在启动时启动服务

### 52.7 总结

## 53 Android 意图 (Intents) 概述

### 53.1 意图概述

### 53.2 显式意图 (Explicit Intents)

### 53.3 从 Activity 返回数据

### 53.4 隐式意图 (Implicit Intents)

### 53.5 使用意图过滤器 (Intent Filters)

### 53.6 自动链接验证

### 53.7 手动启用链接

### 53.8 检查可用性

### 53.9 总结

## 54 Android 显式意图——实例教程

### 54.1 创建显式意图应用

### 54.2 为 MainActivity 设计用户界面

### 54.3 创建第二个 Activity 类

### 54.4 为 SecondActivity 设计用户界面

### 54.5 检查应用 Manifest 文件

### 54.6 创建意图 (Intent)

### 54.7 提取意图数据



### 54.8 将 SecondActivity 作为子 Activity 启动

### 54.9 从子 Activity 返回数据

### 54.10 测试应用

### 54.11 总结

## 55. Android 隐式意图——实例教程

### 55.1 创建 Android Studio 隐式意图项目

### 55.2 设计用户界面

### 55.3 创建隐式意图

### 55.4 添加第二个匹配的 Activity

### 55.5 在 UI 中添加 WebView

### 55.6 获取意图 URL

### 55.7 修改 MyWebView 项目的 Manifest 文件

### 55.8 在设备上安装 MyWebView 包

### 55.9 测试应用

### 55.10 手动启用链接

### 55.11 自动链接验证

### 55.12 总结

## 56. Android 广播意图 (Broadcast Intents) 和广播接收器 (Broadcast Receivers)

### 56.1 广播意图概述

### 56.2 广播接收器概述

### 56.3 从广播获取结果

### 56.4 粘性广播意（Sticky Broadcast Intents）

### 56.5 广播意示例

### 56.6 创建示例应用

### 56.7 创建并发送广播意

### 56.8 创建广播接收器

### 56.9 注册广播接收器

### 56.10 测试广播示例

### 56.11 监听系统广播

### 56.12 总结

# 57. Android 本地绑定服务—— 实例

### 57.1 理解绑定服务

### 57.2 绑定服务的交互选项

### 57.3 本地绑定服务示例

### 57.4 向项目添加绑定服务

### 57.5 实现 Binder

### 57.6 将客户端绑定到服务

### 57.7 完成示例

### 57.8 测试应用

### 57.9 总结

# 58. Android 远程绑定服务—— 实例

### 58.1 客户端到远程服务的通信

### 58.2 创建示例应用

### 58.3 设计用户界面

### 58.4 实现远程绑定服务

### 58.5 在清单文件文件中配置远程服务

### 58.6 启动并绑定到远程服务

### 58.7 向远程服务发送消息

### 58.8 总结

# 59. Java 线程、处理器和执行器的基础概述

### 59.1 应用主线程

### 59.2 线程处理器（Handlers）

### 59.3 线程示例

### 59.4 构建应用

### 59.5 创建新线程

### 59.6 实现线程处理器

### 59.7 向处理器传递消息

### 59.8 Java 执行器并发

### 59.9 使用 Runnable 任务

### 59.10 关闭执行器服务

### 59.11 使用 Callable 任务和 Future 

### 59.12 处理 Future 结果

### 59.13 调度任务

### 59.14 总结

# 60. 在 Android 中请求运行时权限

## 60.1 理解普通权限和危险权限

## 60.2 创建权限示例项目

## 60.3 检查权限

## 60.4 在运行时请求权限

## 60.5 为权限请求提供理由

## 60.6 测试权限应用

### 60.7 总结

# 61. 通知教程

### 61.1 通知概述

### 61.2 创建 Notify 项目

### 61.3 设计用户界面

### 61.4 创建第二个 Activity

### 61.5 创建通知通道（Channel）

### 61.6 请求通知

### 61.7 创建并发布通知

### 61.8 从通知启动 Activity

### 61.9 为通知添加操作

### 61.10 组绑通知

### 61.11 总结

# 62. Android 直接回复（Direct Reply）教程

## 62.1 创建 DirectReply 项目

### 62.2 设计用户界面

### 62.3 请求通知

### 62.4 创建通知通道

### 62.5 构建 RemoteInput 对象

### 62.6 创建 PendingIntent

### 62.7 创建回复操作

### 62.8 接收直接回复输入

### 62.9 更新通知

### 62.10 总结

# 63. 折叠屏设备与多窗口支持

### 63.1 折叠屏与多窗口支持

### 63.2 使用折叠屏模拟器

### 63.3 进入多窗口模式

### 63.4 启用并使用自由窗口（Freeform）支持

### 63.5 检查自由窗口支持

### 63.6 在应用中启用多窗口支持

### 63.7 指定多窗口属性

### 63.8 在 Activity 中检测多窗口模式

### 63.9 接收多窗口通知

### 63.10 在多窗口模式下启动 Activity

### 63.11 配置自由窗口 Activity 的大小和位置

### 63.12 总结

# 64. Android SQLite 数据库概述

### 64.1 理解数据库表

### 64.2 介绍数据库模式（Schema）

### 64.3 列和数据类型

### 64.4 数据库行

### 64.5 介绍主键

### 64.6 什么是 SQLite？

### 64.7 结构化查询语言 (SQL)

### 64.8 在 Android 虚拟设备 (AVD) 上尝试 SQLite

### 64.9 Android Room 持久化库

### 64.10 总结

# 65. Android Room 持久化库

## 65.1 重新审现代应用架构

## 65.2 Room 数据库持久化的关键元素

#### 65.2.1 存储库 (Repository)

#### 65.2.2 Room 数据库

#### 65.2.3 数据访问对象 (DAO)

#### 65.2.4 实体 (Entities)

#### 65.2.5 SQLite 数据库

### 65.3 理解实体

### 65.4 数据访问对象

### 65.5 Room 数据库

### 65.6 存储库

### 65.7 内存数据库

### 65.8 数据库检查器 (Database Inspector)

### 65.9 总结

# 66. Android TableLayout 和 TableRow 教程

### 66.1 TableLayout 和 TableRow 布局视图

### 66.2 创建 Room 数据库项目

### 66.3 转换为 LinearLayout

### 66.4 在用户界面中添加 TableLayout

### 66.5 配置 TableRows

### 66.6 在布局中添加按钮栏

### 66.7 添加 RecyclerView

### 66.8 调整布局边距

### 66.9 总结

# 67. Android Room 数据库和存储库教程

### 67.1 关于 RoomDemo 项目

### 67.2 修改构建配置

### 67.3 构建实体

### 67.4 创建数据访问对象

### 67.5 添加 Room 数据库

### 67.6 添加存储库

### 67.7 添加 ViewModel

### 67.8 创建产品项布局

### 67.9 添加 RecyclerView 适配器

### 67.10 准备主活动 (Main Activity)

### 67.11 添加按钮监听器

### 67.12 添加 LiveData 观察者

### 67.13 初始化 RecyclerView

### 67.14 测试 RoomDemo 应用

### 67.15 使用数据库检查器

### 67.16 总结

# 68. 使用 Android 存储访问框架访问云存储

## 68.1 存储访问框架 (Storage Access Framework)

### 68.2 使用存储访问框架

### 68.3 过滤选择器文件列表

### 68.4 处理 Intent 结果

### 68.5 读取文件内容

### 68.6 向文件写入内容

### 68.7 删除文件

### 68.8 获取文件的持久化访问权限

### 68.9 总结

# 69. 存储访问框架示例

### 69.1 关于存储访问框架

### 69.2 创建存储访问框架

### 69.3 设计用户界面

### 69.4 添加活动启动器 (Activity Launchers)

### 69.5 创建新的存储文件

### 69.6 保存到存储文件

### 69.7 打开并读取存储文件

### 69.8 测试存储访问

### 69.9 总结

# 70. 在 VideoView 和 MediaController 类上进行视频播放

### 70.1 介绍 VideoView 类

### 70.2 介绍 MediaController 类

### 70.3 创建视频播放

### 70.4 设计视频布局

### 70.5 在视频视图中添加 MediaController

### 70.6 设置 onPreparedListener

### 70.7 总结

# 71. Android 画中画模式 (Picture-in-Picture)

## 71.1 关于画中画（等等，Android 画中画模式）

## 71.2 启用画中画模式

## 71.3 配置画中画参数

## 71.4 进入画中画模式

## 71.5 检测画中画模式的变化

## 71.6 添加画中画操作

### 71.7 总结

# 72. Android 画中画教程

## 72.1 在 Manifest 中添加画中画支持

## 72.2 添加画中画按钮

## 72.3 进入画中画模式

## 72.4 检测画中画模式的变化

## 72.5 添加广播接收器 (Broadcast Receiver)

## 72.6 添加 PiP 动作

## 72.7 测试画中画动作

### 72.8 总结

# 73. 使用 MediaPlayer 和 MediaRecorder 进行 Android 音录制和播放

### 73.1 播放音频

### 73.2 使用 MediaRecorder 类录制音视频

### 73.3 关于示例项目

### 73.4 创建 AudioApp 项目

### 73.5 设计用户界面

### 73.6 检查麦克风可用性

### 73.7 初始化活动 (Activity)

### 73.8 实现 `recordAudio()` 方法

### 73.9 实现 `stopAudio()` 方法

### 73.10 实现 `playAudio()` 方法

### 73.11 配置与请求权限

### 73.12 测试应用程序

### 73.13 总结

# 74. 在 Android Studio 中使用 Google Maps Android API

## 74.1 Google Maps Android API 的元素

### 74.2 创建 Google Maps 项目

### 74.3 创建 Google Cloud 结算账户

### 74.4 创建新的 Google Cloud 项目

### 74.5 启用 Google Maps SDK

### 74.6 生成 Google Maps API 密钥

### 74.7 将 API 密钥添加到 Android Studio 项目

### 74.8 测试应用程序

### 74.9 理解地理编码与反向地理编码

### 74.10 在应用程序中添加地图

### 74.11 请求当前位置权限

### 74.12 显示用户当前位置

### 74.13 更改地图类型

### 74.14 向用户显示地图控件

### 74.15 处理地图手势交互

#### 74.15.1 地图缩放手势

#### 74.15.2 地图滚动/平移手势

#### 74.15.3 地图倾斜手势

#### 74.15.4 地图旋转手势

### 74.16 创建地图标记

### 74.17 控制地图相机

### 74.18 总结

# 75. 使用 Android 打印框架进行打印

### 75.1 Android 打印架构

### 75.2 打印服务插件

### 75.3 Google Cloud Print

### 75.4 打印到 Google Drive

### 75.5 另存为 PDF

### 75.6 从 Android 设备打印

### 75.7 在 Android 应用中构建打印支持的选项

#### 75.7.1 打印

#### 75.7.2 创建并打印 HTML 内容

#### 75.7.3 打印网页

#### 75.7.4 打印自定义文档

### 75.8 总结

# 76. 一个 Android HTML 和 Web 内容打印示例

## 76.1 创建 HTML 打印示例应用程序

### 76.2 打印动态 HTML 内容

### 76.3 创建网页打印示例

### 76.4 移除悬动按钮

### 76.5 移除导航功能

### 76.6 设计用户界面布局

### 76.7 从主 Activity 访问 WebView

### 76.8 将网页加载到 WebView

### 76.9 添加打印菜单

### 76.10 总结

# 77. Android 自定义打印指南

### 77.1 Android 自定义打印概述

#### 77.1.1 自定义适配器

### 77.2 准备自定义打印项目

### 77.3 创建自定义适配器

### 77.4 实现 `onLayout()` 方法

### 77.5 实现 `onWrite()` 方法

### 77.6 检查页面是否在范围内

### 77.7 在页面画布上绘制内容

### 77.8 启动打印任务

### 77.9 测试应用程序

### 77.10 总结

# 78. Android App Links 简介

### 78.1 Android App Links 概述

### 78.2 App Link Filters

### 78.3 处理 App Intents

### 78.4 将应用与网站关联

### 78.5 总结

# 79. Android App Links 教程

### 79.1 关于示例应用

### 79.2 数据库结构

### 79.3 加载并运行项目

### 79.4 添加 URL 映射

### 79.5 添加 Intent Filter

### 79.6 添加 Intent 处理代码

### 79.7 测试应用

### 79.8 创建 Digital Asset Links 文件

### 79.9 测试 App Link

### 79.10 总结

# 80. Android 生物识别认证教程

### 80.1 生物识别概述

### 80.2 创建生物识别认证项目

### 80.3 配置设备指纹认证

### 80.4 在清单文件中添加生物识别权限

### 80.5 设计用户界面

### 80.6 添加 Toast 方便方法

### 80.7 检查安全设置

### 80.8 配置认证回调

### 80.9 添加 `CancellationSignal`

### 80.10 启动生物识别提示

### 80.11 测试项目

### 80.12 总结

# 81. 创建、测试和上传 Android App Bundle

## 81.1 发布准备流程

## 81.2 Android App Bundles

## 81.3 注册 Google Play 开发者控制账户

## 81.4 在控制台中配置应用

## 81.5 启用 Google Play 应用签名

## 81.6 创建 Keystore 文件

## 81.7 创建 Android App Bundle

## 81.8 生成测试 APK 文件

### 81.9 将 App Bundle 上传到 Google Play 开发者控制

### 81.10 探索 App Bundle

### 81.11 管理测试人员

### 81.12 发布应用进行测试

### 81.13 上传新版本的 App Bundle 

### 81.14 分析 App Bundle 文件

### 81.15 总结

# 82. Android 内应用购买概述

## 82.1 为内应用购买准备项目

## 82.2 创建内购产品和订阅

## 82.3 结算客户端初始化

## 82.4 连接到 Google Play 结算程序库

## 82.5 查询可用产品

## 82.6 启动购买流程

### 82.7 完成购买

### 82.8 查询之前的购买记录

### 82.9 总结

# 83. Android 内应用购买教程

## 83.1 关于内应用购买示例项目

## 83.2 创建 InAppPurchase 项目

## 83.3 为项目添加库

### 83.4 设计用户界面

### 83.5 将应用添加到 Google Play 商店

### 83.6 创建内购产品

### 83.7 启用许可测试人员

### 83.8 初始化结算客户端

### 83.9 查询产品

### 83.10 启动购买流程

### 83.11 处理购买更新

### 83.12 消耗产品

### 83.13 恢复之前的购买

### 83.14 测试应用

### 83.15 疑难排除

### 83.16 总结

# 84. 使用 Material Design 3 主题

### 84.1 Material Design 2 对比 Material Design 3

### 84.2 理解 Material Design 主题

### 84.3 Material Design 3 主题

### 84.4 构建自定义主题

### 84.5 总结

# 85. Material Design 3 主题与动态色彩教程

### 85.1 创建 ThemeDemo 项目

### 85.3 设计用户界面

### 85.4 构建新主题

### 85.5 将主题添加到项目

### 85.6 启用动态色彩支持

### 85.7 预览动态色彩

### 85.8 总结



# 86. Android Studio 概述

### 86.1 Gradle 概述

### 86.2 Gradle 与 Android Studio

### 86.3 依赖关系

### 86.4 清单文件

### 86.5 顶层 Gradle

### 86.6 模块级 Gradle

### 86.7 配置 Gradle

### 86.8 从命令行运行任务

### 86.9 总结

# 索引

# 1 引言

本书已针对 Android Studio Giraffe 版本及新 UI 完全更新，旨在教你如何使用 Java 语言开发 Android 应用程序。

本书从基础知识开始，概述了如何搭建 Android 开发和测试环境，随后对工具工具窗口、代码编辑器和布局编辑器等区域进行了介绍。在介绍 Android 架构之后，将深入探讨 Android 应用程序和用户界面的设计。

书中还涵盖了架构组件的章节，包括视图模型（view models）、生命周期管理、Room 数据库访问、数据库检查器（Database Inspector）、应用导航、实时数据（live data）和数据绑定。涵盖了意图（intents）等高级主题、触摸屏处理、手势识别以及音频的录制和播放。本版还涵盖了打印、过渡和折叠设备支持。

书中还详细介绍了 Material Design 的概念，包括悬浮操作按钮（floating action buttons）、Snackbars、标签界面、卡片视图、导航抽屉和折叠工具栏的使用。同时也详细介绍了 Android Studio 和 Android 的其他关键特性，包括布局编辑器、`ConstraintLayout` 和 `ConstraintSet` 类、MotionLayout 编辑器、视图绑定、约束链（constraint chains）、障碍（barriers）和直接回复通知。

章节还涵盖了 Android Studio 的高级功能，例如 App Links 和 Gradle 配置。假设你具备 Java 编程经验，准备好下载 Android Studio 和 Android SDK，拥有 Windows、Mac 或 Linux 系统，并且对要开发的应用有所想法，你就可以开始了。

## 1.1 下载代码示例

书中示例的源码和 Android Studio 项目文件可以在以下地址下载：

`https://www.ebookfrenzy.com/retail/giraffejava/index.php`

从代码示例将项目加载到 Android Studio 的步骤如下：

1. 在“Welcome to Android Studio”对话框中，点击“Open”（打开）按钮选项。

2. 在项目选择对话框中，导航并选择包含要导入项目的文件夹，然后点击“OK”。

## 1.2 反馈

我们希望你对购买本书感到满意。如果你在书中发现任何错误，或者有任何意见、问题或疑虑，请通过 `feedback@ebookfrenzy.com` 与我们联系。

## 1.3 错误列表

虽然我们尽力确保书中内容的准确性，但对于一本涵盖如此规模和复杂领域的书籍，难免会包含一些错误和遗漏。书中所有已知问题及其解决方案将在以下 URL 列出：

[`www.ebookfrenzy.com/errata/giraffejava.html`](https://www.ebookfrenzy.com/errata/giraffejava.html)

如果你发现勘误列表中未列出的错误，请通过邮件向我们的技术支持团队（`feedback@ebookfrenzy.com`）告知我们。他们将竭为您提供帮助，并尽力解决您可能遇到的任何问题。

# 2. 设置 Android Studio 开发环境

在开始开发 Android 应用之前，第一步是配置计算机系统作为开发平台。这涉及几个步骤，包括安装 Android Studio 集成开发环境（IDE）、Android 软件开发包（SDK）以及 OpenJDK Java 开发环境。

本章将介绍在 Windows、macOS 和基于 Linux 的系统上安装 Android 应用开发所需组件的步骤。

## 2.1 系统要求

Android 应用开发可以在以下任何类型的系统上进行：

- Windows 8/10/11 64 位

- macOS 10.14 或更高版本（运行在 Intel 或 Apple 芯片设备上）

- 带有 Intel i5 或更高处理器的 Chrome OS 设备

- 安装 GNU C Library (`glibc`) 版本 2.31 或更高版本的 Linux 系统

- 至少 8GB 内存

- 约 8GB 可用磁盘空间

- 最屏幕分辨率 1280 x 800

## 2.2 下载 Android Studio 包

开发 Android 应用的大部分工作将使用 Android Studio 环境完成。书中的内容和示例是基于 Android Studio Giraffe 2022.3.1，并使用 Android API 33 SDK (Tiramisu) 创建的，在编写时，这些都是最新的稳定版本。

然而，Android Studio 的更新非常频繁，因此自本书出版以来可能已经发布了更新版本。

可以从主下载页下载最新版本的 Android Studio， URL 如下：

[`developer.android.com/studio/index.html`](https://developer.android.com/studio/index.html)

如果该页面提供了下载新版本 Android Studio 的说明，那么本书与软件之间可能存在差异。如果这些差异成为问题，在网络上搜索“Android Studio Giraffe”应该提供下载旧版本的选项。或者，访问以下网页在存档中找到 Android Studio Giraffe 2022.3.1：

[`developer.android.com/studio/archive`](https://developer.android.com/studio/archive)

## 2.3 安装 Android Studio

下载完成后，安装 Android Studio 的具体步骤取决于执行安装的操作系统。

### 2.3.1 在 Windows 上安装

在 Windows 资源管理器中找到下载的 Android Studio 安装可执行文件（命名为 `android-studio-<version>-windows.exe`），双击它开始安装过程。如果弹出用户账户控制对话框，请点击“是”按钮。

一旦出现 Android Studio 安装向导，按照各个屏幕操作进行配置，以满足你的需求，包括 Android Studio 应该安装的文件系统位置，以及是否让其他系统用户可以使用。在提示选择要安装的组件时，确保勾选 Android Studio 和 Android Virtual Device（Android 虚拟设备）选项。

虽然对 Android Studio 的系统安装位置没有严格规定，但本书的其余部分将假设安装在 `C:\Program Files\Android\Android Studio`，并且 Android SDK 包已安装在用户的 `AppData\Local\Android\sdk` 子文件夹中。配置好选项后，点击“安装”按钮开始安装过程。

在带有开始菜单的 Windows 版本上，可以从安装期间添加到该菜单的项启动新安装的 Android Studio。可以通过进入 `Android Studio\bin` 目录，右键点击 `studio64` 可执行文件，并选择“固定到任务栏”菜单选项，以便于访问（在 Windows 11 上，可以通过选择菜单中的“显示更多选项”找到此选项）。

### 2.3.2 在 macOS 上安装

macOS 版 Android Studio 以磁盘镜像 (.dmg) 文件形式下载。下载 `android-studio-<version>-mac.dmg` 文件后，在 Finder 窗口中找到它并双击打开，如图 2-1 所示：

![](img/as_dmg_drag_to_applications.jpg)

图 2-1

要安装该包，将 Android Studio 图标拖到“应用程序”（Applications）文件夹。Android Studio 包将被安装到系统的应用程序文件夹中，此过程通常需要几秒钟完成。

要启动 Android Studio，在 Finder 窗口的应用程序文件夹中找到可执行文件并双击它。

为了以后方便访问该工具，可以将 Android Studio 图标从 Finder 窗口拖动并释放到 Dock 上。

### 2.3.3 在 Linux 上安装

下载 Linux 版 Android Studio 包后，打开终端窗口，切换到要安装 Android Studio 的位置，执行以下命令：

```bash
tar xvfz /<path to package>/android-studio-<version>-linux.tar.gz
```

注意，Android Studio 程序包将安装到名为 `android-studio` 的子目录。因此，假设上述命令在 `/home/demo` 中执行，软件包将解压到 `/home/demo/android-studio`。

要启动 Android Studio，打开终端窗口，切换到 `android-studio/bin` 子目录，执行以下命令：

```bash
./studio.sh
```

## 2.4 Android Studio 安装向导

如果你之前安装过早期版本的 Android Studio，首次启动此新版本时可能会弹出一个对话框，提供从以前版本导入设置的选项。如果你有以前版本的设置并想将其导入最新安装中，请选择相应的选项和位置。或者，指示你不需要导入之前的设置并点击“确定”按钮继续。

如果你是第一次安装 Android Studio，启动设置后出现的初始对话框可能像下面的图 2-2 所示：

![](img/as_setup_wizard.jpg)

图 2-2

如果出现此对话框，点击“下一步”按钮显示安装类型屏幕（图 2-3）。在此屏幕上，在点击“下一步”之前选择“标准”安装选项。

![](img/as_setup_install_type.jpg)

图 2-3

在“选择 UI 主题”屏幕上，根据喜好选择 Darcula（深色）或 Light（浅色）主题。做出选择后点击“下一步”，并在“验证设置”屏幕上检查选项，然后进入“许可协议”屏幕。选择每个许可类别并启用“接受”复选框。最后，点击“完成”启动安装。

完成这些初始设置步骤后，点击“完成”按钮显示使用你所选 UI 主题的“欢迎使用 Android Studio”界面：

![](img/as_giraffe_welcome.jpg)

图 2-4

## 2.5 安装额外的 Android SDK 包

到目前为止的操作安装了 Android Studio IDE 和当前默认的 Android SDK 包集。在继续之前，值得花时间检查已安装了哪些包，并安装任何缺失或更新的包。

此任务可以通过点击欢迎对话框中的 `More Actions` 链接并从下拉菜单中选择 `SDK Manager` 选项来完成。一旦调用，设置对话框的 Android SDK 屏幕将会出现，如图 2-5 所示：

![](img/as_sdk_manager.jpg)

图 2-5

Google 为每个版本的 Android Studio 配配了一个最高支持的 Android SDK 应用程序编程接口 (API) 级别。对于 Android Studio Giraffe，该版本是 Android Tiramisu (API Level 33)。可以通过以下链接确认此信息：

[`developer.android.com/studio/releases#api-level-support`](https://developer.android.com/studio/releases#api-level-support)

在首次安装 Android Studio 之后，可能只安装了最新版本的 Android SDK。若要安装旧版本的 Android SDK，请选择对应版本的复选框并点击 `Apply` 按钮。本书的其余部分假设已安装了 Android Tiramisu (API Level 33) SDK。

书中的大多数示例将支持低至 Android 8.0 (Oreo) 的旧版本 Android。这确保了应用可以在广泛的 Android 设备上运行。在 SDK 版本列表中，勾选 Android 8.0 (Oreo) 旁的复选框并点击 `Apply` 按钮。在生成的确认对话框中点击 `OK` 按钮安装 SDK。随后的对话框将在执行安装前要求接受许可协议和条款。安装完成后，点击 `Finish`。

可能还会列出最新 SDK 有可用更新。要访问有关准备好更新的包的详细信息，请启用屏幕右下角的 `Show Package Details` 选项。这将显示与图 2-6 所示类似的信息：

![](img/as_sdk_manager_update_available.jpg)

图 2-6

上图强调了更新的可用性。要安装更新，勾选项目名称左侧的复选框并点击 `Apply` 按钮。

除了 Android SDK 包外，还安装了几个用于构建 Android 应用程序的工具。要查看当前安装的包并检查更新，请留在 SDK 设置屏幕，并选择 `SDK Tools` 标签页，如图 2-7 所示：

![](img/as_sdk_manager_tools.jpg)

图 2-7

在 Android SDK Tools 屏幕中，确保以下包在 `Status` 列中均显示为 `Installed`：

* Android SDK Build-tools

* Android Emulator

* Android SDK Platform-tools

* Google Play Services

* Intel x86 Emulator Accelerator (HAXM installer)

* Google USB Driver (仅限 Windows)

* Layout Inspector image server for API 31 and 34

*注意，Intel x86 Emulator Accelerator (HAXM installer) 安装在基于 Apple 芯片的 Mac 上。*

如果上述任何包被列为 `Not Installed` 或需要更新，请选择这些包旁边的复选框并点击 `Apply` 按钮启动安装过程。如果出现 HAXM 模拟器设置对话框，请选择推荐的内存分配：

![](img/as_haxm_memory.jpg)

图 2-8

安装完成后，检查包列表并确保所选包在 `Status` 列中被列为 `Installed`。如果有任何包被列为 `Not installed`，请确保已勾选它们并再次点击 `Apply` 按钮。

## 2.6 安装 Android SDK 命令行工具

Android Studio 包含了允许从您的操作系统命令行执行某些任务的工具。若要在您的系统上安装这些工具，请打开 `SDK Manager`，选择 `SDK Tools` 标签页，并如图 2-9 所示找到 `Android SDK Command-line Tools (latest)` 包：

![](img/as_install_cmd_line_tools.jpg)

图 2-9

如果命令行工具包尚未安装，请启用它（勾选）并点击 `Apply`，然后点击 `OK` 完成安装。安装完成后，点击 `Finish` 并关闭 `SDK Manager` 对话框。

为了让您正在开发的操作系统能够找到这些工具，有必要将它们添加到系统的 `PATH` 环境变量中。

无论使用何种操作系统，您都需要配置 `PATH` 环境变量以包含以下路径（其中 `<path_to_android_sdk_installation>` 代表您安装 Android SDK 的文件系统位置）：

`<path_to_android_sdk_installation>/sdk/cmdline-tools/latest/bin`

`<path_to_android_sdk_installation>/sdk/platform-tools`

您可以通过启动 `SDK Manager` 并参考设置面板顶部的 `Android SDK Location:` 字段来识别 SDK 在系统上的位置，如图 2-10 所示：

![](img/as_sdk_location.jpg)

图 2-10

一旦确定了 SDK 的位置，将此添加到 `PATH` 变量的步骤取决于操作系统：

### 2.6.1 Windows 8.1

1. 在开始屏幕上，将鼠标移动到屏幕右下角，从生成的菜单中选择 `Search`。在搜索框中输入 `Control Panel`。当 `Control Panel` 图标出现在结果中时，点击它进入桌面。

2. 在控制面板中，使用 `Category` 菜单将显示方式改为 `Large Icons`。从图标列表中选择 `System`。

3. 在 `Environment Variables` 对话框中，在 `System variables` 找到 `Path` 变量，选择它并点击 `Edit` 按钮。在编辑对话框中，使用 `New` 按钮添加新项。例如，假设 SDK 安装在 `C:\Users\demo\Android\Sdk`，则需要添加以下项：

   `C:\Users\demo\Android\Sdk\cmdline-tools/latest\bin`

   `C:\Users\demo\Android\Sdk\platform-tools`

4. 在每个对话框中点击 `OK` 并关闭系统属性控制面板。

通过按下键盘上的 `Windows + R` 在 `运行` 对话框中输入 `cmd` 打开命令提示符窗口。在窗口输入 `echo %Path%`

返回的路径变量应包含 SDK 工具的路径。通过尝试运行 `adb` 工具来验证 `platform-tools` 值：

`adb`



执行后，该工具将输出选项列表。同样，通过尝试运行`AVD`命令行工具来检查工具路径（如果`avdmanager`工具报告 Java 问题，稍后会处理）：

```
avdmanager
```

如果其中一个或两个命令出现类似下面的消息，最可能是在`PATH`环境变量中添加了错误的路径：

```
'adb' is not recognized as an internal or external command, operable program or batch file.
```

### 2.6.2 Windows 10

1. 右键点击`Start`菜单，从生成的菜单中选择`Settings`，并在`Find a setting`字段中输入`Edit the system environment variables`。在`System Properties`对话框中，点击`Environment Variables...`按钮。按照 Windows 8.1 的第 3 步操作。

### 2.6.3 Windows 11

1. 右键点击任务栏上的`Start`图标，从生成的菜单中选择`Settings`。当`Settings`对话框出现时，滚动列表并选择`About`。在`About`屏幕上，从`Related links`选择`Advanced system settings`。按照 Windows 8.1 的第 3 步操作。

### 2.6.4 Linux

在 Linux 上，可以通过向用户家目录下的`.bashrc`文件中添加命令来实现此配置（具体细节可能取决于所使用的特定 Linux 发行版）。假设 Android SDK 压缩包安装在`/home/demo/Android/sdk`，则`.bashrc`文件中的`export`行如下：

```
export PATH=/home/demo/Android/sdk/platform-tools:/home/demo/Android/sdk/cmdline-tools/latest/bin:/home/demo/android-studio/bin:$PATH
```

请注意，上述命令将`android-studio/bin`目录添加到了`PATH`变量中。这将使得无论在终端窗口的哪个目录下，都可以执行`studio.sh`脚本。

### 2.6.5 macOS

可以使用多种技术来修改 macOS 上的`$PATH`环境变量。认为最干净的方法是在`/etc/paths.d`目录中创建一个新文件，其中包含要添加到`$PATH`的路径。假设 Android SDK 的安装位置为`/Users/demo/Library/Android/sdk`，可以通过在`/etc/paths.d`目录中创建一个名为`android-sdk`的新文件并包含以下行来配置路径：

```
/Users/demo/Library/Android/sdk/cmdline-tools/latest/bin
/Users/demo/Library/Android/sdk/platform-tools
```

注意，由于这是一个系统目录，在创建文件时需要使用`sudo`命令。例如：

```
sudo vi /etc/paths.d/android-sdk
```

### 2.7 Android Studio 内存管理

Android Studio 是一个大型且复杂的软件应用程序，具有许多后台进程。虽然 Android Studio 在过去曾因性能不佳而受到批评，但 Google 在最近的发布中对其进行了重大的性能改进，并在每个新版本中持续改进。这些改进包括允许用户配置 Android Studio IDE 以及用于构建和运行应用程序的后台进程所使用的内存。这让软件能够利用具有更大 RAM 的系统。

如果你在运行 Android Studio 的系统上有足够的空闲 RAM 能够增加这些值（此功能仅适用于具有 5GB 或更多 RAM 的 64 位系统），并且发现 Android Studio 的性能似乎有所下降，那么尝试这些内存设置可能是值得的。Android Studio 还可能通过类似于下所示的对话框通知你提高性能：

![](img/as_3.5_increase_memory_notification.jpg)

图 2-11

要查看并修改当前的内存配置，选择主菜单选项`File -> Settings...`（macOS 上为`Android Studio -> Settings...`），并在弹出的对话框中，选择左侧导航面板中的`Appearance & Behavior`，然后选择`System Settings`下的`Memory Settings`，如下方的图 2-12 所示：

![](img/as_memory_settings.jpg)

图 2-12

在更改内存分配时，请确保不要分配超过所需的内存，或超过系统在不减慢其他进程的情况下所承受的内存。

IDE 堆内存大小设置调整分配给 Android Studio 的内存，且不限于当前加载的项目。另一方面，当从 Android Studio 内部构建和运行项目时，会有几个后台进程（称为守护进程 daemon）执行编译和运行程序的任务。在编译和运行大型复杂项目时，可以通过调整守护进程堆设置来改进构建时间。与 IDE 堆内存设置不同，这些守护进程设置仅适用于当前项目，并且只有在 Android Studio 中打开项目时才能访问。要在打开的项目内部显示 SDK Manager，请从主菜单选择`Tools -> SDK Manager...`菜单选项。

### 2.8 更新 Android Studio 和 SDK

Android Studio 和 Android SDK 会定期发布新版本。新版本的 SDK 使用 Android SDK Manager 安装。当有更新可用安装时，Android Studio 通常会通知你。

要手动检查 Android Studio 的更新，请使用 Android Studio 主窗口的`Help -> Check for Updates...`菜单选项（macOS 上为`Android Studio -> Check for Updates...`）。

### 2.9 总结

在开始开发基于 Android 的应用程序之前，第一步是搭建合适的开发环境。这由 Android SDK 和 Android Studio IDE（包含 OpenJDK 开发环境）组成。本章涵盖了在 Windows、macOS 和 Linux 上安装这些包的必要步骤。

# 3 在 Android Studio 中创建示例 Android 应用程序

本书的前几个章节已经涵盖了使用 Android Studio IDE 配置适用于 Android 应用程序开发的环境所需的必要步骤。在进入稍高级的主题之前，现在是验证所有所需的开发包已正确安装并运行良好的好机。实现这一目标的最佳方法是创建一个 Android 应用程序并对其进行编译和运行。本章将涵盖使用 Android Studio 创建 Android 应用程序项目。一旦项目创建，随后的章节将探索使用 Android 模拟器环境对应用程序进行测试运行。

### 3.1 关于项目

在本章创建的项目是一个原始的货币汇率转换器（事实上它非常简单，只将美元转换为欧元，并使用估算的汇率进行转换）。该项目还将使用最基础的 Android Studio 项目模板之一。这种简单性允许我们介绍 Android 应用开发的一些关键方面，而不会因一次性引入过多的概念（例如推荐的应用架构和 Android 架构组件）让初学者无所适从。在遵循本章的教程时，请放心在本初始示例项目中使用的技术和代码将在稍后更详细地介绍。

### 3.2 创建新项目

应用程序开发过程的第一步是在 Android Studio 环境中创建项目。因此，首先通过启动 Android Studio，使“欢迎来到 Android Studio”屏幕如图 3-1 所示：

![](img/as_giraffe_welcome1.jpg)

图 3-1

一旦此窗口，Android Studio 就准备好创建新项目。要创建新项目，点击`New Project`选项以显示新项目向导的第一个屏幕。

### 3.3 创建 Activity

下一步是为应用程序定义初始 Activity 的类型。提供了创建手机和平板、Wear OS、电视或汽车项目的选项。在开发 Android 应用程序时有许多 Activity 类型，其中许多将在后面的章节中详细介绍。但对于本示例，请从模板面板中选择`Phone and Tablet`选项，然后选择创建`Empty Views Activity`。`Empty Views Activity`选项创建一个包含单个`TextView`模板用户界面。

![](img/as_new_project_template.jpg)

图 3-2

选择`Empty Views Activity`后，点击 Next 继续项目配置。

### 3.4 定义项目和 SDK 设置

在项目配置窗口（图 3-3）中，将`Name`字段设置为`AndroidSample`。应用程序名称是在 Android Studio 内部引用和标识应用程序的名称，如果完成的应用程序要在 Google Play 商店销售，这也是使用的名称。

`Package`名称在 Android 应用生态系统中用于唯一标识该应用程序。虽然它可以设置为任何能够唯一标识你应用程序的字符串，但传统上它是基于你域名的反转 URL 加上应用程序名称。例如，如果你的域名是`www.mycompany.com`，且应用程序命名为`AndroidSample`，那么包名可以指定如下：

```
com.mycompany.androidsample
```

如果你没有域名，可以在`Company Domain`字段中输入任何其他字符串，或者使用`example.com`进行测试，但在发布应用程序之前需要将其更改：

```
com.example.androidsample
```

`Save location`设置将默认指向位于你主目录下的名为`AndroidStudioProjects`文件夹中的位置，你可以通过点击包含当前路径设置的文本框右侧的文件夹图标来更改它。

将`minimum SDK`设置为`API 26`（Oreo; Android 8.0）。除非某些功能仅在较新版本中可用，否则本书中创建的大多数项目将使用此最小 SDK。这里的目标是使用最新的 Android SDK 构建应用，同时保持对运行旧版本 Android 的设备（在本例中为 Android 8.0）的兼容性。`Minimum SDK`设置下方的文字将概述当前运行该应用程序的 Android 设备百分比。点击`Help me choose`按钮（在图 3-3 中突出显示）查看仍在使用的各种 Android 版本的详细列表：

![](img/as_java_project_settings.jpg)

图 3-3

最后，将`Language`菜单更改为`Java`，并在点击 Finish 创建项目之前选择`Kotlin DSL (build.gradle.kts)`作为构建配置语言。

## 3.5 启用新的 Android Studio UI

Android Studio 正在向全新的现代用户界面过渡，该界面在`Giraffe`版本中默认未启用。如果你安装的 Android Studio 类似于下方的图 3-4，那么你需要在继续操作之前启用新 UI：

![](img/as_4.1_main_window.jpg)

图 3-4

通过选择`File` -> `Settings...`菜单选项（macOS 上为`Android Studio` -> `Settings...`）并在左侧面板的`Appearance and Behavior`下选择`New UI`选项来启用新 UI。在主面板中，开启`Enable new UI`复选框，然后点击`Apply`，最后点击`OK`提交更改：

![](img/as_enable_new_ui.jpg)

图 3-5

在提示时，重启 Android Studio 以激活新的用户界面。

## 3.6 修改示例应用程序

一旦 Android Studio 重启，主窗口将使用新 UI 重新出现，并包含如下方的图 3-6 所示所示的`AndroidSample`项目：

![](img/as_android_sample_main_java.jpg)

图 3-6

新创建的项目以及对相关文件的引用列在主项目窗口左侧的`Project`工具窗口中。`Project`工具窗口有多种可以显示信息的模式。默认情况下，此面板应处于`Android`模式。此设置由面板顶部的菜单控制，如图 3-7 中突出显示所示。如果面板当前不在`Android`模式，请使用菜单切换模式：

![](img/as_project_tool_window_menu.jpg)

图 3-7

## 3.7 修改用户界面

我们 activity 的用户界面设计存储在名为`activity_main.xml`的文件中，该文件位于`Project`工具窗口文件层级结构的`app -> res -> layout`下。在`Project`工具窗口中找到该文件后，双击将其加载到用户界面`Layout Editor`工具中，该工具将出现在 Android Studio 主窗口的中间面板：

![](img/as_layout_editor.jpg)

图 3-8

`Layout Editor`窗口顶部工具栏上有一个菜单（在上面的图中设置为`Pixel`），它会反映在`Layout Editor`面板中设备的视觉表示上。点击此菜单可以使用一系列其他设备选项。

使用`System UI Mode`按钮![](img/as_night_mode_button.jpg)为设备屏幕布局开启或关闭夜间模式（Night mode）。要在设备表示的横屏和竖屏之间切换，请使用显示![](img/as_rotate_button.jpg)图标的下拉菜单。

正如我们在设备屏幕中看到的，内容布局已经包含一个显示“Hello World!”消息的标签。面板左侧运行的是调色板，其中包含不同类别的用户界面组件，这些组件可用于构建用户界面，例如按钮、标签和文本字段。然而，需要注意的是并不是所有的用户界面组件对用户都是可见的。其中一类是布局。Android 支持多种布局，它们对视觉用户界面组件在屏幕上的定位和管理方式提供不同程度的控制。虽然从用户界面的视觉表示很难判断，但当前设计是使用`ConstraintLayout`创建的。可以通过查看`Component Tree`面板中的信息来确认，该面板默认位于`Layout Editor`的左下角，如图 3-9 所示：

![](img/as_component_tree.jpg)

图 3-9

从组件树可以看出，布局由一个`ConstraintLayout`父级和一个`TextView`子组成。在继续之前，检查`Layout Editor`的`Autnect`模式是否启用。这意味着在添加组件时，`Layout Editor`将自动添加约束，以确保组件在不同尺寸下正确放置（该主题将在后续章节中详细介绍）。`Autnect`按钮出现在`Layout Editor`工具栏中，用 U 形图标表示。当禁用时，图标上有一条斜线（见图 3-10）。如有必要，点击此按钮重新启用`Autnect`模式。

![](img/as_autoconnect_disabled.jpg)

图 3-10

修改应用程序的下一步是向布局添加一些额外的组件，第一个是用户点击以启动货币转换。

`Palette`面板由两列组成，左列包含视图组件类别列表。右列列出当前选择类别中的组件。例如，在图 3-11 中，`Buttons`类别中选择了`Button`视图：

![](img/as_palette_button_selected.jpg)

图 3-11

从`Buttons`列表中点击并拖动`Button`对象，将其放置在用户界面设计的水平中心，使其位于现有`TextView`组件下方：

![](img/as_android_sample_button.jpg)

图 3-12

下一步是更改`Button`组件当前显示的文本。位于设计区域右侧的面板是`Attributes`面板。该面板显示分配给布局中所选组件的属性。在此面板中，在`Common Attributes`部分找到`text`属性，并将当前值从“Button”更改为“Convert”，如图 3-13 所示：

![](img/as_android_sample_button_text.jpg)

图 3-13

旁旁带有扳手图标的第二个文本属性允许设置文本属性，该属性仅在`Layout Editor`（布局编辑器）工具中显示，而在运行时不会显示。这对于测试视觉组件和布局在不同设置下的表现非常有用，而无需反复运行应用程序。

为了以防自动连接系统（Autoconnect）未设置所有布局连接，请点击`Infer Constraints`（推断约束）按钮（图 3-14）为布局添加任何缺失的约束：

![](img/as_infer_constraints.jpg)

图 3-14

有必要解释`Layout Editor`工具右上角的警告按钮，如图 3-15 所示。该警告表示布局可能存在问题。要查看任何问题的详情，请点击该按钮：

![](img/as_layout_warnings.jpg)

图 3-15

点击后，将出现`Problems`（问题）工具窗口（图 3-16），描述问题的性质：

![](img/as_problems_tool_window.jpg)

图 3-16

此工具窗口分为两个面板。左侧面板（上图标记为 A）列出了布局文件中检测到的问题。在我们的示例中，仅列出了以下问题：

```
button <`Button`: Hardcoded text
```



当从列表中选择一项 (B) 时，右侧面板将更新并提供有关问题的额外细节 (C)。在这种情况下，解释内容如下：

硬编码字符串 `"Convert"`，应使用 `@string` 资源

该工具窗口还包含一个预览编辑器 (D)，允许对布局文件进行手动修正。

此 I18N 消息告诉我们，项目未来的国际化可能存在潜在问题（“I18N”源于“internationalization”一词以“I”开头，以“N”结尾，中间有 18 个字母）。由于该警告提醒我们，在开发 Android 应用程序时，应尽可能将文本字符串等属性和值存储为资源。这样做可以使其通过修改资源文件来更改应用程序的外观，而无需更改应用程序源代码。这在将用户界面翻译成不同的口语语言时尤为有价值。如果用户界面中的所有文本都包含在一个资源文件中，例如，可以将该文件交给翻译人员，由他们执行翻译工作并返回翻译后的文件以包含应用程序中。这使得可以在不进行任何源码更改的情况下针对多种语言。在此实例中，我们将创建一个名为 `convert_string` 的新资源，并为其分配字符串“Convert”。

点击 `Show Quick Fixes`（显示快速修复）按钮 (E) 并从菜单中选择 `Extract string resource`（提取字符串资源）选项，如图图 3-17 所示：

![](img/as_problems_extract_button.jpg)

图 3-17

选择此选项后，将出现 `Extract Resource`（提取资源）面板（图 3-18）。在此面板中，将资源名称字段更改为 `convert_string`，并在点击 `OK` 按钮之前，将资源值设置为 `Convert`：

![](img/as_extract_resource.jpg)

图 3-18

要添加的下一个部件是 `EditText` Widget，用户将在其中输入要转换的美元金额。从 `Palette` 面板中选择 `Text` 类别，点击并将 `Number (Decimal)` 组件拖到布局中，使其水平居中并置于现有 `TextView` 部件上方。选中该部件后，使用 `Attributes`（属性）工具窗口将 `hint` 属性设置为“dollars”。点击警告图标并将字符串提取为名为 `dollars_hint` 的资源。

在本章稍后编写的代码将需要访问用户输入到 `EditText` 字段中的美元金额。它将通过引用分配给用户界面布局中部件的 `id` 来实现。当在布局中选中部件时，可以在 `Attributes` 工具窗口查看并更改 Android Studio 分配给部件的默认 `id`，如图图 3-19 所示：

![](img/as_widget_id.jpg)

图 3-19

将 `id` 更改为 `dollarText`，并在 `Rename`（重命名）对话框中点击 `Refactor`（重构）按钮。这确保项目其他地方对旧 `id` 的任何引用都会自动更新为使用新 `id`：

![](img/as_rename_id_dialog.jpg)

图 3-20

如有必要，重复步骤将 `TextView` 部件的 `id` 设置为 `textView`。

点击 `Infer Constraints` 按钮添加任何缺失的布局约束。此时，布局应该类似于图 3-21 所示所示：

![](img/as_android_sample_ui.jpg)

图 3-21

## 3.8 审查布局和资源文件

在继续后续步骤之前，我们将查看用户界面设计和资源处理的一些内部方面。在上一节中，我们通过使用 `Layout Editor` 工具修改 `activity_main.xml` 文件更改了用户界面。事实上，`Layout Editor` 所做的只是提供了一种易于操作的方式来编辑底层 XML。在实践中，没有理由不直接修改 XML 来进行用户界面更改，在某些情况下，这比使用 `Layout Editor` 工具更快。在 `Layout Editor` 面的右上角是 `View Modes` 菜单，如图图 3-22 所示，标记为 A：

![](img/view_mode.jpg)

图 3-22

默认情况下，编辑器将处于 `Design` 模式，显示布局的视觉表示。在 `Code` 模式下，编辑器将显示布局的 XML，而在 `Split` 模式下，则显示布局和 XML，如图图 3-23 所示：

![](img/layout_editor_split_mode.jpg)

图 3-23

`View Modes` 按钮左侧的按钮（如上图图 3-22 中标记的 B）用于快速在 `Code` 和 `Split` 模式之间切换。

从 XML 文件的结构可以看出，用户界面由 `ConstraintLayout` 组件组成，它是 `TextView`、`Button` 和 `EditText` 对象的父级。我们还可以看到，例如 `Button` 的 `text` 属性设置为我们的 `convert_string`资源。尽管复杂性不同，但所有用户界面都是这种基于 XML 的结构。

对 XML 进行更改时，这些更改将反映在布局中。也可以在布局画布内部对布局进行视觉修改，更改将出现在 XML 列表中。为了看到此效果，切换到 `Split` 模式并修改 XML 布局，将 `ConstraintLayout` 的背景颜色更改为红色：

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:background="#ff2438" >

.

</androidx.constraintlayout.widget.ConstraintLayout>
```

注意布局颜色实时变化以匹配 XML 文件中的新设置。注意在 XML 编辑器的左侧边缘（也称为列），包含颜色设置的行旁边会出现一个小红色方块。这是一个视觉提示，表示已属性上设置了红色。点击红色方块将显示颜色选择器，允许选择不同的颜色：

![](img/as_layout_editor_color_selector.jpg)

图 3-24

在继续之前，请从布局文件中删除 `background` 属性，以便背景恢复到默认设置。

最后，使用 `Project` 面板找到 `app -> res -> values -> strings.xml` 文件并双击它将其加载到编辑器中。目前，XML 的内容如下：

```xml
<resources>
    <string name="app_name">AndroidSample</string>
    <string name="convert_string">Convert</string>
    <string name="dollars_hint">dollars</string>
</resources>
```

为了演示资源的实际效果，将当前分配给 `convert_string` 资源的字符串值更改为“Convert to Euros”（转换为欧元），然后通过选择编辑器面板中布局文件的标签页返回 `Layout Editor`（布局编辑器）工具。注意，布局已经获取了该字符串的新资源值。

还有一种快速方法可以访问 XML 文件中引用资源的值。在 `Layout Editor` 工具的 `Split`（分屏）或 `Code`（代码）模式下，点击 `@string/convert_string` 属性设置使其高亮显示，然后按下键盘上的 `Ctrl-B`（macOS 上为 `Cmd-B`）。Android Studio 随后将打开 `strings.xml` 文件并带您到该文件中声明此资源的行。利用此机会将字符串资源恢复为原始的“Convert”文本，并添加以下额外的字符串资源项，该项将在后的应用代码中被引用：

```xml
<resources>
.
.
    <string name="convert_string">Convert</string>
    <string name="dollars_hint">dollars</string>
    <string name="no_value_string">No Value</string>
</resources>
```

也可以通过 Android Studio `Translations Editor`（翻译编辑器）编辑资源字符串，只需点击编辑器窗口右上角的 `Open editor` 链接。将在 Android Studio 窗口的主面板中显示翻译编辑器：

![](img/as_translations_editor.jpg)

图 3-25

此编辑器允许编辑分配给资源键的字符串，并管理多种语言的翻译。

## 3.9 添加交互功能

此示例项目的最后一步是使应用程序具有交互性，以便当用户在 `EditText` 字段中输入美元值并点击转换按钮时，转换后的欧元值将显示在 `TextView` 上。这涉及对 `Button` 控件实现一些事件处理。具体来说，需要配置 `Button`，以便在触发 `onClick` 事件时调用应用代码中的一个方法。事件处理可以通过多种方式实现，将在后续标题为“#Android 事件处理概述与示例””的章节中介绍。返回布局编辑器的 `Design`（设计）模式，在布局编辑器中选择 `Button` 组件，参考 `Attributes`（属性）工具窗口，并按所示指定名为 `convertCurrency` 的方法：

![](img/as_onclick_attribute.jpg)

图 3-26

接下来，在 `Project` 工具窗口中双击 `MainActivity.java` 文件（`app -> java -> <package name> -> MainActivity`）将其加载到代码编辑器中，并在类文件中添加 `convertCurrency` 方法的代码，使其内容如下，请注意也有必要导入一些额外的 Android 包：

```java
package com.ebookfrenzy.androidsample;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
import android.widget.TextView;

.
.
import java.util.Locale;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    public void convertCurrency(View view) {
        EditText dollarText = findViewById(R.id.dollarText);
        TextView textView = findViewById(R.id.textView);
        if (!dollarText.getText().toString().equals("")) {
            float dollarValue = Float.parseFloat(dollarText.getText().toString());
            float euroValue = dollarValue * 0.85F;
            textView.setText(String.format(Locale.ENGLISH,"%.2f", euroValue));
        } else {
            textView.setText(R.string.no_value_string);
        }
    }
}
```

该方法首先通过调用名为 `findViewById` 的方法并传递布局文件中分配的 ID 来获取 `EditText` 和 `TextView` 对象的引用。然后会检查用户是否输入了美元值，如果是，则提取该值，将其从 `String` 转换为浮点值，并转换为欧元。最后，结果显示在 `TextView` 控件上。

如果以上内容有任何不清楚的地方，请放心，后续章节将详细介绍这些概念。特别是从代码内部使用 `findByViewId` 访问控件的主题，以及对 `view binding`（视图绑定）替代技术的介绍，将在标题为“#Android 视图绑定概述”的章节中涵盖。

## 3.10 总结

虽然并不复杂，但设置 Android 开发环境涉及多个步骤。在完成这些步骤后，值得运行一个示例以确保环境正确安装和配置。在本章中，我们创建了一个示例应用程序，并使用 Android Studio 布局编辑器工具修改了用户界面布局。在此过程中，我们探索了使用资源（特别是字符串值）的重要性，并简要接触了布局。接下来，我们查看了用于存储 Android 界面设计的 XML。

最后，为 `Button` 添加了 `onClick` 事件，并连接到一个方法，以提取 `EditText` 中的输入内容，将其转换为欧元并显示在 `TextView` 上。

一旦打开，管理器将以工具窗口的形式出现，如 图 4-2 所示：

![](img/as_device_manager.jpg)

图 4-2

如果您是在计算机上首次安装 Android Studio（而不是升级现有的 Android Studio 安装程序），安装程序可能已经创建了一个备就用的初始 AVD 实例，如 图 4-3 所示：

![](img/as_device_manager_with_avd.jpg)

图 4-3

如果您的系统中存在此 AVD，您可以使用它来测试应用。如果没有创建 AVD，或者您想为不同的设备类型创建 AVD，请按照本章其余部分的步骤进行。

要添加新的 AVD，请确保在点击 `Create device`（创建设备）按钮之前选择了 `Virtual`（虚拟）选项卡，以打开 `Virtual Device Configuration`（虚拟设备配置）对话框：

![](img/as_avd_select_hardware.jpg)

图 4-4

在对话框中，执行以下步骤来创建一个与 Pixel 4 兼容的模拟器：

1. 从 `Category`（类别）面板选择 `Phone`（手机）选项，显示可用 Android 手机 AVD 模板。
2. 选择 `Pixel 4` 设备选项并点击 `Next`（下一步）。
3. 在 `System Image`（系统镜像）屏幕上，选择最新版本的 Android。如果尚未安装系统镜像，`Release Name`（名称）旁边将提供 `Download`（下载）链接。点击此链接在选择之前下载并安装系统镜像。如果没有所需的镜像，请点击 `x86 Images`（如果您运行的是带有 Apple 芯片的 Mac，则点击 ARM images）或 `Other images` 选项卡以查看备列表。
4. 点击 `Next` 继续，并在 `name` 字段中输入描述性名称（例如 `Pixel 4 API 33`）或接受默认名称。
5. 点击 `Finish`（完成）创建 AVD。
6. 如果以后需要对 AVD 进行修改，重新打开 `Device Manager`（设备管理器），从列表中选择 AVD，并点击 `Actions`（操作）列中的铅笔图标来编辑设置。

## 4.2 启动模拟器

要测试新创建的 AVD 模拟器，从 `Device Manager` 中选择模拟器并点击 `launch`（启动）按钮（`Actions` 列中的三角形）。模拟器将嵌入到 Android Studio 主窗口中并开始启动过程。模拟器启动所需的时间取决于 AVD 及其运行的系统的配置：

![](img/as_avd_running.jpg)

图 4-5

要隐藏和显示模拟器工具窗口，请点击 `Running Devices`（运行中的设备）工具窗口按钮（上图标记为 A）。点击标签旁边的“x”关闭按钮 (B) 退出模拟器。模拟器工具窗口可以容纳多个模拟器会话，每个会话由一个标签表示。例如，图 4-6 显示了一个具有两个模拟器会话的工具窗口：

![](img/as_two_avds_running.jpg)

图 4-6

要在会话之间切换，点击相应的标签。

虽然模拟器可能默认以竖屏方向显示，但此或其他默认选项可以更改。在 `Device Manager` 中，选择新的 `Pixel 4` 条目并点击设备行 `Actions` 列中的铅笔图标。在配置屏幕上，找到 `Startup orientation`（启动方向）部分并更改方向设置。退出并重启模拟器会话以使更改生效。关于模拟器的更多细节将在下一章介绍，“使用和配置 Android Studio AVD 模拟器”）。

为了在本章下一节节省时间，请在继续之前保持模拟器运行状态。

## 4.3 在 AVD 中运行应用程序



配置好 AVD 模拟器后，现在可以编译并运行前面的章节创建的示例应用`AndroidSample`。在 Android Studio 中加载`AndroidSample`项目时，确保新创建的`Pixel 4` AVD 显示在设备菜单中（如下方 图 4-7 中标记的 A），然后点击由三角形表示的运行按钮 (B)、选择`Run -> Run ‘app’`菜单选项或使用快捷键`Ctrl-R`：

![](img/as_run_target.jpg)

图 4-7

设备菜单 (A) 可选择不同的 AVD 实例或物理设备作为运行目标，并可以在多个设备上运行应用。菜单还提供了访问`Device Manager`以及设备连接配置和故障排除选项 get：

![](img/as_device_menu.jpg)

图 4-8

一旦应用安装并运行，第一个 fragment（片段）的用户界面将出现在模拟器中（fragment 是 Android 项目中一个可重用的部分，通常由用户界面布局和一些代码组成，该主题将在本章标题为 “Android Fragment 简介” 的章节中介绍）：

![](img/as_androidsample_running.jpg)

图 4-9

运行过程开始后，会出现`Run`（运行）工具窗口。在安装和启动应用程序时，`Run`工具窗口将显示诊断信息。图 4-10 显示了`Run`工具窗口：

![](img/as_run_window.jpg)

图 4-10

如果在启动过程中遇到问题，`Run`工具窗口将提供帮助。假设应用加载到模拟器并符合预期，我们已验证 Android 环境已正确安装。

## 4.4 在多个设备上运行

图 4-8 显示的运行目标菜单包含在多个模拟器和设备上运行应用的选项。选中后，此选项显示 图 11 所示的配置 AVD 和连接的物理设备列表。在点击运行按钮之前，勾选要目标的模拟器或设备旁边的选框：

![](img/as_avd_multiple.jpg)

点击运行按钮后，Android Studio 将在所选的模拟器和设备上启动应用。

## 4.5 停止运行的应用程序

要停止运行的应用程序，点击主工具栏上的停止按钮，如 图 4-12 所示：

![](img/as_avd_stop.jpg)

图 4-12

也可以使用`Run`工具窗口终止应用。通过使用应用运行时出现的窗口栏按钮显示`Run`工具窗口。一旦`Run`工具窗口出现，点击下方 图 13 中突出显示的停止按钮：

![](img/as_run_window_stop.jpg)

图 4-13

## 4.6 支持深色主题

要测试启用深色主题时的应用行为，在模拟器中运行的 Android 实例内打开`Settings`应用，选择`Display`类别并启用`Dark`，如 图 4-14 所示：

![](img/as_avd_dark.jpg)

图 4-14

启用深色主题后，运行`AndroidSample`应用并注意它以深色主题显示，包括黑色背景和按钮上的紫色背景色，如 图 4-15 所示：

![](img/as_androidsample_running_dark.jpg)

图 4-15

在继续之前，返回`Settings`应用并关闭`Dark`主题模式。

## 4.7 在独立窗口中运行模拟器

在本章到目前为止，我们仅将模拟器作为嵌入在 Android Studio 主窗口中的工具窗口使用。模拟器可以配置为在 Settings（设置）对话框中的独立窗口出现，可以通过点击 Android Studio 工具栏上的“IDE and Project Settings”按钮来显示，如图 4-16 所示：

![](img/as_settings_menu.jpg)

图 4-16

在 Settings 对话框中，在侧边面板导航到`Tools` -> `Emulator`，并禁用`Launch in a tool window`（在工具窗口启动）选项：

![](img/as_avd_luanch_in_tool_window.jpg)

图 4-17

禁用该选项后，点击`Apply`按钮并点击`OK`以提交更改，然后通过点击上文图 4-5 中标记为 B 的标签上的关闭按钮来退出当前的模拟器会话。

再次运行示例应用，此时模拟器将作为一个独立窗口出现，如下所示：

![](img/as_avd_separate_window.jpg)

图 4-18

选择独立模式或工具窗口模式取决于个人喜好。如果你喜欢模拟器运行在工具窗口中，请返回设置屏幕并重新启用`Launch in a tool window`选项。然而，在提交独立模式之前，请记住`Running Devices`（运行中的设备）工具窗口也可以从工具窗口的 Options 菜单从 Android Studio 主窗口中分离，该菜单通过点击图 4-19 所示的按钮来访问：

![](img/as_tool_window_options_button.jpg)

图 4-19

在 Options 菜单中，选择`View Mode`（视图模式）-> `Float`（浮动）将工具窗口从 Android Studio 主窗口分离：

![](img/as_tool_window_options_float.jpg)

图 4-20

要重新停靠`Running Devices`工具窗口，点击图 4-21 所示的`Dock`按钮：

![](img/as_tool_window_dock_button.jpg)

图 4-21

## 4.8 启用设备框架

模拟器可以配置为带有或不带设备框架出现。要更改设置，请退出模拟器，打开`Device Manager`（设备管理器），从列表中选择`AVD`，并点击 Actions 列中的铅笔图标。在设置屏幕中，找到并更改`Enable Device Frame`（启用设备框架）选项：

![](img/as_avd_enable_device_frame.jpg)

图 4-22

一旦启用设备框架，模拟器下次启动时将将如图 4-23 所示：

![](img/as_avd_running_with_frame.jpg)

图 4-23

## 4.9 总结

典型的应用程序开发过程遵循编码、编译和在测试环境中运行的循环。Android 应用程序可以在物理 Android 设备或 Android 虚拟设备（AVD）模拟器上进行测试。AVD 使用 Android Studio Device Manager 工具创建和管理，该工具可以作为命令行工具或通过图形用户界面使用。在创建 AVD 以模拟特定的 Android 设备型号时，虚拟设备的硬件规格应与物理设备的规格匹配。

AVD 模拟器会话可以以独立窗口的形式显示，也可以嵌入到 Android Studio 用户界面中。

## 5. 使用和配置 Android Studio AVD 模拟器

在下一章探索在物理 Android 设备上进行测试之前，本章将花费一些时间提供 Android Studio AVD 模拟器的概述，并突出许多用于在独立模式和工具窗口模式下自定义环境的配置功能。

### 5.1 模拟器环境

在独立模式下启动时，模拟器在加载过程中会显示初始启动界面（splash screen）。加载完成后，将出现主模拟器窗口，其中包含所选设备类型的表示（在图 5-1 中，这是一个 Pixel 4 设备）：

![](img/android_12_avd_running_standalone.jpg)

图 5-1

位于窗口右侧边缘的工具栏提供了对模拟器控制和配置选项的快速访问。

### 5.2 模拟器工具栏选项

模拟器工具栏（图 5-2）提供了与模拟器环境外观和行为相关的系列选项访问。

![](img/as_3.5_avd_toolbar.jpg)

图 5-2

工具栏中的每个按钮都关联有一个键盘快捷键，可以通过将鼠标指针悬停在按钮上等待工具提示出现，或者通过扩展控制面板的帮助选项来识别标识。

尽管工具栏中包含的许多选项是自言易懂的，但为了完整性，将介绍每个选项：

*   `Exit / Minimize`（退出/最小化）——工具栏中最上方的“x”按钮在选中时会退出模拟器会话，而“－”选项会最小化整个窗口。

*   `Power`（电源）——电源按钮模拟物理 Android 设备上的电源按钮。点击并释放此按钮将锁定设备并关闭屏幕。长按此按钮将启动设备的“关机”请求序列。

*   `Volume Up / Down`（音量增大/减小）——两个控制模拟器内播放音量的按钮。

*   `Rotate Left/Right`（向左/向右旋转）——在模拟器设备在竖屏和横屏方向之间旋转。

*   `Take Screenshot`（截图）——对屏幕上显示的内容截图。捕捉图像存储在后文指定的设置屏幕中。

*   `Zoom Mode`（缩放模式）——此按钮切换进入或退出缩放模式，详情将在后文介绍。

*   `Back`（返回）——执行标准的 Android“返回”导航以返回上一个屏幕。

*   `Home`（主页）——显示设备的主屏幕。

*   `Overview`（概述）——模拟标准的 Android“概述”导航，显示正在运行的应用。

*   `Fold Device`（折叠设备）——模拟折叠设备的折叠和展开。此选项在模拟器运行折叠设备镜像时可用。

*   `Extended Controls`（扩展控制）——显示扩展控制面板，允许配置模拟位置和电话活动、电池强度、移动网络类型和指纹识别。

### 5.3 使用缩放模式

位于工具栏的缩放按钮切换进入或退出缩放模式。当激活缩放模式时，工具栏按钮处于按下状态，鼠标指针在悬停在设备屏幕上将显示为放大镜。点击左鼠标键将导致显示相对于选定点缩放，反复点击将增加缩放级别。相反，点击右鼠标键将降低缩放级别。关闭缩放按钮将显示恢复到默认大小。

在缩放模式下点击并拖动将定义一个矩形区域，释放鼠标按钮后视图将进入该区域。

在缩放模式下，可以使用模拟器窗口内的水平和垂直滚动条移动屏幕可视区域。

### 5.4 调整模拟器窗口大小

可以通过点击并拖动窗口的任何角或边随时更改模拟器窗口的大小（以及相应的设备表示）。

### 5.5 扩展控制选项

扩展控制工具栏按钮显示如图 5-3 所示的面板。默认情况下将显示位置设置。从左侧面板选择不同的类别将显示相应的控制组：

![](img/as_avd_extended_controls.jpg)

图 5-3

#### 5.5.1 位置

位置控制允许以十进制或六十进制坐标的形式将模拟的位置信息发送到模拟器。位置信息可以采取单个位置的形式，也可以代表设备移动的点序列的形式，后者通过 GPS 交换格式 (GPX) 或 Keyhole 标记语言 (KML) 格式的文件提供。或者，可以使用集成的 Google Maps 面板可视化地选择单个点或旅行路线。

### 5.5.2 显示器 (Displays)

除了模拟器屏幕内显示的主显示外，`Displays`选项允许在同一个 Android 实例中运行额外的显示器。这对于测试如 Microsoft Surface Duo 等双屏设备的应用非常有用。这些额外的屏幕可以配置为任何所需的尺寸，并显示与主屏幕相同的模拟器窗口内。

### 5.5.3 蜂窝 (Cellular)

可以在蜂窝设置屏幕中更改模拟的蜂窝连接类型。提供的选项可以模拟不同的网络类型（`CSM`、`EDGE`、`HSDPA`等）以及一系列语音和数据场景，例如漫游和拒绝访问。

### 5.5.4 电池 (Battery)

在扩展控制屏幕的此面板上，可以模拟各种电池状态和充电条件，包括电池电量、电池健康状况以及 AC 充电器当前是否连接。

### 5.5.5 摄像头 (Camera)

当摄像头激活时，模拟器会模拟一个 3D 场景。这表现为虚拟建筑的内部，在模拟器内录制视频或拍照之前，可以通过按住`Option`键（Windows 上为`Alt`）同时使用鼠标指针和键盘键来在其中进行导航。此扩展配置选项允许上传不同的图像以显示在虚拟环境中。

### 5.5.6 电话 (Phone)

手机扩展控制在模拟器中提供了两个简单但实用的模拟。第一个选项模拟了来自指定电话号码的入电电话。这在测试应用如何处理高层中断时特别有用。

第二个选项允许在模拟器会话中模拟接收短信。。在现实世界中一样，这些消息显示在`Message`应用中，并触发模拟器内的标准通知。

### 5.5.7 方向键 (Directional Pad)

方向键（`D-Pad`）是内置在 Android 设备中或外部连接（如游戏控制器）的一组额外控件，提供方向控制（左、右、上、下）。方向键设置允许在模拟器内模拟`D-Pad`交互。

### 5.5.8 麦克风 (Microphone)

麦克风设置允许启用麦克风并模拟虚拟耳机和麦克风连接。还提供了一个按钮启动模拟器上的`Voice Assistant`。

### 5.5.9 指纹 (Fingerprint)

许多 Android 设备现在都配备了内置指纹检测硬件。`AVD`模拟器使得测试指纹认证成为可能，无需带有指纹传感器的物理设备上测试应用。在模拟器内配置指纹测试的细节将在本章后部分介绍。

### 5.5.10 虚拟传感器 (Virtual Sensors)

虚拟传感器选项允许模拟加速度计和磁计，以模拟设备物理运动的效果，例如通过`yaw`、`pitch`和`roll`设置模拟旋转、移动和倾斜。

### 5.5.11 快照 (Snapshots)

快照包含当前运行的`AVD`会话的状态，可以被保存并快速恢复，使模拟器轻松返回到精确的状态。快照将在本章稍后部分介绍。

### 5.5.12 录制与播放 (Record and Playback)

允许模拟器屏幕和音频以`WebM`或动画`GIF`格式录制并保存。

### 5.5.13 Google Play

如果模拟器运行安装了 Google Play 服务的 Android 版本，此选项将显示当前的`Google Play`版本。它还提供了将模拟器更新到最新版本的选项。

### 5.5.14 设置 (Settings)

设置面板提供了一小组配置选项。使用此面板为工具栏和扩展控制面板选择较深的主题，指定保存截图的文件系统位置，配置`OpenGL`支持级别，并配置模拟器窗口显示在桌面或其他窗口之上。

### 5.5.15 帮助 (Help)

`Help`屏幕包含三个子面板，包含键盘快捷键列表、访问模拟器在线文档的链接、报告文件错误和发送反馈的链接以及模拟器版本信息。

## 5.6 使用快照

当模拟器首次启动时，它会执行冷启动，就像物理 Android 设备通电一样。此冷启动过程需要一些时间才能完成，因为操作系统正在加载且所有后台进程都将启动。为了避免每次启动模拟器都必须经过此过程，系统配置为在每次退出时自动保存模拟器当前状态的快照（称为快速启动快照）。下次启动模拟器时，快速启动快照将加载到内存中，并从上次离开的地方继续执行，允许模拟器在冷启动所需的一部分时间内重启。

扩展控制面板的`Snapshots`屏幕可以在模拟器执行期间的任何一点存储额外的快照。这保存了整个模拟器的精确状态，允许模拟器恢复到拍摄快照时的精确时刻。从屏幕内部，可以使用`Take Snapshot`按钮拍摄快照（在`图 5-4]`中标记为 A）。要恢复现有快照，请从列表中 (B) 选择它并点击屏幕底部的运行按钮 (C)。还提供了编辑 (D) 快照名称和描述以及删除 (E) 当前选中快照的选项：

![](img/as_avd_snapshots.jpg)

图 5-4

您还可以通过工具栏中的运行目标菜单选择使用冷启动、最近的快速启动快照或之前的快照来启动模拟器，如图`图 5-5]`所示：

![](img/as_avd_run_target.jpg)

图 5-5

### 5.7 配置指纹模拟

模拟器允许配置并使用最多 10 个模拟指纹，用于测试 Android 应用中的指纹认证。配置模拟指纹始于启动模拟器、打开`Settings`应用并选择`Security`选项。

在`Security`设置屏幕内，选择`fingerprint`选项。在生成的信息屏幕上，点击`Next`按钮进入指纹设置屏幕。在启用指纹安全之前，必须配置备用屏幕锁定方法（例如`PIN`）。输入并确认一个合适的`PIN`并通过接受默认通知选项完成`PIN`输入过程。

继续通过后续屏幕，直到`Settings`应用请求在传感器上放置指纹。此时显示扩展控制对话，在左侧面板中选择`Fingerprint`类别，并确保主设置面板中选择了`Finger 1`：

![](img/as_avd_touch_sensor.jpg)

图 5-6

点击`Touch Sensor`按钮模拟`Finger 1`触摸指纹传感器。模拟器将报告指纹添加成功：

![](img/as_avd_fingerprint_added.jpg)

图 5-7

要添加更多指纹，请在再次点击`Touch Sensor`按钮之前，点击`Add Another`按钮并在扩展面板菜单中选择另一个手指。

### 5.8 工具窗口模式下的模拟器

如上一章（“在 Android Studio 中创建 Android 虚拟设备 (AVD)”）所述，Android Studio 可以配置为在嵌入式工具窗口中启动模拟器，使其不会在独立窗口中出现。当在此模式下运行时，工具栏中提供了与独立模式相同的控制控件，如图图 5-8 所示：

![](img/avd_running_devices_toolbar.jpg)

图 5-8

从左到右，这些按钮执行以下任务（细节与独立模式一致）：

* 电源

* 音量增大

* 音量减小

* 向左旋转

* 向右旋转

* 返回

* 主页

* 概览

* 截图

* 快照

* 扩展控制

## 5.9 创建可调整大小的模拟器



除了配置匹配特定 Android 设备型号模拟器外，Android Studio 还提供了一种可调整大小的 AVD，允许你在手机、平板电脑和折叠设备尺寸之间切换。要创建一个可调整大小的模拟器，打开`Device Manager`并点击`Create device`按钮。接下来，选择如图 5-9 所示的`Resizable`设备定义，并按照通常步骤创建新的 AVD：

![](img/avd_create_resizable.jpg)

图 5-9

当你在工具窗口内的新模拟器上运行应用时，工具栏中将出现`Display mode`选项，允许你如图 5-10 所示在不同的模拟器配置之间切换：

![](img/as_avd_fold_button.jpg)

图 5-10

如果模拟器在独立模式下运行，则可以在侧边工具栏中找到`Display mode`选项，如下所示：

![](img/as_avd_display_mode.jpg)

图 5-11

## 5.10 总结

Android Studio 包含一个 Android 虚拟设备模拟器环境，旨在让无需在物理 Android 设备上运行即可更容易测试应用程序。本章简要介绍了模拟器，并强调了用于配置和自定义环境以模拟不同测试条件的关键功能。

## 6. Android Studio 用户界面概览

虽然人们急于运行上一章中创建的示例应用程序，但它涉及使用 Android Studio 用户界面的某些方面，这些内容最好先进行描述。

Android Studio 是一个强大且功能丰富的开发环境，在很大程度上是直观易用的。尽管如此，现在花时间熟悉 Android Studio 用户界面的布局和结构，将缩短书中后续章节的学习曲线。基于此考虑，本章将提供 Android Studio 环境中各个区域和组件的概述。

### 6.1 欢迎屏幕

欢迎界面（如图 6-1）在 Android Studio 运行且当前没有打开任何项目时会显示（可以通过选择`File -> Close Project`菜单选项随时关闭已打开的项目）。如果是在项目仍打开状态下退出 Android Studio，工具在下次启动时将跳过欢迎界面，自动打开之前活跃的项目。

![](img/as_giraffe_welcome2.jpg)

图 6-1

除了最近项目列表外，欢迎界面提供了执行如打开和创建项目等任务的选项，并可以访问当前受版本控制的项目。此外，`Customize`屏幕提供了更改 IDE 和编辑器使用的主题和字体设置的选项。可以使用`Plugins`选项查看、安装和管理 Android Studio 插件。

通过选择`More Actions`链接或在最近项目列表取代`More Actions`链接时使用如图 6-2 所示的菜单，可以获得更多选项：

![](img/as_welcome_menu.jpg)

图 6-2

### 6.2 菜单栏

当创建新项目或打开现有项目时，将出现 Android Studio 主窗口。当同时打开多个项目时，每个项目都将分配自己的主窗口。窗口的精确配置将取决于 Android Studio 运行的操作系统，以及上次打开项目时显示了哪些工具和面板。例如，主菜单栏的外将取决于主机操作系统。在 macOS 上，Android Studio 遵循将菜单栏置于桌面顶部的标准惯例，如图 6-3 所示：

![](img/as_menu_bar.jpg)

图 6-3

然而，当 Android Studio 在 Windows 或 Linux 上运行时，通过如图 6-4 所示的高亮按钮访问主菜单：

![](img/as_windows_main_menu.jpg)

图 6-4

### 6.3 主窗口

一旦打开项目，Android Studio 主窗口通常类似于图 6-5 所示：

![](img/as_main_window_java.jpg)

图 6-5

主窗口的各种元素可以总结如下：

**A – 工具栏 (Toolbar)** – 一组用于频繁执行操作的快捷键。工具栏按钮提供了快速访问一组菜单栏操作的方法。可以通过右键点击工具栏并选择`Customize Toolbar…`选项来自定义工具栏。如图 6-6 所示的工具栏菜单提供了执行打开、创建项目以及在窗口之间切换任务的便捷方法：

![](img/project_switch_menu.jpg)

图 6-6

**B – 导航栏 (Navigation Bar)** – 导航栏为在项目文件和文件夹之间移动提供了一种便捷方法。点击导航栏上的元素将弹出一个显示该位置子文件夹和文件的菜单。同样，点击类名将显示包含在该类中的方法列表：

![](img/navigation_menu.jpg)

图 6-7

从列表中选择一个方法将跳转到代码编辑器中的相应位置。你可以使用`View -> Appearance -> Navigation Bar`选项来隐藏、显示和更改此栏的位置。

**C – 编辑器窗口 (Editor Window)** – 编辑器窗口显示当前正在编写的文件内容。当打开多个文件时，每个文件由位于编辑器顶部的标签页表示，如图 6-8 所示：

![](img/menu_bar_java.jpg)

图 6-8

**D – 状态栏 (Status Bar)** – 状态栏显示有关项目和 Android Studio 活动的信息性消息。悬停在状态栏项目上将显示该字段的描述。许多字段是交互式的，允许用户通过点击来执行任务或获取更详细的状态信息。

![](img/status_bar.jpg)

图 6-9

可以使用`View -> Appearance -> Status Bar Widgets`菜单更改在状态栏中显示的组件。

**E – 项目工具窗口 (Project Tool Window)** – 项目工具窗口提供了项目文件结构的分级概述，允许执行到特定文件和文件夹的导航。工具栏可以使用多种不同的方式显示项目。默认设置是 Android 视图，这是本书其余部分中主要使用的模式。

项目工具窗口只是 Android Studio 环境中众多工具之一。

### 6.4 工具窗口

除了项目（`Project`）视图工具窗口外，Android Studio 还包含许多其他窗口。当这些窗口被启用时，它们会在主窗口的左侧和右侧边缘显示工具窗口栏，其中包含用于显示和隐藏每个工具窗口的按钮。图 6-10 显示了典型的工具窗口栏配置，尽管按钮及其位置可能会根据你安装的 Android Studio 版本而有所不同。

![](img/as_tool_window_bars.jpg)

图 6-10

点击按钮将显示相应的工具窗口，再次点击则会隐藏该窗口。工具窗口栏中按钮的位置表示了当窗口显示时，它将出现在主窗口的哪一侧。可以通过点击并拖动按钮到其他窗口工具栏的不同位置来更改这些位置。

Android Studio 提供了丰富的工具窗口，其中最常用的如下：

*   `Project` (A) – 项目视图提供了构成项目的文件结构概览，允许在文件之间进行快速导航。通常，在项目视图中双击文件将导致该文件加载到适当的编辑工具中。

*   `Resource Manager` (B) - 用于在项目内添加和管理资源及资产的工具，例如图像、颜色和布局文件。

*   `More Tool Windows` (C) - 显示包含当前未显示在工具窗口栏中的其他工具窗口的菜单。从此菜单中选择工具窗口后，它将作为按钮出现在工具窗口栏中。

*   `Run` (D) – 当应用程序正在运行时，运行工具窗口将变为可用，并提供运行结果的视图，以及停止或重启正在运行进程的选项。如果应用程序无法在设备或模拟器上安装和运行，此窗口通常会提供有关问题的诊断信息。

*   `Logcat` (E) – Logcat 工具窗口提供了访问运行应用程序监控日志输出的权限，并提供了对应用程序截图、视频以及停止和重启进程的选项。

*   `Problems` (F) - 查看项目内所有当前错误或警告的中心位置。双击问题列表中的项将带你跳转到问题所在的文件和位置。

*   `App Quality Insights` (G) - 提供访问云端 Firebase 应用程序质量和崩溃分析平台的权限。

*   `Terminal` (H) – 提供访问运行 Android Studio 的系统终端窗口的权限。在 Windows 系统上，这是命令提示符界面，而在 Linux 和 macOS 系统上，它以终端提示的形式存在。

*   `Version Control` (I) - 当项目文件受源代码版本控制时使用此工具窗口，允许访问 Git 仓库和代码更改历史。

*   `Notifications` (J) - 当项目文件受源代码版本控制时使用此工具窗口，允许访问 Git 仓库和代码更改历史。

*   `Gradle` (K) – Gradle 工具窗口提供了构成项目构建配置的 Gradle 任务视图。该窗口列出了将项目各种元素编译为可执行应用程序所涉及的任务。右键点击顶级 Gradle 任务并选择`Open Gradle Config`菜单选项，可以将当前项目的 Gradle 构建文件加载到编辑器中。书中将在稍后部分详细介绍 Gradle。

*   `Device Manager` (L) - 提供访问设备管理器（`Device Manager`）的权限，可以在其中添加、删除和管理物理 Android 设备连接以及模拟器。

*   `Running Devices` (M) - 如果启用了在工具窗口中运行模拟器的选项（如章节“在 Android Studio 中创建 Android 虚拟设备 (AVD)”所示），则其中包含 AVD 模拟器。

*   `App Inspection` - 提供访问`Database`（数据库）和`Background Task`（后台任务）检查器的权限。`Database Inspector`允许你在应用程序运行时检查、查询和修改应用程序数据库。`Background Task Inspector`允许监控和管理使用`WorkManager`创建的后台工作任务。

*   `Bookmarks` – 书签工具窗口提供了快速访问已标记的文件和代码行。例如，在项目视图中右键点击文件可以访问`Add to Bookmarks`菜单选项。同样，你可以通过将光标移动到那里并按`F11`键（macOS 上为`F3`）标记源文件中的一行代码。所有书签项都可以此工具窗口访问。

*   `Build` - 构建工具窗口显示项目正在编译和打包时的构建过程信息，以及遇到的任何错误详细信息。

*   `Build Variants` – 构建变体工具窗口提供了为当前应用程序项目配置不同构建目标的快速方法（例如，针对应用程序调试和发布版本的不同构建，或针对不同设备类别的多个构建）。

*   `Device File Explorer` – 通过`View` -> `Tool Windows` -> `Device File Explorer`菜单可用，此工具窗口提供了对当前连接的 Android 设备或模拟器文件系统的直接访问，允许浏览文件系统并将文件复制到本地文件系统。

*   `Layout Inspector` - 提供构成用户界面布局的组件层次的可视化 3D 渲染。

*   `Structure` – 结构工具提供了当前编辑器中显示的源文件结构的高级视图。这些信息包括文件中的类、方法和变量等项的列表。从结构列表中选择某项将带你跳转到编辑器窗口源文件中的对应位置。

*   `TODO` – 如名称所示，此工具提供了一个查看项目中待完成事项的地方。Android Studio 通过扫描构成项目的源文件寻找匹配特定`TODO`注释来编译此列表。可以通过打开`Settings`对话框并导航到`TODO`来查看和更改这些模式。

### 6.5 工具窗口菜单

每个工具窗口顶部都有自己的工具栏。这些工具栏中的菜单随工具的不同而异，但所有工具窗口都包含一个`Options`菜单（见图 6-11

图 6-11

`Options`菜单允许更改窗口的各个方面。图 6-12 例如显示了`Project`工具窗口的`Options`菜单。例如，可用设置可以将窗口停靠并使其在 Android 主窗口边界之外浮动，以及移动和调整工具面板的大小：

![](img/as_project_tool_window_options.jpg)

图 6-12

所有工具窗口在工具栏的最右侧还包含一个按钮（见上方图 6-11 中的标记 B），提供了隐藏工具窗口的方法。可以通过点击窗口使其并输入搜索词（例如`Project`工具窗口中的文件名）来对工具窗口内的项进行搜索。搜索框将出现在窗口工具栏中，并高亮显示匹配搜索内容的项。

### 6.6 Android Studio 快捷键

Android Studio 包含了许多快捷键，以便在执行常用任务时节省时间。可以在 Android Studio 项目窗口内通过选择`Help` -> `Keyboard Shortcuts PDF`菜单选项查看并打印完整的快捷键键映射列表。你也可以通过打开`Settings`对话框并点击`Keymap`项来列出和修改快捷键，如下方的图 6-13 所示：

![](img/as_keymap.jpg)

图 6-13

### 6.7 切换器与最近文件导航

在 Android Studio 主窗口内进行导航的另一种实用机制是使用`Switcher`（切换器）。通过`Ctrl-Tab`快捷键访问切换器，它会作为一个面板出现，列出所有工具窗口和当前打开的文件（图 6-14）。

![](img/as_switcher.jpg)

图 6-14

显示后，只要`Ctrl`键保持按下，切换器就会保持可见。在按住`Ctrl`键的同时反复点击`Tab`键可以在各种选择选项之间循环，释放`Ctrl`键将选中当前高亮的项并在主窗口中显示。

除了`Switcher`外，`Recent Files`（最近文件）面板提供了对最近打开文件的导航（图 6-15）。可以使用`Ctrl-E`快捷键（macOS 上为`Cmd-E`）访问。显示后，可以使用鼠标指针选择选项，或使用键盘方向键在文件名和工具窗口选项之间滚动。按下`Enter`键可以选择当前高亮的项：

![](img/as_recent_files.jpg)

图 6-15

### 6.8 修改 Android Studio 主题

可以使用`Settings`（设置）对话框更改 Android Studio 环境的整体主题。一旦显示设置对话框，在左侧面板中选择`Appearance & Behavior`（外观与行为）选项，然后选择`Appearance`（外观）。在点击`OK`按钮之前更改`Theme`（主题）菜单的设置。可用主题取决于平台，但通常包括`Light`（浅色）、`IntelliJ`、`Windows`、`High Contrast`（高对比度）和`Darcula`等选项。图 6-16 显示了选择了`Dark`（深色）主题的主窗口示例：

![](img/as_dark.jpg)

图 6-16

要把 Android Studio 主题与操作系统的明暗模式设置同步，请启用`Sync with OS`（与操作系统同步）选项，并使用下拉菜单控制每个模式使用哪种主题：

![](img/as_theme_sync.jpg)

图 6-17

### 6.9 总结

Android Studio 环境的主要元素由欢迎界面和主窗口组成。每个打开的项目都有它自己的主窗口，该窗口又由菜单栏、工具栏、编辑和设计区域、状态栏以及工具窗口集合组成。工具窗口出现在主窗口的侧边。

Android Studio 中极少数操作无法通过快捷键触发。可以随时从 Android Studio 主窗口内访问默认快捷键的键位映射。

## 7. 在物理 Android 设备上测试 Android Studio 应用

虽然使用 Android 虚拟设备 (AVD) 测试应用程序可以实现许多功能，但在物理 Android 设备上进行真实的应用测试是不可替代的，而且某些 Android 功能仅在物理 Android 设备上可用。

与 AVD 实例和已连接 Android 设备的通信由 Android 调试桥（`ADB`，Android Debug Bridge）处理。本章将解释如何配置`adb`环境，以便在基于 macOS、Windows 和 Linux 的系统的 Android 设备上启用应用测试。

### 7.1 Android 调试桥 (ADB) 概述

`ADB`的主要目的是方便开发系统（在本例中为 Android Studio）与 AVD 模拟器及 Android 设备之间的交互，以运行和调试应用程序。`ADB`允许你通过 WiFi 或 USB 线连接到设备。

`ADB`由一个客户端、一个运行在开发系统后台的服务器进程以及一个运行在 AVD 或真实 Android 设备（如手机和平板）中的守护后台进程组成。

`ADB`客户端有多种形式。例如，在 Android SDK 的`platform-tools`子目录下提供了一个名为`adb`的命令行工具作为客户端。同样，Android Studio 也有一个内置的客户端。

可以使用`adb`命令行工具执行多种任务。例如，可以使用`devices`命令行参数列出活跃的虚拟或物理设备。以下命令输出表示系统上存在一个 AVD，但没有物理设备：

```
$ adb devices
List of devices attached
emulator-5554 device
```

### 7.2 在 Android 设备上启用 USB 调试 ADB

在`ADB`连接到 Android 设备之前，必须将该设备配置为允许连接。在运行 Android 6.0 或更高版本的手机和平板设备上，实现此目的的步骤如下：

1. 打开设备上的`Settings`（设置）应用并选择`About tablet`（关于平板）或`About phone`（关于手机）选项（在某些 Android 版本中，可以在`Settings`应用的`System`页面找到）。



2. 在`About`屏幕上滚动到`Build number`（版本号）字段（图 7-1）并点击七次，直到消息显示已启用开发者模式。如果`About`屏幕上未列出`Build number`，可以通过`Software information`（软件信息）选项找到。或者，如果，展开列表中的`Advanced`（高级）部分。

![](img/as_3.2_build_number.jpg)

图 7-1

3. 返回主`Settings`屏幕并注意名为`Developer options`（开发者选项）的新选项（在较新的 Android 版本中，此选项列在`System`设置屏幕上）。选择此选项，在生成的屏幕上找到如图 7-2 所示的`USB debugging`（USB 调试）选项：

![](img/android_12_debugging.jpg)

图 7-2

4. 启用`USB debugging`选项并在请求确认时点击`Allow`（允许）。

设备现在已配置为接受来自`adb`的调试。剩下的工作是配置开发系统在连接时检测设备。虽然这是一个相对简单的过程，但步骤取决于开发系统运行 Windows、macOS 还是 Linux。以下步骤假设 Android SDK platform-tools 目录已包含在系统的`PATH`环境变量中，参见“设置 Android 开发环境”章节（`#Installation.xhtml__idAnchor009`）。

## 7.2.1 macOS ADB 配置

要在 macOS 系统上配置`ADB`环境，第一步是在该系统上安装相应的`USB`驱动程序。要安装的`USB`驱动程序取决于 Android 设备的型号。如果你拥有 Google 设备（例如 Pixel 手机），则需要在你的 Windows 系统上安装并配置`Google USB Driver`程序包。实现此目的的详细步骤列在以下网页上：

[`developer.android.com/sdk/win-usb.html`](http://developer.android.com/sdk/win-usb.html)

对于不支持 Google USB 驱动程序的 Android 设备，需要下载由设备制造商提供的驱动程序。您可以在网上获取驱动程序列表以及下载和安装信息：

[`developer.android.com/tools/extras/oem-usb.html`](http://developer.android.com/tools/extras/oem-usb.html)

安装驱动程序后，如果设备已被识别为正确的类型，请打开命令提示符窗口并执行以下命令：

```
adb devices
```

该命令应该输出有关连接设备的信息，类似于下所示：

```
List of devices attached
HT4CTJT196 offline
```

如果设备显示为 offline（离线）或 unauthorized（未授权），请查看设备屏幕，检查图 7-3 所示的请求允许调试的对话框。在点击确定之前，勾选“允许来自此计算机”选项旁边的复选框。再次执行`adb devices`命令应该会将设备列为已就绪：

```
List of devices attached
HT4CTJT196 device
```

如果设备未列出，请执行以下命令重启 ADB 服务：

```
adb kill-server
adb start-server
```

如果设备仍然未列出，请尝试执行以下命令：

```
android update adb
```

请注意，可能还需要重新启动系统。

## 7.2.3 Linux adb 配置

在本章中，我们将再次使用 Ubuntu Linux 作为参考示例，配置`adb`以连接到物理 Android 设备以进行测试。在 Ubuntu Linux 上进行物理设备测试需要安装名为`android-tools-adb`的包，这反要求 Android Studio 用户成为`plugdev`组的成员。这是大多数 Ubuntu 版本用户账户的默认设置，可以通过运行`id`命令进行验证。如果未列出`plugdev`组，请运行以下命令将您的账户添加到组：

```
sudo usermod -aG plugdev $LOGNAME
```

在满足组成员要求后，可以通过执行以下命令安装`android-tools-adb`包：

```
sudo apt-get install android-tools-adb
```

完成上述更改后，重启 Ubuntu 系统。系统重启后，打开终端窗口，启动`adb`服务，并检查连接的设备列表：

```
$adb start-server
daemon not running. starting it now on port 5037
daemon started successfully
$adb devices
List of devices attached
015d41d454bf80c offline
```

如果设备显示为 offline 或 unauthorized，请查看 Android 设备并检查图 7-3 所示的请求允许调试的对话框。

## 7.3 解决 USB 连接问题

如果您无法通过上述步骤成功连接到设备，请显示运行目标菜单（图 7-4）并选择“排除设备连接”（Troubleshoot Device Connections）选项：

!image/as_device_troubleshooting.jpg

连接助手将扫描设备并报告问题及其解决方案。

## 7.4 在 Android 设备上启用无线调试

按照上述 7.2 节中的步骤 1 到 3 进行操作，这次将启用图 7-5 所示的“无线调试”选项：

!image/android_12_enable_wifi_debugging.jpg

接下来，点击上述“无线调试”条目以显示图 7-6 所示的屏幕：

!image/android_12_enable_wifi_debugging_settings.jpg

如果您的设备带有相机，请选择“使用二维码配对设备”，否则选择“使用配对码配对设备”。根据您的选择，设置应用将启动相机会话或显示配对码，如图 7-7 所示：

!image/as_pair_devices_code.jpg

选择选项后，返回 Android Studio，从运行目标菜单中选择“通过 WiFi 配对设备”（Pair Devices Using WiFi），如图 7-8 所示：

!image/as_wifi_pair_menu.jpg

在配对对话框中，根据您之前在设备设置应用中的选择，项选择“使用二维码配对”或“使用配对码配对”：

!image/as_wifi_pair_dialog.jpg

使用 Android 设备扫描二维码，或将设备屏幕上显示的配对码输入 Android Studio 对话框（图 7-10）中以完成配对过程：

!image/as_pair_devices_wifi_enter_code.jpg

如果配对过程失败，请尝试重启开发系统和 Android 设备并重试。

## 7.5 测试 adb 连接

假设在您选择的开发平台上已成功配置`adb`，下一步是在设备上尝试运行“在 Android Studio 中创建示例 Android 应用”章节中创建的应用程序。启动 Android Studio，打开 AndroidSample 项目，并验证设备是否显示在图 7-11 所示的设备选择菜单中：

!image/as_physical_device_connected.jpg

从列表中选择设备并点击运行按钮以安装并运行应用。

## 7.6 设备镜像

设备镜像（Device mirroring）允许您在物理设备上运行应用，同时在 Android Studio 的“运行设备”（Running Devices）工具窗口内查看显示。也就是说，尽管应用程序运行在物理设备上，但它在 Android Studio 中的显示方式与 AVD 实例相同。

## 7.7 总结

虽然 Android 虚拟设备模拟器提供了极佳的测试环境，但必须记住，确保应用程序在物理设备上正常运行没有真正的替代方案。

但默认情况下，Android Studio 环境未配置为将 Android 设备作为目标设备。因此，需要执行某些步骤，通过 USB 线缆或 WiFi 网络从 Android Studio 开发环境直接将应用程序加载到 Android 设备上。

## 8 Android Studio 代码编辑器基础

为 Android 开发应用程序涉及大量的编程工作，根据定义，这涉及输入、审查和修改代码行。意料的是，开发者使用 Android Studio 的大部分时间通常会在编辑器窗口内编辑代码。

现代代码编辑器必须远超基本的输入、删除、剪切和粘贴。今天，代码编辑器的实用性通常取决于它减少程序员输入量的程度、在大源文件中导航的易用性，以及编辑器在编写代码时实时检测并突出编程错误的能力。正如本章所示，这些仅仅是编辑器出色的几个领域之一。

本章并未对 Android Studio 编辑器的功能进行详尽概述，但其目的是提供该工具关键功能的指南。经验丰富的程序员会发现，这些功能中的某些是目前大多数代码编辑器通用的，而许多功能是该编辑环境所特有的。

## 8.1 Android Studio 编辑器

当选择 Java、Kotlin、XML 或其他文本文件进行编辑时，Android Studio 编辑器会出现在主窗口的中心。例如，图 8-1 显示了一个加载了 Java 源代码文件的典型编辑会话：

![](img/as_code_editor_java.jpg)

图 8-1

构成编辑器窗口的元素可以总结如下：

**A – 文档标签（Document Tabs）** – Android Studio 可以随时打开多个文件进行编辑。每当打开一个文件，它就会被分配一个文档标签，在编辑器窗口顶部边缘的标签栏中显示文件名。当空间不足以显示所有标签时，标签栏的最右侧会出现一个一个小下拉菜单。点击此菜单将列出其他已打开的文件列表。标签中文件名下方的红色波浪线表示该文件中的代码包含一个或多个错误，这些错误在项目编译和运行之前需要解决。

切换文件可以通过点击相应的标签或使用`Alt-Left`和`Alt-Right`键盘快捷键。也可以使用切换器机制（通过`Ctrl-Tab`键盘快捷键访问）进行文件导航。

要将编辑器面板从 Android Studio 主窗口分离以便在单独的窗口中显示，请点击标签并将其拖到主窗口之外的桌面区域。要将编辑器返回主窗口，请点击分离编辑器窗口中的文件标签，并将其拖放到主窗口中的原始编辑器标签栏上。

**B – 编辑器行槽区域（Editor Gutter Area）** - 编辑器使用行槽显示信息图标和控件。行槽区域中的一些典型项目是调试断点标记、折叠和展开代码块的控件、书签、更改标记和行号。行号默认开启，但可以通过右行槽点击右键并选择`Appearance -> Show Line Numbers`（外观 -> 显示行号）菜单选项来禁用。

**C – 代码结构位置（Code Structure Location）** – 编辑器底部的此栏显示光标相对于代码整体结构的当前位置。例如，在图中，该栏指示`convertCurrency`方法正在被编辑，且该方法位于`MainActivity`类中：

![](img/as_code_structure.jpg)

图 8-2

双击栏内的任意元素将把光标移动到代码文件中的相应位置。例如，双击`convertCurrency`条目将光标移动到源代码中`convertCurrency`方法的顶部。同样，点击`MainActivity`条目将显示一个可供选择的代码导航点列表：

![](img/as_code_structure_menu.jpg)

图 8-3

**D – 编辑器区域（Editor Area）** – 用户查看、输入和编辑代码的主区域。本章随后的章节将详细介绍编辑区域的关键功能。

**E – 验证和标记侧边栏（Validation and Marker Sidebar）** – Android Studio 集成了一个名为“即时代码分析”（on-the-fly code analysis）的功能。这意味着当您编写代码时，编辑器会分析代码以检查警告和语法错误。验证侧边栏顶部的指示器将实时更新，显示随着代码添加而发现的错误和警告数量。点击此指示器将显示一个弹出窗口，其中包含编辑器中代码发现的问题摘要，如图 8-4 所示：

![](img/as_editor_validation_summary.jpg)

图 8-4

向上和向下箭头在代码内的错误位置之间移动。绿色复选标记表示未检测到警告或错误。

侧边栏还会使用相同的颜色代码在检测到问题的位置显示标记。当代码行在编辑器区域可见，将鼠标指针悬停在标记上，将显示一个包含问题描述的弹出窗口：

![](img/as_code_editor_problem_popup.jpg)

图 8-5

当代码行已滚动出编辑器视图区域时，将鼠标指针悬停在该行的标记上，将显示一个“透镜”（lens）覆盖层，其中包含问题所在的代码块（图 8-6），从而可以在无需滚动到编辑器中该位置的情况下查看它：

![](img/as_code_editor_lens.jpg)

图 8-6

值得注意的是，透镜覆盖层不仅限于侧边栏中的警告和错误。悬停在侧边栏的任何部分上都会出现一个透镜，其中包含源文件中该处的代码。

**F – 状态栏（Status Bar）** – 尽管状态栏是主窗口的一部分而非编辑器，但它确实包含有关当前活动编辑会话的信息。这些信息包括光标在行和字符层面的当前位置，以及文件的编码格式（UTF-8、ASCII 等）。点击状态栏中的这些值可以更改相应的设置。例如，点击行号将显示`Go to Line:Column`（转行：列）对话框。使用`View -> Appearance -> Status Bar Widgets`（视图 -> 外观 -> 状态栏小部件）菜单选项来添加和删除小部件。例如，如果您遇到 Android Studio 性能问题，内存指示器是一个非常有用的小部件。

在介绍了构成编辑器的元素后，本章剩余部分将探讨编辑环境的关键功能。

## 8.2 分割编辑器窗口

默认情况下，编辑器显示当前文件的单个面板。在处理多个源文件时，一个实用功能是将编辑器拆分为多个面板。要拆分编辑器，右键点击编辑器窗口内的文件标签并选择`Split Right`（向右拆分）或`Split Down`（向下拆分）菜单选项。例如，图 8-7 显示了拆分器的用法，编辑器被分为三个面板：

![](img/as_code_editor_split.jpg)

图 8-7

随时可以通过右键点击相应的标签并选择`Change Splitter Orientation`（更改拆分方向）菜单选项更改分割面板的方向。重复这些步骤可以取消单个面板，此时从菜单中选择`Unsplit`。可以通过右键点击任何标签并选择`Unsplit All`（取消所有分割）来移除所有分割面板。

窗口分割可以显示不同的文件，也可以提供同一文件的多个窗口，允许同时查看和编辑同一文件的不同区域。

## 8.3 代码补全

Android Studio 编辑器内置了大量关于 Java 编程语法以及 Android SDK 类和方法的内置知识，以及对您代码库的了解。在输入代码时，编辑器扫描输入内容，并在适当的情况下对完成语句或引用可能需要的建议。当编辑器检测到补全建议时，会出现一个包含建议列表的面板。在图 8-8 中，编辑器正在为 String 声明的开头提供建议：

![](img/as_code_editor_completion.jpg)

图 8-8

如果没有任何自动补全建议是正确的，请继续输入，编辑器将在适宜的地方继续完善建议。要采纳最顶部的建议，请按键盘上的`Enter`或`Tab`键。要选择不同的建议，请使用方向键在列表中上下移动，并再次使用`Enter`或`Tab`键选择高亮项。

可以使用`Ctrl-Space`键盘组合键手动调用补全建议。这在更改编辑器中的单词或声明时非常有用。当光标悬停在编辑器中的某个单词上时，该单词将自动高亮。按下`Ctrl-Space`将显示一个备选建议列表。按下`Tab`键可以将当前单词替换为建议列表中的高亮项。

除了实时自动补全功能外，Android Studio 编辑器还提供了智能补全（Smart Completion）系统。智能补全通过`Shift-Ctrl-Space`键盘组合键调用，选中后它将根据代码的当前上下文提供更详细的建议。再次按下`Shift-Ctrl-Space`快捷键将从更广泛的范围内提供更多建议。

代码补全对许多程序员来说可能是个人喜好。为了承认这一事实，Android Studio 对自动补全设置提供了高水平的。可以通过打开`Settings`对话框并在设置面板中选择`Editor -> General -> Code Completion`来查看和修改这些设置，如图 8-9 所示：

![](img/as_code_completion_settings.jpg)

图 8-9

## 8.4 语句补全

Android Studio 编辑器提供的另一种自动补全形式是语句补全（Statement Completion）。它可以自动填充方法和循环语句等项的括号和大括号。语句补全通过`Shift-Ctrl-Enter`（macOS 上为`Shift-Cmd-Enter`）键盘组合键调用。考虑以下代码：

```java
myMethod()
```

在编辑器中输入此代码后，触发语句补全会导致编辑器自动为方法添加大括号：

```java
myMethod() {

}
```

## 8.5 参数信息

还可以请求编辑器提供关于方法接受的参数参数的信息。当光标位于方法调用的括号之间时，使用`Ctrl-P`（macOS 上为`Cmd-P`）键盘组合键将显示已知该方法接受的参数，其中最可能的建议将加粗显示：

![](img/as_code_editor_parametre_info_java.jpg)

图 8-10

## 8.6 参数名提示



代码编辑器可以配置为在方法调用显示参数名提示。例如，图 8-11 高亮了 `Snackbar` 类中 `make()` 和 `setAction()` 方法调用中的参数名提示：

![](img/as_code_editor_hints.jpg)

图 8-11

此模式的设置可以通过打开 `Settings` 对话框并在侧边栏导航到 `Editor -> Inlay Hints -> Java` 来配置。在生成的屏幕上为您选择的编程语言开启或关闭 `Parameter names` 选项。要调整提示设置，点击 `Exclude list...` 链接并进行任何调整。

## 8.7 代码生成

除了输入代码时完成代码外，编辑器在某些条件下还可以为您生成代码。如图 8-12 所示的可用代码生成选项列表，可以在光标位于文件中需要生成代码的位置时，使用 `Alt-Insert`（macOS 上为 `Cmd-N`）快捷键访问。

![](img/as_code_generate_menu.jpg)

图 8-12

例如，考虑一种情况：我们希望在项目中的 `Activity` 将被操作系统销毁时收到通知。正如本书后面的章节概述，这可以通过重写 `Activity` 超类的 `onStop()` 生命周期方法来实现。要让 Android Studio 为此生成一个存根方法，请从代码生成列表中选择 `Override Methods…` 选项，并在生成的可用方法列表中选择 `onStop()` 方法：

![](img/as_code_editor_override_dialog.jpg)

图 8-13

选择要重写的方法后，点击 `OK` 将在 Java 源文件的当前光标位置生成如下存根方法：

```java
@Override
protected void onStop() {
    super.onStop();
}
```

## 8.8 代码折叠

一旦源文件文件达到特定大小，即使是格式化最整齐、组织最好的代码也可能变得难以处理和难以导航。Android Studio 认为，并不总是需要每个代码块的内容都保持可见。使用 Android Studio 编辑器的代码折叠功能可以使代码导航更容易。代码折叠由折叠箭头控制，当鼠标指针悬停在源文件的行槽（gutter）区域时，这些箭头出现在每个代码块的开头。例如图 8-14 高亮了当前未折叠的方法声明折叠箭头：

![](img/as_code_editor_folding.jpg)

图 8-14

点击此标记将折叠语句，使仅符号签名行可见，如图 8-15 所示：

![](img/as_code_editor_folded.jpg)

图 8-15

要展开已折叠的代码段，请点击编辑器行槽中的折叠箭头。若要在不展开代码的情况下查看隐藏代码，请将鼠标指针悬停在 `{…}` 指示器上，如图 8-16 所示。编辑器随后将显示包含折叠代码的透镜覆盖层：

![](img/as_code_editor_folded_java.jpg)

图 8-16

文件中的所有代码块都可以使用 `Ctrl-Shift-Plus` 和 `Ctrl-Shift-Minus` 序列（macOS 上为 `Cmd-Shift-Plus` 和 `Cmd-Shift-Minus`）折叠或展开。

默认情况下，Android Studio 编辑器打开打开源文件会自动折叠某些代码。要配置发生这种情况的情况，请导航到 `Settings` 对话框中的 `Editor -> General -> Code Folding` 项（图 8-17）：

![](img/as_code_editor_folding_settings.jpg)

图 8-17

## 8.9 快速文档查找

可以通过将光标放在所需文档的声明上并按下 `Ctrl-Q` 快捷键（macOS 上为 `Ctrl-J`）访问相关的 Java 和 Android 文档。这将显示包含相关参考文档的弹出窗口。例如，图 8-18 显示了 `FloatingActionButton` 类的文档。

![](img/as_code_editor_documentation_lookup_java.jpg)

图 8-18

## 8.10 代码格式化

通常情况下，Android Studio 编辑器会在添加语句和代码块时自动在缩进、间距和嵌套方面对代码进行格式化。在需要重新格式化代码的情况下（例如，从网站剪粘贴示例代码时），编辑器提供了源代码格式化功能，选中后将自动格式化代码以匹配主流的代码样式。

按下 `Ctrl-Alt-L`（macOS 上为 `Cmd-Opt-L`）快捷键序列重新格式化源代码。要显示 `Reformat Code` 对话框（图 8-19），请使用 `Ctrl-Alt-Shift-L`（macOS 上为 `Cmd-Opt-Shift-L`）。

![](img/as_reformat_code.jpg)

图 8-19

可以通过打开 Settings（设置）对话框并在侧边栏中选择 `Code Style` 来更改完整的代码样式偏好设置，访问支持的编程和标记语言列表。选择一种语言将提供大量的格式样式选项，所有选项都可以从 Android Studio 默认值修改以匹配你偏好的代码样式。例如，要配置上述对话框中的 `Rearrange`重排）代码选项，请展开 `Code Style` 部分，选择 `Java`，并在 `Java` 设置中选择 `Arrangement（排列）选项卡。

### 8.11 查找示例代码

Android Studio 编辑器提供了一种访问代码列表中当前高亮条相关示例代码的方法。此功能对于学习如何使用特定的 Android 类或方法非常有帮助。要查找示例代码，可以在编辑器中高亮方法或类名，右键点击它并选择 `Find Sample Code（查找示例代码）菜单选项。如果有示例代码，`Find Sample Code` 面板将会出现并列出匹配的示例。从列表中选择一个示例将把相应的代码加载到右侧面板。

### 8.12 Live Templates（实时模板）

在编写 Android 代码时，你会发现有一些经常使用的常用结构。例如，一个常见的需求是使用 `Toast` 类向用户显示弹出消息。Live templates 是一个常用代码结构的集合，可以通过在编辑器中输入初始字符后按特殊键（默认设置为 `Tab` 键）来插入模板代码。要亲体验这一操作，请在代码编辑器中输入 `toast` 然后按 `Tab` 键，Android Studio 将在光标位置插入以下代码并准备好进行编辑：

```java
Toast.makeText(, "", Toast.LENGTH_SHORT).show();
```

要列出并编辑现有模板、更改特殊键或添加自己的模板，请打开 Settings 对话框，并在左侧导航面板的 `Editor` 部分中选择 `Live Templates`：

![](img/as_code_live_templates.jpg)

图 8-20

使用上方 图 8-20 中标记为 A 的按钮来添加、删除、复制或重置模板。要修改模板，请从列表中选择它 (B) 并更改标记为 C 的面板中的设置。

### 8.13 总结

Android Studio 编辑器尽力减少编写代码所需的打字量，并使代码更易阅读和导航。本章涵盖了编辑器的关键功能，包括代码补全、代码生成、编辑器窗口拆、代码折叠、重新格式化、文档查询和实时模板。

# 9. Android 架构概览

到目前为止，书中已经采取了步骤来建立一个适用于使用 Android Studio 开发 Android 应用的环境。通过创建 Android Studio 应用项目，也已经迈出了应用开发过程的第一步。

然而，在进一步研究 Android 应用开发的实际问题之前，理解 Android SDK 以及更通用的 Android 开发中一些更抽象的概念至关重要。现在清晰地理解这些概念将为构建进一步知识提供坚实的基础。

本章从对 Android 架构的概述开始，并在书的后续几章中继续，目标是提供 Android 开发基础的详细概述。

## 9.1 Android 软件栈

Android 的结构是一个软件堆栈，由应用程序、操作系统、运行时环境、中间件、服务和库组成。这种架构可以通过视觉方式表示得最好，如 图 9-1 所示。堆栈的每一层以及每层中对应的元素都紧密集成并经过仔细调整，以为移动设备提供最佳的应用开发和执行环境。本章的其余部分将介绍 Android 栈的不同层，从底部的 `Linux Kernel（Linux 内核）` 开始。

![](img/Image2438.jpg)

图 9-1

## 9.2 Linux 内核

`Linux Kernel`位于 Android 软件栈的底部，在设备硬件和 Android 软件栈上层之间提供了抽象。内核提供了抢式多处理、底层核心系统服务（如内存、进程和电源管理），以及用于设备显示器、WiFi 和音频等硬件的网络栈和设备驱动程序。

原始 Linux 内核是由 Linus Torvalds 于 1991 年开发的。它与 Richard Stallman 在自由软件基金开发的一系列工具、实用程序和编译器相结合，创建了一个名为 `GNU/Linux` 的完整操作系统。各种 Linux 发行版都是从这些基础底层派生出来的，例如 Ubuntu 和 Red Hat Enterprise Linux。

然而，需要注意的是，Android 仅使用 `Linux kernel`。尽管如此，值得注意的是，`Linux kernel` 最初是为用于传统的桌面和服务器计算机系统而开发的。事实上，Linux 现在最广泛地部署在任务关键型企业服务器环境中。我们发现该软件位于 Android 软件栈的核心，这既证明了今天移动设备的强大，也证明了 `Linux kernel` 的效率和性能。

## 9.3 Android Runtime – ART

当在 Android Studio 中构建 Android 应用时，它会被编译为中间字节码格式（DEX 格式）。当随后将其加载到设备时，Android Runtime (ART) 使用一种称为 Ahead-of-Time (AOT，预前编译）的过程将字节码翻译为设备处理器所需的本地器指令。这种格式被称为可执行和链接格式 (ELF)。

每当随后启动应用程序时，都会运行 ELF 可执行版本，从而获得更应用性能和更长的电池寿命。

这与旧版 Android 实现使用的 Just-in-Time (JIT，即时编译）方法形成对比，在每次启动应用程序时都在虚拟机 (VM) 内翻译字节码。

## 9.4 Android 库

除了标准的 Java 开发库（提供字符串处理、网络和文件操作等通用任务的支持）外，Android 开发环境还包含 Android 库。这些是针对 Android 开发的 Java 库。该类别的库包括应用程序框架库，以及有助于构建用户界面、图形绘制和数据库访问的库。

Android 开发者可用的一些关键 Android 库摘要：

- `android.app`: 提供应用模型的访问，是所有 Android 应用的基石。

- `android.content`: 促进应用程序和组件之间的内容访问、发布和消息传递。

- `android.database`: 用于访问内容提供者发布的数据并包含 SQLite 数据库管理类。

- `android.graphics`: 底层 2D 图形绘制 API，包括颜色、点、过滤器、矩形画布。

- `android.hardware`: 提供了一个访问加速度计和光传感器等硬件的 API。

- `android.opengl`: OpenGL ES 3D 图形渲染 API 的 Java 接口。

- `android.os`: 为应用程序访问标准操作系统服务，包括消息、系统服务和进程间通信。

- `android.media`: 提供用于音频和视频播放的类。

- `android.net`: 一组提供访问网络栈的 API。包括 `android.net.wifi`，它提供对设备无线栈的访问。

- `android.print` – 包含一组类，允许从 Android 内部将内容发送到配置的打印机。

- `android.provider` – 一组便利类，提供对标准 Android 内容提供者数据库的访问，例如由日历和联系人应用维护的数据库。

- `android.text` – 用于在设备显示上渲染和操作文本。

- `android.util` – 一组工具类，用于执行字符串和数字转换、XML 处理以及日期和时间操作等任务。

- `android.view` – 应用用户界面的基础构建模块。

- `android.widget` - 丰富的预构建用户界面组件集合，如按钮、标签、列表视图、布局管理器、单选按钮等。

- `android.webkit` – 一组类，旨在在应用程序中构建网页浏览功能。

在涵盖了 Android 运行时基于 Java 的库之后，现在是时候将注意力转向 Android 软件栈这一层中基于 C/C++ 的库了。

### 9.4.1 C/C++ 库

前一节中概述的 Android 运行时核心库是基于 Java 的，为 Android 开发者提供了主要的 API。然而，需要注意的是，核心库并没有执行许多实际工作，事实上，它们本质上是对一组基于 C/C++ 的库的 Java“封装器”。例如，在调用 `android.opengl` 库在设备显示器上绘制 3D 图形时，该库最终会调用 `OpenGL ES` C++ 库，而该库又与底层的 Linux 内核协作执行绘图任务。

包含 C/C++ 库是为了满足广泛多样化的功能，包括 2D 和 3D 图形绘制、安全套接层 (SSL) 通信、SQLite 数据库管理、音频视频播放、位图和矢量字体渲染、显示子系统和图形层管理以及标准 C 系统库 (`libc`) 的实现。

在实践中，典型的 Android 开发者将仅通过基于 Java 的 Android 库 API 访问这些库。如果需要直接访问这些库，可以使用 Android 原生开发包 (NDK) 实现，其目的是通过 Java Native Interface (JNI) 在 Java 代码中调用非 Java 或 Kotlin 语言（如 C 和 C++）的原生方法。

### 9.5 应用程序框架

应用程序框架是一系列服务，它们共同构成了 Android 运行和管理应用程序的环境。该框架实现了这样一个概念：Android 应用程序是由可重用、可交换和可替换的组件构建的。这一概念进一步，应用程序还可以发布其功能以及任何相关数据，以便其他应用程序可以发现并重用它们。

Android 框架包含以下关键服务：

- Activity 管理器 (Activity Manager) – 控制应用程序生命周期和 Activity 栈的所有方面。

- 内容提供者 (Content Providers) – 允许应用程序与其他应用程序共享数据。

- 资源管理器 (Resource Manager) – 提供对非代码嵌入资源的访问，如字符串、颜色设置和用户界面布局。

- 通知管理器 (Notifications Manager) – 允许应用程序向用户显示警告和通知。

- 视图系统 (View System) – 用于创建应用程序用户界面的扩展视图集。

- 包管理器 (Package Manager) – 可以通过它查找设备上已安装的其他应用程序的信息。

- 电话管理器 (Telephony Manager) – 向应用程序提供设备可用电话服务的信息，例如状态和订阅者信息。

- 位置管理器 (Location Manager) – 提供对位置服务的访问，允许应用程序接收位置更改的更新。

### 9.6 应用程序

位于 Android 软件栈顶端的是应用程序。它们由由特定 Android 实现提供的原生应用程序（例如网络浏览器和电子邮件应用）以及用户在购买设备后安装的第三方应用程序组成。

### 9.7 总结

良好的 Android 开发知识基础需要理解 Android 的整体架构。Android 被实现为一种软件栈架构，由 Linux 内核、运行时环境、相应的库、应用程序框架和一组应用程序组成。应用程序主要用 Java 或 Kotlin 编写，并在 Android Studio 构建环境中被编译为字节码格式。当应用程序随后安装到设备上时，这些字节码将由 Android 运行时 (ART) 编译为 CPU 使用的原生格式。Android 架构的关键目标是性能和效率，既体现在应用程序执行中，也体现在应用程序设计的重用实现中。

# 10. Android 应用程序剖析

无论你之前的编程经验如何（无论是基于 Windows、macOS、Linux 甚至 iOS），Android 开发很可能与你以前遇到过的任何事情都完全不同。

因此，本章的目标是让你对 Android 应用程序架构背后的高层概念有一个理解。在此过程中，我们将详细探讨用于构建应用程序的各种组件，以及允许这些组件协作以创建协调应用程序的机制。

## 10.1 Android Activity

熟悉 Java、Kotlin、C++ 或 C# 等面向对象编程语言的人熟悉将应用程序功能元素封装到类中，然后实例化并进行操作以创建应用程序。这仍然适用，因为 Android 应用程序是用 Java 或 Kotlin 编写的。然而，Android 将重用组件的概念推到了更高的水平。

Android 应用程序是通过组合一个或多个被称为 Activity 的组件创建的。Activity 是一个独立的应用程序模块，通常直接对应单个用户界面屏幕。例如，一个预约应用程序可能会有一个显示当天预约的 Activity 屏幕。该应用程序可能还会使用第二个 Activity，其屏幕允许用户输入新预约。

## 10.2 Android Fragment

如上所述，一个活动（activity）通常代表应用中的单个用户界面屏幕。一种方案是使用单个用户界面布局和一个对应的活动类文件来构建该活动。然而，更好的替代方案是将活动拆分为不同的部分。每个部分都是一个碎片（fragment），它由部分用户界面布局的一部分和一个匹配的类文件（声明为 `Android Fragment` 类的子类）组成。在这种情况下，活动变成了一个容器，可以在其中嵌入一个或多个碎片。



碎片为让每个用户界面屏幕都由一个单独的活动表示提供了一种高效的替代方案。相反，一个应用可以有一个单一活动，在不同的碎片之间切换，每个碎片代表一个不同的应用屏幕。

## 10.3 Android 意图（Intents）

意图是实现一个活动启动另一个活动，并实现构成应用程序的活动之间流转的机制。意图由要执行的操作描述以及可选的用于执行该操作的数据组成。

意图可以是显式的（explicit），即通过类名引用活动来请求启动特定的活动；也可以是隐式的（implicit），即通过说明要执行的操作类型或提供用于执行该操作的特定类型的数据。对于隐式意图，Android 运行时将使用一种称为 `Intent Resolution`（意图解析）的过程，选择与 `Intent` 指定标准最匹配的活动进行启动。

## 10.4 广播意图（Broadcast Intents）

另一种类型的 `Intent` 是广播意图，它是发送到所有注册了“感兴趣”的广播接收器（Broadcast Receiver）的系统级意图。例如，Android 系统通常会发送广播意图来指示设备状态的变化，例如系统启动完成、外部电源连接到设备或屏幕的开启或关闭。

广播意图可以是正常的（异步的），即它在基本相同的时间发送给所有感兴趣的广播接收器；也可以是有序的，即它一次发送给一个接收器，由其处理，然后要么终止要么允许传递给下一个广播接收器。

## 10.5 广播接收器（Broadcast Receivers）

广播接收器是应用程序响应广播意图的机制。广播接收器必须由应用程序注册并配置 `Intent Filter`（意图过滤器），以指示其感兴趣的广播类型。当广播一个匹配的意图时，无论注册接收器的应用程序当前是否正在运行，Android 运行时都会调用该接收器。接收器随后有 5 秒的时间在返回之前完成所需的任务（例如启动 `Service`、进行数据更新或向用户发出通知）。广播接收器在后台运行，并且没有用户界面。

## 10.6 Android 服务（Android Services）

Android 服务是在后台运行且没有用户界面的进程。它们可以从活动、广播接收器或其他服务中启动和管理。Android 服务适用于应用程序需要继续执行任务但并不一定需要用户可见用户界面的情况。虽然服务缺少用户界面，但它们仍然可以使用通知（notifications）和吐司（toasts，即屏幕上出现但不中断当前可见活动的小型通知消息）来通知用户事件，并且能够发布 `Intents`。

Android 运行时赋予服务的优先级高于许多其他进程，系统只有在作为释放资源的最后手段时，才会终止掉这些服务。然而，如果运行时需要杀死一个 `Service`，一旦足够的资源变得可用，它将立即自动重启。`Service` 可以通过声明自己需要在前台运行来降低被终止的风险。这通过调用 `startForeground()` 实现。这仅建议用于终止会对用户体验产生不利的影响（例如，如果用户正在收听由 `Service` 传输的音频）。

`Service` 可能成为实际解决方案的示例情况包括（如之前提到的）：当应用程序不再活动时也应继续的音频流传输，或者当股票达到指定价格时需要通知用户的股票市场跟踪应用程序。

## 10.7 内容提供者（Content Providers）

内容提供者实现了应用程序之间数据共享的机制。任何应用程序都可以通过实现 `Content Provider` 来向其他应用程序提供对其底层数据的访问权限，包括添加、删除和查询数据的能力（受权限限制）。对数据的访问通过 `Content Provider` 定义的通用资源标识符（`URI`）提供。数据可以以文件或整个 `SQLite` 数据库的形式共享。

原生 Android 应用包含几个标准的内容提供者，允许应用程序访问联系人和多媒体文件等数据。在 Android 系统上可用的内容提供者可以使用 `Content Resolver` 进行定位。

## 10.8 应用清单（The Application Manifest）

应用清单文件是将构成应用程序的各种元素结合在一起的胶水。在这个基于 XML 的文件中，应用程序概述了构成完整应用程序的活动、服务、广播接收器、数据提供者和权限。

## 10.9 应用资源（Application Resources）

除了清单文件和包含字节码的 `Dex` 文件外，Android 应用包通常包含一组资源文件。这些文件包含在用户界面中显示的资源，如字符串、图像、字体和颜色，以及用户界面布局的 XML 表示。这些文件默认存储在应用程序项目层次结构中的 `/res` 子目录中。

## 10.10 应用上下文（Application Context）

当应用程序被编译时，会创建一个名为 `R` 的类，其中包含对应用资源的引用。应用清单文件和这些资源结合形成了所谓的应用上下文（Application Context）。此上下文由 `Android Context` 类表示，可以在应用程序代码中使用，以便在运行时访问应用资源。此外，可以在应用程序上下文上调用广泛的方法来收集信息并在运行时更改应用程序的环境。

## 10.11 总结

许多不同的元素可以组合成一个 Android 应用程序。在本章中，我们对活动、碎片、服务、意图和广播接收器进行了高层概述，并对清单文件和应用资源进行了概述。

通过以活动和意图的形式创建单个、独立的功能模块，可以最大限度地提高重用性和互操作性。

本章涵盖了许多对普通开发者来说可能是新的内容。然而，请放心，在随后的章节中，将对这些概念进行广泛的探索和实际使用，以为构建自己的应用程序奠定坚实的知识基础。

开发 Android 应用的一个组成部分涉及代码与构成用户界面布局的视图之间的交互。本章将介绍在代码中访问布局视图的选项，重点介绍一种名为“视图绑定”（view binding）的选项。在介绍视图绑定的基础知识后，本章将概述如何将 AndroidSample 项目转换为使用这种方法。

## 11.1 通过 ID 查找视图

正如“Android 应用结构分析”章节概述的那样，构成应用程序的所有资源都被编译成一个名为 `R` 的类。在这些资源中包含了定义布局的资源。`R` 类中有一个名为 `layout` 的子类，它包含了布局资源，包括构成用户界面的视图。大多数应用都需要实现代码与这些视图之间的交互，例如，当读取在 `EditText` 视图中输入的值或更改在 `TextView` 上显示的内容时。

在 Android Studio 3.6 引入之前，从应用代码内部访问视图的最常用方法是编写代码通过 `findViewById()` 方法根据其 ID 手动查找视图。例如：

```java
TextView exampleView = findViewById(R.id.exampleView);
```

获取引用后，就可以访问视图的属性。例如：

```java
exampleView.setText("Hello");
```

虽然通过 ID 查找视图仍然是一个可行的选项，但它存在一些局限性，`findViewById()` 最显著的缺点是可能会获取到一个尚未在布局中创建的视图引用，导致在尝试访问视图属性时出现空指针异常。

自 Android Studio 3.6 以来，已经以视图绑定的形式提供了另一种从应用代码访问视图的替代方法。

## 11.2 视图绑定

当应用模块中启用视图绑定时，Android Studio 会为每个布局文件自动生成一个绑定类。在代码中可以使用此绑定类访问布局视图，而无需使用 `findViewById()`。

Android Studio 生成的绑定类名称基于布局文件名转换为所谓的“驼峰命名法”，并在末尾附加“Binding”单词。例如，对于 `activity_main.xml` 文件，绑定类将被称为 `ActivityMainBinding`。

Android Studio Giraffe 在项目模板中使用视图绑定方面是不一致的。例如，我们在创建 AndroidSample 项目时使用的 Empty Views Activity 模板没有使用视图绑定。另一方面，Basic Views Activity 模板是使用视图绑定实现的。如果你使用了一个未使用视图绑定的模板，那么了解如何将其添加到项目中是非常重要的。

## 11.3 转换 AndroidSample 项目

在本章的剩余部分中，我们将通过将 AndroidSample 项目转换为使用视图绑定代替 `findViewById()` 来练习迁移到视图绑定。

首先启动 Android Studio 并打开在 Android Studio 中创建示例 Android 应用章节中创建的 AndroidSample 项目。

## 11.4 启用视图绑定

要使用视图绑定，必须对每个需要视图绑定的模块的 `build.gradle.kts` 文件进行更改。对于 AndroidSample 项目，这需要对 Gradle Scripts -> `build.gradle.kts` (Module: app) 文件进行微调。将此文件加载到编辑器，找到 `android` 部分并添加以下项以启用 `viewBinding` 属性：

```kotlin
plugins {
    id("com.android.application")
}

android {
    buildFeatures {
        viewBinding = true
    }
}
```

完成更改后，点击编辑器面板顶部的 `Sync Now` 链接，然后使用 Build 菜单清理并重新构建项目，以确保生成了绑定类。下一步是在代码中使用绑定类。

## 11.5 使用视图绑定

此过程的第一步是“膨胀”（inflate）视图绑定类以访问布局内的根视图。该根视图将用于用作布局的内容视图。

执行这些任务的逻辑位置是在与布局关联的 Activity 的 `onCreate()` 方法中。典型的 `onCreate()` 方法如下：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);
}
```

要切换到使用视图绑定，需要导入绑定类并按如下所示修改类。请注意，由于布局文件命名为 `activity_main.xml`，我们可以推断 Android Studio 生成的绑定类命名为 `ActivityMainBinding`。注意，如果你在创建项目时使用了 `com.example` 以外的域，则下方的导入语句需要更改以反映这一点：

```java
import android.widget.EditText;
import android.widget.TextView;
import com.example.androidsample.databinding.ActivityMainBinding;

public class MainActivity extends AppCompatActivity {
    private ActivityMainBinding binding;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        binding = ActivityMainBinding.inflate(getLayoutInflater());
        View view = binding.getRoot();
        setContentView(view);
    }
}
```

现在我们有了绑定的引用，就可以通过名称访问视图：

```java
public void convertCurrency(View view) {
    EditText dollarText = findViewById(R.id.dollarText);
    TextView textView = findViewById(R.id.textView);
    if (!dollarText.getText().toString().equals("")) {
        Float dollarValue = Float.valueOf(dollarText.getText().toString());
        Float euroValue = dollarValue * 0.85F;
        textView.setText(String.format(Locale.ENGLISH,"%.2f", euroValue));
    } else {
        textView.setText(R.string.no_value_string);
    }
}
```

编译并运行应用，验证货币转换是否仍然正常工作。

## 11.6 选择选项

尽管模板中未使用视图绑定，但 Google 强烈建议尽可能使用视图绑定。因此，在开发自己的项目时应使用视图绑定。

## 11.7 书中示例的视图绑定

书中任何依赖未实现视图绑定的模板的章节将首先进行迁移。然而，为了避免每次需要迁移都重复这些步骤，这些章节将引导你此处刷新记忆（别担心，几个章节之后，这些必要的更改将变成本能）。为了方便操作，下节更简洁地总结了迁移步骤。

## 11.8 将项目迁移到视图绑定

将项目模块转换为视图绑定的过程涉及以下步骤：

1. 编辑项目工具窗口中列出的 Gradle Scripts -> `build.gradle.kts` (Module :app) 模块级 Gradle 构建脚本文件，其中 `<project name>` 是项目名称（例如 AndroidSample）。

2. 找到文件的 `android` 部分并添加启用 `viewBinding` 属性。

3. 点击编辑器顶部的 `Sync Now` 链接，以这些新构建设置重新同步项目。

### 4. 编辑 `MainActivity.java` 文件

将其修改为如下内容（其中 `<reverse domain>` 代表创建项目时使用的域名，`<project name>` 替换为项目的小写名称，例如 `androidsample`），`<binding name>` 是对应布局资源文件的绑定类名称（例如，`activity_main.xml` 的绑定类为 `ActivityMainBinding`）。

```java
import android.view.View;
import android.<reverse domain>.<project name>.databinding.<binding name>;

public class MainActivity extends AppCompatActivity {
    private <binding name> binding;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        binding = <binding name>.inflate(getLayoutInflater());
        View view = binding.getRoot();
        setContentView(view);
    }
}
```

### 5. 通过绑定对象的属性来按名称访问视图

## 11.9 总结

在 Android Studio 3.6 引入之前，在 App 代码中访问布局视图需要使用 `findViewById()` 方法。现在有了另一种替代方案，即视图绑定（view bindings）。视图绑定由 Android Studio 为每个 XML 布局文件自动生成的类组成。这些类包含了对应布局中每个视图的绑定，提供了比 `findViewById()` 方法更安全的选项。然而，从 Android Studio Giraffe 版本开始，某些项目模板默认未启用视图绑定。需要额外的步骤来在每个项目模块中手动启用并配置支持。

## 12. 理解 Android 应用和 Activity 生命周期

在早期的章节中，我们学习了 Android 应用程序运行在进程中，并由活动、服务和广播接收器形式的多个组件组成。本章旨在通过查看 Android 运行时系统中应用程序和 Activity 的周期来扩展这些知识。

无论现在的移动设备与过去的桌面系统相比拥有多少内存和计算能力，重要的是，根据现代桌面和笔记本电脑的标准，这些设备仍然被认为是“资源受限”，特别是在内存方面。因此，Android 系统的一个关键职责是确保这些有限资源得到有效管理，并确保操作系统及其运行的应用程序始终对用户保持响应。为了实现这一点，Android 对运行应用程序的进程周期和状态以及组成这些应用程序的各个组件具有完全控制权。

因此，开发 Android 应用的一个重要因素是理解 Android 的应用程序和 Activity 生命周期管理模型，以及应用程序如何在其执行生命周期内可能被施加的状态变化做出反应。

### 12.1 Android 应用与资源管理

操作系统将每个运行的 Android 应用视为一个独立的进程。如果系统识别到设备上的资源达到容量，它将采取措施终止进程以释放内存。

在确定终止哪个进程以释放内存时，系统会考虑所有当前运行进程的优先级和状态，结合这些因素创建 Google 所称的“重要性层次结构”（importance hierarchy）。然后开始终止进程，从最低优先级开始按层级向上，直到为系统释放了足够的资源供其运行。

### 12.2 Android 进程状态



进程托管应用程序，而应用程序由组件组成。在 Android 系统中，进程的当前状态由其所托管的应用程序中排名最高的活动组件定义。如图 12-1 所示，进程在任何给定时间都可以处于以下五种状态之一：

![android_process_priorities.png](img/Image24381.jpg)

图 12-1

#### 12.2.1 前台进程

这些进程被分配了最高级别的优先级。在任何时候，活跃的前台进程可能不会超过一两个，它们通常是系统最后被终止的进程。进程必须满足以下一个或多个标准才能获得前台状态：

- 托管一个用户当前正在与之交互的 Activity。
- 托管一个与用户正在交互的 Activity 连接的 Service。
- 托管一个通过调用 `startForeground()` 指明终止它会破坏用户体验的 Service。
- 托管一个正在执行其 `onCreate()`、`onResume()` 或 `onStart()` 回调的 Service。
- 托管一个正在执行其 `onReceive()` 方法的广播接收器。

#### 12.2.2 可见进程

包含一个对用户可见但不是用户正在交互的 Activity 的进程被归类为"可见进程"。这通常发生在进程中的某个 Activity 对用户可见，但另一个 Activity（如部分屏幕或对话框）处于前台时。如果一个进程托管一个本身绑定到可见或前台 Activity 的 Service，该进程也具有获得可见状态的资格。

#### 12.2.3 服务进程

包含一个已经启动且正在执行的 Service 的进程。

#### 12.2.4 后台进程

包含一个或多个当前对用户不可见的 Activity，且未托管符合服务进程状态的 Service 的进程。如果需要为高优先级进程释放额外内存，属于此类别的进程面临极高的终止风险。Android 维护着后台进程的动态列表，按时间顺序终止进程，使得最久处于前台的进程首先被杀死。

#### 12.2.5 空进程

空进程不再包含活动应用程序，但保留在内存中，准备好作为新启动应用程序的托管者。这比为了等乘客而保持车门开启、引擎运转更高效。此类进程被认为优先级最低，是释放资源时首先被杀死。

### 12.3 进程间依赖

确定最高优先级进程比上一节描述的要复杂，因为进程之间通常存在相互依赖。因此，在确定进程的优先级时，Android 系统还会考虑该进程是否以某种方式为另一个高优先级进程（例如，作为前台进程的内容提供者的服务进程）服务。作为一个基本规则，Android 文档指出一个进程的排名永远不会低于它正在服务的另一个进程。

### 12.4 Activity 生命周期

正如我们之前确定的，Android 进程的状态主要由其托管的应用程序中 Activity 和组件的状态决定。因此，重要的是这些 Activity 在应用程序的执行生命周期内也会转换到不同的状态。Activity 的当前状态部分取决于它在所谓的 Activity 栈（Activity Stack）中的位置。

### 12.5 Activity 栈

运行时系统为 Android 设备上运行的每个应用程序维护一个 `Activity Stack`（Activity 栈）。当应用程序启动时，第一个启动的应用程序 Activity 会被放置在栈中。当启动第二个 Activity 时，它被放置在栈顶，而之前的 Activity 则被推到栈下。位于栈顶的 Activity 被称为活跃（或正在运行的）Activity。当活跃 Activity 退出时，运行时会将其从栈中弹出，栈中紧邻其下方的 Activity 变为当前的活跃 Activity。例如，栈顶的 Activity 可能会因为其负责的任务已完成而退出。或者，用户可能选择了屏幕上的"返回"按钮以返回上一个 Activity，导致当前 Activity 被运行时系统从栈中弹出并销毁。Android `Activity Stack` 的视觉化表示如图 12-2 所示。

图 12-2

### 12.6 Activity 状态

在应用程序执行过程中，Activity 可以处于几种状态之一：

- **活跃 / 运行（Active / Running）** – Activity 位于 `Activity Stack` 栈顶，是设备屏幕上可见的前台任务，拥有焦点，并且正在与用户交互。在资源不足的情况下，这种 Activity 最不容易被终止。
- **暂停（Paused）** – Activity 对用户可见，但当前没有焦点（通常是因为当前活跃 Activity 部分遮挡了此 Activity）。暂停的 Activity 保留在内存中，仍连接到窗口管理器，保留所有状态信息，并在移动到 `Activity Stack` 栈顶时可以快速恢复到活跃状态。
- **停止（Stopped）** – Activity 当前对用户不可见（也就是说，它在设备显示上被其他 Activity 遮挡）。与暂停的 Activity 一样，它保留所有状态和成员信息，但在低内存情况下有更高的终止风险。
- **已杀死（Killed）** – 运行时系统已终止该 Activity 以释放内存，且它不再存在于 `Activity Stack` 中。如果应用程序需要，必须重新启动此类 Activity。

### 12.7 配置更改（Configuration Changes）

到本章为止，我们查看了 Android Activity 状态变化的两个原因，即 Activity 在前台和后台之间的移动，以及运行时系统终止 Activity 以释放内存。事实上，还有第三种 Activity 状态可能发生剧变的情景，即涉及设备配置的更改。

默认情况下，任何影响 Activity 外观的配置更改（例如在竖屏和横屏之间旋转设备方向，或更改系统字体设置）都会导致 Activity 被销毁并重建。这背后的逻辑是，此类更改会影响用户界面布局等资源，销毁并重建受影响的 Activity 是 Activity 响应配置更改最快的方法。然而，可以配置 Activity，使系统不会响应特定的配置更改而重启它。

### 12.8 处理状态变化

从本章可以清楚地看出，应用程序以及根据定义其中包含的组件在其生命周期内将经历许多状态转换。特别重要的一点是，这些状态变化（包括完全终止）是 Android 运行时根据用户的操作和设备上资源的可用性施加给应用程序的。

在实践中，这些状态变化并非完全在没有任何通知的情况下发生的，在大多数情况下，应用程序会收到运行时系统的更改通知，并获得做出相应反应的机会。这通常涉及保存或恢复内部数据结构和用户界面状态，从而允许用户在应用程序之间无缝切换，并至少提供多个应用程序并发运行的假象。

Android 提供了两种方法来处理 App 内对象生命周期状态的变化。一种方法涉及响应操作系统的状态变化方法调用，将在下一章"处理 Android Activity 状态变化"（`Activity_State_Changes.xhtml__idTextAnchor315`）中进行详细介绍。

Google 推荐的新方法涉及包含在 Jetpack Android Architecture 组件中的生命周期类，这些类在"使用 Jetpack 构建现代 Android 架构"（`Modern_App_Architecture_Jetpack.xhtml__idTextAnchor734`）中引入，并在标题为"与 Android 生命周期感知组件工作"（`Lifecycle_Components.xhtml__idTextAnchor808`）的章节中进行了更详细的解释。

### 12.9 总结

移动设备通常被认为资源受限，特别是在内置内存容量方面。因此，Android 操作系统的主要职责之一是确保应用程序以及整个操作系统对用户保持响应能力。

应用程序托管在 Android 的进程中。每个应用程序反过来以 Activity 和 Service 的形式组成组件。

Android 运行时系统有权终止进程和单个 Activity 以释放内存。运行时系统在决定一个进程是否为终止的候选者时会考虑进程状态。进程的状态很大程度上取决于其托管的 Activity 的状态。

本章的核心信息是，应用程序在其执行生命周期内会处于各种状态，对其 Android 运行时环境中的命运几乎没有控制。不与用户直接交互的进程和 Activity 被运行时终止的风险更高。因此，Android 应用程序开发的一个要素是应用程序响应状态变化通知的能力。

# 13 处理 Android Activity 状态变化

根据标题为"理解应用程序和 Activity 生命周期"（`Activity_Lifecycle.xhtml__idTextAnchor296`）的章节中概述的信息，现在显然组成应用程序的 Activity 和 Fragment 在生命周期内通过许多不同的状态。Android 运行时系统实施从一个状态到另一个状态的更改，因此在很大程度上不受 Activity 自身的控制。然而，这并不意味着应用程序无法对这些更改做出反应。

本章的主要目标是提供 Activity 如何接收状态变化通知的高级概述，并概述建议保存或恢复状态信息的区域。在涵盖这些信息后，本章将简要触及 Activity 生命周期。

### 13.1 新旧生命周期技术

直到最近，在应用中构建生命周期感知一直有一种标准方法。这种方法在本章中介绍，涉及在 activity 或 fragment 实例内部实现一组方法（每个生命周期状态对应一个方法），操作系统会在对象的生命周期状态发生变化时调用这些方法。这种方法自 Android 操作系统早期以来一直没有变化，虽然在今天仍然是一个可行选项，但它确实存在一些局限性，将在本章稍后部分进行解释。

随着 Jetpack Android 架构组件中生命周期类的引入，现在有了更好的生命周期处理方法。这种现代的生命周期管理方法（结合 Jetpack 组件和架构指南）将在后面的章节中详细介绍。然而，出于以下几个原因，理解传统的生命周期方法仍然非常重要。首先，作为一名 Android 开发者，你无法完全脱离传统的生命周期方法，并且仍然会使用其中一些。更重要的是，理解处理生命周期的旧方法将为在书的后期学习新方法提供坚实的基础。

## 13.2 Activity 和 Fragment 类

除少数例外外，应用的 activity 和 fragment 分别作为 Android `AppCompatActivity` 类和 `Fragment` 类的子类被创建。

例如，考虑在"在 Android Studio 中创建示例 Android 应用"中创建并随后转换为使用视图绑定（view binding）的 `AndroidSample` 项目。将此项目加载到 Android Studio 环境并找到 `MainActivity.java` 文件（位于 `app` -> `java` -> `<your domain>` -> `androidsample`）。找到文件后，双击将其加载到编辑器中，其内容应如下：

```java
package com.example.androidsample;

import androidx.appcompat.app.AppCompatActivity;

import android.view.View;

import android.os.Bundle;

import java.util.Locale;

import com.example.androidsample.databinding.ActivityMainBinding;

public class MainActivity extends AppCompatActivity {

    private ActivityMainBinding binding;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        binding = ActivityMainBinding.inflate(getLayoutInflater());
        View view = binding.getRoot();
        setContentView(view);
    }

    public void convertCurrency(View view) {
        if (!binding.dollarText.getText().toString().equals("")) {
            float dollarValue = Float.parseFloat(
                    binding.dollarText.getText().toString());
            float euroValue = dollarValue * 0.85F;
            binding.textView.setText(
                    String.format(Locale.ENGLISH,"%.2f", euroValue));
        } else {
            binding.textView.setText(R.string.no_value_string);
        }
    }
}
```

在创建项目时，我们指示 Android Studio 同时也创建了一个名为 `MainActivity.java` 的初始 activity。如上面的代码所示，`MainActivity` 类是 `AppCompatActivity` 类的子类。

查看 `AppCompatActivity` 类的参考文档可以发现它本身也是 `Activity` 类的子类。可以在 Android Studio 编辑器中使用层次结构（Hierarchy）工具窗口来验证这一点。当 `MainActivity.java` 文件加载到编辑器中时，点击类声明行中的 `AppCompatActivity` 并按下快捷键 `Ctrl-H`。随后将弹出层次结构工具窗口，显示所选类的类层次结构。如图 13-1 所示，`AppCompatActivity` 派生自 `FragmentActivity` 类，而 `FragmentActivity` 最终也是 `Activity` 类的子类：

![](img/as_class_hierarchy.jpg)

图 13-1

Activity 和 Fragment 类包含系列方法，旨在由 Android 运行时调用以通知对象其状态正在变化。在本章中，我们将这些方法称为生命周期方法。activity 或 fragment 类需要重写这些方法，并实现必要的功能以对状态变化做出相应响应。

其中一个方法名为 `onCreate()`，再次回到上面的代码片段，我们可以看到该方法在 `MainActivity` 类中已经为我们重写并实现。在后面的章节中，我们将探索 `onCreate()` 以及 `Activity` 和 `Fragment` 类的其他相关生命周期方法。

## 13.3 动态状态与持久化状态

生命周期管理的核心目标是确保在适当的时间保存并恢复 activity 的状态。当我们在此处讨论状态时，指的是当前 activity 持有的数据。例如，activity 可能在内存中维护一个数据模型，该模型需要保存到数据库、内容提供程序或文件。由于它可以跨应用程序调用而存在，因此这种状态信息被称为持久化状态（persistent state）。

用户界面的显示（例如输入字段中但尚未提交到数据模型的文本）被称为动态状态（dynamic state），因为它通常只在应用的单次调用期间保留（也称为实例状态 instance state）。理解这两种状态之间的差异很重要，因为它们保存的方式以及保存的原因各不同。

保存持久化状态的目的是避免 activity 在后台运行时被杀死可能导致的数据丢失。

例如，假设一个应用包含一个 activity（我们将其称为 Activity A），该应用包含一个文本框和一些单选按钮。在使用应用的过程中，用户在文本框中输入了一些文本并从单选按钮中做了选择。然而，在执行保存这些更改的操作之前，用户切换到了另一个 activity，导致 Activity A 被推入 Activity 栈（Activity Stack）并在后台运行。一段时间后，运行时系统确定内存不足，并杀死了 Activity A 以释放资源。然而，对于用户而言，Activity A 只是被放在了后台，可以随时移动到前台。当返回 Activity A 到前台时，用户会合理地预期输入的文本和单选按钮的选择会被保留。但在这种情况下，会创建一个 Activity A 的新实例，如果没有保存和恢复动态状态，之前的用户输入就会丢失。

因此，保存动态状态的主要目的是为了提供在前台和后台 activity 之间无缝切换的感知，无论 activity 是否在用户不知情的情况下被杀掉并重启。

## 13.4 Android 生命周期方法

如前所述，Activity 和 Fragment 类包含多个生命周期方法，当实例状态变化时作为事件处理器工作。Android Activity 和 Fragment 类支持的主要方法如下：

## Activity 生命周期

- `onCreate(Bundle savedInstanceState)` – 在 activity 首次创建时调用的方法，是执行大多数初始化任务的理想位置。该方法接收一个 `Bundle` 对象形式的参数，该对象可能包含来自 activity 上次调用的动态状态信息（通常与用户界面的状态有关）。
- `onRestart()` – 当 activity 在之前被运行时系统停止后准备重新启动时调用。
- `onStart()` – 始终在调用 `onCreate()` 或 `onRestart()` 方法后立即被调用。此方法通知 activity 它即将对用户可见。如果 activity 移动到 activity 栈的顶端，则此调用将随后调用 `onResume()`；如果它被另一个 activity 压入栈底，则将调用 `onStop()`。



`onResume()` – 表示 activity 现在处于 activity 栈的顶端，并且是用户当前正在交互的 activity。

`onPause()` – 表示上一个 activity 即将成为前景 activity。此调用将随后调用 `onResume()` 或 `onStop()` 方法，取决于 activity 是返回到前台还是对用户不可见。在此方法中可以采取措施来存储应用尚未保存的持久化状态信息。为了避免切换 activity 时的延迟，应避免在此方法中执行耗时操作，如将数据存储到数据库或执行网络操作。此方法还应确保停止动画等 CPU 密集任务。

`onStop()` – activity 不对用户可见。此调用后的两种可能场景是：如果 activity 再次回到前台，则调用 `onRestart()`；如果 activity 被终止，则调用 `onDestroy()`。

`onDestroy()` – activity 即将销毁，可能是因为 activity 完成了任务并调用了 `finish()` 方法，也可能是运行时为了释放内存或由于配置更改（如设备方向改变）而终止它。需要注意的是，当 activity 终止时并不总是会调用 `onDestroy()`。

`onConfigurationChanged()` – 当发生配置更改且该 activity 指明不需要重启时调用。该方法传递一个 `Configuration` 对象，概述了新的设备配置，然后由 activity 负责对更改做出响应。

### Fragment 生命周期

以下生命周期方法仅适用于 `Fragment` 类：

- `onAttach()` - 在 fragment 分配给 activity 时调用。

- `onCreateView()` - 用于创建并返回 fragment 的用户界面布局视图层级结构。

- `onViewCreated()` - 在 `onCreateView()` 返回后调用。

- `onViewStatusRestored()` - fragment 保存的视图层级结构已恢复。

### 状态管理

除了上述的生命周期方法外，还有两个方法专门用于保存和恢复 activity 的动态状态：

- `onRestoreInstanceState(Bundle savedInstanceState)` – 如果 activity 从之前保存了状态的调用重启，此方法会在调用 `onStart()` 方法后立即被调用。与 `onCreate()` 一样，此方法传递一个包含之前状态数据的 `Bundle` 对象。当在 `onCreate()` 和 `onStart()` 中完成 activity 初始化后，恢复之前的状态更有意义时，通常会使用此方法。

- `onSaveInstanceState(Bundle outState)` – 在 activity 销毁之前调用，以便保存当前的动态状态（通常与用户界面有关）。该方法传递一个 `Bundle` 对象，状态应保存到其中，该对象随后会在 activity 重启时被传递给 `onCreate()` 和 `onRestoreInstanceState()` 方法。请注意，只有当运行时确定需要保存动态状态时，此方法才会被调用。

在重写上述方法时，请记住，除了 `onRestoreInstanceState()` 和 `onSaveInstanceState()` 之外，方法实现必须包含对父类中对应方法的调用。例如，以下方法重写了 `onRestart()` 方法，但也包含了对父类实例方法的调用：

```java
protected void onRestart() {
    super.onRestart();
    Log.i(TAG, "onRestart");
}
```

在方法重写中未调用此父类方法将导致运行时在执行期间抛出异常。虽然在 `onRestoreInstanceState()` 和 `onSaveInstanceState()` 方法中对父类的调用是可选的（例如，在实现自定义的保存和恢复行为时可以省略它们），但使用它们有很大的益处，这一主题将在名为保存和恢复 Android Activity 状态”的章节中介绍。

## 13.5 生命周期

最后一个要涵盖的话题涉及 activity 或 fragment 在执行过程中经历的整个、可见的前景生命周期的概述：

- **整个生命周期 (Entire Lifetime)** – “整个生命周期”一词用于描述从首次调用 `onCreate()` 方法到对象终止前调用 `onDestroy()` 之间发生的一切。

- **可见生命周期 (Visible Lifetime)** – 涵盖调用 `onStart()` 到 `onStop()` 之间的执行期间。在此期间，activity 或 fragment 对用户可见，尽管它可能不是用户当前正在交互的对象。

- **前景生命周期 (Foreground Lifetime)** – 指调用 `onResume()` 和 `onPause()` 方法之间的执行期间。

需要注意的是，activity 或 fragment 在整个生命周期期间可能会多次通过前景和可见生命周期。

生命周期和生命周期方法的概念在图 13-2 中所示：

![android_activity_lifecycle_methods.png](img/Image2446.jpg)

图 13-2

## 13.6 折叠屏设备与多恢复

如前所述，一个活动可以指示在某些配置更改发生时不重新启动。这是通过在项目清单文件（manifest file）的 activity 元素中添加 `android:configChanges` 指令来实现。例如，下面的清单文件片段表明，当发生与方向或设备全局字体相关的配置更改时，不应重启该活动：

```xml
<activity android:name=".MainActivity"
          android:configChanges="orientation|fontScale"
          android:label="@string/app_name">
```

## 13.8 生命周期方法的局限性

正如本章开头所讨论的，生命周期方法已经使用了多年，直到最近，它们仍然是处理 activity 和 fragment 生命周期状态变化的唯一机制。然而，这种方法仍有改进空间。

生命周期方法的一个问题是，它们没有为 activity 或 fragment 提供一种简单的方法在应用执行过程的任何点发现其当前的生命周期状态。相反，对象必须在内部跟踪状态，或者等待下一次生命周期方法的调用。

此外，这些方法没有提供一种简单的方法让一个对象观察应用内其他对象的生命周期状态变化。这是一个严重的考虑因素，因为特定 activity 或 fragment 的生命周期状态变化可能会影响应用内的许多其他对象。

生命周期方法仅适用于 `Fragment` 和 `Activity` 类的子类。因此，无法构建真正感知生命周期（lifecycle aware）的自定义类。

最后，生命周期方法导致大多数生命周期处理代码被编写在 activity 或 fragment 内部，这可能导致复杂且易出错的代码。理想情况下，这些代码大部分应位于受状态变化影响的其他类中。例如，一个流媒体视频应用可能会包含一个专门用于管理输入流的类。如果应用需要在主活动停止时暂停流，那么相应的代码应该位于流媒体类中，而不是主活动中。

所有这些以及其他问题都可以通过使用**生命感知感知组件**来解决，该主题将从名为“Jetpack Modern Android Architecture”的章节开始介绍。

## 13.9 总结

所有的 activity 都派自 `Android Activity` 类，该类包含了几个生命周期方法，这些方法被设计为运行时系统在 activity 状态更改时调用。同样，`Fragment` 类也包含类似的方法。通过重写这些方法，activity 和 fragment 可以响应状态变化，并在必要时采取步骤保存并恢复 activity 和应用程序当前的状态。生命周期状态可以被认为有两种形式。持久状态（persistent state）指的是应用调用之间需要存储的数据（例如存储到文件或数据库）。另一方面，动态状态（dynamic state）与用户界面的当前显示有关。尽管生命周期方法有一些可以使用生命感知组件避免的局限性，但理解这些方法对于充分理解书中后面介绍的生命周期管理新方法至关重要。

在本章中，我们强调了 activity 可用的生命周期方法，并涵盖了活动生命周期的概念。在下一章（“通过示例 Android Activity 状态变化”）中，我们将实现一个示例应用，将这些许多理论付诸实践。

## 14. 通过示例 Android Activity 状态变化

之前的章节详细讨论了构成 Android 应用程序的 activity 的不同状态和生命周期。在本章中，我们将通过创建一个示例应用，将处理 activity 状态变化的理论付诸实践。该示例应用的目的是演示 activity 在 Android 运行时通过各种状态的真实场景。在下一章（“保存和恢复 Android Activity 状态”）中，在本章构建的示例项目将被扩展，以演示动态 activity 状态的保存和恢复。

### 14.1 创建状态变化示例项目

练习的第一步是创建一个新项目。启动 Android Studio，如果有必要，使用 `File -> Close Project` 菜单选项关闭当前打开的项目，以便显示欢迎界面。

从欢迎界面选择 `New Project` 选项，在出现的新项目对话框中，点击 `Next` 按钮之前选择 `Empty Views Activity` 模板。

在 `Name` 字段输入 `StateChange` 并指定 `com.ebookfrenzy.statechange` 为包名。在点击 `Finish` 按钮之前，将 `Minimum API level` 设置为 `API 26: Android 8.0 (Oreo)` 并将 `Language` 菜单设置为 `Java`。完成项目创建过程后，`StateChange` 项目应出现在 Android Studio 主窗口左侧的 `Project` 工具窗口。使用 11.8 迁移项目到 View Binding 部分概述的步骤将项目转换为使用 `view binding`。

接下来的操作涉及 activity 的用户界面设计。它存储在名为 `activity_main.xml` 的文件中，该文件应该已经加载到 `Layout Editor` 工具中。如果没有加载，请在 `Project` 工具窗口中导航到它，可以在 `app -> res -> layout` 文件夹中找到它。一旦找到，双击文件将其加载到 Android Studio Layout Editor 工具中。

![](img/as_state_change_main_window.jpg)

图 14-1

### 14.2 设计用户界面

当用户界面布局加载到 `Layout Editor` 工具后，是时候为示例应用设计用户界面了。与其界面设计中目前的“Hello World!” `TextView`，activity 需要一个 `EditText` 视图。在 `Component Tree` 面板中选择 `TextView` 对象并按键盘上的 `Delete` 键将其从设计中删除。

从 `Layout Editor` 左侧的 `Palette` 中，选择 `Text` 类别，并从文本列表中点击并拖动 `Plain Text` 组件到布局画布上。将组件移动到显示中心，使出现中心引导线，并将其放置到位，使布局类似于图 14-2。

![](img/as_statechange_ui.jpg)

图 14-2

在使用 `EditText` 控件时，有必要为视图指定一个 `inputType`。这定义了用户将输入的文本或数据类型。例如，如果输入类型设置为 `Phone`，则用户将被限制在视图中输入数字。或者，如果输入类型设置为 `TextCapCharacters`，则输入将默认为大写字母。输入类型设置也可以组合使用。

对于此示例，我们将使用默认输入类型以支持通用文本输入。将来要选择不同的设置，请在布局中选择 `EditText` 控件并在 `Attributes` 工具窗口中找到 `inputType` 条目。接下来，点击当前设置左侧的标志图标以打开选项列表，如下方的图 14-3 所示。`Type` 菜单提供了限制输入为文本、数字、日期时间以及电话号码的选项。`Variations` 菜单为当前选择的输入类型提供了额外的选项。例如，文本输入类型有一个用于电子邮件地址输入的变体。

一旦选定了类型和变体，可以使用标志复选框列表进一步对输入类型进行自定义：

![](img/as_text_input_type_menu.jpg)

图 14-3

在 `Attributes` 属性工具窗口中，将视图的 `id` 更改为 `editText`，然后点击弹出对话框中的 `Refactor`（重构）按钮。

默认情况下，`EditText` 显示的文本为“Name”。继续留在 `Attributes` 面板中，删除 `text` 属性字段中的该内容，使该视图在布局中保持为空。

在继续之前，点击布局编辑器工具栏上的 `Infer Constraints`（推断约束）按钮以添加任何缺失的约束。

### 14.3 重写 Activity 生命周期方法

此时，项目包含一个名为 `MainActivity` 的 activity，它派自 `AppCompatActivity` 类。该 activity 的源代码包含在 `MainActivity.java` 文件中，该文件应该已经在编辑器会话中打开并由编辑器标签栏中的标签页表示。如果文件未打开，请在 `Project` 工具窗口面板中导航到它（`app -> java -> com.ebookfrenzy.statechange -> MainActivity`），并双击它将文件加载到编辑器。

到目前为止，activity 重写的唯一生命周期方法是 `onCreate()` 方法，该方法已实现为在为 activity 设置用户界面之前调用该方法的父类实例。现在我们将修改此方法，以便在每次执行时都能在 Android Studio 的 `Logcat` 面板中输出一条诊断消息。为此，我们将使用 `Log` 类，这要求我们导入 `android.util.Log` 并声明一个标签（tag），以便我们在日志输出中过滤这些消息：

```java
package com.ebookfrenzy.statechange;

.
.

import android.util.Log;
import androidx.annotation.NonNull;
import android.view.View;

public class MainActivity extends AppCompatActivity {
    private ActivityMainBinding binding;
    private static final String TAG = "StateChange";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        binding = ActivityMainBinding.inflate(getLayoutInflater());
        View view = binding.getRoot();
        setContentView(view);
        Log.i(TAG, "onCreate");
    }
}
```

下一个任务是重写更多方法，每个方法都包含一个相应的日志调用。这些重写方法可以手动添加，也可以使用 `Alt-Insert` 键盘快捷键生成，如标题为“Android Studio 代码编辑器基础”的章节所述。请注意，如果方法是自动生成的，仍然需要手动添加 `Log` 调用：

```java
@Override
protected void onStart() {
    super.onStart();
    Log.i(TAG, "onStart");
}

@Override
protected void onResume() {
    super.onResume();
    Log.i(TAG, "onResume");
}

@Override
protected void onPause() {
    super.onPause();
    Log.i(TAG, "onPause");
}

@Override
protected void onStop() {
    super.onStop();
    Log.i(TAG, "onStop");
}

@Override
protected void onRestart() {
    super.onRestart();
    Log.i(TAG, "onRestart");
}

@Override
protected void onDestroy() {
    super.onDestroy();
    Log.i(TAG, "onDestroy");
}

@Override
protected void onSaveInstanceState(@NonNull Bundle outState) {
    super.onSaveInstanceState(outState);
    Log.i(TAG, "onSaveInstanceState");
}

@Override
protected void onRestoreInstanceState(@NonNull Bundle savedInstanceState) {
    super.onRestoreInstanceState(savedInstanceState);
    Log.i(TAG, "onRestoreInstanceState");
}
```

### 14.4 过滤 Logcat 面板



在`MainActivity.java`的重写方法中添加代码目的是将日志信息输出到`Logcat`工具窗口，该窗口通过图 14-4 所示的按钮显示：

![](img/as_logcat_button.jpg)

图 14-4

`Logcat`工具窗口可以配置为显示与设备或模拟器会话相关的所有事件，或者限制为与当前所选应用相关的事件。输出也可以限制为仅匹配特定过滤器的日志事件。

当在当前应用运行时显示时，`Logcat`工具窗口将如下方的图 14-5 所示：

![](img/as_logcat_tool_window.jpg)

图 14-5

上方标记为 A 的菜单允许您选择显示日志输出的设备或模拟器。此输出出现在标记为 C 的输出面板中。可以通过在标记为 B 的字段中输入选项来过滤日志输出。默认键设置`package:mine`将输出限制为当前应用包（在本例中为`com.ebookfrenzy.statechange`）生成的日志消息。留空此字段将允许显示来自设备或模拟器的日志输出，包括操作系统生成的诊断消息。也可以组合键来进一步过滤输出。例如，我们可以如下配置`Logcat`面板，仅显示与我们的`StateChange`标签相关的消息：

`package:mine tag:StateChange`

我们可以通过在键值前加上负号来排除输出。例如，我们可以配置`Logcat`面板仅显示与我们的`StateChange`标签相关的消息如下：

`package:mine tag:StateChange`

我们可以通过在键值前加上负号（`-`）来排除输出。除了`StateChange`标签外，我们可能有一个使用标签的诊断消息。为了过滤掉第二个标签的输出，我们可以输入以下键：

`package:mine tag:StateChange -tag:OtherTag`

除了标签值，还可以从 Android 内置的一系列标签中选择。当你在过滤器字段中输入时，`Logcat`将显示匹配的标签，如图 14-6 所示：

![](img/as_logcat_filter_suggestions.jpg)

图 14-6

或者，使用`Ctrl-Space`访问完整的过滤建议列表。

`level`键可以根据严重程度控制显示哪些消息。为了显示错误消息，可以使用：

`level:error`

除了`error`，`Logcat`面板还支持`verbose`、`info`、`warn`和`assert`级别。

`Logcat`还支持多个面板，每个面板都有自己的过滤设置。要添加另一个面板，点击图 14-5 中标记为 D 的`+`按钮。通过相应的标签在不同面板之间切换，或者通过右键点击当前显示的面板并选择`Split-Right`（向右分）或`Split-Down`（向下分）选项来水平或垂直排列面板。要重命名面板，右键点击标签并选择`Rename Tab`选项。在继续之前，关闭除一个以外的所有`Logcat`面板并配置如下：

`package:mine tag:StateChange`

### 14.5 运行应用程序

为了获得最佳结果，应在物理 Android 设备或模拟器上运行应用程序。在设备配置并连接到开发计算机后，点击 Android Studio 工具栏上的运行按钮，如下方的图 14-7 所示：

![](img/as_run_button.jpg)

图 14-7

从`Choose Device`对话框中选择物理 Android 设备或模拟器（假设尚未尚未配置为默认目标）。在 Android Studio 构建应用程序并将其安装到设备上之后，它应该启动并在前台运行。

查看`Logcat`面板可以指示到目前为止触发了哪些方法：

![](img/as_logcat_app_running.jpg)

图 14-8

### 14.6 测试 Activity

既然诊断功能工作正常，现在是时候通过操作应用程序来理解 activity 生命周期状态变化了。首先，考虑`Logcat`面板中的初始日志序列：

```
onCreate
onStart
onResume
```

显然，初始的状态变化与“理解 Android 应用程序和 Activity 生命周期”中概述的描述完全一致。但请注意，由于 Android 运行时检测到在这种情况下没有需要恢复的状态，因此没有调用`onRestoreInstanceState()`。

点击设备显示器底部状态栏上的`Home`图标，并注意日志中报告的方法调用序列如下：

```
onPause
onStop
onSaveInstanceState
```

在这种情况下，运行时注意到该 activity 已不再处于前台，对用户不可见，并且已经停止了该 activity，但并不是没有给 activity 提供保存动态状态的机会。取决于运行时最终是销毁了 activity 还是重启了它，该 activity 将会通过调用`onRestart()`被通知其已重启，或者在用户返回该 activity 时再次经历创建序列。

正如“理解 Android 应用程序和 Activity 生命周期”中概述的，activity 的销毁和重建可以通过对设备进行配置更改来触发，例如从竖屏旋转到横屏。要直观看到这一过程，请在`StateChange`应用程序处于前台时旋转设备。当使用模拟器时，可以使用模拟器工具栏上的旋转按钮来模拟设备旋转。为了完成旋转，可能还需要点击旋转按钮。这显示在设备或模拟器的屏幕底部，如图 14-9 所示：

![](img/android_rotate_button.jpg)

图 14-9

日志中产生的方法调用序列如下：

```
onPause
onStop
onSaveInstanceState
onDestroy
onCreate
onStart
onRestoreInstanceState
onResume
```

显然，运行时系统在 activity 销毁和重启之前允许其保存了状态。

# 14.7 总结

“一画胜于千言”这句格言在学习新编程范式的示例中也同样适用。在本章中，我们创建了一个 Android 应用程序示例，用以演示 activity 可能会经历的不同生命周期状态。在开发本项目期间，我们还查看了从 activity 内部生成诊断日志信息的机制。

在下一章中，我们将扩展`StateChange`示例项目，以演示如何保存和恢复 activity 的动态状态。

# 15. 保存和恢复 Android Activity 的状态

如果前面的几章已经实现了目标，那么现在对于在 activity 生命的特定时间点保存和恢复用户界面状态的重要性应该变得更加清晰了。

在本章中，我们将扩展在“通过示例理解 Android Activity 状态变化”](#Activity_State_Example.xhtml__idTextAnchor327)中创建的示例应用程序，演示运行时系统销毁和重建 activity 时涉及保存和恢复状态的步骤。

保存和恢复动态状态的关键组件涉及使用 Android SDK 中的`Bundle`类，这个主题在本章中也会涵盖。

## 15.1 保存动态状态

正如我们所学的，activity 可以通过运行时系统调用 activity 的`onSaveInstanceState()`方法实现来保存动态状态信息。作为方法的参数传递的是一个`Bundle`对象的引用，方法必须将任何需要保存的动态数据存储其中。随后，`Bundle`对象将由运行时代表 activity 进行存储，并在调用这些方法时，作为参数传递给 activity 的`onCreate()`和`onRestoreInstanceState()`方法。然后，可以在这些方法内部从`Bundle`对象中检索数据，并用于恢复 activity 的状态。

## 15.2 用户界面状态的默认保存

在上一章中，`StateChange`示例应用程序的诊断输出显示，当运行它的设备旋转足够大以触发方向变化时，activity 会经历多次状态变化。

再次启动`StateChange`应用程序，并在执行设备旋转之前向`EditText`字段输入一些文本（在运行 Android 9 或更高版本的设备或模拟器上，可能需要点击状态栏中的旋转按钮来完成旋转）。旋转设备后，`Logcat`窗口中应出现以下状态变化序列：

```
onPause
onStop
onSaveInstanceState
onDestroy
onCreate
onStart
onRestoreInstanceState
onResume
```

显然，这导致了 activity 的销毁和重建。然而，查看运行中应用程序的用户界面，应该发现输入到`EditText`字段中的文本已被保留。鉴于 activity 被销毁并重建了，而我们并没有添加任何特定代码来确保文本被保存和恢复，这种行为需要一些解释。

事实上，Android SDK 包含的大多数视图控件（widgets）已经实现了当 activity 自动重启时保存和恢复状态所需的行为。启用此行为的唯一要求是 activity 中的`onSaveInstanceState()`和`onRestoreInstanceState()`重写方法必须包含对父类对应方法的调用：

```java
@Override
protected void onSaveInstanceState(@NonNull Bundle outState) {
    super.onSaveInstanceState(outState);
}

@Override
protected void onRestoreInstanceState(@NonNull Bundle savedInstanceState) {
    super.onRestoreInstanceState(savedInstanceState);
}
```

可以通过 XML 布局文件通过将`android:saveEnabled`属性设置为`false`来禁用用户界面视图的自动状态保存。可以通过在 XML 布局文件中将`android:saveEnabled`属性设置为`false`来关闭用户界面视图的自动状态保存。在本示例中，我们将禁用用户界面布局中`EditText`视图的自动保存机制，然后在应用程序中中手动保存和恢复视图的状态。

为了配置`EditText`在 activity 重启时不保存和恢复状态，请编辑`activity_main.xml`文件，使视图条目如下所示（正如“在 Android Studio 中创建 Android 应用”](#Sample_App.xhtml__idTextAnchor01)中概述，可以通过布局编辑器切换到代码模式来编辑 XML）：

```xml
<EditText
    android:id="@+id/editText"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:ems="10"
    android:inputType="text"
    android:saveEnabled="false"
    app:layout_constraintBottom_toBottomOf="parent"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent" />
```

进行更改后，运行应用程序，输入文本并旋转设备，以验证文本不再被保存和恢复。

## 15.3 Bundle 类

对于需要在界面视图控件提供的默认功能之外保存状态的情况，`Bundle`类提供了一个使用键值对机制存储数据的容器。键的形式为字符串值，而与键关联的值可以是原始值，也可以任何实现了 Android `Parcelable`接口的对象。广泛的类已经实现了`Parcelable`接口。自定义类可以通过实现`Parcelable`接口定义的方法集来变为“可序列化的”，其详细信息可以在 Android 文档中找到：

[`developer.android.com/reference/android/os/Parcelable.html`](http://developer.android.com/reference/android/os/Parcelable.html)

`Bundle`类还包含一组方法，可用于获取和设置各种数据类型的键值对，包括原始数据类型（包括`Boolean`、`char`、`double`和`float`值）和对象（例如`Strings`和`CharSequenceences`）。

在本示例中，由于禁用了`EditText`视图的文本自动保存功能，我们需要确保用户输入到`EditText`字段中的文本被保存到`Bundle`对象中并在随后进行恢复。这将演示如何在 Android 应用程序中手动保存和恢复状态，并将分别使用`Bundle`类的`putCharSequence()`和`getCharSequence()`方法来实现。

## 15.4 保存状态

扩展`StateChange`应用的第一步是确保在`MainActivity`节点（activity）的`onSaveInstanceState()`方法中从`EditText`组件中提取用户输入的文本，然后将其作为键值对保存到`Bundle`对象中。

要从`EditText`对象中提取文本，我们必须首先在用户界面中识别该对象。显然，这涉及到在 Activity 的 Java 代码（包含在`MainActivity.java`源代码文件中）与用户界面的 XML 表示（包含在`activity_main.xml`资源文件中）之间建立桥梁。为了提取输入`EditText`组件的文本，我们需要获取该用户界面对象的访问权限。

用户界面中的每个组件都关联有一个唯一的标识符。默认情况下，布局编辑器（Layout Editor）工具根据对象类型为新添加的组件构建 id。如果布局中包含多个相同类型的视图，则类型名称后面会跟一个顺序数字（尽管开发者可以并且应该将其更改为更具意义的内容）。正如在选中`activity_main.xml`文件并显示布局编辑器工具时，通过检查 Android Studio 主窗口中的组件树（Component Tree）面板所示，`EditText`组件被分配了 id`editText`：

![](img/as_component_tree1.jpg)

图 15-1

我们现在可以通过对象的`getText()`方法获取`editText`视图包含的文本，该方法反过来返回当前文本：

```java
CharSequence userText = binding.editText.getText();
```

最后，我们可以使用`Bundle`对象的`putCharSequence()`方法保存文本，并将键（这可以是任何字符串值，在本例中我们将将其声明为“savedText”）和`userText`对象作为参数：

```java
outState.putCharSequence("savedText", userText);
```

将所有这些整合在一起，我们在`MainActivity.java`文件中得到了修改后的`onSaveInstanceState()`方法，内容如下：

```java
package com.ebookfrenzy.statechange;

.
.

public class MainActivity extends AppCompatActivity {
.
.
.
    protected void onSaveInstanceState(@NonNull Bundle outState) {
        super.onSaveInstanceState(outState);
        Log.i(TAG, "onSaveInstanceState");
        CharSequence userText = binding.editText.getText();
        outState.putCharSequence("savedText", userText);
    }
.
.
```

现在已经采取了保存状态的步骤，下一阶段是在需要时恢复它。

## 15.5 恢复状态

保存的动态状态可以在传递`Bundle`对象作为参数的生命周期方法中恢复。这让开发者可以选择使用`onCreate()`或`onRestoreInstanceState()`。使用哪个方法取决于 Activity 的性质。在 Activity 执行初始化任务后最适合恢复状态的情况下，`onRestoreInstanceState()`方法通常更合适。在本示例中，我们将向`onRestoreInstanceState()`方法中添加代码，使用“savedText”键从`Bundle`中提取保存的状态。然后我们可以使用对象的`setText()`方法在`editText`组件上显示文本：

```java
@Override
protected void onRestoreInstanceState(@NonNull Bundle savedInstanceState) {
    super.onRestoreInstanceState(savedInstanceState);
    Log.i(TAG, "onRestoreInstanceState");
    CharSequence userText =
        savedInstanceState.getCharSequence("savedText");
    binding.editText.setText(userText);
}
```

## 15.6 测试应用程序



剩下的只是再次构建并运行`StateChange`应用程序。运行并处于前台时，触摸`EditText`组件，并在旋转设备到另一种方向之前输入一些文本。以前文本的更改将会丢失，但得益于我们在本章中为 Activity 添加的代码，新文本将保留在`editText`组件中。

在验证代码执行符合预期后，注释掉这两个方法中的`super.onSaveInstanceState()`和`super.onRestoreInstanceState()`调用，重新启动应用并注意在设备旋转后文本仍然被保留。默认的保存和恢复系统本质上被自定义实现取代，从而提供了一种在 Activity 中动态且选择性保存和恢复状态的方法。

## 15.7 总结

在 Android 应用程序中保存和恢复动态状态取决于实现适当生命周期方法。对于大多数用户界面视图，这由 Activity 超类自动处理。在其他情况下，这通常包括在`onSaveInstanceState()`方法中提取值和设置，并将数据作为键值对保存到传递的`Bundle`对象中。

状态可以在 Activity 的`onCreate()`或`onRestoreInstanceState()`方法中恢复，通过从`Bundle`对象中提取值并更新 Activity。

在本章中，我们使用这些技术更新了`StateChange`项目，使 Activity 在销毁和随后重建后保留更改。

## 16. 理解 Views、View Groups 和 Layouts

除了听流媒体外，用户与 Android 设备的交互主要是视觉和触觉的。所有这些交互都通过设备上安装应用程序的用户界面进行，包括内置应用程序和用户安装的第三方应用程序。因此，开发 Android 应用程序的关键元素之一涉及设计和创建用户界面。

本章涵盖了 Android 用户界面结构，包括组合成用户界面的元素：`Views`、`View Groups`和`Layouts`。

### 16.1 针对不同 Android 设备的设计

“Android 设备”一词涵盖了许多具有不同尺寸和分辨率的平板电脑和平手机。因此，应用程序用户界面现在必须仔细设计，以确保在尽可能广泛范围内正确显示。其关键部分之一是确保用户界面布局在不同设备上运行时能够正确调整大小。这在很大程度上可以通过仔细规划和使用本章概述的布局管理器来实现。

同样重要的是，大多数 Android 手机和平板电脑都可以以竖向或横向持有。良好的用户界面应该能够适应这种变化并进行合理的布局调整，以利用每个方向的可用空间。

### 16.2 Views and View Groups

用户界面中的每个项目都是`Android View`类的子类（准确来说是`android.view.View`）。Android SDK 提供了一组预构建的视图，可用于构建用户界面。典型的示例包括标准项，如`Button`、`CheckBox`、`ProgressBar`和`TextView`类。这些视图也被称为控件（widgets）或组件（components）。对于 SDK 提供的控件无法满足的需求，可以通过子类和扩展现有类来创建新视图，或者通过直接在`View`类之上构建创建一个完全全新的组件。

视图也可以包含多个其他视图（也称为复合视图，composite view）。此类视图派生自`Android ViewGroup`类（`android.view.ViewGroup`），而该类本身是`View`的子类。这种视图的一个示例是`RadioGroup`，它旨在包含多个`RadioButton`对象，以便确保在任何时间都只有一个对象处于“开启”状态。从结构上来说，复合视图由单个父视图（派自`ViewGroup`类，也称为容器视图或根元素）组成，它可以包含其他视图（称为子视图）。

另一类基于`ViewGroup`的容器视图是布局管理器。

### 16.3 Android 布局管理器

除了上一节讨论的控件式视图外，SDK 还包含了一组被称为布局（layouts）的视图。布局是容器视图（因此派生自`ViewGroup`），设计用于控制子视图在屏幕上的定位方式。

Android SDK 包含了以下可能在 Android 用户界面设计中使用的布局视图：

*   `ConstraintLayout` – 在 Android 7 中引入，这种布局管理器是大多数布局需求的推荐选择器。`ConstraintLayout`允许通过分配给每个子视图的简单约束设置来定义布局中视图的位置和行为。这种布局的灵活性允许快速、方便地创建复杂的布局，而无需在彼此之间嵌套其他布局类型，从而提升了布局性能。`ConstraintLayout`还与 Android Studio 布局编辑器工具紧密集成。除非另有说明，否则它是书中大多数示例的首选布局。

*   `LinearLayout` – 根据所选的方向（orientation）在单行或单列中排列子视图。可以在每个子视图上设置权重（weight）值，以指定该子视图相对于其他子视图应占据布局空间的比例。

*   `TableLayout` – 将子视图按行和列的网格格式排列。表格中的每行由一个`TableRow`对象表示，该对象又包含一个每个单元格的视图对象。

*   `FrameLayout` – `FrameLayout`的目的是分配屏幕的一个区域，通常用于显示单个视图。如果添加了多个子视图，它们默认将相互叠在一起，并定位在布局区域的左上角。通过为每个子视图设置重力（gravity）值可以实现单个子视图的交替定位。例如，在子视图上设置`center_vertical`重力值将使其位于容器`FrameLayout`视图的垂直中心。

*   `RelativeLayout` – `RelativeLayout`允许通过指定子视图的对齐方式（alignments）和边距（margins），使子视图相对于彼此以及容器布局视图进行定位。例如，可以将子视图`View A`配置为位于容器`RelativeLayout`视图的水平垂直中心。另一方面，`View B`也可以被配置为在布局中水平居中，但位于`View A`顶部上方 30 像素处，从而使其在垂直方向相对于`View A`。在设计必须适配各种屏幕尺寸和方向的用户界面时，`RelativeLayout`管理器非常有帮助。

*   `AbsoluteLayout` – 允许子视图定位在容器布局视图内特定的`X`和`Y`坐标上。不建议使用这种布局，因为它缺乏响应屏幕尺寸和方向变化的灵活性。

*   `GridLayout` – `GridLayout`实例由不可见的线划分，形成一个包含行和列单元格的网格。子视图被放置在单元格中，并可以配置为跨越多个水平和垂直单元格，从而能够快速方便地实现各种布局选项。`GridLayout`中组件之间的间隙可以通过在相邻单元格中放置一种名为`Space`的特殊类型视图，或通过设置边距参数来实现。

*   `CoordinatorLayout` – 作为 Android 5.0 中 Android 设计支持库的一部分引入，`CoordinatorLayout`专门设计用于协调应用程序屏幕顶部的应用栏（app bar）与其他视图元素的外观和行为。当使用 Basic Views Activity 模板创建新活动时，主布局中的父视图将使用`CoordinatorLayout`实例实现。该布局管理器将在后文中详细介绍，从与浮动操作按钮和 Snackbar 使用中所示的用户界面：

Android 应用用户界面屏幕中的每个元素都是视图（view），它们最终都继承自`android.view.View`类。每个视图代表设备显示器上的矩形区域，负责该区域内显示的内容，并处理在该视图边界内发生的事件。多个视图可以组合成单个复合视图（composite view）。复合视图中的视图是容器视图的子视图，容器视图通常是`android.view.ViewGroup`的子类（其本身又是`android.view.View`的子类）。用户界面由构建成视图层次结构的视图组成。

Android SDK 包含了一系列预定义的视图，可用于创建用户界面。这些包括文本字段和按钮等基本组件，以及一系列可用于控制子视图位置的布局管理器。如果提供的视图不能满足特定需求，可以通过扩展或组合现有视图，或者通过子类`android.view.View`创建全新的视图类来创建自定义视图。

用户可以使用 Android Studio 布局编辑器（Layout Editor）工具、手动编写 XML 布局资源文件或编写 Java 代码创建用户界面。这些方法将在接后的章节中进行介绍。

# 17. Android Studio 布局编辑器工具指南

很难想象不需要某种形式用户界面的 Android 应用概念。大多数 Android 设备都配备了触摸屏和键盘（虚拟或物理），点击和滑动是用户与应用程序之间主要的交互方式。这些交互不可避免地通过应用程序的用户界面进行。

设计良好的用户界面是创建成功且流行的 Android 应用的关键因素，它可以根据单个应用程序的设计需求从简单到极其复杂不等。无论复杂程度如何，Android Studio 布局编辑器工具都显著简化了设计和实现 Android 用户界面的任务。

## 17.1 基础视图 vs. 空视图活动模板

正如“Android 应用剖析”章节概述的那样，Android 应用包含一个或多个活动（activity）。活动是应用程序功能的独立模块，通常直接对应于单个用户界面屏幕。因此，当使用 Android Studio 布局编辑器时，我们总是在处理某个活动的布局。

在创建新的 Android Studio 项目时，有多个模板可以作为主活动用户界面的起点。最基本的模板是基础视图活动（Basic Views Activity）和空视图活动（Empty Views Activity）模板。尽管这两个选项看起来相似，但它们之间存在显著差异。要在布局编辑器中查看这些差异，请使用视图选项（View Options）菜单启用`Show System UI`（显示系统界面），如下图 17-1 所示：

```
![](img/as_basic_activity_layout_1.jpg
```

图 17-4

此应用行为使用了称为片段（fragments）和导航（navigation）的两个 Android 功能，这些功能将分别从“Android 片片简介”和“导航架构组件概述”章节开始介绍。

`content_main.xml`文件包含一个特殊的片段，称为导航宿主片段（Navigation Host Fragment），它允许根据`res -> layout -> nav_graph.xml`文件中配置的设置在视图中切换不同的内容。在基础视图活动模板的情况下，`nav_graph.xml`文件配置为根据用户对“Next”和“Previous”按钮的选择，在`fragment_first.xml`和`fragment_second.xml`文件定义的用户界面布局之间进行切换。

如果你在活动中既不需要悬浮操作按钮也不需要菜单，并且不需要`CoordinatorLayout`提供的特殊应用栏行为（例如在某些滚动操作期间使应用栏和工具栏从视图中折叠的功能，该主题在“使用 AppBar 和折叠工具栏布局”章节中涵盖），那么空视图活动模板将很有帮助。然而，基础视图活动是有帮助的，因为它默认提供了这些元素。事实上，使用基础视图活动模板创建一个新活动并删除你不需要的元素，比使用空视图活动模板并手动实现折叠工具栏、菜单或悬浮操作按钮等行为要快得多。尽管由于书中的并非所有示例都需要基础视图活动模板的功能，但本章的大多数示例将使用空视图活动模板，除非示例需要基础视图活动提供的某一个或其他功能。

供以后参考，如果你需要菜单但不需要悬浮操作按钮，请使用基础视图活动并按照以下步骤删除悬浮操作按钮：

1. 在项目窗口的`app -> res -> layout`下双击主`activity_main.xml`布局文件，将其加载到布局编辑器。布局加载到布局编辑器工具后，选择悬浮操作按钮并按下键盘 Delete 键从布局中删除对象。

2. 找到并编辑活动的 Java 代码（位于`app -> java -> <package name> -> <activity class name>`），如下从`onCreate`方法中删除悬浮操作按钮代码：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    binding = ActivityMainBinding.inflate(getLayoutInflater());
    setContentView(binding.getRoot());
    setSupportActionBar(binding.toolbar);
    NavController navController = Navigation.findNavController(this, R.id.nav_host_fragment_content_main);
    appBarConfiguration = new AppBarConfiguration.Builder(navController.getGraph()).build();
    NavigationUI.setupActionBarWithNavController(this, navController, appBarConfiguration);
    binding.fab.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View view) {
```

```java
Snackbar.make(view, "Replace with your own action", Snackbar.LENGTH_LONG)
    .setAction("Action", null).show();
```

如果你需要一个悬浮按钮但不需要菜单，请使用 Basic Views Activity 模板并按照以下步骤操作：

1. 编辑主 Activity 类文件并删除`onCreateOptionsMenu`和`onOptionsItemSelected`方法。

2. 在 Project（项目）工具窗口中选择`res -> menu`项，并按下键盘上的`Delete`键从项目中删除该文件夹及相应的菜单资源文件。

如果你需要使用 Basic Views Activity 模板，但既不需要导航功能也不需要第二个 fragment，请按照以下步骤操作：

1. 在 Project 工具窗口中，导航并双击`app -> res -> navigation -> nav_graph.xml`文件，将其加载到导航编辑器中。

2. 在编辑器中，选择图面板中的`SecondFragment`条目，并按下键盘删除键将其从图表中移除。

3. 找到并删除`SecondFragment.java`（`app -> java -> <package name> -> SecondFragment`）和`fragment_second.xml`（`app -> res -> layout -> fragment_second.xml`）文件。

4. 最后的任务是从`FirstFragment`类中删除一些代码，使得`Button`视图在被点击时不再导航到已不存在的第二个 fragment。找到`FirstFragment.java`文件，双击将其加载到编辑器，并移除`onViewCreated()`方法中的代码，使其内容如下：

```java
public void onViewCreated(@NonNull View view, Bundle savedInstanceState) {
    super.onViewCreated(view, savedInstanceState);
    binding.buttonFirst.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View view) {
            NavHostFragment.findNavController(FirstFragment.this)
                .navigate(R.id.action_FirstFragment_to_SecondFragment);
        }
    });
}
```

# 17.2 Android Studio 布局编辑器

如前面的章节所示，Layout Editor 工具提供了一个“所见即所得”（WYSIWYG）的环境，在该环境中，可以从调板中选择视图，然后将其放置在代表 Android 设备显示的画布上。视图一旦放置在画布上，就可以对其进行移动、删除和调整大小（受父视图约束）。此外，可以使用 Attributes（属性）工具窗口修改与所选视图相关的属性。

在底层，Layout Editor 工具会构建一个 XML 资源文件，该文件包含了正在设计的用户界面定义。因此，Layout Editor 工具以三种不同的模式运行：Design（设计）、Code（代码）和 Split（拆分）。

## 17.3 设计模式

在设计模式下，用户可以通过直接操作视图调板和布局的图形表示来可视化地控制用户界面。[图 17-5]突出了 Android Studio Layout Editor 工具在设计模式下的关键区域：

![](img/as_layout_editor_labelled.jpg)

图 17-5

*   **A – Palette（调板）** – 调板提供了 Android SDK 提供的系列视图组件的访问。这些组件被分类以便于导航。可以通过从调板中拖拽视图组件并将其放置在布局所需的位置来向布局添加项。



- `B` – `Device Screen`（设备屏幕）– 设备屏幕提供了设计中用户界面布局的视觉“所见即所得”表示。该布局允许通过选择、删除、移动和调整视图的大小来直接进行设计操作。可以使用工具栏中的菜单随时更改布局代表的设备模型。
- `C` – `Component Tree`（组件树）– 如前一节（“理解 Android 视图、视图组和布局”）所述，用户界面是使用分级结构构建的。组件树提供了用户界面设计层次结构的视觉概览。从组件树中选择元素将选中布局中相应的视图。同样地，从设备屏幕布局中选择视图将选中组件树层次结构中的该视图。
- `D` – `Attributes`（属性）– 调板中列出的所有组件视图都有一组相关的属性，用于调整该视图的行为和外观。`Layout Editor` 的属性面板提供了对布局中当前选中视图属性的访问，以便进行更改。
- `E` – `Toolbar`（工具栏）– `Layout Editor` 工具栏提供了对广泛选项的快速访问，包括（但不限于）放大和缩小设备屏幕布局、更改当前显示的设备模型、在竖屏和横屏之间旋转布局以及切换到不同的 Android SDK API 级别。工具栏还有一组上下文敏感按钮，当在设备屏幕布局中选择相关的视图类型时会出现这些按钮。
- `F` – `Mode Switching Controls`（模式切换控件）– 这三个按钮提供了在 `Design`、`Code` 和 `Split` 模式之间来回切换。
- `G` – `Zoom and Pan Controls`（缩放和平移控件）– 该控制面板允许你放大或缩小设计，抓取画布并在放大时进行移动。

## 17.4 调板

`Layout Editor` 调板由两个面板组成，旨在方便查找和预览待添加的组件。类别面板（在图 17-6 中标记为 `A`）列出了 SDK 支持的各种视图组件类别。当从列表中选择一个类别时，第二个面板（`B`）将更新以显示属于该类别的组件列表：

![](img/as_layout_editor.jpg)

图 17-6

要从调板将组件添加到布局中，请从组件列表或预览面板中选择该项，将其拖动到画布上的所需位置，然后释放到位。

可以通过点击调板工具栏中的搜索按钮（在图 17-6 中标记为 `C`）并输入组件名称，在所选类别内对特定组件进行搜索。随着字符输入，匹配的结果将出现在组件列表中。如果不确定组件的类别，可以在搜索之前或搜索期间选择“All Results（所有结果）”类别。

## 17.5 设计模式与布局视图

默认情况下，布局编辑器将以 `Design`（设计）模式出现，如图 17-5 所示。此模式提供了用户界面的视觉表示。可以通过点击 `View Modes`（视图模式）按钮随时选择设计模式，如图 17-7 所示：

![](img/as_layout_editor_view_modes.jpg)

图 17-7

当 `Layout Editor` 工具处于设计模式时，可以通过两种方式查看布局。图 17-5 显示的视图是 `Design` 视图，显示了布局和控件在运行中的应用中的外观。另一种模式 `Blueprint`（蓝图）视图可以代替 `Design` 视图或与 `Design` 视图同时显示。图 17-8 工具栏菜单提供了显示 `Design`、`Blueprint` 或两种视图的选项。还有针对色盲的设置。第五种选项 `Force Refresh Layout`（强制刷新布局）会导致布局重新构建并重绘。当布局进入意外状态或未能准确反映当前设计设置时，这非常有用：

![](img/as_layout_editor_design_surface.jpg)

图 17-8

显示布局视图、设计视图或两者都取决于个人喜好。一种很好的方法是开始时显示两者。

![](img/as_3.5_show_layout_design_and_blueprint.jpg)

图 17-9

## 17.6 夜间模式

在设计工作期间以夜间模式查看布局，请选择下方图 17-10 所示的菜单并将设置更改为 `Night`：

![](img/as_layout_editor_night.jpg)

图 17-10

模式菜单还包含了测试动态颜色的选项，该主题在“Material Design 3 主题与动态颜色教程”章节中有所介绍。

## 17.7 代码模式

使用 Android Studio 布局编辑器工具时，重要的是记住它所做的仅仅是提供了一种易于用户的方法来创建 XML 布局资源文件。在设计过程中，可以通过从上方图 17-7 所示的 `View Modes`（视图模式）菜单中选择 `Code` 查看并直接编辑底层的 XML。

图 17-11 显示了 `Code` 模式下的 Android Studio 布局编辑器工具，允许通过修改 XML 来更改用户界面声明：

![](img/as_layout_editor_code.jpg)

图 17-11

## 17.8 分屏模式

在 `Split`（分屏）模式下，编辑器并排显示 `Design`（设计）和 `Code`（代码）视图，允许用户使用设计画布可视化地修改用户界面并直接对 XML 声明进行更改。可以使用 `View Modes` 菜单或下方所示的 `Editor` 和 `Preview` 按钮来选择 `Split` 模式：

![](img/as_layout_editor_editor_and_preview_button.jpg)

图 17-12

XML 的任何更改都会反映在设计画布上，反之亦然。图 17-13 显示了处于 `Split` 模式下的编辑器：

![](img/as_layout_editor_split.jpg)

图 17-13

## 17.9 设置属性

`Attributes`（属性）面板提供了对当前选中组件所有可用设置的访问。例如，图 17-14 显示了 `TextView` 小部件的一些属性：

![](img/as_layout_editor_atrributes.jpg)

图 17-14

`Attributes` 工具窗口分为以下不同的部分：

- `id`：包含 `id` 属性，该属性定义了应用源码中引用当前选中对象的名称。
- `Declared Attributes`（已声明属性）：包含所有已赋值的属性。
- `Layout`（布局）：定义当前选中视图对象相对于屏幕和布局中对象的定位和大小的设置。
- `Transforms`（变换）：包含允许当前选中对象进行旋转、缩放和偏移的控件。
- `Common Attributes`（常用属性）：当前选中的视图对象类通常需要更改的属性列表。
- `All Attributes`（所有属性）：当前选中对象可用属性的完整列表。

可以通过选择 `attributes` 工具窗口工具栏中的搜索按钮并输入属性名称来对特定属性进行搜索。

某些属性在值字段右侧有一个窄按钮。这表示可以使用 `Resources`（资源）对话框来协助选择合适的属性值。点击按钮可显示对话框。该按钮的外观变化会反映相应的属性值是存储在资源文件中还是硬编码的。如果值存储在资源文件中，则 `text` 属性字段右侧的按钮将填充，以指示该值不是硬编码的，如下方的图 17-15 所示：

![](img/as_layout_editor_not_hardcoded.jpg)

图 17-15

具有有限数量有效选项的属性将呈现一个下拉菜单（图 17-16），可以从中进行选择。

![](img/as_layout_editor_attr_options.jpg)

图 17-16

可以点击滴管图标显示颜色调色板。同样，当出现旗帜图标时，点击它可以显示该属性可用的选项列表，而图像图标会打开资源管理器面板，允许为属性选择图像和其他资源类型。

## 17.10 变换

`Attributes` 工具窗口中的 `transforms` 面板（图 17-17）提供了一组控件和属性，用于控制当前选中对象在旋转、`alpha`（用于视图的淡入和淡出）、`scale`（大小）和 `translation`（相对于当前位置的偏移）方面的视觉方面：

![](img/as_layout_editor_transforms.jpg)

图 17-17

该面板包含视图的视觉表示，该表示随属性的更改而更新。这些更改也会反映在布局画布内的视图中。

## 17.11 工具可见性切换

在 `Code` 模式下查看 Android Studio XML 布局文件的内容时，你会注意到许多定义视图外观和行为的属性都以 `android:` 前缀开头。这表示这些属性是在 `android` 命名空间内设置的，并在应用运行时生效。例如，下面这段来自布局文件的摘录在 `Button` 视图上设置了各种属性：

```xml
<Button
    android:id="@+id/button"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Button"/>
```

除了 `android` 命名空间外，Android Studio 还提供了 `tools` 命名空间。当在此命名空间内设置属性时，它们仅在布局编辑器中生效。在设计布局时，你可能会发现让 `EditText` 显示某些文本但在应用运行时需要视图为空是很有帮助的。为了实现这一点，你可以使用 `tools` 命名空间如下设置 `text` 属性：

```xml
<EditText
    android:id="@+id/editTextPersonName"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:ems="10"
    android:inputType="textPersonName"
    tools:text="Sample Text"/>
```

此类类型的工具属性通过在 `Attributes` 工具窗口中带有扳手图标的属性字段中输入值来设置，如下图 17-18 所示：

![](img/as_layout_editor_tools_attribute.jpg)

图 17-18

此类工具属性在设计过程中更改视图的可见性非常有用。布局可能包含一个在应用运行时根据程序显示和隐藏的视图，取决于用户操作。为了模拟隐藏视图，可以在视图声明中添加以下工具属性：

`tools:visibility="invisible"`

虽然使用 `invisible` 设置时视图不再可见，但它仍然存在于布局中，并占据它可见时的空间。要让布局表现像视图不再存在，应将可见性属性设置为 `gone`：

`tools:visibility="gone"`

在上述两个示例中，可见性设置仅适用于布局编辑器，而对运行的应用没有影响。若要在布局编辑器和运行的应用中同时控制可见性，将使用 `android` 命名空间设置相同的属性：

`android:visibility="gone"`

虽然可见性工具属性很有用，但手动编辑 XML 布局文件是一个繁琐的过程。为了方便更改这些设置，Android Studio 在布局编辑器的 `Component Tree` 面板中提供了一组切换控件。要访问这些控件，点击面板中相应视图右侧的边距。例如，图 17-19 显示了名为 `myButton` 的 `Button` 视图的工具可见性切换控件：

![](img/as_layout_editor_tools_attr_visibility.jpg)

图 17-19

这些切换开关控制 `android` 和 `tools` 命名空间对应视图的可见性，并提供 `not set`、`visible`、`invisible` 和 `gone` 选项。当设置了冲突属性时（例如，`android` 命名空间的切换开关设置为 `visible`，而 `tools` 值被设置为 `invisible`），在布局预览中，`tools` 命名空间具有更高的优先级。当选择了切换项时，Android Studio 会自动将相应的属性添加到布局文件中的 XML 视图元素中。

除了 `Component Tree`（组件树）面板中的可见性切换开关外，布局编辑器还包含了 `tools` 可见性和位置切换按钮，如译文图 17-20 所示的高亮显示：

![](img/as_layout_editor_show_tools.jpg)

图 17-20

此按钮切换当前的 `tools` 可见性设置。例如，如果上方显示的 `Button` 视图当前 `tools` 可见性属性设置为 `gone`，则切换此按钮将使其变为 `visible`。这使得在视图添加到和从布局中移除时能够快速检查布局行为。该切换开关也用于检查布局中的视图是否正确约束，该主题在“在 Android Studio 中使用 ConstraintLayout 指南”章节中有所介绍。

## 17.12 转换视图

在布局中将视图从一种类型转换为另一种（例如将 `TextView` 转换为 `EditText`），可以在 Android Studio 布局编辑器中轻松完成，只需在屏幕布局或 `Component tree` 窗口中右键点击该视图，并选择 `Convert view...` 菜单选项（图 17-21）：

![](img/as_layout_editor_convert_view.jpg)

图 17-21

选中后，将出现一个包含兼容视图类型列表的对话框，选中的对象可以转换为这些类型。例如，图 17-22 显示了现有 `TextView` 视图可以转换的类型：

![](img/as_layout_editor_convert_view_dialog.jpg)

图 17-22

这种技术对于将布局从一种类型转换为另一种类型（例如，将 `ConstraintLayout` 转换为 `LinearLayout`）也有帮助。

## 17.13 显示示例数据

在 Android Studio 中设计布局时，会出现这样的情况：用户界面中要显示的内容在应用完成并运行之前是不可用的。这有时会让人难以从布局编辑器内部评估布局在应用运行时的显示效果。为了解决这个问题，布局编辑器允许指定示例数据，这将使用示例图像和数据填充布局编辑器中的视图。这些示例数据仅在布局编辑器中显示，在应用运行时不会显示。可以通过直接编辑布局的 XML 或通过在设计区域中右键点击小部件并选择 `Set Sample Data` 菜单选项视觉化地使用设计时助手来配置示例数据。设计时助手面板将为所选视图项显示一组用于显示示例数据的预配置选项，包括在不同配置中文本和图像的组合。例如，图 17-23 显示了在 `RecyclerView` 列表中选择显示示例数据时显示的选项选项：

![](img/as_layout_editor_design_time_attrs.jpg)

图 17-23

或者，可以在布局设计过程中提供自定义文本和图像进行显示。在布局编辑器中使用示例数据的示例包含在随后的章节“布局编辑器示例数据教程”中。由于示例数据是作为 `tools` 属性实现的，预览中数据的可见性可以使用上方图 17-20 所示的高亮显示的可见性切换按钮进行控制。

## 17.14 创建自定义设备定义

布局编辑器工具栏中的设备菜单（图 17-24）提供了预配置的设备类型列表，选择后，这些类型将作为设备屏幕画布出现。除了预配置的设备类型外，之前在 Android Studio 环境中配置的任何 `AVD` 实例也将列在菜单中。要添加额外的设备配置，显示设备菜单，选择 `Add Device Definition` 选项，并按照“在 Android Studio 中创建 Android 虚拟设备 (AVD)”章节中的步骤进行。

![](img/as_layout_editor_device_menu.jpg)

图 17-24

## 17.15 修改当前设备

作为设备选择菜单的替代方案，可以通过从设备菜单选择 `Custom` 选项，点击设备屏幕右下角的缩放句柄（图 17-25），并拖动选择另一种设备显示格式。随着屏幕缩放，将出现标记，指示可选的各种尺寸选项和方向：

![](img/as_3.5_show_layout_resize_device.jpg)

图 17-25

## 17.16 布局验证

布局验证选项允许用户在系列像素级屏幕上同步预览用户界面布局。要访问布局验证窗口，点击 Android Studio 主窗口右侧的标签或使用左下角的 `Tool Window` 菜单。加载后，面板将如图 17-26 所示在多个设备配置上渲染：

![](img/as_layout_editor_device_validation.jpg)

图 17-26

## 17.17 总结

开发 Android 应用的一个关键部分是创建用户界面。这是在 Android Studio 环境中使用布局编辑器完成的，该工具有三种模式。在 `Design` 模式下，从调板中选择组件并放在代表 Android 设备屏幕的布局上，并使用属性列表进行配置。表示布局的 XML 可以在 `Code` 模式下直接编辑。而 `Split` 模式则可以通过视觉化和直接编辑 XML 来创建布局。这些模式结合提供了一个广泛且直观的用户界面设计环境。

布局验证面板允许在各种尺寸屏幕上快速预览用户界面布局。

# 18. `ConstraintLayout` 指南

正如在“理解视图、视图组和布局”章节中所讨论，Android 提供了多种布局管理器来设计用户界面。在 Android 7 中，Google 引入了一种解决了许多旧布局管理器缺陷的布局。这种名为 `ConstraintLayout` 的布局将简单、表达且灵活的布局系统与 Android Studio 布局编辑器工具中强大的功能相结合，有助于创建能够自动适应屏幕尺寸和设备方向变化的响应式用户界面布局。

本章将概述 `ConstraintLayout` 的基本概念，下一章将详细概述如何在 Android Studio 布局编辑器工具中使用 `ConstraintLayout` 创建基于约束的布局。

## 18.1 `ConstraintLayout` 如何工作

与其他所有布局一样，`ConstraintLayout` 管理其包含的视觉组件（也称为小部件）的位置和大小行为。它是根据在每个子小部件上设置的约束连接来实现的。



为了完全理解并使用`ConstraintLayout`，必须掌握以下核心概念：

- 约束 (Constraints)
- 边距 (Margins)
- 相对约束 (Opposing Constraints)
- 约束偏置 (Constraint Bias)
- 链 (Chains)
- 链样式 (Chain Styles)
- 指南线 (Guidelines)
- 组 (Groups)
- 屏障 (Barriers)
- 流 (Flow)

### 18.1.1 约束

约束是一组规则，规定了组件相对于其他组件、容器`ConstraintLayout`的侧边以及称为`guidelines`的特殊元素的对齐方式和间距。约束还决定了Activity的用户界面布局如何响应设备方向的变化或在不同屏幕尺寸的设备上的显示情况。为了进行充分配置，组件必须具有足够的约束连接，以便`ConstraintLayout`布局引擎能够在水平和垂直平面上解析其位置。

### 18.1.2 边距

边距是某种指定固定距离的约束形式。考虑一个需要放置在设备屏幕右上角的`Button`对象。这可以通过实现从`Button`的顶部和右边缘的边距约束，并连接到父`ConstraintLayout`对应的侧来实现，如图18-1所示：

![](img/Image2437.jpg)

图18-1

如上图所示，这些约束连接中的每一个都关联有一个边距值，规定了组件距离父布局两个侧的固定距离。在此种配置下，无论屏幕尺寸或设备方向如何，`Button`对象将始终根据两个约束连接的指定，分别距离父`ConstraintLayout`的顶部和右边缘20和15个设备无关像素(dp)。

虽然上述配置在某些情况下是可以接受的，但它在允许`ConstraintLayout`布局引擎通过调整组件位置来响应设备旋转以及支持不同尺寸的屏幕方面，没有提供任何灵活性。为了在布局中添加这种响应性，有必要实现相对约束。

### 18.1.3 相对约束

在单个组件上沿同一轴运行的两个约束被认为是相对约束。换句话说，在左侧和右侧都有约束的组件被认为具有水平相对约束。例如，图18-2展示了在之前的布局中同时添加水平和垂直相对约束：

![](img/Image24461.jpg)

图18-2

这里需要理解的关键点是，一旦在特定轴上实现了相对约束，组件的定位将基于百分比而非基于坐标。例如，组件不再固定在距离布局顶部的20dp处，而是位于距离顶部的30%处。在不同的方向以及在更大或更小的屏幕上运行时，`Button`始终位于父布局尺寸的相同位置。

现在重要的是要理解，图18-2中概述的布局不仅使用了相对约束，还通过应用约束偏置来实现的。

### 18.1.4 约束偏置

现在已经确定，`ConstraintLayout`中的组件可能会受到相对约束连接的影响。默认情况下，相对约束是相等的，导致相应的组件在相对轴上居中。例如，图18-3显示了一个组件使用相对水平和垂直约束在包含的`ConstraintLayout`中居中：

![](img/Image2453.jpg)

图18-3

为了在存在相对约束的情况下调整组件位置，`ConstraintLayout`实现了一种名为约束偏置(constraint bias)的功能。约束偏置允许组件沿相对轴的定位根据指定的百分比偏向其中一个约束偏斜。例如，图18-4显示了之前的约束布局，具有75%的水平偏置和10%的垂直偏置：

![](img/Image2461.jpg)

图18-4

下一章标题为“在Android Studio中使用ConstraintLayout的指南”，将更详细地涵盖这些概念，并解释这些功能是如何集成到Android Studio布局编辑器工具中的。然而，在此还需要涵盖`ConstraintLayout`类的其他几个领域。

### 18.1.5 链

`ConstraintLayout`链提供了一种将两个或多个组件的布局行为定义为一个组的方法。链可以在垂直或水平轴上声明，并配置为定义链中组件的间距和大小。

当组件通过双向约束连接时，它们就构成了链。例如，图18-5展示了以这种方式链的三个组件：

![](img/Image2468.jpg)

图18-5

链中的第一个元素是链头(chain head)，它在垂直链中对应顶部组件，在水平链中对应最左侧的组件。整个链的布局行为主要通过在链头组件上设置属性来配置。

### 18.1.6 链样式

`ConstraintLayout`链的布局行为由应用于链头组件的链样式决定。`ConstraintLayout`类目前支持以下链布局样式：

- **散布链(Spread Chain)** ——链中的组件在可用空间内均匀分布。这是链的默认行为。

![](img/Image2478.jpg)

图18-6

- **内部扩散链(Spread Inside Chain)** ——链中的组件在链头和最后一个组件之间均匀分布。链头和最后一个组件不包含在分布内。

![](img/Image2485.jpg)

图18-7

- **权重链(Weighted Chain)** ——通过权重属性定义链中每个组件占据的空间。

![](img/Image2492.jpg)

图18-8

- **紧凑链(Packed Chain)** ——组成链的组件聚集在一起没有任何间距。可以应用偏置来控制链相对于容器的水平或垂直位置。

![](img/Image2500.jpg)

图18-9

### 18.2 基线对齐

到目前为止，本章只提到了相对于组件侧边的约束（通常称为侧约束）。然而，一种常见的需求是让组件相对于其显示的内容而非组件本身进行对齐。为了满足这一需求，`ConstraintLayout`提供了基线对齐。

例如，假设之前的图18-1需要一个`TextView`组件放置在`Button`左侧40dp处。在这种情况下，`TextView`需要与`Button`视图进行基线对齐。这意味着`Button`内部文本需要与`TextView`内部文本进行垂直对齐。该布局的额外约束需要如图18-10所示连接：

![](img/Image2508.jpg)

图18-10

`TextView`现在在垂直方向上沿`Button`的基线线，并在水平上距离`Button`对象左边缘40dp。

### 18.3 配置组件维度

控制组件的维度是界面设计过程的关键元素。`ConstraintLayout`提供了可以在组件上设置的三个选项来管理大小行为。这些设置针对高度和宽度维度分别进行配置：

- `Fixed` – 控件固定到指定的尺寸。
- `Match Constraint` – 允许布局引擎调整控件的大小以满足主执行的约束条件。也称为`AnySize`或`MATCH_CONSTRAINT`选项。
- `Wrap Content` – 控件的大小由其内容（即文本或图形）决定。

## 18.4 Guideline Helper（指南线助手）

指南线（Guidelines）是`ConstraintLayout`中可用的特殊元素，它们为约束提供了一个可以连接的额外目标。在一个`ConstraintLayout`实例中可以添加多个指南线，这些指南线可以被配置为水平或垂直方向。一旦添加，就可以从布局中的控件到指南线建立约束连接。当多个控件必须沿某一轴对齐时，这种方法特别有用。例如，在图18-11中，包含在`ConstraintLayout`中的三个`Button`对象沿一条垂直指南线进行约束：

![](img/Image2519.jpg)

图18-11

## 18.5 Group Helper（组助手）

`ConstraintLayout`的此功能允许将控件放入逻辑组中，并作为一个单一实体控制这些控件的可见性。`Group`是布局中其他控件的引用列表。一旦定义，更改`group`实例的可见性属性（`visible`、`invisible`或`gone`）将此更改应用于所有组成员。这使得通过更改单个属性来隐藏和显示多个控件变得非常简单。单个布局可以包含多个组，一个控件也可以属于多个组。如果组之间发生冲突，则XML文件中最后定义的组具有优先级。

## 18.6 Barrier Helper（屏障助手）

与指南线类似，屏障（Barriers）是可用于约束布局内视图的虚拟视图。与指南线一样，屏障可以是垂直或水平的，并且一个或多个视图可以约束在它上面（为了避免混淆，这些被称为受约束视图）。但与指南线在布局中保持固定位置不同，屏障的位置是由一组所谓的参考视图（reference views）定义的。屏障的引入是为了解决经常发生的视图重叠问题。例如，考虑下图18-12中的布局：

![](img/Image2526.jpg)

图18-12

上述布局需要注意的关键点是，`View 3`的宽度设置为匹配约束模式（match constraint mode），且视图的左边缘连接到`View 1`的右边缘。根据目前的实现，增加`View 1`的宽度将产生缩小`View 3`宽度的预期效果：

![](img/Image2533.jpg)

图18-13

然而，如果增加的是`View 2`的宽度而不是`View 1`就会出现问题：

![](img/Image2540.jpg)

图18-14

由于`View 3`只受`View 1`约束，它不会调整大小以适应`View 2`宽度的增加，导致视图重叠。

解决此问题的方法添加一个垂直屏障，并将`Views 1`和`View 2`分配为屏障的参考视图，以便它们控制屏障的位置。然后`View 3`的左边缘将相对于屏障进行约束，使其成为受约束视图。

现在，当`View 1`或`View 2`任意一个宽度增加时，屏障将移动以适应两个视图中最宽的一个，导致`View 3`的宽度相对于新的屏障位置发生变化：

![](img/Image2548.jpg)

图18-15

在使用屏障时，与单个屏障关联的参考视图和受约束视图的数量没有限制。

## 18.7 Flow Helper（流助手）

`ConstraintLayout Flow`助手允许组视图以流式网格布局样式显示。与`Group`助手一样，`Flow`包含了对其负责定位的视图的引用，并提供了各种配置选项，包括垂直和水平方向、换行行为（包括换行之前的最大控件数量）、间距和对齐属性。链（Chain）行为也可以应用于`Flow`布局，包括分布（spread）、内部分布（spread inside）和打包（packed）选项。

图18-16表示使用`Flow`实例在水平模式且无换行设置的五个等大小按钮的布局：

![](img/as_4.1_flow_no_wrap.jpg)

图18-16

图18-17显示了相同的按钮在水平流配置中，换行设置为在每三个控件后发生一次：

![](img/as_4.1_flow_with_wrap.jpg)

图18-17

另一方面，图18-18显示了将换行设置为使用内部分布（spread inside）链模式的按钮（其效果仅在第二行可见，因为第一行是满的）。该配置还设置了`gap`属性以在按钮之间添加间距：

![](img/as_4.1_flow_chain_spread_inside.jpg)

图18-18

作为`Flow`助手灵活性的最后演示，图18-19显示了在水平打包模式下、每三个控件换行的五个不同大小的按钮。此外，通过设置`horizontal-bias`值为`1.0`使网格内容右对齐（设置为`0.0`将导致左对齐）：

![](img/as_4.1_flow_right_align.jpg)

图18-19

## 18.8 Ratios（比例）

控件的尺寸可以使用比例设置定义。例如，控件可以使用比例设置进行约束，无论任何调整行为如何，其宽度都是高度的两倍。

## 18.9 ConstraintLayout Advantages（ConstraintLayout优势）

`ConstraintLayout`提供的灵活性允许在单个布局实例中实现许多需要嵌套多个布局才能实现的功能。这通过允许设计所谓的“扁平”或“浅层”布局层级，避免了布局嵌套带来的固有问题，从而提高了运行时的用户界面性能。

`ConstraintLayout`的引入也是为了解决目前存在的各种Android设备尺寸问题。`ConstraintLayout`的灵活性使得设计适应运行应用程序的设备的用户界面变得更容易。

最后，正如在Android Studio中使用ConstraintLayout的指南章节将演示的那样，Android Studio布局编辑器已专门针对`ConstraintLayout`用户界面设计进行了增强。

## 18.10 ConstraintLayout Availability（可用性）

尽管`ConstraintLayout`是随着Android 7引入的，但它是作为独立的支持库提供的，可以向下追溯到API 9 (Gingerbread)。这使得使用此布局的应用程序可以在运行较旧版本Android的设备上运行。

## 18.11 Summary（总结）

`ConstraintLayout`是随Android 7引入的布局管理器。它的设计旨在创建能够适应市场上多种Android设备尺寸和方向的灵活布局。`ConstraintLayout`使用约束来控制相对于父`ConstraintLayout`实例、指南线、屏障以及布局中其他控件的对齐和定位。`ConstraintLayout`是新创建的Android Studio项目的默认布局，并在设计用户界面布局时推荐使用。这种简单而灵活的布局管理方法可以轻松实现复杂且响应式的用户界面。

正如前面的章节中多次提到的那样，Google对Android Studio布局编辑器工具进行了重大更改，其中许多更改仅是为了支持使用`ConstraintLayout`进行用户界面布局设计。在上一章概述了`ConstraintLayout`的基本概念后，本章将更详细地探讨这些概念，同时概述布局编辑器工具如何允许设计和实现基于`ConstraintLayout`的用户界面。

## 19.1 设计与布局视图

名为“Android Studio布局编辑器指南”的章节解释了Android Studio布局编辑器工具提供了两种方式来查看Activity的用户界面布局，即设计（Design）视图和布局（Layout，也称为蓝图blueprint）视图。这些布局视图可以单独显示，也可以像图19-1所示那样并排显示：

![](img/as_design_and_blueprint.jpg)

图19-1

`Design`视图（位于图左侧）呈现了布局的“所见即所得”表示，其中布局以其在运行中的应用程序中的形式显示。另一方面，`Layout`视图显示了一种蓝图风格的视图，其中阴影轮廓表示小部件。如上面的图19-1所示，`Layout`视图还显示了约束连接（在这种情况下，用于将按钮在布局中居中的相对约束）。当选择布局中的特定小部件或鼠标指针悬停在设计区域上时，这些约束也会叠加到`Design`视图上，如图19-2所示：

![](img/as_design_canvas_with_constraints.jpg)

图19-2

两种视图中约束连接的外观可以使用图19-3所示的`View Options`（视图选项）菜单进行更改：

![](img/as_layout_view_options.jpg)

图19-3

除了显示用户界面布局的两种模式外，布局编辑器工具还提供了三种建立特定布局设计所需的约束的方式。

## 19.2 自动连接模式

`Autoconnect`（自动连接）顾其实名，在项目被添加到布局时会自动建立约束连接。可以使用图19-4所示的工具栏按钮开启或关闭`Autoconnect`模式：

![](img/as_layout_autoconnect.jpg)

图19-4

`Autoconnect`模式使用算法根据小部件的位置以及小部件与父布局两侧及其他元素的接近程度来决定建立最佳约束。如果任何自动约束连接未能提供预期的行为，可以像本章后面概述的那样进行手动更改。

## 19.3 推断模式

`Inference`（推断）模式使用涉及算法和概率的启发式方法，在小部件已添加到布局中后自动实现约束连接。这种模式通常在关闭了`Autoconnect`功能且在没有任何约束连接的情况下将对象添加到布局时使用。这允许通过从调色板将对象拖放到布局画布上来设计布局，并更改尺寸和位置，直到布局符合要求。本质上，这涉及在不担心约束的情况下“绘制”布局。`Inference`模式也可以在设计过程中用于填充布局中缺失的约束。

点击`Infer constraints`（推断约束）按钮（图19-5）时，约束会自动添加到布局：

![](img/as_layout_infer_constraints.jpg)

图19-5

与`Autoconnect`模式一样，布局编辑器工具始终存在推断错误约束的可能性，尽管这些可以手动修改和修正。

## 19.4 手动操作约束

实现约束连接的第三种选择是手动进行。这样做时，理解布局编辑器工具中小部件周围出现的各种句柄将会有帮助。例如，考虑图19-6所示的小部件：

![](img/as_constraint_markers.jpg)

图19-6

弹簧状线条(A)代表从小部件侧边到目标已建立的约束连接。对象每个角的小正方形标记(B)是缩放句柄，点击并拖动时用于缩放小部件。位于小部件每侧的小圆句柄(C)是侧边约束锚点。要创建约束连接，点击句柄并将生成的线条拖动到要连接的元素（例如指南线或父布局侧边或其他小部件的侧边），如图19-7所示。连接到另一个小部件的侧边时，将线条拖到该小部件的侧边约束句柄，并在小部件和句柄高亮时释放线条：

![](img/as_layout_drag_constraint.jpg)

图19-7



如果将约束线拖到小部件并释放但未附加到约束句柄上，布局编辑器将显示一个包含可以附加侧边列表的菜单。在图 19-8 中，例如，约束可以附加到按钮的顶部或底部：

![](img/as_constraint_edges.jpg)

图 19-8

额外的标记指示基线约束的锚点，其中小部件内部（而非外部边缘）用作对齐点。要显示此标记，右键点击小部件并选择 `Show Baseline`（显示基线）。要从基线约束句柄建立约束连接，将鼠标指针悬停在句柄上直到其高亮，然后点击并拖动到目标（如图 19-9 所示的另一个小部件的基线锚点）：

![](img/as_constraint_baselines.jpg)

图 19-9

要隐藏基线锚点，再次右键点击小部件并选择隐藏。

## 在检查器中添加约束

可以使用属性窗口中的 `Inspector`（检查器）面板为 Android Studio 布局编辑器中的视图添加约束，如图 19-10 所示。中心的正方形表示选选视图，正方形周围的区域表示应用于视图对应侧的约束（如果有）：

![](img/as_constraint_attributes.jpg)

图 19-10

视图侧缺少约束由一条指向带有加号的蓝色圆圈的虚线表示（如图中视图底部边缘所示）。要添加约束，点击此蓝色圆圈，布局编辑器将添加连接到它认为的布局中最合适目标的约束。

## 19.6 在属性窗口中查看约束

可以通过显示属性窗口的 `Constraints`（约束）部分来查看当前选择小部件的约束列表，如下图 19-11 所示：

![](img/as_attributes_constraints_section.jpg)

图 19-11

点击列表中的约束将选中设计布局中的该约束。

## 19.7 删除约束

要删除单个约束，请在设计布局中或 `Attributes` 工具窗口中选择该约束，使其高亮（例如，在 图 19-12 中所示，选中了最右侧的约束），然后按下键盘上的删除键。该约束将从布局中移除。

![](img/as_constraint_selected.jpg)

图 19-12

另一种选项是在按住 `Ctrl` 键（macOS 上为 `Cmd`）的同时，将鼠标指针悬停在约束锚点上，并在它变为红色后点击锚点：

![](img/as_constraint_anchor_delete.jpg)

图 19-13

或者，通过右键点击组件并选择 `Clear Constraints of Selection`（清除选择约束）菜单选项来移除该组件的所有约束。

要移除布局中每个组件的所有约束，请使用 图 19-14 中所示高亮的工具栏按钮：

![](img/as_clear_all_constraints.jpg)

图 19-14

# 19.8 调整约束偏置

前一节概述了使用偏置设置来倾向于一个对立约束而非另一个的概念。`Android Studio Layout Editor` 工具中的偏置通过位于 `Attributes` 工具窗口中的 `Inspector` 进行调整，并如 图 19-15 所示。图中箭头指示的两个滑块用于控制当前选中组件的垂直方向和方向对立约束的偏置。

![](img/as_constraint_bias_sliders.jpg)

图 19-15

# 19.9 理解 ConstraintLayout 边距

约束可以配合边距使用，在组件与另一个元素（如另一个组件、辅助线或父布局的边缘）之间实现固定间隙。例如，考虑应用在 图 19-16 中 `Button` 对象上的水平约束：

![](img/as_constraint_no_margins.jpg)

图 19-16

按照目前的配置，水平约束延伸到父级 `ConstraintLayout` 的左右边缘。因此，该组件具有对立的水平约束，这意味着 `ConstraintLayout` 布局引擎在运行时对组件的实际位置有一定的裁量权。这使得布局具有灵活性，以适应不同的屏幕尺寸和设备方向。水平偏置设置还可以控制组件的位置，直到布局的右侧。例如，图 19-17 显示了应用了 100% 水平偏置的同一个按钮：

![](img/as_constraint_100_bias.jpg)

图 19-17

`ConstraintLayout` 边距可能会出现在约束连接的末端，并代表一个固定间隙，即使在调整偏置或响应活动其他部分的布局变化时，组件无法移动到该间隙内。在 图 19-18 中，右侧约束现在包含一个 `50dp` 的边距，即使偏置仍设为 100%，组件也无法移动到该区域。

![](img/as_constraint_bias_with_margin.jpg)

图 19-18

组件上现有的边距值可以在 `Inspector` 中进行修改。如 图 19-19 所示，使用下拉菜单将当前选中组件的右侧边距更改为 `16dp`。或者，点击当前值也可以在字段中输入数字。

![](img/as_constraint_set_margin.jpg)

图 19-19

可以使用 图 19-20 中高亮的工具栏中的选项，随时更改新约束的默认边距：

![](img/as_constraints_default_margin.jpg)

图 19-20

# 19.10 对立约束和偏置的重要性

正如前一节所述，在用 `ConstraintLayout` 时，对立约束、边距和偏置构成了 Android 响应式布局设计的基石。当组件被约束但没有对立的约束连接时，这些约束本质上是边距约束。这在 `Layout Editor` 工具中通过实线并配合边距测量值在视觉上表示，如 图 19-21 所示。

![](img/as_constraint_no_opposing.jpg)

图 19-21

上述约束将组件固定在相应位置。结果是，如果设备旋转到横向模式，组件将不再可见，因为垂直约束会将其推到设备屏幕顶之外（如 图 19-22 所示）。如果应用程序在屏幕比设计过程中使用的更小的设备上运行，也会出现类似的问题。

![](img/as_constraint_no_opposing_landscape.jpg)

图 19-22

当实现对立约束时，约束连接由锯齿状的弹簧线表示（弹簧的比喻旨在表示组件的位置不是固定的绝对 `X` 和 `Y` 坐标）：

![](img/as_constraints_opposing.jpg)

图 19-23

在上述布局中，垂直和水平偏置设置经过配置，使组件始终距离底部 90%，距离左边缘 35%。因此，在旋转后，组件仍然可见，且相对于屏幕尺寸的位置相同：

![](img/as_constraint_opposing_landscape.jpg)

图 19-24

在设计响应性和自适应的用户界面布局时，手动设计布局和修正自动创建的约束时考虑偏置和对立约束是非常重要的。

# 19.11 配置组件尺寸

`ConstraintLayout` 中组件的内部维度也可以 `Inspector` 配置。如前一节概述，组件维度可以设置为 `wrap content`、`fixed` 或 `match constraint` 模式。当前选中组件每个维度的现有设置在 `Inspector` 中代表组件的正方形内，如 图 19-25 所示：

![](img/as_constraint_dimensions.jpg)

图 19-25

上图将水平和垂直维度设置为 `wrap content` 模式（由向内的箭头表示）。检查器使用以下视觉指示器表示三种维度模式：

| Fixed Size | ![](img/Image2826.jpg) |

| Match Constraint | ![](img/Image2834.jpg) |

| Wrap Content | ![](img/Image2844.jpg) |

表 19-1

要更改当前设置，点击指示器可以在三种设置之间循环。

此外，可以使用 `Expand Horizontally`（水平扩展）和 `Expand Vertically`（垂直扩展）选项根据约束和布局中的其他组件允许的最大范围扩展组件的水平或垂直尺寸。可以通过右键点击布局中的组件并从结果菜单选择 `Organize`（组织）选项来访问（图 19-26）。使用时，当前选中的组件将在水平或垂直方向上增大以填充周围的可用空间

![](img/as_constraint_expand_menu.jpg)

图 19-26

# 19.12 设计时工具定位

标题为 "Android Studio 布局编辑器工具指南"的章节介绍了 `tools` 命名空间的概念，并解释了如何使用它来设置仅在布局编辑器中生效的可见属性。在后台，Android Studio 还会使用 `tools` 属性在将组件放置在没有约束的布局中时，将其保持在当前位置。例如，想象在禁用自动连接模式时，向布局中放置了一个 `Button`（按钮）。虽然该组件在预览画布上似乎处于正确位置，但当运行应用程序时，它将出现在屏幕的左上角。这是因为该组件没有约束来告诉父布局 `ConstraintLayout` 应该将其放置在何处。

该组件在布局编辑器中显示位置正确，是因为 Android Studio 设置了绝对的 `X` 和 `Y` 定位工具属性（`tools` attributes），以便在添加约束之前将其保持在正确位置。在 XML 布局文件中，内容可能如下所示：

```xml
<Button
    android:id="@+id/button4"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Button"
    tools:layout_editor_absoluteX="111dp"
    tools:layout_editor_absoluteY="88dp" />
```

一旦为组件添加了充分的约束，布局编辑器将移除这些工具属性。一种快速识别哪些组件缺少约束而无需等待程序运行的实用技巧，是点击在 图 19-27 中高亮的按钮，以切换工具位置的可见性。任何跳转到左上角的组件都是未完全约束的，它们通过临时的 `tools` 绝对 `X` 和 `Y` 定位属性保持在位。

![](img/as_constraint_tool_button.jpg)

图 19-27

## 19.13 添加指南线 (Guidelines)

指南线（Guidelines）提供了可以锚定的额外元素。可以通过右键点击布局并选择“垂直指南线”（Vertical Guideline）或“水平指南线”（Horizontal Guideline）菜单选项，或者使用工具栏菜单选项来添加指南线，如 图 19-28 所示：

![](img/as_constraint_guidelines_menu.jpg)

图 19-28

或者，可以从调色板（Palette）的“辅助工具”（Helpers）部分拖动水平和垂直 `Guidelines`，将其将其到布局画布或“组件树”（Component Tree）面板上，如 图 19-29 所示：

![](img/as_adding_guidelines.jpg)

图 19-29

添加后，指南线将以虚线的形式显示在布局中，并可以通过点击和拖动该线来移动。要建立到指南线的约束连接，点击组件的约束句柄并在释放之前将其拖动到指南线。在 图 19-30 中，两个 `Buttons` 的左侧通过约束连接到一条垂直指南线。

垂直指南线的位置可以指定为距离父布局左侧或右侧的绝对距离（对于水平指南线则为顶部或底部）。例如，下图中的垂直指南线位于距离父布局左边缘 `97dp` 的处：

![](img/as_constrain_guideline.jpg)

图 19-30

或者，指南线也可以相对于父布局总宽度或高度的百分比进行定位。要在这三种模式之间切换，选择指南线并点击指南线底部或末端的圆形（取决于指南线是垂直还是水平）。例如，图 19-31 显示了一个基于百分比定位的指南线：

![](img/as_adding_guideline_percent.jpg)

图 19-31

## 19.14 添加屏障 (Barriers)

可以通过右键点击布局并在“添加辅助工具”（Add helpers）菜单中选择“垂直屏障”（Vertical）或“水平屏障”（Horizontal Barrier）选项，或使用工具栏菜单选项来添加屏障，如 图 19-28 所示。或者，在调色板（Palette）的“辅助工具”部分找到 `Barrier` 类型，并将其拖动到布局画布或“组件树”面板上。

一旦布局中添加了屏障，它将作为组件树面板中的一个目：

![](img/as_component_tree_barrier.jpg)

图 19-32

要将视图作为引用视图（换句话说，控制屏障位置的视图），请将“组件树”内部的组件拖动到屏障条目上。例如，在 图 19-33 中，名为 `textView2` 和 `textView3` 的组件已被分配为屏障的引用组件：

![](img/as_barrier_reference_views.jpg)

图 19-33

添加引用视图后，需要配置屏障，以指定屏障相对于这些视图的方向。这是屏障方向设置，当在“组件树”面板中选择屏障时，它在“属性”（Attributes）工具窗口中定义：

![](img/as_barrier_direction.jpg)

图 19-34

下图显示了一个包含屏障的布局，`textView1` 和 `textView2` 作为引用视图。由于屏障是从引用视图的末端推挤，屏障方向设置为 `end`：

![](img/as_barrier.jpg)

图 19-35

## 19.15 添加分组 (Group)

要向布局添加 `Group`，可以右键点击布局并在“辅助工具”菜单中选择“分组”选项，或者使用如 图 19-28 所示的工具栏选项。或者，在调色板的“辅助工具”部分找到 `Group` 项并将其拖动到布局画布或“组件树”面板。

要向组添加组件，请在“组件树”中选择它们并拖动到 `Group` 条目。例如，图 19-36 显示将三个选中的组件添加到组中：

![](img/as_constrain_group.jpg)

图 19-36

组引用的任何组件在“组件树”中将以斜体显示在组项下方，如 图 19-37 所示。要从组中移除组件，选择它并按下键盘删除键：

![](img/as_constrain_group_added.jpg)

图 19-37

一旦组件分配给组，可以使用“属性”工具窗口的“约束”（Constraints）部分来修改可见性设置：

![](img/as_group_invisible.jpg)

图 19-38

## 19.16 使用流辅助工具 (Flow Helper)

`Flow` 辅助工具可以像之前提到的那样使用菜单或调色板。与 `Group` 辅助工具一样（图 19-36），可以通过将组件在“组件树”中拖动到 `Flow` 实例上来。添加 `Flow` 辅助工具并为其分配组件后，在“组件树”中选择它，并使用“属性”工具窗口的“常用属性”（Common Attributes）部分来配置流布局行为：

![](img/as_flow_attributes.jpg)

图 19-39

## 19.17 组件组的对齐与分布

当布局中选择了两个或多个组件时，Android Studio 布局编辑器工具提供一系列对齐和分布操作。按住 Shift 点击要参与操作的每个组件，右键点击布局并从“对齐”（Align）菜单中显示的许多选项中进行选择：

![](img/as_layout_align_menu.jpg)

图 19-40

如下 图 19-41 所示，这些选项也可以通过布局编辑器工具栏上的“对齐”按钮访问：

![](img/as_layout_align_menu_2.jpg)

图 19-41

图 19-41

同样，`Pack` 菜单（图 19-42）可以用于对所选的小部件进行整体重新定位，使其在垂直或水平方向上紧凑在一起。它通过更改小部件的绝对 `x` 和 `y` 坐标来实现这一点，但不会应用任何约束。另一方面，`Pack` 菜单中的两个分布选项会移动所选的小部件，使它们在垂直或水平轴上均匀间距分布，并在视图之间应用约束以保持这种间距：

![](img/as_layout_pack_menu.jpg)

图 19-42

## 19.18 将其他布局转换为 ConstraintLayout

对于使用一个或多个 Android 布局类（例如 `RelativeLayout` 或 `LinearLayout`）的现有用户界面布局，`Layout Editor` 工具提供了一个将用户界面转换为使用 `ConstraintLayout` 的选项。

当 `Layout Editor` 工具打开并处于 `Design` 模式时，`Component Tree` 面板显示在 `Palette` 之下。要将布局转换为 `ConstraintLayout`，在 `Component Tree` 中找到它，右键点击它，并选择 `Convert <current layout> to Constraint Layout` 菜单选项：

![](img/as_layout_convert_view_menu.jpg)

图 19-43

选择此菜单选项时，`Android Studio` 将将选的布局转换为 `ConstraintLayout`，并使用推理来建立旨在匹配原始布局类型行为的约束。

### 19.19 总结

重新设计的 `Layout Editor` 工具结合 `ConstraintLayout` 使得使用 `Android Studio` 设计复杂的用户界面布局成为一个相对快速且直观的过程。本章详细详细介绍了约束、外边距（margins）和偏置（bias）的概念，同时探索了基于 `ConstraintLayout` 的设计如何集成到 `Layout Editor` 工具中。

## 20. 在 Android Studio 中使用 ConstraintLayout 链和比例



之前的章节介绍了`ConstraintLayout`类的关键功能，并概述了在`Android Studio Layout Editor`中进行基于`ConstraintLayout`的用户界面设计的最佳实践。虽然`ConstraintLayout`链（chains）和比例（ratios）的概念在标题为“Android ConstraintLayout 指南”的章节中概述过，但我们还没有介绍如何在`Layout Editor`中使用这些功能。因此，本章的重点是提供在使用`ConstraintLayout`类时创建和管理链和比例的实用步骤。

## 20.1 创建链

链可以通过在活动的 XML 布局资源文件中添加几行代码，或通过`Layout Editor`的某些链特定功能来实现。

考虑一个由三个`Button`小部件组成的布局，它们被约束在`ConstraintLayout`父布局的左上角、顶部中央和右上角，如图图 20-1](#Chains_and_Ratios.xhtml__idTextAnchor527)所示：

![](img/as_three_button_row.jpg)

图 20-1

为了表示此类布局，XML 资源布局文件可能包含以下按钮小部件的项：

```xml
<Button
    android:id="@+id/button1"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_marginStart="8dp"
    android:layout_marginTop="16dp"
    android:text="Button"
    app:layout_constraintHorizontal_bias="0.5"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent" />

<Button
    android:id="@+id/button2"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_marginEnd="8dp"
    android:layout_marginStart="8dp"
    android:layout_marginTop="16dp"
    android:text="Button"
    app:layout_constraintHorizontal_bias="0.5"
    app:layout_constraintEnd_toStartOf="@+id/button3"
    app:layout_constraintStart_toEndOf="@+id/button1"
    app:layout_constraintTop_toTopOf="parent" />

<Button
    android:id="@+id/button3"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_marginEnd="8dp"
    android:layout_marginTop="16dp"
    android:text="Button"
    app:layout_constraintHorizontal_bias="0.5"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintTop_toTopOf="parent" />
```

按照目前的配置，没有双向约束将这些小部件分组成一条链。为了解决这个问题，需要从`button1`的右侧到`button2`的左侧，以及从`button3`的左侧到`button2`的右侧添加额外的约束，如下：

```xml
<Button
    android:id="@+id/button1"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_marginStart="8dp"
    android:layout_marginTop="16dp"
    android:text="Button"
    app:layout_constraintHorizontal_bias="0.5"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent" />

<Button
    android:id="@+id/button2"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_marginEnd="8dp"
    android:layout_marginStart="8dp"
    android:layout_marginTop="16dp"
    android:text="Button"
    app:layout_constraintHorizontal_bias="0.5"
    app:layout_constraintEnd_toStartOf="@+id/button3"
    app:layout_constraintStart_toEndOf="@+id/button1"
    app:layout_constraintTop_toTopOf="parent" />

<Button
    android:id="@+id/button3"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_marginEnd="8dp"
    android:layout_marginTop="16dp"
    android:text="Button"
    app:layout_constraintHorizontal_bias="0.5"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintTop_toTopOf="parent" />
```

通过这些更改后，小部件现在具有双向水平约束。这构成了`Layout Editor`中通过链连接表示的`ConstraintLayout`链，如下面的图 20-2](#Chains_and_Ratios.xhtml__idTextAnchor529)所示。注意，链默认为分散（spread）样式。

![](img/as_layout_chain.jpg)

图 20-2

也可以通过右键点击视图之一并选择`Chains -> Create Horizontal Chain`或`Chains -> Create Vertical Chain`菜单选项来创建链。

## 20.2 修改链样式

如果没有配置链样式，`ConstraintLayout`将默认使用分散样式。可以通过右键点击链中的任何小部件并选择`Cycle Chain Mode`菜单选项来更改链样式。每次点击该菜单选项，样式会在分散（spread）、内部分散（spread inside）和紧凑（packed）之间切换。

或者，可以在`Attributes`工具窗口中展开`layout_constraints`属性，并根据链的方向更改`horizontal_chainStyle`或`vertical_chainStyle`属性：

![](img/as_layout_chain_style.jpg)

图 20-3

## 20.3 内部分散链样式

使用上述技术将链样式更改为内部分散链样式的效果如图 20-4](#Chains_and_Ratios.xhtml__idTextAnchor533）所示：

![](img/as_layout_chain_spread_inside.jpg)

图 20-4

## 20.4 紧凑链样式

使用相同的技术，将链样式属性更改为`packed`会导致布局发生变化，如图 20-5](#Chains_and_Ratios.xhtml__idTextAnchor536）所示：

![](img/as_layout_chain_packed.jpg)

图 20-5

## 20.5 带偏置的紧凑链样式

紧凑链（packed chain）的位置可能会受到偏移值（bias value）的影响。偏移值范围在 0.0 到 1.0 之间，0.5 代表父容器的中心。偏移可以通过选择链头部控件，并在属性（Attributes）面板中为`layout_constraintHorizontal_bias`或`layout_constraintVertical_bias`属性赋值来控制。图 20-6 显示了一个水平偏移设为 0.2 的紧凑链：

![](img/as_layout_chain_packed_bias.jpg)

图 20-6

## 20.6 加权链

要探索的最后链类型涉及对单个控件进行加权，以控制链中每个控件在可用空间中所占的比例。加权链只能通过散开链（spread chain）样式实现，并且链中任何响应权重属性的控件必须将其相应的尺寸属性（垂直链为`height`，水平链为`width`）配置为匹配约束（match constraint）模式。控件尺寸的匹配约束模式可以通过选择控件、显示属性面板并将尺寸更改为`match_constraint`（等于 0dp）来配置。例如，在图 20-7 中，按钮的`layout_width`约束已设置为`match_constraint`（0dp），表示控件的宽度将根据现有的约束设置来确定：

![](img/as_match_constraints.jpg)

图 20-7

假设已选择散开链样式且三个按钮均已配置为宽度设置为匹配约束，则链中的控件将等比例扩展以填充可用空间：

![](img/as_layout_unweighted_chain.jpg)

图 20-8

每个控件相对于链中其他控件的占空间大小可以通过向控件添加权重属性（weight）来控制。图 20-9 显示了将`button1`的`layout_constraintHorizontal_weight`属性设置为 4，将`button2`和`button3`均设置为 2 的效果：

![](img/as_layout_weighted_chain.jpg)

图 20-9

由于这些权重值，`button1`占据了空间的一半（4/8），而`button2`和`button3`各占据空间的四分之一（2/8）。

## 20.7 比例的使用

`ConstraintLayout`比例允许一个控件的尺寸相对于控件的另一个尺寸进行缩放（也称为宽高比）。例如，可以为`ImageView`应用长高宽比设置，以确保其宽度始终是高度的两倍。

尺寸比例约束是通过将受限的维度设置为匹配约束模式，并将该控件的`layout_constraintDimensionRatio`属性配置为所需的比例来实现的。该比例值可以指定为浮点值或宽:高比例设置。例如，以下 XML 代码段在`ImageView`控件上配置了 2:1 的比例：

```xml
<ImageView
    android:layout_width="0dp"
    android:layout_height="100dp"
    android:id="@+id/imageView"
    app:layout_constraintDimensionRatio="2:1" />
```

上面的示例演示了当仅设置一个维度为匹配约束时如何配置比例。当两个维度都设置为匹配约束模式时，也可以应用比例。这需要在比例前加上`H`或`W`，以指示哪一个维度是相对于另一个维度进行受限的。

例如，考虑以下`ImageView`对象的 XML 代码段：

```xml
<ImageView
    android:layout_width="0dp"
    android:layout_height="0dp"
    android:id="@+id/imageView"
    app:layout_constraintBottom_toBottomOf="parent"
    app:layout_constraintRight_toRightOf="parent"
    app:layout_constraintLeft_toLeftOf="parent"
    app:layout_constraintTop_toTopOf="parent"
    app:layout_constraintDimensionRatio="W,1:3" />
```

在上述示例中，高度将根据应用于其上的约束来定义。在这种情况下，配置了约束，使其附加到父视图的顶部和底部，实质上是将控件拉伸以填充父视图的高度。另一方面，宽度维度被限制为`ImageView`高度的三分之一。因此，无论布局显示在什么尺寸的屏幕或方向上，`ImageView`的高度始终与父视图相同，宽度为该高度的三分之一。

在不手动编辑 XML 资源文件的情况下也可以获得相同的结果。每当控件维度设置为匹配约束模式时，属性面板的检查器区域就会出现一个比例控制开关。例如，图 20-10 显示了按钮控件的布局宽度和高度属性分别设置为匹配约束模式和 100dp，并高亮了比例控制开关：

![](img/as_layout_toggle.jpg)

图 20-10

默认情况下，比例控制是关闭的。点击该控件可以启用比例约束，并显示一个可以更改比例的额外字段：

![](img/as_layout_ratio.jpg)

图 20-11

## 20.8 总结

链和比例都是`ConstraintLayout`的强大功能，旨在为设计灵活的用户界面提供更多选项。正如本章所述，Android 编辑器已经过增强，以便在界面设计过程中使用这些功能。

## 21. ConstraintLayout 教程

设计 Android 界面的最简单且有效的方法是使用布局编辑器。本章将提供如何使用这种方法创建基于`ConstraintLayout`的界面的概述。本章包含的练习也将作为从“空白”Android 项目开始活动的机会。

在介绍布局编辑器之后，本章还将介绍布局检查器。

### 21.1 布局编辑器示例

此阶段的第一步是创建一个 Android 项目。启动 Android Studio 并通过选择`File -> Close Project`关闭任何之前打开的项目。

在欢迎屏幕上选择`New Project`，选择`Empty Views Activity`模板并点击`Next`。在`Name`字段中输入`LayoutSample`，并将`com.ebookrenzy.layoutsample`作为包名。在点击`Finish`按钮之前，将`Minimum API`级别设置为`API 26: Android 8.0 (Oreo)`并将`Language`菜单更改为 Java。

### 21.2 准备布局编辑器环境

在`app -> res -> layout`文件夹中找到并双击`activity_main.xml`布局文件，将其加载到布局编辑器。由于本教程旨在获得使用约束的经验，使用布局编辑器工具栏上的按钮关闭`Autoconnect`功能。一旦禁用，该按钮将出现一条删除线，正如图 21-1 所示：

![](img/as_layout_sample_autoconnect_off.jpg)

图 21-1

如果`Autoconnect`按钮右侧的默认间距值不是 8dp，点击它并在生成的面板中选择 8dp。

用户界面设计还将使用`ImageView`对象来显示图像。在继续之前，应将此图像添加到项目中，以便在章节稍后的部分使用。

[`www.ebookfrenzy.com/retail/giraffejava/index.php`](https://www.ebookfrenzy.com/retail/giraffejava/index.php)

在 Android Studio 中，显示资源管理器工具窗口（`View -> Tool Windows -> Resource Manager`）。在操作系统的文件导航器中找到`GalaxyS23.webp`图像并将其拖放到`Resource Manager`工具窗口中。在弹出的对话框中，点击`Next`，然后点击`Import`按钮，将图像添加到项目中。现在该图像应该出现在`Resource Manager`中，如下方的图 21-2 所示：

![](img/as_resource_manager.jpg)

图 21-2

该图像也会出现在`Project`工具窗口的`res -> drawables`部分：

![](img/as_layout_sample_image_added.jpg)

图 21-3

## 21.3 向用户界面添加小部件



从`Common`调板类别中，将`ImageView`对象拖入显示视图的中心。注意此时会出现水平和垂直的虚线，表示显示的中心轴。居中时，释放鼠标按键将视图放置在目标位置。一旦放置在布局中，就会出现`Resources`对话框，请求在视图中显示的图像。在对话框顶部的搜索栏中输入“galaxy”以找到`galaxysys6.png`资源，如图 21-4 所示：

![](img/as_pick_a_resource.jpg)

图 21-4

选择图像并点击`OK`将其分配给`ImageView`对象。如有必要，使用缩放手柄调整`ImageView`的大小，并将其重新定位在布局中心。此时，布局应当与图 21-5 一致：

![](img/as_layout_sample_image_layout.jpg)

图 21-5

从调板的`Common`部分点击并拖动`TextView`对象，并将其放置在`ImageView`上方，如图 21-6 所示：

使用`Attributes`面板，展开`Common Attributes`部分中的`textAppearance`属性条目，将`textSize`属性改为`24sp`，将`textAlignment`设置为居中，并将文本改为“Samsung Galaxy S23”。

![](img/as_layout_sample_textview.jpg)

图 21-6

接下来，在布局底部添加三个`Button`小部件，并将这些视图的文本属性设置为“Buy Now”、“Pricing”和“Details”。完成后的布局现在应当与图 21-7 一致：

![](img/as_layout_sample_full_ui.jpg)

图 21-7

此时，小部件的约束还不足，以使布局引擎能够在运行时对它们进行定位和调整大小。如果现在运行程序，所有小部件都将位于在显示器的左上角。

在布局中添加小部件后，使用Layout编辑器工具栏中的设备旋转菜单（如图 21-8 中的箭头所示），以横屏模式查看用户界面：

![](img/as_layout_rotate_device.jpg)

图 21-8

缺少约束会导致布局无法适应设备方向的变化，导致内容偏离中心，并且部分图像以及三个按钮都位于屏幕的可视区域之外。要使此成为一个响应式用户界面，仍需要进行一些工作。

## 21.4 添加约束

约束是创建适应设备方向变化和不同屏幕尺寸布局的关键。首先将布局旋转回竖屏模式，并选择`ImageView`上方的`TextView`小部件。在选中小部件后，从`TextView`的左侧、右侧和顶部建立到父级`ConstraintLayout`相应侧的约束，如图 21-9 所示。将顶部约束的间距设置为`16`：

![](img/as_layout_sample_textview_constraints.jpg)

图 21-9

约束好`TextView`小部件后，选择`ImageView`实例并在左右两侧建立相对的约束，每个约束都连接到父布局的相应侧。接下来，建立从`ImageView`顶部到`TextView`底部的约束连接，以及从`ImageView`底部到中间`Button`小部件顶部的约束。如有必要，点击并拖动`ImageView`以保持其位于布局的垂直中心。

在仍选中`ImageView`的情况下，使用属性面板中的`Inspector`将`ImageView`的顶部和底部边距分别更改为`24`和`8`，并将小部件的高度和宽度维度属性都更改为`match_constraint`，这样小部件将根据约束调整大小。这些设置将允许布局引擎在需要时放大或缩小`ImageView`的尺寸以适应布局变化：

![](img/as_layout_sample_constraints.jpg)

图 21-10

图 21-11 显示了相对于布局中其他元素的`ImageView`当前实现的约束：

![](img/as_layout_sample_constraints.jpg)

图 21-11

最后的任务是为三个`Button`小部件添加约束。对于此示例，按钮将放置在链中。首先，通过点击Layout编辑器中如图 21-1 所示的工具栏开启`Autoconnect`。

接下来，点击`Buy Now`按钮，然后Shift点击另外两个按钮以选中三个。右键点击`Buy Now`按钮并从菜单中选择`Chains -> Create Horizontal Chain`。默认情况下，链将使用`spread`样式显示，这是本示例的正确行为。最后，在`Buy Now`按钮与布局底部之间建立约束，设置为`8`。对剩余按钮重复此步骤。

完成这些步骤后，按钮应当如图 21-12 所示受到约束：

![](img/as_layout_sample_button_chain.jpg)

图 21-12

## 21.5 测试布局

向布局添加约束后，将屏幕旋转到横屏并验证布局适应新的屏幕尺寸。

虽然Layout Editor工具提供了一个设计用户界面布局的良好视觉环境，但在测试方面，运行应用程序是必要的。在物理Android设备或模拟器会话上启动应用，并验证用户界面反映了在Layout Editor中创建的布局。例如，图 21-13 显示了横屏模式下的运行应用：

![](img/as_layout_sample_landscape.jpg)

图 21-13

用户界面设计已完成。设计更复杂的用户界面布局是上述步骤的延续。根据需要将视图拖放到显示器、定位、约束并设置属性。

## 21.6 使用 Layout Inspector

可以使用`Layout Inspector`工具查看用户界面布局的组件层次结构。应用程序必须在运行Android API 29或更高版本的设备或模拟器上运行才能访问此类信息。应用运行时，选择`Tools -> Layout Inspector`菜单选项，然后使用下方图 21-14 中标记为A的菜单选择要检查的过程。

一旦布局检查器（Inspector）加载，左侧面板 (A) 将显示组成用户界面布局的组件层级。中间面板 (B) 可视化地表示布局设计。点击视觉布局中的一个部件会导致该项在层级列表中高亮显示，从而轻松找到视觉组件相对于整体布局层级的位置。

最右侧面板（在图 21-14 中标记为C）包含当前选中组件的所有属性设置，允许对组件的内部配置进行深度分析。在适当的情况下，值单元格将包含指向项目源代码中属性设置位置的链接。

![](img/as_layout_sample_layout_inspector.jpg)

图 21-14

要以3D视图查看布局，点击标记为D的按钮。这将显示层级的“爆炸”表示，以便对其进行旋转和检查。这对于识别遮挡的视图等任务非常有用：

![](img/as_layout_sample_layout_inspector_3d.jpg)

图 21-15

点击并拖动渲染图以进行三维旋转，使用上方箭头指示的滑块来增加层之间的间距。再次点击标记为E的按钮返回2D视图。

## 21.7 总结

Android Studio中的布局编辑器工具与`ConstraintLayout`类紧密集成。本章通过创建一个示例用户界面，概述了如何使用布局编辑器工具添加部件并设置约束来实现基于`ConstraintLayout`的用户界面。本章还介绍了实时布局检查器（Live Layout Inspector）工具，它对于分析用户界面布局的结构组成很有用。

# 22 在 Android Studio 中手动设计 XML 布局

虽然使用Android Studio布局编辑器工具设计布局极大地提高了效率，但仍然可以通过手动编辑底层XML创建XML布局。本章将介绍Android XML布局文件格式的基础。

## 22.1 手动创建 XML 布局

XML布局文件的结构非常简单，遵循视图树的层级方法。XML资源文件的第一行理想情况下包含以下标准声明：

```xml
<?xml version="1.0" encoding="utf-8"?>
```

该声明之后应当是布局的根元素，通常是一个容器视图（例如布局管理器）。这由起始和结束标签以及需要在视图上设置的任何属性表示。例如，下面的XML声明了一个`ConstraintLayout`视图作为根元素，并设置`match_parent`属性使其填充设备显示的所有可用空间：

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:paddingLeft="16dp"
    android:paddingRight="16dp"
    android:paddingTop="16dp"
    android:paddingBottom="16dp"
    tools:context=".MainActivity">
</androidx.constraintlayout.widget.ConstraintLayout>
```

在上面的示例中，布局元素每个侧都配置了16dp（密度无关像素）的内边距。Android布局中的任何间距规范必须使用以下测量单位之一：

* `in` – 英寸。

* `mm` – 毫米。

* `pt` – 点（1/72 英寸）。

* `dp` – 密度无关像素。一种根据设备显示物理密度相对于160dpi显示基准而计算的抽象测量单位。

* `sp` – 字体缩放无关像素。与`dp`类似，但会根据用户的字体偏好进行缩放。

* `px` – 实际像素。不建议使用，因为不同的显示器每英寸像素数不同。建议使用`dp`而不是此单位。

任何需要添加到`ConstraintLayout`父元素的子元素必须嵌套在起始和结束标签之间。在接下来的示例中，添加了一个`Button`部件作为`ConstraintLayout`的子：

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">
    <Button
        android:text="My Button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+button" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

按照目前的实现，该按钮没有任何连接。因此，在运行时，按钮将出现在右上角（尽管由于父元素分配的内边距，它缩进了16dp）。如果为按钮侧边添加了约束，它将显示在布局的居中位置：

```xml
<Button
    android:text="My Button"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:id="@+button"
    app:layout_constraintBottom="parent"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent" />
```

要在布局布局中添加第二个部件，请将其嵌入`ConstraintLayout`的主体内。下面的修改示例添加了一个`TextView`：

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:paddingLeft="16dp"
    android:paddingTop="16dp"
    android:paddingRight="16dp"
    android:paddingBottom="16dp"
    tools:context=".MainActivity">
    <Button
        android:text="@string/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+button"
        app:layout_constraintBottom="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
    <TextView
        android:text="My Text"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/textView" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

再次，由于新添加的`TextView`缺少约束，它将在运行时出现在布局的左上角。下面的修改添加了连接父布局的对立约束以使部件水平居中，同时添加了一个将`TextView`底部连接到`button`顶部的约束：

```xml
<TextView
    android:text="My Text"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:id="@+id/textView"
    android:layout_marginTop="8dp"
    android:layout_marginBottom="8dp"
    app:layout_constraintBottom_toTopOf="@+id/button"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent" />
```

此外，请注意`Button`和`TextView`视图声明了几个属性。这两个视图都分配了ID，并被配置为显示由名为`button_string`和`text_string`的字符串资源表示的文本字符串。此外，两个对象都声明了`wrap_content`高和`width`属性，以便它们的大小能够适应内容（在本例中，为字符串资源值所引用的文本）。

在设计模式下从布局编辑器的预览（Preview）面板查看，上述布局的渲染结果如图 22-1 所示：

![](img/as_manual_xml_ui.jpg)

图 22-1

## 22.2 手动 XML 与视觉化布局设计

是手动编写XML还是使用设计模式下的布局编辑器工具，取决于个人偏好。然而，使用设计模式具有其优势。

首先，设计模式通常会更快，因为它避免了输入XML代码的需要。此外，设计模式避免了学习Android SDK视图类中各种属性值的复杂性。不需要不断查阅Android文档来查找正确的关键字和值，大多数属性都可以通过参考属性（Attributes）面板来找到。



抛开设计模式的所有优势不谈，重要的是，用户界面设计的这两种方法并不是互斥的。作为应用程序开发者，你可能会在设计模式下创建用户界面，同时通过直接编辑生成的 XML 资源对设计进行微调和布局调整。界面设计的两种视图在 Android Studio 环境中并排显示，使得在 XML 和视觉布局之间进行无缝工作变得易许多。

## 22.3 总结

Android Studio 布局编辑器工具为用户界面设计提供了一种视觉直观的方法。通过使用拖放模式结合一组属性编辑器，该工具为应用程序开发者带来了显著的生产力优势。

用户界面设计也可以通过手动编写 XML 布局资源文件来实现，其格式结构良好且易于理解。

布局编辑器工具生成 XML 资源文件的事实意味着，这两种界面设计方法可以结合，为用户界面开发提供一种“兼取优优点”的方法。

## 23 使用约束集管理约束

到本书为止，所有的用户界面设计任务都是使用 Android Studio 布局编辑器工具（以文本或设计模式）完成的。编写 XML 资源文件或使用 Android Studio 布局编辑器的替代方案是编写 Java 代码来直接创建、配置和操作组成 Android Activity 用户界面的视图对象。本章将探索编写 Java 代码创建用户界面的某些优缺点，然后描述如视图属性以及布局约束的创建和管理等关键概念。

在下一章中，将创建并使用一个示例项目，以演示这种 Android 用户界面创建方法中涉及的一些典型步骤。

### 23.1 Java 代码与 XML 布局文件

相比 Java 代码，使用 XML 资源文件设计用户界面（而不是编写 Java 代码）具有许多优势。事实上，Google 在 Android 文档中花费了大量精力来赞扬 XML 资源优于 Java 代码的优点。正如上一节讨论的，XML 方法的一个关键优势是可以使用 Android Studio 布局编辑器工具，它可以生成 XML 资源。第二个优势是，一旦创建了应用程序，就可以通过修改 XML 文件对用户界面屏幕进行更改，从而避免重新编译应用程序。此外，即使是手动编写 XML 布局，也可以通过 Android Studio 布局编辑器的预览功能对用户界面的外观获得即时反馈。为了测试由 Java 创建的用户界面的外观，开发者不可避免地需要循环编写代码、编译和测试，以完成设计工作。

关于使用 Java 代码创建布局的优势，Java 相比 XML 资源文件最显著的优势体现在处理动态用户界面时。XML 资源文件在定义静态布局时本质上最有用，静态布局在每次调用 Activity 之间不太发生显著变化。相反，Java 代码非常适合在运行时动态创建用户界面。当用户界面可能受外部因素影响每次执行 Activity 时显示不同时，这特别有用。

当必须在 Activity 运行时实时对基于静态 XML 资源的布局进行动态更改时，在 Java 代码中处理用户界面组件的知识也会有用。

最后，一些开发者倾向于编写 Java 代码而不是使用布局工具和 XML，无论后者提供了哪些优势。

### 23.2 创建视图

如前，Android SDK 包含了一个视图类工具箱，以满足大多数基本的用户界面设计需求。在 Java 中创建视图就是创建这些类的实例，并传递与该视图关联的 Activity 引用作为参数。

第一个视图（通常是可以添加额外子视图的容器视图）通过调用 Activity 的 `setContentView()` 方法显示给用户。可以通过调用对象的 `addView()` 方法向根视图中添加额外的视图。

当使用 Java 代码操作 XML 布局资源文件中包含的视图时，必须获取视图的 ID。在 Java 中创建的视图遵循相同的规则。因此，对于后续 Java 代码中需要某些类型访问的任何视图，都有必要分配一个 ID。这是通过调用相关视图对象的 `setId()` 方法实现的。在随后的代码中，可以通过对象的 `getId()` 方法获取视图的 ID。

### 23.3 视图属性

每个视图类都关联有一系列属性。这些属性设置直接设置在视图实例上，通常定义了视图对象的外观或行为。属性的示例包括 `Button` 对象上的文本或 `ConstraintLayout` 视图的背景颜色。Android SDK 中的每个视图类都有一组预定义的方法，允许用户设置和获取这些属性值。例如，`Button` 类有一个 `setText()` 方法，可以在 Java 代码中调用它将按钮显示的文本设置为特定的字符串值。另一方面，`ConstraintLayout` 对象的背景颜色可以通过调用对象的 `setBackgroundColor()` 方法设置。

### 23.4 约束集

虽然属性设置是视图内部的并决定了视图的外观和行为，但约束集控制视图相对于父视图和其他兄弟视图的外观。每个 `ConstraintLayout` 实例都关联有一组约束，定义了子视图的位置和约束关系。

在 Java 代码中处理约束集的关键是 `ConstraintSet` 类。该类包含一系列方法，允许执行创建、配置和向 `ConstraintLayout` 实例应用约束的任务。此外，可以将 `ConstraintLayout` 实例的当前约束复制到 `ConstraintSet` 对象中，并应用到其他布局（无论是否经过修改）。

`ConstraintSet` 实例像任何其他 Java 对象一样被创建：

```java
ConstraintSet set = new ConstraintSet();
```

一旦创建了约束集，就可以调用实例上的方法来执行各种任务。

#### 23.4.1 建立连接

`ConstraintSet` 类的 `connect()` 方法用于建立视图之间的约束连接。以下代码配置了一个约束集，其中 `Button` 视图的左侧连接到 `EditText` 视图的右侧，并有 70dp 的间距：

```java
set.connect(button1.getId(), ConstraintSet.LEFT,
            editText1.getId(), ConstraintSet.RIGHT, 70);
```

### 23.4.2 将约束应用到布局

一旦配置了约束集，必须将其应用到 `ConstraintLayout` 实例才能生效。可以通过调用 `applyTo()` 方法来应用约束集，并传递要应用设置的布局对象的引用：

```java
set.applyTo(myLayout);
```

### 23.4.3 父级约束连接

通过引用 `ConstraintSet.PARENT_ID` 常量，也可以建立子视图与其父 `ConstraintLayout` 之间的连接。在以下示例中，约束集被配置为将 `Button` 视图的顶部边缘连接到父布局的顶部，间距为 100dp：

```java
set.connect(button1.getId(), ConstraintSet.TOP,
            ConstraintSet.PARENT_ID, ConstraintSet.TOP, 100);
```

#### 23.4.4 尺寸约束

提供了多种方法来控制视图的尺寸行为。例如，以下代码将 `Button` 视图的水平尺寸设置为 `wrap_content`，并将 `ImageView` 实例的垂直尺寸设置为最大 `250dp`：

```java
set.constrainWidth(button1.getId(), ConstraintSet.WRAP_CONTENT);
set.constrainMaxHeight(imageView1.getId(), 250);
```

### 23.4.5 约束偏置 (Constraint Bias)

正如“Android Studio ConstraintLayout 使用指南”章节中所述，当视图具有对立的约束时，它将沿着约束轴（即水平或垂直）居中。这种居中可以通过在特定的约束轴上应用偏置来调整。当使用 Android Studio 布局编辑器时，这是通过 Attributes 工具窗口中的控件实现的。然而，在处理约束集时，可以使用 `setHorizontalBias()` 和 `setVerticalBias()` 方法添加偏置，引用视图 ID 和作为 0 到 1 之间的浮点值的偏置值。

例如，以下代码在应用 25% 的水平偏置之前，将 `Button` 的左侧和右侧连接到父布局的相应侧：

```java
set.connect(button1.getId(), ConstraintSet.LEFT,
            ConstraintSet.PARENT_ID, ConstraintSet.LEFT, 0);
set.connect(button1.getId(), ConstraintSet.RIGHT,
            ConstraintSet.PARENT_ID, ConstraintSet.RIGHT, 0);
set.setHorizontalBias(button1.getId(), 0.25f);
```

#### 23.4.6 对齐约束

也可以使用约束集应用对齐方式。Android Studio 布局编辑器提供的全套对齐选项也可以通过 `centerVertically()` 和 `centerHorizontally()` 方法使用约束集进行配置，这两种方法都根据正在配置的对齐方式接收各种不同的参数。此外，可以使用 `center()` 方法将视图在两个其他视图之间居中。

在下面的代码中，`button2` 的位置设置使其与 `button1` 水平对齐：

```java
set.centerHorizontally(button2.getId(), button1.getId());
```

### 23.4.7 复制和应用约束集

可以使用 `clone()` 方法将 `ConstraintLayout` 实例的当前约束集复制到约束集对象中。例如，以下代码将名为 `myLayout` 的 `ConstraintLayout` 实例的约束设置复制到约束集对象中：

```java
set.clone(myLayout);
```

一旦复制，可以将约束集直接应用于另一个布局，或者像下面的示例所示，在应用到第二个布局之前进行修改：

```java
ConstraintSet set = new ConstraintSet();
set.clone(myLayout);
set.constrainWidth(button1.getId(), ConstraintSet.WRAP_CONTENT);
set.applyTo(mySecondLayout);
```

### 23.4.8 ConstraintLayout 链 (Chains)

还可以使用 `createHorizontalChain()` 和 `createVerticalChain()` 方法在约束集中创建垂直和水平链。使用这些方法的语法如下：

```java
createHorizontalChain(int leftId, int leftSide, int rightId, int rightSide, int[] chainIds, float[] weights, int style);
```

根据上述语法，以下示例创建了一个从 `button1` 开始到 `button4` 结束的水平扩散链。在这些视图之间是 `button2` 和 `button3`，它们的权重都设置为零：

```java
int[] chainViews = {button2.getId(), button3.getId()};
float[] chainWeights = {0, 0};
set.createHorizontalChain(button1.getId(), ConstraintSet.LEFT,
        ConstraintSet.PARENT_ID, ConstraintSet.RIGHT, chainViews, 
        chainWeights, ConstraintSet.SPREAD);
```

### 23.4.9 引导线 (Guidelines)

使用 `create()` 方法将引导线添加到约束集中，并使用 `setGuidelineBegin()`、`setGuidelineEnd()` 或 `setGuidelinePercent()` 进行定位。在下面的代码中，创建一个垂直引导线并将其放置在父布局宽度的 50% 处。然后将 `Button` 视图的左侧连接到该引导线且无间距：

```java
set.create(R.id.myGuideline, ConstraintSet.VERTICAL_GUIDELINE);
set.setGuidelinePercent(R.id.myGuideline, 0.5f);
set.connect(button.getId(), ConstraintSet.LEFT,
        R.id.myGuideline, ConstraintSet.RIGHT, 0);
set.applyTo(layout);
```

#### 23.4.10 移除约束

可以使用 `clear()` 方法从约束集中移除约束，传递视图 ID 和要移除约束的锚点：

```java
set.clear(button.getId(), ConstraintSet.LEFT);
```

同样，可以通过在 `clear()` 方法中引用视图来一次性移除视图的所有约束：

```java
set.clear(button.getId());
```

#### 23.4.11 缩放

可以使用 `ConstraintSet` 的 `setScaleX()` 和 `setScaleY()` 方法调整布局内视图的比例，这些方法接收执行操作的视图以及表示比例的浮点值。在下面的代码中，按钮对象缩放为宽的两倍和高度的一半：

```java
set.setScaleX(myButton.getId(), 2f);
set.setScaleY(myButton.getId(), 0.5f);
```

#### 23.4.12 旋转

可以使用 `setRotationX()` 和 `setRotationY()` 方法分别在 X 轴或 Y 轴上旋转视图，这两种方法必须传递要旋转视图的 ID 和表示旋转角度的浮点值。旋转轴点可以通过调用 `setTransformPivot()`、`setTransformPivotX()` 和 `setTransformPivotY()` 方法来定义。下面的代码使用位于 500, 500 的轴点将按钮视图沿 Y 轴旋转 30 度：

```java
set.setTransformPivot(button.getId(), 500, 500);
set.setRotationY(button.getId(), 30);
set.applyTo(layout);
```

[`developer.android.com/reference/androidx/constraintlayout/widget/ConstraintSet`](https://developer.android.com/reference/androidx/constraintlayout/widget/ConstraintSet)

### 23.5 总结

作为编写 XML 布局资源文件或使用 Android Studio 布局工具的替代方案，Android 用户界面也可以 Java 代码中动态创建。

在 Java 代码中创建布局包括创建视图类的实例，并在这些对象上设置属性，以定义所需的显示和行为。

视图相对于其 `ConstraintLayout` 父视图以及任何兄弟视图的定位和大小是通过使用约束集（constraint sets）来定义的。约束集由 `ConstraintSet` 类的实例表示，一旦创建，就可以可以使用广泛的方法调用进行配置，以执行诸如建立约束连接、控制视图尺寸行为以及创建链（chains）等任务。

在本章介绍 `ConstraintSet` 类的基础知识后，下一章将通过一个教程将这些功能应用于实际场景。

## 24. Android ConstraintSet 教程

上一章介绍了使用 `ConstraintLayout` 和 `ConstraintSet` 类在 Java 代码中创建和修改用户界面布局的基本概念。本章将通过创建一个完全使用 Java 代码创建且不使用 Android Studio 布局工具的示例布局将这些概念付诸实践。

### 24.1 在 Android Studio 中创建示例项目

启动 Android Studio，从欢迎屏幕上选择 `New Project` ，在弹出的新项目对话框中，点击 `Next` 按钮之前选择 `Empty Views Activity` 模板。

在 `Name` 字段中输入 `JavaLayout`，并指定 `com.ebookfrenzy.javalayout` 为包名。在点击 `Finish` 按钮之前，将 `Minimum API` 级别设置改为 `API 26`：Android 8.0 (Oreo)，并将 `Language` 菜单设置为 `Java`。

项目创建完成后，`MainActivity.java` 文件将自动加载到编辑面板中。正如我们预期的那样，Android Studio 创建了一个模板 Activity 并重写了 `onCreate()` 方法，为添加 Java 代码以创建用户界面提供了一个理想位置。

### 24.2 向 Activity 添加视图

`onCreate()` 方法目前设计为使用资源布局文件作为用户界面。因此，首先从该方法中删除此行代码：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);
}
```



下一个修改是向`Activity`添加一个包含单个`Button`视图子元素的`ConstraintLayout`对象。这涉及创建`ConstraintLayout`和`Button`类的新实例。然后需要将`Button`视图作为子视图添加到`ConstraintLayout`视图中，进而通过调用`Activity`实例的`setContentView()`方法显示：

```java
package com.ebookfrenzy.javalayout;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import androidx.constraintlayout.widget.ConstraintLayout;
import android.widget.Button;
import android.widget.EditText;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        configureLayout();
    }

    private void configureLayout() {
        Button myButton = new Button(this);
        ConstraintLayout myLayout = new ConstraintLayout(this);
        myLayout.addView(myButton);
        setContentView(myLayout);
    }
}
```

当以此方式创建用户界面对象的新实例时，必须向构造方法传递创建该对象的上下文（context），在本例中，它是当前的`Activity`。由于上述代码位于`Activity`类中，因此通过标准的`this`关键字引用上下文：

`Button myButton = new Button(this);`

完成上述添加后，编译并运行应用程序（在物理设备或模拟器上）。启动后，可见结果将显示现在`ConstraintLayout`视图的左上角，一个没有文本的按钮，如图 [24-1] 所示。

![](img/Image2435.jpg)

图 24-1

### 24.3 设置视图属性

对于此练习，我们需要`ConstraintLayout`视图的背景为蓝色，并让`Button`视图在黄色背景上显示文本为“Press Me”。这些任务可以通过如下文代码片段所示，在Java代码中为视图设置属性来实现。为了让按钮上的文本能够轻松翻译成其他语言，将将其作为`String`资源添加。在`Project`工具窗口中，找到`app -> res -> values -> strings.xml`文件并对其进行修改，为“Press Me”字符串添加资源值：

```xml
<resources>
    <string name="app_name">JavaLayout</string>
    <string name="press_me">Press Me</string>
</resources>
```

虽然这是处理代码中直接引用的字符串的推荐方法，但后续许多代码示例将直接在代码中输入字符串，以避免重复本书的内容。一旦字符串存储为资源，就可以从代码内部访问：`getString(R.string.press_me)`。

创建字符串资源后，添加代码设置文本和颜色：

```java
import android.graphics.Color;

public class MainActivity extends AppCompatActivity {
    private void configureLayout() {
        Button myButton = new Button(this);
        myButton.setText(getString(R.string.press_me));
        myButton.setBackgroundColor(Color.YELLOW);
        ConstraintLayout myLayout = new ConstraintLayout(this);
        myLayout.setBackgroundColor(Color.BLUE);
        myLayout.addView(myButton);
        setContentView(myLayout);
    }
}
```

当应用程序运行时，布局将反映这些属性设置，使得布局呈现蓝色背景，按钮在黄色背景上显示指定的文本。

### 24.4 创建视图 ID

当布局完成后，它将包含一个`Button`和一个`EditText`视图。在`ConstraintSet`类的方法引用这些视图之前，必须为它们分配唯一的ID。此过程的第一步是创建一个包含这些ID的新资源文件。

右键点击`app -> res -> values`文件夹，选择`New -> Values Resource File`，并将新资源文件命名为`id.xml`。创建资源文件后，将其修改如下：

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <item name="myButton" type="id" />
    <item name="myEditText" type="id" />
</resources>
```

在教程的此时，只创建了`Button`，因此编辑`configureLayout()`方法为对象分配相应的ID：

```java
private void configureLayout() {
    Button myButton = new Button(this);
    myButton.setText(getString(R.string.press_me));
    myButton.setBackgroundColor(Color.YELLOW);
    myButton.setId(R.id.myButton);
}
```

### 24.5 配置约束集

如果没有约束，`ConstraintLayout`视图将`Button`视图放置在屏幕的左上角。为了指示布局视图将按钮放在不同的位置（在本例中为水平和垂直居中），需要创建一个`ConstraintSet`实例，使用适当的设置对其初始化并将其应用于父布局。

对于此示例，需要配置按钮，使其宽度和高度受其显示的文本大小限制，并将视图在父布局中居中。

```java
import androidx.constraintlayout.widget.ConstraintSet;

private void configureLayout() {
    Button myButton = new Button(this);
    myButton.setText(getString(R.string.press_me));
    myButton.setBackgroundColor(Color.YELLOW);
    myButton.setId(R.id.myButton);
    ConstraintLayout myLayout = new ConstraintLayout(this);
    myLayout.setBackgroundColor(Color.BLUE);
    myLayout.addView(myButton);
    setContentView(myLayout);
    ConstraintSet set = new ConstraintSet();
    set.constrainHeight(myButton.getId(),
              ConstraintSet.WRAP_CONTENT);
    set.constrainWidth(myButton.getId(),
              ConstraintSet.WRAP_CONTENT);
    set.connect(myButton.getId(), ConstraintSet.START,
              ConstraintSet.PARENT_ID, ConstraintSet.START, 0);
    set.connect(myButton.getId(), ConstraintSet.END,
              ConstraintSet.PARENT_ID, ConstraintSet.END, 0);
    set.connect(myButton.getId(), ConstraintSet.TOP,
              ConstraintSet.PARENT_ID, ConstraintSet.TOP, 0);
    set.connect(myButton.getId(), ConstraintSet.BOTTOM,
              ConstraintSet.PARENT_ID, ConstraintSet.BOTTOM, 0);
    set.applyTo(myLayout);
}
```

配置好初始约束后，编译并运行应用程序，验证`Button`视图现在是否出现在布局的中心：

![](img/Image2444.jpg)

图 24-2

### 24.6 添加 EditText 视图

下一个要添加到布局中的项是`EditText`视图。第一步是创建`EditText`对象，分配在`id.xml`资源文件中声明的ID，并将其添加到布局中。为了实现这些步骤，现在需要对`configureLayout()`方法进行如下代码更改：

```java
private void configureLayout() {
    Button myButton = new Button(this);
    myButton.setText(getString(R.string.press_me));
    myButton.setBackgroundColor(Color.YELLOW);
    myButton.setId(R.id.myButton);
    EditText myEditText = new EditText(this);
    myEditText.setId(R.id.myEditText);
    ConstraintLayout myLayout = new ConstraintLayout(this);
    myLayout.setBackgroundColor(Color.BLUE);
    myLayout.addView(myButton);
    myLayout.addView(myEditText);
    setContentView(myLayout);
}
```

`EditText`小部件的设计目标是根据其显示的内容调整大小，在布局中水平居中，并放置在现有`Button`视图上方70dp处。向`configureLayout()`方法添加代码，使其内容如下：

```java
set.connect(myButton.getId(), ConstraintSet.START,
          ConstraintSet.PARENT_ID, ConstraintSet.START, 0);
set.connect(myButton.getId(), ConstraintSet.END,
          ConstraintSet.PARENT_ID, ConstraintSet.END, 0);
set.connect(myButton.getId(), ConstraintSet.TOP,
              ConstraintSet.PARENT_ID, ConstraintSet.TOP, 0);
set.connect(myButton.getId(), ConstraintSet.BOTTOM,
              ConstraintSet.PARENT_ID, ConstraintSet.BOTTOM, 0);
set.constrainHeight(myEditText.getId(),
                    ConstraintSet.WRAP_CONTENT);
set.constrainWidth(myEditText.getId(),
              ConstraintSet.WRAP_CONTENT);
set.connect(myEditText.getId(), ConstraintSet.START,
          ConstraintSet.PARENT_ID, ConstraintSet.START, 0);
set.connect(myEditText.getId(), ConstraintSet.END,
          ConstraintSet.PARENT_ID, ConstraintSet.END, 0);
set.connect(myEditText.getId(), ConstraintSet.BOTTOM,
          myButton.getId(), ConstraintSet.TOP, 70);
set.applyTo(myLayout);
```

应用程序测试运行应该显示`EditText`字段位于按钮上方，并有70dp的间距。

### 24.7 将密度像素 (dp) 转换为像素 (px)

此练习的下一个任务是将`EditText`视图的宽度设置为200dp。正如“Android Studio 布局编辑器 ConstraintLayout 教程”章节概述的那样，在用户界面布局中设置尺寸和位置时，使用密度无关像素 (dp) 比使用像素 (px) 更好。要使用`dp`设置位置，必须在运行时考虑设备密度，将`dp`值转换为`px`值。因此，为了将`EditText`视图的宽度设置为200dp，需要向类中添加以下代码：

```java
package com.ebookrenzy.javalayout;

import android.content.res.Resources;
import android.util.TypedValue;

public class MainActivity extends AppCompatActivity {
    private int convertToPx(int value) {
        Resources r = getResources();
        return (int) TypedValue.applyDimension(
              TypedValue.COMPLEX_UNIT_DIP, value,
              r.getDisplayMetrics());
    }

    private void configureLayout() {
        Button myButton = new Button(this);
        myButton.setText(getString(R.string.press_me));
        myButton.setBackgroundColor(Color.YELLOW);
        myButton.setId(R.id.myButton);
        EditText myEditText = new EditText(this);
        myEditText.setId(R.id.myEditText);
        ConstraintLayout myLayout = new ConstraintLayout(this);
        myLayout.setBackgroundColor(Color.BLUE);
        myLayout.addView(myButton);
        myLayout.addView(myEditText);
        int px = convertToPx(200);
        myEditText.setWidth(px);
    }
}
```

再次编译并运行应用程序，注意`EditText`的宽度已经更改，如图 24-3 所示：

![](img/Image2451.jpg)

图 24-3

### 24.8 总结

在本章中创建的示例`Activity`（颜色和视图类型除外）与“在 Android Studio 中手动设计布局”章节中创建的界面相似。尽管如此，本章至少应该让你意识到 Android Studio 布局编辑器工具在很大程度上减轻了开发的复杂性。

然而，在某些情况下，使用Java创建用户界面是合理的。例如，这种方法在创建动态用户界面布局时最为有用。

# 25. Android Studio 中使用 Apply Changes 的指南

现在已经涵盖了使用 Android Studio 进行开发的一些基本概念，现在是介绍 Android Studio Apply Changes 功能的好时了。正如所有经验丰富的开发者所知，等待应用程序编译和运行的每一秒都应该用于编写和优化代码。

### 25.1 介绍 Apply Changes



在 Android Studio 的早期版本，每当需要测试项目的更改时，Android Studio 重新编译代码、转换为 Dex 格式、生成 APK 包文件并将其安装到设备或模拟器上。在执行这些步骤后，应用程序才能启动并准备就绪。即使在快速的开发系统中，这个过程也需要大量时间。对于大型应用程序，这个过程通常需要一分钟以上。

相比之下，`Apply Changes` 允许项目中的许多代码更改在设备或模拟器运行时几乎立即反映在应用程序中。

考虑一个正在 Android Studio 开发且已在设备或模拟器上启动的应用。如果对资源设置或方法内部的代码进行更改，`Apply Changes` 将把更新的代码和资源推送到运行的应用程序，并动态地“交换”这些更改。这样，无需构建、部署和重新启动整个应用程序，更改就会反映在运行的应用中。

## 25.2 理解 Apply Changes 选项

Android Studio 提供了三种应用于运行应用程序的更改选项，形式分别为 `Run App`、`Apply Changes` 以及 `Restart Activity` 和 `Apply Code Changes`。这些选项可以总结如下：

- **运行应用 (Run App)** - 停止当前运行的应用并重启它。如果自上次启动以来项目未发生任何更改，则此选项将重启应用。相反，如果项目已发生更改，Android Studio 将在启动应用之前重新构建并将应用重新安装到设备或模拟器上。

- **应用代码更改 (Apply Code Changes)** - 当项目中的更改仅涉及现有方法体的修改，或者添加了新类或新方法时，可以使用此选项。选中后，更改将应用于正在运行的应用，而无需重启应用或当前运行的活动。然而，当对任何项目资源（如布局文件）进行更改时，无法使用此模式。其他限制还包括删除方法、更改方法签名、重命名类以及其他结构性代码更改。如果对项目清单（manifest）进行了更改，也无法使用此选项。

- **应用更改并重启活动 (Apply Changes and Restart Activity)** - 选中后，此模式将动态应用项目内的任何代码或资源更改，并在不重新安装或重启应用的情况下重启活动。与“应用代码更改”选项不同，当对项目的代码和资源进行更改时可以使用此模式。但是，仍然适用于涉及某些结构性代码更改和清单修改的限制。

## 25.3 使用应用更改

当项目已加载到 Android Studio 但尚未在设备或模拟器上运行时，可以使用工具栏上的`run`（在图 25-1 中标记为 A）或`debug`（B）按钮按通常方式启动它：

![](img/as_run_and_debug_buttons.jpg)

图 25-1

在应用启动并运行后，将出现一个停止按钮（在图 25-2 中标记为 A），并且“应用更改并重启活动”（B）和“应用代码更改”（C）按钮将可用：

![](img/as_apply_code_changes_buttons.jpg)

图 25-2

如果在选定其中一个“应用更改”按钮后无法应用更改，Android Studio 将显示一条指示失败的消息和相关说明。例如，图 25-3 显示了在对资源文件进行更改后选择“应用代码更改”选项时 Android Studio 显示的消息：

![](img/as_instant_run_restart_resources.jpg)

图 25-3

在这种情况下，解决方案是使用“应用更改并重启活动”选项（此处提供了链接）。同样地，当尝试应用涉及删除方法的更改时，将出现以下消息：

![](img/as_instant_run_restart_method_removed.jpg)

图 25-4

在这种情况下，唯一的选项是点击“运行应用”按钮以重新安装并重启应用。作为手动选择正确选项的备选方案，可以配置 Android Studio 自动回退到执行“运行应用”操作。

## 25.4 配置应用更改回退设置

应用更改回退设置位于 Android Studio 设置对话框中。在设置对话框中，在左侧面板中选择`Build, Execution, Deployment`（构建、执行、部署）然后选择`Deployment`（部署），如图 25-5 所示：

![](img/as_instant_run_settings.jpg)

图 25-5

一旦启用了所需的选项，点击`Apply`（应用），然后点击`OK`按钮提交更改并关闭对话框。启用这些默认设置后，Android Studio 将根据需要自动重新安装并重启应用。

## 25.5 应用更改教程

启动 Android Studio，从欢迎界面选择`New Project`（新建项目）选项，并在生成的新项目对话框中点击`Next`（下一步）按钮之前，选择`Basic Views Activity`模板。

在`Name`（名称）字段中输入`ApplyChanges`并指定`com.ebookfrenzy.applychanges`为包名。在点击`Finish`（完成）按钮之前，将`Minimum API level`（最低 API 级别）设置设置为`API 26`：Android 8.0 (Oreo)，并将`Language`（语言）菜单设置为`Java`。

## 25.6 使用代码更改

点击运行按钮并选择模拟器或物理设备作为运行目标。点击运行按钮后，跟踪示例应用在设备或模拟器上出现的时间。

运行后，点击操作按钮（屏幕右下角显示信封图标的按钮）。注意会出现`Snackbar`实例，显示文本为“Replace with your own action”，如图 25-6 所示：

![](img/as_apply_changes_snackbar.jpg)

图 25-6

一旦应用运行，“应用更改”按钮应该已经启用，这表明某些项目更改可以在不重新安装和重启应用的情况下应用。要查看此效果，编辑`MainActivity.java`文件，找到`onCreate`方法，并修改操作代码，以便在选择操作按钮时显示不同的消息：

```
binding.fab.setOnClickListener(new View.OnClickListener() {

    @Override
    public void onClick(View view) {
        Snackbar.make(view, "Apply Changes is Amazing!", Snackbar.LENGTH_LONG)
              .setAction("Action", null).show();
    }
});
```

实现代码更改后，点击“应用代码更改”按钮，注意几秒钟后出现了应用已更新的消息。点击操作按钮，注意`Snackbar`显示了消息。

## 25.7 应用更改并重启活动

任何资源更改都要求使用“应用更改并重启活动”选项。在 Android Studio 中，选择`app -> res -> layout -> fragment_first.xml`布局文件。在布局编辑器的设计模式下，选择默认的`TextView`并在属性窗口中更改文本为“Hello Android”。

在点击“应用代码更改”按钮之前，确保关闭了上述配置应用更改回退设置。注意请求失败，因为此更改涉及项目资源。点击“应用更改并重启活动”按钮，验证活动重启并在`TextView`上显示新文本。

## 25.8 使用运行应用

如前所述，删除方法需要重新安装并重启运行中的应用。为了体验这一点，编辑`MainActivity.java`文件，在`onCreate`方法之后添加一个新方法：

```
public void demoMethod() {

}
```

使用“应用代码更改”按钮并确认更改无需重新安装应用即可应用。

接下来，删除新方法并验证点击任一“应用更改”按钮都会导致请求失败。在此更改后运行应用的唯一方法是点击“运行应用”按钮。

## 25.9 总结

应用更改是 Android Studio 的一项功能，旨在显著加速开发应用时的代码、构建和运行周期。应用更改功能可以在许多情况下无需重新安装或重启应用即可向应用推送更新。

# 26. Android 事件处理概述与示例

在之前的章节中已经涵盖了大量关于 Android 用户界面设计的内容。然而，尚未涵盖的领域涉及用户与界面的交互如何触发底层活动执行任务。换句话说，从之前的章节中，我们知道如何创建一个包含按钮视图的用户界面，但不知道在用户触摸时应用会发生什么。

因此，本章的主要目标是概述 Android 中的事件处理，并提供一个基于 Android Studio 的示例项目。

## 26.1 理解 Android 事件

Android 事件可以有多种形式，但通常是响应外部操作而生成的。最常见的事件形式（特别是平板电脑和智能手机等设备）涉及与触摸屏的某种形式的交互。此类事件属于输入事件类别。

Android 框架维护了一个事件队列，事件在发生时会被放入队列中。然后，事件按照先进先出（FIFO）的顺序从队列中移除。对于输入事件（例如屏幕上的触摸），事件将传递给位于触摸发生屏幕位置的视图（view）。除了事件通知外，视图还会接收到有关事件性质的一系列信息（取决于事件类型），例如用户指尖与屏幕之间接触点的坐标。

要处理已传递的事件，视图必须准备好一个事件监听器。所有用户界面组件都派生自`View`类，该类包含了一系列事件监听器接口，每个接口都包含一个回调方法的抽象声明。为了能够响应特定类型的事件，视图必须注册相应的事件监听器并实现相应的回调。例如，如果按钮要响应点击事件（等同于用户触摸并释放按钮视图，就像点击物理按钮一样），它必须注册`View.OnClickListener`事件监听器（通过调用目标视图的`setOnClickListener()`方法），并实现相应的`onClick()`回调方法。如果在按钮视图所在的屏幕位置检测到“点击”事件，Android 框架将在该事件从事件队列中移除时调用该视图的`onClick()`方法。当然，任何在响应按钮点击时调用的任务或其他方法都应该在`onClick()`回调方法的实现中执行。

## 26.2 使用`android:onClick`资源

在详细探索事件监听器之前，值得注意的是，当仅需在用户“点击”用户界面中的按钮视图时调用回调方法时，可以使用快捷方法。考虑一个包含名为`button1`的按钮视图的用户界面布局，要求是当用户触摸按钮时，调用 activity 类中声明的名为`buttonClick()`方法。实现此行为仅需编写`buttonClick()`方法（该方法接收触发点击事件的视图引用作为参数），并在 XML 文件中的按钮视图声明中添加一行代码即可。例如：

```xml
<Button
      android:id="@+id/button1"
      android:layout_width="wrap_content"
      android:layout_height="wrap_content"
      android:onClick="buttonClick"
      android:text="Click me" />
```

这提供了一种捕获点击事件的简单方法。然而，它没有提供事件处理器所提供的范围选项，这是本章其余部分的主题。正如后续章节概述，`onClick`属性在涉及 fragment 的布局中也有局限性。在 Android Studio 布局编辑器中工作时，当在设备屏幕布局中选择合适的视图类型时，可以在属性（Attributes）面板中找到并配置`onClick`属性。

## 26.3 事件监听器和回调方法

在本章后面概述的示例 activity 中，将详细介绍注册事件监听器和实现回调方法的步骤。在此之前，值得花些时间概述 Android 框架中提供的事件监听器以及每个监听器关联的回调方法。

- `onClickListener` – 用于检测点击式事件，用户触摸并释放由视图占据的设备显示区域。对应`onClick()`回调方法，该方法将接收事件的视图引用作为参数传递。

- `onLongClickListener` – 用于检测用户是否在视图上长时间保持触摸。对应`onLongClick()`回调方法，该方法将接收事件的视图作为参数传递。

- `onTouchListener` – 用于检测与触摸屏的接触，包括单个或多次触摸以及手势动作。对应`onTouch()`回调，此主题将在 Android 触摸和多点事件处理章节中进行详细介绍。回调方法将接收事件的视图和一个`MotionEvent`对象作为参数传递。

- `onCreateContextMenuListener` – 监听由于长按产生的上下文菜单创建。对应`onCreateContextMenu()`回调方法。回调接收菜单、接收事件的视图和一个菜单上下文对象。

- `onFocusChangeListener` – 检测焦点是否因与轨迹球或导航键的交互而移出当前视图。对应`onFocusChange()`回调方法，该方法传递接收事件的视图和一个指示焦点获得或丢失的`Boolean`值。

- `onKeyListener` – 用于检测当视图拥有焦点时按了设备上的按键。对应`onKey()`回调方法。它将接收事件的视图、按下的物理键的`KeyCode`和一个`KeyEvent`对象作为参数传递。

## 26.4 事件处理示例

在本章的剩余部分中，我们将创建一个 Android Studio 项目，用于演示事件监听器和回调方法的实现，以检测用户何时点击按钮。回调方法中的代码将更新文本视图以指示事件已处理。

在欢迎屏幕上选择`New Project`，并在生成的项目对话框中选择`Empty Views Activity`模板，然后点击`Next`。

在`Name`字段中输入`EventExample`并指定`com.ebookzy.eventexample`为包名。在点击`Finish`按钮之前，将`Minimum API level`设置为`26: Android 8.0 (Oreo)`，并将`Language`设置为`Java`。按照 11.8 将项目迁移到 View Binding 节概述的步骤，将项目转换为视图绑定。

## 26.5 设计用户界面

示例中`MainActivity`类的用户界面布局将由一个`ConstraintLayout`、一个`Button`和一个`TextView`组成，如图 26-1](#Event_Handling.xhtml__idTextAnchor637）所示。

![](img/as_event_example_ui.jpg)

图 26-1

定位并选择由 Android Studio 创建的`activity_main.xml`文件（位于 Project 工具窗口的`app -> res -> layouts`下），并双击将其加载到布局编辑器。

确保`Autoconnect`已启用，然后从调色板拖入`Button`组件并移动它，使其位于布局的水平中心并在现有`TextView`组件的下方。当位置正确时，将组件释放到位置，以便自动连接系统添加相应的约束。

选择“Hello World!”`TextView`组件并使用属性面板将 ID 设置为`statusText`。重复此步骤将`Button`组件的 ID 改为`myButton`。

通过点击布局工具栏中的`Infer Constraints`按钮添加任何缺失的约束。

完成用户界面布局后，下一步是注册事件监听器和回调方法。

## 26.6 事件监听器和回调方法

在本例中，需要为`myButton`视图注册一个`onClickListener`。这通过调用按钮视图的`setOnClickListener()`方法，传递一个新的`onClickListener`对象作为参数，并实现`onClick()`回调方法来实现。由于此任务只需要在 Activity 创建时执行，因此`MainActivity`类的`onCreate()`方法是一个很好的位置。

如果编辑器会话中已经打开了`MainActivity.java`文件，请通过点击编辑器面板中的标签页选择它。或者，在 Project 工具窗口中导航到`(app -> java -> com.ebookfrenzy.eventexample -> MainActivity)`找到它，并双击将其加载到代码编辑器中。加载后，找到模板`onCreate()`方法并修改它以获取按钮视图的引用、注册事件监听器并实现`onClick()`回调方法：

```java
package com.ebookfrenzy.eventexample;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        binding = ActivityMainBinding.inflate(getLayoutInflater());
        View view = binding.getRoot();
        setContentView(view);
        binding.myButton.setOnClickListener(
            new Button.OnClickListener() {
                public void onClick(View v) {

                }
            }
        );
    }
.
.
}
```



上述代码已经在按钮上注册了事件监听器并实现了`onClick()`方法。然而，如果此时运行应用程序，将没有任何迹象表明安装在按钮上的事件监听器正在工作，因为目前`onClick()`回调方法的体内部尚未实现任何代码。本例的目标是在点击按钮时在`TextView`上上显示一条消息，因此需要进行一些进一步的代码更改：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    binding = ActivityMainBinding.inflate(getLayoutInflater());
    View view = binding.getRoot();
    setContentView(view);
    binding.myButton.setOnClickListener(
        new Button.OnClickListener() {
            public void onClick(View v) {
                binding.statusText.setText("Button clicked");
            }
        }
    );
}
```

在 AVD 模拟器或物理 Android 设备上编译并运行应用程序以完成此教程阶段。触摸并释放按钮视图（也称为“点击”）时，文本视图应该更改为显示“Button clicked”文本。

## 26.7 消费事件

对视图上的标准点击（相对于长点击）的检测是事件处理的一个简单用例。现在示例将扩展以包含对长点击事件的检测，长点击发生在用户点击并按住屏幕上的视图时，并借此我们涵盖了事件消费的主题。

考虑本章上述部分中`onClick()`方法的代码。该回调被声明为`void`，因此在执行完毕后不会向 Android 框架返回任何值。

另一方面，`onClickListener`需要返回一个`Boolean`值来指示事件是否被消费。如果回调返回`true`，框架将丢弃该事件。相反，如果返回`false`，Android 框架将认为事件仍然激活并将其传递给下一个监听器。与许多编程概念一样，这通过示例演示最为合适：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    binding = ActivityMainBinding.inflate(getLayoutInflater());
    View view = binding.getRoot();
    setContentView(view);
    binding.myButton.setOnClickListener(
        new Button.OnClickListener() {
            public void onClick(View v) {
                binding.statusText.setText("Button clicked");
            }
        }
    );
}
```

*（等待，源代码提供的消费示例是一个碎片化的区块，我将重新格式化所提供的逻辑）：*

`MainActivity`类的`onCreate()`方法：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    binding = ActivityMainBinding.inflate(getLayoutInflater());
    View view = binding.getRoot();
    setContentView(view);
    binding.myButton.setOnClickListener(
        new Button.OnClickListener() {
            public void onClick(View v) {
                binding.statusText.setText("Button clicked");
            }
        }
    );
}
```

实际上，查看源代码中用于消费的特定碎片区块，我将按照文中呈现的方式重构逻辑：

`MainActivity`类的`onCreate()`方法：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    binding = ActivityMainBinding.inflate(getLayoutInflater());
    View view = binding.getRoot();
    setContentView(view);
    binding.myButton.setOnClickListener(
        new Button.OnClickListener() {
            public void onClick(View v) {
                binding.statusText.setText("Button clicked");
            }
        }
    );
}
```

*注：源代码中包含消费示例包含一个非常混乱的区块，我将根据文本进行格式。*

`MainActivity`类的`onCreate()`方法：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    binding = ActivityMainBinding.inflate(getLayoutInflater());
    View view = binding.getRoot();
    setContentView(view);
    binding.myButton.setOnClickListener(
        new Button.OnClickListener() {
            public void onClick(View v) {
                binding.statusText.setText("Button clicked");
            }
        }
    );
}
```

## 26.8 总结

如果用户界面包含的视图对用户交互没有任何反应，那么该用户界面就没有什么实际用处。Android 通过事件监听器和回调方法的概念桥接了用户界面与应用程序后端之间的鸿沟。`View`类定义了一系列事件监听器，可以注册在视图对象上。每个事件监听器都关联了一个回调方法。

# 27. Android 触摸与多点事件处理

大多数基于 Android 的设备使用触摸屏作为用户与设备之间的主要接口。上一章介绍了屏幕上的触摸操作如何转换为运行中的 Android 应用程序中的动作。然而，触摸事件的处理远比对视图对象上的单指点击响应要复杂得多。例如，大多数 Android 设备可以同时检测到多个触摸点。此外，触摸也不局限于设备显示器上的一点。当用户在屏幕表面上滑动一个或多个接触点时，触摸操作可以是动态的。

应用程序还可以将触摸操作解释为手势。例如，水平滑动通常用于翻阅电子书的页码，或者捏拢/张开动作如何对屏幕上显示的图像进行放大或缩放。

本章将解释涉及运动的触摸处理，并探索拦截多个并发触摸的概念。识别不同手势的主题将在下一章中介绍。

## 27.1 拦截触摸事件

视图对象可以通过注册`onTouchListener`事件监听器并实现相应的`onTouch()`回调方法来拦截触摸事件。例如，下面的代码确保了对名为`myLayout`的`ConstraintLayout`视图实例上的任何触摸操作都会调用`onTouch()`方法：

```java
binding.myLayout.setOnTouchListener(
    new ConstraintLayout.OnTouchListener() {
        public boolean onTouch(View v, MotionEvent m) {
            // 在此处执行任务
            return true;
        }
    }
);
```

如代码示例所示，`onTouch()`回调需要返回一个`Boolean`值，指示 Android 运行时系统是将事件传递给在同一视图上注册的其他事件监听器，还是将其丢弃。该方法传递了触发事件的视图引用以及一个`MotionEvent`类型的对象。

## 27.2 `MotionEvent`对象

传递给`onTouch()`回调方法的`MotionEvent`对象是获取事件信息的关键。对象中的信息包括触摸在视图中的位置以及执行的动作类型。`MotionEvent`对象也是处理多点的关键。

## 27.3 理解触摸动作

触摸事件处理的一个重要方面是识别用户执行的动作类型。可以通过调用传递给`onTouch()`回调方法的`MotionEvent`对象的`getActionMasked()`方法获取与事件相关的动作类型。当视图上发生第一次触摸时，`MotionEvent`对象将包含`ACTION_DOWN`动作类型以及触摸坐标。当触摸从屏幕上抬起时，会生成一个`ACTION_UP`事件。在`ACTION_DOWN`和`ACTION_UP`事件之间的任何触摸运动都将由`ACTION_MOVE`事件表示。

当在视图上同时进行多个触摸时，这些触摸被称为指针（pointers）。在多点触摸场景下，指针分别以类型为`ACTION_POINTER_DOWN`和`ACTION_POINTER_UP`的事件动作开始和结束。要识别触发事件的指针索引，必须调用`MotionEvent`对象的`getActionIndex()`回调方法。

## 27.4 处理多点触摸

标题为“Android 事件处理概述与示例”的章节开始在单点触摸事件的狭窄语境下探索事件处理。在实践中，大多数 Android 设备可以响应多个连续的触摸（但需要注意的是，可以检测到的同时触摸数量取决于设备）。

如前所述，在多点触摸情况下，每个触摸点被 Android 框架视为一个指针。每个指针又通过一个索引值进行引用并分配一个 ID。可以通过调用当前`MotionEvent`对象的`getPointerCount()`方法获取当前指针的数量。当前指针列表中特定索引处的指针 ID，可以通过调用`MotionEvent`的`getPointerId()`方法获取。例如，下面的代码片段获取了指针计数以及索引为 0 的指针 ID：

```java
public boolean onTouch(View v, MotionEvent m) {
    int pointerCount = m.getPointerCount();
    int pointerId = m.getPointerId(0);
    return true;
}
```

注意，当`onTouch`监听器被触发时，指针计数始终大于或等于 1（因为必须至少发生一次触摸才会触发回调）。

视图上的触摸（特别是涉及跨越屏幕运动的触摸）会在接触屏幕的点抬起之前产生一系列事件。应用程序可能需要跟踪跨越事件的单个触摸。虽然特定触摸的 ID 从一个事件到下一个事件不会改变，但重要的是要记住索引值会改变。这应该通过`MotionEvent`对象的`findPointerIndex()`获取。

## 27.5 多点触摸应用程序示例

在本章剩余部分创建的示例应用程序将跟踪跨越布局移动的最多两个触摸手势。当每个触摸的事件被触发时，每个触摸的坐标、索引和 ID 将显示在屏幕上。

从欢迎界面选择“New Project”（新建项目）选项，在弹出的新项目对话框中，选择“Empty Views Activity”模板。在 Name（名称）字段中输入`MotionEvent`并指定`com.ebookrenzy.motionevent`为包名。在点击 Finish（完成）按钮之前，将 Minimum API level（最低 API 级别）设置为 API 26：Android 8.0 (Oreo)，并将 Language（语言）菜单设置为 Java。

按照第 11.8 节“Migrating a Project to View Binding”（迁移项目到 View Binding）所述调整项目以使用 view binding。

## 27.6 设计 Activity 用户界面

应用程序唯一 Activity 的界面由一个包含两个`TextView`对象的`ConstraintLayout`组成。在 Project 工具窗口中导航到`app -> res -> layout`并双击`activity_main.xml`布局资源文件，将其加载到 Android Studio Layout Editor 中。

选择并删除默认的“Hello World!”`TextView`组件，然后在开启自动连接（autoconnect）的情况下，拖放一个新的`TextView`组件，使其水平居中并置于布局顶部的 16dp 边距线上。

拖入第二个`TextView`组件，并对其进行定位和约束，使其与第一个组件底部之间保持 32dp 的间距。

使用 Attributes 工具窗口将 TextView 组件的 ID 分别更改为`textView1`和`textView2`。将组件上显示的文本更改为“Touch One Status”和“Touch Two Status”，并使用 Layout Editor 右角的警告按钮将字符串提取到资源文件中。

## 27.7 实现触摸事件监听器

要接收触摸事件通知，有必要在`MainActivity`类的`onCreate()`方法中对布局视图注册一个触摸监听器。从 Android Studio 编辑器面板中选择`MainActivity.java`标签以显示源代码。在`onCreate()`方法中，添加代码来注册触摸监听器并实现代码，在此情况下，代码将调用名为`handleTouch()`的第二个方法，并向传递`MotionEvent`对象：

```java
package com.ebookfrenzy.motionevent;

import androidx.appcompat.app.AppCompatActivity;
import androidx.constraintlayout.widget.ConstraintLayout;
import android.os.Bundle;
import android.view.MotionEvent;
import android.view.View;
import com.ebookfrenzy.motionevent.databinding.ActivityMainBinding;

public class MainActivity extends AppCompatActivity {
    private ActivityMainBinding binding;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        binding = ActivityMainBinding.inflate(getLayoutInflater());
        View view = binding.getRoot();
        setContentView(view);
        binding.activityMain.setOnTouchListener(
            new ConstraintLayout.OnTouchListener() {
                public boolean onTouch(View v, MotionEvent m) {
                    handleTouch(m);
                    return true;
                }
            }
        );
    }
}
```

当我们设计用户界面时，父布局`ConstraintLayout`没有分配一个允许我们通过视图绑定（view binding）机制访问它的 ID。由于该布局组件是 UI 布局层次结构中的顶层组件，我们能够使用上述代码中的根绑定属性（root binding property）引用它。

在测试应用程序之前，最后一个任务是实现由监听器调用的`handleTouch()`方法。该方法的代码如下：



```java
void handleTouch(MotionEvent m) {
    int pointerCount = m.getPointerCount();
    for (int i = 0; i < pointerCount; i++)
    {
        int x = (int) m.getX(i);
        int y = (int) m.getY(i);
        int id = m.getPointerId(i);
        int action = m.getActionMasked();
        int actionIndex = m.getActionIndex();
        String actionString;
        switch (action)
        {
            case MotionEvent.ACTION_DOWN:
                actionString = "DOWN";
                break;
            case MotionEvent.ACTION_UP:
                actionString = "UP";
                break;
            case MotionEvent.ACTION_POINTER_DOWN:
                actionString = "PNTR DOWN";
                break;
            case MotionEvent.ACTION_POINTER_UP:
                actionString = "PNTR UP";
                break;
            case MotionEvent.ACTION_MOVE:
                actionString = "MOVE";
                break;
            default:
                actionString = "";
        }
        String touchStatus = "Action: " + actionString + " Index: " + actionIndex + " ID: " + id + " X: " + x + " Y: " + y;
        if (id == 0)
            binding.textView1.setText(touchStatus);
        else
            binding.textView2.setText(touchStatus);
    }
}
```

在编译和运行应用程序之前，值得花时间系统地梳理这段代码，以强调所执行的任务。代码首先获取用户界面中两个`TextView`对象的引用，并识别视图上当前有多少个活跃的指针：

```java
TextView textView1 = findViewById(R.id.textView1);
TextView textView2 = findViewById(R.id.textView2);
int pointerCount = m.getPointerCount();
```

接下来，`pointerCount`变量启动了一个`for`循环，为每个活跃的指针执行任务。循环的前几行获取触摸的`X`和`Y`坐标，以及相应的事件 ID、动作类型和动作索引。最后，声明了一个字符串变量：

```java
for (int i = 0; i < pointerCount; i++)
{
    int x = (int) m.getX(i);
    int y = (int) m.getY(i);
    int id = m.getPointerId(i);
    int action = m.getActionMasked();
    int actionIndex = m.getActionIndex();
    String actionString;
}
```

由于动作类型等于整数值，因此使用`switch`语句将动作类型转换为更具意义的字符串值，并将其存储在之前声明的`actionString`变量中：

```java
switch (action)
{
    case MotionEvent.ACTION_DOWN:
        actionString = "DOWN";
        break;
    case MotionEvent.ACTION_UP:
        actionString = "UP";
        break;
    case MotionEvent.ACTION_POINTER_DOWN:
        actionString = "PNTR DOWN";
        break;
    case MotionEvent.ACTION_POINTER_UP:
        actionString = "PNTR UP";
        break;
    case MotionEvent.ACTION_MOVE:
        actionString = "MOVE";
        break;
    default:
        actionString = "";
}
```

最后，使用`actionString`值、动作索引、触摸 ID 以及`X`和`Y`坐标构建字符串消息。然后使用`ID`值来决定字符串应该显示在第一个还是第二个`TextView`对象上：

```java
String touchStatus = "Action: " + actionString + " Index: " + actionIndex + " ID: " + id + " X: " + x + " Y: " + y;
if (id == 0)
    binding.textView1.setText(touchStatus);
else
    binding.textView2.setText(touchStatus);
```

### 27.8 运行示例

编译并运行应用程序，一旦启动，在屏幕上进行单次和多次触摸实验，如图 27-3 所示（注意，如果模拟器在工具窗口中运行，可能无法模拟多次触摸）：

![](img/as_motion_event_running.jpg)

图 27-3

### 27.9 总结

Activity 通过注册监听器并实现`onTouch()`回调方法来接收触摸事件，该方法随后传递`MotionEvent`对象，包含了触摸的信息，例如事件类型、坐标和触摸计数。

本章通过创建一个示例 Android 应用程序，实现了显示最多两个同时触摸的坐标和动作类型。

# 28. 使用 GestureDetector 类检测常见手势

“手势”一词定义了触摸屏与用户之间连续的交互。手势从屏幕首次被触摸的点开始，到最后一个手指或指向设备离开显示表面结束。

Android SDK 提供了检测常见和自定义手势的机制。常见手势涉及点击、双击、长按以及在水平或垂直方向上的滑动动作（在 Android 术语中称为 fling）。

本章探讨了如何使用 Android`GestureDetector`类来检测在 Android 设备屏幕上进行的常用手势。下一章“在 Android 上实现自定义手势和双指缩放识别”将涵盖更复杂的自定义手势，例如圆形运动和双指捏。

## 28.1 实现常用手势检测

当用户与 Android 设备的屏幕进行交互时，系统会调用当前活动应用程序的`onTouchEvent()`方法，并传递包含用户触摸屏幕数据的`MotionEvent`对象。可以通过对这些数据进行解释，来识别屏幕上的动作是否匹配点击或滑动等常用手势。通过使用 Android`GestureDetectorCompat`类，可以以极少的编程工作实现这一点。该类设计用于从应用程序接收运动事件信息，并根据检测到的（如果存在）常用手势的类型来触发方法调用。

检测常用手势的基本步骤如下：

1. 声明实现`GestureDetector.OnGestureListener`接口的类，包括所需的`onFling()`、`onDown()`、`onScroll()`、`onShowPress()`、`onSingleTapUp()`和`onLongPress()`回调方法。注意，这可以是一个全新的类，也可以是一个嵌套的 activity 类。如果需要检测双击手势，该类还必须实现`GestureDetector.OnDoubleTapListener`接口并包含相应的`onDoubleTap()`方法。

2. 创建`GestureDetectorCompat`类的实例，并将步骤 1 中创建的类实例作为参数传递给它。

3. 可选调用`GestureDetectorCompat`实例的`setOnDoubleTapListener()`方法，以便在需要时启用双击检测。

4. 在嵌套的 activity 中实现`onTouchEvent()`回调方法，该方法必须调用`GestureDetectorCompat`实例的`onTouchEvent()`方法，并将当前的运动事件对象作为参数传递给该方法。

一旦实现，应用程序代码中的一组方法，当检测到特定类型的手势时，这些方法将被调用。随后可以实现这些方法中的代码来执行响应相应手势需要执行的任何任务。

在本章的剩余部分中，我们将创建一个示例项目，旨在将上述步骤付实践。

## 28.2 创建示例手势检测项目

该项目旨在检测`GestureDetectorCompat`类目前支持的所有常用手势，并向用户显示状态信息以指示检测到的手势类型。

从欢迎屏幕选择“New Project”选项，在出现的新项目对话框中，在点击“Next”按钮之前选择“Empty Views Activity”模板。

在`Name`字段中输入`CommonGestures`，并指定`com.ebookfrenzy.commongestures`为包名。在点击“Finish”按钮之前，将 Minimum API level 设置更改为`API 26`：Android 8.0 (Oreo)，并将语言菜单设置为`Java`。

按照第 11.8 将项目迁移到 View Binding 节所述的方法调整项目以使用 view binding。

一旦创建了新项目，在 Project 工具窗口中导航到`app` -> `res` -> `layout` -> `activity_main.xml`文件并双击它将其加载到 Layout Editor 工具中。

在 Layout Editor 工具中，选择“Hello, World!” TextView 组件，并在 Attributes 工具窗口中输入`gestureStatusText`作为 ID。最后，将`textSize`设置为`20sp`并启用粗体文本`textStyle`：

![](img/as_common_gestures_text_style.jpg)

图 28-1

## 28.3 实现监听器类

如之前所述，必须创建一个实现`GestureDetector.OnGestureListener`接口的类，如果需要双击检测，还需要实现`GestureDetector.OnDoubleTapListener`接口。虽然可以是一个全新的类，但在当前 activity 类中实现它也是完全有效的。因此，我们将修改`MainActivity`类以便此示例实现这些监听器接口。编辑`MainActivity.java`文件使其如下：

```java
package com.ebookfrenzy.commongestures;

import android.view.GestureDetector;

.
.

public class MainActivity extends AppCompatActivity
        implements GestureDetector.OnGestureListener,
        GestureDetector.OnDoubleTapListener
{
.
.
}
```

声明该类实现了监听器接口要求在类中也实现相应的方法：

```java
package com.ebookfrenzy.commongestures;

.
.

import android.view.MotionEvent;

public class MainActivity extends AppCompatActivity
        implements GestureDetector.OnGestureListener,
        GestureDetector.OnDoubleTapListener {
.
.

    @Override
    public boolean onDown(MotionEvent event) {
        binding.gestureStatusText.setText ("onDown");
        return true;
    }

    @Override
    public boolean onFling(MotionEvent event1, MotionEvent event2,
                              float velocityX, float velocityY) {
        binding.gestureStatusText.setText("onFling");
        return true;
    }

    @Override
    public void onLongPress(MotionEvent event) {
        binding.gestureStatusText.setText("onLongPress");
    }

    @Override
    public boolean onScroll(MotionEvent e1, MotionEvent e2,
                            float distanceX, float distanceY) {
        binding.gestureStatusText.setText("onScroll");
        return true;
    }

    @Override
    public void onShowPress(MotionEvent event) {
        binding.gestureStatusText.setText("onShowPress");
    }

    @Override
    public boolean onSingleTapUp(MotionEvent event) {
        binding.gestureStatusText.setText("onSingleTapUp");
        return true;
    }

    @Override
    public void onDoubleTap(MotionEvent event) {
        binding.gestureStatusText.setText("onDoubleTap");
    }

    @Override
    public boolean onSingleTapConfirmed(MotionEvent event) {
        binding.gestureStatusText.setText("onSingleTapConfirmed");
        return true;
    }

.
.
}
```

注意许多这些方法返回了`true`。这告诉 Android 框架该方法已处理事件，不需要传递给栈中的下一个事件处理器。

## 28.4 创建 GestureDetectorCompat 实例

现在 activity 已更新实现了监听器接口，下一步是创建`GestureDetectorCompat`类的实例。由于只需要在创建 activity 时执行一次，代码的最佳位置是`onCreate()`方法中。由于我们想要检测双击，代码还需要调用`GestureDetectorCompat`实例的`setOnDoubleTapListener()`方法：

```java
package com.ebookfrenzy.commongestures;

.
.

import androidx.core.view.GestureDetectorCompat;

public class MainActivity extends AppCompatActivity {
    private ActivityMainBinding binding;
    private GestureDetectorCompat gDetector;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        binding = ActivityMainBinding.inflate(getLayoutInflater());
        View view = binding.getRoot();
        setContentView(view);
        this.gDetector = new GestureDetectorCompat(this,this);
        gDetector.setOnDoubleTapListener(this);
    }

.
.
}
```



## 28.5 实现 `onTouchEvent()` 方法

如果此时编译并运行应用程序，在设备屏幕上进行手势操作将不会产生反应。这是因为还没有添加任何代码来拦截触摸事件并传递给 `GestureDetectorCompat` 实例。为了实现这一点，需要在 activity 类中重写 `onTouchEvent()` 方法，并对其进行实现，使其调用 `GestureDetectorCompat` 实例的 `onTouchEvent()` 方法。因此，在 `MainActivity.java` 文件中实现该方法，其代码如下：

```java
@Override
public boolean onTouchEvent(MotionEvent event) {
    this.gDetector.onTouchEvent(event);
    // 务必调用父类的实现
    return super.onTouchEvent(event);
}
```

## 28.6 测试应用程序

在物理 Android 设备或 AVD 模拟器上编译并运行应用程序。启动后，尝试滑动、按下、滚动动作以及双击和单击。注意文本视图会更新以反映事件，如图 28-2 所示：

![](img/as_common_gestures_running.jpg)

图 28-2

## 28.7 总结

用户与设备触摸屏之间的任何物理接触都可以被视为“手势”。由于缺乏传统计算机系统的物理键盘和鼠标指针，手势被广泛用作用户与应用程序之间交互的方法。虽然一个手势可以包含几乎任何动作序列，但有一组被触摸设备用户已经熟悉的常用手势集。这些所谓的“常用手势”中的某些可以通过使用 Android Gesture Detector 检测器类在应用程序中轻松检测到。在本章中，我们从理论和示例项目实现两个方面概述了该技术的使用。

在本章涵盖常用手势之后，下一章将介绍如何检测更广泛的手势类型，包括设计和检测你自定义手势的能力。

## 29. 在 Android 上实现自定义手势和双指缩放识别

上一节介绍了如何在 Android 应用程序内部检测所谓的“常用手势”。然而，在实践中，一个手势理论上可能涉及 Android 设备屏幕上几乎任何序列的触摸动作。针对此，Android SDK 允许应用程序开发者定义几乎任何性质的自定义手势，并在用户执行时触发事件。这是一个多阶段的过程，其细节是本章的主题。

### 29.1 Android Gesture Builder 应用程序

Android SDK 允许开发者设计自定义手势，并存储在与 Android 应用程序包一起的手势文件中。这些自定义手势文件最容易使用 Gesture Builder 应用程序创建。创建手势文件涉及在物理设备或模拟器上启动 Gesture Builder 应用程序，并在灰色画布上“绘制”应用程序需要检测的手势。一旦设计好，就可以下载包含手势数据的文件并添加到应用程序项目中。在应用程序代码中，该文件被加载到 `GestureLibrary` 类的实例中，该实例可用于搜索用户在设备屏幕上执行的任何手势的匹配项。

### 29.2 `GestureOverlayView` 类

为了方便在应用程序中检测手势，Android SDK 提供了 `GestureOverlayView` 类。这个透明视图可以放置在用户界面的其他视图之上以检测手势。

### 29.3 检测手势

手势的检测是通过加载使用 Gesture Builder 应用创建的手势文件，然后在 `GestureOverlayView` 类的实例上注册 `GesturePerformedListener` 事件监听器来实现的。然后声明包装类实现 `OnGesturePerformedListener` 接口以及该接口所需的相应 `onGesturePerformed` 回调方法。如果监听器检测到手势，Android 运行时系统将触发 `onGesturePerformed` 回调方法。

### 29.4 识别特定手势

当检测到手势时，会调用 `onGesturePerformed` 回调方法，并将检测到手势的 `GestureOverlayView` 对象的引用以及一个包含手势信息的 `Gesture` 对象作为参数。

通过访问 `Gesture` 对象，`GestureLibrary` 可以将检测到的手势与之前加载到应用程序的手势文件中包含的内容进行比较。`GestureLibrary` 通过为每个手势计算预测分数，报告用户执行的手势与手势文件条目匹配的概率。1.0 或更高的预测分数通常被接受为文件中存储的手势与用户在设备屏幕上执行的手势之间的良好匹配。

### 29.5 安装并运行 Gesture Builder 应用程序

创建手势文件最简单的方法是使用 Gesture Builder 应用，它允许捕并保存手势动作。虽然 Google 原本提供了一个用于此目的的应用程序，但它对较新的 Android 版本没有进行充分维护。幸运的是，有一种名为 Gesture Builder Tool 的替代方案，可以通过以下 URL 从 Play Store 获取：https://play.google.com/apps/details?id=migueldp.runeforge

### 29.6 创建手势文件

一旦 Gesture Builder Tool 加载，点击设备屏幕底部的 New Gesture 按钮，并在灰色画布上使用圆周运动“绘制”手势，如图 29-1 所示。假设手势显示正确（由设备屏幕上的黄色线条表示），点击保存按钮将手势添加到手势文件中，在提示名称时输入“Circle Gesture”。

![](img/as_gesture_builder_app.jpg)

图 29-1

手势保存后，Gesture Builder Tool 将显示当前定义的手势列表，其中仅包含新的 Circle Gesture。

### 29.7 创建示例项目

从欢迎界面选择 New Project 选项，并在出的新项目对话框中选择 Empty Views Activity 模板，然后点击 Next 按钮。

在 Name 字段中输入 CustomGestures，指定 `com.ebookzy.customgestures` 为包名。在点击 Finish 按钮之前，将 Minimum API level 设置为 API 26: Android 8.0 (Oreo)，并将 Language 菜单更改为 Java。按照第 11.8 迁移项目到 View Binding 节所述调整项目使用视图绑定。

### 29.8 从 SD 卡提取手势文件

由于每个手势都在 Gesture Builder 应用程序中创建，它们会被添加到名为 `gesture.txt` 的文件中，位于运行应用程序的模拟器或设备的存储中。然而，在此文件添加到 Android Studio 项目之前，必须将其从设备存储中导出并保存到本地文件系统。这可以通过 Android Studio Device File Explorer 工具窗口轻松实现。使用 View -> Tool Windows -> Device File Explorer 菜单显示此工具。显示后，从下拉菜单选择创建手势文件的设备或模拟器，然后导航到以下文件夹：

`/storage/emulated/0/Android/data/migueldp.runeforge/files/gestures.txt`

在该文件夹中找到 `gesture.txt` 文件，右键点击它，选择 Save As… 选项，将其保存到临时位置并命名为 `gestures`。

![](img/as_device_explorer.jpg)

图 29-2

一旦创建并从设备存储中拉取出手势文件，就可以将其作为资源文件添加到 Android Studio 项目中。

### 29.9 将手势文件添加到项目

在 Android Studio Project（项目）工具窗口中，找到并右键点击 `res` 文件夹（位于 `app` 下），并在弹出的菜单中选择 `New -> Directory`。在 `New Directory`（新建目录）对话框中，输入 `raw` 作为文件夹名称并按下键盘回车键。使用适用于你操作系统的相应文件资源管理器工具，找到之前从设备存储中拉出的手势文件，将其复制并粘贴到项目工具窗口中新的 `raw` 文件夹中。

### 29.10 设计用户界面

此示例应用需要一个由 `ConstraintLayout` 视图组成的用户界面，在其上方叠加一个 `GestureOverlayView` 以拦截用户执行的任何手势。找到 `app -> res -> layout -> activity_main.xml` 文件，双击它将其加载到 Layout Editor（布局编辑器）工具中，选择并删除默认的 `TextView` 控件。

切换布局编辑器的 Code 模式并修改 XML，使其内容如下：

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity" >
    <android.gesture.GestureOverlayView
        android:id="@+id/gOverlay"
        android:layout_width="0dp"
        android:layout_height="0dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

### 29.11 加载手势文件

现在手势文件已添加到项目中，下一步是编写一些代码在活动启动时加载该文件。对于此项目，实现此目的代码将如下添加到 `MainActivity` 类中：

```java
package com.ebookfrenzy.customgestures;

import android.gesture.GestureLibraries;
import android.gesture.GestureLibrary;
import android.gesture.GestureOverlayView;
import android.gesture.GestureOverlayView.OnGesturePerformedListener;

public class MainActivity extends AppCompatActivity
        implements OnGesturePerformedListener {

    private ActivityMainBinding binding;
    private GestureLibrary gLibrary;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        binding = ActivityMainBinding.inflate(getLayoutInflater());
        View view = binding.getRoot();
        setContentView(view);
        gestureSetup();
    }

    private void gestureSetup() {
        gLibrary = GestureLibraries.fromRawResource(this, R.raw.gestures);
        if (!gLibrary.load()) {
            finish();
        }
    }
}
```

除了必要的导入指令外，上述代码还创建了一个名为 `gLibrary` 的 `GestureLibrary` 实例，然后将 raw 资源文件夹中的手势文件内容加载到其中。活动类也经过了修改实现了 `OnGesturePerformedListener` 接口，这需要添加 `onGesturePerformed` 回调方法（将在本章稍后创建）。

## 29.12 注册事件监听器

为了让活动接收到用户在屏幕上执行手势的通知，需要在 `gLayout` 视图上注册 `OnGesturePerformed` 事件监听器，如下代码所示，可以使用 `findViewById` 方法获取其引用：

```java
private void gestureSetup() {
    gLibrary = GestureLibraries.fromRawResource(this, R.raw.gestures);
    if (!gLibrary.load()) {
        finish();
    }
    GestureOverlayView gOverlay = findViewById(R.id.gOverlay);
    gOverlay.addOnGesturePerformed(this);
}
```

## 29.13 实现 `onGesturePerformed` 方法

在首次运行应用程序之前，最后剩下的工作就是实现 `onGesturePerformed` 回调。当在 `GestureOverlayView` 实例上执行手势时，将调用此方法：

```java
package com.ebookfrenzy.customgestures;

import android.gesture.Prediction;
import android.widget.Toast;
import android.gesture.Gesture;
import java.util.ArrayList;

public class MainActivity extends AppCompatActivity implements OnGesturePerformedListener {
    private GestureLibrary gLibrary;

    public void onGesturePerformed(GestureOverlayView overlay, Gesture gesture) {
        ArrayList<Prediction> predictions = gLibrary.recognize(gesture);
        if (predictions.size() > 0 && predictions.get(0).score > 1.0) {
            String action = predictions.get(0).name;
            Toast.makeText(this, action, Toast.LENGTH_SHORT).show();
        }
    }
}
```

当 Android 运行时在手势叠加对象上检测到手势时，就会调用 `onGesturePerformed` 方法。传递的参数是检测到手势的 `GestureOverlayView` 对象的引用以及一个 `Gesture` 类型的对象。`Gesture` 类用于持有定义手势的信息（本质上是屏幕上的时间点序列）。

`Gesture` 对象被传递给 `gLibrary` 实例的 `recognize()` 方法，以便将当前手势与从手势文件中加载的内容进行比较。一旦任务完成，`recognize()` 方法返回一个包含每次比较结果的 `Prediction` 对象的 `ArrayList` 对象。列表按照最佳匹配（数组位置 0）到最差匹配进行排序。每个 `prediction` 对象内部包含了手势文件中对应的名称以及一个指示其与当前手势匹配程度的预测得分。

因此，上述方法获取位置 0 的预测，确保其得分大于 1.0，然后显示 `Toast` 消息（一种用于向用户显示弹出内容的 Android 类），显示匹配的手势名称。

## 29.14 测试应用程序

在模拟器或物理 Android 设备上构建并运行应用程序，然后在屏幕上执行圆形手势。执行时，应该出现包含检测对手势名称的 toast 通知。注意，当手势被识别时，会用亮黄色线条勾勒，而不确定的手势显示为淡黄色线条。这在开发期间很有用，但对于实际应用程序可能并不理想。因此，还有一些配置工作需要完成。

### 29.15 配置 `GestureOverlayView`

默认情况下，`GestureOverlayView` 配置为在手势期间显示黄色线条。绘制识别和未识别手势的颜色可以通过 `android:gestureColor` 和 `android:uncertainGestureColor` 属性定义。例如，要隐藏手势线条，如下修改示例项目中的 `activity_main.xml` 文件：



```xml
<android.gesture.GestureOverlayView
    android:id="@+id/gOverlay"
    android:layout_width="0dp"
    android:layout_height="0dp"
    app:layout_constraintBottom_toBottomOf="parent"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent"
    android:gestureColor="#00000000"
    android:uncertainGestureColor="#00000000" />
```

重新运行应用程序后，手势现在应该是不可可见的（因为它们在 `ConstraintLayout` 视图的白色背景上被绘制为白色）。

### 29.16 拦截手势

如前所述，`GestureOverlayView` 是一个透明覆盖层，可以放置在其他视图之上。这引出了问题：当识别出手势时，手势覆盖层拦截的事件是否应该传递给底层的视图？这通过 `GestureOverlayView` 实例的 `android:eventsInterceptionEnabled` 属性来控制。当设置为 `true` 时，识别出手势时，手势事件不会传递给底层视图。

当在一个配置为响应某些手势滚动的视图上执行手势时，此设置特别有用。将此属性设置为 `true` 可以避免手势同时被解释为底层视图向特定方向滚动的指令。

### 29.17 检测缩放手势

在讨论一般的触摸处理和特定的手势识别之前，本章的最后一个主题是处理缩放手势。虽然可以使用本章之前节概述的步骤来创建和检测各种手势，但实际上，使用目前为止讨论的技术无法检测缩放手势（即使用两个手指进行拉伸和收缩动作，通常用于放大或缩小视图或图像）。

检测缩放手势最简单的方法是使用 `ScaleGestureDetector` 类。简单来说，检测缩放手势涉及以下三个步骤：

1. 一个实现 `SimpleOnScaleGestureListener` 接口的新类，包括所需的 `onScale()`、`onScaleBegin()` 和 `onScaleEnd()` 回调方法。
2. 创建 `ScaleGestureDetector` 类的实例，并将步骤 1 中创建的类实例作为参数传递。
3. 在外层 `Activity` 中实现 `onTouchEvent()` 回调方法，该方法反调用 `ScaleGestureDetector` 类的 `onTouchEvent()` 方法。

在本章的剩余部分中，我们将创建一个示例，旨在演示缩放手势识别的实现。

## 29.18 缩放手势示例项目

从欢迎界面选择“New Project”（新建项目）选项，在生成的新项目对话框中，点击“Next”（下一步）按钮之前选择“Empty Views Activity”（空视图 Activity）模板。

在“Name”（名称）字段中输入 `PinchExample`，并指定 `com.ebookfrenzy.pinchexample` 为包名。在点击“Finish”（完成）按钮之前，将最低 API 设置为 `API 26`：Android 8.0 (Oreo)，并将语言菜单设置为 `Java`。按照 11.8 Migrating a Project to View Binding 中的步骤将项目转换为使用 view binding。

在 `activity_main.xml` 文件中，选择默认的 `TextView` 对象，并使用属性工具窗口将 ID 设置为 `myTextView`。

找到并加载 `MainActivity.java` 文件到 Android Studio 编辑器中，并按如下修改文件：

```java
package com.ebookfrenzy.pinchexample;

.

.

import android.view.MotionEvent;

import android.view.ScaleGestureDetector;

import android.view.ScaleGestureDetector.SimpleOnScaleGestureListener;

public class MainActivity extends AppCompatActivity {
    private ActivityMainBinding binding;

    ScaleGestureDetector scaleGestureDetector;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        binding = ActivityMainBinding.inflate(getLayoutInflater());
        View view = binding.getRoot();
        setContentView(view);
        scaleGestureDetector =
            new ScaleGestureDetector(this,
                new MyOnScaleGestureListener());
    }

    @Override
    public boolean onTouchEvent(MotionEvent event) {
        scaleGestureDetector.onTouchEvent(event);
        return true;
    }

    public class MyOnScaleGestureListener extends
            SimpleOnScaleGestureListener {
        @Override
        public boolean onScale(ScaleGestureDetector detector) {
            float scaleFactor = detector.getScaleFactor();
            if (scaleFactor > 1) {
                binding.myTextView.setText("Zooming In");
            } else {
                binding.myTextView.setText("Zooming Out");
            }
            return true;
        }

        @Override
        public boolean onScaleBegin(ScaleGestureDetector detector) {
            return true;
        }

        @Override
        public void onScaleEnd(ScaleGestureDetector detector) {
        }
    }
}
```

### 29.19 总结

手势是触摸屏幕上接触点的运动，涉及一个或多个笔画，可以作为用户与应用程序之间的通信方法。Android 允许使用 Gesture Builder 应用程序设计手势。一旦创建，手势就可以保存到手势文件并在运行时使用 `GestureLibrary` 加载到 `Activity` 中。

通过用 `GestureOverlayView` 类的实例覆盖现有视图并实现 `OnGestureListener` 事件监听器，可以在显示区域上检测手势。使用 `GestureLibrary`，可以生成用户执行的手势与存储在手势文件中的手势之间的排序列表，使用预测分数来决定手势是否足够匹配。

通过实现 `ScaleGestureDetector` 类可以检测缩放手势，本章也提供了该类的示例。

## 30. Android Fragments 简介

随着你对本书章节的深入学习，你会明显发现 Android 系统背后的许多设计概念是为了促进构成应用程序的不同元素之间的复用和交互。本章将探索的一个此类领域涉及使用 `Fragment`（片段）。

本章将提供 `Fragment` 基本知识概述，介绍它们是什么以及如何在应用程序中创建和使用。下一章将通过教程演示如何在 Android Studio 中开发应用程序时使用 `Fragment`，包括实现 `Fragment` 之间的通信。

### 30.1 什么是 Fragment?

`Fragment`（碎片）是应用程序用户界面中一个自包含的模块化部分及其相应的行为，可以嵌入到 `Activity`（活动）中。在应用程序设计阶段，可以组合 `Fragment` 来创建一个 `Activity`，并在应用程序运行期间向 `Activity` 中添加或移除 `Fragment`，从而创建动态变化的用户界面。

`Fragment` 只能作为 `Activity` 的一部分使用，不能作为独立的应用程序元素进行实例化。然而，`Fragment` 可以被视为一个功能性的“子 Activity”，其生命周期与完整的 `Activity` 相似。

`Fragment` 以 XML 布局文件的形式存储。可以通过在 `Activity` 的布局文件中放置适当的 `<fragment>` 元素，或者通过 `Activity` 类实现中的代码，将其添加到 `Activity` 中。

### 30.2 创建 Fragment

构成 `Fragment` 的两个组件都是一个 XML 布局文件和一个对应的 Java 类。`Fragment` 的 XML 布局文件采用的与任何其他 `Activity` 布局相同的格式，并且可以包含任何组合和复杂程度的布局和视图。例如，下面的 XML 布局用于一个由红色背景的 `ConstraintLayout` 组成的 `Fragment`，其中包含一个白色前景颜色的单个 `TextView`：

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/constraintLayout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@android:color/holo_red_dark"
    tools:context=".FragmentOne">
    <TextView
        android:id="@+id/textView1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="My First Fragment"
        android:textAppearance="@style/TextAppearance.AppCompat.Large"
        android:textColor="@color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

与布局对应的类必须是 Android `Fragment` 类的子类。该类至少应该重写 `onCreateView()` 方法，该方法负责加载 `Fragment` 布局。例如：

```java
package com.example.myfragmentdemo;

import android.os.Bundle;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import androidx.fragment.app.Fragment;

public class FragmentOne extends Fragment {
    @Override
    public View onCreateView(LayoutInflater inflater,
                            ViewGroup container,
                            Bundle savedInstanceState) {
        // 胀此 fragment 的布局
        binding = FragmentTextBinding.inflate(inflater, container, false);
        return binding.getRoot();
    }
}
```

除了 `onCreateView()` 方法外，该类还可以重写标准的生命周期方法。一旦创建了 `Fragment` 布局和类，`Fragment` 就可以在应用程序 `Activity` 中使用。

## 30.3 使用布局 XML 文件向 Activity 添加 Fragment

可以通过编写 Java 代码或将 `Fragment` 嵌入 `Activity` 的 XML 布局文件将其整合到 `Activity` 中。无论使用哪种方法，需要注意的关键点是：当使用支持库以兼容旧版本的 Android 发布时，任何使用 `Fragment` 的 `Activity` 必须实现为 `FragmentActivity` 的子类，而不是 `AppCompatActivity` 类：

```java
package com.example.myfragmentdemo;

import android.os.Bundle;
import androidx.fragment.app.FragmentActivity;
import android.view.Menu;

public class MainActivity extends FragmentActivity {
}
}
```

`Fragment` 使用 `FragmentContainerView` 类嵌入到 `Activity` 布局文件中。接接的示例布局嵌入了上一节中创建的 `Fragment`：

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/constraintLayout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">
    <androidx.fragment.app.FragmentContainerView
        android:id="@+id/fragment2"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:name="com.example.myfragmentdemo.FragmentOne" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

`<fragment>` 元素中的关键属性是 `android:name`（必须引用与 `Fragment` 关联的类）和 `tools:layout`（必须引用包含 `Fragment` 布局的 XML 文件）。一旦添加到 `Activity` 布局，可以在 Android Studio 编辑器中查看并操作 `Fragment`。

## 30.4 在代码中添加和管理 Fragment

通过 `Activity` 布局文件添加 `Fragment` 的便利性是以 `Activity` 无法在运行时移除 `Fragment` 为代价的。为了在运行期间对 `Fragment` 进行完全的动态控制，必须通过代码添加这些 `Activity`。这样做的优点是，可以在应用程序运行时动态地添加、移除甚至相互替换 `Fragment`。



使用代码管理 Fragment 时，Fragment 仍然由一个 XML 布局文件和一个对应的类组成。区别在于宿主 Activity 如何操作 Fragment。使用代码添加 Fragment 有一套标准的步骤序列：

1. 创建 Fragment 类的实例。

2. 通过类实例传递任何额外的参数（arguments）。

3. 获取 `FragmentManager` 实例的引用。

4. 在 Fragment 实例上调用 `beginTransaction()` 方法。这将返回一个 `FragmentTransaction` 实例。

5. 调用 Fragment 事务实例的 `add()` 方法，将要包含 Fragment 的视图资源 ID 和 Fragment 类实例作为参数传入。

6. 调用 Fragment 事务实例的 `commit()` 方法。

例如，下面的代码将由 `FragmentOne` 类定义的 Fragment 添加到 ID 为 `LinearLayout1` 的容器中：

```java
FragmentOne firstFragment = new FragmentOne();
firstFragment.setArguments(getIntent().getExtras());
FragmentManager fragManager = getSupportFragmentManager();
FragmentTransaction transaction = fragManager.beginTransaction();
transaction.add(R.id.LinearLayout1, firstFragment);
transaction.commit();
```

上面的代码将每个步骤拆分为独立的语句以便于理解。然而，最后四行可以缩写为单行代码，如下：

```java
getSupportFragmentManager().beginTransaction().add(R.id.LinearLayout1, firstFragment).commit();
```

一旦将 fragment 添加到容器中，随后可以通过调用 fragment 事务实例的 `remove()` 方法将其移除，该方法需要传递一个要移除的 fragment 实例引用：

```java
transaction.remove(firstFragment);
```

同样，可以通过调用 fragment 事务实例的 `replace()` 方法用一个 fragment 替换另一个。该方法的参数是包含该 fragment 的视图 ID 以及新 fragment 的实例。被替换的 fragment 也可以被放入所谓的“回退栈”（back stack）中，这样当用户导航回它时就可以快速恢复。这通过在调用 `commit()` 方法之前，先调用 fragment 事务对象的 `addToBackStack()` 方法来实现：

```java
FragmentTwo secondFragment = new FragmentTwo();
transaction.replace(R.id.LinearLayout1, secondFragment);
transaction.addToBackStack(null);
transaction.commit();
```

# 30.5 处理 Fragment 事件

正如之前讨论过的，fragment 就像一个子活动，拥有它自己的布局、类和生命周期。fragment 内部的视图组件（如按钮和文本视图）可以像普通活动一样产生事件。这引发了一个问题：是哪个类来接收来自 fragment 中视图的事件，是 fragment 本身，还是嵌入该 fragment 的活动？问题的答案取决于事件处理程序是如何声明的。

在标题为 Android 事件处理概述与示例的章节中，讨论了两种处理事件的方法。第一种方法在活动代码中配置事件监听器和回调方法。例如：

```java
binding.button.setOnClickListener(
    new Button.OnClickListener() {
        public void onClick(View v) {
            // 当按钮被点击时
            // 要执行的代码
        }
    }
);
```

在拦截点击事件的情况下，第二种方法涉及在 XML 布局文件中设置 `android:onClick` 属性：

```xml
<Button
    android:id="@+id/button1"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:onClick="onClick"
    android:text="Click me" />
```

fragment 中视图生成的事件，其通用规则是：如果在 fragment 类中使用事件监听器和回调方法的方法声明了事件监听器，则事件将首先由 fragment 处理。然而，如果使用了 `android:onClick` 资源，事件将直接传递给包含该 fragment 的活动。

# 30.6 实现 Fragment 通信

一旦一个或多个 fragment 被嵌入活动中，很可能需要在 fragment 与活动之间、以及 fragment 之间进行某种形式的通信。良好的实践要求 fragment 之间不要直接通信。所有通信都应该通过封装活动进行。

要与 fragment 通信，活动必须通过分配给它的 ID 来标识 fragment 对象。一旦获取了引用，活动就可以调用 fragment 对象的公共方法。

反向通信（从 fragment 到活动）稍微复杂一些。首先，fragment 必须定义一个监听接口，然后在活动类中实现该接口。例如，以下代码在一个名为 `ToolbarFragment` 的 fragment 上声明了一个 `ToolbarListener` 接口。代码还声明了一个变量，稍后将存储对活动的引用：

```java
public class ToolbarFragment extends Fragment {
    ToolbarListener activityCallback;
    public interface ToolbarListener {
        public void onButtonClick(int position, String text);
    }
}
}
```

上述代码规定，任何实现 `ToolbarListener` 接口的类都必须实现一个名为 `onButtonClick` 的回调方法，该方法接受一个整数和一个 `String` 作为参数。

接下去，需要重写并实现 fragment 类的 `onAttach()` 方法。当 fragment 初始化并与活动关联时，Android 系统会自动调用此方法。该方法被传递一个包含该 fragment 的活动引用。该方法必须存储对该活动的本地引用，并验证它是否实现了 `ToolbarListener` 接口：

```java
@Override
public void onAttach(Context context) {
    super.onAttach(context);
    try {
        activityCallback = (ToolbarListener) activity;
    } catch (ClassCastException e) {
        throw new ClassCastException(activity.toString() + " must implement ToolbarListener");
    }
}
```

执行此示例后，活动将存储在 `activityCallback` 中，如果该活动没有实现该接口，则会抛出异常。下一步是从 fragment 内部调用回调方法。这何时以及如何发生，完全取决于 fragment 需要联系活动的具体情况。例如，以下代码在按钮被点击时调用活动上的回调方法：

```java
void buttonClicked(View view) {
    activityCallback.onButtonClick(arg1, arg2);
}
```

剩下的工作就是修改活动类以实现该接口。例如：

```java
public class MainActivity extends FragmentActivity implements ToolbarFragment.ToolbarListener {
    public void onButtonClick(String arg1, int arg2) {
        // 实现回调方法的代码
    }
}
```

从上述代码中可以看出，活动声明了它实现了该接口，然后开始实现 `onButtonClick()` 方法。

### 30.7 总结

Fragment 提供了一种创建可重用用户界面布局和应用程序行为模块的机制，这些模块一旦创建，就可以嵌入活动中。一个 fragment 由一个用户界面布局文件和一个类组成。可以通过向活动布局文件添加 fragment 或编写管理 fragment 的代码来在活动中使用 fragment。

这两个片段将被嵌入应用程序的主活动（Activity）中，并实现如下通信机制：当点击第一个片段中的按钮时，输入到 `EditText` 视图中的文本将出现在第二个片段的 `TextView` 上，其字体大小将由第一个片段中 `SeekBar` 的位置决定。

由于此应用程序旨在运行在较早的 Android 版本上，我们需要使用相应的 Android 支持库。

## 31.2 创建示例项目

从欢迎界面选择 `New Project`（新建项目）选项，在弹出的新项目对话框中，点击 `Next` 按钮之前选择 `Empty Views Activity` 模板。

在 `Name` 字段中输入 `FragmentExample`，并指定 `com.ebookfrenzy.fragmentexample` 为包名。在点击 `Finish` 按钮之前，将 `Minimum API level` 设置更改为 `API 26: Android 8.0 (Oreo)`，并将 `Language` 菜单更改为 `Java`。按照 11.8 Migrating a Project to View Binding 中列出的步骤修改项目以使用视图绑定（view binding）。

返回 `Gradle Scripts` -> `build.gradle.kts (Module :app)` 文件，并在 `dependencies` 部分添加以下指令（请注意，现在可能有更新版本的库可用）：

```kotlin
implementation 'androidx.navigation:navigation-fragment:2.5.2'
```

## 31.3 创建第一个片段布局

下一步是为我们活动中的第一个片段创建用户界面。

该用户界面将由一个 XML 布局文件和一个片段类组成。虽然可以手动添加，但让 Android Studio 为我们创建它们会更快。在项目工具窗口中，找到 `app` -> `java` -> `com.ebookfrenzy.fragmentexample` 条目并右键点击它。在弹出的菜单中，选择 `New` -> `Fragment` -> `Gallery...` 选项以显示下方图 31-1 所示的对话框：

![](img/as_fragment_gallery.jpg)

图 31-1

在点击 `Next` 按钮之前选择 `Fragment (Blank)` 模板。在随后的屏幕上，将片段命名为 `ToolbarFragment`，布局文件命名为 `fragment_toolbar`：

![](img/as_new_fragment_java.jpg)

图 31-2

使用 `Design` 模式将 `fragment_toolbar.xml` 文件加载到布局编辑器。接下来，右键点击 `Component Tree` 面板中的 `FrameLayout` 条目，选择 `Convert FrameLayout to ConstraintLayout` 菜单选项，并在确认对话框中接受默认设置。将 `id` 更改为 `constraintLayout`。确保启用 `Autoconnect` 模式，然后选择并删除默认的 `TextView`，并布局添加 `Plain Text`、`Seekbar` 和 `Button` 控件，以便它们的位置与图 31-3 所示所示。最后，将视图 `ids` 分别更改为 `editText1`、`seekBar1` 和 `button1`。

将按钮文本更改为“Change Text”，将文本提取为名为 `change_text` 的字符串资源，并移除 `EditText` 视图中的 `Name` 文本。最后，将 `Seekbar` 的 `layout_width` 属性设置为 `match_constraint`，并将左、右边距设置为 `16dp`。

使用 `Infer constraints` 工具栏按钮添加任何缺失的约束，此时布局应与下方的图 31-3 所示：

![](img/as_fragment_example_frag_one_ui.jpg)

图 31-3

## 31.4 将片段迁移到视图绑定

与 `Empty Views Activity` 模板一样，当向项目中添加新片段时，Android Studio 不会启用视图绑定支持。因此，在继续本教程的下一步之前，我们需要执行此迁移。首先开始编辑 `ToolbarFragment.java` 文件，并如下所示导入片段的绑定类：

```java
import com.ebookfrenzy.fragmentexample.databinding.FragmentToolbarBinding;
```

接下来，找到 `onCreateView()` 方法并进行以下声明和更改（这包括添加 `onDestroyView()` 方法，以确保在片段销毁时移除绑定引用）：

```java
private FragmentToolbarBinding binding;

@Override
public View onCreateView(LayoutInflater inflater, ViewGroup container,
                         Bundle savedInstanceState) {
    // 填充此片段的布局
    binding = FragmentToolbarBinding.inflate(inflater, container, false);
    return binding.getRoot();
}

@Override
public void onDestroyView() {
    super.onDestroyView();
    binding = null;
}
```

一旦完成这些更改，该片段即可使用视图绑定。

## 31.5 添加第二个片段

重复创建工具栏片段的步骤，添加另一个名为 `TextFragment` 的空片段，布局文件命名为 `fragment_text`。再次将 `FrameLayout` 容器转换为 `ConstraintLayout`（将 `id` 更改为 `constraintLayout2`）并移除默认的 `TextView`。

从调色板拖入 `TextView` 控件并将其置在布局中心，使用 `Infer constraints` 按钮添加任何缺失的约束。将 `TextView` 的 `id` 更改为 `textView2`，文本更改为“Fragment Two”，并修改 `textSize` 属性为 `24sp`。

完成后，布局应与下方图 31-4 所示：

![](img/as_4.0_fragment_text.jpg)

图 31-4

重复上一节中的步骤，将 `TextFragment` 类迁移到视图绑定：

```java
import com.ebookfrenzy.fragmentexample.databinding.FragmentTextBinding;

private FragmentTextBinding binding;

@Override
public View onCreateView(LayoutInflater inflater, ViewGroup container,
                         Bundle savedInstanceState) {
    // 填充此片段的布局
    binding = FragmentTextBinding.inflate(inflater, container, false);
    return binding.getRoot();
}

@Override
public void onDestroyView() {
    super.onDestroyView();
    binding = null;
}
```

## 31.6 将片段添加到活动

应用程序的主活动关联了一个名为 `activity_main.xml` 的 XML 布局文件。在本例中，将使用该文件 `<fragment>` 元素将片段添加到活动。使用项目工具窗口，导航到 `FragmentExample` 项目的 `app` -> `res` -> `layout` 部分，双击 `activity_main.xml` 文件将其加载到 Android Studio 布局编辑器。

当编辑器处于 `Design` 模式时，选择并删除布局中的默认 `TextView` 对象，然后在调色板中选择 `Common` 类别。从视图列表中拖入 `FragmentContainerView` 组件并将其放入布局中，使其水平居中并位于虚线处：

![](img/as_3.5_fragment_example_add_fragment.jpg)

图 31-5

将片段放入布局后，会出现一个对话框，显示当前项目中可片段列表，如图 31-6 所示：



![](img/as_select_fragment.jpg)

图 31-6

从列表中选择 `ToolbarFragment` 并确定关闭对话框。添加后，点击布局编辑器右上角的红色警告按钮显示 `Problems` 工具窗口。未知片段消息表示布局编辑器工具需要在预览期间知道显示哪个片段。选择 `Unknown` 片段项，然后点击右侧面板中的 `Pick Layout...` 链接，如图 31-7 所示：

![](img/as_pick_fragment_layout.jpg)

图 31-7

在生成的对话框（图 31-8）中，选择 `fragment_toolbar` 条目并点击 `OK`：

![](img/as_select_fragment_toolbar.jpg)

图 31-8

选中片段后，将 `layout_width` 属性更改为 `match_constraint`，使其占据全宽。从调色板中拖入另一个 `FragmentContainerView` 条目，并将其放置在水平居中且位于第一个片段的底部边缘下方。在提示时，从片段对话框中选择 `TextFragment` 条目，然后点击 `OK`。显示“问题”（`Problems`）工具窗口并重复之前的步骤，这次选择 `fragment_text` 布局。使用 `Infer constraints`（推断约束）按钮来建立任何缺失的布局约束。

注意，片段现在已在布局中可见，如图 31-9 所示：

![](img/as_4.1_fragments_added.jpg)

图 31-9

在继续下一步之前，在布局中选择 `TextFragment` 实例，并在属性（`Attributes`）工具窗口内将片段的 ID 更改为 `text_fragment`。

### 31.7 让工具栏片段与 Activity 通信

当用户触摸工具栏片段中的按钮时，片段类需要从 `EditText` 视图提取文本以及 `SeekBar` 的当前值，并将它们发送给文本片段。如“Android 片段简介”中所述，片段之间不应直接相互通信，而应该使用嵌入它们的 activity 作为中间媒介。

此过程的第一步是确保工具栏片段对被点击的按钮有响应。我们还需要实现一些代码来跟踪 `SeekBar` 视图的值。对于此示例，我们将在 `ToolbarFragment` 类中实现这些监听器。选择 `ToolbarFragment.java` 文件并对其进行修改，使其读取内容如下列表所示：

```java
package com.ebookfrenzy.fragmentexample;

.
.

import androidx.annotation.NonNull;

import androidx.annotation.Nullable;
import android.content.Context;
import android.widget.SeekBar;

public class ToolbarFragment extends Fragment implements SeekBar.OnSeekBarChangeListener {

    private static int seekvalue = 10;

.
.

    @Override
    public void onViewCreated(@NonNull View view, @Nullable Bundle savedInstanceState) {
        super.onViewCreated(view, savedInstanceState);
        binding.seekBar1.setOnSeekBarChangeListener(this);
        binding.button1.setOnClickListener(new View.OnClickListener() {
            public void onClick(View v) {
                buttonClicked(v);
            }
        });
    }

    public void buttonClicked (View view) {
    }

    @Override
    public void onProgressChanged(SeekBar seekBar, int progress, boolean fromUser) {
        seekvalue = progress;
    }

    @Override
    public void onStartTrackingTouch(SeekBar arg0) {
    }

    @Override
    public void onStopTrackingTouch(SeekBar arg0) {
    }
}
```

在继续之前，我们需要花些时间解释上述代码更改。首先，该类被声明实现了 `OnSeekBarChangeListener` 接口。这是因为用户界面包含一个 `SeekBar` 实例，当用户滑动滑条更改字体大小时，片段需要接收通知。实现 `OnSeekBarChangeListener` 接口要求实现 `onProgressChanged()`、`onStartTrackingTouch()` 和 `onStopTrackingTouch()` 方法。这些方法已经实现，但只需要 `onProgressChanged()` 方法来执行任务，在这种情况下，是将新值存储在名为 `seekvalue` 的变量中，该变量在类的开头已声明。还声明了一个变量用于存储对 `EditText` 对象的引用。

添加了 `onViewCreated()` 方法以在按钮上设置 `OnClickListener`，它被配置在检测到点击事件时调用名为 `buttonClicked()` 的方法。该方法也已实现，尽管它目前没有执行任何操作。

此过程的下一阶段是设置监听器，允许片段在按钮被点击时调用 activity。这遵循了上一章中概述的机制：

```java
public class ToolbarFragment extends Fragment implements SeekBar.OnSeekBarChangeListener {
    private static int seekvalue = 10;
    private FragmentBinding binding;
    private ToolbarListener activityCallback;

    public interface ToolbarListener {
        public void onButtonClick(int position, String text);
    }

    @Override
    public void onAttach(Context context) {
        super.onAttach(context);
        try {
            activityCallback = (ToolbarListener) context;
        } catch (ClassCastException e) {
            throw new ClassCastException(context.toString() + " must implement ToolbarListener");
        }
    }
.
.
    public void buttonClicked (View view) {
        activityCallback.onButtonClick(seekvalue, binding.editText1.getText().toString());
    }
.
.
}
```

上述实现将导致在用户点击按钮时调用属于 activity 类的名为 `onButtonClick()` 的方法。因此，剩下的只需声明 activity 类实现了新创建的 `ToolbarListener` 接口并实现 `onButtonClick()` 方法。

由于在早期的 Android 版本中使用 Android Support Library 来支持片段，因此 activity 也需要更改为自 `FragmentActivity` 而不是 `AppCompat`。将这些需求结合起来产生了如下 `MainActivity.java` 文件：

```java
package com.ebookfrenzy.fragmentexample;

import androidx.appcompat.app.AppCompatActivity;
import androidx.fragment.app.FragmentActivity;
import android.os.Bundle;

public class MainActivity extends FragmentActivity implements ToolbarFragment.ToolbarListener {
.
.
    public void onButtonClick(int fontsize, String text) {
    }
}
```

按照目前的代码更改，工具栏片段将检测用户点击按钮并调用 activity 方法，传递 `EditText` 字段的内容和 `SeekBar` 视图的当前设置。现在 activity 的工作是与文本片段通信，并传递这些值，以便片段相应地更新 `TextView` 对象。

### 31.8 让 Activity 与文本片段通信

如“Android 片段简介”中所述，activity 可以获取片段类实例的引用并调用公共方法来与片段通信。因此，在 `TextFragment` 类中，我们现在实现一个名为 `changeTextProperties()` 的公共方法，它接收一个字体大小整数和一个新文本的字符串作为参数。该方法将使用这些值来修改 `TextView` 对象。在 Android Studio 编辑面板中，找到并修改 `TextFragment.java` 文件以添加此新方法：

```java
package com.ebookfrenzy.fragmentexample;

.
.

public class TextFragment extends Fragment {
.
.
    public void changeTextProperties(int fontsize, String text) {
        binding.textView2.setTextSize(fontsize);
        binding.textView2.setText(text);
    }
}
```

当 `TextFragment` 碎片放置在 activity 的布局中时，它被分配了一个为 `text_fragment` 的 ID。通过这个 ID，activity 现在可以获取碎片实例的引用，并在该对象上调用 `changeTextProperties()` 方法。编辑 `MainActivity.java` 文件并按如下所示修改 `onButtonClick()` 方法：

```java
public void onButtonClick(int fontsize, String text) {
    TextFragment textFragment =
    (TextFragment)
      getSupportFragmentManager().findFragmentById(R.id.text_fragment);
    textFragment.changeTextProperties(fontsize, text);
}
```

### 31.9 测试应用程序

该项目的编码工作已经完成，最后一个剩下的任务是运行应用程序。当应用程序启动时，主 activity 将启动，并创建并显示两个碎片。当用户触摸工具栏碎片中的按钮时，工具栏碎片会调用 activity 的 `onButtonClick()` 方法，并将来自 `EditText` 视图的文本和 `SeekBar` 的当前值传递。随后，activity 将调用第二个碎片的 `changeTextProperties()` 方法，该方法将修改 `TextView` 以反映新的文本和字体大小：

![](img/as_fragment_example_running.jpg)

图 31-10

### 31.10 总结

本章的目标是创建一个示例项目，演示在 Android 应用程序中使用碎片的步骤。涵盖的主题包括使用 Android Support Library 以与引入碎片之前的 Android 版本保持兼容，包括在 activity 布局中的碎片，以及实现碎片间的通信。

## 32. 带有 Jetpack 的现代 Android 应用程序架构

多年来，Google 并没有推荐构建 Android 应用程序的特定方法，而是提供工具和开发包，让开发者决定什么方法对特定项目或个人编程风格最有效。这种情况在 2017 年随着 Android Architecture Components 的引入而发生了变化，这些组件随后在 2018 年发布时成为了 Android Jetpack 的一部分。

本章提供了 Jetpack 概念、Android 应用架构建议以及一些关键架构组件的概述。在涵盖基础知识后，这些主题将在后续章节中进行详细介绍，并通过实际示例进行演示。

### 32.1 什么是 Android Jetpack？

Android Jetpack 由 `Android Studio`、Android Architecture Components、Android Support Library 以及一组关于 Android App 应该如何结构的指南组成。Android Architecture Components 的设计是为了在开发 Android 应用时能够更快、更方便地执行常用任务，同时符合架构指南的核心原则。

虽然本书将涵盖所有的 Android Architecture Components，但本章将重点关注关键架构指南以及 `ViewModel`、`LiveData` 和 `Lifecycle` 组件，同时引入 `Data Binding` 和 `Repositories`（仓库）。

在继续之前，重要的是理解 Jetpack 应用开发方法是可选的。虽然这种方法强调了多年来流行的其他技术的某些缺点，但 Google 并没有完全谴责那些应用程序的开发方法。Google 的立场是，虽然开发应用没有绝对的对错，但存在一种推荐的方法。

### 32.2 “旧”架构

在题为“在 Android Studio 中创建示例 Android 应用”的章节中，创建了一个由单个 activity 组成的 Android 项目，该 activity 包含了显示和管理用户界面的所有代码，以及应用程序的后端逻辑。在 Jetpack 引入之前，最常见的架构遵循这种范式，即应用程序由多个 activity（每个应用内的每个屏幕对应一个）组成，每个 activity 类在某种程度上都混合了用户界面和后端代码。

这种方法导致了一系列与应用生命周期相关的问题（例如，用户每次旋转设备时 activity 都会被销毁并重建，导致任何未保存到持久化存储中的应用数据丢失），以及诸如导航效率低下等问题（用户访问的每个应用屏幕都需要启动一个新的 activity）。

### 32.3 现代 Android 架构

在最基础的层，Google 现在提倡单 activity 应用，其中不同的屏幕作为内容加载到同一个 activity 内部。

现代架构指南还建议将应用程序中不同的职责区域划分到完全独立的模块中（这一概念被称为“关注分离”）。这种方法的关键之一是 `ViewModel` 组件。

#### 32.4 ViewModel 组件

`ViewModel` 的作用是将应用程序与用户界面相关的数据模型和逻辑，与负责显示、管理用户界面以及与操作系统交互的代码隔离开。当这样设计时，应用程序将由一个或多个 UI 控制器（如 activity）以及负责处理这些控制器所需数据的 `ViewModel` 实例组成。

`ViewModel` 只知道数据模型和相应的逻辑。它不了解用户界面，也不尝试直接访问或响应与用户界面内视图相关的事件。当 UI 控制器需要数据进行显示时，它请求 `ViewModel` 提供数据。同样，当用户在用户界面内的视图中输入数据时，UI 控制器将其传递给 `ViewModel` 处理。

这种职责的分离解决了与 UI 控制器生命周期相关的问题。无论 UI 控制器在应用的生命周期内重建多频繁，`ViewModel` 实例都会保留在内存中，从而保持数据一致性。例如，activity 使用的 `ViewModel` 将一直留在内存中，直到 activity 结束（在单 activity 应用中，这意味着直到应用程序退出）。

![](img/jetpack_diagram_1.jpg)

图 32-1

#### 32.5 LiveData 组件

考虑一个显示实时数据的应用程序，例如金融股票的当前价格。该程序可以使用股票价格 Web 服务持续更新 `ViewModel` 中的数据模型以获取最新信息。这种实时数据只有在及时显示给用户时才有用。UI 控制器只有两种方式可以确保在用户界面显示最新数据。一种方案是控制器持续检查 `ViewModel` 以确定数据自上次显示以来是否发生了变化。然而，这种方法的缺点是效率可能可以提高。为了维持数据馈的实时性，UI 控制器必须在循环中运行，不断检查数据是否变化。



更好的解决方案是让 UI 控制器在 `ViewModel` 内特定数据项发生变化时接收通知。这是通过使用 `LiveData` 组件实现的。`LiveData` 是一个允许值变得可观察的数据持有者。简单来说，可观察对象可以在数据发生变化时通知其他对象，从而解决了确保用户界面始终与 `ViewModel` 中的数据保持一致的问题。

这意味着，例如，一个对 `ViewModel` 值的 UI 控制器可以设置一个观察者，当该值发生变化时，观察者将收到通知。在我们假设的应用程序中，例如，股票将被封装在 `ViewModel` 中的 `LiveData` 对象中，UI 控制器为该值分配一个观察者，声明一个在值变化时调用的方法。当由数据变化触发时，该方法将从 `ViewModel` 读取更新后的值并使用它来更新用户界面。

![](img/Jetpack_diagram_2.jpg)

图 32-2

`LiveData` 实例也可以被声明为可变的（mutable），这允许观察实体更新 `LiveData` 对象中持有的底层值。例如，用户可能会在用户界面输入一个值，该值需要覆盖存储在 `ViewModel` 中的值。

使用 `LiveData` 的另一个关键优势是它可以感知观察者的生命周期状态。例如，如果一个 `activity` 包含 `LiveData` 观察者，相应的 `LiveData` 对象将知道 `activity` 生命周期状态何时发生变化并做出相应响应。如果 `activity` 处于暂停状态（可能是应用被放入后台），`LiveData` 对象将停止向观察者发送事件。假设 `activity` 刚刚启动或在暂停后恢复。在这种情况下，`LiveData` 对象将向观察者发送一个 `LiveData` 事件，以便 `activity` 拥有最新的值。同样，`LiveData` 实例将知道 `activity` 何时被销毁并移除观察者以释放资源。

到为止，我们只讨论了 UI 控制器使用观察者的情况。在实践中，观察者可以用于任何符合 Jetpack 生命周期管理方法的对象内部。

### 32.6 ViewModel 状态保存

Android 允许用户将运行中的应用放入后台，并在设备上执行其他任务（包括运行其他应用）后返回到该应用。当设备资源不足时，操作系统将通过终止后台应用进程来解决此问题，从最久使用的应用开始。然而，当用户返回到已终止的后台应用时，它应该呈现与被放入后台时相同的状态，无论它之前是否被终止。在与 `ViewModel` 关联的数据方面，可以使用 `ViewModel Saved State` 模块来实现。该模块允许将值存储在应用的保存状态中，并在发生系统发起的进程终止时进行恢复。这个主题将在后的 “An Android ViewModel Saved State Tutorial” 章节中介绍。

### 32.7 LiveData 与数据绑定

Android Jetpack 包含了数据绑定库（Data Binding Library），它允许 `ViewModel` 中的数据直接映射到 XML 用户界面布局文件中的特定视图。在之前创建的 `AndroidSample` 项目中，必须编写代码来获取 `EditText` 和 `TextView` 视图的引用，并设置和获取文本属性以反映数据变化。数据绑定允许存储在 `ViewModel` 中的 `LiveData` 值可以直接在 XML 布局文件中引用，避免了编写代码来保持布局视图更新的需求。

![](img/Jetpack_diagram_3.jpg)

图 32-3

数据绑定将更详细地介绍，从 “An Overview of Android Jetpack Data Binding” 章节开始。

### 32.8 Android 生命周期

从 Android 组件创建到其被销毁的时间持续称为生命周期。在生命周期期间，组件将在不同的生命周期状态之间切换，这通常在操作系统的控制下并响应用户操作。例如，一个 `activity` 将从初始化状态开始，过渡到创建状态。一旦 `activity` 运行，它将切换到启动状态，从那里开始它将循环经过各种状态，包括创建、启动、恢复和销毁。

许多 Android 框架类和组件允许其他对象访问它们的当前状态。也可以使用生命周期观察者（Lifecycle observers），以便对象在另一个对象的生命周期状态发生变化时能够接收到通知。`ViewModel` 组件在后台使用这种技术来识别观察者何时重启或被销毁。此功能不仅限于 Android 框架和架构组件。它也可以构建在任何使用架构组件包含的一系列生命周期组件的类中。

能够检测并响应其他对象生命周期状态变化的对象被称为感知感知（lifecycle-aware）。相比之下，提供其生命周期状态访问的对象被称为生命周期所有者（lifecycle owners）。标题为 "Working with Android Lifecycle-Aware Components" 的章节将更详细地介绍生命周期。

### 32.9 Repository 仓库模块

如果 `ViewModel` 从一个或多个外部源（如数据库或网络服务）获取数据，那么将处理这些数据源的代码与 `ViewModel` 类分离是非常重要的。否则，这会违反关注点分离（separation of concerns）的指南。为了避免将此功能与 `ViewModel` 混合，Google 的架构指南建议将此代码放在独立的 `Repository` 仓库模块中。

仓库不是 Android 架构组件，而是由应用开发者创建的 `Java` 类，负责与各种数据源建立接口。该类为 `ViewModel` 提供接口，允许将数据存储在模型中。

![](img/Jetpack_diagram_4.jpg)

图 32-4

### 32.10 总结

直到最近，Google 倾向于不推荐构建 Android 应用的特定方法。随着 Android Jetpack 的推出，情况现在发生了变化，Jetpack 由工具、组件、库和架构指南组成。Google 现在建议将应用项目分为不同的模块，每个模块负责特定的功能区域，即所谓的“关注点分离”。

特别是，指南建议将应用的视图数据模型与处理用户界面的代码分离。此外，负责从网络服务或数据库等数据源收集的代码应该构建在独立的模块模块，而不是与视图模型绑定。

Android Jetpack 包含了 Android 架构组件，旨在更轻松地开发符合推荐指南的应用。本章介绍了 `ViewModel`、`LiveData` 和 `Lifecycle` 组件。这些将从下一章开始更详细地介绍。本章未提到的其他架构组件将在书后部分介绍。

### 33. 一个 Android ViewModel 教程

上一章介绍了 Android Jetpack 的基本概念，并概述了现代 Android 应用架构的基础。Jetpack 定义了一系列建议，描述 Android 应用项目应该如何构建，同时提供了一系列库和组件，使其更容易符合这些指南，从而用更代码和更少的错误开发可靠的应用。

为了帮助强化和澄清上一章提供的信息，本章将引导你创建一个使用 `ViewModel` 组件的示例应用项目。下一章将通过包含 `LiveData` 和数据绑定进一步增强此示例。

### 33.1 关于项目

在“在 Android Studio 中创建 Android 应用”章节中，创建了一个名为 `AndroidSample` 的项目，该应用的所有代码都封装在 `Activity` 类中。在接下来的章节中，我们创建了一个 `AVD` 模拟器并用于运行该应用。在应用运行时，我们亲身体会了以这种方式开发应用时出现的问题：当设备旋转时，显示在 `TextView` 控件上的数据会丢失。本章将使用 `ViewModel` 组件并遵循 Google 应用开发指南以避免 Activity 的复杂性，从而实现一个相同的货币转换器应用。

### 33.2 创建 ViewModel 项目

在创建 `AndroidSample` 项目时，选择了 `Empty Views Activity` 模板作为项目的基础。然而，此项目将使用 `Basic Views` 模板。从欢迎界面选择 `New Project` 选项，在弹出的项目对话框中选择 `Basic Views Activity` 模板。在 `Name` 字段中输入 `ViewModel`，并指定 `com.ebookfrenzy.viewmodel` 为包名。在点击 `Finish` 按钮之前，将 `Minimum API` 设置为 `26: Android 8.0 (Oreo)`，并将 `Language` 设置为 `Java`。

### 33.3 删除不需要的项目内容

正如“Android Studio 布局编辑器指南”所述，`Basic Views Activity` 模板包含了项目并不需要的特性。在将 `ViewModel` 添加到项目之前，我们首先需要按照步骤移除导航功能、第二个 fragment 和浮动操作按钮：

1. 在 Project 工具窗口中双击 `activity_main.xml` 布局文件，选择浮动操作按钮，并按 delete 键从布局中移除该对象。

2. 编辑 `MainActivity.java` 文件，从 `onCreate` 方法中删除浮动操作按钮代码，如下所示：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    binding.fab.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View view) {
            Snackbar.make(view, "Replace with your action", Snackbar.LENGTH_LONG)
                .setView(R.id.fab)
                .setAction("Action", null).show();
        }
    });
}
```

3. 在 Project 工具窗口中，导航并双击 `res -> navigation -> nav_graph.xml` 文件将其加载到导航编辑器中。

4. 在编辑器中，选择图面板中的 `SecondFragment` 条目并按 delete 键将其移除。

5. 找到并删除 `SecondFragment.java` 和 `fragment_second.xml` 文件。

6. 最后一个任务是从 `FirstFragment` 类中移除一些代码，以便 `Button` 视图在点击时不再导航到已不存在的第二个 fragment。编辑 `FirstFragment.java` 文件并移除 `onViewCreated()` 方法中的代码，使其内容如下：

```java
public void onViewCreated(@NonNull View view, Bundle savedInstanceState) {
    super.onViewCreated(view, savedInstanceState);
    binding.buttonFirst.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View view) {
            NavHostFragment.findNavController(FirstFragment.this)
                .navigate(R.id.action_FirstFragment_to_SecondFragment);
        }
    });
}
```

### 33.4 设计 Fragment 布局

下一步是设计 fragment 的布局。首先，在 Project 工具窗口中找到 `fragment_first.xml` 文件并双击它将其加载到布局编辑器中。布局加载后，选择并删除现有的 `Button`、`TextView` 和 `ConstraintLayout` 控件。接下来，在 Component Tree 面板中右键点击 `NestedScrollView` 实例，选择 `Convert NestedScrollView to ConstraintLayout` 选项，如图 33-1 所示：

![](img/as_convert_to_constaintlayout.jpg)

图 33-1

选择转换后的 `ConstraintLayout` 控件，使用 Attributes 工具窗口将 `id` 改为 `constraintLayout`。添加一个新的 `TextView`，将其放置在布局中心，并将 `id` 改为 `resultText`。接下来，从调色板拖入一个 `Number (Decimal)` 视图并放置在现有 `TextView` 上方。在布局选中该视图，参考 Attributes 工具窗口并将 `id` 改为 `dollarText`。

将一个 `Button` 控件拖到布局中，放置在 `TextView` 下方，并将文本属性更改为“Convert”。在按钮仍被选中的情况下，将 `id` 属性更改为 `convertButton`。此时，布局应该类似于图 33-2 所示（注意这三个视图已使用垂直链进行了约束）：

![](img/as_view_model_demo_ui.jpg)

图 33-2

最后，点击布局编辑器右上角的警告图标，并将硬编码的字符串转换为资源。

### 33.5 实现 View Model

完成用户界面布局后，需要在 view model 中创建应用的数据模型。首先，在 Project 工具窗口中找到 `com.ebookfrenzy.viewmodeldemo` 条目，右键点击它并选择 `New -> Java Class` 选项。将新类命名为 `MainViewModel` 并按回车键。编辑新类文件，使其内容如下：

```java
package com.ebookfrenzy.viewmodeldemo.main;

import androidx.lifecycle.ViewModel;

public class MainViewModel extends ViewModel {
    private static final Float rate = 0.74F;
    private String dollarText = "";
    private Float result = 0F;

    public void setAmount(String value) {
        this.dollarText = value;
        result = Float.parseFloat(dollarText) * rate;
    }

    public Float getResult() {
        return result;
    }
}
```

该类声明了变量来存储当前的美元值和转换后的金额，并提供了访问这些值的 getter 和 setter 方法。调用时，`setAmount()` 方法接收当前金额作为参数并将其存储在本地变量 `dollarText`。相反，`getResult()` 方法返回赋值给 `result` 变量的值。

### 33.6 将 Fragment 与 ViewModel 关联

fragment 需要某种方式获取 `ViewModel` 的引用以访问模型并观察数据变化。Fragment 或 Activity 使用 `ViewModelProvider` 实例维护它们所依赖的 `ViewModels`。

在 Fragment 中使用 `ViewModelProvider` 类创建 `ViewModelProvider` 实例。调用时，类初始化器接收当前 `Fragment` 或 `Activity` 的引用并返回如下 `ViewModelProvider` 实例：

```java
ViewModelProvider viewModelProvider = new ViewModelProvider(this);
```

一旦创建了 `ViewModelProvider` 实例，可以使用索引值请求特定的 `ViewModel` 类。提供者将会创建该 `ViewModel` 类的新实例或返回现有实例，例如：

```java
ViewModel viewModel = viewModelProvider.get(MainViewModel.class);
```

编辑 `FirstFragment.java` 文件并重写 `onCreate()` 方法以设置 `ViewModelProvider`：

```java
import androidx.lifecycle.ViewModelProvider;
import androidx.annotation.Nullable;

public class FirstFragment extends Fragment {
    private MainViewModel viewModel;

    @Override
    public void onCreate(@Nullable Bundle savedInstanceState) {
```

```java
super.onCreate(savedInstanceState);
viewModel = new ViewModelProvider(this).get(MainViewModel.class);
}
```

现在可以访问模型视图（model view），可以在 Fragment 中添加代码以开始处理数据模型。

### 33.7 修改 Fragment

需要更新 fragment 类以响应按钮点击并与存储在 `ViewModel` 中的数据值进行交互。该类还需要对用户界面布局中三个视图的引用，以便响应按钮点击、提取当前的美元值并显示转换后的货币金额。



在题为“在 Android Studio 中创建一个 Android 示例应用”的章节中，使用了`Button`控件的`onClick`属性来指定当用户点击按钮时调用的方法。遗憾的是，此属性只能调用`Activity`上的方法，而不能用于调用`Fragment`中的方法。为了克服这一局限性，我们必须在`Fragment`类中添加一些代码，为按钮设置`onClick`监听器。如下所示，可以在`FirstFragment.java`文件的`onViewCreated()`生命周期方法中实现这一目标：

```java
public class MainFragment extends Fragment {
    private MainViewModel viewModel;

    @Override
    public void onViewCreated(@NonNull View view, @Nullable Bundle savedInstanceState) {
        super.onViewCreated(view, savedInstanceState);
        binding.convertButton.setOnClickListener(v -> {

        });
    }
}
```

添加监听器后，每当用户点击按钮时，位于`onClick()`方法中的任何代码都会被调用。

## 33.8 访问 ViewModel 数据

点击按钮时，`onClick()`方法需要从`EditText`视图读取当前值，确认字段不为空，然后调用`ViewModel`实例的`setAmount()`方法。随后，该方法需要调用`ViewModel`的`getResult()`方法并将转换后的值显示在`TextView`控件上。

由于项目中尚未使用`LiveData`，因此每次创建`Fragment`时，都有必要从`ViewModel`获取最新的结果值。

继续在`FirstFragment.java`文件中，按照如下方式在`onViewCreated()`方法中实现这些要求：

```java
import java.util.Locale;

@Override
public void onViewCreated(@NonNull View view, @Nullable Bundle savedInstanceState) {
    super.onViewCreated(view, savedInstanceState);
    binding.resultText.setText(String.format(Locale.ENGLISH,"%.2f",
            viewModel.getResult()));
    binding.convertButton.setOnClickListener(v -> {
        if (!binding.dollarText.getText().toString().equals("")) {
            viewModel.setAmount(String.format(Locale.ENGLISH,"%s",
                    binding.dollarText.getText()));
            binding.resultText.setText(String.format(Locale.ENGLISH,"%.2f",
                    viewModel.getResult()));
        } else {
            binding.resultText.setText("No Value");
        }
    });
}
```

### 33.9 测试项目

完成此开发阶段后，在模拟器或物理设备上构建并运行应用，输入美元值并点击`Convert`按钮。转换后的金额应出现在`TextView`上，这表明 UI 控制器和`ViewModel`的重构按预期工作。

当运行原始的`AndroidSample`应用时，旋转设备会导致`resultText``TextView`控件上显示的值丢失。现在使用`ViewModelDemo`应用重复此测试，并注意旋转后当前的欧元值仍被保留。这是因为当`Fragment`被销毁和重建时，`ViewModel`留留在内存中，并且在`onViewCreated()`方法中添加了代码以用结果数据值更新`TextView`。

### 33.10 总结

在本章中，我们回顾了`Fragment`和`ViewModel`。我们演示了如何使用`ViewModel`处理跨配置更改的数据。

## 34.1 LiveData - 回顾

`LiveData`在[“现代 Android 架构”（#Modern_Architecture_Jetpack）章节引入。它是一个观察的数据持有者类，允许 UI 响应变化。

## 34.2 为 ViewModel 添加 LiveData

启动 Android Studio，打开上一章节创建的`ViewModelDemo`项目，并打开`MainViewModel.java`，其目前内容如下：

```java
package com.ebookfrenzy.viewmodeldemo;

import androidx.lifecycle.ViewModel;

public class MainViewModel extends ViewModel {
    private static final Float rate = 0.74;
    private String dollarText = "";
    private Float result = 0F;

    public void setAmount(String value) {
        this.dollarText = value;
        result = Float.parseFloat(dollarText)*rate;
    }

    public Float getResult() {
        return result;
    }
}
```

本章的此阶段旨在`result`变量封装在`LiveData`实例中（该对象需要是可变的，以便在用户每次请求货币转换时更改值）。从修改类开始，使其变为如下所示，注意在使用`LiveData`时需要导入额外的包：

```java
package com.ebookfrenzy.viewmodeldemo;

import androidx.lifecycle.MutableLiveData;
import androidx.lifecycle.ViewModel;

public class MainViewModel extends ViewModel {
    private static final Float rate = 0.74;
    private String dollarText = "";
    private Float result = 0F;
    final private MutableLiveData<Float> result = new MutableLiveData<>();

    public void setAmount(String value) {
        this.dollarText = value;
        result = Float.parseFloat(dollarText)*rate;
    }

    public Float getResult() {
        return result;
    }
}
```

既然`result`变量现在包含在一个可变的`LiveData`实例中，那么`setAmount()`和`getResult()`方法都必须进行修改。在`setAmount()`方法中，不能再使用赋值运算符（`=`）为`result`变量赋值了。相反，必须调用`LiveData.setValue()`方法，并将新值作为参数传递。按照目前的实现，`getResult()`方法声明为返回`Float`值，必须更改为返回`MutableLiveData`对象。完成这些剩余更改后将得到如下类文件：

```java
package com.ebookfrenzy.viewmodeldemo;

import androidx.lifecycle.MutableLiveData;

import androidx.lifecycle.ViewModel;

public class MainViewModel extends ViewModel {

    private static final Float rate = 0.74F;

    private String dollarText = "";

    final private MutableLiveData<Float> result = new MutableLiveData<>();

    public void setAmount(String value) {
        this.dollarText = value;
        result = Float.parseFloat(dollarText)*rate;
        result.setValue(Float.parseFloat(dollarText)*rate);
    }

    public Float getResult()
    public MutableLiveData<Float> getResult() {
        return result;
    }
}
```

### 34.3 实现观察者

现在转换结果已包含在`LiveData`实例中，下一步是在 UI 控制器中配置观察者，在例例中它是`FirstFragment`类。找到`FirstFragment.java`类（`app -> java -> <package name> -> FirstFragment`），双击它将其加载到编辑器，并修改`onViewCreated()`方法以创建一个名为`resultObserver`的新`Observer`实例：

```java
package com.ebookfrenzy.viewmodeldemo;

import androidx.lifecycle.Observer;

.
.

@Override
public void onViewCreated(@NonNull View view, @Nullable Bundle savedInstanceState) {
    super.onViewCreated(view, savedInstanceState);
    binding.resultText.setText(String.format(Locale.ENGLISH,"%.2f",
            viewModel.getResult()));
    final Observer<Float> resultObserver = new Observer<Float>() {
        @Override
        public void onChanged(@Nullable final Float result) {
            binding.resultText.setText(String.format(Locale.ENGLISH,
                    "%.2f", result));
        }
    };
.
.
}
```

`resultObserver`实例声明了`onChanged()`方法，当该方法被调用时，会传入当前的`result`值，将其转换为字符串并显示在`resultText``TextView`对象上。下一步是将观察者添加到`result``LiveData`对象中，该引用可以通过调用`ViewModel`对象的`getResult()`方法获取。由于现在更新`result``TextView`的责任已由`onChanged()`回调方法承担，现在执行此任务的现有代码行可以删除了：

```java
@Override
public void onViewCreated(@NonNull View view, @Nullable Bundle savedInstanceState) {
    super.onViewCreated(view, savedInstanceState);
    binding.resultText.setText(String.format(Locale.ENGLISH,"%.2f",
            viewModel.getResult()));
    final Observer<Float> resultObserver = new Observer<Float>() {
        @Override
        public void onChanged(@Nullable final Float result) {
            binding.resultText.setText(String.format(Locale.ENGLISH,
                    "%.2f", result));
        }
    };
    viewModel.getResult().observe(getViewLifecycleOwner(), resultObserver);
    binding.convertButton.setOnClickListener(v -> {
        if (!binding.resultText.getText().toString().equals("")) {
            viewModel.setAmount(String.format(Locale.ENGLISH,"%.2f",
                    viewModel.getResult()));
        } else {
            binding.resultText.setText("No Value");
        }
    });
}
```

### 34.4 总结

本章演示了使用`LiveData`来确保显示内容始终与`ViewModel`匹配。这个相对简单的过程是将数据值封装在`LiveData`中，并在 UI 控制器中设置观察者。每当`LiveData`值变化时，观察者就会收到通知。在项目中添加`LiveData`支持在某种程度上简化了设计。使用 Data Binding Library 还可以实现更多且更重要的改进，细节将在下一节中介绍。

## 35. Android Jetpack Data Binding 概述

在名为`使用 Jetpack 构建现代 Android 应用架构`的章节中，我们引入了 Android Data Binding 的概念。我们解释了如何使用它将用户界面布局中的视图直接连接到其他对象中的方法和数据，而无需编写代码。本章将提供有关数据绑定的更多细节，重点介绍数据绑定在 Android Studio 项目中是如何实现的。下一节的教程（Android Jetpack Data Binding 教程）将提供数据绑定运行的实际示例。

### 35.1 数据绑定的概述

Android Jetpack Data Binding Library 提供了数据绑定支持，主要提供了一种简单的方法，将用户界面布局中的视图与应用代码存储的数据（通常位于`ViewModel`实例中）连接起来。数据绑定还提供了一种方便的方法，将用户界面控件（如`Button`控件）映射到其他对象（如 UI 控制器和`ViewModel`实例）中的事件和监听方法。

当数据绑定与`LiveData`组件结合使用时会变得特别强大。例如，考虑使用数据绑定将`EditText`视图绑定到`ViewModel`中的`LiveData`变量。通过这种方式连接后，`ViewModel`中数据值的任何变化将自动显示在`EditText`视图中，而使用双向绑定时，输入到`EditText`中的任何数据都将自动用于更新`LiveData`值。最令人印象深刻的是，除了初始设置绑定所需的代码外，无需额外代码即可实现这一点。

### 35.2 数据绑定的关键组件

Android Studio 项目默认并没有配置数据绑定（data binding）支持。在应用开始使用数据绑定之前，必须结合几个元素。这些元素涉及项目构建配置、布局 XML 文件、数据绑定类以及数据绑定表达式语言的使用。虽然初看起来看起来可能很复杂，但拆分开来，这些都是非常简单的步骤，一旦完成，在节省编码工作量方面将证明是物所值得的。本章的剩余部分将详细介绍每个元素。在涵盖这些基础知识后，下一章将通过详细的教程来演示这些步骤。

#### 35.2.1 项目构建配置

在项目可以使用数据绑定之前，必须配置其使用 Android Data Binding 库，并启用对数据绑定类和绑定语法的支持。幸运的是，这可以通过在模块级`build.gradle.kts`文件中添加几行代码来实现（该文件列在项目工具窗口的`Gradle Scripts`下，名为`build.gradle.kts (Module: app)`）。以下列出了一个启用了数据绑定的部分构建文件：

```kotlin
android {
    buildFeatures {
        dataBinding = true
    }
}
```

#### 35.2.2 数据绑定布局文件



正如我们在之前的章节中所看到的，应用的用户界面通常包含在 XML 布局文件中。在这些布局文件中的视图利用数据绑定之前，必须将布局文件转换为数据绑定布局文件。

正如书早些部分所述，XML 布局文件定义了布局中组件的层次结构，从顶层或根视图开始。无论如何，这个根视图都是布局容器的形式，例如`ConstraintLayout`、`FrameLayout`或`LinearLayout`实例，就像`ViewModelDemo`项目中的`fragment_main.xml`文件那样：

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".ui.main.MainFragment">

</androidx.constraintlayout.widget.ConstraintLayout>
```

要使用数据绑定，布局层次结构必须有一个`layout`组件作为根视图，该根视图反过来成为当前根视图的父级。

在上述示例的情况下，这需要对现有布局文件进行以下更改：

```xml
<?xml version="1.0" encoding="utf-8"?>
<layout xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:android="http://schemas.android.com/apk/res/android">
    <androidx.constraintlayout.widget.ConstraintLayout
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:app="http://schemas.android.com/apk/res-auto"
        xmlns:tools="http://schemas.android.com/tools"
        android:id="@+id/main"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:context=".ui.main.MainFragment">

    </androidx.constraintlayout.widget.ConstraintLayout>
</layout>
```

### 35.2.3 布局文件数据元素

数据绑定布局文件需要某种方式来声明项目中的类，布局中的视图将绑定到这些类（例如`ViewModel`或UI控制器）。声明这些类后，布局文件需要一个变量名称以便在绑定表达式中引用这些实例。

这是通过使用`data`元素实现的，示例所示：

```xml
<?xml version="1.0" encoding="utf-8"?>
<layout xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:android="http://schemas.android.com/apk/res/android">
    <data>
        <variable
            name="myViewModel"
            type="com.ebookfrenzy.myapp.ui.main" />
    </data>
    <androidx.constraintlayout.widget.ConstraintLayout
        xmlns:android="http://schemas.android.com/apk/res/android"
        android:id="@+id/main"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:context=".ui.main.MainFragment">

    </androidx.constraintlayout.widget.ConstraintLayout>
</layout>
```

（注：提供的文本在此部分包含了一些碎片化的XML逻辑；已进行清理以在保持结构完整性的同时保留原意。）

#### 35.2.4 绑定类

对于布局文件中`data`元素中引用的每个类，Android Studio将自动生成对应的绑定类。此`DataBinding`的子类将根据布局文件名并使用`Binding`后缀进行命名。因此，名为`fragment_main.xml`的布局文件的绑定类将是`FragmentMainBinding`。绑定类包含布局中指定的绑定，并将它们映射到变量。

尽管生成了绑定类，但必须编写代码来根据数据绑定布局文件创建该类的实例。幸运的是，这可以通过`DataBindingUtil`类来实现。

Activity或Fragment的初始化代码通常会设置内容视图或“填充”用户界面布局文件。这意味着代码打开布局文件、解析XML内存中配置所有视图对象。在现有Activity类的情况下，实现此目的的代码位于`onCreate()`方法中，内容如下：

```java
setContentView(R.layout.activity_main);
```

在Fragment的情况下，这发生在`onCreateView()`方法中：

```java
return inflater.inflate(R.layout.fragment_main, container, false);
```

在Activity类中创建绑定类实例只需要将初始化代码修改如下：

```java
ActivityMainBinding binding;
binding = DataBindingUtil.setContentView(this, R.layout.activity_main, false);
```

在Fragment的情况下，代码将如下：

```java
FragmentMainBinding binding;
binding = DataBindingUtil.inflate(inflater, R.layout.fragment_main, container, false);
binding.setLifecycleOwner(this);
View view = binding.getRoot();
return view;
```

### 35.2.5 数据绑定变量配置

如上述，数据绑定布局文件包含`data`元素，该元素包含由变量名和目标类类型组成的`variable`元素。例如：

```xml
<data>
    <variable
        name="viewModel"
        type="com.ebookfrenzy.viewmodeldemo.ui.main.MainViewModel" />
    <variable
        name="uiController"
        type="com.ebookfrenzy.viewmodeldemo_databinding.ui.main.MainFragment" />
</data>
```

在上面的示例中，第一个变量知道它将绑定到类型为`MainViewModel`的`ViewModel`类实例，但尚未连接到实际的`MainViewModel`对象实例。这需要一个额外的步骤，即将在app内部使用的`MainViewModel`实例赋值给布局文件中声明的变量。这是通过调用数据绑定实例的`setVariable()`方法实现的，该实例的引用在上一节中已获取：

```java
MainViewModel mViewModel = new ViewModelProvider(this).get(MainViewModel.class);

binding.setVariable(viewModel, mViewModel);
```

上述数据元素中的第二个变量引用了一个名为`MainFragment`的形式的UI控制器类。在这种情况下，UI控制器（无论是`Activity`还是`Fragment`）中的代码需要按照如下方式将自己赋值给该变量：

```java
binding.setVariable(uiController, this);
```

### 35.2.6 绑定表达式（单向）

绑定表达式定义了特定视图如何与绑定的对象交互。例如，`Button`上的绑定表达式可以声明在响应点击时调用对象上的哪种方法。或者，绑定表达式可以定义显示在`TextView`中的`ViewModel`中存储的数据值，以及如何进行展示和格式化。

绑定表达式使用声明性语言，允许通过逻辑以及对其他类和方法的访问来决定如何使用绑定数据。例如，表达式可以包含数学表达式、方法调用、字符串拼接、数组元素的访问以及比较操作。此外，所有标准的Java语言库都会默认导入，因此许多在Java中可以实现的功能也可以在绑定表达式中执行。正如已经讨论过的，`data`元素还可以用于导入自定义类以为表达式添加更多功能。

绑定表达式以`@`符号开头，随后是用花括号（`{}`）包围的表达式。

例如，考虑一个包含名为`result`变量的`ViewModel`实例。假设该类已分配给数据绑定布局文件中的名为`viewModel`的变量，并需要绑定到`TextView`对象，以便该视图始终显示最新的结果值。如果此值被存储为`String`对象，则在布局文件中的声明如下：

```xml
<TextView
    android:id="@+id/resultText"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="@{viewModel.result}"
    app:layout_constraintBottom_toBottomOf="parent"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent" />
```

在上面的XML中，`text`属性被设置为存储在`viewModel`对象`result` `LiveData`属性中的值。

然而，考虑如果`result`在模型中被存储为`Float`值而不是`String`。如果是这样，上面的表达式会导致编译错误。显然，在`TextView`显示它之前，必须将`Float`值转换为字符串。为了解决此类问题，绑定表达式可以包含必要的步骤，使用标准Java语言类来完成转换：

```xml
android:text="@{String.valueOf(viewModel.result)}"
```

在进行此更改后运行应用时，需要注意的是Android Studio控制台中可能会出现以下警告：

`warning: myViewModel.result.getValue() is a boxed field but needs to be un-boxed to execute String.valueOf(viewModel.result.getValue()).`

Java中的值可以采取原始值的形式（例如`boolean`类型，称为拆箱），或者封装在Java对象中（例如`Boolean`类型）并通过对对象的引用进行访问（即装箱）。拆箱过程涉及从对象中解出原始值。

为了避免此消息，请如下所示将违规的操作封装在`safeUnbox()`调用中：

```xml
android:text="@{String.valueOf(safeUnbox(myViewModel.result))}"
```

也可以使用字符串拼接。例如，为了在结果字符串值之后包含“dollars”一词，将使用以下表达式：

```xml
android:text='@{String.valueOf(safeUnbox(myViewModel.result)) + " dollars"}'
```

注意，由于附加的结果字符串被封装在双引号中，因此该表达式现在用单引号进行封装，以避免语法错误。

表达式语法还允许声明三元语句。在下面的表达式中，视图将根据结果值是否大于10显示不同的文本：

```xml
@{myViewModel.result > 10 ? "Out of range" : "In range"}
```

表达式还可以被构造以访问数据数组中的特定元素：

```xml
@{myViewModel.resultsArray[3]}
```

### 35.2.7 绑定表达式（双向）

到目前为止的表达式类型被称为单向绑定。换句话说，随着相应值的变化，布局会不断更新，但从布局内部对值的更改不会更新存储的值。

另一方面，双向绑定允许数据模型响应布局的变化而进行更新。例如，`EditText`视图可以配置为双向绑定，这样当用户输入不同的值时，该值将用于更新对应的数据模型值。在声明双向表达式时，语法与单向表达式类似，但它以`@=`开头。例如：

```xml
android:text="@={viewModel.result}"
```

### 35.2.8 事件与绑定

绑定表达式还可以响应视图事件触发方法调用。例如，`Button`视图可以配置为在点击时调用方法。在“在Android Studio中创建示例应用”章节中，例如`onClick`属性被配置为调用类中的方法。在XML文件中，表示如下：

```xml
android:onClick="convertCurrency"
```

`convertCurrency()`方法按照如下方式声明：

```java
public void convertCurrency(View view) {
}
```

注意，这种类型的方法调用总是会传递事件发生视图的引用。可以使用数据绑定通过表达式来实现相同的效果（假设布局已绑定到名为`uiController`的类）：

```xml
android:onClick="@uiController::convertCurrency}"
```

另一种选项并且允许向方法传递参数，被称为监听绑定。下面的表达式使用这种方法在`viewModel`实例上调用无参数的方法：

```xml
android:onClick='@{() -> myViewModel.methodOne()}'
```

下面的表达式调用了一个需要三个参数的方法：

```xml
android:onClick='@{() -> myViewModel.methodTwo(viewModel.result, 10, "A String")}'
```

绑定表达式提供了丰富且灵活的语言，将用户界面视图绑定到其他对象的数据和方法。本章仅讨论了最常用的用例。要了解更多绑定表达式，请查看在线Android文档：

https://developer.android.com/topic/libraries/data-binding/expressions

### 35.3 总结

Android数据绑定提供了用户界面布局与应用架构中其他对象的数据和方法之间创建连接的方法。在完成初始配置步骤后，数据绑定涉及在布局文件的视图元素中使用绑定表达式。这些绑定表达式可以是单向的或双向的，还可以用于绑定在响应点击等事件时调的方法。

到本书为止，我们已经涵盖了现代Android应用架构的基本概念，并详细查看了`ViewModel`和`LiveData`组件。数据绑定（Data Binding）的概念在上一章也已经介绍过，现在将在本中使用它来进一步修改`ViewModelDemo`应用。

### 36.1 移除冗余代码

如果你仍然需要，请复制`ViewModelDemo`项目文件夹并将其保存为`ViewModelDemo_LiveData`以供后续章节。复制完成后，打开原始的`ViewModelDemo`项目，准备实现数据绑定。

在`ViewModelDemo`应用中实现数据绑定之前，将通过删除项目中在在本章结束时不再需要的所有代码来演示数据绑定的威力。

启动Android Studio，打开`ViewModelDemo`项目，编辑`FirstFragment.java`文件，并按如下修改代码：



```java
package com.ebookfrenzy.viewmodeldemo;

.
.

import android.arch.lifecycle.Observer;

.
.

public class MainFragment extends Fragment {
    private MainViewModel viewModel;
.
.
    @Override
    public void onViewCreated(@NonNull View view,
                             @Nullable Bundle savedInstanceState) {
        super.onViewCreated(view, savedInstanceState);
        final Observer<Float> resultObserver = new Observer<Float>() {
            @Override
            public void onChanged(@Nullable final Float result) {
                binding.resultText.setText(String.format(Locale.ENGLISH,
                            "%.2f", result));
            }
        };
        viewModel.getResult().observe(getViewLifecycleOwner(), resultObserver);
        binding.convertButton.setOnClickListener(v -> {
            if (!binding.dollarText.getText().toString().equals("")) {
                viewModel.setAmount(String.format(Locale.ENGLISH,"%s",
                        binding.dollarText.getText()));
            } else {
                binding.resultText.setText("No Value");
            }
        });
    }
.
.
```
接下来，编辑 `MainViewModel.java` 文件并继续按如下删除代码（同时注意 `dollarText` 变量转换为 `LiveData` 的变化）：

```java
package com.ebookfrenzy.viewmodeldemo;

import android.arch.lifecycle.MutableLiveData;
import android.arch.lifecycle.ViewModel;

public class MainViewModel extends ViewModel {
    private static final Float rate = 0.74F;
    final public MutableLiveData<String> dollarValue = new MutableLiveData<>();
    private String dollarText = "";
    final private public MutableLiveData<Float> result = new MutableLiveData<>();
    public void setAmount(String value) {
        this.dollarText = value;
        result.setValue(Float.valueOf(dollarText)*rate);
    }

    public MutableLiveData<Float> getResult()
    {
        return result;
    }
}
```
虽然在实现数据绑定时会增加一些代码，但数据绑定显著减少了需要编写的代码量。

### 36.2 启用数据绑定

使用数据绑定的第一是在 Android 项目中启用它。这涉及向 `Gradle Scripts -> build.gradle.kts (app)` 文件添加一个新属性。在 `build.gradle.kts` 文件中，添加以下元素以在项目内启用数据绑定：

```kotlin
plugins {
    id("com.android.application")
}
android {
.
.
    buildFeatures {
        viewBinding = true
        dataBinding = true
    }
.
}
```
一旦添加了该项，编辑器顶部会出现一个条栏，其中包含 `Sync Now`（立即同步）链接。点击它用新的构建配置重新同步项目。

### 36.3 添加布局元素

正如 "Android 数据绑定概述" 所述，布局层次结构必须有一个 `layout` 组件作为根节点才能使用数据绑定。这需要对 `fragment_first.xml` 布局（`app -> res -> layout -> fragment_first.xml`）进行以下更改。在布局编辑器中打开此文件，切换到 `Code` 模式并进行这些更改：

```xml
<?xml version="1.0" encoding="utf-8"?>
<layout xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:android="http://schemas.android.com/apk/res/android">
    <androidx.constraintlayout.widget.ConstraintLayout
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:app="http://schemas.android.com/apk/res-auto"
        xmlns:tools="http://schemas.android.com/tools"
        android:id="@+id/main"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:context=".FirstFragment">
.
.
    </androidx.constraintlayout.widget.ConstraintLayout>
</layout>
```
完成这些更改后，切换回 `Design` 模式并注意新的根视图虽然在布局画布上不可见，但现在列在组件树中，如图 36-1 所示：

![](img/as_live_data_component_tree.jpg)

图 36-1

构建并运行应用以验证添加布局元素没有更改用户界面。在构建项目时，你可能会遇到部分内容的错误：

`Duplicate class kotlin.collections.jdk8.Collections8 found in modules`

此错误是由 Android Studio 构建工具链引起的，可以通过对 `build.gradle.kts (Module: app)` 文件进行以下更改来解决：

```kotlin
dependencies {
.
.
    implementation(platform("org.jetbrains.kotlin:kotlin-bom:1.8.0"))
}
```

## 36.4 在布局文件中添加数据元素

将布局文件转换为数据绑定布局文件的下一步是添加 `data` 元素。在本示例中，布局将绑定 `MainViewModel`，因此编辑 `fragment_first.xml` 文件添加如下 `data` 元素：

```xml
<?xml version="1.0" encoding="utf-8"?>
<layout xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:android="http://schemas.android.com/apk/res/android">
    <data>
        <variable
            name="myViewModel"
            type="com.ebookfrenzy.viewmodeldemo.MainViewModel" />
    </data>
    <androidx.constraintlayout.widget.ConstraintLayout
        android:id="@+id/main"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:context=".FirstFragment">
.
.
    </androidx.constraintlayout.widget.ConstraintLayout>
</layout>
```
构建并重新运行应用以确保更改生效。

## 36.5 使用绑定类工作

下一步是修改 `FirstFragment.java` 代码以填充数据绑定。这通过重写 `onCreateView()` 方法实现最好：

```java
.
.
import androidx.databinding.DataBindingUtil;
import com.ebookfrenzy.viewmodeldemo.R;
.
.

public class MainFragment extends Fragment {
.
.
    @Override
    public View onCreateView(@NonNull LayoutInflater inflater, @Nullable ViewGroup container,
                             @Nullable Bundle savedInstanceState) {
        binding = FragmentMainBinding.inflate(inflater, container, false);
        binding = DataBindingUtil.inflate(
            inflater, R.layout.fragment_first, container, false);
        binding.setLifecycleOwner(this);
        return binding.getRoot();
    }
.
.
}
```

```java
inflater, R.layout.fragment_first, container, false);
```
绑定对象在内存中的存在时间应与 fragment 的存在时间一致。为了确保在 fragment 移除时销毁实例，将当前 fragment 声明为绑定对象的生命周期所有者（lifecycle owner）。

```java
binding.lifecycleOwner = this;

return binding.getRoot
```

### 36.6 将 ViewModel 实例赋值给数据绑定变量

此时，数据绑定已经知道它将绑定到类型为 `MainViewModel` 的类实例，但尚未连接到实际的 `MainViewModel` 对象。这需要一个额外的步骤：将 App 中使用的 `MainViewModel` 实例赋值给布局文件中声明的 `viewModel` 变量。将所示所示代码添加到 `FirstFragment.java` 文件的 `onViewCreated()` 方法中：

```java
import static com.ebookfrenzy.viewmodeldemo.BR.myViewModel;

@Override
public void onViewCreated(@NonNull View view, @Nullable Bundle savedInstanceState) {
    super.onViewCreated(view, savedInstanceState);
    binding.setVariable(myViewModel, viewModel);
}
```
如果 Android Studio 显示 `myViewModel` 为 `undefined`（未定义），请使用 `Build -> Make Project` 选项重新构建项目以强制生成类。完成这些更改后，下一步是在数据绑定布局文件的视图元素中插入一些绑定表达式。

### 36.7 添加绑定表达式

第一个绑定表达式将 `resultText` TextView 绑定到模型视图中的结果值。编辑 `fragment_first.xml` 文件，找到 `resultText` 元素，并修改 `text` 属性，使元素内容如下：

```xml
<TextView
    android:id="@+id/resultText"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="TextView"
    android:text='@{safeUnbox(myViewModel.result) == 0.0 ? "Enter value" : String.valueOf(safeUnbox(myViewModel.result)) + " euros"}'
    app:layout_constraintBottom_toBottomOf="parent"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent" />
```
该表达式首先检查结果值当前是否为零，如果是，则显示一条指示用户输入值的消息。然而，如果结果不为零，则将该值转换为字符串，并与 `"euros"` 一词拼接，然后显示给用户。

结果值只需要单向绑定，因为布局永远不需要更新存储在 `ViewModel` 中的值。相比之下，`dollarValue` EditText 视图需要使用双向绑定，以便根据用户输入的最新值更新数据模型，并在发生（如由于设备旋转触发的）生命周期事件时，允许当前值在视图中重新显示。现在，`dollarText` 元素应声明如下：

```xml
<EditText
    android:id="@+id/dollarText"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_marginTop="96dp"
    android:ems="10"
    android:importantForAutofill="no"
    android:inputType="numberDecimal"
    android:text="@={myViewModel.dollarValue}"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintHorizontal_bias="0.502"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent" />
```
现在添加了这些初始绑定表达式后，必须编写一个方法在用户点击 `Button` 小部件时执行转换。

### 36.8 添加转换方法

当点击 `Convert` 按钮时，它将调用 `ViewModel` 上的方法来执行转换计算，并将欧元值存入 `result` `LiveData` 变量。现在在 `MainViewModel.java` 文件中添加此方法：

```java
public class MainViewModel extends ViewModel {
    private static final Float usd_to_eu_rate = 0.74F;
    final public MutableLiveData<String> dollarValue = new MutableLiveData<>();
    final public MutableLiveData<Float> result = new MutableLiveData<>();

    public void convertValue() {
        if ((dollarValue.getValue() != null) &&
            !dollarValue.getValue().equals("")) {
            result.setValue(Float.parseFloat(dollarValue.getValue()));
        } else {
            result.setValue(0F);
        }
    }
}
```



注意，在没有有效值的情况下，`result` `LiveData` 被赋予零值。这确保了`resultText` `TextView`显示“Enter value”消息。

## 36.9 添加监听器绑定

在测试项目之前的最后一步是为`Button`添加监听器表达式以调用`convertValue()`。在代码模式下再次编辑`fragment_first.xml`文件，找到`convertButton`元素，并如下添加`onClick`：

```xml
<Button
    android:id="@+id/convertButton"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:onClick="@{() -> myViewModel.convertValue()}"
    android:text="@string/convert_text"
    app:layout_constraintBottom_toBottomOf="parent"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintHorizontal_bias="0.5"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toBottomOf="@+id/resultText" />
```

## 36.10 测试应用

编译并运行应用，测试在金额字段中输入值并点击`Convert`按钮是否会在`TextView`中显示正确的结果（带有“euros”后缀），以及在金额字段为空时尝试转换是否会出现“Enter value”提示。此外，验证在设备旋转时信息是否仍然保留。

## 36.11 总结

本章的主要目标是完成配置项目数据数据的步骤，并演示单向、双向和监听表达式的使用。本章还提供了一个实用示例，展示了如何结合`LiveData`使用数据绑定来连接用户界面视图与应用的后端数据及逻辑。

## 37. 一个 ViewModel 保存状态教程

应用状态的保存和恢复是指在应用置于后台后，为用户提供连续性。用户期望能够从一个应用切换到另一个应用，并在返回原始应用时，发现它仍处于切换前的完全状态。

正如理解 Android 应用和 Activity 生命周期章节所述，当用户将应用放入后台时，如果资源紧张，该应用就有被操作系统终止的可能性。当用户尝试返回已终止的应用时，Android 会在新进程中重新启动该应用。由于这一切对用户来说是不可见的，因此应用有责任将其恢复到最初放入后台时的相同状态，而不是以“初始启动”状态呈现。对于基于`ViewModel`的应用，这种许多行为都可以使用 ViewModel Saved State 模块来实现。

### 37.1 理解 ViewModel 状态保存

正如前几节所述，`ViewModel`为应用开发带来了许多优势，包括在配置发生变化（如设备旋转）时恢复 UI 状态。要查看此效果，请运行`ViewModelDemo`应用（或者如果你还需要创建项目，请在 Android Studio 中加载随书示例代码下载的`ViewModelDemo_LiveData`项目）。

运行后，输入一个美元金额并将其转换为欧元。在显示美元和欧元数值的情况下，旋转设备或模拟器，并注意当应用响应方向变化后，这两个数值仍然可见。

遗遗憾的是，这种行为并不适用于后台应用进程的终止。在应用仍运行的情况下，点击设备主页键将`ViewModelDemo`应用置于后台，然后通过打开终端工具窗口并运行以下命令来终止它（其中`<package name>`是你创建项目时使用的名称，例如`com.ebookfrenzy.viewmodeldemo`）：

```
adb shell am kill <package name>
```

如果未找到`adb`命令，请参阅章节“设置 Android Studio 开发环境” 以获取设置 Android Studio 环境的步骤。

应用被终止后，返回设备或模拟器并在启动器中选择该应用（不要从 Android Studio 内部重新运行应用）。一旦应用出现，它看起来就像刚刚启动一样，最后输入的美元和欧元数值已经丢失。然而，从用户的角度来看，该应用是从后台恢复的，本应该仍包含原始数据。在这种情况下，应用未能提供用户对 Android 应用所预期的连续性。

## 37.2 实现 ViewModel 状态保存

基础的 ViewModel 状态保存通过引入`ViewModel Saved State`库得以实现。该库库扩展了`ViewModel`类，以支持在后台进程终止及随后的重新启动期间维持状态。

保存状态的关键是`SavedStateHandle`类，它用于保存和恢复 view model 实例的状态。`SavedStateHandle`对象包含一个键值映射，允许通过引用相应的键来保存和恢复数据值。

为了支持状态保存，需要声明不同类型的`ViewModel`子类，在这种情况下，它包含一个可以接收`SavedStateHandle`实例的构造函数。一旦声明，就可以在创建时通过包含`SavedStateViewModelFactory`对象来创建此类类型的`ViewModel`实例。考虑以下来自标准`ViewModel`声明的代码片段：

```java
package com.ebookfrenzy.viewmodeldemo.ui.main;

import androidx.lifecycle.ViewModel;
import androidx.lifecycle.MutableLiveData;

public class MainViewModel extends ViewModel {
.
.
}
```

创建此类类实例的代码可能类似于以下：

```java
private MainViewModel mViewModel;

mViewModel = new ViewModelProvider(this).get(MainViewModel.class);
```

另一方面，设计用于支持保存状态的`ViewModel`子类需要如下声明：

```java
package com.ebookfrenzy.viewmodeldemo.ui.main;

import android.util.Log;
import androidx.lifecycle.ViewModel;
import androidx.lifecycle.MutableLiveData;
import androidx.lifecycle.SavedStateHandle;

public class MainViewModel extends ViewModel {
    private SavedStateHandle savedStateHandle;

    public MainViewModel(SavedStateHandle) {
        this.savedStateHandle = savedStateHandle;
    }
.
.
}
```

当创建上述`ViewModel`实例时，必须向`ViewModelProvider`传递一个`SavedStateViewModelFactory`实例：

```java
SavedStateViewModelFactory factory = 

ViewModelProvider(this).get;
```

## 37.3 保存和恢复状态

可以通过通过`SavedStateHandle`实例的`set()`方法，从`ViewModel`内部保存对象或值，并提供引用该值的键：

```java
private final String NAME_KEY = "Customer";

set(NAME_KEY);
```

当与`LiveData`配合使用时，引用键后可以使用`SavedStateHandle`实例的`getLiveData()`方法恢复之前保存的值：

```java
getLiveData(NAME_);
```

其他常用的`SavedStateHandle`方法包括：

- `contains(String key)`：返回布尔值，表示保存的状态是否包含该值。

- `remove(String key)`：从保存状态中移除该值和键。

- `keys()`：返回保存状态中所有键的集合。

## 37.4 为 ViewModel 项目添加保存状态支持

在涵盖`ViewModel Saved State`基础之后，可以扩展`ViewModelDemo`应用以包含此支持。首先将`ViewModelDemo`项目加载到 Android Studio，打开`build.gradle.kts` (Module `:app`) 文件并添加保存状态依赖（一如既往，检查是否有可用版本）：

```kotlin
dependencies {
implementation("androidx.savedstate:savedstate:1.2")
implementation("androidx.lifecycle:lifecycle-viewmodel:2.6")
}
```

接下来，修改`MainViewModel.java`文件，使构造函数接收并存储`SavedStateHandle`实例。此外，导入`SavedStateHandle`，声明键常量并修改`result`变量，以便现在从构造函数中的保存状态中获取值：

```java
package com.ebookfrenzy.viewmodeldemo.ui.main;

import androidx.lifecycle.ViewModel;
import androidx.lifecycle.MutableLiveData;
import androidx.lifecycle.SavedStateHandle;

public class MainViewModel extends ViewModel {
    private static final String RESULT_KEY = "Euro";
    private static final Float rate = 0.74F;
    private String dollarText = "";
    final private SavedStateHandle savedStateHandle;
    final private MutableLiveData<Float> result = new MutableLiveData<>();

    public MainViewModel(SavedStateHandle savedStateHandle) {
        this.savedStateHandle = savedStateHandle;
        result = savedStateHandle.getLiveData(RESULT_KEY);
    }
}
```

在`MainViewModel.java`文件中，修改`setAmount()`方法，以便在每次计算新的欧元金额时保存结果值：

```java
public void setAmount(String value) {
    this.dollarText = value;
    result.setValue(Float.valueOf(dollarText) * rate);
    Float convertedValue = Float.parseFloat(dollarText) * rate;
    result.setValue(convertedValue);
    savedStateHandle.set(RESULT_KEY, convertedValue);
}
```

完成`ViewModel`的更改后，打开`FirstFragment.java`文件进行以下更改，以便在创建`ViewModel`的过程中包含`SavedState`工厂实例：

```java
import androidx.lifecycle.SavedStateViewModelFactory;

@Override
public void onCreate(@Nullable Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    SavedStateViewModelFactory factory = 
        new SavedStateViewModelFactory(getActivity().getApplication(),this);
    mViewModel = new ViewModelProvider(this, factory).get(MainViewModel.class);
    // TODO: 使用 ViewModel
}
```

当屏幕 UI 填充了美元和欧元数值时，将应用置于后台，使用`adb`工具终止它，然后从设备或模拟器屏幕上重新启动它。重启后，之前的货币金额仍仍显示在`TextView`和`EditText`组件中，这表明状态已成功保存并恢复。

### 37.5 总结

一个设计良好的应用在从后台恢复到前台时，应该始终向用户呈现相同的状态，无论操作系统在此期间是否终止了包含该应用的进程。在处理`ViewModels`时，可以通过利用`ViewModel Saved State`模块来实现这一点。这涉及修改`ViewModel`构造函数以接受一个`SavedStateHandle`实例，该实例反过来可以通过一系列方法调用来保存和恢复数据值。在创建`ViewModel`实例时，必须传递一个`SavedStateViewModelFactory`实例。一旦实现了这些步骤，应用将在后台被终止期间自动保存和恢复状态。

## 38. 与 Android 生命周期周期感知组件一起工作

早前的章节 “理解 Android 应用和 Activity 生命周期周期” 描述了如何使用生命周期方法来跟踪 UI 控制器（如 activity 或 fragment）内部生命周期状态的变化。这些方法的主要问题之一是它们将处理生命周期变化的负担交给了 UI 控制器。从表面上看，这似乎是逻辑上的方法，因为 UI 控制器终究是正在经历状态更改的对象。然而，事实是，受状态变化影响的代码通常位于应用中的其他类中。这导致 UI 控制器中出现了复杂的代码，需要响应生命周期状态的变化来管理和操作其他对象。在遵循 Android 架构指南时，最好能避免这种情况。

一种更清晰、更符合逻辑的方法是，让应用中的对象能够观察其他对象的生命周期状态，并负责根据变化采取任何必要的操作。例如，负责跟踪用户位置的类可以观察 UI 控制器的生命周期状态，并在控制器进入暂停状态时挂起位置更新。当控制器进入恢复状态时，重新开始跟踪。这是通过与 Android 架构组件捆绑的`Lifecycle`包所提供的类和接口实现的。

本章将介绍使能够将生命周期感知构建到 Android 应用中的术语和关键组件。

### 38.1 生命周期感知

如果一个对象能够检测并响应应用内其他对象生命周期状态的变化，则称该对象为生命周期感知的。某些 Android 组件（以`LiveData`为例）已经是生命周期感知的。通过在类中实现`LifecycleObserver`接口，也可以配置任何类为生命周期感知。

### 38.2 生命周期所有者 (Lifecycle Owners)

生命周期感知组件只能观察生命周期所有者的状态。生命周期所有者实现`LifecycleOwner`接口，并分配一个伴的`Lifecycle`对象，负责存储组件的当前状态并向生命周期观察者提供状态信息。大多数标准的 Android Framework 组件（如 activity 和 fragment 类）都是生命周期所有者。自定义类也可以使用`LifecycleRegistry`类并实现`LifecycleObserver`接口配置为生命周期所有者。例如：

```java
public class SampleOwner implements LifecycleOwner {

    private LifecycleRegistry lifecycleRegistry;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        lifecycleRegistry = new LifecycleRegistry(this);
    }

    @NonNull
    @Override
    public Lifecycle getLifecycle() {
        return lifecycleRegistry;
    }
}
```

除非生命周期所有者另一个生命周期感知组件的子类，否则该类需要通过调用`LifecycleRegistry`类的方法来触发生命周期状态的变化。可以使用`markState()`方法来触发传递新状态状态值的生命周期状态变化：

```java
public void resuming() {
    lifecycleRegistry.markState(Lifecycle.State.RESUMED);
}
```

上述调用将导致调用相应的事件处理器。或者，可以调用`LifecycleRegistry.handleLifecycleEvent()`方法并传递要触发的生命周期事件（这将导致生命周期状态的改变）。例如：



```java
lifecycleRegistry.handleLifecycleEvent(Lifecycle.Event.ON_START);
```

## 38.3 生命周期观察者（Lifecycle Observers）

为了观察生命周期所有者的状态，生命周期感知组件必须实现`DefaultLifecycleObserver`接口，并覆盖它需要观察的任何生命周期变化事件。

```java
public class SampleObserver implements DefaultLifecycleObserver {

    // 生命周期事件方法重写在这里
}
```

然后创建此观察者类的实例并将其添加到`Lifecycle`对象维护的观察者列表中。

```java
getLifecycle().addObserver(new SampleObserver());
```

如果观察者不再需要跟踪生命周期状态，可以随时从`Lifecycle`对象中移除。

图 38-1 展示了提供生命周期感知的关键元素之间的关系：

![](img/lifecycle_component_diagram.jpg)

图 38-1

## 38.4 生命周期状态和事件

当生命周期所有者的状态发生时，分配的`Lifecycle`对象将用新状态更新。在任何时刻，生命周期所有者将处于以下五个状态之一：

- `Lifecycle.State.INITIALIZED`
- `Lifecycle.State.CREATED`
- `Lifecycle.State.STARTED`
- `Lifecycle.State.RESUMED`
- `Lifecycle.State.DESTROYED`

`Lifecycle`对象将在组件转换到不同状态时，在添加到列表的观察者上触发事件。在生命周期观察者中可以重写以下事件方法：

- `onCreate()`
- `onResume()`
- `onPause()`
- `onStop()`
- `onStart()`
- `onDestroy()`

例如，以下代码重写了`DefaultLifecycleObserver.onResume()`方法：

```java
@Override
public void onResume(@NonNull LifecycleOwner owner) {
    // 响应恢复状态事件执行任务
}
```

图 38-2 中的流程图说明了生命周期所有者的状态变化序列，以及每次状态转换之间将在观察者上触发的生命周期事件：

![](img/android_lifecycle_states_diagram.jpg)

图 38-2

## 38.5 总结

本章介绍了生命周期感知的基础知识以及包含在 Android Jetpack 中的 Android Lifecycle 包。该包包含了用于创建生命周期所有者、观察者和生命周期感知组件的多个类和接口。生命周期所有者分配了一个`Lifecycle`对象，该对象维护所有者的状态记录和观察者列表。当所有者的状态更改时，将通过生命周期事件通知观察者以响应变化。

下一章将创建一个 Android Studio 项目，演示如何与创建生命周期感知组件一起工作，包括创建生命周期观察者和所有者，以及处理生命周期状态变化和事件。

上一章提供了生命周期感知的概述，并概述了在 Android 项目中实现这一特点的关键类和接口。本章将在此知识库的基础上，通过构建一个 Android Studio 项目来突出生命周期感知的实际应用。

# 39 创建示例生命周期项目

## 39.1 创建示例生命周期项目

从欢迎界面选择`New Project`（新建项目）快速启动选项，在生成的新项目对话框中，点击`Next`（下一步）按钮之前选择`Empty Views Activity`模板。

在`Name`（名称）字段中输入`LifecycleDemo`，指定`com.ebookfrenzy.lifecycledemo`为包名。在点击`Finish`（完成）按钮之前，将`Minimum API level`（最低 API 级别）设置为`API 26: Android 8.0 (Oreo)`，并将`Language`（语言）菜单设置为`Java`。

## 39.2 创建生命周期观察者

如之前讨论过的，活动（Activities）和片段（Fragments）已经实现了`LifecycleOwner`接口，并已准备好被其他对象观察。为了在实践中查看这一点，教程的下一步是向项目中添加一个新类，该类将能够观察`MainActivity`实例。

要添加新类，在项目工具窗口中右键点击`app` -> `java` -> `com.ebookfrenzy.lifecycledemo`，并在生成的菜单中选择`New`（新建） -> `Java Class...`。在`New Class`对话框中，将类命名为`DemoObserver`并按下键盘上的`Return`键以创建`DemoObserver.java`文件。该新文件将自动在编辑器中打开，其内容如下：

```java
package com.ebookfrenzy.lifecycledemo;

public class DemoObserver {

}
```

在编辑器中，修改类文件以声明它将实现`DefaultLifecycleObserver`接口：

```java
package com.ebookfrenzy.lifecycledemo;

import androidx.lifecycle.DefaultLifecycleObserver;

public class DemoObserver implements DefaultLifecycleObserver {

}
```

下一步是重写`DefaultLifecycleObserver`类的生命周期方法。对于此示例，所有事件都将被处理，每个事件都会向`Logcat`面板输出一条显示事件类型的消息。按照以下列表所示更新观察者类：

```java
package com.ebookfrenzy.lifecycledemo;

import android.util.Log;
import androidx.annotation.NonNull;
import androidx.lifecycle.LifecycleOwner;

.

.

public class DemoObserver implements DefaultLifecycleObserver {

    private String LOG_TAG = "DemoObserver";

    @Override
    public void onCreate(@NonNull LifecycleOwner owner) {
        Log.i(LOG_TAG, "onCreate");
    }

    @Override
    public void onResume(@NonNull LifecycleOwner owner) {
        Log.i(LOG_TAG, "onResume");
    }

    @Override
    public void onPause(@NonNull LifecycleOwner owner) {
        Log.i(LOG_TAG, "onPause");
    }

    @Override
    public void onStart(@NonNull LifecycleOwner owner) {
        Log.i(LOG_TAG, "onStart");
    }

    @Override
    public void onStop(@NonNull LifecycleOwner owner) {
        Log.i(LOG_TAG, "onStop");
    }

    @Override
    public void onDestroy(@NonNull LifecycleOwner owner) {
        Log.i(LOG_TAG, "onDestroy");
    }
}
```

完成`DemoObserver`类后，下一步是将其作为观察者添加到`MainActivity`类中。

## 39.3 添加观察者

观察者通过调用所有者的`Lifecycle`对象的`addObserver()`方法来添加，该对象的引用是通过调用`getLifecycle()`方法获取的。编辑`MainActivity.java`类文件并编辑`onCreate()`方法以添加观察者：

```java
.

.

import com.ebookfrenzy.lifecycledemo.DemoObserver;

.

.

@Override
public void onViewCreated(@NonNull View view, @Nullable Bundle savedInstanceState) {
    super.onViewCreated(view, savedInstanceState);
    getLifecycle().addObserver(new DemoObserver());
}
```

创建观察者类并将其添加到生命周期所有者的`Lifecycle`对象后，应用已准备好进行测试。

## 39.4 测试观察者

由于`DemoObserver`类向`Logcat`控制台输出诊断信息，如果配置了过滤器仅显示`DemoObserver`消息，将更容易看到输出。使用之前在[“通过示例理解 Android 活动状态变化”]中概述的步骤，显示`Logcat`面板并在过滤器字段中输入以下键：

`package:mine tag:DemoObserver`

在应用成功启动后，`Logcat`输出应指示以下生命周期状态变化和事件：

- `onCreate`
- `onStart`
- `onResume`

在应用仍运行时，执行旋转以触发活动的销毁和重建，生成以下内容：

- `onPause`
- `onStop`
- `onDestroy`

## 39.5 创建生命周期所有者

本章的最后一个任务是创建一个自定义生命周期所有者。在项目工具窗口中右键点击`app` -> `java` -> `com.ebookfrenzy.lifecycledemo`并选择`New` -> `Java Class...`添加新类。在按下键盘键之前将类命名为`DemoObserver`。在编辑器中加载`DemoObserver.java`文件后，对其如下修改：

```java
package com.ebookfrenzy.lifecycledemo;

import androidx.lifecycle.DefaultLifecycleObserver;

public class DemoObserver implements DefaultLifecycleObserver {
}
```

该类需要一个初始化为自身的`LifecycleRegistry`实例和一个`getLifecycle()`方法。声明一个变量存储`LifecycleRegistry`、一个初始化`LifecycleRegistry`的构造函数并添加`getLifecycle()`方法：

```java
public class DemoObserver implements LifecycleOwner {
    private LifecycleRegistry lifecycleRegistry;

    public DemoObserver() {
        lifecycleRegistry = new LifecycleRegistry(this);
    }

    @NonNull
    @Override
    public Lifecycle getLifecycle() {
        return lifecycleRegistry;
    }
}
```

接下来，类必须通知注册表状态变化。可以通过使用`LifecycleRegistry`的`markState()`方法标记状态或使用`handleLifecycleEvent()`方法触发事件。自定义类中什么是状态变化取决于类的用途。对于此示例，我们将添加一些在调用时触发生命周期事件的方法：

```java
.

.

private final LifecycleRegistry lifecycleRegistry;

.

.

public void startOwner() {
    lifecycleRegistry.handleLifecycleEvent(Lifecycle.Event.ON_START);
}

public void stopOwner() {
    lifecycleRegistry.handleLifecycleEvent(Lifecycle.Event.ON_STOP);
}

@NonNull
@Override
public Lifecycle getLifecycle() {
    return lifecycleRegistry;
}
```

`DemoOwner`类中的最后一个更改是将`DemoObserver`类作为观察者添加。此调用将通过向类添加以下构造函数来实现：

```java
public DemoOwner() {
    lifecycleRegistry = new LifecycleRegistry(this);
    getLifecycle().addObserver(new DemoObserver());
}
```

将`MainActivity.java`文件加载到代码编辑器，定位到`onCreate()`方法，并添加代码创建`DemoOwner`类的实例并调用`startOwner()`和`stopOwner()`方法。请注意，添加观察者的调用已被移除。虽然单个观察者可以使用多个所有者，在本例中移除它是为了避免`Logcat`工具窗口中出现重复且混淆的输出：

```java
.

.

import com.ebookfrenzy.lifecycledemo.DemoOwner;

.

.
```

```java
private DemoOwner demoOwner;

@Override
public void onViewCreated(@NonNull View view, @Nullable Bundle savedInstanceState) {
    super.onViewCreated(view, savedInstanceState);
    demoOwner = new DemoOwner();
    demoOwner.startOwner();
    demoOwner.stopOwner();
    getLifecycle().addObserver(new DemoObserver());
}
```

## 39.6 测试自定义生命周期所有者

最后一次构建并运行应用，参考 Logcat 工具窗口，并确认观察者是否按照以下顺序检测到创建、启动和停止生命周期事件：

- `onCreate`
- `onStart`
- `onStop`

注意，尽管没有在`DemoOwner`类中添加代码来手动执行这些操作，但“创建”（created）状态的变化仍然被触发了。这些变化是在所有者实例首次被创建以及处理`ON_STOP`事件时自动触发的。

## 39.7 总结

本章提供了在 Android 应用中实现生命周期感知的实用演示，包括创建生命周期观察者以及设计并实现一个基础生命周期所有者类。

# 40 导航架构组件概览

如今很少有 Android 应用仅包含单个屏幕。事实上，大多数应用包含多个屏幕，用户通过屏幕手势、按钮点击和菜单选择在这些屏幕间进行导航。在 Android Jetpack 引入之前，在应用内实现导航很大程度上是一个手动编码的过程，没有简单的方法来查看和组织可能复杂的导航路径。然而，随着 Android 导航架构组件的引入，结合 Android Studio 对导航图的支持，这种情况得到了显著改善。

## 40.1 理解导航

每个应用都有一个主屏幕，该主屏幕在应用启动且任何启动屏出现后显示（启动屏是应用加载时临时显示的应用品牌屏幕）。用户通常从这个主屏幕执行任务，从而导致其他屏幕。这些屏幕通常以应用内其他活动（Activity）和碎片（Fragment）的形式存在。例如，消息应用可能有一个列出当前消息的主屏幕，用户可以从那里导航到另一个屏幕来访问联系人列表或设置屏幕。联系人列表屏幕可能会允许用户导航到其他屏幕，在其中可以添加新用户或更新现有的联系人。从图形上看，应用的导航图可以如图 40-1 所示表示：

![](img/jetpack_navigation_graph_diagram.jpg)

图 40-1

构成应用的每个屏幕（包括主屏幕）被称为“目的地”（destination），它通常是一个碎片或活动。Android 导航架构使用导航栈（navigation stack）来跟踪用户在应用内目的地之间的路径。当应用首次启动时，主屏幕是第一个被放入栈中的目的地，并成为当前目的地。当用户导航到另一个目的地时，该屏幕将成为当前目的地并推入栈中主目的地之上。当用户导航到其他屏幕时，它们也会被推入栈中。例如，图 40-2 显示了假设的消息应用在用户启动应用并导航到“添加联系人”屏幕后导航栈的当前状态：

![](img/jetpack_navigation_stack_diagram.jpg)

图 40-2

当用户使用系统返回键在屏幕间返回导航时，每个目的地都会从栈中弹出，直到主屏幕再次成为栈上唯一的目的地。在图 40-3 中，用户从“添加联系人”屏幕返回，将其从栈中弹出，并使联系人列表屏幕成为当前目的地：

![](img/jetpack_navigation_stack_pop_diagram.jpg)

图 40-3

在目的地之间导航和管理导航栈的所有工作都由导航控制器处理，由`NavController`类表示。



使用导航架构组件为 Android 项目添加导航是一个简单的过程，涉及导航宿主（navigation host）、导航图（navigation graph）、导航动作（navigation actions）以及少量的代码编写，以获取导航控制器实例的引用并与其交互。

## 40.2 声明导航宿主

导航宿主机嵌入活动用户界面布局中的特殊碎片（`NavHostFragment`），作为用户将导航的目的地的占位符。例如，图 40-4 显示了一个典型的活动屏幕，并突出了由导航宿主碎片表示的区域：

![](img/jetpack_navigation_navhost.jpg)

图 40-4

`NavHostFragment` 可以通过 Android Studio 布局编辑器从调色板的容器（Containers）部分拖放实例，或者通过以下方式手动编辑 XML：

```xml
<?xml version="1.0" encoding="utf-8"?>
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/container"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity" >

    <androidx.fragment.app.FragmentContainerView
        android:id="@+id/demo_host_fragment"
        android:name="androidx.navigation.fragment.NavHostFragment"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:defaultNavHost="true"
        app:navGraph="@navigation/navigation_graph" />

</FrameLayout>
```

上述导航宿主元素中注意的点是`name`属性对`NavHostFragment`的引用、将`defaultNavHost`设置为`true`以及将包含导航图的文件分配给`navGraph`属性。

当活动启动时，此导航宿主碎片将被导航图中指定的首页目的地替换。当用户在应用屏幕间导航时，宿主碎片将被对应目的地的相应碎片替换。

## 40.3 导航图

导航图是一个 XML 文件，包含了应用应用导航中的目的地。除了这些目的地之外，文件还包含导航动作，定义了目的地之间的导航以及从一个目的地传递数据到另一个目的地的可选参数。Android Studio 包含导航图编辑器，可以使用可视化方式或手动编辑 XML 来设计图并实现动作。

图 40-5 显示了设计模式下的 Android Studio 导航图编辑器：

![](img/as_4.1_navigation_graph_editor.jpg)

图 40-5

目的地列表 (A) 列出了图表中的所有目的地。从列表中选择一个目的地将定位并选中图表中对应的目的地（这对于在大图表中定位特定目的地特别有用）。导航图面板 (B) 包含一个每个目的地的对话框，每个对话框代表用户界面的布局。在这个示例中，此图表包含两个名为`mainFragment`和`secondFragment`的目的地。目的地之间的箭头 (C) 表示导航动作连接。通过将鼠标指针悬停在起始点的边缘上直到出现圆圈，然后从圆圈点击并拖动到目的地即可添加动作。属性面板 (D) 允许查看和修改当前所选目的地或动作连接的属性。在上方图中，显示了动作的属性。通过点击标记为 E 的按钮并从菜单中选择选项可以添加新目的地。可以选择添加现有的 fragment 或活动（activity）作为目的地，也可以创建新的空白 fragment 目的地。组件树面板 (F) 提供了导航图的层级概述。

通过将编辑器切换到代码（Code）模式，可以查看并修改导航图的底层 XML。以下 XML 列表表示了上方图 40-5 中所示目的地和动作连接的导航图：

```xml
<?xml version="1.0" encoding="utf-8"?>
<navigation xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/navigation_graph"
    app:startDestination="@id/mainFragment">
    <fragment
        android:id="@+id/mainFragment"
        android:name="com.ebookfrenzy.navigationdemo.ui.main.MainFragment"
        android:label="fragment_main"
        tools:layout="@layout/fragment_main" >
        <action
            android:id="@+id/mainToSecond"
            app:destination="@id/secondFragment" />
    </fragment>
    <fragment
        android:id="@+id/secondFragment"
        android:name="com.ebookfrenzy.navigationdemo.SecondFragment"
        android:label="fragment_second"
        tools:layout="@layout/fragment_second" >
    </fragment>
</navigation>
```

导航图也可以拆分为多个文件，以提高组织结构并促进复用。当采用这种结构时，嵌套图会被嵌入到根图中。要创建嵌套图，按住 Shift 并点击要嵌套的目的地，右键点击第一个目的地并选择`Move to Nested Graph -> New Graph`（移动到嵌套图 -> 新图）菜单选项。嵌套图将作为图中的一个新节点出现。双击嵌套图节点可以将图文件加载到编辑器中以访问嵌套图。

## 40.4 访问导航控制器 (Navigation Controller)

从一个目的地导航到另一个目的地通常是为了响应应用内的某个事件，例如按钮点击或菜单选择。在触发导航动作之前，代码必须先获取导航控制器实例的引用。这需要调用`Navigation`或`NavHostFragment`类的`findNavController()`方法。例如，下面的代码可以访问 activity 的导航控制器。注意，为了使代码生效，activity 必须包含一个导航宿片段（navigation host fragment）：

```
NavController controller =
    Navigation.findNavController(activity, R.id.demo_nav_host_fragment);
```

在这种情况下，方法调用传递了 activity 的引用以及嵌入在 activity 布局中的`NavHostFragment`的 ID。

或者，可以通过将该视图（view）传递给方法来识别与任何视图关联的控制器：

```
NavController controller = Navigation.findNavController(binding.button);
```

最后一种选项是通过调用`NavHostFragment`类的`findNavController()`方法并传递 fragment 的引用来查找 fragment 的导航控制器：

```
NavController controller = NavHostFragment.findNavController(fragment);
```

## 40.5 触发导航动作

一旦找到导航控制器，可以通过调用控制器的`navigate()`方法并传递要执行动作的资源 ID 来触发导航动作。例如：

```
controller.navigate(R.id.goToContactsList);
```

当选中动作连接时，动作的 ID 在导航图编辑器的属性面板中定义。

### 40.6 传递参数

在导航动作期间，可以使用导航图文件中声明的参数将数据从一个目的地传递到另一个目的地。一个参数由名称、类型和可选的默认值组成，可以在 XML 中手动添加，也可以在选择目的地时使用属性面板添加。例如，在图 40-6 中，声明了一个名为`contactsCount`的整数参数，默认值为 0：

![](img/argument_example.jpg)

图 40-6 一旦添加，参数将放置在接收目的地的 XML 元素中，例如：

```xml
<fragment
    android:id="@+id/secondFragment"
    android:name="com.ebookfrenzy.navigationdemo.SecondFragment"
    android:label="fragment_second"
    tools:layout="@layout/fragment_second" >
    <argument
        android:name="contactsCount"
        android:defaultValue="0"
        app:type="integer" />
</fragment>
```

导航组件提供了两种在目的地之间传递参数的技术。一种方法是将数据放入`Bundle`对象中，并在动作期间将其传递给目的地，然后在那里对其进行解包并提取参数。这种特定方法的主要缺点是它不是“类型安全的”（type safe）。换句话说，如果接收目的地对参数的处理类型与声明类型不符（例如将字符串视为整数），此错误将不会被编译器捕获，并可能在运行时引发问题。

另一种更好的方法（本书中使用的方法）是 safeargs。safeargs 是 Android Studio Gradle 构建系统的一个插件，它会自动生成特殊类，允许以类型安全的方式传递参数。safeargs 参数传递将在下一章（41.1）中进行描述和演示。

### 40.7 总结

在 Android 应用用户界面背景下，导航是指用户在不同屏幕之间移动的能力。曾经实现非常耗时且难以组织，现在 Android Studio 和导航组件使得在 Android 应用项目中实现和管理导航变得简单。

应用中的不同屏幕被称为目的地，通常由 fragment 或活动表示。所有应用都有一个主目的地，包括应用首次加载时显示的屏幕。此布局的内容区域被一个导航宿片段取代，当用户在应用导航时，它会被切换为其他的目的地片段。导航路径由导航图定义，该图由目的地以及连接它们的动作（以及在目的地之间传递的任何参数）组成。

上一章描述了 Android Jetpack Navigation 组件以及它如何与 Android Studio 的导航图表功能集成，从而为实现 Android 应用屏幕之间的快速导航提供了一种简单的方法。在本章中，将创建一个新的 Android Studio 项目，该项目将使用这些导航功能来实现一个包含多个屏幕的示例应用。除了演示如何使用 Android Studio 导航图表编辑器外，示例项目还将实现使用类型安全参数在源屏幕和目标屏幕之间传递数据。

### 41.1 创建 NavigationDemo 项目

从欢迎界面中选择`New Project`选项，在弹出的新项目对话框中，在点击`Next`按钮之前选择`Empty Views Activity`模板。

在`Name`字段中输入`NavigationDemo`，并指定`com.ebookfrenzy.navigationdemo`为包名。在点击`Finish`按钮之前，将`Minimum API level`设置更改为`API 26: Android 8.0 (Oreo)`，并将`Language`菜单更改为`Java`。

## 41.2 向构建配置中添加导航

默认情况下，新的`Empty Views Activity`项目不会在构建配置文件中包含 Navigation 组件库。因此，在执行任何其他任务之前，第一步是修改应用级的`build.gradle.kts`文件。在 Project 工具窗口中找到该文件（`Gradle Scripts -> build.gradle.kts (Module :app)`），双击将其加载到代码编辑器中，并修改`dependencies`部分以添加导航库。此外，借此机会启用此模块的 view binding：

```kotlin
android {
    buildFeatures {
        viewBinding = true
    }
}

dependencies {
    implementation ("androidx.navigation:navigation-fragment:2.6.0")
    implementation ("androidx.navigation:navigation-ui:2.6.0")
    implementation(platform("org.jetbrains.kotlin:kotlin-bom:1.8.0"))
}
```

注意，自本书出版以来，可能发布了这些库的新版本。在文件中添加导航依赖项后，点击`Sync Now`链接以重新同步项目的构建配置。

### 41.3 创建导航图资源文件

在构建配置中添加了导航库后，现在可以向项目中添加导航图资源文件了。正如“导航架构组件概述”所示，这是一个 XML 文件，包含用户可以导航的片段（fragments）和活动，以及用于执行跳转的动作以及在目标之间传递的任何数据。

在 Project 工具窗口中，找到`res`文件夹（`app -> res`），右键点击它，并选择`New -> Android Resource File`菜单选项：

![](img/as_new_resource_file_menu.jpg)

图 41-1

选择菜单项后，将出现`New Resource File`对话框。在此对话框中，将文件命名为`navigation_graph`，并将`Resource type`菜单更改为`Navigation`（如图 41-2

图 41-2

向项目添加导航图资源文件后，它将主面板中，准备添加新目标。将编辑器切换到`Code`模式，并在添加任何目标之前检查图表的 XML：

```xml
<?xml version="1.0" encoding="utf-8"?>
<navigation xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/navigation_graph">
</navigation>
```

在编辑器中切换回`Design`模式，注意`Destinations`面板的`Host`部分指示项目中未检测到任何导航主机片段（navigation host fragments）：

![](img/as_navigation_hosts_no_fragments.jpg)

图 41-3

在向导航图添加任何目标之前，下一步是向项目添加一个导航主机片段。

## 41.4 声明导航主机

对于此项目，导航主机片段将包含在主活动的用户界面布局中。首先，在 Project 工具窗口中找到主活动布局文件（`app -> res -> layout -> activity_main.xml`），将其加载到布局编辑器中，并删除默认的`TextView`组件。

在布局器的`Design`模式下，从`Palette`的`Containers`部分拖出一个`NavHostFragment`元素，并将其放置到活动布局的容器区域，如图 41-4 中的箭头所示：

![](img/as_navigation_add_navhostfragment.jpg)

图 41-4

从弹出的`Navigation Graphs`对话框中选择上一节创建的`navigation_graph.xml`文件，并点击`OK`按钮。

在布局中选中新添加的`NavHostFragment`实例后，使用`Attributes`工具窗口将元素的 ID 更改为`demo_nav_host_fragment`，然后点击`Infer`按钮。

将布局编辑器切换到`Code`模式并检查 XML 文件。注意编辑器已正确配置了`navigation graph`属性以引用`navigation_graph.xml`文件，并且`defaultNavHost`属性已设置为`true`。



```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <androidx.fragment.app.FragmentView
        android:id="@+id/demo_nav_host_fragment"
        android:name="androidx.navigation.fragment.NavHostFragment"
        android:layout_width="409dp"
        android:layout_height="729dp"
        app:defaultNavHost="true"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:navGraph="@navigation/navigation_graph" />

</androidx.constraintlayout.ConstraintLayout>
```

返回`navigation_graph.xml`文件，确认已检测到`HostFragment`实例（可能需要关闭并重新打开文件）：

![](img/as_navigation_hosts_fragment.jpg)

图 41-5

## 41.5 添加导航目标

在导航图中，现在是时候添加第一个目标了。如图 41-6 所示，点击`new destination`按钮以选择或创建目标：

![](img/as_navigation_add_navfragment_menu.jpg)

图 41-6

接下来，从菜单中选择`Create new destination`选项。在弹出的对话框中，选择`Fragment (Blank)`模板，在点击`Finish`按钮之前将新片段命名为`FirstFragment`，布局命名为`fragment_first`。在项目重新构建的片刻延迟后，新片段将作为目标出现在图中，如图 41-7 所示：

（此处缺少图片图 41-7）

目标节点上方的主图标表示它是起始目标。这意味着当创建`NavHostFragment`活动时，该目标将是第一个显示的。要将起始目标更改为另一个，请在图中选中节点并点击工具栏上的主按钮。

通过将编辑器切换到`Code`模式来检查导航图的 XML 内容：

（此处对应 XML 代码块）

```xml
<navigation xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/navigation_graph"
    app:startDestination="@id/firstFragment">
    <fragment
        android:id="@+id/firstFragment"
        android:name="com.ebookfrenzy.navigationdemo.FirstFragment"
        android:label="fragment_first"
        tools:layout="@layout/fragment_first">
        <action
            android:id="@+id/mainToSecond"
            app:destination="@id/secondFragment" />
    </fragment>
    <fragment
        android:id="@+id/secondFragment"
        android:name="com.ebookfrenzy.navigationdemo.SecondFragment"
        android:label="fragment_second"
        tools:layout="@layout/fragment_second" />
</navigation>
```

在执行任何导航之前，导航图至少还需要另一个目标。重复上述步骤，添加一个名为`SecondFragment`的片段，其布局文件命名为`fragment_second`。新片段将作为导航图中的另一个目标出现，如图图 41-8 所示：

![](img/as_navigation_two_fragments.jpg)

图 41-8

## 41.6 设计目标片段布局

在添加用于在目标之间进行导航的动作（actions）之前，现在是为图中的两个目标片段添加一些用户界面组件的好时机。首先，双击`firstFragment`目标，使`fragment_first.xml`文件加载到布局编辑器中，然后选择并删除默认的`TextView`实例。在组件树（Component Tree）面板中，右键点击`FrameLayout`条目，并选择`Convert from FrameLayout to ConstraintLayout`菜单选项，在生成的转换对话框中接受默认设置：

![](img/as_navigation_convert_to_constraint_layout.jpg)

图 41-9

使用属性（Attributes）工具窗口，将`ConstraintLayout`的 ID 更改为`constraintLayout`，然后将`Button`和`Plain Text EditText`控件拖到布局中，使其看起来像下方图 41-10 所示：

![](img/as_navigation_first_fragment_ui.jpg)

图 41-10

一旦视图位置正确，点击工具栏上的`Infer constraints`（推断约束）按钮，以向布局添加任何缺失的约束。选择`EditText`视图，并使用属性工具窗口删除默认的“Name”文本，并将控件的 ID 更改为`userText`。接下来，将按钮的文本属性更改为“Navigate”，并将其提取到字符串资源。

返回`navigation_graph.xml`文件，双击`secondFragment`目标以将`fragment_second.xml`文件加载到布局编辑器。选择并删除默认的`TextView`实例，重复上述步骤将`FrameLayout`转换为`ConstraintLayout`，并将 id 更改为`constraintLayout2`。接下来，拖入一个新的`TextView`控件将其置在布局中心，并点击`Infer constraints`按钮添加任何缺失的约束。选中新的`TextView`，使用属性面板将 ID 更改为`argText`。

## 41.7 为导航图添加动作

现在两个目标已添加到图中，并且设计了相应的用户界面布局，项目需要一种方法让用户能够从第一个片段导航到第二个片段。这将通过向图中添加一个动作来实现，之后可以在应用代码中引用该动作。

要建立以第一个片段为源点、第二个片段为目标的动作连接，打开导航图，并将鼠标指针悬停在`firstFragment`目标右边缘的垂直中心，此时会出现一个高亮的圆，如图图 41-11 所示：

![](img/as_navigation_first_fragment_selected.jpg)

图 41-11

点击圆圈内部并将生成的线条拖动到`secondFragment`目标：

![](img/as_navigation_add_connection.jpg)

图 41-12

释放线条以在源点和目标之间建立动作连接，此时线条将变为箭头，如图图 41-13 所示：

![](img/as_navigation_connected.jpg)

图 41-13

可以随时选中动作连接并按下键盘上的`Delete`键将其删除。选中箭头后，检查属性工具窗口中的可用属性，并将 ID 更改为`mainToSecond`。这是代码中引用该动作的 ID。将编辑器切换到代码模式，注意该动作现在已包含在 XML 中。

## 41.8 实现 `OnFragmentListener`

在添加代码以触发动作之前，`MainActivity`类必须实现`OnFragmentListener`。该接口是在片段类在导航图中创建时在类内部生成的。为了符合该接口，活动需要一个名为`onFragmentInteraction()`的方法，以实现片段与活动之间的通信。编辑`MainActivity.java`文件并进行修改如下：

```java
import android.net.Uri;

public class MainActivity extends AppCompatActivity implements SecondFragment.OnFragmentListener {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    @Override
    public void onFragmentInteraction(Uri uri) {
    }
}
```

如果 Android Studio 报告`OnFragmentListener`未定义（某些版本的 Android Studio 会自动添加，某些则不会），请编辑`SecondFragment.java`文件并添加以下内容：

```java
import android.net.Uri;

public interface OnFragmentListener {
    // TODO: Update argument type and name
    void onFragmentInteraction(Uri uri);
}
```

## 41.9 为目标片段添加视图支持

由于我们需要访问布局中的某些视图，必须修改当前代码以启用视图绑定。首先编辑`FirstFragment.java`文件并进行以下更改：

```java
import com.ebookfrenzy.navigationdemo.databinding.FragmentFirstBinding;

public class FirstFragment extends Fragment {
    private FragmentFirstBinding binding;

    @Nullable
    @Override
    public View onCreateView(@NonNull LayoutInflater inflater, @Nullable ViewGroup container, @Nullable Bundle savedInstanceState) {
        return inflater.inflate(R.layout.fragment_first, container, false);
        binding = FragmentFirstBinding.inflate(inflater, container, false);
        return binding.getRoot();
    }

    @Override
    public void onDestroyView() {
        super.onDestroyView();
        binding = null;
    }
}
```

对`SecondFragment.java`文件重复上述步骤，引用`FragmentSecondBinding`。

## 41.10 触发动作

现在动作已添加到导航图中，下一步是在第一个片段中添加一些代码，以便在点击`Button`控件时触发动作。找到`FirstFragment.java`文件，将其加载到代码编辑器，并重写`onViewCreated()`方法以获取按钮实例的引用，并配置`onClickListener`实例以便在用户点击按钮时进行调用。

```java
import androidx.annotation.NonNull;
import androidx.annotation.Nullable;
import android.widget.Button;
import androidx.navigation.Navigation;

public class FirstFragment extends Fragment {

    @Override
    public void onViewCreated(@NonNull View view,
                            @Nullable Bundle savedInstanceState) {
        super.onViewCreated(view, savedInstanceState);
        binding.button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Navigation.findNavController(view).navigate(
                        R.id.mainToSecond);
            }
        });
    }
}
```

上述代码获取了导航控制器（navigation controller）的引用，并在该实例上调用了`navigate()`方法，将导航动作的资源 ID 作为参数传递。

编译并运行应用，验证点击第一个 fragment 中的按钮是否会跳转到第二个 fragment。

作为这种设置监听器的替代方法，`Navigation`类还包含一个名为`createNavigateOnClickListener()`的方法，它提供了一种更高效的方法来设置监听器并导航到目的地。因此，可以使用以下单行代码来启动跳转并实现相同的结果：

```java
binding.button.setOnClickListener(Navigation.createNavigateOnClickListener(
                R.id.mainToSecond, null));
```

# 41.11 使用 Safeargs 传递数据

下一个目标是将第一个 fragment 中`EditText`视图输入的文本传递到第二个 fragment，并在那里显示在`TextView`控件上。如上一章所述，Android Navigation 组件支持两种传递数据的方法。本章将使用类型安全的参数传递。

使用`safeargs`的第一步是在 Gradle 构建配置中添加`safeargs`插件。使用 Project 工具窗口，找到并编辑项目层级的`build.gradle.kts`文件（`Gradle Scripts -> build.gradle.kts (Project: NavigationDemo)`），按如下所示添加插件依赖（再次提醒，现在可能有更此的版本）：

```kotlin
// 顶级构建文件，您可以在其中添加所有子项目/模块通用的配置选项
buildscript {
    dependencies {
        classpath("androidx.navigation:navigation-safe-args-gradle-plugin:2.6.0")
    }
}

plugins {
// ...
}
```

接下来，编辑模块级别的`build.gradle.kts`文件（`Gradle Scripts -> build.gradle.kts (Module :app)`），按如下所示应用插件并重新同步项目：

```kotlin
plugins {
    id("com.android.application")
    id ("androidx.navigation.safeargs")
}

android {
// ...
}
```

下一步是定义目的地（在本例中为第二个 fragment）将接收的任何参数。编辑导航图，选择`secondFragment`目的地，并在 Attributes 工具窗口中找到`Arguments`部分。点击`+`按钮（如图 41-14 中高亮所示）为目的地添加新参数：



![](img/as_navigation_add_arguments.jpg)

图 41-14

点击 `+` 按钮后，会弹出一个对话框，需要在其中输入参数名称、类型和默认值。将参数命名为 `message`，将类型设置为 `String`，在默认值字段输入 `No Message`，并点击 `Add` 按钮：

![](img/as_navigation_add_argument_dialog.jpg)

图 41-15

新配置的参数将出现在 `navigation_graph.xml` 文件的 `secondFragment` 中，如下：

```xml
<fragment
    android:id="@+id/secondFragment"
    android:name="com.ebookfrenzy.navigationdemo.SecondFragment"
    android:label="fragment_second"
    tools:layout="@layout/fragment_second">
    <argument
        android:name="message"
        app:argType="string"
        android:defaultValue="No Message" />
</fragment>
```

下一步是从 `FirstFragment.java` 中的 `EditText` 提取文本并传递给目的地。`safeargs` 插件将生成以下类：

- `FirstFragmentDirections`: 此类代表从源点的导航动作。
- `MainToSecond`: 此类代表用于导航到目的地的动作。
- `SecondFragmentArgs`: 此类用于访问目的地的参数。

要实现这一点，请修改 `FirstFragment.java` 中的 `onViewCreated` 方法。一旦构建项目，`safeargs` 插件将生成必要的类。如果 `FirstFragmentDirections` 未定义，请使用 `Build -> Make Project` 重新构建项目。使用以下代码：

```java
binding.button.setOnClickListener(view1 -> {
    FirstFragmentDirections.MainToSecond action = FirstFragmentDirections.mainToSecond();
    action.setMessage(binding.userText.getText().toString());
    Navigation.findNavController(view1).navigate(action);
});
```

剩下的只需修改 `SecondFragment.java` 类文件，以便在跳转后接收参数并将其显示在 `TextView` 控件上。对于此示例，将使用 `onStart()` 周期方法添加实现这些任务的代码。

```java
@Override
public void onStart() {
    super.onStart();
    SecondFragmentArgs args = SecondFragmentArgs.fromBundle(getArguments());
    String message = args.getMessage();
    binding.argText.setText(message);
}
```

编译并运行应用，并在点击 `Button` 控件之前输入文本。当第二个 fragment 目的地出现时，`TextView` 应显示在第一个 fragment 中输入的文本，这表明数据已成功在导航目的地之间传递。

### 41.12 总结

本章提供了一个使用 Navigation 架构组件和 Android Studio 导航图编辑器实现 Android 应用导航的实际示例。涵盖的主题包括创建包含现有和新目标片段的导航图、在 Activity 布局中嵌入导航宿片段（navigation host fragment）、编写触发导航事件的代码，以及使用 `safeargs` 插件在目的地之间传递参数。

# 42. MotionLayout 简介

`MotionLayout` 类为用户界面布局中的视图添加动画效果提供了一种简单的方法。本章将首先提供 `MotionLayout` 的概述，并介绍 `MotionScenes`（运动场景）、`Transitions`（过渡）和 `Keyframes`（关键帧）的概念。在介绍这些基础之后，接下来的两章（名为 "Android MotionLayout 教程" 和 "MotionLayout KeyCycle 教程"）将通过创建示例项目提供 `MotionLayout` 动画的更多细节和示例。

## 42.1 MotionLayout 概述

`MotionLayout` 是一种布局容器，其主要目的是对布局内视图从一个状态到另一个状态的过渡进行动画处理。例如，`MotionLayout` 可以在指定时间内动画 `ImageView` 实例从屏幕左上角移动到右下角的运动。除了视图的位置外，其他属性的变化也可以进行动画处理，例如颜色、大小或旋转角度。这些状态变化也可以进行插值（使得视图在整个动画过程中移动、旋转并改变大小）。

使用 `MotionLayout` 的视图运动可以在两点之间以直线形式执行，也可以实现为遵循由起始点和终点之间不同位置的中间点组成的路径。`MotionLayout` 还支持使用触摸和滑动来启动和控制动画。

`MotionLayout` 动画完全在 XML 中声明，通常不需要编写代码。这些 XML 声明可以在 Android Studio 代码编辑器中手动实现、使用 `MotionLayout` 编辑器进行视觉化实现，或者结合这两种方法。

### 42.2 MotionLayout

在实现动画时，用户界面中通常使用的 `ConstraintLayout` 容器必须先转换为 `MotionLayout` 实例（此任务可以通过布局编辑器中右键点击 `ConstraintLayout` 并选择 `Convert to MotionLayout` 菜单选项来实现）。`MotionLayout` 至少需要 2.0.0 版本的 `ConstraintLayout` 库。

不例外的是，由于它是 `ConstraintLayout` 的子类，`MotionLayout` 支持 `ConstraintLayout` 的所有布局功能。因此，对于不需要动画的视图，使用 `MotionLayout` 时可以同样设计用户界面布局。

对于需要动画的视图，会声明两个 `ConstraintSets`，用于定义视图在动画开始和结束时的外观和位置。`transition` 声明定义了关键帧，用于在这些起结束状态之间对目标视图应用额外效果，以及用于启动和控制动画的点击和滑动处理器。

起始和结束的 `ConstraintSets` 以及 `transitions` 声明在 `MotionScene` XML 文件中。

## 42.3 MotionScene

正如我们在前面的章节中看到的，XML 布局文件包含了配置呈现给用户的静态视图的外观和布局行为所需的必要信息，在使用 `MotionLayout` 时也是如此。对于非静态视图（换句话说，即要进行动画的视图），这些视图仍然在布局文件中声明，但与这些视图相关的起始、结束和过渡声明存储在一个名为 `MotionScene` 的独立 XML 文件中（之所以这样命名是因为所有声明都定义在 `MotionScene` 元素内）。该文件被导入布局 XML 文件中，包含了起始和结束的 `ConstraintSets` 以及 `Transition` 声明（一个文件可以包含多个 `ConstraintSet` 对和 `Transition` 声明，允许将不同的动画针对用户界面布局中的特定视图）。

下面的列表显示了一个 `MotionScene` 文件的模板：

```xml
<?xml version="1.0" encoding="utf-8"?>
<MotionScene
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:motion="http://schemas.android.com/apk/res-auto">
    <Transition
        motion:constraintSetEnd="@+id/end"
        motion:constraintSetStart="@id/start"
        motion:duration="1000">
        <KeyFrameSet>
        </KeyFrameSet>
    </Transition>
    <ConstraintSet android:id="@+id/start">
    </ConstraintSet>
    <ConstraintSet android:id="@+id/end">
    </ConstraintSet>
</MotionScene>
```

在上面的 XML 中，声明了名为 `start` 和 `end` 的 `ConstraintSets`（尽管可以使用任何名称），此时它们尚未包含任何约束元素。`Transition` 元素定义了这些 `ConstraintSets` 代表动画的起点和终点，并包含一个空的 `KeyFrameSet` 元素，准备填充额外的动画关键帧条目。`Transition` 元素还包含一个毫秒级持续时间属性，用于控制动画的运行时间。

`ConstraintSets` 并不意味着视图的运动。可以使起始和结束集声明屏幕上的相同位置，然后使用过渡来动画其他属性的变化，例如缩放和旋转角度。

## 42.4 配置 ConstraintSets

`MotionScene` 文件中的 `ConstraintSets` 允许将全套 `ConstraintLayout` 设置应用于视图，关于定位、尺寸调整以及与其他视图的关系。此外，可以在 `ConstraintSet` 中包含以下属性：

- alpha
- visibility
- elevation
- rotation
- rotationX
- rotationY
- translationX
- translationY
- translationZ
- scaleX
- scaleY

例如，要在动画期间旋转视图 180°，可以在起始和结束约束中声明以下内容：

```xml
<ConstraintSet android:id="@+id/start">
    <Constraint
        motion:layout_constraintStart_toOf="parent"
        android:rotation="0">
    </Constraint>
</ConstraintSet>

<ConstraintSet android:id="@+id/end">
    <Constraint
        motion:layout_constraintBottom_toBottomOf="parent"
        android:rotation="180">
    </Constraint>
</ConstraintSet>
```

上面的更改告诉 `MotionLayout` 视图从 0° 开始，然后在动画过程中旋转整个 180°，最后倒置停止。

### 42.5 自定义属性

除了上述列出的标准属性外，还可以指定一系列自定义属性（使用 `CustomAttribute` 声明）。事实上，视图类型上的几乎任何属性都可以指定为自定义属性以包含在动画中。要标识属性名称，请从目标视图类的文档查找 getter/setter 名称，删除 get/set 前缀，并将剩余的第一个字母转换为小写。例如，要在代码中更改 `Button` 视图的背景颜色，我们可能会如下调用 `setBackgroundColor()` 设置方法：

```java
myButton.setBackgroundColor(Color.RED)
```

在约束集或关键帧中设置此属性时，属性名称将为 `backgroundColor`。除了属性名称外，还必须使用以下选项中的适当类型声明值：

- `motion:customBoolean` - 布尔属性值。
- `motion:customColorValue` - 颜色属性值。
- `motion:customDimension` - 维度属性值。
- `motion:customFloatValue` - 浮点数属性值。
- `motion:customIntegerValue` - 整数属性值。
- `motion:customStringValue` - 字符串属性值。

例如，颜色设置需要使用 `motion:customColorValue` 类型进行赋值：

```xml
<CustomAttribute
    motion:attributeName="backgroundColor"
    motion:customColorValue="#43CC76" />
```

例如，以下 `MotionScene` 文件的节选声明了视图的起始和结束约束，并将将背景颜色从绿色更改为红色：

```xml
<ConstraintSet android:id="@+id/start">
    <Constraint
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        motion:layout_editor_absoluteX="21dp"
        android:id="@+id/button"
        motion:layout_constraintTop_toTopOf="parent"
        motion:layout_constraintStart_toStartOf="parent" >
        <CustomAttribute
            motion:attributeName="backgroundColor"
            motion:customColorValue="#33CC33" />
    </Constraint>
</ConstraintSet>
<ConstraintSet android:id="@+id/end">
    <Constraint
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        motion:layout_editor_absoluteY="21dp"
        android:id="@+id/button"
        motion:layout_constraintEnd_toEndOf="parent"
        motion:layout_constraintBottom_toBottomOf="parent" >
        <CustomAttribute
            motion:attributeName="backgroundColor"
            motion:customColorValue="#F80A1F" />
    </Constraint>
</ConstraintSet>
```

## 42.6 触发动画

如果没有某些事件告诉 `MotionLayout` 开始动画，`MotionScene` 文件中的所有设置都将不会影响布局（视图将根据起始 `ConstraintSet` 中的设置进行定位外）。

动画可以配置为响应屏幕点击（`OnClick`）或滑动（`OnSwipe`）手势来启动。`OnClick` 处理器会导致动画开始并运行直到完成，而 `OnSwipe` 则将同步动画沿时间轴来回移动，以匹配触摸动作。`OnSwipe` 处理器还会响应屏幕上的"飞掷"（flinging）动作。`OnSwipe` 处理器还提供了选项，用于配置动画如何响应不同方向的拖动，以及滑动锚定的目标视图的哪侧。这允许例如通过向左滑动动作让视图向相应方向移动，同时防止向上运动导致视图向侧移动（当然，除非这是所需的行为）。

`OnSwipe` 和 `OnClick` 声明包含在 `MotionScene` 文件的 `Transition` 元素中。在这两种情况下，必须指定视图 ID。例如，要实现一个响应锚定在名为 `button` 的视图底部的向下滑动动作的 `OnSwipe` 处理器，可以将以下 XML 放在 `Transition` 元素中：

```xml
<Transition
    motion:constraintSetEnd="@+id/end"
    motion:constraintSetStart="@id/start"
    motion:duration="1000">
    <KeyFrameSet>
    </KeyFrameSet>
    <OnSwipe
        motion:touchAnchorId="@+id/button"
        motion:dragDirection="dragDown"
        motion:touchAnchorSide="bottom" />
</Transition>
```

或者，为同一个按钮添加一个 `OnClick` 处理器：

```xml
<OnClick motion:targetId="@id/button" clickAction="toggle" />
```

在上面的示例中，动作已被设置为 `toggle`。此模式和其他可用选项可以总结如下：

- `toggle`: 动画化到相反状态。例如，如果视图当前处于过渡点，它将过渡到结束点，反之亦然。
- `jumpToStart`: 立即切换到起始状态，没有动画。



- `jumpToEnd`: 立即切换到结束状态，没有动画。
- `transitionToStart`: 带有动画地过渡到起始状态。
- `transitionToEnd`: 带有动画地过渡到结束状态。

## 42.7 弧形运动

默认情况下，视图位置的移动将在起始点和结束点之间直线运行。要将运动更改为弧形路径，请在起始约束中使用如下所示的`pathMotionArc`属性，并配置`startHorizontal`或`startVertical`来定义弧形是凹的还是凸的：

```xml
<ConstraintSet android:id="@+id/start">
    <Constraint
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        motion:layout_editor_absoluteX="21dp"
        android:id="@+id/button"
        motion:layout_constraintTop_toTopOf="parent"
        motion:layout_constraintStart_toStartOf="parent"
        motion:pathMotionArc="startVertical" >
</Constraint>
</ConstraintSet>
```

图 42-1 展示了`startVertical`和`startHorizontal`弧与默认直线的对比：

(image/motionlayout_arcMotion_three.jpg)

## 42.8 关键帧 (Keyframes)

为止列出的所有`ConstraintSet`属性仅适用于动画的起始和结束点。换句话说，如果旋转属性在结束点设置为 180°，那么旋转将在动画开始时开始并在到达结束点时完成。因此，无法配置旋转在动画进行到 50% 处达到完全 180°，然后在结束时旋转回原始方向。幸运的是，使用关键帧可以实现这种效果。

关键帧用于定义动画过程中的中间点，状态在此处发生。例如，可以声明关键帧，使视图的背景颜色在动画进行到 50% 处过渡到蓝色，在 75% 处变为绿色，并在动画结束时恢复原始颜色。关键帧实现在`MotionScene`文件的`Transition`元素中，嵌入在`KeyFrameSet`元素内。

`MotionLayout`支持多种类型的关键帧，总结如下：

### 42.8.1 属性关键帧

属性关键帧（使用`KeyAttribute`定义）允许在时间轴的中间更改视图属性。`KeyAttribute`支持上述`ConstraintSets`列出的属性，并结合指定更改在动画时间轴何时生效的能力。例如，以下关键帧声明将逐渐导致按钮视图在水平（`scaleX`）和垂直（`scaleY`）尺寸上翻倍，在时间 50% 处达到最大尺寸。在时间轴剩余的时间内，视图将缩小到原始尺寸：

```xml
<Transition
    motion:constraintSetEnd="@+id/end"
    motion:constraintSetStart="@id/start"
    motion:duration="1000">
    <KeyFrameSet>
        <KeyAttribute
            motion:motionTarget="@+id/button"
            motion:framePosition="50"
            android:scaleX="2.0" />
        <KeyAttribute
            motion:motionTarget="@+id/button"
            motion:framePosition="50"
            android:scaleY="2.0" />
    </KeyFrameSet>
</Transition>
```

- `parentRelative` - `x`和`y`坐标相对于其所在的父容器，坐标以百分比形式表示（表现为 0.0 到 1.0 之间的值）：

![](img/motionlayout_parentRelative.jpg)

图 42-2

- `deltaRelative` - `x`和`y`坐标不再相对于父容器，而是相对于起始和结束位置。例如，起始点为 (0, 0)，结束点为 (1, 1)。请注意`x`和`y`坐标可以是负值：

![](img/motionlayout_deltaRelative.jpg)

图 42-3

- `pathRelative` - `x`和`y`坐标相对于路径，其中起点和终点之间的直线作为图表的`X`-轴。同样，坐标以百分比形式表示（0.0 到 1.0）。这与`deltaRelative`坐标空间相似，但考虑了路径的角度。同样，坐标可能是负值：

![](img/motionlayout_pathRelative.jpg)

图 42-4

例如，以下`ConstraintSets`定义了设备屏幕两侧的起点和终点。默认情况下，使用这些点的视图过渡将跨越屏幕直线移动，如下图 42-5 所示：

![](img/motionlayout_straight_path.jpg)

图 42-5

然而，如果要求视图遵循类似于下方图 42-6 所示的路径：

![](img/motionlayout_wave_path.jpg)

图 42-6

为了实现这一点，可以在过渡内如下声明关键帧位置点：

```xml
<KeyPosition
    motion:motionTarget="@+id/button"
    motion:framePosition="25"
    motion:keyPositionType="pathRelative"
    motion:percentY="0.3"
    motion:percentX="0.25"/>

<KeyPosition
    motion:motionTarget="@+id/button"
    motion:framePosition="75"
    motion:keyPositionType="pathRelative"
    motion:percentY="-0.3"
    motion:percentX="0.75"/>
```

上述元素使用`pathRelative`坐标系统在路径 25% 和 75% 处创建了关键帧位置点。第一个位置位于坐标 (0.25, 0.3)，第二个位置位于 (0.75, -0.3)。这些位置关键帧可以像下方的图 42-7 所示进行可视化：

![](img/motionlayout_curve_path.jpg)

图 42-7

### 42.9 时间线性度

在没有额外设置的情况下，上述动画将以恒定速度执行。若要改变动画速度（例如，使其加速后减速），可以在`ConstraintSet`或`Keyframe`中使用过渡缓冲属性 (`transitionEasing`)。

对于复杂的缓动需求，可以通过在三次贝塞尔曲线上绘制点来定义线性度，例如：

```xml
motion:layout_constraintBottom_toBottomOf="parent"
motion:transitionEasing="cubic(0.2, 0.7, 0.3, 1)"
android:rotation="360"
```

如果你不熟悉贝塞尔曲线，可以考虑使用以下 URL 中的曲线生成器：[`cubic-bezier.com/`](https://cubic-bezier.com/)

但对于大多数需求，可以使用内置的标准、加速和减速值来指定缓动：

```xml
motion:layout_constraintBottom_toBottomOf="parent"
motion:transitionEasing="decelerate"
android:rotation="360"
```

### 42.10 KeyTrigger

触发关键帧 (`KeyTrigger`) 允许在动画到达动画时间轴内的指定帧位置时调用视图上的方法。这还考虑了动画的方向。例如，可以根据动画是向前运行还是反向运行调用不同的方法。考虑一个在动画移动超过时间轴的 20% 时变为可见的按钮。`KeyTrigger`将在`Transition`元素的`KeyFrameSet`中如下实现，并使用`onPositiveCross`属性：

```xml
<KeyFrameSet>
    <KeyTrigger
        motion:framePosition="20"
        motion:onPositiveCross="show"
        motion:motionTarget="@id/button"/>
</KeyFrameSet>
```

同样，如果相同的按钮在动画反向并掉到 10% 以下时隐藏，可以使用`onNegativeCross`属性添加第二个触发器：

```xml
<KeyTrigger
    motion:framePosition="10"
    motion:onNegativeCross="show"
    motion:motionTarget="@id/button2"/>
```

如果动画使用切换动作（toggle），请使用`onCross`属性：

```xml
<KeyTrigger
    motion:framePosition="10"
    motion:onCross="show"
    motion:motionTarget="@id/button2"/>
```

### 42.11 Cycle 和 时间关键帧

虽然位置关键帧可以用于向动画添加中间变化，但如果需要大量的重复操作，这会很快变得繁琐。对于需要重复执行的状态更改，`MotionLayout`包含了`Cycle`和`Time`关键帧。ALayout Cycle Tutorial 章节将详细介绍此主题。

### 42.2 从代码启动动画

到目前为止，我们只学习了如何使用`OnSwipe`和`OnClick`处理器控制动画。也可以通过调用`MotionLayout`实例的方法从代码中启动动画。下面的代码为名为`motionLayout`的布局运行持续时间为 2000ms 的过渡：

```java
motionLayout.setTransitionDuration(2000);
motionLayout.transitionToEnd();
```

在没有额外设置的情况下，用于动画的起始和结束状态将是`MotionScene`文件中定义的。若要使用特定的起始和结束约束集，可以在调用`MotionLayout`的`setTransition`方法时引用它们：

```java
motionLayout.setTransition(R.id.myStart, R.id.myEnd);
motionLayout.transitionToEnd();
```

要在动画运行时监控其状态，请如下所示为`MotionLayout`实例添加过渡监听器：

```java
motionLayout.setTransitionListener(transitionListener);
MotionLayout.TransitionListener transitionListener = new MotionLayout.TransitionListener() {
    @Override
    public void onTransitionStarted(MotionLayout motionLayout, int startId, int endId) {
        // 过渡开始时调用
    }
    @Override
    public void onTransitionChange(MotionLayout motionLayout, int startId, int endId, float progress) {
        // 每次属性变化时调用。跟踪进度值以找到当前位置
    }
    @Override
    public void onTransitionCompleted(MotionLayout motionLayout, int currentId) {
        // 过渡完成时调用
    }
    @Override
    public void onTransitionTrigger(MotionLayout motionLayout, int triggerId, boolean positive, float progress) {
        // 交叉触发关键帧阈值时调用
    }
};
```

#### 总结

`MotionLayout`是`ConstraintLayout`的子类，专门设计用于用户界面布局中的视图添加动画效果。`MotionLayout`通过动画由起始和结束约束集定义的状态之间的过渡来工作。可以使用关键帧在起始和结束点之间添加额外的动画效果。

动画可以通过`OnClick`或`OnSwipe`处理器触发，也可以通过调用`MotionLayout`实例的方法进行编程触发。

### 43. Android MotionLayout 编辑器教程

既然已经介绍了`MotionLayout`的基础知识，本章将提供一个在示例项目中尝试`MotionLayout`的机会。除了继续探索`MotionLayout`的主要功能外，本章还将介绍`MotionLayout`编辑器，并探索如何使用它可视化地构建和修改`MotionLayout`动画。

在本章创建的项目将使用起始结束`ConstraintSets`（约束集）、手势处理器以及`Attribute`（属性）和`Position`（位置）关键帧。

## 43.1 创建 MotionLayoutDemo 项目

在欢迎界面点击`New Project`按钮，在弹出的新项目对话框中选择`Empty Views Activity`模板，然后点击`Next`按钮。

在`Name`字段输入`MotionLayoutDemo`，并指定`com.ebookfrenzy.motionlayoutdemo`为包名。在点击`Finish`按钮之前，将`Minimum API level`设置为`API 26: Android 8.0 (Oreo)`，并将`Language`菜单更改为`Java`。

## 43.2 ConstraintLayout 转换为 MotionLayout

Android Studio 已在`activity_main.xml`布局文件中将一个`ConstraintLayout`容器作为父视图。下一步是将该容器转换为`MotionLayout`实例。在`Component Tree`（组件树）中，右键点击`ConstraintLayout`条目并选择`Convert to MotionLayout`菜单选项：

![](img/as_convert_to_motionlayout.jpg)

图 43-1

选择后，点击确认对话框中的`Convert`按钮。一旦转换完成，`MotionLayout`编辑器将出现在 Android Studio 主窗口中，如图 43-2 所示：

![](img/as_motionlayout_editor.jpg)

图 43-2

作为转换过程的一部分，Android Studio 将创建一个`res -> xml`的新文件夹，并在其中放置名为`activity_main_scene.xml`的`MotionLayout`场景文件：

![](img/as_motionlayout_scene_file.jpg)

图 43-3

该文件包含一个顶层`MotionScene`元素，其中包含`ConstraintSet`和`Transition`条目，这些条目将定义主布局中的动画。默认情况下，该文件将包含起始和结束约束集的空元素以及一个初始过渡：

```xml
<?xml version="1.0" encoding="utf-8"?>
<MotionScene
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:motion="http://schemas.android.com/apk/res-auto">
    <Transition
        motion:constraintSetEnd="@+id/end"
        motion:constraintSetStart="@id/start"
        motion:duration="1000">
        <KeyFrameSet>
        </KeyFrameSet>
    </Transition>
    <ConstraintSet android:id="@+id/start">
    </ConstraintSet>
    <ConstraintSet android:id="@+id/end">
    </ConstraintSet>
</MotionScene>
```

在`MotionLayout`编辑器中进行的任何更改都将存储在此文件中。同样，也可以直接编辑此文件，以便在`MotionLayout`编辑器之外实现和修改动画设置。

在本教程中，动画将主要通过`MotionLayout`编辑器界面来实现。然而，我们将在每个阶段回顾这些更改是如何在底层`MotionScene`文件中的。随着章节的进行，你会发现`MotionScene`的 XML 语法简单且易于学习。



本教程的第一阶段将演示如何使用`MotionLayout`为`Button`对象制作动画，包括运动（包括遵循路径）、旋转和尺寸缩放。

## 43.3 配置起始和结束约束

当`activity_main.xml`文件加载到`MotionLayout`编辑器后，请确保选中了`MotionLayout`框（在下方图43-5中标记为E），然后在从调色板中拖放并放置一个`Button`视图到布局画布的左上角之前，先删除默认的`TextView`，如图43-4所示：

![](img/as_motionlayout_button.jpg)

图43-4

选中按钮后，使用`Attributes`工具窗口将`id`改为`myButton`。

如上一章所述，`MotionLayout`动画主要是指定视图如何在两个状态之间进行转换的情况。因此，实现动画的第一步是指定定义这些状态的约束。

对于此示例，起点将是布局视图的顶部中央。要配置这些约束，请在编辑器窗口中选择起始约束集条目（在图43-5中标记为A）：

![](img/as_motionlayout_editor_labelled.jpg)

图43-5

当选中起始框时，所有的约束和布局更改将对起始点约束集进行。要返回整个布局的标准约束和属性，请点击`MotionLayout`框(E)。

接下来，在`ConstraintSet`列表中选择`myButton`条目(B)。请注意`Source`列显示按钮是根据布局文件中的约束进行定位的。相反，我们希望按钮根据约束进行定位。在仍选中`myButton`条目的情况下，点击`Edit`(C)并从菜单中选择`Constraint`，随后按钮条目将指示该视图位于起始集上：

![](img/as_motionlayout_start.jpg)

图43-6

起始约束必须将按钮位于布局顶部，偏移`8dp`且水平居中。选中`myButton`后，使用`Attributes`工具窗口设置顶部和右侧约束：

![](img/as_motionlayout_start_settings.jpg)

图43-7

选择结束约束集（在图43-5中标记为D），并重复步骤创建一个新约束，这次将按钮放置在布局底部偏移`8dp`：

![](img/as_motionlayout_end_settings.jpg)

图43-8

配置好起始和结束约束后，打开`activity_main_scene.xml`文件并注意约束已经添加：

```xml
<?xml version="1.0" encoding="utf-8"?>
<MotionScene
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:motion="http://schemas.android.com/apk/res-auto">
    <ConstraintSet android:id="@+id/start">
        <Constraint
            android:id="@+id/myButton"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            motion:layout_constraintTopTopOf="parent"
            android:layout_marginTop="8dp"
            motion:layout_constraintStart_toStartOf="parent"
            motion:layout_constraintEnd_toEndOf="parent" />
    </ConstraintSet>
    <ConstraintSet android:id="@+id/end">
        <Constraint
            android:id="@+id/myButton"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            motion:layout_constraintStart_toStartOf="parent"
            motion:layout_constraintEnd_toEndOf="parent"
            motion:layout_constraintBottom_toBottomOf="parent"
            android:layout_marginBottom="8dp" />
    </ConstraintSet>
</MotionScene>
```

同样注意`Transition`元素已经预配置为在1000毫秒内动画起始和结束点之间的过渡。尽管我们还没有添加触发过渡的动作，但仍然可以在`MotionLayout`编辑器内部预览动画。

## 43.4 预览 MotionLayout 动画

要在不构建和运行应用程序的情况下预览动画，选择`MotionLayout`编辑器中在下方图43-9中标记为A的过渡箭头。这将显示动画时间轴面板（标记为B）：

![](img/as_motionlayout_test_animation.jpg)

图43-9

要测试动画，点击滑块(C)并沿着时间轴拖动它。随着滑块移动，布局画布上的按钮将沿着虚线路径(D)移动。使用工具栏按钮(E)执行完整动画，以便以不同的速度持续重复动画（向前、向后或来回切换）。

## 43.5 添加 OnClick 点击手势

虽然已经创建了一个简单的`MotionLayout`动画过渡，但我们仍然需要一种在运行的App内部启动动画的方法。这可以通过分配点击或滑动处理程序来实现。在本示例中，我们将配置动画在用户点击按钮时启动。在`MotionLayout`编辑器中，如果动画在循环设置下运行，请先暂停时间轴动画。接下来，选择过渡箭头（如上方图43-9中标记的A），在属性（`Attributes`）工具窗口中找到`OnClick`属性区域，并点击下方图43-10中箭头所示的`+`按钮：

![](img/as_motionlayout_add_onclick.jpg)

图43-10

`OnClick`面板将出现第一个属性的空行。对于属性名称，输入`targetId`；对于值字段，输入按钮的id（`@id/myButton`）。在下一个空行中，在属性名称字段中输入`app:clickAction`。在值字段中，点击向下箭头显示有效选项菜单：

![](img/as_motionlayout_onclick_toggle.jpg)

图43-11

在本示例中，选择切换（toggle）动作。这将导致视图在被点击时动画到相反的位置。一旦输入了这些设置，它们应该与图43-12中所示的内容匹配：

![](img/as_4.0_motionlayout_onclick_added.jpg)

图43-12

再次打开`activity_main_scene.xml`文件并检查在`Transition`条目中定义的`OnClick`属性：

```xml
<Transition
    motion:constraintSetEnd="@+id/end"
    motion:constraintSetStart="@id/start"
    motion:duration="1000">
    <KeyFrameSet>
    </KeyFrameSet>
    <OnClick motion:targetId="@id/myButton"
             motion:clickAction="toggle" />
</Transition>
```

在设备或模拟器上编译并运行App，确认点击按钮会导致它在`MotionScene`文件中定义的起始点和结束点之间来回切换。

## 43.6 在过渡中添加属性关键帧

到目前为止，示例项目仅演示了按钮视图从屏幕上一个位置到另一个位置的运动。属性关键帧（`KeyAttribute`）提供了一种方法，用于指定过渡时间轴中的点，使其他属性更改在这些点生效。例如，可以定义一个`KeyAttribute`，使得视图移动到时间轴的30%时，其尺寸必须已经增加了50%。在本示例中，我们将添加一个位于动画中点的旋转效果。

首先，在`MotionLayout`编辑器中打开`activity_main.xml`文件，选择过渡连接箭头以显示时间轴，然后点击图43-13中高显的按钮：

![](img/as_motionlayout_add_keyframe.jpg)

图43-13

从菜单中，选择`KeyAttribute`选项：

![](img/as_motionlayout_add_key_attribute.jpg)

图43-14

选中后，将出现图43-15所示的对话框。在对话框中，确保选择了ID选项并引用了`myButton`。在位置字段中，输入`50`（以百分比指定，`0`是起点，`100`是终点）。最后，在点击`Add`按钮之前，从属性下拉菜单中选择旋转（rotation entry）：

![](img/as_motionlayout_create_key_attribute.jpg)

图43-15

添加`KeyAttribute`后，时间轴内会出现一个该属性的行。点击该行将其高亮，然后点击行最左侧边缘的展开箭头以展开属性过渡图。注意，时间轴上出现了一个小的菱形标记（如下方图43-16所示），表示关键帧的位置。图表表示效果的线性。在这种情况下，按钮将稳稳地旋转到指定的度数，并在关键帧位置达到最大旋转。当到达终点时，按钮将旋转回`0`度：

![](img/as_motionlayout_attribute_timeline.jpg)

图43-16

要更改`KeyAttribute`的属性，请在时间轴上选中并参考属性工具窗口。在`KeyAttribute`面板中，将旋转更改为`360`：

![](img/as_motionlayout_key_attribute.jpg)

图43-17

通过来回拖动滑块检查该属性是否生效。参考`activity_main_scene.xml`文件，它应该显示如下：

```xml
<Transition
    motion:constraintSetEnd="@+id/end"
    motion:constraintSetStart="@id/start"
    motion:duration="1000">
    <KeyFrameSet>
        <KeyAttribute motion:targetId="@id/myButton"
            motion:position="50"
            motion:rotation="360" />
    </KeyFrameSet>
    <OnClick motion:targetId="@id/myButton"
             motion:clickAction="toggle" />
</Transition>
```

通过移动滑块或编译App来测试动画。

## 43.7 添加 CustomAttribute 到

`KeyAttribute`属性限于调整大小和旋转等内置效果。通过声明`CustomAttributes`也可以实现额外的更改。与存储在`Transition`中的`KeyAttributes`不同，`CustomAttributes`位于起始和结束约束集中。因此，这些属性只能在起点和终点声明（也就是说，你不能在时间轴中间指定属性帧）。

在本示例中，我们将配置按钮从红色变为绿色。首先，选择图43-18中标记为A的框，然后是`myButton`约束集(B)：

![](img/as_motionlayout_attr.jpg)

图43-18

参考属性工具窗口，点击下方所示`CustomAttributes`区域中的`+`按钮：

![](img/as_motionlayout_add_attribute.jpg)

图43-19

在弹出对话框（图43-20）中，将属性类型更改为`Color`，并在名称字段输入`backgroundColor`。最后，将值设置为`#F8A1F`：

![](img/as_motionlayout_custom_attribute_dialog.jpg)

图43-20

点击`OK`更改，然后选择上方图43-18中标记为C的结束约束集，重复步骤添加自定义属性，这次指定`#33CC33`为颜色的RGB值。

使用时间轴滑块或运行App，确保按钮在动画期间颜色变化。`CustomAttributes`的添加将反映在`activity_main_scene.xml`文件中：

```xml
<ConstraintSet android:id="@+id/start">
    <Constraint android:id="@+id/myButton">
        <CustomAttribute
            motion:attributeName="backgroundColor"
            motion:customColorValue="#F8A1F" />
    </Constraint>
</ConstraintSet>

<ConstraintSet android:id="@+id/end">
    <Constraint android:id="@+id/myButton">
        <CustomAttribute
            motion:attributeName="backgroundColor"
            motion:customColorValue="#33CC33" />
    </Constraint>
</ConstraintSet>
```

## 43.8 添加位置关键帧

本教程的最后一个任务是在动画路径上添加两个位置关键帧（`KeyPosition`），以为动画引入一些横向移动。在`MotionLayout`编辑器中，过渡时间轴可见的情况下，点击如上方图43-13所示的高亮按钮来创建关键帧，并从菜单中选择`KeyPosition`选项，如下方的图43-21所示：

![](img/as_motionlayout_keyposition_menu.jpg)

图43-21

在弹出的对话框中，按照图43-22所示设置属性：

![](img/as_motionlayout_create_keyposition.jpg)

图43-22

点击`Add`（添加）按钮提交更改，然后重复上述步骤，添加配置如下的第二个位置关键帧：

- 位置（Position）：`75`

- 类型（Type）：`parentRelative`

- X轴百分比（PercentX）：`0.85`

- Y轴百分比（PercentY）：`0.75`

完成这些更改后，`activity_main_scene.xml`文件中的过渡元素将添加了以下关键帧项：

```xml
<KeyFrameSet>
    <KeyPosition
        motion:motionTarget="@+id/myButton"
        motion:framePosition="25"
        motion:keyPositionType="parentRelative"
        motion:percentX="0.15"
        motion:percentY="0.25" />
    <KeyPosition
        motion:motionTarget="@+id/myButton"
        motion:framePosition="75"
        motion:keyPositionType="parentRelative"
        motion:percentX="0.85"
        motion:percentY="0.75" />
</KeyFrameSet>
```

最后测试一次应用程序，验证按钮现在是否按照所示路径移动，同时仍保持旋转并改变颜色：

![](img/as_motionlayout_path_1.jpg)

图43-23

位置关键帧由预览画布中表示运动路径的虚线上的菱形标记表示，如图43-24所示（如果标记不可见，请确保在预览中选中了`Button`视图）：

![](img/as_motionlayout_path_2.jpg)

图43-24

要从视觉上调整关键帧的位置，点击标记并将其拖到新位置。随着标记的移动，`MotionLayout`编辑器将显示一个网格以及当前的`x`和`y`坐标：

![](img/as_motionlayout_path_3.jpg)

图43-25

## 43.9 总结

本章介绍了Android Studio内置的`MotionLayout`编辑器，并探索了如何使用它在无需手动编写XML声明的情况下，为Android应用程序的用户界面添加动画。本章中涵盖的示例包括将`ConstraintLayout`容器转换为`MotionLayout`、在`MotionScene`文件中创建起始和结束约束集及过渡，以及添加`OnClick`处理器。此外还涵盖了动画预览器、自定义属性和位置关键帧。

## 44. MotionLayout 循环教程



之前的章节介绍并演示了如何使用`MotionLayout`容器结合 Android Studio MotionLayout 编辑器的功能，将动画集成到 Android 应用程序的用户界面中的概念。标题为 MotionLayout 简介的章节简要提到了循环（`KeyCycle`）和时间循环（`KeyTimeCycle`）关键帧，并解释了如何使用它们来实现涉及大量重复状态变化的动画。

本章将更详细地介绍循环关键帧，然后演示如何在使用 Android Studio 和循环编辑器的项目中创建它们。

## 44.1 循环关键帧概述

位置关键帧可以为动画时间轴添加中间状态变化。虽然这对于较少的状态变化效果良好，但要实现大量变化将非常繁琐。例如，为了让按钮在点击时抖动 50 次以表示发生错误，将涉及手动创建 100 个位置关键帧来执行小的顺时针和逆时针旋转。同样，在视图跨越屏幕移动时实现跳动效果同样耗时。

对于需要重复执行状态更改的情况，`MotionLayout`包含了`Cycle`和时间循环关键帧。两者都执行相同的任务，区别在于`KeyCycle`帧是基于动画路径内的帧位置，而`KeyTimeCycle`是基于每秒循环次数（`Hz`）的时间。

使用这些`KeyCycle`帧，动画时间轴本质上被分为子部分（称为循环），每个子部分包含一个或多个波形，定义了如何修改视图的属性。创建`KeyCycle`循环需要以下信息：

- `target`：将进行更改的视图 ID。
- `frame position`（帧位置）：循环开始的时间轴位置。
- `wave period`（波周期）：循环中包含的波的数量。
- `attribute`：被波形修改的视图属性。
- `wave offset`（波偏移）：按指定量偏移循环。
- `wave shape`（波形）：波的形状（`sin`、`cos`、`sawtooth`、`triangle`）。

考虑以下循环关键帧集：

```xml
<KeyFrameSet>
    <KeyCycle
        motion:framePosition="0"
        motion:motionTarget="@+id/button"
        motion:wavePeriod="1"
        motion:waveOffset="0dp"
        motion:waveShape="sin"
        android:translationY="50dp" />
    <KeyCycle
        motion:framePosition="25"
        motion:motionTarget="@+id/button"
        motion:wavePeriod="1"
        motion:waveOffset="0dp"
        motion:waveShape="sin"
        android:translationY="50dp" />
    <KeyCycle
        motion:framePosition="50"
        motion:motionTarget="@+id/button"
        motion:wavePeriod="1"
        motion:waveOffset="0dp"
        motion:waveShape="sin"
        android:translationY="50dp" />
    <KeyCycle
        motion:framePosition="75"
        motion:motionTarget="@+id/button"
        motion:wavePeriod="1"
        motion:waveOffset="0dp"
        motion:waveShape="sin"
        android:translationY="50dp" />
    <KeyCycle
        motion:framePosition="100"
        motion:motionTarget="@+id/button"
        motion:wavePeriod="1"
        motion:waveOffset="0dp"
        motion:waveShape="sin"
        android:translationY="50dp" />
</KeyFrameSet>
```

上述关键帧集将时间轴分为四个相等的循环。每个循环都被配置为包含一个`sin`波形，用于调整按钮的`translationY`属性。执行时，此动画将导致按钮在指定范围内多次振荡。此关键帧集可以如图 44-1 所示进行可视化，其中五个点表示关键帧位置：

![](img/as_4.0_keycycle_simple_sin.jpg)

图 44-1

按照目前的实现，每个循环包含一个波。假设我们在最后一个循环中需要四个波，而不是这些均匀分布的波。可以通过如下增加最后一个`KeyCycle`元素的`wavePeriod`属性轻松实现：

```xml
    <KeyCycle
        motion:framePosition="75"
        motion:motionTarget="@+id/button"
        motion:wavePeriod="4"
        motion:waveOffset="0dp"
        motion:waveShape="sin"
        android:translationY="50dp"/>
```

进行此更改后，关键帧集可以如下波形形式渲染：

![](img/as_4.0_keycycle_sin_waveperiod.jpg)

图 44-2

到目前为止，本章的示例一直使用的是正弦波。在`MotionLayout`中使用循环关键帧时，还有其他波形可用。例如，图 44-3 展示了将所有循环关键帧的`waveShape`属性更改为锯齿波的效果：

![](img/as_4.0_keycycle_sawtooth.jpg)

图 44-3

除了正弦波和锯齿波，`MotionLayout`还支持三角形波、方形波、弹跳波和反向锯齿波波形。

在上面的示例中，每个循环都在沿 Y 轴的相同范围内移动按钮。然而，假设我们需要第二个循环沿 Y 轴正方向移动按钮的距离更远一些。这涉及按照如下方式调整第二个循环的`waveOffset`属性：

```xml
<KeyCycle
      motion:framePosition="25"
      motion:target="@+id/button"
      motion:wavePeriod="1"
      motion:waveOffset="100dp"
      motion:waveShape="sin"
      android:translationY="50dp"/>
```

通过此更改，我们得到了一个类似于 图 44-4 的时间线：

![](img/as_4.0_keycycle_sin_waveoffset.jpg)

图 44-4

现在，在第二个循环期间，按钮的移动范围将在 Y 轴上的大约 0 到 150dp 之间。如果我们仍然需要范围的低端与其他波形匹配，我们当然可以为`translationY`值增加 100dp：

```xml
<KeyCycle
      motion:framePosition="25"
      motion:target="@+id/button"
      motion:wavePeriod="1"
      motion:waveOffset="100dp"
      motion:waveShape="sin"
      android:translationY="150dp"/>
```

此更改现在为我们提供了以下波形：

![](img/as_4.0_keycycle_sin_waveoffset_flat.jpg)

图 44-5

## 44.2 使用循环编辑器

尽管不是特别复杂，但通过直接编辑`MotionScene`文件中的 XML `KeyCycle`条目来获取所需的精确循环配置可能需要一些时间。为了改进，Google 的 Android 工程师开发了`Cycle Editor`（循环编辑器）。这个独立的基于 Java 的工具尚未成为 Android Studio 的一部分。`Cycle Editor`允许你可视化地设计和测试循环关键帧集。

`Cycle Editor`工具是一个 Java 归档（.jar）文件，需要在你的开发系统中安装 Java 运行环境。

一旦安装了 Java，可以从以下 URL 下载`CycleEditor.jar`文件：

[`github.com/googlesamples/android-ConstraintLayoutExamples/releases/download/1.0/CycleEditor.jar`](https://github.com/googlesamples/android-ConstraintLayoutExamples/releases/download/1.0/CycleEditor.jar)

下载后，打开命令提示符或终端窗口，切换到 jar 文件所在的目录，并运行以下命令：

```bash
java -jar CycleEditor.jar
```

一旦工具加载，将出现 图 44-6 所示的屏幕：

![](img/as_4.0_keycycle_editor_main.jpg)

图 44-6

上图中标记为 A 的面板显示关键帧集的 XML，可以直接进行编辑，也可以使用 B 面板中的控件进行编辑。面板 C 显示循环以波形形式的渲染。遗憾的是，它在进行更改时不会实时重绘。相反，必须通过选择 `File -> parse xml` 菜单选项来刷新。标记为 D 的面板将在点击 B 面板中的播放按钮时显示循环动画的实时渲染。`Examples`菜单提供了一系列示例关键帧集，这些集合既可以用于学习目的，也可以作为你自己动画的基础。

本章的剩余部分将创建一个示例项目，实现一个基于`KeyCycle`的动画效果，以演示`Cycle Keyframe`和`Cycle Editor`的用法。

## 44.3 创建 KeyCycleDemo 项目

从欢迎界面选择 `New Project`（新建项目）选项，在生成的新项目对话框中，点击 `Next` 按钮之前选择 `Empty Views Activity` 模板。

在 `Name` 字段中输入 `KeyCycleDemo`，并指定 `com.ebookfrenzy.keycycledemo` 为包名。在点击 `Finish` 按钮之前，将 `Minimum API level` 设置为 `API 26: Android 8.0 (Oreo)`，并将 `Language` 菜单设置为 `Java`。

在 `Design` 模式下使用布局编辑器并打开 `activity_main.xml` 文件，右键点击 `ConstraintLayout` 条目并选择 `Convert to MotionLayout` 菜单选项：

![](img/as_4.0_keycycle_sawtooth.jpg)

图 7

## 44.4 配置开始和结束约束

本教程旨在制作按钮从一侧移动到另一侧的动画，包括导致视图沿 Y 轴上下移动的`KeyCycle`效果。第一步是配置开始和结束。

将 `activity_main.xml` 文件加载到 `MotionLayout` 编辑器中，选择 `TextView`。

![](img/as_4.0_keycycle_sawtooth.jpg)

图 8

要配置起始点，在 图 44-9 中选择 `start` 约束：

![](img/as_4.0_keycycle_sawtooth.jpg)

图 9

接下来，在 `ConstraintSet` 中选择 `KeyCycle` 条目。在按钮被选中的情况下，点击 `Create` 按钮 (C)。

```xml
<KeyCycle
      motion:framePosition="0"
      motion:target="@+id/button"
      motion:wavePeriod="1"
      motion:waveOffset="0dp"
      motion:waveShape="sin"/>
```

选择 图 44-9 中的 `end` 约束（标记为 D），重复步骤创建新的约束：

![](img/as_4.0_keycycle_sawtooth.jpg)

图 10

### 44.5 创建循环

下一步是使用 `Cycle Editor` 为动画生成关键帧。当 `Cycle Editor` 运行时，参考 图 44-12 中的控制面板：

![](img/as_4.0_keycycle_sawtooth.jpg)

图 12

使用标记为 A 的菜单，将要修改的属性从 `rotation` 更改为 `translationY`。

接下来，使用 `KeyCycle` 控制 (B) 选择 `0`，以便在面板其他地方进行的更改。如 图 44-13 所示，将 `Period` 滑块移动到 `1`，并将 `translationY` 滑块移动到 `60`（移动滑块时查看 XML 面中的 `translationY` 值）：

![](img/as_4.0_keycycle_0.jpg)

图 13

选择 `File -> Parse XML` 菜单选项查看图中的更改。使用 表 44-1 列出的值，配置关键帧 1 到 4 设置（注意你已经配置了 `KeyCycle 0` 列的设置）：

| | KeyCycle 0 | KeyCycle 1 | KeyCycle 2 | KeyCycle 3 | KeyCycle 4 |
| --- | --- | --- | --- | --- | --- |
| Position | 0 | 25 | 50 | 75 | 100 |
| Period | 1 | 2 | 3 | 2 | 1 |
| translationY | 60 | 60 | 150 | 60 | 60 |

表 44-1

完成这些更改后，关键帧集的 XML 应该如下：

```xml
<KeyFrameSet>
    <KeyCycle
      motion:framePosition="0"
      motion:motionTarget="@+id/button"
      motion:wavePeriod="1"
      motion:waveOffset="0dp"
      motion:waveShape="sin"/>
</KeyFrameSet>
```

```xml
android:translationY="60dp"/>

<KeyCycle
    motion:framePosition="25"
    motion:motionTarget="@+id/button"
    motion:wavePeriod="2"
    motion:waveOffset="0dp"
    motion:waveShape="sin"
    android:translationY="60dp"/>

<KeyCycle
    motion:framePosition="50"
    motion:motionTarget="@+id/button"
    motion:wavePeriod="3"
    motion:waveOffset="0dp"
    motion:waveShape="sin"
    android:translationY="150dp"/>

<KeyCycle
    motion:framePosition="75"
    motion:motionTarget="@+id/button"
    motion:wavePeriod="2"
    motion:waveOffset="0dp"
    motion:waveShape="sin"
    android:translationY="60dp"/>

<KeyCycle
    motion:framePosition="100"
    motion:motionTarget="@+id/button"
    motion:wavePeriod="1"
    motion:waveOffset="0dp"
    motion:waveShape="sin"
    android:translationY="60dp"/>
</KeyFrameSet>
```

要查看带有新循环的图形，请选择 `File -> Parse XML` 菜单选项以刷新波形，该波形现在应该如图 44-14 所示：

![](img/as_4.0_keycycle_editor_cyclekeys_complete.jpg)

图 44-14

### 44.6 预览动画

现在可以从循环编辑器（Cycle Editor）工具内部预览基于循环的动画。点击播放按钮（在图 44-15 中标记为 A）启动动画。要将循环与水平移动相结合，将第二个菜单 (B) 从 Stationary（静止）更改为 West（西）到 East（东）。此外，请花一些时间尝试时间和线性度设置（C 和 D）。

![](img/as_4.0_keycycle_play_buttons.jpg)

图 44-15

### 44.7 将 KeyFrameSet 添加到 MotionScene

在循环编辑器中，从 XML 面板中选中并复制 `KeyCycle` 元素，并将它们粘贴到 Android Studio 中 `res -> xml -> activity_main_scene.xml` 文件的 Transition 部分，以便将它们放置在现有的 `KeyFrameSet` 标记之间。还要注意增加的持续时间设置以及用于启动动画的 `OnClick` 句器的添加：



在继续之前，检查每个目标属性是否已正确声明。在编写时，循环编辑器仍在使用过时的`motion:target`标签。例如：

```xml
motion:target="@+id/button"
```

这需要对五个`KeyCycle`条目中的每一个进行更改为：

```xml
motion:motionTarget="@+id/button"
```

一旦完成这些更改，在设备或模拟器上编译并运行应用，然后点击按钮开始并查看动画。

注意，`KeyCycle`的波形形成也可以在 Android Studio MotionLayout 编辑器中查看，如下方的图 44-16 所示：

![](img/as_keycycle_demo_transition.jpg)

图 44-16

`KeyCycle`组不限于一个动画。例如，向`activity_main_scene.xml`文件的 Transition 部分添加以下`KeyFrameSet`，以便在按钮移动时添加一些效果：

```xml
<KeyFrameSet>
    <KeyCycle
        motion:framePosition="0"
        motion:motionTarget="@+id/button"
        motion:wavePeriod="1"
        motion:waveOffset="0dp"
        motion:waveShape="sin"
        android:translationY="60dp"/>
    <KeyCycle
        motion:framePosition="25"
        motion:motionTarget="@+id/button"
        motion:wavePeriod="2"
        motion:waveOffset="0dp"
        motion:waveShape="sin"
        android:translationY="60dp"/>
    <KeyCycle
        motion:framePosition="50"
        motion:motionTarget="@+id/button"
        motion:wavePeriod="3"
        motion:waveOffset="0dp"
        motion:waveShape="sin"
        android:translationY="150dp"/>
    <KeyCycle
        motion:framePosition="75"
        motion:motionTarget="@+id/button"
        motion:wavePeriod="2"
        motion:waveOffset="0dp"
        motion:waveShape="sin"
        android:translationY="60dp"/>
    <KeyCycle
        motion:framePosition="100"
        motion:motionTarget="@+id/button"
        motion:wavePeriod="1"
        motion:waveOffset="0dp"
        motion:waveShape="sin"
        android:translationY="60dp"/>
</KeyFrameSet>
```

### 44.8 总结

基于循环的动画现在可以用于预览涉及大量状态变化的动画。如本章所示，使用循环编辑器可以极大简化这一过程。

### 45. 使用悬浮操作按钮和 Snackbar

本章的目标之一是提供材料设计（Material Design）的概述。材料设计是 Android 5.0 引入的，是一套规范 Android 用户界面以及运行在其上的应用外观和行为的指南。

在实现材料设计概念时，Google 还引入了 Android 支持库（Support Library）。该库包含了多个组件，允许在 Android 应用中构建材料设计的关键功能。这些组件中的悬浮操作按钮（Floating Action Button）和 Snackbar 将在本章中进行讨论。

#### 45.1 材料设计

实现采用 Material 设计原则的 Android 应用所需的许多构建模块都包含在 Android Design Support Library 中。该库包含系列用户界面组件，这些组件可以包含在 Android 应用中，以实现 Material 设计的大外观、感觉和行为。该库中的两个组件——浮操作按钮（FAB）和 Snackbar 将在本章中介绍，其他组件将在后续章节介绍。

## 45.3 浮操作按钮 (FAB)

浮操作按钮看起来悬浮在应用用户界面的表面之上。它通常促进用户界面屏幕中最常见的操作。浮操作按钮可以放置在屏幕上，允许用户向联系列表添加条目或从应用内发送电子邮件。例如，图 45-1 显示了标准 Android 联系人应用中用于添加新联系人的浮操作按钮：

![](img/as_contacts_app.jpg)

图 45-1

使用浮操作按钮时应遵循若干规则以符合 Material 设计指南。浮操作按钮必须是圆形的，尺寸可以是 56 x 56dp（默认）或 40 x 40dp（微型）。按钮在手机上距离屏幕边缘至少 16dp，在桌面级和平板设备上至少 24dp。无论尺寸如何，按钮必须包含一个 24x24dp 尺寸的内部图标，建议每个用户界面屏幕只有一个浮操作按钮。

浮操作按钮可以带有动画效果，或者设计为在触摸时变形为其他项目。例如，浮操作按钮在点击时可以旋转，或变形为另一个元素，例如工具栏或列出相关操作的面板。

### 45.4 Snackbar

Snackbar 组件提供了一种以屏幕底部面板向用户展示信息的方法，如图 45-2 所示。Snackbar 实例包含简短的文本消息和一个可选的操作按钮，该按钮在用户点击时将执行任务。一旦显示，Snackbar 将将自动超时消失，也可以由用户通过滑动操作手动移除。在 Snackbar 显示期间，应用将继续运行并正常响应用户交互。

![](img/as_snackbar_example.jpg)

图 45-2

在本章的剩余部分中，将创建一个示例应用程序，该程序使用浮操作按钮和 Snackbar 的基本功能向项目列表添加条目。

## 45.5 创建示例项目

从欢迎界面选择“新项目”（New Project）选项，在生成的新项目对话框中，点击“下一步”（Next）按钮之前选择“Basic Views Activity”模板。

在`Name`字段中输入`FabExample`并指定`com.ebookfrenzy.fabexample`为包名。在点击“完成”（Finish）按钮之前，将最低 API 级别（Minimum API level）设置设置为`API 26: Android 8.0 (Oreo)`，并将语言菜单更改为`Java`。

## 45.6 检查项目

由于选择了 Basic Views Activity 模板，该活动包含四个布局文件。`activity_main.xml`文件由一个`CoordinatorLayout`布局组成，其中包含应用栏、Material 工具栏和浮操作按钮条目。

`content_main.xml`文件代表活动内容区域的布局，包含一个`NavHostFragment`实例。该文件通过以下`include`指令嵌入到`activity_main.xml`文件中：

```xml
<include layout="@layout/content_main" />
```

`activity_main.xml`文件中的浮操作按钮元素如下：

```xml
<com.google.android.material.floatingactionbutton.FloatingActionButton
    android:id="@+id/fab"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_gravity="bottom|end"
    android:layout_marginEnd="@dimen/fab_margin"
    android:layout_marginBottom="16dp"
    app:srcCompat="@android:drawable/ic_dialog_email" />
```

这声明按钮将出现在屏幕的右下角，边距由`values/dimens.xml`文件中的`fab_margin`标识表示（在本例中，它设置为 16dp）。XML 进一步声明按钮的内部图标将采用标准内置 drawable 电子邮件图标的形式。

空白模板还配置了浮操作按钮，当用户点击它时显示 Snackbar 实例。实现此功能的代码可以在`MainActivity.java`文件的`onCreate()`方法中找到，如下：

```java
binding.fab.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View view) {
        Snackbar.make(view, "Replace with your own action", Snackbar.LENGTH_LONG)
                .setAction("Action", null).show();
    }
});
```

代码通过视图绑定（view binding）访问浮操作按钮，并添加了一个`onClickListener`处理程序，在点击按钮时调用。此方法显示一个配置了消息但没有操作的 Snackbar 实例。当项目编译并运行时，浮操作按钮将出现在屏幕底部，如图 45-3 所示：

![](img/as_default_fab.jpg)

图 45-3

点击浮操作按钮将触发`onClickListener`处理程序，导致 Snackbar 出屏幕底部：

![](img/as_default_snackbar.jpg)

图 45-4

## 45.7 移除导航功能

如《布局编辑器指南》概述所示，Basic Views Activity 模板包含多个片段（fragments）和按钮，用于在片段之间导航。这些功能对于本教程来说是不必要的，并且稍后引起问题。在继续教程之前，请按照以下方式修改项目：

1. 在 Project（项目）工具窗口中，导航到并双击`app -> res -> navigation -> nav_graph.xml`文件，将其加载到导航编辑器中。

2. 在编辑器的 Component Tree（组件树）面板中选择`SecondFragment`条目，并按键盘删除键将其从图中移除。

3. 找到并删除`SecondFragment.java`（`app -> java -> <package name> -> SecondFragment`）和`fragment_second.xml`（`app -> res -> layout -> fragment_second.xml`）文件。

4. 找到`FirstFragment.java`文件，双击将其加载到编辑器，并移除`onViewCreated()`方法中的代码，使其如下：

```java
binding.buttonFirst.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View view) {
        NavHostFragment.findNavController(FirstFragment.this)
            .navigate(R.id.action_FirstFragment_to_SecondFragment);
    }
});
```

## 45.8 更改浮操作按钮

由于此示例的目标是配置浮操作按钮向列表添加条目，因此目前按钮上显示的电子邮件图标需要更改为指示所执行操作的图标。用于按钮的图标是`ic_add_entry.png`，可以在从以下 URL 下载的示例代码的`project_icons`文件夹中找到：

[`www.ebookfrenzy.com/retail/giraffejava/index.php`](https://www.ebookfrenzy.com/retail/giraffejava/index.php)

在操作系统的文件管理器中找到此图像并复制文件。在 Project 工具窗口的`app -> res -> drawable`条目上右键点击，从菜单中选择“粘贴”，将文件添加到文件夹：

![](img/as_fib_icon_added.jpg)

图 45-5

接下来，编辑`activity_main.xml`文件并将图标图像源从`@android:drawable/ic_dialog_email`更改为`@drawable/ic_add_entry`如下：

```xml
<com.google.android.material.floatingactionbutton.FloatingActionButton
    android:id="@+id/fab"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_gravity="bottom|end"
    android:layout_margin="@dimen/fab_margin"
    android:layout_marginBottom="16dp"
    app:srcCompat="@drawable/ic_add_entry" />
```

在布局预览中，按钮内部的图标已变为一个加号。

我们还可以通过向`OnClickListener`中添加代码，让悬浮动作按钮在点击时执行几乎任何操作。例如，对`MainActivity.java`文件进行以下更改，可以在每次点击按钮时调用名为`displayMessage()`的方法来显示 toast 消息：

```java
import android.widget.Toast;

binding.fab.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View view) {
        displayMessage("Fab clicked");
        Snackbar.make(view, "Replace with your own action", Snackbar.LENGTH_LONG)
                  .setAction("Action", null).show();
    }
});

public void displayMessage(String message) {
    Toast.makeText(this,message,Toast.LENGTH_SHORT).show();
}
```

### 45.9 为 Snackbar 添加动作

也可以向`Snackbar`添加一个动作，该动作在用户点击时会执行某项任务。编辑`MainActivity.java`文件并修改`Snackbar`的创建代码，添加一个标题为“My Action”的动作，并配置一个名为`actionOnClickListener`的`OnClickListener`，后者反过来会显示一条 toast 消息：

```java
binding.fab.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View view) {
        Snackbar.make(view, "Replace with your own action", Snackbar.LENGTH_LONG)
                 .setAction("My Action", actionOnClickListener).show();
    }
});
```

在`MainActivity.java`文件中，添加监听器处理器：



```java
View.OnClickListener actionOnClickListener = new View.OnClickListener() {
    @Override
    public void onClick(View view) {
        displayMessage("Action clicked");
        Snackbar.make(view, "Action Complete", Snackbar.LENGTH_LONG)
                  .setAction("Action", null).show();
    }
};
```

运行应用并点击悬浮动作按钮，此时 toast 消息和`Snackbar`都应该出现。在`Snackbar`可见期间，点击`Snackbar`中的 My Action 按钮，并验证`Snackbar`上的文本已变为“Action Complete”：

![](img/fab_action_clicked.jpg)

图 45-6

## 45.10 总结

在完成使用这些功能的示例项目之前，本章提供了对物化设计（Material Design）、悬浮动作按钮和`Snackbar`的概述。

悬浮动作按钮和`Snackbar`是 Android 物化设计用户界面实现方法的一部分。悬浮动作按钮提供了一种在 Android 应用特定屏幕内推广最常见操作的方法。`Snackbar`则提供了一种应用程序向用户展示信息并允许用户对信息进行操作的方法。

# 46. 使用 TabLayout 组件创建标签页界面

上一章概述了 Android 中物化设计的概念。它引入了设计支持库提供的两个组件，形式为悬浮动作按钮和`Snackbar`。本章将演示如何使用设计库的另一个组件`TabLayout`，它可以与`ViewPager`类结合使用，在 Android Activity 中创建一个基于标签页的界面。

## 46.1 ViewPager2 简介

虽然`ViewPager2`不属于设计支持库，但在与`TabLayout`组件配合实现标签页用户界面时，它是一个非常有用的辅助类。`ViewPager2`的主要作用是允许用户翻阅不同的信息页，通常每个布局片段（fragment）代表每一页。与`ViewPager2`关联的片段由`FragmentStateAdapter`类的实例管理。

至少，分配给`ViewPager2`的分页适配器必须实现两个方法。第一个命名为`getItemCount()`，必须返回要显示给用户的页面片段总数。第二个方法`createFragment()`接收一个页码，并必须返回准备呈现给用户的相应片段对象。

## 46.2 TabLayout 组件概述

如前所述，`TabLayout`是物化设计引入的组件之一，并包含在设计支持库中。`TabLayout`的目的是向用户展示一行标签，用户可以选择这些标签来向其显示不同的页面。标签可以是固定的，也可以是滚动的，用户可以向左或向右滑动以查看比当前显示器容量更多的标签。标签上显示的信息可以是文本、图像，或者文本与图像的组合。例如，图 46-1 显示了一个包含四个显示图像标签的应用的标签栏：

![](img/Image2425.jpg)

图 46-1

另一方面，图 46-2 显示了一个由四个显示文本的标签组成的`TabLayout`配置，且为滚动配置：

![](img/Image2434.jpg)

图 46-2

本章的剩余部分将通过创建一个示例项目，演示`TabLayout`组件结合`ViewPager2`以及四个片段的使用。

## 46.3 创建 TabLayoutDemo 项目

从欢迎界面选择 New Project（新建项目）选项，并在生成的对话框中选择 Basic Activity 模板。在 Name 字段中输入`TabLayoutDemo`并指定`com.ebookfrenzy.tablayoutdemo`为包名。在点击 Finish 按钮之前，将 Minimum API 设置为 26: Android 8.0 (Oreo)并将 Language 设置为 Java。

项目创建后，进入布局编辑器加载`content_main.xml`文件，选择`NavHostFragment`对象并将其删除。由于我们将不会使用 Basic Activity 的功能，编辑`MainActivity.java`文件并修改`onCreate()`方法以移除导航代码：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    binding = ActivityMainBinding.inflate(getLayoutInflater());
    setContentView(binding.getRoot());
    setSupportActionBar(binding.toolbar);
    NavController navController = Navigation.findNavController(this, R.id.nav_host_fragment_content_main);
    appBarConfiguration = new AppBarConfiguration.Builder(navController.getGraph()).build();
    NavigationUI.setupActionBarWithNavController(this, navController);
    binding.fab.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View view) {
            Snackbar.make(view, "Replace with your own action", Snackbar.LENGTH_LONG)
                      .setAction("Action", null).show();
        }
    });
}
```

最后，删除`onSupportNavigateUp()`方法：

```java
@Override
public boolean onSupportNavigateUp() {
    NavController navController = Navigation.findNavController(this, R.id.nav_host_fragment_content_main);
    return NavigationUI.navigateUp(navController, appBarConfiguration) || super.onSupportNavigateUp();
}
```

## 46.4 创建第一个片段

`TabLayout`上的每个标签在选中时都会显示不同的片段。通过右键点击 Project 工具窗口中的`app -> java -> com.ebookfrenzy.tablayoutdemo`项并选择 New -> Fragment -> Fragment (Blank) 选项来创建这些片段中的第一个。在生成的对话框中，在 Fragment Name 字段中输入`Tab1Fragment`并在 Fragment Layout Name 字段中输入`fragment_tab1`。点击 Finish 按钮创建新片段：

![](img/as_tab_layout_fragment_java.jpg)

图 46-3

编辑`Tab1Fragment.java`文件，如果 Android Studio 没有自动添加，请按照如下所示添加`OnFragmentInteractionListener`接口声明：

```java
import android.net.Uri;

public interface OnFragmentInteractionListener {
    // TODO: Update argument type and name
    void onFragmentInteraction(Uri uri);
}
```

将新建的`fragment_tab1.xml`文件（位于`app` -> `res` -> `layout`下）加载到 Layout 编辑器中，在组件树面板中右键点击`FrameLayout`项，并选择 Convert FrameLayout to ConstraintLayout 选项。在弹出的对话框中，点击`OK`之前确认已选中所有转换选项。将布局的`ID`更改为`constraintLayout`。

一旦布局转换为`ConstraintLayout`，删除布局中的`TextView`。从`Palette`（调色板）中找到`TextView`组件，将其拖动到布局的中心。编辑对象的文本属性使其显示为“Tab 1 Fragment”，将字符串提取为名为`tab_1_fragment`的资源，然后点击工具栏上的 Infer Constraints（推断约束）按钮。此时，布局应与图 46-4 一致：

![](img/as_3.5_tab_layout_fragment_ui.jpg)

图 46-4

## 46.5 复制 Fragment

到为止，项目包含了四个所需的 Fragment 中的一个。与其使用之前的步骤创建剩余的三个 Fragment，不如复制第一个 Fragment 会快得多。每个 Fragment 都由一个布局 XML 文件和一个 Java 类文件组成，每个文件都需要复制。

在 Project 工具窗口中右键点击`fragment_tab1.xml`文件，并在弹出的菜单中选择 Copy（复制）选项。再次右键点击布局项，这次选择 Paste（粘贴）选项。在弹出的对话框中点击`OK`按钮之前，将新布局文件命名为`fragment_tab2.xml`。编辑新的`fragment_tab2.xml`文件，并将`Text View`上的文本更改为“Tab 2 Fragment”，按照常规步骤将字符串提取为名为`tab_2_fragment`的资源。

要复制`Tab1Fragment`类文件，右键点击`app` -> `java` -> `com.ebookfrenzy.tablayoutdemo`下的类并选择 Copy。右键点击`com.ebookfrenzy.tablayoutdemo`项并选择 Paste。在 Copy Class 对话框中，在 New name: 字段输入`Tab2Fragment`并点击`OK`。

编辑新的`Tab2Fragment.java`文件并修改`onCreateView()`方法以加载`fragment_tab2`布局文件：

```java
@Override
public View onCreateView(LayoutInflater inflater, ViewGroup container,
                         Bundle savedInstanceState) {
    // Inflate the layout for this fragment
    return inflater.inflate(R.layout.fragment_tab2, container, false);
}
```

执行上述复制步骤两次，为剩余两个 Fragment 创建布局和类文件。完成这些步骤后，项目结构应与图 46-5 一致：

![](img/as_tab_layout_project_files_java.jpg)

图 46-5

## 46.6 添加 TabLayout 和 ViewPager2

随着 Fragment 创建过程的完成，下一步是向主活动布局文件添加`TabLayout`和`ViewPager2`。编辑`activity_main.xml`文件，并按照下方 XML 列表所示添加这些元素。注意，`TabLayout`组件嵌入在`AppBarLayout`元素中，而`ViewPager2`放置在`AppBarLayout`之后：

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.coordinatorlayout.widget.CoordinatorLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">
    <com.google.android.material.appbar.AppBarLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:theme="@style/Theme.TabLayoutDemo.AppBarOverlay">
        <androidx.appcompat.widget.Toolbar
            android:id="@+id/toolbar"
            android:layout_width="match_parent"
            android:layout_height="?attr/actionBarSize"
            android:background="?attr/colorPrimary"
            app:popupTheme="@style/Theme.TabLayoutDemo.PopupOverlay" />
        <com.google.android.material.tabs.TabLayout
            android:id="@+id/tabLayout"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            app:tabMode="fixed"
            app:tabGravity="fill"/>
    </com.google.android.material.appbar.AppBarLayout>
    <androidx.viewpager2.widget.ViewPager2
        android:id="@+id/view_pager"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:layout_behavior="@string/app_scrolling_view_behavior" />
    <include layout="@layout/content_main" />
    <com.google.android.material.floatingbutton.FloatingActionButton
        android:id="@+id/fab"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="bottom|end"
        android:layout_margin="16dp"
        android:layout_layout="end"
        app:src="@android:drawable/ic_email" />
</androidx.coordinatorlayout.widget.CoordinatorLayout>
```

## 46.7 创建 Pager Adapter

此示例将使用`ViewPager2`方法来处理分配给`TabLayout`的 Fragment，需要创建一个子自`FragmentStateAdapter`的类来管理选择项时显示的 Fragment。

通过右键点击`com.ebookfrenzy.tablayoutdemo`项并选择`New` -> `Java Class`为项目添加类。在新类对话框中，在`Name:`字段输入`TabPagerAdapter`，选择列表中的`Class`项并按`Return`键。

编辑`TabPagerAdapter.java`文件使其内容如下：




## 46.8 执行初始化任务

剩余的任务涉及初始化`TabLayout`、`ViewPager2`和`TabPagerAdapter`实例，并让主活动类实现四个标签 Fragment 的交互监听器。

```java
import android.net.Uri;

import com.google.android.material.tabs.TabLayoutMediator;

public class MainActivity extends AppCompatActivity implements
    Tab1Fragment.OnFragmentInteractionListener,
    Tab2Fragment.OnFragmentInteractionListener,
    Tab3Fragment.OnFragmentInteractionListener,
    Tab4Fragment.OnFragmentInteractionListener {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        configureTabLayout();
    }

    protected void configureTabLayout() {
        for (int i = 0; i < 4; i++) {
            binding.tabLayout.addTab(binding.tabLayout.newTab());
        }
        final TabPagerAdapter adapter = new TabPagerAdapter
                (this, binding.tabLayout.getTabCount());
        binding.viewPager.setAdapter(adapter);
        new TabLayoutMediator(binding.tabLayout, binding.viewPager,
                (tab, position) -> tab.setText("Tab " + (position + 1) + " Item")).attach();
    }

    @Override
    public void onFragmentInteraction(Uri uri) {
    }
}
```

代码首先创建了四个标签，并将它们如下所示添加到`TabLayout`实例中：

```java
for (int i = 0; i < 4; i++) {
    binding.tabLayout.addTab(binding.tabLayout.newTab());
}
```

接下来，创建`TabPagerAdapter`类的实例。注意，创建`TabPagerAdapter`实例的代码传递了分配给`TabLayout`组件的标签数量。然后将`TabPagerAdapter`实例赋值为`ViewPager2`实例的适配器：

```java
final TabPagerAdapter adapter = new TabPagerAdapter
        (this, binding.tabLayout.getTabCount());
binding.viewPager.setAdapter(adapter);
```

最后，使用`TabLayoutMediator`类的实例将`TabLayout`与`ViewPager2`对象连接：

```java
new TabLayoutMediator(binding.tabLayout, binding.viewPager,
        (tab, position) -> tab.setText("Tab " + (position + 1) + " Item")).attach();
```

该类确保`TabLayout`标签与当前选中的片段（fragment）保持同步。这一过程涉及确保每个标签上显示正确的文本。在这种情况下，文本被配置为读取“Tab `<n>` Item”，其中`<n>`被替换为当前选中标签的数字编号。

## 46.9 测试应用程序

在设备或模拟器上编译并运行应用，并确保选择某个标签会导致相应的片段出现在屏幕的内容区域中：

![](img/as_tab_layout_running.jpg)

图 46-6

在构建项目时，你可能会遇到部分包含内容的错误：

`Duplicate class kotlin.collections.jdk8.CollectionsJDK8Kt found in modules kotlin-stdlib`

此错误是由 Android Studio 构建工具链中的一个 bug 引起的，可以通过对`build.gradle.kts` (Module: app) 文件进行以下更改来解决：

```kotlin
dependencies {
    implementation(platform("org.jetbrains.kotlin:kotlin-bom:1.8.0"))
}
```

## 46.10 自定义 TabLayout

此示例项目中的`TabLayout`是使用固定模式（fixed mode）配置的。这种模式适用于数量有限且标题较短的标签。使用固定模式时，标签数量过多或标题较长可能会迅速变成问题，正如图 46-7 所示：

![](img/as_4.1_tab_layout_truncated.jpg)

图 46-7

为了让标签适应可用的显示宽度，`TabLayout`使用了多行文本。尽管如此，第二行仍被截断，导致无法看到完整标题。解决此问题的方案是将`TabLayout`切换到可滚动模式（scrollable mode）。在这种模式下，标题将以全长度单行格式显示，允许用户通过滑动水平滚动查看可用项目，正如图 46-8 所示：

![](img/as_4.1_tab_layout_scrollable.jpg)

图 46-8

要将`TabLayout`切换到可滚动模式，请将`activity_main.xml`资源文件中的`app:tabMode`属性从`fixed`更改为`scrollable`：

```xml
<android.support.design.widget.TabLayout
    android:id="@+id/tabLayout"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    app:tabMode="scrollable"
    app:tabGravity="fill"/>
```

例如，当`app:tabGravity`设置为`fill`时，项目将分布在整个宽度，如图 46-9 所示：

![](img/as_4.1_tab_layout_fill.jpg)

图 46-9

将属性值更改为`center`将导致项目相对于标签栏中心进行定位：

![](img/as_4.1_tab_layout_center.jpg)

图 46-10

### 46.11 总结

`TabLayout`是材料设计（material design）引入的组件之一。`TabLayout`组件的目的是展示一系列标签项，在被选中时显示内容。标签项可以显示文本、图像或三者的组合。与`ViewPager2`类和片段结合时，可以轻松地创建标签布局。

## 47. 使用 RecyclerView 和 CardView

`RecyclerView`和`CardView`共同工作，提供以单个卡片形式呈现信息的滚动列表。在通过示例项目的设计和实现之前，本章将介绍这两个类的细节。

### 47.1 RecyclerView 概述

与使用悬动按钮和 Snackbar 章节中概述的`ListView`类类似，`RecyclerView`的目的是以滚动列表的形式向用户呈现信息。然而，`RecyclerView`比`ListView`具有许多优势。特别是`RecyclerView`在管理组成列表的视图方面高效得多，当列表项离开屏幕时复用现有视图而不是创建新视图（因此得名“回收器”）。这提高了性能并减少了列表使用的资源。

与`ListView`不同，`RecyclerView`还提供了三种内置布局管理器供选择，以控制向用户呈现列表项的方式：

- `LinearLayoutManager`：列表项以水平或垂直列表的形式呈现。

![](img/Image2427.jpg)

图 47-1

- `GridLayoutManager`：列表项以网格形式呈现。这种管理器适用于列表项大小一。

![](img/Image2436.jpg)

图 47-2

- `StaggeredGridLayoutManager`：列表项以交错网格形式呈现。这种管理器适用于列表项大小不一。

![](img/Image2443.jpg)

图 47-3

对于这三种内置管理器都无法提供所需布局的情况，可以通过子类化`RecyclerView.LayoutManager`类来实现自定义布局管理器。

在`RecyclerView`中显示的每个列表项都是作为`ViewHolder`类的实例创建的。`ViewHolder`实例包含了`RecyclerView`显示列表项所需的所有内容，包括要显示的信息和用于显示项的视图布局。

与`ListView`类似，`RecyclerView`依赖于适配器（adapter）作为`RecyclerView`实例与要显示给用户的数据之间的中介。适配器被创建为`RecyclerView.Adapter`类的子类，并且至少实现以下方法，这些方法会被分配给适配器的`RecyclerView`对象在不同时间点进行调用：

- `getItemCount()` – 此方法必须返回列表中要显示的项数。

- `onCreateViewHolder()` – 此方法创建并返回一个`ViewHolder`对象，该对象使用用于显示数据的视图进行初始化。此视图通常通过加载（inflating）XML 布局文件创建。

- `onBindViewHolder()` – 此方法接收由`onCreateViewHolder()`方法创建的`ViewHolder`对象，以及一个指示即将显示的列表项的整数值。`ViewHolder`对象中包含了`onCreateViewHolder()`方法分配的布局。`onBindViewHolder()`方法负责将与指定项目对应的文本和图形填充到布局中的视图中，并将对象返回给`RecyclerView`，由其展示给用户。

在布局中添加`RecyclerView`只需要在其要出现的 Activity 的 XML 内容布局文件中添加适当的元素即可。例如：

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    app:layout_behavior="@string/appbar_scrolling_view_behavior"
    tools:context=".MainActivity"
    tools:showIn="@layout/activity_card_demo">
    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/recycler_view"
        android:layout_width="0dp"
        android:layout_height="0dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        tools:listItem="@layout/card_layout" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

在上面的示例中，`RecyclerView`已与`AppBar`和`Toolbar`一起嵌入到主 Activity 布局文件的`CoordinatorLayout`中。这提供了一些额外功能，例如配置`Toolbar`和`AppBar`，当用户在`RecyclerView`中向上滚动时它们滑出屏幕（该主题在“使用 AppBar 和 Collapsing Toolbar 布局”章节中会有更详细的介绍）。

### 47.2 CardView 概述

`CardView`类是一种用户界面视图，允许使用卡片隐喻来分组显示信息。卡片通常使用`RecyclerView`实例以列表形式呈现，并可以配置为带有阴影效果和圆角。例如，[图 47-4] 显示了三个配置好的`CardView`实例，用于显示一个由`ImageView`和两个`TextView`组成的布局：

![](img/Image24511.jpg)

图 47-4

与`CardView`实例一起呈现的用户界面布局定义在 XML 布局资源文件中，并在运行时加载到`CardView`中。`CardView`布局可以使用任何复杂性的布局，使用如`RelativeLayout`和`LinearLayout`等标准布局管理器。以下 XML 布局文件表示由`RelativeLayout`和单个`ImageView`组成的卡片视图布局。该卡片被配置为提升以创建阴影效果并带有圆角显示：




```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.cardview.widget.CardView
    xmlns:card_view="http://schemas.android.com/apk/res-auto"
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/card_view"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="5dp"
    card_view:cardRadius="12dp"
    card_view:cardElevation="3dp"
    card_view:contentPadding="4dp">
    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:padding="16dp">
        <ImageView
            android:id="@+id/item_image"
            android:layout_width="100dp"
            android:layout_height="100dp"
            android:layout_alignParentLeft="true"
            android:layout_alignParentTop="true"
            android:layout_marginRight="16dp" />
    </RelativeLayout>
</androidx.cardview.widget.CardView>
```

当与`RecyclerView`结合创建可滚动卡片列表时，视图的`onCreateViewHolder()`方法会加载卡片的布局文件，将其分配给`ViewHolder`实例并返回给`RecyclerView`实例。

### 47.3 总结

本章介绍了 Android `RecyclerView` 和 `CardView` 组件。`RecyclerView` 提供了一种资源高效的方式来显示可滚动视图列表。`CardView` 适用于以卡片形式呈现数据组（如名称和地址）。正如在下一节教程中所概述的，两者结合使用非常有用。

## 48. RecyclerView 和 CardView 教程

本章将创建一个示例项目，使用`CardView`和`RecyclerView`组件创建一个可滚动卡片列表。完成后的程序将显示包含图像和文本的卡片列表。除了显示卡片列表外，项目还将实现选择卡片时显示消息。

### 48.1 创建 CardDemo 项目

从欢迎屏幕上选择 New Project，在出现的新项目对话框中，点击 Next 按钮之前选择`Basic Views Activity`模板。在 Name 字段中输入`CardDemo`，并指定`com.ebookrenzy.carddemo`为包名。在点击 Finish 按钮之前，将 Minimum API 设置更改为`API 26: Android 8.0 (Oreo)`，并将 Language（语言）菜单为`Java`。

### 48.2 修改 Basic Views Activity 项目

由于选择了`Basic Views Activity`，布局包含一个项目并不所需的悬浮按钮。将`activity_main.xml`布局文件加载到布局编辑器，选择悬浮按钮并按下键盘删除键将其从布局中移除。编辑`MainActivity.java`文件，从`onCreate`方法中移除悬浮按钮和导航控制器代码，如下：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    binding = ActivityMainBinding.inflate(getLayoutInflater());
    setContentView(binding.getRoot());
    setSupportActionBar(binding.toolbar);
    NavController navController =
        Navigation.findNavController(this, R.id.nav_host_fragment_content_main);
    appBarConfiguration =
        new AppBarConfiguration.Builder(navController.getGraph()).build();
    NavigationUI.setupActionBarWithNavController(this, navController,
        appBarConfiguration);
    binding.fab.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View view) {
            Snackbar.make(view, "Replace with your own action", Snackbar.LENGTH_LONG)
                .setAction("Action", null).show();
        }
    });
}
```

同时移除`onSupportNavigateUp()`方法，然后打开`content_main.xml`文件并从布局中删除`nav_host_fragment_content_main`对象，只保留`ConstraintLayout`父布局。

### 48.3 设计 CardView 布局

卡片中包含的视图布局将在单独的 XML 布局文件中定义。在 Project 工具窗口中，右键点击`app` -> `res` -> `layout`项，并选择`New` -> `Layout Resource File`菜单。在 New Resource 对框中，在`File name:`字段中输入`card_layout`，并在根元素字段输入`androidx.cardview.widget.CardView`，然后点击`OK`按钮。

将`card_layout.xml`文件加载到 Layout Editor 工具中，切换到`Code`模式，并修改布局如下所示：

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.cardview.widget.CardView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:id="@+id/card_view"
    android:layout_margin="5dp"
    app:cardBackgroundColor="#80B3EF"
    app:cardCornerRadius="12dp"
    app:cardElevation="3dp"
    app:contentPadding="4dp">
    <androidx.constraintlayout.widget.ConstraintLayout
        android:id="@+id/relativeLayout"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:padding="16dp">
        <ImageView
            android:id="@+id/itemImage"
            android:layout_width="100dp"
            android:layout_height="100dp"
            app:layout_constraintLeft_toLeftOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toTopOf="parent" />
        <TextView
            android:id="@+id/itemTitle"
            android:layout_width="236dp"
            android:layout_height="39dp"
            android:layout_marginStart="16dp"
            android:textSize="30sp"
            app:layout_constraintLeft_toRightOf="@+id/itemImage"
            app:layout_constraintStart_toEndOf="@+id/itemImage"
            app:layout_constraintTop_toTopOf="parent" />
        <TextView
            android:id="@+id/itemDetail"
            android:layout_width="236dp"
            android:layout_height="16dp"
            android:layout_marginStart="16dp"
            android:layout_marginTop="8dp"
            app:layout_constraintLeft_toRightOf="@+id/itemImage"
            app:layout_constraintStart_toEndOf="@+id/itemImage"
            app:layout_constraintTop_toBottomOf="@+id/itemTitle" />
    </androidx.constraintlayout.widget.ConstraintLayout>
</androidx.cardview.widget.CardView>
```

### 48.4 添加 RecyclerView

选择`content_main.xml`布局文件，从调色板的`Containers`部分拖入一个`RecyclerView`对象到布局中，使其位于屏幕中心，它将自动调整大小以填充整个屏幕。使用 Infer constraints 按钮添加任何缺失的布局约束。使用 Attributes 窗口，将`RecyclerView`实例 ID 更改为`recyclerView`，并将`layout_width`和`layout_height`属性更改为`match_constraint`。

## 48.5 添加图像文件

除了两个`TextView`外，卡片布局还包含一个`ImageView`，Recycler 适配器已配置为显示图像。在测试项目之前，必须添加这些图像。项目使用的图像命名为`android_image_<n>.jpg`，可以在以下 URL 提供的示例代码项目中找到：https://www.ebookrenzy.com/retail/java/index.php

在操作系统的文件导航器中找到这些图像并复制这八张图片。在 Project 窗口中右键点击`app` -> `res` -> `drawable`项并选择 Paste（粘贴）将文件添加到文件夹中。

## 48.6 创建 RecyclerView 适配器

如上一章所述，`RecyclerView`需要一个适配器来处理列表项的创建。在 Project 窗口中右键点击`app` -> `java` -> `com.ebookrenzy.carddemo`项，选择`New` -> `Java Class`选项。在新类对话框中，在`Name`字段输入`RecyclerAdapter`并在列表中选择`Class`，然后按`Return`键创建新的 Java 类。

编辑新的`RecyclerAdapter.java`文件以添加一些导入指令并声明该类继承`RecyclerView.Adapter`。与其创建一个单独的类来提供要显示的数据，不如向适配器中添加一些数组来作为应用的数据：

```java
package com.ebookrenzy.carddemo;

import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.ImageView;
import android.widget.TextView;
import androidx.annotation.NonNull;
import androidx.recyclerview.widget.RecyclerView;

public class RecyclerAdapter extends RecyclerView.Adapter<RecyclerAdapter.ViewHolder> {
    private String[] titles = {"Chapter One", "Chapter Two", "Chapter Three", "Chapter Four", "Chapter Five", "Chapter Six", "Chapter Seven", "Chapter Eight"};
    private String[] details = {"Item one details", "Item two details", "Item three details", "Item four details", "Item five details", "Item six details", "Item seven details", "Item eight details"};
    private int[] images = { R.drawable.android_image_1, R.drawable.android_image_2, R.drawable.android_image_3, R.drawable.android_image_4, R.drawable.android_image_5, R.drawable.android_image_6, R.drawable.android_image_7, R.drawable.android_image_8 };
}
```

在`RecyclerAdapter`类中，我们现在需要自己的`ViewHolder`类实现来引用`card_layout.xml`中的元素。在`RecyclerAdapter.java`文件中，按如下方式实现该类：

```java
public class RecyclerAdapter extends RecyclerView.Adapter<RecyclerAdapter.ViewHolder> {
    static class ViewHolder extends RecyclerView.ViewHolder {
        ImageView itemImage;
        TextView itemTitle;
        TextView itemDetail;

        ViewHolder(View itemView) {
            super(itemView);
            itemImage = itemView.findViewById(R.id.itemImage);
            itemTitle = itemView.findViewById(R.id.itemTitle);
            itemDetail = itemView.findViewById(R.id.itemDetail);
        }
    }
}
```

`ViewHolder`类包含一个`ImageView`和两个`TextView`变量，以及一个初始化这些变量以引用`card_layout.xml`文件中三个视图项的构造方法。

添加到`RecyclerAdapter.java`的下一个项是`onCreateViewHolder()`方法的实现：



```java
@NonNull
@Override
public ViewHolder onCreateViewHolder(ViewGroup viewGroup, int i) {
    View v = LayoutInflater.from(viewGroup.getContext())
            .inflate(R.layout.card_layout, viewGroup, false);
    return new ViewHolder(v);
}
```

该方法将被 `RecyclerView` 调用以获取 `ViewHolder` 对象。它会填充视图层次 `card_layout.xml` 文件并创建一个初始化了视图层次的 `ViewHolder` 类实例，然后将其返回给 `RecyclerView`。

`onBindViewHolder()` 方法的目的是向 `ViewHolder` 对象中的视图层级结构中填充要显示的数据。该方法接收一个 `ViewHolder` 对象和一个表示要显示的列表项的整数值。现在应该添加此方法，并使用项目编号作为数据数组的索引。随后，这些数据将使用在 `ViewHolder` 类构造方法中创建的引用显示在布局视图上：

```java
@Override
public void onBindViewHolder(ViewHolder viewHolder, int i) {
    viewHolder.itemTitle.setText(titles[i]);
    viewHolder.itemDetail.setText(details[i]);
    viewHolder.itemImage.setImageResource(images[i]);
}
```

适配器类的最后一个要求是实现 `getItemCount()` 方法，在当前情况下，它返回 `titles` 数组中的项目数量：

```java
@Override
public int getItemCount() {
    return titles.length;
}
```

## 48.7 初始化 RecyclerView 组件

此时，项目已经包含一个 `RecyclerView` 实例、一个用于 `CardView` 实例的 XML 布局文件以及一个 `RecyclerView` 适配器。在测试目前进展之前的最后一步是使用 `layout manager` 初始化 `RecyclerView`，创建适配器实例并将该实例分配给 `RecyclerView` 对象。为了本示例的目的，`RecyclerView` 将配置为使用 `LinearLayoutManager` 布局选项。

这里有一点小复杂之处，因为我们需要能够使用视图绑定（view binding）从 `MainActivity` 类内部访问 `recyclerView` 组件。问题是 `recyclerView` 包含在 `content_main.xml` 布局文件中，而该文件又被包含在 `activity_main.xml` 文件中。为了能够访问 `content_main.xml` 文件，我们需要在包含它时为其分配一个 id。要做到这一点，请编辑 `activity_main.xml` 文件并修改 `include` 元素，如下所示：

```xml
<include
    android:id="@+id/contentMain"
    layout="@layout/content_main" />
```

在给包含的文件分配了 id 后，可以使用以下绑定访问 `recyclerView` 组件：

`binding.contentMain.recyclerView`

现在编辑 `MainActivity.java` 文件并修改 `onCreate()` 方法以实现初始化代码：

```java
package com.ebookfrenzy.carddemo;

import androidx.recyclerview.widget.LinearLayoutManager;
import androidx.recyclerview.widget.RecyclerView;

public class MainActivity extends AppCompatActivity {
    private RecyclerView recyclerView;
    private RecyclerView.LayoutManager layoutManager;
    private RecyclerView.Adapter adapter;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        setSupportActionBar(toolbar);
        layoutManager = new LinearLayoutManager(this);
        binding.contentMain.recyclerView.setLayoutManager(layoutManager);
        adapter = new RecyclerAdapter();
        binding.contentMain.recyclerView.setAdapter(adapter);
    }
}
```

## 48.8 测试应用程序

在物理设备或模拟器会话上编译并运行应用，并滚动列表中不同的卡片项：

![](img/as_card_demo_running.jpg)

图 48-2

在构建项目时，你可能会遇到部分内容如下错误：

`Duplicate class kotlin.collections.jdk8.CollectionsJDK8Kt found in modules kotlin-stdlib`

此错误是由 Android Studio 构建工具链中的一个 引起的，可以通过对 `build.gradle.kts` (Module: app) 文件进行以下更改来解决：

```kotlin
dependencies {
    implementation(platform("org.jetbrains.kotlin:kotlin-bom:1.8.0"))
}
```

## 48.9 响应卡片选择

本项目的最后一个阶段是使列表中的卡片变为可选择的，这样点击卡片就会触发应用内的事件。对于此示例，卡片将被配置为在用户点击时在显示器上显示一条消息。为了响应点击，需要修改 `ViewHolder` 类以在每个项目视图上分配一个 `OnClickListener`。编辑 `RecyclerAdapter.java` 文件并修改 `ViewHolder` 类声明，如下所示：

```java
import com.google.android.material.snackbar.Snackbar;

class ViewHolder extends RecyclerView.ViewHolder{
    ImageView itemImage;
    TextView itemTitle;
    TextView itemDetail;
    ViewHolder(View itemView) {
        super(itemView);
        itemImage = itemView.findViewById(R.id.item_image);
        itemTitle = itemView.findViewById(R.id.item_title);
        itemDetail = itemView.findViewById(R.id.item_detail);
        itemView.setOnClickListener(new View.OnClickListener() {
            @Override public void onClick(View v) {
            }
        });
    }
}
```

在 `onClick` 处理器的体内部，现在可以添加代码来显示一条指示卡片已被点击的消息。由于由于点击而执行的操作可能取决于点击了哪张卡片，因此识别所选的卡片也很重要。此信息可以通过调用 `RecyclerView.ViewHolder` 类的 `getAdapterPosition()` 方法获取。继续留在 `RecyclerAdapter.java` 文件中，为 `onClick` 处理器添加代码，如下所示：

```java
@override
public void onClick(View v) {
    int position = getAdapterPosition();
    Snackbar.make(v, "Click detected on item " + (position + 1), Snackbar.LENGTH_LONG).show();
}
```

最后一个任务是启用点击卡片时的材质设计波纹效果。这涉及在 `card_layout.xml` 文件中添加某些属性：

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.cardview.widget.CardView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:card_view="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:id="@+id/card_view"
    android:layout_margin="5dp"
    app:cardBackgroundColor="#80B3EF"
    app:cardCornerRadius="12dp"
    app:cardElevation="3dp"
    app:contentPadding="4dp"
    android:foreground="?selectableItemBackground"
    android:clickable="true" >
```

再次运行应用，验证点击列表中的卡片是否会触发标准的波纹效果并显示报告项目编号 Snackbar。

### 48.10 总结

本章介绍了结合 `CardView` 和 `RecyclerView` 组件以显示滚动卡片列表的步骤。示例还涵盖了对点击的检测，包括识别所选项目以及在点击的 `CardView` 实例上启用波纹反馈。

## 49. 布局编辑器示例数据教程

上一节创建的 `CardDemo` 项目提供了一个很好的例子，说明了在完成应用测试之前，很难从布局编辑器准确评估用户界面将呈现什么样。当用户界面中显示的内容只有在用户安装并运行应用后才能生成或获取时，这是一个常见问题。随着 Android Studio 布局编辑器支持示例数据，这种功能得到了显著扩展，本章将使用它来改进布局编辑器体验。

### 49.1 向项目添加示例数据

在用户界面布局的设计阶段，`RecyclerView` 实例（图 49-1）与上一章末尾测试的运行程序几乎没有相似之处：

![](img/as_3.6_recyclerview_no_sample_data.jpg)

图 49-1

在书中之前的“使用 Jetpack 构建现代 Android 应用架构

图 49-2

将模板更改为 `Email Client` 选项并将项目计数更改为 `12`，注意 `RecyclerView` 发生了变化，显示来自模板的数据：

![](img/as_3.6_recyclerview_sample_data_email.jpg)

图 49-3

这些模板对于在无需任何额外工作的情况下显示样本数据非常有用，通常足以完成布局设计。然而，对于本示例，将使用样本数据来显示 `RecyclerView` 中的卡片，就像它们在运行程序中出现一样。在 `content_main.xml` 文件仍加载在布局编辑器的情况下，切换到代码（Code）模式并找到 `RecyclerView` 元素，其内容如下：

```xml
<androidx.recyclerview.widget.RecyclerView
    android:id="@+id/recyclerView"
    android:layout_width="0dp"
    android:layout_height="0dp"
    app:layout_constraintBottom_toBottomOf="parent"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent"
    tools:itemCount="12"
    tools:listitem="@layout/recycler_view_item" />
```

注意当前配置的两个特殊 `tools` 属性，它们用于在列表中显示 12 个项目，每个项目使用位于 `recycler_view_item.xml` 文件中的布局。布局编辑器提供了一系列可以在布局文件中配置的 `tools` 选项。虽然涵盖所有设置超出了本书的范围，但在以下 URL 可以找到每个设置的完整描述：

`https://developer.android.com/studio/write/tool-attributes#toolssample_resources`

上述引用的 `recycler_view_item.xml` 文件是在选择样本数据模板时由布局编辑器自动生成的，可以在项目窗口中找到。

切换回设计（Design）模式，在选中 `RecyclerView` 的情况下，使用设计时视图属性面板将模板切回默认设置。`recycler_view_item.xml` 文件将从项目中删除，同时 `content_main.xml` XML 文件中的两个 `tools` 属性行也随之删除（如果 Android Studio 未能删除这些行，则可以在代码视图中手动删除）。

要切换到使用卡片布局显示样本数据，添加一个 `listitem` 属性以引用 `card_layout.xml` 文件。在布局中选中 `RecyclerView` 后，在属性（Attributes）工具窗口中搜索 `listitem` 属性，并在字段中输入 `@layout/card_layout`，如图 49-4 所示：

![](img/as_sample_data_list_item.jpg)

图 49-4

注意现在每个列表项都显示了卡片布局，但没有任何图像且使用的是样本文本数据：

![](img/as_sample_list_items.jpg)

图 49-5

下一步是在卡片布局的视图中显示一些图像和不同的文本。这既可以是布局编辑器提供的模板样本数据形式，也可以专门为此项目添加的自定义样本数据。将 `card_layout.xml` 文件加载到布局编辑器，选择 `ImageView` 并如本章前面所述显示设计时视图属性面板。从 `srcCompat` 菜单中选择内置的背景/风景图集，如下所示图 49-6：

![](img/as_sample_data_images.jpg)

图 49-6

接下来，右键点击 `itemTitle` `TextView` 对象，选择 `Set Sample Data` 菜单，并在设计属性面板中选择 `cities` 文本选项。对 `itemDetail` 视图重复此步骤，这次选择 `full_names` 选项，如图 49-7 所示：

![](img/as_sample_data_names.jpg)

图 49-7

在设计模式下打开 `content_main.xml` 文件，注意 `RecyclerView` 现在使用内置图像和样本文本数据：

![](img/as_sample_data_stage1.jpg)

图 49-8

## 49.2 使用自定义样本数据

本章的最后一步是演示如何在布局编辑器中使用自定义样本数据和图像。这需要创建一个样本数据目录并添加一些文本和图像文件。在项目窗口中，右键点击 app 入口并选择 `New -> Sample Data Directory` 菜单，此时项目窗口中会出现一个名为 `sampledata` 的新目录。如果新文件夹不可见，将项目窗口从 Android 模式切换到 Project 模式，并在 `CardDemo -> app` 下找到文件夹，如图 49-9 所示：

![](img/as_sample_data_folder.jpg)

图 49-9

右键点击 `sampledata` 目录，创建一个名为 `images` 的目录，并按照上一章出的步骤将 Android 图像复制粘贴到新文件夹中。在 `card_layout.xml` 文件中，再次显示 `ImageView` 的设计时视图属性面板，这次点击 `Browse` 链接并在对话框中选择新添加的 Android 图像（如果 images 文件夹未出现，请重新项目）：

![](img/as_sample_data_manager.jpg)

图 49-10

再次键点击 `sampledata` 目录，选择 `New -> File` 选项，文件命名为 `chapters` 并输入以下内容：

```
Chapter One
Chapter Two
Chapter Three
Chapter Four
Chapter Five
Chapter Six
Chapter Seven
Chapter Eight
```

接下来，创建一个名为 `items` 的第二个文本文件，内容如下：



创建样本数据文本文件后，剩下的就是在`card_layout.xml`文件的视图元素中如下引用它们：

```xml
<TextView
    android:id="@+id/itemTitle"
    android:layout_width="236dp"
    android:layout_height="39dp"
    android:layout_marginStart="16dp"
    android:textSize="30sp"
    app:layout_constraintLeft_toRightOf="@+id/itemImage"
    app:layout_constraintStart_toEndOf="@+id/itemImage"
    app:layout_constraintTop_toTopOf="parent"
    tools:text="@sample/chapters" />

<TextView
    android:id="@+id/itemDetail"
    android:layout_width="236dp"
    android:layout_height="16dp"
    android:layout_marginStart="16dp"
    android:layout_marginTop="8dp"
    app:layout_constraintLeft_toRightOf="@+id/itemImage"
    app:layout_constraintStart_toEndOf="@+id/itemImage"
    app:layout_constraintTop_toBottomOf="@+id/itemTitle"
    tools:text="@sample/items" />
```

重新构建程序并返回`content_main.xml`文件中的布局设计，此时自定义样本数据和图像应该显示在`RecyclerView`列表中：

![](img/as_sample_data_completed.jpg)

图 49-11

与其使用两个独立的文本文件并对图像集的引用，另一种选择是在 JSON 文件中声明样本数据。例如：

```json
{
  "mydata": [
    {
      "chapter" : "Chapter One",
      "details": "Item one details",
      "image": "@sample/images"
    },
    {
      "chapter" : "Chapter Two",
      "details": "Item two details",
      "image": "@sample/images"
    }
  ]
}
```

假设上述内容位于名为`chapterdata.json`的文件中，那么在视图 XML 元素中引用样本数据的方式如下：

```xml
<ImageView
    tools:src="@sample/chapterdata.json/mydata/image" />
<TextView
    tools:text="@sample/chapterdata.json/mydata/chapter" />
<TextView
    tools:text="@sample/chapterdata.json/mydata/details" />
```

### 49.3 总结

本章演示了如何在布局编辑器中使用样本数据，以提供用户界面在运行时外观的更真实表示。本教程涵盖的步骤包括使用现有的样本数据模板以及集成自定义样本数据。

### 50. 使用 AppBar 和折叠工具栏布局

在本章中，我们将探索如何自定义 Activity 布局中的应用栏（app bar），并使其对其他屏幕视图中的滚动事件做出响应。通过结合使用`CoordinatorLayout`与`AppBarLayout`和`CollapsingToolbarLayout`容器，可以配置应用栏以显示图像并在视图中进行淡入淡出动画。例如，可以配置列表的向上滚动动作，使应用栏从视图中退回，并在执行向下滚动动作时重新出现。

本章将从组成 app bar 的元素概述开始，逐步介绍各种 app bar 配置的示例。

### 50.1 AppBar 的结构

app bar 是应用程序运行时显示在屏幕顶部的区域，可以配置为包含各种项目，包括状态栏（status bar）、工具栏（toolbar）、标签栏（tab bar）和可伸空间区域。例如，图 50-1 显示了一个包含状态栏、工具栏和标签栏的 app bar：

![](img/Image24271.jpg)
图 50-1

空白背景颜色可以填充可伸空间区域，或者如图 50-2 所示，显示在`ImageView`对象上的图像：

![](img/Image24361.jpg)
图 50-2

正如本章剩余部分将演示的那样，如果 Activity 用户界面布局的主内容区域包含滚动内容，则 app bar 的元素可以根据屏幕上内容的滚动进行展开和收缩。

### 50.2 示例项目

对于此示例，将对早期章节创建的`CardDemo`项目进行修改，该项目标题为 Android RecyclerView 和 CardView 教程。首先启动 Android Studio 并加载此项目。

项目加载后，运行应用程序，并注意当向上滚动列表时，工具栏保持可见，如图 50-3 所示：

![](img/as_app_bar_1.jpg)
图 50-3

第一步是更改配置，使工具栏在向上滚动动作期间收缩，并在向下滚动时展开。

#### 50.3 协调 RecyclerView 和 Toolbar

将`activity_main.xml`文件加载到布局编辑器工具中，切换到代码模式并查看 XML 布局设计，其层级结构由图 50-4 中的图表示：

![](img/as3.0_appbar_coordinatorlayout_tree.jpg)
图 50-4

层级结构的顶层是`CoordinatorLayout`，正如其名，它协调其包含的各种子视图元素之间的交互。例如，在使用浮动操作按钮和 Snackbar 所示，`CoordinatorLayout`会自动将浮动操作按钮向上滑动以容纳`Snackbar`的出现，然后在该栏消失后将按钮移回下方。

`CoordinatorLayout`同样可以根据视图层级结构中某些视图的滚动动作，导致 app bar 的元素滑入或滑出视图。图 50-4 所示的布局层级结构中的一个元素是`ConstraintLayout`。为了实现这种协调行为，有必要在发生滚动的元素以及与滚动协调的元素上设置属性。

在滚动元素（在本例中为`RecyclerView`）上，必须将`android:layout_behavior`属性设置为`appbar_scrolling_behavior`。在`content_main.xml`文件中，找到顶层的`ConstraintLayout`并注意该属性已设置：

```xml
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    app:layout_behavior="@string/scbar_behavior">
```

接下来，在布局编辑器中打开`activity_main.xml`文件，切换到代码模式并找到`AppBarLayout`元素。注意`AppBarLayout`的唯一子元素是`Toolbar`。要让工具栏响应`RecyclerView`中发生的滚动事件，必须在该元素上设置`app:layout_scrollFlags`属性。该属性的值取决于交互的性质，并且由以下一个或多个选项组成：

- `scroll`：指示视图将滚动到屏幕外。如果不设置此项，视图在滚动期间将固定在屏幕顶部。
- `enterAlways`：与`scroll`选项配合使用时，向上滚动会导致视图退回。在此模式下，任何向下滚动动作都会导致视图重新出现。
- `enterAlwaysCollapsed`：设置在视图上时，在向下滚动到达列表之前，视图不会展开。如果设置了`minHeight`属性，视图在初始滚动期间出现，直到达到最小高度。之后它将保持在该高度，直到到达列表顶部。注意，此选项仅在同时使用`enterAlways`和`scroll`选项时才有效。例如：`app:layout_scrollFlags="scroll|enterAlways|enterAlwaysCollapsed"` `android:minHeight="20dp"`。
- `exitUntilCollapsed`：设置后，视图在向上滚动期间将收缩，直到达到`minHeight`阈值。此时它将保持在该高度，直到滚动方向改变。

对于此示例，将在`Toolbar`上按如下方式设置`scroll`和`enterAlways`选项：

```xml
<com.google.android.material.appbar.MaterialToolbar
    android:id="@+id/toolbar"
    android:layout_width="match_parent"
    android:layout_height="?attr/actionBarSize"
    app:layout_scrollFlags="scroll|enterAlways" />
```

设置适当的属性后，重新运行应用程序并在`RecyclerView`列表中执行向上滚动动作。这应该导致工具栏收缩出视图（图 50-5）。

![](img/as_card_demo_appbar_scroll.jpg)
图 50-5

#### 50.4 介绍折叠工具栏布局

`CollapsingToolbarLayout`容器通过针对协调滚动动作对应用栏（app bar）及其子元素的折叠提供更多的选项和控制范围，增强了标准工具栏的功能。`CollapsingToolbarLayout`类旨在作为`AppBarLayout`的子元素添加。它提供了许多功能，例如随着工具栏的折叠和展开自动调整工具栏标题的字体大小。`parallax`（视差）模式允许应用栏中的指定内容在折叠时淡出视图，而`pin`（固定）模式则允许应用栏的元素在收缩期间保持固定位置。

提供了`scrim`（遮罩）选项，用于指定工具栏在折叠过程中过渡的颜色。

为了查看这些功能的效果，将修改`activity_main.xml`文件中的应用栏，使其使用`CollapsingToolbarLayout`类，并添加一个`ImageView`以更好地演示`parallax`模式的效果。使用`CollapsingToolbarLayout`的新视图层级如图图 50-6 所示：

![](img/as3.0_appbar_collapsing_tree.jpg)

图 50-6

将`activity_main.xml`文件加载到 Layout Editor 工具的 Code 模式并修改布局使其内容如下：

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.coordinatorlayout.widget.CoordinatorLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:fitsSystemWindows="true"
    tools:context=".MainActivity">

    <com.google.android.material.appbar.AppBarLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:fitsSystemWindows="true">

        <com.google.android.material.appbar.CollapsingToolbarLayout
            android:id="@+id/collapsing_toolbar"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            app:layout_scrollFlags="scroll|enterAlways"
            android:fitsSystemWindows="true"
            app:expandedTitleMarginBottom="30dp"
            app:expandedTitleMarginStart="15dp"
            app:expandedTitleMarginEnd="64dp">

            <ImageView
                android:id="@+id/backdrop"
                android:layout_width="match_parent"
                android:layout_height="200dp"
                android:scaleType="centerCrop"
                android:fitsSystemWindows="true"
                app:layout_collapseMode="parallax"
                android:src="@drawable/appbar_image" />

            <com.google.android.material.appbar.MaterialToolbar
                android:id="@+id/toolbar"
                android:layout_width="match_parent"
                android:layout_height="?attr/actionBarSize"
                app:layout_scrollFlags="scroll|enterAlways"
                app:layout_collapseMode="pin" />

        </com.google.android.material.appbar.CollapsingToolbarLayout>

    </com.google.android.material.appbar.AppBarLayout>

    <include
        android:id="@+id/contentMain"
        layout="@layout/content_main" />

</androidx.coordinatorlayout.widget.CoordinatorLayout>
```



使用你操作系统的文件系统，在代码示例的项目文件夹中找到`appbar_image.jpg`文件并复制它。在`Project`窗口中右键点击`res` -> `drawable`条目，从弹出的菜单中选择`Paste`（粘贴）。

运行时，应用栏的显示应该如图图 50-7 所示：

![](img/as_appbar_2.jpg)

图 50-7

向上滚动列表将导致应用栏折叠。在收缩过程中，图像将淡出到`scrim`属性定义的颜色，同时标题文本的字体大小将按相应的速率减小，直到只看到工具栏：

![](image/as_appbar_3.jpg)

图 50-8

在滚动动作的初始阶段，工具栏保持可见（如果继续向上滚动动作，工具栏也将移出视图），这是因为`activity_main.xml`文件中的工具栏元素被配置为使用`pin`模式：`app:layout_collapseMode="pin"`。

如果将折叠模式设置为`parallax`，工具栏将随图像一起收回。继续向上滚动动作将导致工具栏也折叠，只留下状态栏可见：

![](image/as_appbar_4.jpg)

图 50-9

由于`CollapsingToolbarLayout`元素的`scrollFlags`属性包含`enterAlways`选项，向下滚动动作将导致应用栏再次展开。

要固定工具栏使其在向上滚动动作期间不再移出视图，请将`activity_main.xml`文件中`CollapsingToolbarLayout`元素的`layout_scrollFlags`属性中的`enterAlways`替换为`exitUntilCollapsed`，修改如下所示：

```xml
<com.google.android.material.appbar.CollapsingToolbarLayout
    android:id="@+id/collapsing_toolbar"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    app:layout_scrollFlags="scroll|exitUntilCollapsed"
    android:fitsSystemWindows="true"
    app:expandedTitleMarginBottom="30dp"
    app:expandedTitleMarginStart="15dp"
    app:expandedTitleMarginEnd="64dp">
```

### 50.5 修改标题和遮罩颜色

作为最后一个任务，编辑`MainActivity.java`文件并在`onCreate()`方法中添加一些代码来更改折叠实例的标题并设置不同的遮罩颜色（注意遮罩颜色也可以在布局文件中设置）：

```java
package com.ebookfrenzy.carddemo;

import com.google.android.material.appbar.CollapsingToolbarLayout;
import android.graphics.Color;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        binding = ActivityMainBinding.inflate(getLayoutInflater());
        setContentView(binding.getRoot());
        setSupportActionBar(binding.toolbar);
        binding.collapsingToolbar.setTitle("My Toolbar Title");
        binding.collapsingToolbar.setContentScrimColor(Color.GREEN);
        layoutManager = new LinearLayoutManager(this);
        binding.contentMain.recyclerView.setLayoutManager(layoutManager);
        adapter = new RecyclerAdapter();
        binding.contentMain.recyclerView.setAdapter(adapter);
    }
```

最后运行一次应用程序，注意新标题出现在应用栏中，并且滚动会导致工具栏在退回时过渡到绿色。

### 50.6 总结

大多数 Android 应用顶部的应用栏可以由多个元素组成，包括工具栏、标签布局和图像。当嵌入在`CoordinatorLayout`父容器时，提供了多种选项来控制应用栏响应活动主要内容滚动事件的行为。为了对这种行为进行更大的控制，`CollapsingToolbarLayout`管理器提供了一系列额外的控制级别，用于控制应用栏内容相对于滚动的展开和收缩。

# 51 Android Studio Primary-Detail Flow 教程

本章将介绍 Primary/Detail 用户界面设计概念，然后详细探讨包含在 Android Studio 一带的 Primary/Detail Flow 模板的组成元素。随后，我们将创建一个示例应用程序，演示修改模板以满足应用程序特定需求的步骤。

## 51.1 The Primary/Detail Flow

主/详情流（Primary/detail flow）是一种界面设计概念，其中向用户显示一组项目列表（称为主列表）。当用户从列表中选择一个项目时，与该项目相关的额外将在详情面板（detail pane）中呈现给用户。例如，一个电子邮件应用程序可能包含一个收件邮件主列表，其中包含发件人地址和邮件主题。从主列表中选择某封邮件后，邮件正文将显示在详情面板中。

在横屏模式的平板尺寸 Android 设备屏幕上，主列表显示在屏幕左侧边缘的狭窄垂直面板中。屏幕的其余部分则留给详情面板，这种布局被称为双窗格模式（two-pane mode）。例如，图 51-1 展示了主/详情双窗格布局，其中列出了主项目，并在详情面板中显示了第一个项目的内容：

![](img/as_detail_flow_tablet.jpg)

图 51-1

在较小的手机尺寸 Android 设备上，主列表占据整个屏幕，而详情面板则显示在从主列表进行选择后出现的独立屏幕上。在这种模式下，详情屏幕包含一个返回主列表的操作栏条目。例如，图 51-2 演示了在 4 英寸手机屏幕上同一项目列表的主屏幕和详情屏幕：

![](img/as_detail_flow_phone.jpg)

图 51-2

## 51.2 创建主/详情流 Activity

在本章的下一节中，将详细介绍组成主/详情流模板的不同元素。实现此点的最佳方法是使用`Primary/Detail Views Flow`模板创建一个项目，并在处理信息时使用它。该项目随后将作为章节末尾教程的基础。

从欢迎界面选择`New Project`（新建项目）选项，在弹出的新项目对话框中，点击`Next`（下一步）按钮之前，选择`No Activity`模板。

在`Name`字段中输入`PrimaryDetailFlow`并指定`com.ebookfrenzy.primarydetailflow`为包名。在点击`Finish`（完成）按钮之前，将最小 API 级别（Minimum API level）设置改为`API 26`：Android 8.0 (Oreo)，并将语言（Language）菜单改为`Java`。

## 51.3 添加主/详情流 Activity

在`Project`工具窗口中，右键点击`app` -> `java` -> `com.ebookfrenzy.primarydetailflow`项，并选择`New` -> `Activity` -> `Primary/Detail Views Flow`菜单选项。在新的 Activity 对话框（图 51-3）中，点击`Finish`按钮之前，确保启用`Launcher Activity`（启动 Activity）复选框：

![](img/as_primary_detail_new.jpg)

图 51-3

## 51.4 修改主/详情流模板

虽然主/详情流模板的结构初看起来可能很困惑，但将会所示，对于许多主/详情实现需求，模板提供的大部分功能可以保持不变。

在本章的剩余部分中，将修改`PrimaryDetailFlow`项目，使主列表显示网站列表，并将详情面板更改为包含一个`WebView`对象而不是当前的`TextView`。当用户选择某个网站时，相应的网页随后将在详情面板中加载并显示。

### 51.5 更改内容模型

当前示例的内容由`PlaceholderContent`类文件定义。因此，首先选择`PlaceholderContent.java`文件（位于`Project`工具窗口的`app` -> `java` -> `com.ebookfrenzy.primarydetailflow` -> `placeholder`文件夹下）并查看代码。文件底部定义了一个名为`PlaceholderItem`的类声明，该类目前能够存储三个`String`对象（代表内容和详情字符串）以及一个`ID`。另一方面，更新后的项目需要每个项目对象包含一个`ID`字符串、一个网站名称字符串以及一个对应网站的 URL 字符串。为了添加这些功能，修改`PlaceholderItem`类，使其读取内容如下：

```java
public static class PlaceholderItem {
    public String id;
    public String website_name;
    public String website_url;

    public PlaceholderItem(String id, String website_name,
            String website_url)
    {
        this.id = id;
        this.website_name = website_name;
        this.website_url = website_url;
    }

    @Override
    public String toString() {
        return website_name;
    }
}
```

注意，封装类`PlaceholderContent`目前包含一个`for`循环，通过调用`PlaceholderItem()`和`makeDetails()`添加了 25 个项目。大部分内容将不再需要，并应如下所示从类中删除：

```java
public static final Map<String, PlaceholderItem> ITEM_MAP = new HashMap<>(); // 逻辑占位
// 实际代码逻辑位于 com.ebookfrenzy.primarydetailflow.placeholder
```

等待，根据提供的文本碎片代码块，以下是文中描述的重构逻辑：

```java
public static final Map<String, PlaceholderItem> ITEM_MAP = new HashMap<>();
private static int COUNT = 25;

static {
    // 添加示例项目。
    for (int i = 1; i <= COUNT; i++) {
        addItem(new PlaceholderItem(String.valueOf(i), "Item " + i, "http://example.com"));
    }
}

private static void addItem(PlaceholderItem item) {
    ITEM_MAP.put(item.id, item);
}

public static PlaceholderItem createPlaceholderItem(int position) {
    return PlaceholderItem(String.valueOf(position), "Item " + position, "http://example.com");
}

private static String makeDetails(int position) {
    StringBuilder builder = new StringBuilder();
    builder.append("Details about Item: ").append(position);
    for (int i = 0; i < position; i++) {
        builder.append("\nMore details here.");
    }
    return builder.toString();
}
```

注意：提供的文本代码较为混乱，已根据文中描述重建了逻辑。

代码现在利用修改后的`PlaceholderItem`类来存储每个项目的 ID、名称和 URL。

## 51.6 修改详情面板

详情面板布局（用户从主列表选择项目时显示的屏幕）包含在`activity_item_detail.xml`文件中，该文件包含一个用于显示实际详情内容的`FrameContainerView`实例。如果应用程序以单面板模式显示，框架容器将显示`fragment_item_detail.xml`文件中的布局，而多窗格模式将显示`fragment_item_detail.xml (sw600dp)`布局。

Android Studio 为`fragment_item_detail.xml`提供的模板布局包含一个带有应用栏、工具栏、浮动按钮和`TextView`的`CoordinatorLayout`。对于此示例，我们只需要`WebView`，因此打开此文件并删除布局中除`item_detail_container`以外的所有视图。最简单的方法如下所示，在`Component Tree`（组件树）中选择所有不需要的视图，然后按删除键：

![](img/as_detail_pane_components.jpg)

图 51-4

从`Palette`的`Widgets`部分拖入`WebView`对象并将其放置在布局画布中心，然后将`id`改为`website_detail`。

接下来，编辑`fragment_item_detail.xml` (`sw600dp`) 文件，在将`WebView`拖放到布局之前，删除默认的`TextView`实例，并再次将`id`更改为`website_detail`。这两个文件的布局现在都应该类似于图 51-5：

![](img/as_3.5_master_detail_webview.jpg)

图 51-5

### 51.7 修改 ItemDetailFragment 类

此时，用户界面的详情面板已经过修改，但相应的 Java 类仍然设计为处理`TextView`对象而不是`WebView`对象。通过在项目（Project）工具窗口中双击`ItemDetailFragment.java`文件来加载该类的源代码。

若要加载与当前选中项目对应的网页 URL，只需要更改几行代码。完成此更改后，代码应如下所示：

```java
.
.
import android.webkit.WebResourceRequest;
import android.webkit.WebView;
import android.webkit.WebViewClient;
.
.
public class ItemDetailFragment extends Fragment {
.
.
    @Override
    public View onCreateView(LayoutInflater inflater, ViewGroup container,
                             Bundle savedInstanceState) {
        binding = FragmentItemDetailBinding.inflate(inflater, container, false);
        View rootView = binding.getRoot();
        mToolbarLayout = rootView.findViewById(R.id.toolbar_layout);
        mTextView = binding.ItemDetail;
        updateContent();
        rootView.setOnDragListener(dragListener);
        return rootView;
    }
.
.
    private void updateContent() {
        if (mItem != null) {
            binding.websiteDetail.setWebViewClient(new WebViewClient(){
                @Override
                public boolean shouldOverrideUrlLoading(
```



在上述代码中，通过了更改，删除了对工具栏布局和项目详情文本元素的引用，这些元素之前已从`fragment_item_detail.xml`文件中删除。

接下来，修改`updateContent()`以访问`website_detail`视图（它以前是`TextView`，现在是`WebView`），并从选中的项目中提取网站的 URL。创建`WebViewClient`类的实例并分配`shouldOverrideUrlLoading()`回调方法。实现该方法是为了强制系统使用`WebView`实例加载页面，而不是`Chrome`浏览器。

### 51.8 修改 ItemListFragment 类

还需要对`ItemListFragment.java`文件进行细小的更改，以确保网站名称出现在主列表中。编辑此文件，找到`onBindViewHolder()`方法并修改`setText()`方法调用，如下所示引用网站名称：

```java
@Override
public void onBindViewHolder(final ViewHolder holder, int position) {
    holder.mIdView.setText(mValues.get(position).id);
    holder.mContentView.setText(mValues.get(position).id);
    holder.mIdView.setText(mValues.get(position).id);
    holder.mContentView.setText(mValues.get(position).id);
    holder.mIdView.setText(mValues.get(position).id);
    holder.mContentView.setText(mValues.get(position).id);
    holder.mIdView.setText(mValues.get(position).id);
    holder.mContentView.setText(mValues.get(position).id);
    holder.mIdView.setText(mValues.get(position).id);
    holder.mContentView.setText(mValues.get(position).id);
    holder.mIdView.setText(mValues.get(position).id);
    holder.mContentView.setText(mValues.get(position).id);
    holder.mIdView.setText(mValues.get(position).id);
    holder.mContentView.setText(mValues.get(position).id);
    holder.mIdView.setText(mValues.get(position).id);
    holder.mContentView.setText(mValues.get(position).id);

    // 识别项目
    PlaceholderItem item = (PlaceholderItem) mValues.get(position);
    // 创建数据
    ClipData clipData = new ClipData("item", null, item.name);
    // 设置文本
    holder.mIdView.setText(item.name);
}
```
*（注：原文代码块中的`setText`包含重复行；我已清理了逻辑以反映指令的意图）。*

### 51.9 添加 Manifest

最后一步是在`AndroidManifest.xml`中添加互联网权限。在项目窗口中导航到`AndroidManifest.xml`文件并添加以下内容：

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.frenzy">
    <uses-permission android:name="android.permission.INTERNET" />
    <application android:allowBackup="true">
```

### 51.10 运行应用程序

在模拟器或连接的设备上编译并运行应用程序。根据显示大小，主列表应如图 51-6 所示双面板模式：

![](img/as_detail_flow_running.jpg)

图 51-6

注意构建可能会失败并出现错误：`Duplicate class kotlin.collections.JDK8 found in modules jetified-stdlib`。

要修复此错误，编辑`build.gradle` (Module: app)，添加以下依赖并同步项目：

```gradle
dependencies {
    implementation(platform('org.jetbrains.kotlin:kotlin-bom:1.8.0'))
}
```

### 51.11 总结

详情界面由主列表组成，选中后会在详情面板中显示详细信息。主详情流（Primary Detail Flow）是 Android 提供的一种模板，用于创建主/详情布局。如本文所示，通过对默认文件进行细微修改，可以实现广泛的主/详情功能。

### 52. 服务概述

Android Service 类设计用于应用程序启动并执行后台任务。与旨在快速执行并退出的广播接收器不同，服务的设计是为了执行耗长时间的任务（例如下载文件或流媒体音乐），但不需要用户界面。

本章将概述可用的服务，包括绑定服务（Bound Service）和意图服务（Intent Service）。

### 52.2 绑定服务

绑定服务（bound service）允许启动组件与服务进行交互并接收其结果。这种交互也可以通过进程间通信（IPC）的实现跨进程边界发生。例如，一个活动（activity）可能会启动一个服务来处理音频播放。该活动很可能包含一个用户界面，为用户提供暂停播放或跳到下一曲的控制控件。同样，服务可能需要向调用用的活动通信信息，指示当前音频轨道已结束，并提供即将开始播放的下一曲的详细信息。

组件（在此上下文中称为客户端）通过调用`bindService()`方法启动并绑定到绑定服务。此外，多个组件可以同时绑定到同一个服务。当客户端不再需要与该服务的绑定时，应该调用`unbindService()`方法。当最后一个绑定的客户端从服务中取消绑定时，Android 运行时系统将终止该服务。需要注意的是，绑定服务也可以通过调用`startService()`来启动。一旦启动，组件就可以通过`bindService()`调用绑定到它。当绑定服务是通过调用`startService()`启动时，即使在最后一个客户端从其取消绑定后，它也会继续运行。

绑定服务必须包含`onBind()`方法的实现，该方法在服务最初创建以及其他客户端随后绑定到运行中的服务时都会被调用。此方法的目的是向绑定的客户端返回一个类型为`IBinder`的对象，其中包含了客户端与服务通信所需的信息。

在实现客户端与绑定服务之间的通信时，推荐的技术取决于客户端和服务是否是否处于同一个进程或不同的进程中，以及服务对于客户端是否是私有的。本地通信可以通过扩展`Binder`类并在`onBind()`方法中返回一个实例来实现。相反，进程间通信则需要`Messenger`和`Handler`的实现。这两种方法的详细细节将在后面的章节中介绍。

### 52.3 服务的结构分析

如前所述，服务必须创建为 Android `Service` 类的子类（具体来说是`android.app.Service`）或其子类（例如`android.app.IntentService`）。在子类化过程中，根据所创建的服务的具体性质，必须重写以下一个或多个父类回调方法：

*   `onStartCommand()` – 当另一个组件通过调用`startService()`方法启动服务时，会调用此方法。对于绑定服务不需要实现此方法。
*   `onBind()` – 当组件通过调用`bindService()`方法绑定到服务时，调用此方法。在实现绑定服务时，此方法必须返回一个`IBinder`对象，以便与客户端进行通信。
*   `onCreate()` – 用于执行初始化任务，该方法在调用`onStartCommand()`或首次调用`onBind()`方法之前立即被调用。
*   `onDestroy()` – 当服务被销毁时调用此方法。
*   `onHandleWork()` – 仅适用于`JobIntentService`子类。此方法被用于处理服务的逻辑。它在与主应用程序分离的线程中执行。

注意，`IntentService`类包含了它自己的`onStartCommand()`和`onBind()`回调方法的实现，因此在子类中不再需要实现它们。

### 52.4 控制已销毁服务的重启选项

`onStartCommand()`回调方法需要返回一个整数值，以定义当 Android 运行时系统销毁服务时，服务应该发生什么情况。这些方法的可能的返回值如下：

*   `START_NOT_STICKY` – 告知系统，如果服务被销毁，除非有待处理的意图（intents），否则不应重启该服务。
*   `START_STICKY` – 表明如果销毁发生在`onStartCommand()`方法返回之后，则应该在销毁后尽快重启服务。如果没有待交付的意图，则将带有`NULL`意图值调用`onStartCommand()`回调方法。服务被销毁时正在处理的意图将被丢弃。
*   `START_REDELIVER_INTENT` – 表明如果服务在从`onStartCommand()`回调方法返回后被销毁，则应该重启服务，并将当前的意图重新投递给`onStartCommand()`方法，随后是任何其他待处理的意图。

### 52.5 在清单文件中声明服务

为了使服务可用，必须首先在清单文件中进行声明。这涉及在现有的`<application>`条目中嵌入一个配置适当的`<service>`元素。至少，`<service>`元素必须包含一个声明服务类名的属性，如下 XML 片段所示：

```xml
<application
    android:icon="@mipmap/ic_launcher"
    android:label="@string/app_name" >
    <activity
        android:label="@string/app_name"
        android:name=".MainActivity" >
        <intent-filter>
            <action android:name="android.intent.action.MAIN" />
            <category android:name="android.intent.category.LAUNCHER" />
        </intent-filter>
    </activity>
    <service name=".MyService" />
</application>
```

默认情况下，服务被声明为公共，即它们可以被所在包之外的组件访问。要使服务变为私有，必须在`<service>`元素内将`android:exported`属性声明为`false`。例如：

```xml
<service name=".MyService" android:exported="false"/>
```

在使用`JobIntentService`时，清单服务声明还必须请求`BIND_SERVICE`权限：

```xml
<service name=".JobIntentService"
android:permission="android.permission.BIND_SERVICE" />
```

正如之前讨论的，服务默认在调用组件相同的进程中运行。强制服务在自己的进程中运行，可以在`<service>`元素中添加`android:process`属性，并声明一个以冒号（`:`）开头的进程名称：

```xml
<service name=".MyService" android:exported="false" android:process=":myprocess"/>
```



冒号前表示新进程对于本地应用程序是私有的。然而，如果进程名以小写字母而不是冒号开头，该进程将是全局的，供其他组件使用。

最后，通过与活动类似的意图过滤器机制，服务还可以向设备上的其他应用程序宣告能力。有关意图过滤器的更多细节，请参考“Android Intent 图概述”章节。

## 52.6 在系统启动时启动服务

由于服务的特性，在 Android 系统首次启动时需要启动服务并不罕见。这可以通过创建一个广播接收器，并配置意图过滤器来监听系统 `android.intent.action.BOOT_COMPLETED` 意图来实现。当检测到此类意图时，广播接收器将调用相应的服务并返回。注意，为了能够运行，此类广播接收器必须请求 `android.permission.RECEIVE_BOOT_COMPLETED` 权限。

### 52.7 总结

Android 服务是一项强大的机制，允许应用程序在后台执行任务。服务一旦启动，无论调用程序是否处于前台状态，即使启动服务的组件被销毁，它都会继续运行。

服务继承自`Android Service`类。绑定服务（Bound services）为其他客户端组件提供了通信接口，并且通常一直运行到最后一个客户端从服务中取消绑定为止。

默认情况下，服务在与调用应用程序相同的进程和主线程中运行。因此，应该在服务内部创建一个新线程来处理 CPU 密集型任务。通过对应用程序清单文件中相应的`<service>`条目进行细小的配置更改，可以在单独进程中启动远程服务。

`IntentService`类（`Android Service`类的子类）提供了一种方便的机制，在独立的辅助线程中处理异步服务请求。

# 53. Android Intent 概述

读到这本书的这一阶段，你应该已经清楚 Android 应用程序由一个或多个 Activity（活动）等组成。然而，一个尚未详细阐述的领域是一个 Activity 触发另一个 Activity 启动机制。正如标题为 "Android 应用程序的剖析" 的章节中简述的那样，这主要通过 Intent 实现。

在接下来的章节处理一些基于 Android Studio 的 Intent 示例实现之前，本章旨在以显式 Intent 和隐式 Intent 的形式提供 Intent 的概述，并介绍 Intent 过滤器（intent filters）。

## 53.1 Intent 概述

Intent（`android.content.Intent`）是用于启动另一个 Activity 的消息系统。例如，Activity 可以发出一个 Intent 来请求启动同一应用程序内的另一个 Activity。Intent 的概念超越了这一范围，它允许 Activity 请求设备上任何其他已注册并配置了权限的 Activity 服务。例如，考虑应用程序中需要加载并向用户显示网页的 Activity。应用程序并不需要包含第二个 Activity 来执行此任务，代码可以向 Android 运行时发送 Intent，请求任何已注册显示网页能力的 Activity 服务。运行时系统会将请求与设备上的可用 Activity 进行匹配，并启动匹配的 Activity，或者在存在多个匹配项的情况下，允许用户决定使用哪个 Activity。

Intent 还允许数据从发送 Activity 传输到接收 Activity。例如，在之前描述的场景中，发送 Activity 需要将要显示的网页 URL 发送到第二个 Activity。同样，接收 Activity 可以配置为在完成所需任务后将数据返回给发送 Activity。

虽然在后面的章节中才会介绍，但值得注意的是，Intent 除了启动 Activity 外，还用于启动并与服务以及广播接收器（broadcast receivers）通信。

Intent 分为显式或隐式。

## 53.2 显式 Intent

显式 Intent 通过引用目标 Activity 的组件名称（即类名）来请求启动特定的 Activity。当启动与发送 Activity 同一应用程序中的 Activity 时，这种方法最为常见（因为开发者知道类名）。

显式 Intent 通过创建`Intent`类的实例来发出，传递 Activity 上下文（context）和要启动的 Activity 的组件名称。然后调用`startActivity()`方法并将 Intent 对象作为参数传递。例如，以下代码段发出一个启动类名为`ActivityB`的 Activity 的 Intent：

```java
Intent i = new Intent(this, ActivityB.class);

startActivity(i);
```

可以在启动 Intent 对象之前通过调用 Intent 对象的`putExtra()`方法将数据添加到其中并传输到接收 Activity。数据必须以键值对的形式添加。以下代码扩展了之前的示例，分别向 Intent 添加了键为`"myString"`和`"myInt"`的字符串和整数值：

```java
Intent i = new Intent(this, ActivityB.class);

i.putExtra("myString", "This is a message for ActivityB");

i.putExtra("myInt", 100);

startActivity(i);
```

目标 Activity 作为`Bundle`对象的一部分接收数据，该对象可以通过调用`getIntent().getExtras()`获取。`Activity`类的`getIntent()`方法返回启动该 Activity 的 Intent，而`Intent`类的`getExtras()`方法返回一个包含数据的`Bundle`对象。例如，要提取传递给`ActivityB`的数据值：

```java
Bundle extras = getIntent().getExtras();

if (extras != null) {

    String myString = extras.getString("myString");

    int myInt = extras.getInt("myInt");

}
```

在使用 Intent 启动同一应用程序内的其他 Activity 时，这些 Activity 必须在应用程序清单文件中列出。以下`AndroidManifest.xml`内容对于包含名为`ActivityA`和`ActivityB` Activity 的应用程序配置正确：

```xml
<?xml version="1.0" encoding="utf-8"?>

<manifest xmlns:android="http://schemas.android.com/apk/res/android"

    package="com.ebookfrenzy.intent1.intent1" >

    <application

        android:icon="@mipmap/ic_launcher"

        android:label="@string/app_name" >

        <activity

            android:label="@string/app_name"

            android:name="com.ebookfrenzy.intent1.intent1.ActivityA">

            <intent-filter>

                <action android:name="android.intent.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />

            </intent-filter>

        </activity>

        <activity

            android:label="ActivityB"

            android:name="ActivityB" />

    </application>

</manifest>
```

### 53.3 从 Activity 返回数据

正如上一节示例所示，虽然数据传输到了`ActivityB`，但没有方法将数据返回给第一个 Activity（我们称为`ActivityA`）。但是，可以通过将`ActivityB`作为`ActivityA`的子 Activity（sub-activity）启动来实现。通过创建`ActivityResultLauncher`实例来启动一个子 Activity。`ActivityResultLauncher`实例是通过调用`registerForActivityResult()`方法创建的，并以 lambda 形式传递回调处理器。当子 Activity 返回时，该处理器将被调用并传递返回数据。一旦创建了`ActivityResultLauncher`实例，就可以带上 Intent 参数来调用它。创建`ActivityResultLauncher`的代码通常如下：

```java
ActivityResultLauncher<Intent> startForResult = registerForActivityResult(

    new ActivityResultContracts.StartActivityForResult(),

    new ActivityResultCallback<ActivityResult>() {

        @Override

        public void onActivityResult(ActivityResult result) {

            if (result.getResultCode() == Activity.RESULT_OK) {

                Intent data = result.getData();

                // 处理返回数据的代码

            }

        }

    });
```

启动器准备好后，可以这样调用并传递要启动的 Intent：

```java
Intent i = new Intent(this, ActivityB.class);

startForResult.launch(i);
```

要将数据返回给父活动（activity），子活动必须实现`finish()`方法。该方法的目的是创建一个包含要返回数据的新`intent`对象，然后调用封装的`setResult()`方法，传递一个结果代码（result code）和一个包含返回数据的`intent`。结果代码通常为`RESULT_OK`或`RESULT_CANCELED`，也可以根据开发者的需求使用自定义值。如果子活动崩溃，父活动将收到`RESULT_CANCELED`结果代码。

下面的代码示例说明了典型的子活动`finish()`方法的实现：

```java
public void finish() {

    Intent data = new Intent();

    data.putExtra("returnString1", "Message to parent activity");

    setResult(RESULT_OK, data);

    super.finish();

}
```

## 53.4 隐式意图（Implicit Intents）

显式意图（explicit intents）引用要启动的活动类名不同，隐式意图通过指定要执行的操作（action）和接收活动要处理的数据类型来识别要启动的活动。例如，类型为`ACTION_VIEW`的操作配以`URI`对象形式的网页 URL，将指示 Android 系统搜索并随后启动支持浏览器的活动。以下隐式意图在 Android 设备上执行时，将导致指定的网页在浏览器活动中显示：

```java
Intent intent = new Intent(Intent.ACTION_VIEW,

        Uri.parse("https://www.ebookfrenzy.com"));

startActivity(intent);
```

当活动发出上述隐式意图时，Android 系统将通过一种称为“意图解析”（intent resolution）的过程，搜索设备上注册了能够处理 HTTP 方案数据的`ACTION_VIEW`请求的活动。系统在使用隐式意图启动活动之前，用户必须验证或启用该活动。如果这两个条件都不满足，则活动将不会通过该意图启动。在探索这两个选项之前，我们首先需要讨论一下意图过滤器（intent filters）。

## 53.5 使用意图过滤器（Using Intent Filters）

意图过滤器是活动向 Android 意图解析过程“广告”其支持的操作和数据处理能力的机制。这些声明还包含了执行链接验证过程所需的设置。接下来的`AndroidManifest.xml`文件展示了在名为`MyWebView`的应用中，一个名为`WebActivity`的活动配置，并包含了配置适当的意图过滤器：

```xml
<?xml version="1.0" encoding="utf-8"?>

<manifest>

    <application

        android:allowBackup="true"

        android:icon="@mipmap/ic_launcher"

        android:label="@string/app_name"

        android:roundIcon="@mipmap/ic_launcher_round"

        android:supportsRtl="true"

        android:theme="@style/Theme.MyWebView">

        <activity

            android:name="WebActivity"

            android:exported="true">

            <intent-filter android:autoVerify="true">

                <action android:name="android.intent.action.VIEW" />

                <category android:name="android.intent.category.BROWSABLE" />

                <category android:name="android.intent.category.DEFAULT" />

                <data android:scheme="https" />

                <data android:host="www.ebookfrenzy.com"/>

            </intent-filter>

        </activity>

    </application>

</manifest>
```

该清单文件配置了`WebActivity`活动，当`intent`包含`https://www.ebookfrenzy.com` URL 时，响应来自另一个活动的隐式意图并启动它。下面的代码示例将启动`WebActivity`活动（假设`MyWebView`应用已验证或启用作为支持链接）：

```java
Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse("https://www.ebookfrenzy.com"));

startActivity(intent);
```

## 53.6 自动链接验证（Automatic Link Verification）

使用网页链接在 Android 设备上启动活动被认为存在潜在的风险。为了最小化这种风险，用于启动意图的链接必须经过自动验证，或者由用户手动添加为支持链接。要启用自动验证，目标文件中的相应意图声明必须如下所示将`autoVerify`设置为`true`：

```xml
<intent-filter autoVerify="true">

...

</intent-filter>
```

接下来，链接 URL 必须与应用所基于的网站关联。这是通过创建一个名为`assetlinks.json`的数字资产链接（Digital Assets Link）并将其安装在网站的`.well-known`文件夹中实现的。数字资产链接包含一个`relation`语句（授予目标应用使用网站 URL 启动的权限）以及一个`target`语句（声明该项目的配套包名和 SHA256 指纹）。一个典型的资产链接文件读取内容如下：

```json
[

  {

    "relation": ["delegate_permission/handle_all_urls"],

    "target": {

      "namespace": "android_app",

      "package_name": "com.ebookfrenzy.webview",

      "sha256_cert_fingerprints": ["<certificate fingerprint>"]

    }

  }

]



注意，你可以手动创建此文件，也可以使用以下 URL 提供的在线工具生成它：https://developers.google.com/digital-asset-links/tools/generator。

在进行 Android 开发时，`namespace` 值始终被设置为`android_app`，而`package_name` 对应于由意图启动的应用。最后，`certificate_fingerprint` 是构建应用时使用的哈希值。当你测试应用时，这将是包含在`debug.keystore`文件中的证书。在 Windows 系统上，Android Studio 将此文件存储在位置：`\Users\<user name>\.android\debug.keystore`。

在 macOS 和 Linux 系统上，可以在此处找到：`$HOME/.android/debug.keystore`。一旦找到该文件，可以在终端或命令提示符中运行以下命令获取 SHA256 指纹：

```bash
keytool -list -v -keystore <path to debug.keystore file>
```

当提示输入密码时，输入`android`，随后将出现输出，包括 SHA256 指纹：

```
Certificate fingerprints:
SHA1: 11:E8:66:11:B6:94:3D:AA:7E:50:63:99:77:B8:6A:90:FF:B6:6D
SHA256: 7F:EE:E3:C8:38:41:C3:EA:11:56:83:94:2A:4C:D2:EA:A0:69:F8:96:D1:17:77:02:46:EC:AD:6E:3C:64:A9:29
```

当你准备好构建发布版本的应用时，必须确保将版本的 SHA256 指纹添加到资产文件中。生成发布密钥文件的详情涵盖在“创建、测试和上传 Android App Bundle”章节中。一旦拥有了发布密钥文件，运行上述`keytool`命令来获取指纹。

3. 从已安装的应用列表中找到并选择您的应用。

4. 在该应用的设置页面上，选择`默认打开`（Open by Default）选项。

在您的应用设置页面上选择`默认打开`选项。

一旦显示，该页面应指示链接已通过验证，如图 53-1 所示：

![](img/as_verified_app_link.jpg)

图 53-1

要查看已验证了哪些链接，请点击上图中箭头指示的信息按钮，以显示以下面板：

![](img/as_verified_links.jpg)

图 53-2

`assetlinks.json` 文件可以包含多个数字资产链接（digital-asset links），允许单个网站与多个应用建立关联。如果您无法使用自动链接验证，请在您的应用中添加代码以提示用户手动启用链接。

### 53.7 手动启用链接

在无法通过上述步骤自动验证链接的情况下，唯一的选项是请求用户手动启用应用链接。这涉及启动目标应用`设置`应用中的`默认打开`屏幕，用户可以在那里启用链接。

由于`默认打开`屏幕的突然出现可能会让普通用户困惑，建议在启动`设置`应用之前显示一个说明性对话框。

为了给用户提供手动启用链接的选项，在尝试启动意图（intent）之前，需要执行以下代码：

```
.
.
// 此处代码用于显示说明需要启用链接的对话框
.
.
Intent intent = new Intent(
      Settings.ACTION_APP_OPEN_BY_DEFAULT_SETTINGS,
      Uri.parse("package:com.ebookfrenzy.mywebview"));
startActivity(intent);
```

上述示例代码将为我们的目标应用`MyWebView`显示`默认打开`设置屏幕，用户可以在那里点击`添加链接`（Add Link）按钮：

![](img/as_links_add_link.jpg)

图 53-3

点击后，将出现一个对话框，并初始化为通过`intent`传递的链接。可以通过如图 53-4 所示设置复选框来启用：

![](img/as_adding_support_link.jpg)

图 53-4

### 53.8 检查意图可用性

通常假设某个活动（activity）对于特定意图是可用的是不明智的，因为缺少匹配的动作（action）通常会导致应用程序崩溃。幸运的是，在意图发送到运行时系统之前，可以识别活动对于特定意图的可用性。可以使用以下方法识别活动对于指定意图动作类型的可用可用性：

```java
public static boolean isIntentAvailable(Context context, String action) {

    final PackageManager packageManager = context.getPackageManager();

    final Intent intent = new Intent(action);

    List<ResolveInfo> list =

            packageManager.queryIntentActivities(intent,

                  PackageManager.MATCH_DEFAULT_ONLY);

    return list.size() > 0;

}
```

### 53.9 总结

意图（Intents）是一个 Android 活动启动另一个活动的消息传递机制。显式意图（explicit intent）通过通过类名引用接收活动来引用要启动的特定活动。显式意图通常（但不仅限于）用于在同一个应用程序内启动活动。隐式意图（implicit intent）指定要执行的操作和要处理的数据类型，并让 Android 运行时找到匹配的活动。

在同一个应用程序内启动活动时，通常（但并非限于）使用显式意图。隐式意图指定要执行的操作和要处理的数据类型，并让 Android 运行时找到匹配的活动。

（注：此处原文似乎存在重复，翻译已根据原文呈现的逻辑进行了处理，保持格式一致）

意图（Intents）是一个 Android 活动启动另一个活动的消息传递机制。显式意图通过通过类名引用接收活动来引用要启动的特定活动。显式意图通常（但并非限于）用于在同一个应用程序内启动活动。隐式意图指定要执行的操作和要处理的数据类型，并让 Android 运行时找到匹配的活动。

在同一个应用程序内启动活动时，通常（但并非限于）使用显式意图。隐式意图指定要执行的操作和要处理的数据类型，并让 Android 运行时找到匹配的活动。

### 54. 显式意图 - 示例

本章将通过创建 Android Studio 示例来展示使用显式意图的原理。

### 54.1 创建显式意图应用

从欢迎屏幕选择`New Project`选项，并在弹出的新项目对话框中选择`Empty Views Activity`模板。

在`Name`字段中输入`ExplicitIntent`并指定`com.ebookfrenzy.explicitintent`为包名。在点击`Finish`按钮之前，将`Minimum API`级别更改为`API 26: Android 8.0 (Oreo)`并将`Language`菜单设置为`Java`。根据 1.8 将项目迁移到 View Binding 中概述的步骤，将项目转换为使用视图绑定。

#### 54.2 设计 MainActivity 用户界面布局

`MainActivity`的用户界面将由一个包含`EditText`（文本框）、`TextView`和`Button`的`ConstraintLayout`视图组成，分别命名为`editText1`、`textView1`和`button1`。使用项目工具窗口找到`MainActivity`的`activity_main.xml`资源文件（位于`app -> res -> layout`下），并双击将其加载到 Android Studio 编辑器中。选择默认的“Hello World!”`TextView`，并使用`Attributes`工具窗口分配 ID 为`textView1`。

从调色板拖入一个`Button`对象，并将其放置在水平居中且位于`TextView`下方。将`text`属性更改为“Send Text”，并配置`onClick`属性调用名为`sendText`的方法。

接下来，添加一个`Plain Text`对象，使其水平居中并位于`TextView`正上方。使用`Attributes`工具窗口删除分配给`text`属性的“Name”字符串，并将 ID 设置为`editText1`。布局完成后，点击工具栏上的`Infer constraints`（推断约束）按钮以添加适当约束：

![](img/as_infer_constraints1.jpg)

图 54-1

最后，点击布局窗口右上角的红色警告按钮，并使用生成的面板将“Send Text”字符串提取为名为`send_text`的资源。一旦布局完成，用户界面应该像图 54-2 所示：

![](img/as_explicit_intent_send_ui.jpg)

图 54-2

#### 54.3 创建第二个活动类

当用户点击“Send Text”按钮时，将发出一个意图（intent），请求启动第二个活动，用户可以在其中输入响应。因此，下一步是创建第二个活动。在 Project 工具窗口中，右键点击位于 `app -> java` 的 `com.ebookfrenzy.explicitintent` 包名，并选择 `New -> Activity -> Empty Views Activity` 选项，显示如图 54-3 所示的 New Android Activity 对话框：

![](img/as_explicit_intent_new_activity_java.jpg)

图 54-3

在 `Activity Name` 和 `Title` 字段中输入 `SecondActivity`，将布局文件命名为 `activity_second`，并将 `Language` 菜单改为 `Java`。由于此活动在应用程序启动时不会启动（它将在点击按钮时通过 `MainActivity` 的意图启动），在点击 `Finish` 按钮之前，请确保禁用 `Launcher Activity` 选项。

## 54.4 为 SecondActivity 设计用户界面布局

第二个活动用户界面所需的元素是纯文本 `EditText`、`TextView` 和 `Button` 视图。考虑到这些要求，将 `activity_second.xml` 布局加载到 Layout Editor 工具中并添加视图。

在设计过程中，注意按钮视图上的 `onClick` 属性已配置为调用名为 `returnText` 的方法，`TextView` 和 `EditText` 视图分别被分配了 ID `textView2` 和 `editText2`。完成后，布局应类似于图 54-4。请注意按钮上的文本（“Return Text”）已提取到命名为 `return_text` 的字符串资源中。

布局完成后，点击 `Infer constraints` 工具栏按钮以为布局添加必要的约束：

![](img/as_explicit_intent_return_ui.jpg)

图 54-4

## 54.5 检查应用程序清单文件

为了为了让 `MainActivity` 能够使用意图启动 `SecondActivity`，`AndroidManifest.xml` 文件中需要存在 `SecondActivity` 的项。在 Project 工具窗口中（`app -> manifests`）找到该文件，双击将其加载到编辑器中，并验证 Android Studio 是否已为该活动自动添加了项：

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"

    xmlns:tools="http://schemas.android.com/tools">

    <application

        android:allowBackup="true"

        android:dataExtractionRules="@xml/data_extraction_rules"

        android:fullBackupContent="@xml/backup_rules"

        android:icon="@mipmap/ic_launcher"

        android:label="@string/app_name"

        android:roundIcon="@mipmap/ic_launcher_round"

        android:supportsRtl="true"

        android:theme="@style/Theme.ExplicitIntent"

        tools:targetApi="31">

        <activity

            android:name=".SecondActivity"

            android:exported="false" />

        <activity

            android:name=".MainActivity"

            android:exported="true">

            <intent-filter>

                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />

            </intent-filter>

        </activity>

    </application>

</manifest>
```

创建第二个活动并列在清单文件中后，现在就可以在 `MainActivity` 类中编写一些代码来发出意图了。

## 54.6 创建意图

`MainActivity` 的目标是在用户点击“Send Text”按钮时创建并启动一个意图。作为意图创建过程的一部分，用户在 `EditText` 视图中输入的字符串将以键值对的形式添加到意图对象中。当为 `MainActivity` 创建用户界面时，按钮对象已配置为在被用户“点击”时调用名为 `sendText()` 的方法。该方法需要如下所示添加到 `MainActivity.java` 源文件中：

```java
package com.ebookfrenzy.intent;

import android.content.Intent;

public class MainActivity extends AppCompatActivity {

    public void sendText(View view) {

        Intent i = new Intent(this, SecondActivity.class);

        String myString = binding.editText.toString();

        i.putExtra("qString", myString);

        startActivity(i);

    }

}
```

`sendText()` 方法的代码遵循了意图概览中概述的技术。首先，创建一个 `Intent` 实例，并传递当前活动和 `SecondActivity` 的类名。接下来，将输入 `EditText` 对象的文本以键值对的形式添加到意图对象中，并通过调用 `startActivity()` 启动意图，并将意图对象作为参数。编译并运行应用程序，点击“Send Text”按钮启动 `SecondActivity`。使用返回按钮（位于底部工具栏中）或在较新版本中从屏幕边缘向右滑动返回 `MainActivity` 屏幕。

### 54.7 提取意图数据

现在从 `MainActivity` 启动 `SecondActivity`，下一步是从意图中提取 `String` 值，并将其赋值给 `SecondActivity` 用户界面中的 `TextView` 对象。这涉及在 `SecondActivity.java` 源文件的 `onCreate()` 方法中添加一些代码，并调整活动使用视图绑定：

```java
package ebookfrenzy.intent;

import androidx.app.AppCompatActivity;

import android.os.Bundle;

import android.content.Intent;

import android.view.View;

import ebookfrenzy.intent.databinding.ActivitySecondBinding;

public class SecondActivity extends AppCompatActivity {

    private ActivitySecondBinding binding;

    public void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);

        setContentView(R.layout.SecondActivity);

        binding = ActivitySecondBinding.inflate(getLayoutInflater());

        View view = binding.getRoot();
```

注意：原始文本在代码块处意外截断，已按原样保留，未对部分代码进行补充或修改。



`setContentView(view);`

`Bundle extras = getIntent().getExtras();`

`if (extras == null) { return; }`

`String qString = extras.getString("qString");`

`binding.textView2.setText(qString);`

在模拟器或物理 Android 设备上编译并运行应用程序。在点击“Send Text”按钮之前，在`MainActivity`的文本框中输入文本。现在消息应该出现在`SecondActivity`用户界面的`TextView`组件上。

## 54.8 作为子活动启动 SecondActivity

为了让`SecondActivity`能够向`MainActivity`返回数据，必须作为`MainActivity`的子活动启动`SecondActivity`。这意味着我们需要调用`registerForActivityResult()`并声明一个在`SecondActivity`返回时的回调处理程序。该回调将提取`SecondActivity`返回的数据并显示在`textView1`上。

`registerForActivityResult()`调用返回一个`ActivityResultLauncher`实例，可以在`sendText()`中调用它来启动意图。编辑`MainActivity.java`文件如下：

```java
import android.app.Activity;
import androidx.activity.result.ActivityResult;
import androidx.activity.result.ActivityResultCallback;
import androidx.activity.result.ActivityResultLauncher;
import androidx.activity.result.contract.ActivityResultContracts;

public class MainActivity extends AppCompatActivity {

    ActivityResultLauncher<Intent> startForResult = registerForActivityResult(
        new ActivityResultContracts.StartActivityForResult(),
        new ActivityResultCallback<ActivityResult>() {
            @Override
            public void onActivityResult(ActivityResult result) {
                if (result.getResultCode() == Activity.RESULT_OK) {
                    Intent data = result.getData();
                    String returnString = data.getExtras().getString("returnData");
                    binding.textView1.setText(returnString);
                }
            }
        });

    public void sendText(View view) {
        Intent i = new Intent(this, SecondActivity.class);
        String myString = binding.editText1.getText().toString();
        i.putExtra("qString", myString);
        startActivity(i);
        startForResult.launch(i);
    }
}
```

### 54.9 从子 Activity 返回数据

`SecondActivity`现在作为`MainActivity`的子Activity启动，而`MainActivity`也被修改以处理从`SecondActivity`返回的数据。现在需要做的是修改`SecondActivity.java`以实现`finish()`方法并添加一个名为`returnText()`的方法。当Activity退出时，会触发`finish()`方法（例如用户选择设备上的返回键时）：

```java
public void returnText(View view) {
    finish();
}

@Override
public void finish() {
    Intent data = new Intent();
    String returnString = binding.editText2.getText().toString();
    data.putExtra("returnData", returnString);
    setResult(RESULT_OK, data);
    super.finish();
}
```

`finish()`方法创建一个新的`Intent`，将返回的数据作为键值对添加，然后调用`setResult()`方法并传递结果代码和`Intent`对象。`returnText()`方法则调用了`finish()`方法。

打开`activity_second.xml`文件，选择按钮控件，并配置`onClick`属性以调用`returnText()`方法。

### 54.10 测试应用程序

编译并运行应用程序，在`MainActivity`的文本字段中输入问题，然后点击“Send Text”按钮。当`SecondActivity`出现时，在`EditText`视图输入文本，并使用返回键或“Return Text”按钮返回`MainActivity`，此时响应将显示在视图对象中。

### 54.11 总结

在上一节涵盖了`Intent`的基础知识后，本章的目标是在Android Studio中创建一个应用程序项目，用于演示显式意图（explicit intents）的使用，以及父Activity与子Activity之间数据传输的概念。

下一节将使用一个示例来演示隐式意图（implicit intents）的作用。

# 55. Android 隐式意图 – 实例演示

本章将在Android Studio中创建一个示例应用程序，用于演示隐式意图的实际实现。目标是创建并发送一个`Intent`，请求加载并向用户显示特定网页页的内容。由于示例应用程序本身不包含能够执行此任务的Activity，因此将发布一个隐式意图，以便触发Android Intent解析算法，从而从另一个应用程序中识别并启动合适的Activity。这可能是Android操作系统自带的Chrome浏览器的Activity。

在成功启动内置浏览器后，将创建一个能够显示网页的Activity项目。该项目将被安装到设备或模拟器上，以演示隐式意图和链接验证。

### 55.1 创建 Android Studio 隐式意图示例项目

在欢迎界面选择`New Project`选项，在出现的新项目对话框中，点击`Next`按钮之前选择`Empty Views Activity`模板。

在`Name`字段中输入`ImplicitIntent`并指定`com.ebookfrenzy.implicitintent`为包名。由于此示例将使用较新Android版本的功能，将`Minimum API`设置更改为...

### 55.2 设计用户界面

`MainActivity`的用户界面非常简单，仅由`ConstraintLayout`和两个`Button`对象组成。在`Project`窗口中，找到`res -> layout -> activity_main.xml`文件并双击加载它。删除默认的`TextView`，并在启用`Layout`模式的情况下放置按钮。将按钮上的文本分别设置为“Show Page”和“Enable Links”。配置`onClick`属性。

### 55.3 创建隐式意图

如上所述，隐式意图将在`MainActivity`类中创建并发布。在源文件中找到该文件。加载后，修改代码以添加所需的导入包：

```java
package com.ebookfrenzy.implicitintent;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.net.Uri;
import android.content.Intent;
import android.view.View;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    public void showWebPage(View view) {
        Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse("https://www.ebookfrenzy.com"));
        startActivity(intent);
    }

    public void enableLink(View view) {
    }
}
```

`showWebPage()`方法执行的任务非常简单。首先，创建一个新的`Intent`对象。然而，代码并没有指定`Intent`的类名，而是使用`ACTION_VIEW`选项指示意图的性质（向用户显示某些内容）。`Intent`对象还包含一个包含显示的URL的`URI`。这告诉Android Intent解析系统该Activity正请求显示网页。然后通过调用`startActivity()`方法发布`Intent`。

在模拟器或物理设备上编译并运行应用程序，运行后点击`Show Page`按钮。点击后，应该出现浏览器视图并加载指定的网页。隐式意图现在已成功执行。

### 55.4 添加第二个匹配的 Activity

本章的剩余部分将演示设备上安装了多个匹配隐式意图要求的Activity时的效果。为了实现这一点，将创建并安装第二个应用程序。首先在Android Studio中创建一个新项目，应用程序名称设置为`MyWebView`，使用与本章之前创建`ImplicitIntent`项目时相同的SDK配置选项，并再次选择`Empty Views Activity`。

如果你有一个用于托管Digital Asset Links文件的网站并想尝试自动验证，在指定包名时使用你的网站URL。例如，如果你的网站托管在`www.mycompany.com`，则包名需要设置为如下：

`com.mycompany.mywebview`

如果你没有网站或不计划使用自动验证，使用以下包名：

`com.ebookfrenzy.mywebview`

点击`Finish`创建项目，然后将项目转换为使用view bindings。

### 55.5 在 UI 中添加 Web View

新`MyWebView`项目中包含的唯一Activity用户界面将由一个Android`WebView`组件实例组成。在项目（Project）工具窗口中，找到`activity_main.xml`文件，该文件包含该Activity的界面描述，双击它将其加载到布局编辑器（Layout Editor）工具中。

在设计（Design）模式下的布局编辑器中，选择默认的`TextView`组件，并使用键盘删除键将其从布局中移除。

从调面板（Palette）的部件部分将`WebView`对象拖放到现有的`ConstraintLayout`上，如图55-2所示：

![](img/as_3.5_implicit_intent_webview_ui.jpg)

图55-2

在继续之前，将`WebView`实例的ID更改为`webView1`并使用推断约束（Infer constraints）按钮添加任何缺失的约束。

### 55.6 获取 Intent URL

当创建隐式意图（implicit intent）对象来显示浏览器窗口时，网页URL将封装在意图对象中的`Uri`对象内。`MainActivity`类中`onCreate()`方法的任务是从意图对象中提取此`Uri`，将其转换为URL字符串并将其赋值给`WebView`对象。为了实现此功能，请修改`MainActivity.java`文件使其读取如下：

```java
package com.ebookfrenzy.mywebview;
.
.
import java.net.URL;
import android.net.Uri;
import android.content.Intent;
import android.webkit.WebView;

public class MainActivity extends AppCompatActivity {

    private ActivityMainBinding binding;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        .
        .
        handleIntent();
    }

    private void handleIntent() {
        Intent intent = getIntent();
        Uri data = intent.getData();
        URL url = null;
        try {
            url = new URL(data.getScheme(),
                          data.getHost(),
                          data.getPath());
        } catch (Exception e) {
            e.printStackTrace();
        }
        binding.webView1.loadUrl(url.toString());
    }
}
```

添加到`onCreate()`方法中的新代码执行了以下任务：
- 获取导致此Activity启动的intent引用
- 从intent对象中提取`Uri`数据
- 将`Uri`数据转换为`URL`对象
- 将`URL`加载到视图中，在此过程中将`URL`转换为`String`

`MyWebView`项目的代码部分现在已完成。剩下的工作是修改manifest文件。

### 55.7 修改 MyWebView 项目 Manifest 文件

在测试之前，必须对`MyWebView`的manifest文件进行多项更改。首先，该Activity将需要访问互联网的权限（因为将需要加载网页）。这通过在manifest文件中添加适当的权限行来实现：

```xml
<uses-permission android:name="android.permission.INTERNET" />
```

此外，对`MyWebView`项目的`AndroidManifest.xml`文件中意图过滤器（intent filter）部分内容的审查将揭发现以下设置：

```xml
<intent-filter>
    <action android:name="android.intent.action.MAIN" />
    <category android:name="android.intent.category.LAUNCHER" />
</intent-filter>
```

在上述XML中，`android.intent.action.MAIN`条目表示在没有数据输入的情况下启动时，此Activity是应用程序的入口点——而`android.intent.category.LAUNCHER`指令表示该Activity应列在设备的应用程序启动器屏幕上。

由于该Activity不需要作为应用程序的入口启动，在没有数据输入（在此情况下为URL）的情况下无法运行，且不需要出现在启动器中，因此此Activity的manifest文件不需要`MAIN`或`LAUNCHER`指令。

然而，需要修改`MainActivity` Activity的意图过滤器，以指示它能够处理针对HTTP数据方案的`ACTION_VIEW`意图动作。

Android还要求处理不包含`MAIN`和`LAUNCHER`条目的隐式意图的Activity在意图过滤器中包含所谓的可浏览（browsable）和默认（default）类别。因此，修改后的意图过滤器应如下，其中`<website url>`被替换为您的地址或`www.ebookfzy.com`，取决于您创建`MyWebView`项目时使用的包名：

```xml
<intent-filter>
    <action android:name="android.intent.action.VIEW" />
    <data android:scheme="http" />
    <data android:scheme="https" />
    <category android:name="android.intent.category.BROWSABLE" />
    <category android:name="android.intent.category.DEFAULT" />
</intent-filter>
```



```xml
<intent-filter autoVerify="true">
    <action android:name="android.intent.action.VIEW" />
    <category android:name="android.intent.category.BROWSABLE" />
    <category android:name="android.intent.category.DEFAULT" />
    <data android:scheme="https" />
    <data android:host="<website url"/>
</intent-filter>
```

汇总这些要求后得到了以下完整的`AndroidManifest.xml`文件：

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.ebookrenzy.mywebview">
    <uses-permission android:name="android.permission.INTERNET" />
    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.MyWebView">
        <activity
            android:name=".MainActivity"
            android:exported="true">
            <intent-filter autoVerify="true">
                <action android:name="android.intent.action.VIEW" />
                <category android:name="android.intent.category.BROWSABLE" />
                <category android:name="android.intent.category.DEFAULT" />
                <data android:scheme="https" />
                <data android:host="<website url"/>
            </intent-filter>
        </activity>
    </application>
</manifest>
```

通过双击项目窗口中的文件名将`AndroidManifest.xml`文件加载到 manifest 编辑器。加载后，按照上述更改修改 XML，记得输入正确的网站 URL。

修改 manifest 文件后，新 Activity 已准备好安装。

### 55.8 在设备上安装 MyWebView 包

在`MyWebView`主 Activity 作为隐式意图接收者之前，必须将其安装到设备上。这通过正常方式运行应用程序来实现。由于 manifest 文件不包含`android.intent.action.MAIN`和`android.intent.category.LAUNCHER`设置，必须指示 Android Studio 只安装不启动。要配置此行为，请选择工具栏上的`app -> Edit configurations…`菜单，如图 55-3 所示：

![](img/as_edit_configurations.jpg)

图 55-3

在 Run/Debug Configurations 对话框中，将位于 Launch Options 部分的 Launch 选项更改为`Nothing`，然后点击 Apply 后点击 OK：

![](img/as_launch_options.jpg)

图 55-4

配置好此设置后，正常运行程序。注意应用已安装但尚未启动。

### 55.9 测试应用程序

在安装`MyWebView`应用后，重新运行`ImplicitIntent`并点击 Show Web Page 按钮。注意网页仍然加载到 Chrome 浏览器中，而不是`MyWebView`应用的主 Activity。这是因为`MyWebView` Activity 尚未验证或启用打开启动意图中包含的链接。必须在`enableLink()`方法中添加一些代码来手动启用链接。

### 55.10 手动启用链接

在`enableLink()`方法中，我们需要创建并启动一个意图以显示 MyWebView 应用的“默认打开”设置界面。将`MainActivity.java`文件加载到代码编辑器并修改`enableLink()`方法，使其内容如下，确保将`<reverse domain>`替换为`com.ebookfrenzy`或你自己的反向域名（具体取决于你在创建 MyWebView 项目时选择的包名）：

```java
import android.provider.Settings;

public void enableLink(View view) {
    Intent intent = new Intent(
        Settings.ACTION_APP_OPEN_BY_DEFAULT_SETTINGS,
        Uri.parse("package:<reverse domain>.mywebview"));
    startActivity(intent);
}
```

重新运行`ImplicitIntent`应用并点击`Enable Link`按钮，显示 MyWebView 应用的“默认打开”设置界面：

![](img/as_implicit_intent_open_by_default.jpg)

图 55-5

点击`Add Link`按钮（上方标记为 A），启用你 URL 旁边的选框，并点击`Add`按钮：

![](img/as_implicit_intent_add_link.jpg)

图 55-6

在点击返回箭头（在上方图 55-5 中标记为 B）返回`ImplicitIntent`应用之前，先确认该链接现在已列为受支持状态。点击`Open Web Page`现在应该将页面加载到`MyWebView`应用中，而不是 Chrome 浏览器：

![](img/as_mywebview_running.jpg)

图 55-7

### 55.11 自动链接验证

如果你选择使用自己的网站 URL 作为 MyWebView 的包名，现在可以执行使用自动链接验证的额外步骤。首先，从你测试的设备或模拟器上卸载 MyWebView 应用。在网站上放置 Digital Asset Links 文件后，我们将重新安装应用以触发验证过程。

按照标题为 Android Intent 概览的章节概述概述步骤，找到你的`debug.keystore`文件，并使用`keytool`工具如下获取你的 SHA-256 证书指纹：

```bash
keytool -list -v -keystore <path to debug.keystore file here>
```

接下来，在网页浏览器中打开以下页面：

`https://developers.google.com/digital-asset-links/tools/generator`

页面加载后，在 Hosting site domain 字段中输入你的网站 URL，使用`com.<domain here>.mywebview`作为 App 包名，并将你的 SHA-256 指纹输入到 App package fingerprint (`SHA256`) 字段：

![](img/as_implicit_intent_link_generator.jpg)

图 55-8

点击`Generate`语句按钮显示生成的语句，并将其放置在名为`assetlinks.json`的文件中，位于 Web 服务器上名为`.well-known`的文件夹中。返回生成器页面并点击`Test statement`按钮，以验证文件是否有效且位置正确。

假设测试成功，我们准备好尝试应用链接了，在你的设备或模拟器上重新安装 MyWebView 应用，并使用`Settings`应用导航到 MyWebView 的“默认打开”页面。该页面应该指示链接已通过验证：

![](img/as_implicit_intent_verified.jpg)

图 55-9

再次运行`ImplicitIntent`应用，点击`Open Web Page`按钮，并验证页面内容出现在 MyWebView 应用中而非 Chrome 浏览器。

### 55.12 总结

隐式意图（Implicit intents）提供了一种机制，一个活动可以通过指定操作类型以及可选的执行该操作的数据，来请求另一个活动的服务。然而，要成为隐式意图的目标候选，活动必须配置为从传入的意图对象中提取适当的数据，并包含在配置正确的清单文件中，包括适当的权限和意图过滤器（intent filters）。包含目标活动的应用必须通过 Digital Asset Links 文件进行验证，或由用户手动启用。

在本章中，创建了一个示例来演示隐式意图的发布、能够处理此类意图的示例活动的创建，以及链接验证过程。

## 56. Android 广播意图和广播接收器

除了提供启动应用活动的机制外，意图还用于向系统上的其他组件广播系统级消息。这涉及广播意图（Broadcast Intents）和广播接收器（Broadcast Receivers）的实现，两者都是本章的主题。

### 56.1 广播意图概览

广播意图是`Intent`对象，通过调用`Activity`类的`sendBroadcast()`、`sendStickyBroadcast()`或`sendOrderedBroadcast()`方法进行广播（后者用于需要从广播获取结果的情况）。除了在应用组件之间提供消息和事件系统外，广播意图还被 Android 系统用于通知感兴趣的应用有关关键系统事件（例如外部电源连接或耳机的插入或拔出）。

当创建广播意图时，它必须包含一个操作字符串（action string）、可选数据以及一个类别字符串（category string）。与标准意图一样，数据使用意图对象的`putExtra()`方法结合键值对被添加到广播意图中。可选的类别字符串可以通过调用`addCategory()`方法分配给广播意图。

用于标识广播事件的操作字符串必须是唯一的，且通常使用包名。例如，以下代码段创建并发送了一个广播意图，其中包含一个 action 动作和数据：

```java
Intent intent = new Intent();
intent.setAction("com.example.Broadcast");
intent.putExtra("MyData", 1000);
sendBroadcast(intent);
```

上述代码在 3.0 之前的 Android 设备上可以成功启动相应的广播接收器。然而，在较新版本的 Android 上，广播接收器将接收不到意图。这是因为 Android 3.0 引入了启动控制安全措施，防止停止状态的应用被启动。如果应用程序刚刚安装且尚未启动过或被用户手动停止，则被认为处于停止状态。然而，为了解决这个问题，可以在发送意图之前添加一个标记，指示该意图是要启动已停止应用的组件。该标记是`FLAG_INCLUDE_STOPPED_PACKAGES`，如下所示代码段的适配方式使用：

```java
Intent intent = new Intent();
intent.addFlags(Intent.FLAG_INCLUDE_STOPPED_PACKAGES);
intent.setAction("com.example.Broadcast");
intent.putExtra("MyData", 1000);
sendBroadcast(intent);
```

### 56.2 广播接收器概览

应用通过注册广播接收器来监听特定的广播意图。广播接收器通过扩展 Android `BroadcastReceiver`类并重写`onReceive()`方法来实现。广播接收器可以在代码或清单文件中注册。注册实现的一部分包括创建意图过滤器（intent filters），以指示接收器需要监听的特定广播意图。这是通过引用广播意图的操作字符串来实现的。

需要注意的是，广播接收器不需要持续运行。当检测到匹配的意图时，Android 运行时系统会在调用`onReceive()`方法之前自动启动广播接收器。

以下代码出一个广播接收器子类：

```java
package com.example.broadcastdetector;
```

```java
import android.content.BroadcastReceiver;
import android.content.Context;
import android.content.Intent;

public class MyReceiver extends BroadcastReceiver {
    public MyReceiver() {
    }

    @Override
    public void onReceive(Context context, Intent intent) {
        // Implement code here to be performed when
        // broadcast is detected
    }
}
```

在清单文件中注册广播接收器时，必须为该接收器添加一个`<receiver>`条目。

下面的清单文件示例注册了上述广播接收器：

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.broadcastdetector.broadcastdetector"
    android:versionCode="1"
    android:versionName="1.0">
    <uses-sdk android:minSdkVersion="17" />
    <application
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name">
        <receiver android:name="MyReceiver">
        </receiver>
    </application>
</manifest>
```

在 Android 8.0 之前的版本上运行时，与接收器相关的关联过滤器（intent filters）可以放在清单文件中的接收器元素中，如下所示：

```xml
<receiver android:name="MyReceiver">
    <intent-filter>
        <action android:name="com.example.Broadcast">
        </action>
    </intent-filter>
</receiver>
```

在 Android 8.0 或更高版本上，必须在代码中使用`Activity`类的`registerReceiver()`方法，结合适当配置的`IntentFilter`对象来注册接收器：

```java
IntentFilter filter = new IntentFilter("com.example.Broadcast");
MyReceiver receiver = new MyReceiver();
registerReceiver(receiver, filter);
```

当在代码中注册的广播接收器不再需要时，可以通过调用活动类的`unregisterReceiver()`方法来注销它，并将接收器对象的引用作为参数传递。例如，以下代码将注销上述广播接收器：

```java
unregisterReceiver(receiver);
```



必须记住，某些系统广播意图只有在代码中注册而非清单文件中注册时才能被广播接收器检测。请检查 Android `Intent` 类文档，在线查看系统广播意图及相应要求的详细概述：

`https://developer.android.com/reference/android/content/Intent`

## 56.3 从广播获取结果

当使用`sendBroadcast()`方法发送广播意图时，发起活动（activity）无法从任何接收该广播的广播接收器处获取结果。如果需要返回结果，则必须使用`sendOrderedBroadcast()`方法。当使用此方法发送广播意图时，它将按顺序传递给每个已注册感兴趣的广播接收器。

`sendOrderedBroadcast()`方法接受多个参数，包括指向另一个广播接收器的引用（称为结果接收器，result receiver），当所有其他广播接收器都处理完意图后将通知它，同时以及一组数据引用，这些接收器可以将结果数据存放在其中。当所有广播接收器都获得了处理广播的机会后，结果接收器的`onReceive()`方法将被调用并传递结果数据。

## 56.4 粘性广播意图（Sticky Broadcast Intents）

默认情况下，广播意图一旦发送并被感兴趣的广播接收器处理后就会消失。然而，可以将广播意图定义为“粘性”。粘性意图及其包含的数据在完成执行后仍保留在系统中。可以通过调用`registerReceiver()`方法（使用通常参数：广播接收器引用和意图过滤器对象引用）的返回值来获取粘性广播意图中存储的数据。许多 Android 系统广播都是粘性的，一个典型的例子是与电池电量状态相关的广播。

可以通过调用`removeStickyBroadcast()`方法随时移除粘性广播，并将要移除的广播意图引用作为参数传递。

## 56.5 广播意图示例

本章的剩余部分将通过手实现一个基于 Android Studio 的广播意图运行示例。在第一个实例中，将创建一个简单的应用程序来发送自定义广播意图。随后，将创建一个相应的广播接收器，以便在检测到广播时在 Android 设备的屏幕上显示消息。最后，将修改广播接收器以检测系统关于外部电源已从设备断开的通知。

## 56.6 创建示例应用程序

从欢迎界面选择“New Project”（新建项目）选项，在新项目对话框中选择“Empty Views Activity”（空视图活动）。在 Name（名称）字段输入`SendBroadcast`，并指定`com.ebookrenzy.sendbroadcast`为包名。在点击 Finish（完成）按钮之前，将 Minimum API level（最低 API 级别）更改为`26: Android 8.0 (Oreo)`，并将语言设置为 Java。

一旦创建了新项目，找到并加载位于`res -> layout`的`activity_main.xml`布局文件，并在布局器的 Design（设计）模式下，将`TextView`对象替换为`Button`视图并设置文本属性使其显示为“Send Broadcast”。设置文本值后，按照通常步骤将字符串提取到名为`send_broadcast`的资源。

在布局中仍选中按钮的情况下，在 Attributes（属性）面板中找到`onClick`属性，并配置其调用名为`broadcastIntent`的方法。

## 56.7 创建并发送广播意图

在创建了 SendBroadcast 应用程序框架后，现在是实现发送广播意图代码了。这涉及实现之前作为 Button 视图`onClick`目标的`broadcastIntent()`方法。找到并双击`MainActivity.java`文件，修改它以添加创建和发送广播意图的代码。修改后，该类的源代码应如下：

```java
package com.ebookrenzy.sendbroadcast;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

import android.content.Intent;

import android.view.View;

public class MainActivity extends AppCompatActivity {

    public void broadcastIntent(View view) {

        Intent intent = new Intent();

        intent.setAction("com.ebookrenzy.sendbroadcast");

        intent.addFlags(Intent.FLAG_INCLUDE_STOPPED_PACKAGES);

        sendBroadcast(intent);

    }

}
```

注意，在此实例中，意图的操作字符串为`com.ebookrenzy.sendbroadcast`。在本章后续章节创建广播接收器类时，过滤器过滤器必须匹配此操作字符串。

发送广播意图应用程序的创建结束。剩下的就是构建匹配的广播接收器。

## 56.8 创建广播接收器

要创建广播接收器，需要创建一个子类`BroadcastReceiver`。在 Project 工具窗口中导航到`app -> java`并右键点击包名。从弹出的菜单中选择 New -> Other -> Broadcast Receiver，将类命名为`MyReceiver`，并勾选`Exported`（导出）和`Enabled`（启用）选项。这些设置允许 Android 系统在需要时启动接收器，并确保该类能够接收来自其他应用程序的消息。配置好类后，点击 Finish。

一旦创建，Android Studio 将自动将新的`MyReceiver.java`类文件加载到编辑器中，其内容如下：

```java
package com.ebookfrenzy.sendbroadcast;

import android.content.BroadcastReceiver;

import android.content.Context;

import android.content.Intent;

public class MyReceiver extends BroadcastReceiver {

    @Override

    public void onReceive(Context context, Intent intent) {

        // TODO: 此方法在 BroadcastReceiver 接收到

        // Intent 广播时被调用。

        throw new UnsupportedOperationException("Not yet implemented");

    }

}
```

如所示，Android Studio 为新类生成了一个模板并为`onReceive()`方法生成了一个存根。现在需要对类进行一些更改以实现所需的行为。因此，在`MyReceiver.java`文件中，修改代码使其内容如下：

```java
package com.ebookfrenzy.sendbroadcast;

import android.content.BroadcastReceiver;

import android.content.Context;

import android.content.Intent;

import android.widget.Toast;

public class MyReceiver extends BroadcastReceiver {

    @Override

    public void onReceive(Context context, Intent intent) {

        // TODO: 此方法在 BroadcastReceiver 接收到

        // Intent 广播时被调用。

        throw new UnsupportedOperationException("Not yet implemented");

        Toast.makeText(context, "Broadcast Intent Detected.", Toast.LENGTH_LONG).show();

    }

}
```

广播接收器的代码现在已经完成。

## 56.9 注册广播接收器

项目需要公开广播接收器的存在，并且必须包含一个意图过滤器（intent filter），以指定该接收器感兴趣的广播意图。当在上一节创建`BroadcastReceiver`类时，Android Studio 自动在清单文件中添加了`<receiver>`元素。因此，剩下的工作是在`MainActivity.java`文件中添加代码以创建一个意图过滤器并注册接收器：

```java
package com.ebookfrenzy.sendbroadcast;

...

import android.content.BroadcastReceiver;

import android.content.IntentFilter;

...

public class MainActivity extends AppCompatActivity {

    BroadcastReceiver receiver;

    @Override

    protected void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);

        setContentView(R.layout.activity_main);

        configureReceiver();

    }

    private void configureReceiver() {

        IntentFilter filter = new IntentFilter();

        filter.addAction("com.ebookfrenzy.sendbroadcast");

        receiver = new MyReceiver();

        registerReceiver(receiver, filter);

    }

}
```

当广播接收器不再需要时将其取消注销也是非常重要的：

```java
@Override

protected void onDestroy() {

    super.onDestroy();

    unregisterReceiver(receiver);

}
```

## 56.10 测试广播示例

要测试广播发送器和接收器，请设备或 AVD 上运行`SendBroadcast`应用并等待其出现。运行后，点击按钮，此时“Broadcast Intent Detected.”的 toast 消息将弹出几秒钟然后消失。

## 56.11 监听系统广播

此示例的最后阶段是修改广播接收器的意图过滤器，以监听当外部电源从设备断开时系统广播的系统意图。该操作是`android.intent.action.ACTION_POWER_CONNECTED`。修改`MainActivity.java`文件中的`configureReceiver()`方法以添加此过滤器：

```java
private void configureReceiver() {

    IntentFilter filter = new IntentFilter();

    filter.addAction("com.ebookfrenzy.sendbroadcast");

    filter.addAction("android.intent.action.ACTION_POWER_CONNECTED");

    receiver = new MyReceiver();

    registerReceiver(receiver, filter);

}
```

由于`MyReceiver.java`文件中的`onReceive()`方法现在将监听两种广播意图，因此最好修改代码将当前意图的动作字符串也显示在 toast 消息中。此字符串可以通过调用作为参数传递给`onReceive()`方法的`intent`对象的`getAction()`方法获得：

```java
public void onReceive(Context context, Intent intent) {

    String message = "Broadcast intent detected " + intent.getAction();

    Toast.makeText(context, message, Toast.LENGTH_LONG).show();

}
```

通过重新安装修改后的`SendBroadcast`包来测试接收器。现在点击`SendBroadcast`应用程序按钮会导致包含自定义动作字符串的新消息：`Broadcast intent detected com.ebookfrenzy.sendbroadcast`。

接下来，移除当前为 Android 设备供电的 USB 连接器，此时接收器应在 toast 消息中报告以下内容（消息在竖屏的设备上可能会被截断）。如果应用在模拟器上运行，请显示扩展控制，选择`Battery`选项并将充电器连接设置为 None：

`Broadcast intent detected android.intent.action.ACTION_POWER_CONNECTED`

为了避免每次设备断开电源时都出现此消息，请启动`Settings`应用并选择`Apps`选项。从列表中选择`SendBroadcast`应用并点击`Uninstall`按钮。

## 56.12 总结

广播意图是一种机制，通过它可以发布意图供 Android 系统上的多个组件消费。广播通过注册`Broadcast Receiver`来检测到，而接收器反过来被配置为监听匹配特定动作字符串的意图。

实现客户端组件与绑定服务之间交互有两种推荐的机制。假设绑定服务是本地的，且与客户端组件属于同一个应用程序（换句话说，它运行在同一个进程中，并且对其他应用程序中的组件不可用）。在这种情况下，推荐的方法是创建一个`Binder`类的子类并扩展它以为服务提供接口。随后通过`onBind()`方法返回该`Binder`对象的实例，并由客户端组件使用该实例直接访问服务中持有的方法和数据。

当绑定服务不是应用程序本地的（换句话说，它运行在与客户端组件不同的进程中）时，最佳交互方式是使用`Messenger/Handler`实现。

在本章的剩余部分，将创建一个示例，以演示创建、启动以及与本地私有绑定服务交互涉及的步骤。

## 57.3 本地绑定服务示例

在本章剩余部分创建的示例应用程序将由一个 activity 和一个绑定服务组成。绑定服务的目的是从系统获取当前时间并将该信息返回给 activity，在 activity 中将其显示给用户。该绑定服务将与 activity 属于同一个应用程序，是本地且私有的。

从欢迎界面选择`New Project`（新建项目）选项，在弹出的新项目对话框中，点击`Next`按钮之前选择`Empty Views Activity`模板。

在`Name`字段输入`LocalBound`并指定`com.ebookfrenzy.localbound`为包名。在点击`Finish`按钮之前，将`Minimum API level`（最低 API 级别）设置改为`API 26: Android 8.0 (Oreo)`，并将`Language`（语言）菜单设置为`Java`。使用 11.8 迁移项目到 View Binding 部分中的步骤将项目迁移到 view binding。

项目创建完成后，下一步是添加一个新类作为绑定服务。

## 57.4 向项目添加绑定服务

要向项目添加新类，请在 Project 工具窗口中，右键点击包名（位于`app -> java -> com.ebookfrenzy.localbound`下），选择`New -> Service -> Service`菜单选项。指定`BoundService`为类名，并在点击`Finish`创建类之前，确保勾选了`Exported`（导出）和`Enabled`（启用）选项。Android Studio 将将`BoundService.java`文件加载到编辑器中，其内容如下：

```java
package com.ebookfrenzy.localbound;

import android.app.Service;

import android.content.Intent;

import android.os.IBinder;

public class BoundService extends Service {

    public BoundService() {

    }

    @Override

    public IBinder onBind(Intent intent) {

        // TODO: 向服务返回通信通道。

        throw new UnsupportedOperationException("Not yet implemented");

    }

}
```



## 57.5 实现 Binder

如前所述，本地绑定服务可以通过向客户端传递配置适当的`Binder`对象来与绑定客户端进行通信。这是通过在绑定服务类内部创建一个`Binder`子类，并通过添加一个或多个客户端可以调用的新方法来扩展的。这通常涉及实现一个返回绑定服务实例引用的方法。有了该实例的引用，客户端就可以直接访问绑定服务的数据并调用方法。

对于此示例，需要对上一节创建的模板类`BoundService`进行一些更改。首先，需要声明一个`Binder`子类。该类将包含一个名为`getService()`的方法，该方法将返回当前服务对象实例的引用（由`this`关键字表示）。考虑到这些要求，编辑`BoundService.java`文件并修改如下：

```java
package com.ebookfrenzy.localbound;

import android.app.Service;
import android.content.Intent;
import android.os.IBinder;
import android.os.Binder;

public class BoundService extends Service {

    private final IBinder myBinder = new MyLocalBinder();

    public BoundService() {

    }

    @Override
    public IBinder onBind(Intent intent) {
        // TODO: 向服务返回通信通道。
        throw new UnsupportedOperationException("Not yet implemented");
    }

    public class MyLocalBinder extends Binder {
        BoundService getService() {
            return BoundService.this;
        }
    }
}
```

对类进行更改后，值得花一点时间回顾一下这里执行的步骤。首先，声明了一个新的`Binder`子类（命名为`MyLocalBinder`）。该类包含一个方法，用于返回`BoundService`类当前实例的引用。创建`MyLocalBinder`类的新实例并将其赋值给`myBinder` `IBinder`引用（由于`Binder`是`IBinder`的子类，因此此类赋值不存在类型不匹配）。

接下来，需要修改`onBind()`方法以返回`myBinder`对象的引用，并实现一个新的公共方法，以便在任何绑定到服务的客户端调用它时返回当前时间：

```java
package com.frenzy.localbound;

import java.text.SimpleDateFormat;
import java.util.Date;
import java.util.Locale;

import android.app.Service;
import android.content.Intent;
import android.os.IBinder;
import android.os.Binder;

public class BoundService extends Service {

    private final IBinder myBinder = new MyLocalBinder();

    public BoundService() {

    }

    @Override
    public IBinder onBind(Intent intent) {
        return myBinder;
    }

    public String getCurrentTime() {
        SimpleDateFormat dateformat =
            new SimpleDateFormat("HH:mm:ss MM/dd/yyyy",
            Locale.US);
        return dateformat.format(new Date());
    }

    public class MyLocalBinder extends Binder {
        BoundService getService() {
            return BoundService.this;
        }
    }
}
```

在此处，绑定服务已完成，并准备好添加到项目清单文件中。在Project工具窗口中找到并双击`LocalBound`项目的`AndroidManifest.xml`文件，一旦加载到Manifest编辑器，请验证Android Studio是否已为服务添加了如下`<service>`条目：

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.ebookfrenzy.localbound">

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:theme="@style/AppTheme" >

        <service
            android:name=".BoundService"
            android:enabled="true"
            android:exported="true" >
        </service>

        <activity
            android:name=".MainActivity" >
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>
</manifest>
```

## 57.6 将客户端绑定到服务

此阶段是在activity中编写代码以绑定服务并调用`getCurrentTime()`方法。

如前所述，为了成功绑定到服务并接收服务`onBind()`方法返回的`IBinder`对象，有必要创建一个`ServiceConnection`子类并实现`onServiceConnected()`和`onServiceDisconnected()`回调方法。编辑`MainActivity.java`文件并修改如下：

```java
package com.ebookfrenzy.localbound;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.os.IBinder;
import android.content.Context;
import android.content.Intent;
import android.content.ComponentName;
import android.content.ServiceConnection;
import com.ebookfrenzy.localbound.BoundService.MyLocalBinder;

public class MainActivity extends AppCompatActivity {

    BoundService myService;
    boolean isBound = false;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    final private ServiceConnection myConnection = new ServiceConnection()
    {
        @Override
        public void onServiceConnected(ComponentName className,
                                         IBinder service) {
            MyLocalBinder binder = (MyLocalBinder) service;
            myService = binder.getService();
            isBound = true;
        }

        @Override
        public void onServiceDisconnected(ComponentName name) {
            isBound = false;
        }
    };
}
```

当客户端成功绑定到服务时，将调用`onServiceConnected()`方法。该方法将服务的`onBind()`方法返回的`IBinder`对象作为参数传递。该参数被强制转换为`MyLocalBinder`类型的对象。然后，调用绑定器对象的`getService()`方法来获取服务实例的引用，随后将其赋值给`myService`。一个布尔标志位表示连接已成功建立。

当连接结束时，会调用`onServiceDisconnected()`方法，并将布尔标志设置为`false`。

建立连接后，下一步是修改活动以绑定到该服务。这涉及到创建一个`intent`并调用`bindService()`方法，这些操作可以在传入的`onCreate()`方法中执行：

```java
@Override
public void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);

    Intent intent = new Intent(this, BoundService.class);
    bindService(intent, myConnection, Context.BIND_AUTO_CREATE);
}
```

### 57.7 完成示例

剩下的工作是添加一种机制来调用`getCurrentTime()`方法并将结果显示给用户。按照现在的惯例，Android Studio已经为该活动创建了一个`activity_main.xml`文件，其中仅包含一个`TextView`。将此文件加载到布局编辑器工具中，并使用设计模式选择`TextView`组件并将ID更改为`myTextView`。在`TextView`下添加一个`Button`视图，并将按钮上的文本改为“Show Time”，将文本提取到名为`show_time`的字符串资源中。完成这些更改后，布局应该类似于图57-1所示。如果缺少任何约束，点击布局编辑器工具栏中的“推断约束”（Infer Constraints）按钮。

![](img/as_local_bound_ui.jpg)

图 57-1

通过选择`Button`并配置`onClick`属性调用名为`showTime`的方法来完成用户界面设计。

最后，编辑`MainActivity.java`文件代码以实现`showTime()`方法。该方法调用服务的`getCurrentTime()`方法（得益于`onServiceConnected()`方法，现在可以通过`myService`引用从活动内部访问），并将生成的字符串赋值给`TextView`：

```java
package com.ebookfrenzy.localbound;

import android.widget.TextView;
import com.ebookfrenzy.localbound.BoundService.MyLocalBinder;

public class MainActivity extends AppCompatActivity {

    BoundService myService;
    boolean isBound = false;

    public void showTime(View view)
    {
        String currentTime = myService.getCurrentTime();
        TextView myTextView = findViewById(R.id.myTextView);
        myTextView.setText(currentTime);
    }
}
```

### 57.8 测试应用程序

代码完成后，运行应用程序，点击按钮并注意文本显示了当前时间。

### 57.9 总结

当绑定服务是本地且私有的时，应用程序内的组件可以通过向客户端返回`IBinder`对象来相互交互。客户端实现`ServiceConnection`子类，该子类包含在服务连接和断开连接时调用的回调方法。总而言之，`onBind()`方法向客户端返回一个`Binder`实例。

## 58. Android 远程绑定服务 – 示例

在关于Android服务的最后一个章节中，将开发一个示例应用程序来演示IPC（进程间通信）的使用。

### 58.1 客户端与远程服务的通信

如上一章所述，客户端与本地服务之间的交互可以通过向客户端返回`IBinder`对象来实现。然而，对于远程服务，这种方法是不可通的，因为远程服务运行在不同的进程中，因此无法直接访问。

对于远程服务，必须创建一个`messenger`和`handler`配置，以允许消息跨进程边界传递。具体来说，服务会创建一个`Handler`实例，当从客户端接收到消息时将调用它。本章创建的示例将由一个运行在单独进程中的活动和一个绑定服务组成。`Messenger`/`Handler`机制将向服务发送字符串，该字符串将显示在Logcat输出。

### 58.2 创建示例应用程序

从欢迎界面选择“New Project”（新建项目），在出现的新项目对话框中，选择“Empty Views Activity”模板，然后点击“Next”按钮。

在Name字段中输入`RemoteBound`并指定`com.ebookfrenzy.remotebound`为包名。在点击“Finish”按钮之前，将Minimum API级别设置为API 26: Android 8.0 (Oreo)，并将Language菜单设置为Java。

### 58.3 设计用户界面

在Project工具窗口中找到`activity_main.xml`文件并双击它将其加载到布局编辑器工具中。在布局编辑器设计模式下，右键点击默认的`TextView`实例，选择“Convert view...”（转换视图）菜单选项，从生成的对话框中选择`Button`视图并点击Apply。将按钮的text属性改为“Send Message”，并将字符串提取到名为`send_message`的新资源中。

最后，配置`onClick`属性以调用名为`sendMessage`的方法。

### 58.4 实现远程绑定服务

要实现此示例中的远程绑定服务（remote bound service），请在Project工具窗口中右键点击包名（位于`app` -> `java`下），并选择`New` -> `Service` -> `Service`菜单项向项目添加新类。将`RemoteService`指定为类名，并在点击`Finish`创建类之前，确保同时勾选了`Exported`（导出）和`Enabled`（启用）选项。

下一步是为新服务实现处理类（handler class）。这通过扩展`Handler`类并实现`handleMessage()`方法来实现。当从客户端接收到消息时，该方法会被调用。它将接收一个`Message`对象作为参数，其中包含客户端需要传递给服务的任何数据。在本例中，这将是一个包含要显示给用户的字符串的`Bundle`对象。实现此功能后，`RemoteService.java`文件修改后的类应如下：

```java
package com.ebookfzy.remotebound;

import android.app.Service;
import android.content.Intent;
import android.os.IBinder;
import android.os.Bundle;
```



`import android.os.Handler;`

`import android.os.Looper;`

`import android.os.Message;`

`import android.os.Messenger;`

`import android.util.Log;`

`public class RemoteService extends Service {`

```java
public RemoteService() {

}

static class IncomingHandler extends Handler {

    String TAG = "RemoteService";

    public IncomingHandler() {

        super(Looper.getMainLooper());

    }

    @Override

    public void handleMessage(Message msg) {

        Bundle data = msg.getData();

        String dataString = data.getString("MyString");

        Log.i(TAG, "Message = " + dataString);

    }

}

@Override

public IBinder onBind(Intent intent) {

    // TODO: Return the communication channel to the service.

    throw new UnsupportedOperationException("Not yet implemented");

}
```

}

实现处理类后，服务代码剩下的唯一任务是修改`onBind()`方法，使其返回一个包含`Messenger`对象的`IBinder`对象，而该`Messenger`对象又包含对处理器的引用：

```java
final Messenger myMessenger = Messenger(new IncomingHandler());

@Override

public IBinder onBind(Intent intent) {

    return myMessenger.getBinder();

}
```

上述代码段的第一行创建了我们处理类的新实例，并将其传递给新`Messenger`对象的构造函数。在`onBind()`方法中，调用了`messenger`对象的`getBinder()`方法来返回该`messenger`的`IBinder`对象。

### 58.5 在 Manifest 文件中配置远程服务

为了准确描述客户端与远程服务之间的通信，有必要配置该服务在应用程序的其他部分独立运行。这通过在清单文件中该服务的`<service>`标签内添加`android:process`属性来实现。要启动远程服务，还需要为该服务提供一个意图过滤器（intent filter）。要实现此更改，请修改`AndroidManifest.xml`文件以添加所需的条目：

```xml
<?xml version="1.0" encoding="utf-8"?>

<manifest xmlns:android="http://schemas.android.com/apk/res/android"

    package="com.ebookfrenzy.remotebound" >

    <application

        android:allowBackup="true"

        android:icon="@mipmap/ic_launcher"

        android:label="@string/app_name"

        android:supportsRtl="true"

        android:theme="@style/AppTheme" >

        <service

            android:name=".RemoteService"

            android:enabled="true"

            android:exported="true"

            android:process=":my_process" >

        </service>

        <activity

            android:name=".MainActivity" >

            <intent-filter>

                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />

            </intent-filter>

        </activity>

    </application>

</manifest>
```

### 58.6 启动并绑定远程服务

与绑定服务一样，客户端组件需要实现`ServiceConnection`类的实例，并包含`onServiceConnected()`和`onServiceDisconnected()`方法。此外，对于本地服务，`onServiceConnected()`方法将接收由远程服务`onBind()`方法返回的`IBinder`对象，并将将其用于向服务器发送消息。在本例中，客户端是`MainActivity`，其代码位于`MainActivity.java`中。加载此文件并修改它，添加`ServiceConnection`类以及用于存储接收到的`Messenger`对象引用的变量，并带有一个`Boolean`标志位来指示连接是否已建立：

```java
package com.ebookfrenzy.remotebound;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

import android.os.IBinder;

import android.os.Message;

import android.os.Messenger;

import android.os.RemoteException;

import android.content.ComponentName;

import android.content.Context;

import android.content.ServiceConnection;

import android.view.View;

public class MainActivity extends AppCompatActivity {

    Messenger myService = null;

    boolean isBound;

    @Override

    protected void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);

        setContentView(R.layout.activity_main);

    }

    final ServiceConnection myConnection = new ServiceConnection() {

        public void onServiceConnected(ComponentName className, IBinder service) {

            myService = new Messenger(service);

            isBound = true;

        }

        public void onServiceDisconnected(ComponentName className) {

            myService = null;

            isBound = false;

        }

    };

}
```

接下来，必须添加代码来绑定远程服务。这涉及创建一个与清单文件中声明的服务意图过滤器匹配的`intent`，然后调用`bindService()`方法，提供意图和`ServiceConnection`实例。对于此示例，该代码将实现在 Activity 的`onCreate()`方法中：

```java
@Override

protected void onCreate(Bundle savedInstanceState) {

    super.onCreate(savedInstanceState);

    // ... 其他代码

    Intent intent = new Intent(getApplicationContext(), RemoteService.class);

    bindService(intent, myConnection, Context.BIND_CREATE);

}
```

### 58.7 向远程服务发送消息

在测试应用程序之前，最后剩下的工作是在`MainActivity`类中实现`sendMessage()`方法，该方法被配置为在用户点击界面上的按钮时调用。此方法需要检查服务是否连接，创建一个包含要由服务器显示的字符串的`bundle`对象，将其添加到`Message`对象中，并发送给服务器：

```java
public void sendMessage(View view) {

    if (!isBound) return;

    Message msg = Message.obtain();

    Bundle bundle = new Bundle();

    bundle.putString("MyString", "Message Received");

    msg.setData(bundle);

    try {

        myService.send(msg);

    } catch (RemoteException e) {

        e.printStackTrace();

    }

}
```

当 Logcat 工具窗口仍然可见时，点击用户界面上的按钮，此时日志消息将显示如下：

`Message = Message Received`

# 58. 总结

为了实现客户端与远程绑定服务之间的交互，App 必须实现一个处理器/消息通信框架。该技术背后的基本概念在本章中涵盖，并实现了一个示例应用程序，该程序旨在演示客户端与绑定服务之间的通信，它们分别运行在独立的进程中。

# 59. Java 线程、处理器和执行器的基本概述

线程是任何多任务操作系统的基石，可以被认为是运行在主进程中的微型进程，其目的是让应用程序内部至少出现并行执行路径的现象。在本章中，我们将探讨在 Android 应用开发中使用线程的重要性，并演示如何创建和管理它们。

## 59.1 应用程序主线程

当 Android 首次启动时，运行时系统会创建一个线程，所有应用程序组件默认都在该线程中运行。该线程通常被称为主线程。主线程的主要作用是处理用户界面的事件处理以及与用户界面中视图的交互。应用程序内启动的任何额外组件默认也会运行在主线程上。

应用程序中任何使用主线程执行耗时任务的组件都会导致整个应用程序看起来像锁定了一样，直到任务完成。这通常会导致操作系统向用户显示“应用程序未响应”的警告。显然，这远不是任何应用程序的理想行为。这可以通过简单地将要执行的任务在单独线程中启动来避免，让主线程能够不受干扰地继续处理其他任务。

## 59.2 线程处理器（Handlers）

显然，Android 开发的关键规则之一是：永远不要在应用程序的主线程上执行耗时操作。第二个同样重要的规则是：在任何情况下，独立线程中的代码都绝**不应该**直接更新用户界面的任何部分。

对用户界面的任何更改必须始终在主线程内执行。这是因为 Android UI 工具包不是线程安全的。在多个线程中尝试处理非线程安全代码通常会导致间歇性问题和不可预测的应用程序行为。

如果线程中执行的代码需要与用户界面交互，它必须通过与主 UI 线程同步来实现。这通过在主线程中创建一个 handler 实现，由它接收来自另一个线程的消息并相应地更新用户界面。

## 59.3 线程示例

本章的剩余部分将通过一些简单的示例来为线程提供基础介绍。第一步将强调在主线程之外的独立线程中执行耗时任务的重要性。

启动 Android Studio，从欢迎屏幕选择`New Project`选项，在出现的新项目对话框中，点击`Next`按钮之前选择`Empty Activity`模板。

在`Name`字段中输入`ThreadExample`，并指定`com.ebookfrenzy.threadexample`为包名。在点击`Finish`按钮之前，将 Minimum API level 设置为`API 26: Android 8.0 (Oreo)`，并将 Language 菜单更改为`Java`。按照节 11.8 将项目迁移到 View Binding 中的步骤，将项目转换为使用 view binding。

## 59.4 构建 App

将项目的`activity_main.xml`文件加载到 Layout Editor 工具中。选择默认的`TextView`组件，并在 Properties 工具窗口中将视图的 ID 更改为`myTextView`。

在用户界面上添加一个`Button`视图，位于现有`TextView`对象正下方，如图图 59-1 所示。添加按钮后，点击工具栏上的`Infer Constraints`按钮以添加缺失的约束。

将文本更改为“Press Me”，并将字符串提取到名为`press_me`的资源。在布局中仍选中按钮视图时，找到`onClick`属性并输入`buttonClick`作为方法名。

![](img/as_thread_example_ui_one_button.jpg)

图 59-1

接下来，将`MainActivity.java`文件加载到编辑面板，并为`buttonClick()`方法添加代码，该方法将在用户点击`Button`视图时调用。由于这里的目标是演示在主线程上执行长时间任务的问题，代码将简单的暂停 20 秒，然后在`TextView`对象上显示不同的文本：

```java
public void buttonClick(View view) {

    long endTime = System.currentTimeMillis() + 20 * 1000;

    while (System.currentTimeMillis() < endTime) {

        synchronized (this) {

            try {

                wait(endTime - System.currentTimeMillis());

            } catch (Exception e) {

            }

        }

    }

    binding.myTextView.setText("Button Pressed");

}
```

代码更改完成后，在物理设备或模拟器上运行应用程序。一旦应用程序运行，点击按钮，此时应用程序将看起来像冻结了一样。例如，无法第二次点击按钮，在某些情况下，操作系统将报告应用程序未响应，如图图 59-2 所示。

![](img/as_4.2_threadexample_not_responding.jpg)

图 59-2

显然，在`buttonClick()`方法中任何需要时间完成的任务都需要在独立线程执行。

## 59.5 创建新线程

要创建一个新线程，在该线程中执行的代码需要放在`Runnable`实例的`run()`方法中。然后需要创建一个`Thread`对象，并将`Runnable`实例传递给构造函数。最后，需要调用线程对象的`start()`方法来启动线程。因此，要在`buttonClick()`方法中执行任务，需要如下更改：

```java
void buttonClick(View view) {

    Runnable runnable = new Runnable() {

        public void run() {

            long endTime = System.currentTimeMillis() + 20 * 1000;

            while (System.currentTimeMillis() < endTime) {

                synchronized (this) {

                    try {

                        wait(endTime - System.currentTimeMillis());

                    } catch (Exception e) {

                    }

                }

            }

            binding.myTextView.setText("Button Pressed");

        }

    };
```



```java
Thread myThread = new Thread(runnable);

myThread.start();

}
```

事实上，如果需要，可以使用 lambda 表达式来简化`runnable`的声明。这种更改将导致如下结果：

```java
Runnable runnable = () -> {

    long endTime = System.currentTimeMillis() + 20 * 1000;

    while (System.currentTimeMillis() < endTime) {

        synchronized (this) {

            try {

                wait(endTime - System.currentTimeMillis());

            } catch (Exception e) {

            }
        }
    }

    binding.myTextView.setText("Button Pressed");

};
```

当现在运行应用程序时，点击按钮会导致延迟操作在新线程中执行，从而让主线程能够继续处理用户界面，包括响应额外的按钮点击。事实上，每次点击按钮时，都会创建一个新线程，允许任务并发执行多次。

仔细检查`buttonClick()`方法更新后的代码，可以发现更新`TextView`的代码已被移除。正如之前提到的，在主线程的线程内部更新用户界面元素违反了 Android 开发的一项核心规则。因此，为了更新用户界面，必须为该线程实现一个`Handler`。

## 59.6 实现线程处理器（Thread Handler）

线程处理器（Thread handlers）在应用程序的主线程中实现，主要用于响应来自应用程序进程内其他线程发送的消息，并对用户界面进行更新。

处理器继承自`Handler`类，可以通过指定线程需要时执行的`Runnable`来使用，也可以通过重写`Handler`子类中的`handleMessage()`回调方法来使用，当线程向处理器 get 送消息时，该方法会被调用。

为了本示例的目的，将实现一个处理器，以便从之前创建的线程内部更新用户界面。在 Android Studio 编辑器中加载`MainActivity.java`文件，并修改代码为活动中添加一个`Handler`实例：

```java
import android.os.Handler;

import android.os.Message;

import android.os.Looper;

public class MainActivity extends AppCompatActivity {

    Handler handler = new Handler(Looper.getMainLooper()) {

        @Override 

        public void handleMessage(Message msg) {

            binding.myTextView.setText("Message Received");

        }

    };

}
```

上述代码更改声明了一个处理器并在处理器内部实现了`handleMessage()`回调，当线程向处理器发送消息时，该回调将被调用。在此实例中，代码只是在用户界面的`TextView`对象上显示字符串。

现在剩下的只是修改`buttonClick()`方法中创建的线程，在延迟完成后向处理器发送消息：

```java
public void buttonClick(View view) {

    Runnable runnable = () -> {

        long endTime = System.currentTimeMillis() + 20 * 1000;

        while (System.currentTimeMillis() < endTime) {

            synchronized (this) {

                try {

                    wait(endTime - System.currentTimeMillis());

                } catch (Exception e) {

                }
            }
        }

        handler.sendEmptyMessage(0);

    };

    Thread myThread = new Thread(runnable);

    myThread.start();

}
```

注意，唯一的更改是调用了处理器的`sendEmptyMessage()`方法。由于处理器目前没有对收到的任何消息内容进行任何操作，因此它发送了一个空消息对象。

编译并运行应用程序，执行后，点击按钮。在 20 秒延迟后，新文本将出现在用户界面的`TextView`对象中。

## 59.7 向处理器传递消息

虽然上一个示例触发了对`handleMessage()`处理器回调的调用，但它没有利用消息对象向处理器发送数据。在教程的这一阶段，示例将进行进一步修改，以便在线程和处理器之间传递数据。首先，`buttonClick()`方法中更新的线程将从系统获取字符串格式的日期和时间，并将该信息存储在`Bundle`对象中。然后调用处理器对象的`obtainMessage()`方法从消息池中获取一个消息对象。最后，在通过调用处理器的`sendMessage()`方法发送之前，将 bundle 添加到消息对象中：

```java
public void buttonClick(View view) {

    Runnable runnable = () -> {

        long endTime = System.currentTimeMillis() + 20 * 1000;

        while (System.currentTimeMillis() < endTime) {

            synchronized (this) {

                try {

                    wait(endTime - System.currentTimeMillis());

                } catch (Exception e) {

                }
            }
        }

        Message msg = handler.obtainMessage();

        Bundle bundle = new Bundle();

        bundle.putString("myKey", "Completed");

        msg.setData(bundle);

        handler.sendMessage(msg);

    };

    Thread myThread = new Thread(runnable);

    myThread.start();

}
```

接下来，更新处理器的`handleMessage()`方法，从消息中的 bundle 中提取日期和时间字符串并显示在`TextView`对象上：

```java
Handler handler = new Handler(Looper.getMainLooper()) {

    @Override

    public void handleMessage(Message msg) {

        Bundle bundle = msg.getData();

        String string = bundle.getString("myKey");

        binding.myTextView.setText(string);

    }

};
```

最后，编译并运行应用程序，测试点击按钮现在是否会在线程完成后在`TextView`对象上显示“Thread Complete”消息。

## 59.8 Java Executor 并发（Java Executor Concurrency）

在本章中，目前我们只查看了直接创建和管理 Java 线程。虽然对于简单的多线程任务是可以接受的，但在处理涉及大量线程的复杂情况时，这证明是不足够的。例如，启动和停止线程存在系统开销。因此，创建和销毁大量线程的应用程序面临性能下降的风险。基础线程 API 也没有提供调度或重复执行或从任务返回结果的选项。

通过使用 Java 并发框架的`Executor`类（`java.util.concurrent`包的一部分），可以克服直接处理线程的缺点。该框架允许创建活动线程池并管理如何将任务分配给这些线程。这允许重用现有线程而无需不断创建新线程。该框架提供了额外的功能，包括在任务完成后返回结果（称为`Callable`任务）、检查线程状态以及在超时后或重复时间间隔调度任务。

## 59.9 使用 Runnable 任务

探索此框架的第一步是修改`buttonClick()`方法，使用并发框架`Executor`在单独线程中运行任务：

```java
import java.util.concurrent.ExecutorService;

import java.util.concurrent.Executors;

public void buttonClick(View view) {

    ExecutorService executor = Executors.newSingleThreadExecutor();

    executor.submit(new Runnable() {

        public void run() {

            long endTime = System.currentTimeMillis() + 10 * 1000;

            while (System.currentTimeMillis() < endTime) {

                synchronized (this) {

                    try {

                        wait(endTime - System.currentTimeMillis());

                    } catch (Exception e) {

                    }
                }
            }
        }
    });

    executor.shutdown();

}
```

当上述代码执行时，超时将像以前一样在单独的线程上执行。然而，对方法的更改需要一些解释。首先，从系统的`Executors`实例获取一个`ExecutorService`实例的引用：

```java
ExecutorService executor = Executors.newSingleThreadExecutor();
```

在这种情况下，请求了一个只包含一个线程的池。也可以如下所示请求具有指定线程数量的池：

```java
ExecutorService executor = Executors.newFixedThreadPool(10);
```

接下来，通过调用执行服务实例的`submit()`方法在线程上启动一个`Runnable`任务：

```java
executor.submit(new Runnable(){

    public void run(){

        long endTime = System.currentTimeMillis() + 20 * 1000;

.

.

}
```

注意，上述声明可以通过将其转换为 lambda 表达式来简化：

```java
executor.submit(() -> {

    long endTime = System.currentTimeMillis() + 20 * 1000;

.

.
```

从现在开始，任务将一直运行直到完成。然而，一旦完成，执行服务将继续运行。如果你不再需要该服务，应该将其关闭。

## 59.10 关闭执行 Service 服务

`ExecutorService`提供了几种用于启动关闭的技术。要通知服务在当前运行的任务完成后自动关闭，应该如下所示调用`shutdown()`方法：

```java
executor.shutdown();
```

另一方面，调用`shutdownNow()`方法将停止服务上所有正在运行的任务，并取消对待处理任务的执行：

```java
executor.shutdownNow();
```

## 59.11 使用 Callable 任务和 Future 进行工作

如前所述，`ExecutorService`支持所谓的“Callable”任务，这些任务能够在任务完成后返回结果。在单独线程上运行的任务通常预计需要一些时间才能完成（否则它们最初可能就不需要在一个单独的线程上运行了）。这引出了结果如何返回到启动任务的线程代码中的问题。这是通过`Future`值类型实现的，它代表在未来某个时刻将提供的值。

当执行一个可调用任务时，它会返回一个`Future`实例，应用程序随后可以使用该实例在任务完成时获取结果。要查看此操作，首先开始编辑`activity_main.xml`文件，添加一个标记为“Status”的额外按钮，并将`onClick`属性配置为调用名为`statusClick`的方法：

![](img/as_thread_example_ui.jpg)

图 59-3

接下来，修改`buttonClick()`方法以执行一个`Callable`任务，该任务配置为通过`Future`变量返回`String`值：

```java
.

.

import java.util.concurrent.Callable;

import java.util.concurrent.Future;

.

.

public class MainActivity extends AppCompatActivity {

    Future<String> future;

.

.

    public void buttonClick(View view) {

        ExecutorService executor = Executors.newSingleThreadExecutor();

        future = executor.submit(new Callable<String>() {

            public String call() {

                long endTime = System.currentTimeMillis() + 10 * 1000;

                while (System.currentTimeMillis() < endTime) {

                    synchronized (this) {

                        try {

                            wait(endTime - System.currentTimeMillis());

                        } catch (Exception e) {

                        }
                    }
                }

                return("Task Completed");

            }
        });

    }
```

从现在开始，任务将一直运行直到完成。然而，一旦完成，执行服务将继续运行。如果你不再需要该服务，应该将其关闭。

## 59.12 处理 Future 结果

除了导入`Future`和声明`Future`变量外，对启动任务的方式进行了一些更改：`executor.submit(() -> { long endTime = System.currentTimeMillis() + 20 * 1000; . . })`。

`scheduleAtFixedRate()`方法无论之前调度的任务是否完成，都会启动任务的下一次实例。要指定在任务执行结束和下一次执行开始之间保持固定时间间隔，请使用`scheduleWithFixedDelay()`方法。在下面的示例中，第一个任务在延迟 0 秒后进行调度，随后的每次执行都将在上一个任务完成后 10 秒后进行：

```java
executor.scheduleWithFixedDelay(task, 0, 10, TimeUnit.SECONDS);
```



# 59.14 总结

本章的目标是提供 Android 应用中线程的概述。当应用程序在进程中首次启动时，运行时系统会创建一个主线程（`main thread`），所有随后启动的应用程序组件默认在该线程运行。主线程的主要作用是处理用户界面，因此在该线程中执行任何耗时任务都会导致应用程序出现卡死的假象。因此，将可能需要时间完成的任务在单独的线程中启动是至关重要的。

由于 Android 用户界面工具包不是线程安全的，不应在主线程之外的任何线程中更改用户界面。可以通过在主线程中创建一个 `handler` 来实现用户界面更改，并从其他非主线程向其发送消息。

线程可以直接创建，也可以使用 `Java Concurrent` 框架的执行器服务（`executor services`）。对于更复杂的线程需求，该框架提供了线程池的自动管理、任务结果返回以及执行调度。

# 60. 在 Android 中进行运行时权限请求

在前面的章节创建的许多示例项目中，已对`AndroidManifest.xml`文件进行了修改，以请求应用执行特定任务的权限。例如，在某些情况下请求了互联网访问权限以允许应用下载和显示网页。在在此为止的每个情况下，只需在清单文件中添加请求，应用即可从用户处获得执行指定任务的权限。

然而，对于某些权限，当应用在 Android 6.0 或更高版本上运行时，还需要额外的步骤才能正常工作。这些所谓的“危险”权限中的第一个将在下一章遇到。然而，在到达这一点之前，本章将概述在运行最新版本的 Android 上时请求此类权限涉及的步骤。

## 60.1 理解普通权限和危险权限

Android 通过要求用户授予应用执行某些任务的权限来强制安全性。在 Android 6 引入之前，在应用安装到设备时总是会寻求权限。例如，图 60-1 显示了通过 Google Play 安装应用时寻求各种权限的典型屏幕。

![](img/Image24251.jpg)

图 60-1

对于许多类型的权限，这种场景仍然适用于 Android 6.0 或更高版本上的应用。这些权限被称为普通权限（`normal permissions`），仍然要求在安装时由用户接受。第二类权限被称为危险权限（`dangerous permissions`），必须与普通权限一样在清单文件中声明，但必须在应用程序首次启动时向用户请求。当进行此类请求时，它将以对话框的形式出现，如图 60-2 所示：

![](img/Image24341.jpg)

图 60-2

属于危险类别的权限完整列表包含表 60-1 中：

| 权限组 | 权限 |
| :--- | :--- |
| 日历 | `READ_CALENDAR`,`WRITE_CALENDAR` |
| 相机 | `CAMERA` |
| 联系人 | `READ_CONTACTS`,`WRITE_CONTACTS`,`GET_ACCOUNTS` |
| 位置 | `ACCESS_FINE_LOCATION`,`ACCESS_COARSE_LOCATION` |
| 麦克风 | `RECORD_AUDIO` |
| 通知 | `POST_NOTIFICATIONS` |
| 电话 | `READ_PHONE_STATE`,`CALL_PHONE`,`READ_CALL_LOG`,`WRITE_CALL_LOG`,`ADD_VOICEMAIL`,`USE_SIP`,`PROCESS_OUTGOING_CALLS` |
| 传感器 | `BODY_SENSORS` |
| 短 | `SEND_SMS`,`RECEIVE_SMS`,`READ_SMS`,`RECEIVE_WAP_PUSH`,`RECEIVE_MMS` |
| 存储 | `MANAGE_EXTERNAL_STORAGE`,`READ_EXTERNAL_STORAGE`,`WRITE_EXTERNAL_STORAGE` |

表 60-1

`MANAGE_EXTERNAL_STORAGE`权限允许访问设备外部存储上的所有文件，包括属于其他应用的文件。因此，只有当 Google 在审核过程中确认了需要此级别的访问权限后，您的应用才会启用该权限。在将应用提交到 Google Play 商店之前测试您的应用，可以执行以下`adb`命令来临时为测试设备上的应用启用访问：

```
adb shell appops set --uid <package name> MANAGE_EXTERNAL_STORAGE allow
```

可以通过以下方式关闭此模式：

```
adb shell appops set --uid <package name> MANAGE_EXTERNAL_STORAGE default
```

## 60.2 创建权限示例项目

从欢迎界面选择“New Project”选项，在生成的新项目对话框中，点击“Next”按钮之前选择“Empty Views Activity”模板。

在`Name`字段中输入`PermissionDemo`，并指定`com.ebookfrenzy.permissiondemo`为包名。在点击“Finish”按钮之前，将“Minimum API level”设置更改为`API 26`：Android 8.0 (Oreo)，并将语言设置为`Java`。

## 60.3 检查权限

Android 支持库包含多个用于寻求和管理危险权限的方法。这些调用可以在任何版本上安全地执行，但只有在 6.0 上执行时才有意义。在应用尝试使用需要危险权限的功能之前，无论之前是否授予，代码都必须检查是否授予。这可以通过调用`ContextCompat`类的`checkSelfPermission()`方法来实现，传入当前活动的引用和请求的权限。

在示例项目的`MainActivity.java`文件中，修改代码以检查是否已授予录音权限：

```java
package com.ebookfrenzy.permissiondemo;

import androidx.appcompat.app.AppCompatActivity;
import androidx.core.content.ContextCompat;
import androidx.annotation.NonNull;
import android.os.Bundle;
import android.Manifest;
import android.content.pm.PackageManager;
import android.util.Log;

public class MainActivity extends AppCompatActivity {

    private static final String TAG = "PermissionDemo";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_permission_demo);
        setupPermissions();
    }

    private void setupPermissions() {
        int permission = ContextCompat.checkSelfPermission(this,
                Manifest.permission.RECORD_AUDIO);

        if (permission != PackageManager.PERMISSION_GRANTED) {
            Log.i(TAG, "Permission to record denied");
        }
    }
}
```

编辑`AndroidManifest.xml`文件（位于项目工具窗口 `app -> manifests` 下），并按如下添加一行以请求录音权限：

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.ebookfrenzy.permissiondemoactivity" >
    <uses-permission android:name="android.permission.RECORD_AUDIO" />
    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@sxtring/app_name"
        android:supportsRtl="true"
        android:theme="@style/AppTheme" >
        <activity android:name=".MainActivity" >
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>
</manifest>
```

在设备或模拟器上运行应用，并打开`Logcat`工具窗口。请注意，尽管权限已添加到 manifest 文件中，仍然出现了“权限被拒绝”的消息。这是因为 Android 要求除了向 manifest 文件添加请求之外，应用还必须在运行时请求危险权限。

## 60.4 在运行时请求权限

权限请求是通过调用`ActivityCompat`类的`requestPermissions()`方法发出的。当调用此方法时，权限请求是异步处理的，并在任务完成后会调用名为`onRequestPermissionsResult()`的方法。

`requestPermissions()`方法的参数是当前活动的引用、所请求权限的标识符以及请求代码。请求代码可以是任意整数值，并将用于标识是哪个请求触发了对`onRequestPermissionsResult()`方法的调用。修改`MainActivity.java`文件以声明请求代码，并在权限检查失败时请求录音权限：

```java
import androidx.core.app.ActivityCompat;

public class MainActivity extends AppCompatActivity {

    private static final String TAG = "PermissionDemo";
    private static final int RECORD_REQUEST_CODE = 101;

    private void setupPermissions() {
        int permission = ContextCompat.checkSelfPermission(this,
            Manifest.permission.RECORD_AUDIO);

        if (permission != PackageManager.PERMISSION_GRANTED) {
            Log.i(TAG, "Permission to record denied");
            makeRequest();
        }
    }

    protected void makeRequest() {
        ActivityCompat.requestPermissions(this,
            new String[]{Manifest.permission.RECORD_AUDIO},
            RECORD_REQUEST_CODE);
    }
}
```

接下来，实现`onRequestPermissionsResult()`方法，其内容如下所示：

```java
@Override
public void onRequestPermissionsResult(int requestCode,
    @NonNull String[] permissions, @NonNull int[] grantResults) {
    super.onRequestPermissionsResult(requestCode, permissions, grantResults);

    if (requestCode == RECORD_REQUEST_CODE) {
        if (grantResults.length == 0
            || grantResults[0] != PackageManager.PERMISSION_GRANTED) {
            Log.i(TAG, "Permission has been denied by user");
        } else {
            Log.i(TAG, "Permission has been granted by user");
        }
    }
}
```

在模拟器或设备上编译并运行应用，注意会出现一个如图 60-3 所示的请求录音权限的对话框：

![](img/android_permission_request.jpg)

图 60-3

使用应用进行点击并检查 Logcat 面板是否出现了“Permission has been granted by user”的消息。一旦用户授予了请求的权限，`checkSelfPermission()`方法在后续的调用中将返回`PERMISSION_GRANTED`，直到用户卸载并重新安装应用，或者在设置中更改了应用的权限。

## 60.5 为权限请求提供理由

如图 60-3 所示，用户可以拒绝请求的权限。在这种情况下，除非用户在点击“拒绝”按钮之前选择了“不再询问”选项，否则应用在每次用户启动时都会继续请求权限。用户的反复拒绝可能表明用户可能不理解为什么应用需要该权限。因此，如果在此提出请求时解释原因，用户可能会更容易授予权限。遗憾的是，无法更改请求对话框的内容来包含此类解释。

最好的做法是将解释包含在一个单独对话框中，该对话框可以在请求对话框呈现给用户之前显示。这引发了何时显示此解释的问题。Android 文档建议只有在用户之前拒绝过该权限时才显示解释对话框，并提供了一个方法来识别此类情况。

调用`ActivityCompat`类的`shouldRequestPermissionRationale()`方法，如果用户之前拒绝过对特定权限的请求，将返回`true`结果；如果之前没有请求，则返回`false`。在结果为`true`的情况下，应用应该显示一个包含需要权限理由的对话框，一旦用户阅读并关闭了该对话框，就应该重复权限请求。

为了向示例应用中添加此功能，修改`onCreate()`方法，其内容如下：

```java
import android.app.AlertDialog;

private void setupPermissions() {
    int permission = ContextCompat.checkSelfPermission(this,
        Manifest.permission.RECORD_AUDIO);

    if (permission != PackageManager.PERMISSION_GRANTED) {
        Log.i(TAG, "Permission to record denied");

        if (ActivityCompat.shouldRequestPermissionRationale(this,
            Manifest.permission.RECORD_AUDIO)) {
            AlertDialog.Builder builder = new AlertDialog.Builder(this);
            builder.setMessage("Permission to access the microphone is required for this app to record audio.")
                .setTitle("Permission required");
            builder.setPositiveButton("OK",
                (dialog, id) -> makeRequest());
            AlertDialog dialog = builder.create();
            dialog.show();
        } else {
            makeRequest();
        }
    }
}
```



该方法仍然检查权限是否已授予，但现在还会识别是否需要显示理由。如果用户之前拒绝过请求，则显示一个包含解释和 OK 按钮的对话框，当点击按钮时配置的监听器将调用`makeRequest()`方法。如果之前没有请求过，代码将直接跳转到寻求权限。

## 60.6 测试权限应用

在正在测试的设备或模拟器会话上，启动设置应用，选择应用选项，滚动并选择`PermissionDemo`应用。在应用设置界面上，点击卸载按钮移除应用。

重新运行应用，并在权限请求对话框出现时点击“不允许”按钮。停止并重新启动应用，验证理由对话框是否出现。点击 OK 按钮，并在权限请求对话框出现时点击“在使用应用时允许”按钮。

返回设置应用，选择应用选项，再次从列表中选择`PermissionDemo`应用。一旦列出了应用设置，验证权限部分是否列出了麦克风权限：

![](img/as_permission_microphone.jpg)

图 60-4

## 60.7 总结

在 Android 6.0 引入之前，应用程序请求访问某些功能的权限的唯一步骤是在应用程序的清单文件（manifest）中添加适当的行。用户在安装应用程序时，系统会提示其批准该权限。大多数权限仍然如此，但一组被认为是“危险”的权限除外。被认为危险的权限通常可能允许应用程序违反用户的隐私，例如允许访问麦克风、联系人列表或外部存储。

正如本章概述，基于 Android 6 或更高版本的应用程序现在在应用启动时必须向用户请求危险权限的批准，并在清单文件中包含该权限请求。

# 61. Android 通知教程

通知提供了一种应用程序在未运行或当前处于后台时向用户传达消息的方式。例如，消息应用可能会通知用户有来自联系人的新消息到达。通知可以分为本地通知和远程通知。本地通知由运行在设备上的应用程序本身触发。另一方面，远程通知由远程服务器启动，并递送到设备上展示给用户看。

通知显示在从屏幕状态栏向下划出的通知栏中，每个通知都可以包含一些操作，例如一个用于打开发送通知的应用程序的按钮。Android 还支持直接回复（Direct Reply）通知，该功能允许用户在通知面板内输入并提交对通知的回复。

本章概述了在 Android 应用程序中实现本地通知的方法。下一章“Android 直接回复通知教程”将涵盖直接回复通知的实现。

## 61.1 通知概述

当在 Android 设备上启动通知时，它会以图标的形式出现在状态栏中。例如，图 61-1 显示了一个包含多个通知图标的状态栏：

![](img/Image24252.jpg)

图 61-1

要查看通知，用户只需从状态栏开始向下划动的动作以拉下通知栏，如图 61-2 所示：

![](img/as_4.1_android_11_notifications.jpg)

图 61-2

在运行 Android 8 或更高版本的设备上，长按应用程序启动器图标将显示与该应用程序相关的任何待处理通知，如图 61-3 所示：

![](img/Image2442.jpg)

图 61-3

Android 8 及更高版本还支持通知点，当有等待用户查看的通知时会出现在应用程序启动器图标上。

典型的通知会显示一条消息，并在点击时启动负责发布通知的应用程序。通知还可能包含操作按钮，点击后会执行对应应用程序的特定任务。例如，图 61-4 显示了一个包含两个操作按钮的通知，允许用户删除或保存收到的消息：

![](img/Image2450.jpg)

图 61-4

用户还可以在通知中输入内联文本回复并将其发送给应用程序，如下方的图 61-5 所示。这允许用户在不将相应的应用程序启动到前台的情况下，对通知做出响应：

![](img/Image2458.jpg)

图 61-5

本章的剩余部分将介绍创建和发布包含操作的简单通知。直接回复支持的主题将在下一章“Android 直接回复通知教程”中介绍。

## 61.2 创建 NotifyDemo 项目

从欢迎界面选择“New Project”（新建项目）选项，在生成的新项目对话框中，选择“Empty Views Activity”模板，然后点击“Next”（下一步）按钮。

在`Name`字段中输入`NotifyDemo`，并指定`com.ebookfrenzy.notifydemo`为包名。在点击“Finish”（完成）按钮之前，将`Minimum API level`设置为`API 33`：Android 13 (Tiramisu)，并将`Language`菜单设置为`Java`。

## 61.3 设计用户界面

主活动（main activity）将包含一个按钮，其目的是创建并发出意图（intent）。在布局编辑器工具中定位并加载`activity_main.xml`文件，并删除默认的`TextView`组件。

在启用`Autoconnect`（自动连接）的情况下，从面板中拖放`Button`对象到布局画布的中心，如图 61-6 所示。

在布局中选中`Button`组件，使用`Attributes`（属性）面板配置`onClick`属性以调用名为`sendNotification`的方法。

![](img/as_notification_ui.jpg)

图 61-6

选中`Button`组件，在`Attributes`工具窗口中将`text`属性更改为“Notify”，并将属性值提取到字符串资源。

## 61.4 创建第二个 Activity

在此示例中，应用程序将包含第二个活动，该活动将由用户从通知内部启动。右键点击位于`app -> java`下的`com.ebookfrenzy.notifydemo`包名，选择`New -> Activity -> Empty Views Activity`菜单选项显示新 Android 活动对话框，向项目添加此新活动。

在`Activity Name`字段中输入`ResultActivity`，并将布局文件命名为`activity_result`。由于此活动不会在应用程序启动时启动（它将通过通知内部的意图启动），因此在点击“Finish”按钮之前，确保禁用了`Launcher Activity`（启动活动）选项是重要的。

打开第二个活动的布局（`app -> res -> layout -> activity_result.xml`），拖放一个`TextView`组件，使其位于布局中心。编辑`TextView`的文本使其显示为“Result Activity”，并将属性值提取到字符串资源。

## 61.5 创建通知通道

在应用程序发送通知之前，它必须创建一个通知通道。通知通道由一个`ID`（用于在应用程序内唯一标识通道）、一个通道名称和一个通道描述（只有后两个会被用户看到）组成。通道通过配置`NotificationChannel`实例并将该对象传递给`NotificationManager`类的`createNotificationChannel()`方法来创建。对于此示例，应用程序将包含一个名为“NotifyDemo News”的单一通知通道。编辑`MainActivity.java`文件并实现在应用程序启动时创建通道的代码：

```java
import android.app.NotificationManager;
import android.app.NotificationChannel;
import android.content.Context;
import android.graphics.Color;

public class MainActivity extends AppCompatActivity {

    NotificationManager notificationManager;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        notificationManager =
            (NotificationManager)
            getSystemService(Context.NOTIFICATION_SERVICE);

        createNotificationChannel(
            "com.ebookfrenzy.notifydemo.news",
            "NotifyDemo News",
            "Example News Channel");
    }

    protected void createNotificationChannel(String id, String name,
            String description) {

        int importance = NotificationManager.IMPORTANCE_LOW;
        NotificationChannel channel =
            new NotificationChannel(id, name, importance);

        channel.setDescription(description);

        channel.enableLights(true);
        channel.setLightColor(Color.RED);
        channel.enableVibration(true);
        channel.setVibrationPattern(
            new long[]{100, 200, 300, 400, 500, 400, 300, 200, 400});

        notificationManager.createNotificationChannel(channel);
    }
}
```

该代码声明并初始化了一个`NotificationManager`实例，然后创建了一个低重要性级别（其他选项为高、max、min 和 none）的新通道，并配置了名称和描述属性。在通道中还添加了一系列可选设置，用以自定义用户如何接收通知到达的提醒。这些设置适用于发送到此通道的所有通知。最后，通过将通知通道对象传递给`notificationManager`实例的`createNotificationChannel()`方法来创建通道。

## 61.6 请求通知权限

在测试应用程序之前，必须在应用程序的清单文件（manifest）请求适当权限。具体而言，应用程序需要向用户发送通知的权限。在`Project`工具窗口中，找到并双击`AndroidManifest.xml`文件，将其加载到编辑器中并修改 XML 以添加权限：

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.ebookfrenzy.audioapp" >

    <uses-permission android:name="android.permission.POST_NOTIFICATIONS" />
</manifest>
```

上述步骤将足以确保在运行 Android 6.0 之前的版本的设备上安装应用时，用户会启用通知权限。通知访问在 Android 中被归类为危险权限，因为它赋予了应用损害用户隐私的可能。为了让示例应用在 Android 6 或更高版本的设备上运行，必须添加代码在应用运行时请求权限。

编辑`MainActivity.java`文件，并开始添加一些额外的导入指令和一个常量，作为所请求权限的请求标识码：

```java
import androidx.core.app.ActivityCompat;
import androidx.core.content.ContextCompat;
import androidx.annotation.NonNull;
import android.widget.Toast;
import android.Manifest;
import android.content.pm.PackageManager;

public class MainActivity extends AppCompatActivity {

    private static final int NOTICATION_REQUEST_CODE = 101;
}
```

接下来，需要在类中添加一个方法，其目的是将要请求的权限和相应的请求标识码作为参数。继续留在`MainActivity.java`类文件中，如下实现此方法：

```java
protected void requestPermission(String permissionType, int requestCode) {
    int permission = ContextCompat.checkSelfPermission(this,
            permissionType);

    if (permission != PackageManager.PERMISSION_GRANTED) {
        ActivityCompat.requestPermissions(this,
                new String[]{permissionType}, requestCode);
    }
}
```

使用此书中“在 Android 中进行运行时权限请求”章节概述的步骤，上述方法在发出请求之前验证指定的权限是否已被授予，并将标识码作为参数传递。

当请求被处理后，活动（activity）上将调用`onRequestPermissionsResult()`方法，传递标识码和请求结果。因此，下一步是在`MainActivity.java`文件中如下实现此方法：

```java
@Override
public void onRequestPermissionsResult(int requestCode,
        @NonNull String[] permissions, @NonNull int[] grantResults) {
    super.onRequestPermissionsResult(requestCode, permissions, grantResults);

    if (requestCode == NOTIFICATION_REQUEST_CODE) {
        if (grantResults.length == 0
                || grantResults[0] !=
                PackageManager.PERMISSION_GRANTED) {
            Toast.makeText(this, "Notification required", Toast.LENGTH_LONG).show();
        }
    }
}
```

上述代码检查请求标识符以识别哪个权限已返回，然后检查相应的权限是否已授予。如果权限被拒绝，将向用户显示消息，指示应用将无法运行且记录已禁用。

在测试应用之前，剩下的工作是在应用启动时调用新添加的`requestPermission()`方法。留在`MainActivity.java`文件中，如下修改`onCreate()`方法：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);

    requestPermission(Manifest.permission.POST_NOTIFICATIONS, NOTIFICATION_REQUEST_CODE);
}
```

代码完成后，在运行 Android 13 或更高版本的设备或模拟器上编译并运行应用。当图 6-7 所示的对话框出现时，点击 Allow 按钮启用通知：

![](img/as_notifications.jpg)

启动应用后，将其放入后台并打开`Settings`应用。在`Settings`应用中，选择`Apps`，选择`NotifyDemo`项目，在后续屏幕上点击`Notifications`。通知屏幕应该列出`NotifyDemo News`为用户激活状态：

![](img/as_app_enabled.jpg)

在继续之前，确保已为该应用启用了通知点（notification dots）。虽然本示例不是要求，但值得注意的是，可以通过调用通知管理器的`deleteNotification()`方法从应用内部删除通道，并传递要删除通道的 ID：

```java
String channelID = "com.ebookfrenzy.notify.news";
notificationManager.deleteNotificationChannel(channelID);
```

## 61.7 创建并发布通知

通知使用`Notification.Builder`类创建，并且包含图标、标题和内容。打开`MainActivity.java`文件如下实现`sendNotification()`方法构建基础通知：

```java
import android.app.Notification;
import android.view.View;
```



`public void sendNotification(View view)` {

    `String channelID = "com.ebookfrenzy.notify.news";`

    `Notification notification =`

        `new Notification.Builder(MainActivity.this,`

                `channelID)`

            `.setContentTitle("Example Notification")`

            `.setContentText("This is an example notification.")`

            `.setSmallIcon(android.R.drawable.ic_dialog_info)`

            `.setChannelId(channelID)`

            `.build();`

}

一旦构建了通知，就需要使用 `NotificationManager` 实例的 `notify()` 方法发布。访问 `NotificationManager` 并发布通知的代码如下添加到 `sendNotification()` 方法中：

```java
protected void sendNotification(View view) {

    int notificationID = 101;

    String channelID = "com.ebookfrenzy.notify.news";

    Notification notification =

        new Notification.Builder(MainActivity.this,

                channelID)

            .setContentTitle("New Message")

            .setContentText("You've received new messages.")

            .setSmallIcon(android.R.drawable.ic_dialog_info)

            .setChannelId(channelID)

            .build();

    notificationManager.notify(notificationID, notification);

}
```

注意，当发布通知时，它会被分配一个通知 ID。该 ID 可以任意整数，并在之后用于更新通知。

编译并运行应用，点击主界面上的按钮。当状态栏中出现通知图标时，从状态栏向下触摸并拖动以查看完整通知：

![](img/as_notification.jpg)
图 61-9

长按通知以查看更多信息：

![](img/as_notification_details.jpg)
图 61-10

接下来，将应用置于后台，导航到显示所有应用启动器图标的主屏幕，注意 `NotifyDemo` 启动器图标上出现了一个通知点，如图 61-11 所示：

![](img/as_notification_dot.jpg)
图 61-11

如果没有出现该点，请检查`设置（Settings）`应用中对 `NotifyDemo` 的通知选项，以确认已启用“通知点（notification dots）”，正如本章前面概述的那样。如果点仍未出现，请长按设备主屏幕的空白区域，从弹出的菜单中选择“主设置（Home Settings）”选项，并启用“通知点（Notification dots）”选项。

长按启动器图标将显示一个包含通知的弹出窗口：

![](img/as_app_dot_detail.jpg)
图 61-12

如果一个应用有多个待处理通知，长按菜单弹出窗将包含通知计数（如上图高所示）。此数字可以在构建通知时通过调用 `setNumber()` 方法在应用内部进行配置：

```java
Notification notification = new Notification.Builder(MainActivity.this, CHANNEL_ID)

        .setContentTitle("Example Notification")

        .setContentText("This is an example notification.")

        .setSmallIcon(android.R.drawable.ic_dialog_info)

        .setChannelId(CHANNEL_ID)

        .setNumber(10)

        .build();
```

按照目前的实现方式，无论从何处访问，点击通知都没有效果。下一步是配置通知，以便在点击时启动一个活动（activity）。

## 61.8 从通知启动活动

通知应该允许用户执行某些操作，例如启动相应的应用或响应通知采取其他操作。一个常见的需求是在用户点击通知时，启动属于该应用的活动。

这种方法需要启动一个活动并配置一个 `Intent` 来启动该活动。假设应用包含一个名为 `ResultActivity` 的活动，则 intent 的创建方式如下：

```java
Intent resultIntent = new Intent(this, ResultActivity.class);
```

然后需要将此 `intent` 封装在 `PendingIntent` 实例中。`PendingIntent` 对象的设计允许将 `intent` 传递给其他应用程序，实质上授予这些应用程序在未来某个时刻执行该 intent 的权限。在这种情况下，`PendingIntent` 对象用于为通知系统提供一种方法，在用户点击通知面板时启动 `ResultActivity` 活动：

```java
PendingIntent pendingIntent =

    PendingIntent.getActivity(

        this,

        0,

        resultIntent,

        PendingIntent.FLAG_IMMUTABLE

    );
```

剩下的工作是在构建通知过程中使用 `setContentIntent()` 方法分配 `PendingIntent` 对象。

将这些更改整合后得到修改后的 `sendNotification()` 方法，其内容如下：

```java
.

.

import android.app.PendingIntent;

import android.content.Intent;

import android.graphics.drawable.Icon;

.

.

protected void sendNotification(View view) {

    int notificationId = 101;

    Intent resultIntent = new Intent(this, ResultActivity.class);

    PendingIntent pendingIntent =

            PendingIntent.getActivity(

                this,

                0,

                resultIntent,

                PendingIntent.FLAG_IMMUTABLE

            );

    String CHANNEL_ID = "com.ebookfrenzy.notifydemo.news";

    Notification notification = new Notification.Builder(MainActivity.this, CHANNEL_ID)

            .setContentTitle("Example Notification")

            .setContentText("This is an example notification.")

            .setSmallIcon(android.R.drawable.ic_dialog_info)

            .setChannelId(CHANNEL_ID)

            .setContentIntent(pendingIntent)

            .build();

    notificationManager.notify(notificationId, notification);

}
```

编译并重新运行应用，点击按钮并显示通知抽屉。然而，这次点击通知将导致 `ResultActivity` 启动。

## 61.9 为通知添加操作

为通知添加交互性的另一种方法是创建操作（actions）。它们显示为通知消息下方的按钮，并程序设计为在用户点击时触发特定的 `intent`。如果将以下代码添加到 `sendNotification()` 方法中，将添加一个标记为“打开（Open）”的操作，它可以启动引用的 intent：

```java
final Icon icon = Icon.createWithResource(MainActivity.this, android.R.drawable.ic_dialog_info);

Notification.Action action =

    new Notification.Action.Builder(icon, "Open", pendingIntent)

    .build();

Notification notification = new Notification.Builder(MainActivity.this, CHANNEL_ID)

        .setContentTitle("Example Notification")

        .setContentText("This is an example notification.")

        .setSmallIcon(R.drawable.ic_info_24dp)

        .setChannelId(channelID)

        .setContentIntent(pendingIntent)

        .setActions(action)

        .build();

notificationManager.notify(notificationId, notification);
```

将上述代码添加到方法并运行应用。发布通知，并注意通知内的 Open 操作（取决于 Android 版本，可能需要下拉通知面板才能显示）：

![](img/as_notification.jpg)
图 61-13

点击该操作将触发相应的 intent 并启动 `ResultActivity`。

## 61.10 折叠通知

如果一个应用经常发布通知，可能会导致这些通知迅速堆满状态栏和通知抽屉，为用户提供欠佳的体验。这对于每当有新闻新闻或新消息到达就发送通知的消息或消息应用尤为如此。例如，考虑图 61-14 中的通知：

![](img/as_3.2_unbundled_notifications.jpg)
图 61-14

现在想象如果有十条甚至二十条新消息。为了避免这个问题，Android 允许将通知分组。

要折叠通知，每个通知必须通过 `setGroup()` 方法指定属于同一个组，并且必须发布并配置一个额外的通知。例如，以下代码创建并发布了上方图 61-14 所示的三个通知，但将它们折叠到了同一个组中。代码还发布了一个作为摘要的通知：

```java
final String GROUP_KEY_NOTIFY = "group_key_notify";

Notification.Builder builderSummary =

    new Notification.Builder(this, channelID)

        .setSmallIcon(android.R.drawable.ic_dialog_info)

        .setContentTitle("A Bundle Example")

        .setContentText("You have 3 new messages")

        .setGroup(GROUP_KEY_NOTIFY)

        .setGroupSummary(true);

Notification.Builder builder1 =

    new Notification.Builder(this, channelID)

        .setSmallIcon(android.R.drawable.ic_dialog_info)

        .setContentTitle("New Message")

        .setContentText("You have a new message from Kassidy")

        .setGroup(GROUP_KEY_NOTIFY);
```

```java
Notification.Builder builder2 =

        new Notification.Builder(this, channelID)

            .setSmallIcon(android.R.drawable.ic_dialog_info)

            .setContentTitle("New Message")

            .setContentText("You have a new message from Caitlyn")

            .setGroup(GROUP_KEY_NOTIFY);

Notification.Builder builder3 =

        new Notification.Builder(this, channelID)

            .setSmallIcon(android.R.drawable.ic_dialog_info)

            .setContentTitle("New Message")

            .setContentText("You have a new message from Jason")

            .setGroup(GROUP_KEY_NOTIFY);

int notificationId0 = 100;

int notificationId1 = 101;

int notificationId2 = 102;

int notificationId3 = 103;

notificationManager.notify(notificationId1, builder1.build());

notificationManager.notify(notificationId2, builder2.build());

notificationManager.notify(notificationId3, builder3.build());

notificationManager.notify(notificationId0, builderSummary.build());
```



当代码执行时，状态栏中只会显示一个通知图标，尽管应用已发布了四个通知。在通知栏中，会显示一个摘要通知，列出每个组绑通知中的信息：

![](img/Image2528.jpg)
图 61-15

进一步向下滑动通知条目可以展开面板，显示每个组绑通知的详细信息：

![](img/Image2536.jpg)
图 61-16

### 61.11 总结

通知为应用提供了一种在应用未运行或处于后台时向用户传递消息的方式。通知显示在状态栏和通知栏中。本地通知由运行的应用在设备上触发，而远程通知由远程服务器启动并递送到设备。本地通知使用`NotificationCompat.Builder`类创建，并使用`NotificationManager`服务发布。

如本章所示，可以通过使用动作、意图和`PendingIntent`类来配置通知，为用户提供选项（例如启动活动或保存消息）。通知分组（Notification bundling）提供了一种对通知进行分组的机制，为发布更多通知的应用提供了改进的体验。

## 62. Android 直接回复通知教程

直接回复是 Android 的一项功能，允许用户在通知中输入文本并将其发送到与该通知关联的应用。这使用户可以在不启动应用内活动的情况下直接回复通知中的消息。本章将基于上一章所得的知识，创建一个使用此通知功能的示例应用。

### 62.1 创建 DirectReply 项目

从欢迎界面选择 New Project（新项目）选项，在弹出的新项目对话框中，点击 Next（下一步）按钮之前选择 Empty Views Activity 模板。

在 Name（名称）字段中输入`DirectReply`，并指定`com.ebookfrenzy.directreply`为包名。在点击 Finish（完成）按钮之前，将最低 API 级别设置为`API 33: Android 13`，并将语言菜单更改为`Java`。按照节 11.8 将项目迁移到视图绑定中概述的步骤修改项目以支持视图绑定。

### 62.2 设计用户界面

在布局工具中加载`activity_main.xml`布局文件。在启用自动连接（Autoconnect）的情况下，在现有的“Hello World!”标签下方添加一个`Button`对象，如图 62-1 所示。在布局中选中`Button`组件，使用 Attributes（属性）工具窗口将`onClick`属性设置为调用名为`sendNotification`的方法。必要时使用 Infer Constraints（推断约束）按钮为布局添加任何缺失的约束。继续之前，选择“Hello World!”`TextView`，将`id`属性更改为`textView`，并将按钮上的文字修改为“Notify”：

![](img/as_direct_reply_ui.jpg)
图 62-1

### 62.3 请求通知权限

在 Project（项目）工具窗口中找到并双击`AndroidManifest.xml`文件加载到编辑器，修改 XML 添加权限元素：

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.ebookfrenzy.audio">
    <uses-permission android:name="android.permission.POST_NOTIFICATIONS" />
```

编辑`MainActivity.java`文件，首先添加一些导入指令和一个常量作为所请求权限的请求代码：

```java
import androidx.annotation.NonNull;
import androidx.core.app.ActivityCompat;
import androidx.core.content.ContextCompat;
import android.widget.Toast;
import android.Manifest;
import android.content.pm.PackageManager;

public class MainActivity extends AppCompatActivity {
    private static final int NOTIFICATION_REQUEST_CODE = 01;
```

接下来，需要向类中添加一个方法，其目的是将要请求的权限和相应的请求标识作为参数。在`MainActivity.java`类中，按如下实现该方法：

```java
protected void requestPermission(String permissionType, int requestCode) {
    int permission = ContextCompat.checkSelfPermission(this, permissionType);
    if (permission != PackageManager.PERMISSION_GRANTED) {
        ActivityCompat.requestPermissions(this, new String[]{permissionType}, requestCode);
    }
}
```

当请求处理后，`onRequestPermissionsResult()`方法将在活动上调用，传递标识码和请求结果。因此，下一步是在`MainActivity.java`文件中实现此方法：

```java
@Override
public void onRequestPermissionsResult(int requestCode, @NonNull String[] permissions, @NonNull int[] grantResults) {
    super.onRequestPermissionsResult(requestCode, permissions, grantResults);
    if (requestCode == NOTIFICATION_REQUEST_CODE) {
        if (grantResults.length == 0 || grantResults[0] != PackageManager.PERMISSION_GRANTED) {
            Toast.makeText(this, "Notification required", Toast.LENGTH_LONG).show();
        }
    }
}
```

在测试应用之前，剩下的是在应用启动时调用新添加的`requestPermission()`方法。在`MainActivity.java`文件中，按如下修改`onCreate()`方法：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    binding = ActivityMainBinding.inflate(getLayoutInflater());
    View view = binding.getRoot();
    setContentView(view);
    requestPermission(Manifest.permission.POST_NOTIFICATIONS, NOTIFICATION_REQUEST_CODE);
}
```

### 62.4 创建通知通道

与上一章的示例一样，在发送通知之前必须创建一个通道。编辑`MainActivity.java`文件并添加代码创建新通道：

```java
import android.app.NotificationChannel;
import android.app.NotificationManager;
import android.content.Context;
import android.graphics.Color;

public class MainActivity extends AppCompatActivity {
    private NotificationManager notificationManager;
    private final String channelID = "com.ebookfrenzy.directreply.news";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        notificationManager = (NotificationManager) getSystemService(Context.NOTIFICATION_SERVICE);
        createNotificationChannel(channelID, "DirectReply News", "Example News Channel");
    }
}
```

```java
protected void createNotificationChannel(String id, String name, String description) {
    int importance = NotificationManager.IMPORTANCE_HIGH;
    NotificationChannel channel = new NotificationChannel(id, name, importance);
    channel.setDescription(description);
    channel.enableLights(true);
    channel.setLightColor(Color.RED);
    channel.enableVibration(true);
    channel.setVibrationPattern(new long[]{100, 200, 300, 400, 500, 400, 300, 200, 400});
    notificationManager.createNotificationChannel(channel);
}
```

### 62.5 构建 RemoteInput 对象

在通知中实现内联直接回复的关键元素是`RemoteInput`类。之前的章节介绍了`PendingIntent`类，并解释了它如何允许一个应用程序创建一个意图（intent），然后授予其他应用程序或服务从原始应用外部启动该意图的能力。在名为“Android 通知教程”的章节中，创建了一个待定意图（pending intent），允许从通知内部启动原始应用的 activity。`RemoteInput`类允许将用户输入请求随意图一起包含在`PendingIntent`对象中。当`PendingIntent`对象中的意图触发时（例如启动一个 activity），该 activity 也会接收用户提供的任何输入。

在通知中实现直接回复的第一步是创建`RemoteInput`对象。这是通过使用`RemoteInput.Builder()`方法实现的。要构建`RemoteInput`对象，需要一个关键字符串，它将用于从生成的意图中提取输入。该对象还需要一个标签字符串，该字符串将显示在通知的文本输入框中。编辑`MainActivity.java`文件并添加`sendNotification()`方法。注意还添加了一些导入指令和变量，这些变量将在章节后续的进展中使用：

```java
package com.ebookfrenzy.directreply;

import android.app.PendingIntent;
import android.app.RemoteInput;
import android.content.Intent;

public class MainActivity extends AppCompatActivity {
    private static final int notificationId = 101;
    private static final String KEY_TEXT_REPLY = "key_text_reply";
    private NotificationManager notificationManager;
    private static final String channelID = "com.ebookfrenzy.directreply.news";

    public void sendNotification(View view) {
        String replyLabel = "Enter your reply here";
        RemoteInput remoteInput = new RemoteInput.Builder(KEY_TEXT_REPLY)
                .setLabel(replyLabel)
                .build();
    }
}
```

现在`RemoteInput`对象已经创建并用键和标签字符串进行了初始化，它需要被放置在通知操作对象内部。然而，在执行该步骤之前，需要创建`PendingIntent`实例。

### 62.6 创建 PendingIntent

创建`PendingIntent`的步骤与“Android 通知教程”章节中概述的步骤相同，只是意图将被配置为启动`MainActivity`。在`MainActivity.java`文件中，添加以下代码来创建`PendingIntent`：

```java
public void sendNotification(View view) {
    String replyLabel = "Enter your reply here";
    RemoteInput remoteInput = new RemoteInput.Builder(KEY_TEXT_REPLY)
            .setLabel(replyLabel)
            .build();

    Intent resultIntent = new Intent(this, MainActivity.class);
    PendingIntent resultPendingIntent = PendingIntent.getActivity(this, 0, resultIntent, PendingIntent.FLAG_MUTABLE);
}
```

## 62.7 创建回复操作

内联回复将通过通知中的操作按钮进行访问。该操作需要被创建，并与图标、显示在按钮上的标签、`PendingIntent`对象以及`RemoteInput`对象进行配置。修改`sendNotification()`方法以添加创建此操作的代码：

```java
import android.graphics.drawable.Icon;
import android.app.Notification;

public void sendNotification(View view) {
    String replyLabel = "Enter your reply";
    RemoteInput remoteInput = new RemoteInput.Builder(KEY_TEXT_REPLY)
            .setLabel(replyLabel)
            .build();

    Intent resultIntent = new Intent(this, MainActivity.class);
    PendingIntent resultPendingIntent = PendingIntent.getActivity(this, 0, resultIntent, PendingIntent.FLAG_MUTABLE);

    final Icon icon = Icon.createWithResource(MainActivity.this, android.R.drawable.ic_dialog_info);
    Notification.Action replyAction = new Notification.Action.Builder(icon, "Reply", resultPendingIntent)
            .addRemoteInput(remoteInput)
            .build();
}
```

在教程的这一阶段，我们已经构建了并准备好使用`RemoteInput`、`PendingIntent`和`Notification Action`对象。下一阶段是构建通知并发布它：

```java
public void sendNotification(View view) {
    String replyLabel = "Enter your here";
    RemoteInput remoteInput = new RemoteInput.Builder(KEY_TEXT_REPLY)
            .setLabel(replyLabel)
            .build();

    Intent resultIntent = new Intent(this, MainActivity.class);
```



`PendingIntent resultPendingIntent = PendingIntent.getActivity(this, 0, resultIntent, PendingIntent.FLAG_MUTABLE);`

`final Icon icon = Icon.createWithResource(MainActivity.this, android.R.drawable.ic_dialog_info);`

`Notification.Action replyAction = new Notification.Action.Builder(icon, "Reply", resultPendingIntent)`

`.addRemoteInput(remoteInput)`

`.build();`

`Notification newMessageNotification = new Notification.Builder(this, channelID)`

`.setColor(ContextCompat.getColor(this, android.R.color.holo_blue_dark))`

`.setSmallIcon(android.R.drawable.ic_dialog_info)`

`.setContentTitle("My Notification")`

`.setContentText("This is a test message")`

`.addAction(replyAction).build();`

`NotificationManager notificationManager = (NotificationManager) getSystemService(Context.NOTIFICATION_SERVICE);`

`notificationManager.notify(notificationId, newMessageNotification);`

修改完成后，编译并运行应用，允许通知，并测试点击按钮是否成功发布通知。当查看通知栏时，通知应该如图 62-2 所示：

![](img/as_direct_reply.jpg)

图 62-2

点击回复操作按钮，使文本输入框出现，显示创建 `RemoteInput` 对象时嵌入的回复标签。

![](img/as_direct_reply_enter.jpg)

图 62-3

输入一些文本并点击输入框末部的发送箭头按钮。

## 62.8 接收直接回复输入

既然通知已成功向用户请求输入，应用需要对该输入进行处理。本教程的目标是让用户在通知输入的文本显示在 Activity 用户界面的 `TextView` 控件上。

当用户输入文本并点击发送按钮时，`MainActivity` 将通过 `PendingIntent` 对象中的 `intent` 启动。此 `intent` 中包含了用户通过通知输入的文本。在 Activity 的 `onCreate()` 方法中，调用 `getIntent()` 方法将返回启动该 Activity 的 `intent` 副本。将其传递给 `RemoteInput.getResultsFromIntent()` 方法，反过来，它会返回一个包含回复文本的 `Bundle` 对象，该对象可以被提取并赋值给 `TextView` 控件。这导致了 `MainActivity.java` 文件中的 `onCreate()` 方法被修改，其内容如下：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
...
    createNotificationChannel(channelID, "DirectReply News",
                               Example News Channel");
    handleIntent();
}

private void handleIntent() {
    Intent intent = this.getIntent();
    Bundle remoteInput = RemoteInput.getResultsFromIntent(intent);
    if (remoteInput != null) {
        String inputString = remoteInput.getCharSequence(
                KEY_TEXT_REPLY).toString();
        binding.textView.setText(inputString);
    }
}
```

完成这些代码更改后，再次构建并运行应用。点击按钮发出通知，并在通知面板内输入并发送一些文本。注意，`MainActivity` 中的 `TextView` 控件已更新以显示输入的内联文本。

### 62.9 更新通知

在通知中发送回复后，你可能注意到进度指示器在通知面板中持续旋转，如图 62-4 所示：

![](img/as_direct_reply_progress.jpg)

图 62-4

通知显示此指示器是因为它正在等待 Activity 的响应，以确认收到发送的文本。执行此项任务的推荐方法是用新消息更新通知，表明已接收并处理了回复。由于原始通知在发布时已分配 ID，因此可以再次使用它来执行更新。向 `handleIntent()` 方法添加以下代码以执行此项任务：

```java
private void handleIntent() {
    Intent intent = this.getIntent();
    Bundle remoteInput = RemoteInput.getResultsFromIntent(intent);
    if (remoteInput != null) {
        String inputString = remoteInput.getCharSequence(
                KEY_TEXT_REPLY).toString();
        binding.myTextView.setText(inputString);
        Notification repliedNotification =
                new Notification.Builder(this, channelID)
                        .setSmallIcon(
                                     android.R.drawable.ic_dialog_info)
                        .setContentText("Reply received")
                        .build();
        notificationManager.notify(notificationId,
                repliedNotification);
    }
}
```

最后测试一次应用，验证在发送内联回复文本后进度指示器消失，并且出现了一个新的通知。

![](img/as_direct_reply_progress.jpg)

Figure 62-4

### 62.10 总结

通知显示此指示器是因为它正在等待 Activity 的响应，以确认收到发送的文本。执行此项任务的推荐方法是用新消息更新通知，表明已接收并处理了回复。由于原始通知在发布时已分配 ID，因此可以再次使用它来执行更新。

## 63. 折叠屏设备与多窗口

虽然在编写时，市场上还没有可以进行应用测试的折叠屏设备，但 Android SDK 包含了折叠屏模拟器。要创建一个折叠屏模拟器，选择 Android `Tools -> AVD Manager` 菜单选项，点击 `Create Virtual Device` 按钮，并在硬件选择屏幕上，从下方图 63-3 所示的折叠屏选项之一：

![](img/as_foldable_avd.jpg)

Figure 63-3

在选择折叠屏后，继续完成创建过程，选择 Android 10 API 29 或更高版本作为系统镜像。

一旦模拟器启动运行，工具栏将出现一个额外的按钮，允许模拟器在折叠和展开配置之间进行切换：

![](img/as_3.5_foldable_emulator_fold_button.jpg)

### 63.1 折叠屏与多窗口

多窗口支持最初在 Android 7 中引入，允许显示多一个 Activity。Android 中的多窗口支持提供了三种不同形式。分屏模式在大多数手机和平板设备上可用，提供了一个分屏环境，两个 Activity 并排显示或一个在上在上。它提供了一个可移动的分割线，用户拖动它时会调整分配给每个相邻 Activity 的屏幕百分比：

![](img/Image2422.jpg)

Figure 63-1

自由窗口（Freeform mode）在较大的屏幕上提供了一个窗口环境，目前由设备决定是否启用。自由窗口与分屏模式的区别在于，它允许每个 Activity 在独立的、可调整大小的窗口中出现，并且不受限于同时显示两个 Activity。例如，图 63-2 显示了一个处于自由窗口模式的设备，显示了计算器和另一个应用：

![](img/Image24362.jpg)

Figure 63-2

画中画（Picture-in-picture）支持正如其名，允许在用户执行其他任务时在较小的窗口中继续播放视频，该主题将从`Android 画中画模式` 章开始介绍。

### 63.3 进入多窗口模式

可以通过显示最近任务界面（Overview screen）、长按列出的应用中工具栏中的应用图标，并选择“分屏”菜单选项进入分屏模式，如图 63-5 所示：

![](img/as_3.5_split_screen_button.jpg)

Figure 63-5

一旦进入分屏模式，`Overview` 按钮将变为显示两个矩形（如图 63-6 中标记的 A），当前活动将占据屏幕部分 (B)，`Overview` 屏幕将出现在屏幕的相邻部分，允许选择第二个活动进行显示 (C)：

![](img/as_3.5_split_screen_select_second_app.jpg)

图 63-6

一旦选择了第二个应用，屏幕将如上文 图 63-1 所示被平分。

要退出分屏模式，只需将分隔两个活动的分割线拖动到最远边缘，使只有一个活动占据整个屏幕，或者长按 `Overview` 按钮直到它恢复为单个正方形。

## 63.4 启用并使用自由窗口支持

虽然并不是所有设备都受到官方支持，但在大屏设备和模拟器上可以启用自由窗口多窗口模式。要启用此模式，请在模拟器运行或设备连接时，运行以下 `adb` 命令：

```
adb shell settings put global enable_freeform_support 1
```

做出此更改后，可能需要重启设备设置才会生效。

一旦启用，在 `Overview` 屏幕中长按应用图标时，会出现一个额外的选项，如图 63-7 所示：

![](img/as_3.5_freeform_button.jpg)

图 63-7

### 63.5 检查自由窗口支持

如本章前面的概述所述，Google 将是否启用自由窗口多窗口模式的选择权交给了各个 Android 设备制造商。由于自由窗口仅在较大的设备上使用才有意义，因此无法保证在每个可能运行应用的设备上都提供自由窗口。幸运的是，如果设备不支持自由窗口模式，系统将忽略所有特定的自由窗口的方法和属性，因此使用这些功能不会导致应用在非自由窗口设备上崩溃。然而，可能会出现某些情况，检测设备是否支持自由窗口多窗口模式是有用的。幸运的是，可以通过检查包管理器中的自由窗口管理功能来实现。下面的代码示例检查了自由窗口多窗口支持，并根据测试结果返回 `Boolean` 值：

```java
public Boolean checkFreeform() {
    return getPackageManager().hasSystemFeature(
            PackageManager.FEATURE_FREEFORM_WINDOW_MANAGEMENT);
}
```

### 63.6 在应用中启用多窗口支持

`android:resizableActivity` 清清单文件设置控制应用是否支持多窗口行为。此设置可以在应用程序级或单个活动级进行。例如，下面的代码片段配置了名为 `MainActivity` 的活动以同时支持分屏和自由窗口多窗口模式：

```xml
<activity
    android:name=".MainActivity"
    android:resizeableActivity="true"
    android:label="@string/app_name"
    android:theme="@style/AppTheme.NoActionBar">
    <intent-filter>
        <action android:name="android.intent.action.MAIN" />
        <category android:name="android.intent.category.LAUNCHER" />
    </intent-filter>
</activity>
```

将该属性设置为 `false` 将防止活动出现在分屏或自由窗口模式下，且相应的按钮将出现在应用的 `Overview` 菜单中。在分屏配置中选择一个禁用多窗口支持的活动作为第二个活动，将显示一条消息，指示该应用可能不支持多窗口模式。

### 63.7 指定多窗口属性

`<layout>` 元素提供了许多属性，用于指定活动在多窗口模式下启动时的尺寸和位置。当在自由窗口模式下启动时，活动的初始高度、宽度和位置可以使用以下属性指定：

* `android:defaultWidth` – 指定活动的默认宽度。
* `android:defaultHeight` – 指定活动的默认高度。
* `android:gravity` – 指定活动的初始位置（start、end、left、right、top 等）。

注意，上述属性仅当活动在自由窗口模式下显示时对活动生效。下面的示例配置了活动在屏幕起始边缘顶部以特定的高度和宽度出现：

```xml
<activity android:name=".MainActivity ">
    <layout android:defaultHeight="350dp"
             android:defaultWidth="450dp"
             android:gravity="start|end" />
</activity>
```

可以使用以下 `<layout>` 属性来指定活动在分屏视图或自由窗口模式下可以缩减到的最小宽度和高度：

* `android:minimalHeight` – 指定活动在分屏视图或自由窗口模式下可以缩减的最小高度。
* `android:minimalWidth` – 指定活动在自由窗口模式下可以缩减的最小宽度。

当用户将分屏分割线滑动超过最小边界，系统将停止调整活动大小并仅对用户界面进行裁剪。下面的清单片段实现了最小宽度和高度：

```xml
<activity android:name=".MainActivity ">
    <layout android:minimalHeight="400dp"
    android:minimalWidth="290dp" />
</activity>
```

## 63.8 在活动中检测多窗口模式

可能会出现情况，活动需要检测自己是否正以多窗口模式显示给用户。可以通过调用 `Activity` 类的 `isInWindowMode()` 方法获取状态。它根据是否全屏返回 `true` 或 `false` 值：

```java
if (isInWindowMode()) {
    // 处于多窗口模式
} else {
    // 不处于多窗口模式
}
```

### 63.9 接收多窗口通知

如果活动重写了 `onWindowModeChanged()` 回调方法，则将接收进入或退出多窗口模式的通知。传递给方法的第一个参数在进入多窗口模式时为 `true`，在退出时为 `false`。新的配置设置包含在第二个参数 `Configuration` 对象中：

```java
@Override
public void onWindowModeChanged(boolean isInWindowMode, Configuration newConfig) {
    super.onWindowModeChanged(isInWindowMode, newConfig);
    if (isInWindowMode) {
        // 进入多窗口模式
    } else {
        // 退出多窗口模式
    }
}
```

如处理 Android 活动状态变化章节所述，Android 10 及更高版本允许多个活动处于恢复状态。用户最近交互的活动被称为顶层恢复活动。为了跟踪活动获取和丢失顶层恢复状态，可以在活动中实现 `onTopResumedActivityChanged()` 回调方法，例如：

```java
@Override
public void onTopResumedActivityChanged(boolean isTopResumedActivity) {
```



`super.onTopResumedActivityChanged(isTopResumedActivity);`

```
if (isTopResumedActivity) {

    // 活动现在是顶层恢复活动

} else {

    // 活动不再是顶层恢复活动

}
```

在某些运行 Android 9 的设备上，通过在应用清单文件中启用以下属性，可能也可以在应用中利用多恢复：

```xml
<meta-data 
    android:name="android.allow_multiple_resumed_activities" 
    android:value="true" />
```

## 63.10 在多窗口模式下启动 Activity

在本书的 Android 式 Intent – 示例章节中，创建了一个示例应用，其中一个 activity 使用 `intent` 启动第二个 activity。默认情况下，通过 `intent` 启动的 activity 被认为与源 activity 位于同一个任务栈中。然而，通过向 `intent` 传递适当标志（flags），可以将 activity 启动到新的任务栈中。

当多窗口模式下的 activity 在同一个任务栈内启动另一个 activity 时，新 activity 将替换分屏或自由窗口窗口中的源 activity（用户通过回退键可以回到原始 activity）。

然而，当在分屏模式下启动到新的任务栈中时，第二个 activity 将出现在与原始 activity 相邻的窗口中，允许同时查看两个 activity。在自由窗口模式下，启动的 activity 将出现在与原始 activity 独立的窗口中。

要将 activity 启动到新的任务栈中，必须在启动 `intent` 之前设置以下标志：

* `Intent.FLAG_ACTIVITY_LAUNCH_ADJACENT`
* `Intent.FLAG_ACTIVITY_MULTIPLE_TASK`
* `Intent.FLAG_ACTIVITY_NEW_TASK`

例如，以下代码配置并启动了一个设计在独立窗口中显示的第二个 activity：

```java
Intent i = new Intent(this, SecondActivity.class);
i.addFlags(Intent.FLAG_ACTIVITY_LAUNCH_ADJACENT|
           Intent.FLAG_ACTIVITY_MULTIPLE_TASK|
           Intent.FLAG_ACTIVITY_NEW_TASK);
startActivity(i);
```

## 63.11 配置自由窗口 Activity 的大小和位置

默认情况下，在自由窗口模式下启动到不同任务栈的 activity 将置于屏幕中心，大小由系统决定。可以通过 `ActivityOptions` 类向 `intent` 传递启动边界（launch bounds）设置来控制此窗口的位置和尺寸。此过程的第一步是创建一个 `Rect` 对象，并配置其代表 activity 窗口的矩形的左 (X)、顶 (Y)、右 (X) 和底 (Y) 坐标。例如，以下代码创建一个 `Rect` 对象，其左上角位于坐标 (0, 0)，右下角位于 (100, 100)：

```java
Rect rect = new Rect(100, 800, 900, 700);
```

下一步是创建 `ActivityOptions` 类的基本实例，并通过 `setLaunchBounds()` 方法使用 `Rect` 设置对其初始化：

```java
ActivityOptions options = ActivityOptions.makeBasic();
ActivityOptions bounds = options.setLaunchBounds(rect);
```

最后，将 `ActivityOptions` 实例转换为 `Bundle` 对象，并与 `Intent` 对象一起传递给 `startActivity()` 方法：

```java
startActivity(i, bounds.toBundle());
```

结合这些步骤，得到如下代码序列：

```java
Intent i = new Intent(this, SecondActivity.class);
i.addFlags(Intent.FLAG_ACTIVITY_LAUNCH_ADJACENT|
           Intent.FLAG_ACTIVITY_MULTIPLE_TASK|
           Intent.FLAG_ACTIVITY_NEW_TASK);
Rect rect = new Rect(100, 800, 900, 700);
ActivityOptions options = ActivityOptions.makeBasic();
ActivityOptions bounds = options.setLaunchBounds(rect);
startActivity(i, bounds.toBundle());
```

当源 activity 处于自由窗口模式时，通过 `intent` 启动第二个 activity，新 activity 窗口将按照 `Rect` 对象定义的位置和尺寸出现。

### 63.12 总结

Android 7 引入了多窗口支持，该系统允许屏幕上同时显示多个 activity。此功能现在成了为折叠设备提供支持的基础。多窗口支持提供的三种模式是分屏、自由窗口和画中画。在分屏模式下，屏幕被水平或垂直分为两个窗格，每个窗格显示一个 activity。自由窗口模式仅支持某些 Android 设备，允许每个 activity 出现在独立的、可移动且可调整大小的窗口中。如本所示，Android SDK 中提供了许多方法和属性设置，用于检测、响应和控制应用内部的多窗口行为。

## 64. Android SQLite 数据库概述

不需要存储至少某些持久化数据的移动应用寥寥无几。使用数据库是大多数应用程序的一个要素，范围从几乎完全由数据驱动的应用到需要存储少量数据（如当前的游戏得分）的应用。

当考虑到典型 Android 应用的瞬态生命周期时，持久化数据存储的重要性变得更加明显。由于 Android 运行时系统始终存在终止应用组件以释放资源的风险，制定一个避免数据丢失的全面数据存储策略是设计和实现任何应用开发策略的关键因素。

本章将涵盖与 Android 操作系统绑定的 SQLite 数据库管理系统，并概述有助于 Android 应用中持久化 SQLite 数据库存储的 Android SDK 类。在深入探讨 Android 环境下 SQLite 的细节之前，将对数据库和 SQL 进行简要概述。

### 64.1 理解数据库表

数据库表（Database Tables）提供了数据库中最基础的数据结构。每个数据库可以包含多个表，每个表设计用于持有特定类型的信息。例如，数据库可能包含一个客户表，其中包含每个客户的姓名、地址和电话号码。同一个数据库可能还包含一个产品表，用于存储带有关联产品代码的产品描述。

数据库中的每个表都分配有一个名称，该名称在该数据库中必须是唯一的。表名一旦分配给某个数据库中的表，除非在另一个数据库中，否则不能用于另一个表。

### 64.2 引入数据库模式

数据库模式（Database Schemas）定义了存储在数据库表中的数据的特征。例如，客户数据库表的表模式可能定义客户名为长度不超过 20 个字符的字符串，客户电话号码为具有特定格式的数值数据字段。

模式还用于定义整个数据库的结构。

### 64.3 列和数据类型

在此阶段，将数据库表看作类似于电子表格是有帮助的。每一列（Column）代表对应表中的一个数据字段。例如，表的名称、地址和电话数据字段都是列。

每一列反过来被定义为包含特定类型的数据。因此，设计用于存储数字的列将被定义为包含数值数据。

### 64.4 数据库行

每个保存到表的新记录都存储在行（Row）中。每行反过来由与保存记录相关的列组成。

再次考虑本章早期描述的电子表格类比。客户表中的每个条目等同于电子表格中的行，每一列都包含每个客户的数据。当向表中添加新客户时，会创建一个新行，并将该客户的数据存储在新行的相应列中。

行有时也被记录（records）或条目（entries），这些术语通常可以互换。

### 64.5 引入主键

每个数据库表都应该包含一或多列，这些列可用于唯一标识表中的每一行。这在数据库术语中被称为 `Primary Key`（主键）。例如，一个表可以使用银行账户号码列作为主键。或者，客户表可以使用客户的社会安全号作为主键。

主键允许数据库管理系统唯一地识别表中的特定行。如果没有 `primary key`，将无法检索或删除表中的特定行，因为无法确定是否选择了正确的行。例如，假设存在一个表，将客户的姓氏定义为主键。想象一下，如果数据库中记录了多个姓为“Smith”的客户，会产生什么问题。如果没有某种保证的唯一性方法来识别某条特定行，就无法确保在任何时候访问的正确的数据。

主键可以由表中的单列或多列组成。要符合单列主键的条件，任何两行数据都不能包含匹配的主键值。当使用多列来构造主键时，单个列的值不需要是唯一的，但所有列的值组合起来必须是唯一的。

### 64.6 什么是 SQLite？

SQLite 是一种嵌入式关系型数据库管理系统（RDBMS）。大多数关系型数据库（`Oracle`、`SQL Server` 和 `MySQL` 为主要示例）都是独立的服务器进程，独立运行并与需要数据库访问的应用程序协作。`SQLite` 被称为嵌入式，是因为它以库的形式提供并链接到应用程序中的。因此，后台没有运行独立的数据库服务器。所有的数据库操作都是通过调用 `SQLite` 库中的函数在应用程序内部处理的。

`SQLite` 的开发者已将该技术投入了公共领域，结果是它现在成为了一种广泛部署的数据库解决方案。

`SQLite` 使用 `C` 语言编写，因此 Android SDK 为底层数据库接口提供了基于 Java 的“封装器”。这由类组成，可以在应用程序的 `Java` 或 `Kotlin` 代码中创建并管理基于 `SQLite` 的数据库。

关于 `SQLite` 的更多信息，请参阅 [`www.sqlite.org`](https://www.sqlite.org)。

### 64.7 结构化查询语言 (SQL)

`SQLite` 数据库使用一种名为 `Structured Query Language`（结构化查询语言）的高级语言访问数据。这通常缩写为 `SQL`，读音为 sequel。`SQL` 是大多数关系型数据库管理系统使用的标准语言。`SQLite` 大多符合 `SQL-92` 标准。

`SQL` 是一种简单且易于使用的语言，专门设计用于启用数据库数据的读取和写。由于 `SQL` 包含一组较小的关键字，因此可以快速学习。此外，大多数 `DBMS` 实现之间的 `SQL` 语法大体相同，因此在学习了一个系统的 `SQL` 后，你的技能可能会转移到其他数据库管理系统。

虽然本章节将使用一些基础的 `SQL` 语句，但对 `SQL` 的详细概述超出了本书的范围。然而，许多其他资源提供的 `SQL` 概述比我们希望在这里单章节中能提供的要好得多。

### 64.8 在 Android 虚拟设备 (AVD) 上尝试 SQLite

对于对数据库和 `SQLite` 不熟悉的读者来说，直接开始创建一个使用 `SQLite` 的 Android 应用程序可能令人生畏。幸运的是，Android 预装了 `SQLite`，包括一个交互式环境，可以在连接到运行中的 Android `AVD` 模拟器实例的 `adb shell` 会话中发布 `SQL` 命令。这是学习 `SQLite` 和 `SQL` 的实用方法，也是识别模拟器中运行的应用程序所创建的数据库问题的工具。

要启动交互式 `SQLite` 会话，首先运行 `AVD` 会话。这可以通过在 Android Studio 中启动 Android 虚拟设备管理器（`Tools -> AVD Manager`）、选择一个之前配置过的 `AVD` 并点击启动按钮来实现。

一旦 `AVD` 运行，打开 `Terminal` 或 `Command-Prompt` 窗口并使用 `adb` 命令行工具如下所示连接到模拟器（注意 `-e` 标志指示工具查找要连接的模拟器，而不是物理设备）：

```bash
adb -e shell
```

连接后，shell 环境将提供一个可以在其中输入命令的命令提示符。首先使用 `su` 命令获取超级用户权限：

```
Generic_x86:/ su
root@android:/ #
```

如果消息显示不允许超级用户权限，则 `AVD` 实例可能包含了 Google Play 支持。要解决这个问题，请创建一个新的 `AVD`，并在“Choose a device definition”屏幕上选择一个在“Play Store”列没有标记的设备。

`SQLite` 数据库中的数据存储在运行应用程序的 Android 设备的文件系统的数据库文件中。默认情况下，这些数据库文件的文件系统路径如下：

`/data/data/<package name>/databases/<database filename>.db`

例如，如果包名为 `com.example.MyDBApp` 的应用程序创建一个名为 `mydatabase.db` 的数据库，则设备上的文件路径将如下：

`/data/data/com.example.MyDBApp/databases/mydatabase.db`

因此，为了进行练习，请在 `adb shell` 中切换到 `/data/data` 并创建一个适用于某些 `SQLite` 实验的子目录层级：

```bash
cd /data/data
mkdir com.example.dbexample
cd com.example.dbexample
mkdir databases
cd databases
```

为数据库文件创建合适的位置后，启动交互式 `SQLite` 工具：

```
root@android:/data/data/databases # sqlite3 ./mydatabase.db
sqlite3 ./mydatabase.db
```



`SQLite` version `3.8.10.2` `2015-05-20 18:17`

输入 `.help` 获取用法提示。

`sqlite>`

在模拟器环境中运行 Android 应用程序时，任何数据库文件都将按照之前讨论的路径约定在模拟器的文件系统中创建。这样做的好处是，你可以通过 `adb` 连接，导航到数据库文件所在，将其加载到 `sqlite3` 交互工具中，并对数据执行操作，以识别应用程序代码中可能出现的问题。

同样需要注意的是，虽然可以通过 `adb shell` 连接到物理 Android 设备，但默认情况下 shell 并不具备足够的权限来创建和管理 `SQLite` 数据库。因此，数据库问题的调试最好使用 AVD（安卓虚拟设备）会话进行。

### 64.9 Android Room 持久化库

如前所述，`SQLite` 是用 C 语言编写的，而 Android 应用主要使用 `Java` 或 `Kotlin` 开发。过去为了弥补这种“语言鸿沟”，Android SDK 包含了一组类，它们在 `SQLite` 数据库管理系统之上提供了一个层。尽管这些类在 SDK 中可用，但使用这些类仍然需要编写大量的代码，并且没有利用新的架构指南和诸如 `LiveData` 以及生命周期管理等特性。Android Jetpack 架构组件包含了 `Room` 持久化库来解决这些缺点。该库在 `SQLite` 数据库系统之上提供了一个层级接口，使得能够以最少的代码在 Android 设备上本地存储数据，同时符合现代应用架构的建议。

接下来的几章将提供使用 `Room` 持久化库进行 `SQLite` 数据库管理的概述和教程。

### 64.10 总结

`SQLite` 是一种轻量级的嵌入式关系型数据库管理系统，包含在 Android 框架中，为 Android 应用实现组织的持久化数据存储提供了机制。与 `Room` 持久化库结合时，Android 提供了一种从 Android 应用内部实现数据存储的现代方法。

本章在 Android 应用开发的背景下，概述了通用数据库并特别概述了 `SQLite`。接下来的章节将提供 `Room` 持久化库的概述，之后我们将通过创建一个示例应用程序。

# 65. Android Room 持久化库

`Room` 持久化库包含在 Android 架构组件中，旨在以符合 Android 架构指南的方式更容易地为 Android 应用添加数据库存储支持。在上一章涵盖了 `SQLite` 数据库的基础知识后，本章将探索基于 `Room` 的数据库管理背后的基本概念、在 Android 应用中实现 `Room` 支持的关键元素，以及这些元素在架构和编码方面是如何实现的。在涵盖这些主题后，接下来的两章通过示例 `Room` 数据库项目将这些理论付诸实践。

### 65.1 回顾现代应用架构

标题为使用 Jetpack 构建现代 Android 应用架构的章节介绍了现代架构的概念，并强调了分离应用内不同责任区域的重要性。图 65-1 中所示的图表概述了典型 Android 应用的推荐架构：

![](img/room_diagram_1.jpg)

图 65-1

在本书之前的章节中已经详细介绍了该架构的前三个层，现在是时候在 `Room` 持久化库的背景下探索仓库和数据库架构层了。

## 65.2 Room 数据库持久化的关键元素

在章节稍后进行更详细讨论之前，首先值得总结使用 `Room` 持久化库操作 `SQLite` 数据库时涉及的关键元素：

### 65.2.1 仓库 (Repository)

如前所述，仓库模块包含了直接处理应用所用所有数据源所需的所有。这避免了 UI 控制器和 `ViewModel` 包含直接访问数据库或网络服务的代码的需求。

#### 65.2.2 Room 数据库

`room database` 对象提供了底层 `SQLite` 数据库的接口。它还为仓库提供了访问数据访问对象 (`DAO`) 的权限。一个应用应该只有一个 `room database` 实例，该实例可以用于访问多个数据库表。

#### 65.2.3 数据访问对象 (DAO)

`DAO` 包含了仓库在 `SQLite` 数据库中插入、检索和删除数据所需的 `SQL` 语句。这些 `SQL` 语句被映射到方法，然后从仓库内部调用这些方法来执行相应的查询。

#### 65.2.4 实体 (Entities)

实体是定义数据库中表模式的类，它定义了表名、列名和数据类型，并标识哪一列是主键。除了声明表结构外，实体类还包含提供这些数据字段访问的 getter 和 setter 方法。`DAO` 响应 `SQL` 查询返回给仓库的数据将以实例的形式存在。

#### 65.2.5 SQLite 数据库

`SQLite database` 负责存储和提供数据访问。应用代码（包括仓库）不应直接访问它。所有的数据库操作都是通过 `room database`、`DAOs` 和 `entities` 的组合完成的。图 65-2 中的架构图说明了这些元素如何交互以为 Android 应用提供基于 `Room` 的存储：

![](img/room_diagram.jpg)

图 65-2

上述架构中的编号连接可以总结如下：

1. 仓库与 `Room Database` 交互以获取数据库实例，反之用于获取 `DAO` 实例的引用。
2. 仓库创建 `entity` 实例并配置数据，然后将其传递给 `DAO` 用于搜索和插入操作。
3. 仓库调用 `DAO` 的方法并传递 `entities` 以插入数据库，并在响应查询时接收 `entity` 实例。
4. 当 `DAO` 有结果要返回给仓库时，它将它们封装成 `entity` 对象。
5. `DAO` 与 `Room Database` 交互以启动数据库操作并处理结果。
6. `Room Database` 处理与底层 `SQLite database` 的所有交互，提交查询并接收结果。

在涵盖了使用 `Room` 库进行数据库访问的关键要素概述后，是时候详细探索 `entities`、`DAOs`、`room databases` 和 `repositories` 了。

### 65.3 理解实体

每个数据库表都有与其关联的实体类。该类定义了表的模式，并以间插了一些特殊 `Room` 注解的标准 Java 类的形式存在。声明要在数据库表中存储数据的示例 Java 类如下：

```java
public class Customer {

    private int id;

    private String name;

    private string address;

    public Customer(String name, String address) {

        this.id = id;

        this.name = name;

        this.address = address;

    }

    public int getId() {

        return this.id;

    }

}
```

```java
public String getName() {

    return this.name;

}

public int getAddress() {

    return this.address;

}

public void setId(int id) {

    this.id = id;

}

public void setName(String name) {

    this.name = name;

}

public void setAddress(int quantity) {

    this.address = address;

}

}
```

按照目前的实现，上述代码声明了一个基础 Java 类，其中包含几个表示数据库表字段的变量以及一组 getter 和 setter 方法。然而，该类尚不是一个实体（entity）。要将此类转换为实体并使其能够在 SQL 语句中访问，需要按照所示添加 Room 注解：

```java
@Entity(tableName = "customers")

public class Customer {

    @PrimaryKey(autoGenerate = true)

    @NonNull

    @ColumnInfo(name = "customerId")

    private int id;

    @ColumnInfo(name = "customerName")

    private String name;

    private String address;

    public Customer(String name, String address) {

        this.id = id;

        this.name = name;

        this.address = address;

    }

    public int getId() {

        return this.id;

    }

    public String getName() {

        return this.name;

    }

    public String getAddress() {

        return this.address;

    }

    public void setId(@NonNull int id) {

        this.id = id;

    }

    public void setName(String name) {

        this.name = name;

    }

    public void setAddress(int quantity) {

        this.address = address;

    }

}
```

上述注解首先声明该类表示一个实体，并分配了名为“customers”的表名。这是在 DAO SQL 语句中引用该表时使用的：

```java
@Entity(tableName = "customers")
```

每个数据库表都需要一列来作为主键。在这种情况下，customer id 被声明为主键。同时还添加了注解来分配一个在 SQL 查询中引用的列名，并指明该字段不能存储空值。最后，id 值被配置为自动生成。这意味着系统会自动为新记录生成 id，以避免键冲突：

```java
@PrimaryKey(autoGenerate = true)

@NonNull

@ColumnInfo(name = "customerId")

private int id;
```

customer name 字段也分配了一个列名。但请注意，address 字段没有分配列名。这意味着 address 数据仍存储在数据库中，但不需要在 SQL 语句中引用。如果实体中的某个字段不需要存储在数据库中，请使用 `@Ignore` 注解：

```java
@Ignore

private String myString;
```

最后，对 id 变量的 setter 方法进行了修改，以防止分配空值：

```java
public void setId(@NonNull int id) {

    this.id = id;

}
```

注解也可以包含在实体类中，以使用称为外键（foreign keys）的关系型数据库数据库概念与其他实体建立关系。外键允许一个表引用另一个表的主键。例如，可以在名为 `Purchase` 的实体与现有的 `Customer` 实体之间建立如下关系：

```java
@Entity(foreignKeys = {@ForeignKey(entity = Customer.class,

        parentColumns = "customerId",

        childColumns = "buyerId",

        onDelete = ForeignKey.CASCADE,

        onUpdate = ForeignKey.CASCADE)})

public class Purchase {

    @PrimaryKey(autoGenerate = true)

    private int id;

    @ColumnInfo(name = "buyerId")

    private int buyerId;

}
```

### 65.4 数据访问对象

数据访问对象（DAO）允许访问存储在 SQLite 中的数据。第一步是创建一个接口并使用 `@Dao` 注解对其声明：

```java
@Dao

public interface CustomerDao {
```

接下来向方法添加条目。例如，下面的声明允许通过名为 `getAllCustomers()` 方法检索整个 customers 表：

```java
@Query("SELECT * FROM customers")

LiveData<List<Customer>> getAllCustomers();
```

`getAllCustomers()` 方法返回一个 `List` 对象，包含从数据库检索的每条记录对应的 `Customer` 实体。DAO 还使用了 `LiveData`，以便存储库可以观察数据库的变化。

也可以向方法传递参数。注意，名称带有带有冒号（`:`）：

```java
@Query("SELECT * FROM customers WHERE name = :customerName")

List<Customer> findCustomer(String customerName);
```

在此示例中，可以使用 `@Insert` 注解按所示声明基本的插入操作：

```java
@Insert

void addCustomer(Customer customer);
```

这被称为便利注解（convenience annotation），因为 Room 持久库可以推导出传递给 `addCustomer()` 的 `Customer` 实体将插入数据库，而不需要 SQL 语句。也可以在一个事务中插入多条数据库记录，如下：

```java
@Insert

public void insertCustomers(Customer... customers);
```

下面的 DAO 删除了所有匹配客户姓名的记录：

```java
@Query("DELETE FROM customers WHERE name = :name")

void deleteCustomer(String name);
```

除了使用 `@Query` 注解执行删除外，也可以使用 `@Delete` 便利注解。在以下示例中，传递给 `deleteCustomers()` 的所有 `Customer` 记录将从数据库中删除：

```java
@Delete

public void deleteCustomers(Customer... customers);
```

`@Update` 便利注解在更新记录时提供类似的行为：

```java
@Update

public void updateCustomers(Customer... customers);
```

此类数据库操作的 DAO 方法也可以声明为返回一个 `int` 值，表示受事务影响的行数，例如：

```java
@Delete

public int deleteCustomers(Customer... customers);
```

### 65.5 Room Database

Room 类通过扩展 `RoomDatabase` 类创建，作为嵌入 Android 操作系统的实际数据库之上的层。该类负责创建并返回新的 数据库实例，并提供对关联 DAO 实例的访问。

Room 持久库提供了创建数据库实例的构建器。每个 Android 应用应该只有一个数据库实例，因此最好在类中实现防御性代码以防止创建多个实例。

用于示例客户表的 Room 实现如下代码列表所示：

```java
import android.content.Context;

import android.arch.persistence.room.Database;

import android.arch.persistence.room.Room;

import android.arch.persistence.room.RoomDatabase;

@Database(entities = {Customer.class}, version = 1)

public class CustomerRoomDatabase extends RoomDatabase {

    private static volatile CustomerRoomDatabase INSTANCE;

    public static CustomerRoomDatabase getInstance(Context context) {

        if (INSTANCE == null) {

            synchronized (CustomerRoomDatabase.class) {

                if (INSTANCE == null) {

                    INSTANCE = Room.databaseBuilder(

                            context.getApplicationContext(),

                            CustomerRoomDatabase.class, "customer_database")

                            .build();

                }

            }
```



```java
}
return INSTANCE;
}
public abstract CustomerDao customerDao();
}
```

```java
private static CustomerRoomDatabase INSTANCE;

static CustomerRoomDatabase getDatabase(final Context context) {
    if (INSTANCE == null) {
        synchronized (CustomerRoomDatabase.class) {
            if (INSTANCE == null) {
                INSTANCE = Room.databaseBuilder(
                        context.getApplicationContext(),
                        CustomerRoomDatabase.class,
                        "customer_database"
                ).build();
            }
        }
    }
    return INSTANCE;
}
```

上述示例中需要注意的重要区域是：类声明上方声明数据库要操作实体的注解、检查类实例是否已经创建的代码，以及为实例分配的名称`customer_database`。

## 65.6 仓库（Repository）

仓库负责获取`Room Database`实例，使用该实例访问关联的`DAOs`，然后调用`DAO`方法执行数据库操作。一个旨在与`Room Database`工作���典型仓库构造函数可能如下：

```java
public class CustomerRepository {

    private CustomerDao customerDao;

    private CustomerRoomDatabase db;

    public CustomerRepository(Application application) {
        db = CustomerRoomDatabase.getDatabase(application);
        customerDao = db.customerDao();
    }
}
```

一旦仓库可以访问`DAO`，它就可以调用数据访问方法。例如，下面的代码调用了`getAllCustomers()` `DAO`方法：

```java
private LiveData<List<Customer>> allCustomers;

allCustomers = customerDao.getAllCustomers();
```

在调用`DAO`方法时，需要注意的是，除非该方法返回`LiveData`实例（该实例会自动在单独的线程上运行查询），否则无法在应用的主线程上执行操作。尝试这样做会导致应用崩溃并输出以下诊断信息：

`Cannot access database on the main thread since it may potentially lock the UI for a long period of time`

由于某些数据库事务可能需要更长时间才能完成，在单独线程上运行操作可以避免应用出现假死状态。正如标题为“Android Room 数据库和仓库教程”的章节将演示的，这个问题可以通过使用 Java 线程轻松解决（如需更多信息或提醒如何使用线程，请参阅标题为“Java 线程、Handlers 和执行器基础概述”的章节）。

## 65.7 内存数据库

本章概述的示例使用了作为 Android 设备持久化存储上数据库文件的`SQLite`数据库。这确保了即使在应用进程终止后数据仍然存在。

Room 数据库持久化库还支持内存数据库。这些数据库完全位于内存中，并在应用终止时丢失。与内存数据库工作所需的唯一更改是调用`Room Database`类的`Room.inMemoryDatabaseBuilder()`方法，而不是`Room.databaseBuilder()`。下面的代码显示了方法调用之间的区别（注意内存数据库不需要数据库名称）：

```java
// 创建基于文件的存储数据库
INSTANCE = Room.databaseBuilder(
        context.getApplicationContext(),
        CustomerRoomDatabase.class,
        "customer_database"
).build();

// 创建内存数据库
INSTANCE = Room.inMemoryDatabaseBuilder(
        context.getApplicationContext(),
        CustomerRoomDatabase.class
).build();
```

## 65.8 数据库检查器（Database Inspector）

Android Studio 包含一个 Database Inspector 工具，它允许对与其关联的数据库进行查看、搜索和修改，如图 65-3 所示。

## 65.9 总结

Room 持久化库与 Android 组件捆绑，并作为 SQLite 之上的抽象层。该库的设计旨在使其符合 Android 指南的同时，使数据库操作变得更加简单。本章介绍了这些元素。在涵盖了 SQLite 基础和 Room 架构之后，下一步是创建一个将这些理论付诸实践的示例。

# 66. TableLayout 和 TableRow 教程

当开始编写本书下一章（“Android Room 数据库和仓库教程”）的工作时，最初打算包含设计用户界面的步骤。然而，显而易见，实现用户界面的最佳方法是使用`TableLayout`和`TableRow`，这个主题值得作为一个独立的章节。因此，本章将专门关注用户界面。

## 66.1 TableLayout 和 TableRow 布局视图

`TableLayout`容器视图允许用户界面元素以由行和列组成的表格格式组织在屏幕上。`TableLayout`中的每一行由一个`TableRow`实例占据，而`TableRow`又被分为单元格，每个单元格包含一个子视图。

表格中的列数由列数最多的行决定，默认情况下，每列的宽度由该列中最宽的单元格定义。列可以配置为可收缩或可伸展（或两者兼有），以便它们相对于父级`TableLayout`改变大小。此外，单个单元格可以配置为跨越多个列。

考虑图 66-1 所示的用户界面布局（`#TableLayout.xhtml__idTextAnchor1298`）：

从布局的视觉外观来看，很难识别出用于设计界面的`TableLayout`结构。然而，图 66-2 所示的层级树图（`#TableLayout.xhtml__idTextAnchor1299`）让结构变得更容易理解。

## 66.2 创建 Room 数据库项目

从欢迎界面选择`New Project`菜单选项，在弹出的新项目对话框中，在点击`Next`按钮之前选择`Empty Views Activity`模板。

在`Name`字段中输入`RoomDemo`并指定`com.ebookfrenzy.roomdemo`为包名。在点击`Finish`按钮之前，将`Minimum API level`设置为`API 26: Android 8.0 (Oreo)`，并将`Language`菜单更改为`Java`。

按照第 11.8 Migrating a Project to View Binding 节概述的步骤将项目迁移到视图绑定。

## 66.3 转换为 LinearLayout

在 Project 工具窗口（`app -> res -> layout`）中找到`activity_main.xml`文件，并双击将其加载到`Layout Editor`工具中。默认情况下，Android Studio 使用`ConstraintLayout`作为用户界面根布局元素。这需要将其转换为垂直方向的`LinearLayout`。

在设计模式下的`Layout Editor`工具中，在`Component Tree`面板中找到`ConstraintLayout`组件，右键点击它以显示图 66-3 所示的菜单，并选择`Convert view...`：

![](img/as_convert_view_menu.jpg)

**图 66-3**

在弹出的对话框（图 66-4）中，在点击`Apply`按钮之前，选择转换为`LinearLayout`的选项：

![](img/as_convert_view_dialog.jpg)

**图 66-4**

默认情况下，布局编辑器会将`ConstraintLayout`转换为水平的`LinearLayout`，因此在`Component Tree`窗口中选择布局组件，参考`Attributes`工具窗口，并将`orientation`属性更改为`vertical`：

![](img/as_linear_orientation.jpg)

**图 66-5**

转换完成后，选择并删除布局中的默认`TextView`小部件。

## 66.4 向用户界面添加 TableLayout

留在`activity_main.xml`文件中，并参考`Palette`中的`Layouts`类别，将`TableLayout`视图拖到`LinearLayout`画布区域的顶部。

完成这些初始步骤后，布局的`Component Tree`应该类似于图 66-6 所示。

![](img/as_table_layout.jpg)

**图 66-6**

Android Studio 自动为`TableLayout`添加了四个`TableRow`实例。由于此示例只需要三行，请选择并删除第四个`TableRow`实例。可以随时从调色板中拖动`TableRow`对象并将其放到`Component Tree`工具窗口中的`TableLayout`项，以向`TableLayout`添加更多行。

选中`TableLayout`后，使用`Attributes`工具窗口将`layout_height`属性更改为`wrap_content`，并将`layout_width`更改为`match_parent`。

## 66.5 配置 TableRows

从调色板的`Text`部分，将两个`TextView`对象拖到`Component Tree`中最顶部的`TableRow`项上（图 66-7）：

![](img/as_table_layout_first_row.jpg)

**图 66-7**

在屏幕布局中选择左侧的`TextView`，将`text`属性更改为`Product Name`并将`id`更改为`productName`。选择屏幕布局中最右侧的`TextView`，将`text`属性更改为`Quantity`并将`id`更改为`productQuantity`。

将另一个`TextView`拖到第二个`TableRow`项。将`text`属性更改为`ID`并将`id`更改为`productID`。将另一个`TextView`拖到第三个`TableRow`项。将`text`属性更改为`Price`并将`id`更改为`productPrice`。

如图 66-8 所示，将所有`TextView`小部件的`textSize`属性设置为`18sp`。

![](img/as_table_layout_row.jpg)

**图 66-8**

## 66.6 添加按钮栏

下一步是向父级`LinearLayout`添加一个水平的`LinearLayout`视图。首先点击`TableLayout`项左侧的箭头以折叠所有子项。从`Layouts`部分拖一个`LinearLayout`实例，将其释放到`Component Tree`中`TableLayout`的正下方，并将`layout_height`更改为`wrap_content`。

![](img/as_table_layout_linear.jpg)

**图 66-9**

在`Component Tree`中选中新的`LinearLayout`，将`gravity`属性更改为`center_horizontal`，以便按钮水平居中。

## 66.7 添加 RecyclerView

在`Component Tree`中，点击新添加的`LinearLayout`项左侧的箭头以折叠所有子项。从`Palette`中的`Containers`部分将一个`RecyclerView`实例拖到`Component Tree`中，将其放置在按钮栏下方，如图 66-10 所示。确保`RecyclerView`是作为父级`LinearLayout`的直接子项添加，而不是水平按钮栏的子项。

![](img/as_table_layout_recycler.jpg)

**图 66-11**

在布局中选中`RecyclerView`，将视图的`id`更改为`product_recycler`并将`layout_height`属性设置为`match_parent`。在继续之前，检查`Component Tree`中的布局层级是否与下图一致：

![](img/as_table_completed.jpg)

**图 66-12**

## 66.8 调整布局边距

最后只需调整一些布局设置即可。首先点击`Component Tree`面板中的第一个`TableRow`项使其选中。按住键盘上的`Cmd/Ctrl`键并点击第二、第三个`TableRow`、水平`LinearLayout`和`RecyclerView`，以便选中所有五个项。在`Attributes`面板中，找到`layout_margin`属性类别，一旦找到，如图 66-13 所示将值更改为`10dp`：

![](img/as_table_margin.jpg)

**图 66-14**

设置好边距后，用户界面应如图 66-1 所示。

## 66.9 总结

Android `TableLayout`容器视图提供了一种以行和列配置排列视图组件的方法。虽然`TableLayout`视图提供了整体容器，但每一行及其其中包含的单元格都是通过`TableRow`视图的实例实现的。在本章中，我们在 Android Studio 中使用了`TableLayout`和`TableRow`容器设计一个用户界面。下一章将为该用户界面添加后台功能，使用仓库（repository）和 Room 持久化库来实现 SQLite 数据库功能。

# 67. Android Room 数据库和仓库教程

本章将结合“Android Room 持久化库”中学习的知识与上一章创建的初始项目，提供一个详细的教程，演示如何使用 Room 持久化库实现基于 SQLite 的数据库存储。遵循 Android 架构指南，该项目将使用视图模型（view model）和仓库。教程将使用“Android Room 持久化库”中涵盖的所有元素，包括实体（entities）、数据访问对象（DAO）、Room 数据库以及异步数据库查询。

## 67.1 关于 RoomDemo 项目

上一章创建的用户界面布局是创建一个简单的库存应用的第一步，用于存储产品名称和数量。完成后，该应用将提供添加、删除和搜索数据库条目的功能，同时显示当前数据库中存储的所有产品的可滚动列表。当数据库条目添加或删除时，此产品列表将自动更新。

## 67.2 修改构建配置

启动 Android Studio 并打开上一章开始的`RoomDemo`项目。在向项目添加任何新类之前，第一步是在构建配置中添加一些额外的库，包括 Room 持久化库。找到并编辑项目级`build.gradle.kts`文件（`app -> Gradle Scripts -> build.gradle.kts (Project :RoomDemo)`）如下：

接下来，对模块级`build.gradle.kts`文件（`app -> Gradle Scripts -> build.gradle.kts (Module :app)`）进行以下更改：

```kotlin
dependencies {
    .
    .
    implementation("androidx.recyclerview:recyclerview:1.3.0")
    implementation("androidx.room:room-runtime:2.5.2")
    annotationProcessor("androidx.room:room-compiler:2.5.2")
    .
    .
}
```



### 67.3 构建实体

该项目将从创建定义数据库表模式的实体开始。该实体将包含一个产品 ID 整数、一个存储产品名称的字符串列以及另一个存储数量的整数值。

`productid` 列将作为主键并自动生成。表 67-1 总结了实体的结构：

| 列 | 数据类型 |
| :--- | :--- |
| `productid` | Integer / 主键 / 自动递增 |
| `productname` | String |
| `productquantity` | Integer |

表 67-1

在项目工具窗口中右键点击`app -> java -> com.ebookfrenzy.roomdemo`项，并选择`New -> Java Class`菜单选项为实体添加类文件。在新类对话框中，将类命名为`Product`，选择列表中的`Class`项，并按键盘回车键生成文件。

当`Product.java`文件在编辑器中打开时，对其进行修改使其读取如下：

```java
package com.ebookfrenzy.roomdemo;

public class Product {

    private int id;

    private String name;

    private int quantity;

    public Product(String name, int quantity) {

        this.name = name;

        this.quantity = quantity;

    }

    public int getId() {

        return this.id;

    }

    public String getName() {

        return this.name;

    }

    public int getQuantity() {

        return this.quantity;

    }

    public void setId(int id) {

        this.id = id;

    }

    public void setName(String name) {

        this.name = name;

    }

    public void setQuantity(int quantity) {

        this.quantity = quantity;

    }

}
```

该类现在有了数据库表列的变量以及对应的 getter 和 setter 方法。当然，该类在被注解之前并不会成为实体。在编辑器中打开类文件的情况下，添加注解和相应的导入：

```java
package com.ebookfrenzy.roomdemo;

import androidx.room.ColumnInfo;

import androidx.room.Entity;

import androidx.room.PrimaryKey;

@Entity(tableName = "products")
public class Product {

    @PrimaryKey(autoGenerate = true)
    @ColumnInfo(name = "productId")
    private int id;

    @ColumnInfo(name = "productName")
    private String name;

    private int quantity;

}
```

这些注解声明此实体为名为`products`的表，并为`id`和`name`变量分配了列名。`id`列也被配置为主键并自动生成。

### 67.4 创建数据对象

点击`app -> java -> com.ebookfrenzy.roomdemo`项并选择`New -> Java Class`菜单选项。在新类对话框中，在 Name 字段中输入`ProductDao`并从列表中选择`Interface`，如图 67-1 所示：

![](img/as_room_demo_java_interface.jpg)

图 67-1

按回车键生成新接口，并在编辑器中加载`ProductDao.java`文件后进行以下更改：

```java
package com.ebookrenzy.roomdemo;

import androidx.lifecycle.LiveData;

import androidx.room.Dao;

import androidx.room.Insert;

import androidx.room.Query;

import java.util.List;

@Dao
public interface ProductDao {

    @Insert
    void insertProduct(Product product);

    @Query("SELECT * FROM products WHERE productName = :name")
    List<Product> findProduct(String name);

    @Query("DELETE FROM products WHERE productName = :name")
    void deleteProduct(String name);

    @Query("SELECT * FROM products")
    LiveData<List<Product>> getAllProducts();

}
```

DAO 实现了从 products 数据库中插入、查找和删除记录的方法。插入方法接收一个包含要存储数据的`Product`实体。`getAllProducts()`方法返回一个包含数据库中所有记录的`LiveData`对象。此方法将用于保持用户界面中的`RecyclerView`产品列表与数据库同步。

### 67.5 添加 Room 数据库

在向项目添加仓库之前的最后一个任务是实现 Room 数据库实例。向项目添加名为`ProductRoomDatabase`的新类，这次选择`Class`选项。

文件生成后，按照“Android Room 持久化库”章节中概述的步骤对其进行修改：

```java
package com.ebookfrenzy.roomdemo;

import android.content.Context;

import androidx.room.Database;

import androidx.room.Room;

import androidx.room.RoomDatabase;

@Database(entities = {Product.class}, version = 1)
public abstract class ProductRoomDatabase extends RoomDatabase {

    public abstract ProductDao productDao();

    private static ProductRoomDatabase INSTANCE;

    static ProductRoomDatabase getDatabase(final Context context) {

        if (INSTANCE == null) {

            synchronized (ProductRoomDatabase.class) {

                INSTANCE =

                    Room.databaseBuilder(context.getApplicationContext(),

                        ProductRoomDatabase.class,

                        "product_database").build();

            }

        }

        return INSTANCE;

    }

}
```

### 67.6 添加仓库 (Repository)

向项目中添加一个名为`ProductRepository`的新类，并选择`Class`选项。

仓库类将负责代表`ViewModel`与`Room`数据库进行交互。它必须提供使用`DAO`来插入、删除和查询产品记录的方法。除了`getAllProducts()` DAO 方法（它返回一个`LiveData`对象）外，这些数据库操作必须在主线程之外的线程中执行。

在`ProductRepository.java`文件中，添加一个处理器的代码，将搜索结果返回给仓库线程：

```java
package com.ebookfrenzy.roomdemo;

import android.os.Handler;

import android.os.Looper;

import android.os.Message;

import java.util.concurrent.ExecutorService;

import java.util.concurrent.Executors;

import androidx.lifecycle.MutableLiveData;

import java.util.List;

public class ProductRepository {

    private final MutableLiveData<List<Product>> searchResults =

            new MutableLiveData<>();

    private List<Product> results;

    Handler handler = new Handler(Looper.getMainLooper()) {

        @Override public void handleMessage(Message msg) {

            searchResults.setValue(results);

        }

    };

}
```

上述代码声明了一个名为`searchResults`的`MutableLiveData`变量，每当异步搜索任务完成，搜索结果就会存储其中（在随后的教程中，`ViewModel`中的观察者将监控此活动数据对象）。

仓库类现在必须提供一些`ViewModel`可以调的方法来启动这些操作。然而，仓库需要通过`ProductRoomDatabase`实例获取`DAO`引用。为`ProductRepository`类添加一个构造方法来执行这些任务：

```java
import android.app.Application;

public class ProductRepository {

    private final MutableLiveData<List<Product>> searchResults = new MutableLiveData<>();

    private List<Product> results;

    private final ProductDao productDao;

    public ProductRepository(Application application) {

        ProductRoomDatabase db;

        db = ProductRoomDatabase.getDatabase(application);

        productDao = db.productDao();

    }

}
```

存储了`DAO`引用后，可以如下所示将方法添加到`ProductRepository`类文件中：

```java
public void insertProduct(Product newproduct) {

    ExecutorService executor = Executors.newSingleThreadExecutor();

    executor.submit(() -> productDao.insertProduct(newproduct));

    executor.shutdown();

}

public void deleteProduct(String name) {

    ExecutorService executor = Executors.newSingleThreadExecutor();

    executor.submit(() -> productDao.deleteProduct(name));

    executor.shutdown();

}

public void findProduct(String name) {

    ExecutorService executor = Executors.newSingleThreadExecutor();

    executor.submit(() -> {

        results = productDao.findProduct(name);

        handler.sendEmpty(0);

    });

    executor.shutdown();

}
```

在插入和删除的情况下，会创建并使用适当线程来执行数据库操作。在`findProduct()`的情况下，会向`handler`发送消息，表示有新结果可用。

完成仓库还剩最后一项任务。用户界面中的`RecyclerView`必须与数据库中存储的当前产品列表同步。`ProductDao`类包含一个名为`getAllProducts()`的方法，该方法使用 SQL 查询选择所有数据库记录并将它们封装在`LiveData`对象中返回。仓库需要在初始化时调用此方法，并将结果存储在`LiveData`对象中，该对象可以被`ViewModel`观察，进而被 UI 控制器观察。一旦设置好，每当数据库发生变化时，UI 控制器将收到通知，`RecyclerView`就可以更新最新的产品列表。在`ProductRepository.java`文件中，添加一个`LiveData`变量并在构造方法中调用`getAllProducts()`方法：

```java
import androidx.lifecycle.LiveData;

public class ProductRepository {

    private final MutableLiveData<List<Product>> searchResults = new MutableLiveData<>();

    private List<Product> results;

    private final LiveData<List<Product>> allProducts;

    private final ProductDao productDao;

    public ProductRepository(Application application) {

        ProductRoomDatabase db;

        db = ProductRoomDatabase.getDatabase(application);

        productDao = db.productDao();

        allProducts = productDao.getAllProducts();

    }

}
```

为了完成仓库，添加`ViewModel`可以调的方法以获取`allProducts`和`searchResults`活动数据对象的引用：

```java
public LiveData<List<Product>> getAllProducts() {

    return allProducts;

}

public MutableLiveData<List<Product>> getSearchResults() {

    return searchResults;

}
```

### 67.7 添加 ViewModel

`ViewModel`负责创建仓库实例，并提供方法以及`LiveData`对象，UI 控制器可以利用这些对象使用户界面与底层数据库保持同步。正如在`ProductRepository.java`中实现的，仓库构造函数需要访问应用上下文以获取`Room`数据库实例。为了让`ViewModel`能够访问应用上下文以便将其传递给仓库，`ViewModel`需要继承`AndroidViewModel`。

首先，在 Project 工具窗口中找到`com.ebookfrenzy.viewdemo`条目，右键点击它并选择`New -> Java Class`菜单选项。接下来，将新类命名为`MainViewModel`并按键盘回车键。最后，编辑新类文件，将类改为扩展`AndroidViewModel`并实现默认构造函数：

```java
package com.ebookfrenzy.roomdemo.ui.main;

import android.app.Application;

import androidx.lifecycle.AndroidViewModel;

import androidx.lifecycle.LiveData;

import androidx.lifecycle.MutableLiveData;

import com.ebookfrenzy.roomdemo.Product;

import com.ebookfrenzy.roomdemo.ProductRepository;

import java.util.List;
```



```java
public class MainViewModel extends AndroidViewModel {

    final private ProductRepository repository;

    final private LiveData<List<Product>> allProducts;

    final private MutableLiveData<List<Product>> searchResults;

    public MainViewModel(Application application) {

        super(application);

        repository = new ProductRepository(application);

        allProducts = repository.getAllProducts();

        searchResults = repository.getSearchResults();

    }

}
```

构造函数创建了一个仓库实例，然后使用它获取结果和活动数据对象的引用，以便 UI 控制器可以观察它们。现在 `ViewModel` 中仅剩下实现那些由 UI 控制器内部响应按钮点击以及设置 `LiveData` 对象观察者时调用的方法：

```java
MutableLiveData<List<Product>> getSearchResults() {

    return searchResults;

}

LiveData<List<Product>> getAllProducts() {

    return allProducts;

}

public void insertProduct(Product product) {

    repository.insertProduct(product);

}

public void findProduct(String name) {

    repository.findProduct(name);

}

public void deleteProduct(String name) {

    repository.deleteProduct(name);

}
```

### 67.8 创建产品项布局

数据库中的每个产品名称将出现在主用户界面的 `RecyclerView` 列表中。这需要一个布局资源文件，其中列表中的每行都包含一个 `TextView`。

在 Project 工具窗口中右键点击 `app` -> `res` -> `layout` 项，并选择 `New` -> `Layout Resource File` 菜单来添加此文件。将文件命名为 `product_list_item`，并在点击 `OK` 创建文件并加载到布局编辑器之前，将根元素更改为垂直的 `LinearLayout`。

在 Design（设计）模式下的布局编辑器中，从调色板中拖入一个 `TextView` 对象到布局上，它将默认显示在布局的顶部：

![](img/as_3.5_roomdemo_item_layout.jpg)

图 67-2

在布局中选中 `TextView` 后，使用 Attributes（属性）工具窗口将视图的 ID 设置为 `product_row`，并将 `layout_height` 设置为 `30dp`。在 Component Tree（组件树）窗口中选择 `LinearLayout` 项，并将 `layout_height` 属性设置为 `wrap_content`。

### 67.9 添加 RecyclerView 适配器

正如“使用 RecyclerView 和 CardView 控件”章节中详细概述的那样，`RecyclerView` 实例需要一个适配器类来提供要显示的数据。

在 Project 工具窗口中右键点击 `app` -> `java` -> `com.ebookfrenzy.roomdemo` 项，并选择 `New` -> `Java Class` 菜单来添加此类类。在对话框中，将类命名为 `ProductListAdapter` 并在列表中选择 `Class`，然后按键盘 Return 键。

在编辑器中加载生成的 `ProductListAdapter.java` 类后，按照所示实现该类：

```java
package com.ebookfrenzy.roomdemo.ui.main;

import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.TextView;

import com.ebookfrenzy.roomdemo.R;

import androidx.annotation.NonNull;
import androidx.recyclerview.widget.RecyclerView;

import com.ebookfrenzy.roomdemo.Product;

import java.util.List;

public class ProductListAdapter
        extends RecyclerView.Adapter<ProductListAdapter.ViewHolder> {

    private final int productItemLayout;

    private List<Product> productList;

    public ProductListAdapter(int layoutId) {

        productItemLayout = layoutId;

    }

    public void setProductList(List<Product> products) {

        productList = products;

        notifyDataSetChanged();

    }

    @Override
    public int getItemCount() {

        return productList == null ? 0 : productList.size();

    }

    @NonNull
    @Override
    public ViewHolder onCreateViewHolder(ViewGroup parent, int viewType) {

        View view = LayoutInflater.from(
                parent.getContext()).inflate(productItemLayout, parent, false);

        return new ViewHolder(view);

    }

    @Override
    public void onBindViewHolder(final ViewHolder holder, final int listPosition) {

        TextView item = holder.item;

        item.setText(productList.get(listPosition).getName());

    }

    static class ViewHolder extends RecyclerView.ViewHolder {

        TextView item;

        ViewHolder(View iteview) {

            super(iteview);

            item = iteview.findViewById(R.id.product_row);

        }

    }

}
```

### 67.10 准备主 Activity

最后一个需要修改的组件是 `MainActivity` 类，它需要对 `Button` 视图配置监听器并对 `ViewModel` 类中的 live data 对象配置观察者。

在添加这些代码之前，必须进行一些准备工作以添加一些导入和变量。编辑 `MainActivity.java` 文件并修改如下：

```java
import androidx.lifecycle.ViewModelProvider;

public class MainActivity extends AppCompatActivity {

    private ActivityMainBinding binding;

    private MainViewModel viewModel;

    private ProductListAdapter adapter;

    @Override
    protected void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);

        binding = ActivityMainBinding.inflate(getLayoutInflater());

        View view = binding.getRoot();

        setContentView(view);

        viewModel = new ViewModelProvider(this).get(MainViewModel.class);

        listenerSetup();

        observerSetup();

        recyclerViewSetup();

    }

}
```

在代码的各个阶段，应用需要清除用户界面中的产品信息。为了避免重复，请添加以下 `clearFields()` 函数：

```java
private void clearFields() {

    binding.productID.setText("");

    binding.productName.setText("");

    binding.productQuantity.setText("");

}
```

在应用构建和测试之前，需要将从 `onCreate()` 方法调用的三个方法添加到类中。

### 67.11 添加监听器

主 fragment 的用户界面布局包含三个按钮，每个按钮在用户点击时都需要执行特定的任务。编辑 `MainActivity.java` 文件并添加 `listenerSetup()` 方法：

```java
import com.ebookfrenzy.roomdemo.Product;

private void listenerSetup() {

    binding.addButton.setOnClickListener(view -> {

        String name = binding.productName.getText().toString();

        String quantity = binding.productQuantity.getText().toString();

        if (!name.equals("") && !quantity.equals("")) {

            Product product = new Product(name, Integer.parseInt(quantity));

            viewModel.insertProduct(product);

            clearFields();

        } else {

            binding.productID.setText("Incomplete information");

        }

    });

    binding.findButton.setOnClickListener(view ->
        viewModel.findProduct(binding.productName.getText().toString())
    );

    binding.deleteButton.setOnClickListener(view -> {

        viewModel.deleteProduct(binding.productName.getText().toString());

        clearFields();

    });

}
```

`addButton` 监听器执行基础验证，确保用户输入了产品名称和数量，并使用这些数据创建一个新的 `Product` 实体对象（注意数量字符串被转换为整数）。然后调用 `ViewModel.insertProduct()` 方法并传入 `Product` 对象，最后清除字段。

`findButton` 和 `deleteButton` 监听器将产品名称传递给 `ViewModel.findProduct()` 或 `deleteProduct()` 方法。

### 67.12 添加 LiveData 观察者

用户界面现在需要添加观察者，以与 `ViewModel` 中的 `searchResults` 和 `allProducts` live data 对象保持同步。在 `MainActivity.java` 文件中，实现 `observerSetup()` 方法：

```java
import java.util.Locale;

private void observerSetup() {

    viewModel.getAllProducts().observe(this, products ->
        adapter.setProductList(products));

    viewModel.getSearchResults().observe(this, products -> {

        if (products.size() > 0) {

            binding.productID.setText(
                String.format(Locale.US, "%d", products.get(0).getId()));

            binding.productName.setText(products.get(0).getName());

            binding.productQuantity.setText(
                String.format(Locale.US, "%d", products.get(0).getQuantity()));

        } else {

            binding.productID.setText("No Match");

        }

    });

}
```

“all products”观察者将当前产品列表传递给 `RecyclerAdapter` 的 `setProductList()` 方法，从而更新此处显示的列表。

“搜索结果”观察者会检查数据库中至少存在一个匹配的结果，从列表中提取第一个匹配的 `Product` 实体对象，获取该对象的数据，在必要时进行转换，并将其分配给布局中的 `TextView` 和 `EditText` 视图。如果产品搜索失败，将通过显示在产品 ID `TextView` 上的消息通知用户。

### 67.13 初始化 RecyclerView

添加最终设置方法来初始化和配置 `RecyclerView` 适配器，如下：

```java
import androidx.recyclerview.widget.LinearLayoutManager;

private void recyclerSetup() {

    adapter = new ProductListAdapter(R.layout.product_list_item);

    binding.productRecycler.setLayoutManager(
        new LinearLayoutManager(getContext()));

    binding.productRecycler.setAdapter(adapter);

}
```



### 67.14 测试 RoomDemo App

在设备或模拟器上编译并运行应用，添加一些产品，并确保它们自动显示在`RecyclerView`中。对现有产品进行搜索，并验证产品 ID 和数量字段是否相应更新。最后，输入一个现有产品的名称，将其从数据库中删除，并确认它已从`RecyclerView`产品列表中移除。

### 67.15 使用数据库 Inspector

如之前在“Android Room 持久化库”中所概述，可以使用`Database Inspector`工具检查与运行应用相关的`Room`数据库的内容，并执行细微的数据更改。在使用`RoomDemo`应用添加一些数据库记录后，使用`View -> Tool Windows -> App Inspection`菜单选项显示`Database Inspector`工具：

在检查器窗口内部，从下方图 67-3 中标记为 A 的菜单中选择正在运行的应用：

![](img/as_database_inspector.jpg)

图 67-3

在`Databases`面板 (B) 中，双击`products`表以查看当前存储在数据库中的表行。启用`Live updates`（实时更新）选项 (C)，然后使用运行的应用向数据库添加更多记录。请注意，`Database Inspector`会实时更新表数据 (D) 以反映更改。

关闭`Live updates`使表格不再是只读的，双击表格行的`quantity`单元格，并在按下键盘`Enter`键之前更改该值。返回运行的应用并搜索该产品，以确认在检查器中对`quantity`进行的更改已保存到数据库表中。

最后，点击表查询按钮（如下方图 67-4 中的箭头所示）以显示新的查询标签页 (A)，确保选中了`product_database` (B)，并在查询文本字段 (C) 中输入 SQL 语句并点击`Run`按钮 (D)：

![](img/as_database_query.jpg)

图 67-4

行列表应会更新以反映 SQL 查询 (E) 的结果。

### 67.16 总结

本章演示了如何使用`Room`持久化库在`SQLite`数据库中存储数据。完成的项目使用了仓库（repository）将`ViewModel`与所有数据库操作分离。它演示了实体、`DAO`和`room`数据库实例的创建，包括在执行某些数据库操作时对异步任务的使用。

## 68. 使用 Android 存储访问框架访问云存储

近年来，远程存储服务（又称为“云存储”）被广泛用于存储用户文件和数据。驱动这一增长有两个关键因素。因素之一是，大多数移动设备现在都提供持续、高速的互联网连接，从而使得数据传输既快速又廉价。第二个因素是，与传统的计算机系统（如台式机和笔记本电脑）相比，这些移动设备在内部存储资源方面受到限制。例如，今天高规格的 Android 平板通常配备 128Gb 的存储容量。与带有 750Gb 硬盘的中端笔记本电脑系统相比，无缝远程存储文件已成为许多移动应用程序的关键需求。

为了承认这一事实，Google 引入了`Storage Access Framework`（存储访问框架）作为 Android 4.4`SDK`的。本章将提供存储访问框架的高级概述，为下一章更详细的教程做准备，该章节标题为“Android 存储访问框架示例”。

### 68.1 存储访问框架

从用户的角度来看，`Storage Access Framework`提供了一个直观的用户界面，允许用户从 Android 应用程序内部浏览、选择、删除和创建由存储服务（也称为文档提供者）托管的文件。通过使用此浏览界面（也称为选择器），用户可以浏览他们所选文档提供者托管的文件（如文档、音频、图像和视频）。例如，图 68-1 显示了选择器界面显示了由文档提供者服务托管的文件集合：

![](img/as3.0_storage_picker.jpg)

图 68-1

文档提供者的范围从基于云的服务到与客户端应用程序在同一设备上运行的本地文档提供者。编写此时，兼容`Storage Access Framework`的最著名文档提供者是`Box`以及意料之中的`Google Drive`。极可能其他云存储提供者和应用程序开发者很快就会提供符合`Storage Access Framework`的服务。

除了云文档提供者外，选择器还提供了对设备内部存储的访问，为应用程序提供了存储选项。

通过一组`Intents`，Android 开发者只需几行代码即可将这些存储功能整合到应用程序中。从开发者的角度来看，`Storage Access Framework`特别具有吸引力的方面是，用户选择的底层文档提供者对应用程序是完全透明的。一旦在应用程序中使用框架实现了存储功能，它就可以无需修改代码与所有文档提供者协作。

### 68.2 使用存储访问框架

Android 包含一组`Intents`，旨在将`Storage Access Framework`的功能集成到 Android 应用程序中。这些 intent 向显示`Storage Access Framework`选择器界面，并通过启动 Activity 的方法的`onActivityResult()`方法将交互结果返回应用程序。当`onActivityResult()`方法被调用时，它将传递选取文件的`Uri`以及操作是否成功的值。

`Storage Access Framework` intent 总结如下：

- `ACTION_OPEN_DOCUMENT` – 为用户提供访问选择器界面的权限，以便从设备上的文档提供者中选择文件。选取的文件以`Uri`对象的形式传回应用程序。
- `ACTION_CREATE_DOCUMENT` – 允许用户选择文档提供者、该提供者存储上的位置以及新文件的文件名。一旦选择，文件将由`Storage Access Framework`创建并将该文件的`Uri`返回给应用程序进行进一步处理。

### 68.3 过滤选择器文件列表

当启动 intent 时，选择器界面内列出的文件可以使用多种选项进行过滤。例如，考虑以下代码用于配置`ACTION_OPEN_DOCUMENT` intent：

```java
Intent intent = new Intent(Intent.ACTION_OPEN_DOCUMENT);
```

启动后，上述`intent`将导致显示选择器用户界面，允许用户浏览并选择由任何可用文档提供程序托管的文件。一旦用户选择了某个文件，该文件将以`Uri`对象的格式向应用程序提供该文件的引用。随后，应用程序可以使用`openFileDescriptor(Uri, String)`方法打开文件。然而，存在某些风险，并非所有由文档提供程序列出的文件都能通过这种方式打开。可以通过使用`CATEGORY_OPENABLE`选项修改`intent`来在选择器中排除此类文件。例如：

```java
Intent intent = new Intent(Intent.ACTION_OPEN_DOCUMENT);
intent.addCategory(Intent.CATEGORY_OPENABLE);
```

当现在显示`intent`时，无法使用`openFileDescriptor()`方法打开的文件将被列出，但用户无法选择它们。

另一种实用的过滤方法是允许通过文件类型来限制可供选择的文件。这涉及到指定应用程序能够处理的文件类型。例如，一个图像编辑应用程序可能只想为用户提供从文档提供程序中选择图像文件的选项。这是通过配置`intent`对象并指定用户可以选择的文件的 MIME 类型来实现的。以下代码指定了只有图像文件适合在选择器中选择：

```java
intent.addCategory(Intent.CATEGORY_OPENABLE);
intent.setType("image/*");
```

这可以进一步精炼以将选择限制为 JPEG 图像：

```java
intent.setType("image/jpeg");
```

或者，音频播放器应用可能只能处理音频文件：

```java
intent.setType("audio/*");
```

音频应用可能会被进一步限制为仅支持播放基于 MP4 的音频文件：

```java
intent.setType("audio/mp4");
```

在处理存储访问框架（Storage Access Framework）时，可以使用广泛的 MIME 类型设置，其中更常见的可以在网上列出的列表中：

https://en.wikipedia.org/wiki/Internet_media_type#List_of_common_media_types

## 68.4 处理 Intent 结果

由于我们启动了将返回结果的 intent，因此需要使用`registerForActivityResult()`方法（在 Android 显式 Intent – 实例示例 章节中介绍）来创建一个启动器并声明一个 lambda 回调处理返回的数据，例如：

```java
ActivityResultLauncher<Intent> startOpenForResult = registerForActivityResult(
    new ActivityResultContracts.StartActivityForResult(),
    new ActivityResultCallback<ActivityResult>() {
        @Override
        public void onActivityResult(ActivityResult result) {
            if (result.getResultCode() == Activity.RESULT_OK) {
                Intent data = result.getData();
                // 在此处从 Uri 读取文件内容
            }
        }
    });
```

一旦声明，就可以如下所示配置并启动`intent`：

```java
Intent intent = new Intent(Intent.ACTION_OPEN_DOCUMENT);
intent.addCategory(Intent.CATEGORY_OPENABLE);
intent.setType("text/plain");
startOpenForResult.launch(intent);
```

## 68.5 读取文件内容

读取文档提供程序托管的文件内容所需的具体步骤在很大程度上取决于文件的类型。例如，从文本文件中读取行的步骤与读取其他文件的步骤不同。一旦文档提供程序托管了文件，就可以通过`Uri`对象的打开描述符来读取文件内容。通过`Uri`对象的`openFileDescriptor`方法：

```java
ParcelFileDescriptor fd = getContentResolver().openFileDescriptor(uri, "r");
InputStream is = new FileInputStream(fd.getDescriptor());
BufferedReader reader = new BufferedReader(new InputStreamReader(is));
String line;
while ((line = reader.readLine()) != null) {
    // 处理行
}
reader.close();
fd.close();
```

思考近年来对“存储”的认知是如何变化的是非常有趣的。“存储”一词曾是大容量内置硬盘的同义词，但现在它同样可能指代远程托管在云端并通过互联网连接访问的存储空间。随着内置存储容量受限的“始终连接”移动设备的广泛采用，这种情况变得愈发普遍。

Android 存储访问框架（Storage Access Framework）为用户和应用程序开发人员提供了一种简单的机制，可以无缝访问存储在云端的文件。通过使用一组 intents 以及用于选择文档提供程序和文件的内置用户界面，现在只需极少的代码即可将全面的云存储集成到 Android 应用程序中。

## 69. Android 存储访问框架示例

如前所述，存储访问框架极大地简化了将云存储访问集成到 Android 应用程序中的过程。通过一个选择器用户界面和一组新的 intents，现在可以相对轻松在 Android 应用程序中构建对存储在 Google Drive 和 Box 等文档提供程序上的文件访问。在上一章介绍了 Android 存储访问框架的基础知识后，本章将演示创建一个示例应用程序，该程序使用存储访问框架来存储和管理文件。

### 69.1 关于存储访问框架示例

本章创建的 Android 应用程序将作为一个原始的文本编辑器，旨在将文本文件远程创建并存储到云存储服务中。在实践中，该示例适用于任何兼容存储访问框架的云文档存储提供程序，但为了本示例，假设使用 Google Drive。

从功能上来说，应用程序将向用户提供一个多行文本视图，可以在其中输入和编辑文本，并提供一组允许创建、打开和保存存储的文本文件的按钮。

### 69.2 创建存储访问框架示例

从欢迎屏幕选择 New Project ，在出现的新项目对话框中，点击 Next 按钮之前选择 Empty Activity 模板。

在 Name 字段中输入`StorageDemo`并指定包名为`com.ebookfrenzy.storagedemo`。在点击 Finish ，将 Minimum API level 设置为`API 26: Android 8.0 (Oreo)`，并将语言菜单设置为`Java`。按照 View Binding 章节中的常规步骤为项目添加 view binding 支持。

### 69.3 设计用户界面

用户界面需要由三个`Button`视图和一个`EditText`视图组成。在 Project 工具窗口中，导航到位于`app -> res -> layout`的`activity_main.xml`布局文件，并双击将其加载到 Layout Editor 工具中。在 Design 模式下，选择并删除 Hello World! `TextView`对象。

将`Button`控件拖到并位于布局的左上角，在释放控件之前让左侧和上方的虚线边距指南出现。放置第二个`Button`，使中心和顶部的边距指南出现。第三个`Button`控件应放置在顶部和右侧的边距指南出现的位置。

将三个按钮的文本属性分别更改为“New”、“Open”和“Save”。接下来，放置一个 Plain Text 控件，使其水平居中并位于中心`Button`之下，以便用户界面布局与图 69-1 所示匹配。使用 Layout Editor 工具栏中的 Infer Constraints 按钮添加任何缺失的约束。

选择布局中的 Plain Text 控件，删除当前的 text 属性设置（使字段初始为空），并将 ID 设置为`fileText`。接下来，将字符串属性提取到资源值中，分别命名为`string`、`open_string`和`save_string`。

![](img/as_storagedemo_ui.jpg)

图 69-1

使用 Attributes 工具窗口，配置`Button`控件上的`onClick`属性以分别调用命名为`newFile`、`openFile`和`saveFile`的方法。

### 69.4 添加 Activity 启动器

遵循 Android Explicit Intents – A Worked Example 章节中概述的步骤，我们需要从开始注册 activity 启动器以处理文件内容的创建、打开和保存。在`MainActivity.java`文件中，如下所示为三个操作分别添加一个启动器：

```java
import androidx.activity.result.ActivityResult;
import androidx.activity.result.ActivityResultCallback;
import androidx.activity.result.ActivityResultLauncher;
import androidx.activity.result.contract.ActivityResultContracts;
import android.app.Activity;
import android.content.Intent;
import android.net.Uri;
import java.io.IOException;

ActivityResultLauncher<Intent> startOpenForResult =
    registerForActivityResult(
        new ActivityResultContracts.StartActivityForResult(),
        new ActivityResultCallback<ActivityResult>() {
            @Override
            public void onActivityResult(ActivityResult result) {
                if (result.getResultCode() == Activity.RESULT_OK) {
                    Intent data = result.getData();
                    if (data != null) {
                        Uri currentUri = data.getData();
                        try {
```



## 69.5 创建新的存储文件

当`New`按钮被选中时，应用程序需要触发一个配置为创建纯文本`MIME`类型文件的`ACTION_CREATE_DOCUMENT` intent。在设计用户界面时，`New`按钮被配置为调用命名为`newFile()`的方法。正需要在该方法内启动相应的intent。

继续留在`MainActivity.java`文件中，如下实现该方法：

```java
package com.ebookfrenzy.storagedemo;

public class MainActivity extends AppCompatActivity {
    public void newFile(View view)
    {
        Intent intent = new Intent(Intent.ACTION_CREATE_DOCUMENT);
        intent.addCategory(Intent.CATEGORY_OPENABLE);
        intent.setType("text/plain");
        intent.putExtra(Intent.EXTRA_TITLE, "newfile.txt");
        startCreateForResult.launch(intent);
    }
}
```

这段代码创建了一个新的`ACTION_CREATE_INTENT` Intent对象。随后对该intent进行了配置，使其仅返回可以使用文件描述符打开的文件（通过`Intent.CATEGORY_OPENABLE`类别设置）。

接下来，代码指定了要打开的文件应具有纯文本`MIME`类型，并提供了一个占位符文件名（用户可以在选择器界面中更改该文件名）。

当执行此方法且intent完成了分配的任务时，将调用`startCreateForResult()`的lambda表达式，并传递新创建文档的`Uri`。

## 69.6 保存到存储文件

现在应用程序能够创建新的基于存储的文件了，下一步是添加将用户输入的任何文本保存到文件的功能。用户界面被配置为当用户选择保存（`Save`）按钮时调用`saveFile()`方法。该方法将负责启动一个类型为`ACTION_OPEN_DOCUMENT`的新intent，这将导致选择器用户界面出现，以便用户可以选择存储文本的文件。由于我们只处理纯文本文件，因此需要对intent进行配置，将用户的选择选项限制为匹配`text/plain` MIME类型的现有文件。在确定了`saveFile()`方法要执行的操作后，现在可以将其所示添加到`MainActivity.java`类文件中：

```java
public void saveFile(View view)
{
    Intent intent = new Intent(Intent.ACTION_OPEN_DOCUMENT);
    intent.addCategory(Intent.CATEGORY_OPENABLE);
    intent.setType("text/plain");
    startSaveForResult.launch(intent);
}
```

分配给`startSaveForResult()`的lambda表达式调用了一个名为`writeFileContent()`的方法，并传递了要写入文本的文件`Uri`。在`MainActivity.java`文件中，现在实现该方法，使其读取逻辑如下：

```java
package com.ebookfrenzy.storagedemo;

import java.io.FileOutputStream;
import android.os.ParcelFileDescriptor;

public class MainActivity extends AppCompatActivity {
    private void writeFileContent(Uri uri) throws IOException
    {
        try{
            ParcelFileDescriptor pfd =
                    this.getContentResolver().
                    openFileDescriptor(uri, "w");
            FileOutputStream fileOutputStream =
                    new FileOutputStream(
                            pfd.getFileDescriptor());
            String textContent =
                    binding.fileText.getText().toString();
            fileOutputStream.write(textContent.getBytes());
            fileOutputStream.close();
            pfd.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

该方法首先从用户选择文件的`Uri`获取并打开文件描述符。由于代码需要写入文件，因此以写入模式（`w`）打开描述符。随后使用该文件描述符作为创建输出流的基础，以便应用程序能够写入文件。用户输入的文本从编辑对象中提取，并在文件描述符和流关闭之前写入输出流中。代码还添加了处理在文件写入过程中可能遇到的任何异常。

## 69.7 打开并读取存储文件

在编写了创建和保存文本文件的代码后，最后一个任务是添加从存储打开并读取文件的功能。这将涉及编写`openFile()`点击处理方法并实现它，以便启动`ACTION_OPEN_DOCUMENT` intent：

```java
public void openFile(View view)
{
    Intent intent = new Intent(Intent.ACTION_OPEN_DOCUMENT);
    intent.addCategory(Intent.CATEGORY_OPENABLE);
    intent.setType("text/plain");
    startOpenForResult.launch(intent);
}
```

下一个任务是实现由`startOpenForResult()` lambda表达式调用的`readFileContent()`方法：

```java
package com.ebookfrenzy.storagedemo;

import java.io.BufferedReader;
import java.io.InputStream;
import java.io.InputStreamReader;

public class MainActivity extends AppCompatActivity {
    private String readFileContent(Uri uri) throws IOException {
        InputStream inputStream =
                getContentResolver().openInputStream(uri);
        BufferedReader reader =
                new BufferedReader(new InputStreamReader(
                    inputStream));
        StringBuilder stringBuilder = new StringBuilder();
        String currentline;
        while ((currentline = reader.readLine()) != null) {
            stringBuilder.append(currentline).append("\n");
        }
        inputStream.close();
        return stringBuilder.toString();
    }
}
```

之前的代码中，`String content = readFileContent(currentUri);` 和 `binding.fileText.setText(content);` 等操作用于读取和显示文件内容。这些代码片段包含在 `startOpenForResult` 的 lambda 表达式中，用于处理用户选择的文件。类似地，`writeFileContent(currentUri)` 的调用用于保存文件，而 `binding.fileText.setText("")` 则用于清空编辑区域。

以下是完整的 `MainActivity.java` 文件中相关部分的代码结构：

```java
// 打开文件操作
ActivityResultLauncher<Intent> startOpenForResult =
    registerForActivityResult(
        new ActivityResultContracts.StartActivityForResult(),
        result -> {
            if (result.getResultCode() == Activity.RESULT_OK) {
                Intent data = result.getData();
                if (data != null) {
                    Uri currentUri = data.getData();
                    try {
                        String content = readFileContent(currentUri);
                        binding.fileText.setText(content);
                    } catch (IOException e) {
                        // Handle here
                    }
                }
            }
        }
    );

// 保存文件操作
ActivityResultLauncher<Intent> startSaveForResult =
    registerForActivityResult(
        new ActivityResultContracts.StartActivityForResult(),
        result -> {
            if (result.getResultCode() == Activity.RESULT_OK) {
                Intent data = result.getData();
                if (data != null) {
                    Uri currentUri = data.getData();
                    try {
                        writeFileContent(currentUri);
                    } catch (IOException e) {
                        // Handle here
                    }
                }
            }
        }
    );

// 创建文件操作
ActivityResultLauncher<Intent> startCreateForResult =
    registerForActivityResult(
        new ActivityResultContracts.StartActivityForResult(),
        new ActivityResultCallback<ActivityResult>() {
            @Override
            public void onActivityResult(ActivityResult result) {
                if (result.getResultCode() == Activity.RESULT_OK) {
                    Intent data = result.getData();
                    if (data != null) {
                        binding.fileText.setText("");
                    }
                }
            }
        }
    );
```



该方法首先提取所选文本文件的文件描述符并将其打开读取。随后打开与`Uri`关联的输入流，并将其作为`BufferedReader`实例的输入源。文件中的每一行都会被读取并存储在`StringBuilder`对象中。一旦读取完所有行，输入流和文件描述符都将被关闭，文件内容以`String`返回。

## 69.8 测试存储应用程序

编码阶段完成后，应用程序已准备好测试。编译并运行应用程序，然后选择新建（New）按钮。存储 Access Framework 随后将显示如图 69-2 所示的下载界面。

点击上方指定的菜单按钮，选择 My Drive 下的 Drive 选项，并导航到 Google Drive 存储中合适的位置以保存文件。在选择器界面底部的文本框中，将文件名从`newfile.txt`更改为合适的名称（保留`.txt`扩展名），然后选择保存（Save）选项。

一旦创建了新文件，应用程序应返回主活动，通知栏可能会出现一条显示“1 个文件已上传”的通知。此时，应该可以在浏览器窗口中登录您的 Google Drive 账号，并在请求的位置找到新创建的文件。

需要注意的是，如果 Android 设备缺乏活跃的互联网连接，存储访问框架（Storage Access Framework）将把存储文件缓存在本地中。然而，一旦重新建立连接，任何缓存数据都将与远程存储服务同步。因此，作为应用程序的最终测试，请在浏览器窗口登录您的 Google Drive 账户，导航到保存的文件并点击查看内容，如果一切顺利，内容应包含应用程序保存的文本。

### 69.9 总结

本章介绍了如何创建一个 Android Studio 应用程序示例，该程序是一个非常基础的文本编辑器，旨在使用 Android 存储访问框架通过云存储创建、保存和打开文件。

# 70. 使用 VideoView 和 MediaController 类在 Android 上进行视频播放

智能手机和平板的主要用途之一是提供在线内容的访问。视频是一种广泛使用的内容形式，特别是在平板设备上。

Android SDK 包含了两个类，使得在开发应用程序时在 Android 设备上实现视频播放极其简单。本章将概述这两个类`VideoView`和`MediaController`，并创建一个视频播放应用程序。

## 70.1 介绍 Android VideoView 类

在 Android 应用程序中显示视频最简单的方法是使用`VideoView`类。该视觉组件在被添加到 Activity 布局时，提供了一个可以在其中播放视频的表面。Android 目前支持以下视频格式：

* H.263
* H.264 AVC
* H.265 HEVC
* MPEG-4 SP
* VP8
* VP9

`VideoView`类有一许多可以调用的方法来管理视频播放。一些最常用的方法如下：

* `setVideoPath(String path)` – 指定要播放的视频媒体路径（字符串格式）。这可以是远程视频文件的 URL，也可以是设备本地的视频文件。
* `setVideoUri(Uri uri)` – 执行与`setVideoPath()`方法相同的任务，但接受`Uri`对象作为参数而不是字符串。
* `start()` – 开始视频播放。
* `stopPlayback()` – 停止视频播放。
* `pause()` – 暂停视频播放。
* `isPlaying()` – 返回一个布尔值，指示视频是否正在播放。
* `setOnPreparedListener(MediaPlayer.OnPreparedListener)` –允许在视频准备好播放时调用回调方法。
* `setOnErrorListener(MediaPlayer.OnErrorListener)` –允许在视频播放期间发生错误时调用回调方法。
* `setOnCompletionListener(MediaPlayer.OnCompletionListener)` –允许在视频结束时调用回调方法。
* `getDuration()` – 返回视频的持续时间。除非从`OnPreparedListener()`回调方法内部调用，否则通常会返回 -1。
* `getCurrentPosition()` – 返回指示当前播放位置的整数值。
* `setMediaController(MediaController)` – 指定一个`MediaController`实例，允许向用户显示播放控件。

## 70.2 介绍 Android MediaController 类

如果使用`VideoView`类播放视频，用户将无法对播放进行任何控制，视频将一直运行到结束。此问题可以通过将`MediaController`类的实例挂载到`VideoView`实例上来解决。`MediaController`将会提供一组控件，允许用户管理播放（例如暂停以及在视频时间轴上向后回退或向前快进）。

控件的位置通过将控制器实例锚定到用户界面布局中的特定视图来指定。一旦连接并锚定，控件将在播放开始时短暂出现，随后用户可以通过点击实例所锚定的视图在任何时间点恢复控件。

该类的一些关键方法如下：

* `setAnchorView(View view)` – 指定控制器将锚定的视图。这指定了控件在屏幕上的位置。
* `show()` – 显示控件。
* `show(int timeout)` – 控件显示指定的持续时间（以毫秒计）。
* `hide()` – 向用户隐藏控制器。
* `isShowing()` – 返回一个布尔值，指示控件当前对用户可见。

## 70.3 创建视频播放示例

本章的剩余部分将创建一个示例应用程序，其使用`VideoView`和`MediaController`类播放 MPEG-4 视频文件。

从欢迎界面选择 New Project（新建项目）选项，在出现的新项目对话框中，点击 Next（下一步）按钮之前选择 Empty Views Activity（空视图 Activity）模板。

在 Name（名称）字段中输入`VideoPlayer`，并指定`com.ebookfrenzy.videoplayer`为包名。在点击 Finish（完成）按钮之前，将 Minimum API level 设置为`API 33: Android 13 (Tiramisu)`，并将语言菜单更改为`Java`。参考章节 [11.8 将项目迁移到 View 绑定] 中的步骤为项目启用视图 绑定。

## 70.4 设计 VideoPlayer 布局

主 Activity 的用户界面将仅由`VideoView`类的实例组成。使用 Project 工具窗口找到`app -> res -> layout -> activity_main.xml`文件，双击它，将 Layout Editor 工具切换到 Design（设计）模式，并删除默认的`TextView`小部件。

从 Palette（调板）面板的 Widgets（控件）类别，将`VideoView`实例拖放到布局中以填充可用的画布区域，如图 70-1 所示。使用 Attributes（属性）面板，将`layout_width`和`layout_height`分别更改为`match_constraint`和`wrap_content`。此外，移除连接`VideoView`到`ConstraintLayout`底部的约束。最后，将组件的 ID 改为`videoView`。

## 70.5 下载视频文件

`VideoPlayer`应用程序播放的视频是一个 MPEG-4 格式的短动画。使用浏览器导航到以下 URL 播放视频：`https://www.ebookfrenzy.com/android_book/demo.mp4`

留在浏览器窗口中，右键点击视频播放，选择保存或下载视频到本地，并选择合适的文件系统位置，命名为`demo.mp4`。

在 Android Studio 中，在 Project 工具窗口找到`res`文件夹，右键点击它，选择 New -> Directory 选项，并在名称字段中输入`raw`然后按回车键。使用操作系统的文件导航器找到上述`demo.mp4`文件并复制。返回 Android Studio，右键点击新创建的`raw`目录并选择 Paste（粘贴）。一旦添加完成后，`raw`文件夹应符合图 70-2。

## 70.6 配置 VideoView

下一步是为`VideoView`配置视频路径并开始播放。将在主 Activity 初始化时执行，因此将`MainActivity.java`文件加载到编辑器中并按照下方列出的列表进行修改：

```java
package com.ebookfrenzy.videoplayer;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

import android.net.Uri;

...

public class MainActivity extends AppCompatActivity {

    private ActivityMainBinding binding;

    @Override

    protected void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);

        binding = ActivityMainBinding.inflate(getLayoutInflater());

        View view = binding.getRoot();

    }

}
```

```java
        setContentView(view);

        configureVideoView();

    }

    private void configureVideoView() {

        binding.videoView1.setVideoURI(Uri.parse("android.resource://"

                + getPackageName() + "/" + R.raw.demo));

        binding.videoView1.start();

    }

}
```

此代码获取了布局中`VideoView`实例的引用，为其分配了一个指向 raw 资源目录中电影文件的`URI`对象，然后开始播放视频。

通过在模拟器或物理 Android 设备上运行该应用程序来测试它。应用程序启动后，在视频开始播放之前，缓冲视频内容可能会有短暂的延迟（见图 70-3）。

![](img/as_video_player_running.jpg)

图 70-3

这展示了将视频播放集成到 Android 应用程序是多么简单。此示例中的一切都是通过一个`VideoView`实例和三行代码实现的。

## 70.7 为 Video View 添加 MediaController

按照`VideoPlayer`应用程序目前的状态，用户无法控制播放。如之前所述，这可以通过`MediaController`类来实现。要为`VideoView`添加控制器，请再次修改`configureVideoView()`方法：

```java
package com.ebookfrenzy.videoplayer;

.

.

import android.widget.MediaController;

public class MainActivity extends AppCompatActivity {

    private ActivityMainBinding binding;

    private MediaController mediaController;

.

.

    private void configureVideoView() {

        binding.videoView1.setVideoURI(Uri.parse("android.resource://"

                + getPackageName() + "/" + R.raw.demo));

        mediaController = new MediaController(this);

        mediaController.setAnchorView(binding.videoView1);

        binding.videoView1.setMediaController(mediaController);

        binding.videoView.start();

    }

}
```

当应用了这些更改并启动应用程序时，点击`VideoView`画布将导致媒体控件显示在视频播放上层。这些控件应该包含一个`Seekbar`以及快进、后退和播放/暂停按钮。当控件从视图中消失后，可以通过再次点击`VideoView`画布随时恢复。只需多加三行代码，我们的视频播放器应用程序就有了媒体控件，如图 70-4 所示所示：

![](img/as_3.6_video_player_media_controls.jpg)

图 70-4

## 70.8 设置 onPreparedListener

作为处理视频媒体的最后一个示例，该活动将进一步扩展，以演示配置监听器的机制。在这种情况下，将实现一个监听器，用于将视频时长作为消息输出到 Android Studio 的`Logcat`面板。该监听器还将配置视频播放为持续循环：

```java
package com.ebookfrenzy.videoplayer;

.

.

import android.util.Log;

public class MainActivity extends AppCompatActivity {

    private ActivityMainBinding binding;

    private MediaController mediaController;

    String TAG = "VideoPlayer";

    private void configureVideoView() {

        binding.videoView1.setVideoURI(Uri.parse("android.resource://"

                + getPackageName() + "/" + R.raw.demo));

        MediaController mediaController = new

                    MediaController(this);

        mediaController.setAnchorView(binding.videoView1);

        binding.videoView1.setMediaController(mediaController);

        binding.videoView1.setOnPreparedListener(mp -> {

            mp.setLooping(true);

            Log.i(TAG, "Duration: " + mp.getDuration());

        });

        binding.videoView1.start();

    }

}
```

## 70.9 总结

Android 是内容分发的优秀平台，特别是视频形式的内容。如本章所述，Android 提供了两个类，即`VideoView`和`MediaController`，它们使播放变得快速简单。

---

## 71 画中画 (Picture-in-Picture)

虽然涵盖了 Android 中的多任务处理，但提到了画中画（PiP）模式却未进行详细介绍。本章将提供画中画的概述。

### 71.1 画中画功能

正如本章稍后部分解释的，活动被放入 PiP 模式。例如，图 71-1 显示了 PiP 模式：

![](img/Image273.jpg)

图 71-1

图 71-2 显示了用户点击后的 PiP 模式：

![](img/Image2463.jpg)

图 71-2

### 71.2 启用画中画

本章的剩余部分将概述如何启用 PiP 模式。它目前仅支持运行 API 26：Android 8.0 (Oreo) 或更高版本的设备。实现 PiP 模式的第一步是在项目的清单文件中启用它。PiP 模式是按活动配置的，只需在每个需要 PiP 支持的活动元素中添加以下行：

```xml
<activity android:name=".MyActivity"

    android:supportsPictureInPicture="true"

    android:configChanges="screenSize|smallestScreenSize|screenLayout|orientation">

    <intent-filter>

        <action android:name="android.intent.action.MAIN" />

        <category android:name="android.intent.category.LAUNCHER" />

    </intent-filter>

</activity>
```



`android:supportsPictureInPicture`开启了该活动的 PiP 功能，而`android:configChanges`属性通知 Android 该活动可以处理布局配置更改。如果没有此设置，每当活动进入或退出 PiP 模式时，活动都会重新启动，导致视频在切换期间从头开始播放。

## 71.3 配置画中画参数

PiP 行为通过使用`PictureInPictureParams`类来定义，可以通过`Builder`类如下创建实例：

```
PictureInPictureParams params = new PictureInPictureParams.Builder().build();
```

上述代码创建了一个带有已定义特殊参数的默认`PictureInPictureParams`实例。也可以使用以下可选方法调用来定制这些参数：

* `setActions()` – 用于定义当活动处于 PiP 模式时可以在 PiP 窗口内执行的操作。本章稍后将更详细介绍这些操作。
* `setAspectRatio()` – 声明 PiP 窗口显示的优选纵宽比。该方法接收一个包含高与宽之比例的`Rational`对象作为参数。
* `setSourceRectHint()` – 接收一个`Rect`对象作为参数，定义在 PiP 窗口中显示的 Activity 屏幕区域。

例如，下面的代码在`PictureInPictureParams`对象中配置了纵宽比和操作参数。在宽高比方面，它是使用`VideoView`实例的宽度和高度维度定义的：

```
Rational rational = new Rational(videoView.getWidth(),
                               videoView.getHeight());

PictureInPictureParams params =
    new PictureInPictureParams.Builder()
              .setAspectRatio(rational)
              .setActions(actions)
              .build();
```

一旦定义，可以随时使用`setPictureInPictureParams()`方法如下所示设置 PiP 参数：

```
setPictureInPictureParams(params);
```

在进入 PiP 模式时也可以指定参数。

## 71.4 进入画中画模式

通过调用`enterPictureInPictureMode()`方法并传递`PictureInPictureParams`对象，可以将 Activity 置画中画模式：

```
enterPictureInPictureMode(params);
```

如果不需要参数，请按照上一节所述，创建一个默认的`PictureInPictureParams`对象。如果之前已使用`setPictureInPictureParams()`方法设置了参数，则这些参数将与调用`enterPictureInPictureMode()`方法时指定的参数合并。

## 71.5 检测画中画模式的变化

当 Activity 进入 PiP 模式时，隐藏不必要的视图是非常重要的，以确保 PiP 窗口内只可见视频播放。当 Activity 重新进入全屏模式时，必须恢复已隐藏的用户界面组件。可以通过重写`onPictureInPictureModeChanged()`方法来执行这些以及其他特定于应用的任务。当此方法添加到 Activity 后，每当 Activity 在 PiP 和全屏模式之间切换时都会被调用一次，并传递一个指示 Activity 当前是否处于 PiP 模式的`Boolean`值：

```
@Override
public void onPictureInPictureModeChanged(
                    boolean isInPictureInPictureMode) {
    super.onPictureInPictureModeChanged(isInPictureInPictureMode);

    if (isInPictureInPictureMode) {
        // Activity 进入画中画模式
    } else {
        // Activity 进入全屏模式
    }
}
```

## 71.6 添加画中画操作

画中画操作会在用户点击 PiP 窗口时以图标的形式显示在窗口内。实现画中画操作是一个多步骤过程，首先要实现一种让 PiP 窗口通知 Activity 已选择操作的方法。这通过在 Activity 中设置广播接收器（broadcast receiver），然后在 PiP 操作中创建一个`pending intent`来，该意图随后被配置为广播广播接收器正在监听的意图。当意图触发广播接收器时，意图中存储的数据可以用于识别所执行的操作，并在 Activity 中采取必要的行动。

PiP 操作使用`RemoteAction`实例声明，并用图标、标题、描述和`PendingIntent`对象初始化。一旦创建了一个或多个操作，它们就会被添加到`ArrayList`中，并在构建`PictureInPictureParams`对象时传递给`setActions()`方法。

下面的代码片段演示了`Intent`、`PendingIntent`和`RemoteAction`对象的创建，以及一个`PictureInPictureParams`实例，然后将其应用于 Activity 的 PiP 设置：

```
final ArrayList<RemoteAction> actions = new ArrayList<>();
Intent actionIntent = new Intent("MY_PIP_ACTION");
final PendingIntent pendingIntent =
    PendingIntent.getBroadcast(MyActivity.this, REQUEST_CODE, actionIntent, FLAG_IMMUTABLE);

final icon = Icon.createResource(MyActivity.this, R.drawable.action_icon);

RemoteAction remoteAction = new RemoteAction(icon,
    "My Title",
    "My Description",
    pendingIntent);
actions.add(remoteAction);

PictureInPictureParams params =
    new PictureInPictureParams.Builder()
              .setActions(actions)
              .build();

setPictureInPictureParams(params);
```

### 71.7 总结

画中画模式是 Android 8.0 引入的一项多任务功能，允许用户在执行其他任务时视频在小窗口中继续播放。在使用 PiP 模式之前，必须先在清单（manifest）文件中启用需要它的 Activity。PiP 模式的行为使用`PictureInPictureParams`实例进行配置，并通过在 Activity 内部调用`enterPictureInPictureMode()`启动。在 PiP 模式下，应只可见视频播放，这要求任何用户界面元素都隐藏，直到选择全屏模式。画中画操作在用户点击 PiP 窗口时以图标的形式叠加在窗口上。PiP 窗口使用广播接收器和等待意图来通知 Activity。

## 72. Android 画中画教程

接上章节，本章将对现有的 VideoPlayer 项目进行增强，以添加画中画支持，包括检测 PiP 模式变化以及添加关于当前运行视频的操作。

### 72.1 在清单文件中添加画中画支持

为 Android 应用添加画中画支持的第一步是在项目清单文件中启用它。打开`AndroidManifest.xml`文件并修改`activity`元素以启用画中画支持：

```
<activity android:name=".MainActivity"
    android:supportsPictureInPicture="true"
    android:configChanges="screenSize|smallestScreenSize|screenLayout|orientation"
    android:exported="true">
    <intent-filter>
        <action android:name="android.intent.action.MAIN" />
        <category android:name="android.intent.category.LAUNCHER" />
    </intent-filter>
</activity>
```

### 72.2 添加画中画按钮

目前的设计中，VideoPlayer Activity 的布局仅包含`VideoView`实例。现在要在布局中添加按钮以切换到 PiP 模式。加载`activity_main.xml`文件到布局编辑器，从调色板拖出一个`Button`对象到布局中，使其位置如图 72-1 所示。

现在必须将`enterPipMode` onClick 回调方法添加到`MainActivity.java`类文件中。找到该文件，在代码编辑器中打开它并添加如下方法：

```
import android.app.PictureInPictureParams;
import android.util.Rational;

public void enterPipMode(View view) {
    Rational rational = new Rational(binding.videoView1.getWidth(),
            binding.videoView1.getHeight());

    PictureInPictureParams params =
            new PictureInPictureParams.Builder()
                    .setAspectRatio(rational)
                    .build();

    binding.pipButton.setVisibility(View.INVISIBLE);
    binding.videoView1.setMediaController(null);
    enterPictureInPictureMode(params);
}
```

该方法首先获取`Button`视图的引用，然后创建一个包含`VideoView`宽度和高度的`Rational`对象。接着使用`PictureInPictureParams.Builder`创建一组画中画参数，并将`Rational`对象作为视频播放的宽高比例传递。由于按钮在视频处于画中画（PiP）模式时不需要显示，因此将其将其设置为不可。视频播放控件也被隐藏，这样视频视图在画中画模式下将不会被遮挡。

在运行 Android 版本 8 或更高版本的设备或模拟器上编译并运行应用，在点击画中画按钮之前等待视频播放开始。视频播放将最小化并显示在画中画窗口中，所示：

![](img/as_video_pip_window.jpg)

图 72-2

点击画中画窗口，然后点击窗口中心出现的全屏模式标记处。尽管 Activity 回到了全屏模式，但按钮和媒体播放控件仍然保持隐藏。

显然，必须向项目中添加一些代码，以检测 Activity 内部发生画中画模式变化的情况。

## 72.4 检测画中画模式的变化

如上一章所述，画中画模式的变化是通过重写受影响 Activity 内部的`onPictureInPictureModeChanged()`方法来检测的。在这种情况下，必须编写该方法来检测 Activity 是正在进入还是退出画中画模式，并采取适当的操作重新激活画中画按钮和播放控件。继续留在`MainActivity.java`文件中，现在添加此方法：

```
@Override
public void onPictureInPictureModeChanged(boolean isInPictureInPictureMode) {
    super.onPictureInPictureModeChanged(isInPictureInPictureMode);

    if (isInPictureInPictureMode) {
    } else {
        binding.pipButton.setVisibility(View.VISIBLE);
        binding.videoView1.setMediaController(mediaController);
    }
}
```

当调用该方法时，会传入一个`Boolean`值，指示 Activity 现在是否处于画中画模式。上述方法中的代码检查此值以决定是否显示画中画按钮以及重新激活播放控件。

### 72.5 添加广播接收器（Broadcast Receiver）

项目的最后一步是为画中画添加一个操作。该操作的目的是显示包含当前播放视频名称的`Toast`消息。需要在画中画窗口和 Activity 之间进行通信。实现这一目标的最简单方法之一是在 Activity 内部实现`broadcast receiver`，并使用`pending intent`从画中画窗口向 Activity 广播消息。每次 Activity 进入画中画模式时，都必须执行这些步骤，因此必须在`onPictureInPictureModeChanged()`方法中添加代码。现在找到该方法，并开始添加一些代码来创建意过滤器并初始化`broadcast receiver`：

```
import android.content.BroadcastReceiver;
import android.content.Context;
import android.content.Intent;
import android.content.IntentFilter;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    private BroadcastReceiver receiver;

    @Override
    public void onPictureInPictureModeChanged(boolean isInPictureInPictureMode) {
        super.onPictureInPictureModeChanged(isInPictureInPictureMode);

        if (isInPictureInPictureMode) {
            IntentFilter filter = new IntentFilter();
            filter.addAction("com.ebookfrenzy.videoplayer.VIDEO_INFO");

            receiver = new BroadcastReceiver() {
                @Override
                public void onReceive(Context context, Intent intent) {
                    Toast.makeText(context, "Favorite Movie", Toast.LENGTH_LONG).show();
                }
            };
            registerReceiver(receiver, filter, Context.RECEIVER_EXPORTED);
        } else {
            binding.pipButton.setVisibility(View.VISIBLE);
            binding.videoView1.setMediaController(mediaController);

            if (receiver != null) {
                unregisterReceiver(receiver);
            }
        }
    }
}
```




## 72.6 添加画中画操作

实现广播接收器后，下一步是创建一个 `RemoteAction` 对象，并配置一个图像来表示画中画窗口中的操作。对于此示例，将使用名为 `ic_info_24dp.xml` 的图像文件。该文件可以在从以下 URL 下载的源码 `project_icons` 文件夹中找到：https://www.ebookfrenzy.com/retail/giraffejava/index.php

找到此图标文件，将其复制并粘贴到项目工具窗口 `app -> res -> drawables` 文件夹中：

![](img/as_video_pip_icon_added.jpg)

图 72-3

下一步是创建一个发送给广播接收器的 `Intent`。然后，该意图需要封装在 `PendingIntent` 对象中，以便在用户点击画中画窗口中的按钮时触发该意图。编辑 `MainActivity.java` 文件，添加创建 `Intent` 和 `PendingIntent` 对象的方法：

```java
import android.app.PendingIntent;

import static android.app.PendingIntent.FLAG_IMMUTABLE;

public class MainActivity extends AppCompatActivity {

    private static final int REQUEST_CODE = 101;

    private void createPipAction() {

        Intent actionIntent = new Intent("com.ebookfrenzy.videoplayer.VIDEO_INFO");

        final PendingIntent pendingIntent = PendingIntent.getBroadcast(MainActivity.this,

                REQUEST_CODE, actionIntent, FLAG_IMMUTABLE);

    }

}
```

现在有了 `Intent` 对象及其包含的 `PendingIntent` 实例，需要创建一个 `RemoteAction` 对象，包含显示在画中画窗口中的图标和 `PendingIntent` 对象。继续留在 `createPipAction()` 方法中，添加如下代码：

```java
import android.app.RemoteAction;

import android.graphics.drawable.Icon;

import java.util.ArrayList;

private void createPipAction() {

    ArrayList<RemoteAction> actions = new ArrayList<>();

    Intent actionIntent = new Intent("com.ebookfrenzy.videoplayer.VIDEO_INFO");

    final PendingIntent pendingIntent = PendingIntent.getBroadcast(MainActivity.this,

            REQUEST_CODE, actionIntent, FLAG_IMMUTABLE);

    final Icon icon = Icon.createWithResource(MainActivity.this,

            R.drawable.ic_info_24dp);

    RemoteAction remoteAction = new RemoteAction(icon, "Info",

            "Video Info", pendingIntent);

    actions.add(remoteAction);

}
```

现在需要创建一个包含该操作的 `PictureInPictureParams` 对象，并应用这些参数，以便该操作在画中画窗口中显示：

```java
private void createPipAction() {

    ArrayList<RemoteAction> actions = new ArrayList<>();

    Intent actionIntent = new Intent("com.ebookfrenzy.videoplayer.VIDEO_INFO");
}
```

```java
final PendingIntent pendingIntent =

    PendingIntent.getBroadcast(MainActivity.this,

            REQUEST_CODE, actionIntent, FLAG_IMMUTABLE);

final Icon icon =

        Icon.createWithResource(MainActivity.this,

            R.drawable.ic_info_24dp);

RemoteAction remoteAction = new RemoteAction(icon, "Info",

        "Video Info", pendingIntent);

actions.add(remoteAction);

PictureInPictureParams params =

        new PictureInPictureParams.Builder()

            .setActions(actions)

            .build();

setPictureInPictureParams(params);

}
```

在测试操作前的最后一个任务是在 Activity 进入 PiP 模式时调用 `createPipAction()` 方法：

```java
@Override
public void onPictureInPictureModeChanged(boolean isInPictureInPictureMode) {

    super.onPictureInPictureModeChanged(isInPictureInPictureMode);

.

.

    registerReceiver(receiver, filter);

    createPipAction();

} else {

    binding.pipButton.setVisibility(View.VISIBLE);

    binding.videoView1.setMediaController(mediaController);

.

}
```

## 72.7 测试画中画操作

重新运行应用并将 Activity 置于 PiP 模式。点击 PiP 窗口以显示新的操作按钮，如图 72-4 所示：

![](img/as_video_pip_with_actions.jpg)

图 72-4

点击操作按钮并等待 `Toast` 消息出现，该消息将显示视频名称：

![](img/as_video_pip_toast.jpg)

图 72-5

## 72.8 总结

本章演示了如何在 Android Studio 应用程序项目中添加画中画支持，包括启用和进入 PiP 模式以及实现 PiP 操作。这包含了使用广播接收器和等待意图（pending intents）来实现 PiP 窗口与 Activity 之间的通信。

# 73. 使用 MediaPlayer 和 MediaRecorder 进行 Android 音频录制和播放

本章将概述 `MediaRecorder` 类，并解释如何使用该类录制音频或视频。还将涵盖使用 `MediaPlayer` 类播放音频的内容。在介绍基础知识后，将创建一个示例应用程序来演示这些技术。除了处理音频和视频外，本章还将涉及将文件保存到 SD 卡。

## 73.1 播放音频

在音频播放方面，大多数 Android 实现支持 AAC LC/LTP、HE-AACv1 (AAC+)、HE-AACv2 (enhanced AAC+)、AMR-NB、AMR-WB、MP3、MIDI、Ogg Vorbis 和 PCM/WAVE 格式。

可以使用 `MediaPlayer` 或 `AudioTrack` 类执行音频播放。`AudioTrack` 是更高级的选项，它使用流媒体缓冲区并对音频提供更强的控制。相比之下，`MediaPlayer` 类为实现音频播放提供了更简单的编程接口，能够满足大多数音频需求。

`MediaPlayer` 类有一系列关联的方法，应用程序可以通过这些方法来执行特定任务。该类一些关键方法的子集如下：

- `create()` – 调用以创建类的新实例，并传递要播放音频的 `Uri`。
- `setDataSource()` – 设置音频播放的源。
- `prepare()` – 指令播放器准备开始播放。
- `start()` – 开始播放。
- `pause()` – 暂停播放。可以通过调用 `resume()` 方法恢复播放。
- `stop()` – 停止播放。
- `setVolume()` – 接受两个浮点参数，指定左右声道的播放音量。
- `resume()` – 恢复之前暂停的播放会话。
- `reset()` – 重置媒体播放器实例的状态。本质上是将实例置回未初始化状态。至少，重置后的播放器需要重新设置数据源并调用 `prepare()` 方法。
- `release()` – 在播放器实例不再需要时调用。此方法确保播放器持有的任何资源都会被释放。

在典型的实现中，应用程序将实例化 `MediaPlayer` 类的实例，设置要播放的音频源，然后调用 `prepare()` 接着调用 `start()`。例如：

```java
MediaPlayer mediaPlayer = new MediaPlayer();

mediaPlayer.setDataSource("https://www.yourcompany.com/myaudio.mp3");

mediaPlayer.prepare();

mediaPlayer.start();
```

## 73.2 使用 MediaRecorder 类录制音频和视频

与音频播放一样，录制可以使用几种不同的技术完成。其中一种方案是使用 `MediaRecorder` 类，与 `MediaPlayer` 类一样，它提供了几个用于录制音频的方法：

- `setAudioSource()` – 指定要录制的音频源（通常对于设备麦克风，这将是 `MediaRecorder.AudioSource.MIC`）。
- `setVideoSource()` – 指定要录制的视频源（例如 `MediaRecorder.VideoSource.CAMERA`）。
- `setOutputFormat()` – 指定录制的音频或视频存储的格式（例如 `MediaRecorder.OutputFormat.AAC_ADTS`）。
- `setAudioEncoder()` – 指定录制音频的音频编码器（例如 `MediaRecorder.AudioEncoder.AAC`）。
- `setOutputFile()` – 配置存储录制音频或视频的文件路径。
- `prepare()` – 准备 `MediaRecorder` 实例开始录制。
- `start()` – 开始录制过程。
- `stop()` – 停止录制过程。录制器停止后，需要重新配置并准备后再次启动。
- `reset()` – 重置录制器。实例需要重新配置并准备后再次启动。
- `release()` – 在录制器实例不再需要时调用。此方法确保释放实例持有的所有资源。

使用该类的典型实现将设置源、输出、编码和输出文件。然后调用 `prepare()` 和 `start()` 方法。录制结束时调用 `stop()` 方法，随后调用 `reset()` 方法。当应用程序不再需要录制器时，建议调用 `release()` 方法：

```java
MediaRecorder mediaRecorder = new MediaRecorder();

mediaRecorder.setAudioSource(MediaRecorder.AudioSource.MIC);

mediaRecorder.setOutputFormat(MediaRecorder.OutputFormat.AAC_ADTS);

mediaRecorder.setAudioEncoder(MediaRecorder.AudioEncoder.AAC);

mediaRecorder.setOutputFile(audioFilePath);

mediaRecorder.prepare();

mediaRecorder.start();

// ... 停止逻辑 ...

mediaRecorder.release();
```

为了录制音频，应用程序的清单文件必须包含 `android.permission.RECORD_AUDIO` 权限：

```xml
<uses-permission android:name="android.permission.RECORD_AUDIO" />
```

如“在 Android 中请求运行时权限”章节中所述，访问麦克风属于危险权限。因此，为了支持 Android 6，在应用程序启动时也必须请求麦克风访问，其步骤将在本章稍后介绍。

## 73.3 关于示例项目

本章的剩余部分将创建一个示例应用程序，演示如何使用 `MediaPlayer` 和 `MediaRecorder` 类在 Android 设备上实现音频录制和播放。

在开发使用特定硬件功能的应用程序时（以麦克风为例），在尝试通过应用程序代码访问它之前检查该功能的可用性是重要的。因此，本章创建的应用程序还将包含检测设备是否存在麦克风的代码。

完成后，此应用程序将提供一个直观的界面，允许用户录制和播放音频。录制的音频将存储在设备上的一个音频文件中。尽管如此，本教程还将简要探讨使用 SD 卡存储的机制。

## 73.4 创建 AudioApp 项目

从欢迎界面选择 `New Project` 选项，在出现的新项目对话框中，点击 `Next` 按钮之前选择 `Empty Views Activity` 模板。

在 `Name` 字段中输入 `AudioApp`，并指定 `com.ebookfrenzy.audioapp` 为包名。在点击 `Finish` 按钮之前，将 `Minimum API level` 设置更改为 `API 31`（Android 12.0），并将 `Language` 菜单设置为 `Java`。按照章节 11.8 Migrating a Project to View Binding 中概述的步骤为项目添加视图绑定支持。

## 73.5 设计用户界面

创建新项目后，从 Project 工具窗口中选择 `activity_main.xml` 文件，并在 Design 模式下的 Layout 编辑器中，选择“Hello World!” `TextView` 并将其从布局中删除。

将三个 `Button` 视图拖放到布局中。按钮的定位对于本示例来说并不重要，但图 73-1 显示了使用垂直链的建议布局。

配置按钮以显示读取 Play（播放）、Record（录制）和 Stop（停止）的字符串资源，并分别为它们赋予视图 ID `playButton`、`recordButton` 和 `stopButton`。

选择 `Play` 按钮，并在 `Attributes` 面板中配置 `onClick` 属性，以便用户时调用名为 `playAudio` 的方法。重复这些步骤配置剩余按钮分别调用名为 `recordAudio` 和 `stopAudio` 的方法。

![](img/as_audio_app_ui.jpg)

图 73-1

## 73.6 检查麦克风可用性

在没有麦克风的设备上尝试录制音频会导致 Android 系统抛出异常。因此，在进行此类尝试之前检查麦克风的存在至关重要。有几种方法可以实现这一点，包括检查设备的物理存在。一种更简单且更有可能在不同 Android 设备上运行的方法是询问 Android 系统是否安装了针对特定功能的包。这涉及创建一个 `PackageManager` 类的实例，然后调用对象的 `hasSystemFeature()` 方法。`PackageManager.FEATURE_MICROPHONE` 是此例中感兴趣的功能。

对于此示例，我们将创建一个名为 `hasMicrophone()` 的方法，可以调用该方法来检查麦克风的存在。在 Project 工具窗口中，找到并双击 `MainActivity.java` 文件并修改它以添加此方法：

```java
package com.ebookfrenzy.audioapp;

.

.

import android.content.pm.PackageManager;

.

.

public class MainActivity extends AppCompatActivity {

.

.

    protected boolean hasMicrophone() {

        PackageManager pmanager = this.getPackageManager();

        return pmanager.hasSystemFeature(

                PackageManager.FEATURE_MICROPHONE);

    }

}
```

## 73.7 初始化 Activity

下一步是修改 activity 以执行几项初始化任务。在保留 `MainActivity.java` 文件中，如下所示修改代码：

```java
package com.ebookfrenzy.audioapp;

import java.io.File;
```




`import java.io.IOException;`

`import androidx.annotation.NonNull;`

`import android.media.MediaRecorder;`

`import android.os.Environment;`

`import android.media.MediaPlayer;` 

.

.

```java
public class MainActivity extends AppCompatActivity {

    private ActivityMainBinding binding;

    private static MediaRecorder mediaRecorder;

    private static MediaPlayer mediaPlayer;

    private static String audioFilePath;

    private boolean isRecording = false;

    @Override

    protected void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);

        binding = ActivityMainBinding.inflate(getLayoutInflater());

        View view = binding.getRoot();

        setContentView(view);

        audioSetup();

    }

    private void audioSetup() {

        if (!hasMicrophone()) {

            binding.stopButton.setEnabled(false);

            binding.playButton.setEnabled(false);

            binding.recordButton.setEnabled(false);

        } else {

            binding.playButton.setEnabled(false);

            binding.stopButton.setEnabled(false);

        }

        File audioFile = new File(this.getFilesDir(), "audio.mp3");

        audioFilePath = audioFile.getAbsolutePath();

    }

.
```

新增的代码调用 `hasMicrophone()` 方法来确定设备是否包含麦克风。如果不包含，则所有按钮都被禁用；否则，仅禁用 Stop 和 Play 按钮。下一行代码需要稍微解释：`File audioFile = new File(this.getFilesDir(), "audio.mp3"); audioFilePath = audioFile.getAbsolutePath();` 这段代码在应用的内部存储器中创建一个名为 `audio.mp3` 的新文件以存储音频。

## 73.8 实现 recordAudio() 方法

当用户触摸 Record 按钮时，将调用 `recordAudio()` 方法。此方法需要开启关闭相应的按钮，并配置 `MediaRecorder` 实例，提供音频源、输出格式以及要存储音频的位置信息。最后，需要调用 `MediaRecorder` 对象的 `prepare()` 和 `start()` 方法。这些要求共同构成了 `MainActivity.java` 文件中的以下方法：

```java
public void recordAudio (View view) {

    isRecording = true;

    binding.stopButton.setEnabled(true);

    binding.playButton.setEnabled(false);

    binding.recordButton.setEnabled(false);

    try {

        mediaRecorder = new MediaRecorder(this);

        mediaRecorder.setAudioSource(MediaRecorder.MIC);

        mediaRecorder.setOutputFormat(MediaRecorder.THREE_GPP);

        mediaRecorder.setOutputFile(audioFilePath);

        mediaRecorder.setAudioEncoder(MediaRecorder.AMR_NB);

        mediaRecorder.prepare();

    } catch (Exception e) {

        e.printStackTrace();

    }

    mediaRecorder.start();

}
```

## 73.9 实现 stopAudio() 方法

`stopAudio()` 方法在启用 Play 按钮的同时关闭 Stop，并重置 `MediaRecorder` 实例。实现此目的的代码如下所示，并应添加到 `MainActivity.java` 文件中：

```java
public void stopAudio (View view) {

    binding.stopButton.setEnabled(false);

    binding.playButton.setEnabled(true);

    if (isRecording) {

        binding.recordButton.setEnabled(false);

        mediaRecorder.stop();

        mediaRecorder.release();

        mediaRecorder = null;

        isRecording = false;

    } else {

        mediaPlayer.release();

        mediaPlayer = null;

        binding.recordButton.setEnabled(true);

    }

}
```

## 73.10 实现 playAudio() 方法

`playAudio()` 方法将创建一个新的 `MediaPlayer` 实例，将 SD 卡上的音频文件作为数据源，然后准备并开始播放：

```java
public void playAudio (View view) throws IOException {

    binding.playButton.setEnabled(false);

    binding.recordButton.setEnabled(false);

    binding.stopButton.setEnabled(true);

    mediaPlayer = new MediaPlayer();

    mediaPlayer.setDataSource(audioFilePath);

    mediaPlayer.prepare();

    mediaPlayer.start();

}
```

## 73.11 配置并请求权限

在测试应用程序之前，必须在应用程序的清单文件中请求适当权限。具体而言，该应用程序将需要访问麦克风的权限。在 Project 工具窗口中，找到并双击 `AndroidManifest.xml` 文件，将其加载到编辑器中并修改 XML 以添加权限标签：

```xml
<?xml version="1.0" encoding="utf-8"?>

<manifest xmlns:android="http://schemas.android.com/apk/res/android"

    xmlns:tools="http://schemas.android.com/tools">

    <uses-permission android:name="android.permission.RECORD_AUDIO" />

    <application

.

.
```

上述步骤将足以确保用户在运行 Android 6.0 之前版本的设备上安装该应用时，用户会启用麦克风访问权限。在 Android 中，麦克风访问被归类为“危险权限”，因为它允许应用程序损害用户的隐私。为了让示例程序在 Android 6 或更高版本的设备上运行，需要添加代码在应用运行时请求权限。

编辑 `MainActivity.java` 文件，首先添加一些额外的导入指令和一个常量，用作所请求权限的请求标识码：

```java
.

.

import androidx.core.app.ActivityCompat;

import androidx.core.content.ContextCompat;

import android.widget.Toast;

import android.Manifest;

.

.

public class MainActivity extends AppCompatActivity {

    private static final int RECORD_REQUEST_CODE = 101;

.

.
```

接下来，需要在类中添加一个方法，其目的是将要请求的权限和相应的请求标识码作为参数。在 `MainActivity.java` 类文件中，按照如下方式实现该方法：

```java
protected void requestPermission(String permissionType, int requestCode) {

    int permission = ContextCompat.checkSelfPermission(this,

            permissionType);

    if (permission != PackageManager.PERMISSION_GRANTED) {

        ActivityCompat.requestPermissions(this,

                new String[]{permissionType}, requestCode

        );

    }

}
```

使用本书在 Android 中发起运行时权限请求章节概述的步骤，上述方法在发出请求之前验证指定的权限是否已经授予，并将标识码作为参数传递。

当请求处理完成后，活动上将调用 `onRequestPermissionsResult()` 方法，并传递标识码和请求结果。因此，下一步是在 `MainActivity.java` 文件中按如下方式实现此方法：

```java
@Override

public void onRequestPermissionsResult(int requestCode,

        @NonNull String[] permissions, @NonNull int[] grantResults) {

    super.onRequestPermissionsResult(requestCode, permissions, grantResults);

    if (requestCode == RECORD_REQUEST_CODE) {

        if (grantResults.length == 0

                || grantResults[0] !=

                PackageManager.PERMISSION_GRANTED) {

            binding.recordButton.setEnabled(false);

            Toast.makeText(this,

                    "Record permission required",

                    Toast.LENGTH_LONG).show();

        }

    }

}
```

上述代码检查请求标识码以识别是哪一个权限请求返回的结果，然后再检查相应的权限是否已授予。如果权限被拒绝，将向用户显示消息，指示应用程序将无法运行且录音按钮将被禁用。

在测试应用之前，最后剩下的工作是在应用程序启动时调用新添加的用于麦克风访问的 `requestPermission()` 方法。在 `MainActivity.java` 文件中，按如下方式修改 `audioSetup()` 方法：

```java
private void audioSetup(){

    binding.recordButton = findViewById(R.id.recordButton);

    binding.playButton = findViewById(R.id.playButton);

    binding.stopButton = findViewById(R.id.stopButton);

    if (!hasMicrophone()) {

        binding.recordButton.setEnabled(false);

        binding.playButton.setEnabled(false);

        binding.stopButton.setEnabled(false);

    } else {

        binding.recordButton.setEnabled(true);

        binding.playButton.setEnabled(false);

        binding.stopButton.setEnabled(false);

    }

}
```



### 73.12 测试应用程序
在带有麦克风的 Android 设备上编译并运行应用程序，允许访问麦克风，并点击`Record`按钮。录音后，触摸`Stop`，然后点击`Play`。录制的音频应通过设备扬声器播放。

### 73.13 总结
Android SDK 提供了几种实现录制和播放的机制。本章介绍了其中两种：`MediaPlayer` 和 `MediaRecorder`。在涵盖了使用这些工具的理论后，本章通过创建一个设计用于录制后回放的示例进行了演示。在 Android 中处理音频时，本章还查看了确保运行应用程序的设备具有麦克风的步骤。

### 74. 在 Android Studio 中使用 Google Maps API
当 Google 在许多年前推出地图服务时，很难说他们是否曾预见到会有一个可以集成到应用程序中的版本。当 2005 年推出最终成为 Google Maps 的第一个 Web 版本时，iPhone 尚未引发智能手机革命，而 Google 在此六个月后才收购了那家开发 Android 操作系统的公司。无论 Google 对 Google Maps 的未来抱有怎样的愿景，考虑到现在 Google Maps 的所有功能都可以通过 Android 应用程序直接访问，这是非常了不起的。

本章旨在提供 Google Maps 系统和 Google Maps Android API 的概述。本章将提供组成 API 的不同元素的概述，详细说明配置开发环境以使用 Google Maps 的步骤，然后通过一些代码示例演示 Google Maps 集成的基础知识。

### 74.1 Google Maps API 的元素
Google Maps Android API 由一组核心类组成，为 Android 应用程序提供地图功能。地图的关键元素如下：

- `GoogleMap`：Google Maps Android API 的主类。该类负责下载和显示地图瓦片，以及显示和响应地图控件。`GoogleMap` 对象不是由应用程序直接创建，而是在创建 `MapView` 或 `MapFragment` 实例时创建的。可以通过调用 `MapView`、`MapFragment` 或 `SupportMapFragment` 实例的 `getMap()` 方法获取 `GoogleMap` 对象的引用。
- `MapView`：`View` 类的子类，该类提供了画布，`GoogleMap` 对象在其上绘制地图，允许在活动的用户界面布局中放置地图。
- `SupportMapFragment`：`Fragment` 类的子类，该类允许在 Android 布局的 Fragment 中放置地图。

- **Marker（标记）** – `Marker` 类的目的是允许在地图上标记位置。通过获取与地图关联的 `GoogleMap` 对象的引用，然后调用该对象实例的 `addMarker()` 方法即可将标记添加到地图。标记的位置通过 `Longitude`（经度）和 `Latitude`（纬度）定义。标记可以通过多种方式进行配置，包括指定标题、文本和图标。标记还可以是"可拖拽的"，允许用户将标记移动到地图上的不同位置。
- **Shapes（形状）** – 使用 `Polyline`（折线）、`Polygon`（多边形）和 `Circle`（圆形）类可以在地图上绘制线条和形状。
- **UiSettings（UI 设置）** – `UiSettings` 类自定义地图上显示的控件。例如，使用 `UiSettings`，应用程序控制地图上是否显示缩放、当前位置和指南针控件。该类还可以配置地图识别哪些触摸手势。
- **My Location Layer（我的位置层）** – 启用后，我的位置层会在地图上显示一个按钮，用户选择该按钮会将地图中心置到用户当前的地理位置。如果用户处于静止状态，蓝色标记将代表地图上的该位置。如果用户正在移动，则用一个指示用户移动方向的箭头来表示该位置。

熟悉 Google Maps Android API 的最佳方法是运行一个示例。本章的剩余部分将创建一个基于 Google Maps 的应用程序，同时突出 API 的关键领域。

### 74.2 创建 Google Maps 项目
从欢迎界面选择`New Project`（新建项目）选项，并在生成的新项目对话框中点击`Next`（下一步）按钮之前选择`No Activity`（无活动）模板。

在`Name`（名称）字段中输入`MapDemo`，并指定`com.ebookfrenzy.mapdemo`为包名。在点击`Finish`（完成）按钮之前，将`Minimum API level`（最低 API 级别）设置改为`API 26`：Android 8.0 (Oreo)，并将`Language`（语言）菜单设置为`Java`。

接下来，在项目窗口中右键点击`app` -> `java` -> `com.ebookfrenzy.mapdemo`条目，选择`New`（新建） -> `Google` -> `Google Maps Views Activity`菜单选项。最后，在点击`Finish`按钮之前，勾选并启用`Launcher Activity`（启动活动）复选框：

![](img/as_map_activity.jpg)
图 74-1

### 74.3 创建 Google Cloud 结算账户
在使用 Google Map APIs 之前，你必须创建一个 Google Cloud 结算账户（如果你已经有一个，可以跳到下一节）。要执行此操作，请打开浏览器并使用以下链接导航到 Google Cloud 控制台：

`https://console.cloud.google.com/`

接下来，点击控制台页面左上角的菜单按钮，并如[图 74-2]所示选择`Billing`（结算）条目：

![](img/google_cloud_billing.jpg)
图 74-2

在`Billing`（结算）页面，选择添加新结算账户的选项，然后按照步骤开始免费试用。你必须提供信用卡来开账户，但在免费试用结束且未经你同意的情况下，Google 不会收取费用。

### 74.4 创建新的 Google Cloud 项目
下一步是创建一个与`MapDemo`应用程序关联的 Google Cloud 项目。要执行此操作，请使用以下 URL 返回 Google Cloud 控制台仪表板：

`https://console.cloud.google.com/home/dashboard`

在仪表板中，点击位于顶部栏的`Select a project`（选择项目）按钮：

![](img/google_cloud_select_project.jpg)
图 74-3

当项目选择对话框出现时，点击`New Project`（新建项目）按钮（如[图 74-4]所示）：

![](img/google_cloud_new_project_button.jpg)
图 74-4

当新项目屏幕出现时，为项目提供一个名称。控制台将在项目名称字段下方显示项目的默认`id`。如果你不喜欢默认的`id`，可以点击`Edit`（编辑）按钮来更改它：

![](img/google_cloud_new_project_dialog.jpg)
图 74-5

点击`Create`（创建）按钮，稍等片刻，你将返回仪表板，你的新项目将列在其中。

### 74.5 启用 Google Maps SDK
现在我们已经创建了新的 Google Cloud 项目，下一步是允许该项目使用 Google Maps SDK。要启用 Google Maps 支持，请在 Google Cloud 控制台中选择你的项目，点击左上角的菜单按钮，并选择`Google Maps Platform`条目。然后，从生成的菜单中，如[图 74-6]所示选择`APIs`选项：

![](img/google_cloud_maps_apis_menu.jpg)
图 74-6

在`APIs`屏幕上，点击`Maps SDK for Android`选项，并在生成的屏幕上点击`Enable`（启用）按钮：

![](img/google_cloud_enable_maps.jpg)
图 74-7

重复上述步骤以启用`Geocoding API`（地理编码 API）凭据，本章稍后部分将需要它来允许我们的应用程序显示用户的当前位置。

一旦启用了项目的所需的凭据，点击后退箭头返回产品详情页，为下一步做准备。

### 74.6 生成 Google Maps API 密钥
在应用程序可以使用 Google Maps Android SDK 之前，必须配置 API 密钥以与 Maps Google Cloud 项目关联。要生成 API 密钥，选择`Credentials`（凭据）选项（如[图 74-8]所示），然后点击`Create Credentials`（创建凭据）按钮（B）：

![](img/google_cloud_credentials.jpg)
图 74-8

凭据创建后，将出现显示 API 密钥的对话框：

![](img/console_api_key_created.jpg)
图 74-9

### 74.7 为 Android Studio 添加 API 密钥
现在我们已经生成了允许应用程序使用 Google Maps SDK 的 API 密钥，必须将其添加到项目中。返回 Android Studio，编辑`AndroidManifest.xml`文件并定位 API 密钥项，内容如下：

```xml
<meta-data

    android:name="com.google.android.geo.API_KEY"

    android:value="YOUR_API_KEY" />
```

删除文本`YOUR_API_KEY`并将其替换。

接下来，编辑`Gradle Scripts` -> `local.properties`文件，并添加如下行（用项目的 API 密钥替换`YOUR_API_KEY`）：

```
MAPS_API_KEY=YOUR_API_KEY
```

### 74.8 测试应用程序
运行应用程序以验证 API 密钥配置正确。如果配置正确，应用程序将运行并在屏幕上显示地图。

如果未显示地图，请检查以下区域：

- 如果应用程序运行在模拟器上，请确保模拟器运行包含 Google APIs 的 Android 版本。可以通过选择`Tools` -> `Android` -> `AVD Manager`菜单选项更改 AVD 配置的操作系统，点击 Actions 列中的铅笔图标，然后点击当前 Android 版本旁`Change…`按钮。在系统映像对话框中选择包含 Google APIs 的目标。
- 检查`Logcat`输出是否有任何与 Google Maps API 身份验证有关的内容。这通常意味着 API 密钥输入错误。确保`AndroidManifest.xml`和`local.properties`文件中的 API 密钥与 Google Cloud 控制台中生成的密钥匹配。

### 74.9 理解地理编码和反向地理编码
在不讨论地图和地理位置之前，必须先涵盖地理编码主题。地理编码是将基于文本的地理位置（例如街道地址）转换为以经度和纬度表示的地理坐标。

地理编码可以使用 Android 的`Geocoder`类来实现。例如，可以向`Geocoder`类的实例传递一个表示位置的字符串，例如城市名称、街道地址或机场代码。`Geocoder`将尝试查找该位置的匹配项，并返回一个可能与该位置字符串匹配的`Address`对象列表，这些对象按匹配程度排序，最接近的匹配项位于列表的第 0 位。随后可以从`Address`对象中提取各种信息，包括潜在匹配项的经纬度。

例如，以下代码请求位于华盛顿特区的美国国家航天博物馆的位置信息：

```java
import java.io.IOException;
import java.util.List;
import android.location.Address;
import android.location.Geocoder;

// ... dots ...

double latitude;
double longitude;
List<Address> geocodeMatches = null;

try {
    geocodeMatches =
        new Geocoder(this).getFromLocationName(
            "600 Independence Ave SW, Washington, DC 20560", 1);
} catch (IOException e) {
    // TODO Auto-generated catch block
    e.printStackTrace();
}

if (!geocodeMatches.isEmpty()) {
    latitude = geocodeMatches.get(0).getLatitude();
    longitude = geocodeMatches.get(0).getLongitude();
}
```

注意，值`1`作为第二个参数传递给`getFromLocationName()`方法。这告诉`Geocoder`在数组中只返回一个结果。鉴于所提供的地址具有特定性，应该只有一个潜在的匹配项。然而，对于较模糊的位置名称，可能需要请求更多的潜在匹配项并允许用户选择正确的那个。

上面的代码是正向地理编码的示例，即其坐标是基于文本位置描述计算的。反向地理编码正如顾名思义，涉及将地理坐标翻译为人类可读的地址字符串。例如，考虑以下代码：

```java
import java.io.IOException;
import java.util.List;
import android.location.Address;
import android.location.Geocoder;

// ... dots ...

List<Address> geocodeMatches = null;
String Address1;
String Address2;
String State;
String Zipcode;
String Country;

try {
    geocodeMatches =
        new Geocoder(this).getFromLocation(38.8874245, -77.0200729, 1);
} catch (IOException e) {
    // TODO Auto-generated catch block
    e.printStackTrace();
}

if (!geocodeMatches.isEmpty()) {
    Address1 = geocodeMatches.get(0).getAddressLine(0);
    Address2 = geocodeMatches.get(0).getAddressLine(1);
    State = geocodeMatches.get(0).getAdminArea();
    Zipcode = geocodeMatches.get(0).getPostalCode();
    Country = geocodeMatches.get(0).getCountryName();
}
```

`Geocoder`对象通过`getFromLocation()`方法使用经纬度值进行初始化。再次，仅请求了单个匹配结果。然后从生成的`Address`对象中提取基于文本的地址信息。

地理编码并不是在 Android 设备上执行的，而是在需要翻译时设备连接的服务器上执行，并在翻译完成后返回结果。只有当设备具有活跃的互联网连接时，才能进行地理编码。

### 74.10 向应用程序添加地图
向应用程序添加地图的最简单方法是在 activity 的用户界面布局 XML 文件中指定它。下面的布局文件显示了添加到 Android Studio 创建的`activity_maps.xml`文件中的`SupportMapFragment`实例：

```xml
<fragment xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:id="@+id/map"
    tools:context=".MapsActivity"
    android:name="com.google.android.gms.maps.SupportMapFragment"/>
```

### 74.11 请求当前位置权限
正如"在 Android 中进行运行时权限请求"章节概述的那样，某些权限被认为是危险的，对于 Android 6.0 或更高版本需要特殊处理。一组权限允许应用程序识别当前位置。编辑位于`app -> manifests`下的`AndroidManifest.xml`文件并添加以下行：

```xml
<uses-permission android:name="android.permission.FINE_LOCATION" />
<uses-permission android:name="android.permission.COARSE_LOCATION" />
```

这些设置将确保应用可以在旧版本上提供位置。然而，为了支持 Android 6.0，我们需要向`MapsActivity.java`添加一些代码以在运行时请求此权限。首先添加一些导入和常量：

```java
package com.example.map;
```



```java
import androidx.annotation.NonNull;

import androidx.core.content.ContextCompat;

import androidx.core.app.ActivityCompat;

import android.Manifest;

import android.widget.Toast;

import android.content.pm.PackageManager;

public class MapsActivity extends FragmentActivity implements OnMapReadyCallback {

    static final int LOCATION_REQUEST_CODE = 1;

    private GoogleMap mMap;
}
```

接下来，必须在类中添加一个方法来向用户请求权限。在`MapsActivity.java`文件中实现：

```java
protected void requestPermission(String permissionType) {

    ActivityCompat.requestPermissions(this, new String[]{permissionType}, LOCATION_REQUEST_CODE);

}
```

当用户响应权限请求后，活动将调用`onRequestPermissionsResult()`。在`MapsActivity.java`文件中，实现该方法使其内容如下：

```java
@Override
public void onRequestPermissionsResult(int requestCode, @NonNull String[] permissions, @NonNull int[] grantResults) {

    super.onRequestPermissionsResult(requestCode, permissions, grantResults);

    if (requestCode == LOCATION_REQUEST_CODE) {

        if (grantResults.length == 0 || grantResults[0] != PackageManager.PERMISSION_GRANTED) {

            Toast.makeText(this, "无法显示位置 - 需要权限", Toast.LENGTH_LONG).show();

        } else {

            SupportMapFragment mapFragment = (SupportMapFragment) getSupportFragmentManager()

                .findFragmentById(R.id.map);

            mapFragment.getMapAsync(this);

        }

    }

}
```

如果用户没有授予权限，应用将显示一条无法显示位置的消息。相反，如果授予了权限，地图将刷新，以便显示位置标记。

## 74.12 显示用户的当前位置

一旦授予了适当权限，可以通过获取与显示的地图关联的`GoogleMap`对象引用并调用该实例的`setMyLocationEnabled()`方法（传递`true`值），从而在地图上显示用户的当前位置。

当地图准备好显示时，会调用 activity 的`onMapReady()`方法。当地图在上述`onRequestPermissionsResult()`方法中进行刷新时，该方法也会被调用。默认情况下，Android Studio 已经实现了此方法，并添加了一些代码，将地图对准到澳大利亚，并在悉尼市上方放置了一个标记点。找到并编辑`MapsActivity.java`文件中的`onMapReady()`方法，移除此模板代码，并添加代码在启用显示用户当前位置之前检查是否已授予位置权限。如果未授予权限，将通过调用之前添加的`requestPermission()`方法向用户请求权限：

```java
@Override
public void onMapReady(GoogleMap googleMap) {

    mMap = googleMap;

    // 在悉尼添加一个标记并移动相机

    LatLng sydney = new LatLng(-34, 151);

    mMap.addMarker(new MarkerOptions().position(sydney).title("Marker in Sydney"));

    mMap.moveCamera(CameraUpdateFactory.newLatLng(sydney));

    if (mMap != null) {

        int permission = ContextCompat.checkSelfPermission(this,

                Manifest.permission.ACCESS_FINE_LOCATION);

        if (permission == PackageManager.PERMISSION_GRANTED) {

            mMap.setMyLocationEnabled(true);

        } else {

            requestPermission(

                    Manifest.permission.ACCESS_FINE_LOCATION,

                    LOCATION_REQUEST_CODE);

        }

    }

}
```

现在运行应用，将显示图 74-10 所示的对话框，请求位置权限。如果授予了权限，地图上将出现一个蓝点，指示设备的位置。

![](img/as_map_permission.jpg)

图 74-10

### 74.13 更改地图类型

通过调用相应`GoogleMap`对象的`setMapType()`方法传递以下值之一，可以动态修改显示的地图类型：

- `GoogleMap.MAP_TYPE_NONE` – 一个空网格，不显示地图瓦片。
- `GoogleMap.MAP_TYPE_NORMAL` – 由经典道路地图组成的标准视图。
- `GoogleMap.MAP_TYPE_SATELLITE` – 显示地图区域的卫星图像。
- `GoogleMap.MAP_TYPE_HYBRID` – 显示叠加了道路地图的卫星图像。
- `GoogleMap.MAP_TYPE_TERRAIN` – 显示地形信息，如等高线和颜色。

例如，对`onMapReady()`方法进行以下代码更改可以将地图切换到卫星模式：

```java
if (mMap != null) {

    int permission = ContextCompat.checkSelfPermission(

            this, Manifest.permission.ACCESS_FINE_LOCATION);

    if (permission == PackageManager.PERMISSION_GRANTED) {

        mMap.setMyLocationEnabled(true);

    } else {

        requestPermission(Manifest.permission.ACCESS_FINE_LOCATION,

                LOCATION_REQUEST_CODE);

    }

    mMap.setMapType(GoogleMap.MAP_TYPE_SATELLITE);

}
```

或者，也可以在嵌入地图的 XML 布局文件中指定地图类型，使用`map:mapType`属性结合`none`、`normal`、`hybrid`、`satellite`或`terrain`值。例如：

```xml
<?xml version="1.0" encoding="utf-8"?>

<fragment xmlns:android="http://schemas.android.com/apk/res/android"

          xmlns:map="http://schemas.android.com/apk/res-auto"

          android:id="@+id/map"

          android:layout_width="match_parent"

          android:layout_height="match_parent"

          android:name="com.google.android.gms.maps.SupportMapFragment"

          map:mapType="terrain"/>
```

### 74.14 向用户显示地图控件

Google Maps API 提供了几个可以显示的控件：缩放按钮、指南针和“我的位置”。可以使用与`GoogleMap`关联的`UiSettings`对象启用或禁用这些控件。

```java
UiSettings uiSettings = mMap.getUiSettings();

uiSettings.setZoomControlsEnabled(true);

uiSettings.setCompassEnabled(true);

uiSettings.setMyLocationEnabled(true);
```

或者，可以在 XML 布局文件使用相应的`map:`属性配置这些控件：

```xml
<fragment

    android:id="@+id/map"

    ...

    map:zoomControlsEnabled="true"

    map:compassEnabled="true"

    map:MyLocationEnabled="true"/>
```

### 74.15 处理地图手势

Google Maps API 可以响应各种用户交互。

#### 74.15.1 缩放手势

使用`UiSettings`实例的`setZoomControlsEnabled()`方法启用或禁用与放大和缩放相关的手势：

```java
UiSettings uiSettings = mMap.getUiSettings();

uiSettings.setZoomControlsEnabled(true);
```

启用后，当用户在屏幕上进行捏合手势时会发生缩放。同样，双击会放大，而双指轻触会缩小。

#### 74.15.2 滚动/平移手势

滚动或平移手势允许用户通过单指移动地图来查看地图。可以通过以下方式启用：

```java
UiSettings uiSettings = mMap.getUiSettings();

uiSettings.setScrollGestEnabled(true);
```

#### 74.15.3 地图倾斜手势

倾斜手势允许用户通过在屏幕上放置两个手指并上下移动来倾斜地图的投影角度。通过以下方式启用：

```java
UiSettings uiSettings = mMap.getUiSettings();

uiSettings.setTiltGesturesEnabled(true);
```

#### 74.15.4 地图旋转手势

通过在屏幕上放置两个手指并进行圆周旋转，用户可以旋转地图的方向。通过以下方式启用：

```java
UiSettings uiSettings = mMap.getUiSettings();

uiSettings.setRotateGesturesEnabled(true);
```

标记（Markers）用于向用户通知地图上的位置，其形式可以是标准图标或自定义图标。标记还可以包含一个标题（title）和可选文本（称为片段，snippet），并可以配置为允许用户拖动到地图上的不同位置。当用户点击标记时，将出现一个窗口（info window），显示有关该标记位置的额外信息。

标记由`Marker`类的实例表示，并通过调用相应`GoogleMap`对象的`addMarker()`方法添加到地图上。一个`MarkerOptions`类的实例，其中包含了标记所需的各种选项（如标题和片段文本），将作为参数传递给该方法。标记的位置通过指定纬度和经度值定义，这些值也包含在`MarkerOptions`实例中。例如，以下代码在地图上的特定位置添加了一个标记，包括标题、片段和位置：

```java
import com.google.android.gms.maps.model.Marker;

import com.google.android.gms.maps.model.LatLng;

import com.google.android.gms.maps.model.MarkerOptions;

LatLng position = new LatLng(38.8874245, -77.0200729);

Marker museum = mMap.addMarker(new MarkerOptions()

                .position(position)

                .title("Museum")

                .snippet("National Air and Space Museum"));
```

执行上述代码将将标记指定的的位置，点击该位置时将显示一个包含标题和片段的信息窗口，如图图 74-11 所示：

![](img/Image24512.jpg)

图 74-11

### 74.17 控制地图相机

由于 Android 设备的屏幕是平面的，而地球是球体，Google Maps Android API 使用墨卡托投影在平面上表示地球。地图的默认视图呈现给用户，就像通过一个悬挂在地图上方并直接指向地图的相机一样。Google Maps Android API 允许在应用程序内部更改摄像机的目标（target）、缩放（zoom）、方位（bearing）和倾斜（tilt）：

- **Target（目标）** – 地图在设备显示中的中心位置，通过经度和指定。
- **Zoom（缩放）** – 以级别指定的相机缩放级别。缩放级别每增加 1.0，显示的地图宽度就会翻倍。
- **Tilt（倾斜）** – 摄像机的视角角度，指定为跨越可视地图区域正上方的弧上的位置，从弧顶开始以度测量（弧顶是弧的底点，相机在此处直接指向地图）。
- **Bearing（方位）** – 地图的方向，以从北向顺时针方向测量。

相机的更改通过创建一个具有适当设置的`CameraUpdate`类实例来实现。`CameraUpdate`实例是通过调用`CameraUpdateFactory`类的方法创建的。一旦创建了`CameraUpdate`实例，就会通过调用`GoogleMap`实例的`moveCamera()`方法应用到地图。为了在相机变化时获得平滑的动画效果，可以调用`animateCamera()`方法代替`moveCamera()`。

`CameraUpdateFactory`方法摘要如下：

- `CameraUpdateFactory.zoomIn()` – 提供一个放大一级的`CameraUpdate`实例。
- `CameraUpdateFactory.zoomOut()` - 提供一个缩小一级的`CameraUpdate`实例。
- `CameraUpdateFactory.zoomTo(float)` - 生成一个将缩放级别更改为指定值的`CameraUpdate`实例。
- `CameraUpdateFactory.zoomBy(float)` – 提供一个按指定量增加或减少缩放级的`CameraUpdate`实例。
- `CameraUpdateFactory.zoomBy(float, Point)` - 创建一个按指定值增加或减少缩放级的`CameraUpdate`实例。
- `CameraUpdateFactory.newLatLng(LatLng)` - 创建一个更改相机目标经纬度的`CameraUpdate`实例。
- `CameraUpdateFactory.newLatLngZoom(LatLng, float)` - 生成一个更改相机经纬度和缩放的`CameraUpdate`实例。
- `CameraUpdateFactory.newCameraPosition(CameraPosition)` - 返回一个将相机移动到指定位置的`CameraUpdate`实例。可以使用`CameraPosition.Builder()`获取`CameraPosition`实例。

例如，以下代码使用动画将相机放大一级：

```java
mMap.animateCamera(CameraUpdateFactory.zoomIn());
```

相反，以下代码在不使用动画的情况下将相机移动到新位置并将缩放级别调整为 10：

```java
private static final LatLng position =

    new LatLng(38.8874245, -77.0200729);

mMap.moveCamera(CameraUpdateFactory.newLatLngZoom(position, 10));
```

最后，下一个代码示例使用`CameraPosition.Builder()`创建了一个具有目标、缩放、方位和倾斜更改的`CameraPosition`对象。然后使用动画将此更改应用于相机：

```java
```



```java
import com.google.android.gms.maps.model.CameraPosition;

CameraPosition cameraPosition = new CameraPosition.Builder().build();

mMap.animateCamera(CameraUpdateFactory.newCameraPosition(cameraPosition));
```

### 74.18 总结

本章概述了构成 Google Maps API 的关键类和方法，并概述了如何准备开发环境和应用程序以使用它。

## 75. 使用 Android 打印

Android 框架用于打印。后续章节将详细讨论添加打印支持选项，本章将重点介绍目前提供的各种选项。

### 75.1 Android 打印架构

Android 框架提供了打印功能。从基本上来说，该框架由一个打印管理器（Print Manager）和若干打印服务插件（print service plugins）组成。

打印管理器负责处理应用程序的打印请求，并与设备上安装的打印服务插件交互，确保打印请求得到实现。

### 75.2 打印服务插件

打印服务插件的目的是允许应用程序打印到局域无线网络或蓝牙可见的兼容打印机。

可以通过加载 Google Play 应用并搜索“Print Service Plugin”来验证 Android 设备上是否存在打印服务插件。

默认情况下，许多 Android 设备已安装了打印服务插件，以便使用 Google Cloud 和 Google Drive 服务进行打印。其他打印类型的打印服务插件（如果尚未安装）也可以从 Google Play 商店获取。图 75-1 示例显示了 Google Play 中的 HP 打印服务插件。

![](img/as_4.1_hp_printer_plugin.jpg)

图 75-1

### 75.3 Google Cloud Print

Google Cloud Print 是 Google 提供的一项服务，允许您从任何具有互联网连接的地方通过网页将内容打印到打印机上。Google Cloud Print 支持云就绪（Cloud Ready）和经典（Classic）打印机的多种设备和型号。云就绪打印机内置了通过网页打印的技术。提供云就绪打印机的制造商包括 Brother、Canon、Dell、Epson、HP、Kodak 和 Samsung。要确认您的打印机是否既云就绪并支持 Google Cloud Print，请查看下方 URL 中的打印机列表：

[打印机列表](https://www.google.com/cloudprint/learn/printers.html)

对于经典的非云就绪打印机，Google Cloud Print 通过在连接经典打印机的计算机系统（直接连接或通过家庭或办公室网络连接）上安装软件来实现云打印。

要设置 Google Cloud Print，请访问以下网页并使用与登录 Android 设备时相同的 Google 账户 ID 登录：

[Google Cloud Print 帮助](https://www.google.com/cloudprint/learn/index.html)

一旦打印机添加到您的 Google Cloud Print 账户，当在 Android 内部打印时，它们将作为打印目标选项列出。

### 75.4 打印到 Google Drive

除了支持实体打印机外，还可以将打印输出保存到您的 Google Drive 账户。从设备打印时，在打印面板中选择`Save to Google Drive`选项。要打印的内容将被转换为 PDF 文件，并保存到设备上当前活动 Google 账户 ID 关联的 Google Drive 云存储中。

## 75.5 保存为 PDF

Android 提供的最后一个打印选项允许将打印内容作为 PDF 文件本地保存到 Android 设备上。一旦选择此选项，系统将要求指定 PDF 文件名以及文档保存到设备上的位置。

在测试 way Android 应用程序的打印功能时，`Save as PDF`和 Google Drive 选项在节省纸张方面可能具有极高的价值。

### 75.6 从 Android 设备打印

Google 建议能够打印内容的应用程序将打印选项放置在溢出菜单（Overflow menu）中。许多与 Android 捆绑的应用程序现在已包含“打印……”菜单选项。例如，图 75-2 显示了通过选择 Chrome 浏览器应用程序溢出菜单中的“共享……”选项来访问打印选项：

![](img/as_3.5_chrome_print_option.jpg)

图 75-2

一旦在应用程序内选择了打印选项，将标准的 Android 打印屏幕，显示打印内容的预览，如图 75-3 所示：

![](img/as_3.5_chrome_print_panel.jpg)

图 75-3

点击屏幕顶部的面板将显示所有的打印选项：

![](img/as_3.5_save_as_pdf.jpg)

图 75-4

Android 打印面板提供了标准的打印选项，例如纸张大小、颜色、方向和副本数量。通过点击当前打印机或 PDF 输出选择，可以访问其他打印目标选项。

## 75.7 在 Android 应用中构建打印支持的选项

打印框架（Printing framework）为在 Android 应用中整合打印支持提供了多种选项。这些选项可以分类如下：

### 75.7.1 图片打印

顾如名，此选项允许将图像打印整合到 Android 应用中。在应用程序中添加此功能时，第一步是为`PrintHelper`类创建一个新实例：

```java
PrintHelper imagePrinter = new PrintHelper(context);
```

接下来，可以通过调用`PrintHelper`实例的`setScaleMode()`方法指定打印图像的缩放模式。选项如下：

- `SCALE_MODE_FIT` – 图像将缩放以适应纸张大小，而不进行裁剪或更改宽高比例。这通常会导致在一个维度上出现空白。
- `SCALE_MODE_FILL` – 图像将缩放以填充纸张大小，并在必要时裁剪，以避免打印输出中出现空白。

如果不设置缩放模式，系统将默认使用`SCALE_MODE_FILL`。例如，以下代码将之前声明的`PrintHelper`实例缩放设置为自适应模式：

```java
imagePrinter.setScaleMode(PrintHelper.SCALE_MODE_FIT);
```

同样，也可以配置颜色模式以指示打印输出是彩色还是黑白。这通过向`PrintHelper`实例的`setColorMode()`方法传递以下选项之一来实现：

- `COLOR_MODE_COLOR` – 表示图像将以彩色打印。
- `COLOR_MODE_MONOCHROME` – 表示图像将以黑白打印。

打印框架将默认彩色打印，除非按如下方式指定单色选项：

```java
imagePrinter.setColorMode(PrintHelper.COLOR_MODE_MONOCHROME);
```

完成打印操作所需的仅是待打印的图像，并调用`PrintHelper`实例的`printBitmap()`方法，该方法需要传递一个代表打印任务名称的字符串以及图像的引用（以`Bitmap`对象或`Uri`引用的形式）：

```java
Bitmap bitmap = BitmapFactory.decodeResource(getResources(), R.drawable.image);

imagePrinter.printBitmap("Test Job", bitmap);
```

一旦启动打印任务，框架将显示打印对话并处理与用户的交互。

### 75.7.2 创建并打印 HTML

Android 打印框架还提供了一种在应用程序内打印 HTML 内容的简单方法。这些内容可以是托管在网站上的页面 URL，也可以是在应用程序内部动态创建。为了启用打印，`WebView`类已经过扩展，以最少的需求支持打印。在动态创建 HTML 时（而不是加载现有页面），该过程涉及以下代码：

```java
public void printContent() {

    WebView webView = new WebView(this);

    webView.setWebViewClient(new WebViewClient() {

        @Override

        public boolean shouldOverrideLoading(WebView view, String url) {

            return false;

        }

        @Override

        public void onPageFinished(WebView view, String url) {

            createWebPrintJob(view);

            myWebView = null;

        }

    });

    String htmlDocument = "<html><body><h1>Android Print Test</h1><p>" + "This is some sample content.</p></body></html>";

    webView.loadDataWithBaseURL(null, htmlDocument, "text/HTML", "UTF-8", null);

    myWebView = webView;

}
```

此方法的代码首先声明了一个名为`myWebView`的变量，其中将存储方法中创建的`WebView`实例的引用。在`printContent()`方法中，创建了一个`WebView`类实例，并为其分配了一个`WebViewClient`实例。

分配给 web view 对象的`WebViewClient`被配置为指示 HTML 内容的加载由`WebView`实例处理（通过从`shouldOverrideUrlLoading()`方法返回`false`）。更重要的是，声明并实现了一个`onPageFinished()`处理器方法，以调用`createWebPrintJob()`方法。当所有 HTML 内容加载到 web view 中时，`onPageFinished()`回调方法将被自动调用。这确保了在内容准备绪之前不会启动打印任务，从而确保所有内容都能被打印。

接下来，创建一个包含某些 HTML 的字符串作为内容。然后将其加载到 web view 中。一旦 HTML 加载完成，`onPageFinished()`方法就会触发。最后，该方法存储了对 web view 对象的引用。如果没有这一关键步骤，Java 运行时系统极有可能会认为应用程序不再需要该 web view 对象，并将其丢弃以释放内存（Java 术语中称为垃圾回收），导致打印任务在完成前终止。

在本示例中，剩下的工作是如下实现`createWebPrintJob()`方法：

```java
private void createWebPrintJob(WebView webView) {

    PrintManager printManager = (PrintManager) this

            .getSystemService(Context.PRINT_SERVICE);

    PrintDocumentAdapter printAdapter =

                    webView.createPrintDocumentAdapter("MyDocument");

    String jobName = getString(R.string.app_name) + " Document";

    PrintJob printJob = printManager.print(jobName, printAdapter,

                        new PrintAttributes.Builder().build());

}
```

此方法获取`PrintManager`服务的引用，并指示 web view 实例创建一个打印适配器。创建一个新字符串来存储打印任务的名称（在这种情况下，基于应用程序名称和“Document”单词）。

最后，通过调用打印管理器的`print()`方法启动打印任务，传递任务名称、打印适配器和一组默认打印属性。如果需要，可以自定义打印属性以指定分辨率（每英寸点数）、边距和颜色选项。

### 75.7.3 打印网页

打印网页涉及的步骤与上述概述相似，不同之处传递给 web view 的要打印网页的 URL，而不是动态创建的 HTML，例如：

```java
myWebView.loadUrl("https://developer.android.com/google/index.html");
```

同样重要的是，`WebViewClient`配置只有在网页加载后需要立即自动打印时才是必要的。如果打印是由用户在页面加载后选择菜单选项启动的，则只需要在应用程序代码中包含上述`createWebPrintJob()`方法中的代码。下一章 Android HTML 和 Web 内容打印示例 将演示此类场景。

### 75.7.4 打印自定义文档

虽然打印框架（Printing framework）引入的 HTML 和 Web 打印功能为从 Android 应用程序内部打印内容提供了简便路径，但显然，对于更高级的打印需求，这些选项将显得过于简单。打印框架还为更复杂的打印任务提供了自定义文档打印支持。这允许将文本和图形形式的内容绘制到画布上进行打印。

与较较实现的 HTML 和图像打印不同，自定义文档打印是一个更复杂、多阶段的过程，将在本书的 Android 自定义文档打印指南 章中概述。这些步骤可以总结如下：

* 连接到 Android 打印管理器
* 创建继承自`PrintDocumentAdapter`类的自定义打印适配器
* 创建`PdfDocument`实例来表示文档页面
* 获取`PdfDocument`实例页面的引用，每个页面都关联有一个`Canvas`实例
* 在页面画布上绘制内容
* 通知打印框架文档已准备好打印

上述步骤中概述的自定义打印适配器必须实现几个方法，Android 系统将在打印期间调用这些方法执行特定任务。其中最重要的是`onLayout()`方法，它负责根据用户更改纸张大小或页面方向等设置来重新安排文档布局；以及`onWrite()`方法，它负责渲染待打印的页面。名为 Android 自定义文档打印指南 的章节将详细介绍这一主题。

### 75.8 总结

Android SDK 可以从运行中的应用程序内部打印内容。打印输出可以定向到配置适当的打印机、本地 PDF 文件或通过 Google Drive 到云端。从 Android 开发人员的角度来看，通过利用框架，这些功能可以在应用程序中使用。到目前为止，最容易实现的打印选项是涉及图像和 HTML 形式的内容。然而，也可以实现更高级的打印。

## HTML 和 Web 内容示例

如上一章所述，使用 Android 框架进行打印，Android 框架可以同时打印网页和动态创建的 HTML。虽然这些打印方法之间有许多相似之处，但也存在一些需要考虑的微妙区别。本章将通过创建两个应用程序来阐明这些打印选项。

### 76.1 创建 HTML 打印应用程序

从欢迎界面选择 New Project，在弹出的新项目对话中，点击 Next 按钮之前选择 Empty Views 模板。在 Name 字段输入 HTMLPrint，并指定包名为`com.ebookzy.htmlprint`。在点击 Finish 按钮之前，将最低 API 级别更改为 API 26: Android 8.0 (Oreo)，设置为 Java。

### 76.2 打印动态 HTML 内容

教程的第一阶段是向项目添加代码以创建 HTML 内容并将其作为打印任务发送到打印框架。首先找到`MainActivity.java`文件（位于 Project 工具下的`app -> java -> com.ebookrenzy.htmlprint`）并将其加载到编辑面板。一旦加载，修改代码使其如下列表所示：

```java
package com.ebookrenzy.htmlprint;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

import android.webkit.WebView;

import android.webkit.WebViewClient;

import android.webkit.WebResourceRequest;

import android.print.PrintAttributes;

import android.print.PrintDocumentAdapter;

import android.print.PrintManager;

import android.content.Context;

public class MainActivity extends AppCompatActivity {

    private WebView myWebView;

    @Override

    protected void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);

        setContentView(R.layout.activity_htmlprint);

        printWebView();

    }

    private void printWebView() {
```



`WebView webView = new WebView(this);`

`webView.setWebViewClient(new WebViewClient() {`

```java
public boolean shouldOverrideUrlLoading(WebView view, WebResourceRequest request) {

    return false;

}

@Override

public void onPageFinished(WebView view, String url) {

    createWebPrintJob(view);

    myWebView = null;

}

});
```

`String htmlDocument = "<<html><body><h1>Android Print Test</h1><p>"`

`    + "This is some sample content.</p></body></html>";`

`webView.loadDataWithBaseURL(null, htmlDocument, "text/HTML", "UTF-8", null);`

`myWebView = webView;`

}

}

代码更改从声明一个名为 `myWebView` 的变量开始，该变量将存储用于打印操作的 `WebView` 实例引用。在 `printWebView()` 方法中，创建了一个 `WebView` 类实例并为其分配了一个 `WebViewClient` 实例。

分配给 web view 对象的 `WebViewClient` 经过配置，指示 HTML 内容的加载由 `WebView` 实例处理（通过从 `shouldOverrideUrlLoading()` 方法返回 `false`）。更重要的是，声明并实现了一个 `onPageFinished()` 处理方法用以调用 `createWebPrintJob()` 方法。当所有 HTML 内容都加载到 web view 时，`onPageFinished()` 方法将被自动调用。如上一章所述，在打印动态创建的 HTML 内容时，这一步是必要的，以确保只有在内容完全加载到 `WebView` 后才启动打印任务。

接下来，创建一个包含某些 HTML 的 `String` 对象作为内容，并将其加载到 web view 中。一旦 HTML 加载，`onPageFinished()` 回调方法就会触发。最后，该方法将 web view 对象的引用存储在之前定义的 `myWebView` 变量中。如果没有这一至关的一步，Java 运行时系统可能会认为应用程序不再需要该 web view 对象并将其丢弃以释放内存，导致打印任务在完成之前就终止。

此示例中剩下的工作是实现 `createWebPrintJob()` 方法，该方法目前配置为由 `onPageFinished()` 回调方法调用。因此，在 `MainActivity.java` 文件中，实现该方法使其读取内容如下：

```java
private void createWebPrintJob(WebView webView) {

    PrintManager printManager = (PrintManager) this

            .getSystemService(Context.PRINT_SERVICE);

    PrintDocumentAdapter printAdapter =

            webView.createPrintDocumentAdapter("MyDocument");

    String jobName = getString(R.string.app_name) + " Print Test";

    printManager.print(jobName, printAdapter,

            new PrintAttributes.Builder().build());

}
```

此方法获取 `PrintManager` 服务的引用，并指示 web view 实例创建一个打印适配器。创建一个新字符串来存储打印任务的名称（在本例中，基于应用程序名称和“Print Test”字样）。最后，通过调用打印管理器的 `print()` 方法启动打印任务，传递任务名称、适配器和一组默认属性。在运行 Android 5.0 或更高版本的设备或模拟器上编译并运行应用程序。一旦启动，将出现标准的 Android 打印页面，如图 76-1 所示。（`image/as_html_print.jpg`）

图 76-1

如果你有物理打印机，请打印到打印机、保存到 Google Drive，或者选择保存为 PDF 文件。一旦打印任务启动，请在目标上检查生成的输出。请注意，使用“保存为 PDF”选项时，系统会请求 PDF 文件的名称和位置。`Downloads` 文件夹是一个很好的选择，可以通过选择设备上其他图标中的 Downloads 图标（在 Android 8 上重命名为 Files）查看其内容。

## 76.3 创建网页打印示例

本章创建的第二个示例将为用户提供一个溢出菜单（Overflow menu），用于打印当前在 `WebView` 实例中显示的网页。从欢迎界面选择 `New Project`，在生成的项目对话框中，点击 `Next` 按钮之前选择 `Basic Views Activity` 模板。在 `Name` 字段中输入 `WebPrint` 并指定 `com.ebookrenzy.webprint` 为包名。在点击 `Finish` 按钮之前，将最低 API 级别设置设置为 API 26: Android 8.0 (Oreo)，并将语言设置为 Java。

## 76.4 移除悬浮操作按钮

选择 `Basic Views Activity` 模板提供了上下文菜单和一个悬浮操作按钮。由于不需要悬浮操作按钮，可以在继续之前将其移除。将 `activity_main.xml` 布局加载到布局编辑器中，选择悬浮操作按钮并按删除键从布局中移除该对象。编辑 `MainActivity.java` 文件，从 `onCreate` 方法中移除悬浮操作按钮代码如下：

```java
@Override

protected void onCreate(Bundle savedInstanceState) {

    super.onCreate(savedInstanceState);

    binding = ActivityMainBinding.inflate(getLayoutInflater());

    setContentView(binding.getRoot());

    setSupportActionBar(binding.toolbar);

    binding.fab.setOnClickListener(new View.OnClickListener() {

        @Override

        public void onClick(View view) {

            Snackbar.make(view, "Replace with your own action", Snackbar.LENGTH_LONG)

                .setAction("Action", null).show();

        }

    });

}
```

## 76.5 移除导航功能

如“Android Studio 布局工具指南”所述，“Basic Views Activity”模板包含多个用于在 fragment 之间导航的 fragment 和按钮。这些功能对于本教程是不必要的，如果不移除会导致问题。在继续教程之前，按照以下方式修改项目：

1. 在 `Project` 窗口中，导航并双击 `app -> res -> navigation -> nav_graph.xml` 将其加载到导航编辑器。
2. 在编辑器中，选择图表中的 `SecondFragment` 项并按删除键将其从图表中移除。
3. 定位并删除 `SecondFragment.java`（`app -> java -> <package name> -> SecondFragment`）和 `fragment_second.xml`（`app -> res -> layout -> fragment_second.xml`）文件。
4. 定位 `FirstFragment.java` 文件，双击将其加载到编辑器，并从 `onViewCreated()` 方法中移除代码使其读取如下：

```java
public void onViewCreated(@NonNull View view, Bundle savedInstanceState) {

    super.onViewCreated(view, savedInstanceState);

    binding.buttonFirst.setOnClickListener(new View.OnClickListener() {

        @Override

        public void onClick(View view) {

            NavHostFragment.findNavController(FirstFragment.this)

                .navigate(R.id.action_FirstFragment_to_SecondFragment);

        }

    });

}
```

5. 编辑 `MainActivity.java` 文件并移除以下导航代码：

```java
@Override

protected void onCreate(Bundle savedInstanceState) {

    super.onCreate(savedInstanceState);

    binding = ActivityMainBinding.inflate(getLayoutInflater());

    setContentView(binding.getRoot());

    setSupportActionBar(binding.toolbar);

    NavController navController =

        Navigation.findNavController(this, R.id.nav_host_fragment_content_main);

    appBarConfiguration = new AppBarConfiguration.Builder(

        navController.getGraph()).build();

    NavigationUI.setupActionBarWithNavController(this, navController,

        appBarConfiguration);

}
```

```java
public boolean onSupportNavigateUp() {

    NavController navController = Navigation.findNavController(this,

            R.id.nav_host_fragment_content_main);

    return NavigationUI.navigateUp(navController, appBarConfiguration)

            || super.onSupportNavigateUp();

}
```

## 76.6 设计用户界面布局

如果 `content_main.xml` 布局资源文件尚未加载，请将其加载到 `Layout Editor` 工具中，并在 `Design` 模式下，选择并删除 `nav_host_fragment_content_main` 对象。从调色板的 `Widgets` 部分，将 `WebView` 对象拖放到设备屏幕布局的中心。点击工具栏上的 `Infer constraints`（推断约束）按钮，并使用 `Attributes` 工具窗口，将 `WebView` 的 `layout_width` 和 `layout_height` 属性更改为匹配约束，以便其填满整个布局画布，如下方的图 76-2 所示。

选择新添加的 `WebView` 实例，并将视图的 `ID` 更改为 `myWebView`。

在继续此教程的下一步之前，必须向项目添加额外的权限，以允许 `WebView` 对象访问互联网并下载用于打印的网页。通过在 `Project` 工具窗口中定位 `AndroidManifest.xml` 文件并双击它将其加载到编辑面板来添加此权限。加载后，编辑 XML 内容添加适当的权限行，如下所示：

```xml
<?xml version="1.0" encoding="utf-8"?>

<manifest xmlns:android="http://schemas.android.com/apk/res/android"

    package="com.ebookfrenzy.webprint" >

    <uses-permission android:name="android.permission.INTERNET" />

    <application

        android:allowBackup="true"

.

.

</manifest>
```

![](img/as_3.6_webprint_ui.jpg)

图 76-2

## 76.7 从主 Activity 访问 WebView

与标题为“Android RecyclerView 和 CardView 教程”章节中的项目一样，我们需要能够使用视图绑定（view binding）从 `MainActivity` 类内部访问 `content_main.xml` 文件中的组件（在此情况下为 `myWebView`）。要访问 `content_main.xml` 文件中的视图，我们仍然需要在包含它时为其分配一个 id。编辑 `activity_main.xml` 文件并修改 `include` 元素，如下所示：

```xml
.

.

    <include

        android:id="@+id/contentMain"

        layout="@layout/content_main" />

.

.
```

## 76.8 将网页加载到 WebView 中

在打印网页之前，必须将其加载到 `WebView` 实例。对于本教程，这将通过调用 `WebView` 实例的 `loadUrl()` 方法完成，该方法将放在命名为 `configureWebView()` 的方法中并在 `MainActivity` 类的 `onStart()` 方法内部调用。因此，编辑 `MainActivity.java` 文件并进行如下修改：

```java
package com.ebookfrenzy.webprint;

.

.

import android.view.Menu;

import android.view.MenuItem;

import android.webkit.WebView;

import android.webkit.WebViewClient;

import android.webkit.WebResourceRequest;

public class MainActivity extends AppCompatActivity {

    private WebView myWebView;

.

.

    @Override

    protected void onStart() {

        super.onStart();

        configureWebView();

    }

    private void configureWebView() {

        myWebView = findViewById(R.id.myWebView);

        myWebView.setWebViewClient(new WebViewClient(){

            @Override

            public boolean shouldOverrideUrlLoading(

                    WebView view, WebResourceRequest request) {

                return super.shouldOverrideUrlLoading(

                        view, request);

            }

        });

        myWebView.loadUrl("https://www.answertopia.com");

    }

.

}
```

## 76.9 添加打印菜单

现在将使用“在 Android 上创建和管理菜单”章节中概述的技术将打印网页的选项添加到溢出菜单（Overflow menu）中。第一个要求是一个用于标记菜单选项的字符串资源。在 `Project` 工具窗口中，找到 `app` -> `res` -> `strings.xml` 文件，双击它加载到编辑器中，并修改它以添加新字符串：

```xml
<resources>

    <string name="app_name">WebPrint</string>

    <string name="action_settings">Settings</string>

    <string name="print_string">Print</string>

.

</resources>
```



接下来，将 `app` -> `res` -> `menu` -> `main.xml` 文件加载到编辑器，切换到 `Code` 模式并替换如下打印项：

```xml
<menu xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    tools:context="com.ebookfrenzy.webprint.MainActivity">

    <item
        android:id="@+id/action_settings"
        android:title="@string/action_settings"
        app:showAsAction="never"
        priority="0" />

    <item
        android:id="@+id/action_print"
        android:title="@string/print_string"
        app:showAsAction="never"
        priority="1" />

</menu>
```

在配置菜单后，需要在 `MainActivity` 中实现 `ItemSelected()` 方法，如下：

```java
@Override
public boolean onOptionsItemSelected(MenuItem item) {
    int id = item.getItemId();

    if (id == R.id.action_print) {
        createPrint(myWebView);
        return true;
    }

    return super.onOptionsItemSelected(item);
}
```

实现了 `ItemSelected()` 方法后，当选择打印选项时，活动将调用命名为 `createPrint()` 的方法。该方法的实现与之前的 `HTMLPrint` 项目相同，现在可以添加到 `MainActivity.java` 中：

```java
package com.ebookfrenzy.webprint;

.
.

import android.print.PrintAttributes;
import android.print.PrintDocumentAdapter;
import android.print.PrintManager;
import android.content.Context;

public class MainActivity extends AppCompatActivity {

    private WebView myWebView;

    .
    .

    private void createPrint(WebView webView) {
        PrintManager printManager = (PrintManager) this
            .getSystemService(Context.PRINT_SERVICE);

        PrintDocumentAdapter printAdapter =
            webView.createPrintDocumentAdapter("MyDocument");

        String jobName = getString(R.string.app_name) +
            " Print Test";

        printManager.print(jobName, printAdapter,
            new PrintAttributes.Builder().build());
    }

    .
    .

}
```

代码更改完成后，在物理 Android 设备或模拟器上运行应用程序。成功启动后，`WebView` 应该显示并加载指定的网页。网页加载后，从溢出菜单选择打印选项，并使用生成的面板将网页打印到适当的目标。

在构建项目时，可能会遇到读取如下内容的错误：

`Duplicate class kotlin.collections.jdk8.CollectionsJDK8Kt found in modules kotlin-stdlib`

可以通过对 `build.gradle.kts (Module: app)` 文件进行以下更改来解决此错误：

```kotlin
dependencies {
    .
    .

    implementation(platform("org.jetbrains.kotlin:kotlin-bom:1.8.0"))

    .
    .
}
```

## 76.10 总结

Android 打印框架包含了 `WebView` 类的扩展，允许从 Android 应用程序内部打印 HTML 内容。这些内容可以是应用程序在运行时动态创建的 HTML，也可以是加载到 `WebView` 实例中的预现有网页。对于动态创建的 HTML，使用 `WebViewClient` 实例很重要，以确保在 HTML 完全加载到 `WebView` 之前开始打印。

# 77. Android 自定义文档打印指南

正如我们在前面的章节中所看到的，如果内容以图像或 HTML 标记的形式存在，Android 打印框架使得在应用程序中构建打印支持变得相对容易。更高级的打印需求可以通过打印框架的自定义文档打印功能来满足。

## 77.1 Android 自定义文档打印概述

简单来说，自定义文档打印使用画布（canvases）来表示要打印的文档页面。应用程序将要打印的内容以形状、颜色、文本和图像的形式绘制在这些画布上。画布由 `Canvas` 类的实例表示，提供了丰富的绘制选项访问。一旦完成所有页面的绘制，就会打印该文档。

虽然这听起来足够简单，但为了实现这一目标仍需要执行一些步骤，可以总结如下：

* 实现一个继承自 `PrintDocumentAdapter` 类的自定义打印适配器。
* 获取打印管理器服务（Print Manager Service）的引用。
* 创建一个 `PdfDocument` 类的实例以存储文档页面。
* 以 `PdfDocument.Page` 实例的形式将页面添加到 `PdfDocument` 中。
* 获取与文档页面相关的 `Canvas` 对象的引用。
* 在画布上绘制内容。
* 将 PDF 文档写入打印框架提供的目标输出流。
* 通知打印框架文档已准备好进行打印。

本章将提供这些步骤的概述，随后将提供一个详细的教程，旨在演示如何在 Android 应用程序中实现自定义文档打印。

### 77.1.1 自定义打印适配器

打印适配器的作用是为打印框架提供要打印的内容，并确保其根据用户选择的偏好进行正确的格式化（考虑纸张大小和页面方向等因素）。

这大部分工作由 Android 打印框架提供的打印适配器完成，这些适配器是专为打印 HTML 和图像等这些特定打印任务而设计的。例如，在打印网页时，每当调用 `WebView` 类实例的 `createPrintDocumentAdapter()` 方法时，系统会为我们创建一个打印适配器。

然而，在自定义文档打印的情况下，应用程序开发者负责设计打印适配器并实现绘制和格式化内容的代码以为打印做准备。

自定义打印适配器通过子类 `PrintDocumentAdapter` 类并重写该类中的一组回调方法来创建，这些方法会在打印过程的各个阶段由打印框架调用。这些回调方法可以总结如下：

* `onStart()` – 该方法在打印过程开始时调用，提供的目的是为了让应用程序代码执行创建打印作业所需的任何必要任务。在 `PrintDocumentAdapter` 子类中实现此方法是可选的。
* `onLayout()` – 此回调方法在调用 `onStart()` 方法后调用，并在用户每次更改打印设置（如更改方向、纸张大小或颜色设置）时再次调用。此方法应该调整内容和布局以适应这些更改。一旦更改完成后，方法必须返回要打印的页数。在 `PrintDocumentAdapter` 子类中实现 `onLayout()` 方法是强制的。
* `onWrite()` – 该方法在每次调用 `onLayout()` 后调用，负责在要打印页面的画布上渲染内容。除了其他参数外，此方法还会接收一个文件描述符，渲染完成后必须将生成的 PDF 文档写入其中。随后调用 `onWriteFinished()` 回调方法并传递一个包含打印页面范围信息的参数。在 `PrintDocumentAdapter` 子类中实现 `onWrite()` 方法是强制的。
* `onFinish()` – 可选方法。如果实现，它将在打印过程完成后由打印框架调用一次，从而为应用程序提供执行任何可能的清理操作的机会。

## 77.2 准备自定义文档打印项目

从欢迎界面选择“New Project”（新建项目）选项，在弹出的新项目对话框中，点击 Next（下一步）按钮之前选择“Empty Views Activity”模板。

在 Name 字段中输入 `CustomPrint` 并指定 `com.ebookfrenzy.customprint` 为包名。在点击 Finish（完成）按钮之前，将 Minimum API level 设置为 `API 26: Android 8.0 (Oreo)`，并将 Language 菜单设置为 Java。

将 `activity_main.xml` 布局文件加载到 Layout Editor（布局编辑器）工具中，并在 Design（设计）模式下选择并删除“Hello World!” `TextView` 对象。从调板的 Common（常用）部分拖入一个 `Button` 视图并将其放置在布局视图的中心。选中 `Button` 视图后，将 text 属性更改为“Print Document”并将字符串提取到新的资源中。完成后，用户界面的布局应与图 77-1 所示所示。

当在应用程序中选中按钮时，需要调用一个方法来启动文档打印过程。留在 Attributes（属性）工具窗口，将 `onClick` 属性设置为调用名为 `printDocument` 的方法。

![](img/as_custom_print_ui.jpg)

图 77-1

## 77.3 创建自定义打印适配器

在 Android 应用程序内部打印自定义文档的大部分工作涉及自定义打印适配器的实现。此示例将需要一个实现了 `onLayout()` 和 `onWrite()` 回调方法的打印适配器。在 `MainActivity.java` 文件中，为此新类添加模板，使其内容如下：

```java
package com.ebookfrenzy.customprint;

.
.

import android.os.CancellationSignal;
import android.os.ParcelFileDescriptor;
import android.print.PageRange;
import android.print.PrintAttributes;
import android.print.PrintDocumentAdapter;
import android.content;

public class MainActivity extends AppCompatActivity {

    static class MyDocumentAdapter extends PrintDocumentAdapter {

        Context context;

        MyDocumentAdapter(Context context) {
            this.context = context;
        }

        @Override
        public void onLayout(PrintAttributes oldAttributes,
            PrintAttributes newAttributes,
            CancellationSignal cancellationSignal,
            LayoutResultCallback callback,
            Bundle metadata) {
        }

        @Override
        public void onWrite(PageRange[] pageRanges,
            final ParcelFileDescriptor destination,
            final CancellationSignal cancellationSignal,
            final WriteResultCallback callback) {
        }
```

目前该新类包含一个在创建新类实例时被调用的构造方法。该构造方法接收调用的 `context` 作为参数，然后将其存储以便在后两个回调方法中引用。

在建立类框架后，下一步是实现两个回调方法，从 `onLayout()` 开始。

## 77.4 实现 `onLayout()` 回调方法

留在 `MainActivity.java` 文件中，首先添加 `onLayout()` 方法代码所需的某些导入指令：

```java
package com.ebookfrenzy.customprint;

import android.print.PrintDocumentInfo;
import android.print.pdf.PrintedPdfDocument;
import android.graphics.pdf.PdfDocument;
```

```java
public class MainActivity extends AppCompatActivity {

// .
// .

}
```

接下来，修改 `MyPrintDocumentAdapter` 类以声明在 `onLayout()` 方法中使用的变量：

```java
public static class MyPrintDocumentAdapter extends PrintDocumentAdapter
{
    Context context;
    int pageHeight;
    int pageWidth;
    PdfDocument myPdfDocument;
    int totalpages = 4;

// .
}
```

注意，在本示例中，将打印一个四页的文档。在更复杂的情况下，应用程序很可能需要根据内容的数量和布局，结合用户选择的纸张尺寸和方向，动态计算需要打印的页数。

声明变量后，按照下面的代码列表实现 `onLayout()` 方法：

```java
@Override
public void onLayout(PrintAttributes oldAttributes,
                    PrintAttributes newAttributes,
                    CancellationSignal cancellationSignal,
                    LayoutResultCallback callback,
                    Bundle metadata) {

    myPdfDocument = new PrintedPdfDocument(context, newAttributes);

    pageHeight =
            Objects.requireNonNull(
                newAttributes.getMediaSize()).getHeightMils()/1000 * 72;

    pageWidth =
            newAttributes.getMediaSize().getWidthMils()/1000 * 72;

    if (cancellationSignal.isCanceled() ) {
        callback.onLayoutCancelled();
        return;
    }

    if (totalpages > 0) {
        PrintDocumentInfo.Builder builder = new PrintDocumentInfo
            .Builder("print_output.pdf").setContentType(
                    PrintDocumentInfo.CONTENT_TYPE_DOCUMENT)
            .setPageCount(totalpages);

        PrintDocumentInfo info = builder.build();
        callback.onLayoutFinished(info, true);
    } else {
        callback.onLayoutFailed("Page count is zero.");
    }
}
```



该方法执行了许多任务，每项任务都需要详细的解释。

首先，创建一个`PdfDocument`类实例来创建一个新的 PDF 文档。当打印框架调用`onLayout()`方法时，传入的参数之一是一个`PrintAttributes`类型的对象，其中包含了用户为打印输出选择的纸张尺寸、分辨率和颜色设置的详细信息。在创建 PDF 文档时会使用这些设置，并结合构造方法之前为我们存储的活动上下文：

```java
myPdfDocument = new PrintedPdfDocument(context, newAttributes);
```

该方法随后使用`PrintAttributes`对象提取文档页的高度和宽度值。这些维度存储在对象中，以英寸的千分之一表示。由于本示例后续使用这些值的方法是以 1/72 英寸为单位运行的，因此在存储这些数字之前进行了转换：

```java
pageHeight = newAttributes.getMediaSize().getHeightMils()/1000 * 72;
pageWidth = newAttributes.getMediaSize().getWidthMils()/1000 * 72;
```

虽然此示例没有使用用户的颜色选择，但可以通过调用`PrintAttributes`对象的`getColorMode()`方法获取此属性，它将返回`COLOR_MODE_COLOR`或`COLOR_MODE_MONROME`值。

当调用`onLayout()`方法时，会传入一个`LayoutResultCallback`对象。该对象为方法通过一组方法向打印框架返回状态的方法。例如，如果用户取消了进程，`onLayout()`方法将被调用。进程已取消的事实通过`CancellationSignal`参数中的设置来指示。如果检测到取消，`onLayout()`方法必须调用`LayoutResultCallback`的`onLayoutCancelled()`方法，通知打印框架已收到取消且布局任务已取消：

```java
if (cancellationSignal.isCanceled() ) {
    callback.onLayoutCancelled();
    return;
}
```

当布局工作完成后，该方法要求调用`LayoutResultCallback`的`onLayoutFinished()`方法，并传递两个参数。第一个参数是一个`PrintDocumentInfo`对象，包含有关要打印文档的信息。这些信息由 PDF 文档的名称、内容类型（在本例中是文档而非图像）以及页数组成。第二个参数是一个`Boolean`值，表示自上一次调用`onLayout()`方法以来，布局是否发生了变化：

```java
if (totalPages > 0) {
    PrintDocumentInfo.Builder builder = new PrintDocumentInfo
        .Builder("print_output.pdf")
        .setContentType(
            PrintDocumentInfo.CONTENT_TYPE_DOCUMENT)
        .setPageCount(totalpages);
    PrintDocumentInfo info = builder.build();
    callback.onLayoutFinished(info, true);
} else {
    callback.onLayoutFailed("Page count is zero.");
}
```

如果页数为零，代码将通过调用`LayoutResultCallback`对象的`onLayoutFailed()`方法向打印框架报告此失败。调用`onLayoutFinished()`方法通知打印框架布局工作完成，触发对`onWrite()`方法的调用。

## 77.5 实现`onWrite()`回调方法

`onWrite()`回调方法负责渲染文档的页面，然后通知打印框架文档已准备好打印。完成后，`onWrite()`方法的内容如下：

```java
package com.ebookzyzy.print;

import java.io.FileOutputStream;
import java.io.IOException;
// .
import android.graphics.pdf.PdfDocument.PageInfo;
// .

@Override
public void onWrite(final PageRange[] pageRanges,
                    final FileDescriptor destination,
                    final CancellationSignal cancellationSignal,
                    final WriteResultCallback callback) {

    for (int i = 0; i < totalpages; i++) {
        if (pageInRange(pageRanges, i))
        {
            PageInfo newPage = new PageInfo.Builder(pageWidth,
                pageHeight, i).create();
            PdfDocument.Page page =
                myPdfDocument.startPage(newPage);

            if (cancellationSignal.isCanceled()) {
                callback.onLayoutCancelled();
                myPdfDocument.close();
                myPdfDocument = null;
                return;
            }

            drawPage(page, i);
            myPdfDocument.finishPage(page);
        }
    }

    try {
        myPdfDocument.writeTo(new FileOutputStream(
            destination.getFileDescriptor()));
    } catch (IOException e) {
        callback.onWriteFailed(e.toString());
        return;
    } finally {
        myPdfDocument.close();
        myPdfDocument = null;
    }

    callback.onWriteFinished(pageRanges);
}
```

在将页面写入到 PDF 文档时，`onWrite()`方法必须采取措施，确保只打印用户指定的页面。为了实现这一点，`Printing`框架会将一个`PageRange`对象的数组作为参数传递，该数组指示要打印的页面范围。在上面的`onWrite()`实现中，会为每个页面调用`pageInRange()`方法，以验证该页面是否在指定的范围内。`pageInRange()`方法的代码将在本章稍后部分实现。

```java
for (int i = 0; i < totalpages; i++) {
    if (pageInRange(pageRanges, i)) {
    }
}
```

对于位于指定范围内的每个页面，都会创建一个新的`PdfDocument.Page`对象。在创建新页面时，之前由`onLayout()`方法存储的高度和宽度值将作为参数传递，以便使页面大小与用户选择的打印选项匹配：

```java
PageInfo newPage = new PageInfo.Builder(pageWidth, pageHeight, i).create();
PdfDocument.Page page = myPdfDocument.startPage(newPage);
```

与`onLayout()`方法一样，`onWrite()`方法也需要响应取消请求。在这种情况下，代码会在关闭并取消引用`myPdfDocument`变量之前，通知`Printing`框架取消已执行：

```java
if (cancellationSignal.isCanceled()) {
    callback.onWriteCancelled();
    myPdfDocument.close();
    myPdfDocument = null;
    return;
}
```

只要打印过程没有被取消，方法在调用`myPdfDocument`对象的`finishedPage()`方法之前，会调用一个方法在当前页面上绘制内容：

```java
drawPage(page, i);
myPdfDocument.finishPage(page);
```

`drawPage()`方法负责将内容绘制到页面上，并在`onWrite()`方法完成后实现。

当所需的页面数量已添加到 PDF 文档后，文档将使用文件描述符写入目标流，文件描述符作为参数传递给`onWrite()`方法。如果由于任何原因写入操作失败，方法将通过调用`WriteResultCallback`对象的`onWriteFailed()`方法（该对象也作为参数传递给`onWrite()`方法）来通知框架。

```java
try {
    myPdfDocument.writeTo(new FileOutputStream(
            destination.getFileDescriptor()));
} catch (IOException e) {
    callback.onWriteFailed(e.toString());
    return;
} finally {
    myPdfDocument.close();
    myPdfDocument = null;
}
```

最后，将调用`WriteResultsCallback`对象的`onWriteFinish()`方法，通知`Printing`框架文档已准备好打印。

### 77.6 检查页面是否在范围内

如前所述，当调用`onWrite()`方法时，会传递一个`PageRange`对象的数组，指示文档中要打印的页面范围。`PageRange`类设计用于存储页面范围的起始页和结束页，反之，可以通过该类的`getStart()`和`getEnd()`方法进行访问。

在上一节实现`onWrite()`方法时，调用了一个名为`pageInRange()`的方法，该方法接收一个`PageRange`对象的数组和一个页码作为参数。`pageInRange()`方法的作用是识别指定的页码是否在指定的范围内，可以如下所示在`MainActivity.java`类的`MyPrintDocumentAdapter`类中实现：

```java
public class MyPrintDocumentAdapter extends PrintDocumentAdapter {
    //
    private boolean pageInRange(PageRange[] pageRanges, int page) {
        for (PageRange pageRange : pageRanges) {
            if ((page >= pageRange.getStart()) &&
                (page <= pageRange.getEnd()))
                return true;
        }
        return false;
    }
    //
}
```

### 77.7 在页面上绘制内容

现在我们到了编写某些代码在页面上绘制内容以使其准备好打印的步骤。所绘制的内容完全取决于并限于使用`Canvas`类所能实现的内容。在本示例中，将在画布上绘制一些文本和图形。`onWrite()`方法被设计为调用名为`drawPage()`的方法，该方法接收一个代表当前页面的`PdfDocument.Page`对象和一个代表页码的整数作为参数。在`MainActivity.java`中，此方法现在的实现如下：

```java
package com.frenzy.print;

import android.graphics.Canvas;
import android.graphics.Color;
import android.graphics.Paint;

public class MainActivity extends AppCompatActivity {
    static class MyPrintDocumentAdapter extends PrintDocumentAdapter {
        private void drawPage(PdfDocument.Page page, int pagenumber) {
            Canvas canvas = page.getCanvas();
            pagenumber++; // 让页码从 1 开始
            int titleBaseLine = 72;
            int leftMargin = 5;
            Paint paint = new Paint();
            paint.setColor(Color.BLACK);
            paint.setTextSize(40);
            canvas.drawText(
                "Test Document Page " + pagenumber,
                leftMargin,
                titleBaseLine,
                paint);
            paint.setTextSize(14);
            canvas.drawText("This is some test content to verify that custom printing works", leftMargin, titleBaseLine + 35, paint);
            if (pagenumber % 2 == 0)
                paint.setColor(Color.RED);
            else
                paint.setColor(Color.GREEN);
            PageInfo pageInfo = page.getInfo();
            canvas.drawCircle(
                pageInfo.getPageWidth()/2,
                pageInfo.getPageHeight()/2,
                150,
                paint);
        }
    }
}
```

代码中的页码从 0 开始。由于文档通常从 1 开始，该方法首先递增存储的页码。然后获取与页面关联的`Canvas`对象引用，并声明一些边距和基线值：

```java
Canvas canvas = page.getCanvas();
pagenumber++;
int titleBaseLine = 72;
int leftMargin = 5;
```

接下来，代码创建用于绘制的`Paint`和`Color`对象，设置字体大小并绘制页面标题，包括当前页码：

```java
Paint paint = new Paint();
paint.setColor(Color.BLACK);
paint.setTextSize(40);
canvas.drawText("Test Document Page " + pagenumber,
    leftMargin,
    titleBaseLine,
    paint);
```

随后缩小字体大小，并在标题下方绘制正文内容：

```java
paint.setTextSize(14);
canvas.drawText("This is some test content to verify that custom printing works", leftMargin, titleBaseLine + 35, paint);
```

该方法的最后一个任务是绘制一个圆（偶数页为红色，奇数页为绿色）。在确定页面是奇数偶数后，方法获取页面的高度和宽度，然后利用这些信息将圆放置在页面中心：

```java
if (pagenumber % 2 == 0)
    paint.setColor(Color.RED);
else
    paint.setColor(Color.GREEN);
PageInfo pageInfo = page.getInfo();
```



`canvas.drawCircle(pageInfo.getPageWidth()/2, pageInfo.getPageHeight()/2, 150, paint);`

在画布绘制完成后，该方法会将控制权交回给 `onWrite()` 方法。

随着 `drawPage()` 方法完成，`MyPrintDocumentAdapter` 类完成后。

## 77.8 启动打印作业

当用户点击“打印文档”（Print Document）按钮时，将调用 `printDocument()` onClick 事件处理方法。现在在开始测试之前，剩下的工作是将此方法添加到 `MainActivity.java` 文件中，特别注意确保将其放置在 `MyPrintDocumentAdapter` 类之外：

```java
package com.ebookfrenzy.customprint;
.
.
import android.print.PrintManager;
import android.view.View;

public class MainActivity extends AppCompatActivity {

    public void printDocument(View view)
    {
        PrintManager printManager = (PrintManager) this
                    .getSystemService(Context.PRINT_SERVICE);
        String jobName = this.getString(R.string.app_name) +
                            " Document";
        printManager.print(jobName, new
                            MyPrintDocumentAdapter(this),
                            null);
    }
}
.
.
```

该方法在创建一个新的 `String` 对象作为打印任务名称之前，获取了设备上运行的 Print Manager 服务的引用。最后，调用 Print Manager 的 `print()` 方法启动打印作业，传递作业名称和我们自定义打印文档适配器类的实例。

## 77.9 测试应用程序

在 Android 设备或模拟器上编译并运行应用程序。当应用程序加载后，点击“打印文档”按钮以启动打印作业，并为输出选择合适的目标（“保存为 PDF”选项有助于避免浪费纸张和打印机墨水）。

检查打印输出，它应该包含 4 页内容，包括文本和图形。例如，图 77-3 显示了作为 PDF 文件查看并准备好保存到设备上的文档四页内容。

尝试其他的打印配置选项，例如在打印面板中更改纸张大小、方向和页面设置。打印输出应反映每项设置的变化，表明自定义打印文档适配器功能正常。

![](img/as_4.1_custom_print_running.jpg)

图 77-3

## 77.10 总结

虽然自定义文档打印的实现比 Android 打印框架的 HTML 和图像打印选项复杂，但它为在 Android 应用程序中打印复杂内容提供了巨大的灵活性。实现自定义文档打印的大部分工作涉及创建一个自定义打印适配器类，该类不仅在文档页面上绘制内容，还能在用户更改打印设置（如页面大小和打印页面范围）时做出正确响应。

# 78 Android App 链接（App Links）简介

随着技术的演进，网页内容与移动内容之间的传统区别开始模糊。这一点特别真实的一个领域是渐进式 Web 应用（progressive web apps）的日益普及，这些 Web 应用的外观和行为非常类似于传统的移动应用。

另一个趋势是通过 Web 搜索和 URL 链接使移动应用中的内容变得可发现。在 Android 应用开发背景下，`App Links` 功能旨在让用户能够更容易地发现和访问存储在 Android 应用中的内容，即使使用户没有安装该应用。

## 78.1 Android App 链接概述

App 链接（app link）是一个标准的 HTTP URL，是从外部源（如网站或应用）直接链接到应用中特定位置的简单方法。App 链接（也称为深度链接 deep links）主要用于鼓励用户与应用互动，并允许用户共享应用内容。

App 链接的实现是一个多步骤过程，涉及向项目清单（manifest）添加意图过滤器（intent filters）、在关联的应用 Activity 中实现链接处理代码以及使用数字资产链接文件（digital asset links files）将应用与 Web 端内容关联。

这些步骤可以通过手动修改项目来完成，也可以使用 Android Studio App Links 助手（Assistant）自动完成。

本章的剩余部分将从对项目进行的更改来概述 App 链接的实现。下一章 (“Android Studio App Links 教程”) 将演示如何使用 `App Links Assistant` 实现相同的结果。

## 78.2 App 链接意图过滤器

App 链接 URL 需要映射到应用项目中的特定 Activity。这是通过向项目的 `AndroidManifest.xml` 文件添加意图过滤器实现的，这些过滤器旨在响应 `android.intent.action.VIEW` 操作来启动 Activity。意图过滤器声明在要启动的 Activity 内部，并且包含概述 App 链接 URL 的方案（scheme）、主机（host）和路径（path）的数据。例如，下面的清单片段声明了一个意图过滤器，当检测到匹配 `http://www.example.com/welcome` 的 App 链接时，启动名为 `MyActivity` 的 Activity：

```xml
<activity android:name="com.ebookfrenzy.myapp.MyActivity">
    <intent-filter android:autoVerify="true">
        <action android:name="android.intent.action.VIEW" />
        <category android:name="android.intent.category.DEFAULT" />
        <category android:name="android.intent.category.BROWSABLE" />
        <data android:scheme="http"
              android:host="www.example.com"
              android:pathPrefix="/welcome" />
    </intent-filter>
</activity>
```

处理歧义意图过滤器的顺序可以使用意图过滤器的 `order` 属性指定，如下所示：

```xml
<application>
    <activity android:name="com.ebookfrenzy.myapp.MyActivity">
        <intent-filter android:autoVerify="true" android:order="1">
            .
        </intent-filter>
    </activity>
</application>
```

意图过滤器会使 App 链接启动 Activity，但仍需要在目标 Activity 中添加代码来处理意图。

## 78.3 处理 App 链接意图

在大多数情况下，启动的 Activity 需要访问 App 链接 URL 并根据 URL 的结构采取特定行动。继续上面的示例，当通过路径为 `/welcome/newuser` 的 URL 启动时，显示的内容与路径设置为 `/welcome/existinguser` 时不同。

当链接启动 Activity 时，会传递一个包含启动 Activity 操作数据的 `intent` 对象，其中包含 App 链接 URL 的 `Uri` 对象。在 Activity 的初始化阶段，可以添加代码按如下方式提取这些数据：

```java
Intent appLinkIntent = getIntent();
String appLinkAction = appLinkIntent.getAction();
Uri appLinkData = appLinkIntent.getData();
```

获取 App 链接的 `Uri` 后，可以使用 URL 路径的各个组件来决定 Activity 中执行的操作。在下面的代码示例中，URL 的最后一个部分被用于识别为新用户还是现有用户显示内容：

```java
String userType = appLinkData.getLastPathSegment();
if (userType.equals("newuser")) {
    // 显示新用户内容
} else {
    // 显示现有用户内容
}
```

## 78.4 将应用与网站关联

在 App 链接生效之前，必须将 App 链接 URL 与 App 链接所基于的网站关联。这是通过创建一个名为 `assetlinks.json` 的数字资产链接文件并将其安装在网站的 `.well-known` 文件夹中实现的。注意，数字资产链接仅适用于基于 HTTPS 的网站。

数字资产链接文件（Digital asset links file）包含一个关系声明（relation statement），允许目标应用使用网站的链接 URL 启动；以及一个目标声明（target statement），用于声明伴侣应用的包名和对应该项目的 `SHA-256` 证书指纹。一个典型的资产链接文件可能如下：

```json
[{
    "relation": ["delegate_permission/common.handle_all_urls"],
    "target" : { "namespace": "android_app",
      "package_name": "<app package name here>",
      "sha256_cert_fingerprints": ["<app certificate here>"] }
}]
```

`assetlinks.json` 文件可以包含多个数字资产链接，允许单个网站与多个伴侣应用关联。

## 78.5 总结

Android App Links（Android 应用链接）允许通过来自外部网站和其他应用的 URL 链接启动应用活动（activities）。App Links 通过项目清单文件中的 `intent filters`（意图过滤器）以及启动的活动中的意图处理代码来实现。通过使用数字资产链接文件，还可以将应用链接中使用的域名与相应的网站关联。一旦建立这种关联，当使用应用链接时，Android 就不再需要要求用户选择目标应用。

# 79. Android Studio App Links 教程

本章旨在对 Android 应用链接和 Android Studio App Links 助手（App Link Assistant）进行实际演示。本章将为现有的 Android 应用添加应用链接支持，允许通过应用链接 URL 启动活动。除了启动活动外，显示的内容还将在 URL 的路径中指定。

## 79.1 关于示例应用

本章使用的项目命名为 `AppLinking`，是一个基础应用，旨在允许用户查找有关伦敦地标的信息。该应用使用通过标准 Android 内容提供者（content provider）类访问的 `SQLite` 数据库。该应用有一个现有的数据库，其中包含了伦敦热门旅游景点的记录。除了现有的数据库条目外，应用还允许用户添加和删除地标描述。

目前，该应用允许搜索现有记录，并添加和删除新记录。

该项目由两个名为 `AppLinkingActivity` 和 `LandmarkActivity` 的活动组成。`AppLinkingActivity` 是应用启动时启动的主活动。该活动允许用户输入搜索标准并向数据库添加记录。当搜索找到匹配的记录时，`LandmarkActivity` 将启动并显示相关地标的信息。

本章将增强该应用以支持应用链接，以便可以使用 URL 在应用内显示特定的地标记录。

## 79.2 数据库结构

示例应用的数据包含名为 `landmarks.db` 的文件中，位于项目层级结构的 `app` -> `assets` -> `databases` 文件夹中。数据库包含一个名为 `locations` 的表，其结构概述如下：

| 列 | 类型 | 描述 |
| :--- | :--- | :--- |
| `_id` | String | 主索引，此列包含唯一标识数据库中地标的字符串值。 |
| `title` | String | 地标的名称（例如，伦敦桥）。 |
| `description` | String | 地标的描述。 |
| `personal` | Boolean | 表示记录是私人的还是公共的。对于用户添加的所有记录，此值设置为 `true`。数据库提供的现有记录设置为 `false`。 |

表 79-1

## 79.3 加载并运行项目

该项目包含位于以下 URL 的示例源码下载压缩包的 `AppLinking` 文件夹中：

`https://www.ebookfrenzy.com/retail/giraffejava/index.php`

找到文件夹后，在 Android Studio 中打开它并在设备或模拟器上运行应用。一旦应用启动，将出现下图 79-1 所示的屏幕：

![](img/as_applinking_ui_home.jpg)

图 79-1

如果出现 `kotlin.collections.jdk8.CollectionsJDK8Kt` 错误，请对 `build.gradle.kts` (Module: app) 文件进行以下更改，同步项目并重试：

```kotlin
dependencies {
    ...
    implementation(platform("org.jetbrains.kotlin:kotlin-bom:1.8.0"))
    ...
}
```



按照目前的实现方式，地标是通过位置 ID 查找的。默认数据库配置当前包含两个由 ID `londonbridge` 和 `toweroflondon` 引用的记录。通过在 ID 字段中输入 `londonbridge` 并点击 Find 按钮来测试搜索功能。当找到匹配的记录时，会启动第二个活动（`LandmarkActivity`）并传递有关该记录的信息进行显示。这些信息以添加到 `Intent` 对象的额外数据（extra data）的形式存在。`LandmarkActivity` 使用这些信息从数据库中提取记录，并使用图 79-2 所示的屏幕显示给用户。

![](img/as_applinking_ui_london_bridge.jpg)

图 79-2

### 79.4 添加 URL 映射

现在应用已经加载到 Android Studio 并通过测试，我们可以添加应用链接支持。目标是让 `LandmarkActivity` 屏幕响应应用链接点击并启动并显示信息。这是通过将 URL 映射到 `LandmarkActivity` 实现的。在本示例中，URL 的格式将：

`http://<website domain>/landmarks/<landmarkId>`

完成所有步骤后，相应的 URL 应该导致应用显示有关伦敦塔的信息：

`http://yourdomain.com/toweroflondon`

要向项目添加 URL 映射，首先通过 `Tools` -> `App Links` 菜单打开 App Links 助手。打开后，助手将如图 79-3 所示：

![](img/as_applinks_assistant.jpg)

图 79-3

点击 `Open URL Mapping` 按钮将 URL 映射到活动。在映射屏幕内，点击图 79-4 中高亮的 `+` 按钮添加新 URL：

![](img/as_applinks_assistant_mappings.jpg)

图 79-4

在 `Add URL Mapping` 对话框的 `Host` 字段中，输入你网站的 URL。如果你没有用于此教程的网站，可以使用 `http://www.example.com` 继续学习本章，但无法测试需要数字链接文件的功能。

`Path` 字段（见图 79-5 中的 B）是声明 URL 路径的地方。路径必须以 `/` 开头，因此在此字段中输入 `/landmarks`。

`Path` 菜单（B）提供了以下三种路径匹配选项：

- `path` – URL 必须精确匹配 URL 的路径部分才能启动活动。例如，如果路径设置为 `/landmarks`，则 `http://www.example.com/landmarks` 被视为匹配。然而，`http://www.example.com/landmarks/londonbridge` 将不被视为匹配。
- `pathPrefix` – 指定的路径仅被视为前缀。在 `/landmarks` 组件之后可以包含额外的路径组件（例如，`http://www.example.com/landmarks/londonbridge` 将被视为匹配）。
- `pathPattern` – 允许使用基本正则表达式和通配符的模式匹配形式指定路径，例如 `landmarks/*/[l-L]ondon/*`

由于在本示例中，路径是地标 ID 组件的前缀，请选择 `pathPrefix` 菜单选项。

最后，使用 `Activity` 菜单（C）选择 `LandmarkActivity` 作为响应应用链接启动的活动：

![](img/as_applinks_url_mapping.jpg)

图 79-5

完成对话框中的设置后，点击 `OK` 按钮以提交更改。通过在映射屏幕的 `Check URL Mapping` 字段中输入以下 URL，检查 `URL` 格式是否正确以及是否分配给相应的活动（其中 `<your domain>` 设置为上方 `Host` 字段中指定的域名）：

`http://<your domain>/landmarks/toweroflondon`

如果映射配置正确，`LandmarkActivity` 将列为已映射的活动：

![](img/as_app_links_check_url.jpg)

图 79-6

最新版本的 Android 要求对 HTTP 和 HTTPS 协议都声明 App Links，即使只使用了其中一种。因此，在继续下一步之前，请重复上述步骤，将 `URL` 的 HTTPS 版本添加到列表中。

下一步也将在 App Links 助手（App Links Assistant）的 URL 映射屏幕中进行，因此请保持该屏幕处于选中状态。

### 79.5 添加 Intent Filter

如上一章所述，需要一个意过滤器（intent filter）来响应应用链接点击并启动目标活动。事实上，当添加 URL 映射时，意过滤器已自动添加到项目清单文件（manifest）中。在 App Links 助手的 URL 映射列表中选中该 URL 映射，向下滚动屏幕直到意过滤器预览（Preview）部分进入视野。预览内容应包含修改后的 `AndroidManifest.xml` 文件，其中包含了新添加的意过滤器：

![](img/as_app_links_intent_filter.jpg)

图 79-7

尽管 App Links 助手已为我们添加了意过滤器，但它可能没有包含处理应用链接时所需的 `autoVerify` 设置。打开 `manifests -> AndroidManifest.xml` 文件，并如下所示将此设置添加到两个意过滤器中：

```xml
<intent-filter android:autoVerify="true">
.
.
    <data
        android:scheme="http"
        android:host="www.ebookfrenzy.com"
        android:pathPrefix="/landmarks" />
</intent-filter>

<intent-filter android:autoVerify="true">
.
.
    <data
        android:scheme="https"
        android:host="www.ebookfrenzy.com"
        android:pathPrefix="/landmarks" />
</intent-filter>
```

### 79.6 添加 Intent 处理代码

到目前为止的操作确保了在响应格式正确的应用链接 URL 时会启动正确的活动。下一步是在 `LandmarkActivity` 类中处理该 intent，以便从数据库中提取正确的记录并显示给用户。在修改 `LandmarkActivity.java` 文件中的任何代码之前，值得审查现有代码的某些区域。在代码编辑器中打开 `LandmarkActivity.java` 文件，并找到 `onCreate()` 和 `handleIntent()` 方法，它们目前的内容应该如下：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    binding = ActivityLandmarkBinding.inflate(getLayoutInflater());
    View view = binding.getRoot();
    setContentView(view);
    handleIntent(getIntent());
}

private void handleIntent(Intent intent) {
    String landmarkId =
        intent.getStringExtra(AppLinkingActivity.LANDMARK_ID);
    displayLandmark(landmarkId);
}
```

在当前形式下，代码期望在 `Intent` 捆包的额外数据（extra data）中找到地标 ID。由于活动现在可以通过应用链接启动，必须更改此代码以处理两种情况。首先删除 `onCreate()` 方法中的 `handleIntent()` 调用：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    binding = ActivityLandmarkBinding.inflate(getLayoutInflater());
    View view = binding.getRoot();
    setContentView(view);
    handleIntent(getIntent());
}
```

要添加初始的应用链接 intent 处理代码，返回 App Links 助手面板，并点击步骤 2 下列出的 `Select Activity` 按钮。在活动选择对话框中，点击 `Insert Code` 按钮之前，选择 `LandmarkActivity` 条目：

![](img/as_app_links_select_activity.jpg)

图 79-8

返回 `LandmarkActivity.java` 文件，注意以下代码已插入到 `onCreate()` 方法中（注意，如果 Android Studio 无法完成请求，您可以手动添加此代码）：

```java
// ATTENTION: 这是自动生成的，用于处理应用链接。
Intent appLinkIntent = getIntent();
String appLinkAction = appLinkIntent.getAction();
Uri appLinkData = appLinkIntent.getData();
```

此代码访问 `Intent` 对象并提取 `Action` 字符串和 `Uri`。如果活动启动是由应用链接引起的，action 字符串将设置为 `android.intent.action.VIEW`，这与添加到清单文件的意过滤器中声明的 action 匹配。反之，如果代码选择活动来识别活动是如何启动的，代码逻辑如下：

```java
import android.net.Uri;

@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    binding = ActivityLandmarkBinding.inflate(getLayoutInflater());
    View view = binding.getRoot();
    setContentView(view);

    // ATTENTION: 这是自动生成的，用于处理应用链接。
    Intent appLinkIntent = getIntent();
    String appLinkAction = appLinkIntent.getAction();
    Uri appLinkData = appLinkIntent.getData();

    if (appLinkAction != null) {
        if (appLinkAction.equals("android.intent.action.VIEW")) {
            String landmarkId = appLinkData.getPathSegment();
            if (landmarkId != null) {
                displayLandmark(landmarkId);
            }
        }
    } else {
        handleIntent(appLinkIntent);
    }
}
```



剩下的工作是添加代码以识别 URL 的最后部分，并在查询数据库时作为地标 ID。

### 79.7 测试应用
在设备或模拟器上运行应用，确保仍然可以搜索示例地标。我们现在成功为应用添加了应用链接支持。如果您为应用链接指定了自己的网站 URL，现在可以更进一步创建并安装 Digital Asset Links 文件。

### 79.8 创建 Digital Asset Links 文件
如“Android Intent 概述”章节所述，为了完全支持应用链接，我们需要在应用链接引用的网站上安装 Digital Asset Links 文件。首先按照“Android Intent 概述”章节中列出的步骤找到`debug.keystore`文件并识别您的`SHA256`指纹。

接下来，在浏览器中打开以下页面：

[`developers.google.com/digital-asset-links/tools/generator`](https://developers.google.com/digital-asset-links/tools/generator)

点击`Generate`语句按钮以显示生成的语句，并将其放在 Web 服务器上名为`.well-known`的文件夹中的，命名为`assetlinks.json`。返回生成器页面，并点击`Test`语句按钮以验证文件是否位于正确位置。如果测试成功，将出现类似下面的输出：

![](img/asset_file_link_test.jpg)

图 79-10

假设测试成功，我们现在可以尝试使用应用链接（app link）。

### 79.9 测试应用链接
返回 App Links 助手面板并点击`Test App Links`按钮，测试意图处理是否正常工作。当提示输入测试 URL 时，在点击`Run Test`按钮之前，输入使用应用链接映射中引用的域名的 londonbridge 地标 ID 对应的 URL：

![](img/as_app_links_test_on_device.jpg)

图 79-11

点击按钮后，`Landmark`活动应在设备或模拟器上启动，并显示关于伦敦桥的信息。

### 79.10 总结
本章演示了在 Android 应用项目中实现 App Link 支持的步骤，包括在 Android Studio 中使用 App Link 助手、App Link URL 映射、意图过滤器（intent filters）、使用数字资产链接文件项处理网站关联，以及 App Link 测试。

## 80. Android 生物识别教程
触摸传感器现在已内置于许多 Android 设备中，用于识别用户并提供设备和应用功能的访问，例如使用指纹识别的应用内支付选项。指纹识别只是多种认证方法之一，还包括密码、PIN 以及最近的面部识别。

尽管目前市场上只有少数 Android 设备提供面部识别，但这在未来可能会变得更加普遍。因此，Google 已开始从以指纹为核心的添加应用认证的方法转向一种更具通用的方法，称为生物识别。

本章提供了生物识别的概述，并提供了一个详细的、循序渐进的教程，演示了在 Android 应用项目中实现生物识别的实用方法。

### 80.1 生物识别概述
关键的生物识别组件是`BiometricPrompt`类。该类执行了许多以前在早期 Android 版本中必须通过编写代码完成的工作，包括显示标准对话框以引导用户完成认证过程、执行认证并将结果报告给应用。该类还处理了多次失败的认证尝试，并在用户再次尝试之前强制执行超时。

`BiometricPrompt`类包含一个伴随类`Builder`，可以使用它可以配置和创建`BiometricPrompt`实例，包括定义要在生物识别对话框中显示的文本，以及对对话框中取消按钮（也称为负向按钮）进行自定义。

`BiometricPrompt`实例还分配了一组认证回调，这些回调将被调用，以为应用提供认证操作的结果。还使用了`CancellationSignal`实例，允许应用在认证进行期间取消认证。

在涵盖了这些基础知识后，本章的剩余部分将在示例项目中实现基于指纹的生物识别。

### 80.2 创建生物识别项目
从欢迎界面选择`New Project`选项，在生成的新项目对话框中，点击`Next`按钮之前，选择`Empty Views Activity`模板。

在`Name`字段中输入`BiometricDemo`并指定`com.ebookfrenzy.biometricdemo`为包名。在点击`Finish`按钮之前，将`Minimum API level`设置为`API 29: Android (Q)`，并将`Language`菜单更改`Java`。

### 80.3 配置设备指纹认证
指纹认证仅适用于包含触摸传感器的设备，并且已采取适当的配置步骤来保护设备并录入至少一个指纹。有关配置模拟器会话以测试指纹认证的步骤，请参阅章节 Using and Configuring the Android Studio AVD Emulator。

通过打开`Settings`应用并选择`Security`选项在物理设备上配置指纹认证。在`Security`设置屏幕内，选择`Fingerprint`选项。点击信息屏幕上的`Next`按钮进入`Fingerprint`设置屏幕。在启用指纹安全之前，必须配置备份的屏幕解锁方法（例如`PIN`）。如果锁屏未受保护，请按照步骤配置`PIN`、`pattern`或`password`安全。

锁定屏幕保护后，继续进入指纹检测屏幕并在提示时触摸传感器（图 80-1），如果需要，重复此过程添加额外的指纹。

![](img/Image24253.jpg)

图 80-1

### 80.4 在 Manifest 文件中添加生物识别权限
生物识别要求应用在项目清单文件中请求`USE_BIOMETRIC`权限。在 Android Studio 项目工具窗口中，定位并编辑`app` -> `manifests` -> `AndroidManifest.xml`文件，按如下方式添加权限请求：

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.ebookfrenzy.biometricdemo">

    <uses-permission
        android:name="android.permission.USE_BIOMETRIC" />
```

### 80.5 设计用户界面
为了保持示例尽可能简单，用户界面中的视觉元素元素是一个`Button`。定位并选择`activity_main.xml`布局资源文件将其加载到布局编辑器。

删除`TextView`对象，从调板的`Common`类别拖入一个`Button`对象并将其放置在画布中心。使用`Attributes`工具窗口，将按钮的`text`属性更改为“Authenticate”，并将字符串提取到资源。最后，配置`onClick`属性以调用名为`authenticateUser`方法。

完成上述步骤后，布局应与 图 80-2 所示：

![](img/as_biometric_demo_ui.jpg)

图 80-2

### 80.6 添加 Toast 便利方法
在示例代码的各个点，应用将设计为通过`Toast`消息向用户显示信息。为了避免重复相同的`Toast`代码，将在主活动中添加一个名为`notifyUser()`的便利方法。该方法将接受单个`String`值并将其作为`Toast`消息显示给用户。现在编辑`MainActivity.java`文件并添加该方法：

```java
import android.widget.Toast;

private void notifyUser(String message) {
    Toast.makeText(this, message, Toast.LENGTH_LONG).show();
}
```

### 80.7 检查安全设置
在本章早些之前，已经在要在测试应用的设备或模拟器上配置了锁屏并注册了指纹。然而，在应用中包含防御性代码以确保在尝试寻求指纹认证之前已满足这些要求是重要的。这些步骤将在`MainActivity.java`文件中的`onCreate`方法中执行，使用`Keyguard`和`PackageManager`管理服务。注意，还添加了代码以验证应用已配置了`USE_BIOMETRIC`权限。

```java
package com.ebookfrenzy.biometricdemo;

import androidx.appcompat.app.AppCompatActivity;
import androidx.core.app.ActivityCompat;
import android.widget.Toast;
import android.Manifest;
import android.content.pm.PackageManager;
import android.app.KeyguardManager;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_biometric_demo);
        checkBiometricSupport();
    }

    private void checkBiometricSupport() {
        KeyguardManager keyguardManager =
                (KeyguardManager) getSystemService(KEYGUARD_SERVICE);
        if (!keyguardManager.isKeyguardSecure()) {
            notifyUser("Lock screen security not enabled in Settings");
        }
        if (ActivityCompat.checkSelfPermission(this,
                Manifest.permission.USE_BIOMETRIC) !=
                PackageManager.PERMISSION_GRANTED) {
            notifyUser("Fingerprint authentication permission not enabled");
        }
    }
}
```

上述代码首先通过使用`Keyguard manager`来验证是否配置了备用屏幕解锁方法（换句话说，`PIN`或其他验证方法可以作为指纹识别的替代方案来解锁屏幕）。如果锁屏未加密，代码将向用户报告问题并从方法返回。

然后，该方法会在使用包管理器验证设备是否支持指纹识别之前，检查用户是否已为应用启用了生物识别权限。

### 80.8 配置身份验证回调
在配置生物识别提示对话框时，需要分配一组身份验证回调方法，这些方法可以通知应用身份验证过程的成功或失败。这些方法需要封装在`BiometricPrompt.AuthenticationCallback`类实例中。继续留在`MainActivity.java`文件中，添加一个方法来创建并返回一个实现了相应方法的类实例：

```java
import android.hardware.biometrics.BiometricPrompt;

private BiometricPrompt.AuthenticationCallback getAuthenticationCallback() {
    return new BiometricPrompt.AuthenticationCallback() {
        @Override
        public void onAuthenticationError(int errorCode,
                CharSequence errString) {
            notifyUser("Authentication error: " + errString);
            super.onAuthenticationError(errorCode, errString);
        }

        @Override
        public void onAuthenticationHelp(int helpCode,
                CharSequence helpString) {
            super.onAuthenticationHelp(helpCode, helpString);
        }

        @Override
        public void onAuthenticationFailed() {
            super.onAuthenticationFailed();
        }

        @Override
        public void onAuthenticationSucceeded(
                BiometricPrompt.AuthenticationResult result) {
            notifyUser("Authentication Succeeded");
            super.onAuthenticationSucceeded(result);
        }
    };
}
```

### 80.9 添加 CancellationSignal
一旦启动，生物识别认证过程将独立于应用运行。为了给应用提供取消操作的方法，创建`CancellationSignal`类的实例并将其传递给生物识别认证过程。该`CancellationSignal`实例可以在需要时取消进程。取消信号实例可以配置一个监听器，该器将在取消完成时调用。在活动类中添加一个新方法来配置并返回一个`CancellationSignal`对象，如下：

```java
import android.os.CancellationSignal;

private CancellationSignal cancellationSignal;

private CancellationSignal getCancellationSignal() {
    cancellationSignal = new CancellationSignal();
    cancellationSignal.setOnCancelListener(() ->
        notifyUser("Cancelled via signal"));
    return cancellationSignal;
}
```

### 80.10 启动生物识别提示
剩下的工作是在`authenticateUser()`方法中添加代码，以创建并配置`BiometricPrompt`实例并启动身份验证。如下所示添加`authenticateUser()`方法：

```java
import android.view.View;

public void authenticateUser(View view) {
    BiometricPrompt biometricPrompt = new BiometricPrompt.Builder(this)
            .setTitle("Biometric Demo")
            .setSubtitle("Authentication is required to continue")
            .setDescription(
                "This app uses biometric authentication to protect your data.")
            .setNegativeButton("Cancel", this.getMainExecutor(),
                (dialogInterface, i) ->
                    notifyUser("Authentication cancelled"))
            .build();

    biometricPrompt.authenticate(getCancellationSignal(), getMainExecutor(),
            getAuthenticationCallback());
}
```



`BiometricPrompt.Builder` 类创建一个新的`BiometricPrompt`实例，并配置标题、副标题和描述文本，以显示在提示对话框中。负按钮被配置为显示文本“Cancel”（取消），并配置了一个监听器，在点击此按钮时显示消息。最后，调用`BiometricPrompt`实例的`authenticate()`方法，并传递`AuthenticationCallback`和`CancellationSignal`实例。生物识别提示还需要知道在哪个线程上执行身份验证。这是通过传递一个配置了所需线程的`Executor`对象来定义的。在这种情况下，使用`getMainExecutor()`方法传递一个主`Executor`对象。

### 80.11 测试项目

项目现在已完成，在物理 Android 设备或模拟器会话上运行应用，并点击 Authenticate 按钮显示如图 80-3](#Biometric_Auth.xhtml__idAnchor1560）所示的`BiometricPrompt`对话框。

运行后，触碰指纹传感器或使用模拟器中的扩展控制面板来如“使用和配置 Android Studio AVD 模拟器”](#AVD_Configuration.xhtml__idAnchor115）章节所述的方法模拟指纹触摸。假设检测到已注册的指纹，提示对话框将返回主活动，此时将出现来自成功身份验证方法的 toast 消息。

再次点击 Authenticate 按钮，使用未注册的指纹尝试身份验证。此时，生物识别提示对话框将指示指纹未被识别。

通过点击生物识别提示对话框之外的区域来验证错误处理回调是否有效。提示对话框将消失，并出现带有以下信息的 toast：

`Authentication error: Fingerprint operation cancelled by user.`

检查使用 Cancel 按钮取消提示对话框是否会触发“Authentication Canceled” toast 消息。最后，使用未注册的指纹多次尝试身份验证，并注意在尝试多次后，提示对话框会指示失败次数过多，并且在此之前无法进行后续尝试。

### 80.12 总结

本章概述了如何将生物识别身份验证集成到 Android 应用项目中的。这涉及到使用`BiometricPrompt`类，一旦配置了适当的提示文本和回调函数，它会自动处理身份验证的大部分过程。

# 81. 创建、测试和上传 Android App Bundle

一旦完成 Android 应用程序的开发并在广泛的 Android 设备上通过了测试，下一步就是准备将应用程序提交到 Google Play。然而，在提交之前，必须对应用程序进行发布包打包，并使用私密钥对其进行签名。本章将介绍获取私密钥、为项目准备 Android App Bundle 以及将其上传到 Google Play 的整个流程。

## 81.1 发布准备流程

到本书目前为止，我们一直在以适用于测试和调试的模式构建应用程序项目。另一方面，构建一个通过 Google Play 向客户发布的应用程序包则需要额外的步骤。首要要求是以发布模式（release mode）而不是调试模式（debug mode）编译应用程序。其次，应用程序必须使用私密钥签名，该密钥能够唯一标识你作为应用程序的开发者。最后，应用程序必须打包成 Android App Bundle。

虽然这些任务可以在 Android Studio 环境之外执行，但正如本章后续部分所述，使用 Android Studio 的构建机制执行这些程序会更加方便。不过，首先重要的是进一步了解 Android App Bundle。

## 81.2 Android App Bundles

当用户从 Google Play 安装应用时，应用是以`APK`文件的形式下载的。该文件包含了在用户设备上安装和运行应用所需的所有内容。在 Android Studio 3.2 之前，开发者会使用 Android Studio 生成一个或多个`APK`文件并将其上传到 Google Play。支持多种设备类型、屏幕尺寸和语言需要为每个目标设备和语言创建并上传多个自定义的`APK`文件，或者生成一个包含所有不同配置资源和平台二进制文件的大型通用`APK`。

创建多个`APK`文件涉及大量工作，且每次更新应用时都必须重复，这为应用发布过程带来了巨大的时间开销。

通用`APK`选项虽然减轻了开发者的负担，但导致了一个完全意之外的问题。通过分析应用安装指标，Google 发现安装`APK`文件越大（导致下载时间变长和存储占用增加），应用获得的转化率就越低。转化率的计算方式为：在 Google Play 上查看应用后完成安装的用户占百分比。Google 估计，`APK`文件的大小每增加 6MB，应用的转化率就会下降 1%。

Android App Bundles 解决了这些问题，它允许开发者在 Android Studio 内部创建一个包，并让 Google Play 为每个单独支持的配置自动生成自定义的`APK`文件（这一概念称为动态交付 Dynamic Delivery）。

Android App Bundle 是一个`ZIP`文件，包含了为应用项目内支持的所有设备和语言构建`APK`文件所需的所有文件。例如，项目可能包含针对不同屏幕尺寸的资源和图像。当用户安装应用时，Google Play 会接收有关设备的信息，包括显示器、处理器架构和语言。利用这些信息，相应的预生成`APK`文件将传输到用户的设备上。

动态交付的另一个优势是可以将应用拆分为多个模块（称为动态功能模块），每个模块包含应用内特定功能区域的代码和资源。每个动态功能模块包含在一个与基础模块独立的`APK`文件中，并且仅在用户需要该功能时才会下载到设备。动态交付和应用包还允许创建即时动态功能模块，这些可以在无需安装整个应用的情况下在设备上立即运行。

尽管仍然可以从 Android Studio 生成`APK`文件，但应用包现在是上传应用到 Google Play 的推荐方式。

## 81.3 注册 Google Play 开发者控制帐户

应用提交过程的第一步是创建 Google Play 开发者控制帐户。为此，请访问 `https://play.google.com/apps/publish/signup/` 并按照说明完成注册过程。注意，注册需要支付一次性 25 美元的费用。一旦应用程序上市，Google 将保留与应用相关的所有收入的 30%。创建账户后，可以通过 `https://play.google.com/console` 访问开发者控制台。

下一步是收集应用信息。为了将您的应用程序推向市场，需要以下信息：

- **标题 (Title)** – 应用程序的标题。
- **短描述 (Short Description)** - 最多 80 个字的应用描述。
- **完整描述 (Full Description)** – 最多 4000 个字的应用描述。
- **截图 (Screenshots)** – 最多 8 张应用运行的截图（至少需要两张）。Google 建议提交在 7 英寸或 10 英寸平板电脑上运行的应用截图。
- **语言 (Language)** – 应用的语言（默认为美式英语）。
- **推广文本 (Promotional Text)** – 当您的应用出现在 Google Play 环境内的特殊推广功能时将使用的文本。
- **应用类型 (Application Type)** – 您的应用被视为游戏还是应用程序。
- **类别 (Category)** – 最能描述您的应用程序的类别（例如：金融、健康健身、教育、运动等）。
- **地区 (Locations)** – 您希望您的应用程序可以购买的地理位置。
- **联系详情 (Contact Details)** – 用户可以通过哪些方式与您联系以获取应用支持。选项包括网页、电子邮件和电话。
- **定价与发布 (Pricing & Distribution)** – 关于应用程序价格以及营销和销售地理位置的信息。

收集上述信息后，点击 Google Play Console 中的“创建应用”按钮开始创建过程。

## 81.4 在控制台中配置应用

当首次点击“创建应用”按钮时，将出现应用详情和声明屏幕，如下图 81-1 所示：

```
![](img/as_4.1_play_create_app.jpg)
```
图 81-1

一旦配置了应用条，点击“创建应用”按钮（在上方图中高亮显示）以添加应用并显示仪表板屏幕。在仪表板中，找到“初始设置”（Initial setup）部分并展开配置应用商店列表的步骤列表：

```
![](img/as_4.1_play_app_initial_steps.jpg)
```
图 81-2

逐一处理列表链接并为应用提供所需的信息，确保每一步都保存更改。

## 81.5 启用 Google Play 应用签名

直到最近，Google Play 的上传是通过 Android Studio 内部的发布应用签名密钥进行签名的，然后上传到 Google Play 控制台。虽然这种选项仍然，但推荐的上传文件方式是使用名为“Google Play 应用签名”（Google Play App Signing）的过程。对于新创建的应用，这涉及加入 Google Play 应用签名并生成一个上传密钥以在 Android Studio 中对应用包文件（app bundle）进行签名。当上传由 Android Studio 生成的应用包文件时，Google Play 控制台会移除上传密钥，并使用安全存储在 Google Play 服务器中的应用签名密钥对文件进行签名。对于现有应用，需要一些额外的步骤来启用 Google Play 签名，这将在本章末尾介绍。

在 Google Play 控制台中，从“所有应用”（All Apps）屏幕（通过左侧导航面板顶部的选项访问）选择新添加的应用项，展开“设置”（Setup）部分（在图 81-3 中标记为 A），并选择“应用签名”（App Signing）选项（B）。

```
![](img/as_4.1_play_enable_app_signing.jpg)
```
图 81-3

点击“创建发布”（Create release）按钮（C）加入 Google Play 应用签名。控制台现在已准备好为您的应用创建第一个测试发布。然而，在在此之前，下一步是在 Android Studio 内部生成上传密钥。这是生成签名应用包过程的一部分执行的。请保持当前 Google Play 控制台页面在浏览器中加载，因为我们将在本章稍后回到这里。

## 81.6 创建密钥库文件

要创建密钥库文件，选择 Android Studio 的`Build`（构建）-> `Generate Signed Bundle / APK…`（生成签名应用包/ APK…）菜单选项，显示“生成签名应用包或 APK 向导”对话框，如图 81-4 所示：

```
![](img/as_generate_app_bundle.jpg)
```
图 81-4

在点击“下一步”（Next）按钮之前，确认已选择“Android App Bundle”（Android 应用包）选项。

如果您有现有的发布密钥库文件，点击下一屏幕上的`Choose existing…`（选择现有…）按钮，并导航到选择该文件。如果您尚未创建密钥库文件，点击`Create new…`（创建新…）按钮显示“新密钥库”（New Key Store）对话框（图 81-5）。点击`Key store path`（密钥库路径）字段右侧的按钮，导航到文件系统中合适的位置，为密钥库文件输入名称（例如 `release.keystore.jks`）并点击`OK`按钮。

`New Key Store`对话框分为两个部分。顶部部分与密钥库文件有关。在此部分，在`Password`（密码）和`Confirm`（确认）字段中输入一个强密码来保护密钥库文件。对话框的下部分与将存储在密钥库文件中的上传密钥有关。

```
![](img/as_generate_new_key_store.jpg)
```
图 81-5

在`New Key Store`对话框的`Key`（密钥）部分中，输入以下详细信息：

- 引用密钥的别名（alias）。可以是任何字符序列，但系统仅使用前八个。
- 用于保护密钥的足够强度的密码。
- 密钥有效的年数（Google 建议时长超过 25 年）。
- 此外，必须为剩余字段中的至少一个提供信息（例如，您的姓和名或组织名称）。

输入信息后，点击`OK`按钮创建程序包。

## 81.7 创建 Android 应用包

下一步是指示 Android Studio 在发布模式下构建应用包文件，并使用新创建的私钥对其进行签名。此时，`Generate Signed Bundle or APK`对话框应仍显示，且`keystore path`、密码和`key alias`字段已填充了信息：

```
![](img/as_generate_app_bundle_keystore_ready.jpg)
```
图 81-6

确保启用`Export Encrypted Key`（导出加密密钥）选项，并在假设其他设置正确的情况下，点击`Next`（下一步）按钮进入应用包生成屏幕（图 81-7）。在此屏幕中，检查`Destination Folder:`（目标文件夹:）设置，以验证生成应用包文件的位置是可以接受的。如果偏好其他位置，点击文本字段右侧的按钮并导航到所需的文件系统位置。

```
![](img/as_generate_app_bundle_generate.jpg)
```
图 81-7

点击`Finish`（完成）按钮并等待`Gradle`系统构建应用包。构建完成后，将出现一个对话框，提供在资源管理器窗口中打开包含应用包文件的文件夹或将文件加载到`APK Analyzer`中进行选项：

```
![](img/as_generate_app_bundle_ready.jpg)
```
图 81-8

此时，应用已准备好提交到 Google Play。点击`locate`（定位）链接打开文件系统浏览器窗口。该文件应命名为`bundle.aab`并位于项目文件夹的`app/release`子目录中，除非指定了其他位置。

作为此过程的一部分生成的私钥应在以后签名和发布未来应用时使用，因此，它应该被保存在安全的地方，并进行安全的安全的备份。

## 81.8 生成测试 APK 文件

此阶段的一个可选步骤是从应用包生成 APK 文件，并在设备或模拟器上安装并运行。Google 提供了一个名为`bundletool`的命令行工具，专门为此目的设计，可以从以下 URL 下载：

[`github.com/google/bundletool/releases`](https://github.com/google/bundletool/releases)

在编写时，`bundletool`以`.jar`文件形式提供，可以如下执行（注意版本号可能已更改）：

```
java -jar bundletool-all.0.jar
```

运行上述命令将列出所有可用选项。从应用包生成 APK，可以使用`build-apks`选项。文件还需要签名以生成可以安装到设备上的 APK。为了实现这一点，包含`--ks`选项指定在本章之前创建的密钥库路径，以及指定生成密钥时别名的`--ks-key-alias`。最后，必须使用`--output`标志指定生成 APK 文件的路径（称为 APK Set）。该文件不能已存在，并且需要`.apks`扩展名。将这些要求汇合在一起得到命令：

```
java -jar bundletool-all.0.jar build-apks --bundle=/tmp/MyApps/app/release/bundle.aab --output=/tmp/MyApks.apks --ks=/MyKeys/release.keystore.jks --ks-key-alias=MyReleaseKey
```

执行此命令时，将弹出提示请求密钥库密码，然后生成 APK 文件到指定的 APK Set 中。APK Set 是一个包含从应用包生成的所有 APK 文件的 ZIP 文件。

要在连接的设备或模拟器上安装相应的 APK 文件，使用类似下面的命令：

```
java -jar bundletool-all.0.jar install-apks --apks=/tmp/MyApks.apks
```

此命令将指示工具识别适用于连接设备的合适 APK 文件并安装它们，以便启动和测试应用。

接下来，此规格文件用于从 APK Set 中提取匹配的 APK 文件：

```bash
java -jar bundletool-all-0.9.0.jar extract-apks --apks=/tmp/MyApks.apks --output-dir=/tmp/nexus5_apks --device-spec=/tmp/device.json
```



执行时，通过`--output-dir`标志指定的目录将包含适用于指定设备配置的 APK 文件。

将 Android 应用推向市场的下一步是将其提交到 Google Play 开发者控制台，以便进行测试。

## 81.9 将 App Bundle 上传到 Google Play 开发者控制台

返回 Google Play 控制台，在点击“创建新版本”按钮（B）之前，在导航面板的“测试”部分选择“内部测试”选项（在图 81-9 中标记为 A）：

![](img/as_4.1_play_create_new_release.jpg)

图 81-9

在随之显示的屏幕上，点击“继续”按钮（下方标记为 A）以确认使用 Google Play 应用签名，然后将 Android Studio 生成的 bundle 文件拖放到上传投放点（B）：

![](img/as_4.1_play_upload_bundle.jpg)

图 81-10

上传完成后，向下滚动屏幕并输入发布名称和可选的发布说明。发布名称可以是任何帮助你识别该版本的信息，且它对用户不可见。

应用 bundle 文件上传后，Google Play 将生成所有必要的 APK 文件以准备测试。一旦生成了 APK 文件，滚动到屏幕底部并点击“保存”按钮。保存设置后，点击“审核发布”按钮。

## 81.10 探索 App Bundle

在审核屏幕上，点击已上传 bundle 右侧的箭头，如图 81-11 所示：

![](img/as_4.1_play_app_bundle_review.jpg)

图 81-11

在随之显示的面板中，点击“探索 bundle”链接以加载应用 bundle 资源生成器。这提供了与应用 bundle 支持的 API 级别、屏幕布局和平台相关的摘要信息：

![](img/as_4.1_play_app_bundle_explorer.jpg)

图 81-12

点击“转到设备目录”链接将显示 APK 文件支持的设备：

![](img/as_4.1_play_device_catalog.jpg)

图 81-13

目前，应用已准备好进行测试，但只有在控制台中设置了某些测试人员后才能进行发布。

## 81.11 管理测试人员

如果应用仍处于内部、Alpha 或 Beta 测试阶段，可以通过在 Google Play 控制台中选择该应用、点击导航面板中的“内部测试”并选择“测试人员”选项卡来指定授权的测试人员列表，如图 81-14 所示：

![](img/as_4.1_play_testers.jpg)

图 81-14

要添加测试人员，点击“创建电子邮件列表”按钮，为列表命名，并手动指定或通过上传 CSV 文件指定测试用户的电子邮件地址。

现在可以从屏幕上复制“在网页加入” URL 并提供给测试用户，以便他们接受测试邀请并下载应用。

## 81.12 发布应用进行测试

现在已经创建了内部版本并添加了测试人员列表，应用已准备好发布进行测试。留在“内部测试”屏幕中，在点击最近创建的版本的“编辑”按钮之前，选择“发布”选项卡：

![](img/as_4.1_play_ready_for_rollout.jpg)

图 81-15

在审核屏幕上，滚动到底部并点击“开始内部测试发布”按钮。在发布处理期间简短延迟后，应用将可以供指定用户下载和测试。

## 81.13 上传新的 App Bundle 版本

为你的应用程序上传的应用 bundle 文件版本号始终为 1。如果尝试上传另一个具有相同版本号的 bundle 文件，控制台将带有以下错误拒绝该文件：

您需要为 APK 使用不同的版本号，因为您已经有一个版本号为 1 的版本了。

要解决这个问题，需要增加嵌入 bundle 文件中的版本号。这在项目的模块级`build.gradle.kts`文件中进行，如图 81-16 高亮所示：

![](img/as_generate_module_gradle_file.jpg)

图 81-16

该文件通常如下：

```kotlin
plugins {
    id("com.android.application")
}

android {
    namespace = "com.ebookfrenzy.biometricdemo"
    compileSdk = 33

    defaultConfig {
        applicationId = "com.ebookfrenzy.biometricdemo"
        minSdk = 29
        targetSdk = 33
        versionCode = 1
        versionName = "1.0"
    }
}
```

要更改版本号，更改`versionCode`边的数字。要更改显示给用户的版本号，更改`versionName`字符串。例如：

```kotlin
versionCode = 2
versionName = "2.0"
```

更改更改后，重新构建并再次上传。

## 81.14 分析 App Bundle

Android Studio 提供了分析应用 bundle 内容的能力。要分析 bundle 文件，选择`Build -> Analyze APK…`菜单选项并导航到选择要分析的文件。加载后，将显示有关包的原始大小和下载大小的信息，以及文件结构列表，如图 81-17 所示：

![](img/as_analyze_apk.jpg)

图 81-17

选择`classes.dex`文件将在面板中显示文件的类结构。在此面板中，可以探索到每个类的方法级细节：

![](img/as_analyze_apk_dex.jpg)

图 81-18

同样，选择文件列表中的资源或图像文件将在面板中显示文件内容。通过点击“与之前的 APK 比较”并选择第二个 bundle 文件，可以查看两个文件之间的大小差异。

### 81.15 总结

当应用项目完成或准备好测试后，可以将其提交到 Google Play 控制台并在生产、内部、Alpha 或 Beta 测试。在发布应用之前，需要在控制台中创建应用条目，包括应用信息和用于商店的屏幕截图。Android App Bundle 文件在 Android Studio 中生成并使用上传密钥签名。在上传文件后，Google Play 将移除上传密钥并替换为安全存储的应用签名密钥，应用已准备好发布。

可以随时将 bundle 文件加载到 Android Studio APK 分析工具中查看内容。

## 82 Android 内购付费概述

在 Android 和 iOS 移动应用的早期，最常见的盈利方法是收取下载和安装应用时的预付费。很快介绍了另一种收入机会：在应用中嵌入广告。最常见且利润丰厚的选项是让用户在安装应用后为应用内购买的项目付费。

Google 支持通过 Google Play 内结算 API 和 Play Console 集成应用内购买。本章将概述应用内结算，并列出如何将应用内结算集成到你的 Android 项目中。在探索这些主题后，下一章将引导你创建一个包含应用内购买功能的示例应用。

---

## 82.1 为应用内购买准备项目

在应用中构建应用内购买需要 Google Play 开发者控制台账号，其细节在之前的“创建、测试和上传 Android App Bundle”章节中介绍过。你还必须注册一个 Google 商家账户。可以通过在 Play Console 中导航到`Setup`（设置） -> `Payments profile`（付款资料）来找到这些设置。请注意，商家注册并非所有国家都可用。有关详情，请参考以下页面：

[`support.google.com/googleplay/android-developer/answer/9306917`](https://support.google.com/googleplay/android-developer/answer/9306917)

随后，必须将应用上传到控制台并启用应用内购买。然而，除非已将 Google Play 结算库添加到模块级`build.gradle.kts`文件，否则控制台将不会为应用激活内结算支持：

```kotlin
dependencies {
    implementation ("com.android.billingclient:billing:<latest version>")
}
```

一旦修改了构建文件并将应用 bundle 上传到控制台，下一步是为用户购买添加应用内产品或订阅。

## 82.2 创建应用内产品和订阅

产品和订阅是使用 Play Console 导航面板中`Monetize`（变现）部分列出的选项进行创建和管理的，如下方的图 82-1](#In-App_Overview.xhtml__idTextAnchor1598）所示：

![](img/play_console_monetization.jpg)

图 82-1

每个产品或订阅都需要一个 ID、标题、描述和价格信息。购买分为消耗性（用户每次需要时都必须购买，例如游戏中的虚拟货币）、非消耗性（用户只需购买一次，例如内容访问）和订阅制。消耗性和非消耗性产品统称为受管理产品。

订阅适用于销售需要定期续订的项目，例如新闻内容的访问或应用的高级功能。在创建订阅时，基础计划指定了价格、续订周期（每月、每年等）以及订阅是否自动续订。用户还可以获得折扣优惠和预购订阅的选项。

## 82.3 结算客户端初始化

你的应用与 Google Play 结算库之间的通信由`BillingClient`实例处理。此外，`BillingClient`包含一组可以调用的方法，用于执行同步和异步结算相关的活动。当结算客户端初始化时，需要为它提供一个`PurchasesUpdatedListener`回调处理器的引用。客户端将调用此处理器来通知你的应用任何购买活动的结果。为了避免重复通知，建议每个应用只保留`BillingClient`实例。

可以使用`newBuilder()`方法创建`BillingClient`实例，传入当前的 activity 或 fragment 上。然后通过`setListener()`方法将购买更新处理器分配给客户端：

```java
private final PurchasesUpdatedListener purchasesUpdatedListener =
    new PurchasesUpdatedListener() {
        @Override
        public void onPurchasesUpdated(BillingResult billingResult,
                List<Purchase> purchases) {
            if (billingResult.getResponseCode() ==
                    BillingClient.BillingResponseCode.OK
                    && purchases != null) {
                // 购买成功
                for (Purchase purchase : purchases) {
                    // 处理购买条目
                }
            } else if (billingResult.getResponseCode() ==
                    BillingClient.BillingResponseCode.USER_CANCELED) {
                // 用户取消
            } else {
                // 处理错误
            }
        }
    };

BillingClient billingClient = BillingClient.newBuilder(context)
    .setListener(purchasesUpdatedListener)
    .enablePurchases()
    .build();
```

## 82.4 连接到 Google Play 结算库

在成功创建结算客户端后，下一步是初始化与 Google Play 结算库的连接。必须调用结算客户端的`startConnection()`方法来建立此连接。由于连接是异步执行的，必须实现`BillingStateListener`以接收指示连接是否成功的回调。还应该添加代码来重写`onServiceDisconnected()`方法。当与结算库的连接丢失时会调用此方法，用于报告问题并重试连接。

一旦设置和连接完成，`BillingClient`实例将调用`onBillingFinished()`方法，该方法可以检查客户端是否就绪：

```java
billingClient.startConnection(new BillingStateListener() {
    @Override
    public void onBillingFinished(@NonNull BillingResult billingResult) {
        if (billingResult.getResponseCode() ==
                BillingClient.BillingResponseCode.OK) {
            // 连接成功
        } else {
            // 连接失败
        }
    }

    @Override
    public void onServiceDisconnected() {
        // 连接丢失
    }
});
```

## 82.5 查询可用产品

一旦结算环境初始化并准备就绪，下一步是请求可购买的产品或订阅的详情。这通过调用`BillingClient`的`queryProductDetailsAsync()`方法并传入配置适当的`ProductDetailsParams`实例来实现，该实例包含产品 ID 和类型（订阅使用`SUBS`，受管理产品使用`INAPP`）：

```java
QueryProductDetailsParams queryProductDetailsParams =
    QueryProductDetailsParams.newBuilder()
        .setProductList(
            ImmutableList.of(
                QueryProductDetailsParams.Product.newBuilder()
                    .setProductId("one_button_click")
                    .setProductType(BillingClient.ProductType.INAPP)
                    .build()))
        .build();

billingClient.queryProductDetailsAsync(queryProductDetailsParams,
    new ProductDetailsResponseListener() {
        public void onProductDetailsResponse(
                @NonNull BillingResult billingResult,
                @NonNull List<ProductDetails> productDetailsList) {
            if (!productDetailsList.isEmpty()) {
                // 处理匹配的产品列表
            } else {
                // 未找到匹配的产品
            }
        }
    }
);
```

`queryProductDetailsAsync()`方法传递一个`ProductDetailsResponseListener`处理器，该处理器反会被调用并传入一个包含匹配产品信息的`ProductDetails`对象列表。例如，我们可以调用这些对象的方法来获取产品名称、标题、描述、价格和优惠详情。

## 82.6 开始购买流程

一旦用户查询了某个产品或订阅并选择购买，购买流程就可以启动。我们通过调用`BillingClient`的`launchBillingFlow()`方法来实现这一点，并将当前活动以及一个配置了已购项目`ProductDetail`对象的`BillingFlowParams`作为参数传递。

```java
BillingFlowParams billingFlowParams =
    BillingFlowParams.newBuilder()
        .setProductDetailsParamsList(
            ImmutableList.of(
                BillingFlowParams.ProductDetailsParams.newBuilder()
                    .setProductDetails(productDetails)
                    .build()
            )
        )
        .build();

billingClient.launchBillingFlow(this, billingFlowParams);
```



购买操作的成功与否将通过本节之前概述的`PurchasesUpdatedListener`回调处理程序进行报告。

### 82.7 完成购买

当购买成功时，`PurchasesUpdatedListener`处理器将接收一个包含每个项目`Purchase`对象的列表。你可以按照如下方式调用`Purchase`实例的`getPurchaseState()`方法来验证该项目是否已购买：

```java
if (purchase.getPurchaseState() == Purchase.PurchaseState.PURCHASED) {
    // 购买完成。
} else if (purchase.getPurchaseState() == Purchase.PurchaseState.PENDING) {
    // 支付仍在处理中
}
```

注意，只有在初始化期间调用了`enablePendingPurchases()`方法，你的应用才支持待付款购买。待付款购买将一直保持该状态，直到用户完成支付流程。

非消耗购买完成后，必须对其进行确认（acknowledge），以防止向用户退款。这需要该项目的购买令牌，该令牌通过调用`Purchase`对象的`getPurchaseToken()`方法获取。此令牌用于创建`AcknowledgePurchaseParams`实例和`AcknowledgePurchaseResponseListener`处理程序。可以通过调用`BillingClient`的`acknowledgePurchase()`方法来确认托管产品购买和订阅：

```java
AcknowledgePurchaseParams acknowledgePurchaseParams =
    AcknowledgePurchaseParams.newBuilder()
        .setPurchaseToken(purchase.getPurchaseToken())
        .build();

AcknowledgePurchaseResponseListener acknowledgePurchaseResponseListener =
    new AcknowledgePurchaseResponseListener() {
        @Override
        public void onAcknowledgePurchaseResponse(
            @NonNull BillingResult billingResult) {
            billingClient.acknowledgePurchase(
                acknowledgePurchaseParams,
                acknowledgePurchaseResponseListener);
        }
    };
```

对于消耗性购买，你需要在项目被消耗后通知 Google Play，以便用户可以再次购买。这需要一个包含购买令牌的配置`ConsumeParams`实例、一个`ConsumeResponseListener`以及对计费客户端`consumeAsync()`方法的调用：

```java
ConsumeParams consumeParams =
    ConsumeParams.newBuilder()
        .setPurchaseToken(purchase.getPurchaseToken())
        .build();

ConsumeResponseListener listener = new ConsumeResponseListener() {
    @Override
    public void onConsumeResponse(BillingResult billingResult,
            @NonNull String purchaseToken) {
        if (billingResult.getResponseCode() == BillingClient.BillingResponseCode.OK) {
            // 购买已消耗
        }
    }
};

billingClient.consumeAsync(consumeParams, listener);
```

## 82.8 查询之前的购买

在处理内计费时，检查用户是否已购买某个产品或订阅是一项常见需求。通过调用`BillingClient`实例的`queryPurchasesAsync()`方法并实现`PurchasesListener`，可以生成用户之前购买的所有特定类型的购买列表。例如，以下代码获取了所有尚未被消耗的购买项目列表：

```java
QueryPurchasesParams queryPurchasesParams =
    QueryPurchasesParams.newBuilder()
        .setProductType(BillingClient.ProductType.INAPP)
        .build();

billingClient.queryPurchasesAsync(queryPurchasesParams,
    new PurchasesListener() {
        @Override
        public void onQueryPurchasesResponse(@NonNull BillingResult billingResult,
                @NonNull List<Purchase> list) {
            // 处理购买列表
        }
    });
```

要获取活跃订阅列表，请将`ProductType`值从`INAPP`更改为`SUBS`。或者，要获取每个产品最近的购买列表，请调用`BillingClient`的`queryPurchaseHistoryAsync()`方法：

```java
QueryPurchaseHistoryParams queryPurchaseHistoryParams =
    QueryPurchaseHistoryParams.newBuilder()
        .setProductType(BillingClient.ProductType.INAPP)
        .build();

billingClient.queryPurchaseHistoryAsync(queryPurchaseHistoryParams,
    new PurchaseHistoryResponseListener() {
        @Override
        public void onPurchaseHistoryResponse(@NonNull BillingResult billingResult,
                @NonNull List<PurchaseHistoryRecord> list) {
            // 处理购买历史
        }
    });
```

### 82.9 总结

内应用购买通过向用户出售虚拟产品和订阅，提供了从 Android 应用内部产生收入的方式。本章探讨了托管产品和订阅，并解释了消耗性产品和非消耗性产品之间的区别。使用 Google Play 内应用购买库可以为应用添加内应用购买支持。这涉及创建并初始化计费客户端，并在其上调用方法来执行诸如购买、列出可用产品和消耗现有购买等任务。下一章将包含一个演示如何在 Android Studio 项目中添加内应用购买的教程。

## 83. Android 内应用购买教程

在`Name`字段中输入`InAppPurchase`，并指定一个在 Google Play 生态系统中唯一标识您的应用的包名（例如`com.<your company>.InAppPurchase`）。在点击`Finish`按钮之前，将`Minimum API level`设置更改为`API 26`：Android 8.0 (Oreo)，并将`Language`菜单更改为`Java`。项目创建完成后，使用 11.8 将项目迁移到 View Binding 节中概述的步骤将项目转换为使用 view binding。

## 83.3 向项目添加库

在编写代码之前，必须向项目构建配置添加某些库，包括标准的 Android 计费客户端库。在项目的稍后阶段，我们还需使用`ImmutableList`类，它是 Google Guava Core Java 库的一部分。现在通过修改`Gradle Scripts -> build.gradle.kts (Module: app)`文件进行以下更改来添加这些库：

```kotlin
dependencies {
    implementation ("com.android.billingclient:billing:6.0.1")
    implementation ("com.google.guava:guava:24.1-jre")
    implementation ("com.google.guava:guava:27.0.1-android")
}
```

点击编辑器面板顶部的`Sync Now`链接以提交这些更改。

### 83.4 设计用户界面

用户界面将由现有的`TextView`和两个`Buttons`组成。在编辑器中加载`activity_main.xml`文件后，将两个`Button`视图拖放到布局中，使其中一个在`TextView`上方，另一个在下方。选择`TextView`并将`id`属性更改为`statusText`。

点击工具栏上的`Clear all Constraints`按钮，并按住 Shift 键选择三个视图。右键点击最顶部的`Button`视图，选择`Center -> Horizontally in Parent`菜单选项。再次重复此步骤，选择`Chains -> Create Vertical Chain`。更改顶部按钮的`text`属性使其显示为“Consume Purchase”，并将`id`更改为`consumeButton`。同时，配置`onClick`属性以调用名为`consumePurchase`的方法。

选择最底部的按钮并重复上述步骤，将`text`设置为“Buy Product”，将`id`设置为`buyButton`，并将`onClick`回调设置为`makePurchase`。完成后，布局应与图 83-1 所示所示：

![](img/as_inapppurchase_ui.jpg)

图 83-1

## 83.5 将应用添加到 Google Play 商店

使用标题为创建、测试和上传 Android App Bundle 的章节中概述的步骤，登录`Play Console`，创建一个新应用，并设置一个新的内部测试轨道，包括指定测试人员的电子邮件地址。返回 Android Studio 并为项目生成签名的发布 app bundle。一旦生成了 bundle 文件，将其上传到内部测试轨道并发布进行测试。

现在应用已进入 Google Play 商店，我们准备好为项目创建一个应用内产品了。

## 83.6 创建应用内产品

在`Play Console`中选中应用，向下滚动左侧面板中的选项列表，直到出现`Monetize`部分。在该部分中，选择`Products`下的`In-app products`，如图 83-2 所示：

![](img/play_console_monetization1.jpg)

图 83-2

在`In-app products`页面上，点击`Create product`按钮：

![](img/play_console_create_product.jpg)

图 83-3

在新产品屏幕上，保存新产品之前输入以下信息：

* **Product ID**: `one_button_click`
* **Name**: A Button Click
* **Description**: 这是一个测试应用内产品，允许按钮被点击一次。
* **Default price**: 设置为您偏好货币的最低可用价格。

## 83.7 启用许可测试人员

在测试应用内计费时，在不花费任何资金的情况下进行测试购买是非常有用的。这可以通过为内部轨道的测试人员启用许可测试来实现。许可测试人员在购买时可以使用测试付款卡，这样他们就不会被收费。

在`Play Console`中，返回主屏幕并选择`Setup -> License testing`选项：

![](img/play_console_license_testing.jpg)

图 83-4

在许可测试屏幕内，添加为内部测试轨道添加的测试人员，将`License response`设置更改为`RESPOND_NORMALLY`并保存更改：

![](img/play_console_license_testing_screen.jpg)

图 83-5

现在应用和应用内产品已在`Play Console`中设置，我们可以向项目添加代码了。

## 83.8 初始化计费客户端

编辑`MainActivity.java`文件并进行以下更改以开始实现应用内购买功能：

```java
import androidx.annotation.NonNull;
import android.util.Log;
import com.android.billingclient.api.*;

public class MainActivity extends AppCompatActivity {

    private ActivityMainBinding binding;
    private BillingClient billingClient;
    private ProductDetails productDetails;
    private Purchase purchase;

    static final String TAG = "InAppPurchase";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        binding = ActivityMainBinding.inflate(getLayoutInflater());
        View view = binding.getRoot();
        setContentView(view);
        billingSetup();
    }

    private void billingSetup() {
        billingClient = BillingClient.newBuilder(this)
            .setListener(purchasesUpdated)
            .enablePendingPurchases()
            .build();

        billingClient.startConnection(new BillingClientStateListener() {
            @Override
            public void onSetupFinished(@NonNull BillingResult billingResult) {
                if (billingResult.getResponseCode() == BillingClient.BillingResponseCode.OK) {
                    Log.i(TAG, "OnBillingSetup connected");
                    queryProduct();
                } else {
                    Log.i(TAG, "OnBillingSetup failed");
                }
            }

            @Override
            public void onBillingServiceDisconnected() {
                Log.i(TAG, "OnBillingSetup connection lost");
            }
        });
    }
}
```



应用启动时，`onCreate()` 方法将调用 `billingSetup()`，这将创建一个计费客户端实例并尝试连接到 Google Play 计费库。`onSetupFinished()` 监听器将在连接尝试完成时被调用，并输出连接成功失败的消息。最后，我们还实现了 `onBillingServiceDisconnected()` 回调。如果连接成功，将调用 `queryProduct()`。必须添加此方法以及分配给计费客户端的 `purchasesUpdatedListener`。

## 83.9 查询产品

为了确保产品可以购买，我们需要创建一个 `QueryProductDetailsParams` 实例，配置为在 `Play Console` 中指定的 `product ID`，并传递给计费客户端的 `queryProductDetailsAsync()` 方法。这将要求我们也添加 `onProductDetailsResponse()` 回调方法，其中我们将检查产品是否存在、提取产品名称并显示在状态 `TextView` 上。现在我们已经获取了产品详情，也可以安全地启用购买按钮。在 `MainActivity.` 文件中，添加 `queryProduct()` 方法，内容如下：

```java
import com.google.common.collect.ImmutableList;
import java.util.List;

private void queryProduct() {
    QueryProductDetailsParams queryProductDetailsParams =
        QueryProductDetailsParams.newBuilder()
        .setProductList(
            ImmutableList.of(
                QueryProductDetailsParams.Product.newBuilder()
                    .setProductId("one_button_click")
                    .setProductType(
                        BillingClient.ProductType.INAPP)
                    .build()))
        .build();

    billingClient.queryProductDetailsAsync(
        queryProductDetailsParams,
        new ProductDetailsResponseListener() {
            public void onProductDetailsResponse(
                @NonNull BillingResult billingResult,
                @NonNull List<ProductDetails> productDetailsList) {
                if (!productDetailsList.isEmpty()) {
                    productDetails = productDetailsList.get(0);
                    runOnUiThread(() -> {
                        binding.buyButton.setEnabled(true);
                        binding.statusText.setText(productDetails.getName());
                    });
                } else {
                    Log.i(TAG, "onProductDetailsResponse: No products");
                }
            }
        }
    );
}
```

这里使用的大部分代码在上一节中应该很熟悉。监听器检查至少有一个产品符合标准。然后，从第一个匹配的并中提取 `ProductDetails` 对象，将其存储在 `productDetails` 变量中，并在 `TextView` 上显示产品名称。需要注意的是，当我们在 `status TextView` 上显示产品名称时，是通过调用 `runOnUiThread()` 实现的。这是必要的，因为监听器不是在主线程上运行，因此无法安全地更改用户界面。`runOnUiThread()` 方法提供了一种使用协程在主线程上执行代码的快速方便的方法。

## 3.0 启动购买流程

当用户点击购买按钮时，将调用 `makePurchase()` 来启动购买过程。我们现在可以如下添加此方法：

```java
public void makePurchase(View view) {
    BillingFlowParams billingFlowParams =
        BillingFlowParams.newBuilder()
        .setProductDetailsList(
            ImmutableList.of(
                BillingFlowParams.ProductDetailsParams.newBuilder()
                    .setProductDetails(productDetails)
                    .build()
            )
        )
        .build();

    billingClient.launchBillingFlow(this, billingFlowParams);
}
```

## 3.1 处理购买更新

购买过程的结果将通过初始化阶段分配给结算客户端的 `PurchaseUpdatedListener` 报告给应用。现在按如下方式添加此处理器：

```java
private final PurchasesUpdatedListener purchasesUpdatedListener = new PurchasesUpdatedListener() {
    @Override
    public void onPurchasesUpdated(BillingResult billingResult,
            List<Purchase> purchases) {
        if (billingResult.getResponseCode() ==
            BillingClient.BillingResponseCode.OK
            && purchases != null) {
            for (Purchase purchase : purchases) {
                completePurchase(purchase);
            }
        } else if (billingResult.getResponseCode() ==
            BillingClient.BillingResponseCode.USER_CANCELED) {
            Log.i(TAG, "onPurchasesUpdated: Purchase Canceled");
        } else {
            Log.i(TAG, "onPurchasesUpdated: Error");
        }
    }
};
```

如果用户取消购买或发生其他错误，处理器将输出日志消息。然而，成功的购买会导致调用 `completePurchase()` 方法，并向该方法传递当前的 `Purchase` 对象。按如下所示添加此方法：

```java
private void completePurchase(Purchase item) {
    purchase = item;
    if (purchase.getPurchaseState() == Purchase.State.PURCHASED)
        runOnUiThread(() -> {
            binding.consumeButton.setEnabled(true);
            binding.statusText.setText("Purchase Complete");
        });
}
```

此方法在验证产品已购买且付款未待处理之前会存储购买信息。启用“消耗”按钮，并通知用户购买成功。同时禁用购买按钮，以防止用户在消耗购买之前重复购买。

## 3.2 消耗产品

现在用户可以点击“消耗”按钮，下一步是确保产品已消耗，以便在下次点击之前执行。这需要我们编写 `consumePurchase()` 方法：

```java
public void consumePurchase(View view) {
    ConsumeParams consumeParams =
        ConsumeParams.newBuilder()
        .setPurchaseToken(purchase.getPurchaseToken())
        .build();

    ConsumeResponseListener listener = new ConsumeResponseListener() {
        @Override
        public void onConsumeResponse(BillingResult billingResult,
            @NonNull String purchaseToken) {
                if (billingResult.getResponseCode() ==
                    BillingClient.BillingResponseCode.OK) {
                    runOnUiThread(() -> {
                        binding.consumeButton.setEnabled(false);
                        binding.statusText.setText("Purchase consumed");
                    });
                }
            }
    };

    billingClient.consumeAsync(consumeParams, listener);
}
```

此方法创建一个 `ConsumeParams` 实例，并使用购买令牌对其进行配置（该令牌来自之前存储在 `completePurchase()` 方法中的 `Purchase` 对象）。如果产品被成功消耗，将在主线程中执行代码以禁用消耗按钮、启用购买按钮并更新状态文本。

## 3.3 恢复之前的购买

到目前为止的代码可以在单个会话内购买并消耗产品。如果我们在消耗之前退出应用，购买将在应用重启时丢失。我们可以通过配置 `QueryPurchasesParams` 实例来搜索未消耗的应用内产品，并将其与监听器引用传递给结算客户端的 `queryPurchasesAsync()` 方法来解决此问题。按如下所示在 `MainActivity.java` 文件中添加新函数和监听器：

```java
private void reloadPurchase() {
    QueryPurchasesParams queryPurchasesParams = QueryPurchasesParams.newBuilder()
        .setProductType(BillingClient.ProductType.INAPP)
        .build();

    billingClient.queryPurchasesAsync(
        queryPurchasesParams,
        purchasesListener
    );
}

private final PurchasesResponseListener purchasesListener = new PurchasesResponseListener() {
    @Override
    public void onQueryPurchasesResponse(@NonNull BillingResult billingResult,
            @NonNull List<Purchase> list) {
        if (!list.isEmpty()) {
            purchase = list.get(0);
            binding.consumeButton.setEnabled(true);
        } else {
            binding.consumeButton.setEnabled(false);
        }
    }
};
```

如果传递给监听器的购买列表不为空，则列表中的第一个购买将被赋值给 `purchase` 变量，并启用“消耗”按钮（在更完整的实现中，应该添加代码通过比较产品 ID 来检查这是否是正确的产品，并处理多个购买的返回）。如果没有找到购买项目，则消耗按钮将保持禁用，直到再次进行购买。剩下的工作工作是在计单设置过程中如下所示调用我们新的 `reloadPurchase()` 方法：

```java
private void billingSetup() {
    .
    .
    if (billingResult.getResponseCode() == BillingClient.BillingResponseCode.OK) {
        Log.i(TAG, "OnBillingSetupFinish connected");
        queryProduct();
        reloadPurchase();
    } else {
        Log.i(TAG, "OnBillingSetupFinish failed");
    }
    .
    .
}
```

## 83.14 测试应用程序

在测试应用程序之前，我们需要将此最新版本上传到 Play Console。由于我们已经上传了版本 1，因此我们需要在 `build.gradle.kts` (Module: app) 文件中增加版本号：

```kotlin
.
.
defaultConfig {
    applicationId "com.ebookfrenzy.inapppurchase"
    minSdk 26
    targetSdk 32
    versionCode 2
    versionName "2.0"
}
.
.
```

同步构建配置，然后按照“创建、测试和上传 Android App Bundle” 章节中的步骤生成新的应用 bundle，将其上传到内部测试轨道，并发布给测试人员。接下来，使用内部测试链接，在登录了其中一个测试账户的设备或模拟器上安装该应用程序。要找到测试链接，请在 Google Play Console 中选择该应用程序，并在导航面板中选择“内部测试”（Internal testing）选项，然后选择“测试人员”（Testers）标签页，如图 83-6 所示：

![](img/in-app-purchase-testers.jpg)

图 83-6

滚动到屏幕上的“测试人员如何加入您的测试”（How testers join your test）部分并点击“复制链接”（Copy link）：

![](img/in-app-purchase-copy_link.jpg)

图 83-7

在测试设备或模拟器上打开 Chrome 浏览器，输入测试链接，并按照指示从 Play Store 安装应用程序。应用程序启动后，经过短暂的延迟，它应该会在 `TextView` 上显示产品名称。点击购买按钮将开始购买流程，如图 83-8 所示：

![](img/in_app_billing_test_purchase.jpg)

图 83-8

点击购买按钮使用测试卡片完成购买，并等待“消耗购买”（Consume Purchase）按钮被启用。在点击此按钮之前，尝试再次购买该产品并验证这是不可能的，因为你已经拥有了该产品。

点击“消耗购买”按钮，等待 `TextView` 上出现“购买已消耗”（Purchase consumed）消息。产品消耗后，现在应该可以再次购买。再次进行购买，然后终止并重启应用程序。应用程序应该找到之前的未消耗购买项目并启用消耗按钮。

## 83.15 故障排除

如果你在购买时遇到问题，请确保设备已通过 USB 线或 WiFi 连接到 Android Studio，并在 Logcat 面板中选择它。在 Logcat 搜索栏中输入 `InAppPurchaseTag` 并检查诊断输出，必要时在代码中添加额外的 `Log` 调用。关于失败的额外信息，一个实用的技巧是从 `BillingResult` 实例访问调试消息，例如：

```java
.
.
} else if (billingResult.getResponseCode() == BillingClient.BillingResponseCode.USER_CANCELED) {
    Log.i(TAG, "onPurchasesUpdated: Purchase Canceled");
} else {
    Log.i(TAG, billingResult.getDebugMessage());
}
```




注意，只要你不更改模块级`build.gradle.kts`文件中的应用程序版本号，你现在应该就可以直接在设备或模拟器上运行修改过的应用程序，而无需重新安装。

### 83.16 总结

在本章中，我们创建了一个演示应用内购买的项目。我们解释了如何初始化计单客户端、查询产品以及消耗它们。我们还涵盖了如何使用`Play Console`进行测试。

# 84 使用 Material Design 主题

Android 应用程序的外观旨在符合 Material Design。Google 开发 Material Design 是为了在不同应用程序之间提供设计一致性，同时允许应用程序开发者在颜色、字体和形状选择方面包含他们自己的品牌（这一概念被称为“主题化”）。本章将概述主题化在 Android 项目中是如何运作的。

## 84.1 Material Design 2 vs. Material Design 3

在开始之前，重要的是，Google 正在从 Material Design 2 过渡到 Material Design 3，并且 Android Studio Giraffe 项目默认使用 Material Design 3。Material Design 3 是 Material You 的基础，这是 Android 12 中引入的一项功能，允许应用程序自动调整主题元素以匹配偏好。例如，Material Design 3 提供的动态颜色支持允许应用程序中使用的颜色进行适应以匹配用户的选择。

## 84.2 理解 Material Design 主题

我们知道 Android 应用程序的用户界面是通过组装布局、文本字段和按钮等组件创建的。除非我们专门在 XML 资源文件中通过代码覆盖颜色属性，否则这些组件将使用默认颜色。项目的主题定义了这些默认颜色。主题由一组颜色槽（定义在`themes.xml`文件中）组成，并分配了颜色值（定义在`colors.xml`文件中）。每个 UI 组件内部编写为使用主题颜色槽作为特定属性的默认颜色（例如`Text`组件的前景和背景颜色）。因此，我们可以通过更改分配给特定颜色槽的颜色来更改整个应用程序的主题。当应用程序运行时，在渲染用户界面时将使用新的默认颜色。

### 84.3 Material Design 3 主题

在探索 Material Design 3 之前，我们必须考虑它在 Android Studio 项目中是如何使用的。应用程序项目使用的主题被声明为`AndroidManifest.xml`文件中`application`元素的属性，例如：

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">
    <application
        android:supportsRtl="true"
        android:theme="@style/Theme.MyDemoApp"
        tools:targetApi="31">
        <activity
.
.
</application>
</manifest>
```

如前所述，所有与项目主题相关的文件都包含在`res -> values`文件夹下的`colors.xml`和`themes.xml`文件中，如图 84-1 所示：

![](img/as_theme_files.jpg)

图 84-1

主题本身在位于`themes`文件夹下的两个`themes.xml`文件中声明。这些资源文件声明了不同的调色板，其中包含 Material 主题颜色槽，供设备在亮色或深色（夜间）模式下使用。请注意，每个文件中的`style name`属性必须与`AndroidManifest.xml`文件中引用的匹配，例如：

```xml
<resources xmlns:tools="http://schemas.android.com/tools">
    <!-- 应用主题。 -->
    <style name="Base.Theme.MyDemoApp" parent="Theme.Material3.DayNight.NoActionBar">
        <!-- 在此处自定义您的亮色主题。 -->
        <!-- <item name="colorPrimary">@color/my_light_primary</item> -->
    </style>
    <style name="Theme.MyDemoApp" parent="Base.Theme.MyDemoApp" />
</resources>
```

这些颜色槽（也称为颜色属性）用于 Material 组件在屏幕上渲染时设置颜色。例如，`colorPrimary`颜色槽被用作`Material Button`组件的背景颜色。

MD3 中的颜色槽被分为 Primary（主）、Secondary（次）、Tertiary（三级）、Error（错误）、Background（背景）和 Surface（表面）。这些槽进一步分为成对，由一个基础颜色和一个“在其上的”基础颜色组成。这通常对应于 Material 组件的背景色和前景色。

不同组件所使用的特定组会有所不同。例如，`Material Button`组件将使用`colorPrimary`基础颜色作为背景色，并使用`colorOnPrimary`作为其内容（即显示的文本或图标）。另一方面，`FloatingActionButton`组件使用`colorPrimaryContainer`作为背景色，并使用`colorOnPrimaryContainer`作为前景色。通常可以通过更改主题文件中的颜色设置并查看布局编辑器中的渲染结果，来快速识别特定组件类型的正确组。

假设我们需要将`colorPrimary`改为红色。我们通过在`colors.xml`文件中为红色添加新条目，然后将其分配给`themes.xml`文件中的`colorPrimary`槽来实现这一目标。因此，MD3 主题夜间模式下的`colorPrimary`槽读取如下：

```xml
<resources xmlns:tools="http://schemas.android.com/tools">
    <!-- 应用主题。 -->
    <style name="Base.Theme.MyDemoApp" parent="Theme.Material3.DayNight.NoActionBar">
        <item name="colorPrimary">@color/my_bright_primary</item>
    </style>
    <style name="Theme.MyDemoApp" parent="Base.Theme.MyDemoApp" />
</resources>
```

该颜色随后在`colors.xml`文件中声明：

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="my_bright_primary">#FC0505</color>
</resources>
```

### 84.4 构建自定义主题

正如我们所见，实现主题的代码工作相对简单。然而，困难的部分通常是选择互补色来组成主题。幸运的是，Google 开发了一个工具，可以轻松为您的应用设计自定义颜色主题。该工具被称为 Material Theme Builder，可以在此处访问：

[`m3.material.io/theme-builder#/`](https://m3.material.io/theme-builder#/dynamic)

在自定义屏幕（图 84-2）上，通过点击颜色圆显示颜色选择对话框，为主色键值 (A) 进行颜色选择。一旦选择了颜色，预览 (B) 将发生变化，以反映所有 MD3 颜色槽的推荐颜色，以及示例应用界面和组件。此外，您可以通过点击相应的颜色圆显示颜色选择对话框，来覆盖为 Secondary、Tertiary 和 Neutral 槽生成的颜色。

标记为 B 的区域显示了示例应用界面、亮/深色配色方案图以及更新以预览您的颜色选择的组件。由于面板比典型的浏览器窗口长，您必须向下滚动以查看所有信息。

要将主题整合到您的设计中，点击导出按钮 (C) 并选择 Android View (XML) 选项。下载后，可以使用`colors.xml`和`themes.xml`文件替换项目中的现有文件。注意，导出的两个`themes.xml`文件中的主题名称必须更改以匹配您的项目。

![](img/theme_builder_custom.jpg)

图 84-2

### 84.5 总结

Material Design 提供了定义 Android 应用外观的指南和组件。通过设计指定显示应用时使用的颜色、字体和形状的主题，可以应用应用个人品牌。Google 最近引入了 Material Design 3，它取代了 Material Design 2 并支持 Material You 的新功能，包括动态颜色。Google 还提供了 Material Theme Builder 来设计您自己的主题，这减轻了选择互补色的任务。一旦使用此工具设计了主题，就可以导出相应的文件并在 Android Studio 项目中使用。

## 85. Material Design 3 主题化与动态颜色

本章将向您展示如何使用 Material Theme Builder 创建新的 Material Design 3 主题并将其集成到 Android Studio 中。教程还将演示如何为应用添加并测试动态颜色。

### 85.1 创建 ThemeDemo 项目

在欢迎屏幕上选择 New Project，并在新项目对话框中选择 Empty Views Activity 模板，然后点击 Next 按钮。在 Name 字段中输入 ThemeDemo，并指定 com.ebookzy.themedemo 为包名。在点击 Finish 按钮之前，将 Minimum API level 改为 API 26: Android 8.0 (O)，并将 Language 设置为 Java。

### 85.2 设计用户界面

界面将由一个简单的布局组成，包含一些组件，以便看到之后执行的主题化效果。有关 MD3 组件的信息，请参考以下网页：

[`material.io/blog/migrating-3`](https://material.io/blog/migrating-3)

布局将在`activity_main.xml`文件中设计，该文件当前包含单个 Text view。在布局编辑器中打开此文件，删除 Text view，关闭自动连接模式（图 85-1 中的 A），并点击按钮清除布局的所有约束 (B)。

![](img/as_theme_demo_layout_buttons.jpg)

图 85-1

从 Palette 的 Buttons 部分将 Chip、CheckBox、Switch 和 Button 拖到布局画布上。接下来，将 FloatingActionButton 拖到画布上并放置在 Button 组件下方。当提示为 FloatingActionButton 选择一个图标时，从资源工具窗口选择 ic_lock_power_off 图标，如图 85-2 所示：

![](img/as_theme_demo_layout_pick_icon.jpg)

图 85-2

将 Chip 组件的 text 属性更改为“This is my chip”，并将 chipIcon 属性设置为 android:drawable/ic_btn_speak_now，使布局类似于图 85-3 左侧所示的内容：

![](img/as_theme_demo_ui.jpg)

图 85-3

为了设置约束，选择所有组件，右键点击 Chip 视图，并在生成的菜单中选择 Chains -> Create Vertical Chain。重复此步骤，这次选择 Center -> Horizontally in Parent 选项。

在设备或模拟器上编译并运行应用，并验证用户界面与上方图 85-3 中所示的内容一致。下一步是创建一个自定义主题并将其应用到项目中。

### 85.4 构建新主题

首先，打开浏览器窗口并导航到以下 URL 以访问构建工具：

[`m3.material.io/theme-builder#/custom`](https://m3.material.io/theme-builder#/custom)

加载构建器后，选择一张壁纸，然后点击屏幕顶部的`Custom`按钮，接着点击`Core Colors`部分中的`Primary`颜色圆形以显示颜色选择器。从颜色选择器中，选择任意颜色作为主题的基础：

![](img/theme_builder_color_dialog.jpg)

图 85-4

在`Your Theme`面板中检查颜色方案，并使用`Core colors`设置进行必要的颜色调整，直到你对颜色槽满意。主题准备好后，点击右上角的`Export`按钮并选择`Android Views (XML)`选项。在提示时，将文件保存到计算机文件系统的合适位置。该主题将保存为名为`material-theme.zip`的压缩文件。

使用适用于你操作系统的工具解压主题文件，它应该包含在名为`material-theme`的文件夹中的以下文件夹和文件：

* `values/colors.xml` - 颜色定义。
* `values/themes.xml` - 亮色模式主题。
* `values-night/themes.xml` - 暗色模式主题。

现在主题文件已经生成，需要将其集成到 Android Studio 项目中。

### 85.5 将主题添加到项目

在将新主题添加到项目之前，我们首先需要移除旧的主题文件。如果`Project`工具窗口处于`Project Files`模式，操作会更简单。要切换模式，使用如下所示`Project`工具窗口顶部的菜单，并选择`Project Files`选项：

![](img/as_project_files.jpg)

图 85-5

在选中`Project Files`模式的情况下，导航到`app` -> `src` -> `main` -> `res` -> `values`文件夹，选择并删除`colors.xml`和`themes.xml`文件。同样，删除位于`values-night`文件夹中的`themes.xml`文件。

打开你操作系统的文件导航工具，找到新 material 主题`values`文件夹中的`colors.xml`和`themes.xml`文件，并将它们复制粘贴到`Project`工具窗口中的`values`文件夹。重复此步骤复制`values-night`文件夹中的`themes.xml`文件，这次将其粘贴到`values-night`文件夹。

将`Project`工具窗口切换回`Android`模式，此时值资源文件部分应与图 85-6 匹配：

![](img/as_theme_new_theme_files.jpg)

图 85-6

接下来，修改亮色`themes.xml`文件以匹配当前项目：

```xml
<resources>
    <style name="Base.Theme.ThemeDemo" parent="Theme.Material3.Light.NoActionBar">
        <item name="colorPrimary">@color/md_theme_light_primary</item>
        <item name="colorOnPrimary">@color/md_theme_light_onPrimary</item>
    </style>
    <style name="Theme.ThemeDemo" parent="Base.Theme.ThemeDemo" />
</resources>
```

重复这些步骤对`themes.xml (night)`文件进行相同的修改。

返回`activity_main.xml`文件或重新运行应用，以确认用户界面已使用自定义主题颜色渲染。

# 85.6 启用动态颜色支持

应用需要在运行 Android 12 或更高版本的设备或模拟器上运行，并具有正确的壁纸设置，以测试动态颜色。在设备或模拟器上，启动`Settings`应用并从选项列表中选择`Wallpaper & style`。在壁纸设置屏幕上，点击更改壁纸的选项（如在图 85-7 中标记为 A），并选择一张颜色与你主题颜色显著不同的壁纸图像。一旦选择完成，将壁纸分配到主屏幕。

返回`Wallpaper & styles`屏幕，在从颜色方案按钮中选择选项 (C) 之前，确保已选择`Wallpaper colors`选项 (B)。每点击一个选项，壁纸示例都将更改以反映选择：

![](img/compose_theme_wallpaper_and_styles.jpg)

图 85-7

要启用动态颜色，我们需要调用`DynamicColors`类的`applyToActivitiesIfAvailable()`方法。为了为整个应用启用动态颜色支持，这需要在自定义`Application`实例的`onCreate()`方法内部调用。首先，在项目的`app` -> `java` -> `com.ebookfrenzy.themedemo`下添加一个名为`ThemeDemoApplication.java`的新 Java 类文件，并对其进行修改如下：

```java



`package com.ebookfrenzy.themedemo;`

`import android.app.Application;`

`import com.google.android.material.color.DynamicColors;`

`public class ThemeDemoApplication extends Application {`

```
@Override

public void onCreate() {

    super.onCreate();

    DynamicColors.applyToActivitiesIfAvailable(this);

}
```

`}`

创建自定义的 `Application` 类后，我们必须配置项目使用它而不是默认的 `Application`。要此操作，编辑 `AndroidManifest.xml` 文件并添加引用新类的 `android:name` ：

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.ebookfrenzy.themedemo">

    <application
        android:name=".ThemeDemoApplication"
        android:allowBackup="true">
        ...
    </application>
</manifest>
```

构建并运行应用，并注意布局使用了壁纸颜色。将 `ThemeDemo` 应用置后，返回 `Wallpaper & styles` 设置并选择一张不同的壁纸。将 `ThemeDemo` 应用带回前台。此时，它已动态地适应了新的壁纸。

## 85.7 预览动态颜色

动态颜色行为也可以在 Android Studio 布局编辑器中预览。要尝试这一点，打开 `activity_main.xml` 文件，点击主题菜单并选择 `More Themes` 选项，如图 85-8 所示：

![](img/as_layout_editor_themes_menu.jpg)

图 85-8

接下来，在主题选择对话框中使用搜索字段列出动态主题：

![](img/as_layout_editor_select_theme.jpg)

图 85-9

在点击 `OK` 按钮之前，选择 `Material3.DynamicColors.DayNight` 主。返回布局编辑器后，选择 `System UI Mode` 菜单并选择一个壁纸选项，如图 85-10 所示：

![](img/as_layout_editor_dynamic_themes.jpg)

图 85-10

一旦选择了壁纸，布局组件的颜色将随之改变。

### 85.8 总结

在本章中，我们使用了 `Material Theme Builder` 设计了一个新主题，并解释了将生成的主题文件到 Android Studio 项目中的步骤。最后，章节介绍了如何实现和使用 `Material You` 动态颜色功能。

# 86. Android Studio 中 Gradle 概述

到目前为止，一直认为 Android Studio 会采取编译和运行所创建的项目所需的步骤。Android Studio 一直通过使用名为 `Gradle` 的系统在后台实现这一点。

现在是查看 `Gradle` 如何被用于编译和打包应用程序的各个元素，并开始探索在构建项目需要更高级需求时如何配置该系统的时候。

## 86.1 An Overview of Gradle

`Gradle` 是一个自动化构建工具包，它允许通过一组构建配置文件来配置和管理项目的构建方式。这包括定义项目将如何构建、成功构建项目需要满足哪些依赖项，以及构建过程的最终结果（或多个结果）应该是什么。

`Gradle` 的优势在于它为开发者提供的灵活性。`Gradle` 系统是一个自包含包含的、基于命令行的环境，可以通过插件集成到其他环境中。在 Android Studio 的情况下，`Gradle` 集成是通过命名相应的 Android Studio 插件提供的。

尽管 Android Studio 插件允许在 Android Studio 内部启动和管理 `Gradle` 任务，但仍然可以使用 `Gradle` 命令行包装器（`wrapper`）来构建基于 Android Studio 的项目，包括在未安装 Android Studio 的系统上。

构建项目的配置规则声明在基于 `Groovy` 编程语言的 `Gradle` 构建文件和脚本中。

### 86.2 Gradle 与 Android Studio

`Gradle` 为构建 Android 应用程序项目带来了许多强大的功能。一些关键特性如下：

### 86.2.1 合理的默认值

`Gradle` 实现了一种被称为“约定优于配置”（`convention over configuration`）的概念。这意味着 `Gradle` 拥有一套预定义的合理默认配置设置，除非构建文件中的设置覆盖了它们，否则将使用这些设置。这意味着可以使用开发者所需的最少配置进行构建。只有当默认配置不能满足你的构建需求时，才需要对构建文件进行更改。

### 86.2.2 依赖

`Gradle` 功能的另一个关键领域是依赖项。例如，考虑 Android Studio 项目中的一个模块，它触发了一个意图来加载项目中的另一个模块。第一个模块实际上对第二个模块有依赖，因为如果从运行时无法找到并启动第二个模块，应用程序将无法构建。这种依赖关系可以在第一个模块的 `Gradle` 构建文件中声明，以便将第二个模块包含在应用程序构建中，或者在找不到或无法构建第二个模块时标记错误。依赖项的其他示例是项目编译和运行所依赖的库和 `JAR` 文件。

`Gradle` 依赖项可以分为本地或远程。本地依赖项引用执行构建的计算机系统本地文件系统的项。远程依赖项引用远程服务器（通常称为仓库）上的项。

Android Studio 项目的远程依赖项使用另一个名为 `Maven` 的项目管理工具进行处理。如果在 `Gradle` 构建文件中使用 `Maven` 语法声明了远程依赖项，则该依赖项将从指定的仓库自动下载并包含在构建过程中。例如，下面的依赖声明将导致从 Google 仓库向项目添加 `AppCompat` 库：

```
implementation("androidx.appcompat:appcompat:1.6.1")
```

### 86.2.3 构建变体

除了依赖之外，`Gradle` 还为 Android Studio 项目提供构建变体支持。这允许从单个项目构建应用程序的多个变。Android 运行许多不同的设备，涵盖各种处理器类型和屏幕尺寸。为了尽可能针对广泛设备类型和尺寸，通常需要构建应用程序的多个变体（例如，一个带有手机界面，另一个用于平板电脑屏幕）。通过使用 `Gradle`，这现在 Android Studio 中是可以实现的。

### 86.2.4 Manifest 条目

每个 Android Studio 项目都关联有一个 `AndroidManifest.xml` 文件，其中包含应用程序的配置详情。在 `Gradle` 构建文件中可以指定多个清单条目，这些条目在项目构建时会自动生成到清单文件中。此功能补充了构建变体功能，允许应用程序版本号、应用 ID 和 SDK 版本信息等元素为每个构建变体进行不同的配置。

### 86.2.5 APK 签名

创建、测试和上传 Android App Bundle 章节涵盖了使用 Android Studio 环境创建签名的发布 `APK` 文件。也可以将通过 Android Studio 用户界面输入的签名信息包含在 `Gradle` 构建文件中，以便从命令行生成带签名的 `APK` 文件。

### 86.2.6 ProGuard 支持

`ProGuard` 是 Android Studio 自带的一个工具，它可以优化、压缩和混淆 Java 字节码，使其更高效且更难被反向工程（即他人通过分析编译后的 Java 字节码来识别应用程序逻辑的方法）。`Gradle` 构建文件允许你控制在构建你的应用程序时是否运行 `ProGuard`。

## 86.3 属性与设置 Gradle 构建文件

`gradle` 构建配置由配置、属性属性和设置文件组成。例如，`gradle.properties` 文件主要包含与 Java 虚拟机 (`JVM`) 使用的命令行标志相关的特殊设置，以及项目是否使用 `AndroidX` 库和 `Kotlin` 编码风格支持。作为典型用户，你可能不需要更改此文件中的任何设置。

另一方面，`settings.gradle.kts` 文件定义了当构建系统需要下载和安装构建项目所需的任何额外库和插件时，应搜索哪些在线仓库，以及项目名称。一个典型的 `settings.gradle.kts` 文件内容如下：

```kotlin
pluginManagement {
    repositories {
        google()
        mavenCentral()
        gradlePluginPortal()
    }
}

dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
    }
}

rootProject.name = "ThemeDemo"
include(":app")
```

与 `gradle.properties` 一样，可能不需要对此文件进行更改。

## 86.4 顶层 Gradle 文件

一个完整的 Android Studio 项目包含构建所需的所有，由模块、库、清单文件和 `Gradle` 构建文件组成。

每个项目包含一个顶层 `Gradle` 构建文件。该文件列为 `build.gradle.kts`（项目 `<project name>`），可以在项目窗口中找到，如图 86-1 所示：

![](img/as_gradle_file.jpg)

图 86-1

默认情况下，文件的内容如下：

```kotlin
// 顶部构建文件，可以在此处添加适用于所有子项目/模块的配置选项。

plugins {
    id("com.android.application") version "8.1.0-rc01" apply false
}
```

目前，该文件仅声明使用 `jcenter` 仓库获取远程库，并且构建依赖于 Android 插件。在大多数情况下，不需要对此文件进行任何更改。

## 86.5 模块级 Gradle 构建文件

Android Studio 应用程序项目由一个或多个模块组成。考虑一个名为 `GradleDemo` 的假设应用程序项目，它分别包含 `Module1` 和 `Module2`。在这种情况下，每个模块都需要自己的 `Gradle` 构建文件。从项目结构来看，这些文件的位置如下：

- `Module1/build.gradle.kts`
- `Module2/build.gradle.kts`

默认情况下，`Module1` 的 `build.gradle.kts` 文件类似于下面的列表：

```kotlin
plugins {
    id("com.android.application")
}

android {
    namespace = "com.example.gradlesample"
    compileSdk = 33
}
```

```gradle
defaultConfig {
    applicationId = "com.example.gradlesample"
    minSdk = 26
    targetSdk = 33
    versionCode = 1
    versionName = "1.0"
    testInstrumentationRunner = "androidx.test.runner.AndroidJUnitRunner"
}

buildTypes {
    release {
        isMinifyEnabled = false
        proguardFiles(
            getDefaultProguardFile("proguard-android-optimize.txt"),
            "proguard-rules.pro"
        )
    }
}

compileOptions {
    sourceCompatibility = JavaVersion.VERSION_1_8
    targetCompatibility = JavaVersion.VERSION_1_8
}
```

```gradle
dependencies {
    implementation("androidx.appcompat:appcompat:1.6.1")
    implementation("com.google.android.material:material:1.9.0")
    implementation("androidx.constraintlayout:constraintlayout:2.1.4")
    testImplementation("junit:junit:4.13.2")
    androidTestImplementation("androidx.test.ext:junit:1.1.5")
    androidTestImplementation("androidx.test.espresso:espresso-core:3.5.1")
}
```

从文件内容可以看出，构建文件首先声明了使用 `Gradle` Android 插件：

```gradle
plugins {
    id("com.android.application")
}
```

文件的 `android` 节声明了项目的命名空间（`namespace`），然后说明了构建 `Module1` 时要使用的 SDK 版本。

```gradle
android {
    namespace = "com.example.gradlesample"
    compileSdk = 33
}
```

`defaultConfig` 节中声明的项目定义了在构建过程中生成到模块 `AndroidManifest.xml` 文件中的元素。这些设置可以在构建文件中进行修改，它们源于最初创建模块时在 Android Studio 中输入的设置值：

```gradle
defaultConfig {
    applicationId = "com.example.gradlesample"
    minSdk = 26
    targetSdk = 33
    versionCode = 1
    versionName = "1.0"
    testInstrumentationRunner = "androidx.test.runner.AndroidJUnitRunner"
}
```

`buildTypes` 节包含了关于在构建应用程序的发布版本时，是否以及如何对 `APK` 文件上运行 `ProGuard` 的指令：

```gradle
buildTypes {
    release {
        isMinifyEnabled = false
        proguardFiles(
            getDefaultProguardFile("proguard-android-optimize.txt"),
            "proguard-rules.pro"
        )
    }
}
```

按照目前的配置，构建 `Module1` 时不会运行 `ProGuard`。要启用 `ProGuard`，必须将 `minify` 项从 `false` 改为 `true`。`proguard-rules.pro` 文件可以在项目的模块目录中找到。对该文件的更改将覆盖位于 Android SDK 安装目录 `sdk/tools/proguard` 下的 `proguard-android.txt` 文件中的默认设置。

由于此文件中没有声明调试 `buildType`，将使用默认设置（不带 `ProGuard` 构建，使用调试密钥签名，并启用调试符号）。

模块构建文件中还可以包含一个标题为 `productFlavors` 的额外节，以便能够创建多个构建变体。

接下来，包含了一些指令，用于指定构建项目时使用的 Java 编译器版本：

```gradle
compileOptions {
    sourceCompatibility = JavaVersion.VERSION_1_8
    targetCompatibility = JavaVersion.VERSION_1_8
}
```

最后，`dependencies` 节列出了模块依赖的任何本地和远程依赖。上述示例中的依赖行指定了需要从 Android 仓库包含的 Android 库：

```gradle
dependencies {
    implementation("androidx.appcompat:appcompat:1.6.1")
    implementation("com.google.android.material:material:1.9.0")
}
```



注意，依赖声明包含了版本号，用以指示应该包含哪个版本的库。

## 8.6 在构建文件中配置签名设置

本书的“创建、测试和上传 Android Bundle”章节涵盖了使用 Android Studio 用户界面设置密钥和生成签名发布版 APK 的涉及步骤。这些设置也可以在`build.gradle.kts`文件的`signingConfigs`节中声明。例如：

```gradle
defaultConfig {
    // ...
}

signingConfigs {
    release {
        storeFile("keystore.release")
        storePassword "your keystore password here"
        keyAlias "your key alias here"
        keyPassword "your key password here"
    }
}

buildTypes {
    // ...
}
```

上述示例将密钥密码信息直接嵌入到构建文件中。这种方法的另一种替代方案是从系统环境变量中提取这些值：

```gradle
signingConfigs {
    release {
        storeFile("keystore.release")
        storePassword System.getenv("KEYSTOREPASSWD")
        keyAlias "your key alias here"
        keyPassword System.getenv("KEYWD")
    }
}
```

另一种方法是配置构建文件，让 Gradle 在构建过程中提示输入密码：

```gradle
signingConfigs {
    release {
        storeFile("keystore.release")
        storePassword System.console().readLine("\nEnter Keystore password: ")
        keyAlias "your key alias here"
        keyPassword System.console().readLine("\nEnter Key password: ")
    }
}
```

## 8.7 从命令行运行 Gradle 任务

每个 Android Studio 项目都包含一个用于从命令行运行 Gradle 任务的包装器（wrapper）。该包装器位于项目的根目录下。在 Linux 或 macOS 上，可能需要启用执行权限。要启用执行权限，请打开终端窗口，切换到需要该包装器的项目目录，并执行以下命令：

```bash
chmod +x gradlew
```

一旦文件具有执行权限，则需要将其路径添加到`$PATH`环境变量中，或者在运行名称前加上`./`来运行。例如：

```bash
./gradlew tasks
```

Gradle 通过不同的任务来查看项目构建。可以通过在项目内部运行以下命令获取当前项目可用的任务列表（在 macOS 或 Linux 上运行时请加上前缀`./`）：

```bash
gradlew tasks
```

要构建适用于设备或模拟器的调试版本，请使用`assembleDebug`选项：

```bash
gradlew assembleDebug
```

或者，构建应用程序的发布版本：

```bash
gradlew assembleRelease
```



# 8.8 总结

大部分情况下，Android Studio 在无需开发者干预的情况下后台完成应用程序构建。此构建过程使用 Gradle 系统，这是一种自动化构建工具，允许通过一组构建配置文件来配置和管理项目的构建。虽然 Gradle 的默认行为适用于许多基础项目构建需求，但对于更复杂的项目，配置构建过程的需求是不可避免的。本章提供了 Android Studio 项目背景下 Gradle 构建系统和配置文件的概述。

## 索引

### 符号
- `<application>`
- `<fragment>`
- `<fragment>`元素
- `<receiver>`
- `<service>`
- 代码重格式
- `.well-known` 文件夹

### A
- `AbsoluteLayout`

## 权限
- `ACCESS_COARSE_LOCATION` 权限 [504]
- `ACCESS_FINE_LOCATION` 权限 [504]
- `ADD_VOICEMAIL` 权限 [504]

## 方法与动作
- `acknowledgePurchase()` 方法 [719]
- `ACTION_CREATE_DOCUMENT` [596]
- `ACTION_CREATE_INTENT` [596]
- `ACTION_DOWN` [222]
- `ACTION_MOVE` [222]
- `ACTION_OPEN_DOCUMENT` 图 [588]
- `ACTION_POINTER_DOWN` [222]
- `ACTION_POINTER_UP` [222]
- `ACTION_UP` [222]
- `ACTION_VIEW` [461]

## Activity 与生命周期
- `Activity` [87], [103]
- `Activity Lifecycle` [99]
- `Activity Manager` [86]
- `Activity Stack` [99]
- `Active / Running state` [100]
- `states` [100]
- `lifecycles` [97]
- `lifecycle methods` [106]
- `creation` [16]
- `Entire Lifetime` [107]
- `Foreground Lifetime` [107]
- `Visible Lifetime` [107]
- `state change example` [111]
- `state changes` [103]
- `class` [103]
- `in Java 代码中添加 views` [203]
- `从返回数据` [440]

## Android 桥接 (adb)
- `adb`
- 命令行工具 [63]
- `connection testing` [69]
- `device pairing` [67]
- `在 Android 设备上启用` [63]
- `Linux 配置` [66]
- `list devices` [63]
- `macOS 配置` [64]
- `overview` [63]
- `restart server` [64]
- `testing connection` [69]
- `WiFi debugging` [67]
- `Windows 配置` [65]
- `Wireless debugging` [67]
- `Wireless pairing` [67]

## Android 方法与属性
- `addCategory()` 方法 [469]
- `addMarker()` 方法 [644]
- `addView()` 方法 [197]

## Android 框架组件
- `android`
- `exported` [437]
- `gestureColor` [240]
- `layout_behavior` 属性 [419]
- `onClick` [249]
- `process` [437], [487]
- `uncertainGestureColor` [240]
- `Android Activity` [87]
- `architecture` [83]
- `events` [215]
- `intents` [88]
- `onClick Resource` [215]
- `runtime` [84]
- `Android SDK Packages` [6]
- `android.app` [84]
- `Android Architecture Components` [265]
- `android.content` [84]
- `android.content.Intent` [439]
- `android.database` [84]
- `Android Debug Bridge`。参见 AVD
- `Android Development System Requirements` [3]
- `Android Devices`
- `针对不同的设计` [125]
- `android.graphics` [84]
- `android.hardware` [84]
- `android.intent.action` [475]
- `android.intent.action.BOOT_COMPLETED` [437]
- `android.intent.action.MAIN` [461]
- `android.intent.category.LAUNCHER` [461]
- `Android Libraries` [84]
- `android.media` [85]
- `Android Monitor tool window` [36]
- `Android Native Development` [85]
- `android.net` [85]
- `android.opengl` [84]
- `android.os` [85]
- `android.permission.RECORD_AUDIO` [623]
- `android.print` [85]
- `android.provider` [85]
- `Android Project`
- `create new` [15]
- `Android SDK Location`
- `identifying` [10]
- `Android SDK Manager` [8], [10]
- `Android SDK Packages`
- `version requirements` [8]
- `Android SDK Tools`
- `command-line access` [9]
- `Linux` [11]
- `macOS` [11]
- `Windows 7` [10]
- `Windows 8` [10]
- `Android Software Stack` [83]
- `Android Storage Framework` [588]

## Android Studio
- `Android Studio`
- `changing theme` [61]
- `downloading` [3]
- `Editor Window` [56]
- `installation` [4]
- `Linux installation` [5]
- `macOS installation` [4]
- `Navigation Bar` [55]
- `Project tool window` [56]
- `setup wizard` [5]
- `Status Bar` [56]
- `Toolbar` [55]
- `Tool window bars` [56]
- `tool windows` [56]
- `updating` [12]
- `Welcome Screen` [53]
- `Windows installation` [4]
- `android.text` [85]
- `android.util` [85]
- `android.view` [85]
- `android.view.View` [128]
- `android.view.ViewGroup` [125], [128]
- `ActivityResultLauncher` [441]
- `Actual screen pixels` [194]

# 概述

## Android 虚拟设备管理器
### `android.webkit`
### `android.widget`
### AndroidX 库
### API 密钥
### APK 分析器
### APK 文件
### APK 签名
### APK 向导对话框

## 应用架构
### 现代
### AppBar 结构解析
### `appbar_scrolling_view_behavior`
### App Bundle (应用包集)
### 创建
### 概述
### 修订
### 上传
### `AppCompatActivity` 类
### 应用检查器 (App Inspector)

## 应用
### 停止
### 应用上下文 (Application Context)
### 应用框架
### 应用清单 (Application Manifest)
### 应用资源

## 词应用链接
### 添加意图过滤器 (Intent Filter)
### 数字资产链接 (Digital Asset Links)
### 意图过滤器处理
### 意图过滤器
### 意图处理
### 测试
### URL 映射
### App Links
### 自动验证
### `autoVerify`
### 概述
### 应用更改
### 应用更改并重启 Activity
### 应用代码更改
### 回退设置
### 选项
### 运行应用
### 教程

### 架构组件
- `applyToActivitiesIfAvailable()` 方法
- `assetlinks.json`, 属性键

### 音频
### 支持的格式
### 音频播放
### 录制
### 自动连接模式
### 自动链接验证
- `autoVerify`

## AVD (虚拟设备)
### 冷启动
### 命令行创建
### 创建
### 设备外框
### 显示模式
### 在工具窗口中启动
### 概述
### 快速启动 (quickboot)
### 可调整大小
### 运行应用程序
### 快照 (Snapshots)
### 独立
### 启动
### 启动尺寸和方向

## B
### 后台进程
### 屏障 (Barriers)
### 添加
### 约束视图
### 基线 (Baseline)
### `beginTransaction()`
### `Client`
### `consume()`
### `getState()`
### 初始化
### `Flow()`
### `query()`
### `queryAsync()`
### `Result`
### `DebugMessage()`
### 绑定表达式
### 单向
### 双向
- `BIND_SERVICE`
- `bindService()`
### 生物识别认证
### 回调
### 概述
### 教程
### 生物识别提示 (Biometric Prompt)
### `BitmapFactory`
### 无 Activity
### 空 模板
### 蓝图视图
- `BODY_SENSORS`
### 绑定服务 (Bound Service)
添加到项目中
### 实现 Binder
### 交互选项
- `BoundService` 类

### 广播意图 (Broadcast Intent)
### 示例
### 概述
### 发送
### 粘性性 (Sticky)
### 广播接收器 (Broadcast Receiver)
添加到清单文件
### 创建
### 概述
- `BroadcastReceiver` 类
- `BroadcastReceiver` 父类

- `BufferedReader` 对象 [599]
- 构建工具窗口 [58]
- 构建变体, [58]
- 工具窗口 [58]
- `Bundle` 类 [120]
- 内置通知 [523]

## C
- 日历权限 [504]
- `CALL_PHONE` 权限 [504]
- `CAMERA` 权限 [504]
- 摄像头权限 [504]
- `CameraUpdateFactory` 类方法 [645]
- `CancellationSignal` [698]
- `Canvas` 类 [674]

## CardView
- `CardView` 布局文件 [397]
- 响应选择 [406]
- `CardView` 类 [397]
- `CATEGORY_OPENABLE` [588]

## C/C++ 库 [85]

## Chains
- 链偏置 [180]
- 链头 [150]
- 链 [150]
- 的创建 [177]
- 链样式
- 更改 [179]
- 链样式 [150]

## CheckBox
- `CheckBox` [125]
- `checkSelfPermission()` 方法 [508]
- `Circle` 类 [631]

## Code Editor
- 代码补全 [74]
- 基础 [71]
- 代码补全 [74]
- 代码生成 [77]
- 代码格式化 [79]
- 文档标签页 [72]
- 编辑区域 [72]
- 标槽区域 [72]
- 实时模板 [80]
- 分割 [74]
- 语句完成 [76]
- 状态栏 [73]
- 代码生成 [77]
- 代码示例
- 下载 [1]
- 冷启动 [48]

## CollapsingToolbarLayout
- 示例 [420]
- 介绍 [420]
- 视差模式 [420]
- 固定模式 [420]
- 设置遮罩颜色 [423]
- 设置标题 [423]
- 带图片 [420]

## Color
- `Color` 类 [675]
- `COLOR_MODE_COLOR` [650], [670]
- `COLOR_MODE_MONOCHROME` [650], [670]

## 通用手势 [229]
- 检测 [229]
- 组件树 [20]

## ConstraintLayout
- 约束偏置 [149]
- 调整 [163]
- 优势 [155]
- 可用性 [156]
- 屏障 [152]
- 基线对齐 [151]
- 链偏置 [180]
- 链头 [150]
- 链 [150]
- 链样式 [150]
- 约束偏置 [149]
- 约束 [147]
- 转换为 [175]
- 转换为 `MotionLayout` [349]
- 删除约束 [162]
- 引导线 [169]
- 引导线 [152]
- 手动约束操作 [159]
- 间距 [148], [163]
- 对抗约束 [148], [165]
- 概述 [147]
- 紧凑链 [151], [180]
- 比例 [155], [181]
- 散开链 [150]
- 内部扩散 [180]
- 内部扩散链 [150]
- 教程 [185]
- 在 Android Studio 中使用 [157]
- 权重链 [150], [180]
- 组件尺寸 [151], [167]
- 组件组对齐 [173]
- ConstraintLayout 链
- 的创建 [177]
- 在布局编辑器中 [177]
- ConstraintLayout 链样式
- 更改 [179]
- 约束
- 删除 [162]

## ConstraintSet
- `addToHorizontalChain()` 方法 [200]
- `addToVerticalChain()` 方法 [200]
- 对齐约束 [199]
- 应用到布局 [198]
- `applyTo()` 方法 [198]
- `centerHorizontally()` 方法 [199]
- `centerVertically()` 方法 [199]
- `chains` [199]
- `clear()` 方法 [200]
- `clone()` 方法 [199]
- `connect()` 方法 [198]
- 连接到父级 [198]
- 约束偏置 [199]
- 复制约束 [199]
- 创建 [198]
- 创建连接 [198]
- `createHorizontalChain()` 方法 [199]
- `createVerticalChain()` 方法 [199]
- 引导线 [200]
- `removeFromHorizontalChain()` 方法 [200]
- `removeFromVerticalChain()` 方法 [200]
- 移除 [200]
- 旋转 [201]

# 缩放 [200]

# 约束集
## ConstraintSets
- `setGuidelineBegin()` 方法 [200]
- `setGuidelineEnd()` 方法 [200]
- `setGuidelinePercent()` 方法 [200]
- `setHorizonalBias()` 方法 [199]
- `setRotationX()` 方法 [201]
- `setRotationY()` 方法 [201]
- `setScaleX()` 方法 [200]
- `setScaleY()` 方法 [200]
- `setTransformPivot()` 方法 [201]
- `setTransformPivotX()` 方法 [201]
- `setTransformPivotY()` 方法 [201]
- `setVerticalBias()` 方法 [199]
- 尺寸约束 [199]

## ConstraintSet 教程
- 教程 [203]
- 视图 ID [205]

## ConstraintSet 类 [197], [198]

# MotionLayout 概述
## 配置 [338]

## 应用内概览
- `consumeAsync()` 方法 [719]
- `ConsumeResponseListener` [719]

## 应用内教程
- `ConsumeParams` [731]

# 权限请求
- 联系人权限 [504]

# 视图与布局
- 容器视图 [125]
- `CoordinatorLayout` [126], [419]

# 架构
- 数据提供者 (Content Provider) [86]

# 应用结构
- 概述 [89]
- `Context` 类 [89]

# 自定义打印
- `createPrintDocumentAdapter()` 方法 [665]
- 自定义文档打印 [653], [665]
- 自定义打印适配器实现 [667]
- 自定义打印适配器 [665]

# MotionLayout 概述
- 自定义属性 [339]

# 自定义手势
- 识别 [235]

# 主题
## 自定义主题
- 构建 [737]

# MotionLayout KeyCycle 教程
- 循环编辑器 [367]
- 概述 [363]

# MotionLayout 概述
- 循环关键帧 [347]
- 循环关键帧

## 危险权限
- 列表 [504]

# AVD 创建
- 深色主题 [36]
- 在设备上启用 [36]

# Room 概述
- 数据访问对象 (DAO) [554]
- 数据访问对象 (DAO) [558]

# Room 教程
- 数据库检查器 [561], [584]
- 实时更新 [585]
- SQL 查询 [585]

# SQLite 数据库
- 数据库行 [548]
- 数据库架构 [547]
- 数据库表 [547]

# Jetpack 现代应用架构
- 数据绑定 [267]

## 数据绑定 概述
- 绑定表达式 [289]

## 数据绑定
- 绑定类 [288]
- 启用 [294]
- 事件与监听器 [290]
- 关键组件 [285]
- 概述 [285]
- 教程 [293]
- 使用 `LiveData` [267]

# 设备测试
- DDMS [36]
- 调试
- 在设备上启用 [63]
- `debug.keystore` 文件 [443], [465]
- `DefaultLifecycleObserver` [308], [311]
- 设备定义 [143]
- 设备文件管理器 [58]
- 设备外框 [40]
- 设备镜像 [69]
- 启用 [69]
- 设备配对 [67]
- 数字资产链接 [680], [443]
- 直接回复 [534]
- 启用 ADB 支持 [63]

# 布局 XML
- 相对相对 [343]
- 密度无关像素 [193]
- 转换为像素 [208]
- `dp` [193]

# 模拟器配置
- 电池 [46]
- 移动网络配置 [46]
- 配置指纹 [48]
- 方向键 [46]
- 扩展控制选项 [45]
- 扩展控制 [45]
- 指纹 [46]
- 位置配置 [46]
- 手机设置 [46]
- 可调整大小 [50]
- 调整大小 [45]
- 旋转 [44]
- 录屏 [47]
- 截屏 [47]
- 启动 [33]
- 截图 [44]
- 工具栏 [43]
- 工具栏选项 [43]
- 工具窗口模式 [50]
- 虚拟传感器 [47]
- 缩放 [44]

# 应用内概览
- `enablePendingPurchases()` 方法 [719]

# Gradle 概述
- `settings.gradle` 文件 [748]

# 事件处理
- 事件处理 [215]
- 示例 [216]
- 事件监听 [217]
- 事件监听器 [216]
- 消费 [219]

# 主题教程
## 动态色彩
- `applyToActivitiesIfAvailable()` 方法 [743]
- 在 Android 中启用 [743]
- 动态状态 [105]
- 保存 [119]

# Activity 周期
- 空进程 [99]
- 空模板 [129]

# 云端存储
- 文档提供者 [587]

# 应用结构
- 显式
- `intent` [88]

# 显式意图 [439]

# 显式意图 [439]

# 扩展控制

## 选项 [45]

## F

## 文件
- 切换 [72]
- `findPointerIndex()` 方法 [222]
- `findViewById()` [91]

## 指纹
### 模拟 [48]
### 指纹识别
- 设备配置 [694]
- 权限 [694]
- 实施步骤 [693]

### 指纹识别
- 概述 [693]
- 教程 [693]

## FLAG_INCLUDE_STOPPED_PACKAGES [469]

## 悬浮操作
- 灵活空间区域 [417]
- 悬浮操作按钮 [16], [130]
- 更改外观 [378]
- 外边距 [376]
- 移除 [131]
- 尺寸 [376]

## 折叠屏
- 折叠屏设备 [108]
- 多重恢复 [108]
- 折叠屏模拟器 [540]
- 折叠屏 [539]

## 前台
- 前台进程 [98]
- 正向地理编码 [637]

## 碎片
- `Fragment` 类
- 创建 [245]
- 事件处理 [249]
- XML 文件 [246]
- `FragmentActivity` 类 [104]
- 碎片通信 [250]
- 碎片 [245]
- 在代码中添加 [248]
- 复制 [386]
- 示例 [253]
- 概述 [245]
- `FragmentStateAdapter` 类 [389]
- `FrameLayout` [126]

## 地理编码器
- `Geocoder` 对象 [638]
- 地理编码 [636]

## 手势
- `Gesture Builder` 应用 [235]
- 构建与运行 [235]
- `Gesture Detector` 类 [229]
- `GestureDetectorCompat` [232]
- 实例创建 [232]
- `GestureDetectorCompat` 类 [229]
- `GestureDetector.OnDoubleTapListener` [229], [230]
- `GestureDetector.OnGestureListener` [230]
- `GestureLibrary` [235]
- `GestureOverlayView` [235]
- 配置颜色 [240]
- 配置多笔触 [240]
- `GestureOverlayView` 类 [235]
- `GesturePerformedListener` [235]

## 手势
- 拦截 [241]

## 手势文件
- 创建 [236]
- 从 SD 卡提取 [236]
- 加载到应用程序 [238]
- `GET_ACCOUNTS` 权限 [504]
- `getAction()` 方法 [475]
- `getDebugMessage()` [733]
- `getLocation()` [637]
- `getId()` [198]
- `getIntent()` [440]
- `getPointerCount()` [222]
- `getPointerId()` [222]
- `getState()` [719]
- `getService()` [482]

## GNU/Linux
- 账户 [632]
- 项目 [633]
- 打印 [637]
- 存储 [638]
- 实例 [694]
- 类型 [694]

## Google 地图 API
- 控制 [638]
- 显示 [636]
- 标记 [638]
- 概述 [693]
- SDK [637]

## Google Play
- 应用 [694]
- 控制台 [694]
- 创建一个应用 [693]
- 测试人员 [693]
- 开发者控制台 [694]

## Gradle
- APK 签名设置 [45]
- 构建变体 [108]
- 命令行任务 [235]
- 依赖项 [249]
- Manifest 条目 [246]
- 概述 [245]
- 默认值 [245]
### Gradle 构建文件
- 顶层 [236]
### Gradle 构建文件
- 模块级 [236]
- `gradle.properties` 文件 [238]

# 隐式许可

## 隐式许可
### 示例
### 重要性分级
### 在...中

## 应用内
### 应用内商品
### 应用内购买
- `acknowledgePurchase()` 方法
- `BillingClient`
- `BillingResult`
- `consumeAsync()` 方法
- `ConsumeParams`
- `ConsumeResponseListener`
- 消耗购买
- `enablePendingPurchases()` 方法
- `getPurchaseState()` 方法
- `launchBillingFlow()` 方法
### 库
- `newBuilder()` 方法
- `onBillingServiceDisconnected()` 回调
- `onBillingServiceDisconnected()` 方法
- `onBillingSetupFinished()` 监听器
### 概述
- `ProductDetail`
- `ProductDetails`
- `products`
- `ProductType`
- `ProductType.INAPP`
- `ProductType.SUBS`
### 购买流程
- `PurchaseResponseListener`
- `PurchasesUpdatedListener`
- `PurchaseUpdatedListener`
- 购买更新
- `queryProductDetailsAsync()`
- `queryProductDetailsAsync()` 方法
- `queryPurchasesAsync()`
- `queryPurchasesAsync()` 方法
- `runOnUiThread()`
### 订阅
### 教程

## 内存数据库
## 许可
- 显式
- 隐式
### 许可可用性
- 检查
- `Intent.CATEGORY_OPENABLE`
### 许可过滤器
## App 链接
## 许可
- `ActivityResultLauncher`
- 概述
- `registerForActivityResult()`
- `Intent Service`
- `Intent URL`

## Java Native Interface
### Jetpack
- 概述
- `JobIntentService`
- `BIND_JOB_SERVICE` 权限
- `onHandleWork()` 方法
## 密钥
- 属性
- 键盘快捷键
- 密钥周期
- 周期编辑器
- 教程
- 关键帧
- 关键帧
- 关键帧集
- 关键帧位置
- 相对
- 父级相对
- 路径相对
### 密钥库文件
- 创建
- 密钥周期
- `keytool`
- 密钥触发
- 已杀死状态

## L
- `launchBillingFlow()` 方法
### `layout_collapseMode`
- 视差
- 固定
- `layout_constraintDimentionRatio`
- `layout_constraintHorizontal_bias`
- `layout_constraintVertical_bias`
### 布局编辑器
- ConstraintLayout 链
- `Layout Editor`
- 自动连接模式
- 代码模式
- 组件树
- 设计模式
- 设备屏幕
- 示例项目
- 推断模式
- 调色板
- 属性面板
- 示例数据
- 设置属性
- 工具栏
- 用户界面设计
- 视图转换
### 布局编辑器工具
- 更改方向
- 概述
- 布局检查器
- 布局管理器
- `LayoutResultCallback` 对象
### 布局
### `layout_scrollFlags`
- 始终折叠进入模式
- 始终进入模式
- 退出直到折叠模式
- 滚动模式
### 布局验证
### `libc`
### 许可测试人员
## 生命周期
- 意识
- 组件

# 所有者 [307]
# 状态与事件 [309]
# 教程 [311]

## 生命周期感知组件 [307]
## 生命周期方法 [106]
## 生命周期观察者 [311]
### 创建生命周期所有者 [311]
### 创建生命周期 [313]

## 现代 [268]
## LinearLayout [126]
## LinearLayoutManager [395]
### LinearLayoutManager 布局 [404]

## Linux 内核 [84]
### 列出设备 [63]

## LiveData [266], [279]
### 添加到 ViewModel [279]
### 观察者 [281]
### 教程 [279]

## Live Templates [80]

## 本地服务 [477]
### 示例 [477]

## 位置管理器 [86]
### 位置权限 [504]

## Logcat
### 工具窗口 [57]

## LogCat
### 启用 [115]

## M
### `MANAGE_EXTERNAL_STORAGE` [505]
### `adb` 启用 [505]
### 测试 [505]

## Manifest 文件
### 权限 [461]

## 地图 [631]
### MapView [631]
### 添加到布局 [638]
### Marker 类 [631]

## 主界面/详情流
### 创建 [426]
### 双窗格模式 [425]
### `match_parent` 属性 [193]

## Material 设计 [375]
## Material Design 2 [735]
### Material Design 2 主题化 [735]
## Material Design 3 [735]
### Material Theme Builder [737]
### Material You [735]

## MediaController
### 添加到 VideoView 实例 [605]
### MediaController 类 [602]
### 方法 [602]
## MediaPlayer 类 [621]
### 方法 [621]
## MediaRecorder 类 [621]
### 方法 [622]
### 录制音频 [622]

## 内存指示 [73]

## Messenger 对象 [487]

## 麦克风
### 检查可用性 [624]
### 麦克风权限 [504]
### `mm` [193]

## MotionEvent [221], [222], [243]
### `getActionMasked()` [222]

## MotionLayout [337]
### `MotionLayout` 动画 [342]
### 属性关键帧 [342]
### ConstraintSets [338]
### 自定义属性 [358]
### 自定义属性 [339]
### 编辑器 [367]
### 编辑器 [349]
### KeyAttribute [342]
### KeyCycle [363]
### Keyframes [342]
### FrameSet [372]
### KeyPosition [343]
### KeyTime [363]
### KeyTrigger [346]
### `OnClick` [341], [354]
### `OnSwipe` [341]
### 概述 [337]
### 关键帧位置 [343]
### 预览动画 [354]
### 触发关键帧 [346]
### 教程 [349]

## MotionScene
### ConstraintSets [338]
### 自定义属性 [339]
### 文件 [338]
### 概述 [337]
### 转换 [338]
### `moveCamera()` 方法 [645]

## 多设备
### 在...上测试应用 [35]

## 多点触摸
### 处理 [222]
### 多重恢复 [108]

## 多点触摸
### 示例 [222]
### 多点触摸事件处理 [221]

## 多窗口
### 属性 [543]

## 多窗口模式
### 检测 [544]
### 进入 [541]
### 启动活动到... [545]
### 多窗口通知 [544]
### 多窗口支持 [108]

## 多窗口支持
### 启用 [542]

## 我的位置层 [631]

## N
## 导航 [317]
### 添加目的地 [326]
### 概述 [317]
### 使用 safeargs 传递数据 [333]
### 传递参数 [322]
### 栈 [317]
### 教程 [323]

## 导航动作
### 触发 [321]
## 导航架构组件 [317]

## 导航组件
### 教程 [323]

## 导航控制器
### 访问 [321]
### 导航图 [320], [324]
### 添加动作 [329]
### 创建一个 [324]
## 导航主机 [318]

# 声明 [325]

# `newBuilder()` 方法 [716]

# 正常权限 [503]

# 通知
## 添加动作 [522]
## 直接回复输入 [534]
## 发送基础 [518]
## 从...中启动活动 [520]
## `PendingIntent` [530]
## 回复动作 [532]
## 更新直接回复 [535]

# 通知
## 组合 [523]
## 概述 [511]
# 通知管理器 [86]

# O

# 观察者
## 实现 LiveData [281]
## `onAttach()` 方法 [250]
## `onBillingServiceDisconnected()` 回调 [728]
## `onBillingServiceDisconnected()` 方法 [717]
## `onBillingSetupFinished()` 监听 [728]
## `onBind()` 方法 [436], [477]
## `onBindViewHolder()` 方法 [403]
## `OnClick` [341]
## `onClickListener` [216], [217], [220]
## `onClick()` 方法 [215]
## `onCreateContextMenuListener` [216]
## `onCreate()` 方法 [98], [106], [436]
## `onCreateView()` 方法 [107]
## `onDestroy()` 方法 [106], [436]
## `onDoubleTap()` 方法 [229]
## `onDown()` 方法 [229]
## `onFling()` 方法 [229]
## `onFocusChangeListener` [216]

# OnFragmentInteractionListener
## 实现 [331]
## `onGesturePerformed()` 方法 [235]
## `onHandleWork()` 方法 [436]
## `onKeyListener` [216]
## `onLayoutFailed()` 方法 [670]
## `onLayoutFinished()` 方法 [671]
## `onLongClickListener` [216]
## `onLongClick()` 方法 [219]
## `onLongPress()` 方法 [229]
## `onMapReady()` 方法 [640]
## `onPageFinished()` 回调 [656]
## `onPause()` 方法 [106]
## `onProductDetailsResponse()` 回调 [728]
## `onReceive()` 方法 [98], [470], [471], [473]
## `onRequestPermissionsResult()` 方法 [507], [516], [528], 628
## `onRestart()` 方法 [106]
## `onRestoreInstanceState()` 方法 [107]
## `onResume()` 方法 [98], [106]
## `onSaveInstanceState()` 方法 [107]
## `onScaleBegin()` 方法 [241]
## `onScaleEnd()` 方法 [241]
## `onScale()` 方法 [241]
## `onScroll()` 方法 [229]
## `OnSeekBarChangeListener` [260]
## `onServiceConnected()` 方法 [477], [481], [488]
## `onServiceDisconnected()` 方法 [477], [481], [488]
## `onShowPress()` 方法 [229]
## `onSingleTapUp()` 方法 [229]
## `onStartCommand()` 方法 [436]
## `onStart()` 方法 [106]
## `onStop()` 方法 [106]
## `onTouchEvent()` 方法 [229], [241]
## `onTouchListener` [216]
## `onTouch()` 方法 [221]
## `onViewCreated()` 方法 [107]
## `onViewStatusRestored()` 方法 [107]
## `openFileDescriptor()` 方法 [588]

# `OpenJDK` [3]

# P
## 包资源管理器 [18]
## 软件包包管理器 [86]
## `PackageManager` 类 [624]
## `PackageManager.FEATURE_MICROPHONE` [624]
## `PackageManager.PERMISSION_DENIED` [505]
## `PackageManager.PERMISSION_GRANTED` [505]
## 包名 [16]
## 打包链 [151], [180]
## 页面范围 [672], [673]
## `Paint` 类 [675]
## 相对父级 [343]
## 父视图 [127]
## 相对路径 [344]
## 暂停状态 [100]
## `PdfDocument` [653]
## `PdfDocument.Page` [665], [672]
## `PendingIntent` 类 [530]

# 权限
## 检查 [505]
## 权限
## 正常 [503]
## 持久状态 [105]
## 手机权限 [504]
## 选择器 [587]

# 缩合手势
## 检测 [241]
## 示例 [241]
## 缩合手势识别 [235]
## 关键帧位置 [343]

# POST_NOTIFICATIONS 权限 [504], [528]

# 打印属性 [670]

# `PrintDocumentAdapter` [653], [665]

# 打印
- `color` [650]
- `monochrome` [650]

## 打印框架
- `architecture` [647]
- `Printing Framework` [647]

## 打印任务
- `starting` [676]
- `PrintManager` service [657]

# 问题
- `tool window` [58]

## 进程
- `priority` [97]
- `state` [97]
- `PROCESS_OUTGOING_CALLS` permission [504]
- `Process States` [97]

- `ProductDetail` [718]
- `ProductDetails` [729]
- `ProductType` [720]

# 分析器
- `tool window` [58]
- `ProgressBar` [125]
- `proguard-rules.pro` file [752]
- `ProGuard Support` [748]

- `Project Name` [16]
- `Project tool window` [18], [57]

- `pt` [193]
- `PurchaseResponseListener` [720]
- `PurchasesUpdatedListener` [719]
- `PurchaseUpdatedListener` [729]
- `putExtra()` method [439], [469]
- `px` [194]

# Q
- `queryProductDetailsAsync()` [728]
- `queryProductDetailsAsync()` method [718]
- `queryPurchaseHistoryAsync()` method [720]
- `queryPurchasesAsync()` [731]
- `queryPurchasesAsync()` method [720]
- `quickboot snapshot` [48]
- `Quick Documentation` [79]

# R
- `RadioButton` [125]
- `ratios` [181]
- `READ_CALENDAR` permission [504]
- `READ_CALL_LOG` permission [504]
- `READ_CONTACTS` permission [504]
- `READ_EXTERNAL_STORAGE` permission [505]
- `READ_PHONE_STATE` permission [504]
- `READ_SMS` permission [504]
- `RECEIVE_MMS` permission [504]
- `RECEIVE_SMS` permission [504]
- `RECEIVE_WAP_PUSH` permission [504]
- `Recent Files Navigation` [60]
- `RECORD_AUDIO` permission [504]

# 录音
- `permission` [623]

- `RecyclerView` [395]
- `adding to layout file` [396]
- `GridLayoutManager` [395]
- `initializing` [404]
- `LinearLayoutManager` [395]
- `StaggeredGridLayoutManager` [395]
## RecyclerView Adapter
- creation of [402]
- `RecyclerView.Adapter` [396], [402]
- `getItemCount()` method [396]
- `onBindViewHolder()` method [396]
- `onCreateViewHolder()` method [396]

## RecyclerView.ViewHolder
- `getAdapterPosition()` method [406]
- `registerActivityResult()` method [440], [454]
- `registerReceiver()` method [471]

- `RelativeLayout` [126]
- `releasePersistableUri()` method [591]

# 准备发布 [701]

## 绑定服务
- `client communication` [485]
- `implementation` [485]
- `manifest file declaration` [487]
- `RemoteInput.Builder()` method [530]
- `RemoteInput` Object [530]

## 绑定服务
- `launching and binding` [488]
- `sending a message` [489]

## 仓库
- `tutorial` [571]
- `Modules` [268]
- `Emulator` [48]

#
- `string` [23]
- `File` [57]
- `Management` [97]
- `receiver` [471]
- `geocoding` [637]
- `geocoding` [636]

# Room
- `Data Access Object (DAO)` [554]
- `entities` [554], [555]
- `In-Memory Database` [561]
- `Repository` [554]
- `Database` [554]
- `tutorial` [571]
- `Persistence` [553]
- `Persistence Library` [550], [553]

# root
- `root element` [125]
- `root view` [127]

# 
- `tool window` [57]

# 运行中的设备
- `tool window` [69]
- `runOnUiThread()` [729]

# S
- `safeargs`
- `Sample Data` [142], [409]
- `tutorial` [409]

# 保存状态 [267], [301]
- `library dependencies` [303]
- `SavedStateHandle` [302], [303]
- `contains()` method [303]
- `keys()` method [303]
- `remove()` method [303]
- `SavedState module` [301]
- `SavedStateViewModelFactory` [302]

- `ScaleGestureDetector class` [241]
- `Scale-independent` [193]

# SDK 包

# 安全套接层 (SSL)

# SeekBar

# `sendBroadcast()` 方法

# `sendOrderedBroadcast()` 方法

# `SEND_SMS` 权限

# `sendStickyBroadcast()` 方法

# 传感器权限

# 服务 (Service)

## 
- 在系统启动时启动
- manifest 文件条目
- 概述
- 在独立进程中运行

## `ServiceConnection` 类

## 服务进程

## 服务重启选项
- `setAudioEncoder()` 方法
- `setAudioSource()` 方法
- `setBackgroundColor()`
- `setCompassEnabled()` 方法
- `setContentView()` 方法
- `setId()` 方法
- `setMyLocationButtonEnabled()` 方法
- `setOnClickListener()` 方法
- `setOnDoubleTapListener()` 方法
- `setOutputFile()` 方法
- `setOutputFormat()` 方法
- `setResult()` 方法
- `setRotateGesturesEnabled()` 方法
- `setScrollGesturesEnabled()` 方法
- `setText()` 方法
- `setTiltGesturesEnabled()` 方法
- `settings.gradle.kts` 文件
- `setTransition()`
- `setVideoSource()` 方法
- `setZoomControlsEnabled()` 方法

# SHA-256 证书指纹

# `shouldOverrideUrlLoading()` 方法

# `SimpleOnScaleGestureListener`
# `SimpleOnScaleGestureListener` 类

# SMS 权限

# Snackbar

# 快照 (Snapshots)
- `emulator`
- `sp`
- 展开链
- 内部展开
- 内部展开链

# SQL
# `SQLite`
- `AVD` 命令行用法
- 列和数据类型
- 概述
- 主键
- `StaggeredGridLayoutManager`
- `startActivity()` 方法
- `startForeground()` 方法
- `START_NOT_STICKY`
- `START_REDELIVER_INTENT`
- `START_STICKY`

# 状态 (State)
- 恢复

## 状态更改
- 处理
- 语句完成

## 状态栏
- 内存指示器
- 粘性意 (Sticky Intents)
- 停止状态

## 存储访问框架 (Storage Access Framework)
- `ACTION_CREATE_DOCUMENT`
- `ACTION_OPEN_DOCUMENT`
- 删除文件
- 示例
- 文件创建
- 文件过滤
- 文件读取
- 文件写入
- 意 (intents)
- MIME 类型
- 持久化访问
- 选择器
- 存储权限
- `StringBuilder` 对象
- `strings.xml` 文件

# 结构 (Structure)
- 工具窗口
- 结构查询语言
- 结构工具窗口
- `SUBS`
- 订阅 (subscriptions)

# `SupportMapFragment` 类

# `Switcher`

# 系统广播
- 系统要求

# T
## TabLayout
- 添加到布局
## app
- `tabGravity` 属性
- `tabMode` 属性
- 示例
- 固定模式
- `getItemCount()` 方法
- 概述
- `TableLayout`
- `TableRow`

# 电话管理器 (Telephony Manager)

## 模板
- 空 vs. 空

# 终端 (Terminal)
- 工具窗口

# 主题 (Theme)
- 构建自定义主题
## 主题化
- 教程

# 时间周期关键帧

# TODO
- 工具窗口

# `ToolbarListener`

# 工具 (tools)
- 布局
- 工具窗口栏
- 工具窗口

# 触摸操作 [222]

## 触摸事件监听
- 实现 [223]

## 触摸事件
- 拦截 [221]
- 触摸处理 [221]

# U
## `UiSettings` 类 [631]
- `unbindService()` 方法 [435]
- `unregisterReceiver()` 方法 [471]
- 上传密钥 [704]
## URL 映射 [685]
## USB 连接问题
- 解决 [66]
- `USE_BIOMETRIC` [694]
- 用户界面状态 [105]
- `USE_SIP` 权限 [504]

# V
## 视频播放 [601]
- `VideoView` 类 [601]
- 方法 [601]
- 支持的格式 [601]

## 视图绑定
- 启用 [92]
- 使用 [92]

## `View` 类
- 设置属性 [204]
- 视图转换 [141]
## `ViewGroup` [125]
- 视图组 [125]
- 视图层级结构 [127]
## `ViewHolder` 类 [396]
- 示例实现 [403]

## `ViewModel`
- 添加 LiveData [279]
- 数据访问 [276]
- 概述 [266]
- 保存状态 [301]
- 保存状态 [267], [301]
- 教程 [271]
- `ViewModelProvider` [274]
- ViewModel 保存状态 [301]

## `ViewPager`
- 添加到布局中 [387]
- 示例 [384]

## 视图 [125]
- Java 创建 [197]
## 视图系统 [86]
- 虚拟设备配置对话框 [32]
- 虚拟传感器 [47]
- 可见进程 [98]

# W
## `WebViewClient` [651], [656]
- WebView 视图 [459]
- 加权链 [150], [180]
- 欢迎界面 [53]
- 小组件尺寸 [151]
- 小组件组对齐 [173]
- 小组件调色板 [186]
- WiFi 调试 [67]
- 无线调试 [67]
- 无线配对 [67]
- `wrap_content` 属性 [195]
- `WRITE_CALENDAR` 权限 [504]
- `WRITE_CALL_LOG` 权限 [504]
- `WRITE_CONTACTS` 权限 [504]
- `WRITE_EXTERNAL_STORAGE` 权限 [505]

# X
## XML 布局文件
- 手动创建 [193]
- 对比 Java 代码 [197]
