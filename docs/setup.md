# Setup and capability checks

Use `prompts/setup.md` to prepare project-specific run records.
No package manager, installer script, or compiled runtime is required.
Choose a readable package copy and target workspace. Keep both paths stable during a run.
Use one current run per package copy. Concurrent runs need separate copies.

The package may be inside the target repository or beside it.
Native agents inherit the host working directory. Do not assume a spawn control can change it.
Set application command working directories explicitly to the recorded target workspace.
Resolve initial read-file paths from the actual inherited host directory.
Reading a file does not change that directory.

For a package in the host directory's `lad-factory/` subdirectory, start setup with exactly:

```text
Read lad-factory/prompts/setup.md and follow instructions.
```

When the host directory is the package root, use `Read prompts/setup.md and follow instructions.`
For a sibling package, instantiate its actual relative path, including `../` segments as needed.
Initial stage prompts must use relative paths. Never send a placeholder or absolute prompt path.
Setup records the actual Orchestrator snapshot prompt for the user.

## Continuation mode and authorization

Apply the shared [continuation policy](../context/continuation.md).
Select native Goal mode or the native same-chat heartbeat fallback.
Record explicit user authorization for the selected mode. Reading workflow files alone supplies neither authorization.
For Goal mode, give a separate instruction such as:

```text
Create a native goal for the original target specification and acceptance criteria in the prepared run/current/goal.md, and execute that LAD Factory run.
```

Resolve that goal path through the configured package root.
Alternatively, use a verified native `/goal` composer command and record its observed response.
The composer surface is host-dependent. It is not a shell command.
Do not set a native token budget unless the user requests one.

For heartbeat mode, explicitly authorize recurring work in the owning chat, for example:

```text
Execute the prepared LAD run using one native recurring heartbeat in this chat. Preserve its original criteria and budgets, and stop that heartbeat at closure, cancellation, or a recorded human-input/budget hold.
```

The Orchestrator verifies host scheduling, owner binding, and safe idle-chat resumption before creating or reusing the heartbeat.
Use the shared policy's concise scheduler prompt and lifecycle rules.
Goals are not a required capability in heartbeat mode. Existing active Goal conflicts still require reconciliation.

## Observed capability gate

| Capability | Evidence required before dependent execution |
| --- | --- |
| Selected continuation mode | Goal: supported lifecycle controls and observed owner/objective binding. Heartbeat: native scheduler, same-chat binding, safe idle resumption without overlapping controllers |
| Fresh agents | Actual support for fresh context on stage and nested dispatch |
| Model control | Native settings accept the fixed stage model and reasoning effort |
| Completion events | Native event/mailbox wait for launched identities |
| Files and permissions | Observed access to required inputs and assigned writes in package and target |

Record observations, tool names, and limitations. Never infer capabilities from a filename or documentation alone.

A supported fresh-context control may be `fork_turns="none"` with model and effort set outside the prompt.
For collaboration hosts, use `collaboration.wait_agent` for mailbox events.
Respect the actual per-call wait limit. Repeat event waits after timeouts without status polling.
Progress and helper events do not permit stage acceptance.

Missing common or selected-mode controls stop dependent execution. Preserve prepared files and name the missing capability.
If neither continuation control is available, report that the user must resume manually without promising background continuation.
Do not substitute CLI agent processes, unrelated chats, or a custom controller.

## Prepared records

Setup fills `run/current/bootstrap.md`, goal, state, assignment, and an empty evidence index.
It preserves the original specification, stable criteria, target instructions, path bases, and pre-existing user work.
Setup copies the default finite limits from `context/transitions.md` unless the user supplied other finite limits.
Setup preserves model assignments. It never resets counters on an existing run.

Create an immutable guidance snapshot and separate path/hash manifest using `context/instruction-revisions.md`.
The first Orchestrator prompt reads that snapshot. Later stage prompts read the same pinned revision until an accepted boundary.
Package guidance and target source identities remain separate.

Preserve the target's `AGENTS.md` byte-for-byte by default.
Only when the user authorized target routing, append one small link to this package's routing entrypoint.
Check for an existing equivalent link first. Never replace target instructions or duplicate the addition.

Current-run files and generated history directories are ignored by Git.
Ignore rules provide neither backup nor access control.
Use the target project's retention and backup policy for required evidence.

## Interrupted-run recovery

Read canonical state and original goal, then reconcile the saved continuation control and recorded agent identity under the shared policy.
Reconcile results against the exact invocation, instruction revision, and examined source.
Wait for an active stage or explicitly interrupt it before replacement.
Record interruption and preserve its spent attempt before a new invocation.
Resume only within the remaining limits and hold guards in `context/transitions.md`.

Do not replay writes whose external outcome is unknown.
Resolve their outcome before deciding whether to repeat the action.
Preserve the target's release and external-action gates.
Files support recovery when the user returns. Scheduler availability alone does not prove unloaded-session wakeup.
