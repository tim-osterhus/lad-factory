# Work packet

Run: fixture-greeting

Packet: fixture-p01

Specification: examples/dry-run/goal.md

Original criteria: AC-01, AC-02

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

Two Fixer cycles before Troubleshooter.
One bounded Troubleshooter repair and one Consultant assessment.
One scoped planning repair and one Arbiter remediation plan.

## Handoff

Current-source review evidence for both criteria.
