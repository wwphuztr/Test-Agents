# Testing Persona Diagrams

---

## Diagram 1 — The Building Blocks of a Persona

Every agent is defined by the same 5-layer structure inside a `.agent.md` file:

```mermaid
flowchart TD
    A["📄 .agent.md file\n(.github/agents/)"] --> B

    subgraph B["5 Layers of a Persona"]
        direction TB
        L1["① YAML Frontmatter\n─────────────────\nname: (display name)\ndescription: (when to invoke)\ntools: (what it can use)\nargument-hint: (input hint)"]
        L2["② Role Declaration\n─────────────────\n'You are a senior UI/UX designer...'\n'You are an expert exploratory tester...'\n'You are a senior QA analyst...'"]
        L3["③ Mission\n─────────────────\nOne clear, measurable goal\n(e.g. deliver report in under 2 min)"]
        L4["④ Constraints\n─────────────────\nWhat the agent must NOT do\n(no code, no file edits, time-boxed)"]
        L5["⑤ Methodology + Output Template\n─────────────────\nStep-by-step approach\nFixed report structure"]

        L1 --> L2 --> L3 --> L4 --> L5
    end
```

---

## Diagram 2 — The Three Personas Side by Side

```mermaid
flowchart LR
    INPUT["👤 User gives a URL\nor feature to test"]

    INPUT --> P1
    INPUT --> P2
    INPUT --> P3

    subgraph P1["🎨 UI/UX Reviewer"]
        direction TB
        R1["Role: Senior UI/UX designer\n& accessibility specialist"]
        R2["Tools: Playwright browser\n(screenshot, resize, hover)"]
        R3["Approach:\n1. Baseline screenshot\n2. Visual design check\n3. Nielsen heuristics (top 5)\n4. Accessibility snapshot\n5. Responsive check (1440px)"]
        R4["Output: UI/UX Audit Report\n(Executive Summary +\nSeverity table +\nHeuristics scorecard)"]
        R1-->R2-->R3-->R4
    end

    subgraph P2["🔍 Exploratory Tester"]
        direction TB
        E1["Role: Expert exploratory tester\n(human-like, skeptical)"]
        E2["Tools: Playwright browser\n(click, type, fill, console logs)"]
        E3["Approach:\n1. Define charter & scope\n2. Happy path first\n3. Boundary & error inputs\n4. Observe & screenshot findings"]
        E4["Output: Findings Report\n(Severity counts +\nBug details + Repro steps)"]
        E1-->E2-->E3-->E4
    end

    subgraph P3["📋 Manual Test Planner"]
        direction TB
        M1["Role: Senior QA analyst\n(structured, methodical)"]
        M2["Tools: Playwright browser\n+ read/search workspace"]
        M3["Approach:\n1. Screenshot & inspect page\n2. List all UI elements\n3. Apply test design techniques\n4. Cover mobile + desktop"]
        M4["Output: Manual Test Plan\n(Test case table +\nCoverage summary)"]
        M1-->M2-->M3-->M4
    end
```

---

## Diagram 3 — How a Persona Is Invoked (End to End)

```mermaid
sequenceDiagram
    actor Tester as Tester
    participant CP as GitHub Copilot Chat
    participant AF as .agent.md file
    participant PF as .prompt.md file
    participant BR as Playwright Browser

    Dev->>CP: Select agent + type URL
    CP->>AF: Load persona definition<br/>(role, constraints, methodology)
    CP->>PF: Load prompt template<br/>(structured task instructions)
    CP->>BR: Open browser, take screenshot
    BR-->>CP: Page content + screenshot
    loop For each step in Methodology
        CP->>BR: navigate / click / snapshot / resize
        BR-->>CP: Observations & evidence
    end
    CP-->>Dev: Structured Report<br/>(Markdown with severity ratings)
```

---

## Key Point

> **A persona = a role + a tool set + a methodology + an output template.**
> We define these once in a markdown file. GitHub Copilot reads it and behaves exactly like that specialist — no coding required from the tester.
