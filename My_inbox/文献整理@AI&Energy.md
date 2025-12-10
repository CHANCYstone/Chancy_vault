---
aliases:
created: "[[2025-11-07]]"
🤔:
in:
up:
related: "[[文献整理1]"
author:
---
[[文献整理1]]

[[文献整理2]]

[[文献整理3]]



# 🌲 Evergreen Note
```

```
---

## uid: 20251107-AI-ENERGY-READMAP note-type: evergreen owner: gouge status: in_progress area: 研究·AI×能源·资本市场 created: 2025-11-07 updated: 2025-11-07 keywords: [AI, Energy, Spillover, TVP-VAR, QQR, Connectedness, Risk, Electricity, Renewables, Data centers] tags: [evergreen, ai-energy, literature-map, methodology, replication]

# 🌲 Evergreen Note｜AI × Energy：核心文献速览与方法地图

## ✍️ Summary（200–300字）

人工智能与能源体系的关系在学术与资本市场层面呈现“短期需求侧拉动、长期效率侧提升、结构性非线性与频段异质”的特征：短期内，AI 数据中心与算力投资通过电力负荷、铜/油气/电网设备链条带来需求冲击；中长期，AI 通过预测优化、运维提效、绿色创新与人力资本再配置提升能源效率与绿色全要素生产率（GTFP），但存在“反弹效应”与门槛条件（贸易开放度、区域差异、政策与数字基础设施）。方法上，量化研究从**分位数与时频域溢出（QQR/QVAR、Cross-Quantilogram、TVP‑VAR频域连接度）**到**非线性因果/NARDL**与**XAI**逐步深化，结论普遍指向：极端行情（尾部分位）下短期溢出占优，常态阶段长期成分主导，AI 与清洁能源在不同阶段可能出现“拥挤/替代—协同/共振”的切换。

---

## 🧭 Research Questions（RQ）

- **RQ1 机制**：AI 如何通过需求（算力负荷）、效率（预测/调度/运维）、融资与政策不确定性通道影响能源与资本市场？
    
- **RQ2 时频/分位**：短期 vs 长期、左/右尾部下，AI—能源/碳/大宗之间的风险与收益溢出结构如何变化？
    
- **RQ3 门槛与异质性**：贸易开放、地区发展水平、AI 强度、人力资本与数字基建是否存在门槛与区域异质？
    
- **RQ4 反事实**：若 AI 电力需求与效率提升同时发生，何者主导净效应？
    
- **RQ5 政策与投资**：如何将“短期冲击—长期优化”的时间不一致性内生到对冲/配置与监管框架？
    

---

## 🔧 方法与可复现实证菜单（Method Cheatsheet）

- **TVP‑VAR 频域连接度**（Diebold–Yilmaz 扩展；Total / 1–21 / 21–Inf）：适合刻画动态、频段与方向性溢出；常与滚动窗口比较。
    
- **Quantile‑on‑Quantile（QQR）/ QVAR / Cross‑Quantilogram**：捕捉**尾部分位**下的双向与非线性依赖，识别“高‑高”“低‑低”“高‑低”态下的风险传导结构。
    
- **NARDL / 门槛模型**：检验非对称、非线性与门槛效应。
    
- **XAI（可解释AI）**：在价格/波动预测中比较于传统回归的增益与可解释贡献。
    
- **LSTM/集成学习 + 传统计量**：用于电力负荷/新能源并网预测，或与连接度框架组合进行稳健性校验。
    

> 复现建议：统一事件时点（如 GPT‑4/主要政策/油价冲击），对比**总频段 vs 1–21 vs 21‑Inf**；对**AI 指数/新闻关注/交易量**与**电力/新能源/化石能源/碳**构建多市场系统，进行滚动与分位交叉验证。

---

## 🗺️ 证据地图（Evidence Map | 摘要化）

|主题|样本/数据|方法|关键发现|备注|
|---|---|---|---|---|
|AI ↔ 可再生能源/清洁技术|2018–2023 多市场|广义 QQR 连接度|尾部风险溢出显著；AI/清洁科技与股市倾向净输出，原油与美元指数多为净接收；负相关对冲在部分尾部成立。|资本市场对冲启示|
|AI ↔ 能源结构/转型|中国多期|QQR+小波|长期上 AI 提升可再生占比；短中期整合难度致负面效应显现。|时间不一致性|
|AI ↔ 新能源车|高频|波列‑QQR|短期不同分位下存在“拥挤效应/替代效应”；中长期弱化。|行业协同非必然|
|AI ↔ 能源贫困/绿色福祉/GTFP|多国/地市面板|TWFE/门槛/IV|AI 总体改善能源贫困与 GDW，经由 GTFP、人力资本、创业活动，中西部/东北等存在区域异质。|门槛与异质性|
|AI ↔ 投资与政策不确定性|能源企业|门槛/机制|气候政策不确定性抑制投资；AI 采用可通过分散客户集中度、促进绿专利转化缓解。|企业层证据|
|AI ↔ 电力负荷/预测|电力市场|多准则集成/目标规划|分布式学习与集成决策可提升预测与调度鲁棒性。|运维与调度|
|AI ↔ 油气/传统能源|期货/指数|TVP‑VAR 频域|短期成分在极端时期占优；天然气/原油在系统中常为风险接收或中介节点。|能源链位置|
|ChatGPT 指标↔大宗回报|海量新闻|GPT 指标|ChatGPT 提取的文本比 BERT/BoW 更优，具经济意义。|文本到交易|

> 注：上表为对用户收录文献的综合抽象，以便快速定位“样本—方法—发现—适用场景”的映射。

---

## ✅ TODO（执行清单）

---

## 🧩 引用与阅读便签（按主题分组）

### A. 方法与框架

- Diebold, F. X., & Yilmaz, K. (2009). _Measuring financial asset return and volatility spillovers, with application to global equity markets_. **The Economic Journal, 119**(534), 158–171. https://doi.org/10.1111/j.1468-0297.2008.02208.x
    
- Gubareva, M., Shafiullah, M., & Teplova, T. (2025). Cross‑quantile risk assessment: The interplay of crude oil, artificial intelligence, clean tech, and other markets. **Energy Economics, 141**, 108085. https://doi.org/10.1016/j.eneco.2024.108085
    
- Gong, X., Liu, Y., & Wang, X. (2021). Dynamic volatility spillovers across oil and natural gas futures markets based on a time‑varying spillover method. **International Review of Financial Analysis, 76**, 101790. https://doi.org/10.1016/j.irfa.2021.101790
    

### B. AI × 能源转型/效率/福祉

- Zhao, Q., Wang, L., Stan, S.‑E., & Mirza, N. (2024). Can artificial intelligence help accelerate the transition to renewable energy? **Energy Economics, 134**, 107584. https://doi.org/10.1016/j.eneco.2024.107584
    
- Tao, W., Weng, S., Chen, X., ALHussan, F. B., & Song, M. (2024). Artificial intelligence‑driven transformations in low‑carbon energy structure: Evidence from China. **Energy Economics, 136**, 107719. https://doi.org/10.1016/j.eneco.2024.107719
    
- Li, L., Zhao, J., Yang, Y., & Ma, D. (2025). Artificial intelligence and green development well‑being: Effects and mechanisms in China. **Energy Economics, 141**, 108094. https://doi.org/10.1016/j.eneco.2024.108094
    
- Li, X., Li, S., Cao, J., & Spulbar, A. C. (2025). Does artificial intelligence improve energy efficiency? **Energy Economics, 142**, 108149. https://doi.org/10.1016/j.eneco.2024.108149
    
- Fu, Y., Shen, Y., Song, M., & Wang, W. (2024). Does artificial intelligence reduce corporate energy consumption? **Economic Analysis and Policy, 83**, 548–561. https://doi.org/10.1016/j.eap.2024.07.005
    
- Ding, T. (2024). An inquiry into the nexus between artificial intelligence and energy poverty in the light of global evidence. **Energy Economics**.（在线优先）
    

### C. AI × 市场连接与溢出（股票/电力/碳/清洁能源/化石能源）

- Wang, K.‑H., Jiang, X.‑Y., & Tang, Y. (2025). Artificial intelligence, cloud computing, blockchain, and the energy market in the era of energy transition. **Energy Economics, 151**, 108975. https://doi.org/10.1016/j.eneco.2025.108975
    
- Xu, Y., Shao, X., & Tanasescu, C. (2024). How are artificial intelligence, carbon market, and energy sector connected? **Energy Economics, 132**, 107477. https://doi.org/10.1016/j.eneco.2024.107477
    
- Yousaf, I., Ohikhuare, O. M., Li, Y., & Li, Y. (2024). Interconnectedness between electricity and AI‑based markets during the crisis periods. **Energy Economics, 139**, 107885. https://doi.org/10.1016/j.eneco.2024.107885
    
- Jabeur, S. B., Bakkar, Y., & Cepni, O. (2025). Do global COVOL and geopolitical risks affect clean energy prices? Evidence from explainable AI models. **Energy Economics, 141**, 108112. https://doi.org/10.1016/j.eneco.2024.108112
    
- Ren, Z., Chen, Y., Ma, S., & Shen, T. (2025). Artificial Intelligence and Energy Market Quartile Spillovers. **SSRN**. https://doi.org/10.2139/ssrn.5151621
    

### D. AI × 车辆/5G/供应链等应用侧

- Gu, J., Wu, Z., Song, Y., & Nicolescu, A.‑C. (2024). A win‑win relationship? New evidence on artificial intelligence and new energy vehicles. **Energy Economics, 134**, 107613. https://doi.org/10.1016/j.eneco.2024.107613
    
- Li, T., Yu, L., Ma, Y., et al. (2023). Carbon emissions of 5G mobile networks in China. **Nature Sustainability, 6**(12), 1620–1631. https://doi.org/10.1038/s41893-023-01206-5
    
- Saen, R. F., Yousefi, F., & Azadi, M. (2024). Artificial intelligence powered predictions: Enhancing supply chain sustainability. **Annals of Operations Research**. https://doi.org/10.1007/s10479-024-06088-0
    
- Repetto, M., Colapinto, C., & Tariq, M. U. (2025). Artificial intelligence‑driven demand forecasting: An application to the electricity market. **Annals of Operations Research, 346**(2), 1637–1651. https://doi.org/10.1007/s10479-024-05965-y
    

### E. 生成式AI与资产定价

- Eisfeldt, A. L., Schubert, G., & Zhang, M. B. (2023/2024). _Generative AI and Firm Values_. Working paper/Journal version（关注 AMH 投组与事后收益异象）。
    
- Gao, S., Wang, S., Wang, Y., & Zhang, Q. (2025). ChatGPT and commodity return. **Journal of Futures Markets, 45**(3), 161–175. https://doi.org/10.1002/fut.22568
    

> 提示：更多条目已收录于你的 Zotero/Note 列表；此处选取代表性文献生成 APA7 引用与主题归档，便于后续写作引用。

---

## 🧪 研究设计草图（可直接写入方法部分）

1. **数据**：
    

- 市场：AI 指数（行业/主题/机器人）、清洁能源与子行业指数、原油/天然气、美元指数、碳配额；日/周频。
    
- 宏观：电力负荷/价差（峰谷）、政策不确定性（CPU）、贸易开放度；月/季频。
    

2. **模型顺序**：
    

- TVP‑VAR 频域连接度 → 识别时频结构与方向性；
    
- QQR/QVAR/Cross‑Quantilogram → 尾部分位依赖与非线性；
    
- NARDL/门槛 → 验证非对称与门槛；
    
- XAI/LSTM → 预测与可解释度对比；
    

3. **识别**：事件研究（GPT‑4/重大政策/油价冲击）+ 工具变量（法系起源/机器人滞后/地理扩散）作稳健性参考。
    

---

## 🗂️ Logs

- [[2025-11-07]] 首版阅读地图成稿；待补：数据口径统一与图例规范模板。
    

---

## 📌 附：写作模板（段落骨架）

> **机制—证据—异质—政策/投资**四段式： (i) 阐明 AI→能源的双重路径与时间不一致；(ii) 以 TVP‑VAR 与 QQR 证据支撑短期 vs 长期差异；(iii) 呈现门槛/区域异质与反弹效应；(iv) 给出对冲与监管的“短期稳—长期优”组合策略。

---

## 📚 参考文献（APA7，节选）

（已在“引用与阅读便签”中列出，写作时可直接复制粘贴；建议配合 Zotero‑Better BibTeX 管理 citekey。）



太赞了，这一沓资料已经足够沉淀成一条可复用的 Evergreen！我把你贴进来的条目做了结构化梳理，产出一份可直接粘贴到 Obsidian 的长笔记模板（含：原子化主张、机制脉络、可操作 TODO、Dataview 片段与按 APA 的参考文献）。你可以把下面整段 Markdown 一次性复制到目标笔记里，用它作为后续持续迭代的“母笔记”。

---

````
---
title: 人工智能 × 能源：机制—市场—福利（Evergreen）
uid: 20251107-AI×Energy-evergreen
tags:
  - evergreen
  - AI-energy
  - EnergyEconomics
  - spillover
  - transition
  - efficiency
  - ESG
  - risk
created: 2025-11-07
updated: 2025-11-07
aliases:
  - AI and Energy—Mechanisms, Markets, Welfare
cssclass: evergreen
---

# ✍️ Summary
- 人工智能（AI）对能源系统具有“双元效应”：一方面通过预测、调度与优化显著提升能效和绿色全要素生产率（GTFP）；另一方面在短中期内因数据中心等负载带来能耗回弹与化石侧的“阶段性推升”。（Zhao et al., 2024; Li et al., 2025）
- 跨市场联动呈**分位与频域异质**：极端分位（尾部）风险溢出更强，短期（高频）主导危机期的冲击传导，常态时期则由长期分量驱动。（Gubareva et al., 2025; Yousaf et al., 2024）
- 企业与城市层面证据显示：AI 采用可降低能耗/能强度、改善能源安全与绿色福祉，但存在地区、行业、门槛与非线性差异。（Fu et al., 2024; Xin Li et al., 2025; Wen Zhang & Wen, 2025; Li et al., 2025）
- 治理要点：抑制能耗回弹、加速清洁电源占比、面向极端事件管理尾部风险，并将 AI 纳入 ESG 与披露治理框架。（Zhang & Wang, 2024; He & Wang, 2025）

---

# 🌱 Atomic Claims（原子化主张）
- **[A1] AI 提升能效但短期可能推高能耗占比**：长周期上 AI 提升可再生占比；短中期因融入成本、系统瓶颈与回弹效应，RE 占比可能受抑。（Zhao et al., 2024）
- **[A2] 风险溢出具有“分位—频域”不对称**：AI/清洁科技与原油、美元等传统资产之间的尾部传染显著强于中位，极端上行时油价与美元更像“缓冲器”。（Gubareva et al., 2025）
- **[A3] 危机期短期联动抬升**：电力与 AI 股票之间在疫情与地缘冲突期出现更强的时变连通性，且系统性与市场风险资产（黄金、比特币、债券）是关键驱动因子。（Yousaf et al., 2024）
- **[A4] 企业层面 AI 采用降低能耗/能强度**：机制经由技术创新与数字化转型，在国企、高技行业与非劳动密集型企业更显著。（Fu et al., 2024; Weike Zhang & Zeng, 2024）
- **[A5] 制度与门槛效应重要**：贸易开放、数字金融、环境规制、人力资本与区域差异显著调节 AI→转型/减排/绿色福祉的效应强度与方向。（Qiang Wang, 2024; Li et al., 2025; Wen Zhang & Wen, 2025）
- **[A6] 市场结构中 AI 常为净风险输出者**，传统能源（如原油）更常为净接受者；但在不同分位/频段角色可切换。（Gubareva et al., 2025; Wang et al., 2025）

---

# 🔁 Mechanism Map（机制脉络）
- **效率链**：AI（预测/调度/运维/需求响应） → 能效↑ / 能强度↓ → 排放强度↓（Xin Li et al., 2025; Fu et al., 2024）
- **回弹链**：AI 负载↑（训练/推理/5G/边云） → 用电与制冷需求↑ → 化石边际电源调用↑ → **短中期 RE 占比下降风险**（Zhao et al., 2024；Li et al., 2023, Nat Sustain 5G）
- **金融—联动链**：AI/清洁科技 ↔ 原油/美元/债市（分位—频域连通、尾部更强） → 资产配置与对冲需求变化（Gubareva et al., 2025）
- **治理—ESG 链**：AI 采用 → 绿色创新/管理能力/信息透明度↑ → 绿色福祉、能源安全、ESG 表现↑；同时需抑制“漂绿”。（Li et al., 2025; He & Wang, 2025）

---

# 📈 Evidence Patterns（关键经验证据）
- **量化方法**：QQR（分位对分位）、QVAR/TVP-VAR（时变参数—频域连通）、NARDL（非对称长期/短期）、PSM-DID/SDM（空间/因果）、XAI（可解释 ML）等。
- **尾部主导**：极端分位（q=0.01/0.99）溢出 > 中位，危机期短期分量主导总连通，常态期由长期分量主导。（Gubareva et al., 2025; Wang et al., 2025）
- **非线性与门槛**：AI→RE/减排存在倒 U 或门槛（贸易开放、AI 强度、数字金融、人力资本）。（Qiang Wang, 2024; Li et al., 2025）
- **企业/城市层面的普适但异质的改善**：AI 采用降低能耗/能强度、提升能源安全/绿色福祉，但区域与产业异质显著。（Fu et al., 2024; Wen Zhang & Wen, 2025; Li et al., 2025）

---

# 🎓 Teaching / 应用建议
- **课堂讨论题**（跨学科/财商）：为什么同样是“AI × 能源”，在危机期与常态期的资产联动结论会相反？如何用“尾部 vs. 中位”的图示帮助学生直观理解？
- **研究复现清单**：优先复刻 Zhao (2024) 的 QQR 与 Yousaf (2024) 的 TVP-VAR；在你现有的 returns_long 上，加入 AI/能源/碳市场指数，分位—频域联动图一套出图范式。

---

# ✅ TODO（下一步最小行动）
- [ ] 整理指标字典：AII/AIW、ENI、WTI/Brent、USD、碳价、清洁能源子板块（风/光/储能）。
- [ ] 复刻 QQR（wavelet + QQR）与 TVP-VAR（频域连通）：输出 Total/1–21/21–Inf 三频段网络与时变总连通曲线。
- [ ] 回弹测度：以数据中心用电/温感负荷作为外生冲击，做 NARDL 与门槛回归（贸易开放/数字金融为门槛）。
- [ ] ESG/披露：收集年报文本，做“漂绿识别”基线分类器，与 He & Wang (2025) 的发现对比。

---

# 🔍 Dataview（自动汇总相关笔记）
```dataview
TABLE file.link AS "Note", summary AS "Key Take", created, updated
FROM #AI-energy OR #EnergyEconomics
SORT updated DESC
````

---

# **📚 References（APA）**

- Fu, Y., Shen, Y., Song, M., & Wang, W. (2024). Does artificial intelligence reduce corporate energy consumption? _Economic Analysis and Policy, 83_, 548–561. https://doi.org/10.1016/j.eap.2024.07.005
    
- Gubareva, M., Shafiullah, M., & Teplova, T. (2025). Cross-quantile risk assessment: The interplay of crude oil, artificial intelligence, clean tech, and other markets. _Energy Economics, 141_, 108085. https://doi.org/10.1016/j.eneco.2024.108085
    
- He, L.-Y., & Wang, L. (2025). Can artificial intelligence curb greenwashing? _Energy Economics, 152_, 108954. https://doi.org/10.1016/j.eneco.2025.108954
    
- Li, L., Zhao, J., Yang, Y., & Ma, D. (2025). Artificial intelligence and green development well-being: Effects and mechanisms in China. _Energy Economics, 141_, 108094. https://doi.org/10.1016/j.eneco.2024.108094
    
- Li, T., Yu, L., Ma, Y., Duan, T., Huang, W., Zhou, Y., … Jiang, T. (2023). Carbon emissions of 5G mobile networks in China. _Nature Sustainability, 6_(12), 1620–1631. https://doi.org/10.1038/s41893-023-01206-5
    
- Li, X., Li, S., Cao, J., & Spulbar, A. C. (2025). Does artificial intelligence improve energy efficiency? _Energy Economics, 142_, 108149. https://doi.org/10.1016/j.eneco.2024.108149
    
- Wang, K.-H., Jiang, X.-Y., & Tang, Y. (2025). Artificial intelligence, cloud computing, blockchain, and the energy market in the era of energy transition. _Energy Economics, 151_, 108975. https://doi.org/10.1016/j.eneco.2025.108975
    
- Yang, S., Zhu, M. N., & Yu, H. (2024). Are artificial intelligence and blockchain the key to unlocking the box of clean energy? _Energy Economics, 134_, 107616. https://doi.org/10.1016/j.eneco.2024.107616
    
- Yousaf, I., Ohikhuare, O. M., Li, Y., & Li, Y. (2024). Interconnectedness between electricity and artificial intelligence-based markets during the crisis periods: Evidence from the TVP-VAR approach. _Energy Economics, 139_, 107885. https://doi.org/10.1016/j.eneco.2024.107885
    
- Zhao, Q., Wang, L., Stan, S.-E., & Mirza, N. (2024). Can artificial intelligence help accelerate the transition to renewable energy? _Energy Economics, 134_, 107584. https://doi.org/10.1016/j.eneco.2024.107584
    
- Zhong, C., Cai, H., Fang, S., Xue, R., & Shan, Y. (2025). Does artificial intelligence reduce energy intensity in manufacturing? _Energy Economics, 149_, 108784. https://doi.org/10.1016/j.eneco.2025.108784
    
- Zhang, W., & Wen, H. (2025). Does artificial intelligence help ensure energy security? _Clean Technologies and Environmental Policy, 27_(10), 5381–5399. https://doi.org/10.1007/s10098-025-03172-2
    

```
---

### 小贴士（怎么用这条 Evergreen）
- 后续每读一篇新论文，只需往“Atomic Claims”和“Evidence Patterns”各补 1–2 条要点，并把文献追加到 References（APA）。
- 你的 returns_long/TVP-VAR 图形管线，直接复用上面 TODO 的出图范式；需要我把 QQR 与 TVP-VAR（含 1–21/21-Inf 分频网络）配套 R 代码与模板图一起打包，我也可以马上给你。
```

---
# ✍️ Summary
-　


- ## ref
	- 📒：
	- link：
- ## Logs
	- [[2025-11-07]]
- ## todo
	- [ ] 
---
# 📒 Note




- ## 人工智能驱动的预测：提升供应链可持续性 | 运筹学年鉴 --- Artificial intelligence powered predictions: enhancing supply chain sustainability | Annals of Operations Research
    
    |   |   |
    |---|---|
    |条目类型|网页|
    |网址|[https://link.springer.com/article/10.1007/s10479-024-06088-0](https://link.springer.com/article/10.1007/s10479-024-06088-0)|
    |访问时间|2025/11/7 15:48:23|
    |添加日期|2025/11/7 15:48:23|
    |修改日期|2025/11/7 15:48:23|
    
- ## A win-win relationship? New evidence on artificial intelligence and new energy vehicles
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Jianqiang Gu|
    |作者|Zhan Wu|
    |作者|Yubing Song|
    |作者|Ana-Cristina Nicolescu|
    |摘要|Investigating the vital role of artificial intelligence is essential to develop the electric vehicle market. This study utilises the wavelet-based QQR methodology to seize the dynamic correlation of artificial intelligence index (AII) and electric vehicle indicator (EVI). Based on quantitative deliberations, the favourable effects of AII on EVI at low-low and high-high quantiles and adverse impacts at high-low and low-high quantiles in the short run confirm the role of artificial intelligence in facilitating the electric vehicle market. However, the favourable effect of AII at medium to high quantiles on EVI at low quantiles refutes it because of the crowding-out effect. Conversely, the positive impact of EVI at medium to high quantiles on AII at low to medium quantiles ascertains the crowding-out effect of electric vehicles, while AII at medium to high quantiles cannot agree on it due to safety and convenience needs. In the mid-to-long term, the interactions of AII and EVI are gradually weakened, and speculative behaviours, crowding-out effects, and safety concerns drive the different cases. Therefore, a win-win situation between them does not always hold, and recommendations are being offered to enhance the significance of artificial intelligence in electric vehicles under the new round of scientific and technological revolution.|
    |日期|2024-06-01|
    |短标题|A win-win relationship?|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S0140988324003219](https://www.sciencedirect.com/science/article/pii/S0140988324003219)|
    |访问时间|2025/11/6 21:11:32|
    |卷次|134|
    |页码|107613|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2024.107613](http://doi.org/10.1016/j.eneco.2024.107613)|
    |刊名简称|Energy Economics|
    |ISSN|0140-9883|
    |添加日期|2025/11/6 21:11:32|
    |修改日期|2025/11/6 21:11:32|
    
    ### 标签：
    
    - Artificial intelligence
    - Dynamic
    - Electric vehicles
    - Win-win relationship
    
    ### 附件
    
    - ScienceDirect Full Text PDF
    - ScienceDirect Snapshot
- ## An inquiry into the nexus between artificial intelligence and energy poverty in the light of global evidence
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Tao Ding|
    |摘要|Energy poverty is a global challenge that constrains economic development, jeopardizes people's health, and impedes the improvement of people's lives. Artificial intelligence (AI) could be an important tool to reverse this dilemma. We utilize a panel data covering 64 countries during 2000–2019 to examine AI's impact on energy poverty. The findings reveal that the application of AI effectively alleviates energy poverty. After a series of robustness checks, this conclusion remains valid. Moreover, heterogeneity tests show that AI significantly alle­ viates energy poverty in high-income countries and lower-middle-income countries, but this positive influence is not found in upper-middle-income countries. Mechanism tests indicate that the application of AI can generate economic effects, driving technological progress and enhancing human capital, thereby easing energy poverty. Further discussion reveals AI's impact on energy poverty is long-lasting. In addition, its effects are more prom­ inent in countries that do not participate in cooperative organizations. Our findings offer a fresh perspective and approach to improving the global state of energy poverty. Based on these conclusions, we provide relevant policy implications.|
    |日期|2024|
    |语言|en|
    |文库编目|Zotero|
    |刊名|Energy Economics|
    |添加日期|2024/12/17 18:58:49|
    |修改日期|2025/6/13 11:16:59|
    
    ### 附件
    
    - Ding - 2024 - An inquiry into the nexus between artificial intel.pdf
- ## Are artificial intelligence and blockchain the key to unlocking the box of clean energy?
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Shengyao Yang|
    |作者|Meng Nan Zhu|
    |作者|Haiyan Yu|
    |摘要|The fourth industrial revolution has brought about key technological breakthroughs represented by artificial intelligence (AI) and blockchain (BC), which provide an opportunity for the development of clean energy (CE). We employ a wavelet-based quantile-on-quantile approach to investigate the correlation among AI, BC and CE over different periods and time horizons. The results show that although the integration of AI and CE systems requires a lot of time, it can significantly boost CE development in the long run. However, BC cannot significantly promote CE development except for a few extreme periods. Our results are supported by the mechanism of interaction among AI, BC and CE development, which highlights their relationship. Therefore, the government should focus on promoting the development of new information technologies and their integration with the CE system, which is crucial for the implementation of energy transition strategies. In addition, low-carbon investors should focus on these technologies because of their relationship with CE.|
    |日期|06/2024|
    |语言|en|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S0140988324003244](https://linkinghub.elsevier.com/retrieve/pii/S0140988324003244)|
    |访问时间|2024/12/24 20:55:21|
    |卷次|134|
    |页码|107616|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2024.107616](http://doi.org/10.1016/j.eneco.2024.107616)|
    |刊名简称|Energy Economics|
    |ISSN|01409883|
    |添加日期|2024/12/24 20:55:21|
    |修改日期|2025/6/13 11:16:27|
    
    ### 附件
    
    - Yang 等 - 2024 - Are artificial intelligence and blockchain the key.pdf
- ## Artificial Intelligence and Energy Market Quartile Spillovers: Implications for China's Renewable Energy and High Emission Sectors
    
    |   |   |
    |---|---|
    |条目类型|预印本|
    |作者|Zhengyu Ren|
    |作者|Yujie Chen|
    |作者|Shijie Ma|
    |作者|Tao Shen|
    |摘要|The global transition to a low-carbon economy has accelerated the integration of artificial intelligence (AI) technologies, with digitalization and AI-driven intelligence reshaping industrial and energy markets. This study employs a quantile time-frequency spillover index model, using data from March 27, 2018, to August 7, 2024, to examine the dynamic risk spillover effects among AI technologies, high-emission industries, and renewable and traditional energy markets in China. The findings reveal that systemic risk spillovers exhibit time-varying asymmetries, with heightened sensitivity to extreme market conditions, particularly during upward market surges. Short-term spillovers dominate under extreme volatility, while long-term spillovers are more significant in normal market conditions. Notably, the renewable energy sector demonstrates strong market independence and stability under normal or downward volatility conditions, but its dominance is significantly weakened by extreme events, with the coking coal market emerging as a primary risk driver. Furthermore, the non-ferrous metals and renewable energy sectors act as consistent net risk exporters across varying market conditions. These insights highlight the need for robust risk management frameworks to mitigate systemic risks, promote the green transformation of high-emission industries, and optimize the integration of AI technologies into renewable energy systems to achieve carbon neutrality.|
    |日期|2025-02-24|
    |语言|en|
    |短标题|Artificial Intelligence and Energy Market Quartile Spillovers|
    |文库编目|papers.ssrn.com|
    |网址|[https://papers.ssrn.com/abstract=5151621](https://papers.ssrn.com/abstract=5151621)|
    |访问时间|2025/7/14 18:48:22|
    |地点|Rochester, NY|
    |DOI|[10.2139/ssrn.5151621](http://doi.org/10.2139/ssrn.5151621)|
    |仓库|Social Science Research Network|
    |流派|SSRN Scholarly Paper|
    |存档ID|5151621|
    |添加日期|2025/7/14 18:48:22|
    |修改日期|2025/7/14 18:48:22|
    
    ### 标签：
    
    - Artificial intelligence
    - Energy Markets
    - High Emission Industries
    - Quartile Spillover
    - Time-Frequency Spillover
    
    ### 附件
    
    - Ren et al_2025_Artificial Intelligence and Energy Market Quartile Spillovers.pdf
- ## Artificial intelligence and green development well-being: Effects and mechanisms in China
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Lanbing Li|
    |作者|Jiawei Zhao|
    |作者|Yuhan Yang|
    |作者|Dan Ma|
    |摘要|In a green and low-carbon context, green development well-being (GDW) encapsulates a city’s capacity to convert natural consumption into well-being, and artificial intelligence technology (AIT) potentially serves as a catalyst for advancing GDW. Employing panel data from 282 cities in China spanning 2006–2021, this research develops a composite indicator to measure GDW at the municipal level and adopts a two-way fixed effects (TWFE) approach to investigate AIT’s direct impacts on GDW and their underlying mechanisms. The empirical results reveal that AIT fosters GDW and contributes to GDW by enhancing green total factor productivity (GTFP), refining human capital structure and fostering entrepreneurial activity (EA). The effects of AIT on GDW further manifest heterogeneously, characterized by disparities in environmental regulation and regional contexts. Particularly, AIT’s full impact on GDW remains unrealized in the central and northeast regions. Moreover, AI enterprises are pivotal agents in AIT advancement, playing a critical role in augmenting GDW. This research substantiates the positive influences of AIT on GDW and proposes a novel avenue for elevating GDW standards. Policies should target AIT’s integration within the energy sector to optimize resource allocation, bolster energy efficiency, enforce stringent environmental regulations to incentivize AIT utilization for achieving heightened GDW levels, and foster collaboration between AI enterprises and public institutions in order to expedite AI-driven green development.|
    |日期|01/2025|
    |语言|en|
    |短标题|Artificial intelligence and green development well-being|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S014098832400803X](https://linkinghub.elsevier.com/retrieve/pii/S014098832400803X)|
    |访问时间|2024/12/24 20:55:52|
    |卷次|141|
    |页码|108094|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2024.108094](http://doi.org/10.1016/j.eneco.2024.108094)|
    |刊名简称|Energy Economics|
    |ISSN|01409883|
    |添加日期|2024/12/24 20:55:52|
    |修改日期|2025/6/13 11:16:41|
    
    ### 附件
    
    - Li 等 - 2025 - Artificial intelligence and green development well.pdf
- ## Artificial intelligence driven demand forecasting: an application to the electricity market
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Marco Repetto|
    |作者|Cinzia Colapinto|
    |作者|Muhammad Usman Tariq|
    |摘要|Demand forecasting with maximum accuracy is critical to business management in various ﬁelds, from ﬁnance to marketing. In today’s world, many ﬁrms have access to a lot of data that they can use to implement sophisticated models. This was not possible in the past, but it has become a reality with the advent of large-scale data analysis. However, this also requires a distributed thinking approach due to the resource-intensive nature of Deep Learning models. Forecasting power demand is of utmost importance in the energy industry, and various methods and approaches have been employed by electrical companies for predicting electricity demand. This paper proposes a novel multicriteria approach for distributed learning in energy forecasting. We use a Quadratic Goal Programming approach to construct a robust decision rule ensemble that optimizes a pre-deﬁned loss function. Our approach is independent of the loss function’s differentiability and is also model agnostic. This formulation offers interpretability for the decision-maker and demonstrates less proclivity of regression against the mean that affects autoregressive models. Our ﬁndings contribute to the ﬁeld of energy forecasting and highlight the potential of our approach for enhancing decision-making in the energy industry.|
    |日期|03/2025|
    |语言|en|
    |短标题|Artificial intelligence driven demand forecasting|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://link.springer.com/10.1007/s10479-024-05965-y](https://link.springer.com/10.1007/s10479-024-05965-y)|
    |访问时间|2025/11/7 15:50:20|
    |卷次|346|
    |页码|1637-1651|
    |刊名|Annals of Operations Research|
    |DOI|[10.1007/s10479-024-05965-y](http://doi.org/10.1007/s10479-024-05965-y)|
    |期号|2|
    |刊名简称|Ann Oper Res|
    |ISSN|0254-5330, 1572-9338|
    |添加日期|2025/11/7 15:50:20|
    |修改日期|2025/11/7 15:50:20|
    
    ### 附件
    
    - PDF
- ## Artificial intelligence powered predictions: enhancing supply chain sustainability
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Reza Farzipoor Saen|
    |作者|Farzaneh Yousefi|
    |作者|Majid Azadi|
    |日期|2024-06-15|
    |语言|en|
    |短标题|Artificial intelligence powered predictions|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://link.springer.com/10.1007/s10479-024-06088-0](https://link.springer.com/10.1007/s10479-024-06088-0)|
    |访问时间|2025/11/7 15:50:22|
    |刊名|Annals of Operations Research|
    |DOI|[10.1007/s10479-024-06088-0](http://doi.org/10.1007/s10479-024-06088-0)|
    |刊名简称|Ann Oper Res|
    |ISSN|0254-5330, 1572-9338|
    |添加日期|2025/11/7 15:50:22|
    |修改日期|2025/11/7 15:50:22|
    
    ### 附件
    
    - PDF
- ## Artificial intelligence-driven transformations in low-carbon energy structure: Evidence from China
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Weiliang Tao|
    |作者|Shimei Weng|
    |作者|Xueli Chen|
    |作者|Fawaz Baddar ALHussan|
    |作者|Malin Song|
    |摘要|The widespread integration of artificial intelligence (AI) technology in the realms of energy and the environment has emerged as a catalyst for transformative shifts toward low-carbon energy structures. However, existing literature and practical applications have yet to delve into the intricate ways in which intelligent technology influences energy structures. Consequently, this study addresses this gap by constructing a comprehensive theoretical model that encompasses robots and differentiated energy inputs. By drawing on the Chinese case, this research investigates the impact of AI on low-carbon energy structure transformation, both theoretically and empirically. The study's results reveal that AI technology significantly advances the cause of low-carbon energy transformation. Notably, this effect is manifested in the post-Industry 4.0 era and regions endowed with abun­ dant renewable energy resources and strong governmental support for innovation. Rigorous robustness tests substantiate the existence of this relationship. Furthermore, adopting smart technology fosters energy structure transformation through industrial restructuring, and introduces the energy rebound effect, thereby partially offsetting its positive impact. Importantly, the study underscores that the efficacy of AI is further heightened when the influx of innovation factors surpasses a certain threshold. These findings furnish crucial evidence and policy insights for China and other developing nations, offering guidance on accelerating energy transitions and attaining carbon neutrality.|
    |日期|08/2024|
    |语言|en|
    |短标题|Artificial intelligence-driven transformations in low-carbon energy structure|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S0140988324004274](https://linkinghub.elsevier.com/retrieve/pii/S0140988324004274)|
    |访问时间|2024/12/24 20:55:14|
    |卷次|136|
    |页码|107719|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2024.107719](http://doi.org/10.1016/j.eneco.2024.107719)|
    |刊名简称|Energy Economics|
    |ISSN|01409883|
    |添加日期|2024/12/24 20:55:14|
    |修改日期|2025/6/13 11:16:30|
    
    ### 附件
    
    - Tao 等 - 2024 - Artificial intelligence-driven transformations in .pdf
- ## Artificial intelligence, cloud computing, blockchain, and the energy market in the era of energy transition
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Kai-Hua Wang|
    |作者|Xin-Yu Jiang|
    |作者|Yun Tang|
    |摘要|This study explores the spillover effects between artificial intelligence (AI), cloud computing (CC), blockchain (BC), and eight traditional and renewable energies using cross-quantilogram and quantile time–frequency connectedness approaches. The findings reveal a distinct inverse relationship between the lowest energy return quantile and the highest digital technology quantile. We also find that spillovers change over time, frequency, and quantile levels with hydrogen energy remaining a primary risk transmitter and crude oil as a receiver. Additionally, while digital technologies may impose short-term negative shocks on the energy market, their influence on hedging risks and stabilization is more prominent in comparison. Furthermore, the dependence between AI, CC, BC, and energy indices was insignificant before the COVID-19 pandemic but increased significantly afterward. This analysis is based on high-frequency data from Wind. This study extends the literature by constructing a comprehensive spillover network integrating digital technologies and energy markets. In addition, we conduct a dynamic analysis of asymmetric spillovers across short- and long-term time horizons, while also emphasizing the hedging and stabilizing functions of digital technology within energy markets. Our findings provide actionable insights for promoting digital transformation and strengthening international cooperation.|
    |日期|2025-11-01|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S0140988325008059](https://www.sciencedirect.com/science/article/pii/S0140988325008059)|
    |访问时间|2025/11/6 21:04:09|
    |卷次|151|
    |页码|108975|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2025.108975](http://doi.org/10.1016/j.eneco.2025.108975)|
    |刊名简称|Energy Economics|
    |ISSN|0140-9883|
    |添加日期|2025/11/6 21:04:09|
    |修改日期|2025/11/6 21:04:09|
    
    ### 标签：
    
    - Cross-quantilogram
    - Digital technology
    - Energy market
    - Quantile time–frequency spillover
    
    ### 附件
    
    - ScienceDirect Full Text PDF
    - ScienceDirect Snapshot
- ## Artificial intelligence, digital inclusive finance, and financial performance: Dynamic threshold insights from renewable energy enterprises
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Wenwen Zhang|
    |作者|Shuai Fu|
    |作者|Yi-Bin Chiu|
    |作者|Cody Yu-Ling Hsiao|
    |摘要|With the widespread application of artificial intelligence (AI), industrial robots—being a typical example of AI technology—have provided new tools and opportunities for renewable energy enterprises. This paper uses data from 151 renewable energy enterprises and a dynamic panel threshold model to investigate the nonlinear effect of AI on financial performance of renewable energy enterprises and how this effect evolves with varying levels of digital inclusive finance. This paper finds that industrial robot installation exerts a U-shaped influence on renewable energy enterprises' financial performance, and industrial robot stock has a decreasing positive effect. Furthermore, industrial robots' influence on the financial performance of renewable energy enterprises varies by ownership type and scale. Additionally, at a high level of AI development, a high degree of digital inclusive finance amplifies the beneficial influence of industrial robot installation on the performance of renewable energy enterprises, while weakens the positive impact of industrial robot stock.|
    |日期|2025-08-01|
    |短标题|Artificial intelligence, digital inclusive finance, and financial performance|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S0140988325005146](https://www.sciencedirect.com/science/article/pii/S0140988325005146)|
    |访问时间|2025/11/6 21:08:15|
    |卷次|148|
    |页码|108687|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2025.108687](http://doi.org/10.1016/j.eneco.2025.108687)|
    |刊名简称|Energy Economics|
    |ISSN|0140-9883|
    |添加日期|2025/11/6 21:08:15|
    |修改日期|2025/11/6 21:08:15|
    
    ### 标签：
    
    - Artificial intelligence
    - Digital inclusive finance
    - Financial performance
    - Renewable energy
    
    ### 附件
    
    - ScienceDirect Full Text PDF
    - ScienceDirect Snapshot
- ## Bridge the gap: nexus between artificial intelligence and urban energy resilience, evidence from low-carbon city in China
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Chang-song Wang|
    |作者|Wei Chen|
    |作者|Yang Zheng|
    |作者|Qin Dai|
    |摘要|The development of low-carbon cities is essential for achieving sustainable, high-quality growth and plays a crucial role in ensuring the reliability and stability of energy production and distribution networks. This study employs a PSM-DID model, a dual machine learning model, and a spatial Durbin model to empirically analyze the impact, underlying mechanisms, and spatial effects of low-carbon city pilot on energy resilience. The benchmark regression results show that the low-carbon city pilot has significantly enhanced urban energy resilience, but it shows heterogeneous results in different types of cities. The low-carbon city pilot in large cities (population greater than 1 million) and net inflow cities can greatly enhance urban energy resilience, while the construction of low-carbon cities in small cities (population fewer than 1 million) and net outflow cities has a negative impact on urban energy resilience. The mechanistic analysis demonstrates that the application of artificial intelligence is the primary channel through which low-carbon city pilot drives improvements in urban energy resilience, but the effect shows a non-linear growth. When the application level of artificial intelligence exceeds 4.2909, the effect of low-carbon city pilot on urban energy resilience will be enhanced. In addition, spatial analysis shows that low-carbon city pilot strengthens energy resilience in pilot cities and has a spillover effect on surrounding cities. The series of methods proposed in this paper not only tests the causal relationship between low-carbon city pilot and urban energy resilience but also provides new experience and evidence for improving the resilience of urban energy systems.|
    |日期|2025-12-01|
    |短标题|Bridge the gap|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S0140988325008357](https://www.sciencedirect.com/science/article/pii/S0140988325008357)|
    |访问时间|2025/11/6 21:01:05|
    |卷次|152|
    |页码|109005|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2025.109005](http://doi.org/10.1016/j.eneco.2025.109005)|
    |刊名简称|Energy Economics|
    |ISSN|0140-9883|
    |添加日期|2025/11/6 21:01:05|
    |修改日期|2025/11/6 21:01:05|
    
    ### 标签：
    
    - Artificial intelligence
    - Dual machine learning
    - Low-Carbon City pilot
    - Urban energy resilience
    
    ### 附件
    
    - ScienceDirect Full Text PDF
    - ScienceDirect Snapshot
- ## Can artificial intelligence curb greenwashing? Firm-level evidence based on large language model
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Ling-Yun He|
    |作者|Liang Wang|
    |摘要|Amid growing scrutiny of corporate environmental disclosures, concerns have intensified regarding the prevalence of greenwashing. Although the rapid advancement of artificial intelligence (AI) has drawn increasing attention for its transformative potential in corporate governance, its implications for environmental disclosure have only begun to receive scholarly attention and warrant further investigation. This paper investigates the impact of artificial intelligence adoption on corporate greenwashing using a panel dataset of Chinese A-share listed firms from 2011 to 2022. Leveraging a novel AI adoption index derived from a fine-tuned large language model (LLM), we conduct empirical tests to assess the relationship between AI use and firms’ greenwashing strategies. Our findings reveal that AI adoption significantly reduces the incidence of greenwashing, which remains robust across multiple validation checks. Decomposition analysis across different technological categories shows that planning and decision systems constitute the most influential strand of AI in curbing greenwashing. Mechanism analysis indicates that this effect operates through enhanced operational efficiency, improved human capital structure, and increased green innovation. Additional heterogeneity analysis across subsamples reveals that the deterrent impact exhibits greater intensity in firms characterized by non-state-owned firms, polluting sectors, and technology-intensive enterprises. By highlighting the governance potential of AI in promoting credible environmental disclosure, this study provides new empirical evidence on the intersection of digital transformation and corporate sustainability.|
    |日期|2025-12-01|
    |语言|en|
    |短标题|Can artificial intelligence curb greenwashing?|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S0140988325007819](https://www.sciencedirect.com/science/article/pii/S0140988325007819)|
    |访问时间|2025/11/6 20:58:28|
    |卷次|152|
    |页码|108954|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2025.108954](http://doi.org/10.1016/j.eneco.2025.108954)|
    |刊名简称|Energy Economics|
    |ISSN|0140-9883|
    |添加日期|2025/11/6 20:58:28|
    |修改日期|2025/11/6 20:59:03|
    
    ### 标签：
    
    - AI classification
    - Artificial intelligence
    - Greenwashing
    - Heterogeneous firm
    - Large language model
    
    ### 附件
    
    - ScienceDirect Full Text PDF
    - ScienceDirect Snapshot
- ## Can artificial intelligence empower energy enterprises to cope with climate policy uncertainty?
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Qian Zhong|
    |作者|Qun Zhang|
    |作者|Jingjing Yang|
    |摘要|This study investigates the effect of climate policy uncertainty (CPU) on firm-level investment and through which artificial intelligence (AI) may act upon this relationship. Using panel data from listed energy enterprises in China from 2010 to 2019, we demonstrate that CPU significantly inhibits energy enterprises’ investments, mainly by exacerbating their financing constraints. This effect is more pronounced in firms with strong environmental awareness, strong internal control, high environmental, social, and governance scores, or in the traditional energy industry. Furthermore, we find that AI adoption weakens the impact of CPU on firm-level investments, primarily through two potential mechanisms: mitigating the customer concentration risk and enhancing green patent commercialization. On average, a 1 % increase in the degree of AI adoption by energy firms can boost their investment expenditure by 0.0065 %. Furthermore, AI’s role in mitigating the negative impact of CPU on energy firms’ investments is more significant in non-resource-based cities, cities with high economic growth rates, and cities with advanced IT infrastructure. Our findings provide a deeper understanding of the forces driving sustainable energy transitions in the evolving climate policy landscape.|
    |日期|01/2025|
    |语言|en|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S0140988324007977](https://linkinghub.elsevier.com/retrieve/pii/S0140988324007977)|
    |访问时间|2025/6/13 11:05:28|
    |卷次|141|
    |页码|108088|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2024.108088](http://doi.org/10.1016/j.eneco.2024.108088)|
    |刊名简称|Energy Economics|
    |ISSN|01409883|
    |添加日期|2025/6/13 11:05:28|
    |修改日期|2025/6/13 11:16:53|
    
    ### 附件
    
    - Zhong 等 - 2025 - Can artificial intelligence empower energy enterpr.pdf
- ## Can artificial intelligence help accelerate the transition to renewable energy?
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Qian Zhao|
    |作者|Lu Wang|
    |作者|Sebastian-Emanuel Stan|
    |作者|Nawazish Mirza|
    |摘要|Artificial intelligence (AI) has enormous potential in improving the efficiency and reducing the cost of energy systems; however, it is unclear whether it can help accelerate the transition from traditional fossil energy to renewable energy (RE). Previous studies have primarily focused on the applications of AI in the energy sector from a technical perspective; in contrast, this paper identifies the process and mechanism of AI's impact on the energy transition, using the wavelet-based quantile-on-quantile approach to estimate the impact of various AI quantiles on energy structure quantiles in different periods. Using data from China, the paper finds that the upper quantiles of AI increase the share of RE in total energy in the long term, demonstrating that AI can, by unlocking its vast potential, accelerate the transition to RE. However, in the short and medium terms, AI negatively impacts RE share, primarily due to considerable challenges in integrating AI into the RE sector. Moreover, the non-RE sector may temporarily benefit more from AI than the RE sector. These findings provide crucial insights for policymakers in coordinating AI's short- and long-term effects on the energy transition to effectively harness RE's potential and achieve the goal of a low-carbon economy.|
    |日期|2024-06-01|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S0140988324002925](https://www.sciencedirect.com/science/article/pii/S0140988324002925)|
    |访问时间|2025/11/6 21:12:39|
    |卷次|134|
    |页码|107584|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2024.107584](http://doi.org/10.1016/j.eneco.2024.107584)|
    |刊名简称|Energy Economics|
    |ISSN|0140-9883|
    |添加日期|2025/11/6 21:12:39|
    |修改日期|2025/11/6 21:12:39|
    
    ### 标签：
    
    - Artificial intelligence
    - Energy transition
    - Quantile-on-quantile
    - Renewable energy
    - Wavelet
    
    ### 附件
    
    - ScienceDirect Full Text PDF
    - ScienceDirect Snapshot
- ## Carbon emissions of 5G mobile networks in China
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Tong Li|
    |作者|Li Yu|
    |作者|Yibo Ma|
    |作者|Tong Duan|
    |作者|Wenzhen Huang|
    |作者|Yan Zhou|
    |作者|Depeng Jin|
    |作者|Yong Li|
    |作者|Tao Jiang|
    |日期|2023-08-17|
    |语言|en|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://www.nature.com/articles/s41893-023-01206-5](https://www.nature.com/articles/s41893-023-01206-5)|
    |访问时间|2025/11/7 15:50:44|
    |卷次|6|
    |页码|1620-1631|
    |刊名|Nature Sustainability|
    |DOI|[10.1038/s41893-023-01206-5](http://doi.org/10.1038/s41893-023-01206-5)|
    |期号|12|
    |刊名简称|Nat Sustain|
    |ISSN|2398-9629|
    |添加日期|2025/11/7 15:50:44|
    |修改日期|2025/11/7 15:50:44|
    
    ### 附件
    
    - PDF
- ## ChatGPT 与商品回报 - 高 - 2025 - 期货市场杂志 - 威利在线图书馆 --- ChatGPT and Commodity Return - Gao - 2025 - Journal of Futures Markets - Wiley Online Library
    
    |   |   |
    |---|---|
    |条目类型|网页|
    |网址|[https://onlinelibrary.wiley.com/doi/10.1002/fut.22568](https://onlinelibrary.wiley.com/doi/10.1002/fut.22568)|
    |访问时间|2025/11/7 15:43:12|
    |添加日期|2025/11/7 15:43:12|
    |修改日期|2025/11/7 15:43:12|
    
- ## ChatGPT and Commodity Return
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Shen Gao|
    |作者|Shijie Wang|
    |作者|Yuanzhi Wang|
    |作者|Qunzi Zhang|
    |摘要|This paper investigates the ability of a ChatGPT-based indicator to forecast excess returns of the commodity futures index. Using ChatGPT to extract information from over 2.5 million articles from nine international newspapers, we demonstrate that our constructed commodity news ratio index significantly predicts future commodity returns, both in-sample and out-of-sample. Furthermore, it outperforms traditional textual analysis methods, including Bidirectional Encoder Representations from Transformers (BERT) and Bag-of-Words (BoW), while indicating economic significance within an asset allocation framework. The results highlight the critical role of ChatGPT in forecasting commodity market dynamics and provide valuable insights for both financial market participants and researchers.|
    |日期|2025|
    |语言|en|
    |文库编目|Wiley Online Library|
    |网址|[https://onlinelibrary.wiley.com/doi/abs/10.1002/fut.22568](https://onlinelibrary.wiley.com/doi/abs/10.1002/fut.22568)|
    |访问时间|2025/11/7 15:47:44|
    |其他|_eprint: https://onlinelibrary.wiley.com/doi/pdf/10.1002/fut.22568|
    |卷次|45|
    |页码|161-175|
    |刊名|Journal of Futures Markets|
    |DOI|[10.1002/fut.22568](http://doi.org/10.1002/fut.22568)|
    |期号|3|
    |ISSN|1096-9934|
    |添加日期|2025/11/7 15:47:45|
    |修改日期|2025/11/7 15:47:45|
    
    ### 标签：
    
    - ChatGPT
    - commodity return analysis
    - textual analysis
    
    ### 附件
    
    - Full Text PDF
    - Snapshot
- ## Cross-quantile risk assessment: The interplay of crude oil, artificial intelligence, clean tech, and other markets
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Mariya Gubareva|
    |作者|Muhammad Shafiullah|
    |作者|Tamara Teplova|
    |摘要|This paper explores the interconnections among oil, artificial intelligence (AI), clean technology, and traditional markets. We apply a novel generalized quantile-on-quantile connectedness method that assesses variable crossquantile interdependencies, analyzing data from 2018 to 2023. Our study provides a detailed examination of risk transmission dynamics between oil, AI, clean technology, and major markets including equity, debt, and cur­ rency. Our findings indicate that tail risk spillovers are more pronounced than median quantiles. In contrast, the analysis shows negative spillovers across these tails in markets for U.S. government debt, the U.S. dollar, and gold. The dynamic risk transmission analysis reveals that while the stock and AI markets generally act as net transmitters of risk across all quantiles, the crude oil and USD index markets consistently receive net risk spillovers, particularly in the right tail of the distribution. Our results suggest that, on average, AI, and clean technology markets, along with the stock markets, are more likely to transfer risk spillovers compared to debt, currency, or other commodity markets. This positions the USD and crude oil as potential buffers against extreme risk transmissions emanating from the AI and clean technology sectors. This study highlights the complex risk dynamics and the pivotal role of oil in the interplay between emerging technologies and traditional financial markets.|
    |日期|01/2025|
    |语言|en|
    |短标题|Cross-quantile risk assessment|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S0140988324007941](https://linkinghub.elsevier.com/retrieve/pii/S0140988324007941)|
    |访问时间|2024/12/24 20:54:55|
    |卷次|141|
    |页码|108085|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2024.108085](http://doi.org/10.1016/j.eneco.2024.108085)|
    |刊名简称|Energy Economics|
    |ISSN|01409883|
    |添加日期|2024/12/24 20:54:55|
    |修改日期|2025/6/13 11:16:46|
    
    ### 附件
    
    - Gubareva 等 - 2025 - Cross-quantile risk assessment The interplay of c.pdf
- ## Cross-quantile risk assessment: The interplay of crude oil, artificial intelligence, clean tech, and other markets
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Mariya Gubareva|
    |作者|Muhammad Shafiullah|
    |作者|Tamara Teplova|
    |摘要|This paper explores the interconnections among oil, artificial intelligence (AI), clean technology, and traditional markets. We apply a novel generalized quantile-on-quantile connectedness method that assesses variable cross-quantile interdependencies, analyzing data from 2018 to 2023. Our study provides a detailed examination of risk transmission dynamics between oil, AI, clean technology, and major markets including equity, debt, and currency. Our findings indicate that tail risk spillovers are more pronounced than median quantiles. In contrast, the analysis shows negative spillovers across these tails in markets for U.S. government debt, the U.S. dollar, and gold. The dynamic risk transmission analysis reveals that while the stock and AI markets generally act as net transmitters of risk across all quantiles, the crude oil and USD index markets consistently receive net risk spillovers, particularly in the right tail of the distribution. Our results suggest that, on average, AI, and clean technology markets, along with the stock markets, are more likely to transfer risk spillovers compared to debt, currency, or other commodity markets. This positions the USD and crude oil as potential buffers against extreme risk transmissions emanating from the AI and clean technology sectors. This study highlights the complex risk dynamics and the pivotal role of oil in the interplay between emerging technologies and traditional financial markets.|
    |日期|2025-01-01|
    |短标题|Cross-quantile risk assessment|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S0140988324007941](https://www.sciencedirect.com/science/article/pii/S0140988324007941)|
    |访问时间|2025/11/6 21:07:16|
    |卷次|141|
    |页码|108085|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2024.108085](http://doi.org/10.1016/j.eneco.2024.108085)|
    |刊名简称|Energy Economics|
    |ISSN|0140-9883|
    |添加日期|2025/11/6 21:07:16|
    |修改日期|2025/11/6 21:07:16|
    
    ### 标签：
    
    - Artificial intelligence (AI)
    - Clean technology
    - Directly related tails
    - Generalized quantile connectedness
    - Reversely related tails
    - Risk spillovers
    - Tail risk transmission
    
    ### 附件
    
    - ScienceDirect Full Text PDF
    - ScienceDirect Snapshot
- ## Digital brains, green gains: Artificial intelligence's path to sustainable transformation
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Miaomiao Tao|
    |摘要|The environmental impacts of artificial intelligence on a global scale remain underexplored. This study utilizes a balanced panel dataset to examine artificial intelligence’s complex role in enhancing global green productivity between 2008 and 2019. The findings indicate that artificial intelligence robustly boosts green productivity, even after correcting for potential endogeneity using the legal system’s origin as an instrument. A detailed mediation analysis underscores that artificial intelligence indirectly promotes green productivity by increasing renewable energy use, attracting skilled labor, and dampening stock market performance. Additional analysis confirms that financial development generally amplifies artificial intelligence’s favorable effects on green productivity. However, the combined impact of financial institution access and artificial intelligence on green productivity initially appears hostile, an effect that can be reversed when financial access exceeds a certain threshold. These results offer valuable insights into the interconnection between artificial intelligence and the global shift towards greener practices.|
    |日期|11/2024|
    |语言|en|
    |短标题|Digital brains, green gains|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S0301479724026653](https://linkinghub.elsevier.com/retrieve/pii/S0301479724026653)|
    |访问时间|2025/6/13 11:05:47|
    |卷次|370|
    |页码|122679|
    |刊名|Journal of Environmental Management|
    |DOI|[10.1016/j.jenvman.2024.122679](http://doi.org/10.1016/j.jenvman.2024.122679)|
    |刊名简称|Journal of Environmental Management|
    |ISSN|03014797|
    |添加日期|2025/6/13 11:05:47|
    |修改日期|2025/6/13 11:18:31|
    
    ### 附件
    
    - Tao - 2024 - Digital brains, green gains Artificial intelligen.pdf
- ## Digital inclusive finance, green technological innovation, and carbon emissions from a spatial perspective
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Yang Lu|
    |作者|Ziyi Xia|
    |摘要|Based on the panel data of 276 prefecture-level cities in China from 2011 to 2020, this study explores the impact of digital inclusive finance (DIF) on carbon emissions and the intrinsic mechanism of green technological innovation from a spatial perspective by constructing a spatial econometric model, a mediating effect model, and a threshold model. The results show that DIF significantly inhibits carbon emissions, exhibiting a spatial spillover effect. The transmission mechanism from a spatial perspective shows that green technological innovation plays a partial mediating role between DIF and carbon emissions, with the mediating effect accounting for approximately 59.47%. The heterogeneity analysis suggests that the impact of DIF on the reduction of carbon emissions is more pronounced in large and medium-sized cities and eastern regions. Further discussion reveals that the carbon reduction effect of DIF is also influenced by green technological innovation and industrial structure upgrading, showing threshold effects with marginal decreases and gradual increases, respectively.|
    |日期|2024-04-11|
    |语言|en|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://www.nature.com/articles/s41598-024-59081-9](https://www.nature.com/articles/s41598-024-59081-9)|
    |访问时间|2025/11/7 15:50:40|
    |卷次|14|
    |页码|8454|
    |刊名|Scientific Reports|
    |DOI|[10.1038/s41598-024-59081-9](http://doi.org/10.1038/s41598-024-59081-9)|
    |期号|1|
    |刊名简称|Sci Rep|
    |ISSN|2045-2322|
    |添加日期|2025/11/7 15:50:40|
    |修改日期|2025/11/7 15:50:40|
    
    ### 附件
    
    - PDF
- ## Do global COVOL and geopolitical risks affect clean energy prices? Evidence from explainable artificial intelligence models
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Sami Ben Jabeur|
    |作者|Yassine Bakkar|
    |作者|Oguzhan Cepni|
    |摘要|We investigate the impact of global common volatility and geopolitical risks on clean energy prices. Our study utilizes daily data from January 1, 2001, to March 18, 2024. Using a new framework based on explainable artificial intelligence (XAI) methods, our findings demonstrate that the COVOL index outperforms the geopo­ litical risk index in accurately predicting clean energy prices. Furthermore, the Extreme Trees algorithm shows superior performance compared to traditional regression techniques. Our findings indicate that XAI improves transparency, thereby making a substantial contribution to agile decision-making in predicting clean energy prices. Practitioners, including investors and portfolio managers, can enhance investment decisions and manage systemic risks by incorporating COVOL into their risk assessment and asset allocation models.|
    |日期|01/2025|
    |语言|en|
    |短标题|Do global COVOL and geopolitical risks affect clean energy prices?|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S0140988324008211](https://linkinghub.elsevier.com/retrieve/pii/S0140988324008211)|
    |访问时间|2025/6/13 11:05:31|
    |卷次|141|
    |页码|108112|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2024.108112](http://doi.org/10.1016/j.eneco.2024.108112)|
    |刊名简称|Energy Economics|
    |ISSN|01409883|
    |添加日期|2025/6/13 11:05:31|
    |修改日期|2025/6/13 11:14:49|
    
    ### 附件
    
    - Ben Jabeur 等 - 2025 - Do global COVOL and geopolitical risks affect clea.pdf
- ## Does artificial intelligence help ensure energy security? Evidence from China
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Wen Zhang|
    |作者|Huwei Wen|
    |摘要|The energy security revolution is pivotal to the sustainable development of the global economy, with artificial intelligence (AI) serving as a critical tool in driving the transformation of new energy systems. This study examines the relationship between AI and regional energy security (ES) via statistical data from 30 provinces in China, with the reliability of the findings confirmed through robustness tests. Empirical analysis reveals that AI enhances ES through two primary pathways: improving energy use efficiency and advancing energy development. Energy use efficiency is bolstered by highly skilled personnel and foreign direct investment, whereas energy development is driven by technological innovation and manufacturing agglomeration. Additionally, a nonlinear relationship between AI and ES is identified. Regional heterogeneity analysis further indicates that the positive impact of AI on ES is more pronounced in the eastern region and in areas with higher levels of openness and human capital. Policies for smart energy supply systems are recommended for development and implementation, and AI technologies are encouraged to be used to improve energy efficiency in production and electrify production.|
    |日期|10/2025|
    |语言|en|
    |短标题|Does artificial intelligence help ensure energy security?|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://link.springer.com/10.1007/s10098-025-03172-2](https://link.springer.com/10.1007/s10098-025-03172-2)|
    |访问时间|2025/11/7 15:50:16|
    |卷次|27|
    |页码|5381-5399|
    |刊名|Clean Technologies and Environmental Policy|
    |DOI|[10.1007/s10098-025-03172-2](http://doi.org/10.1007/s10098-025-03172-2)|
    |期号|10|
    |刊名简称|Clean Techn Environ Policy|
    |ISSN|1618-954X, 1618-9558|
    |添加日期|2025/11/7 15:50:16|
    |修改日期|2025/11/7 15:50:16|
    
    ### 附件
    
    - PDF
- ## Does artificial intelligence impact corporate ESG performance? Evidence from a quasi-natural experiment in China
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Yang Wang|
    |作者|Yongheng Wang|
    |作者|Pengyu Yang|
    |摘要|This study examines the impact of China's national-level New Generation Artificial Intelligence Innovation Development Pilot Zones (AIIDPZ) on corporate ESG performance. Using firm-level data from 2010 to 2022, we find that the establishment of AIIDPZs significantly enhances corporate ESG outcomes, and this effect remains robust across a series of validation tests. Mechanism analysis reveals that AIIDPZs foster ESG improvements primarily by promoting green innovation, strengthening managerial capabilities, and reducing both internal and external communication costs. Additional heterogeneity analysis shows that the positive effects are more pronounced for firms led by CEOs with financial or academic backgrounds and for those located in regions with more advanced infrastructure. This study suggests that expanding the coverage of AI innovation pilot zones, strategically deploying digital infrastructure, and improving digital regulatory systems can jointly establish a systemic policy pathway to foster sustainable development.|
    |日期|2025-11-01|
    |短标题|Does artificial intelligence impact corporate ESG performance?|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S014098832500790X](https://www.sciencedirect.com/science/article/pii/S014098832500790X)|
    |访问时间|2025/11/6 21:01:38|
    |卷次|151|
    |页码|108963|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2025.108963](http://doi.org/10.1016/j.eneco.2025.108963)|
    |刊名简称|Energy Economics|
    |ISSN|0140-9883|
    |添加日期|2025/11/6 21:01:38|
    |修改日期|2025/11/6 21:01:38|
    
    ### 标签：
    
    - Artificial intelligence
    - Corporate governance
    - ESG performance
    - Sustainable development
    
    ### 附件
    
    - ScienceDirect Full Text PDF
    - ScienceDirect Snapshot
- ## Does artificial intelligence improve energy efficiency? Evidence from provincial data in China
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Xin Li|
    |作者|Shiyuan Li|
    |作者|Jifeng Cao|
    |作者|Andrei Cristian Spulbar|
    |摘要|As global energy demand rises and environmental awareness increases, improving energy efficiency (EE) has become crucial to achieving sustainable development. This paper employs a two-way fixed effects panel model using data from 30 provinces in China, from 2000 to 2021, to investigate the impact of artificial intelligence (AI) on EE. The research results reveal that advancements in AI have greatly facilitated the improvement of EE. Furthermore, green technology innovation capability plays a positive moderating role between AI and EE. A heterogeneity analysis indicates that the impact of AI on EE is more significant in economically-developed regions. In energy-deficient regions, AI can significantly improve EE, whereas conversely, in energy-abundant regions, AI's impact on EE is negative. Further analysis using a spatial Durbin model (SDM) confirms the presence of spatial effects in the impact of AI on EE. This paper aims to expand the scholarly understanding of the relationship between AI and EE and provides empirical evidence for decision-makers during this critical period of energy transition. By delving into the potential of AI to enhance EE, the paper seeks to illuminate specific strategies and approaches for policymakers and industry participants.|
    |日期|02/2025|
    |语言|en|
    |短标题|Does artificial intelligence improve energy efficiency?|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S0140988324008582](https://linkinghub.elsevier.com/retrieve/pii/S0140988324008582)|
    |访问时间|2025/6/13 11:05:36|
    |卷次|142|
    |页码|108149|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2024.108149](http://doi.org/10.1016/j.eneco.2024.108149)|
    |刊名简称|Energy Economics|
    |ISSN|01409883|
    |添加日期|2025/6/13 11:05:37|
    |修改日期|2025/6/13 11:16:40|
    
    ### 附件
    
    - Li 等 - 2025 - Does artificial intelligence improve energy effici.pdf
- ## Does artificial intelligence promote energy transition and curb carbon emissions? The role of trade openness
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Qiang Wang|
    |摘要|A more comprehensive understanding of the impact of artificial intelligence (AI) on energy transition and carbon emissions could help to use AI to achieve carbon neutrality. To this end, the STIRPAT approach, the mediation effect technique and the panel threshold technique are developed using the panel data in 69 countries from 1993 to 2019. The results show that: (i) AI promote energy transition and carbon emission reduction, and trade openness (indicated by imports, exports and total trade volume) has the mediating effect. (ii) There is a singlethreshold of trade openness in the impact of AI on carbon emissions. When trade openness is below the threshold, AI has an insignificant impact on carbon emissions; when trade openness crosses the threshold, AI has a sig­ nificant negative impact on carbon emissions. There is a double-threshold of trade openness in the impact of AI on energy transition. When trade openness is lower than the first threshold, the impact of AI on energy transition is not significant; When trade openness is higher than the second threshold, the positive impact of AI on energy transition is increased. (iii) When considering the heterogeneity of income levels and AI levels, the trade threshold for achieving carbon emission reductions in the high-income group is lower than that of the global group, and the trade threshold for achieving carbon emission reductions in the low-AI level group is higher than that of the global group. While this study unequivocally delineates the affirmative role of artificial intelligence in carbon emission reduction and energy transformation, particularly in the context of trade openness, we concurrently acknowledge that this viewpoint is not devoid of contention. Amidst the rapid advancement of technology and the landscape of open trade, we discern the presence of counterarguments. The efficacy of artificial intelligence is susceptible to the influence of multifaceted factors. It is imperative to consider associated factors, such as the significant energy consumption required for storing and cooling data centers and servers. The study’s conclusions aid policymakers in devising nuanced emission reduction policies tailored to specific needs.|
    |日期|2024|
    |语言|en|
    |文库编目|Zotero|
    |刊名|Journal of Cleaner Production|
    |添加日期|2025/6/13 11:06:00|
    |修改日期|2025/6/13 11:14:44|
    
    ### 附件
    
    - Wang - 2024 - Does artificial intelligence promote energy transi.pdf
- ## Does artificial intelligence reduce corporate energy consumption? New evidence from China
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Yunyun Fu|
    |作者|Yongchang Shen|
    |作者|Malin Song|
    |作者|Weiyu Wang|
    |摘要|Artificial intelligence is playing a significant role in addressing the energy crisis. This study selected data from manufacturing companies listed on China’s A-share market from 2011 to 2022 and calculated the total energy consumption for the first time. The data include the usage of coal, natural gas, gasoline, diesel and water consumption, electricity usage, and centralized heating. The data were then matched and merged with robot usage data from the International Federation of Robotics to empirically study the impact and mechanism of artificial intelligence on energy consumption levels. Our findings reveal that energy consumption decreases by 0.20 % with a oneunit increase in artificial intelligence applications by a corporation, indicating artificial intelli­ gence can significantly reduce energy consumption. The mechanisms by which artificial intelli­ gence affects energy consumption include technological innovation and digital transformation. Additionally, a heterogeneity analysis revealed that applying artificial intelligence in state-owned enterprises, high-tech companies, and non-heavy-pollution industries can further reduce energy consumption. Our study also provides important practical implications for formulating and optimizing global energy policies to achieve sustainable development goals.|
    |日期|09/2024|
    |语言|en|
    |短标题|Does artificial intelligence reduce corporate energy consumption?|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S0313592624001723](https://linkinghub.elsevier.com/retrieve/pii/S0313592624001723)|
    |访问时间|2025/6/13 11:05:52|
    |卷次|83|
    |页码|548-561|
    |刊名|Economic Analysis and Policy|
    |DOI|[10.1016/j.eap.2024.07.005](http://doi.org/10.1016/j.eap.2024.07.005)|
    |刊名简称|Economic Analysis and Policy|
    |ISSN|03135926|
    |添加日期|2025/6/13 11:05:52|
    |修改日期|2025/6/13 11:16:06|
    
    ### 附件
    
    - Fu 等 - 2024 - Does artificial intelligence reduce corporate ener.pdf
- ## Does artificial intelligence reduce energy intensity in manufacturing? Evidence from country-level data
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Chao Zhong|
    |作者|Hongbo Cai|
    |作者|Shuai Fang|
    |作者|Rui Xue|
    |作者|Yuli Shan|
    |摘要|This paper examines the impact of artificial intelligence (AI) technology on the energy intensity of manufacturing industries using cross-country analysis. The findings reveal that AI adoption significantly reduces energy intensity in manufacturing, underscoring its potential for energy savings. To mitigate endogeneity concerns, the Bartik instrument variable method is used and the key findings are held. We further document substantial heterogeneity across economic contexts. Specifically, in high-income countries and developed economies, especially in G7 and European Union countries, AI application does not significantly reduce energy intensity. However, in middle-income countries and emerging economies, particularly in European emerging markets, AI adoption leads to a substantial decrease in energy intensity. Furthermore, we reveal that AI enhances energy efficiency through technological advancement and application dissemination. Based on these findings, we offer practical policy recommendations for promoting the sustainable development of the AI-energy intensity nexus in manufacturing.|
    |日期|2025-09-01|
    |短标题|Does artificial intelligence reduce energy intensity in manufacturing?|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S0140988325006115](https://www.sciencedirect.com/science/article/pii/S0140988325006115)|
    |访问时间|2025/11/6 21:03:46|
    |卷次|149|
    |页码|108784|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2025.108784](http://doi.org/10.1016/j.eneco.2025.108784)|
    |刊名简称|Energy Economics|
    |ISSN|0140-9883|
    |添加日期|2025/11/6 21:03:47|
    |修改日期|2025/11/6 21:03:47|
    
    ### 标签：
    
    - Artificial intelligence
    - Energy intensity
    - Manufacturing
    - R&D
    - Technology application
    
    ### 附件
    
    - ScienceDirect Full Text PDF
    - ScienceDirect Snapshot
- ## Dynamic connectedness of quantum computing, artificial intelligence, and big data stocks on renewable and sustainable energy
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Mahdi Ghaemi Asl|
    |作者|Sami Ben Jabeur|
    |作者|Hela Nammouri|
    |作者|Kamel Bel Hadj Miled|
    |摘要|This research aims to evaluate the accuracy of the long-term relationship between renewable and sustainable energy sectors and emerging technologies, including quantum computing, artificial intelligence (AI), and big data. Using a novel methodology that integrates the Time-Varying Parameter Vector Autoregressive (TVP-VAR) frequency connectedness approach with Long Short-Term Memory (LSTM) neural networks, the study examines the long-term interconnectedness, considering the dynamic nature of coefficients and covariance structures. The analysis spans from May 14, 2018, to September 6, 2023. It focuses on six critical clusters within the sustainable and renewable energy sectors: clean energy, green energy, solar energy, the water industry, wind energy, and the low-carbon industry. Additionally, the study explores two contemporary technology domains, AI and big data, alongside quantum computing. The findings reveal that AI and its associated technologies generally exhibit weaker connections to the renewable and sustainable energy sectors. However, specific pairs, such as those involving business intelligence and AI, show notable interconnectedness. Overall, quantum computing entities demonstrate lower levels of connectedness than the AI/significant data sector, with Microsoft standing out for its solid and broad connections to renewable and sustainable industries. Further analysis identifies distinct patterns, with AI and related technologies showing strong long-term memory connections with renewables and green energies. At the same time, platforms centered on business intelligence and AI display comparatively weaker long-term ties. Among the quantum computing companies, IBM and Google have shown superior performance through specific subsectors. Finally, this study offers valuable insights into the evolving dynamics and inter­ connectedness at the intersection of renewable and sustainable energies, quantum computing, and the AI/big data industries. The findings support strategic decision-making in sustainable energy transitions and underscore the significance of industry-specific factors in shaping long-term collaborations.|
    |日期|12/2024|
    |语言|en|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S0140988324007254](https://linkinghub.elsevier.com/retrieve/pii/S0140988324007254)|
    |访问时间|2024/12/24 20:54:59|
    |卷次|140|
    |页码|108017|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2024.108017](http://doi.org/10.1016/j.eneco.2024.108017)|
    |刊名简称|Energy Economics|
    |ISSN|01409883|
    |添加日期|2024/12/24 20:54:59|
    |修改日期|2025/6/13 11:16:55|
    
    ### 附件
    
    - Ghaemi Asl 等 - 2024 - Dynamic connectedness of quantum computing, artifi.pdf
- ## Dynamic connectedness of quantum computing, artificial intelligence, and big data stocks on renewable and sustainable energy
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Mahdi Ghaemi Asl|
    |作者|Sami Ben Jabeur|
    |作者|Hela Nammouri|
    |作者|Kamel Bel Hadj Miled|
    |摘要|This research aims to evaluate the accuracy of the long-term relationship between renewable and sustainable energy sectors and emerging technologies, including quantum computing, artificial intelligence (AI), and big data. Using a novel methodology that integrates the Time-Varying Parameter Vector Autoregressive (TVP-VAR) frequency connectedness approach with Long Short-Term Memory (LSTM) neural networks, the study examines the long-term interconnectedness, considering the dynamic nature of coefficients and covariance structures. The analysis spans from May 14, 2018, to September 6, 2023. It focuses on six critical clusters within the sustainable and renewable energy sectors: clean energy, green energy, solar energy, the water industry, wind energy, and the low-carbon industry. Additionally, the study explores two contemporary technology domains, AI and big data, alongside quantum computing. The findings reveal that AI and its associated technologies generally exhibit weaker connections to the renewable and sustainable energy sectors. However, specific pairs, such as those involving business intelligence and AI, show notable interconnectedness. Overall, quantum computing entities demonstrate lower levels of connectedness than the AI/significant data sector, with Microsoft standing out for its solid and broad connections to renewable and sustainable industries. Further analysis identifies distinct patterns, with AI and related technologies showing strong long-term memory connections with renewables and green energies. At the same time, platforms centered on business intelligence and AI display comparatively weaker long-term ties. Among the quantum computing companies, IBM and Google have shown superior performance through specific subsectors. Finally, this study offers valuable insights into the evolving dynamics and interconnectedness at the intersection of renewable and sustainable energies, quantum computing, and the AI/big data industries. The findings support strategic decision-making in sustainable energy transitions and underscore the significance of industry-specific factors in shaping long-term collaborations.|
    |日期|2024-12-01|
    |语言|en|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S0140988324007254](https://www.sciencedirect.com/science/article/pii/S0140988324007254)|
    |访问时间|2025/11/6 21:09:12|
    |卷次|140|
    |页码|108017|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2024.108017](http://doi.org/10.1016/j.eneco.2024.108017)|
    |刊名简称|Energy Economics|
    |ISSN|0140-9883|
    |添加日期|2025/11/6 21:09:12|
    |修改日期|2025/11/6 21:09:12|
    
    ### 标签：
    
    - Artificial intelligence
    - Big data
    - Long short-term memory
    - Quantum computing
    - Renewable and sustainable energies
    - TVP-VAR frequency connectedness approach
    
    ### 附件
    
    - ScienceDirect Full Text PDF
    - ScienceDirect Snapshot
- ## Dynamic volatility spillovers across oil and natural gas futures markets based on a time-varying spillover method
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Xu Gong|
    |作者|Yun Liu|
    |作者|Xiong Wang|
    |摘要|This paper analyzes dynamic volatility spillovers between four major energy commodities (i.e., crude oil, gasoline, heating oil and natural gas) in the oil-natural gas future markets. We construct a time-varying spillover method by combining the TVP-VAR-SV model and the spillover method of Diebold and Yilmaz (2009, 2012, 2014). We use the spillover method to obtain time-varying total, directional and pairwise volatility spillover indices. Our results summarize as follows: (1) The volatility spillover indices present peaks and troughs during some periods, such as shale gas revolution, financial crisis, and oil price crash; (2) After the U.S. shale gas revolution, the size of volatility spillover from natural gas future market has reduced sharply, but volatility doesn't decouple from the other three oil future markets; (3) The directional spillover is asymmetric. The crude oil and heating oil futures market are main net transmitter of volatility risk information, while the gasoline and natural gas futures markets are the net receiver; (4) For natural gas future market, the pairwise volatility spillover from crude oil future market has the most significant influence.|
    |日期|2021-07-01|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S1057521921001277](https://www.sciencedirect.com/science/article/pii/S1057521921001277)|
    |访问时间|2025/6/13 11:40:22|
    |卷次|76|
    |页码|101790|
    |刊名|International Review of Financial Analysis|
    |DOI|[10.1016/j.irfa.2021.101790](http://doi.org/10.1016/j.irfa.2021.101790)|
    |刊名简称|International Review of Financial Analysis|
    |ISSN|1057-5219|
    |添加日期|2025/6/13 11:40:22|
    |修改日期|2025/6/13 11:40:22|
    
    ### 标签：
    
    - Dynamic volatility spillover
    - Energy commodity futures
    - TVP-VAR-SV model
    - Volatility spillover index
    
    ### 附件
    
    - ScienceDirect Snapshot
- ## Exploring volatility interconnections between AI tokens, AI stocks, and fossil fuel markets: evidence from time and frequency-based connectedness analysis
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Imran Yousaf|
    |摘要|Energy and artificial intelligence (AI) are two of the top fields of the present time. However, investors of con­ ventional energy assets have yet to consider the rapidly emerging AI-based assets for diversification. Owing to the rise of new categories of assets in the last two decades, which has sparked the interest of global investors to attain the most favorable outcomes, we examine volatility connectedness between AI stocks (MSFT-Microsoft, GOOG-Alphabet, AMZN-Amazon), AI tokens (AGIX-SingularityNET, OCEAN-Ocean Protocol, FET-Fetch.ai), and fossil fuel markets (WTI, BRENT, and GAS-natural gas) over the period from May 6, 2019, to July 8, 2023. We apply a novel three-dimensional framework in which we model time-domain and frequency-domain volatility spillovers at the median-, lower- and upper-quantiles in static as well as dynamic settings to achieve the ob­ jectives of this paper. We find the variation in static and dynamic connectedness between markets over timefrequencies and quantiles. Results reveal that AGIX, BRENT, FET, MSFT, and WTI are recipients, whereas AMZN, GAS, GOOG, and OCEAN are transmitters of the spillovers at the median quantile. Furthermore, we demonstrated that the short-term and long-term metrics for dynamic total connectedness might not consistently exhibit the same direction. Moreover, our analysis indicates that the short-term fluctuations predominantly in­ fluence the network’s overall shock transmission, while the longer-term aspect has the potential to alter the role of a net transmitter or receiver of shocks. These findings provide portfolio managers, regulators, and policy­ makers with valuable information regarding portfolio adjustments, hedging, and financial stability.|
    |日期|2024|
    |语言|en|
    |文库编目|Zotero|
    |刊名|Energy Economics|
    |添加日期|2024/12/17 18:58:54|
    |修改日期|2025/9/30 11:49:03|
    
    ### 附件
    
    - Yousaf - 2024 - Exploring volatility interconnections between AI t.pdf
- ## Forecasting of photovoltaic power generation and model optimization: A review
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Utpal Kumar Das|
    |作者|Kok Soon Tey|
    |作者|Mehdi Seyedmahmoudian|
    |作者|Saad Mekhilef|
    |作者|Moh Yamani Idna Idris|
    |作者|Willem Van Deventer|
    |作者|Bend Horan|
    |作者|Alex Stojcevski|
    |摘要|To mitigate the impact of climate change and global warming, the use of renewable energies is increasing day by day significantly. A considerable amount of electricity is generated from renewable energy sources since the last decade. Among the potential renewable energies, photovoltaic (PV) has experienced enormous growth in electricity generation. A large number of PV systems have been installed in on-grid and off-grid systems in the last few years. The number of PV systems will increase rapidly in the future due to the policies of the government and international organizations, and the advantages of PV technology. However, the variability of PV power generation creates different negative impacts on the electric grid system, such as the stability, reliability, and planning of the operation, aside from the economic benefits. Therefore, accurate forecasting of PV power generation is significantly important to stabilize and secure grid operation and promote large-scale PV power integration. A good number of research has been conducted to forecast PV power generation in different perspectives. This paper made a comprehensive and systematic review of the direct forecasting of PV power generation. The importance of the correlation of the input-output data and the preprocessing of model input data are discussed. This review covers the performance analysis of several PV power forecasting models based on different classifications. The critical analysis of recent works, including statistical and machine-learning models based on historical data, is also presented. Moreover, the strengths and weaknesses of the different forecasting models, including hybrid models, and performance matrices in evaluating the forecasting model, are considered in this research. In addition, the potential benefits of model optimization are also discussed.|
    |日期|2018-01-01|
    |短标题|Forecasting of photovoltaic power generation and model optimization|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S1364032117311620](https://www.sciencedirect.com/science/article/pii/S1364032117311620)|
    |访问时间|2025/11/7 15:58:42|
    |卷次|81|
    |页码|912-928|
    |刊名|Renewable and Sustainable Energy Reviews|
    |DOI|[10.1016/j.rser.2017.08.017](http://doi.org/10.1016/j.rser.2017.08.017)|
    |刊名简称|Renewable and Sustainable Energy Reviews|
    |ISSN|1364-0321|
    |添加日期|2025/11/7 15:58:42|
    |修改日期|2025/11/7 15:58:42|
    
    ### 标签：
    
    - Artificial intelligence
    - Hybrid model
    - Machine-learning
    - Optimization
    - PV power forecasting
    
    ### 附件
    
    - ScienceDirect Full Text PDF
    - ScienceDirect Snapshot
- ## Generative AI and Firm Values
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Andrea L Eisfeldt|
    |作者|Gregor Schubert|
    |作者|Miao Ben Zhang|
    |摘要|What are the effects of recent advances in Generative AI on the value of firms? Our study offers a quantitative answer to this question for U.S. publicly traded companies based on the exposures of their workforce to Generative AI. Our novel firm-level measure of workforce exposure to Generative AI is validated by data from earnings calls, and has intuitive relationships with firm and industry-level characteristics. Using Artificial Minus Human portfolios that are long firms with higher exposures and short firms with lower exposures, we show that higher-exposure firms earned excess returns that are 0.4% higher on a daily basis than returns of firms with lower exposures following the release of ChatGPT. Although this release was generally received by investors as good news for more exposed firms, there is wide variation across and within industries, consistent with the substantive disruptive potential of Generative AI technologies.|
    |语言|en|
    |文库编目|Zotero|
    |添加日期|2025/10/31 14:22:28|
    |修改日期|2025/10/31 14:22:28|
    
    ### 附件
    
    - PDF
- ## How are artificial intelligence, carbon market, and energy sector connected? A systematic analysis of time-frequency spillovers
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Yingying Xu|
    |作者|Xuefeng Shao|
    |作者|Cristina Tanasescu|
    |摘要|The dual role of artificial intelligence (AI) in carbon emissions has come under scrutiny. The feedback mechanism in the “AI-Carbon-Energy” system contains the enlightenment of coordinated development of environment and economy. Based on the dynamic connectedness index and network diagrams, we quantify how the AI industry is connected to the carbon market and the energy sector in the short-term and long-term. Our empirical findings suggest that the information spillover within the system changes over time and across frequency bands. The longterm component drives the overall information spillover. Both the carbon market and the energy sector are closely connected with the AI industry. Specifically, AI industry trading volume is a main information trans­ mitter. Since the release of GPT-4, however, investor attention to the AI industry becomes more important. The carbon market receives a lot of information from the AI industry trading volume and investor attention to the AI industry, particularly since 2023. Nevertheless, the energy sector is only weakly connected to the other two markets. These findings have important implications for policy makers, investors, and producers.|
    |日期|04/2024|
    |语言|en|
    |短标题|How are artificial intelligence, carbon market, and energy sector connected?|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S0140988324001853](https://linkinghub.elsevier.com/retrieve/pii/S0140988324001853)|
    |访问时间|2024/12/17 18:59:30|
    |卷次|132|
    |页码|107477|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2024.107477](http://doi.org/10.1016/j.eneco.2024.107477)|
    |刊名简称|Energy Economics|
    |ISSN|01409883|
    |添加日期|2024/12/17 18:59:30|
    |修改日期|2025/10/26 03:34:38|
    
    ### 附件
    
    - Xu 等 - 2024 - How are artificial intelligence, carbon market, an.pdf
- ## How does artificial intelligence affect sustainable development by improving energy efficiency and optimizing energy structure
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Kai Dong|
    |作者|Yuanyuan Yang|
    |作者|Tianxiang Sheng|
    |作者|Lingyun Liu|
    |作者|Kaiyi Song|
    |摘要|Currently, the technological revolution represented by Artificial Intelligence (AI) not only drives substantial changes in productivity and profoundly alters people's lifestyle, but also provides solid technological support for sustainable development. The purpose of this study is to explore the degree, mechanism and temporal characteristics of AI's effect on Sustainable development based on data from 280 prefecture level cities in China. Therefore, this article comprehensively employs various econometric methods such as entropy weight method, SBM model, fixed effects model and TVP-SV-VAR model. The research results indicate that AI's effect on sustainable development is positive and this conclusion has passed a series of robustness tests. AI could ameliorate sustainable development by improving energy efficiency and optimizing energy structure. Besides, the heterogeneity analysis reveals significantly improvement of AI's effect on sustainable development in eastern and central regions, while the influence is insignificant in western region. Further analysis illustrates that AI's effect on sustainable development exhibits time-varying characteristics, whether the pulse response applied at different lag periods or different time points. Based on the above research conclusions, this article believes that government should formulate policy measures to promote the development of AI according to local conditions, especially focusing on the deep integration of AI and energy industry. In addition, the formulation and implementation of policies should keep pace with the times, and adjust them in a prompt manner.|
    |日期|2025-09-15|
    |语言|en|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://link.springer.com/10.1007/s10668-025-06618-1](https://link.springer.com/10.1007/s10668-025-06618-1)|
    |访问时间|2025/11/7 15:50:26|
    |刊名|Environment, Development and Sustainability|
    |DOI|[10.1007/s10668-025-06618-1](http://doi.org/10.1007/s10668-025-06618-1)|
    |刊名简称|Environ Dev Sustain|
    |ISSN|1573-2975|
    |添加日期|2025/11/7 15:50:26|
    |修改日期|2025/11/7 15:50:26|
    
    ### 附件
    
    - PDF
- ## How does artificial intelligence affect the transformation of China's green economic growth? An analysis from internal-structure perspective
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Chao Feng|
    |作者|Xinru Ye|
    |作者|Jun Li|
    |作者|Jun Yang|
    |摘要|Artificial intelligence (AI) has been proved to be an important engine of green economic development, yet how it will affect the internal structure of green economy is unknown. The aim of this study is to examine the impact and its mechanism of AI on green total factor productivity (GTFP) from the internal-structure perspective, by using provincial panel data of China from 2009 to 2021 and global Malmquist index. The main research results show that: (1) the development of AI contributes to China’s GTFP growth. And this effect is more significant in undeveloped areas; (2) AI promotes China’s GTFP growth mainly by improving resource allocation efficiency, while it exerts little impact through the paths of technological progress and scale efficiency; (3) the transmission mechanism of AI on GTFP varies greatly among China’s three main regions. In the eastern region, AI improves GTFP mainly by both advancing technological progress and improving resource allocation efficiency, while in central region AI contributes to GTFP growth mainly through technological progress. Compared with the eastern and central regions, AI in the western region plays a stronger impact on GTFP through the channel of improving scale efficiency. This study helps to understand the pathways of artificial intelligence affecting the trans­ formation of green economic growth and formulate differentiated regional policies in light of local conditions.|
    |日期|02/2024|
    |语言|en|
    |短标题|How does artificial intelligence affect the transformation of China's green economic growth?|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S0301479723027111](https://linkinghub.elsevier.com/retrieve/pii/S0301479723027111)|
    |访问时间|2025/6/13 11:05:43|
    |卷次|351|
    |页码|119923|
    |刊名|Journal of Environmental Management|
    |DOI|[10.1016/j.jenvman.2023.119923](http://doi.org/10.1016/j.jenvman.2023.119923)|
    |刊名简称|Journal of Environmental Management|
    |ISSN|03014797|
    |添加日期|2025/6/13 11:05:43|
    |修改日期|2025/6/13 11:18:33|
    
    ### 附件
    
    - Feng 等 - 2024 - How does artificial intelligence affect the transf.pdf
- ## How does clean energy reshape the relationship between artificial intelligence and carbon emissions? Evidence from renewable and nuclear energy
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Fuyu Zhang|
    |作者|Qiang Wang|
    |作者|Rongrong Li|
    |摘要|The high energy demand of artificial intelligence (AI) poses a significant challenge to global decarbonization efforts. This study provides novel insights into AI technology's impact on carbon emissions by examining the energy rebound effect and clean energy as key mechanisms. Using panel data from 62 countries over 1995–2023, a nonlinear mechanism identification model is constructed. The empirical results uncover a stage-dependent relationship: AI initially increases carbon emissions, but reduces them as AI technology develops. This inverted U-shaped pattern is driven by applied rather than foundational AI, with turning points indicating that reducing total carbon emissions is more difficult than lowering carbon emission intensity. The energy rebound effect mediates the AI–emissions relationship—amplifying emissions in the early stages but weakening as AI technology develops. Clean energy moderates the relationship in source-specific ways: renewable energy advances the turning point at which AI contributes to carbon emission reductions, whereas nuclear energy mitigates the initial emission-increasing effects of AI. These findings suggest that realizing the carbon mitigation potential of AI requires a coordinated strategy—curbing energy rebound risks, optimizing clean energy portfolios, and tailoring governance to the evolving stages of AI development.|
    |日期|2025-09-01|
    |短标题|How does clean energy reshape the relationship between artificial intelligence and carbon emissions?|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S0140988325006127](https://www.sciencedirect.com/science/article/pii/S0140988325006127)|
    |访问时间|2025/11/6 21:10:36|
    |卷次|149|
    |页码|108785|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2025.108785](http://doi.org/10.1016/j.eneco.2025.108785)|
    |刊名简称|Energy Economics|
    |ISSN|0140-9883|
    |添加日期|2025/11/6 21:10:36|
    |修改日期|2025/11/6 21:10:36|
    
    ### 标签：
    
    - AI technology
    - Carbon emissions
    - Energy rebound effect
    - Nuclear energy
    - Renewable energy
    
    ### 附件
    
    - ScienceDirect Full Text PDF
    - ScienceDirect Snapshot
- ## Impact of renewable energy utilization and artificial intelligence in achieving sustainable development goals
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|M.A. Hannan|
    |作者|Ali Q Al-Shetwi|
    |作者|Pin Jern Ker|
    |作者|R.A. Begum|
    |作者|M. Mansor|
    |作者|S.A. Rahman|
    |作者|Z.Y. Dong|
    |作者|S.K. Tiong|
    |作者|T.M. Indra Mahlia|
    |作者|K.M. Muttaqi|
    |摘要|Many countries around the world are planning to reach 100% renewable energy use by 2050. In this context and due to the recent sharp increase in RE utilization in the global energy mix along with its progressive impact on the world energy sector, the evaluation and investigation of its effect on achieving sustainable development goals are not covered sufficiently. Moreover, an assessment of the emerging role of artificial intelligence for renewable energy utilization toward achieving SDGs is conducted. A total of 17 SDGs were divided into three groups, namely, environment, society, and economy, as per the three key pillars of sustainable development. Renewable energy has a positive impact toward achieving 75 targets across all sustainable development goals by using an expert elicitation method-based consensus. However, it may negatively affect the accomplishment of the 27 targets. In addition, artificial intelligence can help renewable energy enable the attainment of 42 out of 169 targets. However, with the current exponential growth of renewable energy share and artificial intelligence development and addressing certain present limitations, this impact may cover additional targets in the future. Nevertheless, recent research foci overlook essential aspects. The exponential growth of renewable energy share and rapid evolution of artificial intelligence need to be accompanied through the requisite regulatory insight and technology regulation to cover additional targets in the future.|
    |日期|11/2021|
    |语言|en|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S2352484721007757](https://linkinghub.elsevier.com/retrieve/pii/S2352484721007757)|
    |访问时间|2025/6/13 11:06:20|
    |卷次|7|
    |页码|5359-5373|
    |刊名|Energy Reports|
    |DOI|[10.1016/j.egyr.2021.08.172](http://doi.org/10.1016/j.egyr.2021.08.172)|
    |刊名简称|Energy Reports|
    |ISSN|23524847|
    |添加日期|2025/6/13 11:06:20|
    |修改日期|2025/6/13 11:22:49|
    
    ### 附件
    
    - Hannan 等 - 2021 - Impact of renewable energy utilization and artific.pdf
- ## Impact of technological innovation on China's mining industry: Perspectives of energy and environmental performance
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Runqing Zhu|
    |作者|Zuopeng Justin Zhang|
    |作者|Boqiang Lin|
    |摘要|Scientific and technological innovation is crucial for energy conservation and emissions reduction. This article estimates the impact of technological innovation on the energy and environmental performance of China's mining industry. Most previous research on technological innovation has focused on the industry as a whole part, while the literature on sub-industries from different regions is limited due to the scarcity of information. The contributions of this study are the following. First, it collects provincial patents on China's mining industry through web crawling, which provides accurate empirical data for sub-industry studies. Second, this article thoroughly evaluates the heterogeneous impact of technological innovation caused by economic development. And, third, this article proposes policy recommendations based on empirical results, including strengthening technological innovation and environmental supervision.|
    |日期|2024-09-01|
    |短标题|Impact of technological innovation on China's mining industry|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S0195925524001732](https://www.sciencedirect.com/science/article/pii/S0195925524001732)|
    |访问时间|2024/12/3 15:44:23|
    |卷次|108|
    |页码|107586|
    |刊名|Environmental Impact Assessment Review|
    |DOI|[10.1016/j.eiar.2024.107586](http://doi.org/10.1016/j.eiar.2024.107586)|
    |刊名简称|Environmental Impact Assessment Review|
    |ISSN|0195-9255|
    |添加日期|2024/12/3 15:44:23|
    |修改日期|2024/12/3 15:44:23|
    
    ### 标签：
    
    - Energy and environmental performance
    - Mining industry
    - Patent application
    - Technological innovation
    
    ### 附件
    
    - ScienceDirect Snapshot
- ## Increasing the resilience of the Texas power grid against extreme storms by hardening critical lines
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Julian Stürmer|
    |作者|Anton Plietzsch|
    |作者|Thomas Vogt|
    |作者|Frank Hellmann|
    |作者|Jürgen Kurths|
    |作者|Christian Otto|
    |作者|Katja Frieler|
    |作者|Mehrnaz Anvari|
    |摘要|Abstract The Texas power grid on the Gulf Coast of the United States is frequently hit by tropical cyclones (TCs) causing widespread power outages, a risk that is expected to substantially increase under global warming. Here we introduce a new approach that combines a probabilistic line failure model with a network model of the Texas grid to simulate the spatio-temporal co-evolution of wind-induced failures of high-voltage transmission lines and the resulting cascading power outages from seven major historical TCs. The approach allows reproducing observed supply failures. In addition, compared to existing static approaches, it provides a notable advantage in identifying critical lines whose failure can trigger large supply shortages. We show that hardening only 1% of total lines can reduce the likelihood of the most destructive type of outage by a factor of between 5 and 20. The proposed modelling approach could represent a so far missing tool for identifying effective options to strengthen power grids against future TC strikes, even under limited knowledge.|
    |日期|2024-03-01|
    |语言|en|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://www.nature.com/articles/s41560-023-01434-1](https://www.nature.com/articles/s41560-023-01434-1)|
    |访问时间|2025/11/7 15:50:35|
    |卷次|9|
    |页码|526-535|
    |刊名|Nature Energy|
    |DOI|[10.1038/s41560-023-01434-1](http://doi.org/10.1038/s41560-023-01434-1)|
    |期号|5|
    |刊名简称|Nat Energy|
    |ISSN|2058-7546|
    |添加日期|2025/11/7 15:50:35|
    |修改日期|2025/11/7 15:50:35|
    
    ### 附件
    
    - PDF
- ## Interconnectedness between electricity and artificial intelligence-based markets during the crisis periods: Evidence from the TVP-VAR approach
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Imran Yousaf|
    |作者|Obaika M. Ohikhuare|
    |作者|Yong Li|
    |作者|Yanshuang Li|
    |摘要|This paper examines the returns and volatilities connectedness between the electricity and AI-based markets using the Time-Varying Parameter Vector Autoregression (TVP-VAR) approach. Our sample covers the COVID-19 and Russia-Ukraine conflict-based sub-periods, and the time-varying results provide valuable insights into these two crisis episodes. Further, we estimate the determinants of returns and volatility spillovers between the electricity and AI stock markets. The following findings are apparent in our study: certain AI stocks are considered safer investments during high market risks and uncertainties; being the highest receiver of system shocks does not equate to the most vulnerability. The alternative electricity market acts as a net pairwise shock transmitter to the conventional electricity market; MSFT is the dominant asset in the system of network connectedness between the electricity and AI stock markets. Systemic and market risks and assets like Gold, Bitcoin, and BONDS significantly drive spillover interconnectedness between these electricity and artificial in­ telligence stock markets. These findings have implications for investors and policymakers.|
    |日期|11/2024|
    |语言|en|
    |短标题|Interconnectedness between electricity and artificial intelligence-based markets during the crisis periods|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S0140988324005930](https://linkinghub.elsevier.com/retrieve/pii/S0140988324005930)|
    |访问时间|2024/12/24 20:55:03|
    |卷次|139|
    |页码|107885|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2024.107885](http://doi.org/10.1016/j.eneco.2024.107885)|
    |刊名简称|Energy Economics|
    |ISSN|01409883|
    |添加日期|2024/12/24 20:55:03|
    |修改日期|2025/6/13 11:16:25|
    
    ### 附件
    
    - Yousaf 等 - 2024 - Interconnectedness between electricity and artific.pdf
- ## Investigating the asymmetric impact of artificial intelligence on renewable energy under climate policy uncertainty
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Lihui Tian|
    |作者|Xin Li|
    |作者|Cheng-Wen Lee|
    |作者|Cristi Spulbăr|
    |摘要|The focus on sustainable development and the transition to renewable energy sources has intensified due to the risks associated with climate change. This study provides new insights into the impact of artificial intelligence (AI) and climate policy uncertainty (CPU) on the development of renewable energy (RE) in China. Utilizing a nonlinear autoregressive distributed lag (NARDL) framework, the asymmetric relationship between these variables from January 2013 to April 2023 is revealed. The empirical results indicate a significant positive asymmetric effect of AI on RE development, with downturns in AI having a more pronounced influence compared to upswings. Additionally, CPU has a positive effect on RE development, also exhibiting an asymmetric pattern where declines in CPU have a more substantial impact than upturns. These findings highlight the critical roles of AI and CPU in renewable energy development and add new dimensions to existing research. Policymakers should consider these asymmetric dynamics when formulating strategies to facilitate the energy transition through climate policymaking and the advancement of AI-driven technologies.|
    |日期|2024-09-01|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S0140988324005176](https://www.sciencedirect.com/science/article/pii/S0140988324005176)|
    |访问时间|2025/11/6 21:11:57|
    |卷次|137|
    |页码|107809|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2024.107809](http://doi.org/10.1016/j.eneco.2024.107809)|
    |刊名简称|Energy Economics|
    |ISSN|0140-9883|
    |添加日期|2025/11/6 21:11:57|
    |修改日期|2025/11/6 21:11:57|
    
    ### 标签：
    
    - Artificial intelligence
    - Climate policy uncertainty
    - Energy transition
    
    ### 附件
    
    - ScienceDirect Full Text PDF
    - ScienceDirect Snapshot
- ## Is artificial intelligence a curse or a blessing for enterprise energy intensity? Evidence from China
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Weike Zhang|
    |作者|Ming Zeng|
    |摘要|Artificial intelligence (AI) has experienced significant momentum worldwide in recent years. However, its rapid growth has raised concerns about energy shortages due to its high energy consumption, despite its potential to conserve energy in various ways. This study seeks to investigate the impact of AI on enterprise energy intensity (EI) by analyzing data from Chinese manufacturing listed enterprises during the period of 2011–2019. The findings reveal that the widespread adoption of AI can significantly reduce enterprise EI. Specifically, incorporating an additional unit of industrial robots per hundred workers leads to an approximate 2.5% reduction in enterprise EI. These conclusions remain robust after performing various tests. Moreover, the reduction effect of AI on enterprise EI is more pronounced in enterprises with high energy-dependence, non-labor-intensive enterprises, and state-owned enterprises (SOEs). Mechanism analysis further indicates that AI achieves enterprise EI reduction by facilitating technological innovation and digital transformation. Additionally, the study highlights the influence of business cycles, industrial concentration, and environmental regulations on the impact of AI on reducing enterprise EI. These findings not only alleviate excessive concerns regarding AI's energy consumption but also emphasize the necessity for governments to formulate corresponding policies aimed at reducing enterprise EI.|
    |日期|2024-06-01|
    |语言|en|
    |短标题|Is artificial intelligence a curse or a blessing for enterprise energy intensity?|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S014098832400269X](https://www.sciencedirect.com/science/article/pii/S014098832400269X)|
    |访问时间|2025/11/6 21:14:56|
    |卷次|134|
    |页码|107561|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2024.107561](http://doi.org/10.1016/j.eneco.2024.107561)|
    |刊名简称|Energy Economics|
    |ISSN|0140-9883|
    |添加日期|2025/11/6 21:14:56|
    |修改日期|2025/11/6 21:14:56|
    
    ### 标签：
    
    - Artificial intelligence (AI)
    - Digital transformation
    - Energy intensity (EI)
    - Technological innovation
    
    ### 附件
    
    - ScienceDirect Full Text PDF
    - ScienceDirect Snapshot
- ## Is artificial intelligence an impediment or an impetus to renewable energy investment? Evidence from China
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Wen Li|
    |作者|Jing-Ping Li|
    |作者|Yun-Feng Wang|
    |作者|Sebastian-Emanuel Stan|
    |摘要|This study investigates the bidirectional relationship between artificial intelligence (AI) and renewable energy investment, emphasizing their strategic importance in achieving global low-carbon objectives. Using a high-frequency dataset from 2010 to 2024, which includes monthly observations on the artificial intelligence robotics index (AIW) and the renewable energy index (ENI) in China, this research employs a bootstrap subsample rolling window Granger causality test to examine dynamic causal linkages. The findings reveal that AI accelerates renewable energy investment by enhancing energy forecasting, grid optimization, and intelligent energy management. However, its long-term impact is constrained by high capital costs, resource limitations, and regulatory uncertainty. Moreover, renewable energy development reciprocally promotes AI advancements, particularly in energy storage and autonomous energy systems, although this synergy is vulnerable to policy instability and economic downturns. This study makes significant contributions by providing empirical evidence on the evolving role of AI in renewable energy investments and offering practical policy insights. The results inform policy-makers, investors, and energy firms about optimizing AI applications in renewable energy, improving regulatory frameworks, and fostering economic conditions that accelerate the shift towards a sustainable, carbon-neutral economy. These insights have broad implications for countries aiming to leverage AI-driven solutions for sustainable energy innovation.|
    |日期|2025-06-01|
    |短标题|Is artificial intelligence an impediment or an impetus to renewable energy investment?|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S0140988325003743](https://www.sciencedirect.com/science/article/pii/S0140988325003743)|
    |访问时间|2025/11/6 21:03:04|
    |卷次|147|
    |页码|108550|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2025.108550](http://doi.org/10.1016/j.eneco.2025.108550)|
    |刊名简称|Energy Economics|
    |ISSN|0140-9883|
    |添加日期|2025/11/6 21:03:04|
    |修改日期|2025/11/6 21:03:04|
    
    ### 标签：
    
    - Artificial intelligence
    - Granger causal relationship
    - Renewable energy investment
    - Time varying
    
    ### 附件
    
    - ScienceDirect Full Text PDF
    - ScienceDirect Snapshot
- ## Life cycle environmental impact assessment of natural gas distributed energy system
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Yakun Wang|
    |作者|Ting Ni|
    |作者|Bing He|
    |作者|Jiuping Xu|
    |摘要|Abstract Natural gas distributed energy is recognized as a pivotal means to enhance energy efficiency and mitigate carbon dioxide emissions through localized energy cascading. Positioned as a key option for advancing the Sustainable Development Goals, this system optimizes energy utilization near end-users. While maximizing energy efficiency, it is imperative to address potential environmental challenges. A thorough, comprehensive environmental assessment, facilitated by the life cycle assessment method, proves instrumental in meeting this standard. Employing this method enables an intuitive grasp of the environmental strengths and weaknesses inherent in natural gas distributed energy within the power structure. This insight serves as a foundation for informed project decision-making, fostering the growth of the industry. We selected six environmental impact assessment categories based on the CML 2001 method, and conducted the life cycle analysis across four stages. China's inaugural natural gas distributed energy demonstration project was chosen as a model case, and an environmental impact assessment inventory was established, utilizing survey data and literature for comprehensive data collection and analysis. Results from case testing yield environmental impact assessment outcomes, with a specific sensitivity analysis for stages with notable environmental impact factors. The study underscores that the operation phase has the highest environmental impact, comprising 78.37% of the total combined environmental impact, followed by the fuel production phase. Comparative analyses with coal-fired and conventional natural gas power generation, based on dimensionless literature data, reveal that abiotic resources depletion potential is the primary contributor to the environmental impact of 1 kWh of electricity product, constituting 52.76% of the total impact value, followed by global warming potential. Concrete strategies have been outlined for decision-making in both the operational and planning phases of natural gas distributed energy projects. The strengthening of policies is pinpointed towards grid connection and scale expansion.|
    |日期|2024-02-08|
    |语言|en|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://www.nature.com/articles/s41598-024-53495-1](https://www.nature.com/articles/s41598-024-53495-1)|
    |访问时间|2025/11/7 15:50:37|
    |卷次|14|
    |页码|3292|
    |刊名|Scientific Reports|
    |DOI|[10.1038/s41598-024-53495-1](http://doi.org/10.1038/s41598-024-53495-1)|
    |期号|1|
    |刊名简称|Sci Rep|
    |ISSN|2045-2322|
    |添加日期|2025/11/7 15:50:37|
    |修改日期|2025/11/7 15:50:37|
    
    ### 附件
    
    - PDF
- ## Liquidity, Bank Runs, and Bailouts: Spillover Effects During the Northern Rock Episode
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Paul Goldsmith-Pinkham|
    |作者|Tanju Yorulmazer|
    |摘要|In September 2007, Northern Rock—the ﬁfth largest mortgage lender in the United Kingdom—experienced an old-fashioned bank run, the ﬁrst bank run in the U.K. since the collapse of City of Glasgow Bank in 1878. The run had been contained by the government’s announcement that it would guarantee all deposits in Northern Rock. This paper analyzes spillover effects during the Northern Rock episode and shows that both the bank run and the subsequent bailout announcement had signiﬁcant effects on the rest of the U.K. banking system, as measured by abnormal returns on the stock prices of banks. The paper also shows that the effects were a rational response by investors to market news about the liability side of banks’ balance sheets. In particular, banks that rely on funding from wholesale markets were signiﬁcantly affected, a result consistent with the drying up of liquidity in wholesale markets and the record-high levels of the London Interbank Offered Rate (LIBOR) during the crisis.|
    |日期|6/2010|
    |语言|en|
    |短标题|Liquidity, Bank Runs, and Bailouts|
    |文库编目|DOI.org (Crossref)|
    |网址|[http://link.springer.com/10.1007/s10693-009-0079-2](http://link.springer.com/10.1007/s10693-009-0079-2)|
    |访问时间|2025/11/7 15:50:29|
    |版权|http://www.springer.com/tdm|
    |卷次|37|
    |页码|83-98|
    |刊名|Journal of Financial Services Research|
    |DOI|[10.1007/s10693-009-0079-2](http://doi.org/10.1007/s10693-009-0079-2)|
    |期号|2-3|
    |刊名简称|J Financ Serv Res|
    |ISSN|0920-8550, 1573-0735|
    |添加日期|2025/11/7 15:50:29|
    |修改日期|2025/11/7 15:50:29|
    
    ### 附件
    
    - PDF
- ## Mapping the impact of artificial intelligence on energy poverty: New evidence from spatial panel models
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Manuel A. Zambrano-Monserrate|
    |摘要|Energy poverty remains a critical challenge for sustainable development, particularly in low- and middle-income countries. As countries seek innovative solutions to expand energy access, artificial intelligence (AI) has emerged as a promising tool. While recent studies have explored the role of AI in improving energy access, few have considered its spatial effects. Therefore, this paper investigates how AI adoption affects energy poverty using a spatial panel dataset of 64 countries from 2010 to 2019. Spatial econometric models reveal that higher AI adoption is significantly associated with reductions in energy poverty and that these benefits extend beyond national borders through regional spillovers. Mediation analysis shows that technological innovation, proxied by patent activity, partially transmits the impact of AI, while moderation analysis reveals that the effect of AI is stronger in less urbanized settings and where public spending is relatively low. These findings provide the first empirical evidence of spatial dependence in the AI–energy poverty nexus and highlight the importance of designing targeted, regionally coordinated policies. Thus, promoting AI-enabled off-grid solutions and strengthening innovation systems could help reduce spatial disparities in energy access, especially when embedded within broader international partnerships and adaptive national energy policies.|
    |日期|2025-11-01|
    |短标题|Mapping the impact of artificial intelligence on energy poverty|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S0140988325007364](https://www.sciencedirect.com/science/article/pii/S0140988325007364)|
    |访问时间|2025/11/6 21:02:42|
    |卷次|151|
    |页码|108909|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2025.108909](http://doi.org/10.1016/j.eneco.2025.108909)|
    |刊名简称|Energy Economics|
    |ISSN|0140-9883|
    |添加日期|2025/11/6 21:02:42|
    |修改日期|2025/11/6 21:02:42|
    
    ### 标签：
    
    - Artificial intelligence
    - Energy poverty
    - Spatial econometrics
    - Spatial spillovers
    - Technological innovation
    
    ### 附件
    
    - ScienceDirect Full Text PDF
    - ScienceDirect Snapshot
- ## Measuring Financial Asset Return and Volatility Spillovers, with Application to Global Equity Markets
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Francis X. Diebold|
    |作者|Kamil Yilmaz|
    |日期|2009-01-01|
    |语言|en|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://academic.oup.com/ej/article/119/534/158-171/5089555](https://academic.oup.com/ej/article/119/534/158-171/5089555)|
    |访问时间|2024/12/16 15:54:33|
    |版权|http://doi.wiley.com/10.1002/tdm_license_1.1|
    |卷次|119|
    |页码|158-171|
    |刊名|The Economic Journal|
    |DOI|[10.1111/j.1468-0297.2008.02208.x](http://doi.org/10.1111/j.1468-0297.2008.02208.x)|
    |期号|534|
    |ISSN|0013-0133, 1468-0297|
    |添加日期|2024/12/16 15:54:33|
    |修改日期|2025/10/20 20:24:58|
    
    ### 附件
    
    - 1-s2.0-S014098832400803X-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_IDZSHF34/1)
        - [2 Literature review and hypotheses](zotero://open-pdf/0_IDZSHF34/3)
            - [2.1 GDW studies](zotero://open-pdf/0_IDZSHF34/3)
            - [2.2 AIT and GDW](zotero://open-pdf/0_IDZSHF34/3)
            - [2.3 Influence mechanisms and research hypotheses](zotero://open-pdf/0_IDZSHF34/4)
                - [2.3.1 The channel of GTFP](zotero://open-pdf/0_IDZSHF34/4)
                - [2.3.2 The channel of human capital structure](zotero://open-pdf/0_IDZSHF34/4)
                - [2.3.3 The channel of EA](zotero://open-pdf/0_IDZSHF34/5)
        - [3 Variables and model specification](zotero://open-pdf/0_IDZSHF34/5)
            - [3.1 GDW measurement](zotero://open-pdf/0_IDZSHF34/5)
            - [3.2 Main variables’ description](zotero://open-pdf/0_IDZSHF34/6)
                - [3.2.1 Explained variables](zotero://open-pdf/0_IDZSHF34/6)
                - [3.2.2 Core explanatory variables](zotero://open-pdf/0_IDZSHF34/6)
                - [3.2.3 Mediating variables](zotero://open-pdf/0_IDZSHF34/6)
                - [3.2.4 Control variables](zotero://open-pdf/0_IDZSHF34/6)
            - [3.3 Models](zotero://open-pdf/0_IDZSHF34/7)
                - [3.3.1 Baseline model](zotero://open-pdf/0_IDZSHF34/7)
                - [3.3.2 Mediating effect model](zotero://open-pdf/0_IDZSHF34/7)
            - [3.4 Data sources and descriptive statistics](zotero://open-pdf/0_IDZSHF34/7)
        - [4 Results and analysis](zotero://open-pdf/0_IDZSHF34/8)
            - [4.1 Benchmark analysis](zotero://open-pdf/0_IDZSHF34/8)
            - [4.2 Endogeneity test](zotero://open-pdf/0_IDZSHF34/9)
                - [4.2.1 Omitted variable test](zotero://open-pdf/0_IDZSHF34/9)
                - [4.2.2 Instrumental variable method](zotero://open-pdf/0_IDZSHF34/10)
            - [4.3 Other robust test](zotero://open-pdf/0_IDZSHF34/10)
            - [4.4 Mechanism analysis](zotero://open-pdf/0_IDZSHF34/11)
                - [4.4.1 Green total factor productivity channel](zotero://open-pdf/0_IDZSHF34/11)
                - [4.4.2 Human capital structure channel](zotero://open-pdf/0_IDZSHF34/11)
                - [4.4.3 Entrepreneurial activity channel](zotero://open-pdf/0_IDZSHF34/11)
        - [5 Further discussion](zotero://open-pdf/0_IDZSHF34/12)
            - [5.1 Heterogeneity of environmental regulation](zotero://open-pdf/0_IDZSHF34/12)
            - [5.2 Heterogeneity of regions](zotero://open-pdf/0_IDZSHF34/13)
            - [5.3 Impact of AIT intensity](zotero://open-pdf/0_IDZSHF34/13)
        - [6 Conclusions and policy implications](zotero://open-pdf/0_IDZSHF34/14)
            - [6.1 Main findings](zotero://open-pdf/0_IDZSHF34/14)
            - [6.2 Policy implications](zotero://open-pdf/0_IDZSHF34/14)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_IDZSHF34/15)
        - [Appendix A](zotero://open-pdf/0_IDZSHF34/15)
            - [A.1 DEA-SBM model calculations](zotero://open-pdf/0_IDZSHF34/15)
        - [Appendix B Dictionary of green keywords](zotero://open-pdf/0_IDZSHF34/16)
        - [Appendix C Division of East, Central, West, and Northeast Regions](zotero://open-pdf/0_IDZSHF34/16)
        - [Appendix D Supplementary data](zotero://open-pdf/0_IDZSHF34/16)
        - [References](zotero://open-pdf/0_IDZSHF34/16)
        
    - 1-s2.0-S105752192400005X-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_AKGP8YT5/1)
        - [2 Literature review](zotero://open-pdf/0_AKGP8YT5/4)
        - [3 Data and methodology](zotero://open-pdf/0_AKGP8YT5/4)
            - [3.1 Data](zotero://open-pdf/0_AKGP8YT5/4)
            - [3.2 Volatility estimation](zotero://open-pdf/0_AKGP8YT5/4)
            - [3.3 The QVAR method](zotero://open-pdf/0_AKGP8YT5/5)
            - [3.4 Frequency base of QVAR connectedness](zotero://open-pdf/0_AKGP8YT5/6)
            - [3.5 Wavelet local multiple correlations (WLMC)](zotero://open-pdf/0_AKGP8YT5/6)
            - [3.6 Quantile granger causality test](zotero://open-pdf/0_AKGP8YT5/7)
        - [4 Empirical results](zotero://open-pdf/0_AKGP8YT5/7)
            - [4.1 Spillover analysis during extreme lower quantile (q ​= ​0.01)](zotero://open-pdf/0_AKGP8YT5/7)
            - [4.2 Medium quantile spillover analysis (q ​= ​0.5)](zotero://open-pdf/0_AKGP8YT5/9)
            - [4.3 Spillover analysis during extreme upper quantile (q ​= ​0.99)](zotero://open-pdf/0_AKGP8YT5/12)
            - [4.4 Network plot analysis](zotero://open-pdf/0_AKGP8YT5/13)
            - [4.5 The result of wavelet local multiple correlations (WLMC)](zotero://open-pdf/0_AKGP8YT5/14)
            - [4.6 Robustness test](zotero://open-pdf/0_AKGP8YT5/17)
            - [4.7 Impact mechanisms and discussion of results](zotero://open-pdf/0_AKGP8YT5/17)
        - [5 Conclusions and policy implications](zotero://open-pdf/0_AKGP8YT5/19)
        - [Declaration of competing interest](zotero://open-pdf/0_AKGP8YT5/19)
        - [Data availability](zotero://open-pdf/0_AKGP8YT5/19)
        - [Acknowledgement](zotero://open-pdf/0_AKGP8YT5/19)
        - [References](zotero://open-pdf/0_AKGP8YT5/19)
        
    - 1-s2.0-S0140988324000963-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_5DQHDM9R/1)
        - [2 Literature review](zotero://open-pdf/0_5DQHDM9R/4)
            - [2.1 Energy transition and AI](zotero://open-pdf/0_5DQHDM9R/5)
            - [2.2 BRI and ET](zotero://open-pdf/0_5DQHDM9R/5)
            - [2.3 Paris Agreement and ET](zotero://open-pdf/0_5DQHDM9R/5)
            - [2.4 Geopolitical risks and ET](zotero://open-pdf/0_5DQHDM9R/6)
            - [2.5 Literature gap](zotero://open-pdf/0_5DQHDM9R/6)
        - [3 Theoretical underpinning](zotero://open-pdf/0_5DQHDM9R/6)
        - [4 Econometric approach and data](zotero://open-pdf/0_5DQHDM9R/8)
            - [4.1 Quantile VAR (QVAR) technique](zotero://open-pdf/0_5DQHDM9R/8)
            - [4.2 CQ method](zotero://open-pdf/0_5DQHDM9R/8)
            - [4.3 Data and pre-estimation analysis](zotero://open-pdf/0_5DQHDM9R/8)
        - [5 Results](zotero://open-pdf/0_5DQHDM9R/9)
            - [5.1 Analysis based on dynamic connectedness](zotero://open-pdf/0_5DQHDM9R/9)
            - [5.2 Analysis based on the CQ method](zotero://open-pdf/0_5DQHDM9R/10)
            - [5.3 Discussion](zotero://open-pdf/0_5DQHDM9R/15)
            - [5.4 Policy implications for energy transition based on AI’s role](zotero://open-pdf/0_5DQHDM9R/19)
        - [6 Conclusion](zotero://open-pdf/0_5DQHDM9R/20)
            - [6.1 Policy framework](zotero://open-pdf/0_5DQHDM9R/21)
                - [6.1.1 General policy recommendations](zotero://open-pdf/0_5DQHDM9R/21)
                    - [6.1.1.1 Short-run policies](zotero://open-pdf/0_5DQHDM9R/21)
                    - [6.1.1.2 Medium run policies](zotero://open-pdf/0_5DQHDM9R/21)
                    - [6.1.1.3 Long-run policies](zotero://open-pdf/0_5DQHDM9R/22)
                    - [6.1.1.4 Policy implications for portfolio investments](zotero://open-pdf/0_5DQHDM9R/23)
                    - [6.1.1.5 Further suggestions](zotero://open-pdf/0_5DQHDM9R/24)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_5DQHDM9R/25)
        - [Declaration of competing interest](zotero://open-pdf/0_5DQHDM9R/25)
        - [Appendix A Supplementary data](zotero://open-pdf/0_5DQHDM9R/25)
        - [References](zotero://open-pdf/0_5DQHDM9R/25)
        
    - 1-s2.0-S0140988324001117-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_ZEUM5DTZ/1)
        - [2 Literature review](zotero://open-pdf/0_ZEUM5DTZ/2)
        - [3 Quantitative models](zotero://open-pdf/0_ZEUM5DTZ/3)
            - [3.1 Full sample methodology](zotero://open-pdf/0_ZEUM5DTZ/3)
            - [3.2 Tests of parameter stability](zotero://open-pdf/0_ZEUM5DTZ/3)
            - [3.3 Sub sample methodology](zotero://open-pdf/0_ZEUM5DTZ/3)
        - [4 Data](zotero://open-pdf/0_ZEUM5DTZ/3)
        - [5 Quantitative analysis and discussion](zotero://open-pdf/0_ZEUM5DTZ/4)
        - [6 Conclusions and policy recommendations](zotero://open-pdf/0_ZEUM5DTZ/7)
            - [6.1 Conclusions](zotero://open-pdf/0_ZEUM5DTZ/7)
            - [6.2 Policy implications](zotero://open-pdf/0_ZEUM5DTZ/7)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_ZEUM5DTZ/7)
        - [Appendix A Supplementary data](zotero://open-pdf/0_ZEUM5DTZ/7)
        - [References](zotero://open-pdf/0_ZEUM5DTZ/7)
        
    - 1-s2.0-S0140988324002925-main (1).pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_XPZQR6C8/1)
        - [2 Literature review](zotero://open-pdf/0_XPZQR6C8/2)
        - [3 Theoretical analysis of the impact of AI on the energy transition](zotero://open-pdf/0_XPZQR6C8/3)
        - [4 Methodology](zotero://open-pdf/0_XPZQR6C8/4)
            - [4.1 Wavelet analysis](zotero://open-pdf/0_XPZQR6C8/4)
            - [4.2 Quantile-on-quantile method](zotero://open-pdf/0_XPZQR6C8/4)
        - [5 Data](zotero://open-pdf/0_XPZQR6C8/5)
        - [6 Empirical results](zotero://open-pdf/0_XPZQR6C8/6)
        - [7 Discussion](zotero://open-pdf/0_XPZQR6C8/9)
        - [8 Conclusion and implication](zotero://open-pdf/0_XPZQR6C8/11)
            - [8.1 Conclusion](zotero://open-pdf/0_XPZQR6C8/11)
            - [8.2 Policy implications](zotero://open-pdf/0_XPZQR6C8/11)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_XPZQR6C8/11)
        - [Acknowledgment](zotero://open-pdf/0_XPZQR6C8/11)
        - [Appendix A Supplementary data](zotero://open-pdf/0_XPZQR6C8/11)
        - [References](zotero://open-pdf/0_XPZQR6C8/11)
        
    - 1-s2.0-S0140988324002925-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_2YQJXZVD/1)
        - [2 Literature review](zotero://open-pdf/0_2YQJXZVD/2)
        - [3 Theoretical analysis of the impact of AI on the energy transition](zotero://open-pdf/0_2YQJXZVD/3)
        - [4 Methodology](zotero://open-pdf/0_2YQJXZVD/4)
            - [4.1 Wavelet analysis](zotero://open-pdf/0_2YQJXZVD/4)
            - [4.2 Quantile-on-quantile method](zotero://open-pdf/0_2YQJXZVD/4)
        - [5 Data](zotero://open-pdf/0_2YQJXZVD/5)
        - [6 Empirical results](zotero://open-pdf/0_2YQJXZVD/6)
        - [7 Discussion](zotero://open-pdf/0_2YQJXZVD/9)
        - [8 Conclusion and implication](zotero://open-pdf/0_2YQJXZVD/11)
            - [8.1 Conclusion](zotero://open-pdf/0_2YQJXZVD/11)
            - [8.2 Policy implications](zotero://open-pdf/0_2YQJXZVD/11)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_2YQJXZVD/11)
        - [Acknowledgment](zotero://open-pdf/0_2YQJXZVD/11)
        - [Appendix A Supplementary data](zotero://open-pdf/0_2YQJXZVD/11)
        - [References](zotero://open-pdf/0_2YQJXZVD/11)
        
    - 1-s2.0-S0140988324003244-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_CXJQRH6X/1)
        - [2 Literature review](zotero://open-pdf/0_CXJQRH6X/2)
            - [2.1 AI technology developments and CE nexus](zotero://open-pdf/0_CXJQRH6X/2)
            - [2.2 BC technology developments and CE nexus](zotero://open-pdf/0_CXJQRH6X/3)
        - [3 Theoretical mechanism](zotero://open-pdf/0_CXJQRH6X/3)
            - [3.1 As a basis for further innovation in the CE industry](zotero://open-pdf/0_CXJQRH6X/3)
            - [3.2 Promote the operational efficiency of the entire CE industrial chain](zotero://open-pdf/0_CXJQRH6X/3)
            - [3.3 Increasing investments in research and development (R&amp;D) and talents](zotero://open-pdf/0_CXJQRH6X/3)
            - [3.4 The cautious attitude to technological development](zotero://open-pdf/0_CXJQRH6X/3)
        - [4 Methodology](zotero://open-pdf/0_CXJQRH6X/4)
            - [4.1 Quantile-on-quantile regression](zotero://open-pdf/0_CXJQRH6X/4)
            - [4.2 The wavelet analysis method](zotero://open-pdf/0_CXJQRH6X/4)
        - [5 Data](zotero://open-pdf/0_CXJQRH6X/4)
        - [6 Empirical results](zotero://open-pdf/0_CXJQRH6X/5)
            - [6.1 Results of QQR](zotero://open-pdf/0_CXJQRH6X/5)
            - [6.2 Robust test](zotero://open-pdf/0_CXJQRH6X/9)
        - [7 Conclusions and policy implications](zotero://open-pdf/0_CXJQRH6X/10)
            - [7.1 Conclusions](zotero://open-pdf/0_CXJQRH6X/10)
            - [7.2 Policy implications](zotero://open-pdf/0_CXJQRH6X/10)
            - [7.3 Limitations and future directions](zotero://open-pdf/0_CXJQRH6X/11)
        - [Funding](zotero://open-pdf/0_CXJQRH6X/11)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_CXJQRH6X/11)
        - [Appendix A Supplementary data](zotero://open-pdf/0_CXJQRH6X/11)
        - [References](zotero://open-pdf/0_CXJQRH6X/11)
        
    - 1-s2.0-S0140988324004274-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_8UD5GQHD/1)
        - [2 Literature review](zotero://open-pdf/0_8UD5GQHD/2)
            - [2.1 Measurement and influencing factors of low-carbon energy transformation](zotero://open-pdf/0_8UD5GQHD/2)
            - [2.2 Effects of AI](zotero://open-pdf/0_8UD5GQHD/3)
            - [2.3 Research gaps](zotero://open-pdf/0_8UD5GQHD/3)
        - [3 Theoretical analysis and research hypotheses](zotero://open-pdf/0_8UD5GQHD/3)
            - [3.1 Effects of AI on low-carbon energy transformation](zotero://open-pdf/0_8UD5GQHD/3)
            - [3.2 Influence mechanism of AI and low-carbon energy transformation](zotero://open-pdf/0_8UD5GQHD/4)
            - [3.3 Threshold effect of the flow of innovation factors](zotero://open-pdf/0_8UD5GQHD/4)
        - [4 Methodology and data](zotero://open-pdf/0_8UD5GQHD/5)
            - [4.1 Model setting](zotero://open-pdf/0_8UD5GQHD/5)
            - [4.2 Variables and data](zotero://open-pdf/0_8UD5GQHD/5)
                - [4.2.1 Low-carbon energy structure index](zotero://open-pdf/0_8UD5GQHD/5)
                - [4.2.2 AI variable](zotero://open-pdf/0_8UD5GQHD/6)
                - [4.2.3 Innovation factor flow](zotero://open-pdf/0_8UD5GQHD/7)
                - [4.2.4 Other variables](zotero://open-pdf/0_8UD5GQHD/7)
                - [4.2.5 Data sources](zotero://open-pdf/0_8UD5GQHD/8)
        - [5 Results and discussion](zotero://open-pdf/0_8UD5GQHD/8)
            - [5.1 Correlation and basic results](zotero://open-pdf/0_8UD5GQHD/8)
            - [5.2 Heterogeneity analysis](zotero://open-pdf/0_8UD5GQHD/9)
            - [5.3 Robustness testing](zotero://open-pdf/0_8UD5GQHD/9)
                - [5.3.1 Endogenous processing](zotero://open-pdf/0_8UD5GQHD/9)
                - [5.3.2 Adjustment of variables, samples, and estimation methods](zotero://open-pdf/0_8UD5GQHD/9)
            - [5.4 Mechanism analysis](zotero://open-pdf/0_8UD5GQHD/11)
            - [5.5 Threshold effect analysis](zotero://open-pdf/0_8UD5GQHD/11)
        - [6 Conclusions](zotero://open-pdf/0_8UD5GQHD/12)
        - [7 Policy implications](zotero://open-pdf/0_8UD5GQHD/12)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_8UD5GQHD/13)
        - [Declaration of competing interest](zotero://open-pdf/0_8UD5GQHD/13)
        - [Acknowledgements](zotero://open-pdf/0_8UD5GQHD/13)
        - [Appendix A](zotero://open-pdf/0_8UD5GQHD/13)
        - [Appendix B](zotero://open-pdf/0_8UD5GQHD/15)
        - [Appendix C Supplementary data](zotero://open-pdf/0_8UD5GQHD/16)
        - [References](zotero://open-pdf/0_8UD5GQHD/16)
        
    - 1-s2.0-S0140988324004560-main (1).pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_FAXMZJFT/1)
        - [2 Literature review](zotero://open-pdf/0_FAXMZJFT/3)
            - [2.1 Measurement of energy poverty and its determinants](zotero://open-pdf/0_FAXMZJFT/3)
            - [2.2 The rise of artificial intelligence and its impact](zotero://open-pdf/0_FAXMZJFT/3)
            - [2.3 Literature gaps](zotero://open-pdf/0_FAXMZJFT/4)
        - [3 Research design](zotero://open-pdf/0_FAXMZJFT/4)
            - [3.1 Variable measurements and data sources](zotero://open-pdf/0_FAXMZJFT/4)
                - [3.1.1 Dependent variable](zotero://open-pdf/0_FAXMZJFT/4)
                - [3.1.2 Independent variable](zotero://open-pdf/0_FAXMZJFT/4)
                - [3.1.3 Control variables](zotero://open-pdf/0_FAXMZJFT/4)
                - [3.1.4 Mechanism variables](zotero://open-pdf/0_FAXMZJFT/5)
                - [3.1.5 Sample selection and data sources](zotero://open-pdf/0_FAXMZJFT/5)
            - [3.2 Identification strategy](zotero://open-pdf/0_FAXMZJFT/6)
        - [4 Primary results](zotero://open-pdf/0_FAXMZJFT/6)
            - [4.1 Correlation test](zotero://open-pdf/0_FAXMZJFT/6)
            - [4.2 Cross-sectional dependence and VIF tests](zotero://open-pdf/0_FAXMZJFT/6)
            - [4.3 Baseline results](zotero://open-pdf/0_FAXMZJFT/7)
            - [4.4 Panel quantile regression](zotero://open-pdf/0_FAXMZJFT/7)
            - [4.5 Discussion of heterogeneous effects and mechanisms](zotero://open-pdf/0_FAXMZJFT/8)
                - [4.5.1 Heterogeneous effects](zotero://open-pdf/0_FAXMZJFT/8)
                - [4.5.2 Mechanisms](zotero://open-pdf/0_FAXMZJFT/8)
            - [4.6 Further discussion](zotero://open-pdf/0_FAXMZJFT/10)
                - [4.6.1 Long-term impact](zotero://open-pdf/0_FAXMZJFT/10)
                - [4.6.2 Cooperative organizations](zotero://open-pdf/0_FAXMZJFT/11)
        - [5 Robustness tests](zotero://open-pdf/0_FAXMZJFT/11)
            - [5.1 IV estimations](zotero://open-pdf/0_FAXMZJFT/11)
            - [5.2 Progressive difference-in-differences model](zotero://open-pdf/0_FAXMZJFT/11)
            - [5.3 Other robustness tests](zotero://open-pdf/0_FAXMZJFT/12)
                - [5.3.1 Alternative dependent variable](zotero://open-pdf/0_FAXMZJFT/12)
                - [5.3.2 Alternative independent variable](zotero://open-pdf/0_FAXMZJFT/12)
                - [5.3.3 Control net energy imports](zotero://open-pdf/0_FAXMZJFT/12)
                - [5.3.4 Consider cross-sectional dependence](zotero://open-pdf/0_FAXMZJFT/12)
                - [5.3.5 Sys-GMM](zotero://open-pdf/0_FAXMZJFT/12)
        - [6 Conclusions and policy implications](zotero://open-pdf/0_FAXMZJFT/12)
            - [6.1 Conclusions](zotero://open-pdf/0_FAXMZJFT/12)
            - [6.2 Policy implications](zotero://open-pdf/0_FAXMZJFT/13)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_FAXMZJFT/14)
        - [Declaration of competing interest](zotero://open-pdf/0_FAXMZJFT/14)
        - [Acknowledgements](zotero://open-pdf/0_FAXMZJFT/14)
        - [Appendix A](zotero://open-pdf/0_FAXMZJFT/14)
        - [Appendix A Supplementary data](zotero://open-pdf/0_FAXMZJFT/15)
        - [References](zotero://open-pdf/0_FAXMZJFT/15)
        
    - 1-s2.0-S0140988324004560-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_F7UYHQQ3/1)
        - [2 Literature review](zotero://open-pdf/0_F7UYHQQ3/3)
            - [2.1 Measurement of energy poverty and its determinants](zotero://open-pdf/0_F7UYHQQ3/3)
            - [2.2 The rise of artificial intelligence and its impact](zotero://open-pdf/0_F7UYHQQ3/3)
            - [2.3 Literature gaps](zotero://open-pdf/0_F7UYHQQ3/4)
        - [3 Research design](zotero://open-pdf/0_F7UYHQQ3/4)
            - [3.1 Variable measurements and data sources](zotero://open-pdf/0_F7UYHQQ3/4)
                - [3.1.1 Dependent variable](zotero://open-pdf/0_F7UYHQQ3/4)
                - [3.1.2 Independent variable](zotero://open-pdf/0_F7UYHQQ3/4)
                - [3.1.3 Control variables](zotero://open-pdf/0_F7UYHQQ3/4)
                - [3.1.4 Mechanism variables](zotero://open-pdf/0_F7UYHQQ3/5)
                - [3.1.5 Sample selection and data sources](zotero://open-pdf/0_F7UYHQQ3/5)
            - [3.2 Identification strategy](zotero://open-pdf/0_F7UYHQQ3/6)
        - [4 Primary results](zotero://open-pdf/0_F7UYHQQ3/6)
            - [4.1 Correlation test](zotero://open-pdf/0_F7UYHQQ3/6)
            - [4.2 Cross-sectional dependence and VIF tests](zotero://open-pdf/0_F7UYHQQ3/6)
            - [4.3 Baseline results](zotero://open-pdf/0_F7UYHQQ3/7)
            - [4.4 Panel quantile regression](zotero://open-pdf/0_F7UYHQQ3/7)
            - [4.5 Discussion of heterogeneous effects and mechanisms](zotero://open-pdf/0_F7UYHQQ3/8)
                - [4.5.1 Heterogeneous effects](zotero://open-pdf/0_F7UYHQQ3/8)
                - [4.5.2 Mechanisms](zotero://open-pdf/0_F7UYHQQ3/8)
            - [4.6 Further discussion](zotero://open-pdf/0_F7UYHQQ3/10)
                - [4.6.1 Long-term impact](zotero://open-pdf/0_F7UYHQQ3/10)
                - [4.6.2 Cooperative organizations](zotero://open-pdf/0_F7UYHQQ3/11)
        - [5 Robustness tests](zotero://open-pdf/0_F7UYHQQ3/11)
            - [5.1 IV estimations](zotero://open-pdf/0_F7UYHQQ3/11)
            - [5.2 Progressive difference-in-differences model](zotero://open-pdf/0_F7UYHQQ3/11)
            - [5.3 Other robustness tests](zotero://open-pdf/0_F7UYHQQ3/12)
                - [5.3.1 Alternative dependent variable](zotero://open-pdf/0_F7UYHQQ3/12)
                - [5.3.2 Alternative independent variable](zotero://open-pdf/0_F7UYHQQ3/12)
                - [5.3.3 Control net energy imports](zotero://open-pdf/0_F7UYHQQ3/12)
                - [5.3.4 Consider cross-sectional dependence](zotero://open-pdf/0_F7UYHQQ3/12)
                - [5.3.5 Sys-GMM](zotero://open-pdf/0_F7UYHQQ3/12)
        - [6 Conclusions and policy implications](zotero://open-pdf/0_F7UYHQQ3/12)
            - [6.1 Conclusions](zotero://open-pdf/0_F7UYHQQ3/12)
            - [6.2 Policy implications](zotero://open-pdf/0_F7UYHQQ3/13)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_F7UYHQQ3/14)
        - [Declaration of competing interest](zotero://open-pdf/0_F7UYHQQ3/14)
        - [Acknowledgements](zotero://open-pdf/0_F7UYHQQ3/14)
        - [Appendix A](zotero://open-pdf/0_F7UYHQQ3/14)
        - [Appendix A Supplementary data](zotero://open-pdf/0_F7UYHQQ3/15)
        - [References](zotero://open-pdf/0_F7UYHQQ3/15)
        
    - 1-s2.0-S0140988324005930-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_HZU3S7CF/1)
        - [2 Methodology](zotero://open-pdf/0_HZU3S7CF/3)
            - [2.1 Time-varying parameters vector autoregressive model (TVP-VAR)](zotero://open-pdf/0_HZU3S7CF/3)
        - [3 Data and preliminary analyses](zotero://open-pdf/0_HZU3S7CF/4)
            - [3.1 Data](zotero://open-pdf/0_HZU3S7CF/4)
            - [3.2 Preliminary analyses](zotero://open-pdf/0_HZU3S7CF/4)
                - [3.2.1 Descriptive statistics](zotero://open-pdf/0_HZU3S7CF/4)
                - [3.2.2 Correlation analysis](zotero://open-pdf/0_HZU3S7CF/5)
                - [3.2.3 Causal test](zotero://open-pdf/0_HZU3S7CF/5)
        - [4 Discussion of empirical findings](zotero://open-pdf/0_HZU3S7CF/5)
            - [4.1 Spillover results](zotero://open-pdf/0_HZU3S7CF/5)
                - [4.1.1 Trend of total return and volatility spillover](zotero://open-pdf/0_HZU3S7CF/8)
                - [4.1.2 Implication of the spillover result](zotero://open-pdf/0_HZU3S7CF/8)
            - [4.2 Network plot](zotero://open-pdf/0_HZU3S7CF/9)
            - [4.3 Drivers of the connectedness between electricity and artificial intelligence markets](zotero://open-pdf/0_HZU3S7CF/10)
                - [4.3.1 Implication for electricity market crisis](zotero://open-pdf/0_HZU3S7CF/11)
            - [4.4 Robustness checks](zotero://open-pdf/0_HZU3S7CF/11)
        - [5 Concluding remarks and implication for policy](zotero://open-pdf/0_HZU3S7CF/12)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_HZU3S7CF/12)
        - [Acknowledgements](zotero://open-pdf/0_HZU3S7CF/12)
        - [Appendix A Appendix](zotero://open-pdf/0_HZU3S7CF/13)
        - [Appendix B Supplementary data](zotero://open-pdf/0_HZU3S7CF/15)
        - [References](zotero://open-pdf/0_HZU3S7CF/15)
        
    - 1-s2.0-S0140988324007254-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_TI6LAH6U/1)
        - [2 Literature review](zotero://open-pdf/0_TI6LAH6U/4)
            - [2.1 Intersection of AI, big data, and quantum computing](zotero://open-pdf/0_TI6LAH6U/4)
            - [2.2 AI, big data, quantum computing, and energy market](zotero://open-pdf/0_TI6LAH6U/6)
        - [3 Methodology and data](zotero://open-pdf/0_TI6LAH6U/10)
            - [3.1 Time-varying parameter vector autoregressive (TVP-VAR) frequency connectedness approach](zotero://open-pdf/0_TI6LAH6U/11)
            - [3.2 Long short-term memory (LSTM) neural network based TVP-VAR](zotero://open-pdf/0_TI6LAH6U/13)
            - [3.3 Data](zotero://open-pdf/0_TI6LAH6U/15)
        - [4 Results](zotero://open-pdf/0_TI6LAH6U/16)
        - [5 Conclusion](zotero://open-pdf/0_TI6LAH6U/20)
            - [5.1 Theoretical contribution](zotero://open-pdf/0_TI6LAH6U/21)
            - [5.2 Practical implications](zotero://open-pdf/0_TI6LAH6U/21)
            - [5.3 Limitations and future research](zotero://open-pdf/0_TI6LAH6U/21)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_TI6LAH6U/21)
        - [Declaration of competing interest](zotero://open-pdf/0_TI6LAH6U/21)
        - [Acknowledgements](zotero://open-pdf/0_TI6LAH6U/21)
        - [Appendix A Supplementary data](zotero://open-pdf/0_TI6LAH6U/21)
        - [References](zotero://open-pdf/0_TI6LAH6U/21)
        
    - 1-s2.0-S0140988324007941-mainext.pdf
        
        **Contents**
        
        - [Cross-quantile risk assessment: The interplay of crude oil, artificial intelligence, clean tech, and other markets](zotero://open-pdf/0_TQUISXBC/1)
            - [1 Introduction](zotero://open-pdf/0_TQUISXBC/1)
            - [2 Literature review](zotero://open-pdf/0_TQUISXBC/3)
                - [2.1 Review of the extant literature](zotero://open-pdf/0_TQUISXBC/3)
                - [2.2 Theoretical integration and hypotheses](zotero://open-pdf/0_TQUISXBC/4)
            - [3 Data and methodology](zotero://open-pdf/0_TQUISXBC/5)
                - [3.1 Data](zotero://open-pdf/0_TQUISXBC/5)
                - [3.2 Methodology](zotero://open-pdf/0_TQUISXBC/5)
            - [4 Empirical findings and discussion](zotero://open-pdf/0_TQUISXBC/7)
            - [5 Conclusion](zotero://open-pdf/0_TQUISXBC/11)
            - [CRediT authorship contribution statement](zotero://open-pdf/0_TQUISXBC/12)
            - [Declaration of competing interest](zotero://open-pdf/0_TQUISXBC/12)
            - [Acknowledgements](zotero://open-pdf/0_TQUISXBC/12)
            - [Appendix A Appendix](zotero://open-pdf/0_TQUISXBC/12)
            - [Appendix B Supplementary data](zotero://open-pdf/0_TQUISXBC/13)
            - [References](zotero://open-pdf/0_TQUISXBC/13)
        - [Update](zotero://open-pdf/0_TQUISXBC/15)
            - [Corrigendum to “Cross-quantile risk assessment: The interplay of crude oil, artificial intelligence, clean tech, and other ...](zotero://open-pdf/0_TQUISXBC/1)
        
    - 1-s2.0-S0140988324007977-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_NTUSZF5B/1)
        - [2 Literature review and hypothesis development](zotero://open-pdf/0_NTUSZF5B/2)
            - [2.1 Climate policy uncertainty and energy firms’ investments](zotero://open-pdf/0_NTUSZF5B/2)
            - [2.2 AI, climate policy uncertainty, and energy firms’ investments](zotero://open-pdf/0_NTUSZF5B/3)
        - [3 Research design](zotero://open-pdf/0_NTUSZF5B/4)
            - [3.1 Model specification](zotero://open-pdf/0_NTUSZF5B/4)
            - [3.2 Sample selection and data sources](zotero://open-pdf/0_NTUSZF5B/4)
            - [3.3 Variables](zotero://open-pdf/0_NTUSZF5B/4)
                - [3.3.1 Dependent variable: climate policy uncertainty (CPU)](zotero://open-pdf/0_NTUSZF5B/4)
                - [3.3.2 Independent variable: energy firms’ investment (Inv)](zotero://open-pdf/0_NTUSZF5B/4)
                - [3.3.3 Key variable: degree of AI adoption (AI)](zotero://open-pdf/0_NTUSZF5B/5)
                - [3.3.4 Control variables](zotero://open-pdf/0_NTUSZF5B/5)
        - [4 Empirical results](zotero://open-pdf/0_NTUSZF5B/5)
            - [4.1 Summary statistics](zotero://open-pdf/0_NTUSZF5B/5)
            - [4.2 Baseline results: climate policy uncertainty and energy firms’ investment](zotero://open-pdf/0_NTUSZF5B/6)
            - [4.3 Heterogeneity analysis](zotero://open-pdf/0_NTUSZF5B/8)
                - [4.3.1 Heterogeneity analysis based on firm characteristics](zotero://open-pdf/0_NTUSZF5B/8)
                - [4.3.2 Heterogeneity analysis based on regional characteristics](zotero://open-pdf/0_NTUSZF5B/9)
            - [4.4 Leveraging AI to address climate policy uncertainty](zotero://open-pdf/0_NTUSZF5B/10)
                - [4.4.1 Mechanism analysis: mitigating the customer concentration risk](zotero://open-pdf/0_NTUSZF5B/10)
                - [4.4.2 Mechanism analysis: enhancing green patent commercialization](zotero://open-pdf/0_NTUSZF5B/11)
            - [4.5 Moderating effect](zotero://open-pdf/0_NTUSZF5B/11)
            - [4.6 Robustness tests](zotero://open-pdf/0_NTUSZF5B/12)
                - [4.6.1 Alternative proxy and sample](zotero://open-pdf/0_NTUSZF5B/12)
                - [4.6.2 Additional controls for potential confounding factors](zotero://open-pdf/0_NTUSZF5B/12)
                - [4.6.3 Alternative model](zotero://open-pdf/0_NTUSZF5B/13)
            - [4.7 Endogeneity issues](zotero://open-pdf/0_NTUSZF5B/13)
        - [5 Conclusions and implications](zotero://open-pdf/0_NTUSZF5B/14)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_NTUSZF5B/15)
        - [Declaration of competing interest](zotero://open-pdf/0_NTUSZF5B/15)
        - [Acknowledgements](zotero://open-pdf/0_NTUSZF5B/15)
        - [Appendix A Appendix](zotero://open-pdf/0_NTUSZF5B/15)
            - [A.1 Definition of variables](zotero://open-pdf/0_NTUSZF5B/15)
            - [A.2 Variance Inflation Factor (VIF) analysis](zotero://open-pdf/0_NTUSZF5B/16)
            - [A.3 The regression results with the expanded sample up to 2023](zotero://open-pdf/0_NTUSZF5B/16)
        - [Appendix B Supplementary data](zotero://open-pdf/0_NTUSZF5B/16)
        - [References](zotero://open-pdf/0_NTUSZF5B/17)
        
    - 1-s2.0-S0140988324008211-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_QK4J7ZVK/1)
        - [2 Related literature](zotero://open-pdf/0_QK4J7ZVK/2)
        - [3 Data and methodology](zotero://open-pdf/0_QK4J7ZVK/3)
            - [3.1 Data and variables](zotero://open-pdf/0_QK4J7ZVK/3)
            - [3.2 Methodology](zotero://open-pdf/0_QK4J7ZVK/4)
                - [3.2.1 LASSO regression](zotero://open-pdf/0_QK4J7ZVK/4)
                - [3.2.2 Elastic net regression](zotero://open-pdf/0_QK4J7ZVK/4)
                - [3.2.3 K-nearest neighbors regression](zotero://open-pdf/0_QK4J7ZVK/4)
                - [3.2.4 Light gradient-boosting machine](zotero://open-pdf/0_QK4J7ZVK/4)
                - [3.2.5 EXtreme gradient boosting regression](zotero://open-pdf/0_QK4J7ZVK/6)
                - [3.2.6 Extra trees regression](zotero://open-pdf/0_QK4J7ZVK/7)
                - [3.2.7 Explainable artificial intelligence method](zotero://open-pdf/0_QK4J7ZVK/7)
        - [4 Experiments and robustness](zotero://open-pdf/0_QK4J7ZVK/7)
            - [4.1 Model predictive power](zotero://open-pdf/0_QK4J7ZVK/7)
            - [4.2 Model interpretability](zotero://open-pdf/0_QK4J7ZVK/8)
            - [4.3 Robustness check](zotero://open-pdf/0_QK4J7ZVK/9)
        - [5 Conclusion and policy implications](zotero://open-pdf/0_QK4J7ZVK/10)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_QK4J7ZVK/11)
        - [Declaration of competing interest](zotero://open-pdf/0_QK4J7ZVK/11)
        - [Appendix A Supplementary data](zotero://open-pdf/0_QK4J7ZVK/11)
        - [References](zotero://open-pdf/0_QK4J7ZVK/11)
        
    - 1-s2.0-S0140988324008454-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_UKAJN64R/1)
        - [2 Literature review](zotero://open-pdf/0_UKAJN64R/2)
        - [3 Theoretical analysis and research hypotheses](zotero://open-pdf/0_UKAJN64R/3)
            - [3.1 Direct impact of AI on EEP](zotero://open-pdf/0_UKAJN64R/3)
            - [3.2 Indirect impact of AI on EEP](zotero://open-pdf/0_UKAJN64R/4)
                - [3.2.1 AI, urban green innovation, and EEP](zotero://open-pdf/0_UKAJN64R/4)
                - [3.2.2 AI, human capital, and EEP](zotero://open-pdf/0_UKAJN64R/4)
                - [3.2.3 AI, energy consumption structure, EEP](zotero://open-pdf/0_UKAJN64R/4)
            - [3.3 The spatial and rebound effects of AI](zotero://open-pdf/0_UKAJN64R/5)
        - [4 Model setting, variable selection, and data explanation](zotero://open-pdf/0_UKAJN64R/5)
            - [4.1 Model setting](zotero://open-pdf/0_UKAJN64R/5)
                - [4.1.1 Benchmark regression model](zotero://open-pdf/0_UKAJN64R/5)
                - [4.1.2 Multi-period difference-in-differences (DID) model](zotero://open-pdf/0_UKAJN64R/5)
                - [4.1.3 Mechanism verification model](zotero://open-pdf/0_UKAJN64R/5)
                - [4.1.4 Spatial econometric model](zotero://open-pdf/0_UKAJN64R/6)
            - [4.2 Variable selection](zotero://open-pdf/0_UKAJN64R/6)
                - [4.2.1 EEP](zotero://open-pdf/0_UKAJN64R/6)
                - [4.2.2 AI](zotero://open-pdf/0_UKAJN64R/7)
                - [4.2.3 Control variables](zotero://open-pdf/0_UKAJN64R/8)
            - [4.3 Data explanation](zotero://open-pdf/0_UKAJN64R/8)
        - [5 Results and discussion](zotero://open-pdf/0_UKAJN64R/8)
            - [5.1 Benchmark regression](zotero://open-pdf/0_UKAJN64R/8)
            - [5.2 Effect decomposition](zotero://open-pdf/0_UKAJN64R/8)
            - [5.3 Endogeneity treatment](zotero://open-pdf/0_UKAJN64R/8)
            - [5.4 Robustness testing](zotero://open-pdf/0_UKAJN64R/9)
                - [5.4.1 Substitution of the core variable measurement method](zotero://open-pdf/0_UKAJN64R/9)
                - [5.4.2 Control of other forms of fixed effects](zotero://open-pdf/0_UKAJN64R/10)
                - [5.4.3 Sample of subinterval model estimation](zotero://open-pdf/0_UKAJN64R/10)
                - [5.4.4 Core explanatory variables lagged by one period](zotero://open-pdf/0_UKAJN64R/10)
                - [5.4.5 Testing of exogenous policy shocks](zotero://open-pdf/0_UKAJN64R/10)
            - [5.5 Impact mechanism](zotero://open-pdf/0_UKAJN64R/11)
                - [5.5.1 Enhancing green innovation in cities](zotero://open-pdf/0_UKAJN64R/11)
                - [5.5.2 Optimizing human capital structure](zotero://open-pdf/0_UKAJN64R/11)
                - [5.5.3 Improving the structure of energy consumption](zotero://open-pdf/0_UKAJN64R/11)
            - [5.6 Heterogeneity analysis](zotero://open-pdf/0_UKAJN64R/11)
                - [5.6.1 Classification by geographical location](zotero://open-pdf/0_UKAJN64R/11)
                - [5.6.2 Classification by city size](zotero://open-pdf/0_UKAJN64R/11)
                - [5.6.3 Classification by resource endowment](zotero://open-pdf/0_UKAJN64R/12)
        - [6 Further discussion: Spatial effects and energy rebound effects](zotero://open-pdf/0_UKAJN64R/12)
            - [6.1 Perspective based on spatial effects](zotero://open-pdf/0_UKAJN64R/12)
            - [6.2 Perspectives based on energy rebound effects](zotero://open-pdf/0_UKAJN64R/13)
        - [7 Research conclusions and policy implications](zotero://open-pdf/0_UKAJN64R/13)
        - [Ethical approval](zotero://open-pdf/0_UKAJN64R/14)
        - [Consent to participate](zotero://open-pdf/0_UKAJN64R/14)
        - [Consent to publish](zotero://open-pdf/0_UKAJN64R/14)
        - [Authors’ contributions statement](zotero://open-pdf/0_UKAJN64R/14)
        - [Funding](zotero://open-pdf/0_UKAJN64R/14)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_UKAJN64R/14)
        - [Declaration of competing interest](zotero://open-pdf/0_UKAJN64R/14)
        - [Appendix A Supplementary data](zotero://open-pdf/0_UKAJN64R/14)
        - [References](zotero://open-pdf/0_UKAJN64R/14)
        
    - 1-s2.0-S0140988324008582-main.pdf
    - 1-s2.0-S0301479723027111-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_9BK8VMQG/1)
        - [2 Literature review](zotero://open-pdf/0_9BK8VMQG/2)
        - [3 Mechanism and Hypothesis](zotero://open-pdf/0_9BK8VMQG/3)
            - [3.1 Impact of artificial intelligence on technical progress](zotero://open-pdf/0_9BK8VMQG/3)
            - [3.2 Effect of artificial intelligence on scale efficiency](zotero://open-pdf/0_9BK8VMQG/3)
            - [3.3 Effect of artificial intelligence on resource allocation efficiency](zotero://open-pdf/0_9BK8VMQG/3)
            - [3.4 Total effects impact of artificial intelligence on GTFP](zotero://open-pdf/0_9BK8VMQG/3)
        - [4 Methodology and data](zotero://open-pdf/0_9BK8VMQG/4)
            - [4.1 Basic model](zotero://open-pdf/0_9BK8VMQG/4)
            - [4.2 Data](zotero://open-pdf/0_9BK8VMQG/4)
                - [4.2.1 Green total factor productivity](zotero://open-pdf/0_9BK8VMQG/4)
                - [4.2.2 Artificial intelligence](zotero://open-pdf/0_9BK8VMQG/5)
                - [4.2.3 Control variables](zotero://open-pdf/0_9BK8VMQG/6)
                - [4.2.4 Data source and description](zotero://open-pdf/0_9BK8VMQG/7)
        - [5 Empirical results and discussion](zotero://open-pdf/0_9BK8VMQG/8)
            - [5.1 Green total factor productivity (GTFP)](zotero://open-pdf/0_9BK8VMQG/8)
            - [5.2 Artificial Intelligence(AI)](zotero://open-pdf/0_9BK8VMQG/8)
            - [5.3 Benchmark regression](zotero://open-pdf/0_9BK8VMQG/8)
            - [5.4 Robustness tests](zotero://open-pdf/0_9BK8VMQG/10)
            - [5.5 Heterogeneity tests](zotero://open-pdf/0_9BK8VMQG/12)
            - [5.6 Trend Prediction](zotero://open-pdf/0_9BK8VMQG/13)
        - [6 Conclusion and policy implications](zotero://open-pdf/0_9BK8VMQG/14)
            - [6.1 Conclusions](zotero://open-pdf/0_9BK8VMQG/14)
            - [6.2 Policy implications](zotero://open-pdf/0_9BK8VMQG/14)
            - [6.3 Future perspectives](zotero://open-pdf/0_9BK8VMQG/16)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_9BK8VMQG/16)
        - [Declaration of competing interest](zotero://open-pdf/0_9BK8VMQG/16)
        - [Data availability](zotero://open-pdf/0_9BK8VMQG/16)
        - [Acknowledgement](zotero://open-pdf/0_9BK8VMQG/17)
        - [References](zotero://open-pdf/0_9BK8VMQG/17)
        
    - 1-s2.0-S0301479724026653-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_EQXSSCQ6/1)
        - [2 Literature review &amp; theoretical notations](zotero://open-pdf/0_EQXSSCQ6/3)
            - [2.1 Literature review](zotero://open-pdf/0_EQXSSCQ6/3)
            - [2.2 Theoretical notation](zotero://open-pdf/0_EQXSSCQ6/3)
        - [3 Methodology](zotero://open-pdf/0_EQXSSCQ6/4)
            - [3.1 Model setup](zotero://open-pdf/0_EQXSSCQ6/4)
            - [3.2 Variables](zotero://open-pdf/0_EQXSSCQ6/4)
            - [3.3 Data &amp; stylized facts](zotero://open-pdf/0_EQXSSCQ6/5)
        - [4 Empirical results](zotero://open-pdf/0_EQXSSCQ6/6)
            - [4.1 Baseline validation](zotero://open-pdf/0_EQXSSCQ6/6)
            - [4.2 Robustness validation](zotero://open-pdf/0_EQXSSCQ6/7)
        - [5 Mechanism analysis](zotero://open-pdf/0_EQXSSCQ6/8)
            - [5.1 Mediating effect](zotero://open-pdf/0_EQXSSCQ6/8)
            - [5.2 Moderating effect](zotero://open-pdf/0_EQXSSCQ6/10)
        - [6 Conclusion and policy implications](zotero://open-pdf/0_EQXSSCQ6/12)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_EQXSSCQ6/12)
        - [Declaration of competing interest](zotero://open-pdf/0_EQXSSCQ6/13)
        - [Data availability](zotero://open-pdf/0_EQXSSCQ6/13)
        - [References](zotero://open-pdf/0_EQXSSCQ6/13)
        
    - 1-s2.0-S0306261924004641-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_KTS5P5AD/2)
        - [2 Literature review and research hypothesis](zotero://open-pdf/0_KTS5P5AD/4)
            - [2.1 Artificial intelligence and clean energy transition](zotero://open-pdf/0_KTS5P5AD/4)
            - [2.2 Artificial intelligence, energy intensity, and clean energy transition](zotero://open-pdf/0_KTS5P5AD/6)
            - [2.3 Artificial intelligence, government investment in science, and clean energy transition](zotero://open-pdf/0_KTS5P5AD/6)
            - [2.4 Artificial intelligence, informatization degree, and clean energy transition](zotero://open-pdf/0_KTS5P5AD/6)
        - [3 Methodology](zotero://open-pdf/0_KTS5P5AD/6)
            - [3.1 Benchmark model](zotero://open-pdf/0_KTS5P5AD/6)
            - [3.2 Instrumental variable two-stage least squares (IV-2SLS)](zotero://open-pdf/0_KTS5P5AD/7)
            - [3.3 Moderating effect model](zotero://open-pdf/0_KTS5P5AD/7)
        - [4 Data](zotero://open-pdf/0_KTS5P5AD/7)
            - [4.1 Variable selection](zotero://open-pdf/0_KTS5P5AD/7)
                - [4.1.1 Dependent variable](zotero://open-pdf/0_KTS5P5AD/7)
                - [4.1.2 Core explanatory variables](zotero://open-pdf/0_KTS5P5AD/7)
                - [4.1.3 Control variables](zotero://open-pdf/0_KTS5P5AD/8)
                - [4.1.4 Moderating variables](zotero://open-pdf/0_KTS5P5AD/8)
            - [4.2 Sample and data](zotero://open-pdf/0_KTS5P5AD/8)
        - [5 Analysis of empirical results](zotero://open-pdf/0_KTS5P5AD/9)
            - [5.1 Benchmark regression analysis](zotero://open-pdf/0_KTS5P5AD/9)
            - [5.2 Robustness analysis](zotero://open-pdf/0_KTS5P5AD/10)
                - [5.2.1 IV - 2SLS](zotero://open-pdf/0_KTS5P5AD/10)
                - [5.2.2 Alternate independent variables](zotero://open-pdf/0_KTS5P5AD/11)
                - [5.2.3 Alternate dependent variable](zotero://open-pdf/0_KTS5P5AD/11)
                - [5.2.4 Winsorizing the variables](zotero://open-pdf/0_KTS5P5AD/11)
            - [5.3 Heterogeneity analysis](zotero://open-pdf/0_KTS5P5AD/11)
        - [6 Analysis of the moderating effect of the U-shaped relationship](zotero://open-pdf/0_KTS5P5AD/12)
        - [7 Conclusion and policy implications](zotero://open-pdf/0_KTS5P5AD/13)
            - [7.1 Conclusion](zotero://open-pdf/0_KTS5P5AD/13)
            - [7.2 Policy implications](zotero://open-pdf/0_KTS5P5AD/14)
        - [Ethical approval](zotero://open-pdf/0_KTS5P5AD/14)
        - [Funding](zotero://open-pdf/0_KTS5P5AD/14)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_KTS5P5AD/14)
        - [Declaration of competing interest](zotero://open-pdf/0_KTS5P5AD/14)
        - [Data availability](zotero://open-pdf/0_KTS5P5AD/14)
        - [References](zotero://open-pdf/0_KTS5P5AD/14)
        
    - 1-s2.0-S0313592624001723-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_7YKPTBAD/1)
        - [2 Literature review](zotero://open-pdf/0_7YKPTBAD/2)
        - [3 Theoretical analysis and hypothesis](zotero://open-pdf/0_7YKPTBAD/4)
            - [3.1 Artificial intelligence and energy consumption](zotero://open-pdf/0_7YKPTBAD/4)
            - [3.2 Technological innovation](zotero://open-pdf/0_7YKPTBAD/4)
            - [3.3 Digital transformation](zotero://open-pdf/0_7YKPTBAD/4)
        - [4 Methodology](zotero://open-pdf/0_7YKPTBAD/4)
            - [4.1 Sources of data](zotero://open-pdf/0_7YKPTBAD/4)
            - [4.2 Model](zotero://open-pdf/0_7YKPTBAD/5)
            - [4.3 Variables](zotero://open-pdf/0_7YKPTBAD/5)
                - [4.3.1 Corporate energy consumption (lnFEnergy)](zotero://open-pdf/0_7YKPTBAD/5)
                - [4.3.2 Artificial intelligence application (AIA)](zotero://open-pdf/0_7YKPTBAD/5)
                    - [4.3.2.1 Control variables](zotero://open-pdf/0_7YKPTBAD/6)
        - [5 Empirical analysis](zotero://open-pdf/0_7YKPTBAD/6)
            - [5.1 Descriptive statistics](zotero://open-pdf/0_7YKPTBAD/6)
            - [5.2 Baseline results](zotero://open-pdf/0_7YKPTBAD/6)
            - [5.3 Robustness tests](zotero://open-pdf/0_7YKPTBAD/6)
                - [5.3.1 IV-2SLS method](zotero://open-pdf/0_7YKPTBAD/6)
                - [5.3.2 Heckman’s two-stage model](zotero://open-pdf/0_7YKPTBAD/8)
                - [5.3.3 PSM test](zotero://open-pdf/0_7YKPTBAD/8)
                - [5.3.4 Placebo test](zotero://open-pdf/0_7YKPTBAD/8)
                - [5.3.5 Incorporating industry fixed effects](zotero://open-pdf/0_7YKPTBAD/8)
                - [5.3.6 Altering the level of clustering](zotero://open-pdf/0_7YKPTBAD/9)
                - [5.3.7 Balanced panel data](zotero://open-pdf/0_7YKPTBAD/9)
        - [6 Further analysis](zotero://open-pdf/0_7YKPTBAD/9)
            - [6.1 Mechanism analysis](zotero://open-pdf/0_7YKPTBAD/9)
                - [6.1.1 Technological innovation](zotero://open-pdf/0_7YKPTBAD/10)
                - [6.1.2 Digital transformation](zotero://open-pdf/0_7YKPTBAD/10)
            - [6.2 Heterogeneity analysis](zotero://open-pdf/0_7YKPTBAD/11)
                - [6.2.1 Ownership type of corporations](zotero://open-pdf/0_7YKPTBAD/11)
                - [6.2.2 High-tech or non-high-tech enterprises](zotero://open-pdf/0_7YKPTBAD/11)
                - [6.2.3 Heavily or non-heavily polluting industries](zotero://open-pdf/0_7YKPTBAD/11)
        - [7 Conclusion and implications](zotero://open-pdf/0_7YKPTBAD/11)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_7YKPTBAD/12)
        - [Declaration of competing interest](zotero://open-pdf/0_7YKPTBAD/12)
        - [Acknowledgments](zotero://open-pdf/0_7YKPTBAD/12)
        - [References](zotero://open-pdf/0_7YKPTBAD/12)
        
    - 1-s2.0-S0313592624003333-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_GTK7WB4H/1)
        - [2 Literature review and research hypotheses](zotero://open-pdf/0_GTK7WB4H/3)
            - [2.1 Studies on AI and energy vulnerability](zotero://open-pdf/0_GTK7WB4H/3)
                - [2.1.1 The effect of AI on the energy system](zotero://open-pdf/0_GTK7WB4H/3)
                - [2.1.2 Impact factors of energy vulnerability](zotero://open-pdf/0_GTK7WB4H/3)
            - [2.2 Research hypotheses](zotero://open-pdf/0_GTK7WB4H/3)
                - [2.2.1 AI-EVI nexus](zotero://open-pdf/0_GTK7WB4H/3)
                - [2.2.2 AI, financial development, and EVI](zotero://open-pdf/0_GTK7WB4H/4)
                - [2.2.3 AI, technological progress, and EVI](zotero://open-pdf/0_GTK7WB4H/4)
        - [3 Methodology and data](zotero://open-pdf/0_GTK7WB4H/5)
            - [3.1 The evaluation of EVI](zotero://open-pdf/0_GTK7WB4H/5)
            - [3.2 Economic model](zotero://open-pdf/0_GTK7WB4H/6)
            - [3.3 Variables](zotero://open-pdf/0_GTK7WB4H/6)
                - [3.3.1 Dependent variable](zotero://open-pdf/0_GTK7WB4H/6)
                - [3.3.2 Key independent variable](zotero://open-pdf/0_GTK7WB4H/6)
                - [3.3.3 Control variables](zotero://open-pdf/0_GTK7WB4H/6)
                - [3.3.4 Data sources and sample selection](zotero://open-pdf/0_GTK7WB4H/6)
        - [4 Empirical analysis](zotero://open-pdf/0_GTK7WB4H/7)
            - [4.1 Benchmark results](zotero://open-pdf/0_GTK7WB4H/7)
            - [4.2 Robustness test](zotero://open-pdf/0_GTK7WB4H/7)
                - [4.2.1 Variable substitution](zotero://open-pdf/0_GTK7WB4H/7)
                - [4.2.2 Eliminating the effects of outliers](zotero://open-pdf/0_GTK7WB4H/7)
                - [4.2.3 Endogenous issues](zotero://open-pdf/0_GTK7WB4H/7)
            - [4.3 Heterogeneity analysis](zotero://open-pdf/0_GTK7WB4H/7)
                - [4.3.1 The effect of Industry 4.0](zotero://open-pdf/0_GTK7WB4H/7)
                - [4.3.2 The effect of the financial crisis](zotero://open-pdf/0_GTK7WB4H/9)
                - [4.3.3 The effect of income level disparity](zotero://open-pdf/0_GTK7WB4H/9)
                - [4.3.4 The effect of industrial development disparity](zotero://open-pdf/0_GTK7WB4H/9)
        - [5 Further discussions](zotero://open-pdf/0_GTK7WB4H/9)
            - [5.1 The mechanism effects model](zotero://open-pdf/0_GTK7WB4H/9)
            - [5.2 The role of technological progress](zotero://open-pdf/0_GTK7WB4H/10)
            - [5.3 The role of financial development](zotero://open-pdf/0_GTK7WB4H/10)
        - [6 Conclusions and policy suggestions](zotero://open-pdf/0_GTK7WB4H/10)
            - [6.1 Conclusions](zotero://open-pdf/0_GTK7WB4H/10)
            - [6.2 Policy recommendations](zotero://open-pdf/0_GTK7WB4H/10)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_GTK7WB4H/11)
        - [Declaration of Competing Interest](zotero://open-pdf/0_GTK7WB4H/11)
        - [Acknowledgments](zotero://open-pdf/0_GTK7WB4H/11)
        - [References](zotero://open-pdf/0_GTK7WB4H/11)
        
    - 1-s2.0-S0360544224032730-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_TYR3NE9Z/1)
        - [2 Literature review](zotero://open-pdf/0_TYR3NE9Z/2)
        - [3 Theoretical analysis and research hypotheses](zotero://open-pdf/0_TYR3NE9Z/3)
            - [3.1 Pathways of AI’s impact on urban EE](zotero://open-pdf/0_TYR3NE9Z/3)
            - [3.2 Nonlinear impact of AI on urban EE](zotero://open-pdf/0_TYR3NE9Z/4)
            - [3.3 The moderating role of ISU](zotero://open-pdf/0_TYR3NE9Z/4)
        - [4 Research design and data](zotero://open-pdf/0_TYR3NE9Z/5)
            - [4.1 Research methodology](zotero://open-pdf/0_TYR3NE9Z/5)
                - [4.1.1 Spatial econometric model](zotero://open-pdf/0_TYR3NE9Z/5)
                - [4.1.2 Spatial autocorrelation test](zotero://open-pdf/0_TYR3NE9Z/5)
                - [4.1.3 Super-efficient SBM model](zotero://open-pdf/0_TYR3NE9Z/5)
            - [4.2 Variables and data sources](zotero://open-pdf/0_TYR3NE9Z/5)
                - [4.2.1 Dependent variable](zotero://open-pdf/0_TYR3NE9Z/5)
                - [4.2.2 Core explanatory variable](zotero://open-pdf/0_TYR3NE9Z/6)
                - [4.2.3 Other variables](zotero://open-pdf/0_TYR3NE9Z/6)
                - [4.2.4 Descriptive analysis and collinearity test](zotero://open-pdf/0_TYR3NE9Z/6)
                - [4.2.5 Data interpretation](zotero://open-pdf/0_TYR3NE9Z/7)
        - [5 Results and analysis](zotero://open-pdf/0_TYR3NE9Z/7)
            - [5.1 Spatial econometric analysis of AI’s impact on EE](zotero://open-pdf/0_TYR3NE9Z/7)
                - [5.1.1 Test for spatial correlation](zotero://open-pdf/0_TYR3NE9Z/7)
                - [5.1.2 Selection of spatial econometric models](zotero://open-pdf/0_TYR3NE9Z/7)
                - [5.1.3 Analysis of SDM regression results](zotero://open-pdf/0_TYR3NE9Z/8)
                - [5.1.4 Decomposition of spatial effects](zotero://open-pdf/0_TYR3NE9Z/9)
                - [5.1.5 Robustness test](zotero://open-pdf/0_TYR3NE9Z/10)
            - [5.2 The moderating effect of industrial structure upgrading](zotero://open-pdf/0_TYR3NE9Z/11)
            - [5.3 Discussion](zotero://open-pdf/0_TYR3NE9Z/11)
        - [6 Conclusions and policy recommendations](zotero://open-pdf/0_TYR3NE9Z/12)
            - [6.1 Conclusions](zotero://open-pdf/0_TYR3NE9Z/12)
            - [6.2 Policy recommendations](zotero://open-pdf/0_TYR3NE9Z/12)
            - [6.3 Limitations and future research](zotero://open-pdf/0_TYR3NE9Z/12)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_TYR3NE9Z/12)
        - [Declaration of competing interest](zotero://open-pdf/0_TYR3NE9Z/12)
        - [Acknowledgments](zotero://open-pdf/0_TYR3NE9Z/12)
        - [datalink6](zotero://open-pdf/0_TYR3NE9Z/12)
        - [References](zotero://open-pdf/0_TYR3NE9Z/12)
        
    - 1-s2.0-S0959652624007455-main (1).pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_IM6DF2NZ/1)
        - [2 Literature review](zotero://open-pdf/0_IM6DF2NZ/2)
            - [2.1 The impact of AI on energy and environment](zotero://open-pdf/0_IM6DF2NZ/2)
            - [2.2 The impact of trade openness on energy and environment](zotero://open-pdf/0_IM6DF2NZ/3)
        - [3 Mechanism analysis and research hypotheses](zotero://open-pdf/0_IM6DF2NZ/4)
            - [3.1 Direct impact of AI on carbon emissions and energy transition](zotero://open-pdf/0_IM6DF2NZ/4)
            - [3.2 Indirect impact of AI on carbon emissions and energy transition](zotero://open-pdf/0_IM6DF2NZ/4)
            - [3.3 Non-linear impact of AI on carbon emissions and energy transition](zotero://open-pdf/0_IM6DF2NZ/4)
        - [4 Methods and data](zotero://open-pdf/0_IM6DF2NZ/4)
            - [4.1 Benchmark model](zotero://open-pdf/0_IM6DF2NZ/4)
            - [4.2 Mediation model](zotero://open-pdf/0_IM6DF2NZ/5)
            - [4.3 Panel threshold regression model](zotero://open-pdf/0_IM6DF2NZ/5)
            - [4.4 Variables and data sources](zotero://open-pdf/0_IM6DF2NZ/7)
                - [4.4.1 Independent variable](zotero://open-pdf/0_IM6DF2NZ/7)
                - [4.4.2 Dependent variable](zotero://open-pdf/0_IM6DF2NZ/7)
                - [4.4.3 Mediating variable and threshold variable](zotero://open-pdf/0_IM6DF2NZ/8)
                - [4.4.4 Control variable](zotero://open-pdf/0_IM6DF2NZ/9)
                - [4.4.5 Variable descriptive statistics and cointegration relationship](zotero://open-pdf/0_IM6DF2NZ/9)
        - [5 Results](zotero://open-pdf/0_IM6DF2NZ/9)
            - [5.1 Benchmark regression results](zotero://open-pdf/0_IM6DF2NZ/9)
            - [5.2 Mediating effect results](zotero://open-pdf/0_IM6DF2NZ/10)
            - [5.3 Robustness check](zotero://open-pdf/0_IM6DF2NZ/10)
            - [5.4 Endogeneity treatment](zotero://open-pdf/0_IM6DF2NZ/10)
            - [5.5 Panel threshold regression (PTR) model results](zotero://open-pdf/0_IM6DF2NZ/10)
            - [5.6 Heterogeneous effect results](zotero://open-pdf/0_IM6DF2NZ/13)
                - [5.6.1 Heterogeneous effect results based on different income groups](zotero://open-pdf/0_IM6DF2NZ/13)
                - [5.6.2 Heterogeneous effect results based on different AI development levels](zotero://open-pdf/0_IM6DF2NZ/15)
        - [6 Discussion](zotero://open-pdf/0_IM6DF2NZ/16)
        - [7 Conclusion and policy implications](zotero://open-pdf/0_IM6DF2NZ/18)
            - [7.1 Conclusion](zotero://open-pdf/0_IM6DF2NZ/18)
            - [7.2 Policy implications](zotero://open-pdf/0_IM6DF2NZ/18)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_IM6DF2NZ/19)
        - [Declaration of competing interest](zotero://open-pdf/0_IM6DF2NZ/19)
        - [Data availability](zotero://open-pdf/0_IM6DF2NZ/19)
        - [Acknowledgement](zotero://open-pdf/0_IM6DF2NZ/19)
        - [Appendix A Acknowledgement](zotero://open-pdf/0_IM6DF2NZ/19)
        - [Appendix B Acknowledgement](zotero://open-pdf/0_IM6DF2NZ/32)
        - [References](zotero://open-pdf/0_IM6DF2NZ/33)
        
    - 1-s2.0-S0959652624007455-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_9NDFAL6I/1)
        - [2 Literature review](zotero://open-pdf/0_9NDFAL6I/2)
            - [2.1 The impact of AI on energy and environment](zotero://open-pdf/0_9NDFAL6I/2)
            - [2.2 The impact of trade openness on energy and environment](zotero://open-pdf/0_9NDFAL6I/3)
        - [3 Mechanism analysis and research hypotheses](zotero://open-pdf/0_9NDFAL6I/4)
            - [3.1 Direct impact of AI on carbon emissions and energy transition](zotero://open-pdf/0_9NDFAL6I/4)
            - [3.2 Indirect impact of AI on carbon emissions and energy transition](zotero://open-pdf/0_9NDFAL6I/4)
            - [3.3 Non-linear impact of AI on carbon emissions and energy transition](zotero://open-pdf/0_9NDFAL6I/4)
        - [4 Methods and data](zotero://open-pdf/0_9NDFAL6I/4)
            - [4.1 Benchmark model](zotero://open-pdf/0_9NDFAL6I/4)
            - [4.2 Mediation model](zotero://open-pdf/0_9NDFAL6I/5)
            - [4.3 Panel threshold regression model](zotero://open-pdf/0_9NDFAL6I/5)
            - [4.4 Variables and data sources](zotero://open-pdf/0_9NDFAL6I/7)
                - [4.4.1 Independent variable](zotero://open-pdf/0_9NDFAL6I/7)
                - [4.4.2 Dependent variable](zotero://open-pdf/0_9NDFAL6I/7)
                - [4.4.3 Mediating variable and threshold variable](zotero://open-pdf/0_9NDFAL6I/8)
                - [4.4.4 Control variable](zotero://open-pdf/0_9NDFAL6I/9)
                - [4.4.5 Variable descriptive statistics and cointegration relationship](zotero://open-pdf/0_9NDFAL6I/9)
        - [5 Results](zotero://open-pdf/0_9NDFAL6I/9)
            - [5.1 Benchmark regression results](zotero://open-pdf/0_9NDFAL6I/9)
            - [5.2 Mediating effect results](zotero://open-pdf/0_9NDFAL6I/10)
            - [5.3 Robustness check](zotero://open-pdf/0_9NDFAL6I/10)
            - [5.4 Endogeneity treatment](zotero://open-pdf/0_9NDFAL6I/10)
            - [5.5 Panel threshold regression (PTR) model results](zotero://open-pdf/0_9NDFAL6I/10)
            - [5.6 Heterogeneous effect results](zotero://open-pdf/0_9NDFAL6I/13)
                - [5.6.1 Heterogeneous effect results based on different income groups](zotero://open-pdf/0_9NDFAL6I/13)
                - [5.6.2 Heterogeneous effect results based on different AI development levels](zotero://open-pdf/0_9NDFAL6I/15)
        - [6 Discussion](zotero://open-pdf/0_9NDFAL6I/16)
        - [7 Conclusion and policy implications](zotero://open-pdf/0_9NDFAL6I/18)
            - [7.1 Conclusion](zotero://open-pdf/0_9NDFAL6I/18)
            - [7.2 Policy implications](zotero://open-pdf/0_9NDFAL6I/18)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_9NDFAL6I/19)
        - [Declaration of competing interest](zotero://open-pdf/0_9NDFAL6I/19)
        - [Data availability](zotero://open-pdf/0_9NDFAL6I/19)
        - [Acknowledgement](zotero://open-pdf/0_9NDFAL6I/19)
        - [Appendix A Acknowledgement](zotero://open-pdf/0_9NDFAL6I/19)
        - [Appendix B Acknowledgement](zotero://open-pdf/0_9NDFAL6I/32)
        - [References](zotero://open-pdf/0_9NDFAL6I/33)
        
    - 1-s2.0-S0959652624008606-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_Q7HDY2LL/1)
            - [1.1 Research objectives](zotero://open-pdf/0_Q7HDY2LL/2)
        - [2 Literature survey](zotero://open-pdf/0_Q7HDY2LL/2)
        - [3 Research problem](zotero://open-pdf/0_Q7HDY2LL/3)
        - [4 Research methodology](zotero://open-pdf/0_Q7HDY2LL/5)
            - [4.1 Research design](zotero://open-pdf/0_Q7HDY2LL/5)
            - [4.2 Collection of data](zotero://open-pdf/0_Q7HDY2LL/5)
            - [4.3 Data source](zotero://open-pdf/0_Q7HDY2LL/5)
            - [4.4 Sample size](zotero://open-pdf/0_Q7HDY2LL/5)
            - [4.5 Questionnaire](zotero://open-pdf/0_Q7HDY2LL/5)
        - [5 Results and analysis](zotero://open-pdf/0_Q7HDY2LL/5)
            - [5.1 Percentage analysis](zotero://open-pdf/0_Q7HDY2LL/5)
            - [5.2 Demographic analysis](zotero://open-pdf/0_Q7HDY2LL/6)
            - [5.3 Descriptive statistics](zotero://open-pdf/0_Q7HDY2LL/8)
            - [5.4 ANOVA analysis](zotero://open-pdf/0_Q7HDY2LL/8)
            - [5.5 Correlation analysis](zotero://open-pdf/0_Q7HDY2LL/8)
            - [5.6 Exploratory factor analysis](zotero://open-pdf/0_Q7HDY2LL/10)
            - [5.7 Research implications](zotero://open-pdf/0_Q7HDY2LL/10)
        - [6 Conclusion and future scope](zotero://open-pdf/0_Q7HDY2LL/11)
        - [Funding statement](zotero://open-pdf/0_Q7HDY2LL/11)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_Q7HDY2LL/11)
        - [Declaration of competing interest](zotero://open-pdf/0_Q7HDY2LL/11)
        - [Data availability](zotero://open-pdf/0_Q7HDY2LL/11)
        - [References](zotero://open-pdf/0_Q7HDY2LL/11)
        
    - 1-s2.0-S1364032122003975-main.pdf
        
        **Contents**
        
        - [1 Introduction](zotero://open-pdf/0_NVYY6WUH/1)
        - [2 Background on quantum computing](zotero://open-pdf/0_NVYY6WUH/3)
        - [3 Quantum AI for renewable and sustainable energy](zotero://open-pdf/0_NVYY6WUH/4)
            - [3.1 Quantum machine learning](zotero://open-pdf/0_NVYY6WUH/4)
                - [3.1.1 Data encoding](zotero://open-pdf/0_NVYY6WUH/4)
                - [3.1.2 Parameterized quantum circuits](zotero://open-pdf/0_NVYY6WUH/4)
            - [3.2 Quantum-enhanced optimization](zotero://open-pdf/0_NVYY6WUH/6)
                - [3.2.1 Binary optimization](zotero://open-pdf/0_NVYY6WUH/6)
                - [3.2.2 Continuous optimization](zotero://open-pdf/0_NVYY6WUH/7)
        - [4 Quantum chemistry for sustainable energy materials](zotero://open-pdf/0_NVYY6WUH/8)
            - [4.1 Variational quantum eigensolver](zotero://open-pdf/0_NVYY6WUH/8)
            - [4.2 Quantum phase estimation](zotero://open-pdf/0_NVYY6WUH/9)
            - [4.3 Quantum AI for quantum chemistry calculations](zotero://open-pdf/0_NVYY6WUH/10)
        - [5 Conclusion](zotero://open-pdf/0_NVYY6WUH/10)
        - [Author contribution](zotero://open-pdf/0_NVYY6WUH/10)
        - [Declaration of competing interest](zotero://open-pdf/0_NVYY6WUH/10)
        - [Acknowledgements](zotero://open-pdf/0_NVYY6WUH/10)
        - [Appendix A Supplementary data](zotero://open-pdf/0_NVYY6WUH/10)
        - [References](zotero://open-pdf/0_NVYY6WUH/10)
        
    - 1-s2.0-S2352484721007757-main.pdf
        
        **Contents**
        
        - [Introduction](zotero://open-pdf/0_ILAZZZEW/1)
        - [Methods of the study](zotero://open-pdf/0_ILAZZZEW/2)
            - [Expert elicitation process](zotero://open-pdf/0_ILAZZZEW/2)
            - [Final analysis](zotero://open-pdf/0_ILAZZZEW/3)
            - [Limitations of the research](zotero://open-pdf/0_ILAZZZEW/3)
        - [Assessment on the impacts of RE utilization toward achieving SDGs](zotero://open-pdf/0_ILAZZZEW/3)
            - [RE utilization and environmental outcomes](zotero://open-pdf/0_ILAZZZEW/6)
            - [RE utilization and social outcomes](zotero://open-pdf/0_ILAZZZEW/8)
            - [RE utilization and economic outcomes](zotero://open-pdf/0_ILAZZZEW/9)
        - [Role of AI in RE utilization](zotero://open-pdf/0_ILAZZZEW/10)
        - [Toward sustainable RE utilization](zotero://open-pdf/0_ILAZZZEW/10)
        - [Conclusion](zotero://open-pdf/0_ILAZZZEW/11)
        - [Code availability](zotero://open-pdf/0_ILAZZZEW/11)
        - [CRediT authorship contribution statement](zotero://open-pdf/0_ILAZZZEW/11)
        - [Declaration of competing interest](zotero://open-pdf/0_ILAZZZEW/11)
        - [Data availability](zotero://open-pdf/0_ILAZZZEW/11)
        - [Acknowledgments](zotero://open-pdf/0_ILAZZZEW/11)
        - [Appendix A. Supplementary data](zotero://open-pdf/0_ILAZZZEW/11)
        - [References](zotero://open-pdf/0_ILAZZZEW/11)
        
    - Diebold 和 Yilmaz - 2009 - Measuring Financial Asset Return and Volatility Sp.pdf
- ## Measuring the extreme linkages and time-frequency co-movements among artificial intelligence and clean energy indices
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Hongjun Zeng|
    |作者|Mohammad Zoynul Abedin|
    |作者|Xiangjing Zhou|
    |作者|Ran Lu|
    |摘要|This is the first study analyzing the volatility connectedness and time-frequency interdependence between AI index and clean energy index. Specifically, we use the QVAR frequency connectedness, Wavelet Local Multiple Correlations (WLMC) and Granger causality quantile methods to check the risk spillovers and multivariate time and frequency relationships among the eight clean energy indexes and the AI index. This is over the period from December 18, 2017 to April 4, 2023. Our results show: (1) NASDAQ OMX Geothermal Index is the strongest net sender of short- and long-term shocks in the system during extreme upside market conditions. In downturn conditions, the S&P Global Clean Energy Index is the largest net shock sender. The AI Index exports shocks at all frequencies. In addition, market connectedness among markets is stronger under extreme market conditions. (2) We find that the AI Index predominantly exhibited positive co-movements with clean energy indices, primarily concentrated within the long-term frequency domain. However, they displayed robust cooperative dynamics across all frequency domains within the context of multivariate wavelet interconnections. (3) The quantile granger causality analysis revealed that below the extreme bullish threshold (0.95), the NASDAQ CTA Artificial Intelligence & Robotics index could predict changes in the risk associated with all clean energy indices. However, under extremely bullish quantile conditions, the NASDAQ CTA Artificial Intelligence & Robotics index statisti­ cally exhibited Granger causality only with respect to the NASDAQ OMX Renewable Energy Index, NASDAQ OMX Geothermal Index, and WilderHill Clean Energy Index.|
    |日期|03/2024|
    |语言|en|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S105752192400005X](https://linkinghub.elsevier.com/retrieve/pii/S105752192400005X)|
    |访问时间|2024/12/24 20:55:44|
    |卷次|92|
    |页码|103073|
    |刊名|International Review of Financial Analysis|
    |DOI|[10.1016/j.irfa.2024.103073](http://doi.org/10.1016/j.irfa.2024.103073)|
    |刊名简称|International Review of Financial Analysis|
    |ISSN|10575219|
    |添加日期|2024/12/24 20:55:44|
    |修改日期|2025/6/13 11:20:00|
    
    ### 附件
    
    - Zeng 等 - 2024 - Measuring the extreme linkages and time-frequency .pdf
- ## Measuring the extreme linkages and time-frequency co-movements among artificial intelligence and clean energy indices
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Hongjun Zeng|
    |作者|Mohammad Zoynul Abedin|
    |作者|Xiangjing Zhou|
    |作者|Ran Lu|
    |摘要|This is the first study analyzing the volatility connectedness and time-frequency interdependence between AI index and clean energy index. Specifically, we use the QVAR frequency connectedness, Wavelet Local Multiple Correlations (WLMC) and Granger causality quantile methods to check the risk spillovers and multivariate time and frequency relationships among the eight clean energy indexes and the AI index. This is over the period from December 18, 2017 to April 4, 2023. Our results show: (1) NASDAQ OMX Geothermal Index is the strongest net sender of short- and long-term shocks in the system during extreme upside market conditions. In downturn conditions, the S&P Global Clean Energy Index is the largest net shock sender. The AI Index exports shocks at all frequencies. In addition, market connectedness among markets is stronger under extreme market conditions. (2) We find that the AI Index predominantly exhibited positive co-movements with clean energy indices, primarily concentrated within the long-term frequency domain. However, they displayed robust cooperative dynamics across all frequency domains within the context of multivariate wavelet interconnections. (3) The quantile granger causality analysis revealed that below the extreme bullish threshold (0.95), the NASDAQ CTA Artificial Intelligence & Robotics index could predict changes in the risk associated with all clean energy indices. However, under extremely bullish quantile conditions, the NASDAQ CTA Artificial Intelligence & Robotics index statistically exhibited Granger causality only with respect to the NASDAQ OMX Renewable Energy Index, NASDAQ OMX Geothermal Index, and WilderHill Clean Energy Index.|
    |日期|2024-03-01|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S105752192400005X](https://www.sciencedirect.com/science/article/pii/S105752192400005X)|
    |访问时间|2025/11/7 16:07:22|
    |卷次|92|
    |页码|103073|
    |刊名|International Review of Financial Analysis|
    |DOI|[10.1016/j.irfa.2024.103073](http://doi.org/10.1016/j.irfa.2024.103073)|
    |刊名简称|International Review of Financial Analysis|
    |ISSN|1057-5219|
    |添加日期|2025/11/7 16:07:22|
    |修改日期|2025/11/7 16:07:22|
    
    ### 标签：
    
    - Artificial intelligence
    - Clean energy
    - Quantile granger causality
    - Quantile time-frequency
    - Tail risk
    - Wavelet
    
    ### 附件
    
    - ScienceDirect Snapshot
- ## Measuring the Frequency Dynamics of Financial Connectedness and Systemic Risk*
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Jozef Baruník|
    |作者|Tomáš Křehlík|
    |摘要|We propose a new framework for measuring connectedness among ﬁnancial variables that arise due to heterogeneous frequency responses to shocks. To estimate connectedness in short-, medium-, and long-term ﬁnancial cycles, we introduce a framework based on the spectral representation of variance decompositions. In an empirical application, we document the rich time-frequency dynamics of volatility connectedness in U.S. ﬁnancial institutions. Economically, periods in which connectedness is created at high frequencies are periods when stock markets seem to process information rapidly and calmly, and a shock to one asset in the system will have an impact mainly in the short term. When the connectedness is created at lower frequencies, it suggests that shocks are persistent and are being transmitted for longer periods.|
    |日期|2018-03-01|
    |语言|en|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://academic.oup.com/jfec/article/16/2/271/4868603](https://academic.oup.com/jfec/article/16/2/271/4868603)|
    |访问时间|2025/6/7 11:19:29|
    |版权|http://academic.oup.com/journals/pages/about_us/legal/notices|
    |卷次|16|
    |页码|271-296|
    |刊名|Journal of Financial Econometrics|
    |DOI|[10.1093/jjfinec/nby001](http://doi.org/10.1093/jjfinec/nby001)|
    |期号|2|
    |ISSN|1479-8409, 1479-8417|
    |添加日期|2025/6/7 11:19:29|
    |修改日期|2025/6/7 19:32:38|
    
    ### 附件
    
    - Baruník 和 Křehlík - 2018 - Measuring the Frequency Dynamics of Financial Conn.pdf
- ## On the network topology of variance decompositions: Measuring the connectedness of financial firms
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Francis X. Diebold|
    |作者|Kamil Yılmaz|
    |摘要|We propose several connectedness measures built from pieces of variance decompositions, and we argue that they provide natural and insightful measures of connectedness. We also show that variance decompositions define weighted, directed networks, so that our connectedness measures are intimately related to key measures of connectedness used in the network literature. Building on these insights, we track daily time-varying connectedness of major US financial institutions’ stock return volatilities in recent years, with emphasis on the financial crisis of 2007–2008.|
    |日期|09/2014|
    |语言|en|
    |短标题|On the network topology of variance decompositions|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S0304407614000712](https://linkinghub.elsevier.com/retrieve/pii/S0304407614000712)|
    |访问时间|2025/9/20 16:02:38|
    |卷次|182|
    |页码|119-134|
    |刊名|Journal of Econometrics|
    |DOI|[10.1016/j.jeconom.2014.04.012](http://doi.org/10.1016/j.jeconom.2014.04.012)|
    |期号|1|
    |刊名简称|Journal of Econometrics|
    |ISSN|03044076|
    |添加日期|2025/9/20 16:02:38|
    |修改日期|2025/10/20 20:24:58|
    
    ### 附件
    
    - Diebold 和 Yılmaz - 2014 - On the network topology of variance decompositions.pdf
- ## Past, present, and future of sustainable finance: insights from big data analytics through machine learning of scholarly research
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Satish Kumar|
    |作者|Dipasha Sharma|
    |作者|Sandeep Rao|
    |作者|Weng Marc Lim|
    |作者|Sachin Kumar Mangla|
    |摘要|Sustainable ﬁnance is a rich ﬁeld of research. Yet, existing reviews remain limited due to the piecemeal insights offered through a sub-set rather than the entire corpus of sustainable ﬁnance. To address this gap, this study aims to conduct a large-scale review that would provide a state-of-the-art overview of the performance and intellectual structure of sustainable ﬁnance. To do so, this study engages in a review of sustainable ﬁnance research using big data analytics through machine learning of scholarly research. In doing so, this study unpacks the most inﬂuential articles and top contributing journals, authors, institutions, and countries, as well as the methodological choices and research contexts for sustainable ﬁnance research. In addition, this study reveals insights into seven major themes of sustainable ﬁnance research, namely socially responsible investing, climate ﬁnancing, green ﬁnancing, impact investing, carbon ﬁnancing, energy ﬁnancing, and governance of sustainable ﬁnancing and investing. To drive the ﬁeld forward, this study proposes several suggestions for future sustainable ﬁnance research, which include developing and diffusing innovative sustainable ﬁnancing instruments, magnifying and managing the proﬁtability and returns of sustainable ﬁnancing, making sustainable ﬁnance more sustainable, devising and unifying policies and frameworks for sustainable ﬁnance, tackling greenwashing of corporate sustainability reporting in sustainable ﬁnance, shining behavioral ﬁnance on sustainable ﬁnance, and leveraging the power of new-age technologies such as artiﬁcial intelligence, blockchain, internet of things, and machine learning for sustainable ﬁnance.|
    |日期|02/2025|
    |语言|en|
    |短标题|Past, present, and future of sustainable finance|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://link.springer.com/10.1007/s10479-021-04410-8](https://link.springer.com/10.1007/s10479-021-04410-8)|
    |访问时间|2025/11/7 15:50:18|
    |卷次|345|
    |页码|1061-1104|
    |刊名|Annals of Operations Research|
    |DOI|[10.1007/s10479-021-04410-8](http://doi.org/10.1007/s10479-021-04410-8)|
    |期号|2-3|
    |刊名简称|Ann Oper Res|
    |ISSN|0254-5330, 1572-9338|
    |添加日期|2025/11/7 15:50:18|
    |修改日期|2025/11/7 15:50:18|
    
    ### 附件
    
    - PDF
- ## Quantum computing and quantum artificial intelligence for renewable and sustainable energy: A emerging prospect towards climate neutrality
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Akshay Ajagekar|
    |作者|Fengqi You|
    |摘要|Transitioning from fossil fuels to renewable sources and developing sustainable energy materials for energy production and storage are critical factors in achieving climate neutrality. These can be realized through innovative strategies to provide viable, economically competitive, and scalable technologies ranging across various sectors. Quantum computing (QC) has the potential to revolutionize various domains of science and engineering, including macro-energy systems and sustainable energy materials design. Conventional approaches for renewable and sustainable energy systems solely rely on classical computing techniques that may not scale well with the increasing size and complexity of applications. Owing to the advancements in quantum hardware and algorithms, QC and quantum artificial intelligence make promising tools to handle renewable and sus­ tainable energy systems even at larger scales. In this review, we discuss the prospects of QC for various areas of applications in energy sustainability to help address climate change. In addition to providing a brief background on the operations of quantum computers, the constituent segments of widely adopted QC-based techniques that improve the computational efficiency of quantum chemistry calculations for sustainable energy materials along with quantum artificial intelligence methods that can address complex optimization and machine learning problems arising in renewable energy systems are also introduced in this paper. We screen the presented quantum algorithms based on their performance on current quantum devices despite their promising potential. Furthermore, sustainable energy applications that may draw advantages from QC-based strategies are identified in this work while simultaneously setting realistic expectations over the potential improvements offered over classical techniques.|
    |日期|09/2022|
    |语言|en|
    |短标题|Quantum computing and quantum artificial intelligence for renewable and sustainable energy|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S1364032122003975](https://linkinghub.elsevier.com/retrieve/pii/S1364032122003975)|
    |访问时间|2025/6/13 11:06:10|
    |卷次|165|
    |页码|112493|
    |刊名|Renewable and Sustainable Energy Reviews|
    |DOI|[10.1016/j.rser.2022.112493](http://doi.org/10.1016/j.rser.2022.112493)|
    |刊名简称|Renewable and Sustainable Energy Reviews|
    |ISSN|13640321|
    |添加日期|2025/6/13 11:06:10|
    |修改日期|2025/6/13 11:18:26|
    
    ### 附件
    
    - Ajagekar 和 You - 2022 - Quantum computing and quantum artificial intellige.pdf
- ## Role of artificial intelligence in carbon cost reduction of firms
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Cheng-Jui Tseng|
    |作者|Shih-Yen Lin|
    |摘要|The primary investor for global warming and climate change is carbon dioxide (CO2), which accounts for the largest portion of greenhouse gases in and around firms. Artificial intelligence (AI) can have a big impact on reducing the carbon costs of firms. With AI, companies can monitor energy usage across different processes, identify inefficiencies and suggest ways to reduce them. This helps companies improve resource efficiency and costs while minimizing carbon emissions. The study aims to explore the impact of artificial intelligence (AI) on the carbon cost reduction of firms. This study investigates how businesses can leverage Artificial Intelligence (AI) for the reduction of carbon costs. Specifically, the research explores the impact of AI-based predictions, decisionmaking, recommendations, and renewable energy optimization on firms’ carbon cost reduction. This research employs a quantitative research design and demonstrates that AI use in decision-making and optimizing renewable energy is highly correlated with carbon cost reduction. The outcomes of the research have significant practical implications for policymakers, and industry professionals in their development of sustainable business practices. Additionally, the research contributes to the literature surrounding AI and sustainability by offering an empirical perspective on how AI can be used to support environmental sustainability efforts, enhance corporate social responsibility, and promote long-term economic gains for firms. The statistical analysis shows that there is a significant impact of AI-based predictions on the reduction of carbon costs in firms. Furthermore, it demon­ strates that AI-based decision-making impacts reducing carbon costs for firms. These results highlight the importance of incorporating AI technology into business practices to effectively address sustainability concerns and reduce carbon costs, ultimately promoting long-term economic sustainability and corporate social responsibility.|
    |日期|04/2024|
    |语言|en|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S0959652624008606](https://linkinghub.elsevier.com/retrieve/pii/S0959652624008606)|
    |访问时间|2025/6/13 11:06:07|
    |卷次|447|
    |页码|141413|
    |刊名|Journal of Cleaner Production|
    |DOI|[10.1016/j.jclepro.2024.141413](http://doi.org/10.1016/j.jclepro.2024.141413)|
    |刊名简称|Journal of Cleaner Production|
    |ISSN|09596526|
    |添加日期|2025/6/13 11:06:07|
    |修改日期|2025/6/13 11:18:46|
    
    ### 附件
    
    - Tseng 和 Lin - 2024 - Role of artificial intelligence in carbon cost red.pdf
- ## Secular Stagnation? The Effect of Aging on Economic Growth in the Age of Automation
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Daron Acemoglu|
    |作者|Pascual Restrepo|
    |摘要|Several recent theories emphasize the negative effects of an aging population on economic growth, either because of the lower labor force participation and productivity of older workers or because aging will create an excess of savings over desired investment, leading to secular stagnation. We show that there is no such negative relationship in the data. If anything, countries experiencing more rapid aging have grown more in recent decades. We suggest that this counterintuitive finding might reflect the more rapid adoption of automation technologies in countries undergoing more pronounced demographic changes and provide evidence and theoretical underpinnings for this argument.|
    |日期|2017/05|
    |语言|en|
    |短标题|Secular Stagnation?|
    |文库编目|www.aeaweb.org|
    |网址|[https://www.aeaweb.org/articles?id=10.1257/aer.p20171101](https://www.aeaweb.org/articles?id=10.1257/aer.p20171101)|
    |访问时间|2025/11/7 15:27:28|
    |卷次|107|
    |页码|174-179|
    |刊名|American Economic Review|
    |DOI|[10.1257/aer.p20171101](http://doi.org/10.1257/aer.p20171101)|
    |期号|5|
    |ISSN|0002-8282|
    |添加日期|2025/11/7 15:27:28|
    |修改日期|2025/11/7 15:27:28|
    
    ### 标签：
    
    - 宏观经济学：生产
    - 技术变革：选择和后果;扩散过程
    - 就业;失业;工资;代际收入分配;人力资本总量;总劳动生产率
    - 老年人经济学;残疾人经济学;非劳动力市场歧视
    - 人口趋势、宏观经济影响和预测
    - 业务波动;周期
    - Aggregate Human Capital
    - Aggregate Labor Productivity, Business Fluctuations
    - Business Fluctuations; Cycles
    - Cycles, Demographic Trends, Macroeconomic Effects, and Forecasts, Economics of the Elderly
    - Demographic Trends, Macroeconomic Effects, and Forecasts
    - Diffusion Processes
    - Economics of the Elderly; Economics of the Handicapped; Non-Labor Market Discrimination
    - Economics of the Handicapped
    - Employment; Unemployment; Wages; Intergenerational Income Distribution; Aggregate Human Capital; Aggregate Labor Productivity
    - Intergenerational Income Distribution
    - Macroeconomics: Production
    - Macroeconomics: Production, Employment
    - Non-Labor Market Discrimination, Technological Change: Choices and Consequences
    - Technological Change: Choices and Consequences; Diffusion Processes
    - Unemployment
    - Wages
- ## The dynamic connectedness in the “carbon-energy-green finance” system: The role of climate policy uncertainty and artificial intelligence
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Shaozhou Qi|
    |作者|Lidong Pang|
    |作者|Xinqiang Li|
    |作者|Lin Huang|
    |摘要|The shared vision of mitigating carbon emissions in response to climate change has fostered the interconnection among the EU ETS, traditional energy and green finance sectors. This paper employs the time-frequency spillover methods to explore the connectedness within the Carbon-Energy-Green Finance system, from a time-frequency domain perspective. The empirical results indicate limited connectedness in this system, and are predominantly visible in the high-frequency (short-term) range. Although there are co-movement patterns across different frequencies, the roles of some specific markets tend to shift over time. Notably, the natural gas market primarily serves as the net receiver of spillover effects, demonstrating heightened sensitivity to information from other nodes within the system. In addition, there is heterogeneity in the impact of climate policy uncertainty and artificial intelligence development on the network in time-domain and high-frequency scenarios. However, the dominant positive effects of both can be captured in the long run, albeit with a lesser magnitude. Therefore, investors should be adaptable to adjust their portfolios under different investment horizons. And in the pursuit of sustainable ambitions, the strategy of policymakers to cushion potential external risks also cannot be shelved.|
    |日期|2025-03-01|
    |语言|en|
    |短标题|The dynamic connectedness in the “carbon-energy-green finance” system|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S0140988325000647](https://www.sciencedirect.com/science/article/pii/S0140988325000647)|
    |访问时间|2025/11/6 21:06:38|
    |卷次|143|
    |页码|108241|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2025.108241](http://doi.org/10.1016/j.eneco.2025.108241)|
    |刊名简称|Energy Economics|
    |ISSN|0140-9883|
    |添加日期|2025/11/6 21:06:39|
    |修改日期|2025/11/6 21:06:39|
    
    ### 标签：
    
    - Artificial intelligence
    - Carbon trading market
    - Climate policy uncertainty
    - Green finance
    - Time-frequency spillover
    
    ### 附件
    
    - ScienceDirect Full Text PDF
    - ScienceDirect Snapshot
- ## The dynamics between clean energy, green bonds, grain commodities, and cryptocurrencies: evidence from correlation and portfolio hedging
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Ran Wu|
    |作者|Jiale Yan|
    |作者|Cem Işık|
    |摘要|This study explores the dynamic interconnections among sustainable assets (clean energy, green bonds), grain commodities, and cryptocurrencies, anchored in theories of financial contagion, commodity market financialization, and sustainable investment. Employing TVP-VAR-DY and TVP-VAR-BK methods, we analyze time- and frequency-varying connectedness during the COVID-19 pandemic, elucidating how systemic shocks reshape risk transmission across these asset classes. The pandemic markedly intensified market linkages, with corn, soybeans, and the S&P Clean Energy Index consistently transmitting spillover shocks, propelled by biofuel demand and policy sensitivity. Notably, brown rice shifted from a net receiver to a transmitter, driven by supply chain disruptions and speculative demand, while wheat became a net receiver post-COVID-19, reflecting heterogeneous market dynamics. Other assets, including the WilderHill Clean Energy Index, green bonds, and cryptocurrencies, remained net recipients, with oats exhibiting low long-term connectivity, suggesting safe-haven potential for risk-averse investors. Short-term spillovers dominated, with rising hedging costs, particularly for soybeans against clean energy assets, signaling heightened volatility. Economic policy uncertainty strongly drove connectedness, highlighting policy’s pivotal role. These findings inform investors on portfolio diversification and crisis hedging strategies, guide policymakers in fostering resilient green finance and grain market stabilization, and advance sustainable finance by bridging financial economics with environmental goals amid global market integration.|
    |日期|08/2025|
    |语言|en|
    |短标题|The dynamics between clean energy, green bonds, grain commodities, and cryptocurrencies|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://link.springer.com/10.1007/s10644-025-09902-2](https://link.springer.com/10.1007/s10644-025-09902-2)|
    |访问时间|2025/11/7 15:50:24|
    |卷次|58|
    |页码|60|
    |刊名|Economic Change and Restructuring|
    |DOI|[10.1007/s10644-025-09902-2](http://doi.org/10.1007/s10644-025-09902-2)|
    |期号|4|
    |刊名简称|Econ Change Restruct|
    |ISSN|1573-9414, 1574-0277|
    |添加日期|2025/11/7 15:50:24|
    |修改日期|2025/11/7 15:50:24|
    
    ### 附件
    
    - PDF
- ## The effect of artificial intelligence on energy transition: Evidence from China
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Xiangming Gao|
    |作者|Xinliang Ji|
    |作者|Rong Wang|
    |作者|Jian Yu|
    |摘要|Artificial intelligence (AI) is an important next-generation information technology and a key driver of energy transition. Using panel data from 282 cities from 2006 to 2019, in this study, we examine the influence of AI on energy transition in China. We measure AI using exposure to industrial robots and find that AI can significantly accelerate the energy transition process. Improvements in energy efficiency and research and development innovation are the two mechanisms through which AI promotes energy transition. The results of heterogeneity analysis indicate that AI's impact on energy transition is more pronounced in cities with a high transition potential, specifically those with a low level of electrification, weak environmental regulations, greater fiscal constraints, and those located in the central and western regions of China. These findings provide valuable insights for the application of AI in the field of energy transition and policy guidance for China and other developing countries.|
    |日期|2025-06-01|
    |语言|en|
    |短标题|The effect of artificial intelligence on energy transition|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S0140988325003925](https://www.sciencedirect.com/science/article/pii/S0140988325003925)|
    |访问时间|2025/11/6 21:06:13|
    |卷次|147|
    |页码|108568|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2025.108568](http://doi.org/10.1016/j.eneco.2025.108568)|
    |刊名简称|Energy Economics|
    |ISSN|0140-9883|
    |添加日期|2025/11/6 21:06:13|
    |修改日期|2025/11/6 21:06:13|
    
    ### 标签：
    
    - Artificial intelligence
    - Energy efficiency
    - Energy transition
    - Exposure to industrial robots
    - R&D innovation
    
    ### 附件
    
    - ScienceDirect Full Text PDF
    - ScienceDirect Snapshot
- ## The growing energy footprint of artificial intelligence
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Alex De Vries|
    |日期|10/2023|
    |语言|en|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S2542435123003653](https://linkinghub.elsevier.com/retrieve/pii/S2542435123003653)|
    |访问时间|2025/10/31 14:22:15|
    |卷次|7|
    |页码|2191-2194|
    |刊名|Joule|
    |DOI|[10.1016/j.joule.2023.09.004](http://doi.org/10.1016/j.joule.2023.09.004)|
    |期号|10|
    |刊名简称|Joule|
    |ISSN|25424351|
    |添加日期|2025/10/31 14:22:15|
    |修改日期|2025/10/31 14:22:15|
    
    ### 附件
    
    - PDF
- ## The impact of artificial intelligence on energy environmental performance: Empirical evidence from cities in China
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Qingbin Guo|
    |作者|Yanqing Peng|
    |作者|Kang Luo|
    |摘要|As a form of the next-generation intelligent information technology, artificial intelligence (AI) is anticipated to unleash an “intelligence dividend”, playing a pivotal role in driving efficiency transformation and realizing green development objectives. Based on data from 223 cities in China for 2008 to 2021, this research evaluates the AI level from the three dimensions of intelligent infrastructure, intelligent practical applications, and intelligent technology development. It also delves into AI’s impact and mechanisms on urban energy environmental performance (EEP). The findings show that AI enhances urban EEP and influences EEP by advancing urban green innovation capabilities, improving urban human capital, and optimizing energy consumption structure. Specifically, AI has a notably heightened effect on EEP in the eastern region, large urban areas, and non-resource-based cities. Subsequent analyses reveal a significant siphoning effect of AI’s impacts across geographical distances and indicate that AI does not have a rebound effect on urban energy. In sum, countries and regions should fully seize the strategic opportunities presented by rapid AI development, shape new advantages in technological competition through open integration and innovation, and thus drive the transformation of energy development.|
    |日期|01/2025|
    |语言|en|
    |短标题|The impact of artificial intelligence on energy environmental performance|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S0140988324008454](https://linkinghub.elsevier.com/retrieve/pii/S0140988324008454)|
    |访问时间|2025/6/13 11:05:34|
    |卷次|141|
    |页码|108136|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2024.108136](http://doi.org/10.1016/j.eneco.2024.108136)|
    |刊名简称|Energy Economics|
    |ISSN|01409883|
    |添加日期|2025/6/13 11:05:34|
    |修改日期|2025/6/13 11:16:44|
    
    ### 附件
    
    - Guo 等 - 2025 - The impact of artificial intelligence on energy en.pdf
- ## The impact of artificial intelligence on global energy vulnerability
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Qingyuan Zhu|
    |作者|Chenhao Sun|
    |作者|Chengzhen Xu|
    |作者|Qianqian Geng|
    |摘要|Investigating the effect of artificial intelligence (AI) on energy vulnerability (EVI) is crucial to understanding how technological advances are changing the resilience and sustainability of en­ ergy systems. However, their quantitative relationship still lacks empirical evidence. This study first constructs the EVI of 54 global economies from the perspective of energy security, energy consumption, energy efficiency, and energy availability from 2000 to 2019. Then, a fixed-effect model is employed to investigate the relationship between AI and EVI. Results show that (1) AI can considerably reduce global EVI. The core findings remain reliable after several robustness checks. (2) Mechanism analysis implies that AI can reduce EVI by promoting financial develop­ ment and technological progress. (3) Heterogeneity analysis implies that the impeding role of AI on EVI is more pronounced in countries with low incomes and industrialization levels. Further­ more, the hindering effect of AI on EVI is strengthened after Industry 4.0 and the financial crisis. Some policy implications are further proposed accordingly to reduce global EVI.|
    |日期|03/2025|
    |语言|en|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S0313592624003333](https://linkinghub.elsevier.com/retrieve/pii/S0313592624003333)|
    |访问时间|2025/6/13 11:05:55|
    |卷次|85|
    |页码|15-27|
    |刊名|Economic Analysis and Policy|
    |DOI|[10.1016/j.eap.2024.11.021](http://doi.org/10.1016/j.eap.2024.11.021)|
    |刊名简称|Economic Analysis and Policy|
    |ISSN|03135926|
    |添加日期|2025/6/13 11:05:55|
    |修改日期|2025/6/13 11:16:09|
    
    ### 附件
    
    - Zhu 等 - 2025 - The impact of artificial intelligence on global en.pdf
- ## The impact of clean energy demonstration province policies on carbon intensity in Chinese counties based on the multi-phase PSM-DID method
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Lei Chen|
    |作者|Cunjing Liu|
    |作者|Zhezhou Li|
    |作者|Difan Wu|
    |摘要|Based on China’s empirical data from 2000 to 2020 of 1875 county-level administrative units, combined with the multi-phase by the propensity score matching and difference-in-difference (PSM-DID) model, this paper studies the impact of clean energy demonstration province policies on the carbon intensity of pilot counties, and its further impact on carbon emissions and economic development level. The results showed that 1. from a county-level perspective, although the economic development level of the pilot areas of clean energy demonstration provinces has improved as the carbon emissions have also increased, what is more, the carbon intensity has also significantly improved in this process; 2. there is no time lag in the impact of policies on the carbon intensity of counties, and the impact effects gradually increase over time along with strong regional heterogeneity; 3. the clean energy demonstration policy has weakened the technological level of the county and reduced the proportion of industrial-added value to GDP, thereby increasing the carbon intensity of the county through these intermediaries.|
    |日期|2024-01-18|
    |语言|en|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://link.springer.com/10.1007/s11356-023-31799-5](https://link.springer.com/10.1007/s11356-023-31799-5)|
    |访问时间|2025/11/7 15:50:32|
    |卷次|31|
    |页码|12978-12994|
    |刊名|Environmental Science and Pollution Research|
    |DOI|[10.1007/s11356-023-31799-5](http://doi.org/10.1007/s11356-023-31799-5)|
    |期号|9|
    |刊名简称|Environ Sci Pollut Res|
    |ISSN|1614-7499|
    |添加日期|2025/11/7 15:50:32|
    |修改日期|2025/11/7 15:50:32|
    
    ### 附件
    
    - PDF
- ## The pathway to enhancing energy efficiency: Is artificial intelligence important?
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Nan Ke|
    |作者|Jiamin Shen|
    |摘要|Enhancing energy efficiency is a key solution for alleviating environmental crises and promoting sustainable development. As a strategic future-oriented technology, the rise of artificial intelligence (AI) opens new pathways for improving energy efficiency. However, research exploring the role of AI on regional energy efficiency from spatial perspectives remains scarce. To address these gaps, this study establishes a novel AI evaluation system and applies a combination weighting method to measure the AI indices of 30 Chinese provinces from 2006 to 2021. Furthermore, spatial econometric models are employed to detect the effect and mechanisms of AI on energy efficiency. The results highlight that AI significantly improves provincial energy efficiency, and its spatial spillover effects exhibit regional heterogeneity. In the eastern, high-intelligence and developed regions, AI generates positive spillovers through technological diffusion, while it induces negative externalities in low-intelligence and developing regions. Notably, compared to resourcebased region, non-resource-based region receives more pronounced AI dividend. Further mechanism analysis indicates that industrial structure upgrading and research and development (R&D) elements flow are crucial channels for AI to enhance energy efficiency. These findings enrich the understanding of AI’s influence in the energy sector and provide practical implications for building a modern energy system to achieve sustainable development goals.|
    |日期|2025-10-31|
    |语言|en|
    |短标题|The pathway to enhancing energy efficiency|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://link.springer.com/10.1007/s10668-025-06938-2](https://link.springer.com/10.1007/s10668-025-06938-2)|
    |访问时间|2025/11/7 15:50:28|
    |刊名|Environment, Development and Sustainability|
    |DOI|[10.1007/s10668-025-06938-2](http://doi.org/10.1007/s10668-025-06938-2)|
    |刊名简称|Environ Dev Sustain|
    |ISSN|1573-2975|
    |添加日期|2025/11/7 15:50:28|
    |修改日期|2025/11/7 15:50:28|
    
    ### 附件
    
    - PDF
- ## The Race between Man and Machine: Implications of Technology for Growth, Factor Shares, and Employment
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Daron Acemoglu|
    |作者|Pascual Restrepo|
    |摘要|We examine the concerns that new technologies will render labor redundant in a framework in which tasks previously performed by labor can be automated and new versions of existing tasks, in which labor has a comparative advantage, can be created. In a static version where capital is fixed and technology is exogenous, automation reduces employment and the labor share, and may even reduce wages, while the creation of new tasks has the opposite effects. Our full model endogenizes capital accumulation and the direction of research toward automation and the creation of new tasks. If the long-run rental rate of capital relative to the wage is sufficiently low, the long-run equilibrium involves automation of all tasks. Otherwise, there exists a stable balanced growth path in which the two types of innovations go hand-in-hand. Stability is a consequence of the fact that automation reduces the cost of producing using labor, and thus discourages further automation and encourages the creation of new tasks. In an extension with heterogeneous skills, we show that inequality increases during transitions driven both by faster automation and the introduction of new tasks, and characterize the conditions under which inequality stabilizes in the long run. (JEL D63, E22, E23, E24, J24, O33, O41)|
    |日期|2018-06-01|
    |语言|en|
    |短标题|The Race between Man and Machine|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://pubs.aeaweb.org/doi/10.1257/aer.20160696](https://pubs.aeaweb.org/doi/10.1257/aer.20160696)|
    |访问时间|2025/11/7 15:57:42|
    |卷次|108|
    |页码|1488-1542|
    |刊名|American Economic Review|
    |DOI|[10.1257/aer.20160696](http://doi.org/10.1257/aer.20160696)|
    |期号|6|
    |刊名简称|American Economic Review|
    |ISSN|0002-8282|
    |添加日期|2025/11/7 15:57:42|
    |修改日期|2025/11/7 15:57:42|
    
    ### 附件
    
    - Full Text PDF
- ## The rising role of artificial intelligence in renewable energy development in China
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Xiaojing Zhang|
    |作者|Khalid Khan|
    |作者|Xuefeng Shao|
    |作者|Camelia Oprean-Stan|
    |作者|Qian Zhang|
    |摘要|Exploring the role of artificial intelligence (AI) in renewable energy (RE) development is pivotal for seizing technological opportunities and achieving climate objectives. This study uses wavelet analysis to examine the correlation between AI and RE in China. Our findings indicate a co-movement between AI and RE from 2014 to 2016 and a positive influence from AI to RE emerging from late 2018 to 2022. This suggests that AI acts as a facilitator for China's energy transition. Nevertheless, this effect is not constant; it becomes more pronounced with advancements in AI technology. These outcomes align with the techno-economic paradigms framework, implying that China can benefit from AI breakthroughs to accelerate its energy transition. Future policy efforts may focus on fostering collaboration among the government, businesses, and universities to promote AI and RE development.|
    |日期|2024-04-01|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S014098832400197X](https://www.sciencedirect.com/science/article/pii/S014098832400197X)|
    |访问时间|2025/7/14 19:21:44|
    |卷次|132|
    |页码|107489|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2024.107489](http://doi.org/10.1016/j.eneco.2024.107489)|
    |刊名简称|Energy Economics|
    |ISSN|0140-9883|
    |添加日期|2025/7/14 19:21:44|
    |修改日期|2025/7/14 19:21:44|
    
    ### 标签：
    
    - Artificial intelligence
    - Energy transition
    - Renewable energy
    - Wavelet analysis
    
    ### 附件
    
    - ScienceDirect Snapshot
- ## The role of artificial intelligence in achieving the Sustainable Development Goals
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Ricardo Vinuesa|
    |语言|en|
    |文库编目|Zotero|
    |添加日期|2024/12/17 18:59:27|
    |修改日期|2024/12/17 18:59:27|
    
    ### 附件
    
    - Vinuesa - The role of artificial intelligence in achieving t.pdf
- ## The role of artificial intelligence in renewable energy development: Insights from less developed economies
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Huanyu Zheng|
    |作者|Jie Wu|
    |作者|Runze Li|
    |作者|Yanwu Song|
    |摘要|Global climate change and the growing pressure of energy transition pose complex challenges for less developed economies in achieving environmental sustainability. Artificial intelligence technology offers a promising avenue for advancing renewable energy development. This study analyzes the non-linear impact of AI technology on the renewable energy, drawing on AI patent data from 56 less developed economies from 2007 to 2022. The findings reveal a significant “inverted U-shaped” relationship. That is, AI initially drives renewable energy adoption, but as technological development reaches a certain threshold, its marginal benefits decline, potentially leading to negative effects. Moreover, institutional quality plays a crucial moderating role, with a strong rule of law enhancing AI's positive impact, while digital economic expansion exerts a weakening effect. Technological innovation acts as a key mediating mechanism, facilitating AI's influence on renewable energy adoption. Furthermore, the impact of AI varies across different renewable energy sources, with significant non-linear effects observed for biomass and wind energy, while its influence on solar and hydropower remains limited. These insights contribute to the literature on sustainable energy transitions and provide valuable policy implications for optimizing AI-driven renewable energy strategies in less developed economies.|
    |日期|2025-05-01|
    |语言|en|
    |短标题|The role of artificial intelligence in renewable energy development|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S0140988325003755](https://www.sciencedirect.com/science/article/pii/S0140988325003755)|
    |访问时间|2025/11/6 21:05:20|
    |卷次|146|
    |页码|108551|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2025.108551](http://doi.org/10.1016/j.eneco.2025.108551)|
    |刊名简称|Energy Economics|
    |ISSN|0140-9883|
    |添加日期|2025/11/6 21:05:20|
    |修改日期|2025/11/6 21:05:20|
    
    ### 标签：
    
    - Artificial intelligence
    - Inverted-U relationship
    - Less developed economies
    - Renewable energy
    - Rule of law environment
    
    ### 附件
    
    - ScienceDirect Full Text PDF
    - ScienceDirect Snapshot
- ## The spatial spillover impact of artificial intelligence on energy efficiency: Empirical evidence from 278 Chinese cities
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Yong Wang|
    |作者|Wenhao Zhao|
    |作者|Xuejiao Ma|
    |摘要|Within the framework of global sustainable development, improving energy efficiency (EE) is recognized as a crucial strategy to address environmental challenges and foster economic growth. This research employs the Spatial Durbin Model to investigate the spatial spillover effects of advancements in artificial intelligence (AI) technology on EE across 278 Chinese cities. The analysis reveals several key findings: first, the advancement of AI technology significantly enhances urban EE and generates a positive spatial spillover effect across different spatial weight matrices; second, there is a nonlinear, inverted U-shaped relationship between AI levels and urban EE; third, industrial structure upgrades play a significant moderating role in the impact of AI technology on urban EE. These insights not only illuminate the complex role of AI in improving regional EE but also provide critical recommendations for policymakers aiming to enhance urban EE and achieve sustainable development goals.|
    |日期|12/2024|
    |语言|en|
    |短标题|The spatial spillover impact of artificial intelligence on energy efficiency|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S0360544224032730](https://linkinghub.elsevier.com/retrieve/pii/S0360544224032730)|
    |访问时间|2025/6/13 11:05:58|
    |卷次|312|
    |页码|133497|
    |刊名|Energy|
    |DOI|[10.1016/j.energy.2024.133497](http://doi.org/10.1016/j.energy.2024.133497)|
    |刊名简称|Energy|
    |ISSN|03605442|
    |添加日期|2025/6/13 11:05:58|
    |修改日期|2025/6/13 11:17:12|
    
    ### 附件
    
    - Wang 等 - 2024 - The spatial spillover impact of artificial intelli.pdf
- ## The time‐varying volatility spillover effects between China's coal and metal market
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Boqiang Lin|
    |作者|Tianxu Lan|
    |摘要|This study employs a time‐varying parameter vector autoregression methodology with the Diebold and Yilmaz spillover index to scrutinize the temporal fluctuations in volatility spillovers between the Chinese coal and metal markets. The analysis is conducted from the dual perspectives of security indices and futures prices. The findings reveal a robust correlation between the coal and metal markets, with the coal market serving as a primary conduit for volatility spillover into the metal market. Furthermore, this study investigates the time‐specific impacts of coal decommissioning policies, the COVID‐19 pandemic, and the coal supply crisis on the coal–metal market volatility spillovers. The findings indicate that these three unique shocks significantly increase the overall risk spillover index between the coal and metal markets. Moreover, during these exceptional events, the extent or role of risk spillover in the coal–metal market undergoes varying degrees of change. On the basis of these findings, this article presents pertinent policy recommendations.|
    |日期|05/2024|
    |语言|en|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://onlinelibrary.wiley.com/doi/10.1002/fut.22488](https://onlinelibrary.wiley.com/doi/10.1002/fut.22488)|
    |访问时间|2024/12/5 21:42:07|
    |卷次|44|
    |页码|699-719|
    |刊名|Journal of Futures Markets|
    |DOI|[10.1002/fut.22488](http://doi.org/10.1002/fut.22488)|
    |期号|5|
    |刊名简称|Journal of Futures Markets|
    |ISSN|0270-7314, 1096-9934|
    |添加日期|2024/12/5 21:42:07|
    |修改日期|2025/6/13 11:14:38|
    
    ### 附件
    
    - Lin 和 Lan - 2024 - The time‐varying volatility spillover effects betw.pdf
- ## Understanding the effects of artificial intelligence on energy transition: The moderating role of Paris Agreement
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Muhammad Zubair Chishti|
    |作者|Xiqiang Xia|
    |作者|Eyup Dogan|
    |摘要|This study contributes to the existing literature by investigating and confirming a range of diverse outcomes related to the interplay of factors shaping the global energy transition (ET). Employing advanced methodologies, including the extension of the QVAR technique to short-term (SR), medium-term (MR), and long-term (LR) connectedness analysis, as well as the application of the CQ method to explore relationships within varying market conditions and timeframes, the study examines the interconnectedness of critical variables: artificial intelligence (AI), the Belt and Road Initiative (BRI), the Paris Agreement (PA), green technologies (GT), geopolitical risk (GPR), and ET. The findings highlight several crucial insights. Firstly, all selected variables demonstrate substantial interconnectedness across different time horizons, except for MR, which exhibits comparatively weaker connectedness than SR and LR. Secondly, independent series reveal diverse impacts on ET across various market conditions and periods. For example, in SR, most series produce mixed effects on ET, with BRI having primarily adverse consequences and GPR predominantly yielding positive impacts. In MR, the influence of AI, PA, and GT on ET varies, while BRI enhances ET, and GPR essentially hampers it. Notably, in LR, AI, BRI, PA, and GT significantly promote ET, while GPR disrupts its progress. Additionally, the study underscores the dynamic and time-varying nature of the relationships between AI, BRI, PA, GT, GPR, and ET across different market conditions, thus holding essential implications for shaping global policies to foster sustainable energy transitions.|
    |日期|03/2024|
    |语言|en|
    |短标题|Understanding the effects of artificial intelligence on energy transition|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S0140988324000963](https://linkinghub.elsevier.com/retrieve/pii/S0140988324000963)|
    |访问时间|2024/12/24 20:55:36|
    |卷次|131|
    |页码|107388|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2024.107388](http://doi.org/10.1016/j.eneco.2024.107388)|
    |刊名简称|Energy Economics|
    |ISSN|01409883|
    |添加日期|2024/12/24 20:55:36|
    |修改日期|2025/6/13 11:17:07|
    
    ### 附件
    
    - Chishti 等 - 2024 - Understanding the effects of artificial intelligen.pdf
- ## Unveiling energy security in agriculture through vital indicators extraction and insights
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Reihaneh Haghjoo|
    |作者|Shahla Choobchian|
    |作者|Enayat Abbasi|
    |摘要|Despite advancements in meeting various human needs, energy supply remains a top priority for all countries worldwide. The escalating energy consumption in the agricultural sector underscores the necessity to scrutinize its energy usage. Presently, there exists an absence of a precise tool for accurately measuring this consumption. Hence, this study aims to identify indicators for measuring energy security in agriculture, conducted in three phases: content analysis, indicator validation, and field investigation. In the content analysis phase, energy security indicators were extracted and grouped into four categories: accessibility, availability, utilization, and sustainability. Following this, a two-stage validation process led to the identification of 18 indicators for assessing energy security in agriculture. In the field phase, a tailored questionnaire was distributed to 160 randomly selected farmers. The findings revealed that the availability component held the highest rank in establishing energy security, with an average score of 3.31. However, the current status of the access component indicates a more unfavorable situation compared to other dimensions. Consequently, to achieve energy security in agriculture, particular emphasis should be placed on enhancing energy access. Key areas to address include reducing transportation costs and minimizing the use of chemical pesticides. This indicates a necessity for focused interventions aimed at improving both energy access and sustainability within the agricultural sector. These efforts would contribute to enhancing economic efficiency and promoting environmental conservation.|
    |日期|2024-04-15|
    |语言|en|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://www.nature.com/articles/s41598-024-59273-3](https://www.nature.com/articles/s41598-024-59273-3)|
    |访问时间|2025/11/7 15:50:42|
    |卷次|14|
    |页码|8626|
    |刊名|Scientific Reports|
    |DOI|[10.1038/s41598-024-59273-3](http://doi.org/10.1038/s41598-024-59273-3)|
    |期号|1|
    |刊名简称|Sci Rep|
    |ISSN|2045-2322|
    |添加日期|2025/11/7 15:50:42|
    |修改日期|2025/11/7 15:50:42|
    
    ### 附件
    
    - PDF
- ## Water transfer and losses embodied in the West–East electricity transmission project in China
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Yongnan Zhu|
    |作者|Jing Ke|
    |作者|Jianhua Wang|
    |作者|He Liu|
    |作者|Shan Jiang|
    |作者|Helcio Blum|
    |作者|Yong Zhao|
    |作者|Guohua He|
    |作者|Yuan Meng|
    |作者|Jian Su|
    |摘要|Electricity is an important output of the global energy system. Large amounts of water can be consumed in the process of producing electricity. This article focuses on how that water is virtually transferred from powergenerating regions to electricity-consuming areas. We propose two metrics, i.e., water substitution ratio and virtual water transfer loss, to assess the eﬃciency of water use for power generation and virtual transmission of water through the power transmission system, respectively. These metrics are used to estimate the eﬀects of the West–East Electricity Transmission project in China on the water resources used in power-generating regions. Results show that the electricity delivered by the project increased from 228 TWh in 2008 to 683 TWh in 2017. With the construction of wind and solar energy projects, the growth rate of virtual water was slightly slower than that of the electricity transmitted. In 2017, 2.4 km3 of virtual water was transmitted eastward. The corresponding virtual water transfer loss throughout the transmission system was approximately 100 million m3. We estimate that the virtual water footprint of the project will exceed 4.4 km3 by 2030, which may aﬀect the sustainability of water resources and the ecological environment in western regions of China.|
    |日期|10/2020|
    |语言|en|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S0306261920306644](https://linkinghub.elsevier.com/retrieve/pii/S0306261920306644)|
    |访问时间|2024/12/5 21:42:17|
    |卷次|275|
    |页码|115152|
    |刊名|Applied Energy|
    |DOI|[10.1016/j.apenergy.2020.115152](http://doi.org/10.1016/j.apenergy.2020.115152)|
    |刊名简称|Applied Energy|
    |ISSN|03062619|
    |添加日期|2024/12/5 21:42:17|
    |修改日期|2024/12/5 21:42:17|
    
    ### 附件
    
    - Zhu 等 - 2020 - Water transfer and losses embodied in the West–Eas.pdf
- ## When and how does artificial intelligence impact environmental performance?
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Sana Slimani|
    |作者|Anis Omri|
    |作者|Sami Ben Jabeur|
    |摘要|As concerns grow over climate change, policymakers are increasingly exploring the synergistic potential between digital technologies and sustainable energy systems. Artificial intelligence (AI) holds promise for accelerating the transition to renewable sources through applications like smart grids, predictive maintenance, and resource optimization. However, the dynamics between AI, renewable transitions, digitalization, and their combined impacts on environmental performance remain underexplored. Against this backdrop, this study uses the PROCESS methodology of Hayes (2017) to provide novel insights into the conditional pathways, such as the digital economy, through which AI can indirectly support environmental sustainability via renewable energy transition for 24 developed countries. The findings indicate that renewable energy transition mediates the link between AI and environmental performance. They also show that the digital economy enhances AI's support for the renewable transition to cleaner sources. Considering renewable transition's positive influence on the AI-environmental performance nexus, the moderated mediation model suggests that digital economy moderates the mediating transition pathway. Specifically, higher digitalization likely strengthens AI's impact on transitioning to renewable alternatives. Therefore, AI has more significant indirect effects on sustainability outcomes at elevated levels of digitization that reinforce its impact on accelerating the renewable energy transition. Hence, strategic investments and partnerships across these interconnected domains can help optimize sustainable development pathways amid global decarbonization efforts.|
    |日期|2025-08-01|
    |文库编目|ScienceDirect|
    |网址|[https://www.sciencedirect.com/science/article/pii/S0140988325004700](https://www.sciencedirect.com/science/article/pii/S0140988325004700)|
    |访问时间|2025/11/6 21:03:48|
    |卷次|148|
    |页码|108643|
    |刊名|Energy Economics|
    |DOI|[10.1016/j.eneco.2025.108643](http://doi.org/10.1016/j.eneco.2025.108643)|
    |刊名简称|Energy Economics|
    |ISSN|0140-9883|
    |添加日期|2025/11/6 21:03:48|
    |修改日期|2025/11/6 21:03:48|
    
    ### 标签：
    
    - Artificial intelligence
    - Digital economy
    - Environmental performance
    - Renewable energy
- ## Will artificial intelligence make energy cleaner? Evidence of nonlinearity
    
    |   |   |
    |---|---|
    |条目类型|期刊文章|
    |作者|Chien-Chiang Lee|
    |作者|Jingyang Yan|
    |日期|06/2024|
    |语言|en|
    |短标题|Will artificial intelligence make energy cleaner?|
    |文库编目|DOI.org (Crossref)|
    |网址|[https://linkinghub.elsevier.com/retrieve/pii/S0306261924004641](https://linkinghub.elsevier.com/retrieve/pii/S0306261924004641)|
    |访问时间|2025/6/13 11:05:50|
    |卷次|363|
    |页码|123081|
    |刊名|Applied Energy|
    |DOI|[10.1016/j.apenergy.2024.123081](http://doi.org/10.1016/j.apenergy.2024.123081)|
    |刊名简称|Applied Energy|
    |ISSN|03062619|
    |添加日期|2025/6/13 11:05:50|
    |修改日期|2025/6/13 11:16:00|
    
    ### 附件
    
    - Lee 和 Yan - 2024 - Will artificial intelligence make energy cleaner .pdf