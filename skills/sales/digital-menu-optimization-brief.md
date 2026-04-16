---
name: "Digital Menu Optimization Brief"
category: sales
tools: [claude, chatgpt]
difficulty: intermediate
time_saved: "~2 hr/platform/month"
version: 1.0
last_eval_score: null
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
