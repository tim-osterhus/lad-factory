# Context routes

Backticked paths are relative to the package root.
Read the current assignment before project sources.
Follow the target repository's applicable instructions.

| Role | Required context | Inputs |
| --- | --- | --- |
| Orchestrator | `context/contracts.md`, own prompt | Goal, state, matching results |
| Every stage | `context/contracts.md`, own prompt | `run/current/assignment.md` and cited files |
| Delegating stage or nested worker | `context/nested-models.md` | Written work order and disjoint ownership |
| Planner | Shared contracts only | No nested agents |
| Arbiter | Shared contracts and own prompt | Original goal and complete evidence index |

The assignment routes both work type and affected area to project sources.
Bug work starts with reproduction. Refactoring records behavior to preserve.
Features start with requested behavior. Review starts with criteria and source identity.

Expand context when evidence reveals a relevant dependency.
Do not load unrelated archives, dependencies, or all documentation by default.
Keep stable instructions here and temporary progress in current-run records.
