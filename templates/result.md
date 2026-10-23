# Stage result

Run: <run-id>

Invocation: <invocation-id>

Stage: <stage>

Outcome: <pass | findings | blocked | error>

Examined source: <base revision plus actual diff/relevant untracked identity>

Instruction revision: <same guidance revision as assignment>

Profile/adapter revisions: <same pinned revisions as assignment>

Recommended route: <stage or required human decision>

Parent invocation: <none or exact parent>

## Artifacts and actual changes

<Small evidence index, actual change/diff, and relevant untracked paths.>
<Identify source evidence directly. A summary is not proof.>

## Checks

| Command or observation | Working directory | Status | Relevant output/evidence |
| --- | --- | --- | --- |
| <check> | <directory> | <exit status, failed, or unrun> | <targeted output or path> |

## Findings and criteria

<Stable finding IDs, criteria, reproduction, and current outcomes.>

## Recovery or decisions

<Unresolved issues, proposed route, materially new next step, or missing input/authority.>
<For blocked: exact human dependence and why authorized retrieval, checks, or repair cannot resolve it.>

## Change review

<Actual changed paths compared with assigned paths and existing user work.>
<Unexpected differences and ownership investigation. Preserve files. Parent independently checks aggregate changes.>

## Nested work

<All descendants terminal and results collected, with IDs, work-order/result/log paths, integration checks, or none.>

## Log

<Exact log path and byte count smaller than 5120.>
