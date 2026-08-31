
# Android Studio Ladybug 核心指南：Java 版——使用 Android Studio Ladybug 特性和 Java 开发 Android 应用

![](img/cover.jpeg)

Android Studio Ladybug 基础 - Java 版

## 18.12 转换视图

## 19.3 配置组件尺寸

## 20.10 对向约束与偏置的重要性

## 22. Android Studio 布局教程

### 24.4.7 复制并应用约束集

## 24.5 总结

### 28.6 事件监听器与回调方法

## 29.9 总结

### 31.2 `GestureOverlayView` 类

### 34.8 Android 生命周期 (Android Lifecycles)

## 35.10 总结

### 38.3 添加布局

### 39.4 在 `ViewModelDemo` 项目中添加状态保存支持

### 42.6 传递参数

## 44.2 `MotionLayout`

## 44.13 总结

## 46. MotionLayout 关键循环（KeyCycle）教程

## 47.2 库

## 48.4 创建第一个 Fragment

## 51. 布局编辑器示例数据教程

## 53 Android 服务概览

## 54.2 显式 Intent (Explicit Intents)

## 55.4 设计 `SecondActivity` 的用户界面布局

## 56.3 创建隐式 Intent

## 57.1 广播 Intent 概览

## 58 Android 本地绑定服务 – 实例教程

## 60.1 主线程

## 61.6 测试权限应用

## 62.11 总结

## 64.12 总结

### 65.9.2 `SQLiteDatabase`

## 66.6 添加 `Handler` 方法

### 67.2.3 `insert()`

## 68.4 构建 Authority 和内容 URI

## 68.12 修改数据库处理器 (Database Handler)

## 70.1 重新审现代应用架构

## 70.9 总结

## 72 Android Room 数据库与仓库教程

## 72.13 初始化 `RecyclerView`

## 73.8 生成测试 APK 文件

## 74.4 连接到 Google Play 结算库

## 75.14 测试应用

## 77.6 修改详情面板

## 78.6 添加 Toast 方法

## 79.6 向文件写入内容

## 80.8 测试存储访问应用

## 84.2 使用 `MediaRecorder` 类录制音频和视频

## 85. 在 Android Studio 中使用 Google Maps Android API

## 85.13 更改地图类型

## 86.1 Android 打印架构

## 87. 一个 Android HTML 和 Web 内容打印示例

## 4.7 移除设备外

## 90.9 测试应用链接

## 93.2.5 APK 签名

## 4.8 总结

### 5.5.6 电话

### 5.9 常用 Android 设置

### 6.9 总结

## 11. Android 应用结构

## 14.4 Android 生命周期方法

## 17. 理解 Android Views、View Groups 和布局

## 18.4 调色板 (Palette)

## 18.17 总结

## 20.4 手动操作约束

## 20.11 配置组件尺寸

## 21.3 内部展开链样式 (Spread Inside)

## 22.6 使用布局检查器 (Layout Inspector)

## 24.5 总结

### 28.5 设计用户界面

## 31. 在 Android 上实现自定义手势和缩放识别

### 33.7 让 Toolbar Fragment 与 Activity 通信

## 34.7 `LiveData` 与 Data Binding

## 35.7 修改 Fragment

## 48.10 自定义 TabLayout

## 54.6 自动链接验证

## 59. Android 远程绑定服务——详解

## 70.5 Room Database

```
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

## 15.4 过滤 Logcat 面板

在`MainActivity.java`的重写方法中添加代码的是将日志信息输出到`Logcat`工具窗口，该窗口通过图 15-4 所示的按钮显示：

![image-LR8I7L64.jpg](img/image-LR8I7L64.jpeg)
图 15-4

`Logcat`工具窗口可以配置为显示与设备或模拟器会话的所有事件，或限制为与当前选择的应用程序相关的事件。输出也可以限制为仅匹配特定过滤器的日志事件。

当在当前应用运行时显示时，`Logcat`工具窗口将如图 15-5 所示：

![image-SDF7PAYZ.jpg](img/image-SDF7PAYZ.jpeg)
图 15-5

标记为 A 的菜单允许您选择显示输出的设备或模拟器。标记为 C 的面板显示输出。可以通过在标记为 B 的字段中输入选项进行过滤。默认设置`package:mine`将输出限制为当前应用（在本例中为`.ebookfrenzy.statechange`）。留空此字段将显示来自操作系统的日志。键也可以组合以进一步过滤。例如，我们可以通过在键前加减号 (-)来排除输出。除了`StateChange`标签外，我们可能还有另一个标签的诊断消息。为了过滤掉第二个标签的输出，我们可以输入以下键：`package:mine tag:StateChange -tag:OtherTag`

除了自定义标签值，还可以从 Android 内置标签范围内进行选择。当您在过滤器中输入时，`Logcat`将显示匹配的标签，如图 15-6 所示：

![image-H95JBM7S.jpg](img/image-H95JBM7S.jpeg)
图 15-6

或者，使用`Ctrl-Space`获取完整的过滤建议。

`level`密钥可以根据严重性控制显示的消息。要过滤掉错误消息以外的所有消息，可以使用以下密钥：`level:error`

除了`error`之外，`Logcat`面板支持`verbose`、`info`、`warn`和`assert`级别设置。

`Logcat`还支持多个日志面板，每个面板都有自己的过滤设置。要添加另一个面板，点击图 15-5 中标记为 D 的`+`按钮。使用相应的标签切换不同的面板，或通过右键点击当前显示的面板并选择`Split-Right`或`Split-Down`选项水平或垂直排列面板。要重命名面板，右键点击标签并选择`Rename Tab`选项。在继续之前，关闭除一个以外的所有`Logcat`面板并按如下配置：`package:mine tag:StateChange`

## 15.5 运行应用程序

为了获得最佳，应在物理 Android 设备或模拟器上运行应用程序。在设备配置并连接到开发计算机后，点击 Android Studio 工具栏上的运行按钮，如下图 15-7 所示：

![image-DW8O46WS.jpg](img/image-DW8O46WS.jpeg)
图 15-7

如果出现了“选择设备”对话框，请从中选择物理 Android 设备或手机模拟器（假设你尚未将其配置为默认目标）。在 Android Studio 构建应用程序并将其安装到设备上后，程序将会启动并在前台运行。

查看`Logcat`面板可以指示出目前为止已经触发了哪些方法：

![image-049ONSNQ.jpg](img/image-049ONSNQ.jpeg)
图 15-8

## 15.6 对 Activity 进行实验

既然诊断功能已正常工作，现在是时候运行应用程序以理解 Activity 的生命周期状态变化了。首先，考虑`Logcat`面板中初始的日志事件序列：

```
onCreate

onStart

onResume
```

显然，初始状态更改与“理解 Android 应用程序和 Activity 生命周期”中所概述的完全一致。但请注意，此时并没有调用`onRestoreInstanceState()`，因为 Android 运行时检测到在这种情况下没有需要恢复的状态。

点击设备显示屏底部状态栏上的主页图标，并注意日志中报告的方法调用序列如下所示：

```
onPause

onStop

onSaveInstanceState
```

在这种情况下，运行时注意到 Activity 不再处于前台，对用户不可见，并已停止该 Activity，但它并没有给 Activity 提供保存动态状态的机会。取决于运行时最终销毁了 Activity 还是重启了它，Activity 将会通过调用`onRestart()`被通知其已重启，或者当用户返回 Activity 时将再次经历创建序列。

正如“理解 Android 应用程序和 Activity 生命周期”概述的，Activity 的销毁和重建可以通过对设备进行配置更改来触发，例如从竖屏旋转到横屏。要看到这一操作过程，请在`StateChange`应用程序处于前台时旋转设备。使用模拟器时，可以使用模拟器工具栏上的旋转按钮模拟设备旋转。为了完成旋转，可能还需要点击旋转按钮。该按钮出现在设备或模拟器屏幕的底部，如图 15-9 所示：

![image-MZNW8BVQ.jpg](img/image-MZNW8BVQ.jpeg)
图 15-9

日志中生成的方法调用序列应如下：

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

显然，运行时系统允许 Activity 在被销毁和重启之前保存了状态。

## 15.7 总结

俗语“一画胜千千言”在学习新编程范式的示例中也同样适用。在本章中，我们创建了一个 Android 示例应用程序，以演示 Activity 可能会经历的不同生命周期状态。在在本章开发项目期间，我们还查看了从 Activity 内部生成诊断日志信息的机制。

在下一章中，我们将扩展`StateChange`示例项目，演示如何保存和恢复 Activity 的动态状态。

## 16. 保存和恢复 Android Activity 的状态

如果前面的几章已经实现了目标，那么现在对于在 Activity 生命周期内的特定点保存和恢复用户界面状态的重要性应该变得更加清晰了。

在本章中，我们将扩展在“通过示例 Android Activity 状态更改”中创建的示例应用程序，以演示运行时系统销毁和重建 Activity 时涉及保存和恢复状态的步骤。

保存和恢复动态状态的关键组件涉及使用 Android SDK 中的`Bundle`类，该主题在本章中也会涵盖。

## 16.1 保存动态状态

正如我们所学到的，Activity 可以通过运行时调用 Activity 对`onSaveInstanceState()`方法的实现来保存动态状态信息。传递给方法的参数是一个`Bundle`对象的引用，该方法必须将任何需要保存的动态数据存储其中。随后，`Bundle`对象由运行时代表 Activity 进行存储，并在后续调用 Activity 的`onCreate()`和`onRestoreInstanceState()`方法时作为参数传递给这些方法。然后可以在这些方法内部从`Bundle`对象中检索数据，并用于恢复 Activity 的状态。

## 16.2 用户界面状态的默认保存

在上一章中，`StateChange`示例应用程序的诊断输出显示，当运行它的设备旋转足够大以触发方向更改时，Activity 会经历几次状态变化。

再次启动`StateChange`应用程序，并在执行设备旋转之前向`EditText`字段输入一些文本（在运行 Android 9 或更高版本的设备或模拟器上，可能需要点击状态栏中的旋转按钮来完成旋转）。旋转设备后，`Logcat`窗口中应出现的状态变化序列：

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

显然，这导致了 Activity 的销毁和重建。然而，查看运行中应用程序的用户界面应该显示输入到`EditText`字段中的文本已被保留。鉴于 Activity 已被销毁并重建，且我们没有添加任何特定代码来确保文本被保存和恢复，这种行为需要一些解释。

事实上，Android SDK 包含的大多数视图控件已经实现了当 Activity 自动重启时保存和恢复状态所需的行为。启用此种行为的唯一要求是 Activity 中的重写方法`onSaveInstanceState()`和`onRestoreInstanceState()`必须包含对父类等效方法的调用：

```java
@Override

protected void onSaveInstanceState(@NonNull outState) {

    super.onSaveInstanceState(outState);

}

@Override

protected void onRestoreInstanceState(@NonNull savedInstanceState) {

    super.onRestoreInstanceState(savedInstanceState);

}
```

可以通过在 XML 布局文件中将`saveEnabled`属性设置为 false 来禁用用户界面视图的自动保存。在本示例中，我们将在用户界面布局中禁用`EditText`视图的自动保存机制，然后在应用程序中添加代码手动保存和恢复视图的状态。

更改后，运行应用程序，输入文本并旋转设备，以验证文本不再被保存和恢复。

要配置`EditText`视图以使得……编辑`activity_main.xml`文件使该视图的条目如下（注意正如“在 Android Studio 中创建示例 Android 应用”中所概述，可以通过将布局编辑器切换到代码视图来编辑 XML）：

```xml
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



对于需要在用户界面视图组件提供的默认功能之外保存状态的情况，`Bundle` 类提供了一个使用键值对机制来存储数据的容器。键的形式为字符串值，而与这些键关联的值可以是原始值，也可以是实现了 Android `Parcelable` 接口的任何对象。许多类已经实现了 `Parcelable` 接口。通过实现 `Parcelable` 接口中定义的 set 方法，可以将自定义类转变为“可序列化的（parcelable）”，具体细节可以在 Android 文档中找到：`https://developer.android.com/reference/android/os/Parcelable.html`

`Bundle` 类还包含一组方法，可用于获取和设置各种数据类型的键值对，包括原始类型（包括 `Boolean`、`char`、`double` 和 `float` 值）和对象（如 `Strings` 和 `CharSequenceences`）。

在本例中，由于已经禁用了 `EditText` 视图的文本自动保存功能，我们需要确保用户输入 `EditText` 字段的文本被保存到 `Bundle` 对象中并在随后恢复。这将展示如何在 Android 应用程序中手动保存保存和恢复状态，并将分别使用 `Bundle` 类的 `putCharSequence()` 和 `getCharSequence()` 方法实现。

## 16.4 保存状态

扩展 StateChange 应用程序的第一步是确保用户输入的文本在 `MainActivity` 类的 `onSaveInstanceState()` 方法中从 `EditText` 组件中提取出来，然后以键值对的形式保存到 `Bundle` 对象中。

要从 `EditText` 对象中提取文本，我们必须首先在用户界面中标识该对象。显然，这涉及在 Activity 的 Java 代码（包含在 `MainActivity.java` 源代码文件中）与用户界面的 XML 表示（包含在 `activity_main.xml` 资源文件中）之间建立桥梁。为了提取输入 `EditText` 组件的文本，我们需要获取该用户界面对象的访问权限。

用户界面中的每个组件都关联有一个唯一的标识符。默认情况下，布局编辑器（Layout Editor）工具根据对象类型为新添加的组件构建 `id`。如果布局中包含多个相同类型的视图，则在类型名称后面会跟上一个顺序数字（尽管开发者也可以也应该将其更改更具意义的内容）。通过在 Android Studio 主窗口中选择 `activity_main.xml` 文件并显示布局编辑器工具时，检查组件树（Component Tree）面板可以看到，`EditText` 组件已被分配了 `id` `editText`：

![image-BBAGX0S7.jpg](img/image-BBAGX0S7.jpeg)

图 16-1

我们现在可以通过对象的 `getText()` 方法获取 `editText` 视图包含的文本，该方法反过来返回当前文本：

```java
CharSequence userText = binding.editText.getText();
```

最后，我们可以使用 `Bundle` 对象的 `putCharSequence()` 方法保存文本，将键（这可以是任何字符串值，在本例中，我们将它声明为“savedText”）和 `userText` 对象作为参数传递：

```java
outState.putCharSequence("savedText", userText);
```

将这一切整合在一起，我们在 `MainActivity.java` 文件中得到了一个修改后的 `onSaveInstanceState()` 方法，内容如下：

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

.
```

现在已经采取了保存状态的步骤，下一阶段是在需要时恢复它。

## 16.5 恢复状态

保存的动态状态可以在那些将 `Bundle` 对象作为参数传递的周期方法方法恢复。这让开发者可以选择 `onCreate()` 或 `onRestoreInstanceState()`。使用哪种方法取决于 Activity 的性质。在 Activity 初始化任务完成后最适合恢复状态的情况下，通常 `onRestoreInstanceState()` 方法更合适。在本例中，我们将向 `onRestoreInstanceState()` 方法中添加代码，使用“savedText”键从 `Bundle` 中提取保存的状态。然后，我们可以使用对象的 `setText()` 方法在 `editText` 组件上显示文本：

```java
@Override

protected void onRestoreInstanceState(@NonNull Bundle savedInstanceState) {

    super.onRestoreInstanceState(savedInstanceState);

    Log.i(TAG, "onRestoreInstanceState");

    CharSequence userText = savedInstanceState.getCharSequence("savedText");

    binding.editText.setText(userText);

}
```



## 16.6 测试应用程序

剩下的工作只是再次构建并运行 `StateChange` 应用程序。一旦运行并处于前台，触摸 `EditText` 组件并在旋转设备到另一个方向之前输入一些文本。以前文本更改会丢失，但得益于我们在本章中为 `Activity` 添加的代码，新文本保留在 `editText` 组件中。

在验证代码执行符合预期后，注释掉这两个方法中的 `super.onSaveInstanceState()` 和 `super.onRestoreInstanceState()` 调用，重新启动应用并注意在设备旋转后文本仍然被保留。默认的保存和恢复系统已通过自定义实现所取代，从而提供了在 `Activity` 中动态和选择性保存状态的方法。

## 16.7 总结

Android 应用程序中状态的保存和恢复需要在适当的方法中实现。对于大多数用户界面，这由 `Activity` 基类处理。在其他情况下，这通常包括在 `onSaveInstanceState()` 方法中提取值并以键值对的形式保存到传递给 `Activity` 的 `Bundle` 对象中。可以通过 `onCreate()` 或 `onRestoreInstanceState()` 方法从 `Bundle` 对象中提取值来恢复状态。

在本章中，我们使用这些技术更新了 `StateChange` 项目，使 `Activity` 能够在销毁和随后的重建后保留更改。

## 17. 理解 Android 用户界面结构

除了听流媒体外，用户与 Android 设备的交互主要是视觉和触觉的。所有这些交互都发生在安装在设备上的应用程序界面中，包括内置应用程序和用户安装的任何第三方应用程序。因此，开发 Android 应用的关键要素涉及设计和创建用户界面这并不意外。

本章涵盖了 Android 用户界面结构，包括组成用户界面的元素概述：视图（Views）、视图组（View Groups）和布局（Layouts）。

### 17.1 为不同的 Android 设备设计

“Android 设备”涵盖了许多具有不同屏幕尺寸和分辨率的平板电脑和平手机。因此，应用程序用户界面现在必须仔细设计，以确保在尽可能广泛的尺寸上正确显示。其中的关键部分是确保用户界面布局在不同设备上运行时能够正确调整大小。这在很大程度上可以通过仔细规划和使用本章概述的布局管理器来实现。

同样重要的是，大多数基于 Android 的智能手机和平电脑都可以由用户以竖屏或横屏模式持有。良好的用户界面应该能够适应这些变化，并进行合理的布局调整，以利用每个方向下的可用屏幕空间。

### 17.2 视图（Views）与视图组（View Groups）

用户界面中的每个项目都是 Android `View` 子类（准确来说是 `android.view.View`）。Android SDK 提供了一组预定义的视图，用于构建用户界面。典型示例包括标准项，如 `Button`、`CheckBox`、`ProgressBar` 和 `TextView` 类。这些视图也被称为控件（widgets）或组件（components）。对于 SDK 提供的控件无法满足的需求，可以通过子类和扩展现有类来创建新视图，或者通过直接在 `View` 类之上构建创建一个全新的组件。

视图还可以包含多个其他视图（也称为复合视图，composite view）。此类视图派自 Android `ViewGroup` 类（`android.view.ViewGroup`），而 `ViewGroup` 本身又是 `View` 的子类。这种视图的一个示例是 `RadioGroup`，它旨在包含多个 `RadioButton` 对象，使得在任何时刻只有一个对象处于“开启”状态。在结构方面，复合视图由单个父视图（派生自 `ViewGroup` 类，其他称为容器视图或根元素）组成，该父视图能够包含其他视图（称为子视图）。

另一类基于 `ViewGroup` 的容器视图是布局管理器（layout manager）。

### 17.3 Android 布局管理器

除了上一节讨论的控件式视图外，SDK 还包含一组被称为布局（layouts）的视图。布局是容器视图（因此派自 `ViewGroup`），设计用于控制子视图在屏幕上的对齐方式。

Android SDK 包含了以下布局视图，它们可以用于 Android 用户界面的设计中：

- `ConstraintLayout` – 在 Android 7 中引入，该布局管理器被推荐用于大多数布局需求。`ConstraintLayout` 允许通过分配给每个子视图的简单约束设置，定义布局中视图的位置和行为。这种布局的灵活性允许快速、方便地创建复杂布局，而无需在内部嵌套其他布局类型，从而提升了布局性能。`ConstraintLayout` 也紧密集成到 Android Studio 布局编辑器工具中。除非另有说明，它是书中大多数示例的首选布局。
- `LinearLayout` – 根据所选的方向将子视图放置在单行或单列中。可以在每个子视图上设置权重（weight）值，以指定该视图相对于其他子视图占据布局空间的比例。
- `TableLayout` – 将子视图以行列的网格格式排列。表格中的每一行由一个 `TableRow` 对象子表示，而该对象又包含每个单元格的视图对象。
- `FrameLayout` – `FrameLayout` 的作用是分配屏幕区域，通常用于显示单个视图。如果添加了多个子视图，它们默认将相互堆叠，并定位在布局区域的左上角。通过为每个子视图设置重力（gravity）值，可以实现单个子视图的定位。例如，在子视图上设置 `center_vertical` 重力值将使其位于包含容器 `FrameLayout` 视图的垂直中心。
- `RelativeLayout` – `RelativeLayout` 允许通过指定子视图的对齐和边距，将子视图相对于彼此以及容器布局视图进行定位。例如，子视图 A 可以被配置为位于容器 `RelativeLayout` 视图的水平垂直中心。而视图 B 可能也可以被配置为在布局中水平居中，但位于视图 A 顶部边缘上方 30 像素处，从而产生相对于视图 A 的垂直位置。在设计必须在各种屏幕尺寸和方向上运行的用户界面时，`RelativeLayout` 管理器非常有帮助。
- `AbsoluteLayout` – 允许将子视图位于容器布局视图内特定的 `X` 和 `Y` 坐标上。不建议使用这种布局，因为它缺乏响应屏幕尺寸和方向变化的灵活性。
- `GridLayout` – `GridLayout` 实例由不可见的线划分，形成一个包含行和列单元格的网格。子视图被放置在单元格中，并可以配置为水平和垂直跨越多个单元格，允许快速方便地实现广泛的布局选项。`GridLayout` 中组件之间的间隙可以通过在相邻单元格中放置一种称为 `Space` 的特殊类型视图或设置边距参数来实现。
- `CoordinatorLayout` – 作为 Android Design Support Library 随 Android 5.0 引入，`CoordinatorLayout` 专门用于协调应用程序屏幕顶部标题栏（app bar）与其他视图元素的显示效果和行为。当使用 `Basic Views Activity` 模板创建新活动时，主布局中的父视图将使用 `CoordinatorLayout` 实例实现。该布局管理器将在“使用悬操作按钮和 Snackbar”章节中进行更详细的介绍。

在考虑 Android 应用程序的用户界面布局时，值得记住，正如下一节所述，这些布局可以相互嵌套，以创建几乎任何所需复杂程度的用户界面设计。

### 17.4 视图层次结构（View Hierarchy）

用户界面中的每个视图都代表显示器上的矩形区域。视图负责在该矩形内绘制内容，并响应屏幕该部分的事件（例如触摸事件）。

用户界面屏幕由一个视图层次结构组成，根视图位于树的顶部，子视图位于下方的分支上。容器视图的子视图显示在其父视图之上，并限制在父视图显示区域的边界内。例如，考虑图 17-1 所示的用户界面：

随着对视图（views）、布局（layouts）和视图层次结构（view hierarchy）概念的进一步理解，接下来的几章将重点介绍为 Android `Activity` 创建用户界面的步骤。事实上，用户界面设计有不同的方法：使用 Android Studio 布局编辑器工具、手动编写 XML 布局资源文件或编写 Java 代码，这三种方法都将涵盖涵盖。

### 17.6 总结

Android 应用用户界面屏幕中的每个元素都是 `view`，它们最终派自 `android.view.View` 类。每个视图代表设备显示器上的矩形区域，负责显示该矩形区域内的内容并处理发生在视图边界范围内的事件。多个视图可以组合成单个的复合视图（composite view）。复合视图中的视图是容器视图的子视图，容器视图通常是 `android.view.ViewGroup` 的子类（`ViewGroup` 又是 `android.view.View` 的子类）。用户界面是由视图层次结构形式构建的视图组成的。

Android SDK 包含了一系列预构建视图，可用于创建用户界面。这些包括文本字段和按钮等基本组件，以及一系列可用于控制子视图定位的布局管理器。如果提供的视图不能满足特定需求，可以通过扩展或组合现有视图来创建自定义视图，或者通过派生 `android.view.View` 并创建一个全新的视图类来创建。

用户界面可以使用 Android Studio 布局编辑器工具、手动编写 XML 布局资源文件或编写 Java 代码来创建。这些方法中的每一种将在后续章节中介绍。

## 18. Android Studio 布局编辑器工具指南

要想出一个不需要某种形式用户界面的 Android 应用概念是挑战性的。大多数 Android 设备都配备了触摸屏和键盘（虚拟或物理键盘），点击和滑动是用户与应用程序之间主要的交互方式。这些交互不可避免地通过应用程序的用户界面进行。

设计良好且实现的用户界面是创建一个成功且流行的 Android 应用的关键因素，根据单个应用程序的设计需求，其复杂度从简单到非常复杂不等。无论复杂程度如何，Android Studio 布局编辑器工具都显著简化了设计和实现 Android 用户界面的任务。

### 18.1 基础视图 Activity 与空视图 Activity 模板

正如名为“Android 应用剖析”的章节中所概述的那样，Android 应用包含一个或多个 `Activity`。`Activity` 是应用程序功能的独立模块，通常直接对应于单个用户界面屏幕。因此，在使用 Android Studio 布局编辑器时，我们始终在为 `Activity` 编写布局。

在创建新的 Android Studio 项目时，有多个模板可以作为主 `Activity` 用户界面的起点。最基础的模板是 `Basic Views Activity` 模板和 `Empty Views Activity` 模板。尽管它们乍看起来相似，但这两个选项之间存在显著差异。要在布局编辑器中查看这些差异，请使用视图选项（View Options）菜单启用显示系统 UI（Show System UI），如下图 18-1 所示：

![image-1CELKKI5.jpg](img/image-1CELKKI5.jpeg)

图 18-1

`Empty Views Activity` 模板创建一个单一布局文件，该文件由包含一个 `TextView` 对象的 `ConstraintLayout` 管理器实例组成，如图 18-2 所示：

![image-W29IKLZC.jpg](img/image-W29IKLZC.jpeg)

图 18-2

另一方面，`Basic Views Activity` 包含多个布局文件。顶层布局文件具有 `CoordinatorLayout` 作为根视图，一个可配置的标题栏（包含一个 `toolbar`）显示在设备屏幕顶部（图 18-3 中的标记 A 所示），以及一个浮动操作按钮（标记 B 的电子邮件按钮）。除了这些项目，`activity_main.xml` 布局文件还包含名为 `content_main.xml` 的第二个文件的引用，该文件包含内容布局（标记 C）：

![image-WQ432AD8.jpg](img/image-WQ432AD8.jpeg)

图 18-3

`Basic Views Activity` 包含两个屏幕的布局，包含一个按钮和一个文本视图。此模板旨在演示如何在应用中的多个屏幕之间实现导航。如果运行使用 `Basic Views Activity` 模板的未修改应用，将出现这两个屏幕中的第一个（如图 18-4 中的标记 A 所示）。点击 Next（下一步）按钮将导航到第二个屏幕（B），该屏幕又包含一个返回第一个屏幕的按钮：

![image-HRR3YZ15.jpg](img/image-HRR3YZ15.jpeg)

图 18-4

此应用行为使用了称为片段（fragments）和导航（navigation）的 Android 功能，将分别从名为“Android Fragment 简介”和“导航架构组件概览”的章节开始介绍。

`content_main.xml` 文件包含一个特殊的片段，称为“导航主机片段”（Navigation Host Fragment），它允许根据 `res -> layout -> nav_graph.xml` 文件中的设置在视图中切换不同的内容。在 `Basic Views Activity` 模板的情况下，`nav_graph.xml` 文件配置为根据用户选择 Next 和 Previous 按钮，在 `fragment_first.xml` 和 `fragment_second.xml` 文件中定义的用户界面布局之间进行切换。

如果你在 `Activity` 中既不需要浮动操作按钮也不需要菜单，不需要 `CoordinatorLayout` 提供的特殊标题栏行为（例如在某些滚动操作期间使标题栏和工具栏折，该主题将在“使用标题栏和折叠工具栏”章节介绍），那么 `Empty Views Activity` 模板非常有帮助。然而，`Basic Views Activity` 因为默认提供了这些元素非常有帮助。事实上，使用 `Basic Views Activity` 模板创建一个新 `Activity` 并删除不需要的元素，比使用 `Empty Views Activity` 模板并手动实现行为要快得多。

由于书中并非所有示例都需要 `Basic Views Activity` 模板的功能，因此本章的大多数示例将使用 `Empty Views Activity` 模板，除非示例需要 `Basic Views Activity` 模板提供的一个或其他功能。

为了以后参考，如果你需要菜单但不需要浮动操作按钮，请使用 `Basic Activity` 并按照以下步骤删除浮动操作按钮：

1. 在项目窗口的 `app -> res -> layout` 下双击 `activity_main.xml` 布局文件，将其加载到布局编辑器。将布局加载到布局编辑器后，选择浮动操作按钮并按键盘 Delete 键从布局中删除对象。

2. 找到并编辑 `Activity` 的 Java 代码（位于 `app -> java ->`），如下所示从 `onCreate` 方法中删除浮动操作按钮代码：

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

    NavigationUI.setupActionBarWithNavController(
        this,
        navController,
        appBarConfiguration
    );

    binding.fab.setOnClickListener(new View.OnClickListener() {
        @Override
```

```java
public void onClick(View view) {
    Snackbar.make(
        view,
        "Replace with your own action",
        Snackbar.LENGTH_LONG
    ).setAction("Action", null).show();
}
});
```



如果你需要悬浮操作按钮但不需要菜单，请使用 `Basic Views Activity` 模板并按照以下步骤操作：

1. 编辑主类文件并删除 `onCreateOptionsMenu` 和 `onOptionsItemSelected` 方法。
2. 在 `Project` 工具窗口中选择 `res -> menu` 项，并按键盘 `Delete` 键从项目中删除该文件夹和相应的菜单资源文件。

如果你需要使用 `Basic Views Activity` 模板，但既不需要导航功能也不需要第二个内容碎片，请以下步骤操作：

1. 在 `Project` 工具窗口中，导航并双击 `app -> res -> navigation -> nav_graph.xml` 文件，将其加载到导航编辑器中。
2. 在编辑器中，选择图面板中的 `SecondFragment` 条目，并按键盘删除键将其从图中移除。
3. 找到并删除 `SecondFragment.java`（`app -> java -> -> SecondFragment`）和 `fragment_second.xml`（`app -> res -> layout -> fragment_second.xml`）文件。
4. 最后的任务是从 `FirstFragment` 类中删除一些代码，以便 `Button` 视图在点击时不再导航到已不存在的第二个碎片。找到 `FirstFragment.java` 文件，双击将其加载到编辑器中，并移除 `onViewCreated()` 方法中的代码，使其如下：

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

## 18.2 Android Studio 布局编辑器

如前面的章节所示，布局编辑器工具提供了一个“所见即所得”（WYSIWYG）的环境，在该环境中，可以从调板中选择视图，然后将其放置在代表 Android 设备显示的画布上。视图一旦放置在画布上，就可以对其进行移动、删除和调整大小（受父视图限制限制）。此外，可以使用属性（`Attributes`）工具窗口修改与所选视图相关的属性。

在底层，布局编辑器工具构建一个包含正在设计的用户界面定义的 XML 资源文件。因此，布局编辑器工具以三种不同的模式运行：设计（`Design`）、代码（`Code`）和拆分（`Split`）。

## 18.3 设计模式

在设计模式下，可以直接操作视图调板和布局的图形表示来视觉化操作用户界面。图 18-5 显示了 Android Studio 布局编辑器在设计模式下的关键区域：

![image-HBW4D9NN.jpg](img/image-HBW4D9NN.jpeg)

图 18-5

- **A – 调板 (Palette)** – 调板提供了 Android SDK 提供的系列视图组件的访问。这些组件被分为类别，以便导航。可以通过从调板中拖拽视图组件并将其放置到布局所需的区域来向布局中添加项。
- **B – 设备屏幕 (Device Screen)** – 设备屏幕提供了设计中用户界面布局的视觉“所见即所得”表示。该布局允许通过选择、删除、移动和调整视图的大小来实现直接的设计操作。可以使用工具栏中的菜单随时更改布局代表的设备模型。
- **C – 组件树 (Component Tree)** – 如上一章（“理解 Android 视图、视图组和布局”）所述，用户界面是使用层次结构构建的。组件树提供了用户界面设计层次结构的视觉概述。从组件树中选择元素将导致布局中相应的视图被选中。同样，从设备屏幕布局中选择视图将选中组件树层次结构中的该视图。
- **D – 属性 (Attributes)** – 调板中列出的所有组件视图都有一组关联属性，用于调整该视图的行为和外观。布局编辑器的属性面板提供了布局中当前选中视图属性的访问，以便进行更改。
- **E – 工具栏 (Toolbar)** – 布局编辑器工具栏提供了各种选项的快速访问，包括但不限于缩放设备屏幕布局、更改当前显示的设备模型、在竖屏和横屏之间旋转布局，以及切换到不同的 Android SDK API 级别。工具栏还有一组上下文敏感按钮，当在设备屏幕布局中选择相关的视图类型时，这些按钮将会出现。
- **F – 模式切换控制 (Mode Switching Controls)** – 这三个按钮提供了在布局编辑器工具的设计、代码和拆分模式之间来回切换。
- **G - 缩放和平移动控制 (Zoom and Pan Controls)** – 此控制面板允许你对设计画布进行缩放、抓取并在放大时移动以寻找被遮挡的区域。

## 18.4 调板

布局编辑器调板组织为两个面板，旨在方便查找和预览用于添加到布局设计中的视图组件。类别面板（在图 18-6 中标记为 A）列出了由 Android SDK 支持的不同类别的视图组件。当从列表中选择一个类别时，第二个面板 (B) 将更新以显示属于该类的组件列表：

![image-Z9APWIMG.jpg](img/image-Z9APWIMG.jpeg)

图 18-6

要将组件从调板添加到到布局画布上，请从组件列表或预览面板中选择该项，将其拖动到所需位置并放置到位。在所选类别内搜索特定组件，可以通过点击调板工具栏上的搜索按钮（在图 18-6 中标记为 C）并输入组件名称来启动。随着字符的输入，匹配的结果将出现在组件列表中。如果你不确定组件的类别，在搜索之前或搜索期间选择“所有结果”（`All Results`）类别。

## 18.5 设计模式和布局视图

布局编辑器默认以设计模式出现，如图 18-5 所示。此模式提供了用户界面的视觉表示。可以通过点击图 18-7 中标记为 C 的按钮来选择设计模式：

![image-MGUBENV6.jpg](img/image-MGUBENV6.jpeg)

图 18-7

当布局编辑器工具处于设计模式时，可以用两种方式查看布局。图 18-5 所示的视图是设计视图，显示了布局和控件在运行程序中的外观。另一种模式是蓝图视图（`Blueprint view`），它可以替代或同时设计视图显示。图 18-8 中的工具栏菜单提供了显示设计视图、蓝图视图或两者的选项。还有针对色盲的设置。第五种选项“强制刷新布局”（`Force Refresh Layout`）会导致布局重新构建并重绘。当布局进入意外状态或未准确反映当前设计设置时，这非常有用。

显示布局视图、设计视图还是两者取决于个人喜好。一种很好的方法是像图 18-9 所示同时显示两者：

![image-VL05N59F.jpg](img/image-VL05N59F.jpeg)

图 18-9

## 18.6 夜间模式

要在设计期间以夜间模式查看布局，请选择下方图 18-10 所示的菜单并将设置为 `Night`：

![image-9TCV1KEJ.jpg](img/image-9TCV1KEJ.jpeg)

图 18-10

模式菜单还包括测试动态颜色的选项，该主题在“Material Design 3 主题和动态颜色教程”章节中有所介绍。

# 18.7 代码模式 (Code Mode)

在使用 Android Studio 布局编辑器工具时，请记住它所做的只是提供了一种易于操作的方法来创建 XML 布局资源文件。在设计过程中，可以通过选择图 18-7 中标记为 A 的按钮来查看并直接编辑底层的 XML。

图 18-11 显示了代码模式下的 Android Studio 布局编辑器，允许通过修改 XML 来更改用户界面声明：

![image-PERE2GM0.jpg](img/image-PERE2GM0.jpeg)

图 18-11

## 18.8 分屏模式 (Split Mode)

在分屏模式下，编辑器并排显示设计（`Design`）和代码（`Code`）视图，允许用户使用设计画布视觉化地修改用户界面，并直接对 XML 声明进行更改。使用图 18-7 中标记为 B 的按钮选择分屏模式。

对 XML 的任何更改都会反映在设计画布上，反之亦然。图 18-12 显示了分屏模式下的编辑器：

![image-OCID92TD.jpg](img/image-OCID92TD.jpeg)

图 18-12

## 18.9 设置属性 (Setting Attributes)

属性（`Attributes`）面板提供了当前选中组件的所有可用设置。例如，图 18-13 显示了 `TextView` 小部件的一些属性：

![image-JTN8JDE7.jpg](img/image-JTN8JDE7.jpeg)

图 18-13

属性工具窗口分为以下不同部分：

- `id`：包含 `id` 属性，定义了在应用源码中引用当前所选对象的名称。
- `已声明属性 (Declared Attributes)`：包含所有已赋值值的属性。
- `布局 (Layout)`：定义当前所选视图对象相对于屏幕及布局其他对象的定位和大小的设置。
- `变换 (Transforms)`：包含允许当前所选对象进行旋转、缩放和偏移的控件。
- `常用属性 (Common Attributes)`：当前选中视图对象类通常需要更改的属性列表。
- `所有属性 (All Attributes)`：当前所选对象所有可用属性的完整列表。

也可以通过选择属性窗口工具栏中的搜索按钮并输入属性名称来搜索特定属性。

某些属性在值字段右侧有一个窄按钮。这表示可以使用资源（`Resources`）对话框来帮助选择合适的属性值。点击该按钮可显示对话框。该按钮的外观会变化，以反映相应的属性值是存储在资源文件中还是硬编码的。如果值存储在资源文件中，`text` 属性字段右侧的按钮将填充，表示该值不是硬编码的，如下方的图 18-14 所示：

![image-LA1MYPVT.jpg](img/image-LA1MYPVT.jpeg)

图 18-14

具有有限数量有效选项的属性将显示下拉菜单（图 18-15），可以从中进行选择。

![image-16D49XT7.jpg](img/image-16D49XT7.jpeg)

图 18-15

点击下拉图标可以显示颜色选择调板。同样，当旗帜图标出现时，点击它可以显示该属性可用的选项列表；而图像图标会打开资源管理器面板，允许为属性选择图像和其他资源类型。

## 18.10 变换 (Transforms)

属性工具窗口内的变换面板（图 18-16）提供了一系列控件和属性，用于控制当前所选对象在视觉方面的方面，包括旋转、`Alpha`（alpha，用于视图淡入淡出）、缩放（大小）和平移（相对于当前位置的偏移）：

![image-89S5396X.jpg](img/image-89S5396X.jpeg)

图 18-16

面板包含视图的视觉表示，它会随着属性的更改而更新。这些更改也会反映在布局画布中的视图中。

## 18.11 工具可见性切换 (Tools Visibility Toggles)

在代码模式下查看 Android Studio XML 布局文件的内容时，你会发现许多定义视图外观和行为的属性都以 `android:` 前缀开头。这表示属性是在 `android` 命名空间内设置的，并在应用运行时生效。例如，下面这段布局文件的摘录在 `Button` 视图上设置了多种属性：

```xml
android:id="@+id/button"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="Button"
```

除了 `android` 命名空间外，Android Studio 还提供了 `tools` 命名空间。当属性在此命名空间内设置时，它们仅在布局编辑器的预览中生效。在设计布局时，你可能会发现希望 `EditText` 视图显示某些文本但在应用运行时需要视图为空。为了实现这一点，你将使用 `tools` 命名空间如下所示设置视图的 `text` 属性：

```xml
android:id="@+id/editTextTextPersonName"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:ems="10"
android:inputType="textPersonName"
tools:text="Sample Text"
```

这种类型的工具属性通过扳手图标在属性窗口中设置，如图 18-17 所示：

![image-UYXMH7.jpg](img/image-UYXMH7.jpeg)

图 18-17

具有有限数量有效选项的属性将呈现下拉菜单（图 18-15），可以从中进行选择。

点击下拉图标可以显示颜色选择调板。同样，当旗帜图标出现时，点击它可以显示该属性可用的选项列表；而图像图标会打开资源管理器面板，允许为属性选择图像和其他资源类型。

工具属性在设计过程中更改视图的可见性非常有用。布局可能包含一个在应用运行时根据用户操作显示或隐藏的视图。为了实现隐藏视图，你可以在视图上添加如下工具属性：

```xml
tools:visibility="invisible"
```

虽然在使用 `invisible` 设置时视图不再可见，但它仍然存在于布局中并占据原来的空间。为了让布局表现得该视图不存在，应将可见性属性设置为 `gone`：

```xml
tools:visibility="gone"
```

在上述示例中，可见性设置仅适用于布局编辑器，在运行的应用中不起影响。若要在布局编辑器和运行应用中控制可见性，将使用 `android` 命名空间设置相同的属性：

```xml
android:visibility="gone"
```



此按钮用于切换当前工具的可见性设置。例如，如果上方显示的 `Button` 视图当前的工具可见性属性设置为 `gone`，则切换此按钮将使其变为可见。这使得在视图添加到布局和从布局中移除时，能够快速检查其布局行为。该切换按钮也有助于检查布局中的视图是否正确进行了约束，该主题在题为“Android Studio 中使用 `ConstraintLayout` 指南”的章节中有介绍。

## 18.12 转换视图

在布局中将视图从一种类型更改另一种类型（例如将 `TextView` 转换为 `EditText`），可以在 Android Studio 布局编辑器中轻松实现。只需在屏幕布局或“组件树”窗口中右键点击该视图，然后选择 `Convert view...` 菜单选项（图 18-20）：

![image-3SNTFXKT.jpg](img/image-3SNTFXKT.jpeg)

图 18-20

选中后，将弹出一个对话框，其中列出了所选对象可以转换的兼容视图类型列表。例如，图 18-21 显示了现有 `TextView` 视图可以转换的类型：

![image-Z5ES9P35.jpg](img/image-Z5ES9P35.jpeg)

图 18-21

此技术也有助于将布局从一种类型转换为另一种类型（例如，将 `ConstraintLayout` 转换为 `LinearLayout`）。

## 18.13 显示示例数据

在 Android Studio 中设计布局时，会出现这样一种情况：用户界面中要显示的内容在 App 完成并运行之前是不可用的。这有时可能导致我们很难从布局编辑器内部评估布局在 App 运行时的外观。为了解决这个问题，布局编辑器允许指定示例数据，这将用示例图像和数据填充布局编辑器中的视图。

这些示例数据仅在布局编辑器中显示，在 App 运行时不会显示。可以直接编辑布局的 XML 或通过可视化方式使用设计时助手（在设计区域右键点击小部件并选择 `Set Sample Data` 菜单选项）来配置示例数据。

设计时助手面板将为所选的视图项显示一系列预配置的示例数据选项，包括各种配置下的文本和图像的组合。例如，图 18-22 显示了在 `RecyclerView` 列表中选择显示示例数据时显示的示例数据选项：

![image-6NEIGGP4.jpg](img/image-6NEIGGP4.jpeg)

图 18-22

或者，可以在布局设计过程中提供自定义的文本和图像进行显示。在布局编辑器中使用示例数据的示例包含在后文题为“布局编辑器示例数据教程”的章节中。由于示例数据是作为 `tools` 属性实现的，预览中数据的可见性可以使用上方图 18-19 中高亮显示的切换按钮进行控制。

## 18.14 创建自定义设备定义

布局编辑器工具栏中的设备菜单（图 18-23）提供了一个预配置的设备类型列表，选中后，它们将作为设备屏幕画布出现。除了预配置的设备类型外，之前在 Android Studio 环境中配置的任何 `AVD` 实例也将列在菜单中。

要添加额外的设备配置，显示设备菜单，选择 `Add Device Definition` 选项，并按照“在 Android Studio 中创建 Android 虚拟设备（AVD）”章节中概述的步骤进行。

![image-V7NTKRCY.jpg](img/image-V7NTKRCY.jpeg)

图 18-23

## 18.15 当前设备

作为设备选择菜单的替代方案，可以通过从设备菜单选择 `Custom` 选项，点击位于设备屏幕右下角的缩放句柄（图 18-24），并拖动以选择设备显示格式。随着屏幕大小的调整，将出现标记，指示可选择的各种尺寸选项和方向：

![image-1XM94171.jpg](img/image-1XM94171.jpeg)

图 18-24

## 18.16 布局验证

布局验证选项允许在系列 Pixel 尺寸的屏幕上同时预览用户界面布局。要访问布局验证工具窗口，选择 `View -> Tool Windows -> Layout Validation` 菜单选项。加载后，面板将如图 18-25 所示显示，在多个设备屏幕配置上渲染布局：

![image-4CXYUV9J.jpg](img/image-4CXYUV9J.jpeg)

图 18-25

## 18.17 总结

开发 Android 应用的关键部分涉及用户界面的创建。这是在 Android Studio 环境中使用布局编辑器工具完成的，该工具以三种模式运行。

在设计（Design）模式下，从调色板选择视图组件，将其放置在代表 Android 设备屏幕的布局上，并使用属性列表进行配置。代表用户界面布局的底层 XML 可以在代码（Code）模式下直接编辑。另一方面，拆分（Split）模式允许通过可视化和直接编辑 XML 同时创建和修改布局。

这些模式结合在一起提供了一个详尽且直观的用户界面设计环境。布局验证面板允许在各种设备屏幕尺寸上快速预览用户界面布局。

# 19. Android `ConstraintLayout` 指南

正如在“理解 Android 视图、视图组布局”章节中所讨论的，Android 提供了几种布局管理器来设计用户界面。从 Android 7 开始，Google 引入了一种解决了旧布局许多缺陷的布局。这种名为 `ConstraintLayout` 的布局将简单、灵活且高效的布局系统与 Android Studio 编辑器中的强大功能相结合，以便创建能够适应不同屏幕尺寸和方向变化的响应式用户界面布局。

本章将概述 `ConstraintLayout` 的基本概念，而下一章将详细概述如何在 Android 编辑器中使用 `ConstraintLayout` 创建基于约束的布局。

## 19.1 `ConstraintLayout` 如何工作

与其他所有布局一样，`ConstraintLayout` 管理它包含的视觉组件（也称为小部件）的定位和尺寸行为。它是根据每个小部件设置的约束连接来实现的。

要充分使用 `ConstraintLayout`，理解以下核心概念至关重要：

- 约束（Constraints）
- 外边距（Margins）
- 对立约束（Opposing Constraints）
- 约束偏置（Constraint Bias）
- 链（Chains）
- 链样式（Chain Styles）
- 引导线（Guidelines）
- 组（Groups）
- 屏障（Barriers）
- 流（Flow）

### 19.1.1 约束

约束是定义小部件相对于其他部件、容器 `ConstraintLayout` 边缘以及特殊元素对齐和距离的规则集。约束还决定了 Activity 用户界面布局在设备方向变化或在不同屏幕尺寸设备上显示时如何响应。

为了正确配置，小部件必须具有足够的约束连接，以便 `ConstraintLayout` 布局引擎能够在水平和垂直平面上解析其位置。

### 19.1.2 外边距

外边距是指定固定距离的约束形式。考虑一个需要放置在设备屏幕右上角的 `Button` 对象。这可以通过实现从 `Button` 的顶部和右边缘连接到父 `ConstraintLayout` 对应侧边的外边距约束来实现，如图 19-1 所示（注：此处原文未提供图 19-1 实际图片，但文中提及，此处保留描述翻译逻辑）。

如上图所示，这些约束连接中的每一个都关联有一个边界值（margin value），该值决定了控件距离父布局两侧的固定距离。在这种配置下，无论屏幕大小或设备方向如何，`Button` 对象将始终根据两个约束连接的指定，分别距离父级 `ConstraintLayout` 的顶部和右侧边缘 20 和 15 个设备无关像素（dp）。

虽然上述的配置在某些情况下是可以接受的，但它并没有在允许 `ConstraintLayout` 布局引擎通过调整控件位置来响应设备旋转以及支持不同尺寸的屏幕方面提供任何灵活性。为了在此布局中添加这种响应性，有必要实现对立约束。

### 19.1.3 对立约束（Opposing Constraints）

在单个控件上沿同一轴运行的两个约束被视为对立约束。换句话说，左侧和右侧均有约束的控件被认为具有水平对立约束。例如，图 19-2 展示了在之前的布局中同时添加了水平和垂直对立约束：

![image-E4DSZT6M.jpg](img/image-E4DSZT6M.jpeg)

图 19-2

这里理解的关键点是，一旦在特定轴上实现了对立约束，控件的定位将变为基于百分比而非基于坐标。例如，控件不再固定在距离布局顶部的 20dp 处，而是位于距离顶部 30% 的位置。在不同的方向以及在较大或较小的屏幕上运行时，`Button` 将始终位于相对于父级布局尺寸的相同位置。

现在需要理解的是，图 19-2 中概述的布局不仅是使用对立约束实现的，还通过应用约束偏置（constraint bias）来实现。

### 19.1.4 约束偏置（Constraint Bias）

现在已经确定，`ConstraintLayout` 中的控件可能会受到对立约束连接的影响。默认情况下，对立约束是相等的，导致相应的控件在对立轴上居中。例如，图 19-3 显示了一个控件在对立水平和垂直约束的情况下，在包含它的 `ConstraintLayout` 中居中：

![image-CKNTP2D9.jpg](img/image-CKNTP2D9.jpeg)

图 19-3

为了允许在对立约束的情况下调整控件位置，`ConstraintLayout` 实现了一种名为“约束偏置”的功能。约束偏置允许控件沿对立轴的定位根据指定的百分比向某一个约束倾斜。例如，图 19-4 显示了具有 75% 水平偏置和 10% 垂直偏置的之前的约束布局：

![image-O0OYTQ47.jpg](img/image-O0OYTQ47.jpeg)

图 19-4

下一章标题为“在 Android Studio 中使用 `ConstraintLayout` 的指南”，它将更详细地阐述这些概念，并解释这些功能是如何集成到 Android Studio 布局编辑器工具中的。然而，在此期间，还需要涵盖 `ConstraintLayout` 类的另外几个领域。

### 19.1.5 链（Chains）

`ConstraintLayout` 链（chains）提供了一种将两个或多个控件的布局行为定义为一组的方法。链可以在垂直或水平轴上声明，并进行配置以定义链中控件的间距和尺寸。

当控件通过双向约束连接起来时，它们就构成了链。例如，图 19-5 展示了三个以此方式连接的控件：

![image-UUXZJ6RS.jpg](img/image-UUXZJ6RS.jpeg)

图 19-5

链中的第一个元素是链头（chain head），它在垂直链中表示顶部的控件，在水平链的情况下表示最左侧的控件。整个链的布局行为主要通过在链头上设置属性来配置。

### 19.1.6 链样式（Chain Styles）

`ConstraintLayout` 链的布局行为是通过应用到链头的样式决定的。`ConstraintLayout` 支持以下链样式：

- **散布（Spread）** —— 链中的控件在可用空间内均匀分布。这是链的默认行为。

  ![image-TWWY2L.jpg](img/image-TWWY2L.jpeg)

  图 19-6

- **内部散布（Spread Inside）** —— 链中的控件在链头和最后一个控件之间均匀分布。

  ![image-N9RP75C.jpg](img/image-N9RP75C.jpeg)

  图 19-7

- **权重链（Weighted Chain）** —— 通过权重属性允许链中每个控件占据相应空间。

  ![image-Y46HA73.jpg](img/image-Y46HA73.jpeg)

  图 19-8

- **打包（Packed）** —— 构成链的控件聚集在一起。可以通过应用偏置来控制链相对于父容器的位置。

  ![image-PAD1FAX.jpg](img/image-PAD1FAX.jpeg)

  图 19-9

## 19.2 基线对齐（Baseline Alignment）

到目前为止，本章仅提到相对于控件侧边的约束（通常称为侧边约束）。然而，一种常见的需求是控件相对于其显示的内容进行对齐。为了满足这一需求，`ConstraintLayout` 提供了基线对齐支持。

例如，假设 19-1 中的布局需要 `TextView` 控件位于 `Button` 左侧 40dp 处。在这种情况下，`TextView` 需要与 `Button` 基线对齐。这意味着 `Button` 内的文本需要与 `TextView` 内的文本在垂直方向对齐。该布局的额外约束需要如图 19-10 所示连接：

![image-PGEWHSDF.jpg](img/image-PGEWHSDF.jpeg)

图 19-10

`TextView` 现在沿 `Button` 的基线垂直对齐，并在水平方向上距离 `Button` 边缘 40dp。

## 19.3 配置控件尺寸（Configuring Widget Dimensions）

控制控件的尺寸是界面设计过程的一个关键要素。`ConstraintLayout` 提供了可以设置在控件上的选项来管理尺寸行为。这些设置针对高度和宽度单独配置：

- **固定（Fixed）** —— 控件固定为指定的尺寸。
- **匹配约束（Match Constraint）** —— 允许布局引擎调整大小以满足现行的约束。也称为 `AnySize` 或 `MATCH_CONSTRAINT`。
- **自适应内容（Wrap Content）** —— 控件的大小由其内容决定（即文本或图形）。

## 19.4 辅助线（Guideline Helper）

辅助线是 `ConstraintLayout` 中提供的特殊元素，为可以连接的约束提供了额外的目标。可以向 `ConstraintLayout` 实例中添加多个辅助线，这些辅助线反过来可以配置为水平或垂直方向。

一旦添加，就可以建立布局中控件到辅助线的约束连接。这在多个控件必须沿某一轴对齐时特别有用。例如，图 19-11 所示，包含 `ConstraintLayout` 中的三个 `Button` 对象沿一条垂直辅助线约束：

![image-TQVP4ZOC.jpg](img/image-TQVP4ZOC.jpeg)

图 19-11

## 19.5 组辅助线（Group Helper）

`ConstraintLayout` 的此功能允许将组件置于逻辑组中，并将这些组件的可见性作为一个单一实体进行控制。`Group` 是布局中其他组件的引用列表。

一旦定义，更改 `group` 实例的可见性属性（`visible`、`invisible` 或 `gone`）将此更改应用到所有组内成员。这使得通过更改单个属性就能轻松地隐藏和显示多个组件。

一个布局中可以包含多个 `groups`，且一个组件可以属于多个 `group`。如果组之间发生冲突，则在 XML 文件中最后声明的组具有优先级。

## 19.6 屏障助手（Barrier Helper）

与辅助线（guidelines）类似，`barriers` 是用于约束布局内视图的虚拟视图。与辅助线一样，`barrier` 可以是垂直或水平的，并且一个或多个视图可以被约束在其上（为了避免混淆，这些视图被称为受约束视图）。

但与辅助线在布局中保持固定位置不同，`barrier` 的位置是由一组所谓的参考视图（reference views）定义的。引入 `Barriers` 是为了解决经常发生的视图重叠问题。例如，考虑下方图 19-12 所示的布局：

![image-29LAT7YO.jpg](img/image-29LAT7YO.jpeg)

图 19-12

上述布局需要注意的关键点是：`View 3` 的宽度设置为匹配 `constraint mode`，且该视图的左边缘连接到 `View 1` 的右边缘。按照目前的实现方式，增加 `View 1` 的宽度将产生预期效果，即缩小 `View 3` 的宽度：

![image-161EOC84.jpg](img/image-161EOC84.jpeg)

图 19-13

然而，如果增加的是 `View 2` 的宽度而不是 `View 1`，就会出现问题：

![image-KYC2DWCI.jpg](img/image-KYC2DWCI.jpeg)

图 19-14

由于 `View 3` 只受到 `View 1` 的约束，它不会调整大小以适应 `View 2` 宽度的增加，导致视图重叠。

解决此问题的办法是添加一个垂直 `barrier`，并将 `Views 1` 和 `View 2` 分配为屏障的参考视图，以便它们控制屏障的位置。这样 `View 3` 的左边缘将相对于 `barrier` 进行约束，使其成为受约束视图。

现在，当 `View 1` 或 `View 2` 的任一宽度增加时，`barrier` 将移动以适应其中较宽的视图，从而导致 `View 3` 的宽度相对于新的屏障位置发生变化：

![image-OCB192Z5.jpg](img/image-OCB192Z5.jpeg)

图 19-15

在使用 `barriers` 时，单个 `barrier` 关联的参考视图和受约束视图的数量没有限制。

## 19.7 流助手（Flow Helper）

`ConstraintLayout Flow` 助手允许视图组以流式网格样式布局显示。与 `Group` 助手一样，`Flow` 包含了对其负责定位的视图的引用，并提供了各种配置选项，包括垂直和水平方向、换行行为（包括换行前的最大组件数量）、间距和对齐属性。

链行为（Chain behavior）也可以应用于 `Flow` 布局，包括 `spread`、`spread inside` 和 `packed` 选项。

图 19-16 代表了使用 `Flow` 助手实例在水平模式且无换行设置下定位的五个等大小按钮的布局：

![image-EYOMVF0G.jpg](img/image-EYOMVF0G.jpeg)

图 19-16

图 19-17 显示了相同的按钮在水平流配置下的情况，并将换行设置为每第三个组件后进行换行：

![image-U5O1X731.jpg](img/image-U5O1X731.jpeg)

图 19-17

相比之下，图 19-18 显示了按钮将换行模式设置为使用 `spread inside` 链模式的按钮（其效果仅在第二行可见，因为第一行是满的）。该配置还设置了 `gap` 属性以在按钮之间添加间距：

![image-L4G0JZUF.jpg](img/image-L4G0JZUF.jpeg)

图 19-18

作为 `Flow` 助手灵活性的最终演示，图 19-19 显示了五个大小各异的按钮，配置为水平压缩链模式，并在每第三个组件后换行。此外，通过设置 `horizontal-bias` 值为 `1.0`，网格内容已右对齐（值为 `0.0` 将导致左对齐，而 `0.5` 将使网格内容居中对齐）：

![image-D1I3I1OU.jpg](img/image-D1I3I1OU.jpeg)

图 19-19

## 19.8 比例（Ratios）

组件的尺寸可以使用比例设置来定义。例如，可以使用比例设置约束一个组件，使得无论如何调整，宽度始终是高度的两倍。

## 19.9 `ConstraintLayout` 的优势

`ConstraintLayout` 提供了灵活性，允许使用单个布局实现旧布局的功能。通过允许设计所谓的“扁平”或“浅层”布局层次，避免了嵌套布局的问题，从而提高了运行时的性能。

`ConstraintLayout` 的实现也是为了适应各种 Android 设备尺寸。`ConstraintLayout` 的灵活性使得更容易设计响应运行设备的用户界面。Android Studio 布局工具已针对 `ConstraintLayout` 设计进行了增强。

## 19.10 `ConstraintLayout` 的可用性

尽管 `ConstraintLayout` 是在 Android 7 中引入的，但它是作为支持库提供的，并支持到 API 9。这使得使用该布局的应用程序可以在旧的 Android 版本上运行。

## 19.11 总结

`ConstraintLayout` 是 Android 7 引入的布局管理器。它旨在创建适应各种 Android 设备的灵活布局。`ConstraintLayout` 使用约束来控制相对于 `ConstraintLayout` 实例、辅助线、屏障以及布局中其他组件的对齐和定位。

`ConstraintLayout` 是新创建的 Android Studio 项目的默认布局，并在设计用户界面布局时推荐使用。这种简单而灵活的布局管理方法使得实现复杂的响应式用户界面变得简单。

# 20. Android Studio 中使用 `ConstraintLayout` 的指南

正如前面的章节多次提到的，Google 对 Android Studio 布局工具进行了重大更改，其中许多更改完全是为了支持使用 `ConstraintLayout` 进行用户界面设计。现在我们在上一章中概述了 `ConstraintLayout` 的基本概念，本章将更深入地探讨这些概念，同时概述布局工具如何允许设计和实现基于 `ConstraintLayout` 的用户界面。

## 20.1 设计和布局视图

“Android Studio 布局工具指南”的章节解释了 Android Studio 布局工具提供了两种方式来查看活动的用户界面布局，即设计（Design）和布局（Layout，也称为蓝图）视图。这些布局视图可以单独显示，也可以如图 20-1 所示并排显示：

![image-YX0IXOPM.jpg](img/image-YX0IXOPM.jpeg)

图 20-1

设计视图（Design view，位于上图左侧）呈现了布局的“所见即所得”表示，其中布局的外观与其在运行的应用程序中的显示完全一致。相反，`Layout` 视图显示了一种蓝图风格视图，其中阴影轮廓表示组件。

如上图 20-1 所示，`Layout` 视图还显示了约束连接（在本例中，用于将按钮在布局中居中的对立约束）。当选择布局中的特定组件或鼠标指针悬停在设计区域上时，这些约束也会叠加到 `Design` 视图上，如图 20-2 所示：

![image-A8CNDWC7.jpg](img/image-A8CNDWC7.jpeg)

图 20-2

两种视图中约束连接的显示方式可以通过图 20-3 所示的 `View Options`（视图选项）菜单更改：

![image-MA9Y03AO.jpg](img/image-MA9Y03AO.jpeg)

图 20-3

除了显示用户界面布局的两种模式外，`Layout Editor`（布局编辑器）工具提供了三种为特定布局设计建立约束的方法。

## 20.2 自动连接模式（Autoconnect Mode）

自动连接（Autoconnect）顾名义会在项添加到布局时自动建立约束连接。`Autoconnect` 模式可以使用图 20-4 所示的工具栏按钮来开启或关闭：

![image-7HUGDP1Y.jpg](img/image-7HUGDP1Y.jpeg)

图 20-4

`Autoconnect` 模式使用算法根据组件的位置以及组件与父布局侧边和其他元素的接近程度来决定建立的最佳约束。如果任何自动约束连接未能提供预期的行为，可以像本章稍后概述那样进行手动修改。

## 20.3 推断模式（Inference Mode）

推断模式使用一种涉及算法和概率的启发式方法，在组件已添加到布局后自动实现约束连接。这种模式通常在关闭 `Autoconnect` 功能且在没有任何约束连接的情况下对象添加到布局时使用。

这允许通过从调色板将对象拖放到布局画布上来设计布局，并更改尺寸和位置，直到布局符合要求。本质上，这涉及在不担心约束的情况下“绘制”布局。推断模式也可以在设计过程中用于填充布局中缺失的约束。

点击 `Infer constraints`（推断约束）按钮（图 20-5）时，约束会自动添加到布局中：

![image-5HDFX36S.jpg](img/image-5HDFX36S.jpeg)

图 20-5

与 `Autoconnect` 模式一样，`Layout Editor` 工具始终存在推断错误约束的可能性，尽管这些可以手动修改和更正。

## 20.4 手动操作约束

实现约束连接的第三种方法是手动。在这样做时，理解 `Layout Editor` 工具中组件周围出现的各种句柄将很有帮助。例如，考虑图 20-6 所示的组件：

![image-DH765OH5.jpg](img/image-DH765OH5.jpeg)

图 20-6

像弹簧一样的线条（A）代表了从组件侧边到目标已建立的约束连接。对象每个角上的小正方形标记（B）是缩放句柄，点击并拖动时用于缩放组件尺寸。位于组件每侧的小圆圈句柄（C）是侧约束锚点。

要创建约束连接，点击句柄并将生成的线条拖到要连接约束的元素（例如引导线或父布局的侧边或其他组件的侧边），如图 20-7 所示。当连接到另一个组件的侧边时，将线条拖到该组件的侧约束句柄，并在组件和句柄被高亮时释放线条：

![image-63R860Z6.jpg](img/image-63R860Z6.jpeg)

图 20-7

如果将约束线拖动到组件并释放但未附加到约束句柄，布局编辑器将显示一个菜单，其中列出了约束可以附加的侧边列表。例如图 20-8，约束可以附加到目标按钮组件的顶部或底部边缘：

![image-DDM5UJ26.jpg](img/image-DDM5UJ26.jpeg)

图 20-8

额外的标记指示了基线约束（baseline constraints）的锚点，其中组件内部的内容（而非外部边缘）用作对齐点。要显示此标记，右键点击组件并选择 `Show Baseline`（显示基线）菜单选项。

要从基线句柄建立约束连接，将鼠标指针悬停在句柄上直到其高亮，然后点击并拖到目标（例如另一个组件的基线锚点，如图 20-9 所示）。

![image-K2AFJFLP.jpg](img/image-K2AFJFLP.jpeg)

图 20-9

要隐藏基线锚点，再次右键点击组件并选择 `Hide Baseline`（隐藏基线）菜单选项。

## 20.5 在 Inspector 中添加约束

也可以使用 `Android Studio Layout Editor` 工具中 `Attributes`（属性）工具窗口的 `Inspector`（检查器）面板向视图添加约束，如图 20-10 所示。

![image-RBBCZC.jpg](img/image-RBBCZC.jpeg)

图 20-10

中间的正方形表示选中的视图，周围的区域表示应用于相应侧边的约束。视图侧边没有约束的情况由虚线表示（如图中视图的底部所示）。要添加约束，点击此蓝圈，布局编辑器将向它认为合适的目标添加约束。

## 20.6 在 Attributes 窗口查看约束

通过显示 `Attributes` 工具窗口的 `Constraints` 部分可以查看当前选中组件配置的约束列表，如图 20-11 所示：

![image-REF4O74M.jpg](img/image-REF4O74M.jpeg)

图 20-11

点击列表中的约束将在布局中选中该约束。

## 20.7 删除约束

要删除单个约束，在布局或 `Attributes` 工具窗口中选择约束使其高亮（例如图 20-12 中选择了最右侧的约束），然后按键盘删除键。该约束将从布局中移除。

![image-YCS86QJF.jpg](img/image-YCS86QJF.jpeg)

图 20-12

另一种方法是在按住 `Ctrl` 键（macOS 上为 Command）的同时将鼠标指针悬停在约束锚点，在其变为红色后点击。

或者，通过右键点击组件并选择 `Clear Constraints of Selection`（清除选择约束）菜单选项来移除组件上的所有约束。

要从布局中的每个组件中移除所有约束，使用图 20-14 所示的高亮工具栏按钮：

![image-UZCMOGFV.jpg](img/image-UZCMOGFV.jpeg)

图 20-14

边距（margins）可以配合约束（constraints）使用，用于组件与其他元素（如另一个组件、引导线或父布局的边缘）之间的固定间隙。例如，考虑图 20-16 中应用于 `Button` 对象的水平约束：

![image-5312484H.jpg](img/image-5312484H.jpeg)

图 20-16

按照目前的配置，水平约束延伸到父级 `ConstraintLayout` 的左右边缘。因此，该组件具有相互对立的水平约束，这表明 `ConstraintLayout` 布局引擎在运行时对组件的实际位置具有一定的裁量权。这使得布局具有灵活性，以适应不同的屏幕尺寸和设备方向。

水平偏移（horizontal bias）设置也可以控制组件的位置，一直到布局的右侧。例如，图 20-17 显示了应用了 100% 水平偏移的相同按钮：

![image-2IOWY1NE.jpg](img/image-2IOWY1NE.jpeg)

图 20-17

`ConstraintLayout` 边距可以出现在约束连接的末端，代表一个固定间隙，即使在调整偏移或响应 Activity 中其他地方的布局变化时，组件也无法移动此处。在图 20-18 中，右侧约束现在包含一个 50dp 的边距，即使偏移仍设为 100%，组件也无法移动该间隙。

![image-AY4EYK6P.jpg](img/image-AY4EYK6P.jpeg)

图 20-18

组件上现有的边距值可以在检查器（Inspector）中进行修改。如图 20-19 所示，正在使用下拉菜单将当前选中组件的右侧边距更改为 16dp。或者，点击当前值也可以在字段中输入数字。

![image-IJKHKESS.jpg](img/image-IJKHKESS.jpeg)

图 20-19

新约束的默认边距可以随时使用图 20-20 中高亮工具栏中的选项进行更改：

![image-WVHZZJDJ.jpg](img/image-WVHZZJDJ.jpeg)

图 20-20

## 20.10 对立约束和偏移的重要性

正如上一章讨论过的，在使用 `ConstraintLayout` 时，对立约束、边距和偏移是 Android 响应式布局设计的基石。当组件在没有对立约束连接的情况下被约束时，这些约束本质上是边距约束。

这在布局编辑器工具中通过带有边距测量值的实线直线在视觉上被表示出来，如图 20-21 所示：

![image-L0XZHD4T.jpg](img/image-L0XZHD4T.jpeg)

图 20-21

上述约束将组件固定在该位置。结果是，如果设备旋转到横屏模式，组件将不再可见，因为垂直约束会将其推到设备屏幕顶端之外（如图 20-22 所示）。如果应用程序在比设计过程中屏幕更小的设备上运行，也会出现类似的问题。

![image-F27J220I.jpg](img/image-F27J220I.jpeg)

图 20-22

当实现对立约束时，约束连接由锯齿状弹簧线表示（弹簧比喻旨在表示组件的位置没有固定在绝对 X 和 Y 坐标上）：

![image-E6H1JBOP.jpg](img/image-E6H1JBOP.jpeg)

图 20-23

在上述布局中，垂直和水平偏移设置已配置为组件将始终位于距离父布局底部 90% 处和距离左侧边缘 35% 处。因此，当旋转时，组件仍然可见，并且相对于屏幕尺寸保持在相同的位置：

![image-M51H9JNA.jpg](img/image-M51H9JNA.jpeg)

图 20-24

在设计响应式且自适应的用户界面布局时，手动设计用户界面布局和修正自动创建的约束时，考虑偏移和对立约束是非常重要的。

## 20.11 配置组件尺寸

`ConstraintLayout` 中组件的内部尺寸也可以使用检查器进行配置。正如上一章概述的，组件尺寸可以设置为环绕内容（wrap content）、固定（fixed）或匹配约束（match constraint）模式。

当前选中组件上每个尺寸的常用设置显示在检查器中代表组件的正方形内，如图 20-25 所示：

![image-TL1OK9WY.jpg](img/image-TL1OK9WY.jpeg)

图 20-25

上述图形将水平和垂直尺寸设置为环绕内容模式（由向内的 V 形符号表示）。检查器使用以下视觉指示器来表示三种尺寸模式：

| 模式 | 指示器 |
| --- | --- |
| 固定大小 | `^` |
| 匹配约束 | `^` |
| 环绕内容 | `^` |

表 20-1

要更改当前设置，点击指示器可以在三个设置之间循环切换。

此外，可以使用“水平扩展”（Expand Horizontally）和“垂直扩展”（Expand Vertically）选项将组件的大小水平或垂直方向扩展到布局中约束和其他组件允许的最大值。可以通过右键点击布局中的组件并从生成的菜单中选择“组织”（Organize）选项来访问。使用时，当前选中的组件将在水平或垂直方向上增加尺寸以填充可用空间。

![image-QJP1B5.jpg](img/image-QJP1B5.jpeg)

图 20-26

## 20.12 设计时工具定位

名为“Android Studio 布局工具指南”的章节引入了 `tools` 命名空间的概念，并解释了如何使用它来设置仅在布局编辑器中生效的属性。

在后台，Android Studio 还使用 `tools` 属性在没有约束的情况下放置在布局上时将组件固定在位置。例如，想象在禁用自动连接模式时将 `Button` 放置到布局中。虽然组件在预览中看起来处于正确位置，但当应用程序运行时，它将出现在左上角。这是因为组件没有约束来告诉 `ConstraintLayout` 父容器应该将其放在何处。

组件在布局编辑器中看起来位于正确位置，是因为 Android Studio 设置了绝对 X 和 Y 定位工具，以便在添加约束之前将其保持在正确位置。在 XML 布局文件中，其内容可能如下：

```xml
```



```xml
<Button
    android:id="@+id/button4"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Button"
    tools:layout_editor_absoluteX="111dp"
    tools:layout_editor_absoluteY="88dp" />
```

一旦为组件添加足够的约束，布局编辑器将移除这些 `tools` 属性。一种无需运行应用程序即可快速识别哪些组件缺少约束的实用技巧是点击图 20-27 中高亮的按钮以切换工具位置可见性。任何跳转到左上角的组件都是未完全约束的，是由时的 `tools` 绝对 X 和 Y 属性保持的。

![image-OZKIFM6E.jpg](img/image-OZKIFM6E.jpeg)

图 20-27

## 20.13 添加引导线

引导线提供了额外的锚元素。可以通过右键点击布局并选择“垂直引导线”（Vertical Guideline）或“水平引导线”（Horizontal Guideline）菜单选项，或使用工具栏选项来添加引导线，如图 20-28 所示：

![image-8Z653NZ7.jpg](img/image-8Z653NZ7.jpeg)

图 20-28

或者，可以从调色板（Palette）中的 Helper 部分拖动水平和垂直引导线，并将其丢到布局画布或组件树面板上，如图 20-29 中的箭头所示：

![image-6DES33CJ.jpg](img/image-6DES33CJ.jpeg)

图 20-29

一旦添加，指南线将以虚线的形式显示在布局中，并可以通过点击和拖动 `the line` 来移动。若要与指南线建立约束连接，请点击小部件的约束句柄，并在释放之前将其拖动到指南线上。在图 20-30 中，两个 `Buttons` 的左侧通过约束连接到一条垂直指南线。

垂直指南线的位置可以指定为距离父布局左侧或右侧的绝对距离（对于水平指南线，则为顶部或底部）。例如，下图中的垂直指南线位于距离父布局左边缘 97dp 处：

![image-WGSURLFQ.jpg](img/image-WGSURLFQ.jpeg)

Figure 20-30

或者，指南线也可以根据父布局的整体宽度或高度的百分比进行定位。要在这三种模式之间切换，请选择指南线，并点击指南线底部或末端的圆圈（取决于指南线是垂直的还是水平的）。例如，图 20-31 显示了基于百分比定位的指南线：

![image-NO9AYJ8L.jpg](img/image-NO9AYJ8L.jpeg)

Figure 20-31

## 20.14 添加屏障（Barriers）

可以通过右键点击布局并从 `Add helpers` 菜单中选择 `Vertical` 或 `Horizontal Barrier` 选项，或使用工具栏菜单选项来添加屏障，如图 20-28 所示。或者，在 `Palette` 的 `Helpers` 部分找到 `Barrier` 类型，并将其拖放到布局画布或 `Component Tree` 面板中。

一旦向布局中添加了屏障，它将作为 `Component Tree` 面板中的一个项出现：

![image-OQQN1K90.jpg](img/image-OQQN1K90.jpeg)

Figure 20-32

若要将视图作为引用视图（换句话说，即控制屏障位置的视图），请将部件从 `Component Tree` 内部拖到屏障项上。例如，在图 20-33 中，命名为 `textView2` 和 `textView3` 的部件被分配为屏障的引用小部件：

![image-W56366BO.jpg](img/image-W56366BO.jpeg)

Figure 20-33

添加引用视图后，需要配置屏障以指定屏障相对于这些视图的方向。这是屏障方向设置，当 `Component Tree` 面板中选择屏障时，在 `Attributes` 工具窗口中定义：

![image-HLDEY97F.jpg](img/image-HLDEY97F.jpeg)

Figure 20-34

接下来的图显示了一个包含屏障的布局，该屏障声明 `textView1` 和 `textView2` 作为引用视图，并将 `textview3` 作为受约束视图。由于屏障从引用视图的末端向受约束视图推送，屏障方向被设置为 `end`：

![image-I8T3E9OJ.jpg](img/image-I8T3E9OJ.jpeg)

Figure 20-35

## 20.15 添加分组（Group）

若要向布局中添加 `Group`，请右键点击布局并从 `Add helpers` 菜单中选择 `Group` 选项，或使用图 20-28 所示的工具栏菜单选项。或者，在 `Palette` 的 `Helpers` 部分找到 `Group` 项，并将其拖放到布局画布或 `Component Tree` 面板中。

若要向组添加部件，请在 `Component Tree` 中选择它们并拖放到 `Group` 项。例如，图 20-36 显示将三个选中的部件添加到一个组中：

![image-5EU0PIYJ.jpg](img/image-5EU0PIYJ.jpeg)

Figure 20-36

任何被组引用的部件都将以斜体显示在 `Component Tree` 中组项下方，如图 20-37 所示。若要从组中移除部件，请选择它并按下键盘上的删除键：

![image-0FV6VUO4.jpg](img/image-0FV6VUO4.jpeg)

Figure 20-37

一旦部件被分配给组，使用 `Attributes` 工具窗口的 `Constraints` 部分来修改可见性设置：

![image-G42RNTTI.jpg](img/image-G42RNTTI.jpeg)

Figure 20-38

## 20.16 使用流布局助手（Flow Helper）

正如前文概述其他助手所示，可以使用菜单或 `Palette` 添加流布局助手。与 `Group` 助手（图 20-36）一样，通过在 `Component Tree` 中将部件拖动到 `Flow` 项可以将其添加到 `Flow` 实例中。添加 `Flow` 助手并为其分配部件后，在 `Component Tree` 中选择它并使用 `Attribute` 工具窗口的 `Common Attributes` 部分来配置流布局行为：

![image-ISKAXP6O.jpg](img/image-ISKAXP6O.jpeg)

Figure 20-39

## 20.17 部件组的对齐与分布

当布局中选择两个或多个部件时，Android Studio 布局编辑器工具提供了一系列对齐和分布操作。按住 Shift 点击每个部件以将其包含在操作内。

要表示这种布局，XML 资源布局文件可能包含以下按钮控件的条目：

```xml
android:id="@+id/button1"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_marginStart="8dp"
android:layout_marginTop="16dp"
android:text="Button"
app:layout_constraintHorizontal_bias="0.5"
app:layout_constraintStart_toStartOf="parent"
app:layout_constraintTop_toTopOf="parent" />

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

按照目前的配置，没有双向约束来将这些控件分组成一个链（chain）。为了解决这个问题，需要从 `button1` 的右侧到 `button2` 的左侧，以及从 `button3` 的左侧到 `button2` 的右侧添加额外的约束，如下：

```xml
android:id="@+id/button1"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_marginStart="8dp"
android:layout_marginTop="16dp"
android:text="Button"
app:layout_constraintHorizontal_bias="0.5"
app:layout_constraintStart_toStartOf="parent"
app:layout_constraintTop_toTopOf="parent"
app:layout_constraintEnd_toStartOf="@+id/button2" />

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

android:id="@+id/button3"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_marginEnd="8dp"
android:layout_marginTop="16dp"
android:text="Button"
app:layout_constraintHorizontal_bias="0.5"
app:layout_constraintEnd_toEndOf="parent"
app:layout_constraintTop_toTopOf="parent"
app:layout_constraintStart_toEndOf="@+id/button2" />
```

通过这些更改，控件现在配置了双向水平约束。这构成了在布局编辑器中通过链连接视觉表示的 `ConstraintLayout` 链，下图 21-2 所示。注意，在此配置下，链默认设置为散开链（spread chain）样式。

![image-PZ09J7IA.jpg](img/image-PZ09J7IA.jpeg)

图 21-2

也可以通过右键点击一个视图并选择 `Chains -> Create Horizontal Chain` 或 `Chains -> Create Vertical Chain` 菜单选项创建链。

## 21.2 更改链样式

如果没有配置链样式，`ConstraintLayout` 将默认使用散开链样式。可以通过右键点击链中的任何控件并选择 `Cycle Chain Mode` 菜单选项来更改链样式。每点击一次菜单选项，样式将按照散开（spread）、内部散开（spread inside）和聚集（packed）的顺序切换到另一个设置。

或者，也可以在属性工具窗口中展开 `layout_constraints` 属性，并根据链的方向更改 `horizontal_chainStyle` 或 `vertical_chainStyle` 属性来指定样式：

![image-Q8593OEX.jpg](img/image-Q8593OEX.jpeg)

图 21-3

## 21.3 内部散开链样式

图 21-4 展示了使用上述技术将链样式更改为内部散开链样式的效果：

![image-8U4OCKBW.jpg](img/image-8U4OCKBW.jpeg)

图 21-4

## 21.4 聚集链样式

使用相同的技术，将链样式属性更改为聚集（packed）会导致布局发生，如图 21-5 所示：

![image-J5OJHLEO.jpg](img/image-J5OJHLEO.jpeg)

图 21-5

## 21.5 带偏置的聚集链样式

聚集链的位置可能会受到偏置（bias）的影响。偏置值可以在 `0.0` 到 `1.0` 之间。

![image-DX3OUVZ.jpg](img/image-DX3OUVZ.jpeg)

图 21-6

## 21.6 权重链

每个控件相对于其他控件所占据的空间可以通过添加权重属性来控制。图 21-9 显示了将 `button1` 的 `layout_constraintHorizontal_weight` 设置为 `4`，并将 `button2` 和 `button3` 设置为 `2` 的效果：

![image-C2H9ZSXV.jpg](img/image-C2H9ZSXV.jpeg)

图 21-9

## 21.7 使用比例

`ConstraintLayout` 比例允许一个控件的维度相对于控件的另一个维度进行调整（也称为宽高比）。例如，可以将宽高比应用到 `ImageView` 上，以确保其宽度始终是高度的两倍。

维度比例约束通过将受限维度设置为匹配约束模式并在控件上配置 `layout_constraintDimensionRatio` 属性来配置的。该比例值可以指定为浮点值或宽高比例设置。

```xml
android:layout_width="0dp"
android:layout_height="100dp"
android:id="@+id/imageView"
app:layout_constraintDimensionRatio="2:1" />
```

```xml
app:layout_constraintBottom_toBottomOf="parent"
app:layout_constraintRight_toRightOf="parent"
app:layout_constraintLeft_toLeftOf="parent"
app:layout_constraintTop_toTopOf="parent"
app:layout_constraintDimensionRatio="W,1:3" />
```



在上面的示例中，高度将取决于应用于它的约束条件。在这种情况下，约束已配置为，使它附加到父视图的顶部和底部，实质上是将小部件拉伸以填充整个父视图的高度。另一方面，宽度维度被限制为`ImageView`高度的三分之一。因此，无论布局在什么尺寸的屏幕或方向上显示，`ImageView`的高度将始终与父视图相同，宽度为该高度的三分之一。

不通过手动编辑 XML 资源文件也可以获得相同的结果。每当组件尺寸设置为“匹配约束”（match constraint）模式时，属性面板的检查器（Inspector）区域就会出现一个比例控制开关。例如，图 21-10 显示了分别设置为匹配约束模式和`100dp`的按钮组件的布局宽度和高度属性，并突出显示了组件尺寸预览中的比例控制开关：

![image-NDR1OEEN.jpg](img/image-NDR1OEEN.jpeg)

图 21-10

默认情况下，比例尺寸控制是关闭的。点击该控制控件可以启用比例约束，并显示一个可以在其中更改比例的额外字段：

![image-8JXLY918.jpg](img/image-8JXLY918.jpeg)

图 21-11

## 21.8 总结

链（chains）和比例（ratios）都是`ConstraintLayout`类的强大功能，旨在为 Android 应用程序中设计灵活且响应式的用户界面布局提供额外的选项。正如本章概述，Android Studio 布局编辑器已经过增强，以便在用户界面设计过程中更容易地使用这些功能。

# 22. Android Studio 布局编辑器 ConstraintLayout 教程

为 Android 应用程序设计用户界面最简单且高效的方法是使用 Android Studio 布局编辑器工具。本章将概述如何使用这种方法创建基于`ConstraintLayout`的用户界面。本章包含的练习也将作为一个机会，概述从一个“空壳”级 Android Studio 项目开始创建一个 activity 的过程。

在介绍了 Android Studio 布局编辑器用法之后，本章还将介绍布局检查器（Layout Inspector）工具。

## 22.1 Android Studio 布局编辑器工具示例

此示例阶段的第一步是创建一个新的 Android Studio 项目。启动 Android Studio 并通过选择`File` -> `Close Project`菜单关闭任何之前打开的项目。

从欢迎界面选择`New Project`选项，选择`Empty Views Activity`模板并点击`Next`。在`Name`字段中输入`LayoutSample`，并指定`com.ebookfrenzy.layoutsample`为包名。在点击`Finish`按钮之前，将`Minimum API level`设置为`API 26`：Android 8.0 (Oreo)，并将`Language`菜单设置为`Java`。

## 22.2 准备布局编辑器环境

在`app` -> `res` -> `layout`文件夹中找到并双击`activity_main.xml`布局文件，将其加载到布局编辑器工具中。由于本教程旨在获得使用约束的经验，请使用布局编辑器工具栏上的按钮关闭自动连接（Autoconnect）功能。一旦禁用，该按钮将会出现一条斜线，如图 22-1 所示：

![image-S8KMRLMQ.jpg](img/image-S8KMRLMQ.jpeg)

图 22-1

如果`Autoconnect`按钮右侧的默认边距值未设置为`8dp`，请点击它并在生成的面板中选择`8dp`。

用户界面设计还将使用`ImageView`对象来显示图像。在继续之前，应将此图像添加到项目中，以便在章节后续部分使用。该文件名为`GalaxyS23.webp`，可以在以下 URL 下载的示例代码`project_icons`文件夹中找到：

https://www.payloadbooks.com/product/ladybugjava

在 Android Studio 中，显示资源管理器（Resource Manager）工具窗口（`View` -> `Tool Windows` -> `Resource Manager`）。在操作系统的文件导航器中找到`GalaxyS23.webp`图片，并将其拖到资源管理器工具窗口上。在生成的对话框中，点击`Next`，然后点击`Import`按钮将图像添加到项目中。图像现在应该出现在资源管理器中，如下方的图 22-2 所示：

![image-I63FHRA6.jpg](img/image-I63FHRA6.jpeg)

图 22-2

图像也将出现在项目工具窗口的`res` -> `drawables`部分：

![image-UWIVFZYV.jpg](img/image-UWIVFZYV.jpeg)

图 22-3

## 22.3 将组件添加到用户界面

从`Common`调色板类别内部，将`ImageView`对象拖到显示视图的中心。注意，会出现水平和垂直虚线，表示显示的中心轴。当居中时，释放鼠标按钮将视图放置在目标位置。一旦放置在布局中，将出现资源（`Resources`）对话框，请求在视图中显示的图像。在对话框顶部的搜索栏中输入“galaxy”来查找资源，如图 22-4 所示：

![image-8WX99N5.jpg](img/image-8WX99N5.jpeg)

图 22-4

选择图像并点击`OK`将分配给`ImageView`。如有必要，使用缩放句柄调整`ImageView`的大小并将其重新定位在布局中心。此时，布局应匹配图 22-5：

![image-WN2HH9P.jpg](img/image-WN2HH9P.jpeg)

图 22-5

从调色板的`Common`部分点击并拖入`TextView`对象，并将其放置在`ImageView`上，如图 22-6 所示。

使用属性面板，展开`Common Attributes`部分中的`textAppearance`项，将`textSize`属性更改为`24sp`，`textAlignment`设置为`center`，并将文本更改为“Samsung Galaxy S23”。

![image-HJA1WHKK.jpg](img/image-HJA1WHKK.jpeg)

图 22-6

接下来，在布局底部添加三个`Button`组件，并将这些视图的属性设置为“Buy Now”、“Pricing”和“Details”。完成后的布局现在应该匹配图 22-7：

![image-N9NSW63Y.jpg](img/image-N9NSW63Y.jpeg)

图 22-7

此时，组件的约束尚不充分，以便布局引擎能够在运行时定位并调整组件大小。如果现在运行程序，所有组件将位于显示器的左上角。

缺少约束会导致布局无法适应设备方向的变化，导致内容偏离中心，并且图像以及所有三个按钮位于屏幕可视区域之外。使用布局编辑器工具栏上的设备旋转菜单（如图 22-8 中的箭头所示）在横屏模式下查看用户界面：

![image-GCJLV5NV.jpg](img/image-GCJLV5NV.jpeg)

图 22-8

仍需一些工作来使其成为响应式用户界面。

## 22.4 添加约束

约束是创建适应设备方向变化和不同屏幕尺寸布局的关键。首先将布局旋转回竖屏方向，并选择`ImageView`上方的`TextView`组件。选中组件后，从`TextView`的左侧、右侧和顶部建立`ConstraintLayout`对应边的约束，如图 22-9 所示。将顶部约束的间距设置为`16`：

![image-YGMIU094.jpg](img/image-YGMIU094.jpeg)

图 22-9

在约束`TextView`小部件后，选择`ImageView`实例并在左、右两侧建立相反的约束，每个约束都连接到父布局的对应侧。接下来，建立从`ImageView`顶部到`TextView`底部的约束连接，以及从`ImageView`底部到中心`Button`组件顶部的约束连接。如有必要，点击并拖动`ImageView`以使其保持在布局的垂直中心位置。

在`ImageView`仍处于选中状态时，使用属性面板中的`Inspector`（检查器）将`ImageView`的顶部和底部边距分别更改为 24 和 8，并将组件的高度和宽度维度属性均更改为`match_constraint`，以便组件调整大小以匹配约束。这些设置将允许布局引擎在需要时放大或缩小`ImageView`的尺寸以适应布局的变化：

![image-MJQATNSM.jpg](img/image-MJQATNSM.jpeg)

图 22-10

图 22-11 显示了`ImageView`相对于布局中其他元素的当前实现约束：

![image-3PM4N5IA.jpg](img/image-3PM4N5IA.jpeg)

图 22-11

最后一个任务是为三个`Button`组件添加约束。在本示例中，按钮将以链（chain）的形式放置。首先，通过点击图 22-1 中突出显示的工具栏按钮，在`Layout Editor`中开启`Autoconnect`（自动连接）。

接下来，点击`Buy Now`按钮，然后按住 Shift 点击另外两个按钮以选中全部三个。右键点击`Buy Now`按钮，并在弹出菜单中选择`Chains`（链） -> `Create Horizontal Chain`（创建水平链）菜单选项。默认情况下，链将使用散开（spread）样式显示，这是本示例的正确行为。

最后，在`Buy Now`按钮底部和布局底部之间建立边距为 8 的约束。对剩余按钮重复此步骤。

完成这些步骤后，按钮应按图 22-12 所示的顺序进行约束：

![image-4FXM30WC.jpg](img/image-4FXM30WC.jpeg)

图 22-12

## 22.5 测试布局

在布局中添加约束后，将屏幕旋转到横屏模式，并验证布局是否适应了新的屏幕尺寸。

虽然`Layout Editor`工具提供了一个设计用户界面布局的良好视觉环境，但在测试时，运行中的 App 测试是不可替代的。在物理 Android 设备或模拟器会话上启动 App，并验证用户界面是否反映了在`Layout Editor`中创建的布局。例如，图 22-13 显示了横屏模式下的运行 App：

![image-KCBK131Q.jpg](img/image-KCBK131Q.jpeg)

图 22-13

用户界面设计现在已完成。设计更复杂的用户界面布局是上述步骤的延续。将视图拖放到显示器上，根据需要进行定位、约束并设置属性。

## 22.6 使用 Layout Inspector

可以使用`Layout Inspector`工具查看组成用户界面布局的组件层级。App 必须在运行 Android API 29 或更高版本的设备或模拟器上才能访问此信息。App 运行后，选择`Tools` -> `Layout Inspector`菜单选项，然后按照下方图 22-14 中标记为 A 的菜单选择要检查的进程。

一旦检查器加载，最左侧的面板 (A) 显示组成用户界面布局的组件层级。中间面板 (B) 视觉化地表示布局设计。点击视觉布局中的组件会导致该项在层级列表中突出显示，从而易于找到视觉组件相对于整体布局层级的位置。

最右侧的面板（图 22-14 中标记为 C）包含当前选中组件的所有属性设置，允许对组件的内部配置进行深入分析。在适当的情况下，值单元格将包含指向项目源代码中属性设置位置的链接。

![image-1C1FSJE1.jpg](img/image-1C1FSJE1.jpeg)

图 22-14

要以 3D 视图查看布局，点击标记为 D 的按钮。这将显示层级的“爆炸式”表示，以便进行旋转和检查。这对于识别被遮挡的视图等任务非常有用：

![image-YKTB67T3.jpg](img/image-YKTB67T3.jpeg)

图 22-15

点击并拖动渲染图以进行三维空间旋转，使用上方箭头指示的滑块增加层之间的间距。再次点击标记为 D 的按钮返回 2D 视图。

## 22.7 总结

Android Studio 中的`Layout Editor`工具与`ConstraintLayout`类紧密集成。本章通过创建一个示例用户界面，概述了如何使用`Layout Editor`工具添加小部件并设置约束，来实现基于`ConstraintLayout`的用户界面。本章还引入了`Live Layout Inspector`工具，该工具对于分析用户界面布局的结构组成非常有用。

# 23. 在 Android Studio 中手动设计 XML 布局

虽然使用 Android Studio `Layout Editor`工具设计布局极大地提高了效率，但仍然可以通过手动编辑 XML 来创建布局。本章将介绍 XML 布局文件的基础。

## 23.1 手动创建 XML 布局

XML 布局文件的结构非常直观，遵循视图的分级方法。XML 资源的第一行应包含以下声明：

该声明之后是布局的根元素，通常是一个容器视图。这由开启和闭合标签以及任何需要在视图上设置的属性表示。以下 XML 声明了一个`ConstraintLayout`视图作为根元素，并设置了`match_parent`属性以填充设备的所有空间：

```xml
xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res/auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
android:paddingLeft="16dp"
android:paddingRight="16dp"
android:paddingTop="16dp"
android:paddingBottom="16dp"
tools:context=".MainActivity"
```

在上述示例中，布局元素还配置了各边的内边距。Android 布局中的任何间距规范都必须使用以下单位之一：

- `in` - 英制
- `mm` - 毫米
- `pt` - 磅（1/72 英寸）
- `dp` - 密度无关像素。一种根据设备显示物理密度相对于 160dpi 显示基准的抽象测量单位。
- `sp` - 比例无关像素。与`dp`类似，但会根据用户的字体偏好进行缩放。
- `px` - 实际像素。不建议使用，因为不同的屏幕具有不同的像素密度。优先使用`dp`。

任何需要添加到`ConstraintLayout`父容器的子元素必须嵌套在开启和闭合标签之间。在以下示例中，已添加了一个`Button`组件作为`ConstraintLayout`的子元素：

```xml
<Button
    android:id="@+id/button"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="My Button" />
```

按照目前的实现，该按钮没有任何约束连接。因此，在运行时，按钮将出现在屏幕的左上角（尽管由于父布局分配的内边距缩进了 16dp）。然而，如果在按钮两侧添加了相反的约束，它将居中显示在布局中：

```xml
android:text="My Button"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:id="@+id/button"
app:layout_constraintBottom_toBottomOf="parent"
app:layout_constraintEnd_toEndOf="parent"
app:layout_constraintStart_toStartOf="parent"
app:layout_constraintTop_toTopOf="parent" />
```

若要在布局中添加第二个控件，请将其嵌入`ConstraintLayout`元素的正体内。例如，下面的修改为布局中添加了一个`TextView`控件：

```xml
xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
android:paddingLeft="16dp"
android:paddingTop="16dp"
android:paddingRight="16dp"
android:paddingBottom="16dp"
tools:context=".MainActivity"

android:text="@string/button_string"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:id="@+id/button"
app:layout_constraintBottom_toBottomOf="parent"
app:layout_constraintEnd_toEndOf="parent"
```



`app:layout_constraintStart_toStartOf="parent"`

`app:layout_constraintTop_toTopOf="parent" />`

`android:text="My Text"`

`android:layout_width="wrap_content"`

`android:layout_height="wrap_content"`

`android:id="@+id/textView" />`

同样，新添加的 `TextView` 缺少约束会导致它在运行时出现在布局的左上角。下面的修改添加了与父布局连接的相反约束，以使控件水平居中，同时添加了一个将 `TextView` 底部连接到 `button` 顶部的约束：

```xml
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

此外，请注意 `Button` 和 `TextView` 视图声明了多个属性。这两个视图都被分配了 ID，并配置为显示由名为 `button_string` 和 `text_string` 的字符串资源表示的字符串。此外，两个对象都声明了 `wrap_content` 高和宽属性，以便其尺寸能够适应内容（在本例中，即字符串资源值引用的文本）。

在设计模式下的布局编辑器器的预览面板中查看，上述布局的渲染结果如如图 23-1 所示：

![image-PDWVAL7G.jpg](img/image-PDWVAL7G.jpeg)

图 23-1

## 23.2 手动编写 XML 与 视觉布局设计

是手动编写 XML 还是使用设计模式下的布局编辑器工具，这取决于个人喜好。然而，使用设计模式有其优势。

首先，设计模式通常会更快，因为它避免了输入 XML 代码的需要。此外，设计模式避免了学习 Android SDK 视图类各种属性值复杂性的需要。与其不断参考 Android 文档来查找正确的关键字和值，大多数属性可以通过参考属性面板（Attributes panel）找到。

抛开设计模式的所有优势不谈，重要的是，用户界面设计的两种方法完全不是互斥的。作为应用程序开发者，你可能会在设计模式下创建用户界面，同时通过直接编辑生成的 XML 资源对设计进行微调和布局调整。界面设计的这两种视图在 Android Studio 环境中并排显示，使得在 XML 和视觉布局之间无缝工作变得简单。

## 23.3 总结

Android Studio 布局编辑器工具提供了一种视觉直观的用户界面设计方法。通过使用拖放范式结合一系列属性编辑器，该工具为应用程序开发者带来了显著的生产力效益。

用户界面设计也可以通过手动编写 XML 布局资源文件来实现，其格式结构良好且易于理解。

布局编辑器工具生成 XML 资源文件的事实意味着，这两种界面设计方法可以结合起来，为用户界面开发提供一种“兼顾两者”的方法。

## 24. 使用约束集管理约束

在到本书为止，所有的用户界面设计任务都是使用 Android Studio 布局编辑器工具完成的，无论是文本模式还是设计模式。编写 XML 资源文件或使用 Android Studio 布局编辑器的替代方案是编写 Java 代码来直接创建、配置和操作组成 Android Activity 用户界面的视图对象。本章将在描述视图属性以及布局约束的创建和管理等关键概念之前，将探索编写 Java 代码创建用户界面的某些优缺点。

在下一章中，将创建一个示例项目，并用于演示这种创建方法中涉及的典型步骤。

## 24.1 Java 代码与 XML 布局文件

与使用设计模式下的布局编辑器工具相比，何时手动编写 XML 取决于个人喜好。使用 XML 资源文件设计界面有许多优势。事实上，Google 在 Android 文档中极力推崇 XML 资源优于 Java 代码的优点。正如上一节所述，使用 XML 方法的一个关键优势是可以使用 Android Studio 布局编辑器工具，它可以生成 XML。另一个优势是一旦创建应用程序，就可以通过修改 XML 来更改界面，从而避免重新编译应用程序。此外，即使在编写 XML 布局，也可以通过布局编辑器的预览功能获得界面的实时反馈。

关于 Java 代码布局的优势，Java 相比 XML 资源文件最重要的优势体现在处理动态用户界面时。XML 资源文件本质上对于定义静态布局最有用，这些布局在每次调用 Activity 之间不太发生显著变化。另一方面，Java 代码非常适用于运行时动态创建用户界面。这在用户界面每次执行时都可能不同时尤为有用。

在 Java 代码中处理用户界面组件的知识，在必须在应用程序运行时对静态 XML 资源布局进行动态更改时也同样有用。

最后，某些开发者倾向于编写 Java 代码而不是使用布局工具和 XML，无论后者提供哪些优势。

第一个视图（通常是一个可以添加额外子视图的容器视图）通过调用 activity 的 `setContentView()` 方法显示给用户。可以通过调用该对象的 `addView()` 方法向根视图添加额外的视图。

当使用 `Java` 代码操作在 XML 布局资源文件中包含的视图时，有必要获取视图的 ID。对于在 `Java` 中创建的视图也遵循相同的规则。因此，对于后续在 `Java` 代码中需要进行某些类型访问的任何视图，必须为其分配一个 ID。这可以通过调用相关视图对象的 `setId()` 方法来实现。在随后的代码中，可以通过对象的 `getId()` 方法获取视图的 ID。

## 24.3 视图属性 (View Attributes)

每个视图类都关联有一系列属性。这些属性设置直接作用在视图实例上，通常定义了视图对象的外观或行为。属性的示例包括显示在 `Button` 对象上的文本，或 `ConstraintLayout` 视图的背景颜色。Android SDK 中的每个视图类都有一组预定义的方法，允许用户设置和获取这些属性值。例如，`Button` 类有一个 `setText()` 方法，可以在 `Java` 代码中调用该方法将按钮上显示的文本设置为特定的字符串值。另一方面，可以通过调用对象的 `setBackgroundColor()` 方法来设置 `ConstraintLayout` 对象的背景颜色。

## 24.4 约束集 (Constraint Sets)

虽然属性设置是视图内部的，并决定了视图的外观和行为，但约束集控制了视图相对于其父视图和其他兄弟视图的显示。每个 `ConstraintLayout` 实例都关联有一组约束，定义了其子视图是如何定位和约束的。

在 `Java` 代码中处理约束集的关键是 `ConstraintSet` 类。该类包含一系列方法，允许执行创建、配置和将约束应用于 `ConstraintLayout` 实例等任务。此外，`ConstraintLayout` 实例的当前约束可以复制到 `ConstraintSet` 对象中，并应用于其他布局（可以或可以带有修改）。

`ConstraintSet` 实例的创建就像其他 `Java` 对象一样：

```
ConstraintSet set = new ConstraintSet();
```

一旦创建了约束集，就可以在该实例上调用方法来执行广泛的任务。

### 24.4.1 建立连接 (Establishing Connections)

`ConstraintSet` 类的 `connect()` 方法用于建立视图之间的约束连接。以下代码配置了一个约束集，其中 `Button` 视图的左侧连接到 `EditText` 视图的右侧，间距为 70dp：

```
set.connect(button1.getId(), ConstraintSet.LEFT,
editText1.getId(), ConstraintSet.RIGHT, 70);
```

### 24.4.2 将约束应用于布局 (Applying Constraints to a Layout)

一旦配置了约束集，必须将其应用于 `ConstraintLayout` 实例才能生效。约束集的应用是通过调用 `applyTo()` 方法实现的，并传递要应用设置的布局对象的引用：

```
set.applyTo(myLayout);
```

### 24.4.3 父级约束连接 (Parent Constraint Connections)

子视图与其父 `ConstraintLayout` 之间的连接也可以通过引用 `ConstraintSet.PARENT_ID` 常来建立。在以下示例中，约束集被配置为将 `Button` 视图的顶部连接到父布局的顶部，间距为 100dp：

```
set.connect(button1.getId(), ConstraintSet.TOP,
ConstraintSet.PARENT_ID, ConstraintSet.TOP, 100);
```

### 24.4.4 尺寸约束 (Sizing Constraints)

提供了多种方法来控制视图的尺寸行为。例如，以下代码将 `Button` 视图的水平尺寸设置为 `wrap_content`，并将 `ImageView` 实例的垂直尺寸设置为最大 250dp：

```
set.constrainWidth(button1.getId(), ConstraintSet.WRAP_CONTENT);
set.constrainMaxHeight(imageView1.getId(), 250);
```

### 24.4.5 约束偏置 (Constraint Bias)

正如“在 Android Studio 中使用 ConstraintLayout 的指南”章节概述的那样，当视图具有相反的约束时，它将沿约束轴居中（即水平方向或垂直方向）。这种居中可以通过在特定的约束轴上应用偏置来调整。在使用 Android Studio 布局编辑器时，这是通过属性（Attributes）工具窗口中的控件实现的。然而，在处理约束集时，可以使用 `setHorizontalBias()` 和 `setVerticalBias()` 方法添加偏置，引用视图 ID 和作为 0 到 1 之间的浮点值的偏置值。

例如，以下代码在应用 25% 的水平偏置之前，将 `Button` 的左侧和右侧约束到父布局相应的侧边：

```
set.connect(button1.getId(), ConstraintSet.LEFT,
ConstraintSet.PARENT_ID, ConstraintSet.LEFT, 0);
set.connect(button1.getId(), ConstraintSet.RIGHT,
ConstraintSet.PARENT_ID, ConstraintSet.RIGHT, 0);
set.setHorizontalBias(button1.getId(), 0.25f);
```

### 24.4.6 对齐约束 (Alignment Constraints)

也可以使用约束集应用对齐。Android Studio 布局编辑器提供的全套对齐选项也可以通过约束集进行配置，通过 `centerVertically()` 和 `centerHorizontally()` 方法，这两个方法根据配置的对齐方式接受不同的参数。此外，`center()` 方法用于在两个视图之间居中视图。

在下面的代码中，`button2` 的位置使其与 `button1` 水平对齐：

```
set.centerHorizontally(button2.getId(), button1.getId());
```

### 24.4.7 复制与应用约束集 (Copying and Applying Constraint Sets)

可以使用 `clone()` 方法将 `ConstraintLayout` 实例的当前约束复制到 `ConstraintSet` 对象中。例如，以下代码将名为 `myLayout` 的 `ConstraintLayout` 实例的设置复制到约束集对象：

```
set.clone(myLayout);
```

一旦复制，可以将约束集直接应用于布局，或者如下例所示在应用之前进行修改：

```
ConstraintSet set = new ConstraintSet();
set.clone(myLayout);
set.constrainWidth(button1.getId(), ConstraintSet.WRAP_CONTENT);
set.applyTo(mySecondLayout);
```

### 24.4.8 ConstraintLayout 链 (ConstraintLayout Chains)

可以使用 `createHorizontalChain()` 和 `createVerticalChain()` 方法在约束集中创建垂直和水平链。方法的语法如下：

`createHorizontalChain(int leftId, int leftSide, int rightId, int rightSide, int[] chainIds, float[] weights, int style);`

根据上述语法，以下示例创建从 `button1` 开始到 `button4` 结束的水平分布链。在这些视图之间是 `button2` 和 `button3`，它们的权重均设置为零：

```
int[] chainViews = {button2.getId(), button3.getId()};
float[] chainWeights = {0, 0};
set.createHorizontalChain(button1.getId(), ConstraintSet.LEFT,
button4.getId(), ConstraintSet.RIGHT,
chainViews, chainWeights,
ConstraintSet.CHAIN_SPREAD);
```

可以通过向 `removeFromHorizontalChain()` 或 `removeFromVerticalChain()` 方法传递要移除的视图 ID 从链中移除。可以使用 `addToHorizontalChain()` 或 `addToVerticalChain()` 方法将视图添加到现有链。在两种情况下，方法都以要插入新视图的两个视图 ID 作为参数：

```
set.addToHorizontalChain(newViewId, leftViewId, rightViewId);
```

### 24.4.9 指南线 (Guidelines)

可以使用 `create()` 方法将指南线添加到约束集中，然后使用 `setGuidelineBegin()`、`setGuidelineEnd()` 或 `setGuidelinePercent()` 方法进行定位。在接下来的代码中，创建了一个垂直指南线，并将其定位在父布局宽度的 50% 处。然后将按钮视图的左侧连接到该指南线，且没有边距：

```
set.create(R.id.myGuideline, ConstraintSet.VERTICAL_GUIDELINE);
set.setGuidelinePercent(R.id.myGuideline, 0.5f);
set.connect(button.getId(), ConstraintSet.LEFT,
R.id.myGuideline, ConstraintSet.RIGHT, 0);
set.applyTo(layout);
```

### 24.4.10 移除约束

可以使用 `clear()` 方法从约束集中的视图移除约束，并通过参数传递视图 ID 和要移除约束的锚点点：

```
set.clear(button.getId(), ConstraintSet.LEFT);
```

同样，通过在 `clear()` 方法调用中仅引用视图，即可一次性移除该视图上的所有约束：

```
set.clear(button.getId());
```

### 24.4.11 缩放

可以使用 `ConstraintSet` 的 `setScaleX()` 和 `setScaleY()` 方法调整布局内视图的比例，这些方法接收执行操作的视图以及表示比例的浮点值作为参数。在接下来的代码中，一个按钮对象被缩放到原始宽度的两倍和高度的一半：

```
set.setScaleX(myButton.getId(), 2f);
set.setScaleY(myButton.getId(), 0.5f);
```

### 24.4.12 旋转

分别可以使用 `setRotationX()` 和 `setRotationY()` 方法沿 X 轴或 Y 轴旋转视图，这两个方法都必须传递要旋转视图的 ID 和表示旋转角度的浮点值。旋转发生的中心点可以通过调用 `setTransformPivot()`、`setTransformPivotX()` 和 `setTransformPivotY()` 方法来定义。接下来的代码使用位于点 (500, 500) 的中心点将按钮视图在 Y 轴上旋转 30 度：

```
set.setTransformPivot(button.getId(), 500, 500);
set.setRotationY(button.getId(), 30);
set.applyTo(layout);
```



在涵盖了约束集的理论以及从 Java 代码创建用户界面的方法后，下一章将通过创建一个示例应用程序来将这些理论付诸实践。关于 `ConstraintSet` 类的更多细节，请参考以下 URL 中的参考指南：

`https://developer.android.com/reference/androidx/constraintlayout/widget/ConstraintSet`

## 24.5 总结

作为编写 XML 布局资源文件或使用 Android Studio 布局编辑器工具的替代方案，也可以在 Java 代码中动态创建 Android 用户界面。

在 Java 代码中创建布局包括创建视图类的实例，并在这些对象上设置属性以定义所需的外和行为。

视图相对于其 `ConstraintLayout` 父视图以及任何兄弟视图的定位和大小是通过约束集（constraint sets）定义的。约束集由 `ConstraintSet` 类的实例表示，一旦创建，就可以使用广泛的方法调用进行配置，以执行诸如建立约束连接、控制视图缩放行为和创建链等任务。

在本章涵盖了 `ConstraintSet` 类的基础知识后，下一章将通过一个教程将这些功能应用到实践中。

## 25. Android ConstraintSet 教程

上一章介绍了使用 `ConstraintLayout` 和 `ConstraintSet` 类在 Java 代码中创建和修改用户界面布局的基本概念。本章将通过创建一个使用 Java 代码创建且不使用 Android Studio 布局编辑器工具的示例布局，将这些概念付诸实践。

### 25.1 在 Android Studio 中创建示例项目

启动 Android Studio，从欢迎屏幕上选择 New Project（新建项目）选项，在弹出的新项目对话框中，点击 Next（下一步）按钮之前选择 Empty Views Activity 模板。

在 Name（名称）字段中输入 `JavaLayout`，并指定 `com.ebookfrenzy.javalayout` 为包名。在点击 Finish（完成）按钮之前，将 Minimum API level 设置为 API 26: Android 8.0 (Oreo)，并将 Language（语言）菜单设置为 Java。

项目创建完成后，`MainActivity.java` 文件将自动加载到编辑面板。正如我们预期的那样，Android Studio 创建了一个模板活动并重写了 `onCreate()` 方法，为添加 Java 代码以创建用户界面提供了一个理想的位置。

### 25.2 向 Activity 添加视图

`onCreate()` 方法目前设计为使用资源布局文件创建用户界面。因此，首先从该方法中删除以下几行：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    EdgeToEdge.enable(this);
    setContentView(R.layout.activity_main);
    ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main),
    (v, insets) -> {
        Insets systemBars =
        insets.getInsets(WindowInsetsCompat.Type.systemBars());
        v.setPadding(systemBars.left, systemBars.top,
        systemBars.right, systemBars.bottom);
        return insets;
    });
}
```

下一个修改是向活动添加一个带有单个 `Button` 视图子元素的 `ConstraintLayout` 对象。这涉及创建 `ConstraintLayout` 和 `Button` 类的新实例。然后需要将 `Button` 视图作为子视图添加到 `ConstraintLayout` 中，而后者通过通过的 `setContentView()` 方法显示：

```java
package com.ebookfrenzy.javalayout;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import androidx.constraintlayout.widget.ConstraintLayout;
import android.widget.Button;

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

当以此方式创建用户界面对象的新实例时，构造方法必须传递创建对象所在的上下文，在本例中，上下文是当前活动。由于上述代码位于活动内部，因此通过标准的 `this` 关键字引用上下文：`Button myButton = new Button(this);`

完成上述添加后，编译并运行应用程序（在物理设备或模拟器上）。启动后，可见结果将是一个没有任何文本的按钮出现在 `ConstraintLayout` 视图的左上角，如图 25-1 所示：

![image-74GCK5.jpg](img/image-74GCK5.jpeg)

图 25-1

### 25.3 设置视图属性

对于本次练习，我们需要将 `ConstraintLayout` 视图的背景设置为蓝色，并让 `Button` 视图显示文本为“Press Me”，背景为黄色。这些任务可以通过如下代码片段所示，在 Java 代码中设置视图属性来实现。为了让按钮上的文本轻松翻译成其他语言，将其作为字符串资源添加。在 Project 工具窗口中，找到 `app -> res -> values -> strings.xml` 文件并对其进行修改，为“Press Me”字符串添加资源值：

```xml
JavaLayout
Press Me
```

虽然这是处理代码中直接引用字符串的推荐方法，但在后续的许多示例中将直接在代码中输入字符串，以避免在书中重复此步骤。

一旦字符串存储为资源，就可以按照如下方式从代码内部访问：

`getString(R.string.press_me);`

创建字符串资源后，在 `configureLayout()` 方法中添加代码以设置按钮文本和颜色属性：

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

当应用编译并运行后，布局将反映属性设置，使得布局将以蓝色背景显示，按钮将在黄色背景上显示指定的文本。

## 25.4 创建视图 ID (Creating View IDs)

当布局完成后，它将包含一个 `Button` 和一个 `EditText` 视图。在 `ConstraintSet` 类的方法中引用这些视图之前，必须为它们分配唯一的视图 ID。此过程的第一步是创建一个包含这些 ID 值的新资源文件。

右键点击 `app` -> `res` -> `values` 文件夹，选择 `New` -> `Values Resource File` 菜单选项并将新资源文件命名为 `id.xml`。创建资源文件后，编辑它使其内容如下：

在教程的此阶段，仅创建了 `Button`，因此编辑 `configureLayout()` 方法为对象分配相应的 ID：

```java
private void configureLayout() {
    Button myButton = new Button(this);
    myButton.setText(getString(R.string.press_me));
    myButton.setBackgroundColor(Color.YELLOW);
    myButton.setId(R.id.myButton);
}
```

## 25.5 配置约束集 (Configuring the Constraint Set)

在没有约束的情况下，`ConstraintLayout` 视图将 `Button` 视图放置在屏幕的左上角。为了指示布局视图将按钮放在不同的位置（在本例中为水平和垂直居中），有必要创建一个 `ConstraintSet` 实例，用适当设置对其进行初始化并将其应用于父布局。

对于此示例，需要配置按钮，使其宽度和高度限制为其显示文本的大小，并使视图在父布局中居中。再次编辑 `configureLayout()` 方法以进行这些更改：

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
    set.constrainHeight(myButton.getId(), ConstraintSet.WRAP_CONTENT);
    set.constrainWidth(myButton.getId(), ConstraintSet.WRAP_CONTENT);
    set.connect(myButton.getId(), ConstraintSet.START, ConstraintSet.PARENT_ID, ConstraintSet.START, 0);
    set.connect(myButton.getId(), ConstraintSet.END, ConstraintSet.PARENT_ID, ConstraintSet.END, 0);
    set.connect(myButton.getId(), ConstraintSet.TOP, ConstraintSet.PARENT_ID, ConstraintSet.TOP, 0);
    set.connect(myButton.getId(), ConstraintSet.BOTTOM, ConstraintSet.PARENT_ID, ConstraintSet.BOTTOM, 0);
    set.applyTo(myLayout);
}
```

配置好初始约束后，编译并运行应用，并验证 `Button` 视图现在出现在布局的中心：

![image-PCCH3OZ2.jpg](img/image-PCCH3OZ2.jpeg)

图 25-2

## 25.6 添加 EditText 视图 (Adding the EditText View)

要添加到布局的下一个项是 `EditText` 视图。第一步是创建 `EditText` 对象，按照 `id.xml` 资源文件中的声明分配 ID，并将其添加到布局中。实现这些步骤的代码更改现在需要对 `configureLayout()` 方法进行如下修改：

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

`EditText` 控件的大小旨在根据其显示的内容进行调整，在布局中水平居中，并位于现有 `Button` 视图上方 70dp 处。向 `configureLayout()` 方法添加代码，使其内容如下：

```java
set.connect(myButton.getId(), ConstraintSet.START, ConstraintSet.PARENT_ID, ConstraintSet.START, 0);
set.connect(myButton.getId(), ConstraintSet.END, ConstraintSet.PARENT_ID, ConstraintSet.END, 0);
set.connect(myButton.getId(), ConstraintSet.TOP, ConstraintSet.PARENT_ID, ConstraintSet.TOP, 0);
set.connect(myButton.getId(), ConstraintSet.BOTTOM, ConstraintSet.PARENT_ID, ConstraintSet.BOTTOM, 0);
set.connect(myEditText.getId(), ConstraintSet.START, ConstraintSet.PARENT_ID, ConstraintSet.START, 0);
set.connect(myEditText.getId(), ConstraintSet.END, ConstraintSet.PARENT_ID, ConstraintSet.END, 0);
set.connect(myEditText.getId(), ConstraintSet.TOP, myButton.getId(), ConstraintSet.BOTTOM, 70);
set.connect(myEditText.getId(), ConstraintSet.BOTTOM, ConstraintSet.PARENT_ID, ConstraintSet.BOTTOM, 0);
```



创建字符串资源后，在 `configureLayout()` 方法中添加代码以设置按钮文本和颜色属性：

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

当应用编译并运行后，布局将反映属性设置，使得布局将以蓝色背景显示，按钮将在黄色背景上显示指定的文本。

## 25.4 创建视图 ID（Creating View IDs）

当布局完成后，它将包含一个 `Button` 和一个 `EditText` 视图。在 `ConstraintSet` 类的方法中引用这些视图之前，必须为它们分配唯一的视图 ID。此过程的第一步是创建一个包含这些 ID 值的新资源文件。

右键点击 `app` -> `res` -> `values` 文件夹，选择 `New` -> `Values Resource File` 菜单选项，并将新资源文件命名为 `id.xml`。创建资源文件后，编辑它使其内容如下：

在教程的此阶段，仅创建了 `Button`，因此编辑 `configureLayout()` 方法为对象分配相应的 ID：

```java
private void configureLayout() {

    Button myButton = new Button(this);

    myButton.setText(getString(R.string.press_me));

    myButton.setBackgroundColor(Color.YELLOW);

    myButton.setId(R.id.myButton);

}
```

## 25.5 配置约束集（Configuring the Constraint Set）

在没有约束的情况下，`ConstraintLayout` 视图将 `Button` 视图放置在屏幕的左上角。为了指示布局视图将按钮放在不同的位置（在本例中为水平和垂直居中），有必要创建一个 `ConstraintSet` 实例，用适当设置对其进行初始化，并将其应用于父布局。

对于此示例，需要配置按钮，使其宽度和高度限制为其显示文本的大小，并使视图在父布局中居中。再次编辑 `configureLayout()` 方法以进行这些更改：

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

    set.constrainHeight(myButton.getId(), ConstraintSet.WRAP_CONTENT);

    set.constrainWidth(myButton.getId(), ConstraintSet.WRAP_CONTENT);

    set.connect(myButton.getId(), ConstraintSet.START, ConstraintSet.PARENT_ID, ConstraintSet.START, 0);

    set.connect(myButton.getId(), ConstraintSet.END, ConstraintSet.PARENT_ID, ConstraintSet.END, 0);

    set.connect(myButton.getId(), ConstraintSet.TOP, ConstraintSet.PARENT_ID, ConstraintSet.TOP, 0);

    set.connect(myButton.getId(), ConstraintSet.BOTTOM, ConstraintSet.PARENT_ID, ConstraintSet.BOTTOM, 0);

    set.applyTo(myLayout);

}
```

配置好初始约束后，编译并运行应用，并验证 `Button` 视图现在出现在布局的中心：

![image-PCCH3OZ2.jpg](img/image-PCCH3OZ2.jpeg)

图 25-2

## 25.6 添加 EditText 视图（Adding the EditText View）

要添加到布局的下一个项是 `EditText` 视图。第一步是创建 `EditText` 对象，按照 `id.xml` 资源文件中的声明分配 ID，并将其添加到布局中。实现这些步骤的代码更改现在需要对 `configureLayout()` 方法进行如下修改：

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

`EditText` 控件的大小旨在根据其显示的内容进行调整，在布局中水平居中，并位于现有 `Button` 视图上方 70dp 处。向 `configureLayout()` 方法添加代码，使其内容如下：

```java
set.connect(myButton.getId(), ConstraintSet.START, ConstraintSet.PARENT_ID, ConstraintSet.START, 0);

set.connect(myButton.getId(), ConstraintSet.END, ConstraintSet.PARENT_ID, ConstraintSet.END, 0);

set.connect(myButton.getId(), ConstraintSet.TOP, ConstraintSet.PARENT_ID, ConstraintSet.TOP, 0);

set.connect(myButton.getId(), ConstraintSet.BOTTOM, ConstraintSet.PARENT_ID, ConstraintSet.BOTTOM, 0);
```



创建字符串资源后，在`configureLayout()`方法中添加代码以设置按钮文本和颜色属性：

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

当应用编译并运行后，布局将反映属性设置，使得布局将以蓝色背景显示，按钮将在黄色背景上显示指定的文本。

## 25.4 创建视图 ID (Creating View IDs)

当布局完成后，它将包含一个`Button`和一个`EditText`视图。在`ConstraintSet`类的方法中引用这些视图之前，必须为它们分配唯一的视图 ID。此过程的第一步是创建一个包含这些 ID 值的新资源文件。

右键点击`app` -> `res` -> `values`文件夹，选择`New` -> `Values Resource File`菜单选项并将新资源文件命名为`id.xml`。创建资源文件后，编辑它使其内容如下：

在教程的此阶段，仅创建了`Button`，因此编辑`configureLayout()`方法为对象分配相应的 ID：

```java
private void configureLayout() {

    Button myButton = new Button(this);

    myButton.setText(getString(R.string.press_me));

    myButton.setBackgroundColor(Color.YELLOW);

    myButton.setId(R.id.myButton);

}
```

## 25.5 配置约束集 (Configuring the Constraint Set)

在没有约束的情况下，`ConstraintLayout`视图将`Button`视图放置在屏幕的左上角。为了指示布局视图将按钮放在不同的位置（在本例中为水平和垂直居中），有必要创建一个`ConstraintSet`实例，用适当设置对其进行初始化并将其应用于父布局。

对于此示例，需要配置按钮，使其宽度和高度限制为其显示文本的大小，并使视图在父布局中居中。再次编辑`configureLayout()`方法以进行这些更改：

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

    set.constrainHeight(myButton.getId(), ConstraintSet.WRAP_CONTENT);

    set.constrainWidth(myButton.getId(), ConstraintSet.WRAP_CONTENT);

    set.connect(myButton.getId(), ConstraintSet.START, ConstraintSet.PARENT_ID, ConstraintSet.START, 0);

    set.connect(myButton.getId(), ConstraintSet.END, ConstraintSet.PARENT_ID, ConstraintSet.END, 0);

    set.connect(myButton.getId(), ConstraintSet.TOP, ConstraintSet.PARENT_ID, ConstraintSet.TOP, 0);

    set.connect(myButton.getId(), ConstraintSet.BOTTOM, ConstraintSet.PARENT_ID, ConstraintSet.BOTTOM, 0);

    set.applyTo(myLayout);

}
```

配置好初始约束后，编译并运行应用，并验证`Button`视图现在出现在布局的中心：

![image-PCCH3OZ2.jpg](img/image-PCCH3OZ2.jpeg)

图 25-2

## 25.6 添加 EditText 视图 (Adding the EditText View)

要添加到布局的下一个项是`EditText`视图。第一步是创建`EditText`对象，按照`id.xml`资源文件中的声明分配 ID，并将其添加到布局中。实现这些步骤的代码更改现在需要对`configureLayout()`方法进行如下修改：

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

`EditText`控件的大小旨在根据其显示的内容进行调整，在布局中水平居中，并位于现有`Button`视图上方 70dp 处。向`configureLayout()`方法添加代码，使其内容如下：

```java
set.connect(myButton.getId(), ConstraintSet.START, ConstraintSet.PARENT_ID, ConstraintSet.START, 0);

set.connect(myButton.getId(), ConstraintSet.END, ConstraintSet.PARENT_ID, ConstraintSet.END, 0);

set.connect(myButton.getId(), ConstraintSet.TOP, ConstraintSet.PARENT_ID, ConstraintSet.TOP, 0);

set.connect(myButton.getId(), ConstraintSet.BOTTOM, ConstraintSet.PARENT_ID, ConstraintSet.BOTTOM, 0);
```

*(注：原文中的代码块逻辑顺序与描述略有差异，翻译已按代码逻辑对齐)*

## 25.7 将密度独立像素转换为像素 (Converting Density Independent Pixels to Pixels)

此练习的下一个任务是将`EditText`的宽度设置为 200dp。正如“Android Studio 布局器教程”章节所述，在设置用户界面的大小和位置时，最好在运行时将 dp 值转换为像素 (px)。因此，为了将`EditText`的宽度设置为 200dp，需要向类中添加以下代码：

```java
package com.ebookfrenzy.javalayout;

import android.content.res.Resources;

import android.util.TypedValue;

public class MainActivity extends AppCompatActivity {

    private int convertToPx(int value) {

        Resources r = getResources();

        return (int) TypedValue.applyDimension(TypedValue.COMPLEX_UNIT_DIP, value, r.getDisplayMetrics());

    }

    private void configureLayout() {

        Button myButton = new Button(this);

        myButton.setText(getString(R.string.press_me));

        myButton.setBackgroundColor(Color.YELLOW);

        myButton.setId(R.id.myButton);

        EditText myEditText = new EditText(this);

        myEditText.setId(R.id.myEditText);

        int px = convertToPx(200);

        myEditText.setWidth(px);

    }

}
```



编译并再次运行应用，注意`EditText`视图的宽度已经发生了变化，如图 25-3 所示：

![image-VLMPPHUC.jpg](img/image-VLMPPHUC.jpeg)

图 25-3

## 25.8 总结（Summary）

在本章节中创建的示例 Activity 创建了与之前“Android Studio 中的手动 XML 布局设计”章节创建的类似的界面（尽管如此）。本章至少让人们意识到 Android Studio 布局编辑器工具和 XML 资源在很大程度上保护开发者免受创建 Android 用户界面布局的复杂性影响。

然而，在某些情况下，使用 Java 创建用户界面是合理的。

# 26. Android Studio 中使用 Apply Changes 的指南（A Guide to Using Apply Changes in Android Studio）

既然已经涵盖了使用 Android Studio 进行 Android 开发的一些基本概念，现在是介绍 Android Studio 的“应用更改”（Apply Changes）功能的好时了。正如所有经验开发者所知，等待应用编译和运行的每一秒都不如用于编写和完善代码。

## 26.1 引入应用更改

在 Android Studio 的早期版本中，每次需要测试项目更改时，Android Studio 都会重新编译代码、转换为 Dex 格式、生成 APK 包文件，并安装到设备或模拟器上。完成这些步骤后，应用才会启动并准备好测试。即使在快速的开发系统上，这个过程也需要大量时间完成。对于大型应用程序，此过程花费一分钟或更长时间并不常见。

相比之下，“应用更改”允许在设备或模拟器会话运行的同时，将项目中的许多代码和资源更改几乎瞬间反映到应用中。

例如，考虑一个在 Android Studio 中开发已在设备或模拟器上启动的应用。如果对资源设置或方法内的代码进行了更改，“应用更改”将更新后的代码和资源推送到运行的应用中，并动态地“交换”更改。随后，更改将反映在运行的应用中，而无需构建、部署和重新启动整个应用。这通常允许在没有“应用更改”所需的时间内测试更改。

## 26.2 理解应用更改选项

Android Studio 提供了三种对运行的应用应用更改的选项，形式分别为运行应用（Run App）、应用更改并重启活动（Apply Changes and Restart Activity）以及应用代码更改（Apply Code Changes）。这些选项可以总结如下：

- `Run App`：停止当前运行的应用并重启它。如果自上次启动以来项目未发生更改，此选项将重启应用。反之，如果项目已发生更改，Android Studio 将在启动应用之前重新构建并将应用重新安装到设备或模拟器上。
- `Apply Code Changes`：当项目的更改仅涉及修改现有方法体，或者添加了新类或新方法时，可以使用此选项。选中后，更改将应用于运行的应用，而无需重启应用或当前正在运行的活动。然而，当对任何项目资源（如布局文件）进行更改时，无法使用此模式。其他限制还包括删除方法、更改方法签名、重命名类以及其他结构性代码更改。如果项目清单（Manifest）发生了更改，也无法使用此选项。
- `Apply Changes and Restart Activity`：选中后，此模式将动态应用项目内的任何代码或资源更改，并在不重新安装或重启应用的情况下重启活动。与“应用代码更改”选项不同，当项目代码和资源发生更改时可以使用此选项。但是，涉及某些结构性代码更改和清单修改的限制仍然适用。

## 26.3 使用应用更改

当项目已加载 Android Studio 但尚未在设备或模拟器上运行时，可以使用工具栏上的运行按钮（图 26-1 中标记为 A）或调试按钮（B）照常启动它：

![image-VA5Z2YGQ.jpg](img/image-VA5Z2YGQ.jpeg)

图 26-1

应用启动并运行后，将出现停止按钮（图 26-2 中标记为 A），并且“应用更改并重启活动”（B）和“应用代码更改”（C）按钮将变为可用：

![image-BFA65VL2.jpg](img/image-BFA65VL2.jpeg)

图 26-2

如果在选择其中一个“应用更改”按钮时无法应用更改，Android Studio 将显示一条指示失败及其说明的消息。例如，图 26-3 显示了对资源文件进行更改后，选择“应用代码更改”选项时 Android Studio 显示的消息：

![image-ISKOTRWX.jpg](img/image-ISKOTRWX.jpeg)

图 26-3

在这种情况下，解决方案是使用“应用更改并重启活动”选项（此处提供了相关链接）。同样，当尝试应用涉及删除方法的更改时，将出现以下消息：

![image-GDTXWO0Z.jpg](img/image-GDTXWO0Z.jpeg)

图 26-4

在这种情况下，唯一的选项是点击“运行应用”按钮以重新安装并重启应用。作为手动选择正确选项的替代方案，Android Studio 可以配置为自动回退到执行“运行应用”操作。

## 26.4 配置应用更改回退设置

应用更改的回退设置位于 Android Studio 的设置（Settings）对话框中。在设置对话框中，在左侧面板选择`Build, Execution, Deployment`项，然后选择`Deployment`，如图 26-5 所示：

![image-NAAE8670.jpg](img/image-NAAE8670.jpeg)

图 26-5

一旦启用所需的选项，点击`Apply`，然后点击`OK`按钮提交更改并关闭对话框。启用这些默认设置后，Android Studio 将必要时自动重新安装并重启应用。

## 26.5 应用更改教程

启动 Android Studio，从欢迎屏幕上选择新项目（New Project）选项，并在点击下一步按钮之前，在生成的新项目对话框中选择 Basic Views Activity 模板。

在`Name`字段中输入`ApplyChanges`并指定`com.ebookfrenzy.applychanges`为包名。在点击完成按钮之前，将`Minimum API level`设置为`API 26: Android 8.0 (Oreo)`，并将`Language`菜单更改为`Java`。

## 26.6 使用应用代码更改

从点击运行按钮开始并选择模拟器或物理设备作为运行目标。点击运行按钮后，跟踪示例应用出现的时间。

运行后，点击操作按钮（屏幕右下角显示信封图标的按钮）。注意出现了一个 Snackbar 实例，显示文本为“Replace with your own action”，如图 26-6 所示：

![image-8M1V48.jpg](img/image-8M1V48.jpeg)

图 26-6

一旦应用运行，“应用更改”按钮应该已变为可用，表明某些项目更改可以在无需重新安装和重启应用的情况下应用。要查看此效果，编辑`MainActivity.java`文件，找到`onCreate`方法，并修改操作代码，以便在选择操作按钮时显示不同的消息：

```java
binding.fab.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View view) {
        Snackbar.make(view, "Apply Changes is Amazing!", Snackbar.LENGTH_LONG)
            .setAnchorView(R.id.fab)
            .setAction("Action", null).show();
    }
});
```

实现代码更改后，点击“应用代码更改”按钮，注意几秒内出现一条消息指示应用已更新。点击操作按钮，注意新消息现在显示在 Snackbar 中。

## 26.7 使用应用更改并重启活动

任何资源更改都将需要使用“应用更改并重启活动”选项。在 Android Studio 中，选择`app -> res -> layout -> fragment_first.xml`布局文件。在布局编辑器工具的设计模式下，选择默认的 TextView 组件，并在属性工具中将`text`属性更改为“Hello Android”。

在点击`Apply Code Changes`按钮之前，请确保上述“配置应用更改回退设置”中概述的回退选项已关闭。请注意，请求失败是因为此更改涉及项目资源。点击`Apply Changes and Restart Activity`按钮，并验证活动已重启并在`TextView`小部件上显示了新文本。

## 26.8 使用 Run App

正如之前描述的，删除方法需要完全重新安装并重启正在运行的应用。要体验这一点，请编辑`MainActivity.java`文件，并在`onCreate`方法之后添加一个新方法，如下：

```java
public void demoMethod() {
}
```

使用`Apply Code Changes`按钮，并确认更改在不重新安装应用的情况下已应用。

接下来，删除新方法并验证点击两个`Apply Changes`按钮中的任意一个都会导致请求失败。进行此类更改后，运行应用程序的唯一方法是点击`Run App`按钮。

## 26.9 总结

Apply Changes 是 Android Studio 的一项功能，旨在显著加速开发应用时的代码、构建和运行周期。`Apply Changes`功能可以将更新推送到运行中的应用程序，在许多情况下，无需重新安装或重启应用。Apply Changes 根据应用到项目中的修改性质提供了几个不同层次的支持。

# 27. Gradle 版本目录指南

新创建的 Android Studio 项目将由 Android Studio 自动生成的约 80 个文件组成。当你点击`Run`按钮时，Android Studio 使用一个名为`Gradle`的构建系统来生成额外文件、编译源代码、解析库依赖项并创建可安装的应用程序包。构建完成后，项目文件夹将包含约 700 个文件。

本章将解释`Gradle`构建系统如何确定在构建过程中要包含哪些库，以及你如何使用该系统为你的项目添加库依赖项。

## 27.1 库和插件依赖

在之前题为“Android 架构概述”的章节中，我们简要讨论了 Java API 框架及其包含的库。当`Gradle`构建项目时，它需要知道完成构建需要哪些库及其各自的版本号。例如，一个项目可能依赖于版本 2.6.0 的 Room 数据库运行时库（`androidx.room:room-runtime`）。遗憾的是，当我们在项目中编写 Room 数据库代码时，`Gradle`不会自动向构建配置中添加相应的库依赖项。相反，我们必须通过`Gradle`构建文件和版本目录手动添加这些。

## 27.2 项目 Gradle 构建文件

每个 Android Studio 项目都有一个项目级的`Gradle`文件，你可以通过在项目工具窗口导航到`Gradle Scripts -> build.gradle.kts()`来找到它。该文件的主要目的是定义执行整个项目构建工作的插件，其内容通常如下：

```kotlin
plugins {
    alias(libs.plugins.android.application) apply false
}
```

在实践中，只有在少数情况下才需要对此文件进行更改。

## 27.3 模块 Gradle 构建文件

Android Studio 项目由一个或多个模块组成，每个模块都有自己的构建配置和库依赖项。新项目将包含一个模块，其`gradle`构建文件将列在`Gradle Scripts`文件夹中，显示为`build.gradle.kts (Module: app)`，部分内容如下：

```kotlin
plugins {
    alias(libs.plugins.android.application) apply false
}

android {
    .
    .
}

dependencies {
    implementation(libs.androidx.appcompat)
    implementation(libs.material)
    implementation(libs.androidx.activity)
    implementation(libs.androidx.constraintlayout)
    testImplementation(libs.junit)
    androidTestImplementation(libs.androidx.junit)
    androidTestImplementation(libs.androidx.espresso.core)
}
```

`plugins`部分再次包含了构建项目所需的插件，在大多数情况下，它们将与项目级构建文件中声明的插件保持镜像。当某个模块需要其他模块不需要的插件时，会在这里进行声明。

`dependencies`部分包含了模块所依赖的库列表，这些库在成功完成构建时必须被解析。

## 27.4 版本目录文件

早些时候我们提到除了库名称外，依赖项还必须包含库的版本号。然而，你可能已经注意到，到目前为止检查过的任何配置文件都不包含版本信息。这就是版本目录文件大显身手的地方。版本目录可以在项目工具窗口`Gradle Scripts`文件夹中名为`libs.versions.toml`的文件中找到。下面列出了版本目录示例：

```toml
[versions]
agp = "8.7.2"
junit = "4.13.2"
junitVersion = "1.2.1"
espressoCore = "3.6.1"
appcompat = "1.6.1"
material = "1.12.0"
activity = "1.9.3"
constraintlayout = "2.2.0"

[libraries]
material = { group = "com.google.android.material", name = "material", version.ref = "material" }
activity = { group = "androidx.activity", name = "activity", version.ref = "activity" }

[plugins]
android-application = { id = "com.android.application", version.ref = "agp" }

.
.
```

目录被分为标记为`[versions]`、`[libraries]`和`[plugins]`的部分。为了帮助理解，我们将使用`material`库作为示例。版本目录可以在一个名为`libs.versions.toml`的文件中找到，位于项目工具窗口的`Gradle Scripts`文件夹中。在`[libraries]`部分，`material`库被声明如下：

`material = { group = "com.google.android.material", name = "material", version.ref = "material" }`

`activity = { group = "androidx.activity", name = "activity", version.ref = "activity" }`

`[plugins]`

`android-application = { id = "com.android.application", version.ref = "agp" }`

.
.

目录被分为标记为`[versions]`、`[libraries]`和`[plugins]`的部分。为了帮助理解版本目录如何工作，我们将使用`material`库作为示例。在`[libraries]`部分，`material`库被声明如下：

`material = { group = "com.google.android.material", name = "material", version.ref = "material" }`

`group`条目告诉我们库的实际名称是`com.google.android.material`，而`versions.ref`赋值说明了库如何在`[versions]`部分中被引用。在`[versions]`部分，我们发现库被分配了版本 1.12.0：

`material = "1.12.0"`

最后，该库在模块级构建文件中声明如下：

```kotlin
dependencies {
    .
    .
    implementation(libs.material)
}
```

注意在构建文件中引用库的语法是在`[libraries]`目录使用的名称前加上`libs.`。

虽然我们在示例中关注的是库，但插件的语法是相同的。

## 27.5 添加依赖项

你将在多个项目中添加依赖项，在每个情况下，我们都会引导你完成这一过程。作为一个示例，将在之前的虚拟项目中演示 Room 数据库运行时依赖项。首先，我们必须在`libs.versions.toml`版本目录文件的`[libraries]`部分添加以下条目：

```toml
[libraries]

.
.

androidx-roomruntime = { group = "androidx.room", name = "room-runtime", version.ref = "roomRuntime" }
```

接下来，将版本号添加到`[versions]`目录部分：

```toml
[versions]

.
.

roomRuntime = "2.6.1"
```



最后，将该库添加到模块级 gradle 构建文件的`dependencies`部分：

```kotlin
dependencies {
    .
    .
    implementation(libs.androidx.room.runtime)
}
```

另一个例子是`androidx.navigation:navigation-fragment`库。在这种情况下，库的组是`androidx.navigation`，名称是`navigation-fragment`。该库在版本目录中的声明如下：

```toml
[versions]
.
.
navigationFragment = "2.8.3"

[libraries]
.
.
navigation-fragment = { group = "androidx.navigation", name = "navigation-fragment", version.ref = "navigationFragment" }
```

一旦库已添加到目录，gradle 构建文件的依赖项将所示：

```kotlin
dependencies {
    .
    .
    implementation(libs.navigation.fragment)
}
```

## 27.6 库的更新

虽然声明库和插件依赖主要是一项手动任务，但 Android Studio 会为你做的一件事是在有更新版本的库可用时通知你。它通过在你编辑目录文件时高亮版本号来实现这一点。将鼠标指针悬停在高亮的数字上将显示如图 27-1 所示的面板，提供切换到最新版本的选项：

![image-012JMLYE.jpg](img/image-012JMLYE.jpeg)

图 27-1

## 27.7 总结

Android Studio 项目使用`Gradle`构建系统进行构建，该过程涉及多个步骤。其中一个步骤是解析并包含项目成功编译所需的任何库。虽然新创建的项目将包含简单应用所必需的基础库和插件，但更复杂的项目将具有额外的依赖项。这些依赖在模块级的`Gradle`构建文件中声明。为了提供跨项目模块的版本一致性，并提供一个添加新库或更新版本号的单一位置，`Gradle`使用了版本目录文件（version catalog file）。随着你的代码使用的库和插件越来越多，你必须编辑构建文件和目录文件来添加这些依赖项。

## 28. Android 事件处理概述与示例

在之前的章节中已经涵盖了许多关于 Android 应用用户界面设计的内容。然而，一个尚未涵盖的领域涉及用户与用户界面的交互如何触发底层 Activity 执行任务。换句话说，从之前的章节中，我们知道如何创建一个包含按钮视图的界面界面，但不知道当用户触摸它时如何让应用程序内部发生什么。

因此，本章的主要目标是提供 Android 应用中事件处理的概述，并结合一个基于 Android Studio 的示例项目。

### 28.1 理解 Android 事件

Android 事件可以采取多种形式，但通常是响应外部动作而生成的。常见的事件形式（特别是对于平板电脑和智能手机等设备）涉及与触摸屏的某种交互。此类事件属于输入事件类别。

`Android`框架维护了一个事件队列，事件在发生时会被放入队列中。然后事件根据先进先出（FIFO）的原则从队列中移除。在发生输入事件（例如触摸屏幕）的情况下，事件将传递给位于触摸发生屏幕位置的视图。除了事件通知外，视图还会接收到关于事件性质的一系列信息（取决于事件类型），例如用户手指与屏幕接触点的坐标。

为了处理已传递的事件，视图必须备有一个事件监听器。源自所有用户界面组件的`View`类包含了一系列事件监听器接口，每个接口都包含一个回调方法的抽象声明。为了能够响应特定类型的事件，视图必须注册相应的事件监听器并实现相应的回调。例如，如果按钮要响应点击事件（等同于用户触摸并释放按钮视图，就像点击物理按钮一样），它必须同时注册`View.onClickListener`事件监听器（通过调用目标视图的`setOnClickListener()`方法）并实现相应的`onClick()`回调方法。如果在按钮视图位置的屏幕上检测到“点击”事件，`Android`框架将在该事件从事件队列中移除时调用该视图的`onClick()`方法。当然，任何在响应按钮点击时应执行的任务或其他方法都应该在`onClick()`回调方法的实现内部完成。

### 28.2 使用`android:onClick`资源

在更详细探索事件监听器之前，值得注意的是，当仅需在用户在界面上“点击”按钮视图时调用回调方法时，提供了一个快捷方法。考虑一个包含名为`button1`的按钮视图的用户界面布局，其要求是当用户触摸按钮时，调用 Activity 类中声明的名为`buttonClick()`方法。实现此行为仅需编写`buttonClick()`方法（其接收触发点击事件的视图引用作为参数）并在 XML 文件中按钮视图的声明中添加一行即可。例如：

```xml
android:id="@+id/button1"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:onClick="buttonClick"
android:text="Click me" />
```

这提供了一种捕捉点击事件的简单方法。然而，它没有提供事件处理程序所提供的范围选项，而这是本章其余部分的主题。正如后续章节概述，`onClick`属性在涉及 Fragment 的布局中也有局限性。在 Android Studio 布局编辑器中工作时，当设备屏幕布局中选择合适的视图类型时，可以在属性（Attributes）面板中找到并配置`onClick`属性。

### 28.3 事件监听器和回调方法

在本章稍后概述的示例 Activity 中，将详细介绍注册事件监听器和实现回调方法的步骤。但在在此之前，值得花些时间概述`Android`框架中可用的事件监听器以及每个监听器相关的回调方法。

- `onClickListener` – 用于检测点击样式事件，即用户触摸并释放被视图占据的设备显示区域。对应`onClick()`回调方法，该方法将接收事件的视图引用作为参数传递。

- `onLongClickListener` – 用于检测用户长时间在视图上保持触摸。对应`onLongClick()`回调方法，该方法将接收事件的视图作为参数传递。

- `onTouchListener` – 用于检测与触摸屏的任何接触，包括单次或多点触摸和手势动作。相应的`onTouch()`回调将在“Android 触摸和多点事件处理”章节中详细介绍。回调方法将接收事件的视图和一个`MotionEvent`对象作为参数传递。

- `onCreateContextMenuListener` – 监听由于长按产生的上下文菜单创建。对应`onCreateContextMenu()`回调方法。回调接收菜单、接收事件的视图和一个菜单上下文对象。

- `onFocusChangeListener` – 检测由于与滚轮或导航键的交互导致焦点离开当前视图。对应`onFocusChange()`回调方法，该方法将接收事件的视图和一个指示是否获得或丢失焦点的布尔值。

- `onKeyListener` – 用于检测当视图拥有焦点时按了设备上的键。对应`onKey()`回调方法。它将接收事件的视图、按按物理键的`KeyCode`和一个`KeyEvent`对象作为参数。

### 28.4 事件处理示例

在本章的剩余部分中，我们将创建一个 Android Studio 项目，旨在演示如何实现事件监听器和相应的回调方法，以检测用户何时点击了按钮。回调方法中的代码将更新文本视图以指示事件已处理。

从欢迎界面选择`New Project`选项，在弹出的新项目对话框中，在点击`Next`按钮之前选择`Empty Views Activity`模板。

在`Name`字段中输入`EventExample`，并指定`com.ebookfrenzy.eventexample`为包名。在点击`Finish`按钮之前，将`Minimum API level`设置为`API 26: Android 8.0 (Oreo)`，并将`Language`菜单设置为`Java`。按照第 12.8 节“迁移项目以使用 View Binding”中列出的步骤，将项目转换为使用 view binding。

### 28.5 设计用户界面

本示例中`MainActivity`类的界面布局将包含一个`ConstraintLayout`、一个`Button`和一个`TextView`，如图 28-1 所示。

![image-C7XMRVAI.jpg](img/image-C7XMRVAI.jpeg)

图 28-1

找到并选择 Android Studio 创建的`activity_main.xml`文件（位于 Project 工具窗口的`app -> res -> layouts`下），并双击它将其加载到 Layout Editor 工具中。

确保已启用`Autoconnect`，然后从调色板拖入一个`Button`控件并移动它，使其位于布局的水平居中并在现有`TextView`控件下方。当位置正确时，将控件释放到目标位置，以便 autoconnect 系统添加相应的约束条件。

选择“Hello World!”`TextView`控件，并使用 Attributes（属性）面板将`ID`设置为`statusText`。重复此步骤将`Button`控件的`ID`改为`myButton`。

点击布局编辑器工具栏上的`Infer Constraints`按钮以添加任何缺失的约束条件。

选中`Button`控件的情况下，使用 Attributes 面板将`text`属性设置为`Press Me`。将按钮上的文本字符串提取到名为`press_me`的资源中。

完成用户界面布局后，下一步是注册事件监听器和回调方法。

### 28.6 事件监听器和回调方法

对于本示例，需要为`myButton`视图注册一个`onClickListener`。这是通过调用按钮视图的`setOnClickListener()`方法，并将一个新的`onClickListener`对象作为参数传递，同时实现`onClick()`回调方法来实现。由于此任务只需要在创建 创建时执行，因此良好的位置是`MainActivity`类的`onCreate()`方法。

如果`MainActivity.java`文件已在编辑器会话中打开，点击编辑器面板中的标签页选择它。或者，在 Project 工具窗口中导航到`(app -> kotlin+java -> com.ebookfrenzy.eventexample -> MainActivity)`找到它，并双击将其加载到代码编辑器中。加载后，找到模板`onCreate()`方法并修改它以获取按钮视图的引用、注册事件监听器并实现`onClick()`回调方法：

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

        .

        .

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

上述代码已经在按钮上注册了事件监听器并实现了`onClick()`方法。然而，如果此时运行应用程序，将没有任何迹象表明安装在按钮上的事件监听器正在工作，因为目前`onClick()`回调方法的体内尚未实现任何代码。本示例的目标是在点击按钮时在`TextView`上显示消息，因此需要进行进一步的代码更改：

```java
@Override

protected void onCreate(Bundle savedInstanceState) {

    .

    .

    binding.myButton.setOnClickListener(

        new Button.OnClickListener() {

            public void onClick(View v) {

                binding.statusText.setText("Button clicked");

            }

        }

    );

}
```

在 AVD 模拟器或物理 Android 设备上编译并运行应用程序以完成此教程阶段。在触摸并释放按钮视图（即“点击”）时，文本视图应该更改为显示“Button clicked”文本。

## 28.7get 事件

对视图上标准点击（区别于长按）的检测是事件处理的一个简单案例。现在示例将扩展以包含对长按事件的检测，长按事件发生在用户点击并按住屏幕上的视图时，通过这涵盖了事件消费的主题。

考虑本章上述部分`onClick()`方法的代码。该回调被声明为`void`，因此在执行完毕后它不会向 Android 框架返回任何值。

另一方面，分配给`onLongClickListener`的代码需要向 Android 框架返回一个`Boolean`值。此返回值的目的是向 Android 运行时指示回调是否已消费该事件。如果回调返回`true`值，框架将丢弃该事件。相反，如果回调返回`false`值，则 Android 框架将认为事件仍然有效。

正如许多编程概念一样，这通过一个示例进行演示。第一步是在 activity 中为按钮添加长按事件监听器和回调方法：

```java
@Override

protected void onCreate(Bundle savedInstanceState) {

    .

    .

    binding.myButton.setOnLongClickListener(

        new Button.OnLongClickListener() {

            public boolean onLongClick(View v) {

                binding.statusText.setText("Long click");

                return true;

            }

        }

    );

}
```

当检测到长按时，`onLongClick()`回调将在文本视图上显示“Long click”。然而，注意回调返回了`true`值以指示它已消费该事件。运行应用程序并按住按钮视图直到出现“Long click”文本。释放按钮时，文本视图显示“Long click”文本，表明 onClick 监听器未调用。

接下来，修改代码使`onLongClickListener`现在返回`false`值：

```java
button.setOnLongClickListener(

    new Button.OnLongClickListener() {

        public boolean onLongClick(View v) {

            TextView myTextView = findViewById(R.id.myTextView);

            myTextView.setText("Long click");

            return false;

        }

    }

);
```




再次编译并运行应用程序，执行长按操作直到长按消息出现。然而，这次释放按钮时，注意 `onClick` 监听器也被触发了，且文本变为“Button clicked”。这是因为 `onLongClickListener` 代码返回的 `false` 值指示 Android 框架事件未被消费，可以传递给下一个监听器。

### 28.8 总结

如果界面包含的视图不对用户交互做出任何反应，那么用户界面就没有任何实际用途。Android 通过事件监听器和回调方法的概念桥起了用户界面与应用程序后端代码之间的差距。Android `View` 类定义了一组注册在视图对象上的事件监听器。每个事件监听器都关联了一个回调方法。

当用户界面中的视图（view）上发生事件时，该事件会被放入事件队列，并由 Android 运行时按照先进先出（FIFO）原则进行处理。如果发生事件的视图注册了与事件类型匹配的监听器，就会调用相应的回调方法。该代码在返回之前会执行活动（activity）所需的任何任务。某些回调方法被要求返回一个 `Boolean` 值，以指示该事件是需要传递给注册在视图上的其他事件监听器，还是被系统丢弃。

现在已经涵盖了事件处理的基础知识，下一章将探索触摸事件，并特别强调多点触摸的处理。

# 29. Android 触摸与多点触摸事件处理

大多数基于 Android 设备使用触摸屏作为用户与设备之间的主要界面。上一章介绍了屏幕上的触摸操作如何转换为运行中的 Android 应用程序中的动作。然而，触摸事件的处理远比对视图对象上的单指点击做出响应复杂得多。例如，大多数 Android 设备可以同时检测到多个触摸点。触摸操作也不局限于设备显示器上的一点。当用户在屏幕表面滑动一个或多个接触点时，触摸操作可以是动态的。

应用程序还可以将触摸解释为手势。例如，水平滑动通常用于翻页电子书的页面，或者捏合动作（pinching motion）如何可以放大或缩小屏幕上显示的图像。

本章将解释涉及运动的触摸处理，并探索拦截多个并发触摸的概念。识别不同手势的主题将在下一章介绍。

## 29.1 拦截触摸事件

视图对象可以通过注册 `onTouchListener` 事件监听器并实现相应的 `onTouch()` 回调方法来拦截触摸事件。例如，以下代码确保了任何在名为 `myLayout` 的 `ConstraintLayout` 视图实例上的触摸都会导致调用 `onTouch()` 方法：

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

如代码示例所示，`onTouch()` 回调要求返回一个 `Boolean` 值，告知 Android 运行时系统是否应该将事件传递给注册在同一视图上的其他事件监听器或将其丢弃。该方法传递了触发事件的视图引用以及一个类型为 `MotionEvent` 的对象。

## 29.2 MotionEvent 对象

传递给 `onTouch()` 回调方法的 `MotionEvent` 对象是获取事件信息的关键。对象中的信息包括触摸在视图中的位置以及执行的动作类型。`MotionEvent` 对象也是处理多点触摸的关键。

## 29.3 理解触摸动作

触摸事件处理的一个重要方面是识别用户执行的动作类型。可以通过调用传递给 `onTouch()` 回调方法的 `MotionEvent` 对象的 `getActionMasked()` 方法获取与事件关联的动作类型。当视图上发生第一次触摸时，`MotionEvent` 对象将包含动作类型 `ACTION_DOWN` 以及以及触摸的坐标。当该触摸从屏幕上抬起时，会产生一个 `ACTION_UP` 事件。在 `ACTION_DOWN` 和 `ACTION_UP` 事件之间的任何触摸运动都将由 `ACTION_MOVE` 事件表示。

当在视图上同时进行多次触摸时，这些触摸被称为指针（pointers）。在多点触摸的场景下，指针分别以 `ACTION_POINTER_DOWN` 和 `ACTION_POINTER_UP` 类型的事件动作开始和结束。要识别触发事件的指针索引，必须调用 `MotionEvent` 对象的 `getActionIndex()` 回调方法。

## 29.4 处理多点触摸

标题为“Android 事件处理概述与示例”的章节开始在单点触摸事件的狭窄范围内探索了事件处理。在实践中，大多数 Android 设备可以响应多个连续的触摸（尽管需要注意的是，可以检测到的同时触摸次数取决于设备）。

如前所述，在多点触摸的情况下，每次触摸都被 Android 框架视为一个指针。每个指针反过来通过一个索引值被引用并被分配一个 ID。当前的指针数量可以通过调用当前 `MotionEvent` 对象的 `getPointerCount()` 方法获取。当前指针列表中特定索引处的指针 ID 可以通过调用 `MotionEvent.getPointerId()` 方法获取。例如，以下代码段获取了指针计数以及索引为 0 的指针的 ID：

```java
public boolean onTouch(View v, MotionEvent m) {
    int pointerCount = m.getPointerCount();
    int pointerId = m.getPointerId(0);
    return true;
}
```

注意，当 `onTouch` 监听器被触发时，指针计数将始终大于或等于 1（因为回调的触发意味着至少发生了一次触摸）。

视图上的触摸，特别是涉及跨屏幕运动的触摸，会在接触点从屏幕抬起之前产生一系列事件。应用程序可能需要在多个触摸事件期间跟踪单个触摸。虽然特定触摸手势的 ID 不会从一个事件变到另一个事件，但重要的是要记住，随着其他触摸事件的到来和离开，索引值会发生变化。在跨多个事件处理触摸手势时，必须使用 ID 值作为触摸引用。当调用需要索引值的方法时，应该通过调用 `MotionEvent` 对象的 `findPointerIndex()` 方法将 ID 转换为相应的索引值。

## 29.5 多点触摸应用程序示例

在本章剩余部分创建的示例应用程序将跟踪跨布局视图移动的两个触摸手势。当每个触摸的事件触发时，每个触摸的坐标、索引和 ID 将显示在屏幕上。

拖入第二个 `TextView` 小控件，并对其进行定位和约束，使其与第一个小控件之间保持 32dp 的间距：

![image-U9E4AE8D.jpg](img/image-U9E4AE8D.jpeg)

图 29-2

使用 `Attributes` 属性窗口，将 `TextView` 小控件的 ID 分别更改为 `textView1` 和 `textView2`。将控件上显示的文本更改为“Touch One Status”和“Touch Two Status”，并使用 `Layout Editor` 右角的警告按钮将字符串提取到资源文件中。

## 29.7 实现触摸事件监听器

为了接收触摸事件通知，有必要在 `MainActivity` 类的 `onCreate()` 方法中对布局视图注册触摸监听器。从 Android Studio 编辑器面板中选择 `MainActivity.java` 标签页以显示源代码。在 `onCreate()` 方法中，添加代码来注册触摸监听器并实现代码，在此情况下，该代码将调用一个名为 `handleTouch()` 的第二个方法，并向其传递 `MotionEvent` 对象：

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
        .
        .
        setContentView(view);

        binding.main.setOnTouchListener(
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

当我们在设计用户界面时，父布局 `ConstraintLayout` 没有分配允许我们通过视图绑定机制访问它的 ID。由于此布局组件是 UI 布局层次结构中的最顶层组件，我们能够使用上述代码中的根绑定属性来引用它。

在测试应用程序之前，最后一个任务是实现由监听器调用的 `handleTouch()` 方法。该方法的代码如下：

```java
void handleTouch(MotionEvent m) {
    int pointerCount = m.getPointerCount();

    for (int i = 0; i < pointerCount; i++) {
        int x = (int) m.getX(i);
        int y = (int) m.getY(i);
        int id = m.getPointerId(i);
        int action = m.getActionMasked();
        int actionIndex = m.getActionIndex();
        String actionString;

        switch (action) {
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

在编译和运行应用程序之前，值得花时间系统地梳理这段代码，以突出所执行的任务。

代码首先获取用户界面中两个 `TextView` 对象的引用，并识别当前视图上有多少个活动指针：

```java
TextView textView1 = findViewById(R.id.textView1);
TextView textView2 = findViewById(R.id.textView2);
int pointerCount = m.getPointerCount();
```

接下来，变量 `pointerCount` 启动了一个 `for` 循环，每个活动指针执行任务。循环的前几行获取了触摸的 `X` 和 `Y` 坐标，以及相应的事件 ID、动作类型和动作索引。最后，声明了一个字符串变量：

```java
for (int i = 0; i < pointerCount; i++) {
    int x = (int) m.getX(i);
    int y = (int) m.getY(i);
    int id = m.getPointerId(i);
    int action = m.getActionMasked();
    int actionIndex = m.getActionIndex();
    String actionString;
```

由于动作类型等于整数值，因此使用 `switch` 语句将动作类型转换为更有意义的字符串值，并存储在之前声明的 `actionString` 变量中：

```java
switch (action) {
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

最后，通过 `actionString`、索引、ID、X 和 Y 构造了一个触摸状态字符串。如果 `id` 等于 0，则设置 `textView1`，否则设置 `textView2`：

```java
String touchStatus = "Action: " + actionString + " Index: " + actionIndex + " ID: " + id + " X: " + x + " Y: " + y;

if (id == 0)
    binding.textView1.setText(touchStatus);
else
    binding.textView2.setText(touchStatus);
```

## 29.8 运行应用程序

在编译和运行应用程序之前，值得花时间系统地梳理这段代码，以突出所执行的任务。代码首先获取用户界面中两个 `TextView` 对象的引用，并识别当前视图上有多少个活动指针：

```java
TextView textView1 = findViewById(R.id.textView1);
TextView textView2 = findViewById(R.id.textView2);
int pointerCount = m.getPointerCount();
```

接下来，变量 `pointerCount` 启动了一个 `for` 循环，每个活动指针执行任务。循环的前几行获取了触摸的 `X` 和 `Y` 坐标，以及相应的事件 ID、动作类型和动作索引。最后，声明了一个字符串变量：

```java
for (int i = 0; i < pointerCount; i++) {
    int x = (int) m.getX(i);
    int y = (int) m.getY(i);
    int id = m.getPointerId(i);
    int action = m.getActionMasked();
    int actionIndex = m.getActionIndex();
    String actionString;
```

由于动作类型等于整数值，因此使用 `switch` 语句将动作类型转换为更有意义的字符串值，并存储在之前声明的 `actionString` 变量中：

```java



## 29.9 总结

Activity 通过注册触摸监听器并实现`onTouch()`回调方法来接收触摸事件通知，该方法在调用时会传递`MotionEvent`对象。该对象包含了有关触摸的信息，例如事件类型、坐标以及当前接触点的数量。当涉及多个触摸时，每个接触点被称为一个指针，每个指针都被分配了一个索引和一个 ID。虽然指针的索引可能会随事件发生变化，但 ID 在触摸结束之前将保持不变。

当用户与 Android 设备的屏幕进行交互时，系统会调用当前活跃应用程序的`onTouchEvent()`方法，并传递包含用户接触屏幕数据的`MotionEvent`对象。这些数据可以被解析，用以识别屏幕上的动作是否匹配常见的手势（如点击或滑动）。通过使用`GestureDetector`类，可以用极少的编程工作实现这一目标。该类设计用于接收应用程序的运动事件信息，并根据检测到的（如果有的话）常见手势类型触发方法调用。

检测常见手势的基本步骤如下：

1. 声明一个实现`GestureDetector.OnGestureListener`接口的类，包括所需的`onFling()`、`onDown()`、`onScroll()`、`onShowPress()`、`onSingleTapUp()`和`onLongPress()`回调方法。注意，这可以是一个全新的类，也可以是一个嵌套的 Activity 类。如果需要检测双击手势，该类还必须实现`GestureDetector.OnDoubleTapListener`接口并包含相应的`onDoubleTap()`方法。
2. 创建 Android `GestureDetector`类的实例，并将步骤 1 中创建的类实例作为参数传递。
3. 可选调用`GestureDetector`实例的`setOnDoubleTapListener()`方法，如果需要则启用双击检测。
4. 在嵌套的 Activity 中实现`onTouchEvent()`回调方法，该方法反过来必须调用`GestureDetector`实例的`onTouchEvent()`方法并将运动事件对象作为参数传递给该方法。

一旦实现，应用程序代码中的一组方法，当检测到特定类型的手势时就会调用这些方法。这些方法内部的代码可以被用于执行响应相应手势需要执行的任何任务。

在本章的剩余部分中，我们将创建一个示例项目，旨在将上述步骤付诸实践。

## 30.2 创建示例手势检测项目

此项目旨在检测`GestureDetector`类目前支持的所有常见手势，并向用户显示状态信息，以指示检测到的手势类型。

从欢迎界面选择“New Project”（新建项目）选项，在出现的新项目对话框中，点击“Next”（下一步）按钮之前选择“Empty Views Activity”模板。

在`Name`字段中输入`CommonGestures`，并指定`com.ebookfrenzy.commongestures`为包名。在点击“Finish”（完成）按钮之前，将 Minimum API level 设置更改为`API 26: Android 8.0 (Oreo)`，并将 Language 菜单改为`Java`。

按照第 12.8 节“Migrating a Project to View Binding”中的概述，调整项目以使用 view binding。

一旦创建新项目，在 Project 工具窗口中导航到`app -> res -> layout -> activity_main.xml`文件并双击它，将其加载到 Layout Editor 工具中。

在 Layout Editor 工具中，选择“Hello, World!” `TextView`组件，并在 Attributes 工具窗口中输入`gestureStatusText`作为 ID。最后，将`textSize`设置为`20sp`并启用粗体`textStyle`：

![image-LU2GODXX.jpg](img/image-LU2GODXX.jpeg)

图 30-1

## 30.3 实现监听器类

如前所述，有必要创建一个实现`GestureDetector.OnGestureListener`接口的类，如果需要双击检测，则还需要实现`GestureDetector.OnDoubleTapListener`接口。虽然这可以是一个全新的类，但在当前 Activity 类中实现也是完全有效的。因此，我们将修改`MainActivity`类以便在此示例实现这些监听器接口。编辑`MainActivity.java`文件，使其内容如下：

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

声明类实现了监听器接口意味着类中也必须实现相应的方法：

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

public boolean onDoubleTap(MotionEvent event) {

    binding.gestureStatusText.setText("onDoubleTap");

    return true;

}

@Override

public boolean onTapEvent(MotionEvent event) {

    binding.gestureStatusText.setText("onTapEvent");

    return true;

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

注意这些许多方法返回了`true`。这告诉 Android 框架该方法已处理了事件，不需要传递给下一个事件处理器。

## 30.4 创建 GestureDetector 实例

在 Activity 类实现了监听器接口后，下一步是创建`GestureDetector`实例。由于这只需要在创建时执行一次，最佳位置是`onCreate()`方法。由于我们还想检测双击，代码还需要调用`GestureDetector`实例的`setOnDoubleTapListener()`方法：

```java
.

.

public class MainActivity extends AppCompatActivity

implements GestureDetector.OnGestureListener,

GestureDetector.OnDoubleTapListener {

    private ActivityMainBinding binding;

    private GestureDetector gDetector;

    @Override

    protected void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);

        .

.

        this.gDetector = new GestureDetector(this,this);

        gDetector.setOnDoubleTapListener(this);

    }

.

.

}
```

## 30.5 实现 onTouchEvent() 方法

如果此时编译并运行应用程序，在设备上执行手势都不会发生任何事情。这是因为还没有添加代码来拦截事件并将其传递给`GestureDetector`实例。为了实现这一点，有必要在 Activity 类中重写`onTouchEvent()`方法，并使其调用`GestureDetector`实例的`onTouchEvent()`方法。在`MainActivity.java`文件中，因此实现该方法如下：

```java
@Override

public boolean onTouchEvent(MotionEvent event) {

    this.gDetector.onTouchEvent(event);

    // 确保调用类的实现

    return super.onTouchEvent(event);

}
```

最后，通过`actionString`、索引、ID、X 和 Y 构造了一个触摸状态字符串。`ID`值随后用于判断字符串应该显示在第一个还是第二个`TextView`上：

```java
String touchStatus = "Action: " + actionString + " Index: " + actionIndex + " ID: " + id + " X: " + x + " Y: " + y;

if (id == 0)

    binding.textView1.setText(touchStatus);

else

    binding.textView2.setText(touchStatus);
```

对于`switch (action)`语句，其结构如下：

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




## 30.6 测试应用程序

在物理 Android 设备或 AVD 模拟器上编译并运行应用程序。启动后，尝试滑动、按下、滚动动作以及双击和单击。注意文本视图会更新以反映事件，如图 30-2 所示：

![image-DFIKRI2Y.jpg](img/image-DFIKRI2Y.jpeg)

图 30-2

## 30.7 总结

用户与设备触摸屏器之间的任何物理接触都可以视为一种“手势”。由于缺乏传统计算机系统的物理键盘和鼠标指针，手势被广泛用作用户与应用程序之间交互的方法。虽然一个手势可以包含任何序列的动作，但有一套广泛使用的手势集，触摸屏设备的用户对它们已经非常熟悉。这些所谓的“常用手势”中的一些，可以通过 `Android Gesture Detector` 类在应用程序中轻松检测到。在本章中，我们已经从理论和通过示例项目实现两个方面概述了该技术的使用。

在本章涵盖了常用手势之后，下一章将介绍检测更广泛的手势类型，包括设计和检测您自定义手势的能力。

# 31. 在 Android 上实现自定义手势和双缩放识别

上一章涵盖了在 Android 应用程序内部检测所谓的“常用手势”。然而，在实践中，一个手势在理论上可能涉及 Android 设备屏幕上几乎任何序列的触摸动作。为此，`Android SDK` 允许应用程序开发者定义几乎任何性质的自定义手势，并在用户执行时触发事件。这是一个多阶段的过程，其细节是本章的主题。

## 31.1 Android Gesture Builder 应用程序

`Android SDK` 允许开发者设计自定义手势，这些手势存储在与 Android 应用程序包捆绑的手势文件中。这些自定义手势文件可以通过 `Gesture Builder` 应用程序创建。创建手势文件涉及在物理设备或模拟器上启动 `Gesture Builder` 应用程序，并在灰色画布上“绘制”应用程序需要检测的手势。一旦设计好手势，就可以下载包含手势数据的文件并添加到应用程序项目中。在应用程序代码中，该文件被加载到 `GestureLibrary` 类的实例中，该实例可用于搜索用户在设备屏幕上执行的任何手势的匹配。

## 31.2 GestureOverlayView 类

为了方便在应用程序内检测手势，`Android SDK` 提供了 `GestureOverlayView` 类。这个透明视图可以放在用户界面的其他视图之上以检测手势。

## 31.3 检测手势

手势的检测是通过加载使用 `Gesture Builder` 应用创建的手势文件，然后在 `GestureOverlayView` 类的实例上注册 `GesturePerformedListener` 事件监听器来实现的。然后声明封装类实现 `OnGesturePerformedListener` 接口以及该接口所需的 `onGesturePerformed` 回调方法。如果监听器检测到手势，Android 运行时系统将触发调用 `onGesturePerformed` 回调。

## 31.4 识别特定手势

当检测到手势时，会调用 `onGesturePerformed` 回调方法，并将检测到手势的 `GestureOverlayView` 对象的引用以及包含手势信息的 `Gesture` 对象作为参数。

通过访问 `Gesture` 对象，`GestureLibrary` 可以将检测到的手势与之前加载到应用程序的手势文件中所包含的手势进行比较。`GestureLibrary` 通过计算每个手势的预测分，报告用户执行的手势与手势文件中的条目匹配的概率。预测分为 `1.0` 或更高通常被接受为文件中存储的手势与用户在设备屏幕上执行的手势之间的良好匹配。

## 31.5 安装并运行 Gesture Builder 应用程序

创建手势文件最简单的方法是使用允许捕获和保存手势动作的应用程序。虽然 Google 最初提供了一个用于此目的的应用程序，但它在较新版本的 Android 上已没有得到充分维护。幸运的是，可以通过 `Gesture Builder Tool` 应用程序提供替代方案，该程序可以在 Google Play 商店的以下 URL 获取：

`https://play.google.com/store/apps/details?id=migueldp.runeforge`

## 31.6 创建手势文件

一旦 `Gesture Builder Tool` 加载，点击设备屏幕底部的 `Create New Gesture` 按钮，并在灰色画布上使用圆周运动“绘制”手势，如图 31-1 所示。假设手势显示正确（由设备屏幕上的黄色线条表示），点击保存按钮将手势添加到手势文件中，在提示输入名称时输入“Circle Gesture”：

![image-26K07KT6.jpg](img/image-26K07KT6.jpeg)

图 31-1

手势保存后，`Gesture Builder Tool` 将显示当前定义的手势列表，该列表将仅包含新的 Circle Gesture。

## 31.7 创建示例项目

从欢迎界面选择 `New Project` 选项，在生成的新项目对话框中，在点击 `Next` 按钮之前选择 `Empty Views Activity` 模板。

在 `Name` 字段中输入 `CustomGestures`，并指定 `com.ebookfrenzy.customgestures` 为包名。在点击 `Finish` 按钮之前，将 `Minimum API level` 设置为 `API 26: Android 8.0 (Oreo)`，并将 `Language` 菜单改为 `Java`。按照第 12.8 节迁移项目到 View Binding 的所述调整项目使用 view binding。

## 31.8 从 SD 卡中提取手势文件

由于每个手势都是在 `Gesture Builder` 应用程序中创建的，它们被添加到名为 `gesture.txt` 的文件中，该文件位于运行应用程序的模拟器或设备的存储中。然而，在此文件添加到 Android Studio 项目之前，必须将其从设备存储中拷贝出来。这通过 Android Studio 的 `Device File Explorer` 工具窗口最容易实现。使用 `View -> Tool Windows -> Device File Explorer` 显示该工具。显示后，从下拉菜单中选择创建手势文件的设备或模拟器，然后导航到以下文件夹：

`/storage/emulated/0/Android/data/migueldp.runeforge/files/gestures.txt`

在此文件夹中找到 `gesture.txt` 文件，右键点击它，选择 `Save As…` 选项，将其保存到临时位置并命名为 `gestures`。

![image-9E6FPECS.jpg](img/image-9E6FPECS.jpeg)

图 31-2

一旦手势文件创建并从设备存储提取，就可以作为资源文件添加到 Android Studio 项目。

## 31.9 将手势文件添加到项目

在 Android Studio 项目窗口中，找到并右键点击 `res` 文件夹（位于 `app` 下），从生成的菜单中选择 `New -> Directory`。在 `New Directory` 对话框中输入 `raw` 作为文件夹名并按回车键。使用适用于您操作系统的文件管理器，找到之前从设备存储提取的手势文件，将其复制并粘贴到项目窗口中新的 `raw` 文件夹中。

## 31.10 设计用户界面

此示例应用程序需要由 `ConstraintLayout` 视图组成，在其上方叠加 `GestureOverlayView` 以拦截用户执行的任何手势。找到 `app -> res -> layout -> activity_main.xml` 文件，双击它将其加载到 Layout Editor 工具中，选择并删除默认的 `TextView` 小部件。

切换布局编辑器的 Code 模式并修改 XML 使其如下：

```xml
xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context=".MainActivity">

    android:id="@+id/gOverlay"
    android:layout_width="0dp"
    android:layout_height="0dp"
    app:layout_constraintBottom_toBottomOf="parent"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent" />
```

## 31.11 加载手势文件

既然手势文件已经添加到项目中，下一步是编写一些代码在 Activity 启动时加载该文件。对于本项目，实现此目的的代码将如下所示添加到 `MainActivity` 类中：

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

除了一些必要的导入指令外，上述代码还创建了一个名为 `gLibrary` 的 `GestureLibrary` 实例，然后将位于 `raw` 资源文件夹的手势文件内容加载到其中。Activity 类也经过修改以实现 `OnGesturePerformedListener` 接口，这需要添加 `onGesturePerformed` 回调方法（该方法将在本章节之后创建）。

## 31.12 注册事件监听器

为了让 Activity 接收到用户在屏幕上执行手势的通知，必须按照如下代码段所示，在 `gLayout` 视图上注册 `OnGesturePerformedListener` 事件监听器：

```java
private void gestureSetup() {
    gLibrary = GestureLibraries.fromRawResource(this, R.raw.gestures);

    if (!gLibrary.load()) {
        finish();
    }

    binding.gOverlay.addOnGesturePerformedListener(this);
}
```

## 31.13 实现 onGesturePerformed 方法

在应用程序进行首次测试之前，剩下的工作就是实现 `onGesturePerformed` 回调方法。当在 `GestureOverlayView` 实例上执行手势时，就会调用此方法：

```java
package com.ebookfrenzy.customgestures;

import android.gesture.Prediction;
import android.widget.Toast;
import android.gesture.Gesture;
import java.util.ArrayList;

public class MainActivity extends AppCompatActivity
        implements OnGesturePerformedListener {

    private GestureLibrary gLibrary;

    public void onGesturePerformed(
            GestureOverlayView overlay,
            Gesture gesture) {

        ArrayList predictions = gLibrary.recognize(gesture);

        if (!predictions.isEmpty()
                && predictions.get(0).score > 1.0) {

            String action = predictions.get(0).name;

            Toast.makeText(
                    this,
                    action,
                    Toast.LENGTH_SHORT
            ).show();
        }
    }
}
```

当 Android 运行时在手势覆盖层视图对象检测到手势时，就会调用 `onGesturePerformed` 方法。作为参数传递的是检测到手势的 `GestureOverlayView` 对象的引用，以及一个 `Gesture` 类型的对象。`Gesture` 类用于持有定义特定手势的信息（本质上是屏幕上描述组成手势的笔触路径的一系列定时点）。

`Gesture` 对象被传递给 `gLibrary` 实例的 `recognize()` 方法，以便将当前手势与从手势文件中加载的每个手势进行比较。一旦任务完成，`recognize()` 方法将返回一个 `ArrayList` 对象，其中包含每次比较执行对应的 `Prediction` 对象。列表按照从最佳匹配（数组位置 0）到最差匹配的顺序排序。每个预测对象中包含了手势文件中对应手势的名称，以及一个指示其与当前手势匹配密切程度的预测评分。

因此，上述方法中的代码获取位置 0 处的预测（最接近的匹配），确保其评分大于 `1.0`，然后显示一个 `Toast` 消息（一种设计用于向用户显示弹出通知的 Android 类），显示匹配手势的名称。

## 31.14 测试应用程序

在模拟器或物理 Android 设备上构建并运行应用程序，然后在显示器上执行圆圈手势。执行时，应该出现包含检测到的手势名称的 toast 通知。请注意，当手势被识别时，会在显示器上用亮黄色线条勾勒，而覆盖层不确定的手势则显示为浅黄色线条。虽然这在开发期间有用，但对于实际应用来说可能并不理想。因此，仍然有一些更多的配置工作需要完成。

## 31.15 配置 GestureOverlayView

默认情况下，`GestureOverlayView` 配置为在手势期间显示黄色线条。绘制识别和未识别手势的颜色可以通过 `android:gestureColor` 和 `android:uncertainGestureColor` 属性来定义。例如，为了隐藏手势线条，按如下修改项目中的 `activity_main.xml` 文件：

```xml
android:id="@+id/gOverlay"
android:layout_width="0dp"
android:layout_height="0dp"
app:layout_constraintBottom_toBottomOf="parent"
app:layout_constraintEnd_toEndOf="parent"
app:layout_constraintStart_toStartOf="parent"
app:layout_constraintTop_toTopOf="parent"
android:gestureColor="#000000"
android:uncertainGestureColor="#000000"
```





重新运行应用程序时，手势应该是不可见的（因为它们绘制在`ConstraintLayout`的白色背景上）。

## 31.16 拦截手势

如前所述，`GestureOverlayView` 是位于其他视图之上的透明覆盖层。这产生了一个问题：当手势被识别时，覆盖层拦截的事件是否应该传递给底层视图。这通过`GestureOverlayView`实例的`android:eventsInterceptionEnabled`属性来控制。设置为`true`时，手势事件将不会传递给底层视图。当手势在配置为响应特定手势的视图上执行时，这是一个特别有用的设置。将此属性设置为`true`可以避免手势同时被解释为底层视图向特定方向滚动的指令。

在离开通用的触摸处理和特定的手势识别之前，本章的最后一个主题是处理缩放手势。虽然可以使用本章之前章节概述的步骤创建并检测各种手势，但实际上，使用目前讨论的技术无法检测缩放手势（使用手指进行拉伸和收缩动作，通常用于放大或缩小视图或图像）。

检测缩放手势的最简单方法是使用 Android `ScaleGestureDetector` 类。通常来说，检测缩放手势涉及以下三个步骤：

1. 定义实现`SimpleOnScaleGestureListener`接口的新类，包括所需的`onScale()`、`onScaleBegin()`和`onScaleEnd()`回调方法。
2. 创建`ScaleGestureDetector`类的实例，并将步骤 1 创建的类实例作为参数传递。
3. 在所属`Activity`中实现`onTouchEvent()`回调方法，该方法将调用`ScaleGestureDetector`类的`onTouchEvent()`方法。

在本章的剩余部分，我们将创建一个示例，用于演示缩放手势识别的实现。

## 31.18 缩放手势示例项目

从欢迎屏幕选择`New Project`选项，在弹出的新项目对话框中选择`Empty Views Activity`模板，然后点击`Next`按钮。

在`Name`字段中输入`PinchExample`并指定`com.ebookfrenzy.pinchexample`为包名。在点击`Finish`按钮之前，将`Minimum API level`设置为`API 26: Android 8.0 (Oreo)`，并将`Language`菜单设置为`Java`。按照`12.8 Migrating a Project to View Binding`中的步骤将项目转换为使用 view binding。

在`activity_main.xml`文件中，选择默认的`TextView`对象并使用`Attributes`工具窗口将`ID`设置为`myTextView`。

找到并将`MainActivity.java`文件加载到 Android Studio 编辑器中，并按所示修改文件：

```java
package com.ebookfrenzy.pinchexample;

import android.view.MotionEvent;
import android.view.ScaleGestureDetector;
import android.view.ScaleGestureDetector.SimpleOnScaleGestureListener;

public class MainActivity extends AppCompatActivity {

    private ActivityMainBinding binding;

    ScaleGestureDetector scaleGestureDetector;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

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

该代码声明了一个名为`MyOnScaleGestureListener`的新类，它扩展了 Android 的`SimpleOnScaleGestureListener`类。此接口要求实现三个方法（`onScale()`、`onScaleBegin()`和`onScaleEnd()`）。在此实例中，`onScale()`方法识别比例因子并在文本视图上显示消息，以指示检测到的缩放手势类型。

在`onCreate()`方法中，创建了一个新的`ScaleGestureDetector`实例，并将所属`Activity`的引用以及我们新类`MyOnScaleGestureListener`的实例作为参数传递。最后，为`Activity`实现了`onTouchEvent()`回调方法，该方法调用`ScaleGestureDetector`对象对应的`onTouchEvent()`方法，并将`MotionEvent`对象作为参数传递。

在模拟器或物理 Android 设备上编译并运行应用程序，并在屏幕上执行缩放手势，注意文本视图会根据缩放动作显示“放大”或“缩小”的消息。在模拟器的独立模式下，可以通过按住`Ctrl`（或 macOS 的`Cmd`）键并点击且拖动鼠标指针来模拟缩放手势，如图 31-3 所示：

![image-852JXTPA.jpg](img/image-852JXTPA.jpeg)

图 31-3

## 31.19 总结

手势是触摸屏幕上接触点的运动，涉及一次或多次触摸，可以作为用户与应用程序之间通信的方法。Android 允许使用`Gesture Builder`设计手势。一旦创建，手势就可以保存到手势文件中，并在应用程序运行时使用`GestureLibrary`加载到`Activity`中。

通过将透明`GestureOverlayView`类的实例覆盖在现有视图上，并实现`OnGesturePerformedListener`事件监听器，可以在显示区域上检测手势。使用`GestureLibrary`可以生成用户执行的手势与存储在手势文件中的手势之间的匹配排序列表，并使用预测分数来判断手势是否足够匹配。

通过实现`ScaleGestureDetector`类可以检测缩放手势，本章也提供了该类的示例。

## 32. Android Fragments 简介

随着你对本书章节的不断学习，你会越来越发现，Android 系统背后的许多设计概念的构想是为了促进构成应用程序的不同元素之间的复用和交互。本章将探索的此类领域涉及使用`Fragments`。

本章将提供 Fragment 基础的概述，包括它们是什么以及如何在应用程序中创建和使用它们。下一章将通过教程展示在 Android Studio 中开发应用程序时 Fragment 的运行情况，包括 Fragment 之间通信的实现。

## 32.1 什么是 Fragment？

Fragment 是应用程序用户界面及其相应行为的自包含、模块化部分，可以嵌入到`Activity`中。可以在应用程序设计阶段组合 Fragment 以创建一个`Activity`，并在应用程序运行时将其添加到或从`Activity`中移除，以创建动态变化的用户界面。

Fragment 仅只能作为`Activity`的一部分使用，不能实例化为独立的应用程序元素。然而，Fragment 可以被视为一个功能性的“子 Activity”，其生命周期与完整的`Activity`相似。

Fragment 以 XML 布局文件的形式存储。可以通过在`Activity`的布局文件中放置适当的元素，或者通过`Activity`类中的代码将其添加到`Activity`中。

## 32.2 创建 Fragment

构成 Fragment 的两个组件是一个 XML 布局文件和一个对应的 Java 类。Fragment 的 XML 布局文件格式与任何其他`Activity`的布局相同，可以包含布局管理器和视图的任何组合和复杂度。例如，下面的 XML 布局用于一个由`ConstraintLayout`组成的 Fragment，其背景为红色，包含一个白色前景的`TextView`：

```xml
<ConstraintLayout
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
        android:textAppearance="@style/TextAppearance.Large"
        android:textColor="@color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</ConstraintLayout>
```

与布局对应的类必须是 Android`Fragment`类的子类。该类至少应该重写`onCreateView()`方法，该方法负责加载 Fragment 布局。例如：

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
        // 加载此 fragment 的布局
        binding = FragmentTextBinding.inflate(inflater, container, false);
        return binding.getRoot();
    }
}
```

除了`onCreate()`方法外，该类还可以重写标准的生命周期方法。一旦 fragment 布局和类创建完成，fragment 就可以在应用程序活动中使用了。

## 32.3 使用布局 XML 文件向 Activity 添加 Fragment

可以通过编写 Java 代码或将 fragment 嵌入 activity 的 XML 布局文件中将其纳入活动。无论使用哪种方法，需要注意的关键点是：当使用支持库来兼容旧版本的 Android 发布时，任何使用 fragment 的 activity 必须实现为`FragmentActivity`的子类，而不是`AppCompatActivity`类：

```java
package com.example.myfragmentdemo;

import android.os.Bundle;

import androidx.fragment.app.FragmentActivity;

import android.view.Menu;

public class MainActivity extends FragmentActivity {
    .
    .
```

Fragment 使用`FragmentContainerView`类嵌入到 activity 布局文件中。下面的示例布局将本章上一节创建的 fragment 嵌入到 activity 布局中：

```xml
xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context=".MainActivity"
android:id="@+id/fragment2"
android:name="com.ebookfrenzy.myfragmentdemo.FragmentOne"
android:layout_width="0dp"
android:layout_height="wrap_content"
android:layout_marginStart="32dp"
android:layout_marginEnd="32dp"
app:layout_constraintBottom_toBottomOf="parent"
app:layout_constraintEnd_toEndOf="parent"
app:layout_constraintStart_toStartOf="parent"
app:layout_constraintTop_toTopOf="parent"
tools:layout="@layout/fragment_one" />
```




该元素中的关键属性是`android:name`（必须引用与 fragment 关联类）以及`tools:layout`（必须引用包含 fragment 布局的 XML 资源文件）。一旦添加到 activity 的布局中，就可以在 Android Studio 布局编辑器工具中查看并操作 fragment。例如，图 32-1 显示了 Android Studio 布局编辑器中上述 fragment 的布局：

![image-73HPJB8X.jpg](img/image-73HPJB8X.jpeg)

图 32-1

## 32.4 在代码中添加和管理 Fragment

通过 activity 的 XML 布局文件向其添加 fragment 的便利是以无法在运行时移除 fragment 为代价的。为了在运行时对 fragment 进行完全动态控制，必须通过代码添加这些 activity。这样做的优点是，可以在应用程序运行时动态地添加、删除 fragment，甚至让它们相互替换。

当使用代码管理 fragment 时，fragment 仍然由一个 XML 布局文件和一个相应的类组成。区别在于宿主 activity 在操作 fragment 时。使用代码向 activity 添加 fragment 时有一套标准的步骤序列：

1. 创建 fragment 类的实例。
2. 将任何额外的 intent 参数传递给该类实例。
3. 获取 fragment manager 实例的引用。
4. 在 fragment manager 实例上调用`beginTransaction()`方法。这将返回一个 fragment 事务实例。
5. 调用 fragment 事务实例的`add()`方法，将要包含 fragment 的视图资源 ID 和 fragment 类实例作为参数传递。
6. 调用 fragment 事务的`commit()`方法。

例如，下面的代码添加了由`FragmentOne`类定义的 fragment，使其显示在 ID 为`LinearLayout1`的容器视图中：

```java
FragmentOne firstFragment = new FragmentOne();
firstFragment.setArguments(getIntent().getExtras());
FragmentManager fragManager = getSupportFragmentManager();
FragmentTransaction transaction = fragManager.beginTransaction();
transaction.add(R.id.LinearLayout1, firstFragment);
transaction.commit();
```

上面的代码为了清晰起见，将每个步骤拆分为单独语句。然而，最后四行可以简写为单行代码，如下：

```java
getSupportFragmentManager().beginTransaction()
    .add(R.id.LinearLayout1, firstFragment).commit();
```

一旦添加到容器，随后可以通过调用 fragment 事务实例的`remove()`方法来移除 fragment，并传递要移除的 fragment 实例引用：

```java
transaction.remove(firstFragment);
```

同样，可以通过调用 fragment 事务实例的`replace()`方法用另一个 fragment 替换一个。该方法接受包含 fragment 的视图 ID 和新 fragment 实例作为参数。被替换的 fragment 也可以放入所谓的回栈（back stack）中，以便当用户导航返回时可以快速恢复。这通过在调用`commit()`方法之前，调用 fragment 事务对象的`addToBackStack()`方法来实现：

```java
FragmentTwo secondFragment = new FragmentTwo();
transaction.replace(R.id.LinearLayout1, secondFragment);
transaction.addToBackStack(null);
transaction.commit();
```

## 32.5 处理 Fragment 事件

如前所述，fragment 就像一个拥有自己的布局、类和生命周期的子活动。fragment 内部的视图（如按钮和文本视图）可以产生事件。这产生了一个问题：接收 fragment 中事件的是 fragment 本身，还是嵌入它的 activity？答案取决于事件处理程序的声明。

在“事件处理概述与示例”章节中，讨论了两种处理事件的方法。第一种是在 activity 代码中配置事件监听器和回调方法。例如：

```java
binding.button.setOnClickListener(new Button.OnClickListener() {
    public void onClick(View v) {
        // 按钮点击时执行的代码
    }
});
```

在拦截点击事件时，第二种方法是在 XML 布局文件中设置`android:onClick`属性：

```xml
android:id="@+id/button1"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:onClick="onClick"
android:text="点击我" />
```

fragment 视图产生事件的通用规则是：如果使用监听器和回调方法在 fragment 类中声明监听器，则事件首先由 fragment 处理。但如果使用了`android:onClick`资源，事件将直接传递给所在的 activity。

## 32.6 实现 Fragment 通信

一旦一个或 fragment 被嵌入 activity 中，fragment 与 activity 以及 fragment 之间可能需要某种形式的通信。良好的实践要求 fragment 之间不直接通信。所有通信应通过封装活动进行。

要与 fragment 通信，activity 需要通过分配的 ID 标识 fragment 对象。一旦获取该引用，activity 就可以调用 fragment 的公共方法。

反方向（从 fragment 到 activity）的通信要复杂一些。首先，fragment 必须定义一个监听器接口，然后在 activity 类中实现该接口。例如，下面的代码在名为`ToolbarFragment`的 fragment 上定义了一个`ToolbarListener`接口。代码还声明了一个变量，用于稍后存储 activity 的引用。

```java
public class ToolbarFragment extends Fragment {
  ToolbarListener activityCallback;
  public interface ToolbarListener {
    public void onButtonClick(int position, String text);
  }
  .
  .
}
```

上面的代码规定，任何实现`ToolbarListener`接口的类必须实现一个名为`onButtonClick`的回调方法，该方法反过来接受一个整数和一个`String`作为参数。

接下来，需要重写并实现 fragment 类的`onAttach()`方法。当 fragment 初始化并与 activity 关联时，Android 系统会自动调用此方法。该方法会接收一个包含该 fragment 的 activity 引用。该方法必须存储一个指向该 activity 的本地引用，并验证它是否实现了`ToolbarListener`接口：

```java
@Override
public void onAttach(Context context) {
  super.onAttach(context);
  try {
    activityCallback = (ToolbarListener) activity;
  } catch (ClassCastException e) {
    throw new ClassCastException(activity.toString()
    + " must implement ToolbarListener");
  }
}
```

执行此示例后，activity 的引用将存储在本地`activityCallback`变量中，如果该 activity 没有实现`ToolbarListener`接口，则会抛出异常。

下一步是从 fragment 内部调用 activity 的回调方法。这在何时以及如何发生，完全取决于 fragment 需要联系 activity 的情况。例如，下面的代码在点击按钮时调用 activity 上的回调方法：

```java
public void buttonClicked (View view) {
  activityCallback.onButtonClick(arg1, arg2);
}
```

剩下的工作是修改 activity 类以实现`ToolbarListener`接口。例如：

```java
public class MainActivity extends FragmentActivity
  implements ToolbarFragment.ToolbarListener {
  public void onButtonClick(String arg1, int arg2) {
    // 实现回调方法的代码
  }
  .
  .
}
```

从上述代码中我们可以，activity 声明了它实现了`ToolbarFragment`类的`ToolbarListener`接口，然后按照接口的要求实现了`onButtonClick()`方法。

## 32.7 总结

Fragments 为创建可重用的用户界面布局和应用行为模块提供了一种强大的机制，这些模块一旦创建，就可以嵌入到 activity 中。一个 fragment 由一个用户界面布局文件和一个类组成。可以通过将 fragment 添加到 activity 的布局文件或编写代码在运行时管理 fragment 来在 activity 中利用 fragment。在代码中添加到 activity 的 fragment 可以在运行时动态地删除和替换。fragment 之间的所有通信都应该通过嵌入这些 fragment 的 activity 进行。

在本章涵盖了 fragment 的基础知识后，下一章将通过一个教程来完成，该教程旨在强化本章概述的技术。

## 33. 在 Android Studio 中使用 Fragments - 示例

如上一章所述，fragments 为创建可重用的应用功能模块提供了一种方便的机制，这些模块由用户界面部分和相应的行为组成。一旦创建，fragments 就可以嵌入到 activity 中。

在上一章探索了 fragment 的通用理论后，本章旨在使用 Android Studio 创建一个 Android 应用程序，用于演示创建和使用 fragment 的实际步骤，以及在 activity 内部实现一个 fragment 与另一个 之间的通信。

### 33.1 关于示例 Fragment 应用

在本章创建的应用程序将包含一个 activity 和两个 fragment。第一个 fragment 的用户界面将包含一个由`EditText`视图、一个`SeekBar`和一个`Button`组成的工具栏，所有内容都包含在一个`ConstraintLayout`视图中。第二个 fragment 将仅由`ConstraintLayout`视图中的一个`TextView`对象组成。

这两个 fragment 将嵌入应用程序的主 activity 中，并实现如下通信：当第一个 fragment 中的按钮被按下时，输入到`EditText`视图中的文本将出现在第二个 fragment 的`TextView`上，其字体大小由第一个 fragment 中`SeekBar`的位置决定。

由于此应用程序旨在运行在旧版本的 Android 上，我们变使用适当的 Android 支持库。

### 33.2 创建示例项目

从欢迎屏幕上选择`New Project`选项，在生成的新项目对话框中，点击`Next`按钮之前选择`Empty Views Activity`模板。

在`Name`字段中输入`FragmentExample`并指定`com.ebookfrenzy.fragmentexample`为包名。在点击`Finish`按钮之前，将`Minimum API level`设置更改为`API 26: Android 8.0 (Oreo)`，并将`Language`菜单更改为`Java`。按照`12.8 Migrating a Project to View Binding`中列出的步骤修改项目以使用 view binding。

### 33.3 创建第一个 Fragment 布局

下一步是为我们 activity 中使用的第一个 fragment 创建用户界面。

此用户界面将由一个 XML 布局文件和一个 fragment 类组成。虽然可以手动添加它们，但让 Android Studio 为我们创建会更快。在项目工具窗口中，找到`app -> java -> com.ebookfrenzy.fragmentexample`条目并右键点击它。从生成的菜单中，选择`New -> Fragment -> Gallery...`选项显示图 33-1 所示的对话框：

![image-M73I41TF.jpg](img/image-M73I41TF.jpeg)

图 33-1

在点击`Next`按钮之前选择`Fragment (Blank)`模板。在随后的屏幕上，将 fragment 命名为`ToolbarFragment`，布局文件命名为`fragment_toolbar`：

![image-7U34XVC.jpg](img/image-7U34XVC.jpeg)

图 33-2

使用`Design`模式将布局编辑器加载`fragment_toolbar.xml`文件。接下来，在组件树面板中右键点击`FrameLayout`条目并选择`Convert FrameLayout to ConstraintLayout`选项，接受确认对话框中的默认设置。更改`id`为`constraintLayout`。确保启用`Autoconnect`模式，然后选择并删除默认的`TextView`，添加`Plain Text`、`SeekBar`和`Button`控件，使其位置与图 33-3 所示。最后，分别将视图 id 更改为`editText1`、`seekBar1`和`button1`。

将按钮上的文本更改为“Change Text”，将其提取为名为`change_text`的字符串资源，并移除`EditText`视图中的`Name`文本。最后，将`SeekBar`的`layout_width`属性设置为`match_constraint`，左右设置为`16dp`。

使用`Infer constraints`工具栏按钮添加任何缺失的约束，此时布局应与下图 33-3 所示：

![image-BGSFYI43.jpg](img/image-BGSFYI43.jpeg)

图 33-3

### 33.4 将 Fragment 迁移到 View Binding

与`Empty Views Activity`模板一样，Android Studio 在向项目添加新 fragment 时不会启用 view binding 支持。因此，在继续此教程的下一步之前，我们需要进行此迁移。首先编辑`ToolbarFragment.java`文件并如下导入 fragment 的绑定：

```java
import com.ebookfrenzy.fragmentexample.databinding.FragmentToolbarBinding;
```

接下来，找到`onCreateView()`方法并进行以下声明和更改（包括添加`onDestroyView()`方法以确保在 fragment 销毁时移除绑定引用）：

```java
.
.
private FragmentToolbarBinding binding;

@Override
public View onCreateView(LayoutInflater inflater, ViewGroup container,
Bundle savedInstanceState) {
  // 充入此 fragment 的布局
  return inflater.inflate(R.layout.fragment_toolbar, container, false);
  binding = FragmentToolbarBinding.inflate(inflater, container, false);
  return binding.getRoot();
}

@Override
public void onDestroyView() {
super.onDestroyView();
binding = null;
}
```



完成这些更改后，该 fragment 就可以使用视图绑定（view binding）。

### 33.5 添加第二个 Fragment

重复创建工具栏 fragment 的步骤，添加另一个名为 `TextFragment` 的空白 fragment，其布局文件命名为 `fragment_text`。再次将 `FrameLayout` 容器转换为 `ConstraintLayout`（将 `id` 更改为 `constraintLayout2`）并移除默认的 `TextView`。

从调色板拖入一个 `TextView` 组件并将其放置在布局中心，使用 `Infer`（推断）约束按钮添加任何的约束。将 `TextView` 的 `id` 更改为 `textView2`，将 `text` 设置为“Fragment Two”，并修改 `textSize` 属性为 `24sp`。

完成后，布局应与图 33-4 所示：

![image-UN73GVDG.jpg](img/image-UN73GVDG.jpeg)

图 33-4

重复上一节执行的步骤，将 `TextFragment` 类迁移到使用视图绑定，如下：

```java
.
.
```

```java
import com.ebookfrenzy.fragmentexample.databinding.FragmentTextBinding;
```

```java
.
.
```

```java
private FragmentTextBinding binding;
```

```java
@Override
public View onCreateView(LayoutInflater inflater, ViewGroup container,
        Bundle savedInstanceState) {

    // 载入此 fragment 的布局
    return inflater.inflate(R.layout.fragment_text, container, false);

    binding = FragmentTextBinding.inflate(inflater, container, false);

    return binding.getRoot();
}
```

```java
@Override
public void onDestroyView() {

    super.onDestroyView();

    binding = null;
}
```

### 33.6 将 Fragments 添加到 Activity

应用程序的主 activity 关联了一个名为 `activity_main.xml` 的 XML 布局文件。在本例中，fragment 将使用该文件中的元素添加到 activity 中。使用 `Project` 工具窗口，导航到 `FragmentExample` 项目的 `app -> res -> layout` 部分，并双击 `activity_main.xml` 文件将其加载到 Android Studio 布局编辑器工具中。

在设计模式下的布局编辑器工具中，选择并删除布局中的默认 `TextView` 对象，并在调色板中选择 `Common` 类别。从视图列表中拖出 `FragmentContainerView` 组件并将其释放到布局上，使其水平居中并放置在虚线出现的位置，这表示顶部布局边距：

![image-CHF99CON.jpg](img/image-CHF99CON.jpeg)

图 33-5

将 fragment 释放到布局上时，将出现对话框，显示当前项目中可用的 Fragments 列表，如图 33-6 所示：

![image-ZB5KB344.jpg](img/image-ZB5KB344.jpeg)

图 33-6

从列表中选择 `ToolbarFragment` 条目并点击 OK 关闭 Fragments 对话框。一旦添加，点击布局编辑器右上角的红色警告按钮显示 `Problems` 工具窗口。“unknown fragments”消息将指示布局编辑器需要知道在预览会话期间显示哪个 fragment。选择 `Unknown` fragment 项，然后点击右侧面板中的 `Pick Layout...` 链接，如图 33-7 所示：

![image-QZQEBYXB.jpg](img/image-QZQEBYXB.jpeg)

图 33-7

在生成的对话框（图 33-8）中，选择 `fragment_toolbar` 条目然后点击 OK：

![image-GMYT850F.jpg](img/image-GMYT850F.jpeg)

图 33-8

选中 fragment 后，将 `layout_width` 属性更改为 `match_constraint`，使其占据屏幕全宽。从调色板点击并拖动另一个 `FragmentContainerView` 条目，并将其放置为水平居中并位于第一个 fragment 底部边缘下方。在提示时，点击 OK 之前从 fragment 对话框中选择 `TextFragment` 条目。显示 `Problems` 工具窗口并重复之前的步骤，这次选择 `fragment_text` 布局。使用 `Infer` 约束按钮建立任何缺失的布局约束。

注意 fragment 现在在布局中是可见的，如图 33-9 所示：

![image-VIIA68Y8.jpg](img/image-VIIA68Y8.jpeg)

图 33-9

在继续下一步之前，选择布局中的 `TextFragment` 实例，并在 `Attributes` 工具窗口中将 fragment 的 `ID` 更改为 `text_fragment`。

### 33.7 让 Toolbar Fragment 与 Activity 通信

当用户触摸工具栏 fragment 中的按钮时，fragment 类需要从 `EditText` 视图中提取文本以及 `SeekBar` 的当前值，并将它们发送到文本 fragment。正如“Android Fragments 简介”中所述，fragment 之间不应直接通信，而应该使用嵌入它们的 activity 作为中介。

此过程的第一步是确保工具栏 fragment 对被点击的按钮做出响应。我们还需要实现一些代码来跟踪 `SeekBar` 视图的值。在本例中，我们将在 `ToolbarFragment` 类中实现这些监听器。选择 `ToolbarFragment.java` 文件并修改如下：

```java
package com.ebookfrenzy.fragmentexample;
```

```java
.
.
```

```java
import androidx.annotation.NonNull;
import androidx.annotation.Nullable;

import android.content.Context;
import android.widget.SeekBar;
```

```java
public class ToolbarFragment extends Fragment
        implements SeekBar.OnSeekBarChangeListener {

    private int seekvalue = 10;

    private FragmentToolbarBinding binding;

    @Override
    public void onViewCreated(@NonNull View view,
            @Nullable Bundle savedInstanceState) {

        super.onViewCreated(view, savedInstanceState);

        binding.seekBar1.setOnSeekBarChangeListener(this);

        binding.button1.setOnClickListener(new View.OnClickListener() {

            public void onClick(View v) {

                buttonClicked(v);
            }
        });
    }

    public void buttonClicked(View view) {
    }

    @Override
    public void onProgressChanged(SeekBar seekBar, int progress,
            boolean fromUser) {

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

在继续之前，我们需要花时间解释上述代码。首先，该类声明实现了 `SeekBarChangeListener`。这是因为用户界面包含一个 `SeekBar` 实例，且 fragment 需要在用户滑动线条时接收通知以更改字体大小。实现 `SeekBarChangeListener` 接口要求实现 `onProgressChanged()`、`onStartTrackingTouch()` 和 `onStopTrackingTouch()` 方法。这些方法已经实现，但只有 `onProgressChanged()` 方法需要执行任务，在本例是将新值存储在名为 `seekvalue` 的变量中，该变量在类开头已声明。还声明了一个用于存储 `EditText` 对象的引用。

添加了 `onViewCreated()` 方法来为按钮设置 `OnClickListener`，其配置为检测到点击事件时调用名为 `buttonClicked()` 的方法。该方法也实现了，尽管目前没有执行任何操作。

此过程的下一阶段是设置监听器，允许 fragment 在按钮被点击时调用 activity。这遵循上一节中概述的机制：

```java
public class ToolbarFragment extends Fragment
        implements SeekBar.OnSeekBarChangeListener {

    private static int seekvalue = 10;

    private FragmentToolbarBinding binding;

    ToolbarListener activityCallback;

    public interface ToolbarListener {

        public void onButtonClick(int position, String text);
    }

    @Override
    public void onAttach(Context context) {

        super.onAttach(context);

        try {

            activityCallback = (ToolbarListener) context;

        } catch (ClassCastException e) {

            throw new ClassCastException(context.toString()
                    + " must implement ToolbarListener");
        }
    }

    public void buttonClicked(View view) {

        activityCallback.onButtonClick(
                seekvalue,
                binding.editText1.getText().toString());
    }
}
```

上述实现将导致当用户点击按钮时，会调用属于 activity 类的名为 `onButtonClick()` 方法。因此，剩下的工作就是声明该 activity 类实现了新创建的 `ToolbarListener` 接口，并实现 `onButtonClick()` 方法。

由于在较旧 Android 版本中使用了 Android Support Library 来支持片段（fragment），因此 activity 也需要更改为继承自 `FragmentActivity` 而不是 `AppCompatActivity`。将这些要求结合起来，得到了如下修改后的 `MainActivity.java` 文件：

```java
package com.ebookfrenzy.fragmentexample;

import androidx.appcompat.app.AppCompatActivity;
import androidx.fragment.app.FragmentActivity;

import android.os.Bundle;

public class MainActivity extends FragmentActivity
        implements ToolbarFragment.ToolbarListener {

    public void onButtonClick(int fontsize, String text) {
    }
}
```

按照目前的代码更改，toolbar fragment 将检测用户何时点击按钮，并调用 activity 上的方法，传递 `EditText` 字段的内容和 `SeekBar` 视图的当前设置。现在的任务是让 activity 与 `Text Fragment` 通信，并传递这些值，以便片段能够相应地更新 `TextView` 对象。

### 33.8 让 Activity 与 Text Fragment 通信

正如《Android 片段简介》中所概述的，activity 可以通过获取片段类实例的引用并调用该对象上的公共方法与片段进行通信。因此，在 `TextFragment` 类中，我们现在将实现一个名为 `changeTextProperties()` 的公共方法，该方法接收一个整数作为字体大小，以及一个字符串作为要显示的新文本。然后该方法将使用这些值来修改 `TextView` 对象。在 Android Studio 编辑面板中，找到并修改 `TextFragment.java` 文件以添加此新方法：

```java
package com.ebookfrenzy.fragmentexample;

public class TextFragment extends Fragment {

    public void changeTextProperties(int fontsize, String text) {

        binding.textView2.setTextSize(fontsize);
        binding.textView2.setText(text);
    }
}
```

当 `TextFragment` 片段被放置在 activity 的布局中时，它被赋予了一个 ID `text_fragment`。使用此 ID，activity 现在可以获取片段实例的引用并调用该对象上的 `changeTextProperties()` 方法。编辑 `MainActivity.java` 文件并按如下修改 `onButtonClick()` 方法：

```java
public void onButtonClick(int fontsize, String text) {

    TextFragment textFragment =
            (TextFragment)
            getSupportFragmentManager()
                    .findFragmentById(R.id.text_fragment);

    textFragment.changeTextProperties(fontsize, text);
}
```



### 33.9 测试应用程序

该项目的代码工作已经完成，最后一个剩下的任务是运行应用程序。当应用程序启动时，主`activity`将启动，并创建创建显示两个片段。当用户触摸`toolbar fragment`中的按钮时，`toolbar fragment`将调用`activity`的`onButtonClick()`方法，并传递来自`EditText`视图的文本和`SeekBar`的当前值。随后`activity`将调用第二个片段的`changeTextProperties()`方法，该方法将修改`TextView`以反映新的文本和字体大小：

![image-H2QSSIAC.jpg](img/image-H2QSSIAC.jpeg)

图 33-10

### 33.10 总结

本章的目标是通过创建一个示例项目，演示在 Android 应用程序中使用片段涉及的步骤。涵盖的主题包括使用 Android Support Library 以兼容在引入片段之前的 Android 版本、在`activity`布局中包含片段，以及实现片段间的通信。

## 34. 使用 Jetpack 构建现代 Android 应用架构

多年来，Google 并没有推荐构建 Android 应用的特定方法，而是提供工具和开发工具包，让开发者决定哪种方法对于特定项目或个人编程风格最有效。这种情况在 2017 年随着 Android 架构组件的引入而改变，这些组件随后在 2018 年发布时成为了 Android Jetpack 的一部分。

本章将提供 Jetpack 概念、Android 应用架构建议以及一些关键架构组件的概述。在涵盖基础知识后，这些主题将在后续章节中进行详细介绍，并通过实际示例进行演示。

### 34.1 什么是 Android Jetpack？

Android Jetpack 由 Android Studio、Android 架构组件、Android Support Library 以及一组建议 Android App 应该如何结构的准则组成。Android 架构组件旨在让开发 Android 应用时能够更快、更容易地执行常见任务，同时符合架构准则的核心原则。

虽然本书将涵盖所有的 Android 架构组件，但本章将重点关注关键架构准则以及`ViewModel`、`LiveData`和`Lifecycle`组件，同时引入数据绑定（Data Binding）和仓库（Repositories）。

在继续之前，理解 Jetpack 的应用开发方法是可选的非常重要的。尽管强调了一些多年年来流行的其他技巧的某些缺点，但 Google 并没有完全谴责那些应用开发方法。Google 的立场是，虽然开发应用没有对错之分，但有一种推荐的方法。

### 34.2 “旧”架构

在名为《在 Android Studio 中创建示例 Android 应用》的章节中，创建了一个 Android 项目，它由单个`activity`组成，包含了用于呈现和管理用户界面的所有代码以及应用的后端逻辑。在 Jetpack 引入之前，最常见的架构遵循这种范式，应用由多个`activity`（每个应用内的每个屏幕一个）组成，每个`activity`类在某种程度上都混合了用户界面和后端代码。

这种方法导致了与应用生命周期相关的问题（例如，当用户旋转设备时，`activity`会被销毁并重建，导致未保存到某种持久化存储形式的应用数据丢失），以及诸如导航效率低下的问题（为用户访问的每个应用屏幕启动一个新的`activity`）。

### 34.3 现代 Android 架构

在最基础的层，Google 现在提倡单`activity`应用，并将不同的屏幕作为内容加载到同一个`activity`中。

现代架构准则还建议将应用内部不同的职责划分到完全独立的模块中（这被称为“关注点分离”）。这种方法的关键之一是`ViewModel`组件。

### 34.4 ViewModel 组件

`ViewModel`的目的是将应用中用户界面相关的数据模型和逻辑与负责显示、管理用户界面以及与操作系统交互的代码分开。通过这种设计，应用将由一个或多个 UI 控制器（如`activity`）以及负责处理控制器所需数据的`ViewModel`实例组成。

`ViewModel`只负责数据模型和相应的逻辑。它对用户界面一无所知，也不会尝试直接访问或响应与用户界面内视图相关的事件。当 UI 控制器需要数据进行显示时，它会请求`ViewModel`提供这些数据。同样，当用户在用户界面的视图中输入数据时，UI 控制器会将其传递给`ViewModel`进行处理。

这种职责分离解决了与 UI 控制器生命周期相关的问题。无论 UI 控制器在应用的生命周期内被重建得多频繁，`ViewModel`实例都会保留在内存中，从而保持数据的一致性。例如，`activity`使用的`ViewModel`将一直保留在内存中，直到`activity`结束；在单 Activity 应用中，这意味着直到应用退出才会结束。

![image-UZUAACX7.jpg](img/image-UZUAACX7.jpeg)

图 34-1

### 34.5 LiveData 组件

考虑一个显示实时数据的应用，例如金融股票的当前价格。该应用可以使用股票价格 Web 服务，用最新信息持续更新`ViewModel`中的数据模型。这种实时数据只有在及时显示给用户时才有用。UI 控制器只有两种方式可以确保在用户界面中显示最新数据。一种方案是让控制器持续检查`ViewModel`，以确定数据自上次显示以来是否发生了变化。然而，这种方法的问题在于它的效率可能不够。为了保持数据流的实时性，UI 控制器必须在循环中运行，持续检查数据发生变化。

更好的解决方案是让 UI 控制器在`ViewModel`中的某个特定数据项发生变化时接收到通知。这通过使用`LiveData`组件得以实现。`LiveData`是一个数据持有者，它允许一个值变为可观察的。简单来说，可观察对象可以在其数据发生变化时通知其他对象，从而解决了确保用户界面始终与`ViewModel`中的数据匹配的问题。

这意味着，例如，对`ViewModel`值感兴趣的 UI 控制器可以设置一个观察者，当该值发生变化时，观察者反会收到通知。在我们假设的应用中，例如，股票价格将被封装在`ViewModel`中的一个`LiveData`对象中，UI 控制器将为该值分配一个观察者，声明一个在值变化时调用的方法。当由数据变化触发时，该方法将从`ViewModel`读取更新后的值并用其来更新用户界面。

![image-KCI4OCN9.jpg](img/image-KCI4OCN9.jpeg)

图 34-2

`LiveData`实例也可以被声明为可变的（mutable），允许观察实体更新`LiveData`对象持有的底层值。例如，用户可能会在用户界面中输入一个需要覆盖存储在`ViewModel`中的值的值。

使用`LiveData`的另一个关键优势是它可以感知观察者的生命周期状态。例如，如果一个`activity`包含一个`LiveData`观察者，相应的`LiveData`对象将知道`activity`生命周期状态何时何时变化并做出相应响应。如果`activity`暂停（可能是应用被置于后台），`LiveData`对象将停止向观察者发送事件。假设`activity`刚刚启动或在暂停后恢复。在这种情况下，`LiveData`对象将向观察者发送一个`LiveData`事件，以便`activity`拥有最新的值。同样，`LiveData`实例将知道`activity`何时销并移除观察者以释放资源。

到目前为止，我们只讨论了 UI 控制器使用观察者。在实践中，观察者可以用于任何符合 Jetpack 生命周期管理方法的对象中。

### 34.6 ViewModel 状态的保存

Android 允许用户将活跃的应用置于后台，并在设备上执行其他任务（包括运行其他应用）后返回它。当设备资源不足时，操作系统将通过终止后台应用进程来纠正此问题，从最久未使用的应用开始。然而，当用户返回被终止的后台应用时，无论它是否被终止，它都应该以其被置于后台时的相同状态出现。对于与`ViewModel`关联的数据，可以使用`ViewModel Saved State`模块来实现。该模块允许将值存储在应用的保存状态中，并在系统启动的进程终止时进行恢复。这个主题将在稍后的“Android ViewModel 状态保存教程”章节中介绍。

### 34.7 LiveData 和数据绑定

Android Jetpack 包含了数据绑定库（Data Binding Library），它允许将`ViewModel`中的数据直接映射到 XML 用户界面布局文件中的特定视图。在之前创建的`AndroidSample`项目中，必须编写代码来获取`EditText`和`TextView`视图的引用，并设置和获取文本属性以反映数据变化。数据绑定允许在 XML 布局文件中直接引用存储在`ViewModel`中的`LiveData`值，避免了编写代码来保持布局视图更新的需求。

![image-DL1954WN.jpg](img/image-DL1954WN.jpeg)

图 34-3

数据绑定将更详细地介绍，从“Android Jetpack 数据绑定概览”章节开始。

### 34.8 Android 生命周期

从 Android 组件被创建到它被销毁的时间持续被称为生命周期。在这个生命周期期间，组件将在不同的生命周期状态之间切换，通常受操作系统的控制并响应用户操作。例如，一个`activity`将从初始化状态开始，过渡到创建状态。一旦`activity`运行，它将切换到启动状态，从那里它将在创建、启动、恢复和销毁等状态之间循环。

许多 Android 框架类和组件允许其他对象访问其当前状态。也可以使用生命周期观察者，以便在另一个生命状态变化时接收通知。`ViewModel`组件在后台使用这种技术来识别观察者何时重启或销毁。这种功能不仅限于 Android 框架和架构组件。它也可以构建在架构组件包含的一系列生命周期的任何其他类中。

能够检测并响应其他对象生命周期变化的对象被称为生命周期感知（lifecycle-aware）。相反，提供生命周期状态的对象被称为生命周期所有者（lifecycle owners）。“使用 Android 生命周期周期感知组件”章节将更详细地介绍生命周期。

### 34.9 仓库模块

如果`ViewModel`从一个或多个外部源（如数据库或 Web 服务）获取数据，那么将处理这些数据源的代码与`ViewModel`类分离是非常重要的。毕竟，这样做将违反关注点分离原则。为了避免将此功能与`ViewModel`混合，Google 的架构指南建议将此代码放在独立的仓库（Repository）模块中。

仓库不是 Android 架构组件，而是应用开发者创建的 Java 类，负责与各种数据源进行交互。该类随后为`ViewModel`提供接口，允许将这些数据存储在模型中。

### 34.10 总结

直到最近，Google 往往不会推荐任何特定的 Android 应用结构构建方法。随着 Android Jetpack 的引入，这种情况已经发生了变化。Android Jetpack 由工具、组件、库和架构指南组成。Google 现在建议将应用项目划分为单独模块，每个模块负责特定的功能区域，即“关注点分离”。

特别是，指南建议将应用的视图数据模型（view data model）与处理用户界面的代码分离。此外，负责从网络服务或数据库等数据源收集代码应该构建在独立的仓库模块（repository module）中，而不是与视图模型（view model）打包。

Android Jetpack 包含了 Android 架构组件（Android Architecture Components），旨在开发符合推荐指南的应用更加容易。本章介绍了`ViewModel`、`LiveData`和`Lifecycle`组件。将从下一章开始详细介绍这些组件。本章未提到的其他架构组件将在本书后后部分介绍。

## 35. Android ViewModel 教程

上一章介绍了 Android Jetpack 的基本概念，并概述了现代 Android 应用架构的基础。Jetpack 定义了一系列建议，描述了 Android 应用项目应该如何构建，同时提供了一系列库和组件，使用户更容易遵循这些指南，用更少的代码和更少的错误开发出可靠的应用。

为了帮助强化和澄清上一章提供的信息，本章将逐步创建一个使用`ViewModel`组件的示例应用项目。下一章将通过包含`LiveData`和数据绑定支持来进一步增强此示例。

### 35.1 关于项目

在“在 Android Studio 中创建示例 Android 应用”章节中，创建了一个名为`AndroidSample`的项目，其中应用的所有代码都封装在主`Activity`类文件中。在接下来的章节中，创建并使用了`AVD`模拟器来运行该应用。在应用运行时，我们亲身经历了以这种方式开发应用时出现的问题：当`TextView`小部件上显示的数据在设备旋转期间会丢失。

本章将实现同一个货币转换器应用，将使用`ViewModel`组件并遵循 Google 应用架构指南，以避免`Activity`生命周期的复杂性。

### 35.2 创建 ViewModel 示例项目

在创建`AndroidSample`项目时，选择了`Empty Views Activity`模板作为项目基础。然而，本项目将使用`Basic Views Template`模板。

从欢迎屏幕选择`New Project`选项，在弹出的新项目对话框中，点击`Next`按钮之前选择`Basic Views Activity`模板。

在`Name`字段中输入`ViewModelDemo`，并指定`com.ebookfrenzy.viewmodeldemo`为包名。在点击`Finish`按钮之前，将`Minimum API level`设置更改为`API 26: Android 8.0 (Oreo)`，并将`Language`菜单改为`Java`。

### 35.3 移除不需要的项目元素

正如“Android Studio 布局编辑器工具指南”概述，`Basic Views Activity`模板包含了并非所有项目需要的特性。在将`ViewModel`添加到项目之前，我们首先需要按照所示移除导航功能、第二个内容片段（fragment）和浮动操作按钮：

1. 在 Project 工具窗口中双击`activity_main.xml`布局文件，选择浮动操作按钮，并按键盘删除键从布局中移除该对象。
2. 编辑`MainActivity.java`文件，从`onCreate`方法中移除浮动操作按钮代码，如下所示：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    . ...
    .

    binding.fab.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View view) {
            Snackbar.make(view, "Replace with your own action", Snackbar.LENGTH_LONG)
                .setAnchorView(R.id.fab)
                .setAction("Action", null).show();
        }
    });
}
```

3. 在 Project 工具窗口中，导航并双击`app -> res -> navigation -> nav_graph.xml`文件，将其加载到导航编辑器中。
4. 在编辑器中，选择图面板中的`SecondFragment`条目，并按键盘删除键将其从图中移除。
5. 找到并删除`SecondFragment.java`和`fragment_second.xml`文件。
6. 最后一项任务是从`FirstFragment`类中移除一些代码，以便`Button`视图在点击时不再导航到已不存在的第二个片段。编辑`FirstFragment.java`文件并移除`onViewCreated()`方法中的代码，使其内容如下：

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



## 35.4 设计 Fragment 布局

下一步是设计片段的布局。首先，在 Project 工具窗口中找到`fragment_first.xml`文件并双击将其加载到布局编辑器中。布局加载后，选择并删除现有的`Button`、`TextView`和`ConstraintLayout`组件。接下来，在 Component Tree 面板中右键点击`NestedScrollView`实例，选择`Convert NestedScrollView to ConstraintLayout`菜单选项（如图 31 所示），并在结果对话框中接受默认设置：

![image-FYU2NU.jpg](img/images-FYU2NU.jpeg)
Figure 31

选择转换后的`ConstraintLayout`组件并使用属性窗口将`id`更改为`constraintLayout`。

添加一个新的`TextView`，将其放置在布局中心，并将其`id`更改为`resultText`。接下来，从调色板中拖入`Number (Decimal)`视图并将其放置在`TextView`之上。在布局中选中该视图，参考属性窗口并将`id`更改为`dollarText`。

将一个`Button`拖到布局中，位于`TextView`下方，并将文本属性更改为“Convert”。此时，布局类似于图 32 所示（注意三个视图使用了垂直链）：

![image-OJHMD4Y.jpg](img/images-OJHMD4Y.jpeg)
Figure 32

## 35.5 实现 ViewModel

用户界面布局完成后，需要在视图模型中创建应用的数据模型。首先在 Project 工具窗口中找到`com.ebookfrenzy.viewmodeldemo`条目，右键点击并选择`New -> Java Class`菜单选项。将新类命名为`MainViewModel`并按回车。编辑新类文件使其内容如下：

```java
package com.ebookfrenzy.viewmodeldemo.ui.main;

import androidx.lifecycle.ViewModel;

public class MainViewModel extends ViewModel {

    private static final Float rate = 0.74F;

    private String dollarText = "";

    private Float result = 0F;

    public void setAmount(String value) {

        this.dollarText = value;

        result = Float.parseFloat(dollarText)*rate;

    }

    public Float getResult()

    {

        return result;

    }

}
```

该类声明了变量用于存储当前的美元字符串值以及转换后的金额，并提供了获取（getter）和设置（setter）方法以访问这些数据值。调用`setAmount()`方法时，它会将当前美元金额作为参数并将其存储在局部变量`dollarText`中。美元字符串值将被转换为浮点数，乘以一个虚拟的汇率，并将生成的欧元数值存储在`result`变量中。另一方面，`getResult()`方法返回赋值给`result`变量的当前值。

## 35.6 将 Fragment 与 ViewModel 关联

Fragment 需要某种方式来获取`ViewModel`的引用，以便访问模型并观察数据变化。`Fragment`或`Activity`使用`ViewModelProvider`类的实例来维护其所依赖赖以获取数据的`ViewModels`引用。

在`Fragment`内部使用`ViewModelProvider`类创建`ViewModelProvider`实例。当调用时，会向类初始化器传递当前`Fragment`或`Activity`的引用，并如下所示返回一个`ViewModelProvider`实例：

```java
ViewModelProvider viewModelProvider = new ViewModelProvider(this);
```

一旦创建了`ViewModelProvider`实例，就可以使用索引值来请求特定的`ViewModel`类。提供程序随后将创建该`ViewModel`类的新实例，或返回一个现有实例，例如：

```java
ViewModel viewModel = viewModelProvider.get(MainViewModel.class);
```

编辑`FirstFragment.java`文件并重写`onCreate()`方法来设置`ViewModelProvider`：

```java
import androidx.lifecycle.ViewModelProvider;

import androidx.annotation.Nullable;

public class FirstFragment extends Fragment {

    private MainViewModel viewModel;

    @Override

    public void onCreate(@Nullable Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);

        viewModel = new ViewModelProvider(this).get(MainViewModel.class);

    }

}
```

获得模型视图的访问权限后，现在可以向`Fragment`添加代码以开始处理数据模型。

## 35.7 修改 Fragment

需要更新 Fragment 类以响应按钮点击并与存储在`ViewModel`中的数据值进行交互。该类还需要用户界面布局中三个视图的引用，以便响应按钮点击、提取当前美元值并显示转换后的货币金额。

在题为“在 Android Studio 中创建一个 Android 示例应用”的章节中，使用了`Button`组件的`onClick`属性来指定用户点击按钮时调用的方法。遗憾的是，此属性只能调用`Activity`中的方法，不能用于调用`Fragment`中的方法。为了克服这一限制，我们必须向`Fragment`类添加一些代码，以在按钮上设置`onClick`监听器。如下所示，可以在`FirstFragment.java`文件的`onViewCreated()`生命周期方法中实现这一点：

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

添加监听器后，每当用户点击按钮时，位于`onClick()`方法中的任何代码都将被调用。

## 35.8 访问 ViewModel 数据

点击按钮时，`onClick()`方法需要从`EditText`视图读取当前值，确认字段为空，然后调用`ViewModel`实例的`setAmount()`方法。随后，该方法需要调用`ViewModel`的`getResult()`方法并在`TextView`组件上显示转换后的值。

由于项目尚未未使用`LiveData`，因此在每次创建`Fragment`时，也有必要从`ViewModel`获取最新的结果值。

在`FirstFragment.java`文件中，在`onViewCreated()`方法中如下实现这些需求：

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

## 35.9 测试项目

完成此项目开发阶段后，在模拟器或物理设备上构建并运行应用，输入美元值并点击转换按钮。转换后的金额应出现在`TextView`上，表明 UI 控制器和`ViewModel`的重构符合预期。

当运行原始的`AndroidSample`应用时，旋转设备会导致`resultText` `TextView`组件上显示的值丢失。现在对`ViewModelDemo`应用重复此测试，并注意在旋转后当前的欧元值被保留。这是因为当`Fragment`被销毁和重建时，`ViewModel`仍然留在内存中，并且在`onViewCreated()`方法中添加了代码以用结果数据值更新`TextView`。

## 35.10 总结

在本章节中，我们回顾了书中之前创建的`AndroidSample`项目，并创建了符合 Android Jetpack 指南的新版本项目。示例项目还展示了使用`ViewModels`来分离数据处理与界面。

## 36. Android Jetpack LiveData 教程

上一章节开始按照推荐的 Jetpack 指南构建应用。这些初始步骤在`ViewModel`实例中实现了应用界面的数据模型。

本章节将使用`LiveData`进一步增强应用设计。在本章为项目添加`LiveData`支持后，后续章节（从“Android Jetpack Data Binding 概述”开始）将使用 Jetpack Data Binding 库进一步减少代码。

## 36.1 LiveData - 回顾

`LiveData`之前在“带有 Jetpack 的现代 Android 应用架构”章节中介绍过。如前所述，`LiveData`组件可以作为视图内部数据的封装。一旦包含在`LiveData`实例中，这些变量就可以被应用内的其他对象（通常是`Activity`和`Fragment`）观察到。这允许 UI 控制器在底层`LiveData`值变化时接收通知。通过创建`Observer`类的实例并定义在`LiveData`值变化时调用的`onChange()`方法，可以设置观察者。一旦创建了`Observer`实例，就可以调用`LiveData`对象的`observe()`方法将其附加到`LiveData`对象上。

`LiveData`实例可以使用`MutableLiveData`类声明为可变，从而允许`ViewModel`和 UI 控制器更改底层数据值。

## 36.2 向 ViewModel 中添加 LiveData

启动 Android Studio，打开上一章创建的`ViewModelDemo`项目，并打开`MainViewModel.java`文件，其目前的内容如下：

```java
package com.ebookfrenzy.viewmodeldemo;
```

```java
import androidx.lifecycle.ViewModel;

public class MainViewModel extends ViewModel {

    private static final Float rate = 0.74F;

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

本章的这一阶段是将`result`变量封装在一个`MutableLiveData`实例中（该对象需要是可变的，以便在用户每次请求货币转换时都能更改值）。首先修改该类，使其现在的内容所示，请注意在使用`LiveData`时需要导入一个额外的包：

```java
package com.ebookfrenzy.viewmodeldemo;

import androidx.lifecycle.MutableLiveData;

import androidx.lifecycle.ViewModel;

public class MainViewModel extends ViewModel {

    private static final Float rate = 0.74F;

    private String dollarText = "";

    private Float result = 0F;

    final private MutableLiveData result = new MutableLiveData<>();

    public void setAmount(String value) {

        this.dollarText = value;

        result = Float.parseFloat(dollarText)*rate;

    }

    public Float getResult() {

        return result;

    }

}
```

既然`result`变量已包含在可变的`LiveData`实例中，则必须修改`setAmount()`和`getResult()`方法。在`setAmount()`方法中，不能再使用赋值运算符（`=`）为`result`变量赋值。相反，必须调用`LiveData.setValue()`方法，并将新值作为参数传递。按照目前的实现，`getResult()`方法声明为返回`Float`值，必须更改为返回`MutableLiveData`对象。完成这些剩余更改后将得到以下类文件：

```java
package com.ebookfrenzy.viewmodeldemo;

import androidx.lifecycle.MutableLiveData;

import androidx.lifecycle.ViewModel;

public class MainViewModel extends ViewModel {

    private static final Float rate = 0.74F;

    private String dollarText = "";

    final private MutableLiveData result = new MutableLiveData<>();

    public void setAmount(String value) {

        this.dollarText = value;

        result = Float.parseFloat(dollarText)*rate;

        result.setValue(Float.parseFloat(dollarText)*rate);

    }

    public MutableLiveData getResult() {

        return result;

    }

}
```

## 36.3 实现观察者

现在转换结果已包含在`LiveData`实例中，下一步是在 UI 控制器中配置一个观察者，在例中，该控制器是`FirstFragment`类。找到`FirstFragment.java`类（`app -> java -> -> FirstFragment`），双击将其加载到编辑器，并修改`onViewCreated()`方法以创建一个名为`resultObserver`的新`Observer`实例：



`package com.ebookfrenzy.viewmodeldemo;`

`import androidx.lifecycle.Observer;`

`// ...`

`@Override`

`public void onViewCreated(@NonNull View view, @Nullable Bundle savedInstanceState) {`

`    super.onViewCreated(view, savedInstanceState);`

`    binding.resultText.setText(String.format(Locale.ENGLISH,"%.2f",`

`    viewModel.getResult()));`

`    final Observer resultObserver = new Observer() {`

`        @Override`

`        public void onChanged(@Nullable final Float result) {`

`            binding.resultText.setText(String.format(Locale.ENGLISH,`

`            "%.2f", result));`

`        }`

`    };`

`// ...`

`}`

`resultObserver` 实例声明了 `onChanged()` 方法，该方法在调用时会传入当前结果值，然后将其转换为字符串并显示在 `resultText` TextView 对象上。下一步是将观察者添加到 `result` `LiveData` 对象中，该引用可以通过调用 `ViewModel` 对象的 `getResult()` 方法获取。由于更新 `result` TextView 现在是 `onChanged()` 回调方法的职责，现在可以删除执行此任务的现有代码行：

```java
@Override
public void onViewCreated(@NonNull View view, @Nullable Bundle savedInstanceState) {
    super.onViewCreated(view, savedInstanceState);
    binding.resultText.setText(String.format(Locale.ENGLISH,"%.2f",
    viewModel.getResult()));
    final Observer resultObserver = new Observer() {
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
            binding.resultText.setText(String.format(Locale.ENGLISH,"%.2f",
            viewModel.getResult()));
        } else {
            binding.resultText.setText("No Value");
        }
    });
}
```

编译并运行应用，在美元字段中输入一个值，点击转换（Convert）按钮，并验证转换后的欧元金额是否显示在 TextView 上。这证实了观察者收到了结果值变化的通知。

在上述 `onViewCreated()` 方法中，原本用于每次调用时显示当前值的代码行已被删除。这原本是为了在 Fragment 重建时能够恢复显示值。由于 `LiveData` 监控观察者的生命周期，现在不再需要这样做。当 `LiveData` 检测到 UI 控制器被重建时，它会自动触发相关的观察者并提供最新数据。你可以通过在 TextView 上显示值时旋转设备来验证这一点。

在进入下一章之前，关闭项目，复制 `ViewModelDemo` 文件夹并将其保存为 `ViewModelDemo_LiveData` 以备后用。

## 36.4 总结

本章演示了如何使用 `LiveData` 组件确保显示的数据与存储在 `ViewModel` 中的数据一致。这一简单过程是将 `ViewModel` 值封装在 `LiveData` 对象中，并在 UI 控制器中设置订阅该值的观察者。每当 `LiveData` 值变化时，观察者就会收到通知并调用 `onChanged()` 方法。

为项目添加 `LiveData` 支持在某种程度上简化了设计。使用 Data Binding Library 还可以带来重大的改进，细节将在下一章中讨论。

## 37. Android Jetpack Data Binding 概览

在标题为“使用 Jetpack 构建现代 Android 应用架构”的章节中，我们引入了 Android Data Binding。我们解释了如何使用它直接将 UI 布局中的视图连接到其他对象中的方法和数据，无需编写代码。本章将提供更多关于数据绑定的细节，重点介绍其实现实现的方式。下一章的教程（Android Jetpack Data Binding 教程）将提供一个实用的示例。

## 37.1 Data Binding 概览

Android Jetpack Data Binding Library 提供了绑定支持，主要提供了一种简单的方法，将 UI 布局中的视图与应用代码中存储的数据（通常在 `ViewModel` 实例中）连接起来。

当数据绑定与 `LiveData` 组件结合使用时，其功能变得异常强大。例如，考虑使用数据绑定将 `EditText` 视图绑定到 `ViewModel` 中的 `LiveData` 变量。通过这种方式连接后，`ViewModel` 中数据值的任何更改将自动显示在 `EditText` 视图中；当使用双向绑定时，输入到 `EditText` 中的任何数据都将自动用于更新 `LiveData` 的值。最令人印象深刻的是，这可以在初始化绑定所需的代码之外，无需编写任何额外代码即可实现。

传统上，将交互式视图（如 `Button` 控件）连接到 UI 控制器中的方法，需要开发者编写代码来实现一个监听器方法，以便在点击按钮时调用该方法。数据绑定使得这一切变得非常简单，只需在布局 XML 文件的 `Button` 元素中引用要被调用的方法即可。

## 37.2 数据绑定的核心组件

Android Studio 项目默认并没有配置数据绑定的支持。在应用开始使用数据绑定之前，必须组合几个元素。这些元素涉及项目构建配置、布局 XML 文件、数据绑定类以及数据绑定表达式语言的使用。虽然初看起来之下这可能很复杂，但分离开来看，这些都是非常简单的步骤，一旦完成，在节省编码工作方面是非常值得的。本章剩余部分将详细介绍每个元素。在介绍这些基础之后，下一章将通过详细的教程演示这些步骤。

### 37.2.1 项目构建配置

在项目可以使用数据绑定之前，必须将其配置为使用 Android Data Binding Library，并启用对数据绑定类和绑定语法的支持。幸运的是，只需在模块级 `build.gradle.kts` 文件中添加几行代码即可实现（即项目工具窗口 Gradle Scripts 下列出的 `build.gradle.kts (Module: app)` 的文件）。以下列出了启用了数据绑定的部分构建文件：

```
android {
    buildFeatures {
        dataBinding = true
    }
}
```

### 37.2.2 数据绑定布局文件

正如我们在之前的章节中所看到的，应用的用户界面通常包含在 XML 布局文件中。在这些布局文件中的视图利用数据绑定优势之前，必须将布局文件转换为数据绑定布局文件。

正如书前面所述的，XML 布局文件定义了布局中组件的层次结构，从顶层或根视图开始。无论如何，这个根视图都是布局容器的形式，例如 `ConstraintLayout`、`FrameLayout` 或 `LinearLayout` 实例，就像 `ViewModelDemo` 项目中的 `fragment_main.xml` 文件所示：

```xml
xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:id="@+id/main"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context=".ui.main.MainFragment">
```

要使用数据绑定，布局层次结构必须有一个布局组件作为根视图，该组件反过来成为当前根视图的父视图。

在上述示例的情况下，这将需要对现有布局文件进行以下更改：

```xml
xmlns:tools="http://schemas.android.com/tools"
xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:id="@+id/main"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context=".ui.main.MainFragment">
```

### 37.2.3 布局文件数据元素

数据绑定布局文件需要某种方式来声明项目中的类，布局中的视图将绑定到这些类（例如 `ViewModel` 或 UI 控制器）。声明这些类后，布局文件需要一个变量在绑定表达式中引用这些实例。

这是通过 `data` 元素实现的，示例所示：

```xml
xmlns:tools="http://schemas.android.com/tools"
xmlns:android="http://schemas.android.com/apk/res/android"
name="myViewModel"
type="com.ebookfrenzy.myapp.ui.main.MainViewModel" />
android:id="@+id/main"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context=".ui.main.MainFragment">
```

上述数据元素声明了一个名为 `myViewModel` 类型为 `MainViewModel` 的新变量（注意，在声明变量时必须声明 `MyViewModel` 类的完整包名）。

`data` 元素可以导入其他类，这些类可以在布局文件的其他地方绑定表达式中引用。例如，如果你有一个类，在显示给用户之前需要对某个值调用其中的方法，可以如下所示导入该类：

```xml
name="viewModel"
type="com.ebookfrenzy.myapp.ui.main.MainViewModel" />
```

### 37.2.4 绑定类

对于绑定布局文件中 `data` 元素中引用的每个类，Android Studio 将自动生成一个对应的绑定类。此 `AndroidDataBinding` 类的类将根据布局文件名使用 `Binding` 后缀命名。因此，对于名为 `fragment_main` 的布局，绑定类将是 `FragmentMainBinding`。绑定类包含布局文件中指定的绑定，并映射到变量。

虽然绑定类是自动生成的，但必须编写代码创建该实例。幸运的是，可以通过 `DataBindingUtil` 类来实现。

`Activity` 或 `Fragment` 的初始化代码通常会设置内容视图或“填充”用户界面布局。这意味着代码打开布局文件，解析 XML 并在内存中创建并配置视图对象。对于现有的 `Activity` 类，实现此目的的代码位于 `onCreate()` 方法中，如下：

```java
setContentView(R.layout.activity_main);
```

在 `Fragment` 的情况下，这发生在 `onCreateView()` 方法中：

```java
return inflater.inflate(R.layout.fragment_main, container, false);
```

在 `Activity` 类中创建绑定实例只需要如下所示修改初始化代码：

```java
ActivityMainBinding binding;
binding = DataBindingUtil.setContentView(this, R.layout.activity_main, false);
```

在 `Fragment` 的情况下，代码如下：

```java
FragmentMainBinding binding;
binding = DataBindingUtil.inflate(inflater, R.layout.fragment_main, container, false);
binding.setLifecycleOwner(this);
View view = binding.getRoot();
return view;
```

### 37.2.5 数据绑定变量配置

如上述，数据绑定布局文件包含 `data` 元素，该元素包含 `variable` 元素，由变量名和要建立绑定的类类型组成。例如：

```xml
name="viewModel"
type="com.ebookfrenzy.viewmodeldemo.ui.main.MainViewModel" />
name="uiController"
type="com.ebookfrenzy.viewmodeldemo_databinding.ui.main.MainFragment" />
```

在上述示例中，第一个变量知道它将绑定类型为 `MainViewModel` 的 `ViewModel` 类实例，但尚未连接到实际的 `MainViewModel` 对象实例。这需要额外的步骤，将应用内部使用的 `MainViewModel` 实例赋值给布局文件中声明的变量。通过调用数据绑定实例的 `setVariable()` 方法来实现，该引用在上一章中获取。

```java
MainViewModel mViewModel = new ViewModelProvider(this).get(MainViewModel.class);
binding.setVariable(viewModel, mViewModel);
```

上述数据元素中的第二个变量以 `名为` `Fragment` 的形式引用了一个 UI 控制器类。在这种情况下，UI 控制器（无论是 `Activity` 还是 `Fragment`）中的代码需要按照如下方式将自己赋值给该变量：

```java
binding.setVariable(uiController, this);
```

### 37.2.6 绑定表达式（单向）

绑定表达式定义了特定视图如何与绑定对象进行交互。例如，`Button` 上的绑定表达式可以声明在响应点击事件时调用对象上的哪个方法。或者，绑定表达式可以定义存储在 `ViewModel` 中的哪个数据值将显示在 `TextView` 中，以及如何对其进行展示和格式化。

绑定表达式使用声明式语言，该语言允许通过逻辑以及对其他类和方法的访问来决定如何使用绑定数据。例如，表达式可以包含数学表达式、方法调用、字符串拼接、对数组元素的访问以及比较操作。此外，所有标准的 Java 语言库都会默认导入，因此在 Java 中可以实现的许多功能也可以在绑定表达式中执行。正如讨论过的，数据元素还可以用于导入自定义类，以为表达式添加更多功能。

绑定表达式以 `@` 符号开头，随后是包含在大括号 (`{}`) 中的表达式。

例如，考虑一个包含名为 `result` 变量的 `ViewModel` 实例。假设该类已分配给数据绑定布局文件中名为 `viewModel` 的变量，并需要绑定到 `TextView` 对象，以便该视图始终显示最新的结果值。如果此值被存储为 `String` 对象，则在布局文件中声明如下：

```xml
android:id="@+id/resultText"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
```



进入`/path/to/xxx`目录，找到`xxx.json`。

在表达式`cvar = avar + bvar`中，加法运算符（`+`）将`avar`与`bvar`相加，得到它们的和`cvar`。

在`List.of(arg0, arg1, arg2)`中，`List`接口的工厂方法`of()`接受一系列的元素，返回包含它们的只读列表。

之后我们这样调用`cmd`命令：`cmd arg0 arg1 arg2`。

```
if (condVar > someVal) {console.log("xxx")}
```



`android:text="@={myViewModel.dollarValue}"`

`app:layout_constraintEnd_toEndOf="parent"`

`app:layout_constraintHorizontal_bias="0.502"`

`app:layout_constraintStart_toStartOf="parent"`

`app:layout_constraintTop_toTopOf="parent" />`

现在已经添加了这些初始绑定表达式，必须编写一个方法，在用户点击`Button`组件时执行转换。

## 38.8 添加转换方法

当点击`Convert`按钮时，它将调用`ViewModel`上的方法来执行转换计算，并将欧元值存入`result` `LiveData`变量中。现在在`MainViewModel.java`文件添加此方法：

```java
public class MainViewModel extends ViewModel {

    private static final Float usd_to_eu_rate = 0.74F;

    final public MutableLiveData dollarValue = new MutableLiveData<>();

    final public MutableLiveData result = new MutableLiveData<>();

    public void convertValue() {

        if ((dollarValue.getValue() != null) &&

            (!dollarValue.getValue().isEmpty())) {

            result.setValue(Float.parseFloat(dollarValue.getValue())

                * rate);

        } else {

            result.setValue(0F);

        }

    }

}
```

注意，在没有有效的美元值的情况下，`result` `LiveData`变量将被赋值为零。这确保了分配给`resultText` `TextView`的绑定表达式在用户未输入任何值时会显示“Enter value”消息。

## 38.9 添加监听器绑定

在测试项目之前的最后一步是在布局文件中的`Button`元素添加监听器绑定表达式，以便在点击按钮时调用`convertValue()`方法。再次以`Code`模式编辑`fragment_first.xml`文件，找到`convertButton`元素，并如下添加`onClick`条目：

```xml
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

## 38.10 测试应用

编译并运行应用，测试在美元字段中输入一个值并点击`Convert`按钮是否会在`TextView`上显示正确的结果（连同“euros”后缀），以及在美元字段为空时尝试转换时是否会出现“Enter value”提示。此外，验证用户界面中显示的信息在经过设备旋转后是否仍然得到保留。

## 38.11 总结

本章的主要目标是完成设置项目使用数据绑定的步骤，并演示单向、双向绑定和监听器绑定表达式的使用。本章还提供了一个实用示例，说明了通过结合`LiveData`将用户界面视图与应用的后端数据和逻辑连接起来，可以节省多少代码编写。

## 39. Android ViewModel 状态保存教程

应用状态的保存与恢复关于在应用被置于后台后，为用户提供外观和行为的连续性。用户期望能够从一个应用切换到另一个应用，并在返回原始应用时，发现它正处于切换发生前的完全相同的状态。

正如“理解 Android 应用和 Activity 生命周期”章节所概述的，当用户将应用程序置于后台时，如果资源受限，该应用程序将可能被操作系统终止。当用户尝试返回已终止的应用程序到前台时，`Android`会在新进程中重新启动该应用。由于这一切对用户是不可见的，因此应用程序有责任将自己恢复到最初被置于后台时的相同状态，而不是以其“初始启动”状态呈现。对于基于`ViewModel`的应用，这许多行为可以通过使用`ViewModel` Saved State 模块来实现。

## 39.1 理解 ViewModel 状态保存

如前几章所述，`ViewModel`为应用开发带来了许多益处，包括在发生设备旋转等配置更改时恢复 UI 状态。为了看到这一点，运行`ViewModelDemo`应用（如果你仍需要创建项目，请加载书中附带的`ViewModelDemo_LiveData`项目）。

运行时输入一个美元值并将其转换为欧元。旋转设备或模拟器，注意配置更改后两个值仍然可见。

遗憾的是，这种行为并不适用于后台进程的终止。在应用运行时，点击设备主页将`ViewModelDemo`应用放入后台，然后通过打开终端窗口并运行以下命令（创建项目时使用的名称，例如`com.ebookfrenzy.viewdemo`）：

```
adb shell kill
```

如果找不到`adb`命令，请参考“设置 Android 开发环境”章节来设置你的 Android Studio 环境。

应用终止后，返回设备或模拟器从启动器选择应用（不要在 Android Studio 内部重新运行应用）。应用出现后，将是刚启动的状态，丢失了最后的美元和欧元值。然而从用户的角度来看，应用是从后台恢复的，并且应该包含原始数据。在这种情况下，应用未能提供用户预期的连续性。

## 39.2 实现 ViewModel 状态保存

基本的`ViewModel`状态保存通过引入`ViewModel` Saved State 库实现。该库扩展了`ViewModel`类，增加了在后台进程终止并在重新启动后维护状态的支持。

保存的关键在于`SavedStateHandle`类，它用于保存和恢复视图实例的状态。`SavedStateHandle`对象包含一个键值映射，允许通过引用相应的键来保存和恢复数据值。

为了支持状态保存，需要声明不同的`ViewModel`子类，此处包含一个可以接收`SavedStateHandle`实例的构造函数。一旦声明，可以通过在创建时包含`SavedStateViewModelFactory`对象来创建此类`ViewModel`实例。考虑以下来自标准`ViewModel`声明的代码片段：

```java
package com.ebookfrenzy.viewmodeldemo.ui.main;

import androidx.lifecycle.ViewModel;

import androidx.lifecycle.MutableLiveData;

public class MainViewModel extends ViewModel {

}
```

创建此类实例的代码可能如下所示：

```java
private MainViewModel mViewModel;

mViewModel = new ViewModelProvider(this).get(MainViewModel.class);
```

另一方面，设计用于支持保存状态（saved state）的`ViewModel`子类需要如下声明：

```java
package com.ebookfrenzy.viewmodeldemo.ui.main;

import android.util.Log;

import androidx.lifecycle.ViewModel;

import androidx.lifecycle.MutableLiveData;

import androidx.lifecycle.SavedStateHandle;

public class MainViewModel extends ViewModel {

    private SavedStateHandle savedStateHandle;

    public MainViewModel(SavedStateHandle savedStateHandle) {

        this.savedStateHandle = savedStateHandle;

    }

...

}
```

在创建上述`ViewModel`实例时，必须按照所示向`ViewModelProvider`类的初始化器传递`SavedStateViewModelFactory`实例：

```java
SavedStateViewModelFactory factory =

new SavedStateViewModelFactory(getActivity().getApplication(),this);

mViewModel = new ViewModelProvider(this).get(MainViewModel.class);
```

## 39.3 保存和恢复状态

可以在`ViewModel`内部通过将对象或值传递给`SavedStateHandle`实例的`set()`方法进行保存，并提供一个在执行检索时引用的键字符串：

```java
private static final String NAME_KEY = "Customer Name";

savedStateHandle.set(NAME_KEY, customerName);
```

当与`LiveData`对象一起使用，可以使用`SavedStateHandle`实例的`getLiveData()`方法恢复之前保存的值，再次按照所示引用相应的键：

```java
MutableLiveData restoredName = savedStateHandle.getLiveData(NAME_KEY);
```

要恢复普通（非`LiveData`）对象，请使用`SavedStateHandle`的`get()`方法：

```java
String restoredName = savedStateHandle.get(NAME_KEY);
```

其他有用的`SavedStateHandle`方法包括：

- `contains(String key)` - 返回一个布尔值，表示保存的状态是否包含指定键的值。
- `remove(String key)` - 从保存的状态中移除该值和键。返回返回被移除的值。
- `keys()` - 返回一个包含保存状态中所有键的字符串集合。

## 39.4 为 ViewModelDemo 项目添加保存状态支持

在涵盖了`ViewModel`保存状态的基础后，可以扩展`ViewModelDemo`应用以包含此支持。首先，将“一个 Android Jetpack LiveData 教程”中创建的`ViewModelDemo_LiveData`项目加载到 Android Studio（示例代码下载中也有该项目的副本）。

接下来，修改`MainViewModel.java`文件，使构造函数接受并存储`SavedStateHandle`实例。此外，导入`androidx.lifecycle.SavedStateHandle`，声明一个键字符串常量，并修改结果`LiveData`变量，以便值现在从构造函数中的保存状态中获取：

```java
package com.ebookfrenzy.viewmodeldemo.ui.main;

import androidx.lifecycle.ViewModel;

import androidx.lifecycle.MutableLiveData;

import androidx.lifecycle.SavedStateHandle;

public class MainViewModel extends ViewModel {

    private static final String RESULT_KEY = "Euro Value";

    private static final Float rate = 0.74F;

    private String dollarText = "";

    final private SavedStateHandle savedStateHandle;

    final private MutableLiveData result = new MutableLiveData<>();

    public MainViewModel(SavedStateHandle savedStateHandle) {

        this.savedStateHandle = savedStateHandle;

        result = savedStateHandle.getLiveData(RESULT_KEY);

    }

...
}
```

继续留在`MainViewModel.java`文件中，修改`setAmount()`方法，包含在每次计算新的欧元金额时保存结果值的代码：

```java
public void setAmount(String value) {

    this.dollarText = value;

    result.setValue(Float.valueOf(dollarText)* rate);

    Float convertedValue = Float.parseFloat(dollarText)* rate;

    result.setValue(convertedValue);

    savedStateHandle.set(RESULT_KEY, convertedValue);

}
```

完成对`ViewModel`的更改后，打开`FirstFragment.java`文件进行以下更改，以便在`ViewModel`创建过程中包含一个 Saved State 工厂实例：

```java
..

import androidx.lifecycle.SavedStateViewModelFactory;

..

@Override

public void onCreate(@Nullable Bundle savedInstanceState) {

    super.onCreate(savedInstanceState);

    SavedStateViewModelFactory factory =

    new SavedStateViewModelFactory(

    getActivity().getApplication(),this);

    mViewModel = new ViewModelProvider(this, factory).get(MainViewModel.class);

    // TODO: Use the ViewModel

}
```




当屏幕 UI 显示了美元和欧元值后，将应用置于后台，使用`adb`工具终止它，然后从设备或模拟器屏幕重新启动它。重启后，之前的货币金额仍然显示在`TextView`和`EditText`组件中，这证实了状态已成功保存并恢复。

## 39.5 总结

一个良好的应用程序在从后台返回前台时，应该始终向用户呈现相同的状态，无论操作系统在此期间是否终止了包含应用的进程。在处理`ViewModels`时，可以通过利用`ViewModel`保存状态模块来实现这一点。这涉及修改`ViewModel`构造函数以接受`SavedStateHandle`实例，该实例反过来可以通过一系列方法调用来保存和恢复数据。当`ViewModel`实例创建时，必须向其传递`SavedStateViewModelFactory`实例。一旦实现了这些步骤，应用程序在终止期间会自动保存和恢复状态。

# 40. 与 Android 生命周期感知组件协作

早期的章节“理解 Android 应用和 Activity 生命周期”描述了使用生命周期方法跟踪 UI 控制器（如 Activity 或 Fragment）内部生命状态的变化。这些方法的主要问题之一是将处理生命变化的负担放在了 UI 控制器上。从表面上看，这似乎是逻辑方法，因为 UI 控制器毕竟是经历状态变化的对象。然而，事实是受状态变化影响的代码通常位于应用中的其他类中。这导致 UI 控制器中出现了需要根据响应管理其他对象的复杂代码。

一种更清晰、更有逻辑的方法是应用中的对象能够观察其他对象的生命状态，并负责根据变化采取任何行动。例如，负责跟踪用户位置的类可以观察 UI 控制器的生命状态，并在控制器进入暂停状态时挂起位置更新。当控制器进入恢复状态时，重新开始跟踪。这可以通过 Android 架构组件自带的 Lifecycle 包提供的类和接口实现。

本章将介绍构建生命周期感知到 Android 应用中的术语和关键组件。

## 40.1 生命周期感知

## 40.2 生命周期所有者

生命感知组件只能观察生命周期所有者的对象状态。生命周期所有者实现了`LifecycleOwner`接口，并分配了一个关联的`Lifecycle`对象，负责存储组件的当前状态并向生命周期观察者提供状态信息。大多数 Android 框架组件（如 activity 和 fragment 类）都是生命周期所有者。自定义类也可以使用`LifecycleRegistry`类并实现`LifecycleObserver`接口来配置为生命周期所有者。例如：

```java
public class SampleOwner implements LifecycleOwner {

    private LifecycleRegistry lifecycleRegistry;

    @Override
    protected void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);

        .

        .

        lifecycleRegistry = new LifecycleRegistry(this);

    }

    @NonNull

    @Override
    public Lifecycle getLifecycle() {

        return lifecycleRegistry;

    }

}
```

除非生命周期所有者是生命感知组件的子类，否则该类需要通过调用`LifecycleRegistry`类的方法来触发生命周期状态变化。可以使用`markState()`方法通过传递新的状态值来触发生命周期状态变化：

```java
public void resuming() {

    lifecycleRegistry.markState(Lifecycle.State.RESUMED);

}
```

上面的调用将导致对相应的事件处理程序的调用。或者，可以调用`LifecycleRegistry.handleLifecycleEvent()`方法并传递要触发的生命周期事件（这将导致生命周期状态改变）。例如：

```java
lifecycleRegistry.handleLifecycleEvent(Lifecycle.Event.ON_START);
```

## 40.3 生命周期周期观察者（Lifecycle Observers）

为了观察生命周期所有者的状态，生命感知组件必须实现`DefaultLifecycleObserver`接口，并覆盖它需要观察的任何生命周期变化事件的方法。

```java
public class SampleObserver implements DefaultLifecycleObserver {

    // 生命周期事件方法重写写在这里

}
```

然后创建此观察者类的实例并将其添加到由`Lifecycle`对象维护的观察者列表中。

```java
getLifecycle().addObserver(new SampleObserver());
```

如果观察者不再需要跟踪生命周期状态，可以随时从`Lifecycle`对象中移除。

图 40-1 展示了提供生命感知能力的关键元素之间的关系。

![image-OQ2GYDWO.jpg](img/image-OQ2GYDWO.jpeg)

图 40-1

## 40.4 生命周期状态与事件（Lifecycle States and Events）

当生命周期所有者的状态发生时，分配的`Lifecycle`对象将更新为新状态。在任何时刻，生命周期所有者都处于以下五个状态之一：

- `Lifecycle.State.INITIALIZED`
- `Lifecycle.State.CREATED`
- `Lifecycle.State.STARTED`
- `Lifecycle.State.RESUMED`
- `Lifecycle.State.DESTROYED`

当组件通过不同的状态转换时，`Lifecycle`对象将会在添加到列表的任何观察者上触发事件。在生命周期观察者内部，可以重写以下事件方法：

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

    // 执行响应 Resume 状态事件的任务

}
```

图 40-2 中的流程图说明了生命周期所有者的状态变化序列，以及每次状态转换之间触发观察者上的生命周期事件：

![image-B4LU1I2T.jpg](img/image-B4LU1I2T.jpeg)

图 40-2

## 40.5 总结（Summary）

本章介绍了生命感知的基础知识以及 Android Jetpack 中包含的 Android Lifecycle 包类和接口。该包包含了用于创建生命周期所有者、观察者和生命感知组件的多个类和接口。生命周期所有者分配了一个`Lifecycle`对象，该对象维护所有者的状态记录和订阅观察者列表。当所有者的状态变化时，通过生命周期事件方法通知观察者以响应变化。

下一章将创建一个 Android Studio 项目，演示如何使用和创建生命感知组件，包括创建生命周期观察者和所有者，以及处理生命周期状态变化和事件。

# 41. Android Jetpack 生命周期感知教程

上一章概述了生命感知知识，并列出了使在 Android 应用项目中实现此特点的关键类和接口。本章将在此知识的基础上，通过构建一个 Android Studio 项目来突出生命感知实际应用。

## 41.1 创建示例生命周期项目

从欢迎界面选择“New Project”快速启动选项，在出现的新项目对话框中，在点击“Next”按钮之前选择“Empty Views Activity”模板。

在`Name`字段中输入`LifecycleDemo`，并指定`com.ebookfrenzy.lifecycledemo`为包名。在点击“Finish”按钮之前，将最小 API 级别设置更改为`API 26: Android 8.0 (Oreo)`，并将语言菜单设置为 Java。

## 41.2 创建生命周期观察者

正如之前讨论的，activity 和 fragment 实现了`LifecycleOwner`接口，并准备好被其他对象观察。为了在实践中看到这一点，本教程的下一步是在项目中添加一个新类，该类能够观察`MainActivity`实例。

要添加新类，右键点击`app` -> `java` -> `com.ebookfrenzy.lifecycledemo`，选择`New -> Java Class`。在 New Class 对话框中，将类命名为`DemoObserver`并按回车键创建`DemoObserver.java`文件。该文件应会在编辑器中打开，内容如下：

```java
package com.ebookfrenzy.lifecycledemo

public class DemoObserver {

}
```

留在编辑器中，修改类文件声明它实现`DefaultLifecycleObserver`接口：

```java
package com.ebookfrenzy.lifecycledemo;

import androidx.lifecycle.DefaultLifecycleObserver;

public class DemoObserver {

}
```

下一步是重写`DefaultLifecycleObserver`类的方法。在本示例中，所有事件将被处理，并向 Logcat 面板输出消息。按照以下列表更新观察者类：

```java
package com.ebookfrenzy.lifecycledemo;

import android.util.Log;

import androidx.annotation.NonNull;

import androidx.lifecycle.LifecycleOwner;

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

## 41.3 添加观察者

观察者通过调用所有者`Lifecycle`对象的`addObserver()`方法添加到生命周期所有者中，该对象的引用通过调用`getLifecycle()`方法获取。编辑`MainActivity.java`类文件并编辑`onCreate()`方法以添加观察者：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {

    super.onCreate(savedInstanceState);

    .

    .

    getLifecycle().addObserver(new DemoObserver());

}
```

一旦创建了观察者类并将其添加到生命周期所有者的`Lifecycle`对象中，App 就可以测试了。

## 41.4 测试观察者

由于`DemoObserver`类向 Logcat 控制台输出诊断信息，因此如果配置了过滤器仅显示`DemoObserver`消息，将更容易看到输出。按照前文在“通过示例说明 Android Activity 状态更改”中列出的步骤，显示 Logcat 面板并在过滤器字段中输入以下内容：

`package:mine tag:DemoObserver`

当 App 成功启动后，Logcat 输出应指示以下生命周期状态变化和事件：

- `onCreate`
- `onStart`
- `onResume`

在 App 仍在运行时，执行设备旋转以触发 Activity 的销毁和重建，这将生成以下额外的输出：

- `onPause`
- `onStop`
- `onDestroy`
- `onCreate`
- `onStart`
- `onResume`

在进入本章的下一节之前，请花些时间将 App 的输出与上一章图 40-2 中的流程图进行对比。

## 41.5 创建生命周期所有者

本章的最后一个任务是创建一个自定义的生命周期所有者类，并演示如何在类内部触发事件并修改生命周期状态。

在 Project 工具窗口中右键点击`app` -> `java` -> `com.ebookfrenzy.lifecycledemo`项，并选择`New` -> `Java Class...`菜单选项添加新类。在`Create Class`对话框中按回车键之前将类命名为`DemoOwner`。加载新的`DemoOwner.java`文件到代码编辑器后，对其进行如下修改：

```java
package com.ebookfrenzy.lifecycledemo;

import androidx.lifecycle.Lifecycle;

import androidx.lifecycle.LifecycleOwner;

import androidx.lifecycle.LifecycleRegistry;

import androidx.annotation.NonNull;

public class DemoOwner implements LifecycleOwner {

}
```

该类需要一个`LifecycleRegistry`实例，该实例通过引用自身初始化，并配置`getLifecycle()`方法返回该`LifecycleRegistry`实例。声明一个变量来存储`LifecycleRegistry`引用，并编写一个构造函数来初始化`LifecycleRegistry`实例：

```java
public class DemoOwner implements LifecycleOwner {

    private final LifecycleRegistry lifecycleRegistry;

    public DemoOwner() {

        lifecycleRegistry = new LifecycleRegistry(this);

    }

    @NonNull

    @Override

    public Lifecycle getLifecycle() {

        return lifecycleRegistry;

    }

}
```

接下来，该类必须通知注册表生命周期状态的变化。这可以通过`LifecycleRegistry`对象的`markState()`方法标记状态，或者通过`handleLifecycleEvent()`方法触发生命周期事件来实现。自定义类中什么构成状态更改取决于类的用途。对于此示例，我们将添加一些在调用时会触发生命周期事件的方法：

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

.

.
```




`DemoOwner` 类中的最后一个更改是将`DemoObserver`类作为观察者添加。此调用通过向类构造函数添加以下内容来实现：

```java
public DemoOwner() {

    lifecycleRegistry = new LifecycleRegistry(this);

    getLifecycle().addObserver(new DemoObserver());

}
```

将`MainActivity.java`文件加载到代码编辑器，找到`onCreate()`方法，并添加代码创建`DemoOwner`类的实例并调用`startOwner()`和`stopOwner()`方法。请注意，添加`DemoObserver`作为观察者的调用已被移除。虽然单个观察者可以与多个所有者一起使用，在本情况下移除它是为了避免在 Logcat 工具窗口中产生重复且混淆的输出：

```java
.

.

private DemoOwner demoOwner;

@Override

protected void onCreate(Bundle savedInstanceState) {

    super.onCreate(savedInstanceState);

    getLifecycle().addObserver(new DemoObserver());

    demoOwner = new DemoOwner();

    demoOwner.startOwner();

    demoOwner.stopOwner();

}
```

## 41.6 测试自定义生命周期所有者

最后一次构建并运行 App，参考 Logcat 工具窗口，并确认观察者按以下顺序检测到创建、启动和停止生命周期事件：

- `onCreate`
- `onStart`
- `onStop`

注意，尽管没有在`DemoOwner`类中添加代码来手动执行此操作，“创建”状态更改仍被触发了。这些是在所有者实例首次创建以及处理`ON_STOP`事件时自动触发的。

## 41.7 总结

本章提供了在 Android App 中实现生命周期感知的实际演示，包括创建生命周期观察者以及设计和实现基础的生命周期所有者类。

## 42. 导航架构组件（Navigation Architecture Component）概述

如今很少有 Android App 仅由单个屏幕组成。事实上，大多数 App 包含多个屏幕，用户通过屏幕手势、按钮点击和菜单选择在这些屏幕之间进行导航。在引入 Android Jetpack 之前，在 App 中实现导航在很大程度上是一个手动编码过程，没有简单的方法来查看和组织可能复杂的导航路径。然而，随着导航架构组件的引入以及对导航图的支持，这种情况已经得到了极大改善。

## 42.1 理解导航

每个 App 都有一个主屏幕，它在 App 启动以及任何启动页（splash screen，即 App 加载时临时显示的品牌屏幕）之后出现。用户通常从此主屏幕执行任务，导致出现其他屏幕。这些屏幕通常以 App 内其他 Activity 和 Fragment 的形式存在。例如，一个消息 App 可能有一个列出消息的主屏幕，用户可以那里导航到联系人列表或设置屏幕。联系人列表屏幕可能允许用户导航到添加新用户或更新现有联系人的屏幕。从图上上看，App 的导航图如图 42-1 所示：

![image-B9NMCX99.jpg](img/image-B9NMCX99.jpeg)

此 组成 App 的每个屏幕（包括主屏幕）被称为目的地，通常是一个 Fragment 或 Activity。Android 导航架构使用导航栈跟踪用户在 App 内目的地之间的路径。当 App 首次启动时，主屏幕是第一个放入栈的目的地并成为当前目的地。当用户导航到另一个目的地时，该屏幕成为当前目的地并推入栈中。当用户导航到其他屏幕时，它们也会被推入栈。图 42-2 显示了假设性消息 App 在用户启动 App 并导航到“添加联系人”屏幕时导航栈的当前状态：

![image-29ZHPEBU.jpg](img/image-29ZHPEBU.jpeg)

图 42-2

当用户使用系统返回键导航回屏幕时，每个目的地都会从栈中弹出，直到主屏幕再次成为栈上的唯一目的地。在图 42-3 中，用户从添加联系人屏幕返回，将其从栈中弹出并使联系人列表屏幕成为当前目的地：

![image-BTHNXIXQ.jpg](img/image-BTHNXIXQ.jpeg)

图 42-3

在目的地之间导航和管理导航栈的所有工作都由导航控制器处理，由`NavController`类表示。

使用 Navigation 架构组件为 Android 项目添加导航是一个直观的过程，涉及导航宿主（navigation host）、导航图（navigation graph）、导航动作（navigation actions）以及少量的代码编写，以获取并交互导航控制器（navigation controller）实例。

## 42.2 声明导航主机

导航主机是一个嵌入到 Activity 用户界面布局中的特殊片段（`NavHostFragment`），作为用户进行导航的目标地的占位符。例如，图 42-4 显示了一个典型的 Activity 屏幕，并突出了由导航主机片段表示的区域：

![image-X5SHPY0F.jpg](img/image-X5SHPY0F.jpeg)

图 42-4

可以在 Android Studio 布局编辑器中通过从调面板的容器（Containers）部分拖放实例，或者通过如下方式手动编辑 XML，将`NavHostFragment`放置在 Activity 布局中：

```xml
xmlnsmx:app="http://schemas.android.com/apk/res-auto"

xmlns:tools="http://schemas.android.com/tools"

android:id="@+id/container"

android:layout_width="match_parent"

android:layout_height="match_parent"

tools:context=".MainActivity" >

<fragment

android:id="@+id/demo_nav_host_fragment"

android:name="androidx.navigation.fragment.NavHostFragment"

android:layout_width="match_parent"

android:layout_height="match_parent"

app:defaultNavHost="true"

app:navGraph="@navigation/navigation_graph" />
```

上述导航主机片段元素中注意的点是：`name`属性中对`NavHostFragment`的引用、将`defaultNavHost`设置为 true，以及将包含包含导航图的文件分配给`navGraph`属性。

当 Activity 启动时，此导航主机片段将被导航图中指定的首页目的地所替换。当用户在应用屏幕之间进行导航时，宿主片段将被对应目的地的片段所替换。

## 42.3 导航图

导航图是一个 XML 文件，包含了包含在应用导航中的目的地。除了这些目的地外，文件还包含定义目的地之间导航的导航动作，以及用于从一个目的地传递数据到另一个目的地的可选参数。Android Studio 包含一个导航图编辑器，可以使用可视化方式或手动编辑 XML 来设计图表并实现动作。

图 42-5 显示了设计模式下的 Android Studio 导航图编辑器：

![image-YN42QV8E.jpg](img/image-YN42QV8E.jpeg)

图 42-5

目的地列表 (A) 列出了图表中的所有目的地。从列表中选择一个目的地将定位并选中图中的相应目的地（这对于在大型图中定位特定目的地特别有用）。导航图面板 (B) 包含每个目的地的对话框，代表代表用户界面布局。在例例中，此图表包含两个名为`mainFragment`和`secondFragment`的目的地。目的地之间的箭头 (C) 代表导航动作连接。可以通过将鼠标指针悬停在源地的边缘直到出现圆圈，然后从圆圈点击并拖动到目的地来添加动作。属性面板 (D) 允许查看和修改当前所选目的地或动作连接的属性。在上面的图中，显示了动作的属性。通过点击标记为 E 的按钮并从菜单中选择选项来添加新目的地。可以选择将现有的片段或 Activity 作为目的地，或创建新的空白片段目的地。组件树面板 (F) 提供了导航图的分级概述。

可以通过将编辑器切换到代码模式来查看和修改导航图的底层 XML。接下来的 XML 列表代表了上图 42-5 所示目的地和动作连接的导航图：

```xml
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
```

导航图也可以拆分到多个文件中以改进组织结构并促进重用。当这样结构化时，嵌套图会被嵌入到根图中。要创建嵌套图，按住 Shift 点击要嵌套的目的，右键点击第一个目的地并选择“移动到嵌套图 -> 新图”（Move to Nested Graph -> New Graph）菜单选项。嵌套图将作为图中的新节点出现。双击嵌套图节点将图文件加载到编辑器中访问嵌套图。

## 42.4 访问导航控制器

从一个目的地导航到另一个目的地通常是响应应用内的事件的，例如按钮点击或菜单选择。在触发导航动作之前，代码必须先获取导航控制器实例的引用。这需要调用`Navigation`或`NavHostFragment`类的`findNavController()`方法。例如，下面的代码可以访问 Activity 的导航控制器。注意，为了使代码工作，Activity 必须包含一个导航主机片段：

```java
NavController controller = Navigation.findNavController(activity, R.id.nav_host_fragment);
```

在这种情况下，方法调用传递了 Activity 的引用和嵌入 Activity 布局中的导航主机 ID。

或者，可以通过将任何视图传递给方法来标识与视图关联的导航控制器：

```java
NavController controller = Navigation.findNavController(binding.button);
```

最后一种选项通过调用`NavHostFragment`类的`findNavController()`方法查找片段的导航控制器：

```java
NavController controller = NavHostFragment.findNavController(fragment);
```

## 42.5 触发导航动作

找到导航控制器后，通过调用控制器的`navigate()`方法并传递要执行动作的资源 ID 来触发导航动作。例如：

```java
controller.navigate(R.id.goToContactsList);
```

动作的 ID 在选择动作连接时定义在导航图编辑器的属性面板中。

### 42.6 传递参数

可以使用导航图文件中定义的参数从一个目的地传递到另一个目的地。参数由名称、类型和可选默认值组成，可以在 XML 中手动添加，也可以在图中选择动作箭头或目的地时使用属性面板添加。在图 42-6 中，声明了一个名为`contactsCount`的整数参数，其默认值为 0：

![image-CUWAM5CQ.jpg](img/image-CUWAM5CQ.jpeg)

图 42-6

一旦添加，参数将放置在接收目的地的 XML 元素元素，例如：

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

导航架构组件（Navigation Architecture Component）提供了两种在目的地之间传递数据的技术。一种方法是将数据放入`Bundle`对象中，并在操作（action）期间将其传递给目的地，然后在那里对其进行解包并提取参数。

这种特定方法的主要缺点是它不是“类型安全的”。换句话说，如果接收端目的地对参数的处理类型与其声明的类型不同（例如，将字符串视为整数），编译器将不会捕获此错误，并且很可能在运行时引发问题。

更好的选择（也是本书所采用的方法）是`safeargs`。`safeargs`是适用于 Android Studio Gradle 构建系统的插件，它能够自动生成特殊类，允许以类型安全的方式传递参数。`safeargs`的参数传递方法将在下一章（《Android Jetpack 导航组件实教程》）中进行描述和演示。

## 42.7 总结

Android 应用程序用户界面中的导航是指用户在不同屏幕之间来回移动的能力。过去这种实现方式非常耗时且难以组织，而现在 Android Studio 和导航架构组件使得在 Android 应用项目中实现和管理导航变得更加简单。

应用中的不同屏幕被称为`destinations`（目的地），通常由片段（fragments）或活动（activities）表示。所有应用都有一个首页目的地，包括应用首次加载时显示的屏幕。该布局的内容区域被导航主机片段（navigation host fragment）取代，当用户导航应用时，它会被其他目的地片段片段。导航路径由导航图文件定义，该文件由目的地以及连接它们的操作组成，以及需要在目的地之间传递的任何参数。导航由导航控制器（navigation controllers）处理，它们除了管理导航栈外，还提供了从应用代码内部启动导航操作的方法。

## 43. Android Jetpack 导航组件实教程

上一章描述了 Android Jetpack 导航组件以及它如何与 Android Studio 的导航图表功能集成，为在 Android 应用的屏幕之间实现导航提供简单的方法。在本章中，将创建一个新的 Android Studio 项目，使用这些导航功能实现一个包含多个屏幕的示例应用。除了演示 Android Studio 导航图编辑器的用法外，示例项目还将实现使用类型安全参数在源屏幕和目的地屏幕之间传递数据。

## 43.1 创建 NavigationDemo 项目

从欢迎界面选择“New Project”（新建项目）选项，在弹出的新项目对话框中，点击“Next”（下一步）按钮之前选择“Empty Views Activity”模板。

在`Name`（名称）字段中输入`NavigationDemo`并指定`com.ebookfrenzy.navigationdemo`为包名。在点击“Finish”（完成）按钮之前，将“Minimum API level”（最低 API 级别）设置改为`API 26`：Android 8.0 (Oreo)，并将语言菜单设置为`Java`。

## 43.2 向构建配置中添加导航

新的 Empty Views Activity 项目默认不会在构建配置文件中包含导航组件库。接一步是将导航库添加到构建配置中。首先从编辑`Gradle Scripts -> libs.version.toml`文件开始，并按如下方式对其修改（请注意，现在可能有更新版本的库）：

```toml
[versions]

.

.

navigationFragment = "2.8.3"

[libraries]

.

.

androidx-navigation-fragment = { group = "androidx.navigation", name = "navigation-fragment", version.ref = "navigationFragment" }
```

接下来，打开`Gradle Scripts -> build.gradle.kts (Module: app)`文件，并在`dependencies`部分添加以下指令。此外，借此机会为此模块启用视图绑定（view binding）：

```kotlin
android {



```
buildFeatures {
    viewBinding = true
}
```

在文件中添加导航依赖后，点击“Sync Now”（立即同步）链接以重新同步项目的构建配置。

## 43.3 创建导航图资源文件

在构建配置中添加了导航库后，现在可以将导航图资源文件添加到项目中了。正如“导航架构组件概述”所述，这是一个 XML 文件，包含了用户将能够在其中导航的片段和活动，以及执行切换的操作以及在在之间之间传递的任何数据。

在`Project`（项目）工具窗口中，找到`res`文件夹（`app -> res`），右键点击它，并选择`New -> Android Resource File`菜单选项：

![image-S3L978IS.jpg](img/image-S3L978IS.jpeg)

图 43-1

在选择了该菜单项后，将出现`New Resource File`对话框。在此对话框中，将文件命名为`navigation_graph`，并在点击`OK`按钮创建文件之前，如图 43-2 所示将`Resource type`（资源类型）菜单更改为`Navigation`。

![image-TJLZKUS5.jpg](img/image-TJLZKUS5.jpeg)

图 43-2

导航图资源文件添加到项目后，它将出现在主面板中，准备好添加新的目的地。在添加任何目的地之前，将编辑器切换到`Code`模式并检查图表的 XML：

```xml
xmlns:app="http://schemas.android.com/apk/res-auto"
android:id="@+id/navigation_graph">
```

将编辑器切换回`Design`（设计）模式，并注意`Destinations`（目的地）面板的`Host`（主机）部分指示项目内未检测到导航主机片段：

![image-KFSDUFYK.jpg](img/image-KFSDUFYK.jpeg)

图 43-3

在向导航图添加任何目的地之前，下一步是向项目添加导航主机片段。

## 43.4 声明导航主机

对于本项目，导航主机片段将包含在主活动的用户界面布局中。首先，在`Project`工具窗口中找到主布局文件（`app -> res -> layout -> activity_main.xml`），将其加载到布局编辑器并删除默认的`TextView`组件。

在`Design`模式下，从`Palette`（调色板）的`Containers`部分拖入`NavHostFragment`元素，并放置在活动布局的容器区域，如图 43-4 中的箭头所示：

![image-39S7IJXH.jpg](img/image-39S7IJXH.jpeg)

图 43-4

从弹出的`Navigation Graphs`对话框中选择之前创建的`navigation_graph`文件并点击`OK`按钮。

在布局中选中新添加的`NavHostFragment`实例，使用`Attributes`工具窗口将元素的 ID 更改为`demo_nav_host_fragment`，然后点击`Infer constraints`按钮。

将布局编辑器切换到`Code`模式并查看 XML 文件。注意编辑器正确配置了`navigation graph`属性以引用`navigation_graph.xml`文件，并且`defaultNavHost`属性已设置为 true：

```xml
xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context=".MainActivity">

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
```

返回`navigation_graph.xml`文件并确认`NavHostFragment`实例已检测到（在更改生效之前，可能需要关闭并重新打开文件）：

![image-RUB0C0KQ.jpg](img/image-RUB0C0KQ.jpeg)
图 43-5

## 43.5 添加导航目的地

继续停留在导航图中，现在是时候添加第一个目的地了。点击图 43-6 所示的新目的地按钮来选择或创建目的地：

![image-VG5T7CV8.jpg](img/image-VG5T7CV8.jpeg)
图 43-6

接下来，从菜单中选择`Create new destination`（创建新目的地）选项。在弹出的对话框中，选择`Fragment (Blank)`模板，将新 fragment 命名为`FirstFragment`，并将布局命名为`fragment_first`，然后点击`Finish`按钮。在项目重新构建的短暂等待后，新 fragment 将作为目的地出现在图中，如图 43-7 所示：

![image-JOMEIUPG.jpg](img/image-JOMEIUPG.jpeg)
图 43-7

目的地节点上方的房屋图标表示这是起始目的地。这意味着当`NavHostFragment` activity 创建时，该目的地将是第一个显示的内容。要将起始目的地更改为另一个，请在图中选择该节点并点击工具栏上的主按钮。

通过将编辑器切换到`Code`模式查看导航图的 XML 内容：

```xml
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:id="@+id/navigation_graph"
app:startDestination="@id/firstFragment">

android:id="@+id/firstFragment"
android:name="com.ebookfrenzy.navigationdemo.FirstFragment"
android:label="fragment_first"
tools:layout="@layout/fragment_first" />
```

在执行任何导航之前，图至少还需要一个目的地。重复上述步骤，添加一个名为`SecondFragment`的 fragment，布局文件命名为`fragment_second`。新 fragment 将作为另一个目的地出现在图中，如图 43-8 所示：

![image-NZ4CONWN.jpg](img/image-NZ4CONWN.jpeg)
图 43-8

## 43.6 设计目的地 Fragment 布局

在添加用于目的地间跳转的 action（动作）之前，现在是为图中两个目的地 fragment 添加一些用户界面组件的好时机。首先，双击`firstFragment`目的地，使`fragment_first.xml`文件加载到布局编辑器中，然后选择并删除默认的`TextView`实例。在`Component Tree`（组件树）面板中，右键点击`FrameLayout`条目并选择`Convert from FrameLayout to ConstraintLayout`（从 FrameLayout 转换为 ConstraintLayout）菜单选项，在生成的转换对话框中接受默认设置：

![image-Z93X6HK8.jpg](img/image-Z93X6HK8.jpeg)
图 43-9

使用`Attributes`（属性）工具窗口将`ConstraintLayout`的 ID 改为`constraintLayout`，然后将`Button`和`Plain Text EditText`控件拖放到布局中，使其看起来像下面的图 43-10 所示：

![image-J27KU0VQ.jpg](img/image-J27KU0VQ.jpeg)
图 43-10

一旦视图位置正确，点击工具栏上的`Infer constraints`（推断约束）按钮以为布局添加任何缺失的约束。选择`EditText`视图并使用`Attributes`工具窗口删除默认的“Name”文本，并将控件的 ID 更改为`userText`。接下来，将按钮的文本属性更改为“Navigate”，并将其提取为字符串资源。

返回`navigation_graph.xml`文件并双击`secondFragment`目的地，将`fragment_second.xml`文件加载到布局编辑器中。选择并删除默认的`TextView`实例，重复上述步骤将`FrameLayout`转换为`ConstraintLayout`，并将 id 更改为`constraintLayout2`。接下来，拖入一个新的`TextView`控件将其置在布局中心，并点击`Infer constraints`按钮以添加任何缺失的约束。选中新的`TextView`后，使用`Attributes`面将 ID 更改为`argText`。

## 43.7 为导航图添加 Action

现在图中已经添加了两个目的地并设计了相应的用户界面布局，项目需要一种让用户从第一个 fragment 导航到第二个 fragment 方法。这将通过向图中添加一个 action 来实现，然后可以在应用代码中引用它。

要建立以第一个 fragment 为起点、第二个 fragment 为目的地的 action 连接，请打开导航图并将鼠标指针悬停在`firstFragment`目的地右侧边缘的垂直中心，直到出现一个高亮的圆圈，如图 43-11 所示：

![image-QY0W258P.jpg](img/image-QY0W258P.jpeg)
图 43-11

点击圆圈内部并将生成的连线拖到`secondFragment`目的地：

![image-UGON49A7.jpg](img/image-UGON49A7.jpeg)
图 43-12

释放连线以建立起点和目的地之间的 action 连接，此时连线将变为箭头，所示：

![image-AL2IUPG.jpg](img/image-AL2IUPG.jpeg)
图 43-13 (注：此处对应原文描述的逻辑位置)

你可以可以通过选中 action 并按下`Delete`键随时删除该连接。选中 action 后，在`Attributes`窗口查看属性并将 ID 更改为`mainToSecond`。切换编辑器到`Code`模式查看 action 已包含在 XML 中：

```xml
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:id="@+id/navigation_graph"
app:startDestination="@id/firstFragment">

android:id="@+id/firstFragment"
android:name="com.ebookfrenzy.navigationdemo.FirstFragment"
android:label="fragment_first"
tools:layout="@layout/fragment_first" />

<action
    android:id="@+id/mainToSecond"
    app:destination="@id/secondFragment" />

android:id="@+id/secondFragment"
android:name="com.ebookfrenzy.navigationdemo.SecondFragment"
android:label="fragment_second"
tools:layout="@layout/fragment_second" />
```

## 43.8 实现 OnInteractionListener

在添加触发 action 的代码之前，`MainActivity`类需要实现`OnInteractionListener`接口。该接口是在导航图编辑器创建空白 fragments 时在 Fragment 类中生成的。为了符合接口，activity 需要一个名为`onInteraction()`的方法来实现 fragment 与 activity 之间的通信。

编辑`MainActivity.java`文件使其内容如下：

```java
public class MainActivity extends AppCompatActivity implements SecondFragment.OnInteractionListener {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    @Override
    public void onInteraction(Uri uri) {
    }
}
```

如果 Android Studio 报告`OnInteractionListener`未定义（某些 Android Studio 版本会自动添加，而某些版本不会），请编辑`SecondFragment.java`文件并添加以下内容：

```java
import android.net.Uri;

public interface OnInteractionListener {
    // TODO: 更新参数类型和名称
    void onInteraction(Uri uri);
}
```

## 43.9 为目的地 Fragment 添加 View Binding 支持

由于我们将在 fragment 布局中某些视图，必须修改当前代码启用 view binding 支持。首先编辑`FirstFragment.java`文件并进行以下更改：

```java
import com.ebookfrenzy.navigationdemo.databinding.FragmentFirstBinding;

public class FirstFragment extends Fragment {

    private FragmentFirstBinding binding;

    @Nullable
    @Override
    public View onCreateView(@NonNull LayoutInflater inflater, @Nullable ViewGroup container,
                             @Nullable Bundle savedInstanceState) {
        return inflater.inflate(R.layout.fragment_first, container, false);
    }
}
```

```java
binding = FragmentFirstBinding.inflate(inflater, container, false);
return binding.getRoot();
}

@Override
public void onDestroyView() {
    super.onDestroyView();
    binding = null;
}
```

对`SecondFragment.java`文件重复上述步骤，并引用`FragmentSecondBinding`。

## 43.10 触发动作

现在动作已添加到导航图（navigation graph）中，下一步是在第一个片段（fragment）中添加一些代码，在点击`Button`组件时触发该动作。找到`FirstFragment.java`文件，将其加载到代码编辑器，并重写`onViewCreated()`方法以获取按钮实例的引用，并配置`OnClickListener`实例以便在用户点击按钮时调用它：

```java
import androidx.annotation.NonNull;
import androidx.annotation.Nullable;
import android.widget.Button;
import androidx.navigation.Navigation;
```



```java
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

上述代码获取了导航控制器（navigation controller）的引用，并在该实例上调用`navigate()`方法，将导航动作的资源 ID 作为参数传递。

编译并运行应用，验证点击第一个片段中的按钮跳转到第二个片段。

作为这种设置监听器方法的替代方案，`Navigation`类还包含一个名为`createNavigateOnClickListener()`的方法，它提供了一种更高效的方法来设置监听器并导航到目的地。因此，可以使用以下单行代码来实现相同的跳转效果：

```java
binding.button.setOnClickListener(
    Navigation.createNavigateOnClickListener(
        R.id.mainToSecond, null));
```

## 43.11 使用 Safeargs 传递数据

下一个目标是将第一个片段中`EditText`视图中输入的文本传递给第二个片段，并在该片段中显示在`TextView`组件上。正如上一章所述，Android Navigation 组件支持两种传递数据的方法。本章将使用类型安全的参数传递（type-safe argument passing）。

使用`safeargs`的第一步是将`safeargs`插件添加到 Gradle 构建配置中。使用 Project 工具窗口，找到并编辑`Gradle Scripts -> libs.versions.toml`文件，如下：

```toml
[libraries]

androidx-navigation-safe-args-gradle-plugin = { module = "androidx.navigation:navigation-safe-args-gradle-plugin", version.ref = "navigationFragment" }
```

接下来，编辑项目级别的`build.gradle.kts`文件（`Gradle Scripts -> build.gradle.kts (Project: NavigationDemo)`），如下所示添加插件依赖：

```kotlin
// 顶层构建文件，可以在此处添加所有子项目/模块的通用配置选项

buildscript {
    dependencies {
        classpath(libs.androidx.navigation.safe.args.gradle.plugin)
    }
}
```

接着，编辑模块级别的`build.gradle.kts`文件（`Gradle Scripts -> build.gradle.kts (Module :app)`），按如下所示应用插件并重新同步项目：

```kotlin
plugins {
    alias(libs.plugins.android.application)
    id("androidx.navigation.safeargs")
}
```

下一步是定义目的地将接收的任何参数，在本例中即为第二个片段。编辑导航图，选择`secondFragment`目的地，并在 Attributes（属性）工具窗口中找到`Arguments`部分。点击`+`按钮（如图 43-14 所示）为目的地添加一个新参数：

![image-R830LDD8.jpg](img/image-R830LDD8.jpeg)

图 43-14

点击`+`按钮后，会弹出一个框，需要在其中输入参数名称、类型和默认值。将参数命名为`message`，类型设置为`String`，在默认值字段输入`No Message`，并点击`Add`按钮：

![image-92HC2MYY.jpg](img/image-92HC2MYY.jpeg)

图 43-15

新配置的参数将如下出现在`navigation_graph.xml`文件的`secondFragment`元素中：

```xml
android:id="@+id/secondFragment"

android:name="com.ebookfrenzy.navigationdemo.SecondFragment"

android:label="fragment_second"

tools:layout="@layout/fragment_second">

android:name="message"

app:argType="string"

android:defaultValue="No Message" />
```

下一步是在`FirstFragment.java`文件中添加代码，从`EditText`视图中提取文本并在导航动作期间将其传递给第二个片段。这将涉及使用由`safeargs`插件自动生成的某些特殊导航类。目前，导航涉及`FirstFragment`类、`SecondFragment`类、名为`mainToSecond`的导航动作以及名为`message`的参数。

当项目构建时，`safeargs`插件将生成以下额外的类，用于在导航期间传递和接收参数：

- `FirstFragmentDirections`：代表导航动作的起点（在类名后加上“Directions”），并提供动作对象的访问。
- `ActionMainToSecond`：代表执行跳转的动作（根据导航文件中命名并加上“Action”）。该类包含目的地配置的每个参数的 setter 方法。例如，由于第二个片段包含名为`message`的参数，该类包含名为`setMessage()`的方法。配置完成后，将该类的实例传递给导航控制器的`navigate()`方法以导航到目的地。
- `SecondFragmentArgs`：目的地用于访问从起点传递的参数的类（在类名后加上“Args”）。该类包含每个参数的 getter 方法（即`getMessage()`）。

使用这些类，可以修改`FirstFragment.java`文件中`onViewCreated()`方法内的`OnClickListener`代码，以提取`EditText`组件的当前文本，将其应用于动作并启动到第二个片段的跳转：

```java
binding.button.setOnClickListener(view1 -> {
    FirstFragmentDirections.MainToSecond action =
        FirstFragmentDirections.mainToSecond();

    action.setMessage(binding.userText.getText().toString());

    Navigation.findNavController(view1).navigate(action);
});
```

如果 Android Studio 报告`FirstFragmentDirections`未定义，请使用`Build -> Make Project`菜单重新构建项目。

上述方法中的代码首先获取`TextView`小部件的引用。接下来，调用`SecondFragmentArgs`类的`fromBundle()`方法来提取从源接收到的`SecondFragmentArgs`对象。由于此示例中的参数在`navigation_graph.xml`文件中被命名为`message`，因此在`args`对象上调用相应的`getMessage()`方法来获取字符串值。然后，将该字符串显示在`TextView`小部件上。

编译并运行应用，在点击`Button`小部件之前输入一些文本。当第二个片段目标出现时，`TextView`应该显示在第一个片段中输入的文本，这表明数据已成功在导航目的地之间传递。

## 43.12 总结

本章提供了一个使用`Navigation Architecture Component`（导航架构组件）和`Android Studio navigation graph editor`（导航图编辑器）实现 Android 应用导航的实用示例。涵盖的话包括包含现有和新目标片段的导航图、在 Activity 布局中嵌入导航宿主片段（navigation host fragment）、编写触发导航事件的代码，以及使用`safeargs`插件在目的地之间传递参数。

# 44. MotionLayout 简介

`MotionLayout`类提供了一种为用户界面布局中的视图添加动画效果的简单方法。本章将首先对`MotionLayout`进行概述并介绍`MotionScenes`（运动场景）、`Transitions`（过渡）和`Keyframes`（关键帧）的概念。在涵盖这些基础之后，接下来的两章（标题为“Android MotionLayout 编辑教程”和“MotionLayout 循环教程”）将通过创建示例项目提供`MotionLayout`动画的更多细节和示例。

## 44.1 MotionLayout 概述

`MotionLayout`是一种布局容器，其主要目的是为布局内视图从一个状态到另一个状态的转换制作动画。例如，`MotionLayout`可以使`ImageView`实例在指定时间内从屏幕左上角移动到右下角。除了视图的位置，其他属性的变化也可以制作动画，例如颜色、大小或旋转角度。这些状态更改还可以进行插值（使得视图在整个动画过程中移动、旋转并改变大小）。

使用`MotionLayout`的视图运动可以在两点之间沿直线执行，也可以实现为遵循起点和终点之间不同位置的中间点的路径。`MotionLayout`还支持使用触摸和滑动来启动和控制动画。

`MotionLayout`动画完全在 XML 中声明，通常不需要编写代码。这些 XML 声明可以在 Android Studio 代码编辑器中手动实现、使用`MotionLayout`编辑器进行视觉化实现，或结合两种方法。

## 44.2 MotionLayout

在实现动画时，通常用于用户界面的`ConstraintLayout`容器必须先转换为`MotionLayout`实例（可以通过在布局编辑器中右键点击`ConstraintLayout`并选择`Convert to MotionLayout`菜单项完成）。`MotionLayout`至少需要`2.0.0`版本的`ConstraintLayout`库。

由于它是`ConstraintLayout`的子类，它支持`ConstraintLayout`的所有布局功能。因此，在使用`MotionLayout`设计不需要动画的视图时，可以使用类似的设计。

对于需要动画的视图，会声明两个`ConstraintSets`，定义视图在动画开始和结束时的外观和位置。`transition`声明定义了关键帧，用于在这些状态之间对目标视图应用额外效果，以及用于启动和控制动画的点击和滑动处理程序。

开始和结束的`ConstraintSets`以及`transitions`声明在一个`MotionScene` XML 文件中。

## 44.3 MotionScene

正如我们在前面的章节中所看到的，XML 布局文件包含配置呈现给用户的静态视图的外观和布局行为所需的信息，在使用`MotionLayout`时也是如此。对于非静态视图（换句话说，即要制作动画的视图），这些视图仍然声明在布局文件中，但与这些视图相关的开始、结束和过渡声明存储在一个名为`MotionScene`的独立 XML 文件中（之所以这样做是因为所有声明都定义在一个`MotionScene`元素内）。该文件被导入到布局 XML 文件中，包含开始和结束的`ConstraintSets`以及`Transition`声明（单个文件可以包含多个`ConstraintSet`对和`Transition`声明，允许将不同的动画针对用户界面布局中的特定视图）。

接下来的代码列表显示了一个`MotionScene`文件的模板：

```xml
xmlns:android="http://schemas.android.com/apk/res/android"

xmlns:motion="http://schemas.android.com/apk/res-auto">

motion:constraintSetEnd="@+id/end"

motion:constraintSetStart="@id/start"

motion:duration="1000">
```

在上述 XML 中，声明了名为`start`和`end`（尽管可以使用任何名称）的`ConstraintSets`，它们目前尚未包含任何约束元素。`Transition`元素定义了这些`ConstraintSets`代表动画的起点终点，并包含一个空的`KeyFrameSet`元素，准备填充额外的动画关键帧。`Transition`元素还包含一个毫秒持续时间属性，用于控制动画的运行时间。

`ConstraintSets`并不意味着视图的运动。可以让开始和结束集声明屏幕上的相同位置，然后使用过渡来制作其他属性的变化，例如缩放和旋转。

## 44.4 配置 ConstraintSets

`MotionScene`文件中的`ConstraintSets`允许将全套`ConstraintLayout`设置应用于视图的位置、大小以及与父容器或其他视图的关系。此外，在`ConstraintSet`声明中还可以包含以下属性：

- `alpha`
- `visibility`
- `elevation`
- `rotation`
- `rotationX`
- `rotationY`
- `translationX`
- `translationY`
- `translationZ`
- `scaleX`
- `scaleY`

例如，为了让视图在动画期间旋转 180 度，可以在开始和结束约束中声明以下内容：

```xml
.

motion:layout_constraintStart_toStartOf="parent"

android:rotation="0">
```

```xml
.

motion:layout_constraintBottom_toBottomOf="parent"

android:rotation="180">
```

上述更改告诉`MotionLayout`视图从 0 度开始，然后在动画期间旋转完整的 180 度，最后处于倒置状态。

## 44.5 自定义属性

除了上述列出的标准属性外，还可以指定一系列自定义属性（使用`CustomAttribute`声明）。事实上，视图类型上可用的几乎任何属性都可以作为自定义属性包含在动画中。要标识属性名称，请从目标视图类的文档中找到 getter/setter 名称，删除`get/set`前缀，并将第一个字符转换为小写。例如，在代码中更改`Button`视图的背景颜色时，我们可能会如下调用`setBackground()`设置方法：

```java
myButton.setBackgroundColor(Color.RED)
```

在约束集（constraint set）或关键帧中设置此属性时，属性名称将为`backgroundColor`。除了属性名称外，还必须使用以下选项列表中的相应类型声明值：

- `motion:customBoolean` - 布尔型属性值。
- `motion:customColorValue` - 颜色属性值。
- `motion:customDimension` - 维度属性值。
- `motion:customFloatValue` - 浮点数属性值。
- `motion:customIntegerValue` - 整数属性值。
- `motion:customStringValue` - 字符串属性值。

例如，颜色设置需要使用`customColorValue`类型进行赋值：

```xml
motion:attributeName="backgroundColor"

motion:customColorValue="#43CC76" />
```

例如，以下来自`MotionScene`文件的片段除了将背景颜色从绿色改为红色外，还为一个视图声明了起始和结束约束：

```xml
android:layout_width="wrap_content"

android:layout_height="wrap_content"

motion:layout_editor_absoluteX="21dp"

android:id="@+id/button"

motion:layout_constraintTop_toTopOf="parent"

motion:layout_constraintStart_toStartOf="parent">

motion:attributeName="backgroundColor"
```



`motion:customColorValue="#33CC33"` />

`android:layout_width="wrap_content"`

`android:layout_height="wrap_content"`

`motion:layout_editor_absoluteY="21dp"`

`android:id="@+id/button"`

`motion:layout_constraintEnd_toEndOf="parent"`

`motion:layout_constraintBottom_toBottomOf="parent" >`

`motion:attributeName="backgroundColor"`

`motion:customColorValue="#F80A1F" />

## 44.6 触发动画

如果没有某些事件告诉 `MotionLayout` 开始动画，`MotionScene` 文件中的任何设置都将不会影响布局（视图将根据起始 `ConstraintSet` 中的设置进行定位除外）。

动画可以配置为响应屏幕点击（`OnClick`）或滑动动作（`OnSwipe`）手势来启动。`OnClick` 处理器会使动画开始并运行直到完成，而 `OnSwipe` 则将同步动画，沿时间轴往回移动以匹配触摸动作。`OnSwipe` 处理器还会响应屏幕上的“飞掷”动作。`OnSwipe` 处理器还提供了选项，用于配置动画如何响应不同方向的拖拽，以及滑动锚定的目标视图的哪侧。这允许例如，向左的拖拽动作可以使视图向相应方向移动，同时防止向上运动导致视图向侧移动（除非这确实是需要的行为）。

`OnSwipe` 和 `OnClick` 声明包含在 `MotionScene` 文件的 `Transition` 元素中。在这两种情况下，都必须指定视图 ID。例如，要实现一个响应锚定在名为 `button` 的视图底的向下拖拽动作的 `OnSwipe` 处理器，应将以下 XML 放在 `Transition` 元素中：

```
motion:constraintSetEnd="@+id/end"
motion:constraintSetStart="@id/start"
motion:duration="1000"
motion:touchAnchorId="@+id/button"
motion:dragDirection="dragDown"
motion:touchAnchorSide="bottom" />
```

或者，为同一个按钮添加 `OnClick` 处理器：

```
motion:clickAction="toggle" />
```

在上面的示例中，动作已设置为切换（toggle）模式。这种模式和其他可用选项可以总结如下：

- `toggle` - 动画到相反状态。例如，如果视图当前处于过渡起点，它将过渡到终点，反之亦然。
- `jumpToStart` - 立即切换到起始状态，不进行动画。
- `jumpToEnd` - 立即切换到结束状态，不进行动画。
- `transitionToStart` - 带动画过渡到起始状态。
- `transitionToEnd` - 带动画过渡到结束状态。

## 44.7 弧形运动

默认情况下，视图位置的移动将在起点和终点之间沿直线移动。要将运动更改为弧形路径，请在起始约束中使用如下所示的 `pathMotionArc` 属性，并配置 `startHorizontal` 或 `startVertical` 设置来定义弧形是凹形还是凸形：

```
android:layout_width="wrap_content"
android:layout_height="wrap_content"
motion:layout_editor_absoluteX="21dp"
android:id="@+id/button"
motion:layout_constraintTop_toTopOf="parent"
motion:layout_constraintStart_toStartOf="parent"
motion:pathMotionArc="startVertical" >
```

图 44-1 展示了 `startVertical` 和 `startHorizontal` 弧形与默认直线运动的对比：

![image-HSR4H77F.jpg](img/image-HSR4H77F.jpeg)

图 44-1

## 44.8 关键帧

到目前为止概述的所有 `ConstraintSet` 属性仅适用于动画的起点和终点。也就是说，如果旋转属性在终点被设置为 `180°`，那么旋转将在动画开始时开始，并在到达终点时完成。因此，无法配置旋转在动画进行到 `50%` 处达到 `180°`，然后在终点回到原始方向。

关键帧（Keyframes）用于定义动画期间发生状态变化的中间点。例如，可以声明关键帧，使视图的背景颜色在动画进行到 `50%` 处变为蓝色，在 `75%` 处变为绿色，然后在终点恢复原始颜色。关键帧实现在 `MotionScene` 文件的 `Transition` 元素内部，嵌入 `KeyFrameSet` 元素中。

`MotionLayout` 支持多种类型的关键帧，总结如下：

### 44.8.1 属性关键帧

属性关键帧（使用 `KeyAttribute` 声明）允许在动画的中间点更改视图属性。`KeyAttribute` 支持上述 `ConstraintSets` 中的属性，并能够指定更改在时间轴何时生效。例如，以下关键帧声明将按钮在水平（`scaleX`）和垂直（`scaleY`）方向逐渐增大，在时间轴的 `50%` 处达到全尺寸。在剩余的时间时间内，视图将缩小到原始尺寸：

```
motion:constraintSetEnd="@+id/end"
motion:constraintSetStart="@id/start"
motion:duration="1000"

<motion:KeyAttribute
    motion:motionTarget="@+id/button"
    motion:framePosition="50"
    android:scaleX="2.0" />

<motion:KeyAttribute
    motion:motionTarget="@+id/button"
    motion:framePosition="50"
    android:scaleY="2.0" />
```

### 44.8.2 位置关键帧

位置关键帧（`KeyPosition`）修改视图在起点和终点之间移动时遵循的路径。通过在时间轴上的不同点放置关键位置，可以对动画应用任何复杂的路径。位置使用 `x` 和 `y` 坐标结合时间轴中的对应点进行声明。这些坐标必须相对于以下坐标系之一声明：

- `parentRelative` - `x` 和 `y` 坐标相对于父容器，坐标以百分比（表示为 `0.0` 到 `1.0` 之间的值）指定：

![image-FDCS3SLT.jpg](img/image-FDCS3SLT.jpeg)

图 44-2

- `deltaRelative` - 并不是相对于父，`x` 和 `y` 坐标相对于起始和结束位置。例如，起点为 `(0, 0)`，终点为 `(1, 1)`。请记住 `x` 和 `y` 坐标可以是负值：

![image-2S31SXBP.jpg](img/image-2S31SXBP.jpeg)

图 44-3

- `pathRelative` - `x` 和 `y` 坐标相对于路径，其中起点和终点之间的直线作为图表的 `X` 轴。再次强调，坐标以百分比（`0.0` 到 `1.0`）的形式表示。这与 `deltaRelative` 坐标空间相似，但它考虑了路径的角度。再次强调，坐标可能为负值：

![image-2XZNDA75.jpg](img/image-2XZNDA75.jpeg)

图 44-4

例如，下方的 `ConstraintSets` 在设备屏幕的侧边声明了起点和终点。默认情况下，使用这些点的视图过渡将沿横跨屏幕的直线移动，如图 44-5 所示：

![image-5T1BGL60.jpg](img/image-5T1BGL60.jpeg)

图 44-5

但是，如果要求视图遵循类似于图 44-6 所示的路径，那么：

![image-3JIN9NVT.jpg](img/image-3JIN9NVT.jpeg)

图 44-6

为了实现这一点，可以在过渡中按如下方式声明关键帧位置点：

```
<motion:KeyPosition
    motion:motionTarget="@+id/button"
    motion:framePosition="25"
    motion:keyPositionType="pathRelative"
    motion:percentY="0.3"
    motion:percentX="0.25"/>

<motion:KeyPosition
    motion:motionTarget="@+id/button"
    motion:framePosition="75"
    motion:keyPositionType="pathRelative"
    motion:percentY="-0.3"
    motion:percentX="0.75"/>
```

上述元素使用 `pathRelative` 坐标系在路径的 `25%` 和 `75%` 处创建关键帧位置点。第一个位置位于坐标 `(0.25, 0.3)`，第二个位于 `(0.75, -0.3)`。这些位置关键帧可以像下方图 44-7 所示进行可视化：

![image-IOWMZP6D.jpg](img/image-IOWMZP6D.jpeg)

图 44-7

## 44.9 时间线性

在没有额外设置的情况下，上述概述动画将以恒定速度执行。要改变动画速度（例如，使其加速后减速），可以在 `ConstraintSet` 或 `Keyframe` 中使用过渡缓动属性（`transitionEasing`）。

对于复杂的缓动需求，可以通过在三次贝塞尔曲线上绘制数据点来定义线性度，例如：

```
motion:layout_constraintBottom_toBottomOf="parent"
motion:transitionEasing="cubic(0.2, 0.7, 0.3, 1)"
android:rotation="360">
```

如果你不熟悉贝塞尔曲线，可以考虑使用以下 URL 上的在线曲线生成器：

[`cubic-bezier.com/`](https://cubic-bezier.com/)

然而，对于大多数需求，可以使用内置的标准值 `accelerate`（加速）和 `decelerate`（减速）来指定缓动：

```
motion:layout_constraintBottom_toBottomOf="parent"
motion:transitionEasing="decelerate"
android:rotation="360">
```

## 44.10 KeyTrigger

触发关键帧（`KeyTrigger`）允许在动画到达时间轴内指定的帧位置时调用视图上的方法。这同样考虑了动画的方向。例如，可以根据动画正向运行还是反向运行调用不同的方法。考虑一个当动画移动超过时间轴的 `20%` 时变得可见的按钮。在 `Transition` 元素的 `KeyFrameSet` 中按如下使用 `onPositiveCross` 属性实现 `KeyTrigger`：

```
<motion:KeyTrigger
    motion:framePosition="20"
    motion:onPositiveCross="show"
    motion:motionTarget="@id/button"/>
```

同样，如果当动画反转并降至 `10%` 以下时隐藏同一个按钮，可以使用 `onNegativeCross` 属性添加第二个键触发器：

```
<motion:KeyTrigger
    motion:framePosition="10"
    motion:onNegativeCross="show"
    motion:motionTarget="@id/button2"/>
```

如果动画使用切换操作（toggle action），请使用 `onCross` 属性：

```
<motion:KeyTrigger
    motion:framePosition="10"
    motion:onCross="show"
    motion:motionTarget="@id/button2"/>
```

## 44.11 Cycle 和 Time Cycle Keyframes

虽然位置关键帧可以用于向动画添加中间状态变化，但如果需要实现大量的重复位置和变化，这将很快变得繁琐。对于需要以预测的变化重复执行状态变化的情况，`MotionLayout` 包含了 `Cycle` 和 `Time Cycle` 关键帧。名为“A MotionLayout KeyCycle Tutorial”的章节将详细介绍这一主题。

## 44.12 从代码启动动画

在本章到目前为止，我们只查看了如何使用 `OnSwipe` 和 `OnClick` 处理程序来控制动画。也可以通过调用 `MotionLayout` 实例上的方法从代码内部启动动画。例如，下面的代码为名为 `motionLayout` 的布局运行持续时间为 `2000ms` 的过渡：

```java
motionLayout.setTransitionDuration(2000);
motionLayout.transitionToEnd();
```

完成选择后，点击确认框中的 `Convert` 按钮。一旦转换完成，`MotionLayout` 编辑器将出现在 Android Studio 主窗口中，如图 45-2 所示：

![image-JZPP52MG.jpg](img/image-JZPP52MG.jpeg)

图 45-2

作为转换过程的一部分，Android Studio 将创建一个名为 `res -> xml` 的新文件夹，并在其中放置名为 `activity_main_scene.xml` 的 `MotionLayout` 场景文件：

![image-RERYKZQH.jpg](img/image-RERYKZQH.jpeg)

图 45-3

该文件包含一个顶层 `MotionScene` 元素，其中包含 `ConstraintSet` 和 `Transition` 条目，这些项将定义主布局中的动画。默认情况下，该文件将包含起始和结束约束集的空元素以及初始过渡：

```
<MotionScene
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:motion="http://schemas.android.com/apk/res-auto">

    <Transition
        motion:constraintSetEnd="@+id/end"
        motion:constraintSetStart="@id/start"
        motion:duration="1000">
```

在 `MotionLayout` 编辑器中进行的任何更改都将存储在此文件中。同样，也可以直接编辑此文件以便在 `MotionLayout` 编辑器之外实现和修改动画设置。

在本教程中，动画主要通过 `MotionLayout` 编辑器界面来实现。然而，我们将在每个阶段回顾这些更改是如何反映在底层 `MotionScene` 文件中的。随着章节的进行，你会发现 `MotionScene` 的 XML 语法简单且易于学习。

本教程的第一阶段将演示如何使用 `MotionLayout` 为 `Button` 对象制作动画，包括运动（包括遵循路径）、旋转和尺寸缩放。

## 45.3 配置起始和结束约束

将 `activity_main.xml` 文件加载到 `MotionLayout` 编辑器后，确保已选中 Motion Layout 框（在下方图 45-5 中标记为 E），然后在从调色板将 `Button` 视图拖到布局画布的左上角之前，删除默认的 `TextView`，如图 45-4 所示：

![image-LO6L0LXF.jpg](img/image-LO6L0LXF.jpeg)

图 45-4

选中按钮后，使用属性（Attributes）工具窗口将 `id` 改为 `myButton`。

如上一章所述，`MotionLayout` 动画主要是指定视图如何在两个状态之间转换。因此，实现动画的第一步是指定定义这些状态的约束。

对于此示例，起点将是布局视图的顶部。要配置这些约束，请选择编辑器窗口中的起始约束集条目（在图 45-5 中标记为 A）：

![image-1F53HJ0W.jpg](img/image-1F53HJ0W.jpeg)

图 45-5

当选中起始框时，所有的约束和布局更改都将应用于起始点约束集。要返回整个布局的标准约束和属性，请点击 Motion Layout 框 (E)。

接下来，在 `ConstraintSet` 列表中选择 `myButton` 条目 (B)。注意，源（Source）列显示按钮是根据布局文件中的约束定位的。相反，我们希望按钮根据起始约束集进行定位。在仍选中 `myButton` 条目的情况下，点击 `Edit` 按钮 (C) 并从菜单中选择 `Create Constraint`，之后按钮条目将指示视图将根据起始约束集进行定位：

![image-CXF3BI1W.jpg](img/image-CXF3BI1W.jpeg)

图 45-6

起始约束集必须将按钮放置在布局的顶部，具有 `8dp` 的偏移量并水平居中。在 `myButton` 仍被选的情况下，使用属性工具窗口对视图的顶部、左侧和右侧设置约束，如下：

![image-8BTM5TV6.jpg](img/image-8BTM5TV6.jpeg)

图 45-7

选择结束约束集条目（在图 45-5 中标记为 D），并重复步骤以创建新约束，这次将按钮放置在布局的水平中心，但距离布局底部有 `8dp` 的偏移量：

![image-18LH7GBK.jpg](img/image-18LH7GBK.jpeg)

图 45-8

配置好起始和结束约束后，打开 `activity_main_scene.xml` 文件，并注意约束已添加到文件中：

```
<motion:constraintSetStart
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:motion="http://schemas.android.com/apk/res-auto">
```xml



```xml
xmlns:motion="http://schemas.android.com/apk/res-auto"

android:id="@+id/myButton"

android:layout_width="wrap_content"

android:layout_height="wrap_content"

motion:layout_constraintTop_toTopOf="parent"

android:layout_marginTop="8dp"

motion:layout_constraintStart_toStartOf="parent"

motion:layout_constraintEnd_toEndOf="parent" />

android:id="@+id/myButton"

android:layout_width="wrap_content"

android:layout_height="wrap_content"

motion:layout_constraintStart_toStartOf="parent"

motion:layout_constraintEnd_toEndOf="parent"

motion:layout_toBottomOf="parent"

android:marginBottom="8dp" />
```

此外注意，`Transition` 元素已配置为在起始和结束点之间进行动画。

## 45.4 预览 MotionLayout 动画

要在不构建和运行应用程序的情况下预览动画，请在 MotionLayout 编辑器中选择过渡。这将显示动画时间面板：

![image-2L5WR6.jpg](img/image-2L5WR6.jpeg)

图 45-9

要测试动画，点击滑块（C）并沿着时间轴移动它。随着滑块移动，布局中的按钮将沿着虚线（D）移动。使用工具栏按钮（E）执行完整动画。

## 45.5 添加点击手势

虽然创建了简单的 MotionLayout 动画过渡，但我们仍然需要在运行的应用程序内部启动动画。这可以通过分配点击或滑动处理程序来实现。对于此示例，我们将配置在用户点击按钮时启动动画。

在 MotionLayout 编辑器中，暂停循环运行动画。接下来，选择过渡箭头（在图 45-9 中标记为 A），在属性工具窗口中找到 OnClick 部分，并点击图 45-10 所示的 `+` 按钮：

![image-D8Y4QSX.jpg](img/image-D8Y4QSX.jpeg)

图 45-10

OnClick 面板将为第一个属性出现一个空行。对于属性名，输入 `targetId`；对于值字段，输入按钮的 id（`@id/myButton`）。在下一个空行中，在属性名字段输入 `app:clickAction`。在值字段中，点击向下箭头显示有效选项：

![image-U4CVL405.jpg](img/image-U4CVL405.jpeg)

图 45-11

对于此示例，选择切换操作。这将导致视图在点击时动画到相反的位置。输入这些设置后，它们应与图 45-12 所示的相同：

![image-VLH360EE.jpg](img/image-VLH360EE.jpeg)

图 45-12

再次打开 `activity_main_scene.xml` 文件并检查 Transition 条目中定义的 OnClick 属性：

```xml
motion:constraintSetEnd="@+id/end"

motion:constraintSetStart="@id/start"

motion:duration="1000">

motion:clickAction="toggle" />
```

编译并在设备或模拟器上运行应用程序，并确认点击按钮会导致其在 MotionScene 文件定义的起始和结束点之间来回切换。

到目前为止，示例项目仅实现了按钮视图从屏幕上一个位置到另一个位置的动画。属性关键帧（`KeyAttribute`）提供了一种方法，用于指定过渡时间轴内其他属性变化生效的点。

例如，可以定义 `KeyAttribute` 为：当视图移动到时间轴的 30% 时，其尺寸必须增加 50%。在本示例中，我们将在动画的中点添加一个旋转效果。

首先，在 MotionLayout 编辑器中打开 `activity_main.xml` 文件，选择过渡连接器箭头以显示时间轴，然后点击图 45-13 中高亮显示的按钮：

![image-6VG3FBRW.jpg](img/image-6VG3FBRW.jpeg)

图 45-13

从菜单中选择 `KeyAttribute` 选项：

![image-HMTTHTUS.jpg](img/image-HMTTHTUS.jpeg)

图 45-14

一旦选中，将出现图 45-15 所示的对话框。在对话框中，确保选中了 `ID` 选项并引用了 `myButton`。在位置字段中输入 `50`（此处以百分比指定，`0` 是起点，`100` 是终点）。最后，在点击 `Add` 按钮之前，从属性下拉菜单选择旋转（rotation）项：

![image-P5DA9GI5.jpg](img/image-P5DA9GI5.jpeg)

图 45-15

一旦添加了 `KeyAttribute`，时间轴中会出现一个该属性的一行。点击该行将其高亮，然后点击行最左侧边缘的展开箭头以展开属性过渡图。

注意，时间轴上出现了一个小小的菱形标记（如下方的图 45-16 所示），它表示关键帧的位置。图表表示效果的线性程度。在这种情况下，按钮将稳定地旋转到指定的度数，并在关键帧位置达到最大旋转。随后，按钮将在到达终点时旋转回 `0` 度：

![image-P2NY2UA7.jpg](img/image-P2NY2UA7.jpeg)

图 45-16

要更改 `KeyAttribute` 的属性，请在时间轴中选中它，然后参考 Attributes 工具窗口。在 `KeyAttribute` 面板中，将旋转属性更改为 `360` 度：

![image-ONDZ98RD.jpg](img/image-ONDZ98RD.jpeg)

图 45-17

通过移动滑动块并观察按钮在布局画布中穿过动画路径时的旋转情况，检查该属性是否正常工作。参考 `activity_main_scene.xml` 文件，其内容应如下：

```xml
motion:constraintSetEnd="@+id/end"

motion:constraintSetStart="@id/start"

motion:duration="1000">

motion:motionTarget="@+id/myButton"

motion:framePosition="50"

android:rotation="360" />

motion:clickAction="toggle" />
```

使用过渡滑动块或通过编译运行应用来测试动画，并验证按钮现在在动画期间会旋转。

## 45.7 在过渡中添加 CustomAttribute

`KeyAttribute` 属性限于内置效果，如缩放和旋转。通过声明 `CustomAttributes` 也可以实现额外的更改。

与存储在 `Transition` 元素中的 `KeyAttributes` 不同，`CustomAttributes` 位于起始和结束约束集中。因此，这些属性只能声明在起点和终点生效（换句话说，你无法在过渡时间轴的中间指定属性关键帧）。

在本示例中，我们将配置按钮颜色从红色逐渐变为绿色。首先选择图 45-18 中标记为 A 的起始框，然后是 `myButton` 视图约束集（`B`）：

![image-RURG1ELT.jpg](img/image-RURG1ELT.jpeg)

图 45-18

参考 Attributes 工具窗口，点击下方所示的 `CustomAttributes` 部分的 `+` 按钮：

![image-YJOO0HUF.jpg](img/image-YJOO0HUF.jpeg)

图 45-19

在结果对话框（图 45-20）中，将属性类型更改为 `Color`，并在 `Attribute Name` 字段中输入 `backgroundColor`。最后，将值设置为 `#F80A1F`：

![image-IDCX0M57.jpg](img/image-IDCX0M57.jpeg)

图 45-20

点击 `OK` 提交更改，然后选择结束约束集（上述图 45-18 中标记为 `C`），并重复步骤添加自定义属性，这次指定 `#33CC33` 为颜色的 RGB 值。

使用时间轴滑动块或运行应用，确保按钮在动画期间更改了颜色。

这些 `CustomAttributes` 的添加将反映在 `activity_main_scene.xml` 文件中：

```xml
motion:attributeName="backgroundColor"

motion:customColorValue="#F80A1F" />

motion:attributeName="backgroundColor"

motion:customColorValue="#33CC33" />
```

## 45.8 添加位置关键帧

本教程的最后一个任务是添加两个位置关键帧（`KeyPosition`），为动画引入一些横向移动。在 MotionLayout 显示时间轴的情况下，点击按钮创建一个如图 21 所示高亮的关键帧：

![image-T5Y4WH.jpg](img/image-T5Y4WH.jpeg)

图 45-21

在结果对话框中，按照图 45-22 所示设置属性：

![image-P9BV80P.jpg](img/image-P9BV80P.jpeg)

图 45-22

点击 `Add` 按钮提交更改，然后重复步骤添加第二个位置关键帧如下：

- Position：`75`
- Type：`parentRelative`
- PercentX：`0.85`
- PercentY：`0.75`

完成这些更改后，以下关键帧将添加到 `activity_main_scene.xml` 文件中：

```xml
motion:motionTarget="@+id/myButton"

motion:framePosition="25"

motion:keyPositionType="parentRelative"

motion:percentX="0.15"

motion:percentY="0.25" />

motion:motionTarget="@+id/myButton"

motion:framePosition="75"

motion:keyPositionType="parentRelative"

motion:percentX="0.85"

motion:percentY="0.75" />
```

最后一次测试应用，验证按钮在旋转和改变颜色的同时遵循下所示路径：

![image-3YR5OWL.jpg](img/image-3YR5OWL.jpeg)

图 45-23

位置关键帧由预览画布中表示路径的虚线上的菱形标记表示，如图 45-24 所示（如果标记可见，请确保在预览中选中了 `Button` 视图）：

![image-LKPRPGN.jpg](img/image-LKPRPGN.jpeg)

图 45-24

要视觉调整关键帧的位置，点击标记并将其拖到新位置。随着标记移动，Motion Layout 编辑器将显示当前的 x 和 y 坐标：

![image-6NOJ5K1.jpg](img/image-6NOJ5K1.jpeg)

图 45-25

## 45.9 总结

本章介绍了 Android Studio 内的 MotionLayout 编辑器，并探索了如何使用它在无需手动编写 XML 的情况下为 Android 应用界面添加动画。

本章涵盖的示例包括将 `ConstraintLayout` 容器转换为 `MotionLayout`、在 `MotionScene` 文件中创建起始和结束集及过渡，以及添加 `OnClick` 处理程序。动画预览、自定义属性和位置关键帧也涵盖在内。

# 46. MotionLayout KeyCycle Tutorial

之前的章节介绍并演示了使用 `MotionLayout` 容器将动画集成到 Android 应用界面的概念。标题为“Introduction to MotionLayout”的章节简要提到了循环（`KeyCycle`）和时间循环关键帧（`KeyCycle`），并解释了如何使用这些来实现涉及大量重复状态变化的动画。

本章将详细介绍循环关键帧（cycle keyframes），并演示如何使用 `Android Studio` 和 `Cycle Editor`（循环编辑器）在示例项目创建创建它们。

## 46.1 循环关键帧概述

位置关键帧（Position keyframes）可以为动画时间轴添加中间状态变化。虽然这对于少量的状态变化效果良好，但在数量较多时实现起来会非常繁琐。

例如，为了让按钮在被点击时抖动 50 次以表示发生错误，将涉及手动创建 100 个位置关键帧来执行微小的顺时针和逆时针旋转。同样，在视图跨越屏幕时实现跳动效果也同样耗时。

对于需要重复执行状态变化的情况，`MotionLayout` 包含了 `Cycle`（循环）和 `Time Cycle`（时间循环）关键帧。两者执行相同的任务，区别在于 `KeyCycle` 帧基于动画路径中的帧位置，而 `KeyTimeCycles` 是基于每秒循环次数（`Hz`）的时间。

使用这些 `KeyCycle` 帧，时间轴本质上被划分为若干子集（称为循环），每个子集包含一个或多个波形，定义了视图属性在整个时间轴上的修改方式。

创建 `KeyCycle` 循环时需要以下信息：

- `target view` - 目标视图 - 执行更改的视图 ID。
- `frame position` - 帧位置 - 循环开始的时间轴位置。
- `wave period` - 波周期 - 循环中包含的波形数量。
- `attribute` - 属性 - 被波形修改的视图属性。
- `wave offset` - 波偏移 - 根据指定量从关键帧基线偏移循环。
- `wave shape` - 波形 - 波的形状（`sin` 正弦、`cos` 余弦、`sawtooth` 锯齿、`square` 方形、`triangle` 三角形、`bounce` 弹跳或 `reverse sawtooth` 反锯齿）。

考虑以下循环关键帧集：

```xml
motion:framePosition="0"

motion:motionTarget="@+id/button"

motion:wavePeriod="1"

motion:waveOffset="0dp"

motion:waveShape="sin"

android:translationY="50dp"/>

motion:framePosition="25"

motion:motionTarget="@+id/button"

motion:wavePeriod="1"

motion:waveOffset="0dp"

motion:waveShape="sin"

android:translationY="50dp"/>

motion:framePosition="50"

motion:motionTarget="@+id/button"

motion:wavePeriod="1"

motion:waveOffset="0dp"

motion:waveShape="sin"

android:translationY="50dp"/>

motion:framePosition="75"

motion:motionTarget="@+id/button"

motion:wavePeriod="1"

motion:waveOffset="0dp"

motion:waveShape="sin"

android:translationY="50dp"/>

motion:framePosition="100"

motion:motionTarget="@+id/button"

motion:wavePeriod="1"

motion:waveOffset="0dp"

motion:waveShape="sin"

android:translationY="50dp"/>
```

上述关键帧集将时间轴划分为四个相等的循环。每个循环都配置为包含一个 `sin` 波形，该波形将按钮的 `translationY` 属性调整 50dp。此动画在执行时将导致按钮在指定范围内多次发生垂直振荡。

此关键帧集可以可视化为如图 46-1 所示，其中五个点代表关键帧位置：

![image-ZP8OOFU4.jpg](img/image-ZP8OOFU4.jpeg)

图 46-1

按照目前的实现方式，每个循环包含单个波形。假设我们需要在最后一个循环中包含四个波，而不是这些均匀分布的波。这可以通过增加最后一个 `KeyCycle` 元素的 `wavePeriod` 属性来轻松实现，如下所示：

```xml
...

motion:framePosition="75"

motion:motionTarget="@+id/button"

motion:wavePeriod="4"

motion:waveOffset="0dp"

motion:waveShape="sin"

android:translationY="50dp"/>
```



进行此更改后，帧集可以以波形形式渲染如下：

![image-ILYPB3RH.jpg](img/image-ILYPB3RH.jpeg)

图 46-2

到目前为止，本章的示例一直使用`sin`波。在`MotionLayout`中处理循环关键帧时，还有其他几种波形可用。例如，图 46-3 展示了将所有循环关键帧的`waveShape`属性更改为锯齿波的效果：

![image-9C4J50GP.jpg](img/image-9C4J50GP.jpeg)

图 46-3

除了`sin`和`sawtooth`，`MotionLayout`还支持`triangle`、`square`、`bounce`和`reverse sawtooth`波形。

在上面的示例中，每个循环都沿 Y 轴在相同范围内移动按钮。然而，假设我们需要第二个循环沿正 Y 轴移动按钮的距离更远。这涉及按如下所示调整第二个循环的`waveOffset`属性：

```
motion:framePosition="25"
motion:target="@+id/button"
motion:wavePeriod="1"
motion:waveOffset="100dp"
motion:waveShape="sin"
android:translationY="50dp"/>
```

通过此更改，我们得到了一个类似于图 46-4 的时间轴：

![image-CZ93KNP3.jpg](img/image-CZ93KNP3.jpeg)

图 46-4

按钮在第二个循环中沿 Y 轴的移动范围是 0 到 150dp，这取决于`translationY`的值：

```
motion:framePosition="25"
motion:target="@+id/button"
motion:wavePeriod="1"
motion:waveOffset="100dp"
motion:waveShape="sin"
```

图 46-5

## 46.2 使用 Cycle Editor

虽然实现并不复杂，但通过直接编辑`Scene`文件来获取所需的循环配置可能需要一些时间。为了此，Android 工程师开发了`Cycle Editor`。在`MotionLayout`中处理循环关键帧时非常有用。

`Cycle Editor`工具是一个 Java 归档文件（jar），需要安装 Java 运行时。它尚未成为 Android Studio 的一部分。`Cycle Editor`允许你可视化地设计和测试关键帧集。你可以从以下 URL 下载`CycleEditor.jar`文件：

`https://github.com/googlesamples/ConstraintLayoutExamples/releases/1.0/CycleEditor.jar`

下载后，打开命令行提示符或终端窗口，进入 jar 文件所在目录，并运行以下命令：

`java -jar CycleEditor.jar`

一旦工具加载，将出现图 46-6 所示的屏幕：

![image-TWMS5QA.jpg](img/TWMS5QA.jpeg)

图 46-6

标记 A 的面板显示关键帧集的 XML，可以直接编辑或使用 B 面板中的控件。面板 C 以波形显示渲染。遗憾的是，在更改时不会实时重绘。相反，必须通过选择`File -> parse xml`来刷新。点击 B 面板中的播放按钮时，标记 D 的面板将显示循环的实时渲染。`Examples`菜单提供了示例关键帧集，这些集合既可以用于学习，也可以作为你自己动画的基础。

## 46.3 创建 KeyCycleDemo 项目

本章剩余部分将创建一个基于`KeyCycle`的示例项目，以演示循环关键帧和`Cycle Editor`的用法。

在欢迎屏幕上选择`New Project`，并在随出的新项目对话框中选择`Empty Views Activity`模板，然后点击`Next`按钮。

在`Name`字段中输入`KeyCycleDemo`，并在`package name`中指定`com.ebookfrenzy.keycycledemo`。在点击`Finish`按钮之前，将`Minimum API`级别设置为`API 26: Android 8.0 (Oreo)`并将`Language`菜单改为`Java`。

当布局编辑器处于 Design 模式并打开`activity_main.xml`文件时，右键点击`ConstraintLayout`并选择`Convert to MotionLayout`选项：

![image-KLT5DURM.jpg](img/image-KLT5DURM.jpeg)

图 46-7

完成选择后，点击确认对话框中的`Convert`。

## 46.4 配置起始和结束约束

本教程旨在演示按钮从设备屏幕一侧移动到另一侧的动画，包括导致视图也沿`Y-axis`上下移动的`KeyCycle`效果。第一步是配置起始和结束约束。

将`activity_main.xml`文件加载到`MotionLayout`编辑器中，选择并删除默认的`TextView`小部件。在从调色板拖放`Button`视图之前，确保已选中`Motion Layout`框（见图 46-9 中标记为`E`），以便该视图在垂直方向上居中并位于布局画布的左边缘：

![image-KJIPN5WE.jpg](img/image-KJIPN5WE.jpeg)

图 46-8

要配置起始点的约束，请在编辑器窗口中选择起始约束集项（见图 46-9 中标记为`A`）：

![image-8HSMQ6AW.jpg](img/image-8HSMQ6AW.jpeg)

图 46-9

接下来，选择`ConstraintSet`列表中的按钮项（`B`）。在按钮仍被选中的情况下，点击编辑按钮（`C`）并从菜单中选择`Create Constraint`。

在仍被选中的情况下，使用`Attributes`工具窗口按照如下所示设置视图顶部、左侧和底部的约束：

![image-TUE5B71F.jpg](img/image-TUE5B71F.jpeg)

图 46-10

选择结束约束集项（见上方图 46-9 中标记为`D`），并重复步骤创建新约束，这次对按钮的顶部、底部和右边缘设置约束：

![image-TOH537QD.jpg](img/image-TOH537QD.jpeg)

图 46-11

## 46.5 创建循环

下一步是使用`Cycle Editor`生成动画的循环关键帧。在`Cycle Editor`运行时，请参考下图 46-12 所示的控制面板：

![image-5155DCJY.jpg](img/image-5155DCJY.jpeg)

图 46-12

使用标记为`A`的菜单，将要修改的属性从`rotation`改为`translationY`。

接下来，使用`KeyCycle`控制（`B`）选择`cycle 0`，以便面板中其他处的更改将应用于第一个循环。将`Period`滑块移动到`1`，并将`translationY`滑块移动到`60`，如图 46-13 所示（在移动滑块时，参考`XML`面板查看`translationY`值的精确设置）：

![image-0Y8A02P3.jpg](img/image-0Y8A02P3.jpeg)

图 46-13

选择`File -> Parse XML`菜单选项查看图表的变化。使用表 46-1 中列出的值配置`KeyFrames` 1 到 4 的设置（记住你已经配置了`KeyCycle 0`列中的设置）：

|  | ^(KeyCycle 0) | ^(KeyCycle 1) | ^(KeyCycle 2) | ^(KeyCycle 3) | ^(KeyCycle 4) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| ^(Position) | ⁰ | ²⁵ | ⁵⁰ | ⁷⁵ | ¹⁰⁰ |
| ^(Period) | ¹ | ² | ³ | ² | ¹ |
| ^(translationY) | ⁶⁰ | ⁶⁰ | ¹⁵⁰ | ⁶⁰ | ⁶⁰ |

表 46-1

完成这些更改后，关键帧集的`XML`读取内容如下：

```xml
motion:framePosition="0"
motion:motionTarget="@+id/button"
motion:wavePeriod="1"
motion:waveOffset="0dp"
motion:waveShape="sin"
android:translationY="60dp"/>

motion:framePosition="25"
motion:motionTarget="@+id/button"
motion:wavePeriod="2"
motion:waveOffset="0dp"
motion:waveShape="sin"
android:translationY="60dp"/>

motion:framePosition="50"
motion:motionTarget="@+id/button"
motion:wavePeriod="3"
motion:waveOffset="0dp"
motion:waveShape="sin"
android:translationY="150dp"/>

motion:framePosition="75"
motion:motionTarget="@+id/button"
motion:wavePeriod="2"
motion:waveOffset="0dp"
motion:waveShape="sin"
android:translationY="60dp"/>

motion:framePosition="100"
motion:motionTarget="@+id/button"
motion:wavePeriod="1"
motion:waveOffset="0dp"
motion:waveShape="sin"
android:translationY="60dp"/>
```

要查看带有新循环的图表，选择`File -> Parse XML`菜单选项以刷新波形，它现在应该如图 46-14 所示：

![image-CUJ41DDZ.jpg](img/image-CUJ41DDZ.jpeg)

图 46-14

## 46.6 预览动画

基于循环的动画现在可以在`Cycle Editor`中进行预览，点击按钮即可。基于循环的动画现在可以在`Cycle Editor`中进行预览，点击按钮即可。基于循环的动画现在可以在`Cycle Editor`中进行预览，点击按钮即可。

![image-OFGFK.jpg](img/image-OFGFK.jpeg)

图 46-15

## 46.7 向 MotionScene 添加 KeyFrameSet

在`Cycle Editor`中，从`XML`文件`activity_main_scene.xml`高亮并复制`KeyFrameSet`元素，将其粘贴到`activity_main_scene.xml`的`Transition`部分，使其位于`constraintSetEnd="@+id/end"`和`constraintStart="@id/start"`之间。注意`duration`属性需要改为`7000`。

```xml
motion:framePosition="0"
motion:motionTarget="@+id/button"
motion:wavePeriod="1"
motion:waveOffset="0dp"
motion:waveShape="sin"
android:translationY="60dp"/>

motion:framePosition="25"
motion:motionTarget="@+id/button"
motion:wavePeriod="2"
motion:waveOffset="0dp"
motion:waveShape="sin"
android:translationY="60dp"/>

motion:framePosition="50"
motion:motionTarget="@+id/button"
motion:wavePeriod="3"
motion:waveOffset="0dp"
motion:waveShape="sin"
android:translationY="150dp"/>

motion:framePosition="75"
motion:motionTarget="@+id/button"
motion:wavePeriod="2"
motion:waveOffset="0dp"
motion:waveShape="sin"
android:translationY="60dp"/>

motion:framePosition="100"
motion:motionTarget="@+id/button"
motion:wavePeriod="1"
motion:waveOffset="0dp"
motion:waveShape="sin"
android:translationY="60dp"/>
```



## 46.8 总结

循环关键帧为构建涉及大量匹配波形状态变化的帧动画提供了一种有用的方法。正如本章概述，使用`Cycle Editor`应用可以显著简化这些循环关键帧的生成。

## 47. 使用浮动操作按钮和 Snackbar

本章的一个目标是提供材料设计（material design）概念的概述。材料设计最初作为 Android 5.0 的一部分引入，是一套设计指南，规定了 Android 用户界面以及在 Android 上运行应用的外观和行为。

作为实现材料设计（Material Design）概念的一部分，Google 还引入了 Android 设计支持库（Android Design Support Library）。该库包含多个组件，允许将材料设计的许多关键功能构建到 Android 应用中。其中两个组件——悬浮操作按钮（floating action button）和`Snackbar`将在后续章节介绍其他组件之前在本章中进行介绍。

## 47.1 材料设计

材料设计的原则定义了 Android 环境的整体外观。材料设计由 Google 的 Android 团队创建，它规定构成 Android 用户界面以及运行在其上的应用的元素在行为、阴影、动画和样式方面应以特定的方式显示和运行。材料设计的原则之一是用户界面的元素看起来具有物理深度，并且感觉项目是由物理材料分层构建的。例如，按钮通过阴影效果看起来像是悬浮在其所处布局表面之上的。按下按钮时，按钮会弯曲并抬起，就像是由薄材料制成的，在松开时会产生涟漪。

材料设计还规定了许多标准用户界面元素的布局和行为。一个关键示例是位于屏幕顶部的应用栏（app bar）应该长什么样，以及它相对于活动主内容区域发生的滚动活动应该如何表现。

材料设计涵盖了广泛的领域，从推荐的颜色样式到对象的动画处理。关于材料设计概念和指南的完整描述可以在以下链接中在线找到，它是所有 Android 开发者的推荐读物：

[`material.io/design/introduction`](https://material.io/design/introduction)

## 47.2 设计库

实现采用材料设计原则的 Android 应用所需的许多构建块包含在 Android 设计支持库中。该库包含了一组用户界面组件，可以包含在 Android 应用中以实现材料设计的大部分外观、感觉和行为。该库中的两个组件——悬浮操作按钮和`Snackbar`将在本章中介绍，其他将在后续章节中介绍。

## 47.3 悬浮操作按钮 (FAB)

悬浮操作按钮看起来悬浮在应用用户界面的上方。它通常用于促进用户界面中最常见的操作。悬浮操作按钮可以放置在屏幕上，允许用户向联系人列表添加条目或从应用内发送电子邮件。例如，图 47-1 显示了标准 Android 联系人应用中允许用户添加新联系人的悬浮操作按钮：

![image-PZW9NE0L.jpg](img/image-PZW9NE0L.jpeg)

图 47-1

使用悬浮操作按钮时应遵循材料材料设计指南。悬浮操作按钮必须是圆形的，尺寸可以是 56 x 56dp（默认）或 40 x 40dp（微型）。按钮位置距离手机边缘至少为 16dp，距离桌面设备和平板设备边缘至少为 24dp。无论大小如何，按钮必须包含一个大小为 24x24dp 的内部图标，并且建议每个用户界面屏幕只有一个悬浮操作按钮。

悬浮操作按钮可以进行动画处理，或设计成在触摸时变形为其他项目。例如，悬浮操作按钮可以在被点击时旋转，或变形为另一个元素，例如工具栏或列出相关操作的面板。

## 47.4 Snackbar

`Snackbar`组件提供了一种以屏幕底部面板的形式向用户展示信息，如图 47-2 所示。`Snackbar`实例包含一条短的文本消息和一个可选的操作按钮，当用户点击时，该按钮将执行任务。一旦显示，`Snackbar`将自动超时，或者可以由用户通过滑动动作手动移除。在`Snackbar`显示期间，应用将继续正常运行并响应用户交互。

![image-08GT7JTJ.jpg](img/image-08GT7JTJ.jpeg)

图 47-2

在本章的剩余部分，将创建一个示例应用程序，该程序使用悬浮操作按钮和`Snackbar`的基本功能向项目列表添加条目。

## 47.5 创建示例项目

从欢迎界面选择 New Project（新项目）选项，在生成的新项目对话框中，点击“Next”（下一步）按钮之前选择 Basic Views Activity 模板。

在“Name”字段中输入`FabExample`，并指定`com.ebookfrenzy.fabexample`为包名。在点击“Finish”（完成）按钮之前，将 Minimum API level 设置更改为 API 26: Android 8.0 (Oreo)，并将 Language 菜单更改为 Java。

## 47.6 审查项目

由于选择了 Basic Views Activity 模板，该活动包含四个布局文件。`activity_main.xml`文件由一个`CoordinatorLayout`组成，其中包含应用栏、Material 工具栏和悬浮操作按钮的项。

`content_main.xml`文件代表活动内容区域的布局，包含一个`NavHostFragment`实例。该文件通过以下 include 指令嵌入`activity_main.xml`文件中：

`activity_main.xml`文件中的悬浮操作按钮元素如下：

```xml
android:id="@+id/fab"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_gravity="bottom|end"
android:layout_marginEnd="@dimen/fab_margin"
android:layout_marginBottom="16dp"
app:srcCompat="@android:drawable/ic_dialog" />
```

这声明按钮将出现在屏幕右下角，边距由`values/dimens.xml`文件中的`fab_margin`标识符表示（在本例中为 16dp）。XML 进一步声明按钮内部图标将采用内置图标的形式。

空白模板还配置了悬浮操作按钮，在用户点击时显示`Snackbar`。实现此功能的代码可以在`MainActivity.java`文件的`onCreate()`方法中找到，如下所示：

```java
binding.fab.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View view) {
        Snackbar.make(view, "Replace with your own action", Snackbar.LENGTH_LONG)
            .setAction("Action", null).show();
    }
});
```

代码通过视图绑定访问悬浮操作按钮，并添加了点击按钮时调用的`OnClickListener`set。该方法显示了一个配置了消息但没有操作的`Snackbar`实例。

当项目编译并运行时，悬浮操作按钮将出现在屏幕底部，如图 47-3 所示：

![image-0DYRIVSV.jpg](img/image-0DYRIVSV.jpeg)

图 47-3

点击悬浮操作按钮将触发`OnClickListener`处理方法，导致`Snackbar`显示在屏幕底部：

![image-UJ3BBKI.jpg](img/image-UJ3BBKI.jpeg)

图 47-4

## 47.7 移除导航功能

正如《Android Studio 布局编辑器指南》所述，Basic Views Activity 模板包含了多个片段以及在片段之间导航的按钮。这些功能对于本教程来说是不必要的，如果不移除，稍后会导致问题。在继续教程之前，请按照以下步骤修改项目：

1. 在 Project 工具窗口中，导航并双击 app -> res -> navigation -> nav_graph.xml 文件，将其加载到导航编辑器中。
2. 在编辑器内的 Component Tree 面板中选择`SecondFragment`项，然后按下键盘上的删除键将其从图中移除。
3. 找到并删除`SecondFragment.java`（`app -> java -> -> SecondFragment`）和`fragment_second.xml`（`app -> res -> layout -> fragment_second.xml`）文件。
4. 找到`FirstFragment.java`文件，双击将其加载到编辑器中，并移除`onViewCreated()`方法中的代码，使其内容如下：

```java
binding.buttonFirst.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View view) {
        NavHostFragment.findNavController(FirstFragment.this)
            .navigate(R.id.action_FirstFragment_to_SecondFragment);
    }
});
```

## 47.8 修改悬浮操作按钮 (Floating Action Button)

由于本示例的目标是配置悬浮操作按钮向列表添加条目，因此目前按钮上显示的邮件图标需要更改为更能指示所执行操作的内容。按钮将使用的图标名为`ic_add_entry.png`，它可以在以下 URL 下载的示例代码的`project_icons`文件夹中找到：

[`www.payloadbooks.com/product/ladybugjava`](https://www.payloadbooks.com/product/ladybugjava)

在操作系统的文件导航器中找到此图像并复制该文件。在 Project 工具窗口中右键点击`app -> res -> drawable`项，并从菜单中选择`Paste`（粘贴）将文件添加到文件夹：

![image-E1HP2WNE.jpg](img/image-E1HP2WNE.jpeg)

图 47-5

接下来，编辑`activity_main.xml`文件，将图标的图像源从`@android:drawable/ic_dialog_email`更改为`@drawable/ic_add_entry`如下：

```xml
android:id="@+id/fab"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_gravity="bottom|end"
android:layout_margin="@dimen/fab_margin"
android:layout_marginBottom="16dp"
app:srcCompat="@drawable/ic_add_entry" />
```

在布局预览中，按钮内部的图标将更改为加号。

我们还可以通过向`OnClickListener`添加代码，让悬浮操作按钮在点击时执行几乎任何操作。例如，对`MainActivity.java`文件进行以下更改，每次点击按钮时都会调用名为`displayMessage()`的方法来显示吐消息（toast message）：

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

## 47.9 为 Snackbar 添加操作

也可以为`Snackbar`添加一个操作，该操作在用户点击时执行某项任务。编辑`MainActivity.java`文件并修改`Snackbar`的创建代码，添加一个标题为“My Action”的操作，并配置一个名为`actionOnClickListener`的`OnClickListener`，该监听反过来会显示一条吐消息：

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



运行应用并点击悬浮操作按钮，此时吐消息和`Snackbar`应该都会出现。当`Snackbar`可见时，点击`Snackbar`中的`My Action`按钮，验证`Snackbar`上的文本更改为“Action Complete”：

![image-6JS27DRH.jpg](img/image-6JS27DRH.jpeg)

图 47-6

## 47.10 总结

在学习使用这些功能的示例项目之前，本章提供了 Material 设计（Material Design）、悬浮操作按钮和`Snackbar`的概览。

悬浮操作按钮和`Snackbar`是 Android Material 设计用户界面实现方法的一部分。悬浮操作按钮提供了一种突出 Android 应用特定屏幕内最常用操作的方式。`Snackbar`则提供了一种应用程序向用户展示信息并允许用户对其采取操作的方法。

## 48. 使用 TabLayout 组件创建标签页界面

上一章概述了 Android 中 Material 设计的概念。它引入了设计支持库提供的两个组件，形式为悬浮操作按钮和`Snackbar`。本章将演示如何使用设计支持库的另一个组件——`TabLayout`，它可以与`ViewPager`类结合使用，在 Android 活动（Activity）中创建一个基于标签页的界面。

## 48.1 ViewPager2 简介

虽然`ViewPager2`不是设计支持库的一部分，但在与`TabLayout`组件配合实现标签页用户界面时，它是非常有用的辅助类。`ViewPager2`的主要作用是允许用户翻阅不同的信息页，通常每个页由一个布局片段（fragment）。与`ViewPager2`关联的片段由`FragmentStateAdapter`类的实例管理。分配给`ViewPager2`的分页器至少必须实现两个方法。第一个是`getItemCount()`，必须返回要显示的页面总数。第二个是`createFragment()`，它接收一个页码并必须返回准备好呈现给用户的相应片段。

## 48.2 TabLayout 组件概述

如前所述，`TabLayout`是 Material 设计中引入的组件之一，并包含在设计支持库中。`TabLayout`的目的是为用户提供一行标签，可以通过选择这些标签来显示不同的页面。标签可以是固定的，也可以是滚动的，此时用户可以向左或向右滑动以查看比当前屏幕显示容量更多的标签。标签上显示的信息可以是文本、图像或两者的结合。例如，图 48-1 显示了一个包含四个图像标签的应用程序标签栏：

![image-E1HP2WNE.jpg](img/image-E1HP2WNE.jpeg)

图 48-1

相反，图 48-2 显示了一个包含四个文本标签的滚动配置`TabLayout`：

![image-0OH8BX.jpg](img/image-0OH8BX.jpeg)

图 48-2

本章的剩余部分将通过创建一个演示`TabLayout`组件结合`ViewPager2`和四个片段的示例项目来完成。

## 48.3 创建 TabLayoutDemo 项目

在欢迎界面选择`New Project`，在出现的新项目对话框中选择`Basic Views Activity`模板，然后点击`Next`按钮。

在`Name`字段输入`TabLayoutDemo`，并指定`com.ebookrenzy.tablayoutdemo`为包名。在点击`Finish`按钮之前，将`Minimum API level`设置为`API 26: Android 8.0 (Oreo)`，并将`Language`菜单设置为`Java`。

项目创建后，在`Layout Editor`加载`content_main.xml`文件，选择`NavHostFragment`对象并将其删除。由于我们不会使用`Basic Views Activity`模板的导航功能，请编辑`MainActivity.java`文件并修改`onCreate()`方法以移除导航代码：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    binding = ActivityMainBinding.inflate(getLayoutInflater());
    setContentView(binding.getRoot());
    setSupportActionBar(binding.toolbar);
    NavController navController =
    Navigation.findNavController(this, R.id.nav_host_fragment_content_main);
}
```

```java
appBarConfiguration =
new AppBarConfiguration.Builder(navController.getGraph()).build();
NavigationUI.setupActionBarWithNavController(this, navController, appBarConfiguration);
binding.fab.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View view) {
        Snackbar.make(view, "Replace with your own action", Snackbar.LENGTH_LONG)
        .setAction("Action", null).show();
    }
});
```

最后，删除`onSupportNavigateUp()`方法：

```java
@Override
public boolean onSupportNavigateUp() {
    NavController navController = Navigation.findNavController(this, R.id.nav_host_fragment_content_main);
    return NavigationUI.navigateUp(navController, appBarConfiguration)
    || super.onSupportNavigateUp();
}
```

## 48.4 创建第一个 Fragment

`TabLayout`上的每个标签在选中时将显示不同的 fragment。在`Project`工具窗口中，右键点击`app` -> `java` -> `com.ebookfrenzy.tablayoutdemo`条目，选择`New` -> `Fragment` -> `Fragment (Blank)`即可创建第一个 fragment。在弹出的对话框中，在`Fragment Name:`字段中输入`Tab1Fragment`，在`Fragment Layout Name:`字段中输入`fragment_tab1`。点击`Finish`按钮创建新 fragment：

![image-WSJTKBLJ.jpg](img/image-WSJTKBLJ.jpeg)

图 48-3

编辑`Tab1Fragment.java`文件，如果 Android Studio 没有自动添加，请按照如下所示添加`OnFragmentInteractionListener`接口声明：

```java
.
.
import android.net.Uri;
.
.
public interface OnFragmentInteractionListener {
    // TODO: Update argument type and name
    void onFragmentInteraction(Uri uri);
}
.
.
```

将新创建的`fragment_tab1.xml`文件（位于`app` -> `res` -> `layout`）加载到`Layout Editor`工具中，在`Component Tree`面板中右键点击`FrameLayout`条目，选择`Convert FrameLayout to ConstraintLayout`选项。在弹出的对话框中，点击`OK`之前确保选中了所有转换选项。将布局的 ID 更改为`constraintLayout`。

一旦布局转换为`ConstraintLayout`，请从布局中删除`TextView`。从`Palette`中找到`TextView`控件，并将其拖动到布局的中心。编辑对象的`text`属性使其显示为“Tab 1 Fragment”，将字符串提取为命名为`tab_1_fragment`的资源，并点击`Infer Constraints`工具栏按钮。此时，该布局应与图 48-4 一致：

![image-HH14A1A2.jpg](img/image-HH14A1A2.jpeg)

图 48-4

## 48.5 复制 Fragments

到目前为止，项目包含了四个所需 fragment 中的一个。与其使用之前的步骤创建剩余的三个 fragment，直接复制第一个 fragment 会更快。每个 fragment 都由一个布局 XML 文件和一个 Java 类文件组成，每个文件都需要被复制。

在`Project`工具窗口中右键点击`fragment_tab1.xml`文件，并在弹出的菜单中选择`Copy`选项。再次右键点击布局条目，这次选择`Paste`选项。在弹出的对话框中点击`OK`按钮之前，将新布局文件命名为`fragment_tab2.xml`。编辑新的`fragment_tab2.xml`文件，并将`Text View`上的文本改为“Tab 2 Fragment”，按照通常步骤将字符串提取为命名为`tab_2_fragment`的资源。

要复制`Tab1Fragment`类文件，右键点击`app` -> `java` -> `com.ebookfrenzy.tablayoutdemo`下列出的类并选择`Copy`。右键点击`com.ebookfrenzy.tablayoutdemo`条目并选择`Paste`。在`Copy Class`对话框中，在`New name:`字段中输入`Tab2Fragment`并点击`OK`。

新的`Tab2Fragment.java`文件并修改`onCreateView()`方法以加载`fragment_tab2`布局文件：

```java
@Override
public View onCreateView(LayoutInflater inflater, ViewGroup container, Bundle savedInstanceState) {
    // Inflate the layout for this fragment
    return inflater.inflate(R.layout.fragment_tab2, container, false);
}
```

执行上述复制步骤两次，为剩余的两个 fragment 创建布局和类文件。完成这些步骤后，项目结构应与图 48-5 一致：

![image-MRWSRKW8.jpg](img/image-MRWSRKW8.jpeg)

图 48-5

## 48.6 添加 TabLayout 和 ViewPager2

现在 fragment 创建过程已经完成，下一步是向主活动布局文件添加`TabLayout`和`ViewPager2`。编辑`activity_main.xml`文件，并按照下面的 XML 列表添加这些元素。注意`TabLayout`组件嵌入在`AppBarLayout`元素中，而`ViewPager2`放置在`AppBarLayout`之后：

```xml
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context=".MainActivity">

<AppBarLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:theme="@style/Theme.TabLayoutDemo.AppBarOverlay">

    <Toolbar
        android:id="@+id/toolbar"
        android:layout_width="match_parent"
        android:layout_height="?attr/actionBarSize"
        android:background="?attr/colorPrimary"
        app:popupTheme="@style/Theme.TabLayoutDemo.PopupOverlay" />
</AppBarLayout>

<TabLayout
    android:id="@+id/tabLayout"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    app:tabMode="fixed"
    app:tabGravity="fill" />

<ViewPager2
    android:id="@+id/view_pager"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    app:layout_behavior="@string/appbar_scrolling_view_behavior" />

<FloatingActionButton
    android:id="@+id/fab"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_gravity="bottom|end"
    android:layout_marginEnd="@dimen/fab_margin"
    android:layout_marginBottom="16dp"
    app:srcCompat="@android:drawable/ic_email" />
```

## 48.7 创建 Pager Adapter

本示例使用`ViewPager2`方法处理分配给`TabLayout`的 fragment，需要添加一个子类`FragmentStateAdapter`的类来管理用户选择标签时显示的 fragment。

在`Project`工具窗口中右键点击`com.ebookfrenzy.tablayoutdemo`条目，选择`New` -> `Java Class`为项目添加新类。在新类对话框中，在`Name:`字段中输入`TabPagerAdapter`，选择列表中的`Class`项并按回车键。

编辑`TabPagerAdapter.java`文件使其如下：

```java
package com.ebookfrenzy.tablayoutdemo;

import androidx.annotation.NonNull;
import androidx.fragment.app.*;
import androidx.viewpager2.adapter.FragmentStateAdapter;

public class TabPagerAdapter extends FragmentStateAdapter {
    int tabCount;

    public TabPagerAdapter(@NonNull FragmentActivity fragmentActivity, int numberOfTabs) {
        super(fragmentActivity);
        this.tabCount = numberOfTabs;
    }

    @NonNull
    @Override
    public Fragment createFragment(int position) {
        switch (position) {
            case 0:
                return new Tab1Fragment();
            case 1:
                return new Tab2Fragment();
            case 2:
                return new Tab3Fragment();
            case 3:
                return new Tab4Fragment();
            default:
                return null;
        }
    }

    @Override
    public int getItemCount() {
        return tabCount;
    }
}
```



## 48.8 执行初始化任务

剩余的任务涉及初始化 `TabLayout`、`ViewPager2` 和 `TabPagerAdapter` 实例，并声明主 `Activity` 类实现针对四个标签页碎片（fragment）的片段交互监听器。编辑 `MainActivity.java` 文件，使其内容如下：

```java
package com.ebookfrenzy.tablayoutdemo;

.

.

import android.net.Uri;

import com.google.android.material.tabs.TabLayoutMediator;

.

.

public class MainActivity extends AppCompatActivity implements

    Tab1Fragment.OnFragmentInteractionListener,

    Tab2Fragment.OnFragmentInteractionListener,

    Tab3Fragment.OnFragmentInteractionListener,

    Tab4Fragment.OnFragmentInteractionListener {

    @Override

    protected void onCreate(Bundle savedInstanceState) {

.

.

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

.

.

}
```

代码首先通过以下方式创建四个标签并将它们添加到 `TabLayout` 实例中：

```java
for (int i = 0; i < 4; i++) {

    binding.tabLayout.addTab(binding.tabLayout.newTab());

}
```

接下来，创建一个 `TabPagerAdapter` 类的实例。请注意，创建 `TabPagerAdapter` 实例的代码传递了分配给 `TabLayout` 组件的标签数量。然后，将 `TabPagerAdapter` 实例赋值为 `ViewPager2` 实例的适配器：

```java
final TabPagerAdapter adapter = new TabPagerAdapter

    (this, binding.tabLayout.getTabCount());

binding.viewPager.setAdapter(adapter);
```

最后，使用 `TabLayoutMediator` 类的实例将 `TabLayout` 与 `ViewPager2` 对象连接：

```java
new TabLayoutMediator(binding.tabLayout, binding.viewPager,

    (tab, position) -> tab.setText("Tab " + (position + 1) + " Item")).attach();
```

该类确保 `TabLayout` 标签与当前选中的碎片保持同步。此过程涉及确保每个标签上显示正确的文本。在这种情况下，文本被配置为“Tab Item”，其中 Item 被当前选中标签的数字替换。

## 48.9 测试应用程序

在设备或模拟器上编译并运行应用，确保选择某个标签会导致相应的碎片出现在屏幕的内容区域中：

![image-5M4FM02I.jpg](img/image-5M4FM02I.jpeg)

图 48-6

## 48.10 定制 `TabLayout`

此示例项目中的 `TabLayout` 使用固定模式（fixed mode）配置。这种模式适用于数量较少且标题较短的标签。在使用固定模式时，标签数量过多或标题较长可能会迅速成为问题，如图 48-7 所示：

![image-OR4V3FYD.jpg](img/image-OR4V3FYD.jpeg)

图 48-7

为了使标签适应可用显示宽度，`TabLayout` 使用了多行文本。尽管如此，第二行仍被裁剪，导致无法看到完整标题。解决此问题的解决方案是将 `TabLayout` 切换到可滚动模式（scrollable mode）。在这种模式下，标题以全长度、单行格式出现，允许用户通过滑动水平滚动查看可用项目，如图 48-8 所示：

![image-SPASLAIC.jpg](img/image-SPASLAIC.jpeg)

图 48-8

要将 `TabLayout` 切换到可滚动模式，将 `activity_main.xml` 布局资源文件中的 `app:tabMode` 属性从“fixed”更改为“scrollable”：

```xml
android:id="@+id/tabLayout"

android:layout_width="match_parent"

android:layout_height="wrap_content"

app:tabMode="scrollable"

app:tabGravity="fill"/>
```

在固定模式下，可以配置 `TabLayout` 来控制标签项目的显示方式，以占据屏幕上的可用空间。这是通过 `app:tabGravity` 属性控制的，其结果在较宽的显示（如横屏模式下的平板电脑）上更为明显。例如，设置为“fill”时，项目将均匀分布在 `TabLayout` 的宽度上，如图 48-9 所示：

![image-ZQBURE0W.jpg](img/image-ZQBURE0W.jpeg)

图 48-9

将属性值更改为“center”会导致项目相对于标签栏中心定位：

![image-ISJELU9X.jpg](img/image-ISJELU9X.jpeg)

图 48-10

## 48.11 总结

`TabLayout` 是 Android Material 设计实现引入的组件之一。`TabLayout` 组件的目的是展示一系列显示不同内容的标签项目。当 `TabLayout` 与 `ViewPager2` 类结合时，可以轻松创建显示文本、图像或组合的标签布局。

## 49. 使用 `RecyclerView` 和 `CardView`

`RecyclerView` 和 `CardView` 控件共同工作，为用户提供可滚动列表。本章将涵盖这两个类的详细信息。

### 49.1 `RecyclerView` 概述

与“Floating Action Button and Snackbar”章节中的 `ListView` 类似，`RecyclerView` 的目的是允许呈现可滚动列表。然而，`RecyclerView` 相比 `ListView` 具有若干优势。特别是，`RecyclerView` 在复用滚动出屏幕视图而不是创建新视图方面高效得多（这也是其名称的来源），这在向用户展示大量数据时提高了性能。

与 `ListView` 不同，`RecyclerView` 还提供了三种内置布局管理器来控制标签项目的呈现方式：

- `LinearLayoutManager` —— 标签以水平或垂直列表的形式呈现。

![image-EZ4I49JA.jpg](img/image-EZ4I49JA.jpeg)

图 49-1

- `GridLayoutManager` —— 标签以网格格式呈现。这种管理器最适用于标签大小一致的情况。

![image-T9TSCU41.jpg](img/image-T9TSCU41.jpeg)

图 49-2

- `StaggeredGridLayoutManager` —— 标签以交错网格格式呈现。这种管理器最适用于标签大小不一的情况。

![image-7CCCZQ6O.jpg](img/image-7CCCZQ6O.jpeg)

图 49-3

对于三种内置管理器都无法提供所需布局的情况，可以通过子类化 `RecyclerView.LayoutManager` 类来实现自定义布局管理器。

`RecyclerView` 中的每个列表项都创建为 `ViewHolder` 类的实例。`ViewHolder` 实例包含了 `RecyclerView` 显示列表项所需的所有内容，包括要显示的信息和用于显示的视图布局。

与 `ListView` 一样，`RecyclerView` 依赖适配器（adapter）作为 `RecyclerView` 实例与要显示的数据之间的中介。适配器被创建为 `RecyclerView.Adapter` 类的子类，并至少实现以下方法，这些方法会被分配给它的 `RecyclerView` 对象在不同点调用：

- `getItemCount()` —— 该方法必须返回列表中显示的项目数量。
- `onCreateViewHolder()` —— 该方法创建并返回一个用视图初始化的 `ViewHolder` 对象。该视图通常通过加载 XML 布局文件创建。
- `onBindViewHolder()` —— 此方法接收由 `onCreateViewHolder()` 方法创建的 `ViewHolder` 对象，以及一个指示即将显示的列表项的整数值。`ViewHolder` 对象包含了由 `onCreateViewHolder()` 方法分配的布局。`onBindViewHolder()` 方法负责为布局中的视图填充与指定项目相对应的文本和图形，并将该对象返回给 `RecyclerView`，由其将其展示给用户。

在布局中添加 `RecyclerView` 只需要在要显示该组件的 `Activity` XML 内容布局文件中添加相应的元素即可。例如：

```xml
xmlns:android="http://schemas.android.com/apk/res/android"

xmlns:app="http://schemas.android.com/apk/res-auto"

xmlns:tools="http://schemas.android.com/tools"

android:layout_width="match_parent"

android:layout_height="match_parent"

app:layout_behavior="@string/appbar_scrolling_view_behavior"

tools:context=".MainActivity"

tools:showIn="@layout/activity_card_demo"

android:id="@+id/recycler_view"

android:layout_width="0dp"

android:layout_height="0dp"

app:layout_constraintBottom_toBottomOf="parent"

app:layout_constraintEnd_toEndOf="parent"

app:layout_constraintStart_toStartOf="parent"

app:layout_constraintTop_toTopOf="parent"

tools:listItem="@layout/card_layout" />
```

在上面的示例中，`RecyclerView` 已嵌入到主 `Activity` 布局文件的 `CoordinatorLayout` 中，并带有 `AppBar` 和 `Toolbar`。这提供了额外的功能，例如当用户在 `RecyclerView` 中向上滑动时，配置 `Toolbar` 和 `AppBar` 滑出屏幕（该主题在“使用 AppBar 和 Collapsing Toolbar Layouts”章节中有更详细介绍）。

## 49.2 `CardView` 概述

`CardView` 类是一种用户界面视图，允许使用卡片比喻分组展示信息。卡片通常通过 `RecyclerView` 实例以列表形式呈现，并可以配置为带有阴影效果和圆角。例如，图 49-4 显示了三个配置好的 `CardView` 实例，它们显示一个由 `ImageView` 和两个 `TextView` 组成的布局：

![image-NAO2G9FK.jpg](img/image-NAO2G9FK.jpeg)

图 49-4

随 `CardView` 实例一同呈现的用户界面布局在 XML 布局资源文件中定义，并在运行时加载到 `CardView` 中。`CardView` 布局可以包含任何复杂的布局，可以使用标准的布局管理器如 `RelativeLayout` 和 `LinearLayout`。以下 XML 布局文件表示一个由 `RelativeLayout` 和单个 `ImageView` 组成的卡片视图布局。该卡片被配置为提升以创建阴影效果，并带有圆角显示：

```xml
xmlns:card_view="http://schemas.android.com/apk/res-auto"

xmlns:android="http://schemas.android.com/apk/res/android"

android:id="@+id/card_view"

android:layout_width="match_parent"

android:layout_height="wrap_content"

android:layout_margin="5dp"

card_view:cardCornerRadius="12dp"

card_view:cardElevation="3dp"

card_view:contentPadding="4dp"

android:layout_width="match_parent"

android:layout_height="wrap_content"

android:padding="16dp" >

android:layout_width="100dp"

android:layout_height="100dp"

android:id="@+id/item_image"

android:layout_alignParentLeft="true"

android:layout_alignParentTop="true"

android:layout_marginRight="16dp" />
```

当结合 `RecyclerView` 创建可滚动卡片列表时，适配列表的 `onCreateViewHolder()` 方法会充气卡片的布局资源文件，将其分配给 `ViewHolder` 实例并返回给 `RecyclerView` 实例。

## 49.3 总结

本章介绍了 Android `RecyclerView` 和 `CardView` 组件。`RecyclerView` 提供了一种资源高效的方式，用于 Android 应用中显示可滚动视图列表。当以卡片形式呈现数据组（例如名称和地址列表）时，`CardView` 非常有用。正如在下一章教程中所概述和演示的那样，`RecyclerView` 和 `CardView` 结合使用时特别有用。

## 50. Android `RecyclerView` 和 `CardView` 教程

本章将创建一个示例项目，同时使用 `CardView` 和 `RecyclerView` 组件来创建一个可滚动卡片列表。完成后的应用将显示一个包含图像和文本的卡片列表。除了显示卡片列表外，项目还将实现为：选择卡片将向用户显示消息，指示点击了哪张卡片。

## 50.1 创建 `CardDemo` 项目

从欢迎界面选择 New Project（新建项目），在弹出的新项目对话框中，点击 Next（下一步）按钮之前选择 Basic Views Activity 模板。

在 Name（名称）字段中输入 `CardDemo`，并指定 `com.ebookfrenzy.carddemo` 为包名。在点击 Finish（完成）按钮之前，将 Minimum API level 设置为 `API 26: Android 8.0 (Oreo)`，并将语言菜单设置为 `Java`。

## 50.2 修改 Basic Views Activity 项目

由于选择了 Basic Views Activity，布局中包含了一个该项目所需的悬浮按钮。在布局编辑器中加载 `activity_main.xml` 布局文件，选择悬浮按钮并按删除键将其从布局中移除。编辑 `MainActivity.java` 文件，在 `onCreate` 方法中移除悬浮按钮代码并如下：

```java
@Override

protected void onCreate(Bundle savedInstanceState) {

    super.onCreate(savedInstanceState);

    binding = ActivityMainBinding.inflate(getLayoutInflater());

    setContentView(binding.getRoot());
```



`setSupportActionBar(binding.toolbar);`

`NavController navController = Navigation.findNavController(this, R.id.nav_host_fragment);`

`appBarConfiguration = new AppBarConfiguration.Builder(navController.getGraph()).build();`

`NavigationUI.setupActionBarWithNavController(this, navController, appBarConfiguration);`

`binding.fab.setOnClickListener(new View.OnClickListener() {`

```java
@Override
public void onClick(View view) {
    Snackbar.make(view, "Replace with action", Snackbar.LENGTH_LONG)
        .setAction("Action", null).show();
}
```

`});`

此外，移除 `onSupportNavigateUp()` 方法，然后打开 `content_main.xml` 文件并从布局中删除 `nav_host_fragment` 对象，保留 `ConstraintLayout`。

## 50.3 设计 CardView 布局

卡片内部包含的视图布局将在单独的 XML 文件中定义。在项目工具中，右键点击 `app -> layout` 条目并选择 `New -> Layout Resource File`。在 New Resource 对话框中，在 `File name:` 字段输入 `card_layout`，并在点击 OK 按钮之前根元素字段输入 `androidx.cardview.widget.CardView`。

将 `card_layout.xml` 文件加载到布局编辑器，切换到 Code 模式并修改布局如下：

```xml
xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:id="@+id/card_view"
android:layout_margin="5dp"
app:cardBackgroundColor="#80B3EF"
app:cardCornerRadius="12dp"
app:cardElevation="3dp"
app:contentPadding="4dp" >
```

```xml
android:id="@+id/relativeLayout"
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:padding="16dp">
```

```xml
android:id="@+id/itemImage"
android:layout_width="100dp"
android:layout_height="100dp"
app:layout_constraintLeft_toLeftOf="parent"
app:layout_constraintStart_toStartOf="parent"
app:layout_constraintTop_toTopOf="parent" />
```

```xml
android:id="@+id/itemTitle"
android:layout_width="236dp"
android:layout_height="39dp"
android:layout_marginStart="16dp" />
```

```xml
android:textSize="30sp"
app:layout_constraintLeft_toRightOf="@+id/itemImage"
app:layout_constraintStart_toEndOf="@+id/itemImage"
app:layout_constraintTop_toTopOf="parent" />
```

```xml
android:id="@+id/itemDetail"
android:layout_width="236dp"
android:layout_height="16dp"
android:layout_marginStart="16dp"
android:layout_marginTop="8dp"
app:layout_constraintLeft_toRightOf="@+id/itemImage"
app:layout_constraintStart_toEndOf="@+id/itemImage"
app:layout_constraintTop_toBottomOf="@+id/itemTitle" />
```

## 50.4 添加 RecyclerView

选择 `content_main.xml` 布局文件，从调色板的 `Containers` 部分将 `RecyclerView` 对象拖到布局中，使其位于屏幕中心，它本应自动调整大小以填充整个屏幕。使用 `Infer` 约束工具栏按钮为视图添加任何缺失的布局约束。使用 `Attributes` 工具窗口，将 `RecyclerView` 实例的 `ID` 更改为 `recyclerView`，并将 `layout_width` 和 `layout_height` 属性更改为 `match_constraint`。

## 50.5 添加图片文件

除了两个 `TextView` 之外，卡片布局还包含一个 `ImageView`，该视图已配置 `Recycler adapter` 以显示图像。在项目测试之前，必须添加这些图像。项目将使用的图像命名为 `android_image_.jpg`，可以在从以下 URL 下载的示例代码 `project_icons` 文件夹中找到：

[`www.payloadbooks.com/product/ladybugjava`](https://www.payloadbooks.com/product/ladybugjava)

在你操作系统的文件系统导航器中找到这些图片，选择并复制这八张图片。在 `Project` 工具窗口中右键点击 `app` -> `res` -> `drawable` 项，并选择 `Paste` 将文件添加到文件夹中：

![image-28VJ7YLS.jpg](img/image-28VJ7YLS.jpeg)

图 50-1

## 50.6 创建 RecyclerView Adapter

如上一节所述，`RecyclerView` 需要适配器来处理列表项的创建。在 `Project` 工具窗口中右键点击 `app` -> `java` -> `com.ebookfrenzy.carddemo` 项，并选择 `New` -> `Java Class` 菜单选项将此新类添加到项目中。在新类对话框中，在 `Name` 字段输入 `RecyclerAdapter`，并在列表中选择 `Class`，然后按 `Return` 键创建新的 Java 类文件。

编辑 `RecyclerAdapter.java` 文件以添加一些导入指令，并声明该类现在扩展 `RecyclerView.Adapter`。与其创建一个单独的类来提供要显示的数据，不如向适配器添加一些基础数组作为应用的数据：

```java
package com.ebookfrenzy.carddemo;

import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.ImageView;
import android.widget.TextView;
import androidx.annotation.NonNull;
import androidx.recyclerview.widget.RecyclerView;

public class RecyclerAdapter extends RecyclerView.Adapter {
    final private String[] titles = {
        "Chapter One",
        "Chapter Two",
        "Chapter Three",
        "Chapter Four",
        "Chapter Five",
        "Chapter Six",
        "Chapter Seven",
        "Chapter Eight"
    };

    final private String[] details = {
        "Item one details",
        "Item two details", "Item three details",
        "Item four details", "Item five details",
        "Item six details", "Item seven details",
        "Item eight details"
    };

    final private int[] images = { 
        R.drawable.android_image_1,
        R.drawable.android_image_2,
        R.drawable.android_image_3,
        R.drawable.android_image_4,
        R.drawable.android_image_5,
        R.drawable.android_image_6,
        R.drawable.android_image_7,
        R.drawable.android_image_8 
    };
}
```

在 `RecyclerAdapter` 类中，我们现在需要自己的 `ViewHolder` 类实现，并配置以引用 `card_layout.xml` 文件中的视图元素。留在 `RecyclerAdapter.java` 中，如下如下实现此类：

```java
public class RecyclerAdapter extends RecyclerView.Adapter {
    // ...

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

`ViewHolder` 类包含一个 `ImageView` 和两个 `TextView` 变量，以及一个构造方法，该方法通过对 `card_layout.xml` 文件中三个视图项的引用初始化这些变量。

下一个添加到 `RecyclerAdapter.java` 文件的项是 `onCreateViewHolder` 的实现：

```java
@NonNull
@Override
public ViewHolder onCreateViewHolder(ViewGroup viewGroup, int i) {
    View v = LayoutInflater.from(viewGroup.getContext())
        .inflate(R.layout.card_layout, viewGroup, false);
    return new ViewHolder(v);
}
```

此方法将被 `RecyclerView` 调用以获取 `ViewHolder` 实例。

要添加到 `RecyclerAdapter.java` 的下一个项是 `onBindViewHolder` 方法，它使用索引填充视图数据：

```java
@Override
public void onBindViewHolder(ViewHolder viewHolder, int i) {
    viewHolder.itemTitle.setText(titles[i]);
    viewHolder.itemDetail.setText(details[i]);
    viewHolder.itemImage.setImageResource(images[i]);
}
```

适配器的最后一个要求是实现 `getItemCount()` 方法，在此情况下它返回 `titles` 数组的数量：

```java
@Override
public int getItemCount() {
    return titles.length;
}
```

## 50.7 初始化 RecyclerView 组件

此时，项目包含一个 `RecyclerView` 实例、一个 XML 布局文件和一个 `RecyclerView` 适配器。在测试之前的最后一步是使用布局管理器初始化 `RecyclerView`，创建适配器实例并将其分配给 `RecyclerView` 对象。对于本示例，`RecyclerView` 将配置为使用 `LinearLayoutManager`。

这里有一点复杂性，因为我们需要在 `MainActivity` 类内部使用视图绑定。问题是 `recyclerView` 包含在 `content_main.xml` 中，而该文件又包含在 `activity_main.xml` 中。为了进入 `content_main.xml` 文件，我们需要在包含处为其分配一个 ID。为此，编辑 `activity_main.xml` 文件并修改 `include` 元素如下：

```xml
<include
    android:id="@+id/contentMain"
    layout="@layout/content_main" />
```

为包含的文件分配 ID 后，可以使用以下绑定访问 `recyclerView` 组件：

`binding.contentMain.recyclerView`

现在编辑 `MainActivity.java` 文件并修改 `onCreate()` 方法以实现初始化代码：

```java
package com.ebookfrenzy.carddemo;

// ...

import androidx.recyclerview.widget.LinearLayoutManager;
import androidx.recyclerview.widget.RecyclerView;

// ...

public class MainActivity extends AppCompatActivity {
    private RecyclerView recyclerView;
    private RecyclerView.LayoutManager layoutManager;
    private RecyclerView.Adapter adapter;

    // ...

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        // ...

        setSupportActionBar(toolbar);
        layoutManager = new LinearLayoutManager(this);
        binding.contentMain.recyclerView.setLayoutManager(layoutManager);
        adapter = new RecyclerAdapter();
    }
}
```

```java
binding.contentMain.recyclerView.setAdapter(adapter);
}



## 50.8 测试应用程序

在物理设备或模拟器会话上编译并运行应用，然后滚动列表中的不同卡片项：

![image-HT05V78J.jpg](img/image-HT05V78J.jpeg)

图 50-2

## 50.9 响应卡片选择

此项目的最后一个阶段是使列表中的卡片变为可选择，这样点击卡片就能触发应用内部的事件。在本示例中，卡片将被配置为在用户点击时在显示器上显示消息。为了响应点击操作，需要修改`ViewHolder`类，在每个项目视图上分配一个`OnClickListener`。编辑`RecyclerAdapter.java`文件并修改`ViewHolder`类的声明，使其如下：

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

在`onClick`处理程序的体部中，现在可以添加代码来显示一条消息，指示卡片已被点击。由于点击后执行的操作可能取决于点击了哪张卡片，因此识别选定的卡片也很重要。此信息可以通过调用`RecyclerView.ViewHolder`类的`getAdapterPosition()`方法获取。在留在`RecyclerAdapter.java`文件中，为`onClick`处理程序添加代码，使其如下：

```java
@override

public void onClick(View v) {

    int position = getAdapterPosition();

    Snackbar.make(v, "Click detected on item " + (position + 1),

            Snackbar.LENGTH_LONG)

            .setAction("Action", null).show();

}
```

最后一个任务是启用 Android 应用中点击项目时出现的材质设计波纹效果。这涉及在`card_layout.xml`文件中为`CardView`实例声明添加一些属性，如下：

```xml
xmlns:android="http://schemas.android.com/apk/res/android"

xmlns:card_view="http://schemas.android.com/apk/res-auto"

android:layout_width="match_parent"

android:layout_height="match_parent"

android:id="@+id/card_view"

android:layout_margin="5dp"

app:cardBackgroundColor="#80B3EF"

app:cardCornerRadius="12dp"

app:cardElevation="3dp"

android:contentPadding="4dp"

android:foreground="?selectableItemBackground"

android:clickable="true" >
```

再次运行应用，并验证点击列表中的卡片是否会同时触发接触点的标准波纹效果，以及显示报告所选项目编号的`Snackbar`。

## 50.10 总结

本章介绍了了结合`CardView`和`RecyclerView`组件以显示可滚动卡片式项目列表的步骤。示例还涵盖了对列表项点击的检测，包括识别选中的项目以及在被点击的`CardView`实例上启用波纹效果视觉反馈。

## 51. 布局编辑器示例数据教程

在前一章中创建的`CardDemo`项目提供了一个很好的示例，说明了在完成应用测试之前，从布局编辑器内部准确评估用户界面将如何呈现是多么困难的。当用户界面中要显示的内容只有在用户安装并运行应用后才生成或获取时，这是一个经常发生的问题。

一段时间以来，Android Studio 布局编辑器一直提供了指定简单属性的功能，这些属性仅在设计布局时有效。例如，可以将一个仅限设计时的字符串资源分配给布局编辑器中的`TextView`，该资源在应用运行时不会显示。随着 Android Studio 布局编辑器中引入示例数据支持，这一功能得到了显著扩展，并在本章中使用它来改进`CardDemo`项目中布局编辑器的体验。

## 51.1 为项目添加示例数据

在用户界面布局的设计阶段，`RecyclerView`实例（图 51-1）与上一章末尾测试的运行应用几乎没有相似之处：

![image-O0KNJGHA.jpg](img/image-O0KNJGHA.jpeg)

图 51-1

在书中早前的“使用 Jetpack 构建现代 Android 应用架构”章节中引入了示例数据的概念。为了演示示例数据的使用，现在将修改项目，以便在`RecyclerView`中显示填充好的卡片。在此之前，值得注意的是布局编辑器有一系列预配置示例数据模板可以在设计用户界面时使用。为了查看这些效果，加载`content_main.xml`布局文件并选择`RecyclerView`实例。右键点击`RecyclerView`并选择`Set Sample Data`选项以显示工具属性面板：

![image-KXT0S7C.jpg](img/KXT0S7C.jpeg)

图 51-2

将模板更改为`Email`项目计数更改为 12，注意`RecyclerView`的变化如下：

![image-CFY4CM.jpg](img/CFY4CM.jpeg)

图 51-3

这些模板在无需额外工作的情况下显示数据非常有用，且通常足以完成布局。然而，在本示例中，将使用示例数据来显示卡片在应用中的预期样式。当布局编辑器中仍加载`content_main.xml`文件时，切换到代码模式并找到`RecyclerView`元素，其内容如下：

```xml
android:id="@+id/recyclerView"

android:layout_width="0dp"

android:layout_height="0dp"

app:layout_constraintBottom="parent"

app:layout_constraintEnd_toEndOf="parent"

app:layout_constraintStart_toStartOf="parent"

app:layout_constraintTop_topTopOf="parent"

tools:itemCount="12"

tools:listitem="@layout/recycler_item" />
```

注意用于配置 12 个项目的`tools`属性，每个项目都使用包含在某个文件中的布局。布局编辑器提供了一系列可以在布局文件中配置的`tools`选项。虽然所有这些设置超出了本书的范围，但可以在以下 URL 找到完整描述：

https://developer.android.com/studio/write/tool-attributes#toolssamplesources

上述的`recycler_item`文件是在选择示例数据模板时自动生成的，可以在项目工具窗口中找到。切换回设计模式，在选中`RecyclerView`的情况下，使用设计时工具属性面板将模板切回默认设置。`recycler_item`文件将从项目中删除，同时删除`content_main.xml`XML 文件中的两个`tools`属性行（如果 Android Studio 未能删除这些行，可以从代码视图中手动删除）。

图 51-5

下一步是在卡片布局的视图中显示一些图像和不同的文本。这既可以通过布局编辑器提供的模板示例数据形式实现，也可以专门为此项目添加自定义的示例数据。将`card_layout.xml`文件加载到布局编辑器中，选择`ImageView`，并按照本章较早之前概述的方法显示设计时视图属性（Design-time View Attributes）面板。从`srcCompat`菜单中，选择下方图 51-6 所示的内置背景/风景集：

![image-VQXVA6B8.jpg](img/image-VQXVA6B8.jpeg)

图 51-6

接下来，右键点击`itemTitle` `TextView`对象，选择`Set Sample Data`（设置示例数据）菜单选项，并在设计时属性面板中选择`cities`文本选项。对`itemDetail`视图重复此步骤，这次如图 51-7 所示选择`full_names`选项：

![image-9R9D5O0E.jpg](img/image-9R9D5O0E.jpeg)

图 51-7

在设计模式下打开`content_main.xml`文件，并注意`RecyclerView`现在正在使用内置图像和示例文本数据：

![image-SDWPRIZJ.jpg](img/image-SDWPRIZJ.jpeg)

图 51-8

## 51.2 使用自定义示例数据

本章的最后一步是演示布局编辑器中使用自定义示例数据和图像。这需要创建一个示例数据目录并添加一些文本和图像文件。在 Project（项目）工具窗口中，右键点击`app`条目并选择`New -> Sample Data Directory`（新建 -> 示例数据目录）菜单选项，此时 Project 工具窗口中将出现一个名为`sampledata`的新目录。如果新文件夹不可见，将 Project 工具窗口从`Android`模式切换到`Project`模式，并在图 51-9 所示的`CardDemo -> app`下找到该文件夹：

![image-QSGE6NT3.jpg](img/image-QSGE6NT3.jpeg)

图 51-9

右键点击`sampledata`目录，创建一个名为`images`的目录，并按照上一章概述的相同步骤将 Android 图像复制并粘贴到新文件夹中。在`card_layout.xml`文件中再次显示`ImageView`的设计时视图属性面板，这次点击`Browse`（浏览）链接并在资源对话框选择新添加的 Android 图像（如果 images 文件夹未出现，请尝试重建项目）：

![image-K85T925M.jpg](img/image-K85T925M.jpeg)

图 51-10

再次右键点击`sampledata`目录，选择`New -> File`（新建 -> 文件）选项，将文件命名为`chapters`并输入以下内容：

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

接下来，创建一个名为`items`的第二个文本文件，内容如下：

```
Item one details

Item two details

Item three details

Item four details

Item five details

Item six details

Item seven details

Item eight details
```

创建示例数据文本文件后，剩下的就是如下所示在`card_layout.xml`文件的视图元素中引用它们：

```xml
android:id="@+id/itemTitle"

android:layout_width="236dp"

android:layout_height="39dp"

android:layout_marginStart="16dp"

android:textSize="30sp"

app:layout_constraintLeft_toRightOf="@+id/itemImage"

app:layout_constraintStart_toEndOf="@+id/itemImage"

app:layout_constraintTop_toTopOf="parent"

tools:text="@sample/chapters" />

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

重建应用并返回到`content_main.xml`文件中的布局设计，此时自定义示例数据和图像应该显示在`RecyclerView`列表中：

![image-IACG7X0G.jpg](img/image-IACG7X0G.jpeg)

图 51-11

除了使用两个独立的文本文件并对图像集的引用，另一种选项是在 JSON 文件中声明示例数据。例如：

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

    },

    .

  ]

}
```

假设上述内容包含在名为`chapterdata.json`的文件中，则在视图 XML 元素中引用示例数据如下：

```xml
.

.

.

tools:src="@sample/chapterdata.json/mydata/image" />

.

.

tools:text="@sample/chapterdata.json/mydata/chapter" />

.

.

tools:text="@sample/chapterdata.json/mydata/details" />
```




## 51.3 总结

本章演示了在布局编辑器中使用示例数据来提供更真实的表示。

## 52. 使用 AppBar 和折叠工具栏

在本章中，我们将探索如何自定义 Activity 中的应用栏并使其对滚动事件做出反应。通过 `CoordinatorLayout` 配合 `AppBarLayout` 和 `CollapsingToolbarLayout`，可以配置应用栏进入退出视图。例如，列表的向上滚动可以配置为让应用栏消失并在向下滚动时重新出现。

### 52.1 AppBar 的结构

AppBar 是应用程序运行时显示在屏幕顶部的区域，可以配置为包含状态栏、工具栏和弹性区域。图 52-1 示例展示了一个包含状态栏、工具栏和标签栏的应用栏：

![image-D9MH7WAE.jpg](img/image-D9MH7WAE.jpeg)

图 52-1

空白背景色可以填充弹性区域，或者如图 52-2 所示，在 `ImageView` 上显示图像：

![image-I7I122WZ.jpg](img/image-I7I122WZ.jpeg)

图 52-2

正如本章其余部分将演示的，如果 Activity 用户界面布局的主区域包含可滚动内容，应用栏的元素可以根据内容的滚动进行展开和收缩。

### 52.2 示例项目

对于此示例，我们将对早期章节“Android RecyclerView 和 CardView 教程”创建的项目进行修改。首先启动 Android Studio 并加载该项目。

项目加载后，运行应用并注意当向上滚动列表时工具栏仍然可见，如图 52-3 所示：

![image-IAJX76LJ.jpg](img/image-IAJX76LJ.jpeg)

图 52-3

### 52.3 协调 RecyclerView 和工具栏

第一步是进行配置，使工具栏在向上滚动运动期间收缩，并在向下滚动时展开。

`CoordinatorLayout` 同样可以用于根据视图层级中某些视图的滚动动作，使应用栏（app bar）的元素滑入或滑出。图 52-4 所示布局层级中的一个元素是 `ConstraintLayout`。要实现这种协调行为，必须在发生滚动的元素以及与滚动进行协调的元素上设置属性。

在滚动元素上（在此例中为 `RecyclerView`），必须将 `android:layout_behavior` 属性设置为 `appbar_scrolling_view_behavior`。在 `content_main.xml` 文件中，找到顶层 `ConstraintLayout` 元素，并注意该属性已默认设置：

```xml
xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
app:layout_behavior="@string/appbar_scrolling_view_behavior">
```

接下来，在布局编辑器中打开 `activity_main.xml` 文件，切换到 Code 模式并找到 `AppBarLayout` 元素。注意视图层级中 `AppBarLayout` 的唯一子元素是 `Toolbar`。为了让工具栏响应发生于 `RecyclerView` 的滚动事件，必须在该元素上设置 `app:layout_scrollFlags` 属性。赋给此属性的值取决于所需的交互性质，必须由以下一个或多个选项组成：

* `scroll` – 表示视图将滚动到屏幕外。如果不设置此项，在滚动事件期间，视图将固定在屏幕顶部。
* `enterAlways` – 当与 `scroll` 选项配合使用时，向上滚动动作将导致视图收回。在此模式下，任何向下的滚动动作都会导致视图重新出现。
* `enterAlwaysCollapsed` – 设置在视图上时，在向下滚动动作达到列表限制之前，该视图将不会从折叠状态展开。如果设置了 `minHeight` 属性，视图将在初始滚动动作期间出现，但仅持续到达到高度为止。随后，它将保持在该高度，在到达列表顶部之前不会完全展开。请注意，此选项仅在同时使用 `enterAlways` 和 `scroll` 选项时有效。例如：

```xml
app:layout_scrollFlags="scroll|enterAlways|enterAlwaysCollapsed"
android:minHeight="20dp"
```

* `exitUntilCollapsed` – 设置后，视图将在向上滚动动作期间折叠，直到达到 `minHeight` 阈值。在此时点，它将保持在该高度，直到滚动方向改变。

对于此示例，将如下所示地在 `Toolbar` 上设置 `scroll` 和 `enterAlways` 选项：

```xml
android:id="@+id/toolbar"
android:layout_width="match_parent"
android:layout_height="?attr/actionBarSize"
app:layout_scrollFlags="scroll|enterAlways" />
```

设置好相应的属性后，重新运行应用并在 `RecyclerView` 列表中执行向上滚动动作。这应该导致工具栏折叠出视图（图 52-5）。向下的滚动动作则应导致工具栏重新出现。

![image-J9P1LVP7.jpg](img/image-J9P1LVP7.jpeg)

图 52-5

### 52.4 引入折叠工具栏布局

`CollapsingToolbarLayout` 容器通过提供更多选项，以及对应用栏及其子元素响应协调滚动动作时的折叠行为的控制，增强了标准工具栏。`CollapsingToolbarLayout` 类设计用于作为 `AppBarLayout` 的子元素添加。它提供了诸许多功能，例如随着工具栏的折叠和展开自动调整工具栏标题的字体大小。`parallax` 模式允许应用栏中的指定内容在折叠时淡出，而 `pin` 模式则允许应用栏的元素在收缩期间保持在固定位置。

还可以使用 `scrim` 选项来指定工具栏在折叠序列期间过渡的颜色。

为了看到这些功能的演示，将修改 `activity_main.xml` 文件中包含的应用栏，使其使用 `CollapsingToolbarLayout` 类，并添加一个 `ImageView` 以更好地演示 `parallax` 模式的效果。使用 `CollapsingToolbarLayout` 的新视图层级如图 52-6 所示所示：

![image-KWL4IQRH.jpg](img/image-KWL4IQRH.jpeg)

图 52-6

在布局编辑器的 Code 模式下加载 `activity_main.xml` 文件，并修改布局使其内容如下：

```xml
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
android:fitsSystemWindows="true"
tools:context=".MainActivity">

android:layout_width="match_parent"
android:layout_height="wrap_content"
android:fitsSystemWindows="true">

android:id="@+id/collapsing_toolbar"
android:layout_width="match_parent"
android:layout_height="match_parent"
app:layout_scrollFlags="scroll|enterAlways"
android:fitsSystemWindows="true"
app:expandedTitleMarginBottom="30dp"
app:expandedTitleMarginStart="15dp"
app:expandedTitleMarginEnd="64dp">

android:id="@+id/backdrop"
android:layout_width="match_parent"
android:layout_height="200dp"
android:scaleType="centerCrop"
android:fitsSystemWindows="true"
app:layout_collapseMode="parallax"
android:src="@drawable/appbar_image" />

android:id="@+id/toolbar"
android:layout_width="match_parent"
android:layout_height="?attr/actionBarSize"
app:layout_scrollFlags="scroll|enterAlways"
app:layout_collapseMode="pin" />

android:id="@+id/contentMain"
layout="@layout/content_main" />
```

使用操作系统的文件导航器找到项目文件夹中的 `appbar_image.jpg` 文件并将其复制到项目中。

运行时，应用栏应如图 52-7 所示：

![image-GA36ZCO3.jpg](img/image-GA36ZCO3.jpeg)

图 52-7

向上滚动列表会导致应用栏逐渐折叠。在收缩期间，图像将淡变为 `scrim` 属性定义的颜色，同时标题文本字体大小以相应的速率缩小，直到只剩下工具栏：

![image-V5LG3G0.jpg](img/image-V5LG3G0.jpeg)

图 52-8

在滚动动作的初始阶段，工具栏保持可见（如果继续向上滚动，工具栏也将滑出视图），这是因为 `activity_main.xml` 文件中的工具栏元素配置为使用 `pin` 模式：

`app:layout_collapseMode="pin"`

如果折叠模式设置为 `parallax`，则工具栏将与图像视图一起收回。

继续向上滚动将导致工具栏也折叠，只留状态栏可见：

![image-5ESQFJSN.jpg](img/image-5ESQFJSN.jpeg)

图 52-9

由于 `CollapsingToolbarLayout` 元素的滚动标志属性包含了 `enterAlways` 选项，向下滚动动作将导致应用栏再次展开。

为了固定工具栏位置使其在向上滚动动作期间不再滑出视图，请将 `activity_main.xml` 文件中 `CollapsingToolbarLayout` 元素的 `layout_scrollFlags` 属性中的 `enterAlways` 替换为 `exitUntilCollapsed`：

```xml
app:layout_scrollFlags="scroll|exitUntilCollapsed"
```

作为最后一个任务，编辑 `MainActivity.java` 文件并在 `onCreate()` 方法中添加一些代码，以更改折叠布局管理器（collapsing layout manager）实例上的标题，并设置不同的遮罩颜色（scrim color）（注意遮罩颜色也可以在布局资源文件中设置）：

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



最后运行一次应用，注意新标题出现在应用栏中，并且现在滚动会导致工具栏在收回视图时过渡到绿色。

## 52.6 总结

大多数 Android 应用顶部的应用栏可以由几个元素组成，包括`toolbar`、`tab layout`和`image view`。当它嵌入到`CoordinatorLayout`父布局中时，有多种不同的选项可以控制应用栏响应活动主内容中滚动事件的行为。为了对这种行为进行更细致的控制，`CollapsingToolbarLayout`布局提供了一系列额外的控制级别，用于控制应用栏内容相对于滚动活动的展开和收缩。

## 53. Android 服务概述

`Android Service`类旨在允许应用程序启动并执行后台任务。与广播接收器（broadcast receivers）不同，接收器旨在快速执行任务后退出，而服务旨在执行耗时较长的任务（例如通过互联网连接下载文件或向用户流式音乐），但不需要用户界面。

本章将提供可用服务的概述，包括绑定服务（bound services）和意图服务（intent services）。在涵盖这些基础知识后，后续章节将通过一些示例来演示服务。

### 53.1 Intent Service

如前所述，服务默认在与启动它的组件相同的主线程中运行。因此，服务需要执行的任何 CPU 密集型任务应该在新线程中进行，从而避免影响调用应用程序的性能。

`JobIntentService`类是一个便利类（继承自`Service`类），它为处理后台任务设置了一个工作线程，并异步处理每个请求。一旦服务处理了所有队列中的请求，它就会退出。使用`JobIntentService`类时，只需要实现`onHandleWork()`方法，该方法包含为每个请求要执行的代码。

对于不需要同步处理请求的服务，`JobIntentService`是推荐的选项。然而，需要同步处理请求的服务需要继承自`Service`类，并手动实现和管理线程，以高效地处理任何 CPU 密集型任务。

### 53.2 Bound Service

绑定服务（bound service）允许启动组件与服务进行交互并接收其结果。这种交互也可以通过实现进程间通信（IPC）跨越进程边界进行。例如，一个活动可能会启动一个服务来处理音频播放。该活动极可能会包含一个用户界面，为用户提供暂停播放或跳到下一曲的控制。同样，服务可能需要向调用的活动通信信息，以指示当前音频轨道已结束，并提供即将开始播放的下一曲的详情。

组件（在此上下文中称为客户端）通过调用`bindService()`方法启动并绑定到绑定服务。此外，多个组件可以同时绑定到一个服务。当客户端不再需要该服务绑定时，应该调用`unbindService()`方法。当最后一个绑定的客户端从服务取消绑定时，Android 运行时系统将终止该服务。需要注意的是，绑定服务也可以通过调用`startService()`启动。一旦启动，组件就可以通过`bindService()`调用绑定它。当通过调用`startService()`启动绑定服务时，即使在最后一个客户端从其取消绑定后，它也会继续运行。

绑定服务必须包含`onBind()`方法的实现，该方法在服务最初创建以及其他客户端随后绑定到运行中的服务时都会被调用。该方法的目的是向绑定客户端返回一个`IBinder`类型的对象，其中包含了客户端与服务通信所需的信息。

在实现客户端与绑定服务之间的通信时，推荐的技术取决于客户端和服务端是否位于同一个进程或不同的进程中，以及服务是否对客户端私有。本地通信可以通过扩展`Binder`类并在`onBind()`方法中返回实例来实现。另一方面，进程间通信需要`Messenger`和`Handler`的实现。这两种方法的细节将在后面的章节中介绍。

### 53.3 服务的内部结构

如前所述，服务必须创建为`Android Service`类的子类（具体地说是`android.app.Service`）或其子类（例如`android.app.IntentService`）。在子类化的过程中，取决于所创建的服务的确切性质，必须重写以下一个或多个父类回调方法：

- `onStartCommand()` – 当另一个组件通过调用`startService()`方法启动服务时调用此方法。绑定服务不需要实现此方法。
- `onBind()` – 当组件通过调用`bindService()`方法绑定到服务时调用。在实现绑定服务时，此方法必须返回一个促进通信的`IBinder`对象。
- `onCreate()` – 旨在执行初始化任务的地方，该方法在调用`onStartCommand()`或首次调用`onBind()`之前立即调用。
- `onDestroy()` – 在服务被销毁时调用。
- `onHandleWork()` – 仅适用于`JobIntentService`子类。该方法被调用以处理服务的逻辑。它在独立于主线程的线程中执行。

注意，`IntentService`类包含了`onStartCommand()`和`onBind()`回调方法的实现，因此在子类中不需要实现这些方法。

### 53.4 控制销毁服务的重启选项

`onStartCommand()`回调方法要求返回一个整数值，以定义当 Android 运行时系统销毁服务时发生什么。这些方法的可能返回值如下：

- `START_NOT_STICKY` – 指示系统如果服务被销毁，除非有等待交付的意图，否则不要重启它。
- `START_STICKY` – 指示系统如果服务在`onStartCommand()`方法返回后被销毁，则应尽快重启它。如果没有等待交付的意图，调用`onStartCommand()`回调方法将传入`NULL`意图值。服务销毁时正在处理的意图将被丢弃。
- `START_REDELIVER_INTENT` – 表示如果服务从`onStartCommand()`回调方法返回后被销毁，则应该重启服务，并将当前的 intent 重新投递到`onStartCommand()`方法，随后投递任何待处理的 intent。

## 53.5 在清单文件中声明服务

要使服务（Service）可用，必须首先在清单文件中进行声明。这涉及到在现有条目中嵌入一个配置适当的元素。至少，该元素必须包含一个声明服务类名的属性，如下所示的 XML 片段所示：

```xml
android:icon="@mipmap/ic_launcher"
android:label="@string/app_name"
android:name=".MainActivity" >
```

默认情况下，服务是公开的，因为它们可以被其所在应用包之外的组件访问。要将服务设为私有，必须在清单文件的元素中将`android:exported`属性声明为`false`。例如：

```xml
android:exported="false">
```

在使用`JobIntentService`时，清单中的`Service`声明还必须如下所示请求`BIND_JOB_SERVICE`权限：

```xml
android:name=".MyJobIntentService"
android:permission="android.permission.BIND_JOB_SERVICE" />
```

如前所述，服务默认在与调用组件相同的进程中运行。要强制服务运行在自己的进程中，请向该元素添加`android:process`属性，并声明一个以冒号（`:`）开头的进程名称：

```xml
android:exported="false"
android:process=":myprocess">
```

冒号前缀表示新进程对于本地应用程序是私有的。然而，如果进程名是以小写字母而不是冒号开头，该进程将是全局的，可供其他组件使用。

最后，通过与 Activity 相同的 intent 过滤器机制，服务还可以向设备上运行的其他应用程序发布其能力。有关意图过滤器的更多细节，请参考“Android Intent 概述”章节。

## 53.6 在系统启动时启动运行的服务

考虑到服务的后台性质，在基于 Android 系统首次启动时需要启动服务并不罕见。这可以通过创建一个广播接收器（Broadcast Receiver）来实现，并配置意图过滤器以监听系统`android.intent.action.BOOT_COMPLETED`意图。当检测到此类意图时，广播接收器将调用必要的服务然后返回。注意，为了能够运行，此类广播接收器必须请求`android.permission.RECEIVE_BOOT_COMPLETED`权限。

## 53.7 总结

Android 服务是一种强大的机制，允许应用程序在后台执行任务。服务一旦启动，无论调用它的应用程序是否是前台任务，即使启动服务的组件被销毁，它都将继续运行。

服务继承自`Android Service`类。绑定服务（Bound services）为其他客户端组件提供了通信接口，并且通常一直运行到最后一个客户端从服务取消绑定（unbind）为止。

默认情况下，服务在与调用应用程序相同的进程和主线程中本地运行。因此，应该在服务内部创建一个新线程来处理 CPU 密集型任务。通过对应用程序清单文件中相应条目进行细微配置更改，可以在单独进程中启动远程服务（Remote services）。

`IntentService`类（`Android Service`类的子类）提供了一种方便的机制，用于在单独的工作线程中处理异步服务请求。

## 54. Android Intent 概述

到本书的这个阶段，读者应该已经清楚 Android 包含一个或多个 Activity 等内容。然而，一个尚未详细介绍的领域是一个 Activity 触发另一个 Activity 的机制。正如“Android 应用剖析”章节中所简概述的那样，这主要是通过 Intent（意图）实现的。

在后续章节中通过基于 Android Studio 的示例实现之前，本章旨在以显式意图（explicit intents）和隐式意图（implicit intents）的形式提供 Intent 的概述，并介绍意图过滤器（intent filters）。

## 54.1 Intent 概述

Intent (`android.content.Intent`) 是 Activity 启动另一个 Activity 的消息系统。例如，Activity 可以发出一个 intent 来请求启动同一应用程序中的另一个 Activity。Intent 的概念还超出了此范围，它允许 Activity 请求设备上任何其他已适当注册并配置了权限的 Activity 服务。例如，考虑一个应用程序内包含一个需要加载并向用户显示网页的 Activity。与其让应用程序包含第二个 Activity 来执行此任务，不如代码可以向 Android 运行时发送一个 intent，请求任何注册了显示网页能力的 Activity 服务。运行时系统会将请求与设备上可用的 Activity 进行匹配，并启动匹配的 Activity，或者在存在多个匹配的情况下，允许用户决定使用哪个 Activity。

Intent 还允许数据从发送方 Activity 传输到接收方 Activity。在之前描述的场景中，例如，发送方 Activity 需要将显示的网页 URL 发送到第二个 Activity。同样，接收方 Activity 可以配置为在所需任务完成后向发送方 Activity 返回数据。

虽然在后面的章节中才会介绍，但值得强调，除了启动 Activity 外，Intent 还用于启动并与服务及广播接收器进行通信。

Intent 分为显式或隐式。

## 54.2 显式意图

显式意图通过引用目标 Activity 的组件名称（即类名）来请求启动特定的 Activity。当启动与发送方 Activity 同一应用程序的 Activity 时，这种方法最常见（因为开发者知道类名）。

显式意图是通过创建`Intent`类的实例并传递 Activity 上和要启动的 Activity 组件名称来实现。然后调用`startActivity()`方法并将 intent 对象作为参数。例如，以下代码片段为类名为`ActivityB`的 Activity 发出一个显式意图：

```java
Intent i = new Intent(this, ActivityB.class);
startActivity(i);
```

可以在启动 intent 对象之前，通过调用`putExtra()`方法将数据传输到接收方 Activity。数据必须以键值对的形式添加。以下代码扩展了之前的示例，分别向 intent 添加键为`"myString"`和`"myInt"`的字符串和整数值：

```java
Intent i = new Intent(this, ActivityB.class);
i.putExtra("myString", "This is a message for ActivityB");
i.putExtra("myInt", 100);
startActivity(i);
```

目标 Activity 通过`Bundle`对象接收数据，可以通过调用`getIntent().getExtras()`获取。`Activity`类的`getIntent()`方法返回启动 Activity 的 intent，而`getExtras()`方法（`Intent`类的）返回包含数据的`Bundle`对象。例如，提取传递给`ActivityB`的数据值：

```java
Bundle extras = getIntent().getExtras();
if (extras != null) {
    String myString = extras.getString("myString");
    int myInt = extras.getInt("myInt");
}
```

当使用意图（intent）启动应用程序内的其他活动时，这些活动必须在应用程序清单文件（manifest）中列出。以下`AndroidManifest.xml`内容对于包含名为`ActivityA`和`ActivityB`的活动的应用程序是配置正确的：

```xml
package="com.ebookfrenzy.intent1.intent1" >
android:icon="@mipmap/ic_launcher"
android:label="@string/app_name" >
android:label="@string/app_name"
android:name="com.ebookfrenzy.intent1.intent1.ActivityA" >
android:name="ActivityB"
android:label="ActivityB" >
```

## 54.3 从 Activity 返回数据

如上一节的示例所示，虽然数据传输到了`ActivityB`，但没有方法可以将数据返回给第一个活动（我们将其称为`ActivityA`）。然而，这可以通过将`ActivityB`启动为`ActivityA`的子活动（sub-activity）来实现。通过创建`ActivityResultLauncher`实例可以启动活动作为子活动。`ActivityResultLauncher`实例是通过调用`registerForActivityResult()`方法创建的，并以 lambda 表达式的形式传递一个回调处理程序。当子活动返回时，将调用此处理程序并传递返回数据。一旦创建了`ActivityResultLauncher`实例，就可以带意图参数调用它来启动子活动。创建`ActivityResultLauncher`实例的代码通常如下：

```java
ActivityResultLauncher startForResult = registerForActivityResult(
    new ActivityResultContracts.StartActivityForResult(),
    new ActivityResultCallback() {
        @Override
        public void onActivityResult(ActivityResult result) {
            if (result.getResultCode() == Activity.RESULT_OK) {
                Intent data = result.getData();
                // 处理返回数据的代码
            }
        }
    }
);
```

一旦启动器就绪，可以如下方式调用并传递要启动的意图：

```java
Intent i = new Intent(this, ActivityB.class);
.
.
startForResult.launch(i);
```

要将数据返回给父活动，子活动必须实现`finish()`方法，其目的是创建一个包含要返回数据的新意图对象，然后调用封装的的`setResult()`方法，传递结果代码和包含返回数据的意图。结果代码通常是`RESULT_OK`或`RESULT_CANCELED`，但也可以根据开发者的需求自定义值。如果子活动崩溃，父活动将接收`RESULT_CANCELED`结果代码。

下面的代码说明了典型的子活动`finish()`方法代码：

```java
public void finish() {
    Intent data = new Intent();
    data.putExtra("returnString1", "给父活动的消息");
    setResult(RESULT_OK, data);
    super.finish();
}
```



## 54.4 隐式意图

与显式意图（`explicit intents`）引用要启动的活动的类名不同，隐式意图通过指定要执行的动作（`action`）和接收活动要处理的数据类型来标识要启动的活动。例如，`ACTION_VIEW` 类型的动作配合 `URI` 对象形式的网页 URL，将指示 Android 系统搜索并随后启动能够处理网络浏览器的活动。以下隐式意图在 Android 设备上执行时，将导致指定的网页在网络浏览器活动中显示：

```java
Intent intent = new Intent(Intent.ACTION_VIEW,

    Uri.parse("https://www.ebookfrenzy.com"));

startActivity(intent);
```

当活动发布上述隐式意图时，Android 系统将通过称为意图解析（`intent resolution`）的过程搜索设备上已注册了处理 HTTP 方案数据的 `ACTION_VIEW` 请求能力的活动。在系统使用隐式意图启动活动之前，用户必须验证或启用该活动。如果这两个条件都不满足，该活动将不会通过意图启动。在探索这两个选项之前，我们首先需要谈论意图过滤器（`intent filters`）。

## 54.5 使用意图过滤器

意图过滤器是活动向 Android 意图解析过程“宣告”其支持的动作和数据处理能力的机制。这些声明还包括了执行链接验证过程所需的设置。以下 `AndroidManifest.xml` 文件演示了名为 `MyWebView` 的应用中名为 `WebActivity` 的活动的配置，并配备了恰当的意图过滤器：

```xml
.

.

android:allowBackup="true"

android:icon="@mipmap/ic_launcher"

android:label="@string/app_name"

android:roundIcon="@mipmap/ic_launcher_round"

android:supportsRtl="true"

android:theme="@style/Theme.MyWebView">

android:name="WebActivity"

android:exported="true">
```

...当意图包含 `https://www.ebookfrenzy.com` URL 时，响应另一个活动发的隐式意图而启动。例如，下面的代码将启动 `WebActivity` 活动（假设 `MyWebView` 应用已被用户验证或启用作为支持链接）：

```java
Intent intent = new Intent(Intent.ACTION_VIEW,

    Uri.parse("https://www.ebookfrenzy.com"));

startActivity(intent);
```

## 54.6 自动链接验证

使用网页链接启动 Android 设备上的活动被认为存在潜在的安全风险。为了最小化这种风险，所用于启动意图的链接必须经过自动验证或由用户手动添加到支持列表中。要启用自动验证，相应的意图声明必须将 `autoVerify` 设置为 `true`：

```xml
.

.
```

接下来，链接必须与基础网站关联。这是通过在网站的 `.well-known` 文件夹内创建一个名为 `assetlinks.json` 的数字资产文件来实现的。数字资产文件包含一个允许目标应用使用网站链接的关系声明，以及一个声明包名和 SHA256 指纹的目标语句。一个典型的资产文件可能如下：

```json
[{

"relation": ["delegate_permission/handle_all_urls"],

"target": {

"namespace": "android_app",

"package_name": "com.ebookfrenzy.mywebview",

"sha256_fingerprints":

[""]

}

}]
```

工具可用：[`developers.google.com/digital-asset-links/tools/generator`](https://developers.google.com/digital-asset-links/tools/generator)

在使用 Android 时，`namespace` 值始终设置为 `android_app`，而 `package_name` 对应要启动的应用包。最后，证书指纹是构建应用程序的哈希值。当你测试应用程序时，这将 `debug.keystore` 文件中的调试证书。在 Windows 系统上，Android Studio 将此文件存储在以下位置：

`\Users\.android\debug.keystore`

在 macOS 和 Linux 系统上，可以在此处找到文件：

`HOME/.android/debug.keystore`

找到文件后，可以通过在终端或命令行窗口中运行以下命令获取 SHA 256 指纹：

```bash
keytool -list -v -keystore
```

当提示密码时，输入 `android`，之后将出现输出，包括 SHA 256 指纹：

```text
Certificate fingerprints:

SHA1: 11:E8:66:11:B6:94:3D:AA:7E:50:63:99:77:B8:6A:90:FF:B6:9C:6D

SHA256: 7F:EE:E3:C8:38:41:C3:EA:11:56:83:94:2A:4C:D2:EA:A0:69:F8:96:D1:17:77:02:46:EC:AD:6E:3C:64:A9:29
```

当你准备好构建应用程序的发布版本时，必须确保已将发布版本的 SHA 256 指纹添加到资源文件中。生成发布版密钥库文件的详细信息请参见名为“创建、测试和上传 Android App Bundle”的章节。一旦你拥有了发布版密钥库文件，运行上述 `keytool` 命令来获取指纹。

一旦你将数字资源文件放置在网站上的正确位置，请在设备或模拟器上安装应用并等待 30 秒以验证链接。要检查验证状态，请在命令行或终端提示符运行以下命令：

```
adb shell pm get-app-links --user cur com.example.mywebview
```

输出结果应包含对链接已验证的确认：

```
com.example.mywebview:

ID: 0e399bca-bf58-4cfc-8c7b-d1a6c3b065ec

Signatures: [7F:EE:E3:C8:38:41:C3:EA:11:56:83:94:2A:4C:D2:EA:A0:69:F8:96:D1:17:77:02:46:EC:AD:6E:3C:64:A9:29]

Domain verification state:

www.ebookfrenzy.com: verified

User 0:

Verification link handling allowed: true

Selection state:

Disabled:

www.ebookfrenzy.com
```

你也可以通过以下步骤在设备或模拟器上的 `Settings`（设置）应用中检查状态：

1. 启动 `Settings` 应用。
2. 从主列表中选择 `Apps`（应用）。
3. 从已安装的应用列表中找到并选择你的应用。
4. 在应用的设置页面上，选择 `Open by Default`（默认打开）选项。

在应用的设置页面上选择 `Open by Default` 选项。

一旦显示，该页面应指示链接已验证，如图 54-1 所示：

![image-0VOTDMY6.jpg](img/image-0VOTDMY6.jpeg)

图 54-1

要查看哪些链接已通过验证，点击上图箭头指示的详情按钮以显示以下面板：

![image-L7LZJWQU.jpg](img/image-L7LZJWQU.jpeg)

图 54-2

`assetlinks.json` 文件可以包含多个数字资源链接，允许单个网站与多个应用关联。如果你无法使用自动链接验证，请在你的应用中添加代码以提示用户手动启用链接。

## 54.7 手动启用链接

在无法使用上述步骤自动验证链接的情况下，唯一的选择是请求用户手动启用应用链接。这涉及启动目标应用 `Settings` 应用中的 `Open by Default`（默认打开）屏幕，用户可以在该处启用链接。

由于 `Open by Default` 屏幕突然出现可能会让普通用户感到困惑，建议在启动 `Settings` 应用之前显示一个说明对话框。

为了给用户提供手动启用链接的选项，在尝试启动 `intent` 之前需要执行以下代码：

```
// 此处编写代码以显示对话框，解释需要启用链接

Intent intent = new Intent(

    Settings.ACTION_APP_OPEN_BY_DEFAULT_SETTINGS,

    Uri.parse("package:com.ebookfrenzy.mywebview"));

startActivity(intent);
```

上述示例代码将为我们的目标应用 `MyWebView` 显示 `Open by Default` 设置屏幕，用户可以在该处点击 `Add Link`（添加链接）按钮：

![image-OV3CZTUE.jpg](img/image-OV3CZTUE.jpeg)

图 54-3

点击后，将弹出一个对话框，并使用传入 `intent` 的链接进行初始化。通过勾选如附 54-4 所示的复选框可以启用该链接：

![image-5JJE40QK.jpg](img/image-5JJE40QK.jpeg)

图 54-4

## 54.8 检查 Intent 的可用性

通常认为假设某个 activity 对于特定的 `intent` 可用是不明智的，特别是因为缺少匹配的 action 通常会导致应用程序崩溃。幸运的是，在将其发送到运行时系统之前，可以识别 activity 对于特定 `intent` 的可用性。可以使用以下方法识别指定 `intent` action 类型的 activity 的可用性：

```java
public static boolean isIntentAvailable(Context context, String action) {

    final PackageManager packageManager = context.getPackageManager();

    final Intent intent = new Intent(action);

    List list = packageManager.queryIntentActivities(intent,

            PackageManager.MATCH_DEFAULT_ONLY);

    return list.size() > 0;

}
```

## 54.9 总结

Intent 是一个 Android activity 启动另一个 activity 的消息机制。显式 `intent` 通过类名引用接收方 activity 来引用要启动的特定 activity。显式 intent 通常（但并非限于）用于启动同一应用程序内的 activity。隐式 `intent` 指定了要执行的动作和要处理的数据类型，并让 Android 运行时找到匹配的 activity 来启动。隐式 intent 通常用于启动位于不同应用程序中的 activity。

在处理隐式 intent 时，安全限制要求用户在启动 `intent` 之前，自动验证或手动启用包含 `intent` 目标 activity 的应用。自动验证涉及在与链接 URL 对应的网站上放置数字资产链接文件。

activity 可以将数据封装在 `intent` 对象中向接收方传递数据。只有当 activity 作为发送活动的子活动启动时，才能从其返回数据。

接下来，添加一个 `Plain Text` 对象，使其水平居中并放置在 `TextView` 顶部的上方。使用 `Attributes` 工具窗口，移除分配给文本属性的“Name”字符串，并将 ID 设置为 `editText1`。布局完成后，点击工具栏上的 `Infer constraints`（推断约束）按钮以添加适当的约束：

![image-ABIIAL08.jpg](img/image-ABIIAL08.jpeg)
图 55-1

最后，点击 `Layout Editor` 窗口右上角的红色警告按钮，并使用生成的面板将“Send Text”字符串提取到名为 `send_text` 的资源中。布局完成后，用户界面应该类似于图 55-2 所示：

![image-D6WNC3DR.jpg](img/image-D6WNC3DR.jpeg)
图 55-2

## 55.3 创建第二个 Activity 类

当用户触摸“Send Text”按钮时，将发出一个 `intent`，请求启动第二个 activity，用户可以在其中输入响应。因此，下一步是创建第二个 activity。在 `Project` 工具窗口中，右键点击 `app -> java` 下的 `com.ebookfrenzy.explicitintent` 包名，选择 `New -> Activity -> Empty Views Activity` 菜单选项，显示如图 55-3 所示的 `New Android Activity` 对话：

![image-JVREGK0P.jpg](img/image-JVREGK0P.jpeg)
图 55-3

在 `Activity Name` 和 `Title` 字段中输入 `SecondActivity`，将布局文件命名为 `activity_second`，并将 `Language` 菜单更改 `Java`。由于此 activity 在应用程序启动时不会启动（它将在点击按钮时由 `MainActivity` 通过 `intent` 启动），在点击 `Finish` 按钮之前，确保禁用了 `Launcher Activity` 选项。

## 55.4 为 SecondActivity 设计用户界面布局

第二个 activity 用户界面所需的元素是 `Plain Text EditText`、`TextView` 和 `Button` 视图。考虑到这些要求，将 `activity_second.xml` 布局加载到 `Layout Editor` 工具中并添加视图。

在设计过程中，注意 `button` 视图上的 `onClick` 属性已配置为调用名为 `returnText` 的方法，并且 `TextView` 和 `EditText` 视图分别分配了 ID `textView2` 和 `editText2`。完成后，布局应类似于图 55-4 所示。注意按钮上的文本（“Return Text”）已提取到名为 `return_text` 的字符串资源中。

布局完成后，点击 `Infer constraints` 工具栏按钮为布局添加必要的约束：

![image-DXI6YJQF.jpg](img/image-DXI6YJQF.jpeg)
图 55-4

## 55.5 检查应用程序清单文件文件

为了让 `MainActivity` 能够使用 `intent` 启动 `SecondActivity`，`AndroidManifest.xml` 文件中需要存在 `SecondActivity` 的条目。在 `Project` 工具窗口中（`app -> manifests`）找到该文件，双击将其加载到编辑器中，并验证 `Android Studio` 是否已自动添加了该 activity 的条目：

```xml
xmlns:tools="http://schemas.android.com/tools">

android:allowBackup="true"

android:dataExtractionRules="@xml/data_extraction_rules"

android:fullBackupContent="@xml/backup_rules"

android:icon="@mipmap/ic_launcher"

android:label="@string/app_name"

android:roundIcon="@mipmap/ic_launcher_round"

android:supportsRtl="true"

android:theme="@style/Theme.ExplicitIntent"

tools:targetApi="31">

android:name=".SecondActivity"

android:exported="false" />

android:name=".MainActivity"

android:exported="true">
```

第二个 activity 创建并列在清单文件中后现在是可以在 `MainActivity` 类中编写一些代码来发出 `intent` 了。

## 55.6 创建 Intent

`MainActivity` 的目标是在用户触摸“Send Text”按钮时创建并启动一个 `intent`。作为 intent 创建过程的一部分，用户在 `EditText` 视图中输入的查询字符串将以键值对的形式添加到 `intent` 对象中。当创建 `MainActivity` 的用户界面布局时，`button` 对象被配置为在用户“点击”时调用名为 `sendText()` 的方法。现在需要将此方法添加到 `MainActivity` 类 `MainActivity.java` 源文件中，如下：

```java
package com.ebookfrenzy.explicitintent;

.

.

import android.content.Intent;

.

.

public class MainActivity extends AppCompatActivity {

.

.
```



```java
public void sendText(View view) {

    Intent i = new Intent(this, SecondActivity.class);

    String myString = binding.editText1.getText().toString();

    i.putExtra("qString", myString);

    startActivity(i);

}

}
```

`sendText()` 方法的代码遵循“Android Intent 概述”中概述的技术。首先，创建一个新的 `Intent` 实例，并将当前 activity 和 `SecondActivity` 的类名作为参数传递。接下来，输入到 `EditText` 对象的文本以键值对的形式添加到 `intent` 对象中，并通过 `startActivity()` 传递 `intent`。

编译并运行应用程序，触摸“Send Text”按钮从屏幕右下角（位于 toolbar 上的返回按钮）启动 `SecondActivity`。

## 55.7 提取 Intent 数据

现在 `SecondActivity` 正从 `MainActivity` 启动，下一步是提取 `intent` 中包含的 `String` 值并将其赋值给 `SecondActivity` 用户界面中的 `TextView` 对象。这涉及在 `SecondActivity.java` 源文件的 `onCreate()` 方法中添加代码，并适配使用视图绑定：

```java
package com.ebookfrenzy.explicitintent;

.

.

import android.content.Intent;

import android.view.View;

import com.ebookfrenzy.explicitintent.databinding.ActivitySecondBinding;

public class SecondActivity extends AppCompatActivity {

    private ActivitySecondBinding binding;

    public void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);

        EdgeToEdge.enable(this);

        setContentView(R.layout.SecondActivity);

        binding = ActivitySecondBinding.inflate(getLayoutInflater());

        View view = binding.getRoot();

        setContentView(view);

        ViewCompat.setOnApplyWindowInsetsListener(binding.main, (v, insets) -> {

            Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());

            v.setPadding(systemBars.left, systemBars.top, systemBars.right,

            systemBars.bottom);

            return insets;

        });

        Bundle extras = getIntent().getExtras();

        if (extras == null) {

            return;

        }

        String qString = extras.getString("qString");

        binding.textView2.setText(qString);

    }

}
```

在模拟器或物理 Android 设备上编译并运行应用程序。在触摸“Send Text”按钮之前，在 `MainActivity` 的文本框中输入一些文本。现在消息应该出现在 `SecondActivity` 用户界面的 `TextView` 组件上。

## 55.8 作为子 Activity 启动 SecondActivity

为了让 `SecondActivity` 能够向 `MainActivity` 返回数据，`SecondActivity` 必须作为 `MainActivity` 的子 activity 启动。这意味着我们需要调用 `registerForActivityResult()` 并声明在 `SecondActivity` 返回时调用的回调处理器。此回调将提取 `SecondActivity` 返回的数据并显示在 `textView1` 上。

`registerForActivityResult()` 返回 `ActivityResultLauncher` 实例，可以在 `sendText()` 中调用它可以启动 `intent`。编辑 `MainActivity.java` 文件如下：

```java
.

.

import android.app.Activity;

import androidx.activity.result.ActivityResult;

import androidx.activity.result.ActivityResultCallback;

import androidx.activity.result.ActivityResultLauncher;

import androidx.activity.result.contract.ActivityResultContracts;

.

.

public class MainActivity extends AppCompatActivity {

.

.

    ActivityResultLauncher startForResult = registerForActivityResult(
```

```java
        new ActivityResultContracts.StartActivityForResult(),

        new ActivityResultCallback() {

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
```

## 55.9 从子 Activity 返回数据

`SecondActivity` 现在作为 `MainActivity` 的子 Activity，而 `MainActivity` 也相应地被修改以处理从 `SecondActivity` 返回的数据。现在剩下的的是修改 `SecondActivity.java` 以实现 `finish()` 方法并添加一个名为 `returnText()` 的方法。当 Activity 退出时（例如当用户选择设备上的返回键时），会触发 `finish()` 方法：

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

`finish()` 方法创建一个新的 `Intent`，将返回数据作为键值对添加，然后调用 `setResult()` 方法，传递结果代码和 `Intent` 对象。`returnText()` 方法则调用了 `finish()` 方法。

打开 `activity_second.xml` 文件，选择按钮控件，并配置 `onClick` 属性以调用 `returnText()` 方法。

## 55.10 测试应用程序

编译并运行应用程序，在 `MainActivity` 上的文本字段中输入问题，然后点击“Send Text”按钮。当 `SecondActivity` 出现时，在 `EditText` 视图中输入文本，并使用返回键或“Return Text”按钮返回 `MainActivity`，此时响应应该出现在文本视图对象中。

## 55.11 总结

在上一章涵盖了 `Intent` 的基础知识后，本章的目标是在 Android Studio 中创建一个应用程序项目，设计用于演示显式 Intent（explicit intents）的使用，以及父 Activity 与子 Activity 之间数据传输的概念。

下一章将使用一个示例来演示隐式 Intent（implicit intents）的运行。

# 56. Android 隐式 Intent – 实例演示

本章将在 Android Studio 中创建一个示例应用程序，旨在演示隐式 Intent 的实际实现。目标是创建并发送一个 `Intent`，请求加载并向用户显示特定特定页的内容。由于示例应用程序本身不包含能够执行此项任务的 Activity，因此将发布一个隐式 `Intent`，以便调用 Android Intent 解析算法来识别并启动来自另一个应用程序的合适 Activity。这很可能是 Android 操作系统自带的 Chrome 浏览器的某个 Activity。

在成功启动内置浏览器后，将创建一个能够显示网页的 Activity 新项目。该项目将被安装到设备或模拟器上，以演示隐式 Intent 和链接验证。

## 56.1 创建 Android Studio 隐式 Intent 示例项目

从欢迎界面选择 New Project（新建项目）选项，在出现的新项目对话框中，在点击 Next（下一步）按钮之前选择 Empty Views Activity 模板。

在 `Name`（名称）字段中输入 `ImplicitIntent` 并指定 `com.ebookfrenzy.implicitintent` 为包名。由于此示例将使用仅适用于最新 Android 版本中的功能，在点击 Finish（完成）按钮之前，将 Minimum API level 设置更改为 `API 31: Android 12.0 (S)`，并将语言菜单改为 `Java`。

## 56.2 设计用户界面

`MainActivity` 类的用户界面非常简单，仅由一个 `ConstraintLayout` 和两个 `Button` 对象组成。在 Project 工具窗口中，找到 `app -> res -> layout -> activity_main.xml` 文件并双击它将其加载到 Layout Editor 工具工具中。

删除默认的 `TextView`，并在启用 Autoconnect（自动连接）模式的情况下，在布局中放置 `Button` 控件，使其显示如下所示：

![image-D1A236UH.jpg](img/image-D1A236UH.jpeg)

图 56-1

将按钮上的文本设置为 Show Web Page（显示网页）和 Enable Links（启用链接），并将文本提取到字符串资源中。

选择每个 `Button` 并使用 Attributes 工具窗口配置 `onClick` 属性，分别调用名为 `showWebPage` 和 `enableLink` 方法。

## 56.3 创建隐式 Intent

如上所述，隐式 Intent 将名为 `showWebPage()` 的方法内部创建并发布，该方法反过来需要在 `MainActivity` 类中实现，其代码位于 `MainActivity.java` 源文件中。在 Project 工具窗口中找到该文件并双击将其加载到编辑面板中。加载后，修改代码添加 `showWebPage()` 和 `enableLink()` 方法以及一些必要的导入：

```java
package com.ebookfrenzy.implicitintent;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

import android.net.Uri;

import android.content.Intent;

import android.view.View;

public class MainActivity extends AppCompatActivity {

// ...

    public void showWebPage(View view) {

        Intent intent = new Intent(Intent.ACTION_VIEW,

                Uri.parse("https://www.ebookfrenzy.com"));

        startActivity(intent);

    }

    public void enableLink(View view) {

    }

}
```

`showWebPage()` 方法执行的任务非常简单。首先，创建一个新的 `Intent` 对象。然而，代码没有指定 `Intent` 的类名，而是使用 `ACTION_VIEW` 指定了 `Intent` 的性质（向用户显示内容）。该 `Intent` 对象还包含一个要显示的 `URI`。这告诉 Android 解析系统该 Activity 请求显示网页。然后，通过调用 `startActivity()` 发布该 `Intent`。

在模拟器或 Android 设备上编译并运行应用程序，运行后，点击 Show Web Page 按钮。点击后，应该出现浏览器视图并加载指定的网页。隐式 Intent 现在已成功执行。

## 56.4 添加第二个匹配的 Activity

本章的剩余部分将演示设备上安装了多个匹配隐式 Intent Activity 的效果。将创建并安装第二个应用程序来实现这一点。首先，在 Android Studio 中创建一个新项目，将应用程序设置为 `MyWebView`，并使用与本章早些时候创建 `ImplicitIntent` 项目时相同的 SDK 配置选项，再次选择 Empty Views Activity。

如果你有一个托管 Digital Asset Links 文件的网站并想尝试自动验证，在指定包名时使用你的网站 URL。例如，如果你的网站位于 `www.mycompany.com`，则包名需要设置为：

`com.mycompany.mywebview`

如果你没有网站或不计划使用自动验证，请使用以下包名：

`com.ebookfrenzy.mywebview`

点击 Finish 创建项目，然后按照第 12.8 节所述将项目转换为使用 view bindings。

## 56.5 向 UI 添加 Web View

新 `MyWebView` 项目包含的唯一 Activity 的用户界面将由 Android `WebView` 控件实例组成。在 Project 工具窗口中，找到 `activity_main.xml` 文件（该文件包含 Activity 的用户界面描述），并双击它将其加载到 Layout Editor 工具中。

在设计模式（Design mode）下使用布局编辑器（Layout Editor）工具，选择默认的 `TextView` 小部件并使用键盘删除键将其从布局中移除。

从调色板的小部件（Widgets）部分拖放 `WebView` 对象到现有的 `ConstraintLayout` 视图上，如图 56-2 所示：

![image-20YLFNFR.jpg](img/image-20YLFNFR.jpeg)

图 56-2

在继续之前，将 `WebView` 实例的 ID 更改为 `webView1`，并使用“推约束”（Infer constraints）按钮添加任何缺失的约束。

## 56.6 获取 Intent URL

当创建隐式 `intent` 对象以显示网络浏览器窗口时，网页 URL 将被封装在 `intent` 对象内部的 `Uri` 对象中。`MainActivity` 类中 `onCreate()` 方法的任务是从 `intent` 对象中提取此 `Uri`，将其转换为 URL 字符串并赋值给 `WebView` 对象。要实现此功能，请修改 `MainActivity.java` 文件，使其读取如下所示：

```java
package com.ebookfrenzy.mywebview;

.

.

import java.net.URL;

import android.net.Uri;

import android.content.Intent;

import android.webkit.WebView;

public class MainActivity extends AppCompatActivity {
```



`private ActivityMainBinding binding;`

`@Override`

`protected void onCreate(Bundle savedInstanceState) {`

`.`

`.`

`handleIntent();`

`}`

`private void handleIntent() {`

`Intent intent = getIntent();`

`Uri data = intent.getData();`

`URL url = null;`

`try {`

`url = new URL(data.getScheme(),`

`data.getHost(),`

`data.getPath());`

`} catch (Exception e) {`

`e.printStackTrace();`

`}`

`binding.webView1.loadUrl(url.toString());`

`}`

`}`

添加到`onCreate()`方法中的新代码执行了以下任务：

* 获取导致此活动启动的`intent`引用
* 从`intent`对象中提取`Uri`数据
* 将`Uri`数据转换为`URL`对象
* 将`URL`加载到网络视图中，在此过程中将`URL`转换为`String`

`MyWebView`项目的代码部分现在已完成。剩下的工作是修改清单（manifest）文件。

## 56.7 修改 MyWebView 项目清单文件

在进行测试之前，必须对`MyWebView`的清单文件进行一些更改。首先，该活动需要请求访问互联网的权限（因为将需要加载网页）。这通过向清单文件添加适当的权限行来实现：

此外，检查`MyWebView`项目的`AndroidManifest.xml`文件中`intent filter`（意图过滤器）部分的内容，将发现以下设置：

在上面的 XML 中，`android.intent.action.MAIN`条目表示该活动在没有数据输入的情况下启动时是应用程序的入口点——另一方面，`android.intent.category.LAUNCHER`指令则表示该活动应该列在设备的应用程序启动器屏幕上。

由于该活动不需要作为应用程序的入口点启动，在没有数据输入（在此情况下为`URL`）的情况下无法运行，且不需要在启动器中出现，因此该活动的清单文件中不需要`MAIN`或`LAUNCHER`指令。

然而，需要修改`MainActivity`的`intent filter`，以指示它能够处理 HTTP 数据方案的`ACTION_VIEW`意图动作。

Android 还要求处理不包含`MAIN`和`LAUNCHER`条目的隐式意图的活动必须在`intent filter`中包含所谓的`browsable`和`default`类别。因此，修改后的`intent filter`部分应如下所示，其中`is`被替换为您的网站地址或`www.ebookfrenzy.com`，取决于您创建`MyWebView`项目时使用的包名：

将这些要求汇总，得到了完整的`AndroidManifest.xml`文件：

```xml
<manifest package="com.ebookfrenzy.mywebview">
    android:allowBackup="true"
    android:icon="@mipmap/ic_launcher"
    android:label="@string/app_name"
    android:roundIcon="@mipmap/ic_launcher_round"
    android:supportsRtl="true"
    android:theme="@style/Theme.MyWebView">
    <activity
        android:name=".MainActivity"
        android:exported="true">
```

通过在`Project`工具窗口中双击文件名，将`AndroidManifest.xml`文件加载到清单编辑器中。一旦加载完成，修改 XML 以匹配上述更改，记得输入正确的网站 URL。

对清单文件进行适当的修改后，新活动已准备好安装到设备上。

## 56.8 在设备上安装 MyWebView 包

在`MyWebView`主活动可以作为隐式意图的接收者之前，必须先将其安装到设备上。这通过正常方式运行应用程序来实现。由于清单文件不包含`android.intent.action.MAIN`和`android.intent.category.LAUNCHER`设置，必须指示 Android Studio 安装但不启动应用。要配置此行为，从工具栏上选择`app -> Edit configurations…`菜单，如图 56-3 所示：

![image-9TQMMOYZ.jpg](img/image-9TQMMOYZ.jpeg)

图 56-3

在`Run/Debug Configurations`对话框中，将`Launch`选项设置为`Nothing`，然后点击`Apply`：

![image-3UM0BL7.jpg](img/image-3UM0BL7.jpeg)

图 56-4

配置好此设置后，正常运行应用。注意该应用已安装但尚未启动。

## 56.9 测试应用程序

在`MyWebView`应用安装后，重新运行 ImplicitIntent 并点击`Show Web Page`按钮。注意网页仍然加载到 Chrome 浏览器中而不是主活动。这是因为 MyWebView 活动尚未经过验证或启用。

## 56.10 手动启用链接

在`enableLink()`方法中，我们需要创建并启动一个`intent`以显示该应用的打开默认设置界面。将`MainActivity.java`文件加载到代码编辑器中，并修改`enableLink()`方法使其读取如下所示，请确保替换为`com.ebookfrenzy`或您自己的域名：

```java
.
.
import android.provider.Settings;
...
public void enableLink(View view) {
    Intent intent = new Intent(Settings.ACTION_APP_OPEN_BY_DEFAULT_SETTINGS,
    Uri.parse("package:.mywebview"));
    startActivity(intent);
}
```

重新运行 ImplicitIntent 并点击`Enable Link`显示 MyWebView 应用打开默认设置界面：

![image-26YQF5T33.jpg](img/image-26YQF5T33.jpeg)

图 56-5

点击`Add Link`按钮（标记为 A），启用 URL 旁边的选框，然后点击`Add`按钮：

![image-BSZMR9AM.jpg](img/image-BSZMR9AM.jpeg)

图 56-6

在确认链接已被支持之前，点击返回箭头（图 56-5 中的标记 B）返回 ImplicitIntent 应用。点击 Open Web Page 现在应将网页加载到 MyWebView 应用中而不是 Chrome 浏览器：

![image-YDUS94GT.jpg](img/image-YDUS94GT.jpeg)

图 56-7

接下来，在网络浏览器中打开以下页面：

`https://developers.google.com/digital-asset-links/tools/generator`

页面加载后，将您的网站 URL 输入到`Hosting site domain`字段，将`com..mywebview`作为`App package name`，并将您的 SHA-256 指纹输入到`App package fingerprint (`SHA256`)`字段中：

![image-C4ZPNMPH.jpg](img/image-C4ZPNMPH.jpeg)

图 56-8

点击`Generate`语句按钮显示生成的语句，并将其放置于名为`assetlinks.json`的文件中，位于 Web 服务器上名为`.well-known`的文件夹中。返回生成器页面并点击`Test`语句按钮，验证该文件是否有效且位置正确。

假设测试成功，我们就可以准备尝试应用链接了。请在您的设备或模拟器上重新安装`MyWebView`应用，并使用`Settings`应用导航到`MyWebView`的`Open by Default`页面。该页面应显示链接已通过验证：

![image-O537070U.jpg](img/image-O537070U.jpeg)

图 56-9

再次运行`ImplicitIntent`应用，点击`Open Web Page`按钮，并验证页面内容出现在`MyWebView`应用中而不是`Chrome`浏览器。

## 56.12 总结

隐式意图（Implicit intents）提供了一种机制，一个 activity 可以通过指定操作类型以及（可选的）执行该操作的数据来请求另一个 activity 的服务。然而，为了成为隐式意图的目标候选者，activity 必须配置为从传入的意图对象中提取适当的数据，并包含在配置正确的清单文件中，其中包括适当的权限和意图过滤器。包含目标 activity 的应用还必须通过 Digital Asset Links 文件进行验证，或由用户手动启用。

在本章中，创建了一个示例来演示隐式意图的发送、能够处理此类意图的示例 activity 的创建，以及链接验证过程。

## 57. Android 广播意图和广播接收器

意图（intents）除了提供了启动应用程序的机制外，还用于向系统中的其他组件广播系统范围的消息。这涉及广播意图（Broadcast Intents）和广播接收器（Broadcast Receivers）的实现，两者都是本章的主题。

## 57.1 广播意图概述

广播意图是通过调用`Activity`类的`sendBroadcast()`、`sendStickyBroadcast()`或`sendOrderedBroadcast()`方法广播的`Intent`对象（后者用于需要从广播结果的情况）。除了在应用程序组件之间提供消息传递和事件系统外，广播意图还被 Android 系统用于通知感兴趣的应用程序有关关键系统事件（例如外部电源或耳机的连接或断开）。

当创建广播意图时，它必须包含一个操作字符串、一个可选数据和一个类别字符串。与标准意图一样，数据是使用`intent`对象的`putExtra()`方法结合键值对添加到广播意图中的。可选的类别字符串可以通过调用`addCategory()`方法分配给广播意图。

标识广播事件的操作字符串必须是唯一的，并且通常使用应用程序的包名语法。例如，下面的代码段创建并发送了一个广播意图，包括一个唯一的操作字符串和数据：

```
Intent intent = new Intent();
intent.setAction("com.example.Broadcast");
intent.putExtra("MyData", 1000);
sendBroadcast(intent);
```

上面的代码将在 Android 3.0 之前的 Android 设备上成功启动相应的广播接收器。然而，在较新的 Android 版本中，广播接收器将无法接收该意图。这是因为 Android 3.0 引入了一种启动控制安全措施，防止停止的应用程序组件通过意图启动。如果应用程序刚刚安装且从未启动过，或者被用户使用设备上的应用程序管理器手动停止，则该应用程序被认为处于停止状态。然而，为了绕过这一点，可以在发送意图之前添加一个标记，以指示允许该意图启动停止应用程序的组件。该标记是`FLAG_INCLUDE_STOPPED_PACKAGES`，并将按照以下对之前代码段的适配方式使用：

```
Intent intent = new Intent();
intent.addFlags(Intent.FLAG_INCLUDE_STOPPED_PACKAGES);
intent.setAction("com.example.Broadcast");
intent.putExtra("MyData", 1000);
sendBroadcast(intent);
```

## 57.2 广播接收器概述

应用程序通过注册广播接收器来监听特定的广播意图。广播接收器通过扩展`AndroidBroadcastReceiver`类并重写`onReceive()`方法来实现。广播接收器可以在代码中（例如，在 activity 内部）或清单文件中注册。注册实现的一部分涉及创建意图过滤器（intent filters），以指示接收器需要监听的特定广播意图。这通过引用广播意图的操作字符串来实现。当检测到匹配的广播时，会调用广播接收器的`onReceive()`方法，此时该方法有 5 秒钟的时间来执行任何必要的任务然后返回。需要注意的是，广播接收器不需要持续运行。如果检测到匹配的意图，Android 运行时系统会在调用`onReceive()`方法之前自动启动广播接收器。

下面的代码概述了一个模板化的广播接收器子类：

```
package com.example.broadcastdetector;
import android.content.BroadcastReceiver;
import android.content.Context;
import android.content.Intent;
public class MyReceiver extends BroadcastReceiver {
    @Override
    public void onReceive(Context context, Intent intent) {
        // 在检测到广播时要执行的代码
    }
}
```

在清单文件中注册广播接收器时，必须为该接收器添加一个条目。下面的示例清单文件注册了上面的示例广播接收器：

```xml
<manifest package="com.example.broadcastdetector"
    android:versionCode="1"
    android:versionName="1.0"
    android:icon="@mipmap/ic_launcher"
    android:label="@string/app_name">
```

在 Android 8.0 之前的版本上运行时，与接收器相关的意图过滤器可以放置在清单文件的 receiver 元素中。对于 Android 8.0 或更高版本，必须在代码中使用`Activity`类的`registerReceiver()`方法结合适当配置的`IntentFilter`对象来注册接收器：

```
IntentFilter filter = new IntentFilter("com.example.Broadcast");
MyReceiver receiver = new MyReceiver();
registerReceiver(receiver, filter, RECEIVER_EXPORTED);
```

当代码中注册的广播接收器不再需要时，可以通过调用 activity 类的`unregisterReceiver()`方法进行注销，并将接收对象的引用作为参数。例如，下面的代码将注销上面的广播接收器：

```
unregisterReceiver(receiver);
```



请记住，某些系统广播意图只有当接收器在代码中注册而不是在清单文件中注册时才能被检测到。请在线查看 Android `Intent` 类文档获取系统广播意图及相应要求的详细概述：

[`developer.android.com/reference/android/content/Intent`](https://developer.android.com/reference/android/content/Intent)

## 57.3 从广播获取结果

当使用`sendBroadcast()`方法发送广播意图时，启动的无法从接收该广播的任何广播接收器获取结果。如果需要返回结果，则必须使用`sendOrderedBroadcast()`方法。当使用此方法发送广播意图时，它将按照顺序传递给每个已注册感兴趣的广播接收器。

`sendOrderedBroadcast()`方法接受多个参数，包括一个指向另一个广播接收器的引用（称为结果接收器），当所有其他广播接收器都处理完意图后将通知该接收器，以及一组数据引用，这些接收器可以将结果数据放入这些引用中。当所有广播接收器都获得了处理广播的机会后，结果接收器的`onReceive()`方法将被调用，并传入结果数据。

## 57.4 粘性广播意图

默认情况下，广播意图在发送并被感兴趣的广播接收器处理后就会消失。然而，广播意图可以被定义为“粘性”（sticky）。粘性意图及其包含的数据在执行完成后仍会留存在系统中。存储在粘性广播意图中的数据可以通过调用`registerReceiver()`方法的返回值获取，该方法使用通常的参数（广播接收器的引用和意图过滤器对象）。许多 Android 系统广播都是粘性的，一个典型的例子是与电池量状态相关的广播。

粘性广播可以通过调用`removeStickyBroadcast()`方法随时移除，该方法通过参数传递要移除的广播意图的引用。

## 57.5 广播意图示例

本章的剩余部分将通过实现一个基于 Android Studio 的广播意图运行示例。在第一个实例中，将创建一个简单的应用程序来发布一个自定义的广播意图。随后，将创建一个相应的广播接收器，以便在检测到广播时在 Android 设备的屏幕上显示消息。最后，将修改广播接收器以检测系统关于外部电源已从设备断开的通知。

## 57.6 创建示例应用程序

从欢迎界面选择`New Project`（新建项目）选项，在生成的新项目对话框中，点击`Next`（下一步）按钮之前选择`Empty Views Activity`模板。

在`Name`（名称）字段中输入`SendBroadcast`并指定`com.ebookfrenzy.sendbroadcast`为包名。在点击`Finish`（完成）按钮之前，将`Minimum API level`（最低 API 级别）设置改为`API 33: Android 13.0 (Tiramisu)`，并将`Language`（语言）菜单更改`Java`。

一旦新新项目，在 Project 工具窗口的`app -> res -> layout`下找到并加载`activity_main.xml`布局文件，并在 Design（设计）模式下使用 Layout Editor 工具，将`TextView`对象替换为`Button`视图，并设置`text`属性显示为“Send Broadcast”。一旦设置了文本值，按照通常步骤将字符串提取到名为`send_broadcast`的资源。

在布局中仍选中按钮的状态下，在 Attributes（属性）面板中找到`onClick`属性，并配置为调用名为`broadcastIntent`的方法。

## 57.7 创建并发送广播意图

在创建了`SendBroadcast`应用程序的框架后，现在是时候实现发送广播意图的代码了。这涉及实现之前指定的作为用户界面`Button`视图的`onClick`目标的`broadcastIntent()`方法。找到`MainActivity.java`文件并双击它，修改它以添加创建和发送广播意图的代码。修改后，该类的源代码应如下所示：

```java
package com.ebookfrenzy.sendbroadcast;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

import android.content.Intent;

import android.view.View;

public class MainActivity extends AppCompatActivity {

.

.

public void broadcastIntent(View view)

{

Intent intent = new Intent();

intent.setAction("com.ebookfrenzy.sendbroadcast");

intent.addFlags(Intent.FLAG_INCLUDE_STOPPED_PACKAGES);

sendBroadcast(intent);

}

}
```

注意在此实例中，意图的 action 字符串为`com.ebookfrenzy.sendbroadcast`。当在本章后续章节创建广播接收器类时，意图过滤器声明必须匹配此 action 字符串。

发送广播意图的应用程序创建此结束。剩下的就是构建一个匹配的广播接收器。

## 57.8 创建广播接收器

要创建广播接收器，需要创建一个新类，该类继承自`BroadcastReceiver`超类。在 Project 工具窗口中，导航到`app -> java`并右键点击包名。从生成的菜单中选择`New -> Other -> Broadcast Receiver`菜单选项，将类命名为`MyReceiver`，并确保选择了`Exported`和`Enabled`选项。这些设置允许 Android 系统在需要时启动接收器，并确保该类可以接收来自其他应用程序的消息。配置好类后，点击`Finish`。

一旦创建，Android Studio 将将新的`MyReceiver.java`类文件加载到编辑器中，其内容应如下：

```java
package com.ebookfrenzy.sendbroadcast;

import android.content.BroadcastReceiver;

import android.content.Context;

import android.content.Intent;

public class MyReceiver extends BroadcastReceiver {

@Override

public void onReceive(Context context, Intent intent) {

// TODO: 当 BroadcastReceiver 接收到 Intent 广播时调用此方法。

throw new UnsupportedOperationException("Not yet implemented");

}

}
```

如代码所示，Android Studio 为新类生成了模板以及`onReceive()`方法的存根。现在需要对类进行一些更改以实现所需的行为。在`MyReceiver.java`文件中，修改代码使其如下：

```java
package com.ebookfrenzy.sendbroadcast;

import android.content.BroadcastReceiver;

import android.content.Context;

import android.content.Intent;

import android.widget.Toast;

public class MyReceiver extends BroadcastReceiver {

@Override

public void onReceive(Context context, Intent intent) {

// TODO: 当 BroadcastReceiver 接收到 Intent 广播时调用此方法。

throw new UnsupportedOperationException("Not yet implemented");

Toast.makeText(context, "Broadcast Detected.",

Toast.LENGTH_LONG).show();

}

}
```

广播接收器的代码现在完成了。

## 57.9 注册广播接收器

项目需要公开广播接收器的存在，并包含一个意图过滤器来指定接收器感兴趣的广播意图。当在上节中创建`BroadcastReceiver`类时，Android Studio 已自动在文件中文件中了一个元素。因此，剩下的是在`MainActivity.java`文件中添加代码以创建意图过滤器并注册接收器：

```java
package com.ebookfrenzy.sendbroadcast;

.

.

import android.content.BroadcastReceiver;

import android.content.IntentFilter;

.

.

public class MainActivity extends AppCompatActivity {

BroadcastReceiver receiver;

@Override

protected void onCreate(Bundle savedInstanceState) {

super.onCreate(savedInstanceState);

.

.

configureReceiver();

}

private void configureReceiver() {

IntentFilter filter = new IntentFilter();

filter.addAction("com.ebookfrenzy.sendbroadcast");

receiver = new MyReceiver();

registerReceiver(receiver, filter);

}

.

.

}
```

在不再需要时注销广播接收器也是重要的：

```java
@Override

protected void onDestroy() {

super.onDestroy();

unregisterReceiver(receiver);

}
```

## 57.10 测试广播示例

要测试广播发送者和接收器，请在设备或 AVD 上运行`SendBroadcast`应用并等待它显示在屏幕上。运行后，点击按钮，此时应该弹出一个显示“Broadcast Intent Detected.”的吐司消息（toast），持续几秒后消失。

## 57.11 监听系统广播

此示例的最后一个阶段是修改广播接收器的意图过滤器（intent filter），以监听当外部电源从设备断开时广播的系统意图。该操作是`android.intent.action.ACTION_POWER_DISCONNECTED`。修改`MainActivity.java`文件中的`configureReceiver()`方法以添加此额外的过滤器：

```java
private void configureReceiver() {

    IntentFilter filter = new IntentFilter();

    filter.addAction("com.ebookfrenzy.sendbroadcast");

    filter.addAction(

    "android.intent.action.ACTION_POWER_DISCONNECTED");

    receiver = new MyReceiver();

    registerReceiver(receiver, filter);

}
```

由于`MyReceiver.java`文件中的`onReceive()`方法现在将监听两种类型的广播意图，因此值得修改代码，使当前意图的动作字符串也显示在吐司消息中。此字符串可以通过对作为`onReceive()`方法参数传递的`intent`对象调用`getAction()`方法获取：

```java
public void onReceive(Context context, Intent intent) {

    String message = "Broadcast intent detected "

    + intent.getAction();

    Toast.makeText(context, message,

    Toast.LENGTH_LONG).show();

}
```



重新安装修改后的`SendBroadcast`包来测试接收器。现在点击`SendBroadcast`中的按钮应该产生一个包含自定义动作字符串的新消息：

```
Broadcast intent detected com.ebookfrenzy.sendbroadcast
```

接下来，移除当前为 Android 设备供电的 USB 连接器，此时接收器应该在吐司消息中报告以下内容（在竖屏模式的设备上消息可能会被截断）。如果应用在模拟器上运行，请显示扩展控制面板，选择 Battery 选项并将 Charger 连接设置更改为 None。

```
Broadcast intent detected android.intent.action.ACTION_POWER_DISCONNECTED
```

为了避免每当设备断开电源时都出现此消息，请启动 Settings 应用并选择 Apps 选项。从结果列表中选择`SendBroadcast`应用并点击 Uninstall 按钮。

## 57.12 总结

广播语义（Broadcast intents）是一种机制，可以发布意图供 Android 系统上的多个组件消费。通过注册广播接收器（Broadcast Receiver）检测广播，接收器被配置为监听匹配特定动作字符串的意图。通常情况下，广播接收器保持休眠状态，直到检测到匹配的意图时被系统唤醒。Android 系统还使用广播意图发布事件通知，例如低电量警告或外部电源的连接或断开。

除了提供广播语义和接收器的概述外，本章还有一个发送广播意图并实现广播接收器以监听自定义和系统广播意图的示例。

## 58. Android 本地绑定服务——实例演示

如上一章所述，绑定服务（Bound services）提供了一种实现 Android 服务与一个或多个客户端组件之间通信的机制。本章在“Android 服务概览”中提供的绑定服务概述的基础上，开始一个本地绑定服务的示例实现。

## 58.1 理解绑定服务

提供绑定服务允许应用程序在后台执行任务。多个客户端组件可以绑定到绑定服务，并在绑定后，使用各种机制与该服务交互。

绑定服务是作为`Android Service`类的子类创建的，并且至少实现`onBind()`方法。客户端组件通过调用`bindService()`方法绑定到服务。对绑定服务的首次绑定请求将导致调用该服务的`onBind()`方法（随后的绑定请求不会触发`onBind()`调用）。想要绑定到服务的客户端还必须实现一个`ServiceConnection`子类，该子类包含`onServiceConnected()`和`onServiceDisconnected()`方法，这些方法分别在客户端-服务器连接建立或断开后被调用。在`onServiceConnected()`方法的情况下，将传递一个`IBinder`对象，该对象包含了客户端与服务交互所需的全部信息。

## 58.2 绑定服务交互选项

存在两种实现客户端组件与绑定服务之间交互的推荐机制。假设绑定服务是本地的，且与客户端组件属于同一个应用程序（换句话说，它在同一个进程中运行，并且对其他应用程序中的组件不可用）。在这种情况下，推荐的方法是创建一个`Binder`类的子类并扩展它以为服务提供接口。随后由`onBind()`方法返回该`Binder`对象的实例，并供客户端组件用于直接访问服务中持有的方法和数据。

当绑定服务不是应用程序本地的时（换句话说，它在与客户端组件不同的进程中运行），最佳交互方式是使用`Messenger/Handler`实现。在本章的剩余部分中，将创建一个示例来演示创建、启动和与本地私有绑定服务交互的步骤。

## 58.3 本地绑定服务示例

在本章剩余部分创建的示例应用将由单个 activity 和一个绑定服务组成。绑定服务的目的是从系统获取当前时间，并将该信息返回给 activity，由那里将其显示给用户。绑定服务将是本地的，且与 activity 属于同一个应用程序。

在欢迎界面选择 New Project 选项，并在新项目对话框中选择 Empty Views Activity 模板，然后点击 Next 按钮。

在 Name 字段中输入`LocalBound`并指定包名为`com.ebookfrenzy.localbound`。在点击 Finish 按钮之前，将 Minimum API level 设置为`API 26: Android 8.0 (Oreo)`并将 Language 菜单更改为 Java。使用第 12.8 节 Migrating a Project to View Binding 中的步骤将项目迁移到 view binding。

项目创建完成后，下一步是添加一个新类作为绑定服务。

## 58.4 为项目添加绑定服务

要向项目添加新类，请右键点击 Project 工具窗口中的包名（位于 app -> java -> com.ebookfrenzy.localbound），选择 New -> Service -> Service 菜单。指定`BoundService`为类名，并确保 Exported 和 Enabled 选项都已选中，然后点击 Finish 创建类。Android Studio 将`BoundService.java`文件加载到编辑器中，其内容如下：

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
        // TODO: Return the communication channel to the service.
        throw new UnsupportedOperationException("Not yet implemented");
    }
}
```

## 58.5 实现 Binder

如前所述，本地绑定服务可以通过向客户端传递配置适当的`Binder`对象来与绑定客户端进行通信。这是通过在绑定服务类内部创建一个`Binder`子类，并通过添加一个或多个客户端可以调用的新方法来扩展它来实现。这通常涉及实现一个返回绑定服务实例引的方法。有了该实例的引用，客户端就可以直接访问绑定服务中的数据并调用其中的方法。

对于此示例，需要对在前一节中创建的模板类`BoundService`进行一些更改。首先，需要声明一个`Binder`子类。该类将包含一个名为`getService()`的方法，该方法将返回当前服务对象实例的引用（由`this`关键字表示）。考虑到这些要求，编辑`BoundService.java`文件并进行如下修改：

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
        // TODO: Return the communication channel to the service.
        throw new UnsupportedOperationException("Not yet implemented");
    }

    public class MyLocalBinder extends Binder {
        BoundService getService() {
            return BoundService.this;
        }
    }
}
```

对类进行更改后，值得花一点时间回顾一下这里执行的步骤。首先，声明了一个新的`Binder`子类（命名为`MyLocalBinder`）。该类包含一个方法，用于返回`BoundService`类当前实例的引用。创建`MyLocalBinder`类的新实例并将其赋值给`myBinder``IBinder`引用（由于`Binder`是`IBinder`的子类，因此此赋值不存在类型不匹配）。

接下来，需要修改`onBind()`方法以返回`myBinder`对象的引用，并实现一个新的公共方法，以便在被任何绑定到服务的客户端调用时返回当前时间：

```java
package com.ebookfrenzy.localbound;

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
                new SimpleDateFormat("HH:mm:ss MM/dd/yyyy", Locale.US);
        return (dateformat.format(new Date()));
    }

    public class MyLocalBinder extends Binder {
        BoundService getService() {
            return BoundService.this;
        }
    }
}
```

此时，绑定服务已经完成，并已准备好添加到项目清单文件中。在 Project 工具窗口中找到并双击`LocalBound`项目的`AndroidManifest.xml`文件，一旦加载到 Manifest 编辑器，请验证 Android Studio 是否已添加如下服务条目：

```xml
<service package="com.ebookfrenzy.localbound.localbound"
    android:allowBackup="true"
    android:icon="@mipmap/ic_launcher"
    android:label="@string/app_name"
    android:theme="@style/AppTheme"
    android:name=".BoundService"
    android:enabled="true"
    android:exported="true" >
<activity android:name=".MainActivity">
```

下一阶段是在 activity 内部编写代码以绑定到服务并调用`getCurrentTime()`方法。

## 58.6 将客户端绑定到服务

在本次教程中，客户端是运行应用程序的`MainActivity`实例。如前所述，要成功绑定到服务并接收由服务的`onBind()`方法返回的`IBinder`对象，有必要创建一个`ServiceConnection`子类并实现`onServiceConnected()`和`onServiceDisconnected()`回调方法。编辑`MainActivity.java`文件并进行如下修改：

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

    ...

    final private ServiceConnection myConnection = new ServiceConnection() {
        @Override
        public void onServiceConnected(ComponentName className, IBinder service) {
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

当客户端成功绑定到服务时，将调用`onServiceConnected()`方法。该方法作为参数传递了由`onBind()`方法返回的`IBinder`对象。该参数被强制转换为`MyLocalBinder`类型。通过调用 binder 的`getService()`方法获取`myService`，并将`isBound`设置为`true`。

当连接断开时，调用`onServiceDisconnected()`方法并将`isBound`设置为`false`。

建立连接后，下一步是修改 activity 以绑定到服务。这涉及到在`onCreate()`方法中创建`intent`并调用`bindService()`方法：

```java
@Override
public void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);

    ...

    Intent intent = new Intent(this, BoundService.class);
    bindService(intent, myConnection, Context.BIND_AUTO_CREATE);
}
```

## 58.7 完成示例

最后是添加调用`getCurrentTime()`方法并向用户显示结果的机制。按照惯例，Android Studio 已为 activity 创建一个模板`activity_main.xml`文件，其中包含一个`TextView`。将此文件加载到布局编辑器中，使用设计模式选择`TextView`组件并将 ID 更改为`myTextView`。在`TextView`下方添加`Button`视图并将按钮文本改为“Show Time”，将其提取为名为`show_time`的字符串资源。完成这些更改后，布局应如图 58-1 所示。如果缺少任何约束，点击布局编辑器工具栏上的 Infer Constraints（推断约束）按钮。

![image-DLB7PB.jpg](img/image-DLB7PB.jpeg)
图 58-1

完成用户界面设计，选择按钮并配置`onClick`属性以调用`showTime`方法。

最后，编辑`MainActivity.java`文件代码实现`showTime()`方法。该方法调用服务的`getCurrentTime()`方法（由于`onServiceConnected()`方法，现在可以通过`myService`引用从 activity 内部调用），并将结果字符串赋值给`TextView`：

```java
package com.ebookfrenzy.localbound;

...

import android.view.View;
import android.widget.TextView;
import com.ebookfrenzy.localbound.BoundService.MyLocalBinder;
```



`public class MainActivity extends AppCompatActivity {`

```
public class MainActivity extends AppCompatActivity {

    BoundService myService;

    boolean isBound = false;

    public void showTime(View view) {

        String currentTime = myService.getCurrentTime();

        TextView myTextView = findViewById(R.id.myTextView);

        myTextView.setText(currentTime);

    }

    ...

}
```

## 58.8 测试应用程序

代码更改完成后，对应用程序进行测试运行。一旦界面可见，点击按钮并注意文本视图将更改为显示当前的日期和时间。该示例已成功启动并绑定到一个服务，然后调用了该服务的方法来执行任务，并将结果返回给 activity。

## 58.9 总结

当绑定的服务是本地的且对某个应用程序私有时，该应用程序中的组件可以在不诉助于进程间通信（IPC）的情况下与服务进行交互。通俗来说，服务的 `onBind()` 方法返回一个 `IBinder` 对象，该对象包含一个指向运行中的服务实例的引用。客户端组件实现一个 `ServiceConnection` 子类，其中包含回调方法，这些方法在服务连接和断开连接时会被调用。前一个方法将接收由 `onBind()` 方法返回的 `IBinder` 对象，从而允许调用服务中的公共方法。

在涵盖了本地绑定服务的实现后，下一章将重点关注使用 IPC 与远程绑定服务进行交互。

## 59 Android 远程绑定服务 – 实例示例

在专门用于 Android 服务的最后一章，将开发一个示例应用程序，以演示使用 `messenger` 和 `handler` 配置来促进客户端与远程绑定服务之间的交互。

## 59.1 客户端到远程服务的通信

正如上一章概述，客户端与本地服务之间的交互可以通过向客户端返回一个包含服务对象引用的 `IBinder` 对象来实现。然而，在远程服务的情况中，这种方法行不通，因为远程服务运行在不同的进程中，因此无法从客户端直接访问。

在远程服务的情况下，必须创建一个 `Messenger` 和 `Handler` 配置，这允许消息跨越客户端和服务器之间的进程边界进行传递。

具体而言，服务会创建一个 `Handler` 实例，该实例会在接收到来自客户端的消息时被调用。在初始化方面，由 `Handler` 负责创建一个 `Messenger` 对象，而该对象反过来创建一个 `IBinder` 对象，并在 `onBind()` 方法中将其返回给客户端。客户端使用此 `IBinder` 对象创建 `Messenger` 对象的实例，随后向服务处理器（handler）发送消息。每当客户端发送一条消息时，处理器的 `handleMessage()` 方法就会被调用，并传递消息对象。

本章创建的示例将包含一个运行在单独进程中的 activity 和一个绑定服务。`Messenger/Handler` 机制将向服务发送一个字符串，该字符串将显示 `Logcat` 输出中。

## 59.2 创建示例应用程序

从欢迎界面选择 `New Project` 选项，在生成的新项目对话框中，点击 `Next` 按钮之前选择 `Empty Views Activity` 模板。

在 `Name` 字段中输入 `RemoteBound`，并指定 `com.ebookfrenzy.remotebound` 为包名。在点击 `Finish` 按钮之前，将 `Minimum API level` 设置更改为 `API 26: Android 8.0 (Oreo)`，并将语言菜单设置为 `Java`。

## 59.3 设计用户界面

在 Project 工具窗口中找到 `activity_main.xml` 文件并双击它将其加载到 Layout Editor 工具中。在 Design 模式下的 Layout Editor 工具中，右键点击默认的 `TextView` 实例，选择 `Convert view...` 菜单选项，从弹出的对话框中选择 `Button` 视图并点击 `Apply`。将按钮的文本属性更改为“Send Message”，并将字符串提取到命名为 `send_message` 的新资源中。

最后，配置 `onClick` 属性以调用名为 `sendMessage` 的方法。

## 59.4 实现远程绑定服务

为了实现此示例的远程绑定服务，在 Project 工具窗口中右键点击包名（位于 `app -> java` 下），并选择 `New -> Service -> Service` 菜单选项向项目添加新类。指定 `RemoteService` 为类名，并在点击 `Finish` 创建类之前，确保 `Exported` 和 `Enabled` 选项均已选中。

下一步是为新服务实现处理器类。这通过扩展 `Handler` 类并实现 `handleMessage()` 方法来实现。该方法会在接收到来自客户端的消息时被调用。它将接收一个 `Message` 对象作为参数，其中包含客户端需要传递给服务的任何数据。在本例中，这将是一个包含要显示给用户的字符串的 `Bundle` 对象。一旦实现完成，`RemoteService.java` 文件中的修改后的类应如下：

```java
package com.ebookfrenzy.remotebound;

import android.app.Service;
import android.content.Intent;
import android.os.IBinder;
import android.os.Bundle;
import android.os.Handler;
import android.os.Looper;
import android.os.Message;
import android.os.Messenger;
import android.util.Log;

public class RemoteService extends Service {

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

实现处理器后，服务代码方面剩下的任务是修改 `onBind()` 方法，使其返回一个包含 `Messenger` 对象的 `IBinder` 对象，该对象反过来包含对处理器的引用：

```java
final Messenger myMessenger = new Messenger(new IncomingHandler());

@Override
public IBinder onBind(Intent intent) {
return myMessenger.getBinder();
}
```

上述代码片段的第一行创建了处理器类的实例，并将其传递给新 `Messenger` 对象的构造函数。在 `onBind()` 方法中，调用 messenger 对象的 `getBinder()` 方法返回 messenger 的 `IBinder` 对象。

## 59.5 在清单文件中配置远程服务

为了准确描述客户端与远程服务之间的通信，有必要配置服务与应用程序的其他部分分离运行。这通过在清单文件的服务标签内添加 `android:process` 属性来实现。为了启动远程服务，还需要为服务提供意图过滤器（intent filter）。为了实施此更改，修改 `AndroidManifest.xml` 文件以添加所需的项：

```xml
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
    </activity>
</application>
```

## 59.6 启动并绑定到远程服务

与本地绑定服务一样，客户端组件需要实现 `ServiceConnection` 类的实例，并包含 `onServiceConnected()` 和 `onServiceDisconnected()` 方法。此外，与本地服务相同，`onServiceConnected()` 方法将接收由远程服务的 `onBind()` 方法返回的 `IBinder` 对象，该对象将用于向服务器处理程序发送消息。在示例中，客户端是 `MainActivity`，其代码位于 `MainActivity.java`。加载此文件并对其进行修改，以添加 `ServiceConnection` 类以及一个用于存储接收到的 `Messenger` 对象引用的变量，以及一个用于指示连接是否已建立的 `Boolean` 标志：

```java
package com.ebookfrenzy.remotoundound;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.os.IBinder;
import android.os.Message;
import android.os.Messenger;
import android.os.RemoteException;
import android.content.ComponentName;
import android.content.Context;
import android.content.Intent;
import android.content.ServiceConnection;
import android.view.View;

public class MainActivity extends AppCompatActivity {

    Messenger myService = null;
    boolean isBound;

    final private ServiceConnection myConnection = new ServiceConnection() {

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

接下来，必须添加一些代码来绑定到远程服务。这涉及到创建一个与清单文件中声明的服务的意图过滤器匹配的 `intent`（意），然后调用 `bindService()` 方法，并将 `intent` 和 `ServiceConnection` 实例引用作为参数。对于此示例，这些代码将在应用的 `onCreate()` 方法中实现：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);

    Intent intent = new Intent(getApplicationContext(), RemoteService.class);
    bindService(intent, myConnection, Context.BIND_AUTO_CREATE);
}
```

## 59.7 向远程服务发送消息

在测试应用程序之前，剩下的工作是在 `MainActivity` 类中实现 `sendMessage()` 方法，该方法被配置为当用户触摸界面上的按钮时调用。此方法需要检查服务是否已连接，创建一个包含服务器要显示的字符串的 `bundle`（包）对象，将其添加到 `Message` 对象中，并发送到服务器：

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



完成代码更改后，编译并运行应用程序。加载后，打开 Logcat 工具窗口并在过滤器字段中输入以下内容：

`package:mine tag:RemoteService`

在 Logcat 工具窗口保持可见的情况下，点击用户界面上的按钮，此时日志消息应该如下所示：

`Message = Message Received`

## 59.8 总结

要实现客户端与远程绑定服务之间的交互，应用必须实现一个处理程序/消息通信框架。该技术背的基本概念已在本章中涵盖，并包含了一个示例应用程序的实现，该程序旨在演示客户端与绑定服务之间的通信，每个服务运行在独立的进程中。

## 60. Java 线程、`Handler` 和执行器概述

线程是任何多任务操作系统的基石，可以被认为是运行在主进程中的微进程，其目的是在应用程序中实现至少并行执行路径的假。在本章中，我们将探索在 Android 应用开发中使用线程的重要性，并演示如何创建和管理它们。

## 60.1 应用主线程

当 Android 应用程序首次启动时，运行时系统会创建一个线程，所有应用程序组件默认将在该线程中运行。该线程通常被称为主线程。主线程的主要作用是在事件处理方面处理用户界面并与用户界面中的视图进行交互。应用程序内启动的任何额外组件默认也会运行在主线程上。

应用程序中任何使用主线程执行耗时任务的组件都会导致整个应用程序看起来像锁死了一，直到任务完成。这通常会导致操作系统向用户显示“应用程序未响应”的警告。显然，这对于任何应用程序来说都不是理想的行为。这可以通过简单地将要执行的任务在单独线程中启动来避免，允许主线程不受干扰地继续执行其他任务。

## 60.2 线程 `Handler`

显然，Android 开发的关键规则之一是永远不要在应用程序的主线程上执行耗时操作。第二个同样重要的规则是，在任何情况下，独立线程中的代码都绝不能直接更新用户界面的任何部分。

对用户界面的任何更改必须始终在主线程内部执行。这是因为 Android UI 工具包不是线程安全的。在多个线程中尝试处理非线程安全代码会导致间歇性问题。

如果线程中执行的代码需要与用户界面交互，它必须通过与主线程同步来实现。这通过在主线程中创建 `handler` 来实现，由它接收来自另一个线程的消息并更新用户界面。

## 60.3 线程示例

本章的剩余部分将通过一些简单的示例来对线程进行基础介绍。第一步将强调在独立于主线程执行耗时任务的重要性。

启动 Android Studio，从欢迎屏幕选择 New Project，在出现的新项目对话框中选择 Empty Activity 模板，然后点击 Next 按钮。

在 Name 字段输入 `ThreadExample`，并在 package name 中指定 `com.ebookfrenzy.threadexample`。在点击 Finish 按钮之前，将 Minimum API level 设置为 `API 26: Android 8.0 (Oreo)`并将 Language 菜单改为 Java。按照第 12.8 节的方法将项目转换为 view binding。

## 60.4 构建应用

将项目的 `activity_main.xml` 文件加载到 Layout Editor 工具中。选择默认的 `TextView` 组件，并在 Properties 工具窗口将视图的 ID 更改为 `myTextView`。

在用户界面上添加 `Button`，位于现有 `TextView` 对象正下方，如图 60-1 所示。添加按钮后，点击工具栏上的 Infer Constraints 按钮以添加缺失的约束。

将文本改为“Press Me”，并将字符串提取为名为 `press_me` 的资源。当按钮在布局中仍选中时，找到 `onClick` 属性并输入 `buttonClick` 作为方法名。

接下来，将 `MainActivity.java` 文件加载到编辑面板中，并为 `buttonClick()` 方法添加代码，该方法将在用户点击 `Button` 视图时被调用。由于这里的目标是演示在主线程上执行耗时任务的问题，代码将在 `TextView` 对象上显示不同的文本之前简单地暂停 20 秒：

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

完成代码更改后，在物理设备或模拟器上运行应用程序。一旦应用程序运行，点击按钮，此时应用程序看起来将是冻结了。例如，将无法第二次点击按钮，在某些情况下，操作系统将报告应用程序无响应，如图 60-2 所示。

![image-5SW205AA.jpg](img/image-5SW205AA.jpeg)

图 60-2

显然，`buttonClick()` 方法中任何需要时间完成的操作都需要在独立的线程中执行。

## 60.5 创建新线程

要创建一个新线程，需要将在该线程中执行的代码放置在 `Runnable` 实例的 `run()` 方法中。然后需要创建一个新的 `Thread` 对象，并将 `Runnable` 实例的引用传递给构造函数。最后，需要调用线程对象的 `start()` 方法来启动线程运行。因此，为了执行 `buttonClick()` 方法中的任务，需要进行以下更改：

```java
public void buttonClick(View view) {

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
        }

        binding.myTextView.setText("Button Pressed");

    };

    Thread myThread = new Thread(runnable);

    myThread.start();
}
```

事实上，如果需要，可以使用 Java Lambda 表达式来简化 `runnable` 的声明。进行此更改将导致以下声明：

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

Thread myThread = new Thread(runnable);

myThread.start();
```

现在运行应用程序时，点击按钮会导致延迟在新线程中执行，从而让主线程能够继续处理用户界面，包括对额外的按钮点击做出响应。事实上，每当点击按钮时，都会创建一个新线程，允许任务并发执行多次。

仔细检查 `buttonClick()` 方法的更新代码，会发现删除了更新 `TextView` 的代码。如之前所述，从主线程以外的线程内部更新用户界面元素违反了 Android 开发的一项关键规则。因此，为了更新用户界面，需要为线程实现一个 `Handler`。

## 60.6 实现线程 `Handler`

线程 `Handler` 在应用程序的主线程中实现，主要用于响应运行在应用程序进程内的其他线程发送的消息来更新用户界面。

Handlers 继承自 Android 的 `Handler` 类，可以通过指定在线程需要时执行的 `Runnable` 来使用，也可以通过重写 `Handler` 子类中的 `handleMessage()` 回调方法来使用，该方法会在线程向 handler 发送消息时被调用。

为了本示例，将实现一个 handler 以从之前创建的线程内部更新用户界面。将 `MainActivity.java` 文件加载到 Android Studio 编辑器中，并修改代码向活动中添加一个 `Handler` 实例：

```java
import android.os.Handler;
import android.os.Message;
import android.os.Looper;

public class MainActivity extends AppCompatActivity {

    Handler handler = new Handler(Looper.getMainLooper()) {

        @Override public void handleMessage(Message msg) {

            binding.myTextView.setText("Message Received");

        }

    };

}
```

上述代码更改声明了一个 handler 并在该 handler 中实现了 `handleMessage()` 回调，该回调会在线程向 handler 发送消息时被调用。在此例中，代码简单地在用户界面的 `TextView` 对象上显示字符串。

现在剩下的是修改 `buttonClick()` 方法中创建的线程，在延迟完成后向 handler 发送消息：

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

        // 注意：原文此处代码块逻辑略有混乱，保持原意

}
```

修正：原文提供的示例代码块逻辑似乎错乱（括号不匹配），但根据要求不翻译代码块。

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

        binding.myTextView.setText("Button Pressed");

    };

    Thread myThread = new Thread(runnable);

    myThread.start();

}
```

（注：原文中最后两段代码块存在逻辑错误，如括号未闭合，根据指令不翻译代码块。）

注意，唯一的更改是调用了 handler 的 `sendEmptyMessage()`。由于 handler 目前没有对收到的空消息内容做任何处理。编译并运行应用程序，一旦点击按钮，20 秒延迟后，新文本将出现在 `TextView` 对象上。

## 60.7 向 `Handler` 传递消息

虽然之前的示例触发了 `handleMessage()` 回调，但并没有利用消息对象向 handler 发送数据。在本教程的阶段，示例将进一步修改以在线程和 handler 之间传递数据。首先，`buttonClick()` 方法中的更新线程将获取字符串格式的系统日期时间，并将其信息存储在 `Bundle` 对象中。然后调用 handler 对象的 `obtainMessage()` 方法从消息池中获取消息对象。最后，在通过 handler 对象的 `sendMessage()` 方法发送之前，将 `bundle` 添加到消息对象中：

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

        bundle.putString("myKey", "Thread Completed");

        msg.setData(bundle);

        handler.sendMessage(msg);

    };

    Thread myThread = new Thread(runnable);

    myThread.start();

}
```

接下来，更新 handler 的 `handleMessage()` 方法，从消息中的 `bundle` 对象中提取日期时间字符串，并将其显示在 `TextView` 对象上：

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



最后，编译并运行应用程序，测试点击按钮现在是否会导致“Thread Completed”消息出现在`TextView`对象上。

## 60.8 Java Executor 并发

到本章为止，我们专门查看了直接创建和管理 Java 线程。虽然对于简单的多线程任务来说是可以接受的，但在处理涉及大量线程的复杂情况时，这被证明是不够的。例如，启动和停止线程涉及系统开销。因此，一个创建和销毁大量线程的应用程序面临着性能下降的风险。基础线程 API 也没有提供调度或重复执行任务的预构建选项，也没有提供从任务返回结果的选项。

通过使用 Java 并发框架（属于`java.util.concurrent`包）的`Executor`类，可以克服直接操作线程的缺点。该框架允许创建活动线程池，并管理任务如何分配给这些线程。这使得现有的线程可以被重用于其他任务，而无需不断创建新线程。

该框架还提供了额外功能，包括在任务完成后返回结果的能力（称为`Callable`任务）、检查线程状态，以及调度任务在超时后或按重复的时间间隔运行。

## 60.9 使用 Runnable 任务工作

探索此框架的第一步是修改`buttonClicked()`方法，使用并发框架`Executor`在单独线程中运行任务：

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

            Message msg = handler.obtainMessage();
            Bundle bundle = new Bundle();

            bundle.putString("myKey", "Button Pressed");

            msg.setData(bundle);
            handler.sendMessage(msg);
        }
    });

    executor.shutdown();
}
```

当执行上述代码时，超时将像以前一样在单独线程中执行。然而，对方法进行的更改需要一些解释。首先，从系统`Executors`实例获取`ExecutorService`实例的引用：

```java
ExecutorService executor = Executors.newSingleThreadExecutor();
```

在这种情况下，请求了一个只包含一个线程的池。也可以按如下方式请求具有指定数量线程的池：

```java
ExecutorService executor = Executors.newFixedThreadPool(10);
```

接下来，通过调用执行服务实例的`submit()`方法在线程上启动一个`Runnable`任务：

```java
executor.submit(new Runnable() {
    public void run() {
        long endTime = System.currentTimeMillis() + 20 * 1000;
    }
});
```

注意，上面的声明可以通过将其转换为 lambda 表达式来简化：

```java
executor.submit(() -> {
    long endTime = System.currentTimeMillis() + 20 * 1000;
});
```

从现在开始，该任务将一直运行直到完成。然而，一旦完成，执行服务将继续运行。如果你不再需要该服务，则应该将其关闭。

## 60.10 关闭 Executor 服务

`ExecutorService`提供了几种启动关闭的技术。若要通知服务在当前运行的任务完成后自动关闭，应如下所示调用`shutdown()`方法：

```java
executor.shutdown();
```

另一方面，调用`shutdownNow()`方法会停止服务上运行的所有任务，并取消待处理任务的处理：

```java
executor.shutdownNow();
```

## 60.11 使用 Callable 任务和 Futures 工作

如前所述，`ExecutorService`支持所谓的“Callable”任务，这些任务能够在任务完成后返回结果。运行在单独线程上的任务通常预计需要一些时间才能完成（否则它们可能就不需要在单独线程中运行了）。这引出了问题：如何将结果返回给启动任务的线程中的代码。这是通过使用`Future`值类型实现的，它代表在未来某个点提供的值。

当执行可调用任务时，它返回一个`Future`实例，应用程序随后可以使用该实例在任务完成后获取结果。要查看此效果，首先编辑`activity_main.xml`文件，添加一个标签为“Status”的额外按钮，并配置`onClick`属性以调用名为`statusClick`的方法：

![image-RXBBA957.jpg](img/image-RXBBA957.jpeg)

图 60-3

接下来，修改`buttonClick()`方法以执行配置为通过`Future`变量返回`String`值的`Callable`任务：

```java
import java.util.concurrent.Callable;
import java.util.concurrent.Future;

public class MainActivity extends AppCompatActivity {
    Future future;

    public void buttonClick(View view) {
        ExecutorService executor = Executors.newSingleThreadExecutor();

        future = executor.submit(new Callable() {
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

                Message msg = handler.obtainMessage();
                Bundle bundle = new Bundle();

                bundle.putString("myKey", "Button Pressed");

                msg.setData(bundle);
                handler.sendMessage(msg);

                return "Done";
            }
        });

        executor.shutdown();
    }
}
```

注意，通过导入`java.util.concurrent.Callable`包并声明`Future`变量，对任务启动的方式进行了一些更改：

```java
future = executor.submit(new Callable() {
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

        // ... 逻辑

        return "Result";
    }
});
```

*（注：此处原文示例代码在提供时似乎不完整，已根据上下文补全逻辑以对齐）*

## 60.12 处理 Future 结果

`buttonClick()`方法现在配置为执行一个`Callable`任务，并通过`Future`变量返回`String`值。应用程序现在需要知道任务何时完成以及结果可用。一种方法是调用`Future`的`get()`方法。由于该方法在执行失败或被中断时抛出异常，因此必须在`try/catch`语句中执行，如下所示：

```java
String result = null;

try {
    result = future.get();
} catch (ExecutionException | InterruptedException e) {
    e.printStackTrace();
}
```

遗憾的是，`get()`方法会阻塞当前线程直到任务完成，从而违背了最初在单独线程中运行任务的目的。另一种选择是为`get()`方法提供一个超时时间，超时后会将控制交回当前线程。例如，以下代码会导致`get()`调用在 3 秒后超时：

```java
result = future.get(3, TimeUnit.SECONDS);
```

更好的方案是调用`Future`实例的`isDone()`方法来检查线程状态，并在任务完成后调用`get()`方法。要实现这种行为，请在`MainActivity.java`文件中添加`statusClick()`方法：

```java
import java.util.concurrent.ExecutionException;
import java.util.concurrent.TimeUnit;
import java.util.concurrent.TimeoutException;

public void statusClick(View view) {
    if (future != null && future.isDone()) {
        String result = null;

        try {
            result = future.get(3, TimeUnit.SECONDS);
        } catch (ExecutionException | InterruptedException | TimeoutException e) {
            e.printStackTrace();
        }

        binding.myTextView.setText(result);
    } else {
        binding.myTextView.setText("Waiting");
    }
}
```

完成更改后，运行应用并点击“Press Me”按钮。在任务运行期间，点击`Status`按钮。只要任务仍在运行，`TextView`中就会显示“Waiting”消息。然而，一旦任务完成，`isDone()`方法将返回一个真值，`get()`方法将被调用，并且任务返回的字符串（“Task Complete”）将显示在`TextView`上。

## 60.13 调度任务

最后一个要涵盖的内容涉及使用`ExecutorService`来调度任务执行。这涉及到使用`ScheduledExecutorService`实例，在该实例上需要调用`schedule()`方法，并传递要执行的`Runnable`任务以及一个时间延迟时间。`schedule()`调用将返回一个`ScheduledFuture`实例，该实例可用于识别任务预计启动前的剩余时间。

例如，以下代码调度了一个任务在 30 秒后运行并访问了剩余的延迟时间：

```java
ScheduledExecutorService executor =
        Executors.newScheduledThreadPool(1);

Runnable task = () -> {
    // 在此处执行任务的代码
};

ScheduledFuture<?> future =
        executor.schedule(task, 30, TimeUnit.SECONDS);

long delayRemaining = future.getDelay(TimeUnit.SECONDS);
```

同样地，`ScheduledExecutorService`可用于在可选的初始延迟后以固定的间隔重复执行任务。例如，以下代码导致任务在初始 30 秒延迟后每隔 10 秒执行一次：

```java
executor.scheduleAtFixedRate(task, 30, 10, TimeUnit.SECONDS);
```

`scheduleAtFixedRate()`方法无论之前调度的任务是否完成，都会启动任务的下一个实例。若要指定任务执行结束与下一次执行开始之间的固定时间间隔，请使用`scheduleWithFixedDelay()`方法。在接下来的示例中，第一个任务调度在 0 秒延迟后调度，随后的每次执行都在上一个任务完成 10 秒后发生：

```java
executor.scheduleWithFixedDelay(task, 0, 10, TimeUnit.SECONDS);
```



## 60.14 总结

本章的目标是提供 Android 应用中线程的概述。当应用在进程中首次启动时，运行时系统创建一个主线程，所有随后启动的应用组件默认都在该线程中运行。主线程的主要是处理用户界面，因此在该线程中执行的任何耗时任务都会导致应用出现卡死的假象。因此，将可能需要时间完成的任务启动在单独的线程中是非常关重要的。

由于 Android 用户界面工具包不是线程安全的，不应在主线程之外的任何线程对用户界面进行更改。用户界面更改可以通过在主线程中创建一个`handler`来实现，从其他非主线程向其发送消息。

线程可以直接创建，也可以使用 Java 并发框架的执行器服务来创建。对于更复杂的线程需求，该框架提供了线程池的自动管理、任务结果的返回以及执行调度。

## 61. 在 Android 中请求运行时权限

在之前的几个章节中创建的许多示例项目中，已对`AndroidManifest.xml`文件进行了修改，以请求应用执行特定任务的权限。例如，在某些情况下，已请求了网络访问权限以允许应用下载和显示网页。到此为止的每种情况，只需将请求添加到清单文件中，应用即可从用户处获得执行指定任务的权限。

然而，对于某些权限，应用在 Android 6.0 或更高版本上运行时，需要额外的步骤才能运行。这些所谓的“危险”权限中的第一个将在下一章中遇到。然而，在到达那里之前，本章将概述在运行最新代 Android 系统运行时请求此类权限的涉及步骤。

## 61.1 理解普通权限和危险权限

Android 通过要求用户授予应用执行某些任务的权限来强制执行安全措施。在 Android 6 引入之前，在应用安装到设备上时总是会寻求权限。例如，图 61-1 显示了通过 Google Play 安装应用时寻求各种权限的典型屏幕。

![image-30A8RAR4.jpg](img/image-30A8RAR4.jpeg)

图 61-1

对于许多类型的权限，这种场景仍然适用于 Android 6.0 或更高版本上的应用。这些权限被称为**普通权限**，仍要求用户在安装点予以接受。第二类权限被称为**危险权限**，也必须以普通权限相同的方式在清单文件中声明，但在应用程序首次启动时也必须向用户请求。当发出此类请求时，它将以对话框的形式出现，如图 61-2 所示：

![image-QL53ANFX.jpg](img/image-QL53ANFX.jpeg)

图 61-2

属于危险类的权限完整列表包含在表 61-1 中：

| 权限组 | 权限 |
| :--- | :--- |
| 日历 | `READ_CALENDAR` `WRITE_CALENDAR` |
| 相机 | `CAMERA` |
| 联系人 | `READ_CONTACTS` `WRITE_CONTACTS` `GET_ACCOUNTS` |
| 位置 | `ACCESS_FINE_LOCATION` `ACCESS_COARSE_LOCATION` |
| 麦克风 | `RECORD_AUDIO` |
| 通知 | `POST_NOTIFICATIONS` |
| 电话 | `READ_PHONE_STATE` `CALL_PHONE` `READ_CALL_LOG` `WRITE_CALL_LOG` `ADD_VOICEMAIL` `PROCESS_OUTGOING_CALLS` |
| 传感器 | `BODY_SENSORS` |
| 短信 | `SEND_SMS` `RECEIVE_SMS` `READ_SMS` `RECEIVE_WAP_PUSH` `RECEIVE_MMS` |
| 存储 | `MANAGE_EXTERNAL_STORAGE` `READ_EXTERNAL_STORAGE` `WRITE_EXTERNAL_STORAGE` |

表 61-1

`MANAGE_EXTERNAL_STORAGE`权限允许应用访问设备外部存储上的所有文件，包括属于其他应用的文件。因此，只有当 Google 在审核过程中确认需要这种级别的访问时，权限才会为应用启用。为了在提交到 Google Play 商店之前测试应用，可以执行以下`adb`命令临时为测试设备上的应用启用访问：

`adb shell appops set --uid MANAGE_EXTERNAL_STORAGE allow`

可以通过以下方式关闭此模式：

`adb shell appops set --uid MANAGE_EXTERNAL_STORAGE default`

## 61.2 创建权限示例项目

在欢迎屏幕上选择 New Project（新建项目）选项，并在出现的项目对话框中选择 Empty Views Activity 模板，然后点击 Next 按钮。

在 Name 字段输入`PermissionDemo`，并指定`com.ebookfrenzy.permissiondemo`为包名。在点击 Finish 之前，将 Minimum API level 设置为 API 26: Android 8.0 (Oreo)，并将 Language 菜单设置为 Java。

## 61.3 检查权限

Android 支持库包含几种方法，用于在 Android 应用代码中寻求和管理危险权限。这些 API 调用无论应用运行的 Android 版本如何都可以安全地进行，但只有在 Android 6.0 或更高版本上执行时才会执行有意义的操作。

在 App 尝试使用需要批准危险权限的功能之前，无论之前是否已授予该权限，代码都必须检查该权限是否已授予。可以通过调用`ContextCompat`类的`checkSelfPermission()`方法来实现，并将当前 activity 的引用和请求的权限作为参数传递。该方法将检查权限是否之前已授予，并返回与`PackageManager.PERMISSION_GRANTED`或`PackageManager.PERMISSION_DENIED`匹配的整数值。

在示例项目的`MainActivity.java`文件中，修改代码以检查是否已授予 App 录音的权限：

```java
package com.ebookfrenzy.permissiondemoactivity;

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

        // ...

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

编辑`AndroidManifest.xml`文件（位于 Project 工具窗口的 app -> manifests 下），并添加一行代码来请求录音权限，如下：

```xml
package="com.ebookfrenzy.permissiondemoactivity" >

    android:allowBackup="true"

    android:icon="@mipmap/ic_launcher"

    android:label="@sxtring/app_name"

    android:supportsRtl="true"

    android:theme="@style/AppTheme" >

    android:name="android.intent.category.LAUNCHER" />
```

在设备或模拟器上运行该 App 并打开 Logcat 工具窗口。请注意，尽管权限已添加到 manifest 文件，但仍然出现了权限被拒绝的消息。这是因为 Android 要求除了在 manifest 文件中添加请求外，App 还必须在运行时请求危险权限。

## 61.4 在运行时请求权限

权限请求是通过调用`ActivityCompat`类的`requestPermissions()`方法发出的。当调用此方法时，权限请求将进行异步处理，并在任务完成后调用一个名为`onRequestPermissionsResult()`的方法。

`requestPermissions()`方法的参数包括当前 activity 的引用、所请求权限的标识符和一个请求代码。请求代码可以是任意整数值，并将用于标识是哪个请求触发了对`onRequestPermissionsResult()`方法的调用。修改`MainActivity.java`文件以声明请求代码，并在权限检查失败时请求录音权限：

```java
// ...

import androidx.core.app.ActivityCompat;

// ... ...

public class MainActivity extends AppCompatActivity {

    private static final String TAG = "PermissionDemo";

    private static final int RECORD_REQUEST_CODE = 101;

    // ...

    @Override

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

接下来，实现`onRequestPermissionsResult()`方法，使其内容如下：

```java
@Override

public void onRequestPermissionsResult(int requestCode,

        @NonNull String[] permissions, @NonNull int[] grantResults) {

    super.onRequestPermissionsResult(requestCode, permissions, grantResults);

    if (requestCode == RECORD_REQUEST_CODE) {

        if (grantResults.length == 0

                || grantResults[0] !=

                PackageManager.PERMISSION_GRANTED) {

            Log.i(TAG, "Permission has been denied by user");

        } else {

            Log.i(TAG, "Permission has been granted by user");

        }

    }

}
```

在模拟器或设备上编译并运行该 App，注意看会出现一个请求录音权限的对话框，如图 61-3 所示：

![image-O67TPFTC.jpg](img/image-O67TPFTC.jpeg)

图 61-3

点击“在使用应用程序时”按钮，并检查 Logcat 面板中出现了“Permission has been granted by user”的消息。

一旦用户授予了请求的权限，在未来的 App 调用中，`checkSelfPermission()`方法调用将返回`PERMISSION_GRANTED`结果，直到用户卸载并重新安装 App，或者在设置中更改了 App 的权限。

## 61.5 为权限请求提供理由

如图 61-3 所示，用户可以拒绝请求的权限。在这种情况下，除非用户在点击“拒绝”按钮之前选择了“不再询问”选项，否则 App 在每次用户启动它时都会继续请求权限。用户多次拒绝可能表明用户不理解为什么 App 需要该权限。因此，如果在发出请求时解释了需求的原因，用户可能会更有可能授予权限。遗憾的是，无法更改请求对话框的内容来包含此类解释。

解释最好包含在一个独立的对话框中，可以在向用户展示请求框之前显示。这引出了何时显示此解释对话框的问题。Android 文档建议仅在用户之前拒绝权限时显示解释对话框，并提供了一种方法来识别这种情况。

调用`ActivityCompat`类的`shouldShowRequestPermissionRationale()`方法会在用户之前拒绝请求时返回 true 结果，如果尚未请求则返回 false。在结果为 true 的情况下，App 应显示包含理由的对话框，一旦用户阅读并关闭了对话框，应重复权限请求。

要在示例 App 中添加此功能，请修改`onCreate()`方法使其内容如下：

```java
// ...

import android.app.AlertDialog;

// ...

private void setupPermissions() {

    int permission = ContextCompat.checkSelfPermission(this,

            Manifest.permission.RECORD_AUDIO);

    if (permission != PackageManager.PERMISSION_GRANTED) {

        Log.i(TAG, "Permission to record denied");

        if (ActivityCompat.shouldShowRequestPermissionRationale(this,

                Manifest.permission.RECORD_AUDIO)) {

            AlertDialog.Builder builder = new AlertDialog.Builder(this);

            builder.setMessage("此应用需要访问麦克风权限以录音")

                    .setTitle("需要权限");

            builder.setPositiveButton("OK", (dialog, id) -> makeRequest());

            AlertDialog dialog = builder.create();

            dialog.show();

        } else {

            makeRequest();

        }

    }

}
```



## 61.6 测试权限 App

在进行测试的设备或模拟器会话上，启动设置应用，选择应用选项，然后滚动选择 `PermissionDemo App`。在应用设置界面上，点击卸载按钮移除该 App。

重新运行应用，并在权限请求对话框出现时点击“不允许”（Don’t allow）按钮。停止并重启应用，验证理由对话框是否出现。点击“确定”，并在权限请求对话框出现时点击“应用使用期间”（While using the app）按钮。

返回“设置”应用，选择“应用”选项，再次从列表中选择 `PermissionDemo` 应用。一旦列出应用的设置，验证“权限”部分是否列出了“麦克风”权限。

返回“设置”应用，选择“应用”选项，再次从列表中选择 `PermissionDemo` 应用。一旦列出应用的设置，验证“权限”部分是否列出了“麦克风”权限：

![image-9QOZ6MSN.jpg](img/image-9QOZ6MSN.jpeg)

图 61-4

## 61.7 Summary

在 Android 6.0 引入之前，应用请求访问某些功能的权限的唯一必要步骤是在应用程序清单文件（manifest）中添加适当的行。用户在安装应用时将会被提示确认是否允许该权限。对于大多数权限仍然如此，但一组被认为是“危险”的权限除外。被认为是危险的权限通常具有允许应用违反用户隐私的可能，例如允许访问麦克风、联系人列表或外部存储。

如本章所述，基于 Android 6 或更高版本的应用现在必须在应用启动时向用户请求危险权限的批准，并在清单文件中包含权限请求。

# 62. Android 通知教程

通知为应用提供了一种在应用未运行或当前处于后台时向用户传达消息的方法。例如，消息应用可能会通知用户收到来自联系人的新消息。通知可以分为本地通知和远程通知。本地通知是由运行在设备上的应用本身在相应设备上触发的。另一方面，远程通知由远程服务器启动并递送到设备上供用户显示。

通知显示在从屏幕状态栏向下拉出的通知栏中，每条通知都可以包含某些操作，例如一个用于打开发送该通知的应用程序的按钮。Android 还支持“直接回复”（Direct Reply）通知，该功能允许用户在通知面板中输入并提交对通知的响应。

本章概述了在 Android 应用中实现本地通知的步骤。下一章（“Android 直接回复通知教程”）将涵盖直接回复通知的实现。

## 62.1 通知概述

当 Android 设备上启动通知时，它将作为状态栏中的一个图标出现。例如，图 62-1 显示了一个带有多个通知图标的状态栏：

![image-WI6GCDPC.jpg](img/image-WI6GCDPC.jpeg)

图 62-1

要查看通知，用户需要从状态栏开始执行向下滑动的动作以拉下通知栏，如图 62-2 所示：

![image-VP9GVS9U.jpg](img/image-VP9GVS9U.jpeg)

图 62-2

在运行 Android 8 或更高版本的设备上，长按应用启动器图标将显示与该应用相关的任何等待通知，如图 62-3 所示：

![image-2E9JGHTM.jpg](img/image-2E9JGHTM.jpeg)

图 62-3

Android 8 及更高版本还支持通知点，当有通知等待用户查看时，通知点会出现在应用启动器图标上。

典型的通知会显示一条消息，并在点击时启动负责发布该通知的应用。通知还可能包含操作按钮，点击时会执行针对对应应用的特定任务。例如，图 62-4 显示了一个包含两个操作按钮的通知，允许用户删除或保存收到的消息：

![image-UD7AY5DG.jpg](img/image-UD7AY5DG.jpeg)

图 62-4

用户还可以在通知中输入内联文本回复并发送到应用，如下方的图 62-5 所示。这允许用户在不将相应应用调至前景的情况下对通知做出响应：

![image-49L2GHCL.jpg](img/image-49L2GHCL.jpeg)

图 62-5

本章的剩余部分将介绍创建和发布包含操作的简单通知。直接回复支持的主题将在下一章“Android 直接回复通知教程”中进行介绍。

## 62.2 创建 NotifyDemo 项目

从欢迎界面选择“新建项目”选项，在生成的新项目对话框中，在点击“下一步”按钮之前选择“空视图 Activity”（Empty Views Activity）模板。

在 `Name` 字段中输入 `NotifyDemo` 并指定 `com.ebookfrenzy.notifydemo` 为包名。在点击“完成”按钮之前，将最低 API 级别设置为 `API 33: Android 13 (Tiramisu)`，并将语言菜单更改为 Java。

## 62.3 设计用户界面

主活动将包含单个按钮，其目的是创建并发布一个意图（intent）。在布局编辑器工具中找到并加载 `activity_main.xml` 文件，并删除默认的 `TextView` 组件。

启用自动连接（Autoconnect）的情况下，从面板中拖放一个 `Button` 对象到布局画布的中心，如图 62-6 所示。

在布局中选中 `Button` 组件后，使用属性面板配置 `onClick` 属性以调用名为 `sendNotification` 的方法。

![image-KCOJKXM9.jpg](img/image-KCOJKXM9.jpeg)

图 62-6

选择 `Button` 组件，将属性窗口中的文本更改为“Notify”，并将其提取为字符串资源。

## 62.4 创建第二个 Activity

在本例中，应用将包含一个由用户从通知内部启动的第二个 Activity。通过右键点击 `app -> java` 下的 `com.ebookfrenzy.notifydemo` 包名并选择 `New -> Activity -> Empty Views Activity` 菜单选项将此活动添加到项目中。

在 `Activity Name` 字段中输入 `ResultActivity` 并将布局文件命名为 `activity_result`。由于该活动在应用程序启动时启动（而是通过通知内部的意图启动），在点击“完成”按钮之前，确保禁用“启动 Activity”选项。

打开第二个活动的布局（`app -> res -> layout -> activity_result.xml`），并拖放一个 `TextView` 组件。编辑 `TextView` 的文本使其显示为“Result Activity”，并将其提取为字符串资源。

## 62.5 创建通知通道

在应用发送通知之前，必须创建一个通知通道（Notification Channel）。通知通道由在应用内唯一标识该通道的 ID、通道名称和通道描述组成（后两个用户可见）。通道的创建是通过配置 `NotificationChannel` 实例，并将该对象传递给 `NotificationManager` 类的 `createNotificationChannel()` 方法来实现的。对于示例，应用将包含一个名为“NotifyDemo News”的单一通知通道。编辑 `MainActivity.java` 文件并实现在应用启动时创建通道的代码：

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

        notificationManager =
            (NotificationManager)
            getSystemService(Context.NOTIFICATION_SERVICE);
    }
}
```

```java
createNotificationChannel(
    "com.ebookfrenzy.notifydemo.news",
    "NotifyDemo News",
    "Example News Channel");
}

protected void createNotificationChannel(String id, String name, String description) {

    int importance = NotificationManager.IMPORTANCE_LOW;
    NotificationChannel channel = new NotificationChannel(id, name, importance);

    channel.setDescription(description);
    channel.enableLights(true);
    channel.setLightColor(Color.RED);
    channel.enableVibration(true);
    channel.setVibrationPattern(new long[]{100, 200, 300, 400, 500, 400, 300, 200, 400});

    notificationManager.createNotificationChannel(channel);
}
```

该代码声明并初始化了一个 `NotificationManager` 实例，然后创建了一个具有低重要性级别（其他选项为高、max、min 和 none）的新通道，并配置了名称和描述属性。通道中还添加了一系列可选设置，以自定义用户接收通知到达提醒的方式。这些设置适用于发送到此通道的所有通知。最后，通过将通知通道对象传递给通知管理器实例的 `createNotificationChannel()` 方法来创建通道。

## 62.6 请求通知权限

在测试应用程序之前，必须在应用程序清单文件（manifest file）中请求相应的权限。具体而言，应用程序需要向用户发送通知的权限。在项目（Project）工具窗口中，找到并双击 `AndroidManifest.xml` 文件，将其加载到编辑器中并修改 XML 以添加权限：

```xml
package="com.ebookfrenzy.audioapp" >
```

上述步骤将足以确保当应用安装在运行 Android 6.0 之前的版本的设备上时，用户会启用通知权限。在 Android 中，通知访问被归类为一种“危险权限”（dangerous permission），因为它使应用程序有可能会损害用户的隐私。为了让示例应用在 Android 6 或更高版本的设备上正常运行，必须添加代码以在应用运行时请求权限。

编辑 `MainActivity.java` 文件，首先添加一些额外的导入指令和一个常量，用作所请求权限的请求请求标识码：

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

接下来，需要在类中添加一个方法，其目的是将要请求的权限和相应的请求标识码作为参数。继续留在 `MainActivity.java` 类文件中，按如下方式实现该方法：

```java
protected void requestPermission(String permissionType, int requestCode) {

    int permission = ContextCompat.checkSelfPermission(this, permissionType);

    if (permission != PackageManager.PERMISSION_GRANTED) {
        ActivityCompat.requestPermissions(
            this,
            new String[]{permissionType},
            requestCode
        );
    }
}
```

使用此书中“在 Android 中进行运行时权限请求”章节概述的步骤，上述方法在发出请求之前会验证指定的权限是否尚未授予，并将标识码作为参数传递。

当请求被处理后，将调用活动上的 `onRequestPermissionsResult()` 方法，并传递标识码和请求结果。因此，下一步是在 `MainActivity.java` 文件中按如下方式实现此方法：

```java
@Override
public void onRequestPermissionsResult(
        int requestCode,
        @NonNull String[] permissions,
        @NonNull int[] grantResults) {

    super.onRequestPermissionsResult(
        requestCode,
        permissions,
        grantResults
    );

    if (requestCode == NOTIFICATION_REQUEST_CODE) {
        if (grantResults.length == 0 ||
                grantResults[0] != PackageManager.PERMISSION_GRANTED) {

            Toast.makeText(
                this,
                "Notification permission required",
                Toast.LENGTH_LONG
            ).show();
        }
    }
}
```

上述代码检查请求标识码，以识别哪个权限请求已返回，然后再检查相应的权限是否已授予。如果权限被拒绝，将向用户显示消息，指示应用程序将无法运行且录制按钮将被禁用。

在测试应用之前，剩下的工作是在应用启动时调用新添加的 `requestPermission()` 方法。留在 `MainActivity.java` 文件中，按如下方式修改 `onCreate()` 方法：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {

    super.onCreate(savedInstanceState);

    requestPermission(
        Manifest.permission.POST_NOTIFICATIONS,
        NOTIFICATION_REQUEST_CODE
    );

    notificationManager =
        (NotificationManager)
        getSystemService(Context.NOTIFICATION_SERVICE);
}
```

代码更改完成后，编译并在运行 Android 13 或更高版本的设备或模拟器上运行应用。当显示图 62-7 所示对话框时，点击 Allow（允许）按钮以启用通知：

![image-8PN0LZUJ.jpg](img/image-8PN0LZUJ.jpeg)

图 62-7

启动应用后，将其放入后台并打开设置（Settings）应用。在设置应用中，选择应用（Apps），选择 NotifyDemo 项目，并在后续屏幕上点击通知（Notifications）项。通知屏幕应该列出 NotifyDemo News 类别对用户是激活状态：

![image-RRMVQ6J9.jpg](img/image-RRMVQ6J9.jpeg)

图 62-8

在继续之前，确保为应用启用了通知点。虽然这不是示例的要求，但值得注意的是可以通过调用通知管理器的 `deleteChannel()` 方法从应用中删除通道，传递要删除的通道 ID：

```java
String channelID = "com.ebookfrenzy.notifydemo.news";

notificationManager.deleteNotificationChannel(channelID);
```

## 62.7 创建并发布通知

通知使用 `Notification.Builder` 类创建，并且包含图标、标题和内容。打开 `MainActivity.java` 文件并按如下方式实现 `sendNotification()` 方法以构建基础通知：

```java
import android.app.Notification;
import android.view.View;

public void sendNotification(View view) {

    String channelID = "com.ebookfrenzy.notifydemo.news";

    Notification notification =
        new Notification.Builder(MainActivity.this, channelID)
            .setContentTitle("Example Notification")
            .setContentText("This is an example notification.")
```



```java
.setSmallIcon(android.R.drawable.ic_dialog_info)

.setChannelId(channelID)

.build();

}
```

一旦构建了通知，就需要使用`NotificationManager`实例的`notify()`方法将其发布。访问`NotificationManager`并发布通知需要添加到`sendNotification()`方法中：

```java
protected void sendNotification(View view) {

    int notificationID = 101;

    String channelID = "com.ebookfrenzy.notifydemo.news";

    Notification notification = new Notification.Builder(MainActivity.this, channelID)

        .setContentTitle("New Message")

        .setContentText("You've received new messages.")

        .setSmallIcon(android.R.drawable.ic_dialog_info)

        .setChannelId(channelID)

        .build();

    notificationManager.notify(notificationID, notification);

}
```

注意，当发布通知时，会被分配一个通知 ID。该 ID 可以任意整数，并可以在以后更新通知时使用。

编译并运行应用，点击主活动上的按钮。当通知图标出现在状态栏中时，触摸并从状态栏下拉以查看完整通知：

![image-I5CNGFS3.jpg](img/image-I5CNGFS3.jpeg)

图 62-9

点击并长按通知以查看更多信息：

![image-Z55VAV81.jpg](img/image-Z55VAV81.jpeg)

图 62-10

接下来，将应用置于后台，导航到显示所有应用启动图标的桌面屏幕，并注意如图 62-11 所示，`NotifyDemo`启动图标上出现了一个通知圆点：

![image-PT1MQ4LF.jpg](img/image-PT1MQ4LF.jpeg)

图 62-11

如果没有圆点，请检查`Settings`（设置）应用中`NotifyDemo`的通知选项，以确认已启用通知点，正如本章前面所述。如果圆点仍未出现，长按设备主屏幕的空白区域，从弹出的菜单中选择`Home Settings`（桌面设置）选项，并启用`Notification dots`（通知点）选项。

对启动图标进行长按将显示一个包含通知的弹出窗口：

![image-0FW8M0MM.jpg](img/image-0FW8M0MM.jpeg)

图 62-12

如果一个应用有多个待处理通知，长按菜单弹出窗口将包含通知计数（如上图高所示）。此数字可以在构建通知时通过调用`setNumber()`方法在应用内部进行配置：

```java
Notification notification = new Notification.Builder(MainActivity.this, CHANNEL_ID)

.setContentTitle("Example Notification")

.setContentText("This is an example notification.")

.setSmallIcon(android.R.drawable.ic_dialog_info)

.setChannelId(CHANNEL_ID)

.setNumber(10)

.build();
```

按照目前的实现，无论从何处访问，点击通知都没有任何效果。下一步是配置通知以便在点击时启动一个 activity。

## 62.8 从通知启动 Activity

通知应该允许用户执行某些操作，例如启动相应的应用或响应通知采取其他操作。一个常见的需求是当用户点击通知时，启动一个属于该应用的 activity。

这种方法需要启动一个 activity 并配置一个用于启动该 activity 的`Intent`。假设应用包含一个名为`ResultActivity`的 activity，则 intent 的创建方式如下：

```java
Intent resultIntent = new Intent(this, ResultActivity.class);
```

然后，需要将此 intent 封装在`PendingIntent`实例中。`PendingIntent`对象的设计允许将 intent 传递给其他应用程序，实质上授予这些应用程序在未来某个时刻执行该 intent 的权限。在这种情况下，`PendingIntent`对象用于为`Notification`系统提供在用户点击通知面板时启动`ResultActivity` activity 的方法：

```java
PendingIntent pendingIntent =

PendingIntent.getActivity(

    this,

    0,

    resultIntent,

    PendingIntent.FLAG_IMMUTABLE

);
```

剩下的工作是在构建通知过程中使用`setContentIntent()`方法分配`PendingIntent`对象。

将这些更改整合在一起得到了修改后的`sendNotification()`方法，其内容如下：

```java
import android.app.PendingIntent;

import android.content.Intent;

import android.graphics.drawable.Icon;

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

    Notification notification = new Notification.Builder(MainActivity.this,

    CHANNEL_ID)

    .setContentTitle("Example Notification")

    .setContentText("This is an example notification.")

    .setSmallIcon(android.R.drawable.ic_dialog_info)

    .setChannelId(channelID)

    .setContentIntent(pendingIntent)

    .build();

    notificationManager.notify(notificationId, notification);

}
```

编译并重新运行应用，点击按钮并显示通知栏。然而，这一次点击通知将导致`ResultActivity`启动。

## 62.9 为通知添加动作

为通知添加交互性的另一种方法是创建动作（actions）。它们显示为通知消息下方的按钮，并被为在用户点击时触发特定的 intent。如果将以下代码添加到`sendNotification()`方法中，将添加一个标记为“Open”的动作按钮，在选择时会启动引用的 pending intent：

```java
final Icon icon = Icon.createWithResource(MainActivity.this,

android.R.drawable.ic_dialog_info);

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

将上述代码添加到方法中并运行应用。发布通知并注意通知中出现的`Open`动作（取决于 Android 版本，可能需要向下滑动通知面板以显示`Open`动作）：

![image-ZAKDCBCW.jpg](img/image-ZAKDCBCW.jpeg)

图 62-13

点击动作将触发 pending intent 并启动`ResultActivity`。

## 62.10 折叠通知

如果一个应用经常发布通知，可能会出现这些通知塞满状态栏和通知栏，给用户带来欠佳的体验。这对于每次有突发新闻或新消息到达就发送通知的应用尤为如此。考虑图 62-14 中的通知：

![image-ILT1E2A.jpg](img/image-ILT1E2A.jpeg)

图 62-14

现在假设有了十或二十条新消息。为了避免这个问题，Android 允许将通知折叠成组。要折叠通知，每个通知必须通过`setGroup()`方法指定属于同一个组，并且必须发布额外的通知作为摘要通知。以下代码创建并发布了图 62-14 所示的三个通知，但将它们折叠到同一个组中。代码还发布了一个通知作为摘要：

```java
final String GROUP_KEY_NOTIFY = "group_notify";

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

当代码执行时，即使应用程序发送了四条通知，状态栏中也显示一个通知图标。在通知栏中，会显示一条摘要通知，列出每个捆绑通知中的信息：

![image-7DW18BEW.jpg](img/image-7DW18BEW.jpeg)

图 62-15

在通知条目上进一步向下拖动，面板会展开并显示每个捆绑通知的详细信息：

![image-JYFBH1QG.jpg](img/image-JYFBH1QG.jpeg)

图 62-16

## 62.11 总结

通知提供了一种方式，让应用程序在未运行或当前处于后台时向用户传递消息。通知出现在状态栏和通知栏中。本地通知由运行的应用程序在设备上触发，而远程通知由远程服务器发起并传递到设备。本地通知使用`NotificationCompat.Builder`类创建，并使用`NotificationManager`服务发布。

正如本章所示，可以通过操作（actions）、意图（intents）和`PendingIntent`类来配置通知，为用户提供选项（例如启动活动或保存消息）。通知捆绑（Notification bundling）提供了一种分组通知的机制，为发布更多通知的应用程序提供了改进的体验。

## 63. Android 直接回复通知教程

直接回复（Direct reply）是 Android 的一项功能，允许用户在通知中输入文本并将其发送到与通知关联的应用程序。这允许用户在不启动应用程序内活动的情况下直接在通知中回复消息。本章将基于上一节学到的知识，创建一个使用此通知功能的示例应用程序。

### 63.1 创建 DirectReply 项目

从欢迎界面选择`New Project`（新建项目）选项，在弹出的新项目对话框中，点击`Next`（下一步）按钮之前，选择`Empty Views Activity`模板。

在`Name`（名称）字段中输入`DirectReply`，并指定`com.ebookfrenzy.directreply`为包名。点击`Finish`（完成）按钮之前，将`Minimum API level`（最低 API 级别）设置为`API 33`：Android 13，并将`Language`（语言）菜单设置为`Java`。按照第 12.8 节“迁移项目到 View Binding”中概述的步骤修改项目以支持视图绑定（view binding）。

### 63.2 设计用户界面

将布局文件`activity_main.xml`加载到布局工具中。启用`Autoconnect`（自动连接），并在现有的“Hello World!”标签下方添加一个`Button`对象，如图 63-1 所示。在布局中选中`Button`组件后，使用`Attributes`（属性）工具窗口将`onClick`属性设置为调用名为`sendNotification`的方法。如有，使用`Infer Constraints`（推断约束）按钮为布局添加任何缺失的约束。在继续之前，选择“Hello World!” `TextView`，将`id`属性更改为`textView`，并将按钮上的文本修改为“Notify”：

![image-914PLUSI.jpg](img/image-914PLUSI.jpeg)

图 63-1

### 63.3 请求通知权限

在`Project`（项目）工具窗口中，找到并双击`AndroidManifest.xml`文件加载到编辑器，并修改 XML 添加权限元素：

```xml
package="com.ebookfrenzy.audioapp" >
```

.
.

编辑`MainActivity.java`文件，首先添加一些额外的导入指令和一个常量，作为所请求权限的请求标识码：

```java
.

.

import androidx.annotation.NonNull;

import androidx.core.app.ActivityCompat;

import androidx.core.content.ContextCompat;
```



```java
import android.widget.Toast;
import android.Manifest;
import android.content.pm.PackageManager;
.
.
public class MainActivity extends AppCompatActivity {
    private static final int NOTIFICATION_REQUEST_CODE = 101;
.
.
```

接下来，需要向类中添加一个方法，其目的是将要请求的权限和相应的请求标识码作为参数。留在`MainActivity.java`类文件中，如下实现该方法：

```java
protected void requestPermission(String permissionType, int requestCode) {
    int permission = ContextCompat.checkSelfPermission(
        this,
        permissionType
    );

    if (permission != PackageManager.PERMISSION_GRANTED) {
        ActivityCompat.requestPermissions(
            this,
            new String[]{permissionType},
            requestCode
        );
    }
}
```

当请求处理完成后，活动将调用`onRequestPermissionsResult()`方法，并传递标识码和请求结果。因此，下一步是在`MainActivity.java`文件中如下实现此方法：

```java
@Override
public void onRequestPermissionsResult(
    int requestCode,
    @NonNull String[] permissions,
    @NonNull int[] grantResults
) {
    super.onRequestPermissionsResult(
        requestCode,
        permissions,
        grantResults
    );

    if (requestCode == NOTIFICATION_REQUEST_CODE) {
        if (
            grantResults.length == 0
            || grantResults[0] != PackageManager.PERMISSION_GRANTED
        ) {
            Toast.makeText(
                this,
                "Notification permission required",
                Toast.LENGTH_LONG
            ).show();
        }
    }
}
```

在测试应用程序之前，最后剩下的工作是在应用程序启动时调用新添加的`requestPermission()`方法。留在`MainActivity.java`文件中，如下修改`onCreate()`方法：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);

    binding = ActivityMainBinding.inflate(getLayoutInflater());
    View view = binding.getRoot();
    setContentView(view);

    requestPermission(
        Manifest.permission.POST_NOTIFICATIONS,
        NOTIFICATION_REQUEST_CODE
    );
}
```

### 63.4 创建通知通道

与上一节的示例一样，在发送通知之前必须创建一个通道。编辑`MainActivity.java`文件并添加如下代码创建一个新通道：

```java
.
.
import android.app.NotificationChannel;
import android.app.NotificationManager;
import android.content.Context;
import android.graphics.Color;
.
.
public class MainActivity extends AppCompatActivity {
    ...
    private NotificationManager notificationManager;
    private final String channelID =
        "com.ebookfrenzy.directreply.news";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        ...
        notificationManager =
            (NotificationManager)
            getSystemService(Context.NOTIFICATION_SERVICE);

        createNotificationChannel(
            channelID,
            "DirectReply News",
            "Example News Channel"
        );
    }

    protected void createNotificationChannel(
        String id,
        String name,
        String description
    ) {
        int importance = NotificationManager.IMPORTANCE_HIGH;

        NotificationChannel channel =
            new NotificationChannel(id, name, importance);

        channel.setDescription(description);
        channel.enableLights(true);
        channel.setLightColor(Color.RED);
        channel.enableVibration(true);
        channel.setVibrationPattern(
            new long[]{100, 200, 300, 400, 500, 400, 300, 200, 400}
        );

        notificationManager.createNotificationChannel(channel);
    }
.
.
}
```

### 63.5 构建`RemoteInput`对象

使通知内直接回复文本可能的关键元素是`RemoteInput`类。之前的章节介绍了`PendingIntent`类，并解释了它如何允许应用程序创建一个意图，然后授予其他应用程序或服务在原始应用程序之外启动该意图的能力。在名为“Android 通知教程”的章节中，创建了一个等待许可，允许从通知内部启动应用程序中的活动。`RemoteInput`类允许将用户输入请求与意图一起包含在`PendingIntent`对象中。当`PendingIntent`对象中的意图触发时（例如启动活动），该活动也将收到用户提供的任何输入。

在通知中实现直接回复的第一步是创建`RemoteInput`对象。这是通过使用`RemoteInput.Builder()`方法实现的。要构建`RemoteInput`对象，需要一个键字符串，用于从生成的意图（intent）中提取输入。该对象还需要一个标签字符串（label），它将显示在通知的文本输入字段中。编辑`MainActivity.java`文件并添加`sendNotification()`方法。请注意，还添加了一些导入指令和变量，它们将在章节的后续内容中被用到：

```java
package com.ebookfrenzy.directreply;
.
.
import android.app.PendingIntent;
import android.app.RemoteInput;
import android.content.Intent;
.
.
public class MainActivity extends AppCompatActivity {
    private static final int notificationId = 101;
    private static final String KEY_TEXT_REPLY = "key_text_reply";
    private NotificationManager notificationManager;
    private static final String channelID =
        "com.ebookfrenzy.directreply.news";
.
.
.
    public void sendNotification(View view) {
        String replyLabel = "Enter your reply here";

        RemoteInput remoteInput =
            new RemoteInput.Builder(KEY_TEXT_REPLY)
                .setLabel(replyLabel)
                .build();
    }
.
.
}
```

现在`RemoteInput`对象已经创建并使用键和标签字符串进行了初始化，它需要被放置在通知动作对象中。然而，在执行该步骤之前，需要创建`PendingIntent`实例。

## 63.6 创建`PendingIntent`

创建`PendingIntent`的步骤与“Android 通知教程”章节概述的步骤相同，不同之处在于意图将配置为启动`MainActivity`。在`MainActivity.java`文件中，添加以下代码来创建`PendingIntent`：

```java
public void sendNotification(View view) {
    String replyLabel = "Enter your reply here";

    RemoteInput remoteInput =
        new RemoteInput.Builder(KEY_TEXT_REPLY)
            .setLabel(replyLabel)
            .build();

    Intent resultIntent =
        new Intent(this, MainActivity.class);

    PendingIntent resultPendingIntent =
        PendingIntent.getActivity(
            this,
            0,
            resultIntent,
            PendingIntent.FLAG_MUTABLE
        );
}
```

## 63.7 创建回复动作

内联回复将可以通过动作按钮在通知中访问。此动作需要被创建并配置图标、显示在按钮上的标签、`PendingIntent`对象以及`RemoteInput`对象。修改`sendNotification()`方法以添加创建此动作的代码：

```java
.
.
import android.graphics.drawable.Icon;
import android.app.Notification;
.
.
public void sendNotification(View view) {
    String replyLabel = "Enter your reply here";

    RemoteInput remoteInput =
        new RemoteInput.Builder(KEY_TEXT_REPLY)
            .setLabel(replyLabel)
            .build();

    Intent resultIntent =
        new Intent(this, MainActivity.class);

    PendingIntent resultPendingIntent =
        PendingIntent.getActivity(
            this,
            0,
            resultIntent,
            PendingIntent.FLAG_MUTABLE
        );

    final Icon icon =
        Icon.createWithResource(
            MainActivity.this,
            android.R.drawable.ic_dialog_info
        );

    Notification.Action replyAction =
        new Notification.Action.Builder(
            icon,
            "Reply",
            resultPendingIntent
        )
        .addRemoteInput(remoteInput)
        .build();
}
.
.
```

在教程的这一阶段，我们已经构建了并准备好使用的`RemoteInput`、`PendingIntent`和`Notification Action`对象。下一阶段是构建通知并发布它：

```java
public void sendNotification(View view) {
    String replyLabel = "Enter your reply here";

    RemoteInput remoteInput =
        new RemoteInput.Builder(KEY_TEXT_REPLY)
            .setLabel(replyLabel)
            .build();

    Intent resultIntent =
        new Intent(this, MainActivity.class);

    PendingIntent resultPendingIntent =
        PendingIntent.getActivity(
            this,
            0,
            resultIntent,
            PendingIntent.FLAG_IMMUTABLE
        );

    final Icon icon =
        Icon.createWithResource(
            MainActivity.this,
            android.R.drawable.ic_dialog_info
        );

    Notification.Action replyAction =
        new Notification.Action.Builder(
            icon,
            "Reply",
            resultPendingIntent
        )
        .addRemoteInput(remoteInput)
        .build();

    Notification newMessageNotification =
        new Notification.Builder(this, channelID)
            .setColor(
                ContextCompat.getColor(
                    this,
                    android.R.color.holo_blue_dark
                )
            )
            .setSmallIcon(
                android.R.drawable.ic_dialog_info
            )
            .setContentTitle("My Notification")
            .setContentText("This is a test message")
            .addAction(replyAction)
            .build();

    NotificationManager notificationManager =
        (NotificationManager)
        getSystemService(Context.NOTIFICATION_SERVICE);

    notificationManager.notify(
        notificationId,
        newMessageNotification
    );
}
```

完成更改后，编译并运行应用，允许通知，并测试点击按钮是否会发布通知。点击按钮发布通知的结果如图 63-2 所示：

- [图 63-2](https://example.org/4ZRHP8AX.jpg)（注：此处为占位符，实际应对应图片路径）

完成更改后，编译并运行应用，允许通知，并测试点击按钮是否会发布通知。点击按钮发布通知的结果如图 63-3 所示：

- [图 63-3](https://example.org/8W25C9.jpg)（注：此处为占位符，实际应对应图片路径）

```java
android.R.drawable.ic_dialog_info)
    .setContentText("Reply received")
    .build();

notificationManager.notify(
    notificationId,
    repliedNotification
);

}
}
```




最后一次测试应用程序，并验证在内联回复文本发送后进度指示器会消失，并且会出现一个新面板，表示回复已收到：

![image-AHGYZ098.jpg](img/image-AHGYZ098.jpeg)

图 63-5

## 63.10 总结

直接回复通知功能允许用户在通知内输入文本，并通过`intent`传递给相应应用程序的活动（`activity`）。直接回复是通过`RemoteInput`类实现的，该实例可以嵌入到操作（`action`）中，并与通知一起打包。在处理直接回复通知时，让`NotificationManager`服务知道回复已收到并处理至关重要。实现此点的最佳方法是使用首次发布通知时提供的`notification ID`来更新通知消息。

# 64. 折叠屏设备与多窗口支持

无论我们是否准备好，折叠屏设备都会到来（或者对于第一代三星 Galaxy Fold 来说，可能在设备本身准备好之前就出现了）。为了准备这一新类设备，了解一些应该采取的额外步骤，以确保你的应用程序在折叠屏设备上运行时运行正常。

幸运的是，支持折叠屏设备的大部分行为已经以多窗口支持的形式存在于 Android 中。

## 64.1 折叠屏与多窗口支持

当应用程序运行在折叠屏设备上时，它可能会与其他应用程序共享屏幕，并遇到重大的配置更改（例如，当用户折叠或展开显示器时屏幕尺寸的变化）。如果你的应用程序已经设计为可以处理设备方向的变化，那么它可能也能处理由屏幕折叠引起的变化，尽管建议进行彻底测试。

多窗口支持最初是在 Android 7 中引入的。与 Android 之前的版本不同，Android 7 中的多窗口支持允许在设备屏幕上同时显示多个活动。

Android 中的多窗口提供了不同形式的窗口支持。分屏模式适用于大多数手机、折叠屏设备和平板设备，它提供了一个分屏环境，其中两个活动并排或一个一在上地显示。它提供了一个可移动的分割线，当用户拖动它时，会调整分配给相邻每个活动的屏幕百分比：

![image-CXI3056.jpg](img/image-CXI30562.jpeg)

图 64-1

自由窗口模式为大屏幕设备提供了一个窗口化环境，目前由设备制造商决定启用。自由窗口与分屏模式的区别在于，它允许每个活动出现在独立的、可调整大小的窗口中，并且不限于同时显示两个活动。例如，图 64-2 显示了一个在自由窗口模式下的设备，计算器和第二个应用程序显示在独立的窗口中：

![image-VFWVBP99.jpg](img/image-VFWVBP99.jpeg)

图 64-2

画中画（Picture-in-picture）支持正如其名一样，允许在用户执行其他任务时在较小的窗口中继续视频播放，该主题将从“Android 画中画模式”章节开始介绍。

## 64.2 使用折叠屏模拟器

尽管在编写时，市场上还没有可以进行应用测试的折叠屏设备，但 Android SDK 包含了折叠屏模拟器。要创建一个折叠屏模拟器，选择`Android Studio Tools -> AVD Manager`菜单选项，点击`Create Virtual Device`按钮，并在硬件选择屏幕上选择下方图 64-3 所示的`Foldable`选项之一：

![image-GJEH5IHR.jpg](img/image-GJEH5IHR.jpeg)

图 64-3

在选择折叠屏后，继续创建过程，选择`Android 10 API 29`或更高版本作为系统镜像。

一旦模拟器启动，工具栏上将出现一个额外的按钮，允许模拟器在折叠和展开配置之间进行切换：

![image-IIUYOI9M.jpg](img/image-IIUYOI9M.jpeg)

图 64-4

## 64.3 进入多窗口模式

可以通过显示概览（Overview）屏幕、长按列出应用在工具栏中的应用图标来进入分屏模式，并选择如图 64-5 所示的`Split screen`菜单选项：

![image-7EXXWR0Y.jpg](img/image-7EXXWR0Y.jpeg)

图 64-5

一旦进入分屏模式，概览按钮将变为显示两个矩形（在图 64-6 中标记为 A），当前活动将填充屏幕的一部分（B），概览屏幕将出现在屏幕的相邻部分，允许选择第二个活动进行显示（C）：

![image-I45IIN83.jpg](img/image-I45IIN83.jpeg)

图 64-6

一旦选择了第二个应用，屏幕将如上文图 64-1 所示被均匀平分。

要退出分屏模式，只需将分隔两个活动的分割线拖动到远端，使一个活动填充整个屏幕，或者长按概览按钮直到它恢复为单个正方形。

## 64.4 启用自由窗口支持

尽管并非在所有设备上都得到官方支持，在大屏幕设备和模拟器上可以启用自由窗口模式。要启用此模式，在模拟器运行时或设备连接时运行以下`adb`命令：

```bash
adb shell settings put global enable_freeform_support 1
```

进行更改后，可能需要重启设备才能生效。

一旦启用，在概览屏幕上长按应用图标时将出现一个额外的选项，如图 64-7 所示：

![image-2DRGHZ.jpg](img/image-2DRGHZ.jpeg)

图 64-7

## 64.5 检查自由窗口支持

正如本章早期概述，Google 将是否启用自由窗口多窗口模式交给了各个 Android 设备制造商。由于自由窗口在大屏幕设备上才有意义，因此无法保证在运行应用程序的每个设备上都有自由窗口。幸运的是，如果设备不支持自由窗口，系统将忽略所有特定的自由窗口的方法和属性，因此使用这些不会导致应用程序在非自由窗口设备上崩溃。然而，可能会出现需要检测设备是否支持自由窗口多窗口模式的情况。这可以通过检查包管理器中的自由窗口管理功能来实现。以下代码示例检查了自由窗口多窗口支持，并根据结果返回布尔值：

```java
public Boolean checkFreeform() {
    return getPackageManager().hasSystemFeature(
        PackageManager.FEATURE_FREEFORM_WINDOW_MANAGEMENT);
}
```

## 64.6 在应用中启用多窗口支持

清单文件中的`android:resizableActivity`设置控制应用程序是否支持多窗口行为。该设置可以在应用程序级别或单个活动级别进行。例如，以下片段配置了名为`MainActivity`的活动以分屏和自由窗口多窗口模式：

```xml
android:name=".MainActivity"
android:resizeableActivity="true"
android:label="@string/app_name"
android:theme="@style/AppTheme.NoActionBar">
```

将属性设置为`false`将防止该活动出现在分屏模式或自由窗口模式下，并且相应的按钮将不会出现在概览（Overview）菜单中。在分屏配置中，选择一个禁用了多窗口支持的活动作为第二个活动，将导致一条消息，指示该应用可能不支持多窗口模式。

## 64.7 指定多窗口属性

在元素中提供了若干属性，用于指定活动在进入多窗口模式时启动时的尺寸和位置。当活动在自由窗口模式下启动时，其初始高度、宽度和位置可以使用以下属性指定：

- `android:defaultWidth`：指定活动的默认宽度。
- `android:defaultHeight`：指定活动的默认高度。
- `android:gravity`：指定活动的初始位置（起始、、结束、左侧、右侧、顶部等）。

请注意，上述属性仅在活动于自由窗口模式下显示时生效。以下示例配置了活动以特定的高度和宽度出现在屏幕顶部边缘：

```xml
android:defaultWidth="450dp"
android:gravity="start"
```

可以使用以下属性来指定活动在分屏视图或自由窗口模式下可以缩小的最小宽度和高度：

- `android:minimalHeight`：指定活动在分屏屏幕或自由窗口模式下可以缩小的最小高度。
- `android:minimalWidth`：指定活动可以缩小的最小宽度。

当用户将分屏分割线滑出最小高度或宽度时，系统将停止调整活动的布局，并简单地裁剪用户界面以为相邻的活动留出空间。以下清单文件为某个活动实现了最小宽度和高度属性：

```xml
android:minimalWidth="290dp"
```

## 64.8 检测多窗口模式

可能会出现某些情况，即活动需要检测其当前是否在多窗口模式下显示给用户。可以通过调用`Activity`类的`isInWindowMode()`方法获取当前状态。调用此方法时，它将返回`true`或`false`值，取决于活动当前是否处于全屏状态：

```java
if (this.isInWindowMode()) {
    // 活动正在多窗口模式下运行
} else {
    // 活动不在多窗口模式
}
```

## 64.9 接收多窗口通知

如果活动重写了`onWindowModeChanged()`回调方法，它将接收进入或退出多窗口模式的通知。传递给该方法的第一个参数在进入多窗口模式时为`true`，在活动退出时为`false`。新的配置设置包含在作为第二个参数传递的`Configuration`对象中：

```java
@Override
public void onWindowModeChanged(boolean isInWindowMode, Configuration newConfig) {
    super.onWindowModeChanged(isInWindowMode, newConfig);

    if (isInWindowMode) {
        // 活动已进入多窗口模式
    } else {
        // 活动已退出多窗口模式
    }
}
```

正如“处理活动状态”章节概述，Android 10 及更高版本允许多个活动处于恢复状态（也称为多恢复状态，multi-resume）。用户最近交互的活动被称为顶层活动（topmost activity）。为了跟踪活动在获得和丢失顶层状态时的，可以在活动中实现`onTopResumedActivityChanged()`回调方法，例如：

```java
@Override
public void onTopResumedActivityChanged(boolean isTopResumedActivity) {
    super.onTopResumedActivityChanged(isTopResumedActivity);

    if (isTopResumedActivity) {
        // 活动现在是顶层活动
    } else {
        // 活动不再是顶层活动
    }
}
```

在某些运行 Android 9 的设备上，通过在应用清单中启用以下属性，也可以在应用利用多恢复功能：

```xml
android:name="android.allow_resumed_activities" android:value="true"
```

## 64.10 在多窗口模式下启动活动

在本书的“Android 显式意图——示例”章节中，创建了一个示例应用，其中一个活动使用`intent`启动第二个活动。默认情况下，通过`intent`启动的活动被认为与源活动位于同一个任务栈（task stack）中。然而，可以通过向`intent`传递适当的标志将活动启动到新的任务栈中。

当多窗口模式下的活动在同一个任务栈内启动另一个活动时，新活动将替换分屏或自由窗口窗口中的源活动（用户通过返回键返回到原始活动）。然而，在分屏模式下启动到新的任务栈时，第二个活动将出现在原始活动相邻的窗口中，允许同时查看两个活动。在自由窗口模式下，启动的活动将出现在与原始活动独立的窗口中。

要将活动启动到新的任务栈，必须在启动之前在`intent`上设置以下标志：

- `Intent.FLAG_ACTIVITY_LAUNCH_ADJACENT`
- `Intent.FLAG_ACTIVITY_MULTIPLE_TASK`
- `Intent.FLAG_ACTIVITY_NEW_TASK`

例如，以下代码配置并启动了设计为在独立窗口中出现的第二个活动：

```java
Intent i = new Intent(this, SecondActivity.class);

i.addFlags(Intent.FLAG_ACTIVITY_LAUNCH_ADJACENT |
    Intent.FLAG_ACTIVITY_MULTIPLE_TASK |
    Intent.FLAG_ACTIVITY_NEW_TASK);

startActivity(i);
```

## 64.11 配置自由活动尺寸和位置

默认情况下，在自由窗口模式下启动到不同任务栈的活动将位于屏幕中心，尺寸由系统决定。可以通过`ActivityOptions`类将边界设置传递给`intent`来控制此窗口的位置和尺寸。此过程的第一步是创建一个`Rect`对象，配置代表活动窗口的左侧（X）、顶部（Y）、右侧（X）和底部（Y）坐标。以下示例创建了一个`Rect`对象，其左上角位于（0, 0），右下角位于（100, 100）：

```java
Rect rect = new Rect(100, 800, 900, 700);
```

下一步是创建`ActivityOptions`类的基本实例，并通过`setLaunchBounds()`方法使用`Rect`设置进行初始化：

```java
ActivityOptions options = ActivityOptions.makeBasic();

ActivityOptions bounds = options.setLaunchBounds(rect);
```

最后，将`ActivityOptions`实例转换为`Bundle`对象并与`Intent`对象一起传递给`startActivity()`方法：

```java
startActivity(i, bounds.toBundle());
```

组合这些步骤后得到的代码序列如下：

```java
Intent i = new Intent(this, SecondActivity.class);

i.addFlags(Intent.FLAG_ACTIVITY_LAUNCH_ADJACENT |
    Intent.FLAG_ACTIVITY_MULTIPLE_TASK |
    Intent.FLAG_ACTIVITY_NEW_TASK);

Rect rect = new Rect(100, 800, 900, 700);

ActivityOptions options = ActivityOptions.makeBasic();

ActivityOptions bounds = options.setLaunchBounds(rect);

startActivity(i, bounds.toBundle());
```




当源活动在自由窗口模式下通过`intent`启动第二个活动时，新活动窗口将按照`Rect`对象定义的位置和尺寸出现。

Android 7 引入了多窗口支持，该系统允许屏幕上同时显示多个活动（activity）。这一功能现在已成为支持折叠屏设备的基础。多窗口支持提供了三种模式：分屏模式、自由窗口模式和画中画。在分屏模式下，屏幕被水平或垂直划分为两个窗格，每个窗格中显示一个活动。自由窗口模式仅在某些 Android 设备上支持，它允许每个活动出现在独立的、可移动且可调整大小的窗口中。正如本章概述，`Android SDK`提供了许多方法和属性设置，用于检测、响应和控制应用内部的多窗口行为。

# 65. Android SQLite 数据库概览

不需要存储至少某些持久化数据的移动应用程序寥寥无几。数据库是大多数应用程序不可或缺的方面，范围从几乎完全由数据驱动的应用到需要存储少量数据（如常见的游戏分数）的应用不等。

当考虑到典型 Android 应用的瞬态生命周期时，持久化数据存储的重要性变得显而易见。由于 Android 运行时系统随时存在终止应用程序组件以释放资源的风险，制定一个全面的数据存储策略以避免数据丢失，是设计和实现任何应用开发策略的关键因素。

本章将涵盖与 Android 操作系统绑定的 SQLite 数据库管理系统，并概述用于在 Android 应用中实现持久化 SQLite 数据库存储的 Android SDK 类。在探讨 Android 开发背景下的 SQLite 细节之前，将先对数据库和 SQL 进行简要概述。

## 65.1 理解数据库表

数据库表提供了数据库中最基础层的数据结构。每个数据库可以包含多个表，每个表设计用于存储特定类型的信息。例如，一个数据库可能包含一个客户表，其中包含特定业务每个客户的名称、地址和电话号码。同一个数据库可能还包含一个产品表，用于存储该业务销售的产品描述以及相关的产品代码。

数据库中的每个表都分配有一个名称，该名称在该特定数据库中必须是唯一的。表名一旦分配给某个数据库中的表，除非在另一个数据库的范围内，否则不能用于另一个表。

## 65.2 引入数据库模式（Schema）

数据库模式（Schemas）定义了存储在数据库表中的数据的特征。例如，客户表的模式可能会定义客户名为长度不超过 20 个字符的字符串，并将客户电话为特定格式的数值数据字段。

模式还用于定义整个数据库的结构以及每个数据库中各个表之间的关系。

## 65.3 列和数据类型

在此阶段，将数据库表视为电子表格（数据存储在行和列中）是有帮助的。

每列代表对应表中的一个数据字段。例如，一个表的名称、地址和电话数据字段都是列。

每列又被定义为包含特定类型的数据。因此，设计用于存储数字的列被定义为包含数值数据。

## 65.4 数据库行

保存到表中的每条新记录都存储在行中。每行又由与所存记录相关的各个列组成。

再次考虑本章前面描述的电子表格类比。客户表中的每个条目都等同于电子表格中的行，每一列都包含每个客户的数据（名称、地址、电话等）。当向表中添加新客户时，会创建一个新行，并将该客户的数据存储在该新行的对应列中。

行有时也被称为记录（records）或条目（entries），这些术语通常可以通用使用。

## 65.5 引入主键

每个数据库表都应该包含一个或多个列，用于唯一标识表中的每一行。这在数据库术语中被称为主键（Primary Key）。例如，一个表可以使用银行账户列作为主键。或者，客户表可以使用客户的社会安全号码作为主键。

主键允许数据库管理系统唯一地标识表中的特定行。如果没有主键，将无法检索或删除表中的某个特定行，因为无法确定是否选择了正确的行。例如，假设存在一个表，客户的姓氏被定义为主键。想象一下，如果数据库中记录了多个姓“Smith”的客户，会产生什么问题。如果没有某种确定的方法来唯一地标识某个特定行，要确保在任何时候访问的都是正确的数据是不可能的。

主键可以由表中的单列组成，也可以由多列组成。要符合单列主键的条件，任何两行不能包含匹配的主键值。当使用多个列构建主键时，单个列的值不需要是唯一的，但所有列的值组合起来必须是唯一的。

## 65.6 什么是 SQLite？

SQLite 是一种嵌入式关系型数据库管理系统（RDBMS）。大多数关系型数据库（Oracle、SQL Server 和 MySQL 是主要示例）都是独立运行的后台服务器进程，与需要数据库访问的应用程序协作。SQLite 被称为嵌入式，是因为它以库的形式提供，并链接到应用程序中。因此，后台没有运行独立的数据库服务器。所有的数据库操作都是通过调用 SQLite 库中的函数在应用程序内部处理的。

SQLite 的开发者已将该技术置于公共领域，结果它现在是一项广泛部署的数据库解决方案。

SQLite 使用 C 语言编写，因此 Android SDK 在底层数据库接口周围提供了一个基于 Java 的“封装”。它由类组成，可以在应用程序的 Java 或 Kotlin 代码中用于创建和管理基于 SQLite 的数据库。

有关 SQLite 的更多信息，请参考 `https://www.sqlite.org`。

## 65.7 结构化查询语言 (SQL)

在 SQLite 数据库中使用称为结构化查询语言的高级语言访问数据。这种语言通常缩写为 SQL，读作 sequel。SQL 是大多数关系型数据库管理系统使用的标准语言。SQLite 基本符合 SQL-92 标准。

SQL 是一种直观且易于使用的语言，专门为读取和写入数据库数据而设计。由于 SQL 包含一组较小的关键字，可以快速学习。此外，SQL 语法在大多数 DBMS 实现中大体相同，因此学习了一个系统的后，你的技能可能会转移到其他数据库管理系统。

虽然本章将使用一些基础 SQL 语句，但对 SQL 的详细概述超出了本书的范围。然而，许多其他资源提供的 SQL 概述远比我们在这里这一章中能提供的要。

## 65.8 在 Android 虚拟设备 (AVD) 上尝试 SQLite

对于不熟悉数据库和 SQLite 的读者来说，直接上手创建一个使用 SQLite 的 Android 应用程序可能会让他们感到畏惧。幸运的是，Android 预装了 SQLite，其中包含一个交互环境，允许在连接到运行中的 Android AVD 模拟器实例的`adb shell`会话中发布 SQL 命令。这是学习 SQLite 和 SQL 的一种实用方法，对于识别运行在模拟器中的应用程序所创建的数据库问题是一个极具价值的工具。

要启动交互式 SQLite 会话，首先要运行 AVD 会话。这可以在 Android Studio 中通过启动 Android 设备管理器（`Tools` -> `Device Manager`）、选择一个之前配置过的 AVD 并点击启动按钮来实现。

一旦 AVD 运行，打开终端（Terminal）或命令提示符窗口，使用`adb`命令行工具连接到模拟器，如下所示：

```bash
adb shell
```

连接后，shell 环境将提供一个命令提示符，可以在其中输入命令。首先使用`su`命令获取超级用户权限：

```bash
Generic_x86:/ su
root@android:/ #
```

如果消息显示不允许使用超级用户权限，则该 AVD 实例可能包含 Google Play 支持。要解决此问题，请创建一个新的 AVD，并在“选择设备定义”屏幕上选择一个在“Play Store”列没有标记的设备。

SQLite 数据库中的数据存储在运行应用程序的 Android 设备文件系统的数据库文件中。默认情况下，这些数据库文件的文件系统路径如下：

`/data/data//databases/.db`

例如，如果一个包名为`com.example.MyDBApp`的应用程序创建了一个名为`mydatabase.db`的数据库，则在设备上的文件路径如下：

`/data/data/com.example.MyDBApp/databases/mydatabase.db`

因此，为了本次练习，请在`adb shell`中切换目录到`/data/data`并创建一个适用于某些 SQLite 实验的子目录结构：

```bash
cd /data/data
mkdir com.example.dbexample
cd com.example.dbexample
mkdir databases
cd databases
```

为数据库文件创建合适的位置后，如下所示启动交互式 SQLite 工具：

```bash
root@android:/data/data/databases # sqlite3 ./mydatabase.db
sqlite3 ./mydatabase.db
```

SQLite 版本 3.8.10.2 2015-05-20 18:17:19

输入`".help"`获取用法提示。

`sqlite>`

在`sqlite>`提示符下，可以输入命令来执行任务，如创建表、插入和检索数据。例如，要在我们的数据库中创建一个新表，并包含用于存储 ID、名称、地址和电话的字段，需要以下语句：

```sql
create table contacts (_id integer primary key autoincrement, name text, address text, phone text);
```

注意，表中的每行都应该有一个对该行唯一的主键。在上面的示例中，我们把`ID`字段指定为主键，将其声明为类型为`integer`，并要求 SQLite 在每次添加新行时自动增加数字。这是确保每行都具有唯一主键的常用方法。在大多数其他平台上，主键的名称选择是任意的。然而，在 Android 中，主键必须命名为`_id`，以便使用所有 Android 数据库相关类完全访问数据库。其余字段每个都声明为`text`类型。

要列出当前所选数据库中的表，使用`.tables`语句：

```sql
sqlite> .tables
contacts
```

向表中插入记录：

```sql
sqlite> insert into contacts (name, address, phone) values ("Bill Smith", "123 Main Street, California", "123-555-2323");
sqlite> insert into contacts (name, address, phone) values ("Mike Parks", "10 Upping Street, Idaho", "444-444-1212");
```

从表中检索所有行：

```sql
sqlite> select * from contacts;
1|Bill Smith|123 Main Street, California|123-555-2323
2|Mike Parks|10 Upping Street, Idaho|444-444-1212
```

提取符合特定标准的行：

```sql
sqlite> select * from contacts where name="Mike Parks";
2|Mike Parks|10 Upping Street, Idaho|444-444-1212
```

退出`sqlite3`交互环境：

```sql
sqlite> .exit
```



在模拟器环境中运行 Android 应用程序时，任何数据库文件都将根据之前过的路径约定在模拟器文件系统中创建。这样做的好处是，你可以通过`adb`连接，导航到数据库文件的位置，将其加载到`sqlite3`交互工具中并对数据进行操作，以识别应用程序代码中可能发生的问题。

同样重要的是，虽然可以通过`adb shell`连接到物理 Android 设备，但 shell 默认没有获得足够的权限来创建和管理 SQLite 数据库。因此，数据库问题的调试最好使用 AVD 会话进行。

# 65.9 Android SQLite 类

如前所述，SQLite 是用 C 语言编写的，而 Android 应用程序主要使用 Java 或 Kotlin 开发。为了弥补这种“语言差异”，Android SDK 包含了一组类，在 SQLite 之上提供了一个编程层。本章剩余部分将提供该类别中主要类的简单概述。

## 65.9.1 Cursor

这是一个专门用于访问数据库查询结果的类。例如，对数据库执行的 SQL 操作可能会返回多个匹配行。可以使用`Cursor`实例来遍历这些结果，并在应用程序代码中使用各种方法进行访问。该类的一些关键方法包括：

- `close()`：释放游标使用的资源并关闭它。
- `getCount()`：返回结果集中行数。
- `moveToFirst()`：移动到结果集的第一行。
- `moveToLast()`：移动到结果集的最后一行。
- `moveToNext()`：移动到结果集的下一行。
- `move()`：根据指定的偏移从当前位置移动。
- `get()`：返回当前位置指定列索引处的值（变体包括`getString()`、`getInt()`、`getShort()`、`getFloat()`和`getDouble()`）。

## 65.9.2 SQLiteDatabase

该类提供了应用程序代码与底层 SQLite 之间的主要接口，包括创建、删除和对数据库执行 SQL 操作的能力。该类的一些关键方法包括：

- `insert()`：向数据库表插入新行。
- `delete()`：从数据库表中删除行。
- `query()`：执行指定的数据库查询并通过`Cursor`对象返回匹配结果。
- `execSQL()`：执行不返回结果数据的单条 SQL 语句。
- `rawQuery()`：执行 SQL 查询语句并以`Cursor`对象的形式返回匹配结果。

## 65.9.3 SQLiteOpenHelper

这是一个旨在简化创建和更新数据库的辅助类。该类必须在寻求数据库访问的应用程序代码中子类，并在该子类中实现以下回调方法：

- `onCreate()`：在首次创建数据库时调用。该方法将`SQLiteDatabase`对象作为参数传递给新创建的数据库。这是初始化数据库（创建表和插入任何初始数据行）的理想位置。
- `onUpgrade()`：当应用程序代码包含更新的数据库版本号引用时调用。这通常用于应用程序在设备上更新且需要数据库架构也进行更新以处理额外数据存储的情况。

除了上述强制性的回调方法外，在打开数据库时调用的`onOpen()`方法也可以在子类中实现。

子类的构造函数也必须实现，以调用父类，并传递应用上下文、数据库名称和数据库版本。

`SQLiteOpenHelper`类的常用方法包括：

- `getWritableDatabase()` – 打开或创建一个用于读写的数据库。返回一个以`SQLiteDatabase`对象形式的数据库引用。
- `getReadableDatabase()` – 创建或打开一个仅读的数据库。返回一个以`SQLiteDatabase`对象形式的数据库引用。
- `close()` – 关闭数据库。

## 65.9.4 ContentValues

`ContentValues`是一个便利类，允许声明键/值对，这些键/值对由表列标识符和要存储在每列中的值组成。该类在数据库表中插入或更新条目时具有特别的用处。

# 65.10 Android Room 持久化库

Android SDK`SQLite`类的局限性在于它们需要中等的编码工作，并且没有利用新的架构指南和功能（如`LiveData`和生命周期管理）。Android Jetpack 架构组件包含了 Room 持久化库来解决这些缺点。该库在`SQLite`数据库系统之上提供了一个高层接口，能够以极少的代码在 Android 设备上本地存储数据，同时符合现代应用程序架构的建议。

接下来的章节将提供使用`SQLite`和 Room 持久化库进行 SQLite 数据库管理的概述和教程。

# 65.11 总结

`SQLite`是一个轻量级的嵌入式关系型数据库管理系统，包含在 Android 框架中，并为 Android 应用实现组织化的持久化数据存储提供了机制。与 Room 持久化库结合时，Android 提供了一种从 Android 应用内部实现数据存储的现代方法。

本章在 Android 应用开发的背景下，对数据库以及特别是`SQLite`概述。

# 66. Android SQLite 数据库教程

标题为“Android SQLite 数据库概述”的章节涵盖了使用`SQLite`数据库管理系统将关系数据库存储集成到 Android 应用中的基本原理。在本章中，我们将创建一个使用`SQLite`数据库的项目，用于存储和检索数据。

## 66.1 关于数据库示例

该示例项目是一个简单的数据输入和检索应用程序，允许用户添加、查询和删除数据库条目。该应用程序背后的思想是一个包含客户姓名和电话的简单联系人数据库。

数据库文件的名称将为`customerDB.db`，它反将包含一个名为`customers`的单表。数据库表中的每条记录将包含一个唯一的客户 ID、客户姓名和电话，分别对应列名`customername`和`customerphone`。客户 ID 列将作为主键，并由数据库管理系统自动分配和递增。

## 66.2 创建 SQLDemo 项目

启动 Android Studio，从欢迎界面选择 New Project（新建项目）选项，在生成的新项目对话框中，在点击 Next（下一步）按钮之前选择 Empty Views Activity 模板。

在`Name`（名称）字段中输入`SQLDemo`并指定`com.ebookfrenzy.sqldemo`为包名。在点击 Finish（完成）按钮之前，将 Minimum API level 设置为`API 26`：Android 8.0 (Oreo)，并将语言菜单更改为`Java`。使用第 12.8 节迁移项目到 View Binding 中的步骤为项目启用视图绑定。

## 66.3 设计用户界面

打开`activity_main.xml`文件并删除默认的`TextView`组件。在布局中添加两个 Plain Text（纯文本）字段、三个 Buttons 和一个`TextView`，并如图 66-1 所示进行定位：

![image-DVXU5QQR.jpg](img/image-DVXU5QQR.jpeg)

图 66-1

将 Plain Text 视图的`hint`属性改为“name”和“phone”，并移除默认的“Name”文本属性。修改按钮使其显示为“Add”、“Find”和“Delete”，并将`TextView`文本改为“Database Ready”，将所有字符串值提取到资源中，并手动或使用 Infer 按钮应用布局约束。

将 Plain Text 视图和`TextView`的 ID 分别更改为`customerName`、`customerPhone`和`statusText`。最后，配置按钮调用命名为`addCustomer`、`findCustomer`和`deleteCustomer`的方法。

## 66.4 创建数据模型

完成后，该应用程序将由一个 activity 类和一个数据库处理器类组成。数据库处理器将是`SQLiteOpenHelper`的子类，并在底层`SQLite`数据库与 activity 类之间提供一个抽象层，activity 调用数据库处理器与数据库进行交互（添加、删除和查询数据库条目）。为了以结构化的方式实现这种交互，需要实现第三类来持有在 activity 和处理器之间传递的数据库条目数据。这实际上非常简单的类，能够持有客户 ID、姓名和电话值，以及用于访问这些值的 getter 和 setter 方法。该类的实例可以在 activity 和数据库处理器中创建，并根据需要来回传递。本质上，这个类代表了数据库模型。

在 Project 工具窗口中导航到`app -> java`并右键点击包名。从弹出菜单中选择 New -> Java Class 选项，在 Create New Class 对话框中将类命名为`Customer`，并将 Kind 菜单更改为`Class`，然后按键盘上的 Enter 键。

一旦创建，`Customer.java`源文件将自动加载到 Android Studio 编辑器。加载后，修改代码以添加相应的构造函数：

```java
package com.ebookfrenzy.sqldemo;

public class Customer {

    private int id;

    private String customerName;

    private String customerPhone;

    public Customer() {

    }

    public Customer(int id, String customerName, String customerPhone) {

        this.id = id;

        this.customerName = customerName;

        this.customerPhone = customerPhone;

    }

    public Customer(String customerName, String customerPhone) {

        this.customerName = customerName;

        this.customerPhone = customerPhone;

    }

    public void setID(int id) {

        this.id = id;

    }

    public int getID() {

        return id;

    }

    public void setCustomerName(String customerName) {

        this.customerName = customerName;

    }

    public String getCustomerName() {

        return customerName;

    }

    public void setCustomerPhone(String customerPhone) {

        this.customerPhone = customerPhone;

    }

    public String getCustomerPhone() {

        return customerPhone;

    }

}
```

完成后的类包含了用于存储数据库条目列的数据成员。

## 66.5 实现数据处理器

数据处理器将通过子类 Android`SQLiteOpenHelper`类来实现，并如“Android SQLite 数据库概述”所述，添加构造函数、`onCreate()`和`onUpgrade()`方法。由于处理器需要代表 activity 组件添加、查询和删除数据，该类中还需要添加对应的方法。

首先，向项目添加第二个新类作为处理器，命名为`MyDBHandler`。一旦创建了新类，将其修改为如下：

```java
package com.ebookfrenzy.sqldemo;

import android.database.sqlite.SQLiteDatabase;

import android.database.sqlite.SQLiteOpenHelper;

import android.content.Context;

import android.content.ContentValues;

import android.database.Cursor;

public class MyDBHandler extends SQLiteOpenHelper {
```

```java
public MyDBHandler(Context context, String name,

    SQLiteDatabase.CursorFactory factory, int version) {

    super(context, DATABASE_NAME, factory, DATABASE_VERSION);

}

@Override

public void onCreate(SQLiteDatabase db) {

}

@Override

public void onUpgrade(SQLiteDatabase db, int oldVersion,

    int newVersion) {

}

}
```

现在已经通过模板`onCreate()`和`onUpgrade()`方法预填充了源文件，下一个任务是修改代码，以声明数据库名称、表名、表列和数据库版本的常量，如下：

.

.

```java
public class MyDBHandler extends SQLiteOpenHelper {

    private static final int DATABASE_VERSION = 1;

    private static final String DATABASE_NAME = "customerDB.db";

    public static final String TABLE_CUSTOMERS = "customers";

    public static final String COLUMN_ID = "id";

    public static final String COLUMN_CUSTOMERNAME = "customername";

    public static final String COLUMN_CUSTOMERPHONE = "customerphone";

}
```

.

接下来，需要实现`onCreate()`方法，以便在数据库首次初始化时创建 customers 表。这涉及构造一个 SQL CREATE 语句，该语句包含创建具有适当列的新表所需的指令，然后将其传递给`SQLiteDatabase`对象的`execSQL()`方法，该对象是作为参数传递给`onCreate()`的：

```java
@Override

public void onCreate(SQLiteDatabase db) {

    String CREATE_CUSTOMERS_TABLE = "CREATE TABLE " +

        TABLE_CUSTOMERS + "("

        + COLUMN_ID + " INTEGER PRIMARY KEY," +

        COLUMN_CUSTOMERNAME

        + " TEXT," + COLUMN_CUSTOMERPHONE + " TEXT" + ")";

    db.execSQL(CREATE_CUSTOMERS_TABLE);

}
```

当处理程序使用的数据库版本号大于之前使用的版本时，会调用`onUpgrade()`方法。在此情况下执行的精确步骤将取决于具体的应用程序，因此在本例中，我们将删除旧数据库并创建一个新的：

```java
@Override

public void onUpgrade(SQLiteDatabase db, int oldVersion,

    int newVersion) {

    db.execSQL("DROP TABLE IF EXISTS " + TABLE_CUSTOMERS);

    onCreate(db);

}
```

在`MyDBHandler.java`处理类中，剩下的只需实现添加、查询和删除数据库表条目的方法。

## 66.6 添加处理方法（Add Handler Method）

插入数据库记录的方法将命名为`addCustomer()`，它将接受一个`Customer`数据模型类的实例作为参数。在方法体内部创建一个`ContentValues`对象，并用从`Customer`对象中提取出的数据列的键值对进行填充。接下来，通过调用`getWritableDatabase()`获取数据库引用，然后调用返回的数据库对象的`insert()`方法。最后，在完成插入后，需要关闭数据库：

```java
public void addCustomer(Customer customer) {

    ContentValues values = new ContentValues();

    values.put(COLUMN_CUSTOMERNAME, customer.getCustomerName());

    values.put(COLUMN_CUSTOMERPHONE, customer.getCustomerPhone());

    SQLiteDatabase db = this.getWritableDatabase();

    db.insert(TABLE_CUSTOMERS, null, values);

    db.close();

}
```

## 66.7 查询处理方法（Query Handler Method）

查询数据库的方法将命名为`findCustomer()`，它将接受一个包含要查找的客户名称的`String`对象作为参数。使用此字符串将构造一个 SQL SELECT 语句以在表中找到所有匹配记录。在本例中，将仅返回第一个匹配项，并包含在我们`Customer`数据模型类的新实例中：



public Customer findCustomer(String customername) {

    String query = "SELECT * FROM " + TABLE_CUSTOMERS + " WHERE " + COLUMN_CUSTOMERNAME + " = \"" + customername + "\"";

    SQLiteDatabase db = this.getWritableDatabase();

    Cursor cursor = db.rawQuery(query, null);

    Customer customer = new Customer();

    // ... (省略内部赋值逻辑)

    return customer;

}

```
*(注：根据示例逻辑，代码块内部不翻译，此处为保持结构对齐)*

## 66.8 删除处理方法 (Delete Handler Method)

删除记录的方法将命名为`deleteCustomer()`，它将接受一个包含要删除客户名称的`String`对象作为参数。该方法将使用 SQL SELECT 语句在表中查找所有匹配记录。如果找到，则将其删除。该方法将返回一个布尔值：

```java
public boolean deleteCustomer(String customername) {

    // ... (实现逻辑)

    return true; 

}
```

## 66.9 实现 Activity 方法 (Implementing the Activity Methods)

在测试应用程序之前的最后一个任务是为用户界面上的三个按钮编写`onClick`事件处理程序，如下：

```java
package com.example.ldemo;

// ... (导入部分)

public class MainActivity extends AppCompatActivity {

    private ActivityMainBinding binding;

    private MyDBHandler dbHandler;

    @Override

    protected void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);

        EdgeToEdge.enable(this);

        binding = ActivityMainBinding.inflate(getLayoutInflater());

        setContentView(binding.getRoot());

        ViewCompat.setOnApplyWindowInsetsListener(binding.main, (v, insets) -> {

            Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());

            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom);

            return insets;

        });

        dbHandler = new MyDBHandler(this, null, null, 1);

    }

    public void addCustomer(View view) {

        Customer customer = new Customer(binding.customerName.getText().toString(),

            binding.customerPhone.getText().toString());

        dbHandler.addCustomer(customer);

        binding.customerName.setText("");

        binding.customerPhone.setText("");

    }

    public void findCustomer(View view) {

        Customer customer = dbHandler.findCustomer(binding.customerName.getText().toString());

        if (customer != null) {

            binding.customerPhone.setText(String.valueOf(customer.getCustomerPhone()));

            binding.statusText.setText("Match Found");

        } else {

            binding.statusText.setText("No Match Found");

        }

    }

    public void deleteCustomer(View view) {

        boolean result = dbHandler.deleteCustomer(binding.customerName.getText().toString());

        if (result) {

            binding.statusText.setText("Record Deleted");

            binding.customerName.setText("");

            binding.customerPhone.setText("");

        } else {

            binding.statusText.setText("No Match Found");

        }

    }

}
```

## 66.10 测试应用程序 (Testing the Application)

代码更改完成后，在 AVD 会话或物理 Android 设备上编译并运行应用程序。当应用程序运行后，在用户界面表单中输入客户名称和电话，并点击添加按钮。记录添加后，文本框将清空。重复这些步骤向数据库添加第二个客户。接下来，在客户名称字段中输入新添加客户的名称，并点击查询按钮。表单应更新为所选客户的 ID 和电话。点击删除按钮删除所选记录。随后按客户名称搜索将显示该记录已不存在。

## 66.11 总结 (Summary)

本章通过步进的方式演示了 Android 应用中基于 SQLite 数据库存储的实际应用。为了进一步提升你的数据库开发技能，可以考虑扩展示例，使其包含更新数据库表中现有记录的能力。

## 1. 了解 Android Content Providers（内容提供者）

上一章介绍了如何创建一个示例应用程序，用于使用 SQLite 数据库存储数据。通过这种方式实现时，数据对于该应用程序是私有的，因此在同一台设备上运行的其他应用程序无法访问。虽然对于许多类型的应用程序来说这可能是期望的行为，但不可避免地会出现某些情况，即代表应用程序存储的数据可能让其他应用程序受益。一个典型的例子是 Android 设备上内置“联系人”（Contacts）应用存储的数据。虽然联系人应用主要负责管理用户的通讯录详情，但这些数据也提供给任何需要访问的应用程序。Android 之间的这种数据共享通过实现内容提供者来实现。

## 2. 什么是 Content Provider？

内容提供者在不同的 Android 应用程序之间提供了对结构化数据的访问。这些数据以数据表（与 SQLite 数据库非常相似）或文件句柄的形式暴露应用程序。这本质上涉及一种客户端/服务器架构的实现，其中请求访问数据的应用程序是客户端，内容提供者是服务器，代表客户端执行操作并返回结果。

一个成功的内容提供者实现涉及多个元素，每个元素将在本章的剩余部分进行详细介绍。

## 3. Content Provider

内容提供者是作为`android.content.ContentProvider`类的子类创建的。通常，负责管理要共享数据的应用程序将实现一个内容提供者，以便与其他应用程序共享这些数据。

创建内容提供者涉及实现一些方法来代表其他客户端应用程序管理数据。这些方法如下：

### 3.1 onCreate()

此方法在内容提供者首次创建时调用，应用于执行内容提供者所需的任何初始化任务。

### 3.2 query()

当客户端请求从内容提供者检索数据时，将调用此方法。该方法识别检索的数据（单行或多行），执行数据提取，并将结果封装在`Cursor`对象中返回。

### 3.3 insert()

当需要向提供者数据库插入新行时，会调用此方法。此方法必须识别数据的目标，执行插入操作并返回新添加行的完整 URI。

### 3.4 update()

当需要代表客户端更新现有行时调用的方法。该方法使用传递的参数来更新相应的表行，并返回操作后更新的行数。

### 3.5 delete()

当需要从表中删除行时调用此方法。此方法删除指定的行，并返回被删除的行计数。

### 3.6 getType()

返回由内容提供者存储的数据 MIME 类型。

在内容提供者中实现这些方法时，重要的一点是，除了`onCreate()`方法外，它们都可能同时从多个进程中被调用，因此必须是线程安全的。

一旦实现了内容提供者，随之产生的问题就是如何在 Android 系统中识别该提供者。这就是内容 URI（content URI）发挥用场的地方。

## 4. Content URI

一个 Android 设备可能包含多个内容提供者。因此，系统必须提供某种方法从一个提供者中识别出另一个。同样，单个内容提供者可能提供对多种形式内容的访问（通常以数据库表的形式）。因此，客户端应用程序需要一种方法来指定所需访问的底层数据。这是通过内容 URI 实现的。

内容 URI 用于识别特定内容提供者中的特定数据。URI 的 Authority（授权）部分标识内容提供者，通常形式为内容提供者的包名。例如：

```
com.example.mydbapp.myprovider
```

可以通过在 authority 之后附加表名来引用提供者数据结构中的特定数据库表。例如，以下 URI 引用了内容提供者中名为`products`的表：

```
com.example.mydbapp.myprovider/products
```

同样，可以通过向 URI 附加行 ID 来引用指定表中的特定行。例如，以下 URI 引用了`products`表中`ID`列存储值等于 3 的行：

```
com.example.mydbapp.myprovider/products/3
```

在内容提供者中实现`insert`、`query`、`update`和`delete`方法时，这些方法将负责识别传入的 URI 是指向表中的特定行还是引用了多行，并采取相应的行动。鉴于 URI 可以扩展到多个层级，这可能是一项复杂的任务。然而，使用`UriMatcher`类可以显著简化这一过程，将在书中进行概述。

## 5. Content Resolver（内容解析器）

通过`ContentResolver`对象访问内容提供者。应用程序可以通过调用应用程序上下文的`getContentResolver()`方法获取其内容解析器的引用。

内容解析器对象包含一组与内容提供者镜像的方法（`insert`、`query`、`delete`等）。应用程序只需调用这些方法，并指定要执行操作内容的 URI。然后，内容解析器和内容提供者对象将通信以代表应用程序执行请求的任务。

## 6. Manifest 元素

为了让内容提供者在 Android 系统中可见，必须在其所属应用程序的 Android manifest 文件中声明。这是通过`<provider>`元素实现的，该元素必须包含以下项：

- `android:authority` – 内容提供者的完整授权 URI。例如`com.example.mydbapp.mydbapp.myprovider`。
- `android:name` – 实现内容提供者的类名。在大多数情况下，它的值与 authority 相同。

同样，该元素也可以用于定义客户端应用程序为了访问底层数据而必须拥有的权限。如果没有声明权限，默认行为是允许所有应用程序访问。

权限可以设置为涵盖整个内容提供者，也可以限制特定的表和记录。

## 7. 总结

属于应用程序的数据通常对应用程序是私有的，其他应用程序无法访问。当需要共享数据时，就需要设置内容提供者。本章涵盖了组合实现应用程序间共享的基础元素，并概述了内容提供者、内容 URI 和内容解析器的概念。

在下一章中，我们将扩展之前创建的`SQLDemo`项目，以便通过内容提供者提供底层客户数据。

如上一章所述，内容提供者（content providers）提供了一种机制，使得一个 Android 应用程序的数据可以被其他应用程序访问。在提供了对内容提供者的理论概述后，本章将通过扩展在“Android SQLite 数据库教程”章节中创建的`SQLDemo`项目，来实现基于内容提供者的数据库访问。

## 68.1 复制 SQLDemo 项目

为了保持原始`SQLDemo`项目完整，在修改它以实现该应用程序的内容提供者支持之前，我们将为该项目创建一个备份副本。如果`SQLDemo`项目当前在 Android Studio 打开，请使用`File -> Close Project`菜单选项将其关闭。

使用你操作系统的文件管理器，导航到包含 Android Studio 项目的目录，并将`SQLDemo`项目文件夹复制到名为`SQLDemo_provider`的新文件夹中。

在 Android Studio 欢迎界面，打开`SQLDemo_provider`项目使其加载到主窗口。

## 68.2 添加内容提供者包

下一步是向`SQLDemo`项目添加一个新包以包含内容提供者类。在 Project 工具窗口中导航到`app -> java`，右键点击它，并选择`New -> Package`菜单选项添加此新包。当出现`Choose Destination Directory`对话框时，从目录结构面板选择`..\app\src\main\java`并点击 OK。

在`New Package`对话框中，按下回车键之前在名称字段中输入以下包名：

`com.ebookfrenzy.sqldemo.provider`

新包现在应该列在 Project 工具列表中，如图 38-1 所示：

![image-CCMHUWO5.jpg](img/image-CCMHUWO5.jpeg)

图 68-1

## 68.3 创建内容提供者类

正如“理解 Android 内容提供者”中所讨论，内容提供者是通过子类`android.content.ContentProvider`类创建的。因此，下一步是在新的提供者包中添加一个类作为此应用程序的内容提供者。在 Project 工具窗口中找到新包，右键点击它并选择`New -> Other -> Content Provider`菜单选项。在`Configure Component`对话框中，在`Class Name`字段中输入`MyContentProvider`，并在`URI Authorities`字段中输入以下内容：

`com.ebookfrenzy.sqldemo.provider.MyContentProvider`

在点击 Finish 创建新类之前，请确保新的内容提供者类已导出并启用。

一旦创建了新类，`MyContentProvider.java`文件应该列在 Project 工具窗口提供者包下方，并自动加载到编辑器中，其内容将如下列表所示：

```java
package com.ebookfrenzy.sqldemo.provider;

import android.content.ContentProvider;

import android.content.ContentValues;

import android.database.Cursor;

import android.net.Uri;

public class MyContentProvider extends ContentProvider {

public MyContentProvider() {

}

@Override

public int delete(Uri uri, String selection, String[] selectionArgs) {

// 实现此方法以处理删除一个或多行的请求。

throw new UnsupportedOperationException("Not yet implemented");

}

@Override

public String getType(Uri uri) {

// TODO: 实现此方法以处理对给定 URI 数据的 MIME 类型请求。

throw new UnsupportedOperationException("Not yet implemented");

}

@Override

public Uri insert(Uri uri, ContentValues values) {

// TODO: 实现此方法以处理插入新行的请求。

throw new UnsupportedOperationException("Not yet implemented");

}

@Override

public boolean onCreate() {

// TODO: 实现此方法以便启动时初始化你的内容提供者。

return false;

}

@Override
```



public Cursor query(Uri uri, String[] projection, String selection, String[] selectionArgs, String sortOrder) {  
    // TODO: 实现此方法以处理来自客户端的查询请求。  
    throw new UnsupportedOperationException("Not yet implemented");  
}  

@Override  
public int update(Uri uri, ContentValues values, String selection, String[] selectionArgs) {  
    // TODO: 实现此方法以处理更新一个或多行的请求。  
    throw new UnsupportedOperationException("Not yet implemented");  
}  
```  

快速查看该文件中的代码可以看出，Android Studio 已经为`ContentProvider`子类需要实现的每个方法填充了存根方法（stubs）。很快就需要开始实现这些方法了，但首先需要声明一些与提供者内容权威（authority）和 URI 相关的常量。

## 68.4 构建 Authority 和内容 URI

如上一章所述，所有内容提供者都必须关联有一个权威（authority）和一个内容 URI。在实践中，权威通常是内容提供者类本身的完整包名，在本例中，即在上一节创建新的内容提供者类时声明的`com.ebookfrenzy.sqldemo.provider.MyContentProvider`。

内容 URI 将根据应用程序的要求而异，但对于此示例，它将包含权威并在末尾附加数据库表名。在`MyContentProvider.java`文件中，进行以下修改：

```java
package com.ebookfrenzy.sqldemo.provider;

.

.

public class MyContentProvider extends ContentProvider {

    private static final String AUTHORITY = "com.ebookfrenzy.sqldemo.provider.MyContentProvider";

    private static final String CUSTOMERS_TABLE = "customers";

    public static final Uri CONTENT_URI = Uri.parse("content://" + AUTHORITY + "/" + CUSTOMERS_TABLE);

.
```
```  

上述语句首先创建一个名为`AUTHORITY`的`String`对象并将权威字符串赋值给它。同样，创建一个名为`CUSTOMERS_TABLE`的第二个`String`对象，并用数据库表名初始化。最后，将这两个字符串元素组合，加上前缀`content://`并使用`Uri`类的`parse()`方法转换为`Uri`对象。结果赋值给变量`CONTENT_URI`。

## 68.5 在内容提供者中实现 URI 匹配

当内容提供者的方法被调用时，它们将接收一个指示要执行操作的`URI`作为参数。该`URI`可能采取特定表中特定行的引用形式。`URI`也可能更通用，例如仅指定数据库表。每个方法都有责任识别`Uri`类型并采取相应的行动。使用`UriMatcher`实例可以极大简化这一任务。一旦创建了`UriMatcher`实例，就可以将其配置为在被要求时返回与其检测到的`URI`类型对应的特定整数值。在本教程中，我们将配置`UriMatcher`实例，当`URI`引用整个 customers 表时返回值`1`，当`URI`引用 customers 表特定行的 ID 时返回值`2`。在开始创建`UriMatcher`实例之前，我们首先创建两个整数变量来表示这两种 URI 类型：

```java
package com.ebookfrenzy.sqldemo.provider;

.

.

import android.database.sqlite.SQLiteDatabase;
import android.database.sqlite.SQLiteQueryBuilder;
import android.content.UriMatcher;
import android.text.TextUtils;
import com.ebookfrenzy.sqldemo.MyDBHandler;

public class MyContentProvider extends ContentProvider {

    private static final String AUTHORITY = "com.ebookfrenzy.sqldemo.provider.MyContentProvider";

    private static final String CUSTOMERS_TABLE = "customers";

    public static final Uri CONTENT_URI = Uri.parse("content://" + AUTHORITY + "/" + CUSTOMERS_TABLE);

    public static final int CUSTOMERS = 1;
```

```java
public static final int CUSTOMER_ID = 2;
```

在声明了`Uri`类型变量后，现在是时候添加代码来创建一个`UriMatcher`实例并配置它返回相应的变量了：

```java
public class MyContentProvider extends ContentProvider {

    private MyDBHandler myDB;

    public static final int CUSTOMERS = 1;
    public static final int CUSTOMER_ID = 2;
    private static final UriMatcher sURIMatcher = new UriMatcher(UriMatcher.NO_MATCH);

    static {
        sURIMatcher.addURI(AUTHORITY, CUSTOMERS_TABLE, CUSTOMERS);
        sURIMatcher.addURI(AUTHORITY, CUSTOMERS_TABLE + "/#", CUSTOMER_ID);
    }
}
```

`UriMatcher`实例（命名为`sURIMatcher`）现在已准备好在 URI 仅引用客户表时返回`CUSTOMERS`的值，当 URI 包含表中特定行的 ID 时，返回`CUSTOMER_ID`。

## 68.6 实现 Content Provider 的 `onCreate()` 方法

当内容提供者类被创建并初始化时，将调用该类的`onCreate()`方法。在此方法内部，必须执行该类的任何初始化任务。对于此示例，所有需要执行的操作是在在“Android SQLite 数据库教程”中实现的`MyDBHandler`类的实例。一旦创建了此实例，它将能够被类中的其他方法访问，因此还需要对数据库处理程序进行声明，这导致了`MyContentProvider.java`文件的以下代码更改：

```java
@Override
public boolean onCreate() {
    myDB = new MyDBHandler(getContext(), null, null, 1);
    return false;
}
```

## 68.7 实现 Content Provider 的 `insert()` 方法

当客户端应用程序或活动请求将数据插入到底层数据库时，将调用内容提供者类的`insert()`方法。然而，此时项目中的`MyContentProvider.kt`文件中仅存在一个存根方法（stub method），其内容如下：

```java
public Uri insert(Uri uri, ContentValues values) {
    TODO("实现此方法以处理插入新行的请求。");
}
```

传递给方法的参数是指定插入目标位置的`URI`以及包含要插入数据的`ContentValues`对象。

该方法现在需要修改以执行以下任务：

- 使用`sUriMatcher`对象识别 URI 类型。

- 如果`URI`无效，则抛出异常。

- 获取底层`SQLite database`可写实例的引用。

- 执行 SQL 插入操作将数据插入到数据库表中。

- 通知相应的内容解析器（content resolver）数据库已修改。

- 返回新添加表行的`URI`。

将这些需求整合后得到了修改的`insert()`方法，其内容如下：

```java
@Override
public Uri insert(Uri uri, ContentValues values) {
    int uriType = sURIMatcher.match(uri);
    SQLiteDatabase sqlDB = myDB.getWritableDatabase();
    long id = 0;
    switch (uriType) {
        case CUSTOMERS:
            id = sqlDB.insert(MyDBHandler.TABLE_CUSTOMERS, null, values);
            break;
        default:
            throw new IllegalArgumentException("Unknown URI: " + uri);
    }
    getContext().getContentResolver().notifyChange(uri, null);
    return Uri.parse(CUSTOMERS_TABLE + "/" + id);
}
```

## 68.8 实现 Content Provider 的 `query()` 方法

当调用内容提供者返回数据时，将调用提供者类的`query()`方法。当调用时，此方法会接收以下部分或全部参数：

- `URI` – 指定执行查询的数据源的`URI`。它可以采取带有多个结果的通用查询形式，也可以针对单个表行 ID 的特定查询。

- `Projection`（投影）——数据库表中的行可以包含多列数据。在本应用程序中，例如这些对应于 ID、客户姓名和电话号码。`projection`参数简单的`String`数组，包含要在结果数据集中返回每个列的名称。

- `Selection`（选择）——作为查询一部分执行的选择性“where”元素。该参数控制从指定的数据库选择哪些行。例如，如果要求仅选择名为“John Andrews”的客户，则传递给`query()`方法的`selection`字符串将为`customername = “John Andrews”`。

- `Selection Args`（选择参数）——执行 SQL 查询操作以选择所需的任何额外参数。

- `Sort Order`（排序顺序）——所选行的排序顺序。

当调用时，`query()`方法需要执行以下操作：

- 使用`sUriMatcher`识别`Uri`类型。

- 如果`URI`无效，则抛出异常。

- 根据传递给方法的标准构建 SQL 查询。为了方便起见，可以使用`SQLiteQueryBuilder`类来构建查询。

- 在数据库上执行查询操作。

- 通知内容解析器该操作。

- 返回包含查询结果的`Cursor`对象。

考虑到这些需求，`MyContentProvider.kt`文件中`query()`方法的代码现在应如列表所示：

```java
@Override
public Cursor query(Uri uri, String[] projection, String selection, String[] selectionArgs, String sortOrder) {
    SQLiteQueryBuilder queryBuilder = new SQLiteQueryBuilder();
    queryBuilder.setTables(MyDBHandler.TABLE_CUSTOMERS);
    int uriType = sURIMatcher.match(uri);
    switch (uriType) {
        case CUSTOMER_ID:
            queryBuilder.appendWhere(MyDBHandler.COLUMN_ID + "=" + uri.getLastPathSegment());
            break;
        case CUSTOMERS:
            break;
        default:
            throw new IllegalArgumentException("Unknown URI");
    }
    Cursor cursor = queryBuilder.query(myDB.getReadableDatabase(), projection, selection, selectionArgs, null, sortOrder);
    cursor.setNotificationUri(getContext().getContentResolver(), uri);
    return cursor;
}
```

## 68.9 实现 Content Provider 的 `update()` 方法

当请求对现有数据库行进行更改时，将调用内容提供者的`update()`方法。该方法接收带有`ContentValues`格式的新值的`URI`以及常用的`selection`字符串。

调用时，`update()`方法通常执行以下步骤：

- 使用`sUriMatcher`识别 URI 类型。

- 如果`URI`无效，则抛出异常。

- 获取底层`SQLite database`可写实例的引用。

- 根据选择标准和 URI 类型对数据库执行相应的更新操作。

- 通知内容解析器数据库更改。

- 返回因更新操作更改的行数。

通用`update()`方法以及我们在项目中使用的方法如下：

```java
@Override
public int update(Uri uri, ContentValues values, String selection, String[] selectionArgs) {
    int uriType = sURIMatcher.match(uri);
    SQLiteDatabase sqlDB = myDB.getWritableDatabase();
    int rowsUpdated = 0;
    switch (uriType) {
        case CUSTOMERS:
            rowsUpdated = sqlDB.update(MyDBHandler.TABLE_CUSTOMERS, values, selection, selectionArgs);
            break;
        case CUSTOMER_ID:
            String id = uri.getLastPathSegment();
            if (TextUtils.isEmpty(selection)) {
                rowsUpdated = sqlDB.update(MyDBHandler.TABLE_CUSTOMERS, values, MyDBHandler.COLUMN_ID + "=" + id, null);
            } else {
                rowsUpdated = sqlDB.update(MyDBHandler.TABLE_CUSTOMERS, values, MyDBHandler.COLUMN_ID + "=" + id + " and " + selection, selectionArgs);
            }
            break;
        default:
            throw new IllegalArgumentException("Unknown URI: " + uri);
    }
    getContext().getContentResolver().notifyChange(uri, null);
    return rowsUpdated;
}
```

## 68.10 实现 Content Provider 的 `delete()` 方法

与其他许多其他内容提供方法一样，`delete()`方法接收一个`URI`、一个选择字符串以及一组可选的选择参数。一个典型的`delete()`方法在被调用时还会执行以下任务（这些任务到目前为止已经非常熟悉）：

- 使用`sUriMatcher`来识别`URI`类型。

- 如果`URI`无效，则抛出异常。

- 获取底层`SQLite`数据库写入实例的引用。

- 根据选择标准和`Uri`类型在数据库上执行相应的删除操作。

- 通知内容解析器（content resolver）数据库发生了变化。

- 返回由于更新操作而更改的行数。

典型的`delete()`方法在许多方面与`update()`方法相似，其实现方式如下：



```java
@Override
public int delete(Uri uri, String selection, String[] selectionArgs) {
    int uriType = sURIMatcher.match(uri);
    SQLiteDatabase sqlDB = myDB.getWritableDatabase();
    int rowsDeleted = 0;
    switch (uriType) {
        case CUSTOMERS:
            rowsDeleted = sqlDB.delete(MyDBHandler.TABLE_CUSTOMERS, selection, selectionArgs);
            break;
        case CUSTOMER_ID:
            String id = uri.getLastPathSegment();
            if (TextUtils.isEmpty(selection)) {
                rowsDeleted = sqlDB.delete(MyDBHandler.TABLE_CUSTOMERS, MyDBHandler.COLUMN_ID + "=" + id, null);
            } else {
                rowsDeleted = sqlDB.delete(MyDBHandler.TABLE_CUSTOMERS, MyDBHandler.COLUMN_ID + "=" + id + " and " + selection, selectionArgs);
            }
            break;
        default:
            throw new IllegalArgumentException("Unknown URI: " + uri);
    }
    getContext().getContentResolver().notifyChange(uri, null);
    return rowsDeleted;
}
```

实现了这些方法后，根据本示例的要求，内容提供者类就已经完成了。下一步是确保在项目清单文件中声明了该内容提供者，以便让任何寻求访问的内容解析器都能看到它。

## 68.11 在清单文件中声明内容提供者

除非在内容提供者所属的应用程序清单文件中声明了它，否则内容解析器将无法定位并访问它。如前所述，内容提供者是使用标签声明的，且清单条目必须正确引用内容提供者的权限（authority）和内容 URI。

因此，在项目工具窗口中找到`manifests -> AndroidManifest.xml`文件，并双击它将其加载到编辑面板中。在编辑面板中，确保当`MyContentProvider`类被添加到项目时，Android Studio已经自动添加了内容提供者的声明：

```xml
xmlns:tools="http://schemas.android.com/tools"
android:allowBackup="true"
android:dataExtractionRules="@xml/data_extraction_rules"
android:fullBackupContent="@xml/backup_rules"
android:icon="@mipmap/ic_launcher"
android:label="@string/app_name"
android:roundIcon="@mipmap/ic_launcher_round"
android:supportsRtl="true"
android:theme="@style/Theme.SQLDemo"
tools:targetApi="31">
android:name=".provider.MyContentProvider"
android:authorities="com.ebookfrenzy.sqldemo.provider.MyContentProvider"
android:enabled="true"
android:exported="true">
android:name=".MainActivity"
android:exported="true">
```

在测试应用程序之前，剩下的工作是修改数据库处理器类，使用内容提供者而不是直接访问数据库。

## 68.12 修改数据库处理器

当起初创建此应用程序时，它的设计是使用数据库处理器直接访问底层数据库的。现在已经实现了内容提供者，需要修改数据库处理器，以便通过内容解析器使用内容提供者来执行所有数据库操作。

第一步是修改`MyDBHandler.kt`类，使其获取`ContentResolver`实例的引用。这可以在类的构造方法中实现：

```java
package com.ebookfrenzy.sqldemo;

import android.content.ContentResolver;
import com.ebookfrenzy.sqldemo.provider.MyContentProvider;

public class MyDBHandler extends SQLiteOpenHelper {
    private ContentResolver myCR;
    public MyDBHandler(Context context, String name, SQLiteDatabase.CursorFactory factory, int version) {
        super(context, DATABASE_NAME, factory, DATABASE_VERSION);
        myCR = context.getContentResolver();
    }
}
```

接下来，需要重写`addCustomer()`、`findCustomer()`和`removeCustomer()`方法，使用内容解析器和内容提供者进行数据管理：

```java
public void addCustomer(Customer customer) {
    ContentValues values = new ContentValues();
    values.put(COLUMN_CUSTOMERNAME, customer.getCustomerName());
    values.put(COLUMN_CUSTOMERPHONE, customer.getCustomerPhone());
    myCR.insert(MyContentProvider.CONTENT_URI, values);
}

public Customer findCustomer(String customername) {
    String[] projection = {COLUMN_ID, COLUMN_CUSTOMERNAME, COLUMN_CUSTOMERPHONE };
    String selection = "customername = \"" + customername + "\"";
    Cursor cursor = myCR.query(MyContentProvider.CONTENT_URI, projection, selection, null, null);
    Customer customer = new Customer();
    if (cursor.moveToFirst()) {
        customer.setID(Integer.parseInt(cursor.getString(0)));
        customer.setCustomerName(cursor.getString(1));
        customer.setCustomerPhone(cursor.getString(2));
        cursor.close();
    } else {
        customer = null;
    }
    return customer;
}

public boolean deleteCustomer(String customername) {
    boolean result = false;
    String selection = "customername = \"" + customername + "\"";
    int rowsDeleted = myCR.delete(MyContentProvider.CONTENT_URI, selection, null);
    if (rowsDeleted > 0)
        result = true;
    return result;
}
```

随着数据库处理器类更新为使用内容解析器和内容提供者，现在可以测试应用程序了。编译并运行应用程序，执行添加、查找和删除条目的操作。在操作和功能方面，应用程序的行为与直接访问数据库时完全相同，它现在使用的是内容提供者。

正如我们在下一章中看到的，一旦内容提供者落实并在清单文件中声明，任何其他应用程序都可能访问这些数据（因为没有声明权限）。其他应用程序访问所需的唯一信息是内容 URI 和表中的列名。

## 68.13 总结

本章的目标是提供实现 Android 内容提供者的具体步骤的详细概述，特别关注内容提供者类中查询、插入、删除和更新方法的结构和实现。还涵盖了使用内容解析器类访问内容提供数据的实际用法，并对数据库项目进行了修改，以使用内容提供者和内容解析器。

## 69 内容提供者客户端教程

在关于内容提供者的最后一个章节中，我们将构建一个访问`SQLDemo`内容提供者数据并显示联系人列表的应用程序。

## 69.1 创建 SQLDemoClient 项目

启动 Android Studio，从欢迎屏幕选择 New Project，并在出现的新项目对话框中选择 Empty Views Activity 模板。

在 Name 字段中输入`SQLDemoClient`，并指定包名为`com.ebookfrenzy.sqldemoclient`。在点击 Finish 按钮之前，将 Minimum API level 设置为`API 26: Android 8.0 (Oreo)`并将 Language 菜单更改为`Java`。按照第 12.8 节中迁移项目到 View Binding 的步骤为项目启用视图绑定。

## 69.2 设计用户界面

打开`activity_main.xml`文件并移除默认的`TextView`。在布局中添加一个按钮和一个`TextView`，将按钮文本更改为“Reload”（重载），并调整视图位置使布局类似于图 69-1：

![image-N17ABKO2.jpg](img/image-N17ABKO2.jpeg)

图 69-1

使用 Infer（推断）约束来配置布局约束，将`TextView`的`textAppearance`属性更改为`Display1`并将按钮的`onClick`属性设置为名为`reload()`的方法。

## 69.3 访问 Content Provider

访问内容提供者的代码将包含在`reload()`方法中。第一步是通过调用`Content Resolver`实例的`query()`方法获取`Cursor`对象。调用`query()`时，我们需要为由`SQLDemo`内容提供者管理的`customers`表提供内容 URI，其读取如下：

`content://com.ebookfrenzy.sqldemo.provider.MyContentProvider/customers`

一旦我们有了`Cursor`对象的引用，就可以遍历数据库记录并使用我们的`TextView`组件显示数据。编辑`MainActivity.java`文件并按如下所示添加`reload()`方法：

```java
package com.ebookfrenzy.sqldemoclient;

.

.

import android.database.Cursor;

import android.net.Uri;

...

public class MainActivity extends AppCompatActivity {
.
.
public void reload(View view) {
    Cursor cursor = getContentResolver().query(
        Uri.parse(
        "content://com.ebookfrenzy.sqldemo.provider.MyContentProvider/customers"),
        null, null, null, null);
    if (cursor != null) {
        if (cursor.moveToFirst()) {
            StringBuilder stringBldr = new StringBuilder();
            while (!cursor.isAfterLast()) {
                int nameindex = cursor.getColumnIndex("customername");
                int phoneindex = cursor.getColumnIndex("customerphone");
                if ((nameindex != -1) && (phoneindex != -1)) {
                    String string = cursor.getString(nameindex) + "\n" +
                    cursor.getString(phoneindex);
                    stringBldr.append(string).append("\n\n");
                    binding.textView.setText(stringBldr);
                }
                cursor.moveToNext();
            }
        }
    }
    cursor.close();
}
}
}
```

## 69.4 添加查询权限

在测试应用之前，最后一个任务是请求查询内容提供者的权限。要请求权限，请编辑 manifests -> `AndroidManifest.xml`文件并将其修改如下：

`xmlns:tools="http://schemas.android.com/tools">`

.

.

## 69.5 测试项目

在你用于测试`SQLDemo`应用的设备或模拟器上构建并运行应用，点击`Reload`按钮。应用应该查询`customers`数据库中的记录并在`TextView`上显示它们：

![image-R128QYB7.jpg](img/image-R128QYB7.jpeg)

图 69-2

## 69.6 总结

在本章中，我们创建了一个简单的应用来演示从客户端应用访问存储在内容 provider 中的数据。这涉及将提供者的内容 URI 传递给内容解析器实例的`query()`方法，并在项目清单文件中向内容 provider 请求查询权限。`query()`调用返回了一个`Cursor`对象，我们用它来遍历数据库记录。

## 70. Android Room 持久化库

Room 持久库包含在 Android 架构组件中，旨在以一种符合 Android 架构指南的方式，更容易为 Android 应用添加数据库存储支持。在前面的章节中已经涵盖了 SQLite 数据库的基础知识后，本章将探索基于 Room 的数据库管理、协同工作并在 Android 应用中实现 Room 支持的关键元素，以及这些元素在架构和编码方面是如何实现的的。在涵盖了这些主题后，接下来的两章将通过示例 Room 数据库项目将这些理论付诸实践。

## 70.1 重新回顾现代应用架构

标题为“使用 Jetpack 构建现代 Android 应用架构”的章节介绍了现代应用架构的概念，并强调了分离应用内不同责任区域的重要性。图 70-1 所示的图概述了典型 Android 应用的推荐架构：

![image-DRRS6FEQ.jpg](img/image-DRRS6FEQ.jpeg)

图 70-1

在本书之前的章节中已经详细介绍了该架构的前三个层级，现在是在 Room 持久化库背景下探索仓库和数据库架构层级了。

## 70.2 Room 数据库持久化的关键元素

在章节稍后的详细介绍之前，首先值得总结使用 Room 持久化库处理 SQLite 数据库的关键元素：

### 70.2.1 仓库 (Repository)

如之前所述，仓库模块包含了直接处理应用所用所有数据源所需的所有。这避免了 UI 控制器和`ViewModel`包含直接访问数据库或网络服务的代码。

### 70.2.2 Room 数据库

`room database`对象提供了底层 SQLite 数据库的接口。它还为仓库提供了访问数据访问对象 (`DAO`) 的权限。应用应该只有一个`room database`实例，该实例可以用于访问多个数据库表。

### 70.2.3 数据访问对象 (DAO)

`DAO`包含了仓库在 SQLite 数据库中执行操作所需的 SQL 语句。

### 70.2.4 实体 (Entities)



`entity` 是一个定义数据库表结构的类，它定义了表名、列名、数据类型，并标识哪一列为主键。除了声明表结构外，`entity` 类还包含提供这些字段的 getter 和 setter 方法。`DAO` 响应查询调用返回给仓库的数据以 `entity` 类实例的形式存在。然后调用 getter 方法提取数据。同样，当仓库需要向数据库写入新记录时，它会创建一个 `entity` 实例，通过 setter 调用配置，然后调用 `DAO` 中定义的插入方法并传递 `entity` 实例。

### 70.2.5 SQLite 数据库

SQLite 数据库负责存储和提供数据。应用代码（包括仓库）不应直接访问底层数据库。所有的数据库操作都是通过 `Room Database`、`DAOs` 和 `entities` 的组合完成的。

图 70-2 中的架构图说明了这些元素如何交互并在 Android 应用中提供基于 Room 的数据库存储：

![image-N7ECVFS.jpg](img/image-N7ECVFS.jpeg)

图 70-2

上述架构图中的编号连接可以总结如下：

1. 仓库与 `Room Database` 交互以获取实例，该实例反过来用于获取 DAO 实例的引用。
2. 仓库创建 `entity` 实例并对其进行数据配置，然后将其传递给 `DAO` 用于搜索和插入操作。
3. 仓库调用 `DAO` 方法并传递要插入的 `entity`，并在响应查询时接收 `entity` 实例。
4. 当 `DAO` 有结果要返回给仓库时，它将其封装成 `entity` 对象。
5. `DAO` 与 `Room Database` 交互以启动数据库操作并处理结果。
6. `Room Database` 处理与底层 SQLite 数据库的所有交互，提交查询并接收结果。

在涵盖了使用 Room 持久库进行数据库访问的关键元素的概述后，现在是时候详细探索实体、DAO、Room 数据库和仓库了。

每个数据库表都对应有一个实体类。该类定义了表的结构（schema），并以标准 Java 类的形式存在，其中穿插了一些特殊的 Room 注解。一个声明要存储在数据库表中数据的 Java 类示例如下：

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

按照目前的实现，上述代码声明了一个基础 Java 类，包含若干个表示数据库表字段的变量以及一组 getter 和 setter 方法。然而，该类目前还不是一个实体。要将此类变为实体并使其能够在 SQL 语句中访问，需要按照所示添加一些 Room 注解：

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

上述注解首先声明该类代表一个实体，并分配了“customers”作为表名。这是在 DAO SQL 语句中引用该表的名称：

`@Entity(tableName = "customers")`

每个数据库表都需要一列来作为主键。在这种情况下，customer id 被声明为主键。同时还添加了注解来分配一个在 SQL 查询中引用的列名，并指示该字段不能用于存储空值（null）。最后，`id` 值被配置为自动生成。这意味着系统会自动为新记录生成 `id`，以避免主键冲突：

`@PrimaryKey(autoGenerate = true)`

`@NonNull`

`@ColumnInfo(name = "customerId")`

`private int id;`

customer name 字段也分配了一个列名。但请注意，address 字段没有分配列名。这意味着 address 数据仍将存储在数据库中，但不需要在 SQL 语句中引用。如果实体中的某个字段不需要存储在数据库中，请使用 `@Ignore` 注解：

`@Ignore`

`private String myString;`

最后，修改了 `id` 变量的 setter 方法以防止尝试分配空值：

```java
public void setId(@NonNull int id) {
    this.id = id;
}
```

注解也可以包含在实体类中，以便使用称为外键（foreign keys）的关系型数据库概念来与其他实体建立关系。外键允许一个表引用另一个表的主键。例如，可以在名为 `Purchase` 的实体与我们现有的 `Customer` 实体之间建立如下关系：

```java
@Entity(foreignKeys = {@ForeignKey(entity = Customer.class,
parentColumns = "customerId",
childColumns = "buyerId",
onDelete = ForeignKey.CASCADE,
onUpdate = ForeignKey.RESTRICT})
public class Purchase {

    @PrimaryKey(autoGenerate = true)
    @ColumnInfo(name = "purchaseId")
    private int purchaseId;

    @ColumnInfo(name = "buyerId")
    private int buyerId;

}
```

注意，外键声明还指定了当父记录被删除或更新时要采取的操作。可选选项有 `CASCADE`、`NO_ACTION`、`RESTRICT`、`SET_DEFAULT` 和 `SET_NULL`。

## 70.4 数据访问对象（Data Access Objects）

数据访问对象（DAO）允许访问存储在 SQLite 数据库中的数据。DAO 被声明为标准的 Java 接口，并带有额外的注解，将特定的 SQL 语句映射到仓库随后可以调用的方法。

第一步是创建接口并使用 `@Dao` 注解将其声明为 DAO：

```java
@Dao
public interface CustomerDao {
}
```

接下来，添加包含 SQL 语句和对应方法名的条目。例如，下面的声明允许通过调用名为 `getAllCustomers()` 的方法检索 customers 表中的所有行：

```java
@Dao
public interface CustomerDao {
    @Query("SELECT * FROM customers")
    LiveData<List<Customer>> getAllCustomers();
}
```

`getAllCustomers()` 方法返回一个包含 `Customer` 对象的 `List` 对象。该 DAO 使用 `LiveData`，以便能够观察数据库的变化。参数也可以传递给方法并在 SQL 语句中引用。考虑下面的 DAO 声明，它根据名称搜索数据库记录（注意，`WHERE` 条件中的是实体类中的列名）：

```java
@Query("SELECT * FROM customers WHERE name = :customerName")
List<Customer> findCustomer(String customerName);
```

在此示例中，方法传递一个字符串值，该值通过冒号（`:`）包含在 SQL 语句中。基础插入操作如下所示使用 `@Insert` 注解声明：

```java
@Insert
void addCustomer(Customer customer);
```

这是一个便利注解，因为 Room 库可以推断传递给 `addCustomer()` 的 `Customer` 实体要插入数据库。也可以如下在事务中插入多个数据库记录：

```java
@Insert
public void insertCustomers(Customer... customers);
```

下面的 DAO 根据提供的名称删除记录：

```java
@Query("DELETE FROM customers WHERE name = :name")
void deleteCustomer(String name);
```

作为使用 `@Query` 注解执行删除的替代方案，也可以使用便利注解 `@Delete`。在以下示例中，从数据库中删除所有传递给 `deleteCustomers()` 的 `Customer` 实体：

```java
@Delete
public void deleteCustomers(Customer... customers);
```

便利注解在更新记录时提供了类似的行为：

```java
@Update
public void updateCustomers(Customer... customers);
```

这些类型的数据库操作的 DAO 方法也可以声明返回一个 `int` 值，表示受事务影响的行数，例如：

```java
@Delete
public int deleteCustomers(Customer... customers);
```

## 70.5 Room Database

Room 数据库类通过扩展 `RoomDatabase` 类创建，它是嵌入 Android 操作系统的实际 SQLite 数据库之上的层。该类负责创建并返回新的 Room 数据库实例，并提供对关联 DAO 实例的访问。

Room 库提供了数据库构建器来创建数据库实例。每个 Android 应用应该只有一个 Room 数据库实例，因此在类内部实现防御性代码以防止创建多个实例是最好的。

用于示例客户表的 Room 数据库实现如下代码列表所示：

```java
import android.content.Context;
import android.arch.persistence.room.Database;
import android.arch.persistence.room.Room;
```

```java
import android.arch.persistence.room.RoomDatabase;

@Database(entities = {Customer.class}, version = 1)

public class CustomerRoomDatabase extends RoomDatabase {

    public abstract CustomerDao customerDao();

    private static CustomerRoomDatabase INSTANCE;

    static CustomerRoomDatabase getDatabase(final Context context) {
        if (INSTANCE == null) {
            synchronized (CustomerRoomDatabase.class) {
                if (INSTANCE == null) {
                    INSTANCE = Room.databaseBuilder(
                        context.getApplicationContext(),
                        CustomerRoomDatabase.class, "customer_database")
                    .build();
                }
            }
        }
        return INSTANCE;
    }
}
```

上述示例中需要注意的重要区域包括：类声明上方的注解（声明了数据库要操作的实体）、检查类实例是否已创建的代码，以及为该实例分配的 `customer_database` 名称。

## 70.6 仓库（Repository）

仓库负责获取 `Room Database` 实例，使用该实例访问关联的 `DAOs`，然后调用 `DAO` 方法来执行数据库操作。一个为与 `Room Database` 协作设计的典型构造函数可能如下：

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

一旦仓库可以访问 `DAO`，它就可以调用数据访问方法。例如，下面的代码调用了 `getAllCustomers()` `DAO` 方法：

```java
private LiveData<Customer> allCustomers;
allCustomers = customerDao.getAllCustomers();
```

在调用 `DAO` 方法时，需要注意的是，除非该方法返回 `LiveData` 实例（该实例会在单独线程上自动运行查询），否则无法在应用的主线程上执行该操作。尝试这样做会导致应用崩溃并输出以下诊断信息：

`Cannot access database on the main thread since it may potentially lock the UI for a long period of time`

由于某些数据库事务可能需要更长时间才能完成，因此在单独线程上运行操作可以避免应用出现假死。正如在“Android Room Database and Repository Tutorial”章节中将演示的那样，这个问题可以通过使用 `Java` 线程轻松解决（有关更多信息或如何使用线程的提醒，请参阅“An Overview of Java Threads, Handlers and Executors”章节）。

## 70.7 内存数据库（In-Memory Databases）

本章概述的示例使用了位于 Android 设备持久化存储上的文件的 `SQLite` 数据库。这确保了即使在应用进程终止后数据仍然存在。

`Room` 数据库持久化库也支持内存数据库。这些数据库完全留在内存中，并在应用终止时丢失。使用内存数据库所需的唯一更改是调用 `Room Database` 类的 `Room.inMemoryDatabaseBuilder()` 方法，而不是 `Room.databaseBuilder()`。下面的代码显示了方法调用之间的区别（注意，内存数据库不需要数据库名称）：



```java
// 创建基于文件存储的数据库
INSTANCE = Room.databaseBuilder(context.getApplicationContext(),
    CustomerRoomDatabase.class, "customer_database")
    .build();

// 创建内存数据库
INSTANCE = Room.inMemoryDatabaseBuilder(context.getApplicationContext(),
    CustomerRoomDatabase.class,
    "customer_database")
    .build();
```

## 70.8 数据库检查器（Database Inspector）

Android Studio 包含 `Database Inspector` 工具窗口，允许查看、搜索和修改与运行应用关联的 `Room` 数据库，如图 70-3 所示：

![image-3M5I2TTM.jpg](img/image-3M5I2TTM.jpeg)

图 70-3

`Database Inspector` 将在“Android Room Database and Repository Tutorial”章节中介绍。

## 70.9 总结

`Android Room` 持久化库包含在 `Android Architecture Components` 中，并作为低级 `SQLite` 数据库之上的抽象层。该库的设计旨在使与数据库的操作变得更容易，同时符合 Android 架构准则。本章介绍了在 Android 应用项目中构建基于 `Room` 的数据库存储所需的相互作用的元素，包括实体、仓库、数据访问对象、注解和 `Room Database` 实例。

在涵盖了 `SQLite` 基础和 `Room` 架构之后，下一步是创建一个将这些理论付诸实践的示例应用。由于示例应用程序的用户界面需要一个基于表单的布局，下一章名为“An Android TableLayout and TableRow Tutorial”，将稍微偏离核心主题，介绍 `TableLayout` 和 `TableRow` 视图的基础。

## 71. Android TableLayout 和 TableRow 教程

在开始编写本书的下一章（“Android Room Database and Repository Tutorial”）时，最初的计划是包含为 `Room` 数据库示例应用设计用户界面布局的步骤。然而，很快发现实现用户界面的最佳方法是使用 Android `TableLayout` 和 `TableRow` 视图，而且这个主题值得作为一个独立的章节。因此，本章将专门专注于下一章要完成的数据库应用程序的用户界面设计，并在此花一些时间介绍 Android Studio 中表格布局的基本概念。

## 71.1 TableLayout 和 TableRow 布局

`TableLayout` 视图允许以行和列的形式在屏幕上组织用户界面元素。`TableLayout` 中的每一行由 `TableRow` 实例占据，而 `TableRow` 又被分为单元格，每个单元格包含一个子视图。

表格的列数由列数最多的行决定，默认情况下每列的宽度由该列中最宽的单元格定义。列可以配置为收缩或扩展（或两者兼有），使其相对于 `TableLayout` 大小。此外，单个单元格可以配置为跨越多个列。

考虑图 71-1 所示的用户界面布局：

![image-T7V3A77.jpg](img/image-T7V3A77.jpeg)

图 71-1

从布局的外观来看，很难识别使用的 `TableLayout` 结构。然而，图 71-2 中的层次结构使其变得更容易理解：

![image-W2DGCUF4.jpg](img/image-W2DGCUF4.jpeg)

图 71-2

该布局由父 `LinearLayout` 以及 `TableLayout`、`LinearLayout` 和 `RecyclerView` 组成。`TableLayout` 包含 `TableRow`，代表表格中的三行。`TableRow` 有两个子视图，每个代表列单元格的内容。`LinearLayout` 子视图包含三个 `Button` 子项。

图 71-2 所示的布局是下一章将完成所需的精确布局。因此，本章的剩余部分将使用 Android Studio 布局编辑器逐步完成此布局的设计。

## 71.2 创建 Room 数据库项目

在欢迎屏幕上选择 `New Project` 菜单选项，并在弹出的新项目对话框中选择 `Empty Views Activity` 模板，然后点击 `Next` 按钮。

在 `Name` 字段中输入 `RoomDemo` 并指定 `com.ebookfrenzy.roomdemo` 为包名。在点击 `Finish` 按钮之前，将 `Minimum API` 级别设置为 `API 26: Android 8.0 (Oreo)`，并将 `Language` 菜单更改为 `Java`。

按照第 12.8 节“迁移项目到视图绑定”（Migrating a Project to View Binding）中概述的步骤将项目迁移到视图绑定。

## 71.3 转换为 LinearLayout

在项目（Project）工具窗口中找到 `activity_main.xml` 文件（`app -> res -> layout`），并双击它以将其加载到布局编辑器（Layout Editor）工具窗口中。默认情况下，Android Studio 使用 `ConstraintLayout` 作为用户界面的根布局元素。这需要将其转换为垂直方向的 `LinearLayout`。

在设计（Design）模式下使用布局编辑器工具栏，在组件树（Component Tree）面板中找到 `ConstraintLayout` 组件，右键点击它显示图 71-3 所示的菜单，并选择 `Convert view...`（转换视图）选项：

![image-SL0RX6MN.jpg](img/image-SL0RX6MN.jpeg)

图 71-3

在弹出的对话框（图 71-4）中，在点击应用（Apply）按钮之前，选择转换为 `LinearLayout` 的选项：

![image-OLUVKMVA.jpg](img/image-OLUVKMVA.jpeg)

图 71-4

默认情况下，布局编辑器会将 `ConstraintLayout` 转换为水平 `LinearLayout`，因此在组件树窗口中选择该布局组件，参考属性（Attributes）工具窗口，并将 `orientation`（方向）属性更改为垂直：

![image-HYHVJEUS.jpg](img/image-HYHVJEUS.jpeg)

图 71-5

转换完成后，选择并删除布局中的默认 `TextView` 部件。

## 71.4 向用户界面添加 TableLayout

留在 `activity_main.xml` 文件中，并参考调色板（Palette）中的布局（Layouts）类别，拖入一个 `TableLayout` 视图将其放置在 `LinearLayout` 画布区域的顶部。

完成这些初始步骤后，布局的组件树应该类似于图 71-6 所示。

![image-UYOS44Q1.jpg](img/image-UYOS44Q1.jpeg)

图 71-6

Android Studio 自动为 `TableLayout` 添加了四个 `TableRow` 实例。由于此示例只需要三行，请选择并删除第四个 `TableRow` 实例。可以随时从调色板拖入 `TableRow` 对象并将其置于组件树工具窗口中的 `TableLayout` 条目上，向 `TableLayout` 添加更多行。

选中 `TableLayout`，使用属性工具窗口将 `layout_height` 属性更改为 `wrap_content`，并将 `layout_width` 更改为 `match_parent`。

## 71.5 配置 TableRows

从调色板的文本（Text）部分，将两个 `TextView` 对象拖动到组件树中最顶部的 `TableRow` 条目上（图 71-7）：

![image-49FRT5PA.jpg](img/image-49FRT5PA.jpeg)

图 71-7

选择屏幕布局中最左侧的 `TextView`，并在属性工具窗口中将 `text` 更改为“Product ID”。对右侧的 `TextView` 重复此步骤，将文本更改为“Not assigned”并指定 `ID` 值为 `productID`。

将另一个 `TextView` 部件拖动到组件树中的第二个 `TableRow` 条目上，并将视图上的文本更改为“Product Name”。在调色板中找到 `Plain Text`（纯文本）对象，并将其拖动到图 71-8 所示的组件树中 Product Name `TextView` 下方。接下来，从 `text` 属性中删除“Name”字符串并将 `ID` 设置为 `productName`。

![image-DOXLRSSO.jpg](img/image-DOXLRSSO.jpeg)

图 71-8

将另一个 `TextView` 和一个 `Number (Decimal)`（数字（小数））文本字段拖到第三个 `TableRow` 上，使 `TextView` 位于层次结构中 `EditText` 之上。将 `TextView` 文本更改为“Product Quantity”，并将 `EditText` 对象的 `ID` 设置为 `productQuantity`。

按住 Shift 键以选择布局中的所有部件（如下图 71-9 所示），并使用属性工具窗口将所有对象的 `textSize` 属性设置为 `18sp`：

![image-6DKRI24O.jpg](img/image-6DKRI24O.jpeg)

图 71-9

## 71.6 为布局添加按钮栏

下一步是向父 `LinearLayout` 视图添加一个 `LinearLayout (Horizontal)`（水平）视图，位置紧邻 `TableLayout` 视图下方。首先点击组件树中 `TableLayout` 条目左侧的小展开箭头，使 `TableRows` 折叠隐藏。从布局编辑器调色板的布局（Layouts）部分拖入一个 `LinearLayout (horizontal)` 实例，将其放在组件树面板中 `TableLayout` 条目的正下方，并将 `layout_height` 属性更改为 `wrap_content`：

![image-MMOXEU5J.jpg](img/image-MMOXEU5J.jpeg)

图 71-10

将三个 `Button` 对象拖入新的 `LinearLayout` 中，并为每个按钮分配内容分别为“Add”、“Find”和“Delete”的字符串资源。此类按钮栏布局中的按钮通常应以无边界样式显示。使用每个按钮的属性工具窗口将样式设置为 `Widget.AppCompat.Button.Borderless`，并将 `textColor` 属性设置为 `?attr/colorPrimary`。将按钮的 `IDs` 分别更改为 `addButton`、`findButton` 和 `deleteButton`。

![image-B7G9MQ6.jpg](img/image-B7G9MQ6.jpeg)

图 71-11

在组件树中选中新的 `LinearLayout` 视图，将 `gravity` 属性设置为 `center_horizontal`，以便按钮水平居中。在继续之前，将上述步骤添加的所有 `text` 属性提取到字符串资源中。

## 71.7 添加 RecyclerView

在组件树中，点击新添加的 `LinearLayout` 条目左侧的箭头以折叠所有子项。

从调色板的容器（Containers）部分将一个 `RecyclerView` 实例拖到组件树中，将其放置在图 71-12 所示的按钮栏下方。确保 `RecyclerView` 是父 `LinearLayout` 的直接子级，而不是按钮栏 `LinearLayout` 的子级。

![image-PAZ7PQ7.jpg](img/image-PAZ7PQ7.jpeg)

图 71-12

在布局中选中 `RecyclerView`，将视图的 `ID` 更改为 `product_recycler`，并将 `layout_height` 属性更改为 `match_parent`。

## 71.8 调整布局边距

最后只需调整一些布局设置。首先点击组件树面板中的第一个 `TableRow` 条目使其被选中。按住键盘上的 Cmd/Ctrl 键并点击第二个、第三个 `TableRow`、水平 `LinearLayout` 以及 `RecyclerView`，使所有五个项目被选中。在属性面板中，找到 `layout_margin` 属性类别，一旦找到，如图 71-14 所示将值更改为 `10dp`：

![image-KWCQPPH3.jpg](img/image-KWCQPPH3.jpeg)

图 71-14

设置边距后，用户界面应如图 71-1 所示。

## 71.9 总结

`TableLayout` 容器视图提供了行列配置视图组件的方法。虽然 `TableLayout` 视图提供了整体容器，但每行及其包含的单元是通过 `TableRow` 实例实现的。在本章中，使用 Android Studio 中的 `TableLayout` 和 `TableRow` 设计了用户界面。下一章将为该用户界面添加后台功能，使用仓库（Repository）和 Room 持久库来实现 SQLite 数据库功能。

## 72. Android Room 数据库与仓库教程

本章将结合“Android Room 持久化库”中学到的知识以及上一章创建的初始项目，提供一个详细的教程，演示如何使用 Room 持久化库实现基于 SQLite 的数据库存储。遵循 Android 架构指南，项目将使用 `ViewModel`（视图模型）和 `Repository`（仓库）。本教程将使用“Android Room 持久化库”中涵盖的所有元素，包括实体（Entity）、数据访问对象（DAO）、Room 数据库以及异步数据库查询。

## 72.1 关于 RoomDemo 项目

上一章中创建的用户界面布局是创建一个用于存储产品名称和数量的简易库存应用的第一步。完成后，该应用将提供添加、删除和搜索数据库条目的功能，同时显示当前数据库中存储的所有产品的可滚动列表。当数据库条目添加或删除时，此产品列表将自动更新。

## 72.2 修改构建配置

启动 Android Studio 并打开上一章开始的 `RoomDemo` 项目。在向项目添加任何新类之前，第一步是在构建配置中添加额外的库和插件，包括 Room 持久化库。

使用 `Project` 工具窗口，找到并编辑 `Gradle Scripts -> libs.versions.toml` 文件，如下：

```toml
[versions]
roomRuntime = "2.6.1"
fragment = "1.8.5"

[libraries]
androidx-room-compiler = { module = "androidx.room:room-compiler", version.ref = "roomRuntime" }
androidx-room-runtime = { group = "androidx.room", name = "room-runtime", version.ref = "roomRuntime" }
androidx-fragment = { group = "androidx.fragment", name = "fragment", version.ref = "fragment" }
```

点击 `Sync Now` 链接提交更改。最后，修改模块级 `build.gradle.kts` 文件（`app -> Gradle Scripts -> build.gradle.kts (Module :app)`）：

```kotlin
dependencies {
    implementation(libs.androidx.room.runtime)
    implementation(libs.androidx.fragment)
    annotationProcessor(libs.androidx.room.compiler)
}
```

## 72.3 构建实体

该项目将从创建定义数据库表模式的实体开始。实体将包含一个用于产品 ID 的整数、一个用于存储产品名称的字符串列以及另一个用于存储数量的整数值。

`productid` 列将作为主键并自动生成。表 72-1 汇总了实体的结构：

| 列名 | 数据类型 |
| :--- | :--- |
| `productid` | Integer / 主键 / 自动递增 |
| `productname` | String |
| `productquantity` | Integer |

表 72-1

在 `Project` 工具窗口中右键点击 `app -> java -> com.ebookfrenzy.roomdemo` 项，并选择 `New -> Java Class` 菜单选项，为实体添加一个类文件。在新类对话框中，将类命名为 `Product`，选择列表中的 `Class` 项，并按键盘回车键生成文件。

当 `Product.java` 文件在编辑器中打开时，对其进行修改使其内容如下：



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

该类现在有了数据库表列的变量以及对应的 getter 和 setter 方法。当然，在类被添加注解之前，它不会成为一个实体。在编辑器中保持打开类文件的情况下，添加注解和相应的导入语句：

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

这些注解声明此实体为名为 `products` 的表的实体，并为 `id` 和 `name` 变量分配了列名。`id` 列也被配置为主键并自动生成。由于在 SQL 查询中不需要引用 `quantity` 列，因此没有为 `quantity` 变量分配列名。

## 72.4 创建数据访问对象 (DAO)

定义产品实体后，下一步是创建 DAO 接口。再次参考 `Project` 工具窗口，右键点击 `app -> java -> com.ebookfrenzy.roomdemo` 项，并选择 `New -> Java Class` 菜单选项。在新类对话框中，在 `Name` 字段中输入 `ProductDao`，并如图 72-1 所示从列表中选择 `Interface`：

![image-ZGQRT7BM](img/image-ZGQRT7BM.jpeg)

图 72-1

按回车键生成新接口，并在编辑器中加载 `ProductDao.java` 文件后进行以下更改：

```java
package com.ebookfrenzy.roomdemo;

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

DAO 实现了从产品数据库中插入、查找和删除记录。插入方法传递一个 `Product` 对象，而查找和删除记录的方法传递 `String` 参数。`getAllProducts()` 方法返回包含所有记录的 `LiveData` 对象。此方法将用于保持界面中的 `RecyclerView` 产品列表与数据库同步。

## 72.5 添加 Room 数据库

在将仓库添加到项目之前的最后一个任务是实现 Room 数据库。向项目添加名为 `RoomDatabase` 的新类，这次选择 `Class` 。

文件生成后，按照“Android Room 持久化库”章节概述的步骤对其进行修改：

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
                INSTANCE = Room.databaseBuilder(context.getApplicationContext(),
                        ProductRoomDatabase.class,
                        "product_database").build();
            }
        }
        return INSTANCE;
    }
}
```

## 72.6 添加仓库

向项目添加名为 `ProductRepository` 的新类，选择 `Class` 。

仓库类将代表 ViewModel 与 Room 数据库进行交互。它必须提供使用 `DAO` 插入、删除和查询产品记录的方法。除了 `getAllProducts()` DAO 方法（该方法返回 `LiveData` 对象）外，这些数据库操作必须在主线程之外的独立线程中执行。

在 `ProductRepository.java` 文件中，添加用于将搜索结果返回给仓库线程的代码：

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
    private final MutableLiveData<List<Product>> searchResults = new MutableLiveData<>();
    private List results;
    Handler handler = new Handler(Looper.getMainLooper()) {
        @Override public void handleMessage(Message msg) {
            searchResults.setValue(results);
        }
    };
}
```

上述代码声明了一个名为 `searchResults` 的 `MutableLiveData` 变量，当异步搜索任务完成时，结果就会存储其中（在稍后的教程中，`ViewModel` 内的观察者将监控此活动数据对象）。

仓库类现在必须提供一些 `ViewModel` 可以调用的方法来启动这些操作。然而，仓库需要通过 `ProductRoomDatabase` 实例获取 `DAO` 引用才能完成任务。为 `ProductRepository` 类添加一个构造方法来执行这些任务：

```java
import android.app.Application;

public class ProductRepository {
    private final MutableLiveData<List<Product>> searchResults = new MutableLiveData<>();
    private List results;
    private final ProductDao productDao;

    public ProductRepository(Application application) {
        ProductRoomDatabase db;
        db = ProductRoomDatabase.getDatabase(application);
        productDao = db.productDao();
    }
}
```

在存储了 DAO 引用后，就可以按照以下方法添加到 `ProductRepository` 类文件中：

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
        handler.sendEmptyMessage(0);
    });
    executor.shutdown();
}
```

在插入和删除方法中，创建并使用了适当的新线程来执行相应的数据库操作。在 `findProduct()` 方法中，会向 `handler` 发送消息，指示有新结果可用。

完成仓库类还剩最后一项任务。用户界面布局中的 `RecyclerView` 必须与数据库中存储的当前产品列表同步。`ProductDao` 类已经包含一个名为 `getAllProducts()` 的方法，该方法使用 SQL 查询选择所有数据库记录并将它们封装在 `LiveData` 对象中返回。仓库需要在初始化时调用一次此方法，并将结果存储在一个可以被 `ViewModel` 观察、进而被 UI 控制器观察的 `LiveData` 对象中。一旦设置完成，每当数据库表发生变化时，UI 控制器观察者都会收到通知，`RecyclerView` 就可以更新最新的产品列表。留在 `ProductRepository.java` 文件中，在构造函数添加 `LiveData` 变量并调用 DAO 的 `getAllProducts()` 方法：

```java
import androidx.lifecycle.LiveData;

public class ProductRepository {
    private final MutableLiveData<List<Product>> searchResults = new MutableLiveData<>();
    private List results;
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

为了完成仓库，添加 `ViewModel` 可以调用的方法以获取 `allProducts` 和 `searchResults` 活动数据对象的引用：

```java
public LiveData<List<Product>> getAllProducts() {
    return allProducts;
}

public MutableLiveData<List<Product>> getSearchResults() {
    return searchResults;
}
```

## 72.7 添加 ViewModel

`ViewModel` 负责创建仓库实例，并提供方法以及 `LiveData` 对象，UI 控制器利用这些对象来保持用户界面与底层数据库同步。正如在 `ProductRepository.java` 中实现的那，仓库构造函数需要访问应用上下文以获取 Room 数据库实例。为了让应用上下文在 `ViewModel` 中可访问以便传递给仓库，`ViewModel` 需要继承 `AndroidViewModel` 而不是 `ViewModel`。

首先，在 Project 工具窗口中找到 `com.ebookfrenzy.viewmodeldemo` 条目，右键点击它并选择 `New -> Java Class` 选项。接下来，将新类命名为 `MainViewModel` 并按下回车键。最后，编辑新类文件，将类改为扩展 `AndroidViewModel` 并实现默认构造函数：

```java
package com.ebookfrenzy.roomdemo.ui.main;

import android.app.Application;
import androidx.lifecycle.AndroidViewModel;
import androidx.lifecycle.LiveData;
import androidx.lifecycle.MutableLiveData;
import com.ebookfrenzy.roomdemo.Product;
import com.ebookfrenzy.roomdemo.ProductRepository;
import java.util.List;

public class MainViewModel extends AndroidViewModel {
    final private ProductRepository repository;
    final private LiveData<List<Product>> allProducts;
    final private MutableLiveData<List<Product>> searchResults;

    public MainViewModel (Application application) {
        super(application);
        repository = new ProductRepository(application);
        allProducts = repository.getAllProducts();
        searchResults = repository.getSearchResults();
    }
}
```



构造函数创建了一个仓库实例，然后使用它来获取结果和活动数据对象的引用，以便 UI 控制器可以观察它们。现在`ViewModel`中剩下的所有工作是实现在 UI 控制器中响应按钮点击以及在设置`LiveData`对象观察者时将调用的方法：

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

## 72.8 创建产品项布局

数据库中的每个产品名称将显示在主用户界面的`RecyclerView`列表中。这需要一个包含列表每行`TextView`的布局资源文件。右键点击 Project 工具窗口中的`app -> res -> layout`条目并选择`New -> Layout Resource File`选项来添加此文件。

将文件命名为`product_list_item`，并在点击确定之前将根元素更改为垂直`LinearLayout`，以创建文件并加载到布局编辑器。在布局编辑器设计模式下，从调色板拖一个`TextView`对象到布局中，它默认会出现在布局顶部：

![image-46X8C0PY.jpg](img/image-46X8C0PY.jpeg)

图 72-2

选中布局中的`TextView`，使用属性窗口将视图 ID 设置为`product_row`，并将`layout_height`设置为`30dp`。在 Component Tree 窗口中选择`LinearLayout`项，并将`layout_height`属性设置为`wrap_content`。

## 72.9 添加 RecyclerView 适配器

正如“使用 RecyclerView 和 CardView 组件”章节中详细概述的那样，`RecyclerView`实例需要一个适配器类来提供要显示的数据。在 Project（项目）工具窗口中，右键点击`app -> java -> com.ebookfrenzy.roomdemo`项，选择`New -> Java Class`菜单来添加此类。

在对话框中，将类命名为`ProductListAdapter`，并在列表中选择`Class`，然后按下键盘回车键。将生成的`ProductListAdapter.java`类加载到编辑器后，按照如下代码实现该类：

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
extends RecyclerView.Adapter {

    private final int productItemLayout;
    private List productList;

    public ProductListAdapter(int layoutId) {
        productItemLayout = layoutId;
    }

    public void setProductList(List products) {
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

## 72.10 准备主 Activity

最后一个需要修改的组件是`MainActivity`类，它需要在`Button`视图上配置监听器，并在`ViewModel`类中的 live 数据对象配置观察者。在添加这些代码之前，必须执行一些准备工作以添加导入项和变量。

编辑`MainActivity.java`文件并进行如下修改：

```java
.
.
import androidx.lifecycle.ViewModelProvider;
.
.
public class MainActivity extends AppCompatActivity {

    private ActivityMainBinding binding;
    private MainViewModel viewModel;
    private ProductListAdapter adapter;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
.
.
        viewModel = new ViewModelProvider(this).get(MainViewModel.class);
        listenerSetup();
        observerSetup();
        recyclerSetup();
    }
.
```

在代码的不同阶段，应用程序需要清除用户界面上显示的产品信息。为了避免代码重复，请添加以下`clearFields()`方便函数：

```java
private void clearFields() {
    binding.productID.setText("");
    binding.productName.setText("");
    binding.productQuantity.setText("");
}
```

在应用程序可以构建和测试之前，需要将上述`onCreate()`方法中调用的三个设置方法添加到类中。

## 72.11 添加按钮监听器

主`fragment`的用户界面布局包含三个按钮，每个按钮在用户点击时都需要执行一个特定的任务。编辑`MainActivity.java`文件并添加`listenerSetup()`方法：

```java
.
.
import com.ebookfrenzy.roomdemo.Product;
.
.
private void listenerSetup() {
    binding.addButton.setOnClickListener(view -> {
        String name = binding.productName.getText().toString();
        String quantity = binding.productQuantity.getText().toString();
        if (!name.isEmpty() && !quantity.isEmpty()) {
            Product product = new Product(name,
                    Integer.parseInt(quantity));
            viewModel.insertProduct(product);
            clearFields();
        } else {
            binding.productID.setText("Incomplete information");
        }
    });

    binding.findButton.setOnClickListener(view ->
            viewModel.findProduct(binding.productName.getText().toString()
    )
    );

    binding.deleteButton.setOnClickListener(view -> {
        viewModel.deleteProduct(binding.productName.getText().toString());
        clearFields();
    });
}
.
.
}
```

`addButton`监听器执行了一些基础验证，以确保用户输入了产品名称和数量，并使用这些数据创建了一个新的`Product`实体对象（注意，数量字符串被转换为整数以匹配实体数据类型）。在清除字段之前，随后会调用`ViewModel.insertProduct()`方法并传入该`Product`对象。

`findButton`和`deleteButton`监听器将产品名称传递给`ViewModel.findProduct()`或`deleteProduct()`方法。

## 72.12 添加 LiveData 观察者

用户界面现在需要添加观察者，以便与`ViewModel`内部的`searchResults`和`allProducts` live 数据对象保持同步。留在`MainActivity.java`文件中，按照如下代码实现观察者设置方法：

```java
.
.
import java.util.Locale;
.
.
private void observerSetup() {
    viewModel.getAllProducts().observe(this,
            products -> adapter.setList(products));

    viewModel.getSearchResults().observe(this,
            products -> {
                if (!products.isEmpty()) {
                    binding.productID.setText(String.format(Locale.US, "%d",
                            products.get(0).getId()));
                    binding.productName.setText(products.get(0).getName());
                    binding.productQuantity.setText(String.format(Locale.US, "%d",
                            products.get(0).getQuantity()));
                } else {
                    binding.productID.setText("No Match");
                }
            });
}
```

`allProducts`观察者将当前产品列表传递给`RecyclerView`的`setList`方法。

`searchResults`观察者检查数据库是否至少找到了一个匹配结果，从列表中提取第一个匹配的`Product`对象，在必要时进行转换，并赋值给布局中的`TextView`和`EditText`。如果搜索失败，将通过显示在`TextView`上的消息通知用户。

## 72.13 初始化 RecyclerView

按照如下代码添加设置方法，以初始化和配置`RecyclerView`：



```java
import androidx.recyclerview.widget.LinearLayoutManager;

private void recyclerSetup() {
    adapter = new ProductListAdapter(R.layout.product_list_item);
    binding.productRecycler.setLayoutManager(
            new LinearLayoutManager(getContext()));
    binding.productRecycler.setAdapter(adapter);
}
```

## 72.14 测试 RoomDemo 应用

在设备或模拟器上编译并运行应用程序，添加一些产品并确保它们自动显示在`RecyclerView`中。对现有产品进行搜索，并验证产品 ID 和数量字段相应更新。最后，输入现有产品的名称，从数据库中删除它，并确认它已从`RecyclerView`产品列表中移除。

## 72.15 使用 Database Inspector

正如在“Android Room 持久库”中所概述的，可以使用`Database Inspector`工具检查与运行应用程序关联的 Room 数据库并进行细微的数据更改。在使用`RoomDemo`应用添加了一些数据库记录后，使用`View` -> `Tool Windows` -> `App Inspection`菜单选项显示`Database Inspector`工具：

在检查器窗口中，从下方图 72-3 标记为`A`的菜单中选择运行的应用：

在`Databases`面板(`B`)中，双击`products`表以查看存储在数据库中的表行。启用`Live updates`选项(`C`)，然后运行的应用程序向数据库添加更多记录。注意`Database Inspector`会实时更新表数据(`D`)以反映更改。

关闭实时更新（`Live updates`）以便使表格不再是只读状态，双击表格行的数量单元格，并在按下键盘`Enter`键之前更改值。返回运行中的应用程序并搜索该产品，以确认在检查器（`inspector`）中对数量所做的更改已保存到数据库表中。

最后，点击表格查询按钮（如下方图 72-4 所示的箭头所示）以显示新的查询标签页(`A`)，确保选中了`product_database`(`B`)，在查询文本字段中输入 SQL 语句(`C`)并点击`Run`按钮(`D`)：

![image-B0DOETXT.jpg](img/image-B0DOETXT.jpeg)

图 72-4

行列表应当更新以反映 SQL 查询(`E`)的结果。

## 72.16 总结

本章演示了如何使用`Room`持久化库在`SQLite`数据库中存储数据。完成的项目使用了`repository`（仓库）将`ViewModel`与所有数据库操作分离。它还演示了实体（`entities`）、`DAO`以及`room database`实例的创建，包括在执行某些数据库操作时对异步任务的使用。

## 73. 创建、测试和上传 Android App Bundle

一旦 Android 应用程序的开发工作完成并在广泛的 Android 设备上通过测试，下一步就是准备应用程序提交到`Google Play`。然而，在提交之前，必须对应用程序进行发布打包并使用私钥进行签名。本章将介绍获取私钥、为项目准备`Android App Bundle`以及将其上传到`Google Play`的流程。

## 73.1 发布准备流程

在本书的到目前为止，我们一直在以适用于测试和调试的模式构建应用程序项目。另一方面，通过`Google Play`向客户发布应用程序包则需要额外的步骤。第一个要求是在`release mode`（发布模式）而非`debug mode`（调试模式）中编译应用程序。其次，应用程序必须使用私钥签名，该私钥用于唯一标识你作为应用程序的开发者。最后，应用程序必须打包成`Android App Bundle`。

虽然这些任务可以在`Android Studio`环境之外完成，但正如本章其余所述，使用`Android Studio`的构建机制可以更方便地执行这些操作。不过，了解更多关于`Android App Bundles`的信息是至关重要的。

## 73.2 Android App Bundles

当用户从`Google Play`安装应用时，该应用是以`APK`文件的形式下载的。该文件包含了在用户设备上安装和运行应用所需的所有内容。在`Android Studio 3.2`引入之前，开发者使用`Android Studio`生成一个或多个`APK`文件并将它们上传到`Google Play`。支持多种设备类型、屏幕尺寸和语言需要为每个目标设备和语言创建并上传多个自定义的`APK`文件，或者生成一个包含所有不同配置资源和平台二进制的大型通用`APK`。

创建多个`APK`文件涉及大量工作，且在每次更新应用时都必须重复，这给应用发布过程带来了相当的时间开销。

通用`APK`选项虽然减轻了开发者的负担，但导致了一个完全意外的问题。通过分析应用安装指标，Google 发现安装包`APK`文件越大（导致下载时间变长和存储占用增加），应用获得的转化就越少。转化率的计算方式为在`Google Play`查看该应用后完成安装的用户占用户总数的百分比。Google 估计，`APK`文件大小每增加 6MB，应用的转化率就会下降 1%。

`Android App Bundles`解决了这些问题，允许开发者从`Android Studio`内部创建一个单一包，并让`Google Play`为每个单独的支持配置自动生成自定义的`APK`文件（这一概念称为“动态交付”，`Dynamic Delivery`）。

`Android App Bundle`是一个`ZIP`文件，包含了为应用项目内已支持的设备和语言构建`APK`文件所需的所有文件。例如，项目可能包含不同屏幕尺寸的资源和图像。当用户安装应用时，`Google Play`会接收有关设备的信息，包括显示器、处理器架构和语言。使用这些信息，将相应的预生成`APK`文件传输到用户的设备上。

`Dynamic Delivery`的另一个优点是将应用拆分为多个模块，称为“动态功能模块”（`dynamic feature modules`），每个模块包含应用内特定功能区域的代码和资源。每个动态功能模块都包含在与基础模块独立的`APK`文件中，并且在用户需要该功能时才会下载到设备上。`Dynamic Delivery`和应用包还允许创建即时动态功能模块，这些模块无需安装整个应用即可在设备上立即运行。

尽管仍然可以从`Android Studio`生成`APK`文件，但应用包现在是向`Google Play`上传应用的推荐方式。

## 73.3 注册 Google Play 开发者控制台帐户

应用程序提交过程的第一步是创建一个`Google Play Developer Console`帐户。如需，请访问`https://play.google.com/apps/publish/signup/`并按照指示完成注册过程。注意，注册需要支付一次性 25 美元的费用。一旦应用上市，Google 将保留与应用相关的所有收入的 30%。创建账户后，可以在`https://play.google.com/console`访问开发者控制台。

下一步是收集有关应用程序的信息。为了将应用推向市场，需要以下信息：

- 标题（`Title`）：应用程序的标题。
- 短描述（`Short Description`）：最多 80 字的应用描述。
- 完整描述（`Full Description`）：最多 4000 字的应用描述。
- 截图（`Screenshots`）：应用程序运行的截图（至少需要 2 张）。Google 建议提交 7 英寸或 10 英寸平板电脑的运行截图。
- 语言（`Language`）：应用程序的语言（默认是美国英语）。
- 宣传文字（`Promotional Text`）：当应用出现在 Google Play 环境内的特殊宣传功能时将使用的文本。
- 应用类型（`Application Type`）：您的应用程序被视为游戏还是应用程序。
- 类别（`Category`）：最符合您的应用程序的类别（例如：金融、健康与、教育、运动等）。
- 位置（`Locations`）：您希望应用购买的地理位置。
- 联系详情（`Contact Details`）：用户联系您以获取应用支持的方式。选项包括网站、电子邮件和电话。
- 价格与分（`Pricing & Distribution`）：有关应用程序价格及其营销销售地理位置的信息。

收集上述信息后，在`Google Play Console`中点击`Create app`按钮开始创建流程。

## 73.4 在控制台中配置应用程序

首次点击`Create app`按钮时，将显示如下图 73-1 所示的应用详情和声明屏幕：

![image-89XBZDPY.jpg](img/image-89XBZDPY.jpeg)

图 73-1

一旦应用入口已完全配置完成，点击`Create app`按钮（如上图所示）来添加应用并显示仪表板屏幕。在仪表板中，找到`Set up your app`（设置您的应用）部分并展开任务列表以配置应用商店列目：

![image-4DM6QT4J.jpg](img/image-4DM6QT4J.jpeg)
图 73-2

依次处理链接列表并为应用提供所需信息，确保在每一步中都保存更改。

## 73.5 启用 Google Play 应用签名

直到最近，Google Play 的上传仍是在 Android Studio 内部使用发布应用签名密钥进行签名，然后上传到 Google Play 控制台。虽然此选项可用，但推荐的上传方式是使用名为“Google Play 应用签名”（`Google Play App Signing`）的过程。对于新创建的应用，这涉及加入 Google Play 应用签名并生成上传密钥以在 Android Studio 中对应用包（`bundle`）进行签名。当上传 Android Studio 生成的应用包文件时，Google Play 控制台会移除上传密钥，并使用安全存储在 Play 服务器中的应用签名密钥对文件进行签名。对于现有应用，需要一些额外步骤来启用 Google Play 签名，这将在章末尾介绍。

在 Google Play 控制台中，从`All Apps`屏幕（通过左侧导航面板顶部访问）选择新添加的应用，展开`Setup`（设置）部分（图 73-3 中标记为 A），并选择`App Signing`（应用签名）选项（B）。

![image-7EMUP9.jpg](img/image-7EMUP9.jpeg)
图 73-3

点击`Create`按钮（C）加入 Google Play 签名。控制台现在准备好创建应用的第一个发布版本。然而，在此之前，下一步是在 Android Studio 中生成上传密钥。这是生成签名包过程的一部分。请保持当前 Google Play 屏幕加载状态，因为我们将在本章晚些时候返回此处。

## 73.6 创建密钥库文件

要创建密钥库文件，选择 Android Studio 中的`Build -> Generate Signed Bundle / APK…`选项，显示如图 73-4 所示的`Generate Signed Bundle or APK`对话框：

![image-PADF6JDP.jpg](img/image-PADF6JDP.jpeg)
图 73-4

在点击`Next`按钮之前，确保已选择`App Bundle`（应用包）。如果你有现有的发布密钥库文件，点击下一个屏幕上的`Choose existing…`按钮，并导航到选择该文件。如果你尚未创建密钥库文件，点击`Create new…`按钮显示`New Key Store`（新密钥库）对话框（图 73-5）。点击`Key path`字段右侧的按钮，导航到文件系统上的合适位置，为密钥库文件输入名称（例如`release.keystore.jks`）并点击`OK`按钮。

`New Key Store`对话框分为两个部分。顶部部分与密钥库文件有关。在此部分中，在`Password`（密码）和`Confirm`（确认）字段中输入强密码以保护密钥库文件。底部部分与将存储在密钥库文件中上传密钥有关。

![image-AB0NG7TQ.jpg](img/image-AB0NG7TQ.jpeg)
图 73-5

在`New Key Store`对话框的`Key`部分中，输入以下详细信息：
- 引用密钥的别名（`alias`）。可以是任何字符序列，但系统仅使用前八位。
- 用于保护密钥的足够强密码。
- 密钥有效的年数（Google 建议时长超过 25 年）。
- 此外，必须为剩余字段中的至少一个提供信息（例如，你的姓、名或组织名称）。

信息输入完成后，点击`OK`按钮创建包。

## 73.7 创建 Android 应用包

下一步是指示 Android Studio 在发布模式下构建应用包文件，并使用新创建的私钥对其进行签名。此时，`Generate Signed Bundle or APK`对话框应仍显示，且`keystore path`、`passwords`和`key alias`字段已填充信息：

![image-2ABQA3RO.jpg](img/image-2ABQA3RO.jpeg)
图 73-6

确保已启用`Export Encrypted Key`（导出加密密钥）选项，并在假设其他设置正确的情况下，点击`Next`按钮进入应用包生成屏幕（图 73-7）。在此屏幕中，检查`Destination Folder`（目标文件夹）设置，以验证生成应用包文件的位置是可接受的。如果偏于其他位置，点击文本字段右侧的按钮并导航到所需的文件系统位置。

![image-OYG1NNFJ.jpg](img/image-OYG1NNFJ.jpeg)
图 73-7

点击`Create`按钮并等待`Gradle`系统构建应用包。构建完成后，将出现一个对话框，提供在资源管理器窗口中打开包含应用包文件的文件夹或将文件加载到`APK Analyzer`的选项：

![image-OGEFL2F2.jpg](img/OGEFL2F2.jpeg)
图 73-8

此时，应用已准备好提交到 Google Play。点击`locate`链接打开文件系统浏览器窗口。文件应命名为`bundle.aab`并位于项目指定的`app/release`子目录下。

## 73.8 生成测试 APK 文件

此阶段的一个可选步骤是从应用包生成 APK 文件，并在设备或模拟器上运行它们。Google 提供了一个名为`bundletool`的命令行工具专门用于此，可以从以下 URL 下载：

`https://github.com/google/bundletool/releases`

在编写时，`bundletool`以`.jar`文件的形式提供，可以如下所示从命令行执行（注意版本号可能已发生变化）：

```bash
java -jar bundletool-all-0.9.0.jar
```

运行上述命令将列出工具中的所有选项。要从应用包生成 APK 文件，使用`build-apks`选项。文件还需要签名，以生成可在设备上安装的 APK 文件。为了实现这一点，包含`--ks`选项指定此处之前创建的密钥库路径，以及`--ks-key-alias`选项指定生成密钥时提供的别名。

最后，必须使用`--output`标志指定生成 APK 文件的文件（称为 APK Set）路径。该文件不能已存在且必须具有`.apks`文件扩展名。将这些要求结合起来得到如下命令行（允许根据操作系统路径结构进行调整）：

```bash
java -jar bundletool-all-0.9.0.jar build-apks --bundle=/tmp/MyApps/app/release/bundle.aab --output=/tmp/MyApks.apks --ks=/MyKeys/release.keystore.jks --ks-key-alias=MyReleaseKey
```

执行此命令时，在生成 APK 文件到到 APK Set 文件之前，将弹出提示请求密钥库密码。APK Set 文件是一个包含从应用包生成的所有 APK 文件的 ZIP 文件。

要在连接的设备或模拟器上安装相应的 APK 文件，请使用类似下方的命令：

```bash
java -jar bundletool-all-0.9.0.jar install-apks --apks=/tmp/MyApks.apks
```

也可以在不安装的情况下，从连接设备的 APK Set 中提取 APK 文件。此过程的第一步是按照如下方式获取连接设备的规格说明：

```bash
java -jar bundletool-all-0.9.0.jar get-device-spec --output=/tmp/device.json
```

上述命令将生成一个类似下方的 JSON 文件：

```json
{
  "supportedAbis": ["x86"],
  "supportedLocales": ["en-US"],
  "screenDensity": 420,
  "sdkVersion": 27
}
```

接下来，使用此规格文件从 APK Set 中提取匹配的 APK 文件：

```bash
java -jar bundletool-all-0.9.0.jar extract-apks --apks=/tmp/MyApks.apks --output-dir=/tmp/nexus5_apks --device-spec=/tmp/device.json
```



执行后，通过`--output-dir`标志指定的目录将包含适用于指定设备配置的正确 APK 文件。

将 Android 应用推向市场的下一步是将其提交到 Google Play 开发者控制台以便进行测试。

## 73.9 上传 App Bundle 到 Google Play 开发者控制台

返回 Google Play 控制台，在点击“创建新版本”（B）按钮之前，选择导航面板中“测试”部分的“内部测试”选项（如图 73-9 中的 A 所示）：

![image-AABJA6DW.jpg](img/image-AABJA6DW.jpeg)

图 73-9

在生成的屏幕上，点击“继续”（下方标记为 A）按钮以确认使用 Google Play 应用签名，然后将 Android Studio 生成的 bundle 文件拖放到上传投放点（B）：

![image-QL61I6YG.jpg](img/image-QL61I6YG.jpeg)

图 73-10

上传完成后，向下滚动屏幕并输入发布名称和可选的发布说明。发布名称可以是任何帮助你识别该发布版本的信息，且对用户不可见。

应用 bundle 文件上传后，Google Play 将生成所有用于测试的必要 APK 文件。一旦 APK 文件生成完毕，滚动到屏幕底部并点击“保存”按钮。保存设置后，点击“查看版本”按钮。

## 73.10 探索 App Bundle

在审核屏幕上，点击已上传 bundle 右侧的箭头，如图 73-11 所示：

![image-3HW9T1OR.jpg](img/image-3HW9T1OR.jpeg)

图 73-11

在生成的面板中，点击“探索 bundle”（Explore bundle）链接以加载应用 bundle 探路器。这提供了与应用 bundle 支持的 API 级别、屏幕布局和平台相关的摘要信息：

![image-FA03L815.jpg](img/image-FA03L815.jpeg)

图 73-12

点击“转到设备目录”（Go to device catalog）链接将显示 APK 文件支持的设备：

![image-GYMWNLAG.jpg](img/image-GYMWNLAG.jpeg)

图 73-13

目前，应用已准备好进行测试，但只有在控制台中设置了某些测试人员后才能进行发布。

## 73.11 管理测试人员

如果应用仍处于内部、Alpha 或 Beta 测试阶段，可以通过在 Google Play 控制台中选择应用、点击导航面板中的“内部测试”并如图 73-14 所示选择“测试人员”选项卡来指定授权测试人员列表：

![image-MHIWZOP0.jpg](img/image-MHIWZOP0.jpeg)

图 73-14

要添加测试人员，点击“创建电子邮件列表”（Create email list）按钮，命名列表并手动或通过上传指定测试用户的电子邮件地址。

应用 bundle 文件上传后，Google Play 将生成所有用于测试的必要 APK 文件。一旦 APK 文件生成完毕，滚动到屏幕底部并点击“保存”按钮。保存设置后，点击“查看版本”按钮。

## 73.12 发布应用进行测试

应用已准备好进行测试，但只有在控制台中设置了某些测试人员后才能进行发布。在审核屏幕上，点击已上传 bundle 右侧的箭头，如图 73-11 所示：

![image-3HW9T1OR.jpg](img/image-3HW9T1OR.jpeg)

图 73-11

在生成的面板中，点击“探索 bundle”（Explore bundle）链接以加载应用 bundle 探路器。这提供了与应用 bundle 支持的 API 级别、屏幕布局和平台相关的摘要信息：

![image-FA03L815.jpg](img/image-FA03L815.jpeg)

图 73-12

点击“转到设备目录”（Go to device catalog）链接将显示 APK 文件支持的设备：

![image-GYMWNLAG.jpg](img/image-GYMWNLAG.jpeg)

图 73-13

## 73.13 上传新 App Bundle

如果应用仍处于内部、Alpha 或 Beta 测试阶段，可以通过在 Google Play 控制台中选择应用、点击导航面板中的“内部测试”并如图 73-14 所示选择“测试人员”选项卡来指定授权测试人员列表：

![image-MHIWZOP0.jpg](img/image-MHIWZOP0.jpeg)

图 73-14

要添加测试人员，点击“创建电子邮件列表”（Create email list）按钮，命名列表并手动或上传指定测试用户的电子邮件地址。

应用 bundle 文件上传后，Google Play 将生成所有用于测试的必要 APK 文件。一旦 APK 文件生成完毕，滚动到屏幕底部并点击“保存”按钮。保存设置后，点击“查看版本”按钮。

## 73.14 分析 App Bundle

Android Studio 提供了分析应用 bundle 内容。要分析 bundle 文件，选择 Android Studio Build -> Analyze APK… 菜单，导航并选择要审核的 bundle 文件。一旦加载，工具将显示有关包原始大小和下载大小的信息，以及包结构列表，如图 73-17 所示：

![image-QINKL58D.jpg](img/image-QINKL58D.jpeg)

图 73-17

选择`classes.dex`文件将在下方面板中显示文件的类结构。在此面板中，可以深入到类方法级别探索单个类的详细信息：

![image-Y0M4BPHY.jpg](img/image-Y0M4BPHY.jpeg)

图 73-18

## 73.15 总结

当应用项目完成或准备好测试时，可以将其上传到 Google Play 控制台并发布生产、内部、Alpha 或 Beta 测试。在上传应用之前，必须在控制台中创建一个应用条目，包括有关应用的信息和用于商店的截图。生成发布 Android App Bundle 文件并使用上传密钥进行签名。一旦 bundle 文件上传，Google Play 将移除上传密钥并替换为安全存储的应用签名密钥，应用即可准备好发布。

在 Android 和 iOS 等操作系统的早期，最常见的盈利方法是在下载和安装应用时收取预付费。很快另一种盈利机会是通过在应用中嵌入广告。

Google 支持通过 Google Play In-App Billing API 和 Play Console 集成应用内购买。本章将提供应用内购买的概述，并介绍如何将应用内购买集成到你的 Android 项目中。在探索这些主题之后，下一章将引导你创建一个包含应用内购买功能的示例应用。

## 74.1 为应用内购买准备项目

在应用中构建应用内购买功能需要 Google Play 开发者控制台账号，该账号详情在之前的“创建、测试和上传 Android App Bundle”章节中介绍过。你还必须注册一个 Google 商户账户。可以通过在 Play Console 中导航到`Setup`（设置）-> `Payments profile`（付款资料）找到这些设置。请注意，商户注册并非所有国家都可用。详情信息，请参考以下页面：

[`support.google.com/googleplay/android-developer/answer/9306917`](https://support.google.com/googleplay/android-developer/answer/9306917)

随后必须将应用上传到控制台并启用应用内购买。然而，除非已将模块级`build.gradle.kts`文件添加 Google Play Billing Library，否则控制台不会为应用激活应用内购买支持：

```kotlin
dependencies {
    implementation(libs.billingclient)
}
```

一旦修改了构建文件并将应用包上传到控制台，下一步是添加供用户购买的应用内产品或订阅。

## 74.2 创建应用内产品和订阅

产品和订阅是使用 Play Console 导航面板中`Monetize`（变现）部分列出的选项创建和管理的，如下图 74-1 所示：

![image-8WAIIQPM.jpg](img/image-8WAIIQPM.jpeg)

图 74-1

每个产品或订阅都需要`ID`、`title`（标题）、`description`（描述）和`pricing`（定价）信息。购买分为消耗型（用户每次需要时都必须购买，例如游戏中的虚拟货币）、非消耗型（用户只需购买一次，例如内容访问）和基于订阅的。消耗型和非消耗型产品统称为托管产品。

订阅适用于销售需要定期续订的项目，例如访问新闻内容或应用的高级功能。在创建订阅时，基础方案指定了价格、续订周期（每月、每年等）以及订阅是否自动续订。还可以为用户提供优惠和预购订阅的选项。

## 74.3 Billing Client 初始化

你的应用与 Google Play Billing Library 之间的通信由`BillingClient`实例处理。此外，`BillingClient`包含一组可以调用以执行同步和异步结算相关活动的方法。当初始化结算客户端时，需要为它提供一个`PurchasesUpdatedListener`回调处理程序的引用。客户端将调用此处理程序来通知你的应用任何购买活动的结果。为了避免重复通知，建议每个应用只保留一个`BillingClient`实例。可以使用`newBuilder()`方法创建`BillingClient`实例，传递当前的 activity 或 fragment 上。

```java
private final PurchasesUpdatedListener purchasesUpdatedListener =
    new PurchasesUpdatedListener() {
        @Override
        public void onPurchasesUpdated(BillingResult billingResult, List purchases) {
            if (billingResult.getResponseCode() ==
                    BillingClient.BillingResponseCode.OK
                    && purchases != null) {
                // 购买成功
                for (Purchase purchase : purchases) {
                    // 处理购买
                }
            } else if (billingResult.getResponseCode() ==
                    BillingClient.BillingResponseCode.USER_CANCELED) {
                // 用户取消购买
            } else {
                //在此处处理错误
            }
        }
    };

private BillingClient billingClient = BillingClient.newBuilder(context)
        .setListener(purchasesUpdatedListener)
        .enablePendingPurchases(
            PendingPurchasesParams.newBuilder()
                .enableOneTimeProducts().build()
        )
        .build();
```

## 74.4 连接到 Google Play Billing Library

成功创建 Billing Client 后，下一步是初始化与 Google Play Billing Library 的连接。必须调用结算客户端实例的`startConnection()`方法来建立此连接。由于连接是异步执行的，必须实现`BillingClientStateListener`以接收指示连接是否成功的回调。还应该添加代码来重写`onBillingServiceDisconnected()`方法。当与 Billing Library 的连接丢失时会调用此方法，用于向用户报告问题并重试连接。

一旦设置和连接任务完成，`BillingClient`实例将调用`onBillingSetupFinished()`方法，可用它来检查客户端是否就绪：

```java
billingClient.startConnection(new BillingClientStateListener() {
    @Override
    public void onBillingSetupFinished(@NonNull BillingResult billingResult) {
        if (billingResult.getResponseCode() == BillingClient.BillingResponseCode.OK) {
            // 连接成功
        } else {
            // 连接失败
        }
    }

    @Override
    public void onBillingServiceDisconnected() {
        // 现有连接丢失
    }
});
```

## 74.5 查询可用产品

一旦结算环境初始化并准备就绪，下一步是请求可购买的产品或订阅的详情。这通过调用`BillingClient`的`queryProductDetailsAsync()`方法并传递一个经过配置的`QueryProductDetailsParams`实例来实现，该实例包含产品 ID 和类型（订阅使用`ProductType.SUBS`，托管产品使用`ProductType.INAPP`）：

```java
QueryProductDetailsParams queryProductDetailsParams =
    QueryProductDetailsParams.newBuilder()
        .setProductList(ImmutableList.of(
            QueryProductDetailsParams.Product.newBuilder()
                .setProductId("one_button_click")
                .setProductType(BillingClient.ProductType.INAPP)
                .build()))
        .build();

billingClient.queryProductDetailsAsync(queryProductDetailsParams,
    new ProductDetailsResponseListener() {
        public void onProductDetailsResponse(@NonNull BillingResult billingResult, @NonNull List productDetailsList) {
            if (!productDetailsList.isEmpty()) {
                // 处理匹配的产品列表
            } else {
                // 未找到匹配的产品
            }
        }
    });
```

`queryProductDetailsAsync()`方法传递一个`ProductDetailsResponseListener`处理程序，该处理器随后会被调用并传递包含匹配产品信息的`ProductDetail`对象列表。例如，我们可以调用这些对象的方法获取产品名称、标题、描述、价格和优惠详情。

## 74.6 启动购买流程

一旦用户查询并选择了产品或订阅，购买流程就可以启动了。我们通过调用`BillingClient`的`launchBillingFlow()`方法来实现，传递当前 activity 以及一个配置了所购项目`ProductDetail`对象的`BillingFlowParams`实例。

```java
BillingFlowParams billingFlowParams =
    BillingFlowParams.newBuilder()
        .setProductDetailsParamsList(ImmutableList.of(
            BillingFlowParams.ProductDetailsParams.newBuilder()
                .setProductDetails(productDetails)
                .build()
        ))
        .build();

billingClient.launchBillingFlow(this, billingFlowParams);
```



购买操作的成功与否将通过本章之前概述的`PurchasesUpdatedListener`回调处理程序报告。

## 74.7 完成购买

当购买成功时，`PurchasesUpdatedListener`处理器将接收一个包含每个项目`Purchase`对象的列表。你可以按照如下方式调用`Purchase`实例的`getPurchaseState()`方法来验证项目是否已购买：

```
if (purchase.getPurchaseState() == Purchase.PurchaseState.PURCHASED) {
    // 购买完成。
} else if (purchase.getPurchaseState() == Purchase.PurchaseState.PENDING) {
    // 支付仍在处理中
}
```

请注意，只有在初始化期间调用了`enablePendingPurchases()`方法，你的应用才会支持待处理购买。待处理购买将一直保持状态，直到用户完成付款流程。

当非消耗性项目的购买完成后，必须对其进行确认，以防止向用户退款。这需要项目的购买令牌（purchase token），令牌可以通过调用`Purchase`对象的`getPurchaseToken()`方法获取。该令牌用于创建`AcknowledgePurchaseParams`实例和`AcknowledgePurchaseResponseListener`处理器。托管商品购买和订阅通过如下调用`BillingClient`的`acknowledgePurchase()`方法进行确认：

```
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

对于消耗性购买，你需要在项目被消耗后通知 Google Play，以便用户可以再次购买。这需要一个包含购买令牌的配置`ConsumeParams`实例、一个`ConsumeResponseListener`以及调用结算客户端的`consumeAsync()`方法：

```
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
            // 购买消耗成功
        }
    }
};

billingClient.consumeAsync(consumeParams, listener);
```

## 74.8 查询之前的购买

在处理内应用计费时，检查用户是否已经购买了某个产品或订阅是一项常见需求。通过调用`BillingClient`实例的`queryPurchasesAsync()`方法并实现`PurchaseResponseListener`，可以生成用户之前购买特定类型项目的列表。例如，以下代码获取了所有尚未消耗的之前购买的项目列表：

```
QueryPurchasesParams queryPurchasesParams =
    QueryPurchasesParams.newBuilder()
        .setProductType(BillingClient.ProductType.INAPP)
        .build();

billingClient.queryPurchasesAsync(queryPurchasesParams,
    new PurchasesResponseListener() {
        @Override
        public void onQueryPurchasesResponse(@NonNull BillingResult billingResult,
                @NonNull List list) {
            // 处理购买列表
        }
    });
```

要获取活跃订阅的列表，请将`ProductType`值从`INAPP`更改为`SUBS`。

或者，要获取每个产品最近的购买列表，请调用`BillingClient`的`queryPurchaseHistoryAsync()`方法：

```
QueryPurchaseHistoryParams queryPurchaseHistoryParams =
    QueryPurchaseHistoryParams.newBuilder()
        .setProductType(BillingClient.ProductType.INAPP)
        .build();

billingClient.queryPurchaseHistoryAsync(queryPurchaseHistoryParams,
    new PurchaseHistoryResponseListener() {
        @Override
        public void onPurchaseHistoryResponse(@NonNull BillingResult billingResult,
                @NonNull List list) {
            // 处理购买历史
        }
    });
```

## 74.9 总结

内应用购买通过向用户出售虚拟产品和订阅，提供了一种从 Android 应用内部产生收入的方式。本章探讨了托管商品和订阅，并解释了消耗性产品和非消耗性产品之间的区别。使用 Google Play 内应用计费库为应用添加内应用购买支持。这涉及创建和初始化结算客户端，并调用其方法来执行诸如购买、列出可用产品和消耗现有购买等任务。下一章将包含一个教程，演示如何在 Android Studio 项目中添加内应用购买。

## 75. Android 内应用购买教程

在上一章中，我们探索了如何将内应用购买集成到 Android 项目中，并查看了一些在开发自己的项目时可以使用代码示例。本章将通过创建一个示例项目将这些理论付诸实践，演示如何向 Android 应用添加消耗性内应用产品。该教程还将展示如何在 Google Play 控制台中添加和管理内应用产品，并解释如何启用测试支付，以便在测试期间可以在无需花费真实资金的情况下进行购买。

## 75.1 关于内应用购买示例项目

该项目的简单概念是：在一个应用中，点击按钮之前必须购买内应用产品。该内应用产品在每次点击按钮时都会被消耗，要求用户每次想要点击按钮时都重新购买该产品。初始化时，应用将连接到应用商店，获取产品详情并显示产品名称。一旦应用确认产品可用，购买按钮将启用，点击后将执行购买流程。购买完成后，第二个按钮将启用，用户可以点击它并消耗购买。

## 75.2 创建 InAppPurchase 项目

此练习的第一步是创建一个新项目。启动 Android Studio 并在欢迎界面上选择“New Project”（新建项目）。在新项目对话框中，点击“Next”（下一步）之前选择“Empty Activity”模板。

在“Name”（名称）字段中输入`InAppPurchase`，并指定在 Google Play 生态系统中唯一标识你的应用的包名（例如`com.InAppPurchase`）。在点击“Finish”（完成）按钮之前，将“Minimum API level”（最低 API 级别）设置为 API 26: Android 8.0 (Oreo)，并将“Language”（语言）菜单设置为 Java。项目创建后，使用第 12.8 节“Migrating a Project to View Binding”中概述的步骤将项目转换为 view binding。

## 75.3 向项目添加库

在编写代码之前，必须在项目构建配置中添加一些库，包括标准的 Android 结算库。在项目的后续部分，我们还需要使用`ImmutableList`类，它是 Google Guava Core Java 库的一部分。编辑版本目录（Gradle Scripts -> libs.versions.toml）并添加以下内容：

```toml
[versions]
billing = "7.0.0"
gauvaJre = "32.0.1-jre"
gauvaAndroid = "32.0.1-android"

[libraries]
billingclient = { group = "com.android.billingclient", name = "billing", version.ref = "billing" }
guava-jre = { group = "com.google.guava", name="guava", version.ref = "gauvaJre"}
guava-android = { group = "com.google.guava", name="guava", version.ref = "gauvaAndroid"}
```

进行更改后，点击编辑器顶部的“Sync Now”（立即同步）链接，然后如下修改 Gradle Scripts -> `build.gradle.kts (Module: app)` 文件：

```kotlin
dependencies {
    implementation(libs.billingclient)
    implementation(libs.guava.jre)
    implementation(libs.guava.android)
}
```

再次点击编辑器顶部的“Sync Now”链接以提交这些更改。

## 75.4 设计用户界面

用户界面将由现有的`TextView`和两个`Buttons`组成。将`activity_main.xml`文件加载到编辑器中，将两个`Button`视图拖放到布局中，使其中一个位于`TextView`上方，另一个位于下方。选择`TextView`并将`id`属性更改为`statusText`。

点击工具栏上的`Clear all Constraints`（清除所有约束）按钮，并按住 Shift 点击所有三个视图。右键点击最顶部的`Button`视图，选择`Center -> Horizontally in Parent`（居中 -> 水父水平）菜单选项。再次重复此步骤，选择`Chains -> Create Vertical Chain`（链 -> 创建垂直链）。更改顶部按钮的`text`属性显示为“Consume Purchase”，并将`id`更改为`consumeButton`。此外，配置`onClick`属性调用名为`consumePurchase`的方法。

选择底部的按钮并重复上述步骤，将`text`设置为“Buy Product”，`id`设置为`buyButton`，并将`onClick`回调设置为`makePurchase`。完成后，布局应与图 75-1 所示一致：

![image-4CSTHC6W.jpg](img/image-4CSTHC6W.jpeg)

图 75-1

## 75.5 将应用添加到 Google Play 商店

使用“创建、测试和上传 Android App Bundle”（Creating, Testing, and Uploading an Android App Bundle）章节概述的步骤，登录`Play Console`，创建一个应用并设置一个新的内部测试轨道，包括指定测试人员的电子邮件地址。返回 Android Studio 并为项目生成签名的发布版 app bundle。一旦生成包文件，将其上传到内部测试轨道并发布进行测试。

现在应用已经在 Google Play 商店中，我们准备好为项目创建一个应用内商品了。

## 75.6 创建应用内商品

在`Play Console`中选中应用，向下滚动左侧面板中的列表直到出现`Monetize`（变现）部分。在该部分中，选择`Products`下的`In-app products`（应用内商品）选项，如图 75-2 所示：

![image-4FX361YR.jpg](img/image-4FX361YR.jpeg)

图 75-2

在`In-app products`页面，点击`Create product`（创建商品）按钮：

![image-TV7TN6IZ.jpg](img/image-TV7TN6IZ.jpeg)

图 75-3

在新商品屏幕上，在保存新商品之前输入以下信息：

• `Product ID`: `one_button_click`
• `Name`: A Button Click
• `Description`: 这是一个测试应用内商品，允许按钮被点击一次。
• `Default price`: 设置为您偏好货币的最低价格。

## 75.7 启用许可测试人员

在对应用内计费进行测试时，在不花费任何资金的情况下进行测试购买是有用的。这可以通过为内部轨道的测试人员启用许可测试来实现。许可测试人员在购买时可以使用测试付款卡，这样他们就不会被收费。

在`Play Console`中，返回主界面并选择`Setup -> License testing`（设置 -> 许可测试）选项：

![image-QI6GZHE1.jpg](img/image-QI6GZHE1.jpeg)

图 75-4

在许可测试测试中，添加为内部测试轨道添加的测试人员，将`License response`设置为`RESPOND_NORMALLY`并保存更改：

![image-QMXK040B.jpg](img/image-QMXK040B.jpeg)

图 75-5

现在应用和应用内商品已经在`Play Console`中设置好，我们可以向项目添加代码了。

## 75.8 初始化计费客户端

编辑`MainActivity.java`文件并进行以下更改以开始实现应用内购买功能：

```java
.
.
import androidx.annotation.NonNull;
import android.util.Log;
import com.android.billingclient.api.*;
.
.
public class MainActivity extends AppCompatActivity {
    private ActivityMainBinding binding;
    private BillingClient billingClient;
    private ProductDetails productDetails;
    private Purchase purchase;
    static final String TAG = "InAppPurchaseTag";

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
            .setListener(purchasesUpdatedListener)
            .enablePendingPurchases(
                PendingPurchasesParams.newBuilder()
```



`.enableOneTimeProducts().build()`

```java
billingClient.startConnection(new BillingClientStateListener() {

    @Override
    public void onBillingSetupFinished(@NonNull BillingResult billingResult) {

        if (billingResult.getResponseCode() == BillingClient.BillingResponseCode.OK) {

            Log.i(TAG, "OnBillingSetupFinish connected");

            queryProduct();

        } else {

            Log.i(TAG, "OnBillingSetupFinish failed");

        }

    }

    @Override
    public void onBillingServiceDisconnected() {

        Log.i(TAG, "OnBillingSetupFinish connection lost");

    }

});
```

当应用启动时，`onCreate()` 方法现在将调用 `billingSetup()`，它反过来创建一个新的计费客户端实例并尝试连接到 Google Play 计费库。连接尝试完成后将调用 `onBillingSetupFinished()` 监听器并指示连接尝试成功或失败的 Logcat 消息。最后，我们还实现了 `onBillingServiceDisconnected()` 回调，如果 Google Play 计费库连接丢失，该回调将被调用。

如果连接成功，将调用 `queryProduct()`。必须添加此方法以及分配给计费客户端的 `purchasesUpdatedListener`。

## 75.9 查询商品

为了确保商品可以购买，我们需要创建一个 `ProductDetailsParams` 实例，并配置在 Play Console 中指定的商品 ID，然后将其传递给客户端的 `queryDetailsAsync()` 方法。这要求我们添加 `ProductDetailsResponse()` 回调，在其中我们将检查商品是否存在、名称，并将其显示在状态 `TextView` 上。现在我们获取了商品详情，也可以安全地启用购买按钮。在 `MainActivity.java` 文件中，添加 `queryProduct()` 方法，其内容如下：

```java
import com.google.common.collect.ImmutableList;
import java.util.List;

private void queryProduct() {

    QueryProductDetailsParams queryDetailsParams = QueryProductDetailsParams.newBuilder()
        .setProductList(ImmutableList.of(
            ProductDetailsParams.newBuilder()
            .setProductId("one_button_click")
            .setProductType(BillingClient.ProductType.INAPP)
            .build()))
        .build();

    billingClient.queryProductDetailsAsync(
        queryDetailsParams,
        new ProductDetailsResponseListener() {
            public void onProductDetailsResponse(@NonNull BillingResult billingResult, @NonNull List productDetailsList) {
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

这里的很多代码非常熟悉。监听器代码检查至少有一个商品符合查询条件。然后从第一个匹配的商品中提取 `ProductDetails` 对象，将其存储在 `productDetails` 变量中，并将名称属性显示在 `TextView` 上。

需要注意的是，当我们将商品名称显示在状态 `TextView` 上时，是通过调用 `runOnUiThread()` 实现的。这是必要的，因为监听器不在主线程上运行，所以它无法安全地直接更改用户界面。`runOnUiThread()` 方法提供了一种无需使用协程在主线程执行代码的方法。

## 75.10 启动购买流程

当用户点击购买按钮时，将调用 `makePurchase()` 来启动购买流程。现在我们可以按如下方式添加此方法：

```java
public void makePurchase(View view) {

    BillingFlowParams billingFlowParams = BillingFlowParams.newBuilder()
        .setProductDetailsParamsList(
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

## 75.11 处理购买更新

购买过程的结果将通过初始化阶段分配给 `billingClient` 的 `PurchaseUpdatedListener` 报告给应用。现在按照以下方式添加此处理器：

```java
private final PurchasesUpdatedListener purchasesUpdatedListener = new PurchasesUpdatedListener() {

    @Override
    public void onPurchasesUpdated(BillingResult billingResult, List purchases) {

        if (billingResult.getResponseCode() == BillingClient.BillingResponseCode.OK && purchases != null) {

            for (Purchase purchase : purchases) {
                completePurchase(purchase);
            }

        } else if (billingResult.getResponseCode() == BillingClient.BillingResponseCode.USER_CANCELED) {

            Log.i(TAG, "onPurchasesUpdated: Purchase Canceled");

        } else {

            Log.i(TAG, "onPurchasesUpdated: Error");

        }

    }

};
```

如果用户取消购买或发生其他错误，处理器将输出日志消息。然而，成功的购买将导致调用 `completePurchase()` 方法，并向其传递当前的 `Purchase` 对象。按照下文添加此方法：

```java
private void completePurchase(Purchase item) {

    purchase = item;

    if (purchase.getPurchaseState() == Purchase.PurchaseState.PURCHASED) {

        runOnUiThread(() -> {
            binding.consumeButton.setEnabled(true);
            binding.statusText.setText("Purchase Complete");
        });

    }

}
```

该方法在验证产品确实已购买且支付仍处于挂起状态之前存储了该购买。此时，“消耗”按钮被启用，并通知用户购买成功。同时，购买按钮也被禁用，以防止用户在消耗购买之前重复购买。

## 75.12 消耗产品

现在用户可以点击“消耗”按钮了，下一步是确保产品已被消耗，这样在购买另一个按钮点击之前，只能执行一次点击。这需要我们现在编写 `consumePurchase()` 方法：

```java
public void consumePurchase(View view) {

    ConsumeParams consumeParams = ConsumeParams.newBuilder()
        .setPurchaseToken(purchase.getPurchaseToken())
        .build();

    ConsumeResponseListener listener = new ConsumeResponseListener() {

        @Override
        public void onConsumeResponse(BillingResult billingResult, @NonNull String purchaseToken) {

            if (billingResult.getResponseCode() == BillingClient.BillingResponseCode.OK) {

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

此方法创建了一个 `ConsumeParams` 实例，并配置当前购买的购买令牌（从之前在 `completePurchase()` 方法中保存的 `Purchase` 对象获取）。它被传递给 `consumePurchase()` 方法，该方法在带有 `IO` 调度器的协程中启动。如果成功消耗，将在主线程执行代码以禁用消耗按钮、启用购买按钮并更新状态文本。

## 75.13 恢复之前的购买

通过目前为止添加的代码，我们可以在单个会话中购买并消耗产品。如果我们在购买后并在消耗之前退出应用，那么购买记录在应用重启时将会丢失。我们可以通过配置 `QueryPurchasesParams` 实例来搜索未消耗的应用内产品，并将其传递给 `billingClient` 的 `queryPurchasesAsync()` 方法，同时带上一个将在结果时调用的监听器引用。按照以下方式在 `MainActivity.java` 文件中添加新函数和监听器：

```java
private void reloadPurchase() {

    QueryPurchasesParams queryPurchasesParams = QueryPurchasesParams.newBuilder()
        .setProductType(BillingClient.ProductType.INAPP)
        .build();

    billingClient.queryPurchasesAsync(queryPurchasesParams, purchasesListener);

}

private final PurchasesResponseListener purchasesListener = new PurchasesResponseListener() {

    @Override
    public void onQueryPurchasesResponse(@NonNull BillingResult billingResult, @NonNull List list) {

        if (!list.isEmpty()) {

            purchase = list.get(0);
            binding.consumeButton.setEnabled(true);

        } else {

            binding.consumeButton.setEnabled(false);

        }

    }

};
```

如果传递给监听器的购买列表不为空，则将列表中的第一个购买赋值给 `purchase` 变量并启用消耗按钮（在更完整的实现中，应该添加代码通过比较产品 ID 来检查这是正确的产品，并处理多个购买的返回）。如果没有找到购买，则消耗按钮将被禁用，直到再次进行购买。剩下的工作是在计费设置过程中按如下调用我们新的 `reloadPurchase()` 方法：

```java
private void billingSetup() {

    // ...

    if (billingResult.getResponseCode() == BillingClient.BillingResponseCode.OK) {

        Log.i(TAG, "OnBillingSetupFinish connected");
        queryProduct();
        reloadPurchase();

    } else {

        Log.i(TAG, "OnBillingSetupFinish failed");

    }

    // ...

}
```

## 75.14 测试应用

在测试应用之前，我们需要将此最新版本上传到 Play Console。由于我们已经上传了版本 1，因此需要在 `build.gradle.kts` (Module: app) 文件中增加版本号：

```kotlin
// ...

defaultConfig {

    applicationId "com.ebookfrenzy.inapppurchase"
    minSdk 26
    targetSdk 32
    versionCode 2
    versionName "2.0"

}

// ...
```



请注意，只要你保持模块级`build.gradle.kts`文件中的应用版本号不变，你现在应该能够直接在设备或模拟器上运行修改后的应用，而无需重新打包并上传到控制台。

如果没有列出测试付款卡，请确保设备用户账户已添加到许可测试人员列表中。如果应用正在实体设备上运行，请尝试在模拟器上运行。如果其他所有方法都失败了，你可以输入有效的支付方式进行测试购买，然后通过从 Play 控制台主页访问的订单管理界面来为自己退款。

## 75.16 总结

在本章中，我们创建了一个项目，演示了如何在 Android 应用中添加应用内产品。这包括在 Google Play 控制台中创建该产品，以及编写代码来初始化并连接到计费客户端、查询可用产品、以及购买和消耗产品。我们还解释了如何使用 Play 控制台添加许可测试人员，以便在测试期间无需付费即可进行购买。

## 76. 在 Android 上创建和管理溢出菜单

用户界面设计中一个书中尚未涵盖的领域是 Android 应用程序中的菜单概念。菜单提供了一种机制，用于在界面布局中的视图组件之外为用户提供额外的选择。虽然 Android 开发者可以使用几种不同的菜单系统，但本章将重点关注更常用的溢出菜单（Overflow menu）。本章将涵盖如何通过 XML 手动创建菜单，以及如何使用 Android Studio 布局编辑器工具可视化创建。

## 76.1 溢出菜单

溢出菜单（也称为选项菜单）是用户可以从设备屏幕访问的菜单，它允许开发者在应用程序用户界面之外包含其他应用程序选项。溢出菜单的位置取决于设备上运行的 Android 版本。从 Android 4.0 及更高版本开始，溢出菜单按钮位于右上角（图 76-1），由三个正方形堆叠的图标表示的操作工具栏中：

![image-8M2ZG21O.jpg](img/image-8M2ZG21O.jpeg)

图 76-1

## 76.2 创建溢出菜单

菜单中的项可以在 XML 文件中声明，然后根据需要将其填充（inflate）并显示给用户。这涉及使用`menu`元素，该元素包含每个菜单项的子元素。例如，下面的 XML 定义了一个包含两个与颜色选择相关的菜单项的菜单：

```xml
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
tools:context=".MainActivity" >

    <item
        android:id="@+id/menu_red"
        android:orderInCategory="1"
        app:showAsAction="never"
        android:title="@string/red_string"/>

    <item
        android:id="@+id/menu_green"
        android:orderInCategory="2"
        app:showAsAction="never"
        android:title="@string/green_string"/>

</menu>
```

在上面的 XML 中，`android:orderInCategory`属性决定了菜单项显示时在菜单中出现的顺序。另一方面，`app:showAsAction`属性控制了相应的项作为操作栏本身中的项出现的条件。例如，如果设置为`ifRoom`，当空间足够时，该项将出现在操作栏中。图 76-2 显示了对两个菜单项都将此属性设置为`ifRoom`的效果：

![image-1YHLACJ2.jpg](img/image-1YHLACJ2.jpeg)

图 76-2

应谨慎使用此属性，以避免操作栏过于拥挤。

默认情况下，当创建新的 Android 应用项目时，Android Studio 会创建一个菜单 XML 文件。该文件位于`app -> res -> menu`项目文件夹，并包含一个名为“Settings”的单个菜单项：

```xml
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
tools:context=".MainActivity">

    <item
        android:title="@string/action_settings"
        android:orderInCategory="100"
        app:showAsAction="never" />

</menu>
```

此菜单已配置为在应用运行时，用户在用户界面上选择溢出菜单时显示，因此只需修改这一个项以满足你的需求即可。

## 76.3 显示溢出菜单

溢出菜单是通过重写对应 Activity 的`onCreateOptionsMenu()`方法然后填充菜单的 XML 文件创建的。例如，以下代码创建了名为`menu_main`的菜单 XML 文件中包含的菜单：

```java
@Override
public boolean onCreateOptionsMenu(Menu menu) {
    getMenuInflater().inflate(R.menu.menu_main, menu);
    return true;
}
```

与菜单 XML 文件一样，Android Studio 在新创建的 Android 应用项目的主 Activity 中已经重写了此方法。如果你的 Activity 不需要溢出菜单，请删除或注释掉此方法。

## 76.4 响应菜单项选择

一旦实现了菜单，问题就随之而来：当用户选择菜单项时，应用程序如何接收通知。Activity 接收菜单选择通知需要做的一切就是重写`onOptionsItemSelected()`方法。作为此方法的参数传递的是选中菜单项的引用。然后可以调用项的`getItemId()`方法来获取 ID，并用于识别选中了哪个项。例如：

```java
@Override
public boolean onOptionsItemSelected(MenuItem item) {
    if (id == R.id.menu_red) {
        // 红色项被选中
    } else if (id == R.id.menu_green) {
        // 绿色项被选中
    } else {
        return super.onOptionsItemSelected(item);
    }
    return true;
}
```

## 76.5 创建可检查项组

除了配置独立的菜单项外，还可以创建菜单项组。这在创建可检查菜单项时特别有用，可以在任何时候选择一组项中的一个。通过使用`group`标签将菜单项分配给组。使用`android:checkableBehavior`将组声明为可检查，将其设置为`single`、`all`或`none`。下面的 XML 声明了两个菜单项组成一个组，其中可以选择一个：

```xml
xmlns:app="http://schemas.android.com/apk/res-auto"
android:checkableBehavior="single">

    <item
        android:id="@+id/menu_red"
        android:title="@string/red_string"/>

    <item
        android:id="@+id/menu_green"
        android:title="@string/green_string"/>

</group>
```

当菜单组配置为可检查时，菜单项旁边会出现一个小圆圈，如图 76-3 所示。需要注意的是，该指示器的设置和取消不会自动发生。因此，检查和取消菜单项是应用程序的责任。继续本章之前使用的颜色示例，其实现如下：

```java
@Override
public boolean onOptionsItemSelected(MenuItem item) {
    if (id == R.id.menu_red) {
        item.setChecked(!item.isChecked());
        mainLayout.setBackgroundColor(android.graphics.Color.RED);
    } else if (id == R.id.menu_green) {
        item.setChecked(!item.isChecked());
        mainLayout.setBackgroundColor(android.graphics.Color.GREEN);
    } else {
        return super.onOptionsItemSelected(item);
    }
    return true;
}
```

## 76.6 菜单与 Android Studio 菜单编辑器

Android Studio 允许通过简单将菜单资源文件加载到菜单编辑器工具中、从调色板拖放菜单元素并设置属性来可视化地设计菜单。这极大地减轻了菜单设计过程，但重要的是，仍然需要在`onOptionsItemSelected()`方法中编写代码来实现菜单行为。

要视觉可视化设计菜单，请找到菜单资源文件并双击它将其加载到`Menu Editor`工具中。例如，图 76-4 显示了在设计模式下加载到`Menu Editor`的基础 Activity 默认菜单资源文件：

![image-3GGKWCQV.jpg](img/image-3GGKWCQV.jpeg)

图 76-4

调色板（`A`）包含可以添加到设计区域（`C`）菜单中的项目。`Component Tree`（组件树）（`B`）是识别菜单层级结构的有用工具。`Attributes`（属性）面板（`D`）包含了当前选中项目的常用属性子集。

可以通过将对象拖放到布局画布上或`Component Tree`（组件树）上向菜单中添加新元素。在`Layout Editor`（布局编辑器）工具中处理菜单时，有时将项目丢弃到`Component Tree`（组件树）上会更简单，因为这可以对项目在树中的放置位置提供更大的控制。这在向组添加项目等情况下特别有用。

尽管`Menu Editor`提供了一种可视化的菜单构建方法，但底层的菜单仍然以 XML 格式存储，可以通过上方图中标记为`F`的标签页从`Design`（设计）模式切换到`Code`（代码）模式手动查看和编辑。

## 76.7 创建示例项目

要查看溢出菜单的用法，点击欢迎屏幕上的`New Project`（新建项目）按钮，并在生成的新项目对话框中，点击`Next`（下一步）按钮之前选择`Basic Views Activity`模板。

在`Name`字段中输入`MenuExample`并指定`com.ebookfrenzy.menuexample`为包名。在点击`Finish`（完成）按钮之前，将`Minimum API level`（最低 API 级别）设置为`API 26`：Android 8.0 (Oreo)，并将`Language`（语言）菜单设置为`Java`。

项目创建完成后，在`Project`工具窗口中导航到`app -> res -> layout`文件夹，双击`content_main.xml`文件将其加载到`Android Studio Menu Editor`工具中。将工具切换到`Design`（设计）模式，从`Component Tree`（组件树）面板中选择`ConstraintLayout`，并在`Attributes`（属性）面板的`ID`字段中输入`layoutView`。

## 76.8 设计菜单

在`Project`工具窗口中，找到项目的`app -> res -> menu -> menu_main.xml`文件并双击将其加载到`Layout Editor`工具中。必要时切换到`Design`（设计）模式，并选择删除 Android Studio 添加的默认`Settings`菜单项，使菜单当前为空。

从调色板中，点击并拖动菜单组对象到布局画布的标题栏上，如图 76-5 所示：

![image-WOEXJJV3.jpg](img/image-WOEXJJV3.jpeg)

图 76-5

虽然组项已添加，但它在布局中是不可见的。要验证该元素是否存在，请参考`Component Tree`（组件树）面板，该组将列为菜单的子项：

![image-4L46EP13.jpg](img/image-4L46EP13.jpeg)

图 76-6

在`Component Tree`（组件树）中选择组项，并参考`Attributes`（属性）面板，将`checkableBehavior`属性设置为`single`，这样在任何时候只能选择一个组菜单项：

![image-KAITK2WP.jpg](img/image-KAITK2WP.jpeg)

图 76-7

接下来，从调色板中拖四个`Menu Item`（菜单项）元素并将其丢到`Component Tree`（组件树）中的组元素上。选择第一个项目并使用`Attributes`（属性）面板将标题更改为“Red”，并将`ID`改为`menu_red`：

![image-VC2748N6.jpg](img/image-VC2748N6.jpeg)

图 76-8

对剩余三个菜单项重复这些步骤，将标题分别设置为“Green”、“Yellow”和“Blue”，并设置相应的 ID`menu_green`、`menu_yellow`和`menu_blue`。使用`Component Tree`（组件树）面板中菜单项右侧的警告按钮将字符串提取到资源中：

![image-EPC1JRFX.jpg](img/image-EPC1JRFX.jpeg)

图 76-9

完成这些步骤后，菜单布局应与下方图 76-10 所示：

![image-8ROIH4A2.jpg](img/image-8ROIH4A2.jpeg)

图 76-10

将`Layout Editor`（布局编辑器）工具切换到`Code`（代码）模式并检查菜单的 XML 表示，它应该与以下列表匹配：

```xml
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
tools:context="com.ebookfrenzy.menuexample.MainActivity">

android:id="@+id/menu_red" />
android:id="@+id/menu_green" />
android:id="@+id/menu_yellow" />
android:id="@+id/menu_blue" />
```

## 76.9 修改 onOptionsItemSelected() 方法

当从菜单选择项目时，应用程序 Activity 中重写的`onOptionsItemSelected()`方法将被调用。该方法的作用是识别选择了哪个项目并更改布局。找到`app -> java -> com.ebookfrenzy.menuexample -> MainActivity`文件并进行如下修改：

```java
package com.ebookfrenzy.menuexample;

.

import androidx.constraintlayout.widget.ConstraintLayout;

public class MainActivity extends AppCompatActivity {

.

.

public boolean onOptionsItemSelected(MenuItem item) {
    int id = item.getItemId();
    ConstraintLayout mainLayout = findViewById(R.id.layoutView);

    if (id == R.id.menu_red) {
        item.setChecked(!item.isChecked());
        mainLayout.setBackgroundColor(android.graphics.Color.RED);
    } else if (id == R.id.menu_green) {
        item.setChecked(!item.isChecked());
        mainLayout.setBackgroundColor(android.graphics.Color.GREEN);
    } else if (id == R.id.menu_yellow) {
        item.setChecked(!item.isChecked());
        mainLayout.setBackgroundColor(android.graphics.Color.YELLOW);
    } else if (id == R.id.menu_blue) {
        item.setChecked(!item.isChecked());
        mainLayout.setBackgroundColor(android.graphics.Color.BLUE);
    } else {
        return super.onOptionsItemSelected(item);
    }
```



```java
return true;

}
```

## 76.10 测试应用程序

在模拟器或物理设备上构建并运行应用程序。使用溢出菜单选择菜单项，并验证布局颜色发生变化。注意当前选中的颜色会在菜单中显示：

![image-HFASBMHU.jpg](img/image-HFASBMHU.jpeg)

图 76-11

## 76.11 总结

溢出菜单通过运行应用程序时顶部操作栏的最右侧访问。该菜单为应用程序提供了额外的选项位置。

菜单结构最易在 XML 文件中定义，应用程序通过重写和实现`onOptionsItemSelected()`方法来接收菜单项选择的通知。

# 77. Android Studio 主/详情教程

本章将先解释主/详情用户界面设计概念，然后详细探讨 Android Studio 包含的主/详情流程模板的元素。随后，将创建一个示例应用程序，演示修改模板以满足应用程序开发者特定需求的步骤。

## 77.1 主/详情流程

主/详情流程是一种界面设计概念，其中向用户显示项目列表（称为主列表）。当选择列表中的某项时，与该项目相关的额外信息将在详情格中呈现给用户。例如，电子邮件应用程序可能包含一个接收消息的主列表，其中包含发送者地址和消息主题。当从主列表中选择某条消息时，电子邮件正文将出现在详情格中。

在平板板尺寸的 Android 设备屏幕横屏模式下，主列表显示在屏幕左侧的狭窄垂直面板中。显示器的其余部分用于详情窗格，这种布局被称为“双窗格模式”（two-pane mode）。例如，图 77-1 显示了主列表/详情的双窗格布局，其中列出了主项目，并在详情窗格中显示了第一个项目的内容：

![image-P4GBQ0YR.jpg](img/image-P4GBQ0YR.jpeg)

图 77-1

在较小的手机尺寸 Android 设备上，主列表占据整个屏幕，而详情窗格显示在独立的屏幕上，当用户从主列表中进行选择时该屏幕就会出现。在这种模式下，详情界面包含一个用于返回主列表的操作栏（action bar）条目。例如，图 77-2 展示了在 4 英寸手机屏幕上同一项目列表的主界面和详情界面：

![image-QAWSJC73.jpg](img/image-QAWSJC73.jpeg)

图 77-2

## 77.2 创建主列表/详情流 Activity

在本章的下一节中，将详细介绍组成主列表/详情流（Primary/Detail Flow）模板的不同元素。实现此点的最佳方法是使用 Primary/Detail Views Flow 模板创建一个项目并在学习信息时使用它。该项目随后将作为章节末尾教程的基础。

从欢迎界面选择`New Project`（新建项目）选项，在出现的新项目对话框中，点击`Next`（下一步）按钮之前选择`No Activity`模板。

在`Name`字段输入`PrimaryDetailFlow`，并指定`com.ebookfrenzy.primarydetailflow`为包名。在点击`Finish`（完成）按钮之前，将`Minimum API level`（最低 API）设置为`API 26`：Android 8.0 (Oreo)，并将`Language`（语言）菜单设置为`Java`。

## 77.3 添加主列表/详情流 Activity

在 Project 工具窗口，右键点击`app` -> `java` -> `com.ebookfrenzy.primarydetailflow`项，选择`New` -> `Activity` -> `Primary/Detail Views Flow`选项。在新 Activity 对话框（图 77-3）中，点击`Finish`按钮之前，确保`Launcher Activity`（启动 Activity）复选框已启用：

![image-C9OZ5Z3R.jpg](img/image-C9OZ5Z3R.jpeg)

图 77-3

## 77.4 修改主列表/详情流模板

虽然主列表/详情流模板的结构初看起来可能令人困惑，但事实证明，对于许多主列表/详情实现需求，模板提供的大部分功能可以保持不变。

在本章的剩余部分，将修改`PrimaryDetailFlow`项目，使主列表显示网站名称列表，并将详情窗格更改为包含一个`WebView`对象而不是当前的`TextView`。当用户选择某个网站时，相应的网页随后将在详情窗格中加载并显示。

## 77.5 更改内容模型

目前示例的内由`PlaceholderContent`类文件定义。因此，首先选择`PlaceholderContent.java`文件（位于 Project 工具窗口的`app` -> `java` -> `com.ebookfrenzy.primarydetailflow` -> `placeholder`文件夹中）并查看代码。文件底部是一个名为`PlaceholderItem`的类的声明，它目前能够存储三个`String`对象，分别代表内容、详情字符串和 ID。另一方面，更新后的项目需要每个项目对象包含一个`ID`字符串、一个网站名称的字符串以及一个对应网站 URL 的字符串。为了添加这些功能，请修改`PlaceholderItem`类，使其内容如下：

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

注意，封装类`PlaceholderContent`目前包含一个`for`循环，通过多次调用名为`createPlaceholderItem()`和`makeDetails()`的方法来添加 25 个项目。这些代码大部分将不再需要，并应如下所示从类中删除：

```java
public static final Map ITEM_MAP = new HashMap();

private static final int COUNT = 25;

static {

    // 添加一些示例项目。

    for (int i = 1; i <= COUNT; i++) {

        addItem(createPlaceholderItem(i));

    }

}

private static void addItem(PlaceholderItem item) {

    ITEMS.add(item);

    ITEM_MAP.put(item.id, item);

}

private static PlaceholderItem createPlaceholderItem(int position) {

    return new PlaceholderItem(String.valueOf(position), "Item " + position, makeDetails(position));

}

private static String makeDetails(int position) {

    StringBuilder builder = new StringBuilder();

    builder.append("Details about Item: ").append(position);

    for (int i = 0; i < position; i++) {

        builder.append("\nMore details information here.");

    }

    return builder.toString();

}
```

此代码需要修改以初始化数据：

```java
public static final Map ITEM_MAP =

new HashMap();

static {

    // 添加一些示例项目。

    addItem(new PlaceholderItem("1", "Payload",

    "https://www.payloadbooks.com"));

    addItem(new PlaceholderItem("2", "Amazon",

    "https://www.amazon.com"));

    addItem(new PlaceholderItem("3", "New York Times",

    "https://www.nytimes.com"));

}
```

代码现在利用修改后的`PlaceholderItem`类来存储 ID、网站名称和 URL。

## 77.6 更改详情界面

详情界面的布局（用户从主列表中选择项目时显示的屏幕）包含在`activity_detail.xml`文件中，该文件反过来包含用于显示详情内容的`FrameContainer`实例。如果应用显示的是单窗格模式，框架容器将显示`fragment_detail.xml`中的布局，而多窗格模式将显示`fragment_detail.xml (sw600dp)`布局。

Android Studio 为`fragment_detail.xml`提供的模板布局包含一个带有`app bar`、`toolbar`、`floating action button`和`text view`的`Coordinator`布局。对于此示例，我们需要的是`WebView`，因此打开此文件并删除`item_detail_container`视图以外的所有视图。最简单的方法是在`Component Tree`中选择所有不需要的视图如下所示，然后按下键盘删除键：

![image-QAWSJC73.jpg](img/image-QAWSJC73.jpeg)

从面板板的 Widgets 部分拖入`WebView`对象并将其拖到布局画布中心，将`id`更改为`website_detail`。

接下来，编辑`fragment_detail.xml (sw600dp)`文件并删除默认的`TextView`实例，然后将`WebView`拖到布局中，再次将`id`更改为`website_detail`。这两个文件的布局现在应该像图 77-5：

![image-NVSLATZ8.jpg](img/image-NVSLATZ8.jpeg)

图 77-5

## 77.7 修改 ItemDetailFragment 类

此时，用户界面详情部分已经过修改，但相应的 Java 类仍然是为操作`TextView`对象而不是`WebView`设计。通过双击 Project 工具窗口中的`ItemDetailFragment.java`文件来加载该类的源代码。

为了加载当前选择的项目的网页 URL，只需要更改几行代码。一旦完成此更改，代码应如下：

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
```

```java
binding = FragmentItemDetailBinding.inflate(inflater, container, false);

View rootView = binding.getRoot();

mToolbarLayout = rootView.findViewById(R.id.toolbar_layout);

mTextView = binding.ItemDetail;

updateContent();

rootView.setOnDragListener(dragListener);

return rootView;

}

private void updateContent() {

    if (mItem != null) {

        binding.websiteDetail.setWebViewClient(new WebViewClient(){

            @Override

            public boolean shouldOverrideUrlLoading(

                WebView view, WebResourceRequest request) {

                return super.shouldOverrideUrlLoading(

                    view, request);

            }

        });

        binding.websiteDetail.loadUrl(mItem.website_url);

    }

}
```

在上述代码中，删除了对工具栏布局（toolbar layout）和项目详情文本元素的引用，这些元素之前从`fragment_item_detail.xml`文件中移除了。

接下来，修改`updateContent()`以访问`website_detail`视图（它之前是`TextView`，现在是`WebView`），并从所选项目中提取网站 URL。创建了`WebViewClient`类的实例并为其分配了`shouldOverrideUrlLoading()`回调方法。实现该方法是为了强制系统使用`WebView`实例加载页面，而不是使用 Chrome 浏览器。

## 77.8 修改 ItemListFragment 类

还需要对`ItemListFragment.java`文件进行细小的更改，以确保网站名称出现在主列表中。编辑此文件，找到`onBindViewHolder()`方法，并修改`setText()`方法调用，以如下方式引用网站名称：

```java
@Override

public void onBindViewHolder(final ViewHolder holder, int position) {

    holder.mIdView.setText(mValues.get(position).id);

    holder.mContentView.setText(mValues.get(position).website_name);

}

// 识别内容的 id

ClipData.Item clipItem = new ClipData.Item(mValues.get(position).id);

ClipData dragData = new ClipData(

    ((PlaceholderContent.PlaceholderItem) v.getTag()).website_name,

    new String[]{ClipDescription.MIMETYPE_TEXT_PLAIN},

    clipItem

);
```

## 77.9 添加 Manifest 权限

最后一步是通过 manifest 文件为应用程序添加互联网权限。这将允许`WebView`对象访问互联网并下载网页。导航到 Project 工具窗口中的（app -> manifests）并加载`AndroidManifest.xml`文件，然后双击它将其加载到编辑器中。加载后，向文件中添加适当的权限行：

```xml
package="com.ebookfrenzy.PrimaryDetailflow"

android:allowBackup="true"
```




## 77.10 运行应用程序

在配置适当的模拟器或已连接的 Android 设备上编译并运行应用程序。根据显示器的大小，应用程序将以小屏或双窗格模式显示。无论如何，主列表都应该预先加载内容模型中定义的三个网站的名称。选择一个项目将导致相应的网站出现在详情窗格中，如图 77-6 所示的双窗格模式插图：

![image-QPEQ9ZS5.jpg](img/image-QPEQ9ZS5.jpeg)

图 77-6

## 77.11 总结

主/详情用户界面由主项目列表组成，当选择某项时，会在详情窗格内显示关于该选择的额外信息。主/详情流（Primary/Detail Flow）是 Android Studio 提供的模板，允许快速且轻松地创建主/详情布局。正如本章所示，通过对默认模板文件进行微调，就可以以极少的代码和设计工作实现广泛基于主/详情的功能。

# 78. Android 生物识别认证教程

触摸传感器现在已内置在许多 Android 设备中，用于识别用户并提供设备和应用功能的访问权限，例如使用指纹识别的应用内支付选项。指纹识别只是多种认证方法之一，还包括密码、PIN 码以及最近的脸部识别。

尽管目前市场上只有少数 Android 设备提供面部识别，但这在未来可能会变得更加常见。考虑到这一点，Google 已经开始从以指纹为核心的添加应用认证的方法转向一种不那么具体的针对性的方法，称为生物识别认证。

本章提供了生物识别认证的概述，并提供了一个详细的、分步演示的教程，展示了在 Android 应用项目中实现生物识别认证的实用方法。

## 78.1 生物识别认证概述

关键生物识别认证组件是 `BiometricPrompt` 类。该类执行了许多在早期 Android 版本中必须通过编写代码才能完成的工作，包括显示标准对话框以引导用户通过认证过程、执行认证并将结果报告给应用。该类还处理了多次失败的认证尝试，并在用户再次尝试之前强制执行超时。

`BiometricPrompt` 类包含一个伴侣 `Builder` 类，可用于配置和创建 `BiometricPrompt` 实例，包括定义要显示在生物识别认证对话框中的文本，以及对对话框中取消按钮（也称为负向按钮）进行自定义。

`BiometricPrompt` 实例还分配了一组认证回调，这些回调将被调用以向应用提供认证操作的结果。还使用了 `CancellationSignal` 实例，以允许应用程序在认证进行期间取消认证。

在涵盖这些基础知识后，本章的剩余部分将在示例项目中实现基于指纹的生物识别。

## 78.2 创建生物识别认证项目

从欢迎界面选择 New Project 选项，并在出现的新项目对话框中选择 Empty Views 模板，然后点击 Next 按钮。

在 Name 字段中输入 `BiometricDemo`，并指定 `com.ebookfrenzy.biometricdemo` 为包名。在点击 Finish 按钮之前，将 Minimum API level 设置为 `API 29: Android (Q)` 并将 Language 菜单设置为 `Java`。

## 78.3 配置设备指纹认证

指纹认证仅适用于带有触摸传感器的设备，且已采取相应的配置步骤来保护设备并录入指纹。有关配置模拟器测试指纹认证的步骤，请参考“使用和配置 Android Studio AVD Emulator”章节。

在物理设备上配置指纹认证：打开 Settings 应用并选择 Security。在 Security 设置屏幕上，选择 Fingerprint。在启用指纹安全之前，必须配置一种备份屏幕解锁方法（如 PIN）。如果锁屏未加密，请按照步骤配置 PIN、图案或密码安全。

锁屏加密后，继续进入指纹检测屏幕，并在提示时触摸传感器（图 78-1），重复此过程以添加更多指纹。

![image-BXX6DY8M.jpg](img/image-BXX6DY8M.jpeg)

图 78-1

## 78.4 在 Manifest 文件中添加生物识别权限

生物识别认证需要应用程序在项目清单文件中请求 `USE_BIOMETRIC` 权限。在 Android Studio Project 工具窗口中，找到并编辑 `app -> manifests -> AndroidManifest.xml` 文件，按如下所示添加权限请求：

```xml
package="com.ebookfrenzy.biometricdemo">
```

```xml
android:name="android.permission.USE_BIOMETRIC" />
```

## 78.5 设计用户界面

为了保持示例尽可能简单，用户界面中唯一的视觉元素将是一个 `Button` 视图。找到并选择 `activity_main.xml` 布局资源文件，将其加载到 `Layout Editor` 工具中。

删除示例 `TextView` 对象，从调色板（palette）的 Common（常用）类别拖拽并释放一个 `Button` 对象，将其放置在布局画布的中心。使用 `Attributes` 工具窗口，将按钮的 `text` 属性更改为“Authenticate”，并将该字符串提取到资源。最后，配置 `onClick` 属性以调用名为 `authenticateUser` 的方法。

完成上述步骤后，布局应与图 78-2 所示：

![image-7CPFH8V0.jpg](img/image-7CPFH8V0.jpeg)

图 78-2

## 78.6 添加 Toast 便利方法

在本示例的代码各个处，应用程序都将设计为通过 `Toast` 消息向用户显示信息。为了避免多次重复相同的 `Toast` 代码，将在主活动中添加一个名为 `notifyUser()` 的便利方法。该方法将接受单个 `String` 值并将其作为 `Toast` 消息显示给用户。现在编辑 `MainActivity.java` 文件并添加此方法：

```java
import android.widget.Toast;

private void notifyUser(String message) {
    Toast.makeText(this, message, Toast.LENGTH_LONG).show();
}
```

## 78.7 检查安全设置

在本章前面的部分，已经采取了步骤在测试应用程序的设备或模拟器上配置锁屏并注册了指纹。然而，在应用程序中包含防御性代码以确保在尝试请求指纹识别之前已满足这些要求是非常重要的。这些步骤将在 `MainActivity.java` 文件中的 `onCreate` 方法中执行，并使用 `Keyguard` 和 `PackageManager` 管理服务。注意，还添加了代码来验证是否已为应用程序配置了 `USE_BIOMETRIC` 权限：

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
        checkBiometricSupport();
    }

    private void checkBiometricSupport() {
        KeyguardManager keyguardManager =
                (KeyguardManager) getSystemService(KEYGUARD_SERVICE);

        if (!keyguardManager.isKeyguardSecure()) {
            notifyUser("Lock screen security not enabled in Settings");
        }

        if (ActivityCompat.checkSelfPermission(
                this,
                Manifest.permission.USE_BIOMETRIC
        ) != PackageManager.PERMISSION_GRANTED) {
            notifyUser("Fingerprint authentication permission not enabled");
        }
    }
}
```

上述代码更改首先使用 `Keyguard` 管理器来验证已配置了备用屏幕解锁方法（也就是说，可以使用 PIN 或其他身份验证方法作为指纹识别的替代方案来解锁屏幕）。如果锁屏未加密，代码将向用户报告该问题并从方法返回。

然后，该方法会检查用户是否已为应用程序启用了生物识别权限，然后在使用包管理器验证设备上是否存在指纹识别之前进行检查。

## 78.8 配置身份验证回调

当配置生物识别提示对话框时，需要分配一组身份验证回调方法，可以通过这些方法来通知应用程序身份验证过程的成功或失败。这些方法需要封装在 `BiometricPrompt.AuthenticationCallback` 类实例中。在 `MainActivity.java` 文件中，添加一个方法来创建并返回该类的实例，实现相应的方法：

```java
import android.hardware.biometrics.BiometricPrompt;

private BiometricPrompt.AuthenticationCallback getAuthenticationCallback() {
    return new BiometricPrompt.AuthenticationCallback() {

        @Override
        public void onAuthenticationError(
                int errorCode,
                CharSequence errString
        ) {
            notifyUser("Authentication error: " + errString);
            super.onAuthenticationError(errorCode, errString);
        }

        @Override
        public void onAuthenticationHelp(
                int helpCode,
                CharSequence helpString
        ) {
            super.onAuthenticationHelp(helpCode, helpString);
        }

        @Override
        public void onAuthenticationFailed() {
            super.onAuthenticationFailed();
        }

        @Override
        public void onAuthenticationSucceeded(
                BiometricPrompt.AuthenticationResult result
        ) {
            notifyUser("Authentication Succeeded");
            super.onAuthenticationSucceeded(result);
        }
    };
}
```

## 78.9 添加取消信号

一旦启动，生物识别认证过程将独立于应用程序执行。为了给应用程序提供取消操作的方法，将创建一个 `CancellationSignal` 类实例并将其传递给生物识别认证过程。然后可以使用此 `CancellationSignal` 实例在需要时取消过程。取消信号实例可以配置一个监听器，监听器将在取消完成后被调用。在活动类中添加一个新方法来配置并返回 `CancellationSignal` 对象：

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

## 78.10 启动生物识别提示

剩下的只需在 `authenticateUser()` 方法中添加代码，以创建并配置 `BiometricPrompt` 实例并启动身份验证。按如下方式添加 `authenticateUser()` 方法：

```java
import android.view.View;

public void authenticateUser(View view) {
    BiometricPrompt biometricPrompt =
            new BiometricPrompt.Builder(this)
                    .setTitle("Biometric Demo")
                    .setSubtitle("Authentication is required to continue")
                    .setDescription(
                            "This app uses biometric authentication to protect your data."
                    )
                    .setNegativeButton(
                            "Cancel",
                            this.getMainExecutor(),
                            (dialogInterface, i) ->
                                    notifyUser("Authentication cancelled")
                    )
                    .build();

    biometricPrompt.authenticate(
            getCancellationSignal(),
            getMainExecutor(),
            getAuthenticationCallback()
    );
}
```




`BiometricPrompt.Builder` 类创建了一个新的 `BiometricPrompt` 实例，并配置了标题、副标题和描述文本以显示在提示对话框中。负按钮配置为显示“Cancel”文本，并在点击此按钮时配置显示消息。最后，调用 `BiometricPrompt` 实例的`authenticate()` 方法并传递 `AuthenticationCallback` 和 `CancellationSignal` 实例。生物识别提示还需要知道在哪个线程上执行身份验证。这通过传递一个配置为所需线程的 `Executor` 对象来定义。在这种情况下，使用`getMainExecutor()` 方法将主 `Executor` 对象传递给 `BiometricPrompt` 实例，以便身份验证过程在应用程序的主线程上进行。

## 78.11 测试项目

现在项目已完成，在物理 Android 设备或模拟器会话上运行应用程序并点击 Authenticate 按钮以显示 `BiometricPrompt` 对话框，如图 78-3 所示：

![image-QV6A2PQD.jpeg](img/image-QV6A2PQD.jpeg)

图 78-3

一旦运行，请触摸指纹传感器，或使用模拟器中的扩展控制面板来模拟指纹触摸，如在“使用和配置 Android Studio AVD 模拟器”章节中所述。假设检测到已注册的指纹，提示对话框将返回主活动（activity），此时将显示来自身份验证成功回调方法的 toast 消息。

再次点击身份验证（Authenticate）按钮，并使用未注册的指纹尝试身份验证。这一次，生物识别提示对话框将指示指纹未识别：

![image-5ENEY8ER.jpg](img/image-5ENEY8ER.jpeg)

图 78-4

点击生物识别提示对话框之外的区域，以验证错误处理回调是否正常。提示对话框将消失，并显示带有以下内容的 toast 消息：

身份验证错误：用户取消了指纹操作。

检查使用取消（Cancel）按钮取消提示对话框是否会触发“身份验证取消”的 toast 消息。最后，尝试使用未注册的指纹多次身份验证，并注意在多次尝试后，提示对话框将显示失败次数过多，在此之前无法进行后续尝试。

## 78.12 总结

本章概述了如何将生物识别身份验证集成到 Android 应用项目中。这涉及使用 `BiometricPrompt` 类，一旦配置了适当的消息文本和回调，该类会自动处理大部分身份验证过程。

## 79. 使用 Android 存储访问框架访问云存储

近年来，远程存储服务（称为“云存储”）被广泛用于存储用户文件和数据。驱动这一增长因素有两个关键因素。之一是大多数移动设备现在提供了持续、高速的互联网连接，从而使得数据传输快速且廉价。第二个因素是，与传统的计算机系统（如台式机和笔记本电脑）相比，这些移动设备的内部存储资源受到限制。例如，今天的高规格 Android 平板通常具有 256 GB 的存储容量。与具有 1 TB 硬盘的中端笔记本系统相比，对文件进行无缝远程存储是今天许多移动应用的关键需求。

由于这一事实，Google 在 Android 4.4 SDK 中引入了 `Storage Access Framework`（存储访问框架）。本章将提供存储访问框架的高级概述，为下一章名为“Android 存储访问框架示例”的更详细的教程做准备。

## 79.1 存储访问框架

从用户的角度来看，`Storage Access Framework` 提供了一个直观的用户界面，允许用户在 Android 内部浏览、选择、删除和创建由存储服务（也称为文档提供者）托管的文件。通过此浏览界面（也称为选择器，picker），用户可以浏览所选文档提供者托管的文件（如文档、音频、图像和视频）。例如，图 79-1 显示了选择器界面展示了由文档提供者服务托管的文件集合：

![image-BID0FM1D.jpg](img/image-BID0FM1D.jpeg)

图 79-1

文档提供者可以从云端服务到运行在与客户端应用同一设备上的本地文档提供者不等。在编写本文时，与 `Storage Access Framework` 兼容的最著名的文档提供者是 Box 以及意料之中的 Google Drive。很有可能其他云存储提供者和应用程序开发者很快也会提供符合 Android 存储访问框架的服务。

除了云端文档提供者外，选择器还提供了对设备内部存储，为应用用户提供了一系列文件存储选项。

通过一组`Intents`，Android 开发者只需几行代码即可将这些存储能力集成到应用程序中。从开发者的角度来看，`Storage Access Framework` 特别吸引人的方面是，用户选择的底层文档提供者对应用程序是完全透明的。一旦在应用程序中使用框架实现了存储功能，它将在无需修改代码的情况下与所有文档提供者协作。

## 79.2 使用存储访问框架

Android 包含一组设计用于将 `Storage Access Framework` 功能集成到 Android 应用程序中的`Intents`。这些 intent 向用户显示 `Storage Access Framework` 选择器用户界面，并通过调用启动 intent 的活动的`onActivityResult()` 方法将交互结果返回给应用程序。当`onActivityResult()` 方法被调用时，它将传递所选文件的 `Uri` 以及一个指示操作成功与否的值。

`Storage Access Framework` intent 可总结如下：

- `ACTION_OPEN_DOCUMENT` – 为用户提供选择器用户界面的访问，以便从设备上配置的文档提供者选择文件。选择的文件以 `Uri` 对象的格式返回应用程序。
- `ACTION_CREATE_DOCUMENT` – 允许用户选择文档提供者、该提供者存储上的某个位置以及新文件的文件名。一旦选择，文件将由 `Storage Access Framework` 创建，并将该文件的 `Uri` 返回应用程序以便进一步处理。

## 79.3 过滤选择器文件列表

在启动 intent 时，选择器用户界面中列出的文件可以使用各种选项进行过滤。例如，考虑以下配置 `ACTION_OPEN_DOCUMENT` intent 的代码：

```
Intent intent = new Intent(Intent.ACTION_OPEN_DOCUMENT);
```

启动时，上述 intent 将显示选择器用户界面，允许用户浏览并选择由可用文档提供者托管的任何文件。一旦用户选择了文件，应用程序将以 `Uri` 对象的形式获得该文件的引用。然后应用程序可以使用`openFileDescriptor(Uri, String)` 方法打开文件。然而，存在某些风险，并非文档提供者列出的所有文件都能通过这种方式打开。可以使用 `CATEGORY_OPENABLE` 选项修改 intent 在选择器中排除此类文件。例如：

```
Intent intent = new Intent(Intent.ACTION_OPEN_DOCUMENT);
intent.addCategory(Intent.CATEGORY_OPENABLE);
```

现在显示 intent 时，无法通过`openFileDescriptor()` 方法打开的文件将被列出但供用户选择。

另一种有效的过滤方法允许根据文件类型限制可选择的文件。这涉及指定应用程序能够处理的文件类型。例如，图像编辑应用程序可能只想为用户提供从文档提供者选择图像文件的选项。这是通过为 intent 对象配置供用户选择文件的 MIME 类型来实现的。例如，以下代码指定了只有图像文件适用于选择器中的选择：

```
intent.addCategory(Intent.CATEGORY_OPENABLE);
intent.setType("image/*");
```

这可以进一步精化，以限制仅选择 JPEG 图像：

```
intent.setType("image/jpeg");
```

或者，音频播放器应用可能只能处理音频文件：

```
intent.setType("audio/*");
```

该音频应用可能被进一步限制为仅支持播放 MP4 格式的音频文件：

```
intent.setType("audio/mp4");
```

在使用存储访问框架（Storage Access Framework）时，可以使用广泛的 MIME 类型设置，其中更常见的可以在网上找到如下列举：

https://en.wikipedia.org/wiki/Internet_media_type#List_of_common_media_types

## 79.4 处理 Intent 结果

由于我们启动的 Intent 会返回结果，因此需要使用`registerForActivityResult()` 方法（在“Android 显式 Intent – 实例示例”章节中介绍）来创建一个启动器并声明一个处理返回数据的 lambda 表达式，例如：

```java
ActivityResultLauncher startOpenForResult = registerForActivityResult(
    new ActivityResultContracts.StartActivityForResult(),
    new ActivityResultCallback() {
        @Override
        public void onActivityResult(ActivityResult result) {
            if (result.getResultCode() == Activity.RESULT_OK) {
                Intent data = result.getData();
                // 在此处从 Uri 读取文件内容
            }
        }
    }
);
```

声明完成后，可以按照以下方式配置并启动 intent：

```java
Intent intent = new Intent(Intent.ACTION_OPEN_DOCUMENT);
intent.addCategory(Intent.CATEGORY_OPENABLE);
intent.setType("text/plain");
startOpenForResult.launch(intent);
```

## 79.5 读取文件内容

读取由文档提供者托管的文件内容的具体步骤在很大程度上取决于文件的类型。例如，从文本文件中读取行的步骤与图像或音频文件的步骤不同。

通过从 `Uri` 对象中提取文件描述符，然后将图像解码为 `BitmapFactory` 实例，可以将图像文件分配给 `Bitmap` 对象。例如：

```java
ParcelFileDescriptor pFileDescriptor = getContentResolver().openFileDescriptor(uri, "r");
FileDescriptor fileDescriptor = pFileDescriptor.getFileDescriptor();
Bitmap image = BitmapFactory.decodeFileDescriptor(fileDescriptor);
pFileDescriptor.close();
myImageView.setImageBitmap(image);
```

注意，文件描述符是以`"r"`模式打开的。这表示文件将用于读取。其他选项包括用于写入访问的`"w"`以及用于读写访问的`"rwt"`，其中文件的现有内容将被新内容覆盖。

读取文本文件的内容需要稍多的工作并使用 `InputStream` 对象。例如，以下代码从文本文件中读取行：

```java
InputStream inputStream = getContentResolver().openInputStream(uri);
BufferedReader reader = new BufferedReader(new InputStreamReader(inputStream));
String readline;
while ((readline = reader.readLine()) != null) {
    // 对文件中的每一行进行操作
}
inputStream.close();
```

## 79.6 向文件写入内容

向由文档提供者托管的打开文件写入内容与读取相似，但使用的是输出流而不是输入流。例如，以下代码将文本写入指定的 `Uri` 所引的存储文件的输出流中：

```java
try {
    ParcelFileDescriptor pFileDescriptor = this.getContentResolver().openFileDescriptor(uri, "w");
    FileOutputStream fileOutputStream = new FileOutputStream(pFileDescriptor.getFileDescriptor());
    String textContent = "Some sample text";
    fileOutputStream.write(textContent.getBytes());
    fileOutputStream.close();
    pFileDescriptor.close();
} catch (FileNotFoundException e) {
    e.printStackTrace();
} catch (IOException e) {
    e.printStackTrace();
}
```

首先，从 `Uri` 中提取文件描述符，这次请求对目标文件具有写入权限。随后使用该文件描述符获取文件输出流的引用。在关闭文件描述符和输出流之前，将内容（在本例中为某些文本）写入输出流。

## 79.7 删除文件

是否可以从存储器中删除文件取决于该文件的文档提供者是否支持删除该文件。假设允许删除，可以如下所示对指定的 `Uri` 执行删除操作：

```java
if (DocumentsContract.deleteDocument(getContentResolver(), uri))
    // 删除成功
else
    // 删除失败
```

## 79.8 获取对文件的持久访问权限

当应用程序通过存储访问框架获取文件的访问时，该访问将保持有效，直到运行该应用程序的 Android 设备重启。通过“获取”`Uri` 的必要权限，可以获得对特定文件的持久访问。例如，以下代码为`fileUri` `Uri` 实例引用的文件持久化读写权限：

```java
final int takeFlags = intent.getFlags()
    & (Intent.FLAG_GRANT_READ_URI_PERMISSION | Intent.FLAG_GRANT_WRITE_URI_PERMISSION);
getContentResolver().takePersistableUriPermission(fileUri, takeFlags);
```

一旦应用程序获取了文件的权限，并且假设应用程序保存了 `Uri`，则用户应该能够在设备重启后继续访问该文件，而无需用户从选择器界面重新选择文件。

如果在任何时候不再需要这些持久化权限，可以通过调用内容解析器的`releasePersistableUriPermission()` 方法来释放它们：

```java
final int releaseFlags = intent.getFlags()
    & (Intent.FLAG_GRANT_READ_URI_PERMISSION | Intent.FLAG_GRANT_WRITE_URI_PERMISSION);
getContentResolver().releasePersistableUriPermission(fileUri, releaseFlags);
```



## 79.9 总结

考虑过去几年人们对"存储"的感知变化是非常有趣的。"存储"一词曾与大容量内置硬盘等同，但现在它同样可能指的是通过互联网连接访问的托管在远程云端的存储空间。

## 80 Android 存储访问框架示例

如前所述，存储访问框架极大简化了将云存储访问集成到 Android 应用程序的过程中。通过一个选择器用户界面和一组新的 Intent，现在可以在应用程序中构建对在提供者上存储的文件的访问。

## 80.1 关于存储访问框架示例

在本章创建的 Android 应用程序将采用原始文本编辑器的形式，旨在创建并将文本文件远程存储到云存储服务中。在实践中，该示例适用于任何兼容存储访问框架的云端文档提供者，但本示例假设使用了 Google Drive。

## 80.2 创建存储访问框架示例

在欢迎界面上选择 New Project 选项，在出现的新项目对话框中选择 Empty Views Activity 模板，然后点击 Next 按钮。

在 `Name` 字段中输入 `StorageDemo`，并指定 `com.ebookfrenzy.storagedemo` 为包名。在点击 `Finish` 按钮之前，将 `Minimum API level` 设置更改为 `API 26`：Android 8.0 (Oreo)，并将 `Language` 菜单更改为 `Java`。

按照第 12.8 节"将项目迁移到 View Binding"中的常规步骤操作，为项目添加 View Binding 支持。

## 80.3 设计用户界面

用户界面将由三个 `Button` 视图和一个 `EditText` 视图组成。在 `Project` 工具窗口中，导航到 `app -> res -> layout` 下的 `activity_main.xml` 布局文件，并双击将其加载到 `Layout Editor` 工具中。在工具的 Design（设计）模式下，选择并删除 `Hello World!` 的 `TextView` 对象。

在布局的左上角拖动并放置 `Button` 控件，以便在释放控件之前同时出现左侧和顶部的虚线边距指南。放置第二个 `Button`，使其中心和顶部边距指南出现。第三个 `Button` 控件应放置在顶部和右侧边距指南出现的位置。

将三个按钮的文本属性分别更改为"New"、"Open"和"Save"。接下来，放置一个 `Plain Text` 控件，使其水平居中并位于中心 `Button` 下方，使用户界面布局与图 80-1 所示。使用 `Layout Editor` 工具栏中的 `Infer Constraints`（推断约束）按钮添加任何缺失的约束。

选择布局中的 `Plain Text` 控件，删除当前的文本属性设置（使字段初始为空），并将 `ID` 设置为 `fileText`。接下来，将字符串属性提取为命名为 `string`、`open_string` 和 `save_string` 的资源值。

![image-UPGAFK3U.jpg](img/image-UPGAFK3U.jpeg)

图 80-1

使用 `Attributes` 工具窗口配置 `Button` 控件上的 `onClick` 属性，分别调用名为 `newFile`、`openFile` 和 `saveFile` 的方法。

## 80.4 添加 Activity 启动器

按照名为"Android 显式意图——实例示例"章节中概述的步骤，我们需要开始注册 Activity 启动器以处理文件内容的创建、打开和保存。

在 `MainActivity.java` 文件中，如下所示为三个操作中的每一个添加一个启动器：

```java
.
.
import androidx.activity.result.ActivityResult;
import androidx.activity.result.ActivityResultCallback;
import androidx.activity.result.ActivityResultLauncher;
import androidx.activity.result.contract.ActivityResultContracts;
import android.app.Activity;
import android.content.Intent;
import android.net.Uri;
import java.io.IOException;
.
.
ActivityResultLauncher startOpenForResult =
registerForActivityResult(
    new ActivityResultContracts.StartActivityForResult(),
    new ActivityResultCallback() {
        @Override
        public void onActivityResult(ActivityResult result) {
            if (result.getResultCode() == Activity.RESULT_OK) {
                Intent data = result.getData();
                if (data != null) {
                    Uri currentUri = data.getData();
                    try {
                        String content =
                            readFileContent(currentUri);
                        binding.fileText.setText(content);
                    } catch (IOException e) {
                        // Handle error here
                    }
                }
            }
        }
    }
);

ActivityResultLauncher startSaveForResult =
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
                    // Handle error here
                }
            }
        }
    }
);

ActivityResultLauncher startCreateForResult =
registerForActivityResult(
    new ActivityResultContracts.StartActivityForResult(),
    new ActivityResultCallback() {
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

## 80.5 创建新的存储文件

当选择 `New` 按钮时，应用程序需要触发一个 `ACTION_CREATE_DOCUMENT` 意图，配置为创建一个纯文本 MIME 类型的文件。在设计用户界面时，`New` 按钮被配置为调用名为 `newFile()` 的方法。在该方法内部需要启动相应的意图。

继续留在 `MainActivity.java` 文件中，如下实现该方法：

```java
package com.ebookfrenzy.storagedemo;

public class MainActivity extends AppCompatActivity {
.
.
    public void newFile(View view)
    {
        Intent intent = new Intent(Intent.ACTION_CREATE_DOCUMENT);
        intent.addCategory(Intent.CATEGORY_OPENABLE);
        intent.setType("text/plain");
        intent.putExtra(Intent.EXTRA_TITLE, "newfile.txt");
        startCreateForResult.launch(intent);
    }
.
.
}
```

此代码创建了一个新的 `ACTION_CREATE_INTENT` `Intent` 对象。该意图随后配置为仅返回可以打开的文件（通过 `Intent.CATEGORY_OPENABLE` 设置）。

接下来，代码指定要打开的文件具有纯文本 MIME 类型，并提供了一个占位文件名（用户可以在选择器界面更改它）。

当此方法执行且意图完成任务时，将调用 `startCreateForResult()` 并传递新创建文档的 `Uri`。

## 80.6 保存到存储文件

现在应用程序能够创建新的存储文件，下一步是添加将用户输入的任何文本保存到文件中。用户界面配置为在选择 Save 按钮时调用 `saveFile()` 方法。

```java
public void saveFile(View view)
{
    Intent intent = new Intent(Intent.ACTION_OPEN_DOCUMENT);
    intent.addCategory(Intent.CATEGORY_OPENABLE);
    intent.setType("text/plain");
    startSaveForResult.launch(intent);
}
```

分配给 `startSaveForResult()` 的 lambda 调用名为 `writeFileContent()` 的方法，传递要写入文件的 `Uri`。继续留在 `MainActivity.java` 文件中，现在如下实现该方法：

```java
package com.ebookfrenzy.storagedemo;

import java.io.FileOutputStream;
import android.os.ParcelFileDescriptor;

public class MainActivity extends AppCompatActivity {
.
.
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
.
.
}
```

在编写了创建和保存文本文件的代码后，最后一个任务是添加从存储器中打开和读取文件的功能。这将涉及编写 `openFile()` 点击事件处理方法并实现它，使其启动 `ACTION_OPEN_DOCUMENT` 意图：

```java
public void openFile(View view)
{
    Intent intent = new Intent(Intent.ACTION_OPEN_DOCUMENT);
    intent.addCategory(Intent.CATEGORY_OPENABLE);
    intent.setType("text/plain");
    startOpenForResult.launch(intent);
}
```

下一个任务是实现由 `startOpenForResult()` 表达式调用的 `readFileContent()` 方法：

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



该方法首先提取所选文本文件的文件描述符并将其打开读取。随后打开与 `Uri` 关联的输入流，并将其作为 `BufferedReader` 实例的输入源。

文件的每一行都被读取并存储在 `StringBuilder` 对象中。一旦读取完所有行，输入流和文件描述符都将被关闭，文件内容将作为 `String` 对象返回。

## 80.8 测试存储访问应用程序

编码阶段完成后，应用已准备好进行测试。编译并运行应用程序，点击 `New` 按钮。随后，Storage Access Framework 将显示如图 80-2 所示的下载界面：

![image-2875DUPH.jpg](img/image-2875DUPH.jpeg)

图 80-2

点击上方高亮的菜单按钮并选择 `Drive` 选项，然后选择 `My Drive`，并导航到 Google Drive 存储器上的合适位置以保存文件。在选择器界面底部的文本框中，在选择 `Save` 选项之前，将名称从“newfile.txt”更改为合适的名称（但保留 `.txt` 扩展名）。

![image-H8UNQBYQ.jpg](img/image-H8UNQBYQ.jpeg)

图 80-3

一旦文件文件，应用程序应返回主活动，通知面板中可能会出现显示为“1 file uploaded”（已上传一个文件）的通知。

![image-414HATTE.jpg](img/image-414HATTE.jpeg)

图 80-4

此时，应该可以在浏览器窗口中登录您的 Google Drive 账户，并在请求的位置找到新的文件。如果文件丢失，请确保运行应用程序的 Android 设备已连接到活跃的网络。还可以通过运行 Google Drive 应用（许多 Android 设备默认安装，并可从 Google Play 商店下载）来验证设备对 Google Drive 的访问。

现在我们已经创建了一个文件，在点击“Save”按钮之前，在文本区域输入一些文本。从选择器中选择之前创建的文本文件将内容保存到文件中。返回应用程序后，删除文本并选择“Open”按钮，再次选择您保存的文件。当控制权返回应用程序时，文本视图应该已填充文本文件的内容。

需要注意的是，如果 Android 设备缺少活跃的网络连接，Storage Access Framework 将在本地缓存存储文件。然而，一旦重新连接，任何缓存数据都将与远程存储服务同步。因此，作为应用程序的最终测试，请在浏览器窗口中登录您的 Google Drive 账户，导航到保存的文件并点击它查看内容，如果一切顺利，它应该包含应用程序保存的文本。

## 80.9 总结

本章详细介绍了如何创建一个 Android Studio 应用程序示例，该示例程序是一个非常基础的文本编辑器，旨在使用 Android Storage Access Framework 利用云端存储来创建、保存和打开文件。

# 81. 使用 `VideoView` 和 `MediaController` 类在 Android 上进行视频播放

智能手机和平板电脑的主要用途之一是提供在线内容的访问。视频是一种广泛使用的内容形式，尤其是在平板设备上。

Android SDK 包含了两个类，它们使得在开发应用程序时，在 Android 设备上实现视频播放变得极其简单。本章将提供这两个类——`VideoView` 和 `MediaController` 的概述，并创建一个视频播放应用程序。

## 81.1 介绍 Android `VideoView` 类

在 Android 中显示视频最简单的方法是使用 `VideoView` 类。当此视觉组件被添加到 Activity 的布局时，它提供了一个可以播放视频的表面。Android 目前支持以下视频格式：

- H.263
- H.264 AVC
- H.265 HEVC
- MPEG-4 SP
- VP8
- VP9

`VideoView` 类具有许多可以调用的方法来管理视频播放。一些较常用的方法如下：

- `setVideoPath(String path)` – 指定要播放的视频媒体路径（字符串格式）。这可以是远程视频 URL，也可以是设备本地视频文件。
- `setVideoUri(Uri uri)` – 执行与 `setVideoPath()` 方法的任务，但接收的是 `Uri` 对象而不是字符串。
- `start()` – 开始视频播放。
- `stopPlayback()` – 停止视频播放。
- `pause()` – 暂停视频播放。
- `isPlaying()` – 返回布尔值，指示视频是否正在播放。
- `setOnPreparedListener(MediaPlayer.OnPreparedListener)` – 在视频准备就绪时调用回调方法。
- `setOnErrorListener(MediaPlayer.OnErrorListener)` – 在视频播放期间发生错误时调用回调方法。
- `setOnCompletionListener(MediaPlayer.OnCompletionListener)` – 在视频结束时调用回调方法。
- `getDuration()` – 返回视频持续时间。除非从 `OnPreparedListener()` 回调方法调用，否则通常返回 `-1`。
- `getCurrentPosition()` – 返回指示当前播放位置的整数。
- `setMediaController(MediaController)` – 指定允许显示播放控件的 `MediaController` 实例。

## 81.2 介绍 Android `MediaController` 类

如果使用 `VideoView` 类播放视频，用户将无法控制播放，播放将一直运行到视频结束。通过为 `VideoView` 实例附加 `MediaController` 类的实例可以解决这个问题。`MediaController` 将提供一组控件，允许用户管理播放（例如暂停并在视频时间轴上向前/后移动）。

控件的位置通过将实例锚定用户界面布局中的特定视图来指定。一旦附加并锚定，控件在播放开始时会短暂出现，随后用户可以通过点击锚定实例的视图来随时恢复控件。

该类的一些关键方法如下：

- `setAnchorView(View view)` – 指定将控制器锚定的视图。这决定了控件在屏幕上的位置。
- `show()` – 显示控件。
- `show(int timeout)` – 控件在指定的时长（毫秒）内显示。
- `hide()` – 向用户隐藏控制器。
- `isShowing()` – 返回一个布尔值，表示控件当前是否对用户可见。

## 81.3 创建视频回放示例

本章的剩余部分将创建一个应用程序，该程序使用 `VideoView` 和 `MediaController` 类来播放 MPEG-4 视频文件。

从欢迎界面选择 `New Project`（新建项目）选项，在出现的新项目对话框中，点击 `Next` 按钮之前选择 `Empty Views Activity` 模板。

在 `Name` 字段中输入 `VideoPlayer`，并指定 `com.ebookfrenzy.videoplayer` 为包名。在点击 `Finish` 按钮之前，将 `Minimum API level` 设置为 `API 33: Android 13 (Tiramisu)`，并将 `Language` 菜单更改为 `Java`。参考第 12.8 节 `Migrating a Project to View Binding` 中的步骤为该项目启用视图绑定。

## 81.4 设计 `VideoPlayer` 布局

主 Activity 的用户界面将仅由 `VideoView` 类的实例组成。使用 `Project` 工具窗口找到 `app -> res -> layout -> activity_main.xml` 文件，双击它，将 `Layout Editor` 工具切换到 `Design` 模式，并删除默认的 `TextView` 小部件。

从 `Palette` 面板的 `Widgets` 类别中，将 `VideoView` 实例拖放到布局中以填充可用画布区域，如图 81-1 所示。使用 `Attributes` 面板，将 `layout_width` 和 `layout_height` 属性分别更改为 `match_constraint` 和 `wrap_content`。此外，移除连接 `VideoView` 底部与父 `ConstraintLayout` 底部的约束。最后，将组件的 `ID` 改为 `videoView1`。

![image-MT1V4MV2.jpg](img/image-MT1V4MV2.jpeg)

图 81-1

## 81.5 下载视频文件

`VideoPlayer` 应用将播放的视频是用 MPEG-4 格式编码的短动画电影片段。使用网络浏览器导航到以下 URL 播放视频：

[`www.ebookfrenzy.com/android_book/demo.mp4`](https://www.ebookfrenzy.com/android_book/demo.mp4)

在浏览器窗口中，右键点击视频播放，选择保存或下载视频到本地文件的选项，并选择一个合适的临时文件系统位置，将文件命名为 `demo.mp4`。

在 Android Studio 中，在 `Project` 工具窗口中找到 `res` 文件夹，右键点击它，选择 `New -> Directory` 菜单选项，并在 `name` 字段中输入 `raw`，然后按 `Return` 键。使用操作系统的文件导航器找到上述下载的 `demo.mp4` 文件并复制。返回 Android Studio，右键点击新创建的 `raw` 目录并选择 `Paste`，将视频文件复制到项目中。添加完成后，`raw` 文件夹在 `Project` 工具窗口中应与图 81-2 一致：

![image-F2YLKAS9.jpg](img/image-F2YLKAS9.jpeg)

图 81-2

## 81.6 配置 `VideoView`

下一步是为 `VideoView` 配置要播放的视频路径然后启动播放。这将在主 Activity 初始化时执行，因此将 `MainActivity.java` 文件加载到编辑器中，并按照以下列表概述进行修改：

```java
package com.ebookfrenzy.videoplayer;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

import android.net.Uri;

.

.

public class MainActivity extends AppCompatActivity {

    private ActivityMainBinding binding;

    @Override

    protected void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);

        .

.

        configureVideoView();

    }

    private void configureVideoView() {

        binding.videoView1.setVideoURI(Uri.parse("android.resource://"

        + getPackageName() + "/" + R.raw.demo));

        binding.videoView1.start();

    }

}
```

此代码获取布局中 `VideoView` 实例引用，为其分配一个指向 `raw` 资源目录中电影文件的 `URI` 对象，然后开始播放视频。

通过在模拟器或物理 Android 设备上运行来测试应用程序。应用程序启动后，在视频开始播放之前，视频内容缓冲可能会有短暂延迟（图 81-3）。

![image-AMAKV93D.jpg](img/image-AMAKV93D.jpeg)

图 81-3

这展示了将视频回放集成到 Android 应用中有多简单。此示例中的所有内容都是通过一个 `VideoView` 实例三行代码实现的。

## 81.7 在 `VideoView` 中添加 `MediaController`

目前 `VideoPlayer` 应用的状态是，用户没有办法控制播放。如前所述，可以使用 `MediaController` 类来实现。要为 `VideoView` 添加计数器，请再次修改 `configureVideoView()` 方法：

```java
package com.ebookfrenzy.videoplayer;

.

.

import android.widget.MediaController;

public class MainActivity extends AppCompatActivity {

    private ActivityMainBinding binding;

    private MediaController mediaController;

    private void.privateViewView() {

        ..videoView1.set.URI(..parse("..resource.

        + getPackageName() + "/" + R.raw..));

        binding.videoView1.start();

    }

}
```

这段代码获取了布局中 `VideoView` 实例的引用，为其分配了一个指向 `raw` 资源目录中电影文件的 `URI` 对象，然后开始视频播放。

（注：此处原文提供的代码块似乎存在格式混乱或重复，已根据上下文逻辑保持翻译一致性）

**更正：根据上下文逻辑，此处的代码块逻辑应为：**

```java
package com.ebookfrenzy.videoplayer;

.

.

import android.widget.MediaController;

public class MainActivity extends AppCompatActivity {

    private ActivityMainBinding binding;

    private MediaController mediaController;

    ..

    private void configureVideoView() {

        binding.videoView1.setVideoURI(Uri.parse("android.resource://"

        + getPackageName() + "/" + R.raw.demo));

        mediaController = new MediaController(this);

        mediaController.setAnchorView(binding.videoView1);

        binding.videoView1.start();

    }

}
```

当应用了这些更改后，点击 `VideoView` 画布将媒体控件出现在视频播放上。这些控件包括进度条以及快进、倒退和播放/暂停按钮。在控件消失后，可以随时通过点击 `VideoView` 画布恢复它们。如图 81-4 所示：

![image-AMAKV93D.jpg](img/image-AMAKV93D.jpeg)

图 81-4

## 81.8 设置 `onPreparedListener`

作为处理视频媒体的最后一个示例，将进一步扩展 Activity 以演示配置监听器。在这种情况下，将实现一个监听器，用于在 Android Studio Logcat 中输出视频时长。该监听器还将配置视频循环播放：

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

        MediaController mediaController = new MediaController(this);

        mediaController.setAnchorView(binding.videoView1);

        binding.videoView1.setMediaController(mediaController);

        binding.videoView.start();

        binding.videoView1.setOnPreparedListener(mp -> {

            mp.setLooping(true);

            Log.i(TAG, "Duration = " +

            binding.videoView1.getDuration());

        });

    }

}
```



现在在视频开始播放之前，Android Studio Logcat 面板将出现一条如下所示的消息，并且视频在结束后将重启：

`2023-06-27 09:25:41.313 3050-3050 VideoPlayer com.ebookfrenzy.videoplayer I Duration = 25365`

## 81.9 总结

Android 设备是交付内容的极佳平台，特别是视频媒体形式。如本章所述，Android SDK 提供了两个类，即 `VideoView` 和 `MediaController`，它们结合使得将视频回放集成到 Android 应用中变得快速简单，通常只需要几行 Java 代码。

在之前的章节介绍 Android 多任务处理时，曾简要提到了画中画（Picture-in-picture，PiP）模式，但没有进行详细介绍。画中画模式主要为视频播放设计，允许 activity 屏幕缩小并放置在屏幕的任何位置。在此状态下，activity 继续运行，且无论设备上运行着任何其他活动，窗口都保持可见。这允许用户在执行检查电子邮件或处理电子表格等任务的同时，继续观看视频播放。

本章将对画中画模式进行概述，并在下一章中为 `VideoPlayer` 项目添加对画中画的支持。

## 82.1 画中画功能

正如本章稍后部分解释以及下一章演示的那样，activity 是通过运行中的应用内部调用 API 进入 PiP 模式的。进入 PiP 模式后，可以指定配置选项来控制 PiP 窗口的宽高比，并定义包含在内的 activity 屏幕区域。例如，图 82-1 显示了画中画模式下的视频播放 activity：

![image-70YPWPEJ.jpg](img/image-70YPWPEJ.jpeg)

图 82-1

图 82-2 显示了用户点击窗口后的 PiP 模式窗口。在此模式下，窗口看起来更大，并在中心包含一个全屏操作，点击该操作会将窗口恢复到全屏模式，且右上角有一个退出按钮，用于关闭窗口并将应用置于后台。当在此种模式下显示时，添加到 PiP 窗口的任何自定义操作将出现在屏幕上。在图 82-2 的例中，PiP 窗口包含了自定义的播放和暂停操作按钮：

![image-CRF7IU2R.jpg](img/image-CRF7IU2R.jpeg)

图 82-2

本章剩余部分将概述如何从 Android 应用内部启用和管理 PiP 模式。

## 82.2 启用画中画模式

PiP 模式目前仅支持运行 `API 26`：即 Android 8.0（Oreo）或更高版本的设备。实现 PiP 模式的第一步是在项目的清单文件（manifest file）中启用它。通过在每个需要 PiP 支持的 activity 元素中添加以下行，可以按 activity 配置 PiP 模式：

```xml
android:supportsPictureInPicture="true"

android:configChanges="screenSize|smallestScreenSize|screenLayout|orientation"
```

`android:supportsPictureInPicture` 启用了 activity 的 PiP 功能，而 `android:configChanges` 属性通知 Android 该 activity 可以处理布局配置更改。如果没有此设置，每次 activity 进出 PiP 模式时，activity 都会重启，导致在转换期间从视频开始重新播放。

## 82.3 配置画中画参数

PiP 行为通过使用 `PictureInPictureParams` 类定义，可以使用 `Builder` 类创建如下实例：

```java
PictureInPictureParams params = new PictureInPictureParams.Builder().build();
```

上述代码创建了一个定义了特殊参数的默认 `PictureInPictureParams` 实例。也可以使用以下可选方法调用来自定义参数：

- `setActions()` – 用于定义 activity 处于 PiP 模式时可以在 PiP 窗口内执行的操作。本章稍后将详细介绍操作。
- `setAspectRatio()` – 声明 PiP 窗口外观的首选宽高比。该方法接收一个包含高与宽之比例的 `Rational` 对象作为参数。
- `setSourceRectHint()` – 接收一个 `Rect` 对象作为参数，定义在 PiP 窗口内显示的 activity 屏幕区域。

例如，以下代码在 `PictureInPictureParams` 对象中配置了宽高比和操作参数。在宽高比方面，它是使用 `VideoView` 实例的宽度和高度维度定义的：

```java
Rational rational = new Rational(videoView.getWidth(), videoView.getHeight());

PictureInPictureParams params = new PictureInPictureParams.Builder()
    .setAspectRatio(rational)
    .setActions(actions)
    .build();
```

一旦定义，可以使用如下 `setPictureInPictureParams()` 方法随时设置 PiP 参数：

```java
setPictureInPictureParams(params);
```

在进入 PiP 模式时也可以指定参数。

## 82.4 进入画中画模式

通过调用 `enterPictureInPictureMode()` 方法并传递 `PictureInPictureParams` 对象，可以将 activity 进入画中画模式：

```java
enterPictureInPictureMode(params);
```

如果不需要参数，请按照上一节所述创建一个默认的 `PictureInPictureParams` 实例。如果之前已使用 `setPictureInPictureParams()` 方法设置了参数，则这些参数将与 `enterPictureInPictureMode()` 方法调用时指定的参数合并使用。

## 82.5 检测画中画模式变化

当 activity 进入 PiP 模式时，隐藏不必要的视图非常重要，这样 PiP 窗口内只显示视频播放。当 activity 重新进入全屏模式时，必须恢复隐藏的用户界面组件。可以通过重写 `onPictureInPictureModeChanged()` 方法来执行这些以及其他应用特定的任务。当将此方法添加到 activity 时，每次 activity 在 PiP 和全屏模式之间切换时都会调用该方法，并传递一个指示是否处于 PiP 模式的布尔值：

```java
@Override
public void onPictureInPictureModeChanged(boolean isInPictureMode) {
    super.onPictureInPictureModeChanged(isInPictureMode);

    if (isInPictureMode) {
        // 进入画中画模式
    } else {
        // 进入全屏模式
    }
}
```

## 82.6 添加画中画操作

画中画操作在用户点击 PiP 窗口时会以图标形式显示。实现画中画操作是一个多步过程，起步是实现一种让 PiP 窗口通知应用已选择操作的方法。这通过在应用内部设置广播接收器（broadcast receiver），然后在 PiP 操作中创建一个等待意图（pending intent），该意图被配置为广播接收器正在监听。当意图触发广播接收器时，意图中存储的数据可用于识别执行的操作并在应用内采取相应行动。

画中画操作使用 `RemoteAction` 实例声明，并使用图标、标题、描述和 `PendingIntent` 对象进行初始化。一旦创建了一个或多个操作，将它们添加到 `ArrayList` 中并在构建 `PictureInPictureParams` 对象时通过 `setActions()` 方法传递。

以下代码片段演示了 `Intent`、`PendingIntent` 和 `RemoteAction` 对象的创建，并将其应用于应用的 PiP 设置中：

```java
final ArrayList actions = new ArrayList<>();

Intent actionIntent = new Intent("MY_PIP_ACTION");

final PendingIntent pendingIntent = PendingIntent.getBroadcast(
    MyActivity.this,
    REQUEST_CODE,
    actionIntent,
    FLAG_IMMUTABLE
);

final Icon icon = Icon.createWithResource(
    MyActivity.this,
    R.drawable.action_icon
);

RemoteAction remoteAction = new RemoteAction(
    icon,
    "My Action Title",
    "My Action Description",
    pendingIntent
);

actions.add(remoteAction);

PictureInPictureParams params = new PictureInPictureParams.Builder()
    .setActions(actions)
    .build();

setPictureInPictureParams(params);
```

## 82.7 总结

画中画（Picture-in-Picture mode）是 Android 8.0 引入的一项多任务功能，专门用于允许用户在执行其他应用任务和活动的同时，在小窗口继续播放视频。在使用 PiP 模式之前，必须先在清单文件中为需要 PiP 支持的 activity 启用它。

PiP 模式的行为通过 `PictureInPictureParams` 类的实例进行配置，并在 activity 内部通过调用 `enterPictureInPictureMode()` 方法启动。在 PiP 模式下，应仅显示视频播放，这要求在选择全屏模式之前隐藏任何其他用户界面元素。这些以及其他与模式切换相关的任务可以通过重写 `onPictureInPictureModeChanged()` 方法来完成。

当用户点击 PiP 窗口时，PiP 操作将以叠加在 PiP 窗口上的图标形式出现。选中这些操作后会触发 activity 内部的行为。PiP 窗口使用广播接收器和等待意图（pending intents）来通知 activity。

# 83. Android 画中画教程

延续前面的章节，本章将对现有的 `VideoPlayer` 项目进行增强，以添加画中画支持，包括检测 PiP 模式变化以及添加一个用于显示当前正在运行视频信息的 PiP 操作。

## 83.1 在清单文件中添加画中画支持

在 Android 应用项目中添加 PiP 支持的第一步是在项目的 Manifest 文件中启用它。打开 `manifests -> AndroidManifest.xml` 文件并修改 `activity` 元素以启用 PiP 支持：

```xml
android:name=".MainActivity"

android:supportsPictureInPicture="true"

android:configChanges="screenSize|smallestScreenSize|screenLayout|orientation"

android:exported="true">
```

## 83.2 添加画中画按钮

按照目前的设计，`VideoPlayer` activity 的布局仅包含一个 `VideoView` 实例。现在将向布局中添加一个按钮以切换到 PiP 模式。将 `activity_main.xml` 文件加载到布局编辑器中，从调色板拖入一个 `Button` 对象到布局中，使其位置如图 83-1 所示：

![image-NOEZJJC3.jpg](img/image-NOEZJJC3.jpeg)

图 83-1

将按钮上的文本更改为“Enter PiP Mode”，并将字符串提取到名为 `enter_pip_mode` 的资源中。在继续下一步之前，将按钮的 ID 更改为 `pipButton` 并配置 `onClick` 属性以调用名为 `enterPipMode` 的方法。

## 83.3 进入画中画模式

现在必须将 `enterPipMode` onClick 回调方法添加到 `MainActivity.java` 类文件中。找到该文件，在代码编辑器中打开它，并如下如下添加此方法：

```java
import android.app.PictureInPictureParams;
import android.util.Rational;

public void enterPipMode(View view) {
    Rational rational = new Rational(
        binding.videoView1.getWidth(),
        binding.videoView1.getHeight()
    );

    PictureInPictureParams params =
        new PictureInPictureParams.Builder()
            .setAspectRatio(rational)
            .build();

    binding.pipButton.setVisibility(View.INVISIBLE);
    binding.videoView1.setMediaController(null);

    enterPictureInPictureMode(params);
}
```

该方法首先获取 `Button` 视图的引用，然后创建一个包含 `VideoView` 宽度和高度的 `Rational` 对象。接着，使用 `PictureInPictureParams.Builder` 创建一组画中画参数，并将 `Rational` 对象作为视频播放的宽高比例传递。由于由于在视频处于 PiP 模式时不需要显示按钮，因此将其设置为不可见。视频播放控制控件也被隐藏了，因此视频视图在 PiP 模式下将不会受到任何遮挡。

在运行 Android 版本 8 或更高版本的设备或模拟器上编译并运行应用，在点击 PiP 模式按钮之前等待视频开始播放。视频播放将最小化并显示在 PiP 窗口中，如图 83-2 所示：

![image-V9CD9TAI.jpg](img/image-V9CD9TAI.jpeg)

图 83-2

点击 PiP 窗口，然后点击窗口中心出现的全屏模式标记。尽管 activity 回到了全屏模式，但按钮和媒体播放控制控件仍保持隐藏状态。

显然，必须向项目中添加一些代码来检测 activity 内部何时发生 PiP 模式的切换。

## 83.4 检测画中画模式变化

如在前一节所述，PiP 模式的变化是通过重写受影响 activity 的 `onPictureInPictureModeChanged()` 方法检测的。在这种情况下，必须编写该方法来检测 activity 是正在进入还是退出 PiP 模式，并采取适当行动重新激活 PiP 按钮和播放控件。留在 `MainActivity.java` 文件中，现在添加此方法：

```java
@Override
public void onPictureInPictureModeChanged(
    boolean isInPictureInPictureMode
) {
    super.onPictureInPictureModeChanged(
        isInPictureInPictureMode
    );

    if (isInPictureInPictureMode) {
    } else {
        binding.pipButton.setVisibility(View.VISIBLE);
        binding.videoView1.setMediaController(mediaController);
    }
}
```

当调用该方法时，会传递一个 `Boolean` 值，表示 activity 现在是否处于 PiP 模式。上述方法中的代码检查此值，以决定是否显示 PiP 按钮并恢复播放控件。

## 83.5 添加广播接收器

项目的最后一步是为 PiP 窗口添加一个操作。该操作目的是显示包含当前播放视频名称 `Toast` 消息。这需要 PiP 窗口与 activity 之间的某些通信。实现此目标的最简单方法是在 activity 内部实现广播接收器，并使用等待意图（pending intent）从 PiP 窗口通知 activity。每次 activity 进入 PiP 模式时都要执行这些步骤，因此必须在 `onPictureInPictureModeChanged()` 方法中添加代码。现在找到该方法并开始添加代码创建意图过滤器并初始化广播接收器：

```java
import android.content.BroadcastReceiver;
import android.content.Context;
import android.content.Intent;
import android.content.IntentFilter;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    private BroadcastReceiver receiver;

    @Override
```



```java
public void onPictureInPictureModeChanged(boolean isInPictureInPictureMode) {
    super.onPictureInPictureModeChanged(isInPictureInPictureMode);

    if (isInPictureInPictureMode) {
        IntentFilter filter = new IntentFilter();
        filter.addAction("com.ebookrenzy.videoplayer.VIDEO_INFO");

        receiver = new BroadcastReceiver() {
            @Override
            public void onReceive(Context context, Intent intent) {
                Toast.makeText(context, "Favorite Movie Clips", Toast.LENGTH_LONG).show();
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
```

## 83.6 添加 PiP 操作

实现广播接收器后，下一步是创建一个 `RemoteAction` 对象，并配置图像以表示 PiP 窗口中的操作。

对于本示例，将使用名为 `ic_info_24dp.xml` 的图像图标文件。该文件可以在从以下 URL 下载的源码包的 `project_icons` 文件夹找到：

`https://www.payloadbooks.com/product/ladybugjava`

找到此图标文件，将其复制并粘贴到项目工具窗口 `app -> res -> drawables` 文件夹中：

![image-5JM5MPM9.jpg](img/image-5JM5MPM9.jpeg)

图 83-3

下一步是创建一个将发送到广播接收器（broadcast receiver）的 `Intent`。该 `Intent` 然后需要封装在一个 `PendingIntent` 对象中，以便在用户点击画中画（PiP）窗口中的操作按钮时触发该 `Intent`。

编辑 `MainActivity.java` 文件，添加如下所示的方法来创建 `Intent` 和 `PendingIntent` 对象：

```java
import android.app.PendingIntent;

import static android.app.PendingIntent.FLAG_IMMUTABLE;

public class MainActivity extends AppCompatActivity {
    private static final int REQUEST_CODE = 101;

    private void createPipAction() {
        Intent actionIntent = new Intent("com.ebookfrenzy.videoplayer.VIDEO_INFO");

        final PendingIntent pendingIntent = PendingIntent.getBroadcast(
            MainActivity.this,
            REQUEST_CODE, actionIntent, FLAG_IMMUTABLE);
    }
}
```

### 创建 RemoteAction 对象

现在 `Intent` 对象和包含它的 `PendingIntent` 实例都已创建，需要创建一个 `RemoteAction` 对象，其中包含显示在 PiP 窗口中的图标。在 `createPipAction()` 方法中，按照如下代码添加内容：

```java
import android.app.RemoteAction;
import android.graphics.drawable.Icon;

import java.util.ArrayList;

private void createPipAction() {
    final ArrayList actions = new ArrayList<>();

    Intent actionIntent = new Intent("com.ebookfrenzy.videoplayer.VIDEO_INFO");

    final PendingIntent pendingIntent = PendingIntent.getBroadcast(
        MainActivity.this,
        REQUEST_CODE, actionIntent, FLAG_IMMUTABLE);

    final Icon icon = Icon.createWithResource(
        MainActivity.this,
        R.drawable.ic_info_24dp);

    RemoteAction remoteAction = new RemoteAction(
        icon, "Info", "Video Info", pendingIntent);

    actions.add(remoteAction);
}
```

现在需要创建一个包含操作的 `PictureInPictureParams` 对象并应用参数，以便该操作显示在 PiP 窗口中：

```java
private void createPipAction() {
    final ArrayList actions = new ArrayList<>();

    Intent actionIntent = new Intent("com.ebookfrenzy.videoplayer.VIDEO_INFO");

    final PendingIntent pendingIntent = PendingIntent.getBroadcast(
        MainActivity.this,
        REQUEST_CODE, actionIntent, FLAG_IMMUTABLE);

    final Icon icon = Icon.createWithResource(
        MainActivity.this,
        R.drawable.ic_info_24dp);

    RemoteAction remoteAction = new RemoteAction(
        icon, "Info", "Video Info", pendingIntent);

    actions.add(remoteAction);

    PictureInPictureParams params =
        new PictureInPictureParams.Builder()
            .setActions(actions)
            .build();

    setPictureInPictureParams(params);
}
```

在测试操作之前的最后一个任务是在 activity 进入 PiP 模式时调用 `createPipAction()` 方法：

```java
@Override
public void onPictureInPictureModeChanged(
        boolean isInPictureInPictureMode) {

    super.onPictureInPictureModeChanged(
        isInPictureInPictureMode);

    if (isInPictureInPictureMode) {
        registerReceiver(receiver, filter);
        createPipAction();
    } else {
        binding.pipButton.setVisibility(View.VISIBLE);
        binding.videoView1.setMediaController(mediaController);
    }
}
```

## 83.7 测试画中画操作

重新运行应用并将 activity 置于 PiP 模式。点击 PiP 窗口，使新的操作按钮出现，如图 83-4 所示：

![image-FN88GGQ0.jpg](img/image-FN88GGQ0.jpeg)

图 83-4

点击操作按钮并等待 `Toast` 消息出现，显示视频名称：

![image-UN72Y66H.jpg](img/image-UN72Y66H.jpeg)

图 83-5

## 83.8 总结

本章演示了如何在 Android Studio 应用项目中添加画中画支持，包括启用和进入 PiP 模式以及实现 PiP 操作。这包含了使用广播接收器和等待意图（pending intents）来实现 PiP 窗口与 activity 之间的通信。

## 84. 使用 MediaPlayer 和 MediaRecorder 进行 Android 音频录制和播放

本章将提供 `MediaRecorder` 类的概述并解释如何使用该类录制音频或视频。还将涵盖使用 `MediaPlayer` 类播放音频的内容。在介绍基础知识后，将创建一个示例应用程序来演示这些技术。除了处理音频和视频外，本章还将涉及将文件保存到 SD 卡。

## 84.1 播放音频

在音频播放方面，大多数 Android 实现支持 AAC LC/LTP、HE-AACv1 (AAC+)、HE-AACv2 (enhanced AAC+)、AMR-NB、AMR-WB、MP3、MIDI、Ogg Vorbis 和 PCM/WAVE 格式。

可以使用 `MediaPlayer` 或 `AudioTrack` 类执行音频播放。`AudioTrack` 是更高级的选项，它使用流媒体缓冲区并对音频提供更大的控制。相反，`MediaPlayer` 类提供了一个更简单的编程接口来实现音频播放，能够满足大多数音频需求。

`MediaPlayer` 类关联有一系列可供应用程序调用以执行任务的方法。该类的一些关键方法如下：

- `create()` – 创建类的新实例，传递要播放的音频 Uri。
- `setDataSource()` – 设置音频的源。
- `prepare()` – 通知播放器准备开始播放。
- `start()` – 开始播放。
- `pause()` – 暂停播放。播放可以通过调用 `resume()` 恢复。
- `stop()` – 停止播放。
- `setVolume()` – 指定左右通道音量的浮点参数。
- `resume()` – 恢复之前暂停的会话。
- `reset()` – 重置媒体播放器。本质上是将实例置回初始化状态。至少，重置的播放器需要设置数据源并调用 `prepare()` 方法。
- `release()` – 当播放器不再需要时调用。此方法确保释放播放器持资源。

在典型的实现中，应用程序将实例化 `MediaPlayer` 类，设置音频源，然后调用 `prepare()` 和 `start()`。例如：

```java
MediaPlayer mediaPlayer = new MediaPlayer();

mediaPlayer.setDataSource(
    "https://www.yourcompany.com/yaudio.mp3");

mediaPlayer.prepare();

mediaPlayer.start();
```

## 84.2 使用 MediaRecorder 类录制音频和视频

与音频播放一样，录制可以使用不同的技术。一种选择是使用 `MediaRecorder` 类，它与 `MediaPlayer` 类的方法如下：

- `setAudioSource()` – 指定要录制的音频源（通常将是 `MediaRecorder.AudioSource.MIC`）。
- `setVideoSource()` – 指定要录制的视频的源（例如 `MediaRecorder.VideoSource.CAMERA`）。
- `setOutputFormat()` – 指定录制的音频或视频要存储的格式（例如 `MediaRecorder.OutputFormat.AAC_ADTS`）。
- `setAudioEncoder()` – 指定录制音频的音频编码器（例如 `MediaRecorder.AudioEncoder.AAC`）。
- `setOutputFile()` – 配置存储录制的音频或视频的文件路径。
- `prepare()` – 准备 `MediaRecorder` 实例以开始录制。
- `start()` – 开始录制过程。
- `stop()` – 停止录制过程。一旦录制机停止，在重新启动之前必须重新配置并准备。
- `reset()` – 重置录制机。实例在重启之前需要完全重新配置并准备。
- `release()` – 在录制机实例不再需要时调用。此方法确保释放实例持有的所有资源。

使用此类的典型实现将设置源、输出、编码格式和输出文件。随后将调用 `prepare()` 和 `start()` 方法。录制结束时将调用 `stop()` 方法，然后调用 `reset()` 方法。当应用程序不再需要该录制器实例时，建议调用 `release()` 方法：

```java
MediaRecorder mediaRecorder = new MediaRecorder();

mediaRecorder.setAudioSource(
    MediaRecorder.AudioSource.MIC);

mediaRecorder.setOutputFormat(
    MediaRecorder.OutputFormat.AAC_ADTS);

mediaRecorder.setAudioEncoder(
    MediaRecorder.AudioEncoder.AAC);

mediaRecorder.setOutputFile(audioFilePath);

mediaRecorder.prepare();

mediaRecorder.start();

mediaRecorder.stop();

mediaRecorder.reset();

mediaRecorder.release();
```



要录制音频，应用程序清单文件（manifest）必须包含 `android.permission.RECORD_AUDIO` 权限：

正如名为“在 Android 中请求运行时权限”的章节所述，访问麦克风属于危险权限类别。因此，为了支持 Android 6，在应用程序启动时必须对麦克风访问进行特定请求，相关步骤将在本章稍后介绍。

## 84.3 关于示例项目

本章的剩余部分将创建一个示例应用程序，用于演示使用 `MediaPlayer` 和 `MediaRecorder` 类在 Android 设备上实现音频的录制和播放。

在开发使用特定硬件功能的应用程序时（麦克风就是一个例子），在尝试代码访问该功能之前检查该功能的可用性至关重要。因此，本章创建的应用程序还将包含检测设备是否存在麦克风的代码。

完成后，该应用程序将提供一个简单的界面，允许用户录制和播放音频。录制的音频将存储在设备上的一个音频文件内。既然如此，本教程还将简要探索使用 SD 卡存储的机制。

## 84.4 创建 AudioApp 项目

从欢迎屏幕选择 New Project（新建项目），在弹出的新项目对话框中，选择 Empty Views Activity 模板，然后点击 Next（下一步）按钮。

在 `Name` 字段中输入 `AudioApp`，并指定 `com.ebookfrenzy.audioapp` 为包名。在点击 Finish（完成）按钮之前，将 Minimum API level 设置为 `API 31`: Android 12.0，并将 Language（语言）菜单设置为 Java。使用第 12.8 节 Migrating a Project to View Binding 中概述的步骤为项目添加 view binding 支持。

## 84.5 设计用户界面

创建新项目后，从 Project 工具窗口选择 `activity_main.xml` 文件，并在 Design（设计）模式下的 Layout Editor 工具中，选择“Hello World!” `TextView` 并将其从布局中删除。

将三个 `Button` 视图拖放到布局中。按钮的位置对于本示例来说并不至关重要，但图 84-1 显示了使用垂直链（vertical chain）的建议布局。

配置按钮以显示读取 Play（播放）、Record（录制）和 Stop（停止）的字符串资源，并分别为它们赋予视图 ID：`playButton`、`recordButton` 和 `stopButton`。

选择 Play 按钮，并在 Attributes（属性）面板中，配置 `onClick` 属性，以便在用户选择时调用名为 `playAudio` 的方法。重复这些步骤，配置其余按钮分别调用名为 `recordAudio` 和 `stopAudio` 的方法。

![image-1JF09E5B.jpg](img/image-1JF09E5B.jpeg)

图 84-1

## 84.6 检查麦克风可用性

在没有麦克风的设备上尝试录制音频会导致 Android 系统抛出异常。因此，在进行此类尝试之前检查麦克风的存在至关重要。有几种方法可以实现，包括检查设备的物理是否存在。另一种简单且可能在不同 Android 设备上生效的方法是询问 Android 系统是否安装了针对特定功能的包。这涉及创建一个 `PackageManager` 类的实例，然后调用对象的 `hasSystemFeature()` 方法。在本例中，`PackageManager.FEATURE_MICROPHONE` 是我们关注的功能。

对于此示例，我们将创建一个名为 `hasMicrophone()` 的方法，可以调用它来检查麦克风的存在。在 Project 工具窗口中，找到并双击 `MainActivity.java` 文件，并修改以添加此方法：

```java
package com.ebookfrenzy.audioapp;

import android.content.pm.PackageManager;

public class MainActivity extends AppCompatActivity {

    protected boolean hasMicrophone() {

        PackageManager pmanager = this.getPackageManager();

        return pmanager.hasSystemFeature(

            PackageManager.FEATURE_MICROPHONE);

    }

}
```

## 84.7 初始化 Activity

下一步是修改 activity 以执行几项初始化任务。留在 `MainActivity.java` 文件中，修改代码如下：

```java
package com.ebookfrenzy.audioapp;

import java.io.File;

import java.io.IOException;

import androidx.annotation.NonNull;

import android.media.MediaRecorder;

import android.os.Environment;

import android.media.MediaPlayer;

public class MainActivity extends AppCompatActivity {

    private ActivityMainBinding binding;

    private static MediaRecorder mediaRecorder;

    private static MediaPlayer mediaPlayer;

    private static String audioFilePath;

    private boolean isRecording = false;

    @Override

    protected void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);

        audioSetup();

    }

    private void audioSetup()

    {

        if (!hasMicrophone()) {

            binding.stopButton.setEnabled(false);

            binding.playButton.setEnabled(false);

            binding.recordButton.setEnabled(false);

        } else {

            binding.playButton.setEnabled(false);

            binding.stopButton.setEnabled(false);

        }

        File audioFile = new File(this.getFilesDir(), "myaudio.3gp");

        audioFilePath = audioFile.getAbsolutePath();

    }

}
```

添加的代码调用 `hasMicrophone()` 方法来确定设备是否包含麦克风。如果没有，则禁用所有按钮；否则，仅禁用停止和播放按钮。

下一行代码需要一点解释：

`File audioFile = new File(this.getFilesDir(), "myaudio.3gp");`

`audioFilePath = audioFile.getAbsolutePath();`

此代码在应用程序的内部存储中创建一个名为 `myaudio.3gp` 的新文件以存储录音。

## 84.8 实现 `recordAudio()` 方法

当用户触摸录制按钮时将调用 `recordAudio()` 方法。该方法需要开启相应的按钮并配置 `MediaRecorder` 实例所需的音频源、输出格式编码以及存储音频的位置。最后，需要调用 `MediaRecorder` 对象的 `prepare()` 和 `start()` 方法。这些需求共同在 `MainActivity.java` 文件中形成了以下方法实现：

```java
public void recordAudio (View view) {

    isRecording = true;

    binding.stopButton.setEnabled(true);

    binding.playButton.setEnabled(false);

    binding.recordButton.setEnabled(false);

    try {

        mediaRecorder = new MediaRecorder(this);

        mediaRecorder.setAudioSource(MediaRecorder.AudioSource.MIC);

        mediaRecorder.setOutputFormat(MediaRecorder.OutputFormat.THREE_GPP);

        mediaRecorder.setOutputFile(audioFilePath);

        mediaRecorder.setAudioEncoder(MediaRecorder.AudioEncoder.AMR_NB);

        mediaRecorder.prepare();

    } catch (Exception e) {

        e.printStackTrace();

    }

    mediaRecorder.start();

}
```

## 84.9 实现 `stopAudio()` 方法

`stopAudio()` 方法会启用 `Play` 按钮，关闭 `Stop` 按钮，然后停止并重置 `MediaRecorder` 实例。实现此功能的代码如下列表所示，并应将其添加到 `MainActivity.java` 文件中：

```java
public void stopAudio (View view)

{

    binding.stopButton.setEnabled(false);

    binding.playButton.setEnabled(true);

    if (isRecording)

    {

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

## 84.10 实现 `playAudio()` 方法

`playAudio()` 方法将创建一个新的 `MediaPlayer` 实例，将位于 SD 卡上的音频文件指定为数据源，然后准备并开始播放：

```java
public void playAudio (View view) throws IOException

{

    binding.playButton.setEnabled(false);

    binding.recordButton.setEnabled(false);

    binding.stopButton.setEnabled(true);

    mediaPlayer = new MediaPlayer();

    mediaPlayer.setDataSource(audioFilePath);

    mediaPlayer.prepare();

    mediaPlayer.start();

}
```

## 84.11 配置和请求权限

在测试应用程序之前，必须在清单文件中为应用程序请求适当的权限。具体而言，应用程序将需要访问麦克风的权限。在 `Project` 工具窗口中，找到并双击 `AndroidManifest.xml` 文件以将其加载到编辑器中，并修改 XML 以添加权限标签：

```xml
xmlns:tools="http://schemas.android.com/tools">

.

.
```

上述步骤足以确保当应用安装在运行 Android 6.0 之前的版本的设备上时，用户能够启用麦克风访问权限。在 Android 中，麦克风访问被归类为“危险权限”，因为它允许应用程序可能损害用户的隐私。为了让示例应用在 Android 6 或更高版本的设备上运行，需要添加代码以在应用运行时请求权限。

编辑 `MainActivity.java` 文件，首先添加一些额外的导入指令和一个常量，作为所请求权限的请求标识代码：

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

接下来，需要向类中添加一个方法，其目的是接收要请求的权限和相应的请求标识代码作为参数。在 `MainActivity.java` 类文件中，按照 own 实现此方法：

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

使用此书中“在 Android 中进行运行时权限请求”章节中概述的步骤，上述方法会在发出请求之前验证指定的权限是否已经授予，并将标识代码作为参数传递。

当请求被处理后，活动将调用 `onRequestPermissionsResult()` 方法，并传递标识代码和请求结果。因此，下一步是在 `MainActivity.java` 文件中按所示实现此方法：

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

上述代码通过检查请求标识代码来识别是哪个权限请求返回的，然后再检查相应的权限是否已授予。如果权限被拒绝，将向用户显示一条消息，指示应用将无法运行且录音按钮将被禁用。

在测试应用之前，剩下的工作是在应用启动时调用新添加的 `requestPermission()` 方法来请求麦克风访问。在 `MainActivity.java` 文件中，按所示修改 `audioSetup()` 方法：

```java
private void audioSetup(){

    binding.recordButton = findViewById(R.id.recordButton);

    binding.playButton = findViewById(R.id.playButton);

    binding.stopButton = findViewById(R.id.stopButton);

    if (!hasMicrophone())

    {

        stopButton.setEnabled(false);

        playButton.setEnabled(false);

        recordButton.setEnabled(false);

    } else {
```



```java
playButton.setEnabled(false);

stopButton.setEnabled(false);

}

File audioFile = new File(this.getFilesDir(), "myaudio.3gp");

audioFilePath = audioFile.getAbsolutePath();

requestPermission(Manifest.permission.RECORD_AUDIO,

RECORD_REQUEST_CODE);

}
```

## 84.12 测试应用程序

在带有麦克风的 Android 设备上编译并运行应用，允许麦克风访问，并点击 `Record` 按钮。录音完成后，点击 `Stop` 然后 `Play`。此时，音频应通过设备扬声器播放。

## 84.13 总结

Android SDK 提供了实现音频录制和播放的机制。本章介绍了其中的两种：`MediaPlayer` 和 `MediaRecorder` 类。在涵盖了这些技术的理论后，本章通过创建一个用于录制和播放的示例应用程序。在 Android 中处理音频时，本章还查看了确保设备具有麦克风的步骤。

# 85. 在 Android Studio 中使用 Google Maps API

当 Google 多年前推出地图服务时，很难判断他们是否曾预见到会有可以集成到应用程序中的版本。当后来 Google Maps 的第一个网页版本推出时，iPhone 尚未引发智能手机革命，Google 在六个月后才收购开发 Android 操作系统的公司。无论 Google 对 Google Maps 的未来有什么愿景，现在可以通过 Google Maps Android API 直接在 Android 中访问访问。

本章旨在概述 Google Maps 系统和 Google Maps Android API。本章将提供组成 API 的元素的概述，详细说明配置 Google Maps 开发环境所需的步骤，然后通过一些代码示例演示 Google Maps 集成的基础知识。

## 85.1 Google Maps API 的元素

Google Maps Android API 由一组核心类组成，为 Android 应用程序提供地图功能。地图的关键元素如下：

- `GoogleMap` – Google Maps Android API 的主类。该类负责下载和显示地图瓦片，并显示和响应地图控件。`GoogleMap` 对象不是由应用程序直接创建的，而是在创建 `MapView` 或 `MapFragment` 实例时创建的。可以通过调用 `MapView`、`MapFragment` 或 `SupportMapFragment` 实例的 `getMap()` 方法来获取 `GoogleMap` 对象的引用。
- `MapView` - 这是 `View` 类的子类，该类提供了一个视图画布，`GoogleMap` 对象在其上方绘制地图，允许将地图放置在 activity 的用户界面布局中。
- `SupportMapFragment` – `Fragment` 类的子类，该类允许将地图放置在 Android 布局中的 `Fragment` 中。
- `Marker` – `Marker` 类的目的是允许在地图上标记位置。通过获取与地图相关的 `GoogleMap` 对象引用，然后调用该对象实例的 `addMarker()` 方法，可以将标记添加到地图上。标记的位置通过 `Longitude`（经度）和 `Latitude`（纬度）定义。标记可以通过多种方式进行配置，包括指定标题、文本和图标。标记还也可以是“可拖拽”的，允许用户将标记移动到地图上的不同位置。
- `Shapes` – 使用 `Polyline`、`Polygon` 和 `Circle` 类在地图上绘制线条和形状。
- `UiSettings` – `UiSettings` 类用于自定义地图上显示的控制控件。例如，使用 `UiSettings`，应用程序可以控制地图上是否显示缩放、当前位置和罗盘控件。该类还可以配置地图识别哪些触摸屏手势。
- `My Location Layer` – 启用后，“我的位置层”会在地图上显示一个按钮，当用户选择该按钮时，地图将中心化到用户的当前地理位置。如果用户处于静止状态，蓝色标记将代表地图上的此位置。如果用户正在移动，位置将由一个指示用户行驶方向的箭头（chevron）表示。

熟悉 Google Maps Android API 的最佳方法是运行示例。本章的剩余部分将创建一个基于 Google Maps 的应用程序，同时重点介绍 API 的关键领域。

## 85.2 创建 Google Maps 项目

从欢迎界面选择 `New Project`（新建项目）选项，在生成的新项目对话框中点击 `Next`（下一步）按钮之前，选择 `No Activity` 模板。

在 `Name` 字段中输入 `MapDemo`，并指定 `com.ebookfrenzy.mapdemo` 为包名。在点击 `Finish` 之前，将 `Minimum API level`（最低 API 级别）设置改为 `API 26`：Android 8.0 (Oreo)，并将 `Language`（语言）菜单设置为 `Java`。

接下来，在 Project 工具窗口中右键点击 `app` -> `java` -> `com.ebookfrenzy.mapdemo` 项，选择 `New -> Google -> Google Maps Views Activity` 菜单选项。最后，在点击 `Finish` 按钮之前，在 `New Android Activity` 对话框中启用 `Launcher Activity` 复选框：

![image-Z0Q7SROX.jpg](img/image-Z0Q7SROX.jpeg)

图 85-1

## 85.3 创建 Google Cloud 结算账户

在使用 Google Map APIs 之前，您必须先创建一个 Google Cloud 结算账户（如果您已经有一个，可以跳到下一节）。要执行此操作，打开浏览器并使用以下链接导航到 Google Cloud 控制台：

`https://console.cloud.google.com/`

接下来，点击控制台页面左上角的菜单按钮，如图 85-2 所示选择 `Billing`（结算）项：

![image-UOF32DQC.jpg](img/image-UOF32DQC.jpeg)

图 85-2

在结算页面上，选择添加新结算账户的选项，然后按照步骤开始免费试用。您必须提供信用卡来开设账户，但免费试用结束时，未经您同意，Google 不向您收费。

## 85.4 创建新的 Google Cloud 项目

下一步是创建一个与 `MapDemo` 应用程序关联的 Google Cloud 项目。要执行此操作，使用以下 URL 返回 Google Cloud 控制台仪表板：

`https://console.cloud.google.com/home/dashboard`

在仪表板中，点击顶部工具栏上的 `Select a project`（选择项目）按钮：

![image-8TETFOHK.jpg](img/image-8TETFOHK.jpeg)

图 85-3

当项目选择对话框出现时，点击 `New Project` 按钮（如图 85-4 所示）：

![image-6HCFISAH.jpg](img/image-6HCFISAH.jpeg)

图 85-4

当出现新项目屏幕时，为项目提供一个名称。控制台将在项目名称字段下方显示项目的默认 ID。如果您不喜欢默认 ID，可以点击 `Edit`（编辑）按钮进行更改：

![image-QYR6CGK1.jpg](img/image-QYR6CGK1.jpeg)

图 85-5

点击 `Create`（创建）按钮，稍等片刻您将返回仪表板，那里将列出您的新项目。

## 85.5 启用 Google Maps SDK

现在我们已经创建了新的 Google Cloud 项目，下一步是允许项目使用 Google Maps SDK。要启用 Google Maps 支持，请在 Google Cloud 控制台中选择您的项目，点击左上角的菜单按钮，并选择 `Google Maps Platform` 项。然后，从生成的菜单中如图 85-6 所示选择 `APIs` 选项：

![image-4NVWWFEC.jpg](img/image-4NVWWFEC.jpeg)

图 85-6

在 API 页面上，选择 `Maps SDK for Android` 项目，并在生成的屏幕上点击 `Enable`（启用）按钮：

![image-NGY67L5.jpg](img/image-NGY67L5.jpeg)

图 85-7

重复上述步骤启用 Geocoding API，这稍后需要我们的应用程序显示用户的当前位置。

## 85.6 生成 Google API 密钥

在应用程序可以使用 Google Maps SDK 之前，必须配置 API 密钥以关联 Google Cloud 项目。要生成 API 密钥，选择 `Credentials` 项（如图 85-8 中的 A），然后点击 `Create Credentials` 按钮（B）：

![image-1WLECS.jpg](img/image-1WLECS.jpeg)

图 85-8

凭据创建后，将显示 API 密钥的对话框：

![image-PD8R2SR.jpg](img/image-PD8R2SR.jpeg)

图 85-9

## 85.7 将 API 密钥添加到 Android

现在我们已经生成了允许应用程序使用 Google Maps SDK 的 API 密钥，我们需要将其添加到项目中。返回 Android，编辑 `manifests` -> `AndroidManifest.xml` 文件，并找到以下密钥项：

```xml
android:name="com.google.android.geo.API_KEY" android:value="YOUR_KEY"
```

删除文本 `YOUR_KEY` 并将其替换为在 Google Play Console 创建的密钥。

接下来，编辑 `Gradle Scripts` -> `local.properties` 文件并添加如下新行（用项目的 API 密钥替换 `YOUR_KEY`）：

```properties
MAPS_API_KEY=YOUR_KEY
```

## 85.8 测试应用程序

运行应用程序示例以验证配置是否正确。如果配置正确，应用程序将运行并在屏幕上显示地图。

如果没有显示地图，请检查以下区域：

- 如果应用程序在模拟器上运行，请确保模拟器运行的是包含 Google APIs 的 Android 版本。可以通过选择 `Tools` -> `Android` -> `AVD Manager` 菜单选项更改 AVD 配置的操作系统，点击 Actions 列中的铅笔图标，然后点击当前 Android 版本旁 `Change…` 按钮。在系统映像对话框中选择包含 Google APIs 的目标。
- 检查 `Logcat` 输出是否有与 Google Maps API 身份验证问题相关的区域。这通常意味着 API 密钥输入错误。确保 `AndroidManifest.xml` 和 `local.properties` 文件中的 API 密钥相匹配。

## 85.9 地理编码

在谈论地图和地理位置之前，如果不介绍地理编码（Geocoding）主题是不可能可能的。地理编码是将基于文本的地理位置（如街道地址）转换为以经纬度表示地理坐标。

可以使用 Android 的 `Geocoder` 类来实现地理编码。例如，可以向 `Geocoder` 类的实例传递一个代表位置的字符串，例如城市名称、街道地址或机场代码。`Geocoder` 将尝试查找该位置的匹配项，并返回一个可能与该位置字符串匹配的 `Address` 对象列表，这些对象按匹配程度排序，最匹配的位于列表的第 0 位。随后，可以从 `Address` 对象中提取各种信息，包括潜在匹配项的经纬度。

例如，以下代码请求位于华盛顿特区的国家航空航天博物馆的位置：

```java
import java.io.IOException;

import java.util.List;

import android.location.Address;

import android.location.Geocoder;

.

.

double latitude;

double longitude;

List<Address> geocodeMatches = null;

try {

    geocodeMatches = new Geocoder(this).getFromLocationName(

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

注意，值 `1` 被作为第二个参数传递给 `getFromLocationName()` 方法。这告诉 `Geocoder` 在数组中只返回一个结果。由于所提供的地址具有特定性，应该只有一个潜在的匹配项。然而，对于更模糊的位置名称，可能需要请求更多的潜在匹配项并允许用户选择正确的那个。

上面的代码是正向编码的示例，即坐标是基于文本位置描述计算的。反向编码（Reverse-geocoding）顾顾义是将地理坐标转换为人类可读的地址字符串。例如，考虑以下代码：

```java
import java.io.IOException;

import java.util.List;

import android.location.Address;

import android.location.Geocoder;

.

.

List<Address> geocodeMatches = null;

String Address1;

String Address2;

String State;

String Zipcode;

String Country;

try {

    geocodeMatches = new Geocoder(this).getFromLocation(38.8874245, -77.0200729, 1);

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

通过 `getFromLocation()` 方法使用经度和纬度值初始化 `Geocoder` 对象。再次，只请求了单个匹配结果。然后从生成的 `Address` 对象中提取基于文本的地址信息。

地理编码并不是在 Android 设备上执行的，而是在需要翻译时设备连接的服务器上执行的，翻译完成后返回结果。只有当设备具有活跃的互联网连接时才能进行地理编码。

## 85.10 为应用程序添加地图

向应用程序添加地图最简单的方法是在 activity 的用户界面布局 XML 文件中指定它。以下示例布局文件显示为 Android Studio 创建的 `activity_maps.xml` 文件添加了 `SupportMapFragment` 实例：

```xml
xmlns:tools="http://schemas.android.com/tools"

    android:layout_width="match_parent"

    android:layout_height="match_parent"

    android:id="@+id/map"

    tools:context=".MapsActivity"

    android:name="com.google.android.gms.maps.SupportMapFragment"/>
```

## 85.11 请求当前位置权限

正如“在 Android 中进行运行时权限请求”章节概述的那样，某些权限被认为是危险的，对于 Android 6.0 或更高版本需要特殊处理。一组权限允许应用程序识别用户的当前位置。编辑位于项目工具窗口 `app -> manifests` 下的 `AndroidManifest.xml` 文件，并添加以下权限行：

```xml
android:name="android.permission.ACCESS_FINE_LOCATION" />

android:name="android.permission.ACCESS_COARSE_LOCATION" />
```



这些设置将确保应用在安装在旧版本 Android 上时提供获取位置信息的权限。然而，为了支持 Android 6.0 或更高版本，我们需要在`MapsActivity.java`文件中添加一些代码在运行时请求此权限。

首先添加一些导入指令和一个作为权限请求代码的常量：

```java
package com.ebookfrenzy.mapdemo;

.

.

import androidx.annotation.NonNull;
import androidx.core.content.ContextCompat;
import androidx.core.app.ActivityCompat;

import android.Manifest;
import android.widget.Toast;
import android.content.pm.PackageManager;

.

.

public class MapsActivity extends FragmentActivity implements OnReadyCallback {

    private static final int LOCATION_REQUEST_CODE = 101;

    private GoogleMap mMap;

.

.

}
```

接下来，必须在类中添加一个方法来请求此权限。在`MapsActivity.java`文件中实现该方法：

```java
protected void requestPermission(String permissionType, int requestCode) {
    ActivityCompat.requestPermissions(this, new String[]{permissionType}, requestCode);
}
```

当用户响应权限请求后，`onRequestResult()`方法将被调用。在`MapsActivity.java`文件中实现该方法，如下如下：

```java
@Override
public void onRequestResult(int requestCode, @NonNull String[] permissions, @NonNull int[] grantResults) {
    super.onRequestPermissionsResult(requestCode, permissions, grantResults);

    if (requestCode == LOCATION_REQUEST_CODE) {
        if (grantResults.length == 0 || grantResults[0] != PackageManager.PERMISSION_GRANTED) {
            Toast.makeText(this, "Unable to show location - permission required", Toast.LENGTH_LONG).show();
        } else {
            SupportMapFragment mapFragment =
                    (SupportMapFragment) getSupportFragmentManager().findFragmentById(R.id.map);

            mapFragment.getMapAsync(this);
        }
    }
}
```

如果用户没有授予权限，应用程序将显示一条消息。相反，地图将刷新以为显示标记提供机会。

## 85.12 显示用户的当前位置

一旦获得了适当的权限，就可以通过获取与显示地图相关的`GoogleMap`对象并调用该实例的`setMyLocationEnabled()`方法传递`true`值在地图上显示用户的当前位置。

当地图准备就同时，activity 的`onMapReady()`方法将被调用。此方法在上述`onRequestResult()`方法中刷新地图时再次调用。默认情况下，Android Studio 实现了此方法并添加了一些代码，将地图面向澳大利亚并在悉尼放置标记。定位并编辑`MapsActivity.java`文件中的`onMapReady()`方法，删除这些模板代码并添加代码检查已授予位置权限以启用显示用户的位置。如果尚未授予权限，将通过调用之前添加的`requestPermission()`方法向用户请求：

```java
@Override
public void onMapReady(GoogleMap googleMap) {
    mMap = googleMap;

    // 在悉尼添加标记并移动相机
    LatLng sydney = new LatLng(-34, 151);
}
```

```java
mMap.addMarker(new MarkerOptions().position(sydney).title("Marker in Sydney"));
mMap.moveCamera(CameraUpdateFactory.newLatLng(sydney));

if (mMap != null) {
    int permission = ContextCompat.checkSelfPermission(
            this, Manifest.permission.ACCESS_FINE_LOCATION);

    if (permission == PackageManager.PERMISSION_GRANTED) {
        mMap.setMyLocationEnabled(true);
    } else {
        requestPermission(
                Manifest.permission.ACCESS_FINE_LOCATION,
                LOCATION_REQUEST_CODE);
    }
}
```

当现在运行应用程序时，将显示图 85-10 所示对话框，请求位置权限。如果授予权限，地图上将出现一个蓝点，表示设备的位置。

![image-E7J7648R.jpg](img/image-E7J7648R.jpeg)

图 85-10

## 85.13 修改地图类型

可以通过调用相应`GoogleMap`对象的`setMapType()`方法来动态修改显示的的地图类型，并传递以下值之一：

- `GoogleMap.MAP_TYPE_NONE` – 一个不显示任何地图瓦片的空网格。
- `GoogleMap.MAP_TYPE_NORMAL` – 由经典道路地图组成的标准视图。
- `GoogleMap.MAP_TYPE_SATELLITE` – 显示地图区域的卫星图像。
- `GoogleMap.MAP_TYPE_HYBRID` – 显示叠加了道路地图的卫星图像。
- `GoogleMap.MAP_TYPE_TERRAIN` – 显示等高线和颜色等地形地形信息。

例如，对`onMapReady()`方法进行以下代码更改可以将地图切换到卫星模式：

```java
.

.

if (mMap != null) {
    int permission = ContextCompat.checkSelfPermission(
            this, Manifest.permission.ACCESS_FINE_LOCATION);

    if (permission == PackageManager.PERMISSION_GRANTED) {
        mMap.setMyLocationEnabled(true);
    } else {
        requestPermission(
                Manifest.permission.ACCESS_FINE_LOCATION,
                LOCATION_REQUEST_CODE);
    }

    mMap.setMapType(GoogleMap.MAP_TYPE_SATELLITE);
}

.

.
```

或者，可以在嵌入地图的 XML 布局文件中指定地图类型，使用`map:mapType`属性结合`none`、`normal`、`hybrid`、`satellite`或`terrain`之一的值。例如：

```xml
xmlns:map="http://schemas.android.com/apk/res-auto"

android:id="@+id/map"
android:layout_width="match_parent"
android:layout_height="match_parent"
map:mapType="hybrid"
android:name="com.google.android.gms.maps.SupportMapFragment"/>
```

## 85.14 向用户显示地图控件

Google Maps Android API 提供了若干可以可选显示给用户的控件，包括缩放放大缩小按钮、“我的位置”按钮和指南针。

缩放和指南针控件的显示可以通过编程控制，也可以在 XML 布局资源文件的地图元素中控制。要通过编程配置控件，必须获取与`GoogleMap`对象关联的`UiSettings`对象的引用：

```java
import com.google.android.gms.maps.UiSettings;

.

.

UiSettings mapSettings;
mapSettings = mMap.getUiSettings();
```

缩放控件通过调用`UiSettings`对象的`setZoomControlsEnabled()`方法来开启或关闭。例如：

```java
mapSettings.setZoomControlsEnabled(true);
```

或者，可以在 XML 资源文件的地图元素中设置`map:uiZoomControls`属性：

```xml
map:uiZoomControls="false"
```

指南针可以通过调用`UiSettings`实例的`setCompassEnabled()`方法或通过 XML 资源使用`map:uiCompass`属性来显示。请注意，指南针图标仅在地图相机倾斜或偏离默认方向时才会出现。

正如本章前面提到的，“我的位置”按钮只有在启用“我的位置”模式时才会出现。即使在这种模式下，也可以通过调用`UiSettings`实例的`setMyLocationButtonEnabled()`方法防止按钮显示。

## 85.15 处理地图手势交互

Google Maps Android API 可以响应各种用户交互。这些交互可以用于更改显示的地图区域、缩放级别，甚至是视角（例如为某些城市显示地图区域的 3D 表示）。

### 85.15.1 地图缩放手势

可以使用与`GoogleMap`实例关联的`UiSettings`对象的`setZoomGesturesEnabled()`方法开启或关闭地图缩放手势的支持。例如，以下代码关闭了示例地图的缩放手势：

```java
UiSettings mapSettings;
mapSettings = map.getUiSettings();
mapSettings.setZoomGesturesEnabled(false);
```

在 XML 资源文件中将`map:uiZoomGestures`属性设置为`true`或`false`可以实现相同的结果。

启用后，当用户在屏幕上进行捏合手势时，将发生缩放。同样，双击会放大，而双指轻击会缩小。相反，单指缩放手势是通过双击但不松开第二次轻击，然后在屏幕上上下滑动手指分别进行放大和缩小来实现的。

### 85.15.2 地图滚动/平移手势

滚动或平移手势允许用户通过单指动作在屏幕上拖动地图来移动。可以通过`UiSettings`实例的`setScrollGesturesEnabled()`方法在代码中启用滚动手势：

```java
UiSettings mapSettings;
mapSettings = mMap.getUiSettings();
mapSettings.setScrollGesturesEnabled(true);
```

或者，可以在 XML 资源文件中启用`map:uiGestures`属性。

### 85.15.3 地图倾斜手势

倾斜手势允许用户通过在屏幕上放置两个手指并上下移动它们来调整倾斜角度，改变地图投影的角度。可以通过`UiSettings`实例的`setTiltGesturesEnabled()`方法开启或关闭倾斜手势，例如：

```java
UiSettings mapSettings;
mapSettings = mMap.getUiSettings();
mapSettings.setTiltGesturesEnabled(true);
```

倾斜手势也可以通过 XML 布局文件中的`map:uiTilt`属性开启或关闭。

### 85.15.4 旋转手势

在启用旋转手势的情况下，用户可以通过在屏幕上放置两个手指并旋转它们来旋转地图的方向。这种手势的支持通过调用`UiSettings`实例的`setRotateGesturesEnabled()`方法在代码中开启或关闭，例如：

```java
UiSettings mapSettings;
mapSettings = mMap.getUiSettings();
mapSettings.setRotateGesturesEnabled(true);
```

旋转手势也可以通过 XML 布局文件中的`map:uiRotate`属性开启或关闭。

## 85.16 创建地图标记

标记向用户通知地图上的位置，形式可以是标准图标或自定义图标。标记还可以包含标题和可选文本（称为 snippet），并可以配置为允许用户拖动到地图的不同位置。当用户点击标记时，将出现信息窗口，显示有关标记位置的附加。

标记由`Marker`类实例表示，并通过调用相应`GoogleMap`对象的`addMarker()`方法添加到地图中。将包含标记所需的各种选项（如标题和 snippet）的`MarkerOptions`实例作为参数传递给方法。例如，以下代码在地图上的特定位置添加了一个包含标题、snippet 的标记：

```java
import com.google.android.gms.maps.model.Marker;
import com.google.android.gms.maps.model.LatLng;
import com.google.android.gms.maps.model.MarkerOptions;

.

.

.

LatLng position = new LatLng(38.8874245, -77.0200729);

Marker museum = mMap.addMarker(new MarkerOptions()
        .position(position)
        .title("Museum")
        .snippet("National Air and Space Museum"));
```



执行上述代码后，将标记指定的位置，点击该位置时将显示一个包含标题和代码片段的 `info` 窗口，如图 85-11 所示：

![image-GIT2GATE.jpg](img/image-GIT2GATE.jpeg)

图 85-11

## 85.17 控制地图相机

由于 Android 设备的屏幕是平面的，而地球是球体，因此 Google Maps Android API 使用墨卡托投影在平面上表示地球。地图的默认视图呈现给用户，就像通过一个悬挂在地图上方并直接指向地图的相机一样。Google Maps Android API 允许在应用程序内部更改此相机的目标、缩放、方位角和倾角：

- Target（目标）——设备显示屏地图中心的位置，通过经度和纬度指定。
- Zoom（缩放）——以级别指定的相机缩放级别。缩放级别增加 1.0 将显示地图内容的宽度增加一倍。
- Tilt（倾角）——相机的视角角度，指定为跨越可视地图区域正上方的弧线位置，以从弧顶开始的度数测量（弧顶为相机直接指向地图的底点）。
- Bearing（方位角）——地图的方向，以北为基准顺时针方向测量的数。

通过创建一个具有适当设置的 `CameraUpdate` 类实例来完成相机更改。`CameraUpdate` 实例是通过对 `CameraUpdateFactory` 类的方法调用来创建的。一旦创建了 `CameraUpdate` 实例，就可以通过调用 `GoogleMap` 实例的 `moveCamera()` 方法将其应用到地图。为了在相机更改时获得平滑的动画效果，可以调用 `animateCamera()` 方法代替 `moveCamera()`。

`CameraUpdateFactory` 方法的摘要如下：

- `CameraUpdateFactory.zoomIn()` – 提供一个缩放一层级的 `CameraUpdate` 实例。
- `CameraUpdateFactory.zoomOut()` - 提供一个缩小一层级的 `CameraUpdate` 实例。
- `CameraUpdateFactory.zoomTo(float)` - 生成一个将缩放级别更改为指定值的 `CameraUpdate` 实例。
- `CameraUpdateFactory.zoomBy(float)` – 提供一个缩放级别增加或减少指定量的 `CameraUpdate` 实例。
- `CameraUpdateFactory.zoomBy(float, Point)` - 创建一个按指定值增加或减少缩放级别的 `CameraUpdate` 实例。
- `CameraUpdateFactory.newLatLng(LatLng)` - 创建一个更改相机目标经度和纬度的 `CameraUpdate` 实例。
- `CameraUpdateFactory.newLatLngZoom(LatLng, float)` - 生成一个更改相机纬度、经度和缩放的 `CameraUpdate` 实例。
- `CameraUpdateFactory.newCameraPosition(CameraPosition)` - 返回一个将相机移动到指定位置的 `CameraUpdate` 实例。可以使用 `CameraPosition.Builder()` 获取 `CameraPosition` 实例。

例如，以下代码使用动画将相机缩放大了一级：

```java
mMap.animateCamera(CameraUpdateFactory.zoomIn());
```

另一方面，以下代码将相机移动到新位置并将缩放级别调整为 10，且没有动画：

```java
private static final LatLng position =

new LatLng(38.8874245, -77.0200729);

mMap.moveCamera(CameraUpdateFactory.newLatLngZoom(position, 10));
```

最后，下一个代码示例使用 `CameraPosition.Builder()` 创建一个具有目标、缩放、方位角和倾角变化的 `CameraPosition` 对象。然后使用动画将此更改应用到相机：

```java
import com.google.android.gms.maps.model.CameraPosition;

import com.google.android.gms.maps.CameraUpdateFactory;

CameraPosition cameraPosition = new CameraPosition.Builder()

    .target(position)

    .zoom(50)

    .bearing(70)

    .tilt(25)

    .build();

mMap.animateCamera(CameraUpdateFactory.newCameraPosition(cameraPosition));
```

## 85.18 总结

本章提供了构成 Google Maps Android API 的关键类和方法，并概述了如何准备开发环境和应用程序项目以使用该 API。

# 86. 使用 Android 打印框架打印

Android Printing Framework 用于从 Android 应用程序内部打印内容。随后的章节将更详细地探讨为应用程序添加打印支持的选项，但本章将关注目前 Android 中提供的各种打印选项以及启用这些选项的步骤。

该章节将提供 Android 开发者可用于在应用程序中构建打印支持的各种打印功能的概述。

## 86.1 Android 打印架构

打印框架为 Android 提供了打印功能。从根本上说，该框架由打印管理器（Print Manager）和若干打印服务插件（print service plugins）组成。

打印管理器负责处理设备上应用程序的打印请求，并与安装在设备上的打印服务插件交互，从而确保打印请求。默认情况下，许多 Android 设备安装了打印服务插件，以便使用 Google Cloud Print 和 Google Drive 服务进行打印。其他类型打印机的打印服务插件如果没有安装，也可以从 Google Play 商店获取。

打印服务插件目前适用于 HP、爱普生、三星和佳能打印机，其他打印机制造商的插件极可能在未来发布。然而，Google Cloud Print 服务插件可以从几乎任何类型的打印机打印。

本书将使用 HP 打印服务插件作为示例。

## 86.2 打印服务插件

打印服务插件的目的是允许应用程序打印到通过本地网络或蓝牙可见的兼容打印机。

可以通过加载 Google Play 应用并搜索 `Print Service Plugin` 来验证 Android 设备上是否存在打印服务插件。

一旦插件出现在商店列表中，且尚未安装，即可点击“安装”按钮进行安装。图 86-1 显示了 Google Play 中的 HP 服务插件。

打印服务插件会自动检测 Android 设备当前连接的网络上的兼容打印机，并将它们列为应用程序打印的选项。

![image-8Q500M.jpg](images/8Q5XT0M.jpeg)

图 86-1

## 86.3 Google Cloud Print

Google Cloud Print 是 Google 提供的一种服务，允许您从任何具有互联网连接的地方通过网络将内容打印到打印机上。Google Cloud Print 支持云端和经典的许多设备和模型。云端打印机内置了通过网络打印的技术。提供云端打印机的制造商包括博世、佳能、戴尔、爱普生、HP、柯达和三星。要识别您的打印机是否支持云端且受 Google Cloud Print 支持，请查看以下 URL 中的打印机列表：

`https://www.google.com/cloudprint/learn/printers.html`

对于经典的非云端打印机，Google Cloud Print 通过在连接到经典打印机的计算机系统上（直接连接或通过家庭或办公室网络）安装软件来提供云打印支持。

要设置 Google Cloud Print，请访问以下网页并使用与您登录 Android 设备时相同的 Google 账户登录：

`https://www.google.com/cloudprint/learn/index.html`

一旦打印机添加到您的 Google Cloud Print 账户，当您从 Android 应用程序内部打印时，它们将列为打印目标选项。

## 86.4 打印到 Google Drive

除了支持实体打印机外，还可以将打印输出保存到您的 Google Drive 账户。从设备打印时，请在打印面板中选择 `Save to Google Drive` 选项。待打印内容将被转换为 PDF 文件，并保存到与设备上当前激活的 `Google Account ID` 相关的 Google Drive 云存储中。

## 86.5 保存为 PDF

Android 提供的最终打印选项允许将打印内容作为 PDF 文件本地保存到 Android 设备上。一旦选择此选项，系统将要求为 PDF 文件指定名称以及在设备上保存文档的存储位置。

在测试自己的 Android 应用程序的打印功能时，`Save as PDF` 和 `Google Drive` 选项在节省纸张方面可能极具价值。

## 86.6 从 Android 设备上打印

Google 建议可以打印内容的应用程序通过将打印选项放置在溢出菜单（Overflow menu）中。许多与 Android 绑定的应用程序现在都包含了“打印…”菜单选项。例如，图 86-2 显示了通过选择 Chrome 浏览器应用程序溢出菜单中的“共享…”选项来访问打印选项：

![image-ZLM0IG6U.jpg](img/image-ZLM0IG6U.jpeg)

图 86-2

一旦在应用程序内选择了打印选项，将出现标准的 Android 打印屏幕，显示待打印内容的预览，如图 86-3 所示：

![image-A1EVFE6E.jpg](img/image-A1EVFE6E.jpeg)

图 86-3

点击屏幕顶部的面板将显示完整的打印选项：

![image-KROWSLOZ.jpg](img/image-KROWSLOZ.jpeg)

图 86-4

Android 打印面板提供了标准的打印选项，如纸张大小、颜色、方向和打印份数。通过点击当前打印机或 PDF 输出选择，可以访问其他打印目标选项。

## 86.7 在 Android 应用中构建打印支持的选项

打印框架（Printing framework）为在 Android 应用程序中整合打印支持提供了多种选项。这些选项可以分类如下：

### 86.7.1 图像打印

如所示，此选项允许将图像打印集成到 Android 应用程序中。在应用程序中添加此功能时，第一步是创建一个 `PrintHelper` 类的新实例：

```java
PrintHelper imagePrinter = new PrintHelper(context);
```

接下来，可以通过调用 `PrintHelper` 实例的 `setScaleMode()` 方法指定打印图像的缩放模式。选项如下：

- `SCALE_MODE_FIT` – 图像将缩放以适应纸张大小，而不进行裁剪或更改纵横比。这通常会导致在某个维度上出现空白区域。
- `SCALE_MODE_FILL` – 图像将缩放以填充纸张大小，并在必要时进行裁剪，以避免打印输出中出现空白区域。

如果不设置缩放模式，系统将默认使用 `SCALE_MODE_FILL`。例如，以下代码在之前声明的 `PrintHelper` 实例上将缩放设置为适应模式：

```java
imagePrinter.setScaleMode(PrintHelper.SCALE_MODE_FIT);
```

同样，也可以配置颜色模式，以指示打印输出是彩色还是黑白。这是通过向 `PrintHelper` 实例的 `setColorMode()` 方法传递以下选项之一来完成的：

- `COLOR_MODE_COLOR` – 表示图像将以彩色打印。
- `COLOR_MODE_MONOCHROME` – 表示图像将以黑白打印。

除非按如下指定单色选项，否则打印框架将默认彩色打印：

```java
imagePrinter.setColorMode(PrintHelper.COLOR_MODE_MONOCHROME);
```

完成打印操作所需的只是一个待打印的图像以及调用 `PrintHelper` 实例的 `printBitmap()` 方法，该方法需要传递一个代表分配给打印任务名称的字符串以及图像的引用（以 `Bitmap` 对象或 `Uri` 引用的形式）：

```java
Bitmap bitmap = BitmapFactory.decodeResource(getResources(),

R.drawable.oceanscene);

imagePrinter.printBitmap("My Test Print Job", bitmap);
```

一旦启动打印任务，打印框架将显示打印对话框，并处理后续与用户的交互以及在用户选择的打印目标上打印图像。

### 86.7.2 创建并打印 HTML 内容

Android 打印框架还提供了一种在应用程序内打印基于 HTML 内容的简单方法。这些内容可以是由托管在网站上的页面 URL 引用的 HTML 内容，也可以是在应用程序内部动态创建的 HTML 内容。

为了启用 HTML 打印，`WebView` 类已经过扩展，以最少的代码要求支持打印。

在动态创建 HTML 内容（与加载和打印现有网页相比）时，该过程涉及创建一个 `WebView` 对象并与其关联一个 `WebViewClient` 实例。然后配置 web 客户端，在 HTML 加载到 `WebView` 之后启动打印任务。配置好 web 客户端后，HTML 被加载到 `WebView` 中，并触发打印过程。

例如，考虑以下代码：

```java
public void printContent()

{

    WebView webView = new WebView(this);

    webView.setWebViewClient(new WebViewClient() {

        public boolean shouldOverrideUrlLoading(WebView view,

        String url)

        {

            return false;

        }

        @Override

        public void onPageFinished(WebView view, String url) {

            createPrintJob(view);

            myWebView = null;

        }

    });

    String htmlDocument =

    "# Android Print Test"

    + "This is sample content.";

    webView.loadDataWithURL(null, htmlDocument,

    "text/HTML", "UTF-8", null);

    myWebView = webView;

}
```

该方法的代码首先声明一个变量 `myWebView`，其中将存储方法中创建的 `WebView` 实例。在 `printContent()` 方法中，创建一个 `WebView` 类实例，并为其分配一个 `WebViewClient` 实例。

分配给 web 对象的 `WebViewClient` 被配置为指示 HTML 内容的加载由 `WebView` 实例处理（通过从 `shouldOverrideUrlLoading()` 方法返回 `false`）。更重要的是，声明并实现 `onPageFinished()` 处理方法来调用 `createPrintJob()` 方法。当所有 HTML 内容加载到 web view 时，会自动调用 `onPageFinished()` 回调方法。这确保了在准备就绪之前不会启动打印任务，确保所有内容都被打印。

接下来，创建一个包含某些 HTML 的字符串作为内容。然后将其加载到 web view 中。一旦 HTML 加载，将触发 `onPageFinished()` 方法。最后，该方法存储 web view 对象的引用。如果没有这一至关重要的步骤，Java 运行时系统可能会认为应用程序不再需要该 web view 对象并丢弃它以释放内存（Java 术语中称为垃圾回收），从而导致打印任务在完成之前就终止。

此示例中剩下的工作是按所示实现 `createPrintJob()` 方法：

```java
private void createPrintJob(WebView webView) {

    PrintManager printManager = (PrintManager) this

    .getSystemService(Context.PRINT_SERVICE);

    PrintDocumentAdapter printAdapter =

    webView.createPrintDocumentAdapter("MyDocument");

    String jobName = getString(R.string.app_name) + " Document";

    PrintJob printJob = printManager.print(jobName, printAdapter,

    new PrintAttributes.Builder().build());

}
```



该方法获取`PrintManager`服务的引用，并指令web视图实例创建一个打印适配器。将创建一个新的字符串来存储打印任务的名称（在这种情况下，该名称基于应用程序名称和“Document”一词）。

最后，通过调用打印管理器的`print()`方法来启动打印任务，并传递任务名称、打印适配器以及一组默认打印属性。如果需要的话，可以对打印属性进行自定义，以指定分辨率（每英寸点数）、页边距和颜色选项。

## 86.7.3 打印网页

打印网页涉及的步骤与上述概述的步骤相似，不同之处在于传递web视图的是要打印网页的URL，而不是动态创建的HTML，例如：

```
myWebView.loadUrl("https://developer.android.com/google/index.html");
```

同样重要的是，只有当需要网页在加载加载后立即自动打印时，才需要配置`WebViewClient`。如果打印操作是由用户在页面加载后通过选择菜单选项来启动的，则只需要在应用代码中包含上述概述的`createWebPrintJob()`方法中的代码。下一章“Android HTML和Web内容打印示例”将演示此类场景。

## 86.7.4 打印自定义文档

虽然打印框架引入的HTML和Web打印功能为从Android应用内部打印内容提供了方便路径，但显而易见，对于更高级的打印需求，这些选项过于简单。打印框架还为更复杂的打印任务提供了自定义文档打印支持。这允许将文本和图形形式的内容绘制到画布上然后打印。

与可以相对容易实现的HTML和图像打印不同，自定义文档打印是一个更复杂、多阶段的过程，该过程将在本书的“Android自定义文档打印指南”章节中概述。这些步骤可以总结如下：

- 连接到Android打印管理器
- 创建一个子类自`PrintDocumentAdapter`类的自定义打印适配器
- 创建一个`PdfDocument`实例来表示文档页面
- 获取`PdfDocument`实例页面的引用，每个页面都关联着一个`Canvas`实例
- 在页面画布上绘制内容
- 通知打印框架文档已准备好打印

上述步骤中概述的自定义打印适配器必须实现几个方法，Android系统将在打印期间调用这些方法来执行特定任务。其中最重要的是`onLayout()`方法，它负责响应用户更改纸张大小或页面方向等设置重新排列文档布局，以及`onWrite()`方法，它负责渲染要打印的页面。题为“Android自定义文档打印指南”章节将详细介绍此主题。

## 86.8 总结

Android SDK可以从运行应用内部打印内容。打印输出可以重定向到配置适当的打印机、本地PDF文件或通过Google Drive传输到云端。从Android应用开发者的角度来看，通过使用打印框架，可以在应用程序中使用这些功能。到目前为止，最简单的打印选项是涉及图像和HTML形式的内容。然而，更高级的打印可以使用框架的自定义文档打印功能实现。

## 87. 一个Android HTML和Web内容打印示例

正如上一章“使用Android打印框架打印”概述的那样，Android打印框架可以同时打印网页和动态创建的HTML内容。虽然这两种打印方法有许多相似之处，但也存在一些需要考虑的微妙差异。本章将通过创建两个示例应用程序来使这两种打印选项更加清晰。

## 87.1 创建HTML打印示例应用

从欢迎屏幕上选择“New Project”（新建项目）选项，并在弹出的新项目对话框中，点击“Next”（下一步）按钮之前选择“Empty Views Activity”模板。

在Name字段中输入`HTMLPrint`并指定`com.ebookfrenzy.htmlprint`为包名。在点击“Finish”（完成）按钮之前，将Minimum API level设置为API 26: Android 8.0 (Oreo)，并将Language语言菜单设置为Java。

## 87.2 打印动态HTML内容

本教程的第一阶段是向项目添加代码以创建一些HTML内容并将其作为打印任务发送到打印框架。

首先找到`MainActivity.java`文件（位于Project工具窗口的`app -> java -> com.ebookfrenzy.htmlprint`下），并将其加载到编辑面板。加载后，修改代码使其读取如下列表所示：

```java
package com.ebookfrenzy.htmlprint;

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

        WebView webView = new WebView(this);

        webView.setWebViewClient(new WebViewClient() {

            public boolean shouldOverrideUrlLoading(WebView view,

            WebResourceRequest request)

            {

                return false;

            }

            @Override

            public void onPageFinished(WebView view, String url)

            {

                createWebPrintJob(view);

                myWebView = null;

            }

        });

        String htmlDocument = "# Android Print Test"

        + " This is sample content.";

        webView.loadDataWithBaseURL(null, htmlDocument,

        "text/HTML", "UTF-8", null);

        myWebView = webView;

    }

}
```

代码更改从声明变量`myWebView`开始，该变量将存储用于打印操作的`WebView`实例。在`printWebView()`方法中，创建`WebView`类的实例，并为其分配一个`WebViewClient`实例。

分配给web对象的`WebViewClient`配置为由`WebView`实例处理HTML内容（通过从`shouldOverrideUrlLoading()`方法返回`false`）。更重要的是，声明并实现了一个`onPageFinished()`处理方法以调用`createWebPrintJob()`方法。当所有HTML内容加载到web中时，会自动调用`onPageFinished()`方法。正如上一章概述，当打印动态HTML内容时此步骤是必要的，以确保在内容完全加载到`WebView`之后才启动打印任务。

接下来，创建一个包含某些内容的String对象并随后加载到web中。一旦HTML加载，`onPageFinished()`回调方法就会触发。最后，该方法将web对象的引用存储在先定义的`myWebView`变量中。没有这个关键步骤，Java运行时系统可能会认为应用程序不再需要该web对象并将其丢弃以释放内存，导致打印任务在完成之前就终止。

此示例中剩下的只需实现`createWebPrintJob()`方法，该方法目前配置为由`onPageFinished()`回调方法调用。因此，留在`MainActivity.java`文件中，实现此方法使其读取如下：

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

此方法获取了`PrintManager`服务的引用，并指示web view实例创建一个打印适配器。会创建一个新字符串来存储打印任务的名称（在本例中，基于应用程序名称和“Print Test”字样）。

最后，通过调用打印管理器的`print()`方法启动打印任务，并传递任务名称、打印适配器以及一组默认打印属性。

在运行Android 5.0或更高版本的设备或模拟器上编译并运行应用程序。启动后，将出现如图87-1所示的标准Android打印页面。

![image-ORJ6ODIB.jpg](img/image-ORJ6ODIB.jpeg)

图 87-1

如果你配置了物理打印机，请打印到该打印机；保存到Google Drive；或选择保存为PDF文件。一旦启动打印任务，请在所选目标位置检查生成的输出。请注意，当使用“保存为PDF”选项时，系统会要求指定PDF文件的名称和位置。下载文件夹是一个很好的选择，可以通过点击设备上其他应用图标之间的Downloads图标（在Android 8中重命名为Files）来查看其内容。

## 87.3 创建网页打印示例

在本章创建的第二个示例应用程序将为用户提供一个溢出菜单（Overflow menu）选项，用于打印当前在`WebView`实例中显示的网页。

从欢迎界面界面选择`New Project`（新建项目）选项，在弹出的新项目对话框中，点击`Next`（下一步）按钮之前选择`Basic Views Activity`模板。

在`Name`（名称）字段中输入`WebPrint`并指定`com.ebookfrenzy.webprint`为包名。在点击`Finish`（完成）按钮之前，将`Minimum API level`（最低API级别）设置改为`API 26: Android 8.0 (Oreo)`，并将`Language`（语言）菜单改为`Java`。

## 87.4 移除浮操作按钮

选择`Basic Views Activity`模板提供了一个上下文菜单和一个浮按钮（floating action button）。由于应用程序不需要浮操作按钮，可以在继续之前将其移除。将`activity_main.xml`布局文件加载到`Layout Editor`（布局编辑器）中，选择浮按钮，并按键盘`Delete`键从布局删除该对象。编辑`MainActivity.java`文件，从`onCreate`方法中删除浮按钮代码，如下所示：

```java
@Override

protected void onCreate(Bundle savedInstanceState) {

    super.onCreate(savedInstanceState);

    binding = ActivityMainBinding.inflate(getLayoutInflater());

    setContentView(binding.getRoot());

    setSupportActionBar(binding.toolbar);

/*

    binding.fab.setOnClickListener(new View.OnClickListener() {

        @Override

        public void onClick(View view) {

            Snackbar.make(view, "Replace with your own action",

                Snackbar.LENGTH_LONG)

                .setAction("Action", null).show();

        }

    });

}

*/
```

## 87.5 移除导航功能

正如“Android Studio布局编辑器工具指南”概述所示，“Basic Views Activity`模板包含多个片段（fragments）和按钮，用于从一个片段导航到另一个片段。这些功能对于本教程是不必要的，如果不移除会导致会导致问题。在继续教程之前，按照如下方式修改项目：

1. 在`Project`工具窗口中，导航并双击`app -> res -> navigation -> nav_graph.xml`文件，将其加载到导航编辑器中。

2. 在编辑器中，选择图面板中的`SecondFragment`条目，并按键盘删除键将其从图中移除。

3. 找到并删除`SecondFragment.java`（`app -> java -> -> SecondFragment`）和`fragment_second.xml`（`app -> res -> layout -> fragment_second.xml`）文件。

4. 找到`FirstFragment.java`文件，双击将其加载到编辑器中，并移除`onViewCreated()`方法中的代码，使其内容如下：

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

5. 编辑`MainActivity.java`文件并移除以下导航代码：



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

@Override
public boolean onSupportUp() {
    NavController navController = Navigation.findNavController(this, R.id.nav_host_fragment_content_main);
    return NavigationUI.navigateUp(navController, appBarConfiguration);
}
```

## 87.6 设计用户界面

将 `content_main.xml` 布局资源文件加载到 `Layout Editor` 中（如果尚未加载），并在设计模式下选择 `content_main` 对象。从调色板的 `Widgets` 部分拖放一个 `WebView` 对象到屏幕中心。点击 `Infer constraints`（推断约束）按钮，并在 `Attributes` 工具窗口将 `WebView` 的 `layout_width` 和 `layout_height` 属性匹配，如图 87-2 所示。

选择新添加的 `WebView` 实例并将视图 ID 改为 `myWebView`。

在继续教程下一步之前，必须向项目添加额外的权限，以便 `WebView` 对象能够访问互联网下载打印网页。通过在 `Project` 工具窗口中找到 `AndroidManifest.xml` 文件并双击将其加载。加载后，按照如下所示修改 XML 内容添加权限行：

```xml
package="com.ebookfrenzy.webprint" >
android:allowBackup="true"
```

![image-3SQSRYO.jpg](img/image-3SQSRYO.jpeg)

图 87-2

## 87.7 从主 Activity 访问 WebView

正如“RecyclerView 和 CardView 教程”中的项目一样，我们需要能够使用视图绑定（view binding）从 `MainActivity` 类中访问 `content_main.xml` 文件中的组件（此处为 `myWebView`）。为了访问 `content_main.xml` 文件中的视图，我们再次需要在包含处分配一个 ID。编辑 `activity_main.xml` 文件并修改 `include` 元素如下：

```xml
android:id="@+id/contentMain"

layout="@layout/content_main" />
```

## 87.8 将网页加载到 WebView

在打印网页之前，必须将其加载到 `WebView` 实例。在本教程中，这将通过调用 `WebView` 实例的 `loadUrl()` 方法来实现，该调用将放置在 `configureWebView()` 方法中，并在 `MainActivity` 类的 `onStart()` 方法中调用。因此，编辑 `MainActivity.java` 文件并修改如下：

```java
package com.ebookfrenzy.webprint;

import android.view.Menu;
import android.view.MenuItem;
import android.webkit.WebView;
import android.webkit.WebViewClient;
import android.webkit.WebResourceRequest;

public class MainActivity extends AppCompatActivity {
```

```java
private WebView myWebView;

@Override
protected void onStart() {
    super.onStart();
    configureWebView();
}

private void configureWebView() {
    myWebView = findViewById(R.id.myWebView);

    myWebView.setWebViewClient(new WebViewClient() {
        @Override
        public boolean shouldOverrideUrlLoading(
                WebView view, WebResourceRequest request) {
            return super.shouldOverrideUrlLoading(
                view, request);
        }
    });

    myWebView.loadUrl("https://www.payloadbooks.com");
}
```

## 87.9 添加打印菜单选项

现在将使用“在 Android 上创建和管理溢出菜单”章节中概述的技术，将打印网页的选项添加到溢出菜单中。第一个要求是用于菜单选项标签的字符串资源。在 `Project` 工具窗口中，找到 `app -> res -> values -> strings.xml` 文件，双击它将其加载到编辑器中，并修改它以添加新的字符串资源：

- `WebPrint`
- `Settings`
- `Print`

接下来，将 `app -> res -> menu -> menu_main.xml` 文件加载到菜单编辑器，切换到 `Code`，并将 `Settings` 菜单选项替换为打印选项：

```xml
xmlns:tools="http://schemas.android.com/tools"

tools:context="com.ebookfrenzy.webprint.MainActivity" >

android:id="@+id/action_settings"

android:title="@string/action_settings"

android:orderInCategory="100"

app:showAsAction="never" />

android:id="@+id/action_print"

android:orderInCategory="100"

app:showAsAction="never"

android:title="@string/print_string"/>
```

配置菜单选项剩下的工作是修改 `MainActivity.java` 文件中的 `onOptionsItemSelected()` 处理器方法：

```java
@Override
public boolean onOptionsItemSelected(MenuItem item) {
    int id = item.getItemId();

    if (id == R.id.action_print) {
        createWebPrintJob(myWebView);
        return true;
    }

    return super.onOptionsItemSelected(item);
}
```

实现 `onOptionsItemSelected()` 方法后，当从溢出菜单中选择打印菜单选项时，活动将调用名为 `createWebPrintJob()` 的方法。该方法的实现与之前的 `HTMLPrint` 项目中使用的相同，现在可以将其添加到 `MainActivity.java` 文件中，其内容如下：

```java
package com.ebookfrenzy.webprint;

import android.print.PrintAttributes;
import android.print.PrintDocumentAdapter;
import android.print.PrintManager;
import android.content.Context;

public class MainActivity extends AppCompatActivity {

    private WebView myWebView;

    private void createWebPrintJob(WebView webView) {
        PrintManager printManager = (PrintManager) this
            .getSystemService(Context.PRINT_SERVICE);

        PrintDocumentAdapter printAdapter =
            webView.createPrintDocumentAdapter("MyDocument");

        String jobName = getString(R.string.app_name) + " Print Test";

        printManager.print(jobName, printAdapter,
            new PrintAttributes.Builder().build());
    }
}
```

代码更改完成后，在物理 Android 设备或模拟器上运行应用程序。成功启动后，`WebView` 应该显示并加载指定的网页。页面加载后，从溢出菜单中选择 `Print` 选项，并使用生成的打印面板将网页打印到合适的目的地。

![image-7AAUCGG7.jpg](img/image-7AAUCGG7.jpeg)

图 87-3

## 87.10 总结

Android 打印框架包含了 `WebView` 类的扩展，允许从 Android 应用程序内部打印基于 HTML 的内容。这些内容可以是应用程序在运行时动态创建的 HTML，也可以是加载到 `WebView` 实例的现有网页。对于动态创建的 HTML，使用 `WebViewClient` 实例至关重要，以确保在 HTML 完全加载到 `WebView` 之前不会开始打印。

# 88. Android 自定义文档打印指南

正如前面的章节中所看到的，如果内容以图像或 HTML 标记的形式存在，Android 打印框架为应用程序构建打印支持变得相对。更高级的打印需求可以通过打印框架的自定义文档打印功能来满足。

## 88.1 Android 自定义文档打印概述

简单来说，自定义文档打印使用画布（canvases）来表示要打印的文档页面。应用程序将要打印的内容作为形状、颜色、文本和图像绘制在这些画布上。画布由 `Android Canvas` 类的实例表示，提供了丰富的绘制选项访问。一旦所有页面都绘制完成，文档就会被打印。

虽然这听起来足够简单，但需要执行一些步骤来实现，这些步骤可以总结如下：

- 实现一个继承自 `PrintDocumentAdapter` 类的自定义打印适配器。
- 获取 `Print Manager Service` 的引用。
- 创建 `PdfDocument` 类的实例以存储文档页面。
- 以 `PdfDocument.Page` 实例的形式将页面添加到 `PdfDocument` 中。
- 获取与文档页面相关的 `Canvas` 对象的引用。
- 在画布上绘制内容。
- 将 `PDF` 文档写入到打印框架提供的目标输出流。
- 通知打印框架文档已准备好打印。

本章将提供这些步骤的概述，随后是一个旨在在 Android 应用程序中实现自定义文档打印的详细教程。

### 88.1.1 自定义打印适配器

打印适配器的作用是为打印框架提供要打印的内容，并确保根据用户的偏好（如纸张大小）进行格式化。

许多工作是由框架提供的打印适配器完成的，这些适配器专为打印 HTML 和图像的任务设计。例如，在打印网页时，当调用 `WebView` 实例的 `createDocumentAdapter()` 方法时，就会创建一个打印适配器。

然而，在自定义文档打印的情况下，由应用程序开发者设计打印适配器并实现为打印做准备的代码。

自定义打印适配器通过子类 `PrintDocumentAdapter` 类并重写该类中的一组回调方法来创建，这些方法将在打印过程的不同阶段由打印框架调用。这些回调方法总结如下：

- `onStart()`：此方法在打印过程开始时调用，以便应用程序代码可以执行创建打印作业的必要任务。在 `PrintDocumentAdapter` 子类中实现此方法是可选的。
- `onLayout()`：此回调方法在调用 `onStart()` 方法后以及随后用户每次更改打印设置（如更改方向、纸张大小或颜色设置）时调用。该方法应调整内容和布局以适应这些更改。更改完成后，方法必须返回要打印的页面数。在 `PrintDocumentAdapter` 子类中实现 `onLayout()` 方法是强制的。
- `onWrite()`：此方法在每次调用 `onLayout()` 之后调用，负责在要打印页面的画布上渲染内容。除了其他参数外，此方法还传递了一个文件描述符，一旦渲染完成，必须将生成的 `PDF` 文档写入其中。然后会调用 `onWriteFinished()` 回调方法，传递一个包含要打印页面范围信息的参数。在 `PrintDocumentAdapter` 子类中实现 `onWrite()` 方法是强制的。
- `onFinish()`：一个可选方法。如果实现了该方法，打印框架将在打印过程完成后由其调用一次，从而为应用程序提供执行任何必要的清理操作的机会。

## 88.2 准备自定义文档打印项目

从欢迎屏幕上选择 `New Project` 选项，在生成的新项目对话框中，点击 `Next` 按钮之前选择 `Empty Views Activity` 模板。

在 `Name` 字段中输入 `CustomPrint`，并指定 `com.ebookfrenzy.customprint` 为包名。在点击 `Finish` 按钮之前，将 `Minimum API level`（最小 API 级别）设置为 `API 26`: Android 8.0 (Oreo)，并将 `Language` 菜单设置为 `Java`。

## 88.3 设计 UI

将 `activity_main.xml` 布局文件加载到 `Layout Editor` 工具中，并在 `Design` 模式下，选择并删除“Hello World!” `TextView` 对象。从调色板的 `Common` 部分拖入一个 `Button` 视图并将其放置在布局视图的中心。选中 `Button` 视图后，将 `text` 属性更改为“Print Document”并将字符串提取到新资源中。完成后，用户界面布局应与图 88-1 所示。

当在应用程序中选中按钮时，需要调用一个方法来启动文档打印过程。继续留在 `Attributes` 工具窗口中，设置 `onClick` 属性以调用名为 `printDocument` 的方法。

![image-U3OP134W.jpg](img/image-U3OP134W.jpeg)

图 88-1

## 88.4 创建自定义打印适配器

在 Android 应用程序内部打印自定义文档的大部分工作涉及自定义打印适配器的实现。此示例将需要一个实现了 `onLayout()` 和 `onWrite()` 回调方法的打印适配器。在 `MainActivity.java` 文件中，添加此新类的模板，使其读取内容如下：

```java
package com.ebookfrenzy.customprint;

.
.

import android.os.CancellationSignal;
import android.os.ParcelFileDescriptor;
import android.print.PageRange;
import android.print.PrintAttributes;
import android.print.PrintDocumentAdapter;
import android.content.Context;

public class MainActivity extends AppCompatActivity {

    public static class MyPrintDocumentAdapter extends PrintDocumentAdapter {

        Context context;

        MyPrintDocumentAdapter(Context context) {
            this.context = context;
        }

        @Override
```



进入`/path/to/xxx`目录，找到`xxx.json`。

在表达式`cvar = avar + bvar`中，加法运算符（`+`）将`avar`与`bvar`相加，得到它们的和`cvar`。

在`List.of(arg0, arg1, arg2)`中，`List`接口的工厂方法`of()`接受一系列的元素，返回包含它们的只读列表。

之后我们这样调用`cmd`命令：`cmd arg0 arg1 arg2`。

```
if (condVar > someVal) {console.log("xxx")}
```

---

`public void onLayout(PrintAttributes oldAttributes, PrintAttributes newAttributes, CancellationSignal cancellationSignal, LayoutResultCallback callback, Bundle metadata) { }`

`@Override`
`public void onWrite(final PageRange[] pageRanges, final ParcelFileDescriptor destination, final CancellationSignal cancellationSignal, final WriteResultCallback callback) { }`

目前这个新类包含一个在创建新类实例时调用的构造方法。构造方法接收调用活动的`context`作为参数，然后将其存储，以便稍后在两个回调方法中引用。

建立好类框架后，下一步是实现两个回调方法，从`onLayout()`开始。

### 88.5 实现`onLayout()`回调方法

继续留在`MainActivity.java`文件中，首先添加`onLayout()`方法代码将所需的某些导入指令：

```java
package com.ebookfrenzy.customprint;

.
.
import android.print.PrintDocumentInfo;
import android.print.pdf.PrintedPdfDocument;
import android.graphics.pdf.PdfDocument;

public class MainActivity extends AppCompatActivity {

.
.
}
```

接下来，修改`MyPrintDocumentAdapter`类，声明在`onLayout()`方法中使用的变量：

```java
public static class MyPrintDocumentAdapter extends PrintDocumentAdapter
{
    Context context;
    int pageHeight;
    int pageWidth;
    PdfDocument myPdfDocument;
    int totalpages = 4;

.
.
}
```

注意，对于此示例，将打印一个四页文档。在更复杂的情况下，应用程序可能需要根据内容的数量和布局相对于用户纸张尺寸和页面方向的选择，动态计算要打印的页数。

声明变量后，按照以下代码列表实现`onLayout()`方法：

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

该方法执行了许多任务，每个都需要详细说明。首先，创建一个`PdfDocument`类实例。当打印框架调用`onLayout()`方法时，传入的一个参数是`PrintAttributes`对象，包含了纸张尺寸、分辨率和颜色设置。

该方法随后使用`PrintAttributes`对象提取文档页面的高度和宽度。这些维度以英寸分之一为单位存储在对象中。由于示例中使用这些值的方法是以1/72英寸为单位，因此在存储之前进行了转换：`pageHeight = newAttributes.getMediaSize().getHeightMils()/1000 * 72;` `pageWidth = newAttributes.getMediaSize().getWidthMils()/1000 * 72;`

尽管此示例没有使用用户的颜色选择，但该属性可以通过调用`PrintAttributes`对象的`getColorMode()`方法获取，它将返回彩色或黑白值。

当`onLayout()`方法被调用时，它接收一个类型`LayoutResultCallback`类型的对象。该对象提供了一种通过一组方法向打印框架反馈状态的方法。例如，如果用户取消打印过程，`onLayout()`方法将被调用。过程已取消的事实通过`CancellationSignal`参数中的设置指示。如果检测到取消，`onLayout()`方法必须调用`LayoutResultCallback`对象的`onLayoutCancelled()`方法，以通知打印框架已收到取消请求且布局任务已取消：`if (cancellationSignal.isCanceled() ) { callback.onLayoutCancelled(); return; }`

当布局工作完成后，该方法需要调用`LayoutResultCallback`对象的`onLayoutFinished()`方法并传递两个参数。第一个参数是`PrintDocumentInfo`对象，包含了要打印文档的信息。这些信息包括PDF文档、内容类型（在此情况下是文档而非图像）以及页数。第二个参数是一个布尔值，表示自上次调用`onLayout()`方法以来布局是否发生了变化。

```java
PrintDocumentInfo.CONTENT_TYPE_DOCUMENT)
.setPageCount(totalpages);
PrintDocumentInfo info = builder.build();
callback.onLayoutFinished(info, true);
} else {
    callback.onLayoutFailed("Page count is zero.");
}
```

如果页数为0，代码将通过调用`LayoutResultCallback`对象的`onLayoutFailed()`方法向打印框架报告此失败。

调用`onLayoutFinished()`方法会通知打印框架布局工作已完成，从而触发对`onWrite()`方法的调用。

### 88.6 实现`onWrite()`回调方法

`onWrite()`回调方法负责渲染文档的页面，然后通知打印框架文档已准备好打印。完成后，`onWrite()`方法的实现如下：

```java
package com.ebookfrenzy.customprint;

import java.io.FileOutputStream;
import java.io.IOException;
import android.graphics.pdf.PdfDocument.PageInfo;

@Override
public void onWrite(final PageRange[] pageRanges,
                    final ParcelFileDescriptor destination,
                    final CancellationSignal cancellationSignal,
                    final WriteResultCallback callback) {

    for (int i = 0; i < totalpages; i++) {
        if (pageInRange(pageRanges, i)) {
            PageInfo newPage = new PageInfo.Builder(pageWidth, lineHeight, i).create();
            PdfDocument.Page page = myPdfDocument.startPage(newPage);

            if (cancellationSignal.isCanceled()) {
                callback.onWriteCancelled();
                myPdfDocument.close();
                myPdfDocument = null;
                return;
            }

            drawPage(page, i);
            myPdfDocument.finishPage(page);
        }
    }

    try {
        myPdfDocument.writeTo(new FileOutputStream(destination.getFileDescriptor()));
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

`onWrite()`方法首先循环遍历文档中的每一页。然而，重要的是考虑到用户可能请求只打印组成文档的某些页面。打印框架的用户界面面板提供了指定要打印特定页面或页面范围的选项。例如，图88-2显示了配置为打印文档的第1-4页、第9页和第11-13页的打印面板。

![image-WN7HE8CX.jpg](img/image-WN7HE8CX.jpeg)

图88-2

在将页面写入PDF文档时，`onWrite()`方法必须采取步骤确保打印用户指定的页面。为了实现，打印框架通过参数传递一个`PageRange`对象数组，指示要打印的页面范围。在上述`onWrite()`实现中，对每个页都会调用一次`pageInRange()`方法，以验证该页是否在指定的范围内。`pageInRange()`方法的代码将在本章稍后实现。

```java
for (int i = 0; i < totalpages; i++) {
    if (pageInRange(pageRanges, i)) {
        // ...
    }
}
```

对于位于任何指定范围内的每一页，都会创建一个新的`PdfDocument.Page`对象。在创建新页面时，之前由`onLayout()`方法存储的高度和宽度值将作为参数传递，以便页面大小与用户选择的打印选项匹配：

```java
PageInfo newPage = new PageInfo.Builder(pageWidth, lineHeight, i).create();
PdfDocument.Page page = myPdfDocument.startPage(newPage);
```

与`onLayout()`方法一样，`onWrite()`方法需要响应取消请求。在这种情况下，代码在关闭并取消引用`myPdfDocument`变量之前，会通知打印框架取消已执行：

```java
if (cancellationSignal.isCanceled()) {
    callback.onWriteCancelled();
    myPdfDocument.close();
    myPdfDocument = null;
    return;
}
```

只要打印过程没有取消，该方法在调用`myPdfDocument`对象的`finishPage()`方法之前，会调用一个方法在当前页面上绘制内容：

```java
drawPage(page, i);
myPdfDocument.finishPage(page);
```

`drawPage()`方法负责在页面上绘制内容，将在`onWrite()`方法完成后实现。

当所需的页面数已添加到PDF文档后，文档将使用文件描述符写入目标流，该文件描述符作为参数传递给`onWrite()`方法。如果由于任何原因写入操作失败，该方法将通过调用`WriteResultCallback`对象的`onWriteFailed()`方法（同样作为参数传递给`onWrite()`方法）通知框架。

```java
try {
    myPdfDocument.writeTo(new FileOutputStream(destination.getFileDescriptor()));
} catch (IOException e) {
    callback.onWriteFailed(e.toString());
    return;
} finally {
    myPdfDocument.close();
    myPdfDocument = null;
}
```

最后，调用`WriteResultCallback`对象的`onWriteFinished()`方法通知打印框架文档就绪。

### 88.7 检查页面是否在范围内

正如概述，当`onWrite()`方法被调用时，它接收一个`PageRange`对象数组，指示要打印的页面范围。`PageRange`类用于存储页的起始和结束位置，这些位置可以通过`getStart()`和`getEnd()`方法访问。在上一节中，`onWrite()`方法调用了一个名为`pageInRange()`的方法，其参数为`PageRange`对象数组和页码。`pageInRange()`方法的作用是识别指定的页码是否在范围内，并在`MainActivity.java`中的`MyPrintAdapter`类中实现如下：

```java
public class MyPrintAdapter {
    private boolean pageInRange(PageRange[] pageRanges, int page) {
        for (PageRange pageRange : pageRanges) {
            if ((page >= pageRange.getStart()) && (page <= pageRange.getEnd())) {
                return true;
            }
        }
        return false;
    }
}
```

### 88.8 绘制内容

现在到了需要编写代码在页面上绘制内容以准备打印的阶段。绘制的内容完全取决于应用程序，仅限于使用`Canvas`类可以实现。在本示例中，将在画布上绘制一些文本和图形。

`onWrite()`方法被设计为调用名为`drawPage()`的方法，其参数为代表当前页的`PdfDocument.Page`对象代表页码的整数。在`MainActivity.java`文件中，该方法现在应该实现如下：

代码中的页码计数从`0`开始。由于文档传统上从第1页开始，该方法首先对存储的页码进行增。然后获取与页面相关的`Canvas`对象的引用，并声明了一些边距和基线值：

```
Canvas canvas = page.getCanvas();
pagenumber++;
int titleBaseLine = 72;
int leftMargin = 54;
```



接下来，代码创建了用于绘制的`Paint`和`Color`对象，设置字体大小并绘制页面标题文本，包括当前的页码：

```
Paint paint = new Paint();
paint.setColor(Color.BLACK);
paint.setTextSize(40);
canvas.drawText("Test Print Document Page " + pagenumber,
    leftMargin,
    titleBaseLine,
    paint);
```

随后减小字体大小，并在标题下方绘制了一些正文内容：

```
paint.setTextSize(14);
canvas.drawText("This is some test content to verify that custom document printing works", leftMargin, titleBaseLine + 35, paint);
```

该方法执行的最后一个任务是绘制一个圆（偶数页为红色，奇数页为绿色）。在确定页面是奇是偶后，方法获取页面的高度和宽度，然后利用这些信息将圆置于页面中心：

```
if (pagenumber % 2 == 0)
    paint.setColor(Color.RED);
else
    paint.setColor(Color.GREEN);
PageInfo pageInfo = page.getInfo();
canvas.drawCircle(pageInfo.getPageWidth()/2,
    pageInfo.getPageHeight()/2,
    150, paint);
```

在画布上绘制完成后，该方法将控制权返回给`onWrite()`方法。

随着`drawPage()`方法完成，`MyPrintDocumentAdapter`类编写完毕。

## 88.9 启动打印任务

当用户点击“打印文档”按钮时，将调用`printDocument()` `onClick`事件处理方法。因此，测试开始前剩下的工作是将此方法添加到`MainActivity.java`文件中，并特别注意确保将其放置在`MyPrintDocumentAdapter`类之外：

```
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
        String jobName = this.getString(R.string.app_name) + " Document";
        printManager.print(jobName, new MyPrintDocumentAdapter(this),
            null);
    }
.
.
}
```

该方法在创建作为打印任务名称的新`String`对象之前，获取设备上运行的`Print Manager`服务的引用。最后，调用`Print Manager`的`print()`方法来启动打印任务，传递任务名称和我们自定义打印文档适配器类的实例。

## 88.10 测试应用程序

在 Android 设备或模拟器上编译并运行应用程序。当应用程序加载后，点击“打印文档”按钮启动打印任务，并选择一个合适的输出目标（“保存为 PDF”选项有助于避免浪费纸和打印机墨水）。

检查打印输出，应包含 4 页，包括文本和图形。例如，图 88-3 显示了作为 PDF 文件查看的四页文档，准备保存到设备上。

尝试其他打印配置选项，例如在打印面板中更改纸张大小、方向和页面设置。打印输出应反映每项设置的变化，表明自定义打印文档适配器功能正常。

![image-GR45T9EG.jpg](img/image-GR45T9EG.jpeg)

图 88-3

## 88.11 总结

虽然比 Android 打印框架的 HTML 和图像打印选项实现复杂，但自定义文档打印为在 Android 应用中打印复杂内容提供了极大的活性。实现自定义文档打印的大部分工作涉及创建一个自定义`Print Adapter`类，该类不仅在文档页面上绘制内容，还能在用户更改打印设置（如页面大小和打印页面范围）时做出正确响应。

## 89. Android App Links 简介

随着技术的演进，Web 和移动内容之间的传统区别开始模糊。这一点特别`true`的一个领域是渐进式 Web 应用（PWA）的日益普及，Web 应用的外观和行为与传统的移动应用非常相似。

另一个趋势是通过网络搜索和 URL 链接使移动应用中的内容可发现。在 Android 应用开发的背景下，`App Links`功能旨在让用户更容易地发现和访问存储在 Android 应用中的内容，即使用户没有安装该应用。

## 89.1 Android App Links 概述

App link 是一种标准的 HTTP URL，是从网站或应用等外部源直接链接到你应用中特定位置的简单方法。App links（也称为深度链接`deep links`）主要用于鼓励用户与应用交互，并允许用户分享应用内容。

App link 实现是一个多步骤过程，涉及向项目清单（`manifest`）中添加意图过滤器（`intent filters`）、在关联的应用 Activity 中实现链接处理代码以及使用数字资产链接文件（`digital asset links`）将应用与基于 Web 的内容关联。

这些步骤可以手动完成，也可以通过 Android Studio 助手自动完成。

本章剩余部分将概述 app links 的实现方法。章节（“App Links 教程”）将进行演示。

## 89.2 App Link 图过滤器

App link URL 需要映射到应用内的特定 Activity。这通过向`AndroidManifest.xml`文件添加意图过滤器来实现，旨在响应`intent.action.VIEW`启动 Activity。意图过滤器声明在要启动的 Activity 元素内部，并且包含 app link 的方案（`scheme`）、主机（`host`）和路径（`path`）。例如，下面的清单片段在检测到匹配`http://www.example.com/welcome`的 app link 时启动名为`MyActivity`的 Activity：

```
android:scheme="http"
android:host="www.example.com"
android:pathPrefix="/welcome" />
```

可以使用意图过滤器标签的`order`属性来指定处理歧义意图过滤器的顺序：

意图过滤器会启动正确的 Activity，但仍需要在目标 Activity 中添加代码以适当处理意图。

## 89.3 处理 App Link 意图

大多数情况下，启动的 Activity 需要访问 app link URL，并根据 URL 的结构采取特定行动。继续上面的示例，Activity 通过包含`/newuser`路径的 URL 启动时可能会通过路径设置为`/existinguser`的 URL 显示不同的内容。

当链接启动 Activity 时，会传递一个包含启动 Activity 操作数据的 intent 对象，其中包含包含 app link URL 的`Uri`对象。在 Activity 的初始化阶段，可以添加代码来提取这些数据：

```
Intent appLinkIntent = getIntent();
String appLinkAction = appLinkIntent.getAction();
Uri appLinkData = appLinkIntent.getData();
```

获取 app link 的`Uri`后，可以使用 URL 路径的各个部分来决定在 Activity 中执行的操作。在下面的代码示例中，使用 URL 的最后部分来识别应为新用户还是现有用户显示内容：

```
String userType = appLinkData.getLastPathSegment();
```

```
if (userType.equals("newuser")) {
    // 显示新用户内容
} else {
    // 显示现有用户内容
}
```

## 89.4 将应用与网站关联

在应用链接（app link）生效之前，必须将应用链接 URL 与该链接所属的网站进行关联。这通过创建一个名为`assetlinks.json`的数字资产链接文件并将其安装在网站的`.well-known`文件夹中。请注意，数字资产链接仅基于 HTTPS 的网站。

数字资产链接文件由一个关系声明（relation statement）组成，该声明允许目标应用使用网站的链接 URL 启动；以及一个目标声明（target statement），该声明用于宣布该项目的配套应用包名和 SHA-256 证书指纹。一个典型的资产链接文件内容可能如下：

```
[{
    "relation": ["delegate_permission/common.handle_all_urls"],
    "target" : { "namespace": "android_app",
    "package_name": "",
    "sha256_cert_fingerprints": [""] }
}]
```



`assetlinks.json` 文件可以包含多个数字资产链接，允许单个网站与多个配套应用关联。

## 89.5 总结

Android App Links 允许通过来自外部网站和其他应用的 URL 链接启动应用活动（activity）。应用链接是通过项目清单文件（manifest）中的意图过滤器（intent filters）以及启动活动中的意图处理代码实现的。通过使用数字资产链接文件，可以将应用链接中使用的域名与相应的网站关联起来。一旦建立关联，当使用应用链接时，Android 不再需要用户选择目标应用。

## 90. Android Studio App Links 教程

本章将对 Android 应用链接和 Android Studio App Link 助手（Assistant）进行实际演示。

本章将为现有的 Android 应用添加应用链接支持，允许通过应用链接 URL 启动活动。除了启动活动外，显示的内容将在 URL 的路径中指定。

## 90.1 关于示例应用

本章使用的项目名为 `AppLinking`，是一个基础应用，允许用户查找有关伦敦地标的信息。该应用使用通过标准 Android 内容提供者类访问的 `SQLite` 数据库。该应用有一个现有的数据库，其中包含了伦敦热门旅游景点的记录。除了现有的数据库条目外，该应用允许用户添加和删除地标描述。

目前，该应用允许搜索现有记录并添加和删除新记录。

该项目由两个名为 `AppLinkingActivity` 和 `LandmarkActivity` 的活动组成。`AppLinkingActivity` 是应用启动时启动的主活动。该活动允许用户输入搜索标准并向数据库添加记录。当搜索找到匹配的记录时，`LandmarkActivity` 会启动并显示相关地标的信息。

本章将增强该应用以支持应用链接，以便可以使用 URL 在应用内显示特定的地标记录。

## 90.2 数据库架构

示例应用的数据包含在名为 `landmarks.db` 的文件中，位于项目层级的 `app -> assets ->> databases` 文件夹中。数据库包含一个名为 `locations` 的表，其结构如表 90-1 所示：

| 列 | 类型 | 描述 |
| :--- | :--- | :--- |
| `_id` | String | 主索引，此列包含唯一标识数据库中地标的字符串值。 |
| `title` | String | 地标的名称（例如，伦敦桥）。 |
| `description` | String | 地标的描述。 |
| `personal` | Boolean | 表明记录是私人的还是公共的。对于用户添加的所有记录，此值被设置为 true。数据库提供的现有记录被设置为 false。 |

表 90-1

## 90.3 加载并运行项目

该项目位于以下 URL 示例源码下载包的 `AppLinking` 文件夹中：

`https://www.payloadbooks.com/product/ladybugjava`

找到文件夹后，在 Android Studio 中打开它，并在设备或模拟器上运行该应用。一旦应用启动，将出现下方图 90-1 所示的屏幕：

![image-6KGN07RA.jpg](img/image-6KGN07RA.jpeg)

图 90-1

按照目前的实现方式，地标是使用位置 ID 定位的。默认数据库配置目前包含两个由 ID “londonbridge”和“toweroflondon”引用的记录。通过在 ID 字段中输入 `londonbridge` 并点击 `Find`（查找）按钮来测试搜索功能。当找到匹配的记录时，会启动第二个活动（`LandmarkActivity`）并传递有关记录的信息以进行显示。这些信息以添加到 `Intent` 对象的额外数据形式存在。`LandmarkActivity` 使用这些信息从数据库中提取记录并使用图 90-2 所示的屏幕显示给用户：

![image-QJ5L3A6M.jpg](img/image-QJ5L3A6M.jpeg)

图 90-2

## 90.4 添加 URL 映射

现在应用已加载到 Android Studio 并通过了测试，我们可以添加应用链接支持。目标是让 `LandmarkActivity` 屏幕响应应用链接点击的启动并显示信息。这是通过将 URL 映射到 `LandmarkActivity` 实现的。对于此示例，URL 的格式如下：

`http:///landmarks/`

当完成所有步骤后，对应的 URL 将导致应用显示关于伦敦塔的信息：

`http://yourdomain.com/tower/london`

要向项目添加 URL 映射，首先通过 `Tools -> App Links` 打开 `App Links` 助手。打开后，助手将如图 90-3 所示：

![image-ZVL2932I.jpg](img/image-ZVL2932I.jpeg)

图 90-3

接下来，点击 `Create Applink` 按钮显示下方所示的面板：

![image-85BYKM3.jpg](img/image-85BYKM3.jpeg)

图 90-4

点击 `Open URL Mapping` 按钮将 URL 映射到活动。在映射屏幕中，点击 `+` 按钮（如图 90-5 中高亮所示）来添加新的 URL：

![image-Z8SK25B.jpg](img/image-Z8SK25B.jpeg)

图 90-5

在 `Add URL Mapping` 对话框的 `Host` 字段中，输入你自己的网站 URL。如果你没有网站供教程使用，仍然可以使用 `http://www.example.com` 完成本章的大部分内容，但无法测试需要数字资产链接文件的功能。

`Path` 字段（如图 90-6 中的 B 所示）是声明 URL 路径的地方。路径必须以 `/` 开头，因此在此字段中输入 `/landmarks`。

`Path` 菜单（B）提供以下三种路径匹配选项：

- `path`：URL 必须精确匹配路径部分才能启动活动。例如，如果路径设置为 `/landmarks`，则 `http://www.example.com/landmarks` 被视为匹配。然而，`http://www.example.com/landmarks/londonbridge` 将不会被视为匹配。
- `pathPrefix`：指定的路径仅被视为前缀。在 `/landmarks` 组件之后可以包含额外的路径组件（例如，`http://www.example.com/landmarks/londonbridge` 仍被视为匹配）。
- `pathPattern`：允许使用基本正则表达式和通配符的形式指定路径，例如 `landmarks/*/[l-L]ondon/*`。

由于示例中的路径是地标 ID 组件的前缀，请选择 `pathPrefix` 菜单选项。

最后，使用 `Activity` 菜单（C）选择 `LandmarkActivity` 作为响应应用链接启动的活动：

![image-Y4YAM6WD.jpg](img/image-Y4YAM6WD.jpeg)

图 90-6

在对话框中完成设置后，点击 `OK` 按钮提交更改。通过将以下 URL 输入到映射屏幕的 `Check URL Mapping` 字段中（此处已设置为上方 `Host` 字段中指定的域名），检查 `URL` 格式是否正确以及是否分配给相应的活动：

`http:///landmarks/toweroflondon`

如果配置正确，`LandmarkActivity` 将作为映射的活动列出：

![image-2QCJZCSB.jpg](img/image-2QCJZCSB.jpeg)

图 90-7

最新版本的 Android 要求为 `HTTP` 和 `HTTPS` 协议声明 `App Links`（应用链接），即使只使用了其中一种，也需要如此操作。因此，在继续下一步之前，请重复上述步骤将 `URL` 的 `HTTPS` 版本添加到列表中。

下一步也将在 `App Links Assistant` 的 `URL` 映射屏幕中进行，因此请保持该屏幕处于选中状态。

## 90.5 添加 Intent Filter

如上一章所述，需要一个意图过滤器（intent filter）来响应应用链接点击并启动目标活动。事实上，当添加 `URL` 映射时，意图过滤器已自动添加到项目清单文件中。在 `App Links Assistant` 的 `URL` 映射列表中选中 `URL` 映射，向下滚动屏幕直到意图过滤器的 `Preview`（预览）部分可见。预览应包含修改后的 `AndroidManifest.xml` 文件，其中包含了新添加的意图过滤器：

![image-24J98DCR.jpg](img/image-24J98DCR.jpeg)

图 90-8

尽管 `App Links Assistant` 为我们添加了意图过滤器，但它可能没有包含处理应用链接时所需的 `autoVerify` 设置。打开 `manifests -> AndroidManifest.xml` 文件，并按照如下所示将此设置添加到两个意图过滤器中：

```
.

.

.

.
```

## 90.6 添加 Intent 处理代码

到目前为止采取的步骤确保了在响应格式正确的应用链接 `URL` 时会启动正确的活动。下一步是在 `LandmarkActivity` 类中处理意图（intent），以便从数据库中提取正确的记录并将其显示给用户。在对 `LandmarkActivity.java` 文件中的代码进行任何更改之前，值得查看现有代码的某些区域。在代码编辑器中打开 `LandmarkActivity.java` 文件，并找到 `onCreate()` 和 `handleIntent()` 方法，它们目前的读取如下：

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

在当前形式下，代码期望在 `Intent` 数据包的额外数据中找到地标 ID。由于现在活动可以通过应用链接启动，因此必须更改代码以同时处理这两种情况。首先，删除 `onCreate()` 方法中的 `handleIntent()` 调用：

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

要添加初始的应用链接意图处理代码，返回 `App Links Assistant` 面板，并点击步骤 2 下列出的 `Select Activity` 按钮。在活动选择对话框中，点击 `Insert Code` 按钮之前，选择 `LandmarkActivity` 条目：

![image-8QX88BP7.jpg](img/image-8QX88BP7.jpeg)

图 90-9

返回 `LandmarkActivity.java` 文件，注意以下代码已插入到 `onCreate()` 方法中（注意，如果 Android Studio 无法完成请求，您可以手动添加此代码）：

```java
// ATTENTION: This was auto-generated to handle app links.

Intent appLinkIntent = getIntent();

String appLinkAction = appLinkIntent.getAction();

Uri appLinkData = appLinkIntent.getData();
```

这段代码访问 `Intent` 对象并提取 `Action` 字符串和 `Uri`。如果活动启动由于应用链接，则 action 字符串将设置为 `android.intent.action.VIEW`，这与添加到清单文件的意图过滤器中声明的 action 相匹配。反之，如果活动是由主活动 `findLandmark()` 方法中的标准意图启动代码启动的，则 action 字符串将为 `null`。通过检查分配给 action 字符串的值，可以编写代码来识别活动是如何启动的并采取适当操作：

```java
.

import android.net.Uri;

.

@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);

    .

    // ATTENTION: This was auto-generated to handle app links.

    Intent appLinkIntent = getIntent();

    String appLinkAction = appLinkIntent.getAction();

    Uri appLinkData = appLinkIntent.getData();

    String landmarkId = appLinkData.getLastPathSegment();

    if (landmarkId != null) {
        displayLandmark(landmarkId);
    }
}
```

剩下的是在方法中添加一些额外的代码，以识别启动活动的方式并采取适当操作：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);

    .

    // ATTENTION: This was auto-generated to handle app links.

    Intent appLinkIntent = getIntent();

    String appLinkAction = appLinkIntent.getAction();

    Uri appLinkData = appLinkIntent.getData();

    String landmarkId = appLinkData.getLastPathSegment();

    if (landmarkId != null) {
        displayLandmark(landmarkId);
    }
}
```

（注：此处原文代码逻辑与上文描述略有出入，翻译时保持代码块不变，根据原文的意图处理。）

## 90.5 添加意图过滤器（Intent Filter）

如上一章所述，需要一个意图过滤器（intent filter）来响应应用链接点击并启动目标活动。事实上，当添加 `URL` 映射时，意图过滤器已自动添加到项目清单文件中。在 `App Links Assistant` 的 `URL` 映射列表中选中 `URL` 映射，向下滚动屏幕直到意图过滤器的 `Preview`（预览）部分可见。预览应包含修改后的 `AndroidManifest.xml` 文件，其中包含了新添加的意图过滤器：

![image-24J98DCR.jpg](img/image-24J98DCR.jpeg)

图 90-8

尽管 `App Links Assistant` 为我们添加了意图过滤器，但它可能没有包含处理应用链接时所需的 `autoVerify` 设置。打开 `manifests -> AndroidManifest.xml` 文件，并按照如下所示将此设置添加到两个意图过滤器中：

```
.

.

.

.
```

## 90.6 添加 Intent 处理代码

到目前为止采取的步骤确保了在响应格式正确的应用链接 `URL` 时会启动正确的活动。下一步是在 `LandmarkActivity` 类中处理意图，以便从数据库中提取正确的记录并将其显示给用户。在对 `LandmarkActivity.java` 文件中的代码进行任何更改之前，值得查看现有代码的某些区域。在代码编辑器中打开 `LandmarkActivity.java` 文件，并找到 `onCreate()` 和 `handleIntent()` 方法，它们目前的读取如下：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);

    binding = ActivityLandmarkBinding.inflate(getLayoutInflater());

    View view = binding.getRoot();
```



在完成对话框中的设置后，点击`OK`按钮提交更改。通过将以下 URL 输入到映射屏幕的`Check URL Mapping`字段中（此处已设置为上方`Host`字段中指定的域名），检查`URL`格式是否正确以及是否分配给相应的活动：

`http:///landmarks/toweroflondon`

如果配置正确，`LandmarkActivity`将作为映射的活动列出：

![image-2QCJZCSB.jpg](img/image-2QCJZCSB.jpeg)

图 90-7

最新版本的 Android 要求为`HTTP`和`HTTPS`协议声明`App Links`，即使只使用了其中一种，也需要如此操作。因此，在继续下一步之前，请重复上述步骤将`URL`的`HTTPS`版本添加到列表中。

下一步也将在`App Links Assistant`的`URL`映射屏幕中进行，因此请保持该屏幕处于选中状态。

## 90.5 添加意图过滤器

如上一章所述，需要一个意图过滤器（intent filter）来响应应用链接点击并启动目标活动。事实上，当添加`URL`映射时，意图过滤器已自动添加到项目清单文件中。在`App Links Assistant`的`URL`映射列表中选中`URL`映射，向下滚动屏幕直到意图过滤器的`Preview`（预览）部分可见。预览应包含修改后的`AndroidManifest.xml`文件，其中包含了新添加的意图过滤器：

![image-24J98DCR.jpg](img/image-24J98DCR.jpeg)

图 90-8

尽管`App Links Assistant`为我们添加了意图过滤器，但它可能没有包含处理应用链接时所需的`autoVerify`设置。打开`manifests -> AndroidManifest.xml`文件，并按照如下所示将此设置添加到两个意图过滤器中：

```
.
.
.
.
```

## 90.6 添加`Intent`处理代码

到目前为止采取的步骤确保了在响应格式正确的应用链接`URL`时会启动正确的活动。下一步是在`LandmarkActivity`类中处理意图，以便从数据库中提取正确的记录并将其显示给用户。在对`LandmarkActivity.java`文件中的代码进行任何更改之前，值得查看现有代码的某些区域。在代码编辑器中打开`LandmarkActivity.java`文件，并找到`onCreate()`和`handleIntent()`方法，它们目前的读取如下：

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

在当前形式下，代码期望在`Intent`数据包的额外数据中找到地标 ID。由于现在活动可以通过应用链接启动，因此必须更改代码以同时处理这两种情况。首先，删除`onCreate()`方法中的`handleIntent()`调用：

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

要添加初始的应用链接意图处理代码，返回`App Links Assistant`面板，并点击步骤 2 下列出的`Select Activity`按钮。在活动选择对话框中，点击`Insert Code`按钮之前，选择`LandmarkActivity`条目：

![image-8QX88BP7.jpg](img/image-8QX88BP7.jpeg)

图 90-9

返回`LandmarkActivity.java`文件，注意以下代码已插入到`onCreate()`方法中（注意，如果 Android Studio 无法完成请求，您可以手动添加此代码）：

```java
// ATTENTION: This was auto-generated to handle app links.

Intent appLinkIntent = getIntent();
String appLinkAction = appLinkIntent.getAction();
Uri appLinkData = appLinkIntent.getData();
```

这段代码访问`Intent`对象并提取`Action`字符串和`Uri`。如果活动启动由于应用链接，则 action 字符串将设置为`android.intent.action.VIEW`，这与添加到清单文件的意图过滤器中声明的 action 相匹配。如果活动是由主活动`findLandmark()`方法中的标准意图启动代码启动的，则 action 字符串将为`null`。通过检查分配给 action 字符串的值，可以编写代码来识别活动是如何启动的并采取适当操作：

```java
.
import android.net.Uri;
.
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    .
    // ATTENTION: This was auto-generated to handle app links.

    Intent appLinkIntent = getIntent();
    String appLinkAction = appLinkIntent.getAction();
    Uri appLinkData = appLinkIntent.getData();

    String landmarkId = appLinkData.getLastPathSegment();

    if (landmarkId != null) {
        displayLandmark(landmarkId);
    }
}
```

剩下的是在方法中添加一些额外的代码，以识别启动活动的方式并采取适当操作：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    .
    // ATTENTION: This was auto-generated to handle app links.

    Intent appLinkIntent = getIntent();
    String appLinkAction = appLinkIntent.getAction();
    Uri appLinkData = appLinkIntent.getData();

    String landmarkId = appLinkData.getLastPathSegment();

    if (landmarkId != null) {
        displayLandmark(landmarkId);
    }
}
```



```java
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    binding = ActivityLandmarkBinding.inflate(getLayoutInflater());
    View view = binding.getRoot();
    setContentView(view);
    handleIntent(getIntent());
}
```

要添加初始的应用链接意图处理代码，返回`App Links Assistant`面板，并点击步骤 2 下列出的`Select Activity`按钮。在活动选择对话框中，点击`Insert Code`按钮之前，选择`LandmarkActivity`条目：

![image-8QX88BP7.jpg](img/image-8QX88BP7.jpeg)

图 90-9

返回`LandmarkActivity.java`文件，注意以下代码已插入到`onCreate()`方法中（注意，如果 Android Studio 无法完成请求，您可以手动添加此代码）：

```java
// ATTENTION: This was auto-generated to handle app links.

Intent appLinkIntent = getIntent();

String appLinkAction = appLinkIntent.getAction();

Uri appLinkData = appLinkIntent.getData();
```

这段代码访问`Intent`对象并提取`Action`字符串和`Uri`。如果活动启动由于应用链接，则 action 字符串将设置为`android.intent.action.VIEW`，这与添加到清单文件的意图过滤器中声明的 action 相匹配。如果，如果，如果活动是由主活动`findLandmark()`方法中的标准意图启动代码启动的，则 action 字符串将为 null。通过检查分配给 action 字符串的值，可以编写代码来识别活动是如何启动的并采取适当操作：

```java
.
import android.net.Uri;
.
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    .
    // ATTENTION: This was auto-generated to handle app links.
    Intent appLinkIntent = getIntent();
    String appLinkAction = appLinkIntent.getAction();
    Uri appLinkData = appLinkIntent.getData();
    String landmarkId = appLinkData.getLastPathSegment();
    if (landmarkId != null) {
        displayLandmark(landmarkId);
    }
}
```

剩下的是在方法中添加一些额外的代码，以识别启动活动的方式并采取适当操作：

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    .
    // ATTENTION: This was auto-generated to handle app links.
    Intent appLinkIntent = getIntent();
    String appLinkAction = appLinkIntent.getAction();
    Uri appLinkData = appLinkIntent.getData();
    String landmarkId = appLinkData.getLastPathSegment();
    if (landmarkId != null) {
        displayLandmark(landmarkId);
    }
}
```

返回 App Links 助手面板并点击“测试 App Links”按钮，测试意图处理是否正常工作。当提示输入测试 URL 时，在点击“运行测试”按钮之前，输入伦敦桥地标 ID 的 URL（使用应用链接映射中引用的域名）：

![image-Q0H2Y8X9.jpg](img/image-Q0H2Y8X9.jpeg)

图 90-12

一旦点击该按钮，Landmark 活动（Activity）将在设备或模拟器上启动，并显示关于伦敦桥桥的信息。

## 90.10 总结

本章演示了在 Android 应用项目中实现 App Link 支持的步骤，包括在 Android Studio 中使用 App Link 助手、App Link URL 映射、意图过滤器、使用 Digital Asset Links 文件条目处理网站关联以及 App Link 测试。

## 91. 使用 Material Design 3 主题进行工作

Android 应用的外观旨在符合 Material Design 定义的一系列指南。Google 开发 Material Design 是为了在不同的应用之间提供设计的一致性，同时允许应用开发者在颜色、排版和形状选择方面包含自己的品牌特色（这一概念被称为 Material 主题）。除了设计指南外，Material Design 还包含了一套用于设计用户界面布局的 UI 组件，我们在整本书中已经使用了其中的许多组件。

本章将概述主题化在 Android Studio 项目中是如何运作的，并探索如何修改为新创建的项目提供的默认设计配置，以满足您的品牌化需求。

## 91.1 Material Design 2 与 Material Design 3

在开始之前，重要的是注意 Google 正在从 Material Design 2 过渡到 Material Design 3，且 Android Studio Ladybug 项目默认使用 Material Design 3。Material Design 3 是 Material You 的基础，Material You 是 Android 12 中引入的一项功能，允许应用自动调整主题元素，以适应用户在设备上配置的偏好。例如，Material Design 3 提供的动态颜色支持允许应用中使用的颜色自动适应以匹配用户的壁纸选择。

## 91.2 理解 Material Design 主题

我们知道 Android 应用的用户界面是通过组合布局、文本字段和按钮等组件创建的。除非我们专门在 XML 布局资源文件中通过编写代码来重写某个颜色属性，否则这些组件将使用默认颜色显示。项目的主题定义了这些默认颜色。主题由一组颜色槽位（在`themes.xml`文件中声明）组成，并被分配了颜色值（在`colors.xml`文件中声明）。每个 UI 组件在内部都被设置为使用主题颜色槽位作为特定属性（例如`Text`组件的前景和背景颜色）的默认颜色。因此，我们可以通过更改分配给特定主题槽位的颜色来更改应用的全局主题。当应用运行时，当渲染用户界面时，所有组件都将使用新的默认颜色。

## 91.3 Material Design 3 主题

在探索 Material Design 3 之前，我们必须考虑它如何在 Android Studio 项目中被使用。应用项目使用的主题被声明为`AndroidManifest.xml`文件中`application`元素的属性，例如：

```xml
xmlns:tools="http://schemas.android.com/tools">
.
.
android:supportsRtl="true"
android:theme="@style/Theme.MyDemoApp"
tools:targetApi="31">
.
.
```

如之前讨论过的，所有与项目主题相关的文件都包含`res -> values`文件夹下的`colors.xml`和`themes.xml`文件中，如图 91-1 所示：

![image-ZOIIENJH.jpg](img/image-ZOIIENJH.jpeg)

图 91-1

主题本身声明位于`themes`文件夹下的两个`themes.xml`文件中。这些资源文件声明了不同的色调，包含 Material 主题颜色槽位，用于设备处于亮色或深色（夜间）模式时。注意，每个文件中的`style`名称属性必须与`AndroidManifest.xml`文件中引用的名称匹配，例如：

这些颜色槽位（也称为颜色属性）被 Material 组件用于在屏幕上渲染时设置颜色。例如，`colorPrimary`颜色槽位用作`Material Button`组件的背景颜色。

MD3 中的颜色槽位分为 Primary（主）、Secondary（次要）、Tertiary（三级）、Error（错误）、Background（背景）和 Surface（表面）。这些槽位进一步细分为由基础颜色和“在其之上（on）”基础颜色组成的对。这通常对应 Material 组件的背景颜色和前景颜色。

用于着色的特定组在不同组件之间会有不同。例如，`Material Button`组件将使用`colorPrimary`基础颜色作为背景颜色，使用`colorOnPrimary`作为其内容（即它显示的文本或图标）。另一方面，`FloatingActionButton`组件使用`colorPrimaryContainer`作为背景颜色，使用`colorOnPrimaryContainer`作为前景。通常可以通过更改主题文件中的颜色设置并查看布局编辑器中的渲染结果，来快速识别特定组件类型的正确组。

假设我们需要将`colorPrimary`改为红色。我们通过在`colors.xml`文件中为红色添加一个新条目，然后将其分配给`themes.xml`文件中的`colorPrimary`槽位来实现。因此，MD3 主题夜间模式下的`colorPrimary`槽位读取如下：

```xml
@color/my_bright_primary
```

该颜色在`colors.xml`文件中声明：

```xml
.
.
#FC0505
.
.
```



## 91.4 构建自定义主题

正如我们所见，实现主题的代码工作相对简单。然而，困难的部分通常是选择组成主题的互补颜色。幸运的是，Google 开发了一个工具，可以轻松为应用设计自定义颜色和字体主题。该工具被称为 `Theme Builder`，地址如下：

<https://m3.material.io/theme-builder>

图 91-2 显示了 `Theme Builder` 的版本。然而，Google 每几周就会重新设计 `Builder`，因此您看到的界面可能与当前设计不符。

![image-ZOIIENJH.jpg](img/image-ZOIIENJH.jpeg)

图 91-2

可以通过在上方提供您选择的源颜色（A）、选择标准壁纸（B）、上传图像（C）或进行单独的核心颜色选择（D）来生成自定义 Material 颜色主题。标记 E 的按钮预览了亮色和深色模式下的配色方案。

标记 F 的区域显示了示例应用界面、亮/深色配色方案表以及根据您的颜色选择更新的组件。由于面板大于典型的浏览器窗口，你需要向下滚动查看所有信息。

一旦定义了主题颜色，点击“选择字体”（G）按钮将显示图 91-3 所示的屏幕，您可以在那里选择应用使用的字体：

![image-C6G5YZ5B.jpg](img/image-C6G5YZ5B.jpeg)

图 91-3

要将主题整合到您的设计中，点击上面的导出主题按钮（标记为 A）并选择 `Android Views (XML)`。下载后，`themes.xml` 和 `colors.xml` 文件可以替换项目中的现有文件。注意，导出的 `themes.xml` 文件中的主题名称必须更改为与您的项目匹配。

## 91.5 总结

Material Design 提供了定义 Android 应用程序外观的指南和组件。通过设计指定显示应用时使用的颜色、字体和形状的主题，可以为应用应用个人品牌设计。Google 最近引入了 Material Design 3，它取代了 Material Design 2 并支持 Material You 的新功能，包括动态颜色。Google 还提供了 Material Theme Builder，用于设计你自己的主题，这降低了选择互补主题颜色的任务难度。一旦使用该工具被用来设计了主题，就可以导出相应的文件并在 Android Studio 项目中使用它们。

# 92. Material Design 3 主题与动态颜色教程

本章将向你展示如何使用 `Material Theme Builder` 工具创建一个新的 Material Design 3 主题，并将其集成到 Android Studio 项目中。教程还将演示如何为应用添加对动态主题颜色的支持并测试。

## 92.1 创建 ThemeDemo 项目

在欢迎界面选择 `New Project`（新建项目）选项，在弹出的新项目对话框中，点击 `Next`（下一步）按钮之前选择 `Empty Views Activity` 模板。

在 `Name`（名称）字段中输入 `ThemeDemo`，并指定 `com.ebookfrenzy.themedemo` 为包名。在点击 `Finish`（完成）按钮之前，将 `Minimum API level`（最低 API 级别）设置为 `API 26`：`Android 8.0 (Oreo)`，并将 `Language`（语言）菜单设置为 `Java`。

## 92.2 设计用户界面

主活动将由一个简单的布局组成，包含一些用户界面组件，这些组件使我们能够看到在本章之后执行的主题工作的效果。关于 MD3 组件的信息，请参考以下网页：

[`material.io/blog/migrating-material-3`](https://material.io/blog/migrating-material-3)

布局将在 `activity_main.xml` 文件中设计，该文件目前包含一个的 `Text` 视图。在布局编辑器中打开此文件，删除 `Text` 视图，关闭 `Autoconnect`（自动连接）模式（图 92-1 中标记为 A），并点击按钮清除布局中的所有约束（B）。

![image-0RK7UNDL.jpg](img/image-0RK7UNDL.jpeg)

图 92-1

从 `Palette` 的 `Buttons` 部分将 `Chip`、`CheckBox`、`Switch` 和 `Button` 视图拖到布局画布上。接下来，将一个 `FloatingActionButton` 拖到布局画布上，将其放置在 `Button` 组件下方。当提示选择显示在 `FloatingActionButton` 上的图标时，从资源工具窗口内选择 `ic_lock_power_off` 图标，如图 92-2 所示：

![image-31VUKYAR.jpg](img/image-31VUKYAR.jpeg)

图 92-2

将 `Chip` 组件的文本属性改为“This is my chip”，并将 `chipIcon` 属性设置为 `@android:drawable/ic_btn_speak_now`，以便布局看起来像图 92-3 左侧所示的：

![image-3Q7WGERA.jpg](img/image-3Q7WGERA.jpeg)

图 92-3

为了设置约束，选择所有组件，右键点击 `Chip` 视图，并在弹出的菜单中选择 `Chains -> Create Vertical Chain`（链 -> 创建垂直链）。重复此步骤，这次选择 `Center -> Horizontally in Parent`（在父布局水平居中）菜单选项。

在设备或模拟器上编译并运行应用，验证用户界面是否与上述图 92-3 所示一致。下一步是创建一个自定义主题并将其应用于项目。

## 92.3 构建新主题

项目的主题将使用 `Material Theme Builder` 设计和生成。打开浏览器窗口并导航到以下 URL 以访问构建器工具：

<https://m3.material.io/theme-builder>

一旦加载了构建器，选择一张壁纸，然后点击 `Core colors`（核心颜色）部分的 `Primary`（主色）圆形以显示颜色选择器。从颜色选择器中选择任何你认为适合主题主题的颜色，然后点击 `Apply`（应用）按钮：

![image-LIG6XMLN.jpg](img/image-LIG6XMLN.jpeg)

图 92-4

检查颜色方案并使用 `Core colors` 面板进行任何必要的颜色调整，直到你对颜色槽满意。一旦主题准备绪，点击 `Pick your fonts`（选择你的字体）按钮并进行字体选择。

点击 `Export theme`（导出主题）按钮。在弹出的面板中，点击 `Export`（导出）并选择 `Jetpack Compose (Theme.kt)` 选项。根据提示，将文件保存到计算机文件系统的合适位置。主题将被保存为名为 `material-theme.zip` 的压缩文件。

使用适用于你操作系统的工具解压主题文件，它应该包含在名为 `material-theme` 的文件夹中的以下文件夹和文件：

- `values/colors.xml` - 亮色模式的颜色定义。
- `values/themes.xml` - 亮色模式的主题。
- `values/colors.xml` - 暗色模式的颜色定义。
- `values-night/themes.xml` - 暗色模式的主题。

现在主题文件已经生成，需要将它们集成到 Android Studio 项目中。

## 92.4 将主题添加到项目

在将新主题添加到项目之前，首先需要删除旧的主题文件。如果 `Project` 工具窗口处于 `Project Files`（项目文件）模式，这更简单。要切换模式，使用 `Project` 工具窗口顶部的菜单如下所示，并选择 `Project Files` 模式：

![image-HXVEESSH.jpg](img/image-HXVEESSH.jpeg)

图 92-5

在 `Project Files` 模式下，导航到 `app -> src -> main -> res -> values` 文件夹并删除 `colors.xml` 和 `themes.xml` 文件。

打开你操作系统的文件系统，找到 `values` 文件夹中的 `colors.xml` 和 `themes.xml` 文件，并将它们复制到 `values-night` 文件夹。将项目窗口切换回 Android 模式，此时资源文件应符合图 92-6：

![image-9XOOYKNF.jpg](img/9XOOYKNF.jpeg)

图 92-6

接下来，修改亮色 `themes.xml` 文件以匹配当前项目：

`@color/md_primary`

对 `themes.xml`（night）文件重复这些步骤。

返回 `activity_main.xml` 文件，确认用户界面使用的是自定义主题渲染，使用下方的按钮切换亮暗模式：

![image-BKM4NDY.jpg](img/image-BKM4NDY.jpeg)

图 92-7

## 92.5 启用动态颜色支持

应用需要在运行 Android 12 或更高版本且具有正确壁纸设置的设备或模拟器上运行以测试动态颜色。在设备或模拟器上，启动 `Settings`（设置）应用并在列表中选择 `Wallpaper & style`（壁纸与样式）。在壁纸设置屏幕上，点击浏览壁纸（图 92-8 中标记为 A），选择一张与主题颜色差异很大的图像。一旦选择，将其设置为桌面。

返回 `Wallpaper & styles` 屏幕并确保选择了 `Wallpaper` 颜色选项（B）。每点击一个选项，壁纸示例都会更改以反映选择：

![image-K7PXA3C.jpg](img/image-K7PXA3C.jpeg)

由于

要启用动态颜色，我们需要调用 `DynamicColors` 类的 `applyToActivitiesIfAvailable()` 方法。为了为整个应用启用动态颜色支持，需要在自定义 `Application` 实例的 `onCreate()` 方法内部调用它。首先在 `app -> java -> com.ebookfrenzy.themedemo` 下向项目添加一个新的 Java 类文件，命名为 `ThemeDemoApplication.java`，并修改其内容如下：

```java
@Override
public void onCreate() {
    super.onCreate();
    DynamicColors.applyToActivitiesIfAvailable(this);
}
```

创建自定义的 `Application` 类后，我们必须配置项目以使用该类而不是默认的 `Application` 实例。要实现这一点，请编辑 `AndroidManifest.xml` 文件并添加一个引用新类的 `android:name` 元素：

- `package="com.ebookfrenzy.themedemo"`
- `android:name=".ThemeDemoApplication"`
- `android:allowBackup="true"`

构建并运行应用，并注意布局使用了与壁纸颜色匹配的主题。将 `ThemeDemo` 应用放入后台，返回到“壁纸与样式”（Wallpaper & styles）设置屏幕，并选择不同的壁纸。再次将 `ThemeDemo` 应用带回前台。此时，它将已经动态调整以匹配新的壁纸。

## 92.6 总结

在本章中，我们使用 `Material Theme Builder` 设计了一个新主题，并解释了将生成的主题文件集成到 `Android Studio` 项目中的步骤。最后，本章演示了如何实现和使用 `Material You` 动态色彩功能。

# 93. Android Studio 中的 Gradle 概述

在“Gradle 版本目录指南”章节中，我们引入了库版本目录，并解释了 `Gradle` 构建系统如何依赖它来确保项目使用正确的库和版本进行构建。除了在中间随后的章节中对版本目录和库依赖进行了一些修改外，人们通常认为 `Android Studio` 会采取必要的步骤来编译和运行已创建的应用程序项目。`Android Studio` 一直在后台使用一个名为 `Gradle` 的系统来实现这一点。

现在是时候查看如何使用 `Gradle` 来编译和打包应用项目的各种元素，并开始探索当在 `Android Studio` 中构建项目需要更高级的需求时，如何配置此系统了。

## 93.1 Gradle 概述

`Gradle` 是一个自动化构建工具包，允许通过一组构建配置文件来配置和管理项目的构建方式。这包括定义项目将如何被构建、成功构建需要满足哪些依赖项，以及构建过程的最终结果（或结果）应该是什么。

`Gradle` 的优势在于它为开发者提供的灵活性。`Gradle` 系统是一个自包含的、基于命令行的环境，可以通过插件集成到其他环境中。在 `Android Studio` 的情况下，`Gradle` 的集成是通过适当命名的 `Android Studio Plugin` 提供的。

尽管 `Android Studio Plugin` 允许在 `Android Studio` 内部启动和管理 `Gradle` 任务，但仍然可以使用 `Gradle` 命令行封装来构建基于 `Android Studio` 的项目，包括在未安装 `Android Studio` 的系统中。

构建项目的配置规则声明在基于 `Groovy` 编程语言的 `Gradle` 构建文件和脚本中。

## 93.2 Gradle 与 Android Studio

`Gradle` 为构建 Android 应用项目带来了许多强大的功能。一些关键特性如下：

### 93.2.1 合理的默认值

`Gradle` 实现了一个“约定优于配置”（convention over configuration）的概念。这意味着 `Gradle` 拥有一组预定义的合理默认配置设置，除非构建文件中的设置覆盖了它们，否则将使用这些设置。这意味着可以使用开发者所需的最小配置进行构建。只有当默认配置不能满足你的构建需求时，才需要更改构建文件。

### 93.2.2 依赖项

`Gradle` 功能的另一个关键领域是依赖项。例如，考虑 `Android Studio` 项目中的一个模块，它触发了一个 `intent` 来加载项目中的另一个模块。第一个模块实际上对第二个模块有依赖关系，因为如果无法在运行时找到并启动第二个模块，应用程序将无法构建成功。这种依赖关系可以在第一个模块的 `Gradle` 构建文件中声明，以便将第二个模块包含在应用构建中，或者在无法找到或构建第二个模块时标记错误。依赖项的其他示例是项目编译和运行时所依赖的库和 `JAR` 文件。

`Gradle` 依赖项可以分为本地或远程。本地依赖项引用执行构建的计算机系统本地文件系统上的项。远程依赖项引用存在远程服务器（通常称为仓库）上的项。

`Android Studio` 项目的远程依赖是使用另一个名为 `Maven` 的项目管理工具来处理的。如果在 `Gradle` 构建文件中使用 `Maven` 语法声明了远程依赖项，则该依赖项将从指定的仓库自动下载并包含在构建过程中。例如，下面的依赖项声明将导致从 Google 仓库将 `AppCompat` 库添加到项目项目中：

```gradle
implementation(libs.androidx.appcompat)
```

### 93.2.3 构建变体

除了依赖项外，`Gradle` 还为 `Android Studio` 项目提供构建变体支持。这允许从单个项目构建应用程序的多个变体。Android 运行在许多不同的设备上，涵盖各种处理器类型和屏幕尺寸。为了尽可能针对广泛设备类型和尺寸，通常需要构建应用程序的多个变体（例如，一个用于手机的用户界面，另一个用于平板大小的屏幕）。通过使用 `Gradle`，这在 `Android Studio` 中是可以实现的。

### 93.2.4 Manifest 条目

每个 `Android Studio` 项目都关联有一个 `AndroidManifest.xml` 文件，其中包含有关应用程序的配置细节。在 `Gradle` 构建文件中可以指定多个清单条目，这些条目会在项目构建时自动生成到清单文件中。这种功能与构建变体功能相结合，允许为每个构建变体配置不同的应用版本号、应用 ID 和 SDK 版本信息。

### 93.2.5 APK 签名

“创建、测试和上传 Android App Bundle”章节介绍了如何使用 `Android Studio` 环境创建签名发布 APK。也可以将通过 `Android Studio` 用户界面输入的签名信息包含在 `Gradle` 构建文件中，以便从命令行生成签名 APK。

### 93.2.6 ProGuard 支持

`ProGuard` 是 `Android Studio` 自带的一个工具，它可以优化、压缩和混淆 Java 字节码，使其更高效且更难反向工程（通过分析编译后的 Java 字节码来识别应用程序逻辑的方法）。`Gradle` 构建文件允许你控制构建应用时是否运行 `ProGuard`。

## 93.3 属性和设置 Gradle 构建文件

用于构建的 `Gradle` 由配置、属性和设置文件组成。例如，`gradle.properties` 文件主要包含与 Java 虚拟机（`JVM`）命令行标志相关的特殊设置，项目是否使用 `AndroidX` 库以及 Kotlin 代码风格支持。作为典型用户，你可能不需要更改此文件中的任何设置。

相反，`settings.gradle.kts` 文件定义了当构建系统需要下载和安装构建项目所需的额外库和插件时，搜索哪些在线仓库，以及项目名称。典型的 `settings.gradle.kts` 文件如下：

```kotlin
pluginManagement {
    repositories {
        google()
        mavenCentral()
        gradlePluginPortal()
    }
}
```



```kotlin
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

与`gradle.properties`文件一样，不太可能对此文件进行任何更改。

## 93.4 根级 Gradle 构建文件

一个完整的 Android Studio 项目包含了构建 Android 应用程序所需的所有内容，由模块、库、清单文件和 Gradle 构建文件组成。

每个项目包含一个根级 Gradle 构建文件。该文件被列为`build.gradle.kts`（项目: )，并可以在项目工具窗口中找到，如图 93-1 所示：

![image-F5TD31IT.jpg](img/image-F5TD31IT.jpeg)

图 93-1

默认情况下，根级 Gradle 构建文件的内容读取如下：

```kotlin
plugins {
    alias(libs.plugins.android.application) apply false
}
```

在大多数情况下，没有必要对此构建文件进行任何更改。

## 93.5 模块级 Gradle 构建文件

一个 Android Studio 应用项目由一个或多个模块组成。假设有一个名为`GradleSample`的假设应用项目，它分别包含名为`Module1`和`Module2`的模块。在这种情况下，每个模块都需要它自己的 Gradle 构建文件。从项目结构来看，这些文件位置如下：

- `Module1/build.gradle.kts`
- `Module2/build.gradle.kts`

默认情况下，`Module1/build.gradle.kts`文件将类似于下面的列表：

```kotlin
alias(libs.plugins.android.application) apply false
}

android {
    namespace = "com.example.gradlesample"
    compileSdk = 35

    defaultConfig {
        applicationId = "com.example.gradlesample"
        minSdk = 26
        targetSdk = 35
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
        sourceCompatibility = JavaVersion.VERSION_11
        targetCompatibility = JavaVersion.VERSION_11
    }
}

dependencies {
    implementation(libs.androidx.appcompat)
    implementation(libs.material)
    implementation(libs.androidx.activity)
    implementation(libs.androidx.constraintlayout)
    testImplementation(libs.junit)
    androidTestImplementation(libs.androidx.junit)
    androidTestImplementation(libs.androidx.espresso.core)
}
```

从文件内容可以看出，构建文件首先声明了使用 Gradle Android 插件：

```kotlin
alias(libs.plugins.android.application) apply false
}
```

文件的`android`部分声明了项目的命名空间，然后指明了构建`Module1`时将使用的 SDK 版本。

```kotlin
android {
    namespace = "com.example.gradlesample"
    compileSdk = 35
}
```

`defaultConfig`部分中声明的项定义了在构建期间生成到模块`AndroidManifest.xml`文件中的元素。这些设置可以在构建文件中修改，它们取自模块首次创建时在 Android Studio 中入的设置：

```kotlin
defaultConfig {
    applicationId = "com.example.gradlesample"
    minSdk = 26
    targetSdk = 35
    versionCode = 1
    versionName = "1.0"
    testInstrumentationRunner = "androidx.test.runner.AndroidJUnitRunner"
}
```

`buildTypes`部分包含了关于在构建应用发布版本时是否以及如何对 APK 文件上运行 ProGuard 的指令：

```kotlin
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

按照目前的配置，构建`Module1`时不会运行 ProGuard。要启用 ProGuard，必须将`minify`项从`false`改为`true`。`proguard-rules.pro`文件可以在项目的模块目录中找到。对此文件进行的更改将覆盖`proguard-android.txt`文件中的默认设置，后者位于 Android SDK 安装目录下的`sdk/tools/proguard`目录。

由于此文件中没有声明调试`buildType`，将使用默认值（不带 ProGuard 构建、使用调试密钥签名、并启用调试符号）。

模块构建文件中还可以包含一个名为`productFlavors`的额外部分，以便创建多个构建变体。

接下来，包含了一些指令，用于指定构建项目时使用的 Java 编译器版本：

```kotlin
compileOptions {
    sourceCompatibility JavaVersion.VERSION_11
    targetCompatibility JavaVersion.VERSION_11
}
```

最后，`dependencies`部分列出了模块依赖的任何本地和远程依赖。上述示例文件中的依赖行指定了需要从 Android 仓库包含的 Android 库：

```kotlin
dependencies {
    implementation(libs.androidx.appcompat)
    implementation(libs.material)
    implementation(libs.androidx.activity)
    implementation(libs.androidx.constraintlayout)
    testImplementation(libs.junit)
    androidTestImplementation(libs.androidx.junit)
    androidTestImplementation(libs.androidx.espresso.core)
}
```

## 93.6 在构建文件中配置签名设置

“创建、测试和上传 Android App 包”章节涵盖了使用 Android Studio 界面设置密钥的步骤。这些设置可以在`build.gradle.kts`的`signingConfigs`部分进行配置。例如：

```kotlin
signingConfigs {
    release {
        storeFile = file("release.keystore")
        storePassword = "yourpassword"
        keyAlias = "youralias"
        keyPassword = "yourkeypassword"
    }
}
```

上述示例将密码信息直接嵌入到构建文件中。另一种方法是使用系统环境变量提取这些值：

```kotlin
signingConfigs {
    release {
        storeFile = file("release.keystore")
        storePassword = getenv("KEYSTOREPASSWD")
        keyAlias = "youralias"
        keyPassword = getenv("KEYPASSWD")
    }
}
```

还有一种方法是配置构建文件，以便在构建过程中提示密码：

```kotlin
signingConfigs {
    release {
        storeFile = file("release.keystore")
        storePassword = console().readLine("\nEnter Keystore password: ")
        keyAlias = "youralias"
        keyPassword = console().readLine("\nEnter Key password: ")
    }
}
```

并在`buildTypes`中应用该配置：

```kotlin
buildTypes {
    release {
        signingConfig signingConfigs.release
    }
}
```

## 93.7 从命令行运行 Gradle 任务

每个项目都包含一个 Gradle 封装工具，用于从命令行调用 Gradle 任务。该工具位于项目文件夹根目录下。虽然该工具在 Windows 系统上是可以执行的，但在 Linux 和 macOS 上可能需要启用执行权限才能使用。要启用执行权限，打开终端窗口，进入所需封装的项目目录，并执行以下命令：

```bash
chmod +x gradlew
```

一旦文件具有执行权限，将需要将其路径添加到`$PATH`环境变量中，或者在运行时名称前加上`./`。例如：

```bash
./gradlew tasks
```



在大多数情况下，Android Studio 会在后台执行应用构建，无需开发者干预。此构建过程由`Gradle`系统处理，`Gradle`是一个自动化构建工具包，旨在通过一组构建配置文件来配置和管理项目的构建方式。虽然`Gradle`的默认行为对于满足许多基础项目的构建需求，但对于更复杂的项目，配置构建过程是不可避免的。本章概述了 Android Studio 项目背景下的`Gradle`构建系统和配置文件。

## 索引

### 符号

- `428`
- `255`
- 元素`255`
- `643`
- `555`
- `462`
- `428, 472, 479`
- `.well-known`文件夹`435, 458, 762`

### A

- `AbsoluteLayout` `130`
- `ACCESS_COARSE_LOCATION`权限`496`
- `ACCESS_FINE_LOCATION`权限`496`
- `acknowledgePurchase()`方法`627`
- `ACTION_CREATE_DOCUMENT` `678`
- `ACTION_CREATE_INTENT` `678`
- `ACTION_DOWN` `230`
- `ACTION_MOVE` `230`
- `ACTION_OPEN_DOCUMENT`意`670`
- `ACTION_POINTER_DOWN` `230`
- `ACTION_POINTER_UP` `230`
- `ACTION_UP` `230`
- `ACTION_VIEW` `453`
- 激活 / 运行状态`104`
- `Activity` `91, 107`
- 在代码中添加视图`207`
- `class` `107`
- 创建`14`
- 整个生命周期`111`
- 前台生命周期`111`
- 生命周期方法`110`
- `lifecycles` `101`
- 从`432`返回数据
- 状态更改示例`115`
- 状态更改`107`
- 状态`104`
- 可见生命周期`111`
- `Activity Lifecycle` `103`
- `Activity Manager` `90`
- `ActivityResultLauncher` `433`
- `Activity Stack` `103`
- 实际屏幕像素`198`
- `adb`命令行工具`59`
- 连接测试`65`
- 设备配对`63`
- 在 Android 设备上启用`59`
- Linux 配置`62`
- 列出设备`59`
- macOS 配置`60`
- 概述`59`
- 重启服务器`60`
- 测试连接`65`
- WiFi 调试`63`
- Windows 配置`61`
- 无线调试`63`
- 无线配对`63`
- `addCategory()`方法`461`
- `addMarker()`方法`726`
- `addView()`方法`201`
- `ADD_VOICEMAIL`权限`496`
- `android`
- 可检查行为`645`
- 导出`429`
- 手势颜色`248`
- `layout_behavior`属性`421`
- `onClick` `257`
- `orderInCategory` `644`
- 进程`429, 479`
- 不确定手势颜色`248`
- Android
- `Activity` `91`
- 架构`87`
- 事件`223`
- 意图`92`
- `onClick`资源`223`
- 运行时`88`
- SDK 包`5`
- `android.app` `88`
- Android 架构组件`273`
- `android.content` `88`
- `android.content.Intent` `431`
- `android.database` `88`
- Android 调试桥接。参见`ADB`
- Android 开发
- 系统要求`3`
- Android 设备
- 不同的设计`129`
- `android.graphics` `89`
- `android.hardware` `89`
- `android.intent.action` `467`
- `android.intent.action.BOOT_COMPLETED` `429`
- `android.intent.action.MAIN` `453`
- `android.intent.category.LAUNCHER` `453`
- Android 库`88`
- `android.media` `89`
- Android 监控工具窗口`32`
- Android 原开发包`89`
- `android.net` `89`
- `android.opengl` `89`
- `android.os` `89`
- `android.permission.RECORD_AUDIO` `705`
- `android.print` `89`
- Android 项目
  - 新建`13`
- `android.provider` `89`
- Android SDK
  - 识别`9`
- Android SDK Manager`7, 9`
- Android SDK 包
  - 版本要求`7`
- Android SDK 工具
  - 命令行访问`8`
  - Linux`10`
  - macOS`10`
  - Windows 7`9`
  - Windows 8`9`
- Android 软件栈`87`
- Android 存储访问框架`670`
- Android Studio
  - 更改主题`57`
  - 编辑窗口`52`
  - 安装`4`
  - Linux 安装`5`
  - macOS 安装`4`
  - 导航栏`51`
  - 项目工具窗口`52`
  - 状态栏`52`
  - 工具栏`51`
  - 工具窗口栏`52`
  - 工具窗口`52`
  - 更新`11`
  - 欢迎界面`49`
  - Windows 安装`4`
- `android.text` `89`
- `android.util` `89`
- `android.view` `89`
- `android.view.View` `132`
- `android.view.ViewGroup` `129, 132`
- Android 虚拟设备。参见`AVD`
- 概述`27`
- Android 虚拟设备管理器`27`
- `android.webkit` `89`
- `android.widget` `89`
- AndroidX 库`790`
- API 密钥`717`
- APK 分析器`620`
- APK 文件`613`
- APK
  - 分析`620`
- APK 签名`790`
- APK 向导`612`
- app
  - `showAsAction` `644`
- App 架构
  - 现代`273`
- AppBar
  - 剖析`419`
- `appbar_scrolling_view` `421`
- App 包`609`
  - 创建`613`
  - 概述`609`
  - 修订`619`
- `AppCompatActivity`类`108`
- App 器`53`
- Application
  - 停止`32`
- Application 框架`90`
- Application Manifest`93`
- App 链接
  - 数字资产链接`762, 435`
  - 意图过滤器`770`
  - 意图过滤器`761`
  - 测试`774`
  - URL 映射`667`
- App 链接`761`
  - 自动验证`434`
- `autoVerify` `435`
- 概述`761`
- 应用更改`215`
- 应用更改并重启 Activity`215`
- 备用设置`217`
- 选项`215`
- 运行 App
  - `applyToActivities()` `786`
- 架构组件`273`
- `ART` `88`
- `assetlinks.json` `762, 435`
- 属性帧`346`
- 音频
  - 支持的格式`703`
  - 音播放`703`
  - 录制`703`
- 自动阻塞器`60`
- 自动连接模式`163`
- `AVD`
  - 更改布局`48`
  - 冷启动`44`
  - 命令行创建`27`
  - 创建`27`
  - 设备帧`35`
  - 显示模式`47`
  - 快速启动`44`
  - 可调整`47`
  - 启动应用`30`
  - 快照`43`

### B

- 后台进程`102`
- `BillingClient` `628`
- `acknowledgePurchase()`方法`627`
- `consumeAsync()`方法`627`
- `getPurchaseState()`方法`627`
- `launchBillingFlow()`方法`626`
- `queryProductDetailsAsync()`方法`626`
- `queryPurchasesAsync()`方法`628`
- `BillingResult` `642`
- `getDebugMessage()`方法`642`
- 绑定`295`
  - 单向`295`
  - 双向`296`
- `BIND_JOB_SERVICE`权限`429`
- `bindService()`方法`227, 469`
- 生物识别`661`
  - 回调`665`
  - 概述`661`
- 生物提示`666`
- `BitmapFactory` `671`
- 黑色活动`14`
- 空白模板`133`
- 蓝图视图`161`
- `BODY_SENSORS`权限`496`
- 绑定服务`427, 469`
  - 添加到项目`470`
  - 实现 Binder`470`
  - 交互选项`469`
- `BoundService`类`471`
- 广播意图`461`
  - 示例`664`
  - 概述`92, 461`
  - 发送`664`
  - 粘性`463`
- 广播接收器`461`
  - 添加到 manifest 文件`466`
  - 创建`465`
  - 概述`92, 462`
- `BroadcastReceiver`类`462`
- `BroadcastReceiver`超类`465`
- `BufferedReader`对象`681`
- 构建变体`54`
- 工具窗口`54`
- `Bundle`类`124`
- 组合通知`515`

### C

- 日历权限`496`
- `CALL_PHONE`权限`496`
- `CAMERA`权限`496`
- 权限`496`
- `CameraUpdateFactory`类方法`727`
- `CancellationSignal` `666`
- `Canvas`类`756`
- `CardView`
  - 布局文件`399`
  - 响应选择`407`
  - `CardView`类`399`
- `CATEGORY_OPENABLE` `670`
- C/C++ 库`89`
- 链偏移`184`
- 链头`154`
- 链`154`
  - 创建`181`
- 链样式
  - 更改`183`
- 链样式`154`
- `CheckBox` `129`
- `checkSelfPermission()`方法`500`
- `Circle`类`713`
- 代码补全`70`
- 代码编辑器
  - 基础`67`
  - 代码补全`70`
  - 代码生成`73`
  - 代码格式化`75`
  - 文档页`68`
  - 编辑区域`68`
  - 标格区域`68`
  - 模板`76`
  - 拆分`70`
  - 语句补全`72`
  - 状态栏`69`
- 代码生成`73`
- 代码格式化`75`
- 代码示例
  - 下载`1`
- 冷启动`44`
- `CollapsingToolbarLayout`
  - 示例`422`
  - 介绍`422`
  - 视差模式`422`
  - 固定模式`422`
  - 设置遮罩颜色`425`
  - 设置标题`425`
  - 带有图片`422`
- `Color`类`757`
- `COLOR_MODE_COLOR` `732, 752`
- `COLOR_MODE_MONOCHROME` `732, 752`
- 常见手势`237`
  - 检测`237`
- 组件树`17`
- 约束偏移`153`
- 调整`167`
- `ConstraintLayout`
  - 优势`159`
  - 可用性`160`
  - 障碍`156`
  - 基线对齐`155`
  - 链偏移`184`
  - 链头`154`
  - 链`154`
  - 链样式`154`
  - 约束偏移`153`
  - 约束`151`
  - 转换`179`
  - 转换为`MotionLayout` `353`
  - 删除约束`166`
  - 引导`173`
  - 引导`156`
  - 手动约束操作`163`
  - 边距`152, 167`
  - 相对约束`152, 169`
  - 概述`151`
  - 紧凑链`155, 184`
  - 比例`159, 185`
  - 散布链`154`
  - 散布在`184`
  - 散布在链内`154`
  - 教程`189`
  - 在 Android Studio 中使用`161`

## 小部件（Widgets）

- 加权链`154, 184`
- 小部件尺寸`155, 171`
- 小部件组对齐`177`

## ConstraintLayout 链

- 创建`181`
- 在布局编辑器中`181`

## ConstraintLayout 链样式

- 更改`183`

## 约束（Constraints）

- 删除`166`

## ConstraintSet

- `addToHorizontalChain()`方法`204`
- `addToVerticalChain()`方法`204`
- 对齐约束`203`
- 应用于布局`202`
- `applyTo()`方法`202`
- `centerHorizontally()`方法`203`
- `centerVertically()`方法`203`
- 链`203`
- `clear()`方法`204`
- `clone()`方法`203`
- `connect()`方法`202`
- 连接到父视图`202`
- 约束偏置`203`
- 复制约束`203`
- 创建`202`
- 创建连接`202`
- `createHorizontalChain()`方法`203`
- `createVerticalChain()`方法`203`
- 指导线`204`
- `removeFromHorizontalChain()`方法`204`
- `removeFromVerticalChain()`方法`204`
- 约束`204`
- 旋转`205`
- 缩放`204`
- `setGuidelineBegin()`方法`204`
- `setGuidelineEnd()`方法`204`
- `setGuidelinePercent()`方法`204`
- `setHorizonalBias()`方法`203`
- `setRotationX()`方法`205`
- `setRotationY()`方法`205`
- `setScaleX()`方法`204`
- `setScaleY()`方法`204`
- `setTransformPivot()`方法`205`
- `setTransformPivotX()`方法`205`
- `setTransformPivotY()`方法`205`
- `setVerticalBias()`方法`203`
- 尺寸约束`203`
- 教程`207`
- 视图 ID`209`
- `ConstraintSet`类`201, 202`
- 约束集`202`
- `ConstraintSets`
  - 配置`342`
- `consumeAsync()`方法`627`
- `ConsumeParams` `639`
- `ConsumeResponseListener` `627`
- 联系人权限`496`
- 容器视图`129`

## 内容提供者（Content Provider）90, 553, 571

- `555`
- 访问`571`
- `Authority` `559`
- 客户端教程`571`
- `ContentProvider`类`553`
- 内容解析（Content Resolver）`554`
- `ContentResolver` `567`
- 内容 URI`554`
- 内容 URI`559, 571`
- `ContentValues` `561`
- `delete()` `554, 565`
- `getType()` `554`
- `insert()` `553, 561`
- `onCreate()` `553, 561`
- 概述`93`
- `query()` `553, 562`
- 教程`557`
- `update()` `554, 563`
- `UriMatcher` `560`
- `UriMatcher`类`554`
- `ContentProvider`类`553`
- 内容解析`554`
- `getContentResolver()` `554`
- `ContentResolver` `567`
- `getContentResolver()` `554`
- 内容 URI`554`
- 内容 URI`554, 559`
- `ContentValues` `561`
- `Context`类`93`
- `CoordinatorLayout` `130, 421`
- `createPrintDocumentAdapter()`方法`747`
- 自定义属性`343`
- 自定义文档打印`735, 747`

## 自定义手势（Custom Gesture）

- 识别`243`

## 自定义打印适配器（Custom Print Adapter）

- 实现`749`
- 自定义打印适配器`747`

## 自定义主题（Custom Theme）

- 构建`777`

## 循环编辑器（Cycle Editor）371

- 循环关键帧`351`

## 循环关键帧（Cycle Keyframes）

- 概述`367`

### D

- 危险权限
  - 列表`496`
- 数据访问对象（DAO）`576`
- 数据访问对象（DAO）`580`
- 数据库检查器`583, 606`
  - 实时更新`607`
  - SQL 查询`607`
- 数据库行`540`
- 数据库架构`539`
- 数据库表`539`

## 数据绑定（Data binding）

- 绑定表达式`295`
- 数据绑定`275`
- 绑定类`294`
- 启用`300`
- 事件和监听器绑定`296`
- 关键组件`291`
- 概述`291`
- 教程`299`
- 结合`LiveData` `275`

- DDMS`32`

## 调试（Debugging）

- 在设备上启用`59`
- `debug.keystore`文件`435, 457`
- `DefaultLifecycleObserver` `312, 315`
- `deltaRelative` `348`
- 密度无关像素`197`

## 密度无关像素（Density Independent Pixels）

- 转换为像素`213`

## 设备定义（Device Definition）

- 自定义`147`
- 设备文件管理器（Device Explorer）`54`
- 设备帧`35`
- 设备镜像`65`
- 启用`65`
- 设备配对`63`
- 数字资源文件`762, 435`
- 直接回复`526`
- 文档提供程序`669`
- `dp` `197`

## 动态颜色（Dynamic Colors）

- `applyToIfAvailable()`方法`786`
- 在 Android 中启用`785`

## 动态状态（Dynamic State）109

- 保存`123`

### E

- 空闲进程（Empty Process）`103`
- 空模板`133`

## 模拟器（Emulator）

- 电池`42`
- 蜂窝网络配置`42`
- 指纹`44`
- 方向面板`42`
- 扩展控制选项`41`
- 扩展控制`41`
- 指纹`42`
- 位置配置`42`
- 可调整`47`
- 调整`41`
- 旋转`40`
- 屏幕录制`43`
- 快照`43`
- 开始`29`
- 截图`40`
- 工具栏`39`
- 工具栏选项`39`
- 虚拟传感器`43`
- 缩放`40`
- `enablePendingPurchases()`方法`627`
- 支持 ADB`59`

## 事件处理（Event Handling）223

- 事件监听器`224`
- 事件监听器`224`
- 消费`227`
- `execSQL()` `548`
- 显式`92`
- 显式意图`431`
- 显式意图`431`
- 扩展控制`41`

### F

- `FLAG_INCLUDE_STOPPED_PACKAGES` `461`
- 灵活区域`419`

## 文件（Files）

- 切换`68`
- `findPointerIndex()`方法`230`
- `findViewById()` `95`

## 指纹（Fingerprint）

- 模拟`44`
- 设备配置`662`
- 权限`662`
- 实施`661`

## 指纹认证（Fingerprint Authentication）

- 概述`661`
- 教程`661`

## 文件

- 浮动按钮`14, 134`
- 边距`380`
- 尺寸`380`

## 折叠屏设备（Foldable Devices）112

- 多任务恢复`112`

## 折叠屏模拟器（Foldable Emulator）532

- 折叠屏`531`

## 前台进程（Foreground Process）102

- 地理编码`719`

## Fragment（Fragment）

- 创建`253`
- 事件处理`257`
- XML 文件`254`
- `FragmentActivity`类`109`
- Fragments`253`
- 在代码中添加`256`
- 重复`388`
- 示例`261`
- 概述`253`
- `FragmentState`类`391`
- `FrameLayout` `130`

### G

- Gemini`79`
  - 提问`82`
  - 配置`81`
  - 启用`79`
  - 在 Android Studio 中`79`
  - 内联完成`83`
  - 练习场`82`
  - 建议更改`85`
  - 问题上下文`83`
  - 窗口`80`
  - 代码转换`84`
- `Geocoder` `720`
- 地理编码`718`

## 手势构建器应用（Gesture Builder Application）243

- 构建与运行`243`
- `GestureDetector`类`237`
- 实例创建`240`
- `GestureDetectorCompat` `237`
- `GestureDetector.OnDoubleTapListener` `237, 238`
- `GestureDetector.OnGestureListener` `238`
- `GestureLibrary` `243`
- `GestureOverlayView` `243`
- 配置颜色`248`
- 配置多笔划`248`
- `GestureOverlayView`类`243`
- `GesturePerformedListener` `243`

## 手势（Gestures）

- 拦截`249`（等待，`249`）-> 拦截`249`

## 手势文件（Gestures File）

- 创建`244`
- 从 SD 卡提取`244`
- 加载到应用`246`
- `GET_ACCOUNTS`权限`496`
- `getAction()`方法`467`
- `getContentResolver()` `554`
- `getDebugMessage()` `642`
- `getFromLocation()`方法`720`
- `getId()`方法`202`
- `getIntent()`方法`432`
- `getItemId()`方法`645`
- `getPointerCount()`方法`230`
- `getPointerId()`方法`230`
- `getPurchaseState()`方法`627`
- `getService()`方法`473`
- `getWritableDatabase()` `549`

## GNU/Linux 88

## Google Cloud

- 账单账户`714`
- 新项目`715`
- Google Cloud Print`730`
- Google Drive`670`
- 打印到`730`
- `GoogleMap` `713`
- 地图类型`723`
- `GoogleMap.MAP_TYPE_HYBRID` `723`
- `GoogleMap.MAP_TYPE_NONE` `723`
- `GoogleMap.MAP_TYPE_NORMAL` `723`
- `GoogleMap.MAP_TYPE_SATELLITE` `723`
- `GoogleMap.MAP_TYPE_TERRAIN` `723`

## Google Maps Android API 713

- 控制地图相机
- 显示标记`724`
- 地图标记`726`
- 概述`713`

## Google Maps SDK 713

- API`717`
- 凭据`717`
- 启用`716`
- Android SDK`717`

## Google Play 应用签名 612

- Google Play 控制台`633`
- 创建内购商品`633`
- 测试人员`633`
- Google Play 开发者控制台`610`

## Gradle

- APK 签名`794`
- 构建变`790`
- 命令行任务`795`
- 依赖`789`
- Manifest 条目`790`
- 概述`789`
- 默认值`789`

## Gradle 构建文件

- 顶层`791`
- 模块级`792`
- `gradle.properties`文件`790`

- `GridLayout` `130`
- `GridLayoutManager` `397`

- `PurchaseUpdatedListener` `638`
- 购买更新`638`
- `queryProductDetailsAsync()` `636`
- `queryProductDetailsAsync()`方法`626`
- `queryPurchasesAsync()` `639`
- `queryPurchasesAsync()`方法`628`
- `runOnUiThread()` `637`
- `subscriptions` `623`
- `tutorial` `631`
- 内存数据库`583`
- `Intent` `92`
- `explicit` `92`
- `implicit` `92`

### Intent 可用性

- 检查`438`
- `Intent.CATEGORY_OPENABLE` `678`
- `Intent Filters` `434`
- `App Link` `761`
- `Intents` `431`
- `ActivityResultLauncher` `433`
- 概述`431`
- `registerForActivityResult()` `446`
- `Intent Service` `427`
- `Intent URL` `451`

### J

- Java Native Interface`89`
- Jetpack`273`
- 概述`273`
- `JobIntentService` `427`
- `BIND_JOB_SERVICE`权限`429`
- `onHandleWork()`方法`427`

### K

- `KeyAttribute` `346`
- 键盘快捷键`56`
- `KeyCycle` `367`
- `Cycle Editor` `371`
- `tutorial` `367`
- `Keyframe` `360`
- `Keyframes` `346`
- `KeyFrameSet` `376`
- `KeyPosition` `347`
- `deltaRelative` `348`
- `parentRelative` `347`
- `pathRelative` `348`
- Keystore 文件
  - 创建`612`
- `KeyTimeCycle` `367`
- `keytool` `435`
- `KeyTrigger` `350`
- 杀死状态`104`

### L

- 大语言模型`79`
- `launchBillingFlow()`方法`626`
- `layout_collapseMode`
  - `parallax` `424`
  - `pin` `424`
- `layout_constraintDimentionRatio` `186`
- `layout_constraintHorizontal_bias` `184`
- `layout_constraintVertical_bias` `184`

## 布局编辑器

- `ConstraintLayout chains` `181`
- 布局编辑器`16, 189`
- 自动连接模式`163`
- 代码模式`140`
- 组件树`138`
- 设计模式`137`
- 设备屏幕`138`
- 示例项目`189`
- 推理模式`163`
- 调色板`138`
- 属性面板`138`
- 样本`146`
- 设置属性`141`
- 工具栏`138`
- 用户界面设计`189`
- 视图转换`145`

## 布局编辑器工具

- 更改方向`17`
- 概述`137`

- 布局检查器`55`
- 布局管理器`129`
- `LayoutResultCallback`对象`752`
- 布局`129`
- `layout_scrollFlags`
  - `enterAlwaysCollapsed mode` `421`
  - `enterAlways mode` `421`
  - `exitUntilCollapsed mode` `421`
- 滚动模式`421`
- 布局验证`148`
- `libc` `89`
- `libs.versions.toml`文件`220`
- 许可证测试人员`633`

### Lifecycle

- 生命周期
  - 感知`311`
  - 组件`276`
  - 所有者`311`
  - 状态和事件`313`
  - 教程`315`
- 生命周期感知组件`311`
- 生命周期方法`110`
- `Lifecycle Observer` `315`
  - 创建一个`315`
- 生命周期所有者
  - 创建一个`317`
- 生命周期
  - 现代`276`
- `LinearLayout` `130`
- `LinearLayoutManager` `397`
- `LinearLayoutManager layout` `406`
- Linux 内核`88`
- 列出设备`59`
- `LiveData` `274, 285`
  - 添加到`ViewModel` `285`
  - 观察者`287`
- Live Templates`76`
- LLM`79`
- 本地绑定服务`469`
  - 示例`469`
- 位置管理器`90`
- 位置权限`496`
- `Logcat`
  - 启用`119`

### M

- `MANAGE_EXTERNAL_STORAGE` `497`
- `adb`启用`497`
- 测试`497`
- Manifest 文件
  - 权限`453`
- 地图`713`
- `MapView` `713`
  - 添加到`layout` `720`
- `Marker`类`713`
- 主/详情流
  - 创建`654`
  - 双窗格模式`653`
- `match_parent`属性`197`
- Material design`379`
- Material Design 2`775`
- Material Design 2 主题`775`
- Material Design 3`775`
- Material You`775`
- MediaController
  - 添加到`View`实例`687`
  - `MediaController`类`684`
  - 方法`684`
- `MediaPlayer`类`703`
  - 方法`703`
- `MediaRecorder`类`703`
  - 录音`704`
- 内存指示`69`
- 菜单编辑器`646`
- 菜单项目选择`644`
- 菜单`443`
- 菜单编辑器`446`
- Messenger 对象`479`
- 麦克风
  - 检查可用性`706`
  - 麦克风权限`496`
- `mm` `197`
- `MotionEvent` `229, 230, 251`
- `getActionMasked()` `230`
- `MotionLayout` `341`
- 轨迹`346`

## MotionLayout

- `Attribute Keyframes` `446`
- `ConstraintSets` `342`
- `Custom Attribute` `362`
- `Editor` `353`
- `KeyAttribute` `346`
- `KeyCycle` `367`
- `Keyframes` `446`
- `KeyFrameSet` `376`
- `KeyPosition` `347`
- `KeyTimeCycle` `367`
- `KeyTrigger` `350`
- `OnClick` `345, 358`
- `OnSwipe` `345`
- 概述`341`
- `Position Keyframes` `347`
- 预览动画`358`
- `Trigger Keyframe` `350`
- 教程`353`

## MotionScene

- `ConstraintSets` `342`
- `Custom Attributes` `343`
- 文件`342`
- 过渡`342`
- `moveCamera()`方法`727`
- 多设备`311`
- 多触摸
  - 处理`230`
- 多恢复`112`
- 多触摸
  - 示例`230`
- 多窗口
  - 属性`535`
- 多窗口模式`536`
- 进入`533`
- 多窗口通知`336`
- 多窗口支持`112`
- 多窗口支持`534`
- 我的位置`713`

### N

- 导航`321`
  - 添加目的地`330`
  - 概述`321`
  - 带有`eargs` `337`
  - 传递参数`326`
  - 栈`321`
  - 教程`327`
- 导航动作`325`
- 导航架构组件`321`
- 导航组件`327`
- 导航控制器`325`
- 导航图`324, 328`
  - 添加动作`333`
  - 创建一个`328`
- 导航主机`322`
  - 声明`329`
- `newBuilder()`方法`624`
- 普通权限`495`

## 通知

- 添加动作`514`
- 直接回复`526`
- 基础`510`
- 启动活动`512`
- `PendingIntent` `522`
- 回复动作`524`
- 更新直接回复`527`
- 组合`515`
- 概述`503`
- 通知管理器`90`

### O

- 观察者
  - 实现一个`LiveData` `287`
- `onAttach()`方法`258`
- `onBillingServiceDisconnected()`回调`636`
- `onBillingServiceDisconnected()`方法`625`
- `onBillingSetupFinished()`监听器`636`
- `onBind()`方法`428, 469, 477`
- `onBindViewHolder()`方法`405`
- `OnClick` `345`
- `onClickListener` `224, 225, 228`
- `onClick()`方法`223`
- `onCreateContextMenuListener` `224`
- `onCreate()`方法`102, 110, 428`
- `onCreateOptionsMenu()`方法`644`
- `onCreateView()`方法`111`
- `onDestroy()`方法`110, 428`
- `onDoubleTap()`方法`237`
- `onDown()`方法`237`
- `onFling()`方法`237`
- `onFocusChangeListener` `224`
- `OnFragmentInteractionListener`
  - 实现`335`
- `onGesturePerformed()`方法`243`
- `onHandleWork()`方法`428`
- `onKeyListener` `224`
- `onLayoutFailed()`方法`752`
- `onLayoutFinished()`方法`753`
- `onLongClickListener` `224`
- `onLongClick()`方法`227`
- `onLongPress()`方法`237`
- `onMapReady()`方法`722`
- `onOptionsItemSelected()`方法`644`
- `onOptionsSelected()`方法`649`
- `onPageFinished()`回调`738`
- `onPause()`方法`110`
- `onProductDetails()`响应`636`
- `onReceive()`方法`102`
- `onRestart()`方法`110`
- `onSaveInstanceState()`方法`111`
- `onScaleBegin()`方法`249`
- `onScaleEnd()`方法`249`
- `onScale()`方法`249`
- `onScroll()`方法`237`
- `OnSeekBarChangeListener` `268`
- `onServiceConnected()` `469, 473, 480`
- `onServiceDisconnected()` `469, 473, 480`
- `onShowPress()`方法`237`
- `onSingleTapUp()`方法`237`
- `onStartCommand()`方法`428`
- `onStart()`方法`110`
- `onStop()`方法`110`
- `onTouchEvent()`方法`237`
- `onTouchListener` `224`
- `onTouch()`方法`229`
- `onUpgrade()` `548`
- `onViewCreated()`方法`111`
- `onViewStatusRestored()`方法`111`
- `openFileDescriptor()`方法`670`
- OpenJDK`3`
- 溢出菜单`643`
  - 创建`643`
  - 显示`644`
  - 概述`643`
  - XML 文件`643`
- 溢出菜单
  - 可检查项组`645`

### P

- 包资源管理器`15`
- 包管理器`90`
- `PackageManager`类`706`
- `PackageManager.FEATURE_MICROPHONE` `706`
- `PackageManager.PERMISSION_DENIED` `497`
- `PackageManager.PERMISSION_GRANTED` `497`
- 包名`14`
- 打包链`155, 184`
- 页范围`754, 755`
- `Paint`类`757`
- 父相对`347`
- 父视图`131`
- 路径相对`348`
- 暂停状态`104`
- `PdfDocument` `735`
- `PdfDocument.Page` `747, 754`
- `PendingIntent`类`522`
- 权限
  - 检查`497`
  - 普通`495`
  - 持久状态`109`
  - 手机权限`496`
- 选择器`669`
- 捏合手势
  - 检测`249`
  - 示例`249`
- 捏合手势识别`243`
- 位置关键帧`347`
- `POST_NOTIFICATIONS`权限`496, 520`
- `PurchasesUpdatedListener` `627`
- `PurchaseUpdatedListener` `638`
- `putExtra()`方法`431, 461`
- `px` `198`

### Q

- `queryProductDetailsAsync()` `636`
- `queryPurchasesAsync()` `639`
- `quickboot snapshot` `44`
- `Quick Documentation` `75`

### R

- `RadioButton` `129`
- `ratios` `185`
- `READ_CALENDAR`权限`496`
- `READ_CALL_LOG`权限`496`
- `READ_CONTACTS`权限`496`
- `READ_EXTERNAL_STORAGE`权限`497`
- `READ_PHONE_STATE`权限`496`
- `READ_SMS`权限`496`
- `RECEIVE_MMS`权限`496`
- `RECEIVE_SMS`权限`496`
- `RECEIVE_WAP_PUSH`权限`496`
- `Recent Files Navigation` `56`
- `RECORD_AUDIO`权限`496`

#### 录音音频

- permission`705`

- `RecyclerView` `397`
  - 添加到布局文件`398`
  - `GridLayoutManager` `397`
  - 初始化`406`
  - `LinearLayoutManager` `397`
  - `StaggeredGridLayoutManager` `397`

#### RecyclerView Adapter

- 创建`404`
- `RecyclerView.Adapter` `398, 404`
- `getItemCount()`方法`398`
- `onBindViewHolder()`方法`398`
- `onCreateViewHolder()`方法`398`
- `RecyclerView.ViewHolder`
  - `getAdapterPosition()`方法`408`
- `registerForActivityResult()`方法`432, 446`
- `registerReceiver()`方法`463`
- `RelativeLayout` `130`
- `releasePersistableUriPermission()`方法`673`

#### 释放准备 609

#### 远程绑定服务 477

- 客户端通信`477`
- 实现`477`
- manifest 文件声明`479`
- `RemoteInput.Builder()`方法`522`
- `RemoteInput`对象`522`

#### 远程服务

- 启动与绑定`480`
- 发送消息`481`

#### 存储库

- 教程`593`
- `Repository Modules` `276`

#### 可调整尺寸模拟器 47

#### 资源

- 字符串创建`20`
- 资源文件`22`
- 资源管理`101`
- 资源管理器`53, 90`
- 结果接收器`463`
- 反向地理编码`719`
- 反向地理编码`718`

#### Room

- 数据访问对象（DAO）`576`
- 实体`576, 577`
- 内存数据库`583`
- `Repository` `576`
- `Room Database` `576`
- 教程`593`
- Room 数据库持久化`575`
- Room 持久库`544, 575`
- 根元素`129`
- 根视图`131`

#### 运行

- 工具窗口`53`

#### 运行设备

- 工具窗口`65`
- `runOnUiThread()` `637`

### S

- `safeargs` `337`
- 示例数据`146, 411`
- 教程`411`
- 保存状态`275, 307`
- `SavedStateHandle` `308, 309`
- `contains()`方法`309`
- `keys()`方法`309`
- `remove()`方法`309`
- 保存状态模块`307`
- `SavedStateViewModelFactory` `308`
- `ScaleGestureDetector`类`249`
- 与比例无关`197`
- SDK 软件包`5`
- 安全套接层（SSL）`89`
- `SeekBar` `261`
- `sendBroadcast()`方法`461, 463`
- `sendOrderedBroadcast()`方法`461, 463`
- `SEND_SMS`权限`496`
- `sendStickyBroadcast()`方法`461`
- 传感器权限`496`

#### 服务

- 解剖`428`
- 在系统启动时启动`429`
- manifest 文件项`428`
- 概览`92`
- 在独立进程中运行`429`
- `ServiceConnection`类`480`
- 服务进程`102`
- 服务重启选项`428`
- `setAudioEncoder()`方法`704`
- `setAudioSource()`方法`704`
- `setBackgroundColor()` `202`
- `setCompassEnabled()`方法`724`
- `setContentView()`方法`201, 207`
- `setId()`方法`202`
- `setMyLocationButtonEnabled()`方法`725`
- `setOnClickListener()`方法`223, 225`
- `setOnDoubleTapListener()`方法`237, 240`
- `setOutputFile()`方法`704`
- `setOutputFormat()`方法`704`
- `setResult()`方法`433`
- `setRotateGesturesEnabled()`方法`725`
- `setScrollGesturesEnabled()`方法`725`
- `setText()`方法`126`
- `setTiltGesturesEnabled()`方法`725`
- settings.gradle 文件`790`
- settings.gradle.kts 文件`790`
- `setTransition()` `351`
- `setVideoSource()`方法`704`
- `setZoomControlsEnabled()`方法`724, 725`
- SHA-256 证书指纹`435`
- `shouldOverrideUrlLoading()`方法`738`
- `SimpleOnScaleGestureListener` `249`
- `SimpleOnScaleGestureListener`类`251`
- SMS 权限`496`
- `Snackbar` `379`

#### 快照

- 模拟器`44`
- `sp` `197`
- 缩放链`154`
- 缩放内部`184`

#### SQL 540

- SQL CREATE`548`
- SQLite`539`
- 命令行使用`441`
- 列和数据类型`539`
- 概览`540`
- 主键`539`
- 教程`593`
- `SQLiteDatabase` `544`
- `SQLiteOpenHelper` `546`
- SQL `SELECT` `550`
- `StaggeredGridLayoutManager` `397`
- `startActivity()`方法`431`
- `startForeground()`方法`430`
- `START_NOT_STICKY` `428`
- `START_STICKY` `428`

#### 状态

- 恢复`126`
- 状态更改`105`
- 状态完成`72`
- 状态栏`69`
- 粘性广播`463`
- 停止状态`104`
- 系统广播`467`

### T

- TabLayout
  - 添加到布局`389`
  - 示例`386`
  - `getItemCount()`方法`398`
  - 概览`385`
- `TableLayout` `130`
- `tabGravity` `394`
- `tabMode` `394`
- 电话管理器`90`
- 模板
  - 空白`133`
  - 构建自定义`777`
  - 主题化`777`
  - 教程`781`
- 时间周期`351`
- TODO
  - 工具窗口`55`
- Toolbar`258`
- 工具窗口`55`
- 触摸动作`230`
- 触摸事件监听器`231`
- 触摸事件`229`
- 拦截`229`

### U

- `UiSettings`类`713`
- `unbindService()`方法`427`
- `unregisterReceiver()`方法`463`
- 上传键`612`
- `UriMatcher` `554, 560`
- `UriMatcher`类`554`
- URL 映射`767`
- USB 连接问题
  - 解决`62`
- `USE_BIOMETRIC` `662`
- 用户界面状态`109`
- `USE_SIP`权限`496`

#### V

- 版本目录`219`
- 依赖`221`
- 库`220`
- `libs.versions.toml`文件`220`
- 插件`220`
- 版本`220`
- 视频播放`683`
- `VideoView`类`683`
- 方法`683`
- 支持的格式`683`
- 视图绑定
  - 启用`96`
  - 使用`96`
- 视图类
  - 设置属性`209`
  - 转换`145`
- `ViewGroup` `129`
- 视图组`129`
- 视图层级`131`
- `ViewHolder`类`398`
- 示例实现`405`
- ViewModel
  - 添加`LiveData` `285`
  - 数据访问`283`
  - 概览`274`
  - 保存状态`307`
  - 教程`279`
  - `ViewModelProvider` `282`
- ViewModel 保存状态`307`
- ViewPager
  - 添加到布局`389`
  - 示例`386`
- 视图`129`
- Java 创建`201`
- 视图系统`90`
- 虚拟设备配置对话框`28`
- 虚拟传感器`43`
- 可见进程`102`

#### W

- `WebViewClient` `733, 738`
- WebView 视图`451`
- 加权链`154, 184`
- 欢迎屏幕`49`
- 小组件尺寸`155`
- 小组件组对齐`177`
- 小组件调板`190`
- WiFi 调试`63`
- 无线调试`63`
- 无线配对`63`
- `wrap_content`属性`199`
- `WRITE_CALENDAR`权限`496`
- `WRITE_CALL_LOG`权限`496`
- `WRITE_CONTACTS`权限`497`

### X

- XML 布局文件
  - 手动创建`197`
  - vs. Java 代码`201`
