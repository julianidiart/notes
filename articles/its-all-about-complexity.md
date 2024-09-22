# [It's All About Complexity by Maxi Ferreira (2023)](https://frontendatscale.com/issues/1)

- **Complexity** is the primary source of most software problems, including security flaws and performance bottlenecks.

- **Definition of Complexity**

  - Complexity in software systems is anything that makes them harder to understand or change, such as inconsistent folder structures or disorganized state management.

- **Symptoms of Complexity**

  - _Change amplification_, _cognitive load_, and _unknown unknowns_ as key indicators of growing complexity in codebases.

  - **Change Amplification**: When a small change requires updates in multiple parts of the system, it's a sign of complexity.

  - **Cognitive Load**: High cognitive load occurs when developers must retain excessive information to work with a system, often caused by low cohesion.

  - **Unknown Unknowns**: Dependencies between parts of a codebase that are only discovered during issues are a major source of unpredictable complexity.

- **Strategies for Simplicity**

  - Small changes, such as removing unnecessary props or encapsulating side effects, can significantly reduce complexity over time.
  - Principles for scaling frontend apps include making it _easy to delete_ code and ensuring that knowledge is accessible to all team members, regardless of experience.
