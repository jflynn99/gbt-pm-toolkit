---
name: risk-assessment
description: Prepare AI risk assessment documentation for the Risk Committee (Phase 6). Use when asked to prepare for the Risk Committee, fill the risk intake form, assess AI risks or document risk mitigations for an agent or AI feature.
---

# Risk Assessment

Prepare structured risk assessment documentation for the AI Risk & Assessment Committee (Phase 6 of the GBT lifecycle). The committee reviews AI projects before they go live to ensure they're safe, compliant and well-governed.

## Before Writing

Ask (skip what's already known):

1. **What agent or feature?** — Name and brief description.
2. **What phase is it in?** — Should be approaching or at Phase 6. If earlier, flag that risk assessment may be premature.
3. **What data sources does it use?** — Policy documents, customer data, third-party APIs?
4. **Has evaluation been completed?** — Phase 5 results are key evidence for the committee.
5. **Who's presenting?** — The PM typically presents the business case; the AI team supports with technical details.

## Risk Assessment Structure

### 1. Project Summary
```
**Agent/Feature:** [name]
**PM:** [name]
**AI Team Lead:** [name]
**Purpose:** [1-2 sentences — what it does and who it's for]
**Current phase:** [should be Phase 5-6]
**Target deployment:** [timeline]
```

### 2. Business Case
Why this matters — framed for a committee that may not know the project's history:
- What user problem does this solve?
- What's the business impact of solving it? (Cost savings, efficiency, satisfaction)
- What's the cost of *not* doing it? (Competitive risk, ongoing manual effort, user frustration)

### 3. Risk Matrix

| Risk area | Level | Description | Mitigation | Residual risk |
|-----------|-------|-------------|-----------|---------------|
| **Data privacy** | Low/Med/High | [What personal or sensitive data is involved?] | [Controls in place] | [What remains after mitigation] |
| **Accuracy** | Low/Med/High | [What happens if the agent gives wrong information?] | [Evaluation results, guardrails, confidence thresholds] | |
| **Hallucination** | Low/Med/High | [Can the agent fabricate information?] | [Grounding techniques, source attribution, refusal behavior] | |
| **Bias** | Low/Med/High | [Could responses disadvantage any group?] | [Testing across populations, fairness review] | |
| **Client isolation** | Low/Med/High | [Could one client's data leak to another?] | [Architectural controls, testing evidence] | |
| **Regulatory** | Low/Med/High | [GDPR, data residency, industry regulations?] | [Compliance review status, legal sign-off] | |
| **Reputational** | Low/Med/High | [What's the worst-case public perception?] | [Human oversight, escalation paths, kill switch] | |
| **Duty of care** | Low/Med/High | [Could incorrect info affect traveler safety?] | [Fallback to human agent, disclaimers] | |

### 4. Evaluation Evidence
Summarize Phase 5 results — the committee needs proof the agent works:

```
## Evaluation Summary
- Total test cases: [X]
- Pass: [X] | Partial: [X] | Fail: [X]
- Must-pass failures: [X] (blockers)
- PM recommendation: [Ready / Needs iteration / Needs escalation]

### Key findings
- [What the agent does well]
- [Where it struggles]
- [How must-pass failures were resolved, if applicable]
```

### 5. Human Oversight Plan
Every AI agent needs a human oversight model:
- **Monitoring:** How will accuracy be tracked post-deployment?
- **Escalation:** When does the agent hand off to a human? What triggers escalation?
- **Override:** Can a human correct or override the agent's behavior?
- **Kill switch:** How quickly can the agent be disabled if something goes wrong?
- **Feedback loop:** How do users report issues? How does feedback reach the PM and AI team?

### 6. Deployment Plan
- Phased rollout or big bang?
- Which clients or user segments go first?
- What metrics trigger expansion vs. rollback?
- Who monitors during the initial rollout period?

### 7. Open Questions for the Committee
What you want their input on:
- Specific risk areas where you'd value their judgment
- Decisions that need committee approval before proceeding
- Timeline or scope questions

## Travel-Specific Risk Scenarios

When assessing GBT AI agents, always consider:

- **Incorrect policy guidance** — The agent tells a traveler they can book business class when the policy says economy. Financial and compliance impact.
- **Cross-client data exposure** — Agent trained on Client A's policies accidentally surfaces that information to Client B's travelers.
- **Duty of care failure** — Agent provides incorrect safety information during a travel disruption or crisis. Reputational and legal exposure.
- **Booking errors** — Agent recommends or confirms a booking that violates preferred supplier agreements. Financial impact on client relationships.
- **Prompt injection** — User manipulates the agent into bypassing its instructions or revealing system prompts.

## Writing Conventions

- Be honest about risk levels. Downplaying risks to get through the committee faster will backfire.
- Every risk needs a mitigation. "We haven't thought about this" is worse than "This is medium-risk and here's our plan."
- Use plain language. The committee includes non-technical stakeholders.
- Lead with the business case — the committee needs to understand why this project matters before evaluating its risks.
- Reference evaluation evidence concretely — "8 of 10 test cases passed" not "evaluation went well."
