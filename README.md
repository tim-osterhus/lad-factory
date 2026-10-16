# LAD Factory

LAD Factory is a Markdown workflow for sequential software development with native coding agents.

Use it when a specification needs planning, implementation, independent review, repair, and an Arbiter decision against the original goal. Stage instructions live in files. Current assignments and evidence stay readable on disk.

## Install, then start a run

1. Clone or copy this package into a directory your host session can read.
2. Follow [SETUP.md](SETUP.md) to discover available bindings and prepare a private installation profile and selected adapter.
3. Start [run setup](prompts/setup.md) using its actual path from the host's working directory.
4. Run setup prepares `run/current/`, preserves your criteria and target instructions, and pins the installation files into an immutable snapshot.
5. Start the Orchestrator with setup's recorded single-line prompt after resolving the selected mode's execution gates.

For a package copied into your host directory as `lad-factory/`, the installation prompt is:

```text
Read lad-factory/SETUP.md and follow instructions.
```

Installation recommends model bindings from role needs, permitted model metadata, and your quality, cost, speed, and privacy priorities.
It inspects existing metadata without model calls or benchmarks. Unknown capabilities remain explicit execution gates.

Reading the workflow authorizes neither a native Goal nor recurring work. The Orchestrator verifies the selected controls before delegating.
Model, reasoning effort, and fresh context are agent settings. Every initial stage prompt only reads its pinned stage file. The assignment carries the work.

## Arbiter closure

```text
Recon for existing code -> Planner -> Manager
  -> Builder -> Checker -> Updater -> next packet
                 -> Fixer -> Doublechecker
After two evaluated Fixer cycles: Learning, then the pending route
Unresolved review: Troubleshooter -> Consultant when needed
All packets complete -> Arbiter -> closure or scoped remediation
```

The [Orchestrator](prompts/orchestrator.md) starts one stage at a time and uses its adapter's completion wait or authorized callback yield.
Interactive mode records when you must return to resume. Stages may use fresh helpers for separable work. Planner works alone.

Checker freezes expected behavior before inspecting any target implementation or Builder evidence. Doublechecker preserves that review baseline. Arbiter checks every original criterion independently of packet completion.

## Inspect the package

- [Routing](context/routing.md) identifies each role's required context.
- [Shared contracts](context/contracts.md) define worker ownership, evidence, logs, and assigned limits.
- [Continuation policy](context/continuation.md) defines Goal, heartbeat, callback, and interactive resumption, authorization, recovery, and closure.
- [Transition policy](context/transitions.md) covers every stage outcome and finite dispatch limits.
- [Instruction revisions](context/instruction-revisions.md) preserve review guidance and require changed-path audits before acceptance.
- [Nested model selection](context/nested-models.md) defines helper capability tiers and delegation. Your profile binds their models and efforts.
- [Protocol fixture](examples/dry-run/README.md) exercises documented transitions without running native agents.

## Installed bindings and limits

The optional [adapter source pack](adapter-templates/README.md) contains Codex CLI, Claude Code, OpenCode, Pi, and Hermes Agent starters.
Its [cross-harness guide](adapter-templates/cross-harness.md) describes explicit transport bindings and their limits.
The Codex CLI source supplies the shipped Sol/Astra/Luna defaults. Your installed profile may choose other permitted models.

Setup merges all selected binding guides into self-contained `installation/adapter.md` and writes `installation/profile.md`.
Cross-harness installations include the full shared cross-harness contract in the same pinned adapter file.
Required native files are copied outside the source pack. You may then remove the entire optional `adapter-templates/` folder.
Keep the folder to reconfigure later, or deliberately restore the needed source version. Setup never deletes it automatically.

The host must provide fresh contexts, effective model settings, exact-owner completion, and the selected continuation mechanics.
Native configuration can override requested settings. Provider, permission, and tool inheritance follow the actual host.

Model IDs alone do not enable another harness. No universal bridge, scheduler, or recovery service is included.
Unloaded-session resumption requires actual evidence. Run records require retention and backup.
[Run setup](docs/setup.md) explains execution gates and interrupted-run recovery.

## Sources and license

Stage responsibilities draw on [Millrace v0.21.1](https://github.com/tim-osterhus/millrace/tree/v0.21.1). The layout is informed by Jake Van Clief's Interpretable Context Methodology. [Provenance](docs/provenance.md) records the sources and adaptation boundaries.

Licensed under the [Apache License 2.0](LICENSE).
