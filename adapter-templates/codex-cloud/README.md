# LAD with Codex Cloud

This guide applies the shared LAD methodology to hosted Codex Cloud coding tasks.
It supplies no launcher, pipeline, or native configuration template.
Start with the shared [setup procedure](../../docs/setup.md).

## Install the same LAD workflow

Merge this entire guide into the one self-contained `installation/adapter.md`, with its source and revision.
For cross-harness work, also merge the complete selected guides and [cross-harness contract](../cross-harness.md).
Resolve links to installed paths or source URLs. Keep required native files outside this removable pack.
Retain the adapter, profile, and shared guidance in each accepted instruction revision's snapshot.
Check effective settings against that pinned binding and actual configuration precedence.

Bind Orchestrator and all twelve stages: Recon, Planner, Manager, Builder, Checker, Fixer, Doublechecker, Troubleshooter, Consultant, Updater, Learning, and Arbiter.
Resolve helper tiers L/SM/SH/SX separately. Keep one top-level stage active. Planner never delegates.

Preserve `pass`, `findings`, `blocked`, and `error`, Checker's frozen baseline, and independent review.
Run Learning after two evaluated Fixer/Doublechecker cycles, including a successful second cycle.
Learning writes a separate candidate. Only Orchestrator accepts guidance and activates it at a safe boundary.
Keep each invocation's Markdown log below 5120 bytes. Preserve explicit user limits and actual host concurrency, depth, and tool constraints.

## Bind the capabilities actually exposed

Record the hosted surface, task identity, repository/source revision, observed working directory, writable paths, toolchain, permissions, and available completion mechanism.
Use the exposed fresh-context, model, effort, and wait controls. Local CLI `.codex/agents/*.toml` support does not establish hosted support.

The official [Subagents guide](https://learn.chatgpt.com/docs/agent-configuration/subagents) distinguishes local custom agents from hosted delegation.
It does not establish this account's exact spawn controls, model availability, or supported efforts. Record those as unknown until established.
Resolve only the unknowns needed for the next dependent action. Never silently substitute a model or effort.

Each stage/helper requires a fresh context and a file containing its assignment or work order.
Its initial message contains only `Read <actual-relative-pinned-stage-or-work-order-path> and follow instructions.`
Resolve that path from the worker's observed directory. Keep configuration outside the message and preserve Checker input order.

Use `fork_turns="none"` only if the exposed spawn API documents that field. Do not invent hosted parameters.
If fresh native delegation is unavailable, use a supported fresh-session handoff with explicit artifact return, or gate that stage.
Sequential roleplay in one context cannot replace independent fresh review.

Cloud supports code edits, commands, and tests. Builder and Fixer may run authorized development checks before independent acceptance.
Verify required tools, versions, directories, network destinations, and service access in the selected workspace.
Normal permissions and authorized path audits still apply. Network access or successful checks grant no publishing or external-effect authority.

## Persist work and return to it

In [current Cloud environments](https://learn.chatgpt.com/docs/environments/cloud-environments), new tasks start isolated workspaces from the published prepared filesystem.
Existing tasks retain their own saved files and installed tools. Republished setup changes apply to new tasks.
Saved VM state is recoverable by default for up to seven days after the last turn starts or the task resumes.
Repository skills are available, but local personal skills are not synced. Internet access and network-secret destinations require environment configuration.

The [legacy environment](https://learn.chatgpt.com/docs/environments/cloud-environment) uses container setup/maintenance scripts and different cache, secret, and network behavior.
Its cache speeds setup and is not a backup. Identify the actual surface before applying either guide's assumptions.

Keep source changes, assignments, accepted results, check evidence, and pending work in an authorized durable location.
Use approved source control or export when needed. Native chat/session state and recoverable VM state cannot replace those files.
Reopen the same task to continue its workspace. A new task requires an explicit source/artifact handoff and source-identity check.

Use the actual native completion/wait mechanism, verified callback, or interactive return.
Missing Goal or heartbeat support does not prevent callback or interactive continuation. Never fabricate an API or promise unloaded-task resumption.

Match returned invocation, native session/child identity, examined source, and guidance revision before accepting evidence.
Collect every descendant and confirm terminal status. Hold overlapping writes or replacement launches while an owner or outcome is uncertain.
After interruption, reconcile native status and the current candidate with accepted stage results. Rerun missing checks and resume the shared route.

Official sources above were reviewed October 22, 2026. No Cloud task, installation, account probe, or model request was run to author this guide.
