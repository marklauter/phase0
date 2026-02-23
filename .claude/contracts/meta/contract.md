# Contract

The organizing principle behind the instruction set — what makes a contract different from other knowledge in the system.

## Binding knowledge

A contract is a binding piece of knowledge. It constrains how agents think or what they produce. The system carries many kinds of knowledge — conversation history, domain expert input, model artifacts — but a contract is distinct because it *binds* rather than *informs*. An agent can rephrase a domain expert's input. An agent cannot ignore a form section or violate a principle.

Principles bind how agents think. The actor-lens contract binds the discovering-actors agent to think in terms of conditional goals and derivation chains. Forms bind what agents produce. The use case form binds the designing-usecases agent to produce specific sections in a specific order. Meta contracts bind how the system itself is organized.

## Composition

Contracts compose. An agent loads a stack of contracts through its skills, and the stack has dependencies. The modeling-foundation contract is the base of the stack — it defines what an invariant is, what a domain event is, what "conditional goal" means. The lens contracts build on the foundation — the usecase-lens says "surface invariants" and "name domain events at meaningful state transitions," phrases that are meaningless without the foundation beneath them. Forms constrain what the lens produces. Editorial standards constrain how everything reads.

Some contracts assume other contracts are present. The system works because agents load the full stack they need, and each contract in the stack can rely on the contracts beneath it.
