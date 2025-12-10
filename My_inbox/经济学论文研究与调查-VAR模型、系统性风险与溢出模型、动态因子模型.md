
# 【模型更新-汇总】复现各类VAR模型、系统性风险与溢出模型、动态因子模型等等

原创 lzygoahead FinNote

 _2025年06月30日 18:11_

0. 前言

我擅长各类VAR模型与风险溢出模型建模，并利用这些模型在《统计研究》、《International Review of Economics & Finance》和《Applied Economics》等期刊发表了论文。如果想获取代码资料或者详细学习VAR系列、风险溢出网络和系统性风险测量措施，且接这方面的论文指导，可以加我微信号：lzygoahead，我将提供从方法原理到应用的讲解，同时提供代码指导，助力完成完整的分析。详细模型如下：

![图片](https://mmbiz.qpic.cn/sz_mmbiz_png/2QZPPlpHBL9Js9LQKeticvO9ag62wx5NfWrP4Qm07kABRdKT7nCic8RTu72HPYhpxOUp1sX7iauJ02ZPFgaqeKmhQ/640?wx_fmt=png&from=appmsg&wxfrom=5&wx_lazy=1&tp=wxpic)

# 1. 各类VAR模型

### 1.1 TVP-SV-VAR模型

带有随机波动率的时变参数向量自回归模型，可以分析不同变量之间的动态时变脉冲响应。

> 复现链接请点击下方
> 
> I am 李智勇，公众号：FinNote[复现顶刊《金融研究》- 金融周期如何影响房地产价格？](https://mp.weixin.qq.com/s/b8qc0GvUrXS5xRdY17nM2g)

### 1.2 TVP-SV-FAVAR模型

带有随机波动率的时变参数因子增强向量自回归模型，可以分析成千上百个变量的时变脉冲响应，有效解决高维问题。

> 复现链接请点击下方
> 
> I am 李智勇，公众号：FinNote[【顶刊利器】TVP-SV-FAVAR模型的应用与实现](https://mp.weixin.qq.com/s/JmOEjd8wI2LVqVrF7YlISw)

### 1.3 MS-VAR、TVAR、STVAR模型

除此之外，本人还可以实现马尔科夫区制转换向量自回归模型（MS-VAR）、门限向量自回归（TVAR）和平滑转换向量自回归（STVAR）等非线性VAR模型。

# 2. 风险溢出网络模型

### 2.1 DY模型与BK模型

一种用于衡量不同市场或变量间风险传递强度的工具。同时考虑频域视角下分析短中长期的风险传染效应。

> 复现链接请点击下方
> 
> I am 李智勇，公众号：FinNote[频域视角下的风险溢出网络：从DY溢出到BK溢出](https://mp.weixin.qq.com/s/q2hbJsgWs_1TyY61x7iHxg)

### 2.2 TVP-VAR-DY与TVP-VAR-BK

允许模型参数随时间变化，更好地捕捉经济变量在不同时期的关系变化，这避免了样本损失，使得模型结果更稳定和可靠。

> 复现链接请点击下方
> 
> I am 李智勇，公众号：FinNote[复现顶刊《经济学（季刊）》- 非滚动窗口依赖的时变DY溢出模型](https://mp.weixin.qq.com/s/trJT8hjTDB023RKGoC0_ZQ)

### 2.3 QVAR-DY与QVAR-BK

分位数溢出模型，能够更全面地捕捉变量间的非线性关系，尤其是在面临异常值和偏态分布时具有优势，有助于我们分析极端正面或负面冲击条件下的尾部风险溢出情况。

> 复现链接请点击下方
> 
> I am 李智勇，公众号：FinNote[尾部风险跨市场传染的复杂网络建模：QVAR-DY分位数溢出方法](https://mp.weixin.qq.com/s/UuZhqw_wueCXutJlg7_g5w)

### 2.4 边际溢出模型

杨子晖老师等人在《Management Science》、《中国社会科学》、《金融研究》和《管理世界》等中外顶刊中提出了边际净溢出的测度，该方法能研究在重要事件冲击下风险溢出关系的边际变化。

> 复现链接请点击下方
> 
> I am 李智勇，公众号：FinNote[如同顶刊“收割机”的方法：重大外部冲击下边际风险溢出矩阵与复杂网络构建](https://mp.weixin.qq.com/s/ub8M4OFuOEwvZg9uWM-sGg)

### 2.5 非对称溢出模型

乐观预期与悲观预期的传导研究，杨子晖老师等人在中文顶刊《管理世界》2024年第11期的文章中，建立了市场乐观预期和悲观预期的传导网络，刻画了市场预期的传导机制。

> 复现链接请点击下方
> 
> I am 李智勇，公众号：FinNote[复现顶刊《管理世界》丨 测度乐观与悲观预期传导 多空资金的博弈](https://mp.weixin.qq.com/s/GRDdkxfi9iztpWY9_bbGtg)

### 2.6 分位数溢出与非对称溢出的结合

这种混合方法能分析在不同冲击强度下悲观预期和乐观预期的传导机制，考虑了极端情况。我用该方法发表了论文在《Applied Economics》。

> 复现链接请点击下方
> 
> lzygoahead，公众号：FinNote[新思路！我“创新”了风险溢出模型，发表论文在SSCI二区期刊](https://mp.weixin.qq.com/s/JS8Lgn3SoMe-r6r6kQq8NA)

### 2.7 高维风险溢出网络模型

采用lasso、ridge和弹性网络技术去估计VAR的参数以及构建溢出指数，能有效解决“维度诅咒”的问题。相较于传统VAR-DY模型，显著提升高维数据下的估计效率和稳定性，同时保留动态溢出效应分析能力。

> 复现链接请点击下方
> 
> I am 李智勇，公众号：FinNote[代码实现：全球股市系统性风险如何传染？——基于高维技术LASSO-VAR-DY模型](https://mp.weixin.qq.com/s/pdT6k8IHZZUgA7FurSVEnQ)

# 3. 系统性风险测度

### 3.1 微观机构的系统性风险

ΔCoVaR、MES和SRISK指标：这种方法以金融机构在尾部风险条件下的潜在资产损失衡量系统性金融风险，强调微观金融机构个体对系统性风险的贡献。

> 复现链接请点击下方
> 
> I am 李智勇，公众号：FinNote[顶刊《AER》-通过ΔCoVaR测度系统性风险](https://mp.weixin.qq.com/s/E4cffqR60tgpziraGfK3sg)

### 3.2 金融市场的系统性风险  

CISS指数方法：《金融研究》等顶刊采用的方法，主要采用统计方法对基础指标进行合成，反映金融体系整体风险水平。  

> 复现链接请点击下方
> 
> I am 李智勇，公众号：FinNote[复现顶刊《金融研究》-测算日度高频系统性金融风险](https://mp.weixin.qq.com/s/VocCuWaDef3GAWyLedloxQ)

TVP-FAVAR+MES测度方法：借鉴《中国社会科学》的方法，得到整个金融市场体系的系统性风险值。

> 复现链接请点击下方
> 
> I am 李智勇，公众号：FinNote[复现顶刊《中国社会科学》：通过结合TVP-FAVAR和MES方法测度系统性风险](https://mp.weixin.qq.com/s/0lFjHRElfrj_3d0KZRLY4Q)

TVP-FAVAR测度方法：利用TVP-FAVAR模型提取潜在因子，表征系统性金融风险变量。

> 复现链接请点击下方
> 
> lzygoahead，公众号：FinNote[利用TVP-FAVAR模型测算我国系统性金融风险指数](https://mp.weixin.qq.com/s/NzC4Tb-YDJ6VswcT2DrTiQ)

### 3.3 经济/金融不确定性测度  

基于大数据方法，构建非预期波动性，以此测度不确定性变量。该模型在《经济研究》、《金融研究》等顶刊被多次使用。

> 复现链接请点击下方
> 
> lzygoahead，公众号：FinNote[复现顶刊《金融研究》-基于大数据方法测量中国金融不确定性](https://mp.weixin.qq.com/s/6Z5oh1Vz_iul6IdeDIq6hw)

# 4. 因子模型与经济韧性测度

### 4.1 宏观经济韧性测度

经济韧性反映的是经济系统内部对外部冲击的抵御能力。复现《中国社会科学》上发表的论文《中国宏观经济韧性测度——基于系统性风险的视角》。该方法也在《管理世界》上发表文章《预期引导、经济韧性与宏观经济治理》。

> 复现链接请点击下方
> 
> I am 李智勇，公众号：FinNote[复现顶刊《中国社会科学》-如何度量中国宏观经济韧性](https://mp.weixin.qq.com/s/u_zkgkavK5I_uPWwus9LXw)

### 4.2 马尔科夫区制转换混频动态因子模型

实现隋建利等人在2024年第3期《管理世界》上发表的论文《中国经济韧性的时空敛散与异质分化特征——基于马尔科夫区制转移混频动态因子模型的识别》。该方法能测量我国经济韧性，并构建经济收缩/扩张指数。

> 复现链接请点击下方
> 
> lzygoahead，公众号：FinNote[复现顶刊《管理世界》-利用马尔科夫区制转移混频动态因子模型测算经济韧性](https://mp.weixin.qq.com/s/ZL6_UeuUenJr5cxDcF6KwQ)

### 4.3 可纳入高频数据的混频动态因子模型

混频动态因子模型，可包含季度、月度和周度的数据集，构建一种可以反映宏观经济冷暖的同步指标，能够起到即时预测作用的经济形势指数。

> 复现链接请点击下方
> 
> lzygoahead，公众号：FinNote[实现混频动态因子模型：即时追踪我国周度经济形势指数](https://mp.weixin.qq.com/s/LYjMAdKT_LIAl_2W0FUZAA)
