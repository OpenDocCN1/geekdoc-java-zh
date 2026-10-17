
现在你可以通过打开 `gnuradio-companion rds_rx.grc` 或运行如下所示的 Python 文件来运行 r-rds。

```
cd ..
cd apps
python rds_rx.py
```

![](img/33eab9643eb7fbb4bf9363c117190041_399_0.png)

# GNU Radio 教程及额外链接

更多 GNU Radio 教程：http://files.ettus.com/tutorials/

GNU Radio 视频教程系列：https://www.youtube.com/playlist?list=PL618122BD66C8B3C4

由 HackRF SDR 发明者 Micheal Ossmann 提供的 GNU Radio 综合视频课程可以在找到：https://greatscottgadgets.com/sdr。

# 在 Windows 上从源码编译 RTL-SDR 驱动

编译 RTL-SDR 驱动是一项很有用的技能，因为它允许你测试驱动程序的最新更新，或者尝试各种实验性的 RTL-SDR 分支。其中一个经常更新的实验性分支是 keerened，可以在这里找到 https://github.com/keenerd/rtl-sdr。

注意，如果你只是想使用 RTL-SDR，则没有必要编译驱动。只需遵循第一部分的快速上手指南。

在 Linux 上编译驱动非常简单，官方 osmocom 页面（http://sdr.osmocom.org/trac/wiki/rtl-sdr）提供了说明。

在 Windows 上编译要复杂一些，因此我们在下面提供了一个教程：

## 使用 MINGW 编译

本教程展示了如何使用 MingW 从源码编译，MingW 是一个在 Windows 上编译 Linux 程序的工具。其他用户要使用编译后的文件，需要在其系统中设置 MingW。可以从 http://www.mingw.org/ 下载 MingW。如果 Windows 没有自动设置，请确保在 Windows 中正确设置 MingW 路径（http://stackoverflow.com/questions/5733220/how-to-add-mingw-bin-directory-to-my-system-path）。

1. 安装 MingW，确保安装了开发工具、基础和 g++ 编译器。

| 类 | 安装版本 | 仓库版本 | 描述 |
| --- | --- | --- | --- |
| mingw-developer-tool- | bin | 201307220 | 一个 MinGW 的 MSYS 安装 (meta) |
| mingw32-base | bin | 201307220 | 基础 MinGW 安装 |
| mingw32-gcc | | 4.8-1 | GNU C 编译器 |
| mingw32-gcc-fortran | | 4.8-1 | GNU FORTRAN 编译器 |
| mingw32-gcc-g++ | bin | 4.8-1 | GNU C++ 编译器 |
| mingw32-gdb | | 4.8-1 | GNU 调试器-C 编译器 |
| msys-base | bin | 201307220 | 基础 MSYS 安装 (meta) |

2. 下载并安装 CMake，并在安装期间确保勾选到路径 http://www.cmake.org。

3. 下载 libusb1.0 http://sourceforge.net/projects/libusb/releases/。

4. 下载 threads ftp://sourceware.org/pub/threads-win32/threads-w32-9-1-release.zip。

5. 将 libusb1.0 zip 文件解压到类似 `c:\libraries\libusb-include` 的文件夹，并将 threads 解压到 `c:\libraries\threads-include`。

6. 使用 `git://git.osm.com` 或从 https://github.com/steve/librtdr 下载 zip 包或通过 `git clone` 下载 RTL-SDR 源码。解压到类似 `c:\rtl-sdr` 的目录。

7. 从开始菜单打开 `cmake-gui`。

8. 将源码设置为 `c:\rtl-sdr`

9. 将二进制构建文件夹设置为 `c:\rtl-sdr\build`。点击 Configure，系统会要求你创建构建目录。点击 yes。

10. 选择 "MinGW Makefiles" 作为此项目的编译器，并选择 "Use default compilers"，然后点击 Finish。

![](img/33eab9643eb7fbb4bf9363c117190041_402_0.png)

11. 你可能会收到一个错误，但先不要担心。

![](img/33eab9643eb7fbb4bf9363c117190041_402_1.png)

12. 现在确保勾选了高级（advanced）框。滚动到窗口底部。你应该看到 5 个显示未找到你的目录的库名称。

```
GIT_EXECUTABLE                               C:/Program Files (x86)/Git/cmd/git.cmd
LIBUSB_INCLUDE_DIR                     LIBUSB_INCLUDE_DIR-NOTFOUND
LIBUSB_LIBRARIES                       LIBUSB_LIBRARIES-NOTFOUND
PKG_CONFIG_EXECUTABLE                 PKG_CONFIG_EXECUTABLE-NOTFOUND
THREADS_PTHREADS_INCLUDE_DIR          THREADS_PTHREADS_INCLUDE_DIR-NOTFOUND
THREADS_PTHREADS_WIN32_LIBRARY         THREADS_PTHREADS_WIN32_LIBRARY-NOTFOUND
```

13. 将 `LIBUSB_INCLUDE_DIR` 设置为 `c:\libraries\libusb-include\include\libusb-1.0\`

14. 将 `LIBUSB_LIBRARIES` 设置为 `c:\libraries\libusb-include\MinGW32\static\libusb-1.0.a`

所需的运行环境，它们通常已包含在 Windows 中。

1. 安装 Windows SDK。这是 Windows 7 的下载链接：http://www.microsoft.com/en-us/download/details.aspx?id=8279。

2. 安装 Visual C++ 2010。编译在较新的 Visual C++ 版本上也应该可以工作：http://www.visualstudio.com/en-us/downloads#d-2010-express。

3. 你可能还需要为 Visual C++ 2010 安装服务包包 1：http://www.microsoft.com/en-us/download/details.aspx?id=4422。

4. 为 MingW 编译时，请按照上述节所示的相同步骤对 CMake 操作，但在指定生成器时选择 Visual Studio 10。

![](img/33eab9643eb7fbb4bf9363c117190041_405_0.png)

5. 添加与 MingW 编译相同的库，但对于 `LIBUSB_LIBRARIES` 请使用 `c:\libraries\libusb-include\MS32\static\libusb-1.0.lib`。

6. 点击配置（Configure）然后点击生成（Generate）。

7. 现在在 Windows 资源资源管理器中进入 `c:\rtl-sdr\build\` 并用 Visual C++ Express 2010 打开 `rtlsdr.sln` 文件。

8. 在 GUI 中，将 Visual Studio 顶部菜单中的生成（Build）从 Debug 更改为 Release，然后按 F7 编译文件。

`rtlsdr.dll` 和其他编译后的文件可以在 `c:\rtl-sdr\build\src\Release` 中找到。

# 宽频指南 (PANADAPTER GUIDE)

宽频器是一种连接到传统模拟硬件电台，并通过 RF 频谱和瀑布图显示频谱的可视化设备。大多数 RTL-SDR 软件默认显示 RF 频谱和瀑布图，因此 RTL-SDR 可以作为一个极其廉价的宽频器使用。这让你拥有专用硬件电台的卓越性能，以及软件无线电台常见的视觉化 RF 显示。

制作 RTL-SDR 宽频器取决于硬件电台，因为你需要找到一种将 RTL-SDR 天线输入连接到你硬件电台第一个中频（IF）的方法。一旦 IF 输出连接到天线输入，你只需使用 RTL-SDR 调到 IF 频率即可在瀑布图上看到信号。

一些旧或廉价的电台可能需要一些硬件改装来访问此 IF 输出，而一些新的电台会在电台背面提供可用的 IF 输出。如果你有控制线，大多数硬件电台还允许通过 GUI 软件 Omnirig HDR SDR 进行进行控制。

这是一个优秀的教程，展示了为 ICOM IC-7600 电台设置 RTL-SDR 宽频器的步骤：http://www.ab4oj.com/icom/ic7600/we1x_rtl_sdr_0.pdf。该教程也适用于具有简单 IF 输出的其他电台。

关于针对 Yaesu FT-857 进行此操作的良好教程可以在此 YouTube 视频找到：https://www.youtube.com/watch?v=tshXGarnBQ#t=164。另一个显示 FT-857 配合 RTL-SDR 宽频器性能的视频可以在这里：https://www.youtube.com/watch?v=wqcGACGPtrM。显示许多 Yaesu 电台所需修改的优秀 PDF 在这里：http://www.radioamatoripeligni.it/i6ibe/pdf/panadapter.pdf（注：为意大利语，但有很多很好的图片）。

这是一个针对没有简单 IF 输出的 Heathkit HR-10 的教程：https://www.youtube.com/watch?v=BRVAT9jG4kg。

# RDS 接收指南 (RDS RECEIVING GUIDE)

RDS 代表无线电数据系统（Radio Data System），是嵌入广播 FM 信号中的数字信号。电台用它在 LCD 屏幕上显示电台名称或正在播放的歌曲。

当调到设置为 WFM 模式的广播电台时，SDR#会自动解码 RF 频谱左角的 RDS 数据。

![](img/33eab9643eb7fbb4bf9363c117190041_409_0.png)

如果你不确定电台是否有 RDS，可以在 SDR# 中通过“启用 MPX”选项检查。这将打开一个显示 FM MPX 的新显示。如果电台使用了 RDS，你应该能在 57kHz 处看到一个峰值。在 SDR 上，RDS 更容易看到。你可以通过 SDR 的频谱视觉上检查调到的电台是否有 RDS。在下面的示例中，频谱右侧有一个细信号——这就是 RDS 信号。下方是一个没有 RDS 的 FM 电台示例。

![](img/33eab9643eb7fbb4bf9363c117190041_410_0.png)

另一个常用于 RDS 的程序是 Windows 程序 RDS Spy。RDS Spy 具有更好的灵分析选项，因此适合远距离接收。RDS Spy 可以从 http://rdsspy.com/ 下载。在使用特殊插件时 RDS Spy 才能配合 SDR 工作，因为默认 SDR 会移除输出中的 RDS 音调。RDS Spy 也可以配合 SDR 工作。使用 RDS Spy 解码 RDS 的第一步是设置采样率设置 Virtual Audio Cable 或 Hi-Fi Cable。只有 Virtual Audio Cable 和 Hi-Fi Cable 可以，因为它们是唯一支持 192000 采样率的电缆，这正是 RDS Spy 工作所需的。设置 Hi-Fi Cable 时，只需在 Windows 播放和记录属性中将采样率设置为 192000。按照以下说明设置 Virtual Audio Cable：

1. 你需要下载并安装 Virtual Audio Cable (VAC)。由于试用版支持三个电缆，对于此任务足够了。VAC 试用版的音频不会有问题。

2. 转到开始 -> Virtual Audio Cable -> 控制面板。你可能需要管理员身份打开虚拟控制面板。

3. 创建两个最大采样率为 192000 的音频电缆（使用 SDR 需要两个，使用 SDR 需要一个）。更改选项后确保点击 Set 按钮以永久保存。

![](img/33eab9643eb7fbb4bf9363c117190041_411_0.png)

4. 在 Windows 记录和播放选项中，在高级选项中将每个电缆设备的采样率设置为192000 Hz。你可以通过右键点击电缆设备、点击属性然后进入高级选项卡来访问高级选项。将默认格式设置为 192000 Hz。对记录和播放选项卡中的所有电缆设备执行此操作。

![](img/33eab9643eb7fbb4bf9363c117190041_413_0.png)

![](img/33eab9643eb7fbb4bf9363c117190041_414_0.png)

现在按照以下说明在 SDR 中使用 RDS Spy：

1. 从 http://rtl-sdr.ru/page/vse-dostupnye-na-etom-sajte-plaginy-s-kratkim-opisaniem 下载 MPX Output SDR 插件（注意该页面为俄语，必要时请 Google 翻译），并将其安装 SDR。

2. 打开 SDR并将输出音频设备设置为已设置采样率为192000 的 Virtual Audio Cable。调到一个使用 WFM 模式且带有 RDS 的广播 FM 电台。

3. 在 MPX Output 插件中选择虚拟电缆作为音频设备并点击“Enable MPX output”。

4. 打开 RDS Spy 并进入配置（Configure）-> 选择 RDS 源（Select RDS Source）。

5. 选择声卡（Sound Card）选项卡，然后在输入音频设备下选择虚拟电缆设备，并将声卡输入模式选择为“Direct RDS/ MPX (192 kHz)”。点击确定。

![](img/33eab9643eb7fbb4bf9363c117190041_415_0.png)

6. RDS Spy 现在应该解码 RDS 信号。

作为替代方案，你可以配合 SDR 使用 Spy。要使用 SDR，必须像上面的设置说明所示设置两个采样率为192000 的 Virtual Audio Cables。

1. 打开 SDR。

2. 在 SDR 中点击左下角的声卡按钮，然后选择 RX 输出（到扬声器）下的第一个虚拟电缆设备。

![](img/33eab9643eb7fbb4bf9363c117190041_416_0.png)

3. 点击左下角的带宽（Bandwidth）按钮，然后将输出设置为192000。

![](img/33eab9643eb7fbb4bf9363c117190041_417_0.png)

![](img/33eab9643eb7fbb4bf9363c117190041_418_0.png)

7. 可选（如果你想收听 FM 音频）：转到**开始菜单 -> Virtual Audio Cable -> Audio Repeater (MME)**。

8. 可选（继续）：将 Wave in 设置为第二个虚拟音频电缆，并将 Wave out 设置为扬声器。这将允许你同时收听 FM 电台音频。

![](img/33eab9643eb7fbb4bf9363c117190041_419_0.png)

9. 打开 RDS Spy 并转到 Configure（配置）-> Select RDS Source（选择 RDS 源）。

10. 选择 Sound Card（声卡）选项卡，然后在 Input audio device（输入音频设备）下选择第二个虚拟音频缆设备，并将 Sound Card Input Mode（声卡输入模式）设置为“Direct RDS/MPX (192 kHz)”。点击 OK。

11. RDS Spy 现在应该正在解码 RDS 信号。

对于感兴趣的人，还有一个 GNU Radio RDS 解码器实现，它对于学习如何解码 RDS 也非常有用。可以在此处获取：https://www.cgr.org/wiki/RDS。

# 收听 SCA/SCMO FM 子载波通道

在某些国家，标准广播 FM 收音机包含“子载波”，其中包含数据或额外的音频服务。此类数据子载波的一个例子是 RDS，在上面的教程中对其进行了解释。在某些国家，存在 SCA 子载波，用于提供如盲人朗读服务等额外传输。可以通过 SDR# 配合 MPX Output 插件或 HDSDR、Virtual Audio Cable 和 SDR# 的组合来收听这些音频 SCA 传输。SDR# 的 MPX Output 插件可以从此列表下载：http://rtlsdr.ru/page/vse-dostupnye-na-etom-sajte-plaginy-s-kratkim-opisaniem（注意该页面为俄语，如有必要请使用 Google 翻译）。

你可以通过使用 SDR# 中的 FM MPX 频谱或 HDSDR 中的音频瀑布图来检查你所在是否有音频 SCA 服务，就像上面的 RDS 教程所示一样。音频 SCA 信号位于任何 RDS 信号的右侧。
