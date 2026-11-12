# agentic-system-kit

Skills that install and maintain a repository-local agentic system for AI coding clients. The kit holds two independent systems. Pick one per repository.

| System | Skills | State |
| --- | --- | --- |
| **Orchestrator system** | `bootstrap-orchestrator-system`, `maintain-orchestrator-system`, `improve-orchestrator-system` | current |
| Planner/Implementor system (legacy) | `bootstrap-agentic-system`, `maintain-agentic-system` | frozen: still installable, no longer developed |

## Install

```sh
npx skills add violabg/agentic-system-kit
```

The skills CLI offers two groups: **Agentic System — orchestrator** and **Agentic System — legacy**. Pick the group of the system you want, or expand a group to pick single skills. To choose without the prompt:

```sh
npx skills add violabg/agentic-system-kit --skill bootstrap-orchestrator-system --skill maintain-orchestrator-system --skill improve-orchestrator-system
```

When the CLI runs inside an agent session it may install every skill without asking; run it from a normal shell to choose.

## Orchestrator system

One **orchestrator** role drives the workflow the developer chooses:

- `DESIGN`: a structured design the orchestrator verifies against itself and the developer reviews and approves in a review document, then implementation and review.
- `FAST_IMPLEMENTATION`: a quick path for simple or mechanical changes, with no design and no approval step.
- `DOCUMENTATION`: a guide written from a template, then reviewed.

A local Node runtime serves the workflow one instruction at a time and owns the session store, the design, the mechanical checks and the approval gate. In `DESIGN` the orchestrator never writes production code: it reviews its own design adversarially before you approve it, hands each batch of operations to the code implementor running in its own context, and reviews every work unit itself. In `FAST_IMPLEMENTATION` it implements the change directly, with its build and tests, and checks the result against the knowledge rules it registered. In both it gets codebase facts from read-only explorers that run in parallel. In `DOCUMENTATION` a documentation reviewer checks the guide. The design verifier and implementation verifier roles are still installed, though no workflow step starts them. Two more roles answer project questions (`ask`) and build the project knowledge (`knowledge-builder`).

- **`bootstrap-orchestrator-system`** installs the system. It asks which clients the team uses (Claude Code, Codex, GitHub Copilot in VS Code, OpenCode, Cursor, or another), where sessions should live (inside the repository and ignored by git, or outside it), and how the tracker and other integrations are reached. It then renders every file with a deterministic installer, merges client settings without losing existing ones, and verifies each client.
- **`maintain-orchestrator-system`** upgrades an installation to a newer kit, applies changed decisions, records an approved local runtime fix, or audits the installation. It merges the files the repository customized instead of overwriting them.
- **`improve-orchestrator-system`** audits one or more sessions by id: token use, adherence to the served flow, and gaps in the runtime, the knowledge or the issue. Each finding goes to its own action after you approve it: a local runtime fix, a report for the kit's maintainer, a brief for `knowledge-builder`, or an update through `manage-work-item`. It reads the session and the client transcripts you confirm, and never changes a session.

These skills change only agent-system files: role files, skills, routers, the runtime and its config, workflows, contracts, client settings for the runtime command, guides and the installation records. They never touch application code.

## Legacy: Planner/Implementor system

`bootstrap-agentic-system` and `maintain-agentic-system` install and maintain the earlier system built around Planner, Implementor and Integration Tester roles with gates written in the role bodies. They remain available unchanged for repositories that use them. They receive no new features. A repository moving to the orchestrator system installs it with `bootstrap-orchestrator-system`. This is a new installation, not an upgrade of the legacy one.

## Versions

Each skill keeps its version in the `CHANGELOG.md` inside its own folder, which travels with the installed skill. The orchestrator installer records the kit version it installed in the target repository's manifest; the maintainer compares it with the installed kit.
