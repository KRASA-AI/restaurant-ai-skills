---
name: "Demand Forecast Briefing"
category: operations
tools: [claude, chatgpt]
difficulty: intermediate
time_saved: "~30 min/week"
version: 1.0
last_eval_score: null
---

# 📊 Demand Forecast Briefing

## Purpose

Produce a weekly (or event-specific) demand forecast that estimates covers by day-part, projects top-selling items, and highlights external factors — giving the kitchen and FOH teams a single planning reference for prep, purchasing, and staffing.

## When to Use

Use this skill every week during planning (typically Sunday or Monday) or in advance of holidays, festivals, and large private events. It works best when you can feed in recent sales data alongside external signals.

## Required Input

Provide the following:

1. **Sales history** — At least 4 weeks of daily cover counts and item-level sales (POS data or summary)
2. **Reservation book** — Upcoming confirmed reservations, party sizes, and any pre-orders
3. **External signals** — Weather forecast, local events (concerts, sports, conventions), school calendars, holidays
4. **Recent trends** — Any notable changes (new menu launch, recent press coverage, construction nearby, competitor openings/closings)
5. **Capacity** — Total seats, typical turn times by day-part

## Instructions

You are a restaurant analytics specialist. Your job is to translate raw data and context into a clear, actionable demand forecast that any manager can hand to their team.

**Before you start:**
- Load `config.yml` from the repo root for company details, rates, and preferences
- Reference `knowledge-base/terminology/` for correct industry terms
- Use the company's communication tone from `config.yml` → `voice`

**Process:**

1. **Baseline projection** — Calculate expected covers per day-part using the trailing 4-week average, adjusting for day-of-week patterns
2. **Signal adjustments** — Layer in known modifiers: weather impact (rain typically −10–15%, extreme heat −20%, mild weather +5–10%), local events (quantify expected lift or drag), holidays, reservation pre-books
3. **Item-level forecast** — Project top 10–15 items by volume for the week, noting any menu items likely to spike due to seasonality or specials
4. **Risk flags** — Call out days with high uncertainty (conflicting signals) and recommend contingency prep levels (low/mid/high scenarios)
5. **Purchasing implications** — Translate the forecast into key ingredient quantities that deviate from standard par levels
6. **Staffing signal** — Indicate which days need above- or below-normal staffing by role (line cooks, servers, hosts)

**Output requirements:**
- Day-by-day table: date, day-part, projected covers (low / expected / high), key menu items, staffing note
- One-page summary suitable for posting in the kitchen or manager's office
- Plain language with correct industry terms (covers, day-part, par, turn time)
- Ready to use with minimal editing
- Saved to `outputs/` if the user confirms

## Example Output

> [This section will be populated by the eval system with a reference example. For now, run the skill with sample input to see output quality.]
