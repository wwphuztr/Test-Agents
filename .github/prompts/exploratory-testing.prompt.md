---
description: "Use when: running an exploratory testing session on a live URL, performing a quick smoke test, bug hunting on a web UI, session-based testing, tour-based testing, heuristic testing"
name: "Run Exploratory Testing"
agent: "Exploratory Testing"
argument-hint: "URL or feature area to explore (e.g. 'https://app.example.com/login' or 'the checkout flow')"
---

Conduct an exploratory testing session on the following target:

**Target:** $args

Apply the full exploratory testing approach from your instructions:
1. Capture the baseline state (screenshot + console check)
2. Walk the happy path end-to-end
3. Apply boundary inputs, state transitions, and error paths
4. Check for visual, console, and network issues
5. Produce the full **Findings Report** with severity-rated issues, reproduction steps, and evidence

Focus on surfacing real bugs and broken flows. Be skeptical — do not assume anything works correctly.
