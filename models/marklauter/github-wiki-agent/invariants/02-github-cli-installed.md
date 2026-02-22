# GitHub CLI is installed

## Statement

The `gh` CLI is available on the system and verified before proceeding. Authentication is the concern of `gh` itself, not this system.

## Rationale

Every workspace operation depends on GitHub API access through `gh`. Without it, cloning, publishing, and API queries all fail. Verifying its presence early prevents cryptic downstream errors.

## Scope

- [Populate new wiki](../use-cases/01-populate-new-wiki.md)
- [Review wiki quality](../use-cases/02-review-wiki-quality.md)
- [Revise wiki](../use-cases/03-revise-wiki.md)
- [Sync wiki with source changes](../use-cases/04-sync-wiki-with-source-changes.md)
- [Provision workspace](../use-cases/05-provision-workspace.md)

## Origin

Established by [Provision workspace](../use-cases/05-provision-workspace.md).

## Notes

- If `gh` is not installed, the user is notified. The system does not attempt to install it.
