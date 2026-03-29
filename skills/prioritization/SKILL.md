---
name: prioritization
description: Prioritize features, ideas or work items using structured frameworks. Use when asked to prioritize a backlog, compare ideas, decide what to build next, apply RICE/ICE/MoSCoW or any prioritization exercise.
---

# Prioritization

Apply structured prioritization frameworks to rank features, ideas or work items. The right framework depends on the context — this skill helps you pick the right one and apply it consistently.

## Before Prioritizing

Ask (skip what's already known):

1. **What are we prioritizing?** — Features, bugs, ideas, backlog items, initiatives?
2. **How many items?** — 3-5 items can be gut-ranked. 10+ needs a framework.
3. **What are the constraints?** — Timeline, team capacity, dependencies, budget?
4. **Who are the stakeholders?** — Whose input matters and who makes the final call?
5. **What matters most?** — User impact, revenue, strategic alignment, speed to market?

## Framework Selector

| Situation | Recommended framework |
|-----------|---------------------|
| Comparing 5+ features with different tradeoffs | **RICE** — most comprehensive scoring |
| Quick ranking needed, limited data | **ICE** — fast and intuitive |
| Scoping a release (what's in vs. out) | **MoSCoW** — clear categories |
| Understanding what delights vs. what's expected | **Kano** — user satisfaction model |
| Complex decision with many stakeholders | **Weighted Scoring** — customizable criteria |
| Two options, need to pick one | **Pros/Cons + Decision Criteria** — simplest |

## Frameworks

### RICE
Score each item on four dimensions, then calculate priority:

| Item | Reach | Impact | Confidence | Effort | RICE Score |
|------|-------|--------|-----------|--------|-----------|
| [Feature] | [users/quarter] | [0.25/0.5/1/2/3] | [50-100%] | [person-months] | R x I x C / E |

**Reach:** How many users will this affect in a given time period?
**Impact:** How much will it affect each user? (0.25 = minimal, 3 = massive)
**Confidence:** How sure are you about your estimates? (50% = guess, 100% = data-backed)
**Effort:** How much work? (person-months or story points)

**Tips:**
- Be honest about Confidence. Most PMs overrate it.
- Effort should include design, engineering, QA and rollout — not just coding.
- A high-RICE item with low confidence might need research before building.

### ICE
Faster than RICE. Score each dimension 1-10:

| Item | Impact | Confidence | Ease | ICE Score |
|------|--------|-----------|------|----------|
| [Feature] | [1-10] | [1-10] | [1-10] | I x C x E |

Best for quick prioritization when you don't have precise reach or effort data.

### MoSCoW
Categorize items into four buckets:

| Category | Definition | Rule of thumb |
|----------|-----------|--------------|
| **Must have** | Without this, the release is not viable | If you cut it, does the product still solve the core problem? |
| **Should have** | Important but not critical for launch | High-priority fast follow |
| **Could have** | Desirable if time permits | Won't delay delivery if cut |
| **Won't have** | Explicitly out of scope this time | May revisit in future versions |

**Tips:**
- Be ruthless about Must-haves. If everything is Must, nothing is.
- Won't-haves are as valuable as Must-haves — they prevent scope creep.
- Write down *why* each Won't-have is deferred.

### Kano Model
Categorize features by their effect on user satisfaction:

| Category | If present | If absent | Examples |
|----------|-----------|-----------|---------|
| **Basic (must-be)** | No extra satisfaction | Major dissatisfaction | Login works, pages load, data is accurate |
| **Performance (more is better)** | Satisfaction scales with quality | Dissatisfaction scales with lack | Speed, search relevance, report depth |
| **Delighters (attractive)** | Unexpected satisfaction | No dissatisfaction | Smart suggestions, proactive alerts, beautiful UI |

**When to use Kano:** When you're deciding between "fix the basics" and "build something exciting." Basics first — delighters on a broken foundation don't delight anyone.

### Weighted Scoring
Define custom criteria and weights:

| Item | Criterion A (w: 3) | Criterion B (w: 2) | Criterion C (w: 1) | Weighted Score |
|------|-------------------|-------------------|-------------------|---------------|
| [Feature] | [1-5] | [1-5] | [1-5] | Sum(score x weight) |

**When to use:** When stakeholders disagree on what matters. Making criteria and weights explicit forces alignment on values before scoring items.

## Output Format

### For a prioritized backlog
```
## Prioritization: [Context]
**Framework:** [Which one and why]
**Date:** [date]

### Tier 1 (Do Now)
1. [Item] — Score: [X]. [Why it's top priority]
2. [Item] — Score: [X]. [Why]

### Tier 2 (Do Next)
3. [Item] — Score: [X]. [Why]
4. [Item] — Score: [X]. [Why]

### Tier 3 (Do Later / Investigate)
5. [Item] — Score: [X]. [Why]

### Explicitly Deferred
- [Item] — [Why not now]

### Key Tradeoffs
- [Decision that was hard and why you landed where you did]
```

## Common Mistakes

- **Prioritizing without criteria.** If you don't define what matters, the loudest voice wins.
- **Scoring everything high.** If everything is a 9/10 impact, your scale is broken. Force yourself to differentiate.
- **Ignoring effort.** A high-impact feature that takes 6 months may be lower priority than a medium-impact feature that takes a week.
- **Framework worship.** The framework is a thinking tool, not a decision machine. If the output doesn't feel right, investigate why — don't just override it or blindly follow it.
- **Prioritizing once.** Priorities change as you learn. Re-prioritize quarterly at minimum.

## Writing Conventions

- Show the scoring, not just the result. Stakeholders need to see *why* items are ranked the way they are.
- Be explicit about tradeoffs — what you're giving up by choosing this order.
- If two items score similarly, call it out and explain the tiebreaker.
- Include the "explicitly deferred" list — it prevents the same items from being re-debated.
