# Checker freeze record

Run: fixture-greeting

Packet: fixture-p01

Baseline: examples/dry-run/baseline.md

Baseline version label: fixture-baseline-v1

Baseline SHA-256: 808c1a5518bb13e4e77d18fd168857b5c12dcac755842f797b0930b5339eb8b6

In a live run, Checker records this digest before implementation access.
The Orchestrator verifies it and retains the expected value in canonical state before downstream dispatch.
This fixture records the actual file digest for static consistency only. No Checker invocation or native freeze occurred.
