# Modeling foundation

The shared vocabulary and conceptual foundation for domain modeling — goals, drives, tensions, conflicts of interest, environmental constraints, competing values, conditional goals, invariants, and domain events. Grounded in Alan Cooper's goal-directed design and Eric Evans' domain-driven design. Lens-specific depth lives in actor-lens, usecase-lens, and context-lens.

## Foundations

This vocabulary is grounded in Alan Cooper's goal-directed design and Eric Evans' domain-driven design. Cooper contributes the actor model — goals, drives, conditional goals, and the idea that actors are predictable because of what they value. Evans contributes the structuring model — bounded contexts, domain events as published language, ubiquitous language as the shared vocabulary within a context, and system invariants as continuous constraints.

## Primary actors have goals; supporting actors have drives

A primary actor has a *goal* — a desired end state the system exists to serve. The system is built for them. Their goals always have conditions.

A supporting actor has a *drive* — a reason to participate. Drives explain why supporting actors exist at all. They are born from tensions — gaps between what primary actors value and what can be delivered.

Goals and drives both make actors predictable in a modeling sense. You know what a primary actor wants to achieve, and you know what a supporting actor will optimize for — and therefore where it will fall short. An actor makes decisions shaped by what it cares about.

## Goals are conditional

A primary actor's goal is a conditional goal: a desired end state plus the values the actor holds about how they exist in that state. A conditional goal is a value statement — it expresses both *where* the actor wants to be and *what they value* about being there.

## Tensions have causes

A tension is a force — the named gap between what a primary actor values and what can be delivered. Tensions arise from multiple sources:

- A *conflict of interest* — a supporting actor's drive obstructs achievement of a primary actor's goal condition. The Owner's cost-minimization drive obstructs the Passenger's safety condition. The conflict is the cause; the tension is the force it produces.
- An *environmental constraint* — a physical, systemic, or situational limit that obstructs a primary actor's goal condition. Building capacity obstructs the Passenger's "promptly" condition. No actor controls it — it is a feature of reality.
- *Competing values* — two value conditions on the same primary actor's goal resist simultaneous satisfaction. "Safely" and "promptly" pull in opposite directions. Competing values force the primary actor to make trade-off decisions — prioritization, not delegation.

Tensions produce system design. Supporting actors, use cases, invariants, and trade-off decisions all emerge from tensions. Conflicts of interest and environmental constraints typically spawn supporting actors. Competing values force the primary actor to make trade-off decisions. Any tension can surface a use case or an invariant.

## Domain events are the published language

Actors communicate through meaningful state transitions. A drift assessment, a filed finding, a change report — these are domain events. They are the published language between bounded contexts.

Name them. Define them. They are the integration points of the system.

## Markdown is the wire format

Protocols, domain events, reports, and assessments are all materialized as markdown. The consumers are humans and LLM agents, and markdown is the format both read natively. Every consumer is a capable reader — the wire format and the human-readable format are the same.

This is a deliberate choice. A system whose integration points are optimized for human and AI consumption communicates directly through readable documents.

## Nouns, verbs, and objects

- Actors are nouns. Proofreader, Creator, Corrector, Commissioning orchestrator. They're *who*.
- Use cases are verbs. Populate New Wiki, Review Wiki Quality, Sync Wiki with Source Changes. They're *what happens*.
- Events are nouns — past participles used as nouns. WikiPopulated, FindingFiled, WikiSynced. They're *what was produced*, the fact that something happened.

## Extract what the expert knows

Use case design is Socratic. The designer asks questions; the domain expert has the answers. The designer's job is to draw out goals, constraints, and events that the expert already knows and structure them. Every element in the model traces to something the domain expert confirmed.

Work one phase at a time. Summarize what you heard before moving on. If the answer is task-oriented ("it runs git pull"), redirect to intent ("what state does that achieve?"). If something contradicts a principle in this document, flag it.

The user knows the domain. The designer knows how to structure it.
