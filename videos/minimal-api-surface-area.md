[# Minimal API Surface Area by Sebastian Markbåge (2014)](https://www.youtube.com/watch?v=4anAwXYqLG8&ab_channel=JSConf)

- React aims to reduce the number of framework-specific APIs by relying more on JavaScript's native features.

- **Patterns over frameworks**

  - Learning patterns like higher-order functions and JavaScript paradigms is more valuable than learning framework-specific APIs.

- **Explicit over implicit**

  - Explicit code, while verbose, is easier to understand and maintain than implicit abstractions.

- **Avoid unnecessary abstractions**

  - Abstractions should only be added if they solve real problems, not for convenience.

- **API proliferation problem**

  - The vast number of APIs in JavaScript libraries complicates learning and maintaining code.

- **React’s design**

  - React relies on minimal, explicit APIs like setState and JSX, which are built on top of native JavaScript features.

**Balance abstractions**

- Developers should avoid abstractions that increase complexity, focusing instead on simple, reusable patterns.

- **Burn surface area**

  - For every abstraction added, an equivalent amount of complexity should be removed to maintain simplicity.

- **Standardization**

  - React supports ES6 standards to reduce dependency on proprietary APIs, facilitating easier integration with third-party tools.

> "It's not that the library is too big... it's the total amount of APIs that you have to learn to be productive in this industry."

> "It's much easier to recover from no abstraction than the wrong abstraction."
