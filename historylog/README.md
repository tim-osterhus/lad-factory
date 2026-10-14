# Run history

Generated logs live under `historylog/<run-id>/<invocation-id>/`.
Each invocation creates one UTF-8 Markdown log smaller than 5120 bytes.
Use UTC and `StageName_HHMM-MMDDYY.md`.

Nested workers use their owning stage's name and record their specific role in the body.
Unique invocation directories prevent timestamp collisions.

Record assignment, outcome, evidence paths, decisions, and unresolved issues.
Omit secrets. Generated directories are ignored.
Preserve required evidence under the target project's retention policy.
