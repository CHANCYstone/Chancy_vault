---
title: "[[论文标题]]"
author: "[[作者]]"
year:
  - - 年份
  - - 年份
tags:
  - 论文笔记
  - 研究方法
  - 关键词
citekey: 作者年份
---
[[读TVP-VAR论文]]


```
rm(list = ls())
library(ConnectednessApproach)
library(openxlsx)
library(zoo)

setwd("D:/ai_carbon")
temp =  read.table("ai_recarbon.csv", header = TRUE, sep = ",", row.names = NULL)
data1<-as.zoo(temp[,-1], as.Date(temp[[1]],format='%Y-%m-%d'))
nlag=2  
nfore=100
partition=c(pi+0.00001, pi/21, 0)  

prior = BayesPrior(data1, nlag=nlag)
fit = TVPVAR(data1, configuration=list(nlag=nlag, prior=prior, l=c(0.99,0.99)))
dca = FrequencyConnectedness(Phi=fit$B, Sigma=fit$Q, nfore=nfore, partition=partition) 
dca$TABLE

PlotTCI(dca=dca)
PlotTO(dca=dca)
PlotFROM(dca=dca)
PlotNET(dca=dca)
PlotNPDC(dca=dca)

OverallSp<- data.frame(dca$TCI)  
ToSp<- data.frame(dca$TO)
FromSp<- data.frame(dca$FROM)
NetSp<- data.frame(dca$NET)    
PairSp<- t(data.frame(dca$NPDC)) 

fit1 = VAR(data1, configuration=list(nlag=nlag))
irf = IRF(Phi=fit1$B, Sigma=fit1$Q, nfore=20, orth=TRUE)

sheets_TVP_VAR_BKCI=list("overall"=OverallSp,"to"=ToSp, "from"=FromSp, "net"=NetSp, "pair"=PairSp, "irf"=irf)    

write.xlsx(sheets_TVP_VAR_BKCI,"TVP_VAR_BKCI_recarbon.xlsx", rowNames=T, cloNames=T)
```

# 1-摘要@How are artificial intelligence, carbon market, and energy sector connected? A systematic analysis of time-frequency spillovers

The dual role of artificial intelligence (AI) in [carbon emissions](https://www.sciencedirect.com/topics/economics-econometrics-and-finance/greenhouse-gas-emissions "Learn more about carbon emissions from ScienceDirect's AI-generated Topic Pages") has come under scrutiny. The feedback mechanism in the “AI-Carbon-Energy” system contains the enlightenment of [coordinated development](https://www.sciencedirect.com/topics/earth-and-planetary-sciences/coordinated-development "Learn more about coordinated development from ScienceDirect's AI-generated Topic Pages") of environment and economy. 
Based on the dynamic connectedness index and network diagrams, we quantify 

==**how the AI [industry](https://www.sciencedirect.com/topics/economics-econometrics-and-finance/industry "Learn more about industry from ScienceDirect's AI-generated Topic Pages") is connected to the carbon market and the energy sector in the short-term and long-term.**== 

==如何连接的。。。幽默问题==

Our empirical findings suggest that the **information [spillover](https://www.sciencedirect.com/topics/economics-econometrics-and-finance/spillover-effect "Learn more about spillover from ScienceDirect's AI-generated Topic Pages")** ]]within the system changes over time and across frequency bands. 


==啥是[[information spillovers]]==

- AI 行业、碳市场和能源部门之间相互影响，一个市场的信息（例如，交易量、投资者情绪）会传递到其他市场，影响这些市场的表现。
- 作者使用**动态连接指数和网络图来量化这些信息溢出效应，分析它们如何随时间和频率变化**。

The long-term component drives the overall information spillover. Both the carbon market and the energy sector are closely connected with the AI industry. Specifically, AI industry trading volume is a main information transmitter. Since the release of GPT-4, however, investor attention to the AI industry becomes more important. The carbon market receives a lot of information from the AI industry trading volume and investor attention to the AI industry, particularly since 2023. Nevertheless, the energy sector is only weakly connected to the other two markets. These findings have important implications for policy makers, investors, and producers.



# 2-研究问题 (Research Question)

*   **核心问题 (Main Question):**
    *   研究的核心问题是什么？
    *   问题是否清晰、具体、可衡量？
*   **子问题 (Sub-questions):**
    *   为了回答核心问题，需要解决哪些子问题？
    *   (如果适用)

# 3-数据 (Data)
> 好的，我来帮你把这段英文翻译成中文，保持学术风格：
> 
> ---
> 
> 人工智能的兴起使得人们开始关注其自身产生的碳排放问题，以及能源板块的股票表现。**理论上，投资者的关注会影响其决策，进而影响人工智能产业和碳市场的交易量与收益率（Xu, 2021；Yang 等, 2021；Xu and Lien, 2022）。**
> 
> 例如，噪声交易者往往认为自己掌握了关于风险资产未来价格的特殊信息，并据此制定投资策略。然而，这些错误的信念可能基于媒体报道和社交网络中的传闻信号。成熟交易者则会利用噪声交易者的非理性认知偏差，采取反向投资策略（Xu and Zhao, 2022）。
> 
> **因此，在人工智能产业方面，我们选取了三个指标：投资者对人工智能产业的关注度、中国股市人工智能指数的日收益率和交易量。**
> 
>   
> **在碳市场方面，我们同样考虑投资者关注度，以及中国碳排放配额（CEA）的收益率和交易量。**
> 
> 
> 鉴于**碳排放与包括化石能源和可再生能源（RES）在内的能源来源紧密相关，我们进一步考察中信一级行业指数中的石油石化行业指数（CII-PP）、煤炭行业指数（CII-Coal）、以及电力设备与新能源行业指数（CII-PENE）的股票收益率。**
> 
>   
> 
> 本研究使用的日度数据涵盖九个指标，时间区间为2022年1月5日至2023年10月16日，即AI股票指数正式发布以来的时期。**所有数据均来自iFinD和WIND数据库。** 其中，投资者关注度由iFinD数据库提供的综合新闻指数（CNI）来衡量。
> 




The focus on AI has brought attention to carbon emissions from itself and the stock performance in the energy sector. **Theoretically, investors' attention impacts their decisions, which in turn affects the trading volume and return of the AI industry and the carbon market ([Xu, 2021](https://www.sciencedirect.com/science/article/pii/S0140988324001853#bb0310); [Yang et al., 2021](https://www.sciencedirect.com/science/article/pii/S0140988324001853#bb0350); [Xu and Lien, 2022](https://www.sciencedirect.com/science/article/pii/S0140988324001853#bb0320)).** 


For example, noise traders believe that they have special information about the future price of the risky asset and formulate their investment strategies accordingly. These incorrect beliefs may be based on signals from rumors in media reports and social networks. Sophisticated traders exploit the irrational misperceptions of noise traders and adopt contrarian investment strategies ([Xu and Zhao, 2022](https://www.sciencedirect.com/science/article/pii/S0140988324001853#bb0330)). 

**Therefore, for the AI industry, three indicators are employed, i.e., investor attention to the AI industry, daily returns and trading volume of the AI index of the Chinese stock market.** 

**For the carbon market, we also consider investor attention to it and the trading volume and return of China Emission Allowance (CEA).** 

Given **the tight link between carbon emissions and energy sources including [fossil](https://www.sciencedirect.com/topics/earth-and-planetary-sciences/fossil "Learn more about fossil from ScienceDirect's AI-generated Topic Pages") and RES, we investigate the [stock returns](https://www.sciencedirect.com/topics/economics-econometrics-and-finance/capital-market-returns "Learn more about stock returns from ScienceDirect's AI-generated Topic Pages") of the CITIC Industry Index of petroleum petrochemical industry (CII-PP), [coal industry](https://www.sciencedirect.com/topics/economics-econometrics-and-finance/coal-industry "Learn more about coal industry from ScienceDirect's AI-generated Topic Pages") (CII-Coal), and power equipment and new energy industry (CII-PENE).** 









The daily data employed consists of nine indicators from January 05, 2022 to October 16, 2023, starting with the official launch of the AI stock index. **All data are available from the iFinD and WIND databases.** Specifically, investor attention is measured by the Comprehensive News Index[1](https://www.sciencedirect.com/science/article/pii/S0140988324001853#fn0005) (CNI) provided by the iFinD database.


**数据：**


==就430条==

AI
碳市场
能源用了煤炭石油和新能源

### 不同之处：





![[截屏2025-06-04 11.19.31.png]]


![[截屏2025-06-04 11.24.53.png]]

[Fig. 1](https://www.sciencedirect.com/science/article/pii/S0140988324001853#f0005)(a) displays the trading volume of the AI industry and the investor attention to it. Clearly, the AI industry attention fluctuates widely. 

For example, the CNI for AI increases from 51,761 to 676,369 in about four months (from January 20, 2023 to May 31, 2023), showing a breakout in investor attention to AI industry. 

Although many studies report a strong correlation between investor attention and trading volume, e.g., [Aouadi et al. (2013)](https://www.sciencedirect.com/science/article/pii/S0140988324001853#bb0025) and [Wang (2017)](https://www.sciencedirect.com/science/article/pii/S0140988324001853#bb0285), [Fig. 1](https://www.sciencedirect.com/science/article/pii/S0140988324001853#f0005)(a) indicates that the co-movement between AI trading volume and AI industry attention appears to be weak, particularly before April 2023. From May 2023 to October 2023, both indicators show a downward trend. 

 The Pearson correlation further suggests that the linear correlation between AI trading volume and AI industry attention is statistically insignificant from January 2022 to April 2023 (0.004, _t_-statistic = 0.080). Therefore, the correlation between AI industry attention and AI trading volume is time-varying.


**Fig. 2 shows the returns on five indicators for the three markets, i.e., the AI industry index, CEA, CII-Coal index, CII-PENE index, and CII-PP index.** 
Specifically, all returns are calculated by 1**00 ×( lnPt lnPt_1),** where **Pt denotes the index or the closing price of CEA on day t**. On the one hand, four of the five indicatorsare highly volatile in the first half of the sample period. The only exception is the CEA return, which is more fluctuating in the second half of the sample period. On the other hand, given the sharp fluctuations of the indicators in the short-term, the link of the “AI-Carbon-Energy” system appears to be stronger in the longterm than in the short-term. Table 1 summarizes the de

![[截屏2025-06-05 11.38.36.png]]


![[截屏2025-06-05 11.46.34.png]]



# 4-模型 (Model)与实证结果

```
rm(list = ls())
library(ConnectednessApproach)
library(openxlsx)
library(zoo)

setwd("D:/ai_carbon")
temp =  read.table("ai_recarbon.csv", header = TRUE, sep = ",", row.names = NULL)
data1<-as.zoo(temp[,-1], as.Date(temp[[1]],format='%Y-%m-%d'))

# 这段代码后续可以抄，就是搞一个标准文件 然后用zoo来load


nlag=2  
nfore=100
partition=c(pi+0.00001, pi/21, 0)  

prior = BayesPrior(data1, nlag=nlag)
fit = TVPVAR(data1, configuration=list(nlag=nlag, prior=prior, l=c(0.99,0.99)))
dca = FrequencyConnectedness(Phi=fit$B, Sigma=fit$Q, nfore=nfore, partition=partition) 
dca$TABLE

PlotTCI(dca=dca)
PlotTO(dca=dca)
PlotFROM(dca=dca)
PlotNET(dca=dca)
PlotNPDC(dca=dca)

OverallSp<- data.frame(dca$TCI)  
ToSp<- data.frame(dca$TO)
FromSp<- data.frame(dca$FROM)
NetSp<- data.frame(dca$NET)    
PairSp<- t(data.frame(dca$NPDC)) 

fit1 = VAR(data1, configuration=list(nlag=nlag))
irf = IRF(Phi=fit1$B, Sigma=fit1$Q, nfore=20, orth=TRUE)

sheets_TVP_VAR_BKCI=list("overall"=OverallSp,"to"=ToSp, "from"=FromSp, "net"=NetSp, "pair"=PairSp, "irf"=irf)    

write.xlsx(sheets_TVP_VAR_BKCI,"TVP_VAR_BKCI_recarbon.xlsx", rowNames=T, cloNames=T)

```



# 1.静态

静态连通性对应于没有考虑VAR模型参数动态变化的结果。换句话说，我们基于参数恒定的 VAR 模型来展示整个样本周期的连通性。

表 2 总结了面板 A、B 和 C 中的整体静态连通性以及高频和低频段的结果。在每个面板中，非对角元素显示两个变量之间的相互作用。例如，在面板A的第一列中，52.63%的连通性归因于人工智能行业关注度（即AAI）的冲击，其余47.37%来自系统中的其他变量。关注总连通性指数（即TCI），可以观察到整个样本期间的TCI为28.56%，其中短期的12.45%（如B图所示）和长期的16.11%（如C图所示）。

因此，平均而言，系统内28.56%的预测误差方差可归因于其本身，而每个变量的特殊项捕获的其他因素则贡献了剩余的71.44%。因此，与国际原油网络（Chatziantoniou et al., 2023）、美国金融业（Baruník and Krˇehlík, 2018）等其他系统的连通度超过50%相比，碳市场、人工智能产业和能源部门之间的整体连通度并不大。同时，表2显示，“AICarbon-Energy”系统的连通性主要由长期冲击传导驱动，这与碳市场、能源股等许多其他系统不同（Xu和Li，2023）。就个体变量而言，我们发现人工智能产业（即VAI）的交易量是系统内主要的整体净传送者（净连通度为65.90%），其次是CII-PP回报率（3.26%）。总体净受益者是投资者对碳市场和人工智能行业的关注（即ACEA和AAI），其次是CEA交易量（即VCEA）和CII-PENE回报（即RCII PENE）。从频段来看，AI行业交易量对系统的影响长期（60.57%）大于短期（5.33%），而CII-PP回报则相反。更重要的是，某些变量的作用在不同的时间范围内可能会有所不同。例如，虽然碳市场投资者注意力（即ACEA）在短期内是净传送者（2.91%），但在长期内却是净接收者（32.90%）。相比之下，煤炭和PENE行业的回报在短期内是净受益者（分别为2.39%和5.62%），但从长期来看则成为净回报者（分别为0.63%和0.34%）。 CEA和人工智能行业（即RCEA和RAI）的回报主要传递的是长期冲击，而不是短期冲击。


# TCI

表2的结果显示了“人工智能-碳-能源”系统内的平均连通性，但掩盖了市场之间相互作用的重要变化。因此，我们继续计算“AI-碳-能源”系统的动态连通性。图3显示了基于TVP-VAR框架的动态TCI，及其短期（黑线）和长期（红色阴影区域）的分解。蓝色阴影区域代表的总体 TCI 表明它是随时间变化的，在 24% 到 32% 之间波动。总体 TCI 在此之前呈上升趋势，并于 2022 年 11 月达到峰值。自2022年12月中国全面解除对COVID-19大流行的控制以来，整体TCI开始下降，直到2023年4月。因此，系统的连通性似乎与重要的政策变化相关。 2023年3月和2023年4月，随着GPT-4的发布，人工智能行业取得了巨大突破和成果，投资者对其关注度再创新高（如图1所示）。与此同时，东航的回报率也达到区域峰值。显然，关键发展对碳市场、人工智能产业、能源部门和系统的连通性产生重要影响。样本期内，**短期TCI一般小于长期TCI**。在资产价格由具有不同周期性成分的消费增长驱动的金融体系中，异质反应的冲击会产生不同程度的持续性联系。因此，长期TCI的强劲表明一个市场对其他市场的反应相对持久，这是系统性关联性的主要来源。换句话说，“AI-CarbonEnergy”系统处理信息的速度并不快，即信息传输需要一个日历月。由此可见，最近21个交易日至前100个交易日的窗口内发生的震荡对系统的连通性影响较大。此外，从长远来看，这三个市场似乎更加一体化。与整体TCI类似，长期关联性在2022年11月和2023年4月左右变得更加突出。短期关联性也有类似的波动。因此，重大政治经济事件也会在短期内影响三个市场的连通性。长期和长期。这一发现与重要事件影响系统连通性的文献一致，例如 COVID-19 大流行影响通货膨胀连通性（Xu 和 Lien，2024）。

# NET

识别“AI-碳-能源”系统中的哪些变量通过在不同的时间传递冲击来驱动系统的发展。

为了识别“AI-碳-能源”系统中哪些变量通过不同频率的冲击来驱动系统的发展，我们计算了动态净TCI，并将其呈现在图4中。根据图4，我们可以识别不同时间的净传输者和净接收者。正的网络连通性意味着对应的变量是系统中其他变量的网络信息传递者。反之，负值表示对应变量是其他变量的净信息接收者。在图4中，整体网络连通度由蓝色阴影区域表示，短期和长期网络连通度分别由黑色实线和红色虚线表示。对于人工智能行业，我们注意到，在大部分样本期内，人工智能行业关注度一直充当持续的净信息接收器，直到2023年5月10日，此时它停止了长期上升趋势并开始下降（见图1）。与 TCI 的变化类似，2023 年 4 月 GPT-4 的发布似乎改变了 AI 行业关注度在网络中的角色。此后，AI行业关注度成为网络信息传递者，直至样本期结束。人工智能行业关注度的长期净TCI与整体网络连通度较为相似，均在2023年5月左右从网络信息接收者转变为网络发送者。但在高频段，即不到21个交易日，人工智能行业关注度表现为持久性网络发送者，净TCI范围为0.77%至8.54%。虽然人工智能行业注意力投资者在短期内是信息发送者，但从长期来看，至少在2023年5月之前，它主要是信息接收者。尽管如此，图4表明人工智能行业注意力的角色在样本期内发生了变化。人工智能行业的巨大突破，使得投资者对其的关注成为长期的信息传递者。因此，从投资者的关注度来看，人工智能产业在网络中的重要性得到了加强。相比之下，考虑到整体网络连通性及其在短期和长期范围内的分解，人工智能行业的交易量是一个持续的网络信息传递者。人工智能交易量的净TCI范围为41%至106%，显示其对“人工智能-碳-能源”系统中其他因素的显着影响。长期净TCI与整体净TCI表现出相似的趋势，范围为36%至99%，表明人工智能行业交易量对其他人具有较强的长期影响。虽然短期净TCI远小于长期效应（2.43%~8.69%），但持续为正，表明人工智能行业的交易量在短期内也是一个净信息传递者。与人工智能行业的投资者关注度和交易量相比，人工智能行业回报的网络连通度数值较小，表明该指标在整个网络中的重要性不强。再次，对于频段的差异，AI行业更注重长期的连通性。谈到碳市场，其总体情况与人工智能行业有很大不同。尤其是，除2022年7月18日至2022年8月31日总体TCI为正值的期间外，投资者对碳市场的关注在整个样本期内都发挥着相当大的净信息接收者作用。 2022年8月至2023年7月，整体关联性和长期关联性更加普遍，净TCI分别从4.28%下降至68.80%，从0.01%下降至70.42%。从长期来看，碳市场关注度更多地受到系统中其他变量的影响，因为碳市场关注度的大小

其净 TCI 大于总体结果。与此同时，短期网络连通性保持正值，并随着时间的推移而变得不那么普遍。如表1所示，投资者对人工智能的关注度与对碳市场的关注度在统计上呈负相关，这符合注意力资源有限理论，即人类注意力是识别和处理信息的认知资源（Wickens，2020），影响股票交易和收益（Yang等，2021）。尽管如此，图4表明，人工智能行业关注度和碳市场关注度可能会同时受到其他因素的影响，至少在2022年1月至2023年4月期间，这两个指标主要是净信息接收者。 2022年1月5日至2022年12月20日、2023年4月5日至2023年10月16日，东航交易量作为净信息接收者。全国碳市场“潮沙现象”突出，年初、年末交易量较高，年中表现相对较低。 2022年2月至10月，东航交易量持续低迷，多数天数低于50万吨。但2022年11月和2022年12月，CEA交易量出现明显回升，其角色从网络信息接收者转变为网络信息发送者。直到2023年4月，AI行业关注度激增，CEA交易量再次成为净接收者。长期净连通度与整体净TCI相似。参考高频段，即少于21个交易日，相应的净TCI幅度较小，范围为1.32%至5.00%。在大多数情况下，CEA交易量是短期的净信息传递者。唯一的例外是 2022 年 4 月至 12 月，此时网络连通性略大于零。与AI产业回报类似，CEA回报在系统中的重要性并不强。就能源领域而言，与人工智能行业和碳市场相比，传统能源企业和可再生能源企业在系统中的重要性都较低。能源行业的一个显着特点是其整体关联度与短期业绩相关性更强。具**体而言，煤炭回报（CII-Coal）和电力设备和新能源回报（CII-PENE）在短期内普遍为净接收者，这与整体TCI类似**。相比之下，网络TCI的长期演进的特点是发送和接收信息之间的多次转换。这一发现与Xu和Li（2023）的观点一致，灰色和绿色股票与碳市场之间的长期关联性是时变的，这可以归因于投资者对煤炭市场供需水平以及实际燃料成本的心理预期（Lin和Chen，2019）。石油和石化行业 (CII-PP) 的总体情况与其他两个行业不同。其净TCI在两个频段上均主要为正，表明它总体上是系统中的净信息发射器。就石油石化行业的影响而言，其作为净传输者的作用与Xu（2021）的发现一致，国际原油市场和中国国内原油市场对中国两个具有代表性的碳试点具有显着的溢出效应。 CII-PP的总体净TCI范围为0.64%至6.49%，表明与人工智能行业和碳市场相比，其对其他方面的净影响相对较弱。煤炭与石油石化行业的相反表现可能源于我国煤炭丰富、石油稀缺的资源禀赋。中国煤炭工业协会发布的《2022年煤炭工业发展年度报告》2显示，基于国家资源禀赋和能源安全考虑，短期内煤炭在我国能源消费中的主导地位不会改变。不过，随着中国推动发展绿色转型，加快实施新能源和可再生能源替代传统能源，钢铁、建材等主要煤炭消​​费行业的需求可能会减弱。这使得煤炭、电力和新能源行业在不同的频段发挥着不同的作用。短期来看，随着发电企业受到全国碳市场的监管，碳市场和人工智能产业的动力将传导至煤炭和电力企业。从长远来看，煤炭资源在宏观经济中的主导地位使其成为系统中的信息传递者。因此，我们认为人工智能行业和碳市场对重大事件做出反应，并且这些动态可以通过长期连通性很好地捕捉到。人工智能产业交易量是“人工智能-碳-能源”系统中主要的信息发送者，而人工智能产业关注度、碳市场关注度、CEA交易量一般是主要信息接收者。鉴于网络连通性较小，能源部门在系统中的重要性似乎较低。尽管如此，煤炭行业、电力装备和新能源行业（CII-Coal和CIIPENE）仍然持续充当信息接收者的角色，而石油石化行业（CII-PP）主要是信息发送者。


# npdc

网络成对连通性提供了“人工智能-碳-能源”系统关系随时间演变的更精细的图景。由于我们在系统中包含 9 个变量，因此将有 36 对组合。因此，我们识别出净配对连通性较大的指标组合，并将其绘制在图5中。具体来说，选择了四个指标，即人工智能行业关注度、人工智能交易量、碳市场关注度和CEA交易量。这一选择与图4所示的净TCI所表示的因素重要性一致。虽然碳市场关注度与三种能源回报之间的净配对关系超过3%，但远小于所选配对的净关联度。因此，为简洁起见，此处未报告其他对的结果。
同样，图 5 中的所有图都表明长期成分驱动整体网络成对连通性。图 (a) 显示了人工智能行业关注度与人工智能行业交易量之间的净成对关联度。直到2023年9月，AI行业关注度受到AI行业交易量的净冲击。此后，净信息传递走向相反的方向，即人工智能行业关注度对人工智能交易量产生净信息溢出。这一发现与之前许多关于投资者注意力影响交易活动和交易量的研究一致，例如Yang等人。 （2021）。图（b）显示人工智能行业关注度和碳市场关注度相互作用。具体而言，直到2023年2月，人工智能行业关注度都会受到碳市场关注度的冲击，并在此后将冲击传导至碳市场。同期，人工智能行业关注角色从网络接收者转变为网络发送者（见图4）。这一发现可以用有限注意力理论来解释，即注意力是一种稀缺的认知资源，因此投资者只将有限的注意力投入到个人选择上（Johnston and Pashler，1998）。人工智能行业关注度对碳市场影响（投资者关注度和交易量）的变化也反映出投资者对人工智能行业的高度关注，这使其成为2023年4月以来系统中的净传输者。

那么，AI交易量显然会传导对CEA交易量和碳市场关注度的冲击，分别如图(c)和(d)所示。也就是说，人工智能产业交易量对碳市场具有很强的净溢出效应。一方面，这一发现表明，以人工智能产业为代表的技术进步确实对中国的碳减排发挥了重要作用，特别是从长期来看。另一方面，AI交易量主要对CEA交易量产生直接影响，因为相对于图5中的其他对，碳市场关注度和CEA交易量之间的净配对关联性相对较小（图（f））。碳市场关注度对CEA交易具有净溢出效应

总体而言，净配对连通性的方向和大小都支持图4所示的结果。“AICarbon-Energy”系统的联系紧密，每个市场的变量可以是特定区间内的净信息发送者或净接收者。从频段来看，我们发现长期连通性通常更具有相关性；然而，短期成分对于某些目的也很重要，特别是在能源部门。


# 网络

根据方向性连通性，我们发现 2023 年 4 月是一个重要的结构性断裂日期，这可能归因于 GPT-4 的发布。因此，我们基于整个样本和两个子样本的净成对连通性（即2022年1月5日至2023年3月31日和2023年4月1日至2023年10月16日）提出了“AI-碳-能源”系统的网络结构。在图6中，每个节点代表一个变量。值得注意的是，红色（绿色）的节点表示它是网络信息发送器（接收器）。节点的大小说明了该节点的净溢出效应的强度，即净信息溢出效应的绝对值。边的宽度表示两个节点之间成对溢出的大小，箭头指向信息接收者。同时，我们使用紫色和蓝色分别反映强和弱的成对溢出效应。具体来说，我们将大于 3% 的成对溢出定义为强溢出。


图6显示，GPT-4发布前后的网络结构不同。一是2023年4月以来AI行业关注度和碳市场关注度均净贡献增加。它们在图（g）和（i）中的节点大小大于图（d）中的节点大小
和 （f）。其次，相比之下，长期来看，AI 行业交易量的净贡献自 2023 年 4 月以来有所减弱。直到 2023 年 3 月，AI 行业交易量对 AI 行业关注度具有很强的净溢出效应，而此后则相反。
第三，地块（g）、（h）和（i）中的紫色边多于地块（d）、（e）和（f），这意味着前者节点之间的成对溢出更强。因此，自 2023 年 4 月以来，网络跨频率的连接更加紧密。
第四，2023年4月后，能源板块受AI行业影响更大。在 2023 年 3 月之前，CEA 交易量对 CII-PP 回报的净成对溢出效应很强，在图 （d） 中。对于其他两个能源回报，它们与人工智能行业和碳市场的净成对溢出效应相对较弱。然而，在图（g）中，CII-PP收益和CII-Coal收益受AI行业交易量影响较大，CII-PP收益甚至对碳市场关注度产生净溢出效应。
第五，能源部门对网络的重要性主要体现在短期内。如图（f）和（i）所示，即从长远来看，三个能量指标的节点较小，相关边缘为蓝色，从而表明相应的净成对溢出相对较弱。短期内，即图（e）和（h）中，能源行业与人工智能产业相连。总体而言，这些网络给出了几个值得注意的发现。具体来说，在不同的频率和不同的样本中，人工智能行业往往是“AI-CarbonEnergy”系统中的主要信息传递者，GPT-4的发布似乎进一步凸显了人工智能行业关注的重要性。



# 结论
拉赫曼尼安，F.等人。 (2024)，关注化学不可知论和可解释的电池寿命预测，https Rahmanian, F. 等人。 (2024)，关注化学不可知论和可解释的电池寿命预测。对人工智能行业的巨大关注激发了人们对其对碳排放影响的日益浓厚的兴趣。鉴于AI产业在碳排放方面的双刃剑作用，本文旨在探讨“AI-碳-能源”系统的连通性。我们聚焦于全球最大的排放国中国，考察人工智能产业与碳市场、能源领域的联系。本研究基于动态频率连通性指数和网络方法，考察了短期和长期的整体和定向溢出效应。我们将研究结果总结如下。首先，总体来看，长期成分驱动“AI-碳-能源”系统整体信息溢出，信息处理速度缓慢。其次，AI产业是“AI-碳-能源”体系中最重要的。具体来说，投资者对AI行业的关注是该系统从2023年5月低频段GPT-4发布后不久开始从网络信息接收器转变为网络发送器的重要节点。在高频段，AI行业关注度是持续性的信息传递者，但影响力相对较弱。同时，人工智能行业的交易量在所有频率上都充当了持久而强大的网络信息发射器。第三，碳市场主要是一个信息接收者，尤其是长期信息接收者。投资者对碳市场的关注收到了信息，尤其是来自人工智能行业的信息。第四，能源行业与其他两个市场之间的联系较弱，尤其是从长期来看。即便如此，石油石化行业在系统中充当了信息传递者的角色。最后，投资者注意力是传递信息的重要节点，通过它，碳市场、人工智能产业和能源领域紧密相连。因此，政府可以通过制定政策法规来引导投资者关注，引导投资向低碳绿色技术发展，推动人工智能在能源行业的创新和应用。同时，政府可以要求企业在碳排放、环境保护等方面进行全面的信息披露，帮助投资者更好地了解企业的​​可持续绩效，促进更加环保的投资决策。这项研究具有重要的政策意义。对于政策制定者来说，这项研究提供了有关“AI-碳-能源”系统连通性的重要信息，有利于制定三个市场的协同策略。鉴于碳市场与人工智能产业的紧密联系，特别是人工智能产业的关注，政府可以通过引导投资者的关注，鼓励和支持人工智能技术在碳市场的应用，提高碳减排效率，降低碳排放成本。这可能包括为人工智能在碳监测、碳交易分析、碳减排技术等方面的研发和应用提供财政支持。能源和人工智能行业之间的薄弱联系表明，政策制定者应鼓励能源公司与人工智能行业合作，以推动能源行业的创新和效率。例如，可以通过提供激励计划、研发资金或税收优惠等方式，引导能源企业采用先进的人工智能技术，提高生产效率，降低碳排放，更好地适应碳市场的变化。人工智能产业、碳市场和能源领域相互影响、相互制约，需要加强价格机制、市场政策和绿色认证的协调，形成推动低碳经济转型的最大协同效应。考虑到人工智能产业巨大的碳排放效应，应推动人工智能产业碳控减排政策与碳市场政策，特别是可再生能源相关政策的关联和耦合。换句话说，具有技术意识的气候政策对于整体经济与环境的协调发展是必要的。此外，鉴于“AI-碳-能源”体系关联性较弱，政策应进一步提高投资者对碳市场、AI板块、能源股的认识。通过提供准确信息、加强宣传、开展教育活动，可以促使投资者更全面地考虑这些领域的投资机会，从而促进系统的良性互动。这些结果也引起了生产者和投资者的潜在兴趣。对于生产商来说，我们的研究结果表明人工智能正在成为新能源和传统能源及环境行业的关键推动者。因此，能源行业、公用事业、电力运营商和生产商如果想保持长期竞争力，就需要更加关注人工智能技术的发展。对于投资者来说，可能存在多元化机会，尤其是从长期来看，因为能源行业与人工智能行业和碳市场的联系并不紧密。相比之下，短期内，人工智能行业和能源行业之间的投资组合重新平衡是必要的，因为它们之间存在显着的溢出效应。最后，在制定投资策略时，应考虑投资者关注度对本市场及相关市场的影响。







、、、、、、、、、、

人工智能行业与碳市场之间的紧密联系表明，这两个行业之间的相关性已经受到投资者的广泛关注。这体现在两个市场关注度之间的强烈溢出效应上，尤其是长期来看，CEA 交易量受到 AI 行业关注度的强烈影响。因此，投资者的注意力对于市场之间的联系很重要，这一发现与之前的许多研究一致，例如 Yang 等人 （2021）、Xu 和 Lien （2022） 以及 Xu 和 Zhao （2022）。而AI行业强势
和 （f）。其次，相比之下，长期来看，AI 行业交易量的净贡献自 2023 年 4 月以来有所减弱。直到 2023 年 3 月，AI 行业交易量对 AI 行业关注度具有很强的净溢出效应，而此后则相反。第三，地块（g）、（h）和（i）中的紫色边多于地块（d）、（e）和（f），这意味着前者节点之间的成对溢出更强。因此，自 2023 年 4 月以来，网络跨频率的连接更加紧密。第四，2023年4月后，能源板块受AI行业影响更大。在 2023 年 3 月之前，CEA 交易量对 CII-PP 回报的净成对溢出效应很强，在图 （d） 中。对于其他两个能源回报，它们与人工智能行业和碳市场的净成对溢出效应相对较弱。然而，在图（g）中，CII-PP收益和CII-Coal收益受AI行业交易量影响较大，CII-PP收益甚至对碳市场关注度产生净溢出效应。第五，能源部门对网络的重要性主要体现在短期内。如图（f）和（i）所示，即从长远来看，三个能量指标的节点较小，相关边缘为蓝色，从而表明相应的净成对溢出相对较弱。短期内，即图（e）和（h）中，能源行业与人工智能产业相连。总体而言，这些网络给出了几个值得注意的发现。具体来说，在不同的频率和不同的样本中，人工智能行业往往是“AI-CarbonEnergy”系统中的主要信息传递者，GPT-4的发布似乎进一步凸显了人工智能行业关注的重要性。人工智能行业与碳市场之间的紧密联系表明，这两个行业之间的相关性已经受到投资者的广泛关注。这体现在两个市场关注度之间的强烈溢出效应上，尤其是长期来看，CEA 交易量受到 AI 行业关注度的强烈影响。因此，投资者的注意力对于市场之间的联系很重要，这一发现与之前的许多研究一致，例如 Yang 等人 （2021）、Xu 和 Lien （2022） 以及 Xu 和 Zhao （2022）。虽然人工智能行业在长期内对碳市场产生强烈影响，但其对能源行业的影响主要体现在短期内。AI产业与碳市场密切相关，但与能源板块的关系较弱，反映出AI在能源行业的应用还不够深入。GPT-4发布后，AI产业虽然对能源行业有短期影响，但长期影响较弱。虽然人工智能解决方案是电力行业和可再生能源的未来（Hannan 等人，2021 年），但人工智能的高成本似乎阻碍了两个行业的融合。鉴于人工智能产业的快速发展及其对能源行业的潜在好处，例如提高效率和带来工资溢价（Lyu 和 Liu，2021），它们的融合有望加深。令人惊讶的是，碳市场与能源部门之间的联系性很弱。火电企业同时参与碳市场、电力市场和能源市场，通过共同的市场主体将三个市场连接起来。碳市场与能源部门的衔接性较弱，可能是因为中国全国碳市场仅覆盖电力行业，而电价由国家能源局制定和管理，尚未形成市场化的电价机制。因此，能源消费和碳排放权交易之间的信息传递和成本传递并不畅通，导致两个市场之间的联系薄弱。从国际实践来看，在电力市场化条件下，碳价可以传导到电价上，电价也会对碳价产生不利影响（Keppler and Mansanet-Bataller，2010）。一方面，碳价会叠加在电力市场火电企业的报价上，从而影响成交价格。另一方面，电力市场的供需情况和价格变化会影响火力发电，电力生产的变化会影响碳配额购买需求，进而影响碳价。因此，碳市场与能源部门的弱衔接可能源于中国的电价机制。此外，碳市场与能源部门之间的联系性较弱也可能是由于碳市场成熟度不足造成的。市场参与者较少、机制不完善、信息不对称会降低投资者对碳市场的信心，从而影响投资者参与，转向更成熟、更受关注的能源股市，从而降低两个市场之间的联系性。这反映了碳市场与能源部门之间的低效价格传导和信息传递渠道，这与现有文献的研究结果一致（Xu et al.， 2022）。











### 1.不同时间段的connectedness ✅
The results in Table 2 show the average connectedness within the “AI-Carbon-Energy” system, but mask important changes in the in teractions between markets. Therefore, we proceed to calculate the dynamic connectedness of the “AI-Carbon-Energy” system.

尽管表 2 展示了 "AI-Carbon-Energy" 系统内的平均连接程度，但它忽略了市场间互动的重要动态变化。 因此，作者决定进一步计算 "AI-Carbon-Energy" 系统的动态连接性。


**事实上这个表直接可以得到**
### 2.Dynamic Total Connectedness Index

Fig. 3 displays the **dynamic TCI based on the TVP-VAR framework, and its decomposition in the short-term (black line) and in the long-term (redshaded area)**.
1. The overall TCI represented by the blue-shaded area suggests that it is time-varying and fluctuates between 24% and 32%. The overall TCI **peaks in November 2022**, after an upward trend prior to that. 
2. Since China fully lifted the control on the COVID-19 pandemic in December 2022, the overall TCI starts to decline until April 2023. Therefore, **it appears that the connectedness of the system is associated with important policy changes**. In March and April 2023, with the release of GPT-4, the AI industry made great breakthroughs and achievements, and the investor attention to it reaches a new high (as shown in Fig. 1). At the same time, the return on CEA also reaches a regional peak. Clearly, critical developments have important impacts on the carbon market, the AI industry, the energy sector, and the connectedness of the system.


> [!NOTE] Title
> 1.总体概述
> 2.和大的经济事件相联系

1. During the sample period, **the short-term TCI is generally smaller than the long-term TCI. In a financial system where asset prices are driven by consumption growth with different cyclical components, shocks with heterogeneous responses create linkages with different degrees of persistence.** ==Therefore, the strong long-term TCI indicates that the response of one market to others is relatively persistent, which is the main source of systemic connectedness==. **In other words, the “AI-CarbonEnergy” system does not process information very quickly, i.e., information is transmitted over a calendar month.** 


2. Thereby, the shocks that occurred in the windowfrom the last 21 tradingdays to 100 tradingdays prior have a strong impact on the connectedness of the system. Also, **the three markets appear to be more integrated in the long-term**. Similar to the overall TCI, the long-term connectedness becomes more prominent around November 2022 and April 2023. There are similar fluctuations in the short-term connectedness. Therefore, major political and economic events also affect the connectedness of the three markets in the short-term and long-term. This finding is consistent with the literature that important events affect system connectedness, such as the COVID-19 pandemic impacts inflation connectedness.


> [!NOTE] Title
> 1.长短期比较，为什么长期是系统关联性的主要来源。长期占得面积更大，说明这个系统处理信息的速度并不是那么的快
> 2.车轱辘话，继续强调长期影响的重要性








好的，这是将您提供的关于**静态连接度分析结果**的要点组织成的流畅、连贯的中文段落：

---

> [!NOTE]
> ### 静态连接度分析：AI-碳市场-能源系统
> 
> 本研究的**静态连接度**结果是基于**参数恒定**的VAR模型，展示了**整个样本期**内的系统连接性。总连接度指数（TCI）为 **28.56%**，这意味着系统中 **28.56%** 的预测误差方差可归因于系统内部变量间的相互溢出，而其余的 **71.44%** 则归因于各变量的特异性因素。这一TCI值相对较低，表明该“AI-碳市场-能源”系统的整体连接度**不及**国际原油或美国金融市场等其他系统（其连接度通常超过50%）。从频域分解来看，该系统的连接度主要由**长期冲击传导（16.11%）**驱动，而非短期冲击（12.45%），这与其他许多系统存在显著差异。
> 
> 在个体变量层面，**AI行业交易量（VAI）**是系统中最主要的**总体净发送者**，净连接度高达 **65.90%**，其次是CII-PP回报率（3.26%）。相反，**碳市场和AI行业的投资者关注度（ACEA和AAI）**是主要的**净接收者**。更值得注意的是，变量的角色会随时间跨度发生变化：例如，**碳市场投资者关注度（ACEA）**在**短期**内是净发送者（2.91%），但在**长期**内却转变为强烈的净接收者（32.90%）。类似的，煤炭和PENE行业回报率在短期是净接收者，但长期则变为净发送者。此外，**AI行业交易量（VAI）**对系统的冲击传导也主要体现在**长期**（60.57%），而非短期（5.33%）。
> 
> 






![[截屏2025-06-05 12.05.04.png]]



> [!NOTE]
> 这段文字描述了**动态连接度分析（Dynamic Connectedness Analysis）**的结果，突出了系统相互作用随时间的变化。
> 
> 以下是清晰、学术化的翻译，并组织成流畅的段落：
> 
> ---
> 
> ## 动态连接度分析：系统互动的时间变异性
> 
> **静态连接度**结果（如表2所示）仅代表“AI-碳市场-能源”系统的平均连接度，容易掩盖市场间相互作用的**重要动态变化**。因此，本研究通过计算**动态连接度**来捕捉这种时变性。
> 
> ### 动态 TCI 的波动与事件驱动
> 
> **图3**展示了基于**TVP-VAR框架**的动态总连接度指数（TCI）及其在短期（黑线）和长期（红色阴影区域）的分解。
> 
> - 由蓝色阴影区域代表的**总体TCI**是**时变的**，波动范围在 **24% 到 32%** 之间。
>     
> - 总体TCI在**2022年11月达到峰值**，此前处于上升趋势。随着中国在2022年12月全面解除新冠疫情管制，总体TCI开始下降，直至2023年4月。这表明系统的连接度与**重要政策变化**密切相关。
>     
> - 在2023年3月和4月，随着 **GPT-4的发布**，AI行业取得重大突破，投资者关注度（如图1所示）达到新高，同时CEA回报率也达到局部峰值。这清晰地表明，**关键性事件发展**对碳市场、AI行业、能源部门以及系统的连接度具有重要影响。
>     
> 
> ---
> 
> ### 长期连接度的主导作用
> 
> 在整个样本期内，**短期TCI**通常**小于长期TCI**。在一个由具有不同周期性成分的消费增长驱动的金融系统中，具有异质性反应的冲击会产生不同持久度的关联。
> 
> - **强大的长期TCI**表明一个市场对其他市场的反应具有相对的**持续性**，这是系统连接度的主要来源。
>     
> - 换言之，“AI-碳市场-能源”系统**处理信息的速率较慢**，信息传导持续超过一个日历月。因此，发生在过去**21个交易日至100个交易日**窗口内的冲击对系统连接度有更强的影响。
>     
> - 这三个市场在**长期内显得更加整合**。与总体TCI类似，长期连接度在**2022年11月**和**2023年4月**前后变得更为突出。
>     
> 
> ### 短期与长期连接度的一致性
> 
> 短期连接度也表现出类似的波动。因此，重大的**政治和经济事件**也会在**短期和长期**内影响这三个市场的连接度。这一发现与现有文献一致，即重要事件（例如新冠疫情对通胀连接度的影响）会显著影响系统的连接性。









> [!NOTE] 对于dynamicTCI分析的一个整体的逻辑
> 
> 1. **分析TCI的整体趋势和关键节点：**
>     
>     - **整体趋势：** 观察TCI在整个研究期间的总体变化趋势，是上升、下降还是波动。
>     - **关键节点：** 识别TCI的峰值、低谷以及显著变化的时间点，并尝试找出导致这些变化的潜在原因。例如，这里提到了2022年11月的峰值和2023年4月的变化。
> 2. **区分短期和长期TCI：**
>     
>     - **短期TCI：** 反映的是系统对短期冲击的反应。
>     - **长期TCI：** 反映的是系统长期稳定性和相互依赖性。
>     - **比较：** 比较短期和长期TCI的差异，分析系统对冲击的反应速度和持续性。
> 3. **寻找影响TCI的因素：**
>     
>     - **政策因素：** 关注政府政策的变化，例如，这里提到的中国解除疫情管控。
>     - **经济因素：** 考虑宏观经济指标、市场波动等因素。
>     - **技术因素：** 关注技术创新和突破，例如，GPT-4的发布。
>     - **事件驱动：** 识别可能影响系统连接度的重大事件。
> 4. **结合其他数据和信息：**
>     
>     - **补充数据：** 结合其他相关数据，例如，碳排放配额（CEA）的回报率、投资者情绪等，来验证和解释TCI的变化。
>     - **文献参考：** 参考相关领域的文献，了解类似研究的结论和方法。



### 3.Net TCI for each


![[截屏2025-06-05 12.03.44.png]]

这段文字是对 **“AI-碳市场-能源”系统** 动态净连接度（Dynamic Net TCI）的深入分析，旨在识别在**不同频率**下驱动系统发展的**净冲击发送者和接收者**。

以下是清晰、学术化的翻译，并组织成逻辑连贯的段落：

---

## 动态净连接度分析：系统角色的时变性与频率依赖性

为了识别“AI-碳市场-能源”系统中哪些变量在不同频率下通过传导冲击来驱动系统的发展，我们计算了**动态净TCI**（如图4所示）。图中的**正值**表示相应变量是净信息**发送者（Net-Transmitter）**，而**负值**表示是净信息**接收者（Net-Receiver）**。整体净连接度以蓝色阴影区域表示，短期和长期净连接度则分别由黑实线和红虚线表示。

### I. AI 行业：交易量为主导，关注度角色转变

#### 1. AI 行业交易量（VAI）：持续的净发送者

**AI行业交易量**在总体和短期、长期分解中，均是**持续的净信息发送者**。其净TCI范围在 **41% 到 106%** 之间，显示出对系统中其他因素的显著影响。长期净TCI（36%–99%）与总体净TCI趋势相似，表明其具有强大的**长期影响**。尽管短期净TCI较小（2.43%–8.69%），但持续为正，确认了其在短期内也是净发送者。

#### 2. AI 行业关注度（AAI）：角色发生转变

在样本期的大部分时间里，**AI行业关注度**一直是一个**持续的净信息接收者**。然而，随着 **2023年4月GPT-4的发布**，网络中其扮演的角色发生了显著变化：

- **转变点**：约 **2023年5月**，AI关注度开始从长期上升趋势中回落，并转变为**净信息发送者**，直至样本期结束。
    
- **频率差异**：尽管长期趋势在转变前主要为接收者，但在**高频（短期，小于21个交易日）**频段，AI关注度表现为**持续的净发送者**（TCI范围为0.77%–8.54%）。
    

总体而言，AI行业的重大突破强化了投资者关注度在网络中的重要性，使其在**长期内**具备了信息发送能力。

#### 3. AI 行业回报率：重要性不强

AI行业回报率的净连接度值较小，表明该指标在整个网络中的重要性**不强**。与AI行业的其他指标一样，**长期连接度**处于主导地位。

---

### II. 碳市场：关注度为接收者，交易量具潮汐现象

#### 1. 碳市场关注度（ACEA）：主要的净接收者

**碳市场关注度**在整个样本期内主要扮演**净信息接收者**的角色，仅在2022年7月18日至8月31日期间总体净TCI短暂为正。从2022年8月至2023年7月，其总体和长期连接度显著增加，净TCI最低降至-68.80%，这表明在**长期内**它更容易受到系统内其他变量的影响。短期净连接度保持正值，但重要性随时间下降。此外，AI和碳市场关注度的相关性为负，与**注意力资源有限理论**一致。然而，从2022年1月至2023年4月，两者同时是净接收者，表明它们可能同时受到其他因素的冲击。

#### 2. CEA 交易量（VCEA）：受政策驱动的角色转变

**CEA交易量**主要表现为**净信息接收者**（2022年初至年底，以及2023年4月至10月）。

- **潮汐现象**：由于中国全国碳市场存在明显的“潮汐现象”（年末年初交易量高），2022年11月和12月交易量显著上升，使其角色从净接收者**短暂转变为净发送者**。直到2023年4月AI行业关注度激增，其再次成为净接收者。
    
- **短期效应**：其短期净连接度通常为**正**（净发送者），但量级较小（1.32%–5.00%）。
    

#### 3. CEA 回报率：重要性不强

与AI行业回报率类似，**CEA回报率**在系统中的重要性也**不强**。

---

### III. 能源部门：短期主导与长期角色转换

**能源部门**（包括传统能源和可再生能源企业）在系统中的重要性低于AI行业和碳市场。其突出特点是**总体连接度与短期结果更相关**。

- **煤炭和新能（CII-Coal/CII-PENE）**：它们在**短期内**通常是**净接收者**，与总体TCI相似。但其长期净TCI的演变则表现为在发送和接收信息之间**多次转换**。这可能与投资者对煤炭供需和燃料成本的心理预期有关。
    
    - **角色差异**：由于中国的资源禀赋和能源安全考虑，煤炭在**短期内**受到碳市场和AI行业动态的传导（接收者），但在**长期内**，其在宏观经济中的主导地位使其转变为信息**发送者**。
        
- **石油石化（CII-PP）**：该行业与其他两个部门不同，其**净TCI在两个频段内主要为正**，表明它在系统中通常是**净信息发送者**。其发送者角色与国际原油市场对中国碳市场存在溢出效应的发现是一致的。然而，其总体净TCI范围较小（0.64%–6.49%），表明其净影响相对较弱。
    

---

### 结论与总结

我们认为，**AI行业和碳市场**对重大事件的反应动态被**长期连接度**很好地捕获。

总而言之，**AI行业交易量**是“AI-碳市场-能源”系统的主要信息**发送者**，而**AI行业关注度、碳市场关注度**和**CEA交易量**则通常是主要信息**接收者**。尽管能源部门的净连接度较小，但其中煤炭和新能行业（CII-Coal/CII-PENE）仍持续作为信息**接收者**，而石油石化行业（CII-PP）主要作为信息**发送者**。

















To identify which variables in the “AI-Carbon-Energy” system drive the development of the system through transmitting shocks at different frequencies, we calculate the dynamic net TCI and present it in Fig. 4.

> [!NOTE] 问题
> 识别“AI-碳-能源”系统中哪些变量通过传递冲击驱动系统发展。
> 哪些变量是传递冲击的？


According to Fig. 4, we can identify the net-transmitters and netrecipients at different times. A positive net connectedness means that the corresponding variable is a net information transmitter for other variables in the system. Conversely, a negative value means that the corresponding variable is a net informationreceiver for others. In Fig. 4, the overall net connectedness is denoted by the blue-shaded area, and the short-term and long-term net connectedness are represented by the black solid lines and red dashed lines, respectively.


> [!NOTE] 解释
> 谁是发送者？谁是接受者？
> 说白了就是攻受之别呗
> 大部分为攻/受 长短期攻/受有别


 For the AI industry,we note that for the most of the sample period, AI industry attention acts as a persistentnet information receiver until May 10, 2023, when it stops a long-term uptrend and starts to decline (see Fig. 1). Similar to the changes in the TCI, the release of GPT-4 in April 2023 appears to have changed the role of AI industry attention in the network. Since then, the AI industry attention becomes a net information transmitter until the end of the sample period. The long-term net TCI for the AI industry attention is quite similar to its overall net connectedness, both shifting from a net information receiver to a net transmitter around May 2023. However, in the highfrequency band, i.e., less than 21 trading days, the AI industry attention performs as a persistent net transmitter, with the net TCI ranging from 0.77% to 8.54%. While the AI industry attention investor is an information transmitter in the short-term, it is mainly an information receiver in the long-term, at least before May 2023. Nevertheless, Fig. 4 indicates that the role of AI industry attention changes over the sample period. The great breakthrough in the AI industry makes investors’ attention to it become an information transmitter in the long-term. Hence, from the perspective of investor attention, the importance of the AI industry in the network has been strengthened. By contrast, the trading volume of the AI industry is a persistent net information transmitter considering the overall net connectedness and its decomposition over the short-term and long-term horizons. The net TCI for AI trading volume ranges from 41% to 106%, showing its significant impact on other factors in the “AI-Carbon-Energy” system. The long-term net TCI shows a similar trend to the overall net TCI, ranging from 36% to 99%, showing that the AI industry trading volume has a strong long-term impact on others. Although the short-term net TCI is much smaller than the long-term effect (2.43%–8.69%), it is persistently positive, indicating that the trading volume of the AI industry is also a net information transmitter in the short-term. Compared to investor attention and the trading volume in the AI industry, the value of the net connectedness of AI industry return is small, thus indicating that the importance of this indicator in the entire network is not strong. Again, regarding to the differences between frequency bands, the long-term connectedness takes precedence for the AI industry. Turning to the carbon market, the broad picture is quite different from the AI industry. Particularly, investor attention to the carbon market plays a considerable role as a net informationreceiver during the entire sample period, except for the periodfrom July 18, 2022 to August 31, 2022 when the net overall TCI is positive. Form August 2022 to July 2023, the overall and long-term connectedness become more prevalent, with the net TCI falling from 4.28% to 68.80% and from 0.01% to 70.42%, respectively. In the long-term, the carbon market attention is more affected by other variables in the system because the magnitude of its net TCI is larger than the overall result. Meanwhile, the short-term net connectedness maintains positive and becomes less prevalent over time. As indicated in Table 1, the correlation between investor attention to AI and attention to the carbon market is statistically negative, which is in line with the theory of attention resource limitation, i.e., human attention is a cognitive resource for identifying and processing information (Wickens, 2020), which affects stock trading and returns (Yang et al., 2021). Nevertheless, Fig. 4 suggests that AI industry attention and the carbon market attention can be simultaneously impacted by other factors, at least from January 2022 to April 2023, when both indicators are mainly net information receivers. From January 5, 2022 to December 20, 2022 and from April 5, 2023 to October 16, 2023, the trading volume of CEA acts as a net information receiver. The Chinese national carbon market has a prominent “tidal sand phenomenon”, with high trading volume at the beginning and end of the calendar year and relatively low performance in the middle of the year. From February to October 2022, CEA trading volume remains low, with most days below 500,000 tons. However, in November and December 2022, there is a marked upturn in CEA transaction volume, which turns its role from a net information receiver to a net transmitter. Until April 2023, when the AI industry attention surges, CEA trading volume becomes a net recipient again. The long-term net connectedness is similar to the overall net TCI. With reference to the high frequency band, i.e., less than21 trading days, the magnitude of the corresponding net TCI is small, ranging from 1.32% to 5.00%. In most days, CEA trading volume is a net information transmitter in the short-term. The only exception is from April to December 2022, when the net connectedness is slightly greater than zero. Similar to the AI industryreturn, the importance of the CEA return is not strong in the system. With regard to the energy sector, both traditional and renewable energy enterprises are less important in the system compared to the AI industry and the carbon market. A prominent feature of the energy sector is that its overallconnectedness is more relevant to the short-term results. Specifically, coal returns (CII-Coal) and power equipment and new energy returns (CII-PENE) are generally net receivers in the shortterm, which is similar to the overall TCI. By contrast, the long-term evolution of the net TCI is characterized by multiple transitions between transmitting and receiving information. This finding is in line with Xu and Li (2023) that the long-term connectedness between grey and green stocks and the carbon market is time-varying, which can be attributed to investors ’ psychological expectations about the level of demand and supply in the coal market and the actual fuel cost (Lin and Chen, 2019). The broader picture of the petroleum and petrochemic industry (CII-PP) is different from the other two sectors. Its net TCI is mainly positive for both frequency bands, showing that it is generally a net information transmitter in the system. In terms of the impact of the petroleum petrochemical industry, its role as a net transmitter is consistent with the finding of Xu (2021), where the international crude oil market and China’s domestic crude oil market have significant spillover effects on two representative carbon pilots in China. The overall net TCI of CII-PP ranges from 0.64% to 6.49%, indicating that its net impact on others is relatively weak compared to the AI industry and the carbon market. The opposite performance of the coal and petroleum petrochemical industries may stem from China’s resource endowment, which is rich in coal and scarce in oil. According to the 2022 Annual Report on the Development of the Coal Industry released by the China National Coal Industry Association,2 in the short-term,the dominant position of coal in China’s energy consumption will not change based on the country ’s resource endowment and energy security considerations. However, as China promotes the green transformation of development and accelerates the implementation of new and renewable energy to replace traditional energy, the demand for major coal-consuming industries such as steel and building materials may weaken. This makes the role of coal and electricity and new energy industries different in distinct frequency bands. In the short-term, as power generation companies are regulated by the national carbon market, the dynamics of the carbon market and AI industry will be transmitted to coal and power companies. In the long-term, the dominant position of coal resources in the macroeconomy makes it an information transmitter in the system. We therefore opine that the AI industry and the carbon market respond to significant events, and these dynamics are well captured by the long-term connectedness. The trading volume of AI industry is the main information transmitter in the “AI-Carbon-Energy” system, whereas the AI industry attention, carbon market attention, and CEA trading volume are generally main information receivers. Given the small magnitude of net connectedness, the importance of the energy sector in the system appears to be low. Nevertheless, the coal industry and the power equipment and new energy industry (CII-Coal and CIIPENE) still act as information receivers persistently, whereas the pe troleum petrochemic industry (CII-PP) is mainly an information transmitter.


> [!NOTE] 对于NET TCI的分析 总之，就是不断地分析，谁是接受者，谁是传递者
> 
> 1. **AI 行业分析 (第二段和第三段)**
>     
>     - **AI 行业关注度 (AI industry attention):**
>         - 总体趋势：在2023年5月10日之前，主要作为净信息接收者；之后转变为净信息发送者。
>         - GPT-4 的影响：GPT-4的发布改变了AI行业关注度在网络中的角色。
>         - 短期和长期差异：短期内是净信息发送者，长期内（至少在2023年5月之前）是净信息接收者。
>     - **AI 行业交易量 (AI trading volume):**
>         - 总体趋势：持续作为净信息发送者。
>         - 短期和长期影响：长期影响较强，但短期内也持续为正。
>     - **AI 行业回报 (AI industry return):**
>         - 重要性：在整个网络中重要性不高。
>         - 频率差异：长期连接度优先。
> 2. **碳市场分析 (第四段和第五段)**
>     
>     - **碳市场关注度 (Carbon market attention):**
>         - 总体趋势：在整个样本期间主要作为净信息接收者，但在2022年7月18日至8月31日期间为正。
>         - 长期影响：长期内受其他变量影响较大。
>         - 短期影响：短期内保持正值，但随时间推移影响减弱。
>         - 与其他变量的关系：与AI行业关注度呈负相关。
>     - **碳排放配额交易量 (CEA trading volume):**
>         - 总体趋势：在不同时间段内作为净信息接收者和发送者。
>         - “潮汐沙现象”：年初和年末交易量高，中间年份交易量低。
>         - 短期影响：短期内主要作为净信息发送者。
>     - **碳市场回报 (CEA return):**
>         - 重要性：在系统中重要性不高。
> 3. **能源部门分析 (第六段和第七段)**
>     
>     - **总体特点：** 相比AI行业和碳市场，能源部门的重要性较低。
>     - **频率相关性：** 总体连接度与短期结果更相关。
>     - **煤炭回报 (CII-Coal) 和电力设备及新能源回报 (CII-PENE):**
>         - 短期内通常是净信息接收者。
>         - 长期内在发送者和接收者之间多次转换。
>     - **石油和石化行业 (CII-PP):**
>         - 总体趋势：主要作为净信息发送者。
>         - 影响：对其他因素的净影响相对较弱。
>         - 原因：可能与中国的资源禀赋有关（富煤贫油）。




> [!NOTE] 有个思考
> 我们该如何从经济学上理解 这个1-0的差别？



> [!NOTE]
> 是的，有一些论文探讨了基于网络连接度分析（包括Net TCI）的市场间信息传递、溢出效应以及风险传染等问题。以下是一些相关的论文，它们从不同的角度解释了传递者和接受者的经济学含义：
> 
> **1. 关于金融市场溢出效应和风险传染的论文：**
> 
> - **Diebold, F. X., & Yılmaz, K. (2009). Measuring financial asset return and volatility spillovers, with application to global equity markets. _The Economic Journal_, _119_(534), 158-171.**
>     
>     - 这篇论文提出了一个基于方差分解的方法来衡量金融资产之间的收益和波动溢出效应。虽然没有直接使用Net TCI，但其核心思想与Net TCI类似，都是通过分析变量之间的相互影响来识别风险的来源和目标。
>     - **经济学解释：** 在这篇论文的框架下，传递者可以被视为风险溢出的来源，而接受者则为风险溢出的目标。
> - **Baruník, J., & Křehlík, T. (2018). Measuring connectedness of financial markets: A risk-based approach. _Journal of Financial Econometrics_, _16_(1), 1-35.**
>     
>     - 这篇论文提出了一个基于频率分解的连接度衡量方法，可以分析不同频率下的市场间风险溢出效应。
>     - **经济学解释：** 传递者可以被视为短期或长期风险的来源，而接受者则为相应频率下的风险承受者。
> 
> **2. 关于能源市场和碳市场连接度的论文：**
> 
> - **Reboredo, J. C., & Ugolini, A. (2020). Oil price shocks and stock returns: A network connectedness approach. _Energy Economics_, _90_, 104871.**
>     
>     - 这篇论文使用网络连接度方法分析了油价冲击对股票市场的影响。
>     - **经济学解释：** 在这篇论文的框架下，油价可以被视为能源市场冲击的传递者，而股票市场则为接受者。
> - **Ji, Q., Zhang, D., & Zhao, Y. (2018). Searching for the sources of volatility transmission in the crude oil market: A network approach. _Energy Economics_, _75_, 416-429.**
>     
>     - 这篇论文使用网络方法分析了原油市场中波动率传递的来源。
>     - **经济学解释：** 传递者可以被视为波动率冲击的来源，而接受者则为波动率冲击的目标。





### 4.Net PC for two


![[截屏2025-06-05 12.04.04.png]]
**The net pairwise connectedness provides a more granular picture of the evolution of the “AI-Carbon-Energy” system relationship over time.**


> [!NOTE] 做这个分析是为了对系统做一个更细致的研究


**Since we include nine variables in the system, there will be 36 pairs of combinations. Therefore, we identify combinations of indicators with relatively large net pairwise connectedness and plot them in Fig. 5. Specifically, four indicators are selected, i.e., AI industry attention, AI trading volume, carbon market attention, and CEA trading volume.** 

This selection is consistent with the factor importance indicated by the net TCI shown in Fig. 4. Although the net pairwise connectedness between the carbon market attention and the three energy returns exceeds 3%, it is far smaller than the net connectedness of selected pairs. Therefore, for brevity, the results for the other pairs are not reported here. Again, all plots in Fig. 5 suggestthat the long-termcomponent drives the overall net pairwise connectedness. Plot (a) shows the net pairwise connectedness from AI industry attention to AI industry trading volume. Until September 2023, AI industry attention receives net shocks from the AI industry trading volume. Since then, the net informationtransfer goes in the oppositedirection, i.e., there is a net informationspillover from AI industry attention to AI trading volume. This finding is consistent with many previous studies that investor attention affects trading activities and trading volume, such as Yang et al. (2021). Plot (b) shows that AI industry attention and carbon market attention interacts. Specifically, AI industry attention receives shocks from carbon market attention until February 2023, and transmits shocks to the carbon market thereafter. Over the same period, the role of AI industryattention changes from net receiver to net transmitter (see Fig. 4). This finding can be explained by the limited attention theory that attention is a scarce cognitive resource, so that investors only devote finite attention to personal choices (Johnston and Pashler, 1998). The change in the impact of AI industry attention on the carbon market (investor attention and trading volume) also reflects the high investor attention to the AI industry, which makes it a net transmitter in the system since April 2023. Then, AI trading volume apparently transmits shocks to CEA trading volume and carbon market attention, as shown in Plots (c) and (d), respectively. In other words, AI industry trading volume has a strongnet spillover effect on the carbon market. On the one hand, this finding suggests that technological progress represented by the AI industry indeed plays an important role in China’s carbon emission reduction, particularly in the long-term. On the other hand, AI trading volume mainly has a direct effect on CEA trading volume, as the net pairwise connectedness between carbon market attention and CEA trading volume is relatively small (in Plot (f)) relative to the other pairs in Fig. 5. Carbon market attention has a net spillover effect on CEA trading volume as of December 2022. There is also a large net spillover effect of AI trading volume on CEA trading volume during this period as shown in Plot (e). Therefore, carbon market attention acts as a transmission channel between AI trading volume and CEA trading volume. However, since 2023, carbon market attention mainly receives shocks from CEA trading volume. Compared to the pre-2023 results, the impact of AI trading volume on CEA trading volume weakens from 2023 onwards (Plot (e)). This indirectly indicates that the role of the carbon market attention transmission channel has disappeared, thus weakening the impact of the AI industry on the carbon market. Overall, both the direction and magnitude of net pairwise connectedness support the findings illustrated in Fig. 4. The linkage of the “AICarbon-Energy” system is tight, and the variables in each market can be net information transmitters or net receivers over specific intervals. With reference to frequency bands, we find that long-term connectedness is generally more pertinent; however, the short-term component is also important for some purposes, particularly regarding the energy sector.

> [!NOTE] 选出重要的来分析
> 
> 1. **AI行业关注度与AI行业交易量 (Plot a) (第二段)**
>     
>     - 描述2023年9月之前的关系：AI行业关注度从AI行业交易量接收净冲击。
>     - 描述2023年9月之后的关系：AI行业关注度对AI行业交易量产生净信息溢出。
>     - 引用文献支持：Yang et al. (2021)的研究表明投资者关注会影响交易活动和交易量。
> 2. **AI行业关注度与碳市场关注度 (Plot b) (第三段)**
>     
>     - 描述2023年2月之前的关系：AI行业关注度从碳市场关注度接收冲击。
>     - 描述2023年2月之后的关系：AI行业关注度向碳市场传递冲击。
>     - 解释原因：有限注意力理论，投资者只会将有限的注意力投入到个人选择中。
>     - 与图4结果对比：AI行业关注度从净接收者变为净传递者。
> 3. **AI行业交易量对碳市场的影响 (Plots c, d, e, f) (第四段和第五段)**
>     
>     - AI行业交易量对CEA交易量和碳市场关注度的影响：AI行业交易量明显向CEA交易量和碳市场关注度传递冲击，表明AI行业交易量对碳市场具有强大的净溢出效应。
>     - 解释意义：AI行业代表的技术进步在中国碳减排中发挥着重要作用，尤其是在长期内。
>     - AI交易量主要对CEA交易量产生直接影响。
>     - 碳市场关注度充当了AI交易量和CEA交易量之间的传递渠道。
> 4. **碳市场关注度的作用变化 (第六段)**
>     
>     - 描述2023年之后的关系：碳市场关注度主要从CEA交易量接收冲击。
>     - 与2023年之前的结果对比：AI交易量对CEA交易量的影响减弱。
>     - 解释原因：碳市场关注度传递渠道的作用消失，削弱了AI行业对碳市场的影响。
> 5. **总结 (第七段)**
>     
>     - 净成对连接度的方向和大小都支持图4所示的发现。
>     - “AI-碳-能源”系统的联系紧密，每个市场中的变量在特定时间间隔内可以是净信息传递者或净信息接收者。
>     - 长期连接度通常更相关，但短期成分对于某些目的也很重要，尤其是在能源部门。




> [!NOTE] 该研究：怎么说呢？AI直觉上最和电相关，和电相关的行业都会因为AI的到来而受到影响


### 5.Networks of the net pairwise spillovers.
![[截屏2025-06-05 12.04.42.png]]
According to the directional connectedness, we find that April 2023 is an important structural break date, which may be attributed to the release of the GPT-4. Therefore, we present the network structure of the “AI-Carbon-Energy” system based on the net pairwise connectedness of the entire sample and two sub-samples (i.e., from January 5, 2022 to March 31, 2023 and from April 1, 2023 to October 16, 2023). In Fig. 6, each node represents a variable. Notably, the red (green) colored node indicates that it is a net information transmitter (receiver). The size of a node illustrates the strength of the net spillover effect of that node, i.e., the absolute value of the net information spillover effect. The width of the edge represents the magnitude of the pairwisespillovers between the two nodes, and the arrowpoints to the informationreceiver. Meanwhile, we use purple and blue to reflect strong and weak pairwise spillovers, respectively. Specifically, we define pairwise spillovers greater than 3% as strong spillovers. Fig. 6 shows that the network structure is different before and after the release of GPT-4. First, the net contributions of both AI industry attention and carbon market attention increase since April 2023. The node sizes of them in plots (g) and (i) are larger than those in plots (d) and (f). Second, by contrast, the net contribution of AI industry trading volume weakened since April 2023 in the long-term. Until March 2023, AI industry trading volume has a strong net spillover effect on AI in dustry attention, whereas the opposite is true thereafter.Third, there are more purple edges in plots (g), (h) and (i) than in plots (d), (e) and (f), which means that the pairwise spillovers between nodes are stronger in the former. Thus, the network is more connected across frequencies since April 2023. Fourth, after April 2023, the energy sector is more affected by the AI industry. Before March 2023, there is a strong net pairwise spillover from CEA trading volume on CII-PP returns in plot (d). For the other two energy returns, their net pairwise spillovers with the AI industry and the carbon market are relatively weak. However, in plot (g), the CII-PP returns and CII-Coal returns are strongly affected by the AI industry trading volume, and CII-PP returns even have a net spillover effect on the carbon market attention. Fifth, the importance of the energy sector to the network is mainly reflected in the short-term. As shown in plots (f) and (i), i.e., in the long-term, the nodes of the three energy indicators are small and the associated edges are blue, thus indicating that the corresponding net pairwise spillovers are relatively weak. In the short-term, i.e., plots (e) and (h), the energy sector is connected to the AI industry. Overall, these networks give several noteworthy findings. Specifically, at various frequencies and across different samples, the AI in dustry tends to be the main information transmitter in the “AI-CarbonEnergy” system, and the release of GPT-4 appears to further highlight the importance of the AI industry attention. The strong connection between the AI industry and the carbon market indicates that the correlation between the two sectors has been widely noticed by investors. This is reflected in the strong spillover effect between the attention paid to the two markets, especially in the long-term, CEA trading volume is strongly affected by the AI industry attention. It follows that investor attention is important for the link between markets, a finding that is consistent with many previous studies, e.g., Yang et al. (2021), Xu and Lien (2022), and Xu and Zhao (2022). While the AI industry strongly influences the carbon market in the long-term, its impact on the energy sector mainly seen in the short-term.The AI industryis closely related to the carbon market, but its relationship with the energy sector is weak, reflecting that the application of AI in the energy industry is not deep enough. After the release of GPT-4, although the AI industry has a shortterm impact on the energy sector, the long-term impact is weak. While AI solutions are the futureof the powerindustry and RES (Hannanet al., 2021), the high cost of AI appears to be hindering the integration of the two industries. Given the rapid development of the AI industry and its potential benefits to the energy sector, such as improving efficiency and bringing wage premiums (Lyu and Liu, 2021), the integration of them is expected to deepen. Surprisingly, the connectedness between the carbon market and the energy sector is weak. Thermal power enterprises simultaneously participate in the carbon market, the electricity market, and the energy market, connecting the three markets through a common market player. The weak connection between the carbon market and the energy sector may be because China’s national carbon market only covers the power industry, while the electricity price is set and managed by the National Energy Administration, which has not yet formed a market-oriented electricity price mechanism. Therefore, the information transmission and cost transmissionbetween energy consumption and carbon emission trading are not smooth, resulting in a weak connection between the two markets. From the perspective of international practice, under the conditions of electricity marketization, the carbon price can be trans mitted to the electricity price, and the electricity price will also adversely affect the carbon price (Keppler and Mansanet-Bataller, 2010). On the one hand, the carbon price will be superimposed on the quotation of thermal power enterprises in the electricity market, thus affecting the transaction price. On the other hand, the supply and demand situation and price changes in the electricity market will affect thermal power generation, and the changesin electricity production will affect the demand for carbon allowance purchase, which then affects the carbon price. Therefore, the weak connection between the carbon market and the energy sector may stem from the electricity pricing mechanism in China. Additionally, the weak connectedness between the carbon market and the energy sector may also result from the insufficient maturity of the carbon market. Fewer market participants, imperfect mechanisms, and asymmetric information will reduce investors’ confidence in the carbon market, thus affecting investor participation, and turn to the more mature and concerned energy stock market, which reduces the connectedness between the two markets.This reflects the inefficient price transmission and information transmission channels between the carbon market and the energy sector, which is consistent with the findings of the existing literature (Xu et al., 2022).


> [!NOTE] 最后一个网络分析
> 1. **GPT-4发布前后网络结构的变化 (第二段至第五段)**
>     
>     - **AI行业关注度和碳市场关注度的净贡献增加 (第二段)**
>         - GPT-4发布后，AI行业关注度和碳市场关注度的节点尺寸变大，表明其净贡献增加。
>     - **AI行业交易量的净贡献减弱 (第三段)**
>         - GPT-4发布后，AI行业交易量的净贡献减弱。
>         - AI行业交易量对AI行业关注度的影响方向发生变化。
>     - **节点之间的成对溢出更强 (第四段)**
>         - GPT-4发布后，网络图中紫色边增多，表明节点之间的成对溢出更强。
>         - GPT-4发布后，网络在不同频率上更加连接。
>     - **能源部门受AI行业影响更大 (第五段)**
>         - GPT-4发布前，CEA交易量对CII-PP回报有很强的净成对溢出。
>         - GPT-4发布后，CII-PP回报和CII-Coal回报受到AI行业交易量的强烈影响，CII-PP回报甚至对碳市场关注度产生净溢出效应。
>     - **能源部门的重要性主要体现在短期 (第六段)**
>         - 长期来看，能源指标的节点较小，边为蓝色，表明净成对溢出较弱。
>         - 短期来看，能源部门与AI行业相连。
> 2. **总体发现 (第七段至第十段)**
>     
>     - **AI行业是主要的信息传递者 (第七段)**
>         - 在不同频率和不同样本中，AI行业倾向于成为“AI-碳-能源”系统中的主要信息传递者。
>         - GPT-4的发布进一步突出了AI行业关注度的重要性。
>     - **AI行业与碳市场之间的强连接 (第八段)**
>         - AI行业与碳市场之间的强连接表明投资者广泛关注这两个行业之间的相关性。
>         - AI行业对碳市场关注度的强烈溢出效应，尤其是在长期内，CEA交易量受到AI行业关注度的强烈影响。
>         - 投资者关注对于市场之间的联系非常重要。
>     - **AI行业对能源部门的影响主要体现在短期 (第九段)**
>         - AI行业与碳市场关系密切，但与能源部门的关系较弱，反映出AI在能源行业的应用不够深入。
>         - GPT-4发布后，AI行业对能源部门的短期影响较强，但长期影响较弱。
>         - AI解决方案是电力行业和可再生能源的未来，但AI的高成本似乎阻碍了这两个行业的融合。
>     - **碳市场与能源部门之间的连接较弱 (第十段)**
>         - 碳市场与能源部门之间的连接较弱，可能因为中国的碳市场只覆盖电力行业，而电价由国家能源局设定和管理，尚未形成市场化的电价机制。
>         - 碳市场与能源部门之间连接较弱的另一个原因可能是碳市场不够成熟。






# 5-结论 (Conclusion)

### 核心要点总结

这篇研究论文的核心是探讨**“AI-碳-能源”系统**内部的关联性，并基于其发现提出政策建议。以下是核心要点的结构化总结：

#### **一、 研究背景与目的**

- **背景**：AI产业的巨大关注度引发了人们对其碳排放影响的兴趣。AI产业在碳排放方面扮演着“双刃剑”的角色（自身产生高能耗，也能赋能节能减排）。
- **目的**：以世界最大碳排放国——中国为研究对象，检验“AI-碳-能源”三大市场之间的关联性（信息溢出效应），为政策制定提供依据。

#### **二、 核心研究发现**

研究使用**动态频率关联性指数和网络分析方法**，从短期和长期两个维度分析了信息溢出效应，主要发现如下：

1. **长期驱动为主**：“AI-碳-能源”系统的整体信息溢出主要由**长期**成分驱动，表明市场信息处理速度较慢。
2. **AI产业是系统的核心**：
    - **投资者关注度**：是一个关键节点。自2023年5月GPT-4发布后，在**低频（长期）**层面，它从净信息接收者转变为净信息发送者。在**高频（短期）**层面，它持续发送信息，但影响力较弱。
    - **交易量**：是**最强大、最持久**的净信息发送者，在所有频率（短、长期）都对系统产生显著影响。
3. **碳市场是主要信息接收者**：尤其是在长期，碳市场主要接收来自其他市场的信息，特别是来自**AI产业投资者关注度**的信息。
4. **能源行业关联性较弱**：能源行业与AI和碳市场的连接整体较弱，尤其在长期。但其中，**石油石化行业**在系统中扮演了信息发送者的角色。
5. **投资者关注度是关键连接点**：投资者关注度是连接AI、碳市场和能源行业三大市场的重要枢纽，使它们紧密相连。

#### **三、 主要政策建议**

基于以上发现，研究为政策制定者、生产者和投资者提出了具体建议：

**对政策制定者：**

1. **引导投资者注意力**：通过政策法规引导投资者关注低碳绿色技术，促进AI在能源行业的创新应用。
2. **强化信息披露**：要求企业全面披露碳排放和环保信息，帮助投资者做出更环保的投资决策。
3. **促进AI与碳市场融合**：鉴于AI与碳市场联系紧密，应鼓励和支持AI技术在碳监测、碳交易分析、减排技术等领域的应用，以提高减排效率、降低减排成本。
4. **加强AI与能源行业合作**：鉴于能源与AI行业联系较弱，应通过激励措施、研发资金或税收优惠等方式，鼓励能源企业与AI产业合作，利用AI提升效率、降低排放。
5. **加强跨市场政策协同**：需要协调价格机制、市场政策和绿色认证，形成推动低碳转型的最大合力。尤其需要制定**“技术感知型气候政策”**，将AI产业的碳控排政策与碳市场政策（特别是可再生能源相关政策）相结合。
6. **提升投资者认知**：通过提供准确信息、加强宣传和教育，提升投资者对碳市场、AI和能源股的理解，促进系统良性互动。

**对生产者（企业）：**

- AI正在成为能源和环境行业（无论是新兴还是传统）的关键赋能者。能源、电力等企业若想保持长期竞争力，必须更加重视AI技术的发展和应用。

**对投资者：**

- **长期投资机会**：由于能源行业与AI和碳市场关联性弱，存在**长期多元化投资**的机会。
- **短期策略调整**：由于AI和能源行业在短期存在显著的信息溢出，因此有必要在这两个行业之间进行**投资组合再平衡**。
- **关注投资者情绪**：在制定投资策略时，必须考虑投资者关注度这一关键因素对市场及相关市场的影响。

#### **四、 研究局限与未来方向**

1. **未充分考虑地方碳试点**：未来研究可纳入中国八大区域碳试点市场的数据，进行更深入的区域性分析。
2. **数据频率有限**：目前仅使用日度数据。随着数据积累，未来可引入更多低频宏观经济因素，以探究市场间关联的深层渠道。

# 6-introduction和文献综述

*   **检验方法 (Methods):**
    *   使用了哪些稳健性检验方法？
*   **检验结果 (Results):**
    *   稳健性检验的结果如何？
    *   结果是否支持主要结论？


