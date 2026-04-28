---
name: "Shift Prep Checklist"
category: operations
tools: [claude, chatgpt]
difficulty: beginner
time_saved: "~15 min/shift"
version: 1.2
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

### Example 1 — Saturday PM dinner shift (full-service, 140 expected covers)

**Input:**
- Shift: Saturday PM dinner, 4:00 PM – 11:00 PM, May 16
- Reservations: 112 booked covers + ~28 walk-in projection = 140 total; 11 deuces, 14 four-tops, 3 six-tops, 1 ten-top (private celebration in the back room)
- VIPs: Table 14 (Cohen anniversary, regular, GM has comped a glass of cava in the past); Table 22 (Patel party, dad's 60th, allergy: tree-nut on one guest); 10-top private (Reyes baby shower, 7:30 seating, no nut, one vegetarian)
- Specials: Halibut crudo with stone-fruit (28 portions plated), lamb shoulder for two ($98, plates 12), chocolate budino with olive oil (40 portions)
- Par status: short rib down to 14 portions (need to braise 8 more by 5:00 PM); mussels light at 6 lb (deliver landed late); lemon ricotta down 2 quarts; sauce demi at par
- Equipment: low-boy under expo running 41°F (target 38°F) — flagged from AM; tech booked for Tuesday; using backup walk-in for hot proteins
- 86 list: bone marrow (out until Wednesday delivery); Brussels sprouts running low — limit to 12 covers
- Previous shift: Friday dinner ran out of halibut by 9:15 PM; one server complaint about expo timing on the 8-top at 8:00 PM

**Shift overview:**

> **Saturday Dinner — May 16 — 140 covers projected**
>
> Peak window: **7:30 PM – 9:00 PM** (62 covers seated in 90 minutes; 6-top and 10-top both seated 7:30). Bottleneck risk: grill station + expo. Staffing: 6 servers + 1 floater + 2 bussers + 1 host + 1 SA on the floor; line is 4 + 2 + pastry + dish.
>
> **Top-3 priorities for Chef in pre-shift:**
> 1. Braise 8 add'l short rib portions by 5:00 PM (Friday burned out at 9:15 — same risk tonight)
> 2. Walk Table 22 allergy with Patel server (Marco) personally; tree-nut, no shared fryer for that table
> 3. Confirm low-boy under expo holds <40°F by 4:30 PM with thermometer log; if not, push cold proteins to backup walk-in for the night

**Station-by-station prep (selected):**

| Station | Lead | Prep items + qty | Equipment check | Notes |
|---|---|---|---|---|
| Cold / garde manger | Lina | Halibut crudo: 28 plates portioned, citrus dressed at 5:30; salads pre-built ×40; bread service ×140 | Low-boy at 38°F (CRITICAL — re-temp at 4:30) | Crudo plates count is the cap — when 28 sold, 86 immediately |
| Sauté | Marco | Mussels: portion 6 lb into 12 batches of 0.5 lb (will sell 14–16 — flag 86 at 12); pasta dough portioned ×60; sauce demi at par | Burner #3 igniter (last week's note — verify) | Mussels are short — push the lamb shoulder to anyone undecided |
| Grill | Theo | Short rib: braise 8 add'l by 5:00 PM (now at 14, target 22); steak portions ×24; lamb shoulder ×12 (at par) | Hood vent re-cleaned AM | Short rib is the Friday-night repeat risk — pre-call when at 6 |
| Pastry | Aiko | Budino ×40; lemon ricotta refill 2 qt by 5:00 PM; cava service for Table 14 + Reyes baby shower | Ice machine ✓ | Reyes table cake at 9:00 PM — pre-set candles by 8:45 |
| Expo | Jose | Plate-up sequence cards updated for the night's specials | Heat lamp ✓; QC station mise ✓ | The 8-top at 8:00 PM is the hardest fire — coordinate with Theo |

**Specials inventory:**

| Special | Plate count | Prep location | Holding | 86 trigger |
|---|---|---|---|---|
| Halibut crudo, stone-fruit | 28 | Cold | 38°F low-boy | Sold 28 → 86 immediately |
| Lamb shoulder for two ($98) | 12 | Grill / sauté pickup | Hot hold 145°F | Sold 12 → 86 |
| Chocolate budino | 40 | Pastry | 38°F | Sold 40 → 86 |

**86 list (read at huddle):**

| Item | Reason | Stop-selling time | Return date |
|---|---|---|---|
| Bone marrow | Out of stock | NOW | Wed delivery |
| Brussels sprouts | Low (6 portions) | When 6 portions sold | Tue delivery |
| Halibut crudo (special) | 28 portions plated only | When 28 sold | Tomorrow's prep |

**Reservation alerts:**

> **Allergy table (PRIORITY):** Table 22 — Patel party of 6, 7:00 PM seating, **one guest tree-nut allergy**. Action: Marco (server) walks the menu with the guest at the table; kitchen plates that guest's order on a fresh board with separate utensils; no shared fryer (Brussels and chips out for that table); Chef Lin signs off on the plate before it leaves expo.
>
> **VIPs:**
> - Table 14 — Cohen anniversary, 6:30 PM seating. Regular. Comp glass of cava (per GM standing offer). Andre serving.
> - Private back room — Reyes baby shower, 10-top, 7:30 PM. One nut-free guest (verified at booking), one vegetarian (no fish, dairy OK). Cake at 9:00 PM (we hold; family brought). Lina + Theo split service with Aiko on dessert.

**FIFO rotation (read at lineup):**

| Item | Stock age | Use-by | Storage | Action |
|---|---|---|---|---|
| Short rib (braised batch from Thursday) | 2 days | Tonight | Walk-in, sheet 2 | Use FIRST before tonight's add'l braise |
| Stone-fruit (peaches for crudo) | 3 days | Tomorrow | Cold low-boy | Cap at 28 plates tonight; rest goes to family meal Sun |
| House sourdough | 1 day | Tomorrow lunch | Bread station | All goes out tonight + bread pudding |

**Equipment status:**

| Item | Status | Plan if down |
|---|---|---|
| Low-boy under expo | ⚠ WARNING (41°F, target 38°F) | Re-temp at 4:30; if >40°F, move cold proteins to backup walk-in for the night; tech Tuesday |
| Burner #3 sauté | ✓ Repaired AM | — |
| Hood vent | ✓ Cleaned this AM | — |

**Kitchen huddle script (4:30 PM):**

> "Saturday — 140 covers, peak 7:30 to 9. Three things: short rib braise needs 8 more by 5 — Theo, that's on you, repeat of Friday if we miss it. Table 22 has a tree-nut allergy at 7 — Marco on the floor, fresh board on plate-up, no shared fryer for that table. Low-boy under expo is reading 41 — Lina re-tempts at 4:30 and we move cold to the backup walk-in if it climbs. 86 the bone marrow and crudo cap is 28. Chef Lin signs the allergy plate. Bring it together at 6 sharp. Let's go."

---

### Example 2 — Tuesday AM opening shift (fast-casual, 95 expected covers)

**Input:**
- Shift: Tuesday AM, 6:00 AM open – 11:30 AM, March 4
- Reservations: walk-in only; trailing 4-week Tuesday avg 95 covers (peak 7:30–8:30 AM commuter rush)
- Specials: avocado toast w/ chili crisp ($14, est. 35 plates), breakfast burrito w/ chorizo ($12, est. 25 plates)
- Par: eggs at par (12 dozen); avocado at par (14); chorizo low (2 lb on hand, will need ~4 lb); cold brew tank at 50% (refill takes 6 hours)
- Equipment: griddle pre-heat 5:30 AM; espresso machine descaled Sunday (clean); all clear
- 86: none
- Previous shift: Monday close noted the cold brew tank running low; chorizo delivery short by 1 case

**Shift overview:**

> **Tuesday AM — Mar 4 — 95 covers projected**
>
> Peak: **7:30 AM – 8:30 AM** (52 covers in 60 min — commuter rush). Staffing: 2 line cooks + 1 expo + 2 baristas + 1 cashier + 1 floater (8:00 AM start).
>
> **Top-3 priorities for AM lead:**
> 1. Pull 4 lb chorizo from walk-in by 6:30 AM, brown 2 lb at 6:45 (par for first wave)
> 2. Refill cold brew tank NOW — 6-hour brew = ready by 12:30 PM (lunch coverage)
> 3. Avocado prep: portion 14 avocados into 35 portions by 6:45 AM; lime + salt acidulate to hold

**Station prep:**

| Station | Lead | Prep items | Notes |
|---|---|---|---|
| Hot line | Sam | Eggs portioned ×60 (cracked into pint containers, salted); chorizo browned 2 lb at 6:45; tortillas warmed at 6:50 | Brown 2 add'l lb of chorizo at 8:00 (peak draw) |
| Cold / build | Reyna | Avocado smashed ×35 portions (with lime + salt to hold green); chili crisp decanted into squeeze bottles | Toast bread at 6:55 ready for 7:00 open |
| Bar | Cam | Espresso machine pulled-shot test by 6:30; cold brew refilled NOW (won't be ready till 12:30); milk pitchers staged | Backup is bottled cold brew — sell at $5 if main runs |
| FOH | Kai | Open POS by 6:50; daily specials card in card holder; restroom check; sweep | Specials script: avo toast w/ chili crisp, breakfast burrito |

**86 list:** none.

**Supply chain alert:** chorizo case short by 1 from Monday delivery — verify tomorrow's PFG delivery includes 2 cases (need to email rep by 9 AM if not on the manifest). Cold brew tank empty — single tank coverage today only; consider pre-brewing 2 batches Sunday night going forward.

**Open-shift huddle script (5:55 AM):**

> "Walk-in only, 95 covers, peak's the 7:30 commute. Sam's browning chorizo at 6:45 — we're tight on it, pull a second 2 lb at 8 sharp. Reyna acidulates the avocados to hold green. Cam's refilling the cold brew tank now — we've got bottled cold brew as the backup until 12:30. Specials are the avo toast and the breakfast burrito. Doors at 7. Eyes up."

---

### Example 3 — Friday PM closing shift (sports bar, 220 covers + watch-party)

**Input:**
- Shift: Friday PM, 4:00 PM – 1:30 AM close, June 12 (World Cup tournament, **Brazil match 8:00 PM ET**)
- Reservations: 88 watch-party reservations (deposits taken on parties of 6+); est. 132 walk-ins = 220 covers; 4 reserved tables in the marquee viewing zone (TVs 1–3)
- VIPs: Brazilian-language coverage: 1 PT-fluent server (Lucas) on the floor for the 7:00 PM seating wave
- Specials: Group Stage Pitcher & Pizza bundle ($42, est. 35 attach), Big Match wing drop ($28, est. 28 attach)
- Par: wings 60 lb (will sell ~50 lb tonight); pitcher beer kegs ×8 (Stella, Modelo, Brahma, Heineken — Brahma is Brazil-match call); pizza dough ×50 balls (par); fryer oil fresh from AM
- Equipment: TVs 1–6 audio-zone tested; projector screen tested; ice machine pre-cleaned May 5 (recent)
- 86: none
- Previous shift: Thursday surge ran 30 wing portions short by 11 PM; multilingual (PT/ES) menu insert printed and distributed
- Compliance: Florida service-charge transparency law effective July 1 — disclosure already on every menu since June 1; tonight's 18% auto-grat on parties of 6+ is on the menu and the kiosk; Lucas reads the PT script at check drop on Brazilian-guest tables

**Shift overview:**

> **Friday — Jun 12 — 220 covers — Brazil match 8:00 PM**
>
> Peak windows: **6:30 PM – 8:00 PM** (pre-match seating wave, 102 covers) and **7:55 PM – 9:30 PM** (kickoff + halftime food rush). Bottleneck risk: fryer (wing drop), pizza oven, and the bar (pitcher pour). Staffing: 8 servers (1 PT-fluent), 3 bartenders, 2 bussers, 1 host, expo, 5 BOH.
>
> **Top-5 priorities for pre-shift:**
> 1. Wings: 60 lb on hand; Thursday went short — call US Foods for Saturday emergency 30 lb if Friday close projects <12 lb remaining
> 2. PT-fluent coverage rule: Lucas runs Tables 4, 7, 11, 12 (Brazilian-guest reservations confirmed at booking)
> 3. Auto-grat disclosure: Lucas reads PT script at check drop on every Brazilian-guest table; do not surprise the guest at check
> 4. Bundle attach goal: 35 Pitcher & Pizza + 28 Wing Drop — server pre-shift includes the bundle pitch script
> 5. TV audio zones: marquee zone (TVs 1–3) on Brazilian feed, side bar on neutral feed, patio sound off on a TV-5 only feed

**86 list:** none yet — flag wings at <15 lb remaining, pizza dough at <8 balls remaining.

**Reservation alerts:**

> **Marquee zone:** TVs 1–3 reserved for 4 watch-party tables (8 / 6 / 6 / 4-top). No table-shares on these. Lucas + Andre split service.
>
> **PT-fluent reservation tables:** Table 4 (Brazilian family of 6, dad's birthday), Table 7 (group of 8 Brazilian fans), Table 11 (couple, Portuguese-only), Table 12 (group of 4, mixed PT/EN). Lucas runs all four; Andre is backup.

**FIFO rotation:**

| Item | Stock age | Action |
|---|---|---|
| Wings (Tue delivery batch) | 3 days | Use FIRST — pull from front of walk-in shelf |
| Pizza dough (yesterday's pulls) | 1 day | Use FIRST before tonight's fresh batch |

**Equipment status:** all systems green. Ice machine recently cleaned (key for high-volume night). Backup ice from beverage walk-in pre-staged in 2 totes by the bar.

**Pre-shift huddle script (3:45 PM):**

> "Friday, 220 covers, Brazil kicks at 8. Three things to nail. One: wings — Thursday went short, do not let that happen tonight. Pre-call when we hit 15 lb. Two: Lucas on the floor for Tables 4, 7, 11, 12 — Brazilian guests, full PT service. The auto-grat script reads at check drop in PT — every table, no surprises. Three: bundles — 35 Pitcher & Pizza, 28 Wing Drop. The script is on the back of the order pad. TVs are zoned: marquee on Brasil TV Globo feed, side bar neutral, patio sound on TV-5. Doors are open. Let's go."

**Cross-references:** for the multilingual scripts and the PT auto-grat language, see World Cup 2026 Surge Playbook Steps 3 and 6. For the bundle copy, see Menu Description Writer. For the wing-supply backup-distributor list, see Supplier Negotiation Brief.
