# [Good Abstraction, Bad Abstraction by Maxi Ferreira (2023)](https://frontendatscale.com/issues/2)

- **Deep vs. shallow modules**

  - Deep modules offer powerful functionality through a simple interface, while shallow modules introduce complexity without much value.

- **Encapsulation and detail hiding**

  - Good abstractions should hide unnecessary details and expose important behavior, like asynchronous operations that could affect results.

- **Consistent abstraction level**

  - Modules should operate at a single level of abstraction, avoiding the mixing of responsibilities (e.g., database updates with DOM manipulation).

- **The danger of overusing DRY**

  - Excessive code reuse can lead to bad abstractions, which are hard to maintain and scale as requirements evolve.

- **"Boring" architecture advice**

  - Sticking to simple, proven architectures helps maintain focus on delivering value to users, rather than constantly chasing new frameworks.

- **Separation of concerns**

  - Avoiding mixed responsibilities within a single function ensures more maintainable and predictable code.

- **Focus on problem-solving**

  - Ultimately, abstractions should help solve problems with manageable complexity, not aim for theoretical perfection.
