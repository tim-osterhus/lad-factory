# LAD Factory

LAD Factory is a Markdown workflow for sequential software development with native Codex agents.

Use it when a specification needs planning, implementation, independent review, repair, and an Arbiter decision against the original goal. Stage instructions live in files. Current assignments and evidence stay readable on disk.

## Start a run

1. Clone or copy this package into a directory your Codex session can read.
2. Start the [setup entrypoint](prompts/setup.md) using its actual path from your host's working directory.
3. Setup prepares `run/current/` from the [templates](templates/README.md), preserving your original criteria and target instructions.
4. Select and explicitly authorize native Goal mode, or one same-chat recurring heartbeat when Goals are unavailable or not desired. See [setup](docs/setup.md).
5. Start the Orchestrator with setup's recorded single-line prompt for the immutable instruction snapshot.

For a package copied into your host directory as `lad-factory/`, the setup prompt is:

```text
Read lad-factory/prompts/setup.md and follow instructions.
```

Reading the workflow authorizes neither a native Goal nor recurring work. The Orchestrator verifies the selected control before delegating.
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

The [Orchestrator](prompts/orchestrator.md) starts one stage at a time and waits idle for completion. Stages may use fresh nested agents for separable work. Planner works alone.

Checker freezes expected behavior before inspecting any target implementation or Builder evidence. Doublechecker preserves that review baseline. Arbiter checks every original criterion independently of packet completion.

## Inspect the package

- [Routing](context/routing.md) identifies each role's required context.
- [Shared contracts](context/contracts.md) define worker ownership, evidence, logs, and assigned limits.
- [Continuation policy](context/continuation.md) defines Goal and heartbeat authorization, waiting, recovery, and closure.
- [Transition policy](context/transitions.md) covers every stage outcome and finite dispatch limits.
- [Instruction revisions](context/instruction-revisions.md) preserve review guidance and require changed-path audits before acceptance.
- [Nested model selection](context/nested-models.md) defines worker tiers and delegation.
- [Protocol fixture](examples/dry-run/README.md) exercises documented transitions without running native agents.

## Native dependencies and limits

The host must support fresh contexts, explicit models and efforts, completion-event waiting, and the selected native continuation control. Stage owners use `gpt-6.1-sol`. Only Arbiter uses `gpt-6-astra`. Luna handles bounded nested work.

These files depend on the host to execute those controls. The heartbeat fallback uses the host's verified scheduler and same-chat binding. These files provide no scheduler or process recovery service. Unloaded-session wakeup and Cloud compatibility require actual host evidence. Run records require a retention and backup policy. [Setup](docs/setup.md) explains capability checks and interrupted-run recovery.

## Sources and license

Stage responsibilities draw on [Millrace v0.21.1](https://github.com/tim-osterhus/millrace/tree/v0.21.1). The layout is informed by Jake Van Clief's Interpretable Context Methodology. [Provenance](docs/provenance.md) records the sources and adaptation boundaries.

Licensed under the [Apache License 2.0](LICENSE).
