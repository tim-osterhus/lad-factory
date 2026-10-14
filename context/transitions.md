# Transition policy

This table is the complete stage/outcome policy. Overrides below apply first.
Recommendations provide evidence, never permission to add a route.
The Orchestrator dispatches only within original scope, assigned paths, and remaining budgets.

## Legal routes

| Stage | pass | findings | blocked | error |
| --- | --- | --- | --- | --- |
| Recon | Planner with accepted intake | Consultant for deficient intake | Human hold | Troubleshooter, resume Recon |
| Planner | Manager with accepted specification | Consultant for specification defects | Human hold | Consultant for planning failure |
| Manager | Builder with accepted consistent packets | Consultant for packet defects | Human hold | Consultant for planning failure |
| Builder | Checker | Checker if implementation and check evidence exist, otherwise Troubleshooter to resume Builder | Human hold | Troubleshooter, resume Builder |
| Checker | Updater | Fixer for actionable scoped findings, Consultant for invalid contract/baseline | Human hold | Troubleshooter, resume Checker |
| Fixer | Doublechecker | Doublechecker if inspectable repair exists, otherwise Troubleshooter to resume Fixer | Human hold | Troubleshooter, resume Fixer |
| Doublechecker | Updater through the Learning gate | Fixer while fewer than two cycles, otherwise Troubleshooter through the Learning gate. Consultant for invalid contract/baseline | Human hold | Troubleshooter, resume Doublechecker |
| Troubleshooter | Doublechecker for repaired review, otherwise exact saved interrupted stage | Consultant | Human hold | Consultant |
| Consultant | Accepted diagnosis route below | Accepted diagnosis route below, or Human hold without an actionable proposal | Human hold | Human hold |
| Updater | Accept packet, then Builder for next packet or Arbiter when drained. Affected review first if edits invalidate evidence | Checker for affected new review, Doublechecker when the existing baseline applies. Consultant for defective packet | Human hold | Troubleshooter, resume Updater |
| Learning | Record assessment and restore saved pending route | Record candidate/assessment and restore saved pending route | Learning failure rule below | Learning failure rule below |
| Arbiter | Verify closure guards, then Orchestrator closes the selected continuation control | Manager for bounded original-criterion remediation | Human hold | Retry Arbiter once within its dispatch cap, otherwise Human hold |

Consultant may accept only these diagnoses: scoped execution repair to Troubleshooter, sufficient specification repair to Planner then Manager, or packet repair to Manager.
The execution route requires a saved interrupted stage and unused local-repair budget.
Planning repair consumes the planning-repair budget before dispatching Planner or Manager.
No route returns directly to Consultant or Arbiter without the required intervening work.
An uncertain diagnosis goes to Human hold.

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
| Progress, helper FINAL, or unexpected owner event | Continue idle native event wait. No acceptance or counters for a new dispatch |
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
| Troubleshooter dispatches / local repair attempts per packet or pre-packet failure | 2 / 1 |
| Consultant dispatches per run | 2 |
| Planning repair episodes per run | 1 |
| Learning dispatches per packet | 2 |
| Arbiter dispatches per run, including retries and remediation review | 3 |
| Arbiter remediation episodes per run | 1 |
| Invalid-result replacement per stage and packet (or pre-packet scope) | 1 |
| Nested dispatches / nesting depth per top-level invocation | 4 / 2 |
| Check-command invocations per top-level invocation, including helpers | 12 |
| Wall-clock limit per check command | 600 seconds |

All applicable caps must have capacity. A new packet does not reset run-level counters.
Nested-dispatch and check-command limits cover the entire descendant tree, not a fresh allowance per helper.

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

A Human hold names the exact missing input, authority, budget decision, or path-conflict resolution.
No stage dispatch occurs until the user supplies it and the Orchestrator verifies that the saved route is legal.
Record approved budget changes explicitly. Preserve historical usage.
Human hold is workflow state. Apply `context/continuation.md` for the selected mode.
In Goal mode, a hold does not authorize pausing or blocking contrary to native tool rules.

A reconciliation hold resumes only after exact invocation, native identity, and outcome are established.
An active stage must finish or receive explicit interruption before replacement.
Files, elapsed time, and a recommendation alone cannot satisfy either hold.
