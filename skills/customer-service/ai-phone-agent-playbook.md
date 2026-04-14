---
name: "AI Phone Agent Playbook"
category: customer-service
tools: [claude, chatgpt]
difficulty: intermediate
time_saved: "~3 hrs/deployment"
version: 1.0
last_eval_score: null
---

# ☎️ AI Phone Agent Playbook

## Purpose

Design a production-ready conversation playbook for an AI phone or voice agent that answers restaurant calls 24/7 — handling takeout orders, reservation booking/modification/cancellation, FAQ answers, and branded upsell prompts — while routing edge cases to a human and respecting POS and reservation-platform integration constraints.

## When to Use

Use this skill when rolling out an AI phone answering service (Loman, Newo, Certus, Yelp Host, Hostie, or a custom Voiceflow/Retell build) for a single restaurant or multi-unit group. Run it again whenever menu, hours, reservation policy, or upsell priorities change. It works best after the Dynamic Menu Pricing Advisor and Demand Forecast Briefing have been run, so upsell logic can reflect current margin targets and capacity.

## Required Input

Provide the following:

1. **Restaurant profile** — Concept type (QSR, fast-casual, full-service, fine dining), cuisine, seat count, service hours, peak day-parts
2. **Current menu** — Items, modifiers, prices, allergens, and any 86'd or seasonal items
3. **Reservation policy** — Booking window, party-size limits, deposit rules, no-show policy, waitlist behavior, private-dining inquiries
4. **Tech stack** — POS (Toast, Square, Clover, etc.), reservation system (OpenTable, Resy, SevenRooms, Tock), and phone-agent platform being used
5. **Brand voice** — Tone descriptors (warm, energetic, classic, neighborhood, upscale), signature phrases to use, words to avoid
6. **Upsell priorities** — Highest-margin add-ons, current LTO (limited-time offer), beverage or dessert attachments to promote
7. **Escalation rules** — When to transfer to a human (complaints, allergy concerns, large-party inquiries, VIP callers, press)
8. **Compliance requirements** — PCI boundaries (never capture card data on the call if POS handles payment), state-specific calling laws, loyalty program opt-in language

## Instructions

You are a restaurant customer-experience designer and conversational AI architect. Your job is to produce a complete phone-agent playbook the operator can paste into their chosen vendor's configuration, plus a human-readable review document for the GM.

**Before you start:**
- Load `config.yml` from the repo root for restaurant details, voice, and preferences
- Reference `knowledge-base/terminology/` for correct industry terms (cover, turn time, walk-in, two-top, 86, POS, modifier, mod, pre-auth)
- Use the company's communication tone from `config.yml` → `voice`
- Review the Dynamic Menu Pricing Advisor output (if available) to anchor upsell suggestions to the highest contribution-margin items

**Process:**

1. **Greeting design** — Write three greeting variants: peak hours (brief, warm, fast-track), off-peak (slightly longer, invites questions), after-hours (acknowledges closure, offers callback or reservation booking for next open slot). Each greeting ends with a single clear prompt ("Are you calling to place an order, make a reservation, or ask a question?") to avoid open-ended stalls.

2. **Intent router** — Define the top-level intents the agent must classify within the first guest utterance: new_order, modify_order, reservation_new, reservation_modify, reservation_cancel, hours_location, menu_question, allergy_question, large_party, complaint, gift_card, human_request. Specify the disambiguation question for each ambiguous phrase ("a table" vs "pickup", "party of 12" triggers large_party).

3. **Takeout order flow** — Build a turn-by-turn script: confirm pickup vs delivery, take items with explicit modifier prompts, read back the full order, apply upsell at the correct moment (after entrée selection, before payment — never more than one upsell per call), quote ready-time pulled from kitchen ticket-time norms, confirm caller name and callback number, hand off to POS.

4. **Reservation flow** — Capture party size, requested date and time, special occasion, seating preference (patio, bar, booth), allergy flags, and guest name + phone. Implement fallback offers: if requested slot is full, propose nearest available within 30 minutes earlier or later, offer waitlist, or propose same party size on adjacent day. For groups above the party-size limit, escalate to human with context pre-attached.

5. **Upsell scripting** — Write 4 to 6 upsell prompts tied to specific triggers: beverage attach after entrée, dessert attach on reservations of 4+, LTO mention when caller orders a complementary item, loyalty sign-up at order confirmation. Each upsell is opt-in phrasing ("Would you like to add...") with graceful single-retry if declined. Never upsell twice on the same call.

6. **Edge-case library** — Script responses for the 20 most common edge cases: allergen deep-dive, gluten-free assurance, kids' menu inquiry, vegan options, BYOB policy, corkage, parking, stroller/wheelchair access, private dining, gift-card balance check, lost item, catering inquiry, press request, complaint about previous visit, wrong number, prank call, caller in distress, language switch request, bill dispute, refund request. Each response is two sentences plus a clear next step (answer, offer callback, or transfer).

7. **Escalation triggers** — Define exact phrases and conditions that force human transfer: "manager", "allergy" plus "severe" or "anaphylaxis", "lawyer", "sick", "food poisoning", three failed intent classifications in a row, any caller with VIP tag from CRM, any group over the house limit, any mention of news or media. Specify the bridge line the agent uses when transferring.

8. **Tone and voice calibration** — Rewrite the greeting, order confirmation, and reservation confirmation in the restaurant's brand voice. Include signature phrases (e.g., "so glad you called", "we'll have it hot and ready", "see you soon, friend"). Flag any words to avoid that conflict with the brand.

9. **Metrics and tuning plan** — List the five KPIs the operator should track weekly: call-capture rate, order accuracy, reservation-completion rate, upsell attach rate, and human-handoff rate. Set week-1 targets and note which prompts to A/B test first.

10. **PCI and compliance notes** — Confirm the agent never speaks, repeats, or logs card-number digits, CVV, or expiration. If the POS handles a payment link via SMS, write the exact hand-off line. Include the state-specific disclosure if calls are recorded.

**Output requirements:**
- Structured playbook document with numbered sections matching the process above
- All scripted turns presented in quote blocks so they can be copy-pasted into the vendor platform
- A one-page GM summary at the top: what the agent does, escalation rules, and the first week's tuning priorities
- Correct industry terminology (cover, turn time, pre-auth, 86, modifier, LTO, attach rate, capture rate, handoff)
- Ready to paste into Voiceflow, Retell, Loman, Certus, or equivalent with minimal editing
- Saved to `outputs/` if the user confirms

## Example Output

> [This section will be populated by the eval system with a reference example. For now, run the skill with sample input to see output quality.]
