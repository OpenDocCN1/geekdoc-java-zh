
# Android 开发者的 Kotlin 入门指南：在开发 Android 应用的同时轻松学习 Kotlin

## I. 关于这本书

嘿！非常感谢你对这本书的关注，看到你决定成为 Android Kotlin 专家，我感到非常兴奋。

自从我 2015 年年中开始编写《Android 开发者 Kotlin Go》以来，发生了很多事情。那时，Kotlin 仍然处于早期访问版本。然而，我感受到了这种语言巨大的力量，因此决定在书中解释我所学到的一切。

从那时起，这种语言不断成长，直到 Google 宣布他们开始支持 Kotlin 作为开发 Android 应用的官方语言。

这些是令人震惊的消息。但更惊讶的是，Google 和 JetBrains 都向想要学习这种语言的 Android 开发者推荐了这本书。

如你所知，这是一本精益出版物。这本书的成长和进展感谢读者的评论。因此，我只能感谢你帮助我将这个梦想变为现实。

### 《Android 开发者 Kotlin Go》关于什么

在本书中，我将使用 Kotlin 作为主要语言，从零开始创建一个 Android 应用。其核心思想是通过示例来学习语言，而不是遵循普通的参考书结构。我会停下来解释 Kotlin 中最有用的概念和主意，并将它们与 `Java 6` 进行比较。这样，你就能看到差异在哪里，以及语言的哪些部分可以帮助你加速工作。

这本书并不是作为语言参考书，而是 Android 开发者学习 Kotlin 并能够继续进行自己项目的工具。示例旨在解决我们作为应用开发人员在日常生活中面临的最常见问题，方法是利用 Kotlin 的表达能力以及其他令人兴奋的工具和库。然而，本文涵盖了 Kotlin 的大部分功能，因此在阅读结束时，你将对该语言有深入的了解。

内容非常实用，所以我建议你在电脑前跟随示例和代码，并尝试它建议的所有内容。不过，你可以先读一遍以获得大致概念，然后投入实践。

尽管这本书现在已经完成，但我会定期对其进行回顾，以保持与新的 Kotlin 版本同步。因此，欢迎随时写信告诉我对对这本书的看法，或者哪些地方可以改进。我希望这本书成为 Android 开发者的完美工具，因此欢迎任何帮助和建议。

如果你正在阅读纸质版并希望接收最新的更新，请随时通过 `contact@antonioleiva.com` 向我发送邮件并附上购买证明，我将给你数字版的访问权限。这样，你将持续收到更新。如果你是从任何书店（Kindle, Kobo…）购买的并想获取 PDF 版本，也这样做。

感谢你加入这个令人兴奋的项目！

## II. 这本书适合你吗？

这本书旨在为对学习 Kotlin 语言感兴趣的 Android 开发者提供帮助。

如果你处于以下情况，这本书就适合你：

*   你具有一些 Android 开发、Android SDK 以及 Java 语言的基础知识。
*   你想通过遵循示例来学习如何使用 Kotlin 开发 Android 应用。
*   你需要一份指南，关于如何使用更简洁、表达力的语言来解决 Android 开发者每天面临的许多共同挑战。

另一方面，这本书可能不适合你。以下是你在书中找不到的话题：

*   这些页面的内容并不是 Kotlin 圣经。我会解释所有基础知识，当复杂想法出现时也会进行解释。所以你可能是通过示例学习，而不是通过方法。
*   我不会解释如何开发 Android 应用。你不需要对平台有深入理解，但至少需要一些基础知识，如 Android Studio、`Gradle` 和 `Java` 编程。
*   这本书不是函数式编程指南。当然，`Java 6` 完全不是函数式的。

## III. 关于作者

Antonio Leiva 是一位 Android 工程师，花费时间学习获取 Android 的新方法并撰写文章。他在 [antonioleiva.com](http://antonioleiva.com) 编写博客，专注于帮助 Android 开发者学习 Kotlin。

他还举办密集工作坊，参与者会将书中的内容付诸实践。在 10 小时内，人们可以从无知到能够创建自己的应用。

Antonio 起初担任 CRM 技术的顾问，但一段时间后，在寻找真正的热情时发现了 Android 平台。在获得一些经验后，他在一家移动公司开启了新的冒险，在那里他为知名公司领导了多个项目。

他目前在 [Plex](http://plex.tv) 担任 Android 工程师，他在 Android 应用的设计和 UX 上也起着至关重要的作用。

你可以在 Twitter 上的 [@lime_cl](https://twitter.com/lime_cl) 或 Google+ 上的 +AntonioLeivaGordillo 找到 Antonio。

## 1 引言

在 Google I/O 2017 上，Android 团队宣布 Kotlin 将成为开发 Android 应用的官方语言。

这意味着，虽然仍然可以使用 `Java` 开发 Android 应用，但从现在起 Kotlin 得到了完全支持，Google 正在确保新的 Android 特性、框架、IDE 以及他们所有的库都能与新语言无缝衔接。

在书中，我将向你展示如何做，因此我希望我帮助你理解 Kotlin 让你领先一步并让你的代码变得更好的各种方式。

然而，在深入研究语言的特性之前，让我先简单介绍一下背景。

### 1.1 什么是 Kotlin？

Kotlin 是 [JetBrains](https://www.jetbrains.com/) 开发的一种语言，该公司以构建 IntelliJ IDEA（一款功能强大的 Java 开发 IDE）而闻名。官方 Android IDE Android Studio 也基于 IntelliJ。它最初被设计在 Java 虚拟机上运行。

JetBrains 设计 Kotlin 时考虑了 Java 开发者，并以 IntelliJ 作为其主要的开发 IDE。这两个因素是让 Android 开发者快速采用该语言的突破点：

*   `Kotlin 对 Java 开发者来说非常直观且易于学习`。语言的大部分与我们已经熟悉的非常相似，差异可以很快掌握。
*   `我们免费拥有与日常使用的 IDE 的全方位集成`。Android Studio 可以理解、编译和运行 Kotlin 代码。此外，对这种语言的支持来自开发 IDE 的公司，因此我们 Android 开发者是一等公民。

然而，这仅与语言如何与我们的工具集成。与 Java 6 相比，这种语言的优势何？

*   `它更具表现力`：这是它的主要特点之一。你可以用更少的代码实现更多的功能。
*   `它更安全`：Kotlin 是空安全的，这意味着我们在编译时就能处理可能的空情况，以防止运行时异常。我们需要显式地指定一个对象可以为空，然后在使用它之前检查其空值。你可以节省大量调试空指针异常和修复空值错误的时间。
*   `它是函数式的`：Kotlin 从根本上是一种面向对象的语言，而不是纯函数式语言。但是，像许多其他现代语言一样，它使用了函数式编程的许多概念（如 lambda 表达式）来更自然地解决问题。另一个很棒特性是它处理集合的方式。
*   `它利用扩展函数`：这意味着即使我们无法访问，也可以为任何类扩展新功能。
*   `它是高度的互操作性`：你可以继续使用大多数用 Java 编写的库和代码，因为两种语言之间的互操作性非常好。甚至可以创建混合项目，让 Kotlin 和 Java 文件共存。

然而，这只是冰山一角：

*   自 Kotlin 1.1 版本起，[Kotlin JS](https://kotlinlang.org/docs/reference/js-overview.html) 的最终版本已经发布。这个新变体允许你使用 Kotlin 开发 Web 应用。
*   自 Kotlin 1.2 版本起，你还可以创建[多平台项目](https://kotlinlang.org/docs/reference/whatsnew12.html#multiplatform-projects-experimental)。通过它，你可以在 JVM 和 Javascript 之间共享代码。
*   作为一项实验性特性，JetBrains 团队还发布了 [Kotlin/Native](https://kotlinlang.org/docs/reference/native-overview.html)，该项目终于让 Kotlin 脱离了 JVM。在未来，我们将能够使用 Kotlin 编写大部分代码来实现服务器、Web 以及 Android 和 iOS 应用。此外，你今天就可以尝试它。
*   Gradle 正在添加支持使用 Kotlin Script（Kotlin 的简化版本）来编写 Gradle 文件，而不是 Groovy。该项目正快速接近其 1.0 发布。

所以你可以看到，Kotlin 的未来非常有前景。学习 Kotlin 可能会成为许多其他平台的参考语言，而且在所有平台之间共享代码无疑是一个重大的卖点。

### 1.2 我们通过 Kotlin 得到了什么？

在不深入探究 Kotlin 语言的情况下（我们将在整本书中学习关于它的一切），这些是我们在 Java 中缺失的一些有趣特性：

#### 表现力

使用 Kotlin，要避免样板代码变得简单得多，因为语言默认涵盖了最常见的模式。例如，在 Java 中，如果我们想创建一个数据类，我们需要编写（或至少生成）以下代码：

```java
public class Artist {
    private long id;
    private String name;
    private String url;
    private String mbid;

    public long getId() {
        return id;
    }

    public void setId(long id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getUrl() {
        return url;
    }

    public void setUrl(String url) {
        this.url = url;
    }

    public String getMbid() {
        return mbid;
    }

    public void setMbid(String mbid) {
        this.mbid = mbid;
    }

    @Override public String toString() {
        return "Artist{" +
                "id=" + id +
                ", name='" + name + '\'' +
                ", url='" + url + '\'' +
                ", mbid='" + mbid + '\'' +
                '}';
    }
}
```

使用 Kotlin，你只需要利用数据类：

```kotlin
data class Artist(
    var id: Long,
    var name: String,
    var url: String,
    var mbid: String)
```

这个数据类会自动生成所有字段和属性访问器，以及一些实用的方法，如 `toString()`。

#### 空安全

当我们使用 Java 时，我们大量的代码都是防御性的。我们需要在使用某个东西之前检查一次它是否为空，以防止意外错误。Kotlin 像许多其他现代语言一样是空安全的，因为类型通过安全调用操作符（写作 `?`）显式地定义了对象是否可以为空。

我们可以像这样操作：

```kotlin
// 这无法编译。Artist 不可以为空
var notNullArtist: Artist = null

// Artist 可以为空
var artist: Artist? = null

// 将无法编译，artist 可能为空
artist.print()

// 仅在 artist != null 时打印
artist?.print()

// 智能转换。如果我们之前检查过空值，那么
// 就不需要使用安全调用操作符了
if (artist != null) {
    artist.print()
}

// 仅在在我们确定它不为空时使用它。否则将抛出异常。
artist!!.print()

// 使用 Elvis 操作符在对象为空时提供备选方案。
val name = artist?.name ?: "empty"
```

#### 扩展函数

多亏了扩展函数，你可以为任何类添加新函数。它是我们项目中常见的工具类更整洁的替代方案。例如，你可以为 fragment 添加一个新方法来显示 toast：

```kotlin
fun Fragment.toast(message: CharSequence, duration: Int = Toast.LENGTH_SHORT) {
    Toast.makeText(getActivity(), message, duration).show()
}
```

然后像这样使用它：

```kotlin
fragment.toast("Hello world!")
```

#### 函数式支持 (Lambdas)

如果我们不需要每次在实现点击监听器时声明一个匿名类，而是只需定义我们想做的事情会怎样？我们确实可以这样做。这（以及许多其他有趣的事情）正是得益于 lambda 得到的：

```kotlin
view.setOnClickListener { toast("Hello world!") }
```

这些特性只是 Kotlin 能够功能的一小部分。现在你已经知道了这种语言的许多优秀特性，你可能会决定这不适合你。如果你继续下去，我们将在下一章立即开始编写代码。

## 2 准备工作

既然你已经了解了一些可以用 Kotlin 实现的简单示例，我相信你想尽快开始付诸实践。别担心；前几个章节将帮助你配置开发环境，让你立即开始编写代码。

### 2.1 Android Studio

你需要的第一件事是安装 Android Studio。如你所知，Android Studio 是 Android 的官方 IDE，它于 2013 年作为预览版推出，并于 2014 年正式发布。

Android Studio 是 [IntelliJ IDEA](https://www.jetbrains.com/idea) 的插件实现的，后者是由 [Jetbrains](https://www.jetbrains.com) 创建的 Java IDE，而这家公司也是 Kotlin 的背后主使。所以，正如你看到的，一切都是紧密相连的。

Android Studio 的采用是 Android 开发者的一大进步。首先，我们告别了充满 Bug 的 Eclipse，转而使用了一套专为 Java 开发者设计的工具，这让我们能够与该语言进行深度交互。我们可以享受许多出色的功能，例如快速且令人惊讶的智能代码补全，以及强大的分析和重构工具等。

其次，[Gradle](https://gradle.org/) 成为了 Android 的官方构建系统，这意味着在版本控制、构建和部署方面出现了一系列全新的可能性。两个最令人兴奋的功能是构建类型（build types）和变体（flavors），它们让你在使用相同代码库的同时，以一种简单的方式创建无限版本的应用（甚至是不同的应用）。

如果你仍在使用 Eclipse，我恐怕如果你想跟进这本书，就必须切换到 Android Studio。Kotlin 团队正在为 Eclipse 创建插件，但它可能远落后于 Android Studio 插件，而且集成可能可能没那么顺畅。一旦你开始使用它，你就会发现自己错过了什么。

我没有涵盖 Android Studio 或 Gradle 的使用方法，因为这不是本书的重点。但如果你是第一次使用这些工具，我相信你仍然能够跟上内容，在此期间学习基础知识。

如果你还没有安装，请从[官方页面下载 Android Studio](https://developer.android.com/sdk/index.html)。

### 2.2 安装 Kotlin 插件

自 IntelliJ 15 发布以来，Kotlin 插件已捆绑在 IDE 中。对于 Android Studio，这取决于你使用的版本。

如果你拥有的是 Android Studio 3.0 或更高版本，你已经拥有了所需的一切。如果你的 Android Studio 是 2.3 或更低，你需要手动安装 Kotlin 插件。

因此，进入 `Android Studio Preferences` 内部插件（plugins）部分，安装 Kotlin 插件。如果找不到，请使用搜索工具。

现在，我们的环境已经准备好理解该语言、编译并执行它，就像我们使用 Java 一样无缝。

## 3 创建新项目

现在是时候开始创建我们的 App 了。我特意想让解释保持简单，因为 Android Studio 的向导程序（wizard）会经常变化，这些步骤很快就会过时。



我们的应用由一个简单的天气应用组成，类似于 [Udacity 上的 Google 初学者课程](https://www.udacity.com/course/android-development-for-beginners--ud837)中使用的那一个。我们将关注不同的点，但该应用的核心思想是相同的，因为它包含了许多你在普通应用中会发现的内容。如果你是刚开始 Android 开发，我向你推荐这门课程。

### 3.1 在 Android Studio 中创建新项目

同样，根据你所使用的 Android Studio 版本，会有细小的差别。

对于 Android Studio 3，步骤非常直观。之前的版本需要多做一点工作，但也远不复杂。即使你已经在使用新版本的 Android Studio，我也建议你查看一下整个过程，因为如果你想在 Java 项目上开始使用 Kotlin，这就是你需要的操作。

首先，打开 Android Studio 并选择 `Create New Project`（创建新项目）。第一步是为你的应用确定名称；你可以使用你喜欢的名称：例如 `WeatherApp`。然后向导程序会询问公司域名（Company Domain）。由于你并不发布该应用，这个字段也不太重要，但如果你拥有域名，可以使用它。此外，选择你想要保存项目的位置。

在 Android Studio 3 中，在此处，你会发现一个启用 Kotlin 支持的复选框。如果是你的情况，请勾选它。

下一步，向导程序询问最小 API 版本。我为示例应用选择了 API 15，但 Kotlin 对最小 API 没有任何限制。目前请跳过 `Phone and Tablet` 之外的任何平台。

最后，我们被要求选择一个活动模板。选择 `Empty Activity`（空活动）。此模板生成的代码很少，便于我们添加新逻辑。

保留下一个屏幕中活动或布局（布局）的名称。如果需要，我们稍后会更改它们。按下 `Finish`（完成）并让 Android Studio 完成工作。

使用 Android Studio 3，你就完成了，跳到第 3.4 点。接两个步骤仅在你必须手动安装插件时才需要。

### 3.2 将 MainActivity 转换为 Kotlin 代码

Kotlin 插件包含的一个有趣功能是可以将 Java 代码转换为 Kotlin 代码。作为一个自动化过程，它并不完美，但在你开始习惯 Kotlin 语言的前几天里，它可能会有很大帮助。

因此，我们在 `MainActivity.java` 类中使用此功能。打开文件并选择 `Code -> Convert Java File to Kotlin File`（代码 -> 将 Java 文件转换为 Kotlin 文件）。查看一下差异，以便你开始熟悉这种语言。

你也可以将任何 Java 代码复制到 Kotlin 文件中，插件也会进行转换。

### 3.3 在项目中配置 Kotlin

Kotlin 插件还包含一个工具，可以为我们配置 Gradle 文件。

进入 `Tools -> Project -> Configure Kotlin`。选择最新的 Kotlin 版本，并点击 OK。

检查更改。应该如下所示：

```
buildscript {
     ext.kotlin_version = '1.2.31'
     repositories {
         jcenter()
     }
     dependencies {
         classpath 'com.android.tools.build:gradle:3.1.0'
         classpath "org.jetbrains.kotlin:kotlin-gradle-plugin:$kotlin_version"
     }
}

allprojects {
    repositories {
        jcenter()
    }
}
```

`build.gradle`

你可以看到，它创建一个保存 Kotlin 版本的变量。我们在许多地方都需要该版本号，例如在 Kotlin 插件的新依赖中。

它在模块 `build.gradle` 中再次有用，该配置也添加了 Kotlin 标准库的依赖。现在去检查一下：

```
apply plugin: 'com.android.application'
apply plugin: 'kotlin-android'

android {
    ...
}

dependencies {
    implementation "org.jetbrains.kotlin:kotlin-stdlib:$kotlin_version"
}
```

`app/build.gradle`

### 3.4 引入其他有用配置

我们将使用一些其他额外的库，所以趁此将它们添加到 `build.gradle` 中。

一个重要的库是 Anko，它利用 Kotlin 的力量来简化 Android 中的某些任务。我们稍会使用更多 Anko 模块，但目前只需添加 `anko-common` 即可。该库被拆分为几个较小的库，以便我们只在项目中包含需要的部分。

```
buildscript {
    ext.support_version = '27.1.0'
    ext.kotlin_version = '1.2.31'
    ext.anko_version = '0.10.4'
    repositories {
        jcenter()
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:3.1.0'
        classpath "org.jetbrains.kotlin:kotlin-gradle-plugin:$kotlin_version"
    }
}

allprojects {
    repositories {
        jcenter()
        google()
    }
}
```

`build.gradle`

如果你正在使用 `Android Studio 2.3`，你还需要如上所示添加 Google 仓库。`Android Studio 3` 会自动为你完成这一操作。

接下来，我们在模块文件中添加 `Anko` 库依赖，更新 `AppCompat` 以使用我们的变量，并应用 `Kotlin Android Extensions` 插件：

```
apply plugin: 'com.android.application'
apply plugin: 'kotlin-android'
apply plugin: 'kotlin-android-extensions'

android {
    ...
}

dependencies {
    implementation "com.android.support:appcompat-v7:$support_version"
    implementation "org.jetbrains.kotlin:kotlin-stdlib:$kotlin_version"
    implementation "org.jetbrains.anko:anko-common:$anko_version"
}
```

`app/build.gradle`

通过这些更改，我们应该已经准备好开始了。

### 3.5 测试一切是否正常工作

我们将添加一些代码来检查 `Kotlin Android Extensions` 是否功能完整。我暂时还不对其进行详细解释，但我想确保它对你来说是可以工作的。

首先，进入 `activity_main.xml` 并为 `TextView` 设置一个 id：

```
<TextView
    android:id="@+id/message"
    android:text="@string/hello_world"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"/>
```

`activity_main.xml`

在 `onCreate` 中，尝试为 `TextView` 编写你之前选择的 id（在本例中为 `message`）：

```
override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    setContentView(R.layout.activity_main)
    message.text = "Hello Kotlin!"
}
```

`MainActivity.kt`

你看到魔法了吗？你不需要查找它或使用第三方库即可访问该视图。`Kotlin Android Extensions` 是包含在主 Kotlin 插件中的一个插件，这正是它的主要目的。请耐心等待，很快就会向你展示如何正确使用它。

你还会看到活动中自动添加了一个合成导入（synthetic import），但我们还没有介绍这部分：

```
import kotlinx.android.synthetic.main.activity_main.*
```

`MainActivity.kt`

得益于 Kotlin 与 Java 的互操作性，我们可以将 Java 库的 setter 和 getter 方法作为 Kotlin 中的属性使用。我们稍后也会讨论属性，但请注意我们可以免费地使用 `message.text` 而不是 `message.setText`。编译器使用真实的 Java 方法，因此在使用时没有性能开销。

现在运行应用并检查一切是否运行正常。检查消息的 `TextView` 是否显示了新内容。如果你有任何疑问或想修改某些代码，请查看 [Kotlin for Android Developers 仓库](https://github.com/antoniolg/Kotlin-for-Android-Developers/tree/chapter-3)。当新内容涉及代码修改时，我为每个章节创建了一个分支，因此请务必查看以检查所有更改。

接下来的章节将涵盖你在转换后的 `MainActivity` 中看到的一些新内容。一旦你理解了 Java 和 Kotlin 之间的细微差异，你就可以自己编写新代码而不会有任何困扰。

## 4 类和函数

Kotlin 中的类遵循直观的结构。然而，在我们继续之前，你可能想了解它与 Java 的的一些细微差异。你可以使用 [try.kotlinlang.org](http://try.kotlinlang.org/) 来测试此以及其他一些简单示例，而不需要真实的项目。

你还可以使用 Kotlin 插件附带的 REPL。你可以在 `Tools -> Kotlin -> Kotlin REPL` 中找到它。

### 4.1 如何声明一个类

如果你想声明一个类，只需要使用 `class` 关键字：

```
class MainActivity {
    
}
```

类有一个唯一的默认构造函数。我们将看到可以为某些特殊情况创建额外的构造函数，但请记住，大多数情况只需要一个构造函数。参数写在名称之后。如果类是空的，则不需要大括号：

```
class Person(name: String, surname: String) 
```

那么构造函数的体在哪里？你可以声明一个 `init` 块：

```
class Person(name: String, surname: String) {
    init {
        ...
    }
}
```

### 4.2 类继承

默认情况下，类总是继承自 `Any`（类似于 Java 的 `Object`），但我们可以扩展任何其他类。

```
class Animal {
    open fun makeSound() {
        println("Animal sound")
    }
}

class Dog : Animal() {
    override fun makeSound() {
        println("Bark")
    }
}
```

### 4.3 函数

Kotlin 中的函数使用 `fun` 关键字声明：

```kotlin
fun sum(a: Int, b: Int): Int {
    return a + b
}
```

`Unit` 类似于 Java 中的 `void`，用于不返回值的函数：

```kotlin
fun greet(): Unit {
    println("Hello, World!")
}
```

你也可以对简单函数使用表达式语法：

```kotlin
fun multiply(a: Int, b: Int) = a * b
```

### 4.4 构造函数和参数

Kotlin 中的参数与 Java 有不同。你可以直接在主构造函数中定义属性：

```kotlin
class User(val name: String, var age: Int)
```

参数的一个方便之处是我们可以通过指定**默认值**让它们变得可选：

```kotlin
fun toast(message: String, length: Int = Toast.LENGTH_SHORT) {
    Toast.makeText(this, message, length).show()
}
```

这允许你以不同的方式调用函数：

```
toast("Hello")
toast("Hello", Toast.LENGTH_LONG)
```

还有另一种选择，因为你可以使用**命名参数**，这意味着可以在值之前编写参数名称来指定你想要的哪一个：

```
toast(message = "Hello", length = Toast.LENGTH_SHORT)
```

## 5 编写你的第一个类

我们已经有了 `MainActivity.kt` 类。此活动将渲染未来七天的每日预报列表，因此布局需要一些更改。

### 5.1 创建布局

渲染预报列表的主视图将是一个 `RecyclerView`，因此需要一个新的依赖项。修改 `build.gradle` 文件：

```
1 dependencies {
2     compile fileTree(dir: 'libs', include: ['*.jar'])
3     compile "com.android.support:appcompat-v7:$support_version"
4     compile "com.android.support:recyclerview-v7:$support_version"
5     ...
6 }
```

`app/build.gradle`

现在，在 `activity_main.xml` 中：

```
 1 <FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
 2              android:layout_width="match_parent"
 3              android:layout_height="match_parent">
 4 
5     <android.support.v7.widget.RecyclerView
 6         android:id="@+id/forecast_list"
 7         android:layout_width="match_parent"
 8         android:layout_height="match_parent"/>
 9 
10 </FrameLayout>
```

`activity_main.xml`

在 `MainActivity.kt` 中，删除我们为了测试一切运行正常而添加的那行代码（现在它会显示错误）。目前我们将继续使用传统的 `findViewById()`：

```
1 val forecastList = findViewById(R.id.forecast_list) as RecyclerView
2 forecastList.layoutManager = LinearLayoutManager(this)
```

`MainActivity.kt`

如你所见，我们定义了变量并将其强制转换为 `RecyclerView`。这与 Java 有些不同；我们将在下一章中回顾这些差异。还指定了 `LayoutManager`，使用了属性命名而不是 setter 方法。对于这种布局，一个列表就足够了，所以让我们使用 `LinearLayoutManager`吧。

### 5.2 回收适配器 (Recycler Adapter)

我们需要为回收器创建一个适配器。我前段时间[在我的博客上讨论过 `RecyclerView`](http://antonioleiva.com/recyclerview/)，如果你不熟悉它，这可能对你有帮助。

目前用于 `RecyclerView` 适配器的视图将只是 `TextView`，以及我们手动创建的简单文本列表。添加名为 `ForecastListAdapter.kt` 的新 Kotlin 文件，并包含以下代码：



### 6. 变量与属性

在 Kotlin 中，**一切都是对象**。它与 Java 有一些不同：

#### 6.1 基本类型

数值类型之间没有自动转换。例如，从`Int`到`Double`：

```
val i = 7
val d = i.toDouble()
```

*   字符（`Char`）不能直接作为数字使用。但是，我们可以将其转换为：

```
val c = 'c'
val i = c.toInt()
```

*   位运算略有不同。在 Android 中，我们使用标志位`and`和`or`作为示例：

```
// Java
int bitwiseOr = FLAG1 | FLAG2;
int bitwiseAnd = FLAG1 & FLAG2;
```

```
// Kotlin
val bitwiseOr = FLAG1 or FLAG2
val bitwiseAnd = FLAG1 and FLAG2
```

*   字面量可以提供其类型信息。这不是强制的，但 Kotlin 的常见做法是省略变量类型，让它从字面量推断：

```
val i = 12 // 一个 Int
val iHex = 0x0f // 来自十六进制字面量的 Int
val l = 3L // 一个 Long
val d = 3.5 // 一个 Double
val f = 3.5F // 一个 Float
```

*   `String`可以像数组一样被访问并进行遍历：

```
val s = "Example"
val c = s[2] // 这是字符 'a'

// 遍历字符串
val s = "Example"
for (c in s) {
    print(c)
}
```

#### 6.2 不可变性

在 Kotlin 中，变量可以很容易地定义为可变的（`var`）或不可变的（`val`）。这种想法与 Java 变量中使用`final`非常相似。

不可变对象是在实例化后状态无法更改的对象。如果你需要修改后的版本，你需要创建一个新对象。不可变性使得软件更加健壮且可预测。在 Java 中，绝大多数对象都是可变的，这意味着访问该对象的任何部分都可以修改它，从而影响应用程序的其他部分。

不可变对象从定义上就是线程安全的。因为值是常量，所有线程始终获取相同的对象。

因此，如果我们想利用不可变性，我们在 Kotlin 中思考代码的方式会发生一些微变化。核心概念是：尽可能多使用`val`。在某些情况下（特别是在 Android 中，某些类的构造函数是由系统调用的），不可变性变得很难实现，但大多数情况下它是可以实现的。

之前提到的另一点是，我们通常可以避免指定对象类型，编译器会从值中推断，这使得代码更整洁，修改也更快。我们在上面的章节中已经有了一些示例。

```
1 val s = "Example" // 一个 String
2 val i = 23 // 一个 Int
3 val actionBar = supportActionBar // Activity 上下文中的一个 ActionBar
```

然而，如果我们想使用更通用的类型，则需要指定类型：

```
1 val a: Any = 23
2 val c: Context = activity
```

#### 6.3 属性（Properties）

属性等于 Java 中的字段（fields），但要强大得多。属性实现了字段加上 getter（get 器）和 setter（赋值）。让我们来看一个示例来对比差异。以下代码段显示了 Java 中安全访问和修改字段所需的代码：

```
 1 public class Person {
 2 
3     private String name;
 4 
 5     public String getName() {
 6         return name;
 7     }
 8 
 9     public void setName(String name) {
10         this.name = name;
11     }
12 }
13 
14 ...
15 
16 Person person = new Person();
17 person.setName("name");
18 String name = person.getName();
```

在 Kotlin 中，你只需要一个属性就能实现相同的行为：

```
 1 class Person {
 2     
 3     var name: String = ""
 4         
 5 }
 6 
 7 ...
 8  9 val person = Person()
10 person.name = "name"
11 val name = person.name
```

如果没有指定，属性将使用默认的 getter 和 setter。当然，可以它可以运行所需的任何自定义行为，而无需更改现有代码：

```
1 class Person {
2 
3     var name: String = ""
4         get() = field.toUpperCase()
5         set(value) {
6             field = "Name: $value"
7         }
8 
9 }
```

如果属性在自定义 getter 或 setter 中需要访问其值（如本例所示），则需要创建一个后台字段（backing field）。可以使用保留字`field`来访问它，当编译器发现需要它时，它会自动创建。请注意，如果我们直接使用属性，我们将使用 setter 和 getter，而不是进行直接赋值。你只能在属性的访问器内部使用后台字段。

正如在之前的某些章节中提到的，当处理用 Java 编写的代码时，Kotlin 允许在 Java 定义了 getter 以及可选的 setter 的地方使用属性语法。编译器只需链接到原始的 getter 和 setter，因此在使用这些映射属性时没有性能开销。

### 7 Anko 和扩展函数（Extension Functions）

Kotlin 团队开发了一些很棒的工具来让 Android 开发变得更容易。在本章中，我将向你介绍它们以及你如何开始使用它们。

#### 7.1 什么是 Anko？

[Anko](https://github.com/JetBrains/anko) 是由 JetBrains 开发的一个健壮的库。它的主要目的是通过使用代码而不是 XML 来生成 UI 布局。这个功能非常有趣；如果有机会，请尝试一下，但我不会在这个项目中使用它。对我来说（可能由于多年编写用户界面的经验）使用 XML 更加舒服，但你可能会有不同的想法。

然而，这并不是我们从这个库中可以获得的唯一功能。Anko 包含了许多有用的函数和属性，可以避免大量的样板代码。本书中涵盖了几个示例，但你很快就会看到这个库解决了哪种的问题。

由于 Anko 是一个专门为 Android 编写的库，理解它在背后做了什么是一个很好的练习。你可以随时使用`ctrl + click`（Windows 或 Linux）或`cmd + click`（Mac）导航到 Anko 的源码。Anko 的实现是学习如何充分利用 Kotlin 语言有用方法的极佳示例。

#### 7.2 开始使用 Anko

在继续之前，让我们使用 Anko 来改进几点。正如你将看到的，每当你使用 Anko 的任何东西时，它都会在文件中包含一个带有该属性或函数名称的导入。Anko 使用扩展函数为 Android 框架添加新功能，并且导入会链接到它们。我们将在正下方看到扩展函数是什么以及如何编写它。

在`MainActivity::onCreate`中，可以使用 Anko 扩展函数代替`findViewById`来查找`RecyclerView`。自 API 26 以来，这不再是必要的，因为`findViewById`现在是泛型的，但它仍然可以作为一个示例：

```
1 val forecastList: RecyclerView = find(R.id.forecast_list) 
```

`activities/MainActivity.kt`

看看导入部分，你会发现`find`函数被添加到了那里：

```
1 import org.jetbrains.anko.find
```

这些是我们目前能从库库使用的所有内容，但 Anko 可以帮助我们简化，包括 Intent 的实例化、Activity 之间的导航、Fragment 的创建、数据库访问或警框的构建。我们将在实现应用时看到。

#### 7.3 扩展函数

正如在之前的章节中提到的，当处理 Java 编写的代码时，Kotlin 允许在 Java 定义了 getter 以及可选 setter 的地方使用属性语法。编译器只需链接到原始的 getter 和 setter，因此在使用这些映射属性时没有性能惩罚。扩展函数是为类添加新行为的函数，即使我们无法访问其源代码。在 Java 中，我们通常在包含静态方法的工具类中实现它们。在 Kotlin 中使用扩展函数的优势是我们不需要将对象作为参数传递。扩展函数就像是类的一部分，我们可以通过`this`来实现它。

例如，我们可以创建一个`toast`函数，它可以被任何`Context`以及继承自`Context`的类型（如 Activity 或 Service）使用：

```
1 fun Context.toast(message: CharSequence, duration: Int = Toast.LENGTH_SHORT) {
2     Toast.makeText(this, message, duration).show()
3 }
```

现在你可以在 activity 中使用这个扩展，例如：

```
1 toast("Hello world!")
2 toast("Hello world!", Toast.LENGTH_LONG)
```

当然，Anko 已经包含了自己的自己的扩展函数，与这个非常相似。库提供了针对`CharSequence`和资源的函数，以及针对短长 toast 的不同名称：

```
1 toast("Hello world!")
2 longToast(R.string.hello_world)
```

扩展也可以是属性。因此你可以以非常的方式创建扩展属性。得益于下面的代码，你可以为`ViewGroup`添加一个额外的属性来获取其子视图列表：

```
1 val ViewGroup.childViews: List<View>
2     get() = (0 until childCount).map { getChildAt(it) }
```

先不要太关注实现，因为我们仍然需要涵盖这里的一些概念。扩展函数并没有修改原始类。你可能会发现在使用它的文件中添加了静态导入。你可以在任何地方声明扩展函数，因此常见的做法是创建包含一组相关函数的文件。扩展函数是许多 Anko 功能背后的魔法。从现在起，你也可以创建自己的魔法了。

本章没有太大变化；[你可以在这里找到源码](https://github.com/antoniolg/Kotlin-for-Android-Developers/tree/chapter-7)。

我们目前的占位符文本是了解我们想要目标的绝佳起点，但现在是时候请求真实数据了，这将用于填充`RecyclerView`。我们将利用 [OpenWeatherMap](http://openweathermap.org/) API 来获取数据，并使用一些普通类处理请求。由于 Kotlin 互操作非常强大，你可以使用任何需要的库，例如 [Retrofit](https://github.com/square/retrofit) 来进行服务器请求。然而，由于我们只是执行一个简单的 API 请求，无需添加另一个第三方库就可以更轻松地实现目标。

此外，正如你所看到的，Kotlin 提供了了一些扩展函数，让请求变得简单得多。首先，我们将创建一个新的`Request`类：

```
1 class Request(private val url: String) {
2 
3     fun run() {
4         val forecastJsonStr = URL(url).readText()
5         Log.d(javaClass.simpleName, forecastJsonStr)
6     }
7 
8 }
```

`data/Request.kt`

构造函数接收一个 URL。然后`run`函数读取结果并将 JSON 输出到 Logcat 中。

使用`readText`（Kotlin 标准库中的一个扩展函数）时实现非常直观。这种方法不建议用于大型响应，但在我们的情况下已经足够了。



如果你将此代码与 Java 中需要的代码进行比较，你会发现通过使用标准库我们节省了大量的开销。为了获得相同的结果，需要 `HttpURLConnection`、`BufferedReader` 以及对结果进行迭代，此外还需要管理连接和读取器的状态。显然，这就是该函数在后台执行的工作，但我们免费获得了。

为了能够执行请求，App 必须使用 Internet 权限。因此，必须将其添加到 `AndroidManifest.xml` 中：

```
<uses-permission android:name="android.permission.INTERNET" />
```

`AndroidManifest.xml`

## 8.2 在主线程之外执行请求

正如你所知的，主线程不允许 HTTP 请求，否则 App 将抛出异常。这种限制防止了阻塞 UI 线程，这是一种坏做法。Android 的标准解决方案是使用 `AsyncTask`。然而，这些类非常糟糕，而且很难在没有副作用的情况下实现。如果不小心使用 `AsyncTask` 是危险的，因为当到达 `postExecute` 时，系统可能已经销毁了 activity，导致任务崩溃。

Anko 提供了一个非常简单的 DSL 来处理异步操作，符合大多数基本需求。它提供了一个 `doAsync` 函数，在另一个线程中执行其代码，并可以选择调用 `uiThread` 返回主线程。在辅助线程中执行请求就像这样：

```
val url = "http://api.openweathermap.org/data/2.5/forecast/daily?" +
                 "APPID=15646a06818f61f7b8d7823ca833e1ce&zip=94043&mode=json&units=metric&cnt=7"

doAsync() {
    Request(url).run()
    uiThread { longToast("Request performed") }
}
```

`activities/MainActivity.kt`

你可以从[课程的仓库分支](https://github.com/antoniolg/Kotlin-for-Android-Developers/tree/chapter-8) 获取本课程所需的 url。

`uiThread` 的美妙之处在于它根据调用者对象有不同的实现。当 `Activity` 使用它时，如果 `activity.isFinishing()` 返回 `true`，则 `uiThread` 代码将不会执行，如果 activity 不再有效，它也不会崩溃。

你也可以使用自己的执行器：

```
val executor = Executors.newScheduledThreadPool(4)
doAsync(executor) {
    // Some task
}
```

`doAsync` 返回一个 Java `Future`，以防你想处理 future。如果你需要它返回一个带有结果的 `Future`，可以使用 `doAsyncResult`。

它比 `AsyncTask` 简单且易读。目前，我只是向请求发送了一个静态 URL，以测试我们是否能正确接收内容。

## 9 数据类

数据类是一种功能强大的类，通常提供 getter 和 setter。定义数据类非常简单，连同字段也是：

```kotlin
data class Forecast(val date: Date, val temperature: Float, val details: String)
```

### 9.1 额外函数

除了数据类，我们还免费获得了一些新函数：

*   `equals()`：它比较两个对象。
*   `hashCode()`：我们获得一个哈希码。
*   `copy()`：你可以复制一个对象并修改一个或多个属性。

### 9.2 复制数据类

如果我们像在某些章节中讨论的那样使用不可变性，则需要一个新的实例。例如，如果我们需要更改温度，只需这样做：

```kotlin
val f1 = Forecast(27.5f, "Shiny day")
val f2 = f1.copy(temperature = 30f)
```

通过这样，我们复制了第一个预测并仅修改了温度。

### 9.3 将对象映射到变量

这个过程被称为解构（destructuring），由将对象内部每个属性映射到一个变量组成。这就是为什么会自动创建 `componentX` 函数。使用之前的 `Forecast` 类的示例：

```kotlin
val f1 = Forecast(Date(), 27.5f, "Shiny day")
val (date, temperature, details) = f1
```

这种多声明被编译为以下代码：

```kotlin
val date = f1.component1()
val temperature = f1.component2()
val details = f1.component3()
```

该功能背后的逻辑非常强大，可以在许多情况下帮助简化代码。例如，`Map` 类实现了一些扩展函数，允许在迭代中恢复其键和值：

```
for ((key, value) in map) {
    Log.d("map", "key:$key, value:$value")
}
```

## 10 解析数据

现在我们已经知道如何创建数据类，已经准备好开始解析数据了。在 `data` 包中，创建一个名为 `ResponseClasses.kt` 的新文件。如果你在浏览器中打开我们在第 8 章中使用的 URL，就可以看到 JSON 文件的结构。它由一个包含城市和预测列表的对象组成。城市包含 ID、名称、坐标以及它所属的国家。每个预测都带有一组良好的信息，如日期、不同的温度以及一个包含描述和用于图标的 ID 的天气对象。

### 10.1 将 JSON 转换为数据类

在我们目前的 UI 中，我们不会使用所有这些数据。然而，我们将所有内容都解析为类，以防将来有用。这些是我们需要的数据类：

```kotlin
data class ForecastResult(val city: City, val list: List<Forecast>)
data class City(val id: Long, val name: String, val coord: Coordinates,
                val country: String, val population: Int)
data class Coordinates(val lon: Float, val lat: Float)
data class Forecast(val dt: Long, val temp: Temperature, val pressure: Float,
                    val humidity: Int, val weather: List<Weather>,
                    val speed: Float, val deg: Int, val clouds: Int,
                    val rain: Float)
data class Temperature(val day: Float, val min: Float, val max: Float,
                       val night: Float, val eve: Float, val morn: Float)
data class Weather(val id: Long, val main: String, val description: String,
                   icon: String)
```

`data/ResponseClasses.kt`

由于我们使用 [Gson](https://github.com/google/gson) 来将 JSON 解析到我们的类中，属性名称必须与 JSON 中的名称一致，或者指定一个序列化名称。大多数软件架构中解释的一种良好实践是为应用的不同层使用不同的模型，以便将它们解耦。因此，我倾向于简化这些类的声明，因为会在它们用于应用的其他部分之前对其进行转换。此类中使用的属性名称与 JSON 响应中的名称相同。

现在，`Request` 类需要一些修改以返回解析后的结果。它只接收城市的 `zipcode` 而不是完整的 URL，这样更具可读性。目前，静态 URL 定义在 `companion object` 中。

检查结果生成的代码：

```kotlin
class ForecastRequest(private val zipCode: String) {
    companion object {
        private const val APP_ID = "15646a06818f61f7b8d7823ca833e1ce"
        private const val URL = "http://api.openweathermap.org/data/2.5/" +
                "forecast/daily?mode=json&units=metric&cnt=7"
        private const val COMPLETE_URL = "$URL&APPID=$APP_ID&zip="
    }

    fun execute(): ForecastResult {
        val forecastJsonStr = URL(COMPLETE_URL + zipCode).readText()
        return Gson().fromJson(forecastJsonStr, ForecastResult::class.java)
    }
}
```

`data/ForecastRequest.kt`

记得你需要将 Gson 库添加到 `build.gradle` 依赖中：

```gradle
compile "com.google.code.gson:gson:2.8.1"
```

`app/build.gradle`

### 10.2 构建领域模型层

现在，让我们创建一个代表 `domain` 层的新包。它包含了一些负责执行应用用例的 `Command`。

首先，需要定义 `Command`。在下面的示例中有一个泛型声明。我们将在后续章节中讨论这个主题。

```kotlin
public interface Command<out T> {
    fun execute(): T
}
```

`domain/commands/Command.kt`

这些命令执行一个操作并返回其泛型类型中指定的类对象。记住 Kotlin 中的每个函数都会返回一个值。默认情况下，如果没有指定，它将返回 `Unit` 类的对象。因此，如果我们想让 `Command` 返回任何内容，可以指定 `Unit` 为其类型。

Kotlin 中的接口比 Java（Java 8 之前）更强大，因为它们可以包含代码。然而，目前我们不需要该功能。

第一个命令需要向 API 请求天气预报并将其转换为领域类。这是领域类的定义：

```kotlin
data class ForecastList(val city: String, val country: String, 
                        val dailyForecast:List<Forecast>)

data class Forecast(val date: String, val description: String, val high: Int, 
                    val low: Int)
```

`domain/model/DomainClasses.kt`

当我们以后添加更多功能时，这些类可能需要重新进行审查。目前，它们保留的数据已经足够。

类必须从数据层映射到领域模型，因此接下来的任务将是创建一个 `DataMapper`：

```kotlin
class ForecastDataMapper {
    fun convertFromDataModel(forecast: ForecastResult): ForecastList =
        ForecastList(forecast.city.name, forecast.city.country, 
            convertForecastListToDomain(forecast.list))

    private fun convertForecastListToDomain(list: List<Forecast>)
            : List<ModelForecast> {
        return list.mapIndexed { i, forecast ->
            val dt = Calendar.getInstance().timeInMillis + 
                TimeUnit.DAYS.toMillis(i.toLong())
            convertForecastItemToDomain(forecast.copy(dt = dt)) 
        }
    }

    private fun convertForecastItemToDomain(forecast: Forecast): ModelForecast {
        // 实现细节
    }

    private fun convertDate(date: Long): String {
        val df = DateFormat.getDateInstance(DateFormat.MEDIUM, Locale.getDefault())
        return df.format(date)
    }
}
```

`domain/mappers/ForecastDataMapper.kt`

### 10.3 在 UI 中绘制数据

`MainActivity` 代码发生了一点变化，因为现在我们有真实数据来填充适配器。异步调用需要重写：

```kotlin
doAsync() {
    val result = RequestForecastCommand("94043").execute()
    uiThread {
        forecastList.adapter = ForecastListAdapter(result)
    }
}
```

`ui/activities/MainActivity.kt`

适配器也需要一些修改：

```kotlin
class ForecastListAdapter(private val weekForecast: ForecastList) : 
        RecyclerView.Adapter<ForecastListAdapter.ViewHolder>() {

    override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): ViewHolder {
        return ViewHolder(TextView(parent.getContext()))
    }

    override fun onBindViewHolder(holder: ViewHolder, position: Int) {
        with(weekForecast.dailyForecast[position]) {
            holder.textView.text = "$date - $description - $high/$low"
        }
    }

    override fun getItemCount(): Int = weekForecast.dailyForecast.size

    class ViewHolder(val textView: TextView) : RecyclerView.ViewHolder(textView)
}
```

`ui/adapters/ForecastListAdapter.kt`

本章包含一些新代码，欢迎随时在[仓库](https://github.com/antoniolg/Kotlin-for-Android-Developers/tree/chapter-10)中查看。

## 11 运算符重载

Kotlin 允许我们在任何类中使用一组固定数量的符号运算符。这些符号映射到特定的函数，而该函数提供了运算符所使用的逻辑。通过重载这些运算符，可以提高你代码的可读性和简洁性。

若要通知编译器你想要重载某个运算符，必须使用 `operator` 修饰符对函数进行标记。

### 11.1 运算符列表

在这里，你可以看到一组表格，其中包含一个运算符及其对应的函数。必须实现一个同名的函数，才能在特定类中启用该运算符的使用。

#### 一元操作

| `+a` | `a.unaryPlus()` |
| :--- | :--- |
| `-a` | `a.unaryMinus()` |
| `!a` | `a.not()` |
| `a++` | `a.inc()` |
| `a–` | `a.dec()` |

#### 二元操作

| `a + b` | `a.plus(b)` |
| :--- | :--- |
| `a - b` | `a.minus(b)` |
| `a * b` | `a.times(b)` |
| `a / b` | `a.div(b)` |
| `a % b` | `a.mod(b)` |
| `a..b` | `a.rangeTo(b)` |
| `a in b` | `b.contains(a)` |



| `a !in b` | `!b.contains(a)` |

| `a += b` | `a.plusAssign(b)` |

| `a -= b` | `a.minusAssign(b)` |

| `a *= b` | `a.timesAssign(b)` |

| `a /= b` | `a.divAssign(b)` |

| `a %= b` | `a.modAssign(b)` |

#### 数组类操作

| `a[i]` | `a.get(i)` |

| :--- | :--- |

| `a[i, j]` | `a.get(i, j)` |

| `a[i_1, …, i_n]` | `a.get(i_1, …, i_n)` |

| `a[i] = b` | `a.set(i, b)` |

| `a[i, j] = b` | `a.set(i, j, b)` |

| `a[i_1, …, i_n] = b` | `a.set(i_1, …, i_n, b)` |

#### 等于操作

| `a == b` | `a?.equals(b) ?: b === null` |

| :--- | :--- |

| `a != b` | `!(a?.equals(b) ?: b === null)` |

`equals` 操作稍有不同，因为它们使用了更复杂的转换来执行正确的等性检查，并且它们期望精确的函数规范，而不仅仅是特定的名称。函数必须按照如下方式实现：

```
1 operator fun equals(other: Any?): Boolean
```

运算符 `===` 和 `!==` 执行身份检查（它们在 Java 中分别对应 `==` 和 `!=`）且不能重载。

#### 函数调用

| `a(i)` | `a.invoke(i)` |

| :--- | :--- |

| `a(i, j)` | `a.invoke(i, j)` |

| `a(i_1, …, i_n)` | `a.invoke(i_1, …, i_n)` |

### 11.2 示例

正如你所想象的，Kotlin 列表在标准库中实现了数组类操作，因此我们可以像访问 Java 数组一样访问列表项。但功能不止于此：在可变列表中，你还可以使用相同的运算符为某个位置赋值：

```
1 val x = myList[2]
2 myList[2] = 4
```

如果你还记得的话，我们有一个名为 `ForecastList` 的数据类，它由一个包含一些额外信息的列表组成。直接访问它的项，而不是请求其内部列表来获取项，将会很有趣。顺便提一下，我还将实现一个 `size` 属性，这会进一步简化当前的适配器：

```
1 data class ForecastList(val city: String, val country: String, 
2     private val dailyForecast: List<Forecast>) {
3     
4     val size: Int
5     get() = dailyForecast.size
6 
7     operator fun get(position: Int): Forecast = dailyForecast[position]
8 }
```

`domain/model/DomainClasses.kt`

这让我们的 `onBindViewHolder` 变得简单了一些：

```
1 override fun onBindViewHolder(holder: ViewHolder, position: Int) {
2     with(weekForecast[position]) {
3         holder.textView.text = "$date - $description - $high/$low"
4     }
5 }
```

`ui/adapters/ForecastListAdapter.kt`

以及 `getItemCount()` 函数：

```
1 override fun getItemCount(): Int = weekForecast.size
```

`ui/adapters/ForecastListAdapter.kt`

### 11.3 扩展函数

除了类类，我们还可以为第三方库的类提供扩展操作。例如，我们可以像访问列表一样访问 `ViewGroup`：

```kotlin
1 operator fun ViewGroup.get(position: Int): View
```

现在通过位置获取 `ViewGroup` 视图变得非常简单：

## 12 制作布局

布局需要一些工作才能准备就。首先是创建一个显示图标、日期、最高和最低温度的布局。对于 `forecast`：

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:gravity="center_vertical"
    android:orientation="horizontal">

    <ImageView
        android:id="@+id/icon"
        android:layout_width="48dp"
        android:layout_height="48dp"
        tools:src="@mipmap/launcher"/>

    <LinearLayout
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_weight="1"
        android:gravity="center_horizontal"
        android:orientation="vertical">

        <TextView
            android:id="@+id/date"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:textAppearance="@style/Medium"
            tools:text="May 14, 2015"/>

        <TextView
            android:id="@+id/description"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:textAppearance="@style/Caption"
            tools:text="Light Rain"/>
    </LinearLayout>

    <TextView
        android:id="@+id/maxTemperature"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textAppearance="@style/Medium"
        tools:text="30"/>

    <TextView
        android:id="@+id/minTemperature"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textAppearance="@style/Caption"
        tools:text="15"/>

</LinearLayout>
```

`layout/item_forecast.xml`

领域模型和数据映射器必须生成完整的图标 URL，以便我们可以加载它：

```kotlin
data class Forecast(val date: String, val description: String, 
                    val high: Int, val low: Int, val iconUrl: String)
```

`model/DomainClasses.kt`

在 `ForecastDataMapper` 中：

```kotlin
private fun convertForecastItemToDomain(forecast: Forecast): ModelForecast {
    return ModelForecast(convertDate(forecast.dt), 
            forecast.weather[0].description, forecast.temp.max.toInt(), 
            forecast.temp.min.toInt(), generateIconUrl(forecast.weather[0].icon))
}

private fun generateIconUrl(iconCode: String): String 
        = "http://openweathermap.org/img/w/$iconCode.png"
```

`domain/mappers/ForecastDataMapper.kt`

我们从第一个请求中获得的 `icon` 代码用于构建图标图像的完整 URL。加载图像最简单的方法是使用图像加载库。[Picasso](http://square.github.io/picasso/) 是一个极佳的选择。你必须将其添加到 `build.gradle` 依赖项中：

```
1 compile "com.squareup.picasso:picasso:2.5.2"
```

`app/build.gradle`

适配器也需要进行重构。一个点击监听器是必要的，让我们让我们定义它：

```
1 interface OnItemClickListener {
2      operator fun invoke(forecast: Forecast)
3 }
```

`ui/adapters/ForecastListAdapter.kt`

如果你还记得上节课的内容，调用它时可以省略 `invoke` 方法。所以让我们用它作为一种简化方式。监听器可以通过两种方式被调用：

```
1 itemClick.invoke(forecast)
2 itemClick(forecast)
```

`ViewHolder` 现在将负责将预报绑定到新视图：

```
 1 class ViewHolder(view: View, private val itemClick: OnItemClickListener)
 2     : RecyclerView.ViewHolder(view) {
 3 
 4     private val iconView = view.find<ImageView>(R.id.icon)
 5     private val dateView = view.find<TextView>(R.id.date)
 6     private val descriptionView = 
 7             view.find<TextView>(R.id.description)
 8     private val maxTemperatureView = 
 9             view.find<TextView>(R.id.maxTemperature)
10     private val minTemperatureView = 
 11             view.find<TextView>(R.id.minTemperature)
 12 
 13     fun bindForecast(forecast: Forecast) {
 14         with(forecast) {
 15             Picasso.with(itemView.ctx).load(iconUrl).into(iconView)
 16             dateView.text = date
 17             descriptionView.text = description
 18             maxTemperatureView.text = "$high"
 19             minTemperatureView.text = "$low"
 20             itemView.setOnClickListener { itemClick(this) }
 22         }
 22     }
 23 }
```

`ui/adapters/ForecastListAdapter.kt`

适配器的构造函数现在接收 `itemClick`。创建和绑定的方法变得更了：

```
 1 public class ForecastListAdapter(private val weekForecast: ForecastList, 
 2         private val itemClick: ForecastListAdapter.OnItemClickListener) :
 3         RecyclerView.Adapter<ForecastListAdapter.ViewHolder>() {
 4 
 5     override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): 
 6             ViewHolder {
 7         val view = LayoutInflater.from(parent.ctx)
 8             .inflate(R.layout.item_forecast, parent, false) 
 9 
10         return ViewHolder(view, itemClick)
 11     }
 12 
 13     override fun onBindViewHolder(holder: ViewHolder, position: Int) {
14         holder.bindForecast(weekForecast[position])
15     }
16     ...
17 }
```

`ui/adapters/ForecastListAdapter.kt`

如果你使用这段代码，`parent.ctx` 将无法编译。Anko 提供了许多扩展函数使 Android 编码更简单。例如，它包含了用于 activity 和 fragment 的 `ctx` 属性等，可以返回 context，但它缺少视图的相同属性。因此，我们将在 `ui.utils` 内部创建一个名为 `ViewExtensions.kt` 的新文件，并添加此扩展属性：

```
1 val View.ctx: Context
2     get() = context
```

从现在起，任何视图都可以使用它。这完全没有必要，因为你可以使用 `context` 合成属性，但我认为如果我们计划在其他类中使用 `ctx`，这样可以提供一些一致性。此外，这是如何使用扩展属性的另一个示例。

最后，`MainActivity` 调用 `setAdapter` 的结果如下：

```
1 forecastList.adapter = ForecastListAdapter(result,
2         object : ForecastListAdapter.OnItemClickListener{
3             override fun invoke(forecast: Forecast) {
4                 toast(forecast.date)
5             }
6         })
```

`ui/activities/MainActivity.kt`

如你所见，为了实现匿名类，我们实际上创建了一个实现我们所创建接口的 `object`。这是因为我们没有利用函数式编程的力量，但你将在下一章中学习如何将此代码转换为更整洁的内容。

尝试来自[仓库](https://github.com/antoniolg/Kotlin-for-Android-Developers/tree/chapter-12) 的新更改。

## 13 Lambda（ 表达式）

Lambda 表达式是定义匿名函数的简单方法。Lambda 非常有用，因为它们防止了我们要在抽象类或接口中编写函数规范，然后编写类的实现。

在 Kotlin 中，lambda 是一等公民，这意味着函数表现得像类型一样：它可以被作为参数传递给另一个函数，可以由函数返回，可以保存到变量或属性中等。

### 13.1 简化 setOnClickListener()

让我们通过 Android 中的一个典型示例来看它是如何工作的：来自 `View` 的点击监听器方法。如果我们想在 Java 中实现点击监听器行为，首先需要编写 `OnClickListener` 接口：



```java
interface OnClickListener {
    void onClick(View v);
}
```

然后编写一个实现该接口的匿名类：

```java
view.setOnClickListener(new OnClickListener() {
    @Override
    public void onClick(View v) {
        Toast.makeText(v.getContext(), "Click", Toast.LENGTH_SHORT).show();
    }
});
```

这是代码转换为 Kotlin（使用来自 Anko 的 `toast` 函数）：

```kotlin
view.setOnClickListener(object : OnClickListener {
    override fun onClick(v: View) {
        toast("Click")
    }
})
```

幸运的是，Kotlin 对此有一些优化，lambda 可以替代任何接收单个函数的接口。如果我们这样定义 `setOnClickListener()`：

```kotlin
fun setOnClickListener(listener: (View) -> Unit)
```

要定义 lambda 表达式，在箭头左侧（括号内）指定函数参数，在右侧指定类型。在这种情况下，我们得到 `View` 并返回 `Unit`（无）。所以根据此，我们可以简化之前的代码：

```kotlin
view.setOnClickListener({ view -> toast("Click")})
```

很棒的区别！在定义函数时，我们必须使用大括号并在左侧指定参数值，在右侧指定函数体。如果参数没有被使用，我们甚至可以去掉左部分：

```kotlin
view.setOnClickListener({ toast("Click") })
```

如果函数的最后一个参数也是函数，我们可以将其从括号中移出：

```kotlin
view.setOnClickListener() { toast("Click") }
```

最后，如果函数是唯一的参数，我们可以去掉括号：

```kotlin
view.setOnClickListener { toast("Click") }
```

比原始 Java 代码小了五倍以上，并且更容易理解在做什么。

## 13.2 ForecastListAdapter 的点击监听器

在上一节中，我故意用困难的方法编写点击监听器是为了为开发这一个提供良好的背景。但现在是时候付诸所学了。我们正在从 `ForecastListAdapter` 中移除监听器接口并改用 lambda：

```kotlin
public class ForecastListAdapter(private val weekForecast: ForecastList, 
                                 private val itemClick: (Forecast) -> Unit)
```

`ui/adapters/ForecastListAdapter.kt`

该函数将接收一个预报并不返回。相同的更改也可以对 `ViewHolder` 进行：

```kotlin
class ViewHolder(view: View, private val itemClick: (Forecast) -> Unit)
```

`ui/adapters/ForecastListAdapter.kt`

其余代码保持不变。只是对 `MainActivity` 的最后更改：

```kotlin
val adapter = ForecastListAdapter(result) { forecast -> toast(forecast.date) }
```

`ui/activities/MainActivity.kt`

我们可以进一步简化最后一行。在只有一个参数的 lambda 中，我们可以利用 `it` 引用，这避免了我们显式地定义函数的左部分。因此我们可以这样做：

```kotlin
val adapter = ForecastListAdapter(result) { toast(it.date) }
```

## 13.3 扩展语言

得益于这些转换，我们可以创建自己的构建器和代码块。我们已经在使用一些像 `with` 这样有趣的函数。虽然标准库中包含的稍微复杂一点，但更简单的实现如下：

```kotlin
inline fun <T> with(t: T, body: T.() -> Unit) { t.body() }
```

该函数接收一个类型为 `T` 的对象和一个行为类似于扩展函数的 lambda。实现过程接收该对象并允许执行该函数。由于函数的第二个参数是另一个函数，它可以提取到括号之外，因此我们可以创建一个代码块，在其中我们可以直接使用 `this` 以及该对象的公共属性和方法：

```kotlin
with(forecast) {
    Picasso.with(itemView.ctx).load(iconUrl).into(iconView)
    dateView.text = date
    descriptionView.text = description
    maxTemperatureView.text = "$high"
    minTemperatureView.text = "$low"
    itemView.setOnClickListener { itemClick(this) }
}
```

另一个例子：我们可以创建仅在版本为 Lollipop 或更高版本时才运行的代码块：

```kotlin
inline fun supportsLollipop(code: () -> Unit) {
    if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.LOLLIPOP) {
        code()
    }
}
```

函数体会检查版本，并在满足要求时执行代码。现在我们可以这样做：

```kotlin
supportsLollipop {
    window.setStatusBarColor(Color.BLACK)
}
```

例如，Anko 也是基于这个思想来实现 Android 布局 DSL 的。你也可以查看 Kotlin 参考中的一个示例，它展示了如何从代码中[生成 HTML](http://kotlinlang.org/docs/reference/type-safe-builders.html) 的 DSL。

本章的更改可以在[对应的分支中](https://github.com/antoniolg/Kotlin-for-Android-Developers/tree/chapter-13)找到。

## 14 可见性修饰符

Kotlin 中修饰符的使用与 Java 有不同。这种语言的默认修饰符是 `public`，这节省了大量的时间字符。这里是详细解释：可见性修饰符在 Kotlin 中是如何工作的？

### 14.1 修饰符

#### private

`private` 修饰符是我们可以使用的最严格限制。它表示在文件中可见。因此，如果我们将一个类声明为 `private`，则无法在定义它的文件之外使用它。

另一方面，如果在类内部使用 `private`，则访问被限制在该类内部。即使是扩展它的类也无法使用它。

因此，声明为 `private` 的第一级类、对象、接口……（称为包成员）仅在声明它们所在的文件内部可见，而定义在类或接口内部的所有内容仅对该类或该接口可见。

#### protected

此修饰符仅适用于类或接口的成员。包成员不能是 `protected`。在成员内部，它的工作方式与 Java 相同：它可以被成员本身以及扩展它的成员使用（例如类及其子类）。

#### internal

如果一个内部成员是包成员，则它在整个模块内可见。如果它是另一个作用域的成员，则取决于该作用域的可见性。例如，如果我们写了一个私有类，对 `internal` 函数的访问将限于该类的可见性。

我们可以从同一模块中的任何其他类使用 `internal` 类，但不能从另一个模块使用。

#### public

正如你所猜的，这是限制最少的修饰符。它是默认修饰符，声明为 `public` 的成员在任何地方可见，仅受其作用域限制。定义在私有类中的公共成员在类可见的作用域之外不可见。

### 14.2 构造函数

默认情况下，所有构造函数都是 `public` 的，这意味着可以在类可见的任何作用域中使用它们。如果我们想限制构造函数的可见性，可以使用这种特定语法对其应用修饰符：

```kotlin
class C private constructor(a: Int) { ... }
```

### 14.3 复习我们的代码

我们已经使用了默认的 `public` 修饰符，最新版本的 Kotlin 插件也会检测参数何时可以是私有的。例如，在 `RequestForecastCommand` 中，我们将 `zipCode` 属性设为了私有。

```kotlin
class RequestForecastCommand(private val zipCode: String)
```

此外，在 Kotlin 中，如果编译器可以推断，我们就不需要指定函数的返回类型。这是一个如何获取返回类型的示例：

```kotlin
data class(...) {
    operator fun get(position: Int)
}
```

## 15 Kotlin Extensions

**Kotlin Extensions** 是 Kotlin 团队开发的另一个插件，用于使 Android 开发更加简单。插件会自动创建属性，可以直接访问 XML 中的所有视图。它不需要添加库。

它在底层是如何工作的？这些属性委托给请求视图的函数以及一个防止每次使用属性时都执行 `findViewById` 的缓存函数。请注意，这种缓存机制在接收者为 Activity 或 Fragment 时有效。

### 15.1 如何使用 Kotlin Extensions

让我们看看有多简单。虽然该插件是常规的一部分（不需要安装新插件），但如果你想使用它，需要在 Android 模块中添加一个额外的 `apply`：

```gradle
apply plugin: 'com.android.application'
apply plugin: 'kotlin-android'
apply plugin: 'kotlin-android-extensions'
```

`app/build.gradle`

如果你记得的话，我们在书的开头已经这样做。

#### 从 XML 恢复视图

从现在起，恢复视图就像直接在活动中使用你在 XML 中定义的视图 ID 一样简单。假设你有一个像这样的 XML：

```xml
<FrameLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"

    <TextView
        android:id="@+id/welcomeMessage"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:text="Hello World!"/>

</FrameLayout>
```

如你所见，`TextView` 拥有 `welcomeMessage` ID。在 `MainActivity` 中，你现在可以写：

```kotlin
override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    setContentView(R.layout.activity_main)

    welcomeMessage.text = "Hello Kotlin!"
}
```

要使用它，你需要一个特殊的 `import`（就是我在下面写的这一个），但 IDE 可以为你写好 import：

```
import kotlinx.android.synthetic.main.activity_main.*
```

新的 Android Studio Activity 模板现在通过使用 `include` 标签包含了嵌套布局。重要的一点是，你必须为你使用的每个 XML 添加对应的合成导入（synthetic import）：

```
import kotlinx.android.synthetic.main.activity_main.*
import kotlinx.android.synthetic.main.content_main.*
```

正如我上面提到的，生成的代码包含一个视图缓存（view cache）。因此，如果你再次请求该视图，就不需要再次调用 `findViewById`。让我们来看看它在后台执行了什么。

### Kotlin Android 扩展背后的魔法

当你开始学习 Kotlin 时，理解在使用新特性时生成的字节码是有帮助的。这种做法有助于你理解所做决策背后的隐藏成本。

在 `Tools –> Kotlin` 下有一个操作叫做 `Show Kotlin Bytecode`（显示 Kotlin 字节码）。点击这里，你可以看到打开的类文件编译时生成的字节码。

字节码对大多数人类来说没有帮助，但这里还有另一个选项：`Decompile`（反编译）。

此部分显示了 Kotlin 生成的字节码的 Java 表示。这样，你就可以将 Java 等效代码与编写的 Kotlin 代码进行对比。

我将将其此于上一个示例 Activity，看看 Kotlin Android 扩展生成的代码。

有趣的部分是这一个：

```
...
public View _$_findCachedViewById(int var1) {
   if(this._$_findViewCache == null) {
      this._$_findViewCache = new HashMap();
   }

   View var2 = (View)this._$_findViewCache.get(Integer.valueOf(var1));
   if(var2 == null) {
      var2 = this.findViewById(var1);
      this._$_findViewCache.put(Integer.valueOf(var1), var2);
   }

   return var2;
}

public void _$_clearFindViewByIdCache() {
   if(this._$_findViewCache != null) {
      this._$_findViewCache.clear();
   }

}
```

这就是我们讨论过的视图缓存。当请求一个视图时，它会尝试在缓存中查找。如果那里没有，它会使用 `findViewById` 并将其添加到缓存中。确实非常简单。

此外，它还添加了一个清除缓存的函数：`clearFindViewByIdCache()`。你可以在重建视图时使用它，因为旧视图已经不再有效了。那么这一行：

```
welcomeMessage.text = "Hello Kotlin!"
```

被转换为：

```
((TextView)this._$_findCachedViewById(id.welcomeMessage))
    .setText((CharSequence)"Hello Kotlin!");
```

所以属性并不是真实的，插件并没有为每个视图生成属性。它在编译期间替换代码以访问视图缓存，将其转换为正确的类型并调用方法。

### Fragment 中的 Kotlin Android Extensions

Fragment 也可以使用这个插件。Fragment 的问题在于，视图可以在 Fragment 实例存活的同时重建。那时会发生什么？这意味着缓存中的视图将不再有效。

让我们看看使用 Fragment 时生成的代码。我正在创建这个简单的 Fragment，它使用了我上面写的同一个 XML：



```
class Fragment : Fragment() {

    override fun onCreateView(inflater: LayoutInflater, container: ViewGroup?, 
            savedInstanceState: Bundle?): View? {
        return inflater.inflate(R.layout.fragment, container, false)
    }

    override fun onViewCreated(view: View?, savedInstanceState: Bundle?) {
        super.onViewCreated(view, savedInstanceState)
        welcomeMessage.text = "Hello Kotlin!"
    }
}
```

在`onViewCreated`中，我更改了`TextView`的文本。生成的字节码呢？一切与 Activity 中一样，只有这个细微的区别：

```
// $FF: synthetic method
public void onDestroyView() {
   super.onDestroyView();
   this._$_clearFindViewByIdCache();
}
```

当视图销毁时，该方法会调用`clearFindViewByIdCache`，所以在这里是安全的。

### 自定义 View 中的 Kotlin Android extensions

在自定义 View 上的工作方式非常相似。假设我们有这样一个视图：

```
<merge xmlns:android="http://schemas.android.com/apk/res/android"
              android:orientation="vertical"
              android:layout_width="match_parent"
              android:layout_height="match_parent">

    <ImageView
        android:id="@+id/itemImage"
        android:layout_width="match_parent"
        android:layout_height="200dp"/>

    <TextView
        android:id="@+id/itemTitle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>

</merge>
```

```
class CustomView @JvmOver constructor(
        context: Context, attrs: AttributeSet? = null,
        defStyleAttr: Int = 0
) : LinearLayout(context, attrs, defStyleAttr) {

    init {
        LayoutInflater.from(context).inflate(R.layout.custom, this, true)
        itemTitle.text = "Hello Kotlin!"
    }
}
```

### 从另一个视图恢复视图

Kotlin Extensions 提供的另一种方案是从另一个视图使用属性。我正在使用一个与上一节非常相似的布局。假设它在适配器中加载。你也可以通过使用此插件直接访问子视图：

```
val itemView = ...
itemView.itemImage.setImageResource(R.drawable.image)
itemView.itemTitle.text = "My Text"
```

插件还会帮助你填充`import`。检查这一个不同：

```
import kotlinx.android.synthetic.main.view_item.view.*
```

关于这一点你需要了解几点：

* 在编译时，你可以从任何其他视图引用任何视图。这意味着你可能会引用一个并不是它的直接子元素的视图。当然，在运行时尝试恢复不存在的视图时会崩溃。

* 在这种情况下，视图是不被缓存的，这与`Activities`和`Fragments`不同。

此`experimental`标志意味着该 API 尚未完善，因此它在未来可能会发生。

### 在 ViewHolder（或任何自定义类）上的缓存

你现在可以以简单的方式在任何类上构建缓存。唯一的要求是你的类必须实现`LayoutContainer`接口。该接口提供了插件用于查找子视图的视图。假设我们有一个`ViewHolder`，它持有一个具有如之前示例中所示布局的视图。所需的代码如下：

```
class ViewHolder(override val containerView: View) 
        : RecyclerView.ViewHolder(containerView), LayoutContainer {

    fun bind(title: String) {
        itemTitle.text = "Hello Kotlin!"
    }
}
```

`containerView`是我们从`LayoutContainer`接口中重写的那个，这也就是你需要的全部。从现在起，你可以直接访问视图，不再需要在前面前加上`itemView`来获取对子视图的访问权限。

再次强调，如果你检查代码生成的内容，你会发现它正在从缓存中获取视图：

```
((TextView)this._$_findCachedViewById(id.itemTitle))
    .setText((CharSequence)"Hello Kotlin!");
```

我在这里一个`ViewHolder`上使用了它，但你可以看到它是足够通用的，可以用于任何类。

### 使用 Kotlin Android Extensions 实现 Parcelable

有了新的`@Parcelize`注解，你可以轻松地实现`Parcelable`。只需编写注解，插件就会完成所有繁琐的工作：

```
@Parcelize
class Model(val title: String, val amount: Int) : Parcelable
```

然后，正如你所知道的，你可以将对象添加到 intent 中：

```
val intent = Intent(this, DetailActivity::class.java)
intent.putExtra(DetailActivity.EXTRA, model)
startActivity(intent)
```

并在需要该对象的地方从 intent 中恢复它（在本例中，即在目标 activity 中）：

```
val model: Model = intent.getParcelableExtra(EXTRA)
```

### 自定义缓存构建

此实验性 set 包含的最后一个新功能是一个名为`@ContainerOptions`的新注解。它允许你自定义缓存的构建方式，甚至防止某个类创建缓存。

默认情况下，如我们之前所见，它使用`Hashmap`。这种行为可以更改为使用 Android 框架的`SparseArray`，这在某些情况下可能更高效。最后，如果由于某种原因你想禁用某个特定类的缓存，你也有该选项。

这里是更改缓存实现的一个示例：

```
@ContainerOptions(CacheImplementation.SPARSE_ARRAY)
class MainActivity : AppCompatActivity() {
    ...
}
```

目前，现有选项如下：

```
public enum class CacheImplementation {
    SPARSE_ARRAY,
    HASH_MAP,
    NO_CACHE;

    ...
}
```

现在你已经了 Kotlin Android Extensions 插件提供的所有功能。现在，让我们在代码中使用其中一些功能吧。

### 15.3 重构我们的代码

为了开始使用 Kotlin Android Extensions，我们对示例应用进行的修改非常简单。

让我们从`MainActivity`开始。我们目前只使用了一个`forecast_list`视图，它是`RecyclerView`的实例。让我们清理一下这段代码。

如所述，我们使用`id`来访问视图，因此我更改了`RecyclerView`的`id`，使其不再使用下划线，而是使用符合 Kotlin 变量规范的名称。XML 现在看起来如下：

```
<FrameLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <android.support.v7.widget.RecyclerView
        android:id="@+id/forecastList"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>

</FrameLayout>
```

`layout/activity_main.xml`

现在我们只需要去掉`find`那行了。开始编写视图的 id，自动补全就会帮助你添加导入。否则，你需要添加这个：

```
import kotlinx.android.synthetic.main.activity_main.*
```

`ui/activities/MainActivity.kt`

这是最终生成的代码：

```
override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    setContentView(R.layout.activity_main)

    forecastList.layoutManager = LinearLayoutManager(this)
    ...
}
```

`ui/activities/MainActivity.kt`

改进并不大，因为这个布局只有一个视图。但`ForecastListAdapter`也可以从该插件中受益。在这里，我们可以使用该机制将属性绑定到视图中，这将帮助我们移除`ViewHolder`内部所有的`find`代码。

这是为`item_forecast`需要的合成导入：

```
import kotlinx.android.synthetic.main.item_forecast.view.*
```

`ui/adapters/ForecastListAdapter.kt`

现在我们可以在`ViewHolder`内部通过`itemView`属性找到视图。正如我之前提到的，你可以通过`itemView`使用属性，但如果视图不包含请求的视图，将会崩溃。

为了解决这个问题，可以使用 Kotlin 1.1.4 中的新功能。首先，在`build.gradle`中启用`experimental`标志：

```
androidExtensions {
    experimental = true
}
```

`app/build.gradle`

现在更新`ViewHolder`。你不再需要通过`itemView`访问视图，因为现在视图表现为`ViewHolder`的属性。检查导入是否不同：

```
import kotlinx.android.synthetic.main.item_forecast.*

class ForecastListAdapter(private val weekForecast: ForecastList,
        private val itemClick: (Forecast) -> Unit) :
        RecyclerView.Adapter<ForecastListAdapter.ViewHolder>() {

    ...

    class ViewHolder(override val containerView: View, 
         private val itemClick: (Forecast) -> Unit)
        : RecyclerView.ViewHolder(containerView), LayoutContainer {

        fun bindForecast(forecast: Forecast) {
            with(forecast) {
                Picasso.with(itemView.ctx).load(iconUrl).into(icon)
                dateText.text = date
                descriptionText.text = description
                maxTemperature.text = "${high}º"
                minTemperature.text = "${low}º"
                itemView.setOnClickListener { itemClick(this) }
            }
        }
    }
}
```

`ui/adapters/ForecastListAdapter.kt`

我们的布局非常简单，不会影响性能。无论如何，请记住我们在上面节中讨论过的内容：这并没有缓存视图，这意味着每次调用`bind`函数在底层都会为它的视图执行`findViewById`。

我在 XML 中也做了更改，以便视图的名称与`Forecast`中的属性不同。否则在引用它们时将会出现问题。

```
<TextView
    android:id="@+id/dateText"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:textAppearance="@style/TextAppearance.AppCompat.Medium"
    tools:text="May 14, 2015"/>

<TextView
    android:id="@+id/descriptionText"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:textAppearance="@style/TextAppearance.AppCompat.Caption"
    tools:text="Light Rain"/>
```

`layout/item_forecast.xml`

我们的应用现在使用 Kotlin Android Extensions 来查找视图。运行它并检查一切运行是否符合预期。

Kotlin Android Extensions 插件帮助我们减少了一些样板代码，并尽可能减少访问视图所需的代码。在[仓库中](https://github.com/antoniolg/Kotlin-for-Android-Developers/tree/chapter-15)查看最新更改。

## 16 应用单例与委托属性

我们很快就要实现一个数据库，如果想保持代码简单并让应用处于独立的层级中（而不是将所有内容都添加到 activity 中），我们需要更方便地访问应用上下文（application context）。

### 16.1 应用单例

最简单的方法是像在 Java 中那样创建一个单例：

```
class App : Application() {

    companion object {
        private var instance: Application? = null
        fun instance() = instance!!
    }

    override fun onCreate() {
        super.onCreate()
        instance = this
    }
}
```

`ui/App.kt`

记住你需要将此`App`类添加到`AndroidManifest.xml`中以便作为应用实例使用：



进入`/path/to/xxx`目录，找到`xxx.json`。

在表达式`cvar = avar + bvar`中，加法运算符（`+`）将`avar`与`bvar`相加，得到它们的和`cvar`

在`List.of(arg0, arg1, arg2)`中，`List`接口的工厂方法`of()`接受一系列的元素，返回包含它们的只读列表。

之后我们这样调用`cmd`命令：`cmd arg0 arg1 arg2`。

```
if (condVar > someVal) {console.log("xxx")}
```



```
1 companion object {
2     const val DB_NAME = "forecast.db"
3     const val DB_VERSION = 1
4     val instance by lazy { ForecastDbHelper() }
5 }
```

`data/db/ForecastDbHelper.kt`

`instance` 属性使用了 `lazy` 委托，这意味着该对象在第一次使用之前才不会被创建。这样，如果数据库从未被使用，我们就可以避免创建必要的对象。普通的 `lazy` 委托是阻塞的，以防止从不同线程创建多个实例。这种情况只在两个线程同时尝试访问 `instance` 时才会发生，这虽然很难，但取决于你正在实现的应用程序类型，可能会发生。

为了创建数据库架构，我们需要提供 `onCreate` 函数的实现。在不使用任何库的情况下，表的创建是通过编写原始的 `CREATE TABLE` 查询完成的，我们在其中定义了所有的列及其类型。然而，Anko 提供了一个简单的扩展函数，它接收表名和一组 `Pair` 对象，这些对象用于标识列的名称和类型：

```
1 db.createTable(CityForecastTable.NAME, true,
2         Pair(CityForecastTable.ID, INTEGER + PRIMARY_KEY),
3         Pair(CityForecastTable.CITY, TEXT),
4         Pair(CityForecastTable.COUNTRY, TEXT))
```

`data/db/ForecastDbHelper.kt`

- 第一个参数是表名。
- 第二个参数当设置为 `true` 时，会在尝试创建表之前检查该表是否存在。
- 第三个参数是 `Pair` 的 `vararg` 参数。`vararg` 类型在 Java 中也存在，它是向函数传递相同类型变数量参数的方法。该函数随后接收一个包含这些对象的数组。

列类型使用了一个名为 `SqlType` 的特殊 Anko 类，它可以与 `SqlTypeModifier`（如 `PRIMARY_KEY`）一起使用。`+` 操作的重载方式我们在第 11 节中看到过。这个 `plus` 函数正确地连接了两个值并返回一个新的特殊的 `SqlType`：

```
1 fun SqlType.plus(m: SqlTypeModifier) : SqlType {
2     return SqlTypeImpl(name, if (modifier == null) m.toString() 
3             else "$modifier $m")
4 }
```

如你所示，它还可以连接多个修改器。

回到我们的代码，我们可以做得更好。Kotlin 标准库包含一个名为 `to` 的函数，它再次展示了 Kotlin 让我们根据需求对语言建模的能力。它作为第一个对象的扩展函数并接收另一个对象作为参数，返回一个包含它们的 `Pair` 对象。

```
1 infix fun <A, B> A.to(that: B): Pair<A, B> = Pair(this, that)
```

使用 `infix` 修饰符的单参数函数可以内联使用，因此结果非常整洁：

```
1 val pair = object1 to object2
```

将此应用到我们表的创建中：

```
1 db.createTable(CityForecastTable.NAME, true,
2         CityForecastTable.ID to INTEGER + PRIMARY_KEY,
3         CityForecastTable.CITY to TEXT,
4         CityForecastTable.COUNTRY to TEXT)
```

这是完整方法的写法：

```
 1 override fun onCreate(db: SQLiteDatabase) {
 2     db.createTable(CityForecastTable.NAME, true,
 3             CityForecastTable.ID to INTEGER + PRIMARY_KEY,
 4             CityForecastTable.CITY to TEXT,
 5             CityForecastTable.COUNTRY to TEXT)
 6 
 7     db.createTable(DayForecastTable.NAME, true,
 8             DayForecastTable.ID to INTEGER + PRIMARY_KEY + AUTOINCREMENT,
 9             DayForecastTable.DATE to INTEGER,
10             DayForecastTable.DESCRIPTION to TEXT,
11             DayForecastTable.HIGH to INTEGER,
12             DayForecastTable.LOW to INTEGER,
13             DayForecastTable.ICON_URL to TEXT,
14             DayForecastTable.CITY_ID to INTEGER)
15 }
```

`data/db/ForecastDbHelper.kt`

我们有一个类似的用于删除表的函数。`onUpgrade` 只是删除表以便它们重新创建。我们只是将数据库用作缓存，所以我们需要根据数据库版本改进 `onUpgrade`：

```
1 override fun onUpgrade(db: SQLiteDatabase, oldVersion: Int, newVersion: Int) {
2     db.dropTable(CityForecastTable.NAME)
3     db.dropTable(DayForecastTable.NAME)
4 }
```

### 17.4 依赖注入

如果你还记得，Anko 被分为几个库以变得更加轻量化。我们已经添加了 `anko-common`，但如果我们想使用数据库功能，我们还需要 `anko-sqlite`：

简单来说，如果我们想让类之间相互独立、可测试，并编写出易于扩展的代码，我们需要利用依赖反转。我们不再在类内部实例化协作对象，而是提供它们（通常通过构造函数），并在类的其他处实例化它们。这样，我们就可以用其他对象来替换它们，例如实现相同接口的对象，或者在测试中使用 mock（模拟对象）。

然而，现在这些依赖必须从某个地方提供，因此依赖注入就由提供类所需的协作对象。开发者通常将此项任务委托给依赖注入器。[Dagger](https://google[github.io/dagger/) 可能是 Android 上最著名的依赖注入器。当我们需要某些复杂性来提供这些依赖时，它无疑是一个极好的替代方案。

但更简单的替代方案是利用构造函数中的默认值。我们可以通过为构造函数参数分配默认值来提供依赖，然后在需要时提供不同的实例。例如，在我们的 `ForecastDbHelper` 中，我们可以以更智能的方式提供上下文：

```
1 class ForecastDbHelper(ctx: Context = App.instance) : 
2     ManagedSQLiteOpenHelper(ctx, ForecastDbHelper.DB_NAME, null, 
3     ForecastDbHelper.DB_VERSION) {
4     ...
5 }
```

现在我们有两种方法创建这个类：

```
1 val dbHelper1 = ForecastDbHelper()  // 它将使用 App.instance
2 val dbHelper2 = ForecastDbHelper(mockedContext) // 例如为了测试
```

我们之前在项目中项目中使用过集合（collections），但现在是时候展示它们在结合函数式操作时有多强大了。函数式编程的好处在于，我们不需要解释“如何”做”，只需要说明我们“想要做什么”。例如，如果我们想过滤一个列表，与其创建一个新列表、遍历原始列表并将满足条件的项添加到新列表中，我们只需使用一个 `filter` 函数并指定我们想要使用的过滤器即可。这样一来，我们就可以用更少的代码实现更多的功能。

虽然我们可以使用 Java 集合，但 Kotlin 提供了一组非常好的原生接口，你可能会想要使用它们：

- `Iterable`：父类。任何继承此接口的类都代表一个我们可以迭代的元素序列。
- `MutableIterable`：支持在迭代过程中删除项的可迭代对象。
- `Collection`：此类表示元素的泛型集合集合。我们可以访问返回集合大小、判断集合是否为空、是否包含某个元素或一组元素的函数。此类集合的所有方法都仅用于请求数据，因为集合是不可变的。
- `MutableCollection`：一种支持添加和删除元素的 `Collection`。它提供了额外的函数，如 `add`、`remove` 或 `clear` 等。
- `List`：可能是最流行的集合类型。它表示元素的泛型有序集合。由于它是有序的，我们可以通过 `get` 函数根据位置请求某个项。
- `MutableList`：一种支持添加和删除元素的 `List`。
- `Set`：一种无序元素集合，会忽略重复元素。
- `MutableSet`：一种支持添加和删除元素的 `Set`。
- `Map`：一种键值对集合。map 中的键必须是唯一的，这意味着在 map 中不能有两个具有相同键的对。
- `MutableMap`：一种支持添加和删除元素的 `Map`。

这些集合可以应用一组函数式操作。我想向你展示一些定义以及几种操作的示例。了解有哪些选项是有用的，这样可以更容易识别这些函数可以使用哪些地方。

## 18.1 聚合操作 (Aggregate operations)

#### any

如果至少有一个元素匹配给定的谓词，则返回 `true`。

```
1 val list = listOf(1, 2, 3, 4, 5, 6)
2 assertTrue(list.any { it % 2 == 0 })
3 assertFalse(list.any { it > 10 })
```

#### all

如果所有元素都匹配给定的谓词，则返回 `true`。

```
1 assertTrue(list.all { it < 10 })
2 assertFalse(list.all { it % 2 == 0 })
```

#### count

返回匹配给定的谓词的元素数量。

```
1 assertEquals(3, list.count { it % 2 == 0 })
```

#### fold

从初始值开始，对集合从第一个元素到最后一个元素应用操作来累加值。

```
1 assertEquals(25, list.fold(4) { total, next -> total + next })
```

#### foldRight

与 `fold` 相同，但它是从最后一个元素到第一个元素。

```
1 assertEquals(25, list.foldRight(4) { total, next -> total + next })
```

#### forEach

对每个元素执行给定的操作。

```
1 list.forEach { println(it) }
```

#### forEachIndexed

与 `forEach` 相同，尽管我们还得到了元素的索引。

```
1 list.forEachIndexed { index, value 
2        -> println("position $index contains a $value") }
```

#### max

返回最大的元素，如果没有元素则返回 `null`。

```
1 assertEquals(6, list.max())
```

#### maxBy

返回由给定函数产生最大值的第一个元素，如果没有元素则返回 `null`。

```
1 // 负值更大的那个元素
2 assertEquals(1, list.maxBy { -it })
```

#### min

返回最小的元素，如果没有元素则返回 `null`。

```
1 assertEquals(1, list.min())
```

#### minBy

返回由给定函数产生最小值的第一个元素，如果没有元素则返回 `null`。

```
1 // 负值更小的元素
2 assertEquals(6, list.minBy { -it })
```

#### none

如果没有元素匹配给定的谓词，则返回 `true`。

```
1 // 没有元素能被 7 整除
2 assertTrue(list.none { it % 7 == 0 })
```

#### reduce

与 `fold` 相同，但它不使用初始值。它对集合从第一个元素到最后一个元素应用操作来累加值。

```
1 assertEquals(21, list.reduce { total, next -> total + next })
```

#### reduceRight

与 `reduce` 相同，但它是从最后一个元素到第一个元素。

```
1 assertEquals(21, list.reduceRight { total, next -> total + next })
```

#### sumBy

返回由转换函数从集合元素中产生的所有值之和。

```
1 assertEquals(3, list.sumBy { it % 2 })
```

### 18.2 过滤操作 (Filtering operations)

#### drop

返回一个包含除前 n 个元素以外的所有元素的列表。

```
1 assertEquals(listOf(5, 6), list.drop(4))
```

#### dropWhile

返回一个包含除满足条件的元素以外的列表（注：此处原文描述可能有误，按逻辑翻译）。

```
1 assertEquals(listOf(5, 6), list.dropWhile { it < 5 })
```

#### dropLast

返回一个包含除最后 n 个元素以外的所有元素的列表。

```
1 assertEquals(listOf(1, 2, 3, 4), list.dropLast(2))
```

#### filter

返回一个包含匹配给定谓词元素的列表。

```
1 assertEquals(listOf(2, 4, 6), list.filter { it % 2 == 0 })
```

#### filterNot

返回一个包含不匹配给定谓词元素的列表。

```
1 assertEquals(listOf(1, 3, 5), list.filterNot { it % 2 == 0 })
```

#### filterNotNull

返回一个包含所有非 `null` 元素的列表。

```
1 listWithNull = listOf(1, null, 2, 3, 4)
2 assertEquals(listOf(2, 3, 4), listWithNull.filterNotNull())
```

#### slice

返回包含指定索引元素的列表。

```
1 assertEquals(listOf(2, 4, 5), list.slice(listOf(1, 3, 4)))
```

#### take

返回包含前 n 个元素的列表。

```
1 assertEquals(listOf(1, 2), list.take(2))
```

#### takeLast

返回包含最后 n 个元素的列表。

```
1 assertEquals(listOf(5, 6), list.takeLast(2))
```

#### takeWhile

返回包含满足给定谓词的前元素列表。

```
1 assertEquals(listOf(1, 2, 3), list.takeWhile { it < 4 })
```

### 18.3 映射操作 (Mapping operations)

#### flatMap

遍历元素并为每个元素创建一个新集合，最后将所有集合平化为一个列表。

```
1 assertEquals(listOf(1, 2, 2, 3, 3, 4, 4, 5, 5, 6, 6, 7), 
             list.flatMap { listOf(it, it + 1) })
```

#### groupBy

根据给定函数的结果对原始集合中的元素分组返回 map。

```
1 assertEquals(mapOf("odd" to listOf(1, 3, 5), "even" to listOf(2, 4, 6)),
             list.groupBy { if (it % 2 == 0) "even" else "odd" })
```

#### map

返回一个将转换函数应用于原始集合每个元素结果的列表。

```
1 assertEquals(listOf(2, 4, 6, 8, 10, 12), list.map { it * 2 })
```

#### mapIndexed

返回一个将转换函数应用于原始集合每个元素及其索引结果的列表。

```
1 assertEquals(listOf(0, 2, 6, 12, 20, 30), list.mapIndexed { index, it 
         -> index * it })
```

#### mapNotNull

返回一个将转换函数应用于原始集合中每个非 `null` 元素的列表。



```
1 listWithNull = listOf(1, null, 2, 3, 4)
2 assertEquals(listOf(2, 4, 6, 8), listWithNull.mapNotNull { it * 2 })
```

## 18.4 元素操作 (Elements operations)

### contains

如果在集合中找到了该元素，则返回 `true`。

```
1 assertTrue(list.contains(2))
```

### elementAt

返回给定索引处的元素，如果索引超出此集合范围，则抛出 `IndexOutOfBoundsException`。

```
1 assertEquals(2, list.elementAt(1))
```

### elementAtOrElse

返回指定索引处的元素；如果索引超出此集合的范围，则返回默认函数的执行。

```
1 assertEquals(20, list.elementAtOrElse(10, { 2 * it }))
```

### elementAtOrNull

返回指定索引处的元素；如果索引超出此集合的范围，则返回 `null`。

```
1 assertNull(list.elementAtOrNull(10))
```

### first

返回匹配给定谓词的第一个元素。如果没有找到元素，将抛出 `NoSuchElementException`。

```
1 assertEquals(2, list.first { it % 2 == 0 })
```

### firstOrNull

返回匹配给定谓词的第一个元素；如果没有找到任何元素，则返回 `null`。

```
1 assertNull(list.firstOrNull { it % 7 == 0 })
```

### indexOf

返回元素的第一个索引；如果集合不包含该元素，则返回 -1。

```
1 assertEquals(3, list.indexOf(4))
```

### indexOfFirst

返回匹配给定谓词的第一个元素的索引；如果集合不包含此类元素，则返回 -1。

```
1 assertEquals(1, list.indexOfFirst { it % 2 == 0 })
```

### indexOfLast

返回匹配给定谓词的最后一个元素的索引；如果集合不包含此类元素，则返回 -1。

```
1 assertEquals(5, list.indexOfLast { it % 2 == 0 })
```

### last

返回匹配给定谓词的最后一个元素。如果没有找到元素，将抛出 `NoSuchElementException`。

```
1 assertEquals(6, list.last { it % 2 == 0 })
```

### lastIndexOf

返回元素的最后一个索引；如果集合不包含该元素，则返回 -1。

```
1 val listRepeated = listOf(2, 2, 3, 4, 5, 5, 6)
2 assertEquals(5, listRepeated.lastIndexOf(5))
```

### lastOrNull

返回匹配给定谓词的最后一个元素；如果没有找到此类元素，则返回 `null`。

```
1 val list = listOf(1, 2, 3, 4, 5, 6)
2 assertNull(list.lastOrNull { it % 7 == 0 })
```

### single

返回匹配给定谓词的唯一元素；如果没有元素或有多个匹配元素，则抛出异常。

```
1 assertEquals(5, list.single { it % 5 == 0 })
```

### singleOrNull

返回匹配给定谓词的唯一元素；如果未找到元素或找到了多个元素，则返回 `null`。

```
1 assertNull(list.singleOrNull { it % 7 == 0 })
```

## 18.5 生成操作

### merge

使用提供的转换函数，根据两个集合中具有相同索引的元素构建一个值列表。该列表的长度为最短集合的长度。

```
1 val list = listOf(1, 2, 3, 4, 5, 6)
2 val listRepeated = listOf(2, 2, 3, 4, 5, 5, 6)
3 assertEquals(listOf(3, 4, 6, 8, 10, 11), list.merge(listRepeated) { it1, it2 -> 
4         it1 + it2 })
```

### partition

将原始集合拆分为一对集合，其中第一个集合包含谓词返回 `true` 的元素，而第二个集合包含谓词返回 `false` 的元素。

```
1 assertEquals(Pair(listOf(2, 4, 6), listOf(1, 3, 5)), 
2         list.partition { it % 2 == 0 })
```

### plus

返回一个包含原始集合所有元素以及给定集合所有元素的列表。由于该函数的名称，我们可以对它使用 `+` 运算符。

```
1 assertEquals(listOf(1, 2, 3, 4, 5, 6, 7, 8), list + listOf(7, 8))
```

### zip

返回一个由两个集合中相同索引元素构建的对列表。该列表的长度为最短集合的长度。

```
1 assertEquals(listOf(Pair(1, 7), Pair(2, 8)), list.zip(listOf(7, 8)))
```

### unzip

从 `Pair` 列表生成 `List` 的 `Pair`。

```
1 assertEquals(Pair(listOf(5, 6), listOf(7, 8)), listOf(Pair(5, 7), Pair(6, 8)).unzip())
```

## 18.6 排序操作

### reverse

返回一个元素反序的列表。

```
1 val unsortedList = listOf(3, 2, 7, 5)
2 assertEquals(listOf(5, 7, 2, 3), unsortedList.reverse())
```

### sort

返回一个所有元素排序后的列表。

```
1 assertEquals(listOf(2, 3, 5, 7), unsortedList.sort())
```

### sortBy

返回一个按指定比较器排序的所有元素列表。

```
1 assertEquals(listOf(3, 7), unsortedList.sortBy)
```

### sortDescending

返回一个按降序排序的所有元素列表。

```
1 assertEquals(listOf(7, 5), unsortedList.sortDescending())
```

### sortDescendingBy

返回一个按指定比较器降序排序的所有元素列表。

```
1 assertEquals(listOf(7, 5), unsortedList.sortDescendingBy)
```

## 19. 保存和请求数据

上一章节涵盖了 `SQLiteOpenHelper`，但现在我们需要持久化和恢复数据的方法。

### 19.1 创建类

首先，我们将为数据库创建模型类。还记得我们看到的 map 委托吗？先看 `CityForecast`：

```
1 class CityForecast(val map: MutableMap<String, Any>) {
2     var _id: Long by map
3     var city: String by map
4     var country: String by map
5 
6     constructor(id: Long, city: String, country: String)
7                 : this(HashMap()) {
8         this._id = id
9         this.city = city
10        this.country = country
11    }
12 }
```

默认构造函数获取一个填充了属性值的 map。为了让映射正确工作，属性名称必须与数据库列名相同。我们稍后会说明原因。

此外，第二个构造函数是必要的。因为我们正在将类映射到数据库。因此，与其使用 map，直接从属性中提取值更方便。我们传递一个空 map，但再次得益于委托，当我们为属性赋值时，它会自动向 map 中添加新值。这样，我们的 map 就准备好添加到数据库中了。

现在我们需要第二个类 `DayForecast`，它对应第二个表。这个类每个列有一个属性，并且使用了辅助构造函数。唯一的区别是我们没有分配 id，因为 id 是由 SQLite 自动生成的。

```
1 class DayForecast(var map: MutableMap<String, Any?>) {
2     var _id: Long by map
3     var date: Long by map
4     var description: String by map
5     var high: Int by map
6     var low: Int by map
7     var iconUrl: String by map
8     var cityId: Long by map
9 
10    constructor(date: Long, description: String, high: Int, low: Int, 
11                iconUrl: String, cityId: Long) : this(HashMap()) {
12        this.date = date
13        this.description = description
14        this.high = high
15        this.low = low
16        this.iconUrl = iconUrl
17        this.cityId = cityId
18    }
19 }
```

`data/db/DbClasses.kt`

这些类帮助我们在对象和 SQLite 表之间进行双向数据映射。

`SqliteOpenHelper` 只是一个工具，是面向对象世界和 SQL 世界之间的桥梁。我们在一个新的类中使用它，来请求已保存到数据库中的数据，并保存新数据。该类的定义使用了 `ForecastDbHelper` 和 `DataMapper`，后者负责将数据库类转换为领域模型。我仍然使用默认值作为一种简便依赖注入方式：

```
1 class ForecastDb(
2     private val forecastDbHelper: ForecastDbHelper = ForecastDbHelper.instance,
3     private val dataMapper: DbDataMapper = DbDataMapper()) {
4          ...
5 }
```

`data/db/ForecastDb.kt`

这两个函数都会调用 `use()`，也就是我们在上一章节中见过的函数。Lambda 表达式返回的值将作为我们函数的结果。因此，让我们定义一个根据邮政编码和日期请求预报的函数：

```
1 fun requestForecastByZipCode(zipCode: Long, date: Long) = forecastDbHelper.use {
2     ....
3 }
```

`data/db/ForecastDb.kt`

这里没什么好解释的：我们将 `use` 函数的结果作为我们函数的结果返回。

### 请求预报

需要完成的请求是每日预报，因为我们需要该列表来创建城市对象。Anko 提供了一个简单的请求构建器，让我们利用起来吧：

```
1 val dailyRequest = "${DayForecastTable.CITY_ID} = ? " + 
2     "AND ${DayForecastTable.DATE} >= ?"
3     
4 val dailyForecast = select(DayForecastTable.NAME)
5         .whereSimple(dailyRequest, zipCode.toString(), date.toString())
6         .parseList { DayForecast(HashMap(it)) }
```

`data/db/ForecastDb.kt`

第一行 `dailyRequest` 是查询的 `where` 部分。这是 `whereSimple` 函数需要的第一个参数，与我们通常使用该 helper 时的操作非常相似。还有一个简单称为 `where` 的函数，它接收一些标签和值并进行匹配。我不认为它非常有用，因为我觉得它增加了更多的样板代码，尽管它具有将值解析为我们所需的 `String` 的优点。下面的片段展示了使用它时看起来是什么样的：

```
1 val dailyRequest = "${DayForecastTable.CITY_ID} = {id}" + 
2 "AND ${DayForecastTable.DATE} >= {date}"
3 
4 val dailyForecast = select(DayForecastTable.NAME)
5         .where(dailyRequest, "id" to zipCode, "date" to date)
6         .parseList { DayForecast(HashMap(it)) }
```

`data/db/ForecastDb.kt`

你可以选择你偏好的方式。`select` 函数非常简单，它只是请求表名。`parse` 方法是魔法发生的地方。在这种情况下，我们使用函数 `parseList`，它假设我们正在请求一个项目列表。它使用 `RowParser` 或 `MapRowParser` 将游标（cursor）转换为对象列表。两者的区别在于 `RowParser` 依赖于列的顺序，而 `MapRowParser` 使用列名作为 map 的键。

这两个重载方法之间存在冲突，因此我们无法直接使用那种避免了显式创建对象的简化方法。这种冲突可以通过实现一个扩展函数来解决。我正在创建一个接收 lambda 并返回 `MapRowParser` 的函数。解析器将使用该 lambda 来创建对象：

```
1 fun <T : Any> SelectQueryBuilder.parseList(
2     parser: (Map<String, Any?>) -> T): List<T> =
3         parseList(object : MapRowParser<T> {
4             override fun parseRow(columns: Map<String, Any?>): T = parser(columns)
5         })
```

`extensions/DatabaseExtensions.kt`

如果你还没有完全理解它，可以在我们深入研究泛型后再回来。上一个函数有助于将 `parseList` 请求简化为：

```
1 parseList { DayForecast(HashMap(it)) }
```

解析器接收到的不可变 map 通过使用 `HashMap` 相应的构造函数转换为可变 map（我们在数据库模型中需要它是可变的）。这个 `HashMap` 被 `ForecastDb` 的构造函数使用。

因此，为了理解幕后发生了什么，请求返回一个 `Cursor`。`parseList` 遍历它并从 `Cursor` 中获取行直到到达最后一行。对于每一行，它创建一个以列为键的 map，并将值分配给相应的键。然后将该 map 返回给解析器。

如果请求没有结果，`parseList` 返回一个空列表。

下标将以类似的方式请求城市：

```
1 val city = select(CityForecastTable.NAME)
2         .whereSimple("${CityForecastTable.ID} = ?", zipCode.toString())
3         .parseOpt { CityForecast(HashMap(it), dailyForecast) }
```

`data/db/ForecastDb.kt`

这里的区别是：我们改用 `parseOpt`。此函数返回一个可空对象。结果可能是 `null` 或单个对象，取决于请求是否在数据库中找到内容。另一个名为 `parseSingle` 的函数本质上与它相同，但返回的是一个非可空对象。所以，如果它没有找到行，它会抛出异常。在我们的情况下，由于城市可能不存在，所以我们使用 `parseOpt`。

```
1 fun <T : Any> SelectQueryBuilder.parseOpt(
2     parser: (Map<String, Any?>) -> T): T? =
3         parseOpt(object : MapRowParser<T> {
4             override fun parseRow(columns: Map<String, Any?>): T = parser(columns)
5         })
```

`extensions/DatabaseExtensions.kt`

最后，如果返回的城市不空，我们将将其转换为领域对象并返回。否则，我们直接返回 `null`。



进入`/path/to/xxx`目录，找到`xxx.json`。

在表达式`cvar = avar + bvar`中，加法运算符（`+`）将`avar`与`bvar`相加，得到它们的和`cvar`

在`List.of(arg0, arg1, arg2)`中，`List`接口的工厂方法`of()`接受一系列的元素，返回包含它们的只读列表。

之后我们这样调用`cmd`命令：`cmd arg0 arg1 arg2`。

```
if (condVar > someVal) {console.log("xxx")}
```



该类的完整代码如下：

```
1 class ForecastProvider(private val sources: List<ForecastDataSource> =
2         ForecastProvider.SOURCES) {
3 
4     companion object {
5         const val DAY_IN_MILLIS = 1000 * 60 * 60 * 24
6         val SOURCES = listOf(ForecastDb(), ForecastServer())
7     }
8 
9     fun requestByZipCode(zipCode: Long, days: Int): ForecastList
10             = sources.firstResult { requestSource(it, days, zipCode) }
11 
12     private fun requestSource(source: ForecastDataSource, days: Int,
13             zipCode: Long): ForecastList? {
14         val res = source.requestForecastByZipCode(zipCode, todayTimeSpan())
15         return if (res != null && res.size >= days) res else null
16     }
17 
18     private fun todayTimeSpan() = System.currentTimeMillis() /
19             DAY_IN_MILLIS * DAY_IN_MILLIS
20 }
```

`domain/datasource/ForecastProvider.kt`

我们已经定义了 `ForecastDb`。它现在需要实现 `ForecastDataSource`。

```kotlin
class ForecastDb(private val forecastDbHelper: ForecastDbHelper =
        ForecastDbHelper.instance, 
        private val dataMapper: DbDataMapper = DbDataMapper())
        : ForecastDataSource {

    override fun requestForecastByZipCode(zipCode: Long, date: Long) =
            forecastDbHelper.use {
    ...
    }
    ...
}
```

`data/db/ForecastDb.kt`

我们还没有实现 `ForecastServer`，但它的实现非常直接。它利用 `ForecastDb` 在从服务器接收到响应后将其保存。这样，我们就可以将其缓存到数据库中，以供后续请求。

```kotlin
class ForecastServer(
    private val dataMapper: ServerDataMapper = ServerDataMapper(),
    private val forecastDb: ForecastDb = ForecastDb()) 
    : ForecastDataSource {

    override fun requestForecastByZipCode(zipCode: Long, date: Long): 
            ForecastList? {
        val result = ForecastByZipCodeRequest(zipCode).execute()
        val converted = dataMapper.convertToDomain(zipCode, result)
        forecastDb.saveForecast(converted)
        return forecastDb.requestForecastByZipCode(zipCode, date)
    }

}
```

`data/server/ForecastServer.kt`

它也使用了数据映射（data mapper），即我们创建的第一个，尽管我修改了一些方法的名称，使其与我们用于数据库模型的数据映射相似。你可以查看提供者（provider）以了解细节。

重写后的函数向服务器发送请求，将结果转换为领域对象并将其保存到数据库中。最后它返回数据库中的值，因为我们需要插入查询自动生成的行 ID。

完成这些最后步骤后，提供者已经实现完毕。现在我们需要开始使用它了。`ForecastCommand` 不再应该直接与服务器请求交互，也不再将数据转换为领域模型。

```kotlin
class RequestForecastCommand(private val zipCode: Long,
        private val forecastProvider: ForecastProvider = ForecastProvider()) :
        Command<ForecastList> {

    companion object {
        const val DAYS = 7
    }

    override fun execute(): ForecastList =
        forecastProvider.requestByZipCode(zipCode, DAYS)
}
```

`domain/commands/RequestForecastCommand.kt`

其余的代码修改包括此处的的一些重命名和包结构调整。请查看 [Kotlin for Android Developers 仓库](https://github.com/antoniolg/Kotlin-for-Android-Developers/tree/chapter-21) 中对应的分支。

## 22. 流程控制与范围

我在代码中已经了一些条件表达式，所以你对本章的一些概念并不陌生。但现在是时候更深入地解释它们了。虽然在 Kotlin 中，我们通常比在完全过程式的编程语言中通常使用的流程控制机制要少（有些甚至几乎消失了），但它们仍然很有用。还有一些新的强大思想可以更轻松地解决某些特定问题。

### 22.1 If 表达式

Kotlin 中的几乎所有内容都是表达式，这意味着它们会返回一个值。`If` 条件并不是例外，尽管我们可以像习惯的那样使用 `if`：

```
if (x > 0) {
    toast("x is greater than 0")
} else if (x == 0) {
    toast("x equals 0")
} else {
    toast("x is smaller than 0")
}
```

我们还可以将它的结果赋值给变量。我们在代码中已经这样用过几次：

```
val res = if (x != null && x.size() >= days) x else null
```

这同时也意味着我们不需要类似于 Java 的三元运算符，因为我们可以轻松地解决：

```
val z = if (condition) x else y
```

因此 `if` 表达式总是返回一个值。如果其中一个分支返回 `Unit`，则整个表达式返回 `Unit`，该值是可以被忽略的，在这种情况下，它的行为会像普通的 Java `if` 条件一样。

### 22.2 When 表达式

`When` 表达式类似于 Java 中的 `switch`，但要强大得多。它将参数与可能的情况进行匹配，直到找到匹配的项为止。

Kotlin 为任何可比较类型定义了范围（ranges），但对于数值类型，编译器通过将其转换为 Java 中更简单的模拟代码来优化，以避免额外的开销。数值范围也是可迭代的，循环也会被优化，转换为与 Java 中使用的带索引的 `for` 循环相同的相同的字节码：

```
for (i in 0..10)
    println(i)
```

范围默认是递增的，所以像：

```
for (i in 10..0)
    println(i)
```

这样的将什么都不做。不过，你可以使用 `downTo` 函数：

```
for (i in 10 downTo 0)
    println(i)
```

我们可以通过 `step` 在范围的值之间定义不同于 1 的间距：

```
for (i in 1..4 step 2) println(i)

for (i in 4 downTo 1 step 2) println(i)
```

如果你想创建一个开区间范围（排除最后一个元素），可以使用 `until` 函数：

```
for (i in 0 until 4) println(i)
```

上一行代码打印从 0 到 3，但跳过了最后一个值。这意味着 `0 until 4 == 0..3`。对于列表的迭代，使用 `for (i in 0 until list.size)` 而不是 `for (i in 0..list.size - 1)` 可能会更容易理解。

如前所述，使用范围有非常有创意的方法。例如，获取 `ViewGroup` 内部所有 `View` 列表的一种简便方法是：

```
val views = (0 until viewGroup.childCount).map { viewGroup.getChildAt(it) }
```

范围和函数式操作符的结合避免了必须使用显式循环来遍历集合，也避免了创建一个用于添加视图的显式列表。你可以在单行内完成所有操作。

如果你想了解更多关于如何实现范围的知识，并查看更多示例和有用信息，可以访问 [Kotlin 参考文档](https://kotlinlang.org/docs/reference/ranges.html)。

## 23 创建详情 Activity (Detail Activity)

当我们点击主屏幕上的某个项时，我们期望导航到详情 Activity 并看到关于该天气预报的额外信息。目前我们在点击项后只显示一个 toast，但是时候改变这一点了。

### 23.1 准备请求

由于我们需要知道要在详情 Activity 中显示哪一个项，逻辑告诉我们需要将预报的 `id` 发送到详情页。因此，领域模型需要一个新的 `id` 属性：

```
data class Forecast(val id: Long, val date: Long, val description: String, 
    val high: Int, val low: Int, val iconUrl: String)
```

`domain/model/DomainClasses.kt`

`ForecastProvider` 还需要一个新函数，通过 id 返回请求的预报。`DetailActivity` 将使用它根据接收到的 id 恢复预报。由于所有请求总是遍历源并返回第一个非空结果，我们可以将该行为提取到另一个函数：

```
private fun <T : Any> requestToSources(f: (ForecastDataSource) -> T?): T 
        = sources.firstResult { f(it) }
```

`domain/datasource/ForecastProvider.kt`

该函数使用非空类型进行泛型处理。它将接收一个函数，该函数使用 `ForecastDataSource` 返回一个泛型的可空对象，并最终返回一个非空对象。我们可以这样重写之前的请求并编写新的请求：

```
fun requestByZipCode(zipCode: Long, days: Int): ForecastList = requestToSources {
    val res = it.requestForecastByZipCode(zipCode, todayTimeSpan())
    if (res != null && res.size() >= days) res else null
}

fun requestForecast(id: Long): Forecast = requestToSources { 
    it.requestDayForecast(id) 
}
```

`domain/datasource/ForecastProvider.kt`

现在数据源需要实现这个新函数：

```
fun requestDayForecast(id: Long): Forecast?
```

`domain/datasource/ForecastDataSource.kt`

`ForecastDb` 将始终从之前的请求中缓存了所需的值，因此我们可以这种方式从那里获取：

```
override fun requestDayForecast(id: Long): Forecast? = forecastDbHelper.use {
    val forecast = select(DayForecastTable.NAME).byId(id).
            parseOpt { DayForecast(HashMap(it)) }

    if (forecast != null) dataMapper.convertDayToDomain(forecast) else null
}
```

`data/db/ForecastDb.kt`

`select` 查询与之前的非常相似。我创建了另一个工具函数 `byId`，因为通过 `id` 查询非常常见，一个这样的函数可以简化过程并更易读。该函数的实现非常简单：

```
fun SelectQueryBuilder.byId(id: Long) 

        = whereSimple("_id = ?", id.toString())
```

`extensions/DatabaseExtensions.kt`

它使用了 `whereSimple` 函数并实现了对 `_id` 字段的搜索。这个函数是非常通用的，但如你所见，你可以根据数据库的结构创建任意需要的扩展函数，并极大简化代码的可读性。`DbMapper` 有一些细微的变化，此处未提及。你可以在仓库中检查它们。

另一方面，`ForecastServer` 从未被使用，因为信息始终缓存在数据库中。我们可以实现它来保护代码免受边缘情况的影响，但在本例中没有这样做，所以它只会抛出异常：

```
override fun requestDayForecast(id: Long) 

        = UnsupportedOperationException()
```

`data/server/ForecastServer.kt`

我们需要完成的最后一件事是从新 activity 执行请求，即创建一个命令。代码非常简单：

```
class RequestForecastCommand(

        val id: Long,

        private val forecastProvider: ForecastProvider = ForecastProvider()) :

        Command<Forecast> {

    override fun execute() = forecastProvider.requestForecast(id)

}
```

`domain/commands/RequestForecastCommand.kt`

请求返回一个 `Forecast` 结果，activity 使用它来绘制 UI。

### 23.2 提供一个新的 activity

我们现在准备好创建 `DetailActivity` 了。

在 Android Studio 2.3 及以下版本中，你可以选择创建 activity 的包，右键并选择 `New -> Kotlin Activity`。

对于 Android Studio 3.0，向导已经允许选择语言。选择 `New -> Activity` 和你想创建的 activity 类型。屏幕底部有一个 `Source Language` 下菜单，可以使用它切换语言为 Kotlin。

我们的详情 activity 从主 activity 接收两个参数：预报 id 和城市名称。第一个用于从数据库请求数据，城市名称用于填充工具栏。因此，我们首先需要两个名称来标识 bundle 中的参数：

```kotlin
public class DetailActivity : AppCompatActivity() {

    companion object {

        const val ID = "DetailActivity:id"

        const val CITY_NAME = "DetailActivity:cityName"

    }

    ...

}
```

`ui/activities/DetailActivity.kt`

在 `onCreate` 函数中，第一步是设置内容视图。UI 将非常简单，但对于这个应用示例来说足够了：

```xml
<LinearLayout

    xmlns:android="http://schemas.android.com/apk/res/android"

    xmlns:tools="http://schemas.android.com/tools"

    android:layout_width="match_parent"

    android:layout_height="match_parent"

    android:orientation="vertical"

    android:paddingBottom="@dimen/activity_vertical_margin"
```



`android:paddingLeft="@dimen/activity_horizontal_margin"`

`android:paddingRight="@dimen/activity_horizontal_margin"`

`android:paddingTop="@dimen/activity_vertical_margin"`

```
<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="horizontal"
    android:gravity="center_vertical"
    tools:ignore="UseCompoundDrawables">

    <ImageView
        android:id="@+id/icon"
        android:layout_width="64dp"
        android:layout_height="64dp"
        tools:src="@mipmap/ic_launcher"
        tools:ignore="ContentDescription"/>

    <TextView
        android:id="@+id/weatherDescription"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="@dimen/spacing_xlarge"
        android:textAppearance="@style/TextAppearance.AppCompat.Display1"
        tools:text="Few clouds"/>

</LinearLayout>

<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content">

    <TextView
        android:id="@+id/maxTemperature"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_weight="1"
        android:layout_margin="@dimen/spacing_xlarge"
        android:gravity="center_horizontal"
        android:textAppearance="@style/TextAppearance.AppCompat.Display3"
        tools:text="30"/>

    <TextView
        android:id="@+id/minTemperature"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_weight="1"
        android:layout_margin="@dimen/spacing_xlarge"
        android:gravity="center_horizontal"
        android:textAppearance="@style/TextAppearance.AppCompat.Display3"
        tools:text="10"/>

</LinearLayout>
```

`layout/activity_detail.xml`

然后在 `onCreate` 代码中分配它。使用城市名称填充工具栏标题。`intent` 和 `title` 的方法会自动映射到属性：

```
setContentView(R.layout.activity_detail)
title = intent.getStringExtra(CITY_NAME)
```

`ui/activities/DetailActivity.kt`

`onCreate` 中的另一部分实现了对命令的调用。这与我们之前做的调用非常相似：

```
doAsync {
    val result = RequestDayForecastCommand(intent.getLongExtra(ID, -1)).execute()
    uiThread { bindForecast(result) }
}
```

`ui/activities/DetailActivity.kt`

当从数据库恢复结果时，会在 UI 线程中调用 `bindForecast` 函数。我再次在此 Activity 中使用 Kotlin Android Extensions 插件，以从 XML 中获取属性，而无需使用 `findViewById`：

```
import kotlinx.android.synthetic.main.activity_detail.*

...

private fun bindForecast(forecast: Forecast) = with(forecast) {
    Picasso.with(ctx).load(iconUrl).into(icon)
    supportActionBar?.subtitle = date.toDateString(DateFormat.FULL)
    weatherDescription.text = description
    bindWeather(high to maxTemperature, low to minTemperature)
}
```

`ui/activities/DetailActivity.kt`

这里有一些有趣的事情。例如，我创建了另一个扩展函数，能够将 `Long` 对象转换为可视日期字符串。记住我们在适配器中也使用了它，所以现在是将其提取为函数的好时机：

```
fun Long.toDateString(dateFormat: Int = DateFormat.MEDIUM): String {
    val df = DateFormat.getDateInstance(dateFormat, Locale.getDefault())
    return df.format(this)
}
```

`extensions/ExtensionUtils.kt`

它获取日期格式（或使用默认的 `DateFormat.MEDIUM`），并将 `Long` 转换为用户可理解的 `String`。

另一个有趣的函数是 `bindWeather`。它接收一个 `Int` 和 `TextView` 对的 `vararg`，并根据温度将文本和文本颜色分配给 `TextView`。

```
private fun bindWeather(vararg views: Pair<Int, TextView>) = views.forEach {
    it.second.text = "${it.first}"
    it.second.setTextColor(when(it.first) {
        in -50..0 -> R.color.red_dark
        in 0..15 -> R.color.orange_dark
        else -> R.color.green_dark
    })
}
```

`ui/activities/DetailActivity.kt`

### 23.3 启动 Activity：具化函数

最后一步是从主 Activity 启动详情 Activity。我们可以这样重写适配器实例化：

```
val adapter = ForecastListAdapter(result) {
    val intent = Intent(MainActivity@this, javaClass<DetailActivity>())
    intent.putExtra(DetailActivity.ID, it.id)
    intent.putExtra(DetailActivity.CITY_NAME, result.city)
    startActivity(intent)
}
```

但这太冗长了。像往常一样，Anko 通过使用**具化函数**提供了一种更简单的启动 Activity 的方式：

```
val adapter = ForecastListAdapter(result) {
    startActivity<DetailActivity>(DetailActivity.ID to it.id,
            DetailActivity.CITY_NAME to result.city)
}
```

`ui/activities/MainActivity.kt`

具化函数背后的魔法是什么？如你所知，当我们在 `Java` 中创建泛型方法时，无法从泛型类型获取类。一种通用的替代方法是将类作为参数传递。在 Kotlin 中，内联函数可以被具化，这意味着可以在函数内部获取并使用泛型类型的类。在这种情况下，我们可以通过调用 `T::class.javaClass` 在函数内部创建 intent。Anko 所做功能的简单版本如下（在此示例中我仅使用了 `String` 额外参数）：

```
public inline fun <reified T: Activity> Context.startActivity(
        vararg params: Pair<String, String>) {
    
    val intent = Intent(this, T::class.java)
    params.forEach { intent.putExtra(it.first, it.second) }
    startActivity(intent)
}
```

真正的实现要复杂一些，因为它使用了一个冗长且无聊的 `when` 表达式根据类型添加额外参数，但这对该概念并没有增加多少实用的知识。

具化函数再次是一种简化代码并提高可读性的语法糖。在这种情况下，它通过从泛型类型获取 `javaClass` 来创建一个 intent，遍历 `params` 并将其添加到 intent 中，然后使用该 intent 启动 Activity。具化类型被限制为 `Activity` 的子类。

其余细节可以在[代码仓库](https://github.com/antoniolg/Kotlin-for-Android-Developers/tree/chapter-23) 中找到。我们现在使用 Kotlin 实现了一个简单（但完整）主详情界面 App，而没有使用任何一行 `Java` 代码。

## 24 接口与委托

### 24.1 接口

Kotlin 中的接口比 `Java 7` 更加强大。如果你工作过 `Java 8`，那么它们的相似性会非常接近。在 Kotlin 中，我们可以像在 `Java` 中一样使用接口。假设我们有一些动物，其中一些会飞。这是我们可以为会飞的动物设计的接口：

```
interface FlyingAnimal {
    fun fly()
}
```

鸟类和蝙蝠都可以通过扇动翅膀飞行。所以，让我们为它们创建几个类：

```
class Bird : FlyingAnimal {
    val wings: Wings = Wings()
    override fun fly() = wings.move()
}

class Bat : FlyingAnimal {
    val wings: Wings = Wings()
    override fun fly() = wings.move()
}
```

当多个类扩展一个接口时，它们都共享相同的实现是非常典型的。然而，`Java 7` 接口只能定义行为，而不能实现它。

另一方面，Kotlin 接口可以实现函数。与类的唯一区别在于它们是无状态的，因此需要支持字段的属性需要由类来重写。类负责保存接口属性的状态。

我们可以让接口实现 `fly` 函数：

```
interface FlyingAnimal {
    val wings: Wings
    fun fly() = wings.move()
}
```

如前提到的，类需要重写该属性：

```
class Bird : FlyingAnimal {
    override val wings: Wings = Wings()
}

class Bat : FlyingAnimal {
    override val wings: Wings = Wings()
}
```

现在，鸟类和蝙蝠都会飞了：

```
val bird = Bird()
val bat = Bat()

bird.fly()
bat.fly()
```

### 24.2 委托

[委托](https://en.wikipedia.org/wiki/Delegation_pattern) 是一种实用的模式，可以用于从类中提取职责。Kotlin 原生支持委托模式，因此它避免了手动调用委托对象的需要。委托者只需要指定哪个实例实现了该接口即可。

在我们之前的示例中，我们可以通过构造函数指定动物如何飞翔，而不是直接实现它。例如，一个使用翅膀飞行的动物可以这样实现：

```
interface CanFly {
    fun fly()
}

class Bird(f: CanFly) : CanFly by f
```

我们可以通过使用接口来指示鸟会飞，但鸟飞行的方式是通过构造函数传入的委托定义的，因此我们可以拥有具有不同飞行方法的不同鸟。带翅膀的动物飞行方式在另一个类中定义：

```
class AnimalWithWings : CanFly {
    val wings: Wings = Wings()
    override fun fly() = wings.move()
}
```

带翅膀的动物通过移动翅膀来飞行。因此，现在我们可以创建一个使用翅膀飞行的鸟：

```
val birdWithWings = Bird(AnimalWithWings())
birdWithWings.fly()
```

但现在翅膀也可以用于其他非鸟类动物。如果我们假设蝙蝠总是使用翅膀，我们可以在指定委托的地方直接实例化：

```
class Bat : CanFly by AnimalWithWings()
...
val bat = Bat()
bat.fly()
```



### 24.3 在我们的 App 中实现一个示例

接口可以从具有相似行为的类中提取公共代码。例如，我们可以创建一个处理 App 工具栏的接口。`MainActivity` 和 `DetailActivity` 共享处理工具栏的相似代码。

但需要进行一些更改以使用工具栏而不是 `ActionBar`。第一件事是扩展 `NoActionBar` 主题：

```xml
1 <style name="AppTheme" parent="Theme.AppCompat.Light.NoActionBar">
2     <item name="colorPrimary">#ff2121</item>
3     <item name="colorPrimaryDark">@android:color/black</item>
4 </style>
```

`values/styles.xml`

我们使用的是浅色主题。接下来，创建一个可以在其他布局中包含的工具栏布局：

```xml
1 <android.support.v7.Toolbar
2     xmlns:app="http://schemas.android.com/apk/res-auto"
3     xmlns:android="http://schemas.android.com/apk/res/android"
4     android:id="@+id/toolbar"
5     android:layout_width="match_parent"
6     android:layout_height="?attr/actionBarSize"
7     android:background="?attr/colorPrimary"
8     android:theme="@style/ThemeOverlay.Dark.ActionBar"
9     app:popupTheme="@style/ThemeOverlay.AppCompat.Light"/>
```

`layout/toolbar.xml`

工具栏指定了背景、它生成的弹出主题（例如溢出菜单）。然后我们得到了之前拥有的相同主题：带 `ActionBar` 的浅色主题。

下一步将修改 `MainActivity` 布局以包含工具栏：

```xml
1 <FrameLayout
2     xmlns:android="http://schemas.android.com/apk/res/android"
3     android:layout_width="match_parent"
4     android:layout_height="match_parent">
5 
6     <android.support.v7.RecyclerView
7         android:id="@+id/forecastList"
8         android:layout_width="match_parent"
9         android:layout_height="match_parent"
10        android:clipToPadding="false"
11        android:paddingTop="?attr/actionBarSize"/>
12 
13     <include layout="@layout/toolbar"/>
14 
15 </FrameLayout>
```

`layout/activity_main.xml`

现在已经在布局中添加了工具栏，我们就可以使用它了。我们创建一个接口，允许我们：

*   更改标题
*   指定是否显示返回导航操作
*   滚动时动画工具栏
*   为所有 `Activity` 分配相同的菜单以及操作的事件

所以让我们定义 `ToolbarManager`：

```kotlin
1 interface ToolbarManager {
2     val toolbar: Toolbar
3     ...
4 }
```

`ui/activities/ToolbarManager.kt`

```kotlin
1 var toolbarTitle: String
2     get() = toolbar.title.toString()
3     set(value) {
4         toolbar.title = value
5     }
```

`ui/activities/ToolbarManager.kt`

由于该属性直接使用了 `toolbar`，因此不需要保存额外的状态。

我们现在正在创建一个新函数，通过加载菜单并设置监听器来初始化工具栏：

```kotlin
1 fun initToolbar() {
2     toolbar.inflateMenu(R.menu.menu_main)
3     toolbar.setOnMenuItemClickListener {
4         when (it.itemId) {
5             R.id.action_settings -> App.instance.toast("Settings")
6             else -> App.instance.toast("Unknown option")
7         }
8         true
9     }
10 }
```

`ui/activities/ToolbarManager.kt`

我们还可以添加一个函数来启用工具栏中的导航图标，设置箭头图标以及在点击图标时触发的监听器：

```kotlin
1 fun enableHomeAsUp(up: () -> Unit) {
2     toolbar.navigationIcon = createUpDrawable()
3     toolbar.setNavigationOnClickListener { up() }
4 }
5 
6 private fun createUpDrawable() = 
7      DrawerArrowDrawable(toolbar.ctx).apply { progress = 1f }
```

`ui/activities/ToolbarManager.kt`

该函数接收监听器，使用最终状态下的 `DrawerArrowDrawable`（箭头已经显示时）创建向上 drawable，并将监听器分配给 `toolbar`。

最后，接口提供了一个函数允许工具栏绑定到滚动视图，并根据滚动的方向对工具栏进行动画。当我们向下滚动时，工具栏会被隐藏，向上滚动时会再次显示：

```kotlin
1 fun attachToScroll(recyclerView: RecyclerView) {
2     recyclerView.addOnScrollListener(object : RecyclerView.OnScrollListener() {
3         override fun onScrolled(recyclerView: RecyclerView?, dx: Int, dy: Int) {
4             if (dy > 0) toolbar.slideExit() else toolbar.slideEnter()
5         }
6     })
7 }
```

`ui/activities/ToolbarManager.kt`

让我们创建几个扩展函数来让视图进入和移出屏幕动画。它们会检查是否之前执行过动画。这样可以防止视图在每次滚动变化时都执行动画：

```kotlin
1 fun View.slideExit() {
2     if (translationY == 0f) animate().translationY(-height.toFloat())
3 }
4 
5 fun View.slideEnter() {
6     if (translationY < 0f) animate().translationY(0f)
7 }
```

`extensions/ViewExtensions.kt`

实现工具栏管理器后，该是在 `MainActivity` 中使用它了，它现在必须实现该接口：

```kotlin
1 class MainActivity : AppCompatActivity(), ToolbarManager {
2     ...
3 }
```

`ui/activities/MainActivity.kt`

我们首先指定 `toolbar` 属性。我们可以实现一个懒性查找（lazy find），以便在使用它时 `toolbar` 已经加载完成：

```kotlin
1 override val toolbar by lazy { find<Toolbar>(R.id.toolbar) }
```

`ui/activities/MainActivity.kt`

`MainActivity` 将初始化工具栏、绑定到 `RecyclerView` 滚动视图并修改工具栏标题：

```kotlin
1 override fun onCreate(savedInstanceState: Bundle?) {
2     super.onCreate(savedInstanceState)
3     setContentView(R.layout.activity_main)
4     initToolbar()
5 
6     forecastList.layoutManager = LinearLayoutManager(this)
7     attachToScroll(forecastList)
8 
9     doAsync {
10         val result = RequestForecastCommand(94043).execute()
11         uiThread {
12             val adapter = ForecastListAdapter(result) {
13                 startActivity<DetailActivity>(DetailActivity.ID to it.id,
14                         DetailActivity.CITY_NAME to result.city)
15             }
16             forecastList.adapter = adapter
17             toolbarTitle = "${result.city} (${result.country})"
18         }
19     }
20 }
```

`ui/activities/MainActivity.kt`

`DetailActivity` 也需要一些布局修改：

```xml
1 <LinearLayout
2     xmlns:android="http://schemas.android.com/apk/res/android"
3     xmlns:tools="http://schemas.android.com/tools"
4     android:layout_width="match_parent"
5     android:layout_height="match_parent"
6     android:orientation="vertical">
7 
8     <include layout="@layout/toolbar"/>
9 
10     <LinearLayout
11         android:layout_width="match_parent"
12         android:layout_height="wrap_content"
13         android:orientation="horizontal"
14         android:gravity="center_vertical"
15         android:paddingTop="@dimen/activity_vertical_margin"
16         android:paddingLeft="@dimen/activity_horizontal_margin"
17         android:paddingRight="@dimen/activity_horizontal_margin"
18         tools:ignore="UseCompoundLayout">
19 
20     </LinearLayout>
21 </LinearLayout>
```

`ui/activities/MainActivity.kt`

`DetailActivity` 也需要一些布局修改：

现在每个扩展了 `Context` 的类都可以作为我们类的类型。其他类型是不被允许的。

当然，函数中也允许使用类型。我们可以很容易地构建泛型函数：

```kotlin
1 fun <T> typedFunction(item: T): List<T> {
2     ...
3 }
```

### 25.2 变变 (Variance)

这真的是最难理解的部分之一。在 Java 中，使用泛型类型时存在一个问题。逻辑上说，`List<String>` 应该能够强制转换为 `List<Object>`，因为它的限制更少。但看这个例子：

```java
1 List<String> strList = new ArrayList<>();
2 List<Object> objList = strList;
3 objList.add(5);
4 String str = objList.get(0);
```

如果 Java 编译器允许我们这样做，我们就可以向 `Object` 列表添加一个 `Integer`，这会在某个时刻导致程序崩溃。这就是为什么语言中引入了通配符（wildcards）。通配符在限制这一问题的同时增加了灵活性。

如果我们添加 `? extends Object`，我们就是在使用**协变 (covariance)**，这意味着我们可以处理任何使用比 `Object` 限制更大的类型的对象，但我们只能安全地执行 `get` 操作。如果我们想将一个 `String` 集合拷贝到 `Object` 集合中，应该是允许的，对吧？

那么，如果我们有：

```java
1 List<String> strList = ...;
2 List<Object> objList = ...;
3 objList.addAll(strList);
```

这是可能的，因为 `Collection` 接口中 `addAll()` 的定义类似于：

```java
1 List<String> 
2 interface Collection<E> ... {
3   void addAll(Collection<? extends E> items);
4 }
```

否则，如果没有通配符，我们将不允许使用此方法配合 `String` 列表。相反的情况自然会失败。我们不能使用 `addAll()` 将一个 `Object` 列表添加到 `String` 列表中。由于我们只是从在该方法中使用的集合中获取项，因此它是协变的完美范例。

另一方面，我们可以找到**逆变 (contravariance)**，它只是完全相反的情况。接上 `Collection` 的例子，如果我们想向作为参数传递的 `Collection` 中添加项，我们可以将具有更严格类型的对象添加到更通用的集合中。例如，我们可以将 `String` 添加到 `Object` 列表中：

```java
1 void copyStrings(Collection<? super String> to, Collection<String> from) {
2     to.addAll(from);
3 }
```

我们向 `String` 添加到另一个集合的唯一限制是：该集合接受 `String` 或其父类的 `Object` 类型。

但通配符有一些局限性。通配符定义了**使用处变性 (use-site variance)**，这意味着我们需要在使用它们的地方声明它们。这意味着每当我们声明一个更通用的变量时都要添加样板代码。

让我们来看一个例子。使用与之前类似的的一个类：

```java
1 public class TypedClass<T> {
2     public T doSomething(){
3         ...
4     }
5 }
```

这段代码将无法编译：

```java
1 TypedClass<String> t1 = new TypedClass<>();
2 TypedClass<Object> t2 = t1;
```

尽管这实际上没有意义，因为我们仍然可以调用该类的所有方法，且什么都不会破坏。我们需要指定该类型可以有一个更灵活的定义。

```java
1 TypedClass<String> t1 = new TypedClass<>();
2 TypedClass<? extends String> t2 = t1;
```



在这种情况下，通配符的使用使得事情更难理解，并增加了一些额外的样板代码。

另一方面，Kotlin 通过使用**声明处变性（declaration-site variance）**更自然地处理这个问题。在 Kotlin 中，我们在定义类或接口时指定我们可以处理限制较少的情况，然后就可以到处随意地使用它。

所以让我们看看它是什么样的。Kotlin 没有使用长通配符，而是使用`out`表示协变，使用`in`表示逆变。在这种情况下，由于我们的类产生的对象保存到限制较少的变量中，我们正在使用协变。我们可以直接在类声明中定义它：

```kotlin
1 class TypedClass<out T>() {

2     fun doSomething(): T {

3         ...

4     }

5 }
```

这就是我们需要的全部。现在，Java 中无法编译的相同示例在 Kotlin 中是完全可能的：

```kotlin
1 val t1 = TypedClass<String>()

2 val t2: TypedClass<Any> = t1
```

如果你已经熟悉这些概念，我确定你可以在 Kotlin 中毫无费力地使用`in`和`out`。否则，这需要一些练习和对这些概念的良好理解。

### 25.3 泛型示例

在理论之后，让我们转向一些会让我们的生活更简单的实用函数。与其重复发明轮子，我使用了包含在 Kotlin 标准库中的三个函数。这些函数让我们仅通过一个泛型实现就能完成了不起的事情。它们可能会启发你创建自己的函数。

#### let

`let`是一个可以被任何对象调用的简单函数。它接收一个以对象作为参数的函数，并返回该函数的值。它对于处理可空对象非常方便。这里是它的定义：

```kotlin
inline inline <T, R> T.let(f: (T) -> R): R = f(this)
```

它使用了两个泛型类型：`T`和`R`。第一个类型是调用对象，第二个是结果。我们如何使用它呢？你可能记得，当我们从源获取数据时，结果可能是 null：

```kotlin
1 if (forecast != null) dataMapper.convertDayDomain(forecast) else null
```

这可以被改进。我们不应该那样处理可空类型。我们可以通过使用`let`来避免它：

```kotlin
1 forecast?.let { dataMapper.convertDayDomain(it) }
```

#### with

我们在书中多次提到这个函数。`with`接收一个对象和一个行为得像扩展函数的 lambda 表达式。

```kotlin
inline inline <T, R> with(receiver: T, f: T.() -> R): R
```

泛型在这里的工作原理相同：`T`代表接收者类型，`R`代表结果。如你所见，lambda 被定义为扩展函数：`f: T.() -> R`。这就是为什么我们随后可以调用`receiver.f()`。

我们在整个应用程序中有几个例子：

```kotlin
1 fun convertFromDomain(forecast: ForecastList) = with(forecast) {
    val daily = dailyForecast.map { convertDayDomain(id, it) }
    CityForecast(id, city, country, daily)
}
```

#### apply

它看起来与`with`函数非常相似，但想法有所不同。`apply`可用于避免创建构建器，因为调用函数的对象可以按照它需要的方式进行初始化，而`apply`函数返回同一个对象：

```kotlin
inline inline <T> T.apply(f: T.() -> Unit): T { f(); return this }
```

我们在这里只需要一个泛型类型，因为调用函数的对象也是被返回的值。一个很简单的例子将是：

```kotlin
1 val textView = TextView(context).apply {
    text = "Hello"
    hint = "Hint"
    textColor = android.R.color.white
}
```

它创建了一个`TextView`，修改了一些属性，并将其赋值给变量。一切都在简单、易读且紧凑的语法中。让我们在当前代码中使用它。在`ToolbarManager`中，我们之前是这样创建导航绘制内容的：

```kotlin
1 private fun createUpDrawable() = with(DrawerArrowDrawable(toolbar.ctx)) {
    progress = 1f
    this
}
```

使用`with`并返回`this`显然是可以通过`apply`更容易地完成的：

```kotlin
1 private fun createUpDrawable() = DrawerArrowDrawable(toolbar.ctx).apply { 
2     progress = 1f 
3 }
```

`ui/activities/ToolbarManager.kt`

你可以在 [Android 开发者 Kotlin 仓库](https://github.com/antoniolg/Kotlin-for-Android-Developers/tree/chapter-25) 中查看更多针对 Kotlin 的细微改进。

## 26 设置界面

到目前为止，我们一直使用默认城市来实现应用，但现在是时候添加选择另一个城市的功能了。应用需要一个设置部分，用户可以在那里更改城市。

我们将继续使用邮政编码来识别城市。一个真实的应用可能需要更多信息，因为单凭邮政编码无法识别全球范围内的城市。但我们至少显示一个使用我们在设置中定义的邮政编码的城市。这是一个解释处理偏好不同方法的好机会。

### 26.1 创建设置 Activity

当在工具栏的溢出菜单中选择设置时，将打开一个新的 Activity。因此，我们首先需要一个新的`SettingsActivity`：

```kotlin
 1 class SettingsActivity : AppCompatActivity() {

 2 
 3     override fun onCreate(savedInstanceState: Bundle?) {

 4         super.onCreate(savedInstanceState)

 5         setContentView(R.layout.activity_settings)

 6         setSupportActionBar(toolbar)

 7         supportActionBar?.setDisplayHomeAsUpEnabled(true)

 8     }

 9 
10     override fun onOptionsItemSelected(item: MenuItem) = when (item.itemId) {

 11         android.R.id.home -> { 

 12             onBackPressed() 

 13             true 

 14         }

 15         else -> false

 16     }

 17 }
```

`ui/activities/SettingsActivity.kt`

当用户退出屏幕 Activity 时我们将保存偏好，因此我们将相同的方式处理`Up`操作，将操作重定向到`onBackPressed`。现在，让我们创建 XML 布局。一个简单的`EditText`就足够处理该偏好了：

```xml
 1 <FrameLayout

 2     xmlns:android="http://schemas.android.com/apk/res/android"

 3     android:layout_width="match_parent"

 4     android:layout_height="match_parent">

 5 
 6     <include layout="@layout/toolbar"/>

 7 
 8     <LinearLayout

 9         android:orientation="vertical"

10         android:layout_width="match_parent"

 11         android:layout_height="match_parent"

 12         android:layout_marginTop="?attr/actionBarSize"

 13         android:padding="@dimen/spacing_xlarge">

 14 
 15         <TextView

 16             android:layout_width="wrap_content"

 17             android:layout_height="wrap_content"

 18             android:text="@string/city_zipcode"/>

 19 
 20         <EditText

 21             android:id="@+id/cityCode"

 23             android:layout_width="match_parent"

 23             android:layout_height="wrap_content"

 24             android:hint="@string/city_zipcode"

 25             android:inputType="number"/>

 26 
 27     </LinearLayout>

 28 
 29 </FrameLayout>
```

`layout/activity_settings.xml`

然后在`AndroidManifest.xml`中声明该 Activity：

```xml
1 <activity

2     android:name=".ui.activities.SettingsActivity"

3     android:label="@string/settings"/>
```

`AndroidManifest.xml`

### 26.2 访问共享偏好

你可能知道 Android [Shared Preferences](https://developer.android.com/training/basics/data-storage/shared-preferences.html) 是什么。它们由一组键值对组成，可以使用 Android 框架轻松地保存和恢复。这些偏好与 SDK 的某些部分集成，使某些任务更容易。此外，从 Android 6.0（Marshmallow）开始，共享偏好会自动保存到云端，因此当用户在新设备上恢复应用时，这些偏好也会自动恢复。

得益于属性委托（property delegation），我们可以巧妙地处理偏好。我们可以创建一个委托器，在调用`get`时查询偏好，并在调用`set`时保存它。

由于我们要保存的是`Long`类型的邮政编码，让我们为`Long`属性创建一个委托器。在`DelegatesExtensions.kt`中，实现一个新的`LongPreference`类：

```kotlin
 1 class LongPreference(

 2         private val context: Context, 

 3         private val name: String, val default: Long) {

 4 
 5     private val prefs by lazy {

 6         context.getSharedPreferences("default", Context.MODE_PRIVATE)

 7     }

 8 
 9     operator fun getValue(thisRef: Any?, property: KProperty<*>): Long =

10         prefs.getLong(name, default)

 11 
12     operator fun setValue(thisRef: Any?, property: KProperty<*>, value: Long) {

 13         prefs.edit().putLong(name, value).apply()

 14     }

 15 }
```

`extensions/DelegatesExtensions.kt`

首先，我们创建一个懒加载访问。然后在`DelegatesExt`对象中定义委托，以便在需要时更容易访问：

```kotlin
1 object DelegatesExt {

2     ....

3     fun longPreference(context: Context, name: String, default: Long) =

4         LongPreference(context, name, default)

5 }
```

`DelegatesExtensions.kt`

在`SettingsActivity`中，我们现在可以定义属性来处理偏好。我还创建了用于属性名称和默认值的常量，这样它们可以在应用的其他部分使用。

```kotlin
1 companion object {

2     const val ZIP_CODE = "zipCode"

3     const val DEFAULT_ZIP = 94043L

4 }

5 
6 private var zipCode: Long 

7         by DelegatesExt.longPreference(this, ZIP_CODE, DEFAULT_ZIP)
```

`ui/activities/SettingsActivity.kt`

现在很容易处理这个偏好。在`onCreate`中，我们获取属性的值并赋值给`EditText`：

```kotlin
1 override fun onCreate(savedInstanceState: Bundle?) {

2     ...

3     cityCode.setText(zipCode.toString())

4 }
```

`ui/activities/SettingsActivity.kt`

我们不能使用生成的属性`text`，因为`EditText`在`getText()`中返回`Editable`，所以属性默认是该值。如果我们尝试赋值一个`String`，编译器会报错。使用`setText()`就足够了。

现在我们有了实现`onBackPressed`需要的所有内容。在这里，保存属性的新值：

```kotlin
1 override fun onBackPressed() {

2     super.onBackPressed()

3     zipCode = cityCode.text.toString().toLong()

4 }
```

`ui/activities/SettingsActivity.kt`

`MainActivity`需要一些小更改。首先，它也需要一个`zipCode`属性。

```kotlin
1 private val zipCode: Long by DelegatesExt.longPreference(this, 

         SettingsActivity.ZIP_CODE, SettingsActivity.DEFAULT_ZIP)
```

`ui/activities/MainActivity.kt`

此外，我将加载预报移动到`onResume`，这样每次恢复 Activity 时都会刷新数据，以防邮政编码已更改。当然，有更高效的方法，例如在再次请求预报之前检查邮政编码是否变化。但我想保持示例简单，而且本地数据库已经保存了请求的信息，所以这个解决方案并不糟糕：

```kotlin
 1 override fun onResume() {

 2     super.onResume()

 3     loadForecast()

 4 }

 5 
 6 private fun loadForecast() = doAsync {

 7     val result = RequestForecastCommand(zipCode).execute()

 8     uiThread {

 9         val adapter = ForecastListAdapter(result) {

10             startActivity<DetailActivity>(DetailActivity.ID to it.id,

11                     DetailActivity.CITY_NAME to result.city)

12         }

13         forecastList.adapter = adapter

14         toolbarTitle = "${result.city} (${result.country})"

15     }

16 }
```



`ui/activities/MainActivity.kt`

`RequestForecastCommand` 现在使用的是`zipCode`属性而不是之前的固定值。

我们还需要做最后一件事：当用户点击溢出操作时，启动设置活动。在`ToolbarManager`中，`initToolbar`函数需要一个小小的改：

```kotlin
when (it.itemId) {
    R.id.action_settings -> toolbar.ctx.startActivity<SettingsActivity>()
    else -> App.instance.toast("Unknown option")
}
```

`ui/activities/ToolbarManager.kt`

### 26.3 通用偏好代理

既然我们已经是泛型专家了，为什么不扩展`LongPreference`使其适用于任何 Shared Preferences 支持的类型呢？让我们创建一个新的`Preference`代理：

```kotlin
class Preference<T>(private val context: Context, private val name: String, 
    private val default: T) {

    private val prefs by lazy { 
        context.getSharedPreferences("default", Context.MODE_PRIVATE) 
    }

    operator fun getValue(thisRef: Any?, property: KProperty<*>): T =
        findPreference(name, default)

    operator fun setValue(thisRef: Any?, property: KProperty<*>, value: T) {
        putPreference(name, value)
    }
    ...
}
```

`extensions/DelegatesExtensions.kt`

这个偏好与我们之前的非常相似。我们只是将`Long`替换为泛型类型`T`，并调用了几个执行繁琐工作的函数。这些函数非常简单，尽管有些重复。它们检查类型并使用偏好设置中的特定方法。例如，`findPreference`函数如下：

```kotlin
private fun findPreference(name: String, default: T): T = with(prefs) {
    val res: Any = when (default) {
        is Long -> getLong(name, default)
        is String -> getString(name, default)
        is Int -> getInt(name, default)
        is Boolean -> getBoolean(name, default)
        is Float -> getFloat(name, default)
        else -> throw IllegalArgumentException(
            "This type can't be saved into Preferences")
    }

    res as T
}
```

`extensions/DelegatesExtensions.kt`

`putPreference`函数也相同，但使用了偏好编辑器并在最后通过调用`apply()`来保存`when`的结果：

```kotlin
private fun putPreference(name: String, value: T) = with(prefs.edit()) {
    when (value) {
        is Long -> putLong(name, value)
        is String -> putString(name, value)
        is Int -> putInt(name, value)
        is Boolean -> putBoolean(name, value)
        is Float -> putFloat(name, value)
        else -> throw IllegalArgumentException("This type can be saved into Preferences")
    }.apply()
}
```

`extensions/DelegatesExtensions.kt`

现在更新`DelegatesExt`对象你就完成了：

```kotlin
object DelegatesExt {
    ...
    fun <T> preference(context: Context, name: String, default: T) 
        = Preference(context, name, default)
}
```

`extensions/DelegatesExtensions.kt`

在本章节之后，用户现在可以访问设置屏幕并修改邮编。这样，当他们返回主屏幕时，预报将用新信息自动刷新。检查[仓库中剩余的细微调整](https://github.com/antoniolg/Kotlin-for-Android-Developers/tree/chapter-26)。

## 27 初次接触协程

协程是 Kotlin 1.1 中引入的最重要特性。它们之所以很棒，是因为它们非常强大，而且社区仍在探索如何充分利用它们的特性。

简单来说，协程是一种以顺序方式编写异步代码的方法。与其在回调函数中挣扎，你可以一个接一个地编写代码。其中某些代码可以挂起执行并等待结果可用。

如果你曾是 C# 开发者，`async/await`是最接近的概念。然而，Kotlin 中的协程更强大，因为它们不是某个想法的具体实现，而是一项语言特性，开发者可以用不同的方式实现它解决特定问题。

你可以编写自己的解决方案，或者使用 Kotlin 团队和其他独立开发者构建的多个选项之一。

你需要理解，协程是 Kotlin 1.1 中的一个实验性特性。Kotlin 团队将此类别用于他们想要尽早发布但在未来可能会更改的功能。在协程的情况下，他们计划支持当前的 API，但你可能希望迁移到新定义。正如我们稍后看到的，你需要手动开启此功能。否则，当你使用它时，IDE 会显示警告。

但也意味着，你应该将本章作为你可以所做事情的示例，而不是准则。事情在未来几个月内可能会变化。

### 27.1 理解协程的工作原理

我在这里的目标是让你掌握一些基本概念并使用现有的库之一，而不是构建你自己的实现。但我认为了解内部原理是很重要的，这样你才不会盲目地使用提供的内容。

协程基于“挂起函数”（`suspending functions`）的概念：这种函数在被调用时可以停止执行，并在完成后台任务后继续运行。

挂起函数用保留关键字`suspend`标记，并且只能在其他挂起函数或协程内部调用。

因此，你不能在任何地方调用挂起函数。需要一个周围函数来构建协程并提供所需的上下文。类似于这样：

```kotlin
fun <T> async(block: suspend () -> T)
```

我不会解释如何实现上面的函数。这是一个复杂的过程，超出了本书的范围，而且对于大多数情况，已经有为你实现的解决方案了。如果你对构建自己的感兴趣，可以阅读[coroutines Github](https://github.com/Kotlin/kotlin-coroutines/blob/master/kotlin-coroutines-informal.md) 中编写的规范。你需要知道的是，函数可以有任何你想给它的的名字，并且它至少有一个挂起块作为参数。

然后你可以实现一个挂起函数并在该块内部调用它：

```kotlin
suspend fun mySuspendingFun(x: Int) : Result {
    ...
}

async { 
    val res = mySuspendingFun(20)
    print(res)
}
```

那么协程是线程吗？不完全是。它们的工作原理相似，但要轻量高效得多。你可以在几个线程上运行数百万个协程，这开启了无限可能。

你有三种方法可以使用协程特性：

- 原始实现：这意味着构建你自己的使用协程的方法。这非常复杂，通常完全不需要。
- 低级实现：Kotlin 提供了一组可以在 [kotlinx.coroutines](https://github.com/Kotlin/kotlinx-coroutines) 仓库中找到的库，它解决了一些最困难的部分，并为不同的场景提供了特定的实现。例如，[针对 Android 的](https://github.com/Kotlin/kotlinx-coroutines/tree/master/ui/kotlinx-coroutines-android)。
- 更高级的实现：如果你希望有一个能够提供你立即开始使用协程所需的所有内容的解决方案，那里有几个库可以为你完成所有繁琐的工作，而且这个列表还在不断增长。我将坚持使用 Anko，它提供了一个在 Android 上运行良好的解决方案，而且你已经对这个库非常熟悉了。

### 27.2 使用 Anko 协程

从 0.10 版本开始，`Anko`提供了几种在 Android 中使用协程的方法。

第一种与我们在上面的示例中看到的非常相似，也与其他库的做法相似。

首先，你需要创建一个`async`块，让挂起函数（suspension functions）可以在可以在其中运行：

```kotlin
async(UI) {
    ...
}
```

`UI`参数是`async`块的执行上下文。

然后，你可以创建在后台线程中执行并将结果返回给 UI 线程的块。这些块是使用`bg`函数定义的：

```kotlin
async(UI) {
    val r1: Deferred<Result> = bg { fetchResult1() }
    val r2: Deferred<Result> = bg { fetchResult2() }
    updateUI(r1.await(), r2.await())
}
```

`bg`返回一个`Deferred`对象，当调用函数`await()`时，它会挂起协程，直到返回结果。我们将在下面的示例中看到这个选项。

如你所知，由于 Kotlin 编译器可以推断变量的类型，这可以更简单：

```kotlin
async(UI) {
    val r1 = bg { fetchResult1() }
    val r2 = bg { fetchResult2() }
    updateUI(r1.await(), r2.await())
}
```

第二种替代方案是利用特定子库提供的与监听器的集成，取决于你打算使用哪种监听器。例如，在`anko-sdk15-coroutines`上，存在一个`onClick`监听器，其 lambda 确实是一个协程。因此你可以立即在监听器块内开始使用挂起函数：

```kotlin
textView.onClick {
    val r1 = bg { fetchResult1() }
    val r2 = bg { fetchResult2() }
    updateUI(r1.await(), r2.await())
}
```

如你所见，结果与之前的非常相似。你只是节省了一些代码。

要使用它，你需要根据想要使用的监听器添加其中一些依赖项：

```kotlin
compile "org.jetbrains.anko:anko-sdk15-coroutines:$anko_version"
compile "org.jetbrains.anko:anko-appcompat-v7-coroutines:$anko_version"
compile "org.jetbrains.anko:anko-design-coroutines:$anko_version"
```

### 27.3 在我们的示例中使用协程

我们目前的示例没有多少复杂的请求，在这种情况下，使用协程代替`doAsync`的价值并不大，但我想向你展示如何配置你的项目以开始使用它们。这非常直观。

首先，在`build.gradle`中添加依赖：

```kotlin
compile "org.jetbrains.anko:anko-coroutines:$anko_version"
```
`app/build.gradle`

接下来，如果你还记得，我告诉过你你需要开启该功能。否则，它会显示警告。要做到这一点，只需在模块的`build.gradle`中添加：

```kotlin
kotlin {
    experimental {
        coroutines "enable"
    }
}
```
`app/build.gradle`

现在你准备好开始使用协程了。让我们先去详情页。

你可以更改这段代码：

```kotlin
doAsync {
    val result = RequestResultCommand(intent.getLongExtra(ID, -1)).execute()
    uiThread { bindForecast(result) }
}
```

改为：

```kotlin
async(UI) {
    val result = bg { RequestResultCommand(intent.getLongExtra(ID, -1)).execute() }
    bindForecast(result.await())
}
```
`DetailActivity`

请求在后台请求得益于`bg`函数，它返回一个`Deferred`对象。结果在`bindForecast`调用时被等待，直到它就绪。

这里有一个问题：协程会在 Activity 被销毁时挂起。别担心，因为 Anko 有解决方案。你可以对 Activity 创建弱引用并使用它：

```kotlin
val ref = asReference()
val id = intent.getLongExtra(ID, -1)

async(UI) {
    val result = bg { RequestResultCommand(id).execute() }
    ref().bindForecast(result.await())
}
```

但如果协程多次与 Activity 交互，这可能会变得复杂。在`MainActivity`中，例如，这种解决方案变得更加复杂：

```kotlin
private fun loadForecast() {
    val ref = asReference()
    val id = intent.getLongExtra(ID, -1)

    async(UI) {
        val result = bg { RequestResultCommand(id).execute() }
        ref().bindForecast(result.await())
    }
}
```
`MainActivity.kt`

## 28 测试你的 App

旅程即将结束。你通过这本书学习了大部分 Kotlin 特性，但你可能好奇是否可以使用 Kotlin 测试你的 Android 应用。答案是：当然！

在 Android 中，我们有两种不同的测试：单元测试和仪表测试（instrumentation tests）。本书并不是教你如何编写测试；那里有专门的书籍。我本章的目标是解释如何准备你的环境以编写一些测试，并向你展示 Kotlin 运行得良好。

### 28.1 单元测试

我不会陷入关于单元测试含义的讨论。那里有很多定义，略有不同。一个通的想法可以是单元测试是验证单个代码单元的测试。至于“单元”包含什么留给读者。为了简单起见，我将单元测试定义为不需要设备运行的测试。IDE 可以运行测试并显示哪些测试成功了，哪些失败了。

单元测试通常使用`JUnit`库完成。所以让我们在`build.gradle`中添加依赖。由于此依赖项仅在运行测试时使用，我们可以使用`testImplementation`代替`implementation`。这样该库就不会包含在常规编译中，从而减小 APK 的 own：

```kotlin
dependencies {
    ...
    testImplementation "junit:junit:4.12"
}
```



`app/build.gradle`

现在同步 Gradle 以将库包含在你的项目中。在旧版本的 Android Studio 中，你可能需要选择想要运行的哪种测试。进入“Build Variants”（构建变体）标签（它可能在 IDE 的左侧），并点击“Test Artifact”下拉菜单。你应该在那里选择“Unit Tests”（单元测试）。新版本的 Android Studio 可以同时启用这两种测试，因此此步不是必须的。

你需要做的另一件事是创建一个新文件夹。在`src`下，你可能已经有了`androidTest`和`main`。再创建一个名为`test`的文件夹，并在下方创建一个`java`文件夹。现在，你应该有一个呈绿色的`src/test/java`文件夹。这是一个很好的迹象，表明 IDE 已检测到我们正处于“单元测试”模式，并且该文件夹包含测试文件。

让我们写一个简单的测试来检查一切是否运行正常。使用正确的包名创建一个名为`SimpleTest`的 Kotlin 类（在我的案例中是`com.antonioleiva.weatherapp`，但你需要使用你应用的主包）。一旦创建了新文件，编写这个简单的测试：

```
1 import org.junit.Test
2 import kotlin.test.assertTrue
3 
4 class SimpleTest {
5     @Test
6     fun `unit testing works`() {
7         assertTrue(true)
8     }
9 }
```

`test/SimpleTest.kt`

使用`@Test`注解将该函数标识为测试。请确保使用`org.junit.Test`。然后添加一个简单的断言。它只检查`true`是否为`true`，这应该会成功。

你看到我是如何写函数名的了吗？如果你使用反引号（backquotes），可以为测试提供一个可读的名称。当测试在 Android Studio 中运行时，摘要中显示的文本会易读得多。

你会发现这些名称显示错误。这是因为这种格式不适用于 Android 代码，因此也不适用于仪表测试（instrumentation tests）。但你可以在单元测试中毫无可以使用它们，所以你可以针对测试禁用检查并安全地使用。

要执行测试，右键点击你在`test`下创建的新的`java`文件夹，并选择“Run All Tests”（运行所有测试）。编译完成后，它将运行测试，你会看到显示结果的摘要。你应该注意到你的测试通过了。

现在是时候创建一些真实的测试了。所有涉及 Android 框架的内容可能都需要仪表测试（instrumentation test）或一些额外的库，如 [Robolectric](http://robolectric.org/)。正如此，在这些示例中，我测试的是不使用框架任何内容的内容。例如，我将测试从`Long`创建日期`String`的扩展函数。

创建一个名为`ExtensionTests`的新文件，并添加这些测试：

```
 1 class ExtensionsTest {
 2     @Test
 3     fun `"longToDateString" returns valid value`() {
 4         assertEquals("Oct 19, 2015", 1445275635000L.toDateString())
 5     }
 6 
 7     @Test
 8     fun `"longToDateString" with full format returns valid value`() {
 9         assertEquals("Monday, October 19, 2015", 
10             1445275635000L.toDateString(DateFormat.FULL))
11     }
12 }
```

`test/ExtensionsTest.kt`

这些测试检查`Long`实例是否被正确转换为`String`。第一个测试了默认行为（使用`DateFormat.MEDIUM`），而第二个指定了不同的格式。运行测试并看它们是否全部通过。我还建议你修改一些内容看看它是如何崩溃的。

如果你习惯于在 Java 中测试应用，你会发现这里没有太大区别。我涵盖了一个简单的示例，但从这里你可以创建更复杂的测试来验证应用的其他部分。例如，我们可以为`ForecastProvider`写一些测试。我们可以使用`Mockito`库来模拟（mock）其他类，并能够独立地测试 provider：

```
1 buildscript {
2     ...
3     ext.mockito_version = '2.16.0'
4 }
```

`build.gradle`

```
1 dependencies {
2     ...
3     testImplementation "junit:junit:4.12"
4     testImplementation "org.mockito:mockito-core:$mockito_version"
5 }
```

`app/build.gradle`

现在创建一个`ForecastProviderTest`。我们将测试一个带有返回内容的`DataSource`的`ForecastProvider`是否会获得一个非空结果。所以首先，我们需要模拟一个`ForecastDataSource`：

```
1 val ds = mock(ForecastDataSource::class.java)
2 `when`(ds.requestDayForecast(0)).then {
3     Forecast(0, 0, "desc", 20, 0, "url")
4 }
```

`test/domain/datasource/ForecastProviderTest.kt`

如你所见，`when`函数需要使用反引号，因为`when`是 Kotlin 中的保留字。所以如果我们发现某些使用它的 Java 代码，我们需要对其进行转义。

另一种方法是重命名导入：

```
1 import org.mockito.Mockito.`when` as whenever
2 
3 ...
4 
5 whenever(ds.requestDayForecast(0)).then { ... }
```

这取决于你；我将使用反引号。

你有两种选择来克服这种局面：

*   使用`open`关键字，这将允许 Mockito mock 你的类，同时也允许任何其他类继承该类（这可能出于某种原因被设计为闭的）。
*   提取一个接口并 mock 该接口。这是一种更优雅的解决方案，但如果你没有将该接口用于其他任何地方，它也会有些多余。

然而，还有第三种替代方案：Mockito 2 中的一个实验性功能。该功能允许你 mock`final`类并避免那些额外的产物。可能在你读到这些文字时，该功能已经不再是实验性的了。但如果它仍然是实验性的，你需要添加额外的库来启用该功能：

```
1 testImplementation "org.mockito:mockito-inline:$mockito_version"
```

`app/build.gradle`

即使它是实验性的，它的运行得也很好，所以请放心使用。

现在你可以重新运行测试，看看它是如何神奇地通过的。

### 28.3 仪表测试 (Instrumentation tests)

仪表测试稍有不同。它们通常用于测试 UI 交互，我们需要在测试执行时有一个运行中的`Application`实例。为了做到这一点，我们需要部署应用并在设备上运行测试。

这类测试位于`androidTest`文件夹中，在旧版本的 Android Studio 中，我们必须在“Build Variants”面板中将“Test Artifact”更改为“Android Instrumentation Tests”。实现仪表测试的官方库是 [Espresso](https://google.github.io/android-testing-support-library/)，它可以帮助我们通过编写`Action`轻松地在 App 中导航，并使用`ViewMatcher`和`Matcher`过滤和检查结果。

配置起来比之前的要复杂一点。我们需要许多额外的库和 Gradle 配置。好在是 Kotlin 不会增加任何额外的开销，所以如果你已经知道如何配置 Espresso，这对你来说应该是很容易的。

首先，在`defaultConfig`中指定测试运行：

```
1 defaultConfig {
2     ...
3     testInstrumentationRunner "android.support.test.runner.AndroidJUnitRunner"
4 }
```

`app/build.gradle`

一旦配置了 runner，就可以添加其余的依赖了，这次使用`androidTestImplementation`。这样，这些库只会在我们编译运行仪表测试时才被添加：

```
1 buildscript {
2     ...
3     ext.test_support_version = '1.0.1'
4     ext.espresso_version = '3.0.1'
5 }
```

`build.gradle`

```
 1 dependencies {
 2     ...
 3     androidTestImplementation "com.android.support:support-annotations:$support_versi\
 4 on"
 5     androidTestImplementation "com.android.support.test:runner:$test_support_version"
 6     androidTestImplementation "com.android.support.test:rules:$test_support_version"
 7     androidTestImplementation "com.android.support.test.espresso:espresso-core:$espre\
 8 sso_version"
 9     androidTestImplementation("com.android.support.test.espresso:espresso-contrib:$es\
10 presso_version") {
11         exclude group: 'com.android.support', module: 'appcompat-v7'
12         exclude group: 'com.android.support', module: 'support-v4'
13         exclude group: 'com.android.support', module: 'design'
14         exclude group: 'com.android.support', module: 'recyclerview-v7'
15 }
```

`app/build.gradle`

我不想花很多时间说这些，但这里是对为什么你需要这些库的简要说明：

*   `runner`：它是测试运行器，我们在`defaultConfig`中指定的那个。
*   `rules`：包含一些帮助测试加载和启动 activity 的规则。我们将在示例中使用一个规则。
*   `espresso-core`：Espresso 的基本功能，让仪表测试变得更容易库。
*   `espresso-contrib`：它添加了一些额外功能，例如`RecyclerView`测试支持。我们必须排除它的某些依赖项，因为项目中已经有了它们，否则测试会崩溃。

现在让我们创建一个简单的示例。测试将点击预报列表的第一行，并检查是否可以找到一个 id 为`R.id.weatherDescription`的视图。此视图位于`DetailActivity`中，这意味着我们在点击`RecyclerView`内部的视图后成功地导航到了详情页。

```
1 class SimpleInstrumentationTest {
2 
3     @get:Rule
4     val activityRule = ActivityTestRule(MainActivity::class.java)
5 
6     ...
7 }
```

我们需要创建一个 activity 规则，它实例化测试将使用的 activity。在 Java 中，你会使用`@Rule`对字段进行注解。然而，如你所知，字段和属性是不相同的，所以如果你只使用它，执行将失败，因为对属性内部字段的访问不是公共的。你需要做的是对 getter 进行注解。Kotlin 允许通过在规则名称前指定`get`或`set`来这样做。在这种情况下，写`@get:Rule`。

之后，我们就可以准备好创建第一个测试了：

```
1 @Test fun itemClickNavigatesToDetail() {
2     onView(withId(R.id.forecastList)).perform(
3             RecyclerViewActions
4                 .actionOnItemAtPosition<RecyclerView.ViewHolder>(0, click()))
5     onView(withId(R.id.weatherDescription))
6            .check(matches(isAssignableFrom(TextView::class.java)))
7 }
```

由于这些测试运行在设备上，我们不能使用与单元测试相同的命名格式。该函数使用`@Test`注解，正如我们在单元测试中所做的那样。我们可以在测试体中使用 Espresso。它首先点击第一个位置。然后检查是否可以找到一个是`TextView`实例的视图。

要运行测试，你可以像运行单元测试那样做：右键点击`androidTest`下的`java`文件夹，选择“Run All Tests”。现在，在“Target device”中选择你喜欢的设备。点击“OK”然后运行。你应该看到应用启动，测试点击第一个位置，打开详情页并关闭 App。

现在我们将做一个更难的。测试将打开`Toolbar`的溢出菜单，点击`Settings`操作，更改城市代码并检查 Toolbar 标题是否已更改相应的内容。

```
1 @Test fun modifyZipCodeChangesToolbarTitle() {
2     openActionBarOverflowOrOptionsMenu(activityRule.activity)
3     onView(withText(R.string.settings)).perform(click())
4     onView(withId(R.id.cityCode)).perform(replaceText("94301"))
5     pressBack()
6     onView(isAssignableFrom(Toolbar::class.java))
7             .check(matches(
8                 withToolbarTitle(`is("Palo Alto (US)")))))
9 }
```

测试确切的操作是：

*   它首先通过`openActionBarOverflowOptionsMenu`打开溢出菜单。
*   然后它找到带有`Settings`文字的视图并执行点击。
*   之后，设置 activity 打开了，因此它查找`EditText`并替换旧的城市代码为新值。
*   它按下返回键，这会将新值保存到偏好设置中并关闭 activity。
*   由于`MainActivity`执行了`onResume`，请求再次执行。这获取了新城市的预报。
*   最后一行检查 Toolbar 标题并查看它是否与正确的值匹配。

这里没有默认的检查 Toolbar 标题的匹配器，但 Espresso 很容易扩展，因此我们可以创建一个实现该检查的新匹配器：

```
1 private fun withToolbarTitle(textMatcher: Matcher<CharSequence>): Matcher<Any> =
         object : BoundedMatcher<Any, Toolbar>(Toolbar::class.java) {
            override fun matchesSafely(toolbar: Toolbar): Boolean =
                textMatcher.matches(toolbar.title)
            override fun describeTo(description: Description) {
                description.appendText("with toolbar title: ")
                textMatcher.describeTo(description)
            }
        }
```



`matchesSafely` 函数是执行检查的地方，而 `describeTo` 函数则添加了关于匹配器的信息。

这一章特别有趣，因为我们已经看到 Kotlin 如何完全与单元测试和集成测试兼容，并能与这些测试库进行互操作。[[查看代码](https://github.com/antoniolg/Kotlin-for-Android-Developers/tree/chapter-28) 并尝试自己运行测试。]

## 29 额外概念

在整本书中，我们讨论了 Kotlin 语言中最重要的概念。但在实现 App 时，我们没有使用其中一些概念，我不希望让它们消失在这些书中。在这一章中，我将回顾一些不相关的特性，这些特性在你以后使用 Kotlin 开发下一个 Android App 时可能会有所帮助。

### 29.1 嵌套类

与 Java 一样，我们可以在类内部定义类。默认情况下，内部类无法访问外部类的成员（它在 Java 中的行为表现像一个静态类）：

```kotlin
class Outer {
    private val bar: Int = 1
    class Nested {
        fun foo() = 2
    }
}

val demo = Outer.Nested().foo() // == 2
```

这就是我们用于 `ForecastListAdapter` 内部 `ViewHolder` 的做法。如果我们想访问外部类的成员，需要将其声明为 `inner`（内部）类：

```kotlin
class Outer {
    private val bar: Int = 1
    inner class Inner {
        fun foo() = bar
    }
}

val demo = Outer().Inner().foo() // == 1
```

## 29.2 枚举类

Kotlin 也提供了一种实现 `enum` 的方法：

```kotlin
enum class Day {
    SUNDAY, MONDAY, TUESDAY, WEDNESDAY,
    THURSDAY, FRIDAY, SATURDAY
}
```

枚举可以拥有参数，这些参数在构造函数中声明：

```kotlin
enum class Icon(val res: Int) {
    UP(R.drawable.ic_up),
    SEARCH(R.drawable.ic_search),
    CAST(R.drawable.ic_cast)
}

val searchIconRes = Icon.SEARCH.res
```

可以通过匹配名称的 `String` 请求枚举，我们还可以获取一个包含枚举所有值的 `Array`，以便对它们进行迭代。

```kotlin
val search: Icon = Icon.valueOf("SEARCH")
val iconList: Array<Icon> = Icon.values
```

此外，每个枚举常量都有获取其名称和在声明中位置的函数：

```kotlin
val searchName: String = Icon.SEARCH.name
val searchPosition: Int = Icon.SEARCH.ordinal
```

枚举根据 `ordinal`（序号）实现 `Comparable`，所以它们很容易进行比较。

## 29.3 密封类 (Sealed classes)

密封类用于表示受限的类层次结构，这意味着扩展密封类的类数量是被限制的。它与枚举的相似之处在于，编译器知道密封类有多少个子类型。区别在于，枚举实例是唯一的，而密封类可以有多个实例，这些实例可以包含不同的状态。

例如，我们可以实现类似于 `Option` 类的东西：这种类型通过在对象包含值时返回 `Some` 类，或在为空时返回 `None` 实例，来防止对 `null` 的使用：

```kotlin
sealed class Option<out T>
object None : Option<Nothing>()
data class Just<out T>(val value: T) : Option<T>()
```

密封类的好处是，当它们被用于 `when` 表达式时，我们可以检查所有选项，而不需要添加 `else` 分句。此外，如果我们在以后某处添加了新的子类，编译器会警告我们应该处理它的地方。

```kotlin
val result = when (option) {
    None -> "Empty"
    is Just -> "Contains a value"
}
```

## 29.4 异常

在 Kotlin 中，所有异常都实现了 `Throwable`，拥有消息并且是未检查的（unchecked）。因此，我们不需要对其中任何一个异常使用 `try/catch`。这在 Java 中并非如此，例如抛出 `IOException` 的方法需要被 `try/catch` 块包裹。时间证明检查异常并不是一个好主意。 [Bruce Eckel](http://www.mindview.net/Etc/Discussions/CheckedExceptions)、[Rod Waldhoff](http://radio-weblogs.com/0122027/stories/2003/04/01/JavasCheckedExceptionsWereAMistake.html) 或 [Anders Hejlsberg](http://www.artima.com/intv/handcuffs.html) 等人可以给你提供更好的视角。

抛出异常的方法与 Java 相同：

```kotlin
throw MyException("Exception message")
```

`try` 表达式也是完全相同的：

```kotlin
try {
    // some code
}
catch (e: SomeException) {
    // handler
}
finally {
    // optional finally block
}
```

`throw` 和 `try` 在 Kotlin 中都是表达式，允许将它们赋值给变量。这在处理边界情况时非常有用：

```kotlin
val s = when(x){
    is Int -> "Int instance"
    is String -> "String instance"
    else -> throw UnsupportedOperationException("Not valid type")
}
```

或者

```kotlin
val s = try { x as String } catch(e: ClassCastException) { null }
```

## 30 Java 互操作

到目前，我们一直在讨论从零开始创建一个 App。然而，你可能会发现自己处于已经有 Java 代码的情况。我会涵盖这个主题。

Kotlin 的伟大之处之一是它可以与 Java 完全互操作。因此，尽管你的应用程序代码是用 Java 编写的，你也可以创建 Kotlin 代码。从 Java 调用 Kotlin 再简单不过了。这潜在地为你提供了两个优势：

*   可以在 Java 中使用 Kotlin：在任何已启动的项目中，都可以开始编写新的 Kotlin 代码。
*   如果你不知道如何在 Kotlin 中实现某功能，可以在 Java 中实现。

### 30.1 包级函数

在 Kotlin 中，函数不需要在类内部，但 Java 不是这样的。那么我们如何调用函数呢？假设我们有一个名为 `utils.kt` 的文件，内容如下：

```kotlin
fun logD(message: String) {
    Log.d("", message)
}

fun logE(message: String) {
    Log.e("", message)
}
```

在 Java 中，我们可以通过名为 `UtilsKt` 的类来访问它们，该类包含一些静态方法：

```java
UtilsKt.logD("Debug");
UtilsKt.logE("Error");
```

### 30.2 扩展函数

我们在书中多次使用了扩展函数。然而，它们在 Java 中是什么样的？如果你有如下函数：

```kotlin
fun ViewGroup.inflate(resId: Int, attachToRoot: Boolean = false): View {
    return LayoutInflater.from(context).inflate(resId, this, attachToRoot)
}
```

应用于 `ViewGroup`。它接收一个布局并使用父视图进行加载。如果我们想在 Java 中使用它，会得到什么？结果如下：

```java
View v = UtilsKt.inflate(parent, R.layout.view_item, false);
```

正如你所见，应用该函数的对象（接收者）被作为参数添加到函数中。此外，可选参数在 Java 中变成了强制性的，因为在 Java 中无法使用默认值。

### 30.3 函数重载

如果你想在 Java 中生成对应的重载方法，可以对该函数使用 `@JvmOverloads` 注解。在上一个示例中，你不需要在 Java 中为第二个参数指定 `false`：

```kotlin
@JvmOverloads
fun ViewGroup.inflate(resId: Int, attachToRoot: Boolean = false): View {
    return LayoutInflater.from(context).inflate(resId, this, attachToRoot)
}
```

```java
View v = UtilsKt.inflate(parent, R.layout.view_item);
```

如果你希望在从 Java 调用 Kotlin 时指定类的名称，可以使用一个注解来修改它。在 `utils.kt` 文件中，在 `package` 语句上方添加以下内容：

```kotlin
@file:JvmName("AndroidUtils")
```

现在 Java 中的类名将命名为：

```java
AndroidUtils.logD("Debug");
AndroidUtils.logE("Error");
View v = AndroidUtils.inflate(parent, R.layout.view_item, false);
```

### 30.4 实例字段和静态字段

在 Java 中，我们使用字段来存储状态。它们可以是实例字段（意味着每个对象可以存储不同的值），或者是静态字段（类的所有实例共享它们）。如果我们尝试在 Kotlin 中寻找它们的等价物，它们就是属性（properties）和伴侣对象（companion objects）。如果我们有如下一个类：

```kotlin
class App : Application() {

    val appHelper = AppHelper()

    companion object {
        lateinit var instance: App
    }

    override fun onCreate() {
        super.onCreate()
        instance = this
    }
}
```

这在 Java 中是如何运作的？你可以通过使用 getters 和 setters 像静态字段一样访问伴侣对象的属性：

```java
AppHelper helper = App.instance.getAppHelper();
```

作为 `val`，它在 Java 中只生成 `getter`。如果是 `var`，我们还会有一个 `setter`。对 `instance` 的访问之所以自动生效，是因为使用了 `lateinit` 注解，该注解也暴露了 Kotlin 用于存储状态的字段。但想象我们创建了一个常量：

```kotlin
companion object {
    lateinit var instance: App
    val CONSTANT = 27
}
```

你会发现无法直接使用它。你被迫通过一个名为 `Companion` 的内部类来访问：

```java
KotlinClass.Companion.getCONSTANT()
```

之前的代码段看起来并不特别易读。为了在 Java 中以像静态字段一样的方式暴露字段，你需要一个新的注解：

```kotlin
@JvmField val CONSTANT = 27
```

现在你就可以从 Java 代码中使用它了：

```java
int c = App.CONSTANT;
```

如果你在伴侣对象中有函数，它们将通过 `@JvmStatic` 注解转换为静态方法。定义常量有多种方式，当我们在 Java 中使用 Kotlin 时，它们会生成不同的字节码。如果你还记得，我们之前使用了 `const val`，那些属性可以在不使用 `getter` 的情况下访问。

### 30.5 数据类

有些功能是显而易见的，但另一些则很难知道它们在 Java 中的行为。所以，让我们来看看这些 Kotlin 有但 Java 没有的功能。其中一个例子是*数据类*（data classes）。假设我们有如下数据类：

```kotlin
data class MediaItem(val id: Int, val title: String, val url: String)
```

我们可以创建此类的实例：

```java
MediaItem mediaItem = new MediaItem(1, "Title", "https://antonioleiva.com");
```

但我们遗漏什么吗？首先，检查 `equals` 是否按预期工作：

```java
MediaItem mediaItem = new MediaItem(1, "Title", "https://antonioleiva.com");
MediaItem mediaItem2 = new MediaItem(1, "Title", "https://antonioleiva.com");

if (mediaItem.equals(mediaItem2)) {
    Toast.makeText(this, "Items are equals", Toast.LENGTH_SHORT).show();
}
```

当然，它显示了 `Toast`。该类生成的字节码包含了比较两个项目所需的所有内容，如果状态相同，则项目也是相同的。然而，其他事情很难复制。还记得数据类拥有的 `copy` 功能吗？该方法存在，但你只能通过传递所有参数来使用它：

```java
mediaItem.copy(1, "Title2", "http://google.com");
```

所以它并没有比直接使用构造函数更好。此外，我们失去了解构（destructuring），因为 Java 语言没有表达这种方式。

### 30.6 密封类

另一个你想到的功能是*密封类*（sealed classes）。它们在从 Java 中使用时是如何运作的？让我们尝试一下：

```kotlin
sealed class Filter {
    object None : Filter()
    data class ByType(val type: Type) : Filter()
    data class ByFormat(val format: Format) : Filter()
}
```

我们有一个 `Filter` 类，代表一个可以应用于项目的过滤器。当然，在 Java 中我们不能这样做：

```java
switch (filter) {
    ...
}
```

（注：原文此处存在大量逻辑重复和损坏的描述，已根据核心含义进行清理和翻译）

### 30.7 内联函数和泛型类型

如果你还记得，我们在 Java 中使用 Kotlin 时，可以使用 `inline` 函数和 `reified` 类型。在 Kotlin 中，你可以让内联函数使用泛型类型。如果我们有一个接收消息作为 lambda 的 `toast` 函数，更容易测试：

```kotlin
inline fun Context.toast(message: CharSequence) {
    Toast.makeText(this, message, Toast.LENGTH_SHORT).show()
}
```

我们可以从 Java 这样使用它：

```java
ExtensionsKt.toast(this, () -> "Hello");
```

内联函数可以工作，但这里有一个有趣的地方。当从 Kotlin 使用时，反编译代码如下：

```java
Toast.makeText(this, "Hello", Toast.LENGTH_SHORT).show();
```

函数是按预期内联的。当从 Java 使用时会发生什么？对于泛型类型，在类中指定的如下：

```kotlin
inline fun <reified T : Activity> Context.startActivity() {
    startActivity(Intent(this, T::class.java))
}
```



那么，如果你从 Java 调用此函数，你会发现该方法是私有的，因此泛型类型函数在 Java 代码中是不可用的。

## 31 结

感谢阅读本书。在整个章节中，我们通过实现一个 Android 应用来学习了 Kotlin。天气应用是一个极佳的示例，用于练习大多数应用程序需要的核心功能：主详情界面、与 API 通信、数据库存储、共享偏好……

这种方法的好处在于，你在使用的过程中已经学习了最重要的 Kotlin 概念。在我看来，将新知识付诸实践会更容易被吸收。这是我的首要目标，因为参考书通常是解决特定疑虑的有用工具，但很难从头读到尾。此外，由于示例通常脱离了特定语境，很难理解这些特性解决的是什么类型的问题。

事实上，这也是这本书的另一个目标：向你展示我们在 Android 中面临的真实问题，以及如何使用 Kotlin 来解决它们。任何 Android 开发者在处理异步、数据库，或必须实现冗长的监听器或 Activity 导航时，都会遇到许多问题。通过使用一个真实的 App 作为示例，我们在学习新语言特性的同时回答了许多此类问题。

我希望我实现了这些目标，并希望你不仅学会了 Kotlin，而且享受阅读这本书的过程。既然 Google 已经采用了 Kotlin，我深信学习这门语言是必经之路：你将享受开发 App，并为这项已成为许多 Android 职位日益紧需的新技能做好准备。

这本书已经结束了，但并不意味着它完结了。我将继续将其更新到 Kotlin 的最新版本，并根据你的反馈和建议对其进行审查和改进。欢迎随时给我写信，告诉你的想法、发现的错误、不够清楚的概念或你可能有的任何顾虑。

在写这本书的几个月里，这是一段奇妙的旅程。我也学到了很多，所以再次感谢你让《Kotlin for Android Developers》成为现实。

祝好，

Antonio Leiva

*   网站: [antonioleiva.com](http://antonioleiva.com)
*   邮箱: contact@antonioleiva.com
*   Twitter: [@lime_cl](http://twitter.com/lime_cl)
*   Google+: [+AntonioLeivaGordillo](http://plus.google.com/+AntonioLeivaGordillo)
