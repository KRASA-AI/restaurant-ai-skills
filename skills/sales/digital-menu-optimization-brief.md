---
name: "Digital Menu Optimization Brief"
category: sales
tools: [claude, chatgpt]
difficulty: intermediate
time_saved: "~2 hr/platform/month"
version: 1.1
last_eval_score: 9.00
---

# 📱 Digital Menu Optimization Brief

## Purpose

Produce a platform-specific brief that configures an autonomous digital-menu agent (or guides a human merchandiser) to restructure item visibility, category order, photo priority, modifier flows, and upsell placements across third-party delivery marketplaces and first-party ordering channels — so the digital menu is continuously tuned to live conversion, basket-size, and margin objectives rather than replicating the in-house print menu.

## When to Use

Use this skill when onboarding a new delivery platform, re-launching a revamped menu, noticing conversion drop on a specific channel, preparing a daypart campaign (lunch combos, late-night, weekend brunch), responding to a supplier-driven cost spike on a hero item, or before activating an autonomous menu-optimization agent (Deliverect AI, Olo Engage, DoorDash Merchant Suite, Uber Eats Menu Maker, Toast Digital Menus, Square + MarketMan recipe tools). Pairs tightly with Menu Description Writer (item-level copy), Dynamic Menu Pricing Advisor (price points and day-part rules), and Demand Forecast Briefing (channel mix and capacity ceilings that should throttle promoted items).

## Required Input

Provide the following:

1. **Channels in scope** — Which storefronts are being optimized (Uber Eats, DoorDash, Grubhub, Toast TakeOut, ChowNow, Olo Rails, website, in-app, kiosk); whether each is merchant-managed or marketplace-managed
2. **Current digital menu export** — Items, categories, modifiers, modifier groups, photos present/missing, prep-time tags, availability windows, and per-channel price overrides
3. **Last 30-day channel performance** — By channel and by item: impressions (or menu views), add-to-cart rate, conversion rate, average order value, attach rate on modifiers, cancellation and refund rate
4. **Margin reference** — Item-level food cost, platform commission by channel, packaging cost, and promo contribution so the agent can prioritize contribution-dollar items, not just top-sellers
5. **Operational constraints** — Stations that bottleneck first (fryer, sauté, expo), items that degrade in transit, minimum basket for free delivery, prep-time thresholds that push you off the top rail
6. **Brand rules** — Photography style, category naming conventions, banned modifiers, allergen and dietary badge requirements, locale and language variants
7. **Objective for this run** — One of: maximize contribution dollars, lift attach rate, reduce refund rate on in-transit items, promote a specific LTO, or defend ranking during a competitor promotion
8. **Autonomous-agent toggle** — Whether the output will be executed by a human merchandiser, handed to a semi-autonomous recommender with approval gates, or pushed directly to a fully autonomous agent (and if so, what guardrails and rollback criteria apply)

## Instructions

You are a digital-menu strategist who has shipped changes across all major marketplaces and first-party stacks. Your job is to translate the operator's data and objective into a precise, channel-aware, safely-bounded change set — not a generic "best practices" list.

**Before you start:**
- Load `config.yml` for concept, cuisine, brand voice, price point, and channel contracts
- Reference `knowledge-base/terminology/` for cuisine vocabulary, dietary-badge standards, and banned words
- If `Dynamic Menu Pricing Advisor` has been run, import its Stars/Plowhorses/Puzzles/Dogs classification so promotion priority follows margin logic, not popularity alone
- If `Demand Forecast Briefing` has been run, check capacity by daypart so the brief never promotes items whose station is already saturated during the promotion window

**Process:**

1. **Frame the channel** — For each channel, state the shopper's mental model on that surface (search-driven marketplace vs. destination-brand first-party), the ranking signals the platform weights (conversion, photo coverage, prep-time, availability uptime, badges), and the three levers with highest payoff on that surface. No two channels get identical treatment.

2. **Score the current state** — Produce a per-channel scorecard: photo coverage percentage, description completeness, modifier depth, availability uptime, category order vs. margin order, and the gap between sales-rank order and contribution-dollar order. Flag every item missing a photo, missing a description longer than 40 characters, or missing at least one upsell modifier.

3. **Identify the top 10 change targets** — Rank changes by expected contribution-dollar lift, not vanity metrics. Each target names the item, the change, the channel, and the expected mechanism (improved ranking, higher add-to-cart, larger basket, fewer refunds). Items already running at capacity are excluded from volume-lift targets and are instead candidates for price-hold or substitution.

4. **Write the category and item ordering plan** — Recommend category sequence by channel: lead with the category that has the highest conversion for first-time orderers, then the highest attach-rate category, then margin categories. Within category, order items by contribution dollars per minute of station time, not by menu-print order. Call out the "anchor item" that should sit in position one and why.

5. **Modifier and upsell plan** — For each hero item, design the modifier stack that maximizes attach without creating decision fatigue: one "make it a combo" upsell, one premium swap (e.g., double protein, house-made sauce upgrade), one side attach, and at most one dessert cross-sell at basket review. Cap total modifier groups at six per item. Every modifier needs a plain-language name (no SKU codes).

6. **Photo priority list** — Name the items that most need new or improved photography, ranked by revenue impact. Specify shot type (overhead, three-quarter, in-hand), background, and whether a lifestyle or product-only frame fits the concept. Include a "do not photograph" list for items that consistently look worse than they taste.

7. **Availability and throttling rules** — Write conditional rules the agent can act on autonomously: hide items when station wait exceeds a threshold, pause promotion when prep-time ranking falls below a channel floor, snooze sold-out modifiers instead of whole items, and auto-substitute sold-out items to the nearest margin-equivalent alternative.

8. **Daypart and promotion calendar** — For the next four weeks, map which items are featured on which channel during which daypart, aligned to the capacity signal from Demand Forecast Briefing. Include rollback criteria: if conversion lift is under X percent after Y days, revert. If refund rate on a promoted item exceeds the concept baseline by 20 percent, pause immediately.

9. **Agent guardrails** — If the output will drive an autonomous agent, specify the hard stops: maximum price change per run, maximum items promoted simultaneously, protected categories the agent may not reorder (loyalty favorites, alcohol compliance), and the approval path required to cross any guardrail. Define what counts as a failed experiment and what counts as confirmation to promote the change to a permanent state.

10. **Measurement plan** — Name the three metrics that will close the loop for each change: a channel-ranking proxy, a contribution-dollar proxy, and a guest-experience proxy (refund or low-rating rate). Specify the measurement window, the statistical guardrail (minimum orders before concluding), and the owner responsible for reading the report.

## Output Format

A single brief, ready to drop into the platform's merchant tool or the autonomous agent's configuration:

1. Executive summary — objective, channels, expected contribution-dollar lift range, risks
2. Per-channel scorecards
3. Top 10 prioritized change targets with expected mechanism
4. Category and item ordering plan (per channel)
5. Modifier and upsell plan (per hero item)
6. Photo priority list with shot specs
7. Availability and throttling rule set
8. Four-week daypart and promotion calendar with rollback criteria
9. Agent guardrails (if applicable)
10. Measurement plan and review cadence

## Quality Checks

Before delivering, verify:
- Every change names its channel, expected mechanism, and measurement
- No recommendation promotes an item whose bottleneck station is already over capacity in the relevant daypart
- Contribution-dollar ranking drives promotion order, not raw volume
- Every autonomous-agent rule has a rollback condition
- Brand rules, dietary badges, and allergen callouts are preserved across every proposed change
- Locale and language variants are handled for multi-region operators
- No item is promoted on a channel where its prep-time tag would demote it below the top rail
- Nothing in the brief assumes print-menu ordering is the correct digital ordering

## Related Skills

- `sales/menu-description-writer.md` — Supplies the copy layer this brief promotes
- `admin/dynamic-menu-pricing-advisor.md` — Supplies margin classification and price constraints
- `operations/demand-forecast-briefing.md` — Supplies capacity and daypart signals
- `operations/food-waste-reduction-planner.md` — Supplies "push these ingredients" input that can be expressed as featured-item selections

## Notes on Autonomous Agents

Platform-native autonomous menu agents (Deliverect AI Menu Agent, Square + MarketMan recipe intelligence, Olo Rails optimizer, Toast Digital Menus assistant) increasingly make layout, visibility, and modifier decisions without human approval between runs. This skill produces the *input* brief that tells those agents what to optimize for, which rails to stay inside, and how to measure a successful experiment — the agents still need a contribution-dollar objective, capacity-aware guardrails, and brand rules from the operator. Do not let the agent define its own success metric.

## Example Output

### Example 1 — Mid-week LTO launch across Uber Eats + DoorDash + Toast TakeOut + first-party web (fast-casual)

**Input:**
- Concept: Ramen Loop, 3-unit fast-casual ramen, Chicago (Loop / West Loop / Lincoln Park); Toast POS, Toast TakeOut + Olo Rails feeding Uber Eats / DoorDash / Grubhub
- Objective: launch a "Cold Tantan" summer LTO (limited 4 weeks: 2026-05-27 to 2026-06-23) and lift contribution dollars on the lunch and late-night dayparts without cannibalizing the year-round Tonkotsu hero
- Last 30-day channel mix: Uber Eats 38% / DoorDash 31% / Toast TakeOut 18% / first-party web 13%; Toast TakeOut prep-time tag drifted from "10–15 min" to "20–25 min" in the prior week (kitchen ticket-time creep), demoting two items off the Toast top rail
- Margin reference: Cold Tantan plate cost $4.10, sells $15 first-party / $16.50 marketplace (parity-aware uplift covering commission), CM 73% first-party / 67% marketplace; Tonkotsu plate cost $3.85, sells $14 / $15.50, CM 72% / 65%
- Operational constraints: cold-station bottleneck during the 11:30–1:30 lunch window; Cold Tantan does not degrade in transit (cold-by-design) — safe to promote on marketplace; Lincoln Park unit has a separate cold-station headcount, the other two share
- Brand rules: Japanese terms italicized once (tantan-men, tonkotsu), allergen badges required (sesame, soy, gluten); spice ladder "mild / medium / hot / 5-alarm" — no scoville numbers
- Autonomous-agent toggle: Deliverect AI Menu Agent enabled on Uber Eats + DoorDash with approval gates for any price change > 3% or any new modifier; Toast Digital Menus assistant on auto-run with no agent gating

**Output — Executive summary (CEO / Ops paste-ready):**

> **Objective:** Cold Tantan LTO (4 wk, 2026-05-27 to 2026-06-23) across Uber Eats / DoorDash / Toast TakeOut / first-party web. **Expected contribution-dollar lift range: +$11K to +$18K over the window, blended.** **Top risks:** (1) Toast TakeOut ticket-time drift demoting promoted items, (2) cold-station bottleneck at Loop and West Loop during lunch, (3) cannibalization of Tonkotsu beyond a 12% acceptable swap rate.

**Per-channel scorecards (current state):**

| Channel | Photo coverage | Description completeness | Modifier depth | Availability uptime (30d) | Category order vs. margin order | Top 3 gaps |
|---|---|---|---|---|---|---|
| Uber Eats | 91% | 88% | 4.2 avg / item | 97.4% | 60% aligned | (1) Tonkotsu has no "make it a combo" upsell, (2) Cold Tantan absent (LTO not loaded), (3) 4 items missing 40+ char descriptions |
| DoorDash | 87% | 84% | 3.8 avg / item | 96.1% | 55% aligned | (1) Categories ordered alphabetically (broken), (2) Pickled-egg add-on out of stock at Lincoln Park but live on marketplace, (3) Spice-ladder badge absent |
| Toast TakeOut | 96% | 92% | 4.5 avg / item | 99.1% | 80% aligned | (1) Prep-time tag drift demoting top items, (2) Cold Tantan absent, (3) Combo CTA dead-linked |
| First-party web | 100% | 100% | 5.1 avg / item | 99.7% | 90% aligned | (1) Hero scroll-fold misses the LTO, (2) No loyalty attach on the order CTA, (3) Mobile add-on stack too tall (decision fatigue) |

**Top 10 prioritized change targets (ranked by expected contribution-dollar lift):**

| # | Item | Change | Channel | Mechanism | Expected lift / wk |
|---|---|---|---|---|---|
| 1 | Cold Tantan (LTO) | Load with photo, allergen badges, spice ladder, "Add chilled-egg +$1.50" upsell | All four | New SKU live + ranked | +$2,800 |
| 2 | Tonkotsu | Add "Make it a combo +$4" (gyoza 4-pc + green tea) | UE + DD + Toast | Higher AOV | +$1,400 |
| 3 | Category reorder | Lead with "Summer Limited" → "Signature Ramen" → "Sides" → "Drinks" → "Sweets" | UE + DD | Cold Tantan in position 1 of category 1 | +$1,200 |
| 4 | Toast prep-time tag | Re-baseline to 12–17 min (verify with last 7-day actuals) | Toast | Restore top-rail position | +$900 |
| 5 | Photo refresh: Tantan-men | Three-quarter, hand-held, cold-condensation visible | UE + DD | CTR lift | +$700 |
| 6 | Pickled-egg modifier | Snooze at Lincoln Park; live at Loop + West Loop | DD | Refund-rate drop | +$420 (avoided refunds) |
| 7 | Spice ladder | Add "mild / medium / hot / 5-alarm" badges to every ramen | UE + DD | Decision speed → conversion | +$550 |
| 8 | Allergen badges | Add sesame + soy + gluten on all six items | All four | Compliance + filter rank | +$380 |
| 9 | Mobile add-on cap | Cap at 4 modifier groups per item on web | First-party web | Decision fatigue → conversion | +$300 |
| 10 | Loyalty attach on web CTA | "Earn 2× points on this LTO" banner | First-party web | Repeat rate | +$250 |

**Category and item ordering plan (per channel, lunch + late-night dayparts):**

- **Uber Eats / DoorDash (search-driven marketplaces):** Category 1 = "Summer Limited" (Cold Tantan anchors position 1). Category 2 = "Signature Ramen" (Tonkotsu position 1; CM/min-of-station ordering). Category 3 = "Sides" (gyoza 4-pc anchors position 1 as the combo attach). Category 4 = "Drinks" (Sapporo tall + Japanese cold brew up top). Cold Tantan is the anchor item because it's the only menu item that does not degrade in transit AND sells in the highest-margin daypart band — it's the right ranking signal feed for both surfaces.
- **Toast TakeOut (destination-brand first-party):** Same category sequence; in-category ordering by combo readiness — items with active combo modifiers float to position 1 within the category.
- **First-party web (destination-brand first-party):** Hero scroll-fold = Cold Tantan + loyalty 2× points banner. Below-fold = full menu in margin-ordered position.

**Modifier and upsell plan (Cold Tantan and Tonkotsu — hero items):**

| Item | Combo upsell | Premium swap | Side attach | Dessert cross-sell at basket review |
|---|---|---|---|---|
| Cold Tantan ($15) | "Make it a combo +$4 (gyoza 4-pc + iced barley tea)" | "Add chilled-egg +$1.50" | "Add edamame +$3" | "Add yuzu sorbet +$5" |
| Tonkotsu ($14) | "Make it a combo +$4 (gyoza 4-pc + green tea)" | "Add chashu +$3" | "Add menma +$2" | "Add yuzu sorbet +$5" |

Modifier-group cap: 6 per item. Names plain-language; no SKU codes. Allergen and spice badges live in metadata, not modifier UI.

**Photo priority list:**

| Item | Shot type | Background | Reason |
|---|---|---|---|
| Cold Tantan | Three-quarter, hand-held, cold-condensation visible on bowl rim | Slate gray, soft window light | Hero LTO — new SKU, no prior photo coverage |
| Tantan-men | Overhead with sesame seed close-up | Wood prep board | Existing photo flat-looking; CTR drift down 14% over 30 days |
| Gyoza 4-pc | Three-quarter with steam | Black plate | Lifts combo attach (this is the combo attach SKU) |

Do-not-photograph list: pickled egg (always looks worse than it tastes); chashu solo (better as part of the bowl frame).

**Availability and throttling rules (Deliverect AI agent acts on these autonomously):**

```
IF cold-station ticket-time > 9 min AT Loop OR West Loop DURING 11:30–13:30:
   THROTTLE Cold Tantan promotion 50% on UE + DD (drop from top rail)
ELSE: hold promoted state

IF Toast prep-time tag > 17 min ANYWHERE:
   PAUSE all Toast TakeOut top-rail promotion until tag normalizes for 60 min

IF pickled-egg modifier sold-out AT any unit:
   SNOOZE modifier (not whole item) at that unit only

IF Cold Tantan sells out at any unit:
   AUTO-SUBSTITUTE to Tantan-men (warm variant, same flavor profile) with a
   one-line guest note: "Cold Tantan is sold out tonight — chef recommends
   the warm Tantan-men as the nearest match."
```

**Four-week daypart and promotion calendar:**

| Week | Lunch (11:30–14:00) | Late-night (21:00–23:00) | Channel emphasis | Rollback criteria |
|---|---|---|---|---|
| Week 1 (5/27–6/2) | Cold Tantan featured, position 1 | Cold Tantan paired with Sapporo combo | UE + DD top rail; Toast destination | < 8% lift vs. wk-0 baseline by Day 5 → revert position 2 |
| Week 2 (6/3–6/9) | Hold; A/B test photo refresh | Add yuzu sorbet attach incentive | Same | Refund rate on Cold Tantan > 1.5% → pause UE + DD promo |
| Week 3 (6/10–6/16) | World Cup 2026 lunch-watch window starts 6/11 (US matches in CHI MetLife coverage but no Chicago host site — small but real lift on the late-night daypart from screen audience) | Late-night featured + Sapporo combo | DD + UE late-night top rail | Tonkotsu swap rate > 12% (cannibalization gate) → pause Cold Tantan combo upsell |
| Week 4 (6/17–6/23) | Wind-down — soft scarcity messaging "last week" | Position 2 (off top rail) | Toast TakeOut feature; UE + DD shift to Tonkotsu | n/a — last week of LTO |

**Agent guardrails (Deliverect AI Menu Agent):**

- Max price change per run: 3% (above this requires GM approval gate)
- Max items promoted simultaneously: 3
- Protected categories (no reorder): "Drinks" (alcohol compliance + age gate live)
- Approval path: GM dashboard ping to Maria López at Loop, Marisol Chen at West Loop, Devon Park at Lincoln Park; auto-approve at unit level only if the lift signal is statistically significant after 7 days at p < 0.10
- Failed-experiment criterion: < 8% lift over wk-0 baseline AND refund rate steady — revert to wk-0 layout, log learning to outputs/digital-menu-experiments/2026-05-27-cold-tantan.md
- Successful-experiment criterion: ≥ 12% lift over wk-0 baseline AND refund rate ≤ wk-0 + 0.2 pts — promote the layout to the year-round Tonkotsu-anchor variant for the post-LTO state

**Measurement plan (3 metrics close the loop, weekly cadence, GM-owned):**

| Metric | Channel-ranking proxy | Contribution-dollar proxy | Guest-experience proxy |
|---|---|---|---|
| Cold Tantan | Position-1 share-of-impression on UE + DD top rail (target ≥ 65%) | Daily contribution dollars from Cold Tantan + combo attach (target ≥ $400/day blended across 3 units) | Refund rate ≤ 1.2% AND ≥ 4.6 avg rating |
| Tonkotsu (cannibalization check) | n/a | Daily unit volume vs. wk-0 baseline (acceptable swap: −12%; below this triggers Cold Tantan combo pause) | n/a |

Statistical guardrail: ≥ 200 orders per channel per unit before concluding lift; reported to leadership weekly via the Tuesday ops huddle.

---

### Example 2 — World Cup 2026 host-city multilingual digital-menu surge (Dallas/Arlington premium-casual sports bar, EN/ES dual-channel)

**Input:**
- Concept: Tres Banderas, 180-cover premium-casual sports bar in Arlington TX (10 min from AT&T Stadium, a confirmed World Cup 2026 host venue running 9 matches incl. a SF on 7/14); R365 POS + Toast Digital Menus + Olo Rails into UE / DD / Grubhub; loyalty live (R365 Loyalty)
- Objective: maximize contribution dollars during the World Cup 2026 group-stage and knockout windows (6/11–7/19), defend the year-round brisket-taco hero from cannibalization by the World Cup LTO insert, and capture the visiting-fan multilingual audience (the 9-match Arlington schedule includes 3 LATAM-team matches with substantial Mexican / Argentine / Brazilian fan visitation expected per Dallas Sports Commission projections)
- Last 30-day channel mix: UE 34% / DD 28% / first-party app 24% / Toast TakeOut 14%; first-party app already at 24% (Tres Banderas pre-staged the loyalty CTA during the NRA Show 2026 week — strong baseline)
- Margin reference: World Cup LTO insert items — picanha plate ($34 Star, AAA Marfrig CM 68% first-party / 60% marketplace), pão de queijo ($9 Plowhorse CM 78%), caipirinha ($14 signature CM 79% — alcohol so first-party only), birria taco trio ($24 Star CM 72% / 64%), Argentine choripán ($18 CM 70% / 63%)
- Operational constraints: grill bottlenecks at peak match windows; AT&T Stadium match-day double-peaks (90 min pre-match 11:30–13:30 for early kickoffs, 60 min post-match 16:30–18:00); first-party app pickup window expands to 45 min during match days; loyalty attach is the year-round flywheel (do not cannibalize)
- Brand rules: Spanish + Portuguese accent characters preserved verbatim (picanha NOT picaña; pão de queijo NOT pao de queijo); proper-noun preservation (Marfrig AAA, Leblon cachaça, Pittsburgh-style Star-classification, Dallas Sports Commission); Florida-style transparent service-charge disclosure adopted house-wide ahead of the Florida 2026-07-01 effective date (Texas has no equivalent statute but the operator runs the standard for brand consistency)
- Autonomous-agent toggle: Deliverect AI on UE + DD with approval gates for any > 2% price change; Toast Digital Menus assistant on auto-run; first-party app menu hand-edited by digital ops lead

**Output — Executive summary (CMO / Ops paste-ready):**

> **Objective:** World Cup 2026 LTO insert across UE / DD / first-party app / Toast TakeOut, group-stage window 6/11–7/3 + knockout 7/4–7/19. **Expected contribution-dollar lift range: +$78K to +$112K over the 6-week window, blended across the 3 LATAM-team match windows and the 2 non-LATAM home matches.** **Top risks:** (1) Brisket-taco cannibalization beyond 18% acceptable swap rate, (2) caipirinha alcohol-compliance gating on first-party app pickup, (3) grill bottleneck during the 11:30–13:30 early-kickoff peak, (4) multilingual content drift across channels (UE Spanish toggle live since 2024; DD English-only; first-party app supports EN + ES + PT).

**Per-channel scorecards:**

| Channel | EN coverage | ES coverage | PT coverage | Photo cov. | Allergen badges | Top 3 gaps |
|---|---|---|---|---|---|---|
| Uber Eats | 100% | 92% (US ES toggle) | 0% (UE has no PT US toggle) | 94% | 88% | (1) ES descriptions machine-translated in 4 items (re-translate), (2) Picanha PT term retained verbatim but ES-only audience won't see PT, (3) Caipirinha cannot list (alcohol — UE policy varies by state, OFF in TX) |
| DoorDash | 100% | 0% | 0% | 91% | 84% | (1) No ES surface at all (DD has no US ES toggle 2026Q2), (2) Spanish-speaking guests use DD via English keywords — needs ES keyword density in English descriptions, (3) Match-day prep-time tag needs pre-staging |
| First-party app | 100% | 100% | 100% | 100% | 100% | (1) Hero scroll-fold misses the World Cup insert as of today, (2) Loyalty 3× points on LTO not banner-promoted, (3) Mobile add-on stack too tall on the picanha SKU |
| Toast TakeOut | 100% | 95% | 60% | 96% | 92% | (1) Toast supports EN + ES; PT entries are stored but not surfaced in-product (workaround: PT terms in EN description italicized once), (2) Caipirinha gated to over-21 verification step, (3) Combo CTA dead-linked |

**Top 10 prioritized change targets (contribution-dollar ranked):**

| # | Item | Change | Channel | Mechanism | Expected lift / wk (during group-stage match weeks) |
|---|---|---|---|---|---|
| 1 | Picanha plate (LTO) | Load EN + ES (UE ES toggle) + PT (first-party app + Toast PT in description), allergen badges, AAA Marfrig grade-claim verbatim across all languages | All four | New SKU live + ranked top of LTO | +$5,400 |
| 2 | Birria taco trio (LTO) | Load EN + ES across all channels; defends against brisket-taco cannibalization by sitting as a Mexican-team-match feature anchor | All four | New SKU + LATAM-match anchor | +$3,800 |
| 3 | Caipirinha (LTO) | Load on first-party app + Toast TakeOut only (alcohol policy gating UE + DD off in TX) with 21+ verification + Leblon cachaça brand preservation | First-party + Toast | New SKU on legal channels only | +$2,200 |
| 4 | Argentine choripán (LTO) | Load EN + ES across all channels; Argentine-team-match anchor | All four | New SKU + match-day anchor | +$2,400 |
| 5 | Pão de queijo (LTO) | Load EN + ES (PT term italicized once, untranslated); add as a "Brazil-match starter" combo attach | First-party + Toast + UE | Plowhorse → attach-driven margin lift | +$1,100 |
| 6 | Match-day prep-time pre-stage | Toast: pre-stage 18–22 min tag for 90 min pre-match windows; revert post-peak | Toast TakeOet | Restore top-rail despite ticket-time creep | +$1,800 |
| 7 | First-party app hero scroll-fold | Replace year-round brisket-taco hero with rotating World Cup insert (3 hero rotations per match day) | First-party app | Conversion lift | +$2,100 |
| 8 | Loyalty 3× points banner | "Earn 3× points on the World Cup menu" — first-party app only | First-party app | Loyalty attach + repeat rate | +$1,400 |
| 9 | ES keyword density (DD) | Add "tacos de birria" "picaña a la parrilla" "choripán argentino" as English-tagged keywords (DD's search index reads them despite the EN-only UI) | DD | ES-speaking guest discovery without an ES toggle | +$1,600 |
| 10 | Brisket-taco cannibalization gate | Auto-pause Picanha + Birria combo upsell IF brisket-taco daily volume drops > 18% below wk-0 baseline | All four | Hero defense | n/a (avoided loss: −$2,800/wk if breached) |

**Category and item ordering plan (per channel, World Cup match-day dayparts):**

- **Uber Eats / DoorDash:** Match-day Category 1 = "World Cup Menu" (Picanha plate anchors on Brazil-match days; Birria taco trio anchors on Mexico-match days; Choripán anchors on Argentina-match days — auto-rotated by match calendar). Category 2 = "Signature Tex-Mex" (brisket taco position 1, defends against cannibalization). Category 3 = "Sides" (pão de queijo position 1 on Brazil-match days). Category 4 = "Drinks" (alcohol items hidden on UE/DD per TX policy).
- **First-party app:** Hero scroll-fold rotates by match day. Below-fold = full menu in margin order. Loyalty 3× banner pinned at top of the World Cup Menu category.
- **Toast TakeOut:** Same Category 1 rotation; alcohol category live (Caipirinha + Sapporo + Brazilian beer trio) with 21+ verification step.

**Modifier and upsell plan (hero LTO items):**

| Item | Combo upsell | Premium swap | Side attach | Dessert cross-sell |
|---|---|---|---|---|
| Picanha plate ($34) | "Make it a Brazil-match combo +$8 (pão de queijo basket + caipirinha)" — first-party + Toast only | "Add a chimichurri verde +$2" | "Add pão de queijo +$5" | "Add brigadeiro trio +$7" |
| Birria taco trio ($24) | "Make it a Mexico-match combo +$6 (consommé side + agua fresca)" — all channels | "Add a quesabirria fold-over +$4" | "Add elote +$5" | "Add tres leches +$6" |
| Argentine choripán ($18) | "Add chimichurri side +$2; add empanada attach +$5" | "Add provoleta +$6" | "Add fries +$4" | n/a |

Modifier-group cap: 6 per item. Caipirinha modifier ("Add Leblon premium pour +$3") is loyalty-only and surfaces only on first-party app + Toast.

**Photo priority list:**

| Item | Shot type | Background | Reason |
|---|---|---|---|
| Picanha plate | Overhead with grill marks visible, chimichurri verde in a side ramekin | Slate, soft side light | Hero LTO; AAA Marfrig grade-claim photo must show a recognizable grain pattern |
| Birria taco trio | Three-quarter with consommé in a clear cup; visible cheese pull on one taco | White marble | Mexico-match anchor; cheese pull is the social-share frame |
| Choripán | Three-quarter, hand-held, chimichurri on the bun | Wood prep board | Argentina-match anchor |
| Caipirinha | Overhead with Leblon bottle visible at frame edge | Bar wood | Brand preservation (Leblon) is a legal-claim sourcing line |
| Pão de queijo basket | Overhead, steam, basket | Slate | Plowhorse — needs CTR lift |

Do-not-photograph: brisket-taco (existing photo is the strongest CTR shot in the year-round menu; do not replace).

**Availability and throttling rules:**

```
IF grill ticket-time > 11 min DURING 11:30–13:30 (early-kickoff window):
   THROTTLE Picanha + Choripán promotion 60% on UE + DD (drop from top rail)
ELSE: hold promoted state

IF Toast prep-time tag > 22 min during match-day pre-staged window:
   PAUSE all Toast TakeOut top-rail promotion + DM Maria López (GM) for grill triage

IF brisket-taco daily volume drops > 18% below wk-0 baseline:
   AUTO-PAUSE the Picanha + Birria combo upsells (cannibalization gate)
   AND ping CMO via R365 AI Dashboard alert

IF caipirinha modifier triggered on UE or DD (operator error):
   HARD BLOCK + log to compliance audit (TX alcohol policy — first-party + Toast only)

IF a World Cup LTO item sells out at any unit:
   AUTO-SUBSTITUTE to the nearest LATAM-team match-day anchor with a one-line
   ES + PT note: "Sold out — chef recommends [substitute]" / "Agotado — chef
   recomienda [sustituto]" / "Esgotado — chef recomenda [substituto]"
```

**Six-week daypart and promotion calendar (group-stage 6/11–7/3 + knockout 7/4–7/19, AT&T Stadium 9-match schedule overlay):**

| Week | Match anchor at AT&T (Arlington) | Primary surface | Channel emphasis | Rollback criteria |
|---|---|---|---|---|
| Wk 1 (6/11–6/17) | Tournament opener Mexico v Croatia 6/11 → Birria taco trio anchor; Argentina v Saudi 6/14 → Choripán anchor | First-party app hero rotation + UE/DD top rail | All four; Toast destination | Brisket-taco swap > 18% → pause combos |
| Wk 2 (6/18–6/24) | Brazil v Cameroon 6/19 → Picanha + pão de queijo anchor; USA group match → Brisket-taco home-team anchor | First-party + UE top rail | Same | Refund rate on Picanha > 1.8% → pause UE/DD |
| Wk 3 (6/25–7/1) | Group-stage finals + R32 5/26 → rotation by team-survival | All four | DD + UE rebalance to surviving-team anchors | Loyalty attach < 38% on LTO → reset loyalty banner copy |
| Wk 4 (7/2–7/8) | R32 + R16 at AT&T 7/3 + 7/6 → match-day surge anchoring | First-party + Toast | Toast TakeOet pickup-window expand to 60 min | Grill bottleneck > 60 min sustained → 86 the choripán combo for that day |
| Wk 5 (7/9–7/15) | Quarterfinals at AT&T 7/11 → highest-margin window | All four | All hands; pre-stage at 90 min mark | Same gates |
| Wk 6 (7/16–7/19) | Semifinal at AT&T 7/14 → peak; LTO wind-down 7/19 | First-party hero; UE/DD ramp down | First-party loyalty redemption push | n/a (wind-down) |

Final and 3rd-place at MetLife (NJ) and SoFi (LA) respectively — Arlington's tournament closes 7/14 with the SF.

**Agent guardrails (Deliverect AI):**

- Max price change per run: 2% (tighter than the standard 3% — high-traffic high-attention window)
- Max items promoted simultaneously: 4 (the four LTO anchors + Brisket-taco hero defended)
- Protected categories (no reorder): "Drinks" (alcohol compliance), "Loyalty" (R365 Loyalty surface)
- Approval path: GM dashboard ping to Maria López; auto-approve only with 7-day p < 0.10 lift signal
- Compliance hard-stop: caipirinha modifier on UE or DD → hard block, no override
- Failed-experiment criterion: < 9% lift vs. wk-0 baseline OR brisket-taco swap > 18% → revert combo upsells, log learning to outputs/digital-menu-experiments/2026-06-11-world-cup-2026.md
- Successful-experiment criterion: ≥ 14% lift AND brisket-taco swap ≤ 12% AND loyalty attach ≥ 42% on LTO → promote LTO learnings to the year-round Tex-Mex menu refresh planned for 2026-08

**Measurement plan (R365 AI Dashboard, weekly + match-day cadence):**

| Metric | Channel-ranking proxy | Contribution-dollar proxy | Guest-experience proxy |
|---|---|---|---|
| Picanha plate | Position 1 share-of-impression on UE Spanish toggle + first-party hero (target ≥ 70% on Brazil-match days) | Daily contribution dollars target ≥ $1,800 on Brazil-match days, ≥ $800 on non-anchor days | Refund rate ≤ 1.5% AND ≥ 4.7 avg rating with explicit AAA-grade mentions tracked |
| Birria taco trio | Position 1 share on Mexico-match days (target ≥ 75%) | Daily ≥ $2,100 on Mexico-match days | Same |
| Brisket-taco (defended hero) | Position 1 on Signature Tex-Mex (defend) | Daily volume swap ≤ 12% vs. wk-0 baseline (gate) | n/a |
| Loyalty attach on LTO (R365 Loyalty) | n/a | LTO loyalty attach target ≥ 42% (vs. 35% year-round) | n/a |

Statistical guardrail: ≥ 150 orders per channel per match-window before concluding lift. Reporting cadence: post-match-day flash recap within 18 hours (Maria López owns) + weekly Tuesday huddle (Marcus Reyes CMO + Maria López GM) + 6-week wrap with R365 AI Dashboard prime-cost attribution + LTO loyalty cohort recurrence read at the 6-week + 12-week mark.

**Multilingual compliance audit (pre-launch checklist, all channels):**

- ✅ Picanha NOT picaña (Brazilian PT spelling preserved across all four channels' EN + ES + PT surfaces)
- ✅ Pão de queijo NOT pao de queijo (PT diacritics preserved)
- ✅ Marfrig AAA grade-claim verbatim across EN + ES + PT (no machine translation; human-reviewed)
- ✅ Leblon cachaça brand preservation (Leblon, not generic "cachaça brand")
- ✅ Service-charge transparency disclosure: house-standard "An 18% service charge applies on parties of 8 or more; this is not a tip" in EN, "Se aplica un cargo por servicio del 18% en grupos de 8 o más; esto no es una propina" in ES, "Uma taxa de serviço de 18% é aplicada em grupos de 8 ou mais; isso não é uma gorjeta" in PT (Texas has no equivalent law; this is house policy adopted ahead of FL 2026-07-01)
- ✅ Allergen badges (gluten / dairy / nuts / shellfish) translated EN + ES + PT
- ✅ Spice ladder "mild / medium / hot" → "suave / medio / picante" → "suave / médio / picante" (no machine translation — human-reviewed glossary from `_shared/review-responder` v1.3 Step 8 + `sales/menu-description-writer` v1.3 Step 13 propagated here)
- ✅ Caipirinha is alcohol — gated to first-party app + Toast only on TX (UE + DD alcohol policy off in TX; hard block at the agent layer)
- ✅ No emoji in any language version (brand rule)
- ✅ "Brazilian-grade AAA picanha" is sourcing-claim language verified against Marfrig importer documentation — legal-team-approved across all three languages
