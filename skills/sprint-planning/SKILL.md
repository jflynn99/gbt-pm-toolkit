---
name: sprint-planning
description: Plan a sprint or work iteration. Use when asked to plan a sprint, break down work, prioritize tasks for a time period or structure an iteration cycle for an AI project.
---

# Sprint Planning

Help plan iteration cycles for AI projects, structure work sprints and break down deliverables into manageable chunks. Adapted for the iterative nature of AI development where loop-backs are normal.

## Before Planning

Ask (skip what's already known):

1. **What's the sprint scope?** — Which project or workstream? What phase are we in?
2. **What's the timeframe?** — 1 week, 2 weeks, a month?
3. **What carried over?** — Unfinished work from last sprint?
4. **What's the capacity?** — Any PTO, competing priorities or blocked dependencies?
5. **What must be done vs. what's aspirational?** — Hard deadlines or commitments?

## Sprint Plan Structure

### Sprint Overview
```
## Sprint [X]: [Theme/Focus]
**Dates:** [start] — [end]
**Phase:** [GBT lifecycle phase]
**Sprint goal:** [One sentence — the most important outcome]
```

### Committed Work
Items the team is confident they'll complete. Each item needs:

| Item | Owner | Acceptance criteria | Dependencies | Priority |
|------|-------|-------------------|--------------|----------|
| [Work item] | [Name/role] | [How we know it's done] | [Blockers] | P0/P1/P2 |

**Priority guide:**
- **P0** — Must complete this sprint. Sprint fails without it.
- **P1** — Important, high confidence we'll get to it.
- **P2** — Stretch goal. Nice to finish but acceptable to carry over.

### PM Deliverables
What the PM specifically owns this sprint:

```
### My deliverables
- [ ] [Deliverable] — due [date]
- [ ] [Deliverable] — due [date]

### Waiting on others
- [ ] [What I need] from [who] — needed by [date]
```

### Risks & Mitigations
| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|-----------|
| [What could go wrong] | High/Med/Low | [Consequence] | [Plan B] |

### Lifecycle Checkpoints
Map sprint activities to the GBT 7-phase lifecycle:

- **If in Phase 1-2 (Understanding):** Sprint should focus on intake form completion, data source identification, stakeholder alignment
- **If in Phase 3 (Design):** Sprint should focus on Q&A behavior tables, tone guidelines, boundary definitions
- **If in Phase 4 (Development):** Sprint should focus on answering AI team questions, reviewing checkpoints, preparing eval test cases
- **If in Phase 5 (Evaluation):** Sprint should focus on running test cases, analyzing results, preparing PM recommendation
- **If in Phase 6 (Risk Committee):** Sprint should focus on Smartsheet form, presentation prep, risk narrative
- **If in Phase 7 (Deployment):** Sprint should focus on monitoring setup, feedback collection, iteration planning

## Sprint Retrospective Prompts

At the end of a sprint, use these to reflect:

```
### What went well
- [Keep doing this]

### What didn't go well
- [Stop or change this]

### What did we learn
- [Insight for next sprint]

### Action items
- [ ] [Specific change for next sprint] — owner: [name]
```

Limit to 1-3 action items. More than that and nothing changes.

## Writing Conventions

- Come with a proposed priority order — don't ask the team to prioritize from scratch
- Push back on overcommitment. It's better to commit to less and deliver reliably.
- Every item needs a clear owner and clear acceptance criteria
- Flag items that are underscoped or have hidden complexity
- For AI projects: always build in time for iteration. A realistic timeline includes at least one loop-back.
