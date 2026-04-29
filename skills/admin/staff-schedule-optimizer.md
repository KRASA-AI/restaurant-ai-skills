---
name: "Staff Schedule Optimizer"
category: admin
tools: [claude, chatgpt]
difficulty: intermediate
time_saved: "~1 hr/schedule"
version: 1.1
last_eval_score: null
---

# 📅 Staff Schedule Optimizer

## Purpose

Build a labor-efficient weekly schedule that aligns staffing levels with forecasted demand, respects labor-law constraints, balances employee preferences, and keeps labor cost within target percentage of projected revenue.

## When to Use

Use this skill when building the upcoming week's schedule — ideally after running the Demand Forecast Briefing so projected covers are available. Also useful when re-balancing after call-outs or when onboarding new hires.

## Required Input

Provide the following:

1. **Demand forecast** — Projected covers by day and day-part (from Demand Forecast Briefing or POS forecast)
2. **Staff roster** — Names, roles, certifications (food handler, alcohol service), max hours, availability windows, overtime thresholds
3. **Labor targets** — Target labor-cost percentage (e.g., 25–30% of revenue) and any hard caps on weekly hours
4. **Regulatory rules** — State/local requirements: minimum break durations, maximum consecutive hours, minor-worker restrictions, predictive-scheduling laws if applicable
5. **Preferences & requests** — Time-off requests, preferred shifts, seniority considerations
6. **Historical labor data** — Last 2–4 weeks of actual hours worked vs. scheduled (optional but helps calibrate)

## Instructions

You are a restaurant workforce-planning specialist. Your job is to produce a schedule that keeps service quality high, labor cost controlled, and staff fairly treated.

**Before you start:**
- Load `config.yml` from the repo root for company details, rates, and preferences
- Reference `knowledge-base/terminology/` for correct industry terms
- Use the company's communication tone from `config.yml` → `voice`

**Process:**

1. **Demand-to-labor mapping** — Convert forecasted covers into required labor hours per role per day-part using industry benchmarks (e.g., 1 server per 4–5 tables, 1 line cook per X covers/hour)
2. **Shift construction** — Build shifts that cover required labor windows, minimizing split shifts and short-change turnarounds (less than 10 hours between shifts)
3. **Assignment** — Slot employees into shifts respecting availability, overtime limits, and fair rotation; distribute desirable shifts (Friday/Saturday dinner) equitably over a rolling period
4. **Compliance check** — Verify the draft schedule against all regulatory rules; flag violations
5. **Cost projection** — Calculate total projected labor cost and express as a percentage of forecasted revenue; adjust if outside target range
6. **Contingency plan** — Identify on-call candidates for each high-volume day and note cross-trained staff who can flex between roles
7. **Publication-ready format** — Produce the final schedule in a clean grid format with shift start/end times, assigned station or section, and break windows

**Output requirements:**
- Weekly grid: rows = employees, columns = days, cells = shift time + role/station
- Summary stats: total scheduled hours, projected labor cost, labor-cost %, overtime hours
- Compliance notes (any flags or waivers needed)
- Professional formatting suitable for posting and digital distribution
- Correct industry terminology (labor-cost %, covers-per-labor-hour, clopening, predictive scheduling)
- Ready to use with minimal editing
- Saved to `outputs/` if the user confirms

## Example Output

### Example 1 — Standard Tuesday-Sunday neighborhood full-service week (75-seat, Oregon Fair Work Week Act applies)

**Input:**
- Concept: Cedar & Vine, 75-seat seasonal-American neighborhood concept, Portland OR
- Demand forecast (from Demand Forecast Briefing): 480 covers / week (Tue 50, Wed 55, Thu 70, Fri 95, Sat 130, Sun 80)
- Roster: 14 employees — 3 line cooks (Diego sous, Marcus, Aiden), 1 prep cook (Lina), 1 dishwasher / pantry (Tomás), 5 servers (Priya FOH lead, Sam, Jenna, Carmen, Wes), 2 bartenders (Riley, Jordan), 1 host (Mia), 1 GM working manager (Maria)
- Labor target: 28% of $34K projected revenue ($9,520 labor cap)
- Regulatory: Oregon Fair Work Week Act (Portland) — chain coverage threshold (500+ employees worldwide); the operator is single-unit so the Act does not apply, but the GM has chosen to honor the 14-day advance-post and 10-hour rest-between-shifts rules as house policy
- Preferences: Diego unavailable Sun (recurring); Carmen requests Sat off (one-time, daughter's recital); Wes is closing-only
- Historical: trailing 4 weeks averaged 32.1 hours scheduled vs. 30.8 actual per server (4% no-show / call-out)

**Output — Week of 2026-05-04, posted 2026-04-21 (14-day advance):**

**Weekly grid (server section + bar; BOH on separate sheet, both posted Tuesday 4 PM the prior week):**

| Employee | Tue 5/5 | Wed 5/6 | Thu 5/7 | Fri 5/8 | Sat 5/9 | Sun 5/10 | Hours |
|---|---|---|---|---|---|---|---|
| Maria (GM, working mgr) | 11–8 mid | OFF | 3–close | 3–close | 11–8 mid | OFF | 32 |
| Priya (FOH lead) | OFF | 3–close (sec 3) | 4–close (sec 1) | 4–close (sec 1) | 4–close (sec 1) | 10–4 brunch | 32 |
| Sam (server) | 4–close (sec 2) | 4–close (sec 1) | OFF | 4–close (sec 2) | 4–close (sec 2) | 10–4 brunch (sec 2) | 33 |
| Jenna (server) | OFF | OFF | 4–close (sec 2) | 4–close (sec 2) | 4–close (sec 3) | 10–4 brunch (sec 1) | 25 |
| Carmen (server) | 4–close (sec 1) | 4–close (sec 2) | 4–close (sec 3) | 4–close (sec 3) | OFF (recital) | OFF | 24 |
| Wes (closing only) | OFF | 6–close (sec 4 / floats) | OFF | 6–close (sec 4) | 6–close (sec 4) | OFF | 18 |
| Riley (bar) | 3–close | OFF | 3–close | 3–close | 3–close | OFF | 36 |
| Jordan (bar) | OFF | 3–close | OFF | 5–close (peak only) | 5–close (peak only) | 10–4 brunch bar | 28 |
| Mia (host) | 4–9 | 4–9 | 4–9 | 4–10 | 4–10 | 10–3 | 32 |

**BOH grid (separate sheet, posted same time):**

| Employee | Tue | Wed | Thu | Fri | Sat | Sun | Hours |
|---|---|---|---|---|---|---|---|
| Diego (sous) | 1–close | OFF | 1–close | 1–close | 1–close | OFF | 40 |
| Marcus (line) | 2–close | 2–close | 2–close | OFF | 2–close | 9–3 brunch | 39 |
| Aiden (line) | OFF | 2–close | 2–close | 2–close | 2–close | 9–3 brunch | 38 |
| Lina (prep) | 8–4 | 8–4 | 9–4 | 9–4 | 8–4 | OFF | 38 |
| Tomás (dish/pantry) | 4–close | 4–close | OFF | 4–close | 4–close | 9–close | 39 |

**Summary stats:**

| Metric | Value | Target | Status |
|---|---|---|---|
| Total scheduled hours | 421 | 415 | +1.4% (within tolerance) |
| Projected labor cost | $9,396 | $9,520 cap (28% of $34K) | 27.6% — under cap by 0.4 pts |
| Projected revenue | $34,000 | n/a | from Demand Forecast |
| Overtime hours | 0 | 0 | clean |
| Clopens (close → open same person) | 0 | 0 | clean (Wes-only-closing rule honored) |
| Shifts under 10-hr rest | 0 | 0 | clean |
| Saturday peak coverage | 4 servers + 2 bar + 3 BOH + 1 host + 1 GM | 4 srv / 2 bar / 3 BOH per Demand Forecast | matched |

**Compliance notes:**
- Honored 14-day advance-post per Oregon FWWA standard (posted 2026-04-21 for week of 2026-05-04)
- Honored 10-hr rest between shifts; no clopens
- Carmen's Saturday off documented in roster — schedule rebalanced; Jenna picked up Sat sec 3 (her usual rotation tier)
- Jordan and Marcus both schedule 38–39 hours (under 40-hr OT trigger); cross-trained as flex
- Mia under-18 status check: not applicable (Mia is 22); minor-worker rules did not constrain
- No employee scheduled > 6 consecutive days; no shift > 10 hours

**Contingency plan:**
- High-volume day (Sat 5/9 — 130 covers): on-call = Wes (server) and Tomás (dish, can flex pantry if needed). Trigger: walk-in pace at 6 PM exceeds 40 covers vs. forecast 35.
- BOH cross-train: Aiden trained on sauté and grill; can swap with Marcus station-by-station mid-shift if either calls out.
- FOH cross-train: Priya can run the bar if Riley or Jordan calls out (food-handler + alcohol-service certified).

**Distribution:**
- BOH grid: posted in the kitchen on the back of the walk-in door + emailed to Diego / Marcus / Aiden / Lina / Tomás 2026-04-21 16:00
- FOH grid: posted in the server station + emailed to all FOH 2026-04-21 16:00
- Master spreadsheet: saved to Drive folder `schedules/2026/05/week-of-05-04.xlsx`
- Trade-request channel open in the FOH/BOH Slack until 2026-04-28 (the +14 / -7 window)

---

### Example 2 — Predictive-scheduling-law week (Seattle, Secure Scheduling Ordinance applies)

**Input:**
- Concept: Cantina Verde, 110-seat Tex-Mex with margarita bar, Seattle WA (and 4 sister units in Austin / Houston / Dallas / San Antonio — corporate triggers Seattle Secure Scheduling Ordinance because the brand has 500+ employees globally and 40+ FTE in Seattle)
- Demand forecast: 920 covers / week (event week — Mariners home stand Mon-Wed + Sounders home Sat)
- Roster: 22 employees in the Seattle unit
- Labor target: 26% of $78K projected revenue ($20,280 labor cap)
- Regulatory: Seattle Secure Scheduling Ordinance — 14-day advance posting, predictability pay for any change inside the window (1× hour for added shift, 0.5× for cancelled), rest period 10 hours between shifts (or premium pay), access-to-hours rule (offer existing PT staff additional hours before hiring), good-faith estimate at hire, right-to-request input
- Preferences: 3 servers requested specific time-off; 2 line cooks requested overtime opt-in
- Historical: Seattle unit averages 1.3 schedule-change requests / week from staff post-posting

**Output — Week of 2026-05-11, posted 2026-04-28 (14-day advance, ordinance-compliant):**

**Predictability-pay risk register (built into the schedule, not a post-hoc cleanup):**

| Day | Risk | Mitigation | Owner |
|---|---|---|---|
| Mon 5/11 (Mariners home 7:10 PM) | Walk-in surge from stadium foot traffic | Schedule 2 on-call servers explicitly with paid 90-min on-call window (per ordinance, on-call hours are paid time even if not called in) | GM (Erica) |
| Sat 5/16 (Sounders home 1:30 PM) | Same — afternoon surge into bar from stadium walk-down | Schedule 1 on-call bar | GM |
| Wed 5/13 | Cinco de Mayo carryover demand (week-after holiday) | Build to 90% historical Wed; do not over-schedule (predictability-pay penalty if cut) | GM |

**Access-to-hours offer (ordinance-required):**
- 38 hours of new shifts available this week
- Offered first to existing part-time staff in writing 2026-04-26 (48 hours before posting); 26 hours absorbed by 4 PT staff (Marisol +6, Jorge +8, Ana +6, Lucas +6); 12 remaining hours posted to the trade board for full-time staff who want to flex up

**Weekly grid (excerpt — server section, Sat-heavy day):**

| Employee | Sat 5/16 (Sounders 1:30 + dinner) | Notes |
|---|---|---|
| Erica (GM) | 11–close | working mgr; scheduled, not on-call |
| Lucia (FOH lead) | 12–close (lead, runs sec 1) | +6 access-to-hours absorbed earlier |
| Marisol (server) | 12–9 (sec 2) | bilingual EN/ES — assigned the Sounders-day Spanish-language tables |
| Jorge (server) | 12–9 (sec 3) | |
| Ana (server) | 12–9 (sec 4) | |
| Lucas (server) | 5–close (sec 5, peak only) | closing-only by preference |
| **Hugo** | **on-call 12–3 PM (paid 90-min minimum) → if triggered, 12–close** | **Seattle ordinance: 90-min paid on-call period; if call-in, full shift; if not called, 1.5 hr paid** |
| **Sara** | **on-call 4–6 PM dinner peak (paid 90-min minimum)** | same rule |

**Summary stats:**

| Metric | Value | Target | Status |
|---|---|---|---|
| Total scheduled hours | 1,038 | 1,028 | +1.0% (within tolerance) |
| Projected labor cost | $19,952 | $20,280 cap | 25.6% — under cap by 0.4 pts |
| Predictability-pay reserve | $182 (2 on-call shifts × 1.5 hr × $24 blended + buffer) | n/a | budgeted explicitly |
| Overtime hours | 6 (Diego sous +6, opted in) | OK (opted in, ≤ 8 / wk house cap) | |
| Clopens | 0 | 0 | clean |
| Access-to-hours offer compliance | offered + 48 hrs before post + documented | required by ordinance | clean |
| 14-day advance post | 2026-04-28 for week of 2026-05-11 | required | clean |

**Compliance notes:**
- Schedule posted to all staff via 7shifts and emailed 2026-04-28 16:00 — exactly 14 days before week-start
- Predictability-pay reserve carried explicitly in the labor budget at $182 (any post-posting change inside 14 days adds to this)
- Good-faith estimate refresh: triggered for 1 new hire (Sara, started 2026-04-15) — re-issued GFE with the 5/11 schedule
- Access-to-hours: 38 hours offered to PT staff in writing 2026-04-26 (48 hours before posting); response window honored; written record retained per ordinance
- Right-to-request input: 3 staff submitted scheduling preferences before the post; all 3 accommodated where possible (2 fully, 1 partially with note)
- Rest period: 10-hr minimum between shifts honored on every employee (one near-miss caught in QA — Lucas Mon 5/11 close + Tue 5/12 lunch — moved Tue 5/12 to 12:00 start instead of 11:30)

**Contingency plan:**
- Mariners game (Mon, Tue, Wed): on-call = Hugo (server, opt-in for predictability-pay-triggered call-in). Trigger: walk-in pace by inning 5 exceeds 25 cover increase vs. baseline.
- Sounders game (Sat): on-call = Sara. Trigger: bar pace by 1 PM exceeds 40 covers vs. baseline.
- BOH coverage: 2 line cooks opted in to OT (capped at 8 hr each / week per house policy and Washington state DOL standards for any hour over 40).

**Distribution:**
- 7shifts post + email + printed copy in the back office
- Predictability-pay reserve flagged to the owner for visibility

---

### Example 3 — Mid-week rebuild after Friday-morning callout cluster

**Input:**
- Concept: Cedar & Vine (same as Example 1), week of 2026-05-04 (already posted)
- Disruption: Friday 2026-05-08 8:00 AM — 3 callouts in 90 minutes (Carmen — server, daughter's school nurse called; Aiden — line cook, food poisoning; Tomás — dish/pantry, family emergency)
- Friday demand forecast: 95 covers, peak 7–9 PM
- Constraints: Already inside Oregon Fair Work Week 14-day window — house-policy honors the predictability-pay rule even though Cedar & Vine is single-unit and not strictly covered
- Time of rebuild: 9:00 AM Friday (10 hours before service)

**Output — Friday 2026-05-08 rebuild:**

**Triage (in order of impact):**
1. **Aiden (line cook)** — most service-critical; 2 cooks short on a Saturday-prep + Friday-service day. **Action:** Marcus extends from 2 PM start to 11 AM start (+3 hr), absorbs prep work Aiden was scheduled to do; Diego (sous, already scheduled 1–close) extends to 12:00 start (+1 hr) and runs grill solo with Marcus on sauté; Lina (prep, scheduled 9–4) extends to 9–close (+5 hr) as an extra hand on cold pantry / plating expo; pull Wes early (was scheduled 6 PM closing-only) — call now, ask for 4 PM start (+2 hr) and offer the same closing exit. **Net add: 11 hours; net loss vs. Aiden's 9 scheduled hours: +2 hr ($46 incremental cost).**
2. **Tomás (dish/pantry)** — service-critical at peak. **Action:** Lina (already extended above) covers cold pantry; for dish, call Sasha (off the day, 22 hrs scheduled this week, willing per text) for 4–close (+8 hrs). **Net add: 8 hours vs. Tomás's 8 scheduled; cost-neutral.**
3. **Carmen (server)** — section 3 coverage. **Action:** Pull Jenna early — was scheduled 4–close (Sat sec 3), is off Friday. Call Jenna; offer Friday 4–close at sec 3 + keep Sat shift = Jenna runs Fri-Sat back-to-back at her preferred section. Confirmed via text 9:24 AM. **Net: even.**

**Updated grid (Friday 5/8 only — diff vs. posted):**

| Employee | Originally posted | Rebuilt | Delta |
|---|---|---|---|
| Marcus (line) | OFF | 11 AM – close | +11 hr |
| Diego (sous) | 1 PM – close | 12 PM – close | +1 hr |
| Lina (prep) | 9 AM – 4 PM | 9 AM – close (~10 PM) | +6 hr |
| Wes (server, closing only) | 6 PM – close | 4 PM – close | +2 hr |
| Sasha (dish, was off) | OFF | 4 PM – close | +8 hr |
| Jenna (server) | OFF | 4 PM – close (sec 3) | +8 hr |
| Aiden (line — call-out) | 2 PM – close | OFF (sick) | -8 hr |
| Tomás (dish — call-out) | 4 PM – close | OFF (family emerg.) | -8 hr |
| Carmen (server — call-out) | 4 PM – close (sec 3) | OFF (school) | -8 hr |

**Net cost impact:**
- Hours added: +36
- Hours subtracted: −24
- Net: +12 hours @ blended $24/hr = +$288 incremental Friday labor
- Friday revised labor: original $1,920 → revised $2,208 = +15%
- Week labor: original $9,396 → revised $9,684 = $9,684 / $34K = 28.5% (over the 28% target by 0.5 pts)
- Coverage at peak 7–9 PM: clean (Diego on grill, Marcus on sauté, Lina on pantry/expo, Sasha on dish; FOH: Priya lead sec 1, Sam sec 2, Jenna sec 3, Wes sec 4)

**Compliance / predictability-pay notes (house policy):**
- Cedar & Vine is single-unit and not strictly covered by Oregon FWWA; however, house policy honors the 1× hour added-shift premium for callout-driven additions made inside the 14-day window
- Premium pay budget for this rebuild: 1× added hour × 4 employees × variable hourly rate = $86 estimated, paid out on the next pay cycle
- Marcus, Wes, Sasha, Jenna each receive 1× added-shift premium ; Diego (already scheduled, hours extended on a posted shift) does not trigger the premium under the ordinance text — extensions of an already-posted shift without crossing into a new posted shift are out-of-scope
- Lina extension same posture (already-posted shift extended)
- Documented in the schedule-change log retained for 3 years per ordinance retention requirements

**Communication:**
- Personal calls (not text) to Marcus, Wes, Sasha, Jenna requesting opt-in (each with a clean "no" option)
- All four opted in by 10:30 AM
- Service team on the floor at 11 AM informed at the line-up; revised assignments printed at the pass
- Aiden, Tomás, Carmen acknowledged by GM (Maria) with a "feel better" / "take care of family" text — no rebooking conversation today; that happens next week

**Owner-visibility note:**
- Friday cost variance flagged in the Saturday morning weekly recap to the owner
- Quarter-to-date sick-day pattern: 4 sick days in the trailing 30 days vs. 2 in the prior 30 — flagged to the owner for HR follow-up if the trend persists

**Distribution:**
- Updated grid printed and posted in the kitchen and server station by 11:00 AM
- Updated 7shifts entry filed
- Trade-request channel notified 9:45 AM with the rebuild
- Saved to `outputs/schedule-change-log/2026-05-08-callout-rebuild.md` per house retention policy

---

**Severity-gate / handoff tags:** None of the three examples requires escalation. Example 2's predictability-pay reserve and Example 3's house-policy premium-pay log are both routine and pre-budgeted; if a rebuild costs > $400 incremental in any single day, escalate to the owner before posting per house policy.
