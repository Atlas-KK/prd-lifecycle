# Progressive clarification rounds

Use this reference after the current-state report is confirmed.

## Topic planning

Derive topics from the discovered decision gaps. A common sequence is:

1. Product positioning, users, scope and release level.
2. Inputs, sources, event or object types, and data quality.
3. Information architecture, page structure and key interactions.
4. Lifecycle, state machine, levels, rules and human review.
5. Cross-module transfer, identifiers, contracts and status synchronization.
6. Data, permissions, interfaces, degradation and non-functional requirements.
7. Priorities, acceptance scenarios, dependencies, risks and exclusions.

Merge or skip topics when appropriate. Do not discuss more than one topic in a round.

## Question selection

Ask only decisions that materially change at least one of:

- Product scope or responsibility boundary.
- User workflow or irreversible operation.
- Data model, lifecycle or cross-module contract.
- Permission, audit, safety or compliance behavior.
- Release priority, dependency or acceptance criteria.

Do not ask about facts already visible in code or documents. Convert discoverable facts into recommendations and ask only about the remaining product choice.

## Required choice format

Ask 1 to 3 questions. Use stable identifiers and put the recommendation before alternatives:

```markdown
### Q1：<decision question>

建议：A（推荐）— <recommended decision>

理由：<why it fits repository evidence, user goals and downstream design>。

- A（推荐）：<choice and impact>
- B：<choice and impact>
- C：<choice and impact>

请回复 `Q1-A`、`Q1-B` 或 `Q1-C`；也可以直接说明要修改的选项。
```

If all recommendations are acceptable, explicitly allow the user to reply `按建议执行`.

Choices must be mutually exclusive for the decision being made. Do not create a fake choice where one option is obviously invalid. Do not include an `其他` option when the interface already supports free-form input; always accept a written modification.

## After the answer

Do not immediately start the next topic. First output:

- 本轮已确认内容。
- 尚未确认内容。
- 与代码或文档的冲突。
- 对后续设计和问题顺序的影响。

Then ask the user to confirm the round summary. Only an explicit confirmation opens the next round.

Interpret common replies consistently:

- `按建议执行`: select every recommended option in the current round.
- `确认`: confirm the immediately preceding round summary, not future rounds.
- A modification: record the modified decision verbatim and update downstream recommendations.
- An answer to only some questions: confirm those answers and retain the rest as `待确认`; do not infer missing answers.

## Conflict handling

When a new answer conflicts with code or a document, show:

1. The user's selected decision.
2. The conflicting evidence and source.
3. The expected product and implementation impact.
4. Whether the conflict changes an existing-system behavior or only adds new behavior.

When it conflicts with an earlier confirmed decision, stop and present a revision choice. Never silently replace the earlier decision.

