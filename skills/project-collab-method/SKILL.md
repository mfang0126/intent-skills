---
name: project-collab-method
description: >-
  Use this when starting any project, onboarding an existing repo, shaping,
  dispatching or accepting work, or reporting results across multiple
  agents; it is the single process source: nine fixed rules, risk tiers
  R0-R3 that set review depth, evidence, model and decision defaults, one
  project brief as sole entry, explore-then-build for subjective work, and
  an ask-once decision ledger.
---
# Project collaboration method (single process source)

Goal: no rework loops and no repeated asks. Keep a small fixed core. Everything else is a dial that a named owner turns on a named signal. This skill supersedes earlier process docs. Where they conflict, this skill wins.

## Roles
- **Human**: rules on direction, R3 actions and conflicts. Only the human's own words count as approval.
- **Product owner (PO)**: owns the brief, the done bar, the decision ledger and final acceptance.
- **Builder**: owns the design and quality standard, shapes and dispatches cards, gets the cross-vendor review, and packages the evidence.
- **Coordinator**: owns the global status view and the one-blocking-decision pointer, makes the last mechanical gate, and points the human to the right owner.

## Fixed rules (never dialled)
1. **Red lines.** Irreversible, spend, delete, production, client-facing and secret actions need the human's own yes. Another agent's approval never counts.
2. **One owner per file.** Others propose changes; the owner writes them.
3. **One project brief is the sole entry.** It is under 40 lines and has five parts: intent, done bar vN, locked journey, the one open decision, and non-goals. Every other doc is linked from the brief, never placed beside it.
4. **Fixed handoff order.** PO locks the intent, the Builder builds, a cross-vendor model reviews read-only, the PO accepts, the Coordinator gates, and the owner reports. The depth of each step may change; the order may not.
5. **Evidence before verdict.** No evidence file means no pass. Lint, tests or "file exists" are a floor, never a pass for a judgement criterion.
6. **Locked journey survives changes.** Removing or weakening a locked element needs a numbered decision plus a passing regression check.
7. **Ask once.** Every human ruling goes into the decision ledger with the verbatim quote, message id, scope and what it supersedes. Check the ledger, the brief's non-goals and the brief's premises before asking anything.
8. **Conflicts go to the human first.** Never compromise first and build later.
9. **The owner reports directly.** The Coordinator does not relay details; it only says who to talk to next and why.

## Risk tiers (set per card; drive the dials)
| Tier | Scope | Review | Human |
|---|---|---|---|
| R0 | Read-only, docs, reports | Self-check | Report after |
| R1 | Internal, reversible code | Self-check + cross-vendor review | Report after |
| R2 | Client-visible UI, CMS or copy | R1 + PO gate before dispatch + PO acceptance with evidence | Direction picks only |
| R3 | Production, money, delete, external send | R2 | Own yes, every time |

- The card shaper sets the tier. The Coordinator re-checks it at the gate. A missing tier means the card is not dispatched.
- **Auto-adjust**: three first-pass acceptances in a row on one card type lower review by one tier. Any rework raises it by one tier. R3 never drops.
- Evidence by change type, model tiers, card sizing and decision defaults are in [references/dials.md](references/dials.md).

## Stages
1. **Explore** (subjective work: look, motion, navigation, page direction). Build a reference board and 2–3 cheap prototypes. The human picks only the direction. The PO picks details against the reference images. No build card is dispatched until a prototype is picked.
2. **Lock.** The PO writes done bar vN into the brief, citing the human's words. When the version changes, list the running cards affected and mark each continue, re-scope or stop.
3. **Build.** One card produces one acceptable outcome. Its done bar cites brief vN, and for subjective work it is "matches prototype X". A card reworked twice is split or sent back to Explore.
4. **Accept.** Check the evidence list first, then judge the content. Missing evidence goes straight back.
5. **Handover.** Client-facing files and internal notes are separate files. Scan for internal terms before anything is sent.

## Lessons become mechanisms
- A prohibition becomes a required card field, a script check or a gate line. Chat does not count.
- A rule seen twice becomes a candidate. After three real deliveries (Rule of Three), promote it and regression-test it against the original failure.
- When a rule is added, retire or merge an older one. Superseded docs get a banner and are never deleted.

Repo bootstrap and owner table: [references/dials.md](references/dials.md#repo-bootstrap).
