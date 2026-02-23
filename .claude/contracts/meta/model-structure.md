## Model structure

The single source of truth for what a Phase0 model contains, where each artifact lives, and the design workflow that produces it.

## Model root

Each model lives at `models/{owner}/{repo}/`. The path mirrors the GitHub URL structure of the system being modeled. The model root contains one cross-cutting artifact — `GLOSSARY.md` — and one directory per artifact type.

## Artifact directories

### actors/

Primary actors with conditional goals. Supporting actors with drives. Sub-system actors with capabilities. Each file defines one actor: their role, their goal or drive, and where they appear.

- File naming: `{nn}-{slug}.md` (e.g., `01-user.md`)
- Catalog: `actors/index.md`
- Form: `.claude/contracts/forms/actor.md`

### use-cases/

One file per use case. Each describes one goal pursued by one primary actor — the desired end state, the scenario, the invariants, the obstacles, and the domain events.

- File naming: `{nn}-{slug}.md` (e.g., `01-populate-new-wiki.md`)
- Catalog: `use-cases/index.md`
- Form: `.claude/contracts/forms/usecase.md`

### contexts/

Bounded context definitions. Each file describes one semantic region — its purpose, ubiquitous language, use cases, events produced and consumed, and integration points with other contexts.

- File naming: `{nn}-{slug}.md` (e.g., `01-wiki-creation.md`)
- Catalog: `contexts/index.md`
- Form: `.claude/contracts/forms/context.md`

### events/

Published domain events — durable facts that cross bounded context boundaries. Each file describes one event: the producing context, the consuming contexts, the payload, and the materialization.

- File naming: `{nn}-{slug}.md` (e.g., `01-wiki-populated.md`)
- Event names: PastTense (e.g., WikiPopulated, FindingFiled)
- Catalog: `events/index.md`
- Form: `.claude/contracts/forms/event.md`

### invariants/

Shared invariants — continuous constraints that hold across multiple use cases. An invariant applies to specific use cases, named in its scope. Invariants that appear in only one use case live inside that use case file; they migrate to shared invariants the second time they surface.

- File naming: `{nn}-{slug}.md` (e.g., `01-source-repo-readonly.md`)
- Catalog: `invariants/index.md`
- Form: `.claude/contracts/forms/invariant.md`

### notes/

Timestamped discovery captures. A note records an observation, question, or proposal that emerged during a session. Notes are durable — they persist as a record of how the model evolved.

- File naming: `{ISO-datetime}-{slug}.md` (e.g., `2026-02-22T0332-actor-to-skill-mapping.md`)
- Form: `.claude/contracts/forms/note.md`

### todos/

Ephemeral work items. A todo describes a concrete action to be taken. Todos are deleted when completed — they do not accumulate.

- File naming: `{slug}.md` (e.g., `bootstrap-phase0-model.md`)
- Form: `.claude/contracts/forms/todo.md`

## Cross-cutting artifacts

### GLOSSARY.md

A single file at the model root. Alphabetical entries, one term per entry, one-sentence definition. Terms emerge through all three lenses and crystallize as the model matures. When a term carries different meanings in different bounded contexts, the glossary records the canonical definition; each context's ubiquitous language section records what the term means there.

- Form: `.claude/contracts/forms/glossary.md`

### Catalogs (index.md)

Each artifact directory except notes/ and todos/ contains an `index.md` catalog. One-sentence entries with cross-references. The catalog is the entry point for navigating that artifact type.

- Form: `.claude/contracts/forms/catalog.md`

---

## The design workflow

Design is a process of discovery. The system under design emerges through iterative examination from multiple perspectives — three lenses that form a complete graph (K₃). Three nodes, three edges, no preferred direction.

### The actor-first invariant

The actor lens is the foundational lens. Everything else derives from primary actors and their conditional goals. Establish the primary actor and their conditional goal before dispatching to use case or bounded context work. Even when the conversation enters through a different lens, the facilitator routes to actor discovery first.

### The three lenses

#### Actor lens — who does this system serve, and what do they value?

The actor lens discovers primary actors, their conditional goals, the tensions those goals create, and the supporting actors those tensions spawn.

Phases:

1. Identify primary actors. Refine sloppy nouns into standalone names with singular goals. "Customer" becomes Sender, Recipient, Complainant — each carrying its own meaning.
2. Extract conditional goals. Each primary actor has a desired end state coupled with value conditions. The value conditions are where system design comes from.
3. Expose tensions. Value conditions meet reality and produce tensions — the named gaps between what is valued and what can be delivered. Three sources: conflicts of interest (a supporting actor's drive obstructs a goal condition), environmental constraints (physical, systemic, or situational limits), and competing values (two value conditions on the same goal resist simultaneous satisfaction).
4. Derive system design from tensions. Tensions produce supporting actors, use cases, invariants, and trade-off decisions. Conflicts of interest and environmental constraints typically spawn supporting actors. Competing values force the primary actor to make trade-off decisions. Any tension can surface a use case or an invariant. Every supporting actor has a genealogy traceable to a primary actor's value conditions.

Produces: actor catalog, system boundary.

#### Use case lens — what interactions does the design demand?

The use case lens examines actors, goals, and tensions and asks: what does the system actually need to do? Use cases fall out of the actor lens — they are discovered, not invented.

Phases:

1. Anchor the use case. Confirm the primary actor and their conditional goal. Identify the trigger and the bounded context. Create the artifact early.
2. Discover supporting actors and responsibilities. Who else participates? What does each actor own? What is each supporting actor's drive?
3. Surface invariants and constraints. What rules hold at every moment? What is readonly, what is mutable, who owns each mutation?
4. Walk the scenario. Step by step in terms of intent, not mechanism. Name domain events at meaningful state transitions. Identify goal obstacles and recovery strategies.

Produces: individual use cases, use case catalog.

#### Bounded context lens — where do meanings partition?

The bounded context lens discovers regions where the same word means different things, where responsibilities separate naturally, and where integration contracts are needed.

Phases:

1. Identify context boundaries. Listen for term conflicts and responsibility separations. Each boundary candidate becomes a context.
2. Define ubiquitous language. Name the terms with precise meaning within each context. When a term appears in two contexts with different meanings, both definitions exist.
3. Map events produced and consumed. Walk use cases and identify every state transition that crosses a boundary. Name each as a domain event in PastTense.
4. Define integration points. For each pair of communicating contexts, name the relationship (requires, feeds, shares with) and the protocol.

Produces: bounded context definitions, domain events catalog.

### Cross-cutting artifacts

These emerge through all three lenses:

- Glossary — terms crystallize as the model matures. Any lens can surface a new term.
- Shared invariants — originate from value conditions in the actor lens, discovered when the same rule surfaces across multiple use cases, refined when context work reveals integration constraints.
- Notes — capture cross-lens discoveries, design decisions, and open questions.

### The K₃ feedback loop

Discoveries through any lens can refocus to any other. The facilitator shifts lenses freely, following discoveries wherever they lead.

- Use cases spawn actors. "Who makes this decision? That is not the same person who..." A new actor surfaces through the use case lens and feeds back to the actor lens.
- Bounded contexts redefine system boundaries. A term conflict reveals that what looked like one context is actually two. The actor lens revises accordingly.
- Tensions reveal context boundaries. A tension between two value conditions turns out to live at the boundary between two bounded contexts.
- Domain events expose missing use cases. An event is published but nothing reacts to it. A missing use case surfaces through the bounded context lens and feeds back to the use case lens.

The cycle repeats until the model converges — until new passes through each lens stop producing discoveries that invalidate earlier work.
