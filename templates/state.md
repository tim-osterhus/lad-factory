# Current run state

Run: <run-id>

Native goal reference: <stable host-exposed reference>

Native goal owning thread: <verified thread reference>

Native goal verified objective: <observed objective matching original target>

Native goal verification evidence: <response path and time>

Optional goal_id: <only if exposed, otherwise not exposed>

Native goal status: <observed status, or unverified before native binding>

Workflow status: prepared

Original goal: run/current/goal.md

Accepted specification: <path or not yet accepted>

Current packet: <packet-id or none>

Active stage: <stage or none>

Active invocation: <invocation-id or none>

Native agent ID: <verified identifier or none>

Last accepted result: <path or none>

Evidence index: run/current/evidence.md

Instruction revision: <active immutable revision>

Guidance manifest: <run/current/manifests/revision.md and identity>

Instruction root: <explicit immutable snapshot path>

Pre-dispatch path snapshot: <current invocation snapshot path or none>

## Ordered packets

| Packet | Dependencies | Status | Guidance revision | Baseline | Fixer cycles | Learning status |
| --- | --- | --- | --- | --- | --- | --- |
| <id> | <ids or none> | pending | <revision> | <path and identity or none> | 0 | pending |

## Budgets

| Scope | Budget | Used | Remaining |
| --- | --- | --- | --- |
| <each applicable scope from context/transitions.md> | <finite limit> | 0 | <limit> |

## Dispatch ledger

| Invocation | Stage/packet | Reserved attempt | Native identity | Outcome | Cycle pairing | Path audit |
| --- | --- | --- | --- | --- | --- | --- |
| <id> | <stage and packet or pre-packet> | <counter debit> | <agent ID or unresolved> | <active, rejected, interrupted, or result> | <Fixer/evaluation IDs or none> | <evidence or pending> |

Preserve debits on failed, invalid, interrupted, and unknown dispatches.
Learning status is pending, passed, findings, or failed. Failed Learning preserves the pending route.

## Pending route

<Resume stage after Learning or recovery and its supporting result.>

## Decisions and recovery

<Refinements, superseded invocations, blockers, and required human decisions.>

<Arbiter remediation episode ID, original criteria, reserved debit before Manager dispatch, and retained lineage/counters on rejection or interruption.>

## Guidance candidates and activation

<Candidate paths, old/new revisions, safe boundary, accepted scope, and affected evidence. No-op preserves the revision.>

## Arbiter

<Per-criterion verdict path or not yet reviewed.>
