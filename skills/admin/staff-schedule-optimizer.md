---
name: "Staff Schedule Optimizer"
category: admin
tools: [claude, chatgpt]
difficulty: intermediate
time_saved: "~1 hr/schedule"
version: 1.0
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

> [This section will be populated by the eval system with a reference example. For now, run the skill with sample input to see output quality.]
