# LAD Factory

LAD Factory is a Markdown workflow for sequential software development with native Codex agents.

Use it when a specification needs planning, implementation, independent review, repair, and an Arbiter decision against the original goal. Stage instructions live in files. Current assignments and evidence stay readable on disk.

## Start a run

1. Clone or copy this package into a directory your Codex session can read.
2. Start the [setup entrypoint](prompts/setup.md) using its actual path from your host's working directory.
3. Setup prepares `run/current/` from the [templates](templates/README.md), preserving your original criteria and target instructions.
4. Explicitly authorize native goal creation in a separate user instruction, or provide verified native `/goal` evidence. See [setup](docs/setup.md).
5. Start the Orchestrator with setup's recorded single-line prompt for the immutable instruction snapshot.

For a package copied into your host directory as `lad-factory/`, the setup prompt is:

```text
Read lad-factory/prompts/setup.md and follow instructions.
```

Reading the workflow does not authorize a native goal. The Orchestrator verifies the authorized goal before delegating.
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

Checker records expected behavior before examining the change. Doublechecker preserves that review baseline. Arbiter checks every original criterion independently of packet completion.

## Inspect the package

- [Routing](context/routing.md) identifies each role's required context.
- [Shared contracts](context/contracts.md) define ownership, evidence, logs, and bounded recovery.
- [Transition policy](context/transitions.md) covers every stage outcome and finite dispatch limits.
- [Instruction revisions](context/instruction-revisions.md) preserve review guidance and require changed-path audits before acceptance.
- [Nested model selection](context/nested-models.md) defines worker tiers and delegation.
- [Protocol fixture](examples/dry-run/README.md) exercises documented transitions without running native agents.
- [Native pilot plan](examples/native-pilot/README.md) names the required live scenarios. Results are pending.

## Native dependencies and limits

The host must support native goals, fresh contexts, explicit models and efforts, and completion-event waiting. Stage owners use `gpt-6.1-sol`. Only Arbiter uses `gpt-6-astra`. Luna handles bounded nested work.

These files depend on the host to execute those controls. They provide no scheduler, process recovery service, or automatic wakeup after session unload. Run records require a retention and backup policy. [Setup](docs/setup.md) explains capability checks and interrupted-run recovery.

## Sources and license

Stage responsibilities draw on [Millrace v0.21.1](https://github.com/tim-osterhus/millrace/tree/v0.21.1). The layout is informed by Jake Van Clief's Interpretable Context Methodology. [Provenance](docs/provenance.md) records the sources and adaptation boundaries.

Licensed under the [Apache License 2.0](LICENSE).
