---
aliases: 
created: '[[2025-09-17]]'
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

> [!summary] 概述
>
>   *   **核心目的**：提供快速理解 WorldQuant BRAIN 中新数据字段的六种方法，用于创建 Alpha 因子。
>   *   **方法概述**：通过在“无”中性化和衰减 0 设置下模拟特定表达式，并分析 IS 摘要部分的长期计数和短期计数，来获取数据字段的见解。
>   *   **六种方法**：
> 	*   方法 1：`datafield` - 评估数据字段的覆盖率。
> 	*   方法 2：`datafield != 0 ? 1 : 0` - 确定数据字段的覆盖率，长期计数表示每日平均非零值。
> 	*   方法 3：`ts_std_dev(datafield,N) != 0 ? 1 : 0` - 确定唯一数据的频率（每日、每周、每月等），通过改变 N 值来查找数据更新频率。
> 	*   方法 4：`abs(datafield) > X` - 确定数据字段的边界，通过改变 X 的值并查看长期计数来判断字段是否归一化。
> 	*   方法 5：`ts_median(datafield, 1000) > X` - 确定数据字段在 5 年内的中位数，改变 X 的值并查看长期计数。
> 	*   方法 6：`X < scale_down(datafield) && scale_down(datafield) < Y` - 确定数据字段的分布情况，scale_down 充当 MinMaxScaler，X 和 Y 是介于 0 和 1 之间的值。
>   *   **示例**：模拟 `close <= 0`，如果多空计数都为 0，则表示收盘价总是正值。
>
> **一句话**：本文提供了六种在 WorldQuant BRAIN 中快速理解新数据字段的方法，通过模拟表达式并分析长期计数和短期计数来获取数据字段的覆盖率、频率、边界和分布等信息。



---
# ✍️ Summary
-　


- ## ref
	- 📒：
	- link：
- ## Logs
	- [[2025-09-17]]
- ## to do
	- [ ] 
---
# 📒 Note

WorldQuant BRAIN has thousands of datafields for you to create alphas. But how do you quickly understand a new datafield? Here are 6 ways. Simulate the below expressions in “None” neutralization and decay 0 setting. And obtains insights of specific parameters using the Long Count and Short Count in the IS Summary section of the results.  
WorldQuant BRAIN 为您提供了数千个数据字段用于创建 alpha。但如何快速理解一个新数据字段呢？这里有 6 种方法。在“无”中性化和衰减 0 设置下模拟以下表达式。并使用结果中的 IS 摘要部分的长期计数和短期计数获取特定参数的见解。

|                |                                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| -------------- | ------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Sr. No  序号** | **Expression  表达式**                                    | **Insight  见解**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| 1              | datafield  数据字段                                        | % **coverage**, would approximately be ratio of (Long Count + Short Count in the IS Summary )/ (Universe Size in the settings)  <br>% 覆盖率，大约为（长期计数 + IS 摘要中的短期计数）/（设置中的宇宙大小）                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| 2              | datafield != 0 ? 1 : 0  <br>数据字段 != 0 ? 1 : 0          | **Coverage**. Long Count indicates average non-zero values on a daily basis  <br>覆盖率。长期计数表示每日平均非零值                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| 3              | ts_std_dev(datafield,N) != 0 ? 1 : 0                   | **Frequency** of unique data (daily, weekly, monthly etc.).  <br>唯一数据的频率（每日、每周、每月等）。<br><br>Some datasets have data backfilled for missing values, while some do not. The given expression can be used to find the frequency of unique datafield updates by varying N (no. of days).  <br>一些数据集会对缺失值进行后填，而另一些则不会。通过改变 N（天数）可以使用给定的表达式来查找唯一 datafield 更新的频率。<br><br>Datafields with a quarterly unique data frequency would see a Long Count + Short Count value close to its actual coverage when N = 66 (quarter). When N = 22 (month) Long Count + Short Count would be lower (approx. 1/3rd of coverage) and when N = 5 (week), Long Count + Short Count would be even lower.  <br>具有季度唯一数据频率的数据字段，当 N = 66（季度）时，Long Count + Short Count 值会接近其实际覆盖范围。当 N = 22（月）时，Long Count + Short Count 会较低（约覆盖范围的 1/3），而当 N = 5（周）时，Long Count + Short Count 会更低。 |
| 4              | abs(datafield) > X                                     | **Bounds** of the datafield. Vary the values of X and see the Long Count. For example, X=1 will indicate if the field is normalized to values between -1 and +1?  <br>datafield 的边界。改变 X 的值，查看 Long Count。例如，X=1 将显示该字段是否归一化到-1 和+1 之间的值？                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| 5              | ts_median(datafield, 1000) > X                         | **Median** of the datafield over 5 years. Vary the values of X and see the Long Count. Similar process can be applied to check the mean of the datafield.  <br>datafield 在 5 年内的中位数。改变 X 的值，查看 Long Count。类似的过程可以应用于检查 datafield 的平均值。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| 6              | X < scale_down(datafield) && scale_down(datafield) < Y | **Distribution** of the datafield. scale_down acts as a MinMaxScaler that can preserve the original distribution of the data. X and Y are values that vary between 0 and 1 that allow us to check how the datafield distribute across its range.  <br>datafield 的分布情况。scale_down 充当一个 MinMaxScaler，可以保留数据的原始分布。X 和 Y 是介于 0 和 1 之间的值，使我们能够检查 datafield 在其范围内的分布情况。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

For example, if you simulate [close <= 0], You will see Long and Short Counts as 0. This implies that closing price always has a positive value (as expected!)  
例如，如果你模拟[收盘价 <= 0]，你会看到多空计数都为 0。这意味着收盘价总是具有正值（正如预期的那样）！


