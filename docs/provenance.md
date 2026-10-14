# Provenance

These instructions are newly written for this Markdown package.
They adapt stage responsibilities and context-routing ideas.
They do not redistribute an upstream runtime or claim upstream compatibility.

## Millrace responsibilities

Baseline: [Millrace v0.21.1](https://github.com/tim-osterhus/millrace/tree/v0.21.1), revision `f182c46bc68e5ecc1700058e37f0f052305d28ab`.

- [Planning LAD](https://github.com/tim-osterhus/millrace/blob/v0.21.1/docs/graphs/planning-lad.md): specification sufficiency, packet planning, and goal review.
- [Execution LAD](https://github.com/tim-osterhus/millrace/blob/v0.21.1/docs/graphs/execution-lad.md): Builder, Checker, Fixer, Doublechecker, Troubleshooter, Consultant, and Updater.
- [Learning](https://github.com/tim-osterhus/millrace/blob/v0.21.1/docs/graphs/learning-standard.md): evidence review and the smallest supported guidance change.
- [Stage instructions](https://github.com/tim-osterhus/millrace/tree/v0.21.1/src/millrace_ai/assets/skills/stage): role boundaries.

This package uses native Codex controls and sequential packets.
Recon intake, single-stage Learning, model assignments, and file contracts are local choices.
No upstream controller or graph engine is included.

## Interpretable Context Methodology

ICM was created by Jake Van Clief.
Jake Van Clief and David McDermott describe it in the linked paper.

- [ICM repository](https://github.com/RinDig/Interpretable-Context-Methodology/tree/02ba5d85c7871b75c7c702a2d8da6524723d53d4).
- [ICM Architect](https://github.com/RinDig/icm-architect/tree/e16cafe6a664dcf6d787a726b452adba77d913f4).
- [Paper, arXiv:2603.16021v2](https://arxiv.org/abs/2603.16021v2).

Small context routes, explicit contracts, and inspectable handoffs informed this layout.
No upstream code, template text, paper excerpts, or figures are bundled.
Attribution implies neither endorsement nor canonical ICM conformance.

Upstream repository and paper licenses remain distinct from this package's Apache License 2.0.

## Native host references

- [Goals in Codex](https://developers.openai.com/cookbook/examples/codex/using_goals_in_codex).
- [Subagents](https://learn.chatgpt.com/docs/agent-configuration/subagents).

Capability checks remain necessary. Documentation does not prove that every host exposes every control.
