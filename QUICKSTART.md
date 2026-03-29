# GBT PM Toolkit — Quickstart

Just describe what you need in plain English. The right skill kicks in automatically and asks clarifying questions before generating output.

## Skills Cheat Sheet

| Just say... | What happens |
|-------------|--------------|
| "Write a spec for [feature]" | Asks about the problem, persona, success criteria, then generates a PRD |
| "Write test cases for [agent]" | Asks about the agent and its boundaries, then generates a structured eval set |
| "Write an update on [project] for [audience]" | Asks who it's for, picks the right template (exec, team, forum, manager) |
| "Summarize these notes" | Asks for the lens, produces findings with a "So what for GBT?" section |
| "Prep me for [meeting]" | Asks the meeting type, generates a brief with likely Q&A |
| "How do we compare to [competitor]?" | Asks the focus area, builds a structured competitive analysis |
| "Define success metrics for [feature]" | Asks context, produces North Star + L1/L2 hierarchy with targets |
| "Plan the next sprint for [project]" | Asks scope and capacity, generates a prioritized sprint plan |
| "Write a playbook section on [topic]" | Asks the audience and format, writes in the playbook voice |
| "Brainstorm ideas for [problem]" | Asks the persona and constraints, runs JTBD/HMW/Opportunity Tree |
| "Prep for Risk Committee on [agent]" | Asks about eval results, generates full risk matrix and narrative |
| "Prepare interview questions for [persona]" | Asks research goal and time, generates a Mom Test-based script |
| "Create personas for [product]" | Asks what research exists, builds 3-5 evidence-based personas |
| "Prioritize these features" | Recommends the right framework (RICE/ICE/MoSCoW/Kano), scores items |
| "Run a pre-mortem on [project]" | Generates failure scenarios with mitigations before launch |
| "Write release notes for [feature]" | Asks the audience, generates the right format (user/client/internal/sales) |
| "Run a retro on [sprint/project]" | Picks a retro format, generates structured output with action items |
| "Map the journey for [persona doing X]" | Maps stages with actions, emotions, pain points and opportunities |

## Agents

Agents are personas you can ask for a specific perspective:

| Just say... | What you get |
|-------------|-------------|
| "Run this past the VP" | A senior product leader pressure-tests your work — catches gaps in metrics, edge cases and framing |
| "Explain [technical thing] in PM terms" | Translates AI/engineering concepts into plain English with analogies |

You can also invoke them directly: `/agent:vp-product` or `/agent:ai-team-translator`

## Background References (you never need to touch these)

Two reference files load automatically into every conversation:

- **GBT Domain Context** — Claude already knows GBT is a TMC, who the personas are (Travel Managers, business travelers, arrangers, finance), what NDC and duty of care mean, who the competitors are, and what compliance matters.
- **GBT Lifecycle** — Claude already knows the 7-phase AI project lifecycle, which phases PMs own, what artifacts are expected at each phase, and how it maps to CRISP-DM.

You never invoke these. You never need to explain "we're a travel management company" or "we have a 7-phase process." Claude just knows. It uses this context to make every other skill smarter and more relevant to GBT.

## Tips

- **You don't need to memorize commands.** Just describe what you need naturally. Claude matches to the right skill.
- **Skills ask before they generate.** They'll ask 2-4 clarifying questions, then produce structured output. Skip questions by providing context upfront.
- **Skills cross-reference each other.** After writing a spec, it'll suggest running it past the VP agent. After generating test cases, it'll suggest using stakeholder-update to report results.
- **Everything works for non-AI work too.** The core skills (specs, updates, sprints, metrics) work for platform features, booking flows, TM tools — not just AI agents.
