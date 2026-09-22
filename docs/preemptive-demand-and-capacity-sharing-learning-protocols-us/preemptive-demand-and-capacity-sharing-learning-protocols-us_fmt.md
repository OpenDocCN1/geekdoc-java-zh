
# 基于长短期记忆 (LSTM) 神经网络自编码器的抢占式需求与容量共享学习协议

Praditya Ajidarma*, Shim N. Hof**, Raditya A. Prada**, Wirawan N. Nugro**, Abdul H. Halim**

*Cprism, 普渡伊大学, West Lafayette, IN 47907 美国

(邮箱: pajiram@purdue.edu)

**万隆理工学院 (Institut Teknologi Bandung), Bandung, West Java 40132 印度尼西亚**

(邮箱: akhalim@itb.ac.id)

摘要：本研究旨在应对未来受干扰影响的韧性全球供应链的挑战。在企业协作网络（CNEs）中，企业最近通过容量共享和信息资源进行协作。一种常见的协作共享做法是通过需求和容量共享（CS）进行协作共享，旨在尽管市场不确定性和供应链中断，仍能确保向客户及时交付。CNE 实施的一个关键挑战是，确保容量共享协议在实际需求出现时，能够防止协调失败和订单积压。本研究旨在开发一种新的抢占式 CS——协作式 CS，它利用机器学习从历史数据中学习。使用长短期记忆 (LSTM) 神经网络自动编码器来实时检测异常。检测到的异常可以进入容量共享协议，从而启动抢占式 CS。通过印度尼西亚汽车制造商的案例验证了该模型。平均而言，对于本研究，与协作和非抢占式容量共享协议（DSP）基准场景相比，基于容量学习协议的抢占协议提高了需求-容量共享 CNEs 的履行率。还需要进一步的研究以进行理解。

关键词：协作理论，需求与容量共享，学习协议，抢占式协议

## 1. 引言

企业协作网络（CNEs）中的需求与容量共享（CS）协议旨在协调需求和容量的共享与分配决策。该协议基于协作控制理论，防止企业容量利用不足并最大限度地减少容量共享的延迟，以提高 CNE 的多目标准则（Yoon and Notof, 2015）。CS 协议已扩展并推广为信息物理系统的资源共享框架（Nsayal et al., 2014），并得到了韧性（R）（Reyes and Lef, 2015）和动态协作线（Zhong and Notof, 2020）的支持，CS 协议旨在确保协作供应链网络应对干扰的韧性。

制造系统的动态性被表示为时间序列，这为 CNE 建模引入了新的复杂性维度。研究人员已经开发了具有异构批处理器的共享算法（Hidayat et al., 2016）、学习与遗忘效应（Yerselli et al., 2019）以及与维护计划的结合（Zahed et al., 2016），以解决单个企业内部的复杂性，但很少有模型解决供应链网络的动态性。智能 CS（ICS）协议被开发用于根据基于分布的决策的过程形成应急容量共享（Soek et al., 2016）。关联/分布协议也被开发用于解决可重构 CNEs 的成员身份问题（Yoon and Notof, 2011）。

少数研究通过适应实时数据更新和 CS 协议的自适应解决方案来解决制造系统的动态性。自适应协作 CS 协议被开发用于根据长期预期利润的历史来执行资源分配（Soek and Notof）。基于长期预期利润的抢占式 CS 协议被开发用于通过需求，的 CS 协议以缓解干扰（Yoon and Notof, 2011）。© 2022 作者所有。这是一篇基于 CC BY-NC-ND 许可的开放获取文章。

## 2. 背景

### 2.1 需求与容量共享

需求与容量共享（CS）协议在企业协作网络（CNEs）中旨在协调需求和容量的共享与分配决策。该协议基于协作控制理论，防止企业容量利用不足并最大限度地减少容量共享的延迟，以提高 CNE 的多目标准则（Yoon and Notof, 2015）。CS 协议已扩展并推广为信息物理系统的资源共享框架（Nsayal et al., 2014），并得到了韧性（R）（Reyes and Lef, 2015）和动态协作线（Zhong and Notof, 2020）的支持，CS 协议旨在确保协作供应链网络应对干扰的韧性。

制造系统的动态性被表示为时间序列，这为 CNE 建模引入了新的复杂性维度。研究人员已经开发了具有异构批处理器的共享算法（Hidayat et al., 2016）、学习与遗忘效应（Yerselli et al., 2019）以及与维护计划的结合（Zahed et al., 2016），以解决单个企业内部的复杂性，但很少有模型解决供应链网络的动态性。智能 CS（ICS）协议被开发用于根据基于分布的决策的过程形成应急容量共享（Soek et al., 2016）。关联/分布协议也被开发用于解决可重构 CNEs 的成员身份问题（Yoon and Notof, 2011）。

少数研究通过适应实时数据更新和 CS 协议的自适应解决方案来解决制造系统的动态性。自适应协作 CS 协议被开发用于根据长期预期利润的历史来执行资源分配（Soek and Notof）。基于长期预期利润的抢占式 CS 协议被开发用于通过需求，的 CS 协议以缓解干扰（Yoon and Notof, 2011）。

### 2.2 时间序列中的异常检测

异常检测是一种数据挖掘过程，用于确定数据中发现的异常及其类型（Prost et al., 2015）。异常检测方法包括基于聚类的异常检测、`孤立森林`（isolation forests）、向量机，除了这些经典方法，还有其他基于信号检测的异常检测、时间序列模型（指数模型、`Holt-Winters`）以及深度学习（例如自动编码器和 `LSTM` 神经网络）（Su et al., 2019），以及降维（鲁棒主成分自组织映射）等（Sakakura and Yairi, 2014）。

与标签相关的异常检测类有：监督异常检测和无监督异常检测（Chandola et al., 2009）。在异常检测过程中，有几种情况可以使用。其中包括基于近邻的异常检测（Tian, Azarian and Peicht, 2014）、基于聚类的异常检测（Sairaj, Prugel and Wills, 2012）以及基于统计方法的异常检测（Chandola et al., 2009）。

基于 `LSTM` 的异常检测被分类为无监督异常检测，旨在解决无标签异常问题。模型结合时间序列数据并使用重构函数构建一个新的时间序列模型，以衡量重构质量。原始时间序列数据（实际数据）与重构之间的差异将是残差。模型使用无异常数据进行训练，异常数据的重构误差值很大（Walsh et al., 2020）。指标作为时间序列 $X_t, t=1, 2, \dots, T$ 进行训练，它是 $X$ 的重构。重构误差（$X$ 与 $Y$ 之间的差异）是 $||X_t - \hat{X}_t||, t=1, \dots, T$。每个时间步重构误差的欧几里得距离可以作为异常检测的标准（Wang et al., 2022）。

## 3. 方法论

将数据解码到输出层。然后，将编码后的输出与初始数据进行比较，并对产生的误差进行反向传播，以更新指标的权重值。给定输入 $x \in \mathbb{R}^n$，编码器将 $x$ 压缩为编码后的表示 $z = g(x) \in \mathbb{R}^m$。解码器将重构该表示以输出 $\hat{x} = f(z) \in \mathbb{R}^n$。自动编码器通过最小化重构误差进行训练。

预防性需求共享协议的通用框架如图 1 所示。本研究通过扩展之前开发的容量共享（DCS）网络（Yoon and Nof, 2010），结合基于自动编码器的异常检测技术（Wang et al., 2022）来提前预测协作需求。DCS 和预防性协议都扩展了通用框架。

![预防性需求共享协议的概念框架](img/2e808fcef49f60d7662f167e51d8a4f_2_0.png)

协议详细如下：首先，使用上一个周期的历史数据 $q_t = \{q_t^{(i)}\}$ 来训练 `LSTM` 自动编码器生成异常 $a_t$。第二个周期用于预测协作需求。模型监控订单量 $X_t$，并计算 $e = ||X_t - \hat{X}_t||, t=1, \dots, T$。一旦 `LSTM` 自动编码器检测到订单量 $X_t$ 使得 $e \in A$，它将提高阈值。该阈值激活预防性 DCS，共享容量值为 $C_t$ 和共享长度 $P_t$。

随着协作需求的预测，协议将确定一组 $C_t$、$P_t$ 以及 DCS 的最优参数。协议的最优性由 DCS 的目标标准（Yoon and Nof, 2010）决定，基于本地需求预测率 $y_t$ 本地需求预测 $y_t$ 以及基于协作的需求预测率 $y_t$。

$$Y_t = Y_t + Y_c = \sum_{i \in Y_t} D_i + \sum_{j \in Y_c} D_j$$

## 4. 数值示例与分析

研究中提出的方法使用了来自汽车行业数据集的数值示例。该数据集包含了 2019 年 1 月到 2020 年 12 月期间收集的两年时间序列到达数据。

![高频 SKU 的订单量](img/2e808fcef49f60d7622f167e51d8a4f_3_0.png)

![高频 SKU 的订单量](img/2e808fcef49f60d7622f167e51d8a4f_3_1.png)

图 4：88515BZ50 第 31 个订单的测试损失和阈值；右侧：可视化。由于是预防性 DCS 协议，原始时间序列数据（实际数据）与重构之间的差异将是残差。模型使用无异常数据进行训练，异常数据的重构误差值很大。这种可视化如图 5 所示。

![可视化示例](img/2e808fcef49f60d7622f167e51d8a4f_3_2.png)

### 4.1 基于自动编码器的异常检测

自动编码器通过最小化重构误差进行训练。预防性需求共享协议的通用框架如图 1 所示。本研究通过扩展之前开发的容量共享（DCS）网络（Yoon and Nof, 2010），结合基于自动编码器的异常检测技术（Wang et al., 2022）来提前预测协作需求。DCS 和预防性协议都扩展了通用框架。

### 4.2 基于 LSTM 的异常

基于 `LSTM` 的异常检测被分类为无监督异常检测，旨在解决无标签异常问题。模型结合时间序列数据并使用重构函数构建一个新的时间序列模型，以衡量重构质量。原始时间序列数据（实际数据）与重构之间的差异将是残差。模型使用无异常数据进行训练，异常数据的重构误差值很大。指标作为时间序列 $X_t, t=1, 2, \dots, T$ 进行训练，它是 $X$ 的重构。重构误差（$X$ 与 $Y$ 之间的差异）是 $||X_t - \hat{X}_t||, t=1, \dots, T$。每个时间步重构误差的欧几里得距离可以作为异常检测的标准（Wang et al., 2022）。

| 参数 | 数值 |
| :--- | :--- |
| 共享容量比例 | $c_t=(0.7)$ |
| 预防性共享周期（月） | $P_t=(1-t)$ |
| 仿真时间（天） | 24 |
| 重复次数 | 100 |

表：预防性需求共享协议的参数

## 参考文献

Chandola, V., Banerjee, A. and Kumar, Y. (2009) "异常检测," *ACM Computing Surveys*, 31(3), pp. 1–35. doi:10.1145/1551840.1551848

Hidayat, N.P.A. et al. (2016) "适用于异构批处理的批调度模型," *International Journal of Production Research*, 54(4), pp. 1170–1185. doi:10.1080/00200743.2015.105622.

Hochreiter, S. and Schubert, J. (1997) "长短期记忆神经网络," *Neural Computation*, 9(8), pp. 1735–1780. doi:10.1002/neco.1997.9.1735

Mohaddam, M. and Sof, S.Y. (2014) "企业协作中基于最佳匹配决策的需求与容量共享," *International Journal of Production Economics*, 148, pp. 93–109. doi:10.1016/j.ijpe.2013.11.015.

Mohaddam, M. and Sof, S.Y. (2016) "需求与容量共享的实时优化与控制," *International Journal of Production Economics*, 171, pp. 495–506. doi:10.1016/j.ijpe.2015.07.038

Nayak, A. et al. (2016) "信息物理系统中的资源共享：建模框架与案例研究," *International Journal of Production Research*, 54(23), pp. 6968–6983. doi:10.1080/00200743.2016.114649

Nguyen, H.D. et al. (2021) "基于 LSTM 和注意力技术的预测与异常检测及其在供应链管理中的应用," *International Journal of Information Management*, 57, pp. 102282. doi:10.1016/j.ijm.2020.102282.

Pereira, J. and Silva, V. (2018) "使用带注意力的变分循环自编码器进行时间序列无监督异常检测," 收于第 18 届国际机器学习与应用会议 (ICMLA). IEEE, pp. 1275–1282. doi:10.1109/ICMLA.2018.000267

Provitar, O.L., Liner, Y.M. and Vers, M.M. (2019) "基于 LSTM 自编码器的时间序列无监督异常检测," 2019 IEEE 信息技术进展国际会议 (AIT)., pp. 513–517. doi:10.1109/AIT.A2019.9030505

Reyes, R. L. and Sof, S.Y. (2015) "用于协作供应网络的团队韧性框架," *Computers & Industrial Engineering*, 90, pp. 67–85. doi:10.1016/j.cie.2015.08.017.

Sakurada, M. and Yairi, T. (2014) "使用带非线性降维的自编码器进行异常检测," 收于 MLSDSA2014 数据科学机器学习研讨会论文集-MLSDSA’14. New York, New York: ACM. pp. 4–11. doi:10.1145/2689746.2689747



## References

Seok, H., Kim, K. and Sof, S.Y. (2016) "韧性供应网络的智能认知多源模型," *Expert Systems with Applications*, 51, pp. 107–119. doi:10.1016/j.esa.2015.12.026.

Seok, H. and Sof, S.Y. (2014) "同一网络水平层间为了平衡收益的协作共享," *International Journal of Production Research*, 52(6), pp. 1622–1643. doi:10.1080/00200743.2013.

Seok, H. and Sof, S.Y. (2014) "协调需求与容量共享的动态协调," *International Journal of Production Economics*, 147, pp. 136–146. doi:10.1016/j.ijpe.2013.09.

Su, Y. et al. (2019) "通过随机循环网络进行多变量时间序列鲁棒异常检测," *Proceedings of the 25th ACM SIGKDD Conference on Knowledge Discovery and Data Mining*. New York, NY: ACM. pp. 2329–2336. doi:10.1145/3357492-335753.

Sver, L., Petit-Bettanger, A. and Will, G. (2012) "无监督异常检测在," *Anomaly Detection*, pp. 135–145. doi:10.1007/978-3-642-30507-8.

Tian, J., Arian, M. and Mech, G. (2014) "基于自组织映射的异常检测,"

Toledo, M. et al. (2018) "大规模时间序列的实时异常检测," *KDD 2017: Financial Anomaly Detection*. PMLR (Proceedings of Machine Learning Research), pp. 55–66.

Wang, Y. et al. (2022) "使用循环网络检测制造系统的时间序列异常," *International Journal of Manufacturing Systems*, 62, pp. 311–320. doi:10.1016/j.ijms.2022.01.003.

Wulsin, D. et al. (2010) "使用深度信念网络进行脑波半监督异常检测," *Proceedings of the 20th International Conference on Machine Learning and Applications (IEEE)*, pp. 436–441. doi:10.1109/ICMLA.2010.701.

Yoon, S.W. and Sof, S.Y. (2010) "协作企业中的需求与容量共享决策与协议," *Decision Support Systems*, 49(4), pp. 442–450. doi:10.1016/j.dss.2009.05.005.

Yoon, S.W. and Sof, S.Y. (2011) "需求容量共享网络中的附属决策模型," *International Journal of Production Economics*, 130(2), pp. 135–143. doi:10.1016/j.ijpe.2010.10.002.

Zhong, H. and Sof, S.Y. (2020) *Dynamic Collaborative Lines*. Springer International Publishing. doi:10.1007/978-3-030-34463-4.
