# Context routes

Guidance paths are relative to the loaded immutable instruction root.
Runtime paths use the package root recorded in `run/current/bootstrap.md`.
Target paths use the recorded target workspace.
A snapshot prompt locates bootstrap at `../../../bootstrap.md` relative to its `prompts/` directory.
Setup uses the mutable package root while preparing the first snapshot.
Installation uses `SETUP.md` and creates private `installation/profile.md` and `installation/adapter.md`.
Run setup pins both installed files. Runtime guidance reads their snapshot copies, never the optional adapter sources.
Read the current assignment before project sources.
Follow the target repository's applicable instructions.

| Role | Required context | Inputs |
| --- | --- | --- |
| Orchestrator and run setup | `context/contracts.md`, `context/transitions.md`, `context/instruction-revisions.md`, `context/continuation.md`, own prompt, `docs/setup.md`, installed profile and adapter | Canonical run records and matching results |
| Every stage | `context/contracts.md`, own prompt | `run/current/assignment.md` and ordered cited inputs |
| Delegating stage or nested worker | `context/nested-models.md`, pinned installed profile and adapter | Written work order and disjoint ownership |
| Planner | Shared worker context above | No nested agents or nested-model preload |

The assignment routes both work type and affected area to project sources.
Bug work starts with reproduction. Refactoring records behavior to preserve.
Features start with requested behavior. Review starts with criteria and source identity.
Stage-specific input order overrides generic preloading, including linked or embedded appendices.
Checker freezes its requirement-derived baseline before any target implementation exposure.

Workers load additional policy or project sources only when their assigned responsibility requires them.
Controller policies are not worker preload requirements.
Do not load unrelated archives, dependencies, or all documentation by default.
Keep stable instructions here and temporary progress in current-run records.
