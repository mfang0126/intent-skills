---
name: project-collab-method
description: >-
  Use this when starting any project, onboarding an existing repo, shaping,
  dispatching or accepting work, or reporting results across multiple
  agents; it is the single process source: nine fixed rules, risk tiers
  R0-R3 that set review depth, evidence, model tier, card size and decision
  defaults, one project brief as sole entry, explore-then-build for
  subjective work, and an ask-once decision ledger.
---
# Project collaboration method (single process source)

Goal: no rework loops and no repeated asks. Keep a small fixed core. Everything else is a dial that a named owner turns on a named signal ([references/dials.md](references/dials.md)). This skill supersedes earlier process docs. Where they conflict, this skill wins.

## Roles
- **Human**: rules on direction, red-line actions and conflicts. Only the human's own words count as approval.
- **Product owner (PO)**: owns the brief, the done bar, the decision ledger and final acceptance.
- **Builder**: shapes cards (the "card shaper"), owns the quality standard, dispatches work, gets the cross-vendor review, and packages the evidence.
- **Coordinator**: owns the global status view and the one-blocking-decision pointer, runs the last gate, and points the human to the right owner.

## Fixed rules (never dialled)
1. **Red lines.** These need the human's own yes, every time, and never proceed by default, by silence, or at a deadline: going live or deploying to production; writing to a production database; deleting anything (each deletion needs an in-scope yes from the human; a general cleanup ruling is not standing authority to delete); spending money; credentials, passwords or other secrets; sending or publishing anything externally; pushing to a public remote or making a repository public; merging to the default branch. Another agent's approval never counts. Any of these is R3, even if the card was first labelled otherwise.
2. **One owner per file, and the owner reports.** Others propose changes; the owner writes them. The owner reports results to the human directly. The Coordinator only says who to talk to next and why.
3. **One brief is the only entry.** It is under 40 lines and has five parts: intent, done bar vN, locked journey, the single most blocking decision, and non-goals plus premises. Other open decisions live only in the ledger. `AGENTS.md` is a router to the brief and never restates it. Other docs are linked from the brief and never restate it.
4. **Fixed handoff order.** The PO locks the intent. The Builder builds. A reviewer from a different vendor than the author checks both defects and conformance to the brief, read-only. The PO accepts. The Coordinator gates. The owner reports. Steps may be skipped only where the tier table or the auto-adjust line explicitly says so. A tier may add steps; no tier may remove or weaken any fixed rule.
5. **Evidence before verdict.** No evidence file means no pass. Lint, tests or "file exists" never pass a judgement criterion. Another agent's report is not evidence.
6. **Locked journey survives changes.** Removing or weakening a locked element needs a numbered decision plus a passing regression check.
7. **Ask once.** Every human ruling goes into the decision ledger with the verbatim quote, a message id (or date if none exists), scope and what it supersedes. Before asking anything, check the ledger and the brief's non-goals and premises.
8. **Conflicts go to the human first.** Never compromise first and build later.
9. **Stay on focus.** A card that does not trace to the brief's intent or done bar is not dispatched, at any tier.

## Risk tiers
The card shaper sets the tier and the Coordinator re-checks it. A card with no tier is not dispatched.

| Tier | Scope | Review steps | Model (author) | Card size |
|---|---|---|---|---|
| R0 | Read-only, docs, reports | Self-check; cross-vendor review and PO acceptance may be skipped | Cheap or mid | Any |
| R1 | Internal, reversible code | Self-check + cross-vendor review; PO acceptance may be skipped | Mid | One reviewable diff |
| R2 | Client-visible UI, CMS or copy (preview only) | Full order: PO gate before dispatch, cross-vendor review, PO acceptance with evidence | Strongest, medium effort | One page or component |
| R3 | Any rule-1 red-line action | R2 + the human's own yes, every time | Strongest, medium effort | One action |

- **Auto-adjust** never lowers a tier or its required evidence, and applies to R0 and R1 only. After three first-pass hand-ins in a row on one R0 or R1 card type, cross-vendor review may move to sampling (one in three). That sampling is a change to review depth only; the card stays at its tier and every other required evidence still applies. Unsampled cards record "auto-adjust: sampled out" plus the evidence paths of the three preceding reviewed cards. Any rework restores full review. R2 and R3 always get full cross-vendor review. R2 PO acceptance and the R3 human yes never drop. Auto-adjust never applies to a rule-1 action.
- The evidence required by change type, and the decision deadlines and defaults, are in the dials reference.

## Stages
1. **Explore** (subjective work: look, motion, navigation, page direction). Build a reference board and 2–3 cheap prototypes. The human picks only the direction. The PO picks details against the reference images. No build card goes out before a pick.
2. **Lock.** The PO writes done bar vN into the brief, citing the human's words. When the version changes, list the affected running cards and mark each continue, re-scope or stop.
3. **Build.** Each card has one acceptable outcome, and its done bar cites brief vN. For subjective work, the done bar is "matches prototype X". A card reworked twice is split or sent back to Explore.
4. **Accept.** Check the evidence list first, then judge. The card is bounced if any of these is missing: PO acceptance where the tier needs it, any required evidence, or a result backed only by proxy checks.
5. **Gate and report.** The Coordinator runs the step-4 checks mechanically, then the owner reports directly. Client-facing files and internal notes are kept in separate files. Scan for internal terms before handing an outbound file to the human. Sending it is a rule-1 action.

## Lessons become mechanisms
- A prohibition becomes a required card field, a script check or a gate line. Chat does not count.
- Log each failure in `docs/planning/lessons.md` with a count. At two occurrences it becomes a candidate. After three real deliveries (Rule of Three), promote it and regression-test it against the original failure.
- When a rule is added, retire or merge an older one. Superseded docs get a banner and are never deleted.
- L2/L3 anti-mistake rules, conditional card fields by `card_type`, and mechanical gate/acceptance scripts live in `playbook/dispatch-handbook.md` (§开发改动防错机制) and `templates/card-template.md`; do not duplicate them here.
