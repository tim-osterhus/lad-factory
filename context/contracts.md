# Shared contracts

## Authority and ownership

`run/current/goal.md` preserves the original target specification and stable criterion identifiers.
Planner may propose necessary detail without changing the target.
The Orchestrator accepts refinements within scope and maps them to the original goal.

A material scope decision requires the user.

Only the Orchestrator writes canonical state, assignment, accepted specification, packets, and evidence index.
Stages write assigned artifacts, their result, and their log.
Project edits require explicit writable paths.

Nested workers receive disjoint paths. Their parent owns integration.
Repository instructions and existing user changes remain authoritative.
Path ownership is an instruction, not a sandbox boundary.
Require the pre-dispatch snapshot and actual changed-path audit in `context/instruction-revisions.md` before acceptance.

## Assignment and evidence

Every stage reads `run/current/assignment.md` from the configured package root.
It names run, invocation, stage, original goal, specification, packet, sources, guidance revision, writable paths, checks, budgets, and outputs.
The assignment contains the task.

Initial prompts contain only `Read <actual-relative-snapshot-stage-path>.md and follow instructions.`
Model, effort, and fresh context are native settings.
Resolve guidance, runtime, and target paths using `context/instruction-revisions.md`.
The assignment must match the loaded immutable instruction revision and manifest.

Read linked sources before acting. Record unavailable inputs honestly.
Chat history is not authoritative state.
Use `templates/result.md` for each result.

Outcomes are `pass`, `findings`, `blocked`, or `error`.
A recommendation does not authorize a transition.
The Orchestrator rejects mismatched, superseded, or incomplete results.
`context/transitions.md` defines every legal route, override, counter, and default limit.
Stage and nested agents do not create, adopt, update, or complete the Orchestrator's native goal.

Evidence identifies commands, working directory, exit status, and examined source.
Dirty-checkout identity includes base revision, diff or content hashes, and relevant untracked files.
Keep failed and unrun checks visible.

Success messages and fixture records are not proof of native execution.

## Finish

Write assigned artifacts and a result following `templates/result.md`.
Create the required UTC log under the assigned invocation directory.
Return the result path, outcome, and unresolved issue.

Affirm that all descendants are terminal and their results are collected.

## Independent review

Checker writes expected behavior before opening the implementation diff.
Its separate baseline records criteria, checks, source identity, and accepted pre-existing issues.
It also records the pinned guidance revision and manifest.
The Orchestrator preserves baseline path and identity through Fixer and Doublechecker.

Fixer cannot replace the baseline.
Doublechecker verifies findings and current packet criteria for regressions.
Changed requirements or an invalid baseline route through Consultant.

New evidence may supplement the baseline without silently rewriting it.

## Budgets and recovery

Apply `context/transitions.md` without inventing routes or resetting used counters.
Assignments carry all applicable finite limits and remaining counters.
Record revised packets and affected dependents before resuming.
Preserve unrelated completed work and the original review basis.
Learning activation follows `context/instruction-revisions.md`.
Budget exhaustion requires the named human decision and leaves the goal incomplete.

## Logs

Every Orchestrator, stage, and nested invocation creates one Markdown log smaller than 5120 bytes.
Use UTC and the exact filename `StageName_HHMM-MMDDYY.md`.
StageName is the stage name. Nested workers use their owning stage's name.

Record the nested worker's specific role in the log body.
Write under `historylog/<run-id>/<invocation-id>/`.
Unique invocation directories prevent minute collisions without changing filenames.

Never overwrite another log. Allocate a new invocation directory if necessary.
Log assignment, outcome, evidence paths, decisions, and unresolved issues.
Omit transcripts, credentials, and secrets.

Parents assign each worker's log directory.

## Lifecycle

One top-level stage runs at a time.
The Orchestrator stays entirely idle and waits for native completion events.
A bounded wait timeout permits another event wait, without status polling or parallel work.

Nested work stays inside the active stage.
Parents collect all nested results before finishing.
Only terminal completion from the recorded active stage owner permits result acceptance after all descendants finish.

After interruption, inspect native goal and agent identity before reconciling disk records.
An active stage must finish or be explicitly interrupted before replacement.
Do not infer completion from a file or launch duplicate work.

No guaranteed idle-session wakeup means no promise of background continuation.

An uncertain spawn identity or native outcome requires a reconciliation hold.
Do not replace work or advance stages until exact invocation, native identity, and outcome are established.
If reconciliation fails, request the specific missing host or human evidence.
