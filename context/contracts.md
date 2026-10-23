# Shared worker contracts

## Authority and ownership

`run/current/goal.md` preserves the original specification and stable criterion identifiers.
Planner may propose necessary detail. The Orchestrator accepts refinements within the original scope.
A material product or scope decision requires the user.

Only the Orchestrator writes canonical state, assignment, accepted specification, packets, and evidence index.
Stages write assigned artifacts, their result, and their log.
Project edits require assigned writable paths. Preserve target instructions and existing user work.
Path ownership is an instruction, not a sandbox boundary.

Parents record the base Git revision and relevant existing work before dispatch.
They inspect actual diffs, relevant untracked paths, and ignored invocation outputs before accepting results.

Protect known canonical run records, the frozen baseline, and active guidance used by the invocation even when Git ignores them.
Retain scoped before versions or content identities in parent-owned `run/current/control/<invocation-id>/`, separate from worker outputs and explicit parent bookkeeping updates.
Normally exclude dependencies, caches, and build outputs unless relevant to the task.
Investigate unexpected paths without deleting, resetting, or overwriting user work.
See `context/instruction-revisions.md` for guidance stability and change review.

## Assignment and guidance

Read `run/current/assignment.md` from the package root recorded in bootstrap.
It names the run, invocation, stage, goal, specification, packet, ordered inputs, writable paths, checks, and outputs.
It records source identity, guidance revision, path bases, effective owner binding, and relevant existing work.
Delegating stages load the pinned installation files. Other stages receive their binding in the assignment.

Reject mismatched invocation or stage identity. Retrieve unavailable inputs through already-authorized means.
Initial stage messages contain only `Read <actual-relative-pinned-stage-path>.md and follow instructions.`
Substitute the real path. Set model, effort, and fresh context through native controls outside that message.
Use the pinned adapter's supported controls. Never silently substitute models or ignore native setting precedence.

Use the assigned versioned guidance throughout the packet. Never edit an active snapshot.
Guidance paths use its instruction root. Runtime paths use the recorded package root.
Target paths use the assigned target workspace. Reading a file never changes the working directory.

Read cited inputs in the stage's required order, including embedded appendices.
Generic preloading and chat history never override that order or canonical records.

## Evidence and outcomes

Use the pinned `templates/result.md`.
Outcomes are `pass`, `findings`, `blocked`, or `error`.
Use `findings` for inspectable defects or deficient planning.
Use `error` for execution failures that need diagnosis or repair.
Use `blocked` only for human dependence defined in `context/transitions.md`.
Show why authorized retrieval, checks, or repair cannot resolve the obstacle.

The Orchestrator validates evidence and owns routes and acceptance.
A recommendation cannot grant new scope or authority.
Stages and helpers never control Goals, heartbeats, or run resumption.
Unknown external outcomes require reconciliation before replay.

Keep handoffs small and inspectable:

- Invocation and examined source identity.
- Actual change or diff, including relevant untracked paths.
- Checks with command, working directory, status, and relevant output.
- Findings tied to criteria, unresolved issues, and the proposed route.

Provide an evidence index and targeted supporting evidence to reviewers.
Retain raw evidence only when useful. Transcript exports, full environment archives, and command preauthorization are not required.
A summary never substitutes for the source or check evidence it describes.

Failed and unrun checks stay visible. Assignment metadata does not prove examined source.
Missing logs or paperwork alone do not invalidate code. Regenerate missing check evidence when needed.

## Independent review and development checks

Builder and Fixer may run appropriate development checks within their assigned scope and existing permissions.
Independent review does not prohibit self-testing.
Edit/test authority, independent acceptance, and merge/publish/deploy or other external-action authority are separate.

Checker derives expectations from the original goal, specification, and requirement-side packet inputs.
Checker follows this prohibition:

Do not read, search, or inspect any target application code, code excerpts, diffs, implementation-derived tests, or Builder evidence until you have written and frozen your expectations baseline.

Defer implementation appendices and evidence until after freeze.
Before freeze, record supplied source identity as metadata without inspecting that source.
Record criteria, expected behavior, required checks, guidance revision, and requirement-side pre-existing exceptions.
Before implementation access, freeze the baseline's exact bytes and record its path and SHA-256 in a separate freeze artifact.
The baseline must not contain its own digest. The Orchestrator verifies and pins the freeze artifact's expected digest in canonical state before downstream dispatch.

After freeze, verify actual source identity and record newly discovered pre-existing issues separately.
Never rewrite the baseline to accommodate the implementation.
Preserve it through Fixer and Doublechecker.

Before accepting any worker allowed near the baseline, compare its current SHA-256 with the parent's retained expected value.
This includes Fixer, Doublechecker, Troubleshooter, and Updater. Preserve mismatch evidence, reject the tampered basis, and route through Consultant to fresh Checker review.
Never rewrite the frozen baseline or accept a worker-supplied replacement digest.

Doublechecker checks findings and the full current packet criteria for regressions.
Changed requirements or an invalid baseline require Consultant review and an accepted new review basis.

## Execution and nested work

One top-level stage runs at a time. Nested work stays inside that active stage.
Planner works alone. Other stages use `context/nested-models.md` when delegating.

Parents assign concrete work, disjoint paths, outputs, logs, and applicable explicit user or host limits.
Parents integrate helper results and verify actual changes.
Collect every descendant result and confirm every descendant is terminal before finishing.
Never replace an active or uncertain owner or overlap writers.

Enforce explicit user limits and actual host concurrency and tool limits.
Do not invent default command, duration, dispatch, nesting, recovery, or remediation limits.
Dispatch history records ownership and outcomes for recovery. It is not a capacity ledger.
Two evaluated Fixer/Doublechecker cycles trigger Learning, including a successful second cycle.
This trigger controls routing, not spent capacity.

Learning writes a separate candidate only.
It cannot change active guidance, baselines, target code, canonical state, or the pending route.
The Orchestrator accepts and activates candidates only at a safe boundary.

## Finish and logs

Write assigned artifacts, the result, and one Markdown log smaller than 5120 bytes.
Every Orchestrator, stage, and nested invocation logs under `historylog/<run-id>/<invocation-id>/`.
Use UTC and the exact filename `StageName_HHMM-MMDDYY.md`.
Nested workers use their owning stage's name and record their specific role in the body.

Unique invocation directories prevent collisions. Never overwrite another log.
Record assignment, outcome, evidence paths, decisions, and unresolved issues. Omit transcripts, credentials, and secrets.
Return result path, outcome, unresolved issues, and confirmation that descendants are terminal and collected.
