# LAD with OpenCode v1 configuration

This guide binds LAD to the documented OpenCode v1 agent configuration schema.

Merge and adapt this entire guide as an identified binding section in `installation/adapter.md`. For cross-harness work, merge the entire primary and secondary guides and entire shared cross-harness contract into that same file. Record each section's source and revision. Resolve template markers and source-relative references. Leave no separate mutable guide imports. Record the exact installed version and schema before copying native files. OpenCode v2 is a separate compatibility decision. Do not mix its keys with this guide's `agent`, `mode`, and `permission` format.

## Native binding

Merge resolved entries from [opencode.jsonc.template](opencode.jsonc.template) into an explicitly selected native configuration file. The starter uses JSONC accepted by the documented v1 configuration format. Its marker names are setup inputs, not valid model identifiers. Save the thin [agent-prompt.md.template](agent-prompt.md.template) outside this pack and resolve each `{file:...}` path relative to the installed config file.

Create distinct revisioned agent entries for Orchestrator, all twelve stages, and each enabled helper tier. `mode: primary` selects Orchestrator. Stages/helpers use `mode: subagent`, or `mode: all` only when a documented separate main-session invocation is selected. Map Recon, Planner, Manager, Builder, Checker, Fixer, Doublechecker, Troubleshooter, Consultant, Updater, Learning, and Arbiter to matching lowercase `prompts/<stage>.md` files in the pinned instruction root. Orchestrator uses `prompts/orchestrator.md`. Helpers L/SM/SH/SX read their assigned work-order file.

Set each entry's `model` to the exact profile `provider/model` ID. Resolve effort through the documented provider-specific variant or options. The CLI `--variant` flag is provider-specific. It is not a universal reasoning scale. Record `not supported` when a model has no effort control, and settle that profile decision before launch. Do not copy Codex effort names blindly or inherit an accidental primary model.

Start fresh sessions or Task contexts. Do not continue or fork an unrelated session. The initial user message contains only `Read <actual-relative-pinned-stage-or-work-order-path> and follow instructions.` Resolve that path from the worker's actual working directory. Pass model, variant, and agent identity as native settings. The thin system wrapper contains no assignment context or duplicated stage prompt.

## Permissions and completion

The starter asks for edit, shell, and delegation approval. Resolve its policies to approved access without increasing authority. For Planner, set `permission.task` to `deny`. Other stages select the smallest suitable helper tier within the pinned profile, explicit user limits, and actual host constraints. Native Task permissions use ordered pattern rules with the last match winning. Explicit user `@` invocation can bypass a Task type restriction, so reconcile manually launched workers as well.

Foreground `opencode run` auto-rejects unresolved `ask` requests without `--auto`. It cannot present an interactive approval prompt. Before choosing this route, resolve narrowly authorized commands, write paths, and helper identities to native `allow` rules. Keep other access denied or unresolved. If the installed schema cannot express the required narrow access, use an interactive native session for approvals. Do not add broad `--auto` to make the template run.

Record actual tool/path restrictions, writable roots, inherited rules, configuration precedence, and provider route. LAD ownership instructions do not enforce filesystem isolation. Audit actual changes. Avoid `--auto` and any permission broadening intended only to make a launch pass.

Use the installed version's native Task completion or a foreground `opencode run` process. JSON output alone proves no successful stage outcome. Preserve exact session/agent IDs, process exit where applicable, matching current result, source identity, pinned guidance revision, log, and all descendant results. Confirm all descendants are terminal before returning. If native nesting cannot satisfy the profile, use an explicit interactive handoff or resolve a different profile. Do not invent a background callback.

## Continuation and installed record

Bind `goal`, `heartbeat`, `callback`, or `interactive` only to a mechanism verified in the actual host. Neither v1 agent configuration nor this template installs a scheduler. Use `interactive` when the user must return. Keep parent Goal/heartbeat controls out of delegated work. Reconcile uncertain launches before replacements. Recover from the current candidate and accepted results, then rerun missing checks.

Copy the installed prompt import and native configurations outside `adapter-templates/`. Keep this entire binding and any cross-harness contract/other binding sections in the one self-contained `installation/adapter.md`. Record native destinations and revisions in `installation/profile.md` and that adapter. Retain both installation records in each run's instruction snapshot. Check effective settings against the pinned binding and configuration precedence. Use revisioned files or content checks where mutable discovery could change that binding. Source cleanup requires explicit user authorization for the named folder. Preserve installed files, active runs, snapshots, logs, and evidence.

## Primary sources

Reviewed October 15, 2026: [v1 agents](https://opencode.ai/docs/agents/), [v1 CLI](https://opencode.ai/docs/cli/), and [configuration](https://opencode.ai/docs/config/). Source reference: [agents.mdx at 37e3912](https://github.com/anomalyco/opencode/blob/37e3912d8ea5814593b8591bdc85f91cb69949e2/packages/web/src/content/docs/agents.mdx). Reconcile the installed version against that schema. No OpenCode process or inference request was run for this pack.
