---
name: reading-contexts
description: Read, review, show, or examine bounded context files — boundaries, ubiquitous language, integration points, events produced and consumed. Loads the context form contract.
---

Read the form at `.claude/contracts/forms/context.md` when you need to verify structure.

## Reading contexts

Contexts live at `contexts/` within the model directory, with an `index.md` catalog.

- **Start with the index** — `contexts/index.md` maps each context to its use cases. Read the index for the full context map before drilling into individuals.
- **Ubiquitous language** — terms defined here have precise meaning within this context. The same term may mean something different in another context — that divergence is the boundary.
- **Events produced and consumed** — these are the integration contracts. Produced events flow outward; consumed events flow inward. Together they define how this context communicates.
- **Integration points** — three relationship types: requires (depends on), feeds (provides to), shares with (bilateral). These map the dependency graph between contexts.
