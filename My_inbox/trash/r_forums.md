
1.我用brms做了一个多层线性模型，自定义了一个随机效应模型。
2.在利用brms使用MCMC方法执行贝叶斯推断，以估计模型参数的后延分布
3.在尝试进行模型比较的过程中我遇到了困难

我有以下几个问题：

1. 我尤其想要计算出模型的贝叶斯因子，但是，总是求不出来，得到了如下的错误。想请教一下大家是哪里出了问题为什么计算不出贝叶斯因子呢？（最开始的时候我跑bayes因子过程中，会遇到Rsession aborted的麻烦，但后来通过在rstan 论坛上查询，我解决了Rsession aborted的问题。
3. 我浏览论坛中相关内容，发现对贝叶斯模型的模型比较大致有三种标准：loo bf 以及bic. 有评论说loo是最好的标准，我在代码运行进行阶段LOO的标准也一切运行正常，并得到了这样的结果。我的担忧是bf都无法计算，我的这个loo靠谱么？好用么？
4. 我还遇到了bic相关的问题。

what i have done?
1. I used brms to make a hierarchical linear model and customized a random effects model.
2. I used MCMC method to perform Bayesian inference by brms to estimate the parameter.
3. I met some difficulties while trying to do model comparisons

what is my quesition?
1. In particular, I want to calculate the Bayes factor of the two models, but I can't make it by BayesFactor and get the following error.I would like to ask you what went wrong, why can't I calculate the Bayes factor? (At the beginning, when I ran the bayes factor, I would encounter the problem of Rsession aborted, but later I solved the problem of Rsession aborted by querying on the rstan forum.