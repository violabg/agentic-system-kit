# Changelog

This package tracks public skill versions here instead of in `SKILL.md` frontmatter. VS Code skill metadata validation can warn on unsupported frontmatter fields, so `SKILL.md` stays focused on invocation and discovery metadata.

## Current Skill Versions

- `bootstrap-agentic-system`: `1.11.2`
- `maintain-agentic-system`: `1.4.0`
- `create-work-item-planning-skills`: `1.3.1`
- `create-work-item-from-description`: `1.0.0`

## 2026-07-27

### `bootstrap-agentic-system` 1.11.2

- Added blocking verification that every MCP or platform integration approved during Bootstrap clarification is carried into the named generated agent tool surface by exact tool name.

### `bootstrap-agentic-system` 1.11.1

- Required generated `plan-bug-from-id` and `plan-user-story-from-id` skills to omit skill-level `tools:` frontmatter and use inline `#tool:agent/runSubagent` gathering instructions instead.

### `create-work-item-planning-skills` 1.3.1

- Replaced generated skill `tools:` frontmatter requirements with body-level `#tool:agent/runSubagent` work-item retrieval handoffs for bug and user-story planning skills.

### `bootstrap-agentic-system` 1.11.0

- Kept Bootstrap as one public orchestrator while structuring repository discovery into bounded scout lanes and Gate 2 clarification into a decision register.
- Required non-trivial Bootstrap runs to audit preservation of the current contract before file-plan approval when subagents are available, with an inline equivalent when unavailable.
- Required context glossaries created or updated by Bootstrap to normalize synonymous or ambiguous repository wording with preferred terms, terms to avoid, accepted aliases, and distinctions.

### `maintain-agentic-system` 1.4.0

- Added maintenance checks for context-glossary terminology normalization introduced by Bootstrap 1.11.0.

### `bootstrap-agentic-system` 1.10.0

- Required generated Planner and Tester contracts to preserve baseline `agents:` frontmatter when delegated agents are supported.
- Required Bootstrap to resolve an issue tracker contract before planning ID-based bug or user-story skills, using either an external tracker adapter or a local Markdown issue tracker.

### `create-work-item-planning-skills` 1.3.0

- Required generated `plan-bug-from-id` and `plan-user-story-from-id` skills to share an issue ID retrieval contract.
- Added local Markdown adapter requirements for issue root, ID pattern, lookup or index path, required fields, missing-ID behavior, duplicate-ID behavior, and evidence copy rules.

### `bootstrap-agentic-system` 1.9.1

- Required Bootstrap to present discovered MCP and tool assignments for user confirmation before entering system proposal planning.
- Added bounded choices to add, omit, move, recommend only, or investigate more for each candidate MCP or integration.

### `bootstrap-agentic-system` 1.9.0

- Required generated agents to start from explicit baseline VS Code tool lists and record approved reductions.
- Added repository MCP discovery and role-based assignment rules for tracker, documentation, context, visual, cloud, runtime, and test integrations.

### `create-work-item-planning-skills` 1.2.0

- Required generated `plan-bug-from-id` and `plan-user-story-from-id` skills to declare the Planner tool surface and selected tracker or local Markdown adapter.
- Added guidance to use configured tracker MCPs when available and recommend missing useful MCPs without inventing tool names.

## 2026-07-25

### Initial Package Layout

- Grouped exported skills under `agentic-system` and `work-items` to keep the public package organized as a catalog-style skills repository.
- Added `skills.sh.json` to group the repository page on skills.sh while leaving CLI install behavior to the upstream `skills` tool.

## 2026-07-26

### `bootstrap-agentic-system` 1.8.0

- Added generated-system blueprint and role-contract templates so Bootstrap can install Planner, Implementor, Tester, Knowledge Builder, Vision, Ask, and hidden auditor contracts with stronger public-safe structure.
- Required Bootstrap proposals and generated files to use the blueprint and role-specific templates, including first-install batch decisions, role boundaries, numbered gates, artifacts, validation, and handoff obligations.

### `bootstrap-agentic-system` 1.7.0

- Added mandatory visual-artifact clarification during bootstrap discovery and proposal.
- Required a Vision agent or visual-intake skill when screenshots, mockups, diagrams, UI snapshots, image assets, or image-based QA evidence materially affect the workflow.

### `maintain-agentic-system` 1.3.0

- Added maintenance checks for missing visual-artifact decisions and Vision agent coverage in existing systems.

### `bootstrap-agentic-system` 1.6.0

- Clarified that generated `CONTEXT.md` files must be primarily about repository code/domain vocabulary, with agent-system terms only as a separated secondary section when needed.
- Required generated systems to include root `AGENTS.md` by default, or an approved platform-equivalent root instruction file.

### `maintain-agentic-system` 1.2.0

- Added maintenance checks for root instruction coverage and repo-code-focused context glossaries to keep existing systems aligned with Bootstrap 1.6.0.

### `maintain-agentic-system` 1.1.0

- Aligned maintenance audits with the current Bootstrap contract, including mandatory Knowledge Builder coverage, context-glossary discipline, Planner path references, and index-first knowledge loading.
- Added bounded maintenance scout and contract-auditor subagents when supported by the agent platform.
- Added final maintenance contract validation before handoff.

### `bootstrap-agentic-system` 1.5.0

- Added bounded bootstrap execution subagents for repository workflow discovery and contract auditing when supported by the agent platform.
- Added final bootstrap contract validation to compare generated files against the approved file plan, user requirements, and required skill outputs before final response.

### `bootstrap-agentic-system` 1.4.0

- Made the generated Knowledge Builder agent mandatory in the first bootstrap agent batch.
- Required stronger context-glossary intake from repository wording before file-plan approval.
- Added mandatory post-bootstrap recommendations to run Knowledge Builder and propose work-item planning and creation skills.

### Package Layout Export

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
