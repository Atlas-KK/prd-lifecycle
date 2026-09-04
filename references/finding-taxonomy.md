# Finding taxonomy

Use this reference to classify and calibrate findings.

## Severity

| Severity | Meaning | Typical consequence |
| --- | --- | --- |
| P0 Blocker | Cannot safely or uniquely implement the approved product | Baseline contradiction, unsafe authority, impossible state, destructive data rule |
| P1 Major | Likely to cause substantial rework, wrong behavior, or failed acceptance | Missing contract semantics, inconsistent lifecycle, untestable critical rule |
| P2 Moderate | Bounded ambiguity or coverage gap with a reasonable local fix | Missing edge case, incomplete field constraint, weak but recoverable acceptance |
| P3 Minor | Editorial or low-risk clarity issue | Naming polish, formatting, non-blocking duplication |

Use P0 sparingly. A missing nice-to-have is not P0. A stylistic issue is not P1.

## Categories

- BL: confirmed-baseline regression.
- CON: internal contradiction or terminology drift.
- STM: state machine, lifecycle or transition defect.
- DAT: data model, immutability, version or history defect.
- INT: interface, ownership, idempotency, ordering or synchronization defect.
- TIM: clock, time field or SLA semantic defect.
- PER: persistence, retention, reset or recovery defect.
- AUT: role, permission, approval or audit defect.
- PRO: prototype, simulation or production-claim defect.
- NFR: performance, compatibility, security or observability defect.
- ACC: acceptance or traceability defect.
- ENG: repository feasibility or existing-system compatibility defect.

A finding may have one primary category and related tags.

## High-value adversarial checks

Look especially for:

- A confirmed type, state, threshold or priority silently changed.
- One concept represented by multiple incompatible terms.
- A status that has no legal entry, exit, rollback, owner, or audit event.
- An original record overwritten instead of versioned or appended.
- A Plan, task, UI state, or AI score incorrectly used as event truth.
- Duplicate requests creating duplicate business objects.
- Missing version arbitration for retries, replay or out-of-order messages.
- Simulation time used for operational SLA.
- localStorage, sessionStorage and business persistence mixed without justification.
- A destructive reset crossing module or data-namespace boundaries.
- AI confidence described as accuracy.
- Mocked data described as a production integration.
- P1 or P2 silently promoted into P0, or required P0 pushed out.
- Acceptance criteria that cannot be observed, measured, or reproduced.
- A field or rule present in one section but absent from model, interface or acceptance.
- A suggested reuse path that would require changing existing business semantics.

## False-positive controls

Before publishing a finding, ask:

1. Is the behavior actually defined elsewhere in the same PRD?
2. Is the difference intentional and explicitly versioned?
3. Am I confusing a technical suggestion with a product requirement?
4. Am I treating missing current code as proof the requirement is invalid?
5. Is the alleged conflict based only on a historical document?
6. Can I cite the exact impact if left unchanged?

If the answer weakens the finding, downgrade, reframe, or omit it.

