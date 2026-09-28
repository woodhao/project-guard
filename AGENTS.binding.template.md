## Global Rule Authority

Before any planning, audit, implementation, refactor, test change, documentation change, or repository action, read and obey:

`GLOBAL_RULES.md`

`GLOBAL_RULES.md` is the highest-priority long-lived project rule source for this repository.

`AGENTS.md` defines how agents execute work; it does not override or duplicate `GLOBAL_RULES.md`.

If an execution instruction conflicts with a higher-level approved authority, STOP_AND_REPORT rather than silently choosing an interpretation.

Do not copy the full global rules into `AGENTS.md`; reference and enforce them.
