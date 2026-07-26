# agentic-system-kit

`agentic-system-kit` is a public skills.sh package for bootstrapping and maintaining repository-local Agentic Systems.

## Skills

- `bootstrap-agentic-system`: choose this when a repository does not yet have a deliberate agent workflow, or when an existing setup is informal enough that it should be redesigned from first principles. The skill inspects workflow evidence, identifies costly failure modes, proposes a repo-specific Agentic System, waits for file-plan approval, then generates approved agents, skills, templates, gates, and validation notes. Use it by naming the target repository, preferred agent platform if known, and any workflow risks you already care about.
- `maintain-agentic-system`: choose this when a repository already has an Agentic System and the codebase, team workflow, validation commands, knowledge docs, or Bootstrap contract expectations have changed. The skill detects existing agent-system files, checks whether they still match the repo, current Bootstrap contract, and kit principles, proposes a maintenance plan, waits for approval, applies only approved updates, and validates the maintained contract. Use it by naming the repo, the changed workflow or pain point, and the platform you want to keep supporting.
- `create-work-item-planning-skills`: choose this after bootstrap when the repository needs ID-based bug and user-story planning. It creates both `plan-bug-from-id` and `plan-user-story-from-id` with a shared session-artifact contract, configurable tracker or local-Markdown adapter, bug cause-selection gate, and evidence-preserving user-story intake.
- `create-work-item-from-description`: choose this when a user wants to create a bug or user story through a configured tracker/MCP adapter or as a local Markdown record. It returns an ID and never creates a planning session.

All public skills are intentionally scoped to agent-system files: instructions, agents, skills, prompts, governance docs, knowledge docs, artifact templates, and session workflows. They do not modify application code, database schema, runtime configuration, or product tests unless a future repo-local system explicitly adds that behavior after approval.

## Which Skill Should I Pick?

Use `bootstrap-agentic-system` when you are creating the system: new repo, no clear gates, no durable planner/implementor/tester roles, no knowledge index, or a prompt collection that should become a coherent workflow.

Use `maintain-agentic-system` when you are repairing or evolving the system: stale instructions, missing validation commands, outdated knowledge docs, weak approval gates, changed issue workflow, or agent roles that no longer match how the repo works.

## Versioning

Skill versions live in [CHANGELOG.md](CHANGELOG.md), not in `SKILL.md` frontmatter. VS Code validates skill frontmatter for supported discovery fields, and unsupported metadata such as `version` can produce warnings. Keep `SKILL.md` frontmatter focused on fields the agent uses to find and run the skill, such as `name`, `description`, `argument-hint`, and `disable-model-invocation`.

Each public skill follows Semantic Versioning.

- Patch: wording fixes, clarifications, or compatible behavior fixes.
- Minor: backward-compatible capabilities, gates, templates, or validation improvements.
- Major: contract changes, removed behavior, renamed outputs, or breaking workflow changes.

When a public skill changes, increase that skill's version in the changelog before exporting to `agentic-system-kit`. The `Current Skill Versions` section in the changelog is the machine-readable release ledger used by the package checks.

## Install

```sh
npx skills add violabg/agentic-system-kit
```

The package keeps skills under grouped paths such as `skills/agentic-system/bootstrap-agentic-system` and `skills/work-items/create-work-item-from-description`.

That grouped directory layout lets `npx skills add` offer a parent group choice for installing a whole set at once while still allowing users to expand the group and select individual skills one by one.

Prompted selection during `npx skills add` is still controlled by the `skills` CLI and the environment where it runs. If the CLI detects a host agent session, it may switch to non-interactive installation and install all discovered skills automatically.

If you want explicit selection today, use CLI flags such as `--list`, `--skill`, and `--agent`, or run the command from a normal shell outside an auto-detected agent session.
