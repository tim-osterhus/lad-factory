# Protocol fixture

This fixture describes a greeting change without launching agents, Goals, schedules, or commands.
It checks record structure and routing examples. It does not prove host execution or autonomy.
Read [goal](goal.md), [packet](packet.md), [baseline](baseline.md), [freeze record](freeze.md), [state](state.md), [assignment](assignment.md), and [result](result.md).

The assignment illustrates Learning after two evaluated Fixer/Doublechecker cycles.
The no-op result preserves the pending Troubleshooter route.
A successful second evaluation would save Updater instead.
[Transition policy](../../context/transitions.md) defines all legal stage/outcome routes.

## Transition cases

| Case | Evidence or condition | Required route |
| --- | --- | --- |
| Existing code | Existing target repository | Recon before Planner |
| Sufficient specification | Original request is implementable and verifiable | Planner passes unchanged, then Manager |
| Necessary detail | Required detail fits original scope | Planner proposes it, Orchestrator accepts, then Manager |
| Impossible gate | A packet's first meaningful check requires a later packet | Manager revises the packet set before Builder |
| Circular requirement | Requirements or prerequisites cannot be satisfied together | Consultant, then affected Planner/Manager repair |
| Builder checks | Assigned implementation and existing test permission | Builder runs meaningful development checks, then fresh Checker |
| Checker preparation | Requirement-side goal, specification, and packet | Freeze exact baseline bytes and separate SHA-256 before implementation. Parent verifies and retains expected digest before downstream dispatch |
| First unresolved repair | One evaluated Fixer/Doublechecker pair | Fixer, then Doublechecker |
| Successful second repair | Second evaluation passes | Learning, then saved Updater route |
| Unresolved second repair | Second evaluation reports findings | Learning, then saved Troubleshooter route |
| Failed repair execution | No inspectable Fixer repair or matching evaluation | Troubleshooter, without inventing an evaluated cycle |
| Learning no-op | Evidence does not support guidance change | Record assessment and restore pending route |
| Learning failure | Learning cannot complete | Retain failure and restore valid pending route without changing active guidance |
| Learning prerequisite resolved | Evidence supplies a concrete next step | Fresh Learning invocation may complete the assessment |
| Technical failure | Initial or unrelated repairable environment or execution problem | Troubleshooter, then exact interrupted stage or Doublechecker |
| Unsuccessful recovery | Troubleshooter's approach fails | Consultant for next diagnosis |
| Recurrence after recovery | Same execution failure or review finding after Troubleshooter repair | Consultant diagnosis before further recovery |
| New diagnosis | Concrete materially new next step within existing authority | Accepted repair route, with affected review afterward |
| Repeated approach | Same failure without a materially new evidence-backed approach | Consultant, then Human hold only without a defensible autonomous next step |
| Recoverable access obstacle | Existing permission allows source retrieval | Retrieve or diagnose through the existing route |
| Missing grant | Required access cannot be obtained through authorized means | Human hold naming the exact access and saved resume stage |
| Explicit user limit | User's stated limit prevents necessary action | Respect the limit and request the needed decision |
| Missing check evidence | Necessary output is absent or stale | Rerun the relevant check or correct stage |
| Invalid result | Missing, malformed, wrong invocation, stale, or contradicted by actual diff | Retain invalid artifact when present. Reconcile terminal owner, then fresh same stage. Execution failure or unchanged recurrence uses its error/recovery route |
| Missing log | Source and acceptance evidence remain inspectable | Restore the log without treating code as invalid |
| Existing dirty work | User already changed relevant files | Record base revision and existing diff, preserve ownership |
| Protected untracked work | Git status cannot show changed bytes | Retain needed content identity and inspect actual changes |
| Ignored runtime controls | Canonical records, frozen baseline, or active guidance do not appear in Git diff | Compare scoped parent-owned before versions/identities and audit ignored invocation outputs |
| Baseline mutation | Current SHA-256 differs from parent's retained expected digest | Preserve evidence, reject tampered basis, use Consultant and fresh Checker. Never rewrite the baseline or accept replacement digest |
| Unexpected path | Actual changes exceed assigned paths | Investigate without reset/delete, hold only for unresolved conflict or unsafe uncertainty |
| Active owner | Recorded native owner is still running | Native event wait or explicit terminal interruption before replacement |
| Unknown writer/effect | Spawn or external action may have succeeded | Reconcile exact identity and outcome before overlap or replay |
| Confirmed interruption | Owner terminal, current candidate and last accepted stage known | Fresh invocation of correct stage, regenerate stale evidence |
| Resolved blocked invocation | Human supplies missing input or authority | Verify resolution and dispatch fresh stage, leave old artifact blocked |
| Contract adoption | User authorizes a revised contract for interrupted work | Preserve history and reevaluate current candidate, no retroactive compliance claim |
| Arbiter gap | Original criterion lacks current evidence | Manager remediation, normal implementation/review, then Arbiter |
| Repeated Arbiter gap | Same criterion still lacks evidence | Require materially new evidence-backed remediation for Manager, otherwise Consultant. Human hold only without a defensible autonomous next step |
| Arbiter pass | Every original criterion passes and work is drained | Orchestrator closes the selected continuation control |
| Nonterminal event | Progress, helper completion, or unexpected owner | Continue native wait, no stage acceptance |
| Unsupported Goal/heartbeat | Current session lacks those controls | Record supported callback or interactive mode within authorization |
| Interactive continuation | No verified automatic chat resumption | Save exact owner and resume instruction, require user return |
| Callback continuation | Verified completion delivery to exact owning chat | Authorized yield/wait without claiming workflow closure |
| Late heartbeat wake | Closure, cancellation, or genuine Human hold saved | Stop only this run's heartbeat without dispatch |
| Missing stage capability | Fresh context or effective owner binding unavailable | Stop dependent execution and report exact gap |

## Static acceptance checklist

1. The Orchestrator names all twelve existing stage prompts and all four outcomes have legal routes.
2. Initial stage messages contain only the actual relative read-file instruction. Native settings stay outside the message.
3. Installed owner/helper defaults remain explicit. Codex L is never a stage owner. Planner never delegates.
4. Every coding packet has a concrete outcome, available prerequisites, a development check, and a handoff.
5. Checker freezes requirement-derived expectations and separate exact-byte SHA-256 before implementation exposure. Parent retains the expected digest outside the baseline.
6. Fixture assignment and result match run, invocation, stage, guidance, and pending route.
7. Two evaluated cycle pairings trigger Learning, including a successful second evaluation.
8. Learning preserves active guidance and baseline. Candidate activation occurs only at a safe boundary.
9. Recovery uses current evidence and a concrete next step. No default quota or missing-command-accounting hold exists.
10. Dispatch history establishes exact owners and outcomes without a capacity ledger.
11. Acceptance examines actual diff, relevant untracked paths, ignored outputs, and protected control files while preserving existing user work.
12. Interrupted recovery establishes terminal owner, current candidate, last accepted stage, and required fresh review.
13. Every invocation logs in UTC with a unique directory, exact filename, and fewer than 5120 bytes.
14. Handoffs provide targeted evidence. Summaries never replace proof and full transcripts are optional.
15. Installed runtime guidance remains usable after removal of the optional adapter source pack.
16. The actual baseline SHA-256 matches the external freeze, state, and assignment records. Its version label is not a content identity.
17. Goal and state select interactive mode. Native Goal fields are not applicable.

These checks concern documented consistency only. No native workflow executes in this fixture.
