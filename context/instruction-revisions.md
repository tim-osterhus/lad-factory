# Instruction revisions and path audit

## Immutable guidance

Before dispatch, copy the active package guidance into `run/current/instructions/<revision>/`.
Include `AGENTS.md`, `SETUP.md`, all `prompts/`, `context/`, `templates/`, and `docs/setup.md`.
Include the installed `installation/profile.md` and self-contained `installation/adapter.md` at those same relative paths.
The adapter file contains complete identified sections for the primary guide and every selected secondary guide.
Cross-harness installations also include the full shared cross-harness contract in that file. Separate mutable guide imports are forbidden.

The profile includes every effective stage/helper model, effort, native configuration identity, and explicitly authorized fallback.
Record its explicit revision and the selected adapter identity in bootstrap, state, and assignments.
Required installed/native files live outside optional `adapter-templates/`. Do not snapshot or depend on that source folder.
Verify native files against their recorded identities before dispatch and acceptance. Changed settings require reconciliation.
When the host needs native files outside the snapshot, preserve their exact identity and reject configuration drift.

Do not include generated run records, logs, candidate changes, or manifests in that guidance set.
Write a sorted relative-path and SHA-256 manifest beside the snapshot at `run/current/manifests/<revision>.md`.

Each entry records a package-relative path, regular-file type, byte count, and SHA-256 of the exact file bytes.
Use slash-separated paths and lexicographic ordering. Reject unexpected file types before snapshotting.
Hash exact bytes without newline or encoding conversion. SHA-256 values use 64 lowercase hexadecimal characters.
Derive the revision from the ordered entries, or use a unique identifier bound to that exact manifest.

The manifest does not hash itself. No artifact depends on its own digest.
Verify copied bytes against the manifest before using the snapshot. Never modify an active snapshot.

Assignments, state, results, review baselines, and nested work orders record the revision and manifest path.
Keep the guidance identity separate from the target code revision and dirty-work identity.
Spawn stages by reading their snapshot prompt, not the mutable package prompt.
Hash verification before dispatch and acceptance detects changed snapshot files.
Read guidance from that snapshot throughout the invocation, including contracts and templates.
The Orchestrator follows its pinned snapshot for routing and acceptance throughout the packet.
Every invocation uses the pinned profile and adapter, never changed mutable installation files.
Installation reconfiguration affects future runs only. Do not change active-run model bindings or native controls midway.
Learning activation preserves the run's profile and adapter bytes. A model or host change requires an explicitly prepared future run.

The host working directory remains inherited. Initial prompt paths must resolve from that directory.
For example: `Read lad-factory/run/current/instructions/rev-01/prompts/builder.md and follow instructions.`
That single line contains no extra work description.
Compute the actual relative path from the observed inherited host directory, using `../` segments for locations outside it.
Initial stage prompts must not use absolute paths. Relative paths do not require a working-directory spawn control.

Within a loaded stage prompt, guidance paths resolve relative to its instruction root, the parent of `prompts/`.
Runtime paths such as `run/current/assignment.md` resolve relative to the package root in the bootstrap record.
A snapshot stage can locate bootstrap at `../../../bootstrap.md` relative to its `prompts/` directory.
Bootstrap records explicit package, target, inherited working directory, and instruction-root paths.
Project paths resolve relative to the target workspace, unless an assignment names another explicit base.
Never assume reading a file changes the working directory.

## Learning activation

Learning writes a candidate artifact with proposed guidance changes and supporting evidence.
Learning cannot edit active snapshots, package guidance, review baselines, or application code.
An accepted no-op leaves the revision unchanged.
For a candidate, retain the packet's revision through its remaining review, Updater, and completion.

Activate a candidate only after the current packet completes, before the next packet, or before a documented bounded remediation episode.
A remediation boundary starts a new versioned packet after the prior packet is completed or explicitly superseded.
Preserve the superseded packet's guidance and review basis.

The Orchestrator checks scope, contradictions, and preserved original criteria before accepting activation.
If activation exceeds the user's authorized scope, obtain the exact missing authority first.
Record old/new revisions, changed guidance paths, safe boundary, and affected evidence.

Apply accepted candidate changes only to assigned package paths, create a new immutable snapshot, and verify its manifest.
Existing assignments keep their original snapshot and review basis.
Before the next packet starts, record its accepted new revision and preserve the previous revision in lineage.
Remediation must explicitly identify any new review baseline required by changed guidance.

Example: cycle two passes, Learning proposes clearer Builder checks, and Updater finishes under `rev-01`.
Before packet two, accept the candidate as `rev-02`. Packet one's baseline and results still cite `rev-01`.
If Learning returns no-op or fails, packet two retains `rev-01` unless another explicitly accepted activation occurs.

## Changed-path acceptance

Writable paths are instructions, not a filesystem sandbox.
Native workers may inherit the parent's permissions. Never claim a prompt enforces isolation.

Before dispatch, the parent declares target/package audit roots and records a full inventory of that scope.
Include protected, ignored, and existing untracked paths unless they are explicitly excluded.
Record exact content hashes for existing files, including binary files, and record types, modes, and symlink targets.
Git status alone cannot identify changes to an already-untracked file's bytes.
For Git targets, also record base revision, status, and staged/unstaged differences.
Use the same inventory and content identities for non-Git paths.

List every excluded path or directory and its reason, such as Git internals or declared dependency/output directories.
Exclusions limit the audit's coverage. They do not grant write permission or imply host-wide filesystem enforcement.
Do not exclude protected user files that require change detection.
Refuse acceptance if a protected or out-of-scope change cannot be attributed because the inventory lacks coverage.
Record pre-existing user work separately so acceptance cannot attribute it to the stage.
Record exact identities for authorized parent bookkeeping writes after the snapshot, such as recording the spawned native agent ID.
Compare those parent updates separately. They do not expand worker permissions or excuse unverified canonical edits.

After all descendants finish, compare actual bytes and inventory against the pre-dispatch snapshot.
Capture additions, deletions, renames, modes, and binary changes as well as text differences.
Validate every changed path against the stage's explicit writable paths, including evidence/log artifacts and package guidance.
Each nested parent performs the same audit against each helper's disjoint assigned paths, then checks integration.
The stage reports those helper audits. The Orchestrator checks the aggregate difference independently before acceptance.
Review and Learning stages receive no application-code write permission.

Unexpected changes require rejection and quarantine by recorded differences and a hold.
Preserve the files and user work. Do not reset, delete, or overwrite them to hide the violation.
Record the exact paths and ask for the needed conflict resolution before proceeding.
The audit detects violations after execution. Stronger isolation is outside this package's initial single-stage design.
