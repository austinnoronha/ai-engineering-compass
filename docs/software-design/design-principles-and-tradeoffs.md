# Design principles and trade-offs

**Status:** Recommended  
**Last reviewed:** 2026-11-26

Software design is not a search for a perfect architecture. It is a process of choosing boundaries and dependencies that fit current requirements while keeping important future changes affordable.

## Cohesion and coupling

Keep code that changes together close together. Reduce unnecessary dependencies between parts of a system. The goal is not zero coupling: useful systems depend on one another. The goal is to make those dependencies explicit, stable, and proportionate.

## Prefer the simplest design that preserves required change paths

Start with the smallest structure that meets known requirements. Add layers, interfaces, services, or distributed components when they solve a real problem such as independent scaling, ownership, isolation, or deployment.

An abstraction is useful when it makes a volatile detail replaceable or hides meaningful complexity. It is not useful merely because a design pattern exists.

## Make trade-offs explicit

For a meaningful design decision, record:

- Context and constraints.
- Options considered.
- Benefits and costs of the chosen option.
- Risks and assumptions.
- Conditions that would justify revisiting the decision.

## Common warning signs

- A generic framework built before real use cases are understood.
- Circular dependencies between modules.
- Shared mutable state with unclear ownership.
- Interfaces that mirror implementation details rather than consumer needs.
- Distributed services that add network and operational failure modes without a clear reason.

## Review questions

- Are responsibilities and ownership clear?
- Can the design be tested at useful boundaries?
- Are dependencies pointing in an intentional direction?
- Does the design solve a current requirement?
- What becomes harder because of this choice?

## References

- [Martin Fowler: Monolith First](https://martinfowler.com/bliki/MonolithFirst.html)
- [Microsoft: Cloud design patterns](https://learn.microsoft.com/azure/architecture/patterns/)
