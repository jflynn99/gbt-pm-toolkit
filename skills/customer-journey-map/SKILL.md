---
name: customer-journey-map
description: Map the end-to-end customer experience across touchpoints. Use when mapping a user journey, identifying experience gaps, analyzing a workflow, understanding where users struggle or planning improvements across a multi-step process.
---

# Customer Journey Map

Map the end-to-end experience for a specific persona across all touchpoints. Journey maps reveal where the experience breaks down, where users feel frustrated and where the biggest improvement opportunities are.

## Before Mapping

Ask (skip what's already known):

1. **Which persona?** — A journey map is for one persona at a time. Different personas have different journeys.
2. **What journey?** — End-to-end experience, a specific workflow, onboarding, a failure/recovery scenario?
3. **What's the scope?** — From first awareness to loyal user? Or a specific slice (e.g. booking a trip, setting up policies)?
4. **What data exists?** — Analytics, user research, support tickets, session recordings?

## Journey Map Structure

### Overview
```
## Journey Map: [Persona] — [Journey Name]
**Scope:** [Start point] to [End point]
**Date:** [date]
**Data sources:** [What this is based on]
```

### The Map

For each stage of the journey:

| Stage | User action | Touchpoint | Thinking | Feeling | Pain points | Opportunities |
|-------|-----------|-----------|---------|---------|-------------|---------------|
| [Phase name] | [What they do] | [Where/how] | [What's on their mind] | [Emotional state] | [Friction, confusion, frustration] | [How to improve] |

### Emotional Arc
Plot the user's emotional state across the journey:

```
😊 Positive  ─────╮          ╭─────────────
                   │          │
😐 Neutral   ──────│──────────│──────────────
                   │          │
😤 Frustrated ─────╰──────────╯─────────────
               Stage 1  Stage 2  Stage 3  Stage 4
```

The low points are your biggest opportunities.

### Key Findings
```
### Biggest pain points (ranked by severity)
1. [Pain] at [stage] — affects [X% of users / happens Y times per week]
2. [Pain] at [stage]
3. [Pain] at [stage]

### Moments of delight
1. [What works well] at [stage]

### Gaps
- [Where the experience breaks or users fall through the cracks]

### Opportunities (ranked by impact)
1. [Improvement] at [stage] — estimated impact: [description]
2. [Improvement] at [stage]
```

## GBT Journey Examples

### Traveler Booking Journey
```
Stages: Need to travel → Search → Book → Pre-trip → Travel → Post-trip → Expense

Key touchpoints: Email/calendar, booking tool, mobile app, airport,
hotel, expense system, approval workflow
```

### Travel Manager Onboarding Journey
```
Stages: Contract signed → Account setup → Policy configuration →
User rollout → First bookings → Optimization → Renewal

Key touchpoints: Account manager, admin portal, configuration wizard,
training materials, reports, support
```

### Policy Question Journey
```
Stages: Question arises → Search for answer → Find source →
Interpret policy → Make decision → Validate (or escalate)

Key touchpoints: Intranet, policy docs, chatbot, HR, Travel Manager,
booking tool policy display
```

## Mapping Tips

### Data Sources to Draw From
- **Analytics:** Where do users drop off? Which pages have high bounce rates? Where do they get stuck?
- **Support tickets:** What questions come up most? At which stage?
- **User interviews:** What do users say about each stage? Where do they express frustration or confusion?
- **Session recordings:** What do users actually do (vs. what they say they do)?
- **Sales/account team feedback:** What do prospects and clients complain about?

### Common Mistakes
- **Mapping the ideal journey, not the real one.** Include the workarounds, dead ends and frustrations. That's where the value is.
- **Too many stages.** 4-7 stages is the sweet spot. More granularity goes into sub-journeys.
- **Skipping emotions.** The "Feeling" column is where the real insights live. A functionally correct experience can still feel terrible.
- **No prioritization.** Not every pain point is worth fixing. Rank by severity and frequency.
- **One and done.** Journeys change as the product evolves. Revisit after major launches or when user research reveals new patterns.

## Writing Conventions

- One persona per map. A map that tries to cover everyone covers no one.
- Be specific about touchpoints — "the app" is too vague. "The search results page on mobile after selecting dates" is useful.
- Include both what users *do* and what they *feel*. Actions without emotions miss half the picture.
- Rank opportunities by impact, not by ease. Easy wins are nice but shouldn't overshadow high-impact improvements.
