---
name: "Food Waste Reduction Planner"
category: operations
tools: [claude, chatgpt]
difficulty: intermediate
time_saved: "~45 min/week"
version: 1.2
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
