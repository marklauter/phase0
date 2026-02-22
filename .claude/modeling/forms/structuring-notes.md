# Structuring notes

This skill should be used when the user asks to "write a note", "capture an observation", "create a design note", "review a note file", or when an agent needs the structural contract for note documents. Defines the artifact shape — sections, ordering, and placeholder guidance — for note files captured during design sessions.

## Structure

Note files live at `notes/{ISO-datetime}-{slug}.md` within the model directory. The ISO datetime prefix provides stable chronological ordering (e.g., `2026-02-21T1430`). One file per note. The slug captures the topic in a few words.

```markdown
# {Topic title}

## Context

{What conversation or activity spawned this note. Enough to jog memory — what were we working on, what question or observation triggered this capture. One to three sentences.}

## Body

{The substance. Observations, questions, proposals, raw thinking. This is the note's reason for existing. Prose, bullets, or a mix — whatever captures the content most faithfully.}

## References

{Links back into the model. Each reference names the artifact type and identifier. Use "cross-cutting" when a note touches multiple concerns without belonging to one.}

- {artifact-type}/{nn}-{slug} ({why this note relates})
- cross-cutting ({brief explanation})
```
