# UX Review Skills for Claude

Three skills that turn Claude into a structured UX reviewer. Each one applies a different classic lens, and all three add extra scrutiny for screens where people **review and act on AI output**: summaries, generated content awaiting approval, telemetry, reconciliation queues.

| Skill | Lens | Best for |
|---|---|---|
| `nielsen-heuristics-review` | Jakob Nielsen's 10 usability heuristics | A fast, broad usability pass |
| `laws-of-ux-review` | Laws of UX (Jon Yablonski): perception, cognition, decision-making | Dense data screens, attention and bias problems |
| `tog-principles-review` | Bruce Tognazzini's First Principles of Interaction Design | Deep dives on control, defaults, state, latency, and protecting the user's work |

All three use the same **0–4 severity scale** and the same table-style output, so you can run them together and merge the findings into one prioritized list.

## What you get

Each review returns:

- A one-sentence statement of the screen's job (who decides what, based on which output)
- A findings table with evidence, severity, and a buildable recommendation per row
- The top 3 fixes, ranked by severity × frequency
- Strengths worth keeping

Severity is raised one level when an issue makes it likelier that someone acts on wrong AI output without noticing.

## Install

### Claude Code (recommended)

```
/plugin marketplace add matomaton/ux-review-skills
/plugin install ux-review@ux-review-skills
```

### Claude Code (manual)

Copy any folder from [`plugins/ux-review/skills/`](plugins/ux-review/skills) into `~/.claude/skills/` (personal) or `.claude/skills/` in a project.

### Claude.ai / Claude Desktop

1. Download a skill folder (for example `nielsen-heuristics-review`) and zip it.
2. Go to **Settings → Capabilities → Skills** and upload the zip.

## Usage

Attach a screenshot, Figma link, HTML file, or a written description of a flow, then ask:

- "Run a Nielsen heuristics review on this screen."
- "Review this approval queue with the Laws of UX. Reviewers process about 200 items a day."
- "Do a quick Tog principles review of this dashboard." (`quick` gives top principles only; the default is `deep`.)
- "Run all three reviews and merge the findings into one top-5 list."

Give context if you have it: the user's role, the decision they make on the screen, and what it costs to get it wrong. If you don't, the skill states its assumptions and carries on.

## Sources

- Jakob Nielsen, [10 Usability Heuristics for User Interface Design](https://www.nngroup.com/articles/ten-usability-heuristics/)
- Jon Yablonski, [Laws of UX](https://lawsofux.com/)
- Bruce Tognazzini, [First Principles of Interaction Design](https://asktog.com/atc/principles-of-interaction-design/)

The skills paraphrase these frameworks. They aren't affiliated with or endorsed by the original authors.

## License

[MIT](LICENSE)
