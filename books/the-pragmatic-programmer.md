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

## A Pragmatic Philosophy

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

## A Pragmatic Approach

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
