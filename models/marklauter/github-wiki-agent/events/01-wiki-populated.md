# WikiPopulated

## Context

- **Bounded context:** [Wiki Creation](../contexts/01-wiki-creation.md)
- **Producer:** [Populate New Wiki](../use-cases/01-populate-new-wiki.md)
- **Consumers:** [User](../actors/01-user.md) (wiki is ready for review), [Editorial Review](../contexts/02-editorial-review.md) (wiki is ready for review), [Drift Detection](../contexts/04-drift-detection.md) (wiki has content to sync)
- **Materialization:** Wiki pages on disk and summary presented to user

## Description

The wiki directory has been populated with a complete set of documentation pages from an approved plan. This is the foundational event in Wiki Creation — after this event, the wiki is ready for review via [Review Wiki Quality](../use-cases/02-review-wiki-quality.md) and publishing.

## Payload

- Repo identity (owner/repo)
- Sections with their pages (hierarchical structure matching navigation)
- Audience and tone
- Wiki directory path
