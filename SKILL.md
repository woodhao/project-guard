---
name: project-guard
description: Use when starting a new software project, inheriting a repository without a single rule authority, or before major architecture work when agent instructions, plans, memory, and implementation rules risk drifting or conflicting.
---

# Project Guard

## Overview

Create one governance chain before implementation. A project is not ready to build until long-lived rules, agent execution rules, architecture decisions, implementation scope, and project state agree.

**Core principle:** one authority per level; no implementation before alignment and explicit authorization.

## Authority Hierarchy

Default:

`GLOBAL_RULES.md → AGENTS.md → approved Design Spec → approved Implementation Plan → explicit current administrator authorization → PROJECT_PLAN.md → PROJECT_MEMORY.md`

Lower layers may specialize higher layers but may not silently override them. Changing a higher-level rule requires updating that artifact first.

## Workflow

1. **Inventory first.** Read existing instructions, plans, memories, specs, Git branch/HEAD, tracked dirty files, and untracked files. Separate current authority, historical-only records, temporary configuration, and conflicts. Do not code.

2. **Create `GLOBAL_RULES.md`.** Store only long-lived, cross-stage invariants: product purpose/non-goals, architecture ownership, agent decision boundaries, Source of Truth/data safety, security, Git/workspace rules, and acceptance philosophy. Use `GLOBAL_RULES.template.md`.

3. **Enforce rule purity.** Exclude stage numbers, branches, SHAs, test paths, temporary bugs, fixtures, current measurements, credentials, deployment values, and task-local failure routing.

4. **Bind `AGENTS.md`.** Require reading `GLOBAL_RULES.md` before repository work. Keep agent mechanics here: startup checks, skills, scope discipline, verification, commits, and STOP behavior. Reference global rules; do not duplicate them. Use `AGENTS.binding.template.md`.

5. **Approve architecture before coding.** Architectural work requires an approved Design Spec. Agents do not decide product direction, ownership, Source of Truth, security policy, or architecture during implementation.

6. **Create an atomic Implementation Plan.** Every unit needs exact owning files/interfaces, action, verification command, expected result, regression scope, commit boundary, and deterministic failure routing. Ban open-ended instructions such as “choose the best approach” or “fix related issues.”

7. **Keep state documents non-authoritative.** `PROJECT_PLAN.md` records current stage/next work. `PROJECT_MEMORY.md` records accepted history. Old architecture may remain only as `HISTORICAL_ONLY`; history never reactivates authority.

8. **Run the alignment gate.** Audit all governance artifacts against the same invariants and classify each finding as `ALIGNED`, `HISTORICAL_ONLY`, or `CONFLICT`. Any unresolved `CONFLICT` blocks implementation.

9. **Authorize implementation separately.** Spec approval ≠ Plan approval ≠ implementation authorization. Before coding, preserve unrelated dirty/untracked work; if safe isolation is impossible, STOP_AND_REPORT.

## Completion Gate

Bootstrap is complete only when:
- one global rule authority exists;
- `AGENTS.md` binds to it;
- Design Spec and Implementation Plan are approved where required;
- state documents are not competing authorities;
- alignment has no unresolved conflicts;
- implementation has separate explicit authorization.

## Verification

Use `PRESSURE_TESTS.md` before relying on this skill in a new environment. The skill is incomplete until agents consistently preserve authority hierarchy, rule purity, dirty-worktree safety, and approval gates under pressure.
