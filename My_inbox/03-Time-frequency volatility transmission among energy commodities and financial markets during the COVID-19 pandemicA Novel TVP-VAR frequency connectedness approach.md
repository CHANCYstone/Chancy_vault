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

找不到数据怎么看


# 1-摘要

This paper investigates the dynamic volatility spillover among energy commodities and financial markets in pre-and mid-COVID-19 periods by utilizing a novel TVP-VAR frequency connectedness approach and the **QMLE-based realized volatility data**. Our findings indicate that the volatility
spillover is mainly driven **by long-term components and prominently time-varying with a remarkable but short-lived surge during the COVID-19 outbreak.** We further spot that WTI and NGS are prevailingly transmitting and being exposed to the system volatility simultaneously, especially during the global pandemic, suggesting the energy commodity market becoming more integrated with, more influential and meanwhile vulnerable to global financial markets.
# 2-数据 (Data)

 #### 2.1使用别人的数据
 
 In this paper, we utilize the daily data for the realized volatility (RV) of energy commodities and the other four major asset classes of gold, stocks, bonds and cryptocurrencies. 

 
 **The data set on realized volatilities (RV) is obtained from Da and Xiu (2021) who collect the trade data from Tick Data Inc with the highest frequency available (up to every millisecond) and rinse the data by utilzing the prevalent national best bid and offer (NBBO) after which the realized volatility of nonzero returns for prices is estimated with quasi-maximum**
**likelihood estimates (QMLE) of volatility built on moving-average models MA(q) (Da and Xiu, 2021)**.

> [!NOTE]
> 1. **数据来源和处理：**
>     
>     - 数据来自 Da 和 Xiu (2021) 的研究。
>     - 原始数据是来自 Tick Data Inc. 的高频交易数据（最高可达每毫秒）。
>     - 数据经过清洗，使用了“全国最优买卖报价”（NBBO）。
>     - 使用基于移动平均模型 MA(q) 的准极大似然估计 (QMLE) 来估计非零收益价格的已实现波动率。
> 2. **时间范围：**
>     
>     - 数据集的时间范围是 2018 年 1 月 2 日到 2022 年 4 月 27 日。
>     - 涵盖了疫情前时期（2018 年 1 月到 2019 年 12 月）和疫情中期（2020 年 1 月到 2022 年 4 月）。
> 3. **市场代表：**
>     
>     - 选择了 COMEX 黄金期货、大豆期货、标普 500 指数期货、美元指数期货、美国 10 年期国债期货和 CME 比特币期货的 RV 数据，分别代表非能源商品市场（黄金代表贵金属，大豆代表农产品）、股票市场、外汇市场、债券市场和加密货币市场。
>     - 使用轻质低硫原油（WTI）期货和 NYMEX 天然气期货来研究能源商品市场。

The realized volatility data set ranges from January 2, 2018, to April 27, 2022, which cover a pre-pandemic period (January 2018
to December 2019) and mid-pandemic period (January 2020 to April 2022). The RV data for COMEX Gold futures, Soybean futures,
SP500 futures, Dollar index futures, US 10-year T-note futures and CME bitcoin futures are chosen to proxy for volatilities in the nonenergy commodity markets (gold for precious metal commodity and soybean for agriculture commodity), stock market, forex market,
bond market, and the cryptocurrency market, respectively. We utilize the light sweet crude oil (WTI) futures and NYMEX natural gas
futures to investigate the energy commodity market.

#### 2.2. Preliminary analysis
All the daily realized volatility series are strictly stationary as indicated by the PP test results as shown in Table 1, which satisfies the
demand of TVP-VAR specification. Fig. 1 shows that the Bitcoin market experiences highest volatility throughout the data sample. WTI
encounters a prominent but not lasting volatility spike during the outbreak of the global pandemic, while the natural gas market, gold
and SP500 present a relatively mild but also short-lived increase in volatility level with the outbreak of the COVID-19.

# 3-模型 (Model)



# 4-结论 (Conclusion)

![[截屏2025-06-20 11.05.10.png]]


![[截屏2025-06-20 11.05.24.png]]


![[截屏2025-06-20 11.05.38.png]]



![[截屏2025-06-20 11.05.47.png]]
![[截屏2025-06-20 11.06.01.png]]


# 5-introduction和文献综述

*   **检验方法 (Methods):**
    *   使用了哪些稳健性检验方法？
*   **检验结果 (Results):**
    *   稳健性检验的结果如何？
    *   结果是否支持主要结论？


*   这篇论文对我的研究有什么启发？