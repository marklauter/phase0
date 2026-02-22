# User

## Category

Primary actor.

## Role

The human who owns the repository and authorizes all wiki operations.

## Description

The User is the primary actor in every use case. Every wiki operation begins with the User's intent and ends with the User's approval. The system exists to serve the User's goal of maintaining well-documented, trustworthy software projects. The User retains authority over what gets written and what gets published — plan approval before content is written, post-hoc review via git, and type-to-confirm before destructive actions.

## Goals

- Provide software projects that are well-documented and trustworthy.
- Be a responsible steward of project documentation.

## Experience goals

- Feel confident that the wiki accurately represents the source code.
- Feel in control of what gets written and what gets published — no surprises from autonomous agents.
- Feel that the system respects their judgment — plan approval before content is written (use-cases/01-populate-new-wiki), post-hoc review via git (use-cases/04-sync-wiki-with-source-changes), type-to-confirm before destructive actions (use-cases/06-decommission-workspace).
- Feel that their time is not wasted — summaries are actionable, failures are explained, next steps are clear.

## End goals

- [Populate new wiki](../use-cases/01-populate-new-wiki.md) — a new wiki is populated with complete documentation grounded in source code.
- [Review wiki quality](../use-cases/02-review-wiki-quality.md) — every real documentation problem is exposed as an actionable GitHub issue.
- [Revise wiki](../use-cases/03-revise-wiki.md) — recommended corrections are applied so the wiki content is fixed.
- [Sync wiki with source changes](../use-cases/04-sync-wiki-with-source-changes.md) — every factual claim is brought in line with current sources of truth.
- [Provision workspace](../use-cases/05-provision-workspace.md) — a workspace is set up so wiki operations can begin.
- [Decommission workspace](../use-cases/06-decommission-workspace.md) — the workspace is removed cleanly, with no silent loss of unpublished work.

## Appears in

- [Populate new wiki](../use-cases/01-populate-new-wiki.md)
- [Review wiki quality](../use-cases/02-review-wiki-quality.md)
- [Revise wiki](../use-cases/03-revise-wiki.md)
- [Sync wiki with source changes](../use-cases/04-sync-wiki-with-source-changes.md)
- [Provision workspace](../use-cases/05-provision-workspace.md)
- [Decommission workspace](../use-cases/06-decommission-workspace.md)

## Notes

- The User is the only actor that spans all six use cases.
- use-cases/07-publish-wiki-changes is out of scope and excluded.
