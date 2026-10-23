# LAD adapter templates

This optional pack contains LAD binding guides for six agent environments.

Start with one harness below and the shared [setup procedure](../docs/setup.md). These are inert source templates, not installed configuration. Opening this repository does not activate them. No harness was installed or exercised to author this pack.

| Harness | Source guide | First-version boundary |
| --- | --- | --- |
| Codex CLI | [codex-cli](codex-cli/README.md) | Fresh agents and completion events. Provider and permissions inherit. |
| Codex Cloud | [codex-cloud](codex-cloud/README.md) | Hosted workspaces. Bind only capabilities exposed in the actual task. |
| Claude Code | [claude-code](claude-code/README.md) | Native agents. Nesting and effort depend on installed version. |
| OpenCode | [opencode](opencode/README.md) | Documented v1 configuration schema. Do not apply as v2 configuration. |
| Pi | [pi](pi/README.md) | Manual fresh sessions. Core has no subagent or autonomous continuation. |
| Hermes Agent | [hermes-agent](hermes-agent/README.md) | Native delegation. Background delivery occurs between parent turns. |

## Resolve, copy, pin

1. Record the installed harness version and its configuration precedence without sending model requests.
2. Select models from existing metadata, current provider documentation, and user-confirmed account access. Mark access unknown when unverified.
3. Complete `installation/profile.md` from [the profile template](../templates/installation-profile.md). Bind Orchestrator, all twelve stages, and helpers L/SM/SH/SX.
4. Copy and adapt the selected folder's entire README into `installation/adapter.md` as an identified primary binding section. Record its source and revision.
5. Resolve `{{UPPER_CASE}}` markers before copying native templates outside this pack. Record each destination and revision in the installed guide.
6. For cross-harness work, merge the entire [cross-harness contract](cross-harness.md) and every secondary harness's entire binding README into that same `installation/adapter.md`. Identify each section's harness, source, and revision. Resolve source-relative links to installed paths or source URLs. Copy required native imports outside this pack. Do not leave separate mutable guide imports.
7. Validate syntax, referenced files, model/effort spelling, effective permissions, and configuration precedence statically. Do not probe models through inference.
8. Pin the completed profile, adapter, and required guidance in every run's instruction snapshot. Verify effective native configuration against that binding.

Template markers describe resolution work. They are not valid installed model names. Native configuration must select the exact profile model and native effort. Record unsupported effort as `not supported`, with a deliberate profile decision. Do not silently approximate it.

The Codex [default profile](codex-cli/default-profile.md) preserves the original Sol/Astra/Luna assignments. It is one selectable preset. Harness mechanics and model bindings are separate. Other profiles can choose different providers and models without duplicating stage prompts.

LAD retains twelve stages, four outcomes, recovery, Learning, and the frozen Checker baseline. One top-level stage runs at a time. Planner never delegates. Other stages select the smallest suitable helper tier within explicit user limits and actual host capabilities. LAD adds no command, dispatch, recovery, concurrency, depth, or descendant quotas.

## Cleanup boundary

After setup, a user may explicitly authorize removing the exact `adapter-templates/` source folder or named unused subfolders. First confirm installed guides, imports, and native configuration have no runtime dependency on those folders. Preserve installed native files, active snapshots, run records, evidence, and logs. This pack supplies no deletion script. Cleanup never authorizes deleting another folder.

Changing installation files creates a new revision for future snapshots. It cannot silently change an active run's binding. If native discovery loads mutable configuration, use a revisioned copy or verify the effective configuration before dispatch. Resolve mismatches before dependent work.

## Sources and limits

Each guide names its primary documentation and source revision or review date. The five local harness guides retain October 15, 2026 sources. The Cloud guide uses official documentation reviewed October 22, 2026. Record the actual installed version or hosted surface at setup. These static guides do not establish account access, runtime compatibility, or tested callbacks. No subscription, benchmark, or public report is required.
