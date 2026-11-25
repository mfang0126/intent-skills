---
name: project-collab-method
description: >-
  Use this when starting any project, onboarding an existing repo, dispatching
  or accepting work, or reporting results across multiple Bots/agents; it is the
  fixed method every project follows: one owner per document, fixed handoff
  order, hard pass gate, conflicts to the human first, owning Bot reports
  directly.
---
# Project collaboration method (fixed, all projects)

Goal: stop repeated rework. Every decision and lesson lands once in a known file with one owner, and every worker reads it before starting.

## 1. Roles
- **Product owner (PO)**: owns the intent, the requirements, the done bar and the decisions log, and gives final acceptance.
- **Builder**: owns the design and quality standard, dispatches workers, gets the different-vendor review, and packages the evidence.
- **Coordinator**: keeps the global open-items list and the single most-blocking-decision pointer, makes the last mechanical gate before anything is reported as passed, and points the human to the right owner.
- **Domain bots**: own their own project files end to end.

## 2. Required project files (bootstrap on day one)
Create these in the repo, next to the code:
- `docs/planning/task_plan.md`: a dated Current understanding block (focus: what, why, done bar), plus Non-Goals.
- `docs/planning/decisions.md`: numbered decisions; a superseded decision is marked, never deleted.
- `docs/planning/progress.md`: per-card status and its evidence.
- `docs/planning/lessons.md`: lesson candidates, each with a count of how many times it occurred.
- `docs/design/quality-standard.md`: the benchmark breakdown, the visual red lines, and the screenshot template (UI projects).
- `AGENTS.md`: points to all of the above and carries the hard gates in section 4. Every worker card links it.

Knowledge docs that are not about development go to the knowledge base, not the repo.

## 3. Owner table
| Document | Owner | Update trigger | Reviewer |
|---|---|---|---|
| Requirements / done bar | PO | Human sets or changes a goal, or corrects course. Update BEFORE any card. | Coordinator (checks it against the human's own words) |
| Design / quality standard | Builder | A UI correction, a new benchmark, or a gate upgrade | PO + different-vendor model |
| Decisions / conflicts | PO | The human rules, rejects an option, or a conflict is found | Builder (feasibility) + Coordinator (confirms the human actually ruled) |
| Status | Coordinator (global); Builder (in-repo) | Every hand-in, merge, or report | PO (done bar met, not just closed) |
| Lessons -> skills | Coordinator | The same failure happens twice or more | PO + Builder (Builder syncs it into AGENTS.md) |

## 4. Handoff order and hard gates
1. **PO locks the intent**: purpose, done bar and Non-Goals. An unresolved conflict goes to the human for one ruling before dispatch. Never compromise first and build later.
2. **PO gates the card** against the focus lock. An off-focus card is not dispatched.
3. **Builder dispatches.** The worker builds, a different-vendor model reviews read-only, and the Builder self-checks.
   - UI work requires an aesthetic-evidence section: a real design judgement, critique/polish/audit conclusions, and full-page screenshots at desktop and mobile widths.
   - Lint, detect or tests passing alone is never a pass.
4. **PO gives final acceptance** (PASS or BLOCK).
5. **Coordinator's last gate**: missing PO PASS, missing evidence, or proxy-only results mean it goes back to the Builder and is never reported as passed.
6. **The owning bot reports directly** to the human in its own chat. The coordinator does not relay details; it only says who to talk to next and why, and pushes one blocking decision at a time.

## 5. Lessons become mechanisms
- After every correction, rewrite the principle in Current understanding and mark the old rule superseded.
- Turn each prohibition into a required card field, a script check, or an AGENTS.md line. Not chat.
- Rule of Three: a checklist item proves itself over 3 real deliveries before it is promoted to a shared skill. Regression-test it against the original failure scenario.

## 6. Applying to an existing repo
Run a read-only inventory, then open a draft PR that adds the missing section 2 files and the AGENTS.md gates. Old clauses are marked superseded. Get a different-vendor review. No merge or deploy without the human.
