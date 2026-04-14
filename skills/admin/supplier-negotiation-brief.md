---
name: "Supplier Negotiation Brief"
category: admin
tools: [claude, chatgpt]
difficulty: intermediate
time_saved: "~45 min/vendor"
version: 1.1
last_eval_score: null
---

# 🤝 Supplier Negotiation Brief

## Purpose

Prepare a data-backed negotiation brief for an upcoming vendor conversation — combining 12-week price and usage trends, market benchmarks, contract terms, and leverage points — so the GM or owner walks into the call with specific asks, concession targets, and walk-away thresholds that protect COGS and service levels.

## When to Use

Use this skill before quarterly business reviews with key distributors (Sysco, US Foods, PFG, Shamrock), before renewing produce or protein contracts, when a supplier issues a price-increase notice, before switching to direct-from-farm or specialty vendors, or whenever a single line item drifts more than 5% above target food cost. Pairs well with Dynamic Menu Pricing Advisor (run first to understand margin exposure) and Food Waste Reduction Planner (for accurate usage figures).

## Required Input

Provide the following:

1. **Vendor details** — Company name, rep name and tenure, account number, current contract terms (volume tiers, rebates, early-pay discounts, delivery windows, minimum order)
2. **Purchase history** — At least 12 weeks of invoices: item SKU, pack size, unit price, quantity, total, and delivery date
3. **Usage data** — Current theoretical-vs-actual usage per item (from POS sales mix × recipe yield), waste percentages if tracked
4. **Market benchmarks** — Recent commodity index moves (USDA produce, CME cattle/pork futures, dairy price support levels), competing distributor quotes if available
5. **Contract timeline** — Renewal date, any price-lock or cost-plus escalators, volume commitments, exclusivity clauses
6. **Alternatives** — Back-up suppliers already onboarded, direct-from-producer options, cash-and-carry fallbacks, willingness to drop line items entirely
7. **Strategic context** — Upcoming menu changes, seasonal LTOs, unit-growth plans that affect volume leverage
8. **Target outcomes** — Specific asks (price reduction %, better payment terms, free freight, co-op marketing funds, slotting for a new item, volume-rebate tier)

## Instructions

You are a restaurant purchasing and cost-of-goods strategist with deep experience in broadline distribution, produce specialty houses, and direct sourcing. Your job is to produce a negotiation brief the operator can read the morning of the call and reference in real time.

**Before you start:**
- Load `config.yml` from the repo root for unit count, cuisine, COGS targets, and brand voice
- Reference `knowledge-base/terminology/` for purchasing terms (cost-plus, BOH, back-haul, dead stock, slotting fee, lead time, fill rate, spoils credit)
- Cross-check pricing against current USDA, CME, or Urner Barry indices where relevant
- If Dynamic Menu Pricing Advisor output is available, use it to quantify margin risk per category

**Process:**

1. **Spend map** — Rank items by trailing 12-week spend. Isolate the top 80% of dollars (Pareto) and flag the 10–15 SKUs that will drive negotiation value; tag commodity vs. specialty vs. proprietary items since leverage differs sharply.

2. **Price-trend audit** — For each priority SKU calculate: starting price, current price, % change, number of increases, and variance vs. the relevant commodity index. Call out items that rose faster than their index (vendor margin expansion) vs. items that held or dropped (genuine market moves).

3. **Usage and waste check** — Compare quantity purchased vs. theoretical usage from the recipe/sales-mix math. Flag over-purchasing (possible right-size opportunity), short-dates (spoilage risk), and dead SKUs (candidates to delist for simplification leverage).

4. **Benchmark pull** — State the current market rate per UOM for each priority SKU using at least two of: USDA terminal market reports, CME futures, Urner Barry, competing distributor quotes, buying-group pricing. Note whether your price is above, at, or below market.

5. **Contract and rebate analysis** — Review the active agreement for hidden levers: unpriced line items defaulting to list, missed volume-rebate tiers, expired promotional allowances, freight or fuel-surcharge creep, minimum-order penalties, and early-pay discount capture rate.

6. **Leverage inventory** — Quantify your leverage: annual spend with this vendor, share of category wallet, upcoming volume growth, willingness to multi-source, cash-and-carry alternatives, publicity risk if switching. Rate leverage High / Medium / Low.

7. **Ask ladder** — Structure asks in descending priority: (a) must-have — price relief on top-spend SKUs or matched market, (b) should-have — payment terms 21→30 days, freight waiver over threshold, locked pricing Q2–Q3, (c) nice-to-have — co-op marketing, training hours, new-item slotting, sample allowance. Include a target, an expected, and a walk-away number for each.

8. **Objection prep** — Pre-write responses to the three likeliest vendor objections: "prices are up across the board," "our margin is already thin," "we can't beat the buying group." Each response cites specific data from the brief.

9. **Concession package** — Identify concessions you can offer without damaging operations: consolidating deliveries to 2×/week, committing 90-day forecast, exclusivity on a sub-category, featuring vendor brand on menu, longer contract term. Calculate the real cost of each concession.

10. **BATNA and walk-away plan** — Document the Best Alternative To a Negotiated Agreement: named backup vendors with pricing, onboarding lead time, switching costs (menu prints, staff training, system updates). Define the walk-away trigger — a price and term combination below which you pivot to the backup.

11. **Meeting run-of-show** — Produce a 30-minute agenda: opening framing (2 min), data review (8 min), top 3 asks (10 min), objection handling (5 min), close with written action items and next-step timeline (5 min). Include the exact opening line and the closing recap template.

**Output requirements:**
- One-page executive summary at the top: vendor, total spend, top 3 asks, leverage rating, walk-away position
- Spend-by-SKU table: SKU, pack, 12-week qty, 12-week spend, starting vs. current price, % change, market benchmark, variance, ask
- Contract gap table: clause, current, requested change, annual dollar impact
- Ask ladder table: category, target, expected, walk-away, justification
- Objection-response script (quoted, ready to read aloud)
- BATNA summary with named alternative vendors and switching-cost estimate
- 30-minute meeting agenda with timestamps
- Post-call recap template (who agreed to what, by when)
- Correct terminology: cost-plus, fill rate, slotting, dead SKU, BOH, back-haul, spoils credit, rebate tier, minimum-order penalty, early-pay discount, landed cost
- Formatted for print or a single-screen read during the call
- Saved to `outputs/` if the user confirms

## Example Output

> [This section will be populated by the eval system with a reference example. For now, run the skill with sample input to see output quality.]
