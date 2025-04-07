# [The Twelve-Factor App by Adam Wiggins (2017)](https://12factor.net/)

## Introduction

- **What is the Twelve-Factor App?**

  - A _methodology_ for building Software-as-a-Service (SaaS) apps that are:

  1. **Declarative** in setup for fast onboarding.
  2. **Portable** across different execution environments.
  3. **Optimized** for modern cloud platforms (serverless, managed infra).
  4. **Aligned** across development and production to support:
     - Continuous Deployment
     - Agility
  5. **Scalable** without overhauling architecture or tooling

- **Key Characteristics**

  - Language-agnostic.
  - Compatible with all types of backing services:
    - Databases
    - Message queues
    - Caches
    - Other APIs or services

- **Purpose of the Methodology**

  1. _Synthesize_ real-world experience into best practices.
  2. _Address_ common challenges in SaaS development:
     - Organic app growth
     - Developer collaboration
     - Software erosion
  3. _Provide_:
     - A shared vocabulary
     - Conceptual solutions
     - Practical patterns

## I. Codebase

> "One codebase tracked in revision control, many deploys"

- A twelve-factor app has a _single codebase_ that is:

  - Tracked in a _version control system_ (e.g., Git, Mercurial, Subversion).
  - _Shared_ across all environments: development, staging, production.

- **Key Guidelines**

1. **One App = One Codebase**

   - Every app should have its own unique codebase.
   - Multiple deploys (instances) use this single codebase.

2. **Multiple Codebases ≠ One App**

   - If multiple codebases are involved, it’s considered a distributed system, not a single app.
   - Each part of a distributed system should individually comply with the twelve-factor methodology.

3. **No Shared Codebases Between Apps**

   - Sharing a codebase across multiple apps violates the twelve-factor principles.
   - Instead, extract shared functionality into libraries and include them as dependencies.

## II. Dependencies

> "Explicitly declare and isolate dependencies"

- A twelve-factor app:

  - _Declares all dependencies explicitly_.
  - _Isolates dependencies_ to avoid relying on system-wide packages or tools.

- **Key Practices**

  1. **Dependency Declaration**

     - Use a _dependency manifest_ (e.g., Gemfile, requirements.txt) to:
     - List all libraries the app depends on.
     - Specify versions explicitly and completely.

  2. **Dependency Isolation**

     - Use tools to _isolate the app’s environment_, preventing accidental use of global/system packages.
     - Ensures _reliable, repeatable builds_ across all environments (dev, staging, production).

- Do _not_ assume system tools (e.g., curl, ImageMagick) are available.
  - If needed, these should be:
    - _Vendored_ (included in the app's directory), or
    - Managed explicitly as part of the app’s dependency list.
