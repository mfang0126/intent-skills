# Dials: who turns them and on what signal

| Dial | Owner | Signal |
|---|---|---|
| Risk tier | Card shaper; Coordinator re-checks | Blast radius, reversibility, client visibility |
| Review depth | Follows the tier | Auto-adjusts on first-pass streaks and on rework (see SKILL.md) |
| Done bar | PO | The human sets or changes a goal → bump vN and list affected cards |
| Evidence set | Builder keeps the table below | A new "could not verify" case adds a row |
| Stage | PO | A subjective item with no picked prototype stays in Explore |
| Model tier | Card shaper | How machine-verifiable the task is, and whether the last round failed on capability |
| Card size / appetite | Card shaper | Two reworks → split or return to Explore |
| WIP | Coordinator | Default 3–4; stop dispatching when acceptance backlog exceeds 2 |
| Report cadence | Owner | Hand-in plus a daily digest; R3 and blockers immediately |
| Decision deadline | PO | Every open decision has a recommendation and a deadline |
| Human touchpoints | PO proposes, human sets | Direction picks and R3 only, unless the human asks for more |

## Evidence by change type
| Change | Required evidence |
|---|---|
| Static UI | Full-page screenshots at desktop and mobile widths, plus a design critique against the quality standard |
| Motion / interaction | Screen recording or frame sequence, plus a reduced-motion capture |
| Locked-journey area | Regression script output (required elements present; no long stretch without the primary action) |
| CMS / content model | Admin screenshots plus one real save and read-back in the approved mode |
| Generated artefact | The artefact itself (file, payload, export), not only a picture of it |
| Numbers for a client | Definition, query or script, and timestamp; re-run every doc that cites it when the definition changes |
| Code | Diff, test run and the cross-vendor review verdict |

## Model tiers
- Cheap, fast model: per-item checks. A stronger model reviews only what it flags.
- Mid model: mechanical, well-specified edits.
- Strongest model at medium effort: design, analysis, ambiguous builds. High effort only after asking the human.
- The reviewer always comes from a different vendor than the author.

## Decision defaults
- R0/R1: at the deadline with no objection, apply the recommendation and report after.
- R2/R3: at the deadline, remind once, then park as "known to human, deferred". Never auto-apply, and never re-push it as the top blocker without new information.

## Decision ledger row
`ID | date | verbatim quote | message id | scope | supersedes | status`. One ledger per project, in the repo. Other files link to it and never copy it.

## Repo bootstrap
Add these files next to the code, linked from the brief:
- `docs/planning/brief.md` (or the dated Current understanding block at the top of an existing `task_plan.md`): the sole entry, under 40 lines, five parts.
- `docs/planning/decisions.md`: the decision ledger. A superseded row is marked, never deleted.
- `docs/planning/progress.md`: per-card status, each with its evidence path.
- `docs/design/quality-standard.md` (UI projects): benchmark breakdown, visual red lines and reference images.
- `AGENTS.md`: a short router to the files above, plus the fixed rules that apply to workers. Every card links it.

For an existing repo: do a read-only inventory, then open a draft PR that adds the missing files and marks old clauses superseded. Get a cross-vendor review. No merge or deploy without the human.

## Owner table
| Document | Owner | Update trigger | Reviewer |
|---|---|---|---|
| Brief / done bar | PO | The human sets or corrects a goal, before any card | Coordinator, against the human's words |
| Quality standard | Builder | A UI correction or a new benchmark | PO + cross-vendor model |
| Decision ledger | PO | A ruling, a rejection or a conflict | Builder (feasibility) + Coordinator (confirms the human ruled) |
| Status | Coordinator (global), Builder (repo) | Every hand-in, merge or report | PO |
| Lessons → skills | Coordinator | The same failure twice | PO + Builder |
