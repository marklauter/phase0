# Contract structure

The internal structure of the instruction set — `.claude/contracts/` and `.claude/scripts/`.

## contracts/

### principles/

Core beliefs and philosophical prose that creators follow when producing content. Each file teaches one concept — a lens, a role, a vocabulary, a standard. Principles shape how agents think and what they value during design work.

### forms/

Structural contracts for artifacts. Each form defines the sections, ordering, and placeholder guidance for one artifact type. Forms are pure structure — no philosophy, no creation mechanics. They serve both reading and writing.

### meta/

Meta contracts — documents about the contract system itself. contract.md defines what a contract is. contract-structure.md covers the instruction set tree. model-structure.md covers the model output tree.

## scripts/

Deterministic helper scripts that agents call via Bash. One creation script per artifact type. Judgment stays in the agent; mechanics stay in the script. Always use relative paths (e.g., `bash .claude/scripts/create-note.sh`) to match permission patterns in `settings.json`.

## Extending the system

Read the matching form before writing any artifact. The form is the structural authority — same sections, same ordering. When a new artifact type is introduced, create a form in `.claude/contracts/forms/`, a creation script in `.claude/scripts/`, and corresponding reading and writing skills in `.claude/skills/`.
