# Agentic System

Skills for bootstrapping and maintaining repository-local agent workflows.

## Included skills

- `bootstrap-agentic-system` for designing and generating a new repository-local Agentic System.
- `maintain-agentic-system` for upgrading, evolving, or auditing an existing Agentic System.

Bootstrap can configure multiple environments together, including GitHub Copilot in VS Code, Claude Code, Codex, OpenCode, Cursor, and user-named alternatives. It researches only selected platforms at installation time and preserves canonical content outside approved placeholders and tool bindings. Maintainer uses the same compatibility contract and saved target evidence; neither skill treats generated files alone as verified runtime compatibility.

Every user-facing role, such as Planner or Implementor, runs as the main conversation. On clients without an agent picker, Bootstrap gives each role a verified start method. For Claude Code, Bootstrap asks whether the team uses the VS Code extension. Only on a yes does it offer an explicitly invoked fallback beside native role selection, with its instruction-only limits stated in the guide. Each route's own tool list is verified against the role's operations, and a missing tool gets an approved route-specific alternative or blocks the role on that route. Other clients get the same offer only when evidence shows native selection does not cover every surface the team uses. After an approved plan, the Planner ends with the exact step to start Implementor in a new conversation with the Planning Session ID. Bootstrap also writes a user guide for each selected client (default `docs/agentic-system/`) and links them when it finishes.

Project-root `knowledge/` holds project knowledge. The dedicated maintenance area holds installation/maintenance resources and evidence, excluded from ordinary requests. Bootstrap and Maintainer share the layout/migration and platform/authentication contracts; native entrypoints and per-role integration access require separate verification.
