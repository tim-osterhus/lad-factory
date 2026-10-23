# Work packet

Run: <run-id>

Packet: <packet-id>

Specification: run/current/spec.md

Original criteria: <AC identifiers>

Instruction revision: <packet's guidance revision>

Depends on: <accepted prior packets or none>

Order: <sequential position>

## Outcome

<Concrete behavior this packet establishes.>

## Inputs and prerequisites

<Relevant sources, contracts, preserved behavior, existing issues, and prerequisites available before this packet.>

## Writable paths

<Explicit project paths without an arbitrary file-count ceiling.>

## Implementation detail

<Only necessary decisions and steps.>

## Acceptance and development checks

| Criterion | Check Builder can run during implementation | Required evidence |
| --- | --- | --- |
| <AC-ID> | <command or observation and working directory> | <examined source, status, relevant output> |

<Reconsider the packet if its first meaningful verification requires later work.>
<Independent review still follows implementation.>

## Authority and limits

<Development edit/test authority, separate external-action gates, and applicable explicit user or host limits.>

## Handoff

<Concrete outputs and contracts available to the next packet, unresolved issues, and human gates.>
