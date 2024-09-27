# Clean Architecture by Robert C. Martin (2018)

## Part I: Introduction

### Chapter 1: What Is Design and Architecture?

- **Confusion of Terms**:

  - Historically, there has been **confusion** between the terms _design_ and _architecture_.
    - There is **no difference** between the two terms.
    - Common understanding separates _architecture_ (high-level decisions) from _design_ (low-level details).

- **Unified Concept**:

  - _Architecture_ and _design_ form a **continuous fabric**.
  - High-level and low-level decisions are both part of the same **whole** system.
  - No **clear line** divides design and architecture; they are interconnected and interdependent.
  - Just as a house's design includes both high-level aspects (rooms, layout) and low-level details (outlets, switches), **software** architecture includes both **overall structure** and **fine details**.
    - Example: A home design involves decisions about **space layout** (architecture) and **specific elements** like electrical wiring (design).

- **The Goal of Architecture**:

  - The **primary goal** of software architecture is to minimize the **human resources** required to build and maintain the system.
  - A well-designed architecture results in a **lower effort** over the system's lifetime, making it easier to add new features and fix issues.
  - Architecture should **maximize productivity** by making the system flexible and easy to change.

- **Characteristics of Good Architecture**:

  - _Good software architecture_ leads to a **minimal need** for large teams, extensive documentation, or complex tools.
  - **Changes** become simple and rapid, with minimal defects.
  - Systems with poor architecture tend to slow down and become **difficult to maintain** over time.

- **Real-World Implications**:

  - Many developers experience **bad design** that leads to complex, fragile systems.
  - A poorly designed system results in **high coupling**, where small changes can introduce **significant risks** and delays.
  - The **morale of teams** and **success of businesses** can suffer due to poor architectural choices.

- **The Utopian Vision**:

  - The ideal system operates with **minimal intervention** from developers and remains **adaptable** over time.
  - When software architecture is **done right**, it enables **longevity** and reduces the number of required developers.

### Chapter 2: A Tale of Two Values

- **Two Core Values of Software**:

  - Every software system provides two distinct **values** to stakeholders: **behavior** and **structure**.
  - Developers are responsible for maintaining the **balance** between these two values.

- **Behavior**:

  - Refers to what the software **does** (how it behaves when running and interacting with users).
  - Programmers are hired to ensure the system behaves in ways that make or save **money** for stakeholders.
  - Involves creating a **functional specification** that dictates how the system should behave based on stakeholder requirements.
  - Many developers see this as their **entire job**: to make the machine meet these specifications and to **debug** issues when the system misbehaves.

- **Structure (Architecture)**:

  - Architecture pertains to the software’s **ability to change** (its "softness)."
  - Software must be **easy to change**. When stakeholders change their minds, the system should adapt with minimal effort.
  - **Ease of change** is fundamental to fulfilling software's purpose; otherwise, it would be considered "hardware."
  - Poor architecture leads to **hard-to-change** systems, significantly increasing the effort required for even minor adjustments.

- **Importance of Both Values**:

  - A software system must deliver **both** behavior and maintain a good structure, or it will eventually lose its value.
  - If developers focus too much on behavior without considering architecture, the system may become **fragile** and difficult to maintain or evolve.
  - **Balance** is essential: a system needs to **work well** now (behavior) and be **adaptable** to future changes (structure).

- **Greater Value**:

  - Although both values are important, **structure** tends to hold more significance in the long term.
  - Systems with a well-maintained structure are more **adaptable**, enabling long-term viability.
  - Behavior can be adjusted relatively easily if the system’s architecture is robust, but fixing poor architecture requires significant effort.

- **Eisenhower’s Matrix**:

  - This matrix of **urgency vs. importance** helps illustrate the balance between the two values.
  - **Behavior** represents urgent needs (getting the system to work now), while **architecture** embodies important, long-term needs.
  - Developers often prioritize **urgent** tasks (behavior) over **important** ones (structure), leading to **technical debt** and long-term inefficiency.

- **Fight for Architecture**:

  - Good developers must **advocate** for structure, ensuring that the architecture doesn’t degrade over time.
  - Sacrificing architecture for short-term gains in behavior is a **common mistake**, but it compromises the system’s future adaptability and maintainability.

> “The only way to go fast, is to go well.”

## Part II: Starting with the Bricks: Programming Paradigms

### Chapter 3: Paradigm Overview

- **Structured Programming**:

  - Originated with **Edsger Wybe Dijkstra** in 1968.
  - It involves **replacing unrestrained jumps** (_goto_ statements) with structured control flow mechanisms like **if/then/else** and **do/while/until** loops.
  - This paradigm aims to **impose discipline** on **direct transfer of control**, promoting code clarity and reducing errors.

- **Object-Oriented Programming (OOP)**:

  - Developed by **Ole Johan Dahl** and **Kristen Nygaard** in 1966.
  - Based on the idea of **moving local variables and functions** (from a function call stack frame in **ALGOL**) to a heap, leading to **classes** and **instance variables**.
  - OOP introduces the concept of **polymorphism** through the **disciplined use of function pointers**, evolving into the creation of **methods** in classes.
  - This paradigm disciplines **indirect transfer of control** through object methods.

- **Functional Programming**:

  - The earliest paradigm, developed by **Alonzo Church** in 1936 via **λ-calculus**.
  - The **LISP** language, invented by **John McCarthy** in 1958, is based on λ-calculus and serves as a foundation for functional programming.
  - **Immutability** is central to functional programming, emphasizing **no assignment statements** and restricted changes to the value of a variable.
  - Functional programming imposes **discipline on variable assignments**, distinguishing it from imperative programming models.

- **Food for Thought**:

  - Each of these paradigms **removes certain capabilities** from programmers, enforcing discipline in how they structure and control the flow of a program.
  - The key takeaway is that paradigms focus more on **what not to do**, shaping how programmers write software by limiting unrestricted behaviors like direct jumps, mutable state, or unsafe function pointers.
  - The three programming paradigms **structured**, **OOP**, and **functional programming** likely form the **only three paradigms** of their kind, as no fundamentally new paradigms have emerged since their creation.

### Chapter 4: Structured Programming

- **Edsger W. Dijkstra**:

  - Born in **Rotterdam in 1930**, he was the first programmer employed at the Mathematical Center of Amsterdam.
  - Known for his early recognition of the **intellectual challenge** posed by programming and for **pioneering structured programming**.

- **Proof and Falsifiability**:

  - Dijkstra applied **mathematical proof** techniques to programming, recognizing that programming involves more details than humans can manage without assistance.
  - His vision included constructing a **Euclidean hierarchy** of provable structures, allowing programs to be mathematically proven correct.
  - Dijkstra found that **goto statements** hinder the recursive decomposition necessary for proving program correctness, leading to the development of **structured programming**.

- **A Harmful Proclamation**:

  - In 1968, Dijkstra published his famous letter, _"Go To Statement Considered Harmful"_, where he argued against the use of **goto** statements.
  - His position sparked a decade-long debate, but **modern programming languages** have largely abandoned the goto statement as a result of this battle.
  - **Modern languages** force structured programming by limiting **unrestricted transfer of control** (like goto), allowing programmers to maintain discipline in code flow.

- **Functional Decomposition**:

  - Structured programming allows for **functional decomposition**, where complex problems are broken down into **high-level functions**, which are then further decomposed into **lower-level** functions.
  - By following **structured decomposition**, large systems can be broken into small, **provable units**, ensuring **clarity and maintainability**.

- **No Formal Proofs**:

  - Despite the initial hope for **formal mathematical proofs** of software correctness, the practical challenges led to a decline in this approach.
  - **Programmers** found formal proofs too laborious and complex for everyday use, leading to a focus on **scientific methods** for validating software correctness.

- **Science to the Rescue**:

  - The **scientific method** provided a more pragmatic approach to software correctness, focusing on **falsifiability**.
  - Software correctness, like scientific theories, is never proven beyond doubt but is deemed **correct enough** when sufficient tests fail to falsify it.

- **Tests**:

  - **Testing** demonstrates the presence of bugs, not their absence. Therefore, tests can show that a program is incorrect, but they cannot **prove it correct**.
  - Structured programming encourages writing **provable functions** that can be tested and evaluated for correctness.
  - If tests fail to prove a function incorrect, it is deemed **correct enough** for practical use.

> “Dijkstra once said, “Testing shows the presence, not the absence, of bugs.” In other words, a program can be proven incorrect by a test, but it cannot be proven correct. All that tests can do, after sufficient testing effort, is allow us to deem a program to be correct enough for our purposes.”

### Chapter 5: Object-Oriented Programming

- Several explanations attempt to define OO:

  - **"The combination of data and function"**: This definition implies that calling a method on an object (`o.f()`) is different from passing a function argument (`f(o)`), which is misleading.
  - **"A way to model the real world"**: This is vague and doesn’t clarify what OO truly represents.
  - Some claim that **encapsulation**, **inheritance**, and **polymorphism** are the key pillars of OO. Each is analyzed below:

- **Encapsulation**

  - OO languages enable easy and effective **encapsulation** of data and functions. This allows a clear boundary around a cohesive set of data and functions, with hidden data and selectively available functions.
  - Example: A class with **private** data members and **public** member functions.
  - **Encapsulation** is not unique to OO. In fact, **C** had perfect encapsulation:
    - By forward-declaring data structures and functions in header files and implementing them in separate implementation files, users had no access to internal details.
    - With **OO languages like C++**, perfect encapsulation was compromised due to the need to declare member variables in the class header.

- **Inheritance**

  - **Inheritance** in OO allows a class to derive properties and methods from another class.
  - Example: In **C**, inheritance could be simulated using function pointers and manual redeclaration of variables within a larger scope.
    - However, inheritance existed in some form even before OO was formally introduced, but OO languages made this mechanism much more convenient.

- **Polymorphism**

  - **Polymorphism** refers to the ability to call the same method on different objects, allowing for behavior specific to each object.
  - Pre-OO, C achieved polymorphism using function pointers and standardized function signatures (e.g., for IO operations like `open`, `close`, `read`, `write`).
  - OO languages formalized polymorphism, allowing method calls to be dynamically dispatched based on the object's type.
  - **Polymorphism** allows for the creation of _plugin architectures_, where new features or implementations can be introduced without changing the core code. This ability to decouple components is one of the most powerful features of OOP from an architectural perspective.

- **Dependency Inversion**

  - One of the most important benefits of OOP is _Dependency Inversion_, where high-level policy modules do not depend on low-level detail modules. Instead, both depend on abstractions. This inversion of control is key to creating flexible, maintainable architectures.

### Chapter 6: Functional Programming

- **Functional Programming** is a paradigm based on **immutability** and avoiding side effects in functions.
- It traces its roots back to **λ-calculus**, developed by **Alonzo Church** in the 1930s.
- **John McCarthy** implemented the ideas of λ-calculus into the **LISP** programming language in 1958.

- **Immutability**

  - **Immutability** is central to functional programming.
    - A functional program has **no variable assignment**, meaning values don’t change once they are set.
    - This helps avoid **race conditions**, **concurrent update problems**, and **deadlocks**, making concurrent programming more straightforward.

- **Segregation of Mutability**

  - It is sometimes necessary to introduce **mutable state** in certain parts of a program.
    - The solution is to **segregate** mutable and immutable components.
    - **Transactional memory** can help manage mutable variables safely.
    - For example, in **Clojure**, you can use **atoms** and a **compare-and-swap** mechanism to ensure safe updates:
      ```clojure
      (def counter (atom 0))
      (swap! counter inc)
      ```

- **Event Sourcing**

  - In **event sourcing**, instead of saving **state** (e.g., balances or statuses), we store a **log of events**.
    - State is reconstructed by replaying the sequence of events.
    - This minimizes mutable state and avoids **concurrent update issues**.
    - While this approach seems resource-intensive, modern computing power makes it practical in many scenarios.

## Part III: Design Principles

### Chapter 7: SRP - The Single Responsibility Principle

- **Definition of SRP**

  - SRP states: _"A module should have one, and only one, reason to change."_
  - A more precise version: **A module should be responsible to one actor**.
    - **Actor** refers to a group of people or a stakeholder that would require a change in the system.

- **Common Misunderstanding**

  - SRP is often misunderstood as the principle that every module should do only one thing, which is not accurate.
  - This confusion arises because of SRP's name, but it doesn't mean that every function or class should be responsible for just one task.

- **Explanation**

  - The idea of SRP is to prevent **coupling** different actors within the same module.
  - Example: An **Employee** class with `calculatePay()`, `reportHours()`, and `save()` methods violates SRP.
    - `calculatePay()` belongs to the accounting department (CFO).
    - `reportHours()` belongs to HR (COO).
    - `save()` relates to the database administrators (CTO).
  - By combining these responsibilities, any change by one actor can unintentionally affect the needs of other actors.

- **Symptoms of SRP Violation**

  1. **Accidental Duplication**

     - Duplication can occur when different actors want to modify the same module, leading to unintended consequences.
     - Example: A shared function like `regularHours()` used by both `calculatePay()` and `reportHours()`. A change by one team might break functionality for the other.

  2. **Merges**

     - When code for different actors exists in the same module, it can cause merge conflicts during updates, complicating collaboration.

- **Solutions**

  - **Separate modules** based on their responsibilities to different actors. Each module should only be responsible to **one actor**.
  - Keep code **localized** to avoid unintentional side effects on other parts of the system.
  - Use design patterns like **facades** to provide a unified interface without violating SRP.

### Chapter 8: OCP - The Open-Closed Principle

- **Definition of OCP**

  - The Open-Closed Principle (OCP), coined in 1988 by **Bertrand Meyer**, states:
    - "A software artifact should be **open for extension** but **closed for modification**."
  - This means that software behavior should be **extendible** without modifying the existing codebase.

- **Core Idea**

  - The fundamental reason for studying software architecture is to minimize the impact of changes.
  - If small extensions to requirements cause massive changes, the software’s architecture has failed.

- **Application in Design**

  - Many students of software design understand OCP as it relates to the design of **classes** and **modules**.
    - However, OCP becomes even more critical at the level of **architectural components**.

- **A Thought Experiment**

  - Imagine a system displaying a **financial summary** on a web page where:
    - Data is scrollable, and **negative numbers** are rendered in red.
  - Stakeholders request that this information also be presented as a **printable report**:
    - Paginated, with page headers/footers, and negative numbers shown with parentheses.
  - Some new code will be required for this new format, but the goal is to minimize changes to existing code.
  - A good architecture would reduce the code change to almost zero by applying principles like:
    - **Single Responsibility Principle (SRP)**: Separate concerns like data formatting for web and print.
    - **Dependency Inversion Principle (DIP)**: Organize dependencies to protect parts of the system from changes.

- **Directional Control**

  - **Dependencies** between components should flow in the **correct direction**.
  - Example: A **FinancialDataGateway** interface inverts the dependency, allowing the `Interactor` component to be isolated from changes in the database.

- **Information Hiding**:

  - Protect controllers from unnecessary knowledge about interactors to prevent **transitive dependencies**.

### Chapter 9: Liskov Substitution Principle (LSP)

- **Liskov Substitution Principle (LSP)** was introduced by Barbara Liskov in 1988. It states:

  - If `o1` is an object of type `S`, and `o2` is an object of type `T`, then for all programs `P` that use `T`, the behavior of `P` remains unchanged when `o1` is substituted for `o2`.
  - This implies that **subtypes** must be substitutable for their **supertypes** without altering the behavior of the program.

- **The Square/Rectangle Problem**

- A famous violation of LSP involves **Square** and **Rectangle**:
  - **Rectangle** has independently mutable width and height, while **Square** requires them to change together.
  - If a program expects a **Rectangle**, substituting a **Square** causes the program to fail, violating LSP.
  - Code example:
    ```java
    Rectangle r = ...;
    r.setW(5);
    r.setH(2);
    assert(r.area() == 10);  // Fails if r is a Square
    ```
- To avoid such LSP violations, the program would require additional checks (e.g., an if statement) to identify whether it is dealing with a **Square**.

- **LSP and Architecture**

  - LSP evolved from a rule of **inheritance** into a broader principle that applies to **interfaces** and **implementations**.
    - Applies in scenarios where there are users depending on well-defined **interfaces**.
  - **Substitutability** ensures that different implementations of interfaces do not break the program’s behavior.

### Chapter 10: ISP - The Interface Segregation Principle

- **Interface Segregation Principle (ISP)** advises that **no client** should be forced to depend on interfaces they do not use.

  - Clients should not be burdened with methods they don't need, as it can lead to unnecessary coupling.

- **Avoiding Large Interfaces**

  - Imagine a class **OPS** with multiple operations like **op1**, **op2**, and **op3**.
    - **User1** only uses **op1**, **User2** uses **op2**, and **User3** uses **op3**.
    - Even if **User1** does not care about **op2** or **op3**, they are still indirectly dependent on them if they rely on the entire **OPS** interface.
    - Changes in **op2** or **op3** will force **User1** to recompile and redeploy, even if **op1** remains unchanged.
  - This issue can be solved by **segregating operations into smaller interfaces**:
    - **op1** goes into **U1Ops**, **op2** into **U2Ops**, and **op3** into **U3Ops**.
    - Now, each user depends only on the operations they use, reducing unnecessary dependencies.

- **Statically Typed vs. Dynamically Typed Languages**

  - In **statically typed languages** (e.g., Java), programmers are forced to declare and import interfaces, creating **source code dependencies**.
    - This leads to recompilation and redeployment whenever a change occurs in any part of the interface, even if the client is not using those changes.
  - In **dynamically typed languages** (e.g., Ruby, Python), interfaces are inferred at runtime, leading to **fewer source code dependencies**.
    - This results in more flexible and loosely coupled systems.
    - However, this does not mean ISP is irrelevant in dynamic languages—it still serves as an important architectural consideration.

- **ISP and Architecture**

  - ISP goes beyond just source code dependencies; it also applies at the architectural level.
    - It is generally harmful to depend on modules containing more than what is necessary.
    - Example: If a system depends on a framework bound to a specific database, even if it doesn't use all of the database’s features, changes in the unused features can still affect the system.

### Chapter 11: DIP - The Dependency Inversion Principle

- **Dependency Inversion Principle (DIP)** states that high-level modules should not depend on low-level modules. Both should depend on abstractions.

  - In practical terms, source code dependencies should refer only to **abstract interfaces** or classes, not concrete implementations.
  - The goal is to create systems that are **flexible**, reducing dependency on changing components.

- **Stable Abstractions**

  - **Abstractions** are generally more stable than **concretions**.
    - Changes to an abstract interface often result in changes to all concrete classes that implement it.
    - However, changes to a concrete implementation do not usually require changes to the interface.
    - This means that **interfaces** are inherently **less volatile** and can act as a **stabilizing factor** in system design.

- **Volatile Elements**

  - DIP focuses on **avoiding dependencies on volatile concrete components** that are under active development and frequently change.
    - Concrete implementations are subject to frequent modifications, which can ripple through the system if other components depend directly on them.
    - Abstractions, however, provide **a layer of insulation**, allowing the system to remain more stable and flexible.

- **Factories and Concrete Components**

  - **Factories** are a common pattern used to adhere to DIP:
    - They provide a way to instantiate objects without relying on concrete class dependencies.
    - For example, an abstract **Factory** interface can define methods for creating objects, while the **concrete implementation** of that factory provides the specific instantiation logic.
    - This way, the **high-level application** can depend on the abstract factory without knowing the details of the concrete classes.

- **Concrete Component Example**

  - A typical violation of DIP can be seen in systems where **high-level components** depend on concrete classes.
    - An example could involve a **ServiceFactoryImpl** class that creates services. If the application relies directly on this implementation, it would break DIP.
    - Instead, the application should depend on an **abstract ServiceFactory** interface, with the instantiation of the concrete **ServiceFactoryImpl** being handled by the factory.

- **Application to System Design**

  - DIP is not only about object instantiation but also about the **direction of dependencies** in system architecture.
    - Systems that adhere to DIP are organized such that **dependencies point toward abstractions**, not concretions.
    - This often results in a clear separation between **high-level policies** and **low-level details**.

## Part IV: Component Principles

### Chapter 12: Components

- **Components**: Fundamental units of **deployment** in software systems.

  - Examples:
    - In **Java**: Jar files
    - In **Ruby**: Gem files
    - In **.NET**: DLLs
    - In **compiled languages**: Aggregations of binary files
    - In **interpreted languages**: Aggregations of source files
  - **Key Characteristic**: Components are independently deployable and, hence, **independently developable**.

- **A Brief History of Components**

  - Early development involved programmers controlling memory layout.
  - **Origin statements**: Used to declare where the program would be loaded in memory.
  - Programming once required explicit knowledge of memory addresses, which is largely obsolete today.

- **Relocatability**

  - Modern software components need to be **relocatable**, meaning they don't depend on being loaded at a specific memory address.
  - **Relocatable Binaries**:
    - In older systems, binaries had fixed addresses.
    - Modern systems leverage relocatable binaries that can work at different memory addresses.

- **Linkers**

  - **Linkers** are tools that combine multiple components or files into a **single executable** or library.
    - Can **aggregate** components (e.g., into a .war file or DLLs).
    - Can **link** components either at **compile time** or **runtime** (e.g., dynamic linking).

### Chapter 13: Component Cohesion

- Component cohesion determines **which classes belong in which components**.
- There are three key principles of component cohesion:

  - **REP**: _Reuse/Release Equivalence Principle_
  - **CCP**: _Common Closure Principle_
  - **CRP**: _Common Reuse Principle_

- **The Reuse/Release Equivalence Principle (REP)**

  - **Definition**: _The granule of reuse is the granule of release._
  - **Purpose**: Ensures that components meant for reuse are tracked through a release process.
  - **Key Points**:
    - Components cannot be reused effectively unless they are managed through a **release process**.
    - Components must share an **overarching purpose** and be **releasable together**.
    - Developers should be informed about release schedules and changes.

- **The Common Closure Principle (CCP)**

  - **Definition**: _Gather into components those classes that change for the same reasons and at the same times._
  - **Key Points**:
    - Ensures **related changes** are confined to a single component to minimize the need for wide-scale changes.
    - Changes to one component should not force changes to others, reducing the need for **revalidation** and **redeployment**.
    - **Relation to OCP (Open/Closed Principle)**:
      - CCP ensures that components remain closed to modification for expected changes but open for extension, aligning with the **Open/Closed Principle**.

- **The Common Reuse Principle (CRP)**

  - **Definition**: _Don’t force users of a component to depend on things they don’t need._
  - **Key Points**:
    - Classes that are often reused together should be placed in the same component.
    - Ensures that **dependencies** are meaningful, avoiding the inclusion of classes not relevant to the component’s users.
    - Avoids unnecessary **rebuilds and redeployments** caused by irrelevant changes in the used component.
    - Aligns with **ISP (Interface Segregation Principle)**: Just as ISP advises not to depend on methods not used, CRP advises not to depend on classes not needed.

- **The Tension Diagram for Component Cohesion**

  - The three principles of cohesion can conflict:
    - **REP** and **CCP** are **inclusive** principles that suggest making components larger.
    - **CRP** is **exclusive**, aiming to make components smaller.
  - **Tension Diagram**:
    - Architects must balance these principles to suit **current project needs**, knowing that concerns will change over time.
    - Example:
      - Early in a project, **CCP** may take precedence over **REP**, as **developability** is prioritized over reuse.
      - Over time, as other projects begin to reuse components, the project will shift to prioritize **REP** and **CRP**.

### Chapter 14: Component Coupling

- The goal is to maintain a balance between **flexibility** and **stability** to ensure ease of development and system evolution.
- **Component coupling** deals with relationships between components and the impact of these relationships on system design, maintenance, and buildability.

- **The Acyclic Dependencies Principle (ADP)**

  - **ADP** states that **no cycles** should exist in the **component dependency graph**.
    - Cycles create dependency-related issues, making systems hard to understand and modify.
    - Example: _"The morning after syndrome"_ refers to how changes by one team member can break others' work when there is a dependency cycle.
  - **Dependency cycles** cause severe issues during integration, especially in large projects.
    - Solution: Partition the system into **releasable components**, where each developer or team owns a component.

- **The Stable Dependencies Principle (SDP)**

  - **SDP** states that components should **depend in the direction of stability**.
    - Stable components are hard to change because they have many dependents, while unstable components are easy to change but should have fewer dependents.
    - **Stability** refers to how resistant a component is to change, not its frequency of change.
    - Components that are expected to change should not be depended on by components that are difficult to change.
  - Measuring **stability** involves counting the number of **incoming** and **outgoing dependencies**.
    - Formula: **I** (instability) = **outgoing dependencies / (incoming + outgoing dependencies)**.
      - If **I = 0**, the component is very stable (no outgoing dependencies); if **I = 1**, the component is very unstable.

- **The Stable Abstractions Principle (SAP)**

  - **SAP** states that **stable components** should also be **abstract**.
    - This ensures that the component's **stability** does not prevent it from being extended.
    - Components that are **unstable** should be **concrete**, allowing easy modification.
    - **Abstract components** (interfaces, abstract classes) are more stable because they can be extended without modification.
  - **SAP** and **SDP** together form a key relationship for managing **dependencies** in software systems.
    - This principle resembles **DIP** (Dependency Inversion Principle), applied to components instead of classes.

- **Managing Dependency Structures**

  - **Component dependency graphs** are used to map the **buildability** and **maintainability** of the application.
  - The structure of these dependency graphs should be designed to **localize volatility**.
    - Frequent changes in one part of the system should not cause widespread impact across other components.
  - For example, cosmetic changes to a **GUI** should not affect **business rules** or **high-level policies**.
  - Over time, as a project grows, **ADP** is applied to eliminate dependency cycles, ensuring the system remains manageable.

## Part V: Architecture

### Chapter 15: What Is Architecture?

- **Architecture** refers to the shape of a system, its structure, and the relationships between its components.
- It involves _decisions_ about the **division** of a system into **components**, the arrangement of those components, and how they interact.
- **Architecture's purpose**: To facilitate the **development**, **deployment**, **operation**, and **maintenance** of a software system.

- **Role of the Architect**

  - A **software architect** is still a **programmer** and should continue engaging in programming tasks to understand the consequences of architectural decisions.
  - Good architects guide their team towards a design that maximizes **productivity** and **maintainability** while leaving many **decisions** open for as long as possible.

- **Key Objectives of Architecture:**

  1. **Development**:

  - Architecture supports **team development**, ensuring that teams work independently without causing conflicts.
  - Components should be well-partitioned and isolated to facilitate **independent development** by different teams.

  2. **Deployment**:

  - A good architecture ensures **immediate deployability** after build processes, without needing numerous configurations or manual interventions.

  3. **Operation**:

  - Architecture must support the _system's operational requirements_, like handling specific throughput or response times.
  - The architecture should be flexible enough to support transitions, such as moving from a monolith to a microservices architecture, depending on operational needs.

  4. **Maintenance**:

  - A good architecture makes systems easy to maintain, with changes requiring minimal effort and risk.

- **Strategy of Keeping Options Open**

  - Architects aim to leave decisions about frameworks, databases, and other details **open for as long as possible**.
  - The longer decisions are deferred, the more **flexibility** the architecture provides to adapt to evolving requirements and environments.

- **Device Independence and Flexibility**

  - Architecture should support **device independence**, meaning the system should not be tightly coupled to specific hardware or device types.
  - This allows the system to evolve, shift platforms, or adapt to new technologies without major refactoring.

### Chapter 16: Independence

- **Independence** in software architecture is a critical principle to ensure a system's long-term sustainability and flexibility.
- A good architecture supports:

  - **Use Cases**: Ensuring the system fulfills the primary intent.
  - **Operation**: Allowing systems to handle expected loads and operations efficiently.
  - **Development**: Facilitating ease of changes and additions.
  - **Deployment**: Enabling easy release and distribution of the system.

- **Use Cases**

  - The architecture must **support the intent** of the system.
  - Example: A shopping cart system’s architecture should visibly express its core functionality.
    - **Behavioral clarity** is essential: the system's behavior should be evident in its structure.
    - Key use cases should be visible at the top level, named clearly and prominently.
    - Avoid the need to "hunt" for behaviors—behaviors must be first-class elements.

- **Operation**

  - Architecture plays a substantial role in **system performance**.
    - For example, a system requiring **high throughput** should be structured accordingly (e.g., **parallel services** across servers, threads sharing a process, or even simple monoliths depending on needs).
    - Response times, processing elements, and system scalability depend on how the architecture is designed to **support operational needs**.

- **Development**

  - A system should support **easy development**, ensuring that components can be developed **independently**.
    - Independent development allows teams to work without stepping on each other’s toes, even in complex environments.
    - Development must be agile, with components that are decoupled and can be independently built and tested.

- **Deployment**

  - Architecture must ensure **independent deployability**.
    - The ease of deployment is determined by how decoupled and self-sufficient the components are.
    - Deployment boundaries may include **monoliths** or more advanced **deployment components** like dynamically linked libraries (DLLs) or other shared libraries.

- **Leaving Options Open**

  - A well-designed architecture **delays decisions** about specific details as long as possible.
    - This allows for _flexibility_ and _adaptation_ to future changes without significant rework.
    - The **decoupling of decisions** from the architecture keeps options open for future evolution.

- **Decoupling Layers**

  - **Horizontal decoupling**: The system is divided into distinct layers (UI, application-specific rules, application-independent business rules, database, etc.).
  - **Vertical decoupling**: Use cases, being vertical slices of the system, cut through the horizontal layers. Each use case must be decoupled from others (e.g., the add-order use case is independent from the delete-order use case).

- **Decoupling Use Cases**

  - Use cases change at different rates and for different reasons, so they should be **independently modular**.
  - Each use case should encapsulate some UI, business rules, and database interactions, ensuring that changes to one don’t affect others.

- **Independent Developability**

  - By decoupling components, teams can work on different parts of the system **independently**.
  - Independent developability promotes **concurrent development**, reducing integration issues and making the development process more efficient.

- **Independent Deployability**

  - Components should also be **deployable independently**.
    - A system with high cohesion and loose coupling allows for deployment without affecting the entire system.
    - This reduces risk, simplifies testing, and improves deployment agility.

- **Duplication**

  - Avoid duplication of functionality wherever possible. Duplication increases complexity and hampers independence.
    - Proper use of **shared components** and avoiding the repetition of similar logic in different places help maintain clean architecture.

- **Decoupling Modes (Again)**

  - Different **modes of decoupling** (layers, use cases, deployments) allow for flexibility in both development and operation.
  - Ensure that components remain **independent**, even when making decisions about deployment modes, shared libraries, or distributed services.

### Chapter 17: Boundaries - Drawing Lines

- **Software Architecture** is the art of drawing _boundaries_.
  - These boundaries separate different software elements and control how they interact.
  - Early boundaries help defer decisions and protect the core business logic.
- **Primary Objective of an Architect**: Minimize human resources needed to build and maintain systems.
  - **Coupling**, especially to premature decisions, can drain resources.
  - Premature decisions include non-business critical choices (e.g., frameworks, databases, web servers).
- **A Good Architecture**
  - Defers technical decisions that do not affect business logic.
  - Allows those decisions to be made later without major consequences.
- Boundaries should be drawn where there is an **axis of change**.
- Different components should change for different reasons at different rates.
- **Example**:
  - GUIs change at different rates than business rules, so boundaries should exist between them.
  - Business rules should be separate from frameworks like dependency injection tools.
- The **Single Responsibility Principle** helps identify where boundaries should be drawn.

- **Boundary Drawing Process**

  - Partition the system into components.
  - **Core business rules** are separated from other non-core functions (e.g., plugins).
  - Components are organized such that dependencies point towards the core business, adhering to:
    - The **Dependency Inversion Principle (DIP)**.
    - The **Stable Abstractions Principle (SAP)**.

- **Plugin Architecture**

  - Components that are not related to the core business logic can be treated as _plugins_.
  - A plugin architecture separates concerns, making the system more adaptable.

### Chapter 18: Boundary Anatomy

- **Boundary Crossing**

  - **Boundary crossing** refers to the interaction between components across different boundaries in a system.
    - At runtime, this is typically a **function call** from one side of the boundary to the other, accompanied by data exchange.
    - The critical element is **managing source code dependencies**, as changes in one source code module can trigger changes in others.
  - The goal is to create **firewalls** against the propagation of these changes, keeping components insulated and minimizing the ripple effects of modifications.

- **The Dreaded Monolith**

  - **Monoliths** are systems where boundaries exist conceptually but are not physically represented in the deployment structure.

    - All components are bundled into a **single executable file** (e.g., a Java jar, .NET executable, or a statically linked C/C++ program).
    - Despite the lack of physical separation, a well-structured monolith can still maintain **source-level decoupling**, allowing independent development and assembly of components.

  - **Dynamic polymorphism** is often used to manage internal dependencies in monoliths.
    - Without object-oriented techniques like dynamic polymorphism, separating and decoupling components can become risky, as it may require extensive use of pointers or other unsafe techniques.

- **Deployment Components**

  - **Deployment components** are physically separable boundaries, such as dynamically linked libraries (DLLs), Java jar files, or Ruby gems.
    - These components are deployed in binary form and gathered together during deployment (e.g., into a WAR file).
    - **Deployment-level decoupling** occurs when these components are independently compiled, deployable, and can interact dynamically at runtime.

- **Threads and Local Processes**

  - Components can communicate via **threads** or **local processes** within the same system.
    - Thread-level communication is fast but often tightly coupled, while processes offer more explicit boundary crossing, often using mechanisms like sockets.

- **Services**

  - **Services** represent the most strongly decoupled form of boundary crossing.
    - Components interacting through services are typically located on different machines, with interactions occurring over a network.
    - This separation offers the most independence, though it introduces latency and other distributed system challenges.

### Chapter 19: Policy and Level

- **Software as Policy**

  - **Software systems** are statements of **policy**.
    - A **policy** is a set of rules or principles that define how inputs are transformed into outputs.
    - The role of architecture is to organize and **separate policies** into components based on their likelihood and reasons for change.

- **Levels of Policy**

  - Different parts of a system represent policies at **different levels**:
    - **Low-level policies** manage **input/output** operations.
    - **High-level policies** handle **business rules** and core logic.
  - Policies that change for the same reasons belong at the same level and should be grouped together.
    - Those that change for different reasons should be separated.

- **Architecture and Dependencies**

  - The **art of architecture** involves creating a **directed acyclic graph (DAG)** of components.
    - The nodes in the graph represent **components** containing policies at the same level.
    - The edges represent **dependencies** between components, connecting higher-level policies to lower-level ones.
    - Dependencies should always point from lower-level policies to higher-level policies, ensuring stability and clear separation.

- **Understanding Levels**

  - **Level** can be defined as the **distance from the inputs and outputs**.
    - The farther a policy is from both inputs and outputs, the higher its level.
    - **Input/output management** is typically at the lowest level of the system, while core business logic sits at higher levels.

- **Proper Dependency Direction**

  - It's essential to ensure **source code dependencies** flow in the right direction, **from low-level components to high-level components**.
  - Incorrect dependency management results in an architecture where high-level policies depend on low-level input/output policies, reducing flexibility and maintainability.

### Chapter 20: Business Rules

- **What Are Business Rules?**

  - **Business Rules**: Procedures or guidelines that either **make** or **save money** for a business.
    - These rules **would exist** even if the process was executed manually, without software.
    - Example: A bank charging interest on loans is a business rule. Whether a clerk or a computer calculates the interest is irrelevant.

- **Critical Business Rules**

  - **Critical Business Rules**: Business rules that are **vital** to the core operation of the business.
    - These rules are **inextricably linked** to the business and would remain in place even without automation.
    - Example: For a loan, critical rules might involve calculating the interest rate, determining payment schedules, or managing the loan balance.

- **Critical Business Data**

  - **Critical Business Data** is the data required to support critical business rules.
    - This data exists **independently** of the system and automation.
    - For example, in a loan system, critical business data would include the **loan balance**, **interest rate**, and **payment schedule**.

- **Entities**

  - **Entities** are software objects that embody a set of critical business rules and operate on **Critical Business Data**.
  - Entities either contain the critical business data or have easy access to it.
  - **Entity Interface** consists of functions that implement the critical business rules.

- **Use Cases**

  - **Use Cases**: Specific to automated systems, these rules define **how and when** critical business rules are invoked.
    - They describe how an automated system should behave, including the **input**, **output**, and **processing steps**.
    - Use cases typically control the flow of **entities** and define the sequence of interactions between **entities** and the system.

- **Request and Response Models**

  - **Request Models**: Input data that use cases expect to receive.
  - **Response Models**: Output data that use cases generate after processing.
    - These models are **simple** and should not be tied to any particular **framework** (e.g., HTTP, HTML).
    - They are **pure data structures**, focusing solely on the information needed for the use case.

### Chapter 21: Screaming Architecture

- **The Theme of an Architecture**

  - The **architecture** of a system should make its purpose clear from the top-level structure.
    - Example: The blueprints of a house or library immediately indicate their function—architecture should do the same for software.
  - When looking at the **top-level directories and source files** in your system, it should be evident what kind of system it is.
    - Does it scream **Health Care System**, **Accounting System**, or does it scream **Rails**, **Spring**, or **ASP**?

- **Frameworks Are Tools, Not the Architecture**

  - **Frameworks** should be viewed as tools, not as the foundation of the system's architecture.
    - Frameworks should be chosen and used to serve the **use cases** of the system, not dictate its architecture.
  - If the architecture of your system is dominated by a framework, your architecture will be constrained by the decisions of the framework creators.

- **Architecture Should Support Use Cases**

  - A good architecture is centered on **use cases**, which define how the system functions.
    - The system's structure should reflect its primary use cases, with components organized around these functionalities.
    - The architectural structure should expose the system's behavior clearly.

- **The Purpose of Architecture**

  - **Architecture** is meant to support **development** and **maintenance** by deferring details like frameworks, databases, or user interfaces until later.
  - **Decisions about frameworks, databases, and other specifics** should be deferred as long as possible to maintain architectural flexibility.
  - Architects focus on **the high-level structure** that supports the core use cases, ensuring that the system can grow and adapt without being overly tied to specific technologies early on.

- **Testable Architectures**

  - A well-designed architecture should be **testable**.
    - Architecture should allow for testing without requiring the instantiation of frameworks, databases, or UIs.
    - The **business rules** and logic of the system should be isolated enough to be tested independently of the environment they run in.

### Chapter 22: The Clean Architecture

- **Clean Architecture** integrates several architectural ideas aimed at **separation of concerns** by organizing systems into **layers** and **boundaries**.
- The goal is to keep **business rules** independent from **frameworks, UI, databases**, and other external components.

- **Examples of similar architectures:**

  - **Hexagonal Architecture (Ports and Adapters)** by Alistair Cockburn.
  - **DCI (Data, Context, and Interaction)** by James Coplien and Trygve Reenskaug.
  - **BCE (Boundary, Control, Entity)** by Ivar Jacobson.

- **Characteristics of Clean Architecture:**

  1. **Framework Independence**:

  - The system should not be tightly coupled to any specific framework. This allows frameworks to be used as **tools**, not to dictate the system’s structure.

  2. **Testability**:

  - Business rules can be tested without the need for external elements like the UI, database, or web server.

  3. **UI Independence**:

  - The user interface should be replaceable without requiring changes to business rules or other parts of the system. For example, a web UI could be swapped with a console UI without affecting the core logic.

  4. **Database Independence**:

  - The business rules should be decoupled from the database, allowing the flexibility to switch databases (e.g., Oracle to MongoDB) without impacting business logic.

  5. **Independence from External Agencies**:

  - Business rules should not depend on interfaces to the external world (e.g., APIs or network services).

- **The Dependency Rule**

  - **The Dependency Rule** is the core principle that dictates **how the dependencies between the layers must flow**:
    - **Source code dependencies must always point inward**, towards higher-level policies.
    - Inner layers should not be aware of outer layers. In particular, code in inner layers must not mention or reference entities in outer layers, such as frameworks or user interfaces.

- **Clean Architecture Layers:**

  1. **Entities**:

  - Contain **Critical Business Rules** that are enterprise-wide. Entities can be objects or data structures that encapsulate the most general business rules.
  - These are the **most stable** and **least likely to change** when external elements evolve.

  2. **Use Cases**:

  - Implement **application-specific business rules** that orchestrate the interaction between entities and achieve the goals of the use case.
  - The use case layer is isolated from external systems like databases or user interfaces, ensuring its flexibility and maintainability.

  3. **Interface Adapters**:

  - **Interface adapters** convert data from the use case and entities to the format required by external systems (e.g., UI, database, or external APIs).
  - These adapters isolate the **use cases** and **entities** from external systems, ensuring that they remain unaffected by changes in the UI or databases.

  4. **Frameworks and Drivers**:

  - The outermost layer, containing **frameworks** and **tools** (e.g., web frameworks, databases, and devices).
  - These components are interchangeable without affecting the core business logic.

### Chapter 23: Presenters and Humble Objects

- **Presenters** are a key concept in Clean Architecture, acting as a form of the **Humble Object Pattern**.

  - Their role is to format data into a **View Model** for display.
  - The **View** merely moves this formatted data onto the screen, with no processing logic.

- **The Humble Object Pattern**

  - Designed to separate hard-to-test behaviors from easy-to-test ones.
    - **Humble objects** contain difficult-to-test logic, stripped down to the barest essentials.
    - The **testable object** contains behaviors that are easy to test, split from the humble object.

- **Presenters and Views**

  - **View**: The humble object; it moves data into the GUI but avoids any logic processing.
    - Kept as simple as possible to ensure its role is strictly for visual data representation.
  - **Presenter**: A testable object that accepts application data and formats it for the view.
    - Prepares **View Models** with strings, booleans, and formatted data.
      - Example: A date is passed to the presenter, which formats it and stores it in the View Model as a string.
    - Handles any necessary UI formatting (e.g., setting flags for grayed-out buttons).
    - Prepares and stores everything the view needs, ensuring the view has no additional processing responsibilities.

- **Testing and Architecture**

  - **Testability** is a core aspect of good architecture.
    - The separation between testable and non-testable parts, as seen in the Presenter/View division, helps in defining architectural boundaries.
    - Use of the **Humble Object pattern** at architectural boundaries significantly increases system testability.

- **Database Gateways**

  - **Gateways** exist between use case interactors and databases.
    - These are polymorphic interfaces with methods for CRUD operations.
    - SQL or database-specific logic is handled in the database layer, ensuring interactors remain testable.

- **Data Mappers**

  - **Object Relational Mappers (ORMs)** should be placed in the database layer.
    - They map data between relational databases and data structures, but do not belong to use cases or entities.

- **Service Listeners**

  - The **Humble Object pattern** also applies to service interfaces.
    - Input and output between services should be handled by simple data structures, minimizing the complexity of the logic crossing service boundaries.

### Chapter 24: Partial Boundaries

- **Full-fledged architectural boundaries**

  - Expensive to implement and maintain.
  - Require reciprocal polymorphic **Boundary interfaces**, **Input and Output data structures**, and dependency management to keep components independently compilable and deployable.
  - Involves significant setup and ongoing maintenance.

- **Partial boundary**

  - Introduced when a full boundary is considered too costly but there may be a need for it later.
  - Allows holding a place for a boundary while avoiding full implementation.

- **YAGNI**

  - “You Aren’t Going to Need It” is often cited in Agile development to avoid premature optimization, but architects may opt for a partial boundary as a compromise between cost and future flexibility.

- **Skip the last step**:

  - Involves setting up the components as if a full boundary is in place but keeping them in the same component.
  - Saves on administration costs, such as **version tracking** and **release management**.
  - Still requires significant design and coding effort to maintain the boundary.

- **One-dimensional boundaries**

  - A simpler approach than a full boundary, based on the **Strategy pattern**.
  - **ServiceBoundary interface** isolates the **Client** from **ServiceImpl** classes.
  - Risks include backchannel dependencies that can erode the separation, making maintenance harder.

- **Facade pattern**

  - Simplifies boundary implementation further by eliminating **dependency inversion**.
  - The **Facade class** defines services as methods, directing calls to classes the **Client** isn’t supposed to access.
  - The **Client** maintains a transitive dependency on the service classes, creating risks in static languages, such as **recompilation** requirements when changes are made to the source code.

### Chapter 25: Layers and Boundaries

- Layers and boundaries define the **structure** of a software system by segmenting the system into components with specific responsibilities.
- For many systems, the architecture is seen as comprising three primary layers:

  - **UI (User Interface)**
  - **Business Rules**
  - **Database**

- **Clean Architecture and Boundaries**

  - In **Clean Architecture**, boundaries between components enforce **separation of concerns**.
    - This decoupling ensures that changes in one layer (e.g., the UI) do not impact other layers (e.g., the business rules).
    - Each layer should be **self-contained**, with clearly defined **interfaces** to communicate with other layers.

- **Crossing the Streams**

  - Communication between layers is typically achieved via **data transfer objects** or **API calls**.
    - However, care must be taken to prevent **cross-layer dependencies** from forming.
    - Example: In the Wumpus game, the game rules layer should never depend directly on how the UI layer renders output.

- **Splitting the Streams**

- Over time, a system might evolve to have more than just the basic three layers.
  - Additional layers may be introduced to handle things like **authentication**, **logging**, or **caching**.
  - As the number of layers grows, it's crucial to maintain **boundaries** and ensure that **dependencies** point in one direction (from high-level policies down to lower-level details).

### Chapter 26: The Main Component

- Every system has at least one component responsible for creating, coordinating, and overseeing others.

  - This component is referred to as **Main**.

- **The Ultimate Detail**

  - **Main** is the system's ultimate detail and lowest-level policy.
  - It serves as the **initial entry point** into the system, typically dependent only on the operating system.
  - Responsibilities:
    - Create all factories, strategies, and other global facilities.
    - Hand over control to higher-level abstract portions of the system.

- **Dependency Injection**

  - Dependencies should be injected into **Main** by a **Dependency Injection framework**.
  - After injection, **Main** distributes dependencies without further use of the framework.
  - **Main** is considered the **dirtiest component** in the system since it handles low-level tasks like setup and bootstrapping.

- **Main as a Plugin**

  - **Main** should be treated like a plugin that handles initial conditions, external resource gathering, and then passes control to the system's higher-level logic.
  - This approach allows flexibility:
    - Different **Main** components for different environments (e.g., Dev, Test, Production).
    - Possible configurations based on jurisdiction, customer, or country.

### Chapter 27: Services: Great and Small

- **Service-oriented architectures** (SOA) and **micro-service architectures** have gained popularity for reasons including:

  - **Perceived decoupling**: Services seem to be strongly decoupled from each other. However, this is not always the case.
  - **Independence of development and deployment**: Services appear to allow for independent development and deployment, but this is only partially true.

- **Service Architecture**

  - Using services does not inherently define the **architecture** of a system.
  - True architecture involves boundaries that separate **high-level policy** from **low-level details** and follow the **Dependency Rule**.
  - Services that merely divide application behaviors do not always follow architectural principles. They may function as expensive function calls without architectural significance.

- **Architecturally Significant Services**

  - Not all services need to be architecturally significant. Services separating functionality across processes and platforms can be beneficial, but that alone doesn’t define a system’s architecture.
  - The architecture is determined by which function calls cross architectural boundaries, adhering to the **Dependency Rule**.

- **The Decoupling Fallacy**

  - Many believe that **microservices** guarantee decoupling and independence, but often services become tightly coupled. This happens due to the necessity of coordinating development and deployment, undermining the original purpose of service orientation.

- **Cross-Cutting Concerns**

  - New features that affect multiple parts of a system can lead to tight coupling across services. For example, adding a new feature may require simultaneous changes across many services, reducing their independent development/deployment.

- **Objects to the Rescue**

  - In a **component-based architecture**, the **SOLID design principles** can guide the creation of classes that handle new features through **polymorphism**. This can decouple the new functionality from existing components.
  - For instance, a new feature can be implemented by adding a new class that extends the original class without modifying the existing ones.

- **Component-Based Services**

  - Services can be designed using **component-based architectures** and **SOLID principles**, allowing new components to be added without altering existing ones.
  - In this approach, new features can be added by deploying new components, such as adding new JAR files to a system, adhering to the **Open-Closed Principle**.
  - The **Dependency Rule** ensures that the components within the services maintain proper boundaries, allowing for easier extension and maintenance.

### Chapter 28: The Test Boundary

- **Tests as System Components**

  - Tests are a part of the system architecture like any other component.
  - Tests are structured according to the **Dependency Rule**: tests depend inward on the code being tested.
  - From an architectural point of view, all tests—**unit tests**, **integration tests**, **acceptance tests**, and others—are treated similarly.
  - Tests are usually **independently deployable** and are generally deployed in test systems, not production systems.
  - Tests are the **most isolated component**; no user depends on them, and their role is to support development.

- **Design for Testability**

  - Proper integration of tests into the system's design prevents the **Fragile Tests Problem**, where minor changes in the system require extensive updates to tests.
  - Tests that are strongly coupled with the system make the system rigid and harder to change.
    - For example, tests that use the **GUI** to verify business rules can break with any changes to the GUI.
    - The solution is to design **testing APIs** to bypass volatile system components like GUIs.

- **Testing API**

  - A **Testing API** allows tests to verify business rules without interacting with volatile components like GUIs.
  - The Testing API should enable tests to bypass security constraints, skip expensive resources like databases, and force the system into specific testable states.
  - This API should **decouple** the tests from the application structure, allowing independent evolution of the application and the tests.

- **Structural Coupling**

  - Structural coupling between tests and application code (e.g., one test class per production class) makes both tests and the production code fragile.
  - A **Testing API** helps hide the application’s structure from tests, reducing coupling and promoting flexibility.

- **Security Concerns**

  - **Testing APIs** with superpowers (e.g., bypassing security or resource constraints) could be a security risk if deployed in production.
  - To mitigate this risk, the Testing API should be placed in a **separate, deployable component**, ensuring it is not included in the production environment.

### Chapter 29: Clean Embedded Architecture

- **Embedded Systems** face unique challenges compared to other types of software due to hardware limitations and real-time constraints.

- **Firmware and Hardware Evolution**

  - **Doug Schmidt's Insight**: While software doesn’t wear out, **firmware and hardware become obsolete**, necessitating software updates.
  - Embedded software often becomes tightly coupled with the hardware, creating **dependencies** that shorten its lifespan.

- **Layers in Embedded Systems**

  - **Layering** helps isolate **hardware** from **software**. Layers prevent hardware dependencies from seeping into the system, making it easier to maintain when hardware changes.
  - Common architecture involves **three layers**:
    1. **Hardware Layer**: The lowest level, containing physical hardware.
    2. **Abstraction Layer**: Hides hardware specifics from upper layers.
    3. **Application Layer**: Contains high-level business logic.

- **Target-Hardware Bottleneck**

  - If testing can only occur on target hardware, **development is slowed**.
  - A **clean embedded architecture** can eliminate this bottleneck by making software testable off-target through the use of **Hardware Abstraction Layers (HALs)** and **Operating System Abstraction Layers (OSALs)**.

- **Program to Interfaces**

  - Encourages **programming to interfaces** rather than concrete implementations, which allows for substitutability.
  - A **HAL** decouples the application from hardware specifics, making it easier to swap out hardware without rewriting large portions of code.

- **Testability**

  - A clean embedded system is one where the software is **testable independently** of the hardware. This reduces the dependency on the target hardware during testing, mitigating the **target-hardware bottleneck**.

- Principles to Apply:

  - **Hardware is a Detail**: Treat hardware like any other external dependency. Keep the **hardware details** hidden from the application code by using **abstraction layers**.
  - **Operating System is a Detail**: Use an **Operating System Abstraction Layer (OSAL)** to isolate software from the operating system. This makes it easier to migrate software between operating systems.
  - **Substitutability**: **Programming to interfaces** increases the substitutability of components, making testing and maintenance easier.

### Chapter 30: The Database Is a Detail

- **Database as a Non-Entity**

  - From an architectural standpoint, a database is a low-level **detail** rather than an architectural element.
  - It's similar to how a **doorknob** relates to the overall architecture of a house; it's functional but not central to the design.

- **Distinction Between Data Model and Database**

  - The **data model** (structure of data in the application) is crucial to the system's architecture.
  - The **database** itself is just a utility for accessing that data, and from an architectural point of view, it is irrelevant.

- **Relational Databases**

  - Defined by **Edgar Codd** in 1970, relational databases became the dominant data storage model by the 1980s due to their elegance and robustness.
  - Despite their popularity, relational databases are still just **technologies**—details rather than architecturally significant elements.

- **Architectural Isolation from Database**

  - Data arrangements like **rows and tables** are irrelevant to the architecture.
  - **Use cases** and **business rules** should not know about the structure of the database. This knowledge should be confined to **low-level utility functions**.

- **Error of Passing Database Structures**

  - Many systems erroneously pass database rows and tables as objects throughout the system, creating tight coupling between business rules, use cases, and sometimes the UI.
  - This practice is an **architectural error** and should be avoided.

- **Prevalence of Databases**

  - Database systems dominate the software landscape because of the long history of **disk-based data storage**.
  - **Disks** were the mainstay of storage for five decades, and many generations of programmers were trained to store data on disks.

- **The Problem with Disks**

  - While disk technology evolved from large, slow systems to terabyte storage, they remained **slow** compared to other storage mechanisms.

- **What if There Were No Disks?**

  - When data storage moves to **RAM**, tables and SQL will become irrelevant.
  - Programmers will organize data into structures like **linked lists**, **trees**, and **hash tables**, using **pointers** or **references**.
  - This is already done in practice: data is read from files or databases into **RAM**, where it’s restructured into more useful formats.

- **Details**

  - The database is just a **mechanism** to move data between **disk** and **RAM**.
  - The format of data on disk is inconsequential from an architectural viewpoint.

- **Performance Concerns**

  - Performance in data storage is important but can be encapsulated in **low-level mechanisms**, separate from **business rules**.
  - Thus, performance is a concern, but it does not dictate the **overall system architecture**.
