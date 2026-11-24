---
name: intent-drift-guard
description: Use this when running multi-step or parallel agent projects to prevent scope drift, context loss, or reverted decisions by pairing repo-resident planning/ADR files with an independent conformance gate.
---

# Intent Drift Guard

Prevent multi-step or multi-workstream agent projects from drifting off goal, losing context, or reverting settled decisions.

## Industry Foundations
Combines **Docs-as-Code SSOT**, **ADR (Architecture Decision Records)**, **Spec-Driven Development**, and **Independent Conformance Gates**—replacing prompt-only "remember the plan" habits with repo-resident truth and mechanical checks.

## Guardrails
- **Repo over chat**: Durable goals, constraints, and status live inside the project repository, never only in conversation history.
- **Invariants over prose**: Explicitly state what must **not** be built (`Non-Goals`) and what must **not** be broken (`Invariants` / ADRs), including rejected options and why they were rejected.
- **Anti-meta-work**: Keep planning state to 3 lean files; never build a custom orchestration framework when 3 files plus a review gate suffice.

## 3-Layer Anti-Drift Loop
1. **Lock Intent (Before Execution)**
   Maintain three minimal files in the repo (e.g., `docs/planning/`):
   - `task_plan.md`: Final outcome, measurable "done" bar, explicit **Non-Goals**, and ordered phases.
   - `decisions.md`: Numbered ADRs (`ADR-001`, …) recording locked choices, invariants, and rejected alternatives.
   - `progress.md`: Current phase, verified completions with evidence, open blockers, and exact next step.
2. **Execute Against SSOT (During Execution)**
   - Read the 3 planning files before starting any chunk of work.
   - Never silently expand scope, skip phases, or reverse a locked ADR; escalate conflicts before changing direction.
   - Run independent workstreams in parallel only when their write scopes do not collide (read-only parallel, single writer per shared resource).
3. **Mechanical Drift Gate (Before Claiming Done)**
   Run an independent review (ideally a different model/reviewer than the author) checking **both** defect quality and intent conformance:
   - Did the output satisfy the measurable "done" bar with verified evidence?
   - Did it stay strictly outside `Non-Goals` and honor every locked ADR?
   - Were `progress.md` and `decisions.md` updated in the same change before reporting done?

## Graduation Rule
Abstract a workflow into a reusable skill only after it proves itself across **3 real deliveries** (Rule of Three).
