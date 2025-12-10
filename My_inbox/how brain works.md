---
aliases: 
created: '[[2025-09-03]]'
🤔: 
in: 
up: 
related: 
author:
---
# 🌲 Evergreen Note
```
# note的部分是本篇文章的原文
# summary的部分是我对于原文部分重点的提取，以及自己的思考（用🤔来代表我的思考，**、*====* 是我对重点的两个层级标识）

请你根据# note和# summary的部分帮我总结{activeNote}，按“概述”模式输出。 
> [!summary] 概述  （要写具体内容，点列格式，排版紧凑）
>  
>   
> **一句话**： 

```


一只股票记为G 是一个现实世界的实体。
G(X,Y,Z,...)

我们记alpha=f(y,z,...)  是股票其他指标的一个函数

那么alpha

```
> [!summary] 概述
>
> *   **核心目的**：详细解释 WorldQuant BRAIN 平台如何运作，以及模拟 Alpha 时后台发生的步骤，帮助用户培养直觉，优化 Alpha 创建过程。
> *   **数据结构**：将市场数据视为一个矩阵，其中行代表日期，列代表股票，例如 US TOP3000 股票的收盘价数据。
> *   **模拟过程**：
> 	*   平台针对五年跨度内的每个日期，对市场数据矩阵评估 Alpha 表达式。
> 	*   为每个金融工具持有多头或空头头寸，从而生成 PnL 图表。
> *   **七个步骤**：
> 	*   **步骤 1**：评估表达式，生成 Alpha 向量。
> 	*   **步骤 2**：中性化，从向量中的每个值减去该组向量值的平均值，使所有向量值的总和为 0。
> 	*   **步骤 3**：标准化，缩放向量值，使绝对值总和为 1，得到标准化权重。
> 	*   **步骤 4**：资金分配，使用标准化权重，将 2000 万美元的虚拟资金分配给每只股票。
> 	*   **步骤 5**：计算次日 PnL，根据股票回报计算 Alpha 产生的 PnL。
> 	*   **步骤 6**：重复步骤 1-5，获取样本内期间 (IS) 的每日 PnL。
> 	*   **步骤 7**：计算累积 PnL，生成 Alpha 的 PnL 图表。
> *   **多空市场中性化**：通过多空仓位，策略在市场不同方向都有盈利潜力。
> *   **Alpha 权重**：Alpha 权重是分配给每只股票的权重位置，乘以账面规模得到美元价值。
> *   **换手率**：每日交易的投资组合百分比，模拟结果中报告的是平均日换手率。
> *   **衰减 (Decay)**：引入衰减后，Alpha 的权重结合了当日值和前几日的衰减值，减少交易成本和过度反应。
> *   **样本内 (IS) 和样本外 (OS) 期间**：模拟器计算 IS 期间的 PnL，而 OS 期间用于评估 Alpha 的稳健性。
>
> **一句话**：本文详细解释了 WorldQuant BRAIN 平台模拟 Alpha 的七个步骤，包括数据处理、中性化、标准化、资金分配、PnL 计算以及衰减的应用，旨在帮助用户理解平台运作机制，从而更有效地创建和评估量化交易策略。
```



---
# ✍️ Summary
-　


- ## ref
	- 📒：
	- link：
- ## Logs
	- [[2025-09-03]]
- ## to do
	- [ ] 
---
# 📒 Note


[

  
Simulate

](https://platform.worldquantbrain.com/simulate)[

Alphas

](https://platform.worldquantbrain.com/alphas/unsubmitted)[

Learn

](https://platform.worldquantbrain.com/learn)[

Data

](https://platform.worldquantbrain.com/data)

Competitions (1)

[

Team

](https://platform.worldquantbrain.com/team/active)[

Community

](https://support.worldquantbrain.com/hc/en-us/community/topics)[

Consultant program

](https://platform.worldquantbrain.com/consultant-program/)[

Refer a friend

](https://platform.worldquantbrain.com/referral)

Notifications

User menu

[Courses  课程](https://platform.worldquantbrain.com/learn/courses)[Documentation  文档](https://platform.worldquantbrain.com/learn/documentation)[Operators  操作员](https://platform.worldquantbrain.com/learn/operators)[FAQ  常见问题解答](https://support.worldquantbrain.com/hc/en-us)[Events  活动](https://platform.worldquantbrain.com/events/)[Glossary  术语表](https://support.worldquantbrain.com/hc/en-us/articles/4902349883927)

[Documentation  文档](https://platform.worldquantbrain.com/learn/documentation)[Next: ⭐ Alpha Examples for Beginners  下一页：⭐ 初学者的 Alpha 示例](https://platform.worldquantbrain.com/learn/documentation/create-alphas/19-alpha-examples)

## ⭐ How BRAIN works

The below post illustrates in detail how the BRAIN platform works and what happens in the background when you simulate an Alpha. Even though you’ll never need to do these calculations yourselves, developing an intuition for them will help you in the Alpha making process.  
下面的帖子详细说明了 BRAIN 平台的工作原理，以及当你模拟 Alpha 时后台会发生什么。即使你永远不需要自己进行这些计算，培养对它们的直觉也将有助于你在 Alpha 制作过程中。

Imagine market data being a matrix, with each row representing one date and each column representing one stock. For example, the matrix for close price data of stocks in [universe](https://support.worldquantbrain.com/hc/en-us/articles/4902349883927-Click-here-for-a-list-of-terms-and-their-definitions#:~:text=U-,Universe,-Universe) US TOP3000 would look like this:  
想象市场数据是一个矩阵，每一行代表一个日期，每一列代表一只股票。例如，US TOP3000 股票组合的收盘价数据矩阵看起来是这样的：

![1 table.png](https://api.worldquantbrain.com/content/images/290v4zN6dVd09ELH52-1BLCEtIg=/246/original/1_table.png)

When you input the simulation settings and click “Simulate”, the BRAIN platform will evaluate the Alpha expression against the matrix of market data for each date in a five year span, taking a long or short position for each financial instrument to generate the PnL chart.  
当你输入模拟设置并点击“模拟”时，BRAIN 平台将针对五年跨度内的每个日期，对市场数据矩阵评估 Alpha 表达式，为每个金融工具持有多头或空头头寸，从而生成 PnL 图表。

![2_simulate_771x.png](https://api.worldquantbrain.com/content/images/NwdRXoZepImHCXsWwisSJipBYbQ=/259/original/2_simulate_771x.png)

Behind the scenes, seven steps, or operations, are performed before the final PnL chart is generated.  
在最终 PnL 图表生成之前，后台会执行七个步骤或操作。

Normally, in an Alpha simulation, there would be between 200 and 3,000 stock instruments in the universe. But to better understand this concept, we’ll assume a hypothetical scenario in which the simulation universe has only eight stocks. We simulate the expression **rank(-returns)** with market neutralization, Delay 1 and Decay 0 settings for now.  
通常情况下，在 Alpha 模拟中，股票池中会有 200 到 3,000 种股票工具。但为了更好地理解这个概念，我们将假设一个模拟场景，其中模拟股票池只有八只股票。目前我们使用市场中性化、延迟 1 和衰减 0 的设置来模拟表达式 rank(-returns)。

The hypothesis in this expression is that we want to buy, or go long on, those stocks tomorrow that had negative or comparatively lower returns today, and we want to sell, or go short on, those stocks tomorrow that had positive or comparatively higher returns today.  
这个表达式的假设是我们希望买入或做多那些今天表现负或相对较低收益的股票，同时卖出或做空那些今天表现正或相对较高收益的股票。

We’ve used the rank operator, which ranks the input values inside the operator and return values equally distributed between zero and 1. This is an example of a reversion idea.  
我们使用了 rank 运算符，该运算符对运算符内的输入值进行排序，并返回在 0 和 1 之间均匀分布的值。这是一个回归思想的例子。

![3 table.png](https://api.worldquantbrain.com/content/images/21_y9-wzhl0hc08V2_q6iBlIGOg=/249/original/3_table.png)

In Column B, we have the eight stocks in the Alpha vector. Column C shows the returns of these stocks as of February 1st. These serve as the input data of the Alpha expression.  
在 B 列中，我们有 Alpha 向量中的八只股票。C 列显示了这些股票在 2 月 1 日的收益。这些是 Alpha 表达式的输入数据。

**Step1:** Evaluate the expression for each stock to generate the Alpha vector for the given date.  
步骤 1：对每只股票评估表达式，为给定日期生成 Alpha 向量。

In our case, this date would be February 2nd, because we’ve assumed Delay 1 settings. The Delay 1 setting uses data as of T-1 date to create the Alpha vector as of T date.  
在我们的案例中，这个日期是 2 月 2 日，因为我们假设了延迟 1 设置。延迟 1 设置使用 T-1 日期的数据来创建 T 日期的 Alpha 向量。

To produce the Alpha vector, the simulator performs the rank operation on negative returns and produces a vector of values corresponding to each stock.  
为了生成 Alpha 向量，模拟器对负回报执行排名操作，并生成对应每只股票的值向量。

![4 table.png](https://api.worldquantbrain.com/content/images/XpIzC8CMeVY_hhMY01UeksNeu6g=/250/original/4_table.png)

The resulting vector depends on the operators used in the Alpha expression. In our case, since we’ve used the rank operator, we see equally distributed values between 0 and 1 in Column D. Note that the stock with the lowest return has the highest value, and vice versa, in line with our hypothesis.  
结果向量取决于 Alpha 表达式中使用的操作符。在我们的案例中，因为我们使用了排名操作符，所以在 D 列中看到 0 到 1 之间均匀分布的值。请注意，回报最低的股票具有最高值，反之亦然，这与我们的假设一致。

**_Step 2_**_: From each value in the vector, subtract the average of the vector values in the group. Sum of all vector values = 0._ This is called neutralization.  
第二步：从向量中的每个值减去该组向量值的平均值。所有向量值的总和=0。这称为中和。

The group can be the entire market, but we can also perform this neutralization operation on sector, industry or subindustry groupings of stocks.  
该组可以是整个市场，但我们也可以对股票的行业、行业或子行业分组执行此中和操作。

![5 table.png](https://api.worldquantbrain.com/content/images/bSCbjW3xSTCOReSxQDS9SANd-XA=/251/original/5_table.png)

Since we have only eight stocks in our simulation universe, we’ve assumed to neutralize the stocks over the market.  
由于我们的模拟宇宙中只有八只股票，我们假设对市场中的股票进行中和。

So we take the average of the numbers in Cell D12 and subtract the average from each stock. This gives us a new vector in Column F. Note that both the sum and the average of these new numbers are now zero. Also, the sum of positive values is equal to the sum of negative values.  
因此，我们取单元格 D12 中数字的平均值，并从每只股票中减去该平均值。这给我们带来了 F 列的新向量。请注意，这些新数字的总和和平均值现在都为零。此外，正值的总和等于负值的总和。

**_Step 3:_** _The resulting values are scaled or ‘normalized’ such that absolute sum of the Alpha vector values is 1. These values can be called as normalized weights._  
步骤 3：所得值被缩放或“标准化”，使得 Alpha 向量值的绝对和为 1。这些值可以称为标准化权重。

![6 table.png](https://api.worldquantbrain.com/content/images/MAMy_pb98V3wa96cybcwjrmnOEM=/252/original/6_table.png)

That means, we sum the absolute values of each row and find the sum, which is 2.3. Then we divide each row by this sum, which results in normalized values. By normalize, we mean that the total absolute sum of Column H is 1. We can also call this vector a normalized vector of weights.  
这意味着，我们将每一行的绝对值相加并求和，得到 2.3。然后我们将每一行除以这个和，得到归一化值。通过归一化，我们指的是列 H 的绝对值总和为 1。我们也可以称这个向量为权重归一化向量。

Note: On each iteration/day, the expression rank(-returns) will have access to all the data for returns up to that day, and the matrix will grow by one line every day until it reaches the most recent date. The role of the expression is to transform the input matrix to an output vector of weights as we see in this hypothetical example.  
注意：在每次迭代/每天，表达式 rank(-returns)将能够获取截至当天的所有回报数据，矩阵每天会新增一行，直到达到最新日期。该表达式的功能是将输入矩阵转换为输出权重向量，正如在这个假设示例中所看到的。

**_Step 4:_** _Using normalized weights, the BRAIN simulator allocates capital (from a fictitious book of $20 million) to each stock to construct a portfolio._  
步骤 4：使用标准化权重，BRAIN 模拟器将资本（来自一个虚构的 2000 万美元账户）分配给每只股票，以构建投资组合。

![7 table.png](https://api.worldquantbrain.com/content/images/0zjHFMsINZDVlpwLEVA_skZ2-es=/253/original/7_table.png)

> [!NOTE]
> Column J has a total of $20 million of fictional money allocated to the stocks, using the normalized weights in Column H. This means we have a position of minus $4.4 million in Stock 1 — that is, we’ve shorted $4.4 million worth of Stock 1 — and a long position of $0.6 million in Stock 5. That is, we’ve invested $0.6 million in Stock 5.  
> 列 J 总共分配了 2000 万美元的虚拟资金给股票，使用列 H 中的标准化权重。这意味着我们在股票 1 上的头寸为-440 万美元——也就是说，我们做空了价值 440 万美元的股票 1——而在股票 5 上的多头头寸为 60 万美元。也就是说，我们在股票 5 上投资了 60 万美元。
> 
> This is called long-short market neutralization, and it’s the backbone of creating these predictive models, or Alphas, on BRAIN. With this technique, a strategy can have the potential to be profitable regardless of the direction of the market.  
> 这被称为多空市场中性化，它是创建 BRAIN 上的这些预测模型或 Alpha 的核心。使用这种技术，策略无论市场朝哪个方向走都有可能盈利。
> 

**_Step 5:_** _Calculate next day PnL generated by the Alpha based on observed stock returns the next day_  
步骤 5：根据次日观察到的股票回报计算 Alpha 产生的次日 PnL

That is, after allocating dollar positions on the stocks, we calculate the PnL generated by each stock, based on the returns each stock had that day.  
也就是说，在分配股票的资金头寸后，我们根据每只股票当日的回报计算每只股票产生的 PnL。

![8 table.png](https://api.worldquantbrain.com/content/images/V_X2U8gzlp9lsHoc6cyieR9dRDM=/254/original/8_table.png)

Suppose the actual returns on these stocks as of February 2nd are as shown in Column K. We see that although we expected Stock 1 and Stock 2 to fall in price, they actually went up, so we had a loss, shown in Column L.  
假设截至 2 月 2 日，这些股票的实际收益如 K 列所示。我们看到，尽管我们预期股票 1 和股票 2 的价格会下跌，但它们实际上上涨了，因此我们亏损了，如 L 列所示。

We expected Stock 6 to go up in price, but it stayed flat. So we were wrong about three stocks, but we were right about five. In total, we made a gain of $0.03 million on this day with our Alpha, calculated by adding the PnLs of all stocks in our vector. This is how the simulator calculates the PnL generated by the Alpha for any given date.  
我们预期股票 6 的价格会上涨，但它保持不变。因此，我们对三只股票的判断是错误的，但对五只股票的判断是正确的。总而言之，我们通过 Alpha 策略在这一天获得了 30 万美元的收益，这是通过将我们投资组合中所有股票的 PnL 相加计算得出的。这就是模拟器计算 Alpha 在任何给定日期产生的 PnL 的方式。

**_Step 6:_** _Perform the operations in Step 1 to Step 5 for each date in a several-year history span also called the In-sample period (IS) to get daily PnL generated for each day_  
步骤 6：对几年历史跨度内的每个日期（也称为样本内期间，IS）执行步骤 1 至步骤 5 的操作，以获取每天产生的每日 PnL

> [!NOTE]
> For each day, the expression is evaluated and the values in the Alpha output vector represent the weights to allocate to each stock. Alpha weights are not how much you want to buy or sell, but a weighting position you would reach this day. These weights are multiplied by book size (total money invested in the portfolio) to get the dollar value held in each stock. For example, if the Alpha weight (after [neutralization](https://support.worldquantbrain.com/hc/en-us/articles/4902349883927-Click-here-for-a-list-of-terms-and-their-definitions#:~:text=strategy.-,Neutralization,-Neutralization) and scaling) for MSFT is 0.2423, then we’ll have MSFT stocks with the total value 0.2423*book size.  
> 对于每一天，都会计算表达式，Alpha 输出向量中的值代表分配给每只股票的权重。Alpha 权重并不是你想买入或卖出的数量，而是你当天会达到的权重位置。这些权重乘以账面规模（投资组合中的总资金）以获得每只股票持有的美元价值。例如，如果 Alpha 权重（经过中和和缩放后）对 MSFT 是 0.2423，那么我们将持有总价值为 0.2423*账面规模的 MSFT 股票。

The [weight](https://support.worldquantbrain.com/hc/en-us/articles/4902349883927-Click-here-for-a-list-of-terms-and-their-definitions#:~:text=W-,Weight,-BRAIN) can be negative, meaning you would take a short position on these stocks. If the value is positive, you would take a long position on these stocks, i.e. buy the stocks. A [NAN](https://support.worldquantbrain.com/hc/en-us/articles/4902349883927-Click-here-for-a-list-of-terms-and-their-definitions#:~:text=N-,NaN,-NaN) value would mean no weight is allocated to that instrument (i.e. no money is allocated). The value of stocks you buy/sell on a particular day is determined by the difference between weights today and weights yesterday. The percentage of your portfolio traded in a day (by dollar value) is called ‘turnover’. The [turnover](https://support.worldquantbrain.com/hc/en-us/articles/4902349883927-Click-here-for-a-list-of-terms-and-their-definitions#:~:text=details.-,Turnover,-Average) reported in [simulation](https://support.worldquantbrain.com/hc/en-us/articles/4902349883927-Click-here-for-a-list-of-terms-and-their-definitions#:~:text=definition.-,Simulation,-Simulation) results is the average daily turnover over the simulation.  
权重可以是负数，这意味着你会对这些股票持空头头寸。如果值是正数，你会对这些股票持多头头寸，即买入这些股票。NAN 值表示没有分配权重给该工具（即没有分配资金）。你在某一天买入/卖出股票的金额由当天权重和前一天权重的差值决定。你投资组合在一天内交易的比例（按美元价值计算）称为“换手率”。模拟结果中报告的换手率是模拟期间的平均日换手率。

**_Step 7:_** _Calculate the cumulative PnL of the Alpha from the start of the in-sample period to get the PnL chart of the Alpha._  
步骤 7：计算 Alpha 从样本期开始到结束的累积 PnL，以获取 Alpha 的 PnL 图表。

Based on those daily positions, [PnL](https://support.worldquantbrain.com/hc/en-us/articles/4902349883927-Click-here-for-a-list-of-terms-and-their-definitions#:~:text=consultants-,Profit%20and%20Loss%20\(PnL\),-Profit) is calculated and displayed. By default, the BRAIN platform will normalize your weights (according to the operations you enter) and create a portfolio of $20 million (total [booksize](https://support.worldquantbrain.com/hc/en-us/articles/4902349883927-Click-here-for-a-list-of-terms-and-their-definitions#:~:text=details.-,Booksize,-Booksize)) worth of equity. (Note that a portfolio is just a collection of securities.)  
基于这些每日头寸，计算并显示 PnL。默认情况下，BRAIN 平台将根据您输入的操作对权重进行标准化，并创建一个总市值达 2000 万美元的股票投资组合。（注意：投资组合仅是一组证券的组合。）

This can be better understood with the help of the PnL chart of the Alpha in our example rank(-returns)

![9 graph.png](https://api.worldquantbrain.com/content/images/DZS0EvjBfPBaNVkuezf0A4b7xt8=/255/original/9_graph.png)

In this chart, we have an IS period of five years, from February 2016 to January 2021. Using the steps from the example, the simulator would calculate the daily PnL of the Alpha and derive the cumulative PnL chart, as we see here. Note that the two years from February 2021 to January 2023 are not visible to us in the simulation window. That’s called the out-of-sample, or the OS, period. After you submit an Alpha, several tests are run to analyze the Alpha’s performance in the OS period. An Alpha that passes both the in-sample and out-of-sample tests can be said to be a robust Alpha.

This is how the BRAIN simulator creates the PnL chart from an Alpha.

In our example, we’ve assumed that we’re using market neutralization and Decay 0 settings. But if we used any other neutralization settings, the same operations would be performed on the Alpha.

Say we have 80 stocks in our simulation universe — ten industries with eight stocks each. The simulator would perform the same operations (first Step 1 to Step 5) on each of the ten groups and finally add the PnL from each group to get the daily PnL of the Alpha and create the cumulative PnL chart (Step 6 and Step 7)

However, if we introduce decay into our Alpha settings, an additional step must be performed to get the final Alpha vector.

Suppose we use a decay of 3 in our simulation settings. The final vector of weights in the Alpha would be calculated by combining today’s value with the previous day’s decayed value. In our example, we calculated the normalized weights in the Alpha as of February 2nd. Let’s assume that the normalized weights of stocks in the Alpha vector on February 1st and January 31st are as shown in Columns N and O, respectively.

![10 table.png](https://api.worldquantbrain.com/content/images/RC4miaFltfYX2hKtqxeCgKLZe1M=/256/original/10_table.png)

Then the final weights in the Alpha would be calculated using the given weighted average formula:

which is implemented in Column P. Using this new derived vector, the simulator would calculate the daily PnL and consequently the cumulative PnL chart. Note that even if decay is used, more weight is assigned to the most recent values. So decay is an important factor in reducing transaction costs or turnover, as it includes information from previous days, preventing the Alpha from being reactive.

To summarize, once we input the Alpha expression and simulation settings in the BRAIN simulator, it performs the operations discussed above to take long or short positions for each financial instrument and generates the PnL chart.

[Prev: How to choose the Simulation Settings](https://platform.worldquantbrain.com/learn/documentation/create-alphas/simulation-settings)[Next: ⭐ Alpha Examples for Beginners](https://platform.worldquantbrain.com/learn/documentation/create-alphas/19-alpha-examples)

