# The Pragmatic Programmer

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

- Misuse of subclassing introduces coupling through inherited state and behavior, making code changes risky.
