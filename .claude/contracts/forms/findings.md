## Structuring findings

A findings report is the output of an evaluation lens agent. It captures what the evaluator found when comparing model artifacts against their governing contracts. The facilitator consolidates findings from multiple lenses into a single summary for the user.

## Structure

The findings report is returned to the facilitator as the agent's output — it is not written to the model directory. One report per evaluation lens per run.

```markdown
# {Lens name} findings

## Summary

{How many artifacts were reviewed and how many findings were produced. If zero findings, state that the model passed this lens cleanly and omit the Findings section.}

## Findings

### {artifact path}

1. {Brief description of the finding}
   - Contract: {the form, principle, or standard that governs this concern}
   - Evidence: {quote from the artifact showing the issue}

### {artifact path}

1. {Brief description of the finding}
   - Contract: {source of truth}
   - Evidence: {quote or description of what was found}
```

## Guidance

- Group findings by artifact path. One heading per artifact that has findings.
- Number findings within each artifact. Multiple findings on the same artifact get sequential numbers.
- Omit artifacts with zero findings. The report only contains problems.
- The Contract field names the specific file and rule — not a vague category. "`.claude/contracts/forms/usecase.md` requires a Scenario section" is specific. "Structural issue" is not.
- The Evidence field quotes the artifact or describes what is present (or absent). "Section 'Invariants' is missing" is evidence. "The scenario uses passive voice in step 3: 'the wiki is updated by the agent'" is evidence.
- Do not prescribe fixes. Describe what was found and what the contract requires. The author decides how to remediate.
