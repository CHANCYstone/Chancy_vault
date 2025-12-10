---
title: "[[论文标题]]"
author: "[[作者]]"
year:
  - - 年份
tags:
  - 论文笔记
  - 研究方法
  - 关键词
citekey: 作者年份
---

[[读TVP-VAR论文]]


# 1-摘要
# 2-数据 (Data)
The S&P Goldman Sachs Commodity Index (S&P GSCI) is the largest tracked commodity index which includes most capital participation in
the world. It is also the top used commodity index by long-term investors
such as pension funds and insurance companies in commodity markets.
Currently, it covers five types of commodity markets—i.e., energy,
precious metal, industrial metal, agriculture and livestock products. The
S&P GSCI is based on production-weighted commodity categories, so it
well reflects the Beta coefficient of the commodity markets. Historically,
the S&P GSCI has a powerful advantage in providing investors with
diversified investment and resistance to inflation.

This paper uses the 

#### 1--total return of the five full-category markets of energy, precious metal, industrial metal, agriculture, and livestock. The S&P GSCI 

**用的SP-GSCI数据，大宗商品指数数据**
![[截屏2025-06-18 12.06.26.png]]
**数据长这个样子一共650条数据，这种指数类的数据都是周数据**


[[test-script]]

![[截屏2025-06-18 15.26.58.png]]




started from April 2008, but the data in first two month isn’t
intact. To ensure the integrity of the research, we set our data range from
June 2008 to December 2020. The sample period includes several major
global events and crises—the global financial crisis (2008), the Euro-
pean sovereign debt crisis (2009–2012), the Chinese stock market crash
and the Brazilian crisis (2015–2016), and the COVID-19 period (2020).
According to the work of Garman and Klass (1980), t**his paper uses the**
**highest price, lowest price, opening price, and closing price from**
**Monday to Friday to calculate the weekly range volatility.** The specific
calculation formula is written as follows.

![[截屏2025-06-18 12.09.23.png]]


![[截屏2025-06-18 12.10.04.png]]



Geopolitical risk is the kind of risk related to events such as wars, terrorist acts and political tensions, that can affect the normal and peaceful process of international relations. However, the importance of geopolitical risks has not yet been paid attention to in affecting the financial cycle and macroeconomic condition, and systematic empirical analysis has not yet been carried out. The main limitation is the lack of a long-term, consistent geopolitical risk indicator, as well as real-time geopolitical risk indicator perceived by the media, the public, global investors and policymakers, which is difficult to quantify from the historical literature. For a long time, it can only use virtual variable modeling or event research method for a specific event, and can only analyze the risk of a specific event in a certain period.

Recently, the text analysis technology can quantify the emotional tone of the text ([Jegadeesh and Wu, 2013](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0235)) and better examine the impact of broader news events. For example, [Garcia (2013)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0160) uses content analysis to estimate the emotional bias of long-running columns in the Wall Street Journal and the New York Times and finds that media pessimism gives stock prices a downward pressure. Similarly, [Manela and Moreira (2017)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0330) construct an uncertainty measure based on front-page articles and find that it peaks during extremely difficult times, such as market crashes and World Wars, and can be used to predict future returns.

#### 2-GPR INDEX [Caldara and Iacoviello (2018)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0085) use the text analysis technique to calculate the geopolitical risk (GPR) index.

From a narrow perspective, the index can be defined as “the kind of risk related to events such as wars, terrorist acts and political tensions, that can affect the normal and peaceful process of international relations”. The GPR index allows greater volatility in the measurement of geopolitical risk, so it can provide more reliable inferences. The calculation method of this indicator is to select 11 leading international newspapers (the newspapers in the sample include “Boston Globe”, “Chicago Tribune”, “Daily Telegraph”, “Financial Times”, “Globe and Post”, “Guardian New York Times”, “Los Angeles Times”, “New York Times”, “Times”, “Wall Street Journal” and “Washington Post”), by counting the number of articles related to geopolitical risk of each newspaper every month (accounting for the share of the total number of news articles) to calculate the index and normalize it to an average of 100.

The search mainly identifies articles that quote the above six groups of words: Group 1 includes words related to explicit references to **geopolitical risks**, as well as references to military-related tensions involving the US or much of the world. Group 2 includes words directly related to **nuclear tensions**. Groups 3 and 4 include mentions related to the **threat of war and terrorism**, respectively. Finally, Groups 5 and 6 aim to capture news reports on actual adverse geopolitical events (not just risks) that can be reasonably expected to give a rise to geopolitical uncertainty, such as the inception of terrorist acts or wars.

Based on the search group above, [Caldara and Iacoviello (2018)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0085) propose two indexes to further separate the direct impact of adverse geopolitical events from the geopolitical risks. 

#### 3-The Geopolitical Threats (GPT) index 

contains words belonged to the above-mentioned Groups 1–4, while the 

#### 4-Geopolitical Act (GPA) index 

contains words that belong to Groups 5 and 6. More importantly, the newspapers considered in the GPR index are located in North America and the United Kingdom, so the huge changes in the index are most likely to come from geopolitical news that directly affects these countries or is of great significance at the global level. Such news may have the greatest impact on the global commodity market.

In order to explore the connection between geopolitical risk and commodity market volatility, we use geopolitical risk (GPR) index of [Caldara and Iacoviello (2018)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0085) as a measure of geopolitical risk. [Fig. 2](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#f0010) shows the monthly GPR index for the sample period from June 2008 to December 2020. The index has several notable peaks, corresponding to major international geopolitical events in the corresponding period. For example, the peaks around 2011 are mostly related to the escalation of the Syrian conflict. The peaks around September 2013 are related to the domestic political turmoil in Egypt. In March 2014, Crimea applies and merges with Russia. The Ukrainian crisis affects the nerves of all parties and the world. This situation brings a small peak in March 2014. Since June 2014, the US-Russian relationship has been violent. The European Union and other countries have continuously launched economic sanctions against Russia. The geo-conflict has escalated and reached a new level around September 2014. The peak at the end of 2015 is mostly related to a series of terrorist attacks in France.


# 3-模型 (Model)



[Cogley and Sargent (2001)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0105) first propose the time-varying parameter VAR (TVP-VAR) model. They use the TVP-VAR model to study the dynamic relationship between the inflation rate and the unemployment rate after World War II in the United States and obtain better forecast results compared to the traditional VAR model. Furthermore, the time-varying parameter VAR (TVP-VAR) model is extended twice ([Cogley and Sargent, 2005](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0110); [Primiceri, 2005](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0370)). [Cogley and Sargent (2005)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0110) solve the problem that the initial model of [Cogley and Sargent (2001)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0105) only considers the time-varying properties of VAR coefficients, and the impact is set to be constant. They propose TVP-VAR model with time-varying coefficients and time-varying variance. Then [Primiceri (2005)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0370), on the basis of [Cogley and Sargent (2005)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0110), further relaxes the assumption that the correlation between variables is constant over the same period. They then expands the model to the full time-varying TVP-VAR model (i.e., TVP-VAR-SV model) that the coefficients, variances and covariances all change over time, and use [Bayesian](https://www.sciencedirect.com/topics/economics-econometrics-and-finance/bayesian "Learn more about Bayesian from ScienceDirect's AI-generated Topic Pages") method to realize the [Markov Chain Monte Carlo](https://www.sciencedirect.com/topics/economics-econometrics-and-finance/markov-chain-monte-carlo "Learn more about Markov Chain Monte Carlo from ScienceDirect's AI-generated Topic Pages") (MCMC) estimation of the model. Since then, most scholars have carried out empirical research based on the TVP-VAR-SV model proposed by [Primiceri (2005)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0370), such as [Nakajima (2011)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0345). The basic expression is expressed as follows.(2)where _t_ = _p_ + 1, _p_ + 2, …, _T_. p is the lag order. T is the sample length. _y__t_ is _N_ × 1 dimension observation vector. Φ0, _t_ is _N_ × 1 dimension intercept vector. Φ1, _t_, Φ2, _t_, …, Φ_p_, _t_ are all _N_ × _N_ dimension time-varying lag coefficient matrix. _ε__t_ is random disturbance term with variable variance.

We make Φ_t_ = [Φ0, _t_, Φ1, _t_, Φ2, _t_, …, Φ_p_, _t_], and stack the elements of matrix Φ_t_ into columns then we have _β__t_ = _vecr_(Φ_t_′), where _vecr_(·) is column stacking operator. _β__t_ is (_N_2_p_ + _N_) × 1 dimension coefficient vector. We assume _β__t_ follows random walk process.(3)where the disturbance term _v__t_ is independent and identically distributed Gaussian white noise, and _v__t_~_N_(0, _Σ__β_). _Σ__β_ is a time-invariant diagonal matrix. Let _I__t_ − 1 be the observable information of period _t_ − 1, and there are _ε__t_ ∣ _I__t_ − 1~_N_(0, _Σ__t_), _Σ__t_ is the time-varying conditional covariance matrix.

We re-parameterize _Σ__t_ to get _Σ__t_ = _C__t_−1_D__t_(_C__t_−1)′, where _C__t_ is the lower triangular matrix with diagonal elements equal to 1, and _D__t_ is the diagonal matrix. Furthermore, we straighten the non-diagonal elements of _C__t_ to obtain [_N_(_N_ − 1)/2] × 1-dimension coefficient vector _α__t_, and straighten the diagonal elements of _D__t_ to obtain _N_ × 1-dimension variance vector _σ__t_2, then make _h__t_ = _ln σ__t_2 We also assume that both _α__t_ and _h__t_ obey the random walk process.(4)

where disturbance terms _ς__t_ and _ξ__t_ are independent and identically distributed Gaussian white noises, i.e., _ς__t_~_N_(0, _Σ__α_) and _ξ__t_~_N_(0, _Σ__h_). _Σ__α_ and _Σ__h_ are all time-invariant diagonal matrices. We assume that the disturbance terms _v__t_、_ς__t_ and _ξ__t_ are independent of each other, and all have no correlation with _ε__t_.

The TVP-VAR-SV model set above can be regarded as a linear non-Gaussian [state space model](https://www.sciencedirect.com/topics/economics-econometrics-and-finance/state-space-model "Learn more about state space model from ScienceDirect's AI-generated Topic Pages"), and parameter estimation can be achieved by the [MCMC method](https://www.sciencedirect.com/topics/economics-econometrics-and-finance/monte-carlo-simulation "Learn more about MCMC method from ScienceDirect's AI-generated Topic Pages"). For the specific algorithm, refer to the detailed introduction of [Primiceri (2005)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0370) and [Nakajima (2011)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0345). In each MCMC sampling of the TVP-VAR-SV model, we can obtain random samples of the time-varying parameters _β__t_, _α__t_ and _h__t_. Based on the posterior mean of these time-varying parameters, the volatility overflow index at each time point can be further calculated. First, we need to calculate the time-varying variance decomposition matrix. Usually, we adopt the impulse response function to calculate and obtain the orthogonalized impulse response function by Cholesky decomposition, and then calculate the variance decomposition based on the orthogonalized impulse response. The disadvantage of this method is that the result of variance decomposition will be affected by the order of variables. For this problem, we learn from the approach of [Diebold and Yilmaz (2012)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0125). They use the generalized impulse response function of [Pesaran and Shin (1998)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0360) instead of Cholesky decomposition to calculate the generalized variance decomposition matrix, which effectively overcomes the influence of the order of variables, and reduces the amount of calculation. [Pesaran and Shin (1998)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0360) define each element in the H-step-ahead generalized variance decomposition matrix Θ_t_ as:(5)where  is the coefficient matrix of the TVP-VMA(∞) model.  is the variance matrix-vector of the disturbance term _ε__t_. _H_ is the number of variance decomposition periods.  is the _j_-th of  diagonal elements representing the [standard deviation](https://www.sciencedirect.com/topics/economics-econometrics-and-finance/measure-of-dispersion "Learn more about standard deviation from ScienceDirect's AI-generated Topic Pages") of the disturbance term of the _j_-th equation. _e__i_ and _e__j_ are used as selection vectors that represent the _i_-th and _j_-th column vectors of the unit matrix, respectively. An _N_ × _N_ matrix _Θ__t_ forms the connectedness index, where each item provides the contribution of variable _j_ to the variance of the prediction error of variable _i_. The self-variable and cross-variable contributions are respectively provided by the main diagonal and off-diagonal elements of the generalized variance decomposition matrix _Θ__t_.

Under the generalized decomposition, since the sum of the contribution shares of the self-variable and cross-variable variance is not 1, each item of the variance decomposition matrix is normalized according to the sum of its rows, as shown below:(6)where , N. We obtain the transformed generalized variance decomposition matrix . Therefore, Eq. [(6)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#fo0035) constitutes a natural measure of connectedness in both directions from commodity _j_ to commodity _i_. Based on the generalized variance decomposition matrix, the following various time-varying volatility spillover indices can be calculated.

We sum all the non-diagonal elements of the generalized variance matrix , and then divide by the number of variables to get all the variance decomposition summary in the sample. That is, the total spillover index or total connectedness (TC) of all commodity markets or assets can be written as follows.(7)

The index measures the total information flow between the commodities in the sample. This is measured by the ratio of the sum of all non-diagonal elements to the sum of all elements (non-diagonal and diagonal) in the prediction error variance decomposition matrix. Non-diagonal represents the impact from (to) the other, that is, across-connectedness index of the market. And the diagonal element captures the connectedness index of its own market.

Similarly, the overall connectedness can be decomposed into directional connectedness from one specific market or asset to another (To), and directional connectedness from another specific market or asset to one (From).

The impact of all other markets or asset _j_ on the market or asset _i_ is expressed as:(8)

The impact of the market or asset _i_ to all other markets or assets is expressed as:(9)

Eq. [(8)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#fo0045) represents the directional fluctuation spillover of commodity _i_ received from other commodity _j_, which enables us to identify that each commodity market in the system contributes to the variance of other commodity markets to what extent. Eq. [(9)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#fo0050) indicates the directional fluctuation spillover that commodity _i_ transfers to other commodities _j_. It provides a measure of how a particular commodity responds to the spillover of all other commodities.

Therefore, the net directional spillover is:(10)

_NDC__i_, _t_(_H_) is the difference between the volatility shock transmitted to all other commodity markets and the volatility shock received from all other commodity markets. It helps to identify the nature of the market or asset and determine whether it is a net receiver or a net transmitter.

We turn all market connectedness into a network. According to the explanation of [Diebold and Yilmaz (2014)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0130); [Diebold et al. (2017)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0135), [Gong et al. (2021)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0195) and [Škrinjarić and Šego (2020)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0405), the variance decomposition matrix is the adjacency matrix of the weighted directed network.


#### 1-A full-sample static volatility connectedness index among five commodity markets.

![[截屏2025-06-18 15.41.23.png]]

In [Table 2](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#t0010), the value in the _i_-th row and the _j_-th column represents the contribution of the market in the _j_-th column to the volatility spillover of the market in the _i_-th row. For example, the number in the first row and the second column in [Table 2](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#t0010) indicates that the precious metal market contributes 8.98% to the energy market volatility spillover.

In addition, it should be noted that the “To row” in Row 6 indicates the total contribution of each market to other markets. For example, the number in Row 6 and Column 1 indicates that the total contribution of the energy market to precious metal, industrial metal, agriculture and livestock markets volatility spillover is 29.50%. And the last column “From column” represents the total contribution of volatility spillover received from other markets in each market. For example, the number in Row 1 and Column 6 represents that the other four markets contribute 27.51% to the volatility spillover of the energy market. The last row represents the net spillover effect between the five markets, which is obtained by subtracting the “From” value from the “To” value of each market. The total spillover index in the last column of the last row refers to the average of the spillover effects from all other markets (“From column”).

[Table 2](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#t0010) shows the volatility connectedness among energy, precious metal, industrial metal, agriculture, and livestock markets during the entire sample period. From the volatility series spillover index in [Table 2](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#t0010), we can obtain the following findings.

First, the volatility spillover index of the five markets (i.e., the total spillover effect) reaches 25.39% on average. The own-determined ratio of a single market is between 70.68% and 83.02%, which means volatility spillover effects are obvious.

Second, at the level of a single market, compared to the other four markets, the industrial metal market has the largest volatility spillover effect on other markets, with the most spillover on the precious metal market. The industrial metal market also receives the largest spillover effect from other markets. The net spillover effect of the industrial metal market is the largest at 5.79%, with a positive direction. In terms of absolute value, the industrial metal market receives large volatility spillover from other four markets, which reaches 29.32%, indicating that its volatility spillover is still greatly affected by the volatility spillover effect of other markets. Among them, the precious metal market has the largest external volatility spillover on the industrial metal market. Combining the foregoing analysis, the industrial metal market also has the most significant spillover to the precious metal market, which can be seen that the industrial metal market and the precious metal market exhibit two-way obvious volatility spillover effects.

The maximum value indicates that there is a close linkage of the volatility changes between the industrial metal market and the precious metal market. The close connection between metals may be related to the increasing importance of different metals in financial markets and their competitive role as hedging tools during market turmoil, such as gold and silver in traditional precious metals, and copper in industrial metals. They are all proven to have good hedging properties ([Sakemoto, 2018](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0390); [Baur and Smales, 2020](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0065); [Sikiru and Salisu, 2021](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0400)).

At the same time, the volatility of both industrial metal and precious metal can be denominated by US dollar. The United States, as the most important economy and global financial center, its [monetary policy](https://www.sciencedirect.com/topics/economics-econometrics-and-finance/monetary-policy "Learn more about monetary policy from ScienceDirect's AI-generated Topic Pages") and the subsequent changing value of US dollar may also be important driving factors for the fluctuations in the two markets ([Liu et al., 2021b](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0305)).

The precious metal market has the most spillover to the industrial metal market, followed by the agriculture market and the energy market. The spillover effects of precious metals on agriculture and energy commodities can be attributed to the post-financialization period, in which commodities are used more as financial assets. Precious metals may act as a safe haven against other commodity price variations ([Farid et al., 2021](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0150)). In addition, the precious metal market accepts and transmits second largest volatility spillover, so its net spillover effect also ranks second, at 4.22%.

Similarly, the volatility spillover effects received and transmitted by the energy market are both in the third place. Therefore, in summary, the energy market only shows a small positive net spillover index, which is 1.98%. The energy market is closely related to industrial metal market and precious metal market. This can be confirmed with the work of [An et al. (2020)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0030). They explore that from a community perspective, energy market, industrial metal and precious metal market can have obvious average out-strength or in-strength to each other. It shows that energy market forms a balanced spillover effect and plays a relatively smaller role in the variation process. When [Ding and Zhang (2021)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0140) study the impact of geopolitical [risk factors](https://www.sciencedirect.com/topics/economics-econometrics-and-finance/risk-factor "Learn more about risk factors from ScienceDirect's AI-generated Topic Pages") on the joint volatility of commodities, they find that under the conditions of medium and low frequencies, energy commodities have strong risk spillovers. In the long run, metal products will take over as the overflow center. This can be confirmed by the above research conclusions.

The net spillover indexes of industrial metal, precious metal and energy markets all show positive values, which are the information transmitters of spillover between the bulk commodity markets. However, the net spillover indexes of the agriculture and livestock markets are negative, so they play the role of information receivers. Among them, the agriculture market receives volatility spillover effect at 25.35%, which exceeds volatility transfer value of 23.60%. In comparison, the livestock market, as the market that receives the greatest degree of volatility spillover from other markets and also transmits the smallest spillover to other markets, its net spillover is the most in a negative direction, reaching −10.23%, which is the most obvious information receivers.

It is worth noting that, similar to the strong two-way largest spillover between the industrial metal market and the precious metal market, we find that the energy and livestock markets also receive the same largest level of the external spillover from each other. There will be two-way volatility and spillover between the energy and livestock product markets under a variety of conditions. For example, the demand for biofuels will form the basis of the volatility link between oil and livestock products ([Nazlioglu et al., 2013](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0350); [Barbaglia et al., 2020](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0060)). Under the impact of specific geopolitical risks, the connection between energy and non-energy products, such as agriculture and livestock products, is even more significant with the influence of market sentiment ([Ji et al., 2020](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0245)).


#### 2- Dynamic volatility connectedness analysis

> [!NOTE] bb
> To characterize the time-varying characteristics of connectedness effect, the most commonly used method is the rolling window VAR method. This method requires a time-varying estimation of the overflow index under the condition of a fixed window width, so it has the following limitations. First, the choice of window width seriously affects the estimation results of the model. If the window width is too long, the estimation results in the sample will be smoother, and some sudden structural changes cannot be captured. If the window width is too short, it will generate more outliers and abrupt results, resulting in unreliable estimation results in the sample. Second, the existence of the window width will inevitably lose the samples of the initial window, resulting in the dynamic connectedness effect results missing a window width length of sample. In addition, when the sample data is small, the rolling window VAR method cannot be applied.
> 
> Based on TVP-VAR-SV model, [Liu and Gong (2020)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0035) combine it with the overflow index method constructed by [Diebold and Yilmaz, 2012](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0125), [Diebold and Yilmaz, 2014](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0130) and establish a time-varying overflow index method based on TVP-VAR-SV model. The method does not need to set the window width, so it does not cause the loss of samples, and can effectively compensate for the shortcomings of the time-varying overflow index method constructed by [Diebold and Yilmaz, 2012](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0125), [Diebold and Yilmaz, 2014](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0130). Therefore, this paper uses the overflow index model proposed by [Liu and Gong (2020)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0035) to calculate the time-varying overflow index. Finally, we can see the time-varying overflow index in [Fig. 3](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#f0015), [Fig. 4](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#f0020), [Fig. 5](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#f0025), [Fig. 6](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#f0030), [Fig. 7](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#f0035).

![[截屏2025-06-18 15.44.18.png]]
==**这个FROM-TO是什么意思怎么理解？还没搞清楚**==

**==这个是可以替换的显然==**

> [!NOTE] 一顿bb
> [Fig. 3](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#f0015), [Fig. 4](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#f0020), [Fig. 5](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#f0025), [Fig. 6](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#f0030), [Fig. 7](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#f0035) show that the volatility connectedness effect has obvious time-varying characteristics. The volatility connectedness effect received and transmitted by each market follows a consistent trend of changes. Specifically, during the period from 2008 to 2009, spillover in all kinds of commodity markets, whether flowing out or in, has shown a downward trend. Around 2018, the spillover in all kinds of commodity markets similarly presents a small peak of growth. Starting from 2020, changes of all commodity markets spillover intensify, which shows the unprecedented impact of the COVID-19 epidemic. It strongly affects the dynamic connectedness between commodity markets. Next, we analyze the volatility time-varying spillover index of each market in detail.
> 
> During the entire sample period, the energy commodity market sends and receives an equivalent volatility spillover effect. Therefore, the net volatility spillover effect of the energy commodity market keeps fluctuating around zero, which can correspond to the results of static full-sample analysis. The spillovers in the two directions show the same change trend. It is worth noting that the two-way spillover effects of the energy commodity market with others have all produced a relatively large decline around 2008–2009 and 2011–2012. Since then, they have been oscillating in the 0–20% range. It may be related to the impact on energy market from the [global economic crisis](https://www.sciencedirect.com/topics/economics-econometrics-and-finance/global-economic-crisis "Learn more about global economic crisis from ScienceDirect's AI-generated Topic Pages") and the 2011 NATO airstrike on Libya. Then the energy market has produced large fluctuations and affected the prices of other bulk commodities. Because the spillover effects of receiving and transmitting have reached new levels, the net spillover effect during 2008–2009 ranks the largest in the negative sample period, and the net spillover effect during 2011–2012 is the largest in the positive sample period.
> 
> Different from the energy commodity market, the net spillover effect generated by the precious metal commodity market is positive for most of the sample period and shows an upward trend as a whole. Therefore, during the entire sample period, the precious metal commodity market shows a positive net return spillover effect, as a messenger of information. This is consistent with the results of the previous full sample analysis. Specifically, during 2008–2009, the precious metal commodity market experiences a major decline. In 2009, it bottoms out and starts to rebound. From 2011 to 2012, there is also a second round of major declines. Around 2014, it reaches a low point, and then begins to rise. From this point on, the two directions of acceptance and delivery overflow form a more consistent trend, oscillating in the interval of 0–20%.
> 
> The industrial metal commodity market begins to show a downward trend in volatility during the period 2008–2009, and has not broken through the high volatility spillover index since then. In the period 2017–2018, it appears an obvious upward peak. It can be seen that the industrial metal market and the precious metal market show similar trend change characteristics due to the close connection as metal commodities. This corresponds to the strong two-way spillover of industrial and precious metals in previous static full sample analysis.
> 
> The spillover effect of agriculture commodity market shows great volatility, in which there are obvious peaks around 2010, 2011, 2014, 2019 and 2020. The livestock commodity market is similar to the agriculture commodity market in the trend of "From" and "To" spillovers, with significant peaks in 2010, 2011, 2014, 2018, 2019 and 2020. This is related to the fact that during the period of great [agricultural development](https://www.sciencedirect.com/topics/economics-econometrics-and-finance/agricultural-development "Learn more about agricultural development from ScienceDirect's AI-generated Topic Pages") driven by industrialization, the connection between agriculture and livestock commodities becomes closer. Many developed countries begin to develop mixed agriculture, which is a mixed [grain](https://www.sciencedirect.com/topics/food-science/cereal "Learn more about grain from ScienceDirect's AI-generated Topic Pages") and livestock agriculture that organically combines livestock rearing and grain production.

#### 3-GARCH-MIDAS model

**==GARCH-MIDAS模型通过将波动率分解为短期GARCH成分和长期MIDAS成分，能够有效分析低频地缘政治风险对高频商品市场波动率的影响。==**


> [!NOTE] [[GARCH-MIDAS模型]]
> The inter-market connectedness index calculated based on the improved Diebold & Yilmaz method is the weekly frequency, while the measure of geopolitical risk (i.e., GPR index) is the monthly frequency. About mixing data, if the high-frequency data is down-frequency processed, the effective information in the high-frequency data will be lost, causing bias in parameter estimation, and unable to accurately assess the impact of geopolitical risks on the level of spillover between commodity markets. [Ghysels et al. (2007)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0170) first propose the mixed data sampling model (Mixed Data Sampling, referred to as MIDAS) to optimize the estimation of different frequency samples. On this basis, [Engle et al. (2013)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0145) develop a GARCH-MIDAS model, and apply this model to evaluate the impact of macroeconomic conditions on stock market volatility. They improve the effectiveness of parameter estimation and separate the impact of economic uncertainty on the different components of stock market volatility. Thus, the GARCH-MIDAS model is widely used to study the issues in economy and [finance](https://www.sciencedirect.com/topics/economics-econometrics-and-finance/finance "Learn more about finance from ScienceDirect's AI-generated Topic Pages") (e.g., [Wei et al., 2017](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0445); [Liu et al., 2021a](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0300); [Ma et al., 2021a](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0320)).
> 
> Under the basis of Engle's research, this paper constructs a GARCH-MIDAS model with exogenous variables to analyze the impact of geopolitical risks on the level of spillovers between commodity markets. The conditional variance of the traditional GARCH model can be decomposed into two parts——high-frequency short-term fluctuations and low-frequency long-term fluctuations, expressed as:(11)where _r__it_ is the logarithmic return of _i_-th day of _t_-th month. _μ__t_ is the conditional expectation of _r__it_, _ε__t_ is the error term and obeys normal distribution, that is _ε__t_ ∣ Φ_i_ − 1, _t_~_N_(0, 1).
> 
> The volatility _σ__it_2 is affected by the long-term trend _τ__t_ and the short-term trend _g__it_.(12)where short-term trend _g__it_ obeys the GARCH (1,1) process as follows.(13)(14)where _m_ is the constant term. _θ_ represents the long-term impact coefficient on volatility of RV. _k_ is the lag period. _K_ is the largest lag period of RV.(15)
> 
> Furthermore, from Eq. [(14)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#fo0075), we can see that the long-term trend _τ__t_ can be described as a specification containing different low-frequency variables X, and in this paper, it is the geopolitical risk indexes. In order to study the impact of geopolitical risk (GPR) on the long-term trend _τ__t_, we empirically replace the realized volatility _RV__t_ − _k_ in Eq. [(14)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#fo0075) with geopolitical risk (GPR), and we get the following GARCH-MIDAS model of geopolitical risk. We consider three equations in total, namely the overall geopolitical risk index (GPR), the geopolitical risk sub-index—the geopolitical threat risk index (GPT), and the geopolitical risk sub-index—geopolitical act risk index (GPA), respectively expressed as:
> 
> GARCH-MIDAS-GPR model:(16)
> 
> GARCH-MIDAS-GPT model:(17)
> 
> GARCH-MIDAS-GPA model:(18)
> 
> [Engle et al. (2013)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0145) propose the weighted lagged structure of the Beta index, while [Ghysels et al. (2007)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0170) further point out that the Beta polynomial weight method is more flexible and more adaptable to various lag structures. Therefore, this paper uses Beta-type weight function. Φ_k_(_ω_1, _ω_2) is the weight function of the Beta-type lag variable, and the specific form is(19)
> 
> In order to ensure that the weight of the lagging variable shows a declining trend (the closer to the current period, the greater the impact), _ω_1 = 1 is generally fixed ([Conrad and Loch, 2015](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0115)), and the coefficient _ω_2 determines the attenuation speed of the influence of low-frequency data on high-frequency data. The decay rate can be clearly observed in this way. If the value of _ω_2 gets larger, the decay rate becomes faster, and vice versa. [Conrad and Loch (2015)](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0115) point out the restriction _ω_1 = 1, _ω_2 > 1 guarantees a decaying pattern, i.e. the maximum weight is at the first lag. Their choice has been followed by a few papers ([Engle et al., 2013](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0145); [Liu et al., 2019](https://www.sciencedirect.com/science/article/pii/S0140988322001979?via%3Dihub#bb0295)). This paper selects the appropriate _K_1 and _K_2 based on the BIC and SC information criteria. Then, the Beta weight function is simplified to:(20)
> 
> In addition, we use maximum likelihood to estimate the above GARCH-MIDAS model, the maximum likelihood function is:(21)

![[截屏2025-06-18 17.31.55.png]]






# 4-结论 (Conclusion)



# 5-introduction和文献综述

*   **检验方法 (Methods):**
    *   使用了哪些稳健性检验方法？
*   **检验结果 (Results):**
    *   稳健性检验的结果如何？
    *   结果是否支持主要结论？


*   这篇论文对我的研究有什么启发？