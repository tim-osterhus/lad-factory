# Checker baseline

Run: fixture-greeting

Packet: fixture-p01

Baseline identity: fixture-baseline-v1

Instruction revision: fixture-guidance-v1, illustrative only

Guidance manifest: illustrative path/hash inventory, not generated

Expected source: fixture-source-before-diff

Recorded before implementation diff: yes, illustrative sequence only

| Criterion | Expected behavior | Check |
| --- | --- | --- |
| AC-01 | Surrounding whitespace is removed | Input with surrounding whitespace |
| AC-02 | Whitespace-only name is rejected | Empty trimmed name |

Accepted pre-existing issues: none in this fixture.

This identity remains unchanged through both repair cycles.
These statements describe expected behavior, not executed checks.
