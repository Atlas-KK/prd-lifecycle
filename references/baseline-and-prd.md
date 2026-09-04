# Confirmation baseline and PRD

Use this reference only after all relevant clarification themes are confirmed.

## Requirement confirmation baseline

Produce a compact but complete baseline containing:

- Confirmed decisions, grouped by topic.
- Default assumptions that remain necessary.
- P0, P1 and P2 scope when priorities apply.
- Explicit exclusions and non-goals.
- Unresolved questions.
- Risks and dependencies.
- Conflicts with existing code or documents.
- Terminology, states and identifiers that must remain consistent.
- Proposed PRD filename and next version.

Every entry must be marked as one of `已确认`, `产品假设`, `技术建议`, `待确认`, or `本期不实现` when its status is not obvious.

Stop after the baseline. Generate the PRD only after an explicit instruction such as `确认生成PRD`.

## Version rules

1. Search the target directory for existing versions.
2. If no file exists, start at the user-requested version or `v0.1`.
3. If a file exists, read it and increment the version; do not overwrite silently.
4. Preserve prior files unless the user explicitly authorizes replacement.
5. Add document information and revision history.
6. Record which confirmation baseline the PRD implements.

## PRD content

Adapt the chapter structure to the product, but cover applicable areas:

- Background, objectives, positioning and users.
- Current-state analysis and reusable capabilities.
- Scope, exclusions, terms and information architecture.
- Business process, states, levels and decision rules.
- Page structure, interactions, empty states and degradation.
- Inputs, outputs, data model, identifiers and versioning.
- Interfaces, cross-module contracts, idempotency and synchronization.
- Permissions, audit, security and privacy.
- Performance, compatibility, observability and recovery.
- Priorities, dependencies, risks and unresolved matters.
- Acceptance criteria and representative scenarios.
- Existing-module impact and likely files or directories.

For every material function, provide enough detail for implementation and testing:

- Requirement ID and name.
- User story and preconditions.
- Entry and trigger.
- Main, branch and exception flows.
- Inputs, outputs and state changes.
- Business rules and permissions.
- Audit requirements.
- Priority and affected modules.
- Repository capabilities recommended for reuse.
- Acceptance criteria.

Use Given/When/Then for acceptance criteria where behavior can be observed. Include normal, empty, duplicate, conflicting, failed, recovery, concurrent and unauthorized scenarios when relevant.

## Integrity checks

Before delivery, verify:

- Every confirmed decision appears in the PRD.
- No rejected or historical decision has returned.
- Terms, field names, states and actions are consistent.
- Each requirement has an acceptance path.
- Simulation and production capabilities are clearly separated.
- Unresolved items are visibly marked and do not masquerade as final requirements.
- Proposed technical guidance does not redefine product behavior.
- No code was modified.

