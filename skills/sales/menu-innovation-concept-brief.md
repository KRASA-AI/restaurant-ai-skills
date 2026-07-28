---
name: "Menu Innovation Concept-Validation Brief"
category: sales
tools: [claude, chatgpt]
difficulty: advanced
time_saved: "~8-15 hr/concept slate/quarter"
version: 1.2
last_eval_score: 9.20  # worked-example extended: downstream autonomous-agent handoff table demonstrates the boundary; output_quality 9->10
---

# 🧪 Menu Innovation Concept-Validation Brief

## Purpose

Produce a decision document that screens a slate of new menu-item, limited-time-offer (LTO), beverage, and naming concepts BEFORE the operator commits kitchen, supply-chain, and marketing dollars to a market test — using AI-assisted predictive-demand research, trend-intelligence signals, and a structured concept-scoring rubric in place of slow, expensive, sequential test kitchens. The brief replaces the "build it, test it in a few stores, hope it travels" cycle with a front-loaded screen that ranks concepts on predicted guest pull, operational feasibility, margin headroom, and brand fit, and hands leadership a ranked go / hold / kill recommendation with the assumptions written down. It covers the predictive-research design (asking panelists to forecast how *other* guests will react rather than only their own intent — the "wisdom-of-crowds" / prediction-market pattern that out-predicts stated-preference surveys), the trend-intelligence layer (social-conversation velocity, competitor-menu movement, ingredient-search momentum), the AI concept-screening pass (generating and stress-testing concept and name variants at scale, then scoring them against historical winners), the feasibility and margin gates, the name-and-claim test, and the staged test-market design for the survivors. Produces a one-slate decision brief — not a "the future of food is AI" think piece.

## When to Use

Run this brief when a culinary or marketing team has a backlog of new-item or LTO ideas and limited test-kitchen and test-market capacity to validate them, when leadership wants a ranked recommendation on which two or three of a dozen concepts to advance this quarter, when a competitor has just shipped a category-defining LTO and the operator needs a fast read on whether to fast-follow or hold, when a brand is standing up an internal innovation database and wants a repeatable scoring methodology rather than ad-hoc taste-panel votes, when a beverage or dessert program is being expanded and the team needs to know which flavor and format concepts to prioritize, or when a name or claim for an already-greenlit item needs a predictive read before menu-board printing and marketing spend lock.

Scope is pre-test concept screening and prioritization for an operator's own innovation pipeline. For pricing and contribution-margin moves on items that already exist, use the Dynamic Menu Pricing Advisor. For writing the menu copy once an item is greenlit, use the Menu Description Writer. For macro-trend menu-architecture strategy (the GLP-1 / protein-forward shift), use the GLP-1 Menu Strategy Brief. For making a shipped item legible to AI ordering and discovery surfaces, use the Agentic Ordering App Readiness Brief and the AI Search Visibility Playbook. For the supplier-side sourcing review on a new component a surviving concept requires, use the Supplier Negotiation Brief. For demand sizing on a confirmed LTO once it is in the launch calendar, use the Demand Forecast Briefing. These skills together form the concept-to-launch coverage map.

A boundary worth drawing explicitly in 2026: a new class of *autonomous* AI menu-and-promotion agents has reached commercial scale (e.g., Deliverect's "AI Agents," launched 2026-04-09, which autonomously designed, deployed, and optimized a KFC Netherlands promotion end-to-end and reported a 118% same-day sales lift with no human in the loop). Those agents operate *downstream* of this brief: they continuously rewrite live digital-menu copy, pricing, and promo mechanics on items and concepts that have *already* been chosen. This brief is the *upstream, human-gated* decision — which concepts earn a kitchen, supply-chain, and marketing commitment in the first place. The two are complements, not substitutes: an autonomous agent should only be pointed at a concept that cleared this brief's feasibility, margin, and brand-fit gates, and the brief's predicted-vs.-actual calibration log is exactly the governance record that tells leadership whether a given concept is stable enough to hand to an always-on agent (and where a human must stay in the loop — claims, allergens, brand-voice, and forbidden-zone guardrails an autonomous optimizer must never cross).

## Required Input

Provide the following:

1. **Concept slate** — Every concept under consideration this cycle, each with a one-line description, the daypart and category it targets (breakfast handheld, lunch entrée, snack, dessert, cold beverage, hot beverage, LTO seasonal, permanent-menu candidate), the rough build (components and prep route), and the stage it is at (napkin idea, recipe drafted, test-kitchen sample made). A slate of 8–20 concepts is the typical screen size; fewer than 6 rarely justifies the structured pass.
2. **Brand profile and innovation guardrails** — Concept (QSR, fast-casual, coffee, pizza, bowls, full-service, breakfast, smoothie, full-bar), location count, owned vs. franchised mix, average ticket, daypart mix, and the brand's stated innovation thesis (e.g., "crave-forward indulgence," "protein-forward," "globally inspired," "value-tier traffic driver"). Include the forbidden-zone list — ingredients, claims, formats, or price points the brand will not pursue regardless of predicted pull.
3. **Historical winner/loser library** — The last 12–24 LTOs or new items the brand has launched, each with what actually happened: attach rate, incremental-vs.-cannibalization read, repeat rate, operational drag (added prep seconds, new SKUs, line complaints), and whether it was retained, retired, or made permanent. This is the calibration set the AI screen scores new concepts against — without it the screen is ungrounded.
4. **Predictive-research access** — Whether the brand can field a predictive-demand panel (an internal loyalty panel, a commissioned consumer panel, or a third-party predictive-research vendor), the panel size and composition available, and the turnaround the team needs. Note whether the brand can run the prediction-market question form ("what share of guests *like you* will order this?") versus only the stated-intent form ("would *you* order this?").
5. **Trend-intelligence signals** — Any subscription or data the brand has to trend-intelligence platforms (social-conversation velocity, menu-penetration trackers, ingredient-search momentum, flavor-trend forecasts), plus the team's own read on what is rising and falling in the category. Flag which signals are vendor-supplied vs. internally observed so the brief can weight them.
6. **Feasibility constraints** — Kitchen capacity (can the line execute the build at peak without a new station or a throughput hit?), equipment limits, supply-chain reality on any new component (case-pack size, lead time, single-source risk, cost volatility), shelf-life and hold tolerance, allergen and cross-contact implications, and franchise-system rollout friction (uniformity rules, equipment mandates, training load).
7. **Margin and price context** — Target contribution margin and price band for each category, current food-cost pressure on candidate components, and the value-tier vs. premium-tier slot each concept is competing for. Include the brand's rule on whether an LTO is allowed to run thin-margin as a traffic driver or must clear a margin floor.
8. **Name and claim candidates** — For concepts far enough along, the working names and any health, provenance, or flavor claims under consideration, plus the brand's claim-compliance floor (no unsubstantiated health or weight claims; provenance claims must be defensible; allergen and "made-with" claims must match the actual build).
9. **Decision context** — How many concepts leadership intends to advance this cycle, the test-market budget and store count available, the calendar lock dates (menu-board print, marketing creative, supply commitment), and who signs off (CMO, VP Culinary, COO, franchise advisory council).
10. **Measurement commitments** — What the brief must let leadership track after launch so the predictive screen can be back-tested: predicted rank vs. actual performance for each advanced concept, so the scoring model improves every cycle. The single most valuable output of this skill over time is a calibrated, brand-specific predictive screen — that only happens if predicted-vs.-actual is logged.

## Instructions

You are a menu-innovation strategist who has run concept-validation pipelines for multi-unit operators and who understands why stated-intent surveys over-predict (social-desirability bias, no opportunity cost, no competitive set) and why prediction-market / "forecast-the-crowd" question forms and trend-velocity signals predict actual menu pull better. Your job is to turn a messy concept slate into a ranked, defensible go / hold / kill recommendation with the assumptions exposed — not to declare winners by taste-panel applause.

**Before you start:**
- Load `config.yml` for brand voice, forbidden-zone list, margin floors, claim-compliance rules, and franchise-system constraints
- Reference `knowledge-base/terminology/` for category vocabulary, claim-compliance language, and the brand's innovation-thesis phrasing
- Reference the historical winner/loser library as the calibration set — every concept score must be expressed relative to a named historical comparison ("scores like [retained winner]" / "scores like [retired miss]"), never on an absolute scale the team cannot interpret
- Pull current trend signals and competitor-menu movement before scoring — a stale trend read mis-ranks the slate
- Treat predictive-research output as directional, not precise: report predicted pull as a band with a confidence note, never a single point estimate the team will over-trust

**Process:**

1. **Slate intake and normalization** — Restate every concept in one consistent format: name, daypart, category, target slot (traffic-driver vs. margin-builder vs. brand-halo), build summary, and stage. Group near-duplicates and flag concepts that violate the forbidden-zone list — kill those immediately and say why, so leadership does not re-litigate them. Output a clean, numbered slate table that the rest of the brief scores against.

2. **Predictive-demand screen** — For each surviving concept, design the predictive-research question form and report the expected read. Prefer the prediction-market / "forecast-the-crowd" form (ask panelists to estimate the share of guests like them who would order the concept, and reward accuracy) over raw stated intent, because forecast-the-crowd consistently out-predicts "would you buy this." Where only stated-intent data is available, discount it explicitly for over-prediction bias. Report each concept's predicted pull as a band (e.g., "moderate-high, comparable to [named historical winner]") with the panel basis and a confidence note. Never present a single decimal that implies false precision.

3. **Trend-intelligence overlay** — Layer the trend signals on top of the predictive read: is the concept's core ingredient, flavor, or format rising, flat, or fading in social-conversation velocity, competitor-menu penetration, and ingredient-search momentum? A concept with moderate predicted pull but steep positive trend velocity may outrank a concept with higher current pull on a fading trend. Flag any concept riding a spike that may collapse before the launch calendar lock — trend-chasing LTOs that miss the window are a recurring miss pattern. Distinguish durable shifts from fads in the recommendation.

4. **AI concept-and-name expansion** — For the top concepts, use AI to generate and stress-test variants at scale: alternative builds, format variations (handheld vs. bowl vs. shareable), flavor-system tweaks, and 8–15 candidate names per concept. Score the variants against the historical winner library — which variant most resembles past retained winners on craveability language, format, and price slot. This is where AI screening earns its keep: it explores the variant space in minutes that a test kitchen would explore in months. Hand the team the two or three strongest variants per surviving concept, not the raw list.

5. **Feasibility and margin gates** — Run each surviving concept through the hard gates: kitchen-execution feasibility at peak (added prep seconds, new station, throughput risk), supply-chain reality on any new component (lead time, case-pack fit, single-source and cost-volatility risk), shelf-life and hold tolerance, allergen and cross-contact load, and franchise rollout friction. Then the margin gate: contribution margin at the target price, against the brand's floor and the traffic-driver exception. A concept with top predicted pull that fails the feasibility or margin gate is a hold, not a go — say exactly what would have to change (a reformulation, a second supplier, a price move, an equipment add) to move it to go, and hand any sourcing question to the Supplier Negotiation Brief.

6. **Name-and-claim test** — For greenlit-track concepts, test the working name and any claim. Score names on memorability, search-and-voice-order legibility (will a guest or an AI ordering agent parse it?), trademark and confusion risk, and brand-voice fit. Score claims against the compliance floor: no unsubstantiated health or weight claims, provenance claims must be defensible against the actual build, and "made-with / contains" language must match the recipe. Flag any name or claim that creates a legal or AI-discoverability problem and supply a compliant alternative.

7. **Ranked recommendation and staged test design** — Produce the ranked go / hold / kill table: each concept with its predicted-pull band, trend direction, feasibility verdict, margin verdict, recommended name/variant, and a one-line rationale tied to a named historical comparison. Recommend exactly the number of concepts leadership said they will advance — no more — and for each advanced concept, design the staged test: store count and market selection (control-matched, daypart-representative), the run length, the success thresholds (attach rate, incrementality, repeat, operational drag) the test must clear to go wider, and the kill thresholds that stop it. Close with the predicted-vs.-actual logging plan so this cycle's predictions calibrate next cycle's screen. For any advanced concept the operator intends to hand to an autonomous menu/promo agent post-launch (the Deliverect-class downstream layer noted in *When to Use*), state the guardrails the agent inherits from this brief and must not cross — the margin floor, the claim-compliance and allergen rules, the brand-voice and forbidden-zone list — and name the human owner who reviews the agent's autonomous moves on a set cadence; an autonomous optimizer earns a longer leash only after the predicted-vs.-actual log shows the concept performing in-band.

## Example Output

Below is an abbreviated example. A full brief runs five to nine pages.

# Menu Innovation Concept-Validation Brief — Brasa & Bahia Q3 2026 LTO Slate

**Operator:** Brasa & Bahia — 4-unit Atlanta Latin-Caribbean fast-casual, $9.4M consolidated AUV, operator-owned. Innovation thesis: "globally inspired, crave-forward, protein-forward where it fits." Reviewed by: Maria Restrepo (Area-GM), VP Culinary, owner. Decision: advance **2** concepts to a 2-store, 6-week test ahead of the fall LTO window.

## Slate Intake (11 concepts → 9 after forbidden-zone screen)

Two concepts killed at intake: a caipirinha-based dessert (alcohol-policy hard-block, per house standard) and a shellfish-heavy bowl (cross-contact load exceeds the line's allergen guardrail). Nine advance to scoring. (Full numbered table in the appendix.)

## Predictive-Demand Screen (forecast-the-crowd panel, n≈400 loyalty)

| # | Concept | Predicted pull (band) | Historical comp |
|---|---------|----------------------|-----------------|
| 1 | Guava-glazed chicken handheld | High | scores like the retained 2025 mojo-pork sandwich |
| 2 | Plantain-crust breakfast bowl | Moderate-high | scores like the made-permanent 2024 desayuno bowl |
| 3 | Passionfruit cold-foam refresher | Moderate-high | scores like the retained 2025 hibiscus cooler |
| 4 | Birria-style empanada | Moderate (fading trend, see §3) | scores like the retired 2024 al-pastor taco LTO |
| ... | ... | ... | ... |

Stated-intent numbers ran ~12–18 pts higher across the board and were discounted for over-prediction bias; the forecast-the-crowd form is the basis above.

## Trend Overlay

Guava and passionfruit both show durable positive velocity in beverage and dessert conversation; plantain-crust is rising off a low base. Birria velocity has rolled over from its 2024–25 peak — concept #4 is a fade risk that may miss the fall lock and is held on that basis despite an acceptable predicted pull.

## AI Variant + Name Expansion (top 3 concepts)

Concept #1 advanced as a handheld over a platter variant (handhelds index higher on the brand's retained-winner set and travel better to drive-thru-equivalent digital pickup). Name screen: "Guava Brasa Melt" leads on memorability + voice-order legibility; rejected "Goiabada Smash" (provenance-correct but low search legibility).

## Feasibility + Margin Gates

| Concept | Feasibility | Margin @ target price | Verdict |
|---------|-------------|----------------------|---------|
| Guava Brasa Melt | Pass (uses existing grilled-chicken station) | 68% — clears floor | **GO** |
| Plantain breakfast bowl | Pass | 64% — clears floor | **GO** |
| Passionfruit cold foam | Hold — new cold-foam SKU, single supplier | 71% if sourced | HOLD → Supplier Negotiation Brief |

## Ranked Recommendation

**Advance:** (1) Guava Brasa Melt, (2) Plantain breakfast bowl. **Hold:** passionfruit cold foam (pending second cold-foam supplier), birria empanada (trend fade). **Kill:** the two forbidden-zone concepts + three low-pull/feasibility-fail concepts (appendix).

## Staged Test Design

Buckhead + Decatur (control-matched on AUV and daypart mix), 6 weeks. Go-wider thresholds: ≥6% attach, ≥60% incremental (not cannibalizing the mojo-pork sandwich), ≥25% 4-week repeat, ≤8 added prep seconds at peak. Kill thresholds: <3% attach or >20% line-complaint rate. **Predicted-vs.-actual log** opened for all 9 scored concepts so Q4's screen calibrates against this slate.

## Downstream Autonomous-Agent Handoff (guardrails inherited from this brief)

Brasa & Bahia runs a Deliverect-class autonomous menu/promo agent on its digital channels. Per the *When to Use* boundary, that agent is a downstream execution layer — it may only optimize concepts that cleared this brief's gates, and it inherits the guardrails below. Neither advanced concept is handed to the agent yet: both are still in test and have no predicted-vs.-actual read, so a human owns every change during the 6-week window. The table is written now so the handoff rules are settled before the test closes.

| Advanced concept | Agent may autonomously adjust | Agent may NEVER cross (hard guardrails) | Handoff trigger | Human owner |
|---|---|---|---|---|
| Guava Brasa Melt | menu-tile placement, photo/hero rotation, price within the 66–70% CM band, day-part promo timing, bundle pairing | drop below the 66% margin floor; alter the "guava-glazed / grilled chicken" build or its allergen line; add any health/provenance claim; touch the forbidden-zone list | 3 consecutive weeks of actual pull in-band vs. predicted (High), CM ≥ floor, ≤8 prep-sec confirmed at scale | VP Culinary |
| Plantain breakfast bowl | tile placement, breakfast-daypart promo timing, price within the 62–66% CM band, cross-sell pairing | drop below the 62% margin floor; change the plantain-crust build or "made-with" language; extend past the breakfast daypart without human sign-off; touch the forbidden-zone list | same in-band calibration rule; requires 4-week repeat ≥25% held at scale | VP Culinary |

Claims, allergens, brand-voice, and the forbidden-zone list stay human-reviewed for both — an autonomous optimizer earns a longer leash on placement, timing, and in-band pricing only after the predicted-vs.-actual log shows the concept performing in-band, and never on claims or allergens. The predicted-vs.-actual log is the governance record that authorizes each leash extension.

## Cross-References

- **Dynamic Menu Pricing Advisor** — sets the contribution-margin tier and price band each concept is scored against, and prices the survivors at launch
- **Menu Description Writer** — writes the menu-board and app copy once a concept is greenlit
- **Supplier Negotiation Brief** — sources any new component a held concept needs to move to go (the passionfruit cold-foam second-supplier question above)
- **Demand Forecast Briefing** — sizes covers and prep for the advanced LTOs once they hit the launch calendar
- **GLP-1 Menu Strategy Brief** — upstream macro-trend architecture when the slate is being built against a protein-forward thesis
- **Agentic Ordering App Readiness Brief / AI Search Visibility Playbook** — make the shipped winner legible to AI ordering and discovery surfaces

## Knowledge-Base References

- `knowledge-base/terminology/` — category vocabulary, claim-compliance language, innovation-thesis phrasing
- `knowledge-base/best-practices/` — concept-screening rubric, predicted-vs.-actual calibration log format, historical winner/loser library template
