---
name: reading-catalogs
user-invokable: false
disable-model-invocation: false
description: Read, browse, or review index catalogs — artifact listings, cross-references, what exists in the model. Loads the catalog form contract and reading guidance.
---

Read the form at `.claude/contracts/forms/catalog.md` when you need to verify structure.

## Reading catalogs

Each topic folder (`actors/`, `contexts/`, `events/`, `invariants/`, `use-cases/`) contains an `index.md`.

- **Catalogs are entry points** — read the index before drilling into individual artifacts. The one-sentence description per entry gives enough context to decide which files to read in full.
- **Cross-references vary by type** — actor entries show use case participation and drive. Event entries show producer and consumers. Use case entries show bounded context and primary actor. The form documents each type's cross-reference pattern.
- **Ordering** — entries are ordered by numeric prefix, matching the file ordering in the folder.
- **Referencing style** — siblings use bare `{nn}-{slug}`. Cross-topic references use `{namespace}/{nn}-{slug}`. No markdown link syntax.
