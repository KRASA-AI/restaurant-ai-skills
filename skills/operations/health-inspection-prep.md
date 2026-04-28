---
name: "Health Inspection Prep"
category: operations
tools: [claude, chatgpt]
difficulty: beginner
time_saved: "~30 min/prep"
version: 1.2
last_eval_score: 9.20
---

# 🔍 Health Inspection Prep

## Purpose

Conduct a comprehensive pre-inspection audit using FDA Food Code standards, identifying compliance gaps across temperature control, sanitation, documentation, and personnel health policies — tailored to inspection jurisdiction and type (routine, complaint-driven, follow-up).

## When to Use

Use this skill 2–4 weeks before a scheduled health inspection, after receiving a complaint-driven inspection notice, or during follow-up inspections. It's essential when jurisdiction requirements vary (HACCP vs. simplified food safety, local vs. state standards) and when you need to prioritize remediation by risk level.

## Required Input

Provide the following:

1. **Facility details** — Restaurant name, type (full-service, QSR, catering), seat count, menu scope (hot/cold holding, raw seafood, complex prep)
2. **Inspection type & jurisdiction** — Routine, complaint-driven, or follow-up; state/county/local agency; any known violation history
3. **Current compliance status** — Most recent inspection report (if available), known problem areas, recent corrective actions taken
4. **Equipment inventory** — Refrigeration units with temperature ranges, hot-holding equipment, sanitizer dispensers, handwashing stations, three-compartment sink setup
5. **Staff details** — Number of food handlers, any recently certified or non-certified staff, employee illness protocols in place
6. **Documentation present** — Supplier invoices, time/temperature logs, cleaning schedules, pest control records, HACCP plans (if applicable)

## Instructions

You are a health-code compliance specialist who ensures restaurants pass inspections and maintain food safety integrity. Your job is to deliver a prioritized, actionable pre-inspection audit that flags critical violations and guides remediation.

**Before you start:**
- Load `config.yml` from the repo root for facility details and preferences
- Reference `knowledge-base/terminology/` for FDA Food Code categories and violation classifications
- Use the facility's communication tone from `config.yml` → `voice`

**Process:**

1. **Jurisdiction and inspection-type assessment** — Identify applicable codes (FDA Food Code, state amendments, local ordinances); differentiate critical violations (immediate threat to health) vs. major (significant risk) vs. minor (low risk)
2. **Temperature control audit** — Review cold storage targets (TCS foods at 41°F or below), hot holding (135°F minimum), cooking temps by item type (165°F poultry, 155°F ground meat, 145°F whole cuts/seafood); flag any equipment out of calibration or missing backup thermometers
3. **Sanitation & cross-contamination review** — Check three-compartment sink setup (wash 110–120°F, rinse, sanitize with correct ppm), color-coded cutting boards by protein type, utensil storage separation, bare-hand-contact prevention policies
4. **Personal hygiene & illness policy check** — Verify handwashing station locations (one per station minimum), soap/paper towel supply, employee health agreement signed, sick-leave protocol documented, no staff with gastrointestinal symptoms scheduled
5. **HACCP/hazard analysis (if applicable)** — For high-risk facilities or jurisdictions requiring HACCP, review hazard identification, critical control points (CCPs), monitoring procedures, and corrective action logs
6. **Pest control & facility maintenance** — Confirm pest control service documentation, no evidence of infestation, pest-proofing (screens, air curtains, sealed penetrations), facility cleanliness
7. **Date labeling & food storage** — Verify all prepared foods labeled with date/time opened, "use by" dates on bulk items, proper rotation (FIFO), no expired items in storage
8. **Documentation completeness** — Collect time/temperature logs, supplier verification records, cleaning logs, chemical storage inventory, training certificates for food-handler certifications and any manager-level certifications required
9. **Corrective action prioritization** — Organize findings into three tiers: (a) critical violations requiring immediate action before inspection, (b) major issues to address during inspection week, (c) minor items for post-inspection follow-up
10. **Inspector communication strategy** — Draft talking points highlighting recent corrective actions, staff training improvements, and system enhancements to demonstrate commitment to compliance

**Output requirements:**
- Executive summary: overall risk level, estimated compliance grade, top 3 critical gaps
- Detailed checklist: violation type, current status, required corrective action, timeline to remediate, responsible party
- Equipment audit table: item name, current condition, temp range/ppm (if applicable), certification status, estimated repair/replacement cost if needed
- Documentation checklist: all required forms, sign-off dates, missing items with acquisition priority
- Staff action items: certifications required, specific training modules, health agreement updates
- Ready-to-print facility maps showing handwashing stations, equipment locations, temperature monitoring points
- Professional formatting suitable for owner/GM review and staff communication
- Correct terminology: critical/major/minor violations, TCS foods, time-temperature control, cross-contamination, HACCP
- Saved to `outputs/` if the user confirms

## Example Output

Three reference outputs at progressively higher stakes — a routine annual pre-inspection on a stable full-service operator, a complaint-driven inspection following a foodborne-illness report on a fast-casual concept, and a follow-up re-inspection after a 78-score routine on a multi-unit QSR. Each is paste-ready into the operator's brief packet for the owner / GM / chef pre-inspection huddle and reuses the exact terminology FDA Food Code 2022 inspectors use.

### Example 1 — Routine annual pre-inspection (full-service, 110-seat, single unit)

```markdown
# Health Inspection Prep — Cedar & Vine, 218 N. Elm St., Portland OR
## Routine annual inspection scheduled 2026-05-12 (Multnomah County Environmental Health, Inspector M. Tran historically)

## Executive Summary
- **Overall risk level:** Low-Medium (last 4 inspections scored 92, 94, 91, 93 — no critical violations in trailing 24 months)
- **Estimated compliance grade if inspected today:** 89 (3 critical gaps below would each be -3 to -5)
- **Top 3 critical gaps to close before May 12:**
  1. Reach-in #2 (raw-seafood prep line) running at 43–44°F (TCS food cold-holding requires 41°F or below) — recurring on weekly internal log; gasket replaced 2026-04-08, still drifting. Order Beverage-Air SR48 OEM gasket + thermostat ($340) installed before May 5.
  2. Sushi prep line: chef-knife handle on raw-fish board moved to cooked-station rack twice in 2026-04-22 lunch service per closing checklist. Re-train sushi team on color-coded utensil rule (yellow handle = poultry, red = raw beef, blue = raw fish, green = produce, white = ready-to-eat) and add the visual board to back-line wall by May 1.
  3. Date labels on house-made stocks (chicken, veal, shellfish) are written in chef's shorthand ("CH 4/22") not the FDA-compliant "Use by 4/29 11pm" format. Switch to pre-printed roll-label printer (DayMark MoveMark, $189) and re-train AM prep team by May 3. Random-pull audit weekly until inspection.

## Detailed Critical / Major / Minor Checklist
| # | Tier | Finding | Corrective Action | Owner | Due |
|---|---|---|---|---|---|
| 1 | Critical | Reach-in #2 cold-hold drift 43–44°F | OEM gasket + thermostat replace; verify 41°F-or-below 24h before reload | Chef Diaz | May 5 |
| 2 | Critical | Cross-contamination risk: yellow-handle knife in raw-fish station | Color-coded utensil re-train + wall chart + AM closing checklist sign-off | Sous Chef Park | May 1 |
| 3 | Critical | Date labels non-compliant with FDA Food Code 3-501.17 (7-day rule) | Switch to DayMark MoveMark pre-printed labels with explicit "Use by mm/dd hh:mm" format | Prep Lead Maria | May 3 |
| 4 | Major | Three-comp sink rinse-water temp tested at 102°F (target 110–120°F) | Adjust mixing valve; verify with stem thermometer at every shift open | Dishwasher Lead | Apr 30 |
| 5 | Major | Hand-sink at expo line: paper towel dispenser was empty during 2026-04-25 9pm pull | Add to hourly walk-through checklist + assign expo expediter as owner | FOH Manager | Apr 30 |
| 6 | Major | Walk-in floor: minor mildew at drain — no infestation, but classified as "facility maintenance" finding | Deep-clean cycle Sat night, schedule monthly sanitizer-bleach mop | Porter Team | Apr 28 |
| 7 | Minor | Pest control log missing the 2026-03 service signature (vendor visited; technician forgot to sign) | Email Orkin rep for back-dated signed copy | GM | Apr 30 |
| 8 | Minor | Employee Illness Agreement on file for 26 of 28 staff — 2 new hires from 2026-04-15 not yet signed | Sign at Tuesday lineup; file in HR binder | GM | Apr 28 |

## Equipment Audit
| Equipment | Status | Reading / Spec | Action |
|---|---|---|---|
| Walk-in cooler (Master-Bilt MBR-08) | Pass | 36–38°F all 24h trailing | Maintain monthly coil-clean |
| Walk-in freezer | Pass | 0–2°F all 24h trailing | Maintain |
| Reach-in #1 (cold line) | Pass | 39–40°F | Maintain |
| Reach-in #2 (raw seafood) | **CRITICAL** | 43–44°F drift | OEM gasket + thermostat $340; replace by May 5 |
| Hot-hold line (Vollrath ServeWell) | Pass | 145–155°F | Maintain |
| Three-comp sink rinse temp | **MAJOR** | 102°F | Mixing valve adjustment Apr 30 |
| Sanitizer (chlorine, three-comp) | Pass | 100 ppm at test strip | Maintain |
| Sanitizer (quat, sani-buckets) | Pass | 200 ppm at test strip | Maintain |
| Hand-sink #1 (line) | Pass | Hot 110°F+, soap, towels | Maintain |
| Hand-sink #2 (expo) | **MAJOR** | Towels found empty 2026-04-25 | Hourly walk-through Apr 30 |
| Hand-sink #3 (dish) | Pass | Hot 110°F+, soap, towels | Maintain |

## Documentation Checklist
| Document | Status | Action |
|---|---|---|
| FDA Food Manager Cert (ServSafe) — Chef Diaz | Current, expires 2027-09 | None |
| Food Handler Cards (28 staff, OR Food Handlers Card) | 26 / 28 current | 2 new hires sign at lineup Apr 28 |
| Time/Temperature logs (last 30 days) | Complete | Print + binder for inspector |
| Three-comp sink ppm logs | Complete | Print |
| Cleaning schedule (daily / weekly / monthly) | Complete | Print |
| Pest control service log (Orkin, monthly) | **GAP — Mar 2026 unsigned** | Email rep for re-signed copy Apr 30 |
| Supplier invoices (Sysco, US Foods, local produce, fish) | Complete; 24-month archive | Print last 90 days |
| Employee Illness Agreement | 26 / 28 signed | Tuesday lineup completion |

## Staff Action Items
- Sushi team: 30-min re-train on color-coded utensil rule + visual wall chart, scheduled Tuesday Apr 28 4pm pre-shift (Sous Chef Park leads)
- AM prep team: 20-min re-train on DayMark MoveMark date-label printer + the explicit "Use by mm/dd hh:mm" format, Wednesday Apr 29 9am (Prep Lead Maria leads)
- All staff: 5-min lineup huddle on hand-sink hourly walk-through ownership starting Apr 30 (GM leads)

## Inspector Communication Talking Points (5 minutes)
1. "Inspector Tran, since the September 2025 routine we've added a weekly internal walk-through binder — happy to share the last 12 weeks." (Demonstrates self-audit posture.)
2. "We replaced the reach-in #2 gasket and thermostat on May 5 — the temp log shows 39–40°F cold-hold for the 7 days prior to today; the prior drift is documented and remediated." (Pre-empts the obvious finding.)
3. "We rolled out the DayMark MoveMark date-label printer May 3 — every TCS prep item now carries the explicit Use-by date and time. Walk-in raw-fish station is the easiest place to check." (Invites the inspector to look at the win.)
4. "On the cross-contamination front, we re-trained the sushi team May 1 on the color-coded utensil rule. The wall chart is at the back-line. We're happy to walk through the closing checklist sign-off." (Shows the systemic fix.)
5. "Are there any new state amendments since our September 2025 inspection we should be aware of?" (Closes with a relationship question; signals partnership.)

## Risk Mitigation Plan (Inspection Day)
- 6am: GM walk-through with the critical-violations remediation binder open at each station
- 7am: Pre-shift huddle reminding all staff of the Inspector Communication etiquette (if asked, "Yes, the chef is in the kitchen — I'll get him") and the no-glove-on-phone rule
- 9am: Sous chef walks the line one more time on cold-hold + utensil placement
- Inspector arrival: GM greets, offers the binder, walks the inspector through the corrective-actions list before the inspector starts
```

### Example 2 — Complaint-driven inspection (fast-casual, 60-seat, post-foodborne-illness report)

```markdown
# Health Inspection Prep — Roja Bowls, 1145 Mass Ave, Cambridge MA
## Complaint-driven inspection scheduled 2026-04-29 (City of Cambridge ISD; complaint #2026-0418-CB filed by guest 2026-04-18 alleging gastrointestinal illness 6 hours after 2026-04-17 lunch)

**ALERT — HIGH STAKES:** Complaint-driven inspection following a foodborne-illness allegation. Inspector arrives unannounced. The inspection will be unannounced re-visit class with full pull-and-test authority on TCS items in service AND a 24-hour log review for the alleged exposure window. **Owner / GM / Chef must be on-site through the duration. Counsel notified 2026-04-19. Insurance carrier (CBIZ) notified 2026-04-19.** This brief is for operational pre-inspection ONLY — do not use any of these materials in any guest-facing communication; the holding-statement on the alleged illness is owned by counsel and is strictly limited to "We are cooperating fully with the city's review."

## Executive Summary
- **Overall risk level:** HIGH
- **Estimated compliance grade if inspected today:** Indeterminate — the foodborne-illness allegation is the headline; technical compliance is secondary. A clean technical inspection does not clear the allegation; the city's review is parallel.
- **Top 3 critical gaps to close before Apr 29:**
  1. **Bowl-prep line cold-hold log gap.** Internal temp logs for 2026-04-17 11am–3pm window (alleged exposure) are written in 30-min intervals but the 12:30pm and 2:00pm entries are blank. Reconstruct from the digital cooler-monitoring app (CoolerSense, time-stamped to the second) and assemble a parallel reconstruction binder by Apr 27. Have an entry for every 30-min interval on the alleged exposure day.
  2. **Cilantro / scallion / corn-salsa cold-prep is held in a deli-pan-on-ice configuration.** The ice was last replenished at 11:15am on 2026-04-17 per the closing video review; FDA Food Code 3-501.16 requires TCS items at 41°F or below, and an ice bath that has melted by 1:00pm cannot hold the pan at 41°F. Switch to a Cambro CRPRO refrigerated pan-cube (already on the kitchen wishlist; expedite-ship $1,250 by Apr 26) before re-opening the bowl line.
  3. **Sick-leave protocol on the 2026-04-17 dinner-shift roster.** One bowl-line cook (J. Velasquez) called in sick 2026-04-19 with what was reported as "stomach flu"; the city will ask whether anyone on the 2026-04-17 shift had been symptomatic. Pull the on-shift exclusion / restriction logs (FDA Food Code 2-201.11 requires reporting on Norovirus, Salmonella, Shigella, Shiga-toxin E. coli, Hep A) and any timecard records for the shift. If any staff was symptomatic on Apr 17, the FDA-required 24-hour symptom-free exclusion may apply retroactively. **Counsel reviews this before any statement is offered to the inspector.**

## Detailed Critical / Major / Minor Checklist
| # | Tier | Finding | Corrective Action | Owner | Due |
|---|---|---|---|---|---|
| 1 | Critical | Cold-hold log gap on alleged exposure window | Reconstruct from CoolerSense app + assemble parallel reconstruction binder | Chef Patel | Apr 27 |
| 2 | Critical | Deli-pan-on-ice cold-hold inadequate for the bowl line | Replace with Cambro CRPRO refrigerated pan-cube (expedite ship $1,250) | GM Liu | Apr 26 |
| 3 | Critical | Reporting log on the 2026-04-17 shift not yet reconstructed | Pull timecards + sick-leave records; share with counsel before sharing with inspector | GM Liu / Counsel | Apr 27 |
| 4 | Critical | Hold-and-test all open product from the 2026-04-17 service window (chicken, beef-barbacoa, corn-salsa, cilantro-scallion, salsa-roja, salsa-verde) | Pull representative sample from each lot; chain-of-custody to inspector | Chef Patel | Apr 28 |
| 5 | Major | Final-cook temperature log on the 2026-04-17 chicken batch is missing the second-batch entry (the 1:30pm batch) | Reconstruct from POS-linked smoker app + Sous chef interview | Sous Chef | Apr 27 |
| 6 | Major | Three-comp sink ppm log shows a 0-ppm strip-test on 2026-04-17 5pm (sanitizer container empty) — staff swapped within 4 minutes per the closing video, but the technical violation stands | Document the 4-minute remediation; show the video to the inspector if asked | GM Liu | Apr 28 |

## Hold-and-Test Plan (executed by Apr 28)
- Pull a 4-oz representative sample of each TCS item still in inventory from the 2026-04-17 service-day lot: chicken, beef-barbacoa, corn-salsa, cilantro-scallion, salsa-roja, salsa-verde, queso, brown-rice, white-rice, pinto, black-bean
- Chain-of-custody form per sample: pulled by, time, lot tag, holding temp, hand-off to inspector or to the city-designated lab
- Pull and freeze 1L of the post-mix Coke and Diet Coke from the soda-fountain heads (allegation referenced "iced beverages")
- Photograph each pull with timestamp; cc inspector + counsel

## Documentation Pack for the Inspector
| Document | Owner | Status |
|---|---|---|
| Reconstructed cold-hold log Apr 17 11am–10pm | Chef Patel | Apr 27 |
| Reconstructed cook-temperature log Apr 17 | Sous Chef | Apr 27 |
| Three-comp sink ppm + temperature log Apr 17 | Dish Lead | Pulled |
| Sick-leave / exclusion / restriction log Apr 17 shift | GM Liu / Counsel | Counsel reviews before share |
| Supplier invoices Apr 13–17 (chicken, beef, produce, dairy) | GM Liu | Pulled |
| Pest control log + Apr 14 service slip | GM Liu | Pulled |
| Food Manager Cert (ServSafe) — Chef Patel | Chef Patel | Current |
| Food Handler Cards (12 staff) | GM Liu | 11 / 12 current; one signs Apr 27 |
| Closing-video archive (cloud, last 14 days) | GM Liu | Available for inspector if requested |

## Inspector Communication Posture (counsel-cleared)
- The owner / GM / chef are on-site for the duration
- Posture: cooperative, factual, no admission of fault, no denial of illness, no public-facing comment of any kind
- If asked about the complaint specifically: "We are cooperating fully with the city's review. The owner and counsel are the points of contact."
- If asked about the alleged exposure window: walk through the reconstructed logs in chronological order; do not editorialize
- All public-facing communication on the alleged illness is owned by counsel — staff is briefed at Tuesday lineup that no statement of any kind goes out without counsel sign-off

## Operational Posture (Apr 22–29)
- Bowl line: deli-pan-on-ice REMOVED Apr 22; line operates with backup-walk-in pulls (4 small-pan rotations per service; pull every 90 min; document each pull)
- Cambro CRPRO refrigerated pan-cube installed and validated by Apr 26 — bowl line returns to normal operation Apr 27
- Sick-leave protocol re-iterated at lineup: any staff symptomatic at any time within 24 hours of a scheduled shift reports immediately; pay-protection guarantee on disclosed symptoms (per the brand's existing policy)
- 5pm closing video uploaded to cloud nightly; 30-day archive retained
- Brand-protection: no social posts on the brand's accounts during the inspection window; any DMs / comments routed to the brand-protection lead and counsel
```

### Example 3 — Follow-up re-inspection after a 78-score routine (multi-unit QSR, store #14)

```markdown
# Health Inspection Prep — Bao Burger #14, 2840 SE Powell Blvd, Portland OR
## Follow-up re-inspection scheduled 2026-05-04 (Multnomah County, Inspector R. Okafor; original 2026-04-13 routine scored 78 with 4 critical / 6 major / 3 minor — store is on a 30-day reinspection clock)

## Executive Summary
- **Overall risk level:** Medium-High (78 was the worst score in the 18-store chain in trailing 12 months; the brand-side Director of Operations is on-site for the reinspection)
- **Estimated compliance grade if inspected today:** 91–94 (all 4 prior critical violations remediated and verified by 2026-04-30; the 6 major / 3 minor items have closure dates and are at 100% complete)
- **Top 3 critical gaps already closed (verification ready):**
  1. **Critical #1 — Hot-hold cabinet running 128°F (target 135°F+).** Vollrath ServeWell hot-hold cabinet replaced 2026-04-22 ($2,180); two-week temp-log run shows 145–158°F across 14 days. Photo + receipt + log binder ready.
  2. **Critical #2 — Raw-chicken thawing in the prep sink (no continuous cold-water flow, no ice).** Re-trained AM prep team 2026-04-15 on FDA Food Code 3-501.13 thaw-method-of-record (refrigeration thaw or running-water-below-70°F-with-continuous-flow). Wall chart added; AM-prep daily checklist sign-off live since 2026-04-16.
  3. **Critical #3 — No food-handler card for two staff hired in March.** Both staff completed Oregon Food Handlers Card by 2026-04-18; certificates filed.
  4. **Critical #4 — Date labels missing on 4 of 11 prepared TCS items (kimchi mayo, sweet-soy aioli, pickled daikon, garlic confit).** DayMark MoveMark printer installed 2026-04-20; all 11 prepared items now carry "Use by mm/dd hh:mm". 14-day audit binder shows zero gaps.

## Detailed Status Table — All 13 Original Findings
| # | Tier | Original Finding | Status | Closure Date | Verification |
|---|---|---|---|---|---|
| 1 | Critical | Hot-hold 128°F | CLOSED | Apr 22 | New cabinet + 14-day log |
| 2 | Critical | Raw-chicken thaw method | CLOSED | Apr 15 | Re-train + wall chart + checklist |
| 3 | Critical | Two staff w/o food-handler card | CLOSED | Apr 18 | Certificates filed |
| 4 | Critical | Date labels missing on 4 items | CLOSED | Apr 20 | DayMark printer + 14-day audit |
| 5 | Major | Three-comp sink rinse temp 104°F | CLOSED | Apr 16 | Mixing valve replaced; daily verify |
| 6 | Major | Sanitizer (quat) at 150 ppm (target 200–400) | CLOSED | Apr 15 | Auto-dispenser calibrated; daily test-strip log |
| 7 | Major | Hand-sink at fryer station: no soap | CLOSED | Apr 14 | Wall-mount dispenser installed; hourly walk |
| 8 | Major | Cross-contamination: yellow-handle tongs in raw-beef station | CLOSED | Apr 15 | Color-coded utensil re-train + chart |
| 9 | Major | Walk-in floor: standing water at drain | CLOSED | Apr 23 | Drain rebuilt by plumber; weekly clean |
| 10 | Major | Pest log: missing two months of service signatures | CLOSED | Apr 17 | Vendor (Western Exterminator) provided back-dated signed log |
| 11 | Minor | Employee illness agreement: 3 staff missing | CLOSED | Apr 14 | All 3 signed; HR binder updated |
| 12 | Minor | Chemical storage: bleach next to dry storage flour | CLOSED | Apr 14 | Chemicals relocated to bottom-shelf locked cabinet |
| 13 | Minor | Personal beverage on prep line | CLOSED | Apr 14 | Lineup re-train + visual wall sign |

## Documentation Pack for the Inspector
- 14-day temp logs (hot-hold, walk-in, walk-in freezer, reach-ins) — printed
- 14-day three-comp sink temp + ppm log — printed
- 14-day food-handler / hand-sink supply walk-through checklist (signed by closing manager) — printed
- DayMark MoveMark date-label audit binder (random pulls every Tuesday + Friday for 14 days, zero gaps) — printed
- Receipt for new Vollrath ServeWell hot-hold cabinet ($2,180, installed Apr 22) — copy
- Plumber invoice for walk-in drain rebuild ($580, Apr 23) — copy
- Updated wall-chart photos: color-coded utensil rule, raw-chicken thaw method, hand-sink hourly walk — printed
- Re-training sign-off sheets (AM prep, sushi line, FOH) — printed
- Brand-side Director of Operations site-visit log Apr 28–May 3 — printed
- Cumulative store-#14 score-history chart trailing 24 months (showing the 78 as a single-event outlier on a baseline of 91+) — included

## Inspector Communication Talking Points (counsel-aware; cooperative posture)
1. "Inspector Okafor, since April 13 we've closed all 13 findings — 4 critical, 6 major, 3 minor. The binder on the counter walks each one with the closure date and the verification artifact. We're happy to walk it together or have you point at any one item first."
2. "On the hot-hold cabinet specifically, we replaced the unit on April 22 — the receipt is in the binder; the 14-day temp log shows 145–158°F across the run. The cabinet sits at the same station as the prior one, so you can see the install."
3. "On the raw-chicken thaw method, we re-trained the AM prep team April 15. The wall chart is on the back-line, and the AM-prep daily checklist sign-off is in the binder for every day since."
4. "On the date labels, we installed the DayMark MoveMark printer April 20 — every TCS prep item now carries the Use-by date and time. The audit binder shows two random pulls per week for 14 days, zero gaps."
5. "Brand-side, our Director of Operations has been on-site since April 28 — she'll be on-site through today. She's available if any item needs a brand-side response."

## Operational Posture (Inspection Day)
- 5am: Director of Operations + GM walk-through with the closure binder
- 6am: Pre-shift huddle on inspector-etiquette (if asked, name + role + "I'll grab the GM"; no editorializing on the prior 78)
- 7am: Sous chef walks the line on hot-hold + thaw method + utensil placement + date labels
- Inspector arrival: GM greets, hands the closure binder, walks the 13 findings before the inspector starts
- Director of Operations remains on-site for full inspection duration; counsel on speed-dial
- Post-inspection: same-day debrief call to brand-side leadership; new score posted to brand-side store-execution dashboard within 24 hours
```
