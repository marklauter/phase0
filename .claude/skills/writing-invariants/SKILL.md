---
name: writing-invariants
user-invokable: false
disable-model-invocation: false
description: Create, write, or scaffold shared invariant files — rules, constraints, scope, rationale, origin. Loads the invariant form contract and creation script.
---

!`cat .claude/contracts/forms/invariant.md`

## Creating invariants

Use the `create-invariant.sh` script to create shared invariant files. The script handles file naming, directory creation, and section scaffolding.

```
bash .claude/scripts/create-invariant.sh <model-dir> <nn> <slug> <name> <statement> <rationale> <origin>
```

- **model-dir** — path to the model directory (e.g., `models/marklauter/github-wiki-agent`)
- **nn** — zero-padded number (e.g., `01`). Check `invariants/index.md` or list the directory for the next available.
- **slug** — rule name in kebab-case (e.g., `source-repo-readonly`, `gh-cli-installed`)
- **name** — the invariant's display name (e.g., `Source repository is read-only`)
- **statement** — the rule itself, declarative, present tense
- **rationale** — why this rule exists, what it protects
- **origin** — which use case established this invariant (e.g., `Established by use-cases/01-populate-new-wiki.`)

The script outputs the created file path. Only create files for invariants that span multiple use cases. Single-use invariants stay in the use case's Invariants section. Add an entry to `invariants/index.md` after creating.
