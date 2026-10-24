# agentic-system-kit

Skills that install and maintain a repository-local agentic system for AI coding clients. The kit holds two independent systems. Pick one per repository.

| System | Skills | State |
| --- | --- | --- |
| **Orchestrator system** | `bootstrap-orchestrator-system`, `maintain-orchestrator-system` | current |
| Planner/Implementor system (legacy) | `bootstrap-agentic-system`, `maintain-agentic-system` | frozen: still installable, no longer developed |

## Install

```sh
npx skills add violabg/agentic-system-kit
```

The skills CLI offers two groups: **Agentic System — orchestrator** and **Agentic System — legacy**. Pick the group of the system you want, or expand a group to pick single skills. To choose without the prompt:

```sh
npx skills add violabg/agentic-system-kit --skill bootstrap-orchestrator-system --skill maintain-orchestrator-system
```

When the CLI runs inside an agent session it may install every skill without asking; run it from a normal shell to choose.

## Orchestrator system

One **orchestrator** role drives the workflow the developer chooses:

- `DESIGN`: a structured design the developer reviews and approves in a review document, then implementation and verification.
- `FAST_IMPLEMENTATION`: a quick path for simple or mechanical changes.
- `DOCUMENTATION`: a guide written from a template, then reviewed.

A local Node runtime serves the workflow one instruction at a time and owns the session store, the design, the mechanical checks and the approval gate. The orchestrator never writes production code: it hands the code and the verifications to delegates (code implementor, design verifier, implementation verifier, documentation reviewer), each running in its own context. Two more roles answer project questions (`ask`) and build the project knowledge (`knowledge-builder`).

- **`bootstrap-orchestrator-system`** installs the system. It asks which clients the team uses (Claude Code, Codex, GitHub Copilot in VS Code, OpenCode, Cursor, or another), where sessions should live (inside the repository and ignored by git, or outside it), and how the tracker and other integrations are reached. It then renders every file with a deterministic installer, merges client settings without losing existing ones, and verifies each client.
- **`maintain-orchestrator-system`** upgrades an installation to a newer kit, applies changed decisions, or audits the installation. It merges the files the repository customized instead of overwriting them.

Both skills change only agent-system files: role files, skills, routers, the runtime and its config, workflows, contracts, client settings for the runtime command, guides and the installation records. They never touch application code.

## Legacy: Planner/Implementor system

`bootstrap-agentic-system` and `maintain-agentic-system` install and maintain the earlier system built around Planner, Implementor and Integration Tester roles with gates written in the role bodies. They remain available unchanged for repositories that use them. They receive no new features. A repository moving to the orchestrator system installs it with `bootstrap-orchestrator-system`. This is a new installation, not an upgrade of the legacy one.

## Versions

Each skill keeps its version in the `CHANGELOG.md` inside its own folder, which travels with the installed skill. The orchestrator installer records the kit version it installed in the target repository's manifest; the maintainer compares it with the installed kit.
