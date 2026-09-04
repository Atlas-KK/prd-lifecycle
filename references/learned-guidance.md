# PRD Lifecycle 已批准规则

本文件只记录经用户明确批准、可跨任务复用的 PRD 方法规则。项目事实与一次性业务决定不属于这里。

## Active rules

No user-approved cross-task rules have been recorded yet.

## Entry schema

```markdown
### LG-YYYYMMDD-NN — <short name>

- Status: active | retired | superseded
- Modes: create | refine | review | execute | shared
- Scope: cross-task
- Rule: <one actionable instruction>
- Rationale: <failure or rework prevented>
- Evidence: <sanitized summary without raw content>
- Approved: <date and approving instruction>
- Last reviewed: <date>
- Supersedes: <optional rule IDs>
```

## Maintenance

- 只使用 `active` 且模式和场景匹配的规则。
- 当前指令、已批准 PRD 和真实证据始终优先。
- 不存储原始对话、业务文档、源代码、凭据、个人信息或敏感项目事实。
- 未经明确批准，不提升候选、不改变作用域、不合并、不替换或撤销规则。
- 保留非 active 条目以便审计。
