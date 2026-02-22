---
name: structuring-glossaries
description: This skill should be used when the user asks to "write the glossary", "add a glossary entry", "structure the glossary", "review the glossary format", or when an agent needs the structural contract for glossary documents. Defines the artifact shape — sections, ordering, and placeholder guidance — for GLOSSARY.md files.
---

## Structure

The glossary is a single file that defines every term with precise meaning within the model. The glossary lives at `GLOSSARY.md` in the model root.

```markdown
# Glossary

{Entries in alphabetical order. One entry per term.}

**{Term}** — {Definition in one sentence.}
```

## Entry format

Each entry is a single line:

1. **Term** — bolded, followed by an em dash (`—`)
2. **Definition** — one sentence, present tense, declarative

If a term needs a paragraph, it belongs in a principle or its own artifact.

## Renamed terms

When a term has been renamed, add a "Formerly:" annotation. This prevents newcomers from reviving retired vocabulary.

```markdown
**Editorial lens** — A distinct editorial discipline applied to wiki content during review. Formerly: pass.
```

## Ordering

Entries are alphabetical by term.

## Scope boundaries

Terms defined in a bounded context's ubiquitous language section stay there. A term appears in the glossary when it spans the model — when multiple contexts or artifacts rely on its meaning.
