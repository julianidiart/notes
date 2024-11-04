# [Several Components Are Rendering by Jenna Zeigen (2024)](https://www.youtube.com/watch?v=f-B2mL5Wegk&ab_channel=LeadDev)

## Understanding Performance

- Enhance _user experience_ by reducing latency, ensuring smooth interactions, and eliminating dropped frames.
- _Do less work_ to improve performance.

## Slack and Browser Basics

- Web-based _Electron_ app using HTML, CSS, JavaScript.

## Browser Rendering Basics

- **Rendering Process**:
  - Convert HTML to DOM Tree.
  - Convert CSS to CSSOM Tree.
  - Combine into Render Tree.
- **Layout → Paint → Composite**.
- **Performance Target**: 60 frames per second (~16ms per frame).

## JavaScript and Browser Constraints

- **Single-Threaded Nature**: JavaScript shares the main thread with rendering tasks.
- **Event Loop**: Synchronous and asynchronous tasks managed in a queue.
- **Challenge**: JavaScript tasks longer than 16ms can cause dropped frames.

## User Experience and Performance

- **RAIL Model** (Google’s UX framework):
  - **Respond** within 100ms to user actions.
  - **Animate** within 16ms per frame.
  - **Idle**.
  - **Load**.

## Frontend Performance Challenges

- Cannot upgrade _users' hardware_ like on the backend.
- Large-scale Slack application necessitates efficient state management.

## React and Redux Overview

- **React**: _Component-based UI framework_ promoting modularity.
- **Redux**: _State management library_ with a central store, enabling components to subscribe to state changes.
- Redux Loop: **Actions → Reducers → Store Update → Re-render**.

## Performance Issues in Redux Loop

1. Too Many Redux Dispatches:
   - Frequent _updates_ from API calls, WebSocket events, and user interactions.
2. Excessive Selector Calculations:
   - Thousands of connected _props recalculated_ per loop.
3. Unnecessary Re-renders:
   - Components _re-render_ due to deep-equal but unstable props.

## Optimization Strategies

- Targeting _Problem Components_
  - Channel Sidebar:
    - Identified as a _performance bottleneck_.
    - Optimizations led to a 30% improvement.
  - Solutions:
    - Reduce _repeated work_.
    - Create _specialized components_.
    - Eliminate _unused props_.
- _Broad-Spectrum_ Solutions
  - _Batch Updates_:
    - Delay Redux notifications to improve efficiency.
  - _Codemods_:
    - Automate detection of performance issues in code.
  - _Reducing Redux Usage_:
    - Investigate _IndexedDB_ for storing less critical data.
    - Explore _finer-grained subscriptions_.

## Building a Performance Culture

- Education:
  - _Teaching_ engineers about React/Redux internals.
- Tooling:
  - Lint rules and runtime warnings to _highlight performance liabilities_.
- Evangelism:
  - Encourage _all engineers to contribute_ to performance improvements.

## Reflection and Future Direction

- Trade-offs:
  - _Balancing_ between fixing the current system and rearchitecting.
- Empowering Engineers:
  - _Equip_ engineers with knowledge and tools to tackle performance issues.

> "It takes a lot of work to do less work."
