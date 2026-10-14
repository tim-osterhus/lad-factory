# Native continuation policy

`goal.md` preserves the original specification in either mode.
The Orchestrator owns the selected continuation control. Stages and nested workers never control it.
Record mode, authorization, owning chat, host reference, status, and verification evidence in bootstrap and state.
Fresh contexts, fixed models/efforts, and native completion-event waiting remain required in both modes.

## Select and bind one mode

Use native Goal mode when explicitly authorized and available.
When Goals are unavailable or not desired, the Orchestrator provides itself one native same-chat recurring heartbeat, subject to the gates below.
Heartbeat mode does not require Goal creation, inspection, or completion controls.
Reading workflow files alone authorizes neither a Goal nor a recurring task.

Goal mode requires a separate explicit user Goal request or verified native `/goal` evidence.
Verify the original objective, criteria, owning chat, status, and supported lifecycle controls before adoption or creation.
Save the stable host-exposed reference. Use a verified chat-scoped reference when no internal Goal ID is exposed.
Never invent an ID, slash behavior, or shell Goal control. Set a token budget only when the user requests one.

Keep the Goal incomplete until Arbiter closure. Follow native pause, blocked, and budget rules.
Never complete a Goal to avoid waiting or because a budget expires. Only the user can authorize a pause.

Heartbeat mode requires explicit user recurring-task authorization in the original request, startup instruction, or preserved record.
Verify actual native scheduler availability, exact owning-chat binding, and safe idle-chat resumption without overlapping controllers.
Tool presence alone proves neither safe resumption nor serialization, unloaded wakeup, or Cloud compatibility.

After verification, create or reuse exactly one heartbeat bound to this run and owning chat.
Record its native reference, supported cadence, prompt, and evidence. Never substitute a standalone job.
A five-minute cadence is an example only when the host supports it, not a documented minimum.
Reuse the saved heartbeat on recovery. Do not create another controller or schedule.

Inspect any exposed existing Goal before mode selection. An unrelated active Goal or uncertain binding requires a hold.
Preserve unrelated Goals and schedules. Switching modes cannot silently pause, abandon, replace, or complete an active Goal.
A requested mode change needs explicit user direction and verified lifecycle reconciliation before dependent dispatch.

If neither authorized continuation control is available, report the missing capability and manual user-resume limitation.
Preserve prepared records. Do not fabricate an API, cron/shell loop, custom controller, or background-continuation promise.

## Wait, resume, and close

The heartbeat is a stopgap against premature stopping, not a stage-status checker.
While a stage is active, remain idle in `collaboration.wait_agent` on collaboration hosts.
Repeat native event waits after bounded timeouts. Never periodically inspect active-stage status or end the turn prematurely.

A scheduler wake reconciles saved state and exact active owner before any dispatch.
Preserve scope, criteria, counters, budgets, routes, and instruction identities. Never duplicate active work or restart a completed run.
Reconcile uncertain native identities/outcomes under `context/transitions.md` before advancing.

Only a current Arbiter pass for every original criterion, with all work drained, permits successful closure.
In Goal mode, reinspect the exact owning Goal and complete it with its supported control. Record the returned status.
In heartbeat mode, stop or disable only this run's heartbeat and record the returned status.

Also stop only this heartbeat on cancellation or a legitimate recorded human-input/budget hold.
A late wake after closure, cancellation, or that hold stops the heartbeat and reports saved disposition without dispatch.
Ordinary waiting or an unchanged state is not a hold. Native Goal holds follow the Goal tool rules separately.
If cleanup cannot be verified, report that limitation and the exact remaining native control.

## Concise heartbeat prompt

> Resume this LAD run from saved state. If a stage is active, wait with collaboration.wait_agent. Never duplicate active work or end the turn prematurely. Preserve scope, criteria, counters, budgets, and routes. Continue until Arbiter verifies the original specification. Stop only this heartbeat and report on closure, cancellation, or a recorded human-input/budget hold. A late wake after that disposition must stop without starting another run.

## Documented host boundary

[Scheduled tasks](https://learn.chatgpt.com/docs/automations) documents same-chat tasks and minute intervals.
[Long-running work](https://learn.chatgpt.com/docs/long-running-work) documents Goal mode in desktop, CLI, and IDE surfaces.
The [glossary](https://learn.chatgpt.com/docs/glossary) labels Heartbeat as a desktop feature.
These sources do not establish LAD scheduler behavior, a minimum cadence, serialized controllers, or Cloud compatibility.
