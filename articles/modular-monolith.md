# [May I Interest You In a Modular Monolith? by Maxi Ferreira (2025)](https://frontendatscale.com/issues/45/)

# The Rise of Micro-everything

- Microservices and micro-frontends took over because _monoliths got messy_.
- The initial speed of development eventually led to:
  - _Long build times_
  - Developer _friction_
  - _Risky_ code changes

> “All of these are signs that the well-intentioned monolith has turned into the infamous big ball of mud.”

# The Pitfall of Decomposition

- Distributed systems look like the fix, but without modularity inside the monolith first, you just _move the mess around_.

# Modular Monolith = Organization + Encapsulation

1. **Organization**

- _Structure_ your code meaningfully:
  - Folder structure
  - Logical breakdowns (e.g., domains, layers)
- Common patterns:
  - Layered Architecture
  - Clean Architecture
  - Hexagonal Architecture
  - Domain-Driven Design (DDD)

> “You might follow Clean Architecture to a tee… and still end up with a big ball of mud.”

2. **Encapsulation**

- _Prevent_ modules from reaching into each other’s guts.
- Focus on:
  - **Information Hiding**: Don’t expose internal implementation details.
  - **Guardrails**: Enforce access rules between modules.

# Tools for Guardrails

- ESLint
- Dependency Cruiser

# Modular Monolith or Microservices?

- Modularity is simple in theory, _hard in practice_.
- Modular monoliths offer:
  - Easier testing
  - Internal decoupling
  - Lower operational complexity
- But… sometimes distributed architecture is _the right fit_.

> “It is simple (organization + encapsulation = modularity), but applying it consistently requires discipline and hard work.”
