---
name: reading-todos
user-invokable: false
disable-model-invocation: false
description: Read and review todo files. Check pending work, see open work items, understand what needs doing. Structural contract for todo documents.
---

Read the form at `.claude/contracts/forms/todo.md` when you need to verify structure.

## Reading todos

Todos live at `todos/` within the model directory. No index, no ordering. They are ephemeral — they exist only while the work is pending.

- **List** — `ls todos/` within the model directory. The slug names the action (e.g., `stub-historian-actor.md`, `revise-populate-scenario-3.md`).
- **What and Why** — the What section describes the work. The Why section explains what surfaced the gap. Together they provide enough context to pick up the work without re-reading the source conversation.
- **References** — cross-links to the artifacts this todo touches. Use these to understand what will change when the work is done.
- **Absence is completion** — when a todo is done, it gets deleted. An empty `todos/` directory means all captured work has been addressed.
