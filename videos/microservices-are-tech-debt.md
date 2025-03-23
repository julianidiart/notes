[# Microservices are Technical Debt by Matt Ranney (2024)](https://www.youtube.com/watch?v=LcJKxPXYudE&ab_channel=NeetCodeIO)

- **Microservices: The Good, The Bad, and The Ugly**

  - Microservices solved DoorDash’s scaling problem when their monolith became unmanageable.
  - However, they introduced _massive complexity_, requiring 500+ services just to place an order.
  - _Fan-out is a serious issue_ (one frontend request results in ~1,000 RPC calls due to excessive service separation).
  - Microservices make dependency management a nightmare, upgrading shared libraries (e.g., gRPC clients) across 500 services is extremely difficult.

- **The Socio-Technical Problem**

  - Software _resists_ change when too many people modify it simultaneously.
  - A key challenge is _coordinating large teams_, not just technical issues.
  - When failures occur in a deep RPC call graph, _everyone gets paged_, making debugging painful.
  - Engineers often blindly follow best practices (e.g., microservices for everything) without considering _trade-offs_.

- **Dogmatic Thinking in Software Engineering**

  - Many developers follow _"best practices" like a religion_ (e.g., unit tests, object-oriented programming, strict separation of services).
  - Unit test coverage is often misleading, 100% coverage means nothing without _meaningful assertions_.
  - Sometimes, not writing unit tests _saves time_ in small, well-understood codebases.
  - Engineers should _challenge norms_ and _evaluate_ whether a given practice actually helps their _specific case_.

- **The Need for a Better Architecture**

  - The industry is stuck between monoliths and microservices, with _no middle ground_.
  - A new paradigm is needed, something that balances _scalability with simplicity_.

- **Advice for Engineers**

  - **Write a lot of software**: _Experience_ is key.
  - **Don't blindly trust libraries**: Read the source code and _understand dependencies_.
  - **Avoid unnecessary complexity**: Microservices, unit tests, and design patterns should _serve a purpose_.
  - **Be critical of industry trends**: What works for a big company may not work for a small project.
  - **Think about software as a socio-technical problem**: It’s not just about writing code but about how _teams collaborate_.
