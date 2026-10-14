# Checker baseline

Run: fixture-greeting

Packet: fixture-p01

Baseline identity: fixture-baseline-v1

Instruction revision: fixture-guidance-v1, illustrative only

Guidance manifest: illustrative path/hash inventory, not generated

Supplied source identity: fixture-source-before-review, assignment metadata only

Recorded and frozen before any target implementation access: yes, illustrative sequence only

| Criterion | Expected behavior | Check |
| --- | --- | --- |
| AC-01 | Surrounding whitespace is removed | Input with surrounding whitespace |
| AC-02 | Whitespace-only name is rejected | Empty trimmed name |

Requirement-side pre-existing exceptions: none in this fixture.

Actual source identity verification and discovery of additional pre-existing issues occur after freeze.
Those observations remain separate from this immutable baseline.

This identity remains unchanged through both repair cycles.
These statements describe expected behavior, not executed checks.
