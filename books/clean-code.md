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

## Chapter 2: Meaningful Names

### Introduction

- Good naming practices are essential for readability and maintainability.

### Use Intention-Revealing Names

- Names should reveal intent, making code easier to understand.
- A name should indicate why it exists, what it does, and how it is used.
- Example: Change `int d` to `int elapsedTimeInDays` for clarity.

### Avoid Disinformation

- Avoid names that can mislead or obscure the meaning.
- Use consistent and precise naming to avoid confusion.
- Example: Avoid using similar-looking names or abbreviations that can be mistaken.

### Make Meaningful Distinctions

- Names should differ in meaningful ways, not just by adding numbers or noise words.
- Avoid non-informative names like `a1`, `a2`; use `source` and `destination` instead.
- Example: Differentiate classes like `ProductInfo` and `ProductData` clearly.

### Use Pronounceable Names

- Pronounceable names facilitate discussion and improve collaboration.
- Example: Change `genymdhms` to `generationTimestamp` for clarity.

### Use Searchable Names

- Names should be easy to locate in a codebase.
- Avoid single-letter names or numeric constants that are hard to search.
- Example: Use `WORK_DAYS_PER_WEEK` instead of `5`.

### Avoid Encodings

- Don’t use type or scope encodings in names; they add unnecessary complexity.
- Modern IDEs and languages handle types and scopes better.
- Example: Avoid Hungarian Notation like `m_dsc`; use `description` instead.

### Avoid Mental Mapping

- Names should not require mental translation to understand their meaning.
- Example: Avoid single-letter variable names except for loop counters (`i`, `j`).

### Class Names

- Use noun or noun phrase names for classes.
- Example: Use `Customer`, `WikiPage`, `Account`, and `AddressParser`.

### Method Names

- Use verb or verb phrase names for methods.
- Follow JavaBean naming conventions for accessors and mutators (`get`, `set`, `is`).
- Example: `postPayment`, `deletePage`, `save`.

### Don’t Be Cute

- Avoid clever or humorous names that are not self-explanatory.
- Example: Use `deleteItems` instead of `HolyHandGrenade`.

### Pick One Word per Concept

- Use one consistent term for one concept across the codebase.
- Example: Use either `fetch`, `retrieve`, or `get` consistently, not all three.

### Avoid Puns

- Avoid using the same word for different meanings.
- Example: Use `insert` or `append` instead of overloading `add` for different actions.

### Use Solution Domain Names

- Use technical terms from computer science for clarity.
- Example: `JobQueue`, `AccountVisitor`.

### Use Problem Domain Names

- Use domain-specific terms when there are no equivalent technical terms.
- Example: Use names relevant to the problem domain for better understanding.

### Add Meaningful Context

- Provide context through well-named classes, functions, or namespaces.
- Example: Use `Address` class instead of prefixing variable names like `addrFirstName`.

### Don’t Add Gratuitous Context

- Avoid unnecessary prefixes or context in names.
- Example: Use `Address` instead of `GSDAccountAddress`.

### Final Words

- Good naming requires descriptive skills and a shared cultural background.
- Renaming for clarity is beneficial and should not be feared.
