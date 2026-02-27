---
name: reading-events
description: Read, review, show, or examine domain event files — producers, consumers, payloads, materialization, state transitions. Loads the event form contract.
---

Read the form at `.claude/contracts/forms/event.md` when you need to verify structure.

## Reading events

Events live at `events/` within the model directory, with an `index.md` catalog.

- **Start with the index** — `events/index.md` lists every event with its producer and consumers. Read the index for the full event catalog before drilling into individuals.
- **PastTense naming** — event names describe what happened (WikiPopulated, FindingFiled). The name alone should convey the state transition.
- **Context section** — names the bounded context, the producing use case, the consumers, and the materialization. This is the event's integration contract.
- **Payload** — the data the event carries. Each item is a noun or noun phrase. The payload defines what downstream consumers can depend on.
