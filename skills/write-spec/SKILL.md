---
name: write-spec
description: Draft a PRD, product specification or requirements document. Use when asked to write a spec, PRD, product brief, feature brief or requirements for an AI agent or product feature.
---

# Write Spec

Generate a structured product specification. Adapt the depth and formality to what's being specified — a lightweight feature brief needs less than a full agent PRD.

## Before Writing

Gather context by asking (skip what's already known):

1. **What problem are we solving?** — The user pain, not the solution. Who's affected and how badly?
2. **Who's the primary persona?** — Travel Manager, business traveler, arranger, finance, compliance?
3. **What does success look like?** — Measurable outcomes. How will we know this worked?
4. **What phase are we in?** — Map to the GBT 7-phase lifecycle. Is this a Phase 1 intake or a Phase 3 design spec?
5. **What's out of scope?** — Equally important. What are we deliberately *not* doing?

If the user provides a rough brief or notes, extract answers from those rather than asking redundantly.

## Spec Structure

Use this structure, adjusting sections based on scope:

### 1. Problem Statement
What's broken or missing, who it affects and why it matters now. Lead with the user pain, not the technology.

### 2. User Stories
Format: "As a [persona], I want [capability] so that [outcome]."
Include 3-5 primary stories. For each, add acceptance criteria using Given/When/Then format.

### 3. Proposed Solution
High-level approach. What the agent or feature does, not how it's built. Include:
- Key interactions or workflows
- Behavioral boundaries (what the agent should and shouldn't do)
- Tone and personality guidelines (for agent specs)

### 4. Success Metrics
Tie each metric to a user story or problem statement. Include:
- **Primary KPI** — The one number that defines success
- **Supporting metrics** — 2-3 secondary indicators
- **Guardrail metrics** — What must not get worse (e.g. response accuracy, compliance adherence)

### 5. Scope & Non-Goals
Explicit list of what's included and what's deliberately excluded. Non-goals prevent scope creep and set expectations.

### 6. Dependencies & Risks
Data sources needed, team dependencies, compliance considerations, technical unknowns. For AI agents, always include:
- Data source availability and quality
- Hallucination/accuracy risks
- Multi-client data isolation
- Duty of care implications (if traveler-facing)

### 7. Open Questions
Unresolved items that need answers before or during development. Tag each with who should answer (PM, AI team, legal, client).

## Output Conventions

- Bold key terms and metrics
- Keep sections concise — a good spec is scannable, not exhaustive
- For AI agent specs: include a behavior table (User says -> Agent should respond)
- Reference the GBT lifecycle phase this spec feeds into

## After Writing

Suggest running the spec past a product leader or VP for review — they'll catch gaps in metrics, edge cases and stakeholder framing.

If the spec is for Phase 5, suggest using `/eval-test-cases` to generate the corresponding evaluation set.
