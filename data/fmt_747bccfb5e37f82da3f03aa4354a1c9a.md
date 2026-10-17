
![](img/33eab9643eb7fbb4bf9363c117190041_204_0.png)

## 更新 Kepler 文件与获取卫星过境列表

5. 现在你需要更新你的 Kepler 文件。该文件包含卫星位置信息，由于卫星随时间推移会在轨道上漂移，因此需要定期更新。前往 `File -> Update Keplers` 执行此操作。确保在更新时已连接互联网。

6. 现在你可以前往 `File -> Satellite Pass List` 寻找 NOAA 卫星飞过头顶的时间。同时请记录过境的频率。

### 新西兰奥克兰 (36°55'S 174°35'E) 的卫星过境列表

高度在 8.0 度以上，且最大仰角 (MEL) 超过 20.0 度

从 2013-05-12 16:28:41 新西兰标准时间 (2013-05-12 04:28:41 UTC) 开始

| 卫星 | 方向 | MEL | 经度 | 本地时间 | UTC 持续时间 | 频率 |
|---|---|---|---|---|---|---|
| NOAA 18 | N | 43W | 166E | 05-12 18:37:46 | 04:37:46 | 11:11 | 137.925 |
| NOAA 19 | N | 49W | 166E | 05-12 18:00:14 | 06:00:14 | 11:03 | 137.620 |
| NOAA 16 | S | 47W | 178E | 05-13 00:55:06 | 12:55:06 | 11:22 | 137.100 |
| NOAA 19 | S | 38W | 185E | 05-13 01:21:50 | 13:21:50 | 10:51 | 137.915 |
| NOAA 19 | S | 21W | 182E | 05-13 02:37:06 | 14:37:06 | 09:12 | 137.900 |
| NOAA 16 | S | 24W | 171E | 05-13 03:39:35 | 15:39:35 | 09:22 | 137.620 |
| NOAA 18 | S | 28W | 165E | 05-13 04:02:44 | 16:02:44 | 10:26 | 137.915 |
| NOAA 19 | S | 29W | 162E | 05-14 04:44:34 | 14:44:34 | 10:58 | 137.100 |
| NOAA 18 | S | 38W | 165E | 05-13 06:18:31 | 17:18:31 | 10:39 | 137.620 |

当卫星出现时，打开 WtoImg，然后进入 `File -> Record`，并点击 `Auto Record`。当卫星出现在地平线上时，录制和解码会自动开始。根据卫星过境列表，当卫星消失时会自动停止。由于某些原因录制没有及时开始，你可以点击 `Manual Test` 按钮开始解码。

| 选项 | 值 |
| :--- | :--- |
| 仅记录（如果启用则显示图像） | |
| 录制并自动处理 | |
| 创建图像(s) | Image Settings... |
| 创建视频 | Movie Settings... |
| 将图像添加到网页 | Web Page Settings... |
| 最少扫描行 | 0 (0:00) |
| 删除音频文件 | never |
| 删除原始图像 | never |
| 删除地图 | never |
| 删除图像 | never |

8. 打开 SDR#，在 `Audio Output` 下拉框中选择你正在使用的音频管道方法，然后调谐到卫星广播的频率。在 SDR# 的 `Configure` 按钮下调整增益设置，以便获得良好的信号接收。将接收模式设置为 `WFM`，滤波器带宽设置为 `34 kHz`，并将 `Filter Audio` 设置为 `OFF`。确保取消勾选 `Snap to Grid`（捕捉网格）可能也有帮助。

9. 由于 RTL-SDR 的频率并不准确，且由于多普勒效应，信号可能不在其精确的频率上。只需调整 SDR# 中的频率，直到调谐条对准卫星信号中心即可。

10. 调整 SDR# 中的 `AF Gain` 和/或 Windows 音量设置，使 WXtoImg 右下角的音量条显示绿色。

![](img/33eab9643eb7fbb4bf9363c117190041_207_0.png)

11. WXtoImg 现在应该正在解码并显示接收到的图像。你可能需要定期调整频率使信号居中，因为多普勒效应会导致其移动。然而，对于 RTL-SDR，调整多普勒偏移并不关键，滤波器带宽设置为大于 `34 kHz`（尝试 `36-40 kHz`）即可接收整个信号。

12. 一旦完全接收图像，可以使用 `Enhancement` 菜单下的选项进行处理。

## ORBITRON 教程

使用名为 Orbitron 的程序，可以让 SDR# 在 NOAA 和其他卫星出现在地平线上时自动调谐。虽然对 SDR# 并非完全必要，但 Orbitron 将有助于补偿多普勒效应引起的卫星漂移。

1. 从 `http://www.starr.pl/` 下载并安装 Orbitron。

2. 从 `http://www.starr.pl/orbitron/files/mydde.zip` 下载 Orbitron DDE 驱动（镜像地址见）。将文件提取到 Orbitron 安装目录（通常在 `Program Files (x86)\Orbitron`）。

3. 从 `http://public-s3.amazonaws.com/SatelliteTracker.zip` 下载 SDR# 插件（镜像地址见）。虽然随附的 readme 文件带了安装说明，但某些说明对你不起作用。你可以按照下面的步骤。

4. 将 SDR# 插件文件提取到 SDR 目录。使用记事本或其他编辑器打开 `Plugins.xml`。在 `<Plugins></Plugins>` 标签内添加行：（此处应为代码内容）。

5. 以管理员模式打开 Orbitron（如果是 Windows Vista/7/8），右键点击并选择以管理员身份运行。Orbitron 可能会全屏打开。如果需要，按 `Alt+Enter` 退出全屏。你可能会看到 TLE 更新界面。你可以保持所有框默认。点击带有地球和闪电图标的更新按钮。Orbitron 将下载新的 TLE 文件。TLE 文件包含轨道信息，需要每几天更新一次。以管理员模式运行 Orbitron 非常重要，否则可能写入 TLE 文件。如果没有看到界面，可以通过主 Orbitron 标签中的 `Setup` 图标进入。

![](img/33eab9643eb7fbb4bf9363c117190041_209_0.png)

6. 为了让 Orbitron 准确跟踪卫星，Windows PC 时间准确很重要。Orbitron 提供将 PC 时间同步到提供准确时间的 NTP 服务器的方法。在设置界面点击 `Time Synch` 标签，点击 `Synchronise PC` 按钮自动同步时间。如果你的 PC 始终连接互联网，你可能还想勾选 `Synchronise PC clock when Orbitron starts` 复选框。

![](img/33eab9643eb7fbb4bf9363c117190041_210_0.png)

7. 关闭 Orbitron。现在以管理员模式打开记事本（通过右键点击开始菜单中的快捷方式）。

8. 在记事本中，点击 `File -> Open` 并浏览到你的 `Orbitron\Config` 文件夹。Orbitron 可能安装在 `Program Files (x86)\Orbitron`。打开 `Setup.cfg`。

9. 在 `Setup.cfg` 文件的底部添加这两行：

```
[Drivers]
SDRSharp=SDRSharp.exe
```

![](img/33eab9643eb7fbb4bf9363c117190041_211_0.png)

现在打开 Orbitron 并点击底部设置你的位置。如果你不知道自己的经纬度，可以在右侧选择你的城市。

![](img/33eab9643eb7fbb4bf9363c117190041_211_1.png)

11. 接下来点击 `Load TLE` 并加载 `noaa.txt` 文件，以及你感兴趣跟踪的其他卫星的文件。

![](img/33eab9643eb7fbb4bf9363c117190041_212_0.png)

12. 对于天气卫星图像，我们对 NOAA 15、18 和 19 号卫星，因为它们是唯一运行的，因此在它们旁边打钩。双击卫星名称将选中它并在地图窗口中显示。

### Orbitron 3.71 界面示例

![](img/33eab9643eb7fbb4bf9363c117190041_213_0.png)

奥克兰: 174.7582' E, 36.0551' S

| 方位 | Dlink/MHz | 接收/多普勒 | Dlink 模式 | 驱动 |
|--- | --- | --- | --- | --- |
| 289.3 | 145.000 | 144.99786 | FM-W | SDRSharp |
| 仰角 | 上行/MHz | 发射/多普勒 | 上行模式 | Satellite |
| -11.7 | 145.000 | 145.00214 | | |

与驱动程序的 DDE 会话未激活

Orbitron 3.71 - ©2001-2005 by Sebastian Pohl

13. 现在前往 `Rotor/Radio` 标签，将 `Radio` 模式设置为 `FM-W` 并将 `Driver` 设置为 `SDRSharp`。点击 `Driver` 下拉框旁带有两个窗口的图标，并确保它处于按下状态。第一次按下此按钮时，可能会被要求安装驱动程序。点击是，然后浏览到 Orbitron 文件夹并选择早早复制的 `MyDDE.exe` 文件。

#### 文件选择对话框示例

| 名称 | 修改日期 | 类型 | 大小 |
| --- | --- | --- | --- |
| Lang | 11/05/2013 11:20... | 文件夹 | |
| Notes | 11/05/2013 11:20... | 文件夹 | |
| Output | 11/05/2013 11:20... | 文件夹 | |
| Tie | 19/03/2014 9:42 p... | 文件夹 | |
| MyDE.exe | 26/02/2005 1:00 a... | 应用程序 | 335 KB |
| Orbitron.exe | 8/09/2005 12:00 a... | 应用程序 | 1,218 KB |
| lunins000.exe | 11/05/2013 11:20... | 应用程序 | 654 KB |

文件名：`MyDDE.exe`

文件类型：`DDE 驱动文件 (*EXE)`

14. 打开 SDR#，点击 `Play`，然后进入 Orbitron 插件。在 `Enable` 旁边打一个钩，将 `Tracking Software` 选项设置为 `Orbitron`，然后点击 `next`（下一步）。现在在 Orbitron 中双击卫星名称，应该会自动在 SDRSharp 中设置正确的经过多普勒修正的频率。

![](img/33eab9643eb7fbb4bf9363c117190041_214_0.png)

15. SDR# 现在应该自动吸附到正确的频率并自动调整多普勒效应。你仍需要手动设置正确的滤波器带宽并将模式设置为 `WFM`。此外，由于 RTL-SDR 的频率并不准确，你需要在 SDR# 配置框中调整 `PPM` 修正值，以确保信号居中。

16. 如果你想让 Orbitron 在卫星进入范围时就让 SDR# 自动调谐到该卫星：

17. 转到 `Miscellaneous`（杂项）选项卡，确保选中了 `AOS Notification: Show Notice`（AOS 通知：显示通知），并将 `elevation`（仰角）设置为 `0`。（如果你只想在卫星升得更高、接收效果更好时开始调谐频率，请增加仰角）。

![](img/33eab9643eb7fbb4bf9363c117190041_215_0.png)

18. 转到 `Extra`（额外）选项卡，确保勾选了 `AOS Notification: Make satellite active`（AOS 通知：激活卫星）。

![](img/33eab9643eb7fbb4bf9363c117190041_216_0.png)

19. 最后，如果需要，可以使 WXtoImg 自动输出最新卫星图像的实时网页。此选项可以在 WXtoImg 的 `Options`（选项）-> `Auto Processing Options`（自动处理选项）-> `Web Page Settings`（网页设置）下找到。

# METEOR-M 俄罗斯 LRPT

## 气象卫星指南

![](img/33eab9643eb7fbb4bf9363c117190041_217_0.png)

## METEOR-M 简介

Meteor-M N2 是一颗极轨道俄罗斯气象卫星，于 2014 年 7 月 8 日发射。它的主要任务是天气预报、气候变化监测、海水监测/预测以及空间天气分析/预测。

该卫星目前处于激活状态，发射低分辨率图像传输（LRPT）信号，用于广播实时气象卫星图像，类似于 NOAA 卫星产生的 APT 图像。然而，LRPT 图像要好得多，因为它们以数字信号传输，图像分辨率比旧的模拟 NOAA APT 信号高 12 倍。

将本节开头显示的新西兰图像与上方 NOAA APT 教程部分显示的图像进行比较，即可看到分辨率的差异。一些 Meteor 气象示例图像可以在 `http://meteor.robonica.ru/septembers-gallery/` 找到，并可以在 Orbitron 或在线通过 `http://www.satview.org/?sat_id=40069U` 跟踪卫星。白天的气象图像使用可见光生成，晚上则使用红外线生成。

可以使用 RTL-SDR 以及如 HackRF 等 SDR 配合一些免费软件来接收和解码这些图像。来自 Meteor-M N2 的 LRPT 图像在 `137.1 MHz` 附近以右圆极化传输，因此通常使用与 NOAA 卫星类似的卫星天线，如十字形或四线螺旋天线。更多信息请参见天线指南。

由于 LRPT 是数字信号，接收强度必须良好，请确保使用放置在高处且视野开阔良好的卫星天线。在某些接收不良的情况下，可能还需要天线处的低噪声放大器（LNA）以及一些带通或带阻滤波器。

## 接收卫星图像：Windows 教程

为了在 Windows 上接收这些图像，你首先需要下载并安装以下内容：

- **Audacity**。免费的音频编辑软件。从 `http://audacity.sourceforge.net/` 下载。
- **LRPT BPSK/QPSK 解调器**。从 `https://www.dropbox.com/s/yic/software.zip` 下载（镜像：`http://bit.ly/yicop`）。提取 `LRPT.exe`，压缩包中的其他文件是不需要的。
- **LRPTOfflineDecoder**。从 `http://meteor.robonica.ru/soft/` 下载最新版本（2014.09.01 的镜像）（版本：`http://bit.ly/IUKS4Y`）。

由于这颗卫星非常新，解码过程不像 NOAA 卫星那样精炼。以下步骤概述了该过程：

1. 打开 SDR#，并在配置菜单中将 RTL-SDR 的采样率更改为 `1 Msps`。

2. 当 Meteor-M2 即将经过时（使用 Orbitron 确定时间），在 SDR# 中调谐到 `137.1 MHz`。确保设置了 `Correct IQ`，如果你使用的是基于 RTL2832 的转接器，请确保已启用偏置调谐（offset tuning）。

3. 一旦信号出现，首先确保它在瀑布图中尽可能居中。然后使用标准 SDR# 安装中默认包含的 `Recording` 插件录制一个 `8-bit PCM` 基带文件。

![](img/33eab9643eb7fbb4bf9363c117190041_219_0.png)

4. 卫星经过且信号消失后，停止录制，然后在 Audacity 中打开生成的 `.wav` 文件（记住 SDR# 将其录音保存在与可执行文件相同的文件夹中）。

5. 在 Audacity 的左下角将采样率更改 `130000 Hz`。

![](img/33eab9643eb7fbb4bf9363c117190041_220_0.png)

6. 通过 `File > Export`（文件 > 导出）将重采样后的文件导出为新的 wav 文件。然后选择格式为 `WAV (Microsoft) signed 16-bit PCM`。将新的 wav 文件保存到方便的文件夹中。

7. 现在打开 LRPT 程序，通过点击输入文件名框加载刚刚从 Audacity 导出的重采样 `.wav` 文件。

![](img/33eab9643eb7fbb4bf9363c117190041_220_1.png)

8. 确保选中了 `Swap IQ`（交换 IQ）。

![](img/33eab9643eb7fbb4bf9363c117190041_220.png)

9. 在窗口中间移动滑块到信号最强点。点击右下角的开始按钮。

![](img/33eab9643eb7fbb4bf9363c117190041_221_0.png)

10. 如果看起来像一个 X 或正方形，尝试将符号率从 `72000` 更改为 `80000`。

11. 如果你看到四个簇，遗憾的是卫星处于 `80K` 模式，目前无法解码。

![](img/33eab9643eb7fbb4bf9363c117190041_222_0.png)

12. 如果你在星座图中某处看到四个簇，则可以继续。将滑块移回起始位置。

13. 通过点击左侧输出文件名旁的 `Change` 按钮选择解码 RAW 输出文件的保存位置。默认情况下，输出文件将保存为 `C:\Meteor_001.raw`。

| 输出文件名 |
| --- |
| `\Meteor_001.raw` |

14. 点击程序右下角的 `Start` 按钮开始解码过程。观察滑块并等待到达末尾，然后点击停止。程序不会自动停止，因此必须记得点击停止按钮。停止后点击退出按钮。
