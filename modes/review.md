# 审查模式

用于维护现有知识库：检查矛盾、重复、断链、过期页面、孤儿页面、scrap/dropzone 聚类，以及从长期 log 中提炼 self 信号。

## Step 1：定审查范围

不需要先读全部规则。先根据用户请求和目录结构确定范围：

- 只查某页；
- 只查 `wiki/`；
- 只查 `self/`；
- 只查 `raw/dropzone/` / `wiki/scrap/`；
- 全库健康检查。

如果用户未指定范围，默认先读 `index.md`、近期 `log.md`、`nextstep.md`，再决定下一步要查哪些目录。

## Step 2：按范围读取规则

按实际范围读取：

- 查 root 文件时读 `schemas/root.md`。
- 查 YAML/状态/日期时读 `schemas/common.md`。
- 查 wiki 页面时读 `references/wiki.md` 和 `schemas/wiki.md`。
- 查 self 页面或整理画像时读 `references/self.md` 和 `schemas/self.md`。
- 查 raw/dropzone 或附件指针时读 `references/raw.md` 和 `schemas/raw.md`。

不要为没涉及的层读取规则。

## Step 3：确定性检查

逐项检查当前范围内的问题：

- YAML 字段缺失或受控词表漂移。
- `index.md` 缺条目或链接失效。
- `log.md` 缺记录、记录不可解析或日期不清。
- 页面没有来源、时间线或 updated 日期。
- 重复页面、相似标题、同源重复。
- 过期或强实时页面。
- 页面之间的冲突。
- `wiki/scrap/` 与 `raw/dropzone/` 是否可聚类升级。
- 非 markdown 素材是否缺少 markdown 指针文件。

低风险修复可直接做；会改变语义、合并、删除或提升 self 结论时先问用户。

## Step 4：self 升维

只有用户要求整理画像，或审查范围包含 self/log 行为信号时，才读取 `references/self.md` 和 `schemas/self.md`。

读近期 `log.md` 和 `self/observations.md`：

- 反复出现的主题可能是注意力信号。
- 反复出现的做法可能是工作流偏好。
- 反复出现的评价标准可能是价值观或决策方式。
- 过期的 `self/now.md` 项目应移到历史区，不直接删除。

只有跨时间重复、证据足够、对未来个性化有用时，才建议写入 self。模糊结论进入 `nextstep.md` 等确认。

## Step 5：收尾

如需写入，再读取 `schemas/root.md`：

- 已做的低风险修复写入 `log.md`。
- 待确认事项写入 `nextstep.md`。
- 如果建议新增类型或新规则，说明理由，并建议更新对应 reference/schema。

## 输出

输出审查报告：

- 发现：按严重程度列问题。
- 已处理：列低风险修复。
- 需要决定：列需要用户确认的合并、删除、self 推断。
- 下一步：建议下一轮维护。
