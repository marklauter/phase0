# WorkspaceProvisioned

## Context

- **Bounded context:** [Workspace Lifecycle](../contexts/05-workspace-lifecycle.md)
- **Producer:** [Provision Workspace](../use-cases/05-provision-workspace.md)
- **Consumers:** [Wiki Creation](../contexts/01-wiki-creation.md), [Editorial Review](../contexts/02-editorial-review.md), [Wiki Revision](../contexts/03-wiki-revision.md), [Drift Detection](../contexts/04-drift-detection.md) (all operational contexts discover workspace via config file)
- **Materialization:** `workspace/artifacts/{owner}/{repo}/workspace.config.md` on disk

## Description

A new workspace configuration file has been written to disk. This is the durable fact that all other bounded contexts discover at workspace selection time by scanning for config files matching `workspace/artifacts/*/*/workspace.config.md`.

## Payload

- Repo slug (owner/repo)
- Source directory path
- Wiki directory path
- Audience
- Tone
