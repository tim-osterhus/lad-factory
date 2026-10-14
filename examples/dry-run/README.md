# Protocol fixture

This fixture is a structural walkthrough, not a native Codex run.
No agents, native goal, application checks, or external actions were executed.
Identifiers beginning `fixture-` describe illustrative data.

Read [goal](goal.md), [packet](packet.md), [baseline](baseline.md), [state](state.md), [assignment](assignment.md), and [result](result.md).
The assignment demonstrates Learning after two evaluated Fixer cycles.
The result is an illustrative no-op. It preserves the pending Troubleshooter route.

## Transition cases

| Case | Given | Expected route and assertion |
| --- | --- | --- |
| Normal pass | Builder and Checker pass at current source | Updater, then next ordered packet |
| Successful second repair | Two Fixer cycles, second Doublechecker passes | Learning once, then Updater. Cycles stay 2 |
| Unresolved second repair | Two Fixer cycles, second Doublechecker reports findings | Learning once, then Troubleshooter. Cycles stay 2 |
| Learning no-op | Evidence does not support instruction change | Preserve pending route and record Learning complete |
| Local recovery | Troubleshooter repairs review finding within budget | Doublechecker using the original baseline |
| Planning escalation | Consultant finds incompatible packet contracts | Manager repairs affected packets and checks the whole set |
| Specification insufficiency | Consultant identifies missing necessary detail | Planner works alone, then Manager repairs affected plan |
| Arbiter gap | Packet complete, AC-02 lacks current evidence | Manager creates scoped remediation, then normal review and Arbiter |
| Arbiter closure | All original criteria pass with current independent evidence | Orchestrator completes native goal and verifies returned status |
| Interrupted active stage | Disk state says running and native agent is active | Event wait or explicit interruption before replacement |
| Nonterminal mailbox event | Progress, helper final, or unexpected agent ID arrives | Resume idle wait. Only exact owner FINAL with drained descendants and valid result permits acceptance |
| Unrelated active goal | Native goal target or criteria differ from this run | Preserve that goal and report conflict before dispatch |
| Unknown spawn identity | Spawn may have succeeded before its ID was recorded | Hold for exact invocation, native identity, and outcome. No replacement or advancement |
| Stale result | Result invocation differs from active invocation | Reject result without canonical transition |
| Stale snapshot | Source changed after review | Invalidate affected evidence and recheck at current source |
| Unknown external outcome | A permitted write's outcome cannot be verified | Record unknown and reconcile before any repeat |
| Missing native control | Fresh context, goal, model, or event wait unavailable | Stop dependent execution and report capability |
| Human decision | Required scope or authority is missing | Ask the exact question and leave goal incomplete |

## Static acceptance checklist

1. Every stage entry in Orchestrator names an existing prompt file.
2. Every initial stage prompt contains only the exact read-file instruction.
3. Every top-level owner uses Sol, except Arbiter using Astra.
4. Planner forbids delegation and other stages reference nested selection.
5. Shared contracts and templates agree on ownership and result fields.
6. The fixture assignment and result match run, invocation, and stage.
7. The immutable baseline identity survives two Fixer cycles.
8. Learning preserves counters and the pending route on pass or findings.
9. Arbiter coverage refers to every original criterion.
10. Logs use UTC, unique invocation directories, exact filenames, and less than 5120 bytes.

These checks validate file consistency and documented routing.
They do not validate host autonomy, failure recovery, or production operation.
