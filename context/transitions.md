# Transition policy

This table is the complete stage/outcome policy. Overrides below apply first.
Recommendations provide evidence, never permission to add a route.
The Orchestrator dispatches only within original scope, assigned paths, and remaining budgets.

## Outcome meaning and blocker validation

`pass` supplies sufficient current evidence for the stage's acceptance criteria.
`findings` supplies inspectable defects, unresolved review, or deficient requirements/packets.
`error` reports an execution problem that can use authorized diagnosis or repair.
`blocked` means verified human dependence under the Human hold conditions below.

The Orchestrator validates the obstacle and the work already attempted before choosing a route.
Already-authorized source retrieval and trivial environment repairs are recoverable execution problems.
Missing access requires a Human hold only when the needed grant cannot be obtained through already-authorized means.
Planning defects may route directly to Consultant. Review findings use Fixer/Doublechecker where applicable.

A worker's `blocked` label alone never establishes human dependence.
For a mislabeled recoverable obstacle, retain the result and record the classification correction with evidence.
Use that stage's `findings` or `error` route. Never convert a terminal blocked result into a passing artifact.

## Legal routes

| Stage | pass | findings | blocked | error |
| --- | --- | --- | --- | --- |
| Recon | Planner with accepted intake | Consultant for deficient intake | Human hold | Troubleshooter, resume Recon |
| Planner | Manager with accepted specification | Consultant for specification defects | Human hold | Troubleshooter, resume Planner |
| Manager | Builder with accepted consistent packets | Consultant for packet defects | Human hold | Troubleshooter, resume Manager |
| Builder | Checker | Checker if implementation and check evidence exist, otherwise Troubleshooter to resume Builder | Human hold | Troubleshooter, resume Builder |
| Checker | Updater | Fixer for actionable scoped findings, Consultant for invalid contract/baseline | Human hold | Troubleshooter, resume Checker |
| Fixer | Doublechecker | Doublechecker if inspectable repair exists, otherwise Troubleshooter to resume Fixer | Human hold | Troubleshooter, resume Fixer |
| Doublechecker | Updater through the Learning gate | Fixer while fewer than two cycles, otherwise Troubleshooter through the Learning gate. Consultant for invalid contract/baseline | Human hold | Troubleshooter, resume Doublechecker |
| Troubleshooter | Doublechecker for repaired review, otherwise exact saved interrupted stage | Consultant | Human hold | Consultant |
| Consultant | Accepted diagnosis route below | Accepted diagnosis route below, or Human hold after bounded diagnosis without a safe actionable route | Human hold | Troubleshooter for evidenced scoped execution repair, or same-stage replacement guard below. Human hold only under hold conditions |
| Updater | Accept packet, then Builder for next packet or Arbiter when drained. Affected review first if edits invalidate evidence | Checker for affected new review, Doublechecker when the existing baseline applies. Consultant for defective packet | Human hold | Troubleshooter, resume Updater |
| Learning | Record assessment and restore saved pending route | Record candidate/assessment and restore saved pending route | Learning failure rule below | Learning failure rule below |
| Arbiter | Verify closure guards, then Orchestrator closes the selected continuation control | Manager for bounded original-criterion remediation | Human hold | Troubleshooter for evidenced scoped execution repair, or retry Arbiter once under the replacement guard below. Otherwise Human hold |

Consultant may propose scoped execution repair to Troubleshooter.
Planning proposals may repair a specification through Planner then Manager, or packets through Manager.
The Orchestrator accepts the diagnosis within existing authority and budgets.
The execution route requires a saved interrupted stage and unused local-repair budget.
Planning repair consumes the planning-repair budget before dispatching Planner or Manager.
Diagnosis routes cannot return directly to Consultant or Arbiter without required intervening work.
Guarded same-stage replacements below remain permitted.

Consultant cannot approve its own scope or budget increase.
An exhausted bounded diagnosis without a safe actionable route goes to Human hold with its evidence.
Consultant/Troubleshooter routing preserves spent consultation, planning, local-repair, and dispatch debits.
It never replenishes a budget or bypasses an exhausted cap by choosing another role.

For Consultant or Arbiter execution errors, record the failed operation and exact stage resume point.
An evidenced scoped repair may use Troubleshooter only with unused local-repair budget and all applicable caps.

Otherwise permit one same-stage replacement only after the technical prerequisite is resolved.
Missing or invalid results use the same existing replacement allowance, not a separate retry allowance.
Reserve the replacement debit and require every applicable cap, current identity, and authority guard.

Do not invent a capability or retry an unknown external effect.
If neither bounded route is available, record the exact exhausted budget or human dependence before holding.

Before dispatching Manager for an Arbiter gap, reserve and persist one Arbiter remediation episode debit.
Bind the episode to the original criteria and preserve its packet lineage.
The default maximum is one episode per run, independent of packet names.
Rejected, interrupted, or superseded remediation retains that debit.
Resume the same recorded episode only within remaining dispatch and recovery limits.
Another episode requires an explicit user budget decision. Renaming or replacing packets does not restore capacity.

Recon always precedes Planner for existing projects.
Greenfield projects enter Planner after setup.

## Overrides and accounting

| Condition | Required action |
| --- | --- |
| Progress, helper completion, or unexpected owner event | Continue the adapter's native wait or authorized callback procedure. No acceptance or counters for a new dispatch |
| Stage still active | Wait, or explicitly interrupt before any replacement |
| Interrupted invocation | Preserve evidence and dispatch debit. After confirmed terminal interruption, resume the same stage in a fresh invocation only under the restart guards below. Otherwise Human hold |
| Unknown spawn or external-write outcome | Reconciliation hold. Do not replace or replay until exact evidence resolves the outcome |
| Invalid result, missing required evidence, stale revision, or wrong invocation | Reject acceptance. Preserve the spent attempt and rejection evidence. Retry that same stage once if its dispatch cap allows, otherwise Human hold |
| Out-of-scope changed path | Reject acceptance, record the difference and affected ownership, preserve files, and enter Human hold. No destructive reset |
| Source changed since review | Invalidate affected evidence. Checker establishes a new baseline if the prior basis is invalid. Otherwise Doublechecker rechecks the preserved baseline |
| Existing Goal conflict or selected continuation/common capability unavailable | Human hold before dependent dispatch under `context/continuation.md` |
| Any necessary budget exhausted | Human hold. Do not substitute another role to evade the cap |

Reserve and persist one dispatch attempt before every spawn, including retries.
Failed, blocked, invalid, interrupted, and identifier-uncertain launches retain that debit.
If native dispatch demonstrably never occurred, record proof before returning the reservation.
Unknown usage stays reserved. Resume never resets counters.

Assignments distinguish the current reserved dispatch/replacement from capacity for future invocations.
Zero future capacity does not revoke a valid reservation already debited for the current invocation.

An interrupted-stage restart requires confirmed terminal interruption and the exact native invocation identity.
Validate the pinned instruction snapshot, pre/post path audit, original authority, and any invalid-result or missing-evidence guards.
All applicable dispatch, retry, local-repair, and run caps must have capacity.
Only then dispatch the same stage with a new invocation and fresh context.
If any guard fails, enter Human hold. Identity reconciliation alone does not authorize a new route.

Use the following defaults unless the user sets different finite limits before dispatch.
Record limits and usage in state and copy remaining counts into assignments.

| Scope | Default maximum |
| --- | --- |
| Total top-level dispatches per run, including retries and Learning | 60 |
| Recon, Planner, Manager dispatches each per run | 3 |
| Builder, Checker, Doublechecker, Updater dispatches each per packet | 4 |
| Fixer dispatches per packet, including failed attempts | 3 |
| Evaluated Fixer cycles before escalation per packet | 2 |
| Troubleshooter dispatches / local repair attempts per originating packet lineage or unpacketized run scope | 2 / 1 |
| Consultant dispatches per run | 2 |
| Planning repair episodes per run | 1 |
| Learning dispatches per packet | 2 |
| Arbiter dispatches per run, including retries and remediation review | 3 |
| Arbiter remediation episodes per run | 1 |
| Invalid-result or technical replacement per stage and originating packet lineage (or unpacketized run scope) | 1 |
| Nested dispatches / nesting depth per top-level invocation | 4 / 2 |
| Check-command invocations per top-level invocation, including helpers | 12 |
| Wall-clock limit per check command | 600 seconds |

All applicable caps must have capacity. A new packet does not reset run-level counters.
Nested-dispatch and check-command limits cover the entire descendant tree, not a fresh allowance per helper.

Bind recovery counters to the originating packet lineage.
Without an originating packet, use the run's single persistent unpacketized scope.
That unpacketized scope covers pre-packet, packetless, post-packet, and root recovery, including Arbiter after packet drain.
Never create another scope by failure, invocation, role, phase, or completed-packet boundary.
Consultant, Troubleshooter, and resumed stages retain the originating scope, including through replanning or replacement packets.
Charge Troubleshooter dispatches and local repair attempts to that scope.
Each stage's same-stage technical retries and invalid-result replacements share its single replacement allowance in that scope.
This includes a fresh same-stage technical retry after Troubleshooter repairs a prerequisite.
Reconcile already-recorded usage and reservations before dispatch. An absent field never proves unused capacity.
Unresolved accounting requires reconciliation. Exhausted capacity requires the explicit human budget decision, never another scope or role.

Each nested spawn consumes the assigned nested-dispatch budget, including failed and interrupted attempts.
Parents persist child counters in their invocation artifact before launch and report actual usage.
Commands and local repair attempts use the assignment's finite limits.
The local-repair limit counts attempted repairs even when verification fails or execution is interrupted.

Count an evaluated Fixer cycle once a matching Doublechecker evaluates an inspectable Fixer repair.
A failed Fixer or failed Doublechecker still consumes dispatches, but does not invent an evaluated cycle.
Persist the Fixer invocation paired with its evaluation so a retry cannot count the same cycle twice.
After cycle two, save Updater on pass or Troubleshooter on unresolved findings.
Run Learning before that saved route, including a successful second cycle.
Once Learning is passed, findings, or failed, later reviews restore their legal route without reentering Learning for that packet.

Learning does not recursively invoke Learning or restart repair cycles.
On blocked/error, record failure and preserve the pending route and guidance revision.
Retry Learning once only for a resolved transient prerequisite within its two-dispatch cap.
Otherwise mark `failed`, then restore the pending route if its authority and evidence remain valid.
Missing authority needed by that pending route requires Human hold.

## Human and reconciliation holds

Enter a Human hold only for these conditions:

- Required information or access remains unavailable through already-authorized means.
- A human-owned choice, new scope, or permission is required.
- Protected user work or unsafe outcomes cannot be resolved safely with authorized read-only checks.
- A necessary approved finite budget is exhausted.
- Bounded diagnosis is exhausted with no safe actionable route.

Record the reason/type, triggering invocation, and exact saved resume stage/route in the existing pending-route record.
Record required resolution evidence, source/guidance identities, and relevant historical usage, reservations, and remaining limits.
Retain the original goal, packet lineage, baseline, and exact active-owner identity/outcome.

No autonomous dispatch occurs while the required authority or input is missing.
Human hold is workflow state. Apply `context/continuation.md` for the selected mode.
In Goal mode, a hold does not authorize pausing or blocking contrary to native tool rules.

When the user supplies resolution, verify its scope, authority, source/guidance identities, and the exact active-owner outcome.
Reconcile uncertain owners. Wait for active work or confirm terminal interruption before any replacement.

Recompute invalidated evidence and affected dependents before accepting the saved resume route.
A terminal blocked invocation remains blocked. Never accept stale blocked artifacts to skip a stage.
Dispatch a fresh invocation of the recorded appropriate stage with fresh context and a new reserved debit.
Apply all remaining caps and any applicable replacement/recovery guards before dispatch.

An approved budget change records the new finite limit and preserves every historical and reserved debit.
No recovery role can bypass an exhausted cap.

If the resolution changes the original specification beyond current authority, record the user's explicit scope decision.
Use approved Planner/Manager repair as required. Do not silently change the original goal.

A reconciliation hold resumes only after exact invocation, native identity, and outcome are established.
An active stage must finish or receive explicit interruption before replacement.
Files, elapsed time, and a recommendation alone cannot satisfy either hold.
