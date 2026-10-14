# Setup and capability checks

Copy the package into a directory your Codex session can read.
Keep the package root stable during a run.
No package manager, script, or compiled runtime is required.

Normal target-project tools remain available to authorized agents.

The package root must be the agent's working directory for every initial read-file prompt.
Set that directory through native launch settings when supported.
Otherwise start the host task in the package root.

Record the target code workspace separately in the assignment.
Use that target directory for application commands and source paths.
Fresh agents must reach both directories without relying on inherited conversation.

## Confirm the host

| Capability | Required behavior |
| --- | --- |
| Native goal | Create, inspect, and complete a goal with supported native controls |
| Fresh agents | Start every stage and nested worker without inherited conversation context |
| Model control | Set exact model and effort outside the initial prompt |
| Completion events | Wait for the launched agent without periodic status inspection |
| Files | Read assignments and write assigned artifacts in the shared workspace |

For hosts exposing collaboration tools, fresh context is `fork_turns="none"`.
Set `model` and `reasoning_effort` in the spawn call.
Use `collaboration.wait_agent` for mailbox events.

Respect the actual per-call wait limit. Repeat event waits after timeouts without polling.

Mailbox events may include progress, helper results, and other nonterminal messages.
Those events do not permit stage acceptance. Resume the idle event wait.

For hosts exposing goal tools, use `create_goal`, `get_goal`, and `update_goal`.
Starting this workflow authorizes its native goal.
Do not set a token budget unless the user requests one.

The `/goal` command is a supported composer surface in some Codex hosts.
It is not a shell command or a substitute for unavailable goal access.
Verify actual host behavior before relying on a composer command.

Missing controls stop dependent execution.
Explain the missing capability and preserve prepared files.
Do not substitute CLI agent processes, unrelated chats, or a homemade controller.

## Prepare the current run

1. Create `run/current/` and a unique run identifier.
2. Copy the goal and state templates into that directory.
3. Preserve the user's original specification in the goal.
4. Assign stable identifiers to every acceptance criterion.
5. Record the target workspace, instructions, and existing user changes.
6. Start the Orchestrator from the package root with the README prompt.

Use one current run per package copy.
Concurrent goals require separate copies.
Current-run files and generated history directories are ignored by Git.

Ignore rules provide neither backup nor access control.
Save required evidence under the target project's retention policy.

## Interrupted-run recovery

1. Read state and the original goal.
2. Inspect the native goal and recorded agent identifier.
3. Reconcile results against the exact invocation and examined source.
4. Wait for an active agent or explicitly interrupt it before replacement.
5. Record interruption and allocate a new invocation for any restart.
6. Resume within remaining budgets.

Do not replay writes whose external outcome is unknown.
Resolve their outcome before deciding whether to repeat the action.
Preserve the target repository's release and external-action gates.

Files support recovery when the user returns.
They do not guarantee that an unloaded session will wake.
