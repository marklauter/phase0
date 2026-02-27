# Skill description best practices

## Context

Emerged from two rounds of reworking all 32 skill descriptions. The first round (branch claude/actors-implementation) removed boilerplate prefixes. The second round (branch claude/skill-rework) applied a consistent structural pattern and keyword density strategy. This note codifies what we learned so future skills get it right the first time.

## Body

### The pattern

Every skill description follows this structure:

```
{verb cluster} — {keyword list}. {what gets loaded}.
```

Three segments, separated by an em-dash and a period.

#### Segment 1 — verb cluster

Lead with action verbs that match what users actually say. Use commas to pack multiple verbs: "Create, write, or scaffold" not "Create and structure." The verbs are the primary trigger surface — they determine whether the skill activates.

- Use imperative verbs, not gerunds. "Write, proofread, review" not "Writing prose, proofreading."
- Include 2-4 verbs covering natural language variations. A user might say "inspect" instead of "review" or "look up" instead of "read."
- For reading skills, vary the first verb where it fits the domain: "Look up" for glossaries, "Read, browse" for catalogs, "Read, review, or scan" for notes.
- For writing skills, include "scaffold" or "stub" alongside "create" and "write" — users often want partial files.

#### Segment 2 — keyword list

After the em-dash, pack domain-specific nouns and noun phrases. These are the content trigger surface — they match when users mention specific concepts.

- Use the actual domain vocabulary: "conditional goals, value conditions, tensions" not "actor properties."
- Include the artifact's key structural sections: "scenarios, goals, invariants, obstacles, domain events" for use cases.
- For reading/writing pairs, the keyword lists should overlap but not be identical. The reading skill emphasizes what you inspect; the writing skill emphasizes what you produce.

#### Segment 3 — what gets loaded

End with what the skill injects into context. This serves double duty: it tells the model what it is about to receive, and it distinguishes reading from writing skills.

- Reading skills: "Loads the {type} form contract and reading guidance."
- Writing skills: "Loads the {type} form contract and creation script."
- Behavioral skills (no reading/writing pair): end with a short declarative. "Actor lens depth." "Cooper and Evans foundations for the design cycle."
- Skills without creation scripts (evaluations): "Loads the evaluation form contract." — no "and creation script."

### Anti-patterns

- **Boilerplate tails.** "Structural contract for X documents" is dead weight — it says nothing the skill name does not already say. Replace with "Loads the X form contract" which tells the model what to expect.
- **Quoted exact-match phrases.** Descriptions like '"write that down", "save that", "make a note"' waste tokens on specific phrases that might not match. Use verb clusters instead: "Capture and preserve discoveries durably."
- **Gerund-leading descriptions.** "Writing prose, proofreading" reads as a category label, not an action. "Write, proofread, review" reads as capability.
- **Internal cross-references.** "Lens-specific depth lives in discovering-actors, modeling-usecases, and mapping-contexts" belongs in documentation, not in a trigger description. Every token in the description should help activation.
- **Vague terms.** "Check model quality" could mean anything. "Structural conformance, referential integrity, semantic coherence, editorial standards" names exactly what gets checked.

### Consistency rules

- Em dash character (\u2014), not double hyphens (--).
- No bold, no markdown formatting in descriptions.
- One or two sentences. Never three.
- Every description starts with a verb. No exceptions.

## References

cross-cutting (applies to all 32 skills in .claude/skills/)
