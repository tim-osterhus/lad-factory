# Shared worker contracts

## Authority and ownership

`run/current/goal.md` preserves the original target specification and stable criterion identifiers.
Planner may propose necessary detail. Only the Orchestrator accepts refinements within the original scope.
A material scope decision requires the user.

Only the Orchestrator writes canonical state, assignment, accepted specification, packets, and evidence index.
Stages write assigned artifacts, their result, and their log.
Project edits require explicit writable paths. Preserve repository instructions and existing user work.
Path ownership is an instruction, not a sandbox boundary.

Parents record pre-dispatch path state and audit actual changes before accepting worker outputs.
Assignments supply the audit roots, snapshot, protected paths, exclusions, and permitted writes.
Workers report actual changes and unexpected paths without deleting, resetting, or overwriting protected work.

The Orchestrator independently checks aggregate changes under its controller policy.
Nested parents load `context/instruction-revisions.md`'s changed-path audit section when preparing and accepting helper work.

## Assignment and immutable guidance

Read `run/current/assignment.md` from the package root recorded in bootstrap.
It names run, invocation, stage, goal, specification, packet, ordered inputs, writable paths, checks, budgets, and outputs.
It also supplies source metadata, instruction revision, manifest identity, path bases, and pre-dispatch snapshot.

Reject missing or mismatched assignment identity. Record unavailable inputs honestly.

Initial prompts contain only `Read <actual-relative-snapshot-stage-path>.md and follow instructions.`
Model, effort, and fresh context are native settings.

Verify loaded guidance bytes against the assigned immutable revision and manifest. Never edit an active snapshot.
Guidance paths use that instruction root. Runtime paths use the recorded package root.
Target paths use the assigned target workspace. Reading a file never changes the working directory.

Read cited inputs in the owning stage's required order, including embedded appendices.
Generic preloading never overrides that order. Chat history is not authoritative state.

## Evidence and outcomes

Use the pinned `templates/result.md` for each result.
Outcomes are `pass`, `findings`, `blocked`, or `error`.

Use `findings` for inspectable defects or deficient planning and `error` for recoverable execution failures.
Use `blocked` only when progress requires human input, authority, protected-work resolution, or an approved budget decision.
Show why already-authorized retrieval, checks, or bounded repair cannot resolve the obstacle.

An exhausted bounded diagnosis with no safe actionable route also requires a Human hold.
Do not label ordinary access retrieval or a repairable environment failure human-only.

A recommendation never authorizes a transition or additional budget.
The Orchestrator validates blocker evidence and owns routes, counters, holds, and acceptance.
Stage and nested agents never create, adopt, update, complete, or disable any Goal or heartbeat.
Do not replay an external action with an unknown outcome.

Evidence identifies commands, working directory, exit status, and examined source.
Dirty-checkout identity includes base revision, diff or content hashes, and relevant untracked files.
Keep failed and unrun checks visible. Assignment metadata is not proof of examined source.

## Independent review

Checker derives expectations only from the original goal, specification, and requirement-side packet inputs.
Checker follows this prohibition:

Do not read, search, or inspect any target application code, code excerpts, diffs, implementation-derived tests, or Builder evidence until you have written and frozen your expectations baseline.

Defer embedded implementation appendices and evidence until after freeze.
Before freeze, record supplied source identity as assignment metadata without inspecting that source.
Include only pre-existing exceptions already supplied on the requirement side.
Record criteria, expected behavior, required checks, pinned guidance revision, and manifest identity in the baseline.
Freeze the baseline path and identity before implementation access.

After freeze, verify actual source identity and record newly discovered pre-existing issues as separate observations.
Never silently rewrite the baseline to accommodate implementation or new observations.

The Orchestrator preserves the baseline through Fixer and Doublechecker.
Fixer cannot replace it. Doublechecker checks findings and current packet criteria for regressions.
Changed requirements or an invalid baseline require Consultant review.

## Assigned limits and nested work

Use the assignment's applicable finite limits and used/remaining counters. Never reset usage or invent routes.
Separate this invocation's reserved dispatch/replacement debits from capacity for future invocations.
Zero future capacity does not revoke an already-reserved invocation. It forbids another dispatch under that cap.

Report attempted repairs and check usage, including failed or interrupted attempts.

One top-level stage runs at a time. Nested work stays inside the active stage.
Planner never delegates. Other stages load `context/nested-models.md` when using helpers.

Parents assign disjoint paths, pinned guidance, outputs, log directories, and remaining descendant budgets.
Parents persist child debits before launch and integrate audited helper results.
Parents collect every descendant result and confirm all descendants are terminal before finishing.
Never dispatch a replacement while an owner is active or its identity/outcome is uncertain.

Learning writes only a separate candidate. It cannot change guidance, snapshots, baseline, target code, counters, or pending route.
The Orchestrator owns candidate acceptance and activation under its controller policy.

## Finish and logs

Write assigned artifacts, the result, and one Markdown log smaller than 5120 bytes.
Every Orchestrator, stage, and nested invocation logs under `historylog/<run-id>/<invocation-id>/`.
Use UTC and the exact filename `StageName_HHMM-MMDDYY.md`.
Nested workers use their owning stage's name and record their specific role in the log body.

Unique invocation directories prevent collisions. Never overwrite another log.
Log assignment, outcome, evidence paths, decisions, and unresolved issues. Omit transcripts, credentials, and secrets.

Return the result path, outcome, unresolved issue, and confirmation that all descendants are terminal and collected.
