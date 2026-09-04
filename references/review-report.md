# Review report

Use this format unless the user requests another.

## 1. Review verdict

Choose one:

- Pass: no material defect found within the evidence boundary.
- Pass with changes: implementable after specified P1/P2 corrections.
- Blocked: one or more P0 findings prevent safe or unique implementation.
- Limited review: missing evidence prevents a full conclusion.

State the target version, sources checked, and review boundary.

## 2. Findings summary

| ID | Severity | Category | Location | Short finding | Required action |
| --- | --- | --- | --- | --- | --- |

Order by severity, then implementation dependency. Do not mix optional suggestions into required findings.

## 3. Detailed finding

Use one section per finding:

```markdown
### RT-01 — <concise title>

- Severity: P1 Major
- Category: INT
- Location: <chapter, requirement ID, field, and line when available>
- Evidence: <target text and applicable baseline or repository fact>
- Problem: <precise contradiction, omission, or ambiguity>
- Impact: <product, engineering, test, safety, or delivery consequence>
- Required correction: <narrow bounded change>
- Related requirements: <FR, AC, state, interface, or file>
- Confidence: high | medium
```

Quote minimally. Prefer paraphrase plus location.

## 4. Coverage status

Report each area as reviewed, partially reviewed, not applicable, or not assessable:

- Baseline fidelity.
- Scope and priority.
- Terminology.
- State and lifecycle.
- Data and history.
- Cross-module contract.
- Time semantics.
- Permissions and audit.
- Persistence and recovery.
- Prototype boundary.
- NFR.
- Acceptance and traceability.
- Repository feasibility.

## 5. Recommended revision order

Give the dependency-aware order for corrections without editing the PRD. For example: baseline decisions, terminology, state model, contract, data model, UI behavior, acceptance.

## 6. Optional improvements

List only clearly optional improvements. Keep them separate from findings.

If there are no material findings, say so directly and list residual risks or unassessed evidence. Do not invent issues to populate the report.

