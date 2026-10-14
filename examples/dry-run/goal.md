# Original goal

Run: fixture-greeting

Target workspace: illustrative greeting project

Original source: fixture specification below

Continuation mode: illustrative Goal mode only. No native control is created.

Native goal authorization: none. This fixture does not create a goal.

Native goal reference: not created in this structural fixture

Native goal owning thread: none

Native goal verified objective/status: not observed

Native goal verification evidence: none

Optional goal_id: not exposed

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
