# Native pilot report

On October 14, 2026, a disposable Python receipt fixture completed a native LAD qualification run.
Fresh final Arbiter review passed all six original criteria. The owning root chat then completed its native Goal after independent QA passed.

This report summarizes retained private receipts and audits. It does not publish those records or make them publicly reproducible.
The [protocol fixture](../dry-run/README.md) remains an illustrative walkthrough, separate from this observed run.

## Target and recorded identities

The target used Python's standard library and three immutable tests.
The accepted changes implemented integer-cent display and label normalization with `strip().casefold()`.
Existing validation and aggregation behavior remained covered by the tests.

| Identity | Recorded value |
| --- | --- |
| Fixture Git base | `c4528a5bbcb992dc0e6a9ce1aaae63415e898854` |
| Final `receipt.py` SHA-256 | `f735ba089177591c30774a4acec506eb66290f67bc61b4d77e46759c9a948f45` |
| Immutable `test_receipt.py` SHA-256 | `ed3d0748b11ab4e766b966bff72270d5eb06081d1a4b1cbc4074eb7d17a8f3e2` |
| Frozen guidance revision | `rev-qa-freeze` |
| Frozen guidance manifest SHA-256 | `e8ae733d2bf0ccc575f4e87e41bfa69f700510ac28805703562ecc6031e3f56e` |
| Frozen guidance entries verified | 28 regular files |

These hashes identify the private fixture and frozen guidance. They are not hashes of this report or the current package revision.

## Six original criteria

| Criterion | Observed result |
| --- | --- |
| APP-1: application acceptance | Fresh final `python3 -m unittest -v` exited 0. All three tests passed: display, normalized totals, and invalid items |
| NATIVE-1: normal packet | Distinct fresh Recon, Planner, Manager, Builder, Checker, and Updater owners completed the normal packet. Its scoped two-test acceptance did not claim full-goal completion |
| NATIVE-2: review and repair | Independent Checker reproduced an injected normalization regression. Two distinct Fixer/Doublechecker pairs evaluated repairs against the preserved valid baseline. Cycle two passed, then required Learning recorded a no-op before Updater |
| NATIVE-3: interruption and resume | An active Builder published a checkpoint. The operator interrupted that exact owner. Native status established terminal interruption, disk uncertainty was reconciled, and a distinct fresh Builder resumed successfully |
| NATIVE-4: incomplete evidence | First Arbiter rejected the incomplete submission with two evidence gaps. One reserved R1 remediation episode ran Manager, Builder, independent Checker, and Updater. Restored unchanged primary proof supported fresh final Arbiter acceptance |
| NATIVE-5: native records | Host receipts, assignments, outcomes, logs, source identities, and declared-path audits agreed. The root retained observed Goal creation/current-state evidence and actual completion after final review |

There were 23 retained top-level stage dispatches, including blocked, interrupted, and rejected attempts.
The ledger retained two evaluated Fixer cycles, one invalid Checker replacement, and one Arbiter remediation episode without resetting counters.
Final Arbiter used five of its twelve allowed check-command invocations, each below the 600-second limit.
Historical stage logs were 1,124–2,192 bytes. The final Arbiter log was 1,776 bytes, below the 5 KiB contract.

## Commands and checks

The normal display packet ran this scoped command in the fixture root and passed both tests:

```sh
python3 -m unittest -v test_receipt.ReceiptAcceptance.test_display test_receipt.ReceiptAcceptance.test_invalid_items
```

Final Arbiter independently ran the full suite in the fixture root:

```sh
python3 -m unittest -v
```

The full suite passed 3/3, including exact integer arithmetic, normalized aggregation, invalid inputs, and empty input.
A fixture-only audit command verified all 28 guidance entries and current source/test identities.
A read-only lineage query initially failed on an older audit representation, then passed after diagnostic correction.
Both diagnostic receipts remain retained. The final aggregate path audit reported no unexpected changes.
Those audit helpers and raw process receipts remain private and are not package runtime commands.

## Controlled injections

The display omission and initial normalization defect were deliberately seeded fixture controls.
After a truthful Builder pass, the operator injected `return label` before Checker.
After a truthful first Fixer pass, the operator injected `return label.strip()` before Doublechecker.
Earlier passing checks remained attached to their earlier source identities.
The second Fixer restored `strip().casefold()`, and the second Doublechecker passed without another injection.

The checkpoint interruption and first Arbiter's omitted primary interruption receipt were also deliberate controls.
The restored receipt matched its preserved original bytes.
These cases demonstrate controlled qualification paths. They are not evidence of naturally occurring implementation mistakes.

## Natural incidents retained

The first Recon blocked on changing OS metadata. Its differences and dispatch debit remained retained.
A prospective, explicitly approved metadata exclusion allowed intake to resume. The metadata actor was unobserved.

The first normalization Checker opened an embedded implementation diff before freezing its baseline.
Its result was rejected, and a fresh replacement established a valid baseline before review.
The explicit ordering rule competed with broader cited-input preloading. The incident record preserves both the violation and that ambiguity.
The historical replacement assignment also contained generic `0/1` wording beside an explicit reserved `1/1` replacement.
The spent ledger debit governed, and the inconsistent historical wording remains preserved.

## Host boundary and later guidance

Receipts record requested API model, effort, fresh context, native task identity, and observed host outcomes.
They do not establish the provider's internal model identity or expose hidden tool-call identifiers.
Every stage used the prescribed owner settings. Only Arbiter requested `gpt-6-astra` with `xhigh` effort.
Pilot assignments restricted nested delegation, and no nested workers ran. Public non-Planner helper permissions were therefore not exercised.

The audit covered the declared disposable fixture with explicit exclusions. It did not prove host-wide filesystem isolation.
No scheduler, idle/unloaded-chat wakeup, Cloud compatibility, deployment, publication, or remote execution was tested.
The heartbeat fallback and clarified Checker/reservation wording are post-pilot documentation changes.
They were not native-tested by this run. See the current [continuation policy](../../context/continuation.md) for their gates and limits.
