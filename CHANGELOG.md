# Changelog

This package tracks public skill versions here instead of in `SKILL.md` frontmatter. VS Code skill metadata validation can warn on unsupported frontmatter fields, so `SKILL.md` stays focused on invocation and discovery metadata.

## Current Skill Versions

- `bootstrap-agentic-system`: `1.3.2`
- `maintain-agentic-system`: `1.0.0`
- `create-work-item-planning-skills`: `1.1.0`
- `create-work-item-from-description`: `1.0.0`

## 2026-07-25

### Package Layout

- Grouped exported skills under `agentic-system` and `work-items` to keep the public package organized as a catalog-style skills repository.
- Added `skills.sh.json` to group the repository page on skills.sh while leaving CLI install behavior to the upstream `skills` tool.

## 2026-07-26

### Package Layout

- Moved the source package itself to the same nested `skills/<group>/<skill>` layout used by the exported repo so `npx skills add` can offer one-click group selection as well as per-skill selection.
- Updated the public export, publish, and version-check scripts to discover grouped skills recursively instead of assuming a flat `public-package/skills/*` layout.
- Preserved folder-level metadata files inside `skills/` during export so grouped category docs can ship to the published repo instead of being dropped.

### Group Metadata

- Added category `README.md` files under grouped skill folders structure more closely for installer discovery.

### `create-work-item-planning-skills` 1.1.0

- Added canonical ID-planning gates for bug cause selection and evidence-preserving user-story intake.
- Required generated planning skills to preserve tracker content as Markdown, save selected bug-cause analysis, and resume the repository planning workflow only after evidence is recorded.

## 2026-07-24

### Package

- Moved public skill version tracking from `SKILL.md` frontmatter into this changelog.
- Expanded the README with skill-selection guidance, usage notes, and the versioning policy.

### `bootstrap-agentic-system` 1.2.2

- Required bootstrap proposals to surface glossary conflicts and ask the user how to resolve them before file-plan approval.

### `bootstrap-agentic-system` 1.3.0

- Added a final post-bootstrap proposal for `create-work-item-planning-skills`, including mandatory safe session persistence for generated bug and user-story planning skills.

### `create-work-item-planning-skills` 1.0.0

- Initial release for generating `plan-bug-from-id` and `plan-user-story-from-id` with tracker or local-Markdown session adapters.

### `bootstrap-agentic-system` 1.3.1

- Clarified that Planner sessions are configured during bootstrap, isolated to the current session, and required for Planner-only ID-based planning skills.

### `bootstrap-agentic-system` 1.3.2

- Split session clarification into explicit questions about storage location, internal versus external placement, and current-session-only access.

### `create-work-item-from-description` 1.0.0

- Initial release for creating tracker-backed or local-Markdown bugs and user stories without creating planning sessions.

### `bootstrap-agentic-system` 1.2.1

- Required bootstrap proposals and file plans to explicitly offer `CONTEXT.md` creation or edits when stable terms or source-of-truth boundaries need a glossary.

### `bootstrap-agentic-system` 1.2.0

- Added context-glossary guidance so generated systems can use `CONTEXT.md` for stable vocabulary and source-of-truth boundaries without confusing it with knowledge-index loading.

### `bootstrap-agentic-system` 1.1.1

- Enforced implementation-plan schema adherence in generated Planner contracts, including linked filesystem-tree paths, File Details anchors, backlinks, and schema-over-lint validation behavior.

### `bootstrap-agentic-system` 1.1.0

- Added stricter generated-system requirements for knowledge-index, plan-schema, and question-schema template references.
- Added optional tracker-backed intake and ticket-creation guidance for repositories with issue-tracking workflows.

### `maintain-agentic-system` 1.0.0

- Initial public release for maintaining existing repo-local Agentic Systems.
