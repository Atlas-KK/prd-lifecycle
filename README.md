# PRD Lifecycle Skill

面向产品需求文档全生命周期的 Codex Skill。它将 PRD 创建、分步补全、红队评审和开发执行规划统一到一个入口，并通过明确的确认门禁保护业务决策与代码边界。

## 四种工作模式

| 模式 | 典型输入 | 主要产物 |
| --- | --- | --- |
| `create` | 产品构想与现有代码仓库 | 现状报告、需求确认基线、版本化 PRD |
| `refine` | PRD 或需求草稿 | 分步修订稿、版本历史、可选 Word 文档 |
| `review` | 指定 PRD 与可选仓库证据 | 分级问题、证据和修订建议 |
| `execute` | 已批准 PRD 与现有仓库 | 就绪审计、开发执行文档、追踪矩阵和控制提示词 |

该 Skill 负责需求与执行规划，不直接实现业务代码。

## 核心特点

- 根据已有材料自动选择最合适的模式。
- 区分用户决定、代码事实、文档事实、产品假设和技术建议。
- 在关键阶段要求明确确认，避免把未决事项写成最终需求。
- 支持 PRD 版本管理、修订记录和 Markdown/Word 交付。
- 将批准后的 PRD 转换为可追踪、可分阶段执行的 Codex 开发文档。

## 安装

将本仓库完整放入用户级 Skill 目录：

```text
$HOME/.agents/skills/prd-lifecycle/SKILL.md
```

也可以作为项目级 Skill 放入：

```text
<项目目录>/.agents/skills/prd-lifecycle/SKILL.md
```

Codex 通常会自动发现 Skill；如果没有出现，请重启 Codex。

## 使用示例

显式调用：

```text
$prd-lifecycle 根据当前仓库和这个产品构想创建一份 PRD
```

```text
$prd-lifecycle 红队评审 docs/PRD-v1.2.md，只输出问题和证据
```

```text
$prd-lifecycle 把已批准的 PRD 转为 Codex 开发执行文档
```

也可以直接描述“创建、补全、评审或转化 PRD”的任务，由 Codex 根据 Skill 描述自动匹配。

## 仓库结构

| 路径 | 说明 |
| --- | --- |
| `SKILL.md` | 模式路由、权限边界和主流程 |
| `references/` | 需求澄清、版本管理、评审、就绪审计和执行文档规范 |
| `scripts/prd_doc.py` | PRD 文档初始化、升版与导出辅助脚本 |
| `agents/openai.yaml` | Codex 中的 Skill 展示配置 |

## 工作原则

- 未确认的业务规则保持为待确认项。
- 评审模式只评审，不改文档；执行规划模式只规划，不实现代码。
- 仓库中的代码用于证明现状，不能自动推翻已批准的新需求。
- 进入下一阶段前必须满足 `SKILL.md` 中规定的确认条件。

## 相关文档

- [Skill 主说明](./SKILL.md)
- [项目取证](./references/project-discovery.md)
- [版本管理](./references/versioning.md)
- [执行文档规范](./references/execution-document.md)
- [OpenAI：Build skills](https://developers.openai.com/codex/skills)
