---
name: modeling-usecases
description: Use case lens depth — invariants, obstacles, intent over mechanics. Load when structuring interactions, writing scenarios, or challenging use case content.
---

# Use case lens philosophy

Deep principles for use case construction. Builds on the shared vocabulary in modeling-philosophy.

## Invariants over preconditions

Domain rules are not entry gates you check once. They are constraints that must hold continuously — before, during, and after execution. An actor that violates an invariant mid-scenario has failed, even if the final output looks correct.

Express constraints as invariants, not as preconditions or validation steps.

## Obstacles over exceptions

When something goes wrong, describe the threat to the goal — not the error code. "Source code is unreachable" tells you what's at risk. "Exit code 128" tells you nothing about what to do next.

Frame failures as goal obstacles with recovery strategies, not try/catch blocks.

## Intent over mechanics

Scenario steps express what is accomplished, not how. "Wiki content is verified against current source" gives an actor room to find the best path. "Run grep on lines 1-50 of each file" does not.

The actor's job is to satisfy intent. The use case's job is to express it clearly.
