# [Design Docs at Google by Malte Ubl (2020)](https://www.industrialempathy.com/posts/design-docs-at-google/)

- **Design docs** are informal documents used to define software designs before coding begins.
- They emphasize high-level implementation strategy and key design decisions, focusing on _trade-offs_.

- **Functions of Design Docs**

  - **Early Issue Identification**: Detect design problems when changes are still easy to make.
  - **Consensus Building**: Achieve agreement on design across teams.
  - **Cross-Cutting Concerns**: Ensure aspects like security, privacy, and observability are considered.
  - **Knowledge Sharing**: Disseminate knowledge from senior engineers throughout the organization.
  - **Design Portfolio**: Acts as a technical portfolio artifact for engineers.

- **Anatomy of a Design Doc**

  1. **Context and Scope**

     - Provides a _rough overview_ of the system being built, without being a requirements document.
     - **Goal**: Quickly bring readers up to speed with objective background facts.

  2. **Goals and Non-goals**

     - **Goals**: What the system aims to achieve.
     - **Non-goals**: Things that could reasonably be goals but are explicitly excluded.
       - Example: Deciding whether ACID compliance is a goal or not.

  3. **The Actual Design**

     - Focus on trade-offs made during the design process.
       - Suggest solutions and explain why certain ones were chosen.
     - Key Sections:
       - **System-context-diagram**: Visualizes how the new system fits into the broader technical landscape.
       - **APIs**: Summarize API designs without excessive detail.
       - **Data Storage**: Discuss how and in what form data is stored.
       - **Code/Pseudo-code**: Rarely included, except for novel algorithms.

  4. Degree of Constraint

     - **Greenfield Projects**: Broad design possibilities but need rules to narrow options.
     - **Constrained Systems**: Limited options, focus on creatively combining existing components.

  5. Alternatives Considered

     - Discuss alternative designs and their trade-offs.
     - Importance: Helps justify the chosen design by comparing it to other potential solutions.

  6. Cross-cutting Concerns

     - Design docs should address concerns like security, privacy, and logging.
     - Google projects require separate privacy and security design documents.

- **Best Practices**

  - 10-20 pages for large projects; shorter docs (1-3 pages) for smaller tasks.
    - Keep it detailed but concise to be read by busy engineers.
  - Not necessary for solutions that are straightforward or lack significant trade-offs.
  - May not be suitable for rapid prototyping or situations where iteration speed is critical.

- **Lifecycle of a Design Doc**

  1. Creation and Rapid Iteration

     - Written by authors and iterated through feedback from knowledgeable colleagues.

  2. Review

     - **Lightweight Review**: Document shared with the wider team via email or comments.
     - **Formal Review**: A dedicated meeting where the author presents the doc.
     - Incorporates organizational experience early, especially regarding cross-cutting concerns.

  3. Implementation and Iteration

     - Design docs should be updated as implementation progresses and issues arise.
     - Often, new documents (or "amendments") are created for significant changes.

  4. Maintenance and Learning

     - Design docs serve as the first reference point for engineers unfamiliar with a system.
     - Authors should reflect on their own design docs after some time to improve future decisions.
