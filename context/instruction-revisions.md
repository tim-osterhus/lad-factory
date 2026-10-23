# Instruction revisions and change review

## Stable guidance

Create one versioned guidance snapshot at `run/current/instructions/<revision>/` for each accepted guidance revision.
Include `AGENTS.md`, `SETUP.md`, `prompts/`, `context/`, `templates/`, and `docs/setup.md`.
Include the installed `installation/profile.md` and self-contained `installation/adapter.md` at those same relative paths.
The adapter contains identified sections for the complete primary guide, selected secondary guides, and cross-harness contract when used.
Required installed/native files live outside optional `adapter-templates/`. Runtime guidance never imports that source folder.

Record the snapshot revision and root in bootstrap, state, and assignments.
Keep guidance revision separate from target source identity.
Read stage prompts and all their guidance from the assigned snapshot throughout the packet.
Never edit an active snapshot or change active-run model bindings through mutable installation files.

Use the pinned profile and adapter. Check effective native settings and precedence honestly against that binding.
Investigate configuration drift before dependent dispatch. Repeated hashing and recursive manifests are not required.
A host or model change requires a prepared future run.

The host working directory remains inherited.
Resolve each initial prompt relative to the observed directory, including `../` segments when needed.
For example: `Read lad-factory/run/current/instructions/rev-01/prompts/builder.md and follow instructions.`
Send only that line with the actual path. Never use an absolute initial stage-prompt path.

Within a stage prompt, guidance paths use its instruction root, the parent of `prompts/`.
A snapshot stage locates bootstrap at `../../../bootstrap.md` relative to its `prompts/` directory.
Runtime paths use the package root in bootstrap. Project paths use the assigned target workspace.
Bootstrap records all path bases. Reading a file never changes the working directory.

## Learning activation

Learning writes a separate candidate with proposed guidance changes and supporting evidence.
It cannot edit package guidance, active snapshots, review baselines, or application code.
An accepted no-op leaves the revision unchanged.
Retain the current packet's revision through its review, Updater, and completion.

Activate an accepted candidate after the packet completes, before the next packet or a new remediation packet.
Explicitly complete or supersede the prior packet and preserve its review basis.

The Orchestrator checks authorized scope, contradictions, and original criteria before activation.
Record the old/new revisions, changed guidance paths, safe boundary, and affected evidence.
Apply accepted changes to authorized package paths and create one new snapshot for the revision.
Existing assignments and baselines retain their original revision.
Changed requirements or an invalid review basis require Consultant review and a fresh Checker baseline.

Example: the second repair passes and Learning proposes clearer Builder checks.
Updater finishes under `rev-01`. Packet two may start under accepted `rev-02`.
Packet one's baseline and results still cite `rev-01`.

## Change review and user-work protection

Writable paths are instructions, not a filesystem sandbox.
Workers may inherit parent permissions. Never claim prompts enforce isolation.

Before dispatch, record the target/package roots, base Git revision, and relevant existing user changes.
Use existing staged/unstaged diffs and relevant untracked paths to distinguish prior work from the assignment.
For protected pre-existing untracked or non-Git files, retain content identities only where needed to detect mutation.
Normally exclude dependencies, caches, and build outputs unless they matter to the task.
Do not require full-tree inventories, recursive hash records, or environment archives.

After the owner and descendants finish, inspect the actual diff and relevant untracked changes.
Include additions, deletions, renames, mode changes, and binary changes when present.
Compare actual changes with assigned paths and existing user work.

Each nested parent checks helper changes and integration. The Orchestrator checks the aggregate changes independently.
Keep canonical bookkeeping changes distinct from worker output.
Review and Learning stages receive no application-code write authority.

Investigate unexpected paths and attribute differences before acceptance.
Preserve files and user work. Never reset, delete, or overwrite them to hide an unexpected change.
An unresolved protected-work conflict or unsafe uncertainty requires the exact human decision.
Missing audit paperwork alone can be regenerated. It does not invalidate otherwise inspectable code.
