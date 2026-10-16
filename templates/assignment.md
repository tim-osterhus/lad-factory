# Stage assignment

Run: <run-id>

Invocation: <invocation-id>

Stage: <exact stage name>

Original goal: run/current/goal.md

Accepted specification: <path or none>

Packet: <path or none>

Target workspace: <workspace>

Source identity: <supplied revision plus dirty/untracked metadata, independently verified only at the stage's permitted source-access point>

Instruction revision: <immutable guidance revision>

Profile revision and adapter identity: <pinned installation files and manifest entries>

Effective owner binding: <exact model/provider, effort or supported equivalent, native configuration identity, chosen authorized fallback or none>

Guidance manifest: <path and manifest identity>

Instruction root: <explicit snapshot root>

Path bases: <inherited host working directory, package root, target workspace>

Pre-dispatch path snapshot: <full declared target/package inventory, protected/untracked content identities, and explicit exclusions>

Parent invocation: <none for top-level stages>

Result path: run/current/outputs/<invocation-id>/result.md

Log directory: historylog/<run-id>/<invocation-id>/

## Task and inputs

<Concrete task, work type, affected area, instructions, and ordered input paths.>
<For Checker: requirement-side inputs and already-supplied exceptions first. Separate and defer implementation/evidence appendices until baseline freeze.>

## Writable paths

<Disjoint project paths and artifact directory. Exclude canonical run files.>

## Checks and acceptance

<Required checks, working directories, criteria, and unavailable prerequisites.>
<Supply role-relevant route guards and downstream packet constraints needed for this assignment, without requiring full controller-policy preload.>

## Review baseline

<Immutable baseline path and identity or not yet established.>

## Budgets and counters

<Finite attempts, local repair, planning repair, remediation, used counters, pending route.>
Recovery counter scope: <originating packet lineage or this run's persistent unpacketized scope, with reconciled ledger references>.
Current invocation reservations: <already-debited dispatch attempt and any replacement/recovery debit, with ledger references>.
Future invocation capacity: <remaining counts after those reservations>.
The Orchestrator copies all applicable policy limits and used/remaining counters into this assignment.
Include total-run and nested budgets. Do not allocate fresh limits on resume.
Zero future capacity does not revoke this invocation's valid reservation or authorize another invocation.

## Expected artifacts

<Outputs and evidence index entries.>

## Delegation

<Allowed work, host limits, worker ownership, and context/nested-models.md when delegated. Planner: none, without nested-model input.>
