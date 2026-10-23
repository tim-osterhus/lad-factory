# Default Codex model preset

Preset revision: `codex-default-r1`. This preserves the original LAD assignments. Copy these rows into the installed profile only after selecting this preset. Account access remains unverified until established from existing metadata or user confirmation. Do not send inference requests to test it.

| Owner | Model | Native effort |
| --- | --- | --- |
| Orchestrator | gpt-6.1-sol | high |
| Recon | gpt-6.1-sol | high |
| Planner | gpt-6.1-sol | high |
| Manager | gpt-6.1-sol | xhigh |
| Builder | gpt-6.1-sol | high |
| Checker | gpt-6.1-sol | high |
| Fixer | gpt-6.1-sol | high |
| Doublechecker | gpt-6.1-sol | high |
| Troubleshooter | gpt-6.1-sol | xhigh |
| Consultant | gpt-6.1-sol | xhigh |
| Updater | gpt-6.1-sol | medium |
| Learning | gpt-6.1-sol | high |
| Arbiter | gpt-6-astra | xhigh |

| Helper tier | Model | Native effort | Task boundary |
| --- | --- | --- | --- |
| L | gpt-6-luna | max | Bounded work with concrete inputs and acceptance checks |
| SM | gpt-6.1-sol | medium | Scoped discovery and general judgment |
| SH | gpt-6.1-sol | high | Coupled implementation, debugging, integration |
| SX | gpt-6.1-sol | xhigh | Difficult root cause, architecture, adversarial review |

For this preset, Luna never owns a top-level stage and helpers never use Astra. These restrictions belong to this preset, not every harness or profile. Planner never delegates under the shared LAD contract. Other parents select the smallest suitable helper tier within explicit user limits and actual host constraints.

Resolve the provider route, exact native config identities, permissions, and explicit authorized fallbacks separately. No fallback is authorized by this preset. Unsupported or unavailable bindings require a profile decision before dispatch.
