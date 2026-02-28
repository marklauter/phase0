# Effective knowledge graphs are layered

## Context

Surfaced during reflection on how knowledge graph structure supports both human and agent consumption.

## Body

Effective knowledge graphs are layered. This is how abstractions are built — each layer captures a different level of detail or concern, and a human or agent accesses the relevant layer of information when needed. The layering principle means that no single consumer must parse the entire graph; instead, they navigate to the abstraction level that serves their current task. This mirrors how well-designed systems expose coarse-grained interfaces at higher layers while preserving fine-grained detail beneath.

**Layer boundary criteria.** The note says layers exist but not what makes a cut *right*. Two candidates: distinct consumer needs (an agent planning work needs different grain than one executing a step) and distinct rates of change (glossary terms stabilize early, use case scenarios keep evolving).

**Navigation affordances.** Layering only works if consumers can move between layers — drill down when they need detail, zoom out when they need orientation. That means layers need explicit links between them, not just coexistence in the same graph.

**Leaky layers as a failure mode.** When boundaries are wrong, low-level detail bleeds into high-level reasoning. Same problem as leaky abstractions in software. Worth naming as the thing layering is defending against.

**Phase0 as a concrete instance.** The model itself is a layered knowledge graph — actors at the top, use cases below, events and invariants beneath that, bounded contexts cutting across. Grounding the abstract principle in the thing we're building makes the note more useful.

## References

- cross-cutting (knowledge graph architecture, abstraction design)
