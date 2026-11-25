# Dials: who turns them and on what signal

| Dial | Owner | Signal |
|---|---|---|
| Risk tier | Card shaper (Builder); Coordinator re-checks | Blast radius, reversibility, client visibility |
| Review depth | Follows the tier and auto-adjust | First-pass streaks and rework (see SKILL.md) |
| Done bar | PO | The human sets or changes a goal → bump vN and list affected cards |
| Evidence set | Builder keeps the table below | A new "could not verify" case adds a row |
| Stage | PO | A subjective item with no picked prototype stays in Explore |
| Model tier | Card shaper | Tier default (SKILL.md); go one step up if the last round failed on capability |
| Card size / appetite | Card shaper | Tier default; after two reworks, split or return to Explore |
| WIP | Coordinator | Default 3–4; stop dispatching when acceptance backlog exceeds 2 |
| Report cadence | Owner | Hand-in plus a daily digest; R3 and blockers immediately |
| Decision deadline | PO | Every ledger entry that is still open has a recommendation and a reminder deadline (default 48 h, 24 h for R3). A deadline never authorises a red-line action. Only the most blocking decision sits in the brief |
| Human touchpoints | PO proposes, human sets | Direction picks and red-line actions only, unless the human asks for more |

## Evidence by change type
| Change | Required evidence |
|---|---|
| Static UI | Full-page screenshots at desktop and mobile widths, using the quality standard's screenshot template, plus a design critique |
| Motion / interaction | Screen recording or frame sequence, plus a reduced-motion capture |
| Locked-journey area | Regression script output: required elements present, and no long stretch without the primary action |
| CMS / content model | Admin screenshots plus one real save and read-back in the approved mode |
| Generated artefact | The artefact itself (file, payload, export), not only a picture of it |
| Numbers for a client | Definition, query or script, and timestamp. Re-run every doc that cites the number when its definition changes |
| Docs / report | File path, plus source links or the command output behind each claim |
| Code | Diff, test run and the cross-vendor verdict (defects plus brief conformance) |

## Model notes
- A cheap model does per-item checks; a stronger model reviews only what it flags.
- High effort only after asking the human.
- The reviewer always comes from a different vendor than the author.

## Decision defaults
- A rule-1 red-line item is always R3. It never proceeds by default, by silence, or at a deadline, even if it was first labelled R0, R1 or R2.
- R0/R1 (and only those): at the deadline with no objection, the PO first re-checks the recommendation against rule 1. Any red-line component is reclassified R3 and is not applied. Only then may the recommendation be applied, with a report after.
- R2: at the deadline, remind once, then park as "known to human, deferred". Never auto-apply.
- R3: never auto-apply, never treat silence as yes, never proceed at a deadline. Remind once, then park as "known to human, deferred". Do not re-push it as the top blocker without new information.

## Decision ledger row
`ID | date | verbatim quote | message id (or date if none) | scope | supersedes | status | recommendation | deadline`

There is one ledger per project, kept in the repo. Other files link to it and never copy it.

## Repo bootstrap
The brief is the only entry file. Everything else is linked from it and never restates it.
- `docs/planning/brief.md` (or the dated Current understanding block at the top of an existing `task_plan.md`)
- `docs/planning/decisions.md`: the ledger. A superseded row is marked, never deleted.
- `docs/planning/progress.md`: per-card status with evidence paths.
- `docs/planning/lessons.md`: one row per failure, with an occurrence count.
- `docs/design/quality-standard.md` (UI projects): benchmark breakdown, visual red lines, reference images and the screenshot template.
- `AGENTS.md`: a router only. It links the files above and the `project-collab-method` skill, and holds project-specific gate lines only. It never copies the fixed rules. A card reads `AGENTS.md`, then the brief.

Knowledge docs that are not about development go to the knowledge base, not the repo.

For an existing repo: do a read-only inventory, then open a draft PR that adds the missing files and marks old clauses superseded. Get a cross-vendor review. No merge or deploy without the human.

## Owner table
| Document | Owner | Update trigger | Reviewer |
|---|---|---|---|
| Brief / done bar | PO | The human sets or corrects a goal, before any card | Coordinator, against the human's words |
| Quality standard | Builder | A UI correction or a new benchmark | PO + cross-vendor model |
| Decision ledger | PO | A ruling, a rejection or a conflict | Builder (feasibility) + Coordinator (confirms the human ruled) |
| Status | Coordinator (global), Builder (repo) | Every hand-in, merge or report | PO |
| Lessons → skills | Coordinator | The same failure twice | PO + Builder |
