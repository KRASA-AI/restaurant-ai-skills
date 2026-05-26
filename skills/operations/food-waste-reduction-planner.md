---
name: "Food Waste Reduction Planner"
category: operations
tools: [claude, chatgpt]
difficulty: intermediate
time_saved: "~45 min/week"
version: 1.3
last_eval_score: 9.00
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

### Example 1 — Routine weekly plan, full-service neighborhood concept

**Input:**
- Concept: Cedar & Vine, 75-seat seasonal-American, Portland OR; Toast POS
- Sales history: trailing 4 weeks averaging 470 covers / week, dinner-heavy with Sunday brunch
- Cover forecast (from Demand Forecast Briefing): 480 covers / week (Tue 50 / Wed 55 / Thu 70 / Fri 95 / Sat 130 / Sun 80)
- Inventory close 2026-05-04: walk-in over-par on heirloom tomatoes (12 lb, 4 days to use-by), shoulder cuts of pork (18 lb, 5 days), burrata (8 ea, 3 days); freezer fine; dry storage fine
- Last week's top-5 waste $ drivers: tomato trim (over-portioned at the burrata-tomato app station), pork shoulder spoilage (one case received warm 4/29), bread end-cuts, lettuce butt (over-trim), butcher trim
- Tracking: Leanpath waste-station scale at the prep table, daily 2-min log
- Donation partner: Urban Gleaners (PDX); compost vendor: Recology Composting (commercial)
- Targets: food cost target 29.5%; trailing 4-week actual 30.8% (+1.3 pts over target — recent commodity move on tomato + dairy)
- Bill Emerson Good Samaritan Act + Oregon supplement (HB 2541) liability shield active

**Output — Week of 2026-05-04:**

**One-page kitchen shift brief (printed for Tuesday huddle):**

```
SELL-FIRST (Tuesday → Friday, then escalate):
  1. Heirloom tomato (12 lb)  → days-to-risk: 4 → goal: 100% absorbed by Fri close
  2. Pork shoulder (18 lb)    → days-to-risk: 5 → goal: 100% absorbed by Sat close
  3. Burrata (8 ea)           → days-to-risk: 3 → goal: 100% absorbed by Thu close

TODAY'S SPECIALS (sell-first hooks):
  • Heirloom-Tomato + Burrata Crostini ($12, runs Tue–Thu lunch + dinner) — uses 2 oz tomato + ½ ball burrata each, target 24 portions, plate cost $3.10, CM 74%
  • Pork Carnitas Tacos ($16, 3-taco plate, runs Wed–Sat dinner) — uses 4 oz braised pork shoulder each, target 18 plates Wed / 22 Thu / 28 Fri / 32 Sat, plate cost $3.85, CM 76%
  • Tomato-Watermelon Gazpacho ($9 starter, runs Sat–Sun lunch) — uses 4 oz tomato + 2 oz watermelon (in-stock), target 14 bowls, plate cost $2.20, CM 76%

DON'T-ORDER LIST (purchasing signal to DSR for Mon 5/11 truck):
  • Tomato — drop next case order (have 12 lb on hand, plus 6 lb on Friday's small-vendor delivery)
  • Burrata — drop to 6 ea (from 12 ea standing)
  • Pork shoulder — skip this week (have enough through Saturday close)

86 / SUBSTITUTION PLAN:
  • If burrata sells through by Thursday close → 86 the burrata-tomato app, sub heirloom-tomato bruschetta with goat cheese
  • If pork shoulder runs out before Saturday close → 86 carnitas tacos, sub Korean-style braised short rib (we have 22 lb on hand, on par)

STAFF MEAL SLOTS (use-up):
  • Tue staff meal: tomato-pork-shoulder ragu over polenta (uses ~3 lb tomato + ~4 lb pork shoulder)
  • Sun staff meal (after brunch): bread pudding from end-cuts + pastry trim
```

**Day-by-day prep table (Tuesday — Diego's prep sheet):**

| Station | Item | Standard par | Recommended par | Batch instructions |
|---|---|---|---|---|
| Cold pantry | Burrata-tomato app prep | 24 ea | **30 ea (special-driven)** | Pre-portion 2 oz tomato per app; sell-first leveling on tomato |
| Hot line | Pork carnitas | 0 (not on menu) | **18 portions (special)** | Braise tonight Wed AM in advance, 4 oz portions, cooled overnight |
| Garde manger | Salad mise | 1.5 hotel pan | 1.3 hotel pan (-13%) | Trim economics — under-prep 5–10% on TCS items |
| Bread program | Bread pudding base (Sun staff meal) | n/a | 1 hotel pan | Cube end-cuts, custard tomorrow |
| Bar (no impact) | — | — | — | — |

**Cross-utilization map (5 highest-leverage overlaps this week):**

| SKU | Dishes it crosses into | Batch size | Par-drop trigger |
|---|---|---|---|
| Heirloom tomato | Burrata app, Carnitas pico, Gazpacho LTO, Sat staff meal ragù | 5 lb prep batch | If tomato qty < 4 lb at Thu close → 86 gazpacho |
| Pork shoulder | Carnitas, Sun brunch hash, staff-meal ragù | 8 lb braise batch (twice this week) | If qty < 4 lb at Sat AM → 86 brunch hash, run a chorizo sub |
| Bread end-cuts | Bread pudding (staff meal), croutons (Caesar), French toast (Sun brunch), bread crumbs (meatballs) | Daily | Cube and store same day ; cap at 2 days |
| Pastry trim | Bread pudding, granola crunch (yogurt parfait) | Weekly | Container in walk-in, dated |
| Beet greens / radish tops | Pesto (staff meal), garnish (cold pantry) | Weekly | Cap at 4 days |

**Donation / compost routing this week:**

| Category | Routing | Pickup cadence | Liability note |
|---|---|---|---|
| Donation-eligible prepared foods (still in HACCP window, date-labeled) | Urban Gleaners — pickup Wed 4 PM and Sun 11 AM | 2× / week | Bill Emerson Good Samaritan Act + Oregon HB 2541 liability shield active; donations made in good faith are protected from civil and criminal liability for the donor |
| Retail-imperfect produce (tomato seconds from butcher trim) | Staff meal (Sat) → if surplus, Too Good To Go surprise bag posted Saturday 6 PM | Saturday | n/a |
| TCS items past 7-day threshold | Compost (Recology) — back-of-house bin | Daily | n/a |
| Fryer oil / trim / bones | Mahoney (bones), DAR PRO (oil) | Weekly | n/a |

**KPI dashboard:**

| KPI | Target | Last week | This week goal | Owner |
|---|---|---|---|---|
| Total waste $ | down 5% vs. trailing-4-wk avg ($412) | $437 | ≤ $391 | Diego |
| Top-5-SKU exposure | ≥ 3 of 5 at ≤ 2 days of cover by Friday | 2 of 5 | ≥ 3 of 5 | Diego |
| Donation volume | 12 meals to Urban Gleaners | 9 | ≥ 12 | Lina (prep) |
| Food-cost % (30-day) | 29.5% | 30.8% | trend down to 30.4% by 30-day re-measure | Maria + Reyes |

**Variance follow-through (last week's top-3 drivers):**
- Tomato trim over-portioning at the burrata-tomato station — corrective: 2-oz portion-scale at the pass; spec re-train on Tue AM (Diego owns; verify with all AM cooks by Thursday)
- Pork shoulder spoilage from one warm-receiving incident — corrective: temperature-at-receiving log re-trained; Sysco DSR notified per Supplier Negotiation Brief format (Maria owns; closed in supplier QBR notes)
- Bread end-cut waste — corrective: bread pudding LTO and Caesar crouton run absorb; no further intervention needed

**Purchasing signal to DSR (sent Monday 4 PM):**

```
To: Jordan Reyes, Sysco DSR
Subject: 5/11 truck — small adjustments (sell-first cycle)

  Tomato (heirloom): drop next case (sufficient on hand)
  Burrata: 6 ea (down from 12 ea standing)
  Pork shoulder: skip this week
  All else: standing par

   — Maria, GM
```

**Re-measure scheduled:** Sunday 5/10 close — Lina pulls Leanpath log, Diego scores against the targets above. Feed wrap into next week's Demand Forecast Briefing accuracy review.

---

### Example 2 — Post-LTO over-stock recovery (LTO under-ran forecast by 40%)

**Input:**
- Concept: Cantina Verde, 110-seat Tex-Mex, Austin TX (Square POS)
- LTO: Birria Ramen Cinco-de-Mayo crossover, ran 5/1 – 5/5; forecast 240 portions over 5 days; actual 144 portions (60% sell-through, −40% vs. forecast)
- Resulting over-stock at 5/6 close: 22 lb braised birria (frozen-eligible, 6 mo; current state: 4 days in walk-in, 3 more days TCS-fresh window), 14 lb fresh ramen noodles (sealed cryo-vac, 3 days), 8 qt birria consommé (frozen-eligible)
- Cover forecast for week of 5/11: 720 covers (no event lift, baseline week)
- Tracking: manual log + MarketMan POs
- Donation partner: Central Texas Food Bank (already onboarded)
- Targets: food cost target 28%; the LTO drove margin ~+1.2 pts on the 5/1–5/5 window but the under-run wipes the gain unless the leftover is absorbed

**Output — Recovery plan, week of 5/11:**

**Recovery decision tree (used at the close on 5/6):**

```
22 lb birria → split:
  • 12 lb → freeze immediately (frozen-eligible, 6-mo TCS rule, vacuum-seal in 4-lb portions)
  • 10 lb → run as a 2-day "Birria Quesadilla" feature special 5/8 + 5/9 (lunch + dinner, $14, 4 oz birria + 2 oz cheese in flour tortilla, target 36 portions)

14 lb fresh ramen noodles → 3-day sell-through window:
  • 5 lb → staff meal (Tuesday and Wednesday family meal — birria ramen with the broken portions)
  • 9 lb → run as a "Birria Ramen Encore" $13 lunch-only special 5/7 only (use the 8 qt consommé, target 24 portions; price $2 below the LTO to move volume)
  • Anything beyond 5/7 close → cannot freeze (texture); compost

8 qt consommé → fully absorbed by the 5/7 ramen encore + frozen for July menu development R&D
```

**Daily specials card:**

| Day | Special | Plate cost | Sell price | CM | Target qty | Pitch line for servers/expo |
|---|---|---|---|---|---|---|
| Wed 5/7 (lunch) | Birria Ramen Encore | $3.85 | $13 | 70% | 24 portions | "Last call on the Cinco crossover — chef brought the broth back for one lunch" |
| Thu 5/8 | Birria Quesadilla | $3.20 | $14 | 77% | 18 (12 lunch + 6 dinner) | "Slow-braised birria, smoked-cheddar quesadilla, crispy on the comal" |
| Fri 5/9 | Birria Quesadilla | $3.20 | $14 | 77% | 18 | Same |

**Cross-utilization map:**

| SKU | Dish absorbing | Window |
|---|---|---|
| Birria (10 lb walk-in) | Quesadilla feature 5/8 + 5/9; staff meals 5/7 + 5/8 if surplus | 3 days |
| Birria (12 lb frozen) | Future LTO R&D (planned: birria nachos for July 4 weekend); frozen-cold with 6-mo TCS rule | 6 mo |
| Consommé (8 qt) | Ramen Encore 5/7 (4 qt) + frozen for July R&D (4 qt) | absorbed |
| Fresh ramen noodles (14 lb) | Ramen Encore (9 lb) + staff meal (5 lb) | 3 days |
| Birria-tinted cooking liquid (top of the braise) | Bar program — birria-broth Bloody Mary feature 5/9–5/10 brunch (test of brunch-bar tie-in) | 2 days |

**Donation routing:**
- No donation this week — all leftovers are absorbed via specials, staff meals, freeze, or planned future R&D
- Compost: only the noodle scraps from the 5/7 ramen prep over-trim; estimated < 1 lb

**KPI re-measure:**

| KPI | Target | Status |
|---|---|---|
| 100% of birria absorbed (sold + frozen + staff meal) | Yes / No | TBD by 5/9 close |
| Recovery special CM ≥ 70% | 70% | targets meet (76% / 70%) |
| LTO net margin after recovery | break-even or better vs. forecast | TBD; compare 5/11 close against the 5/1–5/5 forecast |

**Lesson capture (feed back to Demand Forecast Briefing):**
- LTO forecast accuracy: −40%. Pattern: Cinco-week birria-ramen crossover was double-counted in the forecast — the Demand Forecast Briefing assumed birria fans would order birria ramen, AND ramen fans would order birria ramen — but the actual mix showed a cannibalization of carnitas tacos and a softer-than-expected pull from the ramen-base audience.
- Action item: in the next mash-up LTO, model cannibalization explicitly (subtract from the cannibalized item's forecast) and forecast 25% under the optimistic case for first-time crossover items.
- Owner: Erica (GM) + Reyes (chef) — flagged in Tuesday weekly KPI review.

**Purchasing signal to DSR:**
- Drop next birria-cut order (have 12 lb frozen for July); skip ramen-noodle order entirely for the next 2 weeks.
- Hold consommé-grade beef bone supply standing par; the bar's birria-broth Bloody Mary test will set whether to keep that line live.

---

### Example 3 — Mid-week disruption (festival cancellation reshapes Saturday demand)

**Input:**
- Concept: Roja Bowls, 60-seat fast-casual, Cambridge MA (Toast POS)
- Original Saturday forecast (issued Sunday): 220 covers, anchored on the 1.4M-attendance Cambridge Spring Music Festival running 5/9–5/10 (Charles River Lawn, two-blocks away)
- Disruption: Wednesday 5/7 4 PM — festival cancelled by city order due to severe-weather forecast (high wind + lightning risk Sat afternoon). Festival announces refunds; foot traffic now expected at near-zero on Saturday afternoon.
- Revised Saturday forecast: 95 covers (baseline rainy-Saturday level, −57% vs. original)
- Inventory at Wed 5/7 5 PM: walk-in over-par on bowls protein (32 lb chicken thigh marinated for the festival surge, 6 lb tofu, 14 lb saag paneer base); patio-program over-prep on cold-beverage SKUs (40 cans of canned cold-brew, 24 bottled lemonade); produce over-par (24 lb mixed greens, 18 lb cilantro, 12 lb mint)
- Targets: food cost 27%; festival week was forecast at 26% on volume

**Output — Mid-week pivot, Wednesday 5/7 5:30 PM:**

**60-second decision (issued at the Wednesday close huddle):**

```
DEMAND PIVOT: Saturday 5/9 = 95 covers (rainy Saturday baseline), not 220.
ROOT: Festival cancelled by city order.
IMMEDIATE ACTIONS:
  1. Cancel Saturday on-call hires (2 servers + 1 line cook) — call tonight,
     pay 3-hr predictability premium (Cambridge does not have a predictive-
     scheduling ordinance but house policy mirrors Boston's; 3 hrs × $20
     blended = $180 budgeted)
  2. Pull the 32 lb chicken thigh marinated for the surge → freeze 18 lb
     (vacuum-seal, dated 5/7), run 14 lb as a Friday + Saturday special
  3. Cancel Friday's 5/8 chicken-thigh standing order with vendor (PFG Boston)
     — phone the DSR before 6 PM (cutoff)
  4. Patio cold-beverage program: hold; rain forecast does not impact a
     covered patio. SKUs hold.
```

**Saturday menu adjustment:**

| Item | Original Saturday plan | Revised | Reason |
|---|---|---|---|
| Tandoori-chicken bowl | par 80 portions | par 35 | volume drop |
| Chicken-thigh special (2-day, Fri + Sat) | n/a | run @ $13 (vs. menu $15), 4 oz thigh, target 22 Fri + 18 Sat | use-up of marinated thigh that can't freeze marinated past 48 hr |
| Saag paneer bowl | par 30 | par 18 | volume drop |
| Tofu bowl | par 22 | par 12 | volume drop |
| Cold-brew on tap | hold | hold | weather-resilient |

**Cross-utilization (Saturday after the special):**
- Any thigh remaining at Saturday close → Sunday family-meal chicken curry (over-rice; absorbs ~6 lb if needed)
- Mint surplus (12 lb) → mint chutney (8 lb consumed; 4 lb to staff meal)
- Cilantro surplus (18 lb) → green chutney (10 lb consumed; 8 lb to staff meal + freeze)
- Mixed greens (24 lb) → 14 lb absorbed across normal salad par; 10 lb staff meal salad through Sunday
- Saag base (14 lb) → staff meal (Wed–Sat) + freezable in 2-lb portions (4 lb), the rest (4 lb) compost if no movement by Saturday close

**Donation:**
- Wednesday 5/7 close: 6 lb cooked tofu cubes (cooked for festival surge, no freeze) → Greater Boston Food Bank pickup Thursday 11 AM (driver pre-confirmed; donation pickup is twice-weekly Mon + Thu, this is a routine slot)
- Saturday close (if needed): any prepared bowl base in HACCP window → same Thursday-cycle slot for Monday pickup
- Liability shield: Bill Emerson Good Samaritan Act + MA Chapter 94 §328 liability shield (state supplement)

**Compost:**
- Trim & process scrap as normal; compost vendor (Black Earth Compost, MA) routine pickup Thursday 6 AM
- No special ad-hoc pickup needed; regular cadence covers the swing

**Vendor pivot (calls before 6 PM Wednesday):**

| Vendor | Action | Owner | Window |
|---|---|---|---|
| PFG Boston (chicken thigh) | Cancel Friday order entirely | GM | by 5/7 6 PM (cutoff) |
| PFG Boston (paneer) | Drop 1 case from Friday order | GM | same call |
| Russo Produce (greens, cilantro, mint) | Drop Friday order (sufficient on hand) | GM | by 5/7 6 PM |
| Beverage | Hold standing par | n/a | n/a |
| Compost (Black Earth) | No change | n/a | n/a |
| Donation (Greater Boston Food Bank) | Add Thursday 11 AM pickup, 6 lb tofu | Lina | text by 5/7 7 PM |

**Predictability-pay budget for Saturday cancellations:**
- 2 servers + 1 line cook × 3 hrs × $20 blended = $180 — paid out next pay cycle
- House-policy compliance log filed in `outputs/schedule-change-log/2026-05-07-festival-cancel.md`

**KPI revision:**

| KPI | Original Sat target | Revised Sat target | This week goal |
|---|---|---|---|
| Cover volume | 220 | 95 | meet revised |
| Food-cost % | 26% (volume-based) | 27.8% (back to baseline + drag from absorbed marinated thigh) | hold ≤ 28% |
| Waste $ | $50 (festival surge usually drives some) | $145 (absorption-driven, mostly marinated thigh and prepared tofu) | ≤ $145 |
| Donation volume | 0 | 6 lb tofu | meet |

**Lesson capture:**
- Festival-anchored forecast carries a high-magnitude weather-cancellation risk. For the next event-anchored forecast (Boston Calling 2026 — 5/22–5/24), build a Wednesday-of-event-week trigger: if 7-day NOAA forecast shows > 60% cancellation-risk weather, hold the week's purchasing on a 50/50 split (50% of festival surge, 50% of baseline) and decide on Wednesday 4 PM rather than committing the full surge order on Sunday.
- Owner: Maya (GM) + Diego (chef) — feed into Demand Forecast Briefing methodology for event-anchored weekends.

---

**Severity-gate / escalation tags:** Each example flags routine actions. If a single mid-week pivot would push food-cost % above 30% for the trailing 4 weeks, or if donation volume drops below 60% of last month's average two weeks running, escalate to the owner before publication of the next plan.

---

### Example 4 — Multi-unit World Cup 2026 host-city surge prep, NRA Show 2026 vendor-stack anchored (Atlanta 4-unit Latin-Caribbean concept, R365 AI + Crunchtime AI + Leanpath integration)

**Input:**
- Concept: Brasa & Bahia, 4-unit Latin-Caribbean fast-casual (Atlanta Midtown / Buckhead / Decatur / East Atlanta); Toast POS + R365 AI (GA, deployed 2026-05-15 in the post-NRA Show 2026 window after the R365 AI launch on 2026-05-12) + Crunchtime AI Forecasting + Leanpath waste tracker on prep tables
- Operator-decision context: Today is 2026-05-26 → World Cup 2026 kickoff is in 16 days (2026-06-11). Atlanta is a confirmed host city — Mercedes-Benz Stadium runs 8 matches in the group + R32 + R16 windows, including 2 Brazil matches (heavy PT-fan visitation expected) and 1 Mexico match. Area-GM Maria Restrepo just returned from NRA Show 2026 (Chicago, May 16–19) where she spec'd the Crunchtime AI Forecasting + R365 AI bundle at booth #6027 and Leanpath's new SKU-level event-forecast overlay at booth #4842
- Sales history: trailing 4 weeks averaging 1,820 covers / week across the 4 units (Midtown 580 / Buckhead 510 / Decatur 380 / East Atlanta 350); dinner-heavy with weekend brunch
- Cover forecast (Crunchtime AI Forecasting with the World Cup 2026 match-overlay model R365 AI co-produced post-launch): 2,640 covers / week during group-stage match weeks (6/11–7/3) — +45% vs. trailing 4-wk, concentrated on match days (Brazil dates 6/19 and 6/24 at MBS expect +85% vs. baseline; Mexico date 6/16 +70%; non-LATAM home matches +30%)
- Inventory close 2026-05-25: walk-ins on par across 4 units; ahead-of-surge purchasing already staged for the 6/11–6/17 window (picanha 80 lb across 4 units; pão de queijo dough 40 lb; black beans 30 lb prepped; chicken thigh 60 lb marinated for the Mexico-match birria sub-feature; cilantro 28 lb; mint 14 lb)
- Last week's top-5 waste $ drivers (4-unit consolidated, Leanpath export): pão de queijo over-bake at Buckhead (Brazilian-fan pre-test on 5/19 ran the basket spec at 18-per-basket but actual sell-through was 12-per-basket — 33% over-bake), chicken-thigh marinade past 48hr at East Atlanta (over-prep on a slow Sunday), cilantro at all 4 units (over-par on routine Friday delivery), bread end-cuts at Midtown (post-brunch surplus), citrus rinds (juice program over-prep)
- Tracking: Leanpath waste-station scale at every prep table (4 units); daily 2-min log; Leanpath now exports to R365 AI via the May-15 connector for prime-cost variance attribution at the SKU level
- Donation partner: Atlanta Community Food Bank (ACFB) — Tuesday + Friday + Sunday pickups; 4-unit consolidated pickup route added 2026-05-20 ahead of the World Cup window
- Compost vendor: CompostNow (commercial, all 4 units, twice-weekly pickup)
- Targets: house food-cost target 28%; trailing 4-week actual 28.8% (+0.8 pt over target — purchasing pre-stage ahead of surge inflated week-over-week temporarily); R365 AI Dashboard alerts CDO + GM if prime-cost variance exceeds +1.5 pt during any match-day week
- Multilingual surge prep: Step 13 multilingual-convention propagated from `sales/menu-description-writer` v1.3 and `customer-service/review-response-drafter` v1.3 is in effect house-wide for the World Cup window
- Bill Emerson Good Samaritan Act + Georgia Code §51-1-31 liability shield active

**Output — Pre-surge consolidated plan, week of 2026-06-08 (5 days before kickoff):**

**Area-GM 4-unit consolidated kitchen brief (printed for Monday huddle):**

```
SURGE SELL-FIRST (Mon 6/8 → Thu 6/11 kickoff): 4-unit consolidated picture
  1. Pão de queijo dough (40 lb across 4 units, days-to-risk 4)
     → Buckhead 14 lb (largest Brazil-fan radius)
     → Midtown 12 lb (game-watch venue tie-in with Park Tavern viewing party)
     → Decatur 8 lb / East Atlanta 6 lb
     → Goal: 95% absorbed by Thu 6/11 close as match-day pre-staging
  2. Picanha (80 lb consolidated, days-to-risk: 5 for cuts not frozen; 12 lb
     vacuum-sealed and frozen Monday for the 6/24 Brazil-match window)
     → Buckhead 24 lb + Midtown 22 lb + Decatur 18 lb + East Atlanta 16 lb
  3. Chicken thigh marinated for birria sub (60 lb, days-to-risk: 3 — 48hr
     marinade cutoff) → if Mon close volume < 40% baseline, freeze the
     remaining marinated portions at 18 lb across 4 units, run the rest as a
     Mon/Tue "Birria Quesadilla" feature (mirrors Example 2's recovery
     pattern but pre-staged ahead of surge)

PRE-MATCH-DAY SPECIALS (Tue 6/9 + Wed 6/10 — drive trial ahead of 6/11):
  • Pão de Queijo Tasting Trio ($12, 6 portions per order, runs Tue–Thu lunch + dinner)
    — uses 2 lb dough across 6 portions, target 36 portions/unit (144 total) ×4 units
    — plate cost $2.10, CM 82%
    — Pitch line EN: "Three styles of pão de queijo from our chef's Bahia
       playbook — try them before the tournament starts."
    — Pitch line PT (for PT-fluent server use): "Três estilos de pão de
       queijo do livro do chef da Bahia — experimente antes do torneio."

  • Picanha-on-the-Plancha Plate ($28, runs Wed–Thu dinner only)
    — 6 oz picanha + farofa + vinagrete + chimichurri verde
    — target 24 plates/unit (96 total), plate cost $7.20, CM 74%
    — Pitch line EN: "Brazilian-grade AAA picanha, slow-grilled on the
       plancha — chef's recommendation for tournament week."
    — Pitch line PT: "Picanha AAA brasileira grelhada na chapa — recomendação
       do chef para a semana do torneio."

  • Birria Quesadilla feature ($14, runs Mon–Wed lunch + dinner)
    — uses 4 oz chicken birria (sub recipe; absorbs the marinated thigh
      that can't hold past Wed close) + cheese + flour tortilla
    — target 18 portions/unit Mon (72 total), 22 portions/unit Tue (88 total),
      14 portions/unit Wed (56 total) — front-load before the surge
    — plate cost $3.45, CM 75%
    — Pitch line ES: "Quesadilla de birria, hecho a la mexicana — chef's
       prepare for Mexico match week." (ES preserved for ES-fluent server use)

DON'T-ORDER LIST (purchasing signal to Sysco DSR + Inland Seafood for Mon 6/8
truck — sent via R365 AI Dashboard ↔ Sysco Order interface, May-15 connector
auto-routes the down-order):
  • Cilantro: skip routine Friday order; current par + Tuesday standing par
    covers the surge week
  • Pão de queijo dough: hold next bulk order until Thu 6/11 PM
    (post-kickoff demand signal); R365 AI Dashboard alert configured to
    trigger re-order at < 8 lb consolidated stock
  • Bread end-cut absorption: pre-stage Saturday + Sunday brunch French-toast
    feature; absorbs Midtown's Friday surplus + Buckhead's Saturday surplus
  • Citrus: drop Friday order entirely; juice-program over-prep + bar-program
    consumption (caipirinha pre-stage at Buckhead + Midtown for World Cup
    watch-party slots) absorbs the standing par
```

**4-unit day-by-day prep table (Monday 6/8 — consolidated, area-GM view):**

| Unit / Station | Item | Standard par | Recommended par | Batch instructions |
|---|---|---|---|---|
| Midtown / Hot line | Picanha portioning | 0 | 22 portions (3 nights) | 6-oz portions, vacuum-sealed for Wed–Thu; 12 lb dry-aged dry-stage on Mon |
| Midtown / Cold pantry | Pão de queijo tasting trio | 0 | 36 portions (Tue–Thu lunch+dinner) | 6 portions per order × ~36 orders = 1.2 lb dough/day per unit |
| Buckhead / Hot line | Picanha portioning | 0 | 24 portions (3 nights) | Same |
| Buckhead / Bar | Caipirinha pre-stage | 0 | 24 ea Wed–Thu | Leblon premium pour modifier loaded in Toast Bar; ID gate active |
| Decatur / Hot line | Birria quesadilla (Mon-Wed) | 0 | 18 / 22 / 14 portions | Absorbs marinated thigh past 48-hr window |
| East Atlanta / Hot line | Birria quesadilla (Mon-Wed) | 0 | 18 / 22 / 14 portions | Same |
| All units / Brunch | Bread pudding from end-cuts | n/a | 1 hotel pan Sun 6/7 | Cube end-cuts, custard tomorrow — feeds Sat + Sun brunch absorption |

**Cross-utilization map (5 highest-leverage overlaps consolidated 4-unit):**

| SKU | Dishes it crosses into | Batch size | Par-drop trigger |
|---|---|---|---|
| Pão de queijo dough | Tasting trio (4-unit), pre-match Buckhead "Brazil bar bites" basket attach, Sun brunch attach | 2 lb prep per unit per day | If qty < 4 lb consolidated at Thu close → re-order via R365 AI Dashboard auto-trigger |
| Picanha | Plancha plate (Wed–Thu pre-match), Sat 6/13 Brazil-fan match-day surge anchor, Sun 6/14 brunch picanha-and-eggs feature | 5 lb portion-prep per unit per night | If frozen-stock < 8 lb by 6/22 → drop next Brazil-match pre-stage feature |
| Chicken birria (sub) | Mon–Wed lunch + dinner quesadilla feature; Sun staff meal at all 4 units if surplus | 12 lb per unit | If qty < 4 lb consolidated by Tue close → 86 the feature and run the marinated portions as a staff meal |
| Cilantro | Chimichurri verde (Wed–Thu picanha pre-stage), birria garnish (Mon–Wed), Sat 6/13 + Sun 6/14 brunch attach | 4 lb prep per unit | If qty < 2 lb at Fri close → pivot to mint-only garnish |
| Citrus | Caipirinha (Buckhead + Midtown bar), aguas frescas (Decatur + East Atlanta), brunch mimosa surge (all 4 units Sat + Sun 6/13–6/14) | 8 lb juice batch per unit | If qty < 3 lb at Wed close → 86 the brunch mimosa upsell |

**Donation routing this week (4-unit consolidated, ACFB):**

| Category | Routing | Pickup cadence | Units pooled | Liability note |
|---|---|---|---|---|
| Donation-eligible prepared foods (still in HACCP window, date-labeled) | Atlanta Community Food Bank (ACFB) — Tuesday + Friday + Sunday 4-unit consolidated pickup route | 3× / week | Midtown drop-point (consolidates Decatur + East Atlanta the morning of); Buckhead direct | Bill Emerson Good Samaritan Act + Georgia Code §51-1-31 liability shield active; donations made in good faith are protected from civil and criminal liability for the donor |
| Retail-imperfect produce (cilantro seconds, citrus rinds for zest) | Staff meal Sat + Sun across 4 units → if surplus, Too Good To Go surprise bag posted Saturday 6 PM (only Midtown has a TGTG account live; consolidates seconds from the other 3 units) | Saturday | All 4 → Midtown consolidator | n/a |
| TCS items past 7-day threshold | Compost (CompostNow) — back-of-house bin at each unit | Twice-weekly (Mon + Thu) | Per-unit | n/a |
| Fryer oil / trim / bones | Filta (oil, all 4 units), Darling Ingredients (bones, all 4 units) | Weekly | Per-unit | n/a |

**4-unit KPI dashboard (R365 AI Dashboard view, area-GM cockpit):**

| KPI | Target | Last week (4-unit consolidated) | This week goal | Owner |
|---|---|---|---|---|
| Total waste $ | down 8% vs. trailing-4-wk avg ($1,640 consolidated) | $1,798 | ≤ $1,509 | Maria Restrepo (area-GM) |
| Top-5-SKU exposure | ≥ 4 of 5 at ≤ 2 days of cover by Friday | 3 of 5 | ≥ 4 of 5 | Maria + 4 unit shift leads |
| Donation volume to ACFB | 48 meals / week (4 units × 12) | 41 | ≥ 48 | Lina (Midtown lead) + ACFB driver |
| Food-cost % (30-day rolling, R365 AI prime-cost attribution) | 28% | 28.8% | trend down to 28.4% by 30-day re-measure | Maria + Carlos (R365 controller) |
| Pre-surge prime-cost variance | within +1.5 pt of target (R365 AI alert threshold) | +0.8 pt | within +1.5 pt during 6/11 match-day week | R365 AI Dashboard alert → Carlos |

**Variance follow-through (last week's top-3 drivers, R365 AI prime-cost attribution + Leanpath SKU export):**

- Pão de queijo over-bake at Buckhead (Brazilian-fan pre-test 18-per-basket spec vs. 12-per-basket actual sell-through) — corrective: re-spec to 12-per-basket starting Mon 6/8; Brazilian-fan test absorbed into the Tasting Trio attach rate read at 6/9–6/10; Leanpath flagged SKU-level over-portion auto-alert at the Buckhead prep table threshold (Maria owns; verified with Buckhead shift lead by Tue close)
- Chicken-thigh marinade past 48hr at East Atlanta (over-prep on a slow Sunday) — corrective: Crunchtime AI Forecasting low-volume-day model now drops the East Atlanta marinade par on forecasted < 80 covers; East Atlanta shift lead Devon Park gets a Crunchtime mobile alert at the Sunday 7 AM par-confirm window (Maria + Devon own; closed in 2 weeks)
- Cilantro routine over-par at all 4 units — corrective: Friday-delivery par dropped to 0.7× routine through the World Cup surge window (6/11 – 7/19); R365 AI Dashboard cilantro re-order trigger set to 0.8 lb consolidated (Maria owns)

**Purchasing signal to DSR (sent Monday 4 PM, R365 AI Dashboard → Sysco Order auto-route):**

```
To: Tisha Mooney, Sysco Atlanta DSR
Subject: Mon 6/8 truck — World Cup 2026 pre-surge consolidated 4-unit
         (Brasa & Bahia)

  Cilantro: SKIP Friday order; routine Tuesday par holds (4-unit consolidated)
  Pão de queijo dough: HOLD next bulk order until Thu 6/11 PM; R365 AI
    Dashboard auto-trigger will fire at < 8 lb consolidated
  Picanha: confirm Wed 6/10 standing par + add a one-time pre-stage 40 lb
    cut for the 6/19 + 6/24 Brazil-match window (vacuum-seal at receiving;
    flag for the 6-mo TCS frozen-stock log)
  Black beans: STANDING par +10% for the 6/11 – 7/19 window
  Citrus: SKIP Friday order; standing Tuesday par + the bar pre-stage
    consumption covers
  All else: standing par

   — Maria Restrepo, Area-GM
   (R365 AI Dashboard order-confirmation reference: BB-25260-0608)
```

**R365 AI Dashboard alerts configured for the surge window (Maria + Carlos cockpit):**

- Pão de queijo dough < 8 lb consolidated → auto-reorder + DM Maria
- Picanha frozen-stock < 8 lb by 6/22 → 86 the 6/24 pre-stage feature; Crunchtime mobile push to all 4 unit shift leads
- Prime-cost variance > +1.5 pt during any match-day week → R365 AI Dashboard alert to Maria + Carlos within 6 minutes
- Donation volume < 36 meals / wk (75% floor of the 48 target) → ping Lina at Midtown + ACFB driver
- Brisket-taco-style cannibalization gate not applicable to this concept; the Picanha + Birria menu sit beside year-round Brasa & Bahia hero items (rice-bean bowls) which have a different daypart pattern and are not at cannibalization risk

**Staff-facing 4-unit shift brief (one page, printed for kitchen huddle Mon 6/8 at 4 PM at all 4 units):**

```
WORLD CUP 2026 SURGE: 16 days to kickoff. Brazil + Mexico + Argentina matches
at MBS — heavy multilingual fan visitation expected.

TODAY'S SELL-FIRST: pão de queijo dough, chicken birria (Mon-Wed window),
picanha pre-stage cuts.

TODAY'S SPECIALS:
  Lunch + dinner: Pão de Queijo Tasting Trio ($12) — pitch as "before the
  tournament starts"
  Lunch + dinner: Birria Quesadilla ($14) — pitch as "before Mexico match
  week"
  Wed–Thu dinner only: Picanha-on-the-Plancha ($28) — pitch as "chef's
  recommendation for tournament week"

DON'T-ORDER: cilantro (skip Friday), pão de queijo bulk (hold), citrus
(skip Friday). R365 AI Dashboard auto-handled.

86 / SUBSTITUTION PLAN:
  • If pão de queijo dough < 4 lb at Thu close → 86 the tasting trio, sub
    Brazilian-style empanada (we have 60 ea frozen)
  • If picanha pre-stage falls behind by Wed close → 86 the plancha feature
    Thu only, hold for Wed dinner

STAFF MEAL SLOTS (use-up across 4 units):
  Mon dinner: Decatur + East Atlanta staff meal = birria-thigh rice bowl
    (absorbs the marinade-past-48hr portions)
  Sat staff meal (post brunch): bread pudding from end-cuts at Midtown +
    Buckhead

MULTILINGUAL SERVER PRE-BRIEF (Wed 6/10 lineup, all 4 units):
  Lucas (Midtown PT-fluent server), Beatriz (Buckhead PT-fluent floor lead),
  Andrea (Decatur ES-fluent server), and Diego (East Atlanta ES + PT) are
  pre-briefed on the picanha + birria pitch lines in PT and ES per the
  Step 13 multilingual server-pitch convention (`sales/menu-description-
  writer` v1.3). No machine translation on the printed specials cards —
  all PT and ES copy is human-reviewed.
```

**Re-measure scheduled:** Sunday 6/14 close — Maria pulls the R365 AI Dashboard + Leanpath consolidated 4-unit log, scores against the targets above. The pre-surge week is the calibration week for the Brazil-match anchor on 6/19. Feed wrap into the next week's Demand Forecast Briefing accuracy review with the Crunchtime AI Forecasting team and the R365 AI consultant assigned post-launch (Marc Cohen — same R365 AI Solutions Architect who handled the Black Rock Coffee Bar 190+ location case at the NRA Show 2026 Innovation Theater on 5/19).

**Lesson capture (feed forward to the 6/15 Demand Forecast Briefing):**

- Multi-unit consolidated waste planning with an Area-GM + 4 unit shift leads requires the R365 AI Dashboard mobile-alert cockpit to be configured BEFORE the surge starts, not during it. Maria's NRA Show 2026 visit to booth #6027 on 5/18 yielded the alert-threshold templates that are live this week — without that pre-staging, the prime-cost variance alerts would not fire until after the first match-day week.
- Crunchtime AI Forecasting's event-overlay model is the source-of-truth for the per-unit match-day cover forecast; R365 AI's prime-cost variance attribution closes the loop on whether the surge purchasing produced the margin lift it forecasted. The two systems were spec'd as a bundle at NRA Show 2026 specifically because neither one alone covers the consolidated multi-unit pre-surge use case.
- Leanpath SKU-level export to R365 AI (via the 2026-05-15 connector) is the third leg — without it, the prime-cost variance attribution can't trace back to a specific over-portion event. Buckhead's pão de queijo over-bake from the 5/19 Brazilian-fan pre-test was the diagnostic case that proved the integration; the corrective re-spec on Monday 6/8 is the closure.
- Multilingual server pre-brief (PT + ES) is co-owned with `customer-service/review-response-drafter` Step 13 multilingual convention and `sales/menu-description-writer` Step 13. The waste-planning surface is one of three places this convention is now enforced operationally (printed specials cards + server-pitch lines + multilingual review handling).

**Severity-gate / escalation tags:** This is a coordinated multi-unit pre-surge week, NOT a routine plan. If R365 AI Dashboard fires a prime-cost variance > +1.5 pt alert during the surge window, escalate to the owner (Brasa & Bahia LLC) within 6 hours and pause any not-yet-executed pre-stage purchasing. If ACFB donation volume drops below 36 meals/wk for any single surge-window week, the Lina + Driver pickup-route gets a 4-unit consolidated re-confirm call. If multilingual server pre-brief is not completed at any of the 4 units by Wed 6/10 lineup, the unit's specials cards are reverted to EN-only and the missed pre-brief is flagged in the Maria + Carlos R365 AI Dashboard log for the next NRA Show 2027 vendor-conversation prep.
