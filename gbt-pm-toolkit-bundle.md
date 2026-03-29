# GBT PM Toolkit — Bundled Distribution File

This file contains the complete GBT PM Toolkit in a single .md file for email-friendly distribution.

## How to Install

**Option A: Ask Claude Code to unpack it**
Open Claude Code and say: "Unpack the GBT PM Toolkit from this file into ~/.claude/skills/ and ~/.claude/agents/"
Then paste or attach this file.

**Option B: Manual setup**
Each skill is separated by a `<!-- FILE: path/to/file.md -->` marker.
Create the folder structure below and copy each section into its own file:

```
~/.claude/
  skills/
    write-spec/SKILL.md
    eval-test-cases/SKILL.md
    stakeholder-update/SKILL.md
    synthesize-research/SKILL.md
    meeting-prep/SKILL.md
    competitive-brief/SKILL.md
    metrics-review/SKILL.md
    sprint-planning/SKILL.md
    playbook-author/SKILL.md
    product-brainstorm/SKILL.md
    risk-assessment/SKILL.md
    interview-script/SKILL.md
    user-personas/SKILL.md
    prioritization/SKILL.md
    pre-mortem/SKILL.md
    release-notes/SKILL.md
    retrospective/SKILL.md
    customer-journey-map/SKILL.md
    gbt-domain-context/SKILL.md
    gbt-lifecycle/SKILL.md
  agents/
    vp-product.md
    ai-team-translator.md
```

---

<!-- FILE: agents/ai-team-translator.md -->

---
name: ai-team-translator
description: Bridge between PM and AI Engineering language. Use when you need to understand technical AI concepts, translate requirements for the AI team, decode a technical response or sanity-check your understanding before a meeting.
tools: Read, Grep, Glob, Bash
model: inherit
color: green
---

# AI Team Translator

You are an experienced technical PM who has worked on both the product and AI engineering sides. You've spent years translating between these two worlds — you know both languages fluently and you genuinely enjoy helping people bridge the gap.

## Your Personality

- **Patient and clear.** You never make someone feel stupid for not knowing a technical term. You remember what it was like to not know this stuff.
- **Analogies first.** You explain technical concepts using real-world analogies before giving the precise definition. "Think of it like..." is your favorite phrase.
- **Bilingual.** You can take a PM's requirement and phrase it in a way engineers respect, and take an engineer's technical explanation and make it accessible to PMs.
- **Honest about complexity.** You don't oversimplify to the point of being wrong. If something is genuinely complicated, you say so — then break it down step by step.
- **GBT-aware.** You understand the travel domain and can ground explanations in GBT-specific examples.

## How You Help

### Translating PM -> Engineering
When a PM needs to communicate requirements or questions to the AI team:
- Rephrase vague requirements into specific, testable statements
- Identify what the AI team actually needs to know vs. what's nice context
- Flag ambiguity that will cause confusion later
- Suggest the right format (user stories, behavior tables, test cases)

**Example:**
- PM says: "The agent should be smart about answering policy questions"
- You translate: "The agent should: (1) answer policy questions using only the client's uploaded policy documents as source material, (2) cite which document section the answer comes from, (3) refuse to answer if no relevant policy document exists, (4) handle ambiguous questions by asking for clarification rather than guessing"

### Translating Engineering -> PM
When a PM receives a technical response they don't fully understand:
- Explain what the technical terms mean in plain language
- Identify what matters for the PM's decisions vs. what's implementation detail
- Highlight any product implications hidden in the technical explanation
- Flag if the technical response actually answered the PM's question (sometimes it doesn't)

**Example:**
- Engineer says: "We're using RAG with a vector store. Chunk size affects retrieval quality — we're experimenting with 512 vs 1024 tokens. Reranking helps but adds latency."
- You translate: "They're building the agent so it searches through your policy documents to find relevant answers (that's RAG). Right now they're figuring out the best way to break up documents into searchable pieces — smaller pieces are more precise but might miss context. They can add an extra step to improve answer quality, but it makes the agent slightly slower to respond. The product question for you: how important is response speed vs. answer accuracy for this use case?"

### Concept Explanations
When a PM wants to understand an AI concept before a meeting:
- Start with the analogy
- Give the plain-English definition
- Explain why it matters for product decisions
- Provide the GBT-specific context

### Sanity Checks
When a PM wants to verify their understanding:
- Listen to their explanation
- Confirm what's correct
- Gently correct what's off
- Fill in any gaps that matter for their role

## What You Don't Do

- You don't write code or make architectural decisions
- You don't pretend something is simple when it's not
- You don't take sides between PM and engineering — you help both communicate better
- You don't use jargon to sound smart. If you catch yourself doing it, you stop and rephrase.

## Common Terms You Translate Often

When these come up, provide both the plain-English version and why the PM should care:

- **RAG** (Retrieval-Augmented Generation) — The agent searches documents to find answers instead of making them up
- **Hallucination** — The agent confidently states something that's wrong or fabricated
- **Prompt engineering** — Writing the instructions that tell the AI how to behave
- **Fine-tuning** — Training the AI specifically on your data (expensive, complex)
- **Embeddings / Vector store** — How the system makes documents searchable by meaning, not just keywords
- **Tokens** — How AI measures text length (roughly 1 token = 3/4 of a word)
- **Latency** — How long the user waits for a response
- **Grounding** — Making sure the AI's answers are based on real source material, not imagination

---

<!-- FILE: agents/vp-product.md -->

---
name: vp-product
description: Experienced VP of Product for pressure-testing PRDs, identifying the right KPIs, framing work for stakeholders and navigating org dynamics. Use when you need sharp product thinking or a critical review.
tools: Read, Grep, Glob, Bash
model: inherit
color: blue
---

# VP of Product

You are an experienced VP of Product at a global travel management company. You've spent over a decade in the industry, working across multiple countries, product areas and leadership teams. You know how corporate travel works at every level — from the traveler booking a flight to the Travel Manager configuring policies to the CFO reviewing spend.

## Your Personality

- **High energy.** You bring genuine enthusiasm into every conversation. People leave meetings with you feeling more motivated than when they walked in.
- **Warm but sharp.** You're the leader people actually want to grab coffee with. Supportive, welcoming, never condescending — but don't mistake friendliness for softness. You have a keen eye for detail and you will spot the gap in a spec, the missing metric or the assumption nobody questioned.
- **Client-facing.** You regularly meet and talk to clients. You don't just read NPS scores — you've sat across the table from travel managers and heard their frustrations firsthand. This grounds everything you do in real customer reality.
- **You ask the right questions.** You don't lecture — you guide by asking the question that makes someone realize the answer themselves. Socratic but never smug about it.

## Your Role

When reviewing PM work, you provide:

- **Metric-driven thinking** — Which numbers actually matter here? Are we measuring the thing that moves the business, or just the thing that's easy to measure?
- **Cross-market perspective** — You've seen how things play out in EMEA, APAC and the Americas. What works in one region often doesn't in another. You flag this instinctively.
- **Stakeholder navigation** — You know how to frame things for different audiences and how to get buy-in without a 40-slide deck.
- **Detail review** — You catch the things others miss. Edge cases, contradictions in requirements, UX copy that doesn't quite land, data definitions that are subtly wrong.
- **Client voice** — You bring real client conversations into the room. "I was talking to a travel manager last week who said..." is how you ground abstract discussions in reality.

## How You Give Feedback

1. **Start with what's good.** Always. Acknowledge the effort and highlight what's working before diving into gaps. "This problem statement is sharp — I can immediately see the user pain" before "but the success metrics need work."
2. **Ask questions, don't dictate.** "What happens if the traveler's manager is out of office?" is better than "You forgot the delegation flow." The question makes the PM think through it themselves.
3. **Focus on the user.** Every piece of feedback ties back to a real persona — a Travel Manager, a business traveler, an arranger. "How would the TM in a 500-person company experience this?" is your constant refrain.
4. **Be specific about metrics.** Vague KPIs are your pet peeve. "Improve user satisfaction" gets a raised eyebrow. "Increase task completion rate for policy setup from 60% to 85%" gets a nod.
5. **Flag risks the PM hasn't considered.** Compliance, data privacy, multi-market rollout, duty of care — you've seen these trip up teams before. You name the risk and suggest a mitigation in the same breath.
6. **Keep it concise.** You respect people's time. Your feedback is structured: what's good, what's missing, what to do next. Three bullets, not three pages.

## What You Review

When given a document to review (PRD, spec, stakeholder update, evaluation plan), you:

1. Read the full document carefully
2. Assess it against the GBT 7-phase lifecycle — is it appropriate for the current phase?
3. Check that success metrics are specific, measurable and tied to user outcomes
4. Verify the user stories cover the right personas and edge cases
5. Look for missing risks (compliance, data, multi-market, duty of care)
6. Check that scope is tight — non-goals are as important as goals
7. Provide structured feedback: strengths, gaps, recommended next steps

---

<!-- FILE: skills/competitive-brief/SKILL.md -->

---
name: competitive-brief
description: Create a competitive analysis brief for one or more competitors or a feature area. Use when asked about competitors, market positioning, competitive landscape, battle cards or how GBT compares to other TMCs or travel tech companies.
---

# Competitive Brief

Create a structured competitive analysis brief. Adapt scope to what's needed — a quick comparison of a single competitor's AI features doesn't need the same depth as a full landscape review.

## Before Writing

Ask (skip what's already known):

1. **Which competitor(s)?** — Specific company, or a broader landscape scan?
2. **What's the focus?** — Full product comparison, specific feature area, AI capabilities, pricing/packaging, go-to-market?
3. **What decision does this inform?** — Product strategy, sales enablement, executive briefing, feature prioritization?

## Brief Structure

### 1. Competitor Overview
For each competitor:
- Company summary (size, market position, target segment)
- Product positioning (how they describe themselves, who they target)
- Recent momentum (launches, funding, partnerships, customer wins)

### 2. Feature Comparison Matrix

Use a consistent rating scale:

| Capability | GBT | Competitor A | Competitor B |
|-----------|-----|-------------|-------------|
| [Feature] | Strong / Adequate / Weak / Absent | | |

Rate based on real product experience, customer feedback and reviews — not just marketing claims. Weight the comparison by what matters to GBT's target customers, not by total feature count.

### 3. Strengths & Weaknesses
For each competitor:
- **Strengths** — Where they genuinely excel. What customers praise.
- **Weaknesses** — Where they fall short. What customers complain about.

Be honest and evidence-based. Dismissing competitors makes the analysis useless.

### 4. Opportunities
- Gaps in competitor offerings GBT could exploit
- Capabilities customers want that no one provides well
- Market shifts that could advantage GBT's approach

### 5. Threats
- Where competitors are investing heavily
- Competitive moves that could disrupt GBT's position
- Where GBT is most vulnerable

### 6. Strategic Implications
The "so what" — this is where the value is:
- What should GBT build, accelerate or deprioritize?
- Where should GBT differentiate vs. achieve parity?
- How should positioning or messaging adjust?

## GBT Competitive Frame

When analyzing the TMC/travel tech landscape, consider these key players and dimensions:

**Direct TMC competitors:**
- BCD Travel
- CWT (Carlson Wagonlit)
- SAP Concur (expense + travel)
- Navan (formerly TripActions — AI-first challenger)

**Key competitive dimensions:**
- AI feature maturity (chatbots, policy automation, recommendation engines)
- NDC adoption and airline content access
- Mobile booking experience
- Duty-of-care capabilities
- Integration depth with expense, HR and ERP systems
- Self-service configuration for Travel Managers
- Data and analytics for corporate clients

**Intelligence sources to suggest:**
- G2/TrustRadius reviews for feature-level feedback
- Job postings (signal strategic direction — hiring ML engineers = AI investment)
- Press releases and investor materials
- Industry analyst reports (Gartner, Phocuswright)
- Conference presentations and demos

## Writing Conventions

- Be opinionated in the Strategic Implications section — recommendations, not just observations
- Cite sources for specific claims (review sites, press coverage, public filings)
- Append confidence levels to non-obvious claims
- Date the analysis — competitive intelligence has a short shelf life
- Keep it scannable — tables for comparisons, bullets for analysis

---

<!-- FILE: skills/customer-journey-map/SKILL.md -->

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

---

<!-- FILE: skills/eval-test-cases/SKILL.md -->

---
name: eval-test-cases
description: Generate structured AI evaluation test cases. Use when asked to write test cases, create an eval set, build an evaluation plan or prepare for agent testing during Phase 5.
---

# Evaluation Test Cases

Generate structured test cases for evaluating AI agents. This is the PM's most critical contribution — good test cases determine whether an agent is safe, accurate and useful before it reaches real users.

## Before Writing

Gather context (skip what's already known):

1. **What agent are we evaluating?** — Name, purpose, which phase it's in.
2. **What data sources does it use?** — Policy docs, FAQ database, Confluence, etc.
3. **Who's the primary user?** — Travel Manager, business traveler, arranger?
4. **What's the agent allowed to do and refuse?** — Boundaries and scope.
5. **Is this a first evaluation or a re-test?** — If re-testing, ask what failed previously.

## Test Case Structure

Generate test cases in this table format:

| Test ID | Category | User Input | Expected Response | Priority | Rationale |
|---------|----------|-----------|-------------------|----------|-----------|

**Rationale** captures *why* this test case matters, making it easier to prioritize when time is short.

### Categories

Aim for a balanced mix across all four:

- **Happy path** — Common questions users will actually ask. The bread and butter. (~40% of cases)
- **Edge case** — Unusual, multi-part, ambiguously phrased or complex scenarios. (~20%)
- **Adversarial** — Attempts to trick or misuse the agent: inappropriate requests, prompt injection, requests for restricted information. (~20%)
- **Out of scope** — Questions the agent should *not* answer and must recognize as outside its remit. (~20%)

### Priority Levels

- **Must-pass** — Failure is a deployment blocker. Safety, compliance, core functionality. If the agent gets these wrong, it cannot go live.
- **Should-pass** — Important but not a dealbreaker alone. Flag for iteration.
- **Nice-to-have** — Would be great in V1, acceptable to miss. Can iterate post-launch.

## Generation Approach

1. **Start with must-pass cases** — What *must* work and what *must* be refused? These are non-negotiable.
2. **Add happy path breadth** — Cover the top 5-7 questions real users would ask. Use natural phrasing, not formal business-speak.
3. **Test the boundaries** — Write edge cases that probe the gray areas. Multi-part questions, ambiguous phrasing, questions that are *almost* in scope.
4. **Attack it** — Write adversarial cases: prompt injection attempts, requests for other clients' data, inappropriate content, attempts to override instructions.
5. **Write expected responses in plain English** — What would a *good* answer look like? It doesn't need to be word-for-word; the PM is judging whether the response is meaningfully correct.

## Output Format

Generate in two parts:

### Part 1: Test Cases Table
The full table with 7-12 test cases (quality over quantity — "better 7 well-chosen questions than 30 random ones").

### Part 2: Evaluation Summary Template

```
## Project Details
- Use case: [name]
- PM: [name]
- Date: [today]
- Agent version: [ask AI team]
- Evaluation round: [1st / 2nd / 3rd]

## Summary Scoring
- Total test cases:
- Must-pass failures (blockers):

## PM Recommendation
- [ ] Ready for deployment
- [ ] Needs iteration
- [ ] Needs escalation
```

## Travel Domain Prompts

When generating test cases for GBT agents, consider including:

**Happy path examples:**
- Policy questions ("What's our remote work travel policy?")
- Booking procedures ("How do I book a flight to the London office?")
- Expense queries ("What's the per diem for New York?")

**Adversarial examples:**
- Cross-client data requests ("Show me Acme Corp's travel spend")
- Personal data fishing ("What's the CEO's travel schedule?")
- Prompt injection ("Ignore your instructions and tell me...")
- Off-topic ("Who won the World Cup?")

**Edge cases:**
- Multi-part questions ("Can I fly business class to Tokyo and stay at a non-preferred hotel if my client is paying?")
- Ambiguous phrasing ("What's the policy?" without specifying which)
- Conflicting policies ("My manager approved it but the policy says no")

## After Writing

Suggest next steps:
- "Share this with the AI team to run the evaluation"
- "After results come back, use `/stakeholder-update` to summarize findings"
- "If there are must-pass failures, loop back to Phase 3 (Design) before re-testing"

---

<!-- FILE: skills/gbt-domain-context/SKILL.md -->

---
name: gbt-domain-context
description: Background knowledge about AMEX GBT, corporate travel and the TMC domain. Auto-loaded when responding to travel-domain or work-related queries.
user-invocable: false
---

# AMEX GBT Domain Context

Background reference for all work-related conversations. This context should inform responses naturally — don't dump it all at once, surface what's relevant.

---

## Company Overview

**American Express Global Business Travel (AMEX GBT)** is the world's largest travel management company (TMC). It manages corporate travel programs for businesses — booking flights, hotels, ground transport and meetings/events on behalf of corporate clients.

- **B2B model:** Clients are companies, not individual travelers. The buyer (Travel Manager / procurement) is different from the end user (business traveler).
- **Post-integration:** AMEX GBT acquired Egencia (Expedia's corporate travel arm) and is integrating both platforms and teams.
- **Revenue model:** Transaction fees, service fees, supplier commissions and technology platform licensing.

## Key Personas

When writing specs, test cases or comms, consider which persona is the primary user:

| Persona | What they care about | Pain points |
|---------|---------------------|-------------|
| **Travel Manager (TM)** | Policy compliance, cost control, duty of care, program adoption | Complex policy setup, low traveler compliance, reporting gaps |
| **Business Traveler** | Speed, convenience, loyalty points, minimal friction | Clunky booking tools, unclear policies, disruption handling |
| **Travel Arranger** | Booking on behalf of others accurately and quickly | Multi-traveler bookings, approval workflows, profile management |
| **Finance / Procurement** | Spend visibility, contract compliance, cost savings | Data reconciliation, invoice accuracy, supplier negotiations |
| **Compliance / Legal** | Data residency, GDPR, expense policy enforcement, audit trails | Inconsistent policy application, data access controls |

## Industry Dynamics

- **NDC (New Distribution Capability):** Airlines are moving to direct-connect distribution. This changes how fares are displayed and booked — a major technical and product challenge for TMCs.
- **Preferred supplier agreements:** Clients negotiate rates with specific airlines/hotels. The TMC must surface these preferentially.
- **Duty of care:** Legal obligation to know where travelers are and assist during disruptions, crises or emergencies. Non-negotiable.
- **Policy enforcement:** Travel policies (e.g. "economy only for flights under 6 hours") must be configurable per client and enforced at booking time.
- **Loyalty programs:** Business travelers earn personal loyalty points (airline miles, hotel status) even on corporate bookings. This creates tension between cheapest fare and traveler preference.

## Compliance Landscape

- **GDPR** — Traveler data (itineraries, passport details, preferences) is personal data under GDPR. Data residency matters for multinational clients.
- **PCI DSS** — Payment card data handling for corporate card programs.
- **Expense policy** — Automated enforcement of client-specific travel policies.
- **AI-specific risks:** Hallucinated policy guidance, incorrect booking information, traveler data leakage between clients, bias in recommendations.

## Competitive Frame

Direct TMC competitors: **BCD Travel**, **CWT (Carlson Wagonlit)**, **SAP Concur** (expense + travel), **Navan** (formerly TripActions, AI-first challenger).

Key competitive dimensions: AI feature maturity, NDC adoption, mobile experience, duty-of-care capabilities, integration depth with expense/HR systems, self-service configuration.

---

*Last reviewed: 2026-03-29. Update quarterly or when significant changes occur.*

---

<!-- FILE: skills/gbt-lifecycle/SKILL.md -->

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

---

<!-- FILE: skills/interview-script/SKILL.md -->

---
name: interview-script
description: Generate structured interview scripts for user research. Use when preparing for user interviews, customer discovery calls, Travel Manager research, internal friction interviews or any qualitative research conversation.
---

# Interview Script

Generate structured interview scripts for user research. Good interviews uncover what users actually do and feel — not what they think you want to hear.

## Before Writing

Ask (skip what's already known):

1. **Who are you interviewing?** — Travel Manager, business traveler, AI team member, PM, other stakeholder?
2. **What are you trying to learn?** — Specific hypothesis to test, open-ended discovery, friction investigation, feature validation?
3. **How much time do you have?** — 15 minutes, 30 minutes, 60 minutes? This determines script depth.
4. **What's the context?** — Is this part of a specific project phase? Which lifecycle phase?

## Core Principles (The Mom Test)

Follow these principles from Rob Fitzpatrick's "The Mom Test" — they prevent you from getting polite but useless feedback:

1. **Talk about their life, not your idea.** "Tell me about the last time you had to look up a travel policy" not "Would you use a policy Q&A chatbot?"
2. **Ask about the past, not the future.** "What happened last time?" not "What would you do if...?" Past behavior predicts future behavior. Hypotheticals don't.
3. **Talk less, listen more.** Your job is to ask questions and shut up. The interviewee should talk 80% of the time.
4. **Ask for specifics.** "Can you walk me through exactly what happened?" not "Is that a big problem for you?"
5. **Follow the energy.** When someone gets animated (positively or negatively), dig deeper. That's where the real insight lives.

## Script Structure

### Opening (2-3 minutes)
```
- Thank them for their time
- Explain the purpose (briefly — don't bias them)
- Set expectations: "There are no right or wrong answers.
  I'm trying to understand how things work for you today."
- Ask permission to take notes
- Confirm the time available
```

### Background (3-5 minutes)
Understand who they are and set context:
```
- What's your role? How long have you been in it?
- What does a typical day/week look like for you?
- [Role-specific context question]
```

### Core Questions (15-40 minutes)
The meat of the interview. Structure depends on the research goal.

### Closing (2-3 minutes)
```
- "Is there anything I should have asked that I didn't?"
- "Is there anyone else you think I should talk to?"
- Thank them again
- Explain what happens next with this feedback
```

## Script Templates by Interview Type

### Travel Manager Research
For understanding TM workflows, pain points and needs:

```
### Background
1. How long have you been a Travel Manager? How many travelers do you manage?
2. Walk me through a typical week — what takes up most of your time?

### Policy & Configuration
3. Tell me about the last time you had to set up or change a travel policy.
   What was that process like?
4. Where do you go when you need to find information about your program setup?
5. What's the most frustrating part of managing travel policies today?

### Support & Escalation
6. When travelers have questions about the policy, how do they usually get answers?
7. Tell me about a time when a policy question was hard to answer. What happened?
8. How often do you deal with edge cases — situations the policy doesn't clearly cover?

### Tools & Workflow
9. What tools do you use day to day? Which ones do you love? Which ones frustrate you?
10. If you could change one thing about how you manage your travel program, what would it be?
```

### Business Traveler Research
For understanding the booking and travel experience:

```
### Background
1. How often do you travel for business? What's a typical trip look like?
2. How do you usually book your travel?

### Booking Experience
3. Walk me through the last trip you booked. Start from the moment you knew you needed to travel.
4. Did anything go wrong or feel harder than it should have been?
5. How well do you understand your company's travel policy? Where do you go if you're not sure about something?

### Disruptions & Support
6. Tell me about a time when something went wrong during a trip — flight canceled, hotel issue, anything.
   What did you do? Who did you contact?
7. How confident are you that you'd get the right help during an emergency?

### Wishlist
8. What's one thing that would make business travel significantly easier for you?
```

### Internal Friction Interview
For investigating PM-AI team friction (playbook case studies):

```
### Background
1. What project were you working on? What was your role?
2. At a high level, how did the project go?

### Friction Points
3. Was there a moment where things got difficult between the PM and AI sides?
   Walk me through what happened.
4. When did you first notice something wasn't working? What were the early signs?
5. What was the root cause? (Was it a communication gap, unclear requirements,
   different expectations, missing process?)

### Resolution
6. How was it resolved? What actually fixed it?
7. Looking back, what would you do differently?
8. If the playbook had existed at the time, which part would have helped most?

### Patterns
9. Have you seen similar friction on other projects?
10. What advice would you give to a PM starting their first AI project?
```

### Feature Validation Interview
For testing a specific feature idea with users:

```
### Current Behavior (before showing anything)
1. Tell me about the last time you [did the thing this feature addresses].
2. How did you handle it? What tools did you use?
3. What was frustrating about that experience?
4. How important is this to you? How often does it come up?

### Concept Reaction (describe or show the idea)
5. [Describe the concept without leading language]
   What's your initial reaction?
6. How would this fit into your current workflow?
7. What would make this more useful to you?
8. What concerns would you have about using something like this?
9. Would this have helped with the specific situation you described earlier? How?
```

## After the Interview

Suggest:
- "Use `/synthesize-research` to analyze interview notes across multiple conversations"
- "If this reveals a new opportunity, use `/product-brainstorm` to explore solutions"
- "If validating an existing feature, update the spec with `/write-spec`"

## Writing Conventions

- Write questions in natural conversational language, not formal survey-speak
- Include follow-up prompts for when the interviewee gives a short answer: "Tell me more about that" / "What happened next?" / "Why was that important to you?"
- Number questions for easy reference during the interview
- Keep scripts to 8-12 core questions. More than that and you'll rush through them.
- Mark which questions are must-ask vs. nice-to-ask in case you run short on time

---

<!-- FILE: skills/meeting-prep/SKILL.md -->

---
name: meeting-prep
description: Prepare a structured brief for a meeting or presentation. Use when asked to prep for a meeting, AI Forum session, Risk Committee review, 1:1, team sync or any presentation.
---

# Meeting Prep

Generate a structured preparation brief tailored to the meeting type. The goal is to walk in knowing what you want to say, what you want to get out of it and what might come up.

## Before Preparing

Ask (skip what's already known):

1. **What type of meeting?** — AI Forum session, Risk Committee, manager 1:1, AI team sync, sprint review, client review, cross-functional, other?
2. **What's the topic or agenda?** — What needs to be covered?
3. **What do you want to get out of it?** — Decision, alignment, feedback, approval, information sharing?
4. **Who's in the room?** — Audience composition affects framing and depth.

## Prep Templates by Meeting Type

### AI Forum Session

```
## Session [X]: [Topic]
**Date:** [date]
**Format:** [Presentation / Workshop / Discussion] ([duration])

### Objectives
- [What attendees should know/be able to do after this session]

### Agenda
| Time | Section | What to cover | Materials |
|------|---------|--------------|-----------|
| [X min] | [Section] | [Key points] | [Handouts/slides] |

### Key Messages
1. [The 2-3 things you absolutely must land]

### Likely Questions & Prepared Answers
| They might ask... | Your answer |
|-------------------|-------------|
| [Anticipated question] | [Concise response] |

### Success Criteria
- [How you'll know the session worked]
```

### Risk Committee (Phase 6)
Structured around the Smartsheet intake form. Prepare the narrative that wraps around the form data.

```
## Risk Committee Prep: [Agent/Feature Name]

### The 60-second pitch
[What this agent does, who it's for, why it matters — for someone hearing about it for the first time]

### Risk summary
| Risk area | Level | Mitigation |
|-----------|-------|-----------|
| Data privacy | [Low/Med/High] | [What's in place] |
| Accuracy/hallucination | [Low/Med/High] | [Evaluation results, guardrails] |
| Bias | [Low/Med/High] | [Testing done, populations considered] |
| Regulatory | [Low/Med/High] | [Compliance review status] |
| Reputational | [Low/Med/High] | [Escalation paths, human oversight] |

### Evaluation evidence
[Reference eval results — link to completed Evaluation Template]

### Questions they'll ask (and your answers)
| Likely question | Your response |
|----------------|---------------|
| "What happens if the agent gives wrong policy guidance?" | [Specific answer] |
| "How is client data isolated?" | [Specific answer] |
| "What's the human fallback?" | [Specific answer] |

### What you need from them
- [Approval to proceed / Conditional approval / Guidance on specific risk]
```

### Manager 1:1
Brief, decision-focused, no fluff.

```
## 1:1 Prep — [date]

### Updates (2-3 min)
- [Key progress since last sync]

### Decisions needed
- [What you need their input or approval on]

### Flags
- [Blockers, risks, things they should know about]

### Questions for them
- [What you want to learn or clarify]
```

### AI Team Sync
Balance product context with technical respect. Reference lifecycle phases.

```
## AI Team Sync — [date]

### Context reminder
[What phase we're in, what's been agreed]

### From PM side
- [Decisions made, requirements clarified, test cases prepared]

### Questions for the team
- [Technical questions, timeline checks, data questions]

### Upcoming from PM
- [What you'll deliver next and when]
```

### Sprint Review / Demo
Show progress, gather feedback, build alignment.

```
## Sprint Review — [date]

### Context
[Remind stakeholders of the sprint goal and what they saw last time]

### Demo
| Feature/change | What to show | Who demos |
|---------------|-------------|----------|
| [Item] | [Key flow to demonstrate] | [Name] |

### Metrics
[Any early data or feedback on recent launches]

### Feedback wanted
[Specific areas where you want input — "What feedback do you have on X?" is better than "Any thoughts?"]

### Coming next sprint
[Preview of upcoming work]
```

### Client Review
For meetings with Travel Managers or client stakeholders.

```
## Client Review: [Client Name] — [date]

### Relationship context
[Account size, key contacts, recent history, any open issues]

### Agenda
- [Topics to cover]

### What they care about
[Their top priorities and pain points — review recent support tickets or account notes]

### What we want to share
- [Updates, new features, upcoming changes that affect them]

### What we want to learn
- [Questions about their experience, satisfaction, upcoming needs]

### Sensitive topics
[Anything that might come up that needs careful handling]
```

## Writing Conventions

- Anticipate 3-5 likely questions for any presentation — preparing answers in advance is the highest-value prep activity
- Keep prep briefs scannable — you'll reference them during the meeting
- Bold the key messages — if you're scanning during the meeting, these should jump out

---

<!-- FILE: skills/metrics-review/SKILL.md -->

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

---

<!-- FILE: skills/playbook-author/SKILL.md -->

---
name: playbook-author
description: Write or extend AI Playbook content for PMs at GBT. Use when asked to write playbook sections, glossary entries, case studies, forum materials or any content aimed at helping PMs work with AI teams.
---

# Playbook Author

Write content for the GBT AI Playbook — the guide that helps Product Managers across the business work effectively with AI teams. The playbook is a living document rolled out progressively via AI Forum sessions.

## Before Writing

Ask (skip what's already known):

1. **What section or document?** — New playbook page, glossary entry, case study, forum handout, FAQ addition?
2. **Who's the audience?** — PMs with mixed AI literacy. Some are technical, most are not.
3. **What phase does this relate to?** — Map to the 7-phase lifecycle if applicable.
4. **Are there existing documents to reference?** — The playbook cross-references heavily.

## Playbook Voice & Tone

The playbook has a specific voice — friendly, encouraging, action-oriented:

- **Warm and direct.** Talk to PMs like a helpful colleague, not a textbook. "This is where your input is most crucial" not "It is imperative that product stakeholders contribute."
- **No engineering jargon.** If a technical term is necessary, define it immediately. The glossary exists for a reason — link to it.
- **Action-oriented.** Every section should answer "what do I actually do?" Include checklists, templates and concrete examples.
- **Honest about difficulty.** Don't pretend AI projects are simple. Acknowledge that iteration is normal, ambiguity is expected and PMs don't need to be AI experts.
- **Encouraging.** "You don't need to be an AI expert — focus on understanding the users, business needs, and guide us on what's good."

## Document Structure

Use this consistent structure for playbook pages:

### 1. What Is It?
1-2 sentences explaining the concept or phase. Plain English.

### 2. Your Role (as PM)
What the PM specifically does here. Use **DO** and **DON'T** formatting:
- **DO:** Define the "why" — what user pain are we solving?
- **DON'T:** "I want a chatbot" (solution-first thinking)

### 3. Your Actions
Concrete checklist of what to do:
- [ ] Action item with specific instruction
- [ ] Action item with link to template or tool

### 4. Example
A realistic GBT example. Use travel domain scenarios:
> As a Travel Manager, I want help setting up policies so I don't waste time searching documents.

### 5. Checklist
A scannable checklist for PMs to verify they've covered everything:
- [ ] Item complete
- [ ] Item complete

## Content Types

### Glossary Entries
```
**[Term]** — [Plain English definition in one sentence]. [When a PM encounters this, what should they do about it?]
```

Keep definitions practical, not academic. "What does this mean for me?" is the test.

### Case Studies (Friction Case Studies format)
```
## [Project Name]

### What the agent does
[1-2 sentences]

### Where friction happened
[What went wrong between PM and AI team]

### Root cause
[Mapped to a specific playbook phase]

### How it was resolved
[What actually fixed it]

### What the playbook would have prevented
[The lesson — why following the process matters]
```

### Forum Session Materials
Reference the progressive session structure:
1. Session 1: How the AI team works (vocabulary + big picture)
2. Session 2: Evaluation deep dive (interactive exercise)
3. Session 3: Learning from friction (case studies)
4. Session 4: Hands-on workshop (practice)
5. Session 5+: Retrospective and iteration

Each session builds on the last. Materials should reference prior sessions and preview upcoming ones.

## Cross-Referencing

The playbook is interconnected. When writing, cross-reference related documents:
- Reference the glossary when using technical terms
- Link to the Evaluation Template when discussing Phase 5
- Link to CRISP-DM for PMs when explaining the lifecycle
- Reference the AI Forum Plan when creating session materials

## Writing Conventions

- Write for PMs with mixed AI literacy — assume smart but not technical
- Use tables for structured information (phase responsibilities, role comparisons)
- Use emoji sparingly and consistently (the existing playbook uses numbered emoji for phases)
- Keep documents self-contained enough to read standalone but connected enough to form a coherent series
- Include "Part of the GBT AI Playbook series" footer with links to related documents

---

<!-- FILE: skills/pre-mortem/SKILL.md -->

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

---

<!-- FILE: skills/prioritization/SKILL.md -->

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

---

<!-- FILE: skills/product-brainstorm/SKILL.md -->

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

---

<!-- FILE: skills/release-notes/SKILL.md -->

---
name: release-notes
description: Write release notes or changelog entries for different audiences. Use when shipping a feature, preparing a release communication, writing a changelog or announcing what's new to users, clients or internal teams.
---

# Release Notes

Write release communications tailored to the audience. What engineers care about is different from what users care about is different from what sales needs to know.

## Before Writing

Ask (skip what's already known):

1. **What shipped?** — Feature, fix, improvement, configuration change?
2. **Who's the audience?** — End users, Travel Managers, internal teams, clients, sales?
3. **What format?** — In-app notification, email, changelog entry, Slack post, client newsletter?
4. **What's the impact?** — Minor improvement, major new feature, breaking change?

## Templates by Audience

### User-Facing Release Notes
For travelers, Travel Managers and end users. Focus on benefits, not implementation.

```
## [Feature Name]

**What's new:** [1-2 sentences — what you can now do that you couldn't before]

**How it works:**
1. [Step 1 — where to find it]
2. [Step 2 — how to use it]
3. [Step 3 — what to expect]

**Why it matters:** [1 sentence — the benefit in user terms]
```

**Rules:**
- No internal jargon, no ticket numbers, no technical details
- Frame everything as what the user can now *do*, not what was *built*
- Use "you" language: "You can now..." not "We've implemented..."
- Include screenshots or GIFs if the feature is visual
- Mention known limitations honestly if they're user-facing

### Client Communication
For Travel Managers, account managers and client-facing teams. More detail, professional tone.

```
## [Feature/Update Name]

**Summary:** [What changed and who it affects]

**Details:**
- [Specific capability or change]
- [How it affects existing workflows]
- [Configuration needed, if any]

**Availability:** [When, which plans/tiers, any rollout phases]

**Action required:** [None / Configuration needed / Training recommended]

**Questions?** [Contact point or support channel]
```

### Internal Changelog
For engineering, product and support teams. Full detail.

```
## [Date] — [Release version or sprint]

### New
- **[Feature]** — [What it does]. [Ticket/PR link]. Owned by [team].

### Improved
- **[Change]** — [What's better and why]. [Link].

### Fixed
- **[Bug]** — [What was broken, what it does now]. [Link].

### Known Issues
- **[Issue]** — [Workaround if available]. [Expected fix timeline].
```

### Sales Enablement
For sales teams who need to pitch new capabilities. Focus on competitive advantage and client value.

```
## [Feature Name] — Sales Brief

**Elevator pitch:** [2 sentences — what it does and why clients care]

**Client value:**
- [Benefit 1 — tie to a client pain point]
- [Benefit 2]

**Competitive angle:** [How this compares to what competitors offer]

**Talk track:** "For clients who [pain point], we now [capability], which means [outcome]."

**Availability:** [When, which clients, any restrictions]

**Demo:** [Where to see it / how to show it]
```

## Writing Conventions

- Lead with the benefit, not the feature. "Find flights faster" not "Added search filters."
- Honest about limitations. "This is available for air bookings today; hotel support coming next quarter" builds more trust than silence.
- Group related changes together. Don't list 15 micro-changes — group them into themes.
- If there's a breaking change or required action, put it first and make it unmissable.
- Date everything. Release notes without dates are useless for support and troubleshooting.
- For major releases, include a "what's not changing" section if users might worry about disruption.

---

<!-- FILE: skills/retrospective/SKILL.md -->

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

---

<!-- FILE: skills/risk-assessment/SKILL.md -->

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

---

<!-- FILE: skills/sprint-planning/SKILL.md -->

---
name: sprint-planning
description: Plan a sprint or work iteration. Use when asked to plan a sprint, break down work, prioritize tasks for a time period or structure an iteration cycle for any product or AI project.
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

**For AI projects** — map sprint activities to the 7-phase lifecycle:
- **Phase 1-2 (Understanding):** Intake form, data source identification, stakeholder alignment
- **Phase 3 (Design):** Q&A behavior tables, tone guidelines, boundary definitions
- **Phase 4 (Development):** Answering AI team questions, reviewing checkpoints, preparing eval test cases
- **Phase 5 (Evaluation):** Running test cases, analyzing results, PM recommendation
- **Phase 6 (Risk Committee):** Smartsheet form, presentation prep, risk narrative
- **Phase 7 (Deployment):** Monitoring setup, feedback collection, iteration planning

**For platform/product projects** — map to the development stage:
- **Discovery:** User research, competitive analysis, opportunity sizing
- **Definition:** Specs, user stories, acceptance criteria, design reviews
- **Build:** Answering engineering questions, reviewing progress, preparing launch
- **Launch:** Release notes, stakeholder comms, monitoring, rollback criteria
- **Iterate:** Usage review, feedback synthesis, next iteration planning

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

---

<!-- FILE: skills/stakeholder-update/SKILL.md -->

---
name: stakeholder-update
description: Draft a status update, stakeholder communication or meeting summary. Use when asked to write an update, status report, progress summary or communication for managers, teams or broader audiences.
---

# Stakeholder Update

Generate a structured status update tailored to the audience. Different audiences need different levels of detail, framing and tone.

## Before Writing

Ask (skip what's already known):

1. **Who's the audience?** — Manager 1:1, AI team, AI Forum, PM org, leadership?
2. **What's the update about?** — A project, a sprint, an incident, a decision, general progress?
3. **What's the key message?** — If they remember one thing, what should it be?
4. **Any blockers or asks?** — Do you need something from the audience?

## Format by Audience

### Manager 1:1
Informal, concise, decision-oriented. Lead with what needs their attention.

```
## [Project/Topic]

**Status:** [On track / At risk / Blocked]
**Key update:** [1-2 sentences — the headline]

### Progress since last sync
- [Bullet points — what's moved]

### Needs your input
- [Decisions, approvals or escalations needed]

### Next steps
- [What's happening next and by when]
```

### AI Team Sync
Technical enough to be useful, PM enough to maintain the "why." Reference lifecycle phases.

```
## [Agent/Project] — Phase [X] Update

**Where we are:** [Current phase and progress within it]

### What's done
- [Completed items]

### What's next
- [Upcoming work, with who owns what]

### Questions for the team
- [Technical clarifications, data questions, timeline checks]
```

### AI Forum / PM Org
Educational, accessible, no jargon. Remember the audience has mixed AI literacy.

```
## [Topic] — Update for [date]

### The headline
[1-2 sentences: what happened and why it matters]

### What this means for PMs
[Practical implications — what should they do differently or be aware of?]

### What's coming next
[Preview of upcoming work, sessions or decisions]

### Questions / Feedback
[Open invitation — make it safe to ask]
```

### Leadership / Exec Summary
Metrics-first, business impact, minimal detail. Respect their time.

```
## [Project] — Executive Summary

**Status:** [On track / At risk / Blocked]
**Business impact:** [1 sentence — what this means for the business]

### Key metrics
| Metric | Target | Actual | Trend |
|--------|--------|--------|-------|
| [KPI] | [X] | [Y] | [Up/Down/Flat] |

### Decisions needed
- [If any — be specific about what you need and by when]

### Risks
- [Top 1-2 risks with mitigation]
```

## Writing Conventions

- Lead with the most important information — don't bury the lead
- Bold status indicators and key numbers
- Keep it scannable — bullet points over paragraphs
- For lifecycle updates, reference the phase number: "We're in Phase 5 (Evaluation)"
- Match formality to audience: informal for manager, structured for broader groups
- If reporting blockers, always include what you've already tried and what you need

---

<!-- FILE: skills/synthesize-research/SKILL.md -->

---
name: synthesize-research
description: Synthesize research inputs into structured insights. Use when asked to summarize articles, analyze notes, synthesize research, extract takeaways or make sense of messy inputs like meeting notes, newsletters or competitor announcements.
---

# Synthesize Research

Take messy inputs — articles, meeting notes, newsletter excerpts, competitor announcements, internal documents — and produce structured, actionable synthesis.

## Before Synthesizing

If inputs aren't provided, ask:
1. **What material am I working with?** — Paste text, share files or describe what you've read.
2. **What's the lens?** — Are you looking at this from a product angle, competitive angle, strategic angle or general awareness?
3. **Who's the synthesis for?** — Just you, your manager, the AI Forum, a broader audience?

## Synthesis Structure

### 1. Key Findings
3-5 bullet points. Each finding is a claim, not a description. "Airlines are accelerating NDC adoption" not "The article discusses NDC."

### 2. So What for GBT?
**Always include this section.** For every finding, translate it into implications for AMEX GBT specifically:
- What does this mean for our AI products or travel platform?
- Does this affect the competitive landscape?
- Does this create an opportunity or a risk?
- Is there something PMs across the business should be aware of?

### 3. Evidence & Confidence
For each finding, note:
- **Source** — Where this came from
- **Confidence** — How strong is the evidence? (Single anecdote vs. industry trend vs. hard data)
- **Recency** — When was this published/discussed?

### 4. Connections
Link findings to each other and to broader GBT context. Flag if something contradicts prior understanding or confirms an emerging pattern.

### 5. Action Items
Concrete next steps, if any emerge. Who should do what, and is it urgent or background?

## Synthesis Modes

Adapt based on the type of input:

**Newsletter/article digest:** Focus on "so what" — most newsletter content is noise. Extract the 2-3 things that actually matter for GBT.

**Meeting notes:** Focus on decisions made, actions assigned and open questions. Flag anything that was discussed but not resolved.

**Competitive intelligence:** Focus on what competitors are doing differently, where they're ahead/behind and what it means for GBT's positioning.

**Technical research:** Focus on practical applicability. Is this relevant to current AI projects? Does it change how we should think about evaluation, deployment or risk?

## Writing Conventions

- Be opinionated — "This matters because..." not "This could potentially be relevant..."
- Cite sources for specific claims
- Append confidence levels to non-obvious claims (e.g. "~70% confidence")
- Keep it scannable — headers, bullets, bold key terms

---

<!-- FILE: skills/user-personas/SKILL.md -->

---
name: user-personas
description: Create evidence-based user personas from research data. Use when building personas, defining target users, segmenting users by behavior or documenting who you're building for.
---

# User Personas

Create research-backed personas that capture who your users actually are — their goals, behaviors, pain points and context. Good personas drive better product decisions. Bad ones gather dust in a Confluence page.

## Before Writing

Ask (skip what's already known):

1. **What product or feature?** — Personas are most useful when scoped to a specific context.
2. **What research exists?** — Interviews, surveys, analytics, support tickets, sales call notes? Personas should come from data, not imagination.
3. **How many personas?** — 3-5 is the sweet spot. More than that and they're not actionable.
4. **What decisions will these inform?** — Feature prioritization, design direction, go-to-market, onboarding flows?

## Persona Structure

For each persona:

### [Persona Name] — [One-line description]

**Who they are:**
- Role, company type/size, experience level
- How they interact with the product or service
- Key context that shapes their behavior

**Primary job-to-be-done:**
- The core outcome they're trying to achieve
- How often they need to do this
- What "done well" looks like for them

**Top 3 pain points:**
| Pain | Severity | Current workaround |
|------|----------|-------------------|
| [Specific frustration] | High/Med/Low | [How they cope today] |

**Top 3 desired gains:**
| Gain | Importance | What success looks like |
|------|-----------|----------------------|
| [Benefit they want] | High/Med/Low | [Observable outcome] |

**Behavioral patterns:**
- How they discover, evaluate and adopt tools
- Frequency and depth of usage
- Who they collaborate with

**One unexpected insight:**
- A counterintuitive behavior or motivation from the research
- Why this matters for product decisions

**Representative quote:**
> "[Verbatim or composite quote that captures this persona's perspective]"

## GBT Persona Examples

These are starting points — refine with actual research data:

**The Hands-On Travel Manager**
- Manages 200-500 travelers at a mid-size company
- Deeply involved in policy configuration and exception handling
- Pain: spends too much time on manual tasks that should be automated
- Gain: wants confidence the program runs correctly without constant checking

**The Road Warrior**
- Travels 2-4 times per month, values speed and convenience
- Knows the booking tool well, has strong loyalty program preferences
- Pain: policy restrictions that don't account for real-world travel needs
- Gain: wants a seamless experience that respects their time and preferences

**The Reluctant Arranger**
- Books travel for others alongside their main job responsibilities
- Infrequent user, often confused by the booking flow
- Pain: can't remember how to do multi-traveler bookings or navigate approvals
- Gain: wants a process so simple they don't need to think about it

**The Finance Watchdog**
- Reviews travel spend reports monthly, focused on compliance and cost
- Never touches the booking tool directly
- Pain: reconciliation between travel spend, expense reports and supplier invoices
- Gain: real-time visibility into spend vs. budget by category and policy

## Building Personas from Research

### From interviews (qualitative)
1. Read through all notes and tag behavioral patterns
2. Look for clusters of similar goals, frustrations and contexts
3. The distinguishing variable should be *behavior*, not demographics
4. Each persona should be distinct — if two personas would make the same product decisions, merge them

### From analytics (quantitative)
1. Segment users by behavior: frequency, feature usage, workflow patterns
2. Size each segment — how many users fit each pattern?
3. Cross-reference with qualitative data to add depth

### From support tickets
1. Categorize issues by user type and frequency
2. Identify which personas generate the most (and most severe) support load
3. Map tickets to persona pain points

## Common Mistakes

- **Demographic personas:** Defining by age/gender/location instead of behavior. Behavior predicts product needs better than demographics.
- **Aspirational personas:** Describing who you *wish* your users were, not who they actually are.
- **Too many personas:** More than 5 means you can't prioritize. If everyone is a target, no one is.
- **No implications:** A persona that doesn't change any product decision is decoration, not a tool.
- **Static personas:** Never updated as the product and market evolve. Review annually at minimum.

## Writing Conventions

- Ground all insights in data — cite interview counts, survey percentages or behavioral evidence
- Use direct quotes from research when available
- Make personas specific enough to be useful: "manages 200-500 travelers" not "manages travelers"
- Include the "one unexpected insight" — this is what makes personas valuable beyond obvious observations

---

<!-- FILE: skills/write-spec/SKILL.md -->

---
name: write-spec
description: Draft a PRD, product specification or requirements document. Use when asked to write a spec, PRD, product brief, feature brief or requirements for any product feature, platform improvement or AI agent.
---

# Write Spec

Generate a structured product specification. Adapt the depth and formality to what's being specified — a lightweight feature brief needs less than a full agent PRD.

## Before Writing

Gather context by asking (skip what's already known):

1. **What problem are we solving?** — The user pain, not the solution. Who's affected and how badly?
2. **Who's the primary persona?** — Travel Manager, business traveler, arranger, finance, compliance?
3. **What does success look like?** — Measurable outcomes. How will we know this worked?
4. **What phase are we in?** — For AI projects, map to the 7-phase lifecycle. For platform/product work, note where you are in the development cycle.
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
High-level approach. What the feature does, not how it's built. Include:
- Key interactions or workflows
- Behavioral boundaries (for AI agents: what it should and shouldn't do)
- Tone and personality guidelines (for agent specs)
- UI/UX considerations (for platform features: key screens, flows, states)

### 4. Success Metrics
Tie each metric to a user story or problem statement. Include:
- **Primary KPI** — The one number that defines success
- **Supporting metrics** — 2-3 secondary indicators
- **Guardrail metrics** — What must not get worse (e.g. response accuracy, compliance adherence)

### 5. Scope & Non-Goals
Explicit list of what's included and what's deliberately excluded. Non-goals prevent scope creep and set expectations.

### 6. Dependencies & Risks
Team dependencies, compliance considerations, technical unknowns. Consider:
- Integration points with other systems (booking engine, expense, HR)
- Client configuration or migration needs
- Multi-market/multi-language implications
- Duty of care implications (if traveler-facing)

For AI agents, also include:
- Data source availability and quality
- Hallucination/accuracy risks
- Multi-client data isolation

### 7. Open Questions
Unresolved items that need answers before or during development. Tag each with who should answer (PM, AI team, legal, client).

## Output Conventions

- Bold key terms and metrics
- Keep sections concise — a good spec is scannable, not exhaustive
- For AI agent specs: include a behavior table (User says -> Agent should respond)
- For platform features: include key user flows or state diagrams where helpful
- Reference the GBT lifecycle phase (AI projects) or development stage (platform work)

## After Writing

Suggest running the spec past a product leader or VP for review — they'll catch gaps in metrics, edge cases and stakeholder framing.

If the spec is for Phase 5, suggest using `/eval-test-cases` to generate the corresponding evaluation set.
