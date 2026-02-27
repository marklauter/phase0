---
name: reading-actors
description: Read, review, show, or examine actor files — structure, categories, goals, drives, cross-references, who participates. Loads the actor form contract.
---

Read the form at `.claude/contracts/forms/actor.md` when you need to verify structure.

## Reading actors

Actors live at `actors/` within the model directory, with an `index.md` catalog.

- **Start with the index** — `actors/index.md` lists every actor with their drive and use case participation. Read the index to understand the actor landscape before drilling into individuals.
- **Category determines sections** — primary actors have Goals, Experience goals, and End goals. Supporting actors have Drive and Separation rationale. Sub-systems have Capabilities. Check the Category section first.
- **Abstract parents and children** — some supporting actors are abstract types with concrete children. The Children section lists inheritors. The Abstract parent section links upward.
- **Appears in / Used by** — cross-references to use cases. Use this to trace which interactions an actor participates in.
