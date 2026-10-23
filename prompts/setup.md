# Setup

Read `../context/routing.md` relative to this file.
For setup, the instruction and package root are the parent of this file's `prompts/` directory.
Read `context/contracts.md`, `context/transitions.md`, `context/instruction-revisions.md`, `context/continuation.md`, and `docs/setup.md`.

Prepare a run. Do not implement target code or spawn a stage.
Reconcile an existing run through its pinned profile and adapter before considering mutable installation files.
For a new run, require private `installation/profile.md` and self-contained `installation/adapter.md`.
If absent, follow `SETUP.md`.

Check complete owner/helper bindings, native setting precedence, and known capability gaps.
The Orchestrator creates continuation controls only after the selected mode's authorization and capability gates.

1. Determine the inherited host directory, package root, and target workspace.
2. Preserve the original request, criteria, target instructions, and existing user work.
3. Ask only for missing scope, binding, required input, or consequential continuation choices.
4. Record the base Git revision, relevant existing diff/untracked paths, and protected ownership.
5. Record observed capabilities and permissions. Mark unobserved controls unverified.
6. Reconcile any existing current run before writing.
7. For a new run, allocate a unique run ID and prepare canonical records.
8. Record only explicit user limits and actual host or tool limits.
9. Create one versioned guidance snapshot including the installed profile and merged adapter.
10. Record the actual single-line relative read-file prompt for its Orchestrator.

Fill `templates/bootstrap.md` as `run/current/bootstrap.md`.
Record guidance revision/root, path bases, profile revision, adapter revision, and effective bindings.
Choose only authorized fallbacks before pinning.
Keep host-specific paths in private run records.

Prepare goal, state, initial assignment, and evidence index without claiming native execution.
Record the selected continuation mode and its gaps.
Leave native reference/status unverified until observed by the owning Orchestrator.
Preserve target `AGENTS.md` by default.
If target routing is authorized, append one small link after checking for an equivalent entry.

Finish with prepared paths, exact startup prompt, and missing capabilities or inputs.
Do not add a runtime, benchmark, or alternate workflow.
