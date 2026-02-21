# Structuring catalogs

A catalog is an index of artifacts that share a type. Each topic folder in the model has a matching catalog file under `catalogs/`. The catalog gives agents enough context to select which full artifacts to read.

## Location

```
models/{owner}/{repo}/catalogs/{topic}.md
```

Where `{topic}` matches the folder name: `actors`, `contexts`, `events`, `invariants`, `use-cases`.

## Structure

```markdown
# {Topic}

{One-sentence description of what this artifact type represents in the model.}

## Entries

- [{Name}](../topic/nn-slug.md) — {What it signifies, in one sentence.}
  {Cross-references to related artifacts as relative markdown links.}
```

## Entry format

Each entry is a bullet with:

1. **Link** — display name and relative path to the artifact file
2. **Description** — one sentence describing what the artifact signifies — its meaning in the model
3. **Cross-references** — related artifacts from other topic folders, as relative markdown links. The cross-reference labels vary by artifact type:

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

All cross-references use relative markdown links. Reference artifacts by their display name with a link to their path.

```markdown
Producer: [Populate new wiki](../use-cases/01-populate-new-wiki.md).
```
