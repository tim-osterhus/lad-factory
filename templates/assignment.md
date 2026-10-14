# Stage assignment

Run: <run-id>

Invocation: <invocation-id>

Stage: <exact stage name>

Original goal: run/current/goal.md

Accepted specification: <path or none>

Packet: <path or none>

Target workspace: <workspace>

Source identity: <revision plus dirty/untracked identity>

Instruction revision: <immutable guidance revision>

Guidance manifest: <path and manifest identity>

Instruction root: <explicit snapshot root>

Path bases: <inherited host working directory, package root, target workspace>

Pre-dispatch path snapshot: <full declared target/package inventory, protected/untracked content identities, and explicit exclusions>

Parent invocation: <none for top-level stages>

Result path: run/current/outputs/<invocation-id>/result.md

Log directory: historylog/<run-id>/<invocation-id>/

## Task and inputs

<Concrete task, work type, affected area, instructions, and input paths.>

## Writable paths

<Disjoint project paths and artifact directory. Exclude canonical run files.>

## Checks and acceptance

<Required checks, working directories, criteria, and unavailable prerequisites.>

## Review baseline

<Immutable baseline path and identity or not yet established.>

## Budgets and counters

<Finite attempts, local repair, planning repair, remediation, used counters, pending route.>
Current invocation reservations: <already-debited dispatch attempt and any replacement/recovery debit, with ledger references>.
Future invocation capacity: <remaining counts after those reservations>.
Copy all applicable `context/transitions.md` limits and used/remaining counters.
Include total-run and nested budgets. Do not allocate fresh limits on resume.
Zero future capacity does not revoke this invocation's valid reservation or authorize another invocation.

## Expected artifacts

<Outputs and evidence index entries.>

## Delegation

<Allowed work, host limits, worker ownership, and context/nested-models.md. Planner: none.>
