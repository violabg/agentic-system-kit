# Work Items

Skills for creating tracker-backed work items.

## Included skills

- `create-work-item-from-description` for explicitly invoked, approval-gated creation of a bug or user story through an authorized issue-creation tool in the active client, then returning its ID.

ID-based planning skills are not created from here. Bootstrap installs `plan-bug-from-id` and `plan-user-story-from-id` into the target repository directly, and the installed `author-repo-skill` covers reworking them afterwards.
