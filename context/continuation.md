# Native continuation policy

`goal.md` preserves the original specification in every mode.
The Orchestrator owns continuation. Stages and helpers never control Goals, schedules, or run resumption.
Use the pinned `installation/profile.md` and `installation/adapter.md` for actual native controls and limitations.
Record mode, authorization, exact owning session, control reference, status, and evidence in bootstrap and state.
Fresh stage contexts, pinned model settings, sequential ownership, and independent review apply in every mode.

## Select and bind one mode

Select `goal`, `heartbeat`, `callback`, or `interactive` from the installed adapter's supported modes.
Reading workflow files authorizes neither a Goal nor recurring work.
Installation can prepare a mode with unknown capabilities. Verify its gates before dependent execution.

Goal mode requires a separate explicit user Goal request or verified native composer evidence.
Verify the original objective, criteria, owner, status, and supported lifecycle controls before adoption or creation.
Save the stable host-exposed reference. Use a verified session-scoped reference when no internal Goal ID is exposed.

Never invent an ID, slash behavior, or shell Goal control. Set a token budget only when requested.
Keep the Goal incomplete until Arbiter closure. Follow native pause, blocked, and budget rules.
Never complete a Goal to avoid waiting or because a budget expires. Only the user can authorize a pause.

Heartbeat mode requires explicit user recurring-task authorization.
Verify the native scheduler, exact owning-session binding, and safe idle resumption without overlapping controllers.
Tool presence alone proves neither serialization, unloaded wakeup, nor host compatibility.

Create or reuse exactly one verified heartbeat for this run. Record its reference, cadence, prompt, and evidence.
Reuse that heartbeat on recovery. Never substitute a standalone job, shell loop, or another controller.
The heartbeat resumes saved state. It does not periodically poll stage status.

Callback mode requires an adapter-documented completion delivery mechanism for the exact owned invocation.
Verify where completion arrives and whether delivery requires yielding the current turn.
An authorized yield for that callback is waiting, not run completion. Preserve the active owner and pending route.
Promise automatic continuation only when evidence establishes that delivery resumes the owning idle or unloaded session.
If delivery requires a user turn, use interactive mode and disclose that requirement.

Interactive mode requires the user to return and resume the owning session when native autonomous continuation is unavailable.
Save the active invocation, pending route, and exact resume instruction before yielding.
Report what is running, where results will be saved, and that the user must return.
Never claim background continuation. Reconcile the owner and result on return before dispatching anything else.
Interactive mode preserves every stage, review guard, and explicit user limit.

Inspect exposed existing controls before adopting a mode. An unrelated active Goal or uncertain binding requires reconciliation.
Preserve unrelated Goals and schedules. Do not silently pause, abandon, replace, or complete them.

A mode change requires existing user authorization and verified lifecycle reconciliation before dependent dispatch.
When Goal or heartbeat controls are unsupported, record a supported callback or interactive mode within that authorization.
Missing capabilities stop dependent execution. Preserve prepared files and identify the exact missing evidence or authority.
Do not invent APIs, launch unsupported external harnesses, or add a custom continuation service.

## Wait, resume, and close

While a stage is active, use the pinned adapter's native event wait or authorized callback yield.
Repeat bounded native event waits after timeouts. Never periodically inspect stage status or duplicate a dispatch.
Use interactive resumption only as recorded above. Never end a turn with an unsupported continuation promise.

Progress events, helper completions, and unexpected identities cannot advance the stage.
Accept only the adapter's terminal completion signal for the exact recorded owner, with a valid current result and collected terminal descendants.

Every wake or user return reconciles saved state and the exact active owner before dispatch.
Preserve scope, criteria, evaluated cycle history, explicit user limits, routes, and guidance revisions.
Reconcile uncertain identities or outcomes under `context/transitions.md`. Never restart completed work.

Only a current Arbiter pass for every original criterion, with all work drained, permits successful closure.
In Goal mode, reinspect and complete only the exact owning Goal using its supported control. Record the returned status.
In heartbeat mode, stop or disable only this run's heartbeat and record the returned status.
For callback or interactive mode, record closure and reconcile any pending callback. Do not imply a nonexistent lifecycle API.

Stop only this heartbeat on cancellation or a legitimate recorded Human hold.
A late wake after closure, cancellation, or that hold stops the heartbeat without dispatch.
Ordinary waiting or unchanged state is not a hold. Native Goal holds follow native rules separately.
If cleanup cannot be verified, report the limitation and exact remaining native control.

## Heartbeat prompt contract

Save a concise native scheduler prompt that resumes this run from saved state using its pinned adapter.
Require exact-owner waiting, no duplicate work, preserved criteria and explicit user limits, and continuation through Arbiter review.
Require stopping only this heartbeat on closure, cancellation, or a recorded Human hold.
A late wake after that disposition must stop without starting another run.
The adapter supplies actual tool names. This policy defines no generic executable API.
