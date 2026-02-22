# Wiki Revision

## Purpose

Owns the revision of wiki content based on documented problems tracked in GitHub Issues. [Correctors](../actors/15-correctors.md) apply recommended corrections to wiki pages. Issue closure is a consequence of successful remediation, not the goal. This context consumes the published protocol from [Editorial Review](02-editorial-review.md).

## Ubiquitous language

- **Corrector** — An actor with a remediation drive that applies recommended corrections to a wiki page.
- **Targeted edit** — A surgical change to a specific section of a wiki page, preserving surrounding content.
- **Skip reason** — Why a corrector could not apply a recommendation: quoted text no longer exists, recommendation is ambiguous, recommendation contradicts source code.
- **Correction assignment** — The input to a [Corrector](../actors/15-correctors.md): page path, finding (what is wrong), recommendation (what it should say), source reference (the authority). Structurally compatible with [Drift Detection](04-drift-detection.md)'s correction assignments, enabling corrector reuse.

## Use cases

- [Revise wiki](../use-cases/03-revise-wiki.md) — Apply recommended corrections from GitHub issues to wiki pages.

## Events produced

- [WikiRemediated](../events/04-wiki-remediated.md) — Raised when all actionable findings from the current batch of GitHub issues have been applied or skipped with documented reasons.

## Events consumed

- [FindingFiled](../events/02-finding-filed.md) — From [Editorial Review](02-editorial-review.md), via GitHub Issues. Each filed finding becomes a correction assignment for a [Corrector](../actors/15-correctors.md).

## Integration points

- **Requires:** [Workspace Lifecycle](05-workspace-lifecycle.md) — workspace must be provisioned.
- **Requires:** [Editorial Review](02-editorial-review.md) — GitHub issues conforming to the finding schema provide the correction assignments.
- **Shares with:** [Drift Detection](04-drift-detection.md) — corrector protocol is structurally compatible, enabling the same [Correctors](../actors/15-correctors.md) to serve both contexts.

## Notes

- Correction assignments from this context and from [Drift Detection](04-drift-detection.md) share the same structure. This is a deliberate design decision that allows [Correctors](../actors/15-correctors.md) to operate without knowing which context originated the work.
