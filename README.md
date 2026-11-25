# intent-skills

Minimalist, intent-based, token-efficient [Agent Skills](https://agentskills.io/specification) built for reuse across AI coding and assistant tools (Claude Code, Codex, Pi, Cursor, Grok Bot, and any `SKILL.md`-compatible agent).

## Standard & Authoring Rules

- **Open Standard**: Follows the [Agent Skills Specification](https://agentskills.io/specification) with **Progressive Disclosure** — agents read only `name` and `description` upfront, load `SKILL.md` when user intent matches, and pull optional `references/` only on demand.
- **Iron Rule**: Write only the constraints a strong model does not already know and would get wrong without them. Name established methodologies directly (e.g., Garrett's Five Planes of UX, Brad Frost's Atomic Design) instead of repeating textbook explanations.
- **Project-Agnostic**: Zero personal details, client references, or repo-specific paths. Keep each `SKILL.md` concise (~30–50 lines) and immediately portable.

## Skills Catalog

| Skill | Path | When to use |
| --- | --- | --- |
| `website-benchmark-align` | [`skills/website-benchmark-align/SKILL.md`](skills/website-benchmark-align/SKILL.md) | Align on a website's architecture, redesign, or "done" bar against a benchmark site (Garrett's 5 Planes + Atomic Design) before writing code. |
| `intent-drift-guard` | [`skills/intent-drift-guard/SKILL.md`](skills/intent-drift-guard/SKILL.md) | Run multi-step or parallel agent projects without scope drift, context loss or reverted decisions: repo-resident planning/ADR files plus an independent conformance gate, plus an outcome-first, one-decision-per-ask handoff protocol. |
| `prior-art-problem-loop` | [`skills/prior-art-problem-loop/SKILL.md`](skills/prior-art-problem-loop/SKILL.md) | Research a new topic, diagnose a workflow bottleneck or evaluate a design idea: benchmark prior art, blunt MECE check, goal-aligned logic tree. |
| `project-collab-method` | [`skills/project-collab-method/SKILL.md`](skills/project-collab-method/SKILL.md) | Start or onboard a project, dispatch or accept work, or report results across multiple agents: one owner per document, fixed handoff order, hard pass gate, conflicts to the human first, owning agent reports directly. |

## Quick Install

One-liner copy into your agent's skills directory (example for Claude Code / Codex):

```bash
git clone --depth 1 https://github.com/mfang0126/intent-skills.git /tmp/intent-skills && cp -R /tmp/intent-skills/skills/website-benchmark-align ~/.claude/skills/
```

Or manage and sync across Claude Code, Codex, Pi, and other agents via **Magpie** by adding `mfang0126/intent-skills` as a GitHub skill source and running `magpie library skill update website-benchmark-align && magpie library sync`.

## License

MIT
