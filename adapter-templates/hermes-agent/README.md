# LAD with Hermes Agent

This guide binds LAD to Hermes Agent's native delegation and fresh CLI sessions.

Merge and adapt this entire guide as an identified binding section in `installation/adapter.md`. For cross-harness work, merge the entire primary and secondary guides and entire shared cross-harness contract into that same file. Record each section's source and revision. Resolve markers and source-relative references. Leave no separate mutable guide imports. Record the installed version/source revision, profile revision, provider routes, native effort, native profile/config identities, working directory, and actual tool/path authority. Copy required native files outside this optional pack before cleanup.

## Native binding

Use [config.yaml.template](config.yaml.template) as an approved merge fragment for a separately selected non-Planner native Hermes profile. Use [planner-config.yaml.template](planner-config.yaml.template) in a different Planner-only profile. Never launch Planner under the nested-enabled profile. Both fragments require explicit model/provider/effort resolution and contain no credentials. The non-Planner fragment binds one parent and one child route. Its per-model reasoning override applies wherever that model runs. If parent and child use the same model with different efforts, choose separate sessions/configurations instead. Do not overwrite the user's general configuration or configure account providers through this pack.

Bind Orchestrator, Recon, Planner, Manager, Builder, Checker, Fixer, Doublechecker, Troubleshooter, Consultant, Updater, Learning, and Arbiter in `installation/profile.md`. Each stage maps to matching lowercase `prompts/<stage>.md` in the pinned instruction root. Orchestrator reads `prompts/orchestrator.md`. Resolve helpers L/SM/SH/SX separately. Each helper reads its current work-order file.

The initial user message contains only `Read <actual-relative-pinned-stage-or-work-order-path> and follow instructions.` Resolve that path from the worker's actual working directory. Use [entrypoint.md.template](entrypoint.md.template) as that message's source. Keep all model, effort, provider, and permission settings outside the message. For a native delegation call, use that instruction as `goal`, with no appended context. The work-order file contains everything the child needs.

Native `delegation.provider` and `delegation.model` can override the parent route. They are configuration, not assumed model-facing per-call parameters. The documented model-facing task schema does not expose arbitrary per-call provider/model/effort selection. Do not invent those fields. If a stage needs a different binding, start a separate fresh native profile/session with the resolved configuration, or use an explicitly selected existing transport. Do not mutate shared live configuration while any affected worker is running.

For a separate fresh CLI session, the referenced parser supports the following shape, after resolving markers and checking installed help:

```sh
hermes --profile '{{NATIVE_PROFILE_NAME}}' chat \
  --provider '{{PROVIDER_ID}}' --model '{{MODEL_ID}}' \
  --reasoning '{{NATIVE_EFFORT}}' \
  --query 'Read {{ACTUAL_RELATIVE_PINNED_STAGE_PATH}} and follow instructions.'
```

Omit continue/resume flags. On a real terminal this seeds an interactive session. Non-TTY behavior differs, so record the actual process mode and collect its exit status. `agent.reasoning_effort` and provider/model reasoning overrides are version-specific. Verify effective effort without inference probes. Unsupported effort requires a profile decision.

## Delegation and continuation

Native delegation creates fresh child conversations. In the pinned implementation, `role` is a legacy ignored parameter. A child can delegate only when `orchestrator_enabled` is true and its depth is below `max_spawn_depth`. The non-Planner fragment permits nesting through depth 2. Configure finite concurrency and depth within the accepted LAD budget. Native iteration caps do not replace LAD's dispatch and recovery counters.

Launch Planner as a fresh session under its separate Planner-only profile. That fragment sets `orchestrator_enabled: false` and `max_spawn_depth: 1`. It also selects only native `terminal` and `file` toolsets, excluding the delegation tool from Planner itself. Verify the effective tool list contains no delegation or alternative agent-launch tool. Do not inherit the general `hermes-cli` preset or pass toolset overrides that restore delegation. Shell access remains governed by LAD's prohibition on Planner delegation and the recorded command authority. Do not treat a legacy `role: leaf` argument as enforcement.

Current model-facing background delivery occurs only between parent turns. Orchestrator persists the pending stage identity, gives a brief waiting status, and ends its turn without other work. Stage/helper parents may finish independent work permitted by their assignment before ending their turn. Do not imitate Codex's wait API or poll transcripts. A session without a later-result consumer, including one-shot CLI, joins children in the tool call. Record which mechanism actually applies.

For callback mode, verify the precise parent session and delivery consumer. Native subagents do not guarantee durable work across parent process exit, stop, or new-session operations. If no reliable continuation mechanism exists, use `interactive` and require the user to return. This pack installs no scheduler. Only Orchestrator may control an authorized Goal or heartbeat.

Collect exact child/session IDs, terminal status, current result, examined source, pinned guidance revision, log, and every descendant result. A background delivery or child self-report alone is insufficient. Reconcile unknown launches or writes before replacement dispatch and preserve the originating budget ledger.

## Permissions, transports, and installed record

Keep `subagent_auto_approve: false`. Record how refusals are surfaced and handled within existing authority. Toolsets, command approvals, filesystem permissions, and the terminal backend form the real boundary. Writable-path instructions alone do not isolate files. Audit actual changes and do not forward secrets automatically.

The referenced source supports configured provider/ACP routing, including trusted configuration for command/argument selection. These options do not authorize a model to choose arbitrary transport commands. If selecting an existing ACP integration, pin its executable, arguments, configuration, permissions, and completion behavior in the installed guide. Otherwise use the separate-session/manual route above. This pack builds no ACP bridge.

Record native profile and configuration paths/content identities for every stage/helper, including the distinct Planner profile. Keep this entire binding and any entire cross-harness contract/other binding sections in the one self-contained `installation/adapter.md`. Copy required native files outside `adapter-templates/`. Pin both installation records and required native configuration identities in each run. Verify exact loaded bytes before dispatch. Mutable installation edits cannot alter active runs. Cleanup requires explicit user authorization for the exact source folder and preserves installed configurations, active sessions, snapshots, logs, and evidence.

## Primary sources

Reviewed October 15, 2026, source revision `74e7a25c949625479487c009a2fd64d14d5b5c06`: [configuration example](https://github.com/NousResearch/hermes-agent/blob/74e7a25c949625479487c009a2fd64d14d5b5c06/cli-config.yaml.example), [delegation tool](https://github.com/NousResearch/hermes-agent/blob/74e7a25c949625479487c009a2fd64d14d5b5c06/tools/delegate_tool.py), [delegation configuration](https://github.com/NousResearch/hermes-agent/blob/74e7a25c949625479487c009a2fd64d14d5b5c06/tools/delegate_tool_config.py), [native toolset definitions](https://github.com/NousResearch/hermes-agent/blob/74e7a25c949625479487c009a2fd64d14d5b5c06/toolsets.py), and [CLI parser](https://github.com/NousResearch/hermes-agent/blob/74e7a25c949625479487c009a2fd64d14d5b5c06/hermes_cli/_parser.py). The example retains a legacy role comment that contradicts the implementation. Use the implementation's depth-derived capability and record the installed behavior. No Hermes process or model request was run for this pack.
