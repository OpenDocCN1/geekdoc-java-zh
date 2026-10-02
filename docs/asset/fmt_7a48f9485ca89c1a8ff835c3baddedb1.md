
- 15. 在显示的新接收范围中，首先点击显示频率范围的最顶端栏。在栏的左侧输入值 0，右侧输入一个任意大值（例如 1000）。点击 Apply。这将为瀑图选择最大带宽频率范围。
- 16. 要增加瀑图速度，请将瀑图左下角的数值改为较低的值，例如 9。
- 17. 按 `X` 然后 `P` 进入参数屏幕。点击 `First FFT Amplitude` 并新值设置为 20。这会降低底噪。
- 18. 如果你的 PC 处理跟不上，按 `X` 然后 `P` 将 `First FFT Bandwidth` 设置为 1 kHz。
- 19. 要调谐到电台，点击顶部 RF 频谱中的峰值。通过拖动下方频谱中的黄色条来改变带宽。向右拖动增加宽带 FM 的带宽。

## 在 LINUX 上安装 RTL-SDR 驱动

如果你想在 Linux 系统上开始使用 RTL-SDR，第一步是安装驱动。首先使用以下命令更新发行版：

```
sudo apt-get update
```

现在如果没有安装，安装 `git`、`cmake` 和 `libusb`，这是 RTL-SDR 需要的库：

```
sudo apt-get install git
sudo apt-get install cmake
sudo apt-get install libusb-dev
sudo apt-get install libusb-1.0-dev
sudo apt-get install build-essential
```

现在下载、编译并安装 RTL2832 Osmocom 驱动。（注意，我们也建议使用链接 `https://github.com/keenerd/rtl-sdr.git` 克隆 Keenerd 驱动来代替 osmocom）

```
git clone git://osmocom.org/rtl-sdr.git
cd rtl-sdr/
mkdir build
cd build
cmake .. -UDEV_RULES=ON
make
sudo make install
sudo ldconfig
sudo cp ../../etc/rules.d/
```

在某些情况下，你现在需要重启 Linux。

插入加密狗，然后运行 `rtl-test` 测试加密狗。如果 `rtl-test` 在 found devices 头部返回奇怪字符，或者遇到如下错误：

> Kernel driver is active, or device is claimed by second instance of librtdr.

在第一种情况下，请分离或黑名单模块 (`dvb_usb_rtl2xx`)，或者在编译时启用自动分离。

```
usb_claim_interface error -6
Failed to open device #0.
```

这意味着包含在较新 Linux 版本中的 RTL2832 DVB-T 驱动已安装并激活。运行以下命令禁用它们：

```
sudo rmmod dvb_usb_rtl2xx
```

注意运行此命令只会停止一次 DVB-T 驱动。当你移除并重新连接加密狗或重启 Linux，DVB-T 驱动将重新加载，你需要再次运行此行。

为了获得持久的解决方案，在 `/etc/modprobe.d` 中创建一个文本文件 `blacklist-dvb_usb_rtl2xx.conf`。在该文件中写入文本 `black dvb_usb_rtl2xx`。此此简单的方法是在终端中直接输入以下内容：

```
sudo echo "blacklist dvb_usb_rtl2xx" > /etc/modprobe.d/blacklist-dvb_usb_rtl2xx.conf
```

黑名单 DVB-T 驱动后，你可以拔掉并重新连接加密狗，它现在应该默认使用 RTL-SDR 驱动，但在某些情况下你可能需要重启 Linux 黑名单才能生效。

如果你运行 `rtl_test` 时出现奇怪字符，可能表明你没有通过 `cp ../../rtl-sdr.rules /etc/udev/rules.d/` 正确安装 `.rules` 文件。

## RTL_FM

`Rtl_fm` 是一个用于 WBFM/AM/FM/SSB 的轻量级命令行接收机。我们首先需要对术语进行一项区分。当我们提到 `rtl_fm` 时，指的是调谐区域带宽（例如 SDR# 中的阴影区域），而不是宽带瞬时带宽。下面列出了可能的 `rtl_fm` 标志，然后展示一些使用示例。

## RTL_FM 使用示例

要使用下面示例中使用的 `play` 命令，你需要 `sox` 或 `aplay`。在 Debian Linux 上可以通过 `sudo apt-get install sox` 获取 `sox`。在 Mac 上使用 `port sox`。在 Windows 上，可以从 `http://sourceforge.net/projects/sox/` 下载。你需要将安装 `sox` 的文件夹添加到 Windows PATH 中，以便从提示符的任何地方访问。你可能也希望将包含 `rtl_fm` 的文件夹添加到 PATH。在此链接中有一个如何将目录添加到 PATH 的教程：`http://geeksswithblogs.com/renso/archive/2009/10/21/how-to-set-the-windows-path-in-windows-7.aspx`。在 Windows 上，需要在命令末尾添加 `-d` 标志来选择默认设备。此外，在 Windows 上，“play" 命令被 "sox" 命令取代。

## RTL_FM 标志

+ `-M` 设置接收模式 (`wbf`, `fm`, `am`, `lsb`, `usb`, `raw`）（默认为 `fm`）
- `-s` 调谐区域的带宽/采样率（不是整个频谱）
- `-g` 增益（默认是自动）
- `-l` 抑制电平
- `-t` 抑制延迟
- `-p` ppm 偏移
- `-F` 使用更好的滤波器（0 - 9）
- `-r` 输出采样率（极低质量重采样）
- `-d` 加密狗编号（用于使用多个加密狗）
- `-A` 反正切计算 (`std`, `fast`, `lut`)
- `-E` 特殊模式 (`dc`, `deemp`, `direct`, `offset`)

有关完整的类型列表，请参考 `rtl_fm -h`。

# 接收 WBFM

`rtl_fm` 在 WBFM 模式下使用的音频采样率为 32k。

```
rtl_fm -M wbfm -f 88.6M | play -r 32k -t raw -e -s 16 -c 1 -V1 -
```

为了获得更好的音频输出质量，可以使用 `-r` 标志将音频采样率重采样为 48 kHz，如下：

```
rtl_fm -M wbfm -f 88.6M -r 48k | play -r 48k -t raw -e -s 16 -c 1 -V1 -
```

除了 `sox` 之外，也可以使用 Alsa amp 作为替代方案，如下。某些 Linux 计算机播放的音质效果更好。

```
rtl_fm -M wbfm -f 88.6M -r 48k | aplay -r 48k -f S16_LE
```

在 Windows 上请使用以下命令。

```
rtl_fm -M wbfm -f 88.6M | sox -r 32k -t raw -e -s 16 -c 1 -V1 -d
```

此外，除了使用 `-M wbfm`，还可以使用 `-M fm` 并通过 `-s` 指定带宽，通过 `E` 指定去强调选项。这种方法有时会产生更好的音质。

```
rtl_fm -M fm -f 88.6M -s 200k -r 32k -E deemp | play -r 32k -t raw -e -s 16 -c 1 -V1 -
```

# 窄带 FM 示例

```
rtl_fm -M fm -f 161.649M -s 12k -g 50-70 | play -r 12k -t raw -e -s 16 -c 1 -V1 -
```

# AM 示例

```
rtl_fm -M am -f 127.7M -s 12k -g 50 | play -r 12k -t raw -e -s 16 -c 1 -V1 -
```

对于上述示例，可以通过使用 `-F` 选项在增加计算时间的代价下提高接收信号的质量。在 `-F` 之后使用 0-9 之间的数字，数字越大，下采样滤波器的质量越高。即使使用 `-F0` 也会提高音频质量。

# 扫描仪示例

`rtl_fm` 也可以用于扫描多个频率的活动情况。

添加你想要扫描的频道的多个 `-f` 频率。

`rtl_fm` 将继续扫描直到找到活动信号。下所示是一个示例。

```
rtl_fm -M m -f 161.649M -s 12k-161.925M -f 161.825 -s 12k -g 50-70 -1 | play -r 12k -t raw -es -b 16 -c 1 -V1 -
```

你也可以指定频率范围和步长进行扫描。例如，若要扫描航空频段，可以使用以下命令：

```
rtl_fm -M am -f 118M:137M:25k -g 50 | play -r 12k -t raw -es -b 16 -V1 -
```

# 使用 SOX 更改音频采样率

`rtl_fm` 有 `-r` 标志来调整输出采样率。然而，这是一种低质量的转换且无法进行上采样。如果你出于某种原因需要更改 `rtl_fm` 的输出采样率，可以如下所示使用 `sox`。

```
rtl_fm -M fm -f 161.649M -s 12k -g 50 -10 | sox -r 12k -t raw -es -b 16 -traw -r 48k -es -b 16 -c 1 | play -r 48k -t raw -es -b 16 -c 1 -V1 -
```

一个更好的音质 WBFM 使用 `aplay` 的示例：

```
rtl_fm -M fm -f 88.6M -s 170k | sox 170k -t raw -es -b 16 -traw -r 48k -es -b 16 -c 1 | aplay -48k -f S16_LE
```

关于 `rtl_fm` 的完整文档可以在 `http://kmken.com/rtl-demod-guide/index.html` 找到。

如果你想通过网络启动 `rtl_fm` 音频，请连接项目部分的 MP3 streaming_tutorial。此外，若要在如 `multimonng` 等数字解调软件中使用 `rtl_fm`，请参阅本书后半部分的 MultimonongNG 章节。

# 安装 GNU RADIO

GNU Radio 是一个流行的基于 Linux 的数字信号处理平台，兼容 RTL-SDR。GNU Radio 是一个大型且复杂的程序，有时很难安装。下面我们展示了最常见的方法。

重要提示：不要在运行于 SD 卡上的嵌入式设备上运行编译 GNU Radio 的安装过程。GNU Radio 在安装过程中产生的写入次数可能会损坏卡片。安装后，可以通过 `gnuradio` 启动 GNU Radio。

如果你在 Ubuntu 虚拟机运行 GNU Radio，可能需要调整 `/usr/local/gnuradio/conf.d/gr-audio-salsa.conf` 中的某些设置：`period_time = 0.10` 和 `nperiods = 32`。

注意，除非使用下所示的脚本，否则应预安装 RTL-SDR 驱动。请查看 Linux 上安装 RTL-SDR 驱动。如果你不想经历安装 GNU Radio 的过程，有一些预装 GNU Radio 的 Linux 发行版。参考 Live DVD 章节。

# 安装脚本

在几乎任何 Linux 系统上安装最新版本 GNU Radio 的简单方法是使用 Marcus Leech 的脚本。此脚本还会安装 RTL-SDR 和 OsmoSDR 等相关库。我们推荐这种方法，因为它最简单且最可能成功。使用该脚本只需在终端输入：

```
sudo apt-get update
wget http://www.sbrac.org/files/build-gnuradio && chmod a+x ./build-gnuradio && ./build-gnuradio
```

脚本会问几个问题，回答 yes 或 y。它将下载并安装所有依赖项以及 GNU Radio。几分钟到一小时后，脚本将停止并要求你输入管理员密码以执行 `sudo`，因此你需要定期检查脚本的进度。另外注意，取决于你的网络和电脑速度，脚本大约需要 1-3 小时完成。

如果出于兼容性考虑你需要安装旧版本的 GNU Radio 3.6.5.1，可以使用如下 `-o` 标志：

```
wget http://www.sbrac.org/files/build-gnuradio && chmod a+x ./build-gnuradio && ./build-gnuradio
```

如果你发现错误“Fetching GNU Radio- Could not find gnadio”，请尝试下方法。如果出于某种原因脚本不起作用，可以尝试 `pybombs`。

# PYBOMBS

# 包管理器

也可以使用标准的 `apt-get` 过程安装 GNU Radio，但这些预包版本通常不是最新版本。安装较现代版本的 GNU Radio (3.7+) 最简单的方法是使用 Ubuntu 14.04 或更高版本。

FreeDV, wsjt-x, Micro-Fox 15 Config 以及一个 TinyTrak3 配置程序。

`http://sourceforge.net/projects/kb1oiq-andysham/`

# GNU RADIO LIVE DVD

基于 GNU Radio 程序的 Linux 发行版。包含 rtl-sdr 驱动、GNU Radio 3.7.3 版本、gqrx、Mode-S/ADSB 飞机接收器、GrOsmoSDR GNU Radio 模块、GNSS-SDR。

`http://gnuradio/redmine/projects/gnuradio/GNURadioLiveDVD`

# KALI LINUX

Kali Linux 是一个以安全和渗透测试为中心的发行版。Kali Linux 预装了 GNU Radio 和 Wireshark。

`http://www.kali.org/`

# PENTOO

Pentoo 是另一个以安全和渗透测试为中心的发行版。预装了 GNU Radio 和 RTL-SDR 驱动。

`http://www.pentoo.ch/`

# PORTEUS

Porteus 是一个非常轻量级的发行版，针对小体积、速度和效率进行了优化。

`http://www.porteus.org/`

# BEAGLEBONE BLACK SDR IMAGE FILE

这是一个为 BeagleBone black 嵌入式 Linux PC 设计的实用镜像文件。该镜像包含 Ubuntu 14.04 操作系统以及预装的 SDR 软件和驱动，如 RTL-SDR 驱动和 GNU Radio。预装软件的数量不断增加，但在编写时包含以下内容：GNURadio 3.7、keenerd 的 rtlsdr bundle、gqrx、multimode、LTE-Cell-Scanner、LTE-Tracker、multimon、rtl_flex_noX、SuperKuh 的 Dongle Logger – pyrtlsdr、rtl_433、SDR-J、rtl_sdr 宽谱分析仪、DSD 1.7、RTLAMR、RTL_FM_Python。

`http://www.kd0cq.com/2014/08/packed-full-beagle-black-img-file-rtl-sdr-gnuradio-gqrx-lots-more-on-ubuntu-14-04/`

# RTL-SDR 杂项

## RTL-SDR 晶振误差

RTL-SDR 是一种中国批量制造的设备，晶振误差较大高达 +150 PPM 偏移。RTL-SDR 中的晶振器是其时钟源（电路的心脏）。RTL-SDR 使用 28.8 MHz 晶振器，可能会偏差几千兹。结果是已知频率可能不在你预期的位置。请参阅[校准 RTL-SDR]章节或[设置 PPM 偏移]章节，了解如何校准 RTL-SDR 以消除频率偏移。

某些 RTL-SDR 配备了升级版晶振。使用 SMD 晶振的误差可能为 +-30 PPM，而带有 TCXO（温度补偿晶振器）的设备误差为 +-1 PPM。带有 TCXO 的 RTL-SDR 不需要设置任何 PPM 偏移，或者只需要 1 或 2 的偏移。

## RTL-SDR 直流脉冲 (SPIKE)

E4000 适配器（以及 FC0012/13）无论调到哪里，频谱中心都会出现一个巨大的脉冲。这是预期的，因为这是 E4000 的设计方式。要消除 E4000 和 FC0012/13 适配器的直流脉冲，可以使用 SDR# 配置菜单中的“偏移调整 (Offset Tuning)”选项。对于 R220/R820T2，偏移调整无效。

R820T2/R820T2 在中心也有一个微小但明显的直流脉冲，但通常在 SDR 中点击 Correct IQ 即可完全消除它。

## RTL-SDR 杂波 (SPURS)

由于适配器的设计，在 28.8 MHz（内部晶振频率）的倍数处会有杂散（不需要的）信号脉冲。你可能在 48 MHz（USB 时钟频率）的倍数和 480 MHz（USB 数据率）的倍数处看到强杂波。

遗憾的是，对于这些脉冲的位置没有很好的办法。晶振杂波在频谱和瀑布图中看起来像一条细实线。在 LSB/USB 模式下听起来像单音频调。要检查信号是否为晶振产生的杂波，只需将可疑频率除以 28.8 MHz。如果结果是整数，它可能就是杂波。USB 之类的杂波可能像许多聚集在一起的杂波。

# RTL-SDR ADC 位深

RTL2832U ADC 使用物理位为 8，但 ADC 的有效位数通常较低，对于 RTL-SDR 可能约为 7 位。

# RTL-SDR 灵敏度

带有 R820T 调谐器的 RTL-SDR 平均灵敏度约为 -130 dBm。以下是 HB9AJG 执行的一些灵敏度结果。完整报告可以在此处找到：`http://f6fvy.free.fr/rtl_sdr/Some_Measurements_on_E4000_and_R820T_Tune.pdf`。
