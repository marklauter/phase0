# Actors

Every actor that interacts with or operates within the system — who they are, what drives them, and where they appear.

## Entries

### Human actors

- [User](../actors/01-user.md) — Primary actor in every use case; responsible for a GitHub project's wiki documentation.
  Appears in: all use cases.

### Supporting actors

- [Orchestrator](../actors/02-orchestrator.md) — Abstract parent for the four coordinating actors in editorial use cases.
  Drive: coordination.
- [Commissioning orchestrator](../actors/03-commissioning-orchestrator.md) — Coordinates wiki population.
  Drive: commissioning. Appears in: [Populate new wiki](../use-cases/01-populate-new-wiki.md).
- [Oversight orchestrator](../actors/04-oversight-orchestrator.md) — Coordinates editorial review.
  Drive: oversight. Appears in: [Review wiki quality](../use-cases/02-review-wiki-quality.md).
- [Fulfillment orchestrator](../actors/05-fulfillment-orchestrator.md) — Coordinates wiki revision.
  Drive: fulfillment. Appears in: [Revise wiki](../use-cases/03-revise-wiki.md).
- [Alignment orchestrator](../actors/06-alignment-orchestrator.md) — Coordinates drift detection.
  Drive: alignment. Appears in: [Sync wiki with source changes](../use-cases/04-sync-wiki-with-source-changes.md).
- [Developmental editor](../actors/07-developmental-editor.md) — Synthesizes research into wiki structure.
  Drive: synthesis. Appears in: [Populate new wiki](../use-cases/01-populate-new-wiki.md).
- [Assessor](../actors/08-assessor.md) — Abstract parent for read-only judgment actors.
  Drive: read-only judgment.
- [Researchers](../actors/09-researchers.md) — Examine source code from distinct angles.
  Drive: comprehension. Appears in: [Populate new wiki](../use-cases/01-populate-new-wiki.md), [Review wiki quality](../use-cases/02-review-wiki-quality.md).
- [Proofreaders](../actors/10-proofreaders.md) — Examine wiki content through editorial lenses.
  Drive: critique. Appears in: [Review wiki quality](../use-cases/02-review-wiki-quality.md).
- [Fact-checkers](../actors/11-fact-checkers.md) — Verify factual claims against sources of truth.
  Drive: verification. Appears in: [Sync wiki with source changes](../use-cases/04-sync-wiki-with-source-changes.md).
- [Deduplicator](../actors/12-deduplicator.md) — Prevents duplicate GitHub issues.
  Drive: filtering. Appears in: [Review wiki quality](../use-cases/02-review-wiki-quality.md).
- [Content Mutator](../actors/13-content-mutator.md) — Abstract parent for wiki-writing actors.
  Drive: wiki modification.
- [Creators](../actors/14-creators.md) — Write original wiki pages from source code.
  Drive: production. Appears in: [Populate new wiki](../use-cases/01-populate-new-wiki.md).
- [Correctors](../actors/15-correctors.md) — Apply known corrections to wiki pages.
  Drive: remediation. Appears in: [Revise wiki](../use-cases/03-revise-wiki.md), [Sync wiki with source changes](../use-cases/04-sync-wiki-with-source-changes.md).

### Sub-systems

- [GitHub](../actors/16-github.md) — Remote repository host and durable event store.
  Used by: [Review wiki quality](../use-cases/02-review-wiki-quality.md), [Revise wiki](../use-cases/03-revise-wiki.md), [Provision workspace](../use-cases/05-provision-workspace.md).
- [Git](../actors/17-git.md) — Cloning, working tree inspection, post-hoc approval.
  Used by: [Sync wiki with source changes](../use-cases/04-sync-wiki-with-source-changes.md), [Provision workspace](../use-cases/05-provision-workspace.md), [Decommission workspace](../use-cases/06-decommission-workspace.md).
