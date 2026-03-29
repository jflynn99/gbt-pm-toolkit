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
