---
name: writing-actors
description: Create and structure actor files. Write new actors, scaffold primary/supporting/sub-system categories during design work. Structural contract and creation script.
---

!`cat .claude/contracts/forms/actor.md`

## Creating actors

Use the `create-actor.sh` script to create actor files. The script handles file naming, directory creation, and category-specific section scaffolding.

```
bash .claude/scripts/create-actor.sh <model-dir> <nn> <slug> <name> <category> <role> <description>
```

- **model-dir** — path to the model directory (e.g., `models/marklauter/github-wiki-agent`)
- **nn** — zero-padded number (e.g., `01`). Check `actors/index.md` or list the directory for the next available.
- **slug** — actor name in lowercase (e.g., `user`, `orchestrator`, `proofreaders`)
- **name** — display name, capitalized (e.g., `User`, `Orchestrator`, `Proofreaders`)
- **category** — one of: `primary`, `supporting`, `sub-system`. Determines which sections are scaffolded.
- **role** — one sentence: what this actor does in the system
- **description** — one paragraph: what this actor is and why it exists

The script outputs the created file path. Add an entry to `actors/index.md` after creating.
