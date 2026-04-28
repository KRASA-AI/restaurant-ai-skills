---
name: "Supplier Negotiation Brief"
category: admin
tools: [claude, chatgpt]
difficulty: intermediate
time_saved: "~45 min/vendor"
version: 1.2
last_eval_score: 9.20
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

Three reference outputs covering the full leverage spectrum — a broadline distributor QBR with high leverage and a clean ask ladder, a mid-cycle price-increase pushback on a produce specialty house with low immediate leverage, and a direct-from-farm switching analysis with a named BATNA. Each is paste-ready into a brand-side counsel/owner pre-call binder and reuses the exact terminology purchasing professionals expect (cost-plus, fill rate, slotting, dead SKU, back-haul, rebate tier, minimum-order penalty, landed cost).

### Example 1 — Broadline distributor QBR (Sysco, 4-unit fast-casual, high leverage)

```markdown
# Supplier Negotiation Brief — Sysco Q2 2026 QBR
## Cantina Verde (4 units, Austin TX) × Sysco San Antonio
## Meeting: 2026-05-06 10:00 AM CT, video; rep: T. Reyes (8-yr tenure); contract auto-renews 2026-09-30

## Executive Summary
- **Vendor:** Sysco San Antonio | Account #: 4811-22 | 12-week spend: $284,712 | Annualized: ~$1.23M
- **Top 3 asks:** (1) -3.4% price relief on top-15 SKUs (chicken thigh, ribeye, ground chuck, masa, queso oaxaca, jalapeño, lime, tortilla, oil) = ~$28K/yr saved; (2) Net-30 from current Net-21 = ~$8K/yr cash-flow benefit; (3) lock pricing through Q3 on the four protein SKUs that drove 71% of the inflation
- **Leverage rating:** HIGH — annual spend in top 5% of rep's book; 4-unit growth to 6 by 2026-12 (committed); back-up vendor (Restaurant Depot + Performance Food Group) onboarded; willing to multi-source 30% to PFG within 60 days
- **Walk-away position:** -2.0% on top-15 + Net-30 + Q3 protein lock; below this, multi-source 30% to PFG starting 2026-06-01 and re-bid annual contract 2026-08

## Spend Map (Pareto, top 15 SKUs of $284,712 trailing-12-week spend)
| SKU | Pack | 12-wk Qty | 12-wk Spend | Start Price | Current Price | % Δ | USDA/CME Index Δ | Variance | Ask |
|---|---|---|---|---|---|---|---|---|---|
| Chicken thigh BL/SL | 40 lb | 2,180 lb | $11,990 | $5.18 | $5.50 | +6.2% | +2.1% | +4.1% (vendor margin) | -4.0% to $5.28 |
| Ribeye 1×9 IBP | 12 ct | 380 lb | $9,082 | $22.10 | $23.90 | +8.1% | +3.8% (CME live cattle) | +4.3% | -4.0% to $22.94 |
| Ground chuck 81/19 | 10 lb | 940 lb | $4,512 | $4.62 | $4.80 | +3.9% | +3.7% | +0.2% | hold |
| Masa harina (Maseca) | 25 lb | 1,800 lb | $2,520 | $1.32 | $1.40 | +6.1% | +1.4% | +4.7% | -4.0% to $1.34 |
| Queso oaxaca | 5 lb | 480 lb | $4,032 | $8.20 | $8.40 | +2.4% | +0.8% | +1.6% | -2.0% to $8.23 |
| Jalapeño fresh | 25 lb | 920 lb | $1,840 | $1.92 | $2.00 | +4.2% | +5.1% | -0.9% | hold (genuine market) |
| Lime fresh | 40 lb | 2,400 lb | $4,560 | $1.78 | $1.90 | +6.7% | +2.2% | +4.5% | -4.0% to $1.82 |
| Corn tortilla 6" | 30 ct | 14,400 ct | $5,184 | $0.34 | $0.36 | +5.9% | +0.9% | +5.0% | -4.0% to $0.345 |
| Soybean oil 35 lb | jug | 84 jugs | $2,772 | $32.10 | $33.00 | +2.8% | +1.6% | +1.2% | -1.5% to $32.50 |
| Black bean dry | 25 lb | 600 lb | $1,140 | $1.84 | $1.90 | +3.3% | +2.4% | +0.9% | hold |
| Heavy cream | 1 gal | 240 gal | $2,304 | $9.40 | $9.60 | +2.1% | +1.8% | +0.3% | hold |
| Yellow onion | 50 lb | 1,800 lb | $1,584 | $0.84 | $0.88 | +4.8% | -1.2% (USDA terminal) | +6.0% | -5.0% to $0.836 |
| Cilantro | 30 ct | 540 ct | $1,890 | $3.40 | $3.50 | +2.9% | +0.4% | +2.5% | -2.0% to $3.43 |
| Sour cream tub | 5 lb | 360 lb | $2,376 | $6.40 | $6.60 | +3.1% | +2.1% | +1.0% | hold |
| Avocado #2 | 25 lb | 1,200 lb | $9,600 | $7.80 | $8.00 | +2.6% | +1.9% | +0.7% | hold |
| **Top-15 subtotal** | | | **$65,386** | | | | | | **~$2,300/qtr saved if asks land at -3.4% blended** |

## Contract Gap Table
| Clause | Current | Requested Change | Annual $ Impact |
|---|---|---|---|
| Payment terms | Net-21 | Net-30 | +$8K cash-flow benefit (assuming 5.5% capital cost) |
| Volume rebate | 0.75% on >$1.0M annual | 1.25% on >$1.2M (matches our committed 6-unit run-rate) | +$5K |
| Fuel surcharge | $42/delivery | Cap at $35/delivery | +$2.6K |
| Q3 protein lock | None | Lock chicken thigh, ribeye, ground chuck, oil at Q2-end pricing through Q3 | Hedges ~$6K of inflation risk |
| Slotting on new house-made queso program (Q3 launch) | N/A | Free slotting + co-op on launch print | +$3K marketing fund |
| Dead-SKU credit | N/A | 30-day return on un-opened cases at our request (we have 6 dead SKUs taking $1.8K of working capital) | +$1.8K one-time |

## Ask Ladder
| Tier | Ask | Target | Expected | Walk-Away | Justification |
|---|---|---|---|---|---|
| Must-have | Top-15 SKU price relief | -4.0% | -3.4% | -2.0% | Variance vs. USDA/CME index; Restaurant Depot + PFG quotes in hand |
| Must-have | Q3 protein price lock | 4 SKUs | 3 SKUs | 2 SKUs | Q3 commodity volatility forecast on chicken + cattle |
| Should-have | Net-30 | Net-30 | Net-28 | Net-21 (current) | Industry standard at our spend tier |
| Should-have | Volume rebate tier reset | 1.25% on >$1.2M | 1.0% on >$1.2M | hold current | Committed 6-unit growth |
| Should-have | Fuel surcharge cap | $35 | $38 | $42 (current) | Diesel index has eased Q1 |
| Nice-to-have | Slotting on house-made queso | Free | Free + half co-op | hold | Vendor brand exposure on launch print |
| Nice-to-have | Dead-SKU credit | $1.8K | $1.0K | hold | One-time working-capital release |

## Objection Prep (3 likeliest vendor objections + scripted response)
1. **"Prices are up across the board."** — "Across the board, yes — but on chicken thigh, ribeye, masa, lime, corn tortilla, and yellow onion the variance over the USDA terminal and CME futures sits at 4 to 6 percentage points above index. We've pulled the index data — the gap isn't the market, it's the contract. We're asking the contract to track the index more tightly through Q3."
2. **"Our margin is already thin."** — "We respect that. The Net-30 ask isn't asking margin — it's asking working-capital terms. The volume-rebate-tier reset isn't asking margin — it's asking us both to share the upside of the committed 6-unit growth. The price-relief ask is targeted at the 6 SKUs where the index data shows a real variance, not at the broadline. We're trying to keep our partnership simple — match the index on the items that have drifted, lock Q3 on protein, and reset the rebate tier with our growth."
3. **"We can't beat the buying group."** — "We're not asking to beat the buying group. We're asking to be priced where we are — a 4-unit committed-growth account with $1.23M annualized spend, in your top 5% by tenure. Restaurant Depot doesn't carry your queso oaxaca or your custom-cut ribeye, and PFG hasn't onboarded our masa SKU. We've been your account for 5 years. The ask is a tracker on index-variance, a Q3 lock, and a Net-30 — none of which is beating a buying group, all of which is matching what your top 5% by tenure should already be running."

## Concession Package (offerable without operational damage)
- Consolidate to 2× weekly delivery (currently 3×) — saves Sysco a ~$180/wk delivery slot, costs us 4 hrs/wk of inventory-management discipline (acceptable)
- 90-day rolling forecast on the top-15 SKUs (currently 30-day) — saves Sysco supply-planning friction, costs us a discipline upgrade we already need
- 24-month exclusivity on the broadline category (we keep PFG and Restaurant Depot as named back-ups; Sysco gets the broadline lock) — extends contract through 2028
- Featured-vendor placement on our menu insert for Q3 (Sysco branded)

## BATNA — Best Alternative To a Negotiated Agreement
- **Performance Food Group (PFG San Antonio)** — Onboarded 2026-02; quoted -3.0% off our top-15 with Net-30 standard; 5-day onboarding for the additional 30% volume; switching cost ~$1.4K (menu print updates, system updates)
- **Restaurant Depot** — Onboarded for cash-and-carry on a 4-SKU fallback (queso oaxaca, ribeye trim, masa, lime); -8% to -12% on those 4 SKUs but no delivery (driver labor cost ~$60/run × 2 runs/wk)
- **Triggered switch:** If Sysco walk-away is accepted (worse than -2.0% + Net-30 + Q3 lock), shift 30% of broadline to PFG starting 2026-06-01 (60-day notice on volume drop to Sysco), and re-bid the full broadline annually starting 2026-08 RFP

## 30-Minute Meeting Agenda
- 0:00–0:02 — Open: "Thanks for the call, T. Reyes. We've prepped a brief; let's stay tight on time. We're not here to fight on margin — we're here to track index and reset rebate." (warm, factual)
- 0:02–0:10 — Data review: walk Spend Map; pause on chicken thigh, ribeye, masa, lime, corn tortilla, yellow onion (the 6 with variance >2.5%)
- 0:10–0:20 — Top 3 asks: (1) -3.4% blended on top-15 + Q3 lock on 3 proteins, (2) Net-30, (3) volume-rebate-tier reset to 1.0% on >$1.2M
- 0:20–0:25 — Objection-handling: have the index data file open, have the BATNA quotes file open
- 0:25–0:30 — Close: written action items + next-step timeline. Opening line: "Let's commit to the Net-30 today and a written response on the SKU price-relief ask by next Friday."

## Post-Call Recap Template
- Sysco committed to: ___
- Sysco to come back on: ___ by [date]
- Cantina Verde committed to: ___
- Next call: [date]
```

### Example 2 — Mid-cycle price-increase pushback (produce specialty house, single-unit fine-dining, low leverage)

```markdown
# Supplier Negotiation Brief — Greenleaf Mid-Cycle Increase Pushback
## Maison Sage (1 unit, Berkeley CA) × Greenleaf Produce
## Meeting: 2026-05-02 9:00 AM PT, in-person at the restaurant; rep: A. Mendez (3-yr tenure)
## Trigger: Greenleaf issued a +6.2% blended increase notice 2026-04-22 effective 2026-05-15; current 12-mo contract auto-renews 2026-08

## Executive Summary
- **Vendor:** Greenleaf Produce (specialty produce broker, San Francisco) | Account #: BR-1147 | 12-week spend: $42,180
- **Top 2 asks:** (1) Cap the increase at +3.0% blended (USDA Specialty Crop terminal index variance is +1.8% trailing 12 wks; +6.2% is +4.4% above index) on the top-8 SKUs that drive 73% of spend; (2) Honor the 12-mo contract through 2026-08 — the increase notice is mid-cycle and the contract carries no escalator clause
- **Leverage rating:** LOW — single-unit account, sub-$200K annual spend, no comparable specialty-produce broker in the East Bay carrying our tier of microgreens / heirloom tomato / sourcing story; switching cost is high and visible (chef has built menu around 4 named farms only Greenleaf curates)
- **Walk-away position:** +4.0% blended cap (split the difference) + 30-day delay on increase to 2026-06-15 + escalator-cap clause added to next contract renewal capping any future mid-cycle increase at index-variance + 1.0%

## Spend Map (Pareto, top 8 SKUs of $42,180 trailing-12-week spend)
| SKU | Pack | 12-wk Qty | 12-wk Spend | Greenleaf Δ | USDA Specialty Index Δ | Variance | Ask |
|---|---|---|---|---|---|---|---|
| Microgreens (sun-prairie / mizuna / shiso blend) | 8 oz clamshell | 240 cs | $7,440 | +7.1% | +2.4% | +4.7% | -4.0% (cap at +3.1%) |
| Heirloom tomato (4-farm rotation) | 5 lb | 380 lb | $4,940 | +5.8% | +3.0% | +2.8% | -2.0% (cap at +3.8%) |
| Romanesco | 12 ct | 60 ct | $1,440 | +8.0% | +1.4% | +6.6% | -5.0% (cap at +3.0%) |
| Padron pepper | 5 lb | 110 lb | $1,650 | +6.5% | +0.8% | +5.7% | -4.0% (cap at +2.5%) |
| Black mission fig (in season) | 5 lb | 80 lb | $2,000 | +4.0% | +2.2% | +1.8% | hold (genuine market) |
| Stone fruit (peach / nectarine / plum) | 25 lb | 320 lb | $4,800 | +5.0% | +3.6% | +1.4% | hold |
| Trumpet mushroom | 5 lb | 110 lb | $4,840 | +9.5% | +1.1% | +8.4% | -6.0% (cap at +3.5%) |
| Local sorrel + nasturtium + chrysanthemum (4-farm) | half-pound | 220 cs | $3,960 | +6.0% | n/a (specialty) | +6.0% est | -4.0% |
| **Top-8 subtotal** | | | **$31,070** | **+6.4% blended** | **+2.1% blended** | **+4.3% variance** | **-3.4% blended → +3.0% net** |

## Contract Gap Table
| Clause | Current | Requested | $ Impact |
|---|---|---|---|
| Mid-cycle escalator | None — but vendor is invoking anyway | Honor the 12-mo contract through 2026-08 | $1.4K (the difference between +3.0% and +6.2% blended over 14 weeks of remaining contract) |
| 2026-08 renewal escalator-cap clause | None | Cap any future mid-cycle increase at "USDA Specialty Crop terminal index variance + 1.0%" with 60-day notice | Hedges future risk |
| Delivery cadence | 3× weekly | hold | n/a |
| Payment terms | Net-15 | hold (Greenleaf gives us best terms in the category already) | n/a |
| Substitution policy on out-of-stock | At rep discretion | Pre-approved sub-list per SKU (chef + rep agree) | Protects menu integrity |

## Leverage Inventory (honest reading)
- Annual spend: $182K — small for Greenleaf
- Tenure: 3 yrs — modest
- Multi-source: NO realistic alternative on the heirloom tomato / microgreens / 4-farm rotation; the specialty story is the menu
- Public profile: chef has been quoted in SF Chronicle and Bay Area Bites naming 4 of Greenleaf's farms by name; switching is a visible decision
- Strategic context: chef is opening a 2nd unit (downtown Oakland) Q4 2026 — 80–110% spend lift if we stay
- **Net leverage: LOW on price (no realistic BATNA); MEDIUM on relationship (the Q4 2nd-unit opening is the real card)**

## Ask Ladder
| Tier | Ask | Target | Expected | Walk-Away | Justification |
|---|---|---|---|---|---|
| Must-have | Cap mid-cycle increase | +3.0% | +4.0% | +6.2% (full vendor ask) | USDA index variance |
| Must-have | 30-day delay on effective date | 2026-06-15 | 2026-05-29 | 2026-05-15 (vendor ask) | Q1 P&L absorption time |
| Should-have | Escalator-cap clause in 2026-08 renewal | Index-variance + 1.0%, 60-day notice | Index-variance + 1.5%, 45-day notice | Index-variance + 2.0%, 30-day notice | Future-risk hedge |
| Should-have | Pre-approved sub-list per SKU | All top-8 | Top-5 | None (current) | Menu integrity |
| Nice-to-have | Q4 2nd-unit launch slotting fee waiver | Full waiver | Half | hold | Spend-lift offer in exchange |
| Nice-to-have | Co-op print on the 2nd-unit menu | Vendor-branded farm callout | Generic farm callout | hold | Marketing exchange |

## Concession Package
- 12-month exclusivity on the specialty-produce category for both units (Maison Sage + Q4 Oakland) → +80% spend lift vs. dual-source
- Co-op print on the 2nd-unit menu featuring "produce by Greenleaf farms" with 4 named farms
- 30-day forecast on the top-8 SKUs (currently 7-day) — helps Greenleaf's farm-side planning
- Two weeks of social-media-post-generator activity featuring Greenleaf farms during the Q4 2nd-unit launch (chef's Instagram has 38K followers)

## BATNA (honest)
- **No realistic alternative on the specialty produce that anchors the menu.** The 4-farm rotation, the heirloom tomato sourcing story, and the microgreen blend are not curated by another East Bay broker. Switching is a 6-month rebuild of the menu identity.
- **Cash-and-carry options:** Berkeley Bowl can supply microgreens and stone fruit at retail (no farm-story); Imperfect Foods cannot meet our quality bar; the Saturday farmers' market gives us heirloom tomato during summer at +20% retail. None of these is a real BATNA.
- **The walk-away is reluctant:** if Greenleaf walks at +6.2% with no concessions, we absorb the increase, eat the margin, and re-bid the next 12-mo contract starting 2026-06 with one of the smaller East Bay specialty brokers (Far West Fungi for mushrooms, Fifth Crow Farm direct for tomatoes, Mountain Bounty Farm direct for microgreens — but multi-vendor procurement on $180K/yr spend is operational drag).

## Meeting Posture (LOW leverage = relationship-led)
- Open: thank A. Mendez for 3 years of partnership; congratulate Greenleaf on the recent Cherry Lake Farms partnership announcement
- Walk Spend Map; pause on Romanesco, Padron, Trumpet (the 3 SKUs with >5% index variance) — these are the data
- Frame the ask as "honor the 12-mo contract through 2026-08, then we re-cut for 2 units in Oakland — let's get the structure right for the bigger spend"
- Lead with the Q4 2nd-unit opening — the real card
- Close with the escalator-cap clause for 2026-08 renewal — the future-risk hedge

## 30-Minute Meeting Agenda
- 0:00–0:03 — Open: thanks + 2nd-unit announcement
- 0:03–0:12 — Data review: USDA Specialty Crop variance vs. Greenleaf delta on the top-8 SKUs
- 0:12–0:22 — Top 2 asks + escalator-cap renewal clause
- 0:22–0:27 — Objection-handling
- 0:27–0:30 — Close: "Let's commit to a +4.0% cap and a 30-day delay today; we'll co-design the 2nd-unit deal in June."

## Post-Call Recap Template
- Greenleaf committed to: ___
- Greenleaf to come back on: ___ by [date]
- Maison Sage committed to: ___
- 2nd-unit pre-deal call: [date]
```

### Example 3 — Direct-from-farm switching analysis (mid-volume protein, 7-unit chain, named BATNA)

```markdown
# Supplier Negotiation Brief — US Foods Protein Switching Analysis
## Smokestack BBQ (7 units, Kansas City + Wichita) × US Foods Kansas City
## Decision: 2026-05-15 — switch 60% of brisket / pork shoulder volume to direct-from-rancher (Cattle-Tracks Coop, Kansas Flint Hills) starting 2026-07-01
## Counterparty pre-conversation: 2026-05-08 with US Foods rep R. Henderson (12-yr tenure)

## Executive Summary
- **Decision frame:** This is not a price negotiation — this is a sourcing-architecture decision. We are not trying to get US Foods to match the rancher price; we are giving US Foods a full-disclosure conversation, a remaining-scope offer (40% of brisket / pork shoulder + 100% of all other categories), and a 60-day transition runway. The brief is the script for that conversation.
- **Vendor:** US Foods Kansas City | Account #: USF-7741 | Annualized spend: $2.1M | Brisket + pork shoulder: $720K (34% of total)
- **The numbers:** Direct-from-rancher landed cost on brisket = $4.20/lb (vs. US Foods $5.35/lb); on pork shoulder = $1.95/lb (vs. $2.40/lb). 60% switch = $186K/yr saved net of cold-truck transportation lease ($14K/yr) and back-haul on wood pellets ($4K/yr offset).
- **Why a partial-switch (60%) not full:** US Foods carries the produce, dairy, paper goods, smallwares, packaging, oil, sauces, and the off-piste cuts (burnt-end-grade trim, smoked sausage, pulled pork salt-and-pepper rubs sourced through US Foods' specialty arm). Direct-from-rancher does not realistically displace that. A 60% switch on the two highest-volume SKUs is the optimal point on the curve.
- **Walk-away from US Foods (low probability):** if US Foods threatens loss-of-tier or category-exclusivity penalty on the remaining 40%, we full-switch the proteins to Cattle-Tracks Coop (40% upside on the savings) + Restaurant Depot fallback on the off-piste cuts and re-bid the rest of the broadline 2026-Q4

## Sourcing-Architecture Comparison
| Category | Current Supplier | New Supplier | Annual Spend | Annual Saved | Risk |
|---|---|---|---|---|---|
| Brisket (60%) | US Foods | Cattle-Tracks Coop direct | $432K → $246K | $186K | Cold-chain logistics; supply-disruption (single-source) |
| Brisket (40%) | US Foods | hold | $288K | n/a | n/a |
| Pork shoulder (60%) | US Foods | Cattle-Tracks Coop direct | $108K → $61K | $47K | Same as brisket |
| Pork shoulder (40%) | US Foods | hold | $72K | n/a | n/a |
| Smoked sausage | US Foods | hold | $192K | n/a | US Foods specialty arm |
| Pulled-pork rubs / oil / sauce | US Foods | hold | $108K | n/a | n/a |
| Burnt-end trim | US Foods | hold | $36K | n/a | n/a |
| Produce | US Foods | hold | $324K | n/a | n/a |
| Dairy | US Foods | hold | $180K | n/a | n/a |
| Paper / smallwares / oil | US Foods | hold | $360K | n/a | n/a |
| **Net** | | | **$2.1M → $1.69M** | **$186K - $14K (cold truck) - $4K (back-haul) = ~$168K net** | |

## Switching Cost & Transition Plan
| Item | Cost | Timeline |
|---|---|---|
| Cold-truck lease (refrigerated 2-pallet, weekly Cattle-Tracks → Smokestack commissary) | $14K/yr | Lease signed Q2 |
| Cold-truck driver (1 FTE, route 4 hrs × 1 day/wk) | $22K/yr | Existing fleet driver re-routed |
| Wood-pellet back-haul agreement (Cattle-Tracks delivers brisket; we back-haul wood pellets from a partner mill to KC; offsets $4K of trucking) | -$4K/yr | Agreement signed Q2 |
| Cattle-Tracks Coop minimum-order commitment (4,800 lb brisket / 2,400 lb pork shoulder per month, lot-traceable, USDA HACCP-cert) | Locked Q2 | Q2 sign |
| HACCP plan amendment (single-source rancher requires lot-tracking SOP update) | Owner+chef, 8 hrs | Q2 |
| Internal lineup re-train (yields differ slightly; rancher cuts run 1.5% leaner trim) | 90 min × 7 GMs | Jul 1 |
| Backup-rancher onboarded (Konza Cattle, Kansas Flint Hills) for supply-disruption contingency | Q2 sign at 10% volume | Apr–May |

## US Foods Conversation — Pre-Call Frame
**The conversation is honest and proactive.** US Foods is a 12-year partner. We are not switching because of a price grievance — we are switching because the direct-rancher economics on the two highest-volume SKUs are too strong to ignore at our scale. We are giving US Foods 60 days notice and offering 100% of the other categories on a 24-month exclusivity. The conversation is structured to:
1. Lead with the headline (we are taking 60% of brisket + pork shoulder direct on Jul 1)
2. Walk the math (cold-chain landed cost $4.20/lb vs. $5.35/lb, 60% volume = $186K saved gross)
3. Honor the relationship (24-month exclusivity offer on all other categories, 100% of broadline minus the protein direct-pull)
4. Pre-empt objections (NOT a price grievance; NOT a relationship break; YES open to a US Foods Premium-Beef-Coop counter-offer if it lands within 7% of the rancher price)
5. Set the runway (60-day transition; full payment of any minimum-order commitment current; cold-truck lease independent of US Foods relationship)

## Possible US Foods Counter-Offers (handle each)
1. **"We can match the rancher price."** — "We respect the offer. The rancher economics include the lot-traceable single-farm story we're using on the menu — that's the brand-promise we built around the brisket-of-record. The price is part of it but not all of it. We're glad to look at the counter, but the math has to land within 7% of $4.20/lb landed AND include lot-traceable single-farm sourcing."
2. **"You'll lose tier on volume rebate / co-op marketing fund."** — "We've modeled it. The volume-rebate-tier loss is approximately $9K/yr; the co-op marketing fund loss is approximately $4K/yr. The net savings is still ~$155K/yr after both. We'd rather hold those programs and find a structure where the protein direct-pull doesn't trigger them — for example, structuring the direct-pull as a side-letter to the master agreement rather than a category-cut."
3. **"You'll forfeit category-exclusivity protection."** — "We'd like to keep the exclusivity on every other category — produce, dairy, paper, smallwares, oil, sauces, smoked sausage, off-piste protein. Brisket and pork shoulder direct-pull is a one-time category exception. The 24-month exclusivity offer on the remaining 9 categories is the bigger deal economically."

## BATNA Detail
- **Cattle-Tracks Coop (Kansas Flint Hills, USDA HACCP-cert)** — quoted $4.20/lb brisket / $1.95/lb pork shoulder landed at our KC commissary, weekly delivery, lot-traceable to single-farm, 4,800-lb / 2,400-lb monthly minimum, 24-mo agreement Q2 signed
- **Konza Cattle (backup, Kansas Flint Hills)** — onboarded at 10% volume Q2; quoted $4.30/lb brisket / $2.00/lb pork shoulder; supply-disruption contingency; not relationship-displacing to Cattle-Tracks
- **Restaurant Depot (cash-and-carry fallback for the off-piste cuts only)** — covered if US Foods walks the broadline

## 30-Minute Meeting Agenda (with R. Henderson)
- 0:00–0:03 — Open: 12-yr relationship; thanks; structure of today's call
- 0:03–0:08 — Headline: "Effective July 1, we are moving 60% of brisket and pork shoulder volume direct to Cattle-Tracks Coop. We wanted you to hear this from us in person, 60 days out."
- 0:08–0:18 — The math + the why: lot-traceable single-farm story + the $186K landed-cost delta
- 0:18–0:24 — The offer: 24-month exclusivity on all other categories; payment of any current minimum-commitment in full
- 0:24–0:28 — Open the floor: "Is there a Premium-Beef-Coop structure or a side-letter that would change the conversation? We're open."
- 0:28–0:30 — Close: written next-steps, follow-up call within 7 days

## Post-Call Recap Template
- US Foods committed to: ___
- US Foods to counter-offer by: ___
- Smokestack committed to: ___
- 60-day transition timeline: ___
- 24-month exclusivity offer document drafted by: [date]
```
