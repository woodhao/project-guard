# project-guard

A reusable Codex/agent skill for keeping software projects governed before implementation starts.

`project-guard` establishes one authority chain for long-lived rules, agent execution, architecture, implementation plans, and project state so old plans, memories, or local instructions do not silently override current decisions.

## Use it when

- starting a new software project;
- inheriting a repository with scattered or conflicting rules;
- preparing for a major architecture change;
- agent instructions, plans, and memory have started drifting apart.

## Core governance chain

`GLOBAL_RULES.md → AGENTS.md → approved Design Spec → approved Implementation Plan → explicit current administrator authorization → PROJECT_PLAN.md → PROJECT_MEMORY.md`

The skill keeps long-lived rules in one place, separates historical state from current authority, blocks premature implementation, and requires an alignment gate before coding.

## Files

- `SKILL.md` — main reusable skill.
- `GLOBAL_RULES.template.md` — project constitution template.
- `AGENTS.binding.template.md` — minimal binding from agent instructions to the global rule source.
- `PRESSURE_TESTS.md` — pressure scenarios for verifying the skill under conflicting instructions.

## Install for Codex

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
git clone https://github.com/woodhao/project-guard.git "${CODEX_HOME:-$HOME/.codex}/skills/project-guard"
```

Then invoke explicitly with:

```text
$project-guard initialize governance for this repository before implementation.
```

## Principle

One authority per level. No implementation before alignment and explicit authorization.
