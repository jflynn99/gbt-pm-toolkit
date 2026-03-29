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
