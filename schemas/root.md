# Root Schema

适用于知识库根目录的 `index.md`、`log.md`、`nextstep.md`。

## index.md

条目少于 1000 时，`index.md` 是主导航。

```markdown
# 目录

## 概念

- [[wiki/concept/example]] - 一句话 tldr。更新：YYYY-MM-DD。标签：ai, memory。

## 实体

## 话题

## 方法

## 小技巧

## GitHub

## 对比

## 引用

## 碎片

## 自我记忆
```

超过 1000 条时，可以建议增加本地搜索、BM25 或向量层，但仍保留 `index.md`。

`index.md` 只索引"编译后的知识"层（concept/entity/topic/method/tip/github/comparison/quote），**不索引 summary**。summary 是 raw 的前引速读，不是核心知识页（见 `schemas/wiki.md`），把它也列进 index.md 会让根导航随来源数量线性膨胀、稀释"先扫 tldr"的作用。summary 的可达性由它所属的 entity/concept 页面的"已蒸馏作品"或"关联"链接保证：检索路径是 index → entity/concept → summary（如果想看更细）→ raw（如果想看原文），不需要 index.md 兜底。

## log.md

操作日志只追加，记录库发生了什么。最新记录靠前。

```markdown
# Log

## [YYYY-MM-DD HH:MM] distill | 来源或批次标题

- 来源：`raw/inbox/example.md`
- 变更：[[wiki/summary/example]], [[wiki/concept/example]]
- topic：AI
- 备注：冲突/用户问题/弱 self 信号。
```

记录写入、归档、删除、合并、审查、重要结构升级。纯检索不写 log。

## nextstep.md

```markdown
# 下一步

## 待确认

- [ ] `YYYY-MM-DD` [[页面]] - 需要确认什么。

## 数据缺口

- `YYYY-MM-DD` 缺口说明，关联页面/来源。

## 想法

- `YYYY-MM-DD` 想法一句话，可能落点。
```

AI 只追加待确认项，不替用户勾选完成。
