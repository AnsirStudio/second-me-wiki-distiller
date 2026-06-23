# 通用 Schema

所有 wiki/self/root 页面尽量使用稳定 YAML，方便 agent、Obsidian 和 Dataview 查询。

## 通用 Frontmatter

```yaml
---
title: ""
tldr: ""
type: concept
status: current
created: 2026-06-23
updated: 2026-06-23
tags: []
aliases: []
sources: []
related: []
confidence: medium
depth: standard
volatility: evergreen
valid_as_of:
review_by:
review_status: ai-draft
---
```

## 受控词表

- `type`：见 `schemas/wiki.md`、`schemas/self.md`、`schemas/root.md`。
- `status`：`current`, `needs-review`, `superseded`, `deprecated`, `archived`。
- `confidence`：`high`, `medium`, `low`, `uncertain`。
- `depth`：`light`, `standard`, `deep`。
- `volatility`：`evergreen`, `volatile`。
- `review_status`：`ai-draft`, `user-reviewed`。

## 字段说明

- `title`：页面标题。
- `tldr`：一句话摘要，供 index 扫描。
- `sources`：raw 路径、summary 页、URL 或对话来源。
- `related`：内部相关页面。
- `valid_as_of`：仅 volatile 页面必填。
- `review_by`：仅 volatile 页面建议填写，通常 1-6 个月后。
- `review_status`：AI 新建或改动后保持 `ai-draft`；只有用户确认后改 `user-reviewed`。

## 日期

所有持久化日期用 `YYYY-MM-DD`。不要只写“今天”“昨天”“最近”。
