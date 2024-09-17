# Clean Architecture (2018)

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
