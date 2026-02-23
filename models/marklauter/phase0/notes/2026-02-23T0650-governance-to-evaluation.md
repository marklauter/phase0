# Governance decomposed into four evaluation lenses

## Context

Socratic session exploring the right framing for artifact governance. Started from the governing-artifacts agent and the wiki-reviewer agent in the wiki-agent project. Discovered that governance names the authority, evaluation names the act, and the act decomposes into four independent lenses.

## Body

Governance is the authority the facilitator exercises. Evaluation is the act — read-only, compare against standards, produce findings. The single governing-artifacts agent was replaced by four evaluation lens agents, each dispatched in parallel by the facilitator.

The four lenses:
- evaluating-structure — artifact matches its form contract (sections, ordering, naming, location)
- evaluating-references — cross-references resolve to existing, contextually appropriate artifacts
- evaluating-coherence — semantic drift and contradiction across the model as a whole
- evaluating-style — prose against the editorial standards contract

Key architectural decisions:
- Each lens is an independent agent, not a skill or a sub-task within one agent. This allows parallel dispatch.
- Evaluators are read-only — they never modify artifacts. The read-only constraint is both mechanical (tools restricted to Read, Grep, Glob) and principled (the evaluator observes and reports).
- The evaluation form is guidance, not rigid template. Each lens adapts the output format to its needs while meeting shared invariants (summary, evidence, contract citation).
- Stubs are valid — acknowledged incompleteness is not a finding.
- Evaluators do not prescribe fixes. The author decides how to remediate.
- Proto-governance in producing agents (designing-usecases post-write validation) was removed. Durable capture handles in-session preservation. Evaluation is a separate act dispatched separately.
- Self-check principle was scrapped because sessions have no clear done state and running checks every turn wastes context and produces false positives.
- After consolidating evaluation findings, the facilitator offers to create todos for actionable items. The user decides which findings become work.
- Contradiction vs. Ambiguity classification in the coherence lens is not severity — it is classification of the finding type.

## References

cross-cutting (governance architecture, agent decomposition, evaluation lenses)
