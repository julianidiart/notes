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
