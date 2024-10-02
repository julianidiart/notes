# [Conway's Law by Martin Fowler (2022)](https://martinfowler.com/bliki/ConwaysLaw.html)

> "Any organization that designs a system will produce a design whose structure is a copy of the organization's communication structure."

## Conway’s Law and Software Architecture

- Software systems tend to resemble the structure of the teams that create them.
- A team’s _communication_ structure influences _system design_, often in ways that are not immediately obvious.

## Human Communication and Software Coupling

- Communication is a key enabler of software coupling.
- The easier it is for developers to communicate, the more their code will be coupled, both in explicit interactions (like function calls) and implicit assumptions.

## Practical Implications

1. **Tensions in System Architecture**

   - When the architecture of a system doesn't align with the team structure, _tension_ arises.
   - Misaligned teams create _complexities_ in module interactions and overlook beneficial design alternatives due to lack of communication.

2. **Organizational Size and Structure**

   - Small teams (e.g., fewer than 20 people) communicate deeply and informally, creating monolithic systems, but larger teams must organize carefully to avoid architectural tension.

> "The first step in dealing with Conway's Law is knowing not to fight it."

## Responding to Conway’s Law

- **Accept**: Align the system architecture with the organization’s communication structure to avoid conflicts.
- **Inverse Conway Maneuver**: Deliberately restructure teams to encourage a specific desired architecture.

## Common Organizational Mistakes

- **Activity-Oriented Team Structures**: Organizing teams by software layers (e.g., front-end, back-end) can result in structures that complicate feature development.
  - Each feature requires collaboration across layers, but teams are often siloed, leading to inefficiencies and hand-offs.

## Domain-Driven Design (DDD) & Conway’s Law

- **Bounded Contexts**: _DDD_ helps define the right team and system structures by grouping teams around shared understanding and a common language.
