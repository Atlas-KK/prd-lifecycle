# Readiness and repository audit

Use this reference before designing the execution plan.

## 1. Confirm the requirement authority

Record:

- Exact PRD path, title, version and status.
- Applicable confirmation baseline or decision log.
- Target implementation version such as P0 or MVP.
- Explicit exclusions.
- Unresolved items and assumptions.
- User instructions that override or narrow the PRD.

Read the full PRD. Do not plan from its feature list alone.

## 2. Inspect the repository

Read relevant:

- Root and application README files.
- Package manifest, framework, scripts and compiler configuration.
- Application entry, shell, navigation and layout.
- State management, persistence and reset behavior.
- Domain models, engines, services and adapters.
- Shared components and design tokens.
- GIS, media, chart or other specialized subsystems.
- Existing tests, fixtures and demo cases.
- Working-tree status and overlapping user changes.

Use repository facts to protect existing behavior and choose feasible integration points. Do not let missing current code invalidate an approved new requirement.

## 3. Build a gap table

| Requirement | Current capability | Reusable | Required change | Conflict | Decision status |
| --- | --- | --- | --- | --- | --- |

Classify each gap as:

- Additive implementation.
- Existing behavior adaptation.
- Product conflict.
- Technical decision.
- External dependency.
- Deferred scope.

## 4. Separate product and technical decisions

A product decision changes user-visible behavior, business meaning, authority, state, threshold, permission, scope, or acceptance. It cannot be decided by the execution planner.

A technical decision chooses among equivalent implementations while preserving the PRD. It may be recommended with rationale and recorded as `技术建议`.

If a technical choice has materially different product risk, cost, data retention, security, or user experience, return it to the user as a decision.

## 5. Readiness verdict

Choose one:

- READY: PRD and repository evidence are sufficient.
- READY WITH TECHNICAL ASSUMPTIONS: only reversible, documented technical choices remain.
- BLOCKED: a product conflict or missing authority prevents safe planning.
- LIMITED: repository evidence is incomplete; file-level impact is provisional.

Do not hide a blocked decision inside the phase plan.

