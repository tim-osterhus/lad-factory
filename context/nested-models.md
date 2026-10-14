# Nested model selection

Stage owners use the table in `prompts/orchestrator.md`.
This table applies only to fresh nested workers. Planner never delegates.

| Tier | Model | Effort | Select for |
| --- | --- | --- | --- |
| L | `gpt-6-luna` | `max` | Tightly specified edits, extraction, and checks with concrete inputs and acceptance checks |
| SM | `gpt-6.1-sol` | `medium` | Scoped discovery, general judgment, and independent tasks with clear boundaries |
| SH | `gpt-6.1-sol` | `high` | Coupled implementation, difficult debugging, integration, or conflicting evidence |
| SX | `gpt-6.1-sol` | `xhigh` | Hard root-cause analysis, architecture tradeoffs, or serious adversarial review |

Choose the smallest suitable tier. Use Sol for open exploration beyond a bounded Luna task.
Luna never owns a top-level stage.
No nested worker uses Astra.

Explicitly set model, effort, and fresh context outside the initial prompt.
Custom agent configuration must not silently override these settings.

Stages and nested workers may delegate separable parallel work within host limits.
Assign concrete inputs, disjoint writable paths, acceptance checks, and permitted child tiers.
Nested parents select from these four tiers using the same capability guidance.

Report a task beyond the assigned scope to the owning stage before expanding it.
Avoid manager layers for trivial or inseparable work.

Write each worker's work order to a readable Markdown file.
Include run ID, parent invocation, outputs, log directory, and these shared contracts.
Include the parent's pinned guidance revision, manifest, explicit path bases, and remaining nested budgets.
Worker initial prompts contain only the instruction to read that work-order file.

Parents integrate and verify worker results before finishing.
Record pre-dispatch path state and validate helper changes before integration and acceptance.
Never treat writable-path instructions as permission enforcement.
Every worker logs under its own invocation directory using the owning stage name.
Nested agents never edit canonical goal, state, assignment, or packet records.
