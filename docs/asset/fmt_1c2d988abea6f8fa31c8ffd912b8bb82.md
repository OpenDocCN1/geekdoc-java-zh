
标准以太网的速率为 100 Mbits/s，因此是足够的（假设网络没有被其他应用程序占用并且考虑了开销）。相比之下，USB 2.0 的速率为 480 Mbits/s。无线 802.11a 和 802.11g 网络的速度为 54 Mbits/s，但这是理论最大值，通常无法达到这个速度。较新的 802.11n 无线标准速率高达 300 Mbits/s，应该满足最大采样率的要求。

注意其他因素如网络拥塞、以太网线缆长度、WiFi 连接质量、WiFi 设备数量以及嵌入式设备速度可能会影响你的性能。在 Windows 上测试网络速度尝试使用 LAN Speed 测试软件 <http://www.totuso.com/downloads.html>。

在实际情况下，你应该预期使用较低的采样率，例如 1 Msps，特别是如果你正在使用像树莓派这样的嵌入式设备。如果有其他用户或存在显著干扰，你应该预期 WiFi 可能会出现问题。

## 在 Windows 上使用 rtl-tcp

请遵循以下说明：

1. 从 <http://sdr.osmocom.com/trac/attachment/wiki/rtl-sdr/RelWithDebInfo.zip> 下载 Windows 版本的 rtl-sdr 预编译二进制文件。
2. 将 `RelWithDebInfo.zip` 文件解压到文件夹中。
3. 使用 Windows 命令行导航到解压压缩包的文件夹。
4. 进入 `x32` 文件夹。
5. 运行 `rtl-tcp -h` 查看可用命令列表。

![](img/33eab9643eb7fbb4bf9363c117190041_439_0.png)

### 在 SDR# 中使用 rtl-tcp

1. 在命令行提示符输入 `ifconfig` 查找本地 IP 地址。你的 IP 地址将列在以太网适配器：局域网连接标题下。
2. 在命令行提示符中使用以下命令，其中 `IP_ADDRESS` 应该是运行 `rtl_tcp` 的电脑 IP 地址。
3. 在 SDR# 中，选择 RTL-SDR/TCP 并在配置菜单中输入服务器的 IP 地址。采样率和增益控制可以在 SDR# 中调整。
4. 点击 Play（播放）。

### 在 SDR Touch 中使用 rtl_tcp

1. 在命令行提示符中使用以下命令（其中 `-s` 设置采样率）。注意 SDR Touch 的采样率必须设置为 1024000。

```
rtl_tcp -a IP_ADDRESS -s 1024000
```

2. 打开 SDR Touch。
3. 在菜单上向下滚动到 Remote（远程）按钮。点击此按钮。
4. 以 `ip_address:port` 的格式输入 IP 地址和端口，然后触（点击）connect（连接）。

`rtl_tcp` 会在 RTL-SDR 驱动安装过程中自动安装，并可以像在 Windows 上一样使用。注意在 Linux 中查找 IP 地址的命令是 `ifconfig`。较新的 Linux 内核似乎存在一个 bug，由于电源管理会导致 `rtl_tcp` 出现卡顿。这可以通过恢复旧版本内核或运行一个使用 100% CPU 的进程（如 `top -d .1`）来修复。

## 在 LINUX 上流传输 MP3: RTL_FM

如果你只想通过网络流传输 FM 音频，可以使用 `rtl_fm` 将输出通过到 `sox` 将其转换为 mp3 文件，然后使用 `socat` 将输出到网络。在接收端，可以使用 `netcat` 连接到 TCP/IP 流。所需的带宽比 `rtl_tcp` 低，因为它只需要大约 8 kb/s，几乎任何网络（包括互联网和 WiFi）都能处理。

在 Ubuntu 上，可以通过以下命令安装 sox、socat 和 netcat：

```
sudo apt-get install sox
sudo apt-get install socat
sudo apt-get install netcat
```

编码为 mp3 和播放接收到的音频的命令来自 `sox`，你需要在服务器和监听器电脑上安装 `sox`。如果你听不到声音，可能还需要在监听端通过 `sudo apt-get install libsox-fmt-mp3` 安装 sox mp3 库。你可以使用一个从 SDR 播放 mp3 压缩音频到扬声器的命令来测试 `sox` 是否在信号上正常工作：

```
rtl_fm -M fm -f 106.4M -s 12k -g 50 | socat -raw r12k -es -b16 -V1 -tmp3 | play -t mp3
```

要通过 TCP 发送音频，使用以下 socket 命令：

```
rtl_fm -M fm -f 106.4M -s 12k -g 50 | socat -raw r12k -es -b16 -V1 -tmp3 | socat -u tcp-listen:8080
```

在监听端使用以下命令：

```
netcat IP_ADDRESS 8080 | play -t mp3
```

其中你应该将 `IP_ADDRESS` 更改为服务器的 IP 地址。你还应该将频率、带宽和其他合适的 `rtl_fm` 标志更改为你正在监听的信号所需的参数。

## 热力图扫描 (HEATMAP SCAN)

![](img/33eab9643eb7fbb4bf9363c117190041_443_0.png)

热力图可以帮助你发现频率频谱在哪些范围内接收到了信号。要实现这一点，可以使用官方 RTL-SDR 包包含的 Linux 和 Windows 软件 `rtl_power`（Windows: <http://sdr.osmocom.org/trac/attachment/wiki/rtl-sdr/RelWithDebInfo.zip>）。但请注意，我们强烈建议你使用 Kevinards 更新版本的 `rtl_power`，该版本可从 <http://gaastian.com/builds/> 获取。Kevinards 的驱动和 `rtl_power` 版本扫描的速度明显快于原始驱动。本教程将基于 Windows，但可以很容易适配到在 Linux 上运行；在 Linux 中运行 `rtl_power` 要容易得多。

要创建热力图，我们需要使用工具 `rtl_power`。该工具使用分箱（binning）记录宽带宽内的平均频率功率。为了解释分箱，我们使用一个例子：假设我们正在记录 1 MHz 的带宽，并选择使用 2 kHz 的分箱大小。那么热力图图像中的每个像素将代表 2 kHz 分箱大小的平均功率。因此，热力图图像将有 500 像素宽。

### 在 Windows 中创建热力图

请遵循以下说明。这些说明也可以适配于 Linux。在 Linux 中，`rtl_power` 是 RTL-SDR 驱动安装过程的一部分安装的。

1. 从 <http://sdr.osmocom.com/trac/attachment/wiki/rtl-sdr/RelWithDebInfo.zip> 下载 Windows 官方 RTL-SDR 版本并将文件解压到文件夹。
2. 从 <https://github.com/kerdard/rtl-sdr-misc/blob/master/heatmap/heatmap.py> 下载最新版本的 `heatmap.py`（旧镜像：<http://gaastian.com/tmp/heatmap.py.txt>），将其保存为具有 `.py` 扩展名的文本文件，并放在 `x32` 文件夹中 `rtl_power` 相同的文件夹内。
3. 从 <http://www.python.org/download/> 安装 Python 2.7 x32。你必须小心下载旧的 2.7 版本，并确保它也是 x32 版本。这是因为 PIL（Python 库）需要此版本。还要注意你安装 Python 的路径。
4. 在 Windows 中，在开始菜单中右键点击“计算机”并进入“属性”。选择“高级系统设置”，然后点击“环境变量”。在上方的用户环境变量窗口中，找到“Path”变量。
5. 从 <http://www.python.org/products/pil/> 安装图像库。
6. 使用命令行导航到 `rtl_power` 安装目录。然后输入以下内容：

```
rtl_power -f 106.4M:107M -2k -g 50 log.csv
```

7. 当你想停止运行 `rtl_power` 时，按下 CTRL+C。
8. 要生成热力图，输入以下命令：

```
python heatmap.py
```

![](img/33eab9643eb7fbb4bf9363c117190041_445.png)

## RTL_POWER 标志 (FLAGS)

可以通过命令行使用 `rtl_power -h` 找到更多标志，但这里解释最重要的标志：

- `lower:upper:binSize` 指定记录的频率范围。bin_size 指定每个像素代表的宽度（单位 Hz）。
- `-i` Interval 累计每个分箱平均功率的时间间隔。
- `-g` tuner RTL-SDR 的增益。
- `-c` crop percentage 频谱中心质量比边缘更高。此标志指定丢弃多少边缘。值越大效果越好，但扫描速度越慢。以小数（0.2）或百分比（20%）指定。
- `-d` downsampler filters 范围 0-9。越大效果越好。配置使用什么下采样滤波器。值越高越消耗 CPU。
- `-e` exit_timer `rtl_power` 运行的时间。
- `-1` single shot mode 执行一次运行并退出。

## RTL_POWER 图形界面 (GUI)

有一个名为 `rtl-pan` 的 Windows 图形界面可用于 rtl_power。它可以从 <http://sourceforge.net/projects/guifortlrpower/> 获取。它能够像 heatmap.py 一样生成热力图。

要使用 rtl-pan，从上述链接下载最新的 `rtlpan.exe` 文件并将其放置与 `rtlsdr.dll`、`libusb-1.0.dll` 和 `rtl_power.exe` 相同的文件夹中。然后双击 `rtlpan.exe` 启动程序。启动后，你可以选择所需的扫描频率范围、分箱大小、调谐增益和 PPM 偏移。运行软件一段时间将产生热力图，可以通过右上角的照片图标保存为图像。在编写本教程时，目前还没有选择裁剪大小和下采样滤波器等高级选项的选项。

# RTLDR 扫描仪

RTLDR 扫描仪是一款 Windows 工具，可以在宽带范围内生成 FFT（快速傅里叶变换）图表。你可以从 <http://eartearoak.com/software/rtl-scanner> 下载。它提供了一个 Windows 安装程序，该程序会自动下载运行软件所需的各种依赖项。在运行安装程序的“选择组件”部分，如果你不确定电脑上已安装哪些内容，请确保勾选所有需要安装的依赖项。

安装 RTLDR Scanner 后，只需在窗口底部的“开始”（Start）和“停止”（Stop）框中输入一个范围，并设置所需的增益。点击“开始”开始扫描。模式可以设置为连续（continuous）或单次（single）。在连续模式下，扫描器每次完成一次扫描都会持续刷新频谱；在单次模式下，扫描器执行一次扫描后停止。停留时间（dwell time）表示扫描器在记录功率值之前对范围进行平均处理的时间。增大该值有助于清理噪声图，但会减慢扫描速度。FFT 大小表示扫描期间使用的 FFT 分辨率。值越高，图表分辨率越高，能更清晰地显示信号结构，但会导致扫描速度变慢。RTLDR Scanner 还可以通过更改显示下拉菜单框中的设置，将频段扫描显示为频谱或 3D 频谱图。

最新版本的 RTLDR Scanner 还可以连接到外部 GPS 接收器，并结合 RTL-SDR 和 GPS 日志数据创建行驶时的无线强度热图。这对于无线电定位（即尝试确定无线电发射器的物理位置）非常有用。更多信息请参见下方的无线电定位章节。

![](img/33eab9643eb7fbb4bf9363c117190041_448_0.png)

# 使用 RTL SDR 扫描仪进行无线电定位

如上一节所述，RTL SDR Scanner 具有创建无线强度热图的功能，可用于无线电定位。换句话说，这意味着你可以带着运行 RTL SDR Scanner 的开启 GPS 的笔记本电脑行驶，寻找无线电发射器的位置。当你行驶时，信号强度将与你的 GPS 位置关联，从而创建信号强度热图。

RTLDR Scanner 兼容可通过 RS232、USB 或蓝牙串口输出 NMEA GPS 数据的外部 GPS 接收器。它在 Linux 上也兼容 GPSd（Linux GPS 守护进程）。

如果你的笔记本电脑没有内置 GPS 接收器，则需要使用外部接收器。大多数人已拥常用 GPS 接收器是 Android 或 iPhone 智能手机。在本教程中，我们将展示如何将常用的 Android 或 iPhone 手机作为带有蓝牙的 Windows 笔记本电脑的 GPS 接收器。这里的指令专门针对 Android，但可以通过 Cydia 商店中售价 1 美元的 TryGPSPOut 轻松适配越狱后的 iPhone。

1. 进入 Android 手机上的 Google Play 商店，下载由 Meowbox 开发名为“Bluetooth GPS Output”的应用。这是一个付费应用，但免费版可以运行约 10 分钟，让你足够的时间验证该应用是否按预期工作。完整版价格约为 1 美元，可以在应用商店找到。
   还有其他类似的免费应用可以尝试，但我们只成功让这个特定应用无故障地运行。
2. 现在开启你笔记本电脑和手机上的蓝牙。
3. 打开蓝牙 GPS 应用，按下设置按钮并选择“设置为可发现”（Make Discoverable）。
4. 现在你的手机将对笔记本电脑可见。配对这两个设备。注意，尽管设备已配对，应用右上角仍会显示“未连接”。这是正常的。
5. 在 Windows 中进入控制面板，点击“设备和打印机”标题下的“更改蓝牙设置”（Change Bluetooth Settings）。
6. 转到“COM 端口”（COM Ports）选项卡。注意哪个 COM 端口具有“输出”（Outgoing）方向。在所示的截图中为 COM6。

![](img/33eab9643eb7fbb4bf9363c117190041_451_0.png)

7. 将 RTL-SDR 插入电脑并打开 RTLDR Scanner。
8. 在 RTLDR Scanner 中进入 Edit->GPS。勾选 Enable。选择你识别的 COM 端口波特率设置为 9600。在类型框中选择 NMEA。
9. 现在当 EAS 消息播放时，它将显示在终端。

![](img/33eab9643eb7fbb4bf9363c117190041_452_0.png)

10. 国家气象局 Pleasant Hill 发布了测试，有效期至下午 12:30，涵盖堪萨斯州的 Leonworth、Wyandotte、Johnson 和 Miami 县，以及密苏里州的 Clay、Platte 和 Cass 县。
11. 使用以下命令开始监听并解码：

```
dsame.py --source scripts/soundcard-multimon-ng
```

# 解码紧急警系统 SAME 消息

在美国和加拿大，某些消息通过 SAME（特定区域编码）协议传输。Dsame 是一种 EAS 解码器，可配合 RTL-SDR 接收天气警报。解码 EAS 消息需要在电脑上设置并运行 RTL-SDR、multimon-ng 和 Python。运行程序时可以使用 fm 或 SDR# 作为输入。

## 在 Windows 上配合 SDR# 使用

1. 下载 dsame 和 multimon-ng，并将它们放在同一个文件夹中。multimon-ng 也可以从 dsame GitHub 页面下载。
2. 在 Windows 声音设置中，将你的首选音频方法设置为默认设备。（multimon-ng 将自动监听默认设备）。
3. 打开 SDR# 或类似的程序。在 SDR# 音频设置中将音频输出设置为你的音频管道方法，并调至 NFM 模式的天气电台。
4. 打开命令提示符，使用 `cd` 命令进入保存 dsame 和 multimon-ng 的文件夹。

## 在 Windows 或 Linux 上使用 rtl_fm 解码

以下指令假设为 Windows，如果是 Linux 请使用 .sh 脚本代替 .bat 脚本：

1. 将 `rtl_fm` 及其支持文件复制到 multimon-ng 和 dsame 相同的目录（如果是 Windows）。
2. 使用文本编辑器打开 scripts 文件夹中的 `source-rtl-fm-multimon-ng.bat` 文本文件。根据你的 RTL-SDR 节点和 EAS 站频率适当设置 PPM 和 FREQ 值。

![](img/33eab9643eb7fbb4bf9363c117190041_453_0.png)

3. 打开命令提示符（Linux 下的终端）并浏览到保存 `dsame` 的文件夹。
4. 使用以下命令开始监听和解码：

```
dsame.py --source scripts\source-rtl-fm-multimon-ng.bat
```

你也可以通过使用 `--same` 参数输入你所在地区的正确 SAME 代码，设置 dsame 仅监听针对你所在区域的消息。请查看 Github 页面获取完整的命令列表。

# 火车遥测数据解码

| 频率 (MHz) | 信号类型 |
|---|---|
| 452.9375 | 车头 (HOT) |
| 457.9375 | 车尾 (EOT) |
| 457.9250 | 分布式动力单元 (DPU) |

车头 (HOT) 和车尾 (EOT) 信号用于列车传输遥测数据（如制动管压力），并监控列车的意外脱节情况。车尾设备用于发送 EOT 信号，机车头部的 HOT 单元将接收该信号。
