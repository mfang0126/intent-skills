---
name: website-benchmark-align
description: Use this skill when aligning a website's architecture, redesign, or "done" bar against a benchmark site—including requests to compare against a competitor, audit conversion gaps, or apply top-down UX alignment (Garrett's 5 Planes + Atomic Design) before coding.
---

# Website Benchmark Alignment

Align on what "done" means for a website—and isolate true conversion gaps against a benchmark—before writing any code.

## Guardrails
- **Read-only until aligned**: No code edits, PRs, or deploys during alignment.
- **Reuse before crawling**: Audit existing repo routes, docs, and prior notes first; run only targeted, low-cost live checks for missing or stale facts.
- **Conversion over imitation**: Judge every gap by this site's business intent, never raw page count. Explicitly separate real conversion gaps from benchmark bloat (e.g., extra product categories or SEO location pages).
- **Verified facts only**: Ground every page count, route, and gap in verified files or live checks; label what was checked today, reused, or unverified.
- **Locked journey survives redesigns**: Before a later layout or component change removes a CTA, block, or step, re-check it against the agreed journey and done bar; dropping one needs an explicit, approved decision.
- **Eyes over linters**: A clean anti-pattern or lint scan is a floor, not a visual pass; judge real full-page screenshots at desktop and mobile widths before calling a page done.

## 4-Layer Top-Down Framework
Apply **Jesse James Garrett's Five Planes of UX** (Strategy → Scope → Structure → Skeleton → Surface) + **Brad Frost's Atomic Design** in strict top-down order:
1. **User Journey (Strategy & Structure)**: Core visitor intent to conversion (discover → trust → price/estimate → sample/quote/checkout); measure click depth and drop-off friction.
2. **Pages (Scope & Structure)**: Full page inventory (exact count, URLs, visitor intent, CMS coverage) vs. benchmark page architecture.
3. **Layouts (Skeleton)**: Above-the-fold hierarchy, scan flow, and desktop/mobile CTA reachability.
4. **Components (Surface & Atomic Design)**: Reusable UI modules (selectors, calculators, galleries, forms, trust blocks) and their CMS field mapping.

## Deliverables
1. **Concise Summary**: Direct verdict on the user's "done" bar, exact page count, what already beats the benchmark, prioritized conversion gaps, and benchmark items intentionally skipped.
2. **Standalone Offline HTML Comparison**: One self-contained HTML file (inline CSS, SVG journey diagram, embedded real screenshots) comparing both sites across the 4 layers plus a prioritized gap table.

## Handoff: Planning with Files
After the user approves the comparison and target bar, lock the agreed scope into `task_plan.md`, `findings.md`, and `progress.md` (done criteria, in-scope items, explicit non-goals, ordered phases). Start implementation only after that plan is approved.
