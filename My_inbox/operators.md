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

  
Simulate  模拟

](https://platform.worldquantbrain.com/simulate)[

Alphas  Alpha

](https://platform.worldquantbrain.com/alphas/unsubmitted)[

Learn  学习

](https://platform.worldquantbrain.com/learn)[

Data  数据

](https://platform.worldquantbrain.com/data)

Competitions (1)  竞赛 (1)

[

Team  团队

](https://platform.worldquantbrain.com/team/active)[

Community  社区

](https://support.worldquantbrain.com/hc/en-us/community/topics)[

Consultant program  顾问计划

](https://platform.worldquantbrain.com/consultant-program/)[

Refer a friend  推荐朋友

](https://platform.worldquantbrain.com/referral)

Notifications  通知

User menu  用户菜单

[Courses  课程](https://platform.worldquantbrain.com/learn/courses)[Documentation  文档](https://platform.worldquantbrain.com/learn/documentation)[Operators  操作符](https://platform.worldquantbrain.com/learn/operators)[FAQ  常见问题解答](https://support.worldquantbrain.com/hc/en-us?_gl=1*uuonae*_gcl_au*Njg1NjU2NjU3LjE3NTUxNTMwMDM.*_ga*MTc1NTE1MzAwMDQzMWEwNzQyZWYxMzRkNzc.*_ga_9RN6WVT1K1*czE3NTY5MTMyMDUkbzE1JGcxJHQxNzU2OTEzODY4JGo0MCRsMCRoMA..)[Events  活动](https://platform.worldquantbrain.com/events/)[Glossary  术语表](https://support.worldquantbrain.com/hc/en-us/articles/4902349883927)

## Operators  算子

Unlock more complex operators at Expert, Master and Grandmaster Genius levels.  
在专家、大师和大宗师天才级别解锁更复杂的操作符。

## Arithmetic  算术

  操作符

  描述

abs(x)

base

Absolute value of x  x 的绝对值

add(x, y, filter = false), x + y

base

Add all inputs (at least 2 inputs required). If filter = true, filter all input NaN to 0 before adding  
添加所有输入（至少需要 2 个输入）。如果 filter = true，则在相加前将所有输入的 NaN 过滤为 0

densify(x)

base

Converts a grouping field of many buckets into lesser number of only available buckets so as to make working with grouping fields computationally efficient  
将包含多个桶的分组字段转换为更少的可用桶，以使处理分组字段在计算上更高效

Show more  显示更多

divide(x, y), x / y

base  基本

x / y

inverse(x)  逆(x)

base  底

1 / x

log(x)  对数(x)

base

Natural logarithm. For example: Log(high/low) uses natural logarithm of high/low ratio as stock weights.  
自然对数。例如：Log(high/low) 使用 high/low 比值的自然对数作为股票权重。

max(x, y, ..)

base

Maximum value of all inputs. At least 2 inputs are required  
所有输入的最大值。至少需要 2 个输入

Show more  显示更多

min(x, y ..)

base

Minimum value of all inputs. At least 2 inputs are required  
所有输入的最小值。至少需要 2 个输入

Show more  显示更多

multiply(x ,y, ... , filter=false), x * y

base

Multiply all inputs. At least 2 inputs are required. Filter sets the NaN values to 1  
将所有输入相乘。至少需要 2 个输入。Filter 将 NaN 值设置为 1

Show more  显示更多

power(x, y)

base

x ^ y

Show more  显示更多

reverse(x)

base

 - x

sign(x)

base

if input = NaN; return NaN

signed_power(x, y)

base

x raised to the power of y such that final result preserves sign of x  
x 的 y 次幂，最终结果保留 x 的符号

Show more  显示更多

sqrt(x)

base

Square root of x  x 的平方根

subtract(x, y, filter=false), x - y

base

x-y. If filter = true, filter all input NaN to 0 before subtracting  
x-y. 如果 filter = true，则在相减前将所有输入 NaN 过滤为 0

## Logical  逻辑值

  运算符

  描述

and(input1, input2)

base  基础

Logical AND operator, returns true if both operands are true and returns false otherwise  
逻辑与运算符，当两个操作数都为真时返回 true，否则返回 false

if_else(input1, input2, input 3)  
if_else(input1, input2, input3)

base  基础

If input1 is true then return input2 else return input3.  
如果 input1 为真，则返回 input2，否则返回 input3。

Show more  显示更多

input1 < input2

base

If input1 < input2 return true, else return false  
如果 input1 < input2 返回 true，否则返回 false

input1 <= input2

base

Returns true if input1 <= input2, return false otherwise  
如果 input1 <= input2，则返回 true，否则返回 false

input1 == input2

base

Returns true if both inputs are same and returns false otherwise  
如果两个输入相同则返回 true，否则返回 false

input1 > input2

base

Logic comparison operators to compares two inputs  
逻辑比较运算符用于比较两个输入

input1 >= input2

base

Returns true if input1 >= input2, return false otherwise  
如果 input1 >= input2，则返回 true，否则返回 false

input1!= input2  input1 != input2

base

Returns true if both inputs are NOT the same and returns false otherwise  
如果两个输入不相同，则返回 true，否则返回 false

is_nan(input)

base

If (input == NaN) return 1 else return 0  
如果（input == NaN）则返回 1，否则返回 0

Show more  显示更多

not(x)

base

Returns the logical negation of x. If x is true (1), it returns false (0), and if input is false (0), it returns true (1).  
返回 x 的逻辑否定。如果 x 为真（1），则返回假（0），如果输入为假（0），则返回真（1）。

or(input1, input2)

base

Logical OR operator returns true if either or both inputs are true and returns false otherwise  
逻辑或运算符在任一或两个输入为真时返回真，否则返回假

## Time Series  时间序列

  操作符

  描述

days_from_last_change(x)

base

Amount of days since last change of x  
距离上次 x 变化的天数

hump(x, hump = 0.01)

base

Limits amount and magnitude of changes in input (thus reducing turnover)  
限制输入的变化量和幅度（从而减少周转率）

Show more  显示更多

kth_element(x, d, k)

base

Returns K-th value of input by looking through lookback days. This operator can be used to backfill missing data if k=1  
通过查看回溯天数来返回输入的第 K 个值。如果 k=1，此算子可用于填补缺失数据

Show more  显示更多

last_diff_value(x, d)

base

Returns last x value not equal to current x value from last d days  
返回过去 d 天内最后一个不等于当前 x 值的 x 值

ts_arg_max(x, d)

base

Returns the relative index of the max value in the time series for the past d days. If the current day has the max value for the past d days, it returns 0. If previous day has the max value for the past d days, it returns 1  
返回过去 d 天内时间序列中最大值的相对索引。如果当前天是过去 d 天内的最大值，则返回 0。如果前一天是过去 d 天内的最大值，则返回 1

Show more  显示更多

ts_arg_min(x, d)

base

Returns the relative index of the min value in the time series for the past d days; If the current day has the min value for the past d days, it returns 0; If previous day has the min value for the past d days, it returns 1.  
返回过去 d 天中时间序列最小值的相对索引；如果当前天是过去 d 天中的最小值，则返回 0；如果前一天是过去 d 天中的最小值，则返回 1。

Show more  显示更多

ts_av_diff(x, d)

base

Returns x - tsmean(x, d), but deals with NaNs carefully. That is NaNs are ignored during mean computation  
返回 x - tsmean(x, d)，但会小心处理 NaN。也就是说，在计算平均值时会忽略 NaN。

Show more  显示更多

ts_backfill(x,lookback = d, k=1, ignore="NAN")

base

Backfill is the process of replacing the NAN or 0 values by a meaningful value (i.e., a first non-NaN value)  
填充是指用有意义的值（即第一个非 NaN 值）替换 NAN 或 0 值的过程

Show more  显示更多

ts_corr(x, y, d)

base

Returns correlation of x and y for the past d days  
返回过去 d 天的 x 和 y 的相关性

Show more  显示更多

ts_count_nans(x ,d)

base

Returns the number of NaN values in x for the past d days  
返回过去 d 天内 x 中的 NaN 值数量

ts_covariance(y, x, d)

base

Returns covariance of y and x for the past d days  
返回过去 d 天的 y 和 x 的协方差

ts_decay_linear(x, d, dense = false)

base

Returns the linear decay on x for the past d days. Dense parameter=false means operator works in sparse mode and we treat NaN as 0. In dense mode we do not.  
返回过去 d 天的 x 的线性衰减。Dense 参数=false 表示运算在稀疏模式下进行，我们将 NaN 视为 0。在密集模式下则不这样处理。

Show more  显示更多

ts_delay(x, d)

base

Returns x value d days ago  
返回 x 值 d 天前的值

ts_delta(x, d)

base

Returns x - ts_delay(x, d)  
返回 x - ts_delay(x, d)

ts_mean(x, d)

base

Returns average value of x for the past d days.  
返回过去 d 天的 x 平均值。

ts_product(x, d)

base

Returns product of x for the past d days  
返回过去 d 天的 x 乘积。

Show more  显示更多

ts_quantile(x,d, driver="gaussian" )

base

It calculates ts_rank and apply to its value an inverse cumulative density function from driver distribution. Possible values of driver (optional ) are "gaussian", "uniform", "cauchy" distribution where "gaussian" is the default.  
它计算 ts_rank 并将其应用于从驱动分布中获取的逆累积分布函数的值。驱动（可选）的可能值是"gaussian"、"uniform"、"cauchy"分布，其中"gaussian"是默认值。

ts_rank(x, d, constant = 0)

base

Rank the values of x for each instrument over the past d days, then return the rank of the current value + constant. If not specified, by default, constant = 0.  
对每个工具过去 d 天的 x 值进行排名，然后返回当前值的排名+常数。如果未指定，默认常数=0。

ts_regression(y, x, d, lag = 0, rettype = 0)

base

Returns various parameters related to regression function  
返回与回归函数相关的各种参数

Show more  显示更多

ts_scale(x, d, constant = 0)

base

Returns (x - ts_min(x, d)) / (ts_max(x, d) - ts_min(x, d)) + constant. This operator is similar to scale down operator but acts in time series space  
返回 (x - ts_min(x, d)) / (ts_max(x, d) - ts_min(x, d)) + constant。该操作符类似于降尺度操作符，但在时间序列空间中起作用

Show more  显示更多

ts_std_dev(x, d)

base

Returns standard deviation of x for the past d days  
返回过去 d 天的 x 的标准差

ts_step(1)

base

Returns days' counter  返回天数计数器

ts_sum(x, d)

base

Sum values of x for the past d days.  
对过去 d 天的 x 值求和。

ts_zscore(x, d)

base

Z-score is a numerical measurement that describes a value's relationship to the mean of a group of values. Z-score is measured in terms of standard deviations from the mean: (x - tsmean(x,d)) / tsstddev(x,d). This operator may help reduce outliers and drawdown.  
Z 分数是一个数值测量，用于描述一个值与一组值平均值的关系。Z 分数以标准差为单位衡量，即 (x - tsmean(x,d)) / tsstddev(x,d)。这个操作符有助于减少异常值和回撤。

## Cross Sectional  横截面

  操作符

  描述

normalize(x, useStd = false, limit = 0.0)

base

Calculates the mean value of all valid alpha values for a certain date, then subtracts that mean from each element  
计算特定日期所有有效 alpha 值的平均值，然后将该平均值从每个元素中减去

Show more  显示更多

quantile(x, driver = gaussian, sigma = 1.0)

base

Rank the raw vector, shift the ranked Alpha vector, apply distribution (gaussian, cauchy, uniform). If driver is uniform, it simply subtract each Alpha value with the mean of all Alpha values in the Alpha vector  
对原始向量进行排序，对排序后的 Alpha 向量进行平移，应用分布（高斯、柯西、均匀）。如果驱动器是均匀的，则只需将每个 Alpha 值减去 Alpha 向量中所有 Alpha 值的平均值

Show more  显示更多

rank(x, rate=2)

base

Ranks the input among all the instruments and returns an equally distributed number between 0.0 and 1.0. For precise sort, use the rate as 0  
将输入在所有工具中进行排序，并返回 0.0 到 1.0 之间的均匀分布数值。对于精确排序，将 rate 设置为 0

Show more  显示更多

scale(x, scale=1, longscale=1, shortscale=1)

base

Scales input to booksize. We can also scale the long positions and short positions to separate scales by mentioning additional parameters to the operator  
将输入缩放到书大小。我们也可以通过向操作符提及附加参数来将多头头寸和空头头寸缩放到不同的比例

Show more  显示更多

winsorize(x, std=4)

base

Winsorizes x to make sure that all values in x are between the lower and upper limits, which are specified as multiple of std.  
对 x 进行 Winsorize 处理，以确保 x 中的所有值都在指定的下限和上限之间，这些界限是标准差的倍数。

zscore(x)

base

Z-score is a numerical measurement that describes a value's relationship to the mean of a group of values. Z-score is measured in terms of standard deviations from the mean  
Z-score 是一个数值测量，描述了一个值与一组值平均值的关系。Z-score 以标准差为单位衡量与平均值的偏差

Show more  显示更多

## Vector  向量

  操作符

  描述

vec_avg(x)

base

Taking mean of the vector field x  
对向量场 x 取平均值

vec_sum(x)

base

Sum of vector field x  
向量场 x 的和

## Transformational  转换型

  操作符

  描述

bucket(rank(x), range="0, 1, 0.1" or buckets = "2,5,6,7,10")

base

Convert float values into indexes for user-specified buckets. Bucket is useful for creating group values, which can be passed to GROUP as input  
将浮点值转换为用户指定桶的索引。桶可用于创建分组值，这些值可以作为 GROUP 的输入

Show more  显示更多

trade_when(x, y, z)

base

Used in order to change Alpha values only under a specified condition and to hold Alpha values in other cases. It also allows to close Alpha positions (assign NaN values) under a specified condition  
用于在指定条件下仅更改 Alpha 值，并在其他情况下保持 Alpha 值。它还允许在指定条件下关闭 Alpha 头寸（分配 NaN 值）

Show more  显示更多

## Group  分组

  操作符

  描述

group_backfill(x, group, d, std = 4.0)

base

If a certain value for a certain date and instrument is NaN, from the set of same group instruments, calculate winsorized mean of all non-NaN values over last d days  
如果某个日期和某个工具的值是 NaN，则从同一组工具的集合中，计算过去 d 天内所有非 NaN 值的 winsorized 均值

Show more  显示更多

group_mean(x, weight, group)

base

All elements in group equals to the mean  
组内所有元素等于均值

Show more  显示更多

group_neutralize(x, group)

base

Neutralizes Alpha against groups. These groups can be subindustry, industry, sector, country or a constant  
对 Alpha 进行组别中性化。这些组别可以是子行业、行业、部门、国家或常数

Show more  显示更多

group_rank(x, group)

base

Each elements in a group is assigned the corresponding rank in this group  
组内每个元素被分配相应的组内排名

Show more  显示更多

group_scale(x, group)

base

Normalizes the values in a group to be between 0 and 1. (x - groupmin) / (groupmax - groupmin)  
将组内的值归一化到 0 和 1 之间。(x - groupmin) / (groupmax - groupmin)

group_zscore(x, group)

base

Calculates group Z-score - numerical measurement that describes a value's relationship to the mean of a group of values. Z-score is measured in terms of standard deviations from the mean. zscore = (data - mean) / stddev of x for each instrument within its group.  
计算组 Z 分数 - 一种数值测量方法，描述一个值与一组值平均值的关系。Z 分数以标准差为单位衡量。zscore = (data - mean) / x 在其组内的标准差。



