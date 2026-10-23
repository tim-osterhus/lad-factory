# Work packet

Run: fixture-greeting

Packet: fixture-p01

Specification: examples/dry-run/goal.md

Original criteria: AC-01, AC-02

Instruction revision: fixture-guidance-v1, illustrative only

Depends on: none

Order: 1

## Outcome

Trim a name, return the greeting, and reject an empty trimmed name.

## Inputs and prerequisites

Use the original fixture goal and its criteria.
The function and test environment are illustrative and available before this packet.
No later packet is required to verify this behavior.

## Writable paths

Illustrative greeting function and checks only.

## Implementation detail

Trim once, reject an empty result, then form the greeting.

## Acceptance and development checks

| Criterion | Check Builder can run during implementation | Required evidence |
| --- | --- | --- |
| AC-01 | Input with surrounding whitespace, illustrative target directory | Current source and observed greeting |
| AC-02 | Whitespace-only input, illustrative target directory | Current source and observed rejection |

Checks are illustrative, not executed. Independent review follows implementation.

## Authority and limits

Illustrative development edits and tests only. No external actions.
No user limits supplied. Two evaluated repair cycles trigger Learning under transition policy.

## Handoff

Current-source review evidence for both criteria and the accepted greeting behavior.
