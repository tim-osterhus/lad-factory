# LAD with Pi fresh sessions

This guide binds LAD to Pi through explicit manual fresh sessions.

Merge and adapt this entire guide as an identified binding section in `installation/adapter.md`. For cross-harness work, merge the entire primary and secondary guides and entire shared cross-harness contract into that same file. Record each section's source and revision. Resolve all markers and source-relative references. Leave no separate mutable guide imports. Record the exact installed Pi version, profile revision, provider/model IDs, thinking levels, native configuration identities, working directory, and tool/path authority. Copy required native files outside this optional pack before cleanup.

## Manual session binding

Pi's core does not include subagents. This first adapter uses the user to start each fresh stage or helper session and return its artifacts to the owning parent. It does not promise automatic callbacks, unattended stage transitions, or unloaded-session wakeup. Select `interactive` continuation. The twelve-stage workflow and budgets remain intact.

Use [settings.json.template](settings.json.template) only as a resolved native `.pi/settings.json` merge fragment for the selected workspace. For role-specific settings, prefer explicit CLI flags per invocation. Do not repeatedly overwrite a shared config while another worker uses it. Copy [lad-read.md.template](lad-read.md.template) into a deliberately chosen native prompt directory and rename the installed file to `lad-read.md`. Pi discovers `.md` prompt files, not `.md.template` sources. It expands to the file-read instruction and contains no stage logic.

Bind Orchestrator and all twelve stages in `installation/profile.md`. Map Recon, Planner, Manager, Builder, Checker, Fixer, Doublechecker, Troubleshooter, Consultant, Updater, Learning, and Arbiter to their matching lowercase `prompts/<stage>.md` in the pinned instruction root. Orchestrator reads `prompts/orchestrator.md`. Helper tiers L/SM/SH/SX resolve independently and read the current work-order file. A manual handoff does not omit a stage or allocate new counters.

From the declared working directory, start a new session with the exact provider, model, and supported thinking level. For example, after resolving the markers:

```sh
pi --provider '{{PROVIDER_ID}}' --model '{{EXACT_MODEL_ID}}' \
  --thinking '{{NATIVE_THINKING_LEVEL}}' \
  'Read {{ACTUAL_RELATIVE_PINNED_STAGE_PATH}} and follow instructions.'
```

Do not use `--continue`, `--resume`, `--fork`, or an existing session ID for a fresh worker. Resolve the actual relative pinned path from the declared working directory. The first user message contains only that read instruction. Do not use `@file` to append the stage body or task context. Pi's prompt template `/lad-read <path>` is an optional interactive equivalent after verifying its expansion.

## Context, tools, and completion

Pi discovers repository context files and trusted project resources. Inspect AGENTS.md, extensions, skills, and prompt templates for conflicts before dispatch. Extensions run in Pi's process. Enabled tools use the operating-system permissions of that process. A tool allowlist is not path isolation. Record the actual enforcement boundary and audit changed paths. Keep secrets and unrelated provider configuration out of the assignment.

Pi's `--thinking` accepts `off`, `minimal`, `low`, `medium`, `high`, `xhigh`, and `max` in the referenced version. It clamps values to model capabilities. Record the effective level and reject an unapproved clamp or fuzzy model substitution. Use exact provider/model IDs from existing metadata. Resolve unsupported effort explicitly in the profile.

Planner never receives helper work. Other stages may request manual fresh helper sessions within the assigned tiers, disjoint paths, and descendant budgets. The parent integrates their artifacts. All descendants must be terminal and collected before the stage returns. Keep canonical state writes with Orchestrator.

The user records each exact session ID, terminal outcome, current result, examined source, pinned guidance identity, log, and descendant results. For `--print` or `--mode json`, also retain actual process exit status and output. A JSON stream, stopped process, or final summary alone does not establish a stage pass. Unknown launch or write outcomes hold replacement work until reconciled.

## Optional extension boundary

The first-party [Pi Subagent extension](https://github.com/earendil-works/pi-subagent) is a separate opt-in dependency requiring tmux. Its documented child sessions disable nested subagents. Its lifecycle also depends on the spawning Pi session. This adapter neither installs it nor claims the same nesting or continuation behavior as other harnesses. To select it later, record the extension revision, actual commands, result collection, parent lifecycle, and supported depth in a new installed adapter revision. Use explicit manual handoffs for unsupported nesting.

## Installed record and cleanup

Record every model/thinking/native-command identity in `installation/profile.md`. Keep this entire binding and any entire cross-harness contract/other binding sections in the one self-contained `installation/adapter.md`. Copy the installed prompt template outside `adapter-templates/`. Pin both installation records and native config identities in every run. Verify the loaded config still matches those identities before dispatch. Mutable installation changes affect future runs only. Cleanup requires explicit authorization for the exact source folder and must preserve installed files, active sessions, snapshots, logs, and evidence. Parent Goal and heartbeat controls are never delegated.

## Primary sources

Reviewed October 15, 2026: [Pi README](https://github.com/earendil-works/pi/blob/790271cd0218b27068211771704f9e2d42500e9a/packages/coding-agent/README.md), [CLI](https://github.com/earendil-works/pi/blob/790271cd0218b27068211771704f9e2d42500e9a/packages/coding-agent/docs/cli.md), [settings](https://github.com/earendil-works/pi/blob/790271cd0218b27068211771704f9e2d42500e9a/packages/coding-agent/docs/settings.md), and [prompt templates](https://github.com/earendil-works/pi/blob/790271cd0218b27068211771704f9e2d42500e9a/packages/coding-agent/docs/prompt-templates.md). Source revision: `790271cd0218b27068211771704f9e2d42500e9a`, package `@earendil-works/pi-coding-agent`. The former badlogic/pi-mono entrypoint points to this project. No Pi session or model request was run for this pack.
