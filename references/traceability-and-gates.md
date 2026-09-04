# Traceability and gates

Use this reference to make the execution plan auditable.

## FR and AC matrix

Create one row for every in-scope requirement:

| FR | PRD priority | Phase | Architecture owner | Planned files | Tests | Acceptance criteria | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- |

Use exact IDs from the PRD. If the PRD has unnumbered acceptance scenarios, assign execution-only aliases such as `AC-01` and explicitly state that the aliases do not modify the PRD.

## Coverage checks

Before delivery verify:

- Every in-scope FR appears in at least one phase.
- Every in-scope AC maps to a real test or observable check.
- Every planned component, service or engine maps back to an FR or authorized technical need.
- P1 and P2 work is not silently included in P0.
- No phase relies on a later phase for basic safety or data integrity.
- Cross-module behavior has tests on both sides of the contract.
- Empty, duplicate, conflict, failure, recovery, refresh, concurrency and unauthorized cases are mapped when relevant.
- Existing protected behavior has regression coverage.

An FR without a phase is an orphan requirement. Planned work without an FR, NFR, risk control or approved technical basis is unauthorized scope.

## Quality commands

Use actual commands from the repository. Do not invent a test command or claim it passed.

For each phase distinguish:

- Fast targeted tests during implementation.
- Full lint, unit test and build gate.
- Browser or UI smoke checks.
- Performance or stability evidence.
- Manual evidence that cannot be automated in the current repository.

If the baseline command fails before implementation, record the exact failure, isolate code failure from environment failure, and do not report the gate as passed.

## Stage report

Require Codex to report:

1. Current phase and outcome.
2. FR and AC coverage.
3. Files added, modified and intentionally untouched.
4. Decisions made under PRD authority.
5. Tests and commands with real results.
6. Unfinished items.
7. Risks and blockers.
8. Next-phase recommendation only.

The report must stop after the recommendation. It cannot authorize the next phase.

## Final audit

At completion, compare the implementation report against the original matrix. Report completed, partial, failed and deferred items separately. A passing build does not prove requirement acceptance.

