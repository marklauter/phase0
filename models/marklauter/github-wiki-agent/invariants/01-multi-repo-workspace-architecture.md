# Multi-repo workspace architecture

## Statement

This system manages wiki documentation for multiple GitHub projects simultaneously. Each project gets its own isolated workspace. Workspaces are independent — operations on one workspace never affect another.

- Each workspace contains a source clone, a wiki clone, and a config file.
- Config is the source of truth for workspace identity — the existence of `workspace/artifacts/{owner}/{repo}/workspace.config.md` defines whether a workspace exists. See [Config source of truth](04-config-source-of-truth.md).
- One workspace per repository — a given `owner/repo` maps to exactly one workspace, with no partial state or overlap. See [One workspace per repo](05-one-workspace-per-repo.md).

The workspace directory structure enforces isolation:

```
workspace/
  artifacts/{owner}/{repo}/
    workspace.config.md
    reports/
  {owner}/{repo}/           # source clone (readonly)
  {owner}/{repo}.wiki/      # wiki clone (mutable)
```

## Rationale

Isolation protects each project from cross-contamination. Each workspace maintains its own clones, config, and artifacts independently, so failures or changes in one project never ripple into another.

## Scope

- [Populate new wiki](../use-cases/01-populate-new-wiki.md)
- [Review wiki quality](../use-cases/02-review-wiki-quality.md)
- [Revise wiki](../use-cases/03-revise-wiki.md)
- [Sync wiki with source changes](../use-cases/04-sync-wiki-with-source-changes.md)
- [Provision workspace](../use-cases/05-provision-workspace.md)
- [Decommission workspace](../use-cases/06-decommission-workspace.md)

## Origin

Established by [Provision workspace](../use-cases/05-provision-workspace.md).

## Notes

- Sub-rules [Config source of truth](04-config-source-of-truth.md) and [One workspace per repo](05-one-workspace-per-repo.md) also stand as independent invariants because they govern use cases beyond workspace architecture.
