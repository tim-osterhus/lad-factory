# Current-run templates

Copy these structures into `run/current/`.
Replace angle-bracket fields with actual values.
These are record contracts, not an executable schema.
For first installation, fill [installation profile](installation-profile.md) under [SETUP.md](../SETUP.md).
That private installed profile and adapter are pinned into each run's instruction snapshot.

| File | Owner | Purpose |
| --- | --- | --- |
| `goal.md` | Orchestrator | Original target and stable criteria |
| `bootstrap.md` | Setup, then Orchestrator | Paths, observed capabilities, selected-mode authorization, and prepared limits |
| `state.md` | Orchestrator | Selected continuation control, active invocation, counters, evidence |
| `assignment.md` | Orchestrator | One stage's task, inputs, ownership, budgets, outputs |
| `packet.md` | Orchestrator accepts Manager draft | Ordered work unit |
| `result.md` | Assigned stage | Outcome and evidence without state transition |

Stages draft outputs in `run/current/outputs/<invocation-id>/`.
The Orchestrator accepts scoped drafts into canonical records.
Accepted packets live in `run/current/packets/<packet-id>.md`.

The canonical evidence index is `run/current/evidence.md`.
Use `prompts/setup.md` to prepare `bootstrap.md` and project-specific copies.
Snapshot guidance and its separate manifest using `context/instruction-revisions.md`.
No template requires an internal native goal ID that the host does not expose.
Apply [continuation policy](../context/continuation.md) to mode-specific fields.
`goal.md` stores the canonical original specification in every continuation mode.
