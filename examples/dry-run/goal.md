# Original goal

Run: fixture-greeting

Target workspace: illustrative greeting project

Original source: fixture specification below

Continuation mode: illustrative interactive mode. No native control is created.

Continuation authorization: none for execution

Native Goal fields are not applicable in interactive mode. This fixture does not create a Goal.

Native goal reference: not applicable

Native goal owning thread: not applicable

Native goal verified objective/status: not applicable

Native goal verification evidence: not applicable

Optional goal_id: not applicable

Heartbeat reference/owning chat/verification evidence: not applicable

Callback/interactive evidence: a real interactive run records the exact user-return resume instruction

## Original target specification

Implement a greeting function that trims a supplied name and returns Hello, followed by the name.
Reject names that contain only whitespace.

## Acceptance criteria

| ID | Criterion | Required evidence |
| --- | --- | --- |
| AC-01 | Return Hello, Ada for a name with surrounding whitespace | Current-source function check |
| AC-02 | Reject a whitespace-only name | Current-source rejection check |

## Boundaries and authority

Only the greeting function and its checks may change.
No release, remote write, or external communication is authorized.

## Source preservation

This file is the original illustrative specification.
No live source or native goal exists for this fixture.
