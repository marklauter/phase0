# Events

Domain events are meaningful state transitions that cross bounded context boundaries or are exposed to the user as observable outcomes.

## Entries

- [WikiPopulated](../events/01-wiki-populated.md) — The wiki directory has been populated with documentation pages from an approved plan.
  Producer: [Populate new wiki](../use-cases/01-populate-new-wiki.md). Consumers: [User](../actors/01-user.md), [Editorial Review](../contexts/02-editorial-review.md), [Drift Detection](../contexts/04-drift-detection.md).
- [FindingFiled](../events/02-finding-filed.md) — A GitHub issue has been created for a documentation problem.
  Producer: [Review wiki quality](../use-cases/02-review-wiki-quality.md). Consumers: [Wiki Revision](../contexts/03-wiki-revision.md).
- [WikiReviewed](../events/03-wiki-reviewed.md) — The review process has completed.
  Producer: [Review wiki quality](../use-cases/02-review-wiki-quality.md). Consumers: [User](../actors/01-user.md).
- [WikiRemediated](../events/04-wiki-remediated.md) — The remediation run has completed.
  Producer: [Revise wiki](../use-cases/03-revise-wiki.md). Consumers: [User](../actors/01-user.md).
- [WikiSynced](../events/05-wiki-synced.md) — The sync operation has completed.
  Producer: [Sync wiki with source changes](../use-cases/04-sync-wiki-with-source-changes.md). Consumers: [User](../actors/01-user.md).
- [WorkspaceProvisioned](../events/06-workspace-provisioned.md) — A new workspace configuration has been written to disk.
  Producer: [Provision workspace](../use-cases/05-provision-workspace.md). Consumers: All operational contexts.
- [WorkspaceDecommissioned](../events/07-workspace-decommissioned.md) — The workspace has been removed from disk.
  Producer: [Decommission workspace](../use-cases/06-decommission-workspace.md). Consumers: None.
