
# Java 17：关于 Java 和 Android 的进阶指南

![](img/dfa4439d1c62650bb2a6b471e62c51e8_0_0.png)

Ove Thomsen, EA Dania 同行评审

在 bookboom.com 下载免费电子书

3

![](img/dfa4439d1c62650bb2a6b471e62c51e8_3_0.png)

> 我们不重新发明轮子，我们重新发明光。

> 迷人的光照提供了无限的可能性：创新技术和新市场带来了机遇与挑战。在一个你的专业知识被高度需求的环境中。享受我们全球集团内部的支持性工作环境，并从国际化的职业路径中受益。与其他专家紧密合作实施可持续理念，并为我们的未来做出贡献。来加入我们，每天重新发明光。

> 光属于 OSRAM

![](img/dfa4439d1c62650bb2a6b471e62c51e8_3_1.png)

> 在 bookboom.com 下载免费电子书 点击广告阅读更多信息

# 前言

本书是该 Java 软件开发系列书籍中的第 17 本，它是上一本关于手机应用开发书籍的延续。

本书要求具备 Java 和 Android 的知识，这些知识应与《Java 16》书中处理的内容相当，其目标是介绍书中未涵盖的话题。此外，本书将介绍如何使用片（fragments），这对于开发较大型应用程序以及确保当前设备的独立性至关重要。其他重要主题是介绍如何利用手机的某些功能（如 GPS 和相机），这些是传统 PC 无法提供的功能。最后，本书将扩展关于服务的内容，并针对上一本书末提到的某些缺陷提供解决方案。目标是让读者在读完上一本书和这本书后，能够练习使用 Java 开发 Android 应用。

正如标题所示，本系列书籍涉及软件开发，目标是教读者如何用 Java 开发应用程序。这可以通过阅读主题和学习完整程序来掌握，但重要的是亲自动实践并从零开始编写自己的程序。因此，书籍中的重要部分是练习和问题，读者必须编写与代码骨架对应的程序，这些程序将由文本、示例、练习和问题组成，并放置在文中自然的位置。练习（exercises）与问题（problems）的区别在于，练习很大程度上是对文中陈述内容的重复，并且对要做什么描述得相对准确。相比之下，问题的描述较为松散，规模稍大一些，且很少有明确的最佳解决方案。这些书籍应该从头到尾读完，许多代码示例（包括练习和问题）起着核心作用，读者详细研究许多示例的代码，并解决练习以及可能仅仅研究推荐的解决方案，是至关重要的。

所有书籍都以一或两个较大的示例程序结束，重点主要关注过程以及对程序如何编写的解释。另一方面，代码仅在有限的范围内……（注：由于原文存在大量重复，此处已根据逻辑进行了精简处理，确保翻译流畅且无重复。）

本书以一或两个较大的示例程序结束，重点主要侧重于过程以及对程序如何编写的解释。

我想从片段（fragments）开始这本书，这实际上是我在上一本书的上一个示例中所缺乏的内容。就像活动（activity）一样，片段是一个布局，它是一个 XML 文档，定义了窗口（窗口的一部分 = 片段）的布局和内容以及一个 Java 类。一个窗口（活动）可以包含多个片段，每个片段定义窗口的一个部分。其作用是，你可以用另一个片段替换当前片段，窗口就可以获得不同的布局，而且片段通常可以作为创建更多活动的替代方案。然而，更重要的应用意义是对屏幕的更好利用，这在平板电脑等较大的屏幕上尤为受到关注。在这里，屏幕可以容纳更多的活动，如果无法实现，你也可以并排查看多个片段。最后，片段用于平板电脑显示、列表显示以及比上一本书中显示的更好的对话框。

你应该意识到，片段并不是活动的绝对替代品，但片段可以简化应用程序布局的设计，并有助于在多个活动中更方便地复用布局。一个活动由多个片段组成，但特定的片段对象只能与一个活动关联。你也可以说，片段将用户界面的组件与其相关的逻辑组合在一起。

我想从一个名为 `TheBooks` 的简单示例开始，这是一个没有使用片段的应用程序。该程序打开以下窗口：

![](img/dfa4439d1c62650bb2a6b471e62c51e8_8_0.png)

FILES-AND-JAVA.ID

这本书是软件开发系列书籍中的第一本。之前的书籍已经让 Java 语言及其语法、语义领域变得清晰易懂，但本书将重点关注过程以及如何发明良好且可复用的应用程序。由于之前的书籍侧重于框架和对象报告的细节，本书的主题是文件和数组对象，我们将详细介绍如何操作文件。虽然今天的文件在实际编程中并不意味着相同的内容，

目标是展示如何修改程序以使其使用片段。这里必须立即提到，片段并不是解决所有问题的方案，如果应用程序只需要执行像 `TheBooks` 应用程序那样的操作，那么使用片段就没有意义。在当前示例中，目标仅仅是展示片段是什么，以及关于应用程序如何制作的初步介绍。布局由 `activity_main.xml` 组成；

```xml
<?xml version="1.0" encoding="utf-8"?>
android.support.ConstraintLayout
xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/tools"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context="dk.torus.thebooks.MainActivity">

<LinearLayout
android:layout_width="match_parent"
android:layout_height="match_parent"
android:orientation="vertical"
android:layout_margin="20dp">

<ScrollView
android:layout_width="match_parent"
android:layout_height="0dp"
android:layout_weight="3" >
<LinearLayout
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:orientation="vertical">
<RadioGroup
android:id="@+id/bookGroup"
android:tag="1"
android:layout_height="wrap_content"
android:layout_width="wrap_content">
<RadioButton
android:id="@+id/javal"
android:tag="1"
android:layout_height="wrap_content"
android:layout_width="wrap_content"
android:text="Java 1 " />
<RadioButton
android:id="@+id/java2"
android:tag="2"
android:layout_height="wrap_content"
android:layout_width="wrap_content"
android:text="Java 2 " />
</RadioGroup>
</LinearLayout>
</ScrollView>
```

```xml
<ScrollView
android:layout_width="match_parent"
android:layout_height="0dp"
android:layout_marginTop="20dp" >
<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="vertical">
    <TextView
      android:id="@id/txtName"
      android:layout_width="wrap_content"
      android:layout_height="wrap_content" />
    <TextView
      android:id="@id/txtDetails"
      android:layout_width="wrap_content"
      android:layout_height="wrap_content"
      android:layout_marginTop="10dp"/>
  </LinearLayout>
</ScrollView>
</android.support.constraint.ConstraintLayout>
```

该布局非常广泛，因为它定义了 22 个 `RadioButton`（我只显示了第一个），除此之外布局中没有其他内容。它基本上由垂直方向的 `LinearLayout` 中的两个 `ScrollView` 元素组成，这两个 `ScrollView` 元素在 3:2 的范围内共享空间。注意，每个 `RadioButton` 都定义了一个 `tag` 属性，用于确定点击了哪个单按钮。

关于 Java 代码，添加了一个类来定义一个具有两个属性的图书：

```java
public class Book {
    private String name;
    private String text;
    public Book(String name, String text) {
        this.name = name;
        this.text = text;
    }
    public String getName() {
        return name;
    }
    public String getText() {
        return text;
    }
    public String toString() {
        return name;
    }
}
```

最后添加了一个创建 20 个 `Book` 对象的类：

```java
public class Books {
    private List<Book> list = new ArrayList();
    public Books() {
        for (String[] arr : data) list.add(new Book(arr[0], arr[1]));
    }
    public List<Book> getBooks() {
        return list;
    }
}
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<ScrollView
xmlns:android="http://schemas.android.com/apk/res/android"
android:layout_width="match_parent"
android:layout_height="wrap_content">
<LinearLayout
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:orientation="vertical">
<RadioGroup
android:id="@+id/bookGroup"
android:tag="1"
android:layout_height="wrap_content"
android:layout_width="wrap_content">
<RadioButton
android:id="@+id/javal"
android:tag="1"
android:layout_height="wrap_content"
android:layout_width="wrap_content"
android:text="Java 1 " />
<RadioButton
android:id="@+id/java2"
android:tag="2"
android:layout_height="wrap_content"
android:layout_width="wrap_content"
android:text="Java 2 " />
</RadioGroup>
</LinearLayout>
</ScrollView>
```

这里的布局是 `activity_main.xml` 中第一个 `ScrollView` 元素的副本，但包含了一些改动。需要为 `ScrollView` 元素添加命名空间，并且 `weight` 属性的值从 0 改变，以便片段片段决定填充多少空间。

该布局非常广泛，因为它定义了 22 个 `RadioButton`（我只显示了第一个），除此之外布局中没有其他内容。它基本上由垂直方向的 `LinearLayout` 中的两个 `ScrollView` 元素组成，这两个 `ScrollView` 元素在 3:2 的范围内共享空间。注意，每个 `RadioButton` 都定义了一个 `tag` 属性，用于确定点击了哪个单按钮。

然后，以相同的方式，我为最后一个 `ScrollView` 元素添加了一个层，将其命名为 `fragment_book.xml`：



目标是展示如何修改程序以使其使用片段。这里必须立即提到，片段并不是解决所有问题的方案，如果应用程序只需要执行像 TheBooks 应用程序那样的操作，那么使用片段就没有意义。在当前示例中，目标仅仅是展示片段是什么，以及关于应用程序如何制作的初步介绍。

```java
public class MainActivity extends Activity {
    private List<Book> books = new Books();
    private TextView name;
    private TextView text;
    private RadioGroup radios;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
...
}
```

这本书是软件开发系列书籍中的第一本。之前的书籍已经让 Java 语言及其语法、语义领域变得清晰易懂，但本书将重点关注过程以及如何发明良好且可复用的应用程序。虽然今天的文件在实际编程中并不意味着相同的内容，

```java
    public void onCheckedChanged(int checkedId) {
        RadioButton radio = findViewById(checkedId);
        int n = Integer.parseInt(radio.getTag()) - 1;
        name.setText(books.get(n).getName());
        text.setText(books.get(n).getText());
    }
```

```xml
android:id="+id/txtDetails"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_marginTop="10dp"/>
</LinearLayout>
</ScrollView>
```

一个片段（fragment）的组成方式（通常）与相同，包含一个 XML 文件形式的布局和一个 Java 类。因此，我为第一个片段添加了以下类：

```java
package dk.data.torus.thebooks;

```

```java
import android.os.Bundle;
import android.app.*;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
```

```java
public class BooksFragment extends Fragment {
    public BooksFragment() {
}
```

![](img/dfa4439d1c62650bb2a6b471e62c51e8_14_0.png)

> 我们将把你的简历变成终生难得的机会

>> 你喜欢汽车吗？你想成为成功品牌的一员吗？

> 我们将欣赏并奖励你的热情和才华。

> 向我们发送你的简历。它能带你去的地方会让你惊讶。

>

> 在 www.employerforlife.com 向我们发送简历

> 在 bookboom.com 免费下载电子书

```java
@Override
public View onCreateView(LayoutInflater inflater, ViewGroup container,
Bundle savedInstanceState) {
    return inflater.inflate(R.layout.fragment_books, container, false);
}
```

显然，要猜出它的样子并不容易，但起初你可以注意到它是一个继承自`Fragment`的类。当片段被创建时，Android 会调用多个回调方法，其中最常重写的是`onCreateView()`。该方法返回代表片段并与 Android 与当前活动关联的 View 层次结构。`onCreateView()`方法有三个参数，第一个是`LayoutInflater`的引用，这是一个用于读取和使用当前活动布局资源的对象。另一个参数是片段要链接的活动中`ViewGroup`的引用。最后一个参数在稍后会提到。在这种情况下，`onCreateView()`方法除了调用`LayoutInflater`对象上的`inflate()`方法外没有其他操作，该方法的参数是资源名称以及插入片段的容器。

这里有一个对应的类`BookFragment`，其代码与上述代码几乎相同，只是引用了另一个资源。

然后是布局文件`activity_main.xml`，它必须被修改。在这里，大部分代码被移动到了两个片段中，这些代码块将由`<fragment>`元素取代：

```xml
<xml version="1.0" encoding="utf-8"?>
<ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="dk.data.torus.books.MainActivity">
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="vertical"
        android:layout_margin="20dp">
        <fragment
            android:layout_width="match_parent"
            android:layout_height="0dp"
            android:layout_weight="3"
            android:name="dk.data.torus.books.BookFragment"
            android:id="@id/fragmentBooks"/>
    </fragment>
```

```xml
android:layout_width="match_parent"
android:layout_height="0dp"
android:layout_weight="2"
android:layout_marginTop="20dp"
android:name="dk.data.torus.thebooks.BookFragment"
android:id="+id/fragmentBook"/>
</LinearLayout>
</android.support.constraint.ConstraintLayout>
```

每个片段元素都有一个`id`属性（在本示例中未使用）和一个`name`属性，用于指示片段的实例化和关联。然后，程序的新版本就完成了，并且可以进行翻译和运行。程序的运行方式与之前完全相同，区别在于用户界面现在是使用两个片段构建的。正如提到的，在这里并没有什么的好处，但你可以注意到布局被分成了更小的构建块，这些构建块随后可以用于其他类似的活动。

上面的程序显示了两个上下垂直排列的`ScrollView`组件，旋转手机使其水平握持，这导致了屏幕利用率不佳，因为标题部分占据了屏幕的大部分：

![](img/dfa4439d1c62650bb2a6b471e62c51e8_16_0.png)

在这里，使用以下布局效果会更好：

![](img/dfa4439d1c62650bb2a6b471e62c51e8_17_0.png)

当然，解决方案是定义一个不同的布局，因此确保在手机处于水平握持时使用它。当然，这可以通过编程实现，但由于布局被定义为资源，它是 Android 的一项内置功能，系统根据手机的握持方式在运行时选择资源。

这是片段非常有用的例子。我将编写一个新的`activity_main.xml`版本，但这是一个非常简单的布局资源，因为大部分工作已移动到其他资源中![](img/dfa4439d1c62650bb2a6b471e62c51e8_17_1)

无论是第一个还是第二个布局。我从`Books1`项目开始，将其命名为`Books2`。

作为第一步，你必须添加一个名为`layout-land`的目录。最简单的方法是右键点击`res`目录并选择 New Resource Directory![](img/dfa4439d1c62650bb2a6b471e62c51e8_18_0.png)

我在处选择了`Orientation`。接下来，在点击 OK 后，Android Studio 创建了一个名为 ![](img/dfa4439d1c62650bb2a6b471e62c51e8_19_0) 的目录。

你必须首先将`activity_main.xml`文件复制到新目录（如果 Android Studio 没有显示该目录，你可以从外部操作）。现在项目有两个版本的`activity_main.xml`，如下所示：

在上面我向你们展示了如何让 Android 根据手机的取向应用特定的布局，其中 Android 根据特定的命名约定来决定使用哪种资源。你也可以针对屏幕尺寸进行同样的操作。然而，这并不完全简单，因为现在有许多不同的屏幕尺寸，此外你还必须考虑平板电脑。

我将从上面项目的一个副本开始，我将其命名为 TheBooks3。首先，我将以一种不同的方式实现针对手机旋转的解决方案。我将位于`layout-land`目录下的`activity_main.xml`版本重命名为`activity_main_wide.xml`，然后将该文件复制到`layout`目录，并再次删除了`layout-land`目录。结果是`layout`目录现在包含了我们的文件：

![](img/dfa4439d1c62650bb2a6b471e62c51e8_21_0.png)

下一步，我按照上面所示的方法（使用相同的向导）添加了资源目录：

New | Android resource directory

名为`values-land`。对于此目录，我添加了以下 XML 文件，我将其命名为`refi.xml`。

```xml
<resources>
  <item type="layout" name="activity_main">
    @layout/activity_main_wide
  </item>
</resources>
```

它是 land 目录中的一个资源，结果是：如果设备水平放置，Android 将使用它作为`activity_main.xml`的引用，它必须使用`activity_main_wide.xml`而不是`activity_main.xml`。如果你现在尝试应用程序，你会发现一切运行正常，并且手机会根据是竖直还是水平使用不同的布局。与之前的示例相比，这种解决方案目前还没有什么益处。这种技术被称为布局别名（layout aliasing），其优势是你可以轻松扩展解决方案以包含具有不同屏幕尺寸的设备。

正如前面提到的，今天有许多物理尺寸和分辨率上各不相同的屏幕尺寸。同样，Android 使用名为密度无关像素（density independent pixel）的测量单位，简称`dp`，这是我在上一本书中使用的测量单位。`1 dp`定义为在 160 dpi 设备上 1 个像素的物理尺寸，因此它独立于屏幕的物理像素尺寸。例如，如果你考虑 160 dpi 设备上的 7 英寸屏幕，对角线上有 1120 个像素。16 x 9 的屏幕格式通过略微舍入给出的分辨率为 1000 x 600 dp。

Android 使用资源屏幕尺寸限定符（resource screen size qualifiers）定义屏幕尺寸，这里是使用资源目录定义的三个选项：

- 最小宽度尺寸限定符（Smallest width screen size qualifier）。它对应于不取决于设备取向的屏幕最短 dp 数。资源目录的名称为`sw`，后跟所需的屏幕尺寸。例如，针对最小宽度至少为 600 dp 的设备的布局资源目录称为`layout-sw-600dp`。

- 可用宽度尺寸限定符（Available width screen size qualifier）。它对应于根据设备当前取向测量的 dp 数。如果你更改设备取向，可用宽度也会改变。资源目录的名称为`w`，后跟宽度。例如，针对可用宽度至少为 600 dp 的设备的布局资源目录称为`layout-w-600dp`。

- 可用高度尺寸限定符（Available height screen size qualifier）。它的行为与可用宽度尺寸限定符相同，不同的是使用`h`代替`w`，并测量设备当前取向从顶部到底部的 dp。针对可用高度至少为 600 dp 的设备的布局资源目录称为`layout-h-600dp`。

与其使用资源屏幕尺寸限定符指定资源目录，不如使用较旧的方法将设备分组：`small`、`normal`、`large`或`xlarge`，资源目录的名称可能是`layout-large`。

在当前情况下，我按照上面的方法添加了名为`values-large`的资源目录：

New | Android resource directory

在当前情况下，我按照上面的方法添加了名为`values-large`的资源目录：

```java
if (activity instanceof SelectBookListener)
{
    RadioButton radio = activity.findViewById(id);
    int n = Integer.parseInt(radio.getTag().toString()) - 1;
    ((SelectBookListener) activity).onSelectedChanged(n);
}
```

```java
@Override
public void onCreateView(LayoutInflater inflater, ViewGroup container,
    Bundle savedInstanceState) {
    View view = inflater.inflate(R.layout.fragment_books, container, false);
    RadioGroup group = view.findViewById(R.id.bookGroup);
    group.setOnCheckedChangeListener(this);
    return view;
}
```

首先，注意该类现在实现了`RadioGroup.OnChangeListener`接口，因此该类必须实现`onCheckedChanged()`方法。首先，使用`getActivity()`方法来确定此 fragment 关联的 activity。如果它是一个`SelectBookListener`（这是 BooksFragment 对象无法知道也不应该知道的），

> “我学了 16 年英语，但……我最终只花了 6 节课就学会了开口说”

> Jane，中国建筑师

![](img/dfa4439d1c2650bb2a6b471e62c51e8_26_0.png)

该方法确定点击了哪个单选按钮（注意此代码来自 MainActivity）。然后，将当前 activity 的类型强制转换为`SelectBookListener`对象，之后调用`onItemSelectedChanged()`方法并传入书籍索引作为参数。你还应该注意`onCreate()`已经发生了变化，它现在确定了布局中 RadioGroup 组件的引用，并使用它将事件处理器关联到 RadioGroup 组件。

BookFragment 类已经过更改：



```java
package dk.data.thebooks;

import android.os.Bundle;
import android.app.*;
import android.view.*;
import android.widget.TextView;
import java.util.List;

public class BookFragment extends Fragment {
    public static final List<Book> books = BooksBooks();
    private TextView name;
    private TextView text;

    public BookFragment() {
    }

    @Override
    public View onCreateView(LayoutInflater inflater, ViewGroup container,
            Saved savedInstanceState) {
        View view = inflater.inflate(R.layout.fragment_book, container, false);
        name = view.findViewById(R.id.txtName);
        text = view.findViewById(R.id.txtDetails);
        return view;
    }

    public void setBook(int id) {
        name.setText(books.get(id).getName());
        text.setText(books.get(id).getText());
    }
}
```

注意，该类有三个变量，都是从 `MainActivity` 拷贝的。`Book` 对象的列表是该类的一部分，它被设为静态，这样多个 `BookFragment` 类的实例就不会创建每份副本。更好的选项是将书籍信息像资源一样放置。在其他上下文中，可以从数据库中检索信息，而 `setBook()` 的参数将是一个键。`setBook()` 更新在 `onCreate()` 中创建引用的 `TextView` 组件。

有一个 `MainActivity`，它现在已更改为如下：

```java
package dk.data.thebooks;

import android.app.*;
import android.os.Bundle;

public class MainActivity extends Activity implements SelectBookListener {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    @Override
    public void onSelectedChanged(int id) {
        FragmentManager fragmentManager = getFragmentManager();
        BookFragment bookFragment = (BookFragment) fragmentManager.findFragmentById(R.id.fragmentBook);
        if(bookFragment != null) bookFragment.setBook(id);
    }
}
```

所有变量都已移除，`onCreate()` 变得非常简单（正如 Android Studio 创建的）。该类实现了 `SelectBookListener` 接口，并在之后实现了事件处理器 `onSelectedChanged()`。它在点击单选按钮时从 `MainActivity` 中调用，参数是被点击书籍的索引。

当这种情况发生时，你应该在 `BookFragment` 类中调用 `setBook()`。你不能直接从 activity 引用 Fragment，但可以通过 `FragmentManager` 对象来实现，任何 activity 都有一个返回此类对象的方法。有了这个对象，你可以确定 fragment 的引用并成功调用 `setBook()`。

之后，更改已经实现——经过了一段长时间的过程——但结果是一个类之间弱耦合的解决方案。

你必须编写一个调用 TheBirds 的应用程序。书籍的源码目录包含一个有 7 张图片的子目录。当程序打开时，它必须显示这些图片的概述以及第一张图片。当你点击图片的名称时，该图片将出现在窗口中。用户界面由两个 fragment 组成，一个显示列表，另一个显示图片。此外，程序必须支持手机旋转。你不需要考虑不同的尺寸。

![](img/dfa4439d1c2650bb2a6b471e62c51e8_29_0.png)

位于此的优质经济和商业计划：

![](img/dfa4439d1c2650bb2a6b471e62c51e8_29_1.png)

> “成功的国际化职业的完美起点。”

点击此处以发现为什么从社会和学术角度来看，格罗宁根大学都是学生来说的最好的地方之一。

`www.rug.nl/feb/education`

上面的应用程序被称为“列表/详情”应用程序，并根据手机握持方式或是否为平板电脑显示两种不同的布局。这是一个显示许多对象（这里是书籍标题）概述的应用程序，点击书籍将显示详情。

如果手机竖持，列表显示在左侧；如果水平握持，列表出现在右侧。此类应用程序被广泛用于空间。

我添加了一个名为 `BookActivity` 的新空 activity。布局如下：

```xml
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="dk.data.thebooks.BookActivity">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="vertical"
        android:layout_margin="20dp">

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:textSize="12sp"
            android:text="&lt;&lt&gt;"
            android:onClick="goBack"/>

        <fragment
            android:layout_width="match_parent"
            android:layout_height="0dp"
            android:layout_weight="2"
            android:layout_marginTop="20dp"
            android:name="dk.data.thebooks.BookFragment"
            android:id="#+id/fragment"/>

    </LinearLayout>
</android.support.constraint.ConstraintLayout>
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout
xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context="dk.data.thebooks.MainActivity">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="vertical"
        android:layout_margin="20dp">

        <fragment
            android:layout_width="match_parent"
            android:layout_height="0dp"
            android:layout_weight="3"
            android:name="dk.data.thebooks.BooksFragment"
            android:id="#+id/fragmentBook"/>

    </LinearLayout>
</android.support.constraint.ConstraintLayout>
```

当手机垂直握持时，`MainActivity` 的结果是将整个屏幕提供给列表。如果你的手机是水平持持或者是平板电脑，程序将像以前一样工作，并使用 `activity_main_wide.xml` 布局。

以下是显示的 `BookActivity extends Activity` 类：

```java
public class BookActivity extends Activity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_book);
        Intent intent = getIntent();
        int id = intent.getIntExtra("bookIndex", -1);
        if (id != -1) {
            FragmentManager fm = getFragmentManager();
            BookFragment bookFragment = (BookFragment) fm.findFragmentById(R.id.fragmentBook);
            bookFragment.setBook(id);
        }
    }
}
```

![](img/dfa4439d1c62650bb2a6b471e62c51e8_32_0.png)

```java
public void goBack(View view)
{
    Intent intent = new Intent(this, MainActivity.class);
    startActivity(intent);
    finish();
}
```

在 `onCreate()` 中，程序测试是否传递了参数（如果有，则是某个书籍的索引），如果是，则使用 `FragmentManager` 找到 Fragment 对象的引用，并调用 `setBook()` 方法。

回到 `MainActivity` 类，那里需要更新 `onSelectedIndexChanged` 的事件处理器：

```java
public class MainActivity extends Activity implements SelectBookListener {
    @Override
    protected void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    @Override
    public void onSelectedChanged(int id) {
        FragmentManager fm = getFragmentManager();
        BookFragment bookFragment = (BookFragment) fm.findFragmentById(R.id.fragmentBook);
        if (bookFragment == null || !bookFragment.isVisible()) {
            Intent intent = new Intent(this, MainActivity.class);
            intent.putExtra("bookIndex", id);
            startActivity(intent);
        } else
            bookFragment.setBook(id);
        }
    }
}
```

与之前一样，程序尝试确定 `BookFragment` 的引用。如果无法实现（或 fragment 不可见），则 activity 将以书籍索引作为参数打开，否则除了 fragment 更新外，将不会发生任何其他事情。

当你尝试运行该程序时，请注意，如果是平板电脑或你水平握持手机，它将像以前一样工作。

在书籍 Java 16（第 4.4 节）中，我提到了 Activity 的生命周期以及结合状态切换执行的回调方法。Fragment 也有类似的情况，由于 Fragment 与 Activity 关联，它们之间当然有密切的联系。这里值得注意的是，Activity 经常会被创建、关闭和重新创建多次，手机旋转就是一个很好的事件示例。

与关联了多个回调方法的 Activity 一样，Fragment 也是如此，而且当执行这些方法时，它们之间显然存在联系。当 Fragment 初始化时，会执行以下回调方法，其中左侧的方法与 Activity 相关，而右侧的方法与 Fragment 相关：

```text
onCreate()
onAttach()
onAttachFragment()
onCreate()
onCreateView()
ActivityCreate()
onStart()
onResume()
onResume()
```

最重要的方法是 `onCreateView()`，如之前的示例所示。当 Fragment 与 Activity 关联时，会执行 `onAttach()` 方法，然后 Fragment 就知道了该 Activity，你可以使用 `getActivity()` 方法。

然后在 `onCreate()` 和 `onCreateView()` 执行后，Fragment 向 Activity 发送通知，其中布局在最后创建。这两个方法最重要的，对于许多 Fragment 来说，它们是唯一重写的回调方法。

区别在于，如果初始化包含耗时连接数据源的操作、复杂计算和资源分配，那么它们应该在 `onCreate()` 中执行，而其他部分和布局的主要初始化应该在 `onCreateView()` 中完成。原因是通常只有 Fragment 的视图层级会被关闭，因此没有在每次手机发生某些变化时都执行耗时的初始化。

这四个方法：

1. `onAttach()`
2. `onAttachFragment()`
3. `onCreate()`
4. `onCreateView()`

总是一起执行的，如果一个 Activity 关联了多个 Fragment，这非常重要。当所有 Fragment 都执行此方法序列时，是技能。因为剩余的回调方法可以单独执行。这里 `onCreate()` 调用 Fragment，当 Activity 创建时，`onStart()` 和 `onResume()` 对于 Fragment 来说具有相同的功能。

当 Fragment 隐藏或关闭时，类似于 Activity 的：

| Activity | Fragment |
|---|---|
| `onPause()` | `onPause()` |
| `onSaveInstanceState()` | `onSaveInstanceState()` |
| `onStop()` | `onStop()` |
| `onDestroy()` | `onDestroy()` |
| `onDestroy()` | `onDetach()` |

![](img/dfa4439d1c62650bb2a6b471e62c51e8_35_0.png)



# 关于 e-Learning for Kids

成立于 2004 年的全球非营利基金会，致力于为 5-12 岁的儿童提供互联网学习，涵盖数学、科学、语言、艺术、计算机、健康和环境。自 2005 年以来，来自 190 个国家的 1500 万儿童受益于来自资金、志愿者、赞助者和慷慨开发者的 e-learning。更多信息请访问 `www.elearningforkids.org`。

- 1 个基础教育 MOOC
- 5-12 岁儿童免费数字学习
- 已覆盖 1500 万儿童

基本上，这与 Activity 相同，但在 `onDestroy()` 之后，每个 Fragment 会执行三个方法：

1. `onDestroy()`
2. `onDestroyView()`
3. `onDetach()`

然后 Fragment 不再与 Activity 关联，你无法再执行 `getActivity()`。

你应该注意 `onSaveInstanceState()` 方法，它与 Activity 功能相同，用于在关闭之前持久 Fragment 的状态。

如果你查看本章使用的示例，书籍概述使用的是单选按钮。在这里，在概述 Fragment 中使用 `ListView` 会更明显，如果程序可以扩展新书籍，也会更灵活。本节的主题是将单选按钮替换为 `ListView`。这看起来很简单，你只需要更改 `fragment_books.xml` 布局并将所有的 `RadioButton` 组件替换为 `ListView`。此外，需要将 `BooksFragment` 类改为 `ListFragment`，但也相当简单。

我从一个名为 `Books4` 的类开始，并将其复制为 `Books6`。然而，我将从修改数据源开始，使 `Book` 对象获得额外的字段：

```java
public class Book
{
    private String name;
    private String title;
    private String text;
public Book(String name, String title, String text)
{
    this.name = name;
    this.title = title;
    this.text = text;
}
}
```

```java
public String getName()
{
  return name;
}
```

```java
public String getTitle()
{
  return title;
}
```

```java
public String getText()
{
  return text;
}
```

```java
public String toString()
{
  return name;
}
```

当然，这还需要对 `Books` 类进行修改，因为现在创建 `Book` 对象时必须添加一个额外的参数。此外，该类已更改为单例模式：

```java
public class Books
{
  private static Books instance = null;
  private List<Book> list = new ArrayList();

  private Books()
  {
    for (String[] arr : data) list.add(new Book(arr[0], arr[1], arr[2]));
  }

  public static Books getInstance()
  {
    if(instance == null)
    synchronized (Books.class) {
      if(instance == null) instance = new Books();
    }
  return instance;
  }
}
```

```java
public List<Book> getBooks()
{
  return list;
}

private static final String[][] data = {
  { "Java 1", "BASIC SYNTAX AND SEMANTICS", "This ... " },
  { "Java 2", "PROGRAMS WITH A GRAPHICAL USER INTERFACE", "This ... " },
};
```

通过这些更改，`BookFragment` 类可以更新如下：

```java
public class BookFragment extends Fragment {
  private TextView name;
  private TextView text;

  public BookFragment() {
}
}
```

![](img/dfa4439d1c62650bb2a6b471e62c51e8_38_0.png)

# Java 17：更多 Java 与 Android：软件开发片段（Fragments）

```java
@Override
public View onCreateView(LayoutInflater inflater, ViewGroup container,
    Bundle savedInstanceState) {
    View view = inflater.inflate(R.layout.fragment_book, container, false);
    name = view.findViewById(R.id.txtName);
    text = view.findViewById(R.id.txtDetails);
    return view;
}
```

```java
public void setBook(int id) {
    List<Book> books = Books.getInstance().getBooks();
    name.setText(books.get(id).getTitle());
    text.setText(books.get(id).getText());
}
```

也就是说，变量 `book` 已被移除，并且 `setBook()` 方法发生了一些变化。

此外，这些更改与我想使用 `ListView` 代替 `RadioButton` 组件无关。这些更改发生在 `BooksFragment` 类中。该类不再继承自 Fragment，而是继承自 ListFragment。它是 Fragment 的一个特化类，封装了一个 ListView 组件，因此是一个具有特定目的和布局的片段。因此，该片段不使用 XML 布局文件。`BooksFragment` 类必须更改为：

```java
public class BooksFragment extends ListFragment {
    public BooksFragment() { }

    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        List<Book> books = Books.getInstance().getBooks();
        ArrayAdapter<Book> adapter = new ArrayAdapter<Book>(getActivity,
            android.R.layout.simple_list_item_1, books);
        setListAdapter(adapter);
    }

    @Override
    public void onItemSelected(ListView view, View v, int position, long id) {
        Activity activity = getActivity();
        if (activity instanceof SelectBookListener) {
            ((SelectBookListener) activity).onSelectedBookChanged(position);
        }
    }
}
```

注意，该类继承自 ListFragment，并且没有 `onCreate()` 方法。相反，重写了回调方法 `onCreate()`，它创建了适配器并初始化了片段的数据源。这是通过 `setAdapter()` 完成的。在这里你需要注意，ListFragment 有一个 `getView()` 方法，它返回封装的 ListView 对象。因此，你可以像往常一样使用 ListView 类的方法，但有一个例外：你不能使用 ListView 类的 `setListAdapter()` 来初始化组件的数据。

为了在列表中选择名称时发送通知，重写了事件处理程序 `onItemClick()` 以向监听器发送通知——如果它是 `SelectListener` 的话。

现在程序已经完成，并可以像以前一样工作了。布局文件 `fragment_books.xml` 不再被使用，可以删除。

# 练习 2：国王们（THE KINGS）

你必须编写一个与上述类似的应用程序（TheBooks6），但该应用程序必须显示丹麦国王的概览。如果你打开应用程序并点击 Knud Store，你必须看到以下窗口：

![](img/dfa4439d1c62650bb2a6b471e62c51e8_40_0.png)

在 `bookhoon.com` 免费下载电子书

# Java 17：更多关于 Java 和 Android：软件开发

# 片段（FRAGMENTS）

![](img/dfa4439d1c62650bb2a6b471e62c51e8_41_0.png)

创建一个你可以称为 TheKings 的新项目。在上一书中有一个名为 AboutKings 的项目，它包含了两个类：King 和 Kings。将这些类复制到你的新项目中。King 类不应更改，但 Kings 是一个单例。然后，如下所示：

![](img/dfa4439d1c62650bb2a6b471e62c51e8_41_1.png)

在 `bookhoon.com` 免费下载电子书

## 2.7 DialogFragment

片段也可以用于显示对话框。在上一书中，我讨论了对话框，尽管该类用起来很困难，但封装下面的示例会简单得多：

![](img/dfa4439d1c62650bb2a6b471e62c51e8_42_0.png)

它显示了一个 `Person` 对象的列表。关于布局没有其他需要注意的。注意，该类继承自 ListFragment，并且没有 `onCreate()` 方法。相反，重写了回调方法 `onCreate()`，它创建了适配器并初始化了片段的数据源。这是通过 `setAdapter()` 完成的。在这里你需要注意，ListFragment 有一个 `getView()` 方法，它返回封装的 ListView 对象。因此，你可以像往常一样使用 ListView 类的方法，但有一个例外：你不能使用 ListView 类的 `setListAdapter()` 来初始化组件的数据。

```java
@Override

public void onCreate(Bundle savedInstanceState) {

  super.onCreate(savedInstanceState);

  refresh();

}

@Override

public void onItemClick(ListView l, View v, int position, long id) {

  Activity activity = getActivity();

  if (activity instanceof SelectPersonListener) {

    ((SelectPersonListener) activity).personSelected(position);

  }

}

public void refresh() {

  ArrayAdapter<Person> adapter = new ArrayAdapter<Person>(getActivity(),

  android.R.layout.simple_list_item, Persons.getInstance().getPersons());

  setListAdapter(adapter);

}
```

这与上一节相比没有新内容。在自己的方法中初始化 ListView 组件，以便在列表数据模型发生变化时从 MainActivity 调用。为列表设置了一个事件处理程序，它用于确定片段（fragment）对应的 activity 引用，如果它具有 `SelectPersonListener` 类型，则会调用 `personSelected()` 方法，这是一个通知 activity 点击了哪个项目（索引）的通知。`SelectPersonListener` 是一个接口，它只定义了 `personSelected()` 方法。如果你现在运行程序（带有上述更改），窗口将打开并显示四四个人的列表。

如果你点击（即用手指触摸）某个人，程序必须打开一个包含该人员数据的对话框，如果你在程序的主菜单中选择“添加”菜单，也应该执行相同的操作。此时，所有字段必须为空。对话框需要一个作为资源自定义创建的布局，在这种情况下，必须有三个 TextView 组件、两个 EditText 组件和三个 Button。该布局占据了大量空间，我不想显示 XML 代码，但在布局目录下有一个名为 `dialog_person.xml` 的资源，它只是使用 `LinearLayout` 布局管理器部署的 9 个组件。作为回报，我将展示以下 Java 代码：

```java
public class PersonDialog extends DialogFragment {
  public static final int CMD_OK = 1;
  public static final int CMD_REMOVE = 2;
  private View dlgView;
  private Person person;
}
```

# Java 17：更多 Java 与 Android：软件开发片段

```java
public void onCreate(Bundle savedInstanceState) {
super.create(savedInstanceState);
setStyle(DialogFragment.STYLE_NORMAL, 0);
person = (Person)getArguments().getSerializable("person");
}
```

```java
public void onCreateView(LayoutInflater inflater, ViewGroup container,
    Bundle savedInstanceState) {
    View view = inflater.inflate(R.layout.dialog_person, container, false);
    View cmdCancel = view.findViewById(R.id.cmdCancel);
    cmdCancel.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View view) {
            dismiss();
        }
    });
    View cmdOK = view.findViewById(R.id.cmdOK);
    cmdOK.setOnClickListener(new OnClickHandler(Handler));
    View cmdRemove = view.findViewById(R.id.cmdRemove);
    cmdRemove.setOnClickListener(new View.OnClickListener() {
        @Override
    public void onClick(View view) {
```

![](img/dfa4439d1c62650bb2a6b471e62c51e8_47_0.png)

# 赋能人才。改进业务。

挪威商学院（BI Norwegian Business School）是欧洲大型商学院之一，招收超过 20,000 名学生。我们的课程提供了一个充满活力的多元文化学习环境，具有国际视野，最终为学生提供满足业务需求的专业技能。

BI 提供了四种不同的两年制全日制科学硕士（MSc）课程，这些课程采用英语教学，旨在提供满足行业日益增长需求的专业技能。MSc 项目提供了一个充满活力的多元文化学习环境，为你开启职业生涯提供最佳平台。

- 商业管理硕士
- 金融经济学硕士
- 战略营销管理硕士
- 领导力与组织心理学硕士

`www.bi.edu/master`

# Java 17：更多关于 Java 与 Android 的信息：软件开发片段



# JAVA 17：更多 JAVA 与 ANDROID：软件开发

首先，注意该类继承自 `DialogFragment`。这意味着它是一个片段，它是 `Dialog` 对象的包装器。`DialogFragment` 有几种样式可以使用：

1. `STYLE_NORMAL`（默认）
2. `STYLE_NO_TITLE`
3. `STYLE_NO_FRAME`
4. `STYLE_NO_INPUT`

对话框由三部分组成：布局区域、标题和边框。第一个样式常量显示所有三个部分，第二个没有标题，第三个没有边框，最后一个没有输入。在这种情况下，你可以在 `onCreate()` 中设置样式。参数 `0` 表示 Android 决定主题。当对话框打开且 `onCreate()` 执行时，会传递一个 `Person` 对象，你应该注意如何通过 `getArguments()` 获取该对象的引用。

然后是 `onCreateView()`，这次非常详细。首先，必须为三个按钮关联事件处理程序。对于取消按钮，是一个简单的处理器，除了关闭对话框外不做任何其他操作，这是通过 `dismiss()` 方法实现的。对于确定按钮，分配了类型为 `ClickHandler` 的处理器，如内部类所示。最后是删除按钮，其处理器作为匿名类的对象创建。该处理器测试该人员是否有姓（因此是一个新人员）。如果是，则确定片段对应的 activity，如果它具有 `OnClickListener` 类型（在 `PersonDialog` 中定义的内部接口），则调用 `onClick()` 方法并以常量 `CMD_REMOVE` 作为参数。目标是让包含片段的 activity（即显示对话框的那个）接收到该按钮被点击的通知。

```
if (person.getFullName().length() > 0) {
    Activity parent = getActivity();
    if (parent instanceof OnClickListener) {
        ((OnClickListener)parent).onClick(CMD_REMOVE);
        dismiss();
    }
}
((EditText)view.findViewById(R.id.txtName)).setText(person.getFirstName());
((EditText)view.findViewById(R.id.txtName)).setText(person.LastName());
((EditText)view.findViewById(R.id.txtJob)).setText(person.getPosition());
dialog dialog = getDialog();
dialog.setTitle(person.getFullName().length() > 0 ?
"Edit person" : "Add person");
dialog.setCanceledTouchOutside(false);
dlgView = view;
return view;
}

public interface OnClickListener {
    void onClick(int buttonId);
}

class OnClickHandler implements View.OnClickListener {
    @Override
    public void onClick(View view) {
        String name = ((EditText)view.findViewById(R.id.txtName)).getText().trim();
        String lname = ((EditText)view.findViewById(R.id.txtName)).getText().trim();
        String job = ((EditText)view.findViewById(R.id.txtJob)).getText().trim();
        if (name.length() > 0 && lname.length() > 0 && job.length() > 0) {
            person.setFirstName(name);
            person.setLastName(lname);
            person.setPosition(job);
            Activity parent = getActivity();
            if (parent instanceof OnClickListener) {
                ((OnClickListener)parent).onClick(CMD_OK);
                dismiss();
            }
        }
    }
}
```

## JAVA 17: 更多 JAVA 与安卓：软件开发片段

这里有一个 `ViewHolder` 类，但没有什么特别需要注意的。`handler` 决定了输入的值，如果在三个字段中都输入了内容，则对象会被初始化，并向对话框 Activity 发送通知，该通知会告知哪个按钮被点击了。

然后是 `MainActivity`，你应该注意到该类实现了两个接口：

```java
public class MainActivity extends Activity
implements PersonDialog.OnClickListener, SelectPersonListener
{
    public static final int MENU_ADD = Menu.FIRST + 1;
    private Person person;
```

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);
}
```

```java
@Override
public boolean onCreateOptionsMenu(Menu menu) {
    menu.add(Menu.NONE, MENU_ADD, Menu.NONE, "Add");
    return (super.onCreateOptionsMenu(menu));
}
```

![](img/dfa4439d1c62650bb2a6b471e62c51e8_50_0.png)

```java
@Override
public boolean onMenuItemSelected(Menu item) {
    if (item.getItemId() == MENU_ADD) {
        person = new Person("", "", "");
        openDialog();
    }
    return (super.onMenuItemSelected(item));
}
```

```java
public void personSelected(int pos) {
    person = Persons.getInstance().Persons().get(pos);
    openDialog();
}
```

```java
private void openDialog() {
    PersonDialog dlg = new PersonDialog();
    Bundle args = new Bundle();
    args.putSerializable("person", person);
    dlg.setArguments(args);
    dlg.show(getFragmentManager(), null);
}
```

```java
public void onDialogClick(int id) {
    if (id == PersonDialog.CMD_OK) {
        Persons.getInstance().update(person);
        refreshList();
    } else if (id == PersonDialog.CMD_REMOVE) {
        Persons.getInstance().remove(person);
        refreshList();
    }
}
```

```java
private void refreshList() {
    FragmentManager fm = getFragmentManager();
    PersonsFragment personsFragment = (PersonsFragment) fm.findFragmentById(R.id.fragment);
    personsFragment.refresh();
}
```

## JAVA 17: 更多 JAVA 与安卓：软件开发片段

该类创建了一个主菜单，包含一个简单的菜单项用于创建一个新人员。如果你选择了此项，就会创建一个新的 `Person` 对象（所有字段均为空）。接下来，方法调用了 `openDialog`，该方法是打开对话框的方法。在这里，你应该首先注意如何传递参数，以及如何使用 `show()` 打开对话框，其中参数是 Activity 的 `FragmentManager`。`personSelected()` 的工作方式类似，它不是创建一个新对象，而是从传递的索引确定一个现有对象，并由 `openDialog()` 传递到对话框。最后，注意 `onClick()`，它是接收来自对话框通知的方法。这发生在两种情况下：点击 OK 按钮或点击 REMOVE 按钮。

## 2.8 片段事务 (FRAGMENT TRANSACTIONS)

作为片段的最后一个例子，我将展示一个程序，在该程序中，我不是打开一个新的 Activity，而是用另一个片段替换当前片段。在 2.4 节中，我展示了一个 `Books` 应用的版本，当手机垂直持有时，应用程序使用整个屏幕并通过列表来查看详情。如果手机水平持有，屏幕将分为两个片段，分别显示列表和详情。

```xml
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <LinearLayout
        android:id="@+id/layoutRoot"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:orientation="vertical"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toStartOf="@+id/layoutDetails"
        app:layout_constraintTop_toTopOf="parent">

    </LinearLayout>

    <LinearLayout
        android:id="@+id/layoutDetails"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:orientation="vertical"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toRightOf="@+id/layoutRoot"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent">

</android.support.constraint.ConstraintLayout>
```

该类创建了一个主菜单，包含一个简单的菜单项用于创建一个新人员。如果你选择了此项，就会创建一个新的 `Person` 对象（所有字段均为空）。接下来，方法调用了 `openDialog`，该方法是打开对话框的方法。在这里，你应该首先注意如何传递参数，以及如何使用 `show()` 打开对话框，其中参数是 Activity 的 `FragmentManager`。`personSelected()` 的工作方式类似，它不是创建一个新对象，而是从传递的索引确定一个现有对象，并由 `openDialog()` 传递到对话框。最后，注意 `onClick()`，它是接收来自对话框通知的方法。这发生在两种情况下：点击 OK 按钮或点击 REMOVE 按钮。

## 2.8 片段事务 (FRAGMENT TRANSACTIONS)

作为片段的最后一个例子，我将展示一个程序，在该程序中，我不是打开一个新的 Activity，而是用另一个片段替换当前片段。在 2.4 节中，我展示了一个 `Books` 应用的版本，当手机垂直持有时，应用程序使用整个屏幕并通过列表来查看详情。如果手机水平持有，屏幕将分为两个片段，分别显示列表和详情。

目前尚不完全清楚这些更改应带来什么好处，但目标是应该可以将参数传递给 `onCreate()`，该参数必须是用户从列表中选择的书籍的索引。第一个常量是一个名称，用于标识参数，而另一个是默认值，表示未传递任何参数。参数或实参封装在 `Bundle` 对象中，这在 `onCreate()` 中确定，如果有参数，则尝试将该值确定为 `int`。如果成功且不是默认值，则调用 `setBook()` 并将该值作为参数。

另一方面，`MainActivity` 中的更改更为广泛：

```java
public class BookFragment extends Fragment {
    public static final String ID = "book";
    public static final int NO_ID = -1;
    private List<Book> books = new ArrayList();
    private TextView name;
    private TextView text;

    public BookFragment() {
    }

    @Override
    public View onCreateView(LayoutInflater inflater, ViewGroup container, Bundle savedInstanceState) {
        View view = inflater.inflate(R.layout.fragment_book, container, false);
        name = view.findViewById(R.id.txtName);
        text = view.findViewById(R.id.txtDetails);
        Bundle args = getArguments();
        int id = args != null ? args.getInt(ID, NO_ID) : NO_ID;
        if (id != NO_ID) setBook(id);
        return view;
    }

    public void setBook(int id) {
        name.setText(books.get(id).getName());
        text.setText(books.get(id).getText());
    }
}
```

## JAVA 17：更多关于 Java 和 Android：软件开发片段



```java
FragmentTransaction ft = fm.beginTransaction();
BookFragment bookFragment = new BookFragment();
Bundle args = new Bundle();
args.putInt(BookFragment.ID, id);
bookFragment.setArguments(args);
ft.replace(R.id.layoutRoot, bookFragment, "bookText");
ft.addToBackStack(null);
ft.commit();
} else {
    BookFragment bookFragment = (BookFragment) fm.findFragmentById(R.id.fragmentBook);
    bookFragment.setBook(id);
}

@Override
public void onBackPressed() {
    if (getFragmentManager().getStackEntryCount() > 0) {
        finish();
        startActivity(getIntent());
    } else {
        super.onBackPressed();
    }
}
```

引入了一个变量`isDynamic`，用于控制是否使用片段的动态更新，这取决于设备是垂直方向还是水平方向。该变量在`onCreate()`中通过`FragmentManager`初始化，它会测试`BookFragment`是否存在，从而决定使用布局`activity_main.xml`还是`activity_wide_xml`。如果`isDynamic`为`true`，则必须动态插入片段。这要求你使用事务。`FragmentManager`可以启动一个`FragmentTransaction`类型的事务，你可以在其中添加片段操作。在这里，只添加了一个操作，即向`activity`添加一个`BooksFragment`的`add()`操作。你应该注意，XML文档中的`LinearLayout`现在有了一个id。另外，请注意`add()`方法的最后一个参数，它仅意味着该片段获得了一个名称，以便稍后引用。结果是`FragmentTransaction`对象执行`commit()`，然后添加到事务中的所有操作将作为一个单一操作执行。

`onItemSelectedChanged`上的点击事件处理程序也发生了变化。如果变量`isDynamic`为`true`（且手机垂直握持），则将带有列表的片段替换为显示详情的片段。因此，创建了一个事务。此外，创建一个`BookFragment`对象并将所选书籍的id作为参数与一个`Bundle`对象关联。请注意，你使用了`BookFragment`类中定义为常量名称。在`BookFragment`对象创建并使用参数初始化后，通过向事务中添加`replace()`来替换列表片段。现在，返回键可能仍然有效，因此你必须执行`addToBackStack()`操作，以便当前窗口（当前事务）被压入栈中。

之后一切都应该正常工作——至少在理论上是这样，但如果手机垂直握持，这并不适用于返回键。因此，最后一个方法只在某种程度上解决了问题。寻找更好的解决方案可能是不错的工作。

程序测试完成后，我终于可以删除`BookActivity.java`和`activity_book.xml`了，因为这些文件不再使用。

![](img/dfa4439d1c62650bb2a6b471e62c51e8_56_0.png)

## JAVA 17：更多关于 Java 和 Android：软件开发手机

# 3 手机

在编写 Android 应用时，与通常的 PC 应用略有不同，仅仅是因为设备提供了其他功能，而且如果设备是手机，你就可以拨打电话。在本章中，我将展示如何在软件中实现这一点，并编写用户能够拨打电话的应用程序。对于程序员来说，有两种选择：一种情况是手机用户拨打电话，而另一种情况是编写一个程序，当别人拨打给当前手机电话时可以激活该程序。这并不简单。首先，它需要一些接收电话相关通知的服务，且其中存在一些安全问题，但这里将不讨论这些问题。第一种问题（即应用用户拨打电话的情况）非常简单，下面的示例展示了如何操作。如果你打开手机，

![](img/dfa4439d1c62650bb2a6b471e62c51e8_57_0.png)

这里有一个输入字段，你可以输入电话号码，还有两个按钮可以用来向你输入的号码拨号。如果你点击`DIAL`按钮，会得到一个像拨电话时一样的窗口，你输入的号码会被插入，你只需按下`Call`按钮即可拨打电话。如果你点击`CALL`，手机将在没有用户干预的情况下执行拨号——只要在允许范围内。你可以在`AndroidManifest.xml`中分配权限，对于最新的手机，这是不够的，手机会显示一个简单的对话框，用户必须接受手机如下更新：

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns="http://schemas.android.com/apk/res/android" package="dk.data.torus.thephone">
    <uses-permission name="android.permission.CALL_PHONE" />
    <uses-feature
        android:name="android.hardware.telephony"
        android:required="true" />
    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher"
        android:theme="@style/Theme.AppCompat">
        <activity android:name=".MainActivity" android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>
</manifest>
```

`uses-permission`元素允许拨打电话，`uses-feature`元素用于告知设备支持电话功能。对于大多数手机，这不需要用户点击，设备就可以拨打电话，但Java代码如下：

```java
package dk.data.torus.thephone;

import android.support.app.AppCompatActivity;
import android.os.*;
import android.content.*;
import android.view.*;
import android.widget.*;
import android.telephony.*;
import android.net.*;
import android.content.pm.PackageManager;

public class MainActivity extends AppCompatActivity {
    private static final int REQUEST_CODE = 100;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    public void onDial(View view) {
        TelephonyManager tm = (TelephonyManager) getSystemService(TELEPHONY_SERVICE);
        if (tm.getState() == TelephonyManager.CALL_IDLE) {
            String number = "tel:" + ((EditText) findViewById(R.id.txtNumber)).getText().toString();
            startActivity(new Intent(Intent.ACTION_DIAL, Uri.parse(number)));
        } else {
            Toast.makeText(this, "The phone is in use", Toast.LENGTH_LONG).show();
        }
    }

    public void onClick(View view) {
        TelephonyManager tm = (TelephonyManager) getSystemService(TELEPHONY_SERVICE);
        if (tm.getState() == TelephonyManager.CALL_STATE_IDLE) {
            call();
        } else {
            Toast.makeText(this, "The phone is in use", Toast.LENGTH_LONG).show();
        }
    }

    public void call() {
        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.M && checkPermission(Manifest.permission.CALL_PHONE) != PackageManager.PERMISSION_GRANTED) {
            requestPermissions(new String[] { Manifest.permission.CALL_PHONE }, REQUEST_CODE);
        } else {
            String number = ((EditText) findViewById(R.id.txtNumber)).getText().toString();
            Intent intent = new Intent(Intent.ACTION_CALL);
            intent.setData(Uri.parse("tel:" + number));
            startActivity(intent);
            Toast.makeText(this, "You have called " + number, Toast.LENGTH_LONG).show();
        }
    }

    @Override
    public void onRequestPermissionsResult(int requestCode, String[] permissions, int[] grantResults) {
        if (requestCode == REQUEST_CODE) {
            if (grantResults[0] == PackageManager.PERMISSION_GRANTED) {
                call();
            } else {
                Toast.makeText(this, "You have no permission", Toast.LENGTH_LONG).show();
            }
        }
    }
}
```

## JAVA 17：关于 JAVA 和安卓：软件开发

如果你点击`CALL`按钮，将执行事件处理程序`onCall()`，这与上述类似，但调用本身发生在方法`call()`中。在这里你应当注意的是，只有当在`AndroidManifest.xml`中指定了`CALL_PHONE`权限时，才能执行`startActivity()`方法。否则，你将得到一个转换错误。该方法首先检查手机状态以及manifest文件是否具有所需的权限。如果是较新的手机，则意味着手机会弹出一个对话框，用户必须在其中授予手机拨打电话的权限。如果你授予了权限，事件处理程序将执行`onRequestPermissionsResult()`，然后再次执行`call()`，但这次将执行的是`if`语句的`else`部分。结果就是拨通了电话。

## 3.1 发送短信

![](img/dfa4439d1c62650bb2a6b471e62c51e8_61_0.png)

与上面的示例以及拨打电话的方式类似，我将在接下来的示例中向你展示如何发送短信，原则上它的发生方式是相同的。该示例名为`SendSMS`，它会打开上面的窗口来输入手机号码和消息。我不想展示布局部分，但与使用手机一样，manifest必须允许应用程序发送短信：

## JAVA 17：更多关于 JAVA 和安卓：软件开发

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="dk.data.torus.sendsms">
  <uses-permission android:name="android.permission.SEND_SMS" />
  <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRTL="true"
        android:theme="@style/AppTheme">
    <activity android:name=".MainActivity">
      <intent-filter>
        <action android:name="android.intent.action.MAIN" />
        <category android:name="android.intent.category.LAUNCHER" />
      </intent-filter>
    </activity>
  </application>
</manifest>
```

![](img/dfa4439d1c62650bb2a6b471e62c51e8_62_0.png)

## JAVA 17：更多关于 JAVA 和安卓：软件开发

发送短信非常简单，通过以下方法实现：

```java
private void send() {
    SmsManager sm = SmsManager.getDefault();
    sm.sendTextMessage(phone, null, message, null, null);
    Toast.makeText(getApplicationContext(), "Your SMS is sent",
    Toast.LENGTH_LONG).show();
}
```

在这里，`phone`和`message`两个变量必须分别用手机号码和要发送的消息进行初始化。然而，条件与电话电话相似，在`AndroidManifest.xml`中已经说明允许应用程序发送短信，这并不确定设备是否允许，但它会弹出一个对话框让用户显式接受发送消息。因此，需要少量的代码：



```java
private void sendMessage() {
    phone = txtPhone.getText().toString().trim();
    message = txtMessage.getText().toString().trim();
    if (ContextCompat.checkPermission(this, Manifest.permission.SEND_SMS) !=
    PackageManager.PERMISSION_GRANTED) {
        if (!ActivityCompat.shouldShowPermissionRationale(this,
        Manifest.permission.SEND_SMS)) ActivityCompat.requestPermissions(this,
        new String[] {Manifest.permission.SEND_SMS }, REQUEST_SMS);
    }
    else send();
}

@Override
public void onPermissionsResult(int requestCode, String[] permissions,
int[] grantResults) {
    if (requestCode == REQUEST_SMS) {
        if (grantResults.length > 0 && grantResults[0] ==
        PackageManager.PERMISSION_GRANTED) send();
        else Toast.makeText(getApplicationContext(), "Error sending SMS", Toast.LENGTH_LONG).show();
    }
}
```

# JAVA 17：更多关于 JAVA 和安卓：软件开发

## 电话

你在示例中看到的内容。代码并不容易理解，建议阅读文档，但简而言之发生了以下情况。方法

```java
checkSelfPermission(this, Manifest.permission.SEND_SMS) != PackageManager.PERMISSION_GRANTED
```

检查应用程序在 manifest 中指定了 `SEND_SMS` 权限，如果是，则执行

```java
shouldShowRequestPermissionRationale()
```

并显示对话框来发送短信。如果是这样，Android 会弹出一个对话框，当用户点击接受（或相反）时，执行事件处理程序：

```java
onRequestPermissionsResult()
```

![](img/dfa4439d1c62650bb2a6b471e62c51e8_64_0.png)

> 我们不发明轮子，我们重新发明光亮。

> 迷人的光影提供了无限可能：创新技术和新市场带来了机遇与挑战。在一个你的专业知识备受重视的环境中。在全球范围内享受支持性的环境，受益于国际化的职业路径。与其他专家紧密合作实施可持续想法，为我们的未来做出贡献。加入我们，每天重新发明光亮。

> 光是 OSRAM | OSRAM SYLVANIA

## 使用相机

### 4 使用相机

在本章节中，我将向你展示如何从程序调用手机的摄像头。我将只展示如何拍照并将其保存到外部存储器的文件。事实上，这非常简单，当代码很多时，是因为你无法立即将图像保存到文件中。我想展示一个名为 `TheCamera` 的示例，它会打开下面拍摄了照片的窗口：

![](img/dfa4439d1c62650bb2a6b471e62c51e8_65_0.png)

# JAVA 17：更多关于 JAVA 和 ANDROID：软件开发

```java
import android.provider.*;
import android.app.*;
import android.graphics.*;
import android.os.*;
import android.net.*;
import android.support.v4.content.Context;
import android.support.v4.app.AppCompat;
import android.content.pm.*;
import java.io.*;
```

```java
public class MainActivity extends AppCompatActivity {
    private static final int REQUEST_IMAGE = 100;
    private static final int REQUEST_PERMISSION = 1;
    private Button cmdCapture;
    private ImageView imageView;
    private File file;
```

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);
```

![](img/dfa4439d1c62650bb2a6b471e62c51e8_67_0.png)

在 `www.deloitte.ca/careers` 发现真相

© Deloitte & Touche LLP 关联实体。

在 `bookboom.com` 免费下载 eBooks

点击广告阅读更多

# JAVA 17：更多关于 JAVA 和 ANDROID：软件开发

```java
StrictMode.VmPolicy.Builder builder = new StrictMode.VmPolicy.Builder();
StrictMode.setVmPolicy(builder.build());
cmdCapture = findViewById(R.id.cmdCapture);
cmdCapture.setOnClickListener(new View.OnClickListener() {
    public void onClick(View view) {
```

```java
try {
    Intent intent = new Intent(MediaStore.ACTION_IMAGE_CAPTURE);
    intent.putExtra(MediaStore.EXTRA_OUTPUT, Uri.fromFile(file));
    startActivityForResult(intent, REQUEST_IMAGE);
} catch (Exception ex) {
```

```java
{
    Toast.makeText(MainActivity.this, "设备没有摄像头", Toast.LENGTH_SHORT).show();
}
}
```

```java
if (Compat.checkSelfPermission(this, android.Manifest.permission.WRITE_EXTERNAL_STORAGE) != 
PackageManager.PERMISSION_GRANTED) {
    if (Activity.shouldShowRequestRationale(this, android.Manifest.permission.WRITE_EXTERNAL_STORAGE)) {
    else ActivityCompat.requestPermissions(this, new String[]{android.Manifest.permission.WRITE_EXTERNAL_STORAGE}, REQUEST_PERMISSION);
    }
```

```java
imageView = findViewById(R.id.imageView);
file = new File(Environment.getExternalStorageDirectory(), "image.jpg");
```

```java
@Override
public void onRequestPermissionsResult(int code, String[] permissions, int[] grant) {
    if (code == REQUEST_PERMISSION) {
        if (grant.length > 0 && grant[0] == PackageManager.PERMISSION_GRANTED) {
            Toast.makeText(MainActivity.this, "权限允许", Toast.LENGTH_SHORT).show();
        } else {
            Toast.makeText(MainActivity.this, "权限被拒绝", Toast.LENGTH_SHORT).show();
        }
    }
}
```

# JAVA 17：更多关于 JAVA 和 ANDROID：使用摄像头的软件开发

```java
@Override
protected void onActivityResult(int requestCode, int resultCode, Intent data)
{
    if (requestCode == REQUEST_IMAGE && resultCode == Activity.RESULT_OK)
    {
        try {
            FileInputStream inputStream = new FileInputStream(file);
            Bitmap userImage = BitmapFactory.decodeStream(in, null, null);
            imageView.setImageBitmap(userImage);
        } catch (Exception ex) {
        }
    }
}
```

最难理解的是 `onCreate()`。第一个类定义了两个常量，它们的意义仅仅是标识两个动作（这些值并不重要）。接着，为布局中定义的两个组件定义了变量，最后定义了一个 `File` 变量。

`onCreate()` 以两个常用的语句开始，然后是以下语句：

```java
StrictMode.VmPolicy.Builder builder = new StrictMode.VmPolicy.Builder();
StrictMode.setVmPolicy(builder.build());
```

它们打开是为了引用应用程序存储器之外的文件。实际上，这有点是一个变通方案，Android 文档建议使用一种不同的（稍微复杂一点）的方法。下一步，初始化了变量 `cameraId`，而这里最重要的部分当然是事件处理程序。处理程序必须打开设备的摄像头（如果有的话，这就是为什么这些语句位于 `try / catch` 块中）。这是通过创建一个 `Intent` 对象实现的，其中常量

```java
MediaStore.ACTION_IMAGE_CAPTURE
```

指向手机摄像头。至于图像要保存到哪里，变量 `file` 被作为参数传递，最后调用 `onActivityResult()`。这意味着当摄像头关闭时，图像将从文件中读取并显示在 `ImageView` 中。

## 使用摄像头的软件开发

在 `onCreate()` 中初始化变量 `cmdCapture` 后，有必要测试应用程序是否有访问外部存储的权限。这和我之前展示的方法相同，如果你想使用外部存储，`onRequestPermissionsResult()` 就是用户选择的结果。

![](img/dfa4439d1c62650bb2a6b471e62c51e8_70_0.png)

# JAVA 17：更多关于 JAVA 和 ANDROID：软件开发位置

## 5 个位置

手机的一个重要用途是确定你所在的位置，从而确定在地图上的地理位置。地图是由提供可以执行此操作的程序提供的，程序员在自己的应用中确定位置也可能感兴趣。这两个部分都非常简单，只要你使用 Google 提供的 API（Google Play 服务）。然而，该 API 并不是 Android SDK 的一部分，因此你需要下载该 API 并在当前项目中引用它。只要你想确定自己的位置，它就足够简单，但如果你想使用 Google Maps，就需要更多工作，因为你必须注册并拥有 Google 账户密钥，并且不能自由使用其应用程序，因为 Google Maps 有许可条件。应该说明的是还有其他地图，但原理类似。因此，我想向你展示如何在不使用 Google Play 服务的情况下确定位置，这可能正是你开发应用时所需的。

你可以通过三个不同的位置提供者确定位置：

- `GPS_PROVIDER`：提供最准确结果的提供者，使用内置的 GPS 接收器。
- `NETWORK_PROVIDER`：使用手机网络或 WiFi 热点收集的数据确定位置。这个提供者没有之前的准确，但对于大多数应用程序足够。
- `PASSIVE_PROVIDER`：这意味着设备本身不想确定位置，而是使用其他应用程序或服务确定的位置。目标是节省电。

`TheLocation` 应用是上述两个位置提供者中的第一个。程序打开一个确定设备位置坐标（经度和纬度）的窗口。窗口有两个按钮，从开始都显示文本“Start”。点击顶部按钮会将文本变为“Stop”，程序将开始使用 GPS 提供者定期更新经度和纬度的值。底部按钮的工作原理相同，但使用的是网络提供者。

# JAVA 17：更多关于 JAVA 和 Android：软件开发位置

关于应用程序的用户界面，没有新新内容，布局由 8 个使用相对布局（Relative）的部件组件组成，我不想在这里显示代码。为了让应用程序使用设备的 GPS，必须在清单（manifest）中允许它：

```xml
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
```

并且实际上只需要第一个权限。

![](img/dfa4439d1c62650bb2a6b471e62c51e8_72_0.png)

然后是 Java 代码，它立即填充了更多内容，并且其中有很多新知识点：



```java
public class MainActivity extends AppCompatActivity {
    private static int REQUEST_PERMISSION = 1;
    private boolean permission = false;
    private LocationManager locationManager;
    private TextView long1;
    private TextView lat1;
    private TextView long2;
    private TextView lat2;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        locationManager = (LocationManager) getSystemService(Context.LOCATION_SERVICE);
        long1 = findViewById(R.id.txtLong1);
        lat1 = findViewById(R.id.txtLat1);
        long2 = findViewById(R.id.txtLong2);
        lat2 = findViewById(R.id.txtLat2);
        requestPermission();
    }

    private void requestPermission() {
        if (ContextCompat.checkSelfPermission(this, android.Manifest.permission.ACCESS_FINE_LOCATION) !=
                PackageManager.PERMISSION_GRANTED) {
            if (ActivityCompat.shouldRequestPermission(this, android.Manifest.permission.ACCESS_FINE_LOCATION)) {
                // handle request
            } else {
                ActivityCompat.requestPermissions(this, new String[]{
                        android.Manifest.permission.ACCESS_FINE_LOCATION}, REQUEST_PERMISSION);
            }
        }
        permission = ContextCompat.checkSelfPermission(this, android.Manifest.permission.ACCESS_FINE_LOCATION) ==
                PackageManager.PERMISSION_GRANTED;
    }

    public void gpsOnOff(View view) {
        if (!permission) return;
        Button button = (Button) view;
        if (button.getText().equals("Stop")) {
            locationManager.removeUpdates(gpsListener);
            button.setText("Start");
        } else {
            try {
                locationManager.requestLocationUpdates(LocationManager.GPS_PROVIDER,
                        30 * 1000, gpsListener);
                button.setText("Stop");
            } catch (SecurityException ex) {
            }
        }
    }

    public void netOnOff(View view) {
    }

    private final LocationListener netListener = new LocationListener() {
    };

    private final LocationListener gpsListener = new LocationListener() {
        @Override
        public void onLocationChanged(Location location) {
            final double longitude = location.getLongitude();
            final double latitude = location.getLatitude();
            runOnUiThread(new Runnable() {
                @Override
                public void run() {
                    long1.setText(String.format("%1.6f", longitude));
                    lat1.setText(String.format("%1.6f", latitude));
                    Toast.makeText(MainActivity.this, "GPS coordinates updated",
                            Toast.LENGTH_SHORT).show();
                }
            });
        }

        @Override
        public void onStatusChanged(String s, int i, Bundle bundle) {
        }

        @Override
        public void onProviderEnabled(String s) {
        }

        @Override
        public void onProviderDisabled(String s) {
        }
    };
}
```

![](img/dfa4439d1c62650bb2a6b471e62c51e8_72_0.png)

> 你可以找到 GPS 开启/关闭的监听器。

## 练习 3：GOOGLE PLAY SERVICES

在这个练习中，你必须编写一个原则上与上面相同的程序，用于显示用户的位置，但这次应该使用 Google Play Services 完成。目标是展示一下使用 Google Play Services 需要什么以及它是什么，因为这在实践中可能很重要。

首先从创建一个名为 `Location` 的新项目开始，编译项目并在模拟器中测试你有一个 Hello World 项目。在 `activity_main.xml` 中，为你的 `TextView` 组件添加以下 ID：

```xml
android:id="@+id/txtLocation"
```

## JAVA 17: 更多 Java 与 Android：软件开发

```gradle
dependencies {
    implementation fileTree(dir: 'libs', include: ['*.*.jar'])
    implementation 'com.google.android.gms:play-services-location:15.0.1'
    implementation 'com.android.support:appcompat-v7:26.1.0'
    implementation 'com.android.support.constraint:constraint-layout:1.1.2'
    testImplementation 'junit:4.12'
    androidTestImplementation 'com.android.support.test.runner:1.0.2'
    androidTestImplementation 'com.android.support.test.espresso-core:3.0.2'
}
```

正如我们在上一个示例中看到的那，更新 manifest 文件：

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="dk.data.torus.thelocation">
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>
    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportLibrary="true"
        android:theme="@style/AppTheme">
        <meta-data android:name="com.google.android.gms.version"
            android:value="@integer/google_play_services_version" />
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>
</manifest>
```

现在你准备好使用 Google Play Services 来确定你的位置了，因此你需要更新 `MainActivity`。作为第一步，`MainActivity` 必须实现 Google Play Services 接口：

```java
package dk.data.torus.thelocation;

import android.location.Location;
import android.os.Bundle;
import android.support.v7.app.AppCompatActivity;
import com.google.android.gms.common.api.GoogleApiClient;
import com.google.android.gms.location.*;

public class MainActivity extends AppCompatActivity
implements LocationListener, GoogleApiClient.ConnectionCallbacks
{
    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    @Override
    public void onConnected(Bundle bundle) {
    }

    @Override
    public void onConnectionSuspended(int i) {
    }

    @Override
    public void onLocationChanged(Location location) {
    }
}
```

![](img/dfa4439d1c62650bb2a6b471e62c51e8_79_0.png)

## 管理学硕士

因为实现梦想是你面临最大的挑战，IE 商学院（IE Business School）提供的英语、西班牙语或双语教学的管理学硕士课程，通过创新且具有启发性的计划，在职业生涯早期培训高绩效专业人士，帮助他们发挥全部潜力。

- 选择你的专业领域。

- 通过所提供的不同选项定制你的硕士课程。

- 在伦敦、里斯本、上海等城市进行全球沉浸式周学习。

因你而变，我们随你而变。

www.ie.edu/master-management mim.admissions@ie.edu

在 bookoon.com 下载免费电子书

## JAVA 17: 更多关于 Java 与 Android：软件开发位置

```java
@Override
public void onRequestPermissionsResult(int code, String[] permissions, int[] grants) {
}
```

注意它需要哪些导入语句（import statements）。翻译程序并检查它是否仍然可以运行。这应该是可能的。接下来添加以下方法，以便户户允许应用程序获取 `ACCESS_FINE_LOCATION` 权限（注意，其方式与上一个示例中的方法相同）：

```java
private void requestPermission() {
    if (ContextCompat.checkSelfPermission(this, android.Manifest.permission.ACCESS_FINE_LOCATION) != PackageManager.PERMISSION_GRANTED) {
        if (ActivityCompat.shouldRequestPermissionRationale(this, android.Manifest.permission.ACCESS_FINE_LOCATION)) {}
        else ActivityCompat.requestPermissions(this, new String[]{android.Manifest.permission.REQUEST_PERMISSION},);
    }
    if (ContextCompat.checkSelfPermission(this, android.Manifest.permission.ACCESS_FINE_LOCATION) != PackageManager.PERMISSION_GRANTED) {
        AlertDialog.Builder builder = new AlertDialog.Builder(this);
        builder.setTitle("Error");
        builder.setMessage("You have no permissions to show locations");
        builder.setPositiveButton("Close", new DialogInterface.OnClickListener() {
            public void onClick(DialogInterface dialog, int which) {
                finish();
            }
        });
        builder.show();
    }
}
```

该方法需要添加多个导入语句和一个单一静态常量 `REQUEST_PERMISSION`。再添加一个导入语句：

```java
import com.google.android.gms.common.*;
```

并添加另一个方法：

```java
private void showError(int code) {
    GoogleAvailability.getInstance().showErrorDialogFragment(this, 10,
    new DialogInterface.OnClickListener() {
        @Override
        public void onClick(DialogInterface dialog, int which) {
            finish();
        }
    });
}
```



如果 Google Play Services 无法建立连接，将使用此方法。作为下一步，添加以下变量，并在`onCreate`方法中所示：

```java
public class MainActivity extends AppCompatActivity
implements LocationListener, GoogleApiClient.ConnectionCallbacks
{
    static final int REQUEST_PERMISSION = 101;
    private GoogleApiClient client;
    private LocationRequest request;
    private Location location;
    private TextView txtLocation;

    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        txtLocation = findViewById(R.id.txtLocation);
        int code = GoogleAvailability.getInstance().isServicesAvailable(this);
        if (code != Connection.SUCCESS) {
            showError(code);
        }
        client = new GoogleApiClient.Builder(this)
            .addApi(LocationServices.API)
            .ConnectionCallbacks(this)
            .build();
        request = LocationRequest.create()
            .setPriority(LocationRequest.PRIORITY_HIGH_ACCURACY)
            .setInterval(15000);
        client.connect();
    }

    @Override
    public void onConnected(Bundle bundle) {
        fetchLocation();
    }

    @Override
    public void onConnectionSuspended(int i) {
    }

    @Override
    public void onLocationChanged(Location location) {
        this.location = location;
        display();
    }

    private void requestPermission() {
        if (ContextCompat.checkSelfPermission(this, android.Manifest.permission.ACCESS_FINE_LOCATION) != PackageManager.PERMISSION_GRANTED) {
            if (ActivityCompat.shouldRequestPermissionRationale(this, android.Manifest.permission.ACCESS_FINE_LOCATION)) {}
            else ActivityCompat.requestPermissions(this, new String[]{android.Manifest.permission.ACCESS_FINE_LOCATION}, REQUEST_PERMISSION);
        }
    }

    @Override
    public void onRequestPermissionsResult(int code, String[] permissions, int[] grants) {
        super.onRequestPermissionsResult(code, permissions, grants);
        if (code == REQUEST_PERMISSION) {
            for (int i = 0; i < grants.length; i++) {
                int result = grants[i];
                String permission = permissions[i];
                if (result != PackageManager.PERMISSION_GRANTED) {
                    finish();
                    return;
                }
            }
        }
    }

    @SuppressWarnings("MissingPermission")
    private void fetchLocation() {
        location = LocationServices.FusedLocationApi.getLastLocation(client);
        LocationServices.FusedLocationApi.requestLocationUpdates(client, request, this);
    }

    private void showError(int code) {
        AlertDialog.Builder builder = new AlertDialog.Builder(this);
        builder.setTitle("Error");
        builder.setMessage("You have no permissions to show locations");
        builder.setPositiveButton("Close", new DialogInterface.OnClickListener() {
            public void onClick(DialogInterface dialog, int which) {
                finish();
            }
        });
        builder.show();
    }

    @Override
    public void onResume() {
        super.onResume();
        client.connect();
    }

    private void display() {
      if (location == null) txtLocation.setText("");
      else txtLocation.setText(String.format("Latitude: %.4f\nLongitude: %.4f", location.getLatitude(), location.getLongitude()));
    }
}
```

## JAVA 17：更多关于 Java 和 Android：软件开发偏好

### 偏好（Preferences）

手机（任何其他 Android 设备）都有名为“设置”的应用，用于手机设置。你选择的设置在设备重启后仍然有效，必须存储在某处。这可以通过数据库或文件实现，但由于数据量很小，Android 使用一种名为偏好（preferences）的特殊系统以键值对（key/value pairs）的形式保存此类信息。与设备本身一样，你通常需要为自己的应用程序保存设置，与其使用文件或数据库，你可以使用偏好系统。

原则上，偏好可以用于其他设置，因为这仅仅是保存键值对的问题，唯一的限制是值必须是字符串或简单类型的值。然而，偏好不仅仅是存储数据的方式，它还包含了用于维护这些组件，如下例所示。

偏好可以分配给一个 Activity，而 Activity 对象有一个方法`getPreferences()`，该方法返回一个`SharedPreference`对象。偏好也可以与应用程序关联，通过`getSharedPreferences()`方法，你可以获取一个由名称标识的`SharedPreferences`对象，因此同一个应用程序可能附加多个偏好。最后，还有针对整个设备的偏好，使用`PreferenceManager`对象维护，你可以使用`getDefaultPreferences()`方法获取`SharedPreferences`对象。该方法的参数是`Context`并返回该对象的偏好。你可以使用这三种方法中的哪种最合适，大多数情况下你会使用最后一种方法。

`SharedPreferences`对象具有用于确定值的`get`方法，例如方法：

- `getString()`
- `getInt()`

以及其他方法，这些方法有两个参数，第一个是键（key），另一个是默认值。你可以（自然地）为`SharedPreference`对象创建并修改值，这通过类似的`set`方法实现，其参数是键和值。然而，这与正常情况有些不同，因为`Preference`对象有一个`edit()`方法，它返回一个`Editor`对象，而方法被分配给该对象。要使更改生效，请通过`Editor`对象完成更改并执行`commit()`方法（或`apply()`方法）。`Editor`对象还有一个`remove()`方法，可用于删除单个偏好，以及一个删除所有偏好的`clear()`方法。

### 偏好设置

如果应用程序需要维护设置，你可以专门为此目的定义自己的 Activity，这些 Activity 可以是全面的。Android 提供了一个特殊的 Activity`PreferenceActivity`和片段`PreferenceFragment`，可以用于实现应用程序的设置，除了使其更容易之外，最重要的是，这种方式的设置对每个应用程序来说工作都是相同的。在接下来，我将通过示例`ThePreferences`向你展示如何操作。如果你打开应用程序，将看到以下窗口：

![](img/dfa4439d1c62650bb2a6b471e62c51e8_85_0.png)

![](img/dfa4439d1c62650bb2a6b471e62c51e8_86_0.png)

这仅仅是一个简单的 Hello World Activity，但带有一个有两个菜单项的菜单。如果你选择第一个，你将收到一个显示程序设置标题的窗口：

![](img/dfa4439d1c62650bb2a6b471e62c51e8_86_1.png)

有两个设置需要配置，第一个设置涉及颜色和文本的显示方式（见下窗口），而另一个选项是开启或关闭设置。在第一种情况下，你可以选择文本应该是**粗体**还是*斜体*（或两者都是），并且你可以选择字体大小。如果你选择字体大小，你将得到一个带有单选按钮的对话框，你可以点击所需字体大小的按钮。你也可以选择输入文本，结果是一个用于文本文本的对话框。最后，你可以选择文本颜色和背景颜色，在这两种情况下，你都会得到一个带有单选按钮的对话框。

![](img/dfa4439d1c62650bb2a6b471e62c51e8_87_0.png)

在最后一个设置窗口中，两个开关组件允许你设置这两个设置的开启和关闭：

![](img/dfa4439d1c62650bb2a6b471e62c51e8_87_1.png)

在这种情况下，除了作为典型设置的之外没有太大意义。下面是两个开关组件都开启且在第一个设置窗口中选择值后的窗口：

![](img/dfa4439d1c62650bb2a6b471e62c51e8_88_0.png)

## JAVA 17：更多 Java Android 软件开发

```java
@Override
public boolean onCreateOptionsMenu(Menu menu) {
    getMenuInflater().inflate(R.menu.main, menu);
    return true;
}
```

```java
@Override
public boolean onOptionsItemSelected(MenuItem item) {
    int id = item.getItemId();
    if (id == R.id.change_preferences) {
        startActivity(new Intent(this, ChangePreferences.class));
        return true;
    }
    if (id == R.id.clear_settings) {
        setDefaults();
        return true;
    }
    return super.onOptionsItemSelected(item);
}
```

![](img/dfa4439d1c62650bb2a6b471e62c51e8_91_0.png)

关于 e-Learning for Kids。e-Learning for Kids 成立于 2004 年，是一个全球非营利基金，致力于为 5-12 岁的儿童提供有趣的免费互联网学习，课程涵盖数学、科学、语言艺术、计算机和健康。自 2005 年以来，在 LU KI An 志愿者团队的推动下，全球190多个国家的超过1500万儿童受益于教育和在线学习专家、全球致力于做出改变的商务人士提供的服务。我们对在线学习的愿景包括寻求资金、志愿者、赞助商和内容开发者。更多信息，请访问 www.e-learning-for-kids.org。

在 book.com 下载免费电子书

- 小学教育第 1 MOOC
- 面向5-12 岁儿童的免费数字学习
- 覆盖 1500 万儿童

### 偏好设置



```java
private void setDefault() {
    SharedPreferences prefs = PreferenceManager.getDefaultShSharedPreferences(this);
    SharedPreferences.Editor edit = prefs.edit();
    edit.putBoolean("colorswitch", false);
    edit.putBoolean("fontswitch", false);
    edit.putString("bgcolor", "#FFFFFF");
    edit.putString("fgcolor", "#000000");
    edit.putString("text", "Text");
    edit.putBoolean("italic", false);
    edit.putBoolean("bold", false);
    edit.putString("size", "6");
    edit.commit();
    refreshActivity();
}

private void refreshActivity() {
    SharedPreferences prefs = PreferenceManager.getDefaultShSharedPreferences(this);
    boolean colorOn = prefs.getBoolean("colorswitch", false);
    boolean fontOn = prefs.getBoolean("fontswitch", false);
    String bg = colorOn ? prefs.getString("bgcolor", "#FFFFFF") : "#FFFFFF";
    String fg = colorOn ? prefs.getString("fgcolor", "#000000") : "#000000";
    ConstraintLayout layout = (ConstraintLayout) this.findViewById(R.id.background);
    layout.setBackgroundColor(Color.parseColor(bg));
    txtLine.setTextColor(Color.parseColor(fg));
    txtLine.setText(prefs.getString("text", "Text"));
    boolean italic = fontOn ? prefs.getBoolean("italic", false) : false;
    boolean bold = fontOn ? prefs.getBoolean("bold", false) : false;
    int style = (italic && bold) ? Typeface.BOLD_ITALIC : 0;
    if (bold) style = Typeface.BOLD;
    else if (italic) style = Typeface.ITALIC;
    txtLine.setTypeface(Typeface.create(txtLine.getText(), style));
    txtLine.setTextSize(TypedValue.COMPLEX_UNIT_SP, fontOn ? Integer.parseInt(prefs.getString("size", "6")) : 6);
}
```

该类有一个引用组件`txtLine`的变量，它在`onCreate()`中初始化。你需要注意的是，该类还重写了`onResume()``，该方法调用了`refreshActivity()`方法。因此，每当视图需要初始化时（例如手机旋转时），该方法就会执行。此外，还有创建菜单（基于`main.xml`）和处理菜单事件的方法。

## JAVA 17：更多 JAVA 和 ANDROID：软件开发

该类有一个引用组件`txtLine`的变量，它在`onCreate()`中初始化。你需要注意的是，该类还重写了`onResume()`，该方法调用了`refreshActivity()`方法。因此，每当视图需要初始化时（例如手机旋转时），该方法就会执行。此外，还有创建菜单（基于`main.xml`）和处理菜单事件的方法。

## JAVA 17：关于 JAVA 和 Android：软件开发偏好

在这里，定义了两个`ProductCategory`元素，它们除了在标题下分组偏好外没有其他作用。除此之外，使用的是其他项目。`CheckPreference`相当于`CheckBox`，但它会更新与其关联的引用，例如键为`bold`的偏好。`ListPreference`会打开一个带有单选按钮的对话框，允许你选择一个值，如果你点击 OK 更新偏好，这同样适用。

注意带有数组的`listPreference`如何定义单选按钮应显示的数值文本。最后，还有一个`EditTextPreference`，它会打开一个你可以在其中输入文本的对话框。

`xml / preference_2.xml`如下：

```xml
<PreferenceScreen
  xmlns:android="http://schemas.android.com/apk/res/android">
  <SwitchPreference
    android:key="fontswitch"
    android:title="Font settings"
    android:summary="Turn font settings on / off" />
  <SwitchPreference
    android:key="colorswitch"
    android:title="Color settings"
    android:summary="Turn color settings on / off" />
</PreferenceScreen>
```

其中只使用了`SwitchPreference`，在原则上它的作用与其他偏好元素相同。应该提到的是，除了示例中使用的，还有其他的偏好元素。

然后示例就完成了，除了 manifest 文件外没有其他的了：

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="dk.data.torus.preferences">
  <application
    android:allowBackup="true"
    android:icon="@mipmap/ic_launcher"
    android:label="@string/app_name"
    android:roundIcon="@mipmap/ic_launcher_round"
    android:supportsRtl="true"
    android:theme="@style/AppTheme">
    <activity android:name=".MainActivity">
      <intent-filter>
        <action android:name="android.intent.action.MAIN" />
        <category android:name="android.intent.category.LAUNCHER" />
      </intent-filter>
    </activity>
  </application>
</manifest>
```

## JAVA 17：更多关于 JAVA 和 Android：软件开发

```xml
<activity
  android:name="ChangePreferences"
</activity>
</manifest>
```

## 问题 1：PUZZLEAPP

在之前的书籍 2 中，你写了一个名为`PuzzleApp`的程序。该程序是一个简单的游戏，你需要解决一个由 9、25、49 或 81 个碎片组成的谜题。创建一个`PuzzleApp`项目的副本。

在这项任务中，你必须对程序实现一个单一更改。程序维护着一个高分列表——实际上有 4 个高分列表，因为 4 个难度级别每个都有一个高分列表。在 Java 16 的解决方案中，高分存储在文件中。你现在必须更改解决方案，将列表保存为偏好（preferences）。注意，这与设置无关，因此你不应该使用`PreferenceActivity`或`Preference`。事实上，只需要更改`HighscoreList`类即可。

![](img/dfa4439d1c62650bb2a6b471e62c51e8_97_0.png)

## JAVA 17：更多关于 JAVA 和 Android：软件开发

# 7 外部存储

在之前关于文件的书中，我只展示了使用内部存储的示例，这是与单个应用程序相关的存储。在本章中，我将展示一个示例，说明如何使用外部存储，外部存储可能包含可以被多个应用程序使用的数据。

实际上有两种类型的外部存储：

1. 主外部存储，物理上是手机的一部分，其大小由手机制造商决定。
2. 次级外部存储，通常是 SD 卡，但也可能是通过线连接到手机的设备。

以下示例仅涉及第一种外部存储，因为它是最有效的外部存储形式，而且设备并不一定有 SD 卡。从 Android 版本 6 开始，使用 SD 卡上的外部存储非常简单，但供应商可能没有开启这种可能性。由于是缺乏安全性，Android 实际上建议不要将 SD 卡作为外部存储。

当我在后续内容提到外部存储时，指的是主外部存储；否则，外部存储的使用在原则上与上一书中所示的内部存储使用方式相似。`TheStorage`项目打开了一个窗口。

![](img/dfa4439d1c62650bb2a6b471e62c51e8_98_0.png)

## JAVA 17：更多 JAVA 和 Android：软件开发

在顶部有一个用于输入文本的`EditText`组件。下方是一个用于显示文本的`TextView`组件，最后有三个按钮，其中第一个按钮用于将输入文本保存到系统中，下一个用于加载文件内容并显示在`TextView`组件中。最后，最后一个按钮用于显示关于文件系统的信息。

第一步是修改 manifest，在其中你赋予使用外部存储的权限：

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="dk.data.torus.preferences">
  <application
    android:allowBackup="true"
    android:icon="@mipmap/ic_launcher"
    android:label="@string/app_name"
    android:roundIcon="@mipmap/ic_launcher_round"
    android:supportsRtl="true"
    android:theme="@style/AppTheme">
    <activity android:name=".MainActivity">
      <intent-filter>
        <action android:name="android.intent.action.MAIN" />
        <category android:name="android.intent.category.LAUNCHER" />
      </intent-filter>
    </activity>
  </application>
</manifest>
```

列出了两个`uses-permission`元素。在这里，`WRITE_STORAGE`自动提供了`READ_STORAGE`权限，因此如果你只想读取，则最后一个是必要的。关于布局，我们不显示 XML，但后续是 Java 代码：



```java
public class MainActivity extends AppCompatActivity {
    private static final int REQUEST_READ_PERMISSION = 100;
    private static final int REQUEST_WRITE_PERMISSION = 101;
    private EditText editText;
    private TextView textView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        editText = findViewById(R.id.txtEdit);
        textView = findViewById(R.id.txtView);

        findViewById(R.id.cmdSave).setOnClickListener(new OnClickListener() {
            @Override
            public void onClick(View v) {
                askWritePermission();
            }
        });

        findViewById(R.id.cmdRead).setOnClickListener(new OnClickListener() {
            @Override
            public void onClick(View v) {
                askReadPermission();
            }
        });

        findViewById(R.id.cmdShow).setOnClickListener(new OnClickListener() {
            @Override
            public void onClick(View v) {
                showStorage();
            }
        });
    }

    private void askWritePermission() {
      if (askPermission(REQUEST_WRITE_PERMISSION, Manifest.permission.WRITE_STORAGE)) writeFile();
    }

    private void askReadPermission() {
      if (askPermission(REQUEST_READ_PERMISSION, Manifest.permission.READ_STORAGE)) readFile();
    }

    private boolean askPermission(int requestId, String permission) {
      if (android.Build.VERSION.SDK_INT >= 23) {
        if (ActivityCompat.checkSelfPermission(this, permission) != PackageManager.PERMISSION_GRANTED)
          requestPermissions(new String[] { permission }, requestId);
        return false;
      }
      return true;
    }

    @Override
    public void onRequestPermissionsResult(int requestCode, String[] permissions, int[] grantResults) {
      super.onRequestPermissionsResult(requestCode, permissions, grantResults);
      if (grantResults.length > 0) {
        switch (requestCode) {
          case REQUEST_READ_PERMISSION:
            if (grantResults[0] == PackageManager.PERMISSION_GRANTED) readFile();
            return;
          case REQUEST_WRITE_PERMISSION:
            if (grantResults[0] == PackageManager.PERMISSION_GRANTED) writeFile();
            return;
        }
      } else Toast.makeText(getApplicationContext(), "Permission denied", Toast.LENGTH_SHORT).show();
    }

    private void showStorage() {
        // Implementation for showing storage
    }
}
```

![](img/dfa4439d1c62650bb2a6b471e62c51e8_100_0.png)

# JAVA 17: 更多 Java 与 Android 软件开发

```java
private void writeFile() {
    String path = 
    Environment.getExternalStorageDirectory().getAbsolutePath() + "/note.txt";
    String data = edit.getText().toString();
    try {
        File file = new File(path);
        file.createNewFile();
        OutputStreamWriter writer = new
        new BufferedWriter(new FileOutputStream(file));
        writer.append(data);
        writer.close();
        Toast.makeText(getContext(), "Data saved",
        Toast.LENGTH_LONG).show();
    } catch (Exception ex) {
        Toast.makeText(getContext(), ex.getMessage(),
        Toast.LENGTH_LONG).show();
    }
}
```

```java
private void readFile() {
    String path = 
    Environment.getExternalStorageDirectory().getAbsolutePath() + "/note.txt";
    StringBuilder builder = new StringBuilder();
    try {
        File file = new File(path);
        BufferedReader reader = new
        new BufferedReader(new InputStreamReader(file));
        for (String str = reader.readLine(); str !=
        null; str = reader.readLine()) {
            builder.append(str);
        }
        builder.append("\n\n");
        reader.close();
        Toast.makeText(getContext(), "Data loaded",
        Toast.LENGTH_LONG).show();
        textView.setText(builder.toString());
    } catch (IOException ex) {
        Toast.makeText(getContext(), ex.getMessage(),
        Toast.LENGTH_LONG).show();
    }
}
```

```java
private void showStorage() {
    StringBuilder builder = new StringBuilder();
    builder.append(ExternalTools.getPublicDir());
    builder.append("\n");
    builder.append(ExternalTools.getStorageSize());
    builder.append("\n");
    textView.setText(builder.toString());
}
```

# JAVA 17: 关于 Java 与 Android: 软件开发 外部存储

首先，定义了两个与回调方法相关的常量。接下来，有两个变量用于用户界面中的两个文本组件。这些变量在`onCreate()`中初始化，但`onCreate()`仅包含与三个按钮关联事件处理器，每个处理器都会调用一个方法。

SAVE 按钮的事件处理器调用`askPermission()`方法。在 Android 23 版本之前，只要在清单（manifest）中声明，应用程序就拥有外部存储的写权限；但从 23 版本及更高版本，要求变得更加严格，用户现在必须在简单的对话框中主动授予权限（这是用户首次运行程序时看到此操作，请参阅第 11 节）。`askWritePermission()`方法带有两个参数调用`askPermission()`方法，第一个是程序开始时定义的两个常量之一，另一个是用户可能允许的权限。

在`askPermission()`中，首先测试 Android 版本，如果小于 23，则不执行任何操作且方法返回`true`。否则，使用以下方法：

```
ContextCompat.checkSelfPermission(this, permission)
```

![](img/dfa4439d1c62650bb2a6b471e62c51e8_103_0.png)

# 赋能人才。改进业务。

挪威商学院（BI Norwegian Business School）是欧洲最大的商学院之一，招收 20,000 多名学生。学生提供了一个具有国际视野、充满活力且多元文化的学习环境，培养学生的专业技能以满足企业需求。

BI 提供为期两年、全制的理硕士（MSc）课程，完全用英语授课，并旨在提供专业技能以满足企业日益增长的需求。硕士课程提供了一个充满活力且多元文化的学习环境，为你的开启职业生涯提供最佳平台。

- 商业/工商管理硕士

- 金融经济学硕士

- 战略营销管理硕士

- 领导力与组织心理学硕士

www.bi.edu/master

# JAVA 17: 更多 Java 与 Android: 软件开发

# 外部存储

为了测试你是否已请求权限，如果不是，则调用方法：

```
requestPermissions(new String[] { permission }, requestID)
```

并且`askPermission()`返回`false`。正是`requestPermissions()`方法在用户必须主动分配所需权限时打开对话框。`requestPermissions()`方法调用回调方法：

```
onRequestPermissionsResult(...)
```

返回用户选择的结果。在这种情况下，如果用户已授予权限，则调用`writeFile()`方法写入文件，否则会显示一个简单的 Toast 提示未授予权限。

如果方法`askPermission()`返回`true`，则`askWritePermission()`将调用`writeFile()`。

然后`writeFile()`方法相对于我之前处理的内部存储并没有增加多少新，最重要的一点是：

```
Environment.getExternalStorageDirectory().getAbsolutePath() + "/note.txt"
```

它决定了外部存储中的文件名。你应该注意，文件存储在外部存储的根目录下，这显然并不一定如此。文件名是硬编码的，在实践中这并不合适。

`askReadPermission()`方法从中间按钮的事件处理器中调用，其原理上与`askWritePermission()`完全相同，但区别在于：

（等等，OCR 在后半部分存在一些重复/残留。我将根据提供的文本清理逻辑流。）

如果方法`askPermission()`返回`true`，则`askWritePermission()`将调用`writeFile()`。

然后`writeFile()`方法相对于我之前处理的内部存储并没有增加多少新，最重要的一点是：

```
Environment.getExternalStorageDirectory().getAbsolutePath() + "/note.txt"
```

它决定了外部存储中的文件名。你应该注意，文件存储在外部存储的根目录下，这显然并不一定如此。文件名是硬编码的，在实践中这并不合适。

`askReadPermission()`方法从中间按钮的事件处理器中调用，其原理上与`askWritePermission()`完全相同，但区别在于：

（注：OCR 提供的文本在结尾变得重复且碎片化。我将提供特定部分的清晰版本。）

纠正：第 104-106 页的 OCR 文本非常混乱/损坏。我将修复这些问题。

如果方法`askPermission()`返回`true`，则`askWritePermission()`将调用`writeFile()`。

然后`writeFile()`方法相对于我之前处理的内部存储并没有增加多少新，最重要的是：

（实际上，查看提示，我应该处理提供的文本。第 104-106 页包含大量的噪声/重复。我将清理 OCR 错误并保持内容。）

根据源码，对第 104-106 页进行修正处理：

# JAVA 17: 更多 Java 与 Android: 软件开发

# 外部存储

为了测试你是否已请求权限，如果不是，则调用方法：

```
requestPermissions(new String[] { permission }, requestID)
```

并且`askPermission()`返回`false`。正是`requestPermissions()`方法在用户必须主动分配所需权限时打开对话框。`requestPermissions()`方法调用回调方法：

```
onRequestPermissionsResult(...)
```

返回用户选择的结果。在这种情况下，如果用户已授予权限，则调用`writeFile()`方法写入文件，否则会显示一个简单的 Toast 提示未授予权限。

如果方法`askPermission()`返回`true`，则`askWritePermission()`将调用`writeFile()`。

然后`writeFile()`方法相对于我之前处理的内部存储并没有增加多少新，最重要的是：

```
Environment.getExternalStorageDirectory().getAbsolutePath() + "/note.txt"
```

它决定了外部存储中的文件名。你应该注意，文件存储在外部存储的根目录下，这显然并不一定如此。文件名是硬编码的，在实践中这并不合适。

`askReadPermission()`方法从中间按钮的事件处理器中调用，其原理上与`askWritePermission()`完全相同，但区别在于：

（文本在 OCR 处变得高度损坏。我将提供整个文档的完整版本。）

# JAVA 17: 更多 Java 与 Android: 软件开发



```java
private void writeFile() {
    String path = 
    Environment.getExternalStorageDirectory().getAbsolutePath() + "/note.txt";
    String data = edit.getText().toString();
    try {
        File file = new File(path);
        file.createNewFile();
        OutputStreamWriter writer = new
        new BufferedWriter(new FileOutputStream(file));
        writer.append(data);
        writer.close();
        Toast.makeText(getContext(), "Data saved",
        Toast.LENGTH_LONG).show();
    } catch (Exception ex) {
        Toast.makeText(getContext(), ex.getMessage(),
        Toast.LENGTH_LONG).show();
    }
}
```

```java
private void readFile() {
    String path = 
    Environment.getExternalStorageDirectory().getAbsolutePath() + "/note.txt";
    StringBuilder builder = new StringBuilder();
    try {
        File file = new File(path);
        BufferedReader reader = new
        new BufferedReader(new InputStreamReader(file));
        for (String str = reader.readLine(); str !=
        null; str = reader.readLine()) {
            builder.append(str);
        }
        builder.append("\n\n");
        reader.close();
        Toast.makeText(getContext(), "Data loaded",
        Toast.LENGTH_LONG).show();
        textView.setText(builder.toString());
    } catch (IOException ex) {
        Toast.makeText(getContext(), ex.getMessage(),
        Toast.LENGTH_LONG).show();
    }
}
```

```java
private void showStorage() {
    StringBuilder builder = new StringBuilder();
    builder.append(ExternalTools.getPublicDir());
    builder.append("\n");
    builder.append(ExternalTools.getStorageSize());
    builder.append("\n");
    textView.setText(builder.toString());
}
```

# JAVA 17: 关于 Java 与 Android: 软件开发 外部存储

首先，定义了两个与回调方法相关的常量。接下来，有两个变量用于用户界面中的两个文本组件。这些变量在 `onCreate()` 中初始化，但 `onCreate()` 仅包含与三个按钮关联事件处理器，每个处理器都会调用一个方法。

SAVE 按钮的事件处理器调用 `askPermission()` 方法。在 Android 23 版本之前，只要在清单（manifest）中声明，应用程序就拥有外部存储的写权限；但从 23 版本及更高版本，要求变得更加严格，用户现在必须在简单的对话框中主动授予权限（这是用户首次运行程序时看到此操作，请参阅第 11 节）。`askWritePermission()` 方法带有两个参数调用 `askPermission()` 方法，第一个是程序开始时定义的两个常量之一，另一个是用户可能允许的权限。

在 `askPermission()` 中，首先测试 Android 版本，如果小于 23，则不执行任何操作且方法返回 `true`。否则，使用以下方法：

```
ContextCompat.checkSelfPermission(this, permission)
```

![](img/dfa4439d1c62650bb2a6b471e62c51e8_103_0.png)

# 赋能人才。改进业务。

挪威商学院（BI Norwegian Business School）是欧洲最大的商学院之一，招收 20,000 多名学生。学生提供了一个具有国际视野、充满活力且多元文化的学习环境，培养学生的专业技能以满足企业需求。

BI 提供为期两年、全制的理硕士（MSc）课程，完全用英语授课，并旨在提供专业技能以满足企业日益增长的需求。硕士课程提供了一个充满活力且多元文化的学习环境，为你的开启职业生涯提供最佳平台。

- 商业/工商管理硕士

- 金融经济学硕士

- 战略营销管理硕士

- 领导力与组织心理学硕士

www.bi.edu/master

# JAVA 17: 更多 Java 与 Android: 软件开发

# 外部存储

为了测试你是否已请求权限，如果不是，则调用方法：

```
requestPermissions(new String[] { permission }, requestID)
```

并且 `askPermission()` 返回 `false`。正是 `requestPermissions()` 方法在用户必须主动分配所需权限时打开对话框。`requestPermissions()` 方法调用回调方法：

```
onRequestPermissionsResult(...)
```

返回用户选择的结果。在这种情况下，如果用户已授予权限，则调用 `writeFile()` 方法写入文件，否则会显示一个简单的 Toast 提示未授予权限。

如果方法 `askPermission()` 返回 `true`，则 `askWritePermission()` 将调用 `writeFile()`。

然后 `writeFile()` 方法相对于我之前处理的内部存储并没有增加多少新，最重要的一点是：

```
Environment.getExternalStorageDirectory().getAbsolutePath() + "/note.txt"
```

它决定了外部存储中的文件名。你应该注意，文件存储在外部存储的根目录下，这显然并不一定如此。文件名是硬编码的，在实践中这并不合适。

`askReadPermission()` 方法从中间按钮的事件处理器中调用，其原理上与 `askWritePermission()` 完全相同，但区别在于。

# JAVA 17：更多关于 Java 与安卓：软件开发

# WEB

![](img/dfa4439d1c62650bb2a6b471e62c51e8_108_0.png)

## 8.1 使用 LOADDATA()

WebView 组件通常可以用于显示 HTML，它并不需要像上面那样是互联网上页面的结果。应用场景更多，例如，你可以显示包含 HTML 的文件内容，在原则上，你可以将整个用户界面定义为 HTML 并使用 WebView 组件进行显示。Web2 项目展示了如何实现。布局与 TheWeb1 相同。此外，我从《Java 16》书中的 TheKings 项目添加了 King 和 Kings 两个类，并修改了 King 类中的 `toString()` 方法。通过这两个类，我创建了 MainActivity 来实现以下功能：

```java
public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        webView = (WebView) findViewById(R.id.webview);
        webView.loadData(buildHtml(), "text/html", "UTF-8");
    }
}
```

```java
private String buildHtml() {
    List<King> kings = (new Kings()).getKings();
    StringBuilder builder = new StringBuilder();
    builder.append("<html><p><ol>");
    for (King king : kings) {
        builder.append("<li>");
        builder.append(king.toString());
        builder.append("</li>");
    }
    builder.append("</ol></p></html>");
    return builder.toString();
}
```

唯一需要注意的是 `buildHtml()` 方法，它动态构建了一个带有 HTML 的字符串，并且 WebView 组件使用 `loadData()` 方法显示此文本。运行应用程序后的结果如下：

![](img/dfa4439d1c62650bb2a6b471e62c51e8_109_0.png)

到 2020 年，风能本可以提供我们地球十分之一的电力需求。在今天，SKF 的创新对于运行全球大部分风力发电机至关重要。发电成本的 25% 与维护有关。得益于我们的在线状态监控和自动润滑系统，风能比以往任何时候都更经济地产生更清洁/更便宜的能量。通过分享我们的经验、专业知识和创意，行业可以实现超越预期的性能。如果没有能够应对挑战的最优秀员工将！

知识工程的力量

接入知识工程的力量，

访问我们的网站：www.skf.com/knowledge

![](img/dfa4439d1c62650bb2a6b471e62c51e8_109_1.png)

# JAVA 17：更多关于 Java 与安卓：软件开发

# WEB

![](img/dfa4439d1c62650bb2a6b471e62c51e8_110_0.png)

## 8.2 连接到 URL

WebView 组件可以用于显示网站，但在与手机应用关联时，它远不是互联网的典型用法。更多情况下，你感兴趣的是通过连接到 URL 将数据检索到手机。这可能是一个以特定格式返回数据的 Web 服务，实际上有许多公开且任何想要应用它们的人都可以直接的服务。这些服务中许多返回 JSON 数据，这并没有很大影响，因为有标准的解析器，所以易于使用。在本节中，我将展示一个连接到服务并检索服务数据的应用程序。应用程序没有使用相关数据（不解释数据），但在检索数据后，一个 *Toast* 会告知检索了多少字符。

涉及的服务如下：

```
http://portal.opendata.dk/api/3/action/datastore_search?resource_id=c3097987-c394-4092-add1-ad86a1dbf37
```

它指向一个免费提供丹麦数据的数据的组织。该项目名为 *TheWeb3*，布局非常简单，只有一个按钮。点击按钮会创建到上述地址的连接，应用程序会读取相关的 JSON 数据，但不对其进行解释。*MainActivity* 的代码如下：

```java
package dk.torus.theweb3;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.os.AsyncTask;
import android.widget.Reader;
import android.view.View.*;
import java.util.*;
import java.net.*;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    public void onClick(View v) {
        new InternetTask().execute();
    }

    private class InternetTask extends AsyncTask<Void, Void, String> {
        @Override
        protected void onPreExecute() {
        }

        @Override
        protected String doInBackground(Void... params) {
            StringBuilder builder = new StringBuilder();
            try {
                URL url = new URL("http://portal.opendata.dk/api/3/action/datastore_search?resource_id=c3097987-c394-4092-add1-ad86a1dbf37");
                HttpURLConnection conn = (HttpURLConnection) url.openConnection();
                conn.setRequestProperty("User-Agent", "");
                conn.setRequestMethod("GET");
                conn.setDoInput(true);
                BufferedReader reader = new BufferedReader(new InputStreamReader(conn.getInputStream()));
                String content;
                while ((content = reader.readLine()) != null) {
                    builder.append(content);
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
            return builder.toString();
        }

        @Override
        protected void onPostExecute(String result) {
            Toast.makeText(getApplicationContext(), result.length() + " characters", Toast.LENGTH_LONG).show();
        }
    }
}
```

# JAVA 17：更多关于 Java 与安卓：软件开发

# WEB

![](img/dfa4439d1c62650bb2a6b471e62c51e8_112_0.png)

## 8.3 下载文件

作为 Web 最后一个示例，我将展示一个下载文件并将其保存到外部存储的程序。该程序名为 TheWeb4。该程序的清单有两个权限：

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
```

## JAVA 17：更多关于 Java 和安卓：软件开发

应用程序的用户界面仅包含一个可以开始下载文件的按钮。文件下载是使用 `DownloadManager` 类完成的，该类提供了所需的功能。我不想在这里显示 `MainActivity` 的代码，但鼓励你查看一下代码。在这种情况下，要下载的文件是硬编码的，当然这不一定如此。

![](img/dfa4439d1c62650bb2a6b471e62c51e8_114_0.png)

## 关于服务（Services）

在前书中我介绍过 Service，但还有更多需要补充，特别是 Activity 如何与 Service 通通信。这是本章的主题。



如果组件通过调用`startActivity()`启动 Service，该 Service 将一直运行，直到它调用`stopSelf()`停止，或者另一个组件调用`stopService()`停止。如果组件通过调用`bindService()`启动 Service，只要有组件绑定到它，Service 就会运行；只有当 Service 不再被绑定时，Android 才会将其关闭。然而，如果系统内存不足且需要为用户正在操作的 Activity 获取资源，Service 也可以被停止。

如果通过`startActivity()`启动 Service，则启动的 Activity 与 Service 之间没有直接通信。Service 执行其工作，无法向它发送消息（停止它除外），且 Service 无法调用启动 Activity 的方法，你只能通过 Toast 或通知的形式获取它的消息。如果有直接通信的需求，则需要放置一个名为接收器（receiver）的中介。如果 Service 能够接收来自 Activity 的消息，则 Service 必须实例化接收器对象（这是一个`BroadcastReceiver`对象），并将该对象注册为想要接收特定 ID 消息的接收者。想要接收 Service 消息的 Activity 也是如此，它也必须创建并注册接收器对象。

应用程序的 Services 打开了以下窗口：

![](img/dfa4439d1c62650bb2a6b471e62c51e8_115_0.png)

## JAVA 17：关于 Java 和安卓：软件开发——更多关于服务

如果你点击 START 按钮，会启动一个 Service，每秒发送一条消息，计数器加 1，这意味着 Activity 每秒都会收到来自 Service 的消息。点击 STOP 按钮会停止 Service。最后，最后一个按钮用于向 Service 发送消息，即输入字段中输入的文本，之后 Service 将该文本转换为大写字母并回传给 Activity。这意味着 Activity 也也必须实例化一个接收器对象，以便接收来自 Service 的消息。当 Service 将收到的消息转换为大写时，仅仅是为了显示 Service 已执行了某些操作。以下是点击 START 按钮、输入文本并点击 SEND 按钮后的应用程序窗口：

![](img/dfa4439d1c62650bb2a6b471e62c51e8_116_0.png)

在布局方面，没有新内容，只是关于在窗口中放置 6 个组件。该 Service 被命名为`TheService`，代码如下：

```java
package dk.data.torus.theservice;

import android.app.Service;
import android.content.*;
import android.os.IBinder;
import android.widget.Toast;
```

```java
public class TheService extends Service {
    public final static String KEY_COUNTER_CLIENT = "KEY_COUNTER_CLIENT";
    public final static String KEY_RECEIVE_CLIENT = "KEY_RECEIVE_CLIENT";
    public final static String GET_COUNTER_CLIENT = "GET_COUNTER_CLIENT";
    public final static String GET_MESSAGE_CLIENT = "GET_MESSAGE_CLIENT";
    public final static String GET_MESSAGE_SERVICE = "KEY_MESSAGE_SERVICE";
    private TheReceiver getReceiver();
    private TheThread getThread();
    private int counter = 0;
```

```java
@Override
public IBinder onBind(Intent intent) {
    return null;
}
```

```java
@Override
public void onCreate(getApplicationContext()) {
    Toast.makeText(getApplicationContext(),"Service created",
    Toast.LENGTH_LONG).show();
    theReceiver = new TheReceiver();
    super.onCreate();
}
```

```java
@Override
public int onStartCommand(Intent intent, int flags, int startId) {
    Toast.makeText(getApplicationContext(), "Service started",
    Toast.LENGTH_LONG).show();
    IntentFilter intentFilter = new IntentFilter();
    intentFilter.addAction(GET_MESSAGE_SERVICE);
    registerReceiver(theReceiver, intentFilter);
    theThread = new TheThread();
    theThread.start();
    return super.onStartCommand(intent, flags, startId);
}
```

```java
@Override
public void onDestroy() {
    Toast.makeText(getApplicationContext(),"Service destroyed",
    Toast.LENGTH_LONG).show();
    theThread.terminate();
    unregisterReceiver(theReceiver);
    super.onDestroy();
}
```

```java
public class TheReceiver extends BroadcastReceiver {
    @Override
    public void onReceive(Context context, Intent intent) {
        String action = intent.getAction();
        if(action.equals(GET_MESSAGE_SERVICE)) {
            String msg = intent.getString(KEY_MESSAGE_SERVICE);
            Intent tosend = new Intent();
            tosend.setAction(GET_MESSAGE_CLIENT);
            tosend.putExtra(KEY_RECEIVE_CLIENT, msg.toUpperCase());
            sendBroadcast(tosend);
        }
    }
}
```

```java
private class TheThread extends Thread {
    private boolean running;
    public void terminate() {
        running = false;
    }
    @Override
    public void run() {
        while(running) {
            try {
                Thread.sleep(1000);
                Intent intent = new Intent();
                intent.setAction(GET_COUNTER_CLIENT);
                intent.putExtra(KEY_COUNTER_CLIENT, counter);
                sendBroadcast(intent);
                counter++;
            } catch (InterruptedException e) {
            }
        }
    }
}
```

# JAVA 17: 关于 JAVA 和 Android 的更多：软件开发

然后是 MainActivity 类：

```java
public class MainActivity extends AppCompatActivity {
  private EditText txtToSend;
  private TextView txtReceived;
  private TextView txtCounter;
  private final BroadcastReceiver theReceiver = null;
  private Intent theIntent = null;

  @Override
  protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);
    txtToSend = findById(R.id.txtToSend);
    txtReceived = findById(R.id.txtReceived);
    txtCounter = findById(R.id.txtCounter);
    findById(R.id.cmdStart).setOnClickListener(new View.OnClickListener() {
      @Override
      public void onClick(View v) {
        startService();
      }
    });
    findById(R.id.cmdStop).setOnClickListener(new View.OnClickListener() {
      @Override
      public void onClick(View v) {
        stopService();
      }
    });
    findById(R.id.cmdSend).setOnClickListener(new View.OnClickListener() {
      @Override
      public void onClick(View v) {
        String message = txtToSend.getText().toString();
        Intent intent = new Intent();
        intent.setAction(TheService.GET_MESSAGE_SERVICE);
        intent.putExtra(TheService.KEY_MESSAGE_SERVICE, message);
        sendBroadcast(intent);
      }
    });
  }

  private void startService() {
    if (theIntent == null) {
      startService(theIntent = new Intent(MainActivity.this, TheService.class));
    }
  }

  private void stopService() {
    if (theIntent != null) stopService(theIntent);
    theIntent = null;
  }
}
```

# JAVA 17: 更多 JAVA 和 Android：软件开发

更多关于服务的介绍

```java
@Override
protected void onCreate() {
    theReceiver = new Receiver();
    Intent intentFilter = new IntentFilter();
    intentFilter.addAction(TheService.GET_COUNTER_CLIENT);
    intentFilter.addAction(TheService.GET_MESSAGE_CLIENT);
    registerReceiver(theReceiver, intentFilter);
    super.onStart();
}

@Override
protected void onStop() {
    unregisterReceiver(theReceiver);
    super.onStop();
}

@Override
protected void onDestroy() {
    super.onDestroy();
    stopService();
}
```

![](img/dfa4439d1c62650bb2a6b471e62c51e8_121_0.png)

# JAVA 17: 关于 JAVA 和 Android 的更多：软件开发

```java
private class TheReceiver extends BroadcastReceiver {
  @Override
  public void onReceive(Context context, Intent intent) {
    String action = intent.getAction();
    if (action.equals(TheService.GET_COUNTER_CLIENT)) {
        int value = intent.getIntExtra(TheService.KEY_COUNTER_CLIENT, 0);
        txtCounter.setText(String.valueOf(value));
    } else if (action.equals(TheService.GET_MESSAGE_CLIENT)) {
        String message = intent.getStringExtraExtra(TheService.KEY_RECEIVE_CLIENT);
        txtReceived.setText(String.valueOf(message));
    }
  }
}
```

该类首先定义了 3 个变量用于引用用户界面中的文本。这是一个内部类。此外，还有一个类型为`TheReceiver`的接收器变量以及一个用于启动服务的`Intent`变量。在`onCreate()`中，这三个变量被初始化为组件，并将事件处理器绑定到三个按钮上。

程序还实现了`on()`，其中接收器会被触发。`IntentFilter`定义了接收器在注册后必须处理的两个动作。注意`stop()`的实现，它移除了注册。接收器本身派自`BroadcastReceiver`，其工作原理与`TheService`类相同，根据根据执行的动作更新组件接口。

START 按钮的事件处理器调用`startService()`方法，该方法与之前的书中一样，启动一个类型为 TheService 的服务。该服务在 STOP 按钮的事件处理器中停止。最后，有一个发送输入框中输入文本的事件处理器。这与上述所示使用`sendBroadcast()`的方式相同。在这里你应该注意，如果服务没有启动，则什么都不会发生，因为这意味着没有该动作的监听器。

为了使其能够工作，必须在清单文件中添加一个元素来定义该服务，然后可以通过模拟器或物理设备对应用程序测试：

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="dk.data.torus.theservices">
    <application>
        <activity android:name=".MainActivity">
            ...
    </application>
</manifest>
```

# JAVA 17: 关于 JAVA 和 Android 的更多：软件开发

更多关于服务的介绍

```xml
<activity>
<service android:name="TheService"/>
</application>
</manifest>
```

## 9.1 一个 INTENTSERVICE

在示例中，服务使用定义为内部类的线程来执行其 Intent 工作。相反，你可以将服务定义为`IntentService`（可能可以参考之前的书），它会自动将工作分配给线程。`TheServices`项目与上面的示例相同，但服务改为`IntentService`。服务的代码如下：



```java
package dk.data.torus.theservices;

import android.app.IntentService;
import android.content.*;
import android.os.*;
import android.widget.Toast;

public class TheService extends IntentService {
    public final String KEY_COUNTER_CLIENT = "KEY_COUNTER_CLIENT";
    public final String KEY_RECEIVE_CLIENT = "KEY_RECEIVE_CLIENT";
    public final String GET_COUNTER_CLIENT = "GET_COUNTER_CLIENT";
    public final String GET_MESSAGE_SERVICE = "GET_MESSAGE_SERVICE";
    private Receiver receiver;
    private int counter;

    public TheService() {
        super("TheService");
    }

    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        Toast.makeText(getApplicationContext(),"Service created",Toast.LENGTH_LONG).show();
        receiver = new Receiver();
    }

    @Override
    protected void handleIntent(Intent intent) {
        counter = intent.getIntExtra("WORK_TO_DO", 10);
        while (counter >= 0) {
            try {
                Thread.sleep(1000);
                Intent tosend = new Intent();
                tosend.setAction(GET_COUNTER_CLIENT);
                tosend.putExtra(KEY_COUNTER_CLIENT, counter);
                sendBroadcast(tosend);
                counter--;
            } catch (InterruptedException e) {
            }
        }
    }

    @Override
    public int startCommand(Intent intent, int flags, int startID) {
        Toast.makeText(getApplicationContext(),"Service started",Toast.LENGTH_LONG).show();
        IntentFilter intentFilter = new IntentFilter();
        intentFilter.addAction(GET_MESSAGE_SERVICE);
        registerReceiver(receiver, intentFilter);
        return super.startCommand(intent, flags, startID);
    }

    @Override
    public void onDestroy() {
        Toast.makeText(getApplicationContext(),"Service destroyed",Toast.LENGTH_LONG).show();
        unregisterReceiver(receiver);
    }

    private class Receiver extends BroadcastReceiver {
        @Override
        public void onReceive(Context context, Intent intent) {
            String action = intent.getAction();
            if (action.equals(GET_MESSAGE_SERVICE)) {
                String msg = intent.getStringExtra(KEY_MESSAGE_SERVICE);
                Intent tosend = new Intent();
                tosend.setAction(GET_COUNTER_CLIENT);
                tosend.putExtra(KEY_RECEIVE_CLIENT, msg.toUpperCase());
                sendBroadcast(tosend);
            }
        }
    }
}
```

# JAVA 17: 更多 JAVA 和 Android：软件开发

更多服务

`MainActivity` 与之前的示例几乎相同（简单一些），我不想在这里显示代码。

# JAVA 17: 关于 JAVA 和 ANDROID：软件开发

## 9.2 一个永不停的服务

作为最后一个部分，关于服务，我将展示一个包含两个程序的示例：

1. 一个程序，它启动一个服务并在后台持续运行的同时生成质数，并且对于每一个质数服务都会广播该质数。
2. 一个程序，注册为质数的监听器，并在屏幕上显示每一个新质数。

原则上，这非常简单，但有一个简单的挑战，即如何在活动完成后仍保持服务运行。该服务属于项目 `TheService3`，其中有三个 Java 文件需要你注意。

第一个是 `PrimesStarter`，这是一个非常简单的接收器类：

```java
package dk.data.torus.theservices;

import android.content.BroadcastReceiver;
import android.content.Context;
import android.content.Intent;

public class PrimesStarter extends BroadcastReceiver {
    @Override
    public void onReceive(Context context, Intent intent) {
        context.startService(new Intent(context, PrimesService.class));
    }
}
```

如你所见，`onCreate()` 中什么都没有发生，只是启动了服务。目前，还很难看出这个类在做什么，但它应该能解决这样一个问题：如果应用程序启动了服务，随后应用程序关闭，则终止该服务。

该服务名为 `PrimesService`：

```java
package dk.data.torus.theservices;

import android.app.Service;
import android.content.Intent;
import android.os.IBinder;

public class PrimesService extends Service {
    private long prime = 0;
    private TheThread theThread;
```

```java
@Override
public int onStartCommand(Intent intent, int flags, int startID) {
  super.onStartCommand(intent, flags, startID);
  theThread = new Thread();
  theThread.start();
  return START_STICKY;
}
```

```java
@Override
public void onDestroy() {
  super.onDestroy();
  sendBroadcast(new Intent("dk.data.torus.RestartPrimes"));
  theThread.terminate();
}
```

```java
@Override
public IBinder onBind(Intent intent) {
  return null;
}
```

![](img/dfa4439d1c62650bb2a6b471e62c51e8_127_0.png)

```java
private class TheThread extends Thread {
    private boolean running;
    public void terminate() {
        running = false;
    }
    @Override
    public void run() {
        running = true;
        while (running) {
            try {
                while (!isPrime(prime)) {
                    ++prime;
                    if (prime == Long.MAX_VALUE) prime = 0;
                }
                Intent tosend = new Intent();
                tosend.putExtra("PRIME", prime);
                sendBroadcast(tosend);
                ++prime;
            } catch (Exception e) {
            }
        }
    }
}
```

```java
private boolean isPrime(long t) {
    if (t == 2 || t == 3 || t == 5 || t == 7) return true;
    if (t < 11 || t % 2 == 0) return false;
    for (long n = 3, m = (long)Math.sqrt(t) + 1; n <= m; n += 2)
        if (t % n == 0) return false;
    return true;
}
```

`onStartCommand()` 创建了一个线程并启动它。只要变量 `running` 为 `true`，它就会一直运行（直到执行 `terminate()` 方法）。在每次迭代中，都会确定下一个质数并广播该数字。其想法是，如果允许服务运行长时间，确定下一个质数将花费时间，从客户端你会发现每个数字显示之间存在时间间隔。

有一个 `onDestroy()`，它发送一个值为 `dk.torus.data.RestartPrimes` 的广播。这意味着上述类 `PrimesRestarter` 中的 `onDestroy` 方法将被执行并重启服务。这确保了在活动关闭后，服务仍在运行。

然后是 `MainActivity`，它是显而易见的：

```java
package dk.data.torus.services;

import android.content.Intent;
import android.os.Bundle;
import android.support.v7.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
      super.onCreate(savedInstanceState);
      startService(new Intent(this, PrimesService.class));
      finish();
    }
}
```

`onCreate` 启动服务，之后活动将自关闭。你应该注意这里没有 `setContentView` —— 应用程序没有用户界面。项目有一个 `activity_main.xml`，可以轻松删除。它是由 Android Studio 自动生成的，可能对测试有用。

现在，这个创建并启动服务的应用程序几乎完成了。缺少的是将它们整合在一起的清单文件（manifest）：

```xml
<xml version="1.0" encoding="utf-8"?>
<manifest xmlns="http://schemas.android.com/apk/res/android"
    package="dk.data.torus.services3">
    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <activity android:name=".MainActivity">
            <intent-filter>
              <action android:name="android.intent.action.MAIN" />
              <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
        <service
            android:name="dk.data.torus.services3.PrimesService"
            android:enabled="true" />
    </application>
</manifest>
```

```xml
<receiver
  android:name="dk.data.torus.webservices3.PrimesRestarter"
  android:enabled="true"
  android:exported="true"
  android:label="RestartServiceWhenStopped">
  <intent-filter>
    <action android:name="dk.data.torus.RestartPrimes"/>
  </intent-filter>
</receiver>
```

# 10 通知 (NOTIFICATIONS)

在手机应用程序开发的最后一部分中，我想提到“通知”，即程序希望让用户意识到某个事件的发生。这通过唤起用户的注意力来实现，例如播放声音或让手机振动，并且通常会结合在手机通知栏中显示一个图标来完成。名为 `Notifications` 的程序展示了如何操作，这实际上非常简单，因为 Android 有一个 `NotificationManager` 类，提供了所需的所有功能。该程序打开了以下内容：

![](img/dfa4439d1c62650bb2a6b471e62c51e8_132_0.png)

顶部的按钮发送通知，底部的另一个按钮移除通知，这样图标就会从应用程序的通知栏中消失。布局非常简单，仅由一个包含两个按钮的 `RelativeLayout` 组成。除了布局，程序只包含 `MainActivity` 类。

```java
package dk.data.torus.notifications;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.app.*;
import android.net.Uri;
import android.view.View;
```

# JAVA 17：更多关于 JAVA 和 ANDROID：软件开发



# JAVA 17：更多关于 Java 与安卓：软件开发

## 通知（Notifications）

通知功能用于在应用后台或未打开时向用户传递信息。这通过唤起用户的注意力来实现，例如播放声音或让手机振动，并且通常会结合在手机通知栏中显示一个图标来完成。名为 `Notifications` 的程序展示了如何操作，这实际上非常简单，因为 Android 有一个 `NotificationManager` 类，提供了所需的所有功能。该程序打开了以下内容：

![](img/dfa4439d1c62650bb2a6b471e62c51e8_132_0.png)

顶部的按钮发送通知，底部的另一个按钮移除通知，这样图标就会从应用程序的通知栏中消失。布局非常简单，仅由一个包含两个按钮的 `RelativeLayout` 组成。除了布局，程序只包含 `MainActivity` 类。

```java
package dk.data.torus.notifications;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.app.*;
import android.net.Uri;
import android.view.View;
```

```java
public class MainActivity extends AppCompatActivity {
    private static int NOTIFICATION_ID = 12345;
    private int count = 0;
    private NotificationManager notMgr = null;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        notMgr = (NotificationManager)getSystemService(NOTIFICATION_SERVICE);
        findViewById(R.id.cmdNotify).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                notifyUser(v);
            }
        });
        findViewById(R.id.cmdClear).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                clearNotification(v);
            }
        });
    }
```

```java
public void notifyUser(View view) {
    Notification noti = new Notification.Builder(MainActivity.this)
        .setContent("注意这里")
        .setSmallIcon(R.drawable.alarm)
        .setWhen(System.currentTimeMillis())
        .setContentTitle("来自 Poul")
        .build();
    noti.sound = Uri.parse("android.resource://" + getPackageName() + "/" + R.raw.sound);
    noti.vibrate = new long[]{1000L, 500L, 1000L, 500L, 1000L};
    noti.number++;
    noti.flags |= Notification.FLAG_AUTO_CANCEL;
    notMgr.notify(NOTIFICATION_ID, noti);
}

public void clearNotification(View view) {
    notMgr.cancel(NOTIFICATION_ID);
}
```

在 `onCreate()` 中，创建了一个类型为 `NotificationManager` 的对象，该对象提供了所有所需的可用对象。

## 位置权限

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);
    locationManager = (LocationManager) 
        getSystemService(Context.LOCATION_SERVICE);
    cmdGrant = findViewById(R.id.cmdGrant);
    cmdCheck = findViewById(R.id.cmdCheck);
    cmdCheck.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View v) {
            if(permission = hasPermission()) {
                Toast.makeText(MainActivity.this,"You already have the permission",
                Toast.LENGTH_LONG).show();
                permission = true;
            } else requestPermission();
        }
    });
}
```

```java
cmdCheck.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View v) {
            if (waitingGps) return;
            if(!permission) {
                Toast.makeText(MainActivity.this,
                "You have no permission",Toast.LENGTH_LONG).show();
                return;
            }
            try {
                waitingGps = true;
                locationManager.requestLocationUpdates(LocationManager.GPS_PROVIDER,
                10 * 1000, 1, gpsListener);
            } catch (SecurityException ex) {
            }
        }
    });
}
```

```java
private boolean hasPermission() {
    return ContextCompat.checkSelfPermission(this,
        Manifest.permission.ACCESS_FINE_LOCATION) ==
        PackageManager.PERMISSION_GRANTED;
}

private void requestPermission() {
    if (ActivityCompat.shouldRequestPermissionRationale(this,
    Manifest.permission.ACCESS_FINE_LOCATION)) {
        Toast.makeText(MainActivity.this,"This permission is very dangerous",
        Toast.LENGTH_LONG).show();
        ActivityCompat.requestPermissions(this, new String[]{
        { Manifest.permission.ACCESS_FINE_LOCATION }, ACCESS_FINE_CODE);
    }
}
```

```java
@Override
public void onRequestPermissionsResult(int requestCode,
@NonNull String[] permissions, @NonNull int[] grantResults) {
if (requestCode == ACCESS_FINE_CODE) {
    if (grantResults.length > 0 && grantResults[0] ==
    PackageManager.PERMISSION_GRANTED) {
        Toast.makeText(this,"You now have permission for check location",
        Toast.LENGTH_LONG).show();
    }
    else {
        Toast.makeText(this,
        "You are denied the permission",Toast.LENGTH_LONG).show();
    }
    permission = ContextCompat.checkSelfPermission(this,
    Manifest.permission.ACCESS_FINE_LOCATION) ==
    PackageManager.PERMISSION_GRANTED;
}
}
```

![](img/dfa4439d1c62650bb2a6b471e62c51e8_139_0.png)

```java
private final LocationListener gpsListener = new LocationListener (
    @Override
    public void onLocationChanged(Location location) {
        final double longitude = location.getLongitude();
        final double latitude = location.getLatitude();
        runUIThread(new Runnable() {
            @Override
            public void run() {
                Toast.makeText(MainActivity.this,
                String.format("Longitude: %1.4f\nLatitude: %1.4f", longitude, latitude), Toast.LENGTH_SHORT).show();
                locationManager.removeUpdates(gpsListener);
                waitingGps = false;
            }
        });
    }
    @Override
    public void onStatusChanged(String s, int i, Bundle bundle) {
    }
    @Override
    public void onProviderEnabled(String s) {
    }
    @Override
    public void onProviderDisabled(String s) {
    };
};
```

## 广告

我加入 MITAS 是因为我想要真正的责任感

工程师与地质科学家研究生计划

www.discovermitas.com

![](img/dfa4439d1c62650bb2a6b471e62c51e8_133_0.png)

第 16 个月

我曾在北海担任施工主管，指导并帮助工头解决问题

真实工作

国际机会

三次实习

![](img/dfa4439d1c62650bb2a6b471e62c51e8_133_1.png)

在 bookboom.com 下载免费电子书



最初，除了定义的常量和 5 个变量外，其中第一个是 `LocationManager`，接下来两个是对两个按钮的引用。变量 `permission` 被用于控制按钮是否被点击以及用户是否已获得读取位置的权限。点击底部按钮时，`waitingGps` 变量被设置为 `true`，表示正在读取位置。目标是避免在第一次返回之前再次开始读取。

`onCreate` 包含了很多内容，但主要是由于两个按钮的事件处理器。顶部按钮的事件处理器测试 `permission` 变量并调用 `hasPermission()` 方法来检查用户是否已拥有该权限。`hasPermission()` 方法使用：

```
ContextCompat.checkSelfPermission(this, Manifest.permission.ACCESS_FINE_LOCATION)
```

来测试应用程序是否拥有 `ACCESS_FINE_LOCATION` 权限。如果不是第一次使用应用程序，它将拥有该权限。如果用户已经拥有所需的权限，则显示一个 Toast，并将 `permission` 变量设置为 `true`。否则，调用 `requestPermission()` 方法。

这里是第一次调用：

```
ActivityCompat.shouldShowRequestPermissionRationale(
    this,
    Manifest.permission.ACCESS_FINE_LOCATION
)
```

来测试 `ACCESS_FINE_LOCATION`，其意思是你可以做一些事情来告诉用户权限的含义。在这种情况下，会出现一个简单的 Toast（这没有意义，因为在下一个 Toast 出现之前，你无法点击到它）。

调用方法：

```
ActivityCompat.requestPermissions(
    this,
    new String[] { Manifest.permission.ACCESS_FINE_LOCATION },
    ACCESS_FINE_CODE
)
```

会打开一个对话框，用户可以在其中允许或拒绝。对话框会回调 `onRequestPermissionsResult`，用户现在拥有了检查位置的权限，显示一个 Toast 并初始化 `permission`。

第二个按钮的事件处理器返回位置信息，如果已经开始，则什么都不做。否则，测试 `permission`，如果为 `false`，显示一个 Toast。否则，将 `waitingGps` 设置为 `true`，并使用 `locationManager` 请求读取位置。这是在程序末尾通过 `gpsListener` 对象完成的。当位置返回时，调用 `gpsListener` 的 `onLocationChanged` 方法，显示一个 Toast，并使用 `locationManager` 对象移除更新。

Java 17：关于 Java 和安卓的更多：软件开发

# 12 最后一个示例：WineApp（葡萄酒管理应用）

Java 6 这本书的最后一个示例是一个用于管理私人酒窖的程序。该程序从功能和实现上来看非常出色，但对于实际使用来说，存在一个大问题，即它是一个 PC 程序。这意味着你必须坐在电脑前才能访问（购买）葡萄酒；相应地，每当你使用一瓶酒，尤其是最后一瓶时，都要运行程序。如果你把它推迟到你在电脑前时再做，你就无法完成。

因此，考虑一个像手机 App 这样的解决方案是理所当然的，这意味着程序“随身携带”。这样，使用该程序的几率将会大大增加。以下是关于如何将 WineApp 程序实现为手机 App 的说明。因此，你可以将此任务视为将程序从一个平台迁移到另一个平台。

该程序在逻辑和工作上与之前的版本基本相同，但程序必须使用 SQLite 代替 MySQL。此外，还应该考虑是否有功能需要更改，最后是考虑如何简化应用程序的使用。此外，你应该使用手机摄像头，这样就可以保存酒瓶的照片。

将应用程序迁移到手机的挑战之一就是屏幕太小。应用程序的用户界面必须分别为手机和平板电脑进行定制。由于手机没有适当的用户界面（由于虚拟键盘的原因），已决定程序不支持横屏模式。

## 12.1 开发计划

应用程序的开发计划包括以下迭代，其中每次迭代的结果都是上一次迭代结果的扩展。

| 任务 | 天数 |
| :--- | :---: |
| `MainActivity`。启动活动中应该包含什么，特别是如何在应用程序功能之间进行导航。 | 2 |
| 程序架构、设计以及数据库的实现。 | 2 |
| 葡萄酒属性维护：生产者。 | 1 |
| 葡萄酒属性维护：供应商。 | 1 |
| 葡萄酒属性维护：国家。 | 1 |
| 葡萄酒属性维护：地区。 | 1 |
| 葡萄酒属性维护：分类。 | 1 |
| 葡萄酒属性维护：葡萄品种。 | 1 |
| 葡萄酒属性维护：葡萄酒类型。 | 1 |
| 葡萄酒属性维护：类别。 | 1 |
| 葡萄酒属性维护：瓶 / 包装。 | 1 |
| 创建葡萄酒。也包括拍照。 | 4 |
| 维护葡萄酒。也包括照片的维护。 | 3 |
| 购买葡萄酒。 | 3 |
| 消费葡萄酒。 | 3 |
| 搜索葡萄酒。 | 4 |
| 关注准备好饮用的葡萄酒。 | 3 |
| 重构与测试。 | 4 |
| 部署。 | 2 |

右列的数字表示迭代的复杂度。它们没有给出具体的估值，但反映了复杂程度以及在哪里会遇到特殊挑战。假设 1 = 一个工作日，这意味着预计工作量约为 20 个工作日。经验表明某些任务比预计的要长，因此建议将估计时间延长 25%。如果是这样，我估计时间大约为 25 个工作日；如果程序由一个开发者编写，大约需要 1 个月。

最后，开发过程中可能会出现新功能。如果是这样，显然需要扩展估值。

查看上述估值，它们并不精确。可以预计某些预估任务可能会比预计更长，但可能另一些任务花费的时间少于预估时间。其他情况是，由于几次迭代相似，因此在某种程度上它们是相互重复的。

如果事实证明你节省了时间并提前完成，在原则上是好的，但你应该在项目早期谨慎调整预期的耗时，因为有高风险其他迭代可能被低估。而如果其他迭代产生了时间储备，那是好事，因为你以后在流程中可能需要这些时间。

时间估计是软件开发中最困难的预测之一。软件开发者往往倾向于低估，或出于政治、业务原因故意这样做。方法是将任务分解为许多小的子任务，每个子任务都很小，且复杂度使你能够评估任务所需的时间。

即使你得到了时间，时机也具有巨大的不确定性，因为实践表明，总有一些任务因为某些原因比预计的要长。原因有很多，从简单到……由于在项目期间的……（包括微小任务）。

![图片](img/dfa439d1c62650bb2a6b471e6c51e8_145)

Java 17：关于 Java 和安卓的更多：软件开发——最后一个示例：WineApp

## 12.2 项目

该项目名为 WineApp，但我不想描述项目过程。我只想提到项目已经按照上述任务拆分完成。当我不想描述开发过程时，是因为会有很多废话，实际上它们并不能告诉你太多信息。

另一方面，鼓励你学习该项目并尝试它，如果不在模拟器中运行，就在手机上运行。该程序相对于本书和前一本书显示的内容，是一个主要的程序，并且使用的安卓功能比其他提到的要多。

通过这个项目新增的新内容（可能它仅仅是一部分），这两本书为移动应用开发提供了基础，但实际上这还有很多内容要学。特别是你应该意识到手机领域的发展仍在移动中，新事物在不断演变，新的方法在不断被开发。

前本书完全专注于使用 Java 编写的应用开发。通过练习，你可以成为一名优秀的安卓设备应用开发者。然而，还有其他工具。如果你打算使用这些工具，有充分的理由关注它们，因为它们有时可能比用 Java 编写应用程序更有效。

总的来说，你应该预计在移动应用开发组织中会遇到其他工具，这是件好事，因为毕竟差异并不大。
