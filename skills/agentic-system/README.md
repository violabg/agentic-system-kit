# Agentic System

Skills for bootstrapping and maintaining repository-local agent workflows.

## Included skills

- `bootstrap-agentic-system` for designing and generating a new repository-local Agentic System.
- `maintain-agentic-system` for upgrading, evolving, or auditing an existing Agentic System.

Bootstrap can configure multiple environments together, including GitHub Copilot in VS Code, Claude Code, Codex, OpenCode, Cursor, and user-named alternatives. It researches only selected platforms at installation time and preserves canonical content outside approved placeholders and tool bindings. Maintainer uses the same compatibility contract and saved target evidence; neither skill treats generated files alone as verified runtime compatibility.

Every user-facing role, such as Planner or Implementor, runs as the main conversation, and each client gets exactly one way to start it. Clients with a native agent picker that works on every surface the team uses, such as GitHub Copilot in VS Code or OpenCode, register the roles as native agents. Other clients, such as Claude Code or Codex, get no custom agents: their sessions receive every tool and integration the roles need, and users start roles through prefixed skills they invoke by hand. Planner starts only through `plan-bug-from-id` and `plan-user-story-from-id`. On that route, role tool limits are instructions, not enforcement, and the guide says so. Bootstrap and Maintainer always run outside the roles, in a default session. After an approved plan, the Planner ends with the exact step to start Implementor in a new conversation with the Planning Session ID. Bootstrap also writes a user guide for each selected client (default `docs/agentic-system/`) and links them when it finishes.

Project-root `knowledge/` holds project knowledge. The dedicated maintenance area holds installation/maintenance resources and evidence, excluded from ordinary requests. Bootstrap and Maintainer share the layout/migration and platform/authentication contracts; native entrypoints and per-role integration access require separate verification.
