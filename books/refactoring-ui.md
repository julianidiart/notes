# Refactoring UI (2018)

## Starting from Scratch

### Start with a Feature, Not a Layout

- Begin the design process by focusing on a specific feature rather than the overall layout.
  - Example: For a flight booking service, start by designing the flight search feature.
- Avoid designing the app’s shell (navigation bars, sidebars) before understanding the features.

#### Focus on Functionality:

- Design with actual functionality in mind to avoid frustration.
  - Example elements: fields for departure and destination cities, dates, and a search button.

### Detail Comes Later

- In the early stages, avoid getting bogged down by details like typefaces or icons.
- Use simple tools like pen and paper to sketch out ideas without focusing on minute details.

#### Hold the Color

- Start designing in grayscale to ensure strong hierarchy and clarity without relying on color.
- Add color later once the basic design is solid.

#### Don’t Over-Invest in Early Stages:

- Use low-fidelity sketches and wireframes to move quickly and avoid over-investing in static mockups.
- Iterate on a working design rather than trying to perfect everything upfront.

### Don’t design too much

#### Work in Cycles

- Design and build in short cycles, starting with a simple version and iterating based on real use.
- This approach helps address unforeseen complexities more effectively.

#### Be a Pessimist

- Avoid implying functionality that isn’t ready to be built.
- Focus on the simplest useful version of a feature, adding enhancements later.

### Choose a personality

- Determine the design’s personality through concrete elements like font choice, color, border radius, and language.
- Consistency is key to maintaining a cohesive design personality.

### Limit your choices

- Too many options can be paralyzing; limit choices for colors, fonts, and other design elements.
- Use predefined systems to streamline decision-making and avoid fatigue.

#### Systematize Everything

- Establish systems for elements like font sizes, colors, margins, and more to facilitate faster and more confident design decisions.
- Approach design with a mindset focused on creating and utilizing systems to reduce repetitive decision-making.

## Hierarchy is Everything

### Not all elements are equal

- Visual hierarchy determines how important elements appear in relation to each other.
- Effective hierarchy makes interfaces feel designed and less chaotic by emphasizing important elements and de-emphasizing secondary information.

### Size isn’t everything

- Don’t rely solely on font size for hierarchy; use font weight and color to communicate importance.
- Utilize a few colors: dark for primary content, grey for secondary, and lighter grey for tertiary.
- Use two font weights: a normal weight for most text and a heavier weight for emphasis.

### Don’t use grey text on colored backgrounds

- Grey text on colored backgrounds reduces contrast and readability.
  - Instead, choose a color close to the background color to reduce contrast without making text look dull or washed out.

### Emphasize by de-emphasizing

- Sometimes de-emphasizing competing elements can make the main element stand out.
  - For example, using softer colors for inactive items can make active items more prominent.

### Labels are a last resort

- Avoid using labels whenever possible by making data self-explanatory through format or context.
- Combine labels with values (e.g., “12 left in stock” instead of “In stock: 12”) for clarity and emphasis.
- When labels are necessary, de-emphasize them with smaller size, reduced contrast, or lighter weight.

### Separate visual hierarchy from document hierarchy

- Use semantic markup for web development, but don’t let it dictate visual styling.
- Section titles should be supportive and not steal attention from the content.

### Balance weight and contrast

- Use lower contrast for heavy elements like icons to balance their visual weight.
- Use increased weight for low contrast elements when necessary to maintain emphasis without harshness.

### Semantics Are Secondary

- Design actions based on their importance, not just semantics.
- Primary actions should be obvious with high contrast, secondary actions should be clear but not prominent, and tertiary actions should be discoverable but unobtrusive.
- For destructive actions, use secondary or tertiary button treatments unless it's the primary action in a confirmation step.
