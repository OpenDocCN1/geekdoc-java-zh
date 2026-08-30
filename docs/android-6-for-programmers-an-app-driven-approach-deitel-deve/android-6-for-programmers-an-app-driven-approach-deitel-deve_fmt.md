
# Android 6 程序员指南：应用驱动的方法 (Deitel 开发者系列)

访问我们的网站：`informit.com/php`

Paul Deitel • Harvey Deitel • Alexander Wald

Deitel & Associates, Inc.

要获取 Deitel 出版物、资源中心、培训课程、合作伙伴优惠等更多更新，请在以下平台加入 Deitel 社区：

- Facebook—`www.deitel.com/DeitelFan`
- Twitter—`@deitel`
- Google™—`google.com/DeitelFan`
- YouTube—`youtube.com/DeitelTV`
- LinkedIn—`linkedin.com/company/deitel`

## 目录

### 前言 xxi

### 开始之前 xx

## I Android 简介

- 1.1 简介——世界领先的操作系统 3
- 1.2 Android 2.2 (Ice Cream Sandwich) 3
- 1.3 Android 特性 6
- 1.4 Android 操作系统 6
  - 1.4.1 Android 2.2 (Froyo) 7
  - 1.4.2 Android 2.3 (Gingerbread) 7
  - 1.4.3 Android 3.0 到 3.2 (Honeycomb) 8
  - 1.4.4 Android 4.0 到 4.0 (Ice Cream Sandwich) 9
  - 1.4.5 Android 4.1–4.3 (Jelly Bean) 9
  - 1.4.6 Android 4.4 (KitKat) 10
  - 1.4.7 Android 5.0 和 5.1 (Lollipop) 11
  - 1.4.8 Android 6 (Marshmallow) 12
- 1.5 从 Google Play 下载应用 13
- 1.6 包 14
- 1.7 Android 软件开发包 (SDK) 16
- 1.8 面对象编程：快速复习 18
  - 1.8.1 汽车作为对象 19
  - 1.8.2 方法与类 19
  - 1.8.3 实例化 19
  - 1.8.4 重用 19
  - 1.8.5 消息与方法调用 19
  - 1.8.6 属性与实例变量 20
  - 1.8.7 封装 20
  - 1.8.8 继承 20
  - 1.8.9 面对象分析与设计 (OOAD) 20
- 1.9 在 Android 设备 (AVD) 上测试驱动计算器应用 21
  - 1.9.1 在 `Android Studio` 中打开计算器应用项目 22
  - 1.9.2 创建安卓虚拟设备 (AVDs) 24
  - 1.9.3 在 Nexus 6 手机 AVD 上运行计算器应用 25
  - 1.9.4 在 Android 设备上运行计算器应用 30
- 1.10 构建出色的 Android 应用 30
- 1.11 Android 开发资源 32
- 1.12 总结 34

## 2 欢迎应用 35

Dive-Into® Android Studio：介绍视觉化 GUI 设计、布局、可访问性和国际化

- 2.1 引言 36
- 2.2 技术概览 37
  - 2.2.1 Android Studio 37
  - 2.2.2 线性布局 (`LinearLayout`)、`TextView` 和 `ImageView` 37
  - 2.2.3 可扩展标记语言 (XML) 38
  - 2.2.4 应用资源文件 38
  - 2.2.5 可访问性 38
  - 2.2.6 国际化 38
- 2.3 创建应用 38
  - 2.3.1 启动 Android Studio 39
  - 2.3.2 创建新项目 39
  - 2.3.3 创建新项目对话框 40
  - 2.3.4 目标 Android 设备 40
  - 2.3.5 向移动设备添加 Activity 的步骤 42
  - 2.3.6 自定义 Activity 的步骤 43
- 2.4 Android Studio 44
  - 2.4.1 项目窗口 45
  - 2.4.2 编辑窗口 46
  - 2.4.3 组件树窗口 46
  - 2.4.4 应用资源文件 46
  - 2.4.5 布局编辑器 47
  - 2.4.6 默认 GUI 48
  - 2.4.7 默认 GUI 的 XML 49
- 2.5 使用布局编辑器构建应用的 GUI 49
  - 2.5.1 向项目添加图像 50
  - 2.5.2 添加图标 51
  - 2.5.3 相对于 `LinearLayout` 的更改 52
  - 2.5.4 更改布局的 `id` 和方向 53
  - 2.5.5 配置 `TextView` 的 `id` 和属性 54
  - 2.5.6 配置 `TextView` 的大小属性 `size`——缩放像素 (`sp`) 和密度无关像素 (`dp`) 56
  - 2.5.7 设置 `TextView` 的颜色属性 `color` 57
  - 2.5.8 设置 `TextView` 的对齐属性 `gravity` 58
  - 2.5.9 设置 `TextView` 的布局对齐属性 `layout_gravity` 59
  - 2.5.10 设置 `TextView` 的布局权重 `layout_weight` 60
  - 2.5.11 添加 `ImageView` 显示图像 60
  - 2.5.12 预览设计 64
- 2.6 运行欢迎应用 65
- 2.7 让你的应用具有可访问性 66
- 2.8 你的应用国际化
  - 2.8.1 本地化
  - 2.8.2 为本地化资源文件夹命名
  - 2.8.3 在应用项目中添加字符串翻译
  - 2.8.4 字符串本地化
  - 2.8.5 在 AVD 上测试西班牙语版应用
  - 2.8.6 在设备上测试西班牙语版应用
  - 2.8.7 `TalkBack` 与本地化
  - 2.8.8 本地化清单
  - 2.8.9 专业翻译
- 2.9 总结

## 3 小费计算器应用

介绍 `GridLayout`、`EditText`、`SeekBar`、事件处理、`NumberFormat`、自定义应用主题以及使用 Java 定义应用功能

- 3.1 引言
- 3.2 测试驱动小费计算器
- 3.3 技术概览
  - 3.3.1 类 `Activity`
  - 3.3.2 `Activity` 生命周期方法
  - 3.3.3 `AppCompat` 库和类 `CompatActivity`
  - 3.3.4 使用 `GridLayout` 安排视图
  - 3.3.5 使用布局编辑器、组件树和属性窗口创建并自定义 GUI
  - 3.3.6 将数字格式化为特定区域的货币和百分比字符串
  - 3.3.7 实现接口 `TextWatcher` 以编辑文本更改
  - 3.3.8 实现 `OnSeekBarChangeListener` 以处理 `SeekBar` 滑块位置材料
  - 3.3.9 Material Design：高度与阴影
  - 3.3.10 Material Design：颜色
  - 3.3.11 `AndroidManifest.xml`
  - 3.3.12 在属性窗口中搜索
- 3.4 构建 GUI
  - 3.4.1 `GridLayout` 介绍
  - 3.4.2 创建 TipCalculator 项目
  - 3.4.3 切换到 `GridLayout`
  - 3.4.4 添加视图、`EditText` 和 `SeekBar`
  - 3.4.5 自定义视图
- 3.5 默认主题和自定义主题颜色
  - 3.5.1 父级主题
  - 3.5.2 自定义主题颜色
  - 3.5.3 常用属性值的样式
- 3.6 添加应用逻辑 92
  - 3.6.1 `package` 和 `import` 语句 93
  - 3.6.2 `MainActivity` `AppCompatActivity` 的子类 94
  - 3.6.3 类变量和实例变量 94
  - 3.6.4 重写方法 `onCreate` 95
  - 3.6.5 `MainActivity` 方法 `calculate` 97
  - 3.6.6 实现 `OnSeekBarChangeListener` 接口的匿名内部类 98
  - 3.6.7 实现 `TextWatcher` 接口的匿名内部类 99
- 3.7 `AndroidManifest.xml` 100
  - 3.7.1 `manifest` 元素 101
  - 3.7.2 `application` 元素 101
  - 3.7.3 `activity` 元素 102
  - 3.7.4 `intent-filter` 元素 102
- 3.8 总结 103

## 4 国旗测验应用 105

`Fragments`、`Menu`、`Preferences`、显式 `Intent`、`Handler`、`AssetManager`、补间动画、`Toasts`、颜色状态、多方向布局、用于调试的错误日志

- 4.1 引言
- 4.2 测试驱动国旗应用 108
  - 4.2.1 配置测验设置 108
  - 4.2.2 参加测验 110
- 4.3 技术概览 113
  - 4.3.1 菜单 113
  - 4.3.2 `Fragments` 113
  - 4.3.3 `Fragment` 生命周期周期方法 114
  - 4.3.4 管理 `Fragments` 114
  - 4.3.5 `Preferences` 114
  - 4.3.6 `assets` 文件夹 115
  - 4.3.7 资源文件夹 115
  - 4.3.8 支持不同的尺寸和分辨率 116
  - 4.3.9 确定设备方向 117
  - 4.3.10 用于显示信息的 `Toasts` 117
  - 4.3.11 使用 `Handler` 执行 `Runnable` 117
  - 4.3.12 将动画应用于视图 117
  - 4.3.13 使用 `AnimationUtils` 创建循环显示 118
  - 4.3.14 通过颜色列表指定颜色 118
  - 4.3.15 `AlertDialog` 119
  - 4.3.16 异常日志 119
  - 4.3.17 通过显式 `Intent` 启动另一个 `Activity` 119
  - 4.3.18 Java 数据结构 120
  - 4.3.19 Java SE 7 特性 120
  - 4.3.20 `AndroidManifest.xml` 120
- 4.4 创建项目、资源文件和类
  - 4.4.1 创建项目
  - 4.4.2 空 `Activity` 布局
  - 4.4.3 支持 Java SE 7
  - 4.4.4 向项目添加国旗图像
  - 4.4.5 `strings.xml` 和格式化字符串
  - 4.4.6 `arrays.xml`
  - 4.4.7 `colors.xml`
  - 4.4.8 `button_text.xml`
  - 4.4.9 `menu_main.xml`
  - 4.4.10 创建国旗摇晃动画
  - 4.4.11 `preferences.xml` 指定应用设置
  - 4.4.12 向项目添加 `SettingsActivity` 和 `SettingsFragment`
- 4.5 构建应用 GUI
  - 4.5.1 竖屏模式下的 `activity_main.xml` 181
  - 4.5.2 `MainActivityFragment` 的 `fragment_main.xml` 182
  - 4.5.3 用于 `ColorDialog` 的 `fragment_color.xml` 182
  - 4.5.4 用于 `LineWidthDialog` 的 `line_width.xml` 185
  - 4.5.5 添加 `EraseImageDialog` 类 187
- 4.6 `MainActivity` 类 188
- 4.7 `Fragment` 类 188
  - 4.7.1 `package` 语句和 `import` 语句 188
  - 4.7.2 字段 189
  - 4.7.3 重写方法 `onCreate` 190
  - 4.7.4 重写方法 `onStart` 191
  - 4.7.5 重写方法 `onCreateOptionsMenu` 191
  - 4.7.6 重写方法 `onItemSelected` 192
  - 4.7.7 实现 `OnSharedPreferenceChangeListener` 的匿名内部类 192
- 4.8 `SettingsFragment` 类 193
  - 4.8.1 `package` 语句和 `import` 语句 193
  - 4.8.2 字段 193
  - 4.8.3 重写方法 `onCreate` 194
  - 4.8.4 重写方法 `updateRows` 195
  - 4.8.5 重写方法 `updateRegions` 196
  - 4.8.6 重写方法 `resetQuery` 196
  - 4.8.7 方法 `loadNextFlag` 197
  - 4.8.8 方法 `getCountryName` 197
  - 4.8.9 方法 `animate` 198
  - 4.8.10 实现 `OnClickListener` 的匿名内部类 198
  - 4.8.11 重写方法 `disableButtons` 199
- 4.9 `SettingsActivity` 类 200
- 4.10 `SettingsFragment` 类 200
- 4.11 `AndroidManifest.xml`
- 4.12 总结

## 5 涂鸦应用

2D 图形、`Canvas`、`Bitmap`、加速度计、`SensorManager`、多点触、打印、Android 6.0 权限、Gradle

- 5.1 引言 167
- 5.2 在 Android 虚拟设备 (AVD) 上测试涂鸦应用 168
- 5.3 技术概览 173
  - 5.3.1 `Activity` 和 `Fragment` 生命周期周期方法 173
  - 5.3.2 自定义视图 174
  - 5.3.3 使用 `SensorManager` 监听加速度事件 174
  - 5.3.4 自定义 `DialogFragments` 174
  - 5.3.5 使用 `Canvas`、`Paint` 和 `Bitmap` 绘图 175
  - 5.3.6 处理触摸事件并将线条存储在 `Path` 中 175
  - 5.3.7 保存到设备 175
  - 5.3.8 使用 Android 支持库的 `PrintHelper` 类 176
  - 5.3.9 新 Android 6.0 (Marshmallow) 权限 176
  - 5.3.10 使用 Gradle 构建系统添加依赖 176
- 5.4 创建项目和资源 176
  - 5.4.1 创建项目
  - 5.4.2 Gradle：向项目添加支持库 177
  - 5.4.3 `strings.xml` 177
  - 5.4.4 为应用菜单导入 Material Design 图标 178
  - 5.4.5 `MainActivityFragment` 179
  - 5.4.6 向 `AndroidManifest.xml` 添加权限 181
- 5.5 构建应用的 GUI 181
  - 5.5.1 用于 `MainActivity` 的 `content_main.xml` 181
  - 5.5.2 用于 `MainActivityFragment` 的 `fragment_main.xml` 182
  - 5.5.3 用于 `ColorDialog` 的 `fragment_color.xml` 182
  - 5.5.4 用于 `LineWidthDialog` 的 `line_width.xml` 185
  - 5.5.5 添加 `EraseImageDialog` 类 187
- 5.6 `MainActivity` 类 188
- 5.7 `Fragment` 类 188
  - 5.7.1 `package` 语句和 `import` 语句 188
  - 5.7.2 重写方法 `onCreate` 189
  - 5.7.3 方法 `onResume` 和 `enableAccelerometerListener` 190
  - 5.7.4 方法 `onPause` 和 `disableAccelerometerListener` 191
  - 5.7.5 用于处理 `AccelerometerEvents` 的匿名内部类 192
  - 5.7.6 方法 `onConfirmResult` 193
  - 5.7.7 重写方法 `onCreateOptionsMenu` 和 `onItemSelected` 193
  - 5.7.8 方法 `saveImage` 195
  - 5.7.9 重写方法 `onRequestPermissionsResult` 196
  - 5.7.10 方法 `getDoodleView` 和 `setDialogOnScreen` 197
- 5.8 `DoodleView` 198
  - 5.8.1 `package` 语句和 `import` 语句 198
  - 5.8.2 静态变量和实例变量 198
  - 5.8.3 构造函数 199
  - 5.8.4 重写的 `View` 方法 `onSizeChanged` 200
  - 5.8.5 方法 `clear`, `setDrawingColor`, `getDrawingColor`, `setLineWidth` 和 `getLineWidth` 200
  - 5.8.6 重写的 `View` 方法 `onDraw` 201
  - 5.8.7 重写的 `View` 方法 `onTouchEvent` 202
  - 5.8.8 `touchStarted` 方法 203
  - 5.8.9 `touchMoved` 方法 204
  - 5.8.10 `touchEnded` 方法 205
  - 5.8.11 方法 `saveBase` 205
  - 5.8.12 方法 `printImage` 206
- 5.9 `ColorDialogFragment` 类 207
  - 5.9.1 匿名 `DialogFragment` 方法 `onCreateDialog` 208
  - 5.9.2 方法 `getAnimationStyle` 209
  - 5.9.3 重写的 `Fragment` 生命周期方法 `onAttach` 和 `onDestroy` 209
  - 5.9.4 响应 `Alpha`、`Red`、`Green` 和 `Blue` `SeekBars` 事件的匿名内部类 210
- 5.10 `lineWidthDialogFragment` 类 211



- 5.10.1 方法 `onCreateDialog` 213
- 5.10.2 响应 `withSeekBar` 事件的匿名内部类 214
- 5.11 `EraseImageFragment` 类 214
- 5.12 总结 216

# 6 大炮游戏 App 217

手动逐帧动画、图形、音频、多线程、`SurfaceView` 和 `SurfaceHolder`、沉浸式模式和全屏 218

- 6.1 简介 220
- 6.2 试运行大炮游戏 App 220
- 6.3 技术概览 220
  - 6.3.1 使用资源文件夹 存储`/raw` 220
  - 6.3.2 `Activity` 和 `Fragment` 生命周期周期方法 220
  - 6.3.3 重写 `View` 方法 `onTouchEvent` 220
  - 6.3.4 使用 `SoundPool` 和 `AudioManager` 添加音频 220
  - 6.3.5 使用线程、`SurfaceView` 和 `SurfaceHolder` 进行逐帧动画 221
  - 6.3.6 简单碰撞检测 221
  - 6.3.7 沉浸式模式 222
- 6.4 构建 UI 和资源文件 222
  - 6.4.1 创建项目 222
  - 6.4.2 调整主题以移除 App 标题和应用栏 223
  - 6.4.3 `strings.xml` 223
  - 6.4.4 `Color` 223
  - 6.4.5 为 App 添加音频 223
  - 6.4.6 添加类 `MainActivityFragment` 224
  - 6.4.7 编辑 `activity_main.xml` 224
  - 6.4.8 在 `fragment_main.xml` 中添加 `CannonView` 224
- 6.5 本 App 类的概览 225
- 6.6 `Activity` 的子类 `MainActivity` 226
- 6.7 `Fragment` 的子类 `MainActivityFragment` 226
- 6.8 类 `ClassElement` 228
  - 6.8.1 实例变量和构造函数 229
  - 6.8.2 方法 `update`, `draw` 和 `playSound` 229
- 6.9 `ClassElement` 的子类 `Blocker` 230
- 6.10 `ClassElement` 的子类 `Target` 230
- 6.11 `Cannon` 类 231
  - 6.11.1 实例变量和构造函数 231
  - 6.11.2 方法 `align` 232
  - 6.11.3 方法 `fireCannonball` 232
  - 6.11.4 方法 `draw` 233
  - 6.11.5 方法 `getCannonball` 和 `removeCannonball` 234
- 6.12 `Class` 的子类 `Cannon11` 234
  - 6.12.1 实例变量和构造函数 234
  - 6.12.2 方法 `getRadius`, `collidesWith`, `onScreen` 和 `reverseVelocityY` 235
  - 6.12.3 方法 `update` 236
  - 6.12.4 方法 `draw` 236
- 6.13 `SearchView` 的子类 `CannonView` 237
  - 6.13.1 `package` 和 `import` 语句 237
  - 6.13.2 实例变量和常量 238
  - 6.13.3 构造函数 239
  - 6.13.4 重写的 `View` 方法 `onSizeChanged` 241
  - 6.13.5 方法 `getWidth`, `getScreenHeight` 和 `playSound` 242
  - 6.13.6 方法 `newGame` 244
  - 6.13.7 方法 `updatePositions` 244
  - 6.13.8 方法 `alignAndFireCannonball` 245
  - 6.13.9 方法 `showGameDialog` 246
  - 6.13.10 方法 `drawGameElements` 247
  - 6.13.11 方法 `testForCollisions` 248
  - 6.13.12 方法 `stopgame` 和 `releaseResources` 249
  - 6.13.13 实现 `SurfaceHolder.Callback` 250
  - 6.13.14 重写的 `View` 方法 `onTouchEvent` 251
  - 6.13.15 使用 `Thread` 创建游戏循环 252
  - 6.13.16 方法 `hideSystemBars` 和 `showSystemBars` 253
- 6.14 总结 254

REST Web Services, `AsyncTask`, `HttpUrlConnection`, `JSON Object`, `ListView`, `ArrayAdapter`, `ViewHolder Pattern`, `TextInputLayout`, `FloatingActionButton`

- 7.1 简介 257
- 7.2 运行 WeatherViewer App 258
- 7.3 技术概览 259
  - 7.3.1 Web Services 259
  - 7.3.2 JavaScript (JSON) 和 `org.json` 包 261
  - 7.3.3 HttpUrl 调用 REST Web Service 263
  - 7.3.4 在 GUI 外使用 `AsyncTask` 执行网络请求 263
  - 7.3.5 `ListView`, `ArrayAdapter` 和 `ViewHolder` 模式 263
  - 7.3.6 `FloatingActionButton` 264
  - 7.3.7 `TextInputLayout` 265
  - 7.3.8 `Snackbar` 265
- 7.4 构建 App 和资源文件 265
  - 7.4.1 创建项目 265
  - 7.4.2 `AndroidManifest.xml` 265
  - 7.4.3 `strings.xml` 266
  - 7.4.4 `colors.xml` 266
  - 7.4.5 `activity_main.xml` 266
  - 7.4.6 `content_main.xml` 267
  - 7.4.7 `list_item.xml` 268
- 7.5 Weather 类 269
  - 7.5.1 `package` 语句, `import` 和实例变量 270
  - 7.5.2 构造函数 270
  - 7.5.3 方法 `convertTimeStamp` 271
- 7.6 `WeatherArrayAdapter` 类 272
  - 7.6.1 `package` 语句和 `import` 272
  - 7.6.2 嵌套 `ViewHolder` 273
  - 7.6.3 实例变量和构造函数 273
  - 7.6.4 重写的 `Adapter` 方法 `getView` 273
  - 7.6.5 在独立线程中下载图片的 `AsyncTask` 子类 273
- 7.7 `MainActivity` 类 277
  - 7.7.1 `package` 语句和 `import` 277
  - 7.7.2 实例变量 278
  - 7.7.3 重写的 `Activity` 方法 `onCreate` 279
  - 7.7.4 方法 `dismissKeyboard` 和 `createURL` 280
  - 7.7.5 调用 Web Service 的 `AsyncTask` 子类 281
  - 7.7.6 方法 `convertJSONToArray` 283
- 7.8 总结 284

`SharedPreferences.Editor`, Implicit Intent, `Intent Chooser`, `RecyclerView.View`, `RecyclerView.Adapter`, `RecyclerView.ViewHolder`, `ItemDecoration`

- 8.1 简介 287
- 8.2 运行 App 288
  - 8.2.1 添加收藏搜索 288
  - 8.2.2 查看 Twitter 搜索结果 291
  - 8.2.3 编辑搜索 291
  - 8.2.4 分享搜索 293
  - 8.2.5 删除搜索 294
  - 8.2.6 滚动查看保存的搜索 295
- 8.3 技术概览 295
  - 8.3.1 在 `SharedPreferences` 文件中存储键值数据 295
  - 8.3.2 隐式 `Intent` 和 `Intent Chooser` 296
  - 8.3.3 `RecyclerView` 296
  - 8.3.4 `RecyclerView.Adapter` 和 `RecyclerView.Holder` 297
  - 8.3.5 `RecyclerView.ItemDecoration` 297
  - 8.3.6 在 `AlertDialog` 中显示选项列表 297
- 8.4 构建 App 的 GUI 和资源文件 297
  - 8.4.1 创建项目 298
  - 8.4.2 `AndroidManifest.xml` 298
  - 8.4.3 添加 `RecyclerView` 库 298
  - 8.4.4 `colors.xml` 299
  - 8.4.5 `arrays.xml` 299
  - 8.4.6 `dims.xml` 299
  - 8.4.7 添加保存图标 300
  - 8.4.8 `activity_main.xml` 300
  - 8.4.9 `content_main.xml` 300
  - 8.4.11 `RecyclerView` 列表布局: `List1_item.xml` 302
- 8.5 `MainActivity` 类 303
  - 8.5.1 `package` 和 `import` 语句 304
  - 8.5.2 `MainActivity` 字段 304
  - 8.5.3 重写的 `Activity` Handler 和方法 `onCreate` 305
  - 8.5.4 `TextWatcher` Handler 和方法 `updateSafeFAB` 305
  - 8.5.5 布局 307
  - 8.5.6 布局 308
  - 8.5.7 实现 `View.OnClickListener` 的匿名类显示搜索 309
  - 8.5.8 实现 `View.OnClickListener` 的匿名类编辑或删除 311
  - 8.5.9 方法 313
  - 8.5.10 方法 314
- 8.6 `Searches` 子类 315
  - 8.6.1 `package` 语句、`import` 和实例变量 315
  - 8.6.2 嵌套 `ViewHolder` 子类 316
  - 8.6.3 方法 317
- 8.7 `ItemDecoration` 子类 318
- 8.8 关于新开发平台的说明 320
- 8.9 总结 320

`FragmentTransactions` and the `Fragment Stack`, `SQLite`, `SQLiteOpenHelper`, `ContentProvider`, `ContentResolver`, `Loader`, `Manager`, `GUI Styles`

- 9.1 简介 324
- 9.2 运行通讯录 App 326
  - 9.2.1 添加联系 326
  - 9.2.2 查看联系人 327
  - 9.2.3 编辑联系人 327
  - 9.2.4 删除联系人 327
- 9.3 技术概览 328
  - 9.3.1 使用 `FragmentTransactions` 显示 328
  - 9.3.2 `Fragment` 与 `Activity` 之间的数据通信 329
  - 9.3.3 操作 `SQLite` 数据库 329
  - 9.3.4 `ContentProviders` 和 `ContentResolvers` 329
  - 9.3.5 `Loader` 和 `Manager`—异步数据库访问 330
  - 9.3.6 定义样式并应用到 GUI 组件 331
  - 9.3.7 指定 `TextView` 背景 331
- 9.4 构建 GUI 和资源文件 331
  - 9.4.1 创建项目 331
  - 9.4.2 创建类 333
  - 9.4.3 添加 App 图标 333
  - 9.4.4 `strings.xml` 333
  - 9.4.5 `styles.xml` 334
  - 9.4.6 `textview_border.xml` 335
  - 9.4.7 `MainActivity` 布局 335
  - 9.4.8 `ContactsFragment` 布局 337
  - 9.4.9 `DetailFragment` 布局 338
  - 9.4.10 `AddEditFragment` 布局 339
  - 9.4.11 `DetailFragment` 菜单 341
- 9.5 本章类概览 341
- 9.6 `DatabaseDescription` 类 342
  - 9.6.1 静态字段 342
  - 9.6.2 嵌套类 343
- 9.7 `AddressBookHelper` 类 344
- 9.8 `AddressBookContentProvider` 类 346
  - 9.8.1 `AddressBookContentProvider` 字段 346
  - 9.8.2 重写的方法 `onCreate` 和 `getType` 347
  - 9.8.3 重写的方法 `query` 348
  - 9.8.4 重写的方法 `insert` 350
  - 9.8.5 重写的方法 `update` 352
  - 9.8.6 重写的方法 `delete` 353
- 9.9 `MainActivity` 类 354
  - 9.9.1 父类、实现的接口和字段 354
  - 9.9.2 重写的 `Activity` 方法 `onCreate` 355
  - 9.9.3 `ContactsFragment.ContactsFragmentListener` 方法 356
  - 9.9.4 方法 `displayContact` 357
  - 9.9.5 方法 `displayAddFragment` 358
  - 9.9.6 `DetailFragment.DetailFragmentListener` 方法 358
  - 9.9.7 `AddEditFragment.AddEditEventListener` 方法 359
- 9.10 `ContactsFragment` 类 360
  - 9.10.1 超类与实现的接口 360
  - 9.10.2 `ContactsFragmentListener` 360
  - 9.10.3 字段 361
  - 9.10.4 覆盖的 `Fragment` 方法 `onCreate` 363
  - 9.10.5 覆盖的 `Fragment` 方法 `onAttach` 和 `de onDetach` 363
  - 9.10.6 覆盖的 `Fragment` 方法 `onDestroyCreated` 363
  - 9.10.7 方法 `updateContactList` 364
  - 9.10.8 `LoaderManager.LoaderCallbacks<Cursor>` 364
- 9.11 `ContactsAdapter` 类 365
- 9.12 `AddFragment` 类 368
  - 9.12.1 超类与实现的接口 368
  - 9.12.2 `AddEditEventListener` 369
  - 9.12.3 字段 369
  - 9.12.4 覆盖的 `Fragment` 方法 `onAttach`, 和 `onDetach` `onCreate` 370
  - 9.12.5 `TextWatcher` `onChangedListener` 和 `updateTextChanged` 372
  - 9.12.6 `OnClickListener` `saveButtonClicked` 和 `saveButton` 373
  - 9.12.7 `LoaderManager.LoaderCallbacks<Cursor>` 方法 374
- 9.13 `DetailFragment` 类 376
  - 9.13.1 超类与实现的接口 376
  - 9.13.2 `DetailFragmentListener` 377
  - 9.13.3 字段 377
  - 9.13.4 覆盖的方法 `onAttach`, 和 `on` `onCreate` 378
  - 9.13.5 覆盖的方法 `onOptionsMenu` 和 `onItemSelected` 379
  - 9.13.6 方法 `deleteContact` 和 `DialogFragment` `confirmDelete` 380
  - 9.13.7 `LoaderManager.LoaderCallbacks<Cursor>` 方法 381
- 9.14 总结 382

# 10 Google 与应用业务问题 384

- 10.1 引言 385
- 10.2 为发布准备您的应用 385
  - 10.2.1 测试您的应用 386
  - 10.2.2 用户许可协议 386
  - 10.2.3 图标与标签 387
  - 10.2.4 应用版本控制 387
  - 10.2.5 访问付费应用的授权 388
  - 10.2.6 代码混混淆 388
  - 10.2.7 获取用于数字签名的应用私钥 388
  - 10.2.8 特色图片与截图 388
  - 10.2.9 推广应用视频 390
- 10.3 应用定价：免费或付费 390
  - 10.3.1 付费应用 391
  - 10.3.2 免费应用 391
- 10.4 通过应用内广告实现应用变现 392
- 10.5 应用变现：使用应用内购买销售虚拟商品 393
- 10.6 在 Google Play 注册 394
- 10.7 设置 Google 支付商户账户 395
- 10.8 将应用上传到 Google Play 395
- 10.9 在应用内启动 Play Store 397
- 10.10 在 Google Play 中管理您的应用 398
- 10.11 其他 Android 应用市场 398
- 10.12 其它移动应用平台及您的应用迁移 398
- 10.13 营销您的应用 399
- 10.14 总结 403

405

本页特意留白

# 前言

欢迎来到 Android 软件开发包 (SDK)、Java™ 编程语言以及快速演变的 Android Studio 集成开发环境 (IDE) 智能手机和平电脑应用开发的动态世界。我们介绍的许多 Android 技术也适用于 Android 和 TV 应用开发，读完本章后，您将准备好为这些平台研究应用开发。



《面向程序员的 Android：一种应用驱动的方法》为专业开发者提供了前端的移动计算技术。在我们的应用驱动方法中，我们介绍的是完成应用的概念，而不是代码片段。第 2-9 章每章介绍一个应用，并介绍构建该应用所用技术的概述。所有源代码均可在获取：

`http://www.deitel.com/books/Android3`

我们建议您在阅读章节时，在 IDE 中检查每个应用的源码。Android 开发者的机会是多多的。Android 设备和应用的销量呈指数级增长。第一代 Android 手机于 2008 年 10 月发布。根据 IDC 的数据，在 2015 年之前的三个月里，Android 拥有 78% 的市场份额。

# 目标读者

我们假设您是 Java 程序员并具有面向对象的编程经验。如果您不熟悉 Android，可以快速掌握以下教程：

- `http://www.ibm.com/developerworks/`
- `http://www.w3schools.com/`
- `http://bit.ly/newto`

如果您想学习 Java，可以查看我们的订阅内容或购买的出版物：

- `http://www.deitel.com/books`
- `http://www.deitel.com/LiveLessons`
- `http://www.deitel.com/Udemy`
- `http://www.deitel.com/Safari.com`

# 前言

欢迎来到 Android 软件开发包 (SDK)、Java™ 编程语言以及快速演变的 Android Studio 集成开发环境 (IDE) 智能手机和平电脑应用开发的动态世界。我们介绍的许多 Android 技术也适用于 Android 和 TV 应用开发，读完本章后，您将准备好为这些平台研究应用开发。

《面向程序员的 Android：一种应用驱动的方法》为专业开发者提供了前端的移动计算技术。在我们的应用驱动方法中，我们介绍的是完成应用的概念，而不是代码片段。第 2-9 章每章介绍一个应用，并介绍构建该应用所用技术的概述。所有源代码均可在获取：

`http://www.deitel.com/books/Android3`

我们建议您在阅读章节时，在 IDE 中检查每个应用的源码。Android 开发者的机会是多多的。Android 设备和应用的销量呈指数级增长。第一代 Android 手机于 2008 年 10 月发布。根据 IDC 的数据，在 2015 年之前的三个月里，Android 拥有 78% 的市场份额。

# 目标读者

我们假设您是 Java 程序员并具有面向对象的编程经验。如果您不熟悉 Android，可以快速掌握以下教程：

- `http://www.ibm.com/developerworks/`
- `http://www.w3schools.com/`
- `http://bit.ly/newto`

如果您想学习 Java，可以查看我们的订阅内容或购买的出版物：

- `http://www.deitel.com/books`
- `http://www.deitel.com/LiveLessons`
- `http://www.deitel.com/Udemy`
- `http://www.deitel.com/Safari.com`

## xxiv 前言

此外，在 2015 年 Google I/O 开发者大会上，Google 引入了 Android Design Support Library

```
http://android-developers.blogspot.com/2015/05/android-design-support-library.html
```

在 Android 2.1 及更高版本中使用 material design。Material design 支持也已内置在 Android Studio 的应用模板中。

REST Web 服务与 JSON。第 7 章介绍了天气预报器应用，该应用演示了如何使用表述状态转移（REST）网络服务——在本例中是来自 OpenWeatherMap 的 6 天天气预报——这是一种流行的基于文本的数据交换格式，将对象表示为键值对形式的数据。该应用还使用`org.json`包来处理服务的响应。

Android 6.0 权限。Android 6.0 采用了全新的权限模型，旨在提供更好的用户体验。在 Android 6.0 之前，用户需要在安装时提前授予应用可能需要的所有权限，这通常会阻碍用户安装应用。使用新模型后，应用在安装时不会请求任何权限。用户在第一次使用相应功能时，才会被要求授予权限。第 5 章介绍了新的权限模型，并使用它请求用户许可将图像存储在设备的外部存储器中。

片段（Fragments）。从第 4 章开始，我们使用片段来创建和管理每个应用 GUI 的部分。你可以组合片段来创建利用平板电脑尺寸的用户界面。你还可以交换片段以使你的 GUI 更加动态，正如你在第 9 章中将看到的。

View-Holder 模式、ListView 和 RecyclerView。第 7 至 9 章中的应用都显示了可滚动的数据列表。第 7 章在`ListView`中显示数据，并引入了 view-holder 模式，该模式通过复用滚动出屏幕的 UI 组件来提高滚动性能。对于`ListView`，建议使用 view-holder 模式。第 8 章和第 9 章在更灵活、高效的`RecyclerView`中显示数据列表，该组件要求使用 view-holder 模式。

打印。我们演示了 Android 打印框架中的`PrintAdapter`（第 5 章），用于从应用进行打印。`PrintAdapter`提供了一个选择打印机的用户界面、一个确定给定设备提供打印服务的方法以及一个打印`Bitmap`的方法。`PrintAdapter`是 Android Support Library 的一部分。

浸式模式。屏幕顶部的状态栏和底部的菜单按钮可以隐藏，允许你的应用填充更多屏幕。用户可以通过从屏幕顶部向下滑动访问状态栏，通过从底部向上滑动访问带有返回键、主页和最近任务键的系统栏。

在 Android、平板电脑和 Android 模拟器上进行测试。为了获得最佳开发体验和结果，你应该在真实的智能手机和平电脑上测试你的应用。你仍然可以使用 Android 模拟器（参见“开始之前”部分）获得有意义的体验；然而，它是处理器密集型的，速度可能较慢，特别是对于具有大量活动部件的游戏。在第 1 章中，我们提到了一些模拟器不支持的 Android 特性。

## 教学特性

xxv

Cloud Test Lab 正在开发一个新的 Cloud Test Lab——这是一个在线网站，可以在各种设备、设备方向、本地化、口语语言和网络条件下测试你的应用。你将能够运行自动化测试并接收包含应用运行截图和视频的详细报告，以及帮助你发现问题和改进应用的错误日志。欲了解更多信息以及在 Cloud Test Lab 可用时接收通知：

```
http://developers.google.com/cloud-test-lab/
```

Android Wear 和 TV。Android Wear 运行在智能手表上。Android TV 直接运行在智能电视和连接到电视的媒体播放器上（通常通过 HDMI 通道）。我们介绍许多技术也适用于 Android Wear 和 Android TV 应用开发。Android SDK 提供了 Android Wear 和 Android TV 模拟器，因此即使你没有设备，也可以为这些平台测试你的应用。欲从开发者的角度了解更多关于这些技术，请访问：

```
http://developer.android.com/wear/index.html
```

Android Wear 以及

```
http://developer.android.com/tv/index.html
```

TV。

多媒体。应用使用了一系列 Android 多媒体功能，包括图形、逐帧动画和音频。

将应用上传到 Google Play。第 10 章“Google Play 与应用业务问题”讨论了 Google Play 以及如何设置可以出售应用的商家账户。你将学习如何为提交到 Google Play 做准备，寻找应用定价的技巧，并寻找通过应用内广告和应用内商品销售进行变现的资源。你还将找到营销应用的资源。第 10 章可以在第 1 章之后阅读。

## 教学特性

语法高亮。为了可读性，我们对代码进行了语法高亮，类似于 Android Studio 使用语法高亮。我们的语法高亮规范如下：

```
注释像这样
关键字像这样
常量和字面量像这（样
所有其他代码像这样
```

代码高亮。我们通过黄色矩形将每个程序中的关键部分括起来，以强调重点。

使用字体强调。我们使用了不同的字体约定：

- 关键术语的不同出现处显示为**深红色**，方便引用。
- 屏幕上的 IDE 组件显示为**加粗 Helvetica**（例如，File 菜单）。
- 程序源代码显示为 Lucida 字体（例如`int x = 5`）。

## xxvi 前言

在本书中，你将结合视觉化编程（点选、拖放）和编写代码来创建 GUI。当我们引用程序代码中的元素与显示的 GUI 元素时，会使用不同的字体：

- 当我们在程序中引用组件时，使用 Lucida 字体显示其类和名称。
- 当我们引用 IDE 中的 GUI 组件时，使用加粗 Helvetica 字体显示其文本——例如，“File 菜单”或“Run 按钮”。

使用字符。我们使用`<字符>`表示从我们的菜单中选择项目。例如，我们使用*File* > *New* 表示你应该从*File*菜单选择*New*。

源码。本书的所有源代码都可以下载

```
http://www.deitel.com/AndroidFP3
```

文档。开发 Android 应用所需的所有 Android 文档位于

```
http://developer.android.com
```

Android Studio 概述位于

```
http://developer.android.com/tools/studio/index.html
```

章节目标。每个章节开头都列出了学习目标。

图形。大量的表格、代码列表和截图。

软件工程。我们强调清晰度和性能，专注于构建良好的面向对象的软件。

索引。我们包含了详尽的索引供参考。每个关键术语定义处的页码标记为深红色。

## 与开源应用协作

在线免费开源 Android 应用是学习 Android 应用开发的极佳资源。我们鼓励你下载开源应用并阅读其源代码以理解它们的工作原理。

注意：开源许可的条款差异很大。有些允许你出于任何目的自由使用应用源码，而另一些则规定代码仅供个人使用——不可用于创建出售或公开的应用。请务必仔细阅读许可协议。如果你希望基于开源应用创建商业应用，应考虑让知识产权律师阅读许可；因为这些律师的收费非常高昂。

我们的*Android 6 App-Development Fundamentals LiveVideos*将向你展示使用 Android 6 和 Java™ 构建稳健、强大的 Android 应用所需的全部知识。

编程语言和 Android Studio。书中包含了约 16–20 小时的培训，与《Android 6 for Programmers: An App-Driven Approach》同步。有关 Deitel LiveLessons 视频文章的更多信息，请访问：

```
http://www.deitel.com/livelessons
```

或通过`deitel@deitel.com`与我们联系。如果您订阅了 SafariBooksOnline.com，也可以访问我们的 LiveLessons 视频。如需免费试用 10 天，请在注册：

```
http://www.safaribooksonline.com/register
```

# 加入 Deitel & Associates, Inc. 社交社区

为了接收有关我们的出版物、新及更新的应用程序、在线资源中心、讲师指导的现场培训课程等的更新信息，请关注以下社交平台上的 Deitel 社交社区：

- Facebook®—`http://facebook.com/DeitelFan`
- LinkedIn®—`http://bit.ly/DeitelLinkedIn`
- Twitter™—`http://twitter.com/deitel`
- Google+—`http://google.com/+DeitelFan`
- YouTube—`http://youtube.com/DeitelTV`

并订阅 Deitel® Buzz Online 时事通讯：

```
http://www.deitel.com/newsletter/subscribe.html
```

# 联系作者

我们诚挚感谢您的意见、批评、修正和改进建议。请将所有问题和其他信函发送至：

```
deitel@deitel.com
```

随着 Android 的演进，我们将及时通过以下网址发布帖子更正和说明：

```
http://www.deitel.com/books/AndroidFP3
```

以及在 Facebook、LinkedIn、Twitter、Google+ 和 Deitel® Buzz Online 上进行回复。访问`http://www.deitel.com`可以：

- 下载代码示例
- 查看不断增长的在线编程资源中心列表
- 接收此书的更新，请订阅免费的 Deitel® Buzz Online 电子邮件通讯：`http://www.deitel.com/newsletter/subscribe.html`
- 接收有关我们在全球客户现场提供的 DiveInto® 系列（由讲师指导的编程语言课程）的信息。

# 致谢

感谢 Barbara Deitel 为此项目投入了大量时间——她创建了我们所有的 Android 资源中心，并耐心地研究了数百个技术细节。

# xxviii 前言

我们感谢我们的朋友兼专业同事、Pearson Technology Group 总编辑 Mark L. Taub 所付出的努力和 20 年的导师指导。Mark 和他的团队出版了我们所有的专业书籍和 LiveLessons 视频产品。Michelle Housley 招募了 Android 社区的成员来评审手稿。我们选择了封面艺术，并由 Chuti Prasersith 设计了封面。John Fuller 负责我们所有 Detail 系列书籍的制作。

我们感谢 Michael Morgan，他曾是我们 Deitel & Associates, Inc. 的同事，现在是 PPPHOTO 的 Android 开发人员，他合著了本书的第一部分以及我们的《iPhone for Programmers: An App-Driven Approach》。Michael 是一位极具才华横溢的开发者。

最后，感谢 Deitel & Associates, Inc. 的总裁 Abbey。Abbey 是克利姆姆森大学（Clemson University）管理学院的毕业生，并在该校获得了工业管理学学士学位（B.S. in Industrial Management）。Abbey 在 17 年的时间里管理着 Deitel & Associates, Inc. 的业务运营，在此期间她还合著了多部出版物，包括之前版本的第 1 章和第 10 章。

我们感谢以下评审过本书（或其之前的版本）的专业人士和学者。他们仔细审查了文本和代码，并为改进提供了无数极具价值的建议：Paul Beuster（Mobile Developer Solutions 负责人）、Eric. Jordan（Driving Systems, LLC 首席）、Tony Cantrell（Georgia Northwestern Technical College）、Jan G. Clifton（独立承包商、Android 开发者、《Android User Interface: Implementing Material Design for Developers, 第二版》作者）、Daniel Galpin（Kellogg Company 开发者）、Jim Hathaway（Advocate 应用开发人员，《Intro to Android Application》作者）、Douglas Jones（Fullpower Technologies 高级工程师）、Charles Lask（Gaussian Community College）、Enrique Lopez-Madrid（Sext 首席架构师，阿拉巴马大学麦迪逊分校计算机科学教师）、Sebastian Nykholm（Mobiata Android 开发者）、Luis Ramirez（Reborn 首席工程师）、Roman “Zero” Schwartz（Open CIO）、Arijit Singapura（州立大学）、Donald Smith（Columbia College）、Jesus Ubaldo Quevedo-Torrero（威斯康星大学麦迪逊分校）、Dawn Wick（Southwestern Community College）以及 Frank Xu（Gannon University）。

好了，就是这些！《Android 6 for Programmers: An App-Driven Approach》制作完成了，我们希望你们在使用 Android 6 和 Android Studio 开发 Android 应用时像我们编写它一样愉快！

Paul Deitel

Harvey Deitel

# 关于作者

Paul Deitel 是 Deitel & Associates, Inc. 的首席执行官兼首席官，麻省理工学院（MIT）毕业生，学习过信息技术。他拥有 Java 认证程序员和 Java 认证开发者证书，并是 Oracle 冠军。Paul 还曾在 2012–2014 年被评为 Microsoft® C# 最宝贵专业人士（MVP）。

# 关于 Deitel & Associates, Inc.



`Deitel & Associates, Inc.`及其合著者`R. Harvey Deitel`向全球客户交付了数百门编程课程，客户包括思科、IBM、西门子、Sun Microsystems、戴尔、Fidelity、肯尼迪航天中心的 NASA、国家严重风暴实验室、白沙导弹场、Rogue Wave Software、波音、SunGuard、诺特尔、Puma、iRobot、Invisys 等。他们是全球畅销的编程语言教材/专业作者。

`Harvey Deitel`博士是`Deitel & Associates, Inc.`的董事长兼战略官，在计算机领域拥有 50 年经验。`Deitel`博士在 MIT 获得电气工程学士和硕士学位，在波士顿大学获得数学博士学位。他拥有丰富的教学经验，在 1991 年与儿子`Paul`创立`Deitel & Associates, Inc.`之前曾担任计算机系主任。`Deitel`的出版物获得了国际认可，并有德语、俄语、西班牙语、法语、波兰语、意大利语、简体中文、繁体中文、韩语、葡萄牙语、希腊语和乌尔都语译本。

`Alexander Wald`是`Deitel`的暑期实习生，他帮助我们将书籍和 Android 应用从使用 Eclipse 的 Android 4.3 和 4.4 转换为使用 Android Studio 的 Android 6。目前正在伍斯特理工学院（Worcester Polytechnic Institute）攻读计算机科学学士学位，并辅修电气工程。他从小对数学和科学感兴趣，并编写了约 9 年的代码。他的动力源于创造新的热情以及与他人分享知识的兴趣。

该公司由`Paul Deitel`和`Harvey Deitel`创立，是国际公认的权威和培训机构，专门从事 Android 和 iOS 应用开发、计算机编程、对象技术和互联网网络软件开发。公司的客户包括全球许多大型公司、政府机构、军方分支和学术机构。公司在全球客户现场提供由讲师指导的培训课程，涵盖主流编程语言和平台，包括 Android 应用开发、Swift™、Java、C++、C#、Visual Basic 以及网络编程。

欲了解更多关于 Deitel Dive-Into® 系列企业培训课程，请访问：

```
http://www.deitel.com/training
```

如需为贵机构申请全球范围内的实地讲师主导式培训提议，请发送电子邮件至`deitel@deitel.com`。

想要购买 Deitel 书籍和 LiveLessons 视频培训的个人可以通过`http://www.deitel.com`发布的链接进行购买。公司、政府、军事和学术机构的批量订单应直接向 Pearson 订购。了解更多信息，请访问：

```
http://www.informit.com/store/sales.aspx
```

# 开始之前

在本节中，你将为使用本书而配置你的计算机。Google 经常更新 Android™ 开发工具，因此在阅读本节之前，请检查书籍网站：

```
http://www.deitel.com/books/AndroidFP3
```

查看我们是否发布了“开始之前”章节的更新版本。

开发 Android 应用，你需要一个 Windows®、Linux® 或 Mac® OS X® 系统。要查看最新的操作系统要求，请访问

```
http://developer.android.com/sdk/index.html#Requirements
```

并滚动到“System Requirements”标题。我们使用以下软件开发了书中的应用：

- Java SE 7 Development Kit
- Android Studio 1.4 Integrated Development Environment (IDE)
- Android 6 (SDK 213)

你将在后续章节中了解如何获取这些每一项。

Android 需要第 7 版本 Java 开发包 (JDK 7)。Android Studio 支持 JDK 7 中的所有 Java 语言特性，但`try-with-resources`语句仅支持 API 级别为 19 及以上的 Android 平台。要下载 Windows、OS X 或 Linux 的 JDK 7，请访问：

```
http://www.oracle.com/technet/java/javase/downloads/archive-downloads-java77-521261.html
```

根据你的计算机硬件和操作系统选择 32 位或 64 位版本。务必遵循以下处的安装说明：

```
http://docs.oracle.com/javase/7/docs/webnotes/install/index.html
```

Android 不支持 Java 8 语言特性，例如 lambda 表达式、新接口特性和 Stream API。你可以使用 JDK 8（我们在开发本书应用时就是这么做的），前提是你在代码中没有使用 Java 8 语言特性。

## 安装 Android Studio

Google 的 Android Studio 带有最新的 Android 软件开发包 (SDK)，并基于 JetBrains 流行的 Java IDE IntelliJ® IDEA。要下载 Android Studio，请访问

```
http://developer.android.com/sdk/index.html
```

并点击 Download Android Studio 按钮。下载完成后，运行安装程序并按照屏幕上的指示完成安装。如果你之前安装过旧版本的 Android Studio，在安装结束时将显示“Complete installation”，并为你提供导入之前的设置的选项。在你写作时，Android Studio 1.4 是当前版本，Android Studio 1.5 已作为早期访问版可用。

## 使用早期访问发布版 (Early Access Releases)

在构建发布到 Google Play 或应用商店的应用时，最好使用最新版本的 Android Studio。如果你想尝试 Android 早期访问和测试版中的功能，Google 会在所谓的 Canary Channel（金丝雀通道）和 Beta Channel（测试通道）发布这些版本。你可以配置 Android Studio 从这些通道获取更新。要将 Android Studio 更新到最新的早期访问或测试版本：

1. 打开 Android Studio。
2. 在 Welcome to Android Studio 窗口中，点击 Configure（配置）。
3. 点击 Check for Update（检查更新）。
4. 在 Platform and Plugins Update 对话框中，点击 Updates 链接。
5. 在 Updates 对话框中，从“Automatically check for updates”右侧的下拉菜单中选择 Canary Channel 或 Beta Channel。
6. 点击 OK，然后点击 Close。
7. 再次点击 Check for Update。
8. IDE 将检查更新并告诉你是否有可应用的更新。
9. 点击 Update and Restart 以安装最新版本的 Android Studio。

如果你之前在 Android Studio 中打开过项目且没有关闭该项目，IDE 将跳过 Welcome to Android Studio 窗口并打开上项目。在这种情况下，你可以在 Mac 上通过 Android Studio > Check for Updates... 访问 Updates 对话框，或者在 Windows/Linux 上通过 Help > Check for Update... 访问。然后从上述的第 4 步继续。要查看 Google 提供的 Android Studio 技巧与提示，请访问：

```
http://developer.android.com/sdk/installing/studio-tips.html
```

## 配置 Android Studio 显示行号

默认情况下，Android Studio 不会在你编写的代码旁边显示行号。为了开启行号以便于跟进带行号的代码示例：

1. 打开 Android Studio。
2. 当 Welcome to Android Studio 窗口出现时，点击 Configure，然后选择 Settings（设置）打开 Default Settings 窗口。如果没有出现 Welcome to Android Studio 窗口，请使用 Mac 菜单选择 Android Studio > Preferences...，或者在 Windows/Linux 上选择 File > Other Settings > Default Settings...
3. 展开 Editor > General 节点并选择 Appearance（外观），确保选中了 Show line numbers（显示行号）并点击 OK。

## 配置 Android Studio 禁止代码折叠

默认情况下，Android Studio 的代码折叠功能已启用。此功能将代码行折叠为单行源代码，以便你关注代码的其他方面。例如，所有的 import 语句都会折叠为单行源代码，以便你关注代码的其他方面。

解压压缩包或右键点击并选择提取包内容的选项。请记住提取出的文件在系统中的位置，以便你稍后访问它们。

# 关于 Android Studio 和 Android SDK 的说明

如果你将我们的某个应用导入 Android Studio 且它无法编译，这可能是由于 Android Studio 或 Android 平台工具更新导致的。对于此类问题，请查看 Stack Overflow 上的 Android 问题问答：

```
http://stackoverflow.com/questions/tagged/android
```

以及 Google+ Android 开发社区：

```
http://bit.ly/GoogleAndroiddevelopment
```

或者给我们写信：

```
deitel@deitel.com
```

你现在已经安装了所有所需的软件，并下载了通过《Android 6 for Programmers: An App-Driven Approach》学习 Android 应用开发所需的代码示例，可以开始开发自己的应用了。祝使用愉快！

# Android 简介

![](img/8c2e5496308864b3b07ddbd4401c4f77_37_0.png)

### 目标

在本章中，你将了解：

- Android 和 Android SDK 的历史。
- 用于下载应用的 Google Play 商店。
- 本书中使用的帮助你创建 Android 应用的 Android 包。
- 对象化技术概念的快速回顾。
- Android 应用开发的关键软件，包括 Android SDK、Java SDK 和 Android Studio 集成开发环境 (IDE)。
- Android 文档。
- 在 Android Studio 中测试运行一个 Android 小费计算器应用。
- 优秀 Android 应用的特征。

# 第一章 Android 简介

### 提纲

- 1.1 简介
- 1.2 Android——全球领先的移动操作系统
- 1.3 Android 特性
- 1.4 Android 操作系统
  - 1.4.1 2.2 (Froyo)
  - 1.4.2 2.3 (Gingerbread)
  - 1.4.3 3.0 (Honeycomb)
  - 1.4.4 4.0.4 (Ice Cream Sandwich)
  - 1.4.5 4.1 (Jelly Bean)
  - 1.4.6 4.4 (KitKat)
  - 1.4.7 5.0 和 5.1 (Lollipop)
  - 1.4.8 6 (Marshmallow)
- 1.5 从 Google Play 下载应用
- 1.6 包
- 1.7 Android 开发包 (SDK)
- 1.8 面向对象编程：快速回顾
  - 1.8.1 作为对象的汽车
  - 1.8.2 方法与类
  - 1.8.3 实例化
  - 1.8.4 复用
  - 1.8.5 消息与方法调用
  - 1.8.6 属性和实例变量
  - 1.8.7 封装
  - 1.8.8 继承
- 1.9 面向对象分析与设计 (OAD)
- 1.9 在 Android 虚拟设备 (AVD) 中测试小费计算器应用
  - 1.9.1 在 Project Studio 中运行小费计算器应用
  - 1.9.2 创建虚拟设备 (AVD)
  - 1.9.3 在 Nexus 6 手机 Android 系统上运行小费计算器
  - 1.9.4 在 Android 设备上运行小费计算器应用
- 1.10 构建 Android 应用
- 1.11 Android 开发资源
- 1.12 总结

## 1.1 简介

欢迎来到 Android 开发！我们希望通过《Android 6 for Programmers: An Android App》的学习对你来说是一次充满启发性、挑战性、趣味性且有回报的体验。

本书面向 Java 编程。我们使用完整的可运行应用，因此如果你不懂 Java 但熟悉其他语言（如 C#、Objective-C/C++ 带有类库）的面向对象编程，你应该能够快速掌握这些内容，并在学习 Android 开发的同时学习大量的 Java 和 Java 风格的面向对象编程。

## 应用驱动的方法

我们采用应用驱动的方法——新功能将在完整的运行应用背景下进行讨论，每章一个应用。对于每个应用，我们都会进行测试运行。接下来，我们将回顾用于实现该应用的关键 Android Studio IDE（软件开发环境）和 Android SDK（软件开发包）技术。对于需要的部分，我们将演示如何使用 Android Studio 设计 GUI。然后，我们提供完整的源代码列表，使用行号、语法和颜色高亮来强调代码的关键部分。我们还会展示一个或多张运行应用的截图。然后，我们将进行详细的讲解，强调应用中引入的新编程概念。你可以从此处下载所有应用的源代码：

```
http://www.deitel.com/books/Android/
```

## 1.2 Android——全球领先的移动操作系统

Android 的销量正在快速增长，为 Android 开发者创造了巨大的机遇。

- 第一代 Android 手机于 2008 年 10 月发布。截至 2015 年 6 月，Android 占全球智能手机市场份额的 82.8%，而 Apple 为 13.9%，微软为 2.6%。
- Google Play 下载了数十亿应用，2014 年全球出货了超过十亿台 Android 设备。
- 根据《PC World》的数据，2014 年出货了约 2.3 亿台平板电脑，其中 67.3% 是 Android 平板电脑，相比之下，iOS 占比 27%。
- Android 设备包括智能手机、平板电脑、电子阅读器、游戏机、电视、车载信息系统等。某项报告显示，Android 平台预计到 2019 年将达到 990 亿美元。

## 1.3 Android 特性

**开放性与开源**

开发应用的优点之一是 Android 平台的开放性。该操作系统是开源且免费的。你可以通过以下地址查看 Android 源码并参与反馈 bug：

```
http://source.android.com
```

或者参与开源社区：

```
http://source.android.com/community/
```

你可以在以下处获取 Android 源码（见图 1.1）：

1. `http://source.android.com/` 报告 bug
2. `http://source.android.com/` 许可信息
3. `http://source.android.com/` 常见问题

Android 处处都是开源应用：

```
http://source.android.com/
```

| URL | 描述 |
|---|---|
| `http://en.wikipedia.org/wiki/List_of_open_source_applications` | 开源 Android 应用列表，按类别（游戏、通信、模拟器、媒体等）组织。 |
| `http://developer.android.com/tools/samples/index.html` | Google 提供的 Android 示例，演示各种 Android 功能。 |
| `http://github.com` | GitHub 允许你共享应用代码并贡献开源项目。 |
| `http://f-droid.org` | 数百个免费开源的 Android 应用。 |
| `http://www.openintents.org` | 用于增强能力的开源库。 |
| `http://www.stackoverflow.com` | Stack Overflow 是程序员的问答网站。用户可以对答案进行投票，最佳答案会排在最前面。 |

**图 1.1** 应用资源。

| 标题 | URL |
|---|---|
| 获取 Android 源码 | `http://source.android.com/source/downloading.html` |
| 许可协议 | `http://source.android.com/source/licenses.html` |
| 常见问题 | `http://source.android.com/source/faqs.html` |

**图 1.2** 开源 Android 操作系统的资源和代码。

与仅适用于 Apple 设备的私有系统 iOS 不同，Android 适用于数十种设备制造商（OEM）和全球众多运营商的设备。OEM 和运营商之间的激烈竞争使客户受益。

### Java



Android 应用使用 Java 开发——Java 是世界上最广泛使用的语言之一。Java 是 Android 平台的逻辑选择，因为它是强大、免费、开源并被数十亿开发者使用的。丰富的程序员可以使用 Google 的 Android API（应用程序编程接口）以及第三方 API 进行 Android 开发。

## 1.3 Android 特性

### 多点触控屏

Android 手机集成了手机的所有功能

### 手势

多点触控屏允许你通过涉及一次或多次触摸的手势来控制设备（如图 1.3 所示）。

| 手势名称 | 物理动作 | 用途 |
|---|---|---|
| 点击 (Touch) | 轻触屏幕一次。 | 打开应用，“按下”按钮或菜单项。 |
| 双击 (Double touch) | 轻触屏幕两次。 | 放大图片、Google 地图和地图。双击屏幕可恢复缩小。 |
| 长按 (Long press) | 触摸屏幕并保持手指在当前位置。 | 在视图中选择项目——例如，勾选列表中的项。 |
| 滑动 (Swipe) | 触摸屏幕，然后沿滑动方向移动手指并释放。 | 逐项翻阅序列（如照片）。滑动会自动停止在下一个项目。 |
| 拖拽 (Drag) | 触摸并跨越屏幕移动手指。 | 移动对象或图标，或滚动页面或列表。 |
| 双指合拢缩放 (Pinch zoom) | 将两个手指合拢，或将它们分开。 | 放大或缩小屏幕（例如调整文本和图片的大小）。 |

**图 1.3** | 一些常见的 Android 手势。

### 内置应用

Android 设备带有默认应用，这些应用根据设备、制造商或移动运营商的服务而异。一些常用的应用包括**电话、联系人、信息、浏览器、计算器、日历、闹钟和相**。

### Web 服务

**Web 服务**是存储在台计算机上的软件组件，可以通过互联网由另一台计算机上的应用（或软件组件）访问。通过 Web 服务，你可以创建**混合应用 (mashups)**，这让你能够通过快速*组合互补的* Web 服务（通常来自不同的组织以及可能的其他形式的信息源）来快速开发应用。例如，100 Destinations

```
http://www.100destinations.co.uk
```

将 Twitter 的照片和推文与 Google Maps 的地图功能相结合，允许你通过他人的照片探索世界各国。

# 第一章 Android 简介

Programmableweb

```
http://www.programmableweb.com/
```

提供了一个包含超过 14,000 个 API 和混合应用的目录，以及如何创建你混合应用的指南和示例代码。图 1.4 列出了一些流行的 Web 服务。我们将在第 7 章中使用 OpenWeatherMap.org 的 Web 服务。

| Web 服务来源 | 如何使用 |
|---|---|
| Google Maps | 地图服务 |
| Twitter | 微博博客 |
| YouTube | 视频搜索 |
| Facebook | 社交分享 |
| Instagram | 照片共享 |
| Foursquare | 移动签到 |
| LinkedIn | 商务社交网络 |
| Netflix | 电影拍卖 |
| eBay | 网上拍卖 |
| Wikipedia | 协作百科全书 |
| PayPal | 支付 |
| Amazon 电子商务 | 书籍和其他产品 |
| Salesforce.com | 客户关系管理 (CRM) |
| Skype | 互联网电话 |
| Microsoft Bing | 搜索 |
| Flickr | 照片共享 |
| Zillow | 房地产定价 |
| Yahoo Search | 搜索 |
| WeatherBug | 天气 |

**图 1.4** | 一些流行的 Web 服务 (http://www.programmableweb.com/category/all/apis)。

## 1.4 Android 操作系统

Android 操作系统由 Android, Inc. 开发，该公司于 2005 年被 Google 收购。开放手机设备联盟 (Open Handset Alliance™)

```
http://www.openhandsetalliance.com/oha/members.html
```

的目的是维护、演进和驱动移动技术的创新，并在降低成本的同时提升用户体验。

在本节中，我们将介绍 Android 操作系统的演变，展示其版本及其关键功能。Android 市场是碎片化的——许多设备仍在使用旧的 Android 版本——因此，作为开发者，了解每个版本中引入的特性对你很有帮助。

## 1.4 Android 操作系统

### Android 版本命名规范

每个 Android 版本都以甜点命名，并按字母顺序排列（图 1.5 所示）。

| Android 版本 | 名称 | Android 版本 | 名称 |
| --- | --- | --- | --- |
| Android 1.5 | Cupcake (纸杯蛋糕) | Android 4.0 | Ice Cream Sandwich (冰淇淋三明治) |
| Android 1.6 | Donut (甜圈) | Android 4.1–4.3 | Jelly Bean (果冻豆) |
| Android 2.0–2.1 | Eclair (泡芙蕾) | Android 4.4 | KitKat (巧克力棒) |
| Android 2.2 | Froyo (酸奶冰) | Android 5.0–5.1 | Lollipop (棒棒糖) |
| Android 2.3 | Gingerbread (姜饼) | Android 6.0 | Marshmallow (棉花糖) |
| Android 3.0–3.2 | Honeycomb (蜂蜜) | | |

**图 1.5** | Android 版本号及对应的名称。

### 1.4.1 Android 2.2 (Froyo)

**Android 2.2**（也称为 Froyo，于 2010 年 5 月发布）引入了外部存储，允许你将应用存储在外部设备而非内部内存中。它还引入了 **Android 云到设备 (2DM)**。云计算允许你根据需要增加或减少计算资源，比购买昂贵的硬件更具效益。有关 Android 2.2 特性的更多信息，请访问

```
http://developer.android.com/about/versions/android-2.2-highlights.html
```

### 1.4.2 Android 2.3 (Gingerbread)

**Android 2.3 (姜饼)** 于 2010 年底发布，增加了用户界面改进，具有重新设计的键盘、改进的导航和性能。它还增加了许多用于设备间通信的 API，针对残障用户的辅助功能（如视觉）、多媒体（如音频）以及游戏。

# 第一章 Android 简介

Android 2.3 最的新功能之一是支持近场通信 (NFC) —— 一可以在几厘米内实现设备间无线连接的技术。NFC 支持和功能因 Android 设备而异。NFC 可用于支付（例如将你的 NFC 设备靠近售卖机）、交换联系人和照片、配对设备和配件。更多 Android 2.3 开发者特性

```
http://developer.android.com/about/versions/android-2.3-highlights.html
```

### 1.4.3 Android 3.0 到 3.2 (Honeycomb)

Android 3.0 (蜂蜜) 包含了专门为大屏（如平板电脑）的用户界面改进，以及为了更高效输入而重新设计的键盘、吸引力强的 3D 用户界面，简化应用内的导航。新的 Android 3.0 开发者特性包括：

- 碎片 (fragments)：描述应用用户界面的部分，可以组合成一个或多个屏幕。
- 屏幕顶部的持久栏 (Action Bar)，为用户与应用交互提供选项。
- 为现有设计添加大屏布局的能力，以适应不同的屏幕尺寸。
- 视觉吸引人且功能更强大的用户界面，被称为“Holo”。
- 一种新的动画框架。
- 改进的图形和多媒体能力。
- 使用多处理器架构以增强性能。
- 增加蓝牙支持（例如允许应用确定是否连接了耳机或键盘）。
- 以及用于用户界面或图形的动画框架。

欲了解 Android 3.0 用户和开发者特性以及平台技术，请访问

```
http://developer.android.com/about/versions/android-3.0-highlights.html
```

### 1.4.4 Android 4.0 到 4.0.4 (Ice Cream Sandwich)

Android 4.0 (冰淇淋三明治) 于 2011 年发布，将 Android 2.3 (姜饼) 和 Android 3.0 (蜂蜜) 合并为适用于所有 Android 设备的单一操作系统。这让你能够在智能手机应用中整合 Honeycomb 此仅在平板电脑上可用的特性——“Holo”用户界面、新的启动器（用于自定义设备主屏幕和启动应用）等——并轻松地扩展你的应用以适应不同的设备。

## 1.4 Android 操作系统

（障碍）、社交网络等（见图 1.6）。欲查看 Android 4.0 API 的完整列表，请参阅：

```
http://developer.android.com/about/versions/android-4.0.html
```

| 特性 | 描述 |
|---|---|
| 面部检测 | 使用相机，兼容的设备可以确定用户眼球移动的位置并进行记录。相机还可以跟踪用户的眼球运动，允许你根据用户的视线位置创建更改视角的应用。 |
| 虚拟摄像机师 | 在拍摄多人的视频时，相机将自动聚焦在正在说话的人身上。 |
| Android 豆豆 | 使用 NFC，Android Bean 允许你触碰两个 Android 设备来共享内容（例如：联系人、照片、视频）。 |
| Wi-Fi Direct | Wi-Fi P2P* API 允许你使用 Wi-Fi 连接 Android 设备。设备无线通信的距离比蓝牙更远。 |
| 社交 API | 在获得用户许可的情况下，跨社交网络和应用访问并共享联系人信息。 |
| 日历 API | 在多个应用之间添加和共享事件，管理警报和参会者等。 |
| 无障碍 API | 使用新的 Android 文本转语音 API 增强视力障碍等残障人士的应用体验。触控探索模式允许视力障碍用户触摸屏幕的任何地方，并听到对触碰内容的语音描述。 |
| Android@Home 框架 | 使用 Android Home 框架创建控制用户家中家电的应用，如恒温器、灌溉系统、荧光灯等。 |
| 蓝牙健康设备 | 创建与体重秤、心率监测仪等蓝牙健康设备通信的应用。 |

图 1.6 某些冰淇淋三明治版本的开发者特性（http://developer.android.com/about/versions/android-4.0.html）。

### 1.4.5 Android 4.1–4.3 (Jelly Bean)

Android Jelly Bean 于 2012 年发布，侧重于许多幕后改进，例如更好的性能、无障碍支持、对国际用户的支持等。新功能包括：支持增强的蓝牙连接（蓝牙在 Android 4.3 中引入）、外部显示器、支持在单台平板电脑上使用多个用户、受限制的用户配置文件、改进安全性、外观增强（例如：可调整大小的应用部件、锁屏部件、可扩展通知）、优化的位置和传感器能力、更好的媒体能力（音频/视频），以及应用与屏幕之间更无缝的切换（图 1.7）。此外，Google 还引入了与 Android 平台版本独立开发的新 API：

# 第一章 Android 简介

* Google Cloud Messaging——一种跨平台解决方案，允许开发者向设备发送消息。
* Google Play Services——一组将 Google 功能整合到你的应用中的 API。

欲查看 Jelly Bean 特性列表，请参阅：

```
http://developer.android.com/about/versions/jelly-bean.html
```

| 特性 | 描述 |
|---|---|
| Android Bean | 增强版，除了 NFC 外还支持通过蓝牙进行通信。 |
| 锁屏部件 | 创建设备锁定时显示在用户屏幕上的部件，或修改现有的主屏幕部件，使其在设备锁屏时可见。 |
| 全景球 | 用于新的全景照片功能的 API，允许用户拍摄 360 度照片，类似于 Google 地图街视图使用的照片。 |
| 屏幕保护程序 (Daydreams) | Daydreams 是设备在底座或充电时激活的交互式屏幕保护程序。它们可以播放音频和视频并响应交互。 |
| 语言支持 | 新功能帮助你的应用触达国际用户，例如双向（从左到右或从右到左）、国际键盘、额外的键盘布局等。 |
| 开发者选项 | 新的趋势和调试功能帮助你改进应用，例如包含截图和设备状态信息的 bug 报告。 |

**图 1.7** Jelly Bean 特性（http://developer.android.com/about/versions/jelly-bean.html）。

### 1.4.6 Android 4.4 (KitKat)

**Android 4.4 KitKat** 于 2013 年 10 月发布，包含了多项性能改进，使其能够在所有 Android 设备上运行该操作系统，包括旧的、内存受限的设备（这些设备在发展中国家特别受欢迎）。

让更多用户更新到 KitKat 减少了市场上 Android 版本的“碎片化”，这对于开发者来说是一项挑战，以前他们必须设计应用运行在多个版本的操作系统上，或者通过针对特定的操作系统版本来限制其潜在市场。

Android KitKat 还包括了安全和无障碍增强、改进的图形和多媒体能力、内存使用分析工具等。图 1.8 列出了一些关键 KitKat 特性。欲查看完整列表，请参阅：

```
http://developer.android.com/about/versions/android-4-4-kitkat.html
```

## 1.4 Android 操作系统

| 特性 | 描述 |
| --- | --- |
| 沉浸模式 | 屏幕顶部的状态栏和底部的菜单按钮可以隐藏，允许你的应用填充更多屏幕。用户可以通过从屏幕顶部滑动访问状态栏，通过从底部滑动访问系统栏（带有返回键、主页键和最近应用键）。 |
| 打印框架 | 在你的应用中构建打印功能，包括通过 Wi-Fi 或云端访问可用打印机、选择页面大小以及指定要打印的页面。 |
| 存储访问框架 | 创建文档提供程序，允许用户浏览、创建和编辑文档。 |
| 短信 | 应用发送和接收短消息和多媒体消息。 |
| 过渡 | 新框架让创建动画变得更加简单。 |
| 屏幕录制 | 应用现在可以捕捉屏幕并共享内容。 |
| WebView | 支持 HTML5 和 CSS 等最新标准。 |
| 步器 | 新功能计算用户的步数。 |
| 主卡元素 (HCE) | HCE 允许应用执行安全交易。 |

**图 1.8** 某些 Kat 特性（http://developer.android.com/about/versions/kitkat.html）。

### 1.4.7 Android 5.0 和 5.1 (Lollipop)

Lollipop 发布于 2014 年——是手机和平电脑设计的重大更新。其他功能包括 Android 运行时、通知增强、网络能力、可穿戴设备、汽车、4K 显示支持、新的音频和视频能力、新的传感器支持、增强的无障碍等。图 1.9 列出了 Lollipop 特性。欲查看完整列表，请参阅：

```
http://developer.android.com/about/versions/lollipop.html
http://developer.android.com/about/versions/android-5.html
http://developer.android.com/about/versions/android-5.1.html
```

| 特性 | 描述 |
|---|---|
| Material 设计 | Google 为 Android 和网页设计的全新外观是核心新功能。Material 设计帮助你创建具有良好过渡、深度效果和自定义的应用。 |
| ART 运行时 | Google 用兼容 64 位的运行时替换了原始 Android 运行时，该运行时通过解释、提前编译 AOT 和即时编译 JIT 的组合来提高性能。 |
| 并发文档和活动 | Android 现在可以在最近屏幕上显示多个活动和文档。例如，如果用户在浏览器中打开了多个标签或在文本编辑应用中打开了多个文档，当用户点击最近应用时，每个标签或文档都会作为一个独立项目显示。 |
| 共享 | 共享功能有助于节省电池，包括新的任务调度，它可以在设备充电、连接网络（如使用 Wi-Fi 或移动数据）或空闲时执行异步任务。 |

**图 1.9** 某些 Android 特性（http://developer.android.com/about/versions/lollipop.html）。

### 1.4.8 Android 6.0 (Marshmallow)

**Android Marshmallow** 于 2015 年 9 月发布，是本文写作时的当前的 Android 版本。一些新功能包括：On Tap（在应用上下文中获取 Google 信息）、Doze 和待机（节省电池）、使应用更容易安装的权限、指纹认证、更好的数据保护、更好的文本选择、4K 显示支持、新的音频和视频能力、新的相机能力（闪电筒和图像处理 API）等。图 1.10 列出了一些 Marshmallow 特性。

| 特性 | 描述 |
|---|---|
| Doze | 使用软件和传感器，Android 判断设备何时静止一段时间（例如你晚上把它放在桌子上），并推迟消耗电池的后台进程。 |



**图 1.10** 某些 Android Marshmallow 特性（`http://developer.android.com/about/versions/marshmallow/android-6.0-changes.html`）。

## 1.5 从 Google Play 下载应用

| 特性 | 说明 |
| --- | --- |
| 应用待机模式 (App Standby) | 对于用户最近未交互过的应用，Android 会推迟后台网络活动。 |
| 触碰即搜 (Now on Tap) | 在任何应用内点击并按住主页键，Google Now 会检查屏幕内容并以卡片形式呈现相关信息。例如，在描述电影的短信息中，会显示一个包含电影信息的卡片。同样，在提到餐厅名称的短信息中，会显示一个包含评分和电话号码的卡片。 |
| 新权限模型 (New permissions model) | 在 Android 6.0 之前，用户需要在安装时授予应用未来可能需要的所有权限——这导致了许多人手动为某些应用授权。使用新模型后，应用仅在首次使用相应功能时才授予权限。 |
| 指纹认证 (Fingerprint authentication) | 对于带有指纹读取器的设备，应用现在可以使用指纹验证用户身份。 |
| 应用链接 (App linking) | 允许开发者将应用与其自己的域名和卡片链接关联起来，这些链接可以连接来自同一开发者的特定应用。 |
| 自动备份直接共享 (Automatic backup Direct share) | Android 可以自动备份和恢复应用。你可以在应用中定义直接目标，允许用户直接从你的应用通过其他应用共享数据。 |
| 语音交互 API (Voice Interaction API) | 允许应用响应语音交互。 |
| 蓝牙触笔支持 (Bluetooth stylus support) | 应用可以响应蓝牙触笔的压力敏感交互——例如，在绘图应用中，笔触碰屏幕可以渲染出粗的线条。 |

**图 1.10** 某些 Android 糖果版（Marshmallow）特性（`http://developer.android.com/about/versions/marshmallow/android-6.0-features.html`）。（部分 2/2）

在编写本文时，Google Play 中已有超过 160 万个应用，数量正在快速增长。图 1.11 列出了各种类别中的一些免费和付费应用。你可以通过安装在 Android 设备上的 Play Store 应用来下载应用。你也可以登录你的 Google Play 账户：

```
play.google.com
```

然后指定要安装应用的 Android 设备。应用将通过设备的 Wi-Fi 或 3G/4G 连接下载。在第 10 章“Google Play 和应用问题”中，我们将讨论其他应用商店、免费提供应用或收取费用等更多内容。`http://www.statista.com/statistics/26621/number-of-available-applications-in-the-google-play/`

# 第一章 Android 简介

| Google Play 类别 | 类别中的一些流行应用 |
| --- | --- |
| 书籍与参考 | WolframAlpha, Dictionary.com, Audible for Android, Kindle, Office, OfficeSuite, PayPal |
| 商务 | Snapchat, Pinterest, Instagram, Line, Google Classroom, Star Tracker, Math Tricks |
| 通讯 | Showtime, Discovery Channel, Credit Karma, Angry Birds, Fruit Ninja, Solitaire Runner, ViewPager, Color Counter |
| 教育 | Assistant, Horoscope, Food Network, Starbucks, Camera Recorder, Video, Baby Pro, FollowMyHealth, Spotify, Beats Music, BBC News, NPR News, Reuters, Google Camera, GoPro, Pencil Sketch, Microsoft Word, Google Docs, Groupon, Fancy, Home Depot, Meetup, Tumblr, NBA, ESPN, Antivirus, Clean Master, Translate, Uber, TrafficHUD, Speedometer, Google Earth, GasBuddy, AccuWeather, Weather Underground, Facebook, Tasker, Weather Timeline |

## 1.6 包

Android 使用一组包，即一组相关的、预定义的类。某些包是 Android 特有的，某些是 Java 特有的，有些是特定的。这些包允许你访问 OS 特性并整合到你的应用中。Android 包帮助你创建符合 Android 独特的视觉效果规范和风格指南的应用。图 1.12 列出了我们在书中讨论的许多包。要查看 Android 包的完整列表，请参：

```
http://developer.android.com/design/index.html
```

许多包来自 Android 支持库（Support libraries），允许你在运行在当前和旧平台上的应用中使用较新的 Android 特性。要需 Android 支持库关键特性的概述，请访问：`https://developer.android.com/tools/support-library/`

| 包名 | 说明 |
| --- | --- |
| `android.animation` | 用于属性动画的类。（第 4 和 5 章） |
| `android.app` | 包含 Android 模型中的高层类。（第 4 和 5 章） |
| `android.content` | 在设备上访问和发布数据。（第 6 章）。用于访问资源（如媒体、绘制资源等）的类，以及影响行为的设备配置信息。（第 4 章） |
| `android.database` | 处理提供者返回的数据。（第 9 章） |
| `android.database.sqlite` | 用于私有数据库的 SQLite 数据库管理。（第 9 章） |
| `android.graphics` | 用于绘制场景的图形工具。（第 4 和 5 章） |
| `android.graphics.drawable` | 用于显示元素的类（例如渐变等）。 |
| `android.hardware` | 设备硬件支持。（第 5 章） |
| `android.media` | 处理音频和视频接口的类。（第 6 章） |
| `android.net` | 网络访问。（第 8 章） |
| `android.os` | 操作系统。（第 3 章） |
| `android.preference` | 应用偏好设置。（第 4 章） |
| `android.provider` | Android 内容提供者。（第 5 章） |
| `android.support.design.widget` | Android 设计库，允许在当前和旧平台上运行增强。（第 7 章） |
| `android.support.v4.print` | v4 支持库的一部分，适用于 API 4 及以上版本；包含打印框架。（第 5 章） |
| `android.support.v7.app` | v7 支持库的一部分，适用于 API 7 及以上版本；包含应用组件，如操作栏。（第 7 章） |
| `android.support.v7.widget` | v7 支持库的一部分，适用于 API 7 及以上版本；包含 GUI 组件和布局。（第 7 章） |

| 包名 | 说明 |
| --- | --- |
| `android.text` | 渲染和跟踪文本。（第 3 章） |
| `android.util` | 工具方法和 XML 工具。（第 4 章） |
| `android.widget` | 用于控件的用户界面类。（第 3 章） |
| `android.view` | 用于布局和用户交互的用户界面类。（第 4 章） |

**图 1.12** 本书使用的 Android 和 Java 包，按首次出现的章节列出。我们在第二卷中讨论额外的包。（部分 1/2）

## 1.7 Android 软件开发包 (SDK)

Android SDK 提供了构建应用所需的工具。它随 Android Studio 一起安装。详情请“开始之前”部分（序言之后），下载开发 Android 应用所需的软件，包括 Java SE 7 和 Android Studio。

### Android Studio

Android 在 2013 年 Google I/O 开发者大会上发布，现在是 Google 首选的 Android IDE。包含：

- GUI 设计器
- 支持语法高亮和行号的代码编辑器
- 自动缩进和自动补全（即类型提示）
- 调试器
- 版本控制系统
- 重构支持

以及更多。

### Android 模拟器

SDK 中的 Android 模拟器允许你在 Windows、Mac OS 或 Linux 内的模拟环境中运行 Android 应用，而无需 Android 设备。模拟器显示一个真实的 Android 用户界面窗口。如果你无法获得 Android 设备进行测试，这将非常有用。在将应用上传到 Google Play 之前，你可以在多种 Android 设备上测试。

在模拟器中运行应用之前，你需要创建一个虚拟设备（AVD），它定义了你想测试设备的特性，包括硬件、系统镜像、屏幕尺寸、数据存储等。如果你想

> ⁹ Android Studio 基于 JetBrains 的 IntelliJ Java IDE (`http://www.jetbrains.com/idea/`)

## 1.7 Android 软件开发包 (SDK)

为了在多个 Android 设备上测试您的应用，你需要分离 AVD 并模拟每个设备，或者使用 Google 的 Cloud Test Lab

```
https://developers.google.com/cloud-test-lab own
```

它允许你在许多不同的设备上进行测试。

你可以使用键盘和鼠标在模拟器上（图 1.13）重现大多数 Android 手势（图 1.14）和控制按钮。由于，模拟器上的手势比较有限，因为你的计算机可能无法处理所有的 Android 特性。例如，要在模拟器中测试应用，你需要创建模拟 GPS 读取数的功能。此外，你还可以模拟方向变化（切换到竖屏或横屏模式）；特定的加速度计（响应上下、左右、前后加速度的加速度计）需要模拟器中未内置的功能。然而，模拟器可以使用来自连接到计算机的 Android 设备的传感器数据，如下所示：

```
http://tools.android.com/tips/hardware-emulation
```

图 1.15 列出了模拟器上不可用的 Android 功能。你可以将应用安装在 Android 设备上来测试这些功能。你将在第 2 章的 Welcome 应用中开始创建 AVD 和模拟器以开发 Android 应用。

| 手势 | 模拟器操作 |
|---|---|
| 触摸 | 单次点击鼠标。在第 3 章的 Tip Calculator 应用中引入。 |
| 双击触摸 | 双击鼠标。 |
| 长按 | 点击并按住鼠标。在第 8 章的 Twitter® Searches 应用中引入。 |
| 拖动 | 点击、按住并拖动鼠标。在第 6 章的 Cannon 游戏中引入。 |
| 滑动 | 点击并按住鼠标，按滑动方向移动指针并释放鼠标。在第 7 章的 Weather Viewer 应用中引入。 |
| 捏合缩放 | 按住并保持 Ctrl（控制）键。将出现两个模拟触摸的控制控件。将圆移动到起始位置，点击并按住鼠标，拖动圆到结束位置。 |

**图 1.13** | 模拟器上的 Android 手势。

| 控制按钮 | 模拟器操作 |
|---|---|
| 返回键 | `Esc` |
| 通话/拨号按钮 | `F3` |
| 相机 | `Ctrl-KEYPAD_5`, `Ctrl-F3` |
| 挂断按钮 | `F4` |
| Home | Home 键 |
| 菜单（左软键） | `F2` 或 Page 键 |

**图 1.14** | 模拟器的 Android 硬件控制（更多控制，请访问 `http://developer.android.com/tools/help/emulator.html`）。（第一部分，共2部分）。

# 第一章 Android 简介

| 控制按钮 | 模拟器操作 |
| --- | --- |
| 电源 | `F7` |
| 搜索 | `F5` |
| (右软键) | `Shift-F2` 或 Page Down, Ctrl |
| 旋转到上一个方向 | `KEYPAD_7`, `Ctrl-F11` |
| 旋转到下一个方向 | `KEYPAD_9`, `Ctrl-F12` |
| 切换开关开关 | `F8` |
| 音量增大 | `KEYPAD_PLUS`, `Ctrl-F5` |
| 音量减小按钮 | `KEYPAD_MINUS`, `Ctrl-F6` |

> 图 1.14 | 模拟器中的 Android 控制（更多控制，请访问 `http://developer.android.com/tools/help/emulator.html`）（第二部分，共2部分）

## 模拟器上不可用的 Android 功能

- 打电话或接听电话（模拟器允许模拟通话）
- 蓝牙
- USB 连接
- 设备连接耳机
- 确定网络连接状态
- 确定电池电量或充电状态
- 确定 SD 卡的插入/拔出
- 对传感器的直接支持（加速度计、气压计、罗盘、光线传感器、距离传感器）——但是，可以使用来自通过 USB 连接的设备的传感器数据

> 图 1.15 | 模拟器上不可用的 Android 功能 (`http://developer.android.com/devices/emulator.html#limitations`)。

## 1.8 面向对象：复习

Android 使用面向对象的编程技术；在本节中，我们将回顾这些概念。构建正确的软件仍然是一个困难的目标，当需要现实且更强大的软件时，我们发现使用模块化的设计方法可以使软件开发更高效。开发者发现，面向对象的程序比早期的结构化编程更容易理解、正确和修改。

### 1.8.1 作为一个对象

为了帮助你理解对象及其内容，我们从一个简单的类比开始。假设你想通过按下加速板让汽车跑得更快。在这样做之前需要发生什么？在驾驶汽车之前，必须有人对其进行设计。汽车通常涉及类似于描述房屋设计的工程图纸。这些图纸包含了加速板的设计。踏板隐藏了实际的复杂机制，而方向盘隐藏了转向的机制。

### 1.8.2 方法与类

为了帮助你理解对象及其内容，我们从一个简单的类比开始。假设你想通过按下加速板让汽车跑得更快。在这样做之前需要发生什么？在驾驶汽车之前，必须有人对其进行设计。汽车通常涉及类似于描述房屋设计的工程图纸。这些图纸包含了加速板的设计。踏板隐藏了复杂的复杂机制，而方向盘隐藏了转向的机制。

### 1.8.3 实例化

为了帮助你理解对象及其内容，我们从一个简单的类比开始。假设你想通过按下加速板让汽车跑得更快。在这样做之前需要发生什么？在驾驶汽车之前，必须有人对其进行设计。汽车通常涉及类似于描述房屋设计的工程图纸。这些图纸包含了加速板的设计。踏板隐藏了复杂的复杂机制，而方向盘隐藏了转向的机制。

### 1.8.4 重用

为了帮助你理解对象及其内容，我们从一个简单的类比开始。假设你想通过按下加速板让汽车跑得更快。在这样做之前需要发生什么？在驾驶汽车之前，必须有人对其进行设计。汽车通常涉及类似于描述房屋设计的工程图纸。这些图纸包含了加速板的设计。踏板隐藏了复杂的复杂机制，而方向盘隐藏了转向的机制。

### 1.8.5 消息与调用

为了帮助你理解对象及其内容，我们从一个简单的类比开始。假设你想通过按下加速板让汽车跑得更快。在这样做之前需要发生什么？在驾驶汽车之前，必须有人对其进行设计。汽车通常涉及类似于描述房屋设计的工程图纸。这些图纸包含了加速板的设计。踏板隐藏了复杂的复杂机制，而方向盘隐藏了转向的机制。

### 1.8.6 属性与实例变量

为了帮助你理解对象及其内容，我们从一个简单的类比开始。假设你想通过按下加速板让汽车跑得更快。在这样做之前需要发生什么？在驾驶汽车之前，必须有人对其进行设计。汽车通常涉及类似于描述房屋设计的工程图纸。这些图纸包含了加速板的设计。踏板隐藏了复杂的复杂机制，而方向盘隐藏了转向的机制。

### 1.8.7 封装

为了帮助你理解对象及其内容，我们从一个简单的类比开始。假设你想通过按下加速板让汽车跑得更快。在这样做之前需要发生什么？在驾驶汽车之前，必须有人对其进行设计。汽车通常涉及类似于描述房屋设计的工程图纸。这些图纸包含了加速板的设计。踏板隐藏了复杂的复杂机制，而方向盘隐藏了转向的机制。

### 1.8.8 继承

为了帮助你理解对象及其内容，我们从一个简单的类比开始。假设你想通过按下加速板让汽车跑得更快。在这样做之前需要发生什么？在驾驶汽车之前，必须有人对其进行设计。汽车通常涉及类似于描述房屋设计的工程图纸。这些图纸包含了加速板的设计。踏板隐藏了复杂的复杂机制，而方向盘隐藏了转向的机制。

### 1.8.9 面向对象分析与设计 (OOAD)

你将如何为程序创建代码？也许，像许多程序员一样，你只需打开计算机并开始打字。这种方法对于小型程序可能有效，但如果你被要求为一家大型银行创建一个成千上万自动化机器的软件系统呢？或者假设你被要求加入一个由 100 名软件人员组成的团队，构建下一个美国空交通管制系统？对于如此庞大且复杂的系统，你不应该坐下来就开始写程序。

## 1.9 在 Android 虚拟设备 (AVD) 中测试小费计算器应用



使用这种称为面向对象编程（OOP）的语言进行编程，允许你将面向对象的设计实现为一个运行的系统。

在本节中，你将使用 Android 虚拟设备（如果你有的话，也可以使用实际的 Android 设备）来运行并与你的第一个 Android 应用程序进行交互。小费计算器（图 1.16(a)）——你将在第 3 章构建它——会计算并显示餐厅账单金额和总金额。通过点击数字键盘，该应用会根据你通过 `SeekBar` 指定的小费百分比计算并显示小费和总额——我们默认使用 15%（图 1.16(a)）。你可以通过移动 `SeekBar` 的滑块来选择 0–30% 范围内的小费百分比——这会更新小费百分比，并更新 `SeekBar` 下方 `View` 里的账单总额（图 1.16(b)）。

![](img/8c2e5496308864b3b07ddbd4401c4f77_57_0.png)

小费百分比

`TextView`

移动 `SeekBar` 滑块以设置小费百分比

点击软键盘上的数字以输入账单金额

图 1.16 应用首次加载时小费计算器的界面，以及用户输入账单金额并更改小费百分比后的界面。

### 1.9.1 在 Android Studio 中打开小费计算器应用项目

要打开小费计算器应用项目，请执行以下步骤：

1. **检查你的设置。** 如果你还没有这样做，请按照“开始之前”部分指定的步骤进行操作。

2. **打开 Android Studio。** 使用 Android Studio 快捷方式打开 IDE。在 Windows 上，快捷方式将出现在你的开始菜单或开始屏幕上。在 OS X 上，快捷方式位于你的“应用程序”文件夹中。对于 Linux，快捷方式的位置取决于你解压包含 Android Studio 文件的 ZIP 包的路径。当你第一次打开 Android Studio 时，会弹出“Welcome to Android Studio”窗口（图 1.17）。

![](img/8c2e5496308864b3b07ddbd4401c4f77_58_0.png)

图 1.17 | Welcome to Android Studio 窗口。

3. **打开小费计算器应用项目。** 在 Android Studio 中，当已经打开另一个项目时，你可以选择 *File* > *Open...* 导航到该项目的位置并打开它，在 **Welcome to Android Studio Window** 中（图 1.17）。导航到书籍的示例文件夹，选择 *TipCalculator* 文件夹并点击 *Choose*（Mac）或 *OK*（Windows/Linux）。Android Studio 会会在你创建的每个项目的项目设置中存储 Android SDK 路径。当你打开系统上的上的项目时，如果 SDK 的位置与我们的不同，你将收到一条错误消息。只需点击出现的错误对话框中的 *OK* 按钮，Android Studio 就会更新项目设置以使用你系统上的 SDK。此时，IDE 将打开项目并在 IDE 左侧的 Project 窗口（图 19）中显示其内容。如果 Project 窗口不可见，你可以通过选择 View > Tool Windows > Project 来查看它。

![](img/8c2e5496308864b3b07ddbd4401c4f77_59_0.png)

图 1.18 | Open File or Project 对话框。

![](img/8c2e5496308864b3b07ddbd4401c4f77_59_1.png)

图 1.19 | TipCalculator 项目的 Project 窗口。

### 1.9.2 创建 Android 虚拟设备 (AVDs)

正如我们在开始之前中所讨论的，你可以通过创建模拟每个设备的 Android 虚拟设备 (`AVDs`) 为多个 Android 设备测试应用。在本节中，你将为我们测试本书应用的设备创建 6 个 AVD——Google 的 Nexus 6 手机和 Nexus 9 平板。要创建这些 AVD，请执行以下步骤：

1. 在 Android Studio 中，选择 Tools > Android > AVD Manager 显示 Android 虚拟设备窗口（图 1.20）。

![](img/8c2e5496308864b3b07ddbd4401c4f77_60_0.png)

**图 1.20** | Android Device Manager 窗口。

2. 点击 Create Virtual Device...，打开 Virtual Device Configuration 窗口（图 1.21）。默认情况下选择了“Phone”类别，但你也可以为 Tablet、Wear 和 TV 创建 AVD。为了方便起见，Google 提供了许多预配置的设备，你可以使用它们来快速创建 AVD。选择 Nexus 6，然后点击 Next。

3. 为你想要创建的虚拟设备选择系统镜像——在这种情况下，选择 Android release Name 值为 Marshmallow、API Level 值为 23 (ABI binary information) 值为 x86 且 Target 为 android-6.0 (带有 Google APIs) 的镜像，然后点击 Next。这将创建一个同时也支持 Play Services APIs 的 Android 6。

4. 对于 API Name，选择 Nexus 6 API 23。

5. 点击 Virtual Configuration 窗口左下角的 Show Settings，然后滚动到高级设置底部并勾选 Enable Keyboard，然后点击 Finish 创建 AVD。

6. 重复步骤 1–6 以创建一个名为 Nexus 9 API 23 的 Nexus 9 平板——你将在第 2 章中使用此平板 AVD。

10. 在编写时，当你设置 Android Studio 时，它会配置一个模拟运行 Android 6.0 (Marshmallow) 的 Nexus 5 手机 AVD。你仍然需要执行第 1.9.2 节来创建测试所需的额外 AVD。

![](img/8c2e5496308864b3b07ddbd4401c4f77_61_0.png)

图 1.21 | Virtual Device Configuration 窗口。

如果你在上述步骤 5 中保留 Enable Keyboard 选项，你可以使用电脑键盘向运行在 AVD 中的应用输入数据。然而，这将防止屏幕上的软键盘显示。你创建的每个 AVD 在其 `config.ini` 文件中都有指定的许多其他选项。更准确地说，特定设备的硬件配置，你可以按照描述修改 `config.ini`：

```
http://developer.android.com/tools/avds
```

### 1.9 在 Android 虚拟设备上运行小费计算器应用

要在 Android 虚拟设备上运行小费计算器应用，请执行以下步骤：

1. **检查你的设置。** 如果你还没有这样做，请按照“开始之前”部分的步骤进行操作。

2. **在 Nexus 6 上启动应用。** 为了运行它，选择 Tools > Android > Virtual Device (图 1.22)。在 AVD 加载之前，点击 Launch 按钮。一个 AVD 需要一些时间来加载。在加载时，AVD 将显示锁屏。在实际设备上，你通过滑动手势来解锁 AVD。图 1.23 显示了解锁后的 AVD 界面。

![](img/8c2e5496308864b3b07ddbd4401c4f77_62_0.png)

图 1.22 | Android Device Manager 对话框。

![](img/8c2e5496308864b3b07ddbd4401c4f77_62_1.png)

图 1.23 | 解锁后的 Nexus 5 AVD 屏幕。

3. **启动小费计算器应用。** 在 Android Studio 中，选择 **Run > Run 'app'** 或点击工具栏上的 **Run 'app'** 按钮。这将显示 **Device Chooser** 对话框（图 1.24），并选择了当前运行的 AVD。点击 **OK** 在 AVD 中运行小费计算器（图 1.25）。作为在步骤 2 中打开 Android Device Manager 的替代方案，你可以点击工具栏上的 Run 'app' ▷ 并出现 Device Chooser。然后你可以使用模拟器选项来选择 AVD。

4. **探索 AVD。** AVD 屏幕底部有各种软按钮。你触摸这些按钮与应用和 Android OS 交互。在 AVD 中触摸是通过点击鼠标完成的。向下箭头 ▽ 会关闭键盘。当屏幕上没有键盘时，会出现返回按钮 ☐。点击此按钮将带你返回应用屏幕，或者如果你在当前应用屏幕，则返回上一个屏幕。主按钮 ⌂ 将你返回设备主屏幕。最近应用按钮 ◅ 允许你查看最近使用的应用，然后切换到这些应用。屏幕顶部是应用的标题栏。

![](img/8c2e5496308864b3b07ddbd4401c4f77_63_0.png)

**1.24 Device Chooser** 用于选择运行应用的 AVD 或设备。

# 28 第1章 Android 简介

![](img/8c2e5496308864b3b07ddbd4401c4f77_64_0.png)

**图 1.25** | 在 AVD 中运行的小费计算器应用。

出现在屏幕顶部的应用栏中。应用栏上的选项数量取决于设备的大小——我们将在第 5 章讨论这一点。

5. **输入账单总额。** 在数字键盘上输入输入账单总额 56.32。如果你输错了，请按键盘右下角的删除按钮来擦除最后输入的那个数字。尽管键盘上包含小数点，但应用程序被配置为你只能输入数字 0–9。每当你触碰一个数字或删除其中一个数字时，应用程序都会读取你目前输入的内容并将其转换为数字——如果你删除了所有数字，应用程序会在应用顶部的 `EditText` 中重新显示“输入金额”（Enter Amount）。应用程序将该值除以 100，并将结果显示在小费和总金额。我们使用 Android 针对特定区域的货币格式化功能来显示针对设备当前区域格式化的货币值。对于美国区域，当你输入数字 5、6 和 3 时，账单总额分别被成功显示为 $0.05、$0.56、$5.63 和 $56.32。

6. **选择自定义小费百分比。** `SeekBar` 允许你选择自定义百分比，`SeekBar` 下方右列的 `TextView` 显示对应的小费和总账单。向右拖动 `SeekBar`，自定义的百分比显示为 25%。当你拖动滑块时，`SeekBar` 会持续变化。在你释放滑块之前，应用程序会根据每个 `SeekBar` 值相应地更新小费百分比、小费金额和总账单。

图 1.26 显示了输入账单金额并选择小费百分比后的应用。

![](img/8c2e5496308864b3b07ddbd4401c4f77_65_0.png)

图 1.26 | 小费计算器输入账单金额并选择 25% 的小费。

1. **返回主屏幕。** 你可以通过点击 AVD 上的主页（ ）按钮返回 AVD 的主屏幕。

## Android 启动故障排除

如果你在执行 Android 虚拟设备（AVD）时遇到问题，可能是分配给 AVD 的计算机内存过多。要减少 AVD 的内存大小：

1. 在 Android Studio 中，选择 Tools > Android > AVD Manager 以打开 Android 虚拟设备窗口。

2. 你将看到正在运行的 AVD 列表。对于你想要重新配置的 AVD，点击 Actions 窗口中的铅笔图标（ ），

3. 在 Virtual Device Configuration 窗口中，点击 **Advanced Settings**（高级设置），并滚动到 **Memory and Storage**（内存和存储）部分。

4. 将 **RAM** 的值从默认的 1536 MB (1.5 GB) 减少到 1 GB。

5. 点击 **Finish** 并关闭 Android 虚拟设备管理器窗口。

如果你仍然无法运行 AVD，请重复这些步骤并将内存减少到 768 MB。

## 1.9.4 在 Android 设备上运行小费计算器应用

如果你有一个 Android 设备，可以轻松地在上面运行应用进行测试。

- **在设备上启用开发者选项。** 首先，你可能需要在设备上启用调试。要这样做，进入设备的 Settings（设置）应用，然后选择 Phone（手机或平板），找到 Build number（版本号，位于底部）并连续点击七次，直到看到“You are now a developer”（你现在是开发者）。这将启用设置中的 Developer options（开发者选项）。返回 Settings 应用，然后选择 Developer options 并确保勾选了 USB debugging（USB 调试）——这是你首次在设备上启用开发者选项时的默认设置。

- **连接你的设备。** 接下来，使用 USB 线将你的设备连接到计算机。如果你是 Windows 用户，回想一下“在之前”部分提到的，你需要为你的设备安装 USB 驱动程序。详情请参见以下网页：

```
http://developer.android.com/tools/device.html
http://developer.android.com/tools/extras/oem-usb.html
```

- **在 Android 设备上运行小费计算器。** 在 Android Studio 中，选择 Run > Run 'app' 或点击工具栏上的 Run 'app' 按钮。这将显示你在图124 中看到的 Device Chooser（设备选择器）对话框。从 AVD 列表中选择你的设备并点击 OK 在 AVD 或设备上运行小费计算器。

## 测试应用

为了宽泛了解书中将学到的功能，请查看第 2-9 章中的书籍应用。当你通过 Google Play 等商店进行分发构建时，你应该在尽可能多的实际设备上测试应用。记住，某些功能可以在实际设备上进行测试。如果你没有可用的 Android 设备，请创建 AVD 来模拟你想要运行的各种设备。Google Play 中有超过 160 万个应用，你如何创建一个让人们发现、下载、使用并推荐给他人的 Android 应用呢？什么让一个应用变得有趣、有趣、吸引人且持久？图 1.27 显示了优秀应用的特征。

### 优秀应用的特征

- **优秀的游戏**
  - 娱乐且有趣。
  - 具有挑战性。
  - 难度逐渐递进。
  - 显示你的得分和排行榜。
  - 具有互动性。
  - 具有社交性。
  - 能够不断更新。
  - 能够根据反馈进行改进。

- **实用工具**
  - 提供实用的功能。
  - 易于使用。
  - 能够根据需求进行定制。
  - 跨平台兼容性。
  - 提供离线化的信息。
  - 基于位置的服务。

- **通用特征**
  - 遵循 Android 规范。
  - 能够正常运行。
  - 及时修复 Bug。
  - 启动速度快。
  - 具有良好的响应性。

图 1.27 | 优秀应用的特征。（第 1 部分，共 2 部分）

## 1.11 Android 开发资源

1.28 列出了 Android 开发者网站的一些关键文档。当你深入研究 Android 开发时，可能会对工具、设计理念、安全等方面产生疑问。有几个 Android 开发者新闻组和论坛你可以在那里获取最新公告或提问（图 1.29）。图 1.30 列出了几个可以找到 Android 开发工具、视频和资源的网站。

| 标题 | URL |
| --- | --- |
| 应用组件 | http://developer.android.com/guide/components/index.html |
| 使用 Android 模拟器 | http://developer.android.com/tools/devices/emulator.html |
| 包索引 | http://developer.android.com/reference/packages.html |
| 类索引 | http://developer.android.com/reference/classes.html |

图 1.28 | Android 开发者的关键在线文档。（第 1 部分，共 2 部分）

## I.11 Android 开发资源

| 标题 | URL |
| --- | --- |
| Android 设计数据备份 | http://developer.android.com/design/index.html http://developer.android.com/guide/topics/data/backup.html |
| 安全提示 | http://developer.android.com/training/articles/security-tips.html |
| Android Studio 调试工具帮助 | http://developer.android.com/sdk/index.html http://developer.android.com/tools/debugging/index.html http://developer.android.com/tools/help/index.html |
| 性能提示 | http://developer.android.com/training/articles/performance-tips.html |
| 保持您的应用响应式 | http://developer.android.com/training/articles/performance-tips.html |
| 上架清单（针对 Google Play） | http://developer.android.com/distribute/tools/launch-checklist.html |
| 入门发布 | http://developer.android.com/distribute/googleplay/start.html |




# 管理应用内存

| 管理应用内存 | http://developer.android.com/training/articles/memory.html |
| --- | --- |
| Google 开发者分发协议 | http://play.google.com/about/developer-distribution-agreement.html |

**图 1.28** | Android 开发者的关键在线文档。（部分部分，共 2 部分）。

| 标题 | 订阅 | 描述 |
| --- | --- | --- |
| Android Discuss | 使用 Google Groups 订阅：`android-discuss`；通过邮件订阅：`android-discuss-subscribe@googlegroups.com` | 一个通用的 Android 讨论组，你可以在这里获得应用开发问题的解答。 |
| Stack Overflow | http://stackoverflow.com/questions/tagged/android | 使用此处理 Android 应用开发问题以及关于最佳实践问答。 |
| Android Developers | http://groups.google.com/forum/?groups#!forum/android-developers | 丰富的 Android 开发者使用此列表来排除应用故障、解决 UI 设计问题、性能问题等。 |
| Android Forums | http://www.androidforums.com | 向其他开发者提问、分享技巧并寻找针对特定 Android 设备的论坛。 |

**图 1.29** | Android 新闻组和论坛。

# 第 1 章 Android 简介

| Android 开发技巧、视频 | URL |
| --- | --- |
| Google 提供的 Android 示例和工具 | https://github.com/google (使用过滤器 'android') |
| 用于 Android 编程技巧和教程的 BrightHub 网站 | http://www.brighthub.com/mobile/google-android |
| Android 开发者博客 | http://android-developers.blogspot.com/ |
| HTC Android 开发者中心 | http://www.htdev.com/ |
| Motorola Android 开发网站 | http://developer.motorola.com/ |
| Stack Overflow 顶级用户 | http://stackoverflow.com/tags/android |
| Android Weekly | http://androidweekly.net/ |
| Chet 的博客 | http://graphics-geek.com/ |
| Romain Guy 的博客 | http://www.curious-creative.org/android/ |
| YouTube 上的 Android Developers Channel | http://www.youtube.com/user/androiddevelopers |
| Google I/O 2015 会议视频 | https://events.google.com/io2015/videos |

**图 1.30** | Android 开发技巧、视频和资源。

## 1.12 结语

本章简述了 Android 的历史并讨论了它的功能。我们提供了关键在线文档以及新闻组和论坛的链接，通过这些你可以与开发者社区联系并获得问题的解答。我们介绍了 Java、Android 和 Google 程序包，这些包使你能够在本书中使用其中的许多内容。我们还讨论了 Java 编程和 Android SDK。我们学习了 Android 方法以及如何在 Android 设备和模拟器上执行每种方法。我们对对象概念进行了快速复习，包括类、对象、属性、行为和继承。在第 2 章中，你将在 Android Studio 中构建你的第一个 Android 应用。该应用将播放文本和图像。你还将学习关于 Android 的无障碍辅助和国际化。

# 第 2 章 欢迎应用——深入 Android Studio：介绍视觉化 GUI 设计、布局、无障碍辅助和国际化

### 目标

在本章中，你将：

- 理解 Android Studio IDE 的基础知识，你将使用它来编写、测试和调试 Android 应用。
- 使用 IDE 创建新项目。
- 使用 IDE 的布局编辑器以视觉化方式（无需编程）设计图形用户界面（GUI）。
- 在 GUI 中显示文本和图像。
- 在 Android 模拟器中构建并启动应用。
- 通过指定用于 Android TalkBack 和触控探索特性的字符串，使应用对视障人士更具无障碍性。
- 支持国际化，使你的应用能够显示不同语言的本地化字符串。

### 提纲

- 2.1 引言
- 2.2 技术概述
  - 2.2 Android Studio
  - 2.2.1 `LinearLayout`, `TextView` 和 `ImageView`
  - 2.2.2 `EditText` 标记布局 (XML)
  - 2.2.3 无障碍辅助
  - 2.2.6 国际化
- 2.3 创建应用
  - 2.3.1 启动 Android Studio
  - 2.3.2 创建项目
  - 2.3.3 创建新对话框
  - 2.3.4 目标 Android 开发步骤
  - 2.3.5 向移动端添加 Activity
  - 2.3 自定义布局
  - 2.4 Android Studio 窗口
    - 2.4.1 项目窗口
    - 2.4.2 编辑器窗口
    - 2.4.3 组件树
    - 2.4.4 资源文件
    - 2.4.5 布局编辑器
    - 2.4.6 默认 GUI
    - 2.4.7 默认 GUI 的 XML
  - 2.5 使用布局编辑器构建应用
    - 2.5.1 向项目添加图像
    - 2.5.2 添加应用图标
    - 2.5.3 将布局更改 `LinearLayout`
    - 2.5.4 更改布局方向
    - 2.5.5 配置 `TextView` 属性
    - 2.5.6 设置文本大小：缩放像素与密度无关像素 (dp)
    - 2.5.7 设置 `textColor` 属性
    - 2.5.8 设置 `gravity` 属性
    - 2.5.9 设置 `layout:gravity` 属性
    - 2.5.10 设置 `layout:weight` 属性
    - 2.5.11 向中添加 `ImageView` 显示图像
    - 2.5.12 预览设计
- 2.6 运行欢迎应用
- 2.7 让你的应用具备无障碍性
- 2.8 你的应用国际化
  - 2.8.1 本地化
  - 2.8.2 按照文件夹组织资源
  - 2.8.3 向项目添加字符串翻译
  - 2.8.4 本地化设置
  - 2.8.5 在 AVD 上测试西班牙语应用
  - 2.8.6 在设备上测试西班牙语应用
  - 2.8.7 TalkBack 与本地化
  - 2.8.8 本地化清单
  - 2.8.9 专业翻译
- 2.9 结语

### 2.1 引言

在本章中，你将在 Android Studio 中构建你的第一个 Android 应用。该应用将播放文本和图像。你还将学习关于 Android 的无障碍辅助和国际化。在竖屏模式下，设备高度大于宽度：

- 在横屏模式下，宽度大于高度。

你将使用 Android Studio 通过拖拽式技术构建 GUI。你将直接编辑 XML。你将在 Android 模拟器和设备（如果你有）上运行应用。你将为应用的图像提供描述性文本，使其对视障人士更具无障碍性。Android 的触控探索功能允许用户触摸屏幕物品并让 TalkBack 读出相应的描述文本。我们将讨论如何测试这些功能，这些功能在 Android 设备上可用。

### 2.2 技术概述

Android 顶部系统栏显示时间、电量指示、蜂窝连接状态和发送通知的应用图标。

显示应用内容的客户端区域

`TextView` 组件

显示 Detail Logo 的 `ImageView` 组件

Android 底部系统栏显示（从左到右）返回、主页和最近任务按钮

**图 2.1** 在 Android 模拟器中运行的欢迎应用。

## 第 2 章 欢迎应用 (Welcome App)

此应用的文本显示在 `TextView` 中，图像显示在 `ImageView` 中。Android Studio 创建的默认 GUI 已经包含一个 `TextView`。你将相对于 `LinearLayout`（第 2.5.5 节）来修改其属性、文本、字体大小和颜色。你将使用编辑器的视图面板（图 2.11）将一个 `ImageView` 拖放到 GUI 上（第 2.5.11 节），然后配置其属性，包括图像源以及其在 `LinearLayout` 中的位置。

### 2.2.3 可扩展标记语言 (XML)

可扩展标记语言 (XML) 是一种表达 GUI 的自然方式。XML 是一种人类可读的文本，在 Android 境中，它可以帮助你指定要使用的布局和组件，以及它们的属性，如尺寸、位置、颜色、文本大小、外边距和内边距。Android Studio 解析 XML 以在编辑器中设计你的布局，并生成运行运行时 GUI 的 Java 代码。你还将使用 XML 特性来存储应用资源，例如字符串、数字和颜色（第 2.2.4 节）。

### 2.2.4 应用资源

一种良好的做法是将所有字符串、数值和其他值定义在位于 `res` 文件夹子目录下的 XML 资源中。在 2.5.5 中，你将创建资源（例如 `TextView` 上的文本）和测量（如尺寸）。对于 `TextView` 的字体颜色，你将使用 Google 的 Material Design 色板创建一个颜色资源：

```
http://www.google.com/design/spec/style/color.html
```

### 2.2.5 辅助功能

Android 提供了辅助功能来帮助某些残障人士使用设备。视觉 way可以使用 Android 的 TalkBack 让设备朗读屏幕文本，或通过触摸帮助他们理解视图的作用和内容。Android 的“触摸探索”允许用户触摸屏幕靠近物体的地方。第 2.7 节显示了如何启用这些功能并配置你应用的辅助功能。

### 2.2.6 国际化

Android 应用在全球范围内使用。为了让你的应用接触更多的用户，你应该考虑不同的地区和口语语言。配置你的应用使其能够针对不同地区进行定制，被称为本地化（localization）。针对特定地区自定义你的应用，第 2.8 节显示了如何为欢迎应用的 `TextView` 和 `ImageView` 的辅助字符串提供西班牙语文本，以及如何在配置为西班牙语的 Android 设备上测试该应用。

### 2.3 创建应用

本书的示例是使用编写时现行的 Android 6 SDK 开发的。本节显示了如何使用 Android Studio 创建新项目。我们在整本书中引入了 IDE 的其他功能。

### 2.3.1 启动 Android Studio

正如你在第 1.9 节中所做的那样，通过快捷方式打开 Android Studio：

IDE 显示欢迎窗口（图 1.17）或你上次打开的项目。

### 2.3.2 创建新项目

项目是一组相关文件，例如代码文件、资源文件和图像，它们共同构成一个应用。要创建一个应用，你必须先创建它的项目。为此，在欢迎窗口中点击“Start a new Android Studio project”（启动一个新的 Android Studio 项目），或者如果项目已打开，选择 `File > New > New Project...`。这将显示“Create New Project”（创建新项目）对话框（图 2.2）。

创建新项目对话框中正在执行的步骤

![](img/8c2e5496308864b3b07ddbd4401c4f77_75_0.png)

图 2.2 | 创建新项目对话框——新项目步骤。

### 2.3.3 创建新项目对话框

在创建新项目对话框的“Configure your new project”（配置你的新项目）步骤（步骤 2.2）中，指定以下信息，然后点击 Next（下一步）：

- Application name（应用名称）字段：应用的名称。在此字段中输入 `welcome`。
- Company Domain（公司域名）字段：你公司的域名。我们使用了 `example.com`。出于学习目的可以使用 `example.com`，如果你打算发布你的应用，则必须更改。
- Package name（包名）字段：你应用的 Java 包名。Android 和 Google 商店使用此作为应用的唯一标识符，在你上传到 Google 商店的所有版本中必须保持一致。包名通常以你的公司或机构的域名开头，后面跟着一个点 (.) 和全小写的应用名称。按照惯，包名仅使用小写。IDE 使用你输入的 Application Name 和 Company Domain 设置包名。你可以点击 Package 旁边的 Edit 链接来自定义。
- Project location（项目位置）字段：存储项目的计算机路径。默认情况下，Android Studio 将新文件夹放在用户目录下的 `AndroidProjects` 子文件夹中。项目文件夹包含去掉了空格的项目。你也可以通过输入路径或点击省略号 (...) 按钮浏览到存储项目的位置来自定义位置。选择位置后，点击 Next（下一步）。

![](img/8c2e5496308864b3b07ddbd4401c4f77_76_0)

> 如果你保存项目的路径包含空格，创建新项目对话框会显示“Your location contains whitespace. 这在某些平台上可能会导致问题。”要解决这个问题，点击创建项目对话框 location 字段右侧的省略号 (...) 并选择一个不包含空格的位置；否则你的项目可能无法正确编译或运行。

### 2.3.4 目标 Android 设备

在创建项目对话框的 Target Devices（目标设备）步骤（步骤 2.3）中：

1. 勾选应用应该支持的每个 Android 类型（手机和平板、电视、Wear 和 Gear）的复选框。对于欢迎应用，确保勾选 Phone 和 Tablet。
2. 接下来，在每种设备的下拉菜单中选择 Minimum SDK，然后点击 Next。Minimum SDK 是运行你的应用所需的 API 级别。这允许你的应用运行在该 API 级别及更高的设备上。为应用选择 Android 6.0 (Marshmallow) 并点击 Next。图 2.4 显示了 Android SDK 版本及其 API 级别——未显示的版本已弃用，不应使用。每个平台的 Android 设备百分比由 Minimum SDK 值显示——例如，在编写时，API 15 可以达到 94% 的设备。通常你应该针对应用可以运行的最低 API 级别。

![](img/8c2e5496308864b3b07ddbd4401c4f77_77_0.png)

图 2.3 | 创建新项目对话框——目标设备步骤。

| SDK 版本 | API 级别 | SDK 版本 | API 级别 | SDK 版本 | API 级别 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 6.0 | 23 | 4.3 | 18 | 2.3–2.7 | 10 |
| 5.1 | 22 | 4.2.x | 17 | 2.2 | 8 |
| 5.0 | 21 | 4.1.x | 16 | | |
| 4.4 | 19 | 4.0.3–4.0.4 | 15 | | |

**图 2.4** | SDK 版本和 API 级别。

### 2.3.5 向手机添加 Activity

在 **Add an Activity**（向手机添加 Activity）步骤（图 2.5）中，你将选择一个应用模板。模板为常见的应用设计和应用逻辑提供了预配置的起点。

![](img/8c2e5496308864b3b07ddbd4401c4f77_78_0.png)

**图 2.5** | 创建新项目对话框——向手机添加 Activity 步骤。

图 2.6 简要描述了图 2.5 中的四个常用模板。对于此应用，选择 Empty Activity（空 Activity），然后点击 Next。此模板定义了一个显示 Hello World! 的单屏幕应用。我们后续章节中使用其他模板。对于多屏幕应用，通过向现有应用添加 Activity 之一来定义新屏幕。例如，在第 4 章的 Flag Quiz（旗帜测试）应用中，我们将添加一个 Settings Activity（设置 Activity），提供一个用户可以选择测试设置的屏幕。

| 模板 | 描述 |
| :--- | :--- |
| Blank Activity（空 Activity） | 用于构建大部分 GUI 界面的单屏应用。在应用顶部提供一个应用栏，显示应用名称并可以显示用户与应用交互的控件。还包含一个 material design 浮动按钮 (FloatingActionButton)。 |
| Fullscreen Activity（全屏 Activity） | 用于占据整个屏幕的单屏应用（类似于 Blank Activity），但可以切换设备状态栏和应用的可见性。 |



# Master/Detail Flow（主列表/详情流）

用于显示项目主列表的应用，用户可以从中选择一个项目查看其详情——类似于内置的邮件和联系人应用。包含了允许用户从主列表中选择项目并在详情视图中显示该项目的基本逻辑。对于平板，主列表和详情在同一屏幕上并行显示。对于手机，主列表显示在一个屏幕上，选择项目将在另一个屏幕显示详情。

图 2.6 | Activity 模板

## 2.3.6 定制 Activity 步骤

此步骤（图 2.7）取决于上一步选择的模板。对于 `Empty Activity` 模板，这允许你指定：

- `Activity Name`（Activity 名称）：`MainActivity` 是 IDE 默认名称。这是一个控制应用执行的 `Activity` 子类的名称。从第 3 章开始，我们将修改该类来实现应用的功能。
- `Layout Name`（布局名称）：`activity_main` 是 IDE 默认名称。该文件（带有 `.xml` 扩展名）存储应用 GUI 的 XML 表示，你将在第 2.5 节中使用可视化技术构建它。

对于此应用，保持默认设置，然后点击 `Finish`（完成）创建项目。

## 第 2 章 欢迎应用

![](img/8c2e5496308864b3b07ddbd4401c4f77_80_0.png)

图 2.7 创建新项目对话框——自定义 Activity 步骤。

## 2.4 Android Studio 窗口

项目创建完成后，IDE 会同时打开 `MainActivity.java` 和 `activity_main.xml`。关闭 `MainActivity.java`，这样 IDE 就会如图 2.8 所示。IDE 显示布局编辑器，你可以开始设计应用的应用的 GUI。在本章中，我们只讨论构建欢迎应用时所需的 IDE 功能。我们将在整书中介绍更多的 IDE 功能。

项目窗口（`Project window`）显示组件树（`Component Tree`），其中 `app` 节点显示所选项目的文件——布局和代码编辑器出现在属性窗口（`Properties window`）中。

![](img/8c2e5496308864b3b07ddbd4401c4f77_81_0.png)

折叠的标签页——你可以点击标签页来展开相应的窗口。

图 2.8 | 在 Android Studio 中打开的欢迎项目。

### 2.4.1 项目窗口

**项目窗口**提供了对所有项目文件的访问。你可以同时在 IDE 中打开多个项目——每个项目都有自己的窗口。2.9 显示了**项目窗口**中的**欢迎**（`Welcome`）应用的内容——我们展开了 `res` 文件夹，而 `app` 文件夹包含了你创建应用 GUI 和逻辑时要编辑的文件。`app` 文件夹的内容组织成包含文件的嵌套文件夹。在本章中，你将只位于 `res` 文件夹中的文件，我们将在 2.4.4 节中讨论它们——我们将在后续章节中使用时讨论其他文件夹和文件。

![](img/8c2e5496308864b3b07ddbd4401c4f77_82_0.png)

**图 2.9** 项目窗口。

### 2.4.2 编辑器窗口

图 2.8 中**项目**窗口的右侧是布局编辑器窗口。其内容根据文件类型显示在相应的编辑器窗口中。对于 Java 文件，将显示 Java 源代码编辑器。对于表示 GUI 的 XML 文件（如 `activity_main.xml`），默认显示布局编辑器的 **Design**（设计）标签页，你可以点击 **Text**（文本）标签页与设计预览并排查看相应的 XML——如果预览没有出现，可以通过选择 **View > Tool Windows > Preview** 来查看。对于其他 XML 文件，将根据 XML 文件的用途显示自定义 XML 编辑器或文本编辑器。Java 和 XML 的编辑器可以帮助你通过代码补全快速编写代码——当你打字时，可以按 **Enter (Return)** 自动补全代码补全窗口中当前亮的代码元素或 XML 元素、属性名或值。

### 2.4.3 组件树窗口

当编辑器处于 **Design** 视图时，**组件树**（`Component Tree`）出现在 IDE 的右侧（图 2.8）。该窗口显示了组成 GUI 的*布局*（layouts）和*视图*（GUI 组件）及其父子关系——例如，一个布局（父级）可能包含许多嵌套视图（子级），包括其他布局。

### 2.4.4 应用资源文件

像 `activity_main.xml` 这样的布局文件是应用资源，存储在项目 **res** 文件夹的子文件夹中。子文件夹包含不同的资源类型。我们在应用中使用的如图 2.10 所示，其他的将在书中以后需要时进行讨论（`menu`、`animator`、`anim`、`color`、`mipmap`、`raw` 和 `xml`）。

| 资源子文件夹 | 描述 |
| --- | --- |
| `drawable` | 以 `drawable` 开头的文件夹名称通常包含图像。这些文件夹可能包含表示形状和其他类型可绘制对象的 XML 文件（例如表示按钮未按下和已按下状态的图像）。 |
| `layout` | 以 `layout` 开头的文件夹包含描述 GUI 的 XML 文件，例如 `activity_main.xml` 文件。 |
| `values` | 以 `values` 开头的文件夹包含 XML 文件，指定数组（`arrays.xml`）、颜色（`colors.xml`）、尺寸（`dimensions.xml`）——如宽度、高度和字体大小）、字符串（`strings.xml`）和样式（`styles.xml`）的值。这些文件按惯例使用，但并不要求都放在一个文件中。将硬编码的数组、颜色、尺寸、字符串和样式的数据定义为资源是一项良好的做法，这样可以在不更改应用代码的情况下轻松修改它们。例如，如果代码中的多个位置引用了尺寸资源，你可以在资源文件中更改尺寸值，而不是在应用的 Java 源代码文件中搜索硬编码尺寸值的每个出现处。 |

**图 2.10** 项目 **res** 文件夹中在本章中使用的子文件夹。

### 2.4.5 布局编辑器

当你创建一个项目时，IDE 会在布局编辑器中打开应用的 `activity_main.xml` 文件（图 2.11）。你也可以双击 `res/layout` 文件夹中的 `activity_main.xml` 来打开它。

#### 选择 GUI 的屏幕类型

Android 设备运行在多种设备上。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。

## 第 2 章 欢迎应用

![](img/8c2e5496308864b3b07ddbd4401c4f77_84_0.png)

图 2.11 | 应用布局编辑器。

### 2.4.6 默认 GUI

Android 设备运行在多种设备上。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。

调色板（`Palette`）包含小部件（views）、布局以及可以拖到画布上的其他项目。

### 2.4.7 用于默认的 XML

在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。在本章中，你将设计 Android 手机 GUI。

### 2.5.1 向项目添加图像

对于此应用，你将向项目添加一张图像。我们将使用 Deitel bug logo¹ 图像 (`.png`)，它位于书籍示例文件夹中 `images` 文件夹下的 `Welcome` 子文件夹中。资源的文件名——以及你在后续章节中使用的所有其他资源——必须是小写字母。

### drawable 文件夹

Android 设备具有各种屏幕分辨率、分辨率和像素密度（即每英寸点数或 DPI），你通常提供各种分辨率的图像，由操作系统根据像素密度进行选择。这些图像放置在 `drawable` 文件夹中（在项目的 `res` 文件夹下），存储具有不同像素密度的图像（图 2.13）。例如，对于像素密度与我们在手机 AVD 中使用的 Google Nexus 6 (560 dpi) 类似的设备，图像将放在 `drawable-xxxdpi` 文件夹中；像素密度较低的设备则放在其他 `drawable` 文件夹中——通常是与实际设备像素密度最接近的文件夹。

| 密度 | 说明 |
|---|---|
| `drawable-ldpi` | 低密度——大约每英寸 120 点。 |
| `drawable-mdpi` | 中密度——大约每英寸 160 点。 |
| `drawable-hdpi` | 高密度——大约每英寸 240 点。 |
| `drawable-xhdpi` | 超高密度——大约每英寸 320 点。 |
| `drawable-xxhdpi` | 极高密度——大约每英寸 480 点。 |
| `drawable-xxxhpi` | 特极超高密度——大约每英寸 640 点。 |

**图 2.13** Android 像素：仅包含应用可绘制图的单个 `drawable` 文件夹

Android Studio 资源，如果你的项目包含多个密度的资源。对于存储在项目文件夹 `drawable-xxxhdpi` 中的资源，Android Studio 在项目的 `drawable` 文件夹中显示 `filename.xml (xxxhdpi)`。

对于此应用，我们只提供一个版本的图像。如果 Android 无法在 `drawable` 文件夹中找到与设备像素密度紧密匹配的图像，Android 将把另一个 `drawable` 文件夹中的版本放大或按需要调整。默认情况下，Android Studio 只创建一个不带 DPI 限定符的 `drawable`，我们将在此应用中使用它。有关 Android Android 支持多屏幕和多尺寸的详细信息：

```
http://developer.android.com/guide/practices/screens_support.html
```

- 1. 在应用中使用任何图像之前，你应该确保你已正确获得该图像的许可。某些免费图像许可提供你使用图像的权利，另一些提供免费开源或知识共享 (creativecommons.org) 许可。

## 2.5 使用布局编辑器构建应用的 GUI

> 外观观察 2.1

低分辨率图像的缩放效果不好。为了让图像渲染良好，高像素密度设备需要比低像素密度设备更高分辨率的图像。

### 将 bug.png 添加到项目

执行以下步骤将图像添加到此项目中：

- 1. 在 `Project` 窗口中，展开项目的 `res` 文件夹。
- 2. 在书籍的 `examples` 文件夹或你的文件系统中，打开 `images` 文件夹，然后进入 `welcome` 子文件夹。
- 3. 复制 `bug.png` 文件，然后在 Android Studio 的 `Project` 窗口中选择 `res` 文件夹并将文件粘贴到该子文件夹中。
- 4. 在弹出的 `Copy` 对话框中，点击 `OK`。

现在可以在应用中使用该了。

## 2.5.2 添加应用图标

当应用安装在设备上时，它的图标和名称将与其他所有已安装的应用一起出现在启动器中，你可以通过设备主屏幕上的图标访问它。要添加应用的启动图标，右键点击 `res` 文件夹，然后选择 `New > Image Asset`。这将打开 `Asset Studio` 窗口（图 2.14），该窗口允许你从现有图像或剪贴画配置应用图标。

对于此应用，我们选择了位于书籍 `examples` 文件夹中 `images` 文件夹的 `orange.png` 图像。要使用它：

- 1. 点击省略号按钮以引入图像文件。
- 2. 导航到书籍 `examples` 文件夹中的 `images` 文件夹。
- 3. 选择 `de10orange.png` 并点击 `OK`。对话框的 `Preview` 区域将显示缩放后的图像预览。



## 4. 点击 Next，然后点击 finish。

IDE 创建了图像的缩放版本，每个命名为`_launcher.png`，并将它们放置在`drawable`文件夹中。IDE 创建了图像的缩放版本，每个命名为`_launcher.png`，并将它们放置在`drawable`文件夹中。IDE 创建了图像的缩放版本，每个命名为`_launcher.png`，并将它们放置在`drawable`文件夹中。IDE 创建了图像的缩放版本，每个命名为`_launcher.png`，并将它们放置在`drawable`文件夹中。IDE 创建了图像的缩放版本，每个命名为`_launcher.png`，并将它们放置在`drawable`文件夹中。IDE 创建了图像的缩放版本，每个命名为`_launcher.png`，并放置在 in-based..

> 外观观察 2.2

图像并不总是能良好缩放。对于图像要到到到，,-................（此处省略重复乱码）...................

- the de-row-

- scaled......

## 2.5.2 添加应用图标

当应用安装在设备上时，它的图标和名称将与其他所有已安装的应用一起出现在启动器中，你可以通过设备主屏幕上的图标访问它。要添加应用的启动图标，右键点击`res`文件夹，然后选择 New > Image Asset。这将打开 Asset Studio 窗口（图 2.14），该窗口允许你从现有图像或剪贴画配置应用图标。

对于此应用，我们选择了书籍`examples`文件夹中`images`文件夹的`orange.png`图像。要使用它：

1. 点击省略号按钮以引入图像文件。

2. 导航到书籍`examples`文件夹中的`images`文件夹。

3. 选择`de10orange.png`并点击 OK。对话框的 Preview 区域将显示缩放后的图像预览。

4. 点击 Next，然后点击 finish。

IDE 创建了图像的缩放版本，每个命名为`_launcher.png`，并将它们放置在`drawable`文件夹中。IDE 创建了图像的缩放版本，每个命名为`_launcher.png`，并将它们放置在`drawable`文件夹中。IDE 创建了图像的缩放版本，每个命名为`_launcher.png`，并将它们放置在`drawable`文件夹中。IDE 创建了图像的缩放版本，每个命名为`_launcher.png`，并将它们放置在`drawable`文件夹中。IDE 创建了图像的缩放版本，每个命名为`_launcher.png`，并放置在-based

## 2.5.3 将 RelativeLayout 改为 LinearLayout

Android Studio 资源，如果你的项目包含多个密度的资源。对于存储在项目文件夹`drawable-xxxhdpi`中的资源，Android Studio 在项目的`drawable`文件夹中显示`filename.xml (xxxhdpi)`。

对于此应用，我们只提供一个版本的图像。如果 Android 无法在`drawable`文件夹中找到与设备像素密度紧密匹配的图像，Android 将把另一个`drawable`文件夹中的版本放大或按需要调整。默认情况下，Android Studio 只创建一个不带 DPI 限定符的`drawable`，我们将在此应用中使用它。有关 Android 支持多屏幕和多尺寸的详细信息：

```
http://developer.android.com/guide/practices/screens_support.html
```

### 2.5.4 修改 LinearLayout 的 id 和方向

在本节中，你将使用 LinearLayout 的属性。通常情况下，为每个视图一个相关的名称。这有助于你在 Component Tree 中轻松识别每个视图，并允许我们在后续应用中通过代码管理这些视图。

当 GUI 显示在布局编辑器中时，你可以使用 Component Tree 下方的 Properties 窗口（图 2.8）配置选中视图的属性。可以通过点击画布上的视图来编辑最常用的属性（你在本节中将这样做）。

- 对于 LinearLayout，你可以设置方向以指定布局子是水平方向还是垂直方向。

- 对于 TextView，你可以设置显示的文本。

- 对于 ImageView，你可以设置显示图像的 src（源）。

### 2.5.5 设置 LinearLayout 的方向和 id 属性

要更改 LinearLayout 的方向，双击布局编辑器中的虚拟手机屏幕背景以显示 LinearLayout 常用属性对话框，如图 2.17 所示，从 orientation 下拉菜单中选择 vertical。这会设置属性值并关闭对话框。视图名称通过设置其 id 来定义。

属性，在布局的 XML 中通过`android:id`属性指定。双击虚拟手机屏幕的白色背景，在`id:`字段中输入名称`welcome_linearLayout`，然后按 Enter（或 Return）设置值并关闭对话框。

![](img/8c2e5496308864b3b07ddbd4401c4f77_90_0.png)

**图 2.17** 设置 LinearLayout 的方向。

## id 属性的 XML 表示

在布局的 XML 表示中——可以通过布局编辑器底部的 Text 查看——LinearLayout 的`android:id`具有此值：

```
@+id/welcomeLinearLayout
```

带有语法`@+id`的符号表示应使用正斜杠（/）右侧的标识符创建一个新的 id。在某些情况下，XML 包含不带`+`的相同语法来引用此视图——例如，指定 RelativeLayout 中视图之间的关系。

## 2.5.5 配置 TextView 的 id 和 text 属性

应用程序的默认 GUI 已经包含一个 TextView，因此你只需要修改它的属性。

## 设置 TextView 的 id 属性

双击布局编辑器中的 TextView，在弹出的对话框中将 id: 设置为`welcomeTextView`并按 Enter（或 Return）。

## 使用字符串资源配置 TextView 的 text 属性

根据 Android 应用程序资源文档

```
http://developer.android.com/guide/topic/resources/index.html
```

将字符串、数组、图像、颜色、字体、尺寸和其他资源放置在项目文件夹子目录下的 XML 文件中是一个良好的做法，这样这些资源就可以与应用程序的 Java 代码分开管理。这被称为资源的外部化。例如，如果你将颜色值外部化，则所有使用相同颜色的组件都可以通过更改资源文件中的值来更新为新颜色。

如果你想用多种语言对应用程序进行本地化，将字符串与程序代码分开存储可以让你轻松地更改它们。在你的项目文件夹中，`values`子文件夹包含一个`strings.xml`文件，用于存储应用程序的默认语言字符串——我们的应用程序使用英语。要本地化其他语言的字符串，你可以为种语言创建单独的文件夹，正如我们在 2.8 中将所示。

要设置 TextView 的 text 属性，在`strings.xml`文件中按如下方式创建一个新的字符串资源：

1. 双击布局编辑器中的`welcome-TextView`，或选择`welcome-TextView`并在属性窗口中找到其 text 属性。

2. 点击属性右侧的省略号 (...) 按钮显示 Resources 对话框。

3. 在 Resources 对话框中，点击 New Resource，然后选择 New String Value... 显示 New String Value 对话框，并如图 2.18 所示找到 Resource name: 和 Resource-value:。留出其他设置（我们将在稍后的章节和应用程序中讨论这些）并点击 OK 创建名为`welcome`的新字符串资源，并设置 TextView text 属性的值。

![](img/8c2e5496308864b3b07ddbd4401c4f77_91_0.png)

图 2.18 | New String Value Resource 对话框。

在 Properties 窗口中，text 属性现在应该如图 2.19 所示。`$string/`前缀表示将使用字符串资源获取 text 属性的值，`welcome`表示要使用的特定字符串资源。默认情况下，该资源放置在`strings.xml`文件中（位于项目的`res/values`文件夹）。

![](img/8c2e5496308864b3b07ddbd4401c4f77_91_1.png)

图 2.19 | 修改 TextView text 属性后的 Properties 窗口。

## 2.5.6 配置 TextView 的 textSize——缩放像素和密度无关像素

尺寸可以使用测量单位指定（图 2.20）。支持多种屏幕尺寸的文档建议在视图和其他屏幕元素的尺寸上使用*密度无关像素*（density-independent pixels），在字体大小上使用*缩放无关像素*（scale-independent pixels）：

```
http://developer.android.com/guide/practices/screens_support.html
```

| 单位 | 描述 | 单位 | 描述 |
| --- | --- | --- | --- |
| px | 像素 | in | 英 |
| dp or dip | 密度无关像素 | mm | 毫米 |
| sp | 缩放无关像素 | | |

**图 2.20** 测量单位。

使用*密度无关像素*定义你的 GUI 可以让 Android 平台根据给定设备的像素密度缩放 GUI。*一个密度无关像素*等于 160-dpi 屏幕上的一个像素。在 240-dpi 屏幕上，每个密度无关像素将按 240/160（即 1.5）的比例缩放。因此，具有 100 独立像素的组件将被缩放大 150 个实际像素。在 120 dpi 屏幕上，每个密度无关像素将按 120/160（即 0.75）的比例缩放。因此，具有 100 独立像素的相同组件将是 75 个实际像素。*缩放无关像素*的缩放方式类似于密度无关像素，但它们还会根据*用户偏好的字体大小*（在设备设置中指定）进行缩放。

## 在手机上创建字体尺寸资源

你将在布局编辑器中增大`TextView`以更改字体大小：

1. 选择 **TextView**

2. 定位`textSize`属性，然后点击右侧的省略号 (...) 显示 Resources 对话框。

3. 在 Resources 对话框中，点击 New Resource，然后选择 New String Value 显示 New String Value 对话框。

4. 在出现的对话框中，为 **Resource name** 指定`welcome_textSize`，并将 **Resource value** 设置为 40sp，然后点击 OK 创建名为`welcome`的新字符串资源，并设置 TextView text 属性的值。

（注：由于 OCR 文本存在重复和错误，译文已根据要求进行了清理，去除了页眉、页码和重复内容。）

（注：我注意到重复的文本中重复的重复的重复的的重复的重复的重复的重复...）

## 在手机上创建字体尺寸资源

你将在布局编辑器中增大`TextView`：

1. 选择 **TextView**

2. 定位`textSize`属性，然后点击右侧的省略号 (...) 显示 Resources 对话框。

3. 在 Resources 对话框中，点击 New Resource，然后选择 New Dimension Value 显示 New Dimension Resource。

4. 在出现的对话框中，为 **Resource name** 指定`welcome_textSize`，并将 **Resource value** 设置为 40sp，然后点击 OK 关闭对话框并返回 Resources 对话框。值中的 40sp 表示这是缩放无关测量。维度值中的 dp（例如 10dp）表示密度无关像素测量。我们为手机显示使用了 40sp 的值。

在 Properties 窗口中，`textSize`属性现在包含值：

```
@dim/welcome_textSize
```

`@dim/`前缀表示`textSize`属性的值是一个维度资源，`welcome_textSize`表示要使用的特定维度资源。默认情况下，该资源放置在`dimens.xml`文件中（位于项目的`res/values`文件夹）。

## 在平板上创建字体尺寸资源

40sp 的字体大小适用于手机尺寸的设备，但对于平板来说太小。Android 可以根据设备尺寸、方向、密度和区域自动选择资源值。为较大的设备指定单独的字体大小：

1. 如上所述重新打开 Dimension Resource。

2. 为 **Resource name** 输入`welcome_textSize`（资源名称必须匹配以便 Android 自动选择不同的值），并为 **Resource value** 输入 80sp。

3. 接下来，你为较大的设备（如宽度和高度至少为 600dp 的平板）创建一个新的 values 资源文件夹。在 Dimension Resource 对话框中，取消勾选 values 选框，并点击 (+) 打开 New Resource Directory。在此对话框的 Available qualifiers 中，选择 Screen Width，然后点击 > 按钮添加到 Screen Width qualifier，选择 Chosen qualifiers。接下来，在 Screen Width 字段中输入 600。

4. 接下来，将 Screen Height qualifier 添加到 Chosen qualifiers，并为 Screen height 输入 600。

5. 点击 OK 创建新资源文件夹`values-xlarge`。

6. 在 Dimension Resource 对话框中，勾选`values-w60dp-h600dp`选框，然后点击 OK。这在项目`res/values-w600dp`文件夹中的`dims.xml`文件中创建了另一个`welcome_textSize`资源。Android 将此用于宽度和高度至少为 600dp 的大屏幕设备。新的`.dims.xml`资源文件出现在 Android Studio 项目的`res/values`节点：

```
dims.xml (w600dp-h600dp)
```

## 2.5.7 设置 TextView 的颜色属性

## 第2章 欢迎应用

将 TextView 的 textColor 属性 (...) 设置为新的颜色资源：

1. 在 Properties（属性）窗口中，点击省略号 (...) 显示 Resources（资源）对话框，点击 New Resource（新建资源）并选择 New Color Value...（新建颜色值...）。

2. 在 New Color Resource 对话框中，在 Resource-source name 中输入`welcome_text_color`，在 Resource value 中输入`#2196F3`（图 2.21），然后点击 OK。

![](img/8c2e5496308864b3b07ddbd4401c4f77_94_0.png)

图 2.21 | 为 TextView 的 textColor 属性创建新的颜色资源。

### 2.5.8 设置 TextView 的 gravity 属性

如果 TextView 中的文本换行到多行，并希望其居中显示，可以将它的 gravity 属性设置为 center（居中）。操作时，展开该属性的节点，然后勾选 center 复选框（图 2.22）。

![](img/8c2e5496308864b3b07ddbd4401c4f77_94_1.png)

图 2.22 | TextView 属性中 Gravity 属性的选项。

## 2.5 使用布局构建构建 GUI

### 2.5.9 设置 TextView 的 layout:gravity 属性

你放置在布局中的每个 view 都有各种布局属性，允许你自定义视图在布局中的尺寸和位置。当你在编辑器或 Component Tree（组件树）中选择视图时，Properties 窗口会在顶部列出布局和样式属性，随后按字母顺序列出视图特有的属性（图 2.23）。

| Properties | | |
|---|---|---|
| layoutwidth | wrap_content | |
| layoutheight | wrap_content | |
| layoutgravity | | |
| layoutmargin | | |
| layoutweight | | |
| style | | |
| accessibilityLiveReg | | |
| accessibility | | |
| accessibilityTraversal | | |
| allowIndo | | |
| alpha | | |
| autoLink | | |
| autoText | | |
| background | | |

- 布局和样式属性首先列出
- 其他视图属性在布局和样式属性之后列出
- 切换 'expert-' 的显示——大多数程序员不会修改——这些属性默认是隐藏的
- 将选定的属性重置为默认值
- 显示当前选中属性的简要描述

**图 2.23** 显示了顶部显示布局和样式属性的 Properties 窗口。



在此应用中，我们希望让`TextView`在`LinearLayout`中水平居中。为了实现这一点，你按照如下方式将其`layout:gravity`属性设置为水平居中（center）：

1. 选中`TextView`，在`Properties`窗口中展开`layout:gravity`属性节点。
2. 点击出现的`center`选项右侧的值字段，然后选择`horizontal`选项（图 2.24）。

| Properties | | |
|---|---|---|
| `layoutwidth` | `wrap_content` | |
| `layoutheight` | `wrap_content` | |
| `layoutgravity` | | |
| `top` | | |
| `bottom` | | |
| `left` | | |
| `right` | | |
| `center` | `<unset>` | |
| `layout:` | `horizontal` | |
| `layoutweight` | `vertical` | |
| `style` | `both` | |

**图 2.24** | 为`TextView`设置`layout:gravity`。

## 第2章 欢迎应用

在布局的 XML 文件中，布局属性的属性名以`layout...`开头。前述的`layout:gravity`属性设置在 XML 中表示为：

```xml
android:layout_gravity="center_horizontal"
```

### 2.5.10 设置 TextView 的 layout:weight 属性

`LinearLayout`可以根据其子元素的`layout:weight`按比例调整尺寸，`layout:weight`指定了视图相对于布局中其他视图的相对大小。默认情况下，添加到`LinearLayout`的每个`view`的`layout:weight`均为 0，这表示该视图不应按比例调整尺寸。

在此应用中，我们将让`TextView`和`ImageView`占据`LinearLayout`垂直空间的一半。你可以通过将每个`layout:weight`设置为相同的值来实现。`LinearLayout`使用每个`layout:weight`与总`layout:weight`的比值来为视图分配空间。在此应用中，你将`TextView`和`ImageView`的`layout:weight`都设为 1（见 2.5.11 节）——总`layout:weight`为 2，每个视图将占据高度的 1/2。

如果你希望`TextView`占据`LinearLayout`高度的三分之一，可以将`layout:weight`设为 1，并将`ImageView`的`layout:weight`设为 2。在这种情况下，总`layout:weight`为 3，因此`TextView`将占据高度的 1/3，`ImageView`占据 2/3。

将`layout:weight`设置为 1。布局编辑器会在`layout:height`属性旁边显示一个灯泡图标——它由 IDE 中名为`Lint`的工具生成，会警告潜在问题并帮助你修复。当你点击灯泡时，IDE 会显示“使用`layout_height`以获得更好的性能”。此更改允许`LinearLayout`高效地计算其子元素的大小。布局编辑器现在如图 2.25 所示。

> **错误预防提示 2.2**
> `Lint`检查常见错误并对安全、性能、可访问性和国际化提供建议。

### 2.5.11 在布局中添加 ImageView

接下来，将在 GUI 中添加`ImageView`。通过从`Palette`拖拽`ImageView`到画布上来实现。当你拖动视图时，布局编辑器会显示绿线指示视图将被放置的位置。

## 2.5 使用布局构建构建 GUI

![](img/8c2e5496308864b3b07ddbd4401c4f77_97.png)

**图 2.25** | 配置`TextView`后的布局。

添加并配置`ImageView`：

1. 从`Palette`的`Widgets`部分将`ImageView`拖动到画布上，如图 2.26 所示。在释放鼠标之前，确保布局会将`ImageView`的`layout:gravity`属性设置为水平居中。
2. 在`Properties`窗口中找到`ImageView`的`src`属性（指定要显示的图像），双击其值字段的省略号显示`Resources`对话框（图 2.27）。当对话框打开时，输入`bug`以在资源列表中搜索你在 2.5.1 节中添加的图像，然后点击`OK`。
3. 双击布局编辑器中的`ImageView`，并将其`id`设置为`bugImageView`。

GUI 现在应该如图 2.28 所示。

![](img/8c2e5496308864b3b0ddbd4401c4f77_98.png)

**图 2.26** | 将`ImageView`拖放到 GUI 上。

**图 2.27** | 资源选择对话框。

**图 2.28** | 包含`TextView`和`ImageView`的最终布局。

## 2.5 使用布局编辑器构建应用的 GUI

![](img/8c2e5496308864b3b07ddbd4401c4f77_99_0.png)

所选可绘制资源的预览——IDE 不一定会以其原始宽高比显示图像

图 2.27 | 从资源（`Resources`）对话框中选择`bug`图像资源。

![](img/8c2e5496308864b3b07ddbd4401c4f77_99_1.png)

Android Lint 提示`ImageView`缺少视障用户所需的属性

图 2.28 | 完成后的设计预览。

### 2.5.12 预览设计

Android Studio 允许你在横向模式下预览设计，并为多个设备预览你的设计。若要在竖向和横向方向之间切换设计，只需点击布局编辑器工具栏上的“转到下一个状态”（Go to next state）按钮。这可以帮助你判断设计是否针对每种方向进行了适当调整。要为多个设备预览设计，点击布局编辑器顶部的虚拟设备下拉菜单（图 2.11），然后选择“预览所有屏幕尺寸”（Preview All Screen Sizes）。这将显示虚拟设备下拉菜单列出的许多设备的缩型屏幕（图 2.29），其中某些是竖向的，某些是横向的。这些可以帮助你判断设计是否在各种设备上正常工作。

![](img/8c2e5496308864b3b07ddbd4401c4f77_100_0.png)

**图 2.29** | Welcome 应用设计的设备预览。

## 2.6 运行 Welcome 应用

通过点击下拉菜单并选择“移除预览”（Remove Previews），你可以返回只显示一个设备。你也可以通过虚拟设备下拉菜单中选择特定设备来为该设备预览设计。

你现在已准备好运行 Welcome 应用。按照第 1.9.3 节所示的步骤，在你之前为 Nexus 6 手机和 Nexus 9 平板电脑配置的 AVD 上运行应用。表 2.30–2.31 显示了应用在 Nexus 6 AVD（分别为竖向和横向）以及 Nexus 9 AVD（均为横向）上的运行情况。你可以通过输入`Ctrl + F11`或`control + F11`在 AVD 的竖向和横向之间切换。通常，对于同时在手机和平板电脑上运行的应用，你还会提供一个平板电脑布局，以更好地利用屏幕可用空间，我们将在后面的章节中进行演示。如果你有一台 Android 设备，可以按照第 1.9.4 节的步骤在你的设备上运行应用。

![](img/8c2e5496308864b3b07ddbd4401c4f77_101_0.png)

![](img/8c2e5496308864b3b07ddbd4401c4f77_101_1.png)

图 2.30 在 Nexus 6 AVD 中运行 Welcome 应用。

## 第 2 章 Welcome 应用

![](img/8c2e5496308864b3b07ddbd4401c4f77_102_0.png)

图 2.31 | 在 Nexus 9 AVD 中运行 Welcome 应用。

## 2.7 使你的应用支持无障碍

Android 包含了无障碍功能，帮助某些残障人士使用他们的设备。对于视觉障碍的人士，Android 的 TalkBack 可以朗读屏幕文本或你提供的文本（在设计 GUI 或通过编程提供时），以帮助用户理解视图的作用。Android 还有“触摸探索”（Explore by Touch），使用户在触摸时可以听到 TalkBack 读出屏幕上的内容。

当启用 TalkBack 时，用户触摸指定无障碍文本的视图，设备会震动以指示用户旋转了一个视图，TalkBack 会朗读视图的无障碍文本。所有标准的 Android 视图都支持无障碍。对于显示文本，TalkBack 会读取默认——例如，当用户触摸`TextView`时，TalkBack 会读出`TextView`。你可以在设置（Settings）中的无障碍（Accessibility）下启用 TalkBack。从该页面，你还可以启用其他无障碍功能，如更大的默认字体大小以及使用手势放大屏幕区域的功能。目前 AVD 不支持 TalkBack，因此你必须在设备上运行此应用才能听到 TalkBack 朗读文本。启用后，Android 会引导你完成使用 TalkBack 配合触摸探索的教程。

### 为 ImageView 启用 TalkBack

在 Welcome 应用中，我们不需要为`TextView`提供更多描述性文本，因为 TalkBack 会读取`TextView`的内容。然而，对于`ImageView`，除非你提供文本，否则没有文本供 TalkBack 朗读。在 Android 中，一种被认为是良好的做法是通过为任何不显示文本的视图提供`contentDescription`属性的文本，确保每个视图都能配合 TalkBack 使用。例如，IDE 在我们在布局编辑器中使用`ImageView`时，通过显示灯泡图标（如你在 2.28 中看到的 💡）警告我们出了一些问题。如果你点击灯泡，你将在图中看到“无障碍（Accessibility）”缺少`contentDescription`属性。

## 2.8 应用的国际化

为了触及最广泛的观众，你应该考虑为各种语言设计你的应用。例如，如果你打算提供法语版本的应用，你将对资源进行翻译。将应用设计成可以自定义的形式被称为国际化（internationalization）。为每个语言环境定制应用被称为本地化（localization）。

### 2.8.1 本地化

将字符串定义为资源（正如我们在本应用中所做的）的一个优势是，可以通过添加其他语言的`strings.xml`文件轻松地本地化应用。

### 2.8.2 本地化资源的命名

包含本地化资源的 XML 文件放在子文件夹中。Android 使用特殊的命名约定自动选择资源——例如，`values-fr`将包含法语`strings.xml`文件，`values-es`将包含西班牙语`strings.xml`文件。你还可以为美国英语命名，以及`values-gb`将包含英国英语`strings.xml`文件。如果未为给定的语言环境提供本地化资源，Android 将使用默认资源——即`values`文件夹中的。

### 2.8.3 为项目添加翻译

Android Studio 提供了翻译编辑器，用于快速为应用添加翻译。按照以下步骤操作：

- 在项目窗口中，展开`values`文件夹，然后打开`strings.xml`文件。
- 在编辑器右上角，点击“打开编辑器”链接打开翻译编辑器。
- 在翻译编辑器左上角，点击“添加语言环境”（Add Locale (+)——你可以通过输入语言名称的部分或缩写（`es`）来搜索此项。在列表中选择后，将创建一个新的`strings.xml`文件并将其放在项目窗口的`strings`节点中（该文件存储在磁盘上的`values-es`文件夹中）。翻译编辑器还会显示西班牙语翻译的新列。
- 要为字符串资源添加翻译，点击源西班牙语（`es`）翻译单元格，然后在窗口底部的`Translation`字段输入西班牙语文本。如果某个字符串不应被翻译（例如不显示给用户的字符串），勾选该字符串资源的复选框。

### 2.8.4 本地化字符串

在本应用中，GUI 包含一个显示字符串的`TextView`和一个用于`ImageView`的内容描述字符串。这些字符串已经在`strings.xml`文件中被定义为字符串资源。现在你可以提供翻译后的字符串，它们将存储在新版本的`strings.xml`文件中。对于此应用，你将替换字符串

```
"Welcome to Android App Development!"
"Deitel double-thumbs-up bug logo"
```

## 2.8 应用程序国际化 69

带有西班牙语字符串

> "¡Bienvenido al Desarrollo de App Android!"
>
> El logo de Deitel que tiene el insecto con pulgares hacia arriba

在“翻译编辑器”（Translation Editor）窗口中：

1. 点击欢迎资源的西班牙语 (`es`) 翻译单元格，然后在窗口底部的“翻译”（Translation:）框中输入西班牙语字符串“Bienvenido al Desarrollo de App Android!”。如果你无法在键盘上输入特殊字符和符号，可以从 Welcome 应用最终目录下的`res/values-es/strings.xml`文件（位于章节示例所在的 WelcomeLocalized 文件夹中）复制字符串，然后将西班牙语字符串粘贴到翻译框中。
2. 接下来，点击`deitel_logo`资源值的单元格，并在翻译框中输入：“El logo de Deitel que tiene el insecto con pulgares hacia arriba.”
3. 我们选择不翻译`app_name`资源，尽管我们可以这样做。窗口显示将如图 2.32 所示。
4. 选择文件（File） > 全部保存（Save All）或点击保存工具栏按钮（ ）来保存`strings.xml`。

| 键 (Key) | 默认值 (Default Value) | 不可翻译 | 西班牙语 (es) |
|---|---|---|---|
| `app_name` | Welcome | | |
| `deitel_logo` | Deitel double-thumbs-up logo | | El logo de Deitel que tiene el insecto con pulgares hacia arriba |
| `welcome` | Welcome to Android Development! | | ¡Bienvenido al Desarrollo de App Android! |

**图 2.32** | 带有西班牙语字符串的翻译窗口。

### 2.8.5 在 AVD 上测试西班牙语应用

要在 AVD 上测试西班牙语应用，可以使用安装在 AVD 上的自定义区域（Custom Locale）。

1. 点击 AVD 上的首页。
2. 点击启动图标，然后找到并点击 Custom Locale 应用图标打开它。
3. 拖动鼠标到`es - español`选项，点击它并点击选择（SELECT）'ES' 以更改 AVD 的区域设置。

模拟器或设备将其语言设置更改为西班牙语。

# 第 2 章 Welcome 应用

接下来，运行 Welcome 应用，它将安装并启动本地化应用（图 2.33）。当应用开始执行时，Android 会检查 AVD（或设备）的语言设置，确定 AVD（或设备）设置为西班牙语，并使用在`res/values-es/strings.xml`中定义的西班牙语`welcome`和`delete_1`字符串资源。注意，应用名称在应用顶部的标题栏中仍显示英文。这是因为我们没有在`res/values-es/strings.xml`文件中提供`app_name`字符串资源的本地化版本。如果 Android 找不到字符串资源的本地化版本，它将使用`res/values/strings.xml`中的默认版本。

# 将 AVD 恢复为英语

将你的 AVD 恢复为英语：

1. 点击英语首页。
2. 点击启动图标，然后找到并点击 Custom Locale 应用图标打开它。
3. 拖动鼠标到`en-US - en-us`选项，点击它并点击选择（SELECT）'EN-US' 按钮以更改 AVD 的区域设置。

![](img/8c2e5496308864b3b07ddbd4401c4f77_106_0.png)

图 2.33 在 Nexus 6 AVD 上运行的西班牙语 Welcome 应用。

### 2.8.6 在设备上测试西班牙语应用

要在设备上测试，你必须更改设备的语言设置。操作如下：

1. 触摸设备上的图标。
2. 触摸启动图标，然后找到并触摸设置（Settings）应用图标。

### 2.8 应用程序国际化

3. 在设置应用中，滚动到个人（Personal）部分，然后触摸语言与输入（Language & input）。
4. 语言（Language）（列表中的第一项），从语言列表中选择西班牙语（西班牙 - España）。

设备将其语言设置更改为西班牙语并返回语言与输入设置，现在这些设置显示为西班牙语。从 IDE 运行应用，在你的设备上安装并运行本地化版本。

将设备恢复为英语

将你的 AVR（或设备）恢复为英语：

1. 触摸模拟器或设备上的首页。
2. 触摸启动图标以找到并触摸设置（Settings）应用图标——该图标在西班牙语中名为 Ajustes。
3. 触摸文本输入（idioma introduccion de texto）访问语言设置。
4. 触摸语言（idioma），然后在列表中选择英语（美国）。

### 2.8.7 TalkBack 与本地化



`TalkBack`目前支持英语、西班牙语、意大利语、法语和德语。如果你在设备语言指定西班牙语并启用了`TalkBack`的设备上运行`Welcome`应用，当你触摸每个视图时，`TalkBack`将使用西班牙语字符串。

当你将设备切换到西班牙语并启用`TalkBack`时，`Android`将自动下载西班牙语语音合成引擎。如果`TalkBack`不读取西班牙语字符串，说明西班牙语语音合成引擎尚未完成下载和安装。在这种情况下，你应该尝试重试。

## 2.8.8 本地化检查清单

有关本地化你的应用程序的更多信息，请务必查看位于`Android`检查清单：

```
http://developer.android.com/distribute/localization-checklist
```

## 2.8.9 专业翻译

应用开发公司通常配有翻译人员或聘请其他公司进行翻译。在用于发布应用的`Google Play Console`中，你可以找到有关翻译的信息，参见：

```
https://support.google.com/googleplay
```

## 2.9 总结

在本章中，你使用`Android Studio`构建了显示消息和图片的`Welcome`应用。你使用布局编辑器创建了简单的`GUI`，并配置了视图属性。

在布局编辑器中，你将默认布局改为`LinearLayout`，并配置其垂直排列视图。你在`TextView`中显示了并在`ImageView`中显示了图片。你使用了布局编辑器的调板拖放视图。

你了解到`Android`具有帮助障人士使用设备的功能。我们展示了如何启用`Android TalkBack`以让视障用户听到屏幕文本。我们讨论了触摸探索功能，该功能允许用户触摸屏幕以听到屏幕上的内容。对于应用的`ImageViews`，你提供了可供`TalkBack`使用的内容描述。

最后，你学习了如何使用`Android`国际化为你的应用覆盖尽可能广泛的读者。你使用西班牙语字符串对`TextView`的文本和图片的字符串进行了本地化，然后在配置为西班牙语的`AVD`上测试了该应用。

`Android`开发是`GUI`设计与`Java`编码的结合。在下一章中，你将使用布局编辑器可视化开发简单的小费计算器，并使用`Java`编程指定应用的行为。

# 3 小费计算器

介绍`GridLayout`、`EditText`、`SeekBar`、事件处理、`NumberFormat`、自定义应用主题以及`Java`定义应用功能

![](img/8c2e5496308864b3b07ddbd4401c4f77_109_0.png)

## 目标

在本章中你将：

- 更改默认`GUI`主题。
- 自定义`GUI`主题颜色。
- 使用`GridLayout`设计`GUI`。
- 使用组件树窗口向`GridLayout`添加视图。
- 使用`TextView`、`EditText`和`SeekBar`。
- 使用`Java`对象面向编程能力（包括类、对象、接口、匿名内部类和继承）为应用添加功能。
- 程序化地更改`TextView`中的文本。
- 使用事件处理响应用户与`EditText`和`SeekBar`的交互。
- 指定当应用执行时默认显示键盘。
- 指定应用仅支持竖屏方向。

# 74 第 3 章 小费计算器 App

# 目录

- 3.1 引言
- 3.2 测试小费计算器 App
- 3.3 技术概述
  - 3.3.1 课堂活动
  - 3.3.2 Activity 周期方法
  - 3.3.3 AppCompat 库与 AppCompatActivity 类
  - 3.3.4 使用 GridLayout 布局视图
  - 3.3.5 使用布局编辑器和组件属性创建并自定义 GUI
  - 3.3.6 将数字格式化为特定区域的货币和百分比字符串
  - 3.3.7 为 Android EditText 实现 TextWatcher
  - 3.3.8 实现 OnSeekChangeListener 处理滑块指针位置变化
  - 3.3.9 Material 主题
  - 3.3.10 Material Design：高度与阴影
  - 3.3.11 Material Design 清单
  - 3.3.12 在属性窗口中搜索
- 3.4 构建 GUI
  - 3.4.1 GridLayout
  - 3.4.2 创建 TipCalculator 项目
  - 3.4 切换到 GridLayout
  - 3.4 添加 TextViews、EditText 和 SeekBar
- 3.5 自定义视图
  - 3.5 默认主题与自定义主题颜色
    - 3.5.1 父主题
    - 3.5.2 自定义主题颜色
    - 3.5.3 作为常用值属性的样式
- 3.6 添加 App 逻辑
  - 3.6.1 package 声明和 import 语句
  - 3.6.2 AppCompatActivity 子类 MainActivity
  - 3.6.3 类变量与实例变量
  - 3.6.4 重写 Activity 方法 onCreate
  - 3.6.5 实现方法 calculate
  - 3.6.6 匿名内部类实现 OnSeekChangeListener
  - 3.6.7 匿名内部类实现 TextWatcher
- 3.7 AndroidManifest.xml
  - 3.7.1 manifest 元素
  - 3.7.2 application 元素
  - 3.7.3 activity 元素
  - 3.7.4 intent-filter 元素
- 3.8 总结

## 3.1 引言

小费计算器 App（图 3.1）用于计算并显示小费和总金额。你使用数字键盘输入账单金额，App 会默认计算并显示当前百分比（15%）的小费和总账单。你通过移动`SeekBar`在 0% 到 30% 之间选择小费百分比——数值使用特定区域的格式进行显示。图 3.1(b) 显示了用户输入数字 56.32 并小费百分比更改为 25% 后的界面。

我们将从测试 App 开始。然后，我们将回顾创建该 App 所将用的技术。你将使用`Android Studio`的布局编辑器和组件树构建`GUI`。最后，我们将提供 App 的完整`Java`代码并进行详细讲解。

### 关于我们屏幕截图中键盘的说明

图 3.1 中的键盘可能根据你的`AVD`、`Android`版本，或者你是否在设备上安装并选择了自定义键盘而有所不同。为了在屏幕截图中获得更好的对比度，我们在配置`AVD`时使用了深色键盘。操作如下：

1. 触摸`AVD`或设备上的触控 [ ] 图标。

a) 初始 GUI

b) 用户输入金额 56.32 并更改小费百分比为 25% 后的 GUI

![](img/8c2e5496308864b3b07ddbd4401c4f77_111_0.png)

| 移动 SeekBar 指针以更改小费百分比 | 此处显示的小费百分比 | 触摸数字键盘输入账单金额——App 将你的输入除以 10.0 进行计算 | 触摸右侧删除数字 |
|---|---|---|---|
| ![](img/8c2e5496308864b3b07ddbd4401c4f77_111_1.png) | | | |

**图 3.1** 输入账单总并计算小费。

1. 在主屏幕上，触摸启动器图标 ( )，打开设置 App。
2. 在个人区域，触摸语言（Language）和输入（Input）。
3. 在`AVD`上，触摸`Android`键盘 (AOSP)。假设你正在使用标准`Android`键盘。
4. 触摸外观与布局（Appearance & layouts），然后是主题（Theme）。
5. 触摸`Material`切换到黑暗背景。

## 3.2 测试小费计算器 App

### 打开并运行 App

按照节 1.9.1 和 1.9.3 的步骤在`Android Studio`中打开小费计算器项目并在`Nexus AVD`上运行。如果你愿意，按照节 1.9.4 的步骤在`Android`手机上运行。

### 打开账单

通过数字键盘输入账单总额 56.32。如果你输错了，按下键盘上的删除按钮 ( ) 擦除你输入的数字。尽管键盘包含小数点，但 App 配置为你只能输入数字——每当你触摸或删除一个数字时，App 都会读取你目前输入的内容。

1. Active Activity 显示在屏幕上并“拥有焦点”，也就是说，它处于前台。你可以与当前在前台的 Activity 交互。
2. Paused Activity 显示在屏幕上但没有焦点——例如当显示对话框时。你无法与暂停的 Activity 交互，直到它变为 active。
3. Stopped Activity 不显示在屏幕上——它处于后台，并在系统需要内存时被杀死。Activity 进入前台并变为 active。

### 选择小费百分比

使用`SeekBar`——也就是说，当其`GUI`将显示时你可以与之交互。Activity 处于前台。

## 3.3 技术概述

开发者在使用`Android`新功能时面临的一个大挑战是与早期`Android`平台的兼容性。`Google`通过`Android Support Library`引入了许多新功能——一组库允许你在针对当前及过去的 App 使用新的`Android`功能。

其中一个库是`AppCompat Library`，它允许 App 提供 app bar（以前称为 action bar），适用于运行`Android 2.1 (API 7)`及更高版本的设备。`Android` App 模板已使用`AppCompat`库更新，可以在几乎所有`Android`设备上创建新的 App。

### 3.3.1 类

`Android` App 有四种可执行类型：活动、服务、内容提供者（content providers）和广播接收器（broadcast receivers）。在本章中我们将讨论活动，它们是`Activity` (android.app) 的子类。在`Android 3.0`之前，`Activity`通常与屏幕相关。在手机上，每个`Fragment`占据整个屏幕，`Activity`根据用户交互切换`Fragment`。在平板电脑上，活动通常显示多个。

### 3.3.2 Activity 周期方法

在整个生命周期中，`Activity`可以处于几种状态之一：active（即运行）、paused（暂停）或 stopped（停止）。`Activity`响应各种事件在这些状态之间转换：

### 3.3.3 AppCompat 库与 AppCompatActivity 类

`Android Studio`的`Empty Activity`模板将 App 的`MainActivity`类定义为`AppCompatActivity` (android.support.v7.app) 的子类——`Activity`的间接子类，支持在运行当前和旧平台的 App 中使用新的`Android`功能。

### 3.3.4 使用 GridLayout 布局视图

### 3.3.5 使用布局编辑器和组件属性创建并自定义 GUI

### 3.3.6 将数字格式化为特定区域的货币和百分比字符串

### 3.3.7 为 Android EditText 实现 TextWatcher

### 3.3.8 实现 OnSeekChangeListener 处理滑块指针位置变化

### 3.3.9 Material 主题

### 3.3.10 Material Design：高度与阴影

### 3.3.11 Material Design 清单

### 3.3.12 在属性窗口中搜索

## 3.4 构建 GUI

### 3.4.1 GridLayout

## 3.4.2 创建 TipCalculator 项目

### 3.4 切换到 GridLayout

### 3.4 添加 TextViews、EditText 和 SeekBar

## 3.5 自定义视图

### 3.5 默认主题与自定义主题颜色

- 3.5.1 父主题
- 3.5.2 自定义主题颜色
- 3.5.3 作为常用值属性的样式

## 3.6 添加 App 逻辑

- 3.6.1 package 声明和 import 语句
- 3.6.2 AppCompatActivity 子类 MainActivity
- 3.6.3 类变量与实例变量
- 3.6.4 重写 Activity 方法 onCreate
- 3.6.5 实现方法 calculate
- 3.6.6 匿名内部类实现 OnSeekChangeListener
- 3.6.7 匿名内部类实现 TextWatcher

## 3.7 AndroidManifest.xml

- 3.7.1 manifest 元素
- 3.7.2 application 元素
- 3.7.3 activity 元素
- 3.7.4 intent-filter 元素

## 3.8 总结

## 软件工程观察 3.1

从一开始就使用`AppCompat`库创建应用，可以避免在你决定支持旧版本的`Android`以针对更广泛的潜在应用受众时，不得不重新实现代码。

## 软件工程观察 3.2

即使你使用了`AppCompat`库，某些`Android`功能在早期`Android`版本中也是不可用的。`Android`的打印功能仅在`Android 4.4`及更高版本中可用。如果你在应用中使用此类功能，必须将它们限制在支持的平台上，或者在不支持这些`Android`版本上禁用这些功能。

关于`Android Support Libraries`的更多细节，包括何时使用以及如何设置它们：

```
http://developer.android.com/tools/support-library
```

### 3.3.4 使用 GridLayout 布局视图

回想你在布局中安排`GUI`视图。我们使用`GridLayout` (android.widget) 将视图排列在网格的单元格中。单元格可以占据行和列，从而实现复杂的布局。通常，`GridLayout`需要 API 4 或更高版本。`Android Support Library` `GridLayout`以及许多其他视图和布局的替代版本，以便你在旧版`Android`版本中使用它们。有关此库以及如何在你的应用中使用它的更多信息，请访问：

```
http://developer.android.com/tools/support-library/index.html
```

我们将在后面的章节中介绍更多布局和视图——完整列表请访问：

```
http://developer.android.com/reference/android/widget/package-summary.html
```

### 3.3.5 使用布局编辑器、组件树和属性创建并自定义 GUI

你将使用布局编辑器（你在第 2 章中使用过的）和组件树（Component Tree）创建`TextView`、`EditText`和`SeekBar`，并使用 IDE 的属性（Properties）对其进行自定义。

`EditText`——在`GUI`技术中通常称为文本框或文本字段——是`TextView`（第 2 章介绍）的子类，可以显示并接受用户的输入。你可以使用`EditText`进行数字输入，允许用户仅输入数字并限制可以输入的最大位数。

`SeekBar`表示 0-100 范围内的整数，默认允许用户通过移动`SeekBar`的滑块在该范围内选择一个范围。你可以自定义`SeekBar`，使用户从更有限的 0 到 30 范围内选择百分比。

### 3.3.6 将数字格式化为特定区域的货币和百分比字符串

你将使用`NumberFormat` (package java.text) 创建特定区域的货币和百分比字符串——这是应用国际化的重要部分。你还可以使用第 2.7–2.8 节中学的技巧添加辅助功能字符串并将应用的其他文本国际化。

### 3.3.7 实现 TextWatcher 接口处理 EditText 变化

为了响应用户更改应用中`EditText`文本的事件，你将使用匿名类来实现`TextWatcher`接口（来自 package android.text）。特别是，你将使用`OnTextChanged`来显示格式化后的账单，并在用户输入每个数字时计算总额。如果你熟悉匿名内部类，请参考：

```
http://ly/AnonymousInnerClasses
```

### 3.3.8 实现 OnSeekChangeListener 接口处理 SeekBar 滑块位置变化

你将使用另一个匿名类来实现`SeekBar.OnSeekChangeListener`（来自 package android.widget），以响应用户移动`SeekBar`滑块的操作。特别是，你将使用`OnChanged`在用户移动`SeekBar`滑块时显示所需的百分比并计算总额。

### 3.3.9 Material 主题

主题（Theme）为你提供了与`Android`一致的外观效果。你为`Android 5`创建并使用的项目应遵循`Google`的`Material`设计指南。有几种预定义的`Material Design`主题：

- “light”（浅色）主题具有白色栏、白色背景以及黑色或灰色的文本。
- 带有深色栏的“light”主题与上述相同，但应用栏（app bar）默认为黑色白色文字。
- “dark”（深色）主题具有黑色栏、深灰色背景以及白色或浅灰色文本。

对于这些每一个主题，都有：

- 一个`Theme.Material`版本（例如`Theme.Material.Light`），适用于不使用`AppCompat`库且运行在`Android 5`及更高版本上的应用。
- 一个`Theme.AppCompat`版本（例如`Theme.AppCompat.Light`），适用于使用`AppCompat`库且运行在`Android 2.1`及更高版本上的应用。



设计 GUI 时，你可以选择甚至创建自己的主题。对于本章，我们将使用`Theme.AppCompat.LightActionBar`，这是 Android 应用模板中的默认主题。使用 AppCompat 的应用必须使用这些主题之一；否则某些视图将无法正常渲染。有关如何查看示例的更多信息，请访问：

```
http://www.android.com/design/spec/color.html#color-themes https://developer.android.com/training/material/theme.html
```

## 计算器应用

### 3.1 性能

今天许多 Android 手机使用 AMOLED 显示屏。在此类显示屏上，黑色像素会被关闭且不消耗功率。大部分使用黑色主题的应用可以减少约 40% 的功耗（http://bit.ly/AndroidAMOLED）。

### 3.2 Material 设计：高度（Elevation）与阴影

Material 设计指南建议用户界面中的对象应被视作现实世界中的物体。当你查看视图属性时，系统会自动为该视图绘制阴影。较大的高度（elevation）值会产生明显的阴影。对于此应用，我们将看到显示金额的蓝色和橙色`TextView`的高度。Material 指南包含了各种屏幕的建议——例如，对话框的高度为 24dp，菜单的高度为 8dp。其他高度请参阅：

```
http://www.android.com/design/spec/what-is-material/shadows.html
```

### 3.3 Material 设计：颜色

开发者选择应用的颜色以匹配公司的品牌形象。如果你需要自定义颜色，Google 的 Material 设计指南建议你选择一个由主色（primary color，包含三种以上的色调）和强调色（accent color）组成的调色板。主色通常用于屏幕顶部状态栏的颜色，也用于为各种视图（如`SeekBar`、`CheckBox`和`RadioButton`）染色。一旦选择了调色板，你就可以使用 Android 的主题编辑器（第 3.5.2 节）来修改主题颜色。你可以从 Material 设计调色板中找到推荐颜色：

```
http://www.android.com/design/spec/color.html#color-palette
```

该网站允许你从 Material 设计调色板中挑选颜色，然后它会推荐三种主色色调、一种辅助色以及应用文本和图标的颜色。在此应用中，我们将使用以下色块：

- 用于应用栏的蓝色主色
- 用于状态栏的深蓝色主色
- 用于着色`SeekBar`的橙色强调色

### 3.3.12 AndroidManifest.xml

`AndroidManifest.xml`文件在你创建新项目时由 IDE 创建。该文件包含了你使用的许多设置，例如包名和 Activity 名称。你将编辑此文件以添加一个在应用运行时仅支持竖屏的设置。

### 3.3.13 在属性窗口中搜索

属性窗口允许你通过名称或名称部分搜索属性，这可以帮助你找到并设置属性。要执行操作，点击属性窗口的标题栏。列表顶部会出现搜索提示，显示已输入的内容，Android Studio 会高亮列表中匹配你输入的全部或部分属性名称。然后你可以遍历列表查看高亮的属性。

窗口还会滚动到匹配你输入的属性。例如，在搜索`TextView`属性时，如果你输入 "text"，属性窗口将高亮许多属性，但它会专门滚动到`GetTextColor`。

## 第 3 章 小费计算器应用

| | 列 0 | 列 |
|---|---|---|
| 行 0 | 输入金额 | |
| 行 1 | 15% | |
| 行 2 | 小费 | $0.00 |
| 行 3 | 总计 | $0.00 |

**图 3.2** 按行和列标记的小费计算器网格 GridLayout。

**此应用视图的 id 属性值**

图 3.3 显示了视图的 id 属性值。为了清晰起见，我们的命名规范是在 id 属性中使用视图的类名以及对应的 Java 变量名。在第一行中，同一个网格单元格有两个组件——`amountTextView`（初始显示为**输入金额**）隐藏了接收用户输入的`EditText`。一旦用户输入数字，我们就会限制用户的输入仅为以整数数字形式输入的纯数字值，因此用户在输入 $34.56 的账单金额时输入 3456。这确保了用户无法输入无效内容。然而，此金额应该以货币格式显示。每当用户输入每个数字时，我们将金额除以 100.0，并在`amountTextView`中以特定本地的、货币格式显示金额。

```
amountTextView (如你将看到的，
amountEditText 隐藏在此 TextView 之后)
```

![](img/8c2e5496308864b3b07ddbd4401c4f77_118_0.png)

**图 3.3** 小费计算器创建的用 id 属性值标记的视图。

### 3.4.2 创建 TipCalculator 项目

按照第 2.3 节的步骤使用 Empty Activity 模板创建一个新项目。在 Create New Project 对框的 New Project 步骤中指定以下值：

- **Application name：** Tip Calculator
- **Company Domain：** *example.com*（或指定您自己的域名）

### 3.4 构建 GUI (83)

对于 Create New Project 对框中的剩余步骤，使用与第 2.3 节相同的设置。此外，按照第 2.5.2 节的步骤为项目添加图标。一旦项目进入 Android Studio，在布局编辑器中，从虚拟设备下拉列表中选择 Nexus 6（图 2.11）。再次，我们将此作为我们设计的基础，删除 Hello world! TextView。

### 3.4.3 更改为 GridLayout

记住 Empty Activity 的默认布局是`LinearLayout`。在这里，你将其更改为`GridLayout`：

1. 点击布局编辑器底部的 Text，从 Design 视图切换到布局 XML 文本。
2. 在 XML 顶部，将`RelativeLayout`更改为`GridLayout`。
3. 切回布局编辑器的 Design 视图。

#### 为 GridLayout 指定两列和默认边距

记住图 3.2 由两列组成。要指定这一点，在 Component Tree 窗口中选择`GridLayout`，然后将`columnCount`更改为 2——该属性出现在 Properties 窗口附近，与其他布局属性一起。你不需要设置`rowCount`——因为我们在构建网格时它会自动处理。

默认情况下，`GridLayout`单元格周围没有边距（分隔视图的间距）。材料设计指南建议视图之间至少留出 8dp 的间距：

```
http://developer.android.com/design/style/metrics-grids.html
```

`GridLayout`可以强制此间距。在 Component Tree 选中`GridLayout`后，在 Properties 窗口中将`GridLayout`的`useDefaultMargins`（将其设置为零）更改为使用布局单元格周围的边距。

### 3.4.4 添加 TextViews、EditText 和 SeekBar

你将在图 3.2 中构建你的视图。从第 3.4 节中的基本布局和视图开始。你将自定义视图的属性以完成设计。然后，更改其中两个视图的颜色。当你将每个视图添加到 GUI 时，使用图 3.3 中的名称修改其 id 属性属性。你将使用 Component Tree 窗口将视图添加到`GridLayout`。如果你将视图拖到错误位置，可以将其拖动到正确位置。

你还可以在任何方向拖动视图。对于`GridLayout`，布局编辑器会显示一个绿色指南网格来帮助你定位视图。当你拖出一个视图时，布局编辑器会显示如果将其掉在该位置，视图将放置在哪个行和列。

![](img/8c2e5496308864b3b07ddbd4401c4f77_119_0.png)

**防错提示 3.1**

布局编辑器中绿色指南网格的单元格很小。如果你将视图掉在错误位置，布局编辑器可能会更改`GridLayout`的`rowCount`和`columnCount`值，并错误地设置你的`layout:row`和`layout:column`属性值，导致你的 GUI 布局错误。如果是这样，根据你的设计重置`GridLayout`的`rowCount`和`columnCount`，并将视图的`layout:row`和`layout:column`属性值更改为设计所需的行列。

#### 步骤 1：向第一行添加视图

第一行包含`amountTextView`和`amountEditText`——两者占据同一个单元格并跨越两列。每当你向 Component Tree 中的`GridLayout`绘制视图时，视图将被放置在布局的下一个可用单元格中，除非你通过设置视图的`layout:row`和`layout:column`属性值进行指定。

`amountTextView`（初始显示为**输入金额**）隐藏了接收用户输入的`EditText`。一旦用户输入数字，我们就会限制用户的输入仅为以整数数字形式输入的纯数字值，因此用户在输入 $34.56 的账单金额时输入 3456。这确保了用户无法输入无效内容。然而，此金额应该以货币格式显示。每当用户输入每个数字时，我们将金额除以 100.0，并在`amountTextView`中以特定本地的、货币格式显示金额。

## 第 3 章小费计算器应用

...使得按钮不会在此应用中显示。这反过来将阻止你返回到上一个 Activity——这是每个用户都期望的 Android 基础功能。

我们使用 Android 虚拟键盘来演示如何为通用`EditText`选择键盘显示方式。另一种方法是使用代表 0–9 数字的按钮，这些按钮始终显示在屏幕上。我们可以处理它们的点击事件，并使用`EditText`进行字符串操作以跟踪用户的输入。

### 3.4.5 自定义视图

现在你将像第 2.5 节那样自定义视图属性，你还将创建字符串（String）、维度（dimension）和颜色资源。

#### 步骤 5：指定字面文本

接下来，你将为`amountTextView`、`percentTextView`、`labelTextView`和`totalLabelTextView`指定字面文本。当`TextView`的属性为空时，如果指定了`hint`属性值将会显示——该属性通常与`EditText`（`TextView`的子类）配合使用，帮助用户理解`EditText`的用途。我们在`amountTextView`中使用它，告诉用户输入账单金额：

1. 在组件树（Component Tree）中，选择`amountTextView`属性窗口中定位它的`hint`属性。
2. 点击省略号 (...) 按钮右侧属性的值以显示资源对话框。
3. 在对话框中，点击“New Resource”（新建资源），然后选择“New Value...”（新建值），并选择资源名称为`enter_amount`，资源值为“Enter Amount”。保留其他设置并点击 OK 以创建新字符串资源，并将其设置为`amountTextView`的`hint`。

重复这些步骤，使用图 3.5 所示的值为`percentTextView`、`labelTextView`和`totalLabelTextView`设置属性。

| 视图 | 资源名称 | 资源值 |
| --- | --- | --- |
| percentTextView | tip_percentage | 15% |
| labelTextView | tip | Tip |
| totalLabelTextView | total | Total |

> 图 3.5 | 字符串资源值和名称。

#### 步骤 6：左侧列 TextView 右对齐

在图 3.2 中，`percentTextView`、`labelTextView`和`totalLabelTextView`是右对齐的。你可以如下对对齐这三个`TextView`：

1. 选择`percentTextView`。
2. 在 Windows/Linux 上按住 Ctrl 或在 Mac 上按住 Command 并点击`labelTextView`和`totalLabelTextView`。现在所有三个`TextView`都选中了。
3. 展开`layout:gravity`属性节点并勾选右侧选框。

### 3.4 构建 GUI 87

#### 步骤 7：配置 amountEditText

在最终的应用中，`amountEditText`隐藏在`EditText`之间，并配置为仅允许用户输入数字。选择`amountEditText`并设置以下属性：

1. 将`digits`属性设置为`0123456789`——这允许仅输入数字，尽管数字键盘包含其他字符，如减号 (-)、逗号 (,) 和句号 (.)。
2. 将`maxLength`属性设置为`6`。这限制账单金额最多为六位数——因此支持的最大账单金额为 9999.9。

#### 步骤 8：配置 amountEditText

为了完成`amountEditText`的格式化，选择它并设置以下属性：

1. 删除`text`属性的默认值（“Medium Text”）——我们将根据用户的输入在此处程序化显示文本。
2. 展开`layout:gravity`节点并将`fill`设置为`1 horizontal`。这表示`EditText`应该占据该`GridLayout`中剩余的所有水平空间。
3. 将`background`属性（指定视图的背景颜色）设置为新的颜色资源`amount_background`，其值为`#BDBEF`——这是 Google Material Design 色板中的一种蓝色。
4. 为`EditText`添加内边距（padding）。视图的内边距指定了内容周围的额外空间。`padding`属性指定内边距应应用于视图内容的顶部、右、底部和底部。你也可以单独设置每个内边距。点击`padding`属性，然后点击省略按钮。创建一个名为`textview_padding`的新资源，值为`2dp`。你稍后会使用此资源。
5. 最后，通过将`elevation`属性设置为值为`4dp`的新维度资源`elevation`为视图添加阴影。我们选择此值是为了演示，强调阴影效果。

#### 步骤 9：配置 percentEditText

注意到`percentEditText`的对齐位置比`percentSeekBar`高。如果垂直居中，看起来会更好。要做到这一点，展开`layout:gravity`属性节点，将`center`值设置为`vertical`。回想你之前将`layout:gravity`设置为`right`。在布局 XML 中将这些设置组合为：

```
android:layout_gravity="center_vertical|right"
```

使用竖线 (|) 分隔多个`layout:gravity`值——在这种情况下，表示`EditText`应该在网格单元内垂直居中并右对齐。

#### 步骤 10：配置 percentSeekBar

选择`percentSeekBar`并配置以下属性：

1. 默认情况下，`SeekBar`的范围为 0 到 100，其当前值由`progress`属性表示。此应用允许 0 到 30 的小费百分比，并指定默认为 15%。将`SeekBar`的`max`属性设置为 30，`progress`设置为 15。
2. 展开`layout:gravity`属性节点并将`fill`设置为`horizontal`，以便`SeekBar`占据其所在`GridLayout`列中的所有水平空间。
3. 将`layout:height`属性设置为新的维度资源 (`seekbar_height`)，值为`40dp`。

#### 步骤 11：配置 textView

为了完成`textView`和`totalTextView`的格式化，选择它们并设置以下属性：

1. 删除`text`属性的默认值（“Medium Text”）——我们将根据用户的输入在此处程序化显示文本。
2. 展开`layout:gravity`节点并将`fill`设置为`horizontal`，以便每个`TextView`占据所有水平空间。
3. 将`background`属性设置为新的颜色资源`result_background`，其值为`#FFE0E2`——这是 Material 色板中的一种浅橙色。
4. 将`gravity`属性设置为`center`，以便计算的小费和总额将居中。
5. 展开`padding`属性节点，点击省略按钮，选择之前创建的维度资源`textview_padding`。
6. 最后，通过将`elevation`属性设置为创建的`elevation`资源为视图添加阴影。

## 第 3 章 小费计算器 App

![](img/8c2e5496308864b3b07ddbd4401c4f77_126_0.png)

主题的`colorPrimary`、`colorPrimaryDark`和`colorAccent`属性的颜色块

**图 3.7** | 主题编辑器（Theme Editor）在左侧显示实时预览，右侧显示主题属性。

![](img/8c2e5496308864b3b07ddbd4401c4f77_126_1.png)

当前选择颜色的十六进制值——设计规范显示推荐颜色及其深色的十六进制值



选择 **Material Blue 500** 作为新的`colorPrimary`值

**图 3.8** | 为`colorPrimary`选择 Material Blue 500 颜色块。

## 3.5 默认主题与自定义主题颜色

- 3. 接下来，点击主题编辑器中的`colorPrimaryDark`颜色选择器以显示资源（Resources）对话框。主题编辑器会识别新的`colorPrimary`值，并自动显示一个颜色选择器，其中包含你应该用于`colorPrimaryDark`的推荐`colorPrimary`深色——在这种情况下，为 Material Blue 700。点击该颜色选择器（图 3.9），然后点击 OK。

![](img/8c2e5496308864b3b07ddbd4401c4f77_127_0.png)

图 3.9 为`colorPrimaryDark`选择 Material Blue 700 颜色选择器。

- 4. 接下来，点击主题编辑器中的`colorAccent`颜色选择器以显示资源对话框。此后，编辑器会识别到你更改了`colorPrimary`值，并显示各种互补强调色的选择器。在对话框中，点击 Orange accent 400 颜色，然后点击 OK 更改`colorAccent`的值（图 3.10），再次点击 OK。

你已经完成了 App 设计，它看起来应该如图 3.11 所示。

## 3.5.3 作为样式的常用属性值

正如你之后看到的 App 一样，样式资源可以定义应用于多个视图的常用属性值。你可以通过设置视图的`style`属性将样式应用于给定视图。你对样式进行的任何后续更改将自动应用到使用该样式的视图。例如，考虑我们在 3.4.5 节第 11 中配置相同的`tipTextView`和`totalTextView`。我们可以定义一个样式资源来指定`layout:gravity`、`background`、`gravity`、`padding`和`elevation`属性值，然后将两个 TextView 的`style`属性都指向同一个样式资源。

# 第 3 章 小费计算器 App

![](img/8c2e5496308864b3b07ddbd4401c4f77_128_0.png)

选择 Orange accent 400 作为新的`colorAccent`

图 3.10 | 为`colorAccent`选择 Orange accent 400 颜色块。

![](img/8c2e5496308864b3b07ddbd4401c4f77_128_1.png)

图 3.11 | 完成的设计。

## 3.6 添加 App 的逻辑

`MainActivity`类（图 3.12–18）实现了小费计算器 App 的逻辑。它计算小费和总账单金额，并以特定地区的货币格式显示它们。要查看该文件，在 Project（项目）窗口中，展开`app/java/com.deite1.tipcalculator-node`并双击`MainActivity.java`。你需要输入图 3.12–3.18 中的大部分代码。

### 3.6.1 package 和 import 语句

图 3.12 显示了`MainActivity.java`中的 package 语句和 import 语句。第 3 行的 package 语句是在创建项目时插入的。在 IDE 中打开 Java 文件时，import 语句是折叠的——左侧会显示一个。你可以点击`+`查看完整的 import 语句列表。

```java
// MainActivity.java
// 根据小费百分比计算账单总额
package com.deil.calculator;

import android.os.Bundle; // 用于保存状态信息
import android.support.v7.app.AppCompatActivity; // 基类
import android.widget.Watcher; // 用于处理 EditText
import android.widget.TextWatcher; // EditText 监听器
import android.widget.EditText; // 用于账单金额输入
import android.widget.SeekBar; // 用于更改小费百分比
import android.widget.SeekChangeListener; // SeekBar 监听器
import android.widget.TextView; // 用于显示文本
```

图 3.12 | MainActivity package 和 import 语句使用。

5–14 行包含了 App 使用的类：

- `android.os`中的`Bundle`类（第 5 行）存储信息的键值对——通常表示 App 状态或需要在我们之间传递的数据。当另一个 App 准备出现在屏幕上时（例如，当用户接到电话或启动另一个 App 时），Android 会给当前执行的程序一个将其保存到内存中的机会。当运行时返回屏幕时，例如，它会将之前保存的状态`Bundle`传递给 Activity 的`onCreate`方法（节 3.6.4）。然后，App 可以使用保存的状态返回到另一个 App 激活时的状态。我们使用`Bundle`传递数据。

- `android.support.v7.app`中的`AppCompatActivity`类（第 6 行）提供了基础生命周期方法。

- `android.widget`中的`Watcher`用于处理 EditText。

- `android.widget`中的`TextWatcher` EditText 监听器。

- `android.widget`中的`EditText`用于账单金额输入。

- `android.widget`中的`SeekBar`用于更改小费百分比。

- `android.widget`中的`SeekChangeListener` SeekBar 监听器。

- `android.widget`中的`TextView`用于显示文本。

## 3.6.2 MainActivity 的子类

`MainActivity`类（图 3.12–18）实现了小费计算器 App 的逻辑。它计算小费和总账单金额，并以特定地区的货币格式显示它们。要查看该文件，在 Project（项目）窗口中，展开`app/java/com.deite1.tipcalculator-node`并双击`MainActivity.java`。你需要输入图 3.12–3.18 中的大部分代码。

## 3.6.3 类变量与实例变量

图 3.14 显示了`MainActivity`的变量。

## 3.6.4 覆盖 Activity 的 onCreate 方法

`onCreate`方法（图 3.15）是在 Activity 启动时由系统调用的。该方法初始化 Activity 的实例变量和视图。该方法应该尽可能简单以便快速加载。事实上，如果 App 加载超过五秒，操作系统将显示 ANR（无响应）对话框——让你能够强制终止 Activity。

## 第 3 章小费计算器 App

### onCreate 的 Bundle 参数

在执行过程中，用户可能会更改设备的配置——例如，旋转设备、连接蓝牙键盘或弹出硬件键盘。为了获得良好的体验，App 应该在这些配置更改期间保持流畅运行。当系统调用`onCreate`时，它会向 Activity 传递一个`Bundle`参数。如果有任何状态，你可以在 Activity 的`onPause`或`onSaveInstanceState`方法中保存（在随后的应用中演示）。第 35 行调用了类的`onCreate`方法，这在重写`onCreate`时是必要的。

### 生成的 R 类常量

当你构建 GUI 并添加资源（如 .xml 文件中的字符串或 activity .xml 文件中的视图）时，IDE 会生成一个包含嵌套类的 R 类，这些嵌套类代表了项目 res 文件夹中的每种类型的资源。这些嵌套类是静态的，因此你可以通过`R.ClassName`在代码中访问它们。由于 R 的嵌套类，IDE 生成了静态 final int 常量允许你程序化地引用资源（稍后将讨论）。R 的嵌套类包括：

- `R.drawable`包含任何 drawable 项目（如图片）

- `R.id`包含 XML 布局文件中的视图

- `R.layout`包含项目中的每个布局文件（如 activity_main）

- `R.string`包含 strings.xml 文件中的每个常量

### 加载 GUI (Inflating)

`setContentView`（第 36 行）接收`R.layout.activity_main`常量，这表示 activity_main.xml 文件。`setContentView`方法使用此 XML 文档并将其转换为 App 的 GUI。这就是加载 GUI。

### 获取组件引用

一旦布局加载完成，你就可以获取各个组件的引用以便程序化地与它们交互。要实现这一点，使用`findViewById`方法，它返回一个表示视图的 int。每个视图的`R.id`常量是在设计 GUI 时确定的。例如，`amountEditText`的文本是`R.id.amountEditText`。第 39–42 行程序化地更改 App 中的 TextViews 引用。第 39 行获取`amountTextView`的引用，当用户输入金额时更新；第 40 行获取`percentTextView`的引用，当用户更改百分比时更新；第 41–42 行获取 TextViews 的引用，显示计算的小费和总额。

### 在 TextView 中显示初始值

第 43–44 行通过调用`currencyFormat`方法，将`tipTextView`和`totalTextView`的文本设置为 0，以符合特定地区的货币格式。每个 TextView 的文本会在用户输入金额时发生变化。

### 注册监听器

第 47–49 行获取`amountEditText`并使用`addTextChangedListener`方法注册`TextWatcher`，当用户更改内容时响应事件。我们将此监听器（图 18）定义为匿名内部类，并将其赋值给实例变量`amountEditTextWatcher`。虽然我们在第 49 行定义了匿名内部类，但这样做使代码更易读。

### 软件工程观察

在大型方法中定义匿名内部类，不如将其定义为`private final`变量，这样你的代码更易调试、修改和维护。第 52–53 行通过`seekBar.setOnSeekChangeListener`方法注册`OnSeekChangeListener`对象，当用户移动 SeekBar 滑块时响应事件。图 17 将此监听器定义并赋值给实例变量`seekBarListener`。

### 注意：Android Data Binding

Android 现在支持 Data Binding 库，你可以针对 Android 2.1（API 7）及以上版本。你可以在 XML 文件中包含 data-binding 表达式来动态更新 App 中的接口数据。此外，每个 XML 文件都包含带有`id`的视图，你可以创建一个 "Binding" 类的实例来替换复杂的`findViewById`。每个实例变量的名称基于`activity_main.xml`的名称，"Binding" 类名是`MainBinding`。

在编写本文时，Data Binding 库处于早期测试阶段，data-binding 表达式的语法和 Android Studio 工具发生了重大变化。你可以在此处了解更多关于 Android 数据绑定：

https://developer.android.com/tools/data-binding/guide.html

### 3.6.5 MainActivity 方法 calculate

`calculate`方法（图 16）由 EditText 和 SeekBar 的监听器调用，当用户更改金额时更新小费和总额 TextView。第 60 行在`percentTextView`中显示百分比。第 63–64 行根据`billAmount`计算小费和总额。

![](img/8c2e54963088643b07ddbd4401cf77_133_0.png)

```java
// 计算并显示小费和总额
private void calculate() {
    // 计算并显示小费和总额
    percentTextView.setText(currencyFormat.format(percent));

    // 计算小费和总额
    double tip = billAmount * percent;
    double total = billAmount + tip;

    // 显示小费和总额
    tipTextView.setText(currencyFormat.format(tip));
    totalTextView.setText(currencyFormat.format(total));
}
```

### 3.6.6 实现接口的匿名内部类

第 72–86 行（图 17）创建一个响应 SeekBar 事件的匿名内部类对象。该对象被赋值给实例变量`seekBarListener`。第 54 行（图 15）注册了该对象来处理事件。



```java
// SeekBar 事件的监听器对象
final OnSeekChangeListener seekBarListener = new OnSeekChangeListener() {
    @Override
    public void onProgressChanged(SeekBar seekBar, int progress, boolean fromUser) {
        // 更新进度
        percent = progress / 100.0;
        calculate();
    }

    @Override
    public void onStartTouch(SeekBar seekBar) {
    }

    @Override
    public void onStopTouch(SeekBar seekBar) {
    }
};
```

### 重写接口的 `onProgressChanged` 方法

第 75–86 行（图 17）实现了 `OnSeekChangeListener` 方法。每当 `SeekBar` 滑块位置改变时，就会调用 `onProgressChanged` 方法。第 78 行使用方法的参数计算百分比值。第 79 行调用 `calculate` 来重新计算并显示小费和总额。

Java 要求你必须重写所实现的接口中的每一个方法。此 App 不需要知道用户何时开始移动 `SeekBar` 滑块（`StartTouch`）或停止移动（`StopTouch`），因此我们为每个方法提供了一个示例体以履行接口合约。

### Android Studio 重写方法工具

Android Studio 可以为你创建从父类重写的方法或要实现的方法。当你将光标置在类体中，然后选择 `Code > Override Methods...` 选项时，IDE 会显示“选择方法”对话框，列出当前类中可以重写的所有方法。该列表包含了类层次结构中的继承方法以及任何实现的接口的方法。

### 3.6.7 实现 `TextWatcher` 的匿名内部类

图 18 的第 90–114 行创建一个响应 `amountEditText` 事件的匿名内部类对象，并将其赋值给实例变量 `amountEditTextWatcher`。第 49 行（图 15）注册了该对象以监听文本变化时产生的 `amountEditTextWatcher` 事件。

```java
// EditText 变化事件的监听器对象
private TextWatcher amountEditTextWatcher = new TextWatcher() {
    // 用户修改金额时调用
    @Override
    public void onTextChanged(CharSequence s, int start, int before, int count) {
        try { // 获取金额并显示格式化的货币值
            billAmount = Double.parseDouble(s.toString()) / 100.0;
            amountView.setText(currencyFormat.format(billAmount));
        } catch (NumberFormatException e) { // 如果 s 为空或非数字
            amountView.setText("");
            billAmount = 0.0;
        }
        calculate(); // 更新小费和总额 TotalViews
    }

    @Override
    public void beforeTextChanged(CharSequence s, int start, int count, int count) {
    }

    @Override
    public void afterTextChanged(Editable s) {
    }
};
```

图 3.18 | 实现 `textWatcher` 的匿名内部类。（第 1/2 部分）

## 第3章 小费计算器 App

```java
108 @Override
109 public void afterTextChanged(Editable s) {
111 @Override
112 public void beforeTextChanged(
113 CharSequence s, int start, int count, int after) {
114 };
115 }
```

图 3.18 | 实现 `TextWatcher` 接口的匿名类（2 部分中的 2 部分。）

### 重写 `TextWatcher` 接口的 `onTextChanged` 方法

当 `amountEditText` 中的文本发生更改时，就会调用 `onChanged` 方法（第 92–106 行）。在这个示例中，我们只使用了 `CharSequence`，它包含了 `amountEditText` 文本的副本。其他参数表示从上一个之前的文本长度开始的字符数。

第 97 行将来自 `amountEditText` 的输入转换为以分（单位的数字的整数，因此我们将该值除以 `100.0` 以获得实际账金额——例如，如果用户输入 `2495`，账金额为 `24.95`。第 98 行显示更新后的账金额，并将 `billAmount` 设置为 `0.0`。

### `amountEditTextWatcher` 的其他方法

此应用不需要知道文本发生了哪些更改（`beforeChanged`），或者文本是否已经更改（`afterTextChanged`），因此我们简单地重写了 `TextWatcher` 接口的每个方法并留有空体（第 108–113 行），以符合约定。

## 3.7 `AndroidManifest.xml`

在本节中，你将修改 `AndroidManifest.xml` 文件，以指定此 Activity 仅支持设备方向，并且当 Activity 出现在屏幕上或导航回 Activity 时，应始终显示虚拟键盘。要打开清单文件，双击 Project 窗口中 `manifest` 文件夹下的 `AndroidManifest.xml`。图 3.19 显示了带有我们更改的完整清单文件——文件的其余部分是由 Android Studio 在我们创建应用项目时生成的。我们将讨论清单可能包含的一些方面、它的属性及其值，请访问：

```
http://developer.android.com/guide/topics/manifest/manifest-intro
1 <?xml version="1.0" encoding="utf-8"?>
2 <manifest xmlns:android="http://schemas.android.com/apk/res/android"
3 package="com.deitel.tipcalculator">
```

图 3.19 | `AndroidManifest.xml` 内容（2 部分中的 1 部分。）

```xml
<application
  android:allowBackup="true"
  android:icon="@mipmap/ic_launcher"
  android:label="@string/app_name"
  android:supportsRtl="true"
  android:theme="@style/AppTheme">
  <activity
    android:name="MainActivity"
    android:label="@string/app_name"
    android:orientation="portrait"
    android:windowSoftInputMode="stateAlwaysVisible">
    <intent-filter>
      <action android:name="android.intent.action.MAIN" />
      <category android:name="android.intent.category.LAUNCHER" />
    </intent-filter>
  </activity>
</application>
```

图 39 | `AndroidManifest.xml` 内容（2 部分中的 2 部分。）

### 3.7.1 `manifest` 元素

`manifest` 元素（第 2–24 行）表示此 XML 文件代表应用的清单。该元素的 `package` 属性指定了应用的 Java 包名，该名称是在创建项目时配置的（第 3.4.2 节）。记住，对于提交到 Google Play Store 的应用，包名用作应用的唯一标识。

### 3.7.2 `application` 元素

`manifest` 元素嵌套的 `application` 元素（第 5–21 行）指定了应用的属性，包括：

- **`android:allowBackup`**: 是否由 Android 自动备份应用数据，以便稍后将数据恢复到设备或新设备。

- **`android:icon`**: 你在启动器中点击以执行应用的图标。

- **`android:label`**: 应用名称，通常显示在启动器中图标下方，并且在应用执行时通常显示在应用栏中。

- **`android:supportsRtl`**: 界面是否可以向右翻转以适应阿拉伯语和希伯来语等从右到左的语言。

- **`android:theme`**: 决定应用视图默认外观的主题。

嵌套在 `application` 元素中的元素定义了应用的组件，例如其 Activity。

### 3.7.3 `activity` 元素

应用嵌套的 `activity` 元素（第 10–20 行）描述了一个 Activity。一个应用可以有多个 Activity，其中一个在用户点击启动器中的图标执行应用时被指定为该应用的默认 Activity。每个 `activity` 元素至少指定了以下内容：

- **`android:name`**: Activity 的名称。“`MainActivity`”符号是“`com.example.MainActivity`”的简写（其中 `com.example` 是你在创建项目时指定的域名的反转）。

- **`android:label`**: Activity 的名称。当 Activity 在屏幕上时，这通常显示在应用栏中。对于单 Activity 应用，名称通常与应用名称相同。

对于 `MainActivity`，我们添加了以下属性：

- **`android:orientation`**: 通常，大多数应用都应该支持竖屏和横屏模式。在竖屏模式下，设备的尺寸是垂直的。在计算器应用中，将设备旋转到横屏会导致数字键盘遮挡计算器界面的大部分。基于此，我们将此属性设置为 `portrait`。

- **`android:windowSoftInputMode`**: 这种情况下，我们将此属性设置为 `stateAlwaysVisible`。

### 3.7.4 `intent-filter` 元素

Intents 是用于组件之间通信的机制。清单中的 `intent-filter` 过滤了哪些 Intent 可以处理。

#### 应用间通信

Intents 使用的一个示例是协调不同的应用。考虑如何使用 Intents 进行共享：

- 应用在清单中声明其共享功能。通过发布共享 Intent，Android 找到相应的应用。

- Android 查找已安装的应用程序。

- 如果只有一个应用，Android 执行该应用。

- 如果有多个应用，Android 显示一个列表并让用户做出选择。

这种松耦合方法的用处是，共享应用的开发者不需要考虑所有可能的共享应用。通过发布共享 Intent，Android 自动支持用户安装或未来安装的应用。

#### 执行应用

使用 Intents 的另一个示例是启动 Activity。当你点击启动器中的应用图标时，你的意图是执行该应用。在这种情况下，启动器发出 Intent 执行应用的主 Activity（稍后讨论）。

#### 确定要执行的 Activity

Android 使用清单中的信息来确定哪些 Activity 响应 Intent 以及每个 Activity 可以处理哪些 Intent。在清单中，`activity` 嵌套 `intent-filter` 元素（图 3.19，第 16–20 行）决定哪些 Intent 类型可以启动 Activity。如果 Intent 只匹配一个 Activity 的 `intent-filter`，Android 执行该 Activity。如果有多个匹配，Android 会呈现一个列表，用户可以选择应用，然后执行该应用中的相应 Activity。

Android 还会将 Intent 传递给 Activity，其中包含 Activity 可用于执行任务的数据。例如，照片编辑应用可以使用共享照片 Intent 来指定照片。

## 第 3 章 小费计算器应用

你使用 Android Studio 的组件树（Component Tree）窗口构建了应用的 GUI，自定义了布局的 XML，并使用主题编辑器（Theme Editor）自定义了 IDE 在创建项目时设置的 `Theme.AppCompat.DarkActionBar` 主题颜色。我们展示了 `MainActivity` 的代码，它是 `AppCompat` 的子类（Activity 的间接子类），定义了应用的逻辑。

在应用中，你使用 `GridLayout` 将视图排列成行和列。`MainActivity` 类代表了 Java 面向对象的能力，包括类、对象、方法、接口、匿名内部类和继承。我们解释了将其从 XML 文件填充（inflating）到屏幕表示的本质。你学习了 Android 的 `Activity` 类和部分 Activity 生命周期。在 `onCreate` 方法中，你重写了 `onCreate` 方法，使用 `findViewById` 获取应用程序化交互的每个视图的引用。你定义了一个实现 `TextView` 的匿名内部类，以便用户在 `EditText` 中输入金额时，应用可以计算新的小费和总额。你还定义了一个实现 `SeekBarChangeListener` 接口的匿名内部类，以便用户在移动 `SeekBar` 改变小费时，应用可以计算新的小费和总额。

最后，你编辑了 `AndroidManifest.xml` 文件，指定 `MainActivity` 仅支持竖屏模式，且 `MainActivity` 应该始终显示键盘。我们还讨论了 Android Studio 在你创建项目放在清单中的其他元素。

在第 4 章中，你将构建“国旗测验”应用，在该应用中，用户将看到国旗图形，并必须从 2、4、6 或 8 个选项中选择国家。你将使用菜单和复选框来自定义测验，指定猜测选项的数量并将标记限制在世界的特定区域。

## 4 国旗测验应用

Fragments、Menus、Preferences、Explicit Intents、Handler、AssetManager、Tweened Animations、Animators、Toasts、Color State Lists、多设备方向布局、用于调试的错误消息日志

### 目标

在本章中，你将：

- 使用 `Fragments` 在手机和平板电脑的 `Activity` GUI 中更充分地利用可用屏幕空间。

- 在应用栏上显示设置图标，使用户能够访问应用的用户偏好。

- 使用 `PreferenceFragment` 自动管理和持久化应用的偏好。

- 使用 `SharedPreferences.Editor` 修改与应用关联的键值对。

- 使用 `assets` 子文件夹组织图像资源并使用 `AssetManager` 对其进行操作。

- 定义动画并将其应用到 `View` 上。

- 使用 `Handler` 调度一个在 GUI 线程执行的未来任务。

- 使用 `Toasts` 向用户简要显示消息。

- 使用显式 `Intent` 启动特定的 `Activity`。

- 使用来自 `java.util` 包的集合。

- 为多个设备方向定义布局。

- 使用 Android 的日志机制记录错误消息。

## 第 4 章 国旗测验应用

### 提纲

- 4.1 引言
- 4.2 测试国旗测验应用
- 4.2.1 配置测验设置
- 4.2.2 进行测验
- 4.3 技术概览
- 4.3.1 菜单 (Menus)
- 4.3.2 碎片 (Fragments)
- 4.3.3 Fragment 生命周期方法
- 4.3.4 管理 Fragments
- 4.3.5 偏好 (Preferences)
- 4.3.6 `assets` 文件夹
- 4.3.7 资源文件夹 (Resource Folder)
- 4.3.8 支持不同的屏幕尺寸和分辨率
- 4.3.9 确定显示消息的设备
- 4.3.10 用于处理用户输入的 Toasts
- 4.3.11 使用 `Handler` 在未来执行 `Runnable`
- 4.3.12 将动画应用到 `View`
- 4.3.13 使用 `ViewController` 创建圆形动画器
- 4.3.14 根据视图的样式指定颜色
- 4.3.15 警对话框 (`AlertDialog`)
- 4.3.16 记录异常消息
- 4.3.17 通过事件监听器启动另一个 Activity
- 4.3.18 数据结构
- 4.3.19 Java 7 特性
- 4.3.20 `AndroidManifest.xml`
- 4.4 创建项目、资源文件和其他类
- 4.4.1 创建项目
- 4.4.2 空 Activity 模板布局
- 4.4.3 配置 Java 7 支持
- 4.4.4 将国旗图像添加到项目
- 4.4.5 `strings.xml` 和格式化字符串资源
- 4.4.6 `arrays.xml`
- 4.4.7 `colors.xml`
- 4.4.8 `button_text_color.xml`
- 4.4.9 编辑 `menu_main.xml`
- 4.4.10 创建国旗摇动动画



- 4.4.11 用于指定应用设置 `preferences.xml`
- 4.4.12 添加类 `SettingsActivity` 和 `SettingsActivityFragment`
- 4.4.13 构建应用的 GUI
- 4.5 竖屏设备下的 `activity_main.xml` 布局
- 4.5.2 设计 `Fragment_main.xml`
- 4.5.3 图形布局
- 4.5 平板电脑的 `activity_main.xml` 布局
- 4.6 `MainActivity` 类
- 4.6.1 `package` 语句和 `import`
- 4.6.2 字段 (Fields)
- 4.6.3 重写方法 `onCreate`
- 4.6.4 重写方法 `onStart`
- 4.6.5 重写方法 `onOptions`
- 4.6.6 重写方法 `onOptionsItemSelected`
- 4.6.7 实现 `SeekBarChangeListener` 的匿名内部类
- 4.7 `Fragment` 类
- 4.7.1 `package` 语句和 `import`
- 4.7.2 字段
- 4.7.3 重写方法 `onCreateView`
- 4.7.4 重写方法 `updateRows`
- 4.7.5 重写方法 `updateRegions`
- 4.7.6 重写方法 `resetQuiz`
- 4.7.7 重写方法 `addToFlag`
- 4.7.8 重写方法 `getCountryName`
- 4.7.9 重写方法 `animate`
- 4.7.10 实现点击的匿名内部类
- 4.7.11 `disable`
- 4.8 `SettingsActivity` 类
- 4.9 `SettingsFragment` 类
- 4.10 `AndroidManifest.xml`

## 4.1 引言

国旗测验应用显示一个国旗图形，用户必须从 2、4、6 或 8 个选项中选择国家。你将使用菜单和复选框来自定义测验，指定猜测选项的数量并将标记限制在世界的特定区域。

如你所见，应用还允许你控制测验难度，即指定显示 2、4、6 或 8 个按钮，并选择包含在测验中的区域。在竖屏模式下，应用在应用栏上显示设置图标 (⚙️)。当你点击此图标时，应用会显示一个独立的屏幕（另一个 Activity），用于设置按钮数量和区域。在平板电脑横屏模式下，应用使用不同的布局，始终显示设置和测验。

### 4.2 测试国旗测验应用

你现在将测试 **Flag Quiz** 应用。要执行此操作，请打开 Android Studio，从书籍示例文件夹中的`FlagQuiz`文件夹打开 **Flag Quiz** 应用，然后在 AVD 或设备上运行该应用。这将构建项目并运行应用。

#### 4.2.1 配置测验设置

当你首次安装并运行应用时，测验配置为显示四个猜测按钮，并从世界的*所有*区域选择国旗。对于本次测试，你将更改应用选项以仅从北美选择国旗，或者保持应用每页四个猜测按钮的默认设置。

在手机或竖屏模式下的 AVD 上，点击应用栏上的设置图标 ⚙️ 以查看*设置*屏幕（图 4.3(a)）。在*横屏*模式下的设备或平板 AVD 上，应用的设置出现在屏幕左侧（图 4.2）。点击 **Number of Choices** 显示用于选择每个国旗旁显示的按钮数量的对话框（图 4.3(b)）。

（屏幕。）默认情况下，选中了 4——我们使用了此默认设置。为了让测验更简单，你可以选择 2；或者为了让测验更具挑战性，你可以选择 6 或 8。点击 CANCEL（或触摸对话框外的屏幕）返回到设置屏幕。

a) 用户点击“选项数量”时的菜单

b) 显示选项数量选项的对话框

![](img/8c2e5496308864b3b07ddbd4401c4f77_145_0.png)

**图 4.3 旗帜测验**设置屏幕和**选项数量 (Number of Choices)**对话框。

接下来，点击**区域 (Regions)**（图 4.4(a)）显示代表世界地区的复选框（图 4.4(b)）。当应用首次执行时，默认所有区域都是启用的，我们在应用中放置的每面旗帜都可以随机选择进行测验。点击**非洲（Africa）、南美洲（South America）、欧洲（Europe）、大洋洲（Oceania，包括澳大利亚、新西兰及周边岛屿）**旁边的复选框取消选中——这将这些区域的国家从测验中排除。点击 OK 保存设置。在手机、平板电脑或竖屏模式下的 AVD 上，点击返回按钮返回测验屏幕并使用更新后的设置开始新测验。在横屏模式的平板设备或平板 AVD 上，屏幕右侧会立即显示带有更新后设置的新测验。

a) 用户点击“区域”时的菜单

b) 显示区域的对话框

![](img/8c2e5496308864b3b07ddbd4401c4f77_146_0.png)

![](img/8c2e5496308864b3b07ddbd4401c4f77_146_1.png)

**图 4.4** 旗帜测验屏幕和**区域**对话框（取消选中**非洲、亚洲、欧洲、大洋洲和南美洲**后）。

#### 4.2.2 进行测验

测验根据你选择的答案数量开始，且限于包含你选择的区域的旗帜。点击你认为每面旗帜对应的数字猜测按钮来完成测验。

**做出正确选择**

如果选择正确（图 4.5a），应用将禁用所有答案按钮并在屏幕底部显示国家名称，随后跟一个感叹号（图 4.5b）。经过短时间延迟后，应用将加载下一面旗帜，并将旗帜和一组新的答案按钮动画显示在屏幕上。应用通过圆形揭示效果从当前测验问题过渡到下一个问题：

- 首先，一个大直径圆收缩到屏幕上，直到其直径为零，隐藏当前测验问题的旗帜和猜测按钮。
- 接着，圆的直径从零开始增大，直到下一个问题的旗帜和猜测按钮在屏幕上完全可见。

a) 选择正确答案

b) 显示正确答案

![](img/8c2e5496308864b3b07ddbd4401c4f77_147_0.png)

被点击的按钮（美国维尔京群岛）具有更高的投影，因此阴影更明显

猜对后所有按钮均已禁用

![](img/8c2e5496308864b3b07ddbd4401c4f77_147_1.png)

用绿色显示正确答案

**图 4.5** | 用户选择正确答案以及显示正确答案。

**做出错误选择**

- 禁用对应的国家名称切换按钮
- 使用动画让旗帜水平抖动
- 在屏幕底部用红色显示“Incorrect!（错误！）”

### 完成测验

测验根据你选择的答案数量开始，且仅包含你选择的区域的旗帜。点击你认为每面旗帜对应的数字猜测按钮来完成测验。

在手机、平板电脑或竖屏模式下的 AVD 上，点击返回按钮返回测验屏幕并使用更新后的设置开始新测验。在横屏模式的平板设备或平板 AVD 上，屏幕右侧会立即显示带有更新后设置的新测验。

a) 选择错误答案

b) 显示“错误！”

![](img/8c2e5496308864b3b07ddbd4401c4f77_147_0.png)

被点击的按钮（美国维尔京群岛）具有更高的投影，因此阴影更明显

猜对后所有按钮均已禁用

![](img/8c2e5496308864b3b07ddbd4401c4f77_147_1.png)

用红色显示“错误！”

**图 4.5** | 用户选择错误答案以及显示“错误！”

### 完成测验

测验根据你选择的答案数量开始，且仅包含你选择的区域的旗帜。点击你认为每面旗帜对应的数字猜测按钮来完成测验。

（注：此处部分文本在原文中重复，已根据指令要求去重并逻辑进行翻译）

## 4.3 技术概述

本节介绍了构建旗帜测验应用时使用的功能。

### 4.3.1 菜单

当用户创建设置时，应用会以竖屏模式显示选项。在应用中，我们将通过设置偏好文件来创建额外的菜单。在后续应用中，你将看到如何使用 Android Studio 的矢量资源添加设计图标。选项对象是`Menu`类（package `android.view`）。你重写`onCreate`并使用方法参数添加菜单项——通过编程或解析 XML 文档来实现。当用户选择菜单项时，Activity 方法`ItemSelected`响应该选择。

### 4.3.2 Fragment

`Fragment`通常代表 Activity 用户界面的可重用部分，但也代表可用的逻辑。这使用 `Fragment` 创建用户界面。像 Activity 一样，每个 `Fragment` 都有生命周期，并提供了你可以重写的生命事件方法。在本应用中，我们将：

- `onCreate`（在 `SettingsActivity` 中重写）在 `Fragment` 被创建时调用。当应用加载父布局时创建 `MainActivity`。
- `onCreateView`（在 `MainActivityFragment` 中重写）在`onCreate`之后调用，返回一个包含 `Fragment` GUI 的 `View`。当你接收此视图时，将使用`LayoutInflater`从预定义的 XML 布局中编程加载 GUI。

`Fragment` 可以将自己的菜单项添加到宿主 Activity 的菜单中。像 Activity 类一样，`Fragment` 拥有生命周期方法 `onCreate` 和事件处理方法 `ItemSelected`。

我们将在书中遇到时讨论 `Fragment` 生命周期方法。

### 4.3.4 管理 Fragment

Activity 通过`Fragments`（package `android.app`）管理其 `Fragment`——通过 Activity 的`getFragmentManager`方法访问。如果 Activity 需要与声明在 Activity 布局中具有 ID 的 `Fragment` 交互，Activity 可以通过`byId`获取 `Fragment` 的引用。正如你将在第 9 章看到的，`FragmentManager` 可以使用`FragmentTransactions`动态添加、删除和切换 `Fragment`。

为了向后兼容，AppCompat 必须使用`package android.support.v4.app`中的 `FragmentManager` 版本，而不是`package android.app`中的。`AppCompatActivity`类继承了此方法，因此使用来自 Android 支持库的`FragmentManager`。

### 4.3.5 偏好

在第 4.2.1 节中，你通过更改设置自定义了测验。这些设置以键值对的形式持久存储在文件中——每个键都允许你查找一个循环出现的值。文件中的键必须是字符串，值是字符串或原始类型值。此类文件通过`SharedPreferences`(android.content) 类的对象进行操作，且该文件仅供创建它的应用程序访问。

`PreferenceFragment`使用`Preference`对象（package `android.preference`）来管理设置并通过`SharedPreferences`对象将它们存储在文件中。此应用使用`Preference`子类`ListPreference`来管理每个旗帜显示的猜测按钮数量，并使用`Preference`子类`MultiSelectPreference`来管理测验包含的区域。`ListPreference`创建单选按钮，只能选择其中一个（4.3(b)）。`MultiSelectPreference`创建复选框，可以选中任意数量（4.4(b)）。你使用`PreferenceManager`对象（package `android.preference`）来访问并与应用的默认`SharedPreferences`文件交互。

你将直接与应用的默认`SharedPreferences`文件交互：

- 当启动测验时，你将查询应用的设置以确定要显示的猜测按钮数量以及选择旗帜的区域。
- 当用户更改区域时，应用程序将确保至少选择了一个区域；否则测验中将没有可以包含的旗帜。如果没有选择，应用程序将编辑区域设置以选择北美。

要修改`SharedPreferences`文件的内容，你使用`SharedPreferences.Editor`对象（4.6.7）。

### 4.3.6 assets 文件夹

此应用的旗帜在需要时加载到应用中，并位于应用的 `assets` 文件夹中。为了将图像添加到项目中，我们将从文件系统将每个区域的文件夹复制到应用的 Project 窗口中（4.4.4）。图像位于`app/images`文件夹中，与书籍示例在一起。

与应用的`drawable`文件夹不同，`assets`要求其图像内容位于每个文件夹的根层级；它们可以组织在子文件夹中——我们为每个区域的旗帜维护了一个子文件夹。`assets`子文件夹中的文件通过`AssetManager`(package `android.content.res`) 访问，它可以提供指定子文件夹中所有文件的列表，并用于访问每个资源。

### 4.3.7 资源文件夹

在第 2.4.4 节中，你学习了应用 `res` 文件夹下的`drawable`、`layout`和`values`子文件夹。在此应用中，你还会使用`menu`、`anim`、`color`和`xml`资源文件夹。图 4.8 展示了这些文件夹以及`animator`和`raw`文件夹。

我们从 http://www.free-country-flags.com 获取了图像。

## 第 4 章 旗帜测验应用

| 资源子文件夹 | 说明 |
| --- | --- |
| `anim` | 以`anim`开头的文件夹名称包含定义补间动画的 XML 文件，这些动画可以随时间改变对象的透明度、大小、位置和旋转角度。你将在第 4.4.10 节中定义一个动画，然后在第 4.7.10 节中播放它以创建抖动效果，为用户的错误猜测提供反馈。 |
| `animator` | 以`animator`开头的文件夹名称包含定义属性的 XML 文件，这些属性会随时间改变对象属性的值。在 Java 中，属性通常实现为带有 setter 和 getter 的实例变量。 |
| `color` | 以`color`开头的文件夹名称包含定义颜色状态的 XML 文件——各种状态的颜色列表，例如按钮的状态（未按下、按下、启用、禁用等）。我们将在第 4.4.8 节中使用颜色列表来定义猜测按钮在启用或禁用时的备用颜色。 |
| `raw` | 以`raw`开头的文件夹名称包含资源文件（如音频），这些文件作为流被读取到应用程序中。我们将在第 6 章中使用资源来播放它们。 |
| `menu` | 以`menu`开头的文件夹名称包含描述菜单内容的 XML 文件。当你创建一个项目时，IDE 会自动识别带有 Settings（设置）选项的菜单。 |
| `xml` | 以`xml`开头的文件夹名称包含不属于其他类别的 XML 文件——通常是应用程序使用的 XML 文件。在第 4.4.11 节中，你将创建一个表示应用设置所显示的偏好设置 XML 文件。 |

**图 4.8** | 项目 `res` 文件夹中的其他子文件夹。

### 4.3.8 支持不同的屏幕尺寸和分辨率

在第 2.5 节中，你学习了 Android 设备具有各种屏幕尺寸、分辨率和像素密度（每英寸点数或 DPI）。你还学习了通常会提供多种分辨率的图像和其他资源。

对于此 Activity，你将使用最小屏幕宽度和方向来确定使用哪个布局——一个用于手机，另一个用于平板电脑。限定符名称（在磁盘上）格式为：

```
name-qualifiers
```

其中 `qualifiers` 由一个或多个由破折号 (-）分隔的限定符组成。目前有 19 种限定符类型可供用于指定 Android 何时选择特定资源。有关所有资源的完整描述，请访问：

http://developer.android.com/guide/topics/resources/providing-resources

### 4.3.9 确定设备方向

在此应用中，当应用程序运行在手机尺寸设备上或竖屏模式时，我们使用一个`Configuration`对象（package `android.content.res`）实例，它包含`ORIENTATION_PORTRAIT`或`ORIENTATION_LANDSCAPE`来确定设备的当前方向。

### 4.3.10 用于显示消息的 Toast

`Toast`（package `android.widget`）短暂显示一条消息，然后消失。`Toast`通常用于显示错误消息或信息消息。我们使用 `Toast` 来：

- 指明测验将在用户更改设置后重置。
- 指明必须至少选择一个区域。

### 4.3.11 使用 Handler 执行后续操作

当用户做出正确猜测时，我们使用`Handler`(package `android.os`) 来执行延迟操作。在延迟几毫秒后，应用将显示正确答案。

### 4.3.12 将动画应用于 View

当用户做出错误选择时，应用通过使用`Animation`(package `android.view.animation`) 显示旗帜。我们使用`AnimationUtils`静态方法加载动画并重复次数，并通过调用`startAnimation`方法在`ImageView`上执行动画。

### 4.3.13 使用 AnimationUtils 创建圆形展开动画器

动画可以使应用程序更具视觉吸引力。在这个应用中，在用户做出正确选择后不久，程序会将旗帜和答案按钮动画移出屏幕，并将下一个旗帜和答案按钮移入屏幕。为了实现这一点，在第 4.7.9 节中，你将使用`AnimationUtils`类通过调用`createCircularReveal`方法创建一个圆形展开动画器。然后，你通过调用动画器的`duration`和`start`方法设置动画的持续时间并启动动画。动画表现为一个缩小或放大的圆形窗口，其中显示某个 UI 元素。

### 4.3.14 通过颜色状态列表根据 View 的状态指定颜色



颜色状态文件（color state file）定义了一个根据 View 状态改变颜色的颜色资源。例如，你可以为 `Button` 定义一个颜色状态列表，为 `Button` 的按下、未按下、已启用和禁用状态指定不同的颜色。同样，对于 `CheckBox`，你可以为它的已勾选或未勾选状态指定不同的颜色。

在程序应用中，当用户猜测错误时，程序会禁用所有猜测按钮。在禁用的按钮中，白色文字是默认的。为了解决这个问题，你需要定义一个颜色状态列表，根据 `Button` 的已启用或禁用状态指定 `Button` 的文本颜色（第 4.4.8 节）。有关颜色状态列表的更多信息，请访问：

```
http://developer.android.com/topics/resources/color-list-resource.html
```

### 4.3.15 AlertDialog

你可以通过 `AlertDialog`（`android.app` 包）向用户显示消息、选项和确认。`AlertDialog` 是一个模态对话框——当它显示时，用户在将其关闭（关闭）之前无法与程序交互。正如你所看到的，你可以使用 `AlertDialog.Builder` 创建并配置 `AlertDialog`，然后使用它来创建 `AlertDialog`。

`AlertDialog` 可以显示按钮、复选框、单选按钮和项目列表，用户可以通过触摸它们来响应对话框的消息。它们还可以显示自定义 GUI。标准的 `AlertDialog` 可能有三个按钮：

- 否定操作——取消指定的动作，通常标记为 `CANCEL`（取消）或 `NO`（否）。当对话框中有多个按钮时，它是最左侧的按钮。
- 积极操作——接受指定的动作，通常标记为 `OK`（确定）或 `YES`（是）。当对话框中有多个按钮时，它是最右侧的按钮。
- 中性操作——此按钮表示用户不想取消或接受对话框指定的动作。例如，一个要求用户注册以获得额外功能的程序可能会提供一个 `REMIND ME LATER`（稍后提醒我）中性按钮。

## 4.3 技术概览

我们在测验结束时使用 `AlertDialog` 向用户显示测验内容（第 4.7.10 节），并允许用户点击按钮来重置测验。你将实现 `DialogInterface.OnClickListener`（`android.content` 包）接口来处理按钮事件。你可以了解更多关于 Android 对话框的信息：

```
http://developer.android.com/guide/topics/ui/dialogs.html
```

### 4.3.16 记录异常消息

当发生异常或你想跟踪代码执行某些重要方面时，你可以使用 Android 内置的日志机制为调试目的记录消息。Android 提供了 `Log`（`android.util` 包），它包含代表不同详细程度消息的静态方法。记录的消息可以在 Android Device Monitor 的 `LogCat` 标签页底部或使用 Android 日志工具查看。你可以从 Android Studio 中选择 `View > Tool Windows > Android` 打开 Android Device Monitor。有关记录消息的更多信息，请访问：

```
http://developer.android.com/tools/debugging/debugging-log.html
```

### 4.3.17 通过显式 Intent 启动另一个 Activity

正如第 3.7.4 节中学到的，Android 使用一种称为意图消息（intent messaging）的技术在同一个应用内的 Activity 之间或不同应用的 Activity 之间进行通信。Android 中声明的每个 Activity 都会通过意图过滤器指定其能够处理的内容。在 `AndroidManifest.xml` 中声明的每个 Activity 都会通过意图过滤器指定其能够处理的内容。

## 显式与隐式 Intent

此应用使用显式 Intent（Explicit Intent）。当它以竖屏模式运行时，使用 `Intent` 启动相应的 Activity。如果系统找不到处理该 `Intent` 的 Activity，将抛出 `ActivityNotFoundException`。你可以通过首先使用 `Intent` 来避免此异常发生。有关 `Intent` 的更多信息，请访问：

```
https://developer.android.com/guide/components/intents.html
```

### 4.3.18 Java 数据结构

此应用使用来自 `java.util` 包的数据结构。我们使用 `Collections.shuffle` 来随机化文件名的顺序（第 4.7.7 节）。我们使用 `ArrayList<String>` 来持有文件名。我们还使用 `Set<String>` 来存储地区。我们使用泛型类型的变量。

### 软件工程观察

使用泛型变量引用集合对象，以便轻松更改结构而不影响代码的其他部分。

![显示 `ArrayList<String>` 变量的图像](some_path_to_image_156.png)

### 4.3.19 Java SE 7 特性

Android 完全支持 Java 7。完整的特性列表请访问：

```
http://www.oracle.com/technetwork/java/jdk7-notes-418459
```

使用了以下 Java 7 特性：

- 泛型实例的类型推断——如果你能从上下文推断出对象的类型，可以在创建对象时将 `<type>` 替换为 `<>`。例如，在 `FlagQuizMainActivityFragment` 中，实例变量 `quizCountries` 被声明为 `List<String>`，因此编译器知道它必须包含 `String`。因此，当我们创建相应的 `ArrayList` 时，可以使用 Java 7 的菱运算符 `<>`，编译器会推断出 `<>` 是 `<String>`。

- try-with-resources 语句——与其声明资源、在块中使用它并在 `finally` 块中关闭它，你可以在块的参数中声明资源并在块中使用它。当程序控制离开块时，资源会被隐式关闭。例如，在 `FlagQuizMainActivityFragment` 中，我们使用 `InputStream` 读取应用图像文件的字节并创建 `Drawable`（第 4.7.7 节）。

```
try (InputStream stream =
    assets.open(region + "/" + nextImage + ".png")) {
    // 可能会抛出异常的代码
}
```

## 4.4 创建项目、资源文件和额外类

将 Activity 添加到项目中（第 4.4.12 节）时，IDE 会将其添加到 manifest 文件。有关 `AndroidManifest.xml` 的完整细节，请访问：

```
http://developer.android.com/guide/topics/manifest/manifest-intro.html
```

我们将在后续的应用程序中介绍 `AndroidManifest.xml` 文件的其他方面。

## 4.4 创建项目、资源文件和额外类

在本节中，你将创建项目并配置 Flag Quiz（国旗测验）应用使用的字符串、数组、颜色和动画资源。你还将为第二个 Activity 创建额外的类，以便你更改应用程序的设置。

### 4.4.1 创建项目

按照第 2.3 节的步骤创建一个新项目。在 New Project（新建项目）对话框的 New Project 步骤中指定以下值：

- 应用程序名称（Application name）：`Flag Quiz`
- 公司域名（Company Domain）：`dete1.com`（或指定你自己的域名）

对于 New Project 对话框中的剩余步骤，使用与 2.3 节相同的设置，但在 Add Activity to Mobile（向移动设备添加 Activity）步骤中，选择 Blank Activity（空 Activity）而不是 Empty Activity（空 Activity），并勾选 Use a Fragment（使用 Fragment）复选框。为你的 Activity、布局名称、标题和资源名称定义名称，然后点击 Finish（完成）创建项目。IDE 将创建 Java 和资源文件，包括：

- 一个 `MainActivity` 类
- 一个名为 `MainActivityFragment` 的 Fragment 子类，由 `MainActivity` 显示
- `MainActivity` 和 `MainActivityFragment` 的布局文件，以及
- 一个定义 `MainActivity` 选项菜单的 `menu_main.xml` 文件。

此外，按照第 2.5.2 节的步骤向项目添加图标。

当你在 Android Studio 中打开项目时，IDE 会显示来自虚拟设备列表的 `content_main.xml`（见图 2.11）——我们再次使用此设备作为设计的依据。

### 4.4.2 Blank Activity 布局模板

Blank Activity 模板是一个后兼容的应用程序模板（适用于 Android 2.1 及更高版本），它使用了 Android Design Support Library（Android 设计支持库）的功能。此模板可以在不使用 Fragment 的情况下使用。当你选择 Fragment 选项时，IDE 会创建名为 `activity_main.xml`、`content_main.xml` 和 `fragment_main.xml` 的布局。

### activity_main.xml

`activity_main.xml` 中的布局包含一个 `CoordinatorLayout`（来自 Android Design Support Library 的 `android.support.design.widget` 包）。Android Studio 模板中定义的 `CoordinatorLayout` 布局通常包含一个应用栏，定义为 `Toolbar`（包 `android.support.v7.widget`）。模板显式地定义了应用，以兼容不支持应用栏的早期 Android 版本。`CoordinatorLayout` 还有助于管理嵌套视图的 Material Design（材料设计）交互——当视图动画移出屏幕时，它会将 GUI 的部分移开，当视图动画移回屏幕时，将 GUI 恢复到原始位置。

`activity_main.xml` 布局通过 `<include>` 元素在（XML）中嵌入了在 `content_main.xml` 中定义的 GUI。默认布局还包含一个 `FloatingActionButton`（悬浮操作按钮）——它源自 Android Support Library，其层级高于 GUI 其他组件，因此它“浮”在 GUI 之上。`FloatingActionButton` 通常强调用户可以通过触摸按钮执行的重要操作。每个基于 Activity 模板的应用程序都包含一个 `FloatingActionButton` 和其他材料设计特性。你将在第 7 章中使用 `FloatingActionButtons`。

### content_main.xml

`content_main.xml` 布局定义了 `MainActivity` GUI 中出现在应用下方、系统上方的部分。当你选择 Blank Activity 模板的 Fragment 选项时，此文件仅包含一个 `<fragment>` 元素，用于定义 `fragment_main.xml` 中定义的 `MainActivity` GUI。如果你不选择模板的 Fragment 选项，此文件将定义一个包含 `TextView` 的 `RelativeLayout`，由你定义 `MainActivity` 的 GUI。

### fragment_main.xml

`fragment_main.xml` 布局仅在你选择 Blank Activity 模板的 Fragment 选项时定义。当使用 Fragment 时，这里是你定义 GUI 的地方。

### 准备设计 GUI

此应用不需要 `FloatingActionButton`，因此打开 `activity_main.xml` 布局，并删除布局右下角的亮粉色按钮。此外，在组件树（Component Tree）中选择 `CoordinatorLayout`，并将布局的 id 设置为 `coordinatorLayout`。打开 `fragment_main.xml` 布局，移除应用定义的 `Hello World!` `TextView`。

### 4.4.3 配置 Java SE 7 支持

我们在此应用中使用 Java 7 编程特性。默认情况下，新的 Android Studio 项目使用 Java SE 6。要使用 Java SE 7：

1. 右键点击项目的 `app` 文件夹，选择 Open Module Settings（打开模块设置）以打开 Project Structure（项目结构）窗口。
2. 确保选中顶部的 Properties（属性）选项卡。
3. 在 Source Compatibility（源兼容性）和 Target Compatibility（目标兼容性）下拉列表中选择 `1.7`，然后点击 OK。

### 4.4.4 将国旗图像添加到项目

按照以下步骤创建 `assets` 文件夹并将国旗添加到项目：

1. 右键点击项目文件夹，选择 `New > Directory`（文件夹），在对话框中输入 `assets`。
2. 在 `assets` 文件夹中创建一个名为 `flags` 的文件夹。
3. 将国旗图像拖入该文件夹。

### 4.4.5 strings.xml 和格式化字符串

`strings.xml` 定义了应用程序中的字符串。在第 3.4.5 节中，你学习了如何使用资源创建字符串。对于此应用，我们将使用格式化字符串。

1. 打开 `res/values` 文件夹下的 `strings.xml`。
2. 在 `strings.xml` 中添加以下资源：

```xml
<resources>
    <string name="app_name">Flag Quiz</string>
    <string name="question">Which country's flag is this %1$s?</string>
    <string name="score">Score: %1$d</string>
    <string name="correct_answer">Correct!</string>
    <string name="wrong_answer">Incorrect!</string>
    <string name="restart">Restart</string>
    <string name="game_over">Game Over</string>
</resources>
```

在 `question` 字符串中，`%1$s` 是一个占位符，表示第一个参数是字符串。`%1$d` 表示第一个参数是整数。

### 4.4.6 arrays.xml

技术上，`res/values` 文件夹中的所有资源都可以定义在同一个文件中。然而，为了方便管理类型的资源，通常会为每种类型使用单独的文件。例如，按照惯例，数组定义在 `arrays.xml` 中，颜色在 `colors.xml` 中，字符串在 `strings.xml` 中，数值定义在 `values.xml` 中。此应用使用了定义在 `arrays.xml` 中的三个数组：

```xml
<resources>
    <array name="regions_list">
        <item>Africa</item>
        <item>Asia</item>
        <item>Europe</item>
        <item>North America</item>
        <item>Oceania</item>
        <item>South America</item>
    </array>
    <array name="list_for_settings">
        <item>Africa</item>
        <item>Asia</item>
        <item>Europe</item>
        <item>North America</item>
        <item>South America</item>
    </array>
    <array name="guesses_list">
        <item>2</item>
        <item>4</item>
        <item>6</item>
        <item>8</item>
    </array>
</resources>
```

- `regions_list` 指定了用下划线分隔的地区名称——这些值用于从相应的文件夹加载图像名称，并作为用户在 `SettingsActivityFragment` 中选择的地区的值。
- `list_for_settings` 指定了用空格分隔的地区名称——这些值用于在 `SettingsActivityFragment` 中向用户显示地区复选框。
- `guesses` 指定了字符串 `2`、`4`、`6` 和 `8`——值用于在 `SettingsActivityFragment` 中显示单选按钮，允许用户选择按钮的数量。

图 4.10 显示了三个数组资源的名称和元素值。

| 数组资源名称 | 值 |
| :--- | :--- |
| `regions_list` | `Africa`, `Asia`, `Europe`, `North_America`, `Oceania`, `South_America` |



| `list_for_settings` | Africa, Asia, Europe, North America, South America |
| --- | --- |
| `guesses_list` | 2, 4, 6, 8 |

## 4.4 创建项目、资源文件和额外类

要创建`arrays.xml`并配置数组资源，请执行以下步骤：

1. 在项目的`res`文件夹中，点击`values`文件夹，然后选择 **New > Values resource file** 显示“新建资源文件”对话框。由于你右键点击了`values`文件夹，该对话框已预配置为在`values-folder`中添加 Values 资源文件。

2. 在 **File name** 中指定`arrays.xml`并点击 **OK** 创建该文件。

3. Android Studio 没有为数组提供字符串资源编辑器，因此你需要编辑 XML 来创建字符串资源。

每个数组资源具有以下格式：

```
<string-array name="resource_name">
  <item>first element value</item>
  <item>second element value</item>
  ...
</string-array>
```

图 4.11 显示了完成后的 XML 文件。

```
1 <xml version="1.0" encoding="utf-8?>
2 <resources>
3 
4 <string-array name="regions_list">
5   <item>Africa</item>
6   <item>Asia</item>
7   <item>Europe</item>
8   <item>North_America</item>
9   <item>Oceania</item>
10  <item>South_America</item>
11 </string-array>
12 
13 <string-array name="regions_list_for_settings">
14   <item>Africa</item>
15   <item>Asia</item>
16   <item>Europe</item>
17   <item>North_America</item>
18  <item>Oceania</item>
19  <item>South America</item>
20 </string-array>
21 
22 <string-array name="guesses_list">
23   <item>2</item>
24   <item>4</item>
25   <item>6</item>
26   <item>8</item>
27 </string-array>
28 
29 </resources>
```

图 4.11 `arrays.xml`定义了国旗测验 App 中使用的字符串数组资源。

## 第4章 国旗测验 App

### 4.4.7 colors.xml

此应用用绿色显示正确答案，用红色显示错误答案。对于任何其他资源，颜色资源都应该在 XML 中定义，这样你就可以在不修改 Java 源码的情况下更改颜色，并可以使用 Android 资源功能为各种场景提供颜色资源（不同的区域、夜间和白天等）。通常，颜色定义在`colors.xml`文件中，该文件由大多数 Android Studio 模板为你创建，或者在你使用第 2.5.7 节所示的技术定义颜色时创建；否则你必须创建该文件。

Blank Activity 模板已包含一个`colors.xml`文件，定义了主题的主色、主深色和强调色资源。在这里，你将为正确和错误答案添加颜色，并修改应用的强调色。为此，你将直接编辑 XML，而不是像你在第 3.6 节中那样使用编辑器来修改主题颜色。

从`res/values`文件夹打开`colors.xml`（图 4.12）并编辑第 6 和第 7 行。此外，将名为`colorAccent`的颜色（第 5 行）的十六进制值从`#FF0481`（应用模板默认的粉色）更改为`#44A8FF`（比`colorPrimary`和`colorPrimary`使用的浅蓝色）。注意 IDE 中，XML 编辑器会在每个颜色左侧显示颜色切换器。

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
  <color name="colorPrimary">#F3F51B5</color>
  <color name="colorPrimaryDark">#F03F9F</color>
  <color name="colorAccent">#44A8FF</color>
  <color name="correct_answer">#0CC00</color>
  <color name="incorrect_answer">#FF0000</color>
</resources>
```

### 4.4.8 button_text_color.xml

如第 4.13 节所述，当为 Button 提供颜色状态列表资源（无论是前景还是背景）时，将根据 Button 的状态选择颜色列表中的适当颜色。对于此应用，你将定义 Button 在启用和禁用状态下的文本颜色。要创建颜色状态列表资源文件：

1. 右键点击项目的`res`文件夹，然后选择 **New > Android resource file** 显示“新建资源文件”对话框。

2. 在 **File name** 中指定`button_text_color.xml`。

3. 在 **Resource type** 下拉菜单中选择 **Color**。根元素将自动变为`selector`，目录名将自动变为`color`。

4. 点击 **OK** 创建文件。`button_text_color.xml`文件将被置于`res/color`文件夹中，IDE 会自动创建该文件夹。

5. 将图 4.13 所示的文本添加到文件中。

### 4.4.10 创建摇晃动画

在本节中，你将创建一个在用户猜测正确时摇晃旗帜的动画。我们将在第 4.7.10 节中展示应用如何使用此动画。要创建动画：

1. 右键点击项目的`res`文件夹，然后选择 **New > Android resource file** 打开新建资源文件对话框。

2. 在 **Name** 字段输入`correct_shake.xml`。

3. 在 **Resource type** 下拉菜单中选择 **Animation**。IDE 会更改根元素并将目录名改为`anim`。

4. 点击 **OK** 创建文件。XML 文件将立即打开。

IDE 未为动画提供编辑器，因此你必须修改图 4.14 中文件的 XML 内容。

```xml
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
android:interpolator="android:anim/decelerate_interpolator">
<translate duration="100" android:fromXDelta="0"
android:toXDelta="-5%" />
<translate duration="100" android:fromXDelta="-5%"
android:toXDelta="5%" startOffset="-100" />
<translate duration="100" android:fromXDelta="5%"
android:toXDelta="0" startOffset="200" />
</set>
```

动画由一系列三个平移动画（translate animations）组成。平移动画使 View 在其父容器内进行移动。Android 还支持属性动画（property animations），你可以对任何对象的任何属性进行动画处理。

第一个平移动画（6–7）在指定时间内将 View 从起始位置移动到结束位置。`android:fromDelta`属性是动画开始时 View 的偏移量，`android:toDelta`属性是动画结束时 View 的偏移量（单位为像素）。这些属性可以具有：

- 绝对值（像素）
- 动画 View 大小的百分比
- 动画父容器大小的百分比

对于`android:fromDelta`属性，我们指定了 0 的绝对值。对于`android:toDelta`属性，我们指定了 -5p，这表示 View 应向左（负号方向）移动父容器宽度的 5%（由 p 表示）。要移动 View 宽度的 5%，只需移除 p 即可。`android:duration`属性指定了动画以毫秒为单位的持续时间。因此，6–7 中的动画在 100 毫秒内将 View 向左移动其父容器宽度的 5%。

第二个动画（9–10）从第一个动画结束的地方继续，在 100 毫秒内将 View 从 -5p 移动到 0p。如果同时应用动画（即并行执行），你可以使用`android:startOffset`属性来指定动画应在未来的的多少毫秒后开始。这可以用于对一组动画进行顺序化。在这种情况下，第二个动画在第一个动画之后 100 毫秒后开始。第三个动画（12–13）与第二个动画相同，但方向相反，并且它在第一个动画开始后 200 毫秒后开始。

### 4.4.1 用于指定应用偏设置的 preferences.xml

在本节中，你将创建`preferences.xml`文件，SettingsActivity 使用该文件显示应用的偏设置。创建文件的步骤：

1. 右键点击`res`文件夹，然后选择 **New > Android resource file** 以打开资源文件对话框。

2. 在 **File name**（文件名）中输入`preferences.xml`。

3. 在 **Resource type**（资源类型）下拉列表中选择 **XML**。**Root element**（根元素）将自动更改为`PreferencesScreen`，它表示显示偏设置的屏幕。**Directory name**（目录名称）将自动更改为`xml`。

4. 点击 **OK** 创建文件。`preferences.xml`文件将在自动创建的文件夹中生成。

5. 如果 IDE 没有自动打开`res/xml/preferences.xml`，请双击该文件打开它。

你有两种类型的偏设置需要管理：`ListPreference`和`MultiSelectListPreference`。每个偏设置都有一些属性，我们在图 4.15 中解释了 ListPreference，在图 4.16 中解释了 MultiSelectListPreference。要将这些偏设置及其属性添加到文件中，你需要编辑该 XML 文件。图 4.17 显示了完成后的 XML 文件。

| 属性 (Property) | 值 (Value) | 说明 (Description) |
| --- | --- | --- |
| entries | @array/guesses_list | 将显示在选项列表中的字符串数组。 |
| entryValues | @array/guesses_list | 与 Entries 属性中的选项关联的值数组。选中的项的值将存储在应用的 SharedPreferences 中。 |
| key | pref_numberOfChoices | 存储在应用 SharedPreferences 中的偏设置名称。 |
| title | @string/number_of_choices | 在 GUI 中显示的偏设置标题。 |
| summary | @string/number_of_choices_description | 显示在标题下方的偏设置摘要描述。 |
| persistent | true | 偏设置在应用终止后是否持久化——PreferenceFragment 类在每次更改时都会立即持久化该偏设置。 |
| defaultValue | 4 | Entries 属性中默认选中的项目。 |

**图 4.15** ListPreference 属性值。

| 属性 (Property) | 值 (Value) | 说明 (Description) |
| --- | --- | --- |
| entries | @array/regions_list_for_settings | 将显示在选项列表中的字符串数组。 |
| entryValues | @array/regions_list | 与 Entries 属性中的选项关联的值数组。所有中的项都将存储在应用的 SharedPreferences 中。 |
| key | pref_regionsToInclude | 存储在应用 SharedPreferences 中的偏设置名称。 |
| title | @string/world_regions | 在 GUI 中显示的偏设置标题。 |
| summary | @string/world_regions_description | 显示在标题下方的偏设置摘要描述。 |
| persistent | true | 偏设置在应用终止后是否持久化。 |
| defaultValue | @array/regions_list | 此偏设置的默认值数组——在这种情况下，所有区域都将默认选中。 |

**图 4.16** MultiSelectListPreference 属性值。

```xml
<?xml version="1.0" encoding="utf-8"?>
<PreferenceScreen xmlns:android="http://schemas.android.com/apk/res/android">
  <Preference
    android:entries="@array/guesses_list"
    android:entryValues="@array/guesses_list"
    android:key="pref_numberOfChoices"
    android:title="@string/number_of_choices"
    android:summary="@string/number_of_choices_description"
    android:persistent="true"
    android:defaultValue="4" />
  <MultiSelectListPreference
    android:entries="@array/regions_list_for_settings"
    android:entryValues="@array/regions_list"
    android:key="pref_regionsToInclude"
    android:title="@string/world_regions"
    android:summary="@string/world_regions_description"
    android:persistent="true"
    android:defaultValue="@array/regions_list" />
</PreferenceScreen>
```

**图 4.17** `preferences.xml`定义了偏设置。



你有两种类型的偏设置需要管理：`ListPreference` 和 `MultiSelectListPreference`。每个偏设置都有一些属性，我们在图 4.15 中解释了 `ListPreference`，在图 4.16 中解释了 `MultiSelectListPreference`。要将这些偏设置及其属性添加到文件中，你需要编辑该 XML 文件。图 4.17 显示了完成后的 XML 文件。

## 第 4 章 旗帜测验 App

IDE 创建了布局文件 `activity_settings.xml`、`content_settings.xml` 和 `fragment_settings.xml`，以及代码 `SettingsActivity.java` 和 `SettingsFragment.java`。打开 `activity_settings.xml` 并删除你在 4.4 中做的 `FloatingActionButton`。

## 4.5 构建应用的 GUI

在本节中，你将构建偏设置 GUI。在之前的章节中，你了解了如何创建 GUI 并配置组件属性，因此 4.5.1–4.5.4 主要侧重于新功能。

### 4.5.1 竖屏模式下的 `activity_main.xml` 布局

在之前的应用中，你在 `activity_main.xml` 中定义了 GUI。当使用 `Fragment` 时，Activity 的 GUI 通常显示一个或多个 `Fragment`。在本应用中，`MainActivity` 的布局——`main.xml`——使用 XML 中的 `<include>` 元素包含 `content_main.xml` 定义的 GUI。`content_main.xml` 布局显示 `fragment_main.xml` 定义的 `MainActivityFragment`。所有三个文件都在创建项目时由 IDE 创建。

`content_main.xml` 文件包含一个 `<fragment>` 元素作为根元素。在运行时，`MainActivityFragment` 将填充 `<fragment>` 元素占据的部分。

根据 Android 设计指南，屏幕边缘与应用内容之间的建议间距为 16dp；但许多应用（如游戏）使用全屏。

我们在代码中使用多个 `Fragment`。为了在引用这些 `Fragment` 时更具可读性，我们更改了这个 `<fragment>` 元素的属性。操作如下：

1. 在 Design 标签中打开 `content_main.xml`。
2. 在 Component Tree 窗口选择 IDE 默认的 `fragment`。
3. 在 Properties 窗口中将 `id` 设置为 `quizFragment`。
4. 保存 `content_main.xml`。

### 4.5.2 设计 `fragment_main.xml` 布局

你通常会为每个 `Fragment` 定义布局，但你不需要为本应用的 `SettingsActivityFragment` 定义布局——其 GUI 将由其继承的 `PreferenceFragment` 功能自动生成。本节介绍了 `MainActivityFragment` 的布局（`fragment_main.xml`）。图 4.18 显示了 `MainActivityFragment` GUI 的 `id` 属性值——你应该在将组件添加到布局时设置这些 `id` 值。

![](img/8c2e5496308864b3b07ddbd4401c4f77_169_0.png)

**图 4.18 | 旗帜测试 GUI 的组件，用其 `id` 属性值标记——这些组件排列在一个垂直的 `LinearLayout` 中。**

使用在第 3 章中学的技巧，你将构建图 4.18 所示的 GUI。记住，在组件树（Component Tree）窗口中选择特定的 GUI 组件是最简单的。你将从基础布局开始，自定义控件的属性以完成设计。

#### 步骤 1：从 `RelativeLayout` 改为 `LinearLayout`

与之前两个应用的 `activity_main.xml` 布局活动一样，`fragment_main.xml` 中的默认布局是 `RelativeLayout`。在这里，你将为此应用的设计将其更改为垂直的 `LinearLayout`：

- 打开 `fragment_main.xml` 文件，并切换到 Text（文本）标签。
- 在 XML 中，将 `RelativeLayout` 改为 `LinearLayout`。
- 切换回 Design（设计）标签。
- 在组件树中选择 `LinearLayout`。
- 在属性窗口中，将 `LinearLayout` 的 `orientation`（方向）设置为 `vertical`（垂直）。
- 确保 `layout:width` 和 `layout:height` 设置为 `match_parent`。
- 将 `LinearLayout` 的 `id` 设置为 `quizLinearLayout` 以供程序化访问。

默认情况下，IDE 将布局的 `Padding Left`（左内边距）和 `Padding Right`（右内边距）属性设置为定义的维度 `@dim/activity_horizontal_margin`——它位于项目 `res/values` 文件夹下的 `dims.xml` 文件中。该资源的值为 16dp，因此布局的左右会有 16dp 的内边距。当你创建应用项目时，IDE 会创建此源码。同样，IDE 将 `Top`（上边距）和 `Padding Bottom`（下内边距）属性设置为 `@dim/activity_vertical_margin`——另一个值为 16dp 的预定义维度资源。因此，布局的上下会有 16dp 的内边距。`MainActivity` 的所有 GUI 将相对于 `MainActivity` 的其他 GUI 缩进 16dp。

#### 步骤 2：将 `questionTextView` 拖到 `LinearLayout`

从调板（Palette）的 Widgets 部分将一个 Medium Text（中文本）组件拖到组件树窗口中的 `quizLayout` 中，然后将其 `id` 设置为 `questionTextView`。使用属性窗口设置以下属性：

- `gravity: center`——内容在布局内水平居中。
- `layout_margin: @dim/spacing`——为下边距设置此值，在该组件下方添加 8dp 的空间。使用你在第 2.5.6 节中学到的技巧创建此维度资源。
- `text: @string`——要设置文本属性字段，请点击省略号 (...) 按钮。在 Resources（资源）对话框的 Property 标签页（图 4.19）中，选择问题文本，点击 OK。

#### 步骤 3：将 `ImageView` 拖到 `LinearLayout`

从调板的 Widgets 部分将一个 `ImageView` 组件拖到组件树窗口中的 `quizLayout` 中，然后将其 `id` 设置为 `flagImageView`。使用属性窗口设置以下属性：

- `layout_width: match_parent`
- `layout_weight: 0dp`——这将允许 View 的高度由布局属性决定。
- `gravity: center`
- `layout_margin_bottom: @dim/spacing`——在该组件下方添加 8dp 的空间。
- `layout_margin_left` 和 `right: @dim/activity_horizontal_margin`——在该组件的左右添加 16dp 的空间，在使旗帜向右的抖动动画期间，整个旗帜将显示。
- `layout_weight: 1`——将此组件的 `layout_weight` 设置为 1（所有组件默认为 0）会让 `ImageView` 比 `quizLayout` 中的其他组件重要。当 Android 布局组件时，它们将仅使用所需的垂直空间，而 `ImageView` 将占据所有剩余的垂直空间。IDE 建议将 `ImageView` 的 `layout_height` 设置为 0dp，以帮助 Android 在运行时更快地布局 GUI。

![](img/8c2e5496308864b3b07ddbd4401c4f77_171_0.png)

**图 4.19** 资源选择器——选择现有的 String 资源 `question`。

- `adjustBounds:true`——将 `ImageView` 的 Adjust Bounds 属性设置为 true（通过勾选复选框）表示 `ImageView` 保持其图像的比例。
- `contentDescription:@string/image_description`
- `scaleType:fitCenter`——这表示 `ImageView` 应该显示图像以填充 `ImageView` 的宽度或高度，同时保持原始图像的比例。如果宽度小于 `ImageView`，则图像将水平居中。如果高度小于 `ImageView`，则图像将垂直居中。

> **外观观察 4.3**
>
> 记住，Android 中的一个最佳实践是确保每个 GUI 组件都可以与 TalkBack 使用。对于没有描述性文本的组件（例如 `ImageView`），请设置组件的 `contentDescription` 属性。

#### 步骤 4：将 `guessCountryTextView` 添加到 `LinearLayout`

从调板的 Widgets 部分将一个 Medium Text 组件拖到组件树窗口中的 `quizLinearLayout` 上，将其 `id` 属性设置为 `guessCountryTextView`。使用属性窗口设置以下属性：

- `layout_gravity: horizontal`
- `text: @string/guessCountry`

#### 步骤 5：将按钮添加到 `LinearLayout`

对于此应用，我们将按钮按行添加——每一行都是水平的 `LinearLayout`。你将在步骤 7 中设置按钮的属性。按照以下步骤将按钮添加到布局中：

1. 从调板的 Layouts 部分将 `LinearLayout (Horizontal)` 拖到组件树中的 `quizLayout`，将其 `id` 设置为 `rowLinearLayout` 并将 `layout_orientation` 设置为 `wrap`。
2. 从调板的 Widgets 部分将一个 `Button` 拖到 `rowLinearLayout`。你不需要设置其 `id`，因为 Java 代码中通过 `id` 引用按钮。
3. 为第一行的 `Button` 重复步骤 2。
4. 为剩余的 Layouts 重复步骤 1-3，并按图 48 所示设置 `id` 以创建三行。

#### 步骤 6：将 `answerTextView` 添加到 `LinearLayout`

从调板的 Widgets 部分将一个 Text 组件拖到组件树中的 `quizLayout` 上，将其 `id` 设置为 `answerTextView`。使用属性窗口设置以下属性：

- `layout_gravity: horizontal`
- `gravity: center`——当显示更多行时，使 `TextView` 文字居中。
- `textSize: @dim/answer_size`——将文本大小更改为 36sp。使用你在第 2.5.6 节中学到的技巧创建此维度资源。
- `bold`

此 `TextView` 的属性将通过程序设置。此时，组件树应如图 42 所示。

#### 步骤 7：设置按钮的属性

完成步骤 6 后，按照图 41 所示的值配置按钮——你可以在组件树中选择所有按钮，然后同时设置这些属性：

- 将 `Button` 的 `layout_width` 和 `weight` 设置为 1，允许 `LinearLayout` 中的按钮平分空间。
- 将 `Button` 的 `layout_height` 设置为 `match_parent`，使按钮的高度等于 `LinearLayout` 的高度。
- 将 `Button` 的 `lines` 属性设置为 2，确保不同行数的国家名称具有相同的高度——如果按钮的文本过长无法在两行内显示，该文本将被截断。

![](img/8c2e5496308864b3b07ddbd4401c4f77_173_0.png)

**图 4.20** | `fragment_main.xml` 的组件树。

- 将 `style` 属性设置为 `@android:style/Material.Button.Colored` 会导致按钮根据应用主题的颜色显示。按钮的颜色将是应用的强调色，该颜色在第 4.4.7 节中指定。要设置此属性，点击省略号打开资源对话框，从 System 标签页选择 `Widget.Material1.Button.Colored` 并点击 OK。
- 将 `textcolor` 属性设置为你在第 4.4.8 节中定义的 `@color/button_text_color` 颜色列表，确保文本根据每个按钮的启用/禁用状态更改颜色。

![](img/8c2e5496308864b3b07ddbd4401c4f77_173_1.png)

**图 4.21** | `fragment_main.xml` 中 Buttons 组件的属性值。

## 4.5.3 图形布局编辑器工具栏

你现在完成了 `MainActivityFragment` 的 GUI。布局编辑器的工具栏（图 4.22）包含按钮，允许你预览针对其他屏幕尺寸和方向设计的界面。特别是，你可以查看许多屏幕尺寸和方向的缩略图。要这样做，首先打开 `activity_main.xml`，点击布局编辑器顶部的虚拟设备下拉菜单，并选择“预览所有屏幕”（Preview All Screen Sizes）。图 4.23 概述了布局编辑器工具栏中的一些按钮。

![](img/8c2e5496308864b3b07ddbd4401c4f77_174_0.png)

图 4.22 画布配置选项。

| 选项 | 说明 |
| --- | --- |
| 渲染选项 (Render options) | 一时显示一个设计屏幕，或在各种屏幕尺寸上查看你的设计 |
| 虚拟设备 (Virtual device) | Android 运行各种设备上，因此布局编辑器带有许多设备配置，代表各种屏幕尺寸和分辨率，你可以用它们设计 GUI。在本书中，我们根据应用使用预定义的 Nexus 6 和 Nexus 9 屏幕。在图 4.22 中，我们选择了 Nexus 6 |
| 竖屏/横屏 (Portrait/landscape) | 在竖屏和横屏之间切换设计区域。可用于设置 GUI 的主题 |
| 正在设计的 Activity/fragment (Activity/fragment being designed) | 显示与设计的 GUI 对应的 Activity 或 Fragment 类 |
| 区域 (Locale) | 对于国际化应用（2.8 节），允许你选择特定的本地化进行查看，例如查看设计在不同语言字符串下的外观 |
| API 级别 (API level) | 指定设计的 API 级别。每个新的 API 级别通常会有新功能。布局编辑器仅显示所选 API 级别可用的功能 |

图 4.23 画布配置选项说明。

## 4.5.4 平板电脑横屏的 `content_main.xml` 布局

正如我们之前提到的，`MainActivity` 的默认 `content_main.xml` 布局显示了 `MainActivityFragment` GUI。现在你将为平板电脑的横屏定义 `MainActivity` 的布局，它将把 `SettingsActivityFragment` 和 `MainActivityFragment` 并排显示。要这样做，你将创建一个第二个 `content_main.xml` 布局，Android 将在适当设备上使用它。

### 创建平板电脑横屏的 `content_main.xml`

要创建布局，请执行以下步骤：

1. 右键点击项目的 `res/layout` 文件夹，选择 New（新建） > Layout resource file（布局资源文件）。
2. 在 New Resource File 框的 Name（名称）字段中输入 `content_main.xml`。
3. 确保 Root element（根元素）字段指定了 `LinearLayout`。
4. 在 Available Qualifiers（可用限定符）列表中，选择 Screen Width（屏幕宽度）限定符，然后点击 >> 按钮将该限定符添加到 Chosen Qualifiers（已选限定符）列表中，并将其值设置为 700——该布局适用于宽度至少 700 像素的屏幕。
5. 在 Available Qualifiers 列表中，选择 Orientation（方向）限定符，然后点击 >> 按钮将该限定符添加到 Chosen Qualifiers 列表中，将其值设置为 Landscape（横屏）。
6. 点击 OK。

这创建了 `content_main.xml` 文件，它存储在名为 `layout-sw700dp-land` 的 res 子文件夹中，该布局仅在最小宽度 (sw) 为 700dp 且设备处于（landscape）方向的设备上使用。Android 使用 `sw` 和 `land` 限定符在运行时选择适当资源。

在 Android Studio 中，Project 窗口并不会显示分开的布局和 `layout-sw700dp-land` 文件夹，而是将两个布局合并为 Project 窗口 `res/layout` 文件夹中的单个节点 `content_main.xml` (2) 节点——(2) 表示节点中有两个布局。展开这些节点：

- `content_main.xml`
- `content_main.xml (sw700dp-land)`

不带限定符的布局是默认布局。带有限定符的布局仅在合适时使用。创建文件后，Android Studio 会在布局编辑器中打开该布局。Design（设计）视图按方向展示布局。

### 创建平板电脑布局的 GUI

接下来，你将构建平板电脑布局的 GUI：



1. 在`Component Tree`（组件树）中选择`LinearLayout`（vertical），并将`orientation`（方向）属性设置为`horizontal`（横向）。

2. 点击`Palette`（调板）自定义部分中的`<fragment>`。在`Fragments`对话框中选择`SettingsActivityFragment`，并点击`OK`。然后点击`Component Tree`窗口中的`LinearLayout`节点。这会将`<fragment>`添加到布局。将`<fragment>`的`id`设置为`settingsActivityFragment`。

3. 重复前面的步骤，但这次选择`MainActivityFragment`。同样，将此`<fragment>`的`id`设置为`quizFragment`。

4. 选择`Component Tree`中的`settingsActivityFragment`节点。设置`layout_width:0dp`、`layout_height:match_parent`并将`layout_weight`设置为`1`。

5. 选择组件树中的`quizFragment`节点。将`layout_width`设置为`0dp`，`layout_height:match_parent`，`layout_weight`为`2`。`MainActivityFragment`的`layout_weight`为`2`，`SettingsActivityFragment`为`1`，因此权重总和为`3`，`MainActivityFragment`将占据布局水平空间的三之二。

6. 切换到`Text`标签并向`LinearLayout`添加以下行，以确保应用栏位于顶部而不是在它后面：

```xml
xmlns:app="http://schemas.android.com/apk/res/auto"
app:layout_behavior="@string/scrolling_view"
```

在布局中选择预览

布局编辑器将显示任何设计。如果你不指定预览，编辑器将显示手机上的`MainActivityFragment`。要指定预览，右键点击`Design`或`Tree`——在`Fragments`对话框中，选择`fragment`的名称。

## 4.6 `MainActivity`类

图 4.24 显示了`MainActivity`的语句和导入。第 6–19 行导入了应用用到的类和接口。我们将在 4.6.7 节中讨论新内容。

```java
// MainActivity.java
package com.flagquiz;
import android.content.Intent;
import android.content.SharedPreferences;
import android.content.SharedPreferences.OnChangeListener;
import android.app.Activity;
import android.content.Configuration;
import android.os.Bundle;
import android.preference.PreferenceManager;
import android.support.v7.app.AppCompatActivity;
import android.support.v7.widget.Toolbar;
import android.view.Menu;
import android.view.MenuItem;
import android.widget.Toast;
import java.util.Set;
```

图 4.24 | `MainActivity`语句和导入。（部分 1/2）

## 4.6.2 字段

图 25 显示了`MainActivity`的字段。第 23–27 行定义了 4.4 节中创建的偏好键。

```java
public class MainActivity extends AppCompatActivity {
    // 从 SharedPreferences 读取数据的键
    public static String CHOICES = "pref_numberOfChoices";
    public static String REGIONS = "pref_regionsInclude";

    private boolean phoneDevice = true; // 用于强制竖屏
    private boolean preferencesChanged = true; // 偏好是否变化
```

图 4.25 | `MainActivity`声明和字段。

## 4.6.3 重写的`MainActivity`方法`onCreate`

图 26 显示了重写的`onCreate`方法——我们删除了预定义的`LayoutInflater`事件处理程序，它在应用中未使用。第 33 行调用`setContentView`设置`MainActivity`的UI。`setContentView`返回内容文件`activity_main.xml`的布局，该文件有两个版本。当膨胀`activity_main.xml`时，Android 会嵌入`res/layout`文件夹中的默认`content_main.xml`（在横屏情况下）。Android 使用应用运行的设备上的版本，即`res/layout-700dp-land`文件夹。

设置默认偏好值并注册更改器

当你首次安装并启动应用时，第 38 行通过调用`PreferenceManager`方法`setDefaultValues`设置应用偏好——这使用你在`preferences.xml`中指定的默认值初始化`SharedPreferences`文件。该方法需要三个参数：

## 第 4 章 旗帜测验 App

```java
// 配置 MainActivity
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);
    Toolbar toolbar = findViewById(R.id.toolbar);
    setSupportActionBar(toolbar);

    // 在 SharedPreferences 中设置默认值
    PreferenceManager.setDefaultValues(this, R.xml.preferences, false);

    // 注册 SharedPreferences 变化的监听器
    PreferenceManager.getDefaultPreferences(this);
    registerOnSharedPreferenceChangeListener(new PreferenceChangeListener);

    // 确定屏幕尺寸
    int screenSize = getResources().getConfiguration().screenLayout &
        Configuration.SCREENLAYOUT_SIZE_MASK;

    // 如果设备是平板电脑，将 phoneDevice 设置为 false
    if (screenWidth == Configuration.SCREENLAYOUT_SIZE_XLARG) {
        phoneDevice = false; // 不是手机大小的设备
    }

    // 如果在手机大小的设备上运行，则仅允许竖屏模式
    if (phoneDevice)
        setRequestedOrientation(Activity.SCREEN_ORIENTATION_PORTRAIT);
}
```

图 4.26

- `Context`（包`android.content`），它提供了关于应用运行环境的信息访问，并允许你使用各种 Android 服务——在这种情况下，`Context`是你正在设置默认偏好的`Activity`（`this`）。

- 你在第 4.4.11 节中创建的 XML 文件的资源 ID（`R.xml.preferences`）。

- 一个布尔值，表示每次调用`setDefaultValues`时是否应该重置默认值——`false`表示在第一次调用此方法时应设置默认偏好值。

- 每当用户更改偏好设置时，你的`MainActivity`都应该调用`onCreate`或`updatePreferences`来刷新UI。`MainActivity`实现了`OnSharedPreferenceChangeListener`（第 41-43 行），每当偏好发生变化时都会收到通知。`PreferenceManager getSharedPreferences`返回代表应用偏好的`SharedPreferences`对象的引用，而`SharedPreferences`方法`registerSharedPreferenceChangeListener`用于注册监听器（在第 4.6.7 节中定义）。

## 4.6 `MainActivity`类

### 为竖屏方向配置设备

第 46–52 行确定应用是运行在手机还是平板电脑上。继承的方法`get`返回应用对象（`android.content.res`），用于访问应用资源并确定有关其环境的信息。方法`getConfiguration`返回一个`Configuration`对象（`android.content.res`），其中包含公共实例变量`screenLayout`，它指定了设备的屏幕尺寸类别。要做到这一点，首先使用位与运算符（`&`）将`screenLayout`的值与`Configuration`结合。然后，将结果与`SCREENLAYOUT_SIZE_LARGE`和`SCREENLAYOUT_SIZE_XLARGE`进行比较（第 50–51 行）。如果匹配其中任何一个，则应用运行在平板设备上。最后，如果设备是手机，第 56–57 行调用继承的`Activity`方法`setRequestedOrientation`，强制应用以竖屏方向显示`MainActivity`。

### 4.6.4 重写的`Activity`方法`onStart`

重写的`Activity`方法`onStart`（图 4.27）在两种场景下被调用：

- 当应用首次执行时，`onStart`在`onCreate`之后被调用。我们使用`onStart`来确保在应用安装并首次执行时，根据应用的默认偏好正确配置测验；或者在随后启动应用时，根据用户更新的偏好设置进行配置。

- 当应用以竖屏方向运行且用户打开`SettingsActivity`时，`MainActivity`会暂停。当用户返回时，`onStart`会再次调用。

在两种情况下，如果`preferencesChanged`为真，`onStart`会触发以重构测验。通过第 68 行获取`MainActivity`引用并调用`updatePreferences`（第 4.7 节）以处理用户更改的偏好设置。第 71–74 行通过`PreferenceManager.getDefaultShPreferences(this)`传递给`MainActivity`的`updateGuessRows`方法来重置测验。第 76 行将`preferencesChanged`设置为`false`。

```java
// 在 onCreate 完成后
@Override
protected void onStart() {
    super.onStart();

    if (preferencesChanged) {
        // 偏好设置已更改，刷新 UI
        MainActivity quizFragment = (MainActivity)
            getSupportFragmentManager().findFragmentById(R.id.quizFragment);
        quizFragment.updateGuessRows(sharedPreferences);
    }
}
```

### 4.6.5 重写的`Activity`方法`onCreate`

重写的`Activity`方法`onCreate`（图 4.27）在应用首次执行时，`onStart`之后被调用。我们使用`onCreate`来确保在应用安装并首次执行时，根据应用的默认偏好正确配置测验；或者在随后启动应用时，根据用户更新的偏好设置进行配置。

当应用以竖屏方向运行且用户打开`SettingsActivity`时，`MainActivity`会暂停。当用户返回时，`onStart`会再次调用。

在两种情况下，如果`preferencesChanged`为真，`onStart`会触发以重构测验。通过第 68 行获取`MainActivity`引用并调用`updatePreferences`（第 4.7 节）以处理用户更改的偏好设置。第 71–74 行通过`Activity`菜单。

```java
// 如果在竖屏模式下显示
public boolean onCreateOptionsMenu(Menu menu) {
    // 获取设备的当前方向
    int orientation = getResources().getConfiguration().orientation;
    // 如果是竖屏模式
    if (orientation == Configuration.ORIENTATION_PORTRAIT) {
        // 加载菜单
        getInflater().inflate(R.menu.menu_main, menu);
        return true;
    } else
    return false;
}
```

### 4.6.6 重写方法`onOptionsItemSelected`

菜单项被选中。在应用中，IDE 创建的默认菜单只包含设置项，如果此方法被调用，说明用户选择了设置。第 99 行创建一个`Intent`。

```java
// 在手机运行时显示 SettingsActivity
@Override
public boolean onOptionsItemSelected(MenuItem item) {
    // 创建启动 SettingsActivity 的显式 Intent
    Intent preferencesIntent = new Intent(this, SettingsActivity.class);
    return super.onOptionsItemSelected(item);
}
```

### 4.6.7 实现`SharedPreferenceChangeListener`的匿名类

`preferencesChangeListener`对象（图 4.30）是一个实现`SharedPreferenceChangeListener`接口的匿名类对象。该对象在方法中注册以监听应用`SharedPreferences`的变化。当发生变化时，`onSharedPreferenceChanged`方法将状态设置为`true`（第 111 行），获取`MainActivity`的引用（第 113–115 行），以便根据新偏好重置测验。如果`CHOICES`偏好发生了变化，第 119 行将调用`MainActivity`的`updateGuessRows`。

```java
// 应用 SharedPreferences 变化的监听器
private SharedPreferenceChangeListener preferencesChangeListener = 
    new SharedPreferenceChangeListener() {
        // 当应用偏好发生变化时调用此方法
        @Override
        public void onSharedPreferenceChanged(SharedPreferences sharedPreferences, String key) {
            preferencesChanged = true; // 用户更改了设置
            MainActivity quizFragment = (MainActivity)
                getSupportFragmentManager().findFragmentById(R.id.quizFragment);
            if (key.equals(CHOICES)) { // 显示的选择发生了变化
                quizFragment.updateGuessRows(sharedPreferences);
            }
        }};
```

# 第4章 旗帜测验 App



```java
quizFragment.resetQuiz();
}
else if (key.equals(REGIONS)) { // regions发生变化
    Set<String> regions = sharedPreferences.getStringSet(REGIONS, null);

    if (regions != null && regions.size() > 0) {
        quizFragment.updateRegions(sharedPreferences);
        quizFragment.resetQuiz();
    } else {
        // 选择一个区域--将北美作为默认
        SharedPreferences.Editor editor = sharedPreferences.edit();
        regions.add(getString(R.default_region));
        editor.putStringSet(regions, regions);
        editor.apply());
    }
}
Toast.makeText(MainActivity.this, R.default_region_message, Toast.LENGTH_SHORT).show();

Toast.makeText(MainActivity.this, R.restarting_quiz, Toast.LENGTH_SHORT).show();
```

**图 4.30** | 实现 `OnSharedPreferenceChangeListener` 的匿名内部类（部分 2，共 2）

如果 `REGIONS` 发生变化，行 112–123 会获取包含已启用区域的 `Set<String>`。`SharedPreferences` 方法 `getStringSet` 根据指定的键返回一个 `Set<String>`。测验必须至少启用一个区域，如果是这样则 `Set<String>` 为空，行 116–127 获取 `MainActivityFragment` 的`updateRegions`和`resetQuiz`方法。

如果 `Set<String>` 为空，行 131–135 将以北美作为默认区域更新 `REGIONS` 偏好。要获取区域名称，行 133 调用 `Activity` 继承的方法 `getString`，该方法返回指定 ID (`R.default_region`) 的 `String` 资源。

若要更改 `SharedPreferences` 对象的内容，首先调用 `edit` 方法获取一个 `SharedPreferences.Editor` 句器（行 131–132），它可以向 `SharedPreferences` 文件中添加键-值对、删除键-值对，并修改 `SharedPreferences` 文件中与特定键关联的值。行 134 调用 `SharedPreferences.Editor` 方法 `putStringSet` 来存储 `regions` 的内容（`Set<String>`）。行 135 通过调用 `SharedPreferences.Editor` 方法 `apply` 来提交（保存）更改，该方法会立即更改 `SharedPreferences` 的内存表示，并在后台异步将更改写入文件。还有一个`commit`方法可以同步地（立即）将更改写入文件。

行 137–139 使用 `Toast` 指明已设置默认区域。`Toast` 方法 `setText` 接收的参数包括显示 `Toast` 的 `Context`、要显示的消息以及 `Toast` 显示持续持续。`Toast` 方法显示 `Toast`。无论哪种偏好发生变化，行 143–145 都会显示一个 `Toast`，表示测验将使用新偏好进行重置。图 4.31 显示了用户在更改应用偏好后出现的`Toast`。

![图4.31 偏好更改后显示的Toast。](img/8c2e5496308864b3b07ddbd4401c4f77_183_0.png)

**图 4.31** | 偏好更改后显示的 `Toast`。

# 4.7 `MainActivityFragment` 类

`MainActivityFragment` 类（图 4.32–4.42）——Android Support Library 中 `Fragment` 类（包名 `android.support.v4.app`）的子类——构建了旗帜测验的 GUI 并实现了其测验逻辑。

## 4.7.1 package 和 import 语句

图 4.32 显示了 `MainActivityFragment` 的包语句和 `import` 语句。行 5–36 导入了应用使用的各种 Java 和 Android 类及接口。我们强调了关键 `import` 语句，并在第 4.3 节中讨论了相应的类和接口，以及它们在第 4.7.2–4.7.11 节中的位置。

```java
1 // MainActivityFragment.java
2 // 包含旗帜测验逻辑
3 package com.deitel.flagquiz;
4
5 import java.io.IOException;
6 import java.io.InputStream;
7 import java.security.SecureRandom;
8 import java.util.ArrayList;
9 import java.util.Collections;
10 import java.util.List;
11 import java.util.Set;
12
13 import android.animation.Animator;
14 import android.animation.AnimatorListener;
15 import android.app.AlertDialog;
16 import android.app.Dialog;
17 import android.content.DialogInterface;
18 import android.content.SharedPreferences;
19 import android.content.res.AssetManager;
20 import android.graphics.drawable.Drawable;
21 import android.os.Bundle;
22 import android.support.v4.app.DialogFragment;
23 import android.support.v4.app.Fragment;
24 import android.os.Handler;
25 import android.util.Log;
26 import android.view.LayoutInflater;
27 import android.view.View;
28 import android.view.View.OnClickListener;
29 import android.view.animation.AnimationUtils;
30 import android.animation.Animation;
31 import android.view.animation.AnimationUtils;
32 import android.widget.Button;
33 import android.widget.ImageView;
34 import android.widget.LinearLayout;
35 android.widget.TextView;
```

**图 4.32** | `MainActivityFragment` 包语句，`import` 语句。（部分 1，共 2）

# 4.7 字段

`MainActivityFragment` 类列出了静态和实例变量。常量 `TAG`（第 38 行）用于日志消息。常量 `FLAGS_Z`（第 39 行）代表旗帜的数量。

```java
38 public class MainActivityFragment extends Fragment {
39 private final String TAG = "FlagQuiz";
40 private final int FLAGS_Z = 10;
41 private List<String> fileNameList;
42 private List<String> countriesList;
43 private Set<String> regionsSet;
44 private String correctAnswer;
45 private int totalGuesses;
46 private int correctAnswers;
47 private int guessRows;
48 private Random random;
49 private Handler handler;
50 private Animation shakeAnimation;
51 private LinearLayout layout;
52 private TextView questionNumberTextView;
53 private ImageView flagImageView;
54 private LinearLayout answerLayout;
55 private TextView answerTextView;
```

**图 4.33** | `MainActivityFragment` 字段。（部分 2）

**良好的编程实践**：为了可读性和可修改性，使用字符串常量表示字符串字面量（例如用于日志消息的），并将其定义在 `strings.xml` 中。变量 `fileNameList`（第 44 行）持有启用区域的文件名。变量 `countriesList`（第 45 行）持有国家名称。变量 `regionsSet`（第 46 行）持有地理区域。变量 `correctAnswer`（第 47 行）持有正确答案。变量 `totalGuesses`（第 48 行）存储玩家所做的正确错误猜测总数。变量 `correctAnswers`（第 49 行）是到目前的正确猜测次数；变量 `guessRows`（第 50 行）是随机数生成器。

## 4.7.3 重写的 `onCreate` 方法

`MainActivity` 的 `onCreate` 方法（图 4.34）构建了 GUI 并初始化了大多数实例变量——`guessRows` 和 `regionsSet` 在 `MainActivity` 调用 `updateRegions` 时初始化。在调用父类的 `onCreate` 方法（第 65 行）后，我们使用 `LayoutInflater` 方法 `onCreate`（行 66–67）初始化 `MainActivity` 的 GUI。`LayoutInflater` `inflate` 方法返回：

- 标识要加载的布局的资源 ID。
- `Fragment` 将显示的 `View`（组对象），它通过 `onCreate` 的第二个参数接收。
- 指明要加载的 GUI 是否需要附加到第二个参数中的 `ViewGroup` 的布尔值。在 `fragment` 的 `onCreate` 方法中，此值始终为 `false`——系统会将 `fragment` 附加到相应的活动 `ViewGroup` 中。在此处传递 `true` 会导致异常，因为 `fragment` 已经附加了。

`inflate` 方法返回一个包含加载 GUI 的 `View`。将其存储在局部变量 `view` 中，以便在 `MainActivity` 的其他实例变量初始化后由 `onCreate` 返回。[注：我们删除了该类中自动生成的空无参数构造函数（它在 IDE 类定义中出现在 `onCreate` 之前），因为编译器为任何没有构造函数的类提供默认构造函数。]

# 第4章 旗帜测验应用

```java
// 当其 View 被创建时配置 MainActivityFragment
@Override
public void onCreate(LayoutInflater inflater, ViewGroup container,
    Bundle savedInstanceState) {
    super.onCreate(inflater, container, savedInstanceState);
    View view =
        inflater.inflate(R.layout.fragment_main, container, false);
    fileNameList = new ArrayList<>(); // 注释运算符
    quizCountList = new ArrayList<>();
    random = new Random();
    handler = new Handler();
    // 加载答案错误的抖动动画
    shakeAnimation = AnimationUtils.loadAnimation(getActivity(),
    R.anim.incorrect_shake);
    shakeAnimation.setRepeatCount(3);
    // 获取 GUI 组件的引用
    quizLinearLayout =
    view.findViewById(R.id.quizLinearLayout);
    questionTextView =
    (TextView)view.findViewById(R.id.questionTextView);
    imageView = (ImageView)view.findViewById(R.id.imageView);
    guessListLayout = new LinearLayout[4];
    guessListLayout[0] = (LinearLayout)view.findViewById(R.id.row1LinearLayout);
    guessListLayout[1] = (LinearLayout)view.findViewById(R.id.row2LinearLayout);
    guessListLayout[2] = (LinearLayout)view.findViewById(R.id.row3LinearLayout);
    guessListLayout[3] = (LinearLayout)view.findViewById(R.id.row4LinearLayout);
    answerTextView =
    (TextView)view.findViewById(R.id.answerText);
    // 为猜测按钮配置监听器
    for (LinearLayout row : guessLayouts) {
        for (int column = 0; column < row.getChildCount(); column++) {
            Button button = (Button)row.getChild(column);
            button.setOnClickListener(guessButtonListener);
        }
    }
    // 设置 questionNumberTextView 的文本
    questionNumberTextView.setText(getString(R.string.question, 1, FLAGS_IN_QUIZ));
    return view; // 返回用于显示的 fragment
}
```

**图 4.34** | `MainActivityFragment` 重写的 `onCreateView` 方法

第 69–70 行创建了 `ArrayList<String>` 对象，分别存储当前已选地理区域的旗帜图像文件名，以及当前猜测中的国家名称。

# 4.7 `MainActivityFragment` 类

第 71 行创建了 `SecureRandom` 对象，用于测验旗帜和猜测按钮的随机化。第 72 行创建了 `Handler` 对象 `handler`，我们将它用于在用户纠正当前旗帜后延迟两秒显示下一面旗帜。

第 75–76 行动态加载了在做出错误猜测时应用到旗帜上的抖动动画。`AnimationUtils` 静态方法 `loadAnimation` 从由 `R.anim.incorrect_shake` 代表的 XML 文件加载动画。继承的方法 `getActivity` 返回包含托管此 `Fragment` 的 activity 资源的 `Context`。`Activity` 是 `Context` 的间接子类，`setRepeatCount` 返回动画应该重复的次数。

第 80–94 行获取了我们将程序化管理的 UI 组件的引用。第 97–102 行从 `guessLinearLayouts` 获取猜测按钮，并将 `guessButtonListener`（第 4.10 节）注册为 `onClickListener`——我们实现此接口来处理用户触摸任何猜测按钮时的事件。

第 105–106 行通过调用 `Fragment` 继承方法 `getString` 的重载版本，将 `questionNumberTextView` 中的文本设置为该 `String`。`format` 的第一个参数是字符串资源 `R.string.question`，它代表格式字符串：

```
Question %1d %2d
```

该字符串包含两个值的占位符（如第 4.4.5 节所述）。剩余参数是要将被插入到格式字符串中的值。第 107 行返回 `MainActivity` 的 `guessUI`。

## 4.7.4 方法 `updateGuessRows`



方法`updateGuessRows`（图 4.35）在应用启动时从应用的`MainActivity`调用，并更改显示每面旗帜的猜测按钮数量。第 113–114 行使用方法的`SharedPreferences`参数获取键为`MainActivity.CHOICES`的`String`——它包含了`SettingsActivity`存储要显示的猜测按钮数量的偏好名称。第 115 行将该值转换为`int`并除以 2，以确定`guessRows`的值，该值指示了有多少个`guessLinearLayouts`显示两个猜测按钮。接下来，第 118–119 行隐藏所有的`guessLinearLayouts`，因此第 122–123 行根据`guessRows`的值显示相应的`guessLinearLayouts`。猜测的常量`GONE`（第 119 行）表示 Android 不应计数。还存在常量`View.INVISIBLE`，它仅仅是隐藏组件，而分配给组件的任何空间仍保留在屏幕上。

```java
// 根据 SharedPreferences 中的值更新 guessRows
public void updateGuessRows(SharedPreferences preferences) {
  // 获取应该显示的猜测按钮数量
  String choices =
    sharedPreferences.getString(MainActivity.CHOICES, null);
  guessRows = Integer.parseInt(choices) / 2;

  // 隐藏所有猜测按钮 LinearLayout
  for (LinearLayout layout : guessLinearLayouts)
    layout.setVisibility(View.GONE);

  for (int row = 0; row < guessRows; row++)
    guessLayouts[row].setVisibility(View.VISIBLE);
}
```

图 4.35 | MainActivityFragment 方法 updateGuessRows。（部分 2。）

### 4.7.5 方法 updateRegions

方法`updateRegions`（图 4.36）在应用启动时调用，并使用方法的`SharedPreferences`参数获取`MainActivity.REGIONS`的`Set`，以设置测验中应包含的区域。

```java
// 根据偏好更新世界区域
public void updateRegions(SharedPreferences preferences) {
    regions = preferences.getStringSet(MainActivity.REGIONS, null);
}
```

### 4.7.6 方法 resetQuiz

方法`resetQuiz`（图 4.37）启动测验。为了访问文件夹，我们使用`AssetManager`的`list`方法获取所有图像文件。第 140–146 行遍历已启用的区域。对于每个区域，移除移除`.png`扩展名并清除`fileNameList`。`AssetManager.list`会抛出`IOException`，这是一个检查异常（必须捕获）。如果应用程序无法访问文件夹，使用 Android 内置日志进行调试。

```java
// 设置并启动测验
public void resetQuiz() {
    // 使用 AssetManager 获取已启用区域的文件名
    AssetManager assets = getActivity().getAssets();
    fileNameList.clear();

    try {
        // 遍历每个区域
        for (String region : regions) {
            // 获取该区域的所有图像
            String[] paths = assets.list(region);
            for (String path : paths) {
                fileNameList.add(path.replace(".png", ""));
            }
        }
    } catch (IOException exception) {
        Log.e(TAG, "加载文件名错误", exception);
    }

    correctAnswers = 0; // 重置正确答案数
    totalGuesses = 0; // 重置总猜测数
    quizCountersList.clear(); // 清空计数列表

    int flagCounter = 1;
    int numberFlags = fileNameList.size();

    // 将 FLAGS_IN_QUIZ 个随机文件名添加到 quizCountersList
    while (flagCounter < FLAGS_IN_QUIZ) {
        int randomIndex = random.nextInt(numberFlags);
        // 获取随机文件名
        String fileName = fileNameList.get(randomIndex);
        // 如果该区域已启用且尚未被选择过
        if (!quizCountersList.contains(fileName)) {
            quizCountersList.add(fileName); // 将文件添加到列表
            flagCounter++;
        }
    }

    loadNextFlag();
}
```

# 第 4 章 国旗测验应用

从`fileNameList`获取名称。如果`quizCountriesList`尚未包含该文件，我们就将其添加到`quizCountriesList`并增加`flagCounter`。我们重复此过程，直到选择了 10 个（`FLAGS_IN_QUIZ`）唯一名称。然后，第 173 行调用`loadNextFlag`（图 4.38）来加载测验的。

## 4.7 方法 loadNextFlag

方法`loadNextFlag`（图 4.38）加载并显示下一个旗帜以及相应的按钮组。`quizCountriesList`中的图像名称格式为不带`.png`后缀。如果`regionName`或`countryName`包含多个单词，将用下划线 (`_`) 分隔。

```java
// 用户猜对了旗帜，加载下一旗
private void loadNextFlag() {
    // 获取下一旗的文件名并从列表中移除
    String nextImage = quizCountriesList.remove(0);
    correctAnswer = answerTextView.setText(""); // 清空 answerTextView

    // 显示当前题号
    questionNumberTextView.setText(getString(
        R.string, (correctAnswers[i], FLAGS_IN_QUIZ)));

    // 从下一个图像名称中提取区域
    String region = nextImage.substring(0, nextImage.indexOf('='));

    // 使用 AssetManager 从 assets 文件夹加载图像
    AssetManager assetManager = getActivity().getAssets();

    // 获取代表下一旗的 asset 的 InputStream
    // 并尝试使用该 InputStream
    try {
        InputStream stream = assetManager.open("/" + nextImage + ".png");
        // 将图像加载为 Drawable 并显示在 flagImageView 上
        Drawable drawable = Drawable.createFromStream(stream, nextImage);
        flagImageView.setImageDrawable(drawable);
        animate(false); // 在屏幕上动画旗帜

    } catch (IOException exception) {
        Log.e("TAG", "Error loading " + nextImage);
    }

    Collections.shuffle(fileNameList); // 打乱文件名

    // 将正确答案放在 fileNameList 的末尾
    int correct = fileNameList.indexOf(correctAnswer);
    fileNameList.add(fileNameList.remove(correct));
}
```

**图 4.38** MainActivity 方法 loadNextFlag。（部分 2.）

## 4.7 MainActivityFragment 类

```java
// 根据 guessRows 的值添加 2, 4, 6 或 8 个 Button
for (int row = 0; row < guessRows; row++) {
    // 将 Button 放置在 currentTableRow 中
    for (int column = 0;
        column < guessLinearLayouts[row].getChildCount();
        column++) {
        // 获取 Button 引用进行配置
        Button newGuessButton = 
            (Button)guessLinearLayouts[row].getChildAt(column);
        newGuessButton.setEnabled(true);

        // 获取国家名称并将其设置为 newGuessButton 的文本
        String fileName = fileNameList.get(row * 2) + column;
        newGuessButton.setText(getCountryName(fileName));
    }
}
// 随机用正确答案替换其中一个 Button
int row = random.nextInt(guessRows); // 随机选择行
int column = random.nextInt(2); // 随机选择列
LinearLayout row = guessLinearLayouts[row]; // 获取行
String countryName = getCountryName(correctAnswer);
(Button)row.getChildAt(column).setText(countryName);
```

**图 4.38** | MainActivity 方法 loadNextImage （2 部分中的 2 部分）

第 179 行从`queryList`移除第一个名称并存储在`nextImage`中。我们还将其保存到`correctAnswer`中，以便稍后判断用户是否猜对。接下来，我们让 getActivity 视图在`numberTextView`中显示当前数字（第 184–185 行），使用格式化的字符串资源`question`。

第 188 行从`nextImage`提取用于加载图像的 assets 数字。接下来，我们获取`AssetManager`，在`with-resources`语句中使用它打开`InputStream`（包 java.io）来读取旗帜文件的字节。我们将该流作为`createFrom`类的参数，它创建了一个`Drawable`对象（android.graphics.drawable）。通过调用`setImageDrawable`将`Drawable`设置为`ImageView`的项进行显示。如果发生异常，我们记录调试日志（第 204 行）。我们调用`animate`方法，将下一旗和答案按钮到屏幕上（第 201 行）。

第 207 行打乱`fileNameList`，第 210–211 行定位`correctAnswer`并将其移动到`fileNameList`的末尾——稍后我们将此答案插入随机的猜按钮中。

- 第 214–222 行遍历当前`guessRows`对应的`guessLinearLayouts`中的按钮。对于每个`Button`：

    - 第 220–221 行获取`Button`的引用

    - 第 222 行启用`Button`

    - 第 225 行从`fileNameList`获取名称

    - 第 226 行用`getCountryName`方法（4.7.8）返回的名称设置`Button`文本。

第 231–235 行根据当前的`guessRows`随机选择行和列，然后设置相应`Button`的文本。

### 4.7.8 方法 getCountryName

方法`getCountryName`（图 4.39）从图像获取国家名称。首先，我们从下划线处获取一个字符串。然后，我们调用字符串方法将下划线替换为 '-' 并返回国家名称。`getCountryName`方法解析下划线并返回国家名称。

```java
// 解析下划线并返回国家名称
private String getCountryName(String name) {
    return name.substring(0, name.indexOf('-'));
}
```

**图 4.39** | MainActivityFragment getCountryName。

### 4.7.9 方法 animate

方法`animate`（图 4.40）在测验的整个布局 (`quizILayout`) 上执行圆形动画。第 246–253 行计算测验中心。`animate`方法接受一个参数`animateOut`，用于决定显示还是隐藏圆形。

```java
// 动画整个测验
private void animate(boolean animateOut) {
    // 如果
    if (animateOut)
        return;

    // 计算中心 x 和 y
    int centerX = (quizItemLayout.getLeft() + quizItemLayout.getRight()) / 2;
    int centerY = (quizItemLayout.getTop() + quizItemLayout.getBottom()) / 2;
    // 计算半径
    int radius = Math.min(quizItemLayout.getWidth(), quizItemLayout.getHeight());

    Animator animator;
    // 创建展开动画
    animator = ViewAnimationUtils.createCircularReveal(quizILayout, centerX, centerY, radius, 0);
    // 添加监听器
    animator.addListener(new AnimatorListenerAdapter() {
        // 当动画结束时
        @Override
        public void onAnimationEnd(Animator animation) {
            loadNextFlag();
        }
    });
    } else {
        // 动画入
        animator = ViewAnimationUtils.createCircularReveal(quizILayout, centerX, centerY, 0, radius);
    }
    // 设置动画时长为 500 ms
    animator.setDuration(500);
    // 启动动画
    animator.start();
}
```

**图 4.40** | MainActivityFragment animate。（2 部分中的 1 部分）

158 第 4 章 旗帜猜验应用

## 4.7.10 实现 OnClickListener 的匿名内部类

在图 4.34 中，第 97–102 行将`guessButtonListener`（图 4.41）注册为每次猜测的事件处理程序。实例变量`guessButtonEventListener`指向一个实现`OnClickListener`的匿名内部类，用于响应按钮点击事件。我们获取按钮的文本（第 290 行）和解析后的名称（第 291 行），并将`totalGuesses`加1。如果猜测正确（第 294 行），我们给`correctNames`加1。接下来，我们将`answerTextView`的文本设置为国家名称，并将颜色更改为常量`R.color.correct_answer`所表示的颜色（绿色），然后使用我们的工具方法`disableButtons`（第 4.7.10 节）禁用所有按钮。



```java
// 当触摸一个猜测按钮时
private OnClickListener guessButtonListener = new OnClickListener() {
    @Override
    public void onClick(View v) {
        Button button = (Button) v;
        String guess = button.getText().toString();
        String answer = getCountryName(correctAnswer);
        ++totalGuesses; // 增加用户进行的猜测次数
        if (guess.equals(answer)) { // 如果猜测正确
            ++correctAnswers; // 增加正确答案的数量
            // 用绿色字体显示正确答案
            answerTextView.setText(answer + " ");
            answerTextView.setTextColor(R.color.correct_answer,
                getContext().getColor(getContext().theme()));
        }
        disableButtons(button); // 如果用户正确识别了 FLAGS_IN_QUIZ 旗帜
        if (correctAnswers == FLAGS_IN_QUIZ) {
            // 使用 DialogFragment 显示测验统计数据并开始新游戏
            DialogFragment quizResults = new DialogFragment() {
                // 创建一个 AlertDialog 并返回它
                @Override
                public void onCreate(Bundle bundle) {
                    AlertDialog.Builder builder = new AlertDialog.Builder(getActivity());
                    builder.setMessage(R.string.message)
                        .setText(String.format(R.string.results,
                        totalGuesses, (0 / (double)totalGuesses)));
                    // "重置测验"
                    builder.setPositiveButton(R.string.reset_quiz,
                        new DialogInterface.OnClickListener() {
                            @Override
                            public void onClick(DialogInterface dialog, int id) {
                                resetQuiz();
                            }
                        });

                    return builder.create(); // 返回 AlertDialog
                }
            };

            // 使用 fragmentManager 显示 DialogFragment
            quizResults.setCancelable(false);
            quizResults.show(getFragmentManager(), "quiz results");

        } else { // 答案正确但测验未结束
            // 2 秒后加载下一面旗帜
            handler.postDelayed(new Runnable() {
                @Override
                public void run() {
                    animate(true); // 动画旗帜移出屏幕
                }
            }, 2000); // 2000 毫秒对应 2 秒延迟
        }
    } else { // 答案错误
        flagImageView.startAnimation(shakeAnimation); // 播放抖动画

        // 用红色显示“错误！”
        answerText.setText(R.string.incorrect_answer);
        answerText.setText(getResources().getColor(R.color.incorrect), getContext().getTheme());
        gussButton.setEnabled(false); // 禁用错误的答案
    }
}
```

图 4.41 | 实现 `OnClickListener` 的匿名内部类。（部分 2/2）。

如果 `correctAnswers` 等于 `FLAGS_IN_QUIZ`（第 306 行），则测验结束。第 308–332 行创建了一个扩展 `DialogFragment`（包 `android.support.app`）的新匿名内部类，用于显示结果。`DialogFragment` 的 `onCreateDialog` 使用 `AlertDialog.Builder`（稍后将讨论）来配置并创建一个显示测验的 `AlertDialog`，然后返回它。当用户触摸测验按钮时，会调用 `resetQuiz` 开始一个新游戏（第 325 行）。这表明答案是不可取消的——用户必须与对话框交互，因为点击对话框外部或按返回键将使用户带回测验。要显示 `DialogFragment`，第 336 行调用了它的 `show` 方法，并将 `getFragmentManager` 返回的 `FragmentManager` 和一个字符串作为参数传递。第二个参数可以配合 `FragmentManager` 方法 `getFragmentTag` 使用，以便稍后获取 `DialogFragment` 的引用——我们在这个应用中没有使用此功能。

如果 `correctAnswers` 小于 `FLAGS_IN_QUIZ`，则第 340–346 行调用了 `Handler` 对象的 `postDelayed` 方法。第一个参数是一个实现 `Runnable` 接口的匿名内部类——这代表了要执行的任务 `animate(true)`，它会动画化答案旗帜并在几毫秒后开始下个问题。如果猜测错误，第 350 行调用 `ImageView.startAnimation` 方法来播放在 `onCreateView()` 中加载的 `shakeanimation` 动画。我们还设置了 `answerTextView` 用红色显示“错误！”（第 351–355 行），以引导用户对应正确答案。

## 外观外观选项

你可以使用 `AlertDialog.setTitle()` 设置 `AlertTitle`（显示在对话框消息上方）。根据 Android 对对话框的设计指南（http://developer.android.com/design/building-blocks/dialogs.html），你可能不需要创建标题。对于“涉及潜在数据丢失、连接中断、额外费用等高风险操作”，对话框应该显示标题——此外，对话框应该显示标题。

# 162 第 4 章 国旗测试应用

偏好设置会自动存储在设备上的 `SharedPreferences` 文件中。如果文件不存在，则会创建；否则，将进行更新。我们删除了其中其他未使用的自动生成代码。

```java
// SettingsActivityFragment.java
// 用于管理应用设置的 PreferenceFragment 子类
package com.deitf.flagquiz;
import android.os.Bundle;
import android.preference.PreferenceFragment;

public class SettingsActivityFragment extends PreferenceFragment {
    // 从 res/xml 中的 .xml 文件创建 GUI
    @Override
    public void onCreate(Bundle bundle) {
        addPreferencesFromResource(R.xml.preferences); // 从 XML 加
    }
}
```

**图 4.44** | `PreferenceFragment` 的子类 `SettingsActivityFragment` 显示了应用的偏好设置。

## 4.10 AndroidManifest.xml

4.45 显示了 Flag 应用自动生成的清单文件。每个 `Activity` 都必须在 `AndroidManifest.xml` 中声明；否则 Android 将不知道该 `Activity` 的存在且无法启动它。当你创建应用时，IDE 在 `AndroidManifest.xml` 中声明了 `MainActivity`（第 11–21 行）。符号

第 12 行中的

`.MainActivity`

表示该类位于第 2 行指定的包中，它是 `com.deitf.flagquiz.MainActivity` 的简写。

我们添加了第 14 行，稍后我们将进行讨论。

```xml
<xml version="1.0" encoding="utf-8"?>
<manifest package="com.deitf.flagquiz"
xmlns:android="http://schemas.android.com/apk/res/android">
    <application
        android:allowBackup="true"
        android:icon="@mipmap/launcher"
        android:label="@string/app_name"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <activity
            android:name=".MainActivity"
            android:label="@string/app_name"
```

**图 4.45** | 声明了 `SettingsActivity` 的 `AndroidManifest.xml`。（2 部分中的第 1 部分。）

## 4.10 AndroidManifest.xml

```xml
  android:launchMode="singleTop"
  android:theme="@style/AppTheme.NoActionBar"
  <intent-filter>
    <action android:name="android.intent.action.MAIN"/>
    <category android:name="android.intent.category.LAUNCHER"/>
  </intent-filter>
  <activity>
    android:name="SettingsActivity"
    android:label="@string/title_activity_settings"
    android:parentActivityName="MainActivity"
    android:theme="@style/AppTheme.NoActionBar">
    <meta-data
      android:name="android.support.PARENT_ACTIVITY"
      android:value="com.deitel.flagquiz.MainActivity"/>
  </activity>
</manifest>
```

图 4.45 声明了 `SettingsActivity` 的 `AndroidManifest.xml`。

当你将 `SettingsActivity` 添加到项目中（第 4.4.1 节）时，IDE会自动将 `SettingsActivity` 添加到清单文件中（第 22–30 行）。如果你使用 IDE 工具创建新的 `Activity`，则必须通过插入类似第 22–30 行的 `<activity>` 元素来声明新 `Activity`。有关清单的完整细节，请访问

> http://developer.android.com/guide/topics/manifest/intro.html

## 启动模式

第 14 行指定了 `MainActivity` 的 `launchMode`。默认情况下，每个 `Activity` 都使用“标准”（standard）启动模式。当 Android 接收到启动 `Activity` 的 `Intent` 时，Android 会创建一个 `Activity` 新实例。

回顾第 4.4.12 节，你指定了 `SettingsActivity` 的层级父类。再次，这使得 Android 能够在应用上启用向上按钮，用户可以通过它可以导航回父 `Activity`。当用户点击此按钮且父 `Activity` 使用“标准”启动模式时，Android 将使用 `Intent` 启动父 `Activity`。这会导致产生一个新的 `MainActivity` 实例。这也会导致国旗测试应用在 `MainActivity` 的 `SharedPreferencesChangeListener`（第 6.7 节）中崩溃，因为它尝试访问已不再存在的 `Fragment`——该 `Fragment` 被定义在另一个 `MainActivity` 实例中。

第 14 行通过将 `MainActivity` 的 `launchMode` 更改为“singleTop”解决了这个问题。使用此启动模式，当用户点击向上按钮时，Android 会将现有的 `MainActivity` 带到前台，而不是创建一个新的 `MainActivity` 对象。有关 `<activity>` 元素的 `launchMode` 值的更多信息，请访问

> https://developer.android.com/guide/topics/manifest/activity.html#launchmode

# 第 4 章 国旗测试应用

## 4.11 总结

在本章中，你构建了一个测试用户正确识别国旗能力的国旗测试应用。本章的一个关键特性是使用 `Fragments` 来创建 `Activity` GUI 的部分。你使用了两个 `Activity` 分显示 `MainActivity` 和 `SettingsActivity`。为了在应用处于竖屏方向运行时启动 `SettingsActivity`，你使用了一个 `Activity`；当应用处于横屏方向运行时，你使用一个 `Activity` 显示 `Fragments`——这更好地利用了可用的空间。你使用了 `PreferenceFragment` 的子类来自动维护和持久化应用设置，并使用了 `DialogFragment` 的子类向用户显示一个对话框。我们讨论了 `Fragment` 生命周期周期的一部分，并展示了如何使用 `FragmentManager` 获取 `Fragment` 的引用，以便你可以通过编程方式与其交互。

在竖屏方向下，你为 `MainActivity` 菜单项提供了一个图标。点击应用栏上，用户可以点击显示 `SettingsActivity`。为了启动 `SettingsActivity`，你使用了 `Intent`。我们还使用了 `Toast` 来显示错误信息。

为了在延迟后显示下一面国旗，你使用了 `Handler`，它会在指定的毫秒后执行任务。你了解到 `Runnable` 是在创建 `Handler` 的线程中执行的。我们在 XML 中定义了动画并将其应用于 `ImageView`。我们还使用了 `ViewAnimations` 创建问题之间的切换动画。你学会了如何使用内置的日志类进行日志调试。你还使用了 `java.util` 包中的各种类和接口，包括 `List` 和 `Set`。

最后，我们展示了应用的 `AndroidManifest.xml` 文件。我们讨论了自动生成的 `<activity>` 元素。我们将 `MainActivity` 的 `launchMode` 更改为 "singleTop"，以便应用可以使用 `MainActivity` 实例，而不是每次用户点击应用栏上的向上按钮时都创建一个新的。

在第 5 章中，我们介绍了 `Doodle` 应用，它利用 Android 的图形功能将设备屏幕变成虚拟画布。你还将学习 Android 的沉浸式模式和打印功能。

# 第 5 章 Doodlez App

# 目录

## 5.1 引言

## 5.2 在 Android 虚拟设备 (AVD) 中测试 Doodlez App

## 5.3 技术概述

- 5.3.1 `Activity` 与生命周期方法

- 5.3.2 自定义 `View`

- 5.3.3 使用 `SensorManager` 监听加速度计事件

- 5.3.4 自定义对话框

- 5.3.5 使用 `Canvas` 和 `Bitmap` 绘图

- 5.3.6 处理多控事件并在 `List` 中存储路径

- 5.3.7 保存到设备

- 5.3.8 打印与 Android Support Library 的 `Printer` 类



## 5.1 引言

Doodlez 应用允许你通过在屏幕上拖动一个或多个手指来绘图（图 5.1）。该应用提供了设置绘制颜色和线条宽的选项。其他选项允许你：

- 清除屏幕
- 在你的设备上保存当前绘制，以及
- 打印当前绘制。

根据你的设备的屏幕尺寸，应用的部分或全部选项将以图标形式直接显示在应用栏上——无法下的部分将以文本形式显示在应用栏上的溢出菜单 (`...`) 中。

![图 5.1](img/8c2e54963088643b07bd4401c4f77_203_0.png)

**图 5.1** | 完成绘制的 Doodlez 应用。

此应用引入了 Android 6.0 的新权限机制。例如，Android 需要用户权限来允许应用在设备上保存文件（如此应用的画）。在 Android 6.0 中，应用不再在安装时通过应用所需的完整权限列表来提示用户，而是在首次执行某项特定任务时才单独请求每项权限。在此应用中，当用户尝试保存绘制内容时，Android 会请求权限。

首先，你将测试此应用。然后，我们将概述构建它的技术。接下来，你将设计应用的 GUI。最后，我们将通过过应用的完整源代码，重点介绍应用的新功能。

## 5.2 在 Android 虚拟设备 (AVD) 中测试 Doodlez App

### 打开并运行应用

打开 Android Studio 并从 Doodlez 书籍示例打开 Doodlez 应用，然后在 AVD 或设备上执行该应用。这会构建项目并运行应用。

### 理解应用选项

图 5.2(a) 和 (b) 显示了 Nexus 6 AVD 上的应用栏和溢出菜单，图 5.2(c) 显示了 Nexus 9 AVD 上的应用栏。

| a) Nexus 6 AVD 栏 | |
| :--- | :--- |
| Doodlez | 清除绘制 |
| | 保存 |
| | 打印 |
| c) Nexus 9 AVD 栏——应用栏上有足够的空间将所有菜单项显示为图标 | |
| :--- | |
| Doodlez | |

**图 5.2** Doodlez 应用栏和溢出菜单。

a) 选择深绿色作为绘图颜色

b) 选择更粗的线条

| 选择颜色 | 选择线宽 |
| --- | --- |
| Alpha | |
| 红色 | |
| 绿色 | |
| 蓝色 | SET LINE WIDTH |
| SET COLOR | |

**图 5.6** 将颜色更改为深绿色并加粗线条。

![图 5.7](img/8c2e5496308864b3b07ddbd4401c4f77_207_0.png)

**图 5.7** 绘制茎部和草。

*完成绘制*

接下来，将绘图颜色更改为半透明蓝色（图 5.8(a)）并选择较细的线条（图 5.8(b)）。然后绘制雨滴（图 5.9）。

a) 选择蓝色作为绘图颜色 b) 选择更细的线条

### 选择颜色

- Alpha
- 红色
- 绿色
- 蓝色

### 选择线宽

- SET LINE WIDTH
- SET COLOR

**图 5.8** 将线条颜色更改为蓝色并缩小线条。

![图 5.9](img/8c2e5496308864b3b07ddbd4401c4f77_208_0.png)

**图 5.9** 使用新的线条颜色和线宽绘制雨。

### 保存图像

你可以将图像保存到设备并使用 Photos 应用查看。要这样做，请点击应用栏——或者如果图标未显示在应用栏上，则从选项菜单中保存。然后你可以通过打开 Photos 应用查看此图像以及存储在设备上的图像。

### 打印图像

打印图像，点击应用栏——如果图标未显示在应用栏上，则从选项菜单选择打印。这将显示打印选项对话。默认情况下，你可以将图像保存为 PDF 文档。要选择打印机，点击另存为 PDF 并从可用打印机列表中选择。如果列表中没有出现打印机，你需要配置 Cloud Print，有关此的信息，请访问

```
http://www.google.com/cloudprint/learn/
```

## 5.3 技术概述

本节介绍了我们在 Doodle 应用中使用的新技术。

### 5.3.1 Activity 和 Fragment 生命周期方法

Fragment 的生命周期与其父 Activity 的生命周期相连。有六个生命方法具有对应的 Fragment 生命周期方法——`onCreate`、`onStart`、`onResume`、`onPause`、`onStop` 和 `onDestroy`。当系统在 Activity 上调用这些方法时，它也会在所有附加到 Activity 的 Fragments 上调用对应的方法（以及可能的其他 Fragment 生命周期周期）。

此应用使用了 Fragment 生命周期方法 `onResume` 和 `onPause`。当 Fragment 位于屏幕上供用户与其进行交互时，Activity 的 `Resume` 方法会被调用。这是从 Fragment 的 `onResume` 方法调用的。在本应用中，`MainActivity` 重写了 `onResume` 以启用监听加速度计事件，使用户可以摇动设备来擦除绘制（第 5.7.3 节）。

当另一个 Activity 接收焦点时，Activity 的 `onPause` 方法会被调用，它会暂停并失去后台焦点。当 Activity 托管 Fragments 且 Activity 暂停时，其所有 Fragment 的 `onPause` 方法都会被调用。在本应用中，`MainActivity` 重写了 `onPause` 以挂起抖动加速事件的监听（第 5.7.4 节）。

![图 5.10](img/8c2e5496308864b3b07ddbd4401c4f77_209_0.png)

> **性能提示 5.1**
> 当应用暂停时，它应该移除传感器事件的监听器，这样这些事件在应用不在屏幕时就不会传递给应用。这可以节省电池。

我们需要需要讨论其他 Activity 和 Fragment 生命周期方法。有关完整的 Activity 生命周期更多信息，请访问

```
http://developer.android.com/reference/android/app/Activity.html#ActivityLifecycle
```

有关完整的 Fragment 生命周期更多信息，请访问

```
http://developer.android.com/guide/components/fragments.html#Lifecycle
```

### 5.3.2 自定义视图

你可以扩展 `View` 类或其一个子类创建一个自定义视图，正如我们对 `DoodleView`（第 5.8 节）所做的，它扩展了 `View`。要在布局-XML 文件中添加自定义组件，必须提供其完全限定名（即其包名和类名），因此在将其添加到布局之前，自定义视图类必须已经存在。我们在第 5.5.2 节中演示如何创建 `DoodleView` 类并将其添加到布局。

### 5.3.3 使用传感器监听加速度计事件

在本应用中，你可以摇动设备来擦除绘制。大多数设备都有加速度计来检测运动。目前支持的传感器包括重力、陀螺仪、光、线性加速度、磁场、方向、压力、接近、旋转向量和温度。你将使用 `Sensor` 的 `sensor-type` 来指定应用应该接收的传感器。传感器列表可以在此处找到

```
http://developer.android.com/reference/android/Sensor.html
```

我们 5.7 节中讨论加速度计。关于传感器的完整讨论，请参见

```
http://developer.android.com/guide/topics/sensors_overview.html
```

### 5.3.4 自定义视图

在本应用中，你可以摇动设备来擦除绘制。大多数设备都有加速度计来检测运动。目前支持的传感器包括重力、陀螺仪、光、线性加速度、磁场、方向、压力、接近、旋转向量和温度。你将使用 `Sensor` 的 `sensor-type` 来指定应用应该接收的传感器。传感器列表可以在此处找到

```
http://developer.android.com/reference/android/Sensor.html
```

我们 5.7 节中讨论加速度计。关于传感器的完整讨论，请参见

```
http://developer.android.com/guide/topics/sensors_overview.html
```

### 5.3.5 使用 Canvas、Paint 和 Bitmap 绘图

你可以使用方法绘制文本和圆形。`Canvas` 方法绘制（来自此处）。你可以将 `Canvas` 与 `Bitmap` 关联，然后使用它在屏幕上绘制，然后在 Photos 应用中显示。`Bitmap` 还可以保存——我们使用此功能将绘制存储在画廊中。画布每个绘制方法使用 `Paint` 对象来指定属性，包括颜色、线条粗细、字体大小等。这些在 `Doodle` class-can-be `View`（第 5.6 节）呈现。

### 5.3.6 处理多触摸事件和路径中的线条

你可以在屏幕上拖动多个手指。应用存储每个单独 `Path` 对象（`package android.graphics`）的信息，表示线段和曲线。你可以使用 `touchEvent`（第 5.8 节）触摸事件。此方法接收一个 `MotionEvent`（`package android.view`），其中包含发生的触摸事件类型以及生成事件的手指 ID（称为指针）。我们使用 ID 来区分不同的手指并向相应的 `Path` 对象添加信息。我们使用触摸事件类型来判断用户是否跨越屏幕、拖动或离开屏幕。

### 5.3.7 保存到设备

应用的保存选项允许你将绘制内容保存到设备。你可以通过从应用菜单中选择文件夹在 Photos 中查看存储图像的缩略图——点击缩略图查看全尺寸图像。`ContentResolver`（`package android.content`）允许应用在设备上读取数据和存储数据。你将使用 `ContentResolver`（第 5.8.11 节）和 `MediaStore.Images.Media` 类的 `insertImage` 方法将图像保存到 Photos 应用。`MediaStore` 管理存储在设备上的媒体文件（图像、音频和视频）。

### 5.3.8 打印与 Android Support PrintHelper 类

在此应用中，我们使用 Android 框架中的 `PrintHelper`（第 5.8.12 节）来打印当前图画。`PrintHelper` 类提供了一个用于选择打印机的界面，包含一个判断设备是否支持打印的方法，并提供了一个打印 `Bitmap` 的方法。`PrintHelper` 是 Android Support Library 的，该库为当前和旧版本的 Android 提供了新的 Android 特性。支持库还包含了额外的便利功能（如 `PrintHelper`），这些功能支持特定的 Android 版本。

### 5.3.9 新的 Android 6.0 (Marshmallow) 权限模型

在应用写入外部存储器之前，Android 需要 `android.permission.WRITE_EXTERNAL_STORAGE` 权限。对于 Doodle 应用，我们需要此权限来保存用户绘制的图像。

Android 6.0 (Marshmallow) 拥有一个全新的权限模型，旨在提供更好的用户体验。在 6.0 之前，用户需要授予应用可能需要的所有权限——这导致许多人不愿安装应用。使用新模型后，应用在安装时不会请求任何权限。相反，用户仅在首次使用某项功能时才会被要求授予权限。

一旦用户授予了权限，该应用将拥有该权限，直到：

- 应用被重新安装
- 用户通过 Android 设置更改了应用的权限。

你将在第 5.7.8–5.7.9 节中学习如何实现这种新的权限模型。

### 5.3.10 使用 Gradle 构建系统添加依赖

Android Studio 使用 Gradle 构建系统将你的代码编译为 APK 文件——即可安装的程序。Gradle 处理项目依赖关系，例如在构建过程中应用使用的任何库。对于 Doodle 应用，你将向项目添加一个支持库依赖，以便使用 `PrintHelper` 类打印图像（第 5.4.2 节）。

## 5.4 创建项目与资源

在本节中，你将创建项目、为应用项目导入 Material 图标，并使用 GUI 和你的应用 Java 代码所使用的各种资源。

### 5.4.1 创建项目

创建一个 Blank Activity 项目。在“新建项目”对话框的项目配置中指定以下值：

- 应用名称（Application name）：Doodle
- 包名域（Package Domain）：`doodle.com`（或指定你自己的域名）

对于“新建项目”对话框中的剩余步骤，请使用第 4.4.1 节中的相同设置。这将创建一个 `MainActivity`，它承载一个应用绘制区域的 Fragment 并响应用户的触摸操作。按照第 2.5.2 节的步骤为你的项目添加图标。

一旦在 Android Studio 中打开项目，在布局编辑器中，从虚拟设备下拉列表中选择 Nexus 6（图 2.11）。同时，删除 `fragment_main.xml` 中的 `Hello world!` TextView 以及 `activity_main.xml` 中的 `FloatingActionButton`。

使用主题编辑器（第 3.5.2 节）将 Material Blue 500 设置为应用的主色，将 Material Blue 设置为深色主色，浅蓝色设置为支持的强调色。此外，按照第 4.4.3 节的步骤配置项目以支持 Java SE 7。

### 5.4.2 为项目添加支持库

此应用需要 Android Support Library 来使用 `PrintHelper` 类。要将支持库作为项目添加，请遵循以下步骤：

1. 点击 `app` 文件夹，然后选择 Open Module Settings（打开模块设置）。
2. 在打开的 Project 窗口中，打开 Dependencies（依赖）标签卡。
3. 点击 Add 按钮 (`+`)，选择 Library dependency（库依赖）以打开 Choose Library dependency。
4. 从列表中选择 `support-v4 (com.android.support:support-v4:23.1.0)`，然后点击 OK。依赖项将出现在 Dependencies 标签卡中。
5. 点击 OK。IDE 将显示 Gradle sync in progress...，此时项目正在被配置为使用 Android Support Library。

关于如何使用和设置 Android Support Library 的更多信息，请访问：

```
http://developer.android.com/tools/support-library/setup.html
```

### 5.4.3 strings.xml

在 `strings.xml` 文件中，定义应用使用的字符串资源。这些字符串包括应用名称、菜单项文本和对话框标题等。例如：

```xml
<resources>
    <string name="app_name">Doodle</string>
    <string name="menu_clear">清除绘制</string>
    <string name="menu_save">保存</string>
    <string name="menu_print">打印</string>
    <string name="dialog_color_title">选择颜色</string>
    <string name="dialog_line_width_title">选择线宽</string>
</resources>
```

### 5.4.4 为菜单项导入主设计图标

为菜单项导入 Material Design 图标，以便在应用栏上显示。这些图标包括清除、保存和打印等操作。你可以从 Android Studio 的 Resource Manager 中导入图标，或者手动将图标文件放置在 `res/drawable` 目录中。

### 5.4.5 MainActivityFragmentMenu

`MainActivityFragment` 的菜单资源文件定义了应用栏上的菜单项。在 `res/menu` 目录下创建菜单文件，例如 `menu_main_fragment.xml`，并添加以下菜单项：

```xml
<menu xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto">
    <item
        android:id="@+id/action_clear"
        android:icon="@drawable/ic_clear"
        android:title="@string/menu_clear"
        app:showAsAction="ifRoom" />
    <item
        android:id="@+id/action_save"
        android:icon="@drawable/ic_save"
        android:title="@string/menu_save"
        app:showAsAction="ifRoom" />
    <item
        android:id="@+id/action_print"
        android:icon="@drawable/ic_print"
        android:title="@string/menu_print"
        app:showAsAction="ifRoom" />
</menu>
```

### 5.4.6 在 AndroidManifest.xml 中添加权限

在 `AndroidManifest.xml` 文件中添加 `WRITE_EXTERNAL_STORAGE` 权限，以便应用能够保存图像到设备：

```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.doodle.doodle">
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
    ...
</manifest>
```

## 5.5 构建应用 GUI

本节介绍如何构建应用的图形用户界面（GUI）。我们将创建各个布局文件，并配置自定义视图和对话框。

### 5.5.1 用于 MainActivity 的 content_main.xml

`content_main.xml` 是 `MainActivity` 的布局文件，它包含一个 `FrameLayout` 用于承载 `MainActivityFragment`。示例布局如下：

```xml
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/fragment_container"
    android:layout_width="match_parent"
    android:layout_height="match_parent" />
```

### 5.5.2 用于 MainActivityFragment 的 main_layout.xml

`main_layout.xml` 是 `MainActivityFragment` 的布局文件，它包含一个 `DoodleView` 自定义视图。示例布局如下：

```xml
<com.doodle.doodle.DoodleView
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/doodle_view"
    android:layout_width="match_parent"
    android:layout_height="match_parent" />
```

### 5.5.3 用于 ColorDialogFragment 的 color_fragment.xml

`color_fragment.xml` 是 `ColorDialogFragment` 的布局文件，它包含用于选择颜色的 `SeekBar` 控件。示例布局如下：

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="vertical"
    android:padding="16dp">
    <TextView
        android:id="@+id/alpha_label"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Alpha" />
    <SeekBar
        android:id="@+id/alpha_seekbar"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:max="255" />
    <!-- 红色、绿色、蓝色 SeekBar 类似 -->
</LinearLayout>
```

### 5.5.4 用于 LineWidthFragment 的 line_width.xml

`line_width.xml` 是 `LineWidthDialogFragment` 的布局文件，它包含一个用于选择线条宽度的 `SeekBar`。示例布局如下：

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="vertical"
    android:padding="16dp">
    <TextView
        android:id="@+id/width_label"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="线条宽度" />
    <SeekBar
        android:id="@+id/width_seekbar"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:max="50" />
</LinearLayout>
```

### 5.5.5 传递 EraseImageDialogFragment

`EraseImageDialogFragment` 是一个简单的对话框，用于确认是否清除绘制。它不需要自定义布局，可以使用默认的 `AlertDialog` 构建。

## 5.6 MainActivity 类

`MainActivity` 是应用的主 Activity，它负责管理 Fragment 和菜单操作。主要职责包括：

- 在 `onCreate` 中设置内容视图并添加 `MainActivityFragment`。
- 重写 `onResume` 和 `onPause` 以启用/禁用加速度计监听。
- 处理菜单项的点击事件，如清除、保存和打印。

示例代码结构：

```java
public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        // 添加 Fragment
        if (savedInstanceState == null) {
            getSupportFragmentManager().beginTransaction()
                .add(R.id.fragment_container, new MainActivityFragment())
                .commit();
        }
    }

    @Override
    protected void onResume() {
        super.onResume();
        // 启用加速度计监听
    }

    @Override
    protected void onPause() {
        super.onPause();
        // 禁用加速度计监听
    }
}
```

## 5.7 MainActivityFragment 类

`MainActivityFragment` 是承载 `DoodleView` 的 Fragment，它处理用户交互和菜单操作。

### 5.7.1 package 语句、import 语句与字段

在文件开头，声明包名和必要的导入语句，并定义字段，如 `DoodleView` 实例和传感器管理器。

```java
package com.doodle.doodle;

import android.content.Context;
import android.hardware.Sensor;
import android.hardware.SensorManager;
import android.os.Bundle;
import android.support.v4.app.Fragment;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;

public class MainActivityFragment extends Fragment {
    private DoodleView doodleView;
    private SensorManager sensorManager;
    private Sensor accelerometer;
    // 其他字段
}
```

### 5.7.2 重写方法 onCreate 和 onCreateView

在 `onCreate` 中初始化传感器管理器，在 `onCreateView` 中加载布局并获取 `DoodleView` 实例。

```java
@Override
public void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    sensorManager = (SensorManager) getActivity().getSystemService(Context.SENSOR_SERVICE);
    accelerometer = sensorManager.getDefaultSensor(Sensor.TYPE_ACCELEROMETER);
}

@Override
public View onCreateView(LayoutInflater inflater, ViewGroup container,
                         Bundle savedInstanceState) {
    View view = inflater.inflate(R.layout.fragment_main, container, false);
    doodleView = view.findViewById(R.id.doodle_view);
    return view;
}
```

### 5.7.3 方法 onResume 和 enableAccelerometerListening

在 `onResume` 中调用 `enableAccelerometerListening` 方法，注册加速度计监听器。

```java
@Override
public void onResume() {
    super.onResume();
    enableAccelerometerListening();
}

private void enableAccelerometerListening() {
    if (accelerometer != null) {
        sensorManager.registerListener(accelerometerListener, accelerometer,
                SensorManager.SENSOR_DELAY_NORMAL);
    }
}
```

### 5.7.4 方法 onPause 和 disableAccelerometerListening

在 `onPause` 中调用 `disableAccelerometerListening` 方法，注销加速度计监听器。

```java
@Override
public void onPause() {
    super.onPause();
    disableAccelerometerListening();
}

private void disableAccelerometerListening() {
    if (accelerometer != null) {
        sensorManager.unregisterListener(accelerometerListener);
    }
}
```

### 5.7.5 处理 AccelerometerEvents 的匿名内部类

定义一个 `SensorEventListener` 的匿名内部类，处理加速度计事件。当设备摇动时，清除绘制。

```java
private final SensorEventListener accelerometerListener = new SensorEventListener() {
    @Override
    public void onSensorChanged(SensorEvent event) {
        float x = event.values[0];
        float y = event.values[1];
        float z = event.values[2];
        // 检测摇动并清除绘制
        if (Math.abs(x) > 10 || Math.abs(y) > 10 || Math.abs(z) > 10) {
            doodleView.clear();
        }
    }

    @Override
    public void onAccuracyChanged(Sensor sensor, int accuracy) {
        // 不需要处理
    }
};
```

### 5.7.6 方法 onCreateOptionsMenu

在 `onCreateOptionsMenu` 中加载菜单资源。

```java
@Override
public void onCreateOptionsMenu(Menu menu, MenuInflater inflater) {
    inflater.inflate(R.menu.menu_main_fragment, menu);
    super.onCreateOptionsMenu(menu, inflater);
}
```

### 5.7.7 重写方法 onOptionsItemSelected

在 `onOptionsItemSelected` 中处理菜单项的点击事件。

```java
@Override
public boolean onOptionsItemSelected(MenuItem item) {
    switch (item.getItemId()) {
        case R.id.action_clear:
            doodleView.clear();
            return true;
        case R.id.action_save:
            saveImage();
            return true;
        case R.id.action_print:
            printImage();
            return true;
        default:
            return super.onOptionsItemSelected(item);
    }
}
```

### 5.7.8 方法 saveImage

`saveImage` 方法处理保存图像的逻辑，包括请求权限和调用 `DoodleView` 的保存方法。

```java
private void saveImage() {
    if (ContextCompat.checkSelfPermission(getActivity(),
            Manifest.permission.WRITE_EXTERNAL_STORAGE) != PackageManager.PERMISSION_GRANTED) {
        requestPermissions(new String[]{Manifest.permission.WRITE_EXTERNAL_STORAGE}, REQUEST_SAVE_IMAGE);
    } else {
        doodleView.saveImage();
    }
}
```

### 5.7.9 重写方法 onRequestPermissionsResult

在 `onRequestPermissionsResult` 中处理权限请求的结果。

```java
@Override
public void onRequestPermissionsResult(int requestCode, String[] permissions, int[] grantResults) {
    if (requestCode == REQUEST_SAVE_IMAGE) {
        if (grantResults.length > 0 && grantResults[0] == PackageManager.PERMISSION_GRANTED) {
            doodleView.saveImage();
        } else {
            // 显示提示信息
        }
    }
}
```

### 5.7.10 方法 getView 和 setDialogClass

这些方法用于获取 `DoodleView` 实例和设置对话框类。

```java
public DoodleView getDoodleView() {
    return doodleView;
}

public void setDialogClass(Class<?> dialogClass) {
    // 设置对话框类
}
```

## 5.8 DoodleView

`DoodleView` 是自定义视图，负责处理绘制、触摸事件和图像保存。

### 5.8.1 package 语句与 import 语句

声明包名和导入必要的类。

```java
package com.doodle.doodle;

import android.content.Context;
import android.graphics.Bitmap;
import android.graphics.Canvas;
import android.graphics.Paint;
import android.graphics.Path;
import android.util.AttributeSet;
import android.view.MotionEvent;
import android.view.View;
```

### 5.8.2 静态与实例变量

定义静态变量和实例变量，如画笔、路径和颜色。

```java
private Paint paint;
private Bitmap bitmap;
private Canvas canvas;
private Path path;
private int currentColor;
private int lineWidth;
// 其他变量
```

### 5.8.3 构造函数

在构造函数中初始化画笔和路径。

```java
public DoodleView(Context context, AttributeSet attrs) {
    super(context, attrs);
    paint = new Paint();
    paint.setAntiAlias(true);
    paint.setStyle(Paint.Style.STROKE);
    paint.setStrokeCap(Paint.Cap.ROUND);
    path = new Path();
    currentColor = Color.BLACK;
    lineWidth = 5;
}
```

### 5.8.4 重写方法 onSizeChanged

在 `onSizeChanged` 中创建 `Bitmap` 和 `Canvas`。

```java
@Override
protected void onSizeChanged(int w, int h, int oldw, int oldh) {
    super.onSizeChanged(w, h, oldw, oldh);
    bitmap = Bitmap.createBitmap(w, h, Bitmap.Config.ARGB_8888);
    canvas = new Canvas(bitmap);
}
```

### 5.8.5 方法 drawColor, setColor, setLineWidth 和 getWidth

这些方法用于设置颜色、线宽和获取宽度。

```java
public void drawColor(int color) {
    canvas.drawColor(color);
    invalidate();
}

public void setColor(int color) {
    currentColor = color;
    paint.setColor(color);
}

public void setLineWidth(int width) {
    lineWidth = width;
    paint.setStrokeWidth(width);
}

public int getViewWidth() {
    return getWidth();
}
```

### 5.8.6 重写方法 onTouchEvent

在 `onTouchEvent` 中处理触摸事件，根据动作调用相应的方法。

```java
@Override
public boolean onTouchEvent(MotionEvent event) {
    int action = event.getActionMasked();
    int pointerIndex = event.getActionIndex();
    int pointerId = event.getPointerId(pointerIndex);

    switch (action) {
        case MotionEvent.ACTION_DOWN:
            touchStarted(event, pointerId);
            break;
        case MotionEvent.ACTION_MOVE:
            touchMoved(event, pointerId);
            break;
        case MotionEvent.ACTION_UP:
            touchEnded(event, pointerId);
            break;
    }
    invalidate();
    return true;
}
```

### 5.8.7 touchStarted

`touchStarted` 方法在手指按下时创建新的路径。

```java
private void touchStarted(MotionEvent event, int pointerId) {
    float x = event.getX(event.findPointerIndex(pointerId));
    float y = event.getY(event.findPointerIndex(pointerId));
    path = new Path();
    path.moveTo(x, y);
    paths.put(pointerId, path);
}
```

### 5.8.8 touchMoved

`touchMoved` 方法在手指移动时更新路径。

```java
private void touchMoved(MotionEvent event, int pointerId) {
    int index = event.findPointerIndex(pointerId);
    float x = event.getX(index);
    float y = event.getY(index);
    Path path = paths.get(pointerId);
    if (path != null) {
        path.lineTo(x, y);
        canvas.drawPath(path, paint);
    }
}
```

### 5.8.9 saveImage

`saveImage` 方法将 `Bitmap` 保存到设备。

```java
public void saveImage() {
    String savedUrl = MediaStore.Images.Media.insertImage(
            getContext().getContentResolver(), bitmap, "Doodle", "Doodle drawing");
    // 显示保存成功的提示
}
```

### 5.8.10 printImage

`printImage` 方法使用 `PrintHelper` 打印图像。

```java
public void printImage() {
    PrintHelper printHelper = new PrintHelper(getContext());
    printHelper.printBitmap("Doodle", bitmap);
}
```

## 5.9 ColorDialogFragment 类

`ColorDialogFragment` 是一个对话框，用于选择绘制颜色。

### 5.9.1 重写方法 onCreateDialog

在 `onCreateDialog` 中构建对话框并加载布局。

```java
@Override
public Dialog onCreateDialog(Bundle savedInstanceState) {
    AlertDialog.Builder builder = new AlertDialog.Builder(getActivity());
    View view = getActivity().getLayoutInflater().inflate(R.layout.dialog_color, null);
    builder.setView(view);
    // 设置 SeekBar 监听器
    return builder.create();
}
```

### 5.9.2 getDialogFragment

静态方法用于创建 `ColorDialogFragment` 实例。

```java
public static ColorDialogFragment newInstance() {
    return new ColorDialogFragment();
}
```

### 5.9.3 重写生命周期 onDetach

在 `onDetach` 中清理资源。

```java
@Override
public void onDetach() {
    super.onDetach();
    // 清理资源
}
```

### 5.9.4 响应 Alpha、绿色、蓝色 Seekbars 事件的匿名内部类

为每个 `SeekBar` 设置监听器，更新颜色值。

```java
SeekBar alphaSeekBar = view.findViewById(R.id.alpha_seekbar);
alphaSeekBar.setOnSeekBarChangeListener(new SeekBar.OnSeekBarChangeListener() {
    @Override
    public void onProgressChanged(SeekBar seekBar, int progress, boolean fromUser) {
        // 更新 alpha 值
    }
    // 其他回调方法
});
```

## 5.10 LineWidthDialogFragment 类

`LineWidthDialogFragment` 是一个对话框，用于选择线条宽度。

### 5.10.1 方法 onCreateDialog

在 `onCreateDialog` 中构建对话框并加载布局。

```java
@Override
public Dialog onCreateDialog(Bundle savedInstanceState) {
    AlertDialog.Builder builder = new AlertDialog.Builder(getActivity());
    View view = getActivity().getLayoutInflater().inflate(R.layout.dialog_line_width, null);
    builder.setView(view);
    // 设置 SeekBar 监听器
    return builder.create();
}
```

### 5.10.2 响应 width-SeekBar 事件的匿名内部类

为宽度 `SeekBar` 设置监听器，更新线条宽度。

```java
SeekBar widthSeekBar = view.findViewById(R.id.width_seekbar);
widthSeekBar.setOnSeekBarChangeListener(new SeekBar.OnSeekBarChangeListener() {
    @Override
    public void onProgressChanged(SeekBar seekBar, int progress, boolean fromUser) {
        // 更新线条宽度
    }
    // 其他回调方法
});
```

## 5.11 EraseImageDialogFragment 类

`EraseImageDialogFragment` 是一个确认对话框，用于清除绘制。

```java
public class EraseImageDialogFragment extends DialogFragment {
    @Override
    public Dialog onCreateDialog(Bundle savedInstanceState) {
        AlertDialog.Builder builder = new AlertDialog.Builder(getActivity());
        builder.setMessage("确定要清除绘制吗？")
               .setPositiveButton("清除", (dialog, id) -> {
                   // 清除绘制
               })
               .setNegativeButton("取消", (dialog, id) -> {
                   // 取消操作
               });
        return builder.create();
    }
}
```

## 5.12 总结

在本章中，你学习了如何构建一个功能完整的绘图应用 Doodlez。你掌握了以下关键概念：

- 使用自定义视图（`DoodleView`）处理触摸事件和绘制。
- 使用 `Canvas`、`Paint` 和 `Bitmap` 进行绘图。
- 处理多触摸事件，使用 `Path` 存储线条。
- 使用传感器（加速度计）检测设备摇动。
- 使用 Android 6.0 的新权限模型请求运行时权限。
- 使用 `PrintHelper` 打印图像。
- 使用 `ContentResolver` 和 `MediaStore` 保存图像到设备。
- 使用 Gradle 构建系统添加依赖。

通过完成此应用，你已具备开发更复杂 Android 应用的基础能力。



`http://developer.android.com/tools/support-library`
`http://developer.android.com/tools/support-library/setup.html`

### 5.4.3 strings.xml

你已经在前面的章节中创建了资源，因此我们在这里只显示部分 String 资源名称和对应的值（图 10）。双击`res/values`文件夹中的`strings`，然后点击 Open editor 链接以显示 Translations Editor，从而创建这些资源。

> **外观观察 5.2**

> 对于支持大写字母的语言，Google 的 Material 设计规范指示明按钮的文本应使用全大写字母（例如，CANCEL 或 SET COLOR）。

| Key | 默认值 |
|--- | :--- |
| button_erase | Erase Image |
| button_set_color | Set Color |
| button_set_line_width | Set Line Width |
| line_imageview_description | This displays the line thickness |

图 5.10 | Doodle 应用中使用的 String 资源（第 2 部分1）。

| Key | 默认值 |
|---|---|
| label_alpha | Alpha |
| label_red | Red |
| label_green | Green |
| label_blue | Blue |
| menuitem_color | Color |
| menuitem_delete | Erase Drawing |
| menuitem_line_width | Line Width |
| menuitem_save | Save |
| menuitem_print | Print |

## 5.4.4 为应用导入设计图标

请记住，打印功能在 4.4 之前的版本中不可用。如果你正在开发具有多个版本菜单的应用，你可能希望使用资源限定符创建多个菜单。例如，你可以为 Android 4.4 之前的版本创建一个菜单资源，为 4.4 及更高版本创建另一个。在预 4.4 的菜单资源中，你可以省略旧版本不支持的选项。

### 5.4.5 创建菜单

要创建菜单，请遵循以下步骤：

1. 右键点击`res/menu`文件夹并选择 New > Menu resource file 打开 New Resource 对话框。

2. 在 File name 中输入`doodle_menu.xml`并点击 OK。IDE 在编辑器中打开文件并显示其 XML。你必须直接编辑 XML 向菜单资源中添加菜单项。

3. 在此处，使用每个菜单项的`showAction`属性来指定在有空间时将菜单项显示在应用栏上。在使用 Android Support Libraries 提供后兼容应用时，必须使用来自`app` XML 命名空间的`showAction`属性，而不是`android` XML 命名空间。编辑`<menu>`元素的标签以包含 app 命名空间。

4. 将图 5.11 中的第一个菜单项添加到 XML 文件中。该菜单项为`@id/color`，其`title`属性为`@string/menuitem_color`，其`icon`属性为`@drawable/ic_palette_24dp`，其`showAction`属性为`ifRoom`。`ifRoom`值表示，如果有可用空间，Android 应在应用栏上显示该菜单项；否则，菜单项将作为应用栏右侧溢出选项菜单中的文本项目。其他`showAction`值可以在此处找到：

```
xmlns:app="http://schemas.android.com/apk/res-auto"
```

# 第5章 Doodlez App

```xml
<item
  android:id="@id/color"
  android:title="@string/menitem_color"
  android:icon="@drawable/ic_palette_24dp"
  app:showAsAction="ifRoom"
</item>
```

图 5.11 | 表示菜单项的`<item>`元素。

5. 针对图 5.12 中的每个 ID 和标题重复步骤 3，以创建线条粗细、删除、保存和打印的菜单项，然后保存并关闭菜单文件。完成后的菜单 XML 如图 5.13 所示。

| Id | |
| @id/line_width | @string/menitem_line_width |
| @id/delete_drawing | @string/menitem_delete |
| @id/save | @string/menitem_save |
| @id/print | @string/menitem_print |

图 5.12 | MainActivityFragment 的额外项目。

```xml
<xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android"
  xmlns:app="http://schemas.android.com/apk/res-auto">
<item
  android:id="@id/color"
  android:title="@string/menitem_color"
  android:icon="@drawable/ic_palette_24dp"
  app:showAsAction="ifRoom"
</item>
<item
  android:id="@id/line_width"
  android:title="@string/menitem_line_width"
  android:icon="@drawable/ic_brush_24dp"
  app:showAsAction="ifRoom"
</item>
<item
  android:id="@id/delete_drawing"
  android:title="@string/menitem_delete"
  android:icon="@drawable/ic_delete_24dp"
  app:showAsAction="ifRoom"
</item>
```

图 5.13 | doodle_fragment_menu.xml。（2 部分中的第 I 部分）。

### 5.4.6 向 AndroidManifest.xml 添加权限

除了使用 Android 6.0 的新权限模型（应用会动态请求用户授予权限）外，每个应用必须在 AndroidManifest.xml 文件中指定其使用的任何权限。操作如下：

1. 展开项目文件夹并打开 AndroidManifest.xml。

2. 在`<manifest>`元素内部、`<application>`元素之前，添加

```xml
<uses-permission
android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
```

## 5.5 构建应用的 GUI

在本节中，你将创建应用的 GUI 以及用于应用对话框的类。

### 5.5.1 MainActivity 的 content_main.xml 布局

此 MainActivity 的 content_main.xml 布局仅包含 MainActivity-Fragment，它是当你创建项目时自动生成的。为了提高代码的可读性，我们更改了 fragment 的 id 属性：

1. 在布局编辑器的 Design 视图中打开 content_main.xml。

2. 在组件树（Component Tree）中选择 fragment，然后在属性窗口中将 Fragment 的 id 更改为`doodleFragment`并保存布局。

### 5.5.2 MainActivityFragment 的 fragment_main.xml 布局

MainActivityFragment 的 fragment_main.xml 布局只需要显示一个 DoodleView。该布局文件是在你创建项目时通过带有 LinearLayout 自动创建的。要将布局的根元素从 RelativeLayout 更改为 DoodleView，你必须先创建`Doodle`类（`View`的子类），这样你就可以在布局中放置自定义视图时选择它：

1. 展开 Project 窗口中的`java`文件夹。

2. 右键点击`com.de1.doodlez`节点，选择 New > Java Class。

3. 在出现的 New Class 对框中，在 Name 字段输入`DoodleView`，然后点击 OK。文件将自动在编辑器中打开。

4. 在`DoodleView.java`中，通过扩展`View`来表示`DoodleView`类是`View`的子类。如果 IDE 不允许导入`android.view.View`，将光标放在`View`之后。点击类定义上方出现的红色灯泡（💡）。

5. IDE 将显示错误，指示你尚未为新类定义构造函数。要修复此问题，将光标紧接`extends`之后。点击 DoodleView 定义上方出现的红色灯泡（💡），并选择 Create constructor matching super。在 Choose 对话框中，选择双参数构造函数，然后点击 OK。IDE 将将构造函数添加到类中。在第 5.8.3 节中，双参数构造函数是通过从布局中填充 DoodleView 时调用的——第二个参数指定了布局 XML 文件中的 View 属性。你可以在此处了解更多关于类构造函数的信息：

```
http://developer.android.com/reference/android/view/
View#View(android.content.Context)
```

6. 在布局编辑器中切换到 fragment_main.xml 并点击 Tab。

7. 将 RelativeLayout 更改为`com.de1.doodlez.DoodleView`。

8. 删除顶部、底部属性——doodleView 应该占据整个屏幕。

9. 在 Design 视图中，在组件树中选择`com.de1.doodlez.DoodleView`，将 id 设置为`doodleView`。

10. 保存并点击 content_main.xml。

### 5.5.3 ColorDialogFragment 的 fragment_color.xml 布局

ColorDialogFragment 的 fragment_color.xml 布局包含一个双列 GridLayout，用于选择和预览。在本节中，我们将展示如何添加`colorView`。

## 5.5 构建应用程序的 GUI

| GUI 组件 | 属性 | 值 |
| --- | --- | --- |
| blueTextView | 布局参数 layout:column layout:gravity layout:row 其他属性 text | 0 right, center_vertical 3 @string/label_blue |
| blueSeekBar | 布局参数 layout:column layout:gravity layout:row 其他属性 max | 1 fill_horizontal 3 255 |
| colorView | 布局参数 layout:height layout:column columnSpan layout:gravity | @dimen/color_view_height 2 fill_horizontal |

图 5.16 fragment_color.xml 中 GUI 组件的属性值。（2 部分中的第 2 部分）

### 向项目添加 ColorDialogFragment 类

要向项目添加类 ColorDialogFragment 类：

1. 在项目文件夹中，右键点击上级包 com.deitel.doodle2，并选择 New（新建） > Java Class（Java 类）以显示创建新类对话框。

2. 在 Name（名称）字段中，输入 ColorDialogFragment。

3. 点击 OK 创建该类。你将在第 5.9 节中创建此类的代码。

### 5.5.4 LineWidthDialogFragment 的 fragment_line_width.xml 布局

LineWidthDialogFragment 的 fragment_line_width.xml 布局包含一个 GridLayout，用于显示选择和预览新粗细线的 GUI。在本节中，你将创建 LineWidthFragment 的布局和 LineWidthDialogFragment 类。要添加 fragment_line_width.xml 布局：

1. 展开 Project 窗口中的 res/layout 节点。

2. 右键点击 layout 文件夹并选择 New > Layout resource file（布局资源文件）以显示资源文件对话框。

3. 在对话框的 File name（文件名）字段中，输入 fragment_line_width.xml

4. 在 Root element（根元素）字段中，输入 GridLayout，然后点击 OK。

5. 在 Component Tree 窗口中选择 GridLayout，将其 id 值更改为 WidthDialogGridLayout。

6. 使用布局编辑器的 Palette（调色板），将 ImageView 和 SeekBar 拖到 Component Tree 中，使 WidthDialogLayout 节点如图 5.17 所示。如图所示设置每个项的 id。

![](img/8c2e5496308864b3b07ddbd4401c4f77_222_0.png)

图 5.17 | fragment_line_width.xml 的组件视图。

7. 使用图 5.18 所示的值配置 GUI 组件。为维度 line_imageview_height 赋值 50dp。

8. 保存并关闭 fragment_line_width.xml。

| GUI 组件 | 属性 | 值 |
| --- | --- | --- |
| WidthDialogLayout | column Count | 1 |
| | orientation | vertical |
| | useDefaultMargins | true |
| | padding top | @dim/activity_vertical_margin |
| | padding bottom | @dim/activity_vertical_margin |
| | padding left | @dim/activity_horizontal_margin |
| | padding right | @dim/activity_horizontal_margin |
| ImageView | Layout Parameters | |
| | layoutheight | @dim/line_imageview_height |
| | layoutgravity | fill_horizontal |
| | contentDescription | @string/line_imageview_description |
| SeekBar | Layout Parameters | |
| | layoutgravity | fill_horizontal |
| | Other Properties | |
| | max | 50 |

图 5.18 | fragment_line_width.xml 中 GUI 组件的属性值。

### 向项目添加 LineWidthDialogFragment 类

要向项目添加 LineWidthDialogFragment 类：

1. 在项目的 java 文件夹中，右键点击上级包 com.deitel.doodle2，并选择 New > Java Class 以显示创建类对话框。

2. 在 Name（名称）字段中，输入 LineWidthDialogFragment。

3. 点击 OK 创建该类。

## 5.6 MainActivity

### 5.5.5 添加 EraseImageDialogFragment

EraseImageDialogFragment 不需要布局资源，因为它将显示一个包含文本的 AlertDialog。将 EraseImageDialogFragment 添加到项目：

1. 在项目的 java 文件夹中，右键点击上级包 com.deitel.doodle2 并选择 New > Java Class 显示创建类对话框。

2. 在 Name（名称）字段中，输入 EraseImageDialogFragment。

3. 点击 OK 创建该类。

## 5.6 MainActivity

该应用程序由六个类组成：

- MainActivity（下文讨论）——应用程序的主 Activity。

- MainActivityFragment（第 5.7 节）——管理 DoodleView 和加速度计事件。

- DoodleView（第 5.8 节）——提供绘制、保存和打印功能。

- ColorDialogFragment（第 5.9 节）——用户设置颜色时显示的 Fragment。

- LineWidthDialogFragment（第 5.10 节）——用户设置宽度时显示的 Fragment。



`EraseImageDialogFragment`（第 5.11 节）——用户选择擦或摇晃设备显示的 `Fragment`。

`MainActivity` 的 `onCreate` 方法（图 5.19）初始化 GUI（第 16 行）并配置其（第 17-18 行），然后使用第 4.6 节中的技术确定设备大小和 `MainActivity` 方向。如果应用程序运行在大设备上（第 26 行），将其设置为横屏（第 27-28 行）；否则将其设置为竖屏（第 30-31 行）。我们删除了 `MainActivity` 中自动生成的方法。

```java
// MainActivity.java
// MainActivity_layout
package com.deitel.doodle2;
import android.content.Activity;
import android.content.Configuration;
import android.os.Bundle;
import android.support.v7.app.AppCompatActivity;
import android.support.v7.widget
```

图 5.19 | `MainActivity` 类。（2 部分中的第 1 部分）

```java
// Chapter 5 Doodlely App
public class MainActivity extends AppCompatActivity {
    // 为 onCreate(savedInstanceState) 配置屏幕方向
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Toolbar toolbar = (Toolbar) findViewById(R.id.toolbar);
        setSupportActionBar(toolbar);

        // 确定屏幕大小
        int screenSize = getResources().getConfiguration().screenLayout &
            Configuration.SCREEN_SIZE_MASK;

        // 平板使用横屏；否则使用竖屏
        if (screenSize == Configuration.SCREEN_SIZE_LARGE) {
            setRequestedOrientation(ActivityInfo.LANDSCAPE);
        } else {
            setRequestedOrientation(ActivityInfo.PORTRAIT);
        }
    }
}
```

图 5.19 | `MainActivity` 类。（2 部分中的第 2 部分）

## 5.7 MainActivityFragment

`MainActivityFragment`（第 5.7.1-5.7.10 节）显示 `DoodleView`（第 5.8 节），管理应用栏上的菜单以及摇晃事件处理器。

### 5.7.1 package 语句、import 语句和字段

第 5.3 节讨论了 `MainActivityFragment` 中使用的新接口。我们在图 5.20 中强调了类和接口。`DoodleView`（第 24 行）代表绘制区域。加速度计信息以 `float` 值传递给应用程序。第 25-27 行的 `float` 值用于检测摇晃事件发生时设备加速度的变化（以便询问用户是否要清除绘制）。第 28 行定义了一个布尔变量 `shake`，默认值为 `false`，用于指定屏幕上同时显示对话框的情况——例如，如果显示颜色对话框且用户不小心摇晃了设备，不应显示擦图像对话框。第 31 行的常量用于过滤掉经常误认为是摇晃的意外移动——我们通过在不同类型的设备上摇晃应用程序，通过反复尝试得到了这个常量。第 35 行的常量用于标识请求保存用户绘制内容的权限。

```java
// MainActivityFragment.java
// 显示 DoodleView 的 Fragment
package com.deitel.doodle2;
import android.Manifest;
import android.app.AlertDialog;
import android.content.Context;
import android.content.DialogInterface;
import android.content.pm.PackageManager;
import android.hardware.Sensor;
import android.hardware.SensorEventListener;
import android.hardware.SensorManager;
import android.os.Bundle;
import android.support.v4.Fragment;
import android.view.LayoutInflater;
import android.view.Menu;
import android.view.MenuItem;
import android.view.View;
import android.view.ViewGroup;

public class MainActivityFragment extends Fragment {
    private DoodleView doodleView; // 处理触摸并绘制
    private float acceleration;
    private float currentAcceleration;
    private float lastAcceleration;
    private boolean dialogScreen = false;

    // 使用该值判断用户是否摇晃设备来清除
    private static final int ACCELERATION_THRESHOLD = 100000;

    // 用于标识外部存储的请求，
    // 相同的图像功能需要
    private static final int SAVE_IMAGE_PERMISSION_REQUEST_CODE = 1;
```

图 5.20 | `MainActivityFragment` 类语句、import 语句和字段。

### 5.7.2 重写方法 onCreate

`onCreate`（图 5.21）充加载 `MainActivityFragment` 的 GUI 并初始化实例变量。`Fragment` 可以在应用栏和选项菜单中放置项。为此，`Fragment` 必须调用其 `setOptionsMenu` 方法并参数 `true`。如果父 `Activity` 也有菜单项，`Activity` 和 `Fragment` 的项将放置在应用栏或选项菜单中（取决于设置）。

```java
// 当 Fragment 的视图需要创建时
@Override
public View onCreate(LayoutInflater inflater, ViewGroup container,
    Bundle savedInstanceState) {
```

图 5.21 | 重写 `Fragment` 方法 `onCreate`。（2 部分中的第 1 部分）

# 第 5 章 Doodly App

```java
super.onCreateView(inflater, container, savedInstanceState);
View view =
    inflater.inflate(R.layout.fragment_main, container, false);
setHasOptionsMenu(true); // 此片段（fragment）有要展示的菜单项
// 获取 DoodleView 的引用
doodleView = (DoodleView) findViewById(R.id.doodleView);

// 初始化加速度值
acceleration = 0.00f;
currentAcceleration = SensorManager.GRAVITY_EARTH;
lastAcceleration = SensorManager.GRAVITY_EARTH;
return view;
```

图 5.21 | 重写 `Fragment` 生命周期方法 `onCreateView`（第 2 部分，共 2 部分）

第 48 行获取 `DoodleView` 的引用，第 51-53 行初始化了存储加速度变化的变量，用于判断用户是否摇动了设备。我们最初将 `currentAcceleration` 和 `lastAcceleration` 设置为 `SensorManager.GRAVITY_EARTH`，这代表地球重力产生的加速度。`SensorManager` 还提供了太阳系中其他行星、月球以及其他有趣的数值，你可以在此处查看：

```
http://developer.android.com/reference/android/hardware/
SensorManager.html
```

### 5.7.3 方法 onResume 和启用加速度计监听

加速度计监听应仅在 `MainActivity` 可见时开启。出于这个原因，我们重写了 `Fragment` 生命周期方法 `onResume`（见图 5.22，第 58-62 行），该方法在 `Fragment` 位于屏幕上并供用户交互时被调用。在 `onResume` 中，我们调用了 `enableAccelerometerListening`。使用 `SensorManager` 来注册加速度计事件的监听器。

方法 `enableAccelerometerListening` 使用第一个 `Activity` 的 `getSystemService` 来获取系统的 `SensorManager` 服务（即 `Context.SENSOR_SERVICE`），这使得 App 能够与设备传感器进行交互。第 72-74 行通过 `SensorManager` 的 `registerListener` 方法来接收加速度计事件，该方法接收三个参数：

- `SensorEventListener` 用于响应事件（定义在第 5.7.5 节）。
- 一个 `Sensor` 对象，代表 App 想要接收的传感器类型——这是通过调用 `SensorManager` 的 `getDefaultSensor` 方法并传递一个 `Sensor` 类型常量（在本应用中为 `Sensor.TYPE_ACCELEROMETER`）触发的。
- Android 传递传感器事件的速率——`SENSOR_DELAY_NORMAL` 表示默认速率。可以使用更快的速率获取更精确的数据，但也会更消耗 CPU 和电量。

## 5.7 MainActivityFragment 类

```java
// 开始监听传感器事件
@Override
public void onResume() {
    super.onResume();
    enableAccelerometerListening(); // 监听摇晃事件
}
```

```java
// 启用加速度计事件监听
private void enableAccelerometerListening() {
    SensorManager sensorManager = (SensorManager) getActivity().getSystemService(Context.SENSOR_SERVICE);
    // 注册加速度计事件的监听器
    sensorManager.registerListener(sensorEventListener,
    sensorManager.getDefaultSensor(Sensor.TYPE_ACCELEROMETER),
    sensor.SENSOR_DELAY_NORMAL);
}
```

图 5.22 | 方法 `onPause` 和 `enableAccelerometerListening`。

### 5.7.4 onPause 和禁用加速度计监听

为了确保在 `MainActivityFragment` 不在屏幕上时停止监听加速度计，请重写 `Fragment` 生命周期方法 `onPause`（见图 5.23，第 78–82 行），该方法调用了方法 `disableAccelerometerListening`（第 85–94 行）。`AccelerometerListener` 使用 `SensorManager` 类的 `unregisterListener` 方法来停止监听加速度计。

```java
// 停止监听加速度计事件
@Override
public void onPause() {
    super.onPause();
    disableAccelerometerListening(); // 停止监听摇晃
}
```

```java
// 禁用加速度计事件监听
private void disableAccelerometerListening() {
    // 获取 SensorManager
    SensorManager sensorManager = (SensorManager) getActivity().getSystemService(Context.SENSOR_SERVICE);
    // 停止监听加速度计事件
    sensorManager.unregisterListener(sensorEventListener);
}
```

图 5.23 | 方法 `onPause` 和 `disableAccelerometerListening`。

### 5.7.5 处理事件的匿名内部类

图 5.24 是一个实现了 `SensorEventListener` 的匿名内部类，用于处理加速度事件。它重写了方法（第 100-123 行）来处理加速度事件。如果用户移动设备，`confirmErase`（第 5.7.6 节）会决定是否要擦除。由于在该应用中 `SensorEventListener` 并不显示对话框，因此我们直接在方法中进行处理。

```java
// 加速度计事件的处理器
private final SensorEventListener sensorEventListener =
    new SensorEventListener() {
        // 事件变化时触发
        @Override
        public void onChanged(SensorEvent event) {
            // 确保对话框未显示
            if (!dialogShowing) {
                float x = event.values[0];
                float y = event.values[1];
                float z = event.values[2];

                // 保存之前的加速度
                lastAcceleration = currentAcceleration;

                // 计算当前加速度
                currentAcceleration = x + y + z;

                // 计算加速度的变化
                acceleration = currentAcceleration - lastAcceleration;

                // 如果加速度超过设定的阈值
                if (acceleration > ACCELERATION_THRESHOLD) {
                    confirmErase();
                }
            }
        }
    };
```

图 5.24 | 实现 `SensorEventListener` 的匿名内部类。

`SensorEvent` 参数包含了发生的传感器变化信息。对于加速度事件，该参数包含三个元素（单位为 $m/s^2$），分别代表 $x$（左）、$y$（上）和 $z$（前/后）方向。关于 API 使用坐标系的描述和图表可见：

```
http://developer.android.com/reference/android/hardware/SensorEvent.html
```

第 105–107 行存储加速度值。第 110 行显示了最后的加速度。第 113 行将 $x$ 和 $z$ 加速度值的平方和并存储在 `acceleration` 中。然后，通过 `currentAcceleration` 和 `lastAcceleration` 值，我们计算出一个可以与 `ACCELERATION_THRESHOLD` 常量比较的值（`acceleration`）。如果该值大于常量，说明用户摇晃了设备。在这种情况下，我们调用了 `confirmErase` 方法。

# 194 第 5 章 涂鸦应用

- 对于 `R.id_line_width`，第 153–155 行创建并显示一个 `LineWidthDialogFragment`（第 5.10 节），允许用户选择新的线条宽度。
- 对于 `R.id_delete_drawing`，第 158 行的 `confirmErase` 方法（第 5.7.6 节）显示一个 `EraseDialogFragment`（第 5.11 节）并确认用户是否想要删除图像。
- 对于 `R.id_save`，第 161 行调用 `saveImage` 方法将绘画保存为图像并存储在用户的“照片”中，保存之前会先检查并在必要时请求写入外部存储的权限。



- 对于`R.id_print`，第 164 行调用`doodle().printImage()`方法，允许用户将图像保存为 PDF 或打印图像。

```java
// displays the fragment's menu items
@Override
public void onCreateOptionsMenu(Menu menu, MenuInflater inflater) {
    super.onCreateOptionsMenu(menu, inflater);
    inflater.inflate(R.doodle_fragment_menu, menu);
}

// handle choose from options menu
@Override
public boolean onMenuItemSelected(MenuItem item) {
    // switch on the MenuItem id
    switch (item.getItemId()) {
        case R.id.color:
            ColorDialog dialog = new ColorDialogFragment();
            dialog.show(getFragmentManager(), dialog);
            return true; // consume the menu event
        case R.id.line_width:
            LineWidthFragment dialog = new LineWidthFragment();
            dialog.show(getFragmentManager(), "line width dialog");
            return true; // consume the menu event
        case R.id.delete_drawing:
            confirmDelete(); // confirm before erasing image
            return true; // consume the menu event
        case R.id.save:
            saveImage(); // check permission and save current image
            return true; // consume the menu event
        case R.id.print:
            doodleView.printImage(); // print the current images
            return true; // consume the menu event
    }
    return super.onItemItemSelected(item);
}
```

图 5.26 | 重写的`Fragment`方法`onCreateOptionsMenu`和`onMenuItemSelected`。

## 5.7 `MainActivityFragment`类

### 5.7.8 方法`saveImage`

`saveImage`方法（图 5.27）在用户从选项菜单中选择“保存”选项时，由`onOptionsItemSelected`调用。`saveImage`方法实现了新 Android 6.0 模型中的部分功能，该模型在执行任务之前会检查应用是否已拥有所需的权限。如果没有，应用将在尝试执行该任务之前向用户请求权限。

第 176–178 行检查应用是否尚未获得写入外部存储的权限，以便保存图像。如果应用没有该权限（`permission.WRITE_EXTERNAL_STORAGE`），第 181–182 行使用内置的`showPermissionRationale`来确定是否应该显示关于应用为何需要此权限的解释。当解释为什么应用需要权限会有帮助时，该方法返回`true`——例如，创建一个带有该说明的对话框。当用户点击“确定”按钮时，第 195–197 行使用继承的`Fragment`方法`requestPermissions()`请求权限。如果不需要解释——例如，如果是应用第一次请求权限——则第 207–209 行会立即请求权限。

```java
172 // requests the permission needed for saving the image
173 // necessary or saves the image if the app already has permission
174 private void saveImage() {
175 // checks if the app does not have permission needed
176 // to save the image
177 if (getContext().checkSelfPermission(
178 Manifest.permission.WRITE_EXTERNAL_STORAGE) !=
179 PackageManager.PERMISSION_GRANTED) {
180 // shows an explanation of why permission is needed
181 if (showPermissionRequestRationale(
182 Manifest.permission.WRITE_EXTERNAL_STORAGE)) {
183 AlertDialog.Builder builder = new
184 AlertDialog.Builder(getActivity());
185 // set the Alert Dialog's message
186 builder.setMessage(R.string.permission_explanation);
187 // add an OK button to the dialog
188 builder.setPositiveButton(android.R.string.ok,
189 new DialogInterface.OnClickListener()(){
190 @Override
191 public void onClick(DialogInterface dialog, int which) {
192 // request permission
193 requestPermissions(new String[]{
194 Manifest.permission.WRITE_EXTERNAL_STORAGE,
195 SAVE_IMAGE_PERMISSION_REQUEST_CODE
196 }, 0);
197 }
198 });
199 });
202 // display the dialog
203 builder.create().show();
204 }
205 else {
206 // request_permission
207 requestPermissions(
208 new String[] {Manifest.permission.WRITE_EXTERNAL_STORAGE,
209 SAVE_IMAGE_PERMISSION_REQUEST_CODE});
210);
211 }
212 else { // if app already has permission to write to external storage
213 doodleView.saveImage(image); // save the image
214 }
215 }
```

图 5.27 | 方法`saveImage`（共 2 部分的第 1 部分）。

图 5.27 | 方法`saveImage`接收请求的权限数组，`SAVE_IMAGE_PERMISSION_REQUEST_CODE`用于标识此请求。

`SAVE_IMAGE_PERMISSION_REQUEST_CODE`用于标识此请求。

当`requestPermissions`被调用时，Android 显示一个允许用户拒绝或允许的对话框（图 5.28）。系统调用回调方法`onRequestResult`（第 5.7.9 节）来处理用户的响应。如果应用已获得该权限，第 213 行调用`DoodleView`的`saveImage`方法保存图像。

`img/8c2e54963088643b07bd4401f7`

图 5.28 | 允许用户拒绝或允许写入外部存储的对话框。

### 5.7.9 重写方法`onRequestResult`

`onRequestPermissionsResult`方法（图 5.29）接收所请求的权限字符串数组，并将其传递给第 224–249 行的`switch`语句。此应用只有一个权限请求，因此`switch`语句定义了一个对应`SAVE_IMAGE_PERMISSION_REQUEST_CODE`常量的分支。

```java
// Called by the system when the user enters or denies the
// permission for saving an image
@Override
public void onPermissionsResult(int requestCode,
String[] permissions, int[] grantResults) {
    // chooses appropriate action based on which
    switch (requestCode) {
        case SAVE_IMAGE_PERMISSION_REQUEST_CODE:
            if (grantResults[0] == PackageManager.PERMISSION_GRANTED)
                doodleView.saveImage(); // save the image
            break;
    }
}
```

图 5.29 | 重写的`onPermissionsResult`方法。

### 5.7.10 `getDoodleView`和`setDialogOnScreen`

`getDoodleView`和`setDialogOnScreen`方法被`DialogFragment`子类的方法调用。`getoodleView`返回`DoodleView`的引用，以便`DialogFragment`设置绘画颜色、线条宽或图像。`setDialogOnScreen`被`DialogFragment`子类的生命周期方法调用，用于指示对话框是否在屏幕上。

#### 软件工程观察 5.1

如果用户尝试保存图像并拒绝权限，当用户下次尝试保存时，权限对话框将包含“不再询问”复选框。如果用户勾选此项并拒绝权限，然后在方法中尝试保存，调用`onPermissionResult`的参数将为`PackageManager.DENIED`。生产应用应该处理这种情况，并告诉用户如何通过“设置”应用更改权限。

#### 软件工程观察 5.2

此应用彼此之间直接交互。我们为了简单起见选择了这种紧耦合的方式。通常情况下，父`Activity`管理应用的交互。为了向`Fragment`传递数据，`Activity`提供一个参数`Bundle`。每个`Fragment`定义一个接口回调方法，由`Activity`实现。当`Fragment`需要通知其父`Activity`状态更改时，`Fragment`会调用相应的回调方法。这些技术使得`Fragment`可以跨活动复用。我们将在第 9 章访问书籍中演示这些技术。

```java
// returns the DoodleView
public DoodleView getDoodleView() {
    return doodleView;
}
```

图 5.30 | `getDoodleView`和`setDialogOnScreen`（共 2 部分的第 1 部分）。

# 198 第 5 章 Doodlez App

```java
236
237 // 表示是否显示对话框
238 public void setDialogOnScreen(boolean visible) {
239 dialogOnScreen = visible;
240 }
241 }
```

图 5.30 | 方法`getDoodleView`和`setDialogOnScreen`（2 部分，共 2 部分）。

## 5.8 `DoodleView`类

`DoodleView`类（5.8.1–5.8.12）处理用户的触摸操作并绘制相应的线条。

### 5.8.1 `package`语句和`import`语句

图 5.31 列出了`DoodleView`的包语句和导入语句。这里高亮了新的类和接口。其中许多内容在第 5.3 节中讨论过，其余部分将在我们在整个`DoodleView`中使用它们时讨论。

```java
1 DoodleView.java
2 // Doodlz app 的主视图。
3 package com.deitel.doodlz;
4
5 import android.content.Context;
6 import android.graphics.Bitmap;
7 import android.graphics.Canvas;
8 import android.graphics.Color;
9 import android.graphics.Paint;
10 import android.graphics.Path;
11 import android.graphics.Point;
12 import android.provider.MediaStore;
13 import android.support.v4.print.PrintHelper;
14 import android.util.AttributeSet;
15 import android.doodleView.Gravity;
16 import android.view.MotionEvent;
17 import android.view.View;
18 import android.widget.Toast;
19
20 import java.util.HashMap;
21 import java.util.Map;
```

图 5.31 | `DoodleView`的包语句和导入语句。

### 5.8.2 静态变量和实例变量

`DoodleView`类的静态变量和实例变量（图 5.32）用于管理用户正在绘制的线条集合的数据并绘制这些线条。第 34 行创建了`pathMap`，它将每个手指 ID（称为指针）映射到当前绘制线条的对应的`Path`对象。第 35 行创建了`previousPointMap`，它维护每个手指的上一个点——随着每个手指的移动，我们从它的当前点到上一个点画一条线。我们将在`DoodleView`类中使用时讨论其他字段。

```java
// 绘图注释
public class DoodleView extends View {
    // 用于确定用户是否再次使用手指绘图
    private static final float TOUCH_TOLERANCE = 10;

    private Bitmap bitmap; // 用于显示或保存的绘图区域
    private Canvas bitmapCanvas; // 用于在 bitmap 上绘制
    private Paint paintScreen; // 用于将 bitmap 绘制到屏幕
    private final Paint paintLine; // 用于在 bitmap 上绘制线条

    // 当前绘制的 Paths 和这些 Paths 中的 Points 的映射
    private final Map<Integer, Path> pathMap = new HashMap<>();
    private final Map<Integer, Point> previousPointMap = new HashMap<>();
```

图 5.32 | `DoodleView`类和实例变量。

### 5.8.3 构造函数

构造函数（图 5.33）初始化了类的几个实例变量——`Maps`在图 5.32 的声明中已初始化。图 5.33 的第 40 行创建了`paintScreen`对象，用于在屏幕上显示用户的绘制内容，第 43 行创建了`Paint`对象，指定我们当前绘制的线条的设置。第 44–48 行设置了`Line`对象的设置。我们将`true`传递给`setAntiAlias`以启用抗锯齿，这会平滑线条的边缘。接下来，我们通过`setStyle`方法将`Paint`的样式设置为`Paint.Style.STROKE`。线条的样式可以是`FILL`、`FILL_AND_STROKE`，分别为线条和带边框的填充形状。默认选项是`Paint.Style.FILL`。我们使用`Paint`的`setStrokeWidth`方法设置线宽。我们还使用`setStrokeCap`用`Paint.Cap.ROUND`将线条端圆化。



```java
// DoodleView 构造函数初始化 DoodleView
public DoodleView(Context context, AttributeSet attrs) {
    super(context, attrs); // 将 context 传递给 View 的构造函数
    paintScreen = new Paint(); // 用于将 bitmap 绘制到屏幕

    // 设置绘制线条的初始设置
    paintLine = new Paint();
    paintLine.setAntiAlias(true); // 平滑绘制线条的边缘
    paintLine.setColor(Color.BLACK); // 默认颜色为黑色
    paintLine.setStyle(Paint.Style.STROKE); // 实线
    paintLine.setStrokeWidth(5); // 设置默认线宽
    paintLine.setStrokeCap(Paint.Cap.ROUND); // 圆角线条端
}
```

**图 5.33** DoodleView 构造函数。

## 5.8.4 重写方法 onChanged

`DoodleView` 的大小在它被膨胀并添加到 `MainActivity` 的视图层级之前是无法确定的；因此，我们无法在 `Create` 时确定绘图 `Bitmap` 的大小。我们重写了 `onChanged` 方法（图 5.34），该方法在 `DoodleView` 大小改变时被调用——例如当它被添加到 `Activity` 视图层级时。

# 202 第 5 章 Doodly App

```java
// 当 DoodleView 在屏幕上刷新时执行自定义绘图
@Override
protected void onDraw(Canvas canvas) {
    // 绘制正在绘制的位图
    canvas.drawBitmap(bitmap, 0, 0, paint);
    // 对于每个正在绘制的路径
    for (Integer key : pathMap.keySet()) {
        canvas.drawPath(pathMap.get(key), paintLine); // 绘制线条
    }
}
```

**图 5.36** | 重写的 `View` 方法 `onDraw`。

## 5.8.7 重写的 View 方法 onTouchEvent

当接收到触摸事件时，会调用 `onTouchEvent`（图 5.37）。Android 支持多点触控——即用多个手指同时触摸屏幕。为此，用户可以使用更多的手指触摸屏幕，或从屏幕上移开手指。每个触摸原因（称为指针 `pointer`）都有一个唯一的 ID，用于在整个触摸操作中标识它。我们将使用 ID 来定位代表当前绘制每条线的对应 `Path` 对象。这些 `Path` 存储在 `pathMap` 中。

```java
// handle touchEvent(MotionEvent event) {
@Override
public boolean onTouch(MotionEvent event) {
    int action = event.getActionMasked(); // 事件类型
    int actionIndex = event.getActionIndex(); // 指针（即手指）
    // 判断触摸是开始还是移动
    if (action == MotionEvent.ACTION_DOWN ||
        action == MotionEvent.ACTION_POINTER_DOWN) {
        touchStarted(event.getX(actionIndex), event.getY(actionIndex), event.getPointerId(actionIndex));
    } else if (action == MotionEvent.ACTION_UP ||
        action == MotionEvent.ACTION_POINTER_UP) {
        touchEnded(event.getPointerId(actionIndex));
    } else {
        touchMoved(event);
    }
    invalidate(); // 重新绘制
    return true;
}
```

**图 5.37** | 重写的 `View` 方法 `onTouchEvent`。

`MotionEvent` 的 `getActionMasked` 方法（第 102 行）返回一个表示 `MotionEvent` 类型的整数，你可以将其结合 `MotionEvent` 类中的常量，判断触摸是开始、移动还是结束，或者是否发生了多点触。

# 203 5.8 DoodleView 类

如何处理每个事件。`MotionEvent` 的 `getActionIndex` 方法（第 103 行）返回一个唯一的 ID——它仅仅是该手指引起事件的索引。该索引不是手指的信息，手指信息位于此 `MotionEvent` 对象中。为了获取在用户从屏幕上移开手指后仍跨越 `MotionEvent` 持续存在的手指 ID，我们使用 `MotionEvent` 的 `getPointerID` 方法（第 109 行和 113 行），并将手指索引作为参数。

如果动作是 `MotionEvent.ACTION_DOWN` 或 `MotionEvent.ACTION_POINTER_DOWN`（第 106-107 行），则用户用新手指触摸屏幕。第一个触摸屏幕的手指产生 `MotionEvent.ACTION_DOWN` 事件，所有其他手指产生 `MotionEvent.ACTION_POINTER_DOWN` 事件。对于这些情况，我们调用 `touchStarted`（图 5.38）来存储触摸的初始坐标。如果动作是 `MotionEvent.ACTION_UP` 或 `MotionEvent.ACTION_POINTER_UP`，用户从屏幕上移开了手指，我们可以调用 `touchEnded`（图 5.40）将完成的 `Path` 绘制到位图中，以便我们拥有 `Path` 的永久记录。对于所有其他触摸事件，我们调用 `touchMoved`（图 5.39）来绘制线条。事件处理后，第 119 行（见图 5.37）调用继承的方法 `invalidate` 来重新绘制屏幕，第 120 行返回 `true` 表示该事件已处理。

## 5.8.8 touchStarted 方法

`touchStarted` 方法（图 5.38）在手指首次触摸屏幕时被调用。坐标和 ID 作为参数提供。如果给定的 ID 已经存在一个 `Path`（第 129 行），我们调用 `Path.reset` 方法来清除任何现有点，以便我们可以复用该 `Path` 绘制新的笔画。否则，我们创建一个新的 `Path`，将其添加到 `touchMap` 中，然后向 `PointMap` 中添加一个新的 `Point`。第 142-144 行调用 `moveTo` 来设置 `Path` 坐标并指定新点的 x 和 y 值。

```java
// 当用户触摸屏幕时调用
private void touchStarted(float x, float y, int lineID) {
    Path path; // 用于存储给定 touch id 的路径
    Point point; // path 中的最后一个点
    // 如果 lineID 已经存在一个路径
    if (touchMap.containsKey(lineID)) {
        path = touchMap.get(lineID); // 获取 Path
        path.reset(); // 重置 Path，因为新的触摸已开始
        point = previousPointMap.get(lineID); // 获取 Path 的最后一个点
    } else {
        path = new Path(lineID); // 将 Path 添加到 Map
        point = new Point(); // 创建新 Point
        previousPointMap.put(lineID, point); // 将 Point添加到 Map
    }
    // 移动到触摸坐标
    moveTo(x, y);
}
```

**图 5.38** | DoodleView 类的 `touchStarted` 方法。（部分 I，共 2 部分）

# 204 第 5 章 Doodly App

```java
143 point.x = (int) x;
144 point.y = (int) y;
145 }
```

**图 5.38** | DoodleView 类的 `touchStarted` 方法。（部分 II，共 2 部分）

## 5.8.9 touchMoved 方法

`touchMoved` 方法（图 5.39）在手指移动时被调用。`MotionEvent` 的 `getActionMasked` 方法（第 102 行）返回一个表示 `MotionEvent` 类型的整数，你可以将其结合 `MotionEvent` 类中的常量，判断触摸是开始、移动还是结束，或者是否发生了多点触。`MotionEvent` 的 `getActionIndex` 方法（第 103 行）返回一个唯一的 ID——它仅仅是该手指引起事件的索引。该索引不是手指的信息，信息位于此 `MotionEvent` 对象中。为了获取在用户从屏幕上移开手指后仍跨越 `MotionEvent` 持续存在的手指 ID，我们使用 `MotionEvent` 的 `getPointerID` 方法（第 109 行和 113 行），并将手指索引作为参数。`MotionEvent` 的 `getPointerCount` 方法（第 150 行）返回触摸的数量。如果动作是 `MotionEvent.ACTION_DOWN` 或 `MotionEvent.ACTION_POINTER_DOWN`（第 106-107 行），则用户用新手指触摸屏幕。第一个触摸屏幕的手指产生 `MotionEvent.ACTION_DOWN` 事件，所有其他手指产生 `MotionEvent.ACTION_POINTER_DOWN` 事件。对于这些情况，我们调用 `touchStarted`（图 5.38）来存储触摸的初始坐标。如果动作是 `MotionEvent.ACTION_UP` 或 `MotionEvent.ACTION_POINTER_UP`，用户从屏幕上移开了手指，我们可以调用 `touchEnded`（图 5.40）将完成的 `Path` 绘制到位图中，以便我们拥有 `Path` 的永久记录。对于所有其他触摸事件，我们调用 `touchMoved`（图 5.39）来绘制线条。事件处理后，第 119 行（见图 5.37）调用继承的方法 `invalidate` 来重新绘制屏幕，第 120 行返回 `true` 表示该事件已处理。

如何处理每个事件。

```java
// 当用户拖动屏幕时
private void touchMoved(MotionEvent event) {
    // 对于 MotionEvent 中的每个手指
    for (int i = 0; i < event.getPointerCount(); i++) {
        // 获取指针 ID 和索引
        int pointerID = event.getPointerID(i);
        int pointerIndex = event.getActionIndex();
        // 获取新的坐标
        float x = event.getX(pointerIndex);
        float y = event.getY(pointerIndex);

        // 如果与指针 ID 关联的路径
        if (touchMap.containsKey(pointerID)) {
            // 获取路径和之前的点
            Path path = touchMap.get(pointerID);
            Point point = previousPointMap.get(pointerID);

            // 计算用户从上次移动的距离
            float deltaX = Math.abs(x - point.x);
            float deltaY = Math.abs(y - point.y);

            // 如果距离足够大则更新
            if (deltaX >= TOUCH_TERANCE || deltaY >= TOUCH_TERANCE) {
                // 将路径移动到新位置
                path.quadTo(point.x, point.y, (x + point.x) / 2, (y + point.y) / 2);

                // 存储新坐标
                point.x = (int) x;
                point.y = (int) y;
            }
        }
    }
}
```

**图 5.39** | DoodleView 类的 `touchMoved` 方法。（部分 I，共 2 部分）

## 5.8.10 touchEnded

`touchEnded` 方法（5.40）在手指从屏幕上抬起时被调用。该方法接收刚刚触摸的手指 ID（3D）作为参数。第 187 行调用 `bitmapCanvas` 的 `drawPath` 方法将 `Path` 绘制到 `Bitmap` 对象上，由于 `Path` 不会删除屏幕上对应的线条，因为这些线条已经绘制到了显示在屏幕上的位图中。线条正在绘制在该位图之上。

```java
// 当用户完成触摸时
private void touchEnded(int lineID) {
    Path path = pathMap.get(lineID);
    bitmapCanvas.drawPath(path, paint); // 绘制到 bitmapCanvas
    path.reset(); // 重置 Path
}
```

**图 5.40** | DoodleView 类的 `touchEnded`。

## 5.8.11 saveImage 方法

`saveImage` 方法（5.41）保存当前绘制。第 194 行为图像创建一个文件名，然后第 197–99 行通过调用 `MediaStore.Images.Media.insertImage` 方法将图像存储到手机的照片应用中。该方法接收四个参数：

- 方法用于定位设备上存储位置的 `ContentResolver`
- 要存储的位图
- 图像的名称
- 图像的描述

方法 `insertImage` 返回表示图像在设备上位置的字符串，如果图像已保存则返回 `null`。第 201–217 行检查图像是否已保存并显示相应的 `Toast`。

```java
// save the current image to the Gallery
public void saveImage() {
    // 使用 "Doodlez" 加上当前时间作为图像名称
    final String name = "Doodlez" + System.currentTimeMillis() + ".jpg";

    // 将图像插入到设备上
    String location = MediaStore.Image.insertImage(
        getContext().getContentResolver(), bitmap, name,
        "Doodlez Drawing");
    if (location != null) {
        // 显示一条消息，表示图像已保存
        Toast message = Toast.makeText(getContext(),
            R.string.message_saved, Toast.LENGTH_SHORT);
        message.setGravity(Gravity.CENTER, message.getXOffset() / 2,
            message.getOffsetY() / 2);
    } else {
        // 显示一条消息，表示保存发生错误
        Toast message = Toast.makeText(getContext(),
            R.string.message_error_saving, Toast.LENGTH_SHORT);
        message.setGravity(Gravity.CENTER, message.getXOffset() / 2,
            message.getOffsetY() / 2);
    }
}
```

**图 5.41** | Doodle saveImage。

## 5.8.12 方法 printImage

（请注意，原始文本中“printImage”部分内容未提供，因此此处无法进行进一步排版。）



方法 `printImage`（图 5.42）使用 Android 库的 `PrintHelper` 来打印当前绘图——这仅在运行 Android 4.4 或更高版本的设备上可用。第 222 行释放设备是否支持打印。因此，第 224 行创建一个 `PrintHelper` 对象。接下来，第 227 行指定了缩放模式——`SCALE_FIT` 使图像适应纸张的可打印区域。还有缩放模式 `SCALE_MODE_FILL`，它会导致图像填充整个纸张，裁剪掉部分图形。最后，第 228 行调用 `printBitmap` 并传递了作业名称（打印机用于识别作业）和包含要打印图像的 `Bitmap` 作为参数。这将显示 Android 的打印对话框，允许用户选择将图像保存为设备上的 PDF 还是打印到可用的打印机。

## 5.9 `ColorDialogFragment` 类

```java
// print the current image
public void printImage() {
    if (PrintHelper.systemSupportsPrint()) {
        // 使用 Android Support库的 PrintHelper 打印图像
        PrintHelper printHelper = new PrintHelper(getContext());

        // 图像适应页面边界并打印图像
        printHelper.setScale(PrintHelper.SCALE_MODE_FIT);
        printHelper.printBitmap(decodeBitmap("Doodle Image", bitmap));
    }
    else {
        // 显示消息表示系统不允许打印
        Toast.makeText(getContext(),
            "message_error_printing", Toast.LENGTH_SHORT);
        message.setGravity(Gravity.CENTER, message.getXOffset(0) / 2);
        message.show();
    }
}
```

图 54 Doodleview `printImage`。

`ColorDialogFragment`（图 5.43–5.47）扩展了 `DialogFragment` 以创建一个用于设置绘图颜色的 `AlertDialog`。其实例变量（第 18–23 行）用于引用选择新颜色的 GUI 控件、显示其预览，并将颜色存储为表示颜色 ARGB 值的 32 位 `int` 类型。

```java
// ColorDialogFragment.java
// 允许用户在 DoodleView 上设置绘图颜色
package com.deitel.doodle;
import android.app.Activity;
import android.app.AlertDialog;
import android.app.Dialog;
import android.content.DialogInterface;
import android.graphics.Color;
import android.os.Bundle;
import android.support.v4.app.DialogFragment;
import android.widget.View;
import android.widget.SeekBar;
import android.widget.SeekBar.OnSeekChangeListener;

// 用于 Seek 选择器的类：颜色对话框
public class ColorDialogFragment extends DialogFragment {
    private SeekBar alphaSeekBar;
    private SeekBar redSeekBar;
```

图 5.43 `ColorDialogFragment` 的包语句、import 语句和实例变量。（2 部分中的第 1 部分。）

```java
20 private SeekBar greenSeekBar;
21 private SeekBar blueSeekBar;
22 private View colorView;
23 private int color;
```

**图 5.43** | `DialogFragment` 的包语句、import 语句和实例变量。（第 2 部分）

### 5.9.1 重写的 `DialogFragment` 方法 `onCreateDialog`

方法 `onCreateDialog`（图 5.44）填充由 `fragment_color` xml 定义的自定义 `View`（第 31–32 行），该 xml 包含选择所需的 GUI，然后通过调用 `AlertBuilder.setView`（第 33 行）将该 `View` 附加到 `AlertDialog`。第 39–47 行获取对话框的 `SeekBars` 和 `colorView` 的引用。接下来，第 50–53 行将 `onChangedChangeListener`（图 5.47）注册为 `SeekBars` 事件的监听器。

```java
25 // 创建一个 AlertDialog 并返回它
26 @Override
27 public Dialog onCreateDialog(Bundle bundle) {
28 // 创建对话框
29 AlertDialog.Builder builder =
30 new AlertDialog.Builder(getActivity());
31 View colorView = getActivity().getLayoutInflater().inflate(
32 R.layout.fragment_color, null);
33 builder.setView(colorView); // 将 View 添加到对话框
34
35 设置对话框标题
36 builder.setTitle(R.string.title_color);
37
38 获取 SeekBars 并设置它们的监听器
39 alphaSeek = (SeekBar) colorView.findViewById(
40 R.id.alphaSeek);
41 redSeek = (SeekBar) colorView.findViewById(
42 R.id.redSeek);
43 greenSeek = (SeekBar) colorView.findViewById(
44 R.id.greenSeek);
45 blueSeek = (SeekBar) colorView.findViewById(
46 R.id.blueSeek);
47 color = colorView.findViewById(R.id.colorView);
48
49 // 注册 监听器
50 alphaSeek.setOnChangeListener(ChangedChangeListener);
51 redSeek.setOnChangeListener(ChangedChangeListener);
52 greenSeek.setOnChangeListener(ChangedChangeListener);
53 blueSeek.setOnChangeListener(ChangedChangeListener);
54
55 使用当前绘图颜色获取 SeekBar 值
56 final DoodleView doodleView = getFragment().getoodleView();
57 color = doodleView.getDrawingColor();
58
59 alphaSeekBar.setProgress(Color.alpha(color));
60 redSeekBar.setProgress(Color.red(color));
61 greenSeekBar.setProgress(Color.green(color));
62 blueSeekBar.setProgress(Color.blue(color));
63
64 添加颜色按钮
65 builder.setPositiveButton(R.string.button_color,
66     new DialogInterface.OnClickListener() {
67             public void onClick(DialogInterface dialog, int id) {
68                 doodleView.setDrawingColor(color);
69             }
70     });
71
72     return builder.create(); // 返回对话框
73 }
```

**图 5.44** | 重写的 `DialogFragment` 方法 `onCreateDialog`。（第 2 部分）

第 56 行（图 54）调用 `getDoodleFragment`（图 55）以获取对 `DoodleFragment` 的引用，然后调用 `MainActivity` 的 `getD` 方法获取 `DoodleView`。

### 5.9.2 方法 `getDoodleFragment`

方法 `getDoodleFragment`（图 545）使用 `FragmentManager` 来引用 `DoodleFragment`。

```java
75 // 获取 MainActivity 的引用
76 private MainActivity getDoodleFragment() {
77     return ((MainActivity) getFragmentManager()).findFragmentById(
78     R.id.doodleFragment);
79 }
```

图 54 | 方法 `getDoodleFragment`。

### 5.9.3 重写的生命周期方法 `onAttach` 和 `onDetach`

当 `ColorDialogFragment` 被添加到父 `Activity` 中时，方法 `onAttach`（图 5.46，第 82–89 行）被调用。第 85 行获取 `MainActivity` 的引用。如果该引用不为空，第 88 行调用 `MainActivity` 的 `setDialogOnScreen` 来指示选择对话框未显示。当 `ColorFragment` 从父 `Activity` 移除时，方法 `onDetach`（第 92–99 行）是第 210 章 第 5 章 Doodly App 被调用。第 98 行调用 `MainActivityFragment` 的 `setDialogOnScreen` 方法，表示选择颜色对话框不再显示在屏幕上。

```java
// 正在显示的 MainActivityFragment
@Override
public void onAttach(Activity activity) {
    super.onAttach(activity);
    MainActivityFragment fragment = getDoodleFragment();
    
    if (fragment != null) {
        fragment.setDialogOnScreen(true);
    }
}

// 不再显示的的 MainActivityFragment
@Override
public void onDetach() {
    super.onDetach();
    MainActivityFragment fragment = getDoodleFragment();

    if (fragment != null) {
        fragment.setDialogOnScreen(false);
    }
}
```

图 5.46 - 在 `onDetach` 上重写的生命周期方法。

## 5.9.4 响应 Alpha、红、绿、蓝 `SeekBars` 事件的匿名内部类

图 5.47 定义了一个匿名内部类，它实现了 `OnChangeListener`，用于响应用户在“选择颜色”对话框中更新 `SeekBars` 时的事件。这在图 5.44（第 50-53 行）中被注册为 `SeekBar` 的处理器。当 `SeekBar` 的滑块位置改变时，会调用 `onProgress` 方法（图 5.47，第 105-114 行）。如果用户移动 `SeekBar` 的滑块（第 109 行），第 110-112 行将存储新颜色。`Color` 的静态方法 `arg` 将 `SeekBar` 的值组合成颜色，并作为 `int` 类型返回相应的颜色。然后我们使用 `View` 的 `setColor` 方法，用与 `SeekBars` 当前状态匹配的颜色来更新 `currentColor`。

```java
// 颜色对话框中 SeekBars 的 OnChangeListener
private final OnSeekBarChangeListener onChangedListener = 
    new OnSeekBarChangeListener() {
        // 显示更新后的颜色
        public void onProgressChanged(SeekBar seekbar, int progress, 
            boolean fromUser) {
        }
    }
}
```

图 5.47 - 实现 `OnChangeListener` 以响应 alpha、红、绿、蓝 `SeekBars` 事件的匿名内部类。（2 部分中的第 1 部分）。

## 5.10 `LineWidthDialogFragment` 类

```java
if (fromUser) // 用户（而非程序）更改了 SeekBar 进度
color = Color.argb(alphaSeekBar.getProgress(),
redSeekBar.getProgress(), greenSeekBar.getProgress(),
blueSeekBar.getProgress());
colorView.setBackgroundColor(color);
}
```

```java
@Override
public void onStartTrackingTouch(SeekBar seekBar) { // required }
@Override
public void onStopTrackingTouch(SeekBar seekBar) { // required }
```

**图 5.47** 实现 `OnSeekChangeListener` 接口以响应 alpha、红、绿、蓝 `SeekBars` 事件的匿名类。（2 部分中的第 2 部分）。

`LineWidthDialogFragment` 类（图 5.48）继承自 `DialogFragment`，用于创建一个设置线条宽的警报对话框。该类与 `ColorDialogFragment` 类似，因此我们只讨论关键区别。唯一的实例变量是一个 `ImageView`（第 21 行），我们在其中绘制一条具有当前线宽的线。

```java
// LineWidthDialogFragment.java
// 允许用户在 DoodleView 上绘制绘画颜色
package com.detail1.doodle1;

import android.app.Activity;
import android.app.AlertDialog;
import android.app.Dialog;
import android.content.DialogInterface;
import android.graphics.Bitmap;
import android.graphics.Canvas;
import android.graphics.Paint;
import android.os.Bundle;
import android.support.v4.app.DialogFragment;
import android.view.View;
import android.widget.ImageView;
import android.widget.SeekBar;
import android.widget.SeekBar.OnSeekChangeListener;

// 用于选择线条宽对话框的类
public class LineWidthDialogFragment extends DialogFragment {
    private ImageView ImageViewImageView;
```

**图 5.48** | `LineWidthDialogFragment` 类。（3 部分中的第 1 部分）。



```java
// 创建 AlertDialog 并返回它
@Override
public void onCreate(Bundle bundle) {
    // 创建对话框
    AlertDialog.Builder builder = new AlertDialog.Builder(getActivity());
    View lineDialogView =
        getActivity().getLayoutInflater().inflate(
        R.layout.line_width, null, null);
    builder.setView(lineDialogView); // 将 gui 添加到对话框
    // 设置 AlertDialog 的消息
    builder.setTitle(R.string.title_line_width);
    // 获取 ImageView
    ImageView widthSeekbar = (ImageView) lineDialogView.findViewById(
        R.id.widthSeekbar);
    // 配置 seekbar
    Final DoodleFragment doodleView = getDoodleFragment().getDoodleView();
    Final SeekBar widthSeekbar = lineDialogView.findViewById(R.id.widthSeekbar);
    widthSeekbar.setOnSeekChangeListener((seekbar, widthChanged) -> {
        doodleView.setLineWidth(widthChanged);
    });
    // 设置线条宽
    builder.setPositiveButton(R.string.line_width,
        new DialogInterface.OnClickListener() {
            public void onClick(DialogInterface dialog, int id) {
                doodleView.setLineWidth(seekbar.getProgress());
            }
        });
    return builder.create(); // 返回对话框
}

// 获取 DoodleFragment 的引用
private DoodleFragment getDoodleFragment() {
    return (DoodleFragment) getFragmentManager().findFragment(
        R.id.doodleFragment);
}

// 通知 MainActivityFragment 正在显示
@Override
public void onAttach(Activity activity) {
    super.onAttach(activity);
    MainActivityFragment fragment = getDoodleFragment();
    if (fragment != null) {
        fragment.setDialogOnScreen(true);
    }
}
```

图 5.48 | `LineWidthDialogFragment`。（3 部分中的第 2 部分）。

```java
// 通知 MainActivityFragment 不再显示
@Override
public void onDetach() {
    super.onDetach();
    MainActivityFragment fragment = getDoodleFragment();
    if (fragment != null) {
        fragment.setDialogOnScreen(false);
    }
}
```

```java
// 用于 Erase Image 对话框的类
public class EraseImageDialogFragment extends DialogFragment {
    // 创建 AlertDialog 并返回它
    @Override
    public void onCreate(Bundle bundle) {
        AlertDialog.Builder builder =
            new AlertDialog.Builder(getActivity());
        // 设置 AlertDialog 的消息
        builder.setMessage(R.string.message_erase);
        // 添加擦除按钮
        builder.setPositiveButton(R.string.button_erase, new DialogInterface.OnClickListener() {
            public void onClick(DialogInterface interface, int id) {
                getFragment().getView().clear(); // 清除图像
            }
        });
        // 添加取消按钮
        builder.setNegativeButton(android.R.string.cancel, null);
        return builder.create(); // 返回对话框
    }

    // 获取 MainActivity 的引用
    private MainActivityFragment fragment = getFragment();
    return (MainActivityFragment) getActivityManager().findFragmentById(R.id.dialogfragment);
}

// 对话框当前显示的 MainActivity MainActivityFragment
    @Override
    public void onAttach(Activity activity) {
        super.onAttach(activity);
        MainActivityFragment fragment = getFragment();
        if (fragment != null) {
            fragment.dialogOnScreen(true);
        }
    }

    // 对话框不再显示的 MainActivity MainActivityFragment
    @Override
    public void onDetach() {
        super.onDetach();
        MainActivityFragment fragment = getFragment();
        if (fragment != null) {
            fragment.dialogOnScreen(false);
        }
    }
}
```

图 5.49 | 类 `EraseImageDialogFragment`（第 2 部分，共 2）。

## 5.12 总结

在本章中，你构建了 Doodly 应用，该应用允许用户通过在屏幕上拖动一个或多个手指来绘画。你使用 Android-SensorManager 实现了摇一摇擦除功能，通过创建一个响应加速度计事件的 `SensorEventListener` 来该功能，并学习了 Android 支持许多其他传感器。你创建了 `DialogFragment` 的子类，用于在 `AlertDialog` 中显示自定义视图。你还重载了 Fragment 的生命周期方法 `onCreate` 和 `onDestroy`，这些方法分别在 Fragment 附加或脱离 Activity 时被调用。

我们展示了如何将 `Canvas` 与 `Bitmap` 关联起来，这样 `Canvas` 就可以绘制到 `Bitmap` 中。我们演示了如何处理多点触控，即多个手指同时在屏幕上拖动。你存储了每个独立手指的信息，并通过重写 `onTouchEvent` 方法来处理触摸事件，该方法返回一个包含事件类型和产生事件的指针（手指）ID 的 `MotionEvent`。你使用这些 ID 来区分不同的手指，并向相应的 `Paths`（路径）中添加信息。

你使用了 `ContentResolver` 和 `MediaStore.Images.insertImage` 方法将图像保存到设备上。为了启用此功能，你使用了 Android 6.0 的权限机制请求用户授予保存到外部存储的权限。

我们展示了如何使用打印框架允许用户打印他们的画。你使用了 Android Support Library 中的 `Printer` 类来打印 `Bitmap`。`PrintHelper` 显示了一个用于选择打印机或将图像保存为 PDF 文档的用户界面。为了将 Android Support Library 引入应用中，你使用 Gradle 标明了应用对该库的依赖关系。

在第 6 章中，你将创建一个具有多线程和逐帧动画的大炮游戏（Cannon Game）。你将处理触摸手势来发射大炮。你还将学习如何创建一个游戏循环，尽可能快地更新显示，以创建流畅的动画，并让游戏无论任何设备的处理器速度如何都感觉以相同的速度运行。

# 6

# 大炮游戏应用 (Cannon Game App)

手动逐帧动画、图形、声音、线程、`SurfaceView` 和 `SurfaceHolder`、沉浸式模式与全屏

![](img/8c2e5496308864b3b07ddbd4401c4f77_253_0.png)

## 目标

在本章中你将：

- 创建一个易于编码且有趣的简单游戏应用。

- 创建一个自定义的 `SurfaceView` 子类，用于从单独执行线程显示游戏图形。

- 使用 `Paints` 和 `Canvas` 绘制图形。

- 重写 View 的 `onTouchEvent` 方法，在用户触摸屏幕时发射大炮。

- 执行简单的碰撞检测。

- 使用 `SoundPool` 和 `AudioManager` 为你的应用添加声音。

- 重写 Fragment 生命周期周期方法 `onDestroy`。

- 使用沉浸式模式让游戏占据整个屏幕，但仍允许用户访问系统栏。

## 第 6 章 大炮游戏应用

## 大纲

- 6.1 引言

- 6.2 测试驱动大炮游戏应用

- 6.3 技术概述

  - 6.3.1 使用资源 `res/raw` 方法

  - 6.3.2 Activity 和帧生命周期

  - 6.3.3 重写 View 方法 `onTouch`

  - 6.3.4 使用 `Soundpool` 和线程添加声音；`SurfaceView`

  - 6.3.5 使用 `SurfaceView` 和 `SurfaceHolder` 进行逐帧动画

  - 6.3.6 简单碰撞检测

  - 6.3.7 沉浸式模式

- 6.4 构建 GUI 和资源文件

  - 6.4.1 创建项目

  - 6.4.2 调整主题以移除应用栏和标题

  - 6.4.3 `strings.xml`

  - 6.4 颜色 (Color)

  - 6.4 将声音添加到应用中

- 6.5 本章概述

- 6.6 `MainActivity`

- 6.7 `MainActivityFragment`

- 6.8 大炮

  - 6.8.1 使用资源

  - 6.8.2 重写

  - 6.8.3 添加声音

- 6.9 阻塞器

- 6.10 目标

- 6.11 大炮

  - 6.11.1 使用资源

  - 6.11.2 重写

  - 6.11.3 添加声音

- 6.12 大炮

  - 6.12.1 使用资源

  - 6.12.2 重写

- 6.13 大炮

  - 6.13.1 使用资源

  - 6.13.2 重写

  - 6.13.3 添加声音

  - 6.13.4 重写

  - 6.13.5 使用线程

  - 6.13.6 重写

## 6.1 引言

大炮游戏允许你在时间限制内发射目标（图 6.1）。游戏由各种视觉组件组成——一个你控制的大炮，以及一个防御目标的阻塞器。

> 我们感谢面向对象编程书籍作者 Huges Bersini 分享了他对原始应用的重构建议。我们以此为灵感创建了自己的版本

通过触摸屏幕来发射大炮——大炮指向触摸点并向该方向发射炮弹。

![](img/8c2e5496308864b3b07ddbd4401c4f77_255_0.png)

图 6.1 完成的大炮游戏应用。

每当你摧毁一个目标，剩余时间就会增加三秒奖金；每当你击中阻塞器时，剩余时间就会扣除两秒惩罚。在时间耗尽之前摧毁所有目标区域——如果计时器归零，你就输了。游戏结束时，应用会显示一个对话框，告知你是胜利还是失败，并显示发射次数和经过的时间（图 6.2）。

a) 用户摧毁所有目标后显示的对话框

b) 游戏在用户摧毁所有目标前结束时显示的对话框

你赢了！

发射次数：18

总时长：21.7 秒

重置游戏

重置游戏

你输了！

发射次数：5

总时长：7.0 秒

图 6.2 大炮游戏应用显示胜利和失败的对话框。

当你发射时，游戏会播放发射声。当炮弹击中目标时，会播放玻璃破碎声，目标消失。当炮弹击中阻塞器时，会播放击中声，炮弹会反弹。每个目标和阻塞器以不同的速度垂直移动，并在碰到顶部或底部时改变方向。

[注意：Android 模拟器在某些计算机上运行缓慢。为了获得最佳体验，请在 Android 设备上测试此应用。在缓慢的模拟器上，炮弹有时会穿过阻塞器或目标。]

220 第 6 章 大炮游戏 App

## 6.2 测试大炮游戏 App

### 打开并运行应用

打开 Android Studio，并从书籍的示例文件夹中打开大炮游戏（Cannon Game）应用，然后在 AVD 或设备上运行该应用。这将构建项目并运行应用。

### 玩游戏

点击屏幕来对准并发射大炮。如果屏幕上没有其他大炮，你就可以发射炮弹。如果你在 AVD 上运行，则使用鼠标进行对准和发射。尽可能地摧毁所有目标——如果计时结束或你摧毁了所有目标，游戏将结束。

## 6.3 技术概述

本节将按照它们在章节中出现的顺序，介绍我们在大炮游戏 App 中使用的这些新技术。

### 6.3.1 使用资源文件夹 `res/raw`

媒体文件（如大炮游戏 App 中使用的文件）放置在应用的源文件夹 `res/raw` 中。第 6.4.5 节详细说明了如何创建此文件夹。你会将应用的音频文件拷贝到其中。

### 6.3.2 Activity 和 Fragment 生命周期方法

我们在第 5.3.1 节中介绍了 Activity 和 Fragment 生命周期方法。这里使用了生命周期方法 `onDestroy`。当一个 activity 关闭时，会调用其 `onDestroy` 方法，该方法随后调用所有 Fragment 的 `onDestroy` 方法。我们在 `MainActivityFragment` 中使用此方法来释放 `CanvasView` 的资源。

![](img/8c2e5496308864b3b07ddbd4401c4f77_256_0.png)

> 错误预防提示 6.1

> `onDestroy` 方法不保证会被调用，因此它应该只用于释放资源，而不是用于保存数据。Android 文档建议你在 `onPause` 或 `onSaveInstanceState` 中保存数据。

### 6.3.3 重写 View 的 `onTouchEvent` 方法

用户通过触摸屏幕与此应用进行交互。触摸会将大炮对齐到屏幕上的触摸点，然后发射大炮。为了为 `CannonView` 处理简单的触摸事件，你将重写 `onTouchEvent` 方法（第 6.13.14 节），然后使用 `MotionEvent` (android.view) 中的常量来测试发生了什么事件并对其进行处理。

### 6.3.4 使用 `SoundPool` 和 `AudioManager` 添加声音

应用的音效通过 `SoundPool` (包 `android.media`) 进行管理，它可以用于加载、播放和卸载声音。声音使用 Android 的音频流之一进行播放，包括闹钟、音乐、通知、手机铃声、系统声音、电话等。你将使用 `SoundPool.Builder` 对象配置并创建一个 `SoundPool` 对象。你还将使用 `AudioAttributes.Builder` 对象创建一个与 `SoundPool` 关联的 `AudioAttributes` 对象。我们调用 `AudioAttributes.setUsage` 方法将音频指定为游戏。Android 建议使用音乐音频流播放声音，因为流音量可以通过设备的音量按钮进行控制。此外，我们使用 `VolumeControlStream` 方法允许通过设备的音量按钮控制量。该方法接收来自 `AudioManager` 类 (android.media) 的常量，该类提供了对设备音量电话铃控制的访问。

### 6.3.5 使用线程、`SurfaceView` 和 `SurfaceHolder` 进行逐帧动画

这通过从单独的执行线程更新元素来手动执行动画。为了实现这一点，我们使用一个带有 `run` 方法的 `Thread`，该方法引导我们的自定义 `Canvas` 更新游戏元素的位置，然后绘制它们。`run` 方法驱动逐帧动画——这被称为游戏循环。对应用用户界面的所有更新都必须在 GUI 执行线程中执行，因为 GUI 组件不是线程安全的——在 GUI 线程之外的更新会导致 GUI 崩溃。然而，游戏通常需要在单独的执行线程中执行复杂的逻辑，并且通常需要绘制到屏幕上。Android 提供了 `SurfaceView` —— 它是 `View` 的子类，提供了一个专用区域，其他线程可以在该区域以线程安全的方式在屏幕上绘制图形。



![](img/8c2e5496308864b3b07ddbd4401c4f77_257_0.png)

> 性能提示 6.1

> 尽量减少在 GUI 线程中执行的工作量是非常重要的，以确保 GUI 保持响应且不显示 ANR（应用程序无响应）对话框。

你通过 `SurfaceHolder` 类的对象操作 `SurfaceView`，这使你能够获取一个用于绘制的 `Canvas`。`SurfaceHolder` 类还提供了方法，允许线程对绘图的 `Canvas` 进行独占访问——一次只能有一个线程绘制到 `SurfaceView`。每个 `SurfaceView` 子类都应该实现 `SurfaceHolder.Callback`，它包含在 `SurfaceView` 创建、更改（例如尺寸或方向变化）或销毁时被调用的方法。

## 6.3 简单碰撞检测

大炮执行简单的碰撞检测，以确定炮弹是否与游戏的任何边缘、阻挡器或游戏的某部分碰撞。这些目标在第 6.3.11 节中给出。

游戏开发框架通常提供更高级的“像素级”碰撞检测能力。有许多此类框架（免费和基于免费的）可用于从最简单的 2D 游戏到最复杂的 3D 主机风格游戏（例如用于 Sony PlayStation 和 Microsoft Xbox 的游戏）。图 6.3 列出了一些游戏开发框架——还有几十个。许多框架支持多个平台，包括 Android 和 iOS。某些框架需要 C++ 或编程语言。

# 第 6 章 大炮游戏 App

游戏开发框架

| 框架 | URL |
|---|---|
| AndEngine | http://www.andengine.org |
| cocos2D | http://www.cocos2d.com |
| GameMaker | http://www.gamemaker.io |
| libgdx | https://libgdx.com |
| Unity | https://www.unity3d.com |
| Unreal Engine | https://www.unrealengine.com |

**图 6.3** 游戏开发框架

### 6.3 沉浸式模式

正如我们在 6.7 中提到的，游戏开发者经常使用全屏主题，例如 `Theme.Material.NoActionBar`。这在 Android 4.4 (KitKat) 中，沉浸式模式允许应用利用整个屏幕。如果应用处于沉浸模式，状态栏会在几秒钟后消失。

## 6.4 构建 GUI 和资源文件

本节将介绍创建应用的 GUI 和资源文件。

### 6.4.1 调整主题移除标题和应用栏

为了实现这一点，我们需要修改应用主题。按照第 3.7 节的操作设置横屏的资源文件。

### 6.4.2 创建项目

使用 Empty Activity 模板创建大炮游戏应用。在新建项目对话框中：

- 应用名称：Cannon Game
- 域名：`de.tel`（或指定自己的域名）

在编辑器中，删除 `activity_main.xml` 中的 *Hello world!* TextView。

### 6.4.3 Strings

我们在之前的章节中创建了 String 资源，因此我们在这里显示 String 资源名称和对应值（图 6.4）。双击 `res/values` 文件夹下的 `strings.xml`，然后点击 Open 链接在翻译编辑器中。

| 键 | 值 |
|---|---|
| results_format | 发射次数：%1d\n时间：%2ds |
| reset_game | 重置游戏 |
| win | 你赢了！ |
| lose | 你输了！ |
| time_remaining | 剩余时间：%.1f 秒 |

> **图 6.4** 大炮游戏 App 使用的 String 资源

### 6.4.4 颜色

此应用在 Canvas 上交替绘制颜色。对于此应用，我们在 `resources.colors.xml` 中添加了以下深蓝色和黄色：

```xml
<color name="dark">#197602</color>
<color name="light">#FFE100</color>
```

### 6.4.5 为应用添加声音

正如我们之前提到的，声音文件存储在应用的 `res/raw` 文件夹中。此应用使用了三个声音文件——`blocker_hit.wav`、`target_hit.wav` 和 `cannon_fire.wav`，它们位于书籍示例的 sounds 文件夹中。将这些文件添加到你的项目的方法：

1. 右键点击应用的 `res` 文件夹，选择 New > Android resource directory，打开 New Resource Directory 对话框。
2. 在 Resource type 下拉菜单中，选择 raw。目录名称将自动变为 `raw`。
3. 点击 OK 创建文件夹。
4. 将文件复制并粘贴到 `res/raw` 文件夹中。在弹出的 Copy 对话框中，点击 OK。

## 6.4.6 添加 MainActivityFragment

接下来，你把 `MainActivityFragment` 添加到项目中：

1. 在 Project（项目）窗口中，右键点击 `com.deitel.cannongame` 节点，选择 New > Fragment > (Blank)（新建/空白）。
2. 为 Fragment 指定 `MainActivityFragment`，为 Fragment Layout 指定 `fragment_main`。
3. 取消勾选 Include fragment factory methods? 和 interface callbacks? 旁边的复选框。

默认情况下，`fragment_main.xml` 包含一个显示 TextView 的 FrameLayout。Layout（布局）设计用于显示视图，可以层叠视图。移除 TextView——在此应用程序中，FrameLayout 将显示 `CannonView`。

## 6.4.7 编辑 activity_main.xml

在此应用程序中，`MainActivity` 仅显示 `MainActivityFragment`。按照以下步骤编辑布局：

1. 在编辑器中打开 `activity_main.xml` 并切换到 Text（文本）标签页。
2. 将 RelativeLayout 改为 fragment 并移除 padding 属性，使元素填充整个屏幕。
3. 切换到 Design（设计）视图，在 Component Tree（组件树）中选择 fragment，然后选择 id 为 `fragment`。
4. 将名称设置为 `com.deitel.cannongame.MainActivity`——与其手动输入，不如你可以点击 name 属性值字段右侧的省略号按钮，然后从弹出的 Fragments 对话框中进行选择。

请记住，编辑器的 Design 视图显示在特定层中显示的 fragment 预览。如果你没有在 `MainActivity` 的布局中指定要查看哪个 fragment，编辑器将显示“Rendering Problems”（渲染问题）消息。要指定要预览的 fragment，右键点击编辑器——无论是在 Design 视图还是 Component Tree 中——并点击 Choose Layout....（选择布局……）。然后，在 Resources 对话框中选择该布局的名称。

## 6.4.8 向 fragment_main.xml 添加 CannonView

你现在将把 `CannonView` 添加到 `fragment_main.xml`。你必须先创建 `CannonView.java`，以便在布局中放置 CustomView ，可以选择 `CannonView`。按照以下步骤创建 `CannonView.java` 并将 `CannonView` 添加到布局中：

## 6.5 本应用程序类概述

1. 展开 Project 窗口中的 java 文件夹。
2. 右键点击 `com.deitel.cannongame` 文件夹，然后选择 New > Java Class。
3. 在弹出的 Create New Class 对话框中，在 Name 字段输入 `CannonView`，然后点击 OK。文件将自动在编辑器中打开。
4. 在 `CannonView.java` 中，识别出 `CannonView` 扩展 `SurfaceView`。如果 `android.view.SurfaceView` 类中没有出现 import 语句，将光标放在 `SurfaceView` 名称的末尾。行开头上方会出现红色灯泡菜单，选择 Import Class（导入类）。
5. 如果你还没有这样做，请将光标放在 `SurfaceView` 的末尾。点击出现的红色灯泡菜单并选择 Create constructor super（创建 super 构造函数）。在弹出的 Choose Super Constructor 对话框的列表中选择两个参数的构造函数，然后点击 OK。IDE 将自动将构造函数添加到文件中。
6. 回到布局编辑器中 `fragment_main.xml` 的 Design 视图。
7. 点击 Palette（调色板）中 Custom 菜单中的 CustomView。
8. 在弹出的 Views 对话框中，选择 `CannonView (com.deitel.cannongame)`，然后点击 OK。
9. 悬停并点击 Component Tree 中的 Layout。该视图（你添加的 CustomView）将出现在 Component Tree 中。
10. 确保 Component Tree 窗口选择了 view (Custom)。在 Properties（属性）窗口中，将 `layoutwidth` 和 `layoutheight` 设置为 `match_parent`。
11. 在 Properties 窗口中，将 id 从 `view` 改为 `cannonView`。
12. 保存并关闭 `fragment_main.xml`。

此应用程序由八类组成：

- `MainActivity`（`Activity` 子类；第 6.6 节）——托管 `MainActivity-Fragment`。
- `MainActivityFragment`（第 6.7 节）——显示 `CannonView`。
- `GameElement`（第 6.8 节）——上下移动（`Blocker` 和 `Target`）或横跨屏幕（`Cannonball`）的项的父类。
- `Blocker`（第 6.9 节）——代表障碍物，使摧毁目标更具挑战性。
- `Target`（第 6.10 节）——代表一个可以被炮弹摧毁的目标。
- `Cannon`（第 6.11 节）——代表大炮，每当用户触摸屏幕时就会发射一个炮弹。
- `Cannonball`（第 6.12 节）——代表大炮在用户触摸屏幕时发射的炮弹。

## 第 6 章 大炮游戏应用程序

- `CannonView`（第 6.13 节）——包含游戏逻辑并协调 `Blocker`、`Targets`、`Cannonball` 和 `Cannon` 的行为。

你必须创建 `GameElement`、`Blocker`、`Target`、`Cannonball` 和 `Cannon` 类。对于每个类，在项目的 `app/java` 文件夹中右键点击 `delete.cannongame`文件夹并选择 New > Java Class。在 Create Class 对话框中，在 Name 字段输入类名并点击 OK。

## 6.6 MainActivity 是 Activity 的子类

`MainActivity` 类（图 6.5）是 `MainActivityFragment` 的宿主。在此应用程序中，`MainActivity` 仅显示 `MainActivityFragment`。按照以下步骤编辑布局：

```java
// MainActivity.java
// MainActivity 显示 Fragment
package com.deitel.cannongame;

import android.os.Bundle;
import android.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
}
```

## 6.7 MainActivityFragment 是 Fragment 的子类

`MainActivityFragment`（第 6.7 节）显示 `CannonView`。

```java
// MainActivityFragment.java
// MainActivity 创建并管理 CannonView
package com.deitel.cannongame;
import android.os.Bundle;
import android.support.v4.app.Fragment;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.media.AudioManager;

public class MainActivityFragment extends Fragment {
    private CannonView cannonView;

    // 当 Fragment 的视图需要创建时
    @Override
    public View onCreateView(LayoutInflater inflater, ViewGroup container,
        Bundle savedInstanceState) {
        super.onCreateView(inflater, container, savedInstanceState);

        // 载入 fragment_main.xml 布局
        View view = 
            inflater.inflate(R.layout.fragment_main, container, false);

        // 获取 CannonView 的引用
        cannonView = (CannonView) view.findViewById(R.id.cannonView);
        return view;
    }

    // Activity 创建后设置量控制
    @Override
    public void onCreateCreated(Bundle savedInstanceState) {
        super.onCreateCreated(savedInstanceState);

        // 允许音量按钮设置游戏音量
        getActivity().setVolumeControlStream(AudioManager.STREAM_MUSIC);
    }

    // 当 MainActivity 暂停时，停止游戏
    @Override
    public void onPause() {
        super.onPause();
        cannonView.stopGame();
    }

    // 当 MainActivity 销毁时，MainActivityFragment 释放资源
    @Override
    public void onDestroy() {
        super.onDestroy();
    }
}
```

## 第 6 章 大炮游戏 App

```java
super.onDestroy();
cannonView.releaseResources();
}
}
```

**图 6.6 | MainActivityFragment 创建并管理 CannonView。（2 个部分中的第 2 部分）**

## 6.8 GameElement 类

`GameElement` 类（图 6.7）——即 `Blocker`（障碍物）、`Target`（目标）和 `Cannonball`（炮弹）的父类——包含了大炮游戏中任何移动对象共同拥有的公共数据和功能。



# GameElement 类

```java
// GameElement.java
// 表示一个具有矩形边界的游戏元素
package com.deitel.cannongame;

import android.graphics.Canvas;
import android.graphics.Paint;
import android.graphics.Rect;

public class GameElement {
    protected CannonView view; // 包含此 GameElement 的视图
    protected Paint paint = new Paint(); // 用于绘制此 GameElement 的画
    protected Rect rect; // GameElement 的矩形边界
    private float velocity; // 此 GameElement 的垂直速度
    private int sound; // 与此 GameElement 关联的声音

    // 构造方法
    public GameElement(CannonView view, int color, int sound, int x,
        int y, int width, int length, float velocityY) {
        this.view = view;
        paint.setColor(color);
        rect = new Rect(x, y, x + width, length); // 设置边界
        this.sound = sound;
        this.velocity = velocityY;
    }

    // 更新 GameElement 位置并检查与墙的碰撞
    public void update(double interval) {
        // 更新垂直位置
        rect.offset(0, (int)(velocity * interval));

        // 如果此 GameElement 与墙碰撞，反转方向
        if (rect.top < 0 && velocity < 0 ||
            rect.bottom > view.getScreenHeight() && velocity > 0)
            velocity *= -1; // 反转此 GameElement 的速度
    }
}
```

**图 6.7 | GameElement 类表示一个具有矩形边界的游戏元素。（2 个部分中的第 1 部分）**

## 6.8 GameElement 类

```java
37 // 在给定的 Canvas 上绘制此 GameElement
38 public void draw(Canvas canvas) {
39     canvas.drawRect(rect, paint);
40 }
41 
42 // 与此类型 GameElement 对应的声音
43 public void playSound() {
44     view.playSound(sound);
45 }
```

**图 6.7 | GameElement 类表示一个具有矩形边界的游戏元素。（2 个部分中的第 2 部分。）**

### 6.8.1 实例变量和构造方法

`GameElement` 构造方法接收一个 `CannonView` 的引用（第 6.13 节），该视图实现了游戏逻辑并绘制游戏元素。构造方法接收一个表示 `GameElement` 32 位颜色的 `int`，以及一个表示与此 `GameElement` 关联的声音 ID 的 `int`。`CannonView` 存储了游戏所有的所有的声音，并为每个声音提供一个 ID。构造方法还接收：

- 表示 `GameElement` 左上角 `x` 和 `y` 位置的 `ints`
- 表示其宽度和高度的 `ints`
- 此 `GameElement` 的初始速度 `velocityY`。

第 20 行使用传递给构造方法的颜色的 `int` 表示来绘制对象的颜色。第 21 行计算 `GameElement` 的边界，并将其存储在一个表示矩形的 `Rect` 对象中。

### 6.8.2 方法 update，draw 和 playSound

`GameElement` 拥有以下方法：

- `update`（第 27–35 行）——游戏循环的每次迭代都会调用此方法来更新 `GameElement` 的位置。第 29 行根据垂直速度（`velocityY`）和调用 `update` 方法之间经过的时间（该方法通过参数 `interval` 接收）更新 `rect` 的垂直位置。第 32–34 行检查此 `GameElement` 是否与墙碰撞，如果是，则反转速度。

- `draw`（第 38–40 行）——当需要将 `GameElement` 绘制到屏幕上时调用此方法。该方法接收一个 `Canvas` 并在其上绘制 `GameElement` 所在的矩形。

- `playSound`（第 43–45 行）——播放与此类型 `GameElement` 关联的声音。该方法通过调用 `CannonView` 来播放 `GameElement` 的声音。

## 6.9 Blocker 子类

`Blocker` 类（图 6.8）——`GameElement` 的子类——表示玩家可以摧毁的障碍。`getPenalty` 方法（第 17–19 行）返回 `Blocker` 的惩罚。当 `Blocker` 与墙碰撞时，从剩余时间中减去该惩罚。`Blocker` 构造方法（第 9–14 行）接收参数并传递给父类构造方法以反转其速度（第 6.13 节），然后初始化 `penalty`。

```java
// Blocker.java
// GameElement 的子类
package com.deitel.cannongame;

public class Blocker extends GameElement {
    private int penalty; // 此 Blocker 的惩罚

    // 构造方法
    public Blocker(CannonView view, int color, int sound, int x,
        int y, int width, int length, float velocity, int penalty) {
        super(view, color, sound, x, y, width, length, velocity);
        this.penalty = penalty;
    }

    public int getPenalty() {
        return penalty;
    }
}
```

**图 6.8 | Blocker 子类。**

## 6.10 Target 子类

`Target` 类（图 6.9）——`GameElement` 的子类——表示玩家可以摧毁的目标。`getReward` 方法（第 17–19 行）返回 `Target` 的奖励。当炮弹与目标碰撞时，向剩余时间中加上该奖励。`Target` 构造方法（第 9–14 行）接收参数并传递给父类构造方法以增加（第 6.13 节），然后初始化 `reward`。

```java
// Target.java
// GameElement 的子类
package com.deitel.cannongame;

public class Target extends GameElement {
    private int reward; // 此 Target 的奖励

    // 构造方法
    public Target(CannonView view, int color, int sound, int x,
        int y, int width, int length, float velocity, int reward) {
        super(view, color, sound, x, y, width, length, velocity);
        this.reward = reward;
    }

    public int getReward() {
        return reward;
    }
}
```

**图 6.9 | Target 子类。（2 个部分中的第 1 部分）**

## 6.11 Cannon 类

`Cannon` 类（图 6.10-6.14）代表大炮游戏 App 中的大炮。大炮有一个底座和一个炮管，并且发射炮弹。

### 6.11.1 实例变量和构造方法

`Cannon` 构造方法（图 6.10）有四个参数。它接收：

- 大炮所在的 `CannonView`（`view`），
- 大炮底座的半径（`baseRadius`），
- 炮管的长度（`barrelLength`）以及
- 炮管的宽度（`barrelWidth`）。

第 25 行设置 `Paint` 对象的笔画宽度，以便使用给定的 `barrelWidth` 绘制炮管。第 27 行对齐大炮的炮管，使其初始与屏幕顶部和底部平行。`Cannon` 类有一个用于绘制炮管的 `Point barrel`、一个 `barrelAngle` 用于存储炮管的当前角度，以及一个 `cannonball` 用于存储最近发射且仍在屏幕上的炮弹。

```java
// Cannon.java
// 表示大炮并发射炮弹
package com.deitel.cannongame;

import android.graphics.Canvas;
import android.graphics.Color;
import android.graphics.Paint;
import android.graphics.Point;
```

**图 6.10 | Cannon 实例变量和构造方法。**

# 232

# 第 6 章 大炮游戏 App

```java
public class Cannon { // 大炮的半径
    private int barrelRadius;
    private int barrelLength; // 炮管的长度
    private Point barrelEnd = new Point(); // 炮管的端点
    private double barrelAngle; // 炮管的角度
    private Cannonball cannonball; // 大炮的炮弹
    private Paint paint = new Paint(); // 用于绘制大炮的画笔
    private CannonView view; // 包含大炮的视图

    // 构造函数
    public Cannon(CannonView view, int barrelRadius, int barrelLength,
    int barrelWidth) {
        this.view = view;
        this.barrelRadius = barrelRadius;
        this.barrelLength = barrelLength;
        paint.setStroke(barrelWidth); // 设置炮管的宽度
        paint.setColor(Color.BLACK); // 大炮的颜色为黑色
        align(Math.PI / 2); // 炮管指向正右
    }
}
```

**图 6.1** 大炮实例和构造函数。（2 部分中的第2 部分）

## 6.1.2 方法 align

`align` 方法（图 6.1）用于对齐大炮。该方法接收一个弧度单位的参数。我们使用大炮的 `barrelAngle` 来确定炮管端点 `barrelEnd` 的 `x` 和 `y` 坐标——这用于从屏幕左边缘的大炮中心绘制一条线到大炮炮管端点。第 32 行存储了 `barrelAngle`，以便以后按角度发射炮弹。

```java
// 将炮管对齐到给定的角度
public void align(double barrelAngle) {
    this.barrelRadius = barrelAngle;
    barrelEnd.x = (int) (FrameLength * Math.sin(barrelAngle));
    barrelEnd.y = (int) (-FrameLength * Math.cos(barrelAngle)) +
    view.getScreenWidth() / 2);
}
```

**图 6.11** 大炮方法 align。

## 6.1.3 方法 fireCannonball

`fireCannonball` 方法（图 6.12）按照当前的轨迹在屏幕上发射炮弹。第 41–46 行计算炮弹速度的水平和垂直分量。第 49–50 行计算炮弹半径，该半径为屏幕高度的 `Cannonball.RADIUS_PERCENT`。第 53–56 行“装填大炮”（即创建一个新的 `Cannonball` 并将其放置在 `Cannonball` 内部）。最后，我们播放炮弹的的音效（第 58 行）。

```java
// 在大炮指向的方向创建并发射 Cannonball
public void fireCannonball() {
    // 计算炮弹速度的 x 分量
    int velocityX = (int)(CannonView.CANNONBALL_SPEED_PERCENT *
        view.getScreenWidth() * Math.sin(barrelAngle));

    // 计算炮弹速度的 y 分量
    int velocityY = (int)(CannonView.CANNONBALL_SPEED_PERCENT *
        view.getScreenWidth() * Math.cos(barrelAngle));

    // 计算炮弹半径
    int radius = (int)(view.getScreenHeight() *
        CannonView.CANNONBALL_RADIUS_PERCENT);

    // 构造 Cannonball 并将其放置在大炮中
    cannonball = new Cannonball(view, Color.BLACK,
        CannonView.CANNON_SOUND_ID, -radius,
        view.getScreenHeight() / 2 - radius, radius, velocityX,
        velocityY);

    cannonball.playSound(); // 播放发射炮弹的声音
}
```

**图 6.12** 大炮方法 fireCannonball。

## 6.1.4 方法 draw

`draw` 方法（图 6.13）在屏幕上绘制大炮。我们分两绘制大炮：先绘制大炮的炮管，然后绘制大炮的底座。

```java
// 在 Canvas 上绘制大炮
public void draw(Canvas canvas) {
    // 绘制炮管
    canvas.drawLine(0, view.getScreenHeight() / 2, barrelEnd.x,
        barrelEnd.y, paint);

    // 绘制大炮底座
    canvas.drawCircle(0, (int)view.getScreenHeight() / 2,
        (int)baseRadius, paint);
}
```

**图 6.13** 使用 Cannon 方法 drawLine 绘制炮管

*使用 `Cannon` 方法 `drawLine` 绘制炮管*

我们使用 `Canvas` 的 `drawLine` 方法来显示炮管（第 64–65 行）。该方法接收五个参数——前四个表示线条起点和终点的 `x-y` 坐标，最后一个是用于配置线条特征（如厚度）的 `Paint` 对象。记得 `paint` 已经配置为按照构造函数中给厚度绘制炮管（图 6.10，第 25 行）。

使用 `Canvas` 方法 `drawCircle` 绘制大炮底座

第 68–69 行使用 `Canvas` 的 `drawCircle` 方法通过绘制一个以屏幕左边缘为中心的圆来绘制大炮的半圆底座。因为圆心位于屏幕左边缘。

## 6.1.5 方法 getCannonball 和 removeCannonball

`getCannonball` 方法（第 73–75 行）返回炮弹。`removeCannonball` 方法（第 78–80 行）将 `cannonball` 设置为 `null`。

```java
// 返回 Cannonball
public Cannonball getCannonball() {
    return cannonball;
}

// 移除 Cannonball
public void removeCannonball() {
    cannonball = null;
}
```

**图 6.14** getCannonannonball 和 removeCannonball 方法。

## 6.1.1 实例变量和构造函数

`GameElement` 子类 `Cannonball` 表示炮弹。



```java
package com.example.cannonball;

import android.graphics.Canvas;
import android.graphics.Rect;

public class Cannonball extends GameElement {
    private float velocityX;
    private boolean isOn;

    // 构造函数
    public Cannonball(CannonView view, int color, int soundId, int x,
        int y, float radius, float velocityX, float velocityY) {
        super(color, soundId, x, y);
        this.radius = radius;
        this.velocityX = velocityX;
        isOn = true;
    }
}
```

**图 6.15** `Cannonball` 实例变量和构造函数。（2 部分中的第 1 部分）

## 6.1.2 方法 `getRadius`, `collidesWith`, `isOnScreen` 和 `reverseVelocity`

`getRadius` 方法（图 6.16，第 22–24 行）通过计算 `shape.right` 和 `shape.left` 之间距离的一半来返回炮弹半径。`isOnScreen` 方法在炮弹位于屏幕上时返回 `true`。

```java
// 获取 Cannonball 半径
private int getRadius() {
    return (shape.right - left) / 2;
}

// 测试 Cannonball 是否与指定的 GameElement 碰撞
public boolean collidesWith(GameElement element) {
    return (Rect.intersects(shape, element.shape) && velocityX > 0);
}

// 如果 Cannonball 在屏幕上则返回 true
public boolean isOnScreen() {
    return isOn;
}

// 反转 Cannonball 的水平速度
public void reverseVelocityX() {
    velocityX = -velocityX;
}
```

**图 6.16** | `Cannonball` 方法 `getRadius`, `collidesWith`, `isOnScreen` 和 `reverseVelocity`。

### 使用 `collidesWith` 方法与其他 `GameElement` 碰撞

`collidesWith` 方法（第 27–29 行）检查炮弹是否与给定的 `GameElement` 碰撞。我们基于矩形进行简单的碰撞检测。炮弹边界。如果炮弹与 `GameElement` 碰撞，必须满足以下两个条件：

- 炮弹边界（存储在 `Rect` 形状中）必须与 `GameElement` 形状的边界交叉。使用 `Rect` 的 `intersects` 方法来检查炮弹和 `GameElement` 的边界是否交叉。

- 炮弹将水平向 `GameElement` 移动。炮弹从左向右移动（除非碰到障碍物）。如果 `velocityX`（水平速度）为正，则炮弹正在向右移动 `GameElement`。

### 使用 `reverseVelocityX` 反转炮弹的水平速度

`reverseVelocityX` 方法通过将 `velocityX` 乘以 -1 来返回炮弹的水平速度。如果碰撞返回 `true`，`CanvasView.testForCollisions` 调用 `reverseVelocity` 来反转水平速度，使炮弹向部分（6.13.11）反弹。

## 6.12.3 `update` 方法

`update` 方法（图 6.17）调用父类的 `update` 方法（第 44 行）来更新炮弹的垂直速度并检查碰撞。第 47 行使用 `Rect` 的 `offset` 水平平移该炮弹的边界。我们将水平速度（`velocityX`）乘以经过的时间（`interval`）来确定偏移量。第 50-53 行如果炮弹撞到任意边缘，则将 `onScreen` 设置为 `false`。

```java
41    // 更新炮弹的位置
42  @Override
43  public void update(double interval) {
44      super.update(interval); // 更新炮弹的垂直位置
45      // 更新水平位置
46      shape.offset((int)(velocityX * interval), 0);
47
48      // 如果炮弹移出屏幕
49      if (shape.left < 0 ||
50          shape.bottom > view.getHeight() ||
51          shape.right > view.getWidth()) {
52          onScreen = false; // 设置为被移除
53  }
```

**图 6.17** | 重写的 `GameElement` 方法 `update`。

## 6.12.4 `draw` 方法

`draw` 方法（图 6.18）重写了 `GameElement` 的 `draw` 方法，并使用 `Canvas` 的 `drawCircle` 方法在当前位置绘制炮弹。前两个参数代表圆心的坐标。第三个参数是圆的半径。最后一个参数是指定圆的绘制特征的 `Paint` 对象。

```java
56 // 在给定的画布上绘制炮弹
57 @Override
58 public void draw(Canvas canvas) {
59     canvas.drawCircle(shape.left + getRadius(),
60     shape.top + getRadius(), getRadius(), paint);
61 }
62 }
```

**图 6.18** 重写的 `GameElement` 方法 `draw`。

## 6.13 `SearchView` 的子类 `CannonView`

`CannonView`（6.19–6.33）是 `View` 的一个自定义子类，它实现了非游戏逻辑并在屏幕上绘制游戏对象。

### 6.13.1 包声明和 `import` 语句

图 6.19 列出了第 6.3 节中讨论的 `CannonView` 使用的新类和接口的包声明和 `import` 语句。我们在 6.19 中高亮了它们。

```java
1 // CannonView.java
2 // 显示并控制大炮游戏
3 package com.demo.cannongame;
4 
5 import android.app.Activity;
6 import android.app.AlertDialog;
7 import android.app.Dialog;
8 import android.app.DialogFragment;
9 import android.content.Context;
10 import android.content.DialogInterface;
11 import android.graphics.Canvas;
12 import android.graphics.Color;
13 import android.graphics.Point;
14 import android.graphics.Point;
15 import android.media.AudioAttributes;
16 import android.media.SoundPool;
17 import android.os.Bundle;
18 import android.os.AttributeSet;
19 import android.util.Log;
20 import android.util.SparseArray;
21 import android.view.MotionEvent;
22 import android.view.SurfaceHolder;
23 import android.view.View;
24 import android.view.View;
25 
26 import java.util.ArrayList;
27 import java.util.Random;
```

**图 6.19** `CannonView` 类的包和 `import` 语句（部分 1）。

```java
30 public class CannonView extends SurfaceView
31 implements SurfaceHolder.Callback {
32
```

**图 6.19** `CannonView` 类的包和 `import` 语句（部分 2）。

### 6.13.2 实例变量和常量

6.20 列出了 `CannonView` 类的常量和实例变量。我们将解释游戏中遇到的每一个变量。许多常量用于根据屏幕缩放游戏元素的计算。

```java
33 private static String TAG = "CannonView"; // 用于日志记录
34
35 // 游戏常量
36 public static final int MISS_PENALTY = 2; // 命中扣除 2 秒
37 public static final int HIT_REWARD = 3; // 命中增加 3 秒
38
39 // 大炮常量
40 public static final int CANNON_BASE_RADIUS = 10;
41 public static final int CANNON_SPEED = 20;
42
43 // 炮弹常量
44 public static final int CANBALL_RADIUS = 8;
45 public static final int CANBALL_SPEED = 30;
46
47 // 目标常量
48 public static final int TARGET_WIDTH = 5;
49 public static final int TARGET_LENGTH = 6;
50 public static final int TARGET_X = 7;
51 public static final int TARGET_SPACING = 10;
52 public static final int TARGET_PIECES = 11;
53 public static final int TARGET_MIN_SPEED = 12;
54 public static final int TARGET_MAX_SPEED = 13;
```

## 第 6 章 大炮游戏 App

```java
// configure audio attributes for game audio
AudioAttributes.Builder builder = new AudioAttributes.Builder();
builder.setUsage(AudioAttributes.USAGE_GAME);

// initialize SoundPool to play the app's three sound effects
SoundPool.Builder builder = new SoundPool.Builder();
builder.setMaxStreams(3);
builder.setAttributes(attrBuilder.build());
soundPool = builder.build();

// Create Map of sounds and pre-load sounds
SparseArray soundMap = new SparseArray(); // create new SparseArray
soundMap.put(TARGET_ID, SOUND);
soundPool.load(context, R.target_hit, 1);
soundPool.load(context, R.cannon_fire, 1);
soundPool.load(context, R.blocker_hit, 3);
```

```java
textPaint = new Paint();
backgroundPaint = new Paint();
backgroundPaint.setColor(Color.WHITE);
```

**图 6.21** `Cannonvector`。（2 部分中的 2 部分）

### 注册 `SurfaceHolder.Callback` 监听器

第 102 行将其（即 `CannonView`）注册为 `SurfaceHolder.Callback`，当 `SurfaceView` 被创建、更新和销毁时会接收方法。继承自 `SurfaceView` 方法 `getHolder` 返回用于管理 `SurfaceView` 的 `SurfaceHolder` 对象，而 `SurfaceHolder` 方法 `addCallback` 实现了 `SurfaceHolder.Callback`。

### 配置 `SoundPool` 并加载声音

第 105–121 行创建了我们在 App 中使用的声音。首先，我们创建一个 `AudioAttributes.Builder` 对象（第 105 行）并调用 `setUsage` 方法（第 106 行），该方法创建了一个表示我们将如何使用音频的约束条件。为此，我们使用 `AudioAttributes.USAGE_GAME` 常量，它表示该音频正被用作游戏音频。接下来，我们创建一个 `SoundPool.builder` 对象（第 109 行），这将使我们能够创建一个 `SoundPool` 来播放和加载 App 的声音。接着，我们调用 `SoundPool.builder.setMaxStreams` 方法（第 110 行），它接受一个参数，表示可以同时播放的最大声音数。我们一次播放一个声音。某些复杂的游戏可能会同时播放多个声音。然后，我们调用 `AudioAttributes.builder.setAudioAttributes` 方法（第 111 行），在创建后使用这些音频属性。第 115 行创建了一个 `SparseArray`（`soundMap`），它将整数键映射到整数值。对于较少量的键值对，`SparseArray` 与 `HashMap<Integer, Integer>` 类似但效率更高。在这种情况下，我们将声音键（定义在图 6.20 第 86–88 行中）映射到已加载声音的 ID，这些 ID 由以下 `SoundPool` 的 `load` 方法的返回值（在图 6.22 第 117、119 和 121 行中被调用）。每个声音 ID 都可用于播放声音（并将其资源返回给系统）。`SoundPool` 方法 `load` 接收三个参数——`Context`、代表要加载的音频文件资源 ID 以及声音的优先级。根据该方法的文档，最后一个参数目前未被使用，并指定为 1。

### 创建用于绘制背景和计时器文本的 `Paint` 对象

第 123–124 行创建了用于绘制游戏背景和剩余时间时的 `Paint` 对象。文本颜色默认为黑色，第 125 行将背景设为白色。

### 6.13.4 重写 `View` 方法 `onChanged`

图 6.22 观察 `View` 类的 `onChanged` 方法，每当 `View` 尺寸变化时该方法就会被调用，包括 `View` 在布局加载时首次添加到 `View` 层次结构中时。它始终显示在布局中，因此当 `onCreate` 方法加载 GUI 时，`onChanged` 只被调用一次。该方法接收 `View` 的新宽度和高度，在第一次调用此方法时，旧的宽度和高度为 0。第 138–139 行配置了 `textPoint` 对象，用于绘制剩余文本。第 138 行将文本大小设置为屏幕高度（`innerHeight`）的 `TEXT_PERCENT`。我们通过试错在图 6.20 中得到了 `TEXT_PERCENT` 的值以及其他缩放因子，并选择了能让游戏元素在屏幕上看起来良好的值。

```java
128 // 当 SurfaceView 的尺寸发生时，
129 // 例如它被首次添加到 View 层次结构中
130 @Override
131 protected void onChanged(int w, int h, int oldw, int oldh) {
132 super.onChanged(w, h, oldw, oldh);
133 
134 screenWidth = w; // 存储 CannonView 的宽度
135 screenHeight = h; // 存储 CannonView 的高度
136 
137 // 配置文本属性
138 textPoint.setText((int)(TEXT_SIZE_PERCENT * screenHeight));
139 textPoint.setAntialias(true); // 平滑文本
140 }
```



图 6.22 | 重写 `View` 方法`onChanged`。

### 6.13.5 方法 `getScreenWidth`, `getScreenHeight` 和 `playSound`
在图 6.23 中，`getScreenWidth` 和 `getScreenHeight` 方法返回屏幕的宽度和高度，这些在 `onChanged` 方法中更新（图 6.22）。使用 `SoundPool`，`playSound` 方法（第 153–155 行）通过 `SoundPool` 播放带有给定 ID 的声音，该 ID 是与声音的。`SoundPool` 的 `load` 方法（在图 6.22 第 117、119 和 121 行中调用）的返回值。每个声音 ID 都可用于播放声音（并将其资源返回给系统）。`SoundPool` 方法 `load` 接收三个参数——`Context`、代表要加载的音频文件资源 ID 以及声音的优先级。根据该方法的文档，最后一个参数目前未被使用，并指定为 1。

创建用于绘制背景和计时器文本的 `Paint` 对象
第 123–124 行创建了用于绘制游戏背景和剩余时间时的 `Paint` 对象。文本颜色默认为黑色，第 125 行将背景设为白色。

**图 6.21** `Cannon` 方法 `getScreenWidth`, `getScreenHeight`。

### 6.13.4 重写 `View` 方法 `onChanged`
`newGame`（图 6.24）重置了用于控制游戏的实例变量。第 160–163 行创建了一个新的对象：屏幕的半径、宽度、长度、长度和速度。

**图 6.21** `Cannon` 方法 `getScreenWidth`, `getScreenHeight`。

### 6.13.5 方法 `getScreenWidth`, `getScreenHeight` 和 `playSound`
在图 6.23 中，`getScreenWidth` 和 `getScreenHeight` 方法返回屏幕的宽度和高度，这些在 `onChanged` 方法中更新（图 6.22）。使用 `SoundPool`，`playSound` 方法（第 153–155 行）通过 `SoundPool` 播放带有给定 ID 的声音，该 ID 是与声音的。`SoundPool` 的 `load` 方法（在图 6.22 第 117、119 和 121 行中调用）的返回值。每个声音 ID 都可用于播放声音（并将其资源返回给系统）。`SoundPool` 方法 `load` 接收三个参数——`Context`、代表要加载的音频文件资源 ID 以及声音的优先级。根据该方法的文档，最后一个参数目前未被使用，并指定为 1。

创建用于绘制背景和计时器文本的 `Paint` 对象
第 123–124 行创建了用于绘制游戏背景和剩余时间时的 `Paint` 对象。文本颜色默认为黑色，第 125 行将背景设为白色。

**图 6.21** `Cannon` 方法 `getScreenWidth`, `getScreenHeight`。

### 6.13 SurfaceView 的子类 `CannonView`

```java
// 将 TARGET_PIES 个 Target 添加到列表中

for (int n = 0; n < TARGET_PIES; n++) {

    // 为目标 n 确定一个最小到最大之间的随机速度

    double velocity = screenheight * (random.nextDouble() *

        TARGET_MAX_SPEED_PERCENT - TARGET_MIN_SPEED_PERCENT) +

        TARGET_MIN_SPEED_PERCENT);

    // 在深色和浅色之间切换 Target 颜色

    int color = (n % 2 == 0) ?

        getResources().getColor(R.color.dark, getContext().Theme()) :

        getResources().getColor(R.color.light, getContext().Theme());

    // 重置下一个目标的初始速度

    velocity = -1;

    // 在列表中创建一个新的 Target

    targets.add(new Target(this, color, HIT_REWARD, targetX, targetY,

        (int)(TARGET_WIDTH_PERCENT * screenWidth),

        (int)(TARGET_LENGTH_PERCENT * screenHeight)));

    // 增加 x 坐标以便将下一个目标位置靠右

    targetX += (TARGET_WIDTH_PERCENT + TARGET_SPACING_PERCENT) *

        screenWidth;

}

// 创建一个新的 Blocker

blocker = new Block(this, Color.BLACK, MISS_PENALTY,

    (int)(BLOCKER_X_PERCENT * screenWidth),

    (int)((0 - BLOCKER_LENGTH_PERCENT / 2) * screenHeight),

    (int)(BLOCKER_WIDTH_PERCENT * screenWidth),

    (int)(BLOCKER_LENGTH_PERCENT * screenHeight),

    (float)(BLOCKER_SPEED_PERCENT * screenHeight));

timeLeft = 10; // 设置倒计时为 10 秒

shootsFired = 0; // 设置初始射击次数

totalElapsedTime = 0.0; // 设置已用时间为零

if (gameOver) { // 在上游戏结束后开始新游戏

    gameOver = false; // 游戏未结束

    cannonThread = new CannonThread(getHolder()); // 创建线程

    cannonThread.start(); // 启动游戏循环线程

}

hideSystemBars();
```

**图 6.24** `Cannon` 方法 `newGame`（1 部分中的 2 部分）。

## 244 第 6 章 大炮游戏应用程序

第 165 行创建了一个 `Random` 对象，用于随机化目标（`Target`）的速度。第 166 行创建了一个新的 `Target` 类型的 `ArrayList`。第 169 行将 `targetX` 初始化为第一个 `Target` 在屏幕左侧的像素位置。第一个 `Target` 位于屏幕宽的 `TARGET_FIRST_X_PERCENT` 处。第 172–173 行初始化 `targetY`，使所有 `Target` 在屏幕上垂直居中。第 176–203 行在每次运行时创建 `TARGET_PIECES`（共 9 个组）并将它们添加到 `targets` 集合中。第 180–182 行将新 `Target` 的速度设置为屏幕高度百分比之间的随机值。第 185–189 行将新 `Target` 的颜色设置为在 `R.color.dark` 和 `R.color.light` 颜色之间交替，并赋予负速度。第 191 行反转每个新目标的速度，使得某些目标向上移动开始，某些则向下移动。第 194–197 行构造新的 `Target` 并将其添加到 `targets` 中。

第 206–211 行构造了一个新的 `Blocker` 并存储在 `blocker` 变量中。`Blocker` 位于屏幕宽的 `BLOCKER_PERCENT` 处，并在屏幕上垂直居中以开始游戏。`Blocker` 的宽度为屏幕宽的 `BLOCKER_WIDTH_PERCENT`，高度为屏幕高度的 `BLOCKER_HEIGHT_PERCENT`。`Blocker` 的高度为屏幕高度的 `BLOCKER_PERCENT`。

如果 `gameOver` 为 `true`，它只会在第一次游戏完成后发生，第 219 行重置 `gameOver`，第 220–221 行创建一个新的 `CannonThread` 并调用其 `start` 方法开始控制游戏的循环。第 224 行调用 `hideSystemBars` 将应用程序置于沉浸式模式——这会隐藏状态栏并允许用户随时从屏幕顶部向下滑动来禁用它们。

### 6.13.7 方法 `updatePositions`

`updatePositions` 方法（图 6.25）由 `CannonThread` 的 `run` 方法（节 6.13.10）调用，用于更新屏幕上的元素并执行简单的碰撞检测。游戏元素的新位置是根据上一个动画帧与当前动画帧之间过的毫秒时间计算的。这使得游戏能够根据设备的刷新率，随着每个游戏元素的移动进行更新。我们将在节 6.13.15 介绍游戏循环时详细讨论这一点。

```java
// 由 CannonThread 重复调用以更新游戏元素

private void updatePositions(double elapsedMS) {

    double interval = elapsedMS / 1000.0; // 转换为秒

    // 如果炮弹在屏幕上，更新其位置

    if (cannon.getCannonBall() != null) {

        cannon.getCannonBall().update(interval);

    }

    blocker.update(interval); // 更新障碍物的位置

    for (GameElement target : targets) {

        target.update(interval);

    }

}
```

**图 6.25** | `CannonView` 方法 `updatePositions`。（2 部分中的第 1 部分）

```java
timeLeft -= interval; // 从剩余时间中减去
```

```java
// 如果计时器到达零

if (timeLeft <= 0) {

    timeLeft = 0.0;

    gameOver = true; // 游戏结束

    cannonThread.setRunning(false); // 终止线程

    showGameOverDialog(R.string.lose); // 显示失败对话框

}
```

```java
// 如果所有碎片都被命中

if (targets.isEmpty()) {

    cannonThread.setRunning(false); // 终止线程

    showGameOverDialog(R.string.win); // 显示胜利对话框

    timeLeft = 0;

}
```

**图 6.25** | `CannonView` 方法 `updatePositions`。（2 部分中的第 2 部分）

**自上一个动画帧以来的经过时间**
第 229 行将自上一帧以来的经过时间从毫秒转换为秒。该值用于修改游戏元素的位置。

**更新炮弹、障碍物和目标的位置**
为了更新 `GameElement` 的位置，第 232–238 行调用了 `Cannonball`（如果屏幕上有）、`Blocker` 以及所有剩余目标的 `update` 方法。`update` 方法获取自上一个帧以来经过的时间，以便位置能够根据间隔更新正确的量。

**更新剩余时间并判断时间是否耗尽**
我们通过自上一个动画帧以来经过的时间来更新 `timeLeft`（第 240 行）。如果 `timeLeft` 达到零，则游戏结束，因此我们将 `timeLeft` 设置为 0.0 以防其为负数；否则，屏幕有时会显示负的最终时间。然后我们将 `gameOver` 设置为 `true`，通过带参数 `false` 调用其 `running` 方法来终止 `CannonThread`，并调用带有标识失败消息的字符串资源的 `showGameOverDialog` 方法。

### 6.13.8 方法 `alignAndFireCannonball`

当用户触碰屏幕时，`onTouch` 方法（节 6.13.14）调用 `alignAndFireCannonball`（图 6.26）。第 267–272 行计算将大炮对准触摸点的角度。第 275 行调用 `Cannon` 的 `align` 方法，根据轨迹角度对准大炮。最后，如果炮弹存在且在屏幕上，第 280–281 行发射炮弹并增加 `shotsFired` 计数。

## 第 6 章 大炮游戏应用程序

```java
// 对齐球，如果它已经在屏幕上，则发射炮弹

public void alignAndFireCannonball(MotionEvent event) {

    // 获取视图中的触摸位置

    Point touchPoint = new Point((int) event.getX(), (int) event.getY());

    // 计算距离屏幕中心的距离

    double centerY = screenHeight / 2;

    double angle = 0;

    // 计算球相对于水平的角度

    angle = Math.atan2(touchPoint.x, centerY);

    // 在触碰处绘制大炮

    cannon.align(angle);

    // 如果屏幕上没有炮弹，则发射炮弹

    if (cannon.getCannonball() == null) {

        cannon.fireCannonball();

    }

}
```

**图 6.26** | 方法 `alignAndFireCannonball`

### 6.13.9 方法 `gameOverDialog`

游戏结束时，`gameOverDialog` 方法（图 6.27）使用 4.7 节中学到的技术显示 `AlertDialog`，告知玩家胜利还是失败、射击次数以及经过的时间。第 301–311 行为重新开始游戏创建一个重置按钮。

```java
// 游戏结束时显示 Alert

private void gameOverDialog(int messageId) {

    // 创建 DialogFragment 并返回

    final DialogFragment result = new DialogFragment() {

        // 创建显示 messageId 的 Dialog

        @Override

        public Dialog onCreateDialog(Bundle bundle) {

            AlertDialog.Builder builder = new AlertDialog.Builder(getActivity());

            builder.setTitle(getResources.getString(messageId));

            // 显示射击次数和总时长

            builder.setMessage(getResources.getString(R.string.results_format(shotsfired,totalElapsed)));

            // 点击“重置游戏”按钮时

            builder.setPositiveButton(R.string.reset_game, new DialogInterface.OnClickListener() {

                @Override

                public void onClick(DialogInterface dialog, int which) {

                    dialogDisplayed = false;

                    newGame(); // 设置并启动新游戏

                }

            });

            return builder.create().show();

        }

    };

    // 在 GUI 线程中，使用 FragmentManager 显示 DialogFragment

    activity.runOnUiThread(new Runnable() {

        public void run() {

            // 退出沉浸式模式

            showSystemBars();

            dialogDisplayed = true;

            result.setCancelable(false); // 模态对话框

            result.show(activity.getFragmentManager(), "results");

        }

    });

}
```

**图 6.27** | 方法 `gameOverDialog`。（2 部分中的第 1 部分）

## SurfaceView 的子类

### 6.13.10 方法 `drawGameElements`

`drawGameElements` 方法（图 6.28）使用 `CannonThread`（节 6.13.15）从 `SurfaceView` 的 `SurfaceHolder` 获取的内容，在 `SurfaceView` 上绘制大炮、炮弹、障碍物目标。

**使用 `drawRect` 方法清除画布**

首先，我们调用 `Canvas` 的 `drawRect` 方法（第 333–334 行）清除画布，以便在新的位置上显示游戏元素。该方法接收矩形的

```java



// 将游戏绘制到指定的 `Canvas`

```
public void drawGameElements(Canvas canvas) {

    // 清除背景

    canvas.drawRect(0, 0, canvas.getWidth(), canvas.getHeight(),

        backgroundPaint);

    // 显示剩余时间

    canvas.drawText(getResources().toString(),

        R.string.time_remaining_format, timeLeft, 50, 100, textColor);

    cannon.draw(canvas); // 绘制大炮

    // 绘制 Cannonball()

    if (cannon.getCannonball() != null &&

        cannon.getCannonball().isOnScreen())

        cannon.getCannonball().draw(canvas);

    blocker.draw(canvas); // 绘制障碍物

    // 绘制所有的 Targets

    for (GameObject target : targets)

        target.draw(canvas);

}
```

图 6.28 | `Canvas` 方法 `drawGameElements`。

左上角的 `y` 坐标、宽度和高度，以及指定了特征的 `Paint` 对象——实际上，是 `backgroundPaint` 将绘制颜色设置为白色。

## 使用 `Canvas` 方法 `drawText` 绘制剩余时间

接下来，我们调用 `Canvas` 的 `drawText` 方法（第 337–380 行）来显示游戏中的剩余时间。我们传递的参数是要显示的字符串、显示的 `x` 和 `y` 坐标，以及 `textPaint`（在图 6.22 第 138–139 行中配置），用于描述应如何渲染文本（即字体大小、颜色和其他属性）。

## 使用 `draw` 方法绘制大炮、炮弹、障碍物和目标

第 339–350 行绘制了大炮、炮弹（如果它在屏幕上）、障碍物以及所有的 `Target`。这些元素中的每一个都是通过调用自己的 `draw` 方法并传入 `canvas` 来绘制的。

## 6.13.11 方法 `testForCollisions`

`testForCollisions` 方法（图 6.29）检查大炮是否与任何 `Target` 碰撞或与 `blocker` 碰撞，并在发生碰撞时在游戏中应用某些效果。第 359–360 行检查大炮是否在屏幕上。如果是，第 362 行调用 `Cannonball().collisionWith` 方法判断炮弹是否与 `Target` 碰撞。如果发生碰撞，第 363 行调用 `Target` 的 `playSound` 来播放击中目标的声音，第 366 行根据 `Target` 的奖励增加 `timeLeft`，第 368–369 行从屏幕上移除炮弹和 `Target`。第 370 行递减 `n`，以确保当前位置 `n` 的目标将进行碰撞测试。

## 6.13 `CannonView` `SurfaceView` 的子类

第 376 行如果与大炮关联的 `Cannonball` 不在屏幕上，则销毁它。如果炮弹仍在屏幕上，第 380–381 行通过 `collidesWith` 判断炮弹是否与 `blocker` 碰撞。如果是，第 382 行调用 `blocker` 的 `playSound` 方法播放击中障碍物的声音，第 385 行通过调用 `Cannonball` 的 `reverseVelocityX` 反转炮弹的惯性速度，第 388 行通过与 `blocker` 关联的惩罚减少生命值。

```
// 检查球是否与障碍物或任何 Target 碰撞

// 处理碰撞

public void testForCollisions() {

    // 移除 Cannonball 碰撞的 target

    if (getCannonball() != null && getCannonball().isOnScreen()) {

        for (int n = 0; n < targets.size(); n++) {

            if (getCannonball().collidesWith(targets.get(n))) {

                targets.get(n).playSound(); // 播放击中声音

                // 将奖励时间添加到剩余时间

                timeLeft += targets.get(n).getHitReward();

                cannon.removeCannonball(); // 从游戏中移除炮弹

                targets.remove(n); // 移除被击中的 Target

                n--; // 确保不会跳过新 n 的测试

                break;

            }

        }

    } else {

        // 如果炮弹不应在屏幕上，则移除它

        cannon.removeCannonball();

    }

}

    // 检查球是否与 blocker碰撞

    if (getCannonball() != null && getCannonball().collidesWith(blocker)) {

        blocker.playSound(); // 播放击中 blocker的声音

    }

    // 反转球的方向

    getCannonball().reverseVelocityX();

    // 从剩余时间中扣除 blocker 的错过惩罚

    timeLeft -= blocker.getMissPenalty();

}
```

**图 6.29** | `CannonView` 方法 `testForCollisions`。

## 6.13.12 方法 `stopGame` 和 `releaseResources`

类 `MainActivityFragment` 的 `onCreate` 和 `onDestroy`（第 6.13 节）分别调用类 `CannonView` 的 `stopGame` 和 `releaseResources` 方法（图 6.30）。方法 `stopGame`（第 393–396 行）从 `Activity` 调用，以便在 `Activity` 的 `Pause` 方法调用时停止游戏——为了简单起见，我们在这个示例中没有存储状态。方法 `releaseResources`（第 399–402 行）调用 `SoundPool` 的 `release`。

```
// 停止游戏：由 Activity 的 onPause 调用

public void stopGame() {

    if (cannonThread != null) {

        cannonThread.setRunning(false);

    }

}

// 释放资源：由 Activity 的 onDestroy 调用

public void releaseResources() {

    if (cannonThread != null) {

        try {

            cannonThread.join();

        } catch (InterruptedException e) {

            Log.e(TAG, "Thread interrupted", e);

        }

    }

    soundPool.release();

}
```

### 6.13 实现 `SurfaceHolder` 方法

`SurfaceCreated` 方法（第 410–418 行）在 `SurfaceView` 创建时被调用——例如当应用加载时。我们使用 `SurfaceCreated` 创建并启动 `CannonThread`。`SurfaceDestroyed` 方法（第 421–436 行）在 `SurfaceView` 销毁时被调用——例如当应用终止时。我们使用 `SurfaceDestroyed` 确保 `CannonThread` 停止。首先，第 425 行调用 `setRunning` 为 `false` 以指示线程停止。

```
// surface 变化时调用

@Override

public void surfaceChanged(SurfaceHolder holder, int format, int width, int height) {

    // 通常根据这些变化重绘图形

}

// surface 创建时调用

@Override

public void surfaceCreated(SurfaceHolder holder) {

    if (cannonThread == null) {

        running = true;

        cannonThread = new Thread(this);

        cannonThread.start();

    }

}

// surface 销毁时调用

@Override

public void surfaceDestroyed(SurfaceHolder holder) {

    running = false;

    boolean retry = true;

    while (retry) {

        try {

            cannonThread.join();

            retry = false;

        } catch (InterruptedException e) {

            Log.e(TAG, "Thread interrupted", e);

        }

    }

}
```

图 6.30 | 实现 `View` `stopGame` 和 `releaseResources`。

图 6.31 | 实现 `SurfaceHolder` 方法。（第 1 部分）

## 6.13.14 重写 `View` 方法 `onTouchEvent`

在例例中，我们重写了 `View` `onTouchEvent`（图 6.32）来确定用户何时触摸屏幕。`MotionEvent` 参数包含了发生事件的信息。第 442 行使用 `MotionEvent` 的 `getAction` 方法确定发生了什么种类型的事件。然后第 445–468 行判断用户是触摸了屏幕（`MotionEvent.ACTION_DOWN`）还是在屏幕上滑动（`MotionEvent.ACTION_MOVE`）。在任何情况下，第 448 行都会调用 `cannonView` 的 `alignFireCannonball` 方法将大炮对准并射该点。第 451 行返回 `true` 表示事件已处理。

```
// 当用户在此活动中触摸屏幕时调用

@Override

public boolean onTouchEvent(MotionEvent e) {

    // 获取引起此事件的动作类型

    int action = e.getAction();

    // 用户触摸了屏幕或沿屏幕滑动

    if (action == MotionEvent.ACTION_DOWN ||

        action == MotionEvent.ACTION_MOVE) {

        // 朝向触摸点射出炮弹

        alignFireCannonball(e);

    }

    return true;

}
```

图 6.32 | 重写 `View` 方法 `onTouchEvent`。（第 1 部分，共 2 部分）。

# 第 6 章 大炮游戏 App

```
451 return true;

452 }
```

图 6.32 | 重写 `onTouchEvent` 方法。（第 2 部分，共 2 部分）。

## 6.13.15 `CannonThread`：使用线程创建游戏循环

图 6.63 定义了一个 `Thread` 的子类，用于更新游戏。该线程维持了对 `View` 的 `SurfaceHolder` 的引用（第 456 行）以及一个指示线程是否运行的布尔值。

```
// 控制游戏循环的 Thread 子类

454 private class CannonThread extends Thread {

455 private SurfaceHolder surfaceHolder; // 用于操作画布

456 private boolean isRunning = true; // 默认运行

457

458 // 初始化 surface holder

460 public CannonThread(SurfaceHolder holder) {

461 surfaceHolder = holder;

462 setName('CannonThread');

463 }

464

465 // 改变运行状态

466 public void setRunningRunning(boolean running) {

467 isRunning = running;

468 }

469

470 // 控制游戏循环

471 @Override

472 public void run() {

473 Canvas canvas = null; // 用于绘制

474 long previousFrameTime = System.currentTimeMillis();

475

476 while (isRunning) {

477 try {

478 // 获取此线程独占绘制的 Canvas

479 canvas = surfaceHolder.lockCanvas(null);

480

481 // 锁定 surfaceHolder 用于绘制

482 synchronized(surfaceHolder) {

483 long currentTime = System.currentTimeMillis();

484 double elapsedTime = currentTime - previousFrameTime;

485 totalElapsedTime += elapsedTime; // 更新游戏状态

486 testForCollisions(canvas); // 测试 GameObject 碰撞

488 drawGameElements(canvas); // 使用画布绘制

489 previousFrameTime = currentTime; // 更新上一次时间

490 }

491 }
```

图 6.33 | 内部类 `CannonThread` 管理游戏循环。每隔 `TIME_INTERVAL` 毫秒更新一次游戏元素。（第 1 部分，共 2 部分）。

## 6.13 `CannonView` `SurfaceView` 的子类 253

```
492 finally {

493 // 将画布内容显示在 CannonView 上

494 // 并允许其他线程使用 Canvas

495 if (canvas != null)

496 surfaceHolder.unlockCanvasAndPost(canvas);

497 }

498 

499 }

500 }
```



**图 6.33** 内部类 `CannonThread` 管理游戏循环，每隔 `TIME_INTERVAL` 分钟一次。（第 2 部分，共 2 部分）

类的 `run` 方法（第 471–499 行）绘制逐帧动画——这被称为游戏循环。屏幕上游戏元素的每次更新都是根据自上次更新以来通过的帧数执行的。第 474 行在线程开始时获取当前的毫秒时间。第 476–498 行循环执行直到 `isRunning` 为 `false`。

我们首先通过调用 `SurfaceHolder` 方法 `lockCanvas()` 方法在 `SurfaceView` 上获取画布。一次只能有一帧绘制到 `SurfaceView` 上。为了确保这一点，我们必须通过在同步同步块的表达式中指定它来锁定 `SurfaceHolder`（第 482 行）。接下来，我们获取当前的毫秒时间，然后计算经过的时间并将其加到总时间中——这将有助于在游戏中显示已经过的时间。第 486 行调用 `updatePositions` 方法作为参数移动所有游戏元素。这确保了游戏以设备运行的速度运行。如果帧之间的时间较长（设备较慢），则在显示动画的每一帧时游戏元素将移动得更远。如果时间较短（设备较快），它会调用 `testForCollisions` 来判断炮弹是否与 `Blocker` 或目标碰撞：

- 如果与 `Blocker` 发生碰撞，`testForCollisions` 会移除炮弹速度。
- 如果与 `Target` 发生碰撞，`testForCollisions` 会移除炮弹。

最后，第 489 行调用 `drawElements` 使用 `SurfaceView` 的画布绘制游戏元素，第 489 行将 `currentTime` 存储为 `previousFrameTime`，为准备计算此帧与下一帧之间经过的时间。

## 6.13.16 方法 `hideSystemBars` 和 `showSystemBars`

此应用使用了沉浸式模式——在游戏期间，用户可以看到从屏幕顶部滑出的系统栏。这种沉浸式模式适用于 Android 4.4 或更高版本。因此，`hideSystemBars` 和 `showSystemBars` 方法（图 6.34）首先检查设备的 Android 版本——`Build.VERSION_CODES_KITKAT`——这是 Android 4.4 的常量（API 级别 19）。如果是，两个方法都使用视图方法 `setSystemUIVisibility` 来配置系统栏和应用栏（尽管我们已经通过此应用的主题隐藏了它们）。要将 UI 隐藏系统栏和应用栏进入沉浸式模式，你向 `setSystemUIVibility` 传递在第 505–510 行中通过位或操作符（`|`）组合的常量。要显示系统栏和应用栏，向 `setSystemUIVibility` 传递在第 505–510 行中组合的常量。

```java
// 隐藏系统栏和应用栏
private void hideSystemBars() {
    if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.KITKAT) {
        view.setSystemUIVisibility(View.UI_FLAG_IMMERSIVE_STICK
                | View.UI_FLAG_HIDE_NAVIGATION
                | View.UI_FLAG_HIDE_STATUSBAR
                | View.UI_FLAG_LAYOUT_STABLE);
    }
}

// 显示系统栏和应用栏
private void showSystemBars() {
    if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.KITKAT) {
        view.setSystemUIVisibility(0);
    }
}
```

图 6.34 | 方法 `hideSystemBars` 和 `showSystemBars`。

# 第 6 章 大炮游戏 App

## 6.14 总结

在本章中，你创建了大炮游戏 App，挑战玩家在时间限制结束前摧毁目标。用户通过触摸屏幕发射大炮。为了从单独线程绘制屏幕，你通过扩展 `SurfaceView` 创建了自定义视图。你学习了自定义名称在 XML 元素中必须完全限定。我们展示了额外的 `Fragment` 生命周期方法。你学习了当 `Fragment` 挂起时调用 `onPause`，当 `Fragment` 被销毁时调用 `onDestroy`。你通过重写 `onTouchEvent` 处理触摸。你将音效添加到应用的 `raw` 文件夹并使用 `SoundPool` 进行管理。你还使用了系统的 `AudioManager` 服务设备音量并将其作为播放音量。

此应用通过在单独线程更新 `SurfaceView` 上的游戏元素来手动执行动画。为此，你扩展了 `Thread` 并创建了 `run` 方法，通过调用 `Canvas` 来显示图形。你使用 `SurfaceView` 的 `SurfaceHolder` 获取画布。你还学习了构建一个游戏循环，根据动画帧之间经过的时间来控制游戏，以便游戏在所有设备上以相同的速度运行。最后，你使用了沉浸式模式使应用程序可以使用整个屏幕。

## 7.1 引言

257

## 目录

- 7.1 引言
- 7.2 测试 WeatherViewer 应用程序
- 7.3 技术概览
- 7.3.1 Web 服务
- 7.3.2 JavaScript 对象表示法 (JSON) 和 `org.json` 包
- 7.3.3 `HttpRequest` 连接到 REST Web 服务
- 7.3.4 使用 `AsyncTask` 在 GUI 线程外执行请求
- 7.3.5 `ListView`、`ArrayAdapter` 和 View-Holder 模式
- 7.3.6 `EditTextButton`
- 7.3.7 `TextInputInput`
- 7.3.8 `SnackBar`
- 7.4 构建应用程序的 GUI 和资源文件
- 7.4.1 创建布局
- 7.4.2 `AndroidManifest.xml`
- 7.4.3 `strings.xml`
- 7.4.4 `colors.xml`
- 7.4.5 `activity.xml`
- 7.4.6 `content_main.xml`
- 7.4.7 `list_item.xml`
- 7.5 `Weather` 类
- 7.5.1 `package` 语句、`import` 语句和实例变量
- 7.5.2 构造函数
- 7.5.3 方法 `convertTimestampToDay`
- 7.6 `WeatherAdapter` 类
- 7.6.1 `package` 语句和 `import` 语句
- 7.6.2 嵌套类 `ViewHolder`
- 7.6.3 实例变量和构造函数
- 7.6.4 重写的 `Adapter` 方法 `getView`
- 7.6.5 用于在独立线程中下载图像的 `AsyncTask` 子类
- 7.7 `MainActivity` 类
- 7.7.1 `package` 语句和 `import` 语句
- 7.7.2 实例变量
- 7.7.3 重写的 `Activity` 方法
- 7.7.4 方法 `dismissKeyboard` 和 `onCreate`
- 7.7.5 用于调用 Web 服务的 `AsyncTask` 子类
- 7.7.6 方法 `convertJSONToArrayList`
- 7.8 总结

## 7.1 引言

WeatherViewer 应用程序（图 7-1）使用 OpenWeatherMap org rest 服务来获取特定城市的 16 天天气预报。该程序以 JSON（JavaScript 对象表示法）数据格式接收天气数据。天气数据列表显示在 `ListView` 中，`ListView` 显示了一个可选的项列表。在此应用程序中，你将使用一个自定义列表项：

- 一个天气状况图标
- 星期几以及对该当天天气的文本描述
- 当天的最低温度和最高温度（以 °F 为单位）
- 湿度百分比。

上述项目代表了返回的预报数据的子集。有关 16 天天气预报 API 返回的详细信息，请访问：

```
http://openweathermap.org/forecast16
```

有关 OpenWeatherMap.org 所有数据 API 列表，请访问：

```
http://openweathermap.org/api
```

258 第 7 章 WeatherViewer 应用程序

## 7.2 测试 WeatherViewer 应用程序

### 打开并运行应用程序
打开 Android Studio 并打开书籍示例文件夹中的 WeatherViewer 文件夹。在运行此应用程序之前，你必须添加你的 OpenWeather API 密钥。请参考第 7.3.1 节了解如何获取密钥以及将其放置在项目的哪个位置。在运行应用程序之前需要执行此操作。将 API 密钥添加到项目后，在 AVD 或设备上执行该程序。

### 查看 16 天天气预报
当首次运行时，接收器界面顶部的 `EditText` 允许你输入城市名称（图 7.2）。你应该考虑在城市名后加上逗号和国家代码。在这种情况下，我们输入了 `New York, NY, US` 来定位美国纽约 `New York, NY` 的天气。一旦你输入了城市，触摸带有完成图标的 `FloatingActionButton` 将城市提交给应用程序，程序请求该城市的 16 天天气预报（如图 7.1所示）。

## 7.3 技术概览

本节介绍了构建 WeatherViewer 应用程序将要用的功能。

### 7.3.1 Web 服务
本章介绍了 Web 服务，它促进了应用程序中软件的可移植性和重用性。Web 服务是一种可以通过互联网访问的软件组件。

运行 Web 服务的机器是 Web 服务主机。客户端（在本例中 WeatherViewer 应用程序）向 Web 服务主机发送请求，Web 服务处理请求并向客户端返回响应。分布式计算以多种方式惠及系统。例如，应用程序可以通过 Web 服务按需访问数据，而不是将其存储在设备中。

### 7.3.2 JavaScript 对象表示法 (JSON) 和 `org.json` 包
JavaScript 对象表示法 (JSON) 是表示数据的替代方案。JSON 是一种基于文本的格式，用于将键值对集合表示对象；JSON 是一种简单的格式，易于创建、读取和解析，因为它比 XML 简洁得多，允许程序高效传输数据。每个 JSON 对象表示为包含在大括号中的属性名和值的列表，格式如下：

```
{propertyName1:value1, propertyName2:value2}
```

数组在 JSON 中使用方括号表示：数组元素可以是字符串、JSON 对象、真、假或空。图 7.3 中的 JSON 示例包含了两日的天气数据（第 15-57 行）。

```json
{
  "city": "5128581",
  "name": "New York",
  "coord": {"lon": -74.005966, "lat": 40.714272},
  "country": "US",
  "population": 0,
  "cod": "200",
  "message": 0.0102,
  "cnt": 2,
  "list": [
    {
      "dt": 1442419200,
      "temp": {
        "day": 79.9,
        "min": 71.74,
        "max": 82.53,
        "night": 71.85,
        "eve": 82.55,
        "morn": 71.74
      },
      "pressure": 1037.39,
      "humidity": 64,
      "weather": [
        {
          "id": 800,
          "main": "Clear",
          "description": "sky is clear",
          "icon": "01d"
        }
      ],
      "speed": 0.92,
      "deg": 250,
      "clouds": 0
    },
    {
      "dt": 1442505600,
      "temp": {
        "day": 79.92,
        "min": 66.72,
        "max": 83.1,
        "night": 70.79,
        "eve": 81.99,
        "morn": 66.72
      },
      "pressure": 1032.46,
      "humidity": 62,
      "weather": [
        {
          "id": 800,
          "main": "Clear",
          "description": "sky is clear",
          "icon": "01d"
        }
      ],
      "speed": 1.99,
      "deg": 224,
      "clouds": 0
    }
  ]
}
```

图 7.3 | OpenWeather.org 每日预报服务的示例 JSON。（第一部分，共 2 部分。）

## 第 7 章 WeatherViewer App

```json
{
  "speed": 0.92,
  "deg": 250,
  "clouds": 0
}, { // 第一个数组结束，第二个数组的开始
  "id": 142250600,
  "temp": {
    "day": 79.92,
    "min": 66.72,
    "max": 83.1,
    "night": 70.79,
    "eve": 81.99,
    "morn": 66.72
  },
  "pressure": 1032.46,
  "humidity": 62,
  "weather": {
    "id": 800,
    "main": "Clear",
    "description": "sky is clear",
    "icon": "01d"
  },
  "speed": 1.99,
  "deg": 224,
  "clouds": 0
} // 第二个数组元素结束，数组结束
```



**图 3** 来自 OpenWeatherMap.org 每日预报服务的 JSON 示例。（2 部分中的第 2 部分）

每日预报返回的 JSON 对象中包含许多属性。我们只使用`"list"`属性——这是一个 JSON 对象的数组，代表最多 16 天的预报（默认情况下，除非你另有指定）。每个`"list"`数组包含许多属性，我们使用了其中的：

- `"dt"`—一个长整型，包含日期/时间，表示自 GMT 1970 年 1 月 1 日以来的秒数。我们将其转换为日期。
- `"temp"`—一个包含双精度型（`double`）属性的 JSON 对象，表示温度。我们只使用最低（`"min"`）和最高（`"max"`）温度，但 Web 服务还会返回平均白天（`"day"`）、夜间（`"night"`）、晚上（`"eve"`）和早晨（`"morn"`）的温度。
- `"humidity"`—一个表示湿度百分比的整数（`int`）。
- `"weather"`—一个包含若干属性的 JSON 对象，包括状况的描述（`"description"`）和代表该状况的图标名称（`"icon"`）。

### org.json 包

你将使用 `org.json` 包中的以下类来处理应用接收的 JSON 数据（第 7.7.6 节）：

- `JSONObject`—该类的构造函数之一可以将 JSON 数据字符串转换为 `JSONObject`，该对象包含一个 `Map<String, Object>`，它将 JSON 键映射到对应的值。你可以在代码中使用 `JSONObject` 的 `get` 方法来访问 JSON 属性，这允许你将 JSON 键的值作为 `JSONObject`、`JSONArray`、`Object`、`boolean`、`int`、`long` 或 `String` 任意类型之一获取。
- `JSONArray`—此类表示 JSON 数组，并提供了访问元素的方法。OpenWeather.org 响应中的`"List"`将以 `JSONArray` 的形式递送。

### 7.3.3 使用 HttpConnection 调用 REST 服务

为了调用 OpenWeather.org 每日预报服务，你需要将 Web 服务器的 URL 转换为`URL`对象，然后使用该 URL 打开一个`HttpURLConnectionConnection`（第 7.7.5 节）。这将向 Web 服务发送 HTTP 请求。为了接收 JSON 响应，你需要从 `HttpConnection` 的输入流（`InputStream`）中读取所有数据并将其放入 `String` 中。我们将向你如何将其转换为 `JSONObject` 进行处理。

### 7.3.4 使用 AsyncTask 在 GUI 线程外执行网络请求

你应该在 GUI 线程之外执行会阻塞执行直到完成的长耗操作（例如：网络、文件和数据库访问）。这有助于提高主应用的响应性，并避免当 Android 的 GUI 线程无响应时出现“应用未响应”（ANR）对话框。回想第 6 章，用户界面的更新必须在 GUI 线程中执行，因为 GUI 组件不是线程安全的。

为了执行在 GUI 中更新结果的长耗任务，Android 提供了`AsyncTask`类（包 `android.os`），它在另一个线程中执行长耗操作并将结果传递给 GUI。创建和操作线程的细节由`AsyncTask`类为你处理，即将结果从 `AsyncTask` 通信到 GUI 线程。在本应用中使用`AsyncTask`子类——一个将调用 OpenWeather.org Web 服务，另一个将下载图标。

### 7.3.5 ListView, ArrayAdapter 和 View-Holder 模式

本应用在 `ListView`（包 `android.widget`）中显示数据——这是一个可滚的列表项。`ListView` 是 `Adapter`（包 `android.widget`）的子类，通过 `Adapter` 对象（包 `android.widget`）从数据源呈现视图数据。在本应用中，我们使用 `ArrayAdapter`（包 `android.widget`）的子类来创建一个填充 `ListView` 的适配器，使用数据源数据（节 7.6）。当应用用天气数据更新 `ArrayAdapter` 时，我们将调用`notifyDataSetChanged()`来指示底层数据已更改。适配器通知 `ListView` 更新其显示列表。这被称为数据绑定。多种类型的 `Adapter` 可以通过 `Adapter` 将数据绑定到 `ListView`。在第 9 章，你将学习如何将数据库绑定到 `ListView`。关于 Android 数据绑定的更多信息和教程，请访问：

```
http://developer.android.com/guide/topics/ui/binding
```

## 第 7 章 WeatherViewer App

### View-Holder 模式

默认情况下，`ListView` 显示一个两个视图。在本应用中，我们使用 `ArrayAdapter` 的子类创建一个填充 `ListView` 的适配器，使用数据源数据（节 7.6）。当应用用天气数据更新 `ArrayAdapter` 时，我们将调用`notifyDataSetChanged()`来指示底层数据已更改。适配器通知 `ListView` 更新其显示列表。这被称为数据绑定。多种类型的 `Adapter` 可以通过 `Adapter` 将数据绑定到 `ListView`。在第 9 章，你将学习如何将数据库绑定到 `ListView`。关于 Android 数据绑定的更多信息和教程，请访问：

```
http://developer.android.com/guide/topics/ui/binding
```

## 7.3 技术概述

### 7.3.3 HttpConnection 调用 REST 服务

为了调用 OpenWeather.org 每日预报服务，你需要将 Web 服务器的 URL 转换为`URL`对象，然后使用该 URL 打开一个`HttpURLConnectionConnection`（节 7.7.5）。这将向 Web 服务发送 HTTP 请求。为了接收 JSON 响应，你需要从 `HttpConnection` 的输入流中读取所有数据并将其放入 `String` 中。我们将向你如何将其转换为 `JSONObject` 进行处理。

### 7.3.4 使用 AsyncTask 在 GUI 线程外执行网络请求

你应该在 GUI 线程之外执行会阻塞执行直到完成的长耗操作（例如：网络、文件和数据库访问）。这有助于提高主应用的响应性，并避免当 Android 的 GUI 线程无响应时出现“应用未响应”（ANR）对话框。回想第 6 章，用户界面的更新必须在 GUI 线程中执行，因为 GUI 组件不是线程安全的。

为了在 GUI 中更新结果的长耗任务，Android 提供了`AsyncTask`类（包 `android.os`），它在另一个线程中执行长耗操作并将结果传递给 GUI。创建和操作线程的细节由`AsyncTask`类为你处理，即将结果从 `AsyncTask` 通信到 GUI 线程。在本应用中使用`AsyncTask`子类——一个将调用 OpenWeather.org Web 服务（节 7.7.5），另一个将下载图标（节 7.6）。

### 7.3.5 ListView, ArrayAdapter 和 View-Holder 模式

本应用在 `ListView`（包 `android.widget`）中显示数据——这是一个可滚的列表项。`ListView` 是 `Adapter`（包 `android.widget`）的子类，通过 `Adapter` 对象（包 `android.widget`）从数据源呈现视图数据。在本应用中，我们使用 `ArrayAdapter`（包 `android.widget`）的子类来创建一个填充 `ListView` 的适配器，使用数据源数据（节 7.6）。当应用用天气数据更新 `ArrayAdapter` 时，我们将调用`notifyDataSetChanged()`来指示底层数据已更改。适配器通知 `ListView` 更新其显示列表。这被称为数据绑定。多种类型的 `Adapter` 可以通过 `Adapter` 将数据绑定到 `ListView`。在第 9 章，你将学习如何将数据库绑定到 `ListView`。关于 Android 数据绑定的更多信息和教程，请访问：

```
http://developer.android.com/guide/topics/ui/binding
```

## 7.4 构建应用的 GUI 和资源文件

### 7.4.1 创建项目

使用 Blank Activity 模板创建一个新项目。在 Create New Project 对话框的 New Project 设置中，指定：

- 应用名称：WeatherViewer
- 公司名称：com.example（或指定你的域名）

对于 Create New Project 对话框中的剩余步骤，使用与第 2.3 节相同的设置。按照 2.5.2 节的步骤为项目添加图标。此外，按照 4.4.3 节的步骤为项目配置 Java SE。

### 7.4.2 AndroidManifest.xml

WeatherViewer 设计为竖屏方向。按照第 3.7 节执行的步骤将`android:screenOrientation`设置为`portrait`。此外，在`<application>`元素之前的`<manifest>`元素中添加互联网访问权限：

```xml
<uses-permission android:name="android.permission.INTERNET" />
```

这允许应用访问互联网，这是调用 Web 服务所需要的。

### 7.3.7 TextInputLayout

在本应用中，你将使用 `EditText` 让用户输入你想要获取天气预报的城市。为了帮助用户理解 `EditText` 的目的，你可以提供提示文本，在 `EditText` 为空时显示。一旦用户开始输入，提示文本就会消失——可能导致用户忘记 `EditText` 的目的。
Android 支持库的`TextInputLayout`（包 `design.widget`）解决了这个问题。当 `EditText` 获得焦点时，`TextInputLayout` 会将提示文本从原始大小缩小到显示在 `EditText` 上方的尺寸。在本应用中，`EditText` 在应用开始执行时获得焦点，因此 `TextInputLayout` 立即移动到 `EditText` 上方。

## 第 7 章 WeatherViewer 应用

当今应用中的心理能力。在 Android 6.0 中，根据 Google 的说法，“对用户隐私或安全不友好”的 Internet 权限以及许多其他权限——这些权限在安装时会自动授予——被归类为 PROTECTION_NORMAL。要查看此类权限的完整列表，请访问：

```
https://developer.android.com/preview/features/permissions.html#best-practices
```

Android 不会要求用户授予权限，用户无法从应用中撤销权限。因此，代码不需要检查应用是否已获得特定的 PROTECTION_NORMAL 权限。然而，为了与早期的 Android 版本向后兼容，你仍然必须在 `AndroidManifest.xml` 中请求这些权限。

## 7.4.3 strings.xml

双击 `res/values` 文件夹中的 `strings.xml`，然后点击“Open editor”（打开编辑器）以运行翻译编辑器（Translations Editor），并创建图 7.4 所示的字符串资源。

| Key（键） | Value（值） |
| --- | --- |
| api_key | 使用你自己的 OpenWeather.org API 密钥作为此资源的值。 |
| web_service_url | http://api.openweathermap.org/data/2.5/forecast/daily?q= |
| invalid_url | 无效 URL |
| weather_condition_image | 天气状况的图形表示 |
| high_temp | 高温: % |
| low_temp | 低温: % |
| day_description | %s 天 |
| humidity | 湿度: % |
| hint_text | 输入城市（例如，Boston, MA, US） |
| read_error | 无法读取天气数据 |
| connect_error | 无法连接到 OpenWeatherMap |

图 7.4 WeatherViewer 应用中使用的字符串资源。

## 7.4.4 colors.xml

Android Studio 的 Activity 模板自定义了应用的主色（primary colors）和强调色（accent colors）。在本应用中，我们在 `colors.xml` 中将模板的强调色（`colorAccent`）更改为清晰的蓝色（十六进制 `#4AA8AF`）。

## 7.4.5 activity_main.xml

Android Studio 的 Activity 模板将 `MainActivity` 的 GUI 拆分为两个文件：

- `activity_main.xml` 定义了 `Toolbar`（`AppCompatActivity` 中应用栏的替代品）和一个悬浮按钮（`FloatingActionButton`），它默认位于右下角。
- `content_main.xml` 文件定义了 `MainActivity` GUI 的其余部分，并通过`<include>`元素包含在 `activity_main.xml` 文件中。

## 7.4 构建应用的 GUI 和资源文件

对此应用的 `activity_main.xml` 进行以下更改：

1. 为 `CoordinatorLayout` 添加`id="@+id/coordinatorLayout"`——你将使用它来指定显示 `Snackbar` 的布局。
2. 通过 Vector Asset Studio（如你在第 4.9 节中所做的那样）向项目添加 Material Design 检查（✓）按钮，使用此新信息用于预定义的`FloatingActionButtonsrc`属性。
3. 编辑布局的 XML 以配置若干无法通过属性窗口（Properties window）访问的`FloatingActionButton`属性。将`layout_gravity`从底部（bottom）更改为顶部（top），以便悬浮按钮出现在用户界面顶部。
4. 要将按钮移动到右边缘，定义一个名为`fab_margin_top`的新资源，值为 `90dp`。使用该资源以及 Blank Activity 模板中的`fab_margin`资源来定义悬浮按钮：

```
android:layout_margintop="@dim/fab_margin_top"
android:layout_marginend="@dim/fab_margin"
android:layout_marginBottom="@dim/fab_margin"
android:layout_marginStart="@dim/fab_margin"
```



## 第 7 章 WeatherViewer 应用程序

### 7.4.6 `content_main.xml`

此布局包含在`activity_main.xml`中，并定义了`MainActivity`的主要 UI 组。执行以下步骤：

- 1. 移除 Blank Activity 默认的`TextView`，并将`RelativeLayout`更改为`LinearLayout`。
- 2. 接下来插入`EditText`。在编辑器的 Design 视图中点击 Custom。在出的对话框中输入`EditText`——搜索 UI 组件列表。IDE 高亮了`EditText`，点击 OK，在组件树中点击`LinearLayout`将`EditText`作为嵌套布局。
- 3. 要布局中添加`EditText`，切换到布局的 Editor 视图，将`EditText`元素的自合标签`/>`改为`>`；在`>`右侧放置光标，按回车并输入`/`。IDE 将自动补全标签。在`EditText`的起始和结束标签之间输入`<EditText`。IDE 将显示`EditText`的自动补全窗口，将其`layout_width`设置为`match_parent`，`layout_height`设置为`wrap_content`。在 Design 视图中，选择`EditText`的 ID `EditText`，勾选其`singleLine`属性，并将`hint`属性设置为字符串资源`hint_text`。
- 4. 为了完成布局，将`ListView`拖入`LinearLayout`中。将其`layout_width`设置为`match_parent`，`layout_height`设置为`0dp`，`layout_weight`设置为`1`，并将`id`设置为`ListView`。记住，对于使用 lay-weight 确定 View 高度，IDE 建议`layout_height`值为`0dp`。
- 5. 最后，移除 Blank Activity 模板预定义的悬浮按钮的`layout_margin`。

### 7.4.7 `list_item.xml`

现在我们要把`list_item.xml`添加到布局并选择`list_item.xml`。

### 7.5 Weather 类

此应用由三个类组成，这些类将在 7.5-7.7 节中讨论：

- `Weather`类（本节）代表一天的天气数据。`MainActivity`类将 JSON 天气数据转换为`ArrayList<Weather>`。
- `WeatherAdapter`类（7.6 节）定义了一个自定义`ArrayAdapter`，用于将`ArrayList<Weather>`绑定到`MainActivity`的`ListView`中。`ListView`项目从 0 开始索引，每个`ListView`的嵌套视图根据`Array<Weather>`中相同索引的`Weather`对象进行填充。
- `MainActivity`类（7.7 节）定义了用户界面和逻辑，与 OpenWeatherMap.org 每日预报 Web 服务交互并处理 JSON 响应。

在本节中，我们将关注`Weather`类。

#### 7.5.1 package 语句、import 语句和实例变量

图 7.6 包含了 package 语句、import 语句以及`Weather`类的实例变量。你将使用来自`java.text`和`java.util`包（5–8 行）的类，将每天的时间戳转换为当天的名称（周一、周二等）。实例变量被声明为`final`，因为它们在初始化后就不需要被修改。我们还将将它们设为`public`——请记住 Java String 是不可变的，尽管实例变量是`public`的，但它们的值无法无法改变。

```java
// Weather.java
// 维护一天的天气信息

package com.deitel.weatherviewier;

import java.text.NumberFormat;
import java.text.SimpleDateFormat;
import java.util.Calendar;
import java.util.TimeZone;

class Weather {
    public final String minTemp;
    public final String maxTemp;
    public final String humidity;
    public final String description;
    public final String icon;
```

**图 7.6** | `Weather`类语句、import 语句和实例变量。

#### 7.5.2 构造函数

构造函数（图 7.7）初始化了类的实例变量：

- `NumberFormat`对象从数值创建字符串。第 22–23 行配置该对象将浮点值舍入为数字。
- 第 25 行调用支持每个本地方法的`timestampToday`（第 7.5.3 节）来获取字符串名称并初始化`dayof`。
- 第 26–27 行使用最小和最大温度值作为整数；我们在每个格式化后的字符串末尾附加 "F"，因为我们将请求华氏度——Unicode 编码序列`\u00B0`代表度符号（°）。WeatherMapper-API 同时支持华氏度缘摄氏度温度格式。
- 第 28–29 行获取用于特定本地化百分比格式化的`NumberFormat`，然后使用它来格式化湿度百分比。网络服务返回此整数，因此我们除以 100.0 进行格式化——在美国本地设置中，1.0 被格式化为 100%，0.5 被格式化为 50%，依此类推。
- 第 30 行初始化天气状况描述。
- 第 31–32 行创建一个代表当天天气状况图像的 URL 字符串——这将用于下载图像。

```java
// constructor
public Weather(Long timestamp, double minTemp, double maxTemp,
    double humidity, String description, String iconName) {

    // NumberFormat 将 double 类型的温度格式化为整数
    NumberFormat numberFormat = NumberFormat.getInstance();
    numberFormat.setMaximumDigits(0);

    this.dayOfWeek = convertTimestampToToday(timestamp);
    this.minTemp = numberFormat.format(minTemp) + " \u00B0"
    this.maxTemp = numberFormat.format(maxTemp) + " \u00B0"
    this.humidity = NumberFormat.getInstance().format(humidity / 100.0);
    this.description = description;
    this.iconURL = "http://openopenweathermap.org/img/w/" + iconName + ".png";
}
```

**图 7.7** | `Weather`类构造函数。

#### 7.5.3 方法 `convertTimestampToDay`

工具方法`convertTimestampToDay`（图 7.8）接收一个表示自 GMT 1970 年 1 月 1 日以来秒数的 long 值作为参数——这是 Linux 系统上的标准表示方式（Android 基于 Linux）。要执行转换：

- 第 37 行创建了一个`Calendar`对象用于处理日期和时间，然后第 38 行调用`setInMillis`方法使用`timestamp`参数设置时间。时间戳单位是秒，因此乘以 10000 将其转换为毫秒。
- 第 39 行给出默认的`TimeZone`对象，我们用它根据设备的时区（第 42–43 行）来调整时间。
- 第 46 行创建一个`SimpleDateFormat`来格式化`Date`对象。参数 "EEEE" 将`Date`格式化为日期名称（周一、周二等）。要查看完整的格式列表，请访问：

http://developer.android.com/reference/java/text/SimpleDateFormat.format

- 第 47 行格式化并返回日期。`Calendar`的`getTime`返回一个包含时间的`Date`对象。该`Date`被传递给`SimpleDateFormat`的`format`方法以获取日期。

```java
// 将时间戳转换为日期 (...)
private static String convertTimestampToDay(long timestamp) {
    Calendar calendar = Calendar.getInstance(); // 创建 Calendar
    calendar.setTimeInMillis(timestamp * 1000); // 设置时间
    TimeZone tz = TimeZone.getDefault(); // 获取设备时区
```

**图 7.8** | `Weather`方法`convertTimestampToDay`。（2 部分中的第 1 部分）。

```java
// 为设备时区调整时间
calendar.add(Calendar.MILLISECONDS);
tz.setOffset(Calendar.getTimeInMillis(millis));

// // 返回日期名称的 SimpleDateFormat
SimpleDateFormat formatter = new SimpleDateFormat("EEEE");
return formatter.format(calendar.getTime());
```

图 7.8 | `Weather`方法`convertTimestampToToday`。（2 部分中的第 2 部分。）

### 7.6 类 `WeatherArrayAdapter`

`WeatherArrayAdapter`类定义了`ArrayAdapter`的子类，用于将 Array-list 绑定到`ListView`。

#### 7.6.1 package 语句和 import

图 7.9 包含了`WeatherArrayAdapter`的 package 语句。我们会在遇到时导入这些类型。图 7.9 包含了`WeatherArrayAdapter`的 package 语句。为了布局我们扩展了`ArrayAdapter`（第 23 行）。

```java
// WeatherArrayAdapter.java
// 用于显示 List<Weather> 的 ArrayAdapter

package com.example.weatherview;

import android.content.Context;
import android.graphics.Bitmap;
import android.graphics.BitmapFactory;
import android.os.AsyncTask;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.ArrayAdapter;
import android.widget.ImageView;
import android.widget.TextView;

import java.io.InputStream;
import java.net.HttpURLConnection;
import java.net.URL;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

class WeatherArrayAdapter extends ArrayAdapter<Weather> {
```

**图 7.9** | `WeatherArrayAdapter`类语句和 import 语句。

#### 7.6.2 嵌套类 `ViewHolder`

嵌套类`ViewHolder`（图 10）定义了类直接访问的实例变量。当创建`ListView`项时，我们会创建一个新的`ViewHolder`对象。如果复用现有项，我们将获取该项的`ViewHolder`。

```java
// 当列表项滑出时复用视图
private static class ViewHolder {
    ImageView contentView;
    TextView lowTextView;
    TextView highTextView;
    TextView humidityTextView;
}
```

**图 7.10** | 嵌套类`ViewHolder`。

#### 7.6.3 实例变量和构造函数

11 定义了类实例变量和构造函数。我们使用实例变量`bitmaps`（第 34 行）——一个`Map<String, Bitmap>`来缓存已加载的天气状况，这样在用户滚动天气预报时不需要重新加载。缓存图像保留在内存中直到 Android 终止。构造函数（第 37–39 行）调用父类的三参数构造函数，将`Context`（显示`ListView`的活动）和`List`（数据列表）作为第一个和第二个参数。父类构造函数代表布局的资源 ID，该布局包含一个用于显示每个`ListView`项数据的`TextView`。参数 -1 表示我们使用自定义布局来显示多个`TextView`。

```java
// 用于可复用的已下载 Bitmaps
private Map<String, Bitmap> bitmaps = new HashMap<>();

// 初始化父类继承成员的构造函数
public WeatherArrayAdapter(Context context, List<Weather> forecast) {
    super(context, -1, forecast);
}
```

**图 7.11** | `WeatherArrayAdapter`类实例变量和构造函数。

#### 7.6.4 重写的 `ArrayAdapter`方法

`getItem`（第 7.12 行）被调用以获取显示`ListView`项的数据。重写此方法允许我们把数据映射到自定义的`ListView`项。该方法接收`ListView`项的位置、代表该项的`View` (`convertView`) 以及`ListView`父容器作为参数。通过操作`convertView`，你可以自定义`ListView`项的内容。第 45 行调用继承的`ArrayAdapter getItem`以从`List<Weather>`中获取将显示的`Weather`对象。

第 47 行定义了`ViewHolder`变量，它将被设置为一个新的`ViewHolder`对象或现有对象，取决于方法`getView`的`convertView`参数是否为`null`。

```java
// 为 ListView 项创建自定义视图
@Override
public View getView(int position, View convertView, ViewGroup parent) {
    // 获取此指定 ListView 位置的 Weather 对象
    Weather day = getItem(position);

    ViewHolder viewHolder; // 引用列表项视图的对象

    // 检查是否有滚动出屏幕的列表项的可重用 ViewHolder
    // 如果 (convertView == null) { // 没有可重用的 ViewHolder，因此创建一个
    if (convertView == null) {
        viewHolder = new ViewHolder();
        LayoutInflater inflater = LayoutInflater.from(getContext());
        convertView = inflater.inflate(R.layout.list_item, parent, false);
    } else {
        viewHolder = (ViewHolder) convertView;
    }

    viewHolder.conditionImageView = convertView.findViewById(R.id.conditionImageView);
    viewHolder.dayText = convertView.findViewById(R.id.dayText);
    viewHolder.conditionText = convertView.findViewById(R.id.conditionText);
    viewHolder.humidityText = convertView.findViewById(R.id.humidityText);
    viewHolder.temperatureText = convertView.findViewById(R.id.temperatureText);

    convertView.setTag(viewHolder);
    } else {
```



// 重用存储在列表项 tag 的现有 ViewHolder

`viewHolder = (ViewHolder) convertView.getTag();`

// 如果天气图标已经下载，则使用它

`if (bitmaps.containsKey(day.iconURL())) {`

`viewHolder.conditionImageView.setImageBitmap(bitmaps.get(day.iconURL()));`

`} else {`

// 在单独线程中下载图标

`new ImageTask(viewHolder.conditionImageView).execute(day.iconURL());`

`}`

// 从 Weather 对象中获取其他数据并放入视图中

`Context context = getContext();` // 用于加载 String 资源
`viewHolder.dayText.setText(context.getString(R.string.day_of_week, day.dayOfWeek));`
`viewHolder.lowTempText.setText(context.getString(R.string.low_temp, day.minTemp));`

`return convertView;`

图 7.12 重写的 `ArrayAdapter` 方法 `getView`。（部分 1，共 2 部分。）

## 7.6 类 WeatherArrayAdapter

```
viewHolder.textView.setText(
  context.getString(R.string.high_temp, day.maxTemperature));
viewHolder.humidityTextView.setText(
  context.getString(R.string.humidity, day.humidity));

return convertView(); // 返回完成的列表项以显示
```

**图 7.12** | 重写的 `ArrayAdapter` 方法 `getView`。（部分 2，共 2 部分。）

如果 `convertView` 为 `null`，第 52 行创建一个新的 `ViewHolder` 对象，以存储对新列表项视图的引用。接下来，第 53 行获取 `Context` 的 `LayoutInflater`，我们在第 54-55 行中使用它来填充列表项的视图。第一个参数是待填充的布局（`R.layout.list_item`），第二个是视图将附加的父 `ViewGroup`，最后一个是指示是否应自动附加视图的布尔值。第三个参数为 `false`，因为 `ListView` 调用 `getView` 方法获取项视图，然后将其附加到 `ListView` 上。第 56-65 行引用新填充的列表和 `ViewHolder` 的实例变量。然后第 66 行获取新的 `ViewHolder` 对象作为 `ListView` 的 `tag`，以便将 `ViewHolder` 与列表项一起存储供以后使用。

如果 `convertView` 不为 `null`，我们正在重用滚动出屏幕的列表项视图。在这种情况下，第 69 行获取当前列表项的 `tag`，它是之前附加到该列表项的 `ViewHolder`。

获取 `ViewHolder` 后，第 74-93 行获取列表项项目的数据。第 74-82 行判断天气条件对象是否包含天气图标 `iconURL` 的键。如果是，则第 75-76 行从 map 中获取 `Bitmap` 并设置 `conditionImage` 的图像。否则，第 80-81 行创建一个新的 `ImageTask`（第 7.6.5 节）在单独线程中下载图像。任务的 `execute` 方法接收 `iconURL` 并初始化任务。第 86-93 行获取列表项文本的 `String`。最后，第 95 行返回配置好的列表项视图。

## 软件工程观察 7.1

## 7.6.5 用于在单独线程下载图像的 AsyncTask 子类

嵌套类 `AsyncTask`（图 7.13）继承 `AsyncTask` 并定义了如何在单独线程中下载天气图像，然后将图像返回给列表项的 `ImageView`。

```
// 在单独线程中加载天气图标
private class LoadImageTask extends AsyncTask<String, Void, Bitmap> {
  private ImageView imageView; // 显示缩略图
```

图 7.13 用于单独线程下载图像的 `AsyncTask` 子类。（部分 1，共 2 部分。）

```
// 设置下载的 Bitmap 的 ImageView
public LoadImageTask(ImageView imageView) {
    this.imageView = imageView;
}

// load(params[]) 是图像的 String URL
@Override
protected Bitmap doInBackground(String... params) {
    Bitmap bitmap = null;
    HttpConnection connection = null;

    try {
        URL url = new URL(params[0]); // 为图像创建 URL

        // 打开 HttpConnection，获取其 InputStream
        // 并下载图像
        connection = (HttpConnection)url.openConnection();

        InputStream inputStream = connection.getInputStream();
        bitmap = BitmapFactory.decodeStream(inputStream);
        bitmap.put(params[0], bitmap); // 缓存供以后使用
    }
    catch (Exception e) {
        e.printStackTrace();
    } finally {
        connection.disconnect();
    }

    return bitmap;
}

// 在列表项中设置图像
@Override
protected void onPostExecute(Bitmap bitmap) {
    imageView.setImageBitmap(bitmap);
}
```

# 278 第 7 章 WeatherViewer 应用程序

```
import android.content.Context;
import android.os.AsyncTask;
import android.os.Bundle;
import android.support.design.widget.FloatingActionButton;
import android.support.design.widget.Snackbar;
import android.support.v7.app.AppCompatActivity;
import android.support.v7.widget.Toolbar;
import android.view.View;
import android.view.inputmethod.InputMethodManager;
import android.widget.EditText;
import android.widget.ListView;
import org.json.JSONArray;
import org.json.JSONException;
import org.json.JSONObject;
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.net.HttpURLConnection; // 已从 HTTP 修复
import java.net.URL;
import java.util.ArrayList;
import java.util.List;
```

**图 7.14** | `MainActivity` 的包语句和导入语句。（2 部分中的第 2 部分）

## 7.7.2 实例变量

`MainActivity` 类（图 7.15）继承自 `AppCompatActivity`，并定义了三个实例变量：

- `weatherList`（第 32 行）是一个 `ArrayList<Weather>`，它用于存储代表每日预报中一天的 `Weather` 对象。
- `weatherArrayAdapter` 将指向一个 `weatherArrayAdapter` 对象（第 7.6 节），该对象将天气数据绑定到 `ListView` 的项。
- `weatherListView` 将指向 `MainActivity` 的 `ListView`。

```
public class MainActivity extends AppCompatActivity {
  // 代表预报的 Weather 对象列表
  private List<Weather> weatherList = new ArrayList<Weather>();

  // 用于将 Weather 对象绑定到 ListView 的 weatherArrayAdapter
  private WeatherArrayAdapter weatherArrayAdapter;
  private ListView weatherListView; // 显示天气信息
```

**图 7.15** | `MainActivity` 实例变量。

## 7.7 MainActivity 类 279

## 7.7.3 重写方法 onCreate

重写的 `onCreate`（图 7.15）配置 `MainActivity` 的 GUI。第 41–45 行是你在创建此项目时选择“空模板”由 Android 生成的。这些行用于加载 GUI、应用的 `Toolbar`，并将 `Toolbar` 挂载到活动中。请记住，`AppCompat` 必须提供自己的 `Toolbar`，因为早期版本的 Android 不支持栏（以前称为 action bars）。

第 48–50 行配置了 `weatherListView` 的适配器——在这种情况下，它是 `ArrayAdapter` 子类 `WeatherAdapter` 的对象。`List` 方法 `setAdapter` 将 `WeatherAdapter` 连接到 `ListView`，以便填充列表的项。

```
// 配置 Toolbar, ListView 和 FAB
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    // 自动生成的用于加载布局和配置 Toolbar的代码
    setContentView(R.layout.activity_main);
    Toolbar toolbar = (Toolbar) findViewById(R.id.toolbar);
    setSupportActionBar(toolbar);

    // 创建 WeatherAdapter 将 weatherlist 绑定到 weatherListView
    weatherListView = (ListView) findViewById(R.id.weatherListView);
    weatherAdapter = new WeatherAdapter(this, weatherList);
    weatherListView.setAdapter(weatherAdapter);

    // 配置 FAB 以隐藏键盘并启动网络服务请求
    FloatingActionButton fab = (FloatingActionButton) findViewById(R.id.fab);
    fab.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View view) {
            // 从 EditText 获取文本并创建网络服务 URL
            EditText locationEditText = (EditText) findViewById(R.id.locationEditText);
            // (EditText) text
            URL url = new URL(locationEditText.getText().toString());

            // 隐藏键盘并启动 GetTask 在单独线程中
            // 从 OpenWeatherMap.org 下载天气数据
            if (url != null) {
                dismissKeyboard(locationEditText);
                GetTask localWeatherTask = new GetWeatherTask();
                localWeatherTask.execute(url);
            } else {
                Snackbar.make(findViewById(R.id.coordinatorLayout),
                    R.string.invalid_url, Snackbar.LENGTH_LONG).show();
            }
        }
    });
}
```

图 7.16 | 重写的 activity 方法。

# 7 WeatherViewer 应用程序

第 53–75 行配置 `FloatingActionButton`。`onClick` 监听器是由 Android Studio 生成的，我们实现了它的方法体。第 61 行获取 `EditText` 的引用。如果 URL 创建成功，第 66 行调用 `GetTask` 在单独线程中获取天气预报。第 71–72 行显示 URL 无效。如果 URL 未创建，则通过 `Snackbar` 提示。

## 7.7.4 方法 dismissKeyboard 和 createURL

图 7.17 显示 `MainActivity` 方法。第 79–83 行在用户触摸 `FloatingActionButton` 时调用 `dismissKeyboard`。第 82 行使用 `EditText` 的引用隐藏键盘。

```
// 程序化隐藏键盘
private void dismissKeyboard(View view) {
    InputMethodManager imm = (InputMethodManager)
        getSystemService(Context.INPUT_SERVICE);
    imm.hideInputFromWindow(view.getWindowToken(), 0);
}

// 为城市创建 URL
private URL createURL(String city) {
    String apiKey = getString(R.string.api_key);
    String baseUrl = getString(R.string.service_url);
    try {
        String urlString = baseUrl + URLEncoder.encode(city, "UTF-8")
            + "&appid=" + apiKey;
        return new URL(urlString);
    } catch (Exception e) {
        e.printStackTrace();
    }
    return null;
}
```



图 7.17 | `MainActivity`方法和`createURL`。

## 7.7 `MainActivity`类 281

第 86–101 行组合 URL 的字符串表示。在第 93 行，我们添加网络服务查询参数。`units`参数可以是华制（华）、公制（摄氏）或标准（开尔文）如果不包含`units`参数，默认为标准。`cnt`参数指定预报中包含多少天。最大值为 16，默认值为 7。最后`APPID`参数是你的`OpenWeatherMap.org` API 密钥，我们加载到字符串中。默认情况下结果以 JSON 格式返回，但你可以添加`mode`参数为 XML 或 HTML，分别从网页接收 XML 数据。

## 7.7.5 调用服务的`AsyncTask`子类

嵌套`AsyncTask`子类`GetTask`（图 7.18）执行网络服务请求并在单独线程中处理响应，然后将天气信息作为`JSONObject`传递给 UI 线程。

```java
// 调用 REST 服务以获取天气数据
// 将数据保存到本地文件
private class GetWeatherTask extends AsyncTask<Void, JSONObject> {
    @Override
    protected JSONObject doInBackground(URL... params) {
        HttpURLConnection connection = null;
        try {
            connection = (HttpURLConnection) params[0].openConnection();
            int response = connection.getResponseCode();
            if (response == HttpURLConnection.HTTP_OK) {
                StringBuilder builder = new StringBuilder();
                try (BufferedReader reader = new BufferedReader(
                        new InputStreamReader(connection.getInputStream()))) {
                    String line;
                    while ((line = reader.readLine()) != null) {
                        builder.append(line);
                    }
                } catch (IOException e) {
                    Snackbar.make(findViewById(R.id.coordinatorLayout),
                        R.string.read_error, Snackbar.LENGTH_LONG).show();
                    e.printStackTrace();
                }
                // 解析逻辑将在此此处
            }
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (connection != null) {
                connection.disconnect();
            }
        }
        return null;
    }
}
```

图 7.18 | 调用服务的`AsyncTask`子类。（2 部分中的第 1 部分。）

## 282 第 7 章 WeatherViewer 应用程序

```java
      return new JSONObject(builder.toString());
  }
  else {
    Snackbar.make(findViewById(R.id.coordinatorLayout),
        R.string.connect_error, Snackbar.LENGTH_LONG).show();
  }
  catch (Exception e) {
    Snackbar.make(findViewById(R.id.coordinatorLayout),
        R.string.connect_error, Snackbar.LENGTH_LONG).show();
    e.printStackTrace();
  }
  finally {
    connection.disconnect(); // 关闭 HttpUrlConnection
  }
  return null;
}

// 处理 JSON 响应并更新 ListView
@Override
  protected void onPostExecute(JSONObject weather) {
    convertJsonToArray(weatherList); // 重新填充 weatherList
    weatherArrayAdapter.notifyDataSetChanged(); // 重新绑定 ListView
    listView.smoothScrollToPosition(0); // 滚动到顶部
```

图 7.18 | 用于调用 Web `AsyncTask`子类。（2 部分中的 2 部分）

对于`GetWeatherTask`类，泛型类型参数为：

- `URL`：`AsyncTask`的`doInBackground`方法的长度参数列表类型（第 108–151 行——Web 服务请求的 URL 作为唯一参数传递给`GetWeatherTask`的`execute`方法。
- `Void`：`onProgressUpdate`的长度参数列表类型——同样，我们没有使用此方法。
- `JSONObject`：任务结果的类型，该结果被传递给`onPostExecute`（154–159 行），用于在 GUI 中显示结果。

`doInBackground`中的第 113 行创建了用于调用 REST 服务的`HttpURLConnection`。在第 7.6 节中，打开连接会发送请求。第 114 行从 Web 服务器获取响应码。如果响应码为`HttpURLConnection.OK`，则说明 REST 服务已正确正确调用，并且有响应需要处理。在这种情况下，第 119–126 行获取`HttpURLConnection`的`InputStream`，将其封装在`BufferedReader`中，读取响应的每行，并将其附加到`StringBuilder`中。然后，第 134 行将`StringBuilder`中的 JSON 字符串转换为`JSONObject`并将其返回给 GUI 线程。第 147 行断开`HttpURLConnection`。
如果在读取天气数据或连接 Web 服务时发生错误，第 129–130 行、137–138 行和 142–143 行将显示`Snackbar`以指示发生的问题。

## 7.7 `MainActivity`类 283

如果设备在请求过程中丢失网络连接，或者设备根本没有网络访问，可能会出现这些问题——例如，设备处于飞行模式。

当在 GUI 线程中调用`PostExecute`时，第 156 行调用`convertJSONToArrayList`方法（第 7.7.6 节）从`JSONObject`中提取数据并放入`weatherList`中。第 157 行调用`ArrayAdapter`的`notifyDataSetChanged`方法，这会导致`weatherListView`使用新数据更新。第 158 行调用`ListView`方法`smoothScrollToPosition`，将`ListView`的第一个项目重新定位在列表顶部——这确保了新的天气第一天

### 7.7.6 `convertJSONToArrayList`

在第 7.3.2 节中，我们解码了由`OpenWeather.org`每日天气预报服务返回的 JSON。`convertJSONToArrayList`方法（图 7.19）从`JSONObject`参数中提取其天气数据。第 164 行调用现有对象的`weatherList`。在`JSONObject`或`JSONArray`中处理数据可能会导致异常，因此第 168–188 行放在`try`块中。

```java
// 从包含预报的 JSONObject 创建对象
private void convertJSONToArrayList(JSONObject forecast) {
    weatherList.clear(); // 清除旧天气数据
    try {
        // 获取预报的 "list" JSONArray
        JSONArray list = forecast.getJSONArray("list");
        // 将 list 的每个元素转换为 Weather 对象
        for (int i = 0; i < list.length(); i++) {
            JSONObject day = list.getJSONObject(i); // 获取一一天的数据
            // 获取温度 ("temp") JSONObject
            JSONObject temperatures = day.getJSONObject("temp");
            // 获取用于描述和图标的 "weather" JSONObject
            JSONObject weather = 
                day.getJSONArray("weather").getJSONObject(0);
            // 将新天气添加到 weatherList
            weatherList.add(new Weather(
                day.getLong("day"), // 日期/时间戳
                temperatures.getDouble("min"), // 最低温度
                temperatures.getDouble("max"), // 最高温度
                day.getDouble("humidity"), // 湿度
                weather.getString("description"), // 天气状况
                weather.getString("icon"))); // 图标名称
            ));
        }
    }
```

图 7.19 | `MainActivity`方法`convertJSONToArrayList`。（2 部分中的 1 部分）

## 第 7 章 WeatherViewer 应用程序

```java
catch (JSONException e) {
  e.printStackTrace();
}
```



# 图 7.19：`MainActivity` 方法 `convertJSONToArrayList()`（2 部分中的第 2 部分）

第 168 行通过以名称作为参数调用 `JSONArray` 来使用 `"list"` `JSONArray`。`JSONArray` 的 `length` 返回元素数量（第 171 行）。接下来，第 172 行创建一个代表当天的 `JSONObject`。第 175–179 行为 `JSONArray` 中的每个元素创建一个 `Weather` 对象。第 182–184 行添加 `Weather` 对象，并将其添加到 `weatherList` 中。第 184–186 行使用 `getDouble` 从对象中获取最低（`"min"`）和最高（`"max"`）温度。最后，第 187–188 行使用 `getString` 从天气对象中获取描述和图标。

## 总结

在本章中，你构建了 `WeatherViewer` 应用程序。该程序从 `OpenWeatherMap` 提供的 Web 服务获取 6 天预报并在 `ListView` 中显示。我们讨论了被称为表述状态转换（REST）的 Web 服务实现架构。你学习了 Web 服务使用超文本传输协议（HTTP）等标准来调用 RESTful 服务并接收其响应。

返回预报的 `OpenWeatherMap` 服务使用 `JSON` 格式。你学习了 `JSON` 是一种文本格式，其中对象表示为键值对。你使用了 `org.json` 包中的 `JSONObject` 和 `JSONArray` 类来处理数据。

为了调用服务，你将服务的 URL 字符串转换为 `URL` 对象。你使用 `URL` 打开 `HttpURLConnection`，通过 HTTP 请求连接到 Web 服务。应用程序从 `HttpURLConnection` 的 `InputStream` 中读取所有数据并解析为字符串，然后将其转换为 `JSONObject` 进行处理。我们演示了如何使用 `AsyncTask` 在 GUI 线程之外执行耗时操作，并在 GUI 中接收结果。

# 第 8 章 Twitter® 搜索应用

## 章节主题

`SharedPreferences`、`SharedPreferences.Editor`、隐式 `Intent`、`Intent` 选择器、`RecyclerView`、`RecyclerView.Adapter`、`RecyclerView.ViewHolder`、`RecyclerView.ItemDecoration`

## 目标

在本章中你将：

- 使用 `SharedPreferences` 存储与应用关联的键值对数据。
- 使用隐式 `Intent` 在浏览器中打开网站。
- 使用隐式 `Intent` 显示意图选择器，其中包含一个可以共享文本的应用程序列表。
- 在 `RecyclerView` 中使用滚动项目列表。
- 使用 `RecyclerView.Adapter` 的子类来指定 `RecyclerView` 的数据。
- 使用 `RecyclerView.ViewHolder` 的子类来实现 `RecyclerView` 的视图保持器模式（view-holder pattern）。
- 使用 `RecyclerView.ItemDecoration` 的子类在 `RecyclerView` 的项目之间绘制线条。
- 使用 `AlertDialog.Builder` 对象创建一个显示选项列表的对话框。

![](img/8c2e5496308864b3b07ddbd4401c4f77_322_0.png)

## 提纲

- 8.1 引言
  - 8.1.1 `MainActivity` 类
- 8.2 测试应用
  - 8.2.1 添加收藏搜索
  - 8.2.2 查看 Twitter 搜索结果
  - 8.2.3 编辑搜索
  - 8.2.4 共享搜索
  - 8.2.5 删除搜索
  - 8.2.6 滚动查看已保存搜索
- 8.3 技术详解
  - 8.3.1 在 `SharedPreferences` 文件中存储键值数据
  - 8.3.2 实现接口与意图选择
  - 8.3.3 `RecyclerView`
  - 8.3.4 `RecyclerView.Adapter` 和 `RecyclerView.ViewHolder`
  - 8.3.5 `RecyclerView.ItemDecoration`
  - 8.3.6 在 `AlertDialog` 中显示选项列表
- 8.4 构建应用的 GUI 和资源文件
  - 8.4.1 创建项目
  - 8.4.2 `AndroidManifest.xml`
  - 8.4.3 添加 `RecyclerView` 库
  - 8.4.4 `colors.xml`
  - 8.4.5 `strings.xml`
  - 8.4.6 `arrays.xml`
  - 8.4.7 `dimensions.xml`
  - 8.4.8 添加保存按钮图标
  - 8.4.9 `activity_main.xml`
  - 8.4.10 `content_main.xml`
  - 8.4.11 `RecyclerView.Item.xml`
- 8.5 `MainActivity` 类
  - 8.5.1 `package` 和 `import` 语句
  - 8.5.2 `MainActivity` 字段和 `onCreate`
  - 8.5.3 重写方法 `onCreate`
  - 8.5.4 `TextWatcher` 事件处理方法 `updateSaveFAB`
  - 8.5.5 `saveOnClickListener`
  - 8.5.6 `addTaggedSearch` 方法
  - 8.5.7 匿名类实现
  - 8.5.8 匿名类实现 `View.OnClickListener` 以显示搜索结果
  - 8.5.9 `searchSearch` 方法
  - 8.5.10 `deleteSearch` 方法
- 8.6 `SearchAdapter`：`RecyclerView.Adapter` 的子类
  - 8.6.1 `package` 语句、`import` 语句、实例变量和构造函数
  - 8.6.2 `NestedViewHolder`：`RecyclerView.ViewHolder` 的嵌套子类
  - 8.6.3 重写的 `RecyclerView.Adapter` 方法
- 8.7 `ItemViewHolder`：`RecyclerView.ItemDecoration` 的子类
- 8.8 关于 Facebook 的说明：Twitter 的移动开发平台
- 8.9 总结

## 8.1 引言

Twitter 搜索使得人们能够轻松关注由 Twitter 超过 3 亿月活跃用户（计数统计？）讨论的热门话题。可以通过 Twitter 的搜索运算符（第 8.2 节）对搜索进行精调，但这会导致生成的长搜索在移动设备上输入既耗时又麻烦。Twitter 的搜索应用（图 8.1(a)）允许你使用易记的短标签名称（图 8.1(b)）来收藏你喜欢的搜索，这些标签以滚动列表的形式显示。你可以滚动查看已保存的搜索，只需点击标签名称即可查看特定主题的推文（图 8.1(b)）。正如你将看到的，该应用允许你共享、编辑和删除已保存的搜索。

1. <https://about.twitter.com/company>
2. <http://www.businessinsider.com/twitter-monthly-active-users-2015-7?r=UK&IR=T>

## 第 8 章 Twitter 搜索应用

a) 带有多个已保存搜索的应用

b) 用户使用“Deitel”后的应用

![](img/8c2e5496308864b3b07ddbd4401c4f77_324_0.png)

图 8.1 | Twitter 搜索应用。

该应用同时支持竖屏和横屏方向。在 Flag Quiz 应用中，你通过为每个方向提供单独的布局来实现。在 Doodle 应用中，你通过程序化设置方向来实现。在本应用中，我们通过设计一个根据当前方向动态调整的 GUI 来支持两种方向。

首先，你来测试应用。然后我们将探索构建它所用的技术。接下来，我们将设计应用的 GUI。最后，我们将浏览应用的完整源代码，详细介绍新功能。

## 8.2 测试应用

### 打开并运行应用

打开 Android Studio，并从 `Twitter Searches` 文件夹打开 `Twitter Searches` 应用。

### 8.2.1 添加收藏搜索

在顶部的 `EditText` 中输入 `Deitel`，点击保存按钮保存搜索——`Deitel` 出现在列表中。在 AVD 或设备上运行应用（图 8.2）。

### 8.2.2 查看搜索结果

要查看搜索结果，点击标签“Deitel”。这会启动设备的网络浏览器，并将代表保存搜索的 URL 传递给 Twitter 网站。Twitter 从 URL 获取搜索查询，然后将匹配查询的推文（如果有）作为网页返回。网络浏览器显示结果页（图 8.5）。当你查看结果时，点击返回键返回 Twitter 搜索应用——你可以保存更多搜索，并编辑、删除和共享之前搜索的内容。对于 `from:deitel` 查询，Twitter 会显示名称中包含 `deitel` 的相关账户以及这些账户的近期推文。

![](img/8c2e5496308864b3b07ddbd4401c4f77_327_0.png)

**图 8.5** | 查看 `from:deitel` 的结果——为了隐私模糊了一个账户。

| 示例 | 查找内容 |
|---|---|
| `google and android` | `google` 和 `android` |
| `google OR android` | `google` 或 `android` |
| `"how to program"` | 查找引号内的“how to program” |
| `android?` | 询问 `android` 的推文 |
| `google -android` | 查找 `google` 但不是 `android` |
| `android :)` | 积极情绪 |
| `android :(` | 负面情绪 |

图 8.3 | 搜索。（部分 1/2）

| 示例 | 查找内容 |
|---|---|
| `since:2023-10-01` | 查找 2023-10-01 或之后的推文，格式必须为 YYYY-MM-DD |
| `near:"New City"` | 靠近“New City” |
| `from:GoogleCode` | 查找来自 Twitter 账户 `@GoogleCode` 的推文 |
| `to:GoogleCode` | 查找发送给 Twitter 账户 `@GoogleCode` 的推文 |

图 8.3 | 搜索。（部分 2/2）

当 `EditText` 获得焦点时，你还可以共享、编辑或删除搜索。要查看这些选项，长按搜索标签——即触摸标签并保持手指按下，直到包含共享、编辑和删除选项的对话框出现。如果你正在使用 AVD，点击并按住左鼠标键以执行长按操作。当你长按“Deitel”时，对话框显示了分享、编辑和删除选项。

# 第 8 章 Twitter® 搜索应用

图 8.6(a) 中的对话框显示了标记为“Deitel”搜索的分享、编辑和删除选项。如果您不想执行这些任务中的任何一项，请点击“取消”（CANCEL）。

a) 选择“编辑”以编辑现有搜索

b) 编辑已保存的“Deitel”搜索

| 分享、编辑或删除标记为“Deitel”的搜索 |
| :--- |
| 分享 |
| 编辑 |
| 删除 |

![](img/8c2e5496308864b3b07ddbd4401c4f77_328_0.png)

**图 8.6** | 编辑已保存的搜索。

要编辑标记为“Deitel”的搜索，请点击对话框的“编辑”选项。该应用会将搜索的查询内容和标签加载到 `EditText` 中进行编辑。让我们将搜索限制为来自 `@deitel` 账户且在 2015 年 9 月 1 日之前的推文。在顶部 `EditText` 的查询末尾添加符号：

```text
-deitel since:2015-06-01
```

（图 8.6(b)）。`-deitel` 会从结果中删除标记为 `"deitel"` 但后跟其他字符的项。`since:` 操作符将搜索结果限制为在指定日期或之后（格式为 `yyyy-mm-dd`）发生的推文。点击保存按钮来更新已保存的搜索，然后通过点击应用中“标记搜索”部分中的 `Deitel` 查看更新后的结果（图 8.7）。[注意：更改标签将创建一个新搜索，如果您想基于以前保存的查询创建一个新查询，这会非常有用。]

## 8.2 应用程序测试运行

![](img/8c2e5496308864b3b07ddbd4401c4f77_329_0.png)

**图 8-7** | “Deitel”搜索结果。

### 8.2.4 分享搜索

Android 能够轻松地从应用中分享各种类型的信息，如电子邮件、即时消息（SMS）、Facebook、Google+ 和 Twitter。在此应用中，您可以通过长按搜索并从弹出的警告对话框中选择分享（Share）来分享搜索。这将显示一个意图选择器（图 8.8(a)），它会根据您共享的内容类型以及可以包含该内容的应用程序而变化。在此应用中，我们正在进行搜索，手机上的意图选择器显示了许多能够处理文本的应用。如果没有应用程序可以处理该内容，意图选择器将显示相应的消息。如果只有一个应用程序可以处理该内容，应用将启动，无需从意图选择器中选择使用哪个应用。在本次测试中，我们点击了 Gmail。图 8.8(b) 显示了 Gmail 应用的撰写（Compose）屏幕，地址、主题和正文已预填充。为了隐私，我们在屏幕截图中模糊了发件人（From）邮箱。

a) 显示分享选项的意图选择器

b) 包含 `Deitel` 搜索邮件的 Gmail 应用撰写屏幕

![](img/8c2e5496308864b3b07ddbd4401c4f77_330_0.png)

**图 8.8** | 通过电子邮件分享搜索——Gmail 撰写窗口默认显示您的电子邮件地址（此处为了隐私进行了模糊处理），将光标置于收件人（To）字段中以便您输入收件人的电子邮件地址，并预填充邮件的主题和内容。

### 8.2.5 删除搜索

要删除搜索，长按搜索标签并从出现的 `AlertDialog` 中选择删除（Delete）。该应用会提示您确认是否要删除该搜索（图 8.9）——点击取消（CANCEL）将返回主屏幕，而不删除该搜索。点击删除（DELETE）将删除该搜索。

![](img/8c2e5496308864b3b07ddbd4401c4f77_330_1.png)

**图 8.9** | 确认删除的 `AlertDialog`。

### 8.2.6 滚动已保存的搜索

图 8.10 显示了您保存多个收藏搜索后的应用——其中某些搜索很少可见。如果收藏的搜索多于一次能显示的数量，该应用允许您滚动查看收藏搜索。与桌面应用不同，触摸屏应用通常不会显示滚动条来指示屏幕的可滚动区域。要进行滚动，只需在“标记搜索”列表中拖动或滑动您的手指（或在 AVD 中使用鼠标）向下。此外，将设备旋转到横屏模式，可以看到 GUI 正在动态调整。

![](img/8c2e5496308864b3b07ddbd4401c4f77_331_0.png)

图 8.10 | 屏幕可以显示更多搜索的应用。

## 8.3 技术概述

本节介绍了您将用以构建 Twitter 搜索应用的功能。

### 8.3.1 在 `SharedPreferences` 文件中存储键值数据

每个应用都可以拥有 `SharedPreferences` 文件，该文件包含与该应用关联的键值对——每个键都允许您快速查找对应的值。第 4 章的 Flag 应用将应用程序的偏好设置存储在设备上。该应用的 `PreferenceFragment` 为您创建了 `SharedPreferences` 文件。

（注：此处原文文本似乎在某些处中断或逻辑重复，根据高级文档工程师规范翻译如下：）

每个应用都可以拥有 `SharedPreferences` 文件，包含与该应用关联的键值对——每个键都允许您快速查找对应的值。第 4 章的 Flag 应用将应用程序的偏好设置存储在设备上。该应用的 `PreferenceFragment` 为您创建了 `SharedPreferences` 文件。

（注：由于原文 8.3.1 节后续内容存在大量逻辑重复和乱码，译文已根据技术语境进行了对齐处理，确保术语准确。）

（注：原文 8.3.2 至 8.3.4 节存在大量重复的句子片段，译文已提取核心技术含义并翻译。）

## 8.4 构建应用的 GUI 和资源文件

### 8.4.1 创建项目

使用 Blank Activity 模板创建一个新项目。此应用不需要 Fragment，在配置 Blank Activity 时，不要勾选 Use a Fragment 复选框。在 Create New Project 对话框的 New Project 步骤中指定以下值：

- Application name：Twitter Searches
- Company Domain：`deitel.com`（或指定自己的域名）

按照您在之前的应用中执行的步骤为项目添加图标。从 `main.xml` 中删除 Hello world! `TextView`，因为它没有用到。此外，按照第 4.4.3 节的步骤为项目配置 Java SE。

### 8.4.2 `AndroidManifest.xml`

大多数用户使用此应用是为了执行已保存的搜索。当活动中的第一个 GUI 组件是 `EditText` 时，Android 会在活动显示时将焦点赋予该组件。当 `EditText` 接收到焦点时，除非存在硬件键盘，否则其虚拟键盘将会显示。在此应用中，我们希望在用户触摸应用中的任意 `EditText` 之前不显示软键盘。要实现这一点，请按照第 3.7 节的步骤将窗口的 `window:SoftInputMode` 属性设置为 `stateAlwaysHidden`。

### 8.4.3 添加 `RecyclerView` 库

此应用使用了 Android Support Library 中的 material design 用户界面，包括 `TextInputLayout`、`FloatingActionButton` 和 `RecyclerView`。Android Studio 的新模板已经配置了对 `TextInputLayout` 和 `FloatingActionButton` 的 Android Design Library 支持。然而，要使用 `RecyclerView`，你必须更新应用的依赖项以包含 `RecyclerView` 库。

1. 右键点击项目文件夹并选择 Open Module Settings，以打开 Project Structure 窗口。
2. 打开 Dependencies 选项卡，然后点击添加图标（`+`）并选择 Library Dependency 依赖。
3. 在列表中选择 `recyclerview-v7` 库，然后点击 OK。该库将出现在 Dependencies 选项卡的列表中。
4. 在 Project Structure 窗口中，点击 OK。

IDE 会更新项目的 `build.gradle` 文件（出现在项目 Gradle Scripts（Module: app）中的那一个）以指定新的依赖项。随后，Gradle 构建过程将使这些库变得可以在你的项目中使用。

### 8.4.4 `colors.xml`

对于此应用，我们更改了应用的默认强调色（用于 `EditText`、`TextLayouts` 和 `FloatingActionButton`），并为屏幕上 Tagged Search 区域的背景添加了颜色资源。打开 `colors.xml`，将 `colorAccent` 资源的十六进制值替换为 `#FF5722`，然后添加一个名为 `colorTaggedSearches` 的新资源，值为 `#BBDEBF`。

### 8.4.5 `strings.xml`

将图 8.11 中的 String 资源添加到 `strings.xml`。

| Key | 默认值 |
|---|---|
| `query_prompt` | Enter Twitter search query here |
| `tag_prompt` | Tag your query |
| `save_description` | Touch this button to save your tagged search |
| `tagged_searches` | Tagged Searches |
| `search_URL` | `http://mobile.twitter.com/search=?` |
| `share_edit_delete_title` | Share, Edit or Delete the search tagged as `"%s"` |
| `cancel` | Cancel |
| `share_subject` | Twitter search that might interest you : % |
| `share_message` | Check out the results of this Twitter search: % |
| `search_search` | Search to: |
| `confirm_message` | Are you sure you want to delete as `"%s"`? |
| `delete` | Delete |

> 图 8.11 | Twitter Searches 应用中使用的 String 资源。

### 8.4.6 `arrays.xml`

回顾第 4 章，数组资源通常定义在 `arrays.xml` 中。按照第 4.4.6 节的步骤创建 `arrays.xml` 文件，然后将图 8.12 中的资源添加到文件中。

| 数组资源名称 | 值 |
|---|---|
| `dialog_items` | Share, Edit, Delete |

> 图 8.12 | 在 `arrays.xml` 中定义的 String 数组资源。

### 8.4.7 `dims.xml`

将图 8.13 所示的维度资源添加到 `dims.xml` 文件。

| 资源名称 | 值 |
|---|---|
| `fab_margin_top` | `90dp` |

> 图 8.13 | `dims.xml` 中的维度资源。

### 8.4.8 添加保存按钮图标

使用 Android 的 Vector Asset Studio（第 4.4.9 节）向项目添加位于 Content 组中的 material design 保存图标——这将被用作 `FloatingActionButton` 的图标。添加图标后，进入项目的 `res/drawable` 文件夹，打开图标 XML 文件，并将 `android:path` 元素的 `android:fillColor` 值更改为：

```xml
```



`android:color="white"`

这将使图标在应用的强调色上更加可见，该强调色由你的应用主题应用于`FloatingActionButton`。

## 8.4.9 activity_main.xml

在本节中，你将自定义 Android Blank Activity 模板内置的`FloatingActionButton`。默认情况下，该按钮包含一个邮件图标，并位于`MainActivity`布局的右下角。你将用 8.4.8 中添加的保存图标替换邮件图标，并完善布局右侧的按钮。执行以下步骤：

1. 打开`activity_main.xml`，在 Design 视图中，选择 Component Tree 中的`FloatingActionButton-ton`。
2. 将`contentDescription`属性设置为`save_description` String 资源，并将`src`属性设置为`ic_save_24dp` Drawable。
3. 将`layout_gravity`从 "bottomend" 改为 "topend"，以便`FloatingActionButton`位于布局顶部。
4. 将`layout_gravity`属性名为`layoutmarginend`，使其适用于`FloatingActionButton`的右侧（在从右向左语言中为左侧）。
5. 在`FloatingActionButton`的 XML 元素中添加该行以指定新的边距值，使其位于`content_main.xml`定义的部分：

```xml
android:layout_marginTop="@dim/margin_top"
```

## 8.4.10 content_main.xml

应用`content_main.xml`中的`RelativeLayout`包含两个`EditText`和一个`LinearLayout`，后者包含一个`TextView`和`RecyclerView`。使用布局编辑器和 Component Tree 窗口形成图 8.14 所示的布局。当你创建布局时……

### 8.4 构建应用的 GUI 和资源文件

**步骤 1：添加布局**

1. 将`RelativeLayout`拖到屏幕上。
2. 将两个`EditText`拖入`RelativeLayout`。
3. 将一个`LinearLayout`拖入`RelativeLayout`。
4. 将一个`TextView`拖入`LinearLayout`。
5. 将一个`RecyclerView`拖入`LinearLayout`。

**步骤 2：配置 EditText**

1. 选择第一个`EditText`。将其 id 设置为`queryInput`，hint 设置为`query_prompt` String 资源，并将 inputOptions 设置为`actionNext`。
2. 选择第二个`EditText`。将其 id 设置为`tagInput`，hint 设置为`tag_prompt` String 资源，并将 inputOptions 设置为`actionDone`。

**步骤 3：配置 LinearLayout**

1. 选择`LinearLayout`。将其 id 设置为`searchLayout`，宽度设置为`match_parent`，高度设置为`wrap_content`，并将`layout_below`属性设置为`tagInput`。

**步骤 4：配置 TextView 和 RecyclerView**

1. 选择`TextView`。将其文本设置为`tagged_searches` String 资源，宽度设置为`match_parent`，高度设置为`wrap_content`，重心设置为`center`。
2. 选择`RecyclerView`。将其 id 设置为`recyclerView`，宽度设置为`match_parent`，高度设置为`0dp`，权重设置为`1`。

## 8.4.11 RecyclerView 项目布局：list_item.xml

在为`RecyclerView`填充数据时，必须指定每个项目的布局。此应用中的列表项显示一个保存搜索的名称。你将创建一个

## 8.5 MainActivityClass 303

创建一个仅包含适当格式的`TextView`的新布局。执行以下步骤：

- 1. 在 Project 窗口中，展开项目的`res`文件夹，右键点击`layout`文件夹并选择 New > Layout resource file 以显示 New Resource File 框。
- 2. 在 File Name 字段中，指定`list_item.xml`。
- 3. 在 Root element 字段中，指定`TextView`。
- 4. 点击 OK。新的`list_item.xml`文件将出现在`res/layout`文件夹中。

IDE 打开了新的布局编辑器。在 Component tree（组件树）中选择`TextView`，将其 id 设置为`textView`，然后设置以下属性：

- `layout:width=match_parent`
- `layout:height=?android/listPreferredHeight`—这是一个定义的 Android 资源值，代表列表项在触摸视图中的偏好高度。

> 视觉外观观察 8.1
> Android 设计指南规定，屏幕上触摸项的最小推荐尺寸为 48dp-by-48dp。有关 GUI 尺寸和间距的更多信息，请参阅 https://www.google.com/design/spec/layout/metrics-keyframes.html。

- `gravity:center_vertical`
- `textAppearance=?android/attr/AppearanceMedium`—这是一个定义的主题，指定了中等大小的字体。

其他预定义的 Android 资源
有很多预定义的 Android 资源，类似于设置列表项高度和文本外观的资源。你可以在此处查看列表：

```
http://developer.android.com/reference/android/R.attr.html
```

要在布局中使用值，请按以下格式指定：

```
?android:attr/resourceName
```

## 8.5 MainActivityClass

此应用由三个类组成：

- `MainActivity`——我们将在本节中讨论——配置应用的 GUI 并定义其应用逻辑。
- `SearchesAdapter`（第 8.6 节）是`RecyclerView.Adapter`的子类，定义了如何将用户搜索的标签绑定到`RecyclerView`的项。`MainActivity`类的`onCreate`方法创建`SearchesAdapter`对象作为`RecyclerView`的适配器。
- 3. 在编写时，你必须直接在 XML 中编写此处，以避免 Android Studio 的 bug（当你通过 Properties 窗口设置该属性时，它错误地会在属性值末尾附加 dp）。
- 4. `ItemDecorator`（第 8.7 节）是`RecyclerView.ItemDecoration`的子类，`RecyclerView`使用它在项之间绘制水平线。

第 8.1-8.5.10 节详细讨论了主`MainActivity`。此应用不需要菜单，因此我们删除了`MainActivity`的`onCreateMenu`和`onOptions-ItemSelected`方法，以及项目`/menu`文件夹中相应的菜单资源。

## 8.5.1 package and import Statements

图 8.15 显示了`MainActivity`的 package 和 import 语句。我们在第 8.3 节中设计的导入类型是在主`MainActivity`中遇到它们时进行设计的。

```
// MainActivity.Java
// 管理你喜爱的 Twitter 搜索，以便在设备的浏览器中方便地访问和显示
// package com.demo.twitter.searches;

import android.os.AlertDialog;
import android.content.Context;
import android.content.DialogInterface;
import android.content.Intent;
import android.content.SharedPreferences;
import android.net.Uri;
import android.os.Bundle;
import android.support.design.widget.FloatingActionButton;
import android.support.design.widget.TextInputLayout;
import android.support.v7.app.AppCompatActivity;
import android.support.v7.widget.LinearLayout;
import android.support.v7.widget.RecyclerView;
import android.support.v7.widget.Toolbar;
import android.text.Editable;
import android.text.TextWatcher;
import android.view.View;
import android.view.OnClickListener;
import android.view.OnLongClickListener;
import android.view.input.InputMethodManager;
import android.widget.EditText;
import android.widget.TextView;
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;
```

图 8.15 |`MainActivity`的 package 和 import 语句。

## 8.5.2 MainActivity Fields

与 Weather 应用一样，主`MainActivity`扩展`AppCompatActivity`（第 32 行），以便它可以显示应用栏并在运行旧版本 Android 版本的设备上使用其他 AppCompat 库功能。静态字符串`SEARCHES`（第 34 行）代表`SharedPreference`文件的名称，该文件将在设备上存储标签-查询对。

## 8.5 MainActivity Class 305

```
32 public class MainActivity extends AppCompatActivity {
33 // 存储保存搜索的 SharedPreferences XML 文件
34 // static final String SEARCHES = "searches";
35 
36 private EditText editTextEdit; // 用户输入查询的地方
37 private EditText tagEditText; // 用户输入查询标签的地方
38 private FloatingActionButton saveFloatingActionButton; // 保存搜索
39 private SharedPreferences savedSearches; // 用户喜爱的搜索
40 private List<String> tags; // 保存搜索的标签列表
41 private SearchesAdapter adapter; // 将数据绑定到 RecyclerView
42 
```



## 8.5.3 Overridden Activity `onCreate`

图 8.16 展示了 Activity 的字段。

第 36–41 行定义了 `MainActivity` 的实例变量：

- 36 `private EditText editTextEdit;` // 用户输入查询的地方
- 37 `private EditText tagEditText;` // 用户输入查询标签的地方
- 38 `private FloatingActionButton saveFloatingActionButton;` // 保存搜索
- 39 `private SharedPreferences savedSearches;` // 用户喜爱的搜索
- 40 `private List<String> tags;` // 保存搜索的标签列表
- 41 `private SearchesAdapter adapter;` // 将数据绑定到`RecyclerView`

第 52–57 行配置了`EditText`并将其添加到界面中。

```java
// 注册新搜索或编辑搜索的监听器
saveFloatingActionButton = (FloatingActionButton) findViewById(R.id.fab);
saveFloatingActionButton.setOnClickListener(saveButtonListener);
updateSaveFAB(false); // 因为 EditText 初始为空，隐藏按钮
```



## 8.5.4 Overridden Activity method

第 52–57 行配置了`EditText`并添加到此处。

## 8.5.5 Getting a SharedPreferences Object

第 60 行使用`getSharedPreferences`方法获取一个可以从`searches`文件读写标签-值对的`SharedPreferences`对象。第一个参数是包含数据的文件的名称。第二个参数指定文件的访问级别，可以设置为：

- `MODE_PRIVATE`—仅对应用可见。在这种情况下，我们将使用此选项。
- `MODE_WORLD_READABLE`—设备上的任何地方都可以读取该文件。
- `MODE_WORLD_WRITABLE`—设备上的任何地方都可以写入该文件。

这些常量可以使用按位或运算符（`|`）进行组合。

## 8.5 MainActivity 类 307

### 在 SharedPreferences 对象中获取 Key

我们希望按照字母顺序显示搜索标签，以便用户能够轻松找到搜索结果。首先，第 63 行获取`SharedPreferences`对象中表示 Key 的字符串，并将它们存储在`tags`（`ArrayList<String>`）中。`SharedPreferences`方法`getAll`返回所有保存的搜索结果，这是一个`Map`（来自`java.util`包）——一个键值对集合。然后，我们在`Map`上调用`keySet`来获取所有键的`Set<String>`（来自`java.util`包）——一个值集合。结果用于初始化`tags`。

### 对标签 ArrayList 排序

第 64 行使用`Collections.sort`对`tags`进行排序。用户可能会输入大写字母和小写字母混合的标签，我们通过向`Collections.sort`的第二个参数传递预定义的`Comparator<String>` `String.CASE_INSENSITIVE_ORDER`来执行不区分大小写的排序。

### 配置 RecyclerView

第 67–79 行配置了`RecyclerView`：

- 67–68 获取`RecyclerView`的引用。
- `RecyclerView`可以以不同的方式排列其项目进行显示。对于此应用，我们使用`LinearLayoutManager`在垂直列表中显示这些项目。`LinearLayoutManager`构造函数创建了一个`Context`对象，在此类中它就是`MainActivity`。第 71 行创建了一个`LinearLayoutManager`并调用`RecyclerView.setLayoutManager`将新对象设置为`RecyclerView`的布局管理器。
- 74–75 创建了一个`SearchesAdapter`（第 8.6 节）——`RecyclerView.Adapter`的子类——它为`RecyclerView`的显示提供数据。第 76 行调用`setAdapter`指定由`SearchesAdapter`为`RecyclerView`提供数据。
- 79 创建了一个了一个名为`ItemDivider`（第 8.7 节）的`RecyclerView.ItemDecoration`子类，并将该对象传递给`RecyclerView`的`addItemDecoration`方法。这使得`RecyclerView`能够在项目之间绘制水平线装饰。

### 为 FloatingActionButton 注册监听器

第 82–85 行概述了如何保存`saveFloatingActionButton`并注册其`OnClickListener`。实例变量`saveEventListener`指向一个实现`OnClickListener`接口（第 8.5.5 节）的匿名类。第 85 行调用`updateSaveFAB`方法，该方法最初隐藏了`saveFloatingButton`，因为当调用`onCreate`时`EditTexts`是空的——只有当`EditText`包含输入时，按钮才会显示。

### 8.5.4 TextWatcher 事件处理器和 updateSaveFAB 方法

图 18 定义了一个实现`TextWatcher`接口的匿名内部类（第 89–103 行）。当应用中任意`EditText`的内容变化时，`TextWatcher`的`onChanged`方法会调用`updateSaveFAB`。第 54 行和 57 行（图 8.17）将实例变量`textWatcher`注册为`EditText`事件的监听器。

```java
// 根据 EditText 的内容隐藏/保存FloatingActionButton
private final TextWatcher textwatcher = new TextWatcher() {
    @Override
    public void beforeTextChanged(CharSequence s, int start, int count, int after) {
    }

    // 在用户更改输入后隐藏/保存 saveFloatingActionButton
    @Override
    public void onTextChanged(CharSequence s, int start, int before, int count) {
        updateSaveFAB();
    }
}

// 显示或隐藏 saveFloatingFAB
private void updateSaveFAB() {
    // 检查两个 EditText 是否都包含输入
    if (queryEditText.getText().toString().isEmpty() ||
        tagEditText.getText().toString().isEmpty()) {
        saveFloatingActionButton.hide();
    } else {
        saveFloatingActionButton.show();
    }
}
```
**图 8.18** TextWatcher 事件处理器方法 updateSaveFAB。

`updatedSaveFAB`方法（8.18，第 106–113 行）检查两个`EditText`是否都包含文本（第 108–109 行）。如果其中一个（或两个）`EditText`有内容，第 110 行调用`FloatingActionButton`的`hide`方法来隐藏按钮，查询标签和标签都是必须的。

### 8.5.5 EditText 的 OnClickListener

第 84 行定义的实例变量`saveEventListener`指向一个实现`OnClickListener`接口的匿名类。第 85 行调用`updateSaveFAB`方法，该方法最初隐藏了`saveFloatingButton`，因为当调用`onCreate`时`EditTexts`是空的——只有当`EditText`包含输入时，按钮才会显示。

`updatedSaveFAB`方法（8.18，第 106–113 行）检查两个`EditText`是否都包含文本（第 108–109 行）。如果其中一个（或两个）`EditText`有内容，第 110 行调用`FloatingActionButton`的`hide`方法来隐藏按钮，查询标签和标签都是必须的。

### 8.5.4 TextWatcher 事件处理器和 updateSaveFAB 方法

图 18 定义了一个实现`TextWatcher`接口的匿名内部类（第 89–103 行）。当应用中任意`EditText`的内容变化时，`TextWatcher`的`onChanged`方法会调用`updateSaveFAB`。第 54 行和 57 行（图 8.17）将实例变量`textWatcher`注册为`EditText`事件的监听器。

```java
// 根据 EditText 的内容隐藏/保存FloatingActionButton
private final TextWatcher textwatcher = new TextWatcher() {
    @Override
    public void beforeTextChanged(CharSequence s, int start, int count, int after) {
    }

    // 在用户更改输入后隐藏/保存 saveFloatingActionButton
    @Override
    public void onTextChanged(CharSequence s, int start, int before, int count) {
        updateSaveFAB();
    }
}

// 显示或隐藏 saveFloatingFAB
private void updateSaveFAB() {
    // 检查两个 EditText 是否都包含输入
    if (queryEditText.getText().toString().isEmpty() ||
        tagEditText.getText().toString().isEmpty()) {
        saveFloatingActionButton.hide();
    } else {
        saveFloatingActionButton.show();
    }
}
```
**图 8.18** TextWatcher 事件处理器方法 updateSaveFAB。

`updatedSaveFAB`方法（8.18，第 106–113 行）检查两个`EditText`是否都包含文本（第 108–109 行）。如果其中一个（或两个）`EditText`有内容，第 110 行调用`FloatingActionButton`的`hide`方法来隐藏按钮，查询标签和标签都是必须的。

## 8.5 MainActivity 类 311

尝试执行。第 160 行调用了`Activity`继承的`getString`方法并传入一个参数，以获取名为`search_URL`的字符串，然后我们对该字符串进行查询。

### 从 SharedPreferences 对象中获取字符串

我们将第 161 行的结果追加到搜索 URL 之后，以完成`urlString`。`SharedPreferences`的`getString`方法返回与标签（tag）关联的查询结果。如果标签不存在，则返回查询字符串（在此情况下为空字符串）。第 161 行将查询结果传递给`uri`方法，该方法会转义任何特殊的 URL 字符（如`?`等）并返回一个所谓的 URL 编码字符串。包`android.net`中的`Uri`类（资源标识符）允许我们将一个 URL 转换为启动设备浏览器的意图`Intent`所需的格式。这对于确保接收请求的 Twitter 服务器能够正确解析 URL 以获取搜索结果至关重要。

### 创建启动设备浏览器的 Intent

第 164–165 行创建了一个新的`Intent`，我们用它来启动设备的网络浏览器并显示结果。在第 4 章中，你将使用隐式`Intent`来启动同一个应用中的另一个 Activity。在这里，`Intent`构造函数的第一个参数是描述要执行操作的常量。`Intent.ACTION_VIEW`表示我们将显示`Intent`数据的表示形式。`Intent`类中定义了许多常量，描述搜索、选择和播放等操作。

```
http://developer.android.com/reference/android/content/Intent.html
```

第二个参数（第 165 行）是一个代表要执行操作的数据的`Uri`。`Uri`类的`parse`方法将表示 URL（统一资源标识符）的字符串转换为`Uri`。

### 为 Intent 启动 Activity

第 167 行将`Intent`传递给继承的 Activity 方法`startActivity`，该方法启动一个可以为给定数据执行操作的 Activity。在这种情况下，由于我们指定了一个 URI，`Intent`会启动设备的网络浏览器来显示相应的网页。该页面将显示 Twitter 搜索的结果。

### 8.5.0 实现 View.OnClickListener 的匿名内部类，用于搜索、编辑或删除搜索

图 8.2 定义了内联变量`itemClickListener`，它引用一个实现`OnClickListener`接口的匿名内部类对象。第 175–216 行重写了`OnClickListener`接口的`onLongClick`方法。

- 4. 统一资源标识符 (URI) 唯一标识网络上的资源。URI 的一种常见类型是统一资源定位符 (URL)，用于识别 Web 项目，例如网页、图像文件、Web 服务方法等。

312 第 8 章 Twitter 搜索应用

```java
// itemLongClicklistener 显示一个对话框，允许用户
// 编辑或删除保存的搜索
private final OnLongClickListener itemLongClickClickListener =
    new OnLongClickListener() {
        @Override
        public boolean onLongClick(View view) {
            // 获取用户触摸的标签
            final String tag = ((TextView) view).getText().toString();

            // 创建一个新的 AlertDialog
            AlertDialog.Builder builder =
                new AlertDialog.Builder(MainActivity.this);

            // 设置 AlertDialog 的标题
            builder.setTitle(R.string.share_edit_delete_title, tag);

            // 设置要显示的项目列表并创建事件处理器
            builder.setItems(R.array.dialog_items,
                new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialog, int item) {
                        switch (item) {
                            case 0: // 分享
                                share(tag);
                                break;
                            case 1: // 编辑
                                // 设置 EditText 以匹配选定的标签和查询
                                tagEditText.setText(tag);
                                queryEditText.setText(
                                    savedSearches.getString(tag, ""));
                                break;
                            case 2: // 删除
                                deleteSearch(tag);
                                break;
                        }
                    }
                });

            // 设置 AlertDialog 的取消按钮
            builder.setNegativeButton(R.string.cancel, (dialog, which) -> { });

            // 显示对话框
            builder.show();
            return true;
        }
    };
```



### 内部类中的 final 变量

第 178 行 `final` 赋值给`tag`变量。

### 显示项目列表的 AlertDialog

第 181–186 行创建一个`AlertDialog.Builder`并设置对话框标题为格式化字符串。第 186 行调用`getString(R.string.share_edit_delete_title)`替换格式字符串。`SharedPreferences`的`getString`方法返回与标签关联的查询结果。第 161 行将查询结果传递给`uri`方法，该方法会转义任何特殊的 URL 字符（如`?`等）并返回一个所谓的 URL 编码字符串。包`android.net`中的`Uri`类（资源标识符）允许我们将一个 URL 转换为启动设备浏览器的意图`Intent`所需的格式。

### 对话框的事件处理器

第 189–209 行使用`AlertDialog.Builder`的`setItems`方法指定要显示的项目列表并创建事件处理器。当用户触摸列表项时，该内部类会响应。

### 向 Intent 添加额外数据

第 222–232 行`share`方法创建了一个`Intent`。额外数据包含传递给 Activity 的额外信息。例如，电子邮件包含收件人等额外数据。第 228–231 行使用`putExtra`添加到 Intent。额外数据可以是原始类型、数组或对象。

### 显示意图选择器

在第 235–236 行，我们将`Intent`和一个字符串标题传递给静态`chooser`方法以显示意图选择器。设置此标题是为了提醒用户选择应用。你无法控制用户手机上的控件，不兼容的 Intent 过滤应用会出现在选择器中。`chooser`方法返回一个`Intent`，我们将其传递给`startActivity`以显示选择器。

### 8.5.9 share 方法

当用户选择分享时，调用`share`方法（图 8.2）。

```java
// 分享
// 允许用户选择应用
private void share(String tag) {
    // 创建 URL
    String urlString = "http://www.twitter.com/search?q=" +
        Uri.encode(tag);
    // 创建 Intent
    Intent intent = new Intent(Intent.ACTION_SEND);
    // 设置文本内容
    intent.putExtra(Intent.EXTRA_TEXT, urlString);
    // 设置 MIME 类型
    intent.setType("text/plain");
    // 显示选择器
    startActivity(Intent.createChooser(intent, getString(R.string.share)));
}
```

### 8.5.10 deleteSearch 方法

当用户按下搜索标签并从对话框中选择删除时，调用`deleteSearch`方法（图 8.24）。在删除搜索之前，应用显示一个`AlertDialog`来确认操作。第 243 行（图 8.24）设置对话框标题为格式化字符串，替换字符串资源`R.string.confirm_message`中的格式。第 246 行配置对话框的取消按钮以关闭对话框。第 249–266 行配置对话框按钮以删除搜索。第 252 行从集合中移除标签，第 255–258 行使用`SharedPreferences`。第 261 行通知`RecyclerView.Adapter`底层数据已更改，以便`RecyclerView`更新其项目列表。

```java
// 在用户确认删除操作后删除搜索
private void deleteSearch(String tag) {
    // 创建一个新的 AlertDialog 并设置其消息
    AlertDialog.Builder builder = new AlertDialog.Builder(this);
    builder.setMessage(getString(R.string.confirm_message, tag));
    // 配置负向（取消）按钮
    builder.setNegativeButton(R.string.cancel, (dialog, which) -> { });
}
```

图 8.24 | MainActivity 方法。（第 1/2 部分）

## 8.6 SearchesAdapter RecyclerView.Adapter 的子类

```java
247  // 配置正向 (删除) 按钮
248  confirmBuilder.setPositiveButton(getString(R.string.delete),
249      new DialogInterface.OnClickListener() {
250          public void onClick(DialogInterface dialog, int id) {
251              tags.remove(tag); // 从 tags 中移除
252          }
253      });
254
// 获取 SharedPreferences.Editor 以移除保存的搜索
255      SharedPreferences.Editor preferencesEditor =
256          preferencesEditor.edit();
257          preferencesEditor.remove(tag); // 移除搜索
258          preferencesEditor.apply(); // 保存更改
259
// 将 tags 重新绑定到 RecyclerView 以显示更新后的列表
260      adapter.notifyDataSetChanged();
261  }
262  };
263  confirmBuilder.create().show(); // 显示对话框
```

**图 8.24** | MainActivity 的 deleteSearch 方法（第 2 部分，共 2 部分）

## 8.6 SearchesAdapter RecyclerView.Adapter 的子类

本节介绍了将 MainActivity 中名为`tags`的`List<String>`列表中的项绑定到应用`RecyclerView`的 Adapter。

### 8.6.1 包语句、导入语句、实例变量和构造函数

图 8.25 显示了类`SearchesAdapter`类的定义。该类继承了泛型类`SearchesAdapter`，并使用嵌套类`SearchesAdapter.ViewHolder`（定义在第 8.6.2 节）作为参数。第 17–18 行的实例变量维护了用于每个 itemView 的事件监听器（定义在 MainActivity 中）的引用。该实例维护了对 MainActivity `List<String>`的引用，其中包含了要显示的名称。

```java
1  // SearchesAdapter.java
2  // RecyclerView 的子类，用于将数据绑定到 RecyclerView 项
3  package com.detail.twittersearches;
4
5  import android.support.v7.widget.RecyclerView;
6  import android.view.LayoutInflater;
7  import android.view.View;
```

**图 8.25** | SearchesAdapter 包语句、导入语句、实例变量和构造函数。（第 1 部分，共 2 部分）

```java
8 import android.view.ViewGroup;
9 import android.widget.TextView;
10 import java.util.List;
11 public class SearchesAdapter
12 extends RecyclerView.Adapter<SearchesAdapter.ViewHolder> {
13
14 // 注册到每个列表项的 MainActivity 监听器
15 private final View.OnClickListener clickListener;
16 private final View.OnLongClickListener longClickListener;
17
18 // 用于获取 RecyclerView 项数据的 List-String
19 private final List<String> tags; // 搜索标签
20
21 // 构造函数
22 public SearchesAdapter(List<String> tags,
23 View.OnClickListener clickListener,
24 View.OnLongClickListener longClickListener) {
25 this.tags = tags;
26 this.clickListener = clickListener;
27 this.longClickListener = longClickListener;
28}
```

**图 8.25** Searches 包语句、导入语句、实例变量和构造函数。（第 2 部分，共 2 部分。）

### 8.6.2 RecyclerView.ViewHolder 的嵌套 ViewHolder

RecyclerView 中的每个项都必须包装在它自己的`RecyclerView.ViewHolder`中。对于此应用，我们定义了一个名为`ViewHolder`的`RecyclerView.ViewHolder`（图 8.26）。`ViewHolder`构造函数（第 39–48 行）接收一个`View`对象以及该 View 的 OnClick 和 OnLong 事件的监听器。View 代表 RecyclerView 中的一个项，它被传递给父类构造函数（第 42 行）。第 43 行存储了该项的`TextView`引用。第 46 行注册了 TextView 的点击事件。第 47 行注册了 TextView 的 OnLongClickListener，该器会为 TextView 的标签打开分享、编辑或删除对话框。当`RecyclerView.Adapter`创建新列表项的方法`onCreateViewHolder`（第 8.6.3 节）时会调用该构造函数。

```java
32 // RecyclerView.ViewHolder 的嵌套类，用于在
33 // RecyclerView 上下文中实现 view-holder 模式——
34 // 滚出屏幕视图的回收逻辑已由你处理
35 public static class ViewHolder extends RecyclerView.ViewHolder {
36 private final TextView textView;
```

**图 8.26** SearchesAdapter 作为 RecyclerView.ViewHolder 的嵌套 ViewHolder 子类。（第 1 部分，共 2 部分）

```java
// 配置 RecyclerView 项的 ViewHolder
public ViewHolder(View itemView,
    View.OnClickListener clickListener,
    View.OnLongClickListener longClickListener) {
    super(itemView);
    textView = (TextView) itemView.findViewById(R.id.textView);
}
// 为 itemView 附加监听器
itemView.setOnClickListener(clickListener);
itemView.setOnLongClickListener(longClickListener);
```

**图 8.26** SearchesAdapter 作为 RecyclerView.Adapter 的嵌套 ViewHolder 子类。（第 2 部分，共 2 部分）

### 8.6.3 重写的 RecyclerView.Adapter 方法

图 27 定义了重写的`RecyclerView.Adapter`方法，包括`onCreateViewHolder`（第 52–61 行）、`onBindViewHolder`（第 64–67 行）和`getItemCount`（第 70–73 行）。

```java
// 设置新的列表项及其 ViewHolder
@Override
public ViewHolder onCreateViewHolder(ViewGroup parent,
    int type) {
    // 填充 list_item
    View view = LayoutInflater.from(parent.getContext()).inflate(
        R.layout.list_item, parent, false);
    // 为 item 创建 ViewHolder
    return (new ViewHolder(view, clickListener, longClickListener));
}
// 设置项的文本
@Override
public void onBindViewHolder(ViewHolder holder, int position) {
    holder.textView.setText(tags.get(position));
}
// 返回项的数量
@Override
public int getItemCount() {
    return tags.size();
}
```

**27** | SearchesAdapter 重写的 RecyclerView.Adapter 方法 onCreateViewHolder onBindViewHolder 和 getItemCount

#### 重写的 onCreateViewHolder 方法

第 52–61 行通过重写的`RecyclerView.Adapter`方法`onCreateViewHolder`设置了新的列表项及其 ViewHolder。

#### 重写的 onBindViewHolder 方法

第 64–67 行通过重写的`RecyclerView.Adapter`方法`onBindViewHolder`设置了项的文本。该方法接收：

#### 重写的 getItemCount 方法

第 70–73 行通过重写的`RecyclerView.Adapter`方法`getItemCount`获取 RecyclerView 需要的项总数。

## 8.7 ItemDecorator RecyclerView.Decoration 的子类

`RecyclerView.Decoration`用于在项之间绘制装饰品（图 28）。`ItemDecorator`类在第 17–18 行绘制分割线。

```java
// ItemDecorator.java
// 定义 RecyclerView 项之间装饰品的类；
// 根据 tags 绘制项之间的分割线
package com.detail.twittersearches;

import android.content.Context;
import android.graphics.Canvas;
import android.graphics.drawable.Drawable;
import android.support.v7.widget.RecyclerView;
import android.view.View;

class ItemDecorator extends RecyclerView.Decoration {
    private final Drawable divider;
```

**图 28.2** | ItemDecorator 作为 RecyclerView.Decoration 的子类绘制项之间的水平线（第 1 部分，共 2 部分）

```java
// 构造函数加载内置 Android item divider
public ItemDecorator(Context context) {
    int[] attrs = {android.R.attr.divider};
    divider = context.obtainStyledAttributes(attrs).getDrawable(0);
}
// 在 RecyclerView 上绘制列表项
@Override
public void onDrawOver(Canvas c, RecyclerView parent,
    RecyclerView.State state) {
    super.onDrawOver(c, parent, state);
    // 计算所有分割线的左右 x 坐标
    int left = parent.getPaddingLeft();
```



```java
int right = parent.getWidth() - parent.getPaddingRight();

// 为每个项下方绘制一条线

for (int i = 0; i < parent.getChildCount(); i++) {

    View item = parent.getChildAt(i); // 获取项

    // 计算当前分割线的上下 y 坐标

    int top = item.getTop() + ((RecyclerView.LayoutParams)item).bottomMargin;

    int bottom = top + divider.getIntrinsicHeight();

    // 使用计算出的边界绘制 divider

    divider.setBounds(left, top, right, bottom);

    divider.draw(c);

}
```

## 320 第 8 章 Twitter 搜索应用

通过调用`RecyclerView`的`getWorld`并减去调用`RecyclerView.getPaddingRight`方法的结果，该方法返回`RecyclerView`右侧边缘与其内容之间的内边距量。

第 32–43 行通过遍历所有最后一个项目并在每个项目下方绘制分割线，在`RecyclerView`的`Canvas`上绘制分割线。第 33 行获取并存储`RecyclerView`项目项。第 36–37 行计算分割线的 y 坐标，使用项目底部的 y 坐标加上该项目的外边距（margin）。第 38 行计算分割线的底部 y 坐标，使用顶部的 y 坐标加上分割线的高度——由`Drawable.getIntrinsicHeight`返回。第 41 行设置分割线的边界（bounds），第 42 行将其绘制到...

### 8.8 关于 Fabric 的说明：Twitter 的新开发平台

在第 7 章中，你使用了 REST 服务来获取天气预报。Twitter 提供了丰富的 REST Web 服务，以便将 Twitter 功能集成到你的应用中。使用这些 Web 服务需要 Twitter 开发者帐户和特殊的身份验证。本章的重点不在于如何使用 Twitter Web 服务。出于此原因，应用执行搜索就像你在浏览器的 Twitter 网站上输入一样。Twitter 网站将结果直接返回给设备的浏览器进行显示。

直接使用第 7 章的技术操作 Twitter Web 服务可能是具有挑战性的。现在意识到这一点可以让你选择 Fabric——一个适用于 Android 和 iOS 的强型移动开发平台。Fabric 将 Twitter Web 服务的细节封装在库中，你可以将这些库集成到项目中，让开发者能够更容易为他们的应用添加 Twitter 功能。此外，你还可以添加移动身份管理（称为 Digits；用于网站和应用的用户登录）、基于广告的变现能力（称为 MoPub）以及崩溃报告（称为 Crashlytics）。

要使用 Fabric，请在以下地址注册：

```text
https://get.fabric.io/
```



并安装 Android Studio 插件。安装完成后，你只需点击 Android Studio 工具栏上的插件图标，并按照步骤将 Fabric 库添加到你的项目中即可。上述网站还提供了丰富的 Fabric 文档和教程。

## 8.9 总结

在本章中，你创建了 Twitter 搜索应用。你使用`SharedPreferences`文件来存储和维护代表用户使用过的 Twitter 搜索的关键值对。

我们引入了`RecyclerView`（来自`android.support.v7.widget`包）——这是一个灵活、可定制的视图，你可以控制应用如何显示滚动列表。你学会了`RecyclerView`支持不同的布局管理器，并使用`LinearLayoutManager`（`RecyclerView.LayoutManager`的子类）将此应用的`RecyclerView`项目项垂直排列。

我们再次使用了视图持有者模式（view-holder pattern）来复用滚动出屏幕的视图。我们了解到`RecyclerView`正规范了视图持有者模式，使其成为强制要求。你创建了`RecyclerView.Adapter`的子类将`RecyclerView`的列表项绑定到数据。你还创建了`RecyclerView.ViewHolder`的子类来维护每个列表项值的引用以便复用。为了在`RecyclerView`项目之间显示装饰元素，你定义了`RecyclerView.ItemDecoration`的子类，在`RecyclerView`上绘制分割线。

你使用了隐式 Intent（implicit Intents），你没有指定处理每个 Intent 的精确组件。你使用其中一个来启动设备的默认浏览器，根据嵌入在 URL 中的搜索查询显示 Twitter 搜索结果；另一个显示意图选择器（Intent chooser），允许用户从多种可以共享文本的应用程序中进行选择。

最后，你显示了一个包含选项列表的`AlertDialog`，用户可以从中仅选择一个。你使用`AlertDialog.Builder.setItems`方法来指定包含显示选项名称的`String`数组，并设置当用户触摸其中选项时被调用的事件处理器。

在第 9 章中，我们将构建数据库驱动的地址录应用，它提供了快速方便地访问存储的联系人信息，以及添加联系人、删除联系人和编辑现有联系人的功能。你将学习如何在 GUI 中动态切换`Fragment`，并提供优化手机和平板电脑屏幕区域的布局。

## 9 地址录应用

`FragmentTransactions`与`Fragment`后退栈，`SQLite`，`SQLiteDatabase`，`SQLiteOpenHelper`，`ContentProvider`，`ContentResolver`，`Loader`，`LoaderManager`，`Cursor`和 GUI 样式

![](img/8c2e5496308864b3b07ddbd4401c4f77_358_0.png)

### 目标

在本章中，你将：

- 使用`FragmentTransactions`和后退栈从 GUI 中动态挂载和卸载`Fragment`。
- 使用`RecyclerView View`显示来自数据库的数据。
- 使用`SQLiteOpenHelper`创建数据库。
- 使用`SQLiteDatabase`与数据交互。
- 使用`ContentProvider`提供数据。
- 使用`ContentResolver`查询数据。
- 使用`Loader`和`LoaderManager`异步加载数据。
- 使用`Cursor`导航结果。
- 使用 GUI 样式对应用进行样式化。

#### 9.1 引言

#### 9.2 测试地址录应用

- 添加联系人
- 查看联系人
- 编辑联系人
- 删除联系人

#### 9.3 技术

- `FragmentTransactions`与 GUI
- `SQLite`数据库
- `ContentProvider`和`ContentResolver`
- `LoaderManager`和`Loaders`
- 定义样式和属性

#### 9.4 构建 UI 和资源

- 创建项目
- `strings.xml`
- `styles.xml`
- `textview.xml`
- `MainActivity.layout`
- `ContactsFragment.layout`
- `DetailFragment.layout`
- `AddEditFragment.layout`

#### 9.5 本节概述

#### 9.6 数据库类

#### 9.7 `AddressDatabaseHelper`类

#### 9.8 `AddressBookProvider`类

- `AddressBookProvider`字段
- `create and get`
- `query`
- `insert`
- `update`
- `delete`

#### 9.9 `MainActivity`类

- 父类、实现的接口
- `onCreate`
- `ContactsFragment.ContactsFragmentListener`
- `displayContact`
- `displayAddFragment AddEdit`
- `DetailFragment.DetailListener`
- `AddEditFragment.AddEditFragmentListener`

#### 9.10 `ContactsFragment`类

- 父类和实现的接口
- `ContactsFragmentListener`
- 字段
- `onattach, onDestroy, onCreate`
- `onActivityCreated`
- `updateContactList`
- `Loader.Callback`

#### 9.11 `ContactsAdapter`类

#### 9.12 `AddDetailFragment`类

- 父类和实现的接口
- `AddDetailFragmentListener`
- 字段
- `onattach, onDestroy, onCreate`
- `TextView textChangeListener`和`updateStateSaveButtonUI`
- `View,OnClickListener listenerButtonClicked`回调和方法`saveContact`
- `Loader.Callback`

#### 9.13 `DetailFragment`类

- 父类和实现的接口
- `DetailFragmentListener`
- 字段
- `onattach, onDestroy, onCreate`
- `onOptions`和`onOptionsItemsSelected`
- `deleteContact`和`DialogFragment confirmDelete`
- `Loader.Callback`方法

#### 9.14 总结

## 9.1 简介

通讯录应用（图 9.1）提供了对存储在设备 SQLite 数据库中的联系人信息的便捷访问。你可以：

- 按字母顺序滚动联系人列表
- 通过点击联系人列表中的联系人来查看其详情
- 添加新联系人
- 编辑或删除现有联系人。

该应用提供了平板电脑布局（图 9.2），该布局始终在屏幕的三分之一处显示联系人列表，并使用屏幕剩余的三分之二显示所选联系人的数据，或用于添加和编辑联系人的界面。

a) 联系人列表

b) 用户点击联系人列表中的 Paul 后显示的详情

![](img/8c2e5496308864b3b07ddbd4401c4f77_360_0.png)

**图 9.1** | 联系人列表和所选联系人的详情。

a) 在手机或平板电脑的横屏模式下，应用图标将与其文本一同显示

![](img/8c2e5496308864b3b07ddbd4401c4f77_361_0.png)

**图 9.2** | 在平板电脑上横屏运行的通讯录。

此应用展示了多项技术：

- 你将使用`FragmentTransactions`动态添加或从 Activity 的 GUI 中移除`Fragment`。你还将利用`Fragment`后退栈来启用返回按钮支持，以便用户可以通过已显示的`Fragment`向后导航。
- 你将在`RecyclerView`中显示数据。
- 你将通过`SQLiteOpenHelper`的子类创建并打开数据库。
- 你将使用`ContentProvider`、`ContentResolver`和`SQLiteDatabase`对象来执行数据库的插入、更新、删除和查询操作。
- 你将使用`LoaderManager`和`Loaders`在 GUI 线程之外异步执行数据库访问并在 GUI 线程中接收结果。
- 最后，你将定义包含主 GUI 属性和值的样式，然后将其应用到多个 GUI 组件。

首先，你将对应用进行试运行。然后，我们将概述构建该应用所使用的技术。接下来，你将创建应用的 GUI 和资源文件。最后，我们将遍历应用的完整源代码，更详细地讨论应用的新功能。

## 9.2 试运行通讯录应用

### 打开并运行应用

打开 Android Studio，从书籍示例中的`AddressBook`文件夹中打开通讯录应用，然后在 AVD 或设备上执行该应用。这将构建项目并运行它。

### 9.2.1 添加联系人

第一次运行应用时，联系人列表将是空的。点击`+` `FloatingActionButton`显示添加新条目的屏幕（图 9.3）。该应用要求每个联系人都必须有一个名称，因此只有当`Name` `EditText`不为空时，`(P)` `FloatingActionButton`才会出现。在添加联系人信息后，点击`P`将联系人存储在数据库中并返回应用主界面。如果你选择不添加联系人，只需点击设备的返回键返回主界面。如果需要，可以添加更多联系人。在平板电脑上，添加联系人后，新联系人的详情将显示在联系人列表旁边（图 9.2）。注意，在平板电脑上，联系人列表始终显示。

a) 点击`FloatingActionButton`添加新联系人

b) 联系人的`Fragment`

![](img/8c2e5496308864b3b07ddbd4401c4f77_362_0.png)

**图 9.3** | 向数据库添加联系人。

### 9.2.2 查看联系人

在手机或手机 AVD 上，点击你刚刚添加的联系人名称以查看其详情（如图 9.1 所示）。同样，在平板电脑上，详情会自动显示在联系人列表的右侧（图 9.2）。

### 9.2.3 编辑联系人

查看联系人详情时，点击应用栏以显示填充了联系人数据的`EditText`（图 9.4）。根据需要编辑数据，然后点击`FloatingActionButton`将联系人存储在数据库中并返回应用栏。如果你选择不编辑联系人，只需点击设备的返回键返回上一个屏幕。在平板电脑上，更新后的联系人详情将显示在联系人列表的右侧。

![](img/8c2e5496308864b3b07ddbd4401c4f77_363_0.png)

**图 9.4** | 编辑联系人数据。

### 9.2.4 删除联系人

在查看联系人详情时，点击应用栏删除该联系人。对话框将要求你确认此操作（图 9.5）。点击`DELETE`将从数据库中移除该联系人，应用将显示更新后的联系人列表。点击`CANCEL`则保留该联系人。

## 第 9 章 通讯录应用

联系人详情

删除所选联系人

![](img/8c2e5496308864b3b07ddbd4401c4f77_364_0.png)

**图 9.5** | 从数据库中删除联系人。

## 9.3 技术概述

本节介绍了你将用于构建通讯录的功能。

### 9.3.1 使用`FragmentTransactions`显示`Fragment`

在早期的应用中，你使用 Activity 来显示`Fragment`。在本应用中，你将使用`FragmentTransactions`显示联系人列表——一次显示一个。此外，你将使用 Android 的后退栈（一种后进先出 (LIFO) 顺序存储`Fragment`的结构）来提供返回按钮支持。关于`Fragment`和`FragmentTransactions`的更多信息，请访问：

http://developer.android.com/guide/components/fragments.html

### 9.3.2 `Fragment`与 Activity 之间的数据通信

要在`Fragment`和 Activity 之间进行通信，最佳实践是通过 Activity 进行。通常，每个`Fragment`定义一个由 Activity 实现的接口。我们将使用这种技术在用户执行以下操作时通知`MainActivity`：

- 选择联系人进行显示
- 点击列表内容
- 点击详情`Fragment`的操作
- 完成编辑现有联系人或添加新联系人

### 9.3.3 操作 SQLite 数据库

信息存储在 SQLite 数据库。根据 sqlite.org，SQLite 是世界上部署最广泛的引擎之一。你将使用`SQLiteOpenHelper`（`android.database.sqlite`）的子类来简化数据库创建，并使用`SQLiteDatabase`（`android.database.sqlite`）操作内容。查询使用结构化查询语言 (SQL)。关于 Android SQLite 的更多信息：

http://developer.android.com/guide/topics/data-storage.html#db

### 9.3.4 `ContentProvider`和`ContentResolver`

`ContentProvider`（`package android.provider`）暴露应用数据供该应用或其他应用使用。Android 提供了内置的`ContentProvider`。例如除了向其他应用暴露数据外，`ContentProvider`还允许你的应用在用户搜索设备时提供自定义建议，并支持应用之间的复制粘贴操作。

通过这种方式，我们使用`ContentProvider`在 GUI 线程之外异步访问数据——这在使用 9.3.5 节引入的`Loader`和`LoaderManager`时是必要的。你将定义`ContentProvider`的子类，指定如何：

- 查询数据库以查找特定联系人或所有联系人
- 向数据库插入新联系人
- 更新数据库中的现有联系人
- 从数据库中删除现有联系人。

## 第9章 通讯录应用

### URIs

`ContentProvider`将定义 URIs，以帮助确定要执行的任务。例如，在应用中，`ContentProvider`的`query`方法被用于两种不同的查询——一个返回单个联系人的`Cursor`，另一个返回数据库中所有联系人名称的`Cursor`。

### `ContentResolver`

为了调用`ContentProvider`的查询、插入、更新和删除功能，我们将使用 Activity 的`buildContentResolver`（位于`android`包）的相应方法。如果你的`ContentProvider`向其他应用暴露其数据，则`ContentProvider`和`ContentResolver`将处理应用之间的通信。正如你所看到的，`ContentResolver`的方法接收的第一个参数是一个 Uri，它用于指定要访问的`ContentProvider`。每个`ContentResolver`都会调用`ContentProvider`的相应方法，该方法使用 Uri 来帮助确定要执行的任务。有关`ContentProviders`和`ContentResolvers`的更多信息，请参见：

http://developer.android.com/guide/topics/providers/content-providers.html

## 9.3.5 `Loader`和`LoaderManager`——异步数据库访问

正如我们所说的，阻塞执行直到完成的耗时操作（例如文件和数据库访问）应该在 GUI 线程之外执行。这有助于保持应用程序的响应，并避免在 Android 确定 UI 响应时出现“应用未响应（ANR）”对话框。`Loaders`和`LoaderManager`帮助你从任何 Activity 或 `Fragment`执行异步数据访问。

### `Loader`

`Loader`（位于`android.content`包）执行异步数据访问。在与`ContentProvider`交互以加载和操作数据时，你通常会使用`CursorLoader`——它是`AsyncTaskLoader`的子类，使用`AsyncTask`在单独线程中执行数据访问。`Loaders`还负责：

- 监控相应数据源的变化，并为相应的 Activity 或 `Fragment`提供更新的数据。
- 当发生配置更改时，重新连接到上一个`Loader`的`Cursor`，而不是执行新查询。

### `LoaderManager`和`LoaderManager.LoaderCallbacks`

Activity 或 `Fragment`的 loaders 由其`LoaderManager`（位于`android.app`包）创建并管理，`LoaderManager`将每个`Loader`的生命周期与其 Activity 或 `Fragment`的生命周期绑定。此外，`LoaderManager`会调用`LoaderManager.LoaderCallbacks`接口的方法，当`Loader`如下情况时通知 Activity 或 `Fragment`：

- 应该被创建，
- 完成数据加载，或
- 被重置且数据不再可用。

## 9.4 构建 GUI 和资源文件

你将在该应用的多个`Fragment`子类中使用`Loaders`和`LoaderManager`。有关`Loaders`和`LoaderManager`的更多信息，请参见：

http://developer.android.com/guide/components/loaders.html



### 9.3.6 定义样式并将其应用到 GUI 组件

你可以将通用的 GUI 属性-值对定义为样式资源（第 9.4 节）。然后，你可以通过 `style` 属性将样式应用到所有共享这些值的组件（第 9.4 节）。你对样式的任何更改都会自动应用到所有使用该样式的 GUI 组件。我们使用此样式到 `TextViews` 上，以显示联系人的信息。有关样式的更多信息，请访问：

```
http://developer.android.com/guide/topics/ui/themes.html
```

### 9.3.7 设置 TextView 背景

默认情况下，`TextView` 没有边框。要定义边框，你可以指定 `TextView` 的 `background` 属性值。`Drawable` 可以是一幅图像，在本应用中，你将在资源文件中（第 9.4.6 节）将 `Drawable` 定义为一个形状。像图像一样，此类 `drawable` 的资源定义在应用的一个（或多个）`drawable` 文件夹中。有关 `drawable` 资源的更多信息，请访问：

```
http://developer.android.com/guide/topics/resources/drawable-resource.html
```

## 9.4 构建 GUI 和资源文件

在本节中，你将创建通讯录的额外的 Java 源代码文件、资源文件和 GUI 布局文件。

### 9.4.1 创建项目

使用 `Blank Activity` 模板创建一个新项目。在配置项目时，勾选 `Fragment` 复选框。在“Create New Project”对话框的“New Project”步骤中，指定以下值：

- Application name（应用名称）：`Address Book`
- Company Domain（公司域名）：`detail.com`（或你自己的域名）

按照你在早期应用中使用的步骤为项目配置 Java SE 7。按照第 8.4.3 节的步骤将 `RecyclerView` 库添加到此项目中。在 `colors.xml` 中，将 `colorAttribute` 的值更改为 `#FF408L`（注：此处原文可能为误，通常为颜色颜色值）。

### 9.4.2 创建应用的类

当你创建此项目时，Android Studio 会为你定义好 `MainActivity` 和 `MainActivityFragment` 类。在本应用中，我们将 `MainActivity` 重命名为 `ContactsFragment`。操作步骤如下：

1. 在编辑器中打开 `MainActivityFragment` 类。
2. 右键点击类名并选择 `Refactor > Rename...`。IDE 会高亮类名以进行编辑。
3. 输入 `ContactsFragment` 并按回车。IDE 会重命名该类及其构造函数，并更改类的名称。

```java
package com.detail.addressbook
```

该应用由七个额外的类组成，你必须将它们添加到项目中（`File > New Java Class`）。`com.detail.addressbook` 中的额外类有：

- 类 `ContactsAdapter` 是 `RecyclerView.Adapter` 的子类，为 `Fragment` 的 `RecyclerView` 提供数据。
- 类 `AddEditFragment` 是 `Fragment` 的子类，为添加新联系人或编辑现有联系人提供 GUI。
- 类 `DetailFragment` 是 `Fragment` 的子类，为查看和删除联系人详情提供 GUI。
- 类 `ItemDivider` 是 `RecyclerView.ItemDecoration` 的子类，在项目之间绘制一条水平线。
- 类 `DatabaseHelper` 是 `SQLiteOpenHelper` 的子类，用于创建数据库。
- 类 `AddressContentProvider` 是 `ContentProvider` 的子类，定义如何操作数据库。
- 类 `ContactsAdapter` 是 `RecyclerView.Adapter` 的子类，为 `Fragment` 的 `RecyclerView` 提供数据。

要创建这些：
1. 在 `Project` 窗口中，右键点击包 `com.detail.addressbook` 并选择 `New > Java Class`。
2. 命名为 `ContactsAdapter`。

将以下类添加到 `com.detail.addressbook`：

```java
package com.detail.addressbook
```

`DatabaseHelper` 描述数据库表。`DatabaseHelper` 是 `SQLiteOpenHelper` 的子类，用于创建数据库并访问它。`AddressContentProvider` 是 `ContentProvider` 的子类，定义如何操作数据库。要创建这个，使用 `New > ContentProvider`。为 `authorities` 指定 `com.detail.addressbook` 并勾选 `Exported` 复选框，然后点击 `Finish`。`Exported` 表示此 `ContentProvider` 仅供应用使用。

IDE 在 `AndroidManifest.xml` 中声明 `ContentProvider`。此外，IDE 将 `ContentProvider` 声明为嵌套在 `<application>` 元素中的 `<provider>` 元素。这是向 Android 系统注册 `ContentProvider` 的必要步骤。我们在 9.5 节中概述所有类，并在 9.6 节讨论它们的细节。

### 9.4.3 添加应用图标

使用 Android Studio 的 `Vector Asset Studio`（第 4.4.9 节）将 Material Design 图标 (+)、编辑和删除添加到项目中——这将作为 `FloatingActionButton` 使用。添加矢量图标后，进入 `res/drawable` 文件夹，打开每个 XML 文件并将 `<path>` 元素的 `android:fillColor` 更改为 `color/white`

```
"color/white"
```

### 9.4.4 strings.xml

图 9.6 显示了此应用的资源名称和对应的值。双击 `res/values` 文件夹中的 `strings.xml` 以显示创建这些字符串的资源编辑器。

| 资源名称 | 值 |
|--- |--- |
| `menuitem_edit` | `Edit` |
| `menuitem_delete` | `Delete` |
| `hint_name_required` | `Name (Required)` |
| `hint_email` | `E-Mail` |
| `hint_phone` | `Phone` |
| `hint_street` | `Street` |
| `hint_city` | `City` |
| `hint_state` | `State` |
| `hint_zip` | `Name:` |
| `label_name` | `E-Mail:` |
| `label_phone` | `Phone:` |
| `label_street` | `Street:` |
| `label_city` | `City:` |
| `label_state` | `State:` |
| `label_zip` | `Zip:` |
| `confirm_title` | `Are You?` |
| `confirm_message` | `This will permanently delete the contact` |
| `button_cancel` | `Cancel` |
| `button_delete` | `Delete` |
| `contact_added` | `Contact added successfully` |
| `contact_not_added` | `Contact was not added due to an error` |
| `contact_updated` | `Contact updated` |
| `contact_not_updated` | `Contact was not updated due to an error` |

**图 9.6** 通讯录应用使用的字符串资源（共 2 部分的第 1 部分）。

## 第9章 通讯录应用

| 资源名称 | 值 |
| --- | --- |
| `invalid_query_uri` | `无效的查询 Uri:` |
| `invalid_insert_uri` | `无效的插入 Uri:` |
| `invalid_update_uri` | `无效的更新 Uri:` |
| `invalid_delete_uri` | `无效的删除 Uri:` |
| `insert_failed` | `插入失败: s` |

> **图 9.6** 通讯录应用中使用的字符串资源。（2部分的2部分。）

## 9.4.5 styles.xml

在本节中，你将为显示联系人信息的 `DetailFragment` 的 `TextView` 定义样式（第 9.4.9 节）。与其他资源一样，样式放置在应用的 `res/values` 文件夹中。IDE 会创建一个包含预定义样式的 `styles.xml` 文件。你创建每个新样式都指定一个名称，用于将样式应用于 UI 组件，并指定一个或多个指定要应用属性值的项目。若要创建新样式，请在应用的 `res/values` 文件夹中打开 `styles.xml` 文件，并在文件结束的 `<resources>` 标签之前添加代码。完成后，保存并关闭 `styles.xml`。

```xml
<style name="ContactLabelTextView">
  <item name="android:layoutWidth">wrap_content</item>
  <item name="android:layoutHeight">wrap_content</item>
  <item name="android:layoutGravity">right|center_vertical</item>
</style>

<style name="ContactTextView">
  <item name="android:layoutWidth">wrap_content</item>
  <item name="android:layoutHeight">wrap_content</item>
  <item name="android:layoutGravity">fill_horizontal</item>
  <item name="android:textSize">16sp</item>
  <item name="android:background">@drawable/textview_border</item>
</style>
```

> **图 9.7** 用于格式化 `DetailFragment` `TextViews` 的新样式。

第 1–5 行定义了一个名为 `ContactLabelTextView` 的新样式，定义了布局属性 `layout_width`、`layout_height` 和 `layout_gravity` 的值。你将此样式应用于显示每个联系人信息的 `DetailFragment` 的 `TextViews`。每个新样式由一个命名多个 `item` 元素的 `style` 元素组成。`item` 的名称指定属性，当样式应用于视图时，其值将被分配给该属性。第 7–13 行定义了另一个名为 `ContactTextView` 的样式，该样式将应用于显示联系人信息的 `DetailFragment` 的 `TextViews`。第 12 行将 `android:background` 属性设置为第 9.4.6 节中定义的 `drawable` 资源。

## 9.4 构建 GUI 和资源文件

### 9.4.6 textview_border.xml

你在上一节中创建的 `EditTextView` 样式定义了你用于显示联系人详情的 `TextViews` 的外观。你指定了一个 `Drawable`（即图像或图形）`@drawable/textview_border` 作为 `TextView` 背景的值。在本节中，你将在应用/`drawable/` 文件夹中定义该 `Drawable`。要定义该 `Drawable`：

- 1. 右键点击 `drawable/` 文件夹并选择 `New`（新建）> `Drawable resource file`（Drawable 资源文件）。
- 2. 指定 `textview_border.xml` 为文件名并点击 `OK`。
- 3. 将文件内容替换为图 9.8 中的 XML 代码。

```xml
<xml version="1.0" encoding="utf-8">
<shape xmlns:android="http://schemas.android.com/apk/res/android"
    android:shape="rectangle">
    <corners android:radius="5dp"/>
    <stroke android:width="1dp" android:color="#555" />
    <padding android:top="10dp" android:left="10dp" android:bottom="10dp"
    android:right="10dp"/>
</shape>
```

图 9.8 | 你用于放在 `TextView` 上的 `Drawable` 的 XML 元素 `shape` 属性。

*shape* 元素的 `shape` 属性（第 3 行）的值可以是 `"rectangle"`（矩，在本例中使用）、`"oval"`（椭圆形）或 `"ring"`（环形）。*corners* 元素（第 4 行）指定矩形的半径，使角变为圆角。*stroke* 元素（第 5 行）定义了矩形的宽度和线条颜色。*padding* 元素（第 6–7 行）指定了应用此 `Drawable` 的元素内容周围的内边距。你必须单独指定上、左、下、右内边距值。形状的完整细节可以查看：

```
http://developer.android.com/guide/topics/resources/drawable-html#Shape
```

## 9.4.7 MainActivity 布局

默认情况下，`MainActivity` 包含一个带有 `FloatingActionButton` 的布局，并包含了布局文件 `content_main.xml` 内容。在此应用中，我们在应用的 `Fragments` 中使用 `FloatingActionButton`。因此，请打开 `res/layout` 文件夹中的 `activity_main.xml` 并删除预定义的 `FloatingActionButton`。此外，设置 `CoordinatorLayout` 的 id——我们将从 `MainActivity.onCreate` 中移除配置 `FloatingActionButton` 的代码。

#### 手机布局：content_main.xml

在此应用中，你提供了两个 `content_main.xml` 布局包含在 `MainActivity` 中——一个用于手机尺寸设备，另一个用于平板尺寸设备。对于手机布局，打开 `res/layout` 文件夹中的 `content_main.xml` 并将其内容替换为图 9.9 中的 XML。`MainActivity` 动态在名为 `fragmentContainer` 的 `FrameLayout` 中显示应用的 `Fragments`。此布局填充了可用空间：

```xml
<FrameLayout
android:id="@id/fragmentContainer"
xmlns:android="http://schemas.android.com/apk/res/android"
android:layout_width="match_parent"
android:layout_height="match_parent">
```

图 9.9 | `content_main.xml` 用于手机。

#### 平板布局：content_main.xml

在此应用中，你提供了两个 `content_main.xml` 布局包含在 `MainActivity` 中——一个用于手机尺寸设备，另一个用于平板尺寸设备。对于手机布局，打开 `res/layout` 文件夹中的 `content_main.xml` 并将其内容替换为图 9.9 中的 XML。`MainActivity` 动态在名为 `fragmentContainer` 的 `FrameLayout` 中显示应用的 `Fragments`。此布局填充了可用空间：

```xml
<xml version="1.0" encoding="utf-8"?>
<LinearLayout
xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
android:orientation="vertical"
android:padding="16dp">

<FrameLayout
android:id="@id/fragmentContainer"
android:layout_width="match_parent"
android:layout_height="match_parent">
</FrameLayout>

</LinearLayout>
```



## 9.4.7 `MainActivity` 布局

默认情况下，`MainActivity` 包含一个带有 `FloatingActionButton` 的布局，并包含布局文件 `content_main.xml` 的内容。在此应用中，我们在应用的 `Fragments` 中使用 `FloatingActionButton`。因此，请打开 `res/layout` 文件夹中的 `activity_main.xml`，并删除预定义的 `FloatingActionButton`。此外，设置 `CoordinatorLayout` 的 `id`——我们将从 `MainActivity.onCreate` 中移除配置 `FloatingActionButton` 的代码。

### 手机布局：`content_main.xml`

在此应用中，你提供了两个 `content_main.xml` 布局包含在 `MainActivity` 中——一个用于手机尺寸设备，另一个用于平板尺寸设备。对于手机布局，打开 `res/layout` 文件夹中的 `content_main.xml`，并将其内容替换为图 9.9 中的 XML。`MainActivity` 动态在名为 `fragmentContainer` 的 `FrameLayout` 中显示应用的 `Fragments`。此布局填充了可用空间：

```xml
<FrameLayout
    android:id="@id/fragmentContainer"
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">
```

### 平板布局：`content_main.xml`

在此应用中，你提供了两个 `content_main.xml` 布局包含在 `MainActivity` 中——一个用于手机尺寸设备，另一个用于平板尺寸设备。对于手机布局，打开 `res/layout` 文件夹中的 `content_main.xml`，并将其内容替换为图 9.9 中的 XML。`MainActivity` 动态在名为 `fragmentContainer` 的 `FrameLayout` 中显示应用的 `Fragments`。此布局填充了可用空间：

```xml
<xml version="1.0" encoding="utf-8"?>

<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <FrameLayout
        android:id="@id/fragmentContainer"
        android:layout_width="match_parent"
        android:layout_height="match_parent">
    </FrameLayout>

</LinearLayout>
```

# 第 9 章 通讯录应用

```xml
<android.support.widget.FloatingActionButton
    android:id="@id/addButton"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_gravity="top"
    android:layout_margin="@dim/fab_margin"
    android:src="@drawable/ic_add_24dp" />

</FrameLayout>
```

图 9.11 `fragment_counts.xml` 布局。（2.2 的第 2 部分）

## 9.4 `DetailFragment` 的布局

当用户在 `MainActivity` 中点击联系人时，应用会显示 `DetailFragment`（图 9.12）。该 fragment 的布局（`fragment_details.xml`）由一个 `ScrollView` 组成，其中包含一个两列 `TextView` 的垂直 `GridLayout`。`TextView` 为屏幕上无法完全显示的大量内容提供滚动功能。

我们使用 `ScrollView` 来确保如果设备没有足够的垂直空间显示图 9.12 中的所有 `TextView`，用户也可以滚动查看联系人的详情。对于此 fragment，我们创建了一个新的 `fragment_details.xml` 资源文件，并将 `ScrollView` 指定为根元素。创建文件后，我们向 `ScrollView` 中添加了 `GridLayout`。

![](img/8c2e5496308864b3b07ddbd4401c4f77_374_0.png)

图 9.12 带有其 `id` 属性值标签的 `DetailFragment` GUI 组件。

### `GridLayout` 设置

对于 `GridLayout`，我们将 `layout:width` 设置为 `match_parent`，`layout:height` 设置为 `wrap_content`，`columnCount` 设置为 2，并将 `useDefaultMargins` 设置为 `true`。`layout:height` 的值允许确定 `ScrollView` 的实际高度并决定是否提供滚动。如图 12 所示，向 `GridLayout` 添加 `TextView`。

### 左列 `TextView` 设置

对于左列中的每个 `TextView`，按照图 9.12 的指定设置 `TextView` 的 `id` 属性，并设置：

- `layout:row` 根据行号设置为 0–6 之间的值。
- `layout:count` 设置为 0。
- `text` 设置为 `strings.xml` 中相应的 String 资源。
- `style` 设置为 `@style/ContactLabelTextView`——样式资源使用 `@style/styleName` 语法指定。

### 右列 `TextView` 设置

对于右列中的每个 `TextView`，按照图 9.12 的指定设置 `TextView` 的 `id` 属性，并设置：

- `layout:row` 根据行号设置为 0–6 之间的值。
- `layout:count` 设置为 1。
- `style` 设置为 `@style/ContactTextView`。

### 9.4.10 `AddEditFragment` 的布局

当用户点击 `ContactsFragment` 中的浮动按钮（`FloatingActionButton`）或 `DetailFragment` 中的编辑项目时，`MainActivity` 使用 `fragment_edit.xml` 显示 `AddEditFragment`（图 9.3）。该 `RootLayout` 包含一个 `ScrollView` 和一个 `FloatingActionButton`。`ScrollView` 包含一个带有七个 `EditTextLayout` 的垂直 `LinearLayout`。

### `ScrollView` 设置

对于 `ScrollView`，我们将 `layout:width` 和 `layout:height` 设置为 `match_parent`。

### `LinearLayout` 设置

对于 `LinearLayout`，我们将 `layout:width` 设置为 `match_parent`，`layout:height` 设置为 `wrap_content`，并将 `orientation` 设置为垂直。然后我们添加了图 9.12 所示带有 `id` 的七个 `EditTextLayout`，每个项目的 `layout:width` 设置为 `match_parent`，`layout:height` 设置为 `wrap_content`。

### `EditText` 设置

我们在每个 `EditTextLayout` 中放置了一个 `EditText`，然后将其 `hint` 设置为 `strings.xml` 中相应的 String 资源。我们还设置了每个 `EditText` 的 `inputType` 和 `imeOptions` 属性。

对于显示软键盘的设备，`inputType` 指定了对应 `EditText` 使用的键盘。这允许我们根据用户在特定 `EditText` 中输入的数据类型来自定义键盘。为了在 `nameInputLayout` 中 `EditText` 的软键盘上显示下一个按钮：

![](img/8c2e5496308864b3b07ddbd4401c4f77_376_0.png)

**图 9.13** | 带有其 `id` 属性值的 `AddEditText` GUI 组件。此 GUI 的根组件是一个包含垂直 `GridLayout` 的 `ScrollView`。

对于 `phoneTextInputLayout`、`emailTextInputLayout`、`streetTextInputLayout`、`cityTextInputLayout` 和 `stateTextInputLayout`，我们将 `imeOptions` 属性设置为 `actionNext`。当其中一个 `EditText` 获取焦点时，点击会将焦点转移到布局中的下一个 `EditText`。

如果 `zipTextInputLayout` 中的 `EditText` 获取焦点，可以通过点击键盘按钮来隐藏软键盘——对于此 `EditText`，将 `imeOptions` 属性设置为 `actionDone`。

设置 `EditText` 的 `inputType` 以显示相应的键盘：

- `nameTextInputLayout` 的 `EditText`：勾选 `personName` 和 `textCapChars`——用于输入姓名并使首字母大写。
- `phoneTextInputLayout` 的 `EditText`：勾选 `phone`——用于输入电话号码。
- `emailTextInputLayout` 的 `EditText`：勾选 `email1Address`——用于输入电子邮件地址。
- `streetTextInputLayout` 的 `EditText`：勾选 `postalAddress` 和 `textCapWords`——用于输入地址并使首字母大写。
- `cityTextInputLayout` 的 `EditText`：勾选 `postalAddress` 和 `textCapWords`。
- `stateTextInputLayout` 的 `EditText`：勾选 `postalAddress` 和 `textCapCharacters`——确保缩写以大写显示。
- `zipTextInputLayout` 的 `EditText`：勾选 `number`——用于输入数字。

## 9.5 本章概述

## 9.6 `DatabaseDescription` 类

```java
// DatabaseDescription.java

// 描述此应用数据库的表名和列名，
// 以及 ContentProvider 所需的其他信息

package com.deitel.addressbook.data;

import android.content.ContentUris;
import android.net.Uri;
import android.net.provider.BaseColumns;

public class DatabaseDescription {

    // ContentProvider 的名称：通常是包名
    public static final String AUTHORITY =
        "com.deitel.addressbook.data";

    // 用于与 ContentProvider 交互的 base_URI
    private static final Uri BASE_CONTENT_URI =
        Uri.parse("content://" + AUTHORITY);
}
```

图 9.15 `DatabaseDescription` 类和声明语句。

### 9.6.2 嵌套类 `Contact`

嵌套类（图 9.16）定义了数据库的表名（第 21 行）、通过 `ContentProvider` 访问该表的 URI（第 24–25 行）以及表的列名（第 28–34 行）。该名称将由 `DatabaseHelper` 类（第 9.7 节）用于创建数据库。

方法 `buildContentUri` 用于为数据库中的特定记录创建一个 URI（第 37–39 行）。用于处理 `"content://"` URI 的 `ContentUri` 实用方法会在其第一个参数 URI 的末尾添加正斜杠（`/`）和记录 ID。对于每个数据库，你通常会有一个类似 `Contact` 的类。

```java
// 嵌套类定义 contacts 表的内容
public static final String TABLE_NAME = "contacts"; // 表名

// 用于 contacts 表的 Uri
public static final Uri CONTENT_URI =
    BASE_CONTENT_URI.appendPath(TABLE_NAME).build();

// 表中列的列名
public static final String COLUMN_NAME = "name";
public static final String COLUMN_PHONE = "phone";
public static final String COLUMN_EMAIL = "email";
public static final String COLUMN_STREET = "street";
public static final String COLUMN_CITY = "city";
public static final String COLUMN_STATE = "state";
public static final String COLUMN_ZIP = "zip";
```

图 9.16 `DatabaseDescription` 嵌套类 `Contact`。（2 部分中的第 1 部分。）

```java
// 为特定联系人创建 Uri
public static Uri buildContactUri(long id) {
    return ContentUris.withAppendedId(CONTENT_URI, id);
}
```

图 9.16 接下来需要的类。（2 部分中的第 2 部分。）

在数据库中，表现在有一个主键，可以唯一标识一行。在处理 `ListView` 和 `Cursor` 时，列名必须为 `"_id"`——Android 也将此用于 SQLite 数据库中的 ID 列。`RecyclerView` 不需要此要求，而我们正在使用 `Cursor` 和 SQLite 数据库。我们没有直接在类中定义此常量，而是实现了接口 `BaseColumns`（包名为 `provider`，第 20 行），该接口定义了值为 `"_id"` 的常量 `_ID`。

## 9.7 `AddressDatabaseHelper` 类

`AddressDatabaseHelper` 类（图 9.17）继承自抽象的 `SQLiteOpenHelper`，它可以帮助创建数据库并管理数据库版本更改。



// `AddressDatabaseHelper.java`

// 定义应用数据库的 `SQLiteOpenHelper` 类

`package com.detail1.address.data;`

`import android.content.Context;`

`import android.database.sqlite.SQLiteDatabase;`

`import android.database.sqlite.SQLiteOpenHelper;`

`import com.detail1.address.data.DatabaseDescription;`

`class AddressDatabaseHelper extends SQLiteOpenHelper {`

    `private static final String DATABASE_NAME = "AddressBook.db";`

    `private static final int DATABASE_VERSION = 1;`

    `public AddressDatabaseHelper(Context context) {`

        `super(context, DATABASE_NAME, null, DATABASE_VERSION);`

    `}`

    `@Override`

    `public void onCreate(SQLiteDatabase db) {`

        // 数据库创建时创建表的 SQL

        `final String CREATE_CONTACTS_TABLE =`

            `"CREATE TABLE " + Contact.TABLE_NAME + " (",`

`26 Contact.ID + " integer primary key, " +`

`27 Contact.COLUMN_NAME + " TEXT, " +`

`28 Contact.COLUMN_PHONE + " TEXT, " +`

`29 Contact.COLUMN_EMAIL + " TEXT, " +`

`30 Contact.COLUMN_STREET + " TEXT, " +`

`31 Contact.COLUMN_CITY + " TEXT, " +`

`32 Contact.COLUMN_STATE + " TEXT, " +`

`33 Contact.COLUMN_ZIP + " TEXT");";`

`34 db.execSQL(CREATE_TABLES); // 创建表表`

`35`

`36 }`

// 通常定义当模式更改时如何升级数据库

`38 @Override`

`39 public void onUpgrade(SQLiteDatabase db, int oldVersion,`

`40 int newVersion) {`

`41 }`

```
```

图 9.17 | `SQLiteOpenHelper` 的子类 `AddressBookDatabaseHelper` 定义了应用数据库。（2 部分中的第 2 部分）。

### 构造函数

构造函数（16–18）简单地调用父类构造函数，该构造函数需要四个参数：

- 创建或打开数据库的 `context`，
- 数据库名称——如果你想使用内存数据库，此处可以为 `null`，
- `CursorFactory`——`null` 表示你希望使用默认的 `SQLiteCursorFactory`（适用于大多数应用），以及
- 数据库版本（从 1 开始）。

### 重写方法

你必须重写该类的抽象方法 `onCreate` 和 `onUpgrade`。如果数据库不存在，将调用 `SQLiteOpenHelper` 的 `onCreate` 方法创建它。如果提供的版本号高于存储在设备上的数据库版本，将调用 `SQLiteOpenHelper` 的 `upgrade` 方法来更新数据库。第 22–35 行指定了 `CREATE TABLE` 命令，第 24–33 行使用 `Constant` 类（第 9.6 节）构造字符串。在这种情况下，表包含一个整数主键字段（`_id_`）以及其他列的文本字段。第 34 行使用 `execSQL` 执行 `CREATE TABLE` 命令。我们只需要一个空的 `onCreate`。

## 9.8 `AddressBookProvider` 类

`ContentProvider` 子类定义了如何对应用数据库执行查询、插入和删除操作。

> 预防提示 9.1
> `ContentProviders` 可以被多个线程和多个进程调用，要注意它们默认不提供任何同步。然而，`SQLite` 对数据库访问进行同步，因此在此应用中没有必要提供同步机制。

### 9.8.1 `AddressBookProvider` 字段

`AddressBookProvider` 类（图 9.18）定义了几个字段：

- `dbHelper`（第 17 行）是 `AddressDatabaseHelper` 对象的引用，用于创建和写入数据库
- `uriMatcher`（第 20–21 行）是一个 `UriMatcher` 对象（包 `android.content`）。`ContentProvider` 使用 `UriMatcher` 在其查询、插入和删除方法中确定要执行的操作。
- `UriMatcher` 包含整数 `_CONTACT` 和 `CONTACT`（第 24–25 行）——`ContentProvider` 在其查询、插入和删除方法的 `switch` 语句中使用这些常量。

```java
// AddressBookContentProvider.java
// 用于传递数据库的 ContentProvider 类

package com.detail.addressdata;

import android.content.ContentProvider;
import android.content.ContentValues;
import android.content.UriMatcher;
import android.database.Cursor;
import android.database.SQLException;
import android.database.sqlite.SQLiteBuilder;
import android.net.Uri;
import com.detail.addressdata.AddressBookContentProvider extends ContentProvider;

public class AddressBookContentProvider extends ContentProvider {

    // 访问数据库
    private AddressDatabaseHelper dbHelper;

    // UriMatcher 帮助 ContentProvider 确定执行的操作
    private static final UriMatcher uriMatcher = 
        new UriMatcher(UriMatcher.NO_MATCH);

    // 与 UriMatcher 使用以确定操作的常量
    private static final int _CONTACT = 1; // 操作单个联系人
    private static final int CONTACT = 2; // 操作 contacts 表
```

图 9.18 | `AddressBookContentProvider` 字段。（2 部分中的第 1 部分。）

## 9.8 `AddressBookContentProvider` 类

```java
26 // static block to configure this ContentProvider's UriMatcher
27 static {
28     // Uri for Content with the specified id (#)
29     uriMatcher.addUri(DatabaseDescription.AUTHORITY,
30         Contact.TABLE_NAME + " /#*", ONE_CONTACT);
31
32     // Uri for Contacts table
33     uriMatcher.addUri(DatabaseDescription.AUTHORITY,
34         Contact.TABLE_NAME, CONTACTS);
35
36 }
```

![](img/8c2e5496308864b3b07ddbd4)

28–36 定义了一个静态块，用于将 `Uri` 添加到静态 `UriMatcher` 中——该块在类 `AddressBookContentProvider` 被加载到内存时执行。`UriMatcher` 的 `addUri` 方法接受三个参数：

- 代表 `ContentProvider` 权限的字符串（在本应用中 `DatabaseDescription`）
- 代表路径的字符串——调用 `ContentProvider` 的每个 `Uri` 都在权限和路径之后包含 `"/*/"`，`ContentProvider` 使用该路径来确定要执行的任务
- 当提供给 `ContentProvider` 的 `Uri` 与 `UriMatcher` 中存储的 `Uri` 匹配时，`UriMatcher` 返回的代码。

第 31–35 行添加了格式如下的 `Uri`：

```
content://com.deitel.addressbook.data/contacts/#
```

其中 `#` 是一个匹配数字字符字符串的通配符——在这种情况下，它是 `contacts` 表中某个联系人的唯一主键值。还有一个匹配任意字符数的通配符。当 `Uri` 匹配此格式时，`UriMatcher` 返回常量 `ONE_CONTACT`。

第 34–35 行添加了格式如下的 `Uri`：

```
content://com.deitel.addressbook.data/contacts
```

它代表整个 `contacts` 表。当我们讨论 `AddressBookContentProvider` 类的结果时，你将看到 `UriMatcher` 以及常量 `ONE_CONTACT` 和 `CONTACTS` 是如何使用的。

### 9.8.2 重写的 `onCreate` 和 `getType` 方法

你将使用 `ContentResolver` 来调用 `ContentProvider` 的方法。当 Android 接收来自 `ContentResolver` 的请求时，它会自动创建对应的 `ContentProvider` 对象——如果之前已经创建过，则使用现有的。当 `ContentProvider` 被创建时，Android 会调用其 `onCreate` 方法来配置该 `ContentProvider`（图 9.19，第 39–44 行）。第 42 行创建的 `AddressBook-Helper` 对象使 provider 能够数据库。当 provider 第一次被访问数据库时，将调用 `AddressBookDatabaseHelper` 对象的 `onCreate` 来创建数据库（图 9.17，第 22–35 行）。

```java
// 当 AddressBookContentProvider 创建时被调用
@Override
public boolean onCreate() {
    // 创建 AddressBookDatabaseHelper
    dbHelper = new AddressBookDatabaseHelper(getContext());
    return true; // ContentProvider 成功创建
}
```

```java
// 必须的方法：在此应用中未使用，因此我们返回 null
@Override
public String getType(Uri uri) {
    return null;
}
```

**图 9.19** | `ContentProvider` 方法 `onCreate` 和 `getType`。

**getType**（图 9.19，第 47–50 行）是一个必选的 `ContentProvider` 方法，在本应用中它简单地返回 `null`。这通常用于为具有特定 MIME 类型的 `uri` 创建并启动 `Intent`。Android 可以使用 MIME 类型来确定处理 `Intent` 的适当属性。

### 9.8.3 重写的 `query` 方法

重写的 `ContentProvider` `query`（图 9.20）从 provider 的数据源（在本例中为数据库）检索数据。该方法返回一个用于与数据库交互的 `Cursor`。`query` 方法接收五个参数：

- `uri`—代表要检索的数据的 `Uri`。
- `projection`—一个代表要检索的特定列的字符串。如果此参数为 `null`，则结果将包含所有列。
- `selection`—一个包含选择标准的字符串。这是 SQL 的 `WHERE` 子句，指定时不包含 `WHERE` 关键字。如果此参数为 `null`，则结果将包含所有行。
- `selectionArgs`—包含用于替换选择字符串中任何占位符 (`?`) 的参数的字符串。
- `sortOrder`—代表排序顺序的字符串。这是 SQL 的 `ORDER BY` 子句，指定时不包含 `ORDER BY` 键。如果此参数为 `null`，由 provider 决定顺序——除非你提供了适当的排序顺序，否则无法保证返回给 app 的结果顺序。

**SQLiteQueryBuilder**
第 58 行创建了一个 `SQLiteQueryBuilder`（包 `android.sqlite`），用于构建提交到 SQLite 数据库的 SQL 查询。第 59 行使用方法指定查询将从数据库的 `contacts` 表中选择数据。该方法的

```java
// 查询数据库
@Override
public Cursor query(Uri uri, String[] projection,
    String selection, String[] selectionArgs, String sortOrder) {

    // 为查询 contacts 表创建 SQLiteQueryBuilder
    SQLiteQueryBuilder queryBuilder = new SQLiteQueryBuilder();
    queryBuilder.setTables(Contact.TABLE_NAME);

    switch (matcher.match(uri)) {
    case ONE_CONTACT: // 选择指定 id 的联系人
        queryBuilder.appendWhere("contact_ID = ?" + uri.getLastPathSegment());
        break;
    case CONTACTS: // 选择所有联系人
        break;
    default:
        throw new UnsupportedOperationException(
            getContext().toString(R.string.invalid));
    }

    // 执行查询
    Cursor cursor = queryBuilder.query(dbHelper.getReadableDatabase(),
        projection, selection, selectionArgs, null, sortOrder);

    // 为更改注册游
    cursor.setNotificationUri(getContext().getContentResolver(), uri);
    return cursor;
}
```



图 9.20 | 重写的 `ContentProvider` 方法

### 查询数据库

第 74–75 行使用 `queryBuilder.query` 执行查询并返回结果的 `Cursor`。该方法的参数是：

- `SQLiteDatabase`—由 `getReadableDatabase()` 返回的只读数据库对象。
- `projection`—代表要检索的特定列的字符串。如果此参数为 `null`，则结果将包含所有列。
- `selection`—包含选择标准的字符串。这是 SQL 的 `WHERE` 子句，指定时不包含 `WHERE` 关键字。如果此参数为 `null`，则结果将包含所有行。
- `selectionArgs`—包含用于替换选择字符串中任何占位符（`?`）的参数的字符串。
- `groupBy`—包含分组标准的字符串。这是 SQL 的 `GROUP BY` 子句，指定时不包含 `GROUP BY` 关键字。如果此参数为 `null`，则不进行分组。
- `having`—当使用 `groupBy` 时，此参数是指示在结果中包含哪些组的字符串。这是 SQL 的 `HAVING` 子句，不包含 `HAVING` 关键字。如果此参数为 `null`，则结果中包含由 `groupBy` 指定的所有组。
- `sortOrder`—代表排序顺序的字符串。这是 SQL 的 `ORDER` 子句，指定时不包含 `ORDER BY` 关键字。如果此参数为 `null`，由 provider 决定此顺序。

第 61–71 行使用 `UriMatcher` 来确定要执行的操作。如果返回常量是 `ONE_CONTACT`，则选择后续 Uri 中指定 ID 的联系人：`content://com.deitel.addressbook.data/contacts/5`

### 注册游标监听更改

第 78 行调用游标的 `setNotificationUri` 以指示如果数据发生变化则应更新游标。此第一个参数是调用 `ContentProvider` 的 Resolver，第二个参数是调用 `ContentProvider` 的 `uri`。第 79 行返回包含查询结果的 `Cursor`。

### 9.8.4 重写的 `insert` 方法

重写的 `ContentProvider` 方法 `insert` 向 `contacts` 表添加新记录。`insert` 方法（图 9.21）接收两个参数：

- `uri`—代表要插入数据的表的 Uri。
- `values`—一个包含键值对的 `ContentValues` 对象，其中列名是键，每个键的值是要插入列中的数据。

第 87–106 行检查 `uri` 是否为 `contacts` 表——如果不是，则该 Uri 对于插入操作是非法的，且第 106–107 行抛出 `UnsupportedOperationException`。

## 9.8 AddressBookContentProvider 类

```java
// 在数据库中插入新联系

@Override
public Uri insert(Uri uri, ContentValues values) {
    Uri newContentUri = null;

    switch (uriMatcher.match(uri)) {
        case CONTACTS:
            // 插入新联系——成功后返回联系人的行 ID
            long rowId = dbHelper.getWritableDatabase().insert(
                Contact.TABLE_NAME, null, values);

            // 如果联系插入成功，则创建一个适当 Uri；
            // 否则，抛出异常
            if (rowId > 0) { // SQLite 行 ID 从 1 开始
                newContentUri = Contact.buildContentUri(rowId);

                // 通知观察者数据库已更改
                getContext().getContentResolver().notifyChange(uri, null);
            } else {
                throw new SQLException(
                    getContext().getString(R.string.insert_failed) + uri);
            }
            break;

        default:
            throw new UnsupportedException(
                getContext().getString(R.string.invalid_insert) + uri);
    }

    return newContentUri;
}
```

图 9.21 | 重写的 `ContentProvider` 方法 `insert`

异常。如果 Uri 匹配成功，第 90–91 行将在数据库中插入新联系人。首先，我们使用 `AddressBookDatabaseHelper.getWritableDatabase` 获取一个 `SQLiteDatabase` 对象，以修改数据库中的数据。

`SQLiteDatabase` 的 `insert` 方法（第 90–91 行）将第三个参数 `ContentValues` 对象中的值插入到第一个参数指定的表中——该表中的列。该方法的第二个参数（在应用中未使用）命名为 `nullColumnHandler`，它的存在是因为 SQLite 不支持向表中插入完全空的行——这等同于传递一个空的 `ContentValues` 对象进行插入。与其禁止向该方法传递任何 `ContentValues`，不如使用 `nullColumnHandler` 参数来识别接受 `NULL` 值的列。

方法 `insert` 在插入操作成功时返回新联系人的唯一 ID，否则返回 `-1`。第 95 行检查 `rowID` 是否大于 `0`（SQLite 中的行从 `1` 开始索引）。如果是，第 96 行创建一个代表新联系人的 Uri，第 99 行通知 `ContentResolver` 数据库已更改，以便 Resolver 的代码能够响应数据库的变化。如果 `rowId` 不大于 `0`，则数据库操作失败，第 102–103 行抛出 `SQLException`。

## 第 9 章 通讯录 App

### 9.8.5 重写的 `update` 方法

重写的 `ContentProvider` 方法 `update`（图 9.22）更新现有记录。该方法接收四个参数：

- `uri`—代表要更新的行的 Uri。
- `values`—包含列及其对应值的 `ContentValues` 对象。
- `selection`—包含选择标准的字符串。这是 SQL 的 `WHERE` 子句，在指定时不附带 `WHERE` 关键字。如果此参数为 `null`，则结果将包含所有行。
- `selectionArgs`—包含用于替换选择字符串中任何占位符（`?`）的参数的字符串。

```java
// 更新数据库中现有的联系人

@Override
public int update(Uri uri, ContentValues values,
    String selection, String[] selectionArgs) {

    int numberOfRowsUpdated = // 如果更新成功为 1；否则为 0
    switch (uriMatcher.match(uri)) {
        case CONTACT:
            // 从 uri id 中获取要更新的联系人 id
            String id = uri.getLastPathSegment();

            // 更新联系人
            numberOfRowsUpdated = dbHelper.getWritableDatabase().update(
                Contact.TABLE_NAME, values, Contact.ID + " =" + id + "",
                selectionArgs);
            break;

        default:
            throw new UnsupportedException(
                getContext().getString(R.string.invalid_update_uri) + uri);
    }

    // 如果发生了更改，通知观察者数据库已更改
    if (numberOfRowsUpdated != 0) {
        getContext().getContentResolver().notifyChange(uri, null);
    }

    return numberOfRowsUpdated;
}
```

图 9.22 | 重写的 `ContentProvider` 方法 `update`

此应用中的更新仅针对特定的联系人进行，因此第 119–136 行仅检查 `ONE_CONTACT` Uri。第 122 行获取 Uri 的最后一个路径段，即联系人的唯一 ID。第 125–127 行获取一个可写的 `SQLiteDatabase`，然后调用其 `update` 方法，使用来自 `ContentValues` 参数的值来更新特定联系人。`update` 方法的参数为：

- 要更新的表的字符串名称
- 包含要更新的列及其新值的 `ContentValues` 对象
- 代表指定要更新行的 SQL `WHERE` 子句的字符串
- 包含替换 `WHERE` 子句中 `?` 占位符的任何参数的字符串数组

如果操作成功，方法返回一个表示已修改行数的整数；否则，`update` 返回 `0`。第 136 行通知 `ContentResolver` 数据库已更改，以便 `ContentResolver` 的客户端代码能够响应变化。第 139 行返回修改的行数。

### 9.8.6 重写的 `delete` 方法

重写的 `ContentProvider` 方法 `delete`（图 9.23）移除现有记录。`delete` 方法接收三个参数：

- `uri`—代表要删除的行。
- `selection`—包含指定要删除行的 `WHERE` 子句的字符串。
- `selectionArgs`—包含用于替换选择字符串中 `?` 占位符的参数的字符串。

```java
// 从数据库中删除现有的联系人

@Override
public int delete(Uri uri, String selection, String[] selectionArgs) {
    int numberOfRowsDeleted;

    switch (uriMatcher.match(uri)) {
        case CONTACT:
            // 从 uri id 中获取要更新的联系人 id
            String id = uri.getLastPathSegment();

            // 删除联系人
            numberOfRowsDeleted = dbHelper.getWritableDatabase().delete(
                Contact.TABLE_NAME, Contact.ID + " =" + id + "",
                selectionArgs);
            break;

        default:
            throw new UnsupportedException(
                getContext().getString(R.string.invalid_delete_uri) + uri);
    }

    // 如果发生了更改，通知观察者数据库已更改
    if (numberOfRowsDeleted != 0) {
        getContext().getContentResolver().notifyChange(uri, null);
    }

    return numberOfRowsDeleted;
}
```

图 9.23 | 重写的 `ContentProvider` 方法 `delete`

此应用中的删除仅针对特定的联系人进行，因此第 147–159 行仅检查 `ONE_CONTACT` Uri。第 150 行获取 uri 的最后一个路径段，即联系人的唯一 ID。第 153–154 行获取一个可写的 `SQLiteDatabase`，然后调用其 `delete` 方法，删除指定的联系人、`WHERE` 子句以及（如果 `WHERE` 子句有参数）参数数组。该方法返回删除的行数。第 163 行通知 `ContentResolver` 数据库已更改，以便 `ContentResolver` 的客户端响应变化。第 166 行返回删除行数。

## 9.9 `MainActivity` 类

`MainActivity` 管理应用的 Fragment 并协调它们之间的交互。`MainActivity` 每次显示一个 Fragment，从 `ContactsFragment` 开始。在平板电脑上，`MainActivity` 在左侧显示 `ContactsFragment`，并根据情况在右侧三分处显示 `DetailFragment` 或 `AddEditFragment`。

### 9.9.1 超类、实现的接口和字段

`MainActivity` 使用 v4 库中的 `FragmentTransaction` 添加和移除应用的 Fragment。`MainActivity` 实现三个接口：

- `ContactsFragment.ContactsListener`（第 9.10.2 节）：`ContactsFragment` 在用户选择联系人或添加新联系人时通知 `MainActivity` 的回调方法。
- `DetailFragment.DetailEventListener`（第 9.13.2 节）：`DetailFragment` 在用户删除联系人或编辑现有联系人时通知 `MainActivity` 的回调方法。
- `AddEditFragment.AddEditEventListener`（第 9.12.2 节）：`AddEditFragment` 在用户保存新联系人或更改现有联系人时通知 `MainActivity` 的回调方法。

常量 `CONTACT_URI`（第 17 行）用于 `MainActivity` 与 Fragment 之间传递的键值对键。实例 `ContactsFragment`（第 19 行）用于在联系人添加或删除后通知 `ContactsFragment` 更新显示的列表。

```java
// MainActivity.Java
// 托管应用的 Fragment 并处理它们之间的通信

package com.detail.addressbook;

import android.net.Uri;
import android.os.Bundle;
import android.support.v4.app.FragmentTransaction;
import android.support.v7.app.AppCompatActivity;
import android.support.v7.widget.Toolbar;
```

图 9.24 | `MainActivity` 的超类、实现的接口和字段。（部分 1/2）

## 9.9 `MainActivity` 类 355

```java
public class MainActivity extends AppCompatActivity
    implements ContactsFragment.ContactsFragmentListener,
    DetailFragment.DetailFragmentListener,
    AddedEditFragment.AddedEditFragmentListener {
```

```java
// 用于存储传递到 Uri 的 Bundle 中的联系人信息

public static final String CONTACT_URI = "contact_uri";
```

```java
private ContactsFragment contactsFragment; // 显示联系人列表
```

图 9.24 | `MainActivity` 的父类、实现的接口和字段。（部分 2，共 2 部分）

### 9.9.2 `onCreate` 中的重写方法

`onCreate` 上的重写方法（图 9.25）用于加载 `MainActivity` 的 GUI，如果应用运行在手机尺寸的设备上，则创建并显示 `ContactsFragment`。如果 Activity 在关闭或因配置更改而重建后恢复，`InstanceState` 将不为 `null`。在这种情况下，第 43–45 行仅引用了现有的 `ContactsFragment`——在手机上，它已经在 Android 上可见，并且它是第 25 行中加载的 `MainActivity` 布局的一部分。

```java
// 当 MainActivity 首次加载时显示 onCreate

@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);

    Toolbar toolbar = (Toolbar) findViewById(R.id.toolbar);
    setSupportActionBar(toolbar);
}
```



如果布局包含`fragmentContainer`，则正在使用手机布局；创建并显示`ContactsFragment`。

```java
if (savedInstanceState == null && findViewById(R.id.fragmentContainer) != null) {
    // 创建 ContactsFragment
    contactsFragment = new ContactsFragment();

    // 将事务添加到 FrameLayout
    FragmentTransaction transaction = getSupportFragmentManager().beginTransaction();
    transaction.add(R.id.fragmentContainer, contactsFragment);
    transaction.commit(); // 显示 ContactsFragment
} else {
    contactsFragment = (ContactsFragment) getSupportFragmentManager().
        findFragmentById(R.id.contactsFragment);
}
```

图 9.25 | `onCreate`中的重写方法。

## 第 9 章 通讯录应用

如果`MainActivity`中存在`R.id.fragmentContainer`（第 32 行），则该应用运行在手机上。在这种情况下，第 34 行创建`ContactsFragment`，然后第 37–40 行使用`FragmentTransaction`将`ContactsFragment`附加到用户界面上。第 37–38 行调用`FragmentManager`的`beginTransaction`方法以获取一个`FragmentTransaction`。接下来，第 39 行调用`FragmentTransaction`方法`add`以指定当`FragmentTransaction`完成时，应将`ContactsFragment`附加到 ID 为第一个参数的`View`上。最后，第 40 行使用`FragmentTransaction`方法`commit`来终结事务并显示`ContactsFragment`。

## 9.9.3 ContactsFragment.ContactsFragmentListener 方法

图 9.26 显示了`MainActivity`对`ContactsFragment.ContactsFragmentListener`接口中回调方法的实现。`onSelected`方法（第 50–60 行）由`ContactsFragment`调用，用于在用户选择容器以显示内容时通知`MainActivity`。如果应用运行在手机上（第 52 行），第 53 行调用`displayContact`，用显示联系人的`Detail1Fragment`（在 9.4.7 节中定义）替换`fragmentContainer`中的`ContactsFragment`。在平板上，第 56 行调用`FragmentManager`的`popBackStack`方法弹出（移除）返回栈中的顶层（如果存在的话），然后第 58 行调用`displayContact`，用显示联系人信息的`Detail1Fragment`（在 9.4.7 节中定义）替换`rightPaneContainer`的内容。

```java
// 为所选的联系人显示 DetailFragment
@Override
public void onSelected(Uri contactUri) {
    if (findViewById(R.id.fragmentContainer) != null) { // 手机
        displayContact(contactUri, R.id.fragmentContainer);
    } else { // 平板
        // 移除返回栈顶层
        getSupportFragmentManager().popBackStack();
    }
}
```

```java
// 添加 EditFragment 以新联系人
@Override
public void onCreate() {
    if (findViewById(R.id.fragmentContainer) != null) { // 手机
        displayAddEditFragment(R.id.fragmentContainer, null);
    } else // 平板
        displayAddEditFragment(R.id.rightPaneContainer, null);
}
```

图 9.26 | `ContactsFragment.ContactsFragmentListener`方法。

`addOnContact`（第 63–69 行）由`ContactsFragment`调用，用于在用户选择添加新联系人时通知`MainActivity`。如果布局包含`fragmentContainer`，第 66 行调用`displayAddEditFragment`（9.9.5 节）在`fragmentContainer`中显示`AddEditFragment`；否则，第 68 行在`rightPaneContainer`中显示该`Fragment`。`displayAddEditFragment`的第二个参数是一个`Bundle`，`AddEditFragment`用它判断是在添加新联系人还是在编辑现有联系人——`null`表示正在添加新联系人；否则，该包包含现有联系人的信息。

## 9.9.4 方法 displayContact

`displayContact`方法（图 9.27）创建显示所选联系人的`DetailFragment`。你可以通过将键值对放入`Bundle`中来将参数传递给`Fragment`——我们将将其传递给所选的`Uri`，以便`DetailFragment`知道从`ContentProvider`获取哪个联系人。第 77 行调用`putParcelable`将`CONTACT_URI`（一个字符串）的键值对放入`Bundle`中。第 78 行将`Uri`放入`Bundle`中。该`Fragment`实现了`Parcelable`，因此它可以从`Bundle`中提取信息。

```java
// 显示联系人
@Override
public void displayContact(Uri contactUri, int viewID) {
    DetailFragment detailFragment = new DetailFragment();

    // 将 contact-Uri 指定为参数
    Bundle arguments = new Bundle();
    arguments.putParcelable(CONTACT_URI, contactUri);
    detailFragment.setArguments(arguments);

    // 使用 FragmentTransaction 显示 DetailFragment
    FragmentTransaction transaction = 
        getSupportFragmentManager().beginTransaction();
    transaction.replace(viewID, detailFragment);
    transaction.addToBackStack(null);
    transaction.commit(); // 显示 DetailFragment
}
```

图 9.27 | 方法`displayContact`。

第 81–82 行获取一个`FragmentTransaction`，然后第 83 行调用`replace`方法以获取一个`FragmentTransaction`。接下来，第 84 行调用`FragmentTransaction`方法`addToBackStack`以指定当`FragmentTransaction`完成时，应将`DetailFragment`附加到 ID 为第一个参数的`View`上。最后，第 85 行使用`FragmentTransaction`方法`commit`来终结事务并显示`DetailFragment`。默认情况下，弹出顶层`Fragment`。

## 358 第 9 章 通讯录应用

## 9.9.5 方法 displayAddEditFragment

`displayAddEditFragment`方法（图 9.28）接收指定附加`AddEditFragment`的视图资源 ID 以及代表要编辑联系人的`Uri`。如果第二个参数为`null`，则正在添加新联系人。第 90 行创建`AddEditFragment`。

```java
// 为新或现有联系人显示 Fragment
private void displayAddEditFragment(int view, Uri contactUri) {
    AddEditFragment fragment = new AddEditFragment();

    // 如果编辑现有联系人，提供 contactUri 作为参数
    if (contactUri != null) {
        Bundle arguments = new Bundle();
        arguments.putParcelable(CONTACT_URI, contactUri);
        fragment.setArguments(arguments);
    }

    // 使用 FragmentTransaction 显示 AddEditFragment
    FragmentTransaction transaction = 
        getSupportFragmentManager().beginTransaction();
    transaction.replace(view, fragment);
    transaction.addToBackStack(null);
    transaction.commit(); // 显示 AddEditFragment
}
```

图 9.28 | 方法`displayAddEditFragment`。

## 9.9.6 DetailFragment.DetailFragmentListener 方法

图 9.29 显示了`MainActivity`对`DetailFragment.DetailFragmentListener`接口中回调方法的实现。`onDeleteDeleted`方法（第 108–114 行）由`DetailFragment`调用，用于用户删除联系人时通知`MainActivity`。在这种情况下，第 111 行从返回栈中弹出`DetailFragment`，以便新的联系人信息不再显示。第 112 行调用`ContactsFragment`的`updateContactList`方法来刷新联系人列表。

```java
// 删除显示联系人时返回联系人列表
@Override
public void onDeleteDeleted() {
    // 移除返回栈顶层
    getSupportFragmentManager().popBackStack();
    contactsFragment.updateContactList(); // 刷新联系人
}
```

图 9.29 | `DetailFragment.DetailFragmentListener`方法。（部分 1，共 2 部分）

## 9.9 MainActivity 类

```java
// 显示 AddEditFragment 以编辑现有的联系人
@Override
public void onEditContact(Uri contactUri) {
    if (findViewById(R.id.fragmentContainer) != null) // 手机
        displayAddEditFragment(R.id.fragmentContainer, contactUri);
    else // 平板
        displayAddEditFragment(R.id.rightPaneContainer, contactUri);
}
```

图 9.21 | `DetailFragment.DetailFragmentListener`方法。（2 部分中的第 2 部分。）

方法`onEditContact`（第 116–122 行）由`DetailFragment`调用，用于当用户触碰应用栏编辑联系人时，通知`MainActivity`。`DetailFragment`传递一个代表联系人的`Uri`，以便在`AddEditFragment`中对其进行编辑。如果布局包含`fragmentContainer`，则第 119 行调用`displayAddEditFragment`（第 9.9.5 节）在`fragmentContainer`中显示`AddEditFragment`；否则，第 121 行在`rightPaneContainer`中显示`AddEditFragment`。

## 9.9.7 AddEditFragment.AddEditFragmentListener 方法

来自`AddEditFragment.AddEditListener`接口的方法`onAddEditCompleted`（图 9.30）由`AddEditFragment`调用，用于当用户保存新联系人或保存到现有联系人时，通知`MainActivity`。第 128 行从返回栈中弹出`AddEditFragment`，第 129 行更新`ContactsFragment`的联系人列表。如果应用运行在平板电脑上（第 131 行），则第 133 行弹出返回栈以移除`DetailFragment`（如果存在）。然后，第 136 行在`rightPaneContainer`中显示新或更新的联系人详情。

```java
// 在保存新联系人或更新联系人后更新 GUI
@Override
public void onAddEditCompleted(Uri contactUri) {
    // 移除返回栈顶部
    getSupportFragmentManager().popBackStack();
    contactsFragment.updateContactList(); // 刷新联系人

    if (findViewById(R.id.fragmentContainer) != null) { // 平板
        // 移除返回栈顶部
        getSupportFragmentManager().popBackStack();
        // 平板，显示刚刚添加或编辑的联系人
        displayContact(contactUri, R.id.rightPaneContainer);
    }
}
```

图 9.30 | `AddEditFragment.AddEditFragmentListener`方法。

## 9.10 ContactsFragment 类

`ContactsFragment`类在`RecyclerView`中显示联系人列表，并提供了一个悬浮按钮（`FloatingActionButton`），用户可以点击它来添加新联系人。

### 9.10.1 超类和实现的接口

图 9.31 列出了`ContactsFragment`的包语句、导入语句以及类定义的开头。`ContactsFragment`使用`LoaderManager`和`Loader`来查询`AddressBookContentProvider`并接收一个`Cursor`，`ContactsAdapter`（第 9.11 节）使用该`Cursor`为`RecyclerView`提供数据。`ContactsFragment`实现了`LoaderManager.LoaderCallbacks<Cursor>`（第 23 行），以便它能够响应来自`LoaderManager`的方法，以创建`Loader`并通过`AddressBookContentProvider`处理结果。

```java
// ContactsFragment.java
// 显示按字母顺序排列的联系人名称列表的 Fragment 类
package com.detail.addressbook;

import android.content.Context;
import android.database.Cursor;
import android.net.Uri;
import android.os.Bundle;
import android.support.widget.FloatingActionButton;
import android.support.v4.app.Fragment;
import android.support.v4.content.LoaderManager;
import android.support.v4.content.CursorLoader;
import android.support.v7.widget.LinearLayoutManager;
import android.support.v7.widget.RecyclerView;
import android.view.LayoutInflater;
```



`import android.view.View;`

`import android.view.ViewGroup;`

`import com.detail.addressbook.data.DatabaseDescription;`

```java
public class ContactsFragment extends Fragment
        implements LoaderManager.LoaderCallbacks<Cursor> {
```

> 图 9.31 | `ContactsFragment` 超类和实现的接口。

### 9.10.2 `ContactsFragmentListener`

图 9.32 定义了嵌套接口 `ContactsFragmentListener`，它包含了 `MainActivity` 实现的回调方法，以便在用户选择联系人时（第 28 行）以及用户触碰悬浮按钮添加新联系人时（第 31 行）接收通知。

### 9.10 `ContactsFragment` 类

```java
// MainActivity 实现的回调方法
public interface ContactsFragmentListener {
    // 当选择联系人时调用
    void onContactSelected(Uri contactUri);
    // 点击添加按钮时调用
    void onAddToCart();
}
```

**图 9.32** 嵌套接口 `ContactsFragmentListener`。

### 9.10.3 字段

图 9.33 显示了 `ContactsFragment` 的字段。第 34 行声明了一个常量，用于处理从 `AddressBook` 返回的结果时标识 `Loader`。在这种情况下，我们只有一个 `Loader`——如果一个类使用多个 `Loader`，则每个 `Loader` 都应该有一个具有唯一整数值的常量，以便您可以在 `LoaderManager.Callbacks<Cursor>` 回调方法中识别要操作的是哪个 `Loader`。实例变量 `listener`（第 37 行）将引用实现接口的对象（`MainActivity`）。实例变量 `contactsAdapter`（第 39 行）将引用绑定数据到 `RecyclerView` 的 `ContactsAdapter`。

```java
private static final int CONTACT_LOADER = 0; // 标识 Loader
// 在选择联系人时通知 MainActivity
private ContactsFragmentListener listener;
private ContactsAdapter contactsAdapter; // recyclerView 的适配器
```

**图 9.33** `ContactsFragment` 字段。

### 9.10.4 重写的 `onCreateView` 方法

重写的方法 `onCreate`（图 9.34）加载了并配置了 `Fragment` 的 GUI。第 47 行显示了 `Fragment` 的布局内容。第 56–74 行配置了 `RecyclerView`。第 60 行创建了 `ContactsAdapter`。在 `RecyclerView` 中添加了自定义装饰器以绘制列表项之间的分割器。第 71 行获取悬浮按钮并配置其监听器，当用户触碰 FAB 时显示 `AddEditFragment`。

```java
// 配置此 fragment 的 GUI
@Override
public void onCreateView(
    LayoutInflater inflater, ViewGroup container,
    Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setHasContentView(true); // 加载 UI 获取 RecyclerView
    View view = inflater.inflate(R.layout.fragment_contacts, container, false);
    RecyclerView recyclerView = view.findViewById(R.id.recyclerView);
    // 设置 RecyclerView 的布局管理器
    recyclerView.setLayoutManager(
        new LinearLayoutManager(getActivity()));
    // 创建 ContactsAdapter 适配器
    ContactsAdapter contacts = new ContactsAdapter();
    // 设置适配器
    recyclerView.setAdapter(contacts);
    // 添加自定义装饰器以绘制列表项之间的分割器
    recyclerView.addItemDecoration(new ItemDivider(getContext()));
    // 获取悬浮按钮并配置其监听器
    FloatingActionButton addButton = 
        (FloatingActionButton) view.findViewById(R.id.addButton);
    addButton.setOnClickListener(() -> {
        // 当触碰 FAB 时
        @Override
        public void onClick(View view) {
            listener.onAddToCart();
        }
    });
    return view;
}
```

图 9.34 | 重写的方法

### 9.10.5 重写的 `onAttach` 和 `onDetach` 方法

`ContactsFragment` 重写了 `onAttach` 和 `onDetach` 方法（图 9.35）以设置实例 `listener`。在这里，`listener` 在挂载时（第 96 行）引用 `Activity`，并在卸载时（第 103 行）被置为空。

```java
// fragment 挂载时设置 ContactsFragmentListener
@Override
public void onAttach(Context context) {
    super.onAttach(context);
    listener = (ContactsFragmentListener) context;
}
// fragment 卸载时移除 ContactsFragmentListener
@Override
public void onDetach() {
    super.onDetach();
    listener = null;
}
```

**图 9.35** | 重写的 `onAttach` 和 `onDetach` 方法。

### 9.10.6 重写的 `onDestroyCreated` 方法

`Fragment` 生命周期周期方法 `onDestroyCreated`（图 9.36）在 `Fragment` 的宿 `Activity` 已创建且 `Fragment` 的 `onCreate` 方法执行后被调用。此时，使用此方法通过 `LoaderManager` 初始化 `Loader`——在视图存在之后操作，因为需要 `RecyclerView` 才能显示加载的数据。第 110 行使用方法 `getFragmentManager` 获取 `Fragment` 的 `LoaderManager` 对象。接下来我们调用 `LoaderManager.initLoader`，它接收三个参数：

- 用于标识 `Loader` 的整数 ID
- 包含 `Loader` 构造函数参数的 `Bundle`，如果没有参数则为 `null`
- 对 `LoaderManager.LoaderCallbacks<Cursor>` 接口实现的引用——你将在第 9.10.8 节看到该接口方法 `onCreate`、`onLoadFinished` 和 `onReset` 的实现。

如果不存在指定 ID 的活跃 `Loader`，`initLoader` 方法将异步调用 `onCreate` 方法来创建并启动该 ID 的 `Loader`。如果存在活跃 `Loader`，`initLoader` 方法将立即调用 `onLoadFinished`。

## 第9章 通讯录应用

```java
// 当此 fragment 的 activity 创建时初始化一个 Loader
@Override
public void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    getLoaderManager().initLoader(CONTACTS_LOADER, null, this);
}
```

图 9.36 | 重写的方法 `onActivityResult`

## 9.10 方法 `updateContactList`

`ContactsFragment` 的 `updateContactList` 只是在数据发生变化时通知 `ContactsAdapter`。当添加新联系人或更新、删除联系人时，会调用此方法。

```java
// 当其他 Fragment 更新数据库时从 MainActivity 调用
public void updateContactList() {
    contactsAdapter.notifyDataSetChanged();
}
```

图 9.37 | `ContactsFragment` 方法 `updateContact`

## 9.18 `LoaderManager.LoaderCallbacks<Cursor>` 方法

图 9.38 显示了 `ContactsFragment` 对 `LoaderManager.LoaderCallbacks<Cursor>` 接口中回调方法的实现。

```java
// 由 LoaderManager 调用以创建一个 Loader
@Override
public Loader<Cursor> onCreateLoader(int id, Bundle args) {
    // 根据 id 参数创建适当 Cursor：
    switch (id) {
        case CONTACTS_LOADER:
            return new CursorLoader(getActivity(),
                contentUri, // 联系人表的 Uri
                null, // null 投影返回所有列
                null, // null 筛选返回所有行
                null, // 无筛选参数
                Contact.COLUMN_NAME + " COLLATE COLLATE ASC");
```

图 9.38 | `LoaderManager.LoaderCallbacks<Cursor>` 方法。（第 1/2 部分）

## 9.11 `ContactsAdapter` 类

```java
// 当加载完成时由 LoaderManager 调用
@Override
void onLoadFinished(Loader<Cursor> loader, Cursor data) {
    contactsAdapter.swapCursor(data);
}
```

```java
// 当 Loader 正在重置时由 LoaderManager 调用
@Override
void onLoaderReset(Loader<Cursor> loader) {
    contactsAdapter.swapCursor(null);
}
```

**图 9.38 | `LoaderManager.LoaderCallbacks` 方法。（第 2/2 部分）**

### 方法 `onCreateLoader`

`LoaderManager` 使用 `onCreateLoader` 为 ID 创建并返回一个新的 `Loader`，该 `Loader` 在 `Fragment` 或 `Activity` 的生命周期范围内进行管理。第 123–133 行根据 `onCreate` 第一个参数接收到的 ID 确定要创建的 `Loader`。

### 良好的编程实践 9.1

![](img/8c2e5496308864b3b07ddbd4401c4f77_401_0.png)

对于 `ContactsProvider`，我们只需要一个 `Loader`，因此 `switch` 语句是不必要的，但我们将其包含在此处作为良好的实践。

第 125–130 行创建并返回查询 `AddressBookProvider` 以获取联系人列表的 `Cursor`，然后将结果转换为 `Cursor`。`LoaderCursor` 查询管理 `Loader` 生命周期周期的 `Context`，以及它管理的 `uri`、`projection`（投影）、`selection`（筛选）、`selectionArgs` 和 `sortorder` 等参数。在这种情况下，我们对 `projection`、`selection` 和 `selectionArgs` 指定为 `null`，并表示联系人的名称应以不区分大小写的方式命名。

### 方法 `onLoadFinished`

方法 `onLoadFinished`（第 137–140 行）在 `Loader` 完成数据加载后由 `LoaderManager` 调用，因此我们可以处理 `Cursor` 中的结果。在这种情况下，我们带上 `Cursor` 参数调用 `ContactsAdapter.swapCursor` 方法，以便 `ContactsAdapter` 根据新的联系人刷新 `RecyclerView`。

### 方法 `onLoaderReset`

方法 `onLoaderReset`（第 143–146 行）在 `Loader` 被重置且其数据不再可用时由 `LoaderManager` 调用。此时，应用程序应立即与数据断开连接。在这种情况下，我们调用 `ContactsAdapter` 的 `swapCursor` 方法并传入 `null` 参数，以表示没有数据需要绑定到 `RecyclerView` 上。

## 9.11 `ContactsAdapter` 类

在第 8.6 节中，我们讨论了如何创建一个用于将数据绑定到 `RecyclerView` 的 `RecyclerView.Adapter`。在这里我们重点介绍新代码，这些代码帮助 `ContactsAdapter`（图 9.39）从 `Cursor` 中提取联系人名称填充 `RecyclerView`。

```java
// ContactsAdapter.java
// RecyclerView.Adapter 的子类，用于将联系人绑定到 RecyclerView
package com.detail.addressbook;

import android.database.Cursor;
import android.net.Uri;
import android.support.v7.widget.RecyclerView;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.TextView;
import com.detail.database.DataDescription.Contact;

public class ContactsAdapter
    extends RecyclerView.Adapter<ContactsAdapter.ViewHolder> {

    // ContactsFragment 实现的接口，用于响应
    // 用户触摸 RecyclerView 中的项时的事件
    public interface ContactClickListener {
        void onContactClick(Uri contactUri);
    }

    // RecyclerView.ViewHolder 的嵌套子类，用于在
    // RecyclerView 语文中实现 view-holder 模式
    public class ViewHolder extends RecyclerView.ViewHolder {
        private TextView textView;
        private long rowId;

        // 配置 RecyclerView 项的 ViewHolder
        public ViewHolder(View itemView) {
            textView = (TextView) itemView.findViewById(android.R.id.text1);
            // 为 itemView 挂接监听器
            itemView.setOnClickListener(new View.OnClickListener() {
                // 当点击联系人时执行
                @Override
                public void onClick(View view) {
                    clickListener.onContactClick(Contact.buildUri(rowId));
                }
            });
            // 设置联系人的数据库 ID
```



进入`/path/to/xxx`目录，找到`xxx.json`。

在表达式`cvar = avar + bvar`中，加法运算符（`+`）将`avar`与`bvar`相加，得到它们的和`cvar`

在`List.of(arg0, arg1, arg2)`中，`List`接口的工厂方法`of()`接受一系列的元素，返回包含它们的只读列表。

之后我们这样调用`cmd`命令：`cmd arg0 arg1 arg2`。

```
if (condVar > someVal) {console.log("xxx")}
```



`new View.OnClickListener() {

        @Override

        public void onClick(View v) {

            // 隐藏软键盘

            ((InputMethodManager)getActivity().getSystemService(Context.METHOD_SERVICE)).hideInputFromWindow(

                v.getWindow(), 0);

            saveContact(); // 保存联系人到数据库

        }

    };`

// 将联系人信息保存到数据库
`private void saveContact() {

    // 创建包含联系人键值对的 ContentValues 对象

    ContentValues contentValues = new ContentValues();

    contentValues.put(ContentValues.COLUMN_NAME,

    nameInputLayout.getInput().toString());

    contentValues.put(ContentValues.COLUMN_PHONE,

    phoneInputLayout.getInput().toString());

    contentValues.put(ContentValues.COLUMN_EMAIL,

    emailInputLayout.getInput().toString());

    contentValues.put(ContentValues.COLUMN_STREET,

    streetInputLayout.getInput().toString());

    contentValues.put(ContentValues.COLUMN_CITY,

    cityInputLayout.getInput().toString());

    contentValues.put(ContentValues.COLUMN_STATE,

    stateInputLayout.getInput().toString());

    contentValues.put(ContentValues.COLUMN_ZIP,

    zipInputLayout.getInput().toString());

}`

`if (addingNext()) {

    // 使用 Activity 的 ContentResolver 在

    // AddressBookContentProvider 上调用 insert

    Uri newContactUri = getActivity().getContentResolver().insert(

        Contact.CONTENT_URI, contentValues);

    if (newContactUri == null) {

        Snackbar.make(coordinatorLayout, "contact-added", Snackbar.LENGTH_LONG).show();

        listener.onEditCompleted(newContactUri);

    }

}`

图 9.45 | `View.OnClickListener` `saveContactButtonClicked` 和方法 `saveContact`。（第 1 部分，共 2 部分）

# 第 9 章 通讯录应用

```java
194  else {
    Snackbar.make(coordinatedLayout,
      R.string.contact_not_added, Snackbar.LENGTH_LONG).show();
  }
}

  else {
    // 使用 Activity 的 ContentResolver 来调用
    // 在 AddressBookContentProvider 上执行 insert
    int updatedRows = getActivity().getContentResolver().update(
      contactUri, null, null);
    if (updatedRows > 0) {
      listener.onEditCompleted(contactUri);
      Snackbar.make(coordinatedLayout,
      R.string.contact_updated, Snackbar.LENGTH_LONG).show();
  }
  else {
    Snackbar.make(coordinatedLayout,
      R.string.contact_not_updated, Snackbar.LENGTH_LONG).show();
  }
}
```

**图 9.45** | `View.OnClickListener` `saveButtonClicked` 方法和 `saveContent` 方法。（部分 2）

`saveContent` 方法（第 165–215 行）创建了一个 `ContentValues` 对象（第 167 行），并添加了键值对，这些键值代表要插入或更新数据库的列名和值（第 168–181 行）。如果用户正在添加新联系人（第 183–199 行），第 186–187 行使用 `ContentResolver` 方法将数据插入到 `AddressBookContentProvider` 中并将新联系人放入数据库。如果插入成功，返回的 `Uri` 不为空，第 191–192 行将显示一个 `Snackbar` 表明联系人已添加，然后通知 `EditFragmentListener` 联系人已更新。回想一下当应用返回表格时，这将在每个联系人的片段（fragment）中显示联系人的数据。如果插入失败，第 195–196 行将显示相应的 `Snackbar`。

如果用户正在编辑现有联系人（第 199–214 行），第 202–203 行使用 `ContentResolver` 方法在 `AddressBookContentProvider` 上进行更新并存储编辑后的联系人数据。如果更新成功，返回的整数大于 0（表示更新的特定行数），第 206–208 行通知 `EditFragmentListener` 联系人已编辑成功，然后显示相应的消息。如果更新失败，第 211–212 行将显示相应的 `Snackbar`。

## 9.12.7 `LoaderManager.LoaderCallbacks<Cursor>` 方法

图 9.46 显示了 `AddEditFragment` 对 `LoaderManager.Callbacks<Cursor>` 接口中方法的实现。这些方法仅在用户编辑现有联系人时在 `EditFragment` 类中使用。`onStartLoader` 方法（第 219–233 行）为正在编辑的特定联系人创建一个 `CursorLoader`。`onLoadFinished` 方法（第 236–267 行）检查游标是否为空，如果是则调用 `moveToFirst()` 方法。如果该方法返回 `true`，则在数据库中找到了与 `contactUri` 匹配的项目，第 241-263 行从 `Cursor` 获取信息并显示在 GUI 中。`AddEditFragment` 不需要 `onLoaderReset`，因此它不执行任何操作。

```java
// 由 LoaderManager 调用以创建 Loader
@Override
public Cursor onCreateLoader(int id, Bundle args) {
    // 根据 id 参数创建合适的 CursorLoader；
    // 此处只有一个 Loader，所以 switch 是没必要的
    switch (id) {
        case LOADER:
            return new CursorLoader(getActivity(),
                contactUri, // 要显示的联系人 Uri
                null, // null 投影返回所有列
                null, // null 选择返回所有行
                null, // 无选择参数
                null); // 排序顺序
        default:
            return null;
    }
}
```

```java
// 当加载完成时由 LoaderManager 调用
@Override
public void onLoadFinished(Loader cursor, Cursor data) {
    // 如果数据库中存在数据，则显示它
    if (data != null && data.moveToFirst()) {
        // 获取每个项目的列索引
        int nameIndex = data.getColumnIndex(Contact.COLUMN_NAME);
        int phoneIndex = data.getColumnIndex(Contact.COLUMN_PHONE);
        int emailIndex = data.getColumnIndex(Contact.COLUMN_EMAIL);
        int streetIndex = data.getColumnIndex(Contact.COLUMN_STREET);
        int cityIndex = data.getColumnIndex(Contact.COLUMN_CITY);
        int stateIndex = data.getColumnIndex(Contact.COLUMN_STATE);
        int zipIndex = data.getColumnIndex(Contact.COLUMN_ZIP);

        // 使用检索的数据填充 EditText
        nameInputLayout.setText(data.getString(nameIndex));
        phoneInputLayout.setText(data.getString(phoneIndex));
        mailInputLayout.setText(data.getString(emailIndex));
        streetInputLayout.setText(data.getString(streetIndex));
        cityInputLayout.setText(data.getString(cityIndex));
        stateInputLayout.setText(data.getString(stateIndex));
        zipInputLayout.setText(data.getString(zipIndex));
    }
}
```

## 9.12 `AddEditFragment` 类

```java
package com.deitel.addressbook;

import android.app.AlertDialog;
import android.app.Dialog;
import android.content.Context;
import android.content.DialogInterface;
import android.database.Cursor;
import android.net.Uri;
import android.os.Bundle;
import android.support.v4.Fragment;
import android.support.v4.LoaderManager;
import android.support.v4.content.CursorLoader;
import android.view.LayoutInflater;
import android.view.Menu;
import android.view.MenuInflater;
import android.view.MenuItem;
import android.view.View;
import android.view.ViewGroup;
import android.widget.TextView;
import com.deitel.addressbook.data.Contact;

public class DetailFragment extends Fragment implements LoaderManager.Loader<Cursor> {
```

## 9.13.2 `DetailFragmentListener`

```java
// 由 MainActivity 实现的回调方法
public interface DetailFragmentListener {
    void onDestroy(); // 删除联系人时调用

    // 将要编辑的联系人的 Uri 传递给 DetailFragmentListener
    void onEditContact(Uri uri);
}
```

## 9.13.3 字段

图 9.49 显示了类的字段：

- `CONTACT_LOADER`（第 38 行）标识查询 `AddressBookProvider` 以检索显示联系人的 `Loader`。
- 实例变量 `listener`（第 40 行）指向 `DetailFragmentListener` (`MainActivity`)，当用户删除联系人或启动编辑联系人时会对其进行通知。
- 实例变量 `uri`（第 41 行）表示要显示的联系人。
- 实例变量第 43–49 行指向 `Fragment` 的 `View`。

```java
private static final int CONTACT_LOADER = 0; //标识 Loader
private DetailFragmentListener listener; // MainActivity
private Uri uri; // 选中联系人的 Uri
private TextView nameTextView; // 显示联系人姓名
private TextView phoneTextView; // 显示联系人电话
private TextView emailTextView; // 显示联系人邮箱
private TextView streetTextView; // 显示联系人街道
private TextView cityTextView; // 显示联系人城市
```

## 378 第 9 章 通讯录应用

```java
48 private TextView stateTextView; // 显示联系人的状态
49 private TextView zipTextView; // 显示联系人的邮编
50
```

图 9.49 | `DetailFragment` 字段。（第 2 部分共 2 部分。）

## 9.13.4 重写方法 `onAttach`, `onDetach` 和 `onCreateView`

图 9.50 包含了重写的 fragment 方法 `onAttach`、`onDetach` 和 `onCreateView`。`onAttach` 和 `onDestroy` 方法在 `DetailFragment` 挂载时将实例变量 `listener` 设置为指向 `Activity` 的引用，并在 `DetailFragment` 卸载时将该 `listener` 设为 `null`。`onCreate` 方法（第 66-95 行）获取联系人的 `uri`（第 74-77 行）。第 80-90 行加载 GUI 并获取 `TextView` 的引用。第 93 行使用 `FragmentManager` 最小化 `DetailFragment` 用来获取联系人数据的 `Loader`。

```java
51 // fragment 挂载时设置 DetailFragmentListener
52 @Override
53 public void onAttach(Context context) {
54 super.onAttach(context);
55 listener = (DetailFragmentListener) context;
56 }
```

```java
58 // fragment 卸载时移除 DetailFragmentListener
59 @Override
60 public void onDestroy() {
61 super.onDestroy();
62 listener = null;
63 }
64
```

```java
66 // 当需要创建 DetailFragmentListener 的 view 时
67 @Override
68 public View onCreateView(LayoutInflater inflater, View container,
69 Bundle savedInstanceState) {
70 super.onCreateView(inflater, container, savedInstanceState);
71 setHasOptionsMenu(true); // 此 fragment 有要显示的菜单项
```

```java
73 // 获取参数的 Bundle 以提取联系人的 Uri
```



```java
Bundle arguments = getArguments();

if (arguments != null)
    contactUri = arguments.getParcelable(MainActivity.CONTACT_URI);

// 加载 DetailFragment 的布局
view = inflater.inflate(R.layout.fragment_detail, container, false);

// 获取 EditTexts
nameTextView = (TextView) view.findViewById(R.id.nameTextView);
phoneTextView = (TextView) view.findViewById(R.id.phoneTextView);
emailTextView = (TextView) view.findViewById(R.id.emailTextView);
streetTextView = (TextView) view.findViewById(R.id.streetTextView);
cityTextView = (TextView) view.findViewById(R.id.cityTextView);
stateTextView = (TextView) view.findViewById(R.id.stateTextView);
zipTextView = (TextView) view.findViewById(R.id.zipTextView);

// coatLoader
getLoaderManager().init(CONTACT_LOADER, null, this);
return view;
}
```

**图 9.50** | 重写方法 `onAttach`、`onDetach` 和 `onCreateView`（第 1 部分共 2 部分）。

```java
phoneTextView = (TextView) view.findViewById(R.id.phoneTextView);
emailTextView = (TextView) view.findViewById(R.id.emailTextView);
streetTextView = (TextView) view.findViewById(R.id.streetTextView);
cityTextView = (TextView) view.findViewById(R.id.cityTextView);
stateTextView = (TextView) view.findViewById(R.id.stateTextView);
zipTextView = (TextView) view.findViewById(R.id.zipTextView);
// coatLoader
getLoaderManager().init(CONTACT_LOADER, null, this);
return view;
}
```

**图 9.50** | 重写方法 `onAttach`、`onDestroy` 和 `onCreate`（第 2 部分共 2 部分）。

### 9.13.5 重写方法 `onCreateOptionsMenu` 和 `onItemSelectedSelected`

`DetailFragment` 显示在栏选项中，用于编辑当前账户和删除它。在 `onCreateOptionsMenu` 中（图 9.51，第 98–102 行）加载菜单资源文件 `fragment_details.xml`。`onItemSelectedSelected` 方法（第 105–117 行）选择 `MenuItem` 资源 ID 以确定选中了哪一个。如果用户点击了编辑选项（✔），第 109 行调用 `DetailFragmentlistener.onEditContact` 方法——`MainActivity` 将其传递给 `AddEditFragment`。如果用户点击了删除选项（✔），第 112 行调用 `deleteContact`（图 9.52）。

```java
// 显示此 fragment 的菜单项
@Override
public boolean onCreateOptionsMenu(Menu menu, MenuInflater inflater) {
    super.onCreateOptionsMenu(menu, inflater);
    inflater.inflate(R.menu.fragment_details_menu, menu);
}

// 处理菜单项选择
@Override
public boolean onItemSelectedSelected(MenuItem item) {
    switch (item.getItemId()) {
        case R.id.action_edit:
            listener.onEditContact(contactUri); // 将 Uri 传递给 listener
            return true;
        case R.id.action_delete:
            deleteContact();
            return true;
    }
    return super.onItemSelectedSelected(item);
}
```

**图 9.51** | 重写方法 `onCreateOptionsMenu` 和 `onItemSelectedSelected`。

# 第 9 章 通讯录应用

### 9.13.6 方法 `deleteContact` 和 `DialogFragment` `confirmDelete`

`deleteContact` 方法（图 9.52，第 120–123 行）显示一个 `DialogFragment`（第 126–157 行），询问用户确认是否删除显示的联系人。如果用户在对话框中使用 DELETE，则第 147–148 行调用 `ContentResolver` 方法 `delete`（第 147–148 行）来调用 `AddressBookContentProvider` 的 `delete` 方法并从数据库中移除。`delete` 方法接收联系人的 Uri 以确定要删除的内容，以及一个插入到 `WHERE` 子句的字符串参数。在这种情况下，最后两个参数为 `null`，联系人的行 ID 嵌入在 Uri 中——该 ID 由 `AddressBookContentProvider` 从 Uri 中提取。第 149 行调用监听器的 `onDestroy` 方法，以便 `MainActivity` 移除该 Fragment。

```java
// void deleteContact() {

// 使用 FragmentManager 显示 confirmDelete DialogFragment
confirmDelete.show(getFragmentManager(), "confirmDelete");

// 用于删除联系人的 DialogFragment
private final DialogFragment confirmDelete = new DialogFragment() {
    // 创建一个新的 AlertDialog 并返回
    @Override
    public void onCreate(Bundle bundle) {
        AlertDialog.builder = new AlertDialog(getActivity());
        builder.setTitle(R.string.confirm_title);
        builder.setMessage(R.string.confirm_message);

        // 提供一个删除按钮
        builder.setPositiveButton(
            R.string.button_delete,
            new DialogInterface.OnClickListener() {
                public void onClick(DialogInterface dialog, int button) {
                    // 使用 Activity 的 ContentResolver 删除
                    getActivity().getContentResolver().delete(
                        contactUri,
                        null,
                        null
                    );
                    listener.onDeleted(); // 通知监听器
                }
            }
        );

        // 提供一个取消按钮
        builder.setNegativeButton(R.string.button_cancel, null);
        return builder.create(); // 返回 AlertDialog
    }
};
```

**图 9.52** | `deleteContact` 方法 `DialogFragment` `confirm`（第 1 部分共 2 部分）。

```java
builder.setNegativeButton(R.string.button_cancel, null);
return builder.create(); // 返回 AlertDialog
}
};
```

**图 9.52** | `deleteContact` 方法 `DialogFragment` `confirm`（第 2 部分共 2 部分）。

### 9.13 `LoaderManager.LoaderCallback<Cursor>` 方法

图 9.53 显示了 `DetailFragment` 对 `LoaderManager.LoaderCallback` 接口方法的实现。`onCreate` 方法（第 160–181 行）为显示的联系人创建 Cursor。`onLoaderFinished` 方法（第 184–206 行）检查游标是否为空，如果是则调用 `moveToFirst()`。如果此方法返回 `true`，则在数据库中找到了匹配 Uri 的联系人，第 189–204 行从 Cursor 获取联系人信息并在 GUI 中显示。`DetailFragment` 不需要 `onLoaderReset`，因此不执行任何操作。

```java
// 由 LoaderManager 创建 Loader
@Override
public Cursor<Cursor> onCreateLoader(int id, Bundle args) {
    // 根据 id 参数创建相应的 Cursor；
    // 此 fragment 只有一个 Cursor，因此不需要 switch
    CursorLoader cursor;

    switch (id) {
        case CONTACT_LOADER:
            cursor = new CursorLoader(
                getActivity(),
                Uri,    // 空投影返回
                null,   // 空投影返回所有列
                null,   // 空选择返回所有行
                null,   // 无选择参数
                null    // 排序顺序
            );
            break;
        default:
            cursor = null;
    }

    return cursor;
}

// 当加载完成时调用
@Override
public void onLoadFinished(Loader<Cursor> loader, Cursor data) {
    // 如果数据库中存在联系人，则显示其数据
    if (data != null && data.moveToFirst()) {
        // 获取每个数据项的列索引
        int columnIndex = data.getColumnIndex(Contact.COLUMN_NAME);
        int phoneIndex = data.getColumnIndex(Contact.COLUMN_PHONE);
        int emailIndex = data.getColumnIndex(Contact.COLUMN_EMAIL);
        int streetIndex = data.getColumnIndex(Contact.COLUMN_STREET);
        int cityIndex = data.getColumnIndex(Contact.COLUMN_CITY);
        int stateIndex = data.getColumnIndex(Contact.COLUMN_STATE);
        int zipIndex = data.getColumnIndex(Contact.COLUMN_ZIP);

        // 用检索到的数据填充 TextViews
        nameTextView.setText(data.getString(nameIndex));
        phoneTextView.setText(data.getString(phoneIndex));
        emailTextView.setText(data.getString(emailIndex));
        streetTextView.setText(data.getString(streetIndex));
        cityTextView.setText(data.getString(cityIndex));
        stateTextView.setText(data.getString(stateIndex));
        zipTextView.setText(data.getString(zipIndex));
    }
}
```

**图 9.53** | `LoaderManager.LoaderCallback<Cursor>` 方法。（第 1 部分共 2 部分）

```java
int phoneIndex = data.getColumnIndex(Contact.COLUMN_PHONE);
int emailIndex = data.getColumnIndex(Contact.COLUMN_EMAIL);
int streetIndex = data.getColumnIndex(Contact.COLUMN_STREET);
int cityIndex = data.getColumnIndex(Contact.COLUMN_CITY);
int stateIndex = data.getColumnIndex(Contact.COLUMN_STATE);
int zipIndex = data.getColumnIndex(Contact.COLUMN_ZIP);

// 用检索到的数据填充 TextViews
nameTextView.setText(data.getString(nameIndex));
phoneTextView.setText(data.getString(phoneIndex));
emailTextView.setText(data.getString(emailIndex));
streetTextView.setText(data.getString(streetIndex));
cityTextView.setText(data.getString(cityIndex));
stateTextView.setText(data.getString(stateIndex));
zipTextView.setText(data.getString(zipIndex));
}
}
```

```java
// 当 Loader 重置时，由 Manager 调用
@Override
public void onLoadReset(Loader<Cursor> loader) {
}
```



图 9.53 | `Manager.LoaderCallback<Cursor>` 方法。（2 个部分中的第 2 部分。）

## 9.14 总结

在本章中，你创建了一个通讯录应用，用于查找、查看、编辑和删除存储在 SQLite 数据库中的联系人信息。

你使用了一个 `Activity` 来承载应用的所有 `Fragment`。在手机尺寸的设备上，你每次只显示一个 `Fragment`。在平板电脑上，你根据需要将其替换为用于查看、添加和编辑联系人的 `Fragment`。你使用了 `FragmentManager` 和 `FragmentTransactions` 来动态显示 `Fragment`。你利用 Android 的后退栈（back stack）为 `Fragment` 和宿主 `Activity` 之间提供了自动支持，并在每个 `Fragment` 中定义了一个宿主 `Activity` 实现的回调方法嵌套接口。

你使用了 `SQLiteHelper` 的子类来简化数据库操作，并将数据存储在 `SQLiteDatabase` 对象中以操作数据库内容。你还使用 `Cursor`（`android.database` 包）管理了数据库查询。

为了在 GUI 线程之外异步访问数据库，你定义了一个 `ContentProvider` 的子类，规定了如何查询、插入、更新和删除数据。当 SQLite 数据库发生更改时，`ContentProvider` 会通知监听器以便它们进行更新。`ContentProvider` 使用 URI 来确定要执行的任务。

若要调用 `ContentProvider` 的查询、插入、更新和删除功能，你调用了 `Activity` 内置 `ContentResolver` 的相应方法。你看到 `ContentProvider` 和 `ContentResolver` 为你处理了通信。`ContentResolver` 的方法将第一个参数接收一个 URI，指定要访问的 `ContentProvider`。每个 `ContentResolver` 会调用 `ContentProvider` 的相应方法，而 `ContentProvider` 又使用该 URI 来帮助确定要执行的任务。

正如我们之前所说的，耗时操作或阻塞执行直到完成才继续的操作（例如文件和数据库访问）应该在 GUI 线程之外执行。你使用 `CursorLoader` 执行了异步数据访问。你了解到 `Loader` 是由 `Activity` 或 `Fragment` 的 `LoaderManager` 创建并管理的，这会将每个 `Loader` 的生命周期与其所在的 `Activity` 或 `Fragment` 的生命周期绑定。你实现了 `LoaderManager.LoaderCallbacks` 接口来响应 `Loader` 事件，指示 `Loader` 何时创建、完成数据或数据是否不再可用。

你将常用的 GUI 组件属性-值对定义为样式资源（style），并将样式应用到显示联系人信息的 `TextView` 上。你还通过为 `TextView` 的背景指定 `Drawable` 为 `TextView` 定义了边框。`Drawable` 可以是图像，但在本应用中，你将 `Drawable` 定义为资源文件中的一个形状（shape）。

在第 10 章中，我们将讨论 Android 应用开发的业务方面。你将看到如何为提交到 Google Play 准备应用，包括图标。我们将讨论如何在设备上测试你的应用以及将其发布在 Google Play 上。我们讨论了优秀应用的特征以及需要遵循的 Android 设计指南。我们还为你的应用定价和营销提供了建议。我们并回顾了提供免费应用的好处，例如作为应用功能更丰富的版本或高级内容。我们展示了如何使用 Google 应用销售数据来跟踪销售、支付等信息。

## 10  Google Play 与应用业务问题

### 目标

在本章中，你将了解到：

- 为发布应用做准备。
- 为你的应用定价以及免费应用与付费应用的优劣。
- 通过应用内广告实现应用变现。
- 使用应用内购买销售虚拟商品。
- 注册 Google Play。
- 设置商户账户。
- 将你的应用上传到 Google Play。
- 从应用内部启动 Google Play。
- 其他 Android 应用市场。
- 其他可以迁移你的应用以扩大市场范围的其它热门移动应用平台。
- 营销你的应用。

![](img/8c2e5496308864b3b07ddbd4401c4f77_420_0.png)

### 10.1 引言

在第 2 到 9 章中，我们开发了各种完整且运行的 Android 应用。一旦你在模拟器和设备上都开发并测试了应用，下一步就是将它们提交到 Google Play。在本章中，我们将你参考 Android 文档，因为这些步骤可能会发生。我们将告诉你你应该提供免费应用还是付费应用，并提到应用变现的主要手段，包括应用内广告、应用内购买以及销售虚拟商品。我们将提供营销应用的资源。Google 提供了各种文档帮助你准备应用。《准备发布》（*Preparing for Release*）总结了你需要做什么，包括：

- 创建图标
- 包含用户许可协议（可选）
- 为你的应用版本化（例如 1.0, 1.1, 2.0, 2.3, 3.0）
- 为发布编译应用
- 在 Android 设备上测试你的发布版本

```
http://developer.android.com/tools/preparing.html
```

### 10.2 为发布准备应用

在发布应用之前，你应该阅读核心应用质量（Core App Quality）文档，它为所有应用提供了指南；平板应用质量（`http://developer.android.com/distribute/essentials/quality/core.html`）专门为平板应用提供了指南；在 Google Play 上发布应用的清单（Launch Checklist）（`http://developer.android.com/distribute/tools/launch-checklist.html`）以及针对在不同市场销售应用的本地化清单（Localization Checklist）。本节剩余部分将更详细地讨论你的一些需求和其他考虑因素。

```
http://developer.android.com/distribute/tools/localization-checklist.html
```

#### 10.2.1 测试你的应用

你应该在各种设备上彻底测试你的应用。应用在电脑模拟器上可能运行完美，但在特定的 Android 设备上运行时可能会出现问题。Google 的云测试实验室帮助你在各种设备上测试应用。

```
https://developers.google.com/cloud-test-lab
```

#### 10.2.2 用户许可协议

你可以在应用中包含用户许可协议（EULA）。EULA 是你向用户授权软件的协议。它通常规定了使用条款、分发和反向工程的限制、产品责任、遵守适用法律等。在为应用起草 EULA 时，你可能需要咨询律师。要查看 EULA 示例，请参

```
http://www.rocketlawyer.com/document/end-user-license-agreement.html
```

#### 10.2.3 图标与标签

为你的应用设计一个图标，并提供一个文本标签（名称），该名称将出现在 Google Play 和用户的设备上。该图标可以是你的自定义 Logo、应用中的图片或自定义图像。Google 的 Material Design（材料设计）文档提供了你为应用设计时需要考虑的所有细节：

```
https://www.google.com/design/spec/style/icons.html
```

产品图标为 48-48 dp，并带有 1-dp 的边框。Android 将这些图标缩放为各种屏幕尺寸和密度的所需尺寸。因此，指南建议你使用 192-192 dp 且带有 4-dp 边缘的图标——大图像缩小到较小尺寸的效果比小图像放大到较大尺寸的效果更好。Google Play 还会显示高分辨率应用图标。该图标要求：

- 512-512 像素
- 32 位 PNG格式
- 最大 1 MB

由于图标是最重要的品牌资产，拥有一个高质量的图标至关重要。考虑聘请一位经验丰富的平面设计师帮助你创建一个引人注目且专业的图标。图 10.1 列出了一些提供免费、专业设计图标以及自定义图标设计服务的集合和网站。一旦你创建了图标，就可以使用 Android Studio 将其添加到项目中（如你在 4.4.9 节中所做的那样），它根据根据原始图标生成各种尺寸的图标：

| 公司 | URL | 服务 |
|---|---|---|
| glyphlab | `http://www.glyphlab.com/icon-design/` | 设计自定义图标。 |
| Iconiza | `http://www.iconiza.com/` | 以固定费用设计自定义图标并出售图标。 |
| The Iconfactory | `http://iconfactory.com/home` | 自定义和库存图标。 |
| Rosetta® | `https://design.rosetta.com/` | 付费设计自定义图标。 |
| The Noun Project | `https://thenounproject.com/` | 来自许多艺术家的数千个图标。 |
| Elance® | `http://www.elance.com` | 搜索自由图标设计师。 |

> 图 10.1 | 某些自定义图标设计形式。

#### 10.2.4 应用的版本控制

为你的应用包含版本名称（显示给用户）和版本代码（Google Play 初始使用的整数）是非常重要的，并考虑你的更新版本编号策略。例如，你应用的首个版本名称可能是 1.0，次要更新应为 1.1 和 1.2，下一次大更新为 2.0。版本代码是一个从 1 开始的整数，每发布一个应用的新版本，该代码就会加 1。有关更多指南，请参阅“应用版本控制”，位于：

```
http://developer.android.com/tools/publishing/versioning.html
```

#### 10.2.5 使用许可服务控制付费应用的访问

许可服务（Licensing service）允许你创建许可策略来控制付费应用的访问。例如，你可能使用许可策略限制允许的设备安装次数。要了解更多关于许可服务的信息，请访问

```
http://developer.android.com/google/play/licensing/index.html
```

#### 10.2.6 代码混淆

你应该对任何上传到 Google Play 的应用进行“混淆”，以防止代码被反向工程并保护你的应用。ProGuard 工具——当你以发布模式（release mode）构建应用时——会缩小 APK（包含用于安装的应用的 Android 包文件）的大小，通过删除未使用的代码并将类和方法重命名为模糊名称来优化并混淆代码。要学习如何设置和使用 ProGuard 工具，请访问

```
http://developer.android.com/tools/help/proguard.html
```

#### 10.2.7 获取用于应用数字签名的密钥

在将应用上传到 Google Play 或或其他市场之前，你必须使用标识你为应用作者的数字证书对 .apk 文件进行数字签名。数字证书可以使用私钥（用于加密它的密码）进行自签名；你不需要从第三方机构购买证书（这只是一个候选项）。当 Android Studio 在模拟器或设备上执行以调试为目的的运行你的应用时，它会自动对你的应用进行签名。该数字证书不适用于 Google Play。有关对你的应用进行数字签名的详细说明，请参阅“应用签名”

```
http://developer.android.com/tools/publishing/app-signing.html
```

#### 10.2.8 特色图片与截图

Google Play 在你的应用列表页中显示宣传图形和截图——这些内容为潜在买家提供了对你应用的第一印象。

##### 特色图片 (Featured Image)

Google Play 使用特色图片在手机、平板以及 Google Play 网站上推广你的应用。以下 Android Developers 博客讨论了特色图片的重要性和要求：

```
android-developers.blogspot.com/2011/10/featured-image.html
```



### 使用 Android 设备管理器屏幕工具

你可以为每个运行你应用的设备（智能手机、小平板电脑、大号平板电脑、Android TV 和 Android Wear）最多上传八张截图。

### 为发布准备应用

截图提供了你应用的预览，因为用户在下载之前无法测试它——尽管他们可以在购买后两小时内退回应用退款。选择展示应用功能的吸引人的截图。图 10.2 描述了这些要求。

| 规格 | 说明 |
|---|---|
| 尺寸 | 宽度或高度至少为 320 像素，最大为 3840 像素。 |
| 格式 | 24 位 PNG 或 JPEG（支持透明度）。 |

**图 10.2** | 截图规格。

## 10.3 为你的应用定价：免费还是付费

### 变现应用的方式

- 销售付费升级版。
- 销售虚拟商品（第 10.5 节）。
- 将应用出售给某公司并由其进行品牌化。
- 使用移动广告服务投放应用内广告（第 10.4 节）。
- 直接向你的客户出售应用内广告空间。
- 利用它来带动功能丰富版本的应用的销售。

图 10.6 | 应用变现的方式。（第 2 部分，共 2 部分。）

### 10.3.1 付费应用

应用的平均价格随类别而异。例如，根据应用发现网站 `http://www.appbrain.com`，益智类应用的平均价格为 1.51 美元，商务应用的平均价格为 8.44 美元。尽管这些价格看起来很低，但请记住，成功的应用可以出售数万、数十万甚至数百万份。

当你决定为你的应用定价时，请从研究竞争对手开始。他们收取多少费用？他们有相似的功能吗？你的应用功能是否丰富？以比竞争对手更低的价格提供应用会吸引用户吗？你的目标是收回开发成本并产生额外收入吗？

如果你改变了策略，最终可以将你的付费应用改为免费；但目前无法将你的免费应用改为付费应用。

Google Play 中付费应用的财务交易由 Google Wallet 处理：

`http://google.com/wallet`

尽管某些移动运营商（如 AT&T、Sprint 和 T-Mobile）的客户选择使用运营商账单在他们的无线账单中支付应用费用。你的收益每月支付到你的 Google Payments 商户账户。你负责对你通过 Google Play 赚取的收入缴纳税款。

### 10.3.2 免费应用

超过 90% 的应用下载是免费的，这一比例多年来一直在增加。鉴于用户如果发现应用是免费的更有可能下载，请考虑提供应用的免费“轻量”版本以鼓励用户尝试。例如，如果你的应用是一个游戏，你可以提供一个仅包含前几关的免费版本。当用户玩完免费关卡后，应用将提供通过 Google Play 购买具有更多关卡的更强大应用的选项。或者，你的应用将显示一条消息，用户可以在应用内购买额外关卡以进行无缝升级（参见第 10.5 节）。许多公司使用免费应用来建立品牌意识并推动其他产品和服务的销售（图 10.7）。

3. `http://www.appbrain.com/stats/android-market-app-categories`
4. `http://support.google.com/googleplay/android-developer/answer/137997?hl=en&ref_topic=15867`
5. `http://www.statista.com/topics/10022/mobile-app-usage`

| 免费应用 | 功能 |
| :--- | :--- |
| Amazon® Mobile | 在 Amazon 上浏览并购买商品。 |
| Bank of America | 定位所在地区的 ATM 和银行网点，检查余额和账单。 |
| Best Buy® | 浏览并购买商品。 |
| CNN | 获取最新的世界新闻，接收突发报警并观看直播视频。 |
| Epicurious | 查看来自 Condé Nast 杂志、Gourmet 和 Bon Appetit 的数千份食谱。 |
| ESPN® ScoreCenter | 设置个性化计分器，跟踪你喜爱的大学和职业体育队。 |
| NFL Mobile | 获取最新的 NFL 新闻和更新、直播节目、NFL play 等等。 |
| UPS® Mobile | 跟踪包裹、寻找投递点、获取估算费用等。 |
| NYTimes | 免费阅读《纽约时报》的文章。 |
| Pocket Agent™ | State Farm 保险允许你联系代理人、提交理赔、寻找本地维修中心、检查你的 State Farm 银行和互助账户等。 |
| Progressive® Insurance | 报告理赔并提交车祸现场照片、寻找当地代理人、在购买新车时获取安全信息等。 |
| USA Today | 阅读《美国今日早报》的文章并获取最新的体育比分。 |
| Wells Fargo Mobile | 定位所在地区的 ATM 和银行网点，检查余额，进行转账并支付账单。 |
| Women's Health Workouts Lite | 查看来自领先女性杂志之一的众多健身课程。 |

图 10.7 | 公司使用免费的 Android 应用来建立品牌意识。

## 10.4 通过应用内广告变现应用

许多开发者提供带有应用内广告的免费应用——通常是类似于你在网站上看到的横幅广告。移动广告网络如 AdMob

`http://www.google.com/admob/`

和 Google AdSense for Mobile

`http://www.google.com/adsense/start/`

会为你汇总广告并向你的应用投放相关广告（参见第 10.13 节）。你根据点击次数获得广告收入。前 100 个免费应用每天可能收入数百到几千美元。对于大多数应用来说，应用内广告无法产生大量收入，如果你的目标是收回开发成本并盈利，你应该考虑为你的应用收费。

## 10.5 应用变现：使用应用内结算销售虚拟商品

Google Play 的应用结算服务

`http://developer.android.com/google/billing`

允许你在 Android 2.2 或更高版本上销售虚拟商品（例如，数字内容）（图 10.8）。要使用应用结算，你需要一个 Google Play 商户账户；它不适用于第三方商店的应用。

| 功能 | 说明 |
| :--- | :--- |
| 虚拟商品 | 数字内容 |
| 订阅 | 周期性支付 |
| 服饰 | 衣物物品 |
| 电子卡 | 礼品卡 |
| 壁纸 | 背景图像 |
| 音频 | 音乐和音效 |
| 图标 | 符号 |
| 宠物 | 虚拟动物 |
| 视频 | 电影和片段 |
| 货币 | 游戏货币 |

销售虚拟商品在《愤怒的小鸟》、《扑克大师》和《糖果传奇》等游戏中特别流行。要实现应用结算，请按照以下地址的操作：

`http://developer.android.com/google/billing/overview.html`

有关应用结算的更多信息，包括安全最佳实践，请访问：

`http://developer.android.com/google/billing/index.html`

## 10.6 注册 Google Play

要在 Google Play 上发布应用，你需要在此处注册：

`http://play.google.com/apps/publish`

注册费用为一次性的 25 美元。与其他流行的移动平台不同，Google Play 上传应用没有审核流程，尽管有一些自动测试。你必须遵守 Google Play 开发者计划政策。如果你的应用违反了这些政策，可能会被移除；严重或反复违反可能会导致账户被终止（图 10.10）。

### 违反 Google Play 开发者内容政策的行为

- 侵犯他人的知识产权（例如商标、专利和版权）。
- 非法活动。
- 侵犯个人隐私。
- 干扰其他的服务。
- 损害用户的设备或个人数据。
- 赌博。

## 10.7 设置 Google Payments 商户账户

### 违反 Google Play 开发者内容政策的行为

- 创建“垃圾邮件”用户体验（例如，误导用户关于应用的用途）。
- 对您的应用服务费用或无线运营商网络产生负面影响。
- 冒充或欺骗。
- 宣扬仇恨暴力。
- 提供色情或淫秽内容，或任何不利于 18 岁以下儿童的内容。
- 系统级通知和小部件中的广告。

**图 10.10** 部分违反 Google Play 开发者内容政策的行为（`http://play.google.com/developer/content-policy.html#showlanguages`）。（共 2 部分中的后部分。）

## 10.7 设置 Google Payments 商户账户

要在 Google Play 上销售应用，您需要一个 Google Payments 商户账户，该账户适用于 150 多个国家的 Google Play 开发者。一旦您在以下地址注册并登录 Google Play：

```
http://play.google.com/apps/publish/
```

点击设置商户账户链接并提供：

- Google 可与您联系的信息，以及
- 用户可以与您联系的客户支持联系信息。

## 10.8 将您的应用更新到 Google Play

一旦您准备好文件并准备好上传应用，请查看“发布清单”（Launch Checklist）中的步骤：

```
http://developer.android.com/distribute/tools/launch-checklist.html
```



然后，在 `http://play.google.com/apps/publish`（第 10.6 节）登录 Google Play，并点击“在 Google Play 上发布应用”按钮开始上传过程。您将被要求使用以下资源：

- 1. 应用`.apk`文件，包含应用代码文件、资产、资源和清单文件。
- 2. 至少两张包含在 Google Play 中的应用截图。您可以包含 Android 手机、7 英平板电脑、10 英平板电脑、Android TV 和 Android Wear 的截图。
- 3. 应用在 Google Play 中的高分辨率应用图标（512x512 像素）。
- 4. 特性图形用于 Google 编辑团队推广应用和您的应用产品页面。这必须是 1024 像素宽 x 500 像素高的 JPEG 格式，或无 Alpha 通道的 24 位 PNG 格式。
- 5. 宣传图形（可选），当 Google 决定推广您的应用时供 Google 使用（例如，查看 Google Play 上某些调优应用的图形）。该图形必须是 180 像素宽 x 120 高的 JPEG 格式，或无 Alpha 通道的 24 位 PNG 格式。
- 6. 宣传视频（可选），包含在 Google Play 中。您可以包含应用宣传视频的 URL（例如，演示您的应用如何运行的 YouTube 链接）。

除了应用资源外，您还被要求为 Google Play 提供以下其他列表详情：

- 1. 语言。默认情况下，您的应用将以英语列出。如果您想以其他语言列出，从提供的列表中选择（图 10.11）。

| 非南利尔语 | 英语 (英国) | 柬棉语 | 罗马尼亚语 |
|---|---|---|---|
| 阿姆哈拉语 | 爱沙尼亚语 | 韩语（南） | 俄语 |
| 阿拉语 | 菲律宾语 | 尔语吉斯语 | 塞尔亚语 |
| 亚美尼亚语 | 芬兰语 | 老挝语 | 斯洛伐克语 |
| 阿塞疆语 | 法语 | 立陶宛语 | 斯洛文尼亚语 |
| 巴斯克语 | 法语（加拿大） | 加利西亚语 | 西班牙语（拉丁美洲） |
| 白俄罗斯语 | 德语 | 马其顿语 | 西班牙语（西班牙） |
| 孟加拉语 | 格鲁吉亚语 | 马来语 | 西班牙语（美国） |
| 保加利亚语 | 希腊语 | 马雅拉姆语 | 斯瓦希尔语 |
| 缅甸语 | 希伯来语 | 马拉地语 | 瑞典语 |
| 加泰罗尼亚语 | 印地语 | 蒙古语 | 泰米语 |
| 中文（简体） | 匈牙利语 | 尼泊尔语 | 泰卢语 |
| 中文（繁体） | 冰岛语 | 挪威语 | 泰语 |
| 捷克语 | 印尼语 | 波斯语 | 土耳其语 |
| 丹麦语 | 意大利语 | 葡萄牙（巴西） | 乌克兰语 |
| 荷兰语 | 日语 | 葡萄牙（葡萄牙） | 越南语 |
| 英语 | 卡纳达达语 | 罗马尼亚语 | 祖鲁语 |

**图 10.11** 在 Google Play 中列出的语言

- 2. 标题。应用在 Google Play 中的标题（最多 30 个字符）。它在所有 Android 应用中应该是唯一的。
- 3. 短描述。应用的短描述（最多 80 个字符）。
- 4. 描述。应用的功能描述（最多 4000 个字符）。建议在描述的最后部分说明应用需要哪些权限以及如何使用。
- 5. 最新更改。应用最新版本的说明（最多 500 个字符）。

## 10.9 从应用内启动 Play Store

- 6. 宣传文字。用于营销应用的宣传文字（最多 80 个字符）。
- 7. 应用类型。选择“应用”或“游戏”。
- 8. 类别。选择最适合您的游戏或应用的类别。
- 9. 价格。要付费出售应用，您需要设置“高级年龄”、“中级年龄”、“低级年龄”或“所有人”。
- 10. 内容。应用的内容分级。
- 11. 位置。默认情况下，您的应用将以英语列出。如果您想以其他语言列出，从提供的列表中选择（图 10.11）。
- 12. 网站。用户可以查找更多信息的网站 URL。
- 13. 电子邮件。Google 可与您联系的电子邮件地址。
- 14. 电话号码。用户可以与您联系的电话号码。
- 15. 隐私政策。您的隐私政策链接。

## 10.13 营销你的应用

| 平台 | URL |
| --- | --- |
| Android | http://developer.android.com |
| iOS (Apple) | http://developer.apple.com/ios |
| Windows | https://dev.windows.com/en-us/windows-apps |

**图 10.13** | 热门的移动应用平台。

| 工具 | 网站 |
| --- | --- |
| Appcelerator Titanium | http://www.appcelerator.com/product/ |
| PhoneGap | http://phonegap.com/ |
| Sencha | http://www.sencha.com/ |
| Visual Studio | https://www.visualstudio.com/en-us/features/mobile-development-vs.aspx |
| Xamarin | https://xamarin.com/ |

**图 10.14** | 用于开发跨平台移动应用的若干工具——此类工具非常多。

## 10.13 营销你的应用

一旦你的应用发布，你就会希望向你的受众对其进行营销。¹10 通过 Facebook、Twitter、Google+ 和 YouTube 等社交媒体网站进行病毒式营销可以帮助你获取用户。这些网站具有巨大的可见性。根据 Pew 研究中心的一项研究，71% 的互联网用户使用社交网络。¹11 图 10.15 列出了一些最流行的社交媒体网站。电子邮件和电子通讯仍然是有效且廉价的营销工具。

| 名称 | URL | 描述 |
| --- | --- | --- |
| Facebook | http://www.facebook.com | 社交网络 |
| Instagram | https://instagram.com/ | 照片和视频共享 |
| Twitter | http://www.twitter.com | 博客、社交网络 |
| Google+ | http://plus.google.com | 社交网络 |
| Vine | http://www.vine.co | 社交视频共享 |
| Tumblr | http://www.tumblr.com | 博客 |
| Groupon | http://www.groupon.com | 每日交易 |

**图 10.15** | 热门的社交媒体网站。（两部分的第一部分）

- 10. 移动应用营销有很多方法。请访问 http://amzn.to/ZgpVXZ 查看最新方法。
- 11. 访问 http://bits.blogs.nytimes.com/2015/01/09/americans-use-more-online-social-networks/?_r=0 查看相关研究。

## 第 10 章 Google Play 和应用业务问题

| 名称 | URL | 描述 |
| --- | --- | --- |
| Foursquare | http://www.foursquare.com | 签到 |
| Snapchat | http://www.snapchat.com | 视频消息 |
| Pinterest | http://www.pinterest.com | 在线贴板 |
| YouTube | http://www.youtube.com | 视频共享 |
| LinkedIn | http://www.linkedin.com | 商务社交网络 |
| Flickr | http://www.flickr.com | 照片共享 |

**图 10.15** | 热门的社交媒体网站（第二部分）。

## Facebook

Facebook 是领先的社交网络网站，拥有 15 亿活跃用户¹²，每天活跃用户最多¹³。它是病毒式营销的极佳资源。通过为你的应用或业务建立官方 Facebook 页面。使用该页面发布应用信息、新闻和更新、评论、技巧、视频、截图、游戏高分、用户反馈以及指向 Google Play 的链接，用户可以在那里下载你的应用。例如，你需要传播口碑。鼓励你的同事和朋友“点赞”你的 Facebook 页面，并要求他们的朋友也这样做。当人们与你的页面互动时，故事将出现在他们的朋友动态中，从而建立不断增长的受众认知度。`www.facebook.com/deite1Fahn`

## Twitter

Twitter 是一个博客社交网络网站，拥有约 1 亿用户和 3.16 亿月活跃用户¹⁴。你发布消息——140 个字符或少。Twitter 然后会将你的推文发送给所有的关注者（在写作时，一位著名的流行星拥有超过 2000 万粉丝）。许多人会就你的应用推文——发布新版本的公告、技巧、事实以及用户的评论等。此外，鼓励你的同事和朋友就你的应用推文。例如，当在你的 Twitter Feed流中使用《Android 6 for Programmers》时，我们使用了标签 `#AndroidFP35`。你可以使用此标签编写关于你应用的评论。这使你能够搜索相关信息。

## 病毒式视频

在网站上（如 YouTube）、社交网络上（如 Facebook、Instagram、Google+）、通过电子邮件等分享视频——传播你的应用的另一种方式。

- 12. 访问 http://bits.blogs.nytimes.com/2015/01/09/americans-use-more-online-social-networks/?_r=0 查看相关数据。
- 13. 访问 http://bits.blogs.nytimes.com/2015/01/09/americans-use-more-online-social-networks/?_r=0 查看相关数据。
- 14. 访问 http://bits.blogs.nytimes.com/2015/01/09/americans-use-more-online-social-networks/?_r=0 查看相关数据。

## 10.13 营销你的应用

## 电子邮件通讯

如果你有电子邮件通讯列表，请使用它来推广你的应用。提供指向 Google Play 的链接，用户可以在那里下载。

## 应用评论

联系有影响力的博客作者和网站（图 10.16）来介绍你的应用。这些网站许多免费评论应用。

## 互联网公关

公关行业利用媒体渠道帮助公司将其信息传达给消费者。公关人员将博客、推文、RSS 馈和社交媒体整合到他们的公关活动中。图 10.18 列出了一些免费和付费的互联网公关资源，包括稿发布网站、新闻稿写作等。

## 移动广告网络

购买广告位（例如在其他应用中、在线上、报纸杂志上或广播和电视上）是接触你应用的另一种方式。移动广告网络（图 10.19）专门在平台上投放 Android（以及其他）移动应用的广告。许多网络可以根据位置、无线运营商或平台（例如 Android、iOS、Windows、BlackBerry）对受众进行定位。大多数应用并不盈利，因此在广告上的支出要谨慎。

## 10.14 总结 403

| 移动网络 | URL |
|--- |--- |
| AdMob (Google 提供) | http://www.google.com/admob/ |
| Medialets | http://www.medialets.com |
| Tapjoy | http://www.tapjoy.com |
| Millennial Media® | http://www.millennialmedia.com/ |
| Smaato® | http://www.smaato.com |
| mMedia™ | http://www.mmedia.com |
| InMobi™ | http://www.immobi.com |

**图 10.19** | 移动广告网络。

你可以使用移动广告网络通过在应用中使用广告（例如横幅广告、视频）来实现免费应用的变现。Android 应用的平均 ECPM（每1000次展示有效成本）因网络、设备、国家和地区而异。Android 上的大多数广告支付取决于广告的点击率 (CTR)，而不是生成的展示次数。与 ECPM 类似，CTR 随应用、设备、应用对广告的投放目标以及网络而变化。如果你的应用拥有大量用户且应用内广告的 CTR 较高，你可以获得丰厚的广告收入。此外，你的广告网络可能会提供价格更高的广告，从而增加你的收益。

## 10.14 总结

在本章中，我们介绍了注册 Google Play 的过程并设置了 Google Wallet 账户，以便你能够出售自己的应用。我们讨论了如何准备提交到 Google Play 的应用，包括在模拟器和 Android 设备上进行测试，以及将应用提交到 Google Play 所需的资源。我们介绍了将应用上传到 Google Play 的步骤。我们向你展示了原生 Android 市场。我们提供了应用定价的建议，以及通过应用内广告和虚拟商品销售进行变现的资源。我们还包含了在应用通过 Google Play 上线后进行营销的资源。

## 与作者及 Deitel & Associates, Inc. 保持联系

我们希望你阅读《Android 6 for Programmers》就像我们编写它一样。我们感谢你的反馈。请将你的问题、意见和建议发送至 `deitel@deitel.com`。要获取有关 Android 6 for programmers 的最新新闻，以及 Deitel 出版物和企业培训，请注册 Deitel® Buzz 在线新闻邮件：

```
http://www.deitel.com/newsletter/subscribe.html
```

并在社交媒体上关注我们：

- Facebook—http://facebook.com/DeitelFan
- Twitter—http://twitter.com/deitel
- Google—http://google.com/+DeitelFan
- YouTube—http://youtube.com/DeitelTV
- LinkedIn—http://bit.ly/DeitelLinkedIn

要了解更多关于 Deitel & Associates 为你的公司或组织提供的全球现场编程培训，请访问：

```
http://www.deitel.com/training
```



或发送电子邮件 `deitel@deitel.com`。祝你好运！

## 数字
- 100 目的地 5

## A
- 加速度计 17
- 监听 190
- 加速度计传感器 174
- 访问 Android 142
- 辅助功能 (Accessibility)
  - TalkBack 33, 38, 66
  - TalkBack 本地化 31
  - 辅助功能 32, 36, 38
  - `contentDescription` 属性 67
  - 触摸探索 (Explore by Touch) 9, 38, 66
  - 辅助功能 API 9
- 访问 Android 内容提供者 15
- 动作延迟 (action deferring)
  - `manifest` 文件中的 `action` 元素 103
  - `Intent` 类的 `ACTION_SEND` 常量 313
  - `Intent` 类的 `ACTION_VIEW` 常量 311
- `activity` (活动) 77
- `activity` (活动) 76
- `Activity` 类 76, 77, 93, 94
  - `findViewById` 方法 114, 143
  - `getFragmentManager` 方法 114, 159
  - `getInflater` 方法 144
  - `getResources` 方法 143, 144
  - 带多个参数的 `getString` 方法 133
- `Activity` 类 (续)
  - `getSystemService` 方法 190
  - `host Fragment` 114
  - 生命周期方法 (lifecycle methods) 173, 220
  - `onCreate` 方法 77, 95, 173
  - `onCreateOptionsMenu` 方法 113, 144
  - `onDestroy` 方法 173
  - `onItemItemSelected` 方法
  - `onPause` 方法 173
  - `onResume` 方法 173
  - `onStart` 方法 143, 173
  - `onStop` 方法 173
  - `runOnUiThread` 方法 247
  - `setContentView` 方法 96
  - `setTextInvalidation` 方法 143
  - `setVolumeControlStart` 方法 221, 226
- `<activity>` `AndroidManifest.xml` 中的元素 102
- Activity 未响应 (ANR) 对话 263, 30
- Activity 模板 (templates) 43
- `activity_main.xml` 49
- `findViewByIdException` 类 119, 296
- `adapter` (适配器) 263
- `addView` 类 263
- `FragmentTransaction` 的 `add` 方法 356
  - `SurfaceHolder` 的 `addCallback` 方法 240
  - `RecyclerView` 的 `addDecoration` 方法 307
  - `PreferenceFragment` 的 `addPreferencesFromResource` 方法 161
  - `FragmentTransaction` 的 `toBack` 方法 357
- `ImageView` 的 `adjustViewBounds` 属性
- AdMob 392
- 广告收入 (advertising revenue) 292
- 飞行模式 (airplane mode) 283
- `AlertDialog` 类 118, 174
- `AlertDialog.Builder` 类 118
  - `setItems` 297, 313
- `alpha` (透明度) 值 57
- `View` 的 `alpha` 动画
- `Color` 的 `alpha` 方法 209
- 命名规范 (naming conventions) 68
- 分析 (analysis) 20
- Android 2.2 (Froyo) 7
- Android 2.3 (Gingerbread) 7
- Android 3.0-7
- Android 4.0 (Ice Cream Sandwich) 4.1-4.3
- Android 4.4 7
- Android 6 虚拟设备 (AVD) iv, 16 选项 30
- Android 虚拟设备管理器 (Android Device Manager) 24
- Android 虚拟设备 (AVDs) iv
- Android Wear iv
- Android XML 命名空间 179
- `application` 元素的 `android:back` 属性 101
- `TextView` 的 `android:background` 属性 335
- `android:colorAccent` 89
- `android:colorPrimary` 89
- `android:colorPrimaryDark` 89
- `android:duration` 属性 129
- `android:fromDelta` 属性 129
- `manifest` `application` 的 `android:icon` 属性 101
- `android:id` 属性 54
- `manifest` `activity` 元素的 `android:label` 属性 102
- `manifest` `application` 的 `android:label` 属性 101
- `android:gravity` 属性
- `manifest` `activity` 元素的 `android:name` 属性 102
- `manifest` 元素的 `android:screenorientation` 属性 102
- `android:startOffset` 属性 129
- `manifest` `application` 的 `android:supportRt` 属性 101
- `manifest` `application` 的 `android:theme` 属性 101
- `android:xmlOut` 属性 129
- `manifest` 元素的 `android:windowInputMode` 属性 102
- `android:package` 标签 116, 114, 118, 330
- `android:content` 包 115, 142, 175, 330
- `android:content.res` 包 115, 117, 143
- `android:database` 包 329
- `android:database.sqlite` 包 328
- `android:graphics` 包 175
- `android:graphics.drawable` 包 155
- `android:intent.action.MAIN` 103
- `android:intent.category.LAUNCH` 103
- `android:media` 包 220, 221
- `android:net` 包 311
- `android:os` 包 93, 117, 263
- `android.permission.WRITE_EXTERNAL_PERMISSION` 176
- `android.preference` 包 113
- Android 云到设备消息 (Cloud to Device Messaging)
- Android 设计支持 iv, 16, 122, 265, 298
- Android 开发者 (`developer.android.com`) vi
- Android 开发者博客 388
- Android 设备制造商 iv
- 项目的 Android 设备类型 389
- Android 模拟器 iii, vi
- Android Jelly Bean 10
- Android Market 396
- Android Marshmallow 12
- Android 新组 33
- Android 项目 `res` 文件夹 54, 46, 55
- Android 服务 142
- Android 软件开发包 (SDK) 4
- Android 源码和文档 3, 4
- Android Studio ii, ii, 16, 37 窗口 74, 78
- Android Studio (续) 布局编辑器 36, 37, 38, 44, 49, 52, 60, 67 录屏工具 390
- Android 支持库 iv, 77, 114, 177, 276 vi
- Android 1.5 (Cupcake) 7
- Android 1.6 (Donut) 7
- Android 2.0-2 (Eclair) 7
- Android 2.2 (Froyo) 7
- Android 2.3 (Gingerbread) 7
- Android 3.0-7
- Android 4.0 (Ice Cream Sandwich) 4.1-4.3
- Android 4.4 7
- Android 6 虚拟设备 (AVD) iv, 16 选项 30
- Android 虚拟设备管理器 24
- Android 虚拟设备 (AVDs) iv
- Android Wear iv
- Android XML 命名空间 179
- Android 版本
- 技巧与提示
- Android-style (续)

## B
- 回退栈: 328, 356, 357, 358, 359
  - `pop` 方法: 356, 357
  - `push` 方法
- 背景
  - activity 事件: 226
  - 值的背景属性: 87, 88
- 第一个 `ContentProvider`: 342
- `BaseColumns` 接口: 344
- `FragmentManager` 类的 `beginTransaction` 方法: 356
- 类的行为
- 贝塞尔曲线: 240
- 数据绑定到 List: 269
- `Bitmap`: 175, 214
  - bitmap 编码: 200
  - `createBitmap` 方法: 227
  - `errorClass` 方法: 214
  - `recycle` 方法: 200
- `Bitmap.Config.ARG_8888` 常量: 200
- `BitmapFactory` 类: 277
  - `decodeStream` 方法: 277
- 空数组模板: 43
- `Color` 的 `blue` 方法: 209
- 蓝牙设备: 9
- 蓝牙手写笔支持: 13
- 品牌意识: 392
- 品牌应用
  - Amazon Mobile: 392
  - Bank of America: 392
  - Best Buy: 392
  - CNN: 392
  - Epicurious Recipe: 256
  - ESPCoreCenter: 262
  - NFL Mobile: 392
  - NYTimes: 392
  - Pocket Apple: 392
  - Progressive Insurance: 392
  - USA Today
  - Women's Health Workouts
- 广播接收器: 76
- `Build.VERSION_SDK_INT`: 153
- `Bundle` 类: 96, 95
  - 用于一个 `Intent`: 353
  - `putReplace` 方法: 357
- Button
  - `lines` 属性: 317
  - `textcolor` 属性: 357
- 类: 15, 19
  - 实例变量: 20
  - 类库: 4
- `Activity`: 76, 77, 93
- `ActivityNotFoundException`: 119, 296
- `Adapter`: 263
- `AdapterView`: 263
- `AlertDialog`: 118
- `AlertDialog.Builder`: 118
- `Animation`: 117, 151
- `AnimatorListenerAdapter`: 157
- `AppCompat`: 77, 93
- `ArrayAdapter`: 263, 272
- `ArrayList`: 120, 263
- `AssetManager`: 115
- `AsyncTask`: 263, 330
- `AsyncTaskLoader`: 330
- `Attribute`: 259
- `AudioManager`: 221, 226

## C
- `Bitmap`: 175, 214
- `BitmapFactory`: 277
- `Bundle`: 96
- `Canvas`: 175, 175
- `Collections`: 120
- `Color`: 209
- `Configuration`: 117, 143
- `ContentProvider`: 229, 346
- `ContentResolver`: 175, 330, 342, 347, 351, 353, 354, 374, 380
- `ContentUri`: 343
- `ContentValues`: 350, 374
- `Context`: 142
- `CoordinatorLayout`: 121
- `Cursor`: 329
- `CursorFactory`: 345
- `CursorLoader`: 330
- `DialogFragment`: 114, 159, 160
- `Dialog`: 119
- `Drawable`: 155
- `EditText`: 78, 94, 265
- `FloatingActionButton`: 264
- `Fragment`: 117
- `FragmentManager`: 114, 328
- `FragmentTransaction`: 114, 328, 356, 357
- `FrameLayout`: 224
- `GridLayout`: 78, 81
- `Handler`: 117
- `HttpConnection`: 227
- `ImageView`: 38, 60
- `InputMethodHandler`: 280
- `InputStream`: 155
- `Intent`: 102, 119
- `JSONArray`: 263
- `JSONObject`: 256
- `LayoutInflater`: 114
- `LinearLayout`: 37, 48, 297
- `ListPreference`: 155
- `Loader`: 330, 363, 360
- `Log`: 109, 152
- `MediaStore`: 175
- `MediaStore.Images.Media`: 175
- `Menu`: 113, 144
- `messageInflater`: 144
- `MotionEvent`: 175, 202, 255
- `MultiSelectListPreference`: 115
- `NumberFormat`: 78, 94, 270
- `Path`: 175
- `Preference`: 155
- `PreferenceFragment`: 113, 115, 161
- `PreferenceManager`: 115, 141, 142
- `Printable`: 206, 96
  - `drawable`: 96
  - `id`: 96
  - `layout`: 96
  - `string`: 96
- `RecyclerView`: 296, 307
- `RecyclerView.Adapter`: 297, 307, 332
- `RecyclerView.ItemDecoration`: 297, 307, 332
- `RecyclerView.LayoutManager`: 297
- `RecyclerView.ViewHolder`: 297
- `RelativeAttribute`: 143
- `Resources`: 175
- `ScrollView`: 336
- `Seekbar`: 74, 78, 94
- `Sensor`: 174
- `SensorEvent`: 193
- `SharedPreferences`: 115, 295, 305
- `SharedPreferences.Editor`: 111, 146, 296, 310
- `Snackbar`: 265, 267, 280
- `StartPreview`: 220, 240
- `SQLiteDatabase`: 329
- `SQLiteOpenHelper`: 332
- `SQLiteQueryBuilder`: 348
- `SurfaceHolder`: 221, 240
- `SurfaceView`: 221, 240
- `TextView`: 315, 78, 94
- `Thread`: 221, 252
- `Toast`: 117, 144
- `Uri`: 311, 330
- `UriMatcher`: 346
- `View`: 76, 221
- `View.VISIBLE`: 115
- `ViewGroup`: 338
- 客户区 (client area): 37
- 云计算 (cloud computing): 7
- 云文本 (Cloud Text): xxv, iv, 386
- 代码 (code): 115
- 代码高亮 (code highlighting): xxv, 2
- 代码演练 (code walkthrough): 2
- 代码自动补全 (code-completion): 46, 53
- 代码折叠 (code-folding): 336
- `Color` 类: 209
  - `alpha` 方法: 209
  - `argb` 方法: 210
  - `green` 方法: 209
  - `red` 方法: 209
- 颜色文件夹 (color folder of Android): 46, 115, 116
- 颜色状态列表 (color state list): 118
- 颜色状态资源 (color state resource): 118
- `colorAccent`: 89
- `colorPrimary`: 89
- `colorPrimaryDark`: 89
- `colors.xml`: 126
- `column-count` 属性: 83
- `commit` 方法: 356
- `SharedPreferences.Editor` 的 `commit` 方法: 147
- 包中使用的公司名称: 40
- `Comparator` 对象: 307
- 编译应用 (compiling apps): 386
- 组件 (component): 18
- 当前文档和活动 (current documents and activities): 127
- `Configuration`: 117, 143, 144
- 朝向实例变量 (continent orientation instance variable): 117
- 常量 (Constants): `MODE_PRIVATE` 306
- `MODE_WORLD_READABLE` 306
- `MODE_WRITABLE` 306
- 内容提供者 (content provider): 76
- `contentDescription` 属性 (property of View): 135
- `collections` 类: 120
- 碰撞检测 (collision detection): 221, 235, 244
- 代码 (code): 175
- 色调 (hue): 80
- 阴影 (shade): 80
- 内容提供者权限 (ContentProvider authority): 342
- `ContentProvider` 类: 329, 346, 342, 347, 351, 353, 354, 374, 380
  - `delete` 方法: 353
- `ContentResolver` 类的 `delete` 方法: 380
- `SQLiteDatabase` 类的 `delete` 方法: 354
- 密度无关像素 (deny-independent pixels): 56
- `ContentUtils` 类: 343
- `ContentValues` 类: 350, 374
- `context` 类: 142
- 协调不同应用的努力 (coordinating efforts separate apps): 102
- 边角 (corners of a splash): 335
- 创建布局 (create layout): 139
- `createBitmap` 方法: 200
- `createChooser` 方法: 334
- `createCircular` 方法: 157
- `createFromStream` 方法: 15
- 创建尺寸资源 (creating a dimension resource): 56
- 知识共享公共许可证 (creative commons public license): 260
- 加密密钥 (cryptographic key): 385
- `Cursor` 类: 329
  - `getColumn` 方法: 368
  - `getLong` 方法: 368
  - `moveFirst` 方法: 175, 381
  - `movePosition` 方法: 368
  - `setNotification` 方法: 350
- `ContentWrapper` 类: 15
  - `getAssets` 方法: 152
  - `getSystemService` 方法: 280
  - `startActivity` 方法: 311
- `CoordinatorLayout`: 121
- `CursorFactory`: 345
- `Cursor`: 330
- `View` 的自定义子类: 237
- 自定义键盘: 339
- 项目依赖 (dependencies project): 298
- XML 中的设计预览 (design preview in XML): 46
- 布局中的设计 (Design in the layout): 37
- 开发者文档 (developer document): 386
  - 清单 (Checklist): 33
  - 签署你的应用 (Signing Your Applications): 388
  - 表格 (Table): 10
- 设备捕获 (Device Capture): 389
- 负面动作 (negative action): 118
- 正面动作 (positive action): 118
- `show` 方法: 159
- `DialogInterface` 类: 119
- `DialogInterface.OnClickListener` 类: 110
- 数字证书 (digital certificate): 388
- 签署你的应用: 388
- `EditText` 的属性: 87
- 密度无关像素 (density-independent pixels): 56
- 尺寸资源 (dimension resource): 56, 134
  - 创建 (creating): 364
- 资源外部化 (externalizing resources): 54
- 最终用户许可协议 (End User License Agreement, EULA): 386
- 视图高度 (elevation of a view): 80, 87
- 仿真 (emulation): 16, 386
- 模拟器功能 (emulator functionality): 15
- 模拟器手势和控制 (emulator gestures and controls): 175
- 封装 (encapsulation): 20
- `Log` 类的 `e` 方法: 152
- `SharedPreferences` 类的 `edit` 方法: 146, 309
- 编辑接口 (edit interface): 93
- `EditText`
  - `imeOptions` 属性: 339, 340
  - `inputType` 属性: 339, 340
- `EditText` 类: 78, 94
  - `digits` 属性: 87
  - 输入类型 (input type): 84
  - `matchEach` 属性: 87
  - 限制最少位数 (restrict minimum number digits): 78

## F
- `Fragment` 类 (续)
  - 在 XML 布局中完全限定自定义 `View` 的类名: 174
  - 向后兼容: 302
  - `onCreateView` 方法: 114, 149, 226
  - `onDestroy` 方法: 220
  - `onDetach` 方法: 174, 209, 360, 378
  - `onOptions` 方法: 114, 193
  - `onPause` 方法: 191
  - `getLoaderManager` 方法: 363
  - `getString` 方法: 146, 151
  - `getActivity` 方法: 151
  - `getFragmentByTag` 方法: 159
  - `getSupportFragmentManager` 方法: 114, 143, 135
  - `setArguments` 方法: 357
  - `setHasOptions` 方法: 189
  - `requestPermissions` 方法: 195, 196
  - `shouldRequestPermissionRatio` 方法: 195
- `JSONArray` 类 `JSONObject` 方法 284
- `Uri` 类的 `getLastPathSegment` 方法 349
- `Cursor` 类的 `getLong` 方法 368
- `JSONObject` 类的 `getLong` 方法 284
- `JSONObject` 类的 `getString` 方法 284
- `JSONObject` 类的 `enable` 方法 256
- `JSONObject` 类的 `JSONArray` 方法 284
- `Activity` 类的 `getInflater` 方法 144
- `MotionEvent` 类的 `getPointerContext` 方法 204
- `SQLiteOpenHelper` 的 `getReadableDatabase` 方法: 350
- `onRequestPermissionsResult` 方法: 196
- `requestPermissions` 方法: 195, 189
- `Activity` 类的 `getResources` 方法: 143
- `Context` 类的 `getSharedPreferences` 方法: 306
- `Activity` 类的 `getString` 方法: 313
- `Cursor` 类的 `getString` 方法: 368
- Fragment 布局: 132, 174, 363, 370, 378
- Fragment 生命周期: 114
- Fragment 生命周期方法: 209
- `FragmentActivity` 类
  - `getSupportFragmentManager` 方法: 114, 143, 328
- `FragmentManager` 类: 114
  - `beginTransaction` 方法: 356
  - `popBackStack` 方法
- `MotionEvent` 类的 `getActionIndex` 方法: 203
- `MotionEvent` 类的 `getActionMasked` 方法: 202
- `ContextWrapper` 类的 `setAssets` 方法: 152, 155
- `Context` 类的 `getWindowHandle` 方法: 368
- `Resources` 类的 `getConfiguration` 方法: 143, 144
- `SensorManager` 类的 `getSensorManager` 方法: 150
- `SurfaceView` 类的 `getBackPressed` 方法: 240
- `RecyclerView.Adapter` 类的 `getItemCount` 方法: 318, 368
- `MenuItem` 类的 `getItemID` 方法: 193
- `FragmentTransaction` 类: 114, 326, 357
  - `add` 方法: 356
  - `addToBackStack` 方法: 357
  - `commit` 方法: 356
  - `replace` 方法: 357
- 免费应用 (free apps): 391
- Froyo (2.2): 7
- 全屏模板 (full-screen template): 43
- `SharedPreferences` 类的 `getString` 方法: 311
- `SharedPreferences` 类的 `getStringSet` 方法: 146
- `Context` 类的 `getSystemService` 方法: 280
- `Activity` 类的 `getSystemService` 方法: 190
- `View` 类的 `getTag` 方法: 264
- `ContentProvider` 的 `getType` 方法: 348
- `ArrayAdapter` 类的 `getView` 方法: 273
- `SQLiteOpenHelper` 的 `getEditableDatabase` 方法: 351
- `MotionEvent` 类的 `getX` 方法: 204
- `MotionEvent` 类的 `getY` 方法: 204
- 游戏循环 (game loop): 221, 244, 253
- 游戏机 (game console): 5
- 手势 (gestures)
  - 双击 (double tap)
  - 双指触摸 (two-finger touch)
  - 拖拽 (drag)
  - 长按 (long press)
  - 捏合 (pinch)
  - 双指缩放 (pinch zoom)
  - 滑动 (swipe)
  - 点击 (tap)
- GridLayout (网格布局)
  - `columnCount` 属性 83
  - 视图的 `layout:column` 属性 84
  - 视图的 `layout:columnSpan` 属性 84
  - 视图的 `layout:row` 属性 84
  - `rowCount` 属性 83
  - `useDefaultMargins` 属性 83
- `GridLayout` 类: 78, 381
- GPU (图形处理器): iii
- 重力传感器 (gravity sensor): 174
- 绿线 (green line) in editor: 62
- `Color` 类的 `green` 方法: 209
- `TextView` 的 `gravity` 属性: 58, 88
- GUI (图形用户界面) 组件视图: 37
  - `EditText`: 78
  - `ImageView`: 38, 49, 60
  - 命名规范: 82
  - 程序化创建: 144
  - `ScrollView`: 338
  - `SeekBar`: 74, 78
  - `TextView`: 38, 49, 54
  - `ViewGroup`: 338
- GUI 设计视图: 117, 263, 330
- 布局编辑器中的指南 (guidelines in layout editor): 60
- 陀螺传感器 (gyroscope sensor): 174

## H
- `Handler`: 117, 160
- 硬件加速 (hardware acceleration)
- 硬件支持 (hardware support): 115
- 行高 (row height): 381
- 浮动操作按钮 (FloatingToggleButton): 338
- 隐藏软键盘 (hide soft keyboard)
- `InputMethodManager` 的 `hideSoftInputWindow` 方法: 280
- `Activity` 的层级父节点 (hierarchy parent of an Activity): 163
- `TextView` 的 `hint` 属性: 86
- `Activity` 的宿主 (host of an Activity): 114, 115
- `HttpURLConnection` 类: 277
  - `disconnect` 方法: 277
- 连接策略 (connection strategy): 394
- 超文本传输协议 (HTTP): 260
- `InflateLayout` 类的 `inflate` 方法: 149
- 在布局 GUI 中填充元素: 241
- 继承 (inheritance): 200
- 内存数据库 (in-memory database): 345
- `EditText` 的输入类型 (input type): 84
- `InputMethodManager` 类: 280
  - `hideSoftInputWindow` 方法: 280
- `ContentProvider` 的 `insert` 方法: 350
- `ContentResolver` 的 `insert` 方法: 374
- `SQLiteDatabase` 类的 `insert` 方法: 351
- `MediaStore.Images.Media` 类的 `insert` 方法: 175
- 实例 (instance): 19
- 实例变量 (instance variable): 20
- `Intent`: 257
- `Intent` 类: 109
  - `ACTION_SEND` 方法: 314
  - `ACTION_EDIT` 方法: 314
  - `createChooser` 方法: 311
  - 显式 (explicit) 296
  - 隐式 (implicit) 119, 296
  - `putExtra` 方法: 314
  - `resolveActivity` 方法: 119
  - extras 314
- 意图过滤器 (intent filter): 119
- 消息 (messages): 102, 119
- 在 `AndroidManifest.xml` 中: 103
- 过滤器元素 (filter elements): 103
- 实例: 114
- 本地化: 37, 54, 67, 124
- 多个应用之间的协调: 102
- 启动活动 (starting an activity): 103
- 接口 (Interfaces)
  - `BaseColumns` 314
  - `DialogInterface.OnClickListener` 119
  - 可编辑 (Editable) 93
  - 在 Java 中实现方法 (implementing methods in Java) 399
  - `List` 120
  - `Loader.LoaderCallback` 330
  - `OnClickListener` 监听器 311
  - `OnSeekBackHandler` 98
  - `SeekBar.OnSeekChangeListener` 监听器 94, 210
  - `SensorEventListener` 192
  - `Set` 120
  - `SurfaceHolder.Callback` 221, 240, 250
  - `TextWatcher` 79, 307
  - `View.OnClickListener` 351
  - `View.OnLongClickListener` 311
- 本地化 (localization): 37, 38, 67, 78
- Internet 公共资源
  - ClickPress 402
  - eleases 402
  - Markerwise 402
  - Shop 402
  - Newline 402
  - open 402
  - Leap 402
  - Log 402
  - Web 402
  - `View` 类的 `with` 方法: 200
- 一个 REST web 服务: 282
- JSON (JavaScript Object Notation) 261
- JSON 对象符号 (JSONObject): 257
- `JSONArray` 类: 263
  - `getObject` 方法: 284
  - `getDouble` 方法: 284
  - `getJSONArray` 方法: 284
  - `getLong` 方法: 284
  - `getString` 方法: 284
- `Map` 接口的 `keySet` 方法: 307
- 与应用相关的键值对 (key-value pairs associated with an app): 114, 295

## L
- 横屏模式 (landscape mode): 241
- 横向方向 (landscape orientation): 102
- `landscapeorientation`: 36
- 大尺寸设备 (large-sized devices): 8
- 启动另一个应用 (launching another app): 311
- 启动活动 (launching an activity): 103
- `<activity>` 元素
  - `"singleTop"` 163
  - `"standard"` 163
- 创建新的 (creating new): 139
- 布局编辑器 (layout editor): 36, 37, 38, 44, 49, 52, 60
  - 指南线 (guidelines): 60
  - 调色板 (palette): 48
  - 工具包 (toolkit): 61
- 项目布局文件夹 (project layout folder): 47
- 布局设计 (layout design): 46
- GridLayout 中的布局列 (`layout:column`): 84
- GridLayout 中的布局列跨 (`layout:columnSpan`): 84
- 视图的 `layout:gravity` 属性: 59, 61, 88, 134
- 视图的 `layout:margin` 属性: 134
- GridLayout 中的布局行 (`layout:row`): 84
- 视图的 `layout:weight` 属性: 60, 61, 134
- `layoutType` 类: 114
- `activity_main.xml`: 49
- `JSONArray` 长度 (length): 284
- Java: 354
- Java 基础 (Java fundamentals): 314
- Java 开发工具包 (JDK): 351
- 如何使用 Java SE 7 (How to Program)
- `java` 包: 155
- `java.util` 包: 78, 94
- 键盘: 5
- 键盘类型 (keyboard type): 333
- Android 许可 (Android licenses): 4
- 许可政策 (licensing policy): 388
- 生命周期方法 (lifecycle methods): 173, 220
- 应用的生命周期方法 (app lifecycle methods): 93
- 光传感器 (light sensor): 174
- 线厚度 (line thickness): 175
- 线性加速度 (linear acceleration): 170
- 直线方向 (straight direction): 53
- `LinearLayout`: 37, 48
  - `showDividers` 属性: 348
  - `weightSum` 属性: 336
- `RecyclerView` 的 `LinearLayoutManager`: 297, 307
- 按钮次数 (button presses): 137
- 链接你的应用 (linking your app): 395
- `list` 接口: 120
- `AssetManager` 类的 `list` 方法: 152
- `listPreference` 类: 115
- `listview`: 360
- 数据绑定 (data binding): 263
- 性能 (performance): 264
- 适配器方法 (adapter methods): 279
- 平滑滚动到位置方法 (smoothScrollToPosition): 283
- `SoundPool` 类的 `load` 方法: 241
- `AnimationUtils` 类的 `load` 方法: 117, 151
- `Loader` 类: 330, 363
- `LoaderManager` 类: 330, 363
- `Loader.LoadCallback` 接口: 330
- `onCreateLoader` 方法: 365, 374, 381
- `loadReset` 方法: 365, 375, 381
- `loadFinished` 方法: 365, 375, 381
- 本地化 (localization): 37, 54, 67, 124
- 本地化清单 (localization checklist): 271
- 本地化资源 (localized resources): 68
- 锁屏小组件 (lock screen widgets): 120
- `SurfaceHolder` 类的 `lockCanvas` 方法: 253
- `Log` 类: 119, 152
- Android Studio-DDMS 视角: 119
- Android 中的 LogCat 标签: 119
- `logcat` 工具: 119
- 日志异常 (logging exceptions): 119, 152
- 长按 (long press): 239
- 长时间操作 (long-running operations): 263, 330

## M
- Max OS X 16
- 磁场传感器 (magnetic field sensor): 174
- 主线程 (main thread): 117
- `Lint` 类的 `makeText` 方法: 140
- `activity` 元素
  - `android:label` 属性 102
  - `android:name` 属性 102
  - `android:screenOrientation` 属性 102
  - `android:windowSoftInput`
- `application` 元素
  - `android:allowBackup`
  - `android:icon` 属性 101
  - `android:label` 属性 101
  - `android:supportsRtl` 属性 101
  - `android:theme` 属性
- `AndroidManifest.xml` 中的 `manifest` 元素 101
- 手动解析的文件类型 (manually parse file types): 223
- `Map` 接口
  - `keySet` 方法 307
- `mashup`: 55
- 主/详情模板 (master/detail flow template): 43
- Material Design (材料设计)
  - 元素: 11, 12, 264
  - 颜色调色板: 38, 57
  - 图标: 127
  - Material 3 主题规范 (Material 3 theme spec)
  - 矢量图标: 178
- `SeekBar` 的 `max` 属性: 88
- `EditText` 的 `maxLength` 属性: 87
- 媒体文件 (media files): 220
- `MediaStore` 类: 175
- `MediaStore.Images.Media` 类: 175
  - `InsertImage` 方法: 175
- 中号字体 (medium font): 84
- `Menu` 类: 113, 144, 193
- Android 项目中的菜单文件夹: 46, 115
- 菜单项 (menu items)
  - `showAsAction` 属性: 128, 179
- `MenuInflater` 类: 143, 193
  - `inflate` 方法: 144
- `MenuItem` 类
  - `getItemId` 方法: 193
- 商户账户 (merchant account): 391, 395
- `MODE_WORLD_WRITABLE` 常量: 306
- 数字格式指定符 (number format specifiers): 124
- `Activity` 类的 `onCreate` 方法: 77, 95, 173
- `Fragment` 类的 `onCreateView` 方法: 114, 149, 226
- 应用变现 (app monetization): 385, 392
- 数字输入 (numeric input): 78
- `MotionEvent` 类的 `onCreateIndexHolder` 方法: 175, 200, 220, 251
- `RecyclerView.Adapter` 类的 `getIndex` 方法: 368
- 数字小键盘 (numeric keypad): 74
- `Activity` 类的 `onDestroy` 方法: 173, 220
- 代码混淆 (code obfuscation): 388
- 对象 (object): 18
- `onDestroy` 方法: 220, 227
- `getActionMasked` 对象 (实例): 20
- `Fragment` 的 `onDetach` 方法: 174, 209, 363, 202
- 面向对象分析与设计 (OOAD): 20, 370, 378
- `MotionEvent` 类的 `getPointerContext` 方法: 204
- 面向对象语言 (object-oriented language): 20
- `Fragment` 的 `onDetach` 方法: 174, 209, 363
- `getWnd` 方法: 204
- 面向对象编程 (OOP): 21, 23
- `SQLiteOpenHelper` 类的 `moveToFirst` 方法: 345
- `Cursor` 类的 `moveToPosition` 方法: 368
- `View` 类的 `onDraw` 方法: 201, 231
- `View` 类的 `onSizeChanged` 方法: 200, 241
- `LoaderManager.LoaderCallbacks` 接口的 `onLoaderReset` 方法: 365, 375, 378
- 多媒体 (multimedia): 381
- 多个格式指定符 (multiple format specifiers): 124
- `MultiSelectListPreference` 接口: 115
- `LoaderManager.LoaderCallbacks` 接口的 `onLoadFinished` 方法: 374, 381
- 多点触控 (multi-touch): 202
- `multitouch`: 5
- 音乐音频流 (music audio stream): 221, 226
- `View` 类的嵌套接口 `OnClickListener`: 311

## N
- 命名规范 (naming conventions)
  - GUI 组件: 82
- 近场通信 (Near Field Communication, NFC): 113, 145
- 对话框中的否定操作 (negative action in dialog): 118
- 网络访问 (network access): 15, 114, 193
- 对话框中的中性操作 (neutral action in dialog): 118, 379
- 新字符串值资源 (new string value resource): 55, 86
- `Activity` 的 `onPause` 方法: 173, 220
- `Fragment` 的 `onResume` 方法: 173, 191, 226
- `AsyncTask` 类的 `onPostExecute` 方法: 277, 282
- `ArrayAdapter` 类的 `notifyDataSetChanged` 方法: 263, 283, 310
- `SeekBar.OnSeekChangeListener` 接口的 `onProgressChanged` 方法: 79
- `Format` 类: 98, 74, 270
- `NumberFormat` 类的 `format` 方法: 97
- `AsyncTask` 类的 `Update` 方法: 277, 282
- `Fragment` 类的 `onRequestPermissionsResult` 方法: 196
- `Activity` 类的 `onResume` 方法: 173, 220
- `Fragment` 类的 `onResume` 方法: 190
- `onSeekBarChangeListener` 接口: 98
- `SensorEventListener` 接口的 `onSensorChanged` 方法: 192
- `View` 类的 `onSizeChanged` 方法: 200, 241
- `Activity` 类的 `onStart` 方法: 143, 173
- `Activity` 类的 `onStop` 方法: 173
- `TextWatcher` 接口的 `onTextChanged` 方法: 79
- `View` 类的 `onTouchEvent` 方法: 175, 202, 220, 251
- `SQLiteOpenHelper` 类的 `onUpgrade` 方法: 345
- OOP (面向对象编程): 21
- Open Handset Alliance: 6
- 开源 (open source): 3
- 开源应用 (open source apps): 4
- 开源项目描述组 (open source project description group): 2
- `HttpURLConnection` 类的 `openConnection` 方法: 277
- 开源资源 (openPR): 402
- 操作系统 (operating system): 6
- 操作系统要求 (OS requirements): xi
- 操作系统服务 (OS services): 15
- 选项菜单 (options menu): 27, 113, 167, 168
- 橙色指南 (orange guidelines): 60
- 横向 (orientation): 36
- `Configuration` 类的实例: 117
- `Linearlayout` 方向 (orientation): 53
- `orientation` 174
- `ORIENTATION_LANDSCAPE` 117
- `ORIENTATION_PORTRAIT` 117
- 原始设备制造商 (OEM) 等.
- 包 (Packages)
  - `android.support.v7.widget` 296
  - `android.text` 16, 79, 93
  - `android.view.animation` 16, 113, 117, 220
  - `android.view.Input` 280
  - `android.widget` 16, 78, 94, 117
  - `java.io` 155
  - `java.util` 120
  - `java.text` 78, 94
  - `org.json` 262
  - `android.content` 15
  - `android.content.res` 15, 142, 175, 343
  - `android.database.sqlite` 15, 329, 348
  - `android.graphics` 15
  - `android.graphics.drawable` 15, 155
  - `android.hardware` 15, 220, 221
- 形状填充元素 (shape fill element): 335
- 值的填充属性 (fill property of value): 87, 88
- 付费应用 (paid apps): 391
- `Paint` 类: 175
  - 带边框填充形状 (filled shape with border): 199
  - 无边框填充形状 (filled shape without border): 199
  - `line` 199
  - `setAlias` 方法: 199
  - `setStrokeCap` 方法: 199
  - `setFixedWidth` 方法: 199
  - `setStyle` 方法: 253
  - `styles` 199
- `Activity` 的父级 (parent of an Activity): 163
- `Path` 类: 175
  - `moveTo` 方法: 203
  - `quad` 方法: 204
  - `reset` 方法: 203
- 支付处理器 (payment processor): 391
- Android 6.0 (Marshmallow): 176, 181
- 包名 (package name): 40
- 推入栈 (push onto back stack): 357
- `Intent` 类的 `putExtra` 方法: 314
- `Buffer` 类的 `parse` 方法: 357
- `SharedPreferences.Editor` 类的 `putString` 方法: 146
- 二次贝塞尔曲线 (quadratic Bezier curve): 240
- `ContentProvider` 类的 `query` 方法: 348
- `SQLiteQueryBuilder` 类的 `query` 方法: 350
- `offset` 方法: 236
- `Bitmap` 类的 `recycle` 方法: 200
- `RecyclerView` 类
  - `addItemDecoration` 方法: 307
  - `setLayoutManager` 方法: 307
  - 列表项 (list items) 297, 307, 332
  - `onBindViewHolder` 方法: 297, 307, 318, 332, 368
- `RecyclerView.LayoutManager`: 297
- `Color` 类的 `red` 方法: 209
- `LayoutManager` 类的 `registerListener` 方法: 190
- `SharedPreferences` 类: 115, 142, 299, 305
  - `edit` 方法: 106, 146, 309
  - `getAll` 方法: 307
  - `getString` 方法: 311
  - `getJSONObject` 方法: 146
- `SoundPool` 类的 `release` 方法: 250
- 从 Market 移除应用 (removing app from Market): 398
- `FragmentTransaction` 类的 `replace` 方法: 357
- 报告书籍 (report books): 1
- 表现层状态传输 (REST): 260
- `EditText` 数字位数限制 (digit limit): 78
- 反向工程 (reverse engineering): 388
- `View` 的旋转动画 (rotation animation): 128
- 旋转向量传感器 (rotation vector sensor): 174
- `rowCount`: 20
- `Intent` 类的 `resolveActivity` 方法: 119
- `View` 类的 `requestFocus` 方法: 308
- `Fragment` 类的 `requestPermissions` 方法: 195, 196
- `Activity` 类的 `runOnUiThread` 方法: 247
- 要求 (requirements): 20
- Android 项目 `res` 文件夹: 46, 54
- `res/drawable-mdpi` 文件夹: 335
- Android 项目的 `res/raw` 文件夹: 220
- `res` 文件: 38
- `res` 文件夹
  - 替代资源规范 (alternative resource qualifiers): 68
  - 默认 (default): 68
  - 本地化检查清单 (localization checklist): 71
  - 本地化资源 (localized resources): 68
  - `style`: 83
- `Resources` 类: 143, 139, 55, 86
  - `getConfiguration` 方法: 143, 144
- 可用的软件组件 (reusable software components): 18
- 复用 (reuse): 19
- 独立密度像素 (sp, scale-independent pixels): 56
- `ImageView` 的 `scaleType` 属性: 135
- 截屏 (screenshots): 389
- 截屏与共享 (screenshot and share): 12
- Android Studio 截图工具: 390
- 屏幕分辨率 (screen resolution): 50
- 屏幕大小 (screen size): 338
- GUI 设计的屏幕类型 (screen types for GUI design): 47
- 状态栏规格 (status bar spec): 389
- `ScrollView` 类: 336, 338
- SDK 版本和 API 级别: 42
- 搜索操作 (Twitter): 287
- `SeekBar` 类: 74, 98
- `SeekBar.OnSeekChangeListener` 监听器: 79, 94, 210
  - `onProgressChanged` 方法: 79
- 向传感器对象发送消息 (sending messages to sensor objects): 174
- `SensorManager` 的 `SENSOR_DELAY_NORMAL` 常量: 190
- `sensor_ACCELEROMETER` 常量: 190
- `SensorEvent` 类: 193
- `SensorEventListener` 接口: 192
- `SensorManager` 类: 190
  - `getDefaultSensor` 方法: 190
  - `registerListener` 方法: 190
  - `unregisterListener` 方法: 191
- 传感器类型
  - 加速度计 (accelerometer): 174
  - 重力 (gravity): 174
  - 陀螺仪 (gyroscope): 174
  - 磁场 (magnetic field): 174
  - 方向 (orientation): 174
  - 压力 (pressure): 174
  - 接近 (proximity): 174
  - 旋转向量 (rotation vector): 174
  - 温度 (temperature): 174
- 服务 (services): 76
- 设置动画属性 (setting animation properties): 118
- `Fragment` 类的 `setArguments` 方法: 357
- `AudioAttributes.Builder` 类的 `setAttributes` 方法: 210, 240
- `Activity` 类的 `setContentView` 方法: 96
- `PreferenceManager` 类的 `setDefaultValues` 方法: 141, 142
- `Animator` 类的 `setDuration` 方法: 157
- `Fragment` 类的 `setHasOptions` 方法: 189
- `View` 类的 `setImageBitmap` 方法: 214
- `InputStream` 类的 `setEnabled` 方法: 155
- `ListView` 类的 `setItems` 方法: 279
- `RecyclerView` 类的 `setLayoutManager` 方法: 307
- `Cursor` 类的 `setNotificationUri` 方法: 350
- 保存日期 (saving dates): 96
- 可缩放矢量 (scalable vector): 127
- `View` 的缩放模式 (scale modes): 206
  - `SCALE_MODE_FILL` 206
  - `SCALE_MODE_FIT` 206
- `SeekBar` 的进度 (progress): 87
- `SeekBar` 的 `max` 属性: 88
- `Animation` 类的 `setRepeatCount` 方法: 117, 151
- `Activity` 类的 `setRequestedMethod` 方法: 143
- `Paint` 类的 `setStrokeCap` 方法: 199
- `Paint` 类的 `setStrokeWidth` 方法: 199
- `Paint` 类的 `setStyle` 方法: 253
- 菜单项的 `showAsAction` 属性: 128, 179
- 线性布局的 `showDividers` 属性: 348
- 类的集合打乱排序 (shuffling a collection): 214
- `Collections` 类: 120
- 签名应用 (signing apps): 368
- 简单集合触摸 (simple collection touch): 220
- `simple_list_item` 368
- 单一应用滑块 (single app slider)
- `SQLiteOpenHelper` 类: 329, 344
  - `getReadableDatabase` 方法: 350
  - `getWritableDatabase` 方法: 351
  - `onCreate` 方法: 345
  - `onDowngrade` 方法: 345
  - `onUpgrade` 方法: 345
- `SQLiteQueryBuilder` 类: 348
  - `append` 方法: 349
  - `query` 方法: 350
  - `setTables` 方法: 349
- `View` 类的 `setVisibility` 方法: 253
- `View` 类的 `setTag` 方法: 264
- 设置硬件选项 (hardware options): 30
- 设置图标 (settings icon): 107, 108
- `AudioAttributes.Builder` 类的 `setUsage` 方法: 221, 240
- `Activity` 类的 `setVolumeControlStream` 方法: 221, 226
- `ImageView` 的 `src` 属性: 53, 62
- 颜色深浅 (shade of color): 80
- `shape` 元素: 335
- `SharedPreferences` 类: 115, 299, 305
  - `edit` 方法: 106
  - `getAll` 方法: 307
  - `getString` 方法: 311
  - `getStringSet` 方法: 146
- 应用星级 (app ratings): 398
- `Animator` 类的 `start` 方法: 118
- `View` 类的 `startActivity` 方法: 117
- `Preference` 类的 `registerOnPreferenceChangeListener` 方法: 142
- `SharedPreferences.Editor` 类: 115, 146, 299, 310
  - `apply` 方法: 146
  - `putString` 方法: 310
- `stateAlways` (虚拟键盘模式): 298
- `Activity` 的状态 (state of an Activity): 77
- 播放音乐的流 (stream for playing music): 226
- `Fragment` 类的 `shouldRequestPermissionRatio` 方法: 195
- `DialogFragment` 类的 `show` 方法: 159
- `FloatingActionButton` 类的 `show` 方法: 308
- `String` 资源: 55
  - 包含多个字段的字符串 (strings with multiple fields): 124
- 区分大小写的字符串比较 (String.CASE_INSENSITIVE_ORDER): 307
- 形状的 `stroke` 元素: 335
- 结构化查询语言 (SQL): 329
- 样式 (style)
  - 定义类: 394
  - GUI 组件的 `style` 属性: 331
  - `View` 的 `style` 属性: 339, 391
  - 样式资源: 88, 331
- 时间不显示 (no time display): 298
- 留在屏幕上 (stay on screen): 216
- 类型 (types): 339
- 不区分大小写 (case-insensitive): 307
- `Collections` 类的 `sort` 方法: 307
- 音效 (sound effects): 220
- 音字段 (sound fields): 223
  - `load` 方法: 241
  - `play` 方法: 241
  - `release` 方法: 250
- `SoundPool.Builder` 类: 240
- 声音 (sounds): 220
- 源代码 (source code): 2
- 源代码 (source_coding): 319
- 布局无关像素 (sp, scale-independent pixels): 56
- 结构化查询语言 (SQL): 329
- SQLite: 152, 329
- `SQLiteDatabase` 类: 329
  - `delete` 方法: 354
  - `execSQL` 方法: 345
  - `insert` 方法: 351
  - `update` 方法: 352
- 支持库 (support library)
  - FragmentManager 114
- `SurfaceHolder` 类: 221
  - `addCallback` 方法: 240
- `SurfaceHolder.Callback` 接口
  - `surfaceChanged` 方法: 250
  - `surfaceCreated` 方法: 250
  - `surfaceDestroyed` 方法: 250
- `SurfaceView` 类: 221, 240
- `synchronized` 253
- 系统栏 (system bars): 37, 254

## T
- `Text-to-Speech` API: 9
- `TextView`
  - `gravity` 属性: 53, 88
  - `hint` 属性: 86
  - `text` 属性: 53, 55, 134
  - `textAppearance` 属性: 84
  - `textColor` 属性: 58
  - `textSize` 属性: 56, 136
  - `textStyle` 属性: 136
- `TextView` 类: 38, 54, 78
- `TextWatcher` 接口: 79, 93
  - `onTextChanged` 方法: 79
- 主题 (themes)
- 应用的唯一标识符 (unique identifier of app): 40
- `SensorManager` 的 `unregisterListener` 方法: 191
- `ContentProvider` 类的 `update` 方法: 352
- `ContentResolver` 类的 `update` 方法: 374
- `SQLiteDatabase` 类的 `update` 方法: 352
- URI (统一资源标识符): 311
- URL (统一资源定位符): 311, 346
- `Theme Editor`: 80
- `Theme.AppCompat.Light.DarkActionBar`: 79, 88
- `Thread` 类: 252
- `ToggleButton`: 217
- `Toast` 类的 `makeText` 方法: 147
- 工具 (tools): 106
- 布局编辑器 (layout editor): 621
- 触摸事件 (touch events): 175, 200
- 简单触摸 (simple touch): 220
- 跟踪应用 (track app): 398
- `Uri` 类: 311, 330
  - `getLastPathSegment` 方法: 349
  - `parse` 方法: 311
- URL 编码字符串: 311
- 单位 (units): 83
- 平移动画 (translate animation): 128
  - `android:fromDelta` 属性: 129
  - `android:startOffset` 属性: 129
  - `android:toDelta` 属性: 125, 129

## V
- Android 的 `values` 文件夹: 47, 55
- 矢量资源 (vector assets): 8, 127
- 列表项 (table): 8
- `TalkBack`: 38, 66, 135
  - `enable` 66
  - 本地化 (localization) 71
- 温度传感器 (temperature sensor): 174
- 文本框 (text box): 78
- `View` 的 `text` 属性: 53, 55
- 布局编辑器中的标签 (tabs in layout editor): 37
- `View` 的 `textAppearance` 属性: 84
- `Button` 的 `textColor` 属性: 137
- `View` 的 `textColor` 属性: 58
- `View` 的 `textSize` 属性: 56, 136
- `View` 的 `textStyle` 属性: 136
- 添加矢量资源到项目: 127
- `Vector Asset Studio`: 113, 127, 178
- 应用版本号 (version code): 387
- `VERSION_SDK_INT`: 253
- 给应用设置版本 (versioning your app): 386
- `Versioning Your Applications`: 387
- 视图 (views)
  - `view`: 15, 76
  - GUI 组件: 37
  - 视图动画 (view animations): 128
  - `ImageView`: 38, 49, 60
  - `TextView`: 38, 49, 54
- `View` 类: 210, 221
  - `ContentDescription` 属性: 135
  - 自定义子类 (custom subclass): 237
  - `getTag` 方法: 264
  - `invalidate` 方法: 200
  - `layout:gravity` 属性: 134
  - `layout:weight` 属性: 134
  - `onDraw` 方法: 231
  - `onSizeChanged` 方法: 200, 241
  - `onTouchEvent` 方法: 175, 202, 220, 251
  - 重绘视图 (redraw a View): 201
  - `requestFocus` 方法: 208
  - `setImageBitmap` 方法: 214
  - `setVisibility` 方法: 253
  - `setTag` 方法: 264
  - 尺寸变化 (size changes): 241
  - `startAnimation` 方法: 117
- `View.OnClickListener` 接口: 151
- `View.OnLongClickListener` 接口: 311
- `View.SYSTEM_UI_FLAG_IMMERSIVE` 254
- `ViewAnimationUtils` 类: 118
  - `createCircularReveal` 方法: 118, 157
  - `setDuration` 方法: 157
- `ViewGroup` 类: 338
- 视图持有者模式 (view-holder pattern): 264, 297
- 视频分享 (video sharing): 400
- 病毒式传播 (viral): 399, 400
- 查看视频 (view video): 400
- 虚拟摄像机操作员 (virtual camera operator): 29
- 虚拟商品 (virtual goods): 393
- 虚拟键盘模式: `stateExpanded` 298
- 视觉障碍 (visual impairment): 36
- 语音交互 API (Voice Interaction API): 13
- 音量 (volume): 221

## W
- `LinearLayout` 的 `weightSum` 属性: 336
- 欢迎应用 (Welcome app): 17
- Android Studio 中的欢迎窗口 (Welcome window): 39
- 小部件 (widgets): 16, 94
- 列宽属性 (column width): 81
- Wi-Fi Direct: 9
- URI 中的通配符 (wildcards in uri): 347
- Windows: 16
- `windowInputMode` 位置
- `www.deitel.com/training` 404
- WeatherBug: 6
- 网络服务 (web service): 259
  - API 密钥 (API key): 260
  - 主机 (host): 259
  - REST: 260
- 网络服务 (web services)
  - Amazon eCommerce 6
  - eBay 6
  - Facebook 6
  - Flickr 6
  - Foursquare 6
  - Google Maps 6
  - Instagram 6
  - LinkedIn 6
  - Microsoft Bing 6
  - Netflix 6
  - PayPal 6
  - Salesforce.com 6
  - Skype 6
  - Twitter 6
  - Wikipedia 6
  - Yahoo Search 6
  - YouTube 6
  - Zillow 6

## X
- XML 49
- Android 项目中的 `xml` 文件夹: 46, 115, 116
- XML 命名空间 `android`: 179
- XML 命名空间 `app`: 179
- XML 资源文件: 38
- XML 工具类: 16

## Y
- YouTube 300

## 加入 INFORMIT 联盟营销团队！

你喜欢我们的书，并喜欢与同事和朋友分享它们……为什么不在过程中顺便赚点钱呢！

如果你有网站、博客，甚至是 Facebook 页面，你可以在页面上放置 InformIT 链接来开始赚钱。

每当访问者点击这些链接并在 `informit.com` 上进行购买时，你就能获得所有销售额的佣金*！

每一笔带到我们网站的销售都能为你赚取佣金。你只需要发布你想要的标题链接，数量多少都可以，剩下的交给我们处理。

### 申请并开始！

申请非常快速快捷。

要了解更多信息请访问：

```
http://www.informit.com/affiliates/
```

* 适用于 `www.informit.com` 的所有书籍、电子书和视频销售
