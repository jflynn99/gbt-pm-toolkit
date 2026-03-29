# GBT PM Toolkit

A set of Claude Code skills for Product Managers at AMEX GBT. These skills accelerate common PM workflows and embed business travel domain context so you spend less time explaining your world and more time doing the work.

## What's Included

### Core PM Skills

| Skill | Command | What it does |
|-------|---------|-------------|
| Write Spec | `/write-spec` | PRDs and product specs with GBT lifecycle structure |
| Eval Test Cases | `/eval-test-cases` | AI evaluation test cases for Phase 5 |
| Stakeholder Update | `/stakeholder-update` | Status comms tailored by audience |
| Synthesize Research | `/synthesize-research` | Research synthesis with "So what for GBT?" lens |
| Meeting Prep | `/meeting-prep` | Prep briefs for AI Forum, Risk Committee, 1:1s, team syncs |

### Strategic Skills

| Skill | Command | What it does |
|-------|---------|-------------|
| Competitive Brief | `/competitive-brief` | Competitive analysis with TMC landscape context |
| Metrics Review | `/metrics-review` | Define or review KPIs and success metrics |
| Sprint Planning | `/sprint-planning` | Plan iterations aligned to the 7-phase lifecycle |
| Playbook Author | `/playbook-author` | Write AI Playbook content for PMs across the business |

### Background References (auto-loaded)

These load automatically to give Claude context about GBT and the AI project lifecycle. You don't invoke them directly — they just make everything smarter.

- **GBT Domain Context** — Company overview, traveler personas, TMC dynamics, compliance landscape, competitive frame
- **GBT Lifecycle** — 7-phase AI project lifecycle, PM responsibilities, CRISP-DM mapping

### Agents

- **VP of Product** (`/agent:vp-product`) — An experienced product leader persona for pressure-testing PRDs, metrics and stakeholder framing

## Setup

### Option 1: Claude Code Plugin (recommended)

Add this to your `~/.claude/settings.json` under `plugins`:

```json
{
  "plugins": [
    "C:/Users/[your-username]/path/to/gbt-pm-toolkit"
  ]
}
```

Skills will be available as `gbt-pm-toolkit:write-spec`, `gbt-pm-toolkit:eval-test-cases`, etc. Or just describe what you need in natural language and Claude will pick the right skill.

### Option 2: Copy to Personal Skills

Copy the contents of `skills/` into your `~/.claude/skills/` directory and `agents/` into `~/.claude/agents/`.

## Usage

You don't need to memorize commands. Just describe what you need:

- "Write a spec for a new traveler notification agent"
- "Generate eval test cases for the FAQ LLM"
- "Prep me for the Risk Committee meeting on Thursday"
- "Summarize these notes and tell me what matters for GBT"
- "Write an update on the TM Onboarding project for leadership"
- "How does GBT compare to Navan on AI features?"
- "Help me define success metrics for the policy Q&A agent"
- "Plan the next sprint for the TM Onboarding project"
- "Write a new playbook section on prompt engineering for PMs"

## Contributing

Found a gap? Want to add a new skill? PRs welcome. Keep skills:
- Under 5KB (concise and scannable)
- In American English
- Free of personal references (names, personal file paths)
- Focused on PM workflows at GBT

## License

Internal use at AMEX GBT. Skills are remixed from open-source sources (Apache 2.0, MIT) with original GBT-specific content.
