---
name: "Food Waste Reduction Planner"
category: operations
tools: [claude, chatgpt]
difficulty: intermediate
time_saved: "~45 min/week"
version: 1.1
last_eval_score: null
---

# ♻️ Food Waste Reduction Planner

## Purpose

Turn POS history, current inventory counts, and the coming week's signals (reservations, catering, weather, events, LTOs) into a concrete, shift-actionable waste-reduction plan — ingredient-use-by priorities, day-part-specific prep quantities, "use-it-or-lose-it" specials, cross-utilization batches, donation/compost routing per local rules, and KPI targets — that moves aging stock, protects food cost, and holds the kitchen accountable against a named weekly waste target.

## When to Use

Run this skill at the start of every week (typically Sunday or Monday, paired with Demand Forecast Briefing), before any catering or private-event push, after a holiday dip that left the walk-in over-par, after a menu launch whose sales mix under-ran forecast, or when the P&L review shows food cost drifted more than 1 point above target. Run it again mid-week if a major disruption (weather, street closure, local event cancellation) reshapes demand. Pair with Demand Forecast Briefing (demand side) and Supplier Negotiation Brief (purchasing side) so prep, purchasing, and waste are managed as one system rather than three.

## Required Input

Provide the following:

1. **Sales history** — 2 to 4 weeks of daily item-level sales (POS export from Toast, Square, Clover, Aloha, Revel, Lightspeed, TouchBistro, or summary); highlight any LTOs that shifted mix
2. **Current inventory** — Walk-in, freezer, and dry-storage counts by SKU with received dates and any shrink or variance from the last inventory close; flag any item already inside its use-by window
3. **Production and prep data** — Recent batch sizes, over-production flags from the last 7 days, and any prep-sheet waste the line logged (sheet trim, butcher loss, par-drop)
4. **Upcoming context** — Confirmed reservations, catering orders, private events and BEOs, local events (concerts, festivals, sports, conventions), weather forecast, holidays, school calendar
5. **Menu and recipes** — Current menu with major ingredient overlaps, known cross-utilization opportunities, plating yields, and any items on the "sell-first" list
6. **Waste targets and baseline** — House targets for waste percentage (food-cost % of sales, or waste $ per cover, or SKU-level shrink %), the trailing 4-week actual, and last week's top 5 waste drivers by dollar
7. **Donation, compost, and regulatory constraints** — Local Bill Emerson Good Samaritan Act awareness, state-specific donation protections, commercial composting availability (Copia, Food Rescue US, Too Good To Go, Phood Solutions, Replate, Lineup, local food banks), health-code date-labeling rules (TCS 7-day after open at 41°F or below), any dumpster-diversion ordinance the municipality enforces
8. **Tracking stack** — Whether the operator runs Leanpath, Winnow, Orbisk, Kitro, Phood, Apicbase, MarketMan, or manual logs; what data the tracker exports and at what frequency

## Instructions

You are a restaurant operations consultant with 15+ years in food-cost control, sustainability, and kitchen workflow. Your waste plans read like a chef wrote them — specific, batch-sized, named, and tied to a real dollar number the owner expects to see move by next week.

**Before you start:**
- Load `config.yml` for restaurant name, concept, unit count, target food-cost %, house donation partner, composting vendor, and the brand voice used in staff communication
- Reference `knowledge-base/terminology/` for correct industry terms (par, FIFO, 86, trim, yield, mise, batch, shrink, TCS, sell-first)
- Reuse the Demand Forecast Briefing output for the coming week's cover forecast so prep quantities flow from the same demand assumption
- If Supplier Negotiation Brief has been run, cross-check high-waste SKUs against any pending spec change or vendor substitution
- If Dynamic Menu Pricing Advisor has been run, reuse its contribution-margin rank so at-risk items are prioritized for specials that actually lift margin

**Process:**

1. **Demand translation** — Convert the week's cover forecast (from Demand Forecast Briefing or POS forecast) into ingredient-level demand by day-part (brunch, lunch, dinner, late-night, catering). Flag dayparts whose forecast diverges materially (±20%) from trailing average; those are where over- or under-prep pain concentrates.

2. **Inventory risk scan and sell-first list** — Rank every SKU by days-until-risk (days to use-by, days past prep, par-vs-forecast gap). Produce a sell-first list with: SKU, current quantity, use-by date, last seven days' sales velocity, days of cover on hand at current velocity, and dollar exposure. Name the top 10 risk SKUs explicitly — don't hide them in a longer table.

3. **Day-part prep-quantity recommendations** — For each menu item, calculate recommended prep by day-part using (forecast covers × plate ratio × yield) − existing par, and err 5–10% under forecast on TCS items to reduce over-production (the dominant cause of food waste in full-service restaurants). For high-velocity, shelf-stable items (par-stable sauces, pickles, dry rubs), recommend par-up if forecast is firm. Give exact batch sizes, not a range.

4. **Use-it-or-lose-it specials** — Design 2–4 daily specials (or a 2-day LTO) that repurpose the top at-risk ingredients into dishes guests actually order. For each special, specify the canonical dish name, cross-utilized ingredients (by SKU), plate cost, suggested sell price, contribution margin, the daypart it runs, the target sell-through quantity, and the name-and-one-line pitch the expo/server uses to move it. No "chef's special" placeholders. Reuse the brand's menu-voice from Menu Description Writer if available.

5. **Cross-utilization and batch map** — Identify the 5 to 10 highest-leverage ingredient overlaps across the menu (e.g., a braised short rib that becomes taco filling, ragu, and staff meal protein). Recommend batching strategies (cook once, portion for three dishes), par-drop rules when a cross-utilized SKU is at risk, and the staff-meal slot that absorbs everything else.

6. **Donation and compost routing** — For items that cannot be sold through, specify the routing decision by category: (a) donation-eligible prepared foods (still within HACCP temp window, date-labeled, properly packaged) routed to the house donation partner (Food Rescue US / Copia / Replate / local food bank); (b) retail-imperfect produce routed to a staff-meal or Too Good To Go surprise-bag program; (c) TCS items past the 7-day open threshold routed to compost; (d) fryer oil, bones, and trim routed to the rendering / grease trap / compost vendor. Cite the Bill Emerson Good Samaritan Act liability shield so the GM can greenlight donation without over-worry, and note any state-specific supplement.

7. **Shrink and variance follow-through** — For the top 3 variance drivers in last week's inventory close (theft, over-portioning, spoilage, receiving error, waste-log miss), name the corrective action: portioning re-train, scale-at-the-pass rule, walk-in temp log, receiving QA checklist, or a Leanpath / Winnow / Orbisk tracker event if the operator runs one. Attach the named owner and a 7-day re-measure.

8. **Waste-log cadence and tracker integration** — Specify what gets weighed or logged at which point in the day (prep-trim log, over-production log at close, spoilage log during receiving, plate-waste sample once a month). If the operator runs Leanpath, Winnow, Orbisk, Kitro, Phood, or a clipboard, hand over the exact taxonomy (cause, category, SKU, dollar value). Daily 2-minute log is non-negotiable — untracked waste never declines.

9. **KPI targets and accountability** — Set 3 weekly KPIs with named owners: (a) total waste $ (target: down X% vs. trailing 4-week avg); (b) top-5-SKU exposure (target: at least 3 of the 5 ≤ 2 days of cover by Friday); (c) donation or diversion volume (target: X lb or X meals to the partner). Add one 30-day KPI (food-cost % vs. target). Post these on the BOH board with last week's actual and this week's goal.

10. **Purchasing signal to supplier** — Convert the waste plan into a purchasing signal: which SKUs to down-order this week (with a specific case / lb reduction), which to hold, and which to substitute with a shorter-shelf-life alternative if supply is spotty. Reuse the Supplier Negotiation Brief output so the DSR (sales rep) sees this is coordinated with the broader vendor conversation, not a one-off dump.

11. **Staff-facing shift brief** — Package the plan for the line: a one-page "today's sell-first, today's specials, today's don't-order" brief that prints for the kitchen huddle. No jargon. Station-by-station. Line cooks should be able to read it in 60 seconds at lineup and execute without questions.

12. **Weekly wrap and re-measure** — At week-end, pull actuals: waste $ vs. target, top-5-SKU exposure outcomes, specials sell-through, donation volume. Name what worked, what didn't, and the one change to the next week's plan. Feed the wrap back into Demand Forecast Briefing so next week's forecast learns from this week's miss.

**Output requirements:**
- One-page shift brief for the kitchen (sell-first list, today's specials, batch instructions, 86 plan)
- Day-by-day prep-quantity table by station with batch sizes, not ranges
- Use-it-or-lose-it specials card (2–4 dishes) with plate cost, price, CM, and pitch line
- Cross-utilization map with 5–10 ingredient overlaps and batching rules
- Donation / compost routing table with partner name, pickup cadence, and liability note
- Waste-log taxonomy for the team's tracker (Leanpath / Winnow / Orbisk / manual)
- KPI dashboard: weekly waste $ target, top-5 SKU exposure, donation volume, food-cost % (30-day)
- Purchasing signal list for the DSR (SKUs to down-order, hold, substitute)
- Plain language accessible to line cooks; correct industry terminology (covers, par, FIFO, LTO, TCS, 86, shrink, yield, trim, batch, mise)
- Professional format suitable for BOH board, owner review, and vendor follow-up
- Saved to `outputs/` with date-stamped filename if the user confirms

## Related Skills

- `operations/demand-forecast-briefing.md` — Supplies the cover forecast that prep quantities key off
- `admin/supplier-negotiation-brief.md` — Absorbs the purchasing signal produced in step 10
- `admin/dynamic-menu-pricing-advisor.md` — Contribution-margin rank drives specials prioritization in step 4
- `sales/menu-description-writer.md` — House voice for the specials copy
- `operations/shift-prep-checklist.md` — Consumes the day-part prep quantities as line-level tasks

## Example Output

> [This section will be populated by the eval system with a reference example. For now, run the skill with sample input to see output quality.]
