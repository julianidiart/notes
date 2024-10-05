# [The Two Reacts by Dan Abramov (2024)](https://overreacted.io/the-two-reacts/)

## Client-Side Components

- **Client-side interactivity**: _UI = f(state)_.
- Components that run on the user's computer.
- Instant feedback during user interactions.

## Server-Side Components (UI = f(state))

- **Server-side data processing**: _UI = f(data)_.
- Doesn't require the user's device to handle raw data.
  - Reduces the complexity of client-side operations.

## Mutual Incompatibility

- While client-side components enable interactive UI, server-side components cannot utilize client-only APIs.
  - Running all components on the server limits their interactivity.
    - They can only render initial states without knowledge of user interactions

## Need for a Hybrid Approach

- _UI = f(data, state)_.
- Leverage the strengths of both paradigms
- Enable components to function effectively across client and server environments.
