要使用 Dataview 插件动态生成 moc，你需要创建一个新的笔记，并在其中编写 Dataview 查询语句。以下是一个示例，可以自动提取所有包含 `#AI+能源` 标签的笔记，并将它们以列表的形式展示在 moc 中：

1.  **创建新的笔记：**
    *   在 Obsidian 中创建一个新的笔记，例如，命名为 "AI+能源 MOC (Dataview)"。

2.  **编写 Dataview 查询语句：**
    *   在新的笔记中，输入以下 Dataview 查询语句：

    ```markdown
    ```dataview
    LIST file.link
    WHERE contains(file.name,"毕业设计“)
    SORT file.mtime DESC
    ```






    ```dataview
    LIST 
    WHERE contains(file.name,"关于")
    SORT file.mtime DESC
    ```


> [!NOTE] Title
> 引用里面需要 英文引号




    ```dataview
    LIST file.link
    WHERE contains(file.name,"毕业设计“)
    SORT file.mtime DESC
    ```

    *   **解释：**
        *   `` `dataview`` `：表示这是一个 Dataview 查询语句。
        *   `LIST`：表示以列表的形式展示结果。
        *   `FROM #AI+能源`：表示从所有包含 `#AI+能源` 标签的笔记中提取数据。
        *   `SORT file.mtime DESC`：表示按照笔记的修改时间降序排序。

3.  **查看结果：**
    *   切换到阅读模式，你将看到一个动态生成的列表，其中包含了所有包含 `#AI+能源` 标签的笔记的链接。

**更高级的用法：**

*   **展示更多信息：** 你可以使用 Dataview 提取和展示笔记的更多信息，例如，标题、摘要、创建时间、修改时间等。

    ```markdown
    ```dataview
    TABLE file.mtime AS "修改时间", summary AS "摘要"
    FROM #AI+能源
    SORT file.mtime DESC
    ```

    *   `TABLE file.mtime AS "修改时间", summary AS "摘要"`：表示以表格的形式展示结果，包括 "修改时间" 和 "摘要" 两列。
    *   `file.mtime AS "修改时间"`：提取笔记的修改时间，并将其重命名为 "修改时间"。
    *   `summary AS "摘要"`：提取笔记的 "summary" 属性（需要在笔记的 YAML frontmatter 中定义），并将其重命名为 "摘要"。

*   **分组展示：** 你可以使用 Dataview 将笔记按照特定的属性进行分组展示。

    ```markdown
    ```dataview
    LIST
    FROM #AI+能源
    GROUP BY file.folder
    ```

    *   `GROUP BY file.folder`：表示按照笔记所在的文件夹进行分组。

*   **自定义样式：** 你可以使用 CSS 代码自定义 Dataview 的样式，使其更符合你的需求。

**示例：**

假设你有以下几个笔记：

*   [[AI在智能电网中的应用]]，包含 `#AI+能源` 标签，YAML frontmatter 中包含 `summary: "介绍AI在智能电网中的应用"`。
*   [[AI在能源预测中的应用]]，包含 `#AI+能源` 标签，YAML frontmatter 中包含 `summary: "介绍AI在能源预测中的应用"`。
*   [[碳市场]]，包含 `#碳市场` 标签。

在 "AI+能源 MOC (Dataview)" 笔记中，输入以下 Dataview 查询语句：

```markdown
```dataview
TABLE file.mtime AS "修改时间", summary AS "摘要"
FROM #AI+能源
SORT file.mtime DESC
```

切换到阅读模式，你将看到以下结果：

| 文件              | 修改时间             | 摘要            |
| --------------- | ---------------- | ------------- |
| [[AI在智能电网中的应用]] | 2025-06-05 10:00 | 介绍AI在智能电网中的应用 |
| [[AI在能源预测中的应用]] | 2025-06-04 18:00 | 介绍AI在能源预测中的应用 |

**总结：**

使用 Dataview 插件动态生成 moc，可以帮助你更方便地组织和管理笔记，并根据你的需求自定义 moc 的内容和样式。 关键在于编写合适的 Dataview 查询语句，提取和展示你需要的信息。 建议阅读 Dataview 插件的文档，了解其所有功能和选项。

