---
description: "Use when: auditing UI/UX quality on a live page, checking accessibility and WCAG compliance, reviewing design consistency, evaluating usability heuristics, checking color contrast, typography, spacing, responsive layout"
name: "Run UI/UX Audit"
agent: "UI/UX Reviewer"
argument-hint: "URL to audit (e.g. 'https://app.example.com') or a specific flow (e.g. 'the onboarding flow at https://...')"
---

Conduct a thorough UI/UX audit on the following target:

**Target:** $args

Apply the full audit approach from your instructions:
1. Take a baseline screenshot and check for console errors
2. Audit visual design: typography, color/contrast, spacing, branding
3. Evaluate all 10 Nielsen usability heuristics
4. Check accessibility: keyboard navigation, ARIA semantics, alt text, form labels
5. Test at mobile (375px), tablet (768px), and desktop (1440px) breakpoints
6. Review hover states, loading states, and form validation feedback

Produce the complete **UI/UX Audit Report** including:
- Executive Summary
- Severity-rated findings with evidence and recommendations
- Heuristics Scorecard
- Responsive Summary
- Top 3 Accessibility Quick Wins
- Recommended Next Steps

Use `evaluate` scripts to extract measurable evidence (contrast colors, missing alt text, unlabeled interactive elements).
