# Current run state

Run: <run-id>

Continuation mode: <goal, heartbeat, callback, or interactive>

Continuation authorization: <preserved selected-mode user evidence>

Continuation owning chat/reference/status/evidence: <verified saved selected control>

These native Goal fields apply only in Goal mode. Mark them not applicable in other modes.

Native goal reference: <stable host-exposed reference>

Native goal owning thread: <verified thread reference>

Native goal verified objective: <observed objective matching original target>

Native goal verification evidence: <response path and time>

Optional goal_id: <only if exposed, otherwise not exposed>

Native goal status: <observed status, or unverified before native binding>

Heartbeat details: <heartbeat mode only: cadence, exact prompt, safe idle-resumption/serialization evidence, lifecycle receipt, otherwise not applicable>

Callback/interactive details: <exact owner delivery and authorized yield, or saved resume instruction requiring user return, otherwise not applicable>

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

Profile revision and adapter identity: <pinned installation files and manifest entries>

Effective native configuration identities: <recorded paths, hashes, precedence and selected owner/helper bindings>

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
| <each applicable scope from context/transitions.md> | <finite limit> | <0 for a new run, otherwise reconciled debits> | <remaining after recorded debits> |

Recovery counter scope: <originating packet lineage or this run's persistent unpacketized scope, with reconciled ledger references>

## Dispatch ledger

| Invocation | Stage/packet | Reserved attempt | Native identity | Outcome | Cycle pairing | Path audit |
| --- | --- | --- | --- | --- | --- | --- |
| <id> | <stage, packet if any, and originating recovery counter scope> | <counter debit and scope reference> | <agent ID or unresolved> | <active, rejected, interrupted, or result> | <Fixer/evaluation IDs or none> | <evidence or pending> |

Preserve debits on failed, invalid, interrupted, and unknown dispatches.
Learning status is pending, passed, findings, or failed. Failed Learning preserves the pending route.

## Pending route

<Resume stage after Learning or recovery and its supporting result.>

<For a Human hold: reason/type, triggering invocation, exact saved resume stage/route, and necessary human resolution evidence.>
<Source/guidance identities and relevant historical usage, current reservations, remaining limits, and active-owner identity/outcome.>
<On resolution: verified scope/authority and identities, affected evidence/dependents, approved finite budget changes preserving past debits, and fresh resume invocation/debit.>
<A terminal blocked invocation remains blocked. Reconcile active or uncertain owners before replacement.>

## Decisions and recovery

<Refinements, superseded invocations, blockers, and required human decisions.>

<Selected-mode recovery/closure under context/continuation.md. Preserve active owner and control reference, never duplicate schedules, and record legitimate holds/cancellation/closure.>

<Arbiter remediation episode ID, original criteria, reserved debit before Manager dispatch, and retained lineage/counters on rejection or interruption.>

## Guidance candidates and activation

<Candidate paths, old/new revisions, safe boundary, accepted scope, and affected evidence. No-op preserves the revision.>

## Arbiter

<Per-criterion verdict path or not yet reviewed.>
