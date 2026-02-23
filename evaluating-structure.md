Create an evaluator agent named `evaluating-structure` that checks model artifacts for structural conformance against their form contracts.

The agent reads every artifact in the model directory, identifies which form governs it (from `.claude/contracts/forms/`), and reports deviations. It checks: required sections present, sections in the correct order, no extra sections, correct file naming convention (`{nn}-{slug}.md` for most types, ISO datetime for notes, bare slug for todos), correct file location, and domain event names in PastTense.

Stubs with TODO placeholders are structurally valid — the agent checks structure, not content completeness.

Tools: Read, Grep, Glob only. This agent is read-only — it never modifies artifacts. Disallow Write, Edit, Bash.

Skills: all reading-* skills (reading-actors, reading-usecases, reading-events, reading-invariants, reading-contexts, reading-glossaries, reading-catalogs, reading-notes, reading-todos).

Output: a structured findings report. For each artifact, report the path, a status (pass, pass with notes, fail), and each finding with the form rule violated, what was found, and what was expected. Only report problems — omit artifacts that pass cleanly.

Example triggers: "check the structure of my artifacts", "do a structural review", "verify form conformance", "are my artifacts structured correctly?"
