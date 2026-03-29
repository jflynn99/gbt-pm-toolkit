---
name: metrics-review
description: Define or review success metrics and KPIs. Use when asked about metrics, KPIs, success criteria, measurement approaches, OKRs or when reviewing whether any product feature, platform capability or AI agent is performing well.
---

# Metrics Review

Help define, review or critique success metrics for AI features and products. Good metrics drive good decisions — vague ones drive nothing.

## Before Writing

Ask (skip what's already known):

1. **What are we measuring?** — A specific agent, feature, product or team?
2. **What's the context?** — Defining metrics for a new project, reviewing existing performance, preparing a quarterly review?
3. **What data is available?** — Paste numbers, share a dashboard screenshot or describe what's tracked.
4. **Are there existing targets?** — Goals, OKRs or benchmarks to compare against?

## Metrics Hierarchy

Structure metrics in three layers:

### North Star Metric
The single metric that best captures the core value delivered to users. It should be:
- **Value-aligned** — moves when users get more value
- **Leading** — predicts long-term business success
- **Actionable** — the product team can influence it
- **Understandable** — everyone knows what it means

### L1 Health Metrics (5-7 max)
The key indicators that together paint a complete picture:

| Category | What it measures | Example for AI agents |
|----------|-----------------|----------------------|
| **Adoption** | Are users finding and using it? | % of eligible users who've tried the agent |
| **Activation** | Are they reaching the value moment? | % who get a useful answer on first interaction |
| **Engagement** | Are active users getting value? | Queries per user per week, repeat usage |
| **Accuracy** | Is it giving correct answers? | % of responses rated accurate by evaluators |
| **Satisfaction** | How do users feel about it? | CSAT, NPS, thumbs up/down ratio |
| **Efficiency** | Is it saving time/cost? | Support ticket deflection rate, time saved |

### L2 Diagnostic Metrics
Detailed metrics for investigating changes in L1:
- Funnel conversion at each step
- Segment breakdowns (by client size, region, user type)
- Error rates and failure modes
- Response latency and performance

## Travel/TMC-Specific Metrics

When reviewing GBT products, consider the domain:

**Platform/booking metrics:**
- Booking completion rate (searches that result in a confirmed booking)
- Time to book (from search to confirmation)
- Adoption rate (% of eligible travelers using the online tool vs. calling)
- Policy compliance rate (% of bookings within policy)
- Mobile vs. desktop usage split
- Search-to-book conversion by channel
- Preferred supplier attachment rate

**Traveler experience metrics:**
- NPS / CSAT by touchpoint (booking, support, post-trip)
- Self-service resolution rate
- Average handle time for support interactions
- Traveler app engagement (sessions per trip)

**AI agent metrics:**
- Response accuracy rate
- Hallucination rate (incorrect or fabricated information)
- Refusal accuracy (correctly declining out-of-scope requests)
- Escalation rate (how often the agent hands off to a human)
- Response latency
- Support ticket deflection rate
- Cost per interaction (agent vs. human)

**Guardrail metrics** (must not get worse):
- Client data isolation (zero cross-client data leaks)
- Compliance adherence
- Duty of care accuracy (correct information during disruptions)
- Booking accuracy (no incorrect itineraries)

## Output Formats

### For defining metrics (new project)
```
## [Project] — Success Metrics

### North Star
[Metric]: [Target] by [date]

### L1 Health Metrics
| Metric | Current | Target | How measured |
|--------|---------|--------|-------------|
| [metric] | [baseline or TBD] | [target] | [tool/method] |

### Guardrails
| Metric | Threshold | Why it matters |
|--------|-----------|---------------|
| [metric] | Must not drop below [X] | [consequence if violated] |
```

### For reviewing metrics (existing data)
```
## [Project] — Metrics Review ([period])

### Summary
[2-3 sentences: overall health, most notable change, key callout]

### Scorecard
| Metric | Current | Previous | Change | Target | Status |
|--------|---------|----------|--------|--------|--------|
| [metric] | [value] | [value] | [+/- %] | [target] | [On track / At risk / Miss] |

### Bright Spots
- [What's working well]

### Areas of Concern
- [What needs attention]

### Recommended Actions
- [Specific next steps]
```

## Writing Conventions

- Always show context: current value + comparison (previous period, target, benchmark). A number alone is useless.
- Be careful about attribution — correlation is not causation
- Not all metric movements matter. Small fluctuations are noise. Focus on meaningful changes.
- If a metric is missing its target, don't just report the miss — recommend what to do about it
- Segment analysis often reveals that an aggregate metric masks important differences
