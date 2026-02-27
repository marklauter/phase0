---
name: reading-glossaries
user-invokable: false
disable-model-invocation: false
description: Read the glossary. Look up a term, check the vocabulary, find a definition. Structural contract for GLOSSARY.md files.
---

Read the form at `.claude/contracts/forms/glossary.md` when you need to verify structure.

## Reading glossaries

The glossary is a single file at `GLOSSARY.md` in the model root. Entries are alphabetical.

- **Model-spanning terms only** — the glossary holds terms that span the model. Terms scoped to one bounded context live in that context's Ubiquitous language section instead.
- **Check both locations** — to find a term's definition, check GLOSSARY.md first, then the relevant context file's Ubiquitous language section.
- **Formerly annotations** — renamed terms carry a "Formerly:" note. If you encounter an unfamiliar term, it may have been renamed — grep the glossary for the old name.
