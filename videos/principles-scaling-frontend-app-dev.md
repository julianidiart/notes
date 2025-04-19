[# Principles for Scaling Frontend Application Development by Malte Ubl (2023)](https://www.youtube.com/watch?v=tqhLK0Fb5_4)

1. **Tear Down the Barriers**

- **Problem**: Sharing code via private npm modules is _slow_ and _inefficient_.
- **Solution**: Move to a _monorepo_ to streamline collaboration and sharing.
  - _Faster collaboration_.
  - _Lower friction_ for internal code reuse.

> "My one weird trick: move to a monorepo. It’s worth it."

2. **Make It Easy to Delete Code**

- _Big codebases grow_, it’s natural.
- The challenge is making code deletion _safe_ and _reliable_.
- Tailwind/CSS-in-JS encourages _co-location_ → easy deletions.
- Data fetching in components allows _self-contained_ logic → safe to delete entire units.

3. **Always Migrate Incrementally**

- _Big bang migrations fail_.
- Plan migrations as _gradual steps_ from the start.
- Design APIs that support _partial adoption_.

> "There are two types of migrations: the incremental ones and the failed ones."

4. **Always Getting Better, Never Getting Worse**

- Enforce rules via _linters_ and _policies_, but don't halt progress with full rewrites.
- Use _allow lists_ for rule exceptions instead of littering with eslint-disable.
- _Track violations_ over time, let them decline naturally.

> "The marginal value of a lint rule is highest on new code, not old code."

5. **Embrace Lack of Knowledge**

- Junior devs or new team members lack _full context_.
- **Your job**: encode best practices in _machine-readable form_.
- Enforced through _allow lists + owners = safe_, scalable guardrails.

6. **Eliminate Systematic Complexity**

- Identify recurring pain points → _abstract_ them away.
  - Example: _“Version skew”_ between client and server.
