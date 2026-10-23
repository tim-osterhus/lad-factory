# Transition policy

This table defines all stage/outcome routes. The recovery rules below apply first.
The Orchestrator dispatches within the original scope, assigned paths, existing authority, and explicit user limits.

## Outcomes

`pass` supplies sufficient current evidence for the stage's criteria.
`findings` supplies inspectable defects, unresolved review, or deficient requirements or packets.
`error` reports an execution failure that needs diagnosis or repair.
`blocked` reports verified human dependence under the Human hold conditions below.

Validate the obstacle and available evidence before choosing a route.
Authorized source retrieval and repairable environment failures do not establish human dependence.
Retain a mislabeled blocked result and record the classification correction.
Use the stage's findings or error route. Never turn a blocked artifact into a pass.

## Legal routes

| Stage | pass | findings | blocked | error |
| --- | --- | --- | --- | --- |
| Recon | Planner with accepted intake | Consultant for deficient intake | Human hold | Troubleshooter, resume Recon |
| Planner | Manager with accepted specification | Consultant for specification defects | Human hold | Troubleshooter, resume Planner |
| Manager | Builder with accepted consistent packets | Consultant for packet defects | Human hold | Troubleshooter, resume Manager |
| Builder | Checker | Checker if implementation is inspectable, otherwise Troubleshooter to resume Builder | Human hold | Troubleshooter, resume Builder |
| Checker | Updater | Fixer for actionable scoped findings, Consultant for invalid contract or baseline | Human hold | Troubleshooter, resume Checker |
| Fixer | Doublechecker | Doublechecker if repair is inspectable, otherwise Troubleshooter to resume Fixer | Human hold | Troubleshooter, resume Fixer |
| Doublechecker | Updater through the Learning gate | Fixer before the second evaluated cycle, otherwise Troubleshooter through the Learning gate. Consultant for invalid contract or baseline | Human hold | Troubleshooter, resume Doublechecker |
| Troubleshooter | Doublechecker for repaired review, otherwise exact saved interrupted stage | Consultant | Human hold | Consultant |
| Consultant | Accepted diagnosis route below | Accepted diagnosis route, or Human hold without a defensible autonomous next step | Human hold | Troubleshooter for a concrete technical recovery, otherwise Human hold without a defensible autonomous next step |
| Updater | Accept packet, then Builder for next packet or Arbiter when drained. Affected review first if edits invalidate evidence | Checker for a new review, Doublechecker when the existing baseline applies. Consultant for defective packet | Human hold | Troubleshooter, resume Updater |
| Learning | Record assessment and restore saved route | Record candidate or assessment and restore saved route | Learning failure rule below | Learning failure rule below |
| Arbiter | Verify closure guards, then Orchestrator closes the selected continuation control | Manager for original-criterion remediation | Human hold | Troubleshooter, resume Arbiter |

Recon precedes Planner for existing projects. Greenfield projects enter Planner after setup.

Consultant proposes specification repair through Planner then Manager, or packet repair through Manager.
A concrete technical recovery uses Troubleshooter with the exact interrupted stage recorded.
The Orchestrator accepts only proposals within existing authority.
Consultant cannot approve scope or permission changes.
After repair, use the normal review route. No diagnosis or recommendation bypasses acceptance.

Arbiter gaps use Manager to create ordered remediation tied to the original criteria.
Preserve unaffected accepted work and record superseded packets.
Run the normal implementation and review path, then return to Arbiter.
Remediation is ordinary work toward the original goal. It has no invented episode allowance.

## Recovery and evidence

Troubleshooter owns the first autonomous recovery from technical failure or unresolved review after the Learning gate.
Consultant owns planning defects and the next diagnosis when Troubleshooter's approach fails.
Further work may continue when evidence supports a concrete, materially new next step within existing authority.
Record what changed in the diagnosis or prerequisite and what the next step will establish.
Do not repeat an unchanged failed approach indefinitely or rotate roles to disguise that repetition.

| Condition | Required action |
| --- | --- |
| Progress, helper completion, or unexpected owner event | Continue native waiting or the verified callback procedure. No stage acceptance |
| Stage still active | Wait, or explicitly interrupt and confirm terminal status before replacement |
| Interrupted invocation | Establish terminal owner, current candidate, and last accepted stage. Retain history and use a fresh invocation of the correct stage |
| Unknown spawn, writer, or external-effect outcome | Reconcile the exact owner and outcome before overlapping work or replay |
| Wrong invocation or stale result | Reject acceptance and obtain current evidence for the correct invocation |
| Missing or stale check evidence | Rerun the relevant check or stage with a fresh owner where required |
| Missing log or paperwork | Restore the concise record. Do not invalidate code solely for that omission |
| Unexpected changed path | Investigate ownership and actual differences. Preserve files. Hold only for unresolved protected-work conflict or unsafe uncertainty |
| Source changed since review | Recheck affected criteria. Use Doublechecker if the frozen baseline remains valid, otherwise Consultant and fresh Checker |
| Required native capability unavailable | Stop dependent execution and use a supported recorded continuation mode when authorized |
| Explicit user limit reached | Respect the limit and request only the decision needed to continue |

Record dispatch history sufficient to identify each invocation, native owner, stage, result, and relevant recovery relationship.
No historical command accounting or capacity reconstruction is required.
Do not infer failure from elapsed time or replay an external action with an unknown outcome.

## Learning gate

An evaluated cycle pairs an inspectable Fixer repair with its matching Doublechecker evaluation.
Record the pair so one evaluation cannot count twice.
A failed Fixer or Doublechecker execution does not create an evaluated cycle.
After two evaluated cycles, save Updater on pass or Troubleshooter on unresolved findings.
Run Learning before that route, including after a successful second cycle.

Learning records a candidate or no-op assessment without changing active guidance or review history.
On blocked or error, retain the failure and restore the saved route when its authority and evidence remain valid.
A resolved prerequisite may justify a fresh Learning invocation with a concrete next step.
Do not recursively invoke Learning or restart the packet's cycle history.
After an assessment or recorded failure, later reviews follow their legal route without reentering Learning for that packet.
A pending route requiring missing authority or input uses the Human hold conditions below.

## Human and reconciliation holds

Enter a Human hold only when:

- Required input, credentials, access, or authority cannot be obtained through authorized means.
- A human product or scope choice is required.
- Unsafe uncertainty or a protected-work conflict cannot be resolved safely within existing authority.
- An explicit user limit prevents the necessary next action.
- Evidence supports no defensible autonomous next step.

Record the reason, triggering invocation, exact saved resume stage, and required resolution evidence.
Retain the original goal, relevant packet history, frozen baseline, source/guidance revision, and owner status.
Human hold is workflow state. Native Goal status changes still follow `context/continuation.md`.

On resolution, verify authority, current candidate, owner outcome, and affected evidence.
Wait for active work or confirm terminal interruption before replacement.
A terminal blocked invocation remains blocked.
Use a fresh invocation of the appropriate stage and regenerate missing or stale evidence.
A changed scope requires the user's explicit decision and affected Planner/Manager repair.

A reconciliation hold ends only when the exact invocation, native identity, and outcome are established.
Files, elapsed time, and recommendations alone do not prove completion.
