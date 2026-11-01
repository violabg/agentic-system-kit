# Orchestrator system skills

| Skill | Use it to |
| --- | --- |
| `bootstrap-orchestrator-system` | install the orchestrator agentic system into a repository |
| `maintain-orchestrator-system` | upgrade, change, patch or audit an installation |
| `improve-orchestrator-system` | audit one or more sessions for token waste, drift from the flow, and gaps in the runtime, the knowledge or the issue |

All run in a plain client session, never inside one of the roles, and write nothing before you approve. Maintenance uses the installer that ships with the Bootstrap skill, so install those two together. The Improver sends a local runtime fix through the Maintainer.
