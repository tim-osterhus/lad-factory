# LAD with Codex CLI

This guide binds LAD stages to Codex CLI's fresh custom agents.

Merge and adapt this entire guide as an identified binding section in `installation/adapter.md`. For cross-harness work, merge the entire primary and secondary guides and shared cross-harness contract into that same file. Record every section's source and revision. Resolve template markers and source-relative references there. Record the installed version, profile revision, native configuration paths, working directory, and authorized read/write roots. Leave no separate mutable guide import. The installed guide must remain usable after the optional pack is removed.

## Native binding

Use [agent.toml.template](agent.toml.template) once per stage or helper identity. Copy resolved files to the explicitly chosen project `.codex/agents/` directory or personal agents directory. Use unique revisioned names such as `lad-r1-checker`. Keep Orchestrator's model and effort in its selected native session configuration. [config.toml.template](config.toml.template) shows a small configuration fragment. Merge only approved settings into an existing configuration. Do not replace unrelated settings.

Select the [default profile](default-profile.md) or resolve another complete profile. The default is source data, not an active native profile. Stage filenames map directly to the shared files: Recon → `prompts/recon.md`, Planner → `prompts/planner.md`, Manager → `prompts/manager.md`, Builder → `prompts/builder.md`, Checker → `prompts/checker.md`, Fixer → `prompts/fixer.md`, Doublechecker → `prompts/doublechecker.md`, Troubleshooter → `prompts/troubleshooter.md`, Consultant → `prompts/consultant.md`, Updater → `prompts/updater.md`, Learning → `prompts/learning.md`, Arbiter → `prompts/arbiter.md`. Orchestrator reads `prompts/orchestrator.md`. Helpers read their assigned work-order file.

In the installed guide, replace those paths with paths inside the run's pinned instruction root. For native collaboration exposing the MultiAgentV2 spawn API, explicitly set `fork_turns="none"` on every stage/helper spawn. Never omit it: the default `"all"` copies parent history. Set the exact resolved model/effort outside the message. Verify the actual installed API/version supports this field. Do not invent it for other spawn APIs. If that API cannot guarantee fresh context, use a separate fresh CLI session or resolve another supported binding before dispatch.

The first user message contains only `Read <actual-relative-pinned-stage-or-work-order-path> and follow instructions.` Compute the relative path from the worker's observed working directory. Do not append task context. Assignment and work-order files carry that context.

Current standalone custom agents require `name`, `description`, and `developer_instructions`. Their `model` and `model_reasoning_effort` override resolved spawn settings. Verify the loaded file matches the profile. Never assume a model requested in prose overrides a conflicting custom agent file.

Custom agents inherit the parent's provider, permissions, and MCP servers. They cannot switch those through a custom agent file. Provider changes require an explicitly configured separate session, covered by the merged cross-harness section of the pinned adapter when applicable. Project-local provider settings may be ignored. Keep provider configuration at its documented native scope and record its identity without secrets.

## Ownership and continuation

Native sandbox and approval settings enforce their documented boundary. LAD's writable-path list is an additional instruction, not a sandbox. Record the actual sandbox, approval policy, writable roots, configuration precedence, and inherited capabilities. Use normal approved permissions. Do not enable bypass or widen roots to make a dispatch succeed.

Planner has no helpers under LAD policy. Non-Planner stages select the smallest suitable helper tier within the pinned profile, explicit user limits, actual host constraints, and disjoint write ownership. Respect native concurrency and depth limits. LAD defines no additional quotas. Descendants must all be terminal and collected before a stage finishes.

Use native completion-event waiting when available. Collect the exact agent ID, terminal state, current result, examined source, pinned guidance identity, log, and descendant results. A final chat message alone does not pass a stage. For a separate `codex exec`, preserve actual process exit status and assigned artifacts as well as JSON events.

`codex exec` checks its Git/trusted-workspace requirement. Add `--skip-git-repo-check` only for a deliberately selected, authorized non-Git workspace recorded in the binding. This skips the repository gate without expanding permissions. Never use permission bypass for this purpose.

Bind `goal`, `heartbeat`, `callback`, or `interactive` only when the actual host supplies that mechanism. CLI installation alone proves no Goal, scheduler, same-chat callback, or unloaded-session wakeup. With `interactive`, the user returns to continue. Delegate no parent Goal or heartbeat controls.

## Installed record and cleanup

Record every stage/helper's native agent name, model, effort, configuration path, and revision in `installation/profile.md`. Keep this entire binding and any cross-harness contract/other binding sections inside the one self-contained `installation/adapter.md`. Copy required native files outside `adapter-templates/` before source cleanup. Retain both installation records in each run's instruction snapshot. Verify effective native settings against the pinned binding and actual configuration precedence. Use revisioned files or content checks where mutable discovery could change that binding. Reconcile uncertain launches before replacement work. Preserve active workers and evidence during recovery. Cleanup requires explicit user authorization for the exact source folder and preserves installed files.

## Primary sources

Reviewed October 15, 2026: [Subagents](https://learn.chatgpt.com/docs/agent-configuration/subagents), [CLI reference](https://learn.chatgpt.com/docs/cli/reference), and [configuration reference](https://learn.chatgpt.com/docs/config-file/config-reference). This template targets the documented standalone-agent TOML format. Record your installed CLI version rather than assuming an older custom-role schema is equivalent. No native invocation or model call was run for this pack.

Freshness reference: [MultiAgentV2 spawn source at 6ae8b8a](https://github.com/openai/codex/blob/6ae8b8aa7c608730d4315d59c5c081897ae02780/codex-rs/core/src/tools/handlers/multi_agents_v2/spawn.rs) defines `fork_turns` and its full-history default. Gate this binding on the installed API rather than transferring its parameters to another harness.
