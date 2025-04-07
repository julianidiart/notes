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

## III. Config

> "Store config in the environment"

- Configuration should be stored in _environment variables_ (env vars), not in the codebase.

- Configuration includes everything that _varies between deploys_.

- **Violations of Twelve-Factor**

  1. _Hardcoding config as constants in code_.
  2. _Using config files_ (e.g., config/database.yml) that:

  - May accidentally be committed to version control
  - Scatter config across locations and formats
  - Are often _language/framework-specific_

- **Why Environment Variables?**

  - **Benefits**:
    - Separation of config from code
    - Easy to modify per deploy without touching code
    - Less risk of accidentally committing secrets
    - Standardized across languages and operating systems
  - **Security Tip**: A proper app should be safe to open-source _without exposing credentials_, thanks to env var-based config.

- **Avoid “Environment Grouping”**

  - Traditional frameworks group config (e.g., "development", "production").
  - This doesn't scale well — leads to:
    - Fragile naming patterns (e.g., joes-staging, qa2)
    - Difficult maintenance and management
  - **Twelve-Factor Approach**:
    - Use _individual env vars_, not grouped environments.
    - Each variable is:
      - _Independent_
      - _Granular_
      - _Easily adjustable per deploy_

## IV. Backing services

> "Treat backing services as attached resources"

- **Core Principles**

  1. **Treat All Services as Attached Resources**

     - No difference between _local_ and _third-party_ services.
     - Both are accessed via _configuration_ (e.g., URL, credentials).
     - Swappable without code changes — only the config changes.

  2. **Resources Are Loosely Coupled**

  - Services can be:
    - _Attached_ (connected via config)
    - _Detached_ (replaced or removed)
  - Example: Replacing a local MySQL DB with Amazon RDS _requires no code change_, only an updated connection string.

- **Benefits**

  - **Flexibility**: Easily switch between providers or instances.
  - **Resilience**: Quickly recover from failures (e.g., swap DB server).
  - **Environment Agnosticism**: Works across development, staging, and production without code changes.

## V. Build, release, run

> "Strictly separate build and run stages"

- **Three Stages of Deployment**

  0. _Codebase_
     ↓
  1. **Build** → Executable Build
     ↓
  2. **Release** → Build + Config = Release
     ↓
  3. **Run** → App processes launched from release

1. **Build Stage**

- **Purpose**: Turn code into an executable bundle.
- **Tasks**:
  - Pull code from a specific commit.
  - Fetch and vendor dependencies.
  - Compile code, assets, and binaries.
- **Triggered by**: A developer during deployment.

2. **Release Stage**

- **Purpose**: Combine build with environment-specific config.
- **Result**: A _release_ that is:

  - Immutable
  - Executable
  - Identified by a unique release ID (e.g., timestamp or version number)

- **Rollbacks**
  - Releases are _append-only_ and cannot be modified.
  - Rollbacks are achieved by selecting a previous release (e.g., using tools like Capistrano).

3. **Run Stage**

- **Purpose**: Run the app in its execution environment using a selected release.
- **Characteristics**:

  - No code changes allowed during runtime.
  - App is launched by a _process manager_ or _runtime environment_.
  - Should remain _simple and reliable_, since failures often happen without developer intervention.

- **Best Practices**
  - Do:
    - Keep build and release processes _automated and reproducible_.
    - Use _unique release IDs_ for tracking and rollback.
    - Ensure run stage is _simple_ to avoid runtime failures.
  - Don’t:
    - Modify code or config at runtime.
    - Couple build logic with runtime behavior.
    - Allow mutable releases or manual hotfixes in production.

## VI. Processes

> "Execute the app as one or more stateless processes"

- A twelve-factor app runs as one or more _stateless processes_. Any persistent data must be stored in external backing services (e.g., databases, caches).

- **Stateless & Share-Nothing**

  - Allowed:
    - Short-lived memory or filesystem use (e.g., temporary cache for a single operation).
    - Example: Download → Process → Save result to DB.
  - Not Allowed:
    - Relying on local state to persist across requests or restarts.
    - Assuming one process will handle sequential requests from the same user.

- Some apps use _“sticky sessions”_ – binding users to a specific app process.

  - This breaks process statelessness.
  - Instead, session data should be stored in a _shared, external store_ like Redis.

- **Why Stateless?**

  - **Scalability**: Processes can be added/removed easily without rebalancing
  - **Reliability**: Restarting a crashed process doesn’t lose application state
  - **Portability**: Processes can be relocated across environments effortlessly

## VII. Port binding

> "Export services via port binding"

- A twelve-factor app exports services by _binding to a port_, rather than relying on an external web server injected at runtime.

- **Traditional Model vs. Twelve-Factor Model**

  - _Traditional Web App_
    - Injected into a container server
    - Example: PHP inside Apache
    - Server managed by external agent
  - _Twelve-Factor App_
    - Self-contained web server in code
    - Example: Python app with Tornado
    - App binds to a port itself

- **How Port Binding Works**

  - In _Development_: App listens on a localhost port.
  - Example: http://localhost:5000/
  - In _Production_: A routing layer maps public URLs to internal ports.
  - Example: A load balancer routes requests to web processes bound on internal ports.

- Apps can export _any protocol_ via port binding (not only HTTP).

- **Port Binding Enables**:

  - Easy _local testing_ and development.
  - Apps acting as _services for other apps_ via config-defined URLs.
  - Clean _decoupling_ from infrastructure — app expects just a port, not a runtime web server.

- **Best Practices**

  - Do
    - Use internal webserver libraries (e.g., Jetty, Thin)
    - Bind to a specific port and serve requests
    - Use the port-binding model for any service protocol
  - Don’t
    - Depend on external containers like Apache or Tomcat
    - Assume a pre-configured runtime web server
    - Hardcode environment-specific port logic
