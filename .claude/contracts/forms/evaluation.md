# Structuring evaluations

An evaluation report is the output of an evaluation lens agent. It captures what the evaluator found when comparing model artifacts against their governing contracts. The facilitator consolidates reports from multiple lenses into a single summary for the user.

## Structure

The evaluation report is returned to the facilitator as the agent's output — it is not written to the model directory. One report per evaluation lens per run.

This form is guidance, not a rigid template. Each lens adapts the format to its needs — a structural evaluator may use tables, a coherence evaluator may quote two artifacts side by side. The invariants below apply to all lenses; the specific layout is the lens's choice.

## Invariants

Every evaluation report includes:

- A summary with artifact count and finding count.
- Findings grouped by artifact path or by category — the lens decides which grouping serves clarity.
- Evidence for every finding — quote the artifact text or describe what is present or absent.
- Contract citation for every finding — name the specific file and rule, not a vague category. "`.claude/contracts/forms/usecase.md` requires a Scenario section" is specific. "Structural issue" is not.
- Zero-finding case — if no findings exist, state that the model passed this lens cleanly.

## Minimal example

```markdown
# {Lens name} evaluation

## Summary

{Artifact count, finding count. If zero findings, state the model passed this lens cleanly.}

## Findings

### {artifact path}

1. {Brief description of the finding}
   - Contract: {the form, principle, or standard that governs this concern}
   - Evidence: {quote from the artifact showing the issue}
```
