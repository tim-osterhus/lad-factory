# Stage result

Run: <run-id>

Invocation: <invocation-id>

Stage: <stage>

Outcome: <pass | findings | blocked | error>

Examined source: <revision plus dirty/untracked identity>

Instruction revision: <same immutable revision as assignment>

Guidance manifest: <same path and identity as assignment>

Recommended route: <stage or human decision>

Parent invocation: <none or exact parent>

## Artifacts

<Paths, identities, and scope.>

## Checks

| Check | Working directory | Result | Evidence |
| --- | --- | --- | --- |
| <command or observation> | <directory> | <exit status, failed, or unrun> | <path> |

## Findings and criteria

<Stable finding IDs, criteria, reproduction, and current outcomes.>

## Recovery or decisions

<Attempt usage, pending route, proposed repair, missing authority or inputs.>

## Changed-path audit

<Pre-dispatch snapshot path, post-state/difference evidence, actual changed paths, and comparison with assigned writable paths.>
<Parent performs an independent audit before acceptance. Record unexpected paths without deleting user work.>

## Nested work

<Affirm all descendants terminal and results collected. Include worker IDs, pinned revisions, work-order/result/log paths, spent counters, changed-path audits, integration checks, or none.>

## Log

<Exact log path and byte count smaller than 5120.>
