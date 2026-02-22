# Editorial Review

## Purpose

Owns the critique of existing wiki content across four editorial lenses: structure, line, copy, and accuracy. The review process exposes problems as GitHub Issues — it never modifies wiki content. This context produces the published protocol consumed by [Wiki Revision](03-wiki-revision.md).

## Ubiquitous language

- **Editorial lens** — A distinct editorial discipline applied to wiki content. Four lenses: structure (organization, flow, gaps), line (sentence-level clarity), copy (grammar, formatting, terminology consistency), accuracy (claims verified against source code).
- **Finding** — A specific documentation problem identified by a [Proofreader](../actors/10-proofreaders.md), with quoted problematic text, a recommendation, and (for accuracy) a source file citation.
- **Severity** — Classification of a finding: must-fix or suggestion.
- **Deduplication** — Comparing new findings against existing open GitHub issues to prevent duplicates. The [Deduplicator](../actors/12-deduplicator.md) only drops a finding when it clearly matches an existing open issue about the same problem.
- **Proofread cache** — Ephemeral storage for coordinating actors during a single review run. Created at start, cleaned up at end.

## Use cases

- [Review wiki quality](../use-cases/02-review-wiki-quality.md) — Review wiki quality across four editorial lenses and file GitHub issues for each finding.

## Events produced

- [FindingFiled](../events/02-finding-filed.md) — Raised each time a deduplicated finding is filed as a GitHub issue. Published to [Wiki Revision](03-wiki-revision.md).
- [WikiReviewed](../events/03-wiki-reviewed.md) — Raised when all editorial lenses have completed their review pass and all findings have been filed or deduplicated.

## Events consumed

This context consumes no events from other contexts. Editorial review is initiated directly by the [User](../actors/01-user.md).

## Integration points

- **Requires:** [Workspace Lifecycle](05-workspace-lifecycle.md) — workspace must be provisioned.
- **Feeds:** [Wiki Revision](03-wiki-revision.md) — findings filed as GitHub issues are consumed by [Correctors](../actors/15-correctors.md).

## Notes

- Accuracy findings may become stale if [Drift Detection](04-drift-detection.md) independently corrects the same inaccuracy. This is an accepted trade-off — editorial review and drift detection operate independently.
