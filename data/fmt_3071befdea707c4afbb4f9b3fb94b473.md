
- 4. 在 General Settings（常规设置）下将你的接收器命名为 RTL-SDR。
- 5. 将数据源更改为 "AVR or Beast Raw Feed"。
- 6. 保持 IP 地址为 `127.0.0.1`（除非使用远程服务器），但如果使用 ADSB#，将端口号更改为 `47806`；如果使用 RTL1090，则更改为 `31001`。（下图显示了使用 RTL1090 时应使用的设置。）

![](img/33eab9643eb7fbb4bf9363c117190041_182_0.png)

上述的大多数解码器会将解码后的 ADS-B 数据通过本地（或根据需要通过公共）网络连接发送。有几种软件选项可以接收并显示这些网络数据。这里我们展示了四种最流行的，其中三个是免费的，一种是付费的并提供试用选项。要使用这些程序，你需要同时运行你的 ADS-B 解码器。

3. 现在，使用 Windows 资源管理器导航到你安装 PlanePlotter 的文件夹。默认安装路径为 `C:\Program Files (x86)\COAA\PlanePlotter`。在此文件夹中找到 `google_aircraft.kml` 文件并双击它。该文件应自动用 Google Earth 打开并显示飞机的俯视图。你也可以打开 `google_cockpit.kml` 来查看飞机的模拟座舱视图。

若要配合 Virtual Radar Server 安装 `basestationsq` 数据库，请遵循 <http://planeplotter.pbworks.com/w/page/17117301/Databases> 中列出的说明。

## ADSBSCOPE

AdsbScope 是一款免费的 ADS-B 雷达程序，可以从 <http://www.sprut.de/electronic/pic/projekte/adsb/adsb_en.html#downloads> 下名为“ZIP-File with all relevant data (13 MB)”的链接进行下载。有些人更倾向于使用 adsbScope 而上述其他程序，因为它是免费的且不基于网络浏览器。adsbScope 的最新版本还为 ADSB# 和 RTL1090 提供了简单的设置选项。要安装并使用 adsbScope，请遵循以下说明。

- 1. 下载并解压 adsbScope 到文件夹。导航到 `pc_software/adbscope/26` 文件夹。运行 `adsbcope26_16384.exe` 打开程序。
- 2. 进入 `other` -> `Network` -> `Network setup`。
- 3. 显示如下屏幕。在 `presets`（预设）下，根据你选择的解码器点击 ADSB# 或 RTL1090。点击 `local`（本地）按钮，除非你正在使用共享服务器，此时请输入服务器的 URL。如果你更改了任一解码器的端口，请将 `RAW-data-client` 框中的 `Portnumber` 设置为相同的值。

![](img/33eab9643eb7fbb4bf9363c117190041_189_0.png)

- 4. 现在开启 RTL1090 或 ADSB#。
- 5. 在 adsbScope 中点击 `start RAW-data CLIENT` 按钮。按下后，按钮将变为彩色，ADS-B 数据现在应显示在 adsbScope 中。
- 6. 你可以使用鼠标在地图上移动，并使用缩放按钮放大或缩小。你也可以点击地图按钮下载屏幕显示区域的地图。
- 7. 使用鼠标和缩放将十字准中心对准你的接收器位置。
- 8. 进入 `Navigation` -> `set Receiver Location` 将接收器设置为十字准的当前位置。

![](img/33eab9643eb7fbb4bf9363c117190041_190.png)

ADSBScope 还可以创建一个最大范围图，该图可以覆盖一段时间，并显示你的天线工作情况。它将为随时间看到的每架飞机绘制一条线。要开启它，只需遵循以下步骤：

- 1. 进入 `Config` -> `Maximum Range` 并启用‘show all altitudes’（显示所有高度）。
- 2. 确保勾选了 `View` -> `Maximum Range`。

## BASESTATION

BaseStation 是原始的 ADS-B 显示软件之一。它出现在仅有专用 ADS-B 接收器的那个时代。许多用户更喜欢此软件，因为它简单易用，且能与专业雷达显示配合使用。要让 BaseStation 配合 RTL1090 或 ADSB# 工作，请遵循这些说明。要让它配合 Modesdeco 工作，你可以跳到第 4 步打开 BaseStation - 如果你想使用 BaseStation 的易用性，强烈建议使用 modesdeco 为解码器。

- 1. 下载并安装 com0 模拟器 <http://sourceforge.net/projects/com/>。安装期间，你可能会遇到未签名驱动程序的问题。要解决这个问题，你需要禁用驱动程序签名。安装 com0 后，重启电脑。启动 com0 后，根据你的系统设置，注意对应的 COM 端口号（通常是 COM6 或 COM7）。

![](img/33eab9643eb7fbb4bf9363c117190041_191_0.png)

- 2. 下载并安装 modesdeco（从 <http://ads.github.com/> 下载并解压 `.zip` 文件）。
- 3. 在文件夹中创建一个 `.bat` 文件。
- 4. 在 `.bat` 文件中输入以下内容：

```
@echo off
mode com=COM6 baud=115200,n,8,1
modesdeco.exe -r COM6 -w 127.0.0.1:3000,127.0.0.1:30001
```

*（请根据实际端口号修改代码中的 COM6 或 COM7）*

- 5. 运行该 `.bat` 文件。
- 6. 打开 BaseStation。
- 7. 在 BaseStation 中，进入 `Network` -> `Network setup`。
- 8. 在 `presets` 下，点击 ADSB# 或 RTL1090。
- 9. 点击 `local` 按钮。如果你更改了解码器的端口，请确保 `RAW-data-client` 区域中的 `Portnumber` 一致。
- 10. 开启 RTL1090 或 ADSB#。
- 11. 此时 BaseStation 应该能显示飞机数据。

如果你希望在导航显示窗口中显示航点（Waypoints）、导航台（NavAid）和 VOR 等地面符号，请从 <http://data.x-plane.com/get_data.html> 下载 X-Plane 9.00-9.70 数据。将数据解压到文件夹，并在 XHSI 中将 AptNav Resources 目录设置为你解压数据的目录。

![](img/33eab9643eb7fbb4bf9363c117190041_197_0.png)

# 监测军用飞机

虽然军用飞机配备了 ADS-B Mode S 转发器，但它们通常不传输位置信息。尽管如此，仍有一些军用飞机爱好者乐于接收并记录来自军用机的 ADS-B 信号。即使接收不到位置信息，观测者仍然可以获取军用机的十六进制代码（hex code）、注册号、机型、基站位置和高度。

milaircomms.com 的爱好者们为树莓派和 Windows 开发了自定义的 ADS-B 软件，称为 MilAirComms1090。该软件可以记录军用飞机数据，并将其网站上许多志愿者提供的数据进行上传和聚合。由于有志愿者在世界各地记录数据（主要在美国和欧洲），通过日志有可能发现军用飞机过去出现过的地方。你可以在 <http://milaircomms.com/mil_air_modes_logger.html> 找到更多关于该项目的信息。

另一个类似网站 <http://www.live-military-mode-s.eu/> 的类似软件可以在 <http://www.live-military-mode-s.eu/share/V4.0/> 找到，其教程详见 <http://www.jc-images.de/docs/RTL1090_Mode_S_Logger_Virtual_Server_Configuration.pdf>。

# 滑翔机和直升机的 ADS-B：FLARM

滑翔机和某些直升机等小型飞机使用一种改进版的 ADS-B，称为 FLARM。FLARM 是 Flight alarm（飞行报警）系统的缩写。FLARM 是一种低成本、低功耗的 ADS-B 替代方案，通常用于轻型飞机的避障。它的发明是因为滑翔爱好者需要一种更廉价、更易安装的 ADS-B 避障系统，以适应滑翔机中常见的近距离飞行。

尽管信号要弱得多，但只要使用正确的天线，就可以像商业飞机一样追踪这些轻型飞机。这对于住在滑翔俱乐部附近的人来说可能很有趣。FLARM 信号在 `868 MHz` 传输，其强度比标准 ADS-B 信号有效弱 100-100 倍，但仍然可以接收。

<http://wiki.glidernet.org/start> 的 Open Glider Network 是滑翔机追踪爱好者群体使用 RTL-SDR 和自定义软件实时追踪滑翔机。在他们的网站 <http://live.glidernet.org/> 和 <http://live.glidernet.org/3D/> 上可以看到聚合的实时滑翔机追踪示例。Open Glider Network 项目主要活跃在欧洲。

# NOAA 气象卫星 (APT) 指南

![](img/33eab9643eb7fbb4bf9363c117190041_199_0.png)

## NOAA 气象卫星简介

美国 NOAA（国家海洋和大气管理局）气象卫星每天会多次经过你的所在地。当它们飞过时，每颗 NOAA 气象卫星都会广播自动图像传输（APT）信号，其中包含你所在区域的实时天气图像。RTL-SDR 结合良好的天线、如 SDR# 等 SDR 程序以及解码程序，可以下载并显示这些实时图像。

目前有三个活跃的 NOAA 卫星：NOAA 15、NOAA 18 和 NOAA 19。每颗卫星以约 `137 MHz` 的频率传输，采用右旋圆极化（RHCP）。

## NOAA 气象卫星接收教程

为了设置 NOAA 气象卫星接收站，你需要：

- 音频管道方法。如果没有设置，请查看附录 A。
- 适用于 `137 MHz` 的圆极化天线。
- 用于解码的 WXToImg 等。

## NOAA 气象卫星天线

NOAA 卫星以 `137 MHz` 附近的频率发送圆极化信号。对于卫星接收，理想的是指向天空的圆极化天线。最常用的两种天线是字形线（turnstile），它是两个成 90° 角的偶极子排列，有时被称为交叉偶极线（cross dipole）。字形线有两种类型。

四臂螺旋线（QFH）是一种由 PVC 管和电缆制成的圆极化天线。大多数人报告 QFH 的接收效果优于字形线，但人使用字形线。另一种有效的天线是双十字（DCA），它基本上是以特定方式排列的四个偶极子，产生圆极化信号。圆锥天线（discones）或四分之一波地线天线也可能接收信号，但如果不是圆极化天线，信号会严重衰减。更多信息请参见天线指南。

许多人报告，天线处的低噪声放大器（LNA）和广播滤波器有助于接收。请参见 LNA 部分和滤波器部分。

## WXTOIMG 软件教程

WXtoImg 是一个适用于 Windows、Linux、OSX 甚至树莓派的免费气象卫星解码程序。它可以解码 APT 信号并告知你卫星通过的频率。

1. 首先，从 <http://www.wxtoimg.com/> 下载并安装 WXToImg。
2. 打开 WXToImg，通过 Options -> Ground Location 设置你的地面站位置（即天线的坐标）。你所在的城市应该足够，但如果你愿意，输入精确的经纬度和高度会更准确。位置信息用于确定卫星何时经过你的上空。

![](img/33eab9643eb7fbb4bf9363c117190041_203_0.png)

3. 在 WXToImg 中设置你正在使用的音频管道方法。进入 Options -> Recording Options，并确保声卡选项下选择了正确的音频设备。
4. 此外，在此窗口中，你还可以调整“仅在活跃 APT 卫星位于头顶时记录”、“最大仰角（度）”以及“仅当卫星位于（度）以上时记录”设置。如果你的天线天空视野良好，但发现 WXtoImg 停止记录或启动不够快（尽管 SDR# 中存在 APT 信号），你可能需要减小默认值。

接收效果会更好，因为通天线的路径更畅通。当卫星位于地平线较低位置时，由于障碍物，接收效果可能会很差。你应该根据你的地形设置这些值。
