# Setup

Read `../context/routing.md` relative to this file.
For setup, the instruction root and package root are the parent of this file's `prompts/` directory.
Read `context/contracts.md`, `context/transitions.md`, `context/instruction-revisions.md`, `context/continuation.md`, and `docs/setup.md` from that root.

Prepare a run. Do not implement target code or spawn a stage.
Leave continuation-control creation to the owning Orchestrator after the selected mode's explicit authorization and capability gates.

1. Determine the actual inherited host working directory and this package root.
2. Identify the target workspace and preserve its original user request and acceptance criteria.
3. Ask only for missing target, specification, scope, or selected-mode authorization under `context/continuation.md`.
4. Read target instructions and record the full declared target/package inventory, content identities, ownership, and explicit exclusions.
5. Record observed native capabilities and file permissions. Mark unobserved controls unverified.
6. If `run/current/` exists, reconcile it before writing. Preserve active work, original criteria, counters, and recorded native identities.
7. For a new run, allocate a unique run ID and fill canonical records from the templates.
8. Copy the finite default limits from `context/transitions.md`, or the user's explicit finite limits.
9. Create and verify the immutable guidance snapshot and its separate manifest.
10. Record the actual single-line relative read-file prompt for that snapshot's Orchestrator.

Fill `templates/bootstrap.md` with the observed paths, capabilities, permission evidence, authority, and prepared budgets.
Save it as `run/current/bootstrap.md`.
Also record the active instruction root, revision, manifest, and exact startup prompt.
Paths inside private run records may be host-specific. Do not copy them into public package guidance.

Prepare goal, state, initial assignment, and evidence index without claiming verified native execution.
Record the selected mode. Leave its native reference/status unverified until the owning Orchestrator observes and binds the actual control.
Do not replace or alter an existing target `AGENTS.md` by default.
If the user authorized adding routing, append one package-routing link only after checking for an equivalent existing entry.

Finish with prepared record paths, the exact startup prompt, and missing capabilities or required inputs.
No new runtime, installer, model-selection system, or alternate workflow is part of setup.
