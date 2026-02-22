# No CLI-style flags

## Statement

Commands are agent interactions, not CLI programs. Confirmation and disambiguation happen through conversation, not `--force` or `--all` flags.

## Rationale

This system is conversational. Flags bypass the judgment and confirmation that make agent interactions safe. Conversation gives the user a chance to understand what will happen before it happens.

## Scope

- [Revise wiki](../use-cases/03-revise-wiki.md)
- [Decommission workspace](../use-cases/06-decommission-workspace.md)

## Origin

Established by [Provision workspace](../use-cases/05-provision-workspace.md).

## Notes

- This invariant reinforces the conversational nature of the agent. Where a CLI would use flags for mode selection, this system uses dialogue.
