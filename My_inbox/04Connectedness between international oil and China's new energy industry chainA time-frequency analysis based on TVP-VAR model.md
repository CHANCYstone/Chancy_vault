---
title: "[[论文标题]]"
author: "[[作者]]"
year: [[年份]]
tags: [论文笔记, 研究方法, 关键词]
citekey: 作者年份  # 用于Zotero等文献管理软件的引用键
---
[[读TVP-VAR论文]]

# 0-锐评
## 01-哪里好？

## 02-哪里有点问题？


# 1-摘要
With the growing prominence of global environmental concerns, the interplay between the oil and new energy industries has become increasingly vital. We employ a connectedness approach based on the TVP-VAR model to explore the dynamic connectedness in both time and frequency domains between the oil and various industries within the new energy industry chains. Empirical findings reveal total connectedness of approximately 70 %, primarily manifested as inter-industry associations within the new energy industry and total connectedness predominantly emerges in short term and is sensitive to extreme events. Additionally, the oil and wind power industries have consistently played roles as net recipients of risk. Conversely, the photovoltaic, energy storage, and new energy battery industries have consistently acted as net risk propagators. The roles of the hydroelectric, nuclear power, and new energy vehicle sectors in risk propagation vary with different frequency components. Thirdly, we identify six pairs of industry combinations exhibiting significant two-way spillover effects. Finally, after two robustness tests, the above conclusions remain valid. These research findings offer valuable insights for policymakers and investors.

> [!NOTE]
> **研究背景：**
> 
> - 全球环境问题日益突出，石油和新能源产业之间的相互作用变得至关重要。
> 
> **研究方法：**
> 
> - 采用基于 TVP-VAR 模型的关联性方法。
> - 在时域和频域上探讨石油和新能源产业链中各行业之间的动态关联性。
> 
> **研究发现：**
> 
> - 总体关联性约为 70%，主要表现为新能源产业内部的行业间关联。
> - 总体关联性主要出现在短期内，并且对极端事件敏感。
> - 石油和风电行业始终是风险的净接受者。
> - 光伏、储能和新能源电池行业始终是风险的净传播者。
> - 水电、核电和新能源汽车行业在风险传播中的角色随频率成分而变化。
> - 识别出六对行业组合，它们之间存在显著的双向溢出效应。
> 
> **稳健性检验：**
> 
> - 经过两次稳健性检验，以上结论仍然有效。
> 
> **研究意义：**
> 
> - 为政策制定者和投资者提供有价值的见解


# 2-数据 (Data)

 **研究对象：**

- 国际原油市场（以布伦特原油期货价格为代表）。
- 新能源产业链中各行业的股票市场。

**数据选择：**

- **原油市场：** 布伦特原油期货价格（ICE 和 NYMEX 交易所交易）。
- **新能源产业链：**
    - **新能源生产：** 光伏 (PV)、风电 (WP)、水电 (HP)、核电 (NP) 股票价格指数。
    - **能源储存：** 储能 (ES) 股票价格指数。
    - **新能源应用：** 新能源汽车 (NEV)、新能源电池 (NEB) 股票价格指数。
- 所有新能源指标均使用每日收盘价。

**数据时间范围：**

- 2016 年 1 月 4 日至 2023 年 7 月 31 日（共 1824 个数据点）。
- 涵盖了中美贸易战、COVID-19 疫情和俄乌冲突等重大事件。

**数据来源：**

#### 1 布伦特原油期货价格数据来自 Wind 数据库。
#### 2 新能源产业链行业数据来自 RESSET 金融研究数据库。


![[截屏2025-06-20 11.16.40.png]]




> [!NOTE]
> Our focus primarily encompasses the international crude oil market as well as the stock markets of various industries within the new energy industry chain. We have chosen the Brent crude oil futures price as a representative indicator of the international crude oil market. Brent crude oil futures are traded on both the ICE and NYMEX exchanges and around 70 % of global crude oil futures transactions are priced concerning Brent crude oil, making its futures price a relatively accurate reflection of price fluctuations in the international crude oil market.
> 
> Regarding the new energy industry chain, we have selected seven stock prices from the aspects of new energy production, energy storage, and application, to illustrate the development status of different industries within the new energy industry. Among these, the stock price indices of the photovoltaic industry (PV), wind power industry (WP), hydroelectric index (HP), and the China Securities Index for nuclear power (NP) represent the production aspect of new energy. The stock price index of the energy storage industry (ES) is chosen to signify the energy storage part of new energy. Finally, the stock price indices of the new energy vehicle industry (NEV) and the new energy battery industry (NEB) represent the application industries of new energy. All new energy indicators use the daily closing price as the index price of the day.
> 
> All sample data are collected at a daily frequency, spanning from January 4, 2016, to July 31, 2023. This sample period covers significant events such as the US-China trade war in early 2018, the COVID-19 pandemic in early 2020, and the Russia-Ukraine conflict in early 2022. These events may lead to significant changes in the connectedness between oil prices and the new energy industry chain. Furthermore, the sample period is determined by the intersection of trading days across various markets, resulting in a total of 1824 data points. Brent crude oil futures price data is sourced from the Wind database, while industry data for the new energy chain is obtained from the RESSET Financial Research Database. Furthermore, in alignment with previous research ([Nham, 2022](https://www.sciencedirect.com/science/article/pii/S0140988324006625#bb0305); [Qiao et al., 2022](https://www.sciencedirect.com/science/article/pii/S0140988324006625#bb0310)), we perform a logarithmic differencing on the daily settlement price of Brent crude oil futures and the closing prices of individual new energy stock indices to derive their respective rate of change, and the results are presented in [Fig. 1](https://www.sciencedirect.com/science/article/pii/S0140988324006625#f0005).

# 3-模型 (Model)
#### 2.1.1. TVP-VAR-DY model

#### 2.1.2. TVP-VAR-BK model


> [!NOTE]
> **研究背景：**
> 
> - Baruník and Křehlík (2018) 指出金融市场对不同频率的经济冲击反应不同。
> - 决策者和投资者根据金融市场中不同的频率指标调整经济政策和投资组合 (Baruník and Ellington, 2024)。
> - 因此，理解异质频率指数之间的关联性至关重要。
> 
> **研究方法发展：**
> 
> - 基于 Diebold and Yilmaz (2009, 2012) 的工作，Baruník and Křehlík 开发了频域框架内的溢出指数。
> - Ellington and Baruník (2020) 将 BK 溢出方法与 TVP-VAR 模型结合，提出了新的频域溢出方法，该方法结合了时变特征，本文称之为 TVP-VAR-BK 方法。
> 
> **TVP-VAR-BK 方法的优势：**
> 
> - 继承了 Antonakakis et al. (2020) 提出的 TVP-VAR-DY 模型的优点。
> - 揭示了变量之间在不同频率上的动态关联性，丰富了我们对经济相互关系的理解。
> 
> **TVP-VAR-BK 方法的构建：**
> 
> - 与 TVP-VAR-DY 类似，TVP-VAR-BK 需要一个具有时变特征的响应方程。
> - 不同之处在于，TVP-VAR-BK 在频率域构建这个方程。

# 4-结论 (Conclusion)


![[截屏2025-06-20 11.21.08.png]]


TVP-VAR-BK 模型将数据分为短期（1-5 天）、中期（5-22 天）和长期（超过 22 天）三个部分。这使我们能够分析变量在不同频率上的动态关联性。




# 5-introduction和文献综述

*   **检验方法 (Methods):**
    *   使用了哪些稳健性检验方法？
*   **检验结果 (Results):**
    *   稳健性检验的结果如何？
    *   结果是否支持主要结论？


*   这篇论文对我的研究有什么启发？