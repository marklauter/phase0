# Wiki Creation

## Purpose

Owns the transition from an empty wiki to a populated wiki. The source code is explored, a wiki structure is proposed and approved by the user, and creators produce pages. This context assumes the wiki has no existing content pages — restructuring an existing wiki belongs to [Wiki Restructuring](06-wiki-restructuring.md).

## Ubiquitous language

- **Exploration report** — A structured summary of one facet of the source code (API surface, architecture, configuration), produced by a [Researcher](../actors/09-researchers.md).
- **Wiki plan** — A hierarchical structure of sections containing pages, each with filename, title, description, and key source files. Proposed by the [Developmental Editor](../actors/07-developmental-editor.md), refined and approved by the [User](../actors/01-user.md).
- **Writing assignment** — The input to a [Creator](../actors/14-creators.md): page file path, title, description, key source files, audience, tone, and editorial guidance.

## Use cases

- [Populate new wiki](../use-cases/01-populate-new-wiki.md) — Populate a new wiki from source code with a user-approved structure.

## Events produced

- [WikiPopulated](../events/01-wiki-populated.md) — Raised when all writing assignments have been fulfilled and the wiki contains its initial set of content pages.

## Events consumed

This context consumes no events from other contexts. Wiki creation is initiated directly by the [User](../actors/01-user.md).

## Integration points

- **Requires:** [Workspace Lifecycle](05-workspace-lifecycle.md) — workspace must be provisioned before wiki creation.
- **Feeds:** [Editorial Review](02-editorial-review.md) — populated wiki is ready for quality review.
- **Feeds:** [Drift Detection](04-drift-detection.md) — populated wiki has content pages to sync.

## Notes

- Wiki creation is a one-time operation per workspace. If the wiki already has content, the [User](../actors/01-user.md) is directed to [Wiki Restructuring](06-wiki-restructuring.md) instead.
- The [Orchestrator](../actors/02-orchestrator.md) coordinates exploration, planning, and writing phases sequentially — each phase completes before the next begins.
