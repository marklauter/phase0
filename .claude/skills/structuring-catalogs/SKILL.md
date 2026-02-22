---
name: structuring-catalogs
description: This skill should be used when the user asks to "write an index", "create a catalog", "update the index file", "review the index format", or when an agent needs the structural contract for catalog documents. Defines the artifact shape — index format, entry layout, cross-references, and ordering — for index.md files.
---

## Location

Each topic folder in the model contains an `index.md` that indexes the artifacts in that folder. The index gives agents enough context to select which full artifacts to read.

```
models/{owner}/{repo}/{topic}/index.md
```

Where `{topic}` is one of: `actors`, `contexts`, `events`, `invariants`, `use-cases`.

## Structure

```markdown
# {Topic}

{One-sentence description of what this artifact type represents in the model.}

## Entries

- {nn}-{slug} — {What it signifies, in one sentence.}
  {Cross-references to related artifacts as paths.}
```

## Entry format

Each entry is a bullet with:

1. **Identifier** — the file's `{nn}-{slug}` (no extension, no namespace — the index is already in the folder)
2. **Description** — one sentence describing what the artifact signifies — its meaning in the model
3. **Cross-references** — related artifacts from other topic folders, using the `{namespace}/{nn}-{slug}` identifier format. The cross-reference labels vary by artifact type:

### Use cases

- Bounded context, primary actor

### Contexts

- Use cases that live in this context

### Events

- Producer (the use case that emits this event)
- Consumers (the use cases or contexts that react to it)

### Actors

- Use cases this actor participates in
- Drive (one phrase)

### Invariants

- Use cases this invariant governs

## Ordering

Entries are ordered by numeric prefix, matching the file ordering in the topic folder.

## Referencing style

Sibling artifacts (same folder) use the bare `{nn}-{slug}` identifier. Cross-topic references use the full `{namespace}/{nn}-{slug}` path. No markdown link syntax — the path is the identifier.

```markdown
Producer: use-cases/01-populate-new-wiki.
```
