# The Pragmatic Programmer: 20th Anniversary Edition (2019)

## From the Preface to the First Edition

### What Makes a Pragmatic Programmer?

- **Early Adopter/Fast Adapter**: Quickly understands and integrates new technologies.
- **Inquisitive**: Asks questions and gathers facts.
- **Critical Thinker**: Questions norms and vendor promises.
- **Realistic**: Understands the difficulty and time required for tasks.
- **Jack of All Trades**: Familiar with a broad range of technologies; can adapt to new areas.

```
Tip 1: Care About Your Craft
- Aim for excellence in software development.
```

```
Tip 2: Think! About Your Work
- Continuously critique and think about your work.
```

## Chapter 1: A Pragmatic Philosophy

### Topic 1: It's your Life

- You control your life and your career.
- Embrace Change: Ask, "Why can't you change it?"

```
Tip 3: You Have Agency
- Improve your work environment or find a new one.
- Study new technologies in your own time.
- Leverage the industry's opportunities.
```

### Topic 2: The Cat Ate My Source Code

- Take responsability.
- Admit ignorance and mistakes.
- Things go wrong despite testing and planning.
- Be honest and direct about shortcomings.
- Depend on and be dependable to team members (build trust!).

```
Tip 4: Provide Options, Don't Make Lame Excuses
- Think through your reasons before presenting them.
- Offer solutions instead of excuses.
```

### Topic 3: Software Entropy

- Despite plans and quality work, projects can deteriorate over time due to psychological or cultural issues.
- Neglecting small issues (like a broken window) leads to a sense of abandonment and accelerates decay.
- Ignoring problems creates a sense of hopelessness that spreads among team members.

```
Tip 5: Don’t Live with Broken Windows:
- Address problems immediately to prevent further damage.
- If immediate fixes aren't possible, take temporary measures to mitigate issues.
```

- Clean and maintain the system to avoid software rot (aka _tech debt_).
- In crises, avoid causing additional damage (collateral damage).

### Topic 4: Stone Soup and Boiled Frog

- Start small, show progress, and gradually gain support for the complete solution.

```
Tip 6: Be a Catalyst for Change
- Start with modest proposals to inspire and involve others gradually.
```

- Don’t ignore gradual changes in projects; keep the big picture in mind to avoid slow, unnoticed degradation.

```
Tip 7: Remember the Big Picture
- Continuously review the overall direction and context, not just immediate tasks.
```

### Topic 5: Good-Enough Software

- Strive for software that is "good enough" to meet user needs, future maintainers, and personal satisfaction.
  - _Good enough_ does not mean poor quality. It must still meet user requirements and basic standards (performance, privacy, security).

```
Tip 8: Make Quality a Requirements Issue
- Discuss scope and quality as part of system requirements.
- Users may prefer functional software now over a perfect version later.
```

- User feedback on early versions can lead to a better final product.
- Accept that no software can be perfect. Avoid unnecessary embellishments and move on to the next task.

### Topic 6: Your Knowledge Portfolio

- Knowledge and experience are crucial but expiring assets in the fast-evolving tech world.
- Managing Your Knowledge Portfolio
  - Invest Regularly: Make continuous learning a habit.
  - Diversify: Broaden your knowledge across various technologies and non-technical skills.
  - Manage Risk: Balance learning between low-risk, established tech and high-risk, emerging tech.
  - Buy Low, Sell High: Learn new technologies early for potential high rewards.
  - Review and Rebalance: Periodically update and shift focus in your learning.

```
Tip 9: Invest Regularly in Your Knowledge Portfolio
- Consistent investment in learning is key to career success.
```

- Take on questions you can’t answer as opportunities to learn.

```
Tip 10: Critically Analyze What You Read and Hear
- Always verify information and analyze sources critically.
- Ask the "Five Whys": Dig deep into issues by asking "why" repeatedly.
- Who Benefits?: Follow the money to understand underlying interests.
- Context Matters: Consider the specific context and prerequisites of advice or practices.
- Second-Order Thinking: Think about the long-term consequences.
```

### Topic 7: Communicate!

- Effective communication is crucial for sharing ideas and making them impactful.

```
Tip 11: English is Just Another Programming Language
- Treat natural language with the same principles as code (clarity, precision, and structure).
```

- Effective Communication Strategies

  - Know Your Audience: Tailor your message to the audience’s needs and capabilities.
  - Know What You Want to Say: Plan and outline your communication to convey your message clearly.
  - Choose Your Moment: Present ideas at appropriate times considering the audience’s current context and priorities.
  - Choose a Style: Adapt your communication style to suit the audience’s preferences and expertise level.
  - Make It Look Good: Use good presentation practices for written documents; ensure clarity and professionalism.

- Engage your audience with early drafts and feedback to improve communication and build relationships.
- Actively listen and encourage dialogue to enhance understanding and engagement.
- Respond promptly to maintain communication and show consideration.

```
Tip 12: It’s Both What You Say and the Way You Say It
- Effective communication increases your influence and impact.
```

```
Tip 13: Build Documentation In, Don’t Bolt It On
- Integrate documentation into the development process.
- Use code comments to explain why things are done, not how.
- Avoid redundant comments; focus on explaining design decisions and trade-offs.
```

## Chapter 2: A Pragmatic Approach

### Topic 8: The Essence of Good Design

```
Tip 14: Good Design Is Easier to Change Than Bad Design
- The essence of good design is adaptability.
- ETC Principle: Easier to Change (ETC) should guide design decisions.
```

- Good design adapts to user needs through ease of change.
- Consciously evaluate if your actions make the system easier to change.
- Ask yourself if recent changes improved adaptability.

### Topic 9: DRY - The Evils of Duplication

- Maintenance should be seen as an integral part of development, not just post-release fixes.

```
Tip 15: DRY—Don’t Repeat Yourself
- Every piece of knowledge should have a single, authoritative representation in the system.
- Avoid expressing the same thing in multiple places to prevent contradictions and errors.
```

- DRY applies to all forms of knowledge, not just code. It includes documentation, data structures, and even project discussions.
- Promote strong team communication, code reviews, shared utility libraries, and documentation.

```
Tip 16: Make It Easy to Reuse
- Create an environment where finding and reusing existing code is simpler than writing new code.
- Encourage team collaboration and create accessible repositories for common utilities and scripts.
```

### Topic 10: Orthogonality

- Localized changes simplify development and testing.
- Promotes reuse of independent components.
- Isolates diseased code sections to minimize the spread of issues.
- Simplifies testing and makes the system less fragile.

```
Tip 17: Eliminate Effects Between Unrelated Things
- Design self-contained components with clear purposes.
```

- Write shy code that doesn’t reveal unnecessary details or rely on other modules’ implementations.
- Use local contexts or parameters instead of global variables (avoid _global data_).
- Refactor to eliminate duplicate code structures.

### Topic 11: Reversibility

- Use principles like DRY, decoupling, and external configuration to reduce the impact of critical decisions.
- Design systems so that components like databases can be swapped with minimal changes.
- Maintain flexibility in architecture, deployment, and vendor integration to adapt to changing requirements.

```
Tip 18: There Are No Final Decisions
- Treat decisions as written in sand, not stone.
- Be prepared for change and build flexibility into your projects.
```

- Architecture best practices evolve rapidly, from big iron to serverless applications.

```
Tip 19: Forgo Following Fads
- Avoid chasing every new trend.
- Build systems that can adapt to changes and withstand evolving practices.
```

### Topic 12: Tracer Bullets

- Prioritize critical and uncertain areas first to test overall system interactions early.

```
Tip 20: Use Tracer Bullets to Find the Target
- Implement a basic, functional path through the system to validate integration and reduce risk.
```

- Advantages of Tracer Code
  - Immediate Feedback: Operates in the same environment as the final system for real-time adjustment.
  - User Engagement: Provides early, visible progress to users, fostering their involvement and feedback.
  - Structured Development: Establishes a framework for adding new features incrementally.
  - Integration Platform: Continuous integration allows for regular updates and testing, avoiding big-bang integration.
  - Progress Measurement: Easier to track and demonstrate progress through small, manageable steps.
  - Demo Readiness: Always have something functional to demonstrate to stakeholders.

### Topic 13: Prototypes and Post-it Notes

- Prototype particular aspects of a project to reduce risk and allow for early correction.
- Could be simple code to explore functionality, or Post-it notes, whiteboards, or mock-ups for UI and workflow.

```
Tip 21: Prototype to Learn
- Use prototypes to explore uncertain elements and gain insights.
```

- Clearly communicate that prototype code is disposable and incomplete (set the right expectations and avoid misinterpretation).

### Topic 14: Domain Language

```
Tip 22: Program Close to the Problem Domain
- Write code using the vocabulary of the application domain.
```

- Use Off-the-Shelf External Languages (prefer YAML, JSON, or CSV to save effort).
- Use host language features where possible to create domain-specific functionality.
- Implement simple functions without heavy metaprogramming to achieve domain language features.

### Topic 13: Estimating

```
Tip 23: Estimate to Avoid Surprises
- Develop estimation skills to anticipate feasibility and resource needs.
```

- Understand the required accuracy of your estimate.
- Choose units that reflect the precision you want to convey:
  - 1–15 days: Quote in days.
  - 3–6 weeks: Quote in weeks.
  - 8–20 weeks: Quote in months.
  - 20+ weeks: Consider avoiding a direct estimate.
- Where Do Estimates Come From?
  - Ask Someone Experienced: Leverage past experiences from similar situations.
  - Grasp the scope and context before estimating.
  - Create a mental or mathematical model to understand the problem.
  - Break the Model into Components.
  - Assign Values to Parameters: Focus on parameters with the most significant impact.
  - Hedge your answers with different scenarios.
  - Record estimates and compare them with actual outcomes.
- Provide optimistic, most likely, and pessimistic estimates.

```
Tip 24: Iterate the Schedule with the Code
- Update your schedule based on progress and experience in each iteration.
```

- Responding to Estimate Requests: _“I’ll get back to you.”_.

## Chapter 3: The Basic Tools

### Topic 16: The Power of Plain Text

```
Tip 25: Keep Knowledge in Plain Text
- Store information in a format that is easily readable and editable by humans and machines.
```

- Plain text should be comprehensible to humans, not just printable characters.
- Even with advanced technologies, the simplicity of plain text ensures continued relevance and usability.
- Utilizing plain text for knowledge storage and manipulation ensures durability, flexibility, and compatibility with a wide range of tools and technologies.

### Topic 17: Shell Games

- Command shells allow extensive automation and customization.

```
Tip 26: Use the Power of Command Shells
- Gain familiarity with the command shell to enhance productivity.
```

- Combine tools using pipes, launch applications, debug, browse, edit, and filter output.
- Program the shell to build complex macro commands for repetitive tasks, increasing efficiency.
- GUI interfaces are limited to the capabilities their designers intended, restricting automation and tool combination.

### Topic 18: Power Editing

```
Tip 27: Achieve Editor Fluency
- Aim to become fluent with your editors to enhance productivity and thought flow.
```

- Fluency reduces the cognitive load of editing mechanics, allowing your thoughts to flow directly into your code, improving overall programming efficiency.
- Observe your editing habits and identify repetitive actions.
- Repetition is key. Consciously use new features many times a day until they become instinctive.

### Topic 19: Version Control

```
Tip 28: Always Use Version Control
- Use VCS for all projects, regardless of size or duration.
```

- Benefits of using a version control includes:

  - Undo and Redo
  - Change Tracking
  - Release Management
  - Concurrent Work

- Apply VCS to everything you type, including documentation, scripts, and configuration files.
- Using version control systems effectively transforms project management, enhances collaboration, and provides a safety net for managing changes and recovering from mistakes.

### Topic 20: Debugging

- Embrace debugging as a technical challenge rather than a blame game, and adopt a systematic approach to locate and resolve bugs.

```
Tip 29: Fix the Problem, Not the Blame
- Focus on solving the issue rather than assigning blame.
```

```
Tip 30: Don’t Panic
- Stay composed and systematically analyze the issue.
```

```
Tip 31: Failing Test Before Fixing Code
- Create a failing test to isolate the bug and inform the solution.
```

```
Tip 32: Read the Damn Error Message
- Carefully read error messages to identify the issue.
```

- Use a divide-and-conquer approach to narrow down the source of the problem.
- Use tracing statements to log diagnostic messages and track program state over time.
- Explain the problem to someone (or something) else to gain new insights.

```
Tip 33: “select” Isn’t Broken
- Assume the issue lies within your code unless proven otherwise.
```

```
Tip 34: Don’t Assume It—Prove It
- Verify assumptions through testing and evidence.
```

### Topic 21: Text Manipulation

```
Tip 35: Learn a Text Manipulation Language
- Mastering a text manipulation language can significantly enhance your productivity.
- The ability to rapidly test and iterate on ideas is crucial for experimenting and refining concepts.
```

### Topic 22: Engineering Daybooks

- Use daybooks as a place to store ideas that are not immediately relevant, helping you stay focused on current tasks without losing track of your thoughts.
- Use a physical notebook to jot down notes, ideas, and sketches related to your work.
- Writing by hand can engage your brain differently compared to typing, fostering creativity and better retention of information.

## Chapter 4: Pragmatic Paranoia

```
Tip 36: You Can’t Write Perfect Software
-  Accept it. Embrace it. Celebrate it. Because perfect software doesn’t exist.
```

### Topic 23: Design by Contract

- DBC is a method where software functions and methods have well-defined contracts that specify:
  - Preconditions: What must be true for the routine to be called.
  - Postconditions: What the routine guarantees after execution.
  - Class Invariants: Conditions that must always hold true for a class, from the perspective of the caller.

```
Tip 37: Design with Contracts
- Ensure that all routines meet their preconditions, postconditions, and class invariants.
```

- Assertions can partially implement DBC by enforcing logical conditions at runtime.
- Semantic invariants are fundamental truths about a system that must always hold.

### Topic 24: Dead Programs Tell No Lies

- Adopt a defensive coding strategy, ensuring data integrity and proper version control.

```
Tip 38: Crash Early
- Detect problems as soon as possible and crash early to avoid further damage.
```

- When an "impossible" event occurs, terminate the program to prevent further damage.
- Embrace errors as opportunities to improve the robustness and reliability of your programs

### Topic 25: Assertive Programming

- Avoid assumptions such as "This application will never be used abroad, so why internationalize it?", "Count can’t be negative.", "Logging can’t fail.", etc, and ensure that we validate our expectations explicitly.

```
Tip 39: Use Assertions to Prevent the Impossible
- They verify that certain conditions are met in our code, providing a safeguard against unexpected behaviors.
```

### Topic 26: How to Balance Resources

```
Tip 40: Finish What You Start
- The function or object that allocates a resource should be responsible for deallocating it
```

```
Tip 41: Act Locally
- When in doubt, reduce the scope of resource usage.
```

- Build code that checks resources are freed appropriately.

### Topic 27: Don’t Outrun Your Headlights

- Check for feedback frequently to avoid making predictions about an uncertain future.

```
Tip 42: Take Small Steps—Always
- Always take small, deliberate steps, checking for feedback and adjusting before proceeding.
```

- Avoid tasks that require "fortune-telling," such as estimating completion dates months in the future or guessing future tech availability.
- Make code replaceable to handle changes effectively, enhancing cohesion, coupling, and DRY principles.

```
Tip 43: Avoid Fortune-Telling
- Avoid making predictions about the future, as unexpected, high-impact events ("black swans") can dramatically alter the landscape.
```

## Chapter 5: Bend, or Break

### Topic 28: Decoupling

- Decoupling ensures flexibility, allowing individual components to change independently.

```
Tip 44: Decoupled Code Is Easier to Change
- Code that is decoupled is easier to modify without causing issues in other parts of the system.
```

- Symptoms of coupling include wacky dependencies, propagation of simple changes through unrelated modules, developer fear of changing code, and mandatory all-hands meetings for changes.
- Method chains (train wrecks) introduce implicit knowledge and make changes difficult.

```
Tip 45: Tell, Don’t Ask
- Don’t make decisions based on an object's internal state and then update the object. Instead, delegate the responsibility to the object itself.
```

- The Law of Demeter (LoD) suggests limiting the scope of method calls to methods of the current object, its parameters, created objects, and global variables. Simplify this by avoiding chaining method calls with more than one dot.

```
Tip 46: Don’t Chain Method Calls
- Avoid chaining method calls beyond one level of depth to minimize coupling and dependencies.
```

- Global data creates hidden dependencies, making code harder to maintain and test. Avoid using global variables and singletons; instead, encapsulate data within controlled interfaces.

```
Tip 47: Avoid Global Data
- Avoid global data to reduce hidden dependencies and make the codebase more modular and testable.
```

```
Tip 48: If It’s Important Enough to Be Global, Wrap It in an API
- Always wrap resources behind code that you control.
```

- Misuse of subclassing introduces coupling through inherited state and behavior, making code changes risky.

### Topic 29: Juggling the Real World

- Applications must be responsive to a constantly changing environment, handling events effectively to remain functional and interactive.
- Applications that respond to events are more interactive and resource-efficient.
- Strategies to Handle Events:
  - Finite State Machines (FSM): A specification of how to handle events with a set of states and transitions based on events.
  - The Observer Pattern: Involves an observable source of events and multiple observers interested in those events.
  - Publish/Subscribe (Pub/Sub): Generalizes the observer pattern by decoupling publishers and subscribers via channels.
  - Reactive Programming and Streams: Treats events as collections of data, allowing manipulation, combination, and filtering.
- Design code to be responsive to real-world events.

### Topic 30: Transforming Programming

- Focus on programs as transformations of input data to output, simplifying design, structure, error handling, and reducing coupling.

```
Tip 49: Programming Is About Code, But Programs Are About Data
- Emphasize transforming data to achieve program goals.
```

- Start with the requirement and determine its inputs and outputs.
- Break down the process into a series of transformation steps.

```
Tip 50: Don’t Hoard State; Pass It Around
- Emphasize passing data through transformations rather than encapsulating it in objects.
```

- Use a wrapper to indicate valid or error states.
- Handle errors inside transformations or defer function calls until previous steps succeed.
- Viewing code as a series of transformations leads to cleaner, more maintainable, and less coupled designs.

### Topic 31: Inheritance Tax

- Avoid using inheritance in object-oriented programming; consider alternatives like interfaces, delegation, and mixins.

```
Tip 51: Don’t Pay Inheritance Tax
- Inheritance introduces unnecessary complexity and coupling; avoid it when possible.
```

- Interfaces and protocols, delegation, and mixins are powerful alternatives to inheritance, providing flexibility and reducing coupling.

```
Tip 52: Prefer Interfaces to Express Polymorphism
- Interfaces provide polymorphism without the drawbacks of inheritance.
```

```
Tip 53: Delegate to Services: Has-A Trumps Is-A
- Delegate responsibilities to services to avoid tight coupling and maintain control over APIs.
```

```
Tip 54: Use Mixins to Share Functionality
- Mixins allow sharing of functionality without the complexity of inheritance.
```

- Avoid dragging unnecessary dependencies (the whole jungle) along with your design decisions.

### Topic 32: Configuration

- Externalize configuration values that may change after deployment or are environment-specific.

```
Tip 55: Parameterize Your App Using External Configuration
- External configuration makes your code adaptable to different environments and requirements.
```

- Avoid making configuration data globally accessible; instead, wrap it in a thin API to decouple the code from the configuration details.
- Dynamic configuration is crucial for highly available applications, enabling real-time updates without downtime.
- Code that relies on hard-coded values or lacks external configuration (Dodo-Code) is inflexible and non-adaptable.

## Chapter 6: Concurrency

### Topic 33: Breaking Temporal Coupling

- Avoiding temporal coupling increases flexibility and responsiveness.
- Use activity diagrams to capture and analyze workflows, identifying potential concurrency.

```
Tip 56: Analyze Workflow to Improve Concurrency
- Identify activities that can be performed in parallel to enhance efficiency.
```

- Concurrency should be exploited for activities that take time but not processing time (e.g., querying a database, accessing external services, waiting for user input).
- Concurrency is a software mechanism; parallelism is a hardware concern.
- Use multiple processors to handle independent tasks in parallel, reducing overall time.

### Topic 34: Shared State Is Incorrect State

- Shared state leads to inconsistencies and unexpected behavior in concurrent environments.
- Shared state leads to race conditions where multiple entities access and modify the same resource.

```
Tip 57: Shared State Is Incorrect State
- Avoid shared state to prevent inconsistencies and race conditions.
```

- Semaphores control access to shared resources by allowing only one process to access the resource at a time.
- Centralize control by making resource access atomic.

```
Tip 58: Random Failures Are Often Concurrency Issues
- Concurrency problems can cause unpredictable errors; manage them carefully.
```

### Topic 35: Actors and Processes

```
Tip 59: Use Actors For Concurrency Without Shared State
- Actors handle concurrency without the complexities of shared state.
- No central control or shared state.
- Messages are one-way; actors communicate by sending messages to each other's mailboxes.
- Actors process one message at a time, ensuring no shared state conflicts.
```

- Actors handle concurrency implicitly by processing messages independently.

### Topic 36: Blackboards

- A blackboard system facilitates collaboration and problem-solving by allowing independent agents to read and write information on a shared board.

```
Tip 60: Use Blackboards to Coordinate Workflow
- Blackboard systems help coordinate workflows by allowing different agents to contribute and process shared information.
- Detectives (agents) do not need to know about each other’s existence (They have different expertise and work independently).
- Information can be posted in any form: text, images, physical evidence, etc.
- The system evolves organically as contributions are made.
```

## Chapter 7: While You Are Coding

### Topic 37: Listen to Your Lizard Brain

```
Tip 61: Listen to Your Inner Lizard
- Pay attention to your instincts, which can alert you to potential issues in your code.
```

- Prototyping is a useful technique to overcome the fear of the blank page and to explore ideas freely.
- Externalize the problem by doodling, explaining it to a coworker, or using a rubber duck.
- Look for patterns in unfamiliar code to understand the original author's decisions.
- Analyze uneasy feelings about a design or requirement to prevent future problems.

### Topic 38: Programming by Coincidence

- Aim for deliberate and intentional programming to prevent false conclusions and unexpected failures.

```
Tip 62: Don’t Program by Coincidence
- Be Aware: Understand and be conscious of your coding decisions.
- Explain the Code: If you can’t explain your code to a junior programmer, you might be relying on coincidences.
- Don’t Code in the Dark: Avoid using technologies or writing code you don’t fully understand.
- Plan: Whether it’s in your head or on paper, have a plan.
- Rely on Reliable Things: Only depend on well-documented and tested components.
- Document Assumptions: Clearly state and test your assumptions.
- Test Assumptions: Use assertions to verify assumptions in your code.
- Prioritize Effort: Focus on important aspects and be ready to refactor.
- Don’t Be a Slave to History: Don’t let existing code dictate future decisions; be prepared to make necessary changes.
```

- Understand and be conscious of your coding decisions.

### Topic 39: Algorithm Speed

```
Tip 63: Estimate the Order of Your Algorithms
- Use Big-O notation to understand the growth of time or space requirements as input size increases.
```

```
Tip 64: Test Your Estimates
- Validate your theoretical estimates with practical tests.
- Relationships are often not linear; some algorithms have significantly worse performance as input size increases.
```

- Common Big-O notations:
  - O(1): Constant time
  - O(log 𝑛): Logarithmic time (e.g.: Algorithms halving the input each iteration)
  - O(𝑛): Linear time (e.g.: Most loops running from 1 to 𝑛)
  - O(𝑛 log 𝑛): Log-linear time (e.g.: Algorithms partitioning input and processing each part recursively, like quicksort)
  - O(𝑛^2): Quadratic time (e.g.: Most two nested loops)
  - O(𝑛^3): Cubic time
  - O(2^𝑛): Exponential time
- Ensure an algorithm is a true bottleneck before optimizing.

### Topic 40: Refactoring

- Software development is more akin to gardening: organic, adaptive, and continuous.
- Refactoring, as defined by Martin Fowler, is a disciplined technique for restructuring an existing body of code, altering its internal structure without changing its external behavior.
  - Disciplined: It is a methodical process, not a chaotic rewrite.
  - No change in external behavior: The functionality remains the same; only the internal structure is improved.
- Refactor when you've learned something new, when requirements change, or when you notice code smells.
- Delaying refactoring can lead to greater time investment later due to increased dependencies and code complexity.

```
Tip 65
- Refactor Early, Refactor Often
```

- Refactoring should be slow, deliberate, and careful.
- Ensure refactoring doesn’t introduce new bugs by running tests frequently.
- Follow a disciplined approach to refactoring to maintain code quality and functionality.

### Topic 41: Test to Code

```
Tip 66: Testing Is Not About Finding Bugs
- The true benefit of testing isn't just in finding bugs but in the thought process it encourages.
```

```
Tip 67: A Test Is the First User of Your Code
- A test can serve as the first user of your code, providing immediate feedback and helping you catch issues early.
```

- TDD is a methodology where you write tests before writing the actual code. This practice ensures that you always have tests for your code and encourages a design that is easy to test.
- Maintain a balance between writing tests and keeping an eye on the big picture.
  - While TDD has many benefits, it's important not to become a slave to the process.

```
Tip 68: Build End-to-End, Not Top-Down or Bottom-Up
- Traditional design methods like top-down and bottom-up are flawed because they assume you know all the requirements up front.
- Building software incrementally allows you to learn and adapt as you go.
```

- Software components should be designed to be tested easily, similar to how hardware components are tested.
- Unit testing should be viewed as testing against the contract of the code.
- Ad hoc testing involves manually testing your code using various inputs and checking outputs.

```
Tip 70: Test Your Software, or Your Users Will
- Adopting a culture of testing ensures that all tests pass consistently.
```

### Topic 42: Property-Based Testing

```
Tip 71: Use Property-Based Tests to Validate Your Assumptions
- Use property-based testing to automate testing based on defined contracts and invariants to validate code behavior without shared preconceptions.
```

- Property-based testing frameworks generate a wide range of test data to ensure thorough validation.
- Enhance unit testing with complementary unit testing by focusing on invariants and contracts, leading to better code design and fewer edge cases.

### Topic 43: Stay Safe Out There

- Analyze potential internal errors and external threats, considering all ways the system can be compromised.

```
Tip 72: Keep It Simple and Minimize Attack Surfaces
- Reduce the number of access points where attackers can enter or extract data.
```

- Use the least amount of privilege necessary for the shortest time possible.
- Default settings should prioritize security over convenience.
- Never store sensitive data in plain text.

```
Tip 73: Apply Security Patches Quickly
- Maintain Security Updates: Regularly apply security patches to all systems and devices.
```

- Rely on well-vetted, open-source libraries for encryption and other security measures instead of creating your own solutions.
- Consider using third-party authentication providers to enhance security and reduce the burden on your development team.

### Topic 44: Naming Things

- Write meaningful names that reflect the role they play in the code.
- Names should clarify the code's functionality, making it easier to read and understand.
- Follow the naming conventions and culture of the programming language or environment to avoid jarring inconsistencies.

```
Tip 74: Name Well; Rename When Needed
```

## Chapter 8: Before the Project

### Topic 45: The Requirements Pit

- Programmers help clients understand what they want by interpreting their needs and providing feedback, initiating an exploratory process.

```
Tip 75: No One Knows Exactly What They Want
- Requirements rarely lie on the surface; they are buried under layers of assumptions and politics.
```

- Requirements gathering is an ongoing feedback loop where programmers help refine clients' needs through prototypes and mockups.

```
Tip 76: Programmers Help People Understand What They Want
- The initial statement of need is an invitation to explore, not an absolute requirement.
```

```
Tip 77: Requirements Are Learned in a Feedback Loop
- Generate feedback to help clients refine their thinking and understand the consequences of their requirements.
```

- Use user stories and a project glossary to ensure clarity and consistency.
- Keep requirements abstract and simple, focusing on the business need.

```
Tip 78: Work with a User to Think Like a User
- Spend time in the client's environment to gain insights and build trust.
```

```
Tip 79: Policy Is Metadata
- Implement the general case with policy information as metadata, allowing for easy updates when policies change.
```

```
Tip 80: Use a Project Glossary
```

### Topic 46: Solving Impossible Puzzles

- Distinguish between absolute constraints and preconceived notions.
- Enumerate all possible solutions without dismissing any initially.
- If a problem seems insurmountable, take a break or work on something different.
- Discuss the problem with someone else.
- Provide your subconscious with plenty of raw material by reflecting on what works and what doesn’t.

```
Tip 81: Don’t Think Outside the Box — Find the Box
- Identify the real constraints of a problem, as this helps in finding the true solution space.
```

### Topic 47: Working Together

- Pair programming and mob programming are effective methods to achieve close collaboration.
- Team communication structures influence software design, as per Conway's Law.

```
Tip 82: Don’t Go into the Code Alone
- Collaborate with others to enhance problem-solving and code quality.
```

- Focus on building code rather than egos, start small, criticize the code not the person, listen to others, and conduct frequent retrospectives.

### Topic 48: The Essence of Agility

- Agility is about how you do things, not a specific set of practices.
- There can't be a fixed agile process because agility involves constantly responding to change and feedback.
- Agility relies on a continuous feedback loop: assess current state, make small meaningful changes, evaluate outcomes, and adjust as necessary.

```
Tip 83: Agile Is Not a Noun; Agile Is How You Do Things
- Focus on adapting and responding to feedback rather than following a fixed plan.
```

### Chapter 9: Pragmatic Projects

### Topic 49: Pragmatic Teams

```
Tip 84: Maintain Small, Stable Teams
- A pragmatic team is small (under 10-12 members) and stable, with members rarely changing. Trust and dependency among team members are crucial.
```

- Quality should be a collective responsibility, with all team members actively ensuring no "broken windows" are left unfixed.
- Teams must stay vigilant to changes in project scope, requirements, and environment to avoid gradually getting overwhelmed.

```
Tip 85: Schedule It to Make It Happen
- Schedule time for maintenance, process improvement, new technology experiments, and skill development to foster continuous improvement.
```

- Avoid duplication of effort by maintaining frictionless communication and awareness within the team.
- Implement features through a tracer bullet approach, ensuring all necessary skills are present within the team to handle different aspects of the project.
- Automate repetitive tasks to ensure consistency and reliability in development and deployment.

```
Tip 86: Organize Fully Functional Teams
```

### Topic 50: Coconuts Don’t Cut It

```
Tip 87: Do What Works, Not What’s Fashionable
- Adopt methods that fit your unique situation rather than blindly copying popular companies like Spotify or Netflix.
```

- Pilot new ideas, keep what works, and discard what doesn’t. Continuous adaptation is key.
- No single methodology fits all; combine the best parts from various approaches to suit your needs.

```
Tip 88: Deliver When Users Need It
- Aim for continuous delivery by progressively shortening your delivery cycle and establishing a solid infrastructure.
```

### Topic 51: Pragmatic Starter Kit

- Make tasks like build, release, testing, and documentation automatic and repeatable to ensure consistency and avoid manual errors.

```
Tip 89: Use Version Control to Drive Builds, Tests, and Releases
- Use version control to manage everything needed for your project, driving builds, tests, and releases automatically.
```

```
Tip 90: Test Early, Test Often, Test Automatically
- Test early, often, and automatically to catch bugs as soon as possible.
```

```
Tip 91: Coding Ain’t Done ’Til All the Tests Run
```

```
Tip 92: Use Saboteurs to Test Your Testing
```

```
Tip 93: Test State Coverage, Not Code Coverage
```

```
Tip 94: Find Bugs Once
- Whenever a bug is found, add a test for it to ensure it doesn’t happen again.
```

### Topic 52: Delight Your Users

- Focus on the business problems your users need solving, not just on delivering software.
- Ask how success will be measured after project completion.
- Ensure the entire team understands user expectations and make decisions that move towards those goals.

```
Tip 96: Delight Users, Don’t Just Deliver Code
- As your domain knowledge grows, proactively suggest improvements that can further address user needs.
```

### Topic 53: Pride and Prejudice

- Take pride in your work, but avoid becoming territorial. Treat others' code with respect.
- Anonymity can lead to poor code quality and lack of accountability.
- Code can be owned by a team rather than an individual, with practices like pair programming to maintain quality.
- Your signature on code should signify high quality, solid, well-written, tested, and documented work.

```
Tip 97: Sign Your Work
- Artisans of an earlier age were proud to sign their work. You should be, too.
```

## Chapter 10: Postface

```
Tip 98: First, Do No Harm
- No one is perfect; everyone misses things now and then.
```

```
Tip 99: Don’t Enable Scumbags
```

```
Tip 100: It’s Your Life. Share it. Celebrate it. Build it. AND HAVE FUN!
```
