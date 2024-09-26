# [Documenting Architecture Decisions by Michael Nygard (2011)](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions)

- **Modular documentation**

  - Small, modular documents are easier to maintain and update than large, comprehensive ones.
  - **Architecture Decision Records (ADRs)** are a short, standardized format for capturing significant architectural decisions.

- **Avoid blind decisions**

  - ADRs help prevent future developers from either blindly accepting or changing decisions without understanding their context.

- **Simple, structured format**

  - ADRs consist of sections like _Title_, _Context_, _Decision_, _Status_, and _Consequences_, ensuring clarity and brevity.

- **Sequential and permanent**

  - ADRs are numbered sequentially and remain in the project repository even if a decision is reversed.

- **Capturing intention**

  - ADRs are particularly useful for documenting long-term intentions and architectural shifts.

- **Visibility of rationale**

  - The rationale behind decisions is preserved, preventing confusion for new team members.

- **Impact on future decisions**

  - Each ADR’s consequences become the context for subsequent decisions, similar to pattern languages in architecture.

- **Version control**

  - ADRs are stored in version control systems, making them accessible and up-to-date alongside the code.
