---
name: "GLP-1 Menu Strategy Brief"
category: sales
tools: [claude, chatgpt]
difficulty: intermediate
time_saved: "~6-10 hr/brand/quarter"
version: 1.0
last_eval_score: null
---

# 💪 GLP-1 Menu Strategy Brief

## Purpose

Produce a brand-level strategic brief for adapting menu architecture, item-level macronutrient labeling, kiosk and digital-channel callouts, and AI-discoverability for the GLP-1 era — the structural shift toward smaller-portion, high-protein, lower-carb dining triggered by mass GLP-1 (Ozempic, Wegovy, Mounjaro, Zepbound) adoption. Covers the menu-section decision (build a dedicated GLP-1 / Protein-Forward section vs. embed callouts on existing items vs. both), macronutrient label design and FDA / FTC compliance, the kiosk and app badge system, the smaller-portion / half-size architecture, the cross-utilization map that keeps a new section affordable, the AI-feed adjustments that make the brand legible to Menu-Order-AI and in-assistant ordering apps, the test-market and rollout plan, the four-metric measurement plan, and the franchise-system communication pack. Produces a one-brand decision document — not a "GLP-1 is changing food" think piece.

## When to Use

Run this brief when a brand is planning a menu refresh and the leadership team has flagged GLP-1 / protein-forward dining as a strategic input, when a competitor has just launched a high-protein or "Good Fit"–style menu and the operator wants a position paper by end of week, when a quarterly menu review is surfacing under-performance on indulgent-only items or on shareable-format heavy entrées, when a CMO is deciding whether to add macronutrient (gram of protein, net carb, calorie) badges to kiosks and the native app, or when a digital lead is responding to the rise of Menu-Order-AI and similar consumer apps that score restaurant menus on GLP-1 fit and may surface or suppress the brand independent of its own marketing.

Scope is brand-level menu architecture and macronutrient labeling strategy. For per-item description copy, use the Menu Description Writer. For per-item pricing, contribution margin, and menu-engineering matrix moves, use the Dynamic Menu Pricing Advisor. For making the resulting menu legible to ChatGPT, Gemini, Claude, or Perplexity ordering apps, use the Agentic Ordering App Readiness Brief. For making it legible to AI answer engines and discovery, use the AI Search Visibility Playbook. For supplier-side cost negotiations triggered by a protein-heavy reformulation, use the Supplier Negotiation Brief. These six skills together form the complete coverage map for a GLP-1-era menu refresh.

## Required Input

Provide the following:

1. **Brand profile** — Concept (QSR, fast-casual, coffee, pizza, bowls, full-service, breakfast, smoothie, full-bar), location count, owned vs. franchised mix, market footprint, daypart mix, average ticket, and current penetration of any "healthy," "lighter," "lite," or "wellness" sub-menu
2. **Current menu and macros** — Every item with selling price, contribution margin, sales mix volume over the last 8 weeks, and macronutrient values per as-served portion (calories, total protein in grams, total fat in grams, saturated fat in grams, total carbs in grams, sugar in grams, fiber in grams, sodium in milligrams). Flag items where the macros are estimates vs. lab-verified, and flag any items that are cooked-to-order and therefore vary by build
3. **Guest segmentation data** — Loyalty data (if available) on the share of guests reporting GLP-1 use, protein-forward intent, low-carb intent, smaller-portion preference, or weight-management goals; survey or panel data the brand has commissioned in the last 6 months; any internal sales-mix shift signals (lighter-tier item growth, half-portion order growth, salad attach-rate changes)
4. **Daypart and channel context** — Which dayparts are softening (often dinner shareables, indulgent desserts) and which are growing (often breakfast protein, mid-afternoon protein snack); which channels (drive-thru, kiosk, native app, third-party delivery, in-assistant ordering) over- and under-index for GLP-1-leaning guests
5. **Channel surface inventory** — Where macronutrient information can or must be displayed (kiosk badges, native app filters, web menu, third-party delivery storefront, in-store menu board, printed menu, drive-thru pre-confirmation screen, receipt) and which are gated by vendor capability today (e.g., a third-party delivery platform may not support a custom macro badge in 2026)
6. **Regulatory and franchise constraints** — FDA chain menu-labeling rule applicability (≥20 locations doing business under the same name and selling substantially similar standardized items), state-level menu-labeling overlays, alcohol service rules, franchise-system menu uniformity rules, and any class-action or AG settlement language constraining health claims; any third-party certification programs the brand is enrolled in (Whole Grain Council, Plant Based Foods Association, NSF Certified Gluten-Free, Whole30 Approved)
7. **Competitive and category benchmark** — Which peer brands have shipped a Protein Packed / Good Fit / High-Protein / GLP-1-Friendly section or a macronutrient-callout program; their callout language, badge design, item count, daypart coverage, and any public claims on traffic or attach lift; whether Menu-Order-AI, ChatGPT-app aggregators, or third-party delivery wellness filters are surfacing or suppressing the brand
8. **Operational constraints** — Smallbatch-prep capacity (can the kitchen run a half-portion entrée without doubling labor?), protein-supply elasticity (chicken vs. beef vs. plant-based vs. dairy), shrink-and-waste tolerance for new SKUs, kiosk and POS configuration capacity (can the kiosk render a custom badge per item without a vendor release?), and any equipment-driven limits (smaller-portion bowl SKUs, half-size containers)
9. **Brand-voice and disclaimer posture** — Whether the brand will use the term "GLP-1" explicitly, lean on neutral framing ("Protein-Forward," "Good Fit," "Higher-Protein," "Smaller-Portion"), or avoid the topic by surface area; whether the brand will publish a per-item macro card with a "Talk to your doctor" disclaimer or only display per-item gram counts; the brand's house position on weight-loss claims (the brand should not make any direct weight-loss claim — both an FTC and a litigation risk)
10. **Measurement commitments** — What the brand will report to leadership at 4 weeks and 12 weeks: section penetration (% of orders that include at least one Protein-Forward item), incremental-vs.-cannibalization split (lift to total transactions vs. internal substitution), daypart impact (breakfast vs. dinner), guest-retention impact on loyalty users in the GLP-1 segment, gross margin on the new section, and the operational cost per new SKU (training, prep time, waste, kiosk configuration)

## Instructions

You are a menu-strategy consultant who has shipped chain-wide menu refreshes against macro-trend shifts (low-carb, gluten-free, plant-based, clean-label, and now GLP-1) and who understands how chain menu-labeling rules, FTC advertising guidance, kiosk and app surface mechanics, and AI-feed legibility interact. Your job is to produce a concrete one-brand brief — what to add, what to retire, what to relabel, in what order, with what disclaimers, on which surfaces, and with what KPIs.

**Before you start:**
- Load `config.yml` for brand voice, forbidden claims, daypart definitions, and franchise-system rules
- Reference `knowledge-base/terminology/` for macronutrient phrasing, FDA chain menu-labeling vocabulary (standard menu item, reasonably available, succinct statement), and the brand's preferred way of referring to GLP-1 dining without making a weight-loss claim
- Reuse the Menu Description Writer output for any item-level copy that ships with the new section
- Reuse the Dynamic Menu Pricing Advisor output for the contribution-margin tier on each new or relabeled item — Puzzles and high-margin Stars carry the section, low-margin Plowhorses and Dogs do not
- Reuse the Supplier Negotiation Brief output if a protein-heavy reformulation is being modeled on the input side
- Pull the current FDA chain menu-labeling rule, FTC health-claim guidance, and any state overlays before writing the disclosure step — the legal floor moves and a 2024 brief is not 2026 valid

**Process:**

1. **Section-architecture decision** — Recommend one of three patterns for the first 12 months: (a) a dedicated "Protein-Forward" / "Good Fit" / "High-Protein" section on the canonical menu, kiosk, and app — used by Shake Shack, Chipotle, El Pollo Loco; (b) embedded per-item callouts on existing items without a dedicated section — used by McDonald's via 17 protein badges across breakfast, lunch, and dinner; (c) both — a dedicated section plus callouts on legacy items that already qualify. Score each option against guest legibility (can a GLP-1 guest find the qualifying items in under 10 seconds on a kiosk?), brand-voice coherence (does a "Good Fit" section dilute the indulgence story for non-GLP-1 guests?), operational lift (a new section adds SKUs and prep complexity; callouts on existing items don't), franchise acceptability (uniformity rules, signage cost), and AI-feed legibility (does Menu-Order-AI or a ChatGPT app pick up callouts as well as a section header?). Prescribe one pattern as the launch shape and the trigger conditions that would force a revisit.

2. **Item shortlist for the launch section or callouts** — For each candidate item, list macronutrients per as-served portion, contribution margin, current sales mix volume, and the qualification rule the brand will enforce — typical thresholds in the category as of 2026 are 15g+ protein for a callout (McDonald's threshold), 25g+ protein for a "High-Protein" qualifier (Chipotle's High Protein Menu), and 20g+ protein and ≤30g net carbs for a "GLP-1 Friendly" qualifier (closer to Shake Shack Good Fit and Smoothie King's GLP-1 menu). Include at least one item per daypart the brand operates. For full-service or fast-casual brands, include a smaller-portion / half-size variant where the existing entrée portion runs over 600 calories or 90 grams of carbs. Cap the launch section at 8–12 items — a section any larger blurs the legibility benefit.

3. **Macronutrient label design and disclosure** — Specify the per-item label format the brand will display on each surface: the kiosk badge (icon + "23g Protein"), the app filter (toggleable filters: "Protein 20g+," "Net Carbs ≤30g," "Calories ≤500," "Smaller Portion"), the web menu callout (badge + macro card on hover or tap), the third-party-delivery storefront (whatever the platform supports — usually a tag or a description-line callout), the printed menu (per-item gram count beside the description if FDA chain menu-labeling applies; otherwise discretionary), and the drive-thru pre-confirmation screen (callout where the platform supports it, otherwise none). Spell out the FDA chain menu-labeling compliance posture: calories on standard menu items at the point of ordering, written nutrition information available on request (succinct statement), and consistency across surfaces. Spell out the FTC posture: no direct weight-loss claim ("Lose weight with our High-Protein menu" — never), no medical claim ("Recommended for GLP-1 users" — never; "Higher-protein options to fit a protein-forward eating pattern" — acceptable), and a "Talk to your doctor or registered dietitian about what fits your eating plan" footer on any page that names GLP-1 or weight management. Provide the exact label microcopy the brand will use across surfaces — the same macro text appears on the kiosk, app, web, and third-party-delivery feed, by policy, to avoid drift.

4. **Smaller-portion and half-size architecture** — Recommend the half-size or smaller-portion architecture if and only if the kitchen can produce the smaller portion without more than a 10% labor lift per item. Define the half-size SKU rules: the price ratio (typical 60–70% of the full portion — half-size is not half-priced and the brand should not pretend it is), the build differences (same components, smaller scoop / smaller bun / smaller bowl — never a different recipe, which doubles training), the modifier compatibility (half-size accepts the same modifiers as the full size unless capacity-limited), and the kiosk and app placement (a "Smaller Portion" toggle inside the entrée detail page rather than a duplicate SKU, where the POS supports a size variant). Reference Olive Garden's 2026 smaller-portions section and Starbucks's small-format protein pockets as live precedents — both are smaller-build variants of existing items, not net-new recipes.

5. **Cross-utilization map for protein-supply efficiency** — Build the cross-utilization map across the launch section: which proteins, dairies, and fiber-dense components recur across items so the brand is not buying eight new SKUs for a 10-item section. Aim for 60% component overlap with the legacy menu — the protein loaded into the new section should be the protein the kitchen already preps. Where a new component is unavoidable (Greek yogurt for a parfait, edamame for a bowl, cottage cheese for a breakfast bowl), score it on case-pack size, par-level fit, shrink risk, and supplier elasticity, and hand the top three new components off to the Supplier Negotiation Brief for sourcing review. Spell out the par-level adjustments at the line and the waste-management plan for the first 60 days — the launch section will over- or under-perform forecast and the kitchen needs a written rule for both.

6. **AI-feed and discoverability tuning** — Make the new menu legible to Menu-Order-AI, ChatGPT-app aggregators, the brand's own in-assistant app (if shipped), in-app dietary filters, and third-party delivery wellness filters: include the macronutrient values in the canonical menu feed (HTML, Schema.org `nutrition` properties, OpenAPI feed for in-assistant apps), the dietary tags ("high-protein," "lower-carb," "gluten-free" where applicable), the daypart availability, and the section name as a queryable tag. Recommend that the brand ship a short FAQ page on the marketing site that answers the queries Menu-Order-AI and the ChatGPT apps cite most ("Which menu items have 20g+ of protein?" "What's on the Good Fit / Protein-Forward menu?" "Does the brand have GLP-1-friendly options?") and a structured menu page Schema.org `MenuSection` and `MenuItem` markup that lets answer engines extract the section without hallucinating. Cross-reference the AI Search Visibility Playbook for the broader discovery layer and the Agentic Ordering App Readiness Brief for the in-assistant ordering layer; this step focuses on the data-feed shape only.

7. **Test-market and rollout plan** — Recommend a four-phase rollout: Phase 1 (4 weeks) — soft launch in 5–10 stores in 2 markets with a kiosk and app callout, no marketing spend, instrumentation only. Phase 2 (8 weeks) — 50–100 stores in 4 markets with social and email support; A/B the section header naming ("Protein-Forward" vs. "High-Protein" vs. "Good Fit"); A/B the macronutrient surface (badge only vs. badge + filter vs. badge + filter + macro card). Phase 3 (12 weeks) — full system rollout once the Phase 2 KPI gates are met (incremental-vs.-cannibalization split is incremental-positive, gross margin on the new section is at or above the menu average, no operational complaints from the line). Phase 4 (ongoing) — quarterly refresh cadence, including LTO additions, supplier swaps, and macro-card updates. Spell out the kill-switch criteria: a 12-week section penetration below 4% of orders, a measurable cannibalization signal on indulgent items that exceeds the lift on the new section, or a supplier-side cost shock that flips the section's gross margin below the menu average.

8. **Franchise-system communication pack** — Draft the franchise-operator FAQ: why the brand is shipping the section, what the franchisee must do (kiosk and POS reconfiguration, line training, signage refresh), what the franchisee can opt out of (only with explicit corporate approval — uniformity rules apply), the menu-labeling compliance burden (consistent across stores and channels, FDA succinct statement, written nutrition information available on request), and the FAQ for line crew ("Is this menu for GLP-1 users?" "Can I tell a guest a dish will help them lose weight?" — never). Include a 5-question franchise-operator Q&A and a 5-question crew Q&A that line GMs can use in pre-shift huddles. Reference the Health Inspection Prep skill where the macronutrient-claim accuracy ties into the regulatory inspection scope.

9. **Four-metric measurement plan** — At 4 weeks and 12 weeks, report: (a) **Section Penetration** — % of orders that include at least one item from the new section or with the new callout, daypart-split. (b) **Incremental-vs.-Cannibalization Split** — using a difference-in-differences design across test and control markets, the lift to total transactions and to total revenue net of internal substitution. (c) **Gross Margin Index** — gross margin on the new section vs. the menu average, post supplier and labor adjustments. (d) **Guest-Retention Lift in the GLP-1 Segment** — for loyalty guests who self-identify as GLP-1, protein-forward, or smaller-portion, the 12-week repeat-rate delta vs. matched non-segment guests. Spell out the threshold each metric must clear to justify Phase 3 system rollout. Hand the measurement plan off to the brand's analytics team with the exact event taxonomy (item-level kiosk_badge_view, item-level macro_filter_apply, section-level section_landing_view, basket-level glp1_section_attach) and the data-warehouse query template.

10. **Communication and launch pack** — Draft the launch communication: a one-page guest-facing landing page for the marketing site, a one-line kiosk and app banner ("New: Protein-Forward Menu — find your fit"), a three-line email to loyalty guests (no weight-loss claim, no medical claim, "Talk to your doctor" footer), an Instagram and TikTok caption set (8–12 captions across the launch section items, reuse the Social Media Post Generator output), a press-kit Q&A for the trade press (no weight-loss claim, no medical claim, focus on the brand's craft and the protein-forward eating pattern), a franchise-system internal memo, and a 60-second crew training video script. Every artifact must pass a single compliance check: no weight-loss claim, no medical claim, no implied endorsement of GLP-1 medication, and a "Talk to your doctor" footer on any artifact that names GLP-1 or weight management. Where the brand opts out of naming GLP-1 entirely, all of the same artifacts apply with the GLP-1 mention removed.

11. **Risk register and decision log** — Document the top six risks: (a) FTC enforcement on health claims (highest risk; clear language and disclaimer policy is the primary control); (b) state AG menu-labeling enforcement; (c) macronutrient drift between kiosk, app, web, third-party delivery, and in-assistant feeds; (d) guest backlash (the indulgent-only guest who reads a "Good Fit" header as a brand identity shift — managed by the section / callout decision in Step 1); (e) supplier-side cost shock on a protein-heavy reformulation (managed by the cross-utilization map in Step 5 and a Supplier Negotiation Brief handoff); (f) AI-feed legibility regression (a Menu-Order-AI score change after launch — managed by Step 6's structured feed and the AI Search Visibility Playbook). For each risk, name the owner, the trigger that escalates the risk, and the mitigation already in place. Append a one-page decision log of every choice the brief locked in and the data that justified each — so a future Q3 refresh can reopen the same decisions with the same evidence base.

12. **Final consistency check** — Before delivery, verify: every item has macronutrient values per as-served portion that match across kiosk, app, web, third-party delivery, and in-assistant feeds; every claim on every surface is literally true and not a weight-loss or medical claim; the FDA succinct statement is rendered where chain menu-labeling applies; the FTC posture passes a "would I defend this in a 30-second deposition" read; the smaller-portion variants do not under-cut the full-size on margin without a documented reason; the cross-utilization map covers at least 60% of new-section components; and the four-metric measurement plan has named owners and a data-warehouse query template. Flag any unresolved gap and recommend whether the brand should ship anyway with a 60-day-revisit note or hold the launch.

**Output requirements:**
- Section-architecture decision brief (one page) with the recommended pattern and trigger conditions for revisit
- Item shortlist table (8–12 items) with macros, margin, sales mix, qualification rule, and label microcopy per surface
- Macronutrient label design pack — per-surface badge / filter / card / footer specifications and the exact compliance microcopy
- Smaller-portion / half-size architecture spec, including price ratio, build difference, modifier compatibility, and POS configuration notes
- Cross-utilization map across the launch section, with new SKU shortlist for Supplier Negotiation Brief handoff
- AI-feed and discoverability spec: structured menu markup, FAQ topics, and a Menu-Order-AI / ChatGPT-app legibility checklist
- Test-market and rollout plan (4 phases) with named KPI gates and kill-switch criteria
- Franchise-operator FAQ and crew Q&A pack
- Four-metric measurement plan with event taxonomy, data-warehouse query template, and the threshold each metric must clear
- Launch communication pack: landing page, kiosk and app banner, loyalty email, social captions, press-kit Q&A, franchise memo, and 60-second crew training script — every artifact passes the FTC and FDA compliance check
- Risk register (six risks) with owner, trigger, and mitigation per risk
- Decision log of every choice the brief locked in
- Saved to `outputs/` if the user confirms

## Example Output

```markdown
# GLP-1 Menu Strategy Brief — [Brand Name] Q2 2026

## Section-Architecture Decision
**Recommended pattern:** Embedded per-item callouts (McDonald's pattern) for Phase 1, with a dedicated "Protein-Forward Picks" filter on the kiosk and app.
**Rationale:** [Brand Name] does not have an "indulgence vs. wellness" voice split; a dedicated section header would dilute the core craft story. Embedded callouts give a GLP-1 guest the legibility they need without forcing a section commitment.
**Trigger to revisit:** if Phase 2 callout-only attach rate stalls below 6% of orders, A/B a dedicated section header in 25 stores in Q4 2026.

## Launch Item Shortlist (12 items)
| Item | Daypart | Cal | Protein g | Net Carbs g | Margin | Sales Mix | Qualification |
|---|---|---|---|---|---|---|---|
| Grilled Chicken Bowl | Lunch / Dinner | 480 | 38 | 28 | 72% | 8% | Protein-Forward 20g+ |
| Egg White Breakfast Bowl | Breakfast | 320 | 26 | 14 | 78% | 5% | Protein-Forward 20g+ |
| ... | ... | ... | ... | ... | ... | ... | ... |

## Macronutrient Label Pack
- **Kiosk badge:** circular icon + "26g Protein" beside item name
- **App filter:** toggle "Protein 20g+" + toggle "Net Carbs ≤30g"
- **Web menu:** macro card on hover with calories, protein, net carbs, fiber
- **Third-party delivery:** description-line callout — "26g protein • 14g net carbs"
- **Footer microcopy (any GLP-1 surface):** "Talk to your doctor or registered dietitian about what fits your eating plan."

## Test-Market and Rollout Plan
- **Phase 1 (Weeks 1-4):** 8 stores in Charlotte and Phoenix, kiosk and app callouts only.
- **Phase 2 (Weeks 5-12):** 65 stores across 4 markets, social and email support, header A/B.
- **Phase 3 (Weeks 13-24):** System rollout pending KPI gates.
- **Kill switch:** Section penetration < 4% at week 12, or cannibalization > lift.

## Four-Metric Measurement Plan
| Metric | 4-Week Threshold | 12-Week Threshold | Owner |
|---|---|---|---|
| Section Penetration | ≥3% | ≥6% | VP Digital |
| Incremental Lift | Positive in test markets | ≥1.5% transaction lift | CFO |
| Gross Margin Index | ≥ menu average | ≥ menu average | COO |
| GLP-1 Segment Repeat | Positive trend | ≥3pt lift vs. control | Loyalty Lead |
```

## Cross-References

- **Menu Description Writer (sales)** — per-item description copy for the launch section items, applied to each surface in this brief's label pack
- **Dynamic Menu Pricing Advisor (admin)** — contribution-margin tier per item, used in Step 2's qualification rule and Step 5's cross-utilization map
- **Agentic Ordering App Readiness Brief (sales)** — in-assistant ordering app menu feed adjustments triggered by Step 6
- **AI Search Visibility Playbook (sales)** — answer-engine discovery for the FAQ and Schema.org markup recommended in Step 6
- **Digital Menu Optimization Brief (sales)** — third-party delivery storefront layout for the launch section
- **Supplier Negotiation Brief (admin)** — sourcing review for the new components surfaced by the cross-utilization map in Step 5
- **Health Inspection Prep (operations)** — regulatory accuracy of macronutrient claims, particularly under the FDA chain menu-labeling rule
- **Social Media Post Generator (sales)** — caption set for the launch communication pack in Step 10
- **Demand Forecast Briefing (operations)** — feeds the Phase 1 par-level and waste plan for the new SKUs

## Knowledge-Base References

- `knowledge-base/regulations/` — FDA chain menu-labeling rule, FTC health-claim guidance, state-level menu-labeling overlays, and the brand's claim ladder
- `knowledge-base/terminology/` — macronutrient phrasing, succinct-statement language, "talk to your doctor" footer policy
- `knowledge-base/best-practices/` — section vs. callout architecture rules, smaller-portion price-ratio convention, cross-utilization 60% target
