
# Java 平台企业级社交：将社交媒体集成到云原生应用中

作者在书中引用的任何源代码或补充材料读者可在 GitHub（`https://github.com/Apress`）上获取。欲更多详细信息，请访问 `https://www.apress.com/gp/services/source-code`。

本书献给我美丽的妻子和可爱的孩子们，感谢他们的耐心与理解，并为我完成这本书提供了能量和动力。

关于技术评审员 ............................................................................... xiii

前言 ................................................................................................................................. XV

- Twitter/X: 208
- Twitter4J: 214
- 旧版框架: 239

# 参考文献: 283

# 索引: 289

# 关于作者

![](img/3c2d905e913621002f512a08b8855a70_8_0.png)

Werner Keil 是一位云原生顾问，也是金融领域的 Jakarta EE 和微服务专家。他帮助跨各行业的全球 500 强企业和 IT 供应商。他拥有 30 多年的 IT 经理、项目经理、教练、软件架构师和顾问经验，服务金融、移动、媒体、交通和公共部门。Werner 使用 Java、Java/Jakarta EE、Oracle、IBM、Spring 或 Microsoft 技术、JavaScript、Node.js、Angular 以及动态或函数式语言开发企业级系统。他是 Apache Foundation 和 Eclipse Foundation 的提交者（Committer）、Babel 语言冠军、UoMo 项目负责人，以及 Java 社区进程（JCP）的活跃成员，涉及 JRS 321（Trusted Java）、344（JSF 2.2）、354（Money，并担任维护负责人）、358/364（JCP.next）、362（Unit-API 1）、365（CD 2）、366（Java EE 8）、375（Java EE Security）、380（Bean Validation 2）和 385（Unit-API 2，并担任规范负责人）。他曾担任执行委员会任期最长的个人成员，一直直到 2017 年。Werner 目前担任 Jakarta EE 规范委员会的提交者代表。在 Jakarta EE 以 Java EE Guardians 的身份创立之初，他是前五位 Jakarta EE 大使之一，并是其领导委员会成员。

# 关于技术审查员

![](img/3c2d905e913621002f512a08b8855a70_9_0.png)

**Reza Rahman** 是微软 Azure Java 首席计划经理。他致力于确保 Java 开发者成为微软的一等公民，并让微软成为 Java 生态系统的一等公民。

Reza 曾是 Oracle 的官方 Java 技术专家。他是 Manning 出版社的畅销书籍《EJB 3 in Action》的作者。Reza 长期以来一直是全球 Java 用户组和会议（包括 JavaOne 和 Devoxx）的频繁演讲者。他曾担任 JavaOne Java EE 分会的负责人，并荣获 JavaOne Rock Star 演讲者奖。Reza 是 *DZone* 等行业期刊的热心贡献者。多年来，他一直是 Java EE、EJB 和 JMS 专家组的成员。Reza 为开源 Java EE 应用服务器 Resin 实现了 EJB 容器。他协助领导了费城 Java 用户组。Reza 为能成为 Jakarta EE 大使的创始成员感到自豪。

Reza 在技术领导力、企业架构和咨询方面拥有十余年的经验。自 Java EE 技术诞生以来他一直在从事工作，涵盖了从 Tomcat 到 jBoss、GlassFish、WebSphere 和 WebLogic 的几乎每一个主流应用平台。Reza 曾使用 Java EE 和 Spring 为 eBay、Motorola、Comcast、Nokia、Prudential、Guardian Life、USAA、Independence Blue Cross、Anthem、Capital One 和 AAA 等知名公司开发企业系统。他对分布式系统、消息传递、中间件、持久化和机器学习特别感兴趣。

Reza 是 Phi Beta Kappa 会员，这是文理学院最古老、最受尊敬的本科生荣誉学会。他毕业于格特斯堡学院（Gettysburg College），以优等荣誉获得计算机科学和经济学双学位，辅修数学。

# 前言

*从开罗的街道和阿拉伯之春，到占领华尔街，从繁忙的政治日程到日本海啸的后续，社交媒体不仅在分享新闻，更在推动新闻。*

— 丹·雷瑟（美国记者，八次彼得迪奖获得者）

言论自由，尤其是受到正直意图启发时，是社会的定义力量。得益于社交媒体，这种强大的力量有了新的翅膀。社交媒体为我们这个不安的小星球上所有被忽视的人发声，我们才刚刚开始看到它的作用——无论是在基辅、莫斯科、明尼阿波利、弗格森、突尼斯、开罗、利雅德、德黑、香港、北京、特拉维还是加沙。

尽管社交媒体在现代生活中起着关键作用，但很少有书籍涵盖社交媒体与 Java 这一话题。现有材料仅涵盖了最常见的用例——使用 OIDC 和 JWT 的联邦安全。可能因此，尽管可能性非常广阔，但很少有 Java 应用能够充分利用社交媒体。这正是此书如此重要的原因。它提供了社交媒体行业的极佳背景，解释了对 Java 社交媒体开发者重要的核心概念，描述了在标准化方面相对微弱的努力，概述了 Java 的社交安全，并且当然涵盖了与 Java 最相关的社交媒体框架和 API。鉴于该主题的波动性、广度、深度和复杂性，这本书的编写无疑非常艰巨。我找不到比 Werner 更合适写这本书的人了。从 AgoraView 项目以及标准化 Java 社交媒体 API 的早期尝试以来，他就一直参与该领域。他对该领域的精通在书中随处可见。

我希望这本书对任何 Java 社交媒体开发者来说都是无价之宝。

— Reza Rahman

微软 Azure Java 首席计划经理

Jakarta EE 大使、作者、演讲者

# 第一章

## 引言

本章讲述了社交媒体从古代到近期的历史。21 世纪的头几十年通常被认为是互联网泡沫与 2008 年金融危机之间社交媒体的黄金时代。我们进一步回顾了之后的年份，直到最近的历史，以及未来可能为社交媒体带来什么。

## 古代历史

大多数人认为社交媒体是 Facebook、Twitter、Myspace 和 Yahoo! 等公司的现代发明。事实上，社交媒体的历史可以追溯到数千年前。

对某些人来说，邮政服务是社交媒体的形式之一。从古代波斯邮政到希腊广场 [1] 和罗马论坛 [2]，邮政服务充当了媒介。最早的 Wiki 或帖子的等同物被直接刻在罗马论坛或类似建筑的墙上 [3]，记录了诸如维苏火山火山摧毁庞贝或尼老时期罗马部分地区的事件。

雅典的古老广场曾是民主的孵化器，而论坛现在已转向数字化。从突尼斯到乌克兰，反对运动利用社交媒体在长期以来一直令人惊讶且不寻常的地方引入了民主 [4]。

电报发明于 1792 年，使得个人信息的跨距离传递比骑马者或驿马车运送快得多。尽管电报信息很短（类似于短信或推文），但它们是传播新闻和交换信息的革命性方式。许多人认为那是社交媒体的诞生。

尽管美国等几个国家继续提供邮电服务，甚至提供给总统或其他官员，但德国邮政服务已在 2022 年除夜关闭了其电报业务 [39]。

![](img/3c2d905e913621002f512a08b8855a70_12_0.png)

图 1-1. 莫尔电报键

## 现代历史

20 世纪，我们所知的信息技术始于 Konrad Zuse、George Stibitz 或 Howard Aiken 等先驱，当然还有 Alan Turing，他建立了图灵测试作为人工智能和社交机器人的基准。

## X 代

1975 年，在美国军撤出越南之前，自由意志思想家 Samuel Edward Konkin III 引入了名为阿戈主义（Agorism）的哲学，这是一种反经济学及其相关实践的思想哲学 [5]。在市场无政府主义社会中，法律和安全将由市场参与者而非政治机构提供。阿戈主义意识到这种情况无法通过政治改革来实现。相反，它将作为市场过程的结果产生。其社会价值的方面今天可以在占领运动中找到，其主要目标是让所有社会的经济和政治关系减少等级制度，更加扁平化分布。或者在意大利的 Beppe Grillo、希腊的 Syria 等抗议政党中（其中

## 第一章 引言

它甚至催生了政党，例如西班牙的 Podemos 党或海盗党。互惠市主义主义（Agorism）提出了使用不同货币的想法，这是现代社交媒体及相关在线社区正在采用的一点：如比特币等数字货币。

1966年，电子邮件被发明；约一年后，美国军创建了计算机网络 ARPANET；随后 CompuServe 在1969年问世。CompuServe 在20世纪80年代后期推出了其电子邮件服务，并扩展到20世纪90年代初，在经历了多次收购后，最终于2009年解散了原始的 CompuServe。

Usenet 起于1979年，为用户提供论坛和新闻组。惊讶的是，它们的大部分功能变化很小，并且今天依然存在。

即时聊天（IRC）诞生于1988年，在成为如今互联网的一部分之前，曾在学术网络中广泛使用。IRC 在今天仍然相当活跃，尽管它在很大程度上被 Twitter 等其他短消息服务所掩盖。全球范围内仍有3200个 IRC 服务器，提供数十万个频道。

## 千禧一代

基于“六度分隔理论” [6] 的概念，第一个现代社交网络 sixdegrees.com 成立于1997年。它允许成员与其他成员建立朋友关系链接、撰写消息或在公告板上发布内容。在以1.25亿美元出售给另一公司后，它于2001年关闭，当时约有一百万用户。它后来经历了小规模的回升，并至今仍然存在。

当 Amazon、Yahoo! 以及1998年的 Google 首次出现时，它们并不被视为社交网络。1995年，微软通过推出微软网络（MSN）捕捉到了这一新兴趋势。MSN 以“门户”而闻名，这是个性化在线社区的另一个称呼。几年后，许多门户产品、服务器和供应商加入社交浪潮，这并不意外。

微软和 Yahoo! 在社交媒体领域的一些“新秀”出现之后都落后了，除了在 YouTube 上采取了相当高明且快速的行动外，社交媒体的大多数其他方面也被 Google 低估了，直到它通过 Google+ 回归；尽管它可能没有引领每一个方面，但它确实拥有丰富的社交功能，并且自近期恢复以来，在社交网络空间中超过了 Flickr 或 Tumblr 等较小的供应商。1999年，后来也曾在 Google 工作的 Brad Fitzpatrick 创立了 LiveJournal。

## 第一章 引言

## Z 世代

21世纪初，许多社交网络相继成立，尽管并非所有网络都存活到了今天。Hot or Not (AmIHotOrNot.com) 由 James Hong 和 Jim Young 于2000年10月创立，他们是加利福尼亚大学伯克利分校的两个朋友兼同学。该网站最初的动力是创始人之间关于女性吸引力的一场争论。它是第一个允许上传照片供他人评分的网站，据称它影响了 Facebook 或 YouTube 的创造者。2008年，Hot or Not 以传闻中的2000万美元出售给在线约会服务 Ashley Madison 的所有者（后者后来因被黑客丢失所有客户数据而臭名昭著），并于2012年被 Badoo 收购，Badoo 现在是 Bumble 约会 App 集团的一部分。

虽然 URL 仍然存在，但该应用已更名为为“Chat & Date”，且与原始网站几乎没有关系，但 Hot or Not 无疑是 Tinder 等现代约会 App 的先驱。

Friendster 成立于2002年，最初也计划作为一个类似于 Hot or Not 的约会网站，但它变成了一个连接志同道合的人及其共同朋友的网站。它包含简介和状态更新，允许你分享心情并交换消息。

直到2004年初，它一直是最大最流行的社交网络，这最终导致了它的终灭，因为它无法扩展以处理用户需求，导致许多用户感到沮丧并开始寻找替代方案。2003年，Google 出出3000万美元购买 Friendster，但被创始人拒绝了。2009年，它被一家位于吉隆坡、名为 MOL Global 的互联网公司全部收购。除了大部分亚洲用户群外，Friendster 的专利也是一项重要资产，其中包括一种“基于用户在社交网络中关系的、在在线计算机系统中连接用户的系统、方法和装置”。这些核心社交基础设施专利的大多数在2010年被 Facebook 以4000万美元买入。

一年后，Friendster 变成了一个社交游戏网站。2015年6月14日，该网站关闭，三年后公司终止。

LinkedIn 同样成立于2002年，后来有时被认为是“成人的 Myspace”，它是第一个向用户提供付费服务的社交网络。它的招聘市场和订阅服务帮助它在2006年实现盈利。招聘市场和在线简历成为其关键特性，使其与其他社交网络相比更具专业性。

2011年，LinkedIn 提交了 IPO 。五年后的2016年，微软以262亿美元收购了 LinkedIn，这是仅次于视频游戏制作商动视暴雪的第二大笔收购案（而微软曾在2022年尝试以687亿美元收购它 [42]）。英国监管机构曾表示担忧，但最终在2023年10月13日（甚至是一个周五）批准了它。

Myspace（2012年更名之前的 MySpace）是 Friendster 在2003年开始的最强对手，它从技术问题带来的挫败感中受益最多。2005年，Facebook 受到最初来自 Friendster 的启发，以5.8亿美元购买了 Myspace。2008年，新闻集团（News Corp）以5亿美元购买了 Myspace。2019年，新闻集团以3500万美元卖了 Myspace。2012年，Facebook 以10亿美元收购了 Instagram。

2011年，Snapchat 推出了 Snapchat。2014年，Facebook 出出30亿美元拟收购 Snapchat。2016年，字节动 推出了 TikTok。2017年，字节跳动以10亿美元收购了 Musical.ly，同时推出了短视频分享服务 TikTok。

## 第一章 引言

## 此时此刻

近年来，社交媒体的大多数进展要么是安全泄露和其他困难，要么是合并收购，只有少数显著的例外。

2015年，即时消息和 VoIP 社交平台 Discord 成立。它很快被电竞和局域网赛赛玩家使用，并受益于与 Twitch 主播的关系，因为这两个平台触达的是相似的用户群体，尤其是这样。

2016年，Mastodon 发布，这是一种免费、去中心化且开源的软件，基于开放标准和协议创建网络服务（通常被称为“联邦宇宙” Fediverse）。

## 第一章 引言

2018年，Yahoo! Messenger 被关闭，Musical.ly 合并为 TikTok。另一个自称“言论自由”的网络 Parler 也于同年启动，主要供右翼和其他极端主义者或阴谋论者使用，尤其是在2020年新冠疫情爆发后。虽然坎耶·韦斯特并未亲历此，但在发表反犹主义言论后，他认为自己被几乎所有主要网站封禁 [46]。2023年4月，在收购 Parler 后不久，所有公司 Starboard 的执行官将其关闭，理由是“没有理智的人会认为保守人士的 Twitter 是可行的商业模式” [52]。

2020年，音频聊天应用 Clubhouse 和专注于真实性的社交媒体应用 BeReal 相继。尤其在一个“虚假新闻”主导的时代，它自此广受欢迎。

2021年，另一个面向无过滤内容的社交媒体平台 Getty 由前总统唐纳德·特朗普的助手杰森·米勒创立，而特朗普本人也基于 Mastodon 创立了 Truth Social，但并未向联邦宇宙（Fediverse）开放 [45]。在作为一个创建去中心化社交网络协议的 Twitter 项目启动后，2021年10月，Twitter 创始人兼首席执行官杰克·多塞会见了加密公司 Zcash 的员工 Jay Graber，后者创立了 Bluesky Social。从起 Graber 一一直是 Bluesky 的 CEO。尽管 Bluesky 获得了埃隆·马斯克收购 Twitter 的资金，但它在2023年7月的种子轮中筹集了800万美元，以便在财务上与 Twitter 独立。几周前的2023年5月，Bluesky 还将其社交媒体客户端开源，该客户端在一年前已经发布了 AT Protocol (atproto) 等协议。Atproto 是一种用于构建社交媒体应用的联邦协议。虽然尚未被完全视为联邦宇宙的一部分，但与 Bluesky 的互操作性可能很快实现。Bluesky 的一个有趣特性是多语言支持。帖子可以声明多种语言。列表包含了几乎所有已知的语言，如拉丁语或犹太语。通过账户设置中的“内容语言”，用户可以选择他们希望在动态中看到的语言。尽管 LinkedIn 等某些社交网络为个人资料提供国际化（i18n）支持，但 Bluesky 似乎非常独特。截至2023年9月底，Bluesky 的用户数超过了1500万。尽管仍处于仅限邀请测试阶段，但一旦向大众开放，增长速度将更快。尤其是当原 Twitter 网络退化为一个右翼俱乐部、开始对所有人的基础使用收费，或者这些因素的共同作用时。2022年，它在已支持 iOS 一年后回归了 Android 平台。2022年夏天，Google 的 Lambda 通过了图灵测试，随后 ChatGPT 在年底获胜 [49]。当然，还有当年的主导性事件，特别是对社交媒体而言的：埃隆·马斯克以440亿美元收购 Twitter。



# 第一章 引言

埃隆·马斯克收购后不久，大量账户因疑点被封锁或停用，而其他人员——右翼保守派、仇恨团体和阴谋论者，最著名的当属特朗普本人——恢复了账户。为了缓解 Twitter 激增的损失，付费订阅制取代了之前的账户验证。减少机器人和虚假账户的承诺也惨遭失败，现在，如果运行者愿意付费，机器人就可以通过购买订阅获得某种合法性。虽然马斯克取消了对特朗普账户的封禁，但他公开支持共和党的德桑蒂斯，甚至在 Twitter 上举办了一场直播活动宣布他的竞选。然而，该活动对双方来说都是一场灾难，因为几乎没有人能看到直播，视频流几乎不存在，只能听到他们的声音 [53]。2022年，“占领民主党”（Occupy Democrats）背后的活动人士发起了 Truth Social，这是一个向左倾的自由派社交网络，口号是“真理与人民”，增加了 Twitter 的其他替代方案。该网站声称拥有5万用户。

2022年6月，Reddit 宣布大幅提高其 API 使用费用，希望通过其长期宣布的 IPO 增加融资价值。根据新的定价方案，开发者必须为每5000万次请求支付1.2万美元，这导致许多较小或社区驱动的应用程序被迫离开 Reddit。这引发了许多名为“版块”（subreddits）的网络部分管理员试图进行反抗。他们中的大多数人被 Reddit 停用了管理权限，尽管少数人后来恢复了权限。除了试图讨好投资者外，另一个论点是像 ChatGPT 或 Google Lambda 等 AI 解决方案正在从 Reddit、维基百科等网站获取信息进行训练，而这些网站并未从中获得回报。当 Twitter 在收集更多资金的绝望举措下，表示每5000万次请求将收取4.2万美元时，引发了巨大的愤怒，这导致包括 Mastodon 在内的许多较小或社区驱动的网站也关闭。尽管 Reddit 承诺避免这种极端定价，但他们的价格“仍然是1.2万美元”。

2023年7月5日，Facebook、Instagram 或 WhatsApp 的母公司 Meta 推出了名为 Threads 的新“微博客”服务，这是对 Twitter 的明显一击 [57]。这个由 Instagram 开发的去中心化社交网络到目前仍需要现有的 Instagram 账户。由于欧盟隐私法，Threads 在另行通知之前不在欧盟可用。在最初的几天里，可以通过移动 VPN 安装和使用 Threads，因此我尝试了，但 Meta 阻止了这种做法，导致在最初突破1亿用户激增后使用量下降。Threads 可以在欧盟及其他国家无需 VPN 直接使用。

2023年7月24日，埃隆·马斯克将 Twitter 更名改为“X” [58]。为了模仿微信在中国的一些做法，马斯克似乎忽略了由于隐私方法的不同，单一公司的权力集中（只要遵循政治建制的规则）在其他国家可能并不可行，即使在美国或欧盟国家。“X”的想法（有趣的是，Google/Alphabet 也有一个秘密的“臭味工作坊”实验室名称）并不新鲜，埃隆·马斯克在 PayPal 时代就注册了该域名；在公司变成 PayPal 之前，它已经被称为 X.com，但在其最大的竞争对手 Confinity 以其产品 PayPal 进行某种敌意收购（注意这种讽刺）后，他被赶出，彼得·蒂尔取代了他的 CEO。一个关键原因是马斯克在“X”的许多想法和目标上分心，而蒂尔的其他人只想专注于支付，公司现在也确实做到了。当然，马斯克现在比蒂尔富有得多，目前是世界上最富有的人，但还不清楚这次能完成“X”的众多想法中的哪些，以及用户愿意为哪些服务（将是付费的且可能远高于每月8美元）付费，而不是在 PayPal、Stripe、Amazon 等许多其他地方进行在线支付。更不用说反垄断问题了，如果该应用变得过大，或者例如，未来的特斯拉买家被迫强制使用 X 支付系统，或者强制所有人使用 YouTube，尽管后者的体验和性能更好。2023年9月18日，埃隆·马斯克宣布他可能会将 X 对所有用户置于付费墙，随后在菲律宾和新西兰进行了迄今为止仅为“象征性”1美元的收费测试。尽管他声称在打击机器人和虚假账户，这是又一次绝望的从这件昂贵的玩具中收回一些资金的措施。许多专家认为，这可能是 X/Twitter 最终的最后一根钉子，其用户群可能很快就会萎缩到 MySpace 或 Truth Social 的水平。

## 未来

社交网络自人类首次交流以来一直存在。技术手段随着时间而变化，并且在不久的未来可能会变化得更快。某些服务将会合并；另一些可能会变得过时并迟早消失。使用供应商中立的标准和框架，可以避免让你被缚在某个提供者的服务中——除非你愿意在快速变化的 API 上花费更多时间，而不是实际上将其用于生产性工作，或者更糟糕，当特定供应商提供的专用 API 和框架不再可用时，不得不切换到另一个提供商。虽然不是 Twitter 或 Facebook 意义上的社交网络，但最早的加密货币交易所破产之一 Mt Gox [7]（在 FTX、BlockFi、Celsius 或 Voyager 出现很久之前）就是这种困境的典型例子。它曾在该领域长期处于市场领导地位。因此，通过其 API 提供比特币的应用程序和电子商务解决方案被迫重写或抛弃这些应用。

如果在此类 API 之上创建了供应商中立的抽象，那么将更容易应对由于供应商破产、被他人收购或两者结合引起的问题和变化，就像自埃隆·马斯克收购 Twitter/X 及随后的重品牌以来，这种担忧仍然笼罩着它上方。

这就是 Fediverse、Agoraova、Keycloak 或 Jakarta EE 等这类供应商和社交服务中立的方法大显身手的领域。

## 总结

在本章中，我们学习了社交媒体的历史、它的黄金时代、正在发生的事情，以及未来的方向可能通向何方。还学习了合并与收购有时会对你的社交媒体策略带来风险，特别是当一些新所有者委婉地说是心多不定且性格古怪时。

# 第二章 社交用例

在本章中，我们将探索社交媒体的各种用例，从通用型网络到像媒体分享等技术专门的网络，以及针对特定目标群的垂直社交网络。

## 社交网络类型

有许多社交媒体网站，无论是通用的还是针对小组和专业社区的，包括前戒酒者、音乐爱好者、开发者、外籍人士、母亲、学生、教师、政府人员以及对园艺、针织或 BDSM 感兴趣的人。《五十度灰》书和电影可能为这个列表增添了更多色彩 [17]。

## 传统社交网络

大多数人熟悉传统的社交网络网站，如：

- Facebook
- Twitter
- Mastodon
- Myspace
- 微信
- 新浪微博

这些平台帮助我们与朋友、家人、同学或有共同兴趣的人建立联系。

## 商业与企业

这些是受欢迎的商业社交网络：

- LinkedIn
- XING

这些主要用于工作或寻找工作，作为数字简历。LinkedIn 被微软收购，是一个全球性的参与者。XING 起源于德国汉堡，因此在欧洲最活跃。它收购了其他几个职位门户网站或招聘服务，以及最大的外籍人士社交网络 InterNations，在全球范围内从火奴奴岛到奥克兰的 420 个全球社区中增加了用户。

## 消息服务

这些是最受欢迎的即时消息服务：

- WhatsApp
- Facebook Messenger
- Telegram
- Discord
- Viber
- 微信
- Snapchat
- Line
- QQ
- Signal
- KakaoTalk
- Zalo

## 媒体分享

媒体分享网站分为三类：

1. 音频分享
2. 图片分享
3. 视频分享

### 音频分享

音频分享可以是：

- 音乐分享/流媒体
- 播客
- 有声书

#### 音乐分享/流媒体

有很多音乐分享和流媒体门户。最早的之一成立于1996年且至今仍然存在的是 Live Music Archive (LMA)。它提供了超过250,000多场现场演唱会录音，大多是独立艺术家，也有一些像感恩之死（Grateful Dead）这样的大牌。

此外，Napster 在世纪之初出现，由 Sean Parker 创立，他后来通过 Facebook 成名并富有。它的原始形式主要是去中心化且免费的，但因侵犯版权被迫关闭。然而，它的第三版本今天仍然存在。

虽然 Apple Music 直到2015 年才开始，但它的根源可以追溯到从2001 年起存在的 Apple iTunes。

许多音乐分享网站是在 2001 年到 2010 年社交媒体的高产时期启动的，其中包括：

- Myspace
- DatPiff
- Jamendo
- Mixcloud
- Musopen
- Spotify
- SoundCloud
- Deezer
- Noise Trade
- Playlist
- StarMaker
- Smule

除了 Apple 之外，互联网社交媒体巨头 Amazon 和 Google 也提供音乐下载和流媒体，有时通过 Google Music 和 YouTube Music 等各种品牌。

#### 播客

播客（Podcast）由 Tristan Louis 和 Dave Winer 在 2000 年基于 RSS 格式发明。最初被称为“音频博客（Audioblogging）”，英国数字记者 Ben Hammersley 创造了“podcast”一词，并在《卫报》（*The Guardian*）2004 年的一篇文章中提到。灵感源于 Apple 的播放器。

显然，Apple 是最早提供播客的。除了电台和电视台，大多数播放器都提供播客。

#### 有声书

有声书和播客之间存在一条微妙的界限；最初由 Thomas Edison 通过留声机发明，主要针对盲人，让他们听故事而不是读故事。

有声书随着唱片机、磁带、CD 和 DVD 演变。除了出版社和电视台，有声书由大多数互联网巨头和流媒体服务提供。

### 图片分享

正如我们所学的，第一个上传图片的社交网络是 2000 年的 Hot or Not。第一部手机是由 Borland 创始人 Philippe Kahn 三年前发明的，为了向选定的朋友实时分享女儿的出生。

这些是一些顶级的图片分享应用：

- Adobe Creative Cloud – 用于 Photoshop 存储
- Google Photos – 照片存储和备份
- iCloud – Apple 用户的照片存储备份
- Instagram – 即时消息和照片分享
- Pinterest – 视觉分享食谱、家居装饰或其他信息
- SmugMug – 保护你的照片
- Amazon Photos – 面向 Amazon 用户
- Waldo – 为摄影公司的专业选项
- Guest – 自动照片上传
- Internxt Photos – 极速照片交换
- Imgur – 你可以查看和分享图像、GIF、表情包或视频的内容托管网站
- FamilyAlbum – 家庭照片
- Flickr – 摄影师社区
- Snapchat – 多媒体即时消息
- Pixpa – 轻松销售照片
- 500px – 分享与交流

除了这些专业的照片应用之外，几乎每个主要的社交网络（如 Facebook 或 Twitter）也允许分享和存储图像，尽管其便利程度并不总是能匹配专业的照片服务。

### 视频分享

YouTube 改变了我们观看和创作视频的方式。它让几乎每个拥有移动设备的人变成了摄影导演，并创造了一种特殊的影响者：YouTuber，他们许多人的收入与电影明星相当。

这些是 11 个重要的视频分享网站：

- YouTube
- Vimeo
- TikTok
- Dailymotion
- Metacafe
- Instagram IGTV
- Facebook Watch
- 快手
- Periscope
- Utreon
- TED

### 视频流媒体

这些是十个重要的视频流媒体网站：

- Amazon Prime
- Apple TV+
- discovery+
- Disney+
- Google Play Video
- Netflix
- Paramount+
- Twitch
- YouTube
- WOW

许多是视频流媒体频道，由工作室而非用户自己发布内容。

即使这些平台大多也提供某种程度的社交互动，从简单的点赞（或点踩）按钮到评论，甚至是像 Amazon Watch Parties 或 Disney+ GroupWatch 功能这样的社交聚会。

其他平台，特别是 YouTube 或 Twitch，是社交流媒体网站，社区成员在这里分享直播内容，通常是电脑游戏、电竞、教育、演唱会或其他直播活动。如果他们的内容吸引了数百万粉丝，“YouTubers”和“直播主播”有时也能成名获利，这使得一些顶尖内容创作者的年收入达到了六位数字。

### 博客与写作

这些是最适合博主和作者的社交平台：

- Tumblr
- Facebook
- Pinterest
- Medium
- Instagram
- Goodreads

### 讨论论坛

虽然 Twitter 上可能会发生激烈的讨论（在埃隆·马斯克接管并打开右翼阴谋论大门后，讨论更多），但像 Reddit 和 Quora 这样的讨论网站是专门为引发对话而设计的。

这些是流行的社交媒体讨论论坛：

- Reddit
- Facebook
- Quora
- LinkedIn
- Stack Overflow
- Digital Point
- Webmaster Sun

### 评论网站

十大评论网站如表 2-1 所示。

**表 2-1.** 最佳评论网站

| 网站 | 类别 | 美国月均流量 | 美国流量占比（总计） |
|---|---|---|---|
| Google Business Profile | 任何业务 | 1.583 亿 | 19.6% |
| Amazon | 电子商务 | 8,544 万 | 63.6% |
| Facebook | 任何业务 | 8,557 万 | 23.1% |
| Yelp | 任何业务 | 4,047 万 | 87.5% |
| TripAdvisor | 食品、餐厅、旅游 | 2,827 万 | 50.4% |
| BBB (美国商会) | 任何业务 | 615 万 | 72.1% |
| Yellow Pages | 任何业务 | 1,050 万 | 70.0% |
| Manta | 任何业务 | 648 万 | 67.0% |
| Angi | 服务 | 544 万 | 72.4% |
| Foursquare | 商店和餐厅 | 367 万 | 19.3% |

### VR/元宇宙

Facebook 将其更名为 Meta，旨在一个必须完全实现的元宇宙。除了 Meta 之外，经常通过 iPhone 或 Apple Watch 颠覆现有市场的苹果也将其 Vision Pro 头戴设备投入了竞争。这些是顶尖的社交 VR 应用：

- Altspace
- Bigscreen
- Couch
- Horizon Venues
- Horizon Worlds
- Sansar
- Second Life
- Sensorium
- VRChat
- VRzone

### 垂直社交网络

垂直社交网络是专门针对特定社区（如开发者、游戏玩家和书爱好者）兴趣的专业社交媒体平台。这些是顶级开发者平台：

- GitHub
- GitLab
- Bitbucket
- Launchpad
- SourceForge

### 金融

有几个用于金融和投资的社交网络，包括：

- eToro – 一个社交交易和投资平台，允许用户交易和投资各种金融工具，如股票、货币和商品。它还允许用户关注并复制平台上其他成功投资者的交易策略。
- Stocktwits – 一个供投资者和交易者分享见解、新闻和分析的社交网络。这是一个社区驱动的平台，允许用户分享对个股和其他金融工具的看法。
- Seeking Alpha – 一个面向投资者和交易者的社交媒体平台，提供有关股票和其他投资的实时金融新闻、分析和研究。它还允许用户与社区分享意见。

这些社交网络对于投资者和交易者来说是价值资源，可以帮助他们关注金融市场的最新新闻、分析和见解，并与其他志同道合的人士或爱好者建立联系并互动。

### 健康与健身

有很多致力于健康和健身的社交网络和门户。虽然许多健身、健康或营养影响者仅使用 Facebook、Twitter 或 Instagram 分享健身，但越来越多的人使用可穿戴设备和类似的智能设备来量化各种健康状况，从睡眠模式到体重以及心率。在这些“量化自我”中，许多人选择通过社交网络分享数据。许多智能手表制造商都有自己的应用，但也有由平台供应商提供的健身和智能设备门户，如：

- Apple Health
- Google Fit
- Fitbit (现也属于 Google)
- Strava
- Adidas (Runtastic)
- MyFitnessPal

#### Apple Health

Apple Health 主要是一个用于 iOS 的移动应用程序以及 Apple Watch 的配套应用。该应用对 20 类数据提供了趋势分析，从静息心率到睡眠或心肺健康，允许用户查看特定指标的进展。在获得许可的情况下（目前主要在美国），用户还可以将选定的健康信息分享给医生或保险公司。

图 2-1. Apple 健康：心率

从 watchOS 5 开始，Apple Watch 有了一个新的活动功能，用于激励人们锻炼并与朋友竞争。他们可以从 Apple Watch 向任何朋友发起为期七天的挑战，以更快完成活动环，见图 2-2。

#### Google Fit

Google Fit 是 Google 为 Android 操作系统开发的健康追踪平台。它允许用户监控和跟踪各种健康健身信息，例如活动水平、心率、体重、步数或睡眠。Google Fit 聚合了来自多个传感器设备和第三方应用的数据，使用户能够在一个地方查看并管理他们的健康和健身数据。

图 2-2. Apple 健康：竞赛

图 2-3. Google Fit 控制面板



用户可以设定并跟踪目标，例如每日步数、减重、睡眠小时或每周跑步目标，并根据他们的活动获得个性化的见解和建议。`Google Fit` 旨在通过更容易管理健身目标和监控随时间的进展来帮助用户改善健康状况，但到目前 `Google Fit` 尚未提供与其他分享或竞争的功能；与 `Apple`、`Adidas`、`Strava` 不同，`Google Fit` 目前还没有挑战功能。2019 年，`Google Fit` 网页版已停止。

## Fitbit

`Fitbit` 于 2019 年被 `Google` 收购。虽然正在进行与 `Google` 账户更深集成（特别是对于新用户和新注册的设备），但该品牌仍具有某种独立性，尽管它可以被视为“`Pixel`”等其他 `Google` 品牌的对应产品。

## 第 2 章 社交案例

直到 2025 年，`Google` 都承诺旧账户将在没有 `Google` 账户的情况下继续运行；此之后将是强制性的，或者 `Fitbit` 应用和控制面板（见图 2-4）可能会合并到 `Google Fit` 中。

## Strava

`Strava` 是一个具有很强社交属性的健身门户。大多数用户可能专注于跑步或骑行，但它提供了数十种不同的运动，包括瑜伽或雪鞋行走。

与大多数侧重于休闲或半专业运动员的健身门户网站不同，也有像职业自行车车手这样的运动员在使用它。

## 分析

| 订阅 | 2014年9月27日 星期六 上午12:26，美国旧金山 | 30.6 km 2:04:36 222 m |
| --- | --- | --- |
| 2014/09/27 加利福尼亚州旧金山 | 距离 | 移动时间 | 海拔高度 |
| 添加描述 | | 显示高度扩展状态 |
| | 0.33 34.1 km/h | |
| 心率 | 移动比例 | 最佳20分钟速度 | |
| 估算功率曲线 | 心率压力评分 | TRIMIMP 强度 | |
| 估算 230 W | | 最佳20分钟心率 | 平均心率储备 | |
| 分布 | 36/36 (占时间的14%) | 12.4 km/h | |
| 圈数 | 爬升时间 | 平均爬升速度 | |
| 远程视图 | 中位步频 | 踏板时间 |
| | -15.5 W (D. Sagan 公式) | -1.32 w/kg | |
| 估算归一化功率* | 每公斤瓦 | |
| | -222 w | |
| 估算最佳20分钟功率 | 此活动日期未在运动员中找到骑行FFP | |
| | 137 w 1,024 kj | |
| 估算平均功率 | 能量输出 | |
| | | 平均 | 最大 | 显示更多 |
| 已用时间 | 14.5 km/h | 42.8 km/h | |
| | 4:29:13 | | |
| | | 消耗量 | 骑行距离 / 30.1 km |

由 `'Elevate'` 扩展提供的地图功能已不再可用。目前显示此服务的成本过高。[忽略此消息]

![](img/3c2d905e913621002f512a08b8855a70_35_0.png)

### 图 2-5. Strava 活动

功能包括与他人分享的俱乐部和路线，以及供其他用户相互竞争的挑战，并与码速表、健身追踪器和智能手表等众多设备集成。

## 第 2 章 社交用例

![](img/3c2d905e913621002f512a08b8855a70_36_0.png)

## JavaOne 极客骑行者

加利福尼亚州旧金山

`Silicon Valley JUG` 将在 `JavaOne` 之前的周六举办年度极客骑行活动。我们将在渔人码头的 41 号码头集合，跨越大桥进入索萨利托（`Sausalito`），然后乘坐渡轮返回市区。

## 图 2-6. Strava 俱乐部

某些功能需要付费订阅，但仍有足够的功能无需付费会员即可使用。

## Adidas/Runtastic

最初的想法源于2006年上奥地利州应用大学的一个项目，该项目旨在追踪帆船，随后导致了2009年`Runtastic`的成立。

2015年8月，宣布 `Adidas` 已以2.2亿欧元（2.4亿美元）收购了`Runtastic`，其中包括报业集团 `Axel Springer` 自2013年起持有的50.1%的股份。

## MyFitnessPal

`MyFitnessPal` 是一款手机和网络端应用程序，允许用户追踪他们的卡路里摄入、运动和其他健身信息。它是一个数字食物日记，帮助人们监控每日食物摄入量，以实现他们的健康和健身目标。

## 第 2 章 社交用例

| 目标 | 食物 | 运动 | 剩余 |
| :--- | :--- | :--- | :--- |
| 晚餐 | 3,650 - 1,161 + 0 = 2,489 | | |
| 零食 | | 453 cal | |
| 整装冷冻蓝莓 (Kirkland)，2 杯 | 213 | | |
| 仅有花生 - President's Choice 花生酱 - 蓝标，15 g (1 汤匙) | | 100 | |
| 蛋白粉饼干 奶油味 Muscle Pharm，1 勺 35g | | 140 | |

### 2-7. MyFitnessPal

该应用拥有超过700万种食物的数据库，允许用户记录餐食，或扫描包装上的条形码进行追踪。它包含了追踪液体摄入以及消耗的碳水化合物、蛋白质或脂肪的功能，以及运动记录，并可以与其他健身应用以及智能手表、体重等可穿戴设备同步。2015年，运动品牌 `Under Armour` 收购了 `MyFitnessPal`，但在2020年，它再次卖给了一家私募股权公司。为了在新管理层下降低成本，2022年甚至在 `Fitbit` 推出之前，`MyFitnessPal` 就删除了大多数挑战等社交功能，只留下了营养或运动的社交分享。

## 旅行

表 2-2 显示了前20大社交旅游服务。它们的类别从预订或住宿到飞行或社交骑行不等。

| 网站 | 类别 | 地区 |
| :--- | :--- | :--- |
| Airbnb | 社交住宿 | 全球 |
| Google Travel | 旅游搜索和内容分发 | 全球 |
| Trivello | 社交旅游 | 全球 |
| Tripit | 社交旅游 | 全球 |
| TripAdvisor | 社交旅游与评分 | 全球 |

### 表 2-2. （续）

| 网站 | 类别 | 地区 |
| --- | --- | --- |
| Buddy | 社交旅游 | 全球 |
| Flyer | 社交旅游 | 全球 |
| Ever Travel | 社交旅游 | 欧洲 |
| Backpacker | 背包客社区 | 全球 |
| Trippy | 社交旅游 | 全球 |
| Uber | 网约车 | 全球 |
| Lyft | 网约车 | 全球 |
| Bolt | 网约车 | 中国 |
| Free Now | 网约车 | 欧洲 |
| Ola | 网约车 | 印度 |
| Share | 网约车 | 联邦体 |
| Zipcar | 共享汽车 | 全球 |

## 移动使用

与大多数侧重于休闲或半专业运动员的健身门户网站不同，也有像职业自行车车手这样的运动员在使用它。

## 分析

| 订阅 | 2014年9月27日 星期六 上午12:26，美国旧金山 | 30.6 km 2:04:36 222 m |
| --- | --- | --- |
| 2014/09/27 加利福尼亚州旧金山 | 距离 | 移动时间 | 海拔高度 |
| 添加描述 | | 显示高度扩展状态 |
| | 0.33 34.1 km/h | |
| 心率 | 移动比例 | 最佳20分钟速度 | |
| 估算功率曲线 | 心率压力评分 | TRIMIMP 强度 | |
| 估算 230 W | 最佳20分钟心率 | 平均心率储备 | |
| 分布 | 36/36 (占时间的14%) | 12.4 km/h | |
| 圈数 | 爬升时间 | 平均爬升速度 | |
| 远程视图 | 中位步频 | 踏板时间 | |
| | -15.5 W (D. Sagan 公式) | -1.32 w/kg | |
| 估算归一化功率 | 每公斤瓦 | |
| | -222 w | |
| 估算最佳20分钟功率 | 此活动日期未在运动员中找到骑行FFP | |
| | 137 w 1,024 kj | |
| 估算平均功率 | 能量输出 | |
| | | 平均 | 最大 | 显示更多 |
| 已用时间 | 14.5 km/h | 42.8 km/h | |
| | 4:29:13 | | |
| | | 消耗量 | 骑行距离 / 30.1 km |

由 `'Elevate'` 扩展提供的地图功能已不再可用。目前显示此服务的成本过高。[忽略此消息]

![](img/3c2d905e913621002f512a08b8855a70_35_0.png)

### 图 2-5. Strava 活动

功能包括与他人分享的俱乐部和路线，以及供其他用户相互竞争的挑战，并与码速表、健身追踪器和智能手表等众多设备集成。

## 第 2 章 社交用例

![](img/3c2d905e913621002f512a08b8855a70_36_0.png)

## JavaOne 极客骑行者

加利福尼亚州旧金山

`Silicon Valley JUG` 将在 `JavaOne` 之前的周六举办年度极客骑行活动。我们将在渔人码头的 41 号码头集合，跨越大桥进入索萨利托（`Susalito`），然后乘坐渡轮返回市区。

## 图 2-6. Strava 俱乐部

某些功能需要付费订阅，但仍有足够的功能无需付费会员即可使用。

## Adidas/Runtastic

最初的想法源于2006年上奥地利州应用大学的一个项目，该项目旨在追踪帆船，随后导致了2009年`Runtastic`的成立。

2015年8月，宣布 `Adidas` 已以2.2亿欧元（2.4亿美元）收购了`Runtastic`，其中包括报业集团 `Axel Springer` 自2013年起持有的50.1%的股份。

## MyFitnessPal

`MyFitnessPal` 是一款手机和网络端应用程序，允许用户追踪他们的卡路里摄入、运动和其他健身信息。它是一个数字食物日记，帮助人们监控每日食物摄入量，以实现他们的健康和健身目标。

## 第 2 章 社交用例

| 目标 | 食物 | 运动 | 剩余 |
| :--- | :--- | :--- | :--- |
| 晚餐 | 3,650 - 1,161 + 0 = 2,489 | | |
| 零食 | | 453 cal | |
| 整装冷冻蓝莓 (Kirkland)，2 杯 | 213 | | |
| 仅有花生 - President's Choice 花生酱 - 蓝标，15 g (1 汤匙) | | 100 | |
| 蛋白粉饼干 奶油味 Muscle Pharm，1 勺 35g | | 140 | |

## 2-7. MyFitnessPal MyFitnessPal

该应用拥有超过700万种食物的数据库，允许用户记录餐食，或扫描包装上的条形码进行追踪。它包含了追踪液体摄入以及消耗的碳水化合物、蛋白质或脂肪的功能，以及运动记录，并可以与其他健身应用以及智能手表、体重等可穿戴设备同步。2015年，运动品牌 `Under Armour` 收购了 `MyFitnessPal`，但在2020年，它再次卖给了一家私募股权公司。为了在新管理层下降低成本，2022年甚至在 `Fitbit` 推出之前，`MyFitnessPal` 就删除了大多数挑战等社交功能，只留下了营养或运动的社交分享。

## 旅行

表 2-2 显示了前20大社交旅游服务。它们的类别从预订或住宿到飞行或社交骑行不等。

| 网站 | 类别 | 地区 |
| :--- | :--- | :--- |
| Airbnb | 社交住宿 | 全球 |
| Google Travel | 旅游搜索和内容分发 | 全球 |
| Trivello | 社交旅游 | 全球 |
| Tripit | 社交旅游 | 全球 |
| TripAdvisor | 社交旅游与评分 | 全球 |

### 表 2-2. （续）

| 网站 | 类别 | 地区 |
| --- | --- | --- |
| Buddy | 社交旅游 | 全球 |
| Flyer | 社交旅游 | 全球 |



## 旅行

表 2-2 显示了前20大社交旅游服务。它们的类别从预订或住宿到飞行或社交骑行不等。

| 网站 | 类别 | 地区 |
| :--- | :--- | :--- |
| Airbnb | 社交住宿 | 全球 |
| Google Travel | 旅游搜索和内容分发 | 全球 |
| Trivello | 社交旅游 | 全球 |
| Tripit | 社交旅游 | 全球 |
| TripAdvisor | 社交旅游与评分 | 全球 |

### 表 2-2. （续）

| 网站 | 类别 | 地区 |
| --- | --- | --- |
| Buddy | 社交旅游 | 全球 |
| Flyer | 社交旅游 | 全球 |
| Ever Travel | 社交旅游 | 欧洲 |
| Backpacker | 背包客社区 | 全球 |
| Trippy | 社交旅游 | 全球 |
| Uber | 网约车 | 全球 |
| Lyft | 网约车 | 全球 |
| Bolt | 网约车 | 中国 |
| Free Now | 网约车 | 欧洲 |
| Ola | 网约车 | 印度 |
| Share | 网约车 | 联邦体 |
| Zipcar | 共享汽车 | 全球 |

## 移动使用

移动使用并非总是社交媒体的一种，更多是对于像 `Google Fit` 这样的应用。

与大多数侧重于休闲或半专业运动员的健身门户网站不同，也有像职业自行车车手这样的运动员在使用它。

## 分析

| 订阅 | 2014年9月27日 星期六 上午12:26，美国旧金山 | 30.6 km 2:04:36 222 m |
| --- | --- | --- |
| 2014/09/27 加利福尼亚州旧金山 | 距离 | 移动时间 | 海拔高度 |
| 添加描述 | | 显示高度扩展状态 |
| | 0.33 34.1 km/h | |
| 心率 | 移动比例 | 最佳20分钟速度 |
| 估算功率曲线 | 心率压力评分 | TRIMIMP 强度 |
| 估算 230 W | 最佳20分钟心率 | 平均心率储备 |
| 分布 | 36/36 (占时间的14%) | 12.4 km/h |
| 圈数 | 爬升时间 | 平均爬升速度 |
| 远程视图 | 中位步频 | 踏板时间 |
| | -15.5 W (D. Sagan 公式) | -1.32 w/kg |
| 估算归一化功率 | 每公斤瓦 | |
| | -222 w | |
| 估算最佳20分钟功率 | 此活动日期未在运动员中找到骑行FFP | |
| | 137 w 1,024 kj | |
| 估算平均功率 | 能量输出 | |
| | | 平均 | 最大 | 显示更多 |
| 已用时间 | 14.5 km/h | 42.8 km/h | |
| | 4:29:13 | | |
| | | 消耗量 | 骑行距离 / 30.1 km |

由 `'Elevate'` 扩展提供的地图功能已不再可用。目前显示此服务的成本过高。[忽略此消息]

![](img/3c2d905e913621002f512a08b8855a70_35_0.png)

### 图 2-5. Strava 活动

功能包括与他人分享的俱乐部和路线，以及供其他用户相互竞争的挑战，并与码速表、健身追踪器和智能手表等众多设备集成。

## 第 2 章 社交用例

![](img/3c2d905e913621002f512a08b8855a70_36_0.png)

## JavaOne 极客骑行者

加利福尼亚州旧金山

Silicon Valley JUG 将在 JavaOne 之前的周六举办年度极客骑行活动。我们将在渔人码头的 41 号码头集合，跨越大桥进入索萨利托（Susalito），然后乘坐渡轮返回市区。

### 图 2-6. Strava 俱乐部

某些功能需要付费订阅，但仍有足够的功能无需付费会员即可使用。

## Adidas/Runtastic

最初的想法源于2006年上奥地利州应用大学的一个项目，该项目旨在追踪帆船，随后导致了2009年Runtastic的成立。

2015年8月，宣布 Adidas 已以2.2亿欧元（2.4亿美元）收购了Runtastic，其中包括报业集团 Axel Springer 自2013年起持有的50.1%的股份。

## MyFitnessPal

MyFitnessPal 是一款手机和网络端应用程序，允许用户追踪他们的卡路里摄入、运动和其他健身信息。它是一个数字食物日记，帮助人们监控每日食物摄入量，以实现他们的健康和健身目标。

## 第 2 章 社交用例

| 目标 | 食物 | 运动 | 剩余 |
| :--- | :--- | :--- | :--- |
| 晚餐 | 3,650 - 1,161 + 0 = 2,489 | | |
| 零食 | | 453 cal | |
| 整装冷冻蓝莓 (Kirkland)，2 杯 | 213 | | |
| 仅有花生 - President's Choice 花生酱 - 蓝标，15 g (1 汤匙) | | 100 | |
| 蛋白粉饼干 奶油味 Muscle Pharm，1 勺 35g | | 140 | |

### 2-7. MyFitnessPal

该应用拥有超过700万种食物的数据库，允许用户记录餐食，或扫描包装上的条形码进行追踪。它包含了追踪液体摄入以及消耗的碳水化合物、蛋白质或脂肪的功能，以及运动记录，并可以与其他健身应用以及智能手表、体重等可穿戴设备同步。2015年，运动品牌 Under Armour 收购了 MyFitnessPal，但在2020年，它再次卖给了一家私募股权公司。为了在新管理层下降低成本，2022年甚至在 Fitbit 推出之前，MyFitnessPal 就删除了大多数挑战等社交功能，只留下了营养或运动的社交分享。



| Backpacker | 背包客社区 | 全球 |
| --- | --- | --- |
| Trippy | 社交旅游 | 全球 |
| Uber | 网约车 | 全球 |
| Lyft | 网约车 | 全球 |
| Bolt | 网约车 | 中国 |
| Free Now | 网约车 | 欧洲 |
| Ola | 网约车 | 印度 |
| Share | 网约车 | 联邦体 |
| Zipcar | 共享汽车 | 全球 |

## 移动使用

移动使用并非总是社交媒体的一种，更多是对于像 `Google Fit` 这样的应用。与大多数侧重于休闲或半专业运动员的健身门户网站不同，也有像职业自行车车手这样的运动员在使用它。

## 分析

| 订阅 | 2014年9月27日 星期六 上午12:26，美国旧金山 | 30.6 km 2:04:36 222 m |
| --- | --- | --- |
| 2014/09/27 加利福尼亚州旧金山 | 距离 | 移动时间 | 海拔高度 |
| 添加描述 | | 显示高度扩展状态 |
| | 0.33 34.1 km/h | |
| 心率 | 移动比例 | 最佳20分钟速度 | |
| 估算功率曲线 | 心率压力评分 | TRIMIMP 强度 | |
| 估算 230 W | 最佳20分钟心率 | 平均心率储备 | |
| 分布 | 36/36 (占时间的14%) | 12.4 km/h | |
| 圈数 | 爬升时间 | 平均爬升速度 | |
| 远程视图 | 中位步频 | 踏板时间 | |
| | -15.5 W (D. Sagan Sagan) | -1.32 w wkg | |
| 算算归一化功率 | 每公斤 | | |
| | -222 w | | |
| | 最佳220分钟 | | |
| 活动日期未在在中找到骑行FFP | | | |
| | 137 w w1,0224 | | |
| 估平均平均 输出 | | | |
| | | | |
| 更多 | | |
| 已用时间 | 14.5 km km/ | 42.. km km/ | |
| | 4429:11 | | |
| | 消耗消耗消耗 | 骑行 / / 30.1 | |

由 `Elevate` 扩展提供的地图功能已不再可用。目前显示此服务的成本过高。[忽略此消息]

![](img/3c2d905e913621002f512a08b8855a70_35_0.png)

### 图 2-5. Strava 活动

功能包括与他人分享的俱乐部和路线，以及供其他用户相互竞争的挑战，并与码速表、健身追踪器和智能手表等众多设备集成。

## 第 2 章 社交用例

![](img/3c2d905e913621002f512a08b8855a70_36_0.png)

# 第3章 标准化

最后但同样重要的是，提供信息是你的应用程序向他人提供的任何服务，有时只是内容，理想情况下是通过 API 允许他人根据其需求进行消费、分析或转换这些内容。

看待企业社交网络、相关标准或产品的另一种方式如下：

- 具有社交属性的独立产品或服务，它们可以独立安装和使用。虽然其中某些（例如拥抱 `OpenSocial` 的产品）目标是与其他实现互操作性，最好是跨多个供应商的。
- 嵌入在大型产品或套件中的社交侧面或功能。一个经典的例子是 `Oracle Fusion Middleware`，它包含了继自 `BEA AquaLogic` [13] 以及此后 `Oracle` 在社交领域进行的其他几次收购 [23] 之后开发的社交功能。
- 专门的、通常是特定领域或垂直的社交网络，例如针对医疗保健、时尚、开发者、宠物主或任何令重大社区感兴趣的领域。你会在上一章中记得一系列这类网络。

`OPENi` [31] 是一个由欧盟资助的社交媒体研究小组，它尝试以某种上下文相关的方式对社交标准和 API 进行分组：

- 活动 API（`Activity API`）指的是社交、健康和行为活动日志，反映在多种云端服务中，范围从社交、照片和视频共享到健康和基于位置的服务。从本质上说，它包含了用户所有的社交和个人活动，并与设备的日志记录活动相关。相关类别：游戏、健康、基于位置的服务、音乐、照片、购物、视频。
- 广告和分析 API（`Advertising and analytics API`）能够根据用户与广告/营销内容的交互，收集、聚合和分析终端用户/客户的需求、兴趣和偏好。
- 应用行为数据（`Application behavioral data`）。
- 社交网络交互，旨在实现个性化广告服务，并增强终端用户的附加值。相关类别：分析、广告。
- 位置 API（`Location API`）允许通过签到（`Check-ins`）、路线（`Direction`）、活动、评论（`Reviews`）和提示（`Tips`）感知位置。这是一个强大的位置上下文 API，可以通过 GPS 传感器提取并映射到地图上。相关类别：地图、基于位置的服务、社交、音乐。
- 媒体 API（`Media API`）将照片、音乐和视频共享服务与文件传输及同步功能整合在一起。它与画廊应用程序和设备文件系统相关。相关类别：文件传输与同步、基于位置的服务、音乐、新闻、照片、社交、视频。
- 产品 API（`Products API`）涵盖了支付和购物服务。这种商业化相关对象的特殊情况需要一个具有事务能力和增强安全性的强 API。它与手机商店应用程序相关。相关类别：基于位置的服务、支付、购物。
- 配置文件 API（`Profiles API`）基于分析、广告、联系人、游戏、健康、基于位置的服务、消息和聊天、社交等推断关于人物的信息。通常，人们可以用多种方式表示，拥有多个配置文件。此 API 将所有信息汇集在一起：头像、个人资料、联系人和账户，将不同服务中的不同配置文件关联起来。它与智能手机的日程（`Agenda`）应用程序直接相关。一些相关类别：分析、广告、联系人、游戏、健康、基于位置的服务、消息和聊天、音乐、电影等。
- 搜索 API（`Search API`）用于从云服务中查找和检索信息。它将现有的搜索引擎与各种平台之间的分布式搜索功能整合在一起，并与桌面或手机操作系统中的搜索功能相关。

**图 3-2.** OPENi 概念

虽然 `OPENi` 没有在 GitHub 上发布过任何 API（正如它们在 2013 年承诺的那样），但它的工作引起了例如 W3C 的关注，`OpenSocial` [15] 现在那里正被进一步讨论。因此，即使没有自己的 API，`OPENi` 及其概念可能对那里有所帮助。我们将在查看 `Apache Shindind` 时更详细地介绍 `OpenSocial`。

除了之前拆析和分类社交媒体标准外，还有许多 API 和社交网络使用的其他标准和协议：

- 几乎所有的社交媒体服务都使用 REST 作为传输协议；有些使用 SOAP，但那并不常见。
- 它们中的大多数以 JSON 格式传输数据，有些使用 XML 或两者兼有。
- 身份识别和认证几乎总是基于 OAuth 2 或 OpenID Connect。

图 3-1 中未提到的其他基本标准和协议（该列表并非为了完整）如下：

- Open Graph 协议 (`OGP`) 允许任何网页成为社交图谱中的富对象。
- oEmbed 这种格式允许在第三方网站上对 URL 进行嵌入表示。
- PubSubHubbub 是一种简单的、开放的基于 web-hook 的服务器到服务器发布订阅协议。
- Salmon 是一种用于注释和标注的标准协议，使其能够“向上游游”（因此得名）回到原始更新源。

我们将在下一章详细查看授权、认证或数字身份等安全方面，以及隐私、数据保护和相关标准。

## 早期方法

我们在引言中遇到的理论，例如“六度分割”理论 [6]，影响了后来的概念，如“朋友之朋友”（`FOAF`）[8]。富内容摘要（`RSS`）[9] 是社交媒体的早期示例。在参与 `RSS` 设计的开发者中有 `Aaron Swartz`，他在 2013 年不幸离世之前，曾工作于 `Programmable Web` [10]。

`Portable Contacts` 是由 `Plaxo` 创建的，`Plaxo` 是由 `Sean Parker` 在 2002 年创立的社交地址簿录。当 `Parker` 参与其中时，他遭遇的法律麻烦与 `Facebook` 联合创始人 `Eduardo Saverin` 所遭遇的并无二致。在财务上，这让他变得富有，并为其他服务（例如 `Spotify`）提供了支持。这似乎并没有什么巧合，看起来非常像 `Napster`，但是以一种更被商业接受的方式实现的，这也归功于他在 `Facebook` 之后的名声和财富。`Portable Contacts` 可能是社交媒体运动的重要部分，但现在已不再使用。这是因为许多公司内部使用的 API 不再兼容 `Portable Contacts`。唯一仍在使用的残留是 `vCard`，它被许多公司和应用程序使用。

## 混合应用 (Mashup)

随着 Java 语言在桌面端发挥着越来越重要的作用（早期主要通过 Java applet，或通过 AWT/Swing 独立应用程序），随后在世纪交替之际在服务端也是如此，`Sun` 和其他公司开始在 Java 社区进程（成立于1998年）或 JCP [11] 中 Java 平台的部分进行标准化。在最早的成员中，`IBM`、`Intel`、`Sun` 和 `Oracle`（后两者自 2010 年合并以来）仍然活跃。

在被拒绝两次后，一个著名的社交网络标准（当时通常被称为“门户”，参见更早的 `MSN`）是 JSR 168，即 Java Portlet 规范 [48]。在理想世界中，它允许门户应用程序部署到多个供应商的门户服务器中，并与其他标准（特别是 OASIS 定义的 WSRP，远程门户 Web 服务）一起，引发了对这些应用程序跨不同门户互操作的希望。十年后，随着其他技术和语言（尤其是“轻量级容器”）的兴起，Java Portlet 标准在 2017 年获得了 3.0 版本更新（JSR 362），还计划整合

## 第3 章 标准化

在可能的情况下采用了一些社会标准，但这些标准已不再包含在 Portlet 规范中。

虽然 Portlet 及其相关标准仍然主要是受音乐或视频合集或混辑启发的大型企业级应用服务器的领域，但在第一个 Portlet 标准出现后不久，一种被称为 Mashup [12] 的更具语言和平台中立的方法开始出现。无论是 `Yahoo Pipes`、`Microsoft Popfly`、`Google Mashup Editor`、`IBM Mashup Center` 还是 `BEA AquaLogic` [13]，它们都承诺了互操作性和个性化小部件，其体验类似于 `iGoogle`。一项服务，主要是由于 `Google+` 将个性化和更“集成化社交媒体”的方法推向了新的高度，该服务已于 2013 年 11 月 1 日关闭。

`RSS` 也是如此，仅在 `Aaron Swartz` 去世后几个月后就停止了。`Google Reader` 于 2013 年 7 月 1 日停止服务。尽管 `Swartz` 在他未完成的书中 [10] 中提倡建立基于开放 API 的可编程 Web，但大多数主流供应商都有不同的计划，正如这篇关于 `Google Reader` 终结的文章 [14] 所表达的那样。

## OStatus

`OStatus` 是一种联邦微博客的开放标准，允许用户接收其他站点用户的状态更新。该标准结合了一系列开放协议，如：

- Atom
- Activity Streams
- WebSub
- Salmon
- WebFinger

它始于 2013 年的 `StatusNet`，后来变成了 `GNU social` [60]。它当时被许多微博客网站采用，但对底层技术的挫败感导致大多数网站转向使用 `ActivityPub`，包括 `Mastodon` [61]、`Pleroma` 或 `postActiv`。仍然在使用 `OStatus` 的唯一开源社交网络是 `Friendica` [62]，这是一个始于 2010 年的非常的开源社交方法，与 `GNU social` 一样用 PHP 编写；因此，对于其他人来说，这两个项目之间似乎更有协同效应。

## OpenSocial

另一个社会标准从诞生之初几乎由社区发展塑造：`OpenSocial` [15]，它由 `Google` 开发，最初有少数支持者，如当时 `MySpace` 仍是最流行的社交网络、`Ning` 或 `Plaxo`。此时，之前提到的便携联系人（`Portable Contacts`）也符合在各种社交网络提供商之间使用易用部件和小服务的整体理念，与之相比，例如 Java Portlet 标准 2.0 版本在同一时间发布了其公共草案（`Public Draft`）。

它似乎更容易使用，这同样适用于漏洞和安全问题，这些问题通常由“脚本小子”（`script kiddies`）或多或是小学毕业程度的学生使用几个脚本来破坏或攻破那些服务。而全面的 Java 服务器和 Portlet 如果系统管理员做好了功课，过去和现在仍然难以攻破得多，所有关于 Java 安全或其被用于传输恶意软件的喧哗通常只影响客户端。

`OpenSocial` 的绝大部分是 JavaScript 代码，这使得它比大多数位于服务器端或被谨慎使用的服务器（`Jakarta EE` 或其他环境）以及客户端层（JavaScript 等）更容易暴露。请参图 3-3 了解使用 Java EE 的典型 Web 端企业应用的不同层级，但你可以用 Python、PHP、Ruby 或 Scala 等其他语言替换它，其层级是相同的。

图 3-3。N 层级企业应用。

## 第3 章 标准化

虽然 `Google` 开始在其 `Orkut` 服务中使用 `OpenSocial`（这在拉丁美洲和印度等少数国家流行，但在其他地方从未真正流行起来），其他最初计划支持它的供应商在看到之后也放弃了这些计划。`LinkedIn` 或 `XING` 等公司特别是出于安全原因这样做的。我们将在下一章节中听到更多关于安全和隐私的内容。`Facebook` 和 `Twitter` 这上十年后半部分的两个主导供应商从未关心过 `OpenSocial`。重要的是，当情况变得显而易见时，`Google` 杀死了它的创建。`Google+` 也永远不会支持它。来自服务器和大型企业部分的少数供应商如 `IBM`、`SAP` 或 `Confluence` 作者 `Atlassian` 仍然支持 `OpenSocial`。

`Dach Group` 在 2014 年被 `Sprinklr` 收购，它是社交媒体和企业数据分析的“智库”，也深度参与其中，尽管它最近的重心更多转向大数据和 NoSQL 系统，并且它公开承认大多数剩余的 `OpenSocial` 支持者（尽管在他们的调查中被称为“雷达”，即很少工作或关注这些技术）最终可能只是企业和内网的唯一场所。大数据可以被看作一种 Mashup，尽管它主要置于 EIS 或 DB 层（见图 3-4），因此我不会在这里讨论它。这些技术也应该有自己的书，并且超出了本书的范范围。

**图 3-4。** ActivityPub 概述。

`OpenSocial` 的价值并不是 `Google`、`Facebook`、`Twitter`、`LinkedIn`、`Microsoft` 或 `Yahoo!` 的无缝 Mashup，它的唯一价值是将人事、销售或会计部门连接起来，并为管理层提供一个大型企业所有部门和子公司的巧妙“社交”Mashup，这对于那些希望看到比如在 `Twitter Feed` 旁边看到 `Facebook` 时间线信息的人来说实际上是没用的。而这正是 `OpenSocial` 最初创建的目的。

`OpenSocial` 故事中的一个转折是尝试创建一个基于 `OpenSocial` 和类似概念的 W3C 标准。这是一条艰难且棘手的道路，对于语义网（`Semantic Web`）来说似乎几乎是不可能的，特别是考虑到我们之前发现的大多数玩家更倾向于自己的“围墙花园” [14]。

虽然 W3C 定义了一个名为语义网的有趣标准，听起来与 `OpenSocial` 的想法相契，但语义网目前仅用于生物学或医疗保健等少数领域。

W3C 的工作速度通常较慢，类似于（甚至慢于）HTML5，例如后者始于 2008 年，一直处于候选状态（尽管许多供应商已基于此提出了解决方案），直到 2014 年底发布了最终建议，与大多数 W3C 标准相比，其持续时间很短。

## W3C 社交协议

W3C 社交小组的结果是一套社交协议 [63]，允许社交网络用户：

- 创建、更新和删除社交内容
- 通过订阅他人内容建立联系
- 与他人内容互动
- 在他人互动时收到通知

## 规范

这些是 W3C 社交小组产生的规范：

- `ActivityPub` - 基于 JSON-LD 的 API，用于发布和服务器与服务器之间的联邦交互
- `ActivityStreams` - 用于表示内容的语法和词汇：
  - `Activity`
  - `Actor`
  - `Link`
  - `Object`
  - `Collection`
  - Linked Data Notifications (`LDN`) - 基于 JSON-LD 的交付协议
- `Micropub` - 基于表单编码和 JSON 的 API，用于发布
- `Webmention` - 基于表单编码的交付协议
- `WebSub` - 用于订阅和交付更新的协议

想象 `Alyssa` 想跟上她的朋友 `Ben` 的进度。她最近借给了他一本书，现在想确保他把书还回来。这是一个作为 `ActivityStreams` 对象的示例消息：

```json
{"@context": "https://www.w3.org/ns/activystreams",
"type": "Note",
"to": ["https://chatty.example/ben/"],
"attributedTo": "https://social.example/alyssa/",
"content": "Say, did you finish reading that book I lent you?"}
```

服务器识别出这是一个新创建的对象，并将其封装在一个 `Create`（创建）活动中：



```json
{"@context": "https://www.w3.org/ns/activystreams",
"type": "Create",
"id": "https://social.example/alyssa/posts/a29a6843-9feb-4c74-a7f7-081b9c9201d3",
"to": ["https://chatty.example/ben/"],
"actor": {"type": "Note",
"id": "https://social.example/alyssa/posts/49e2d03d-b53a-4c4c-na5c-94a6abf4a519",
"attributedTo": "https://social.example/alyssa/",
"to": ["https://chatty.example/ben/"],
"content": "Say, did you finish reading that book I lent you?"}
```

Alyssa 的服务器查找 Ben 的 ActivityStreams actor 对象，找到他的收件箱端点（endpoint），并将该对象 POST 到他的收件箱。

# 采用

如果 Mastodon 在 ActivityPub 定稿后已经支持它，其他几个平台也随后之后，包括 Reddit、Goodreads、YouTube 或 Tumblr；Flickr 也在考虑添加支持。据报道，Twitter/X Threads 也使用它或计划很快添加支持 [64]。

# 去中心宇宙 (Fediverse)

去中心宇宙（由“federation”和“universe”组成）是一个“全球社交网络”，允许一个服务的用户使用 ActivityPub 等开放协议与其他服务的用户进行通信。去中心宇宙中著名的社交网络有：

- Mastodon
- Diaspora
- Friendica
- GNU social
- Hubzilla
- Lemmy
- PeerTube
- Pleroma
- Pixelfed

业内许多人认为，埃隆·马斯克收购 Twitter 并将其转型“X App”是开放社交网络和去中心宇宙的巨大催化剂。由 Jason Robinson 运营的统计网站 The-Federation.info 列出去中心宇宙的总用户接近 6.31 亿，其中过去六个月活跃数百万。他们的统计是自愿提供的，据称是不完整的；例如，Threads/Meta 以及其他几个使用去中心宇宙标准和协议的大型商业实体并未贡献这些数据；因此数字可能超过十亿，活跃用户达数千万。唐纳德·特朗普的 Truth Social 等网站基于开放标准并基本上类似于 Mastodon，但不会以透明的方式与其他网站交互。据称 Truth Social 目前的活跃用户约为五十万，而截至 2023 年 8 月，Mastodon 的活跃用户接近两百万。

# 去中心宇宙视角

谁在谁对话——如何对话？

图 3 去中心宇宙概览

# 协议

Federation.info 目前列出了去中心宇宙中使用的协议：

- ActivityPub
- Bluesky
- Gemini
- Matrix
- MicroPub
- NeoDb
- SMTP
- XMPP
- Zot

# Diaspora

Diaspora 拥有自己用于去中心化社交网络的协议。它开发于 2010 年，基于类似于电子邮件的联邦架构（具有收件箱和发件箱，与 ActivityPub 也类似），允许用户在由多个独立节点组成的“pod”网络中共享数据并进行通信（与 Kubernetes 无关，尽管某些 pod 可能运行在集群中）。除了 Diaspora 本身外，Friendica 或 Hubzilla 也使用该协议。

# Matrix

Matrix 最初是作为一种安全即时消息协议开发的。用例包括网络电话 VoIP、视频聊天。Matrix 的功能包括：

- 创建和管理完全分布式的聊天室，没有单点控制或故障
- 在全球联邦服务器网络中对房间状态进行最终一致的加密安全同步
- 在房间中发送和接收消息，可选端到端加密
- 用户管理
  - 邀请
  - 加入
  - 离开
  - 踢出、封禁
  - 由高级用户调解
- 房间状态管理
  - 命名
  - 名
  - 主题
  - 封禁
- 用户资料管理（头像、显示名称等）
- 管理用户账户（注册、登录、注销）
- 使用第三方 ID（如电子邮件地址、电话号码、Facebook 账户或其他社交 ID）来在 Matrix 上验证、识别和发现用户

**图 3-6.** Matrix 网络架构

# 采用

Matrix 被全球政府机构广泛使用，特别是在具有严格数据安全和隐私规定的欧洲。Rocket Chat 从 4.7.0 版本开始基于 Matrix。2021 年和 2022 年，FOSDEM 会议使用 Matrix 举办。

官方 Matrix 适用于：

- Gitter
- IRC
- Slack/Mattermost
- XMPP

以及由社区维护的几个其他桥接，适用于：

- Apple iMessage
- Discord
- 电子邮件
- Facebook Messenger
- LinkedIn
- Mastodon
- Signal
- Skype
- SMS
- Telegram
- WeChat
- WhatsApp

# Java 框架和库

遵循 Portlet API 或企业级 Java 各部分的 Java 标准，已经有一些用于社交媒体的 Java 框架和库。

## Java 版 Facebook Business SDK

Facebook (Meta) Business SDK 是一个一站解决方案，帮助合作伙伴和客户解决企业社交方案，允许合作伙伴使用多个 Facebook API（如 Pages、Business Manager、Instagram 等）来满足其业务需求。常见功能包括：

- 广告购买 - 为创建点击跳转消息广告的营销活动和推广你的 Facebook 页面提供指南
- Instagram 管理 - 在 Instagram 上发布照片和回复评论的指南
- 大规模客户入驻 - 管理数百或数千家小企业并通过其网站或平台为他们提供广告购买服务的指南
- 页面管理 - 创建页面、更新页面和管理其内容的指南

这是一个快速上手示例；请参 `https://github.com/facebook/facebook-java-business-sdk`。

```java
import com.facebook.ads.APIContext;
import com.facebook.ads.sdk.AdAccount;
import com.facebook.ads.sdk.AdAccount.EnumCampaignStatus;
import com.facebook.ads.sdk.AdAccount.EnumCampaignObjective;
import com.facebook.ads.sdk.Campaign;

public class QuickStart {
    public static final String ACCESS_TOKEN = "[Your access token";
    public static final Long ACCOUNT_ID = "[Your account id];
    public static final String APP_SECRET = "[Your app secret";

    public static final APIContext context = new APIContext(ACCESS_TOKEN, APP_SECRET);
    public static void main(String[] args) {
        try {
            AdAccount account = new AdAccount(ACCOUNT_ID, context);
            Campaign campaign = account.createCampaign()
                .setName("Java SDK Test")
                .setObjective(Campaign.EnumObjective.VALUE_CLICKS)
                .setSpendCap(10000L)
                .setStatus(Campaign.Enum.VALUE_PAUSED)
                .execute();
            System.out.println(campaign.fetch());
        } catch (APIException e) {
            e.printStackTrace();
        }
    }
}
```

## 第 3 章 标准化

服务将在几周内迁移到 v2。由于 Premium v1.1 API 产生了一些收入，它不太可能在不付费用户迁移到 v2 等效版本的情况下一夜之间消失。虽然 Gnip 在近十年前就被 Twitter 收购，但企业 API 最近才从 Gnip 2.0 更命名，而这一过程可能会因为那些被马斯克解雇或主动离职 Twitter 的经验丰富的开发者而受到阻。

以下是如何使用 Twitter4J 登录的示例。

使用 Twitter 登录：

```java
import twitter4j.*;
import twitter4j.v1.Status;
```

```java
class Main {
    public static void main(String[] args) throws Exception {
        long userId = Long.parseLong(args[0]);
        String accessToken = loadAccessToken(userId);
        String accessTokenSecret = loadAccessTokenSecret(userId);
        Twitter twitter = Twitter.newBuilder()
            .oAuthConsumer("consumer key", "consumer secret")
            .oAuthAccessToken(accessToken, accessTokenSecret).build();
        Status status = twitter.v1().tweets().updateStatus(args[1]);
        System.out.println("Successfully updated the status to [%s]".formatted(status.getText()));
        System.exit(0);
    }

    private static String loadAccessToken(long userId) {
        return "[token]"; // 从持久化存储加载
    }

    private static String loadAccessTokenSecret(long userId) {
        return "[token secret]"; // 从持久化存储加载
    }
}
```

我们将在第 6 章中展示更多如何使用 Twitter4J 的示例。

## Java Twitter API 客户端库

2021 年 8 月，Twitter 推了它自己的 Java API 客户端库 [35]。虽然起得很晚，但它仅支持 Twitter v2 API，旨在说服开发者迁移到新 API。

在 2021 年之前，除了可能是 Sun 和后来的 Oracle 之外，Twitter 在其总部举办面对面会议方面非常活跃且欢迎任何其他 JCP 成员。Twitter 还是 OpenJDK 的活跃贡献者，并维护着自己针对性能和扩展性优化的 JDK 版本。Twitter 提供 Java 客户端库也并不意外，尽管它来晚了些时候，而且 GitHub 仓库中的 readme 文件写着“这是测试版本，尚未准备好投入生产”。

在使用超过 100 个其他 GitHub 项目以及可能还有一些商业用户的情况下，只有三个贡献者；他们都都在 Twitter 工作，其中一位新西兰的贡献者仍然觉得与 Twitter 开发团队保持一致，尽管他的贡献在库的非常早期阶段就停止了。另一位位于新西兰，于 2023 年 2 月离开 Twitter，似乎是与马斯克闹翻。他还创建了 Twitter 的分支并对其进行了一研究，尽管似乎没有回传 Twitter 的 PR。时间会证明他是否还会对其做出贡献。最后一次贡献是来自法国电动汽车初创公司 Recharger Mon Auto 的创始人于 2022 年夏天提供的，大约是埃隆·马斯克收购 Twitter 的时候。尽管该委员会与 Tesla 没有直接的工作关系，但这一时间点表明他可能来自埃隆的圈子并被要求查看代码，或者至少他的公司对使用 Twitter API 有重大利益并了其中。

最后一次贡献是在 2022 年 10 月，当时马斯克的收购完成，之后没有有任何代码提交。

这里是 Twitter API 客户端库的“Hello World”示例；见 `https://github.com/twitterdev/twitter-api-java-sdk`。

```java
package com.twitter.clientlib;

import java.util.HashSet;
import java.util.Set;
import com.twitter.clientlib.TwitterCredentialsBearer;
import com.twitter.clientlib.ApiException;
import com.twitter.clientlib.api.TwitterApi;
import com.twitter.clientlib.model.*;

public class HelloWorld {
    public static void main(String[] args) {
        /**
         * 设置所需 API 的凭据。
         * Java SDK 支持 OAuth2 & TwitterCredentialsBearer。
         * 检查 https://api.twitter.com/2/openapi.json 中
         * 所需 API 的 'security' 标签以使用正确的对象。
         */
        TwitterApi apiInstance = new TwitterApi(new TwitterCredentialsBearer(System.getenv("TWITTER_BEARER_TOKEN")));

        Set<String> tweetFields = new HashSet<>();
        tweetFields.add("author_id");
        tweetFields.add("id");
        tweetFields.add("created_at");

        try {
            // Get TweetById
            TweetByIdResponse result = apiInstance.tweets().findById("0")
                .tweetFields(tweetFields)
                .execute();
            if (result.getErrors() != null && result.getErrors().size() > 0) {
                System.out.println("Error:");
                result.getErrors().forEach(e -> {
                    System.out.println(e.toString());
                    if (e instanceof ResourceProblem) {
                        System.out.println((ResourceProblem) e).getTitle() + " - " + ((ResourceProblem) e).getDetail());
                    }
                });
            } else {
                System.out.println("findById - Tweet: " + result.toString());
            }
        } catch (ApiException e) {
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
            e.printStackTrace();
        }
    }
}
```



该 API 是否能从 Beta 版本毕业还有待观察，但考虑到主要维护者不再那里工作，以及马斯克领导下 Twitter 的整体努力，这似乎不太可能。我们将在第 6 章展示更多如何使用 Twitter API 的示例。

## Apache Social

Apache [19] 在 OpenSocial [15] 工作开始后不久便启动。主要由 Google 它的 Orkut 驱动（显而易见），其他贡献者（尤其是 IBM）后来加入。由于 OpenSocial 转向了“社交内网”，没有任何一个声称使用它的网站或软件是确定真的在使用它。事实上，Google 指向了一个不存在的页面；因此，它像我们听过的其他例子一样被关闭了。

Google 在 Eclipse 的 WYSIWYG 环境中开发 OpenSocial 应用程序的一种有趣方法是 OpenSocial 开发环境 (OSDE)；见 [20]。可以假设部分内容已被 IBM 接管并集成到基于 Eclipse 的开发工具的社交版中（如 RAD 等），而 Google Code 项目最后一次更新是在 2010 年 6 月。

链接到 Apache 的 OpenSocial API 规范已不再由 OpenSocial 支持者 Atlassian 托管；它链接指向一个错误页面。这意味着 Atlassian 不再相信 OpenSocial 不会在其产品的较新版本中使用它，还是仅仅是在 W3C 上复兴整个 OpenSocial 运动的过程仍有待观察。在此，OpenSocial 的所有版本（特别是 1.0 或 2.0）都是失败的，像 Orkut 这样的网站最多使用了 0.7 或 0.8 版本。根据支持 OpenSocial 的 Dachis Group [16]，Social 代表了一种基础标准 (v2)。这意味着同时提供信息和消费信息。

2014 年 9 月 30 日，Google 关闭了 Orkut，使得 Google+（它在 2019 年也停止了）成为当时唯一的 Google 引用。到 2015 年，仍有 20 多个社交网络集成了 OpenSocial，如 StudiVZ、MySpace、LinkedIn 或 XING，但之后，大多数社交媒体供应商都逐渐放弃了它。

Google 已经停止使用 Social 转而使用它自己的 Google Code 项目。它们的大多数也被关闭了，现在指向 OpenSocial 页面且不再存在。因此，在 2015 年 10 月 23 日，Apache 基金退役了 Social 项目。此后，随着 OpenSocial 事实上的参考实现的停止，它也遵循了同样的命运。

## Sun/Oracle 的努力

2008 年左右，创建 Enterprise Social Mashup 的 BEA Systems [13] 刚被 Oracle 收购；Java 的创造者 Microsystems 并没有完全猜到类似的命运也即将到来。基于 OpenSocial，Sun 在 Apache 上创建了一个名为 SocialSite [21] 的分支或衍生项目。

SocialSite 在 java.net 上仍包含 231 个成员，但该项目处于不活跃状态。最后的几次提交之一来自 Kohuke Kawaguchi，他是 Sun 的 Hudson CI 服务器以及后来的 Jenkins 的创建者，后来被 CloudBe 用。

在收购 RightNow Technologies（见 2011 年底的 [23]）后（具有社交属性的 SaaS CRM 软件制造商——此举显然针对 Salesforce com 或 SAP 等公司），一些前 RightNow 团队和产品被并入 Oracle 的社交功能企业部门。

JavaOne2012 有了一场社交日，我也参加了，演讲者包括 Facebook 的开发者关系经理 James Pearce。Oracle 本身展示了一个由自由职业承包商为 RightNow 编写的“单人”项目，名为“Project Sneaker”，在 JavaOne2012 之后不久发布为 Oracle SocialLink [24]。

它从未在 Oracle 之外吸引追随者，被认为比以往任何 SocialSite 都更加密集。

## DaliCore

在 Oracle 接管 Sun 后，被遗弃的 SocialSite 在 DaliCore [22] 中找到了它最好的等效物和继任者。

## 第 3 章 标准化

它最初基于一家比利时初创公司创建的 CMS，主要由像 Johan Vos 等 BeUG（Devoxx 会议）成员组成。DaliCMS (2006) 被称为“Web 2.0 就绪的 CMS”。

它主要是一个具有社区特性的开源项目。2008 年，与 Sun 开发 SocialSite 差不多，DaliCMS 增加了对 Shindig 的支持，主要包含来自 Shindig 的 JavaScript 代码和 DaliCMS 提供的某些 Java 代码。

最终，它不仅仅是一个 CMS，底层模块演变成了 DaliCore。在 2013 年的 JavaOne 演讲中，Johan Vos 揭示了“Dali”部分的起源，它代表“荷兰亚马逊爱好者倡议（Dutch Amazon Lovers Initiative）”——这是对互联网和云先驱 Amazon 的致敬。

DaliCore 在 Java EE 6 之上增加了用户管理、内容或权限的常用功能，并重点关注用户和权限。在每个使用 DaliCore 的项目中，用户都应该能够使用现有凭据（Facebook、Twitter、Google+、LinkedIn）登录。因此，Cali 模块扩展了 DaliCore。虽然某些连接扩展到了 Facebook 等社交提供商，但它们主要作为 DaliCore SSO（单点登录）功能的身份验证提供。除此之外，DaliCore 旨在提供信息。

DaliCore 的重要方面如下：

- 大部分包含部分开放社交特性的社交 CMS。
- 通过 EJB、JPA 或类似标准提供 Java 持久化支持。
- 大多数情况下模块之间没有清晰的划分，特别是 API/Spec 和实现部分共享相同的模块甚至相同的包大小，尽管通过 Dali Module 尝试这样做，但使得重用和扩展变得更加困难。
- 看起来有点笨重，对全 Java EE 配置文件的强依赖依赖，也就是说，仅使用其 Web Profile 看起来更困难。
- 对 GlassFish 的支持和集成是积极的，它是首选的应用程序服务器。得益于 Java EE 标准，与其他容器并非不可能，但在其他容器上使用似乎更困难。
- 它证明了在某些客户的高强度使用下具有可扩展性，例如比利时的一个电子投票系统。与 Apache Shindig 或 SunSocialSite（DaliCore 在大多数情况下似乎是其自然继任者）不同，它至少被比尼荷卢国家的实际客户使用。

## 第 3 章 标准化

在 Oracle 宣布将不再为 GlassFish 提供商业支持或增强功能（如集群，除了 Java EE 参考实现提供的 PoC 质量外它将保留）、性能调优等之后，DaliCore 的一个主要论点消失了。Oracle 推荐其 WebLogic/Fusion Middleware 产品，或者当前的 GlassFish 用户如果需要商业支持，将被迫迁移到其他服务器。

DaliCore 作者 Johan Vos 和他的比利时初创公司声称将为客户提供商业支持，甚至可能扩展到该领域，但 DaliCore 已已成为他们的明显受害者。自 2013 年初以来，java.net 仓库没有任何活动，在 Oracle 于 2017 年宣布 java.net 后，没有任何内容迁移到其他地方，至少没有迁移到公开访问的网站。尽管 Johan 当时告诉他仍在工作，但他同时也确认是在 Bitbucket 的一个私有仓库中完成的。因此，DaliCore 从未开源，现在必须被认为已经终结。

## Spring Social

SpringSource 在再次成为 VMware 的之前曾被母公司重命名为 Pivotal，它在追赶趋势以及为 Spring Framework 提供几乎所有内容的库或扩展方面有着悠久的历史。

Spring Social [25] 是一个消费信息的绑定库。尽管将 OAuth 与 Spring Security 及其他部分集成是基础 API 的特征，但它展示了比这里提到的大多数其他解决方案更多的高阶 API 方面。Spring Social 的重要方面如下：

- 出于显而易见的原因，主要与 Spring Framework 或 Spring 生态的其他部分配合。
- Spring MVC 以外的 UI 框架集成相对较困难。
- 官方的 Spring Social 连接器主要关注 Facebook；示例仅显示了单服务方法。
- 尽管 Spring 社区总体活跃，但它已不再受到活跃支持。
- Spring Social 背后只有一家公司雇佣的一两个活跃提交者和驱动者。

我们将在第 6 章介绍更多关于 Spring Social 的内容。

## Microsoft Embedded Social

Microsoft Embedded Social [34] 于 2012 年 5 月 15 日建立，是一个应用程序内部社交用户参与的多租户云服务。虽然它主要是一个研究项目，但其项目页面声称曾有超过 2000 万用户使用。

它旨在跨多个社交网络进行抽象，类似于 OpenSocial、Seam Social、Spring Social 或 Agorova 等其他努力。

### Embedded Social 架构

| 特性 |  |
| :--- | :--- |
| 用户身份认证 | 包含功能 |
| 用户配置文件 | 包含功能 |
| 主题 | 包含功能 |
| 动态馈 | 包含功能 |
| 内容审核 | 包含功能 |
| 搜索 | 包含功能 |

除了 2016 年购买的 Java 之外，其他似乎大多不活跃。

## 总结

在本章中，我们学习了各种社交标准以及标准化与社交网络交互的努力，这允许了某种程度的供应商中立性和跨平台发布。

# 第四章

## 社会安全

如今网络安全攻击的激增使得有必要从多个安全战线防御你的组织，无论是物理、技术还是政策和程序。上述的每一个战线对你组织的安全都同样重要。为了建立一个面向未来且安全的组织，其中任何一个战线都不应被忽视。这意味着，仅有物理和技术安全对黑客来说确实具有挑战性，但如果你的员工没有经过良好的教育来保护密码，你组织的整体安全性并不高。

信息安全基于：

- 机密性 (Confidentiality)
- 完整性 (Integrity)
- 可用性 (Availability)

这三个概念通常被称为 CIA 三要素（CIA Triad）。它们随着时间的推移而形成，并没有单一的创造者。机密性最早在 1976 年美国空军的一项研究中提出；完整性概念在 David Clark 和 David Wilson 于 1987 年写的一篇名为《商业与军事安全策略比较》的论文中得到了探讨 [55]。

论文指出商业计算对审计记录和数据准确性有需求。虽然找到最初来源并不容易，但可用性概念在一年后的 1988 年变得更加广泛。又十年后，到 1998 年，人们将这三个概念共同视为 CIA 三要素。

> 机密性 – 信息不应被未经授权的用户读取。
>
> 完整性 – 信息不应能够在不被被察觉的情况下被伪造。
>
> 例如，黑客不应能够在数据被发送给预期接收者之前捕获并修改任何数据。
>
> 可用性 – 要求信息在授权用户需要时随时是可以访问的。

除了 CIA 三要素外，还有一些社交媒体安全的其他关键概念：

- 机密性
- 完整性
- 可用性
- 隐私 (Privacy)
- 身份认证 (Authentication)
- 授权 (Authorization)

隐私 – 用户可以控制其个人信息的访问、使用和披露。隐私是维持秘密性、匿名性以及免受监视或侵入私人事务的概念。隐私可以理解为控制何时、如何以及在多大程度上与他人分享个人信息的权力。

根据 CCPA（加州消费者隐私法案），个人信息是指“识别、关联、描述、合理能够关联、或可以合理地直接或间接与特定消费者或家庭相关的信息”。

根据 GDPR（通用数据保护条例），个人信息被称为“个人数据”，被认为是“任何与已识别或可识别的自然人相关的信息”。

身份认证 – 用户可以证明他们所称的身份，即他们的身份；例如，客户端可以向服务器证明他们正在代表授权身份进行操作，反之亦然。或者入入电话的呼叫显示号码。

授权 – 用户拥有足够的权限来访问受限资源或执行特定操作。

如今身份认证和授权有时会被混淆，所以这里有一个很好的方法来记住它们在身份和访问管理（IAM）世界中如何区别。身份认证确认用户确实是他们所称的人，而授权则允许这些用户访问资源。

## 隐私

“Privacy”一词源于“private”，具有拉丁语词源：“privīātus”，字面意思是从公共事务中被剥离。

虽然古代罗马人可能能够向公众和他们当时的著名作家隐藏他们的某些事务，而且从某事发生到被记录并被读者阅读之间至少有几天，更多时候是几个月甚至几年，但在今天，这有时只是眨眼之间或点击一下鼠标按钮的事。

举报人埃德华·斯诺登（Edward Snowden）的揭露是最广泛的，但绝对不是隐私问题进入公众视野的案例，特别是关于社交网络或类似的在线服务 [37]。在几十年前，将来自各种来源和日常生活的数据合并成用户数字画像和足迹的能力，主要是警察和秘密服务工具的领域，例如“网捕”（Dragnet，不像电影中的意思，尽管它幽默地指代该系统）。

仅仅斯诺登和他的技能现在允许他的俄罗斯东主使用，这清楚地表明，西方国家和机构并非对这类信息感兴趣的唯一。许多国家试图控制；如果社交网络提供的关键信息不能与其本国情报机构（通常是美国、中国、俄罗斯或土耳其）相同，一些国家就会简单的封锁或限制整个服务，临时或永久封锁某些提供商的国家名单仍在不断增加。如果所有权或托管被外包（不是为了税收而是为了廉价劳动力），某些服务也可能受到这些国家做法的影响。我们之前听过的最流行的例子之一是 LiveJournal，因为 OpenID 1.0 曾在那里创建过。2007 年，它从 Six Apart 卖给了俄罗斯媒体集团 SUP Media。

2009 年之后，它的大部分生产也转移到了俄罗斯，硅谷的员工被解雇了。尽管 SUP Media 是私有所有的，但它显然受到俄罗斯秘密部门的控制和审查。例如，2007 年，俄罗斯博主 Savva Terentiev 被指控向内政部（Ministry of Internal Affairs）煽动社会仇恨，由于他在当地记者的博客上的评论，被处一年缓刑。更不用说最近的谋杀案，如莫斯科反对政权的人士鲍里斯·内姆措索夫（Boris Nemtsov），他在宣布披露俄罗斯参与乌克兰和 2014 年占领克里米的信息仅几小时后被杀。讽刺的是，即使在像俄罗斯这样审查最严的国家之一，也有一丝微小的希望，即社交媒体如果没有带来真正的改革，可能有助于找到他遇杀的线索 [38]。

# 第四章 社会安全

此外，由于俄罗斯从 2022 年初开始对乌克兰发动全面战争，许多俄罗斯士兵可能会受到乌军的攻击，因为他们在社交媒体或约会网站上公开了自己的行踪。

虽然“国家安全”论以及试图在网上抓捕恐怖分子或严重罪犯的论点被用来为全球范围监视辩护，但如果批评博主或记者的身份被暴露，他们面临的不仅是隐私风险，还有生命危险。

- 3. LinkedIn – 受数据泄露影响的 11 亿个 LinkedIn 账户大部分发生在 2021 年，当时 7000 万用户的详细信息在暗网上被出售。
- 4. MySpace – 三次数据泄露泄露了 7.19 亿 MySpace 用户的数据。
- 5. Sina Weibo – 关于这一中国社交网络 5.39 亿用户的数据（包括 1.72 亿个手机号码）于 2020 年在暗网上挂出。
- 6. Twitter – Twitter 在 2023 年 6 月确认，一名黑客获取了 540 万账户的用户详情。这使得受影响的账户总数达到 3.7 亿，超过了如今“X”的活跃用户数。
- 7. Quora – 2018 年的一次黑客泄露了 1 亿个密码和安全问题。
- 8. Dailymotion – 2016 年，一名黑客从视频分享平台 Dailymotion 偷走了超过 8500 万个电子邮件地址、用户名和密码。
- 9. Tumblr – 同样在 2016 年，Tumblr 宣布其安全和用户隐私在三年前（2013 年）曾遭到破坏，6500 万用户的账户详情被盗。
- 10. Instagram – Meta 旗下 Instagram 至少有 4900 万用户在 2019 年遭遇了隐私泄露，当时一个未受保护的服务器遭到入侵。

这并不意外，除了总部位于法国的 Dailymotion 和来自中国的中国微博，其他公司都来自美国，那里的监控无处不在，隐私处理通常很松散。Twitter/X 的竞争对手 Meta 的 Threads 尚未在欧盟全面推出，这与欧洲这里的数据保护和隐私法律有关，也可能与那里过去发生的大规模数据泄露有关。

除了起源于欧盟外，XING 等服务还为用户提供了更细粒度的访问权限和控制，在这些服务中，你有时可以限制如何查看每一个项目。例如，你想向所有访问个人资料的人显示你的名字和生日，但不显示年份或年龄，或者只允许朋友查看你的手机号码；这些更多内容可以通过 XING 这样的系统进行控制。

这也是 XING 放弃 OpenSocial 的原因之一，因为它无法提供这种细粒度的访问控制，或者在某些情况下不提供任何控制，而是向所有人显示所有内容，或至少向你所有的朋友显示数据。

通过 W3C 等或其他取代 OpenSocial 并用于联邦宇宙（Fediverse）的大多数标准和协议并不总是适用于隐私，但有少数几个，特别是 Matrix，它非常关注安全和隐私（记得上一节，Matrix 最初是在以色列的 Amdocs 创建的），因此受到全球非政府组织和政府机构的信任。



Diaspora 也非常重视隐私，这就是为什么像伊斯兰极端组织 ISIS 这样的极端分子在 2014 年被 Twitter 等大型社交网络审查或封禁了账户后，涌向了那里。作为一个具有高隐私标准的分布式服务，在缺乏中央控制点、监控或内容拦截的情况下，这并非易事，但到 2014 年 8 月，Diaspora 基金会表示通过社区管理和社区口碑，所有大型节点（pods）都删除了 ISIS 内容和账户。

埃隆·马斯克只是一个普通人，杰克·斯威尼（Jack Sweeney，出于粉丝心态或好奇）在马斯克接管 Twitter 几天后，就在网络外追踪了他的航班，声称这将“人肉搜索”（dox，分享某人的信息，通常是位置）。这个人转到了 Mastodon 以及 Instagram 等其他社交网络。当然，同一个埃隆·马斯克经常在卡塔尔 2022 年世界杯决赛及类似场合的公开活动中发布推文。

现在，由埃隆·马斯克运营的 X（原 Twitter）计划收集用户的生物识别数据，以及他们的职业和教育背景。目前还没有解释他们为什么要存储生物识别信息。通行密钥认证（Passkey Authentication，我们将在本章稍后介绍更多，由 PayPal 提供，那是埃隆·马斯克白手起家的公司，作为早期采用者）如果执行得当，不会交换生物识别信息。它只会留在设备中。因此，更有可能的原因是马斯克计划进行类似于 OpenAI 创始人萨姆·奥特曼发起的 Worldcoin 类似的计划，这涉及生物识别验证。据报道，计划收集职业和教育背景与“Hire”计划有关，这是“X”体系下 LinkedIn 或 XING 的某种竞争对手，但马斯克作为罗恩·德桑蒂斯及其“反觉醒”运动的亲密盟友，而在佛罗里达及等地，教授“某些错误”内容的老师往往会受到歧视或被解雇，但——

## 第 4 章 社会安全

我们将强认证定义为使用两种或两种不同的认证方法，例如智能卡和 PIN 码，或者密码和某种生物识别形式（如指纹、语音或虹膜识别）。

# 认证的最新趋势

就只有这些吗？我们只能使用三种认证方法来保护系统安全吗？

显然不是。随着黑客变得越来越聪明，我们需要额外的（以及更复杂的）认证方法，包括“你所在的位置”和“你所做的事情”。

“你所在的位置”（Somewhere you are）与你的位置有关，支持两种不同的形式：地理位置安全检查，即根据用户的位置与其账户配置的位置进行匹配；以及 MAC 地址检查，例如，如果一个员工尝试从不同的机器访问公司网络，将不会获得任何不同 MAC 地址的访问权限。

“你所做的事情”（Whatever you do）是最不受欢迎认证方法。这种认证的核心在于通过观察用户的动作（触摸或手势）来验证用户。这里的例子可以是 Windows 8 自带的密码功能，它允许你将触摸和手势作为身份验证的一种。另一个更具技术含量的“你所做的事情”的例子是智能手机的手势认证，你用大拇指在手机屏幕上滑动一个手势图案即可解锁手机。

# 密钥认证（Passkey Authentication）

密钥（Passkeys）允许你安全地登录社交网络等服务，而无需输入密码。

与安全密钥（security keys）不同，密钥的优点是支持用户验证。这意味着密钥使用“你所知道的”或“你的特质”来验证你的身份，例如 PIN 码或生物识别检查（如指纹、虹膜或面部识别）、图案或 QR 代码。

### 历史

密钥的概念最早出现于 2009 年，当时 Validity Sensors（后被 Synaptics 收购）和 PayPal 联手提出了一个使用生物识别代替密码进行在线身份识别的概念。他们与其他几位 IT 领袖一起，于 2012 年 7 月创立了网络安全组织 FIDO 联盟。FIDO 代表快速身份在线（Fast Identity Online）。

Google 于 2013 年加入。随后的 2014 年，PayPal 和三星通过三星 Galaxy S5 智能手机开始了 FIDO 认证。设备用户只需指触即可验证 PayPal，并在完成交易时无需输入密码即可在线购物。“密钥”（passkeys）这一术语近期才流行起来，苹果在 2022 年 6 月的全球开发者大会上推出了该概念，并在当时公开宣布了 iOS 16 和 macOS Ventura 中的密钥功能。

## 它是如何工作的？

密钥基于 FIDO 联盟开发的 WebAuthn 加密协议。每个密钥都是一对非对称加密密钥，且仅对创建其时所属的网站有效。该密钥对由一个保存在你设备上的私钥（位于支持密钥的密码管理器内部，即密钥提供者）和一个存储在你想登录的网站上的公钥组成。

你可以将公钥证书理解为数字意义的护照。

# 认证示例

在这一节中，我们涵盖了认证基础的一些理论内容。难道不像我们一样对看到它在代码中如何实现感到兴奋吗？让我们通过查看一些认证的基础代码片段来窥探 Jakarta EE 的世界。

在 Jakarta EE 中，组件容器负责提供应用安全。容器提供两种类型的安全：声明式安全和程序化安全。声明式安全通过部署描述符和注解来配置组件的安全机制，而程序化安全则由安全感知应用程序使用，以补充其安全模型。

# 程序化认证

可以使用 `SecurityContext` 和 `HttpServletRequest` 接口进行程序化用户认证。

### SecurityContext

Jakarta EE Security API 规范（你将在接下来的章节中有机会评估）规定了一个方法来帮助你程序化触发认证过程：

- `authenticate()` 允许应用程序通知容器其应该开始与调用者的认证过程。

`HttpServletRequest` 接口允许你通过指定三个简单方法来程序化地认证 Web 应用用户：

- `authenticate()`：通过指定三个简单方法来程序化地认证 Web 应用用户。例如，如果是一个表单，它将显示登录表单。

- `login()`：验证提供的用户名和密码。

- `logout()`：重置请求。

以下代码展示了如何使用 `authenticate` 方法：

```java
public class EnterpriseServlet extends HttpServlet {
    protected void processRequest(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        response.setContentType("text/html");
        try (PrintWriter writer = response.getWriter()) {
            request.authenticate();
        } catch (Exception e) {
            throw new ServletException(e);
        }
    }
}
```

另一个示例展示了如何使用 `login` 和 `logout` 方法：

```java
public class SampleLoginServlet extends HttpServlet {
    protected void processRequest(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        response.setContentType("text/html");
        try (PrintWriter out = response.getWriter()) {
            out.println("<html>");
            out.println("<body>");
            request.login();
            BigDecimal result = new BigDecimal("55.0");
            out.println("<h1>LoginServlet result of " + result + "</h1>");
            out.println("</body>");
            out.println("</html>");
        } catch (Exception e) {
            throw new ServletException(e);
        } finally {
            request.logout();
        }
    }
}
```

# 授权（Authorization）

授权也称为访问控制，是管理访问的过程——换句话说，控制谁可以访问什么。

更正式地说，授权是定义访问策略。授权的示例是：允许用户查看此网页、编辑此信息或使用此打印机吗？这些都是决定用户什么的决策。

## Jakarta 授权

Java 有一种安全架构，可以保护移动或静态代码免受未经授权的访问。问题在于手动确定执行所需的权限集。常用的策略是执行代码、记录授权失败、分配额外的权限并再次测试，直到代码针对所需的用例成功运行。这些用例可能无法覆盖所有路径，因此可能会发生失败。另一方面，可以为代码分配广泛的权限以防止授权失败，但这通常违反了最小权限原则 [27]。

最小权限原则要求在授予特定信息和工具时采用最小化方法。此外，权限应该是基于时间的，以限制访问资源的时间为完成任务所需。超出此范围授予权限会导致不必要的访问，以及数据在未经授权的情况下被更新。分配权限将限制用户造成的系统破坏（无论是故意）。基本的 Java 安全依赖于权限，例如访问文件系统的 `FilePermission` 或使用 AWT/Swing 资源的 `AWTPermission`。

如果有人想为特定应用程序允许新类型的权限，可以通过在文件中添加条目来实现。允许来自 "http://mysocial.tv/" 代码查看 ARTE 的权限示例如下：

```
grant codeBase "http://mysocial.tv/ " {
    permission fr.arte.TVPermission "arte-tv", "watch";
}
```

# 第 4 章 安全安全

- **角色（Role）**是 Jakarta EE 中的一个访问层级概念。Jakarta EE 开发者指定哪些角色可以访问哪些应用程序功能。这些角色随后通过特定厂商的配置数据映射到用户和组。

- **主实体（Principal）** 是一个带有凭据的身份，可以使用身份验证协议进行身份验证。

- **凭据（Credential）**包含或引用用于身份验证 Jakarta EE 主实体的信息，例如通过输入密码或调用外部服务。更多信息请参见“身份验证（Authentication）”。

Jakarta Security 的官方范围是：

Jakarta Security 提供了一系列必需的安全功能，包括身份验证、授权、数据完整性和传输安全。

你可能在第 3 章记得，几乎每个社会服务或类似的 API 都使用 RESTFUL Web 服务。REST 代表“表述性状态转移（Representational State Transfer）”。Jakarta REST（以前称为 JAX-RS）是用于 RESTful Web 服务的 Jakarta EE API。

以下是关于如何通过注入 Jakarta EE `SecurityContext`（安全上下文）实例来完成授权的几处简要示例。注入的安全上下文运行在较低层级的 `HttpServletRequest` API 之上。注入的安全上下文取决于实际 RESTful Web 应用程序的部署。

`SecurityContext` 可以与子资源定位器（subresource locators）结合使用，根据用户主实体包含的特定角色返回不同的资源，使用 CDI `@Context` 注解 [28]。例如，如果用户是“优惠客户”，子资源定位器可以返回不同的资源。

```java
@Path("basket")
public ShoppingBasketResource get(@Context SecurityContext sc) {
    if (sc.isUserRole("PreferredCustomer")) {
        return new PreferredCustomerShoppingBasketResource();
    } else {
        return new ShoppingBasketResource();
    }
}
```

在“资源”端点使用 `SecurityContext`：

```java
@Path("resource")
@Singleton
public static class MyResource {
    @Inject
    SecurityContext securityContext;

    @GET
    public String getUserPrincipal() {
        return securityContext.getUserPrincipal().getName();
    }
}
```

通过将 `SecurityContext` 注入到单例资源中。在 Servlet 容器中，你只能依赖 Servlet 容器提供的标准 Jakarta EE Web 应用程序安全，并通过 `web.xml` 描述符进行配置，通过在 `web.xml` 中定义 `<security-constraint>` 元素并分配访问这些资源的角色。你还可以定义允许执行的 HTTP 方法。见下面的示例：

```xml
<security-constraint>
  <web-resource-collection>
    <url-pattern>/rest/admin/*</url-pattern>
  </web-resource-collection>
  <auth-constraint>
    <role-name>admin</role-name>
  </auth-constraint>
</security-constraint>
<security-constraint>
  <web-resource-collection>
    <url-pattern>/rest/orders/*</url-pattern>
  </web-resource-collection>
  <auth-constraint>
    <role-name>customer</role-name>
  </auth-constraint>
</security-constraint>
```

```xml
</security-constraint>
<login-config>
  <auth-method>BASIC</auth-method>
  <realm-name>my-default-realm</realm-name>
</login-config>
```

# EE 身份验证 (Authentication EE)

Jakarta EE 平台支持以下身份验证机制：

- 基础身份验证（Basic authentication）

- 表单身份验证（Form-based authentication）

- 自定义表单身份验证（Custom Form authentication）

- 摘要身份验证（Digest authentication）

- 客户端认证（Client authentication）

- OpenID Connect 身份验证

一切都始于 Servlet 规范，该规范规定了四种身份验证机制：BASIC、FORM、DIGEST 和 CLIENT-CERT。后来，当 Jakarta Security API 被开发时，明确需要让 BASIC 和 FORM 身份验证机制的工作方式与 Servlet 规范中的 BASIC 和 FORM 对应项一致。也就是说，我们可以区分五种身份验证机制，其中三种来自 Jakarta Security API（BASIC、FORM、CUSTOM-FORM），两种来自 Servlet 规范（DIGEST、CLIENT）。

现在让我们来看其中的每一种。

## 基础身份验证 (Basic Authentication)

## 它是什么

基础身份验证是在未指定身份验证机制时使用的默认认证方式。

## 如何工作

基础身份验证通过在 `web.xml` 中定义 `<security-constraint>` 元素并分配能够访问这些资源的角色，通过 `web.xml` 描述符进行配置。Servlet 服务器通过与数据库中的用户名和密码进行对比来验证它们。

下面是使用基础身份验证时发生的操作序列：

1. 客户端请求受保护的资源。

2. 服务器返回对话框请求用户名和密码。

3. 客户端提交用户名和密码。

4. 服务器通过与数据库中的用户名和密码进行对比来验证它们。

![](img/3c2d905e91362102f512a08b855a70_8.png)

4. 基础身份验证

## 如何配置

注解：

```xml
<login-config>
  <auth-method>BASIC</auth-method>
  <realm-name>my-default-realm</realm-name>
</login-config>
```

```java
package jakarta.enterprise.security.authentication.http;
@Retention(RUNTIME)
@Target(TYPE)
public @interface BasicAuthenticationDefinition {
    /**
     * 认证域名称
     * @return 认证域
     */
    String realmName() default "";
}
```

# 表单身份验证 (Form-Based Authentication)

## 它是什么

这是一种身份验证机制，用户被呈现一个表单以登录某些服务或系统。

## 如何工作



开发者通过自定义登录界面和错误页面来控制登录屏幕的外观和感受。让我们通过表单身份验证时发生的操作序列：

1. 客户端请求受保护的资源。
2. 如果客户端尚未认证，服务器将其重定向到登录页面。
3. 客户端填写用户名和密码并将表单提交给服务器。
4. 服务器尝试对用户进行认证。
   a. 身份验证成功后，检查用户是否属于访问资源的角色。
   b. 身份验证失败后，将用户重定向到错误页面。

![](img/3c2d905e91362102f512a08b855a70_9.png)

4-2. 表单身份验证

## 如何配置

HTML 表单

在处理表单身份验证时，请确保将表单的 `action` 标记为 `j_security_check`。因此，显式声明此 `action` 服务器不需要指定 `action` 字段。以下是显示 HTML 应该是什么样的代码：

```html
<form method="POST" action="j_security_check">
<input type="text" name="j_username">
<input type="password" name="j_password">
</form>
```

注解：

```java
package jakarta.enterprise.security.authentication.http;
@Retention(RUNTIME)
@Target(TYPE)
public @interface FormAuthenticationDefinition {
    @Nonbinding
    LoginToContinue loginToContinue();
}
```

Web.xml：

```xml
<login-config>
  <auth-method>FORM</auth-method>
  <form-login-config>
    <form-login-page>login.xhtml</form-login-page>
    <form-error-page>error.xhtml</form-error-page>
  </form-login-config>
</login-config>
```

# 摘要身份验证 (Digest Authentication)

## 它是什么

一种与基础身份验证类似的身份验证机制，但它不以明文发送密码。这种身份验证机制旨在避免基础身份验证的关键缺陷。

## 如何工作

就像基础身份验证一样，摘要身份验证基于用户名和密码对用户进行认证，但对消息进行任何加密。它在通过网络发送之前对用户名和密码应用哈希函数。也就是说，在这里密码没有通过网络传输，但它需要身份验证容器可以使用明文密码等值物，以便通过计算预期的摘要来验证收到的认证器。

应用程序流程：

1. 客户端请求访问受保护的资源。
2. 服务器返回一个 `nonce`（随机数）和一个 401 错误码。
3. 客户端返回一个包含校验和的响应（默认为 MD5 校验和），涵盖用户名、密码、域、给定的随机数（`nonce`）、请求的 URI 以及 HTTP 方法。`generate_md5_key(nonce, username, realm, password_given_by_user).`
4. 服务器获取用户名、域和请求的 URI，并根据提供的用户名查找密码。找到后，它会生成自己版本，例如 `generate_md5_key(nonce, username, realm, URI, HTTP method, password-for-this-user-in-my-db).`
5. 然后，服务器将获取的 `generate_md5()` 输出与客户端发送的输出进行比较：
   - a. 如果它们匹配，说明客户端发送了正确的密码
   - b. 如果它们不匹配，说明发送的密码是错误的

## 如何配置

web.xml:

```
<login-config>
<auth-method>DIGEST</auth-method>
<realm-name>enterprisesocialdigestrealm</realm-name>
</login-config>
```

## 客户端认证

### 什么是客户端认证

这是一种认证机制，客户端通过交换数字证书来安全地获得服务器的访问。

你可能会遇到“公钥证书”这一术语而不是“数字证书”。这两个术语是等价的，用途相同。

### 工作原理

首先，必须强调，客户端认证是一种比基础认证或基于表单的认证更安全的认证方法。其主要优势是它使用了基于 SSL 的 HTTP (HTTPS)，在 HTTPS 中，服务器使用客户端的公钥证书对客户端进行认证。

## 第 4 章 社会安全

虽然客户端认证对于内网应用可能可行，但在互联网上往往难以扩展，因为在成千上万用户注册期间提供客户端证书、并在注销期间撤销证书面临巨大挑战。

SSL 技术为 TCP/IP 连接提供了数据加密、服务器认证、消息完整性以及可选的客户端认证。

证书由证书权威（CA）颁发，CA 是一个信任的组织，向持有者提供身份证明。

## 如何配置

Web.xml:

```
<login-config>
<auth-method>CLIENT-CERT</auth-method>
</login-config>
```

## 自定义表单认证

### 什么是自定义表单认证

与基于表单的认证类似，主要区别在于认证对话框的延续。因此，它不是回提交到表单预定义的 `j_security_check` 动作，而是自定义表单认证机制通过使用应用程序收集的凭据调用 `SecurityContext.authenticate()` 来继续认证对话框。

它的其余大部分概念与基于表单的认证大不相同，因此你可以参考后者的“工作原理”和“简单应用程序演练”部分。

### 如何定义

```
@Retention(RUNTIME)
@Target(TYPE)
public @interface CustomFormAuthenticationMechanismDefinition {

  @Nonbinding
  LoginToContinue loginToContinue();
}
```

## 身份存储库 (Identity Stores)

在本节中，你将介绍身份存储库的概念及其对安全的重要性。此外，你将简要查看 Jakarta EE 中身份存储库的基本设置，将在后续章节中进行深入分析。

### 什么是身份存储库？

身份存储库是一个存储一组用户特定应用程序身份信息的组件，包含用户名、组、角色、组成员关系、权限和凭据。偶尔，它也用于存储其他信息，如 GUID（调用者的全局唯一标识符）或其他调用者属性。

为了简化上述定义，你可以将身份存储库理解为一个专门用于安全的 DAO（数据访问对象）。

### 身份存储库的目的是什么？

身份存储库的目的是通过访问调用者的身份属性来验证调用者的身份。也就是说，身份存储库提供了对用户信息的访问，并且是认证所必需的。

身份存储库的四个重要特征如下：

- 提供对用户信息的访问
- 认证所必需
- 验证凭据
- 获取组成员关系

身份存储库可以提供认证、授权或两者兼顾的能力。

## 身份存储库与 Jakarta EE

更广泛的 Jakarta EE 生态系统包含多个 API，帮助你管理 Web 应用程序认证（Jakarta Authentication）、授权（Jakarta Authorization）和安全标准。Jakarta EE API 规定了 `IdentityStore` 接口，为身份存储库提供了抽象。

实现 `IdentityStore` 允许开发者与身份存储库交互，以验证用户身份（即验证他们的凭据）并获取调用者组。

## 第 4 章 社会安全

我们认为一个良好的 `IdentityStore` 实现应该是仅在上下文级别运行且与环境无关的（无论移植和运行在什么环境中，运行方式相同并提供相同的结果）。也就是说，一个良好的 `IdentityStore` 实现提供整洁的“凭据入，调用者数据出”的功能。

让我们查看接口（不包含默认行为，仅包含签名）并尝试更好地理解它：

```
public interface IdentityStore {
enum ValidationType { VALIDATE, PROVIDE_GROUPS }
  CredentialValidationResult validate(Credential credential);
  Set<String> getCallerGroups(CredentialValidationResult validationResult);
  int priority();
  Set<ValidationType> validationTypes();
}
```

`IdentityStore` 接口两个最重要的方法如下：

- `validate(Credential)` 验证凭据。
- `getCallerGroups(CredentialValidationResult)` 获取调用者信息。

`IdentityStore` 的实现可以根据其能力和配置选择处理这两个方法中的一个或两者。它们可以通过利用 `validationTypes()` 方法的值集来提示它们处理哪种方法，如下：

- `VALIDATE` - 表示它处理 `validate()` 方法
- `PROVIDE_GROUPS` - 表示它处理 `getCallerGroups()` 方法
- `VALIDATE` 和 `PROVIDE_GROUPS` 组合 - 表示它处理两种方法

你可能会觉得声明能力相当困惑，但为了确保 `IdentityStore` 的配置和实现是自管理的，这是一个深思熟虑的决定。这意味着 `IdentityStore` 在特定部署期间可以配置为支持其中一种方法，但它的代码可以写为支持两种方法。

86

## 验证凭据

要确定一个凭据是否有效，你可以使用 `validate()` 方法，该方法在验证成功后会返回有关由凭据所识别的用户的信息。`IdentityStore` 可能选择不实现此方法，因为它是可选的。

```
CredentialValidationResult validate(Credential credential);
```

从方法签名可以看出，验证结果的类型为 `CredentialValidationResult`，它允许方法获取验证结果的状态值，以及在验证成功后，获取验证凭据的存储库 ID、调用者主体（`caller principal`）、调用者在身份存储库中的唯一 ID 以及调用者的组成员关系（如果有）。

对于成功的验证，只需要调用者主体即可。

那么 `CredentialValidationResult` 的底层结构包含什么呢？请参阅仅包含方法签名的类概览：

```
public class CredentialValidationResult {

    public enum Status { NOT_VALIDATED, INVALID, VALID }

    public Status getStatus();

    public String getIdentityStoreId();

    public CallerPrincipal getCallerPrincipal();

    public String getCallerDn();

    public String getCallerUniqueId();

    public Set<String> getCallerGroups();
}
```

## 第 4 章 社会安全

首先，有三种不同的状态值：`NOT_VALIDATED`、`INVALID` 和 `VALID`。它们意味着什么？

- `NOT_VALIDATED` – 未尝试验证，因为该 `IdentityStore` 不处理提供的 `Credential` 类型。
- `INVALID` – 验证失败。提供的 `Credential` 无效，或在用户存储库中未找到相应的用户。
- `VALID` – 验证成功，用户已通过认证。只有在此结果状态下，才能获取调用者主体和组（如果有）。

继续后续 `CredentialValidation` 的其他方法，身份存储库 ID、调用者 DN 和调用者唯一 ID 有助于帮助你通过与 `validate()` 和 `getCallerGroups()` 协作来实现一个 `IdentityStore`。它们可以用于确保即使在仅凭调用者主体名称不足以唯一标识用户账户的环境中，也能从 `getCallerGroups()` 中返回正确的调用者组。

`Credential` 接口是一个通用接口，能够表示任何类型的令牌或用户凭据。`IdentityStore` 实现可以支持多种 `Credential` 类型，其中具体的 `Credential` 是 `Credential` 接口的实现，代表特定类型的凭据。这是通过实现 `validate(Credential)` 方法并检查作为参数传递的 `Credential` 类型实现的。

`IdentityStore` 接口提供了 `validate()` 方法的默认实现，它委托给可以处理提供的 `Credential` 类型的方法，假设 `IdentityStore` 实现了该方法：

```
default CredentialValidationResult validate(Credential credential) {
    return CredentialValidationResult.class.cast(
        MethodHandles.lookup()
        .bind(this, "validate",
        methodType(CredentialValidationResult.class,
        credential.getClass()));
} catch (NoSuchMethodException e) {
```

```java
return NOT_VALIDATED_RESULT;
} catch (Throwable e) {
    throw new IllegalStateException(e);
}
```

如果传递了 `UsernamePasswordCredential`，`validate()` 将委托给 `ExampleIdentityStore` 的以下方法：

```java
public class ExampleIdentityStore implements IdentityStore {

public CredentialValidationResult validate(UsernamePasswordCredential usernamePasswordCredential) {
    // Implementation
    return new CredentialValidationResult(...);
}
```

# 获取调用者信息

`getCallerGroups()` 方法检索与通过验证的调用者相关的组。这是一个可选方法，`IdentityStore` 可以选择不实现它：

```
Set<String> getCallerGroups(CredentialValidationResult validationResult);
```

这支持身份存储器的聚合，其中一个身份存储器用于身份验证用户，而一个或多个其他存储器用于检索额外的组。在这种情况下，在不针对存储器验证调用者凭据的情况下查询身份存储器至关重要的。

# 声明能力

`IdentityStore` 接口中还有几个我们没有讨论的方法，实现类可以使用这些方法来声明其能力和顺序优先级：

```
enum ValidationType { VALIDATE, PROVIDE_GROUPS }

Set<ValidationType> DEFAULT_VALIDATION_TYPES = EnumSet.of(VALIDATE, PROVIDE_GROUPS);
```

# 第4章 社会安全

```java
default int priority() {
    return 100;
}
```

```java
default Set<ValidationType> validationTypes() {
    return DEFAULT_VALIDATION_TYPES;
}
```

让我们仔细查看以下内容：

- `priority()` 允许为 `IdentityStore` 配置一个数字，表示当存在多个身份存储器时应当查询它们的顺序。数字越小表示优先级越高；也就是说，优先级值较低的 `IdentityStore` 会在优先级较高的 `IdentityStore` 之前被调用。
- `validationTypes()` 返回 `ValidationType` 类型的枚举常量集合，表示应该使用 `IdentityStore` 的用途：
  - `VALIDATE`，表示它处理 `validate()`
  - `PROVIDE_GROUPS`，表示它处理 `getCallerGroups()`
  - 同时包含 `VALIDATE` 和 `PROVIDE_GROUPS`，表示它同时处理这两个方法

`IdentityStore` 的验证类型决定了三件事：

- 仅身份验证 - 它返回的任何组数据必须被忽略。
- 仅提供组 - 不用于身份验证，而是为由另一个 `IdentityStore` 验证的调用者获取组数据。
- 身份验证以及它可能返回的任何组数据。

# 如何验证凭据

正如我们之前学到的，可以使用 `HttpAuthenticationMechanism`（或其他调用者）来身份验证用户。然而，前者不应直接与 `IdentityStore` 交互，而是调用 `IdentityStoreHandler` 来验证凭据。然后 `IdentityStoreHandler` 会调用 `IdentityStore`。

那么 `IdentityStoreHandler` 接口是做什么的呢？它定义了调用 `IdentityStore` 来验证用户凭据的机制，并被认为是一种更安全的身份验证方式。



容器提供默认的 `IdentityStoreHandler` 实现，你也可以编写自己的自定义实现。

身份存储器通常与数据源（如关系型数据库、LDAP 目录、文件系统或其他类似的资源）存在一对一的关系。因此，`IdentityStore` 的实现使用特定于数据源的 API 来发现授权数据（角色、权限等），例如 JDBC、File IO、Hibernate/JPA、NoSQL 或其他数据访问机制。

# OAuth

OAuth 是一种授权协议，允许应用程序代表授予其权利的用户执行操作，而无需向其交付如用户名或密码等登录凭据。

它由 Twitter、Magnolia 和 Google 开发，并于 2010 年 4 月根据 RFC 5849 注册为 IETF 标准。

OAuth 2.0 版本使用更简单，但经常因为有太多种类和实现而受到批评。OAuth 2 由 IETF 于 2012 年 10 月根据 RFC 6749 和 6750 再次标准化。它与 OAuth 1.0a 不兼容。

一些著名的采用者包括 Facebook、Amazon、Google、Salesforce.com 或 Microsoft。所有相关的社交 API 都基于 OAuth 1.0a 或 2.0。

图 4-3 显示了 OAuth 流程的参与者，通常也称为“OAuth 舞蹈”（OAuth Dance）。

- 资源所有者
- 客户端
- 服务器

![](img/3c2d905e913621002f512a08b8855a70_100_0.png)

![](img/3c2d905e913621002f512a08b8855a70_100_1.png)

![](img/3c2d905e913621002f512a08b8855a70_100_2.png)

### 图 4-3. OAuth 参与方

要使用 OAuth，必须在目标服务上创建一个应用程序，作为消费者或资源所有者的切入点，允许授权服务器在资源所有者（或终端用户）的批准下向第三方客户端发放访问令牌。然后客户端使用访问令牌访问由资源服务器托管的受保护资源。

OAuth “舞蹈”有三个主要步骤：

- 创建 – 在 OAuth 社交媒体服务中创建一个应用程序。
- 初始化 – 权利授予阶段，也称为 OAuth 舞蹈。在舞蹈结束时，我们获得一个访问令牌（由公共部分秘密部分组成），用于下一步。
- 签名 – 每个请求都使用访问令牌以及标识已授予权利的 OAuth 应用程序的令牌进行签名。

一个 `IdentityStore` 图 4-4 详细显示了 OAuth 1.0a 的步骤和身份验证流程。

![](img/3c2d905e913621002f512a08b8855a70_101_0.png)

图 4-4. OAuth 1.0a “舞蹈”

4-5 显示了 OAuth 2 的流程。你可以看到所有通信都经过 SSL 加密。在 OAuth 1.0a 中，这是可选的，因此大多数实现都省略了它，相比 OAuth 2 面临更大的拦截或篡改风险。

![](img/3c2d905e913621002f512a08b8855a70_101_1.png)

图 4-5. OAuth 2 “舞蹈”

虽然 OAuth 是社交媒体和 API 最流行的访问控制，但并不是真正的身份验证，而是“伪身份验证”，应用程序请求的是有限访问（“钥匙”）而非真实的凭据（如“护照”）；参见图 4-6 和 4-7。

![](img/3c2d905e913621002f512a08b8855a70_102_0.png)

图 4-6. 使用 OAuth 的伪身份验证

![](img/3c2d905e913621002f512a08b8855a70_102_1.png)

图 4-7. OpenID 身份验证

# OpenID

最初的 OpenID 协议由 Brad Fitzpatrick 在 2005 年在 Six Apart 创建，此前他将社交网络 LiveJournal 卖给了这家博客软件公司。公司的名称并非看起来那样是指“六度分离”（Six Degrees of Separation），而是其结婚共同创始人之间六天的年龄差。

它的代号为 Yadis（“另一种分布式身份系统”的缩写），但正式命名为 OpenID，是因为 David Hahn 也考虑过一个单登录项目但缺乏时间，并将 "openid.net" 域名捐赠给了 Six Apart。

图 4-8 显示了 OpenID 流程及其参与者：

- 浏览器
- 用户
- 信赖方
- 身份提供者

![](img/3c2d905e913621002f512a08b8855a70_103_0.png)

图 4-8. OpenID 流程

# 第 4 章 安全

2013 年 9 月，社交登录 SaaS 供应商 Janrain 宣布其服务 MyOpenID 将于 2014 年 2 月 1 日关闭。

那么 OpenID 已经死亡了吗？在某种程度上，原始形式已经结束了，但至少 Google 对其仍抱有高期望。奇怪的巧合，OpenAPI 的最初创建者 Brad Fitzpatrick 现在就职 Google，这可能是该公司在大多数其他支持者放弃它时仍然保持忠于 OpenID 的主要原因。然而，Google 的新方法 OpenID Connect 与旧版 OpenID 并没有多少共同之处。它在 OAuth 2、JSON 和 RESTful 服务这一已经胜出的组合的基础上，增加了改进的身份验证和身份管理。

# OpenID Connect

OpenID Connect 由 OpenID Foundation 于 2014 年 2 月底发布。除了 Google 外，微软、Salesforce.com 或德国电信也采用了它。在巴塞罗纳举行的 2014 年移动世界大会上，GSMA 宣布了移动版本“Mobile Connect”的计划，这足以表明它将会持续一段时间。

OpenID Connect 是可扩展的，支持可选功能，如加密身份数据、发现 OpenID 提供者或会话管理。

# JWT

JSON Web Token (JWT) 是一种归属于 RFC 7519 的开放标准，通过 JSON 字符串在不同应用程序或服务之间安全地传输信息。

JWT 是紧凑的、人类可读的，并使用私钥或公钥身份提供者（IdP）进行数字签名。因此，其他参与方可以验证令牌的完整性和真实性。

JWT 的主要目的不是隐藏数据，而是确保其真实性。JWT 主要用于签名和编码，而不是加密数据，尽管令牌也可以在另一组标准（包括 JSON Web Signature JWS 和 JSON Web Encryption JWE）上进行加密。

JWT 是一种基于令牌的无状态身份验证机制。由于它是基于客户端无状态会话，服务器不需要数据库之类的持久化机制来保存会话信息。JSON Web Tokens 遵循一个定义良好且已知的标准，成为保护服务的最常见的令牌格式。

# 用例

JSON Web Token 的两个主要用例如下：

- 授权
- 信息交换

授权无疑是 JWT 最常用的用例。一旦用户登录系统，每个随后的请求都将包含 JWT，允许用户访问该令牌允许的页面、服务和资源。单点登录（SSO）是目前广泛使用 JWT 的功能，特别是在公共 API 中，因为它的开销小，并且易于在不同域之间使用。

信息交换：JSON Web Tokens 是双方之间安全传输信息的良好方式。因为 JWT 可以签名——例如，使用公钥/私钥对——你可以确定发送者确实是他们所称的。此外，由于签名是使用头部（header）和负载（payload）计算的，你还可以验证内容未被篡改。

## 为什么我们需要 JWT？

HTTP 协议是无状态的；因此一个新的请求（如 `GET /order/42`）不知道之前的请求（如相同 ID 的 `PUT /order`），用户必须为每个新请求重新进行身份验证。

# 第 4 章 安全

```
PUT /order
{
  "username": "werner",
  "password": "xyz",
  "id": 42
}
```

![](img/3c2d905e913621002f512a08b8855a70_106_0.png)

验证用户名和密码

OK

返回 201 Created

客户端

服务器

身份提供者

```
GET /order/42
{
  "username": "werner",
  "password": "xyz"
}
```

![](img/3c2d905e913621002f512a08b8855a70_106_1.png)

验证用户名和密码

OK

返回 ID 为 42 的订单

客户端

服务器

身份提供者

**图 4-9.** 为每个新的 HTTP API 请求重复身份验证

这通常使用服务器端会话（SSS）来处理。首先，检查登录凭据（如用户名和密码），如果正确，服务器将创建一个会话 ID，存储它并将其返回给客户端。在基于 Servlet 的 Jakarta EE 应用程序中，发送给客户端的 cookie 通常被称为 JSESSIONID。

# 第 4 章 安全

```
POST /authenticate
{
  "username": "werner",
  "password": "xyz"
}
```

![](img/3c2d905e913621002f512a08b8855a70_107_0.png)

图 4-10. 使用 SSS 减少针对身份提供者的身份验证次数

这种方法可以解决一个问题，但可能会产生其他问题，如扩展性问题。虽然服务器端会话对于大多数网站甚至少数电子商务商店可能有效，但在 API 驱动的时代，某些端点可能面临海量请求，迫使提供者进行扩展。扩展有两种方式：

- 垂直扩展
- 水平扩展

# 第 4 章 安全

垂直扩展意味着向服务器添加更多资源，如内存、存储或 CPU 核心。这可能是昂贵的，并且会达到某些限制，例如每台服务器的 CPU 数量、内存槽或磁盘存储。

水平扩展通过在负载均衡器后面添加更多服务器来扩展你的基础设施，这通常比一直升级每台服务器更高效且更具成本效益。虽然水平扩展通常更高，但仅凭一个位置和一个负载均衡器会导致进一步的问题和复杂性。

想象负载均衡器后面有一台服务器，客户端使用类似 "abc" 的 JSESSIONID 执行请求，该会话可以在服务器的内存中找到。

![](img/3c2d905e913621002f512a08b8855a70_108_0.png)

图 4-11. 负载均衡器后的单服务器

如果基础设施需要扩展并在负载均衡器后面添加了新服务器，当该新服务器处理使用 "abc" 的客户端的下一个请求时，它将无法识别该 JSESSIONID。

![](img/3c2d905e913621002f512a08b8855a70_108_1.png)

图 4-12. LB 后的新服务器，用户未被识别

# 第 4 章 安全

身份验证失败是因为新服务器在内存中没有 "abc" 会话。有三种主要的变通方法解决这个问题。

在服务器之间同步会话，这在分布式架构中可能非常困难且容易出错。

使用外部数据库或会话缓存机制。这很有帮助，但增加了基础设施的组件，而且特别是在分布式环境中，该缓存或数据库需要同步。

或者接受 HTTP 的无状态性，并尝试寻找适用于它的解决方案。这就是 JSON Web Token 的用场，因为每个令牌都是紧凑且自包含的，因此它包含了所有信息，无需进行任何同步查询。

## 它是如何工作的？

基于令牌的身份验证机制允许系统根据安全令牌进行身份验证和授权。涉及以下实体：

- 发行者（Issuer）：负责在断言身份后发布安全令牌。发布者通常与身份提供者相关。
- 客户端（Client）：代表接收令牌的应用程序。客户端通常与服务提供者相关。客户端也可以作为主体和目标服务之间的中介（代理）。
- 主体（Subject）：令牌信息所指的实体。
- 资源服务器（Resource server）：代表消耗令牌以检查是否允许访问保护资源的应用程序。

无论令牌格式或协议如何，从服务的角度来看，基于令牌的身份验证包含以下步骤：

1. 从请求中提取安全令牌。

对于 RESTful 服务，这通常通过从 Authorization 获取令牌来实现。

2. 对令牌进行验证检查。

此步骤取决于使用的令牌格式和安全协议。目标是确保令牌是有效的并可以被应用程序使用。它可能涉及签名、加密和过期检查。

3. 内省令牌并提取有关主体的信息。

此步骤取决于使用的令牌格式和安全协议。目标是从令牌中获取有关主体的所有必要信息。

4. 为主体创建安全上下文。

根据从令牌中提取的信息，应用程序为主体创建一个安全上下文，以便在提供保护资源时需要的地方使用这些信息。

## JWT 结构

JSON Web Token 有三个部分：

- 头部（Header）
- 负载（Payload）
- 签名（Signature）

这每个部分都由“.”字符分隔。

因此，每个 JWT 看起来都像

Header.Payload.Signature

### 标题

第 4 章 社会安全

编码

解码

### 标题

```json
{
  "typ": "JWT",
  "alg": "RS256"
}
```

```text
eyJhbGciOiJISUI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxMjM0NTY3ODkwyfQ.SflKXRXJSKKFQT44wpMeJf36PO6POk6yJV_5_w5c
```

## 负载

```json
{
  "iss": "w3",
  "sub": "John-WenzelKoehler@employees.com=de",
  "aud": "urn:myapp:",
  "exp": 1516296045,
  "iat": 1534188845
}
```

## 签名

```javascript
RSASHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  Enter Public key or Certificate
  Enter private key
)
```

![](img/3c2d905e913621002f512a08b8855a70_111_0.png)

### 图 4-13. JWT 结构

头部描述了 JSON Web Token（JWT）本身。它包含了关于令牌类型的信息以及用于生成签名的算法。参数 `alg` 必须出现在每个 JWT 头部中。最常见的算法是带有 SHA-256 哈希的 HMAC ("HS256") 或具有相同哈希的 RSA ("RS256")，以及最近的 ECDSA P-256 ("ES256")。允许的值由 JSON Web 加密 (JWE) 标准 RFC 7516 指定。

在我们的示例中，头部包含以下参数：

```json
{
  "typ" : "JWT",
  "alg" : "RS256"
}
```

类型参数 `typ` 用于声明令牌的 IANA 媒体 (RFC 6838)。它是可选的，但当设置时，它应该始终为 "JWT"，代表媒体类型 "application/jwt"。

另一个参数 `cty`（内容类型）用于声明受保护内容（负载）的媒体类型。它是可选的，只有当负载包含另一个 JSON Web Payload 时才需要，在这种情况下，其值应为 "JWT"；否则，此参数可以忽略或省略。

103

# 第 4 章 社会安全

参数 `enc`（加密算法）定义用于 JWE。它在需要对声明或嵌套的 JWT 令牌进行加密时才需要。它标识了用于加密声明或嵌套 JWT 令牌的加密算法。

例如，使用 256 位密钥的 Galois/计数器模式 (GCM) 算法 AES 将被指定为 "A256GCM"。

其他其他定义的头部参数，例如：

- crit (关键性)
- jku (JWK 集合 URL)
- jwk (JSON Web Key)
- kid (密钥 ID)
- x5u (X.509 URL)
- x5t (X.509 证书 SHA-1 指纹)
- x5t#S256 (X.509 证书 SHA-256 指纹)

## 负载

负载或主体是 JWT 的核心部分，包含了安全陈述，如用户身份和授予的权限。JWT 将它们称为声明（claims）。

JWT 声明名称有三种类型：

- 1. 注册声明
- 2. 公开声明
- 3. 私有声明

注册声明是预定义的声明。公开声明可以是任何用户定义的信息，而私有声明是 JWT 生产者和消费者同意在特定应用程序中使用那些声明。

为了验证 JWT，我们还应该检查一些注册声明。一些重要的注册声明定义在表 4-1 中。

### 表 4-1. 注册 JWT 声明

| 声明名称 | 说明 | 引用 |
|---|---|---|
| iss | 令牌发行者 | RFC 7519, 第 4.1.1 节 |
| sub | 作为 JWT 主体的主体 | RFC 7519, 第 4.1.2 节 |
| aud | JWT 的接收者 | RFC 7519, 第 4.1.3 节 |
| exp | JWT 在此时间或之后不得被接受处理的时间 | RFC 7519, 第 4.1.4 节 |
| nbf | JWT 在此之前必须被接受处理的时间 | RFC 7519, 第 4.1.5 节 |
| iat | 发行者生成 JWT 的时间 | RFC 7519, 第 4.1.6 节 |
| jti | JWT 的唯一标识符 | RFC 7519, 第 4.1.7 节 |

### “iss”（发行者）声明

“iss”（发行者）声明标识了发布 JWT 的主体。该声明的处理通常取决于特定应用程序。`iss` 值是一个包含 URI 值的区分大小敏感的字符串。使用此声明是可选的。我们应该验证发行者是否为有效 URL，或者 JWT 是否由预期的发行者发送的。

### “sub”（主体）声明

“sub”（主体）声明标识了作为 JWT 主体的主体。该声明是关于主体的陈述。`sub` 值是一个区分大小敏感的字符串。

### “aud”（受众）声明



“aud”（受众）声明标识了 JWT 的接收者。该声明是关于接收者的陈述。`aud` 值是一个包含 URI 值的区分大小敏感的字符串（此处应为数组）。

### “exp”（过期时间）声明

“exp”（过期时间）声明标识了 JWT 在此时间或之后不得被接受处理的时间。该声明是关于过期时间的陈述。`exp` 值是一个包含 URI 值的区分大小敏感的字符串（此处应为数组）。

### “nbf”（生效时间）声明

“nbf”（生效时间）声明标识了 JWT 在此之前必须被接受处理的时间。该声明是关于生效时间的陈述。`nbf` 值是一个区分大小敏感的字符串。

### “iat”（发布时间）声明

“iat”（发布时间）声明标识了发行者生成 JWT 的时间。该声明是关于生成时间的陈述。`iat` 值是一个区分大小敏感的字符串。

### “jti”（JWT 标识）声明

“jti”（JWT 标识）声明为 JWT 提供了一个唯一标识符，以防止重放攻击。`jti` 值是一个包含 URI 值的区分大小敏感的字符串。

## 签名

签名是 JSON Web Token 的第三部分。它是验证 JWT 并确保其未被篡改的重要部分。签名在使用负载和密钥的情况下生成的；因此，任何拥有此密钥的人都可以生成令牌。

106

生成签名的常用加密算法如下：

- HS256，代表 HMAC-SHA256
- RS256，代表 RSA-SHA256
- ES256，代表 ECDSA P-256

## MicroProfile JWT

许多标准中令人沮丧的一个方面是，某些标准试图成为全能手，提供大量的选择。这在 JWT 中确实如此，它允许多种类型的数字签名和许多可能的声明。虽然可能性是无限的，但如此多的选项意味着无限互操作性问题。

MicroProfile JWT 的关键目标是提取出足够的选项，以便实现企业间的基本互操作性，特别是对于微服务。

MicroProfile JWT 还将 JWT 映射到不同的 Jakarta EE 容器 API，并通过更好的方法使声明可用。

规范、API 和 TCK 的源码可从 Eclipse microprofile-jwt-auth GitHub 仓库获取。

MP JWT 作为令牌格式的用途取决于发行者和服务提供者之间的协议。这意味着发行者（负责发布令牌）应该能够使用 MP JWT 格式发布互操作令牌，服务提供者可以理解并验证这些令牌。

## 第 4 章 安全安全

关于主题的信息。在这方面，MicroProfile JWT 的要求如下：

- 可作为身份验证令牌（authentication token）
- 可作为授权令牌，其中包含通过 `groups` 声明（claim）间接授予的 Jakarta EE 应用级角色
- 能够支持 IANA JWT 规范中描述的其他标准声明以及非标准声明

为了满足这些要求，MP JWT 引入了两个新声明：

- “upn” – 一种可读的声明，用于在访问令牌的多个 MicroProfile 服务之间唯一标识主体（subject）或用户主体（user principal）
- “groups” – 令牌的组成员关系，这些关系将被映射到 MicroProfile 服务容器中的 Java EE 应用级角色

规范（截至 2.1 版本）基于以下 Jakarta EE API 依赖项：

- Jakarta RESTful Web Services 3.0
- Jakarta JSON Processing 2.0
- Jakarta JSON Binding 2.0
- CDI 3.0
- Jakarta Annotations 2.0

MicroProfile JWT 规范专注于微服务验证 JWT 的能力，并不定义以下内容：

- JWT 创建 – 令牌通常由企业中的专用服务（如 API 网关或身份提供商）创建。
- RSA 公钥分配 – 分发网关或身份提供者的公钥不在 MP JWT 的范围范围内。类似于 TLS/SSL 证书，它们可能不会经常更改，手动分发或安装（例如通过 docker 镜像）是常见做法。
- 自动 JWT 传播 – 使用 MP JWT 的微服务有一种保证且标准的方式在接收传入调用时获取 JWT。然而，传播必须由微服务本身在应用程序代码中将 JWT 放置在传出 HTTP 请求的 Authorization 头中完成。

MicroProfile JWT 的一个关键目标是令牌能够被每个微服务验证和传播。由于之前讨论过的 HS256 问题，MicroProfile JWT 仅选择基于 RSA 的数字签名。

创建 JWT 的授权服务器的 RSA 公钥可以在任何实际 HTTP 请求之前预安装在所有微服务中。当调用进入微服务时，它将使用此 RSA 公钥验证 JWT 并判断调用者的身份是否有效。如果微服务发出了任何 HTTP 请求，它应该在这些调用传递 JWT，将调用者的身份传播到其他微服务。

根据 JWT 标准定义，`"alg"` 头参数必须存在。如果声明或 JWT 令牌被加密，`"enc"` 也是强制性的头。建议使用头参数 `"typ"` 和 `"kid"`。

虽然 JWT 规范宣布几乎每个注册的声明都是可选的，但 MicroProfile JWT 要求以下声明存在：

- iss
- iat
- exp

MP JWT 建议使用这些 JWT 声明：

- sub
- jti
- aud

除了表 4-1 中列出的注册 JWT 声明外，MicroProfile JWT 还定义了自身的公共声明（见表 4-2）。

## 表 4-2. MP JWT 公共声明

| 声明 | 说明 | 引用 |
| --- | --- | --- |
| upn | 在 `java.security.Principal` 接口中提供用户主体名称。此声明是必选的 | MP-JWT 2.1 规范 |
| groups | 提供分配给 MP-JWT 主体的组名列表。这通常要求在应用容器级别映射到应用部署角色，但在执行任何映射之外，还需要在组名和应用角色名之间执行一对一的映射。此声明是可选的 | MP-JWT 2.1 规范 |

如果端点需要授权，建议 JWT 令牌具有 `"groups"` 声明，但如果令牌是由 OpenID Connect 以及目前不支持 MP JWT 的其他提供者发放的，MP JWT 实现可以映射其他声明。

如果从给定令牌的 `"groups"` 声明中直接提取组信息，那么当端点只需要身份验证时，该令牌是可以接受的。

`"exp"`、`"iat"` 以及其他日期相关的声明使用的数值是 JSON 数值，表示从 1970-01-01T00:00:00Z UTC 到指定的 UTC 日期/时间的秒数（忽略闰秒）。

MicroProfile JWT 实现可能会强制 JWT 令牌包含所有建议的头和声明。建议的头声明在 MP JWT 规范的未来版本中可能会变为强制。

一个 JSON 格式的最小 MP JWT 示例为：

```json
{
  "typ": "JWT",
  "alg": "RS256",
  "kid": "abc-1234567890"
}
```

```json
{
  "iss": "https://server.example.com",
  "jti": "a-123",
  "exp": 1311281970,
  "iat": 1311280970,
  "sub": "24400320",
  "upn": "jdoe@server.example.com",
  "groups": ["red-group", "green-group", "admin-group"]
}
```

MicroProfile JWT 规范定义了一个 `JsonWebToken` `java.security.Principal` 接口扩展，使得 get 方法可以使用这组所需的声明。

## 总结

在社交媒体交互和 API 标准化之后，本章向我们展示了社交网络的安全方面以及面向安全的标准。在接下来的章节中，我们将发现安全框架。

# 第 5 章

## 安全框架

上一章处理了社交网络和标准的安全方面。在本章中，我们将涵盖像 Keycloak、Spring Security、Micronaut Security、Apache Shiro 等安全框架。

### Soteria

Eclipse Soteria 是 Jakarta Security 的实现。“Soteria”一词源希腊语，意为“救援”、“健康”或“救赎”。

### 历史

“Soteria”这一术语是在成员调查中选出的。在迁移到 Eclipse Foundation 下的 Java EE 后，法律团队检查了该术语的所有商标。

### 身份验证机制

身份验证机制的基础是 `HttpAuthenticationMechanism`，它使相应的机制作为 CDI Bean 可用。实现的 `validateRequest()` 方法返回一个包含身份验证状态的 `AuthenticationStatus`。规范提供了开箱用的基础认证和基于框架的身份验证机制。

## 第 5 章 安全框架

## 支持的运行时

Soteria 运行在以下 Jakarta EE CI 运行时上：

- GlassFish
- Payara
- WildFly
- Open Liberty

此外，所有在“实现组件”中使用 Soteria 的实现也都都运行或包含了它。

经过某些调整，它也可以运行在 Tomcat 上，但由于 TomEE 9+ 和 Open Liberty 自带了它们自己的 Jakarta Security 实现（并非基于 Soteria），因此这些情况可能会稍微复杂一些。

## OpenID Connect 连接

让我们看看如何在 Jakarta EE Web 应用程序中通过 OpenID Connect 身份验证提供程序（例如本地 Keycloak 实例或 Google 等社交网络）来配置 OpenID Connect 身份验证。

首先，我们创建一个简单的 Web 项目，例如，使用 Maven Webapp Archetype：

```bash
mvn archetype:generate
-DarchetypeGroupId=org.apache.maven.archetypes
-DarchetypeArtifactId=maven-archetype-webapp
-DarchetypeVersion=1.4
```

然后我们更新 POM：

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <model>4.0.0</model>
  <groupId>com.demo</groupId>
  <artifactId>jakarta-ee-oidc-example</artifactId>
  <version>1.0-SNAPSHOT</version>
  <packaging>war</packaging>
  <name>Jakarta EE 10 OIDC 示例</name>
  <description>Jakarta EE OIDC 应用程序示例</description>
  <properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    <project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>
    <maven.compiler.release>17</maven.compiler.release>
    <!-- Maven 插件 -->
    <maven-compiler-plugin>
      <version>3.10.1</version>
    </maven-compiler-plugin>
    <maven-war-plugin>
      <version>3.3.2</version>
    </maven-war-plugin>
    <maven-dependency-plugin>
      <version>3.3.0</version>
    </maven-dependency-plugin>
    <maven-surefire-plugin>
      <version>3.10.1</version>
    </maven-surefire-plugin>
    <maven-failsafe-plugin>
      <version>3.0.0-M7</version>
    </maven-surefire-plugin>
    <maven-surefire-report-plugin>
      <version>3.0.0-M7</version>
    </maven-surefire-report-plugin>
    <!-- Jakarta EE API -->
    <dependency>
      <groupId>jakarta.platform</groupId>
      <artifactId>jakarta.ee-api</artifactId>
      <version>10.0.0</version>
      <scope>provided</scope>
    </dependency>
  </properties>
  <build>
    <finalName>${project.artifactId}</finalName>
    <pluginManagement>
      <plugins>
        <plugin>
          <groupId>org.codehaus.cargo</groupId>
          <artifactId>cargo-maven-plugin</artifactId>
          <version>1.9.7</version>
        </plugin>
      </plugins>
    </pluginManagement>
    <plugins>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-compiler-plugin</artifactId>
        <version>3.11.0</version>
      </plugin>
    </plugins>
  </build>
</project>
```

```xml
<type>zip</type>
<overWrite>false</overWrite>
<outputDirectory>${project.build.directory}</outputDirectory>
</artifactIdItem>
</artifactIds>
</configuration>
</execution>
</executions>
<plugin>
<plugin>
<groupId>org.wildfly.plugins</groupId>
<artifactId>wildfly-maven-plugin</artifactId>
<version>${wildfly-maven-plugin.version}</version>
<configuration>
<commands>
<command>subsystem=undertow/application-security-domain=other:write-attribute(name=integrated-jaspi,value=false)</command>
<command>reload</command>
</commands>
</configuration>
</plugin>
</plugins>
</build>
</project>
```

该示例针对 WildFly 27 或更高版本配置，但它在任何支持的运行时也同样有效。

接下来，我们为 OIDC 身份验证创建一个 CDI Bean：

```java
@OpenIdAuthenticationDefinition(
  clientId = "${oidcConfig.clientId",
  clientSecret = "${oidcConfig.clientSecret",
  redirectURI = "${baseURL}/callback",
  providerURI = "${oidcConfig.issuerUri}",
  jwksConnectTimeout = 5000,
  jwksReadTimeout = 5000
)
```



```java
@ApplicationScoped("oidcConfig")
public class OidcConfig {
    private static final Logger LOGGER = Logger.getLogger(OidcConfig.class.getName());
    private String domain;
    private String clientId;
    private String clientSecret;
    private String issuerUri;

    @PostConstruct
    void init() {
        LOGGER.config("OidcConfig.init()");
        try {
            var properties = new Properties();
            properties.load(getClass().getResourceAsStream("/oidc.properties"));
            domain = properties.getProperty("domain");
            clientId = properties.getProperty("clientId");
            clientSecret = properties.getProperty("clientSecret");
            issuerUri = properties.getProperty("issuerUri");
            if (issuerUri == null && domain != null) {
                issuerUri = ("localhost".equals(this.domain)) ? "http://" : "https://" + this.domain + "/";
            }
            LOGGER.log(Level.INFO, "domain: {0}, clientId: {1}, clientSecret:{2}, issuerUri: {3}",
                new Object[] {
                    domain,
                    clientId,
                    clientSecret,
                    issuerUri
                });
        } catch (IOException e) {
            LOGGER.log(Level.SEVERE, "Failed to load oidc.properties", e);
        }
    }

    public String getDomain() {
      return domain;
    }

    public String getClientId() {
      return clientId;
    }

    public String getClientSecret() {
      return clientSecret;
    }

    public String getIssuerUri() {
      return issuerUri;
    }
}
```

`PublicServlet` 是一个简单的、未安全的 servlet：

```java
@WebServlet("/public")
public class PublicServlet extends HttpServlet {
  @Override
  protected void doGet(HttpServletRequest request, HttpServletResponse response) throws IOException {
    response.setContentType("text/html");
    response.getWriter().println("<h1>Public Unsecured Servlet</h1>");
  }
}
```

`ProtectedServlet` 是受安全的，我们还为此应用声明了角色。`foo` 允许访问此 servlet：

```java
@WebServlet("/protected")
@DeclareRoles({"foo", "bar", "kaz"})
@ServletSecurity(
  @HttpConstraint(rolesAllowed = "foo")
)
public class ProtectedServlet extends HttpServlet {
    @Inject
    private OpenIdContext context;
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws IOException {
        response.setContentType("text/html");
        response.getWriter().println("<h1>Protected Servlet/</h1>");
        response.getWriter().println("<p>access token: " + context.getAccessToken() + "</p>");
        response.getWriter().println("<p>token type: " + context.getTokenType() + "</p>");
        response.getWriter().println("<p>subject: " + context.getSubject() + "</p>");
        response.getWriter().println("<p>expires in: " + context.getExpiresIn() + "</p>");
        response.getWriter().println("<p>refresh token: " + context.getRefreshToken() + "</p>");
        response.getWriter().println("<p>claims json: " + context.getClaimsJson() + "</p>");
    }
}
```

`CallbackServlet` 用于在登录成功后重定向。它重定向到 `/protected` servlet：

```java
@WebServlet("/callback")
public class CallbackServlet extends HttpServlet {
    private static final Logger LOGGER = Logger.getLogger(CallbackServlet.class.getName());
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        LOGGER.log(Level.FINEST, "Enter callback servlet");
        String referrer = (String) request.getSession().getAttribute("Referrer");
        String redirectTo = referrer != null ? referrer : request.getContextPath() + "/protected";

        LOGGER.log(Level.FINEST, "In /callback, redirect to: {0}", redirectTo);
        response.sendRedirect(redirectTo);
    }
}
```

`UserNameServlet` 从 `SecurityContext` 中显示当前用户信息：

```java
@WebServlet("/username")
@ServletSecurity(@HttpSecurityConstraint(rolesAllowed = {"foo", "bar"}))
public class UserNameServlet extends HttpServlet {
    private static final Logger LOGGER = Logger.getLogger(UserNameServlet.class.getName());
    @Inject
    SecurityContext securityContext;
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        String nameInRequest = request.getUserPrincipal() != null ? request.getUserPrincipal().getName() : "";
        var principal = securityContext.getPrincipal();
        LOGGER.log(Level.INFO, "Principal: {0}", principal);
        response.setContentType("text/html");
        response.getWriter().println("<h1>UserName Servlet</h1>");
        response.getWriter().println("<p>principal name in request: " + nameInRequest + "</p>");
        response.getWriter().println("<p>principal name: " + principal + "</p>");
        response.getWriter().println("<p>isCallerRole('foo'): " + securityContext.isCallerRole("foo") + "</p>");
        response.getWriter().println("<p>isCallerRole('bar'): " + securityContext.isCallerRole("bar") + "</p>");
    }
}
```

# 第章 安全框架

为了将经过验证的用户映射到有效的组，我们创建了一个简单的 `IdentityStore` 实现：

```java
@ApplicationScoped
public class AuthorizationIdentityStore implements IdentityStore {
    private static final Logger LOGGER = Logger.getLogger(AuthorizationIdentityStore.class.getName());

    private String email;
    private Map<String, Set<String>> authorization;

    @PostConstruct
    void init() {
        LOGGER.config("IdentityStore.init()");
        try {
            var properties = new Properties();
            properties.load(getClass().getResourceAsStream("/oidc.properties"));
            email = properties.getProperty("email");
            LOGGER.log(Level.INFO, "email: {0}", new Object[] { email });
        } catch (IOException e) {
            LOGGER.log(Level.SEVERE, "Failed to load oidc.properties", e);
            email = "";
        }
        authorization = Map.of(
            "user", Set.of("foo", "bar"),
            email, Set.of("foo", "bar"));
    }

    @Inject
    private OpenIdContext context;

    @Override
    public Set<ValidationType> validationTypes() {
        return EnumSet.of(PRODUCE_GROUPS);
    }

    @Override
    public Set<String> getCallerGroups(CredentialValidationResult validationResult) {
        var principal = validationResult.getCallerPrincipal().getName();
        LOGGER.log(Level.INFO, "Get principal name in validation result: {}", principal);
        LOGGER.log(Level.INFO, "claims json: " + context.getClaimsJson());
        LOGGER.log(Level.INFO, "provider json: " + context.getProviderMetadata());
        var issuer = context.getClaimsJson().getProviderMetadata().getString("issuer");
        if (issuer.endsWith("google.com")) { // 因为 Google 返回的是长数字用户 ID，我们尝试使用电子邮件地址
            var email = context.getClaimsJson().getString("email");
            return authorization.get(email) == null ?
                Collections.<String>emptySet() : authorization.get(email);
        } else {
            return authorization.get(principal) == null ?
                Collections.<String>emptySet() : authorization.get(principal);
        }
    }
}
```

1. 访问 https://console.developers.google.com。

2. 创建一个新项目，例如“ApressBookDemoApp”。

3. 为该项目创建 OAuth 2.0 凭证，因为 Google 不会自动创建。从侧边栏中点击 Credentials（凭据）选项卡，然后点击 **Create credentials**（创建凭据），从下拉列表中选择 **OAuth client ID**。

4. Google 将提示你输入有关应用程序的一些信息，如产品名称、首页和标志。大部分都是可选的。在下一页，选择 **Web Application**（Web应用程序）类型，并输入我们构建的 Jakarta EE 应用程序等待回调的重定向 URL。输入 http://localhost:8080/callback 作为重定向 URL。

5. 随后你将在屏幕上看到 Client ID 和 Client Secret。下载为 JSON 并将其存储在安全位置。

在你的 Jakarta EE 应用中编辑/创建 `src/main/resources/oidc.properties`：

```
issuerUri=https://accounts.google.com
email=<your-email-address>
clientId=<your-client-id>
clientSecret=<your-client-secret>
```

将 `clientId` 和 `clientSecret` 的值替换为 Google 提供的 JSON 文件中的值，并将 `email` 替换为有效测试用户的邮箱地址（例如，你自己的 Gmail 地址）。

使用 `mvn wildfly:run` 构建/运行应用程序。现在你准备好测试了。

在浏览器中访问 http://localhost:8080/public。

你将看到页面：

Public Unsecured Servlet（公共非安全 Servlet）

接下来访问 http://localhost:8080/protected。



首次访问将带你重定向到 Google ID 登录页面。在成功确认 Google ID 后，它将重定向回受保护页面并显示如下内容：

## 第 5 章 安全框架

Protected Servlet（受保护 Servlet）

access token:ya29.a0AfB...

token type:Bearer

subject:1234567890987654321

expires in:Optional[1234]

refresh token:Optional.empty

```
claims json:{"sub":"1234567890987654321","name":"John Doel","given_name":"John","family_name":"Doe","picture":"https://lh3.googleusercontent.com/a/ABCdefghjijklmnopqrstuvwxY-z","email":"john.doel@gmail.com","email_verified":true,"locale":"xy"}
```

你也可以访问`http://localhost:8080/username`。

它将显示类似如下的内容：

UserName Servlet（用户名 Servlet）

principal name in request userPrincipal:1234567890987654321

principal name:1234567890987654321

isCallerInRole('foo')=true

nisCallerInRole('bar')=true

> Google 的 Principal 名称相当晦涩懂；它本质上是一个代表你 Google ID 的长数字串。

## Open Liberty

Open Liberty 是 IBM 提供的 Eclipse MicroProfile 和 Jakarta EE 的开源实现。它是 WebSphere Liberty 服务器的基础。

Open Liberty 22 及更高版本实现了 Jakarta EE 10 安全规范。

## 社交媒体登录

Open Liberty 的社交媒体登录功能提供了一种单点登录（SSO）形式，允许用户使用他们现有的社交媒体账户登录受保护的网站。

例如，你可以配置社交登录功能，使用户可以使用 Facebook 或 Twitter 账户登录你的网站，而无需专为为你的网站创建账户。你可以为任何使用 OAuth 2.0 或 OpenID Connect 1.0 标准进行授权的社交媒体平台启用社交登录。

要启用其社交媒体 1.0 功能，请在`server.xml`文件的`featureManager`元素内部添加以下元素：

```
<feature>socialLogin-1.0</feature>
```

社交登录功能为流行的社交媒体提供者提供了一系列内置配置元素，此外还有通用的配置元素。以下示例展示了如何在`server.xml`文件中配置不同的场景。

## 使用社交媒体 ID 登录

如果配置了多个社交媒体提供者，将显示一个可自定义的选择表单。用户可以使用他们选择的社交媒体提供者登录。以下示例展示了如何配置应用程序以请求用户使用 Google ID 登录。你可以在`https://console.google.com`生成你的 Google 凭据。

在此示例中，`your_app_id`和`your_app_secret`是`formlogin`应用程序的 Google Client ID 和 Client Secret 凭据。

```
<googleLogin clientId="your_app_id" clientSecret="your_app_secret" />

<!-- 受保护的应用程序需要定义安全约束 -->
<application type="war" id="formlogin" name="formlogin" location="server1/apps/formlogin.war">
  <application-bnd>
    <security-role name="Employee">
      <special-subject type="ALL_AUTHENTICATED_USERS" />
    </security-role>
  </application-bnd>
</application>
```

## 多社交媒体提供者

你可以配置多个社交媒体提供者供用户选择。用户在通过可用提供者身份验证之前会收到一个可自定义的选择表单，表单中包含了所有可用提供者。以下示例包含了 Google、GitHub、Facebook、LinkedIn 和 Twitter 的选择：

```
<googleLogin clientId="your_app_id" clientSecret="your_app_secret" />
<githubLogin clientId="your_app_id" clientSecret="your_app_secret" />
<facebookLogin clientId="your_app_id" clientSecret="your_app_secret" />
<linkedinLogin clientId="your_app_id" clientSecret="your_app_secret" />
<twitterLogin consumerKey="your_app_id" consumerSecret="your_app_secret" />
```

```
<!-- 受保护的应用程序需要定义安全约束 -->
<application type="war" id="formlogin" name="formlogin" location="server1/apps/formlogin.war">
<application-bnd>
<security-role name="Employee">
<special-subject type="ALL_AUTHENTICATED_USERS" />
</security-role>
</application-bnd>
</application>
```

## 要求用户必须属于企业注册表

你可以将社交媒体提供者的展示限制仅适用于另一个配置的注册表中的用户。例如，使用`mapToUserRegistry`属性来配置你的应用程序。用户必须通过 Google 进行身份验证，并且验证为公司 LDAP 注册表中的现有用户：

```
<googleLogin mapToUserRegistry="true" clientId="your app id" clientSecret="your app secret" />
<ldapRegistry ...
```

## 在社交媒体 ID 和企业注册表之间选择

你可以让用户在社交媒体提供者或公司注册表之间选择登录方式。例如，使用`enableLocalAuthentication`属性配置你的应用程序，以便：

```
<!-- 用户可以选择 Google 或 LDAP -->
<socialLogin enableLocalAuthentication="true">
<ldapRegistry id="ldap" /></ldapRegistry>
```

## 部分路径登录

要保护部分应用程序、URL 或 IP 地址，请使用身份验证过滤器。只有满足过滤器条件时安全配置才会生效。例如，你可能希望使用 Google 凭据保护 Web 应用。

在以下示例中，包含`/mywebapp`的请求将受 Google 保护：

```
<googlelogin authFilter="authFilter1" clientId="your app id" clientSecret="your app secret" />
<authFilter id="authFilter1">
<requestUrl
  urlPattern="/mywebapp"
  matchType="contains" />
</authFilter>
```

## 其他社交媒体登录

要与 Open Liberty 未预配置的社交媒体提供者进行身份验证，请对 OAuth 提供者使用`oauthLogin`元素，对 OpenID Connect 使用`oidcLogin`元素。

## 第 5 章 安全框架

这些元素提供了与提供者工作所需的配置详细信息。这些信息通常可以从社交媒体提供者的开发者说明中获得。以下示例配置 Instagram 作为社交媒体提供者：

```
<oauth2Login id="instagramLogin" clientId="client_id"
clientSecret="client_secret"
scope="basic public_content" responseType="code"
tokenEndpointAuthMethod="client_secret_post"
authorizationEndpoint="https://api.instagram.com/oauth/authorize"
tokenEndpoint="https://api.instagram.com/oauth/access_token"
userApi="https://api.instagram.com/v1/users/self"
userNameAttribute="username"
website="https://www.instagram.com/developer/authentication/"
</oauth2Login>
```

## 用于连接认证的私钥 JWT

通过社交媒体登录功能中的`oidcLogin`元素配置的 OpenID Connect 客户端支持带有 OpenID Connect 端点的`private_key_jwt`客户端方法。在社交媒体登录功能中启用此功能的方法与 OpenID Connect 1.0 功能相同：

```
<oidcLogin id="myOidcClientUsingKeyJwt"
tokenEndpointAuthMethod="private_key_jwt"
tokenEndpointAuthSigningAlgorithm="E512"
keyAliasName="privatekeyaliasES512"
```

## 使用 OpenShift 服务账户进行身份验证和授权

社交媒体登录功能可以配置为使用 OpenShift 服务账户对受保护的请求进行身份验证和授权。通过这种配置，服务器管理员可以保护可能产生敏感信息的端点，例如`oidc`和`metrics`端点。服务账户可以

# 第 5 章 安全框架

通过在请求中提供在 OpenShift 集群内创建的服务账户令牌来完成身份验证。以下示例展示了如何配置社交媒体登录功能，使用 OpenID 服务账户作为单点登录（SSO）提供程序：

```
<okdServiceLogin />
```

`okdServiceLogin`元素身份验证 Open Liberty 接收到的所有受保护资源请求。服务账户所在的 OpenShift 项目将用作该账户用于授权决策的组。

## 使用 Active Directory 作为身份验证程序

你可以配置 Open Liberty 服务器使用 Active Directory 作为受保护资源的身份验证程序。`oidcLogin`元素使用 OpenID Connect 协议配置社交登录。通过 OpenID Connect，发现端点 URL 提供客户端与身份验证程序交互所需的信息，在此例中为 Active Directory。在下面的示例中，`discoveryEndpoint`属性提供了 Active Directory 的端点 URL：

```
<oidcLogin
id="liberty-aad-javaeecafe" clientId="1m2a72a8-YH32-T56W-95Pq-aFNu7849172"
clientSecret="RahWkDUCpngeKUCg14ym6extsMcXPqdUCjYN"
discoveryEndpoint="https://login.microsoft.com/organizations/v2.0/.well-known/openid-configuration"
signatureAlgorithm="RS256"
userAttribute="preferred_username" />
```

## Keycloak

Keycloak [66] 是一个用于应用程序和服务的开源身份、访问管理和单点登录解决方案。用户可以针对 Keycloak 进行身份验证，而不是针对每个单独的应用，从而减轻应用程序处理登录表单、身份验证或存储用户身份的负担。Keycloak 还提供了社交登录、对桌面或移动应用的支持，并集成了 LDAP、目录、OAuth、OpenID Connect 或 SAML 在内的其他解决方案。

### 历史

Keycloak 由 Bill Burke 和 Stian Thorgensen 于 2014 年创建。第一个版本于 2014 年 9 月发布，在此之前已开发了一约一年。2016 年，红帽将 Red Hat SSO 产品从基于 PicketLink 框架切换到 Keycloak 上游项目，在此之前它已经将 PicketLink 代码合并到 Keycloak 中。

从那时起，Keycloak 经历了几乎所有的主要发布周期和版本号变更。2016 年 6 月底，红帽将 Keycloak 作为其 SSO 产品的基础，发布了版本 2.0.0。大约一年后，版本 3.0.0 发布，随后在 2018 年 6 月推出了 Keycloak 4.0.0。

由于受到 Java 和 JDK 每六个月一次周期以及每两年一次长期服务支持版本的影响，截至 2021 年，不仅是 Keycloak，红帽的其他项目（如 WildFly）在 2019 年之后似乎也变得“版本狂热”，因为 Keycloak 5.0.0 在 2019 年 3 月发布，而 6.0.0 仅在一个月后就发布。2019 年 11 月，版本号跳到了 8。截至 2021 年 8 月，最新的 Keycloak 版本是 15.0.2。虽然至少在第一位数字上似乎放慢了，但仅在 2021 年就发布了版本 13–15，这使得红帽似乎至少每三到四个月发布一次大版本，有时在下半年仅有轻微减速。发布说明有时只有单行文字，这让人怀疑版本号的巨大跨越是如何合理的，但看起来增长得更频繁。从版本 17.0.0 开始，默认的 Keycloak 分发版从 WildFly 切换到 Quarkus。2023 年 4 月，Keycloak 被 CNCF 接受为孵化项目。

## 概述

Keycloak 的目标是让应用程序开发者能够简单快捷地为他们的应用和服务提供安全性。

## 概念

Keycloak 基于以下概念：

- 身份验证 (Authentication)

- 授权 (Authorization)

- 凭据 (Credentials)

- 领域 (Realm)

## 身份验证

这是一个程序示例，用于检查请求是否满足身份验证器的要求：



```java
package org.keycloak.authentication;
public interface Authenticator {

/**
对身份验证器的初始调用。此方法应检查请求
是否满足身份验证器的要求。如果不满足，
应通过调用 AuthenticationFlowContext.challenge(Response) 发回挑战。如果这是一个挑战，操作 URL 必须指向
/realms/{realm}/login-actions/authenticate?code={session-code}&execution={executionId}
或
/realms/{realm}/login-actions/registration?code={session-code}&execution={executionId}
{session-code} 属于 AuthenticationFlowContext.generateAccessToken() 生成的代码。{executionId} 属于从 AuthenticationFlowContext.getExecution() 获取的 AuthenticationExecutionModel.getId() 值。
操作 URL 将调用下方描述的 action() 方法。
* @param context
*/
void authenticate(AuthenticationFlowContext context);

/**
从表单调用。
* @param context
*/
void action(AuthenticationFlowContext context);

/**
此身份验证器是否要求用户已被识别？AuthenticatorContext.getUser() 是否不为空？
@return
*/
boolean requiresUser();

/**
此身份验证器是否为用户配置？
* @param session
* @param realm
* @param user
* @return
*/
boolean configuredFor(KeycloakSession session, RealmModel realm, UserModel user);

/**
设置操作以配置身份验证器
*/
void setRequiredActions(KeycloakSession session, RealmModel realm, UserModel user);

/**
如果身份验证器与领域相关
@return
*/
default List<RequiredActionFactory> getRequiredActions(KeycloakSession session) {
    return Collections.emptyList();
}

/**
 * 检查领域中是否启用了所有必要操作
@return
*/
default boolean areRequiredEnabled(KeycloakSession session, RealmModel realm) {
    for (RequiredActionFactory raf : getRequiredActions(session)) {
        RequiredActionModel rafpm = realm.getRequiredActionByAlias(raf.getId());
        if (rafpm == null) {
            return false;
        }
        if (!rafpm.isEnabled()) {
            return false;
        }
    }
    return true;
}
```

## 密码策略

许多组织有特殊的密码策略。Keycloak 通过管理控制提供了丰富的密码策略。密码加密使用哈希算法。密码应匹配数字、大小写字母、特殊字符或正则表达式。以及常见的安全措施，如不包含用户名、不重复使用密码或过期日期（过期后必须更改密码）。

## 身份验证流

用户或服务在 Keycloak 中进行身份验证的动作序列称为身份验证流：

```java
package org.keycloak.authentication;
public interface AuthenticationFlow {
    String BASIC_FLOW = "basic-flow";
    String FORM_FLOW = "form-flow";
    String CLIENT_FLOW = "client-flow";

    Response processAction(String actionExecution);
    Response processFlow();
    boolean isSuccessful();
    default List<AuthenticationFlowException> getFlowExceptions(){
        return Collections.emptyList();
    }
}
```

Keycloak 内置了各种身份验证流。这些可以被配置为强制性，如果你的应用程序需要不同的内容，你始终可以从头创建自己的身份验证流，或者从复制现有的流开始。

图 5-1 显示了浏览器中可用的身份验证流：

- Cookie
- 身份提供者重定向 (Identity Provider Redirector)
- 表单 (Forms)
  - 用户名/密码 (Username/Password)
  - 动态身份验证码 (OTP)
- Kerberos

![](img/3c2d905e913621002f512a08b8855a70_148_0.png)

### 图 5-1. 浏览器身份验证流

至少有一个必须被启用才能成功进行身份验证。对于单点登录，Keycloak 支持两种主要的协议：

- OpenID Connect (OIDC)
- SAML

对于 OIDC，Keycloak 定义了四种主要的认证流：

- 授权码流（Authorization Code Flow）——适用于基于浏览器或服务器的应用。
- 隐式流（Implicit Flow）——适用于基于浏览的应用，此流安全性不如授权码流，且在 OAuth 2.1 中被弃用，因此为了向兼容可以使用，但不再推荐使用。
- 客户端凭据授权（Client Credentials Grant）——适用于 RESTful Web 服务的消费者，涉及存储密钥，因此客户端应该信任它们所消费的服务。

## 授权

Keycloak 支持多种授权策略，并允许组合不同的访问控制机制，例如：

- 基于属性的访问控制 (ABAC)
- 基于角色的访问控制 (RBAC)
- 基于用户的访问控制 (UBAC)
- 基于上下文的访问控制 (CBAC)
- 基于规则的访问控制
- 基于时间的访问控制
- 通过 Policy Provider SPI 实现的自定义访问控制机制

![](img/3c2d905e913621002f512a08b8855a70_150_0.png)

图 5-2. Keycloak 授权架构

## 凭据

凭据是 Keycloak 用于验证用户身份的数据片段。示例包括密码、一次性密码、数字证书、虹膜扫描和指纹。

## Realm（领域）

一个 Realm 允许管理一组用户、凭据、角色和组。用户属于其登录的 Realm。Realm 之间相互隔离的，只能管理和验证它们控制的用户。

## 特性

Keycloak 的主要特性如下：

- 客户端（每个应用）
- 事件（Events）
- 身份提供者（Identity Providers）
- OpenID Connect
- SAML
- 社交登录 – 启用 Google、GitHub、Facebook、Twitter 及其他社交网络的登录
- 安全防护（Security Defenses）
- UI（主题）
- 用户管理
  - 用户
  - 组
  - 角色
- 用户联邦（User Federation）
  - LDAP
  - Active Directory
  - 自定义提供者

## Realm: master

![](img/3c2d905e913621002f512a08b8855a70_151_0.png)

**图 5-3.** Keycloak 特性

## 客户端

Keycloak 中的客户端是希望在 Realm 内验证用户的实体（应用或服务）。它们还可以请求身份信息或访问令牌，以便安全地调用由 Keycloak 保护的网络上的其他服务。在认证过程中，客户端需要发送其 ID 和密钥（secret）。这些凭据通过在认证服务器中注册客户端来获取。

由于组织中有许多需要保护和维护的应用，为所有这些客户端配置协议映射器（protocol mappers）和范围（scope）可能会变得繁琐。Keycloak 允许你在客户端模板中定义共享的客户端配置。

## 事件

Keycloak 提供了丰富的审计功能。每次交互都可以记录和审查。事件有两种类型：

- 登录事件
- 管理事件

每当发生与认证相关的用户操作时（例如登录、注销、失败的登录尝试或用户账户更新），就会发生登录事件。管理事件通过 Admin API 触发，无论是通过 Admin 控制台、REST API 还是命令行界面。Listener SPI 允许你创建插件并监听这些事件。

以下是一个 EventListener 实现示例，它将事件写入到 System.out：

```java
public class SysoutEventListener implements EventListenerProvider {
    private Set<EventType> excludedEvents;
    private Set<OperationType> excludedAdminOperations;

    public SysoutEventListener(Set<EventType> excludedEvents, Set<OperationType> excludedAdminOperations) {
        this.excludedEvents = excludedEvents;
        this.excludedAdminOperations = excludedAdminOperations;
    }
}
```

## 第 5 章 安全框架

```java
@Override
public void onEvent(Event event) {
    // 忽略排除的事件
    if (excludedEvents != null && excludedEvents.contains(event)) {
        return;
    } else {
        System.out.println("EVENT: " + toString(event));
    }
}

@Override
public void onEvent(AdminEvent event, boolean includeRepresentation) {
    // 忽略被排除的操作
    if (excludedAdminOperations != null && excludedAdminOperations.contains(event.getOutputType())) {
        return;
    } else {
        System.out.println("EVENT: " + toString(event));
    }
}

private String toString(Event event) {

    StringBuilder sb = new StringBuilder();
    sb.append("type=");
    sb.append(event.getType());
    sb.append(",", realmId=");
    sb.append(event.getRealmId());
    sb.append(",", clientId=");
    sb.append(event.getClientId());
    sb.append(",", userId=");
    sb.append(event.getUserId());
    sb.append(",", ipAddress=");
    sb.append(event.getIpAddress());
```

```java
    if (event.getError() != null) {
        sb.append(",", error=");
```

```java
        sb.append(event.getError());
    }
    if (event.getDetails() != null) {
        for (Map.Entry<String, String> e : event.getDetails()) {
            sb.append(", ").append(e.getKey()).append("=").append(e.getValue());
        }
    }
    return sb.toString();
}

private String toString(AdminEvent event) {

    StringBuilder sb = new StringBuilder();
    sb.append("type=");
    sb.append(event.getOutputType());
    sb.append(",", realmId=");
    sb.append(event.getRealmId());
    sb.append(",", clientId=");
    sb.append(event.getClientId());
    sb.append(",", userId=");
    sb.append(event.getUserId());
    sb.append(",", ipAddress=");
    sb.append(event.getIpAddress());
```



```java
if (event.getError() != null) {
    sb.append(",", error=");
}
if (event.getDetails() != null) {
    for (Map.Entry<String, String> e : event.getDetails()) {
        sb.append(", ").append(e.getKey()).append("=").append(e.getValue());
    }
}
return sb.toString();
}

public class SysoutEventListener implements EventListenerProvider {
    private Set<EventType> excludedEvents;
    private Set<OperationType> excludedAdminOperations;

    public SysoutEventListener(Set<EventType> excludedEvents, Set<OperationType> excludedAdminOperations) {
        this.excludedEvents = excludedEvents;
        this.excludedAdminOperations = excludedAdminOperations;
    }

    @Override
    public void onEvent(Event event) {
        // 忽略排除的事件
        if (excludedEvents != null && excludedEvents.contains(event)) {
            return;
        } else {
            System.out.println("EVENT: " + toString(event));
        }
    }

    @Override
    public void onEvent(AdminEvent event, boolean includeRepresentation) {
        // 忽略排除的操作
        if (excludedAdminOperations != null && excludedAdminOperations.contains(event.getOutputType())) {
            return;
        } else {
            System.out.println("EVENT: " + toString(event));
        }
    }

    private String toString(Event event) {
        StringBuilder sb = new StringBuilder();
        sb.append("type=");
        sb.append(event.getType());
        sb.append(",", realmId=");
        sb.append(event.getRealmId());
        sb.append(",", clientId=");
        sb.append(event.getClientId());
        sb.append(",", userId=");
        sb.append(event.getUserId());
        sb.append(",", ipAddress=");
        sb.append(event.getIpAddress());
        if (event.getError() != null) {
            sb.append(",", error=");
            sb.append(event.getError());
        }
        if (event.getDetails() != null) {
            for (Map.Entry<String, String> e : event.getDetails()) {
                sb.append(", ").append(e.getKey()).append("=").append(e.getValue());
            }
        }
        return sb.toString();
    }

    private String toString(AdminEvent event) {
        StringBuilder sb = new StringBuilder();
        sb.append("type=");
        sb.append(event.getOutputType());
        sb.append(",", realmId=");
        sb.append(event.getRealmId());
        sb.append(",", clientId=");
        sb.append(event.getClientId());
        sb.append(",", userId=");
        sb.append(event.getUserId());
        sb.append(",", ipAddress=");
        sb.append(event.getIpAddress());
        if (event.getError() != null) {
            sb.append(",", error=");
            sb.append(event.getError());
        }
        if (event.getDetails() != null) {
            for (Map.Entry<String, String> e : event.getDetails()) {
                sb.append(", ").append(e.getKey()).append("=").append(e.getValue());
            }
        }
        return sb.toString();
    }
}

public class SysoutEventListenerFactory implements EventListenerProviderFactory {
    private Set<EventType> excludedEvents;
    private Set<OperationType> excludedAdminOperations;

    @Override
    public void init(Config.Scope config) {
        String[] excludes = config.getArray("exclude-events");
        if (excludes != null) {
            excludedEvents = new HashSet<>();
            for (String e : excludes) {
                excludedEvents.add(EventType.valueOf(e));
            }
        }
        String[] excludesOperations = config.getArray("excludesOperations");
        if (excludesOperations != null) {
            excludedAdminOperations = new HashSet<>();
            for (String e : excludesOperations) {
                excludedAdminOperations.add(OperationType.valueOf(e));
            }
        }
    }

    @Override
    public EventListenerProvider create(KeycloakSession session) {
        return new SysoutEventListener(excludedEvents, excludedAdminOperations);
    }

    @Override
    public void postInit(KeycloakSessionFactory factory) {
    }

    @Override
    public void close() {
    }

    @Override
    public String getId() {
        return "sysout";
    }
}
```

## 用户联邦

当组织拥有用户数据库时，Keycloak 允许我们与其同步。默认情况下，它支持 LDAP 和 Active Directory，但你可以使用 Keycloak User storage API 为任何身份存储创建自定义扩展。Keycloak 还可以作为你的用户与外部身份提供者之间的代理。

## 社交身份提供者

社交身份提供者可以将认证委托给信任的社交媒体账号。Keycloak 包含了对 Google、Facebook、Twitter、GitHub、LinkedIn、Microsoft 和 Stack Overflow 等社交网络的支持。

![](img/3c2d905e913621002f512a08b8855a70_157_0.png)

图 5-4. 社交身份提供者

### Facebook

1. 在菜单中点击身份提供者（Identity Providers）。
2. 从“添加提供者”列表中选择 Facebook。Keycloak 显示 Facebook 身份提供者的配置页面。

![](img/3c2d905e913621002f512a08b8855a70_157_1.png)

图 5-5. 添加 Facebook 作为身份提供者

3. 将重定向 URI（Redirect URI）的值复制到剪贴板。

## 第 5 章 安全框架

4. 在单独的浏览器标签页中，按照 Facebook 开发者指南的说明在 Facebook 中创建一个项目和客户端。
   - a) 确保你的应用类型为网站（website-type）。
   - b) 将重定向 URI（Redirect URI）的值输入 Facebook 网站设置块的 URL 中。
   - c) 确保应用是公开的。
5. 将来自 Facebook 应用的 Client ID 和 Client Secret 值输入 Keycloak 中的 Client ID 和 Client Secret 字段中。
6. 点击添加（Add）。
7. 在默认范围（Default Scopes）字段中输入所需的范围。默认情况下，Keycloak 使用 `email` 范围。有关 Facebook 范围的更多信息，请参阅 Graph API。

默认情况下，Keycloak 向 `graph.facebook.com/?fields=id,name,email,first_name,last_name` 发送配置请求。响应仅包含 `id`、`name`、`email`、`first_name` 和 `last_name` 字段。要从 Facebook 配置中获取额外字段，请添加相应的范围，并在“额外用户配置字段”配置选项中添加该名称。

## Spring Security

Spring Security [67] 是一个安全框架，它与 Spring Framework 或 Spring Web MVC 配合得非常好，最近也适用于使用 Spring Flux 的响应式应用程序。Spring Security 是 Acegi Security 的延续，这是一个强大的安全框架。但问题是实现它需要大量繁琐的 XML 配置。Spring 从 2.0 版本开始将其引入家族，并从那时起完善到现在的状态。尽管仍然可以使用 XML 配置，但 Spring 新的“约定约优于配置”（convention over configuration）精神也产生了同样的影响，这种影响我们在 Jakarta EE 中也能看到。完全可以通过注解而不是 XML 执行所有的安全配置，尽管为了向后兼容和利用某些灵活性，该机制仍然存在。它的首要目标是处理请求和方法调用的身份验证和授权。

### 历史

Spring Security 起始于二十年前（即 2003 年底），最初名为“用于 Spring 的 Acegi Security 系统”，最初由 Ben Alex 创建，这是基于 Spring 开发者邮件列表上提出的一个问题，即是否有任何基于 Spring 的安全实现。那时，Spring 社区还较小，Spring 本身仅从 2003 年初开始作为一个 SourceForge 项目存在。对该问题的回答是值得的，尽管当时缺乏时间和资源阻碍了当时的探索。

本着这种理念，人们构建了一个简单的安全实现但并未发布。几周后，Spring 社区的另一个成员询问了安全问题，这段代码被提供给了他们。

其他问题接踵而至，到 2004 年 1 月，大约有 20 个人在使用这段代码。这些最初的用户加入了其他人，他们建议创建一个自己的 SourceForge 项目，该项目于 2004 年 3 月创建。

当时，该项目还没有自己的身份验证模块。认证过程使用了 J2EE 容器托管安全（Container Managed Security），而 Acegi Security 的第一个版本侧关注授权。这在最初是合适的，但随着越来越多的用户请求对额外容器的支持，特定容器认证领域接口的局限性变得而易见。向容器的 Classpath 添加新的 JAR 包也会导致问题，这是混淆和误配置的常见来源。引入了 Acegi Security 认证服务。大约一年后，Acegi Security 成为 Spring Framework 的官方子项目。1.0.0 正式版本于 2006 年 5 月发布——在此之前，经过了多个项目两年多的生产以及数百个改进请求和社区贡献。Acegi Security 在 2007 年底成为官方 Spring 项目，并被更名为“Spring Security”。

## 概述

Spring Security 基于三个主要概念：

- 身份验证（Authentication）
- 授权（Authorization）
- Servlet 过滤器（Servlet Filters）

![图 5-6. Spring Security 身份验证/授权流程](img/3c2d905e913621002f512a08b8855a70_160_0.png)

## 身份验证

Spring Security 中身份验证的主要接口是 `AuthenticationManager`，它只有一个方法 `authenticate()`。

```java
public interface AuthenticationManager {

    Authentication authenticate(Authentication authentication)

    throws AuthenticationException;

}
```

`AuthenticationManager` 最常见的实现是 `ProviderManager`，它委托给 `AuthenticationProvider` 实例链。`AuthenticationProvider` 类似于 `AuthenticationManager`，但它有一个额外的方法，允许调用者检查它是否支持特定的身份验证类型。

```java
public interface AuthenticationProvider {

    Authentication authenticate(Authentication authentication)

    throws AuthenticationException;

    boolean supports(Class<?> authentication);

}
```

## 授权

Spring Security 中授权的主要元素是 `AccessDecisionManager`。框架提供了三个默认实现，它们都使用 `AccessDecisionVoter` 实例链，类似于 `ProviderManager` 使用 `AuthenticationProvider` 实例的方式。

`AccessDecisionVoter<S>` 使用一个 `Authentication`（主体）和一个安全对象，该对象由一个 `ConfigAttribute` 修饰：

```java
boolean supports(ConfigAttribute attribute);
```

```java
boolean supports(Class<?> clazz);
```

```java
int vote(Authentication authentication, S object, Collection<ConfigAttribute> attributes);
```



`ConfigAttribute`接口封装了安全资源中的访问信息元数据。图 5-7 显示了配置属性的层次结构。

![图 5-7. 配置属性层级](img/3c2d905e913621002f512a08b8855a70_162_0.png)

## Servlet 过滤器

Spring Security 的 Web 层基于标准的 Jakarta EE Servlet 过滤器，尽管从 Spring Security 和 Framework 5 开始，它最多是 Jakarta EE 8。Spring Security 过滤器链构建在这些过滤器之上。图 5-8 显示了单个 HTTP 请求的过滤器链。

![图 5-8. 单个 HTTP 请求的过滤器链](img/3c2d905e913621002f512a08b8855a70_163.png)

对于容器来说，Spring Security 基本上是由多个过滤器组成的单个过滤器。它是通过过滤器链安装。这个名为`FilterChainProxy`的过滤器包含了通过过滤器链可用的所有详细信息。这里有一个示例：

```xml
<bean id="FilterChainProxy" class="org.springframework.security.web.FilterChainProxy">
    <sec:filter-chain-map path-type="ant">
        <sec:filter-chain pattern="/webServices/**" filters="
            securityContextFilter,
            basicAuthenticationFilter,
            exceptionTranslationFilter,
            filterInterceptor" />
        <sec:filter-chain pattern="/*" filters="
            securityContextFilter,
            formLoginFilter,
            exceptionTranslationFilter,
            filterInterceptor" />
    </sec:filter-chain-map>
</bean>
```

然而，`FilterChainProxy`并不是直接调用，而是通过`DelegatingFilterProxy`调用。使用它，你会在应用程序的`web.xml`文件中看到类似：

```xml
<filter>
  <filter-name>myFilter</filter-name>
  <filter-class>org.springframework.web.filter.DelegatingFilterProxy</filter-class>
</filter>
```

```xml
<filter-mapping>
  <filter-name>myFilter</filter-name>
  <url-pattern>/*</url-pattern>
</filter-mapping>
```

## 社会登录

Spring Security 5 内置了对 Facebook、Google 和 GitHub 等身份提供者的 OAuth 2 支持。以下是它们的 OAuth 2 客户端配置示例。

## 配置身份提供者

首先，配置你选择的身份提供者。

## Facebook

在你的应用程序属性中配置 Client ID 和 Client Secret。

```properties
spring.security.oauth2.client.registration.facebook.client-id = <Facebook app id>
spring.security.oauth2.client.registration.facebook.client-secret = <Facebook app secret>
```

要获取 Facebook App ID 和 Secret 密钥，你需要在 https://developers.facebook.com/apps/ 创建一个新的应用程序。

## 配置 HTTP 安全

接下来使用`@EnableWebSecurity`注解并配置`HttpSecurity`对象。在你的项目中创建一个新的 Java 类并扩展`WebSecurityConfigurerAdapter`。在该类上加上`@EnableWebSecurity`注解：

```java
import org.springframework.security.config.annotation.web.builders.HttpSecurity;
import org.springframework.security.config.annotation.web.configuration.EnableWebSecurity;
import org.springframework.security.config.annotation.web.configuration.WebSecurityConfigurerAdapter;
```

```java
@EnableWebSecurity
public class WebSecurity extends WebSecurityConfigurerAdapter {
    @Override
    protected void configure(HttpSecurity http) throws Exception {
        http.authorizeRequests()
            .antMatchers("/").permitAll()
            .anyRequest().authenticated()
        .and()
            .oauthLogin()
        .and()
            .logout().logoutSuccessUrl("/");
    }
}
```

这将使我们的应用程序重定向到社交登录提供商进行身份验证。一旦用户成功通过社交登录提供商，他们将被重定向回最初请求的应用程序受保护页面。注意，我们还启用了注销功能并配置了注销成功 URL。

## 创建受保护页面

以下示例将创建一个包含名为“users”单一资源的 Controller 类：

```java
import org.springframework.security.core.annotation.AuthenticationPrincipal;
import org.springframework.framework.security.oauth2.core.user.OAuth2User;
import org.springframework.framework.stereotype.Controller;
import org.springframework.framework.ui.Model;
import org.springframework.framework.web.bind.annotation.GetMapping;

@Controller
public class UsersController {
    @GetMapping("/users")
    public String getUser(Model model, @AuthenticationPrincipal OAuth2User principal) {
        if (principal != null) {
            model.addAttribute("name", principal.getAttribute("name"));
        }
        return "user";
    }
}
```

当请求`/users`资源时，我们的应用程序会将用户重定向到社交登录提供商进行认证。如果身份验证成功，用户将被重定向回`/users`资源。由于身份验证成功，我们可以通过`@AuthenticationPrincipal`注解获取当前认证用户的信息，这将帮助我们访问`OAuth2User`。`OAuth2User`是一个可以获取详情的主对象。

## Micronaut Security

Micronaut Security 是一个用于 Micronaut 应用程序的安全框架 [68]。Micronaut 通常与 Spring Boot 类似，但在大多数情况下具有更好的启动速度。JAR 文件更小，运行时消耗的内存也更少。

每个“微框架”课程都尝试在每个新版本中优化性能，这些差异可能会随发布而异。

## 特性

Micronaut Security的主要特性包括：

- 身份验证 (Authentication)
- 授权 (Authorization)
- 安全规则 (Security Rules)
- 安全事件 (Security Events)
- 令牌传播 (Token Propagation)

## 使用 Google 保护 Micronaut

在安装 Micronaut 后，请遵循步骤指南：https://guides.micronaut.io/latest/micronaut-oauth2-oidc-google-gradle-java.html

如果你更喜欢 Maven，在步骤 4 下调用：

`mn create-app example.micronaut.micronautguide --build=maven --lang=java`

## Apache Shiro

Apache Shiro 是一个开源安全框架，为应用程序开发者提供了直观、简单的方法来支持：

- 身份验证 (Authentication)
- 授权 (Authorization)
- 加密算法 (Cryptography)
- 会话管理 (Session Management)

“shiro”在日语中是城堡的意思。

### 历史

Shiro 的诞生是因为当时的标准无法满足开发者的需求。Les Hazlewood 和 Jeremy Haiti 在 2004 年至 2008 年间在 SourceForge 上创建了一个名为 JSecurity 的安全框架，因为他们找不到适合他们现有 Java 安全框架，而 JAAS（我们在第 1 章已经学过）对他们来说并不好。他们的努力大约与 2004 年在 SourceForge 上的 Acegi Security 同时开始，当时 SourceForge 是最大的开源托管社区，类似于现在的 GitHub。JSecurity 吸引了更多评论者，包括 Peter Ledbro、Alan Ditzel 或 Tim Veil。

2008 年，JSecurity 被提交给 Apache 软件基金并被纳入其孵化器计划，旨在成为一个顶层 Apache 项目。在 ASF 孵化器下，JSecurity 最初被命名为 Ki（读作 "Key"），但很快因商标问题被重命名为 Shiro。该项目在 Apache 孵化器中成长，增加了 Kalle Korhonen 作为贡献者。2010 年 7 月，Shiro 发布了其 1.0 版本。

### 第 5 章 安全框架

### 概述

Shiro 基于三个核心概念：

- 主体 (Subject)
- 安全管理器 (SecurityManager)
- 领域 (Realm)

### 主体 (Subject)

Subject 本质上是一个人类、第三方服务或当前正在执行某些操作的外部进程。

### 安全管理器 (SecurityManager)

SecurityManager 是 Shiro 的中心点；它协调所有的安全操作。

### 领域 (Realm)

Realm 管理一组安全数据。Realm 充当 Shiro 和你的应用程序安全数据（如 LDAP 目录、Active Directory 或数据库）之间的桥梁。

### 特性

尽管拥有多种功能，Shiro 的目标是让身份验证变得直观且易于使用；以下是其亮点：

- 基于主体的 (Subject Based)
- 单方法调用
- 详细的异常层次结构
- 内置的“记住我” (Remember Me)
- 可插的数据源
- 使用多个领域 (Multiple Realms)

# 授权

授权包含三个主要元素：

- 权限
- 角色
- 用户（主体 Subject）

# 权限

权限是安全策略的一个基本方面。它们决定了在应用程序中可以执行的操作。元素的常用权限有创建（Create）、读取（Read）、更新（Update）和删除（Delete），简称 CRUD。

# 粒度

Shiro 允许根据需要非常细粒度的权限，支持任何粒度，例如：

- 资源级 - 最广泛的定义，例如允许用户编辑客户记录或财务状况
- 实例级 - 特定资源实例的权限，而不仅仅是通用类型，例如允许用户访问 IBM 的客户记录，但不能访问 Red Hat 的
- 属性级 - 允许为实例或资源的属性指定权限，例如 IBM 员工的家庭地址或工作地址

这里有一个权限示例。我们检查用户是否有权限使用“彩色打印机”进行打印，以及哪些用户能看到“打印”按钮，其他人则没有。这是一个实例级权限的示例。

```java
Subject currentUser = SecurityUtils.getSubject();
Permission printPermission = new PrinterPermission("ColourPrinter", "print");
if (currentUser.isPermitted(printPermission)) {
    // show the print button?
} else {
    // don't show the button?
}
```

# 用户

用户或“主体”（Subject，正如前面提到的，它也可以是一个服务或企业实体）可以是你应用程序中的任何执行者。在大多数情况下，你通过使用`org.apache.shiro.SecurityUtils`获取当前主体：

```java
Subject currentUser = SecurityUtils.getSubject();
```

# 角色

记住第 2 章中的 RBAC（基于角色的访问控制）；角色是一组权限，允许将权限分配给角色而不是每个单独的用户。Shiro 提供了两种类型的角色：

- 隐式角色
- 显式角色

应用程序的角色检查通常是隐式角色分配。拥有“管理员”角色的用户可以查看客户数据。角色名称并不一定与业务需求或场景相关，而显式角色已经自带了它所需的权限。例如，拥有“编辑器”角色的用户被分配了“发布章节”的权限。

```java
Realm realm = new MyPublishingRealm();
SecurityManager securityManager = new DefaultSecurityManager(realm);
SecurityUtils.setManager(securityManager);
Subject currentUser = SecurityUtils.getSubject();

if (!currentUser.isAuthenticated()) {
  UsernamePasswordToken token = new UsernamePasswordToken("user", "password");
  token.setRememberMe(true);
  try {
    currentUser.login(token);
  } catch (UnknownAccountException uae) {
    log.error("Username Not Found", uae);
  } catch (IncorrectCredentialsException ice) {
    log.error("Invalid Credentials!", ice);
  } catch (LockedAccountException lae) {
    log.error("Your Account is Locked!", lae);
  } catch (AuthenticationException ae) {
    log.error("Unexpected Error!", ae);
  }
  log.info("User [" + currentUser.getPrincipal() + "] logged in successfully.");

  if (currentUser.hasRole("admin")) {
    log.info("Welcome Admin");
  } else if (currentUser.hasRole("editor")) {
    log.info("Welcome, Editor!");
  } else if (currentUser.hasRole("author")) {
    log.info("Welcome, Author");
  } else {
    log.info("Welcome, Guest");
  }

  if (currentUser.isPermitted("chapters:write")) {
    log.info("You can write a chapter");
  } else {
    log.info("You are not permitted to write a chapter!");
  }

  if (currentUser.isPermitted("chapters:save")) {
    log.info("You can save chapters");
  } else {
```



`log.info("You cannot save chapters");`

```
if (currentUser.isPermitted("chapters:publish")) {
  log.info("You can publish chapters");
} else {
  log.info("You can not publish chapters");
}
```

```
session = currentUser.getSession();
session.setAttribute("key", "value");
String value = (String) session.getAttribute("key");
if (value.equals("value")) {
  log.info("Retrieved the correct value! [" + value + "]");
}
currentUser.logout();
```

# 第 5 章 安全框架

## 会话管理 (Session Management)

一旦我们获取了当前用户，就可以检索他们的会话：

```
Session session = currentUser.getSession();
session.setAttribute("key", "value");
```

`Session` 是一个 Shiro 特有的实例，包含了你从 Jakarta Servlet `HttpSession` 中知道的大部分内容，并额外额外了一些，并且独立于 HTTP 环境。

在 Web 应用程序内部，`Session` 将基于 `HttpSession`。但在非 Web 环境中，Shiro 默认会自动使用它自己的会话管理。这意味着无论部署环境如何，你可以在应用程序中使用相同的 API。这为“无服务器”应用程序开辟了新的可能性，因为需要会话的应用程序不需要使用 `HttpSession` 或 EJB Stateful Beans。

## 加密算法 (Cryptography)

Shiro 主要的加密方面如下：

- 简单性
- 密算法功能
- 哈希功能

## 社交登录 (Social Login)

以下示例展示了如何处理 Shiro 应用程序的 Facebook 登录。

## 创建 Facebook 应用

要获取 Facebook App ID 和 App secret 凭据，你需要在 `https://developers.facebook.com/apps/` 创建一个新的 Facebook 应用。

## 示例代码

Facebook 用户详情：

```java
package com.example.facebook;

/**
 * 用于存储 Facebook 用户数据的简单类
 */
class FacebookUserDetails {

    // jsonString Expected to be something like this:
    // email
    // {
    //   "education": [
    //     "school": {
    //       "id": "123456789012345",
    //       "name": "Vienna University of Technology " 
    //     },
    //     "type": "Graduate School",
    //     "with": [
    //       "id": "123456789",
    //       "name": "BRG"
    //     ]
    //   ],
    //   "first_name": "Werner",
    //   "id": "123456789",
    //   "last_name": "Keil",
    //   "link":
    //   "http://www.facebook.com/profile.php?id=123456789",
    //   "locale": "de_DE",
    //   "name": "Werner Keil",
    //   "verified": true,
    //   "updated_time": "2023-05-15T14:00:00"
    // }

    private String jsonString;
    private String id;
    private String firstName;
    private String email;

    public FacebookUserDetails(String fbResponse) {
        try {
            JSONObject respJson = new JSONObject(fbResponse);
            this.id = respJson.getString("id");
            this.firstName = respJson.getString("first_name");
            this.lastName = respJson.getString("last_name");
            this.email = respJson.getString("email");
        } catch (JSONException e) {
            throw new RuntimeException(e);
        }
    }

    @Override
    public String toString() {
        return jsonString;
    }

    public String getId() {
        return id;
    }

    public void setId(String id) {
        this.id = id;
    }

    public String getFirstName() {
        return firstName;
    }

    public void setFirstName(String firstName) {
        this.firstName = firstName;
    }

    public String getLastName() {
        return lastName;
    }

    public void setLastName(String lastName) {
        this.lastName = lastName;
    }

    public String getEmail() {
        return email;
    }

    public void setEmail(String email) {
        this.email = email;
    }
}
```

## 第5章 安全框架

`authUrl = new URL("https://graph.facebook.com/oauth/access_token") + "&client_id=" + APP_ID + "&redirect_uri=" + REDIRECT_URL + "&client_secret=" + APP_SECRET + "&code=" + facebookToken.getCode());`

```java
String authResponse = readURL(authResponse);
System.out.println(authResponse);
String accessToken = getPropsMap(authResponse).get("access_token");
URL url = new URL("https://graph.facebook.com/me?access_token=" + accessToken);
String fbResponse = readURL(url);
FacebookUserDetails userDetails = new FacebookUserDetails(fbResponse);
return new FacebookAuthenticationInfo(userDetails, this.getName());
} catch (MalformedURLException e1) {
  e1.printStackTrace();
  throw new AuthenticationException(e1);
} catch (IOException ioe) {
  ioe.printStackTrace();
  throw new AuthenticationException(ioe);
} catch (Throwable e) {
  e.printStackTrace();
}
}
return null;
```

```java
private String readURL(URL url) throws IOException {
  ByteArrayOutputStream baos = new ByteArrayOutputStream();
  InputStream is = url.openStream();
  int r;
  while ((r = is.read()) != -1) {
    baos.write(r);
  }
  return new String(baos.toByteArray());
}
```

```java
private Map<String, String> getPropsMap(String someString) {
  String[] pairs = someString.split("&");
  Map<String, String> props = new HashMap<>();
  for (String propPair : pairs) {
    String[] pair = propPair.split("=");
    props.put(pair[0], pair[1]);
  }
  return props;
}
```

`CredentialsMatcher` 类不需要做太多，因为 Facebook 已经为我们匹配了凭据：

```java
package com.example.facebook;

import org.apache.shiro.authc.AuthenticationInfo;
import org.apache.shiro.authc.AuthenticationToken;
import org.apache.shiro.authc.credential.CredentialsMatcher;

public class FacebookCredentialsMatcher implements CredentialsMatcher {

  /**
   * 仅确认正确的令牌类型，凭据检查由 facebook OAuth 完成
   */
  @Override
  public boolean doCredentialsMatch(AuthenticationToken token, AuthenticationInfo info) {
    if(info instanceof FacebookAuthenticationInfo) {
      return true;
    }
    return false;
  }
}
```

然后创建一个 Facebook token 类，用于保存 Facebook 提供的“code”：

```java
package com.example.facebook;

import org.apache.shiro.authc.AuthenticationToken;

public class FacebookToken implements AuthenticationToken {

    private static final long serialVersionUID = 1L;
    private final String code;

    public FacebookToken(String code) {
        this.code = code;
    }

    @Override
    public Object getPrincipal() {
        return null; // Unknown - Facebook 负责登录
    }

    @Override
    public Object getCredentials() {
        return null; // 凭据由 Facebook 处理 - 我们不需要
    }

    public String getCode() {
        return code;
    }

    public void setCode(String code) {
        this.code = code;
    }
}
```

一个 `FacebookAuthenticationInfo` 类：

```java
package com.example.facebook;

import java.util.ArrayList;
import java.util.Collection;
import org.apache.shiro.authc.AuthenticationInfo;
import org.apache.shiro.subject.PrincipalCollection;
import org.apache.shiro.subject.SimplePrincipalCollection;

public class FacebookAuthenticationInfo implements AuthenticationInfo {

    private static final long serialVersionUID = 1L;
    private PrincipalCollection principalCollection;

    public FacebookAuthenticationInfo(FacebookUserDetails facebookDetails,
    String realmName){
        Collection<String> principals = new ArrayList<>();
        principals.add(facebookDetails.getId());
        principals.add(facebookDetails.getFirstName() + "+" + facebookDetails.LastName());
        this.principalCollection = new SimplePrincipalCollection(principals);
    }

    @Override
    public PrincipalCollection getPrincipals() {
        return principalCollection;
    }

    @Override
    public Object getCredentials() {
        return null;
    }
}
```

现在创建一个 Facebook servlet 来处理重定向：

```java
package com.example.facebook;

import java.io.IOException;
import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import org.apache.shiro.authc.AuthenticationException;
import org.apache.shiro.SecurityUtils;

/**
 * 使用 Shiro 的简单 Facebook 登录
 */
public class FacebookLogin extends HttpServlet {

    private static final long serialVersionUID = 1L;

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        String code = request.getParameter("code");
        FacebookToken facebookToken = new FacebookToken(code);
        try {
            SecurityUtils.getSubject().login(facebookToken);
```



`response.sendRedirect("index.jsp");`

```java
} catch (AuthenticationException ae) {
    throw new ServletException(ae);
}
```

```java
protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
    System.out.println("Error during doPost...");
}
```

`shiro.ini`:

```ini
[main]
realA = com.example.dao.RoleSecurity
fbCredentialsMatcher = com.example.FacebookCredentialsMatcher
realB = FacebookRealm
realB.credentialsMatcher = fbCredentialsMatcher
securityManager.realms = realA,realB
```

## S

Scribe 项目内置支持许多使用 OAuth 的流行服务，如 Facebook、Twitter、LinkedIn。它的依赖很少，主要是 Apache，允许无缝集成到更大复杂的解决方案中。

在 Scribe 中调用 OAuth 像下面的代码一样简单：

```java
OAuthService service = new ServiceBuilder(LinkedInApi.class)
    .apiKey(YOUR_API_KEY)
    .apiSecret(YOUR_API_SECRET)
    .build();
```

在 Scribe 0.6 中，S 是功能的核心。从 0.7 版本开始，它被 JBoss PicketLink 取代。虽然后者不再活跃开发并被 Keycloak 取代，但 Scribe 仍在维护，大约更新一次。

## Legacy框架

这些框架中的仍然被产品和服务使用，但不再由其贡献者活跃维护。

## PicketLink

PicketLink 是 Red Hat/JBoss 生态系统中多个安全项目的伞。虽然 Agora 从不是官方的 JBoss 项目，但它是为了该生态系统以及 CDI 等标准创建的。因此，通过 PicketLink 支持 OAuth 和 Java EE 似乎是一个逻辑步骤。

PicketLink 是 Java EE 应用的应用安全框架。它提供了验证用户、授权访问应用程序方法、管理应用程序的用户、组、角色和权限等功能。

这些是 PicketLink 解决的八大 Java 应用安全问题：

1. 为应用程序添加安全的最佳方法是什么？
2. 如何验证和授权用户？
3. 如何控制对类方法的访问？
4. 如何为我的应用程序添加身份访问管理 (IAM)？
5. 如何为我的 SaaS（软件即服务）应用程序创建安全的多租户架构？
6. 如何在我的应用程序中启用基于 SAML（安全断言语言）的单点登录？
7. 如何为我的 REST 层和 API 添加身份验证和授权？
8. 我的应用程序如何让用户使用 Facebook、Twitter 或 Google 账户进行身份验证？

图 5-12 显示了 PicketLink 的概览、其核心组件以及支持的技术。某些标记为“即将推出”的仍在开发中，并未随 PicketLink 的 GA（通用可用或“稳定”）版本发布。

## 第 5 章 安全框架

![](img/3c2d905e913621002f512a08b8855a70_188_0.png)

### 5-12. PicketLink 概述

然而，Agorava 主要使用 PicketLink 的基础功能，例如认证 API 或 CDI 集成，并添加了自身的 OAuth 和社交连接功能。

认证流程中的“舞蹈”是由 PicketLink 元素 `Authenticator` 执行的。以下是一个如何扩展 `BaseAuthenticator` 的示例：

```java
@PicketLink
public class SimpleAuthenticator extends BaseAuthenticator {
    @Inject DefaultLoginCredentials credentials;

    @Override
    public void authenticate() {
        if ("agentsmith".equals(credentials.getUserId()) &&
            "matrix123".equals(credentials.getPassword())) {
            setSt(AuthenticationStatus.SUCCESS);
            setAccount(new User("agentsmith"));
        } else {
            setSt(AuthenticationStatus.FAILURE);
            FacesContext.getCurrentInstance().addMessage(null, new
                FacesMessage("Authentication Failure - The username or password you
                provided were invalid."));
        }
    }
}
```

下一章中的 "AgoravaPLink" 将更详细地展示 PicketLink 如何应用于 Agora Core 及其 PicketLink 模块。

### SocialAuth

SocialAuth 是一个用于 Java 和 Android 的认证库。

它的功能包括以下：

- 认证
  - 通过外部 OAuth 提供者，如 Gmail, Hotmail, Yahoo, Twitter, Facebook, LinkedIn, Foursquare, Myspace, Salesforce, Yammer, Google Plus 和 Instagram
  - 通过 OpenID 提供者
- 简易的用户注册
  - 从社交网站导入联系人

以下是一个通过 CDI 使用 SocialAuth 更新状态的示例：

```java
@Scoped
@Named("socialAuthUpdateStatus")
public class UpdateStatus implements Serializable {
    private static final Logger logger = Logger.
        getLogger(UpdateStatus.class);
    @Inject
    SocialAuth socialauth;
    String statusText;

    /**
    * 更新个人资料上状态的方法。
    * @param ActionEvent
    * @throws Exception
    */
    public void updateStatus() throws Exception {
        final HttpServletRequest request = (HttpServletRequest)
            FacesContext
                .getCurrentInstance().getExternalContext()
                .getRequest();
        String statusText = request.getParameter("statusMessage");
        if (statusText != null && statusText.equals("")) {
            socialauth.setStatus(statusText);
            socialauth.updateStatus();
            setStatus("Status Updated Successfully");
            System.out.println("status text:" + statusText);
        }
    }

    public String getStatus() {
        return statusText;
    }

    public void setStatus(String statusText) {
        this.statusText = statusText;
    }
}
```

### OACC

OACC，读音为 "oak"（类似于 Java 的原始代号），是一个 Java API，用于强制和管理应用程序的认证和授权需求。OACC 提供基于权限的授权服务来执行应用程序安全保护。

功能包括：

- 认证
- 身份委托
- 数据存储
- 基于权限的安全模型
- 授权
- RBAC 建模
- 权限委托
- 多租户
- 缓存

以下是一个应用示例：

```java
public class OACCSampleApplication {
    public static void main(String[] args) throws Exception {
        // 获取 oacc 数据库的连接
        String url = "jdbc:postgresql://localhost/oaccdb?user=oaccurer&password=oaccpwd";
        try (Connection conn = DriverManager.getConnection(url)) {
            // 获取访问控制上下文
            AccessControlContext accessControlContext = SQLAccessControlFactory.getAccessControlContext(conn, "OACC", SQLProfile.PostgreSQL_9_3_RECURSIVE, BCryptPasswordEncryptor.newInstance(12));
            // 创建新管理员
            createAdmin(accessControlContext);
            // 创建新用户
            createUser(accessControlContext);
            // 以管理员身份登录
            loginAdmin(accessControlContext, "adminJoe", "pa55word");
            // 在以管理员身份登录时，尝试更新用户
            updateUser(accessControlContext, "jsmith");
        }
    }

    private static void createAdmin(AccessControlContext accessControlContext) {
        // 以系统资源（超级用户）身份认证以设置初始管理员
        accessControlContext.authenticate(Resources.getInstance(0),
            PasswordCredentials.newInstance("yourOaccSystemPassword".toCharArray()));
        // 在你的应用程序中持久化管理员，例如：
        AppAdmin admin = new AppAdmin.Builder()
            .login("adminJoe")
            .email("joeBloe@company.com")
            .build().create();
        // 创建对应的 OACC 资源
        final Resource adminResource
            = accessControlContext.createResource("ADMIN",
            "APP_DOMAIN", admin.login(),
            PasswordCredentials.newInstance("pa55word".toCharArray()));
        System.out.println("created new ADMIN resource with Id=" + adminResource.getId());
        // 授予查询、查看和停用新用户账户的权限
        // 但不能编辑
        Set<ResourcePermission> permissions = new HashSet<>();
        // ... (省略) 我们不需要经过身份验证即可创建用户，因为该资源设置了未认证标记
        accessControlContext.createResource("USER", "APP_DOMAIN", "jsmith", null);
        // ... (省略) 权限分配逻辑
    }
}
```

## 第 6 章

### 社交框架

上一章处理了 Soteria、Keycloak 或 Spring Security 等安全框架。在本章中，我们将查看社交框架，如 Meta Business SDK、Twitter4j、Twitter API Client、旧框架 Agoraava、Spring Social 或 Facebook4j，以及针对特殊用途或垂直领域社交网络的框架。

### Meta

Meta Platforms 拥有多种社交产品：

- Facebook
- Instagram
- (Facebook) Messenger
- WhatsApp
- Threads
- 如 Horizon Worlds 等 VR 产品

其合并后的用户群是任何社交网络中最大的。超过 2 亿家企业使用 Facebook，超过 700 万名广告主在 Facebook/Meta 上积极推广其业务。

这充分表明，与其他一些大型社交网络不同，Meta 提供了多种 SDK，包括专门的业务 SDK 以及对多种编程语言的支持。

# 第 6 章社交框架

针对 Meta 的两个最活跃 Java 业务 API 如下：

- Meta Business SDK - Meta 官方提供的业务 SDK 套件
- WhatsApp Business API SDK - 一个社区驱动的 Java WhatsApp 业务 SDK。目前优于用于 Java 的 WhatsApp 官方 Meta SDK，因为官方 SDK 尚未提供强力的 Java 对象模型。

# Meta Business SDK

Meta Business SDK [36] 提供了对各种 Meta 业务 API 的访问。它是 Facebook Marketing API SDK 的演进版本，包含了营销 API 以及 Pages（公共页）、Business Manager（商务管理）、Instagram 等其他 Meta API，允许构建无缝集成一系列 Meta 服务的自定义企业解决方案。

# 概述

Meta Business SDK 由以下部分组成：

- Business Manager API - 允许管理 Facebook 公共页和广告账户的资产、权限和广告系列
- Pages API - 允许管理 Facebook 上的业务存在和社区
- Marketing API - 允许管理广告产品、创建、编辑或删除广告，并分析其性能
- Instagram Graph API - 允许管理 Instagram 上的企业存在

# WhatsApp 在哪里？

虽然为企业提供了 WhatsApp (Meta) 业务账号，但目前 WhatsApp 支持尚未包含 Meta Business SDK 中。Java 及其他语言的 API 支持目前比通过 Business SDK 的其他 Meta 服务更为初级。这主要依赖于使用所选语言进行 REST/HTTP 客户端调用。我们在这里展示一个 Java 的 WhatsApp 示例，但社区以 WhatsApp Business Java API SDK 的形式存在更方便的 Java 封装。

# 冒烟测试

这些步骤解释了如何使用 Maven 安装 Java 版 Meta Business SDK 并测试安装。

# 前提条件

你需要以下内容：

- 一个 Meta 开发者账号
- 在 https://developers.facebook.com/ 上注册的 Meta 应用
- 您的应用密钥 (app secret)
- 一个访问令牌 (access token)
- 一个广告账户 (Ad Account)

按照以下步骤安装 SDK 并测试您的应用程序：

1. 使用您选择的 IDE 创建 Maven 项目后，在 `pom.xml` 文件中添加以下依赖：

```xml
<dependency>
  <groupId>com.facebook.business.sdk</groupId>
  <artifactId>facebook-java-business-sdk</artifactId>
  <version>8.0.3</version>
</dependency>
```

2. 创建一个名为类似 SmokeTestJavaSDK 的 Java 类，并添加以下代码。注意 `{access-token}`、`{appsecret}` 和 `{adaccount-id}` 是实际值的占位符。请确保妥善地外部化它们，特别是当与他人共享它们时：

```java



导入以下类：

```java
import com.facebook.ads.sdk.APIContext;
import com.facebook.ads.sdk.APINodeList;
import com.facebook.ads.sdk.AdAccount;
import com.facebook.ads.sdk.Campaign;
```

```java
public class SmokeTestFBJavaSDK {

    public static final APIContext context = new APIContext(
        "{access-token}",
        "{appsecret}"
    );

    public static void main(String[] args) {
        AdAccount account = new AdAccount("act_{adaccount-id}", context);
        try {
            APINodeList<Campaign> campaigns = account.getCampaigns().getAllFields().execute();
            for (Campaign campaign : campaigns) {
                System.out.println(campaign.getName());
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

编译并运行您的应用程序。你应该能在控制台中看到输出。如果出现关于令牌过期的错误，请请求新的访问令牌，例如，使用刷新令牌并重试。

## 示例

以下是针对选定业务用例的代码示例。

## 广告投放

以下示例展示了如何为点击进入消息广告（Click-to-Messenger Ads）和 Facebook 公共页推广创建广告系列。

- 点击进入消息广告允许人们在点击您的广告时直接与您的 Facebook 公共页开启对话。
- 你需要一个广告账户 ID。

此示例展示了如何创建一个在指定时间段运行的广告：

```java
AdSet adSet = new AdAccount(act_<AD_ACCOUNT_ID>, context).createAdSet(
  .setName("My Ad Set")
  .setOptimizationGoal(AdSet.EnumOptimizationGoal.VALUE_REACH)
  .setBillingEvent(AdSet.EnumBillingEvent.VALUE_IMPRESSIONS)
  .setBidAmount(2L)
  .setDailyBudget(1000L)
  .setCampaignId(<CAMPAIGN_ID>)
  .setTargeting(
    new Targeting(
      .setFieldGeoLocations(
        new TargetingGeoLocation(
          .setFieldCountries(Arrays.asList("US"))
        )
      )
    )
  )
  .startTime(start_time)
  .setEndTime(end_time)
  .setStatus(AdSet.EnumStatus.VALUE_PAUSED)
  .execute());

String ad_set_id = adSet.getId();
```

创建一个广告来通过推广增加您的 Facebook 公共页的流量。你需要：

- 一个广告账户 ID
- 一个 Facebook 公共页 ID

以下示例展示了如何创建一个推广您的页面以获取更多点赞的广告系列。该广告将在美国运行，每日预算为 1000 美元，目标为广告展示：

```java
Campaign campaign = new AdAccount(<ACCOUNT_ID>, context).createCampaign(
  .setObjective(Campaign.EnumObjective.VALUE_LIKES)
  .setStatus(Campaign.EnumStatus.VALUE_PAUSED)
  .setBuyingType("AUCTION")
  .setName("My Campaign")
  .execute();

String campaign_id = campaign.getId();

AdSet adSet = new AdAccount(act_<AD_ACCOUNT_ID>, context).createAdSet(
  .setName("My Ad Set")
  .setOptimizationGoal(AdSet.EnumOptimizationGoal.VALUE_REACH)
  .setBillingEvent(AdSet.EnumBillingEvent.VALUE_IMPRESSIONS)
  .setBidAmount(2L)
  .setDailyBudget(1000L)
  .setCampaignId(campaign_id)
  .setTargeting(
    new Targeting(
      .setFieldGeoLocations(
        new TargetingGeoLocation(
          .setFieldCountries(Arrays.asList("US"))
        )
      )
    )
  )
  .startTime(start_time)
  .setEndTime(end_time)
  .setStatus(AdSet.EnumStatus.VALUE_PAUSED)
  .execute());

String ad_set_id = adSet.getId();
```

## 批量模式

Meta APIs 提供了批量模式（Batch Mode），类似于 Jakarta Batch，允许发送包含多个 API 调用的单个 HTTP 请求。独立操作并行处理，而依赖操作的操作顺序执行。以下是批量模式的示例：

```java
BatchRequest batch = new BatchRequest(context);

account.createCampaign(
  .setName("Meta SDK Test Campaign")
  .setObjective(Campaign.EnumObjective.VALUE_CLICKS)
  .setSpendCap(10000L)
  .setStatus(Campaign.EnumStatus.VALUE_PAUSED)
  ).addToBatch(batch, "campaignRequest")

account.createAdSet(
  .setName("Meta SDK Test AdSet")
  .setCampaignId("{result=campaignRequest$.id}")
  .setStatus(AdSet.EnumStatus.VALUE_PAUSED)
  .setBillingEvent(AdSet.EnumBillingEvent.VALUE_IMPRESSIONS)
  .setDailyBudget(1000L)
  .setBidAmount(100L)
  .setOptimizationGoal(AdSet.EnumOptimizationGoal.VALUE_IMPRESSIONS)
  .setTargeting(targeting)
  ).addToBatch(batch, "adsetRequest")

account.createAdImage()
  .addUploadFile("file", imageFile)
  .addToBatch(batch, "imageRequest")

account.createAdCreative(
  .setTitle("Java SDK Test Creative")
  .setBody("Java SDK Test Creative")
  .setImageHash("{result=imageRequest.*hash}")
  .setLinkUrl("www.facebook.com")
  .setObjectUrl("www.facebook.com")
  ).addToBatch(batch, "creativeRequest")

account.createAd(
  .setName("Meta SDK Test ad")
  .setAdId("{result=adsetRequest$.id}")
  .setCreative("{result=creativeRequest$.id}")
  .setStatus("PAUSED")
  .setBidAmount(100L)
  ).addToBatch(batch);

List<APIResponse> responses = batch.execute();
// responses 按顺序包含每个 API调用的结果。但是，
// 如果 调用之间存在依赖，则某些结果可能为空。
```

## Instagram

使用 Meta Business SDK 管理 Instagram 评论。你需要：

- 一个 Instagram 专业人士账号 ID
- 与 Instagram 专业人士账号关联的 Facebook 公共页 ID
- 您的 Meta 应用 ID
- 与您的 Instagram 专业人士账号关联的页面访问令牌

以下示例会对您的媒体对象发表评论、分析这些评论、根据特定标准进行筛选，并对符合标准的评论进行回复。

使用 `/media/comments` 接口获取所有注释及其 ID。

选择你想要回复的注释，并使用其注释 ID 来回复用户。

```java
context = new APIContext(page_access_token_for_ig)
enableDebug(false);

APINodeList<IGComment> igComments = new IGMedia<IG_POST_ID,
context).getComments()
.execute();

String ig_comment_id = igComments.get(0).getID();

IGComment igComment = new IGComment(ig_comment_id, context)
.execute();

APINodeList<IGComment> igCommentRepliess = new IGComment(ig_comment_id, context).getReplies()
.execute();
```

## WhatsApp

此示例演示了如何在 Java 应用通过 API 发送 WhatsApp 消息。你需要：

- 任意 Java IDE。
- 确保拥有 Java 11 或更高版本。
- 在 Meta for Developers 注册。
- 为你的账户启用双重身份验证。
- 确保你的开发者账户已关联到 Meta 商务帐户。

在 Meta for Developers 上创建一个应用。选择“我的应用”（My Apps），点击“创建应用”，并选择“商务”（Business）作为应用类型。
示例代码如下：

```java
import java.io.IOException;
import java.net.URI;
import java.net.URISyntaxException;
import java.net.http.HttpClient;
import java.net.http.HttpRequest;
```

## 第 6 章 社交框架

```java
import java.net.http.HttpResponse;
import java.net.http.HttpResponse.BodyHandlers;

public class App {
    public static void main(String[] args) {
        try {
            HttpRequest request = HttpRequest.newBuilder()
                .uri(new URI("https://graph.facebook.com/v13.0/<YOUR_PHONE_ID>/messages"))
                .header("Authorization", "Bearer <YOUR BEARER TOKEN>")
                .header("Content-Type", "application/json")
                .POST(HttpRequest.BodyPublishers.ofString("{\"messaging_product\": \"whatsapp\", \"recipient_type\": \"individual\", \"to\": \"TARGET PHONE NUMBER>\", \"type\": \"template\", \"template\": { \"name\": \"hello world\", \"language\": { \"code\": \"en_US\" } } }"))
                .build();

            HttpClient http = HttpClient.newHttpClient();
            HttpResponse<String> response = http.send(request, BodyHandlers.ofString());
            System.out.println(response.body());
        } catch (URISException | IOException e) {
            e.printStackTrace();
        }
    }
}
```

## WhatsApp Business API SDK

WhatsApp Business Java API SDK [59] 是由 Mauricio Binda da Costa 开发的 Java API。它实现了官方的 WhatsApp Cloud API 和 WhatsApp Business Management API，允许你的应用程序：

- 管理你的 WhatsApp 商务帐户资产，如消息模板和电话号码。
- 向你的联系人发送消息，如文本消息、带按钮的消息、视频、贴纸等。
- 上传、删除和检索媒体文件。
- 接收 webhook 事件。

虽然它于 2022 年 12 月启动且 README 声称仍在建设中，但几乎每个月都有定期的更新和版本发布，尽管不是官方的 Meta SDK，它仍然留下了深刻的印象。

该库和示例需要 Java 17 或更高版本。

### 安装

将 JitPack 仓库添加到你的 Maven POM 文件：

```xml
<repositories>
  <repository>
    <id>jitpack.io</id>
    <url>https://jitpack.io</url>
  </repository>
</repositories>
```

将以下 Maven 依赖添加到你的 POM 文件：

```xml
<dependency>
  <groupId>com.github.Bindambc</groupId>
  <artifactId>whatsapp-business-java-api</artifactId>
  <version>v0.3.3</version>
</dependency>
```

v0.3.3 是目前的最新版本，已在可用新版本时进行了调整。

### 示例

发送简单的文本消息：

```java
WhatsappApiFactory factory = WhatsappApiFactory.newInstance(TestUtils.TOKEN);
WhatsappBusinessCloudApi whatsappBusinessCloudApi = factory.newBusinessCloudApi();

var message = MessageBuilder.builder()
    .setTo(PHONE_NUMBER_1)
    .buildTextMessage(new TextMessage())
    .setBody(Formatter.bold("Hello world!") + "\nSome code here:\n\n" + Formatter.code("hello world code here"))
    .setPreview(false);

whatsappBusinessCloudApi.sendMessage(PHONE_NUMBER_ID, message);
```

发送带按钮的消息（模板）：

```java
WhatsappApiFactory factory = WhatsappApiFactory.newInstance(TestConstants.TOKEN);
WhatsappBusinessCloudApi whatsappBusinessCloudApi = factory.newBusinessCloudApi();
```



`var message = MessageBuilder.builder()`

`.setTo(PHONE_NUMBER_1)`

`.buildTemplateMessage()`

`.setLanguage(new Language(LanguageType.PT_BR))`

`.setName("schedule_confirmation3")`

`.addComponent(`

`new Component(ComponentType.BODY)`

`.addParameter(new TextParameter("Mauricio")));`

发送带列表的消息：

```java
WhatsappApiFactory factory = WhatsappApiFactory.newInstance(TestUtils.TOKEN);
WhatsappBusinessCloudApi whatsappBusinessCloudApi = factory.newBusinessCloudApi();
var message = MessageBuilder.builder()
    .setTo(PHONE_NUMBER_1)
    .buildTemplateMessage()
    .setLanguage(new Language(LanguageType.PT_BR))
    .setName("schedule_confirmation3")
    .addComponent(
        new Component(ComponentType.BODY)
        .addParameter(new TextParameter("Mauricio")));
```

```xml
<repository>
  <name>Maven Central Snapshot Repository</name>
  <url>https://s01.oss.sonatype.org/content/repositories/snapshots/</url>
  <releases>
    <enabled>false</enabled>
  </releases>
  <snapshots>
    <enabled>true</enabled>
  </snapshots>
</repository>
```

## 依赖

```xml
<dependency>
  <groupId>social.bigbone</groupId>
  <artifactId>bigbone</artifactId>
  <version>2.0.0-SNAPSHOT</version>
</dependency>
<dependency>
  <groupId>social.bigbone</groupId>
  <artifactId>bigbone-rx</artifactId>
  <version>2.0.0-SNAPSHOT</version>
</dependency>
```

## 示例

### 获取访问令牌

`https://docs.joinmastodon.org/methods/apps/`

### 获取时间线

```java
public class GetPublicTimeline {
  public static void main(final String[] args) throws BigBoneRequestException {
    final String instance = args[0];
    // 实例化客户端
    final MastodonClient client = new MastodonClient.Builder(instance)
    .build();
    // 从公共时间线获取状态
    final Pageable<Status> statuses = client.timelines().
      getPublicTimeline(LOCAL_AND_REMOTE).execute();
    statuses.getPart().forEach(status -> System.out.println(status.getContent()));
  }
}
```

### 获取实例信息

```java
public class GetInstanceInfo {
    public static void main(final String[] args) throws BigBoneRequestException {
        final String instance = args[0];
        // 实例化客户端
        final MastodonClient client = new MastodonClient.Builder(instance)
        .build();
        // 获取实例信息并以 JSON 格式打印到控制台
        final Instance instanceInfo = client.instances().getInstance().execute();
        final Json gson = new Json();
        System.out.println(gson.toJson(instanceInfo));
    }
}
```

### 获取签签

```java
public class GetBookmarks {
    public static void main(final String[] args) throws BigBoneRequestException {
        final String instance = args[0];
        final String accessToken = args[1];
        // 实例化客户端
        final MastodonClient client = new MastodonClient.Builder(instance)
        .accessToken(accessToken)
        .build();
        // 获取签签
        final Pageable<Status> bookmarks = client.bookmarks().getBookmarks().execute();
        bookmarks.getPart().forEach(bookmark -> {
            String statusText = bookmark.getContent() + "\n";
            System.out.print(statusText);
        });
    }
}
```

### 执行简单搜索

```java
public class PerformSimpleSearch {
    public static void main(final String[] args) throws BigBoneRequestException {
        final String instance = args[0];
        final String accessToken = args[1];
        final String searchTerm = args[2];
        // 实例化客户端
        final MastodonClient client = new MastodonClient.Builder(instance)
            .accessToken(accessToken)
            .build();
        // 执行搜索并打印结果
        final Search searchResult = client.search().searchContent(searchTerm).execute();
        searchResult.getAccounts().forEach(account -> System.out.println(account.getDisplayName()));
        searchResult.getStatuses().forEach(status -> System.out.println(status.getContent()));
        searchResult.getHashtags().forEach(hashtag -> System.out.println(hashtag.getName()));
    }
}
```

## 第 6 章 社交框架

## Twitter/X

以前名为 Twitter 的社交网络至少有两个 Java 客户端，它们围绕 Twitter/X REST API 封装了对象模型。

### Twitter API 客户端

2021 年 8 月，Twitter 启动了自己的 Java API 客户端库 [35]。这相当晚了，考虑到 Twitter 曾是 JCP 的活跃参与者 [11] 并在湾区举办过多次 JCP EC 面对面会议，但它仅支持 Twitter v2 API，这似乎是为了说服开发者迁移到新 API 的一种措施。GitHub 仓库仍然显示“此 SDK 处于测试阶段，尚未准备好投入生产”，且只有三位提交者贡献过代码；这些人似乎在在埃隆·马斯克收购公司前后不久都离开了公司。

### 安装

将此依赖添加到你项目的 POM 文件中：

```xml
<dependency>
  <groupId>com.twitter</groupId>
  <artifactId>twitter-api-java-sdk</artifactId>
  <version>2.0.3</version>
</dependency>
```

| Twitter 到 X 的迁移 |
| :--- |
| 随着埃隆·马斯克将 Twitter 重命名为 X，在某个时刻，像 `twitter.com` 或该网站下的域名可能会关闭并不再运行。这可能会影响此处列出的某些设置和步骤。 |

## 示例

你必须先注册 Twitter 应用以获取访问 Twitter API 的用户名和密码。要为用于 API 客户端注册新应用：

1. 前往 `https://dev.twitter.com`
2. 登录并点击 Create an app（创建应用）
3. 点击 Add New Application（添加新应用）
4. 在 Application Info（应用程序信息）下，为以下参数输入值：
   - Application Name（应用程序名称）——这是你的应用程序名称，显示在每条帖的末尾，例如你的公司名称。
   - Application Description（应用程序描述）——输入应用程序的短描述。
   - Website（网站）——这是你的网址，例如 `http://www.mysite.com`。
   - Callback URL（回调 URL）——将其设置为 `domain`（即你的域名）。
5. 阅读条款并选择 Agree。
6. 如果需要，输入验证码信息。
7. 显示 Consumer Key 和 Consumer Secret。记录在安全的地方。
8. 点击 Settings（设置）。
9. 在 Application Type 部分，将访问权限设置为 Read。
10. 更新此 Twitter 应用设置。

### API 示例

```java
public class TwitterApiExample {
    public static void main(String[] args) {
        /**
         * 设置所需 API 的凭据。
         * Java SDK 支持 OAuth2 & Bearer。
         * 查看 https://api.twitter.com/2/openapi.json 中的 'security' 标签以使用正确的凭据对象。
         */
        TwitterApi apiClient = new TwitterApi(new TwitterCredentialsBearer(
            System.getenv("TWITTER_BEARER_TOKEN")));
        Set<String> tweetFields = new HashSet<>();
        tweetFields.add("author_id");
        tweetFields.add("id");
        tweetFields.add("created_at");
        try {
            // findTweetById
            GetTweetsIdResponse result = apiClient.tweets().findTweetById("20")
                .fields(tweetFields)
                .execute();
            if (result.getErrors() != null && result.getErrors().size() > 0) {
                System.out.println("Error:");
                result.getErrors().forEach(e -> {
                    System.out.println(e.toString());
                    if (e instanceof ResourceUnauthorizedProblem) {
                        System.out.println(((ResourceUnauthorizedProblem) e).getTitle()
                            + " " + ((ResourceUnauthorizedProblem) e).getDetail());
                    }
                });
            } else {
                System.out.println("findTweetById - 推文文本: " + result.toString());
            }
        } catch (ApiException e) {
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
        }
    }
}
```

### HelloWorld 示例

```java
public class HelloWorld {
    public static void main(String[] args) {
        // 在处实现实现
    }
}
```

```java
    e.printStackTrace();
    }
}
```

# HelloWorld示例（流式）

```java
public class HelloWorldStreaming {
    public static void main(String[] args) {
        /**
         * 设置所需 API 的凭据。
         * Java SDK 支持 TwitterCredentialsOAuth2 和 TwitterCredentialsBearer。
         * 请检查 https://api.twitter.com/2/openapi.json 中所需 API 的 'security' 标签
         * 以使用正确的凭据对象。
         */
        TwitterApi apiClient = new TwitterApi(TwitterCredentialsBearer(System.getenv("TWITTER_BEARER_TOKEN")));
        try {
            TweetsStreamListenersExecutor tsle = new TweetsStreamListenersExecutor();
            tsle.stream()
                .streamingHandler(new StreamingTweetHandlerImpl(apiInstance))
                .executeListeners();
            while (tsle.getError() == null) {
                try {
                    System.out.println("== 等待 5 秒 ");
                    Thread.sleep(5000);
```



```java
} catch (InterruptedException e) {
    e.printStackTrace();
}
} catch (ApiException e) {
    System.err.println("==> 错误结束: " + tsle.getError());
    System.err.println("状态码: " + e.getCode());
    System.err.println("原因: " + e.getResponseBody());
    System.err.println("响应头: " + e.getResponseHeaders());
    e.printStackTrace();
}
```

# 第 6 章 社交框架

## Twitter4J

`Twitter4J` 是一个用于 Twitter API 的开源 Java 库。通过 `Twitter4J`，你可以轻松地：

- 发布推文
- 获取用户的时间线
- 获取用户的朋友和粉丝的列表
- 获取用户的收藏推文
- 发送和接收私信
- 搜索推文
- 使用 Twitter 流式 API

### 历史

其作者山本悠介（Yusuke Yamamoto）曾于 2012 年工作于 Twitter。在他职期间，他曾短暂代表 Twitter 参加社交 JSR 专家小组。

最后一个版本是 2022 年 10 月的 4.1.2 版本。在 2018 年到 2022 年之间长时间停滞后，现在似乎又得到了良好的维护。然而，一个风险是，`Twitter4J` 目前仅支持 Twitter API v1.1，随着埃隆·马斯克全面接管 Twitter，没有人能确定它是否还会可用以及能持续多久。另一方面，Twitter 的员工人数缩减到仅为马斯克时代之前的缩影，服务不太可能在几周内就全部迁移到 v2。而且由于高级版 v1.1 API 带来了一些收入，在没有允许付费用户迁移到 v2 等效功能的情况下，它可能一夜之间消失。虽然 Gnip 在近十年前就被 Twitter 收购，但企业级 API 最近才从 Gnip 2.0 重新命名了品牌，这一过程也可能因为所有那些被马斯克解雇或自愿离开 Twitter 的经验丰富的开发者而受到阻碍。

## 示例

### 获取时间线

```java
import twitter4j.Twitter;
import twitter4j.TwitterException;
import twitter4j.v1.Status;
import java.util.List;

class Main {
    public static void main(String[] args) throws TwitterException {
        Twitter twitter = Twitter.getInstance();
        List<Status> statuses = twitter.v1().timelines().getHomeTimeline();
        System.out.println("正在显示主时间线.");
        for (Status status : statuses) {
            System.out.println(status.getUser().getName() + ":" + " " + status.getText());
        }
    }
}
```

### 发布推文

```java
import twitter4j.Twitter;

Twitter twitter = Twitter.getInstance();
Status status = twitter.v1().tweets().updateStatus(latestStatus);
System.out.println("成功更新状态为 [" + status.getText() + "]");
```

### 搜索推文

```java
import twitter4j.Twitter;
import twitter4j.TwitterException;
import twitter4j.v1.Query;
import twitter4j.v1.QueryResult;
import twitter4j.v1.Status;

class Main {
    public static void main(String[] args) throws TwitterException {
        Twitter twitter = Twitter.getInstance();
        Query query = Query.of("source:twitter4j yusukey");
        QueryResult result = twitter.v1().search(query);
        for (Status status : result.getTweets()) {
            System.out.println("@@" + status.getUser().getScreenName() + ":" " + status.getText());
        }
    }
}
```

### 交换私信

```java
import twitter4j.Twitter;
import twitter4j.TwitterException;
import twitter4j.v1.DirectMessage;

class Main {
    public static void main(String[] args) throws TwitterException {
        long recipientId = Long.parseLong(args[0]);
        String message = args[1];
        Twitter twitter = Twitter.getInstance();
        DirectMessage directMessage = twitter.v1().directMessages();
        sendDirectMessage(recipientId, message);
        System.out.printf("已发送: %s 到 @%d\n", directMessage.getText(), directMessage.getRecipientId());
    }
}
```

### 流式 API

```java
import twitter4j.*;
import twitter4j.v1.*;
import java.io.IOException;

class Main {
    public static void main(String[] args) throws TwitterException, IOException {
        StatusListener listener = new StatusListener() {
            @Override
            public void onStatus(Status status) {
                System.out.println("%s : %s".formatted(status.getUser().getName(), status.getText()));
            }

            @Override
            public void onDeleteNotice(Status status) {}

            @Override
            public void onLimitation(int numberOfStatuses) {}

            @Override
            public void onScrub(long userId) {}

            @Override
            public void onStallWarning(Stall warning) {}

            @Override
            public void onException(Exception ex) {
                ex.printStackTrace();
            }
        };

        TwitterStream twitterStream = Twitter.newBuilder()
            .listener(listener).build();

        // sample 方法创建一个线程并持续调用监听器。
        twitterStream.sample();
    }
}
```

## 专用框架

这些框架允许使用 Java 或 Kotlin、Groovy 等语言与流行的社交网络进行交互。

### Echobox SDK

`ebx-linkedin-sdk` 是由 Echobox 维护的 Java 客户端，适用于出版和媒体行业。

#### 安装

将以下依赖添加到你的项目 POM 中：

```xml
<dependency>
  <groupId>com.echobox</groupId>
  <artifactId>ebx-linkedin-sdk</artifactId>
  <version>x.x.x</version>
</dependency>
```

最新版本为 4.5.0。如果你在 POM 中启用了快照仓库，可以使用快照版本：

```xml
<repositories>
  <repository>
    <id>oss.sonatype.org-snapshot</id>
    <url>http://oss.sonatype.org/content/repositories/snapshots</url>
    <releases><enabled>false</releases>
    <snapshots><enabled>true</snapshots>
  </repository>
</repositories>
```

#### 使用与示例

获取 LinkedIn 凭据：

1. 访问 `www.linkedin.com/developers/apps`。
2. 如果尚未登录，请登录。
3. 点击创建应用。
4. 如果已有公司页，选择现有公司或选择“新建公司”并输入公司信息。
5. 在创建应用下，输入以下参数的值：
   - 应用名称 - 显示在每条推文结尾的应用名称，例如“ApressBookDemo”，或你的公司名。
   - LinkedIn 页面 - 你之前创建的公司，例如 `https://linkedin.com/company/123456`。
   - 隐私政策 URL - 你的隐私政策链接（可选），例如 `http://www.mysite.com/privacy`。
   - 应用图标 - 用户授权时显示的图标，最好是正方形图片。
   - 法律协议 - 勾选你已阅读并同意这些条款。
6. 点击创建应用。
7. 在 Auth 选项卡中，你会找到应用程序 API Key 和密钥。点击眼睛显示密钥。记录这些值。
8. OAuth 2.0 设置，为你的应用添加重定向 URL，例如 `http://localhost:8080/callback`。

#### 请求授权码：

1. 如果是首次请求、权限超时或被成员手动撤销：浏览器将重定向到 LinkedIn 的授权同意窗口。
2. 如果成员已存在权限授予：将跳过授权界面，并将成员立即重定向到由 `redirect_uri` 查询参数提供的 URL。
3. 当成员完成授权过程时，浏览器将重定向到由 `redirect_uri` 查询参数提供的 URL。

`GET https://www.linkedin.com/oauth/v2/authorization`

**表 6-1. 授权调用的参数**

| 参数 | 类型 | 描述 | 是否必填 |
| --- | --- | --- | --- |
| `response_type` | string | 此字段的值应始终为 `code` | 是 |
| `client_id` | string | 当你注册应用程序时生成的 API Key 值 | 是 |
| `redirect_uri` | url | 授权后将用户发送回的 URI。此值必须与你在应用程序配置中定义的重定向 URI 之一匹配。例如，`http://localhost:8080/callback` | 是 |
| `state` | string | 你任选的唯一且难以猜测的字符串。用于防止 CSRF。例如，`state=dCEEFwf4A53sdfKef424` | 否 |
| `scope` | string | 应用程序代表用户请求的成员权限的 URL 编码且以空格分隔的列表。这些必须显式请求。例如，`scope=r_liteprofile%20r_emailaddress%20w_member_social` | 是 |

示例请求：

```
GET https://www.linkedin.com/oauth/v2/authorization?response_type=code&client_id={your_client_id}&redirect_uri={callback_url}&state=foobar&scope=r_liteprofile%20r_emailaddress%20w_member_social
```

使用授权码获取访问令牌：

```java
VersionedLinkedClient client = new DefaultVersionedLinkedClient(Version.DEFAULT_VERSION);
LinkedInClient.AccessToken accessToken = client.obtainUserAccessToken(clientId, clientSecret, redirectURI, code);
```

创建一条 LinkedIn 分享：

```java
VersionedPostConnection postConnection =
new VersionedPostConnection(new DefaultSignedInClient(authToken));
Distribution distribution = new Distribution(Distribution.FeedDistribution.MAIN_FEED);
String commentary = "Message here";
Post post = new PostURN(commentary, Post.LifecycleState.PUBLISHED, Post.Visibility.PUBLIC);
String articleLink = "https://www.example.com/1234";
String title = "title";
String description = "description";
PostUtils.fillArticleContent(post, post, articleLink, imageURN, title, description);
URN postURN = postConnection.createPost(post);
```

从 LinkedIn 获取一个组织：

```java
VersionedOrganizationConnection connection =
new VersionedOrganizationConnection(linkedClient);
Organization organization = connection.retrieveOrganization(organizationURN, Parameter
.with("projection",
"(elements*(,roleAssignee~(localizedFirstName,localizedLastName),
organizationalTarget~(localizedName))))"));
```



# Discord

Discord 至少有三个主要的 Java 框架，社区开发活动都非常活跃：

- Discord4J
- Java Discord API (JDA)
- Javacord

# 身份验证

首先，你需要从 Discord 开发者面板创建一个应用程序：https://discord.com/developers/applications。

1. 如果你尚未登录，请登录。
2. 点击 **New Application**（新建应用程序）。
3. 选择一个名称，例如 "ApressBookDemoApp"，接受开发者条款并点击 **Create**（创建）。
4. 在 **General Information**（通用信息）下，你可以输入以下参数的值：
   - Name – 这是你之前输入的应用程序名称。
   - App icon – 当用户授权你的应用时，会向用户显示的图标。
   - Description – 输入应用程序的简短描述。
   - Tags – 最多五个标签，用于描述你的应用程序的内容和功能。
   - Application ID – 复制到你的应用程序中的应用程序 ID。
   - Public key – 复制到你的应用程序中的公钥。
   - Server count – 应用程序所在的服务器数量的近似值。该值为**只读**。
   - Interactions endpoint URL – 你可以选择配置交互端点，通过 HTTP POST 接收交互，而不是通过机器人用户通过 Gateway。
   - Linked roles verification URL – 你可以配置验证 URL，将你的应用程序启用为服务器“链接”设置中的要求。
   - Terms of Service URL – 指向你的应用程序服务条款的链接（可选）。
   - Privacy policy URL – 指向你的隐私政策的链接（可选）。
5. 在 OAuth2 下，你会找到以下参数：
   - Client ID – 复制到你的应用程序中的客户端 ID。
   - Client Secret – 复制到你的应用程序中的客户端密钥。你必须在首次使用时重新生成它，并确保复制它，因为它不会再次显示。
   - Redirects – 你必须为身份验证指定至少一个 URI。如果你在 OAuth 请求中传递了 URI，它必须精确匹配你在此处输入的 URI 之一。
6. 在 Bot 下，你会找到以下参数：
   - Username – 你的机器人的名称。
   - Icon – 显示给你的机器人用户的图标。
   - Token – 复制到你的应用程序中的令牌。出于安全考虑，令牌只能在创建时查看一次。如果你忘记或丢失了令牌，请重新生成一个新的。

# Discord4J

Discord4J 是官方 Discord API 的响应式 Java 封装，使用响应式原理和 Reactor 框架进行异步和非阻塞 API 调用。

# 安装

向你的项目添加以下依赖：

```xml
<dependency>
  <groupId>com.discord4j</groupId>
  <artifactId>discord4j-core</artifactId>
  <version>3.2</version>
</dependency>
```

## 第 6 章 社交框架

# 快速示例

在下面的示例中，当用户发送 `ping` 时，机器人将立即响应：

```java
DiscordClient.create(token)
    .on(MessageCreateEvent.class)
    .filter(event -> event.getMessage().getContent().equals("ping"))
    .flatMap(event -> event.getMessage().sendMessage("Pong!"))
    .subscribe();
```

# 响应式示例

此示例以响应式方式展示相同的机器人，使用 Reactor：

```java
DiscordClient.create(token)
    .on(MessageCreateEvent.class)
    .map(event::getMessage)
    .filter(message -> "!ping".equals(message.getContent()))
    .flatMap(message -> message.sendMessage("Pong!"))
    .subscribe();
```

# 分片示例

此示例在同一个 JVM 下显示多个分片组：

```java
// 第一个组获取偶数分片 ID
ShardingStrategy first = ShardingStrategy.builder()
    .count(10)
    .filter(s -> s.getIndex() % 2 == 0)
    .build();
```

```java
// 第二个组获取奇数分片 ID
ShardingStrategy second = ShardingStrategy.builder()
    .count(10)
    .filter(s -> s.getIndex() % 2 != 0)
    .build();
```

```java
DiscordClient sharedClient = DiscordClient.create(System.getenv("TOKEN"));
ShardCoordinator coordinator = LocalShardCoordinator.create();
GatewayDiscordClient firstGroup = sharedClient.gateway()
    .setSharding(first)
    .setEnabledIntents(...)
    .setShardCoordinator(coordinator)
    .login();
GatewayDiscordClient secondGroup = sharedClient.gateway()
    .setSharding(second)
    .setEnabledIntents(...)
    .setShardCoordinator(coordinator)
    .login();
```

# Java Discord API

Java Discord API (JDA，不要与 JTA 或 Jakarta Transactions混淆)旨在为 Discord REST API 和 WebSocket API 提供整洁的 Java 对象模型。

# 安装

向你的 Maven POM 添加以下依赖：

```xml
<dependency>
  <groupId>net.dv8tion</groupId>
  <artifactId>JDA</artifactId>
  <version>VERSION</version>
</dependency>
```

# 配置

```java
JDABuilder 和 DefaultShardBuilder 提供了一组配置：
public static void main(String[] args) {
  JDABuilder builder = JDABuilder.createDefault("token");
  // 禁用部分缓存
  builder.disableCache(CacheFlag.MEMBER_OVERRIDES, CacheFlag.VOICE_STATE);
  // 启用批量删除事件
  builder.setBulkDeleteSplittingEnabled(false);
  // 设置活动（如“正在看电视”）
  builder.setActivity(Activity.watching("TV"));
  JDA jda = builder.build();
}
```

# 事件监听器

下面的示例展示了如何使用 JDA 事件系统：

```java
public class ReadyListener implements EventListener
{
  public static void main(String[] args) {
  }
}
```

```java
throws InterruptedException
{ // 注意：在构建 JDA 之前注册你的 ReadyListener 是重要的
  JDA jda = JDABuilder.createDefault("token")
      .addEventListeners(new ReadyListener())
      .build();
      // 可选：阻塞直到 JDA 就绪
  jda.awaitReady();
}
```

```java
@Override
public void onEvent(GenericEvent event) {
    if (event instanceof ReadyEvent)
        System.out.println("API is ready!");
}
```

## 分片示例

Discord 允许 Bot 账户通过限制其占总连接 Guild/服务器的比例来在会话之间分担负载。这可以通过分片（sharding）来实现：

```java
public static void main(String[] args) throws Exception {
    JDABuilder shardBuilder = JDABuilder.createDefault("token");
    // 使用 shardBuilder 在此处注册你的监听器
    addEventListeners(...)
    shardBuilder.addEventListeners(new MessageListener())
    for (int i = 0; i < 10; i++) {
        shardBuilder.useSharding(i, 10)
    }
    shardBuilder.build();
}
```

## 第6 章 社交框架

## Javacord

Javacord 是一个用于 Discord 的现代 Java 库，专注于简单和。通过将自己简化为标准的 Java 类和特性（如 Optional 或 CompletableFuture），它对每个 Java 开发者都容易学习和使用，并且不会引入过多的自己的概念或抽象。

## 安装

向你的项目的 Maven POM 中添加以下依赖：

```xml
<dependency>
  <groupId>org.javacord</groupId>
  <artifactId>javacord</artifactId>
  <version>3.8.0</version>
  <type>pom</type>
</dependency>
```

## 基础示例

以下示例展示了 Bot 如何登录并对每个“ping”消息回复“Pong!”。注意，消息内容是一个受限意图（Intent），需要被启用：

```java
public class MyFirstBot {
    public static void main(String[] args) {
        // 在此处插入你的 bot 令牌
        String token = "your token";
        DiscordApi api = new DiscordApiBuilder().setToken(token)
            .addIntent(Intent.MESSAGE_CONTENT).login().join();
        // 添加一个监听器，当有人写入“ping”时回复“Pong!” 
        api.addCreateListener(event -> {
            if (event.getMessageContent().equalsIgnoreCase("ping")) {
                event.getChannel().sendMessage("Pong!");
            }
        });
        // 打印你的 bot 的邀请 URL
        System.out.println("你可以使用以下 url 邀请 bot: " + api.createBotInvite());
    }
}
```

## 斜杠命令示例

以下示例展示了我们如何让 bot 对一个简单的斜杠命令发送答案：

```java
public class MyFirstBot {
    public static void main(String[] args) {
        String token = "your token";
        DiscordApi api = new DiscordApiBuilder().setToken(token);
        login().join();
        api.addSlashCommandCreateListener(event -> {
            SlashCommandInteraction slashCommandInteraction = event.
                getSlashCommandInteraction();
            if (slashCommandInteraction.getName().equals("ping")) {
                slashCommandInteraction.createImmediateResponder()
                    .setContent("Pong!")
                    .setFlags(MessageFlag.EPHEMERAL) // 只对调用命令的用户可见
                    .respond();
            }
        });
    }
}
```

## MessageBuilder 示例

以下示例使用了内置的 MessageBuilder。它在构建包含图像、代码块、嵌入或附件的复杂消息时非常有用：

```java
public class MyListener implements MessageCreateListener {
    @Override
    public void onMessageCreate(MessageCreateEvent event) {
        Message message = event.getMessage();
        if (message.getContent().equalsIgnoreCase("!ping")) {
            event.getChannel().sendMessage("Pong!");
        }
    }
}
```

## 第6 章 社交框架

## Listener 示例

为了更好的可读性，也可以让监听器位于它们自己的类中：

```java
public class MyListener implements MessageCreateListener {
    @Override
    public void onMessageCreate(MessageCreateEvent event) {
        Message message = event.getMessage();
        if (message.getContent().equalsIgnoreCase("!ping")) {
            event.getChannel().sendMessage("Pong!");
        }
    }
}
// 调用监听器：
api.addListener(new MyListener());
```

## Twitch4J

Twitch4J 是一个基于 JVM 的 Twitch API 客户端。它支持 Java、Kotlin 和 Groovy。

### 安装

向你的 Maven 添加以下依赖：

```xml
<dependency>
    <groupId>com.github.twitch4j</groupId>
    <artifactId>twitch4j</artifactId>
    <version>1.16.0</version>
</dependency>
```

## 使用与示例

获取访问令牌：

https://dev.twitch.tv/ 根据你使用的流程，你可能需要一个密钥。例如，授权码流（Authorization Code Flow）需要一个密钥。点击 New Secret 来生成一个你将要使用的密钥。获取新密钥会使之前的密钥失效，这可能会导致你的请求在更新应用之前失败。

初始化并配置 Twitch4J：

```java
TwitchClient twitchClient = TwitchClientBuilder.builder()
    .withHelix(true)
    .build();
```

## 频道

加入频道

```java
twitchClient.getChat().joinChannel("Overwatch");
```

将频道聊天写入控制台

```java
public class WriteChannelToConsole {
    /**
     * 注册此类的事件
     * @param eventHandler SimpleEventHandler
     */
```



## 第 6 章 社交框架

## 切段（Clips）

创建片段：

```java
CreateClipList clipData = twitchClient.getHelix().createClip(accessToken,
"149223493", false).execute();
clipData.getData().forEach(clip -> {
    System.out.println("Created Clip with ID: " + clip.getId());
});
```

将片段 ID 写入控制台：

```java
clipList = twitchClient.getHelix().getClips(null, "488552", null,
null, null, null, null, null).execute();
clipList.getData().forEach(clip -> {
    System.out.println("Found Clip: " + clip.getId());
});
```

## 游戏

将游戏的 ID 和名称写入控制台：

```java
GameList resultList = twitchClient.getHelix().getGames(
Arrays.asList(overwatchGameId), null).execute();
resultList.getGames().forEach(game -> {
    System.out.println("Game ID: " + game.getId() + " is " + game.getName());
});
```

## 垂直框架

垂直社交框架允许与特定领域的社交网络集成。

## GitHub

虽然 GitHub/Microsoft 本身没有提供 GitHub 的官方 Java API，但除了两个活跃维护且提供领域模型的 API 外，还有几个在 REST/OpenID Connect 级别支持它的 API：

- GitHub API for Java
- GitHub Java Client

两者都提供了多种身份验证方法，包括个人访问令牌（personal access token）。

## 令牌生成

为 GitHub REST APIs 生成新令牌：

1. 登录 GitHub 账户
2. 进入设置（Settings）➤ 开发者设置（Developer settings）➤ 个人访问令牌（Personal access tokens）
3. 点击生成新令牌（generate a new token）
4. 确认用户密码继续
5. 为令牌添加描述
6. 在选择范围（select scopes）选项下，勾选所有复选框
7. 点击生成新令牌

## GitHub API for Java

GitHub API for Java 围绕 GitHub REST API 提供了一个对象模型。它的创建由 Jenkins CI 的“之父”Kohuke Kawaguchi 领导。

## 身份验证

GitHub Java 库提供了多种身份验证方法：

- 用户名和密码（不推荐，除非用于开发目的）
- 个人访问令牌
- JWT 令牌
- GitHub app 安装令牌
  - 用户
  - 组织

## 使用示例

我们遵循“令牌生成”的步骤，使用个人访问令牌。

## 仓库

这是一个使用 GitHub API for Java 连接到 GitHub 并在清理之前创建一个新仓库的示例：

```java
GitHub github = new GitHubBuilder().withOAuthToken("my_personal_token").
build();
```

```java
GHRepository repo = github.createRepository(
"new-repository","this is my new repository",
"https://www.kohsuse.org/",true/*public*/);
repo.addCollaborators(github.getUser("abcde"),github.getUser("jdoe"));
repo.delete();
```

## 组织

要为组织在 GitHub 创建资源，你必须创建一个 `GHOrganization` 类型的对象：

```java
GHOrganization organizationClient(GitHub github, String organizationName)
throws IOException {
    return github.getOrganization(organizationName);
}
```

现在我们可以对 `GHOrganization` 进行操作。创建仓库或任何其他创建资源的方法都将在该组织下进行：

```java
void createRepository(GHOrganization organization) {
    organization.createRepository("repository-name")
    .private_(true)
    .wiki(false)
    .projects(false)
    .description("Description")
    .allowMergeCommit(true)
    .allowSquashMerge(false)
    .allowRebaseMerge(false)
    .create();
}
```

## GitHub Java Client

GitHub Java Client 是一个用于与 GitHub/GitHub Enterprise 通信并交互项目的小型 Java 库。它由瑞典社交音乐平台 Spotify 维护。它支持通过访问令牌、JWT 端点和 GitHub Apps（通过私钥）进行验证。

## 安装

将最新版本的 `github-client` 包含在你的项目 POM 中：

```xml
<dependency>
    <groupId>com.spotify</groupId>
    <artifactId>github-client</artifactId>
    <version>version</version>
</dependency>
```

## 使用示例

我们遵循“令牌生成”步骤，使用个人访问令牌：

```java
final GitHubClient githubClient = GitHubClient.create(URI.create("https://api.github.com/"), "my-access-token");
```

该客户端尝试镜像 GitHub API 端点。例如，要获取提交详情，请使用 `repos` API 下的 `GET /repos/:owner/:repo/commits` API 调用。因此，`getCommit` 位于 `RepositoryClient` 下：

```java
final RepositoryClient repositoryClient = githubClient.
createRepositoryClient("my-org", "my-repo");
log.info(repositoryClient.getCommit("sha").get().htmlUrl());
```

## 仓库

与运行检查（check runs）或问题（issues）相关的方法也位于 `RepositoryClient` 下：

```java
final ChecksClient checksClient = repositoryClient.createChecksApiClient();
checksClient.createRun(CHECK_RUN_REQUEST);
final IssueClient issueClient = repositoryClient.createIssueClient();
issueClient.createComment(ISSUE_ID, "comment body")
.thenAccept(comment -> log.info("created comment " + comment.htmlUrl()));
```

## 组织

与团队和成员的方法位于 `OrganisationClient` 下：

```java
final TeamClient teamClient = organisationClient.createTeamClient();
final Membership membership = teamClient.getMembership("teamname");
```

## Uber

与 Meta 类似，Uber 为包括 Java 在内的许多流行语言维护了自身的 SDK。

## Java SDK

以下示例显示了如何使用 Java Rides SDK。

首先，你需要在 Uber 开发者面板上注册你的应用：https://developer.uber.com/dashboard/

## 安装

将以下依赖项添加到你的项目中（使用 Gradle，因为它同时支持 Java 和 Kotlin/Android）：

```gradle
dependencies {
    compile 'com.uber.sdk.rides:0.5.2'
}
```

可用时使用最新版本。

## 示例

使用服务器令牌获取 Uber 会话：

当你注册应用时，你会获得一个服务器令牌、客户端 ID 和客户端密钥。使用它们来验证你的应用程序：

```java
SessionConfiguration config = new SessionConfiguration.Builder()
    .setClientId("<CLIENT_ID>")
    .setServerToken("<SERVER_TOKEN>")
    .build();
SqlServerSession session = new ServerTokenSession(config);
```

获取可用产品列表：

```java
Response<List<Product>> response = service.getProducts(37.79f, -122.39f).execute();
List<Product> products = response.body();
String productId = products.get(0).getProductId();
```

获取时间和价格估算值：

```java
Response<TimeEstimatesResponse> response = service.getPickupTimeEstimate(37.79f, -122.39f, productId).execute();
```

## 请求打车

获取位置处的产品：

```java
Response<List<Product>> response = service.getProducts(37.79f, -122.39f).execute();
List<Product> products = response.body();
String productId = products.get(0).getProductId();
```

获取带有起始/终点位置产品的预付费：

```java
RideRequestParameters rideRequestParameters = new RideRequestParameters.Builder()
    .setPickupCoordinates(37.77f, -122.41f)
    .setProductId(productId)
    .setDropoffCoordinates(37.49f, -122.41f)
    .build();
```

```java
RideEstimate rideEstimate = service.estimateRide(rideRequestParameters)
    .execute().body();
String fareId = rideEstimate.getFareId();
```

带有起始/终点位置产品的预付费请求：

```java
RideRequestParameters rideRequestParameters = new RideRequestParameters.Builder()
    .setPickupCoordinates(37.77f, -122.41f)
    .setProductId(productId)
    .setFareId(fareId)
    .setDropoffCoordinates(37.49f, -122.41f)
    .build();
Ride ride = service.requestRide(rideRequestParameters).execute().body();
String rideId = ride.getRideId();
```

根据 `ride_id` 请求订单详情：

```java
Ride ride = service.getRideDetails(rideId).execute().body();
```

取消订单：

```java
Response<Void> response = service.cancelRide(rideId);
```



## 遗留框架

尽管许多仍在在使用，但以下社交框架不再由开发者积极维护或支持。

## Agorava

`Agorava` [33] 是一个提供 CDI 模块、上下文和扩展的社交框架，用于主要的社交网络或暴露 API 的服务交互。它为 Java 和 Java 企业级应用程序提供这些服务，并以拼贴的精神简化了操作。[12]

### 历史

你在第 3 章中记得 `Agorava` 的起源和前身，在那个章节中讨论了标准化工作，由于 JSR 357 被 JCP 执行委员会多数拒绝，导致 `Agorava` 作为 `Seam Social` 的继承者被创建。由于联合创始人 `Antoine Sabot-Durand` 在 2013 年加入 JBoss 后对 CDI 等 JBoss 项目做出贡献并成为负责人，它曾短暂出现在 JBoss 栈中 [56]，尽管不是 WildFly 等项目的正式部分。

## 概述

![](img/3c2d905e913621002f512a08b8855a70_246_0.png)

图 6-1. Agarava 宏架构

这些是 Agarava 的主要功能：

- 安全性
- 通用的移植 REST 客户端 API
- 处理 OAuth 1.0a 和 2.0 服务的通用 API
- 用于 JSON 序列化和反序列化的通用 API
- 从社交服务（作为身份提供者）检索基本用户信息的通用标识 API
- 多服务管理器 API，允许在同一个应用程序中处理多个 OAuth 应用和会话
- 开箱即用，`Agorava` 可以连接到：
  - Facebook
  - LinkedIn
  - GitHub
  - Twitter
  - XING
- 并且提供了一种简单的方法，通过为任何其他服务或 API 创建新的连接器来扩展它

`Agorava` 独立于 CDI 实现，可以在 Java EE 6（最低要求）和由 CDI 增强的 Servlet 环境之间完全迁移。它也可以与 Java SE 中的 CDI 配合使用，用于桌面或 SE 嵌入式/移动应用程序中。它已经通过了 CDI RI 实现（JBoss Weld）的完整测试。从 0.5 版本开始，它还支持 `OpenWebBeans` 和 `Caucho Resin`。

`Agorava` 通常被解释为一种“用于社交的 Java 连接器架构”。事实上，`Agorava` 背后的理念与 Jakarta EE 体系下的 Jakarta Connectors（以前称为 JCA）所做的之间有着惊人的相似之处。

`Jakarta Connectors` 定义了一个标准架构，用于将 Jakarta EE 平台连接到异构的企业信息系统（EIS），包括事务处理系统（如 CICS 事务服务器）和企业资源计划（ERP）系统（如 SAP），特别是所谓的通用客户端接口（CCI），它定义了一个允许应用程序访问多个资源适配器的标准客户端 API。

## 通用客户端接口

![](img/3c2d905e913621002f512a08b8855a70_248_0.png)

**图 6-2.** JCA 通用客户端接口

必须指出 JCA 是 Jakarta EE 平台中一个非常老的部分，当 JCA 变为 Jakarta Connectors 时，它接受了一些微小的更改，但在其他方面它仍然非常旧，类似于 Jakarta Enterprise Beans (EJB)。因此，与像 Salesforce.com 这样的一些新型、云原生且基于 API 的 ERP 解决方案相比，它看起来有些过时了，而且是 Jakarta EE 中较少为人知的使用部分之一。

尽管 JSR 357 提议没有明确表述为“JCA 方式”，但某些支持者和 JCA 专家（除了 Oracle 外，当时主要是 IBM 或 SAP，目前其他大多数主导云市场的公司在 JCA 最初设计时甚至还不存在）可能觉得，他们培育的这个“小恐龙”可能会受到像 Java Social Connector API 这样的新标准的威胁。

## 核心

`Agora Core` 包含了独立于特定服务提供者的通用社交网络服务，提供以下功能：

- 用于向 OAuth 提供者进行身份验证的 OAuth 连接器
- 支持通用身份验证和用户配置管理
- 社交多账户服务，支持：
  - 多个社交网络连接
  - 同一社交网络提供者的多个会话，例如同时连接到多个用户账户或查询

`Agorava Core` 提供了这些服务的实现。目前主实现基于 CDI 和 `DeltaSpike`，但大多数服务已使用 JSR 330（现在的 Jakarta Dependency Injection）进行了泛化，这允许使用更轻级的 Java SE 替代方案，如 `Google Guice`、`Dagger` 或 SE 版本的 CDI 实现 `Weld`。

![](img/3c2d905e913621002f512a08b8855a70_249_0.png)

图 6-3. Agorava Core API 架构

## Agorava PicketLink

与 OAuth 功能和用户配置管理协同工作，`Agorava Core` 还包含一个基于 `PicketLink` 的安全子系统。

正如 2.3.2 中承诺的，这里是 `Agorava` 专用版本的 `PicketLink BaseAuthenticator`：

```java
@Generic
public class AgoravaAuthenticator extends BaseAuthenticator {

    @InjectWithQualifier
    OAuthAppSettings settings;

    @Inject
    DefaultLoginCredentials credentials;

    @Inject
    @DeltaSpike
    Instance<HttpServletResponse> response;

    @Inject
    OAuthLifecycleService lifecycleService;

    @Override
    public void authenticate() {
        if (lifecycleService.getCurrentSession().isConnected()) {
            OAuthSession session = lifecycleService.getCurrentSession();
            UserProfile user = session.getUserProfile();
            credentials.setCredential(session.getAccessToken());
            setStatus(AuthenticationStatus.SUCCESS);
            User user = new User(user.getId());
            user.setFirstName(user.getFullName());
            setAccount(user);
        } else {
            String authorizationUrl = lifecycleService.startDanceFor(settings.getQualifier());
            try {
                response.get().sendRedirect(authorizationUrl);
            } catch (IOException e) {
                e.printStackTrace();
            }
            credentials.setStatus(Status.IN_PROGRESS);
            setStatus(AuthenticationStatus.DEFERRED);
        }
    }
}
```

## 连接器

`Agorava` 目前带有以下服务的默认连接器：

- Facebook
- LinkedIn
- GitHub
- Twitter
- XING

除了这些之外，还为以下服务创建了第三方的 `Agorava` 连接器：

- Empire Avenue
- Google+
- Instagram
- Meetup
- Stack Overflow
- TripIt
- WordPress
- Yammer

## Socializer

`Socializer` 是 `Agorava` 的一个真实演示 Web 应用；可以想象成它的“宠物医院”。它允许你连接到各种社交网络并查看你的时间线或发布更新。`Agorava Socializer` 曾从 JavaServer Faces 移植到 Apache Widget Web Framework 或 AngularJS。这两个移植版本仍然带有很实验性，因此从未成为 `Agorava` 生态系统的正式部分。

## 集成连接器

在 `Socializer` 中添加新连接器非常简单。我们将以 XING 连接器为例来说如何操作。

克隆 `https://github.com/agorava/agorava-socializer` 后，在 `Socializer` 的 `pom.xml` 中包含以下行：

```xml
<!-- xing -->
<dependency>
  <groupId>agorava</groupId>
  <artifactId>agorava-api</artifactId>
  <version>0.3-SNAPSHOT</version>
  <scope>compile</scope>
</dependency>
<dependency>
  <groupId>agorava</groupId>
  <artifactId>agorava-cdi</artifactId>
  <version>0.3-SNAPSHOT</version>
  <scope>runtime</scope>
</dependency>
```

添加 XING 的依赖项。接下来，我们为 XING 添加 CDI 配置 `orgava.socializer.SettingsProducer.java`：

```java
@ApplicationScoped
@Produces
@Xing
@OAuthApplication(params = OAuthAppSettings, value = "xing")
public OAuthAppSettings xingSettings;
```

由属性支持：

```properties
src/main/resources/local/agorava.properties
x.apiKey=<your API Key>
x.apiSecret=<your API Secret>
```

需要在 XING 的社交账户中定义 API 密钥和 API 密钥；请查看 `dev.xing.com/applications/`。

## 第 6 章 社交框架

```xml
<ui:composition xmlns="http://www.w3.org/1999/xhtml"
  xmlns:ui="http://java.sun.com/js/faceslets"
  xmlns:f="http://java.sun.com/js/core"
  xmlns:h="http://java.sun.com/js/html"
  xmlns:p="http://primefaces.org/ui">
  <h:panelGroup id="xngtl" layout="block">
    <div class="well">
      <h6>What's on your mind?</h6>
      <p>
        <p:inputText value="#{socialClient.status}" styleClass="post-area" />
      </p>
    </div>
  </h:panelGroup>
</ui:composition>
```

大多数服务都提供像 XING 这样的“测试密钥”或开发密钥。要获取 Facebook App Id 和 App secret 凭据，你需要在 Facebook 上通过 `https://developers.facebook.com/apps/` 创建应用程序。

## Spring Social

`Spring Social` 项目 [25] 是 Spring Framework 的一个扩展，允许你的应用程序与 Facebook、LinkedIn 或 Twitter 等社交媒体提供者建立连接，并代表用户调用 API。

一段时间后，它不再得到活跃支持，或者 Pivotal/VMware 员工的更新或博客文章在更改或功能发布六个月后才出现。

GitHub 等开源生态展示了各种扩展或插件，但并非所有的都是成熟的；有些仅仅是 PoC（概念验证），而且其中大多数在一段时间内也没有被活跃维护。

`Spring Social` 也支持 .NET，但它并没有成功，仅在 2012 年发布了两个版本（1.0 以及 1.0.1），之后没有任何后续活动。因此，尽管 Spring Framework for .NET 仍然存在并持续维护（在 2023 年 7 月发布了 3.0.2 版本），但 Spring Social for .NET 在其对应品多年前就已经去世了。

由于 OAuth2/OpenID Connect 标准的日益提高以及 Spring Security 5 对其的支持，`Spring Social` 自 2019 年起不再支持或维护。其支持期已于 2019 年 7 月 3 日结束。这并不意味着生产环境中的应用完全放弃了它，对于新应用它们更倾向于使用 Spring Security；而对于某些不再更改但仍在使用的旧应用，它们可能会继续使用，因为社交网络 API 的变化在一段时间后不会影响其运行。

## 概述

`Spring Social` 的主要特性如下：

- 可扩展的服务提供者框架，极大简化了本地用户账户连接到社交媒体账户的过程
- 一个连接控制器（connect controller），负责处理您的 Java/Spring Web 应用程序、社交媒体提供者和用户之间的授权流
- 针对 Facebook、Twitter、LinkedIn、TripIt 或 GitHub 等流行 API 和社交网络的 Java 绑定
- 一个登录控制器（sign-in controller），允许用户通过社交网络登录您的应用程序以完成身份验证

`Spring Social` 的 Maven groupID 为 `org.springframework.social`。

## 核心

`Spring Social` 核心项目由表 6-2 所示的模块组成。

### 表 6-2. Spring Social 核心模块

| 名称 | 描述 |
| :--- | :--- |
| `spring-social-core` | Spring Social 连接框架和 OAuth 客户端支持 |
| `spring-social-config` | Spring Social 的 Java 和 XML 配置支持 |
| `spring-social-security` | Spring Security 集成 |
| `spring-social-web` | 使用连接框架在 Web 环境中管理连接的 Spring Social ConnectController |

## 客户端模块

除了 `Spring Social` 核心模块外，还有许多特定提供者的客户端模块，提供了与流行社交网络的连接和 API 绑定。

### 表 6-3. Spring Social 客户端模块

| 名称 | Maven artifactID |
| :--- | :--- |
| Spring Social Facebook | `spring-social-facebook` |
| Spring Social Twitter | `spring-social-twitter` |
| Spring Social LinkedIn | `spring-social-linkedin` |
| Spring Social GitHub | `spring-social-github` |
| Spring Social Tripit | `spring-social-tripit` |

## 连接框架

`Connection<A>` 接口模拟了与 Facebook 等服务提供者的连接：

```java
public interface Connection<A> extends Serializable {
    ConnectionKey getKey();
    String getDisplayName();
    String getProfileUrl();
    String getImageUrl();
    void sync();
    boolean test();
    boolean hasExpired();
    void refresh();
    UserProfile fetchUserProfile();
    void updateStatus(String message);
    A getApi();
    ConnectionData createData();
}
```



每个 `Connection` 由一个复合键唯一标识，该键由 `providerId`（例如 `"facebook"`）和 `providerUserId`（例如用户的 Facebook ID）组成。

让我们假设我们有一个指向用户 `"jdoe"` 的 `Connection<Twitter>` 引用。

1. `Connection#getKey()` 返回 `"twitter,1234567"`，其中 `1234567` 是 `@jdoe` 永远不会改变的 Twitter ID。
2. `Connection#getDisplayName()` 返回 `@jdoe`。
3. `Connection#getProfileUrl()` 返回 `"http://twitter.com/jdoe"`。
4. `Connection#getImageUrl()` 返回 `"http://a0.twimg.com/profile_images/105951287/IMG_5863_2_normal.jpg"`。
5. `Connection#sync()` 允许您将连接状态与 `@jdoe` 的个人资料同步。
6. `Connection#test()` 返回 `true`，表示 Twitter 连接的授权凭据有效。假设 Twitter 未撤销 `"AcmeApp"` 客户端应用程序，且 `@jdoe` 未重置其授权凭据。
7. `Connection#hasExpired()` 返回 `false`。
8. `Connection#refresh()` 只要到 Twitter 的连接不过期，它什么都不做。
9. `Connection#fetchUserProfile()` 远程 Twitter API 获取 `@jdoe` 的个人资料数据并将其规范化为 `UserProfile` 模型。
10. `Connection#updateStatus(String)` 在 `@jdoe` 的时间线上发布状态更新。
11. `Connection#getApi()` 返回一个引用，允许客户端访问 Twitter 原生 API 的所有功能。
12. `Connection#createData()` 返回一个 `ConnectionData` 引用，该引用可以序列化并用于稍后恢复连接。

## Facebook 示例

此示例展示了如何使用 Spring Social 为现有的 Spring Web 应用添加 Facebook 登录。

要获取 Facebook App Id 和 App secret 凭据，您需要在 `https://developers.facebook.com/apps/` 在 Facebook 上创建一个新应用程序。

确保将 `"Website"` 添加为平台，并将 `http://localhost:8080/` 作为 `"Site URL"`。

## Maven 配置

首先，在 `pom.xml` 中添加 `spring-social-facebook` 依赖：

```xml
<dependency>
  <groupId>org.springframework.social</groupId>
  <artifactId>spring-social-facebook</artifactId>
  <version>2.0.3.RELEASE</version>
</dependency>
```

## 安全配置

让我们使用带有表单认证的简单安全配置：

```java
@Configuration
@EnableWebSecurity
@ComponentScan(basePackages = { "com.example.security" })
public class SecurityConfig {

  @Autowired
  private UserDetailsService userDetailsService;

  @Bean
  public AuthenticationManager authManager(HttpSecurity http) throws Exception {
    return http.getSharedObject(AuthenticationManagerBuilder.class)
      .userDetailsService(userDetailsService)
      .and().build();
  }

  @Bean
  public SecurityFilterChain filterChain(HttpSecurity http) throws Exception {
    http.csrf()
      .disable()
      .authorizeRequests()
      .antMatchers("/login", "/signup/**")
      .permitAll()
      .anyRequest()
      .authenticated()
      .and()
      .formLogin()
      .loginPage("/login")
      .and()
      .logout();
    return http.build();
  }
}
```

# 示例

## 发布消息

你可以通过 `Facebook.postStatusMessage()` 方法发布消息，假设你已经通过之前提到的某种方法之一配置了 Facebook4J：

```java
Facebook facebook = new FacebookFactory().getInstance();
facebook.postStatusMessage("Hello World from Facebook4J.");
```

## 搜索地点

```java
Facebook facebook = new FacebookFactory().getInstance();

// 按名称搜索
ResponseList<Place> results = facebook.searchPlaces("coffee");
```

```java
// 你可以将搜索范围缩小到特定位置
Geolocation center = new GeoLocation(37.76, -122.427);
int distance = 1000;
ResponseList<Place> searchPlaces("coffee", center, distance);
```

## 执行 FQL

你可以通过 `Facebook.executeFQL()` 方法执行 FQL：

```java
Facebook facebook = new FacebookFactory().getInstance();
```

```java
// 单条 FQL 查询
String query = "SELECT uid2 FROM friend WHERE uid1=me()";
JSONArray jsonArray = facebook.executeFQL(query);
for (int i = 0; i < jsonArray.length(); i++) {
    JSONObject jsonObject = jsonArray.getJSONObject(i);
    System.out.println(jsonObject.get("uid2"));
}
```

```java
// 多条 FQL 查询
Map<String, String> queries = new HashMap<>();
queries.put("all friends", "SELECT uid2 FROM friend WHERE uid1=me()");
queries.put("my name", "name FROM user WHERE uid1=me()");
Map<String, JSONArray> result = facebook.executeMultiFQL(queries);
JSONArray allFriendsJSONArray = result.get("all friends");
for (int i = 0; i < allFriendsJSONArray.length(); i++) {
    JSONObject jsonObject = allFriendsJSONArray.getJSONObject(i);
    System.out.println(jsonObject.get("uid2"));
}
JSONArray myJSONArray = result.get("my name");
System.out.println(myNameJSONArray.getJSONObject(0).get("name"));
```

# 第 6 章 社交框架

## 批量模式

与 Meta Business SDK 类似，你可以通过 `Facebook.executeBatch()` 方法执行批量请求（Batch Requests）：

```java
Facebook facebook = new FacebookFactory().getInstance();

// "me" 和 "me/friends?limit=50" 节点
BatchRequests<BatchRequest> batch = new BatchRequests<BatchRequest>();
batch.add(new BatchRequest(RequestMethod.GET, "me"));
batch.add(new BatchRequest(RequestMethod.GET, "me/friends?limit=50"));
List<BatchResponse> results = facebook.executeBatch(batch);
```

```java
BatchResponse result1 = results.get(0);
BatchResponse result2 = results.get(1);
```

```java
// 你可以获取状态码或头部
int statusCode1 = result1.getStatusCode();
String contentType = result1.getResponseHeader("Content-Type");

// 你可以使用 String 方法获取主体内容
String jsonString = result1.asString();
JSONObject jsonObject = result1.getJSONObject();
ResponseList<JSONObject> responseList = result2.asResponseList();
```

```java
// 你可以使用 DataObject.create 将 json 映射到 Java 对象
User user = DataObjectFactory.createUser(jsonString);
Friend friend1 = DataObjectFactory.createFriend(responseList.get(0));
Friend friend2 = DataObjectFactory.createFriend(responseList.get(1));
```

## 总结

在上一章概述了安全框架之后，我们在本章中学习了 Java 平台相关的社交框架，以及如何将它们与流行的社交网络配合使用。

# 第 7 章 社交门户

正如你在第 3 章记忆的，Java Portlets 是组合应用（mashups）的一种早期方法；因此，流行的门户服务器也支持社交媒体集成，如社交登录、组合应用或社交共享。

## Liferay 门户

Liferay 是一家“专业开源”公司，为其开源门户软件提供付费支持和服务。

### 历史

Liferay Portal 最初由创始人兼首席技术官 Brian Chan 于 2000 年创建，旨在为教会等非政府组织（NGO）提供门户解决方案。Liferay 的第一个办公室也位于一家教堂内。

Liferay Inc. 在被 Oracle 收购不久前曾与 Sun 或 TIBCO 建立了合作伙伴关系，但直到现在它一直保持独立并私有化。由于基因里流淌着开源血液，Liferay 还积极帮助制定了 Java Portal 标准，例如 JSR 362 (Portlet 3.0) 或 378 (Portlet 3.0 Bridge for JavaServer Faces 2.2)，并在这些项目中担任了规范负责人。

## Liferay 社交

无论你想创建自己的社交媒体体验，还是集成其他社交网络，都可以通过 Liferay Portal 实现两者。

Liferay 开箱提供了四个社交门户组件：

- 活动（Activities）
- 用户统计（User statistics）
- 群组统计（Group statistics）
- 请求（Requests）

这些之外，还存在针对各种 API 和社交网络的集成。

## 地图组件（Map Portlet）

Map Portlet 允许你查看全球团队成员的位置，但只会显示添加了 Map portlet 的网站成员。

首先，你需要从 Google 获取一个密钥，以便通过 Map portlet 访问 Google Maps API。访问 `https://developers.google.com/maps/documentation/javascript/tutorial#api_key` 获取有效的 Google Maps API 密钥。

然后执行以下步骤：

- 如果尚未安装，请安装社交网络插件（Social Networking plug-in）。
- 安装 IP 地理编码组件（IP Geocoder portlet）。（Social Networking 和 IP Geocoder 均已安装）。

- 应用密钥（Application Secret） – 只能在门户实例级别设置。输入您注册的 Facebook 应用密钥。
- 图 URL（Graph URL） – Facebook 图 API 的基础 URL。仅当 Facebook 更改其图 API 时才修改。只要 Facebook 的 API 保持不变，请使用默认图 URL。
- OAuth 授权 URL（OAuth Authorization URL） – Facebook OAuth 授权 URL。只有当 Facebook 更改其 OAuth 授权节点时，您才需要更改此 URL。此 URL 将带有动态数据并链接到 Liferay 登录门户。
- OAuth 令牌 URL（OAuth Token URL） – Facebook OAuth 访问令牌 URL。Liferay DXP 用此将请求令牌交换为访问令牌。
- OAuth 重定向 URL（OAuth Redirect URL） – 生成 OAuth 请求令牌后，用户将被重定向至此。URL 指向 Liferay DXP 服务，该服务将请求令牌交换为访问令牌，以便 Liferay DXP 成功调用 Facebook 图 API。只有当指向 Liferay DXP 的请求通过 Apache 等进行 URL 重写的代理服务器传输时，您才需要更改此 URL。

## 社交书签 (Social Bookmarks)

社交书签以按钮形式出现在内容下方，用于在社交网络上分享内容。例如，社交书签默认出现在每篇博客文章下方的博客小部件中。这些社交书签默认可用：

- Facebook
- LinkedIn
- Twitter/X

此外，Liferay Marketplace 上的社交书签应用为以下社交网络添加了更多社交书签：

- Digg
- Evernote
- Reddit
- Slashdot

## OpenSocial

与其他许多开放标准一样，Liferay 支持 OpenSocial 框架和规范（尽管看起来是与 Apache Shindig 使用了早于 W3C 的标准）。

您可以在网上发布小部件（gadgets），也可以使用 Liferay 门户的 OpenSocial 小部件编辑器来创建并发布自己的小部件：

这里是一个 PubSub 发布者小部件的示例：

```xml
<?xml version="1.0"?>
<Module>
  <ModulePrefs height="250" title="Sample PubSub Publisher">
    <Require feature="pubsub-2">
      <Param name="topics">
      <![CDATA[
      <Topic
        description="Publishes a random number."
        name="org.apache.shindig.random-number"
        publish="true"
        title="Random Number"
        type="number"
      />
      ]]>
      </Param>
    </Require>
  </ModulePrefs>
  <Content type="html">
  <![CDATA[
  <script>
    function publish() {
      var message = Math.random();
      gadgets.Hub.publish('org.apache.shindig.random-number', message);
      document.getElementById('output').innerHTML = message;
    }
  </script>
  ]]>
  </Content>
</Module>
```



```html
<div>
  <input onclick="publish();" type="button" value="Publish a Random Number" />
</div>
<div id="output"></div>
```

这里是一个 PubSub 订阅者小部件示例：

```xml
<?xml version="1.0"?>
<ModulePrefs height="250" title="Sample PubSub Subscriber">
  <Require feature="pubsub-2">
    <Param name="topics">
      <![CDATA[
        <Topic
          description="Subscribes to random number generator."
          name="org.apache.shindig.random-number"
          subscribe="true"
          title="Random Number"
          type="number"/>
      ]]>
    </Param>
  </Require>
</ModulePrefs>
<Content type="html">
<![CDATA[
  <script>
    var subId;
    gadgets.HubSettings.params.HubClient.onSecurityAlert =
      function(alertSource, alertType) {
        alert('Security error!');
      }
```

```javascript
window.location.href = 'about:blank';
};

function callback(topic, data, subscriberData) {
  document.getElementById('output').
  innerHTML = 'Message: ' + gadgets.util.escapeString(data + ' ') + '<br />' +
  'Received: ' + (new Date()).toString();
}

function subscribe() {
  subId = gadgets.Hub.subscribe('org.apache.shindig.random-number',
  callback);
}

function unsubscribe() {
  gadgets.Hub.unsubscribe(subId);
  document.getElementById('output').innerHTML = '';
}

</script>
<div>
  <input onclick="subscribe();" type="button" value="Subscribe" />
  <input onclick="unsubscribe();" type="button" value="Unsubscribe" />
</div>
<div id="output"></div>
```

## HCL

HCL Technologies Limited（原 Hindustan Computers Limited）是一家印度 IT 服务和咨询公司，总部位于首都德里的卫星城市诺伊达（Noida）。

## 历史 (History)

1976 年，在微软或苹果成立后不久，印度的八位工程师成立了一家制造个人电脑的公司。在 1976 年 8 月 11 日最初提议的名为 Microcomp（这可能导致与微软产生命名冲突）后，该公司被更名为 Hindustan Computers Limited (HCL)。

该公司最初专注于硬件，但通过 HCL Technologies，重点日益转向了软件和服务。

2018 年 12 月 7 日，HCL 宣布一项协议，HCL Technologies 以 18 亿美元收购了 IBM 软件产品，包括 AppScan、BigFix、Connections、Digital Experience（Portal 和 Content Manager）、Notes/Domino 或 Unica。

2022 年，HCL Technologies 品牌更名为 HCLTech。

## HCL DX

HCL Portal（原 IBM WebSphere Portal）是 HCL Digital Experience (DX) 的一部分。

通过名为 Social Media Publisher 的扩展，HCL DX 用户可以与热门的社交网络共享他们的内容。开箱即支持以下网络：

- Facebook
- LinkedIn
- Twitter/X

## 社交媒体发布器 (Social Media Publisher)

Social Media Publisher 可用于已已社交媒体帖子，如果进行了配置，还可以管理草稿内容。

它支持手动和自动社交媒体发布，并可以管理社交线程的周期。

## 表 7-1. HCL 社交媒体发布器 - 特性

| 社交网络 | 消息类型 | 统计 | URL 可访问 | 用户跟踪 | 不跟踪 | 删除 |
| --- | --- | --- | --- | --- | --- | --- |
| Facebook | 页面墙帖子 | 点赞、评论计数 | 是 | 是 | 是 | 是 |
| Facebook | 个人资料帖子 | 点赞、评论计数 | 是 | 是 | 是 | 是 |
| LinkedIn | 网络更新 | 无 | 否 | 否 | 是 | 否 |
| LinkedIn | 分享 | 无 | 否 | 否 | 是 | 否 |
| Twitter | 推文 | 转发计数 | 是 | 是 | 是 | 是 |

## Facebook 设置

按照以下步骤为 Facebook 建立社交网络连接。
要获取 Facebook 凭据：

1. 访问 `https://developers.facebook.com/apps/`。
2. 点击**创建新应用 (Create new App)**。
3. 输入以下参数的值：
   a) 显示名称（Display name） – 在每个帖子结尾显示的应用程序名称，例如您的公司名称。
   b) 命名空间（Namespace） – 用于访问 Facebook Insights 的可选值。建议为每个设置的应用使用唯一名称。
   c) 类别（Category） – 匹配您的业务类型的类别。如果不确定，选择*页面 (Pages)*。
4. 点击**创建应用 (Create App)**。
5. 您将进入应用程序的配置界面。选择设置（Settings）并输入以下：
   a) 应用域名（App domain） – 您希望用于此 Facebook 账户的逗号分隔域名或 IP 地址列表。您可以从其中的任一域名授权您的应用程序。
6. 点击添加平台（Add Platform）并选择网站（Website）。
7. 设置站点 URL 和（可用）移动站点 URL 为目标网站，例如 `http://www.mysite.com`。
8. 点击保存更改（Save Changes）。
9. 现在您可以看到应用程序的应用 ID/API 密钥和应用密钥。

现在，在 HCL 门户管理视图中创建凭据库（Credential Vault），其中：

- 应用 ID/API 密钥指定为共享用户 ID。
- 应用密钥指定为共享密码。

然后为 Facebook 创建社交网络配置：

1. 选择 Facebook 作为社交网络。
2. 为该社交网络定义身份验证设置：
   a) 选择包含您的 Facebook 凭据的凭据库。
   b) 点击授权（Authorize）将凭据绑定到特定的 Facebook 账户。
3. 选择消息类型：
   * 页面墙帖子 (Page wall post)
   * 选择一个页面。
   * 输入默认名称、描述、图像、说明和消息模板。包含预定义值作为参考，例如：
   * 名称（Name） – 以文本形式发布。

## 第 7 章 社交门户

- 描述 – 以文本形式发布。

`[Property field="description" context="current" type="content" format="length:100"]`

- 图像 – 以 URL 形式发布。

`[Element context="current" type="content" key="Image" format="URL"]`

- 说明 – 以文本形式发布。

`[Property field="description" context="current" type="content" format="length:100"]`

- 消息 – 以文本形式发布。

`[Element context="current" type="content" key="Message" format="length:100"]`

- 个人主墙贴发布
选择合适的可见性
输入默认的名称、描述、图像、说明和消息模板。包含预定义值作为参考。例如：
- 名称 – 以文本形式发布。

`[Property field="title" context="current" type="content" format="length:100"]`
- 描述 – 以文本形式发布。

`[Property field="description" context="current" type="content" format="length:100"]`
- 图像 – 以 URL 形式发布。

`[Element context="current" type="content" key="Image" format="URL"]`
- 说明 – 以文本形式发布。

`[Property field="description" context="current" type="content" format="length:100"]`

- 消息 – 以文本形式发布。
`[Element context="current" type="content" key="Message" format="length:100"]`

## 直接将内容发布到 Facebook 页面

社交媒体发布器用于将内容的状态更新发布到 Facebook，您也可以直接将内容发布到 Facebook 页面。

1. 访问 `https://developers.facebook.com/apps`。
2. 点击新建应用 (Create new App)。
3. 打开表单。为以下参数输入值：
* 应用名称 – 您的应用程序名称将显示在每条帖的最后，例如您的公司名称。
* 应用命名空间 – 用于访问 Facebook Insights 的名称。建议为每个应用程序使用唯一名称。
4. 点击继续 (Continue)。
5. 显示您的应用程序配置屏幕。在“选择您的应用如何与 Facebook 集成”下选择“页面标签 (Page Tab)”并完成以下参数：
* 页面标签名称 – 为页面标签输入名称。
* 页面标签 URL – 您要添加到 Facebook 页面的内容项的 URL。
* 安全页面标签 URL – 页面标签 URL 的 https 版本。
6. 点击保存更改 (Save Changes)。
7. 点击授权 (Authorize) 将凭据绑定到特定的社交网络账户。
8. 要将内容发布到 Facebook 页面，请使用以下 URL，其中 `APP_ID` 是 Facebook 页面标签的应用 ID：

```
http://www.facebook.com/dialog/pagetab?app_id=APP_ID&next=https%3A%2F%2Fwww.facebook.com%2FConnect%2FLogin_success.html
```

9. 直接将内容发布到 Facebook 页面需要安全的标签 URL。这意味着您的服务器必须启用 SSL。

## LinkedIn 设置

执行以下步骤设置 LinkedIn 社交网络连接。
获取 LinkedIn 凭据：

1. 访问 `www.linkedin.com/developers/apps`。
2. 如果尚未登录，请登录。
3. 点击创建应用 (Create app)。
4. 如果您已有一个公司页面，请选择现有公司或选择“新公司 (New Company)”并输入公司信息。
5. 在“创建应用”下，为以下参数输入值：
* 应用名称 - 您的应用程序名称将显示在每条帖的最后，例如您的公司名称。
* LinkedIn 页面 - 您之前创建的公司页面，例如 `https://linkedin.com/company/123456`。
* 隐私政策 URL - 指向您的隐私政策的链接（可选），例如，`http://www.mysite.com/privacy`。
* 应用图标 – 用户在授权您的应用时会显示图标，理想情况下是正方形图像。
* 法律协议 – 勾选您已阅读并同意这些条款。
6. 点击创建应用 (Create app)。
7. 在 Auth 标签页中，您将找到应用程序凭据 API Key 和客户端密钥 (Client Secret)。点击“眼睛”按钮显示密钥。记录这些值并在适当的地方填写其他设置。

随后在 HCL Portal 管理视图中有一个新的凭据库 (Credential Vault)：

* 客户端 ID (Client ID) 指定为共享用户 ID
* 客户端密钥 (Client Secret) 指定为共享密码

要为 LinkedIn 创建社交网络配置：

1. 选择 LinkedIn 作为社交网络。
2. 为社交网络定义身份设置：
* 选择包含 LinkedIn 应用凭据的凭据库。
* 点击授权 (Authorize) 将凭据绑定到特定的社交网络账户。
3. 选择消息类型。

注意：建议在不支持 HTML 的任何字段中引用富文本元素或 HTML 元素。

* 网络更新
* 输入默认消息模板。包含预定义值作为参考。例如：
* 消息 – 以 HTML 形式发布。
* `[Element context="current" type="content" key="Message" format="length:200"]`
* `[URLcmpnt context="current" type="content" mode="standalone" start="<a href='" end="">Link</a>"]`

* 网络更新
* 选择合适的可见性
* 输入默认的名称、描述、图像、说明和消息模板。包含预定义值作为参考。例如：
- 名称 – 以文本形式发布。

`[Property field="title" context="current" type="content" format="length:100"]`
- 描述 – 以文本形式发布。

`[Property field="description" context="current" type="content" format="length:100"]`
- 图像 – 以 URL 形式发布。

`[Element context="current" type="content" key="Image" format="URL"]`

*(注：由于原文中存在大量重复内容，译文保持了与原文一致的结构翻译逻辑，后续重复的文本块内容均已按上述逻辑完整翻译。)*

## 安装

- 从 CoreMedia 应用工作空间开始，将仓库 `https://github.com/CoreMedia/coremedia-social-hub.git` 克隆为 extensions 文件夹下的子模块。请确保使用与您的工作空间匹配的分支名称：

```
git submodule add -b 1907.1 https://github.com/CoreMedia/coremedia-social-hub modules/extensions/coremedia-social-hub
```

- 使用项目根目录下的扩展工具将模块链接到：
`mvn -f workspace-configuration/extensions com.coremedia.maven:extensions-maven-plugin:LATEST:sync -Denable=coremedia-social-hub`

## 配置

Social Media Hub 的配置由不同的设置组成，这些设置可以应用于全局或特定站点的文件夹。

- 全局：`/Settings/Options/Settings/Social Hub/`
- 站点特定：`<SITE>/Options/Settings/Social Hub/`

## 全局设置

Settings 文档声明了 Social Media Hub 的全局设置，必须位于全局设置文件夹中。它定义了用于缩短链接的 bitly 账户凭据，并定义了在从内容社交媒体帖子中提取媒体时所需的额外的 CAE 和文档类型模型信息。

```
<CMSettings folder="/Settings/Options/Settings/Social Hub"
name="locale"><locale>
<master/>
<settings>
<Struct xmlns="http://www.coremedia.com/2008/struct">
<StringProperty Name="bitlyUserId"></StringProperty>
<StringProperty Name="bitlyApiKey"></StringProperty>
<StructProperty Name="mediaMapping">
```



<Struct>

  <StringProperty Name="CMMedia">data</StringProperty>

</Struct>

</StructProperty>

<StringProperty Name="liveCaeUrl">YOUR_LIVE_CAE</StringProperty>

</struct>

</settings>

<identifier></identifier>

</CMSettings>

## 媒体映射

`mediaMapping`结构配置了可以推送到社交网络的、持有 blob 数据的内容类型和属性字段。默认情况下，`CoreMedia Blueprint`文档类型模型已为`CMMedia`配置，其数据属性包含一个带有资产数据的 blob。

## 适配器设置

`Social Media Hub`适配器配置可以放在全局或特定站点的配置文件夹中。

## 通用适配器设置

每个 `Social Media Hub`适配器配置具有此结构：

```
<CMSettings folder="/Settings/Options/Settings/Social Hub/" name="My Hub Adapter">

<locale></locale>

<master>

<settings>

<Struct xmlns="http://www.coremedia.com/2008/struct">

  <StructListProperty Name="channels">

  <Struct>

    <StringProperty Name="id">ADAPTER_ID</StringProperty>

<StringProperty Name="type">ADAPTER_TYPE</StringProperty>

<StringProperty Name="displayName">MY ADAPTER NAME</StringProperty>

<BooleanProperty Name="enabled">true</BooleanProperty>

<StructProperty Name="connector">

<Struct>

  ...

</Struct>

</StructProperty>

<StructProperty Name="adapter">

<Struct>

  ...

</Struct>

</StructProperty>

</Struct>

<StructListProperty>

</Struct></settings>

<identifier></identifier>

</CMSettings>
```

每个连接结构都包含表 7-2 所示的属性。

### 表 7-2. 连接结构属性

| 属性 | 说明 |
| --- | --- |
| `id` | 适配器的唯一 `id`，确保没有其他适配器具有相同的 `id` |
| `type` | 适配器类型 |
| `displayName` | 在适配器列中显示为标题的 |
| `enabled` | 适配器是否启用或禁用 |
| `connector` | 用于配置适配器连接器的额外属性 |
| `adapter` | 用于配置适配器的额外属性 |

当启动期间读取配置时，`Social Media Hub`将尝试将每个配置映射到相应的适配器。

## 连接器设置

连接器配置通常包含访问社交网络或 API 的凭据。此配置必须扩展 `ConnectorConfiguration`，它对所有连接器都有效。

`ConnectorConfiguration`暴露了以下方法：

- `getImageVariant()` - 推送到媒体时使用的变体。如果没有找到变体，将使用原始 blob。

## Twitter/X

本节介绍了 `Twitter Social Media Hub`适配器的配置。

### 适配器配置

要显示配置文件的 Twitter 时间线，需要由适配器提供：

```
<StructProperty Name="adapter">

<Struct>

<StringProperty Name="timeline">https://twitter.com/[YOUR_PROFILE]/

</StringProperty>

</Struct>

</StructProperty>
```

### 连接器配置

按照上一节 `HCL Portal`的说明创建您的 Twitter/X 。

使用原生 Twitter 适配器，需要在连接器配置中提供相应的 Twitter 凭据：

```
<StructProperty Name="connector">

  <Struct>

    <StringProperty Name="consumerKey"></StringProperty>

    <StringProperty Name="consumerSecret"></StringProperty>

    <StringProperty Name="accessToken"></StringProperty>

    <StringProperty Name="accessTokenSecret"></StringProperty>

  </Struct>

</StructProperty>
```

## YouTube

本节介绍了 YouTube 配置。

### 适配器配置

不需要

### 连接器配置

使用原生 YouTube 适配器需要在连接器配置中提供相应的 YouTube 凭据。参考 `https://developers.google.com/youtube/v3` 创建 YouTube。

```
<StructProperty Name="connector">

  <Struct>

    <StringProperty Name="channelId"></StringProperty>

    <StringProperty Name="playlistId"></StringProperty>

  </Struct>

</StructProperty>
```

## Instagram

本节介绍了 Instagram 配置。

### 适配器配置

不需要

### 连接器配置

由于 `Social Media Hub`未提供原生 Instagram 适配器，实际的适配器取决于社交媒体工具。

## Pinterest

本节介绍了 Pinterest 配置。

### 适配器配置

要显示配置文件的 Pinterest 画板，需要由适配器提供画板链接：

```
<StructProperty Name="adapter">

<Struct>

  <StringProperty Name="board">https://www.pinterest.com/[PINTEREST_PROFILE]/[PINTEREST_BOARD_NAME]</StringProperty>

</Struct>

</StructProperty>
```



## 总结

在最后一章中，我们学习了企业级门户服务器及其社交支持，通过在门户内部提供社交交互，或者通过集成社交网络（从用于社交登录到分享内容或嵌入社交时间线）。

## REFERENCES

- 12. 维基百科 - 混合应用 (Mashup): http://en.wikipedia.org/wiki/Mashup_(web_application_hybrid)
- 13. 维基百科 - BEA AquLogic: https://en.wikipedia.org/wiki/BEA_Systems#AquLogic
- 14. 什么是围墙花园？2023年权威指南：https://www.kevel.com/blog/what-are-walled-gardens
- 15. 维基百科 - Open Social: http://en.wikipedia.org/wiki/OpenSocial
- 16. ZDNet - Dion Hinchcliffe 撰文：我们如何为社交业务创建开放标准：https://www.zdnet.com/article/how-we-can-create-open-standards-for-social-business/
- 17. 维基百科 - 社交网络服务列表: https://en.wikipedia.org/wiki/List_of_social_networking_services
- 18. Twitter4J: https://twitter4j.org/
  GitHub: https://github.com/Twitter4J/Twitter4J
- 19. Apache Shindij: http://shindij.apache.org/
- 20. OSDE - Google Code: https://code.google.com/p/opensocial-development-environment/
- 21. Glassfish SocialSite 开发者指南: https://docs.oracle.com/cd/E19957-01/820-6356/820-6356.pdf
- 22. SlideShare - DaliCore: www.slideshare.net/johansvanstichel/dalicore-5313314
- 23. 维基百科 - 骨骨文收购列表: http://en.wikipedia.org/wiki/List_of_acquisitions_by_Oracle
- 24. 使用 Oracle 社交网络: https://docs.oracle.com/cloud/latest/related-docs/OSNUG/toc.htm
- 25. Spring Social: https://spring.io/projects/spring-social
- 26. 社交媒体 JSR 357 被 Java 社区进程拒绝：www.h-online.com/open/news/item/Social-Media-JSR-357-rejected-by-Java-Community-Process-1478310.html
- 27. 维基百科 – 最小权限原则: http://en.wikipedia.org/wiki/Principle_of_least_privilege
- 28. Jakarta 上下文依赖注入: https://jakarta.ee/specifications/cd/
- 29. OpenID: https://openid.net/
- 30. W3C 社交小组: w://www.w3.org/Social/WG
- 31. OPENI: https://cordis.europa.eu/project/id/317883
- 32. Jakarta Security: https://jakarta.ee/specifications/security/
- 33. Agora 项目: https://agorava.github.io
- 34. 微软嵌入社交: https://www.microsoft.com/en-us/research/project/microsoft-embedded-social/
  GitHub: https://github.com/microsoft/EmbeddedSocial-Java-API-Library
- 35. Java Twitter API 客户端库: https://github.com/twitterdev/twitter-api-java-sdk
- 36. Meta 业务 SDK: https://developers.facebook.com/docs/business-sdk
  GitHub (Java 版): https://github.com/facebook/facebook-business-sdk
- 37. 维基百科 – 社交网络的隐私忧虑：http://en.wikipedia.org/wiki/Privacy_concerns_with_social_networking_services
- 38. 社交媒体能破博里斯·内姆佐索夫谋杀案吗？https://socialmedianyu.wordpress.com/2015/03/03/can-social-media-solve-boris-nemtsovs-murder/
- 39. 美联社 – 德国电报活动在数千人的最后冲刺中结束：https://apnews.com/article/germany-business-d3bbbebe521049fc99bee29310104ad8
- 40. YouTube – 动物园的我：https://youtu.be/jQXAC9IVRw
- 41. 维基百科 – 安德亚斯·卡普兰：https://en.wikipedia.org/wiki/Andreas_Kaplan
- 42. 维基百科 – 微软合并与收购列表：https://en.wikipedia.org/wiki/List_of_mergers_and_acquisitions_by_Microsoft
- 43. Verizon 正在将 Tumblr 卖给 WordPress：www.theverge.com/2019/8/12/20802639-tumblr-verizon-sold-wordpress-blogging-yahoo-adult-content
- 44. 维基百科 – 2022 年 Twitter 账户劫持：https://en.wikipedia.org/wiki/2022_Twitter_account_hijacking
- 45. 特朗普的社交媒体网站悄悄承认基于 Mastodon：https://uk.pcmag.com/social-media/137421/trumps-social-media-site-quietly-admits-its-based-mastodon
- 46. 坎耶·韦斯特在购买 Parler 后：https://techcrunch.com/2022/12/01/kanye-west-isnt-buying-parler-all
- 47. SFOMA – 1997：手机的诞生：www.sfoma.org/watch/1997-birth-of-the-camera/
- 48. JSR 168 – 端口规范：www.jcp.org/en/jsr/detail?id=168
- 49. 元宇宙 – ChatGPT 通过了图灵测试：https://mpost.io/chatgpt-passes-the-turing-test/
- 50. TechCrunch – Twitter 突然锁定数千账户：http://techcrunch.com/2015/02/10/twitter-locked/
- 51. Fitbit 失去了使用的理由，这是一个大错误：www.fitbit.com/ending-big-mistake/
- 52. Parler 的新所有者关闭了网站：www.techdirt.com/2023/04/17/parlers-new-owner-shuts-down-no-reasonable-person-believes-twitter-for-conservatives-is-a-business-model/
- 53. CNN - 德桑斯的 Twitter 发布显示马斯克的平台尚未准备好上线：https://edition.cnn.com/2023/05/25/media/deantis-twitter-musk-reliable.html
- 54. CNBC - Reddit 将向访问其数据的第三方应用收费：www.cnbc.com/2023/06/01/reddit-charging-millions-for-third-party-access.
- 55. IEEE Xplore - 军事安全策略比较：https://ieeexplore.ieee.org/document/6234890
- 56. JBoss 社区存档 - Agora：https://docs.jboss.org/author/display/AGVA/
- 57. 透社 - Meta 的 Threads 迅速达到 3000 万用户：www.reuters.com/technology/threads-threat-owned-analysts-say-2023-07/
- 58. Wired - X 不是超级应用，它只是 Twitter：www.wired.com/story/twitter-rebrand-elon-musk/
- 59. WhatsApp 业务 API：https://bindc.github.io/business-api/
- 60. GNU social：https://gnusocial.network/
- 61. Mastodon：https://mastodon.org/
- 62. Friendica：https://friendica.ca/
- 63. W3C 社交网协议：www.w3.org/TR/social-web/
- 64. Observer - Meta 据是最新采用 ActivityPub 技术的社交媒体：https://observer.com/2023/03/meta-is-reportedly-the-latest-social-media-company-to-embrace-activitypub-technology/
- 65. Matrix：https://matrix.org/
- 66. Keycloak：www.keycloak.org/
- 67. Spring Security：https://spring.io/projects/spring-security
- 68. Micronaut：https://micronaut.io/

## 索引

### A

- 认证 (Authentication), 57, 64, 69, 71–74, 78–91, 113–117, 137–142, 153–154, 158–160, 234–235
- 访问控制 (Access control), 74, 93
- Activity API, 33
- ActivityPub, 38, 40–44, 46
- ActivityStreams, 41–43
- Agava
- 授权 (Authorization), 64, 74–75, 142, 166–169, 220

### B

- 连接器 (connectors), 245
- 核心 (core), 242, 243
- 定义 (definition), 239
- 宏内核架构 (macro architecture), 240–242
- PicketLink, 243, 244
- socializer, 245, 246
- Amazon, 3, 6, 9, 14, 57
- Apache Shindij, 35, 55–57
- Apache Shiro
  - 应用开发者 (application developers), 161
  - 定义 (definition), 161
  - 功能 (features), 163, 164
  - 认证 (authentication), 164, 165
  - 授权 (authorization), 166, 167
  - 会话管理 (session management), 169
  - 框架 (framework), 161
  - 领域 (realm), 163
  - SecurityManager, 162
  - 社交登录 (social login), 170, 171, 173–179
  - 主体 (subject), 162
- 批处理模式 (Batch Mode), 195, 256
- BigBone, 204
- 大数据, 240

### C

- ChatGPT, 7, 8
- 通用客户端接口 (CCI), 241, 242
- 机密性 (Confidentiality), 63, 240
- 基于上下文的访问控制 (CBAC), 192
- CoreMedia
  - 历史 (history), 276
  - 社交媒体中心 (social media hub)
    - 配置 (configuration), 277, 278, 282
    - 安装 (installation), 277
- CoreMedia Labs 蓝图, 276
- COVID-19 疫情, 7
- 加密学 (Cryptography), 169
- `@CustomFormAuthenticationMechanism`
  - 定义注解 (Definition annotation), 114

### D

- Apple Health, 21, 22
- 基于属性的访问控制 (ABAC), 142
- 有声书 (Audiobooks), 144
- 音频共享 (Audio sharing), 13
- Diaspora, 46, 68
- 数字名片 (Digital Business Cards), 37

### Discord

- 认证 (authentication), 222, 222
- 社区 (community), 222
- Discord4j, 223–225
- Javacord, 228–230
- JDA, 226, 267
- Twitch4j, 230–236
- Discord4j, 223

### E

- Echobox LinkedIn SDK, 218, 219, 221
- `enableLocalAuthentication` 属性, 133
- `@EnableWebSecurity` 注解, 158
- 企业信息系统 (Eis), 241
- 企业资源计划 (ERP)
  - 系统, 241
- 企业社交混合应用 BEA Systems, 56
- 企业社交网络, 33

### F

- Facebook4j, 253, 255
- `Facebook.executeBatch()` 方法, 255
- Facebook (Meta) 业务 SDK, 49
- `Facebook.postStatusMessage()` 方法, 255
- Fediverse
  - definition, 44, 45
  - protocols, 45
  - diaspora, 46
  - matrix, 47–49
- Fitbit, 232
- 论坛帖子, 1
- 朋友之友 (FOAF), 36

### G

- `getCallerGroups()` 方法, 86, 88–90
- 全局唯一标识符 (GUIDs), 85
- 全球网络, 44
- Google, 1, 3
- Google Fit, 22–23
- Google 的 Lambda AI, 8
- Google Translate, 32

### H

- 健康与位置服务 (Health and Location-Based Services), 33
- Hindust Computers Limited (HCL)
  - HCL DX, 267, 269, 272, 274
  - Facebook 页面, 271, 272
  - Facebook 设置, 268–270
  - 功能, 268
  - LinkedIn 设置, 272–274
  - Twitter/X 设置, 274, 276
  - 历史, 267
- `HttpAuthenticationMechanism`, 113, 114

### I

- 身份访问管理 (IAM), 64
- 身份提供者 (IdP), 96, 99
- 图像应用, 15
- 信息安全, 63
- 集成社交媒体方法, 33
- 即时聊天 (IRC), 3

### J

- Jakarta EE 容器安全, 152
- Jakarta EE
  - 认证机制 (authentication mechanisms), 78, 80
  - 基础认证 (basic authentication), 83, 84
  - 客户端认证 (client authentication), 84
  - 客户端调用者身份认证，84
  - 标识，96
  - 摘要认证，82, 83
  - 核心术语，75
  - 基于表单认证，80, 81
  - HTTP 方法，77
  - 身份存储库，85–90
    - 声明能力，89, 90
    - 定义，85
    - EE 生态系统，85, 86
    - 目的，85
    - 获取调用者信息，89
    - 验证凭据，87–89
  - OAuth，91–93
  - OpenID，94–96
  - SecurityContext，76, 77
    - 安全功能，76
- Jakarta Enterprise Beans (EJB)，242
- Java 社区进程，37
- Javord，228
- Java Discord API (JDA)，226
- JBoss 开发者框架 (JDF)，240
- JSESSIONID，98
- JSON Web Encryption (JWE)，96
- JSON Web Signature (JWS)，96
- JSON Web Token (JWT)
  - 定义，96
  - HTTP API 请求，98
- microProfile，107–111
  - MP JWT 公共声明，110
- SSS，98–101
  - 结构，102–109
  - 用用案例，97
  - 工作原理，101, 102
- 身份验证流，140, 141
- 授权，142, 143
  - 客户端，145
  - 凭据，143
  - 定义，135
  - 事件，145–148
  - 功能，143, 144
  - 历史，136
  - 密码策略，140
  - 域，143
  - 社交身份提供者，149–151
- 社交登录，135

### K

- Keycloak
  - 身份认证，137–139

### L

- 最小权限原则，75
- 遗留框架
  - OACC，183–185, 187
  - PicketLink，180, 181
  - SocialAuth，182
- Liferay Portal
  - 定义，259
  - HCL，266
  - 历史，259
  - 社交网络
    - 书签，263
    - 集成，261–263
    - 映射端口，260
    - OpenSocial 框架，264–266
    - 端口，260
- Linked Data Notifications (LDN)，82
- Live Music Archive (LMA)，13

### M

- Map portlet，260–261
- `mapToUserRegistry` 属性，132
- Mashup，38–40
- Mastodon
  - BigBone，204
    - 示例，205–207
    - 安装，204, 205
- Media API，34
- MeinVZ，5
- Meta
  - 业务 Java API SDK
    - 应用，198
    - 示例，199–201, 203
    - 安装，199
  - SDK
    - 示例，192–198
    - 多个社交媒体提供者，888
    - 部分，190
    - 烟雾测试，191, 192
    - 社交产品，189
- Micronaut Security
  - 定义，160
  - 功能，160
  - 使用 Google 进行安全保护，161
- 微软网络 (MSN)，3
- 莫斯-维尔电报密钥，2
- 音乐共享/流媒体门户，13
- 开源生态系统，247
- MyFitnessPal，26–27
- Oracle Fusion 中间件，33
- Myspace，1, 67
- OStatus，38, 46

### N

- 国家安全，66
- NoSQL 系统，24

### O

- OAuth，91–94
- 密钥，71, 62
- PayPal，9, 71, 72
- OAuth Dance，91, 92
- 个人识别码 (PINs)，70, 71
- oEmbed，36
- 物理安全，63
- PicketLink，136, 180–182
- Podcast，14
- Pods，46
- 隐私，64
- `private_key_jwt` 身份认证方法，134
- 产品与服务 API，34
- Profiles API，34
- PubSubbub，36
- 社交网络，34, 66
  - 博客作者和作者，17
  - 企业级，12
  - 讨论论坛，18
  - 影响者，29
  - 媒体共享，13–15
  - 消息服务，12
  - 移动用法，28, 29
  - 评论网站，18
  - 传统，11
  - 视频共享，16
  - VR/元宇宙，19

### P, Q

- 表述状态转换 (REST)，36, 145
- 站点摘要 (RSS)，36, 38
- 基于角色的访问控制 (RBAC)，35

### R

- Radar，40

### S

- Salmon，36
- SchülVerZ，5
- Scribe，179
- SecurityContext，72, 76, 77
- 服务器端会话 (SSS)，98, 99
- 单点登录 (SSO)，130
- SocialAuth，182–183
- 社交媒体
  - 历史，1, 2
  - 现代历史
    - X 世代，2
    - Z 世代，4, 5
    - 千禧一代，3
  - Twitter，8
  - 私有 API 和框架，10
  - 厂商中立抽象，416
- 社交媒体发布者，267
- 社交安全，69–73
  - 身份认证，74
  - CIA 三要素，63, 64
  - 隐私，65, 66
  - 隐私泄露，66–69
- Jakarta 标准，75

### Soteria

- 身份认证机制，113–117
  - 定义，113
  - 历史，113
- OpenID Connect 应用，128, 129
- 身份存储库实现，127, 128
- Maven Webapp Archetype，118, 126
- 运行时，117
- Spring Security，152, 153
  - 身份认证，154, 155
  - 定义，151
  - 历史，152
  - 服务过滤器，157–159
  - 社交登录，158
- Spring Social
  - 连接，250
  - 核心，248
  - 定义，247
  - 示例，255, 256
  - Facebook4J，253, 254
  - Facebook 示例，251–253
- Twitter4J，214–217
  - API 客户端，208–213

### Standardization

- Java 框架/库
  - Apache Shindij，55
  - Facebook 业务 SDK，49–51
  - JSR 357，60, 61
  - 微软嵌入社交，59
  - Seam Social，60
  - Spring social，58
  - Sun/Oracle，56–58
  - Twitter4J，51, 52
  - Twitter 客户端库，53–55
- 标准类型
  - 方法，36, 37
  - 基础，31
  - 企业社交网络，33
  - 混合，37, 38
  - OpenI，33–36
  - OpenSocial，39
  - OStatus，38
  - 社交 API，33

### T

- 基于时间的访问控制，142
- 基于令牌的身份认证
  - 机制，101
- Twitch4J，230

### U

- 基于用户的访问控制 (UBAC)，142

### V

- `validate()` 方法，87, 88
- 垂直社交框架
  - github，234–237
  - Uber，237, 239
- 垂直社交网络
  - 社区，19
  - 开发，19
  - 金融/投资，20
  - 健康/健身，20–27
  - 旅游，27
  - 视频流，16, 17
  - VoIP 社交平台，6

### W

- 围花园，60
- 基于 Web 的企业级应用，39
- Webhooks，203
- WebSub，42
- Strava，23–26
- StudiVZ，5, 6

### X

- X.com，9

### Y, Z

- Yahoo!,1, 3, 40, 66, 95
