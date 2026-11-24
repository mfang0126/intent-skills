---
name: website-benchmark-align
description: Use when aligning on a website's structure, redesign, or "done" bar against a benchmark site—or when the user casually asks to analyze a website, compare against a competitor, check pages/layouts/components/user journey/conversion, or recalls "that website analysis framework" before writing code.
---

# Website Benchmark Alignment (4-Layer Intent-Based)

## Purpose
Align on what "done" means for a website—and where real conversion gaps sit relative to a benchmark site—**before writing any code**.

## Core Rules
1. **Read-only until aligned**: Never edit application code, open PRs, or deploy during alignment.
2. **Reuse before crawling**: Inspect existing repo routes, docs, and prior benchmark notes first. Check the live benchmark site only with targeted, low-cost lookups for missing or potentially stale facts.
3. **Conversion over imitation**: Judge gaps by the site's own business intent, not raw page count. Explicitly separate true conversion gaps from bloat that only exists because the benchmark serves broader categories.
4. **No fabricated evidence**: Ground page counts, routes, and gap claims in verified files or live checks.

## Intent-Based 4-Layer Framework (Top-Down)
Always analyze and explain in this order, starting from visitor intent:
1. **User Journey (Top)**: Core visitor intent to conversion (e.g., discover product -> build trust -> estimate price -> request sample/quote/checkout). Measure click depth, friction, and drop-off points.
2. **Pages**: Complete page inventory (exact count, URLs, purpose, CMS coverage) mapped to distinct visitor intents vs. the benchmark's page architecture.
3. **Layouts**: Page skeleton, above-the-fold hierarchy, mobile/desktop CTA reachability, and information flow.
4. **Components (Base)**: Reusable UI building blocks (selectors, calculators, galleries, forms, trust modules) and how cleanly they map to CMS fields.

## Deliverables
1. **Concise Intent Summary**: Direct verdict against the user's "done" bar, exact page count, what already beats the benchmark, true conversion gaps, and benchmark elements intentionally skipped.
2. **Standalone HTML Comparison Page**: Single self-contained HTML file (inline styles/SVG journey diagram + real screenshots when available) comparing both sites side by side across the 4 layers, plus a prioritized gap table (recommendations only, no code changes).

## Handoff: Planning with Files
Once the user reviews the comparison and confirms the target bar, lock the agreement into project planning files (`task_plan.md`, `findings.md`, `progress.md`):
- Explicit "done" criteria and checkable acceptance items
- In-scope pages, layouts, components, and conversion features
- Explicit non-goals / deferred items
- Ordered phases; implementation starts only after this plan is approved, and every task updates progress until all boxes are checked.
