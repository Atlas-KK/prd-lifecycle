# Review protocol

Use this reference to establish an auditable review before searching for defects.

## 1. Identify inputs

Record:

- Exact PRD path, title and version.
- Review request and expected depth.
- Confirmed baseline or decision records.
- Relevant product documents.
- Repository root and current branch when code claims require verification.
- Known historical drafts that are context only.
- Missing or inaccessible evidence.

Read the entire target PRD. Do not review from isolated excerpts when the full document is available.

## 2. Establish authority

Create a source table:

| Source | Version or date | Role | Authority | Notes |
| --- | --- | --- | --- | --- |
| Current instruction | Current turn | Scope and overrides | Highest | Explicit only |
| Confirmation baseline | Identified artifact | Confirmed product decisions | High | May constrain PRD |
| Target PRD | Exact version | Review target | Target | Not self-validating |
| Code and tests | Current checkout | Existing behavior | Evidence | Not a substitute for new requirements |
| Historical documents | Earlier versions | Context | Low | Cannot override current baseline |

If the baseline is absent, review internal consistency and executability, then mark baseline fidelity as not fully assessed.

## 3. Extract invariants

Before findings, extract the statements that must remain stable:

- Users, roles and data scope.
- In-scope and excluded capabilities.
- Types, codes, levels and thresholds.
- State names, transitions and irreversible actions.
- Source records, aggregate records and history rules.
- IDs, versions, idempotency and ordering.
- Cross-module ownership and close authority.
- Storage, retention and reset boundaries.
- Event time, operational time and display time.
- Permissions, approvals and audit requirements.
- P0, P1 and P2 boundaries.
- Quantified non-functional targets.
- Acceptance obligations.

Do not infer an invariant from a single ambiguous sentence. Mark ambiguity as evidence uncertainty.

## 4. Verify repository claims

When the PRD claims an existing capability, reuse path, framework, model, Store, API, test, or component:

1. Locate it in current code.
2. Verify its actual behavior and signature.
3. Note differences between the claim and code.
4. Decide whether the difference is a PRD defect, implementation gap, or expected future change.

Do not criticize a new requirement merely because current code lacks it.

## 5. Coverage passes

Run distinct passes to reduce missed defects:

1. Baseline regression pass.
2. Terminology and cross-section consistency pass.
3. Lifecycle and state transition pass.
4. Data model, immutability and audit pass.
5. Interface, idempotency, ordering and recovery pass.
6. Permissions and irreversible operations pass.
7. Simulation versus production claim pass.
8. NFR and measurable acceptance pass.
9. Repository feasibility and impact pass.
10. FR-to-acceptance traceability pass.

Deduplicate issues after the passes. Keep the strongest evidence and broadest accurate impact in one finding.

## 6. Evidence limits

State areas not fully assessed, such as missing baseline, unavailable code, unresolved external contract, inaccessible design, or absent test data. Do not convert missing evidence into a factual defect.

