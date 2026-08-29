# lad-factory

`lad-factory` is a bounded static Lean Agentic Development (LAD) runtime for executing scoped software work packets through implementation, independent checking, recovery, and evidence-backed closure.

It is for operators who want autonomous coding work to remain inspectable and recoverable instead of treating an agent's final message as proof of completion.

**Status:** pre-alpha repository scaffold. No runnable controller exists yet. The first deliverable is the qualification suite described below; do not use this repository for production orchestration.

```bash
git clone https://github.com/tim-osterhus/lad-factory.git
cd lad-factory
```

There is nothing to install or run yet. The repository will expose checked commands as implementation lands.

## Frozen execution topology

The initial runtime target is one operator-approved graph, not a general workflow compiler:

```text
READY -> BUILDER -> CHECKER
                       | pass -> UPDATER -> TASK_DONE
                       | findings -> FIXER -> DOUBLECHECKER
                                              | pass -> UPDATER
                                              | exhausted -> TROUBLESHOOTER

Execution failure -> bounded retry -> TROUBLESHOOTER -> CONSULTANT
CONSULTANT -> existing stage | planning incident | WAITING_FOR_HUMAN
Root lineage drained -> ARBITER -> CLOSED | remediation | WAITING_FOR_HUMAN
```

The controller will own transitions, retry budgets, stale-result rejection, human gates, and closure. Agents will emit typed results, evidence, and recommendations; they will not rewrite the graph or declare their own output authoritative.

## Runtime truth

The implementation target has five non-negotiable properties:

- Every work packet names its scope, writable paths, checks, budgets, and legal next actions.
- Packet, attempt, transition, incident, wait, and closure state survives process restarts.
- Checker establishes an independent baseline that Fixer and Doublechecker cannot silently replace.
- Ordinary failures route through bounded Troubleshooter and Consultant recovery before asking for a human.
- Arbiter closes a root lineage only from its canonical contract and inspectable evidence.

These are design targets, not current feature claims.

## Qualification before claims

The runtime will not be called operational until an automated qualification track proves all of the following:

1. A normal packet reaches Builder, Checker, Updater, and closure.
2. A Checker finding reaches Fixer and Doublechecker against one immutable baseline.
3. A deterministic local failure reaches Troubleshooter and resumes at the interrupted stage.
4. A defective packet contract reaches Consultant, planning repair, and revised execution.
5. A planning-side failure is repaired without restarting unrelated work.
6. A controller kill, restart, stale result, and current-generation completion reconcile correctly.
7. An Arbiter gap produces bounded remediation and eventual closure.
8. A genuinely human-only action stops in a durable wait before the protected action occurs.

Passing requires zero unauthorized transitions, duplicate completions, or manual runtime-state edits. Each run must remain reconstructable from durable records and repository state.

## Deliberate limits

The first implementation will not include dynamic or agent-authored graph topology, a plugin system, a generic workflow-package layer, arbitrary fan-out and joins, unbounded retries, or chat history as authoritative state. Stable packet and evidence contracts can preserve later migration paths without putting those abstractions on the critical path now.

## License

Licensed under the [Apache License 2.0](LICENSE).
