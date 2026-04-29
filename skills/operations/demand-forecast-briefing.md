---
name: "Demand Forecast Briefing"
category: operations
tools: [claude, chatgpt]
difficulty: intermediate
time_saved: "~30 min/week"
version: 1.2
last_eval_score: null
---

# 📊 Demand Forecast Briefing

## Purpose

Produce a weekly (or event-specific) demand forecast that estimates covers by day-part, projects top-selling items, quantifies weather and event impact in ranges a kitchen can act on, and hands off one planning reference the GM, chef, and bar manager use to drive prep, purchasing, staffing, and reservation-desk pacing. Bridges POS history and external signals into a three-scenario (low / expected / high) plan with named owners for each risk day.

## When to Use

Run this skill every week during Sunday or Monday planning, in front of holidays and major local events (Valentine's, Mother's Day, Restaurant Week, city-wide festivals, home playoff games, conferences), before a menu launch or LTO window, after a price or hours change when the trailing baseline is unreliable, or when weather forecasts shift materially mid-week. Pair with Staff Schedule Optimizer (downstream for labor) and Food Waste Reduction Planner (downstream for prep and purchasing) so the three skills share one demand assumption.

Scope note: this brief is the weekly forecast and the single-event pre-brief. For a multi-week mega-event surge — most prominently the FIFA World Cup 2026 (June 11 – July 19, 2026, 16 host cities), but the same applies to a future Olympics, Super Bowl host-week, or sustained festival series — use the World Cup 2026 Surge Playbook for the multi-week match-window calendar, multilingual operations layer, surge staffing pipeline, supply-chain stress test, and after-tournament wind-down. The Surge Playbook calls Demand Forecast Briefing as a daily / weekly sub-routine; the two are complementary.

## Required Input

Provide the following:

1. **Sales history** — At least 4 weeks (prefer 8 to 13) of daily cover counts and item-level sales (POS export from Toast, Square, Aloha, Clover, Revel, Lightspeed, TouchBistro, Oracle Simphony, or a POS-forecast summary from Toast Forecast, CrunchTime Net-Chef, RASI Forecaster, Restaurant365 Forecasting, or Fourth/HotSchedules forecaster)
2. **Reservation book** — Upcoming confirmed reservations by day and day-part (OpenTable, Resy, SevenRooms, Tock, Yelp Reservations); party-size distribution; any pre-orders, deposits, BEOs, or tasting-menu commitments; walk-in share assumption by day
3. **External signals** — 7-to-10-day weather forecast (temperature range, rain probability, wind, severe weather), local events calendar (concerts, sports home games, festivals, conferences, conventions, restaurant week), school and university calendars (in-session vs. break), holidays (federal, religious, locally observed)
4. **Recent trends and disruptions** — New menu items or LTOs launched in the last 8 weeks, recent press coverage, nearby construction or street closures, competitor openings or closings within 0.5 mile, delivery-platform promotions or commission changes
5. **Capacity** — Total seats, bar seats, patio seats, private dining, typical turn times by day-part, reservation pacing rules, walk-in capacity floor; any capacity constraint from staff shortage or equipment issue
6. **House targets and thresholds** — Target food-cost %, target labor %, the cover band the GM calls "slammed" vs. "slow," and the reservation-pacing rule that triggers a pause on additional walk-ins
7. **Known one-offs** — Confirmed private events, buyouts, chef's table seatings, media visits, influencer reservations, or VIP holds that shift mix away from baseline
8. **Forecast recipients and use** — Who consumes the brief (GM, chef, sous, bar manager, FOH manager, host lead, owner) and what they each need to act on (prep par, purchasing, schedule, reservations, floor plan, marketing pulse)

## Instructions

You are a restaurant analytics lead with 10+ years reading POS data, weather APIs, and reservation curves against the four walls of a dining room. Your forecast reads like a chef-and-GM wrote it together — quantified, day-part specific, conservative on the floor, and honest about the downside scenario.

**Before you start:**
- Load `config.yml` for concept, unit count, seat layout, target metrics, forecast confidence interval, and the cadence the house expects (weekly Sunday, holiday pre-brief, etc.)
- Reference `knowledge-base/terminology/` for correct usage of covers, turn, pace, par, day-part, TCS, mise, BEO, pre-shift, 86
- Pull last week's forecast from `outputs/` and score accuracy (actual vs. expected) on the 3 biggest-miss dayparts before you write this week — the feedback loop is how the forecast improves month over month
- If Reservation book is thin, anchor on trailing day-of-week averages and flag uncertainty; do not paper over sparse data with smoothed numbers

**Process:**

1. **Baseline projection by day-part** — Calculate expected covers for every day × day-part using the trailing 4-to-8-week average, day-of-week seasonality factor, and a same-week-last-year check (if available). Express baseline as a point estimate and a confidence interval (e.g., ± 8%). Include walk-in share by day-part because holidays and events compress it.

2. **Weather-impact adjustment** — Layer in weather with explicit ranges: light rain −5–10%, heavy rain −10–15%, thunderstorm/snow −15–25%, extreme heat (>95°F / 35°C) −15–25%, extreme cold (<20°F / −7°C) at patio-heavy concepts −10–20%, mild and sunny on a weekend +5–10%, first warm spring weekend +10–20%. Note whether the concept is patio-dependent, air-conditioned, or storm-door-facing; these modify the range. Cite the exact daily forecast reading behind the adjustment.

3. **Event and calendar adjustment** — Quantify local-event lift or drag with a named source (home NFL/NBA/MLB/NHL game, concert at venue X, convention center block, festival, Restaurant Week, school / university calendar in or out of session). Use concept-specific rules: a game-day sports bar is +30–60%, a fine-dining room near the same arena is −10–20% because guests cancel. Don't force a one-size lift.

4. **Reservation-pace overlay** — For each day-part, lay the reservation book's current pace against the forecast. Flag days where reservations alone already fill > 80% of capacity (overbook pressure), where pace is < 50% of forecast with four days out (marketing pulse candidate), or where walk-in variance is too high to plan labor against (wide confidence interval).

5. **Three-scenario output** — For each day, produce a low / expected / high cover count with the probability the GM should plan at each. Prep and purchasing should key off expected, with a documented "call-up" trigger (e.g., if reservations cross X by Thursday 5 PM, prep to the high scenario). This is the one specification that separates a usable forecast from a spreadsheet exercise.

6. **Item-level forecast** — Project the top 10 to 20 items by volume for the week, noting items likely to spike due to seasonality, weather (hot-drink attach in cold, salad attach in heat), holiday, LTO, or a press mention. Flag any item whose projected demand exceeds current par or upcoming delivery coverage. Reuse the Food Waste Reduction Planner's sell-first list so the item forecast nudges demand toward at-risk SKUs.

7. **Risk day callouts** — Identify the 2 to 3 highest-uncertainty days (conflicting signals, weather volatility, event week, labor thin) and assign each a named owner (GM, chef, FOH manager), a decision point (when the call is made to flex), and a contingency play (extend happy hour, push patio promo, pull back on an LTO, trigger delivery surge pricing, invoke the on-call cook). Uncertainty without a decision owner becomes a post-mortem.

8. **Purchasing and prep implications** — Translate the forecast into key ingredient quantities that deviate from standard par. Specify SKU, usual par, recommended par, day-part the change applies to, and the DSR (broadline sales rep) conversation needed if the delta exceeds the regular order window. Link to Food Waste Reduction Planner's down-order list so the two plans reconcile before Monday's truck.

9. **Staffing signal** — Indicate which days need above- or below-normal staffing by role (line, sauté, grill, pantry, garde manger, expo, dish, server, host, bar, support, runner). Quantify by labor hours, not vague "heavy night." Hand off to Staff Schedule Optimizer as the demand input rather than have the scheduler re-forecast.

10. **Marketing and reservation-desk actions** — For soft days, recommend one concrete pull lever: a push on OpenTable PrimeTime, a surge of an LTO through Social Media Post Generator, a promo to the loyalty list via email, an email-drafter handoff for a private-event upsell. For slammed days, recommend a guardrail: close additional walk-in seating, pause delivery-platform promos, or move the host to a reservation-pacing app view.

11. **Forecast accuracy feedback loop** — At week-end, score actual vs. expected for covers (MAPE), item mix (top-10 accuracy), and weather/event adjustments (right direction and right magnitude). Log systematic biases (always under-forecasts brunch after rain? Always over-forecasts Monday?) so next week's baseline learns.

12. **Publication-ready brief** — Package the forecast for three audiences: (a) one-page GM / chef dashboard with the day-by-day table, risk day callouts, and action owners; (b) BOH wall posting with covers and par adjustments per day-part; (c) a short owner summary with the three big-weekend calls and their rationale.

**Output requirements:**
- Day-by-day table: date, day-part, reservations-on-book, walk-in estimate, low / expected / high covers, top 3 items, staffing note, risk flag, named owner
- Weather-impact table with forecast reading and % adjustment
- Event-impact table with source, concept-specific rule, and % adjustment
- Three-scenario output with call-up triggers
- Item-level forecast for the top 10–20 SKUs with par-change recommendations
- Risk day callouts with named owner, decision point, and contingency play
- Purchasing delta list handed to the DSR
- Staffing hours-by-role signal handed to Staff Schedule Optimizer
- Marketing / reservation-desk action list for soft and slammed days
- Accuracy feedback table (last week actual vs. forecast) — MAPE on covers, top-10 hit rate on items
- One-page summary suitable for posting in the kitchen or manager's office
- Plain language with correct industry terminology (covers, day-part, par, turn, pace, BEO, 86, mise, TCS, MAPE)
- Ready to use with minimal editing
- Saved to `outputs/` with date-stamped filename if the user confirms

## Related Skills

- `admin/staff-schedule-optimizer.md` — Consumes the staffing signal from step 9 as demand input
- `operations/food-waste-reduction-planner.md` — Shares the cover forecast so prep, purchasing, and waste move in sync
- `admin/supplier-negotiation-brief.md` — Absorbs the purchasing delta list from step 8
- `sales/social-media-post-generator.md` — Runs the marketing pulse for soft days in step 10
- `operations/shift-prep-checklist.md` — Consumes the day-part covers and top items as line-level tasks
- `admin/dynamic-menu-pricing-advisor.md` — Cross-checks event-day surcharge / day-part pricing decisions

## Example Output

### Example 1 — Standard week forecast, full-service neighborhood concept

**Input:**
- Concept: Cedar & Vine, 75-seat seasonal-American, Portland OR; Toast POS
- Sales history: trailing 8 weeks, daily covers 60–155, dinner-heavy with Sunday brunch
- Reservation book (5/4 Sunday 4 PM pull): Tue 24 / Wed 32 / Thu 48 / Fri 76 / Sat 102 / Sun (brunch) 38; party-size 2-mode with 4 large-tops on Sat
- Weather (NOAA 7-day): Tue mild 68°F sun; Wed 61°F partly cloudy; Thu 72°F sun (first warm Thu); Fri 78°F sun; Sat 81°F sun; Sun 75°F sun (warm spell on a patio-heavy concept)
- Events: Portland Timbers home Sat 5/9 7:30 PM (3 mi away — game-day softens fine-dining 5–10%); No major festivals; Mother's Day is the following Sunday (5/10 next week — preview week)
- Capacity: 75 seats + 18-seat patio (weather-active); typical Sat dinner pace 130–150 covers in season
- Targets: target food cost 29.5%, target labor 28%, "slammed" = 140+ covers / day, "slow" = < 60 covers / day
- House baselines (trailing 8): Tue 52 / Wed 58 / Thu 68 / Fri 92 / Sat 128 / Sun 76 — with ±8% confidence interval
- Last week's accuracy: covers MAPE 6.2%; biggest miss = Saturday under-forecast by 14 covers (festival walk-up)

**Output — Week of 2026-05-04, GM/chef dashboard (one page):**

**Day-by-day cover forecast:**

| Date | Day-part | Reservations | Walk-in est. | Low | **Expected** | High | Top 3 items | Staffing note | Risk flag | Owner |
|---|---|---|---|---|---|---|---|---|---|---|
| Tue 5/5 | dinner | 24 | +28 (54%) | 44 | **52** | 60 | Burger / Salmon / Caesar | normal | none | Maria |
| Wed 5/6 | dinner | 32 | +25 (44%) | 48 | **57** (+5%) | 65 | Burger / Pasta / Salmon | normal | none | Maria |
| Thu 5/7 | dinner | 48 | +28 (37%) | 65 | **76** (+12% — first warm Thu, patio open) | 86 | Salmon / Burger / Heirloom-tomato app | +1 patio server | weather lift | Priya |
| Fri 5/8 | dinner | 76 | +24 (24%) | 88 | **98** (+7% — warm Fri, patio peak) | 110 | Salmon / Burger / Pasta | +1 patio server, +0.5 hr expo | reservations 80% of cap | Priya |
| Sat 5/9 | dinner | 102 | +30 (23%) | 122 | **134** (+5% — warm Sat baseline + Timbers softens fine-dining 5–10%, two effects partially cancel) | 148 | Salmon / Burger / Heirloom-tomato app / Pasta | +1 patio server, +1 line cook 4 PM | high uncertainty (event + weather) | Maria |
| Sun 5/10 | brunch | 38 | +42 (53%) | 70 | **80** (+5% — warm Sun, patio active for brunch) | 92 | Pancakes / Eggs Benedict / Avocado toast | +1 patio brunch server | first patio brunch in 2 wks | Diego |

**Week total: low 437 / expected 497 / high 561 covers**

**Weather-impact table:**

| Day | Forecast | Adjustment vs. baseline | Reasoning |
|---|---|---|---|
| Tue | 68°F sun | 0 | mild on a Tuesday — patio doesn't move the needle |
| Wed | 61°F partly cloudy | 0 | baseline |
| Thu | 72°F sun | +12% | first warm Thu — patio opens, walk-in lift on a Thursday |
| Fri | 78°F sun | +7% | warm Fri pushes patio + walk-in; baseline already strong |
| Sat | 81°F sun | +5% | warm Sat lifts walk-in but patio is at cap; net +5% |
| Sun (brunch) | 75°F sun | +5% | warm brunch Sunday is patio-active |

**Event-impact table:**

| Day | Event | Source | Concept-specific rule | Adjustment |
|---|---|---|---|---|
| Sat 5/9 | Timbers home 7:30 PM (3 mi) | timbers.com schedule | fine-dining 3-mi from MLS stadium = −5–10% | −5% (game softens, not games-day-bar) |
| All week | Mother's Day on Sun 5/10 NEXT week (preview) | calendar | guests pre-booking next week absorbs some of this week's reservation pace | informational, no adjustment |

**Three-scenario output with call-up trigger:**

```
LOW (437 covers): plan to this if Saturday weather shifts to rain-risk above 50%
                  (NOAA refresh Wednesday 6 AM — re-run if shift detected).
EXPECTED (497 covers): default plan. Prep, purchasing, and labor key off this.
HIGH (561 covers): call-up trigger = if Saturday reservations cross 115 by
                  Thursday 5 PM, prep to high. Owner: Maria. Deadline: Thu 5 PM.
                  Action if triggered: +0.5 line cook to Saturday, +1 dishwasher,
                  +1 case salmon to Sat purchasing, +1 par on burger patties.
```

**Item-level forecast (top 10 by volume):**

| Item | Trailing-week avg | This week projection | Δ | Driver | Par-change rec |
|---|---|---|---|---|---|
| Cedar burger | 142 | 156 (+10%) | +14 | warm-week burger demand | +1 case patty |
| Salmon | 84 | 96 (+14%) | +12 | seasonal anchor + warm weather | +6 portions |
| Burrata-tomato app | 38 | 58 (+53%) | +20 | first warm Thu + sell-first sell-through | +12 portions |
| Caesar salad | 76 | 78 | flat | baseline | hold |
| Cacio e pepe | 64 | 60 | -6% | warm weather softens pasta demand slightly | -8 portions |
| Heirloom-tomato app | 22 | 36 (+64%) | +14 | sell-first ladder week | +14 portions |
| Cedar negroni | 88 | 92 | flat | summer cocktail trend | hold |
| Brunch pancakes | 36 | 42 (+17%) | +6 | warm brunch Sunday | +6 portions |
| Eggs Benedict | 28 | 30 | flat | baseline | hold |
| Avocado toast | 24 | 28 (+17%) | +4 | warm brunch Sunday | hold (par at 32) |

**Risk day callouts (top 3):**

| Day | Risk | Decision point | Contingency play | Owner |
|---|---|---|---|---|
| Sat 5/9 | Cover band wide (122–148) due to event + weather + reservation pace | Thursday 5 PM reservation count | If ≥ 115 → call-up; if ≤ 95 → hold to expected | Maria |
| Thu 5/7 | First warm Thursday — patio walk-in could over-perform | Thursday 4 PM walk-in pace | If ≥ 8 walk-ins by 5 PM → push patio par; pre-call patio server to extend | Priya |
| Sun 5/10 brunch | First warm patio brunch in 2 weeks; baseline thin | Sunday 9:30 AM walk-in + reservation no-show rate | If pace > 20 covers / hour by 11 AM → extend brunch service to 3:30 PM (vs. 3 PM) | Diego |

**Purchasing delta list (handed to Sysco DSR Mon 5/4 4 PM):**
- Salmon: +6 portions (1 extra side per case adjustment)
- Heirloom tomato: drop next case (sell-first cycle from Food Waste Reduction Planner)
- Burrata: drop to 6 ea
- Burger patty: +1 case
- All else: hold

**Staffing signal (handed to Staff Schedule Optimizer):**
- Tue/Wed: standard
- Thu: +1 patio server 5 PM (warm-Thu lift)
- Fri: +1 patio server, +0.5 hr expo
- Sat: +1 patio server, +1 line cook 4 PM, on-call: 1 server + 1 dish (call-up triggered if reservations cross 115 by Thu 5 PM)
- Sun brunch: +1 patio brunch server

**Marketing / reservation-desk actions:**
- Tue (slow night): push the "industry Tuesday" promo via the loyalty list (already scheduled)
- Sat (peak): close walk-in additions after 8 PM if reservations cross 130; pause OpenTable PrimeTime promo on the high-uncertainty hour 7–8 PM
- Sun brunch: post-on-Threads call-out about the patio re-opening Sunday for brunch (handoff to Social Media Post Generator with the patio-warm-Sunday angle)

**Accuracy feedback (last week):**

| Metric | Forecast | Actual | Δ | Notes |
|---|---|---|---|---|
| Total covers | 484 | 497 | +2.7% (slight under) | Saturday under by 14 (festival walk-up) |
| Top-10 hit rate | n/a | 9 of 10 | +90% | Missed cacio e pepe (-12%) — post-photo virality wore off |
| Saturday adjusted MAPE | 7% | n/a | n/a | Festival lift not in our calendar — add Music Millennium store events to next week's pull |

**Owner summary (3 bullets, sent in the Monday email):**
- Expected 497 covers vs. 484 last week (+2.7%); first warm patio week of May should drive Thu and Sun brunch above baseline
- Sat 5/9 has the widest band (122–148) due to Timbers home + warm weather; call-up trigger at Thursday 5 PM, owner Maria
- Mother's Day reservations for next week (5/10 brunch + dinner) at 89% of last year's pace by tonight — pre-fix the reservation overflow before Tuesday close

---

### Example 2 — Holiday pre-brief (Mother's Day at a brunch-heavy concept)

**Input:**
- Concept: Cantina Verde, 110-seat Tex-Mex with weekend brunch, Austin TX (Square POS); Mother's Day is the largest brunch volume day of the year
- Holiday: Mother's Day (Sunday 2026-05-10), brunch 10 AM – 3 PM, dinner 5 PM – 10 PM
- Reservation book (5/4 Monday 9 AM pull, 6 days out): Brunch 178 / Dinner 96 — early indicator strong (last year same-week-out: brunch 134 / dinner 78); party-size mode 4–6 with 18 large-tops (8+) on the brunch side
- Weather: NOAA 6-day: Sun 5/10 86°F sun (warm, patio-active); no rain risk
- Trailing year Mother's Day: 312 brunch covers + 184 dinner = 496 total; second-busiest day of the year after NYE
- Last 4 weeks Sunday brunch trailing: 178 covers / week; pace 18 covers per 30-min window peak 11 AM – 1 PM
- Capacity: 110 seats + 24-seat patio + 36-seat private dining (PDR); brunch + dinner crossover at 3 PM is a tight handoff
- Reservation cap so far: brunch 220 (vs. 280 capacity, leaving 60 walk-in floor); dinner 130 (vs. 180 capacity)

**Output — Mother's Day pre-brief, issued Monday 5/4 (6 days out):**

**Demand projection:**

| Day-part | Last-year actual | Reservations on book (5/4) | Walk-in est. | Low | **Expected** | High | Capacity | Pace utilization |
|---|---|---|---|---|---|---|---|---|
| Brunch (10–3) | 312 | 178 (still 6 days out, will close at ~250) | +60 (24%) | 280 | **310** | 340 | 280 reservation cap + 60 walk-in floor = 340 | 91% expected |
| Dinner (5–10) | 184 | 96 (will close at ~140) | +50 (35%) | 165 | **190** | 215 | 180 hard cap (PDR open for catering on Mother's Day) | 106% — overbook check needed |
| Total | 496 | 274 (currently) | +110 | 445 | **500** | 555 | n/a | n/a |

**Three-scenario call-up triggers:**
- **Reservations close-out check:** Wed 5/7 noon — if brunch reservations cross 240, close brunch reservations and post a walk-in-only line; if dinner crosses 145, close dinner reservations entirely and message 5/8–5/9 walk-up overflow to the next available Sunday
- **High-side prep:** Wed 5/7 — order 50% above baseline on signature brunch items (chilaquiles, brunch enchiladas, churros pancakes, breakfast tacos)
- **Bar program:** Friday 5/8 — pre-batch the Mother's Day mimosas and frozen-margarita rotation

**Weather-impact table:**

| Day | Forecast | Adjustment | Reasoning |
|---|---|---|---|
| Sun 5/10 | 86°F sun | +0 (factored in baseline) | Warm Sunday is the historical Mother's Day baseline; not an additional lift |

**Event-impact table:**

| Source | Effect | Adjustment |
|---|---|---|
| Mother's Day | flagship Sunday — historical 96th percentile day | already in projection |
| UT Austin spring graduation 5/9–5/10 | family overflow into Sunday brunch | +5% to brunch (already in expected) |
| Austin City Limits not running | n/a | 0 |
| ABC News Austin Mother's Day round-up (we made the list 2026-05-02) | press lift | +3% (built into expected) |

**Item-level forecast (Mother's Day-specific):**

| Item | Last-year actual | This year projection | Par-change rec |
|---|---|---|---|
| Chilaquiles | 96 | 105 (+10%) | +18 portions (avocado short-shipped — call DSR Wed) |
| Mother's Day mimosa flight | 88 | 110 (+25%) | pre-batch Saturday — 4 oz × 4 flutes per flight |
| Brunch enchiladas | 78 | 85 (+9%) | hold |
| Churros pancakes | 64 | 80 (+25%) | +16 portions; bread program ready Saturday afternoon |
| Breakfast tacos | 142 | 168 (+18%) | +20 portions; chorizo standing par doubled for Saturday cook-down |
| PDR private brunch buffet (large-tops) | n/a | 4 confirmed bookings × 12 covers each = 48 covers in PDR | already in expected |
| Mother's Day fixed-price dinner ($45) | 96 | 110 (+15%) | hold |

**Pace-by-30-min reservation overlay (brunch only, 5/10):**

| 30-min slot | Reservations on book (5/4) | Reservation cap (target) | Status |
|---|---|---|---|
| 10:00 | 18 | 24 | open |
| 10:30 | 24 | 26 | tight |
| 11:00 | 32 | 32 | full — close to additional reservations |
| 11:30 | 36 | 32 | overbooked by 4 — push to 11:00 or 12:00 |
| 12:00 | 28 | 32 | open |
| 12:30 | 22 | 28 | open |
| 1:00 | 14 | 24 | open |
| 1:30 | 4 | 22 | open |

**Action: Reservation desk re-paces — push 4 of the 36 11:30 reservations to 11:00 or 12:00; phone outreach starts Tuesday 5/5 AM (Maria + Erica).**

**Risk day callouts:**

| Risk | Decision point | Contingency play | Owner |
|---|---|---|---|
| Brunch overbook 11:30 slot | Tue 5/5 EOD | Re-pace via guest call; offer table-2 same time | Maria |
| Dinner cap pressure (96 → 140 trajectory; 180 capacity) | Wed 5/7 noon | If 5/7 noon reservations cross 145, close dinner reservations | Maria |
| Pastry capacity for churros pancakes (+25% projection) | Sat 5/9 PM bake-off | If Sat trial doesn't complete the +16 portions on time, sub the day-glo lemon ricotta pancake (also strong on Mother's Day mix) | Reyes (chef) |
| Brunch-to-dinner turnover at 3 PM | Sun 5/10 2:30 PM | Pre-stage the dinner setting at 2:30 in the patio half (which closes brunch at 2 PM); main dining room turns at 3:00 PM with a 30-min break | Erica (FOH lead) |
| Walk-in queue management at 11 AM | Sun 5/10 10 AM | Mia (host) + 1 floater (Lucas) take outside-line; offer text-when-table at the QR-code link; cap at 90 min wait promise | Mia |

**Purchasing delta list (sent to PFG DSR Wednesday 5/6 AM):**
- Chorizo: 2× standing par (Friday delivery)
- Avocado: confirm 5 cases not 3; quality QA on receipt
- Eggs: +20 dozen for Saturday + Sunday (brunch volume)
- Premium tequila (mimosa flight + frozen margarita): Friday delivery confirmed
- Sparkling wine for mimosas: 24 bottles vs. standard 12

**Staffing signal:**
- Brunch: 8 servers (vs. baseline 5), 2 hosts (vs. baseline 1), 4 line cooks (vs. baseline 3), 2 dishwashers (vs. baseline 1), 1 floater
- Dinner: 6 servers (vs. baseline 4), 2 hosts (vs. baseline 1), 4 line cooks (vs. baseline 3), 2 dishwashers
- Cross-shift: brunch crew leaves 3:00 PM; dinner crew arrives 2:30 PM; 30-min handoff stagger
- Predictability-pay reserve (house policy mirroring Austin's labor norms): $250 for any post-posting changes inside the 14-day window — none expected

**Marketing actions:**
- Tuesday 5/5: post the Mother's Day reservation-closing nudge via the loyalty email + Threads (handoff to Social Media Post Generator)
- Friday 5/8: post the Saturday-evening "few seats left for Sunday brunch — walk-up line opens 10 AM" message
- Saturday 5/9: post the patio-confirm message ("patio open for Mother's Day brunch — first warm forecast of May")
- Pause all new OpenTable promotions for the week of 5/10 — capacity is the binding constraint, not demand

**Owner summary (3 bullets):**
- Mother's Day projection: 500 covers expected (vs. 496 last year; trajectory strong with 20%+ early reservation lift)
- Three reservation-desk actions before Wednesday: re-pace 11:30 brunch slot, close dinner reservations if Wed noon cross 145, confirm 4 large-top PDR brunch buffets
- Purchasing call to PFG Wednesday AM: chorizo 2× par, eggs +20 dozen, avocado QA at receipt; press lift confirmed (ABC News round-up)

---

### Example 3 — Risk-week forecast (Mariners home stand + adverse weather)

**Input:**
- Concept: Cantina Verde, 110-seat Tex-Mex (Seattle unit), Seattle WA
- Reservation book (5/4 Sunday 4 PM): Tue 28 / Wed 38 / Thu 24 / Fri 62 / Sat 88 / Sun 42
- Events: Mariners home stand 5/4–5/7 (Mon, Tue, Wed all 7:10 PM home; Thu day-game 1:10 PM); Sounders home Sat 5/9 1:30 PM; 0.4 mi from T-Mobile Park (game-day sports-bar lift)
- Weather: NOAA 7-day: Mon 58°F overcast; Tue 56°F rain; Wed 54°F heavy rain (1.2" forecast); Thu 60°F clearing; Fri 64°F sun; Sat 68°F sun; Sun 65°F partly cloudy
- Capacity: 110 seats; covered patio (8 seats, weather-resilient); typical Tue night 35–55 covers; typical Sat 140–180 (event-week)
- Concept-specific event rules: game-day sports-bar lift +30 to 60% on Mariners and Sounders home days because of proximity (within walk distance); but adverse weather at game-time can cancel the walk-up entirely
- Last week's accuracy: covers MAPE 11.4% — high uncertainty week with two weather miss-fires

**Output — Risk-week forecast for week of 2026-05-04, Sunday 5/3 4 PM issuance:**

**Day-by-day cover forecast with confidence bands:**

| Date | Reservations | Walk-in est. | Low | **Expected** | High | Confidence | Top 3 items | Risk flag |
|---|---|---|---|---|---|---|---|---|
| Tue 5/5 (Mariners 7:10) | 28 | +60 if rain holds off; +20 if rain at 5–7 PM | 48 | **78** | 105 | LOW (weather binary) | Tacos / Margarita / Chips & guac | weather kill-switch |
| Wed 5/6 (Mariners 7:10, heavy rain) | 38 | +5–15 (game-day-walk-up will be < 50% of dry case) | 43 | **48** | 65 | MEDIUM-LOW | Tacos / Burrito / Margarita | weather drag |
| Thu 5/7 (Mariners day-game 1:10) | 24 | +30 (post-game lunch lift) | 50 | **62** | 75 | MEDIUM | Tacos / Birria bowl / Margarita | day-game lunch lift, dinner soft |
| Fri 5/8 | 62 | +28 (44%) | 75 | **88** | 102 | HIGH | Tacos / Margarita / Burrito | none |
| Sat 5/9 (Sounders home 1:30) | 88 | +50 (matchday lunch + dinner) | 124 | **140** | 162 | MEDIUM-HIGH | Tacos / Margarita / Birria bowl | matchday over-promise risk |
| Sun 5/10 | 42 | +28 (40%) | 60 | **70** | 84 | HIGH | Tacos / Brunch tacos / Bloody | none |

**Week total: low 400 / expected 486 / high 593 covers — a 193-cover band, the widest of the trailing 8 weeks.**

**Weather-impact table (game-day specific):**

| Day | Forecast | Game-day modifier | Net adjustment | Reasoning |
|---|---|---|---|---|
| Tue 5/5 | 56°F rain | -25% on rain × +30–60% on game-day → net wide band | range +5% to +25% | Rain at game-time cancels half the walk-up; covered patio absorbs only 8 seats |
| Wed 5/6 | 54°F heavy rain (1.2") | -40% on heavy rain × +30–60% on game-day → net potentially negative | range -15% to +15% | Heavy rain expected to cancel most of the matchday walk-up; bar program holds the night |
| Thu 5/7 | 60°F clearing day-game | +0% (afternoon clears) × +20% on day-game lunch lift | +20% lunch / -10% dinner | Day game pushes lunch + early dinner; later dinner soft as guests already left |
| Fri 5/8 | 64°F sun | +5% sunny Fri | +5% | normal Friday + slight weather lift |
| Sat 5/9 | 68°F sun | +5% × +30–60% on Sounders home | +35% range | Best case: sunny Sat + Sounders walk-up + dinner crossover. Worst case: walk-up satiated by neighborhood after 6 PM |
| Sun 5/10 | 65°F partly cloudy | +0 | 0 | baseline |

**Three-scenario output with three call-up triggers:**

```
LOW (400 covers) — plan to this if Tuesday + Wednesday rain hits forecast
                  AND Saturday sees heavy weather. Inventory: down-order
                  $1,800 vs. baseline; staff: cut 2 servers + 1 line cook
                  from Wed; predictability-pay budget: $260.

EXPECTED (486 covers) — default plan. Prep, purchasing, and labor key off
                       this. Staff: per Monday-posted schedule.

HIGH (593 covers) — call-up trigger = Saturday 5/9 reservations cross 100
                   by Thursday 5/7 5 PM. If triggered:
                     1. +1 server, +1 line cook, +1 dishwasher for Sat
                     2. Birria pre-batch + 1 case to Friday's PFG order
                     3. Frozen-margarita pre-batch on Saturday morning
                     4. Hold-back the bar's Sounders watch-party messaging
                        until Thursday 5 PM call-up confirmation
                     Owner: Erica (GM). Decision time: Thursday 5 PM.
```

**Reservation-pace overlay (Saturday matchday):**

| 30-min slot | Reservations on book (5/4) | Capacity target | Status |
|---|---|---|---|
| 12:00 (lunch) | 6 | 14 | open |
| 12:30 (Sounders walk-down) | 8 | 16 | open |
| 1:00 (game time) | 4 | 16 (walk-up fills) | open — walk-up window |
| 4:00 | 6 | 12 | open |
| 5:00 | 14 | 16 | tight |
| 6:00 | 22 | 22 | full |
| 7:00 | 26 | 22 | overbooked by 4 — push 2 to 6:30 + 2 to 7:30 |
| 8:00 | 18 | 22 | open |
| 9:00 | 12 | 16 | open |

**Action: Erica calls 4 of the 7:00 PM bookings on Tuesday AM to re-pace.**

**Item-level forecast (top 5 risk items):**

| Item | Trailing | Projected | Driver | Par-change |
|---|---|---|---|---|
| Birria bowl | 64 | 86 (+34%) | Sounders matchday + birria-LTO carryover from Cinco | +1 case |
| Margarita (fresh-lime) | 184 | 240 (+30%) | matchday bar program lift | +1.5 cases lime, +2 bottles tequila reposado |
| Brunch tacos (Sun) | 48 | 56 (+17%) | normal warm-Sun lift | hold |
| Heavy rain Wed → birria bowl + soup demand | n/a | n/a | rain-day comfort food | +6 portions of birria bowl, +12 portions of pozole |
| Frozen margarita (matchday) | 32 | 60 (+88%) | Sounders walk-up | pre-batch Saturday AM |

**Risk day callouts (top 3):**

| Day | Risk | Decision point | Contingency | Owner |
|---|---|---|---|---|
| Wed 5/6 | Heavy rain at game-time → walk-up canceled but bar still open | Wed 5 PM | If walk-up < 5 by 5:30 PM, cut a server (predictability-pay $60); pivot to bar-only floor; bar gets matchday-night drink-and-cheer-from-the-bar promo | Erica |
| Sat 5/9 | Matchday over-promise on the patio (8 seats only) → 30+ matchday walk-ups stuck | Sat 12 PM | Pre-stage the bar with a Sounders-matchday seating-area; cap walk-up at 90-min wait; offer bar-only | Lucas (FOH lead) |
| Tue 5/5 | Weather-binary on Tue rain probability — could go +25% or -15% | Tue 4 PM | If walk-in by 5:30 PM > 12, prep to high; if < 8, prep to low | Erica |

**Purchasing delta list (Wed 5/6 AM call to PFG):**
- Lime: +1.5 cases (matchday-margarita demand)
- Tequila reposado: +2 bottles to Friday delivery
- Birria-cut beef: +1 case to Friday delivery
- Tortilla (corn): +12 doz to Friday delivery
- All else: hold

**Staffing signal:**
- Tue: keep 2 on-call (paid on-call window per Seattle Secure Scheduling Ordinance — 90-min minimum paid), trigger at 5:30 PM
- Wed (heavy rain): cut 1 server pre-emptively (paid 3-hr predictability-pay premium per ordinance); bar runs the night
- Thu: standard
- Fri: standard +1 line cook (Friday baseline)
- Sat: high-side staff already posted; trigger +1 server / +1 cook / +1 dish if call-up at Thu 5 PM
- Predictability-pay reserve: $260 (Wed cut + 2 Tue on-call paid windows)

**Accuracy feedback (last week, MAPE 11.4%):**

| Day | Forecast | Actual | Δ | Bias |
|---|---|---|---|---|
| Tue (rain forecast 40%, actual rain) | 78 | 56 | -28% | Rain days under-cut walk-up more than the model captures |
| Sat (Mariners home + sun) | 130 | 156 | +20% | Matchday + sun was over-modeled negatively |
| Other 5 days | within 6% | within 6% | within 6% | clean |

**Methodology adjustment (for Wed 5/6 heavy rain):** weight rain-day walk-up at 0.45× baseline (vs. 0.6× currently) — last week's miss confirms rain at game-time fully cancels the lift instead of partially; build into model.

**Owner summary (3 bullets):**
- Risk-week forecast: 400–593 cover band (193-cover spread, widest of the trailing 8 weeks; weather + game-day combine)
- Three call-up triggers: Tue rain at 5:30 PM (binary), Wed heavy rain (almost certain — pre-cut staff and pivot to bar-only), Sat reservations crossing 100 by Thu 5 PM (matchday call-up)
- Predictability-pay reserve: $260 budgeted (Seattle Secure Scheduling Ordinance compliance; full audit log retained per 3-yr ordinance retention requirement)

---

**Distribution and saving:**
- Each example saved to `outputs/forecast/2026-05-04-week-of-05-04.md` (Example 1) and `outputs/forecast/2026-05-04-mothers-day-pre-brief.md` (Example 2) and `outputs/forecast/2026-05-03-risk-week-mariners.md` (Example 3)
- BOH posting: one-page kitchen dashboard from the day-by-day table
- Owner summary: 3-bullet email Mondays before 9 AM
- Accuracy feedback table appended at week-end and rolled forward into next week's baseline

**Severity-gate / handoff tags:** Examples 1 and 2 are routine. Example 3 carries an explicit weather-binary kill-switch on Tuesday and Wednesday — if either triggers, the week's prep / purchasing / labor cascade re-runs at 6 PM the night before. The Saturday call-up trigger requires the GM (not the chef) to make the decision because it touches purchasing + labor + bar program in the same call.
