---
name: writing-todos
user-invokable: false
disable-model-invocation: false
description: Write todos — actionable work items, follow-up tasks, remediation from evaluation findings. Loads the todo form contract and creation script.
---

!`cat .claude/contracts/forms/todo.md`

## Creating todos

Use the `create-todo.sh` script to create todo files. The script handles file naming, directory creation, and section scaffolding.

```
bash .claude/scripts/create-todo.sh <model-dir> <slug> <title> <what> <why> <references>
```

- **model-dir** — path to the model directory (e.g., `models/marklauter/github-wiki-agent`)
- **slug** — action in kebab-case (e.g., `stub-historian-actor`, `revise-populate-scenario-3`). No numeric prefix, no datetime.
- **title** — the action title (e.g., `Stub historian actor`)
- **what** — what needs to happen, one to three sentences
- **why** — what discovery exposed this gap, one to two sentences
- **references** — artifacts this todo touches (e.g., `use-cases/01-populate-new-wiki (discovery source)`)

The script outputs the created file path. Todos are ephemeral — delete the file when the work is done.
