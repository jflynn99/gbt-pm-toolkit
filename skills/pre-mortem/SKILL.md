---
name: pre-mortem
description: Run a pre-mortem exercise to identify what could go wrong before launch. Use when preparing for a launch, kicking off a risky project, stress-testing a plan or when the team needs to surface concerns they're not voicing.
---

# Pre-Mortem

Imagine the project has already failed. Now figure out why. A pre-mortem surfaces risks, assumptions and blind spots *before* they become real problems — when you can still do something about them.

## Before Running

Ask (skip what's already known):

1. **What's the project or launch?** — Feature, agent, product, initiative?
2. **When is the launch?** — How much time do we have to mitigate?
3. **Who's involved?** — PM, engineering, design, stakeholders?
4. **What does success look like?** — We need to know what "it worked" means before we can imagine "it failed."

## Pre-Mortem Structure

### The Setup
```
## Pre-Mortem: [Project Name]
**Date:** [date]
**Scenario:** It's [launch date + 3 months]. The project has failed.
Users aren't using it, stakeholders are frustrated, and the team is doing a postmortem.

**What went wrong?**
```

### Step 1: Generate Failure Scenarios
For each, describe a plausible way the project could fail:

| # | Failure scenario | Category | Likelihood | Impact |
|---|-----------------|----------|-----------|--------|
| 1 | [What went wrong] | [See categories below] | High/Med/Low | High/Med/Low |

**Failure categories:**
- **User adoption** — They don't use it, don't find it, don't understand it
- **Quality/accuracy** — It doesn't work well enough, too many errors
- **Scope** — We built too much (late) or too little (underwhelming)
- **Dependencies** — Another team, system or vendor didn't deliver
- **Communication** — Stakeholders were surprised, users weren't prepared
- **Technical** — Performance issues, integration failures, data problems
- **Compliance/legal** — Regulatory issue, privacy concern, policy violation
- **Resourcing** — Key person left, team got pulled to another priority
- **Market/timing** — Competitor moved faster, user needs shifted, budget cut

### Step 2: Identify the Top Risks
Pick the 3-5 failure scenarios that are most likely AND most impactful. These are your real risks.

### Step 3: Build Mitigations

For each top risk:

```
### Risk: [Failure scenario]
**Likelihood:** [High/Med/Low]
**Impact:** [High/Med/Low]

**Early warning signs:**
- [What would we see if this was starting to happen?]

**Mitigation plan:**
- [Specific action to reduce likelihood or impact]
- [Owner and timeline]

**Contingency (if it happens anyway):**
- [What we'd do to recover]
```

### Step 4: Action Items
```
### Pre-Mortem Actions
| Action | Owner | Due | Risk it addresses |
|--------|-------|-----|------------------|
| [Specific task] | [Name/role] | [Date] | [Which failure scenario] |
```

## GBT-Specific Failure Modes

When running pre-mortems for GBT projects, always consider:

- **"Nobody uses it"** — The tool is built but Travel Managers stick to their old workflow. Why? Training gap? Not solving a real pain? Too hard to find?
- **"It works in testing, fails in production"** — Test cases covered happy paths but real travelers ask questions we never anticipated.
- **"Client data incident"** — Even a perceived data leak between clients destroys trust. One incident can undo months of work.
- **"Policy got it wrong"** — The agent gave incorrect policy guidance and a traveler booked a non-compliant trip. Who's liable?
- **"Competitor shipped first"** — Navan or another competitor launched a similar feature while we were still in Phase 3.
- **"Stakeholder pulled the plug"** — Budget review or reorg killed the project. Did we build enough incremental value along the way?

## Facilitation Tips

If running this as a team exercise:

1. **Make it safe.** People need permission to be pessimistic. Frame it as "smart risk management" not "negativity."
2. **Write independently first.** Have each person write their failure scenarios before sharing. Prevents groupthink.
3. **No dismissing.** Every scenario gets recorded. Evaluate likelihood and impact later, not during brainstorming.
4. **Focus on controllable risks.** "The economy collapses" isn't useful. "Our key engineer leaves mid-project" is.
5. **End with actions.** A pre-mortem without mitigation actions is just anxiety. Always close with concrete next steps.

## Writing Conventions

- Be specific about failure scenarios — "users don't adopt it" is too vague. "Travel Managers at companies with fewer than 100 travelers don't see enough value to change their workflow" is actionable.
- Every risk needs an early warning sign. If you can't spot it coming, you can't react in time.
- Keep mitigations to actions you can actually take, not things you hope will happen.
