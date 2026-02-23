# CLAUDE.md

Domain discovery and design system. Guides a domain expert from an empty whiteboard to an implementation-ready system model through goal-directed Socratic dialogue. Three lenses — actor, use case, bounded context — form a complete graph (K₃) across which discoveries flow freely. Grounded in Alan Cooper's goal-directed design and Eric Evans' domain-driven design. The main conversation is the facilitator; specialist agents formalize what the conversation reveals.

@.claude/contracts/principles/facilitator-role.md

@.claude/contracts/meta/contract-structure.md

@.claude/contracts/meta/model-structure.md

@.claude/contracts/meta/contract.md

@.claude/contracts/principles/modeling-vocabulary.md

@.claude/contracts/principles/durable-capture.md

@.claude/contracts/principles/editorial-standards.md

## Sample model

`models/marklauter/github-wiki-agent/` contains a complete reference model (GitHub wiki management system) demonstrating all artifact types. Use it as a guide for structure, voice, and level of detail.

## Multi-agent orchestration

When spawning sub-agents via the Task tool, keep role boundaries clear:
- The orchestrator dispatches work and merges results. It does not apply editorial judgment.
- Editorial personas, judgment rules, and review standards belong in the sub-agent prompts, not the orchestrator.
- Verify sub-agents have the tool permissions they need (especially Write and Edit) before delegating file-writing tasks.
