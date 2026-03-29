---
name: product-brainstorm
description: Structured ideation for new features, products or improvements. Use when brainstorming ideas, exploring opportunities, running a Jobs-to-Be-Done analysis or evaluating whether a feature idea is worth pursuing.
---

# Product Brainstorm

Structured ideation for new features, products and improvements at GBT. Moves beyond "wouldn't it be cool if..." to opportunities grounded in real user needs and feasibility. Works for AI agents, platform features, booking flows, TM tools — any product work.

## Before Brainstorming

Ask (skip what's already known):

1. **What's the starting point?** — A user problem, a vague idea, a competitor feature, a stakeholder request?
2. **Who's the target persona?** — Travel Manager, business traveler, arranger, finance?
3. **What constraints exist?** — Timeline, data availability, compliance, technical limitations?
4. **What's the goal?** — Explore broadly, evaluate a specific idea, or prioritize among several?

## Brainstorm Frameworks

Use the most appropriate framework for the situation. Don't force all of them — pick the one that fits.

### Jobs-to-Be-Done (JTBD)
Best for: understanding what users actually need (not what they say they want).

For each persona, map:

| Job type | The job | Current solution | Pain with current solution |
|----------|---------|-----------------|--------------------------|
| **Functional** | What they're trying to accomplish | How they do it today | What's slow, broken or missing |
| **Social** | How they want to appear to others | How they manage perceptions | Where they feel exposed or unsupported |
| **Emotional** | How they want to feel | What gives them confidence today | What causes anxiety or frustration |

**GBT examples (AI):**
- TM functional: "Set up travel policies quickly so I can move on to other work"
- Traveler emotional: "Feel confident the program is running correctly without checking everything manually"

**GBT examples (platform/product):**
- Traveler functional: "Book a compliant trip in under 3 minutes on my phone"
- Arranger social: "Look competent when booking for executives — no mistakes"
- Finance functional: "Reconcile travel spend against budget without manual data wrangling"

### Opportunity Solution Tree
Best for: connecting a desired outcome to concrete solutions.

```
Desired Outcome (metric we want to move)
├── Opportunity 1 (user need or pain point)
│   ├── Solution A
│   │   └── Experiment: [how to validate cheaply]
│   └── Solution B
│       └── Experiment: [how to validate cheaply]
├── Opportunity 2
│   ├── Solution C
│   └── Solution D
└── Opportunity 3
    └── Solution E
```

Every solution should have a low-effort validation experiment before committing to build.

### How Might We (HMW)
Best for: reframing problems as opportunities.

Take a pain point and reframe it:
- Pain: "Travel Managers waste hours searching policy documents"
- HMW: "How might we surface the right policy answer instantly when a TM needs it?"
- HMW: "How might we reduce the number of policy questions TMs get in the first place?"
- HMW: "How might we make policy documents self-service without AI?"

Generate 3-5 HMW statements per pain point. The best ones open up solution space without prescribing a specific answer.

## Feasibility Check

For every promising idea, run a quick feasibility assessment against the GBT lifecycle:

| Question | Answer | Risk level |
|----------|--------|-----------|
| **Data:** What data or integrations would this need? Do they exist? | | |
| **Compliance:** Does this touch sensitive data or regulated decisions? | | |
| **Multi-market:** Does this need to work across regions, languages or client configurations? | | |
| **Dependencies:** Does this depend on other teams, vendors or platform changes? | | |
| **Effort:** Is this a quick win, a quarter-long project or a multi-quarter bet? | | |

For AI features, also assess:
| **Accuracy:** What happens if the AI gets it wrong? | | |
| **Isolation:** Does this need client-by-client data separation? | | |
| **Fallback:** What's the human fallback when the AI fails? | | |

Ideas that score high risk on compliance or data need extra scrutiny. AI features will also face the Risk Committee (Phase 6).

## Output Format

### For broad exploration
Generate 5-8 opportunity areas with 2-3 solution ideas each. Rank by estimated impact and feasibility.

### For evaluating a specific idea
```
## [Idea Name]

### The opportunity
[What user need does this address? Which persona? How painful is it today?]

### Proposed approach
[High-level description — what would this do?]

### Feasibility assessment
[Quick check against the table above]

### Risks and unknowns
[Top 2-3 concerns]

### Recommended next step
[Validate with user research / Build a prototype / Write a spec / Park it]
```

### For prioritizing among ideas
| Idea | Persona | Impact | Feasibility | Risk | Recommendation |
|------|---------|--------|------------|------|----------------|
| [idea] | [who] | High/Med/Low | High/Med/Low | High/Med/Low | Build / Explore / Park |

## Writing Conventions

- Be opinionated about which ideas are strongest — don't present everything as equal
- Ground every idea in a real user need, not a technology capability
- "We could use AI to..." is a solution looking for a problem. Start with the problem.
- Include at least one "boring" idea alongside the ambitious ones. Sometimes the highest-impact solution is the simplest.
