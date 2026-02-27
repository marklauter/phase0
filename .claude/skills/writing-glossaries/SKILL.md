---
name: writing-glossaries
description: Add glossary entries. Define a term, update the glossary, maintain alphabetical order. Structural contract and creation script.
---

!`cat .claude/contracts/forms/glossary.md`

## Writing glossary entries

Use the `create-glossary-entry.sh` script to add entries. The script creates `GLOSSARY.md` if it doesn't exist and appends the entry.

```
bash .claude/scripts/create-glossary-entry.sh <model-dir> <term> <definition>
```

- **model-dir** — path to the model directory (e.g., `models/marklauter/github-wiki-agent`)
- **term** — the term to define (e.g., `Editorial lens`)
- **definition** — one sentence, present tense, declarative (e.g., `A distinct editorial discipline applied to wiki content during review.`)

The script appends to the end of the file. Use Edit to move the entry into alphabetical position after appending. If a term is only meaningful within one bounded context, add it to that context's Ubiquitous language section instead.
