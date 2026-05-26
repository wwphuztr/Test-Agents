---
description: "Use when: creating a manual test plan for a web page or feature, generating test cases from a live UI, writing step-by-step test scenarios, documenting test coverage for a feature"
name: "Create Manual Test Plan"
agent: "Manual Test Planner"
argument-hint: "Page or feature to plan (e.g. 'the current browser page', 'the login page at https://...', 'checkout flow')"
---

Create a comprehensive manual test plan for the following page or feature:

**Target:** $args

Apply the full test planning approach from your instructions:
1. Take a screenshot and snapshot of the current state
2. Enumerate all interactive elements (inputs, buttons, links, dropdowns)
3. Identify features, preconditions, and expected outputs
4. Apply Equivalence Partitioning, Boundary Value Analysis, and Error Guessing
5. Check at both mobile (375px) and desktop (1440px) viewports

Produce the complete **Manual Test Plan** in the structured Markdown table format, covering:
- Happy path test cases
- Negative / error cases
- Boundary value cases
- Responsive layout cases

Include a Test Coverage Summary and list any out-of-scope areas.
