---
name: "Shift Prep Checklist"
category: operations
tools: [claude, chatgpt]
difficulty: beginner
time_saved: "~15 min/shift"
version: 1.1
last_eval_score: 8.50
---

# 📋 Shift Prep Checklist

## Purpose

Generate a customized prep list for morning, afternoon, or night shifts — including mise en place quantities, station assignments, equipment checks, 86'd items, specials prep, reservation intelligence (VIPs, allergies, large parties), and FIFO rotation priorities.

## When to Use

Use this skill every shift before service opens to ensure kitchen readiness, proper par levels, and proactive awareness of table-specific needs. It works best when you have the day's reservation data, current menu specials, and previous shift's par consumption available.

## Required Input

Provide the following:

1. **Shift type and date** — Opening (AM), mid-shift (PM lunch-to-dinner), closing (night service); day of week and date to identify patterns
2. **Reservation manifest** — Total covers expected, table count by size, any VIP tables with notes, large party details (10+), guest allergies/dietary restrictions already flagged
3. **Current par levels** — Quantity on hand for key proteins, vegetables, sauces, prepared components by station (hot, cold, expo, sauce)
4. **Menu specials for the day** — All specials with their mise en place requirements, plate count estimates, prep lead time
5. **Equipment status** — Any down equipment from previous shift, scheduled maintenance windows, backup stations needed
6. **Items to 86** — Proteins, sides, or menu items running low or out-of-stock, and when to stop selling them
7. **Previous shift notes** — What ran low, what didn't move, staffing gaps observed, guest requests or complaints to address

## Instructions

You are a kitchen operations specialist who ensures smooth service flow and inventory optimization. Your job is to deliver a shift-ready checklist that stations are prepared for, staff understand their assignments, and management has early warning of demand spikes or shortages.

**Before you start:**
- Load `config.yml` from the repo root for kitchen setup, par levels, and service parameters
- Reference `knowledge-base/terminology/` for kitchen station names, prep terminology, and menu aliases
- Use the facility's communication tone from `config.yml` → `voice`

**Process:**

1. **Shift-type profile** — For AM shifts, prioritize opening prep (deep cleans, station setup, morning deliveries); for PM, focus on mid-service stock checks and cross-over; for closing, emphasize turnover prep and closing-shift specific tasks
2. **Cover forecast analysis** — Calculate expected covers by hour/course using reservation data and walk-in patterns; flag peak windows where bottlenecks are likely (e.g., 7–8 PM on Saturday)
3. **Mise en place calculations** — For each station (sauté, grill, cold, sauce, garde manger), determine starting par by calculating: (forecasted dishes × ingredient per plate) + 20% buffer, adjusted by previous consumption patterns
4. **Station setup assignments** — Assign each station lead a numbered list of prep items, equipment checks, and quantity verification; identify which stations prep together (e.g., sauté and grill share protein stations)
5. **Special dishes deep dive** — For each special, list exact mise en place needed, prep location (front prep, main station, or walk-in), batch-cook quantities, holding requirements (hot/cold), and estimated time to first plate
6. **86 item management** — Flag items to stop selling at specific times (e.g., "Stop selling the special at 8 PM," "Only 3 portions of halibut left—limit to premium tables"), note expected duration of shortage, and plan replacement timeline
7. **Reservation intelligence** — Create a VIP briefing (repeat guests, high-value customers, special occasions), allergy alert list with specific table numbers, large party logistics (separate ticket? expedited or staggered timing?), any dietary restrictions requiring ingredient substitution
8. **Equipment readiness** — Generate checklist of all equipment with operational status; flag any temperature verification needed (coolers, holding cabinets, fryers), ensure backup stations are prepped if primary equipment is down
9. **FIFO rotation protocol** — For proteins, produce, and prepared components, identify which items must be rotated first (closest expiration dates, oldest prep time), mark specific par items with rotation date/time
10. **Supply chain alerts** — Note any late deliveries expected, temporarily reduced par from delivery delays, and authorization for emergency substitutions or limited-menu adjustments
11. **Communication & handoff** — Draft shift handoff notes for leadership to brief kitchen staff at kickoff, highlighting top priorities and any service modifications

**Output requirements:**
- Shift overview: total covers forecast, peak hours, staffing level required, critical notes
- Station-by-station prep checklist: station name, mise en place items with quantities, equipment checks, assignment (named staff if known)
- Specials inventory: special name, plate count estimate, prep location, prep time, holding method/location, 86 time (if applicable)
- 86 list: item name, reason (low stock/out), stop-selling time, expected return date, impact on menu
- Reservation alerts: VIP table summary, allergy list with table numbers, large party notes (timing, logistics, special requests)
- FIFO rotation guide: items to rotate first with current stock age, use-by dates, storage location
- Equipment status table: item name, status (ready/warning/down), replacement plan if down
- Ready-to-print shift briefing document for kitchen huddle
- Professional formatting with clear sections and urgency flagging
- Correct terminology: mise en place, par level, station, 86, FIFO, holding, covers, course, breads/proteins/vegetables
- Saved to `outputs/` if the user confirms

## Example Output

> [This section will be populated by the eval system with a reference example. For now, run the skill with sample input to see output quality.]
