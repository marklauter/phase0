# Invariants

Cross-cutting rules that apply continuously — before, during, and after execution.

## Entries

- [Multi-repo workspace architecture](../invariants/01-multi-repo-workspace-architecture.md) — Each project gets its own isolated workspace; workspaces are independent.
  Governs: all use cases.
- [GitHub CLI is installed](../invariants/02-github-cli-installed.md) — The `gh` CLI is available on the system.
  Governs: [Populate new wiki](../use-cases/01-populate-new-wiki.md), [Review wiki quality](../use-cases/02-review-wiki-quality.md), [Revise wiki](../use-cases/03-revise-wiki.md), [Sync wiki with source changes](../use-cases/04-sync-wiki-with-source-changes.md), [Provision workspace](../use-cases/05-provision-workspace.md).
- [Source repo is readonly](../invariants/03-source-repo-readonly.md) — Source clones are reference material; no use case may modify them.
  Governs: [Populate new wiki](../use-cases/01-populate-new-wiki.md), [Review wiki quality](../use-cases/02-review-wiki-quality.md), [Revise wiki](../use-cases/03-revise-wiki.md), [Sync wiki with source changes](../use-cases/04-sync-wiki-with-source-changes.md).
- [Config is the source of truth](../invariants/04-config-source-of-truth.md) — Workspace identity is defined by the existence of workspace.config.md.
  Governs: all use cases.
- [One workspace per repository](../invariants/05-one-workspace-per-repo.md) — A workspace for a given owner/repo either exists or it does not.
  Governs: [Provision workspace](../use-cases/05-provision-workspace.md), [Decommission workspace](../use-cases/06-decommission-workspace.md).
- [Repo freshness is the user's responsibility](../invariants/06-repo-freshness-user-responsibility.md) — The system does not pull or verify that clones are up to date.
  Governs: [Populate new wiki](../use-cases/01-populate-new-wiki.md), [Review wiki quality](../use-cases/02-review-wiki-quality.md), [Revise wiki](../use-cases/03-revise-wiki.md), [Sync wiki with source changes](../use-cases/04-sync-wiki-with-source-changes.md).
- [Scripts own deterministic behavior](../invariants/07-scripts-own-deterministic-behavior.md) — All deterministic operations belong in scripts; the LLM handles judgment only.
  Governs: [Review wiki quality](../use-cases/02-review-wiki-quality.md), [Revise wiki](../use-cases/03-revise-wiki.md), [Provision workspace](../use-cases/05-provision-workspace.md), [Decommission workspace](../use-cases/06-decommission-workspace.md).
- [Commands do not chain](../invariants/08-commands-do-not-chain.md) — Each command is self-contained and never invokes another.
  Governs: all use cases.
- [No CLI-style flags](../invariants/09-no-cli-style-flags.md) — Commands are agent interactions; confirmation happens through conversation.
  Governs: [Revise wiki](../use-cases/03-revise-wiki.md), [Decommission workspace](../use-cases/06-decommission-workspace.md).
