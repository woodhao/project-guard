# <Project Name> Global Rules

`GLOBAL_RULES.md` is the highest-priority long-lived project rule source for this repository.

## Authority

Default priority:

`GLOBAL_RULES.md → AGENTS.md → approved Design Spec → approved Implementation Plan → explicit current administrator authorization → PROJECT_PLAN.md → PROJECT_MEMORY.md`

Lower-level documents may specialize but may not silently override higher-level rules.

## Rule Purity

Keep only long-lived cross-stage principles here. Exclude temporary stages, branches, commit SHAs, test paths, bugs, fixtures, current measurements, credentials, environment values, and task-local execution routing.

## Product Purpose

- Primary product goal:
- Explicit non-goals:
- What technical PASS does **not** prove:

## Architecture Invariants

- Single owners for major runtime responsibilities:
- Capabilities that must not be duplicated:
- Forbidden alternate execution paths:

## Agent Decision Boundary

- Decisions reserved for the administrator/product owner:
- Decisions agents may make mechanically:
- STOP_AND_REPORT conditions:

## Source of Truth and Data Safety

- Canonical business/system SoTs:
- Read-only systems:
- Schema/migration approval rule:
- Temporary/sandbox data rule:

## Security and Side Effects

- Trusted identity source:
- Final authorization owner:
- Idempotency/receipt requirements:
- Unknown side-effect replay rule:

## Git and Workspace

- Branch/worktree convention:
- Dirty/untracked preservation rule:
- Commit scope rule:
- Push/PR/merge/deploy authorization rule:

## Testing and Acceptance

- Root-cause development principle:
- Targeted/full regression requirements:
- Human acceptance boundary:
- Product completion criteria:
