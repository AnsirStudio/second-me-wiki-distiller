# Raw 规则

`raw/` 是原始来源层。它保存素材和附件，不承担最终知识表达。

## 目录

```text
raw/
  inbox/
    clipping/
  attachment/
  articles/
  books/
  chats/
  design/
  ideas/
  research/
  videos/
  work/
  socialmedia/
  dropzone/
```

## 分类

- `raw/inbox/`：待处理入口。
- `raw/inbox/clipping/`：浏览器/Obsidian clipper 自动保存内容。
- `raw/attachment/`：被 markdown 引用的图片、PDF、视频或其他附件。附件必须被某个 raw markdown 引用。
- `raw/articles/`：文章、博客、论文、报告等成稿文本。
- `raw/books/`：书籍、长摘录、读书笔记。
- `raw/chats/`：与人或 AI 的对话记录。
- `raw/design/`：设计、审美、截图、参考图相关素材。
- `raw/ideas/`：个人灵感原始记录。
- `raw/research/`：调研合集、搜索结果、带来源清单的研究材料。
- `raw/videos/`：视频、讲座、访谈、字幕、逐字稿。
- `raw/work/`：工作材料、项目材料、文档、PPT/PDF 提取文本。
- `raw/socialmedia/`：社交媒体内容，包括抖音、YouTube、小红书、B 站、X 等。
- `raw/dropzone/`：过小、方向不清、暂时无法蒸馏的碎片。

## 处理原则

- raw 尽量保持原貌，不把蒸馏结果写回 raw。
- 不为了一个普通链接强行创建 raw 文件；轻量指针可以直接作为 wiki 页来源。
- 重要长来源建议创建 `wiki/summary/`。
- 对重复来源先合并记录，不让同一来源重复支撑同一结论。
- 附件只在影响理解时检查，不把无关媒体塞进 wiki 正文。
- 非 markdown 素材不要孤立存在。PDF、图片、视频、PPT、音频等二进制文件放入 `raw/attachment/`，并在合适的 raw 分类下创建一个最小 markdown 指针文件引用它。
- 指针文件只需要记录标题、来源、文件路径、素材类型、简短说明和后续处理状态；不要为了“格式完整”虚构不存在的 metadata。

## 重复识别

写入前检查：

- original_url 是否已存在；
- 标题、作者、平台是否高度相似；
- 正文是否大段重合；
- 半年前保存过的内容是否再次进入 inbox。

处理：

- 完全重复：不新建知识页，在 log 中说明跳过或合并。
- 疑似重复：互相标注关系，或进入 `nextstep.md` 等用户确认。
- 同主题但不同角度：正常保留，互链说明区别。

## 非 Markdown 素材

当素材本身不是 markdown：

1. 把原始文件放进 `raw/attachment/`。
2. 在最合适的 raw 分类下创建一个 `.md` 指针文件，例如 `raw/articles/某报告.md`、`raw/design/某截图.md`、`raw/videos/某视频.md`。
3. 指针文件用 markdown 链接或 Obsidian embed 指向附件。
4. 如果从 PDF/图片/视频中提取了文字，提取文本写在指针文件正文中，并保留附件路径。
5. 后续蒸馏只引用这个 markdown 指针文件；附件作为证据，不直接当成 wiki 页面。
