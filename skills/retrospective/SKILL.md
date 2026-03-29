---
name: retrospective
description: Run a structured retrospective for a sprint, project or initiative. Use when asked to facilitate a retro, reflect on what worked and what didn't, run a lessons learned session or improve team processes.
---

# Retrospective

Facilitate a structured retrospective that surfaces what went well, what didn't and — most importantly — what to change. A retro without action items is just venting.

## Before Running

Ask (skip what's already known):

1. **What's the scope?** — Sprint retro, project retro, incident retro, quarterly review?
2. **Who's participating?** — PM, engineering, design, cross-functional?
3. **What happened?** — Brief summary of the period or project being reviewed.
4. **Were there previous retro actions?** — Follow up on commitments from the last retro.

## Retro Formats

Pick the format that fits the situation. Variety prevents staleness.

### Standard (What Went Well / What Didn't / Actions)
Best for: Regular sprint retros. Simple and reliable.

```
## Retrospective: [Sprint/Project] — [Date]

### What went well
- [Celebrate successes — be specific about what and why]

### What didn't go well
- [Be specific about what happened, not who's to blame]

### What was confusing or unclear
- [Ambiguities, misunderstandings, process gaps]

### Action items
| Action | Owner | Due |
|--------|-------|-----|
| [Specific change to make] | [Name] | [Date] |
```

**Limit to 1-3 action items.** More than that and nothing changes.

### Start / Stop / Continue
Best for: When the team needs to evaluate current practices.

```
## Start / Stop / Continue — [Date]

### Start doing
- [New practice or behavior to adopt]

### Stop doing
- [Practice that's not working — be specific about why]

### Continue doing
- [What's working well — explicitly name it so it doesn't get dropped]

### Action items
| Action | Owner | Due |
|--------|-------|-----|
```

### 4 Ls (Liked / Learned / Lacked / Longed For)
Best for: Project retros or when the team needs a more reflective format.

```
## 4 Ls Retrospective: [Project] — [Date]

### Liked
- [What the team enjoyed or found satisfying]

### Learned
- [New insights, skills or knowledge gained]

### Lacked
- [What was missing — resources, clarity, support, tools]

### Longed for
- [What the team wishes they'd had — aspirational]

### Action items
| Action | Owner | Due |
|--------|-------|-----|
```

### Incident / Failure Retro
Best for: When something went wrong and needs root cause analysis.

```
## Incident Retrospective: [What happened] — [Date]

### Timeline
| Time | What happened |
|------|--------------|
| [timestamp] | [Event] |

### What went wrong
- [Root cause — dig past symptoms to underlying causes]

### What went right
- [How the team responded, what prevented it from being worse]

### Contributing factors
- [Process gaps, communication failures, technical debt, unclear ownership]

### Action items
| Action | Owner | Due | Prevents recurrence of |
|--------|-------|-----|----------------------|
```

**For incidents, use "5 Whys":** Ask "why?" five times to get from the symptom to the root cause.
- Symptom: "The agent gave wrong policy information"
- Why? "It pulled from an outdated policy document"
- Why? "The document wasn't updated when the policy changed"
- Why? "There's no process to sync policy updates to the agent's data sources"
- Why? "Document management was out of scope for V1"
- Root cause: Missing content update process. Action: build one.

## Facilitation Tips

1. **Create safety.** People must feel safe to be honest. Start by naming that this is a blame-free zone. Focus on systems and processes, not individuals.
2. **Write independently first.** Give 5 minutes of silent writing before discussion. Prevents groupthink and ensures quieter voices are heard.
3. **Time-box.** Sprint retros: 30-45 minutes. Project retros: 60-90 minutes. More than that and energy drops.
4. **Follow up on previous actions.** Start every retro by reviewing what was committed last time. If actions aren't followed up on, people stop proposing them.
5. **Rotate facilitators.** The PM doesn't always have to run it. Different facilitators bring different energy.
6. **Vary the format.** Using the same format every sprint leads to autopilot. Rotate between formats.

## Writing Conventions

- Be specific. "Communication could be better" is useless. "The design handoff lacked acceptance criteria, which caused rework" is actionable.
- Celebrate wins explicitly. Retros that only focus on problems are demoralizing. What went well matters.
- Every action item needs an owner and a due date. Unowned actions don't happen.
- Keep the retro doc short and scannable. It's a working document, not a report.
