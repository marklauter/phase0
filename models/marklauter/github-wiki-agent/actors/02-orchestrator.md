# Orchestrator

## Category

Supporting actor.

## Role

Resolves the workspace, absorbs editorial context, dispatches other agents, collects results, and presents summaries.

## Description

The Orchestrator is an abstract type whose children coordinate the editorial use cases (use-cases/01-populate-new-wiki through use-cases/04-sync-wiki-with-source-changes). The orchestrator makes no editorial judgments — it delegates judgment to specialized agents. The shared behavioral trait that children inherit is: workspace resolution, editorial context absorption, agent dispatch, result collection, and summary presentation. Each editorial use case instantiates an orchestrator whose drive determines what it coordinates and how it decides when to advance between phases.

## Drive

Coordination.

## Children

- [Commissioning orchestrator](03-commissioning-orchestrator.md) — commissioning
- [Oversight orchestrator](04-oversight-orchestrator.md) — oversight
- [Fulfillment orchestrator](05-fulfillment-orchestrator.md) — fulfillment
- [Alignment orchestrator](06-alignment-orchestrator.md) — alignment

## Appears in

- [Populate new wiki](../use-cases/01-populate-new-wiki.md)
- [Review wiki quality](../use-cases/02-review-wiki-quality.md)
- [Revise wiki](../use-cases/03-revise-wiki.md)
- [Sync wiki with source changes](../use-cases/04-sync-wiki-with-source-changes.md)

## Notes

- Orchestrators appear only in the editorial use cases (use-cases/01-populate-new-wiki through use-cases/04-sync-wiki-with-source-changes). Workspace lifecycle use cases (use-cases/05-provision-workspace, use-cases/06-decommission-workspace) are handled directly by the command without orchestration.
- Each concrete orchestrator is named after its publishing-world counterpart — commissioning editor, managing editor, production editor, revisions editor — reflecting the nature of the coordination it performs.
