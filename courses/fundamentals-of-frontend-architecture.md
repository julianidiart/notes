# Fundamentals of Frontend Architecture by [Maxi Ferreira](https://frontendatscale.com/) (2024)

## 1. Foundations

### What is Software Architecture?

- **Defining software architecture**

  > "Architecture is definitely about the structure of the system."

  > "Architecture is the decisions that you wish you could get right early in a project."

  > "Architecture is the things that people perceive as hard to change."

  > "Architecture is about the important stuff, whatever that is."

  > "A system’s software architecture is a set of significant design decisions about how the software is organized to promote desired quality attributes."

- **Four-dimensional framework**

  - Architecture can be broken down into four key dimensions—_style_, _characteristics_, _decisions_, and _components_.

    - **Style**:

      - The architectural style (e.g., microservices, layered architecture) shapes how the system is structured.

    - **Characteristics**

      - Quality attributes are things like performance, accessibility, deployability, scalability, and so on.

      - In the same way that the class of our character determines its overall look and feel, then the style would determine the overall shape of our architecture.

  - **Decisions**

    - Architectural decisions act as structural guides for teams, helping navigate implementation complexities and making informed trade-offs.

    - We can’t really prioritize all of the characteristics at the same time. This is about choosing priorities or what are the things that we care about the most.

  - **Components**

    - Components like modules, UI elements, and functions represent the building blocks that make up the architecture.

### What is Frontend Architecture?

- **Frontend architecture definition**

  > "Frontend architecture is a set of decisions about how we organize our frontend layer to promote these higher quality attributes."

  > "Frontend architecture is about the important frontend stuff, whatever that is."

- **Frontend-backend spectrum**

  - The distinction between frontend and backend is no longer clear-cut; it’s a spectrum that includes tools crossing both areas.

- **Four-dimensional framework**

  - **Style**

    - The architectural style defines the system’s organization, while characteristics like performance or scalability shape its priorities.

  - **Characteristics**

    - Different frontend architectures focus on different quality attributes, like performance, scalability, or maintainability, depending on the team’s needs.

  - **Decisions**

    - Decisions like shared global state or mutating data in server actions can drastically change the internal structure of frontend systems.

  - **Components**

    - Logical components (e.g., hooks, views, templates) represent the building blocks that define the architecture’s structure.

- **User-facing vs. internal structure**

  - Despite appearing the same to the user, different architectures can have vastly different internal implementations and decisions.

### Software Design vs Architecture

- _Architecture_ deals with the structure of a system, while _design_ focuses on code details, such as naming conventions and patterns.

- **Architectural decisions** are _strategic_, harder to change, and typically affect multiple teams over the long term.

- **Design decisions** are more _tactical_, easier to change, and often involve immediate team-level concerns.

- Decisions exist on a spectrum between architecture and design, depending on how hard they are to change and their long-term impact.

- The more a decision falls on the architectural side, the more time and effort should be spent analyzing it.

- **Avoiding underestimation**: Treating architectural decisions too lightly can result in long-term issues that are hard to resolve later.

- **Avoiding overestimation**: Spending too much time on trivial design decisions can waste valuable resources and slow down progress.

- Architectural decisions require broader team alignment and documentation, whereas design choices can be made more autonomously.

### The Frontend Architect Role

- **Modern architects' role**

  - Architects are embedded in development teams, writing and reviewing code while making architectural decisions

  - The outdated model of architects working in isolation no longer applies; architects now collaborate closely with their teams.

- **Setting technical direction**

  - Architects create and maintain a technical vision and strategy, ensuring team alignment.

- **Architectural thinking**

  - Architects analyze trade-offs, translate business drivers into requirements, and balance technical breadth and depth.

- **Pyramid of knowledge**

  - Architects need expertise (depth) in specific areas, while also having a broad understanding (breadth) of technologies outside their usual scope.

  - Frontend architects must go beyond their comfort zone, learning about servers, databases, and backend technologies to make informed decisions.

- **Glue work**

  - Architects are responsible for invisible but essential tasks like documentation, mentorship, and facilitating communication within the team.

- **No formal title required**

  - Even if "frontend architect" isn't an official title, anyone can contribute to architecture by thinking strategically and improving systems.

  - Architecture is not just the architect’s job; every team member shares the responsibility of building maintainable and robust systems.

- **Mentorship**

  - Architects help grow the team’s knowledge by sharing insights and encouraging best practices around architecture and design.

## 2. Understanding

### The C4 Model

- The **C4 Model** is a set of diagrams that represent software architecture at different levels of detail, from system context to individual code structures.

  - Simon Brown developed the C4 Model, and his work and resources are referenced throughout the course for deeper understanding.

- **C4 Model Levels**

  1. **System context diagram (Level 1)**: The highest level, showing the software system and its interaction with users and external systems, useful for non-technical stakeholders.

  2. **Container diagram (Level 2)**: Zooms into a system to show applications, APIs, and databases, still accessible to non-technical audiences but with more technical detail.

  3. **Component diagram (Level 3)**: Focuses on the key components within a container, more useful for developers and architects; frequent updates may be necessary.

  4. **Code diagram (Level 4)**: Represents detailed code-level structures like class diagrams or entity relationships; more useful for developers during implementation.

- **Documentation**

  - The higher levels (system context and container diagrams) are useful for documentation, while lower-level diagrams (component and code) need frequent updates due to changing code.

### Architectural Drivers

- **Architectural drivers** are the influencers that shape architecture, determining the requirements and guiding architectural decisions.

- **Business goals**

  - The most critical drivers, including revenue growth, cost reduction, and improving efficiency, serve as the main reasons for building the system.

- **Quality attributes**

  - Performance, scalability, maintainability, and other "ilities" determine the non-functional qualities the architecture must support.

- **Constraints**

  - Non-negotiable factors, such as budget, deadlines (business constraints) or specific technologies (technical constraints), limit architectural choices.

- **Functional requirements**

  - These define what the system can do, such as search functionality or shopping carts, with a focus on the architecturally significant ones.

- **Team experience**

  - The knowledge and skills of the team, including the architect's breadth of expertise, influence the architectural decisions made.

- **Technology trends**

  - Staying aware of new trends while favoring stable, reliable technologies helps architects evaluate trade-offs in their decisions.
  - While stability is preferred, architects must stay informed about emerging trends to assess potential trade-offs.

- Architectural drivers translate into specific requirements that define the architecture’s success and influence its design.
- Different architectural drivers result in different architectures for the same application, as seen in prior discussions of frontend architecture.
- These decisions, shaped by the drivers, fall toward the strategic, hard-to-change side of the spectrum and impact long-term system outcomes.
