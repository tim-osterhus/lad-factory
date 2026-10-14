# Work packet

Run: fixture-greeting

Packet: fixture-p01

Specification: examples/dry-run/goal.md

Original criteria: AC-01, AC-02

Instruction revision: fixture-guidance-v1, illustrative only

Guidance manifest: illustrative path/hash inventory, not generated

Depends on: none

Order: 1

## Outcome

Trim a name, return the greeting, and reject an empty trimmed name.

## Inputs and constraints

Use the original fixture goal and its two criteria.
The target implementation and source identities are illustrative.

## Writable paths

Illustrative greeting function and checks only.

## Implementation detail

Trim once, reject an empty result, then form the greeting.

## Acceptance and checks

| Criterion | Check | Required evidence |
| --- | --- | --- |
| AC-01 | Name with surrounding whitespace | Current source and observed greeting |
| AC-02 | Whitespace-only name | Current source and observed rejection |

## Budgets

Use the illustrative default limits and counters in state.md, following context/transitions.md.
Two evaluated Fixer cycles trigger Learning before the saved route.
Failed, invalid, and interrupted attempts still debit dispatch limits.

## Handoff

Current-source review evidence for both criteria.
