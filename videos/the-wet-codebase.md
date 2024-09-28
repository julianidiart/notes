[# The wet codebase by Dan Abramov (2019)](https://www.youtube.com/watch?v=17KCHwOwgms)

- Overly complex abstractions can lead to difficult-to-maintain codebases.
- Blindly following _"Don't Repeat Yourself"_ can lead to fragile, bug-prone abstractions.
- Abstractions often evolve to include special cases, which increase complexity and reduce clarity.
- Copy-pasting code can be beneficial when abstractions don't fit all cases.
- Best practices like _DRY_ need to be applied with context; rigid application can result in worse outcomes.
- Shared abstractions create dependencies, making it hard to change one part of the system without affecting others.
- Simple, isolated code is often better than abstracting too early. Inline abstractions when necessary.
- When passing on coding best practices, it's essential to explain the trade-offs involved.
- Abstractions can lead to overly layered (_"lasagna"_) code that becomes as confusing as unstructured (_"spaghetti"_) code.

- **Cost of Abstraction**

  - Accidental coupling
  - Extra indirection
  - Inertia

- **Abstract Responsability**

  - Test concrete code
  - Delay adding layers
  - Be ready to _inline it_
