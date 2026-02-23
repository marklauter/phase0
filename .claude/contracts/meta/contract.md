## Contract

What a contract is, how the layers relate, and where to edit.

## The atomic unit

A contract is the atomic unit of modeling knowledge. Each contract has two expressions that share the same name:

- The modeling file in `.claude/contracts/` (a principle or a form) is the single source of truth — it defines what to produce or what to verify, and carries the authoritative prose.
- The skill file in `.claude/skills/` is a thin loader — YAML front matter for triggering, plus a `!`cat`` directive that injects the modeling file's content at activation time. Skills carry no duplicated body content.

The modeling file is the only place to edit contract content. The skill's YAML `description` is the source of truth for triggering language. Agents receive contract content by listing skills in their `skills:` array — the skill injects the modeling file when the agent loads.

## Form contracts and skill pairs

Form contracts map to a pair of skills:

- `reading-*` — `!cat` to the form + discovery and navigation exposition. How to find and interpret artifacts of this type.
- `writing-*` — `!cat` to the form + creation machinery (scripts, guidance). How to produce artifacts of this type.

The form is the single source of truth for structure. The skills add operational knowledge — one for consumption, one for production. Three files, no duplication.

## Layering

Each layer has one job: principles teach rules, agents declare scope, skills inject content. Say it once, in the right place.
