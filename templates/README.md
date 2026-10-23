# Current-run templates

Copy these structures into `run/current/` and replace angle-bracket fields.
These are readable record contracts, not an executable schema.
For installation, fill [installation profile](installation-profile.md) under [SETUP.md](../SETUP.md).
Each run retains the installed profile and merged adapter in its versioned guidance snapshot.

| File | Owner | Purpose |
| --- | --- | --- |
| `goal.md` | Orchestrator | Original target and stable criteria |
| `bootstrap.md` | Setup, then Orchestrator | Paths, capabilities, authority, installed binding, and continuation |
| `state.md` | Orchestrator | Active owner, candidate, dispatch history, routes, and evidence |
| `assignment.md` | Orchestrator | One stage's task, ordered inputs, ownership, checks, and outputs |
| `packet.md` | Orchestrator accepts Manager draft | Ordered, independently verifiable work unit |
| `result.md` | Assigned stage | Outcome and evidence without a canonical transition |

Stages draft outputs under `run/current/outputs/<invocation-id>/`.
The Orchestrator accepts scoped drafts into canonical records.
Accepted packets live at `run/current/packets/<packet-id>.md`.
The canonical evidence index is `run/current/evidence.md`.

Use `prompts/setup.md` and `context/instruction-revisions.md` to prepare records and stable guidance.
No template requires an internal native Goal ID the host does not expose.
Apply [continuation policy](../context/continuation.md) to mode-specific fields.
`goal.md` preserves the original specification in every mode.
