# Skills audit report

**25 skills reviewed** across 3 categories: 7 philosophy, 9 reading, 9 writing.

## What's working well

- **All `!cat` targets resolve.** Every referenced file in `modeling-contracts/` exists. No broken injections.
- **All scripts referenced in writing skills exist.** 9 scripts, 9 writing skills, all matched.
- **Reading/writing pairs are complete.** All 9 artifact types have both a reading and writing skill.
- **Consistent internal structure.** Philosophy skills are pure `!cat`. Reading skills are `!cat` + "## Reading {type}" guidance. Writing skills are `!cat` + "## Creating {type}" with script usage. Clean pattern.
- **Script paths use relative format** per CLAUDE.md convention (`bash .claude/scripts/...`).
- **Frontmatter is valid** on all 25 skills — `name` and `description` present, no malformed YAML.

## Issues to address

### 1. Duplicate injection — `facilitating-design` content loaded twice

CLAUDE.md includes this:

```
## Facilitation
@.claude/modeling-contracts/principles/facilitating-design.md
```

The `facilitating-design` skill also `!cat`s the same file. In the main conversation, the content from CLAUDE.md's `@`-include is always present. When the skill fires, the same content appears a second time. This wastes context window.

**Fix:** Remove the `@`-include from CLAUDE.md and rely solely on the skill, OR remove the skill and rely on the `@`-include (since this is always-on guidance for the facilitator role, the `@`-include may be the right home).

### 2. Ghost directory — `testing-content-injection`

The directory `.claude/skills/testing-content-injection/` is empty or doesn't exist, yet it appears in the IDE's additional working directories. Stale reference from an experiment.

**Fix:** Delete the empty directory if it exists, or remove the working directory reference.

### 3. Naming anomaly — `writing-documentation`

Named like a writing skill (`writing-*`) but functions as a philosophy skill — it `!cat`s from `principles/`, not `forms/`. There's no corresponding `reading-documentation` skill. This breaks the naming convention where `writing-*` always pairs with `reading-*` and always injects a form.

**Fix:** Consider renaming to something that doesn't collide with the form-pair pattern — e.g., `editorial-standards`, `prose-style`, or `style-guide`. Update all references (agent skills arrays, CLAUDE.md, memory).

### 4. Description trigger overlap — `writing-usecases` vs `modeling-usecases`

- `writing-usecases`: *"write a use case"*, *"create a use case file"*, *"structure a use case"*
- `modeling-usecases`: *"design a use case"*, *"write a scenario"*, *"identify goal obstacles"*, *"structure an interaction"*

A user saying "structure a use case" fires the writer. A user saying "structure an interaction" fires the philosopher. These are conceptually different (structure = form scaffold vs. structure = design philosophy), but the near-identical phrasing could cause misfires.

**Fix:** Sharpen the differentiator in each description. E.g., `writing-usecases` could emphasize "create the use case *file*" and "scaffold sections." `modeling-usecases` could emphasize "discover the scenario through interview" and "apply use case lens philosophy."

### 5. Boilerplate prefix — "This skill should be used when..."

All 25 descriptions start with "This skill should be used when..." — 8 words of zero-information prefix before any trigger content. The description field is what Claude matches against. Conciser descriptions would improve signal-to-noise for triggering.

Current:

> "This skill should be used when the user asks to 'read an actor', 'review an actor', 'check the actor format', 'understand who participates', or when an agent needs to understand the structure of actor files. Loads the structural contract for actor documents."

Could be:

> "Read, review, or check actor files and their format. Understand the structure of actor documents. Loads the structural contract."

**Fix:** This is a style choice and the consistency has value. But if you want tighter triggering, trim the boilerplate.

### 6. Potential double-injection in agents loading both `reading-*` and `writing-*`

Both `reading-usecases` and `writing-usecases` inject the identical form via `!cat .claude/modeling-contracts/forms/usecase.md`. Any agent loading both would get the form twice. Currently `designing-usecases` only loads `writing-usecases`, so this doesn't happen in practice. But future agents loading both pairs would waste context.

**Fix:** No immediate action needed. Worth noting as a design constraint — agents should load one or the other per artifact type, not both.

### 7. `preserving-discoveries` has no user trigger phrases

Every other skill includes quoted user phrases ("read an actor", "map bounded contexts"). `preserving-discoveries` only describes agent behavior: *"when an agent conducts interviews, models artifacts..."* It will never fire from a user's natural language request.

**Fix:** This is probably intentional — it's agent-behavioral, not user-facing. But if you want it user-triggerable (e.g., "capture this discovery", "preserve what we just found"), add trigger phrases.

## Summary

- Broken references: 0 — clean
- Missing pairs: 0 — complete
- Structural consistency: 25/25 — uniform
- Duplicate injection: 1 — `facilitating-design` via CLAUDE.md + skill
- Naming anomaly: 1 — `writing-documentation` breaks pair pattern
- Trigger overlap: 1 — `writing-usecases` / `modeling-usecases`
- Ghost artifact: 1 — `testing-content-injection`
