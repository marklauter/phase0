# WikiReviewed

## Context

- **Bounded context:** [Editorial Review](../contexts/02-editorial-review.md)
- **Producer:** [Review Wiki Quality](../use-cases/02-review-wiki-quality.md)
- **Consumers:** [User](../actors/01-user.md) (knows what is strong, what needs fixing, and where to start)
- **Materialization:** Summary presented to user; GitHub issues as durable record

## Description

The review process has completed. The user knows what is strong, what needs fixing, and where to start.

## Payload

- Pages reviewed count
- Issues identified count
- Issues filed count
- Clean pages
- Failed reviews
- Failed filings
