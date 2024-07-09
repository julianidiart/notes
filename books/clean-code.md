# Clean Code (2008)

## Chapter 1: Clean Code

### There Will Be Code

- Growth in domain-specific languages will occur, enhancing but not eliminating code.
- Well-specified requirements act as executable tests for code.
- Code will always be necessary to express requirements precisely.

### Bad Code

- Reasons for writing bad code:
  - Rushing to complete tasks quickly.
  - Pressure from bosses or deadlines.
  - Fatigue or eagerness to move on to other tasks.
  - Overwhelming backlog leading to hasty coding decisions.
- Common experiences:
  - Leaving messy code for another day.
  - Feeling relief when a messy program works, rationalizing that it’s better than nothing.
  - Postponing cleanup, often indefinitely, as per LeBlanc’s law: `Later equals never`.

### The Total Cost of Owning a Mess

- Messy code significantly slows down programmers over time.
- Initial fast-moving teams can slow down to a snail's pace within a year or two.
- Every code change can break multiple parts of the system, making even minor modifications complex.
- The increasing complexity and messiness of the code make it impossible to clean up.
- As the code mess grows, team productivity decreases, approaching zero.
- Management often adds more staff to increase productivity, but new staff lack familiarity with the system's design.
- Increased pressure to boost productivity leads to more messes, further reducing productivity.

#### The Grand Redesign in the Sky

- A "grand redesign" is often demanded, but it can take years and still result in messy code.

#### Attitude

- Blame for messy code often lies with developers, not external factors like management or schedules.
- Professional developers should resist pressure to create messy code to meet deadlines.

#### The Primal Conundrum

- Clean code is essential for meeting deadlines efficiently.

#### The Art of Clean Code?

- Writing clean code requires discipline, techniques, and a sense of "cleanliness" or "code-sense."
- Developers with "code-sense" can transform messy code into clean code through systematic improvements.

#### What Is Clean Code?

> Clean code is elegant, efficient, with minimal dependencies, comprehensive error handling, and performs optimally. Clean code does one thing well.
> _Bjarne Stroustrup_

> Clean code is simple, direct, and reads like well-written prose, clearly exposing the problem and solution without obscuring the designer’s intent.
> _Grady Booch_

> Clean code is readable and easily enhanced by others, with meaningful names, minimal dependencies, and thorough testing. It provides a clear, minimal API.
> _Dave Thomas_

> Clean code shows care and attention to detail, appearing as though nothing more can be done to improve it.
> _Michael Feathers_

> Clean code runs all tests, contains no duplication, clearly expresses design ideas, and minimizes the number of entities. It uses abstractions to simplify code.
> _Ron Jeffries_

> Clean code meets expectations without surprises, making the language seem tailor-made for the problem, and is beautiful in its simplicity and obviousness.
> _Ward Cunningham_

### Schools of Thought

- Like martial arts, different schools of thought exist about clean code, each with its own techniques and teachings.
- While the book presents a specific school of thought, it acknowledges the validity of other approaches and encourages readers to learn from them as well.

### We Are Authors

- Programmers are authors responsible for writing code that communicates well with readers.
- A significant portion of coding involves reading existing code, with a time ratio of over 10:1 for reading vs. writing.
- Most time in coding sessions is spent scrolling, navigating, and contemplating changes, rather than typing.
- Making code easy to read is crucial as it directly impacts the ease of writing new code.

### The Boy Scout Rule

- Apply the principle "leave the campground cleaner than you found it" to code.

### Prequel and Principles

- This book serves as a prequel to "Agile Software Development: Principles, Patterns, and Practices (PPP)" written in 2002.
- References to design principles such as Single Responsibility Principle (SRP), Open Closed Principle (OCP), and Dependency Inversion Principle (DIP) are included.

### Conclusion

- Like art books, it offers insights into techniques and thought processes without promising mastery.
