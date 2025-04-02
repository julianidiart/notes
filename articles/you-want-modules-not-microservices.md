# [You Want Modules, Not Microservices by Ted Neward (2023)](https://blogs.newardassociates.com/blog/2023/you-want-modules-not-microservices.html)

## Common Claims About Microservices:

> At the heart of microservices, we're told we'll find... Lots of Good Things (TM)!

1. **Scalability**: Independently deployable components.
2. **Focus**: Developers concentrate on business logic.
3. **Availability**: Always-on backend services.
4. **Simplicity**: Easier enterprise app development.
5. **Responsiveness**: Scales with transaction loads.
6. **Reliability**: Redundancy and fault tolerance.

> ⚠️ These same claims were also made about:
>
> - EJBs (20 years ago)
> - Tuxedo (40+ years ago)

- The same benefits are _recycled_ through different generations of technology.

### Breaking Down the "Top 10 Microservices Benefits"

- Each microservices benefit by comparing it with historical precedents:

1. **Big Data Best Practices**: Microservices resemble _Unix's pipes-and-filters architecture_ from the 1970s.
2. **Ease of Building & Higher Code Quality**: Aligns with _Unix philosophy_: small, composable programs.
3. **Higher Code Quality**: Idem.
4. **Simplified Team Coordination**: Claims SOA is "heavyweight", but microservices can still use heavy protocols (like gRPC or SOAP). _Nothing prevents microservices from being "heavy"_.
5. **Real-Time Processing**: Event-driven architecture is _not exclusive to microservices_.
6. **Rapid Growth**: Reuse and repurposing of data—_not a new idea_ (Crystal Reports, OOP, libraries).
7. **More Outputs**: Idem.
8. **Better Lifecycle Management**: Often just _buzzwords_ without real depth.
9. **Scalability**: _Every architectural trend has promised this_—from EJB to mainframes.
10. **Tool Support**: Tools always emerge after _hype gains traction_ (e.g., UML, CASE tools).

## What Are We Really Talking About?

> At the heart of microservices, we find... modules.

### The Core Concept: Modularity

- Small, independently built and deployed units.
- Known for decades: DLLs, JARs, Packages, Assemblies.
- Classic definition from David Parnas (1971):
  > "Each task forms a separate, distinct program module..."

### Modular design supports:

- Independent development & testing
- Clear boundaries and interfaces
- Easier maintenance & scalabil

## What Microservices Actually Solved

> At the heart of microservices, we often find... the Fallacies of Distributed Computing.

### Organizational Clarity

- Microservices helped enable cross-functional, autonomous teams.
- Inspired by companies like Amazon, where teams:
  - Owned their full stack
  - Had end-to-end responsibility (infra, QA, DB, UX, etc.)
  - Worked independently to deliver value

### The Trade-offs

- Requires more versatile developers ("Full Stack")
- Hiring is harder, but teams move faster
- On-call support, deployment, and ownership increases for developers

### The Fallacies of Distributed Computing:

- First identified by Peter Deutsch and others in the 1980s/90s.
- Problems like:
  - Latency
  - Network reliability
  - Bandwidth constraints
- Microservices bring these issues front and center, especially when communication crosses network boundaries.

> "Distributed systems are 5–7 orders of magnitude slower than in-memory module calls."

## What We Really Need

> At the heart of microservices, we need... to start rethinking what we really need.

### Ask Better Questions

- Instead of rushing into microservices, ask:
  - Do you need independent deployment or modularity?
  - What dependencies are slowing your teams?
  - Can teams be reorganized for autonomy without needing microservices?

### Focus on:

- Solid API design
- Clear boundaries
- Team autonomy
- Reuse of existing technology (servlets, .NET, Ruby, Python, etc.)
