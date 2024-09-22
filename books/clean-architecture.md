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
