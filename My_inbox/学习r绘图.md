[Skip to content](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#start-of-content)



一般来说让gpt 生成一个模板

然后剩下的自己打磨才对，不能完全不会，

如果完全不会，每次都考gpt生成的代码，每次都是全新的代码，无法做到控制。

从理解第一段代码开始。





### 1.控制坐标轴的刻度
```
x_breaks_yearly <- seq(
  from = floor_date(min(returns_long$date, na.rm = TRUE), "year"),
  to   = ceiling_date(max(returns_long$date, na.rm = TRUE), "year"),
  by   = "1 year"
)
```

### 2.控制主题

```
# —— 自定义“顶刊极简”主题 —— 
theme_top <- function(base_family = "cn", base_size = 11){
  theme_minimal(base_family = base_family, base_size = base_size) %+replace%
    theme(
      # 仅保留 y 主网格；去掉 x 网格、所有次网格
      panel.grid.major.x = element_blank(),
      panel.grid.minor.x = element_blank(),
      panel.grid.minor.y = element_blank(),
      panel.grid.major.y = element_line(colour = "grey85", linewidth = 0.4),
      # 轴线与刻度
      axis.line         = element_line(colour = "grey30", linewidth = 0.4),
      axis.ticks        = element_blank(),
      axis.title.x      = element_text(angle = 60, hjust = 1, vjust = 1, margin = margin(t = 8)),
      axis.title.y      = element_text(margin = margin(r = 6)),
      axis.text.x       = element_text(size = base_size),
      axis.text.y       = element_text(size = base_size),
      # 分面条（放左侧），浅灰底更克制
      strip.background  = element_rect(fill = "grey95", colour = NA),
      strip.text        = element_text(face = "bold", size = base_size),
      strip.placement   = "outside",
      # 版心留白
      panel.spacing     = unit(10, "pt"),
      plot.margin       = margin(6, 10, 6, 6),
      # 绝对无标题/副标题/图例
      plot.title        = element_blank(),
      plot.subtitle     = element_blank(),
      plot.caption      = element_blank(),
      legend.position   = "none"
    )
}

```

- **网格**：panel.grid.*（主/次、x/y），element_blank() 关闭。
    
- **轴线与刻度**：axis.line.x / axis.line.y；axis.ticks 与 axis.ticks.length。
    
- **文字**：axis.text.* / axis.title.* / strip.text / legend.text / legend.title，用 element_text() 改字体、大小、加粗、外边距。
    
- **背景**：panel.background / plot.background / strip.background / legend.background。
    
- **间距**：panel.spacing（分面之间）、plot.margin（整图外边距）。
    
- **图例**：legend.position（“none”/“right”/…）、legend.justification、legend.box、legend.key。
    
- **分面条带**：strip.placement="inside|outside"、strip.text；**条带位置上下左右**在 facet_wrap(..., strip.position="bottom") 里定。
    
- **全局生效**：theme_set(theme_top(...))；恢复默认：theme_set(theme_grey())。
    

---




哪里有问题得知道去哪里进行修改
### 3 主图拼装
```
p <- ggplot(returns_long, aes(x = date, y = Return_Pct)) +
  geom_line(color = "black", linewidth = 0.35, lineend = "round") +
  geom_hline(yintercept = 0, colour = "grey30", linewidth = 0.45) +
```



```
  facet_wrap(
    ~ Index, ncol = 3, scales = "fixed",
    labeller = labeller(Index = index_labels),
    strip.position = "bottom"
  ) +
```

- facet_wrap：按 Index 分面。ncol = 3 → 每行 3 张。
    
- scales = "fixed"：所有面板**共享同一 y 轴范围**（可比性强）。
    
- labeller = labeller(Index = index_labels)：把代码“RS/RW/…”映射成中文标签。
    
- strip.position = "bottom"：**分面标题移到下面**（你要的风格）。

这个玩意就比较搞了


```
  scale_x_date(
    breaks = x_breaks_yearly, date_labels = "%Y",
    expand = expansion(mult = c(0.01, 0.02))
  ) +
  scale_y_continuous(
    name   = "日对数收益",
    labels = scales::label_number(accuracy = 0.1, suffix = "%"),
    breaks = scales::pretty_breaks(n = 5)
  ) +
  labs(x = "时间")

```

对于 x轴和y轴的控制






```

# —— 年度刻度（整年对齐）——
x_breaks_yearly <- seq(
  from = floor_date(min(returns_long$date, na.rm = TRUE), "year"),
  to   = ceiling_date(max(returns_long$date, na.rm = TRUE), "year"),
  by   = "1 year"
)

# —— 自定义“顶刊极简”主题 —— 
theme_top <- function(base_family = "cn", base_size = 11){
  theme_minimal(base_family = base_family, base_size = base_size) %+replace%
    theme(
      # 仅保留 y 主网格；去掉 x 网格、所有次网格
      panel.grid.major.x = element_blank(),
      panel.grid.minor.x = element_blank(),
      panel.grid.minor.y = element_blank(),
      panel.grid.major.y = element_line(colour = "grey85", linewidth = 0.4),
      # 轴线与刻度
      axis.line         = element_line(colour = "grey30", linewidth = 0.4),
      axis.ticks        = element_blank(),
      axis.title.x      = element_text(margin = margin(t = 6)),
      axis.title.y      = element_text(margin = margin(r = 6)),
      axis.text.x       = element_text(size = base_size),
      axis.text.y       = element_text(size = base_size),
      # 分面条（放左侧），浅灰底更克制
      strip.background  = element_rect(fill = "grey95", colour = NA),
      strip.text        = element_text(face = "bold", size = base_size),
      strip.placement   = "outside",
      # 版心留白
      panel.spacing     = unit(10, "pt"),
      plot.margin       = margin(6, 10, 6, 6),
      # 绝对无标题/副标题/图例
      plot.title        = element_blank(),
      plot.subtitle     = element_blank(),
      plot.caption      = element_blank(),
      legend.position   = "none"
    )
}

# —— 分面：名称在子图下面 —— 
p <- ggplot(returns_long, aes(x = date, y = Return_Pct)) +
  geom_line(color = "black", linewidth = 0.35, lineend = "round") +
  geom_hline(yintercept = 0, colour = "grey30", linewidth = 0.45) +
  facet_wrap(
    ~ Index, ncol = 3, scales = "fixed",
    labeller = labeller(Index = index_labels),
    strip.position = "bottom"          # <— 名称放在子图下面
  ) +
  scale_x_date(
    breaks = x_breaks_yearly, date_labels = "%Y",
    expand = expansion(mult = c(0.01, 0.02))
  ) +
  scale_y_continuous(
    name   = "日对数收益",
    labels = scales::label_number(accuracy = 0.1, suffix = "%"),
    breaks = scales::pretty_breaks(n = 5)
  ) +
  labs(x = "时间") +
  theme_minimal(base_family = "cn", base_size = 11) +
  theme(
    # —— 不要任何灰底（含分面条带） ——
    strip.background  = element_blank(),   # <— 去灰色背景
    panel.background  = element_blank(),   # （theme_minimal 本就无底，这里再明确）
    # —— 分面名称样式（在下方） ——
    strip.text        = element_text(face = "bold", size = 11, margin = margin(t = 4)),
    # —— 网格克制：只保留 y 主网格 ——
    panel.grid.major.x = element_blank(),
    panel.grid.minor.x = element_blank(),
    panel.grid.minor.y = element_blank(),
    panel.grid.major.y = element_line(colour = "grey85", linewidth = 0.4),
    # —— 轴与间距 ——
    axis.title.x      = element_text(margin = margin(t = 6)),
    axis.title.y      = element_text(margin = margin(r = 6)),
    axis.text.x       = element_text(size = 11),
    axis.text.y       = element_text(size = 11),
    legend.position   = "none",
    plot.title        = element_blank(),
    plot.subtitle     = element_blank(),
    plot.caption      = element_blank(),
    panel.spacing     = unit(10, "pt")
  )


p <- p + scale_x_date(
  breaks = seq(lubridate::floor_date(min(returns_long$date, na.rm = TRUE), "year"),
               lubridate::ceiling_date(max(returns_long$date, na.rm = TRUE), "year"),
               by = "1 year"),
  date_labels = "%Y",
  expand = expansion(mult = c(0.01, 0.02))
) +
  theme(
    axis.text.x = element_text(angle = 60, hjust = 1, vjust = 1, margin = margin(t = 8))
  )

print(p)

```








## Navigation Menu

[](https://github.com/)

[CerrenRichards](https://github.com/CerrenRichards)[ggplot2-for-publications](https://github.com/CerrenRichards/ggplot2-for-publications)

Type / to search

[](https://github.com/copilot)

[](https://github.com/issues)[](https://github.com/pulls)

[](https://github.com/notifications)

- [Code](https://github.com/CerrenRichards/ggplot2-for-publications)
- [Issues1](https://github.com/CerrenRichards/ggplot2-for-publications/issues)
- [Pull requests](https://github.com/CerrenRichards/ggplot2-for-publications/pulls)
- [Actions](https://github.com/CerrenRichards/ggplot2-for-publications/actions)
- [Projects](https://github.com/CerrenRichards/ggplot2-for-publications/projects)
- [Security](https://github.com/CerrenRichards/ggplot2-for-publications/security)
- [Insights](https://github.com/CerrenRichards/ggplot2-for-publications/pulse)

![Owner avatar](https://avatars.githubusercontent.com/u/39834789?s=48&v=4)**[ggplot2-for-publications](https://github.com/CerrenRichards/ggplot2-for-publications)**Public

- [](https://github.com/CerrenRichards/ggplot2-for-publications/fork)
    

# CerrenRichards/ggplot2-for-publications

t

|Name|||
|---|---|---|
|[![CerrenRichards](https://avatars.githubusercontent.com/u/39834789?v=4&size=40)](https://github.com/CerrenRichards)[CerrenRichards](https://github.com/CerrenRichards/ggplot2-for-publications/commits?author=CerrenRichards)<br><br>[Update README.md](https://github.com/CerrenRichards/ggplot2-for-publications/commit/01b70df60c72f3e0eeda687d0368a0af393eef75)<br><br>[01b70df](https://github.com/CerrenRichards/ggplot2-for-publications/commit/01b70df60c72f3e0eeda687d0368a0af393eef75) · 5 years ago|   |   |
|[.gitignore](https://github.com/CerrenRichards/ggplot2-for-publications/blob/master/.gitignore ".gitignore")|[Initial uplosd](https://github.com/CerrenRichards/ggplot2-for-publications/commit/88d0b4f9faecbe9555e95bcffbb3d53e30a4c100 "Initial uplosd")|5 years ago|
|[README.md](https://github.com/CerrenRichards/ggplot2-for-publications/blob/master/README.md "README.md")|[Update README.md](https://github.com/CerrenRichards/ggplot2-for-publications/commit/01b70df60c72f3e0eeda687d0368a0af393eef75 "Update README.md<br>Uploaded all images")|5 years ago|
|[ggplot-tutorial.Rmd](https://github.com/CerrenRichards/ggplot2-for-publications/blob/master/ggplot-tutorial.Rmd "ggplot-tutorial.Rmd")|[Initial uplosd](https://github.com/CerrenRichards/ggplot2-for-publications/commit/88d0b4f9faecbe9555e95bcffbb3d53e30a4c100 "Initial uplosd")|5 years ago|
|[ggplot-tutorial.html](https://github.com/CerrenRichards/ggplot2-for-publications/blob/master/ggplot-tutorial.html "ggplot-tutorial.html")|[Initial uplosd](https://github.com/CerrenRichards/ggplot2-for-publications/commit/88d0b4f9faecbe9555e95bcffbb3d53e30a4c100 "Initial uplosd")|5 years ago|
|[ggplot2-for-publications.Rproj](https://github.com/CerrenRichards/ggplot2-for-publications/blob/master/ggplot2-for-publications.Rproj "ggplot2-for-publications.Rproj")|[Initial uplosd](https://github.com/CerrenRichards/ggplot2-for-publications/commit/88d0b4f9faecbe9555e95bcffbb3d53e30a4c100 "Initial uplosd")|5 years ago|

## Repository files navigation

- [README](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#)

# Making figures ready for publication with `ggplot2`  
使用 `ggplot2` 制作适合发表的图形

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#making-figures-ready-for-publication-with-ggplot2)

This tutorial offers a step-by-step guide for how to create publication-ready figures using `ggplot2` and the data from `palmerpenguins`.  
本教程提供逐步指南，教你如何使用 `ggplot2` 和 `palmerpenguins` 中的数据创建适合发表的图形。

[![image](https://user-images.githubusercontent.com/39834789/86522447-78104680-be38-11ea-8330-3d5fc96ceafc.png)](https://user-images.githubusercontent.com/39834789/86522447-78104680-be38-11ea-8330-3d5fc96ceafc.png)

## Install the package & data  
安装软件包和数据

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#install-the-package--data)

```
# Install the package
remotes::install_github("allisonhorst/palmerpenguins")

# Load the package
library(palmerpenguins)

# Load the data into the Global Environment
data("penguins")
```

## Meet the Penguins  认识企鹅

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#meet-the-penguins)

[![image](https://user-images.githubusercontent.com/39834789/86522450-7f375480-be38-11ea-9437-9fd2a382aa7b.png)](https://user-images.githubusercontent.com/39834789/86522450-7f375480-be38-11ea-9437-9fd2a382aa7b.png)

Artwork by @allison_horst  
插图作者：@allison_horst

## What are culmen length & depth?  
喙长和喙深是什么？

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#what-are-culmen-length--depth)

The culmen is the upper ridge of a bird’s bill. In the simplified penguins data, culmen length and depth are renamed as variables bill_length_mm and bill_depth_mm to be more intuitive. For this penguin data, the culmen (bill) length and depth are measured as shown below:  
喙是鸟嘴的上部隆起。在简化的企鹅数据中，喙长和喙深被重命名为变量 bill_length_mm 和 bill_depth_mm，以更直观。对于这个企鹅数据，喙（嘴）的长度和深度测量如下：

[![image](https://user-images.githubusercontent.com/39834789/86522451-84949f00-be38-11ea-9555-6409579f3b58.png)](https://user-images.githubusercontent.com/39834789/86522451-84949f00-be38-11ea-9555-6409579f3b58.png)

Artwork by @allison_horst  
插图作者：@allison_horst

## The steps for creating a beautiful scatter plot in `ggplot2`  
创建一个漂亮的散点图的步骤 `ggplot2`

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#the-steps-for-creating-a-beautiful-scatter-plot-in-ggplot2)

First we will create a basic scatterplot of `body_mass_g` against `bill_length_mm`.  
首先我们将创建一个 `body_mass_g` 对 `bill_length_mm` 的基本散点图。

```
# Load the package
library(ggplot2)

ggplot(penguins, aes(body_mass_g, bill_length_mm))+ # this is the data
     geom_point() # here we add the points
```

[![Screen Shot 2020-07-04 at 9 09 20 PM](https://user-images.githubusercontent.com/39834789/86522580-cd4d5780-be3a-11ea-9cd7-9748d668cbbd.png)](https://user-images.githubusercontent.com/39834789/86522580-cd4d5780-be3a-11ea-9cd7-9748d668cbbd.png)

### Change the size of points  
改变点的尺寸

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#change-the-size-of-points)

We can manually change the size of our datapoints. The points in the standard plot are quite small, so lets increase the size of the points with `size = 3`.  
我们可以手动改变数据点的尺寸。标准图中的点非常小，所以让我们用 `size = 3` 增加点的大小。

```
ggplot(penguins, aes(body_mass_g, bill_length_mm))+ 
     geom_point(size = 3) 
```

[![Screen Shot 2020-07-04 at 9 11 04 PM](https://user-images.githubusercontent.com/39834789/86522590-e5bd7200-be3a-11ea-822e-c40d3e55dcdc.png)](https://user-images.githubusercontent.com/39834789/86522590-e5bd7200-be3a-11ea-822e-c40d3e55dcdc.png)

### Change the shape of points  
改变点的形状

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#change-the-shape-of-points)

In `ggplot2`, it is possible to change the shape of the points. Here is a quick reference guide:  
在 `ggplot2` 中，可以改变点的形状。这里是一个快速参考指南：

[![shapes](https://user-images.githubusercontent.com/39834789/86522564-8e1f0680-be3a-11ea-9c7b-8cd1f39eb479.png)](https://user-images.githubusercontent.com/39834789/86522564-8e1f0680-be3a-11ea-9c7b-8cd1f39eb479.png)

The shape of all datapoints can be changed with e.g. `shape = 8`.  
所有数据点的形状都可以通过例如 `shape = 8` 来改变。

```
ggplot(penguins, aes(body_mass_g, bill_length_mm))+
     geom_point(size = 3, shape = 8) 
```

[![Screen Shot 2020-07-04 at 9 15 40 PM](https://user-images.githubusercontent.com/39834789/86522659-e4407980-be3b-11ea-823a-65dabc7f10e2.png)](https://user-images.githubusercontent.com/39834789/86522659-e4407980-be3b-11ea-823a-65dabc7f10e2.png)

Alternatively, we can change the shape of our points based on species with `aes(shape = species)`.  
或者，我们可以根据物种改变点的形状，使用 `aes(shape = species)` 。

```
ggplot(penguins, aes(body_mass_g, bill_length_mm))+ 
     geom_point(aes(shape = species), size = 3) 
```

[![Screen Shot 2020-07-04 at 9 16 06 PM](https://user-images.githubusercontent.com/39834789/86522661-e7d40080-be3b-11ea-9d02-fb763a7c2c00.png)](https://user-images.githubusercontent.com/39834789/86522661-e7d40080-be3b-11ea-9d02-fb763a7c2c00.png)

### Change the opacity of points  
改变点的透明度

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#change-the-opacity-of-points)

You can also change the opacity of the data points using `alpha`. Alpha values are required to be between 0 - 1 where 0 is transparent and 1 is opaque.  
您也可以使用 `alpha` 更改数据点的透明度。Alpha 值必须在 0 到 1 之间，其中 0 表示完全透明，1 表示完全不透明。

```
ggplot(penguins, aes(body_mass_g, bill_length_mm))+ 
     geom_point(aes(shape = species), size = 3, alpha = 0.6) 
```

[![Screen Shot 2020-07-04 at 9 16 40 PM](https://user-images.githubusercontent.com/39834789/86522662-e86c9700-be3b-11ea-8cd7-ff602bbfd4ad.png)](https://user-images.githubusercontent.com/39834789/86522662-e86c9700-be3b-11ea-8cd7-ff602bbfd4ad.png)

### Adding colour  添加颜色

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#adding-colour)

Now lets explore the different species by adding colour with the code `colour = species`.  
现在让我们通过添加颜色来探索不同的物种，使用代码 `colour = species` 。

```
ggplot(penguins, aes(body_mass_g, bill_length_mm))+ 
     geom_point(aes(shape = species, colour = species), size = 3, alpha = 0.6) 
```

[![Screen Shot 2020-07-04 at 9 17 00 PM](https://user-images.githubusercontent.com/39834789/86522663-e86c9700-be3b-11ea-961d-0321b70dc2e7.png)](https://user-images.githubusercontent.com/39834789/86522663-e86c9700-be3b-11ea-961d-0321b70dc2e7.png)

This red-green colour combination is colourblind unfrieldly, so lets change the colour of the points with `scale_colour_manual`. To ensure the shapes match with the names we will also use `scale_shape_manual`.  
这种红绿颜色组合对色盲不友好，所以让我们用 `scale_colour_manual` 更改点的颜色。为了确保形状与名称匹配，我们也将使用 `scale_shape_manual` 。

```
ggplot(penguins, aes(body_mass_g, bill_length_mm))+ 
     geom_point(aes(shape = species, colour = species), size = 3, alpha = 0.6)+ 
  
  scale_colour_manual(values = c("#C15CCB", "#00868B", "#FF6A00"), 
                      labels = c("Chinstrap", "Gentoo", "Adélie"))+
  scale_shape_manual(values = c(17, 15, 16),
                     labels = c("Chinstrap", "Gentoo", "Adélie"))
```

[![Screen Shot 2020-07-04 at 9 17 21 PM](https://user-images.githubusercontent.com/39834789/86522664-e9052d80-be3b-11ea-8124-a6e5e97002ab.png)](https://user-images.githubusercontent.com/39834789/86522664-e9052d80-be3b-11ea-8124-a6e5e97002ab.png)

We won't change the points any more, so let's save the plot as `penguin_plot`, so we can build upon it.  
我们不再改变这些点，所以让我们将图表保存为 `penguin_plot` ，以便在此基础上继续构建。

```
penguin_plot <- ggplot(penguins, aes(body_mass_g, bill_length_mm))+ 
     geom_point(aes(shape = species, colour = species), size = 3, alpha = 0.6)+ 
  
     scale_colour_manual(values = c("#C15CCB", "#00868B", "#FF6A00"), 
                      labels = c("Chinstrap", "Gentoo", "Adélie"))+
     scale_shape_manual(values = c(17, 15, 16),
                     labels = c("Chinstrap", "Gentoo", "Adélie"))
```

### Changing the background  更改背景

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#changing-the-background)

You can change the background of `ggplot2` figures in a variety of ways with:  
您可以通过以下方式更改 `ggplot2` 图形的背景：

- `theme_gray()`
- `theme_bw()`
- `theme_linedraw()`
- `theme_light()`
- `theme_minimal()`
- `theme_classic()`
- `theme_void()`
- `theme_dark()`

[![Screen Shot 2020-07-04 at 9 18 04 PM](https://user-images.githubusercontent.com/39834789/86522665-e99dc400-be3b-11ea-9696-4ad2a5adfb0f.png)](https://user-images.githubusercontent.com/39834789/86522665-e99dc400-be3b-11ea-9696-4ad2a5adfb0f.png)

My personal favourite is `theme_bw` therefore we will continue to make our plot with this theme.  
我最喜欢 `theme_bw` ，因此我们将继续使用这个主题来制作我们的图。

We will further remove the thicker lines in the background with `panel.grid.major = element_blank()`, and the thinner lines with `panel.grid.minor = element_blank()`.  
我们将进一步使用 `panel.grid.major = element_blank()` 去除背景中的粗线，使用 `panel.grid.minor = element_blank()` 去除细线。

```
penguin_plot + 
  theme_bw()+ # set the background theme                                                 
  theme(panel.grid.major = element_blank(), # remove the major lines
        panel.grid.minor = element_blank()) # remove the minor lines
```

[![Screen Shot 2020-07-04 at 9 22 35 PM](https://user-images.githubusercontent.com/39834789/86522769-8ad94a00-be3d-11ea-8f85-e925c5b40cce.png)](https://user-images.githubusercontent.com/39834789/86522769-8ad94a00-be3d-11ea-8f85-e925c5b40cce.png)

### Changing the text size  更改文本大小

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#changing-the-text-size)

There are several ways to change the size of the font, but we can quickly change all font size with `theme_bw(base_size = 20)`.  
有多种方法可以改变字体大小，但我们可以快速通过 `theme_bw(base_size = 20)` 更改所有字体大小。

```
penguin_plot <- penguin_plot + 
  theme_bw(base_size = 15)+                                                 
  theme(panel.grid.major = element_blank(),
        panel.grid.minor = element_blank()) 

penguin_plot
```

[![Screen Shot 2020-07-04 at 9 23 00 PM](https://user-images.githubusercontent.com/39834789/86522979-5fa42a00-be40-11ea-9271-6a1b831736e8.png)](https://user-images.githubusercontent.com/39834789/86522979-5fa42a00-be40-11ea-9271-6a1b831736e8.png)

### Renaming the axes and legend  
重命名坐标轴和图例

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#renaming-the-axes-and-legend)

You can rename the axes and legend using `labs`.  
你可以使用 `labs` 重命名坐标轴和图例。

```
penguin_plot <- penguin_plot + 
  labs(x = "Body Mass (g)", y = "Bill Length (mm)", colour = "Species", shape = "Species")

penguin_plot
```

[![Screen Shot 2020-07-04 at 9 23 16 PM](https://user-images.githubusercontent.com/39834789/86522980-629f1a80-be40-11ea-963c-c74015f4e1f3.png)](https://user-images.githubusercontent.com/39834789/86522980-629f1a80-be40-11ea-963c-c74015f4e1f3.png)

### Change axes position  更改坐标轴位置

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#change-axes-position)

In the standard plots, the axes titles are really close to the plot. We will increase their distance with `vjust`:  
在标准图中，坐标轴标题与图形非常接近。我们将通过 `vjust` 增加它们的距离：

```
penguin_plot <- penguin_plot + 
    theme(axis.title.y = element_text(vjust = 3))+ # increase distance from the y-axis
    theme(axis.title.x = element_text(vjust = -1)) # increase distance from the x-axis

penguin_plot
```

[![Screen Shot 2020-07-04 at 9 23 33 PM](https://user-images.githubusercontent.com/39834789/86522981-6337b100-be40-11ea-8cad-2ec62cbba3c6.png)](https://user-images.githubusercontent.com/39834789/86522981-6337b100-be40-11ea-8cad-2ec62cbba3c6.png)

### Change legend position  更改图例位置

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#change-legend-position)

Legends can be positioned in a number of different ways using `legend.position`:  
图例可以使用 `legend.position` 以多种方式定位：

- `theme(legend.position="top")`
- `theme(legend.position="bottom")`
- `theme(legend.position="left")`
- `theme(legend.position="right")`
- `theme(legend.position="none")`

Legend loction can be also a numeric vector c(x,y), where x and y are the coordinates of the legend box. Their values should be between 0 - 1. c(0,0) is the “bottom left” and c(1,1) is the “top right” position.  
图例位置也可以是一个数值向量 c(x,y)，其中 x 和 y 是图例框的坐标。它们的值应在 0 - 1 之间。c(0,0) 是“左下”位置，c(1,1) 是“右上”位置。

```
penguin_plot <- penguin_plot + 
    theme(legend.position = c(0.85, 0.2))

penguin_plot
```

[![Screen Shot 2020-07-04 at 9 23 52 PM](https://user-images.githubusercontent.com/39834789/86522982-63d04780-be40-11ea-9840-93bd41523d72.png)](https://user-images.githubusercontent.com/39834789/86522982-63d04780-be40-11ea-9840-93bd41523d72.png)

### Saving the figure  保存图形

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#saving-the-figure)

Publications require high quality images and they specify the size and format required on their website.  
出版物需要高质量的图像，并且它们会在其网站上指定所需的尺寸和格式。

#### `ggsave`

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#ggsave)

`ggsave` is one example of how to save your figures.  
`ggsave` 是保存您图像的一种方法。

It allows you to save high quality images in a variety of different file types (e.g. "png", "eps", "ps", "tex", "pdf", "jpeg", "tiff", "png", "bmp", "svg", "wmf"). You can also specify the `width` and `height` in "in", "cm", or "mm", and specify the plot resolution with `dpi`.  
它允许您以多种不同的文件类型（例如 "png"、"eps"、"ps"、"tex"、"pdf"、"jpeg"、"tiff"、"png"、"bmp"、"svg"、"wmf"）保存高质量图像。您还可以指定 `width` 和 `height` 以 "in"、"cm" 或 "mm" 为单位，并使用 `dpi` 指定绘图分辨率。

```
# This will save the last plot for the code you ran:

ggsave("penguin_plot.pdf", 
       dpi = 600, 
       width = 100, height = 60, unit = "mm")
```

#### `pdf`

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#pdf)

An alternative method is to use `pdf`. This allows you to specify the colour mode (e.g. cmyk).  
另一种方法是使用 `pdf` 。这允许您指定颜色模式（例如 cmyk）。

```
pdf("ggplot-cmyk.pdf", width = 12 / 2.54, height = 8 / 2.54,
    colormodel = "cmyk")

print(penguin_plot)

dev.off()
```

## More `ggplot2` plots and tricks  
更多 `ggplot2` 图表和技巧

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#more-ggplot2-plots-and-tricks)

### Change the size of points based on other data  
根据其他数据调整点的大小

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#change-the-size-of-points-based-on-other-data)

Size can be changed based on data within the `penguins` dataframe. For example, here we have changed the size of the points based on `bill_depth_mm`.  
点的大小可以根据 `penguins` 数据框中的数据进行调整。例如，这里我们根据 `bill_depth_mm` 调整了点的大小。

```
ggplot(penguins, aes(body_mass_g, bill_length_mm))+ 
     geom_point(aes(size = bill_depth_mm)) 
```

[![Screen Shot 2020-07-04 at 9 24 22 PM](https://user-images.githubusercontent.com/39834789/86522983-63d04780-be40-11ea-9169-6c766151715c.png)](https://user-images.githubusercontent.com/39834789/86522983-63d04780-be40-11ea-9169-6c766151715c.png)

### Adding an ellispe  添加椭圆

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#adding-an-ellispe)

Add 95% confidence interval ellispses with `stat_ellipse`.  
添加 95%置信区间椭圆，使用 `stat_ellipse` 。

```
ellipse<- penguin_plot + 
  stat_ellipse(aes(colour = species, level=0.95))
  

ellipse
```

[![Screen Shot 2020-07-04 at 9 24 42 PM](https://user-images.githubusercontent.com/39834789/86522964-29ff4100-be40-11ea-8a8b-dfb4fa8cb66a.png)](https://user-images.githubusercontent.com/39834789/86522964-29ff4100-be40-11ea-8a8b-dfb4fa8cb66a.png)

### Linear regression line  线性回归线

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#linear-regression-line)

Add a linear regression line with `geom_smooth(method=lm)`.  
添加线性回归线 `geom_smooth(method=lm)` 。

```
lm <- penguin_plot + 
  geom_smooth(method=lm, aes(colour = species))

lm 
```

[![Screen Shot 2020-07-04 at 9 24 56 PM](https://user-images.githubusercontent.com/39834789/86522966-2cfa3180-be40-11ea-8a52-2a9b094f2c62.png)](https://user-images.githubusercontent.com/39834789/86522966-2cfa3180-be40-11ea-8a52-2a9b094f2c62.png)

### `facet_wrap 根据某个标准分割图形`

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#facet_wrap)

`facet_wrap` is a fantastic tool to slit plots based on a specified categorical column. Here we will use the `species` column.  
`facet_wrap` 是一个根据指定分类列分割图形的绝佳工具。这里我们将使用 `species` 列。

```
penguin_plot + 
  facet_wrap(~species, ncol = 3, nrow = 1) + # specifying 3 columns, 1 row
  theme(legend.position = "none") # remove legend
```

[![Screen Shot 2020-07-04 at 9 25 12 PM](https://user-images.githubusercontent.com/39834789/86522947-e4db0f00-be3f-11ea-9766-0b4539fec0b9.png)](https://user-images.githubusercontent.com/39834789/86522947-e4db0f00-be3f-11ea-9766-0b4539fec0b9.png)

### Changing strip design  更改标签设计

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#changing-strip-design)

It is also possible to change the `size`, `colour`, `face` and `fill` colour of the facet strips with the following code:  
也可以通过以下代码更改 `size` 、 `colour` 、 `face` 和 `fill` 的色条颜色：

```
penguin_plot + 
  facet_wrap(~species, ncol = 3, nrow = 1) + # specifying 3 columns, 1 row
  theme(legend.position = "none")+ # remove legend
    theme(strip.text.x = element_text(size = 16, color = "white", face = "bold"), 
          strip.background = element_rect(fill="black"))
```

[![Screen Shot 2020-07-04 at 9 25 28 PM](https://user-images.githubusercontent.com/39834789/86522949-e73d6900-be3f-11ea-8d8c-d94e218183d3.png)](https://user-images.githubusercontent.com/39834789/86522949-e73d6900-be3f-11ea-8d8c-d94e218183d3.png)

### Removing white space and free axes  
删除空白和自由坐标轴

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#removing-white-space-and-free-axes)

We can also remove the free space using `scales = free`.  
我们也可以使用 `scales = free` 来去除空白。

```
penguin_plot + 
  facet_wrap(~species, scales = "free")+ 
  theme(legend.position = "none")+ # remove legend
    theme(strip.text.x = element_text(size = 16, color = "white", face = "bold"), 
          strip.background = element_rect(fill="black"))
```

[![Screen Shot 2020-07-04 at 9 25 48 PM](https://user-images.githubusercontent.com/39834789/86522950-e7d5ff80-be3f-11ea-907d-6db8db3bbdc7.png)](https://user-images.githubusercontent.com/39834789/86522950-e7d5ff80-be3f-11ea-907d-6db8db3bbdc7.png)

### `facet_grid`: Free facet width  
`facet_grid` : 免费分面宽度

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#facet_grid-free-facet-width)

To allow the facets to be different widths, we must use `facet_grid` and `space = "free"`. This can be used with `scales = "free"`.  
为了让分面具有不同的宽度，我们必须使用 `facet_grid` 和 `space = "free"` 。这可以与 `scales = "free"` 一起使用。

```
penguin_plot + 
  facet_grid(.~species, scales = "free", space = "free")  +
  theme(legend.position = "none")+ # remove legend
    theme(strip.text.x = element_text(size = 16, color = "white", face = "bold"), 
          strip.background = element_rect(fill="black"))
```

[![Screen Shot 2020-07-04 at 9 26 06 PM](https://user-images.githubusercontent.com/39834789/86522951-e86e9600-be3f-11ea-9bbc-e4421015a054.png)](https://user-images.githubusercontent.com/39834789/86522951-e86e9600-be3f-11ea-9bbc-e4421015a054.png)

### Bar plot  条形图

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#bar-plot)

```
library(dplyr)
penguin_summary <-  penguins %>% 
                    group_by(species) %>% 
                    summarise(mean = mean(body_mass_g, na.rm = T), 
                              sd = sd(body_mass_g, na.rm = T))


ggplot(penguin_summary, aes(y = mean, x=species, fill = species)) + 
  geom_bar(stat="identity")+
   geom_errorbar(aes(ymin = mean-sd, ymax = mean+sd), 
                width=.1)  
```

[![Screen Shot 2020-07-04 at 9 26 26 PM](https://user-images.githubusercontent.com/39834789/86522919-988fcf00-be3f-11ea-9150-58c63f1029e7.png)](https://user-images.githubusercontent.com/39834789/86522919-988fcf00-be3f-11ea-9150-58c63f1029e7.png)

Create the plot like the code above for the scatter plot.  
按照上面的代码创建散点图。

```
bar <- ggplot(penguin_summary, aes(y = mean, x = species, fill = species)) + 
  geom_bar(stat = "identity")+
  geom_errorbar(aes(ymin = mean-sd, ymax = mean+sd), 
                width=.1)+
  theme_bw(base_size = 20)+
  theme(panel.grid.major = element_blank(), panel.grid.minor = element_blank())+
  labs(x = "Species", y = "Body Mass (g)")+
 scale_fill_manual(values = c( "#FF6A00","#C15CCB",  "#00868B"))+
  theme(legend.position = "none") +
  scale_y_continuous(limits = c(0, 5700))+
  theme(axis.title.y = element_text(vjust = 3)) +
  theme(axis.title.x = element_text(vjust = -1)) 

bar
```

[![Screen Shot 2020-07-04 at 9 26 41 PM](https://user-images.githubusercontent.com/39834789/86522921-99c0fc00-be3f-11ea-84a6-11f299072466.png)](https://user-images.githubusercontent.com/39834789/86522921-99c0fc00-be3f-11ea-84a6-11f299072466.png)

### Histogram  直方图

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#histogram)

```
ggplot(penguins, aes(x = flipper_length_mm, fill = species)) + 
  geom_histogram(alpha = 0.4)+
  scale_fill_manual(values = c( "#FF6A00","#C15CCB",  "#00868B"))
```

[![Screen Shot 2020-07-04 at 9 26 57 PM](https://user-images.githubusercontent.com/39834789/86522901-5cf50500-be3f-11ea-8118-717799bcfcbd.png)](https://user-images.githubusercontent.com/39834789/86522901-5cf50500-be3f-11ea-8118-717799bcfcbd.png)

### Density Plot  密度图

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#density-plot)

```
ggplot(penguins, aes(x = flipper_length_mm, fill = species)) + 
  geom_density(alpha = 0.4)+
  scale_fill_manual(values = c( "#FF6A00","#C15CCB",  "#00868B"))
```

[![Screen Shot 2020-07-04 at 9 27 14 PM](https://user-images.githubusercontent.com/39834789/86522902-5ebec880-be3f-11ea-9a0e-695413543356.png)](https://user-images.githubusercontent.com/39834789/86522902-5ebec880-be3f-11ea-9a0e-695413543356.png)

```
 flipper <- ggplot(penguins, aes(x = flipper_length_mm, fill = species, colour = species)) + 
  geom_density(alpha = 0.4)+
  scale_fill_manual(values = c( "#FF6A00","#C15CCB",  "#00868B"))+
  scale_colour_manual(values = c( "#FF6A00","#C15CCB",  "#00868B"))+
  theme_bw(base_size = 20)+
  theme(panel.grid.major = element_blank(), panel.grid.minor = element_blank())+
  labs(x = "Flipper Length (mm)", y = "Density", fill = "Species", colour = "Species")+
  #theme(legend.position = "none") +
  scale_x_continuous(expand = c(0,0), limits = c(165, 238))+
  scale_y_continuous(expand = c(0,0), limits = c(0, 0.065), breaks=seq(0, 0.065, 0.02))+
  theme(axis.title.y = element_text(vjust = 3)) +
  theme(axis.title.x = element_text(vjust = -1)) 

flipper 
```

[![Screen Shot 2020-07-04 at 9 27 30 PM](https://user-images.githubusercontent.com/39834789/86522903-5feff580-be3f-11ea-8d42-52f75619abaf.png)](https://user-images.githubusercontent.com/39834789/86522903-5feff580-be3f-11ea-8d42-52f75619abaf.png)

### Add a mean line  添加平均线

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#add-a-mean-line)

```
flipper_mean <- penguins %>%
        group_by(species) %>%
        summarise(mean = mean(flipper_length_mm, na.rm = TRUE))
  
density <- flipper +
  geom_vline(data = flipper_mean, aes(xintercept = mean, colour = species), linetype = "dashed", size = 1.3)

density
```

[![Screen Shot 2020-07-04 at 9 27 47 PM](https://user-images.githubusercontent.com/39834789/86522904-60888c00-be3f-11ea-91a6-8d1e3ae38e46.png)](https://user-images.githubusercontent.com/39834789/86522904-60888c00-be3f-11ea-91a6-8d1e3ae38e46.png)

### Box plot  箱线图

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#box-plot)

```
ggplot(na.omit(penguins), aes(x=species, y=flipper_length_mm, fill=sex)) +
  geom_boxplot()
```

[![Screen Shot 2020-07-04 at 9 28 03 PM](https://user-images.githubusercontent.com/39834789/86522880-156e7900-be3f-11ea-9f1c-9959595a8e5f.png)](https://user-images.githubusercontent.com/39834789/86522880-156e7900-be3f-11ea-9f1c-9959595a8e5f.png)

```
box_plot<- ggplot(na.omit(penguins), aes(x=species, y=flipper_length_mm, fill=sex)) +
  geom_boxplot()+
  theme_bw(base_size = 20)+
  theme(panel.grid.major = element_blank(), panel.grid.minor = element_blank())+
  labs(x = "Species", y = "Flipper Length (mm)", fill = "Sex")+
   theme(axis.title.y = element_text(vjust = 3)) +
  theme(axis.title.x = element_text(vjust = -1)) +
  theme(legend.position = c(0.15, 0.8))

box_plot
```

[![Screen Shot 2020-07-04 at 9 28 17 PM](https://user-images.githubusercontent.com/39834789/86522876-0ab3e400-be3f-11ea-92c7-8a7bf2fb638d.png)](https://user-images.githubusercontent.com/39834789/86522876-0ab3e400-be3f-11ea-92c7-8a7bf2fb638d.png)

### Arrange plots  排列图

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#arrange-plots)

There are several different methods that allow you to arrange your plots into different panels.  
有多种不同的方法可以将您的图表排列在不同的面板中。

#### `ggarrange`

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#ggarrange)

Here we will arrange four of the plots that we made above into one figure using `ggarrange`. You can specify the number of rows `nrow` and `ncol` and add `labels.  
在这里，我们将上面制作的四个图表使用 `ggarrange` 排列成一个图表。您可以指定行数 `nrow` 和 `ncol` ，并添加`labels。

Note we previously saved our figures (`ellipse`, `density`, `bar`, `box_plot`) in the Global Environment and we are calling on them here.  
请注意，我们之前将图表（ `ellipse` , `density` , `bar` , `box_plot` ）保存在全局环境中，并且在这里调用它们。

```
library(ggpubr)

ggarrange(ellipse, density, bar, box_plot,
          nrow = 2, ncol = 2,
          labels = c("a", "b", "c", "d"))
```

[![Screen Shot 2020-07-04 at 9 28 41 PM](https://user-images.githubusercontent.com/39834789/86522873-f4a62380-be3e-11ea-8d5f-1f914c14a793.png)](https://user-images.githubusercontent.com/39834789/86522873-f4a62380-be3e-11ea-8d5f-1f914c14a793.png)

#### Same axes  相同的坐标轴

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#same-axes)

If two plots have the same axes, you can remove one and use `align = "v"` to ensure the plots remain the same size.  
如果两个图形具有相同的坐标轴，你可以删除其中一个，并使用 `align = "v"` 来确保图形保持相同的大小。

```
# Remove y axes text and title
lm <- lm +
   theme(axis.title.y=element_blank(),
        axis.text.y=element_blank(),
        axis.ticks.y=element_blank())


ggarrange(ellipse, lm,
          nrow = 1, ncol = 2,
          labels = c("a", "b"),
          align = "v")
```

[![Screen Shot 2020-07-04 at 9 29 02 PM](https://user-images.githubusercontent.com/39834789/86522871-e48e4400-be3e-11ea-99cd-f43f1c9edd5d.png)](https://user-images.githubusercontent.com/39834789/86522871-e48e4400-be3e-11ea-99cd-f43f1c9edd5d.png)

#### `patchwork`

[](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#patchwork)

`patchwork` is a very straighforward and intuative package for arranging plots. e.g:  
`patchwork` 是一个非常直接且直观的包，用于排列图形。例如：

- `plot1 + plot2` aligns two plots next to each other  
    `plot1 + plot2` 将两个图形并排放置
- `plot1 / plot2` aligns plot2 under plot1  
    `plot1 / plot2` 将 plot2 置于 plot1 下方

Lets make a fancy one.  
让我们做一个花哨的。

We add the figure labels with e.g. `labs(tag = 'a')`. We will also make two of our plots half the size of the main plot with `plot_layout(widths=c(2,1))`.  
我们用 `labs(tag = 'a')` 添加图形标签。我们还将使我们的两个图是主图的一半大小，用 `plot_layout(widths=c(2,1))` 。

```
library(patchwork)

(ellipse + labs(tag = 'a')| ((bar+ labs(tag = 'b')) / (box_plot +labs(tag = 'c')))) + plot_layout(widths=c(2,1))
```

[![Screen Shot 2020-07-04 at 9 29 25 PM](https://user-images.githubusercontent.com/39834789/86522867-d93b1880-be3e-11ea-863c-d4ca3b0498f6.png)](https://user-images.githubusercontent.com/39834789/86522867-d93b1880-be3e-11ea-863c-d4ca3b0498f6.png)

[![image](https://user-images.githubusercontent.com/39834789/86522452-88282600-be38-11ea-8095-4d2cfcd60373.png)](https://user-images.githubusercontent.com/39834789/86522452-88282600-be38-11ea-8095-4d2cfcd60373.png)

Artwork by @CerrenRichards  
艺术作品来自 @CerrenRichards

## About

This tutorial runs through the basics of ggplot2 and how to make a figure ready for publication.  
本教程介绍了 ggplot2 的基础知识以及如何制作适合发表的图表。

### Resources

 [Readme](https://github.com/CerrenRichards/ggplot2-for-publications?tab=readme-ov-file#readme-ov-file)

 [Activity](https://github.com/CerrenRichards/ggplot2-for-publications/activity)

### Stars

 [**54** stars](https://github.com/CerrenRichards/ggplot2-for-publications/stargazers)

### Watchers

 [**2** watching](https://github.com/CerrenRichards/ggplot2-for-publications/watchers)

### Forks

 [**4** forks](https://github.com/CerrenRichards/ggplot2-for-publications/forks)

[Report repository](https://github.com/contact/report-content?content_url=https%3A%2F%2Fgithub.com%2FCerrenRichards%2Fggplot2-for-publications&report=CerrenRichards+%28user%29)

## [Releases](https://github.com/CerrenRichards/ggplot2-for-publications/releases)

No releases published

## [Packages](https://github.com/users/CerrenRichards/packages?repo_name=ggplot2-for-publications)

No packages published  

## Languages

- [HTML100.0%](https://github.com/CerrenRichards/ggplot2-for-publications/search?l=html)

## Footer

[](https://github.com/)© 2025 GitHub, Inc.

### Footer navigation

- [Terms](https://docs.github.com/site-policy/github-terms/github-terms-of-service)
- [Privacy](https://docs.github.com/site-policy/privacy-policies/github-privacy-statement)
- [Security](https://github.com/security)
- [Status](https://www.githubstatus.com/)
- [Community](https://github.community/)
- [Docs](https://docs.github.com/)
- [Contact](https://support.github.com/?tags=dotcom-footer)
- Manage cookies
- Do not share my personal information