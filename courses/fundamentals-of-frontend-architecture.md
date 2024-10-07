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

### Architectural Requirements

- **Architectural requirements** are the success criteria for the architecture, ensuring it meets the needs of the business, users, and team.

- **Architectural discovery**

  - Architects must engage stakeholders, including developers, PMs, and users, to discover key architectural requirements.

- **Tools for architects**

  - Books like _Design It_ and structured activities help architects uncover and prioritize architectural requirements throughout the project lifecycle.

- **Template for requirements**

  - A structured document, like the one Maxi provides, organizes requirements by categories like business goals, constraints, and quality attributes.

### Architectural Decisions

- **Architectural decisions** define the system's structure, are hard to change, and have long-term implications, making them central to the architecture.

- **Early decisions**

  - In the initial stages of a project, most decisions are architectural since there is little code to inform design decisions.

- **Framework choice**

  - Selecting a frontend framework (e.g., Next.js) can be an architectural decision since it dictates the project's structure.

- **Version control**

  - Decisions about using a monorepo or multiple repos impact how the codebase is organized and deployed.

- **External vendors**

  - Choosing third-party services, like _Pusher_ for real-time functionality, may be necessary if the project has external dependencies.

- **Last Responsible Moment**

  - Avoid making all decisions too early. Make decisions when there is enough information to act, reducing the risk of "analysis paralysis."

- **ADRs (Architectural Decision Records)**

  - A structured way to document architectural decisions, focusing on the reasoning ("why") rather than just the decision itself.

- **Positive and negative consequences**

  - Documenting both helps provide a balanced view of the decision, making it easier for future teams to understand its impact.

- Keeping a record of architectural decisions ensures that future questions about why decisions were made can be answered with clarity.

## 3. Designing

### Entities, Modules, and Components

- **Entities**

  - Represent domain concepts (e.g., restaurant, customer) with attributes like name and address.
  - Entities exist conceptually and don’t directly translate into code without representation as models, classes, or services.
  - Entities have **attributes** (e.g., a restaurant has a name) and **operations** (e.g., adding an item to a shopping cart).

- **Modules**

  - The building blocks of an application, organizing it into parts (e.g., restaurant module, customer module).
  - While modules may correspond to entities, there’s no strict rule for a 1:1 mapping.
  - Modules are abstract but may be represented as folders, routes, or pages in a codebase.

- **Components**

  - Concrete implementations like UI views or widgets in modern frameworks like React, Svelte, or Vue.
  - Components are typically seen directly in code, representing specific UI or visual elements.

### Domain Modeling

- **Domain modeling** is a flexible tool for identifying and organizing the key entities and their attributes within a system, aligning the data model with the UI.

- **Entities and attributes**

  - Entities like restaurants, customers, and food items are identified by analyzing functional requirements and UI specifications.

- **UI-driven modeling**

  - Domain modeling helps match the data model to the needs of the user interface, reducing unnecessary complexity.

- **Naming consistency**

  - Early domain modeling ensures that entities are consistently named, avoiding confusion (e.g., using "restaurant" uniformly rather than mixing terms like "store" or "shop").

- **Longevity of entities**

  - Entities like "restaurant" or "customer" are core to the domain and often remain constant, even if the codebase or features change.

- **Aligning with data**

  - Domain models should be designed for the UI, not just based on the API or database structure, making them more useful for frontend developers.

- **Complexity management**

  - Domain modeling encapsulates data transformation logic, allowing easier handling of complex data structures from the API.

- **Collaboration tool**

  - Domain modeling facilitates discussions about responsibilities, like which entity should handle operations such as adding items to a cart.

- **Cheaper early decisions**

  - Engaging in domain modeling discussions early allows for easier adjustments before the code is implemented, avoiding costly changes later.

- **Visual representation**

  - Domain modeling can be captured as simple lists or more visually as class diagrams or entity relationship diagrams.

### Breaking Things Down

- **Level 3 of the C4 Model**

  - At this level, modules are identified as the internal building blocks of the application, based on the application's top-level concerns.

- **'Modules' instead of 'Components'**

  - Instead of using _"components"_ (which may confuse frontend developers), Maxi refers to the building blocks as modules to represent larger concerns.

- **Starting with routes**

  - By examining potential routes in the app (e.g., home, search, restaurant), developers can identify the key modules needed.

- **Module-entity relationship**

  - Not all modules correspond directly to entities—some are based on actions or features, like search, which is a module but not an entity.

- **Submodules and complexity**

  - Certain areas of the app, such as menu items, have enough complexity to become standalone modules, even if they are part of a larger route (e.g., restaurant).

- **Non-route modules**

  - Some modules, such as shopping carts, don’t have their own route but exist across multiple pages, still requiring modular implementation.

- **Shared functionality and code**

  - There will be overlap between modules, especially when modules depend on one another (e.g., menu items depend on restaurants).

- **Focus on identifying modules**

  - The primary goal is to identify and organize modules based on their functionality and role within the application.

- **Implementation phase**

  - Once modules are identified, the next step is dealing with shared functionality and dependencies during the implementation phase.
  - After identifying modules, they can be divided among developers for individual implementation, with communication between dependent modules being addressed later.

### Useful Diagrams

- **Diagrams** are essential for clarifying thoughts and communicating with the team during the design phase of software development.

  1. **Flowcharts**

  - Used to represent logic and workflows, flowcharts help break down complex conditions and scenarios, aiding in implementation.

  2. **State diagrams**

  - Especially useful when working with state management systems, state diagrams visually depict different states and transitions between them.

  3. **Class diagrams**

  - These diagrams show entities and their attributes, operations, and relationships, and are helpful even outside object-oriented programming (e.g., for representing models or types).

  4. **Sequence diagrams**

  - These are useful for illustrating the sequence of operations, particularly for asynchronous processes involving multiple actors or services.

- **Short-lived nature**

  - These diagrams are not meant for long-term documentation but serve as tools to quickly brainstorm, visualize, and iterate on design ideas.

- **Communication aid**

  - Diagrams act as a starting point for discussions with the team, helping identify potential issues or edge cases before implementation.

- **Tools for diagramming**

  - Maxi recommends using simple, low-effort tools like Mermaid, Scaledraw, or TLdraw for creating these diagrams quickly and efficiently.

### The Design Document

- **Design documents** outline solutions in detail and invite feedback from stakeholders and team members, improving the final architecture.

- **Two levels of design docs**

  - **High-level** design documents focus on overall architecture.
  - **Low-level** design docs detail specific feature implementation.

- **Standard structure**

  - The typical structure includes an _overview_, _context_, _goals_, _high-level design_, _alternatives considered_, _detailed design_ (for low-level docs), _timeline_, _risks_, and an _appendix_.

- **High-level design docs**

  - These describe the system architecture, often using container diagrams and system context diagrams, and discuss overall decisions like technology stacks.

- **Low-level design docs**

  - These focus on implementation, often including pseudocode, mock data types, and diagrams related to specific features.

- **Alternatives section**

  - It's important to document why certain frameworks or technologies were _not chosen_, providing clarity on the decision-making process.

- **Timeline and estimation**

  - While challenging to predict accurately, timelines should include the _best estimate_ for how long a project or feature will take to implement.

- **Risks and open questions**

  - This section highlights potential _risks_ and _uncertainties_ that need to be addressed during implementation.

- A concise design doc is more likely to be read and understood, increasing its effectiveness for gathering feedback.

## 4. Implementing

### Implementing Modules

- **Modules and routes**

  - While modules often correspond to routes, they don’t always map 1:1, making it important to separate them from the routing system.

- **Separate modules folder**

  - A dedicated modules folder ensures that all modules are _organized_ and _accessible_, without being mixed into the routing system.
  - Some modules, like the shopping cart, don’t have routes, so organizing them outside the routing folder avoids confusion.
  - Modules like menu items may not have top-level routes, but they still need to be treated as standalone modules, avoiding unnecessary nesting.
  - Keeping modules in a dedicated structure helps improve _navigation_ and _consistency_, making it easy to find where each piece of functionality is implemented.
  - The _app_ (Next.js) folder should only handle routing and entry points to modules, with the logic of each module being implemented separately.
  - By separating routing and modules, developers can quickly locate and modify components or features within their respective modules.
  - Hierarchy within modules: Each module can have its own internal structure, such as features and components, maintaining a clear hierarchy of functionality.
