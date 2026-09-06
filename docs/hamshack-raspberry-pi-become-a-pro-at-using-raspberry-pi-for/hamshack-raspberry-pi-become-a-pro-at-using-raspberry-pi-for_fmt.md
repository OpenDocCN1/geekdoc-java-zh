
# Hamshack Raspberry Pi：成为业余无线电活动 Raspberry Pi 高级指南

## 引言

无论你已经获得了无线电执照还是打算获取，选择阅读这本书都是明智之举。

你听过的所有酷的无线电活动，例如电码通信、卫星跟踪甚至简单的无线电操作，这本书将很快教会你。

而最棒的部分是？你不需要花费数千甚至数百美元。只需要一台廉价的树莓派电脑和其他工具，就可以开启你的无线电之旅。

如果你认为因为没有被介绍过名为树莓派的微型电脑就跳过这本书，那么你就大错特错了。

从你购买 Pi 的那一刻起，到实际操作 hamshack，这本书将引导你学习安装、配置和操作 Pi 以享受世界上最有趣的爱好。

听起来很划算吧？现在让我们玩玩无线电吧？

## 介绍树莓派

树莓派（读作 raspberry pie）是一种只有信用卡大小的微型电脑。树莓派基金会将信用卡作为这种电脑打印电路板（PCB）的设计模板。

树莓派或 Pi、RasPi 或 RPi（随你最喜欢的称呼），信你信信。它的主板包含了桌面电脑中常见的硬件（如内存、处理器等），这意味着这种信用卡大小的电脑也能让你编辑文档、播放视频、玩游戏等。

当然，它的尺寸无法提供像普通 PC 那样的动力，但其约 35 美元的廉价解决了一切问题。实际上，这种电脑诞生的核心思想是用最小投资让孩子们学习计算机科学。弄坏树莓派并更换一个新的要方便得多。

树莓派正如听起来那样有趣。通过这种微型电脑，你可以超越“表面”层，深入探索大多数人并不熟悉的“黑盒”。学习树莓派已被证明是人们采用软件和硬件工程技能的最简单方法。

但树莓派不仅适用于这些“学者”。这种信用卡式电脑更神奇的地方在于它的粉丝群体非常多元。有很多 DIY 爱好者和黑客让树莓派成为他们电脑实验的重要部分。

### 简述历史

对于偶尔关注电脑技术的人来说，树莓派似乎是全新的。大多数博客和网站都是这样对待这种电脑的，所以看起来如此。但事实是树莓派已经存在多年。事实上，Pi 的创造者 Rob Mullins、Eben Upton、Alan Mycroft 和 Jack Lang 在 2006 年首次提出了微型电脑的想法。这是由于他们观察到当时市廉价电脑（如 Amiga 或 Spectrum）对编程教育产生了负面影响，因为它们大大降低了学习计算机科学的能力。由于笔记本电脑和桌面电脑花费数百甚至数千美元，当时的孩子们真的负担不起这种家庭电脑。因此，需要一个廉价的学习平台是可以理解的。

为了实现他们的想法，Pi 的创造者尝试了各种微控制器、PCB 和面包板，但直到 2008 年，由于更新的技术和更便宜的芯片，他们的概念才变为现实。新的强大工具帮助他们创建了一个不仅能够命令行编程而且支持媒体的平台。在 David Braben 和 Pete Lomas 的加入下，原始创造者形成了现在盛名的树莓派基金会，并在三年后的 2011 年，第一台树莓派上市了。

随着技术的进步，出现了许多不同型号的树莓派，每种都比其祖先提供更好的功能。

### 硬件

如果你已经购买了树莓派，你可能已经注意到设备送来时实际上有多么“裸”。它的价格可能很廉，，大约 35 美元，但涉及一些隐藏成本。Pi 确实是一台电脑，但你还需要其他东西才能让它正常工作。

5V 电源。对于一个 USB 供电的设备，大家都会同意树莓派（无论你的是哪种型号）是电渴的。它的抽电流约为 600 到 700 mA。虽然它可以通过 USB 端口供电（额定约为 500 mA），但使用实际的电源适配器至关重要。你可以使用现代智能手机充电器，因为大多数在 5V 下提供 700 mA，但要检查你的充电器是否处于该功率的底部。

如果你没有优质的充电器，一旦连接了摄像头模块或简单的 Wi-Fi 适配器等设备，它们将从 Pi 抽取更多电源，导致其变得不稳定。

另一方面，如果电源没有提供稳定的 5V，可能提供了过电压，主板很容易损坏。

能为你的树莓派提供充足电源的优质第三方供应商有：

- AdaFruit
- MoodMyPi
- SparkFun

SD 卡。它很小且强大，但树莓派本身没有存储数据的能力。因此，SD（安全数字）卡——一种可移动存储设备——是必不可少的。

为树莓派购买 SD 卡时，你需要寻找以下内容：

- 标准 SD 卡。你的 Pi 支持标准 SD 卡，而不是 Mini 或 Micro SD，但如果你恰好有 Micro 或 Mini，可以使用适配器进行转换。
- 可信赖的品牌。避免廉价选择，选择优质的 SD 卡，如金士、闪迪或威达。
- 至少 4 GB 容量
- 4 级或更高。该等级非常重要，因为它指示了卡片实际读写数据的速度。例如，4 级 SD 卡每秒可以读写若干 MB。6 级更快，可达每秒 6 MB，10 级每秒可以读写 10 MB，……

请记住，标准 SD 卡有 SDHC（安全数字高容量）和 SDXC（安全数字扩展容量）之分。请检查您的 Pi 的兼容性，并查看哪种最适合您的设备。SDHC 支持最高 32 GB，而 SDXC 支持最高 2T。

**电源 USB 集线器。** USB 集线器是一个紧凑的设备，可以连接几个 USB 设备。例如，如果你有一个廉价的树莓派，可能只有一或两个端口。插上鼠标和键盘后，你就没法插其他东西了。这就是为什么 USB 集线器是树莓派用户在购买电脑后购买的主要物品之一。

**以太网线。** 如果你想将树莓派连接到互联网（你当然想），那么除了显而易见的网络连接外，你还需要一根以太网线来实现。你将以太网线的一端插入 Pi，另一端插入无线路由器、电缆调制调器或你任何用于连接互联网的设备。

**显示器。** 即使你计划以无头远程的方式使用树莓派，很可能很快你就会想将电脑连接到显示器或电视。

**线缆。** 为了将树莓派连接到显示器或电视，你需要线缆。为此，你可能需要一根 HDMI 线或一复合视频线。

如果你将使用模拟视频，你还需要一根 3.5 mm 立声音频线，无论你想在连接电视或显示器后获得声音，还是计划连接外部扬声器。

**USB 鼠标和键盘。** 作为一台电脑，树莓派也需要键盘和鼠标。你可以使用有线的或无线的，但要注意，许多用户报告了无线键盘和鼠标的一些问题，因为大多数 Pi 模型在树莓派重启时需要你拔掉再重新插入。

## 开始使用 Pi

现在你已经知道开始树莓派之旅需要什么了，下一步是实际开始使用这台神奇的微型计算机。在我们开始设置无线电台并学习适用于你火电台（Ham Shack）的各种无线电程序之前，必须先学会如何安排一切，以便让你的 DJ 技巧尽情发挥。

在本章中你将学习关于安装和开始使用新树莓派的所有知识。我保证，当你进入下一章时，你将不再对几天前买的原始主板感到畏惧。那么，让我们开始吧？

### 安装

现在是时候在你的树莓派上安装操作系统了。与传统电脑不同，树莓派上的操作系统不是安装在硬盘上（因为 Pi 没有硬盘），而是安装在 SD 卡上。虽然有许多方法可以在 Pi 上安装操作系统，但这种是最好也最方便的。

### NOOBS 和 BerryBoot

NOOBS（即 New Out of The Box Setup）是树莓派基金会创建的官方安装方法，目的是简化初学者的操作，并在单张卡上为不同的操作系统添加多个支持工具。BerryBoot 先于 NOOBS 出现，它实际上支持更多的操作系统，并能够将它们安装在 USB 闪盘上，还可以备份、克隆和恢复操作系统。

安装 NOOBS 和 BerryBoot 你需要执行以下操作：

- 访问 `http://www.berryterminal.com/doku.php/berryboot` 下载 BerryBoot，或者访问 `http://www.raspberrypi.org/downloads` 下载 NOOBS。
- 根据你使用的操作系统，将你的 SD 卡格式化为 FAT32。
- 如果你使用 Windows，建议使用 SD 协会的 SD Formatter。访问 `https://www.sdcard.org/downloads/formatter_4/` 获取它。
- 如果你是 Linux 用户，请坚持使用 GParted。
- 现在是在向 SD 卡上解压下载的压缩包了。

### 使用 RAW 镜像安装 Raspbian

这是用于在 SD 卡上安装操作系统的原始方法。RAW 镜像包含了所有必要的二进制数据，包括主引导记录（MBR）以及所有分区。

这种方法的最大优势是它支持每个操作系统，而且几乎不会出错，但缺点在于它的灵活性不够。在同一张卡上启动多个系统相当困难。此外，镜像文件具有静态分区表，这意味着你将有很多空闲但未使用的空间。

#### 在 Windows 上写入镜像

- 访问 `https://launchpad.net/win32-image-writer` 并下载 Win32 Disk。
- 选择正确的镜像文件。
- 在下拉菜单中找到并选择你的 SD 卡。
- 点击“写入”并弹出卡片。

#### 在 Linux 上写入镜像

- 首先，确保 SD 卡未被挂载。
- 将 `mmcblk0` 替换为正确的设备以向磁盘写入。为此，你必须运行此命令：

```
# dd if=file.img of=/dev/mmcblk0 bs=4M
```

- 运行此命令 `# sync` 是非常重要的，以便在移除 SD 卡之前刷新文件系统缓冲区。

### 启动

现在你已经安装了 Raspbian 并写入了镜像，是时候通过首次启动你的 Pi 来进行初始设置了。最好的方法是使用键盘、显示器和鼠标。

插入卡片并连接显示器、键盘和鼠标。当提示用户名时，输入 `pi`，当提示密码时，输入 `raspberry`。最后，输入 `startx` 加载熟悉的 UI。

只需将以太网线连接到树莓派即可。

### 扩展文件系统

如果你使用 Raspbian，可以通过 `raspi-config` 脚本中的 `Expand Filesystem`（扩展文件系统）自动完成此操作。如果你选择运行 `sudo raspi-config`，也有手动启动它的方法。然而，如果没有提供自动处理的方法，你实际上可以在树莓派上扩展文件系统。

1. 输入以下命令启动 fdisk：

```
# fdisk /dev/mmcblk0
```

2. 按 `p` 并回车。显示内容应类似于：

```
Command (m for help): p
Disk /dev/mmcblk0: 29.7 GiB, 31918653440 bytes, 62341120 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: dos
Disk identifier: 0x417ee54b
```

| Device | Boot | Start | End | Blocks | Id | System |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| /dev/mmcblk0p1 | | 2048 | 186367 | 92160 | c | W95 FAT32 (LBA) |
| /dev/mmcblk0p2 | | 186368 | 3667967 | 1740800 | 5 | Extended |
| /dev/mmcblk0p5 | | 188416 | 3667967 | 1739776 | 83 | Linux |

3. 卡上有一个逻辑分区 P5 的扩展分区 P2。你需要删除 P2 以自动删除 P5。

```
Command (m for help): d
Partition number (1,2,5, default 5): 2
```

分区 2 已删除。

4. 现在你需要在刚刚删除的地方创建一个新的扩展分区。该分区的扇区必须与被删除区的扇区匹配。之后，只需接受建议的最后一个扇区即可用尽空闲空间。

```
Command (m for help): n
Partition type :
   p   primary (1 primary, 0 extended, 3 free)
   e   extended
Select (default p): e
Partition number (2-4, default 2): 2
First sector (186368-62341119), +size{K,M,G,T,P} (186368-62341119):
Last sector, +sectors or +size{K,M,G,T,P} (186368-62341119), default 62341119):
```

创建了一个类型为“扩展”、大小为 29.7 GiB 的分区 2。

5. 代被删除分区创建一个新的逻辑分区并确保该分区与旧的起始扇区匹配：

```
Command (m for help): n
Partition type:
   p   primary (1 primary, 1 extended, 2 free)
   l   logical (numbered from 5)
Select (default p): 1
```

添加逻辑分区 5

第一个扇区 (188416-62341119，默认 188416):

最后一个扇区，+sectors 或 +size{K,M,G,T,P} (188416-62341119)，默认 62341119):

创建了一个类型为 'Linux' 大小为 29.7 GiB 的新分区 5。

6. 显示分区表并确保结束扇区是唯一的不同：

```
命令（m 获取帮助）：p
磁盘 /dev/mmblk0: 29.7 GiB, 31918653440 字节, 62341120 扇区
单位: 1 * 512 = 512 字节的扇区
扇区大小 (逻辑/物理): 512 字节 / 512 字节
I/O 大小 (最小/最优): 512 字节 / 512 字节
磁盘标签类型: dos
磁盘标识: 0x417ee54b
```

| 设备 |  | 开始 | 结束 | 块 |
|---|---|---|---|---|
| Id /dev/mmblk0p1 | 2048 | 186367 | 92160 | c |
| W95 FAT32 (LBA) /dev/mmblk0p2 | 186368 | 62341119 | | |
| 31077376 5 | 扩展分区 | | | |
| /dev/mmblk0p5 | 188416 | 62341119 | | |
| 31076352 83 | Linux | | | |

7. 将分区表写入磁盘：

```
命令（m 获取帮助）：w
```

8. 重启你的树莓派：

```bash
# reboot
```

9. 现在登录以调整文件系统大小：

```bash
# resize2fs /dev/mmblk0
```

### 用户管理

安装好操作系统后，你应该采取的下一步是设置一个实际的用户账户。正如你可能注意到的，Raspberrybian 已经有一个名为 pi 的默认用户以及默认密码 raspberry。那么为什么要更改它们呢？嗯，用户名和密码是众所周知的，运行这些默认设置的系统完全不安全。如果你想在将来避免任何安全问题，我建议你更改密码。

安装程序没有设置 root 密码，因此用户应该使用 `sudo` 来运行此类命令。设置 root 密码非常重要，因为它将允许在 root shell 中执行管理任务。以下是你可以如何标准化安装的方法：

1. 以 pi 用户身份登录。

2. 使用此命令更改默认密码：

```bash
# passwd
```

3. 进入 root shell：

```bash
# sudo -i
```

4. 再次运行 `passwd` 来更改密码。由于你正处于 root shell 中，这将自动更改 root 密码。

5. 选择一个新的用户名并使用此命令添加它（在示例中，我使用了 John 作为新用户名）：

```bash
# adduser john
```

6. 如果你想让你的用户执行某些任务，它必须是某些组的一部分。为了确保这一点，输入以下命令。再次，将 john 替换为你选择的用户名：

```bash
# usermod -a -G m,dialout,cdrom,sudo,audio,video,plugdev,games,users,netdev,input,spi,gpio john
```

如果你想以新用户的身份启动桌面，实际上可以在不使用 `raspi-config` 的情况下实现。以下是操作方法：

1. 启用 LightDM 服务：

```bash
# update-rc.d lightdm enable 2
```

2. 在 `/etc/lightdm/lightdm.conf` 中设置 `autologin-user` 变量，这是必须的。请注意，使用 `#` 注释将会在你每次启动 Pi 时为你提供登录窗口，这要安全得多，特别是当你有多个用户时非常有益。

如果你想实现相反的操作，只需禁用 LightDM 即可。

### 远程访问树莓派

安装好操作系统后，你可以使用 USB 键盘、USB 鼠标和 HDMI 屏幕开始开发。然而，如果你没有这些配件，一切也无可救。你仍然可以远程访问你的树莓派。这里有几种实现方法。

#### SSH 远程服务器

SSH 是一个非常棒远程服务器，可以用于大多数远程管理过程。由于 Pi 是一个极好的“无头”服务器，Raspbian 默认就可能安装了远程服务器。在 Linux 中，你可以通过 `ssh` 命令轻松地连接到 SSH：

```bash
ssh user@IP:port
```

如果你使用的是 Windows，可以使用 PuTTY 建立 SSH 连接，你可以从 `http://www.chiark.greenend.org/~sgtaham/putty/` 下载它。

确保 SSH 安全

如果你想从本地网络外部访问树莓派，那么你应该非常小心，并尽一切保护它免受不受的机器人和黑客的攻击。大多数机器人倾向于连接到 22 端口并暴力破解密码，即使密码是安全的，这仍会导致日志中充满多次建立连接的尝试。

保护自己最简单的方法是更改端口号并禁用 SSH 的 root 登录选项。要做到这一点，编辑 `/etc/ssh/sshd_config` 并设置这些选项：



```bash
Port 1286 # 任何未使用的端口号均可
PermitRootLogin no
```

但这无法阻止别人扫描你的开放端口。最理想的情况是禁用任何密码登录，并仅为此目的使用密钥。要做到这一点，你需要生成两个密钥——公钥和私钥。将公钥发送到远程服务器，并将私钥妥善地保密，并用它代替密码进行登录。

如果使用 Windows，可以使用 PuTTY 生成密钥：

- 将公钥拷贝到这里`~/.ssh/authorized_keys`，并将私钥保存在 PC 上。
- 如果你想保护密钥，更改`authorized_keys`的权限：

  ```bash
  # chmod 600 ~/.ssh/authorized_keys
  ```

- 在 PuTTY 中，点击“Save Private Key”。

在 Linux 中，你可以通过这种方式生成密钥：

- 输入`ssh-keygen -t rsa`。
- 现在，接受推荐的保存位置并输入你的密码短语。`id_rsa.pub`的内容应该被复制到`~/.ssh/authorized_keys`，但这可以轻松完成：

  ```bash
  # ssh-copy-id user@IP -p PORTNUMBER
  ```

- 一旦你看到可以使用私钥连接到树莓派，返回`/etc/ssh/sshd_config`禁用密码登录：

  ```text
  PasswordAuthentication no
  ```

最棒的一点是你实际上可以添加多个公钥。例如，如果你想允许他人访问你的树莓派，只需向他们索要公钥并将密钥添加到你的`authorized_keys`文件中即可。

还有一件事要做，就是安装`fail2ban`。这将封禁所有恶意 IP 并对抗各种攻击：

```bash
# apt-get install fail2ban
```

现在，打开配置文件以编辑`sudo nano /etc/fail2ban/jail.local`，并粘贴以下内容：

```ini
# SSH
# 3次重试失败：封禁 10 分钟
[ssh]
enabled = true
maxretry = 3
bantime = 600
ignoreip = 192.168.0.0/24

[ssh-ddos]
enabled = true
maxretry = 10
bantime = 60
ignoreip = 192.168.0.0/24
```

现在重启`fail2ban`：

```bash
sudo /etc/init.d/fail2ban restart
```

#### 传输文件

如果你认为 SSH 仅用于执行命令，那么你就错了。SSH 也提供了传输文件的机会。

如果你想执行简单的文件传输，这个命令可以帮助你：

```bash
$ scp /path/to/src user@IP:/path/to
```

然而，如果你在寻找更强大的命令，可以使用这个：

```bash
$ rsync /path/to/src user@IP:/path/to -av
```

如果你是 Windows 用户，可以使用 WinSCP，可以从 http://winscp.net 获取。它的 GUI 使用密钥，并允许你在 PC 和 Pi 之间传输文件。

#### X11 转发

好了，你现在可以执行命令并传输文件。但你还需要考虑到 GUI。X 窗口系统可以使用远程显示，你可以使用 SSH 将 GUI 程序转发到本地 X 服务器。

如果你使用 Linux，可以像以前一样启动 SSH，只需增加`-Y`参数。当你的 SSH 会话准备就绪，启动`leafpad`。

如果你是 Windows 用户，你需要运行一个 X 服务器。这里是一些可选方案：

- Cygwin/X 可以从 http://x.cywin.com/ 找到。
- Xming，位于 http://sourceforge.net/projects/xming/。
- VcXrv 可在此获取：http://sourceforge.net/projects/vcxsrv/。

#### 使用 Screen 维持远程会话

虽然`screen`和`ssh`并不直接相关，但它们是黄金组合。思考一下如果在你的 SSH 会话期间连接中断会发生什么。显然，一切都会丢失。这就是为什么`screen`如此重要。通过`screen`，你可以根据需要轻松地重新连接和分离。例如，如果你的连接中断了，你可以重新连接回到`screen`会话并从你离开的地方继续。由于 Raspian 默认设置中没有包含`screen`，你需要使用此命令来安装它：

```bash
# apt-get install screen
```

安装完成后，你可以通过运行以下命令启动它：

```bash
# screen n
```

要开始使用，你需要添加一些绑定键。你可以通过`CTRL + A`然后按另一个键来实现。例如，如果你想断离（detach）`screen`会话，可以`CTRL + A`然后按`d`。断离后，你可以通过运行以下命令返回：

```bash
# screen -x
```

#### 反向 SSH（Reverse SSH）

如果你的 Pi 位于防火墙后面且没有访问端口转发的权限，那么你无法直接访问它。但如果你想要连接的电脑不在防火墙后面，并且运行着活跃的 SSH 服务器，那么使用反向 SSH 是最佳选择。

使用此命令启动 SSH：

```bash
$ ssh -N -R 2222:localhost:22 user@IP
```

在这里，`-N`意味着你不想执行其他命令，`-R 2222:localhost:22`意味着远程计算机会将端口 22 隧道到端口 2222。

之后，你可以连接到 2222 端口，它会将你重定向到 22 端口：

```bash
$ ssh user@localhost -p 2222
```

#### VNC 与虚拟显示（Virtual Display）

你也可以使用 VNC 远程访问 Pi。VNC 有两种形式。第一种`x11vnc`允许 Pi 连接的显示器进行远程镜像。另一种被称为虚拟显示（virtual display）。虚拟显示不会显示在显示器上，对于那些需要启动多个独立 VNC 会话的情况非常有用。但没有 VNC 客户端，你无法连接到 VNC。一个完美的例子是 TightVNC。

因此，你唯一实际上可以使用显示器的方法是安装了`x11vnc`，这可以通过运行以下命令完成：

```bash
# apt-get install x11vnc
```

然而，要使用虚拟显示，你需要安装 TightVNC，可以通过运行以下命令完成：

```bash
# apt-get install tightvncserver
```

当你第一次运行`vncserver`时，你会注意到一些步骤。你需要关注输出内容，因为你将在找到服务器实际运行的显示器编号。如果你想停止运行 VNC，可以使用`-kill`选项。这将杀死显示器`:1:`的服务器：

```bash
$ vncserver -kill :1
```

#### Synergy

还有一种在不同系统之间共享鼠标和键盘的选项。例如，你可以有一个连接到 Pi 的显示器，并且实际上可以通过连接在 PC 上的鼠标和键盘来运行。

以下是操作方法：

- 在你的 PC 上下载 synergy 服务器。你可以在 http://synergy-foss.org 找到它。运行它并按照设置步骤进行操作。
- 使用此命令在 Pi 上安装它：

  ```bash
  # apt-get install synergy
  ```

- 使用此命令从 Pi 的桌面启动 Synergy：

  ```bash
  # synergyc IP
  ```

# 无线连接

想要在树莓派 Pi 上建立互联网连接是显而易见的。有几种方法可以实现，但由于你可能对设置无线连接最感兴趣，在本节中，我将讨论如何让你的 Pi 无线连接网络。

### Pixel 桌面（Pixel Desktop）

提供了一个 GUI，可以帮助你在带有 PIXEL 桌面的 Raspbian 中设置无线连接。如果你查看 Pi 菜单栏的右侧，你会看到网络图标。如果你的 Wi-Fi 适配器已插入，点击该图标后将列出可用的无线网络。如果你的 Wi-Fi 适配器已插入，点击该图标后将列出可用的无线网络。如果你的 Wi-Fi 适配器已插入，点击该图标后将列出可用的无线网络。如果网络是加密的，会弹出一个对话框让你输入密码。如果你的 Wi-Fi 适配器已插入插入，点击图标后将列出列列无线网络。。网络是是加密，，的，会出一个出一个输入。输入密码。

密码：

### 命令行（Command Line）

这是在，你在 Pi Pi Pi连接连接连接方法方法方法方法方法方法方法方法方法方法方法方法无线方法。如果你的 Wi-Fi 适配器已插入，点击该图标后将列出可用的无线网络。如果你的 Wi-Fi 适配器已插入，点击该图标后将列出可用的无线网络。如果你的 Wi-Fi 适配器已插入，点击该图标后将列出可用的无线网络。如果网络是加密的，会弹出一个对话框让你输入密码。如果你的 Wi-Fi 适配器已插入，点击该图标后将列出可用的无线网络。如果网络是加密的，会弹出一个对话框让你输入密码。

### 安装 Samba（Installing Samba）

想象你在 PC 上有文件想在树莓派上访问。为了这个目的，你需要安装 Samba 软件。但我的网络中没有 Windows 客户端，你可能会这样。好吧，即使如此，你仍然可以从 Samba 中获益。例如，Photo Mate RAW —— 一个 Android 处理应用程序——可以访问存储在 PC 上的图片。如果你想从 Android 访问文件，那么 Samba 就是方法。

你可以通过以下命令安装 Samba：

```bash
sudo apt-get install samba samba-common-bin
```

然后，将用户 pi 添加 smbpasswd 文件：

```bash
sudo smbpasswd -a pi
```

在 nano 中，打开`smb.conf`文件：

```bash
sudo nano /etc/samba/smb.conf
```

确保删除`security = user`这一行。在文件末尾添加共享定义。在下面的例子中，我们想访问照片：

```ini
[Photos]
path = /path/to/dir
available = yes
valid users = @users
read only = no
browsable = yes
public = yes
writable = yes
```

之后，只需保存你的更改并重启 Samba：

```bash
sudo /etc/init.d/samba restart
```

显然，你需要做的第一件事是安装 Raspian 操作系统。回到上一章的开头，按照步骤安装操作系统。完成后，启动设备并对你的网络进行简单的`nmap`扫描，看看是否能找到你的树莓派：

```bash
sudo nmap -sP 192.168.1.1-25 4
```

假设发现了一个具有树莓派地址的设备：

```text
Nmap 扫描 report for raspberrypi (192.168.1.111)

Host is up (0.0013s latency)

MAC Address: B8:27:EB:B6:A3 (Raspberry Pi Foundation)
```

现在，使用 SSH 通过默认凭据连接到该 IP。记得我们说过更改密码至关重要吗？现在是时候执行它了。

```bash
pi@raspberrypi:~ $ passwd
Changing password for pi.
(current) UNIX password:
Enter new UNIX password:
Retype new UNIX password:
passwd: password updated successfully
```

之后，更新系统：

```bash
pi@raspberrypi:~ $ sudo apt-get update
pi@raspberrypi:~ $ sudo apt-get upgrade
```

确保安装了所有可用的更新。现在，让我们移除以太网线并设置无线连接。当然，如果你没有 Wi-Fi 适配器或卡，你也可以跳过此步继续使用以太网连接。

在此之前，让我们确保 Wi-Fi 卡被自动识别：

```bash
pi@raspberrypi:~ $ iwconfig
wlan0 unassociated Nickname:"<WIFI@REALTEK"
Mode:Managed Frequency=2.412 GHz Access Point: Not-Associated
Sensitivity:0/0
Retry:off RTS:off Fragment thr:off
Power Management:off
Link Quality:0 Signal level:0 Noise level:0
Rx invalid nwid:0 Rx invalid crypt:0 Rx invalid frag:0
Tx excessive retries:0 Invalid Missed:0
```

在这种情况下，你可以看到卡被注册为`wlan0`。让我们编辑`wpa_supplicant`配置并重启接口，就像我们在上一章中讨论的那样：

```bash
pi@raspberrypi:~ $ sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
```

```ini
network={
ssid="MYSSID"
PSK="MYWIFIPPASSWORD"
}
```

重启网络接口并检查其是否有 IP 地址：

```bash
pi@raspberrypi:~~$ sudo ifdown wlan0
pi@raspberrypi:~~$ sudo ifup wlan0
pi@raspberrypi:~~$ ifconfig wlan0
```

```text
wlan0 Link encap:Ethernet HWaddr 74:da:38:5a:6e:e0
inet addr:192.168.1.138 Bcast:192.168.1.255 Mask:255.255.255.0
inet6 addr: fe80::26f5:8a4f:82c4:b75e/64 Scope:Link
UP BROADCAST RUNNING MULTICAST MTU:1500 Metric:1
RX packets:24 errors:0 dropped:6 overruns:0
TX packets:37 errors:0 dropped:0 overruns:0 collisions:0 txqueuel:1000
RX bytes:2933 (2.8 KiB) TX bytes:8033 (7.8 KiB)
```

### 安装并配置 AX.25

无线电所需的一切都运行在 AX.25 协议之上。这就是为什么安装它至关重要：

```bash
pi@raspberrypi:~ $ sudo apt-get install ax25-tools ax25-node ax25-apps
```

现在，让我们配置作为无线电网络接口的 AX.25 端口：

```bash
pi@raspberrypi:~ $ sudo nano /etc/ax25/exports
```

文件应该有两个被`#`注释的示例行。现在添加这些：

```text
0 CALLSIGN-N 9600 255 2 145.030 MHz (120bps)
```

让我们解析上面的行：

- `0`——这是端口名称。可以是文本或数字。
- `CALLSIGN-N`——这是你的呼号，后面必须跟一个数字。
- `9600`——代表端口速度。实际上这不是无线电连接的速度，而是 TNC 与计算机之间的速度。在这种情况下是 9600 波特率。
- `255`——这是 PacLen（包长度）。
- `2`——这是窗口（window）。
- `145.030 MHz (120bps)`——这是一个提示。你可以在这里输入任何文本描述来提醒自己该端口的作用。

接下来，是设置 netrom（一种运行在 AX.25 端口上的数据包协议）。为了建立节点，你需要先设置 netrom。如果你只想连接到其他节点，则不必强制配置 netrom，但请记住，这将使连接远程节点的过程变得简单得多。

```bash
pi@raspberrypi:~ $ sudo nano /etc/ax25/nrports
```

现在，添加类似的内容：

```text
netrom CALLSIGN-N #ALIAS 255 145.030 MHz (1200bps)
```

再次解析：

- `Netrom`——端口名称。
- `CALLSIGN-N`——与之前相同，呼号后跟数字。
- `#ALIAS`——netrom 数据包的别名。将其视为他人连接到你节点的备用名称。
- `255`——PaClen（包长度）。
- `145.030 MHz (1200 bps)`——之前一样，作为 netrom 端口的描述。

让我们编辑一个守护进程配置文件。删除文件中的所有内容并替换为下面的文本。小心，你必须以使其匹配已配置端口的方式进行编辑：

```ini
[CALLSIGN-N VIA 0]
NOCALL ***** L
default ***** - root /usr/sbin/ax25-node ax25-node
<netrom>
NOCALL ***** L
default ***** - root /usr/sbin/ax25-node ax25-node
```

不要忘记用实际内容更新章节标题。例如，`CALLSIGN-N`应该是你的呼号加上你选择的数字。`VIA 0`应该更新并包含 AX.25 端口的名称等。

现在，让我们启用 AX.25 端口的接口：

```bash
sudo kissattach /dev/ttyUSB0
```

`/dev/ttyUSB0`需要替换为你自己的 KISS TNC 对应的串口端口。记住，这里的`0`实际上是你之前配置的 AX25 文件名。通过使用`ifconfig`，你现在可以检查 AX.25 端口是否上线：



```
pi@raspberrypi:~ $ ifconfig ax0
ax0 Link encap:AMPR AX.25 WHDaddr CALLSIGN-N
UP BROADCAST RUNNING MTU:255 Metric:1
RX packets:0 errors:0 dropped:0 overruns:0 frame:0
TX packets:0 errors:0 dropped:0 overruns:0 carrier:0
```

## 配置数据包节点

在确保 AX.25 运行后，我们现在可以设置数据包节点，使其启动后自动运行，并带有正确的提示、命令和权限监听接入连接。

首先，编辑负责节点主设置的文件，即`node.conf`文件。

```
pi@raspberrypi:~ $ sudo nano /etc/ax25/node.conf
```

虽然文件的大部分内容不需要更改默认设置，但应该修改`HostName`和`NodeId`。注意你还需要将`Nport`配置为指定的端口名称。

以下是外观示例：

```
Host KE7SAL-9
NodeId CARMEL:KE7SAL-9
NrPort netrom
```

让我们添加节点权限。如果你愿意，可以将其设置为用户需要密码。

```
pi@raspberrypi:~ $ sudo nano /etc/ax25/node.perms
```

读取`node.perms`页面查看设置和权限。在示例中，`node.perms`文件如下：

```
# user type passwd perms
ke7sal * * PASS 25 5
```

```
# 每种连接类型的默认权限。
#
* ax25** * 7
* netrom ** * 7
* local ** * 7
* ampr ** * 7
* inet ** * 7
* host ** * 7
```

```
pi@raspberrypi:~ $ sudo nano /etc/ax25/nrbroadcast
```

主页面包含大量信息。此示例的设置如下：

```
# ax25_name min_obs def_qual worst_qual verbose
0 5 192 100 0
```

现在是时候创建 netrom 端口了：

```
pi@raspberrypi:~ $ sudo nrattach notch m
```

将其设置为 TCP/IP 服务将使你更容易从 shell 直接连接到本地数据包节点（packet node）。不过，让我们先定义端口和服务吧：

```
pi@raspberrypi:~ $ sudo nano /etc/services
```

在末尾添加此行：

```
ax25-node    4444/tcp    # KE7SAL 数据包节点
```

在这里你实际上可以将 4444 端口更改为任何未使用的端口。让我们让该服务在启动后自动运行：

```
pi@raspberrypi:~ $ sudo nano /etc/inetd.conf
```

在末尾添加：

```
ax25-node stream tcp nowait root /usr/bin/ax25-node ax25-node
```

现在，你可以重启服务了：

```
pi@raspberrypi:~ $ sudo service inetd restart
```

这一切使你能够直接从命令行 telnet 到本地数据包节点。此外，你也可以从任何其他系统 telnet 它，只要你的树莓派在同一网络中，并且开放了 4444 端口允许远程连接即可。

```
Spi@raspberrypi:~ $ telnet localhost 4444
Trying ::1...
Trying 127.0.0.1...
Connected to localhost.
```

转义字符是 `'^]'`。

LinuxNode v0.3.2 (KE7SAL-9)

login:

太好了！现在只需使用你的呼号登录。你会看到类似的内容：

```
#CARMEL:KE7SAL-9 欢迎来到 KE7SAL-9 网络节点
```

输入 `?` 查看命令列表。`help <commandname>` 会提供指定命令的描述。

如果你想获取所有命令列表，只需输入 `?`。现在，调整节点的无线电，并使用 AX25 发起呼叫。你可以通过添加以下内容来对你的节点进行更改：

```
C 0 WALKER
```

当然，你必须更新这条命令。`C` 代表 CONNECT（连接），不一定需要更改。`0` 代表我们之前配置的 AX.25 端口。`WALKER` 是本地数据包节点的别名。你必须将其更改为你自己的本地数据包节点的别名。你应该得到类似下面的内容：

```
#CARMEL:KE7SAL-9 Trying WALKER on port 0... Type <RETURN> to abort
#CARMEL:KE7SAL-9 Connected to WALKER on port 0 (Escape: CTRL-T)
```

现在，断开连接：

```
#CARMEL:KE7SAL-9 Trying WALKER on port 0... Type <RETURN> to abort
#CARMEL:KE7SAL-9 Connected to WALKER on port 0 (Escape: CTRL-T)
bye
#CARMEL:KE7SAL-9 Reconnected to KE7SAL-9
```

```
bye
#CARMEL:KE7SAL-9 Goodbye
```

连接被远程主机关闭。

我们希望我们的节点能够监听其他节点的 netrom 广播，并确保我们确实有一个服务器在监听其他系统的接入连接。这可以通过简单的两行代码实现：

```
pi@raspberrypi:~ $ sudo netromd
pi@raspberrypi:~ $ sudo ax25d
```

我们已经成功配置了它。

## 启动节点引导

实现此操作有很多方法，但我们将选择最简单的。我们将简单地将所有命令放在一个地方 - `/etc/rc.local`

```
pi@raspberrypi:~ $ sudo nano /etc/rc.local
```

在编辑行之前，添加以下文本：

```
/sbin/modprobe ax25 # 加载 ax.25 内核模块
/sbin/modprobe netrom # 加载 netrom 内核模块
/usr/sbin/kissatatch /dev/ttyUSB0 0 # 创建 AX.25 接口
/usr/sbin/nratatch netrom # 创建 netrom 接口
/usr/sbin/netromd # 启动 netrom 服务
/usr/sbin/ax25d # 启动 ax.25 服务并开始监听
```

现在，重启你的树莓派：

```
pi@raspberrypi:~ $ sudo reboot
```

## 备份节点列表

通常节点广播列表每 30 – 60 分钟更新一次。一旦节点看到列表，它会自动更新自己的表。重启节点后，列表会被清空，节点变得更难以使用。在这种情况下，你只需要等待更多的广播。如果你想让过程更顺畅，可以定期备份你的节点并在启动时恢复列表。

首先，你需要创建一个恢复脚本：

```
pi@raspberrypi:~ $ sudo touch /etc/ax25/nodebackup.sh
pi@raspberrypi:~ $ sudo chmod u+x /etc/ax25/nodebackup.sh
```

如果你创建一个定时任务（cron job），你就可以定期备份节点：

```
pi@raspberrypi:~ $ sudo crontab -e
```

在此示例中，此行将其设置为每 60 分钟运行一次：

```
0 * * * * /usr/sbin/nodesave /etc/ax25/nodebackup.sh
```

使文件具有可执行权限，并在启动时运行它：

```
/etc/ax25/nodebackup.sh
```

在检查其如何工作之前，你需要先等待节点列表填充。

```
pi@raspberrypi:~ $ sg cat /etc/ax25/nodebackup.sh
```

现在只需重启。当你的树莓派再次上线时，重新登录数据包节点以列出已知节点。如果它不是空的，说明一切运行正常。

## 在空中玩 Zork

拥有一个数据包节点真的太棒了。虽然节点大多是为了应急目的，但你也可以为你的数据包无线电找到一些非常很棒的用途。由于这套设备可能只需要花费你大约 100 美元，我认为这是一个非常负担得起的爱好。

如果等待紧急情况或在节点之间跳跃并将它们全部映射在一起有点很无聊，那么这里有一个你全新的无线电数据包节点的绝佳用途。通过这个示例，你可以学习如何在空气中玩 Zork，如果这都不算惊奇，我真的不知道什么才算惊奇了。

但是为了让你能够在 Linux 上玩 Zork，你首先需要一个模拟器。此目的的绝佳模拟器是 `frotz`：

```
pi@raspberrypi:~ $ sudo apt-get install frotz
```

之后，你可以直接从 infocom 下载 Zork：

```
pi@raspberry:~ $ mkdir ~/games
pi@raspberry:~ $ mkdir ~/games/zork
pi@raspberry:~ $ cd ~/games/zork
pi@raspberry:~/games/zork $ curl http://www.infocom.org/downloads/zork1.Zip > zork.zip
```

（注：此处为示例）

在下载完成后，你可以本地启动 Zork：

现在你需要找到一种方法让节点用户能够实际运行 Frotz 模拟器并玩 Zork。为了正确启动应用程序，首先需要创建一个 shell 脚本：

```
pi@raspberry:~ ~ nano zork.sh
```

创建脚本后，添加以下：

```bash
#!/bin/bash
export HOME="/home/pi"
export TERM="linux"
/usr/games/frotz/home/pi/zork/DATA/ZORK1.DAT
```

允许执行：

```
pi@raspberry:~ ~ chmod u+x zork.sh
```

通常当你启动 Zork 时只需要输入最后一行。但当你从 AX25 端口启动它时，如果没有导出终端变量，Frotz 将无法启动。由于我们已经有了脚本，我们唯一做的就是在节点上创建一个新命令：

```
pi@raspberrypi:~ ~ sudo nano /etc/ax25/node.conf
```

转到 `ExtCmd` 部分的底部，添加如下：

```
ExtCmd Zork 1 /home/pi/zork.sh NULL
```

这将创建命令 `Zork`。我们使用大写的 `ZO`，这样你就不需要一直使用完整名称。确保那里留有 `NULL` 部分，否则节点将无法执行。

# 树莓派业余无线电项目

一旦建立并运行了自己的业余无线电台，你会发现你实际上上可以用它做几十种事情，而不仅仅是将其用于应急目的。在现阶段，发送和跟踪无线电信号可能让你觉得无从从，甚至认为是不可能的，但请相信我，一旦你尝试了本章节中精彩的项目，你不仅会发现业余无线电是一项多么棒的爱好，还会发现它可以轻松掌握。

虽然你可以先尝试这些程序中的任何一个，但我真的建议你按照列出的顺序进行，因为我在排列顺序上花费了大量精力，以帮助你快速掌握业余无线电。我们开始吧？

## 使用 Fldigri 进行数字调制

首先，让我简要解释一下什么是数字模式以及它们为什么重要。数字模式代表了业余无线电爱好者在键盘帮助下操作的一种手段。在这里，计算机充当调制解调器（或称调制-解调器），允许你打字，并看到他人的输入内容。它负责控制发射机，提供实用的功能，并根据需要更改模式。在这种情况下，这些模式用于高频频段，特别是聊天模式——即用于与电报进行对话的模式——它们能让不同的操作者参与到同一个网络。

树莓派可以使用 USB 声卡的音频输入来解码这些数字模式。今天业余无线电用户支持这些模式的最流行且有效的程序是 `Fldigi`。该程序与高频（HF）SSB 收发机配合工作，并使用 USB 卡向无线电台输入和输出。

`Fldigi` 最棒的一点是它是多模式的，这意味着它可以运行多种模式，而无需切换程序。`Fldigi` 包含了所有流行的模式：

- THOR
- CW
- PSK
- Concordia
- Throb
- NAVTEXT/SITB
- Hell
- Olivia
- 8PSK
- RTTY
- DominoX
- MFSK
- MT63
- QPSK
- WEFAX

以下是如何使用 PIXEL Desktop GUI 安装 `Fldigi`：

1. 从 PIXEL GUI 中打开左上角的应用程序菜单。选择“偏好”（Preferences），然后选择“添加/移除软件”（Add/Remove Software）
2. 搜索 `Fldigi`，并勾选复选框
3. 找到“应用”（Apply）按钮并点击它以安装 `Fldigi`

安装完成后，你只需打开 PIXEL GUI 中左上角的应用程序菜单，选择“Internet, Fldigi”即可启动该程序。

调制与解调的硬件配置：

- 八田 Yaesu 数据线，CT-39
- CT-39 数据输出线，1200 bps – FT-857D
- CT-39 数据输出，连接到 Behringer Xenyx 320 USB 的线路输入
- CT-39 数据输入，插入树莓派的扬声器接口

无线电控制的硬件配置：

- 树莓派 P3 Model B
- 八田 Yaesu Cat 线，CT-62
- USB 双串口适配器 (Micro Connectors. Inc)
- 八田收发机，FT-857D

配置树莓派端口：

- 确保树莓派 P3 Model B 已开机。
- 使用带供电的 USB Hub，将 USB 双串口适配器插入树莓派的 USB 端口。
- 这应该是 `/dev/` 目录下显示的内容：`dev/ttyUSB0` `/ttyUSB1`
- 将八田 Ya CT-62 Cat 线插入 FT-857D 收发机
- 开启 FT-857D 收发机
- 将八田 CT-62 线连接到双串口适配器的 RS-232 S1。RS-232 S1 接口为 `/dev/ttyUSB0`。

## 业余无线电世界时

你可以找到几个钟程序，但我坚信 `Twclock` 是目前最好的。这个程序不仅显示 GMT 时间和本地时间，还会显示全球数百个城市的时间。此外，它还带有一个内置闹钟，可以提醒你进行台呼代码的时间。

这个闹钟实际上可以通过几种不同的方式通知你。它可以闪烁闹钟按钮、通过 CW 音发送你的呼号，或者简单让连接的扬声器鸣响。

安装过程非常简单，可以通过命令行（CLI）完成。

首先，你需要更新树莓派的仓库索引。可以通过以下命令完成：

```
sudo apt-get update
```

然后，你需要搜索仓库索引并找到 `twclock` 程序：

```
apt-cache search twclock
```

最后，你可以使用此命令安装 `twclock`：

```bash
sudo apt-get install twclock
```

启动 `Twclock`，打开 PIXEL 的左上角应用程序菜单，然后选择“附件”（Accessories）中的 `Twclock`。你会发现这会打开两个 `twclock` 程序。其中一个用于显示本地时间，另一个用于 GMT 时间。

如果由于某种原因你想卸载 `twclock`，可以输入此命令：

```bash
sudo apt-get uninstall twclock
```

## SDR 和 GNU Radio

在解释 GNU Radio 是什么以及如何安装它之前，我只想告诉你们，通过树莓派，你实际上可以搭建最廉价的 SDR（软件定义无线电）接收器。为了这个目的，除了树莓派之外，你还需要一个廉价的 RTL 狗子和一个 USB 声卡。如果你认为这可能很简陋，你会惊讶地发现，你实际上可以接收从 25 MHz 到惊人的 1800 MHz 的任何信号。要创建一个功能相当强大的扫描仪，你只需要将其连接到磁盘天线上即可。

当然，要实现这一切现实，你需要在 Raspbian 中运行 SDR。

现在来说说 GNU。GNU radio 是一个免费软件工具包，负责处理块以实现软件定义无线电。它可以与一些低成本的外部硬件配合创建 SDR，甚至可以在没有硬件的仿真环境中使用。它主要由想要支持现实无线电以及进行 Wi-Fi 通信研究的爱好者使用。

在大多数情况下，GNU Radio 的应用是用 Python 语言编写的，而提供的信号处理路径是用 C++ 语言实现的，并在可能的情况下使用一些处理器浮点扩展。

此特定包附带有 `gnuradio-companion`，这是一个可以创建信号流图并生成源码的图形化工具。它还包含了许多其他实用工具。

安装方法同样使用命令行（CLI）。首先，你需要更新树莓派的仓库索引：

```bash
sudo apt-get update
```

然后，你需要搜索索引查找 `gnuradio` 程序。你可以运行此命令：

```bash
apt-cache search gnuradio
```

这是你将看到的：



在树莓派终端中，使用`apt-cache search gnuradio`命令可以搜索与`gnuradio`相关的软件包。搜索结果如下：

```
pi@raspberrypi:~ $ apt-cache search gnuradio
gnuradio - GNU Radio Software Toolkit
gnuradio-dev - GNU Software Radio development
gnuradio-doc - GNU Software Radio toolkit documentation
gr-air-modes - GNU Radio Mode-S/ADS-B
gr-fcdproplus - RTL Dongle Pro Plus controller for GNU
gr-osmosdr - Gnuradio blocks from the OsmoSDR
libair-modes0 - Guradio Mode-S/ADS-B
libgnuradio-analog3.7.5 - gnuradio analog functions
libgnuradio-atsc3.7.5 - gnuradio atsc functions
libgnuradio-audio3.7.5 - gnuradio audio functions
libgnuradio-blocks3.7.5 - gnuradio blocks functions
libgnuradio-channels3.7.5 - gnuradio channels functions
libgnuradio-comedi3.7.5 - gnuradio instrument control functions
libgnuradio-digital3.7.5 - gnuradio digital communications functions
libgnuradio-dtv3.7.5 - gnuradio digital TV signal processing blocks
libgnuradio-fcd3.7.5 - gnuradio FunCube Dongle support
libgnuradio-fcdproplus - RTL Dongle Pro Plus controller for GNU
libgnuradio-f3.7.5 - gnuradio forward error correction functions
libgnuradio-fft3.7.5 - gnuradio fast Fourier transform functions
libgnuradio-filter3.7.5 - gnuradio filter functions
libgnuradio-iqbalance0 - GNU Radio Blind IQ imbalance estimator and correction
libgnuradio-noaa3.7.5 - gnuradio noaa satellite signals functions
libgnuradio-osmosdr0.1.3 - Gnuradio blocks from the OsmoSDR
libgnuradio-pager3.7.5 - gnuradio pager radio functions
libgnuradio-pmt3.7.5 - gnuradio pmt container library
libgnuradio-qtgui3.7.5 - gnuradio Qt graphical user interface functions
libgnuradio-runtime3.7.5 - gnuradio core runtime
```

`libgnuradio-trellis3.7.5` - gnuradio 栅格调制函数

`libgnuradio-uhd3.7.5` - gnuradio 通用硬件驱动函数

`libgnuradio-video-sdl3.7.5` - gnuradio 视频函数

`libgnuradio-vocoder3.7.5` - gnuradio 语音编码器函数

`libgnuradio-wavelet3.7.5` - gnuradio 小波函数

`libgnuradio-wxgui3.7.5` - gnuradio wxgui 函数

`libgnuradio-zeroq3.7.5` - gnuradio zeromq 函数

`libvolk-bin` - 向量优化运行时工具

`libvolk-dev` - gnuradio 向量优化函数头文件

`libvolk0.0.0` - gnuradio 向量优化函数

现在，请先安装`gnuradio`：

```
sudo apt-get install gnuradio
```

然后安装`gr-osmosdr`：

```
sudo apt-get install gr-osmosdr
```

最后，安装`gr-air-modes`：

```
sudo apt-get install gr-air-modes
```

## 业余卫星跟踪

卫星跟踪绝对是你用你的火腿树莓派可以做的最简单有趣的项目之一。为了让你能尽情跟踪卫星，你必须先安装`GPredict`软件。`GPredict`或`Gnome Predict`是一款免费且实时的卫星跟踪程序。这是一段非常棒的软件，包含了这些惊人的功能：

- 跟踪卫星的数量是不限制的。嗯，它仅限于你计算机的计算能力。
- 你可以在地图、列表、极坐标图中显示数据，甚至将它们所有结合在一起。
- 你可以同时打开多个模块。
- 你还可以使用多个地面站。
- 关于实时数据以及预测过境时间的信息极其详尽。
- 通过`Hamlib rigd`，它实际上允许多普勒无线电调谐。

再次强调，安装过程使用命令行（CLI）。

首先，你需要更新树莓派的仓库索引：

```
sudo apt-get update
```

然后，你需要在索引中搜索`GPredict`程序：

```
apt-cache search gpredict
```

现在，安装软件：

```
sudo apt-get install gpredict
```

要打开`GPredict`，前往 PIXEL GUI 的左上角应用程序菜单，选择“Education”（教育），然后点击“GNOME Predict”。

如果你想卸载它，可以使用此命令：

```
sudo apt-get uninstall gpredict
```

一旦你在树莓派上安装了`GPredict`，你实际上可以跟踪世界范围内任何可以想象的实时卫星。

下一步仅仅是让你的树莓派与天线控制器连接，并开始跟踪现实世界卫星的乐趣。

## XLog 日志记录

就像你的手机一样，你的火腿无线电也需要一个有序的日志列表。跟踪日志非常。`XLog`实际上是一个业余日志程序，它负责跟踪日志，并将最近的联系置在列表顶部。日志保存在文本文件中，QSO（呼叫记录）以列表形式显示。

这个程序非常方便，因为它实际上允许你添加、删除甚至更新列表。

每个联系记录都显示有 DXCC 信息，其中计算了距离和方位，无论路径是长路径还是短路径。

`XLog`的安装通过你桌面操作系统的 PIXEL GUI 完成：

- 从 PIXEL GUI 打开左上角的应用程序菜单，点击“Preferences”（偏好），然后点击“Add/Remove Software”（添加/移除软件）。
- 在弹出的窗口中搜索`XLog`。
- 依次勾选两个`XLog`复选框以选中。
- 要安装`XLOG`，只需点击“Apply”（应用）按钮。

要启动`XLog`程序，点击 PIXEL GUI 左上角的应用程序菜单，选择“Applications”（应用程序），然后点击`XLog`。

## 图形收发器控制程序

控制图形火腿无线电收发器的最佳程序绝对是`Flrig`。这个程序可以作为之前提到的`Fldgi`程序的配合，但它独立运行的效果也非常出色。

`Flrig`的安装包含了桌面 PIXEL GUI：

- 选择你的 PIXEL GUI 中左上角的应用程序菜单，点击“Preferences”（偏好），然后点击“Add/Remove Software”（添加/移除软件）。
- 当窗口出现时，尝试找到`Flrig`程序，
- 点击并勾选该程序框进行选择。
- 点击“Apply”（应用）按钮安装`Flrig`。

你可以通过选择 GUI 左上角的应用程序菜单并点击`Flrig`来启动程序。

所需的硬件配置：

- 树莓派 Pi 3 Model B
- 八野（Yaesu）收发器，FT-857D
- 八野 CAT 数据线，CT-62
- USB 双串口适配器（Micro Connectors. Inc）

Pi 的端口配置：

配置与`Fldgi`程序完全相同：

- 确保树莓派 Pi 3 Model B 已开机。
- 使用带供电的 USB Hub，将 USB 双串口适配器插入树莓派的 USB 端口。
- 这是在`/dev/`目录下应该显示的内容：`dev/ttyUSB0` / `dev/ttyUSB1`
- 将八野 CT-62 线插入 FT-857D 收发器。
- 打开 FT-857D 收发器。
- 将八野 CT-62 线连接到双串口适配器的 RS-232 S1。RS-232 S1 接口为`/dev/ttyUSB0`。

### Flrig 配置：

- 选择 Config（配置）、Setup（设置），然后 Transceiver（收发器）
- 确保主标签页中：
  - Rig（设备）为 FT-857D
  - Ser.Port（串口）为`/dev/ttyUSB0`
  - Baud（波特率）为 4800
  - 勾选 PTT via CAT（通过 CAT 进行 PTT）
  - 2 StopBids（停止位）

最后，按下 Init（初始化）按钮

现在，`Flrig`程序已控制 FT-857D 收发器。

## 摩尔斯码虚拟电台

摩尔斯码由萨缪尔·摩尔斯（Samuel Morse）于1836年发明，代表了通过滴声（长音和短音）帮助发送和接收消息的方法，其中短音被称为“点”（dot），长音被称为“划”（dash）。这种方法是火腿无线电用户之间通信的方式，因此无需赘述。

确保删除底部的这几行。我们稍后会将它们还原：

```
tone_obj.play(-1)
time.sleep(2)
tone_obj.stop()
```

现在，复制下面的文本：

```
pin = 4
key = gpio.Button(pin, pull_up=True)
```

```
while True:
    reading = key.is_pressed
    print("ON" if reading else "OFF")
    time.sleep(1)
```

然后，按下 Ctrl + O 和回车键保存，当按键释放时按下 Ctrl + X 退出（注：原文0应为字母O）。

如果你也选择了上拉配置，当按键释放时它应该显示 OFF。按住几秒钟直到它显示 ON。

OFF

OFF

OFF

ON

ON

ON

OFF

OFF

OFF

按下 Ctrl + C 退出。

# 播放音调

只有当程序在我们每次按下按键时都响应并播放和停止，摩斯电码虚拟电台才能真正工作。

看以下代码：

```
tone_obj = ToneSound(frequency = 800, volume = .5)
```

```python
pin = 4
key = gpio.Button(pin, pull_up=True)
print("Ready")
while True:
    key.wait_for_press()
    tone_obj.play(-1) # -1 表示循环播放声音
    key.wait_for_release()
    tone_obj.stop()
```

要进行编辑，输入此命令：

```
nano morse-code.py
```

`ToneSound`应该位于程序的顶部，并且应该删除它之前的`while`循环。现在输入上面的代码。

要测试你的代码，输入：

```
./morse-code.py
```

你可以通过按下 Ctrl + C 退出。

# 解码摩斯码

为了能够解码摩斯电码，你需要了解点（dot）和划（dash）之间的区别。通常，一个点的持续时间约为 0.15 秒。如果它比这个时间长，那么它很可能是一个划。

这是一个简单的代码：

```python
tone_obj = ToneSound(frequency = 800, volume = .5)

pin = 4
key = gpio.Button(pin, pull_up=True)

DOT = ""
DASH = "-"

key_down_time = 0
key_down_length = 0
```

```python
print("Ready")

while True:

    key.wait_for_press()

    key_down_time = time.time() # 记录按键按下的时间

    tone_obj.play(-1) # -1 表示循环播放声音

    key.wait_for_release()

    key_down_length = key_up_time - key_down_time # 获取

    按住持续的时间

    tone_obj.stop()

    if key_down_length > 0.15:

        print(DASH)

    else:

        print(DOT)
```

要编辑，输入：

```
nano morse-code.py
```

此时你可以选择保存或退出。使用以下命令测试代码：

```
./morse-code.py
```

你的输出应该像这样：

```
.
.
-
.
.\.
```

# 将代码转换为文本

显然，重点是能够将代码翻译成文本以便通信。

这段代码将帮助你找到点和划对应的数字和字母：

```
wget https://goo.gl/aRljuj -O morse_lookup.py --no-check-certificate
```

要编辑，输入此：

`morse_code_lookup`作为一个字典对象。通过它，你实际上可以使用自己的字典并在两种语言之间翻译。

```python
english_to_french = {
    "Hello": "Bonjour",
    "Yes": "Oui",
    "No": "Non"
}

print(english_to_french["Hello"])
```

在这里，结果将是 Bonjour。

# 添加代码

再次，要编辑，输入此：

```
nano morse_lookup.py
```

现在，我们添加两个变量。第一个将记录按键释放的时间，以测量静间隙。第二个持有划和点的列表。

```python
key_up_time = 0
buffer = []
```

现在，让我们将变量添加到代码中：

```python
key_down_time = 0
key_down_length = 0
key_up_time = 0
buffer = []
```

```python
print("Ready")

while True:
    key.wait_for_press()
    key_down_time = time.time() # 记录按键按下的时间
    tone_obj.play(-1) # -1 表示循环播放声音
    key.wait_for_release()
    key_up_time = time.time() # 记录按键释放的时间
    key_down_length = key_up_time - key_down_time # 获取
    按住持续的时间
    tone_obj.stop()
    buffer.append(DASH if key_down_length > 0.15 else DOT)
```

添加 Ctrl + O 然后按回车保存。

现在，添加这些：

```python
#!/usr/bin/python3
import pygame
import time
import gpiozero as gpiozero
import _thread as thread
```

```python
from array import array
from pygame.locals import *
from morse_lookup import *
```

然后，你需要放入在完全不同的线程上运行的代码：

```python
def decoder_thread():
    global key_up_time
    global buffer
    new_word = False
    while True :
        time.sleep(.01)
        key_up_length = time.time() - key_up_time
        if len(buffer) > 0 and key_up_length >= 1.5:
            new_word = True
            bit_string = "".join(buffer)
            try_decode(bit_string)
            buffer[:]
        elif new_word and key_up_length >= 4.5:
            new_word = False
            sys.stdout.write(" ")
            sys.stdout.flush()
```

最终代码应该像这样：

```python
#!/usr/bin/python3
import pygame
import time
import gpiozero as gpio
import _thread as thread
from array import array
from pygame.locals import *
from morse_lookup import *

pygame.mixer.pre_init(44100, -16, 1, 1024)
pygame.init()
class ToneSound(pygame.mixer.Sound):
    def __init__(self, frequency, volume):
```



```python
self.frequency = frequency
pygame.mixer.Sound__init__(self, self.build_samples())
self.set_volume(volume)
```

```python
def build_samples(self):
    period = int(round(pygame.mixer.get_init()[0] / self.frequency))
    samples = array("h", [0] * period)
    amplitude = 2 ** (abs(pygame.mixer.get_init()[1])) - 1 - 1
    for time in range(period):
        if time < period / 2:
            samples[time] = amplitude
        else:
            samples[time] = -amplitude
    return samples
```

```python
def decoder_thread():
    global key_up_time
    global buffer
    new_word = False
    while True:
        time.sleep(.01)
        key_up_length = time.time() - key_up_time
        if len(buffer) > 0 and key_up_length >= 1.5:
            new_word = True
            bit_string = "".join(buffer)
            try:
                decode(bit_string)
                buffer[:]
        elif new_word and key_up_length >= 4.5:
            new_word = False
            sys.stdout.write(" ")
            sys.stdout.flush()
```

```python
tone_obj = ToneSound(frequency = 800, volume = .5)
```

```python
pin = 4
key = gpio.Button(pin, pull_up=True)
```

```python
DOT = ""
DASH = "-"
```

```python
key_down_time = 0
key_down_length = 0
key_up_time = 0
buffer = []

thread.start_new_thread(decoder_thread, ())

print("Ready")

while True:
    key.wait_for_press()
    key_down_time = time.time() # 记录按键按下的时间
    tone_obj.play(-1) # -1 表示循环播放声音
    key.wait_for_release()
    key_up_time = time.time() # 记录按键释放的时间
    key_down_length = key_up_time - key_down_time # 获取
    按住持续的时间
    tone_obj.stop()
    buffer.append(DASH if key_down_length > 0.15 else DOT)
```

# 结论

你还在什么？这是一个非常廉价且真正有趣的爱好，可以在享受乐趣的同时向任何人介绍软件科学。开启你自己的业余无线电台，让我们从高频探索世界。

感谢阅读本书，祝你在无线电中玩得开心！

你觉得这本书对你有帮助吗？请留下评价并让其他人知道。你的反馈我们将不胜感激。

![](img/2cb396b278b4689ca2ae10896df42604_62_0.png)

你的知识与文化之门。所有人可用。

z-library.sk z-lib.gs z-lib.fm go-to-library.sk

官方 Telegram 频道

Z-Access

https://wikipedia.org/wiki/Z-Library
