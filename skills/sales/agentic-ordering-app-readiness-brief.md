---
name: "Agentic Ordering App Readiness Brief"
category: sales
tools: [claude, chatgpt]
difficulty: intermediate
time_saved: "~4-6 hr/brand/quarter"
version: 1.4
last_eval_score: 9.20  # 2026-07-13: worked example extended to the 4th (POS-native) stance — 4-column matrix + Section 1b. Weighted HOLDS at 9.20: the example now EARNS the output_quality 10 that 07-06 was already carrying. The 07-06 note's promised "+0.20 to 9.40" was arithmetically unavailable — see scores.yml.
---

# 🛒 Agentic Ordering App Readiness Brief

## Purpose

Produce a brand-level readiness brief for launching (or deciding not to launch) a first-party ordering experience inside a conversational AI assistant — the in-ChatGPT / in-Gemini / in-Claude / in-Perplexity "app" pattern that lets a guest describe a craving, group, budget, or mood in natural language and walk out with a prepared order. Covers the checkout-stance decision — keep payment in the brand's own app and loyalty wallet, allow end-to-end checkout inside the assistant via an aggregator such as Bites, or ride a **POS-native, auto-opted-in integration** in which the point-of-sale platform itself publishes the brand into the assistant with zero merchant setup (the Square-in-ChatGPT / Square-in-Claude pattern that went live 2026-07-01, where eligible US Square Online Ordering merchants were opted in with no work and orders route straight into existing Square POS, Kitchen Display, and reporting), or simply *inherit* an **aggregator-mediated agent surface** the brand never opted into (the guest's assistant drives a third-party-delivery app on the guest's behalf — Gemini task automation building a DoorDash or Uber Eats cart on Android and stopping short of the final "place order" tap; Alexa+ conversational ordering through Uber Eats and Grubhub) — the vibe-to-menu mapping layer, the menu structure that agentic construction requires, pricing-parity and disclosure commitments, loyalty account-linking path, commission-displacement and third-party-delivery governance, edge-case and fallback copy, and the four-metric measurement plan that tells the operator whether in-assistant ordering is a growth channel or a cannibalization channel.

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
- Check whether the brand's **POS platform has already published it into an assistant** before scoping a build. As of 2026-07-01, Square auto-opted-in eligible US food-and-beverage sellers with active Square Online Ordering profiles into a ChatGPT app and a Claude plugin at no extra cost and zero technical setup, with orders flowing into existing Square POS / Kitchen Display / reporting; if the brand runs Square (or another POS that ships a comparable native integration), the "should we build?" question may already be moot for the base ordering flow — the real decision shifts to loyalty attach, checkout mechanic (in-chat completion via Order by Cash App vs. redirect to the brand's ordering page with the basket pre-populated), and whether to layer a brand-owned app on top
- Separate the surfaces the brand **chooses** from the surface it **inherits**. A brand can decline to build an in-assistant app and still have agent-originated orders arriving today, because the guest's assistant can drive the *aggregator's* app rather than the brand's: Gemini-class task automation on Android assembles a DoorDash / Uber Eats basket end-to-end and hands the final "place order" tap back to the guest, and Alexa+-class voice assistants take conversational orders through Uber Eats and Grubhub. These orders land in the brand's existing third-party-delivery pipe at full marketplace commission and are invisible in channel reporting — they look like ordinary aggregator orders. Establish, before Step 1, whether the brand can even *see* this traffic; if it cannot, the first deliverable is an attribution ask to the aggregators, not a build plan
- Track the emerging **agentic-commerce protocol landscape** so the brief does not lock the brand to one vendor: the Agentic Commerce Protocol (OpenAI + Stripe), the Universal Commerce Protocol / UCP (Square + Google, being co-developed specifically for local food ordering and delivery), the AAIF Agentic Commerce Working Group, and the W3C Web Payments Working Group. Prefer stances that keep the brand portable across these standards rather than single-surface exclusives

**Process:**

1. **Checkout-stance decision brief** — Open by separating the **inherited** surface from the **chosen** ones. The inherited surface — (0) **aggregator-mediated agent ordering**, where the guest's assistant drives a third-party-delivery app rather than the brand's (Gemini-class cart-building on Android that stops at the final tap; Alexa+-class conversational ordering via Uber Eats / Grubhub) — is not a stance the brand elects; it is happening whether or not the brand ships anything, it carries full marketplace commission, and it is reported as ordinary aggregator volume. Quantify it (or state plainly that the brand cannot yet see it) before recommending any build, because it sets the baseline the chosen stances have to beat. Then produce a two-page decision brief comparing the four live stances the brand can actually choose: (a) first-party in-assistant app + handoff-to-brand-checkout (the Starbucks and Little Caesars pattern); (b) end-to-end in-assistant checkout via a direct-ordering aggregator (the Bites pattern); (c) **POS-native auto-opted-in publication** (the Square-in-ChatGPT / Square-in-Claude pattern live 2026-07-01 — the POS platform lists the brand with zero merchant setup and no marketplace commission, charging only the standard online transaction fee, ~2.9% + 30¢, and orders drop straight into the existing POS / KDS / reporting stack); and (d) two-or-more-in-parallel. Score each option against: loyalty attach rate, gross margin after third-party delivery commission, data ownership, brand-voice control at the moment of purchase, speed to market (POS-native can be effectively day-zero since the merchant does nothing), and franchise-operator acceptability. For the POS-native stance, explicitly resolve the checkout-mechanic fork — completion entirely in-chat (e.g., Order by Cash App) vs. redirect to the brand's own ordering page with the basket pre-populated — because that fork, not the build effort, is where loyalty attach and brand-voice control are won or lost. Recommend one stance for the first 90 days and document the trigger conditions that would force a revisit.

2. **Vibe and persona mapping layer** — For each of the 15 to 30 target guest prompts in the input, write the expected agent reasoning (inputs the model should extract: mood, group size, dietary filters, budget ceiling, occasion, pickup vs. delivery, daypart), the canonical menu pick(s) the agent should propose, the runner-up if the primary is unavailable, and the upsell attach (size up, add-on, dessert, loyalty enroll). Flag prompts that should explicitly hand off to a human ("I have a nut allergy and my daughter is anaphylactic" must not proceed to checkout without a human-reviewed allergen confirmation). Make explicit that the agent's persona interprets user phrasing but does not invent menu items that do not exist on the canonical source.

3. **Menu structure for agentic construction** — Specify the menu-data shape the assistant app needs on day one: canonical item ID, display name, size tier, per-size price, modifier groups with min/max selection rules, dietary and allergen tags, daypart availability, store-level availability, LTO windows, combo rules, and substitution suggestions. Call out the four failure modes agentic construction trips on — phantom modifiers ("add extra jalapeño" when jalapeño is not a modifier), dietary contradiction ("vegan" + "bacon"), price drift across channels, and group-size scaling without a max-cart guard — and prescribe the data-layer fix for each. Reuse the Digital Menu Optimization Brief's modifier ontology so the third-party-delivery and in-assistant surfaces stay reconciled.

4. **Loyalty and account-linking path** — Prescribe the account-linking flow end-to-end: first-time account link (OAuth token exchange with the brand's identity provider, fallback OTP via SMS or email if OAuth is not live), linked-account return path (silent refresh, reauth after 30 days or policy window), pickup-location binding (nearest store detection, explicit store selection, handoff if the selected store is unavailable), and the loyalty-attach promise (points post within X minutes, tier progress visible in-assistant or only in the brand's own app). Name the three loyalty-preservation patterns: handoff-to-app (Starbucks-style), in-assistant link-on-first-order (deferred account creation), and pre-linked (the guest is already signed in because the brand has a live integration). Recommend which pattern the brand should ship first.

5. **Pricing parity and disclosure commitments** — Require price parity with the brand's own app and web for the first 90 days — no in-assistant markup, no hidden service fee, no inflated delivery minimum. Draft the exact disclosure line the assistant app displays before checkout ("Prices match the [Brand] app. A standard delivery fee applies for delivery orders."), the source-of-truth price feed path, and the per-SKU drift alert threshold (more than $0.05 difference between the canonical menu and the assistant surface triggers an immediate sync). Spell out what the brand will disclose to the assistant vendor about pricing logic vs. what is contractually protected.

6. **Commission-displacement and third-party-delivery governance** — Produce a one-page governance position on whether the brand allows a direct-ordering aggregator (Bites-class) to fulfill orders inside the assistant that would otherwise have gone through third-party delivery (DoorDash, Uber Eats, Grubhub), and under what conditions. Anchor the commission math on the now-live spread: a POS-native assistant order (the Square-in-ChatGPT / Claude pattern) carries only the standard online-processing fee (~2.9% + 30¢) with no marketplace commission, versus a typical ~30% third-party-delivery aggregator cut — so an assistant order that displaces a DoorDash/Uber Eats order can recover on the order of 25+ margin points, which reframes assistant ordering as a delivery-disintermediation lever, not just a new discovery channel. **Do not overstate this: agent-originated does not mean commission-free.** When the guest's assistant drives the *aggregator's* app (the inherited surface in Step 1 — Gemini-class cart automation, Alexa+-class voice ordering through Uber Eats / Grubhub), the marketplace commission is fully preserved and the brand captures none of the spread. Disintermediation is a property of the *route*, not of the agent. The margin case therefore rests on winning route share — getting the guest's assistant to reach the brand's POS-native or first-party surface instead of the aggregator's app — which is a discovery, listing, and protocol problem, not a checkout problem. Size the two routes separately in the brief. State plainly whether the brand's goal is incremental demand, aggregator displacement, or both, because that goal changes the governance posture. Answer: does the brand accept lower-commission aggregator fulfillment even if unit economics are not identical to native app orders? Does it require the aggregator to use the brand's own delivery network, a shared network, or a third-party-delivery last-mile? How does it prevent double-listing confusion (the same guest seeing the brand via DoorDash inside ChatGPT and via Bites inside ChatGPT)? For franchise systems, document the opt-in / opt-out mechanism, the minimum market-coverage threshold, and the escalation path if a franchisee objects.

7. **Edge-case and fallback copy** — Draft the exact assistant app phrases for the 12 most likely edge cases: item out of stock ("The [item] you asked about is 86'd at this store — want to try [nearest alternative]?"), store closed ("[Store] is closed right now; the next opening is [time]. Want me to schedule pickup then, or try a nearby location?"), delivery zone mismatch ("That address is outside our delivery range. Pickup is available at [nearest store] — want to switch?"), allergen conflict ("You mentioned a peanut allergy, and [item] is prepared in a kitchen that handles peanuts. I'll recommend [alternative] — please confirm with the store before you pick up."), budget exceeded ("Your cart is $4 over your $60 cap — remove [item], swap to a smaller size, or increase the cap?"), modifier unavailable, age-restricted item (alcohol), franchise-variance item, gift card or catering ("That's better handled by our [catering / gift card] team — want me to open that page?"), payment declined, session timeout, and a general "I don't know how to help with that" graceful handoff. Every fallback must preserve brand voice and avoid fake urgency.

8. **Measurement plan and reporting cadence** — Define the four metrics that close the loop: in-assistant channel revenue (weekly, monthly, quarterly), average order value vs. native app vs. third-party delivery, loyalty attach rate on in-assistant orders (target within 10 points of native app by week 12), and basket abandonment at the checkout handoff (the drop-off between "cart confirmed in assistant" and "payment completed in brand app"). Add two cannibalization checks: share of in-assistant orders that appear to displace native-app orders from the same guest, and share that displaces third-party delivery. Add one **route-share** check: of all agent-originated orders the brand can identify, what fraction arrived via the brand's own (POS-native or first-party) route versus the aggregator-mediated route. This is the metric that tells the operator whether the disintermediation thesis in Step 6 is actually being realized — channel revenue can grow while route share moves the wrong way, and only the route-share read distinguishes those two worlds. If the aggregators do not expose agent-origination flags, record that as an open attribution gap and make it a standing quarterly ask, not a silent omission. Specify the owner, the reporting cadence (weekly for the first 12 weeks, monthly thereafter), and the four-week-in go / hold / roll-back gate thresholds.

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

### Example 1 — 50-unit fast-casual evaluating ChatGPT app (handoff-to-app) vs. Bites aggregator end-to-end checkout

**Input (CEO-level brief request, 5-day deadline):**
- Brand: Cinco Coastal, 50-unit fast-casual coastal-California concept (CA + AZ + NV + TX); all corporate-owned, no franchise
- Current digital stack: native iOS + Android app (Olo-built), Olo Rails into UE / DD / Grubhub, Toast POS, Punchh loyalty (2.4M members, 38% digital-order loyalty attach), Stripe payments, Deliverect for marketplace menu sync
- Assistant surfaces under consideration: ChatGPT app (Apple-distribution global ChatGPT 5.5 release expected mid-2026) + Bites aggregator listing on ChatGPT — board wants a recommendation by Friday
- Loyalty posture: Hard requirement — Punchh attach is the CEO's growth flywheel; CMO can accept attach degradation up to a floor of 28% (vs. 38% baseline) during a 12-week test if the channel revenue replaces it
- Checkout-stance options: (a) handoff-to-app pattern (Starbucks-style), (b) Bites end-to-end inside ChatGPT, (c) parallel pilot
- Vibe / persona target list (sample): "a light dinner for two under $35 with one pescatarian," "a coastal-grain bowl that's not too spicy for my picky 7-year-old," "a healthy lunch I can pick up in 12 minutes," "an order I can split between two pickup points for a work team of 12," "happy hour drinks pickup at the closest store, $50 budget, group of 6"
- Menu: 47 SKUs across 4 categories; modifier taxonomy 6-deep average; dietary/allergen tags complete; daypart rules live (HH 15:00–18:00 weekdays); 2 states have variant items (TX kolache add-on; AZ no-alcohol in 3 dry-county units)
- Competitive coverage: Starbucks ChatGPT app (handoff-to-app, no in-assistant checkout, launched 2026-04 with public claim of 4% lift on AOV from group orders); Little Caesars ChatGPT app (handoff-to-app, "Vibe Ordering" press claims 7% repeat-rate lift); Sweetgreen (no in-assistant surface yet); Chipotle (no in-assistant surface yet); Cava (announced exploring, no ship)
- Risk tolerance: CEO + CDO sign launch; data-sharing constraint — no per-guest history may be shared with the assistant vendor; brand wants public framing as "guest-convenience, not labor-displacement"
- Measurement commitments: 4-week and 12-week reports to the board; weekly internal flash; CDO owns

**Output — 1-page CEO summary (top of the brief):**

> **Recommendation:** Ship the **ChatGPT app handoff-to-Cinco-Coastal-app pattern (Option a) as the first 90-day stance.** Defer the Bites end-to-end aggregator checkout (Option b) to a Phase 2 evaluation after the 12-week handoff results clear the loyalty-attach floor. Run no parallel pilot — split testing across two checkout patterns in the first 90 days dilutes signal on both surfaces and confuses guests reading press coverage.
>
> **Loyalty stance:** Punchh attach is the deal-breaker. Handoff-to-app gives us full identity continuity. Bites end-to-end will degrade attach by ~12–18 points based on Little Caesars' public commentary and Bites-class aggregator commission economics — below our 28% floor in 3 of the 4 internal projection scenarios.
>
> **Commission-displacement position:** We are NOT ready to allow Bites-class aggregator fulfillment in Phase 1. UE + DD + Grubhub remain the only third-party fulfillment channels through 2026-Q3. We will revisit when Bites publishes a measured-ROI deployment case with a Punchh-class loyalty integration disclosed.
>
> **4-week KPI targets (CDO-owned):** In-assistant channel revenue ≥ $480K (~$2.4M annualized run-rate at 50 units, ~1% of total digital); AOV within 5% of native-app AOV; loyalty attach ≥ 32% (vs. 38% baseline; floor 28%); basket abandonment at handoff ≤ 22% (this is the new metric; no baseline).
>
> **12-week KPI targets:** In-assistant channel revenue ≥ $1.6M (cumulative); AOV within 3% of native-app; loyalty attach ≥ 34%; basket abandonment ≤ 18%; cannibalization of native-app from same-guest cohort ≤ 14% (acceptable swap zone — beyond this we are buying our own customers via OpenAI's surface, which is not the strategy).
>
> **Top 3 risks:** (1) Apple distribution flake — if ChatGPT 5.5 global rollout slips past 2026-Q3, our launch window slips with it; mitigation: stage launch around an OpenAI press window, not a fixed date. (2) Cannibalization of native-app from same-guest cohort — if same-guest swap rate exceeds 14%, we are paying OpenAI rev-share + Apple cut on revenue we already owned; mitigation: weekly cannibalization read at the cohort level. (3) Embarrassing-recommendation risk — the assistant may surface item combos our brand voice wouldn't (e.g., "kale bowl with extra ranch and bacon"); mitigation: termination-for-reputation contract clause with a 24-hour delisting SLA.

**Section 1 — Checkout-stance decision matrix:**

| Lever | Handoff-to-app (Starbucks pattern) | End-to-end via Bites | POS-native auto-opt-in (Square pattern) | Parallel pilot |
|---|---|---|---|---|
| Loyalty attach (projected at wk 12) | 34–38% (within 0–4 pts of baseline) | 22–28% (degraded, near floor) | **Not available on Toast today.** If Toast ships an equivalent: attach depends entirely on the in-chat-vs-redirect fork — redirect-with-basket ≈ handoff economics (34–38%); complete-in-chat ≈ Bites-class degradation (22–28%) | Confounded — neither surface gets clean signal |
| Gross margin after commission | Native-app economics (no marketplace cut) | 6–9 pts below native-app (Bites 12–15% commission + Stripe) | **Best-in-class if available** — no marketplace commission, standard online transaction fee only (~2.9% + 30¢ on the Square pattern), i.e. ~9–12 pts better than a 12–15% aggregator cut | Mixed |
| Data ownership | Full — Cinco Coastal owns the order, identity, loyalty | Partial — Bites holds the order; we receive a feed | Full — order lands in the POS / KDS / reporting stack the brand already owns | Confounded |
| Brand voice at purchase moment | Cinco Coastal app + native checkout UX | Bites checkout UX (vendor-skinned) | POS-vendor-skinned if completed in-chat; brand-native if redirected — **this fork is the whole decision** | Mixed |
| Speed to market | ~10 weeks (OpenAI app submission + handoff plumbing) | ~6 weeks (Bites onboarding) | Effectively day-zero *for eligible merchants* — the merchant does nothing (which is also the governance problem: see below) | ~12 weeks (both pipelines + measurement design) |
| Franchise-operator acceptability | n/a (Cinco Coastal is 100% corporate) | n/a | n/a here — but for a franchised brand this is the sharpest stance: an auto-opt-in publishes *units*, not the brand, and can list a franchisee before the franchisor has a position | n/a |
| **Weighted score** | **Recommended** | Defer to Phase 2 | **Blocked by POS choice — not electable in Phase 1** | Not recommended |

**Section 1b — The POS-native stance, worked honestly (why it's a strategic finding, not a "no"):**

The POS-native auto-opt-in stance (Square-in-ChatGPT / Square-in-Claude, live 2026-07-01) is the best economics on this matrix — zero build, zero marketplace commission, orders straight into the existing stack. Cinco Coastal **cannot elect it**, because they run Toast, and the pattern is published by the POS platform, not the brand. That is not a footnote; it is three findings the board should hear:

1. **A POS decision is now an agentic-commerce distribution decision.** Toast vs. Square was underwritten as a back-of-house call. It now determines whether the brand gets a zero-cost assistant storefront handed to it. Add "assistant-surface publication roadmap" to the POS vendor scorecard at the next renewal, and ask Toast directly, in writing, what their equivalent is and when.
2. **The stance the brand can't elect still sets the competitive floor.** Square-based local competitors in Cinco Coastal's trade areas were listed in ChatGPT and Claude on 2026-07-01 with no work and no commission. Cinco Coastal is spending ~10 weeks and an OpenAI rev-share to reach a surface a smaller neighbor got for free. That does not change the recommendation (handoff-to-app is still right for a 50-unit loyalty-led brand), but it should change how the CEO reads a slow ramp: the channel is not empty, it is already populated by merchants who didn't have to decide anything.
3. **Auto-opt-in is a governance event, not just an offer.** The defining feature of this stance — the merchant does nothing — means a brand can be published without a decision. Cinco Coastal is corporate-owned, so the blast radius is bounded; a franchised peer could wake up to franchisee units listed in an assistant under brand marks with no franchisor sign-off, no pricing-parity commitment, and no disclosure copy. **Action for Cinco Coastal now, ahead of any Toast equivalent:** pre-write the opt-out/pause procedure and the brand-standards position *before* the POS ships auto-opt-in, so the answer exists in the franchise agreement and the vendor contract rather than being improvised the week it goes live.

**Revised trigger to revisit the POS-native stance:** Toast (or Olo, at the ordering layer) announces an assistant-publication integration. On that announcement, the first question is **not** "do we turn it on" but "is it opt-in or opt-out, and does it complete in-chat or redirect to our checkout with the basket pre-populated?" The redirect fork keeps Punchh attach and brand voice and is the only version that clears the 28% floor; the complete-in-chat fork does not, and should be declined on the same reasoning as Bites end-to-end.

Trigger conditions to revisit Bites end-to-end in Phase 2:
- Bites publishes a measured-ROI deployment case with a Punchh-class loyalty integration disclosed, OR
- A peer brand of similar size publishes 12-week data showing loyalty attach holds within 5 pts of native-app baseline on Bites end-to-end, OR
- OpenAI / Anthropic / Google publishes a loyalty-passthrough API that solves the attach degradation at the protocol level

**Section 2 — Vibe-to-menu mapping (top 5 of the 20 target prompts, full mapping in appendix):**

| Sample guest prompt | Agent extraction | Canonical menu pick | Runner-up | Upsell attach |
|---|---|---|---|---|
| "Light dinner for two under $35 with one pescatarian" | group=2, budget=$35, dietary=pescatarian (1 of 2), daypart=dinner, pickup default | 1× Salmon-Avocado Grain Bowl ($14), 1× Spicy Chicken Tinga Bowl ($13), 1× Cilantro-Lime side ($4) → $31 + tax | 1× Salmon-Avocado, 1× Vegan Coastal Bowl ($13) | Add chips + salsa $4 / Add agua fresca pair $7 → cap at $35 |
| "Coastal-grain bowl that's not too spicy for my picky 7-year-old" | group=1 (kid), spice=mild-only, dietary=age-appropriate | 1× Kid's Coastal-Grain Bowl ($8) with mild salsa selected, no jalapeño | 1× Build-Your-Own with mild only | Add fruit cup $3 / Add kid agua fresca $3 |
| "Healthy lunch I can pick up in 12 minutes" | group=1, daypart=lunch, prep-time-priority, healthy filter | 1× Coastal Greens Bowl ($12) — flagged "<10 min" in canonical feed | 1× Tinga Bowl light | Add agua fresca $3 / Loyalty enroll prompt |
| "Order I can split between two pickup points for a work team of 12" | group=12, multi-pickup, business-account hint | Split-order flow: 6 at nearest store, 6 at second store; cart-builder picks 4× sharing platters + 8× individual bowls | Split 8/4 with mixed protein | Add corporate-bill prompt + chips/salsa platters $8 each → 4 of them |
| "Happy hour drinks pickup at closest store, $50 budget, group of 6" | group=6, daypart=HH (15–18 wkdays — confirm time), budget=$50 | 6× HH margaritas at $7 each = $42 + 2× chips + salsa $8 = $50 (or split to 4 cocktail / 2 NA) — TX + CA + NV units only; AZ 3-unit dry-county HARD HANDOFF to a "this store is non-alcohol" reply | 4× margs + 2× agua fresca for split groups | "Add a guacamole + chips $7 to round it out?" |

Flagged hard-handoff prompts (must NOT proceed to checkout without human review):
- Any anaphylactic allergen mention ("my daughter is anaphylactic to peanuts" → human-allergen-confirmation flow, store callback within 4 min)
- Any minor-purchasing-alcohol signal ("16-year-old at home, can I add a margarita")
- Any catering > 25 covers (routes to the catering team email)
- Any gift-card or balance-inquiry prompt (routes to the loyalty support team)

Agent persona reinforcement: "Interpret guest phrasing; never invent menu items that are not in the canonical source." Drift-detection on this rule is part of the weekly QA review (Section 8).

**Section 3 — Menu structure for agentic construction (gap audit + fixes):**

| Failure mode | Where it would trip Cinco Coastal | Data-layer fix | Owner |
|---|---|---|---|
| Phantom modifier ("add extra jalapeño") | Jalapeño is not a modifier on the Coastal Greens Bowl | Reconcile modifier ontology with Digital Menu Optimization Brief output; explicit modifier whitelist per SKU | Marcus Reyes (digital ops) |
| Dietary contradiction ("vegan" + "ahi tuna") | Vegan bowl SKU exists but ahi is a protein swap on it — flag as conflict | Add dietary-conflict constraint to the modifier engine | Marcus Reyes |
| Price drift ($14.50 in-app vs. $14.99 in-assistant) | Apple/OpenAI surface may cache; canonical feed update latency is 4 hours | Add pre-checkout reconciliation gate; show in-assistant disclaimer until parity confirmed | Engineering + Stripe team |
| Group-size scaling beyond max-cart | "Order for 80" with no cart guard → POS swamp | Cap max-cart at 30 SKUs in-assistant; route catering > 25 covers to catering team | Marcus Reyes |
| AZ dry-county alcohol surfacing | Margarita SKU surfaces in 3 AZ units that don't sell alcohol | Add store-level availability gate at the SKU level; agent must check store-availability before offering | Engineering |
| LTO timing drift | Summer LTO surfaces after 2026-09-01 end-date | LTO window honored in canonical feed; agent must respect daypart + LTO window flags | Marcus Reyes |

**Section 4 — Loyalty and account-linking path (handoff-to-app pattern):**

```
Guest in ChatGPT → "Order me a Salmon-Avocado bowl + agua fresca for pickup"
  ↓
Agent confirms: store, time, modifiers, allergens, price
  ↓
Agent: "I'll send this to your Cinco Coastal app to finish — open the app to confirm and pay."
  ↓
Deep link → Cinco Coastal app (iOS Universal Link or Android App Link)
  ↓
App opens with cart pre-loaded + Punchh OAuth silent refresh (if last-30-day login) OR OTP fallback via SMS/email
  ↓
Guest taps "Confirm + Pay" → Stripe → Punchh earn-event fires automatically
  ↓
Order routed to Toast POS → store confirms
  ↓
Agent in ChatGPT receives push: "Order confirmed at Cinco Coastal — Marina del Rey. Ready at 7:42 PM."
```

Loyalty-preservation patterns evaluated:
- **handoff-to-app (Starbucks-style):** Recommended. Punchh attach holds at native-app baseline.
- **in-assistant link-on-first-order (deferred account creation):** Phase 2 candidate. Attach will degrade unless OpenAI surfaces a passthrough OAuth.
- **pre-linked (guest already signed in via OpenAI ↔ Cinco Coastal integration):** Phase 3 — requires OpenAI to expose a brand-identity passthrough that does not exist as of 2026-Q2.

**Section 5 — Pricing parity and disclosure (90-day commitment):**

- Price parity: in-assistant SKU price = first-party app SKU price, ±$0.00, for 90 days
- Disclosure line (shown above the basket in ChatGPT, italicized):
  > *Prices match the Cinco Coastal app. Pickup is free; delivery (if available at your store) adds a standard fee shown in the app before you pay.*
- Source-of-truth price feed: Cinco Coastal canonical menu feed (Toast → Olo → Deliverect → assistant vendor); 4-hour update SLA
- Drift alert: > $0.05 difference between canonical and assistant price for any SKU → CDO + engineering on-call ping; sync within 30 min; reconciliation report at week-end
- Pricing-logic protection: pricing methodology (HH windows, daypart pricing, regional variance) is contractually protected; assistant vendor sees the *output* prices, not the rules

**Section 6 — Commission-displacement and third-party-delivery governance:**

- Phase 1 stance: Cinco Coastal does NOT allow Bites-class aggregator fulfillment in ChatGPT. UE + DD + Grubhub remain the only third-party fulfillment channels.
- Phase 2 trigger: Bites publishes a measured-ROI case with a Punchh-class loyalty integration disclosed.
- Double-listing prevention: Cinco Coastal claims its own ChatGPT app listing; brand registry filed with OpenAI on launch day. If a guest searches "Cinco Coastal" in ChatGPT, the app result is the brand's own; aggregator listings (when allowed) sit below as fulfillment options, not as the brand surface.
- Franchise opt-in/opt-out: n/a (Cinco Coastal is 100% corporate-owned). For peer brands that are franchised: this section is the highest-friction governance work and benefits from a separate franchisee-operator FAQ.

**Section 7 — Edge-case and fallback copy (12 most-likely scenarios, paste-ready):**

```
1. Item out of stock:
   "The Salmon-Avocado bowl is 86'd at Marina del Rey tonight — the Tinga
   bowl is the closest match. Swap it, or pick a different store?"

2. Store closed:
   "Marina del Rey is closed right now; the next opening is tomorrow at
   11:00 AM. I can schedule pickup then, or check a nearby store — want
   to try El Segundo (open until 9:30 PM)?"

3. Delivery zone mismatch:
   "Your address is outside Cinco Coastal's delivery range. Pickup is
   available at Marina del Rey (12 min away) or El Segundo (18 min) —
   want to switch to pickup?"

4. Allergen conflict (peanut warning):
   "You mentioned a peanut allergy, and our Spicy Chicken Tinga is
   prepared in a kitchen that also handles peanuts. I'll recommend the
   Coastal Greens Bowl instead — please also confirm with the store team
   when you arrive."

5. Allergen conflict (anaphylactic — HARD HANDOFF):
   "I see you mentioned an anaphylactic allergy. For your safety, please
   call Marina del Rey directly at (310) 555-0188 before placing this
   order — they'll review prep details with you."

6. Budget exceeded:
   "Your cart is $4 over your $35 cap — I can remove the agua fresca
   ($3.50) and we'd be at $31.50. Or want to raise the cap?"

7. Modifier unavailable:
   "Avocado is sold out at Marina del Rey tonight — would you like the
   bowl without, or with a free pickled-onion sub?"

8. Age-restricted item (alcohol):
   "Margaritas need an over-21 ID check at pickup. I'll add it to the
   order — please bring a valid ID."

9. AZ dry-county variance:
   "The Tempe store (your nearest) doesn't serve alcohol. I can swap the
   margaritas for our Cucumber-Mint agua fresca, or switch to the
   Scottsdale location (12 min away) which does serve."

10. Catering (> 25 covers — HANDOFF):
    "An order for 40 is best handled by our catering team — they can do
    delivery, family-style trays, and a 24-hour lead time. Want me to
    open the catering page?"

11. Payment declined:
    "Your card was declined. Want to try another card in the Cinco Coastal
    app, or use Apple Pay?"

12. Session timeout / "I don't know how to help":
    "I'm not sure I can help with that one — but the Cinco Coastal team
    can. The Marina del Rey number is (310) 555-0188, open until 9:30 PM."
```

All fallbacks preserve the brand voice (warm, direct, no fake urgency). No "exclusive deal — order now" copy; no countdown timers; no manufactured scarcity.

**Section 8 — Measurement plan (4-metric loop, weekly cadence, CDO-owned):**

| Metric | Target wk 4 | Target wk 12 | Read frequency | Owner |
|---|---|---|---|---|
| In-assistant channel revenue | ≥ $480K | ≥ $1.6M cumulative | Weekly | CDO |
| AOV vs. native-app | Within 5% | Within 3% | Weekly | CMO |
| Loyalty attach on in-assistant orders | ≥ 32% (floor 28%) | ≥ 34% | Weekly | CMO + Punchh team |
| Basket abandonment at handoff | ≤ 22% (new metric) | ≤ 18% | Weekly | CDO + Engineering |
| Same-guest cannibalization vs. native-app | n/a wk 4 | ≤ 14% by wk 12 | Bi-weekly | CMO + Analytics |
| Cannibalization of third-party-delivery (UE + DD + Grubhub) | n/a wk 4 | ≤ 8% by wk 12 | Bi-weekly | CMO + Analytics |

4-week-in go / hold / roll-back gate:
- **Go (continue + expand):** All four core metrics within target.
- **Hold (continue + diagnose):** One metric below target by ≤ 5 pts; pause new feature ship; root-cause analysis.
- **Roll-back (delist):** Loyalty attach below 28% (the hard floor) OR same-guest cannibalization > 18% OR basket abandonment > 30%.

Reporting cadence: weekly flash to CDO; bi-weekly to CEO + CMO; monthly board update; full 12-week recap with go/hold/scale recommendation.

**Section 9 — Launch-day comms pack (5 artifacts):**

- **Public statement (1 paragraph):** "Cinco Coastal guests can now place orders inside ChatGPT — describe a craving, budget, or group, and we'll suggest the closest match from our menu. The order finishes in our Cinco Coastal app, where loyalty points earn just like any other digital order. We built this for guest-convenience and we'll keep refining what's helpful."
- **Loyalty-member email + push (3 lines):** "Order Cinco Coastal in ChatGPT. Points earn the same. Open the app once to link — takes 8 seconds. [Link.]"
- **Franchise-operator FAQ:** n/a (100% corporate)
- **Crew briefing (2 lines, posted at every store + Toast huddle screen):** "Some guests may arrive with orders they placed in ChatGPT. The ticket prints the same way as any app order. Treat them as Cinco Coastal app orders — same warmth, same speed."
- **Press-ready response for trade press:** "We're an early ChatGPT app partner because our guests have asked us to meet them where they're already planning meals. The launch is guest-convenience — our store teams keep doing what they do best."

**Section 10 — Pre-signature contract checklist (legal + digital teams run this before any signature):**

- Data-use rights: per-order data may not be used to train models or shared with other brands; brand reserves the right to audit
- Brand-voice carveouts: vendor may not rewrite our item descriptions; vendor may not generate new item names; the canonical menu feed is the only source
- Exclusivity: no exclusivity to OpenAI; Cinco Coastal reserves the right to ship Gemini, Claude, and Perplexity apps in parallel
- Price-parity: 90-day mutual commitment to honor brand-set prices; no vendor-driven markup
- Delisting cadence: 24-hour delisting SLA on brand request; 4-hour delisting SLA on a reputation-incident trigger
- Incident-escalation SLA: 30-min response, 4-hour resolution target on a Sev-1 issue
- Menu-sync latency SLA: 4-hour update from canonical feed to assistant surface
- Termination-for-reputation clause: if the assistant platform ships a model update that produces materially-embarrassing or unsafe recommendations involving our brand, we may exit with 24-hour notice and recover any prepaid fees pro-rata

---

This brief is paste-ready for the CDO's board pack. Section 1 (decision matrix), Section 8 (measurement plan), and Section 10 (contract checklist) typically copy directly into the board slides; Sections 4–7 typically copy into the engineering + ops launch runbook.
