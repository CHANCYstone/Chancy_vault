1. 写一篇论文，用moc可以迅速打出来一篇初稿。搞出来初稿之后，后面的就不太需要用ob了
2. 












太好了，这正是 MOC（Maps of Content）能大放异彩的地方。下面给你一篇**“边写边练”的系统化实操文章**：从概念—设计—落地—进阶到维护评估，一路给到可直接复制的模板与练习清单。你可以照顺序完成，每一步都会在你的 Vault 里留下可见的进展。



---

# **一、MOC 是什么、解决什么问题（5 分钟）**

  

**定义（实践口径）**：MOC 是一张“**主题导航页**”，把同一主题下的关键子主题、代表性素材、常用工作流**显式地**链接在一起，既像索引又像看板，是**人工策展**而非自动目录。它的价值在于：让“链接网络”的**入口**稳定、**语义结构**清晰，并能随你的理解演化（Milo 对此有系统论述）。

  

**与文件夹/标签/全局图谱的关系**

- **文件夹**：存放；**MOC**：讲述关系、呈现结构（更“语义”）。
    
- **标签**：打点；**MOC**：连线 + 编排（把点串成路）。
    
- **图谱（Graph）**：全局观察；**MOC**：主题层面的**可操作入口**。
    

  

> 练习 A（立刻动手）：新建一张顶层首页 Home MOC，把你最常用的 3–5 个领域（如“六年级数学”、“学习科学”、“AI×能源研究”）各自做成子 MOC 的链接。这就是你的“中心—子中心”第一跳。

---

# **二、信息架构：从“主题—子主题—原子笔记”到多层 MOC（15 分钟）**

  

**五级分解（可自顶向下或自底向上）**

1. **Home MOC**：整个 Vault 的总导航。
    
2. **领域 MOC**（如：K12 数学 / 学习科学 / 研究方法）：主题清单 + 常用操作。
    
3. **专题 MOC**（如：分数应用题、Polya 方法、TVP-VAR）：更细颗粒的知识网与案例集。
    
4. **原子笔记**：一条概念/一段证据/一张图。
    
5. **素材/文献卡**：书摘、论文条目、课堂片段。
    

  

MOC 强调“**人工挑选 + 语义编排**”，不是把所有出链都塞上去（那会退化成目录）。LYT 社区的实践将 MOC视为**不断演化的主题地图**，而不是一次性完工的纲要。

  

> 练习 B：在 Home MOC 下，新建三个子 MOC：

> K12·数学 · MOC、学习科学 · MOC、AI×能源 · MOC。先只列“你已经写过或准备写的 8–12 个子主题链接”，不要追求完美。

---

# **三、写作模板：把“策展 + 导航 + 工作流”装进一张 MOC（10 分钟）**

  

**MOC 模板（可复制）**

把它存为你的 Templater/模板笔记（或直接手建）：

````
---
type: moc
topic: <% tp.file.title %>
owner: gouge
review: weekly
updated: <% tp.date.now("YYYY-MM-DD") %>
---

# <% tp.file.title %>
> 该 MOC 服务的目标：用 1–2 句话写清楚（面向谁？解决什么？形成什么产出？）

## 1. 主题分区（人工策展）
- 核心概念｜[[概念A]] · [[概念B]] · [[概念C]]
- 典型任务｜[[任务模板A]] · [[任务模板B]]
- 代表案例｜[[案例1]] · [[案例2]]（简注：为什么重要？）
- 关键文献｜[[文献选读]]（挑 5–10 篇“入口级”）

## 2. 快速入口（最近在做）
- [[当周任务看板]] · [[复盘/周记]] · [[课堂设计草稿]]

## 3. 待补洞
- [ ] 子主题 X 需要补充示例
- [ ] 文献 Y 需要反驳/比较
- [ ] 课程 Z 需要插入形成性评价

## 4. 自动聚合区（Dataview）
```dataview
TABLE WITHOUT ID file.link AS 笔记, file.mtime AS 最近修改
FROM "你的内容文件夹路径"
WHERE contains(file.name, "关键词A") OR contains(file.name, "关键词B")
SORT file.mtime DESC
LIMIT 20
````

````
> 设计要点：1）**上半页**纯手工策展（最有价值）；2）**下半页**用 Dataview 做“最近更新/素材池”，随写随涨；3）每个 MOC 写明“**目标与下一步**”。

若你更喜欢“按链接关系自动抓取”，可以在**专门的 MOC**里用社区理念（“MOC 是 hub 的人工策展”）+ 插件自动化混合：例如 Dataview 从指定**标签/路径**汇总，辅以图谱/Backlinks 检索。 [oai_citation:4‡blacksmithgu.github.io](https://blacksmithgu.github.io/obsidian-dataview/reference/functions/?utm_source=chatgpt.com)

---

# 四、边写边练的“三回路”工作流（30 分钟就能跑通）

**回路 1：捕捉—生长（日）**  
- 今日输入走 **Daily Note**：课堂灵感、文献摘录、问题清单。  
- 每条记录尽量落成**原子笔记**（1 概念/1 证据/1 图），并**立刻放 1–2 个内链**到相关 MOC。  
- 在 MOC 的“自动聚合区”中，通过关键词或标签把“最近素材”拉上来复核。  
（用 Backlinks 辅助核对是否已被 MOC 锚住。） [oai_citation:5‡Obsidian Help](https://help.obsidian.md/plugins/backlinks?utm_source=chatgpt.com)

**回路 2：编排—重构（周）**  
- 打开每个核心 MOC，检查“**主题分区**”是否仍合理；把“自动聚合区”里出现的新材料**上移**到策展区或新开子 MOC。  
- 用 Graph 的**分组/着色**检查是否有“孤岛主题”；对孤岛新建入口段落或归并到现有分区。 [oai_citation:6‡Obsidian Help](https://help.obsidian.md/plugins/graph?utm_source=chatgpt.com)

**回路 3：产出—回灌（月）**  
- 从某个成熟 MOC 出**微型产出**：一页讲义/一篇博文/一节公开课。  
- 把产出反向链接回 MOC 的“代表案例/资源”，形成“**产出—知识网**”的闭环。

> 练习 C：挑一个正在进行的主题（比如“分数应用题”），把过去 7 天的 Daily Note 中相关片段，转成 5–8 条原子笔记，加入 `K12·数学 · MOC` 的“代表案例/典型任务”分区。随后用 Graph 给这些新笔记上色，检查互联是否到位。 [oai_citation:7‡Obsidian Help](https://help.obsidian.md/plugins/graph?utm_source=chatgpt.com)

---

# 五、Dataview 小配方：让 MOC“动起来”（可直接贴用）

**1）列出“指向本页的所有子链”（半自动目录）**  
> 手工策展仍是主角；但你可以用标签/命名规范给 MOC 提供补充自动视图。

```dataview
TABLE WITHOUT ID file.link AS 子页, file.mtime AS 最近修改
FROM #moc/k12-math
SORT file.mtime DESC
````

**2）基于“本主题关键词”的最近更新**

```
LIST file.link
FROM "Teaching" OR "Research"
WHERE contains(file.name, "分数") OR contains(file.name, "应用题")
SORT file.mtime DESC
LIMIT 15
```

**3）按“子主题”分组（洞见哪块在生长）**

```
TABLE length(rows) AS 数量, max(rows.file.mtime) AS 最近更新
FROM #k12/math AND -"Archive"
GROUP BY 子主题
SORT length(rows) DESC
```

> 注：子主题 可以是你的 YAML 字段或正文 子主题:: xxx 内联字段。函数与语义参考 Dataview 文档。

---

# **六、进阶：用“Typed Links”表达结构（Breadcrumbs 插件）**

  

当你需要**显式的“上下/同级/部件”关系**时，Breadcrumbs 提供**类型化链接**与多视图（矩阵、阶梯、图等），能把**层次关系**叠加在普通内链之上，非常适合在**大专题 MOC**里梳理“纲—目—叶”。

  

**最小可行示例（YAML 里声明上下级）**：

```
---
up: [[K12·数学 · MOC]]
same: [[学习科学 · MOC]]
down:
  - [[分数·模型与意义]]
  - [[分数应用题·类型谱]]
---
```

然后在 K12·数学 · MOC 中，用 Breadcrumbs 的面板/视图快速巡航、校验**父—子链**是否覆盖关键节点。更多快速入门可见 Obsidian Hub 的指南。

---

# **七、与其他体系的对比与组合**

- **PARA**：偏“项目/领域/资源/归档”的**工作流分拣**；常与 MOC 互补（PARA 放，MOC 讲）。
    
- **Johnny Decimal**：用编号建稳定层级，适合文档治理；但在**知识生长/迭代**上略显刚性，因此很多 Obsidian 用户在**动态主题**上更倾向 MOC，再把 JD 用于“制度性资料”。
    

---

# **八、质量评估清单（每月 10 分钟）**

- 该 MOC 的**目标陈述**仍清晰？是否服务当前产出？
    
- “主题分区”的**命名粒度**是否均匀？是否有“多余层级/冗长标题”？
    
- 最新 30 天新增的原子笔记中，**>70%** 已被某个 MOC 吸纳？（Backlinks 检查）
    
- 自动聚合区的**信号噪声比**：是否需要收紧 FROM/WHERE 或改用标签前缀？
    
- 是否有**产出**从该 MOC 诞生，并被回链沉淀？
    

---

# **九、为你的场景定制的 3 张起步 MOC（可直接粘贴）**

  

**1）K12·数学 · MOC（示例）**

````
# K12·数学 · MOC
## 核心概念
- [[分数的多重表征]] · [[比例与比率]] · [[几何测量的单位意识]]
## 课堂任务
- [[分数应用题·类型谱]] · [[错题·诊断与再设计]]
## 代表案例
- [[六年级·分数·单元设计]] · [[课堂观察·同伴互评框架]]
## 文献入口
- [[Polya·怎样解题·读书卡]] · [[TIMSS/PISA 框架卡]]
## 自动聚合
```dataview
LIST file.link
FROM "Teaching" AND #k12/math
SORT file.mtime DESC
LIMIT 10
````

````
**2）学习科学 · MOC（示例）**
```markdown
# 学习科学 · MOC
- 记忆与提取练习｜[[检索练习设计]] · [[间隔复习与交错练习]]
- 元认知与动机｜[[自我解释]] · [[成长型思维]]
- 评估与反馈｜[[形成性评价技巧]] · [[同伴互评量表]]
````

**3）AI×能源 · MOC（示例）**

```
# AI×能源 · MOC
- 主题走廊｜[[数据中心用电与电网]] · [[储能与调度优化]] · [[AI 板块×能源板块联动]]
- 方法与数据｜[[TVP-VAR 笔记]] · [[连接性网络指标卡]] · [[数据源清单]]
- 文献起点｜[[综述·AI 与电力系统]] · [[市场联动·代表论文]]
```

---

# **十、常见坑与避免策略**

- **把 MOC 写成“自动汇总页”**：失去“策展与结构”的价值——请把**上半页留给人工编排**。
    
- **过度层级化**：层级>3 就要警惕；能用“多 MOC 并列 + 交叉链接”就不要深挖层级。
    
- **早期过度模板化**：先让主题长肉；模板只提供**最小骨架**。
    
- **把 MOC 当“最终产品”**：它应随学习与项目进展**持续演化**。
    

---

## **结语（下一步就做这两件事）**

1. 建立 Home MOC 与三个子 MOC（K12·数学 / 学习科学 / AI×能源）。
    
2. 给每个子 MOC 填上**3 个子主题 + 1 个代表案例 + 1 个自动聚合区**。
    
    做完这一步，你就拥有了一个可工作的**主题导航系统**；随后按“三回路”让它持续产出。
    

---

## **参考文献（APA）**

- Milo, N. (n.d.). _MOCs overview_. Linking Your Thinking. （对 MOC 的核心定义与特性做了系统阐述。）
    
- Obsidian Help. (n.d.). _Backlinks_；_Graph view_.（MOC 相关核心插件的官方说明。）
    
- Blacksmithgu. (n.d.). _Dataview: Functions reference_.（Dataview 表达式/函数权威文档。）
    
- SkepticMystic. (n.d.). _Breadcrumbs plugin docs_；_Breadcrumbs (GitHub)_。（类型化链接与层级导航的实现方式。）
    
- Andremonthy, A. (2025, October). _Stop overthinking Obsidian: A beginner’s guide that actually works_. Medium.（提出“Home MOC”作为起点的实操建议。）
    
- Obsidian Hub. (n.d.). _Breadcrumbs quickstart guide_.（社区整合的快速上手指南。）
    

---

如果你愿意，我可以**直接用你的实际文件夹/标签**改造上面的 Dataview 片段，并把三张 MOC 做成一页“教学仪表盘”（最近更新、案例库、任务看板、周复盘入口），你只需要告诉我：①教学与研究文件夹的相对路径；②你打算用的 3–5 个关键词或标签。