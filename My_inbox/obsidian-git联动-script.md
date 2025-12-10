---
aliases: 
created: '[[2025-12-10]]'
🤔: 
in: 
up: 
related: 
author:
---
# 🌲 Evergreen Note
```

```



---
# ✍️ Summary
-　


- ## ref
	- 📒：
	- link：
- ## Logs
	- [[2025-12-10]]
- ## todo
	- [ ] 
---
# 📒 Note

核心思路一句话：**让你的 Obsidian Vault 本身就是一个 Git 仓库，然后用 Git 做版本管理 + 同步。**

下面我分「最简单命令行版」和「懒人插件版」说一遍，你可以二选一，也可以混用。

---

## **一、整体思路先搞清楚**

1. 你的 Vault 其实就是一个普通文件夹。
    
2. 把这个文件夹 git init，它就变成 Git 仓库。
    
3. 平时写完东西：
    
    - git add .
        
    - git commit -m "今天的更新"
        
    - 有远端（GitHub / Gitee 等）就再 git push
        
    
4. 换一台电脑：
    
    - git clone 这个仓库
        
    - 在 Obsidian 里「打开已有库」→ 选这个文件夹
        
        就完成同步 + 版本管理了。
        
    

---

## **二、在本地给 Obsidian 库接上 Git（命令行版）**

  

假设你用的是 Mac，Obsidian 库在：~/Documents/ObsidianVault

  

### **1. 把 Vault 变成 Git 仓库**

```
cd ~/Documents/ObsidianVault
git init          # 初始化仓库
git status        # 看看当前状态
```

### **2. 建议先加一个** 

### **.gitignore**

  

在 Vault 根目录新建 .gitignore，内容示例：

```
# 系统文件
.DS_Store
Thumbs.db

# Obsidian 工作区临时状态（可选）
.obsidian/workspace*
.obsidian/workspace.json

# 缓存类文件（有些插件会用）
.obsidian/plugins/*/node_modules
.obsidian/plugins/*/dist
```

> 原则：

- > **配置**（主题、插件设置）一般可以跟着版本控制
    
- > **纯临时文件 / 缓存**、系统文件可以忽略
    

  

### **3. 做第一次提交**

```
git add .
git commit -m "首次提交：导入 Obsidian 笔记"
```

以后日常更新：

```
git add .
git commit -m "YYYY-MM-DD 笔记更新"
```

你可以写个 alias 或者脚本简化，比如：

```
git add . && git commit -m "auto: update notes"
```

---

## **三、连接远端仓库（GitHub / Gitee / GitLab 都可以）**

  

这里以 GitHub 为例（国内也可以用 Gitee，逻辑一样）。

  

### **1. 在 GitHub 创建一个空仓库**

- 新建 repo，比如：obsidian-notes
    
- 不要勾选「README」「.gitignore」「LICENSE」（免得和本地冲突）
    

  

记下仓库地址，例如：

```
git@github.com:yourname/obsidian-notes.git
# 或
https://github.com/yourname/obsidian-notes.git
```

### **2. 绑定远端并推送**

  

在 Obsidian Vault 目录下：

```
git remote add origin git@github.com:yourname/obsidian-notes.git
git branch -M main
git push -u origin main
```

之后日常更新就简单了：

```
git pull           # 先拉
git add .
git commit -m "update"
git push
```

---

## **四、多设备同步 Obsidian + Git**

  

### **1. 在第二台设备上**

```
cd ~/Documents
git clone git@github.com:yourname/obsidian-notes.git
```

然后在 Obsidian 里：

- 选择「打开已有库」
    
- 选 ~/Documents/obsidian-notes 这个文件夹
    

  

之后多设备流程就是经典的 Git 流程：

1. 每次写之前：git pull
    
2. 写完后：git add . && git commit -m "..." && git push
    

  

> 小建议：

- > 同一个文件不要在两台设备**同时改**然后各自 push，不然容易冲突
    
- > 如果实在冲突了，Obsidian 只是普通 Markdown 文件，用编辑器 / diff 工具手动合并即可
    

---

## **五、懒人方案：用 Obsidian Git 插件自动化**

  

如果你不想每次都在终端敲命令，可以装 **Obsidian Git 插件**：

1. 打开 Obsidian → 设置 → 社区插件
    
2. 关闭「安全模式」
    
3. 在社区插件搜索框输入 Obsidian Git
    
4. 安装并启用
    

  

插件主要功能：

- 定时自动 commit + push
    
- 打开 Vault 时自动 pull
    
- 一键按钮执行 pull/push（侧边栏会有图标）
    

  

### **常见设置（大致方向）**

  

在「设置 → Obsidian Git」里：

- **Vault backup interval**：比如设成 10 分钟，自动提交一次
    
- **Auto pull on startup**：打开 Vault 时自动 git pull
    
- 提交信息模板：例如 "auto: {{date}} 更新"
    

  

前提依旧是：**这个 Vault 已经是一个 Git 仓库，并且配置好了远端**

（也就是前面那套 git init + remote add 的步骤）

---

## **六、一个可以照抄的日常工作流示例**

  

给你一个相对「无脑」但还算稳妥的习惯模板：

  

### **单设备用法**

1. 打开 Obsidian 写东西
    
2. 写到一个阶段、或者准备下课 / 下班：
    

```
git add .
git commit -m "2025-12-10 自我管理论文笔记更新"
git push
```

  

  

### **多设备用法（比如 Mac + Windows）**

- **任何一台设备上开始写之前**：
    

```
git pull
```

-   
    
- 写完之后：
    

```
git add .
git commit -m "2025-12-10 AI-能源联动文献整理"
git push
```

  

  

这样做的好处：

- Obsidian 里的所有改动都有版本历史（想回滚某天的笔记很容易）
    
- 多设备间靠 Git 同步，不依赖 Obsidian 官方同步服务
    
- 以后你要做「研究笔记版本管理」「毕业论文草稿演化」都特别香
    

---

## **七、一些实战小建议（结合你这种重度用户的情况）**

1. **研究型库强烈建议用 Git 管理**
    
    - 比如：AI-能源-资本市场研究 单独一个 Vault / 子目录
        
    - 每次做完一轮实证 / 改一轮文献综述，就做一次 commit
        
        以后写「研究日志」可以直接对着 commit 记录回顾。
        
    
2. **教学 / 课堂备课库也可以用 Git**
    
    - 例如 K12_Math_Teaching 仓库
        
    - 不同学期的教案演化，版本历史一目了然。
        
    
3. **可以用分支做「大改版」**
    
    - 比如准备重构整套笔记结构 → 新建分支 refactor-notes
        
    - 改爽了再 merge 回 main，改崩了就直接丢掉分支。
        
    

---

如果你愿意告诉我：

- 你现在 Obsidian 的库大概有几个？
    
- 是「研究型 + 教学型」分开，还是 all in one？
    

  

我可以直接给你设计一个「适合你现在工作流」的 Git+Obsidian 结构方案（仓库怎么分、目录怎么建、commit 命名怎么定成模板那种）。


