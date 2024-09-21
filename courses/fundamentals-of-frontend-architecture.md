# Fundamentals of Frontend Architecture from [Maxi Ferreira](https://frontendatscale.com/) (2024)

## Foundations

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
