# Project discovery

Use this reference for the initial repository-grounding step.

## Evidence collection

Locate relevant files with fast repository search. Read only material relevant to the requested module, but include each applicable category:

- Root and application README files.
- Package manifests, framework configuration, build and test commands.
- Application entry, shell, navigation and layout.
- State management and persistence.
- Domain models, business engines and validation rules.
- Services, adapters and external integrations.
- Shared components, design tokens and responsive layout.
- GIS, chart, video or other domain-specific capabilities when applicable.
- Existing tests and representative fixtures.
- Product documents, MVP specifications and historical proposals.
- Working-tree status, so user changes are not mistaken for baseline code.

Use current code and tests to describe existing behavior, not to veto a new requirement. Historical documents are context unless the user identifies them as authoritative.

## Current-state report

Report the following, omitting sections that genuinely do not apply:

1. Existing product positioning and business loop.
2. Current pages, navigation, modules and main interactions.
3. Relevant data flow, state, domain models and integrations.
4. Reusable components, engines, services and visual language.
5. Likely code and document impact areas.
6. Differences between code, tests and product documents.
7. Decisions that must be clarified before design.
8. Evidence limitations.

For important claims, cite repository file paths and useful line numbers when available.

## Discovery boundary

- Do not write the full target solution.
- Do not modify code or product documents.
- Do not begin the first clarification round in the same response unless the user explicitly requested a combined flow.
- End by asking the user to confirm the current-state analysis. This confirmation gate is not one of the round's key questions.

If required repository evidence is unavailable, ask at most one bounded choice question:

- A（推荐）: provide or authorize access to the missing project material.
- B: continue using explicitly listed assumptions.
- C: produce a repository-independent outline only.

