# Self Schema

适用于 `self/` 五件套。所有页面继承 `schemas/common.md`，`type` 使用 self 类型。

## Types

`self-observations`, `self-identity`, `self-preferences`, `self-now`, `self-profile`

## observations.md

```markdown
# 观察

## 事实流

- `YYYY-MM-DD` | 明确/强推断/弱信号 | 观察内容。证据：`来源`。

## 时间线

- `YYYY-MM-DD`：更新说明。
```

规则：只追加，不重写旧观察。

## identity.md

```markdown
# 身份

## 稳定身份

## 价值观与原则

## 思维方式与决策依据

## 待确认问题

## 时间线
```

只收稳定、可复用、对 second me 有帮助的内容。

## preferences.md

```markdown
# 偏好

## 沟通

## 工具与工作流

## 学习

## 审美与风格

## 明确的不要

## 时间线
```

每条偏好说明适用场景和证据。

## now.md

```markdown
# 当前

## 当前项目

## 活跃问题

## 近期目标

## 曾经在忙

## 时间线
```

旧事项移到历史区，不删除。

## profile.md

控制在 500 token 以内。

```markdown
# 个人画像

用户是……

用户重视……

用户偏好……

截至 YYYY-MM-DD，当前关注……

使用这个 profile 时要注意……

## 时间线
```

只有 identity/preferences/now 有实质更新，或审查模式触发时，才重新生成。
