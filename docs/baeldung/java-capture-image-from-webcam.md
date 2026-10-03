
# 用 Java 从网络摄像头捕捉图像

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-capture-image-from-webcam>

## 1. 概览

通常，Java 不提供对计算机硬件的简单访问。这就是为什么我们可能会发现使用 Java 很难访问网络摄像头。

在本教程中，我们将探索一些 Java 库，这些库允许我们通过访问网络摄像头来捕捉图像。

## 2. JavaCV

首先，我们将考察`javacv`库。这是 **[Bytedeco](https://web.archive.org/web/20220524115457/http://bytedeco.org/) 的[对 OpenCV](/web/20220524115457/https://www.baeldung.com/java-opencv) 计算机视觉库**的 Java 实现。

让我们将最新的`javacv-platform` Maven 依赖添加到我们的`pom.xml`:

```xml
<dependency>
    <groupId>org.bytedeco</groupId>
    <artifactId>javacv-platform</artifactId>
    <version>1.5.5</version>
</dependency>
```

类似地，当使用 Gradle 时，我们可以在`build.gradle`文件中添加`javacv-platform`依赖项:

```groovy
compile group: 'org.bytedeco', name: 'javacv-platform', version: '1.5.5'
```

现在我们已经准备好了设置，让我们使用`OpenCVFrameGrabber`类来访问网络摄像头并捕捉一帧:

```java
FrameGrabber grabber = new OpenCVFrameGrabber(0);
grabber.start();
Frame frame = grabber.grab();
```

这里，**我们将设备号作为`0`传递，指向系统的默认摄像头**。但是，如果我们有多个可用的摄像机，那么第二个摄像机在 1 处可用，第三个在 2 处可用，依此类推。

然后，我们可以使用`OpenCVFrameConverter`将捕获的帧转换成图像。同样，我们将使用`opencv_imgcodecs`类的`cvSaveImage`方法**保存图像:**

```java
OpenCVFrameConverter.ToIplImage converter = new OpenCVFrameConverter.ToIplImage();
IplImage img = converter.convert(frame);
opencv_imgcodecs.cvSaveImage("selfie.jpg", img);
```

最后，我们可以使用`CanvasFrame`类来显示捕获的帧:

```java
CanvasFrame canvas = new CanvasFrame("Web Cam");
canvas.showImage(frame);
```

让我们来看一个完整的解决方案，它访问网络摄像头，捕捉图像，在一个框架中显示图像，并在两秒钟后自动关闭框架:

```java
CanvasFrame canvas = new CanvasFrame("Web Cam");
canvas.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

FrameGrabber grabber = new OpenCVFrameGrabber(0);
OpenCVFrameConverter.ToIplImage converter = new OpenCVFrameConverter.ToIplImage();

grabber.start();
Frame frame = grabber.grab();

IplImage img = converter.convert(frame);
cvSaveImage("selfie.jpg", img);

canvas.showImage(frame);

Thread.sleep(2000);

canvas.dispatchEvent(new WindowEvent(canvas, WindowEvent.WINDOW_CLOSING));
```

## 3. `webcam-capture`

接下来，我们将研究`webcam-capture`库，它通过支持多种捕捉框架来允许使用网络摄像头。

首先，让我们将最新的`webcam-capture` Maven 依赖添加到我们的`pom.xml`:

```xml
<dependency>
    <groupId>com.github.sarxos</groupId>
    <artifactId>webcam-capture</artifactId>
    <version>0.3.12</version>
</dependency>
```

或者，我们可以在 Gradle 项目的`build.gradle`中添加`webcam-capture`:

```groovy
compile group: 'com.github.sarxos', name: 'webcam-capture', version: '0.3.12'
```

然后，让我们编写一个简单的例子来使用`Webcam`类捕捉图像:

```java
Webcam webcam = Webcam.getDefault();
webcam.open();

BufferedImage image = webcam.getImage();

ImageIO.write(image, ImageUtils.FORMAT_JPG, new File("selfie.jpg"));
```

在这里，我们访问默认的网络摄像头来捕捉图像，然后将图像保存到一个文件中。

或者，我们可以使用`WebcamUtils`类来捕捉一个图像:

```java
WebcamUtils.capture(webcam, "selfie.jpg");
```

同样，我们可以使用`WebcamPanel`类在一个帧中显示捕获的图像:

```java
Webcam webcam = Webcam.getDefault();
webcam.setViewSize(WebcamResolution.VGA.getSize());

WebcamPanel panel = new WebcamPanel(webcam);
panel.setImageSizeDisplayed(true);

JFrame window = new JFrame("Webcam");
window.add(panel);
window.setResizable(true);
window.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
window.pack();
window.setVisible(true);
```

在这里，我们将**`VGA`设置为网络摄像头的视图大小，创建了`JFrame`对象，并将`WebcamPanel`组件添加到帧**中。

## 4. Marvin 框架

最后，我们将探索 Marvin 框架来访问网络摄像头和捕捉图像。

像往常一样，我们将最新的`marvin`依赖项添加到我们的`pom.xml`:

```xml
<dependency>
    <groupId>com.github.downgoon</groupId>
    <artifactId>marvin</artifactId>
    <version>1.5.5</version>
</dependency>
```

或者，对于 Gradle 项目，我们将在`build.gradle`文件中添加`marvin`依赖项:

```groovy
compile group: 'com.github.downgoon', name: 'marvin', version: '1.5.5'
```

现在设置已经准备好了，让我们**使用`MarvinJavaCVAdapter`类通过为设备号**提供 0 来连接到默认的网络摄像头:

```java
MarvinVideoInterface videoAdapter = new MarvinJavaCVAdapter();
videoAdapter.connect(0);
```

接下来，我们可以使用`getFrame`方法捕获帧，然后我们将使用`MarvinImageIO`类的`saveImage`方法**保存图像:**

```java
MarvinImage image = videoAdapter.getFrame();
MarvinImageIO.saveImage(image, "selfie.jpg");
```

同样，我们可以使用`MarvinImagePanel`类来显示一帧图像:

```java
MarvinImagePanel imagePanel = new MarvinImagePanel();
imagePanel.setImage(image);

imagePanel.setSize(800, 600);
imagePanel.setVisible(true);
```

## 5. 结论

在这篇短文中，我们研究了几个 Java 库，它们提供了对网络摄像头的简单访问。

首先，我们探索了提供 OpenCV 项目的 Java 实现的`javacv-platform`库。然后，我们看到了使用网络摄像头捕捉图像的`webcam-capture`库的示例实现。最后，我们看一下使用 Marvin 框架捕捉图像的简单示例。

像往常一样，所有的代码实现都可以在 GitHub 上获得。
