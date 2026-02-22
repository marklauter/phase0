# WikiRemediated

## Context

- **Bounded context:** [Wiki Revision](../contexts/03-wiki-revision.md)
- **Producer:** [Revise Wiki](../use-cases/03-revise-wiki.md)
- **Consumers:** [User](../actors/01-user.md) (remediation results are ready for review)
- **Materialization:** Summary presented to user; wiki files corrected on disk; GitHub issues closed

## Description

The remediation run has completed. Every actionable issue has been processed — either corrected and closed, or skipped with a reason.

## Payload

- Issues corrected count
- Issues skipped count
- Issues close-deferred count
- Remaining open count
