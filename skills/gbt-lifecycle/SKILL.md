---
name: gbt-lifecycle
description: GBT 7-phase AI project lifecycle reference. Provides context about project phases, PM responsibilities and AI team handoffs. Auto-loaded for lifecycle-related queries.
user-invocable: false
---

# GBT 7-Phase AI Project Lifecycle

This is the standard lifecycle for AI projects at AMEX GBT. It maps to CRISP-DM with two GBT-specific additions: a dedicated Design phase (Phase 3) and an AI Risk Committee gate (Phase 6).

Projects are **iterative, not waterfall**. Looping back to earlier phases is normal and expected.

---

## Phase Summary

| # | Phase | PM Effort | PM Owns | AI Team Owns |
|---|-------|-----------|---------|-------------|
| 1 | **Business Understanding** | High | Problem definition, user pain, success criteria, KPIs. Fill AI Intake form. | Advise on feasibility. |
| 2 | **Data / Source Understanding** | Medium | Point to data sources, flag privacy/access concerns. | Audit data quality, identify gaps. |
| 3 | **Design & Preparation** | High | Expected Q&As, agent tone/scope, do's and don'ts, boundaries. | Data pipelines, prompt design, knowledge base. |
| 4 | **Development** | Low | Answer clarifications, confirm "good enough" at checkpoints. | Build, test, iterate the agent. |
| 5 | **Evaluation** | **Highest** | Write test cases and expected answers. Judge quality. Define "good enough." | Run agent, collect responses, analyze results. |
| 6 | **AI Risk & Assessment Committee** | Medium | Fill Smartsheet intake form. Present business case to committee. | Support with technical risk details. |
| 7 | **Deployment & Monitoring** | Medium | Review usage/KPIs/feedback, spot patterns, flag issues. | Track metrics, handle incidents, iterate. |

## Common Loop-Backs

| Trigger | Loop destination |
|---------|-----------------|
| Agent can't answer a common question type | Phase 2 — need more data sources |
| Risk Committee flags compliance concern | Phase 3 — adjust boundaries |
| Users ask unexpected questions post-launch | Phase 5 -> Phase 3 — new test cases, then expand scope |
| Poor data quality discovered | Phase 1 — reassess problem/data fit |

## Key Artifacts by Phase

- **Phase 1:** AI Intake form (Confluence)
- **Phase 3:** Q&A behavior table (user says -> agent should)
- **Phase 5:** Evaluation Template (test cases, expected answers, pass/fail, PM recommendation)
- **Phase 6:** Smartsheet risk assessment form
- **Phase 7:** KPI dashboard, user feedback log

## Evaluation Framework (Phase 5 Detail)

This is the PM's most critical contribution. Structure:

**Test case categories:**
- Happy path — common real-world questions
- Edge case — unusual, multi-part, ambiguously phrased
- Adversarial — trick questions, prompt injection, restricted info requests
- Out of scope — agent should decline or redirect

**Priority levels:**
- Must-pass — blocker if failed (safety, compliance, core functionality)
- Should-pass — important, flag for iteration
- Nice-to-have — acceptable to miss in V1

**PM recommendation options:**
- Ready for deployment
- Needs iteration (another evaluation round)
- Needs escalation (safety/compliance/quality concerns)

## CRISP-DM Mapping

GBT's 7 phases map to CRISP-DM's 6:
1. Business Understanding = Business Understanding
2. Data/Source Understanding = Data Understanding
3. Design & Preparation = Data Preparation (expanded for PM input)
4. Development = Modeling
5. Evaluation = Evaluation
6. AI Risk Committee = *No CRISP-DM equivalent* (GBT governance addition)
7. Deployment & Monitoring = Deployment

The Risk Committee exists because GBT operates in a regulated industry (corporate travel, financial services) where AI decisions about policies, data and user interactions need oversight.

---

*Sourced from GBT AI Playbook materials. Last reviewed: 2026-03-29.*
