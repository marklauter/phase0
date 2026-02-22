# Use cases

Each use case describes one goal pursued by one primary actor.

## Entries

- [Populate new wiki](../use-cases/01-populate-new-wiki.md) — Populate new wiki from source code with user-approved structure.
  Context: [Wiki Creation](../contexts/01-wiki-creation.md). Actor: [User](../actors/01-user.md).
- [Review wiki quality](../use-cases/02-review-wiki-quality.md) — Review wiki quality across four editorial lenses, file GitHub issues.
  Context: [Editorial Review](../contexts/02-editorial-review.md). Actor: [User](../actors/01-user.md).
- [Revise wiki](../use-cases/03-revise-wiki.md) — Apply recommended corrections from GitHub issues to wiki pages.
  Context: [Wiki Revision](../contexts/03-wiki-revision.md). Actor: [User](../actors/01-user.md).
- [Sync wiki with source changes](../use-cases/04-sync-wiki-with-source-changes.md) — Fact-check wiki claims against source code and external references, correct drift.
  Context: [Drift Detection](../contexts/04-drift-detection.md). Actor: [User](../actors/01-user.md).
- [Provision workspace](../use-cases/05-provision-workspace.md) — Clone repos and write config for a new project workspace.
  Context: [Workspace Lifecycle](../contexts/05-workspace-lifecycle.md). Actor: [User](../actors/01-user.md).
- [Decommission workspace](../use-cases/06-decommission-workspace.md) — Remove a project workspace with safety checks for unpublished work.
  Context: [Workspace Lifecycle](../contexts/05-workspace-lifecycle.md). Actor: [User](../actors/01-user.md).
- [Publish wiki changes](../use-cases/07-publish-wiki-changes.md) — Commit and push wiki changes *(out of scope)*.
  Context: [Workspace Lifecycle](../contexts/05-workspace-lifecycle.md). Actor: [User](../actors/01-user.md).
- [Refactor existing wiki](../use-cases/08-refactor-existing-wiki.md) — Interactively restructure an existing wiki *(not yet designed)*.
  Context: [Wiki Restructuring](../contexts/06-wiki-restructuring.md). Actor: [User](../actors/01-user.md).
