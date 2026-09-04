# Development execution document

Use this reference to turn the readiness audit into a Codex-ready plan.

## Required sections

Adapt headings to the project, but include:

1. Document information and requirement authority.
2. Use rules and conflict order.
3. Development objective and explicit non-goals.
4. Current repository baseline.
5. Target technical architecture.
6. Module ownership and dependency boundaries.
7. Data, identifiers, versions and invariants.
8. State, persistence, clock and synchronization architecture when applicable.
9. Development phase overview.
10. Detailed phase instructions.
11. Test strategy and quality commands.
12. FR/AC traceability.
13. Stop conditions and prohibited actions.
14. Codex total-control prompt.
15. Single-phase prompt template.
16. Delivery checklist and artifacts.

Mark non-product conclusions as `技术建议`. Mark unresolved matters as `待确认`.

## Architecture rules

Derive architecture from the PRD and current code:

- Reuse existing capabilities when semantics match.
- Create a new bounded module when reuse would change existing meaning.
- Keep domain rules out of UI components.
- Prefer pure functions for rules, state transitions, mapping, metrics and idempotency.
- Keep Stores or controllers responsible for orchestration, not duplicated rules.
- Define one owner for cross-module mutations.
- Separate business state from UI state.
- Preserve immutable or append-only records required by the PRD.
- Keep simulation, production adapter and failure-injection boundaries explicit.
- Do not propose a new library when platform or existing dependencies are sufficient.
- Directory layouts are technical recommendations, not product requirements.

Only include architecture dimensions relevant to the PRD. Do not add distributed-system machinery to a local prototype without evidence.

## Phase design

Phase 0 is mandatory and read-only:

- Read PRD and execution document.
- Inspect specified code and tests.
- Check working-tree status.
- Build the formal traceability matrix.
- Run or record the current quality baseline.
- List conflicts without resolving them.
- Stop for user confirmation.

For each implementation phase provide:

| Field | Required content |
| --- | --- |
| Goal | One coherent outcome |
| Requirement coverage | Exact FR and AC IDs |
| Preconditions | Prior phases and decisions |
| Planned files | Add, modify or explicitly avoid |
| Tasks | Bounded implementation steps |
| Prohibited work | Scope that must not be pulled forward |
| Tests | Unit, integration, browser or performance as applicable |
| Acceptance evidence | Observable proof |
| Quality gate | Actual repository commands |
| Stop gate | User confirmation required |

Order phases by dependency: application shell, domain contracts, persistence or adapters, pure engines, UI, cross-module integration, recovery and NFR, then full acceptance. Adapt this sequence rather than forcing irrelevant phases.

A phase must be independently reviewable. Avoid both one giant phase and file-by-file micro-phases that do not produce a coherent behavior.

## Existing-system protection

List protected behaviors and the tests or manual checks that prove they remain intact. Include reset isolation, persistence compatibility, existing demo cases, public entry points, contracts and visual behavior when relevant.

Loading, resetting or testing one module must not silently erase another module's data unless the PRD explicitly requires a global reset.

## Final artifacts

Specify expected source code, tests, data fixtures, migration or storage tests, documentation updates, traceability report, performance evidence, unimplemented-scope list and known risks. Do not promise artifacts outside the approved release.

