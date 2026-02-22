# Drift Detection

## Purpose

Owns the ongoing verification of factual claims in the wiki against their sources of truth — source code, external references, linked specifications. Claims that have drifted are corrected. Claims that are accurate are left untouched. This context operates autonomously ([Git](../actors/17-git.md) is the approval gate) and does not interact with GitHub Issues.

## Ubiquitous language

- **Drift** — A factual claim in the wiki that no longer matches its source of truth.
- **Fact-checker assessment** — A structured report for one wiki page listing every factual claim checked, with verdict (verified, inaccurate, unverifiable), quoted text, correct fact, and source reference. Produced by a [Fact-Checker](../actors/11-fact-checkers.md).
- **Correction assignment** — The input to a [Corrector](../actors/15-correctors.md): page path, list of inaccurate claims with correct facts and source references, audience, tone, editorial guidance. Structurally compatible with [Wiki Revision](03-wiki-revision.md)'s correction assignments, enabling corrector reuse.
- **Sync report** — A durable, time-stamped report showing corrections applied, pages verified, and claims that could not be checked.
- **Source of truth** — The authoritative reference for a factual claim. May be source code, an external URL, a linked specification, or other referenced material.

## Use cases

- [Sync wiki with source changes](../use-cases/04-sync-wiki-with-source-changes.md) — Fact-check wiki claims against source code and external references, correct drift.

## Events produced

- [WikiSynced](../events/05-wiki-synced.md) — Raised when all wiki pages have been fact-checked and any detected drift has been corrected.

## Events consumed

This context consumes no events from other contexts. Drift detection is initiated directly by the [User](../actors/01-user.md) or on a scheduled basis.

## Integration points

- **Requires:** [Workspace Lifecycle](05-workspace-lifecycle.md) — workspace must be provisioned.
- **Shares with:** [Wiki Revision](03-wiki-revision.md) — corrector protocol is structurally compatible, enabling the same [Correctors](../actors/15-correctors.md) to serve both contexts.

## Notes

- Corrections applied by drift detection may render [Editorial Review](02-editorial-review.md) accuracy findings stale. This is an accepted trade-off in favor of keeping drift detection fast and independent.
- Drift detection does not file GitHub Issues. Its approval gate is [Git](../actors/17-git.md) — changes are committed directly and reviewed through the normal version control workflow.
