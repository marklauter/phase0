# One workspace per repository

## Statement

A workspace for a given `owner/repo` either exists or it does not. There is no partial state, no dual config, no overlapping workspaces for the same repository.

## Rationale

A one-to-one mapping between repository and workspace eliminates conflict. Provisioning and decommissioning are clean transitions — the workspace is either fully present or fully absent.

## Scope

- [Provision workspace](../use-cases/05-provision-workspace.md)
- [Decommission workspace](../use-cases/06-decommission-workspace.md)

## Origin

Established by [Provision workspace](../use-cases/05-provision-workspace.md).

## Notes

- Also a sub-rule of [Multi-repo workspace architecture](01-multi-repo-workspace-architecture.md).
