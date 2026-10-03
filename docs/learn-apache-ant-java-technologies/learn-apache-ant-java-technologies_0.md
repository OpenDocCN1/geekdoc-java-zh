
# Learn Apache ANT [Java 技术]

我想将这本书献给将使用这本书的学生们。祝你们未来职业成功，并希望你们永停止学习。

# 引言

ANT 代表 **Another Neat**（另一个简洁）工具。它是来自计算机软件开发公司 Apache 的基于 Java 的构建工具。在进入 Apache Ant 的细节之前，让我们先了解为什么我们需要构建工具。

## 构建工具的必要性

平均而言，开发者花费大量时间在构建和部署等琐碎任务上，包括：

- 编译代码
- 打包二进制文件
- 将二进制文件部署到测试服务器
- 测试更改
- 将代码从一个位置复制到另一个位置

为了自动化和简化上述任务，Apache Ant 非常有用。它是一个操作系统的构建和部署工具，可以从命令行执行。

## Apache Ant 的历史

Ant 是由软件开发者 James Duncan Davidson 创建的，他也是 Web 服务器应用 Tomcat 的原始创建者。

Ant 最初用于构建 Tomcat，并作为 Tomcat 分发的一部分被打包。

它的诞生是为了解决 Apache Make 工具相关的问题和复杂性。

它在 2000 年作为 Apache 的独立项目被推广。截至 2020 年 9 月，Apache Ant 的最新版本为 **1.10.9**。

## Apache Ant 的特性

Apache Ant 的特性列举如下：

- 它是可用的最完整的 Java 构建和部署工具。
- 它是平台中性的，可以处理平台特定的属性，例如文件分隔符。
- 它可以执行平台特定的任务，例如使用 `touch` 命令修改文件的修改时间。
- Ant 脚本使用纯 XML 编写。如果你已经熟悉 XML，你就可以很快学会 Ant。
- Ant 擅长自动化处理复杂的重复性任务。
- Ant 带有一个大量的预定义任务列表。
- Ant 提供了一个开发自定义任务的接口。
- Ant 可以从命令行轻松调用，并可以与免费和商业 IDE 集成。

# 环境搭建

Apache Ant 根据 Apache Software License 进行分发，这是一项由开源倡议认证的完全开源许可。

最新的 Apache Ant 版本（包括其完整源代码、类文件和文档）可以在 [`ant.apache.org`](https://ant.apache.org/) 找到。

## 安装 Apache Ant

假设你已经在计算机上下载并安装了 Java 开发工具包 (JDK)。如果没有，请遵循 `file:///C:/java/java_environment_setup.htm` 提供的说明。

- 确保环境变量 `JAVA_HOME` 设置为 JDK 安装所在的文件夹。
- 从 [`ant.apache.org`](https://ant.apache.org/) 下载二进制文件。
- 使用 Winzip、winRAR、7-zip 或类似的工具将 zip 文件解压到方便的位置 `c:\folder`。
- 创建一个名为 `ANT_HOME` 的新环境变量，指向 Ant 安装文件夹。在这种情况下，它是 `c:\apache-ant-1.10.9-bin` 文件夹。
- 将 Apache Ant 批处理路径添加到 `PATH` 环境变量中。在我们的案例中，这将是 `c:\apache-ant-1.10.9-bin` 文件夹。

## 验证安装

要验证 Ant 是否安装成功，在命令提示符上输入 `ant`。你应该看到下面的输出：

```
Ant(TM) version 1.10.9 compiled on September 27 2020
```

## 安装 Eclipse

教程还涵盖了 Ant 与 Eclipse 开发环境 (IDE) 的集成。

### 安装 Eclipse 的步骤

- 从 [www.eclipse.org](https://www.eclipse.org/) 下载最新的二进制文件。
- 将二进制文件解压到方便的位置，例如 `c:\folder`。
- 运行 `eclipse.exe`。

# 构建文件

通常 Ant 的构建文件 `build.xml` 位于项目根目录。然而，文件名或位置没有限制。对于本次练习，创建一个名为 `build.xml` 的文件，内容如下：

```xml
<?xml version="1.0"?>
<project name="Hello World" default="info">
  <target name="info">
    <echo>Hello - Welcome to Ant!</echo>
  </target>
</project>
```

注意声明之前不应该有空行。如果你允许，执行 ant 时会出现以下错误：

`The processing instruction target matching is not allowed.`

所有构建文件都需要 `project` 元素和至少一个 `target` 元素。

XML `project` 元素有三个属性：

| 序序号 | 属性与描述 |
| :--- | :--- |
| 1 | `name`: 项目名称（可选）。 |
| 2 | `default`: 构建脚本的默认目标。项目可以包含任意目标。此属性指定哪个目标应被视为默认目标（强制）。 |
| 3 | `basedir`: 项目的基础目录或根文件夹（可选）。 |

目标（target）是你想要作为一个单元运行的任务集合。在我们的示例中，我们有一个简单的目标来向用户提供信息。

目标可以依赖于其他目标。例如，`deploy` 目标可能依赖 `package` 目标，`package` 目标可能依赖 `compile` 目标，依此类推。依赖关系使用 `depends` 属性表示。

例如：

```xml
<target name="deploy" depends="package">
</target>
<target name="package" depends="clean,compile">
</target>
<target name="clean">
</target>
<target name="compile">
</target>
```

`target` 元素具有以下属性：

| 序序号 | 属性与描述 |
| :--- | :--- |
| 1 | `name`: 目标的名称（强制）。 |
| 2 | `depends`: 此目标依赖的所有目标的逗号分隔列表（可选）。 |
| 3 | `description`: 目标的简短描述（可选）。 |
| 4 | `if`: 根据条件属性的真值允许执行目标（可选）。 |
| 5 | `unless`: 将目标添加到指定扩展点的依赖列表中。扩展点与目标类似，但它包含任何任务（可选）。 |

上述示例中的 `echo` 任务是一个打印消息的简单任务。在我们的示例中，它打印了消息 **Hello World**。

要运行 ant 构建文件，请打开命令提示符并导航到 `build.xml` 所在的文件夹，然后输入 `ant info`。你也可以直接输入 `ant`。两种方法都可以生效，因为 `info` 是构建文件中的默认目标（target）。

你应该看到如下输出：

```
C:\>ant
Buildfile: C:\build.xml
info: [echo] Hello World - Welcome to Apache Ant!
BUILD SUCCESSFUL
Total time: 0 seconds
C:\>
```

# 属性任务 (Property Task)

Ant 构建文件是用 XML 编写的，它不允许像你最喜爱的编程语言那样声明变量。然而，正如你可能想象的那样，如果 Ant 允许声明如项目名称、项目源码目录等变量，将会非常有用。

Ant 使用 `property` 元素允许你指定属性。这允许属性从一个构建到另一个构建或从一个环境到另一个环境更改。

## Ant 属性 (Ant Properties)

默认情况下，Ant 提供了以下预定义的属性，可以在构建文件中使用：

| 序号 | 属性与描述 |
| :--- | :--- |
| 1 | `ant.file` - 构建文件的完整位置。 |
| 2 | `ant.version` - Apache Ant 安装的版本。 |
| 3 | `basedir` - 构建的根目录，由项目元素中 `basedir` 属性指定。 |
| 4 | `ant.java.version` - Ant 使用的 JDK 版本。 |
| 5 | `ant.project.name` - 项目的名称，由项目元素中 `name` 属性指定。 |
| 6 | `ant.project.default-target` - 当前项目的默认目标。 |
| 7 | `ant.project.invoked-targets` - 当前项目中被调用的目标的逗号分隔列表。 |
| 8 | `ant.core.lib` - Ant jar 文件的完整位置。 |
| 9 | `ant.home` - Ant 安装的根目录。 |
| 10 | `ant.library.dir` - Ant 库文件的根目录 - 通常是 `ANT_HOME/lib` 文件夹。 |

Ant 还提供了系统属性（例如：`file.separator`）供构建文件使用。

除了上述属性，用户可以使用 `property` 元素定义额外的属性。

以下示例展示了如何定义一个名为 `sitename` 的属性：

```xml
<? xml version = "1.0" ?>
<project name = "Hello World Project" default = "info" >
  <property name = "sitename" value = "www.tutorialspoint.com" />
  <target name = "info" >
    <echo> Apache Ant version is ${ant.version} - You are at ${sitename} </echo>
  </target>
</project>
```

在上述构建文件运行 Ant 会产生如下输出：

```
C:\>ant
Buildfile: C:\build.xml
info: [echo] Apache Ant version is Apache Ant(TM) version 1.10.9
compiled on September 27 2020 - You are at www.tutorialspoint.com
BUILD SUCCESSFUL
Total time: 0 seconds
C:\>
```

# 属性文件 (Property Files)

如果你只需要少数几个属性，直接在构建文件中设置属性是可以的。但对于大型项目，将属性存储在单独的属性文件中是有意义的。

## 处处 (Benefits)

将属性存储在单独文件中具有以下优点：

* 它允许你重用同一个构建文件，针对不同的执行环境使用不同的属性设置。例如，可以为 DEV、TEST 和 PROD 环境单独维护构建属性文件。
* 当你事先不知道某个属性（在特定环境中）的值时，它是很有用的。这允许你在已知属性值的其他环境中执行构建。

这虽然没有硬性规定，但通常属性文件被命名为 `build.properties` 并放置在 `build.xml` 文件旁边。你可以根据部署环境创建多个构建属性文件 - 例如 `build.properties.dev` 和 `build.properties.test`。

构建属性文件的内容与普通的 Java 属性文件相似。每行包含一个属性。每个属性由一个名称和值对表示。

名称和值对由等号（`=`）分隔。强烈建议对属性进行适当的注释。注释使用井号（`#`）列出。

以下示例展示了一个 `build.xml` 文件及其关联的 `build.properties` 文件：

### build.xml

下面是 `build.xml` 文件的示例：

```xml
<? xml version = "1.0" ?>
<project name = "Hello World Project" default = "info" >
  <property file = "build.properties" />
  <target name = "info" >
    <echo> Apache Ant version is ${ant.version} - You are at ${sitename} </echo>
  </target>
</project>
```

### build.properties

下面是 `build.properties` 文件的示例：

```properties
# The Site Name
sitename=www.tutorialspoint.com
buildversion=3.3.2
```

在上述示例中，`sitename` 是一个映射到网站名称的自定义属性。你可以以此方式声明任意数量的自定义属性。

另一个列出的自定义属性是 `buildversion`。

除了上述的，Ant 还提供了许多预定义的属性，如下：

# 数据类型 (Data Types)

Ant 提供了许多数据类型。

| 序号 | 属性与描述 |
| :--- | :--- |
| 1 | `ant.file` - 构建文件的完整位置。 |
| 2 | `ant.version` - Apache Ant 安装的版本。 |
| 3 | `basedir` - 构建的根目录，由项目元素中 `basedir` 属性指定。 |
| 4 | `ant.java.version` - Ant 使用的 JDK 版本。 |
| 5 | `ant.project.name` - 项目的名称，由项目元素中 `name` 属性指定。 |
| 6 | `ant.project.default-target` - 当前项目的默认目标。 |
| 7 | `ant.project.invoked-targets` - 当前项目中被调用的目标的逗号分隔列表。 |
| 8 | `ant.core.lib` - Ant jar 文件的完整位置。 |
| 9 | `ant.home` - Ant 安装的根目录。 |
| 10 | `ant.library.dir` - Ant 库文件的根目录 - 通常是 `ANT_HOME/lib` 文件夹。 |

Ant 提供了许多数据类型。不要将“数据类型”一词与编程语言中的类型混淆。

## Ant 中的数据类型

Ant 提供以下数据类型：

### 文件集 (Fileset)

`fileset` 数据类型表示文件的集合。它用于根据特定模式包含或排除文件。

例如，参考以下代码。此处 `src` 属性指向源文件夹。

```xml
<fileset dir="${src}" casesensitive="yes">
  <include name="*.java" />
  <exclude name="*Stub*" />
</fileset>
```

`fileset` 选择源文件夹中所有的 `.java` 文件，但包含“Stub”的文件。大小敏感过滤器应用于文件集，这意味着名为 `Samplestub.java` 的文件不会被排除。

### 模式集 (Pattern set)

`pattern set` 允许根据某些模式轻松过滤文件或文件夹。可以使用以下元字符创建模式：

* `?` - 匹配一个字符。
* `*` - 匹配零或多个字符。
* `**` - 递归匹配零或多个目录。

下面的示例描述了模式集的用法：

```xml
<patternset id="java.files.without_stubs">
  <include name="src/**/*.java" />
  <exclude name="src/**/*Stub*" />
</patternset>
```

随后，`patternset` 可以如下重用在 `fileset` 中：

```xml
<fileset dir="${src}" casesensitive="yes">
  <patternset refid="java.files.without_stubs" />
</fileset>
```

### 文件列表 (File list)

`filelist` 数据类型与 `fileset` 相似，但有以下不同：

* 它包含显式命的文件列表，不支持通配符。
* 该数据类型可以应用于存在或不存在的文件。

让我们来看 `filelist` 数据类型的后续示例。在这里，属性 `webapp.src.folder` 指向项目的 Web 应用源码文件夹。

```xml
<filelist id="config.files" dir="${webapp.src.folder}" >
  <file name="applicationConfig.xml" />
  <file name="faces-config.xml" />
  <file name="web.xml" />
  <file name="portlet.xml" />
</filelist>
```

### 过滤器集 (Filter set)

通过结合 `copy` 使用 `filterset` 数据类型，可以将所有文件中匹配模式的某些文本替换为替换值。

一个常见的示例是在发布日志文件中附加版本号，如下所示。

```xml
<copy todir="${output.dir}" >
  <fileset dir="${releasenotes.dir}" includes="**/*.txt" />
  <filterset>
    <filter token="VERSION" value="${current.version}" />
  </filterset>
</copy>
```

在上述代码中 −

* 属性 `output.dir` 指向项目的输出文件夹。
* 属性 `releasenotes.dir` 指向项目的发布日志文件夹。



属性 `current.version` 指向项目的当前版本文件夹。

`copy` 任务正如其名，用于将文件从一个位置复制到另一个位置。

## 路径 (Path)

`path` 数据类型通常用于表示类路径（class-path）。`path` 中的条目使用分号或冒号分隔。然而，这些字符在运行时会被执行系统的路径分隔符所替换。

类路径被设置为项目中 jar 文件和类的列表，如下例所示。

```xml
<path id="build.classpath.jar" >
  <pathelement path="${env.J2EE_HOME}/${j2ee.jar}" />
  <fileset dir="lib" >
    <include name="**/*.jar" />
  </fileset>
</path>
```

在上述提供的代码中 −

*   属性 `env.J2EE_HOME` 指向环境变量 `J2EE_HOME`。
*   属性 `j2ee.jar` 指向 J2EE 基础目录下 J2EE jar 文件的文件名。

# 构建项目 (Building Projects)

既然我们已经学习了 Ant 中的数据类型，现在是时候将知识付诸实践了。在本章中我们将构建一个项目。本章的目标是构建一个 Ant 文件，编译 Java 类并将它们放在 `WEB-INF\classes` 文件夹中。

考虑以下项目结构 −

*   数据库脚本存储在 `db` 文件夹中。
*   Java 源代码存储在 `src` 文件夹中。
*   图像、js、META-INF、样式（css）存储在 `war` 文件夹中。
*   Java 页面（JSPs）存储在 `jsp` 文件夹中。
*   第三方 jar 文件存储在 `lib` 文件夹中。
*   Java 类文件存储在 `WEB-INF\classes` 文件夹中。

该项目将作为教程后续部分的 `Hello World` Fax 应用程序。

```
C:\work\FaxWebApplication>tree
Folder PATH listing
Volume serial number is 00740061 EC1C:ADB1
C:.
+---db
+---src
. +---faxapp
. +---dao
. +---entity
. +---util
. +---web
+---war
+---images
+---js
+---META-INF
+---styles
+---WEB-INF
+---classes
+---jsp
+---lib
```

这是该项目所需的 `build.xml`。让我们逐部分考虑它。

```xml
<?xml version="1.0" ?>
<project name="fax" basedir="." default="build" >
  <property name="src.dir" value="src" />
  <property name="web.dir" value="war" />
  <property name="build.dir" value="${web.dir}/WEB-INF/classes" />
  <property name="name" value="fax" />
  <path id="master-classpath" >
    <fileset dir="${web.dir}/WEB-INF/lib" >
      <include name="*.jar" />
    </fileset>
    <pathelement path="${build.dir}" />
  </path>
  <target name="build" description="Compile source tree java files" >
    <mkdir dir="${build.dir}" />
    <javac destdir="${build.dir}" source="1.5" target="1.5" >
      <src path="${src.dir}" />
      <classpath refid="master-classpath" />
    </javac>
  </target>
  <target name="clean" description="Clean output directories" >
    <delete>
      <fileset dir="${build.dir}" >
        <include name="**/*.class" />
      </fileset>
    </delete>
  </target>
</project>
```

首先，让我们声明一些属性。

```xml
<property name="src.dir" value="src"/>
<property name="web.dir" value="war"/>
<property name="build.dir" value="${web.dir}/WEB-INF/classes"/>
```

在上述代码中 −

*   `src.dir` 指向源码文件夹。
*   `web.dir` 指向 web 文件夹。
*   `build.dir` 指向输出文件夹。

你可以过滤 javadoc 过程，仅显示公共（public）、私有（private）、包（package）或保护（protected）类和成员。这通过使用 `private`、`public`、`package` 和 `protected` 属性来实现。

你还可以通过相应的属性告诉 javadoc 任务包含作者和版本信息。

你还可以使用 `group` 属性将包分组，以便于导航。

## 整合在一起

让我们继续 `Hello world` Fax 应用程序主题，并为我们的 Fax 应用程序项目添加一个文档目标（target）。

下面是我们在项目中使用的一个 javadoc 任务示例。在这个示例中，我们指定 javadoc 使用 `src.dir` 作为源目录，并将 `doc` 作为目标目录。

我们还自定义了出现在 Java 文档页面上的窗口标题、页眉和页脚信息。

此外，我们还创建了三个组：

*   一个用于源文件夹中的工具类，
*   一个用于用户界面类，
*   一个用于与数据库相关的类。

你可能会注意到，数据包组有两个包——`faxapp.entity` 和 `faxapp.dao`。

```
<target name = "generate-javadoc" >
<javadoc packagenames = "faxapp.*" sourcepath = "${src.dir}"
destdir = "doc" version = "true" windowtitle = "Fax Application" >
<doctitle> <![CDATA[= Fax Application =]]> </doctitle>
<bottom>
<![CDATA[Copyright © 2011\. All Rights Reserved.]]>
</bottom>
<group title = "util packages" packages = "faxapp.util.*" />
<group title = "web packages" packages = "faxapp.web.*" />
<group title = "data packages" packages = "faxapp.entity.*:faxapp.dao.*" />
</javadoc>
<echo message = "java doc has been generated!" />
</target>
```

让我们执行 javadoc Ant 任务。它会生成 Java 文档文件并放在 `doc` 文件夹中。

当执行 `javadoc target` 时，它会产生以下结果：

```
C : \>ant generate - javadoc
Buildfile : C : \build . xml
java doc has been generated !
BUILD SUCCESSFUL
Total time : 10.63 second
```

Java 文档文件现在存在于 `doc` 文件夹中。

通常，javadoc 文件是在发布（release）或打包（package）目标的一部分。

## 创建 JAR 文件

在编译 Java 源文件之后的下一个逻辑步骤是构建 Java 归档，即 Java 归档（JAR）文件。使用 Ant 的 `jar` 任务创建 JAR 文件非常简单。

## 属性

`jar` 任务常用的属性如下：

| 序号 | 属性与描述 |
| :--- | :--- |
| 1 | `basedir`: 输出 JAR 文件的基础目录。默认情况下，它设置为项目的根目录。 |
| 2 | `compress`: 建议 Ant 在创建 JAR 文件时压缩文件。 |
| 3 | `keepcompression`: 虽然 `compress` 属性适用于单个文件，但 `keepcompression` 属性执行相同的操作，只不过它适用于整个归档。 |
| 4 | `destfile`: 输出 JAR 文件的名称。 |
| 5 | `duplicate`: 建议 Ant 在发现重复文件时采取的操作。你可以添加、保留或在遇到重复文件时失败。 |
| 6 | `excludes`: 建议 Ant 不要将此逗号分隔的文件列表包含在包中。 |
| 7 | `excludesfile`: 与上述相同，但排除的文件使用模式指定。 |
| 8 | `inlcudes`: `excludes` 的反反。 |
| 9 | `includesfile`: `excludesfile` 的反反。 |
| 10 | `update`: 建议 Ant 覆盖已构建的 JAR 文件中的文件。 |

继续我们的 `Hello World` Fax 应用程序项目，让我们添加一个新目标来生成 jar 文件。

在此之前，让我们考虑下面提供的 `jar` 任务。

```
<jar destfile = "${web.dir}/lib/util.jar"
basedir = "${build.dir}/classes"
includes = "faxapp/util/**"
excludes = "**/Test.class"
/>
```

在这里，`web.dir` 属性指向 Web 源文件的路径。在我们的案例中，这是 `util.jar` 放置的地方。

示例中的 `build.dir` 属性指向构建文件夹，可以在那里找到用于 `util.jar` 的类文件。

在这个示例中，我们使用来自 `faxapp.util.*` 包的类创建一个名为 `util.jar` 的 jar 文件。然而，我们排除了以 `Test` 命名的类。输出的 jar 文件将放在 web 应用程序的 lib 文件夹中。

如果我们想让 `util.jar` 可执行 jar 文件，我们需要添加带有 `Main-Class` 元属性的 `manifest`。

因此，上面的示例将更新如下：



```xml
<jar destfile="${web.dir}/lib/util.jar"
basedir="${build.dir}/classes"
includes="faxapp/util/**"
excludes="**/Test.class" class="ts"
<manifest class="ts">
<attribute name="Main-Class" value="com.example.Main"/>
</manifest>
```

让我们执行 `javadoc` Ant 任务。它生成并把 Java 文档文件放在 `doc` 文件夹中。

当执行 `javadoc target` 时，它会产生以下结果：

```
C : \>ant generate - javadoc
Buildfile : C : \build . xml
java doc has been generated !
BUILD SUCCESSFUL
Total time : 10.63 second
```

Java 文档文件现在存在于 `doc` 文件夹中。

完全可以嵌套类、`lib`、`metainf` 和 `webinf` 目录，使它们存在于项目结构中任何位置的分散文件夹中。但是，最佳实践建议你的 Web 项目的 Web 内容结构应该类似于 WAR 文件的结构。Fax Application 项目根据这一基本原则概述了其结构。

要执行 `war` 任务，请将其封装在一个目标内部（最常见的是 `build` 或 `package` 目标），并运行它们。

```xml
<target name="build-war" >
  <war destfile="fax.war" webxml="${web.dir}/web.xml" >
    <fileset dir="${web.dir}/WebContent" >
      <include name="**/*.*" />
    </fileset>
    <lib dir="thirdpartyjars" >
      <exclude name="portlet.jar" />
    </lib>
    <classes dir="${build.dir}/web" />
  </war>
</target>
```

在此文件上运行 `Ant` 将为我们创建 `fax.war` 文件。

以下是运行 Ant 文件的结果如下：

```
C : \>ant build - war
Buildfile : C : \build . xml
BUILD SUCCESSFUL
Total time : 12.3 seconds
```

`fax.war` 文件现在被放置在输出文件夹中。war 文件的内容将所示：

`fax.war`:

+---jsp 此文件夹包含 jsp 文件

+---css 此文件夹包含样式表文件

+---js 此文件夹包含 javascript 文件

+---images 此文件夹包含图像文件

+---META-INF 此文件夹包含 Manifest.Mf

+---WEB-INF

+---classes 此文件夹包含编译后的类

+---lib 第三方库和工具用 jar 文件

`WEB.xml` 定义 WAR 包的配置文件

# 应用程序打包

我们已经通过 `Hello World` Fax web 应用程序零散地学习了 `Ant` 的不同方面。

现在，是时候将所有内容整合在一起，创建一个完整的 `build.xml` 文件了。请参考 `build.properties` 和 `build.xml` 文件如下：

### build.properties

下面给出了 `build.properties` 文件内容。

`deploy . path = c : \tomcat6\webapps`

### build.xml

`build.xml` 文件如下：

```xml
<?xml version = "1.0" ?>
<project name="fax" basedir="." default="usage" >
  <property file="build.properties" />
  <property name="src.dir" value="src" />
  <property name="web.dir" value="war" />
  <property name="javadoc.dir" value="doc" />
  <property name="build.dir" value="${web.dir}/WEB-INF/classes" />
  <property name="name" value="fax" />
  <path id="master-classpath" >
    <fileset dir="${web.dir}/WEB-INF/lib" >
      <include name="*.jar" />
    </fileset>
    <pathelement path="${build.dir}" />
  </path>
  <target name="javadoc" >
    <javadoc packagenames="faxapp.*" sourcepath="${src.dir}"
      destdir="doc" version="true" windowtitle="Fax Application" >
      <doctitle> <![CDATA[ <h1> = Fax Application = </h1> ]]> </doctitle>
      <bottom> <![CDATA[Copyright © 2011\. All Rights Reserved.]]> </bottom>
      <group title="util packages" packages="faxapp.util.*" />
      <group title="web packages" packages="faxapp.web.*" />
      <group title="data packages" packages="faxapp.entity.*:faxapp.dao.*" />
    </javadoc>
  </target>
  <target name="usage" >
    <echo message="" />
    <echo message="${name} build file" />
    <echo message="-----------------------------------" />
    <echo message="" />
    <echo message="Available targets are:" />
    <echo message="" />
    <echo message="deploy --> Deploy application as directory"/>
    <echo message="deploywar --> Deploy application as a WAR file"/>
    <echo message="" />
  </target>
  <target name="build" description="Compile main source tree java files" >
    <mkdir dir="${build.dir}" />
    <javac destdir="${build.dir}" source="1.5"
      target="1.5" debug="true"
      deprecation="false" optimize="false" failonerror="true" >
      <src path="${src.dir}" />
      <classpath refid="master-classpath" />
    </javac>
  </target>
  <target name="deploy" depends="build" description="Deploy application" >
    <copy todir="${deploy.path}/${name}" preservelastmodified="true" >
      <fileset dir="${web.dir}" >
        <include name="**/*.*" />
      </fileset>
    </copy>
  </target>
  <target name="deploywar" depends="build" description="Deploy application as a WAR file" >
    <war destfile="${name}.war" webxml="${web.dir}/WEB-INF/web.xml" >
      <fileset dir="${web.dir}" >
        <include name="**/*.*" />
      </fileset>
    </war>
  </target>
</project>
```

```xml
<group title = "util packages" packages = "faxapp.util.*" />
<group title = "web packages" packages = "faxapp.web.*" />
<group title = "data packages" packages = "faxapp.entity.*:faxapp.dao.*" />
</javadoc>
</target>

<target name = "usage" >
<echo message = "" />
<echo message = "${name} build file" />
<echo message = "-----------------------------------" />
<echo message = "" />
<echo message = "Available targets are:" />
<echo message = "" />
<echo message = "deploy --> Deploy application as directory"/>
<echo message = "deploywar --> Deploy application as a WAR file"/>
<echo message = "" />
</target>

<target name = "build" description = "Compile main source tree java files" >
<mkdir dir = "${build.dir}" />
<javac destdir = "${build.dir}" source = "1.5" target = "1.5" debug = "true"
deprecation = "false" optimize = "false" failonerror = "true" >
<src path = "${src.dir}" />
<classpath refid = "master-classpath" />
</javac>
</target>

<target name = "deploy" depends = "build" description = "Deploy application" >
<copy todir = "${deploy.path}/${name}" preservelastmodified = "true" >
<fileset dir = "${web.dir}" >
<include name = "**/*.*" />
</fileset>
</copy>
</target>

<target name = "deploywar" depends = "build" description = "Deploy application as a WAR file" >
<war destfile = "${name}.war" webxml = "${web.dir}/WEB-INF/web.xml" >
<fileset dir = "${web.dir}" >
<include name = "**/*.*" />
</fileset>
</war>
<copy todir = "${deploy.path}" preservelastmodified = "true" >
<fileset dir = "." >
<include name = "*.war" />
</fileset>
</copy>
</target>

<target name = "clean" description = "Clean output directories" >
<delete>
<fileset dir = "${build.dir}" >
<include name = "**/*.class" />
</fileset>
</delete>
</target>
```

<!-- ============================================================ -->

<!-- Tomcat tasks -->

<!-- ============================================================ -->

```xml
<path id = "catalina-ant-classpath" >
<!-- We need the Catalina jars for Tomcat -->
<!-- * for other app servers - check the docs -->
<fileset dir = "${appserver.lib}" >
<include name = "catalina-ant.jar" />
</fileset>
</path>

<taskdef name = "install" classname = "org.apache.catalina.ant.InstallTask" >
<classpath refid = "catalina-ant-classpath" />
</taskdef>
<taskdef name = "reload" classname = "org.apache.catalina.ant.ReloadTask" >
<classpath refid = "catalina-ant-classpath" />
</taskdef>
<taskdef name = "list" classname = "org.apache.catalina.ant.ListTask" >
<classpath refid = "catalina-ant-classpath" />
</taskdef>
<taskdef name = "start" classname = "org.apache.catalina.ant.StartTask" >
<classpath refid = "catalina-ant-classpath" />
</taskdef>
<taskdef name = "stop" classname = "org.apache.catalina.ant.StopTask" >
<classpath refid = "catalina-ant-classpath" />
</taskdef>

<target name = "reload" description = "Reload application in Tomcat" >
<reload url = "${tomcat.manager.url}" username = "${tomcat.manager.username}"
password = "${tomcat.manager.password}" path = "/${name}" />
</target>
</project>
```

在这个示例中，我们使用了 Tomcat 作为应用服务器。

首先，在构建属性文件（build properties file）中，我们定义了一些额外的属性，说明如下：

- `appserver.home` 指向 Tomcat 应用服务器的安装路径。

- `appserver.lib` 指向 Tomcat 安装文件夹中的库文件。

- `deploy.path` 变量现在指向 Tomcat 中的 webapp 文件夹。

Tomcat 中的应用程序可以使用 Tomcat manager 应用进行停止和启动。manager 应用的 URL、用户名和密码在 `build.properties` 文件中指定。

接下来，我们声明了一个包含 `catalina-ant.jar` 的新 `CLASSPATH`。通过 Apache Ant 执行 Tomcat 任务需要此 jar 包。

## 任务 (Tasks)

`catalina-ant.jar` 提供了以下任务：

| 序号 | 属性与描述 |

| :--- | :--- |

| 1 | InstallTask 安装一个 web 应用。类名：`org.apache.catalina.ant.InstallTask` |

| 2 | ReloadTask 重载 web 应用。类名：`org.apache.catalina.ant.ReloadTask` |

| 3 | ListTask 列出所有 web 应用。类名：`org.apache.catalina.ant.ListTask` |

| 4 | StartTask 启动一个 web 应用。类名：`org.apache.catalina.ant.StartTask` |

| 5 | StopTask 停止一个 web 应用。类名：`org.apache.catalina.ant.StopTask` |



## 使用 Ant 执行 JUnit 测试

JUnit 是基于 Java 开发中常用的单元测试框架。它易于使用且易于扩展。有许多 JUnit 扩展可用。如果你不熟悉 JUnit，应该从 [www.junit.org](https://junit.org/junit5/) 下载并阅读其手册。

本章将展示如何使用 Ant 执行 JUnit 测试。使用 Ant 使得通过 `junit` 任务执行测试变得直观简单。

`junit` 任务的属性如下所示：

| 序号 | 属性与描述 |
| :--- | :--- |
| 1 | `dir` 指定调用虚拟机（VM）的目录。当禁用 `fork` 时会忽略此属性。 |
| 2 | `jvmCommand` 用于调用 JVM。当禁用 `fork` 时会忽略此属性。 |
| 3 | `fork` 在独立的 JVM 中运行测试。 |
| 4 | `errorproperty` 当发生 JUnit 错误时设置的属性名称。 |
| 5 | `failureproperty` 当发生 JUnit 失败时设置的属性名称。 |
| 6 | `haltonerror` 发生测试错误时停止执行。 |
| 7 | `haltonfailure` 发生失败时停止执行。 |
| 8 | `printsummary` 建议 Ant 显示每个测试的简单统计信息。 |
| 9 | `showoutput` 建议 Ant 将输出发送到日志和格式化器。 |
| 10 | `tempdir` Ant 将使用的临时文件路径。 |
| 11 | `timeout` 退出运行时间超过此设置（毫秒）的测试。 |

让我们继续 Hello World Fax 应用程序，并添加一个 JUnit 目标（target）。

以下示例展示了一个简单的 JUnit 测试执行：

```xml
<target name = "unittest" >
  <junit haltonfailure = "true" printsummary = "true" >
    <test name = "com.tutorialspoint.UtilsTest" />
  </junit>
</target>
```

此示例展示了在 `com.tutorialspoint.UtilsTest` junit 类上执行 JUnit。

运行上述代码会产生以下输出：

```
test:
[echo] Testing the application
[junit] Running com.tutorialspoint.UtilsTest
[junit] Tests run: 12, Failures: 0, Errors: 0, Time elapsed: 16.2 sec
BUILD PASSED
```

## 扩展 Ant

Ant 自带了一组预定义的任务，但你可以像下面的示例所示创建你自己的任务。

自定义 Ant 任务应该继承 `org.apache.tools.ant.Task` 类并扩展 `execute()` 方法。

下面是一个简单的示例：

```java
package com.tutorialspoint.ant;

import org.apache.tools.ant.Task;
import org.apache.tools.ant.Project;
import org.apache.tools.ant.BuildException;

public class MyTask extends Task {
    String message;
    public void execute() throws BuildException {
        log("Message: " + message, Project.MSG_INFO);
    }
    public void setMessage(String message) {
        this.message = message;
    }
}
```

要执行自定义任务，你需要在 Hello World Fax 应用程序中添加以下内容：

```xml
<target name = "custom" >
  <taskdef name = "custom" classname = "com.tutorialspoint.ant.MyTask" />
  <custom message = "Hello World!" />
</target>
```

执行上述自定义任务会打印消息 'Hello World!'

```
c : >ant custom
test :
[ custom ] Message : Hello World !
elapsed : 0.2 sec
BUILD PASSED
```

这只是一个简单的示例。你可以利用 Ant 的功能来做任何你想改进构建和部署过程的事情。
