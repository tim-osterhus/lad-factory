# LAD with Claude Code

This guide binds LAD stages to fresh Claude Code agents.

Merge and adapt this entire guide as an identified binding section in `installation/adapter.md`. For cross-harness work, merge the entire primary and secondary guides and shared cross-harness contract into that same file. Record each section's source and revision. Resolve template markers and source-relative references there. Record the installed version, profile revision, native paths, working directory, allowed writes, and effective permissions. Leave no separate mutable guide imports. Copy required native files outside this optional pack before cleanup.

## Native binding

Create one resolved [agent.md.template](agent.md.template) per stage/helper in an explicitly selected `.claude/agents/` directory. Names must be unique across discovered scopes. A revisioned name such as `lad-r1-checker` prevents accidental reuse. The file's frontmatter selects the exact profile `model` and `effort`. Use [settings.json.template](settings.json.template) only as an approved merge fragment after confirming the installed version supports its freshness control.

Bind Orchestrator plus Recon, Planner, Manager, Builder, Checker, Fixer, Doublechecker, Troubleshooter, Consultant, Updater, Learning, and Arbiter. Each stage reads its matching lowercase `prompts/<stage>.md`, with `doublechecker` and `troubleshooter` spelled exactly. Orchestrator reads `prompts/orchestrator.md`. Helpers L/SM/SH/SX each resolve to their profile model, native effort, and agent identity, then read a current work-order file. Use the run's pinned paths in every dispatch.

The first user message contains only `Read <actual-relative-pinned-stage-or-work-order-path> and follow instructions.` Resolve the relative path from the worker's actual working directory. Pass model, effort, permissions, and fresh-session settings through native configuration. Never place a full stage prompt or task appendix in the wrapper. Preserve Checker input order and freeze its expectation baseline before implementation access.

Use a new agent context. Where the installed version supports it, set `CLAUDE_CODE_FORK_SUBAGENT=0` to disable fork mode and record the effective setting. Current documentation says interactive fork mode defaults on from v2.1.232. Verify the installed version supports the control. Otherwise select a documented fresh agent type or a separate new CLI session. Never infer freshness from an omitted setting. For separate CLI sessions, omit `--resume` and `--continue`. Inspect inherited CLAUDE.md, settings, skills, environment, and managed policy for conflicts. Do not preload implementation into Checker through a memory file or system-prompt append.

## Native limits and completion

The current docs describe per-agent `effort` values `low`, `medium`, `high`, `xhigh`, and `max`, subject to model support. The environment variable `CLAUDE_CODE_EFFORT_LEVEL` overrides agent effort. Model allowlists may substitute another model. Record effective values and reject an unapproved substitution before accepting work. Claude's model field selects a Claude-provider model. It does not launch Codex CLI or make that CLI's provider and sandbox available.

The starter explicitly denies `Agent` and omits it from its tool allowlist. Keep both controls for Planner. For a non-Planner agent permitted to delegate, remove that denial and add `Agent` only within actual host constraints and explicit user limits. Respect the installed version's real concurrency and depth settings. LAD supplies no numeric defaults. `Agent(type)` allowlists restrict main agents, but the nested subagent form ignores the type list. Treat the pinned work order as an additional policy boundary. Do not claim type-level native enforcement for nested workers.

Use `permissionMode: default` and approved native settings. The main session can override a child's mode: `bypassPermissions`, `acceptEdits`, and `auto` propagate despite the child field. Verify and record the effective parent and child permissions before dispatch. Do not infer a restrictive boundary from frontmatter alone. Tool allowlists and denylists do not turn a writable-path instruction into filesystem isolation. Record actual enforcement and audit changed paths. Preserve the user's existing settings and account route. Do not enable permission bypass.

Use native foreground completion or the owning session's supported background event. Record exact agent/session IDs. Noninteractive nested background work can report to the main conversation after its launcher ends. Require the stage to collect every descendant and verify terminal state before returning. A Stop hook or summary alone is insufficient. Match current result, source identity, guidance revision, log, and descendant records.

## Continuation and installed record

Choose `goal`, `heartbeat`, `callback`, or `interactive` from actual host evidence. This pack configures no scheduler or callback. Without a verified same-session wakeup, select `interactive`, save the pending state, and require the user to return. Never delegate parent Goal or heartbeat controls. An uncertain agent identity or launch holds replacement dispatch until reconciled.

Record all stage/helper bindings and native configuration paths/revisions in `installation/profile.md`. Retain that record and this installed guide in every run's instruction snapshot. Check effective settings against the pinned binding and native configuration precedence. Use revisioned files or content checks where mutable discovery could change that binding. Installation edits create a new revision without silently changing an active run. Source cleanup needs explicit user authorization for the exact folder and preserves installed files, snapshots, evidence, and active agents.

## Primary sources

Reviewed October 15, 2026: [subagents](https://code.claude.com/docs/en/sub-agents), [CLI reference](https://code.claude.com/docs/en/cli-reference), and [permissions](https://code.claude.com/docs/en/permissions). This format targets the documented modern 2.1.x frontmatter. Native depth support and defaults vary by version. Record the installed version and supported fields during setup. No agent or inference request was run for this pack.
