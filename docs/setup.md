# Run setup and capability checks

First follow [installation setup](../SETUP.md) to prepare the private profile and selected host adapter.
Then use `prompts/setup.md` for each run. No installer program or compiled runtime is required.
Choose stable package and target paths. One package copy holds one current run.
Concurrent runs require separate copies.

The package may be inside the target repository or beside it.
Native agents inherit their host directory unless the installed adapter establishes another control.
Set application command working directories explicitly to the recorded target workspace.
Resolve initial read-file prompts from the actual inherited directory. Reading a file never changes that directory.

For a package in the host directory's `lad-factory/` subdirectory, initialize a run with:

```text
Read lad-factory/prompts/setup.md and follow instructions.
```

At the package root, use `Read prompts/setup.md and follow instructions.`
For a sibling package, instantiate its actual relative path, including `../` segments.
Initial stage prompts must contain one actual relative read-file instruction, without placeholders or appended context.

## Installed binding and continuation

For a new run, read `installation/profile.md` and the self-contained `installation/adapter.md`.
For an existing run, read their pinned snapshot copies before considering mutable installation changes.
The adapter contains the complete primary guide, every selected secondary guide, and the full shared contract for cross-harness installations.
These are identified sections in one file with resolved paths, not imports from separate mutable guides.

Check all owner/helper bindings, effective native configuration identities, and authorized fallback triggers.
No silent model substitution is allowed. Select any explicitly authorized fallback during run setup and pin the effective binding.
Changed mutable installation files never alter an active run.

Apply [continuation policy](../context/continuation.md) using the installed adapter's actual controls.
Select Goal, heartbeat, callback, or interactive mode without changing stage responsibilities.
Reading files alone authorizes neither a Goal nor recurring work.

An explicit native Goal request may refer to the prepared original specification and criteria in `run/current/goal.md`.
A recurring-task request must authorize one native heartbeat in the owning session and its closure/hold cleanup.
Do not set a token budget unless the user requests one.
Callback yield requires exact owner delivery evidence. Interactive mode explicitly requires the user to return.

## Execution gates

| Capability | Evidence required before dependent execution |
| --- | --- |
| Selected continuation mode | Actual lifecycle/owner binding or documented callback delivery and verified resume mechanics. Interactive mode records user-return limitation |
| Fresh agents | Actual adapter support for fresh stage and helper contexts. |
| Model control | Effective model/effort settings and native config identities match the pinned profile. |
| Completion | Exact owner terminal signal and native event wait or authorized yield/resume mechanism. |
| Files and permissions | Observed access to required reads and assigned writes in package and target. |

Classify evidence as observed, documented, user-confirmed, or unknown, with dates and limitations.
Documentation alone does not establish current runtime access or automatic resumption.
Installation may finish without runtime proof. Missing controls stop only dependent execution.
Do not run trial inference, benchmarks, calibration, or compatibility probes to complete installation.
Do not substitute unrelated chats, unsupported CLI processes, or a custom controller.

## Prepared records

Setup fills bootstrap, goal, state, assignment, and an empty evidence index under `run/current/`.
Preserve the original specification, stable criteria, target instructions, path bases, and existing user work.
Copy finite limits from `context/transitions.md` unless the user supplied other finite limits.
Never reset counters on an existing run.

Create an immutable instruction snapshot and separate manifest under [instruction revisions](../context/instruction-revisions.md).
Include the installed profile and complete merged adapter. Verify separate native configuration identities before dispatch and acceptance.
Required installed/native files must exist outside the optional source folder.
The first Orchestrator prompt and every stage read pinned guidance.
Keep guidance/profile identity separate from target source identity.

Preserve target `AGENTS.md` byte-for-byte by default.
When the user authorized target routing, append one small link after checking for an equivalent existing entry.
Never replace target instructions or duplicate the link.

Private installation files, current-run records, and generated history directories are ignored by Git.
Ignore rules provide neither backup nor access control. Apply the target's retention and backup policy.

## Interrupted-run recovery

Read canonical state and original goal. Reconcile the saved continuation control and exact owner under the pinned adapter.
Validate results against the invocation, guidance/profile revision, manifest, and examined source.
Wait for active work or explicitly interrupt it before replacement.
Record interruption and preserve its spent attempt before a new invocation.
Resume only within remaining limits and hold guards in `context/transitions.md`.

Do not replay external writes with unknown outcomes. Verify the outcome before deciding whether to repeat the action.
Preserve target release and external-action gates.
Files support recovery when the user returns. Scheduler presence alone does not prove unloaded-session wakeup.
