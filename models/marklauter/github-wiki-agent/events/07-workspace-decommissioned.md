# WorkspaceDecommissioned

## Context

- **Bounded context:** [Workspace Lifecycle](../contexts/05-workspace-lifecycle.md)
- **Producer:** [Decommission Workspace](../use-cases/06-decommission-workspace.md)
- **Consumers:** None (workspace simply ceases to exist)
- **Materialization:** Config file, source clone, and wiki clone removed from disk

## Description

The workspace config file, source clone, and wiki clone have been removed. This is the inverse of [WorkspaceProvisioned](06-workspace-provisioned.md). After this event, the workspace selection procedure will no longer discover this workspace.

## Payload

- Repo slug (owner/repo)
