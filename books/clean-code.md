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

## Chapter 3: Functions

### Small

- Functions should be small.
- Functions should be even smaller than that.

### Blocks and Indenting

- Blocks within if, else, while, etc., should be one line long, ideally a function call.

### Do One Thing

- Functions should do one thing, do it well, and do it only.
- A function should perform actions that are one level of abstraction below its name.

#### Sections within Functions

- Functions that truly do one thing cannot be divided into sections like declarations, initializations, and processing.

### One Level of Abstraction per Function

- Ensure all statements within a function are at the same level of abstraction.

#### Reading Code from Top to Bottom: The Stepdown Rule

- Functions should read like a narrative, with each function followed by those at the next level of abstraction.

### Switch Statements

- Bury switch statements in low-level classes, using them to create polymorphic objects.

### Use Descriptive Names

- Use names that clearly describe the purpose and behavior of functions and variables.
- Names should not require additional context to understand their meaning.

### Function Arguments

- Zero is the ideal number of arguments, one is the second best, two is acceptable but harder, three should be avoided, and more than three requires special justification and should generally be avoided.
- Arguments add complexity and require more mental processing.
- More arguments increase the complexity of testing all combinations.

#### Common Monadic Forms

- Examples:
  - Question: `boolean fileExists(String fileName)`
  - Transformation: `InputStream fileOpen(String fileName)`
  - Event: `void passwordAttemptFailedNtimes(int attempts)`

#### Flag Arguments

- Thi is and ugly practice. Passing a boolean indicates the function does more than one thing.
- Example: Instead of `render(boolean isSuite)`, use `renderForSuite()` and `renderForSingleTest()`.

#### Dyadic Functions

- Use methods or classes to reduce the number of arguments.

#### Triads

- Example of Confusion: `assertEquals(message, expected, actual)` often leads to misinterpretation.

#### Argument Objects

- If a function needs more than two or three arguments, wrap related arguments into an object.
- Example:

```
Circle makeCircle(double x, double y, double radius); // Complex
Circle makeCircle(Point center, double radius); // Simplified
```

#### Argument Lists

- Treat variable arguments as a single argument of type List.
- Examples

```
void monad(Integer... args);
void dyad(String name, Integer... args);
void triad(String name, int count, Integer... args);
```

#### Verbs and Keywords

- A function name combined with its argument should clearly convey the action.
  - Example: `write(name)`
- Encode argument names into the function name for clarity.
  - Example: `assertExpectedEqualsActual(expected, actual)` instead of `assertEquals(expected, actual)`

### Have No Side Effects

- Consequences of Side Effects
  - Temporal Coupling: Functions can only be called at specific times to avoid unintended consequences.
  - Unexpected Behavior: Callers may not expect the function to perform additional actions beyond its stated purpose.
- Ensure the name reflects all actions performed, though this might violate the "Do one thing" principle
- Design functions to perform only their intended task, avoiding hidden state changes.

#### Output Arguments

- Use object-oriented principles to change the state of the owning object rather than using output arguments.
  - Example:

```
public void appendFooter(StringBuffer report) // Ambiguous
report.appendFooter(); // Clear and intuitive
```

### Command Query Separation

- Functions should either do something (command) or answer something (query), but not both.
  - Example:

```
public boolean set(String attribute, String value); // Confusing Function
if (set("username", "unclebob"))... // Ambiguous Usage

// Separate Functions
if (attributeExists("username")) {
  setAttribute("username", "unclebob");
}
```

### Prefer Exceptions to Returning Error Codes

- Using error codes can lead to command query separation violations.
- Error handling with error codes leads to nested if statements.

#### Extract Try/Catch Blocks

- Separate the try/catch blocks into distinct functions for clarity.

#### Error Handling Is One Thing

- Functions should do one thing. If they handle errors, they should do only that.

#### The Error.java Dependency Magnet

- Error enums create dependencies, requiring recompilation and redeployment when modified.
- New exceptions can be added without forcing recompilation or redeployment.

### Don’t Repeat Yourself

- Duplication bloats code and increases maintenance effort.
- Use methods to reduce duplication, enhancing readability and maintainability.

### Structured Programming

- Every function and block should have one entry and one exit.
  - Functions should have only one return statement.
  - Avoid using break or continue in loops.
  - Goto statements should be avoided.

### How Do You Write Functions Like This?

- First drafts often contain nested loops, long argument lists, arbitrary names, and duplicated code.
  - Ensure every line of code is covered by tests.
- Split out functions, rename variables, and eliminate duplication.
- Continuously refine the code while keeping tests passing.

### Conclusion

- Write functions that are short, well-named, and nicely organized.
- Ensure that functions fit cleanly into the language of the system to help tell its story effectively.

## Chapter 4: Comments

- Comments are not inherently good; they are a fallback for when code fails to express intent clearly.
- Code should be self-explanatory, minimizing the need for comments.
- Problems with comments:
  - Comments can become outdated and inaccurate.
  - Keeping comments updated with code changes is challenging.
  - Only the code provides the ultimate truth about what it does.

### Comments Do Not Make Up for Bad Code

- Instead of commenting bad code, refactor it to be more understandable.

### Explain Yourself in Code

- Instead of comments, use meaningful function names.
  - Example:

```
// Instead of this...
// Check to see if the employee is eligible for full benefits
if ((employee.flags & HOURLY_FLAG) && (employee.age > 65))

// Do this..
if (employee.isEligibleForFullBenefits())
```

### Good Comments

#### Legal Comments

- Necessary for copyright and authorship.
  - Example:

```
// Copyright (C) 2003,2004,2005 by Object Mentor, Inc. All rights reserved.
// Released under the terms of the GNU General Public License version 2 or later.
```

#### Informative Comments

- Provide useful information not immediately clear from the code.
  - Example:

```
// Returns an instance of the Responder being tested.
protected abstract Responder responderInstance();
```

#### Explanation of Intent

- Explain the reasoning behind a decision.
  - Example:

```
return 1; // we are greater because we are the right type.
```

#### Clarification

- Translate obscure arguments or return values into something readable.
  - Example:

```
// a == a
// a != b
// ab == ab
// a < b
```

#### Warning of Consequences

- Warn other developers about certain consequences.
- Example:

```
// SimpleDateFormat is not thread safe,
// so we need to create each instance independently.
SimpleDateFormat df = new SimpleDateFormat("EEE, dd MMM yyyy HH:mm:ss z");
```

#### TODO Comments

- Remind about future improvements or changes.
  - Example:

```
// TODO-MdM these are not needed
// We expect this to go away when we do the checkout model
protected VersionInfo makeVersion() throws Exception {
  return null;
}
```

#### Amplification

- Highlight the importance of something that might seem trivial.
  - Example:

```
// the trim is real important. It removes the starting
// spaces that could cause the item to be recognized
// as another list.
String listItemContent = match.group(3).trim();
```

#### Javadocs in Public APIs

- Well-documented public APIs are crucial.
  - Example:

```
/**
 * Returns an immutable list of colors.
 *
 * @return a list of colors
 */
public List<Color> getColors() {
  // ...
}
```

### Bad Comments

- Comments should be as carefully crafted as the code itself.

#### Mumbling

- The comment is vague and does not provide clear information.
  - Example:

```
catch(IOException e) {
  // No properties files means all defaults are loaded
}
```

#### Redundant Comments

- The comment merely restates what the code does, adding no value.
  - Example:

```
// Utility method that returns when this.closed is true. Throws an exception if the timeout is reached.
public synchronized void waitForClose(final long timeoutMillis) throws Exception {
  if (!closed) {
    wait(timeoutMillis);
    if (!closed)
      throw new Exception("MockResponseSender could not be closed");
  }
}
```

#### Misleading Comments

- The comment incorrectly describes the behavior, leading to misunderstandings.
  - Example:

```
// Utility method that returns when this.closed is true.
public synchronized void waitForClose(final long timeoutMillis) throws Exception {
  if (!closed) {
    wait(timeoutMillis);
    if (!closed)
      throw new Exception("MockResponseSender could not be closed");
  }
}
```

#### Mandated Comments

- Required comments often result in pointless, redundant descriptions.
  - Example:

```
/**
* @param title The title of the CD
* @param author The author of the CD
* @param tracks The number of tracks on the CD
* @param durationInMinutes The duration of the CD in minutes
*/
public void addCD(String title, String author, int tracks, int durationInMinutes) {
  CD cd = new CD();
  cd.title = title;
  cd.author = author;
  cd.tracks = tracks;
  cd.duration = durationInMinutes;
  cdList.add(cd);
}
```

#### Journal Comments

- Modern source control systems make these unnecessary and they clutter the code.
  - Example:

```
* Changes (from 11-Oct-2001)
* --------------------------
* 11-Oct-2001 : Re-organised the class and moved it to new package com.jrefinery.date (DG);
* 05-Nov-2001 : Added a getDescription() method, and eliminated NotableDate class (DG);
```

#### Noise Comments

- These comments state the obvious and add no meaningful information.
  - Example:

```
/**
* Default constructor.
*/
protected AnnualDateRule() { }
```

#### Scary Noise

- Javadocs for private fields or non-public APIs are unnecessary and distracting.
  - Example:

```
/** The name. */ private String name;
/** The version. */ private String version;
/** The licenceName. */ private String licenceName;
```

#### Don’t Use a Comment When You Can Use a Function or a Variable

- Example:

```
// does the module from the global list <mod> depend on the subsystem we are part of?
if (smodule.getDependSubsystems().contains(subSysMod.getSubSystem()))

// Refactored to...
ArrayList moduleDependees = smodule.getDependSubsystems();
String ourSubSystem = subSysMod.getSubSystem();
if (moduleDependees.contains(ourSubSystem))
```

#### Position Markers

- These are rarely useful and generally add clutter.
  - Example:

```
// Actions //////////////////////////////////
```

#### Closing Brace Comments

- Long functions needing these comments should be refactored for clarity.
- Example:

```
} // try
catch (IOException e) { System.err.println("Error:" + e.getMessage());
} //catch
```

#### Attributions and Bylines

- Source control systems handle this information more effectively.
  - Example:

```
/* Added by Rick */
```

#### Commented-Out Code

- Leads to clutter and confusion. Modern source control negates the need for this.
  - Example:

```
// InputStream resultsStream = formatter.getResultStream();
// StreamReader reader = new StreamReader(resultsStream);
```

#### HTML Comments

- Makes comments hard to read in the code editor.
  - Example:

```
/**
* Task to run fit tests.
* <pre>
* &lt;taskdef name=&quot;execute-fitnesse-tests&quot;
* </pre>
*/
```

#### Nonlocal Information

- Local comments should not describe system-wide settings.
  - Example:

```
/**
* Port on which fitnesse would run. Defaults to <b>8082</b>.
*/
public void setFitnessePort(int fitnessePort) {
  this.fitnessePort = fitnessePort;
}
```

#### Too Much Information

- Historical or irrelevant details should not be in comments.
  - Example:

```
/*
RFC 2045 - Multipurpose Internet Mail Extensions (MIME)
Part One: Format of Internet Message Bodies
section 6.8. Base64 Content-Transfer-Encoding
*/
```

#### Inobvious Connection

- The relationship between comment and code is unclear.
  - Example:

```
/*
* start with an array that is big enough to hold all the pixels
* (plus filter bytes), and an extra 200 bytes for header info
*/
this.pngBytes = new byte[((this.width + 1) * this.height * 3) + 200];
```

#### Function Headers

- Short, well-named functions usually don't need comments.

#### Javadocs in Nonpublic Code

- Javadocs are helpful for public APIs but unnecessary for internal code.
