# agentic-system-kit

`agentic-system-kit` is a public skills.sh package for bootstrapping and maintaining repository-local Agentic Systems.

## Skills

- `bootstrap-agentic-system` `1.0.0`: design and install a repo-specific Agentic System after discovery, proposal, approval, and validation.
- `maintain-agentic-system` `1.0.0`: review and update an existing repo-local Agentic System when the target repository evolves.

## Versioning

Each public skill carries a `version` field in `SKILL.md` frontmatter and follows Semantic Versioning.

- Patch: wording fixes, clarifications, or compatible behavior fixes.
- Minor: backward-compatible capabilities, gates, templates, or validation improvements.
- Major: contract changes, removed behavior, renamed outputs, or breaking workflow changes.

When a public skill changes, increase that skill's version before exporting to `agentic-system-kit`.

## Install

```sh
npx skills add violabg/agentic-system-kit
```

## Boundary

These skills help create and maintain agent-system files. They do not modify application code, database schema, runtime configuration, or product tests unless a future repo-local system explicitly adds that behavior after approval.
