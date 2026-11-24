# intent-skills

Minimalist, intent-based, token-efficient [Agent Skills](https://agentskills.io/) designed for reuse across AI coding and assistant workflows (Claude Code, Codex, Pi, Cursor, and other SKILL.md-compatible agents).

## Philosophy

- **Intent first**: Start from the user and business outcome, then work top-down to structure, layouts, and implementation details.
- **Minimal and token-efficient**: Keep each skill short, self-contained, and focused on decision rules rather than bloated playbooks.
- **Project-agnostic**: Every skill is stripped of project-specific paths, client details, and tool lock-in so it drops cleanly into any repository or agent library.
- **Evidence before code**: Align on scope, "done" criteria, and verified facts before writing code.

## Skills Catalog

| Skill | Path | When to use |
| --- | --- | --- |
| `website-benchmark-align` | [`skills/website-benchmark-align/SKILL.md`](skills/website-benchmark-align/SKILL.md) | Align on a website's structure, redesign, or "done" bar against a benchmark site across 4 layers (User Journey, Pages, Layouts, Components) before writing code. |

## Usage

Each skill lives under `skills/<skill-name>/SKILL.md` with standard YAML frontmatter (`name`, `description`):

- **Agent skill managers (e.g. Magpie)**: Add `mfang0126/intent-skills` as a GitHub skill source and enable the desired skill(s) for your agents.
- **Manual / local install**: Copy `skills/<skill-name>/` into your agent's skills directory (for example `~/.agents/skills/<skill-name>/` or `.claude/skills/<skill-name>/`).

## License

MIT
