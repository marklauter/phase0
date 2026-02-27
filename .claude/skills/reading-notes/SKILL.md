---
name: reading-notes
user-invokable: false
disable-model-invocation: false
description: Read, review, or scan design notes — captured observations, questions, discoveries, session history. Loads the note form contract and reading guidance.
---

Read the form at `.claude/contracts/forms/note.md` when you need to verify structure.

## Reading notes

Notes have no index file. Discovery is manual.

- **List** — `ls notes/` within the model directory. The ISO datetime prefix sorts chronologically. Newest notes are often most relevant to active work.
- **Scan by topic** — grep `notes/` to find notes related to a specific artifact, actor, or design question. Matches may appear in the title, Context, Body, or References sections.
- **Follow references** — the `## References` section cross-links back into the model. Use it to find every note that touches a specific artifact.
- **Staleness** — notes are raw captures. Some will have been formalized into artifacts since they were written. Check whether the referenced artifact already incorporates the note's content before acting on it.
