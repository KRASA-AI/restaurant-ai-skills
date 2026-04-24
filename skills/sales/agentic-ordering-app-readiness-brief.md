---
name: "Agentic Ordering App Readiness Brief"
category: sales
tools: [claude, chatgpt]
difficulty: intermediate
time_saved: "~4-6 hr/brand/quarter"
version: 1.0
last_eval_score: null
---

# 🛒 Agentic Ordering App Readiness Brief

## Purpose

Produce a brand-level readiness brief for launching (or deciding not to launch) a first-party ordering experience inside a conversational AI assistant — the in-ChatGPT / in-Gemini / in-Claude / in-Perplexity "app" pattern that lets a guest describe a craving, group, budget, or mood in natural language and walk out with a prepared order. Covers the checkout-stance decision (keep payment in the brand's own app and loyalty wallet vs. allow end-to-end checkout inside the assistant via an aggregator such as Bites), the vibe-to-menu mapping layer, the menu structure that agentic construction requires, pricing-parity and disclosure commitments, loyalty account-linking path, commission-displacement and third-party-delivery governance, edge-case and fallback copy, and the four-metric measurement plan that tells the operator whether in-assistant ordering is a growth channel or a cannibalization channel.

## When to Use

Run this brief when a brand is evaluating its first in-assistant ordering app (ChatGPT apps, Gemini extensions, Claude apps, Perplexity shopping, or an emerging agent surface), when a chain CEO has just seen a competitor's announcement and wants a position paper by end of week, when a loyalty program leader is worried an in-assistant launch will leak loyalty attach rate, when a VP Digital is sizing the commission-displacement case for bypassing third-party delivery via a direct-ordering aggregator, or when a franchise system needs a governance framework before individual franchisees enable third-party in-assistant aggregator listings.

Scope is conversational in-assistant ordering. For discovery and reservation-capture through AI answer engines, use the AI Search Visibility Playbook. For third-party delivery storefronts (DoorDash, Uber Eats, Grubhub, Deliverect-mediated channels), use the Digital Menu Optimization Brief. For voice ordering at the drive-thru lane, use the Drive-Thru AI Rollout Playbook. For full-service phone / reservation voice agents, use the AI Phone Agent Playbook. These five skills together form the complete AI-surface coverage map for a modern restaurant brand.

## Required Input

Provide the following:

1. **Brand profile** — Concept (QSR, fast-casual, coffee, pizza, full-service), number of locations, owned vs. franchised mix, market footprint (US-only, multi-country), daypart mix, average ticket, and the proportion of digital vs. in-person orders today
2. **Current digital stack** — Native mobile app (iOS, Android), web ordering provider, POS (Toast, Square, Clover, PAR, NCR Voyix, Qu, Revel), loyalty program and vendor, payment processor, delivery integration layer (Deliverect, Olo Rails, Checkmate, Otter, ItsaCheckmate), and any existing agentic menu feed (Deliverect AI, Square + MarketMan, Olo menu tuner)
3. **Assistant surfaces under consideration** — First-party in-assistant app (ChatGPT app, Gemini extension, Claude app, Perplexity shopping), aggregator in-assistant listing (Bites or equivalent direct-ordering network), or both; country availability; launch date target
4. **Loyalty posture** — Hard requirement that loyalty points accrue on every order, soft preference, or indifferent; whether the loyalty program is the brand's main customer-acquisition flywheel; whether a loss of loyalty attach on in-assistant orders is acceptable during a test window
5. **Checkout-stance options** — Whether the brand will accept end-to-end checkout inside the assistant (the guest pays without leaving ChatGPT or Gemini), require a deep-link handoff to the brand's own app or web checkout (the Starbucks / Little Caesars pattern), or pilot both
6. **Vibe / persona target list** — 15 to 30 sample guest prompts this assistant app must handle well on day one (e.g., "a light dinner for four under $60 with one vegan and one gluten-free guest," "a pick-me-up espresso drink that matches this photo of a rainy window," "a family pizza night for six with two picky kids under ten")
7. **Menu source of truth** — HTML canonical menu URL (or equivalent structured feed), modifier and variant taxonomy, dietary and allergen tags, daypart availability rules, off-menu items to suppress, and the regional variance rules (state-specific menu items, alcohol rules, franchise-specific LTOs)
8. **Competitive coverage** — Which peer brands have already shipped in-assistant apps on the same surface, what checkout stance each chose, and any public claims on commission or conversion lift
9. **Risk tolerance and governance** — Who signs off on launch (CEO, CMO, CDO, VP Digital), whether franchisees can opt in or out individually, data-sharing constraints (can the assistant vendor see per-guest order history?), and the brand's public position on AI-generated recommendations
10. **Measurement commitments** — What the brand will report to leadership at 4 weeks and 12 weeks: channel revenue, average order value, loyalty attach rate on in-assistant orders, repeat rate, basket abandonment at handoff, and any cannibalization of native app or third-party delivery orders

## Instructions

You are a digital-channel strategist who has launched ordering experiences across native apps, third-party delivery, kiosks, drive-thrus, and now conversational AI assistants, and who understands the commercial and brand-posture tradeoffs of each checkout stance. Your job is to produce a concrete one-brand readiness brief — not a generic "agentic commerce is the future" think piece.

**Before you start:**
- Load `config.yml` for brand voice, loyalty-program rules, forbidden claims, and regional menu variance
- Reference `knowledge-base/terminology/` for restaurant-specific phrasing (attach rate, basket, handoff, parity, LTO, variant, modifier, daypart)
- Reuse the Menu Description Writer output for canonical item copy so in-assistant descriptions match the rest of the stack
- Reuse the Digital Menu Optimization Brief output for modifier ontology so agent-built baskets reconcile with third-party delivery storefronts
- Reuse the AI Search Visibility Playbook output so target guest prompts, FAQ content, and schema signal a coherent brand to both discovery and ordering surfaces
- Pull the most recent assistant-surface documentation (ChatGPT apps developer notes, Gemini extensions, Claude app SDK, Perplexity shopping) and the aggregator's integration spec before writing any step — vendor mechanics change monthly in 2026

**Process:**

1. **Checkout-stance decision brief** — Produce a two-page decision brief comparing first-party in-assistant app + handoff-to-brand-checkout (the Starbucks and Little Caesars pattern) vs. end-to-end in-assistant checkout via a direct-ordering aggregator (the Bites pattern) vs. both-in-parallel. Score each option against: loyalty attach rate, gross margin after third-party delivery commission, data ownership, brand-voice control at the moment of purchase, speed to market, and franchise-operator acceptability. Recommend one stance for the first 90 days and document the trigger conditions that would force a revisit.

2. **Vibe and persona mapping layer** — For each of the 15 to 30 target guest prompts in the input, write the expected agent reasoning (inputs the model should extract: mood, group size, dietary filters, budget ceiling, occasion, pickup vs. delivery, daypart), the canonical menu pick(s) the agent should propose, the runner-up if the primary is unavailable, and the upsell attach (size up, add-on, dessert, loyalty enroll). Flag prompts that should explicitly hand off to a human ("I have a nut allergy and my daughter is anaphylactic" must not proceed to checkout without a human-reviewed allergen confirmation). Make explicit that the agent's persona interprets user phrasing but does not invent menu items that do not exist on the canonical source.

3. **Menu structure for agentic construction** — Specify the menu-data shape the assistant app needs on day one: canonical item ID, display name, size tier, per-size price, modifier groups with min/max selection rules, dietary and allergen tags, daypart availability, store-level availability, LTO windows, combo rules, and substitution suggestions. Call out the four failure modes agentic construction trips on — phantom modifiers ("add extra jalapeño" when jalapeño is not a modifier), dietary contradiction ("vegan" + "bacon"), price drift across channels, and group-size scaling without a max-cart guard — and prescribe the data-layer fix for each. Reuse the Digital Menu Optimization Brief's modifier ontology so the third-party-delivery and in-assistant surfaces stay reconciled.

4. **Loyalty and account-linking path** — Prescribe the account-linking flow end-to-end: first-time account link (OAuth token exchange with the brand's identity provider, fallback OTP via SMS or email if OAuth is not live), linked-account return path (silent refresh, reauth after 30 days or policy window), pickup-location binding (nearest store detection, explicit store selection, handoff if the selected store is unavailable), and the loyalty-attach promise (points post within X minutes, tier progress visible in-assistant or only in the brand's own app). Name the three loyalty-preservation patterns: handoff-to-app (Starbucks-style), in-assistant link-on-first-order (deferred account creation), and pre-linked (the guest is already signed in because the brand has a live integration). Recommend which pattern the brand should ship first.

5. **Pricing parity and disclosure commitments** — Require price parity with the brand's own app and web for the first 90 days — no in-assistant markup, no hidden service fee, no inflated delivery minimum. Draft the exact disclosure line the assistant app displays before checkout ("Prices match the [Brand] app. A standard delivery fee applies for delivery orders."), the source-of-truth price feed path, and the per-SKU drift alert threshold (more than $0.05 difference between the canonical menu and the assistant surface triggers an immediate sync). Spell out what the brand will disclose to the assistant vendor about pricing logic vs. what is contractually protected.

6. **Commission-displacement and third-party-delivery governance** — Produce a one-page governance position on whether the brand allows a direct-ordering aggregator (Bites-class) to fulfill orders inside the assistant that would otherwise have gone through third-party delivery (DoorDash, Uber Eats, Grubhub), and under what conditions. Answer: does the brand accept lower-commission aggregator fulfillment even if unit economics are not identical to native app orders? Does it require the aggregator to use the brand's own delivery network, a shared network, or a third-party-delivery last-mile? How does it prevent double-listing confusion (the same guest seeing the brand via DoorDash inside ChatGPT and via Bites inside ChatGPT)? For franchise systems, document the opt-in / opt-out mechanism, the minimum market-coverage threshold, and the escalation path if a franchisee objects.

7. **Edge-case and fallback copy** — Draft the exact assistant app phrases for the 12 most likely edge cases: item out of stock ("The [item] you asked about is 86'd at this store — want to try [nearest alternative]?"), store closed ("[Store] is closed right now; the next opening is [time]. Want me to schedule pickup then, or try a nearby location?"), delivery zone mismatch ("That address is outside our delivery range. Pickup is available at [nearest store] — want to switch?"), allergen conflict ("You mentioned a peanut allergy, and [item] is prepared in a kitchen that handles peanuts. I'll recommend [alternative] — please confirm with the store before you pick up."), budget exceeded ("Your cart is $4 over your $60 cap — remove [item], swap to a smaller size, or increase the cap?"), modifier unavailable, age-restricted item (alcohol), franchise-variance item, gift card or catering ("That's better handled by our [catering / gift card] team — want me to open that page?"), payment declined, session timeout, and a general "I don't know how to help with that" graceful handoff. Every fallback must preserve brand voice and avoid fake urgency.

8. **Measurement plan and reporting cadence** — Define the four metrics that close the loop: in-assistant channel revenue (weekly, monthly, quarterly), average order value vs. native app vs. third-party delivery, loyalty attach rate on in-assistant orders (target within 10 points of native app by week 12), and basket abandonment at the checkout handoff (the drop-off between "cart confirmed in assistant" and "payment completed in brand app"). Add two cannibalization checks: share of in-assistant orders that appear to displace native-app orders from the same guest, and share that displaces third-party delivery. Specify the owner, the reporting cadence (weekly for the first 12 weeks, monthly thereafter), and the four-week-in go / hold / roll-back gate thresholds.

9. **Launch-day comms and brand-posture pack** — Produce the launch-day communication pack: a one-paragraph public statement, a three-line loyalty-member email or push that links the account before first use, a franchise-operator FAQ (5–8 questions: capex, commission, loyalty attach, opt-out, brand-standards liability if the AI recommends something embarrassing), a two-line crew briefing ("Guests may arrive with orders placed through ChatGPT — treat them the same as app orders"), and a one-paragraph press-ready response for trade-press follow-ups. Do not overclaim — the tech is new and press scrutiny is high. Frame the launch as guest-convenience, not labor-displacement.

10. **Assistant-vendor and aggregator contract checklist** — Close with a pre-signature checklist the brand's legal and digital teams run before agreeing to any assistant-app or aggregator contract: data-use rights (what the vendor may do with per-order data, guest identifiers, recipe descriptions), brand-voice carveouts (can the vendor's own prompts rewrite the brand's item descriptions?), exclusivity clauses, price-parity terms, delisting cadence (how fast can the brand exit if unit economics break), incident-escalation SLA, SLA on menu-sync latency, and a termination-for-reputation clause for cases where the assistant platform ships a model update that produces embarrassing or unsafe recommendations.

**Output requirements:**

- Structured brief document with numbered sections matching the process above
- All assistant-app copy (disclosures, fallback lines, edge-case handoffs, loyalty prompts) in quote blocks so they can be pasted directly into the assistant-app configuration
- A one-page CEO / CDO summary at the top: recommended checkout stance, loyalty stance, commission-displacement position, 4-week and 12-week KPI targets, and the three biggest risks
- Correct restaurant-industry terminology throughout (attach rate, basket, parity, 86, LTO, daypart, handoff, capex, FBC, modifier, variant)
- Ready to paste into a board-ready slide deck, a franchise-operator FAQ, or a vendor SOW with minimal editing
- Saved to `outputs/` if the user confirms

## Related Skills

- `sales/ai-search-visibility-playbook.md` — Being found and booked via AI answer engines; upstream discovery surface to this ordering surface
- `sales/digital-menu-optimization-brief.md` — Third-party-delivery menu structure; shares the modifier ontology referenced in step 3
- `sales/menu-description-writer.md` — Canonical item copy reused as the assistant-app item description source
- `customer-service/ai-phone-agent-playbook.md` — Voice-agent surface for full-service phone / host / reservation
- `customer-service/drive-thru-ai-rollout-playbook.md` — Voice-agent surface for QSR drive-thru lanes
- `admin/dynamic-menu-pricing-advisor.md` — Contribution-margin source for upsell prioritization in step 2

## Example Output

> [This section will be populated by the eval system with a reference example. For now, run the skill with sample input to see output quality.]
