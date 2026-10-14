# Protocol fixture

This fixture is a structural walkthrough, not a native Codex run.
No agents, native Goal, heartbeat, application checks, or external actions were executed.
Identifiers beginning `fixture-` describe illustrative data.

Read [goal](goal.md), [packet](packet.md), [baseline](baseline.md), [state](state.md), [assignment](assignment.md), and [result](result.md).
The assignment demonstrates Learning after two evaluated Fixer cycles.
The result is an illustrative no-op. It preserves the pending Troubleshooter route.
The exhaustive legal routes and finite default limits are in [transition policy](../../context/transitions.md).
The table below illustrates guards and traces. It does not replace that normative policy.

## Transition cases

| Case | Given | Expected route and assertion |
| --- | --- | --- |
| Normal pass | Builder and Checker pass at current source | Updater, then next ordered packet |
| Successful second repair | Two Fixer cycles, second Doublechecker passes | Learning once, then Updater. Cycles stay 2 |
| Unresolved second repair | Two Fixer cycles, second Doublechecker reports findings | Learning once, then Troubleshooter. Cycles stay 2 |
| Learning no-op | Evidence does not support instruction change | Preserve pending route and record Learning complete |
| Learning independent failure | Learning errors with no resolved prerequisite | Record failed Learning, preserve revision/counters, restore legal pending route. No recursive Learning or reset |
| Learning transient retry | Learning errors, prerequisite is demonstrably resolved, one dispatch remains | One new Learning invocation, debit remaining attempt, retain pending route |
| Candidate activation | Learning proposes guidance while current packet remains open | Keep packet's fixture-guidance-v1 through Updater. Accept new snapshot only at a recorded safe boundary |
| Missing internal goal ID | Host exposes owning thread, objective, and status only | Persist verified thread-scoped reference and objective/status. Do not require or fabricate goal_id |
| Unauthorized goal startup | User only asks to read a workflow file | Prepare records, require separate explicit native-goal authorization before creation |
| Authorized heartbeat fallback | Goals unavailable or not desired, recurring authorization and native same-chat safe resumption verified | Orchestrator creates or reuses one heartbeat under [continuation policy](../../context/continuation.md). No Goal capability required |
| Unverified heartbeat host | Scheduler tool exists but idle resumption or owner binding is unproven | Report missing evidence and manual user-resume limitation. Do not promise background continuation |
| Heartbeat with active stage | Saved exact owner still has active work | Continue `collaboration.wait_agent`. No periodic status check, duplicate dispatch, or premature turn ending |
| Late heartbeat wake | Closure, cancellation, or legitimate recorded human-input/budget hold already saved | Stop only the saved heartbeat and report disposition. Do not start another run |
| Reserved replacement at zero future capacity | Current replacement already debited, future replacements 0 | Execute the reserved invocation within its assigned limits. No further replacement authorized |
| Builder error | Builder cannot complete implementation | Debit attempt, Troubleshooter with exact Builder resume point and remaining local-repair budget |
| Planner technical error | Authorized input retrieval fails for a repairable technical reason | Troubleshooter, then fresh Planner with exact saved resume point. Specification defects remain findings to Consultant |
| Manager technical error | A repairable prerequisite prevents packet drafting | Troubleshooter, then fresh Manager. Packet-defect findings go to Consultant |
| Recoverable access obstacle | Worker reports blocked, but existing authorization permits retrieving the required source | Retain result, record evidenced error classification, and use the stage's execution-recovery route. No unsupported Human hold |
| Missing access grant | Required source needs a grant unavailable through authorized means | Human hold records exact grant, triggering invocation, saved resume stage, identities, and limits |
| Repairable build configuration | A check fails because an assigned build prerequisite needs scoped repair | Troubleshooter within existing writable paths and repair budget, then exact saved stage or Doublechecker for repaired review |
| Consultant execution error | A scoped prerequisite prevents diagnosis | Troubleshooter within remaining repair budget, then fresh Consultant. Resolved technical/invalid-result replacement shares the existing once guard |
| Arbiter execution error | A scoped prerequisite prevents complete goal review | Troubleshooter within remaining repair budget, then fresh Arbiter. Replacement never refreshes the Arbiter dispatch cap |
| Root recovery after packet drain | Arbiter execution error has no originating packet | Charge the same persistent unpacketized run scope used before packets. Its 2/1 Troubleshooter/repair limits never refresh at packet drain |
| Consultant recovery scope | Consultant error follows a packet failure or an unpacketized failure | Inherit that originating packet lineage or persistent run scope. Replanning and replacement packets cannot create repair capacity |
| Shared replacement allowance | A stage already consumed its invalid-result replacement, then needs a technical retry | The same stage/scope allowance is exhausted. Require the exact budget decision rather than a new retry bucket |
| Missing accounting field | Existing recovery usage or reservations are not yet mapped to the persistent scope | Reconcile the existing ledger first. An absent field does not authorize unused capacity |
| Updater blocked | Documentation requires missing input or authority | Human hold naming that input. No next packet acceptance |
| Resolved terminal blocked invocation | Human supplies the required input within original authority | Verify resolution, owner outcome, current identities, and affected evidence. Fresh recorded-stage invocation with a new debit. Prior artifact stays blocked |
| Budget hold resolution | User explicitly approves a larger finite necessary limit | Record the approved limit and preserve historical/reserved usage. Dispatch the saved stage only if every applicable cap allows it |
| Scope decision on resume | Human resolution changes requirements beyond current authority | Record the explicit scope decision, then approved Planner/Manager repair and affected review. No silent original-goal rewrite |
| Invalid result | Matching owner returns no required evidence | Reject, retain debit, one same-stage replacement if all caps allow, otherwise Human hold |
| Failed Fixer attempt | Fixer errors before inspectable repair | Debit Fixer dispatch, no fabricated evaluated cycle, Troubleshooter within remaining caps |
| Consultant exhausted | Diagnosis needs another consultation after run cap | Human hold. Do not route through another stage to refresh the cap |
| Unexpected review edit | Checker changes application code outside allowed artifacts | Parent rejects acceptance, records differences, preserves files, enters Human hold |
| Existing dirty work | User already changed or deleted a relevant file | Pre-dispatch snapshot preserves ownership and hashes. Audit only actual post-dispatch differences |
| Protected untracked mutation | Checker rewrites an existing protected untracked file but Git still reports the same `??` status | Full pre/post content hashes detect changed bytes. Reject acceptance, preserve files, and require conflict resolution |
| Audit coverage gap | Protected or unexpected change cannot be attributed because baseline inventory omitted it | Refuse acceptance. Record the missing coverage and preserve user work |
| Confirmed interrupted restart | Exact stage owner is confirmed terminal after interruption, snapshot/path/authority guards pass, all caps remain | Debit a new fresh invocation of the same stage. Preserve the prior debit and history |
| Interrupted restart denied | Native identity is known but interruption is not terminal, or snapshot/audit/budget guard fails | No replacement. Continue active-stage wait or enter the applicable hold |
| Arbiter remediation reservation | Arbiter reports an original-criterion gap and one episode remains | Reserve episode debit before Manager dispatch. Remaining episodes become zero and survive rejected/interrupted/superseded attempts |
| Renamed remediation packet | A consumed remediation episode gets new packet names | Remaining episode count stays zero. Another episode requires the user's explicit budget decision |
| Local recovery | Troubleshooter repairs review finding within budget | Doublechecker using the original baseline |
| Planning escalation | Consultant finds incompatible packet contracts | Manager repairs affected packets and checks the whole set |
| Recovery budget exhaustion | Consultant could recommend another role, but the required repair cap is spent | Human hold for the exact budget decision. Consultant/Troubleshooter routing cannot replenish usage |
| Specification insufficiency | Consultant identifies missing necessary detail | Planner works alone, then Manager repairs affected plan |
| Arbiter gap | Packet complete, AC-02 lacks current evidence | Manager creates scoped remediation, then normal review and Arbiter |
| Arbiter closure | All original criteria pass with current independent evidence | Orchestrator closes the selected native continuation control and verifies returned status |
| Interrupted active stage | Disk state says running and native agent is active | Event wait or explicit interruption before replacement |
| Nonterminal mailbox event | Progress, helper final, or unexpected agent ID arrives | Resume idle wait. Only exact owner FINAL with drained descendants and valid result permits acceptance |
| Unrelated active goal | Native goal target or criteria differ from this run | Preserve that goal and report conflict before dispatch |
| Unknown spawn identity | Spawn may have succeeded before its ID was recorded | Hold for exact invocation, native identity, and outcome. No replacement or advancement |
| Stale result | Result invocation differs from active invocation | Reject result without canonical transition |
| Stale snapshot | Source changed after review | Invalidate affected evidence and recheck at current source |
| Unknown external outcome | A permitted write's outcome cannot be verified | Record unknown and reconcile before any repeat |
| Missing native control | Fresh context, model, event wait, or selected continuation control unavailable | Stop dependent execution and report capability |
| Human decision | Required scope or authority is missing | Ask the exact question and leave objective incomplete. Handle the selected control under continuation policy |

## Static acceptance checklist

1. Every stage entry in Orchestrator names an existing package-relative prompt suffix.
2. Every instantiated initial prompt reads its real immutable snapshot path in one line, relative to inherited host directory.
3. Every top-level owner uses Sol, except Arbiter using Astra.
4. Planner forbids delegation and other stages reference nested selection.
5. Shared contracts and templates agree on ownership and result fields.
6. The fixture assignment and result match run, invocation, and stage.
7. The immutable baseline identity survives two Fixer cycles.
8. Learning preserves counters and the pending route on all four outcomes under the bounded failure guard.
9. Arbiter coverage refers to every original criterion.
10. Logs use UTC, unique invocation directories, exact filenames, and less than 5120 bytes.
11. Every stage has all four outcome cells. Invalid/interrupted/missing-evidence overrides retain dispatch debits.
12. Assignments, results, baselines, and state pin guidance independently of target-code identity.
13. Snapshot manifests exclude themselves and generated outputs. Active snapshot bytes remain unchanged.
14. Parent acceptance requires a changed-path audit against pre-dispatch user work and stage/helper writable paths.
15. Protected untracked bytes remain in the inventory even when status text is unchanged. Coverage gaps prevent acceptance.
16. Interrupted restart requires terminal interruption and every restart guard, then resumes the same stage with a fresh invocation.
17. Arbiter remediation counters debit before Manager dispatch and cannot reset through rejection, interruption, or packet renaming.

These checks validate file consistency and documented routing.
They do not validate host autonomy, failure recovery, or production operation.
