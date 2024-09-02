# Clean Agile (2019)

## 1. Introduction to Agile

### History of Agile

- Agile principles, which focus on small, intermediate goals and progress measurement, have roots in early software development practices.
- These principles were overshadowed by the rise of Scientific Management, which emphasized heavy planning and a top-down approach.

### The Agile Manifesto

- Individuals and interactions over processes and tools.
- Working software over comprehensive documentation.
- Customer collaboration over contract negotiation.
- Responding to change over following a plan.

### Agile Overview

- Agile is based on continuous feedback and adjustment.
- Agile emphasizes flexibility and responsiveness, with a focus on delivering value regularly through iterative development.

### A Waterfall Project

- Agile integrates analysis, design, and implementation into every iteration, allowing for continuous refinement and realistic project adjustments based on actual progress​.

### The Agile Way

- Agile projects are divided into short, time-boxed iterations or sprints.
- Each sprint includes planning, execution, and review stages, ensuring that feedback is constantly integrated.

### Circle of Life

- Agile is a small discipline that helps small software teams manage small projects. Big projects are made from small projects.

## 2. The Reason for Agile

### Professionalism

- Discipline over ceremonial practices
- Agile disciplines help programmers ensure their software is safe and reliable, reducing the risk of serious errors that could have severe consequences.

### Reasonable Customer Expectations

- Agile aims to meet reasonable customer expectations by ensuring:
  - High-quality software with minimal defects.
  - Continuous technical readiness, meaning the software can be deployed at the end of each iteration.
  - Stable productivity over the course of the project to avoid the common pattern of declining efficiency as projects progress.
- Agile practices promote a sustainable work pace to prevent burnout and encourage collective ownership to avoid knowledge silos.
- Agile supports ongoing improvement and adaptation.

### The Bill of Rights

- Bill of Rights for customers and developers: Emphasizing transparency, mutual respect, and the right to high-quality work.

## 3. Business Practices

### Planning

- Agile planning involves breaking down a project into smaller pieces and estimating those pieces.

#### User Stories and Story Points

- User stories are simple descriptions of a feature from the user's perspective.
- They are written on index cards to keep them concise and flexible.

#### Iteration Planning

- Each iteration starts with an Iteration Planning Meeting, where the team estimates their capacity and selects stories to work on.
- The goal is to focus on delivering complete stories, not just individual tasks.

#### INVEST Stories

- Good user stories should adhere to the INVEST criteria, meaning they are Independent, Negotiable, Valuable, Estimable, Small, and Testable.

#### Story Estimation

- Some techniques to estimate are Flying Fingers and Planning Poker.
- If estimates vary widely among team members, further discussion is encouraged to reach a consensus.
- Stories that are too unclear or large may be split or require further research.

#### Iteration and Release

- It's preferable to have a few stories fully done than many partially completed.
- At the end of each iteration, teams present a demo to stakeholders, showcasing completed features and passing acceptance tests.
- A rising or falling velocity can indicate issues like story point inflation or declining code quality.
- Teams aim to release as often as possible, ideally after every change.

### Acceptance Test

- These are tests written from the user's perspective to validate that the implemented features meet the desired requirements.
- Acceptance tests are a key component in defining what "done" means for a user story, and they are written before development begins to guide the implementation.

### Whole Team

- All members of the project team (developers, testers, business analysts, etc.) work together in close collaboration.
- This reduces communication barriers, improves efficiency, and encourages a shared sense of responsibility for the project's success.

## 4. Team Practices

### Methapor

- Using a common language and shared metaphors helps improve communication within the team

### Sustainable Pace

- Emphasizes the importance of working at a sustainable speed to avoid burnout and maintain long-term productivity.
- Overworking can lead to mistakes and burnout, which are detrimental to both individuals and projects​.

### Collective Ownership

- The entire team shares ownership of the codebase, which encourages collaboration and reduces knowledge silos.
- This approach helps in maintaining quality as all team members can contribute to and improve any part of the project​.

### Continuous Integration

- Encourages frequent integration of code changes to detect issues early and ensure a stable codebase.
- Promotes automated testing and immediate feedback, which helps maintain the quality of the software being developed.

### Standup Meetings

- Short, regular meetings where team members share their progress, plans, and any obstacles they face.
- These meetings are designed to keep everyone on the same page and address issues quickly​.

## 5. Technical Practices

### Test-Driven Development

- TDD emphasizes writing test cases before writing the corresponding production code.
- Ensures that every feature is defined by its tests, providing a clear path from specification to implementation​.
- The primary benefit of TDD is to give developers the courage to make changes without fear of breaking the system, as the tests act as a safety net​.
- TDD follows a Red/Green/Refactor cycle: write a failing test (Red), write just enough code to pass the test (Green), and then refactor the code for improvement without changing its behavior (Refactor)​.

### Refactoring

- Refactoring involves improving the internal structure of the code without changing its external behavior. This practice is essential to keep the codebase clean, maintainable, and adaptable.
- Regular refactoring helps prevent code rot and allows the code to evolve gracefully as new features are added or requirements change.

### Simple Design

- The principle of Simple Design focuses on creating the simplest possible solution that works. This involves avoiding unnecessary complexity and ensuring that the code is straightforward and easy to understand​.
- Simple Design is guided by four rules: the code must pass all tests, reveal intent clearly, avoid duplication, and contain the fewest number of elements necessary to solve the problem.

### Pair Programming

- In Pair Programming, two developers work together at one workstation. One writes the code (the driver), while the other reviews each line as it's written (the navigator).
- This collaboration helps improve code quality and spreads knowledge throughout the team​.
- Pair Programming encourages constant code review, leading to fewer defects and better design. It also facilitates knowledge sharing, making the team more resilient to personnel changes.
