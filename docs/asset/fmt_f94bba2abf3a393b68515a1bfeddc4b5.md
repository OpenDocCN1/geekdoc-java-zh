
- 8. 现在运行以下命令用小写字母解压文件、编译解码器，并将编译后的解码器复制到 `/tetra/bin` 文件夹。

```bash
unzip -L en_30039502v010301p0.zip
patch -p -N -E < codec.diff
cd c-codec
make
cp cdecoder decoder /tetra/bin
```

如果你安装的是 64 位 Linux，则需要使用单独的步骤代替上述步骤 8。这些步骤展示了如何在 64 位的 Ubuntu OS 中设置 32 位环境。

- 1. 使用以下指令代替上述的步骤 8。

```bash
sudo su
mkdir /build32
apt-get update
apt-get install debootstrap
debootstrapstrap --variant=buildd --arch i386 whezy /build32
mkdir /build32/root/codec
```

- 2. 现在将 `en_30039502v010301p0.zip` 文件和解码器文件移动到 `/build32/root/codec` 并使用以下命令编译解码器。

```bash
cd /home/user/osmo-tetra-sq5bpf/etsi_codec-patches
cp en_30039502v010301p0.zip /build32/root/codec
cp codec.diff /build32/root/codec
chroot /build32
apt-get install unzip
cd root/codec
unzip -L en_30039502v010301p0.zip
patch -p1 -N -E < codec.diff
cd c-code
make
exit
cd /build32/root/codec/c-code
cp c-decoder sde-coder /tetra/bin
exit
```

## 运行解码软件

现在一切已安装完成，我们可以运行软件来解码一些 TETRA 信号。

- 1. 打开一个终端窗口，进入 `~/osmo-tetra-sq5bpf/src` 并运行 `./receiver1 1`。

```bash
cd ~/osmo-tetra-sq5bpf/src
./receiver1
```

- 2. 打开第二个终端窗口或标签页，使用以下命令打开一个特殊尺寸的 xterm 窗口。

```bash
/usr/bin/xterm -font fixed -bg black -fg white -geometry 203x60
```

- 3. 在 xterm 窗口中，进入 `~/telive` 并运行 `./rxx`。

```bash
cd ~/telive
./rxx
```

- 4. 打开另一个终端窗口或标签页，进入 `/tetra/bin` 并运行 `./tetrad`。

```bash
cd /tetra/bin
./tetrad
```

- 5. 打开另一个终端窗口或标签页，输入以下内容打开 GNU Radio Companion。

```bash
gnuradio-companion
```

- 6. 在 GNU Radio 中打开位于 `~/telve/gnuradio-companion` 的 `televe_1ch.grc` 文件。你也可以使用 `telve_1ch_simple.grc`，它会显示图形化的 FFT 频谱，可以通过点击进行调谐帮助，但这会消耗额外的 CPU 资源。

- 7. 在 GNU Radio 流图左侧，双击标记为 `Center Freq` 的变量，将频率更改为你之前找到的 TETRA 信号频率减去 500 kHz。例如，如果发现 TETRA 信号在 858.562 MHz，则你输入的中心频率应为 `858.562 MHz - .500 MHz = 858.062 MHz`。这是因为默认偏移值被设置为 500 kHz。

- 8. 双击标记为 `ppm` 的变量，输入你的接收器特定的 PPM 校正值。

## 分析 TETRA

即使 TETRA 信号经过了加密，我们仍然可以以类似于 GSM 信号的方式查看发送的系统数据，从而分析 TETRA 信号。

- 1. 如果尚未安装，请在终端窗口中使用以下命令安装 Wireshark。

```bash
sudo apt-get install wireshark
```

- 2. 现在请在“收听 TETRA”教程章节中执行上述步骤。

- 3. 打开第二个终端窗口或标签页，通过输入 `sudo wireshark` 来打开 Wireshark。由于我们以 sudo 身份运行 Wireshark，可能会弹出一些错误和警告，但这些可以安全地忽略。注意，我们以 sudo 运行 Wireshark 是为了获取本地环回接口的权限。由于 Airprobe 将数据导出到 UDP 端口，我们必须设置 Wireshark 监听该端口。

- 4. 在 Wireshark 的开始按钮下，首先将捕获接口设置为“Loopback: lo”，然后点击开始。接着在过滤器框中输入 `gsmtap`。这将确保只显示 TETRA 数据。此时，TETRA 系统数据应该显示在 Wireshark 中。

## 射电文学指南

结合合适的天线和低噪声放大器（LNA），RTL-SDR 已被用作天文工具来：

- 观测氢线和银系面。
- 探测进入大气层的流星。

### 观测氢线和银系面

通过将高增益定向天线指向星际介质，可以在 1420 MHz（21cm）处观测到氢线。星际介质是存在于星之间的物质。它由大量中性氢组成，在 1420.4057577 MHz 发射电磁辐射。对于单个氢原子来说，这种发射非常稀有，但星际介质由大量的中性氢组成，使得合适的无线电设备和天线很容易探测到这种发射。

通过观测移动天空中的氢线，可以探测到银系面。这是因为银系面上的氢比真空空间中得多。当天线指向银系中心时，氢线频率的信号强度会增强。

此外，还可以观测我们银河系旋臂的多普勒频移。由于星系正在旋转，旋转臂发射的氢线会产生多普勒频移，偏离 1420 MHz。当指向正确的方向时，可以在 1420 MHz 附近的多个光谱功率峰处观测到多个旋臂。这是因为内臂的旋转速度与外臂不同，导致它们的氢线多普勒频移存在差异。这是天文学家确定星系形状的一种方法。

观测氢线所需的物品：

- 大型卫星天线（>1m）、高增益八线天线、螺旋天线或喇叭天线。
- 1-2 个 LNA 前置放大器和 1-3 个线路放大器。
- 1420 MHz 带通滤波器。

Marcus Leech 是最早尝试射电文学和 RTL-SDR 的人之一，他在这里有一篇优秀的文章：http://www.sbr.org/files/budget_radio_telescope.pdf。他写道，使用 RTL-SDR 观测氢线至少需要 1 米的大天线。在大多数有卫星电视的国家，可以相对廉价地找到旧天线。如果你很难获得天线，其他实验者使用非天线定向天线取得了成功，例如 22 元八线天线 http://www.y1pwe.co.uk/RAProgs/HLRrtrtl.pdf，这可能更便宜且更容易制作。另一个成功案例是使用 22 元八线天线作为螺旋天线和喇叭天线。在这里可以找到一个用于 RTL-SDR 射电文学的喇叭天线示例：http://rishi-patel.blogspot.com/2013/10/summary-of-horn-antenna-project.html。在以下链接中可以找到更多氢线实验示例：

- 3M 锅面：http://lea.hamrad.si/~s57ra/index.php/radio-astronomy/hydrogen-line-with-rtl-sdr
- 3.6M 锅面：http://lea.hamradio.si/~s53rm/Radio%20Astronomy.htm

观测氢线的方法是将定向天线/锅面指向天空，并将无线电调谐到 1420 MHz。由于氢线信号非常微弱，需要为天线配备多个放大器，以获得接收器能够检测到的足够信号强度。通常使用两个或三个线路放大器并直接在天线后放置一个极低噪声放大器。此外，还需要 1420 MHz 附近进行良好的带通滤波，以消除来自人为源的带外干扰。有了正确的设备，通过对一段时间的光谱功率进行测量并对数据进行积分或平均，即可观测到氢线。

为了平均数据，你需要能够对一段时间内的 FFT 频谱进行平均的软件。可以使用 http://1ype.co.uk/RAPProgs/index.html 的 `RAFFT.exe` 软件。基于 Linux GNU Radio 的 `simple_ra` 软件位于 https://www.cgan.org/wiki/simple_ra。关于 `simple_ra` 的有用说明可以在 http://superkul.com/rtlsdr.html#simple_ra 找到，尽管目前 `simple_ra` 似乎仅适用于旧版本 3.6。

### 流星散射探测

RTL-SDR 可探测流星。流星散射的工作原理是探测来自远程广播站的信号。当流星进入大气层时，它会电离空气留下痕迹。注意，射频信号并不是从流星本身反射，而是从它留下的电离空气反射。流星探测需要一个距离你的天线 300 到 1200 公里的具有强载波的广播站。这个距离远到不会直接接收到过强的信号，但又近到让天空中的流星可以将信号反射到你的接收器。50-80 MHz 的电视频段是最佳选择。然而，由于数字转换，模拟电视发射正在减少，88-108 MHz 的 FM 波段也可以作为替代方案，可能还有 UHF 频率的数字传输，尽管 UHF 频率的结果较差。如果你住在欧洲，位于法国频率为 143.050 MHz 的 Graves 雷达是最佳选择，因为它发射的是纯载波信号，非常适合该项目。在美国，也有强大的雷达可以使用，但你需要确定哪些位于你附近。在北美几个州运行的 40.670 MHz SNOTEL 系统可能是另一个值得研究的发射源。

由于流星散射信号可能很微弱，你应该使用调谐至监控频的高增益八线天线，并将其指向广播站的天空。非定向天线也可以工作，但增益可能不足以获得良好的性能。有些人报告使用磁环天线取得了成功。一个 LNA 也是理想的。探测到的流星会在射频频谱瀑布图中显示为弯曲或倾斜的亮点，并且如果接收器设置为 USB 模式，则会产生一种哨哨声。

业余射电天文学家 Marcus Leech 的一篇关于使用 RTL-SDR 进行流星散射探测的良好论文在这里：http://www.sbrac.org/files/meteor_forward_scatter.pdf。Morgan 博士撰写的更多关于业余流星散射探测介绍及使用 RTL-SDR 进行探测的文章可以在此处找到：

http://www.britastro.org/radio/projects/meteorproj.html。这里还有由 *Sky at Night* 编写的有趣文章，讨论了流星散射，并展示了如何构建用于 Graves 雷达的 Yagi 天线：http://www.britastro.org/radio/downloads/SkyAtNight/BBC_SatN_HOWTO OBSERVEEMETEORS.pdf。

虽然可以在 SDR# 等独立 SDR 软件中通过肉眼监测流星，但使用额外的流星检测软件进行长时间监测会更有用。某些软件会自动计数检测到的流星“脉冲”数量。下文讨论了 Baudeline、HROFFT、`rtl_power`、Spectrum Lab 或 `meteor_detector` 软件包，它们可用于监测发射器频率周围的小带宽以进行流星散射。

## RTL_POWER

若要对 53 MHz 发射器周围的小带宽进行 1 小时的监测，可以使用以下 `rtl_power` 命令。注意，对于流星散射，最好使用非常小的分箱大小（binning size）和小带宽以获得高分辨率。请查看 *Heatmap Bandscan Tutorial* 了解更多关于 `rtl_power` 的信息。

```bash
rtl_power -f 52.995M:53.005M -1 g -50 1i -1h meteor_scatter.csv
```

## HROFFT

可以使用 RTL-SDR 名为 HROFFT 的 Windows 程序来监测流星散射。HROFFT 会监测你调谐频率的音频频谱，并每 10 分钟输出一次彩色谱图（音频 FFT 图像）。可以从 http://www.bcmeteors.net/php/index/radio-methods/87-radio-detection-basics?showall&start=4 下载 HROFFT。要使用 HROFFT 请按照以下说明操作。

- 1. 下载并解压 HROFFT 到文件夹中。
- 2. 打开 `header.txt` 文件并输入它所要求的信息。
- 3. 打开你喜欢的 SDR 接收器（如 SDR#），并将首选的音频管道（audio piping）方法设置为输出。
- 4. 调谐到远程发射站的中心频率，然后向上调高几 kHz。将接收模式设置为 USB 并将调谐区域带宽增加到最大。
- 5. 打开 HROFFT。
- 6. 调整 SDR# 中的音量和 HROFFT 中的信号电平，使底部显示的蓝色信号电平位于第一线下方。如果蓝色信号比第一条水平线强，则流星将被计为检测到，因此你可能需要相应调整音量和信号电平设置，以便只有真实的流星反射会触发该线。
- 7. 在看到几个流星回声后，你可能希望调整音频带宽，使其覆盖你正在检测的信号带宽。左侧垂直轴上的灰色条显示带宽，可以通过 `f1` 和 `f2` 设置进行调整。这将更好地检测流星，因为信号强度取自该带宽内信号之和。

![](img/33eab9643eb7fbb4bf9363c117190041_345_0.png)

流星通常表现为短促的闪烁，但大流星可能会产生较大的回声。长轨迹可能指示了来自飞机的无线电反射。关于分析 HROFFT 图像的更多信息可以在这里找到 http://www.amro-net.jp/about-hro/analyze-hrofft.htm。

## BAUDLINE

在 Linux 上，频域 FFT `baudline` 也可用于记录流星散射活动。使用它在瀑布图中搜索闪烁。从 http://www.baudline.com/download.html 下载 Baudline。可以使用以下示例启动 Baudline。

```bash
rtl_sdr -f 91M -s 2400000 -g 50 - | /baudline -reset -sampler 2400000 -channels 2 -format u8 -quadrature -quadrature
```

另一个检测流星的优秀软件程序是 Spectrum Lab，它可以在 http://www.qsl.net/dl4yhf/spectra1.html 免费下载。关于使用 RTL-SDR 使用 Spectrum Lab 进行流星检测的指南可以在此文档中找到：http://www.britannastbro.org/radio/downloads/TECHNIQUES_FOR_USING_the_RTL_Dongle.pdf。前述论文同一作者的其他关于流星检测的额外文档可以在 http://www.britastro.org/radio/projects/meteorproj.html 找到。

## METEOR_DETECTOR

`Meteordetector` 是一个 GNU Radio 程序，可用于检测流星散射。它曾可从 https://www.cgan.org/ 获取，但在编写本文时（2015 年 1 月）该网站似乎已关闭。我们建议你定期回来检查以获取更新，或在 IRC freenode 的 #rtlsdr 联系 patchvonbraun 获取代码。

## SOLAR INTERFEROMETRY

RTL-SDR 可作为太阳干涉仪来测量太阳的变化，例如太阳黑子。干涉测量法是一种简单的方法，可以将较小的无线电望远镜天线连接在一起，使其近似于更大的天线。

Superkh 有一个正在构建的 11 GHz 太阳干涉仪。关于它的细节可以在 http://superk.com/rtlsdrinterferometer.html 找到。

## OTHER SIMPLE RADIO ASTRONOMY EXPERIMENTS

使用带有 LNB 和 RTL-SDR 的简单 18 英寸直接电视卫星天线可以进行更多简单的无线电实验。这些组件可以用于...（注：此处原文似乎不完整，已根据现有内容翻译）

- http://www.rtl-sdr.com/passive-radar-dual-coherent-channel-rtl-sdr/
- http://www.rtl-sdr.com/rtl-sdr-based-coherent-multichannel-receiver/
- http://www.rtl-sdr.com/rtl-sdr-based-passive-multistatic-radar-used-track-aircraft/

# HF 模式解码指南

要接收高频（HF）信号，你需要一个带有上变频器的 RTL-SDR 调谐器、启用直接采样功能，或者使用实验性的 HF 驱动程序之一。更多信息请参阅书中前面的“接收 LF/MF/HF 指南”。或者，你也可以使用支持 HF 的 SDR 无电台，例如 Funcube Dongle 或 SoftRock SDR。你还需要一个 HF 天线，大多数 VHF 和 UHF 天线完全无法接收 HF 信号。关于 HF 天线的更多信息，请参阅“天线指南”章节。

# 短波广播

短波广播实际上是通过 HF 频段发送的国际调幅（AM）广播。接收这些内容只需要一个良好的 HF 天线和一个支持 HF 的 RTL-SDR。有时，寻找和监听短波电台的爱好被称为 SWLing（短波收听）。在这里找到常见的短波电台列表：http://support.radioshack.com/support_tutorials/communications/swave-6.htm。
