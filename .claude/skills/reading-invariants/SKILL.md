---
name: reading-invariants
user-invokable: false
disable-model-invocation: false
description: Read and review invariant files. Check what rules apply, understand constraints, inspect scope and origin. Structural contract for invariant documents.
---

Read the form at `.claude/contracts/forms/invariant.md` when you need to verify structure.

## Reading invariants

Shared invariants live at `invariants/` within the model directory, with an `index.md` catalog. Single-use invariants stay local to their use case's Invariants section.

- **Start with the index** — `invariants/index.md` lists shared invariants with their scope. Read the index to understand which rules span multiple use cases.
- **Check use cases too** — local invariants only appear in individual use case files. To find all invariants governing an interaction, read both the shared invariants index and the specific use case's Invariants section.
- **Scope** — lists every use case the invariant governs. Use this to understand the invariant's reach.
- **Origin** — names the use case or design decision that established the invariant. Use this to trace why the rule exists.
