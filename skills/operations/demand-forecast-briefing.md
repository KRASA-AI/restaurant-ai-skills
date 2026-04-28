---
name: "Demand Forecast Briefing"
category: operations
tools: [claude, chatgpt]
difficulty: intermediate
time_saved: "~30 min/week"
version: 1.1
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

> [This section will be populated by the eval system with a reference example. For now, run the skill with sample input to see output quality.]
