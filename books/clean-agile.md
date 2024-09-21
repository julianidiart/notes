# Clean Agile by Robert C. Martin (2019)

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

## 5. Technical Practices

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

## 6. Becoming Agile

### Agile Values

- There are four core values essential to Agile:
  1. Courage: Teams must maintain high code quality and discipline, even when facing pressures to cut corners for political safety.
  2. Communication: Effective communication within the team and with external stakeholders is crucial. Informal communication helps strengthen team bonds and stakeholder relationships.
  3. Feedback: Agile practices provide rapid feedback, allowing teams to quickly identify and correct issues. This feedback loop also helps teams learn from their past decisions.
  4. Simplicity: Agile encourages direct solutions, reducing unnecessary complexity both in code and in personal interactions.

### Transformation

- Transitioning to Agile involves a significant shift in values, particularly for large organizations accustomed to traditional management styles focused on safety, consistency, and control.
- Middle management often resists Agile adoption due to its emphasis on direct communication and risk-taking, which contrasts with their traditional roles.
- Agile transformations may also be met with resistance from roles like tech leads or project managers, who may feel their roles are diminished. However, their skills are still crucial in an Agile environment.

### Coaching

- Agile coaches play a vital role in guiding teams through the transition, ensuring adherence to Agile principles.
- Unlike external Agile trainers who might provide short-term training, coaches are typically team members who maintain the Agile way internally.
- Coaching involves asking the right questions to help teams discover how Agile practices can solve their problems, rather than dictating solutions.

#### Coaching—An Alternative View (by Damon Poole)

- Coaching focuses on asking questions and addressing the unique circumstances of each team.
- Effective coaching requires demonstrating the personal benefits of Agile to the team members.
- The goal of coaching is not to prescribe solutions but to reveal blind spots and challenge underlying beliefs.
- An Agile transformation should be conducted iteratively, not as a top-down, project-like initiative.

### Agile in the Large

- Agile was originally designed for small teams but has been adapted for large organizations.
- Techniques like Scrum of Scrums and frameworks such as SAFe (Scaled Agile Framework) and LeSS (Large Scale Scrum) are used to scale Agile practices.
- Managing large teams in software development involves organizing them into smaller, more manageable groups.

### Agile Tools (by Tim Ottinger and Jeff Langr)

- Mastery of both simple and complex tools is essential for software developers, but only tools that provide significant value with minimal learning effort should be chosen.
- Great tools should help achieve objectives, be easy to learn, become transparent in use, allow for adaptation, and be affordable.
- For co-located Agile teams, simple physical tools like sticky notes and whiteboards are effective, but remote teams might require more sophisticated digital tools.
- Complex Agile Lifecycle Management tools should support, not constrain, team processes. The tool should adapt to the team's needs, not the other way around.

## 7. Craftsmanship (by Sandro Mancuso)

### The Software Craftsmanship Manifesto

- Programming is not just a job but a profession that involves pride in well-crafted software.
- The Software Craftsmanship Manifesto builds on the Agile Manifesto, highlighting the importance of well-crafted software, continuous improvement, community, and productive partnerships.
- Craftsmanship Principles:
  - Well-Crafted Software: Emphasizes the importance of producing not just working software but software that is well-crafted, maintainable, and of high quality​(clean-agile).
  - Continuous Value Addition: Focuses on steadily adding value through software development, ensuring that each iteration enhances the product's value​(clean-agile).
  - Community of Professionals: Encourages developers to be part of a community that shares knowledge, best practices, and continually learns from each other​(clean-agile).
  - Productive Partnerships: Stresses the importance of fostering productive relationships between customers and developers, beyond mere collaboration

### Ideologies and Methodologies

- Agile is seen as an ideology with a focus on business agility and customer satisfaction. In contrast, methodologies like Scrum and XP are tools or methods to achieve these goals.
- Craftsmanship, unlike fixed methodologies, promotes a continuous search for better practices and adaptation to meet evolving goals and challenges.
