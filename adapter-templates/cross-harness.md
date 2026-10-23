# Cross-harness LAD handoffs

Use an existing native CLI, MCP, or ACP integration to assign a bounded LAD invocation to another harness. This guide defines the handoff contract. It supplies no transport daemon, controller, scheduler, or pair-specific bridge program.

Merge this entire contract and the entire primary and selected secondary binding guides into the one self-contained `installation/adapter.md`. Identify each source and revision. Resolve source-relative links to installed native paths or source URLs. Leave no separate mutable guide imports. Copy required native files outside the optional pack and record their paths/revisions. Retain the complete adapter and profile in every affected run's instruction snapshot. Verify effective native settings against the pinned binding and actual configuration precedence. No active invocation may depend on removable templates.

## One assignment across the boundary

Keep the existing LAD assignment, work-order, result, and log formats. A secondary stage receives the canonical assignment through its pinned stage file. A helper receives a separate work-order file written by its owning stage. The first user message contains only `Read <actual-relative-pinned-stage-or-work-order-path> and follow instructions.` Compute that path from the worker's declared working directory. Configuration belongs outside that message. Preserve required input order, especially Checker's baseline freeze before implementation access.

Before launch, the parent records the following in the assignment or work order and installed binding records:

| Record | Required content |
| --- | --- |
| Ownership | Run, invocation, exact parent identity, stage/helper role, disjoint allowed writes, protected paths, existing target changes |
| Execution | Harness executable/integration and version, native agent/profile identity, working directory, read roots, permission enforcement |
| Model | Exact provider route, model ID, supported native effort, effective native configuration, explicit authorized fallback |
| Guidance | Pinned profile revision, adapter revision, instruction root/revision, ordered inputs, examined source identity |
| Constraints | Explicit user limits, actual host concurrency/depth/tool constraints, ordinary permissions |
| Return | Exact result and log paths, artifact paths, process/session/child identity, terminal status and descendant collection method |
| Continuation | Actual parent delivery mechanism, supported wait/turn-end behavior, interruption recovery, or explicit manual return |

Use a fresh worker context. Do not resume a session selected by a familiar name, inherited directory, or last-used-session shortcut. Native agent model configuration does not select another harness. A Claude Agent running a Claude model is distinct from a Codex CLI process. Provider permission, configuration, billing, and context boundaries follow the actual owning harness.

## Launch and collection

1. The parent verifies the assignment, approved authority, pinned bindings, source revision, existing changes, and applicable constraints.
2. The parent records the invocation in dispatch history before launch.
3. The parent launches exactly one identified owner for the assigned paths through the selected native mechanism.
4. The parent records returned process/session/child IDs and where terminal status will be collected.
5. The parent uses supported completion delivery. Orchestrator remains idle in native waiting or yields for the documented callback. Only stage/helper parents may do independent work while helpers run, within ownership and input order.
6. The parent collects actual terminal status and the matching current result, artifacts, source identity, guidance identity, log, and every descendant result.
7. The parent independently audits changed paths and required checks before accepting the result or changing canonical LAD state.

A zero exit code, JSON response, agent summary, transport acknowledgment, or callback alone is insufficient. Match run, invocation, parent, stage, examined source, and pinned guidance against the current assignment. Retain stderr, process exit status, and interrupted or failed attempts. A result copied from an earlier invocation cannot satisfy the current one.

All descendants must be terminal and collected. Non-Planner nesting follows the secondary harness's real capabilities, pinned profile, and explicit user limits. Planner never delegates. Pi's first adapter uses manual fresh-session handoffs. A selected Pi extension that disables nesting does not satisfy nested dispatch automatically. Hermes background completion requires the parent to end its turn when using a later-result consumer. Follow the installed guide's semantics instead of copying another harness's wait API.

## Uncertainty and authority

If launch acknowledgment, writer identity, process status, or write outcome is uncertain, hold overlapping writes and replacement dispatch. Reconcile native process/session records and current artifacts first. Never retry blindly. Recover from the current candidate and accepted stage results, then rerun missing checks. Changing harnesses or restoring a session preserves explicit user limits, ownership, and dispatch history.

The secondary harness cannot expand authority unavailable to the parent. Keep normal approvals and sandboxing. A native shell tool's availability does not authorize all commands it can run. An MCP or ACP connection is not permission to forward credentials, provider accounts, environment secrets, or unrelated context. Use the already configured provider boundary without automatic secret forwarding.

Only Orchestrator writes canonical state, assignment, packets, and accepted guidance. Secondary agents never control the parent's Goal or heartbeat. Their result recommends a route among the existing four outcomes. It does not authorize another stage, changed requirements, or replacement of Checker's frozen baseline. Learning remains a separate candidate process under the shared contract.

## Claude primary → Codex secondary

Example: Claude Code hosts Orchestrator. The selected profile assigns one Builder invocation to Codex CLI. Setup has merged this entire contract and both entire binding guides into the pinned `installation/adapter.md`. The user has authorized the target edits. The assignment declares the exact writable project paths and output directory. No other owner writes those paths.

Before running the command, Claude records the invocation, source revision, existing changes, pinned guidance revision, working directory, output paths, and normal native permissions. Claude checks effective Codex configuration for conflicting provider/model settings and instruction discovery. Any unknown account access remains explicit. Do not call a model to test access.

The following is an operator-reviewed command example, not an installed launcher. Replace every `{{...}}` marker with already resolved values. Create the unique output directory through the ordinary authorized setup procedure. Choose a workspace containing the authorized project and output paths, or resolve the documented native writable-root arrangement first. Do not broaden the sandbox to make missing paths writable.

Resolve `RELATIVE_PINNED_BUILDER_STAGE_PATH_FROM_DECLARED_DIRECTORY` from the directory passed to `--cd`, using `../` segments when needed. Verify that the relative path resolves to the exact pinned Builder file. For `/work/project` and `/work/project/lad-factory/run/current/instructions/rev-01/prompts/builder.md`, send `Read lad-factory/run/current/instructions/rev-01/prompts/builder.md and follow instructions.` The initial prompt never contains an absolute path.

```sh
bridge_output='{{ABSOLUTE_EXISTING_INVOCATION_OUTPUT_DIRECTORY}}'
codex exec \
  --cd '{{ABSOLUTE_DECLARED_WORKING_DIRECTORY}}' \
  --model '{{EXACT_CODEX_MODEL_ID}}' \
  --config 'model_reasoning_effort="{{CODEX_NATIVE_EFFORT}}"' \
  --sandbox workspace-write \
  --json \
  --output-last-message "$bridge_output/codex-last-message.md" \
  'Read {{RELATIVE_PINNED_BUILDER_STAGE_PATH_FROM_DECLARED_DIRECTORY}} and follow instructions.' \
  >"$bridge_output/codex-events.jsonl" \
  2>"$bridge_output/codex-stderr.log"
bridge_exit=$?
printf '%s\n' "$bridge_exit" >"$bridge_output/codex-process-exit.txt"
```

Use a shell context that reaches the exit capture after a failed command. If an enclosing shell uses automatic exit-on-error, handle that explicitly. Preserve the process handle when a native terminal tool returns before process completion, then collect its actual exit before writing the exit record. A timeout or lost handle is an uncertain launch, not permission to start another writer.

This starts a new `codex exec` session. It uses no resume/fork option, permission bypass, new subscription, or additional usage mode. The initial prompt only reads the pinned Builder file. That file loads the current assignment. Model, effort, sandbox, and working directory stay in native flags. Provider identity remains the configured Codex route, verified against the profile. Do not assume Claude's own provider credentials configure Codex.

Codex exec also checks its Git/trusted-workspace requirement. For an intentionally selected, authorized non-Git workspace, add the documented `--skip-git-repo-check` only after recording that workspace decision. This flag skips the repository gate. It does not expand filesystem permissions or authorize a different workspace. Never use permission bypass to defeat the gate.

Codex writes the assigned LAD result and log separately from `codex-last-message.md`. Claude then verifies those artifacts, exact invocation and pinned identities, actual source changes, checks, and descendant collection. Claude records failed/unrun checks and audits allowed writes before taking the next LAD transition. If this were Checker, its pinned stage would require the expectation baseline before any target code or Builder evidence access. The bridge must not attach those materials to the initial prompt or preload them through native memory.

For a foreground process, Claude can remain attached through its native process-completion mechanism. For an already configured callback, record the exact originating Claude session and evidence that delivery resumes it. Without that evidence, save the pending state and use interactive return. This guide does not promise that an exited or unloaded parent resumes automatically.

## Primary sources and scope

The example uses [Codex CLI reference](https://learn.chatgpt.com/docs/cli/reference) flags reviewed October 15, 2026. The [Claude CLI reference](https://code.claude.com/docs/en/cli-reference) describes Claude's own session entrypoints. Each selected adapter records its versioned source and native differences. This pack performs no bridge invocation and claims no runtime qualification for every harness pair.
