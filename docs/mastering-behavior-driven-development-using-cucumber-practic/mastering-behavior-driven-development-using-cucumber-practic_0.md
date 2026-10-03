
# 使用 Cucumber 的行为驱动开发

## 实践与实现

### 页面对象设计模式、Cucumber 测试套件、POM TestNG 以及 Selenium Grid 协作

献给我亲爱的父母：Shri Ashok Anant Chaubal、Sulabha Ashok Chaubal，以及我亲爱的儿子 Arnav

## 关于作者

Pinakin Chaubal 是一位计算机科学学士（BE），在 IT 领域拥有超过 19 年的工作经验。他是认证的 `PMP`、`ISTQB`、`HP0-M47`（QTP 11.0 功能测试专家）和 `INS-21`（通用保险）。他目前在 Intellect Design Arena Ltd（前身为 Polaris Consulting）担任自动化架构师。

在此之前，他曾任于 Patni、Accenture、ACS International（美国）、L&T Infotech（美国和印度）、Polaris Financial Technology 和 SQS 等公司。他拥有 6 年美国驻外工作经验以及 8 个月的香港和中国工作经验，与客户紧密合作，并参与高级管理和利益相关者会议。

他服务过的客户包括 YES Bank、HSBC、Travelers Insurance、Harleysville insurance、Albertsons 零售链、Bellsouth Telecommunications、GE-Fleet Services 和 GE-Supply。

他是 YouTube 频道“Automation Geek”的创立者，该频道教授 PMP、ISTQB、使用 Selenium 和 Cucumber 进行测试自动化以及使用 JMeter 3.0 进行性能测试。

他是 Packt Publishing 出版的《Page Object Model using Selenium WebDriver and Java》、《Selenium WebDriver Quick Start Guide》以及 BPB Publications 出版的《Selenium Framework design with Keyword Driven Testing》的作者。他还是 Carl Cocchiaro 新出的 Selenium 框架书籍《Selenium Framework Design in Data Driven Testing》的评审员。

### 关于评审员

Narottam Singh 是一位软件测试工程师，在交付高质量产品方面拥有超过 10 年的经验。目前，他的职责包括 Android 和 iOS 平台上移动 App 的端到端测试（手动和自动化）。

到为止，他有机会接触软件行业中一些最热门的技术，例如 Elastic search、Kafka、OpenShift 和测试自动化（Web、Rest-API 和移动应用）。他使用 `JAVA`、`Python`、`Node.js`、`Selenium`、`Cypress.io` 和 `Linux` 编程语言进行测试自动化。

在不同机构的职业中，Narottam 学到产品质量对于客户和终端用户的满意度至关重要。他始终认为，如果用质量范式构建产品，就能让客户的生活变得轻松。

LinkedIn：`https://www.linkedin.com/in/narottamgla`

GitHub：`https://github.com/narottamgla`

Garima Chauhan 是一位软件测试工程师，在实现高质量产品方面拥有超过 6 年的经验。目前，她在 Walmart 担任三级质量工程师。她负责 Android 和 iOS 平台上移动 App 的端到端测试（手动和自动化）。

到为止，她已参与了几乎所有的测试垂直领域，即手动测试、自动化测试、负载测试、性能测试和 A/B 测试。为了交付稳定且无错误的产品，她开始学习自动化测试。她使用 `JAVA`、`Python`、`Selenium`、`JavaScript` 和 `Linux` 编程语言并实施了测试。

Garima 的职业始于 B2B 公司 RechargeItNow，担任助理质量工程师进行手动测试。随后，她在 Citrus Payments Solutions 和 PayU 工作了近 5 年的首席软件工程师。她担任首席测试软件工程师并交付了完全测试的产品，以确保用户在支付流程中无无体验。

所有产品已并在 Hotstar、GoAir、Dream 11、NDTV Gadgets、Big Basket、Lenskart、Zee、Videocon 等更多商户使用……

她曾在 Sequoia Consulting Group 工作过，这是一家位于美国的公司，从事健康保险和人力资源管理领域。在该机构，她学习了如何测试或验证大量的敏感数据，这完全是手动测试和自动化测试的结合。

她在该机构工作了 1 年，学习了不同的测试方法，并主要负责微服务、API 和网站门户。Garima 喜欢花时间测试事物，她的爱好包括旅行、瑜伽和烹饪。她始终相信，如果用质量范式构建产品，就能让客户的生活变得轻松。

## 致谢

我想感谢几位在本书编写期间为我提供持续支持的人。首先，我要感谢我的父母不断鼓励我写这本书——没有他们我无法完成。
