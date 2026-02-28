# Skill description best practices

## Context

Emerged from three rounds of reworking all 32 skill descriptions. The first round removed boilerplate prefixes. The second round applied a structural pattern and keyword density strategy. The third round stripped repetitive "Loads the X form contract" tails and normalized writing-* verbs, revealing that every token in a description must earn its place as trigger surface.

## Body

### The pattern

Every skill description follows this structure:

```
{verb phrase} — {keyword-rich detail}.
```

Two segments, separated by an em dash.

#### Segment 1 — verb phrase

Lead with the action the skill performs. The verb phrase is the primary trigger surface — it determines whether the skill activates.

- Use imperative verbs, not gerunds. "Write, proofread, review" not "Writing prose, proofreading."
- For writing skills, lead with "Write" and name the artifact type. "Write actor files", "Write notes", "Write domain event files."
- For reading skills, lead with verbs that match how users ask. Vary by domain: "Look up" for glossaries, "Read, browse, or review" for catalogs, "Read, review, or scan" for notes.
- For behavioral skills, lead with the skill's core action. "Discover, identify, and challenge actors", "Capture and preserve discoveries durably."

#### Segment 2 — keyword-rich detail

After the em dash, pack domain-specific nouns, noun phrases, and structural terms. These are the content trigger surface — they match when users mention specific concepts.

- Use actual domain vocabulary: "conditional goals, value conditions, tensions, drives" not "actor properties."
- Include the artifact's key structural elements: "scenarios, goals, invariants, obstacles, domain events" for use cases.
- For reading/writing pairs, the keyword lists should overlap but not be identical. The reading skill emphasizes what you inspect; the writing skill emphasizes what you produce.
- Spend every token on terms that help the model discriminate between skills. If a phrase appears identically in multiple descriptions, it adds no discriminating power and should be replaced with something specific.

### Anti-patterns

- **Repetitive tails.** "Loads the X form contract and creation script" appears on every writing skill and "Loads the X form contract and reading guidance" on every reading skill. Identical boilerplate across a category adds zero discriminating power — the model cannot use it to choose between skills. Replace with domain keywords that differentiate.
- **Quoted exact-match phrases.** Descriptions like '"write that down", "save that", "make a note"' waste tokens on specific phrases that might not match. Use verb clusters instead: "Capture and preserve discoveries durably."
- **Gerund-leading descriptions.** "Writing prose, proofreading" reads as a category label, not an action. "Write, proofread, review" reads as capability.
- **Internal cross-references.** "Lens-specific depth lives in discovering-actors, modeling-usecases, and mapping-contexts" belongs in documentation, not in a trigger description. Every token in the description should help activation.
- **Vague terms.** "Check model quality" could mean anything. "Structural conformance, referential integrity, semantic coherence, editorial standards" names exactly what gets checked.

### Consistency rules

- Em dash character, not double hyphens.
- No bold, no markdown formatting in descriptions.
- One or two sentences. Never three.
- Every description starts with a verb. No exceptions.

## References

cross-cutting (applies to all 32 skills in .claude/skills/)
