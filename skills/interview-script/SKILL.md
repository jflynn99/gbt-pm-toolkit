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
