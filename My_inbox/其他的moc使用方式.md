```dataview
	LIST
	WHERE contains(file.name,"moc")
```


对，你的感觉没错！Dataview 的 **DQL** 基本就是“类 SQL 的筛选器”，90% 的场景用三五行就能搞定。给你一眼入门心法👇

  

## **一眼心法（把它当 SQL 用）**

- **SQL**：SELECT 列 FROM 表 WHERE 条件 GROUP BY 分组 ORDER BY 排序 LIMIT N
    
- **DQL**：TABLE 列1, 列2 FROM "文件夹" WHERE 条件 GROUP BY 表达式 SORT 表达式 DESC LIMIT N
    

  

**差异点（记住这 7 条就很顺）：**

1. **没有表**：每个笔记=一行数据，字段来自 **YAML/内联** **key:: value**，还有一堆内置的 file.*（如 file.name/file.mtime）。
    
2. **FROM 是“来源”**：写 **“文件夹”**、**#标签**、或 **[[页面]]**（入链/出链可用 outgoing([[...]])）。
    
3. **字符串一定要半角引号**："..." 或 '...'；中文引号会报 _Expected: string_。
    
4. **数组要先拍平**：列表/多选字段先 FLATTEN keywords AS kw 再 WHERE contains(kw, "AI")。
    
5. **分组后数据在** **rows**：GROUP BY 之后用 length(rows) / max(rows.file.mtime) 做聚合。
    
6. **正则匹配**：regexmatch('^关于(“|")', file.name)。
    
7. **性能习惯**：尽量 **限定 FROM**（文件夹/标签），再 WHERE，少做全库扫描。
    

  

## **两个超常用模板**

- 列出两个文件夹的所有 Markdown，按更新时间：
    

```
TABLE WITHOUT ID file.link AS 文件, file.folder AS 文件夹, file.mtime AS 最近修改
FROM "毕业论文@实证结果分析" OR "毕业论文@文献综述"
WHERE file.ext = "md"
SORT file.mtime DESC
```

- 按年份分组统计（用格式化拿年份）：
    

```
TABLE length(rows) AS 数量, max(rows.file.mtime) AS 最近更新
FROM "毕业论文@"
GROUP BY dateformat(file.mtime, "yyyy") AS 年份
SORT 年份 DESC
```

## **小排错清单**

- 报 _Expected: string_ → 检查是否混用了中文引号 / 少了闭合引号。
    
- 没结果 → 路径是否写全？FROM "上级/子文件夹"。
    
- 表头想中文 → AS 改名：file.mtime AS 最近修改。
    
- 默认首列太丑 → TABLE WITHOUT ID。
    

  

如果你把常用字段（比如 导师/关键词/进度/DDL）先统一，我可以给你拼一页“毕业论文仪表盘”的 DQL，直接落地用。