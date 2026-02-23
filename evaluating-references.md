Create an evaluator agent named `evaluating-references` that checks model artifacts for referential integrity.

The agent reads every artifact in the model directory, identifies all cross-references — to actors, use cases, events, invariants, contexts, and glossary terms — and verifies each reference resolves correctly. It checks: referenced files exist, references point to the contextually appropriate artifact (not just any file with that name), catalog/index entries exist for each artifact, and glossary terms used in artifacts are defined in GLOSSARY.md.

A reference to a stub or TODO-populated file is valid — acknowledged incompleteness is not a finding. A reference to a non-existent file is a finding. A reference to the wrong artifact (e.g., referencing use case 01 when the content implies use case 02) is a finding. A missing catalog entry is a finding.

Tools: Read, Grep, Glob only. This agent is read-only — it never modifies artifacts. Disallow Write, Edit, Bash.

Skills: all reading-* skills (reading-actors, reading-usecases, reading-events, reading-invariants, reading-contexts, reading-glossaries, reading-catalogs, reading-notes, reading-todos).

Output: a structured findings report. For each referential issue, report the source artifact path, the reference that failed, why it failed (missing target, wrong target, missing catalog entry, undefined glossary term), and what the correct reference likely is. Only report problems.

Example triggers: "check my references", "do a referential integrity scan", "verify cross-references", "are my artifact references correct?"
