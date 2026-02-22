# FindingFiled

## Context

- **Bounded context:** [Editorial Review](../contexts/02-editorial-review.md)
- **Producer:** [Review Wiki Quality](../use-cases/02-review-wiki-quality.md)
- **Consumers:** [Wiki Revision](../contexts/03-wiki-revision.md) via [Revise Wiki](../use-cases/03-revise-wiki.md) (issue drives remediation)
- **Materialization:** GitHub issue with `documentation` label, conforming to `documentation-issue.md` schema

## Description

A GitHub issue has been created for a documentation problem. This is the only published event that crosses a bounded context boundary as a formal contract. The issue body schema (`documentation-issue.md`) is the integration protocol between Editorial Review and Wiki Revision. [GitHub](../actors/16-github.md) is a sub-system — the issue is the durable fact.

## Payload

- Issue number
- Page
- Editorial lens
- Severity
- Finding text (with quoted problematic text)
- Recommendation (with corrected text where applicable)
- Source file citation (accuracy lens only)
