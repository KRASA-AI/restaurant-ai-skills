---
name: "Meeting Summarizer"
category: _shared
tools: [claude, chatgpt]
difficulty: beginner
time_saved: "~15 min/meeting"
version: 1.4
last_eval_score: 9.20
---

# 📝 Meeting Summarizer (Restaurant)

## Purpose

Turn raw notes, a transcript, or a voice-memo dump from a restaurant meeting — pre-shift lineup, weekly manager meeting, monthly owner review, vendor QBR, health-inspector debrief, BEO kickoff, R&D tasting — into a structured recap with decisions, owners, due dates, 86/substitutions, guest callouts, cost implications, and the specific follow-ups the next shift or next meeting needs to close, so nothing slips between service and back office.

## When to Use

Use this skill after any of the following: daily pre-shift lineups (FOH + BOH), weekly manager meetings, monthly P&L / labor / COGS reviews with the owner, vendor QBRs with broadline or specialty distributors, health-inspector or food-safety debriefs, incident reviews (injury, allergy, complaint, walkout, walk-in failure), catering and private-event BEO kickoffs, R&D tastings and menu launches, marketing/LTO planning syncs, staff town halls, and post-shift debriefs after a slammed service. Pair with Shift Prep Checklist (handoff of line-level action items), Supplier Negotiation Brief (QBR follow-through), and Health Inspection Prep (post-inspection corrective-action plan).

## Required Input

Provide the following:

1. **Meeting type** — Pre-shift, weekly manager, monthly owner, vendor QBR, health-inspector debrief, incident review, BEO kickoff, R&D tasting, marketing sync, staff town hall, post-shift debrief
2. **Date, day-part, and location** — Including whether this covers a specific service (Saturday dinner, Sunday brunch) or a reporting period (week ending 4/13)
3. **Attendees** — Names and roles (GM, chef, sous, KM, FOH manager, bar manager, owner, vendor rep, inspector, consultant), who was absent
4. **Raw material** — One of: shorthand notes, a transcript, a voice memo, a Slack/Teams thread, a whiteboard photo, or dictated bullet points
5. **Key numbers referenced** — Covers, labor %, food cost %, prime cost, void %, comp %, top 10 sales mix, top 5 waste SKUs, inventory variance, reservation pace, weather or event calendar ties
6. **Open items from last meeting** — What was promised last time and what's now closed, in-progress, or blocked
7. **Audience for the recap** — Line team (short & operational), manager group (fuller), owner (P&L-tilted), vendor (contract-tilted), inspector (compliance-tilted)
8. **Confidentiality flag** — Any item that must be scrubbed from a wider distribution (staff discipline, wage conversations, legal, guest PII)

## Instructions

You are a restaurant chief-of-staff who has taken notes at thousands of shifts, QBRs, and owner meetings. Your recaps read like a GM wrote them — tight, actionable, quantified, with every owner and due date named.

**Before you start:**
- Load `config.yml` for restaurant name, unit count, concept, reporting-period conventions, brand voice, and the meeting cadence defaults
- Reference `knowledge-base/terminology/` so dish names, POS terms, financial terms, and vendor names are spelled correctly
- Load last week's or last month's recap from `outputs/` so you can close open action items explicitly
- Redact anything flagged confidential before producing the distributed version

**Process:**

1. **Identify the meeting's core purpose** — State in one sentence why the meeting happened and the single decision or outcome it was supposed to drive. Everything in the recap supports or deviates from that purpose.

2. **Separate decisions from discussion** — Decisions are items the group agreed on; discussion is context. Put decisions first with a one-line justification; put discussion second. Long recaps lose line cooks and owners equally.

3. **Name the owner and due date on every action item** — Every action item has (a) a verb, (b) a named owner, (c) a specific due date or service, (d) the definition of done. No "we should," no "team to look into." If an owner was not named in the meeting, flag it explicitly so the GM assigns before distribution.

4. **Surface numbers and targets** — When numbers came up (labor % variance, food-cost spike, cover gap, guest-feedback score), pull them out into a small table. Include target vs. actual vs. delta so the owner and chef can see trend without re-reading prose.

5. **Pre-shift specific structure** — For pre-shift lineups, structure the recap as: 86 list & substitutions, new items or LTOs with pronunciation and allergen notes, VIP/reservation callouts with table and time, special-diet flags by reservation, weather/event context, service goals (attach rate, upsell targets), safety or cleaning focus, staff shout-outs, and a single "one thing to nail tonight."

6. **Manager-meeting specific structure** — For weekly manager meetings, structure as: last week's KPIs vs. targets (covers, labor %, food cost %, guest score, turnover), top issues by P&L line, top guest themes from reviews and comment cards, schedule issues for the coming week, training focus, marketing/LTO status, and top three priorities for the coming week.

7. **Owner-meeting specific structure** — For monthly owner reviews, structure as: P&L snapshot, prime cost trend, labor/COGS variance with root causes, cash position and AP aging headlines, capex or repair requests, HR/hiring status, brand and guest-score trend, strategic items, and approval asks.

8. **Vendor QBR specific structure** — For QBRs, structure as: spend vs. forecast, service-level KPIs (fill rate, on-time %, short-ships), price movement vs. commodity index, contract issues, product quality incidents, upcoming launches or menu changes, and asks (from us to them, and from them to us).

9. **Health-inspector / incident debrief structure** — For post-inspection or incident reviews: factual narrative, code citations or incident category, immediate corrective actions taken that shift, documented follow-up actions with owners and due dates, training implications, escalation path, owner/legal/insurance notification status, and retention plan for records. Note: produce two versions — the internal recap (full detail, retained in GM files) and the staff distribution version (corrective actions + expectations only, no inspector name/badge number). For re-inspection tracking, include a countdown-to-re-inspection callout at the top of the staff version.

10. **Open-items tracker** — Include a short table of open items from prior meetings with status (closed / in-progress / blocked / dropped) and the current owner. Do not let items disappear silently; if an item is dropped, say why.

11. **Risk and blocker callouts** — A short list of things that could derail the next period: a cost exposure, a staffing gap, a compliance deadline, a reservation wave against a short kitchen. Each risk has an owner and a decision point.

12. **Audience-tuned versions** — Produce the line-team version (short, operational, no P&L numbers), the manager version (full), and — when relevant — the owner summary (three bullets) and the vendor-facing or inspector-facing version with anything internal stripped out.

13. **Pre-distribute review** — Read each version aloud. Strip passive voice and weasel words. Verify every number reconciles with the source data. Confirm no confidential item leaked into a wider distribution.

**Output requirements:**
- Meeting title, date, day-part, attendees, absentees
- One-sentence purpose and the decision/outcome
- Decisions table: decision, rationale, effective date
- Action items table: action, owner, due date, definition of done, status
- Numbers table: metric, target, actual, delta, note (when relevant)
- Meeting-type-specific section (pre-shift / manager / owner / QBR / inspector / incident / BEO / tasting)
- Open-items tracker from prior meetings
- Risks & blockers
- Audience-tuned versions (line / manager / owner / external) as needed
- Correct terminology consistent with `knowledge-base/terminology/`
- Confidentiality scrub on any distributed version
- Saved to `outputs/` with date-stamped filename if the user confirms

## Related Skills

- `operations/shift-prep-checklist.md` — Consumes pre-shift recap items as line-level tasks
- `admin/supplier-negotiation-brief.md` — Drives vendor-QBR prep and the post-QBR action items
- `operations/health-inspection-prep.md` — Feeds the post-inspection debrief structure

## Example Output

### Example 1 — Saturday dinner pre-shift lineup

**Input:**
- Meeting type: pre-shift
- Date / day-part / location: 2026-04-25, Saturday dinner, [Restaurant Name] — Main Dining Room
- Attendees: Maria López (GM), Chef Reyes (Exec Chef), Diego (Sous), Priya (FOH manager), Sam (Bar manager); absent: Marcus (KM, off)
- Raw material: 5 minutes of shorthand whiteboard notes from the 4:30 PM lineup
- Key numbers: 142 covers booked (vs. 118 same-Saturday last week); 4 large-party reservations (8+); soft-shell crab special running 24 portions
- Open items from last meeting: water-glass spotting issue (Diego's task — closed); allergen card reprint (Priya's task — in progress, due Monday)
- Audience: line team
- Confidentiality flag: none

**Recap — Saturday Dinner Pre-Shift, 2026-04-25 (line-team version, 285 words):**

**Purpose:** Set the line and floor for a 142-cover Saturday with four 8+ tops and a 24-portion soft-shell crab special.

**86 list & substitutions:**
- 86 the lamb shank (out of fresh demi until Tuesday — sub: braised short rib pappardelle)
- Low on burrata (12 left — confirm with Reyes before pushing the heirloom tomato app)

**New items / LTOs:**
- Soft-shell crab special — 24 portions, $38, contains shellfish + gluten (panko). Pronunciation: "Maryland soft-shell." Pair on the floor with the Albariño BTG (Sam will confirm pour test by 5:00).

**VIP / reservation callouts:**
- 6:30 — Chen party of 6 (David, our wine-club regular). Patio table reserved. Send Sam to greet at the table; champagne welcome on the house per house policy for wine-club birthdays.
- 7:00 — Khan party of 2. Note: peanut allergy on file; no peanut oil at any station tonight, no satay app fired for this ticket. Diego owns the kitchen-side check.
- 8:30 — birthday party of 10 (Foster). Cake brought in by guest; pastry plates the slice with one candle.

**Special-diet flags by reservation:** 1 GF (Khan), 2 dairy-free (Foster), 1 vegan (walk-in flagged on Resy notes).

**Service goals tonight:** 18% wine BTG attach (vs. 14% last Saturday); soft-shell crab specials sold by 8:30 PM.

**Safety / cleaning focus:** Hand-wash check at every station change; sanitizer buckets refreshed every 90 minutes (Diego's call).

**Staff shout-out:** Priya — last Saturday's table turn was the cleanest of the month; the floor saw it.

**One thing to nail tonight:** The Khan peanut-allergy ticket. Diego confirms the kitchen-side check at fire; Priya confirms the floor-side check at delivery. Two-step.

**Action items table:**

| Action | Owner | Due | Definition of done |
|---|---|---|---|
| Confirm Albariño pour with Sam | Sam | 5:00 PM today | Tasting note added to BTG card |
| Burrata 86 trigger to Reyes | Diego | Live (when count hits 6) | Reyes paged on KDS |
| Khan ticket two-step verify | Diego + Priya | Live at 7:00 service | Both initial the ticket |
| Allergen card reprint follow-up | Priya | Monday EOD | Cards in service stations |

**Risks / blockers:** Tomato delivery truck logged 30 min late on the morning route; if it hits the back door past 5:30, the heirloom-tomato app may fire 6 short until the second wave is plated.

---

### Example 2 — Monthly owner P&L review

**Input:**
- Meeting type: monthly owner review
- Date: 2026-04-22, period = March 2026
- Attendees: Owner ([owner_name]), Maria López (GM), Chef Reyes (Exec Chef), CFO consultant ([cfo_name]); absent: none
- Raw material: 90-minute transcript + the March P&L PDF + the prime-cost trend chart
- Key numbers: Sales $612K (vs. $585K plan); food cost 31.2% (vs. 29.5% target, +1.7 pts); labor 28.4% (vs. 30% target, –1.6 pts); prime cost 59.6% (vs. 59.5% target, +0.1 pts); guest-score average 4.6 / 5 (steady)
- Open items from last month: dishwasher repair quote (Maria — closed, repair done $2,400); Q2 LTO calendar (Reyes — in progress)
- Audience: owner (P&L-tilted) + manager group (full)
- Confidentiality flag: a wage-conversation item (line-cook hourly band) must be redacted from the manager-group version

**Recap — Monthly Owner Review, March 2026 (owner-tilted version, ~340 words):**

**Purpose:** Review March P&L, root-cause the food-cost spike, and approve Q2 capex requests.

**Decisions:**
- Approved $4,800 capex for new walk-in shelving (replaces the rusted unit flagged in the 2026-03-12 health-inspector visit). Vendor: KitchenPro. Effective: order Monday.
- Approved an LTO calendar slot for Memorial Day weekend — Chef Reyes to come back with item-level P&L modeling by 2026-05-01.
- Held: no decision on the line-cook hourly band increase pending a labor-market read; revisit at the May review.

**Decisions table:**

| Decision | Rationale | Effective |
|---|---|---|
| Approve walk-in shelving capex ($4,800) | Inspector callout + spoilage trend | Order 2026-04-28 |
| Memorial Day LTO slot | Q2 traffic ramp + margin model needed | LTO modeling due 2026-05-01 |
| Hold line-cook wage band | Need labor-market read | Re-review 2026-05-22 |

**Numbers table:**

| Metric | Target | Actual | Δ | Note |
|---|---|---|---|---|
| Sales | $585K | $612K | +$27K | Strong second-half, two private events |
| Food cost % | 29.5% | 31.2% | +1.7 pts | Beef and dairy commodity move; see root cause |
| Labor % | 30.0% | 28.4% | –1.6 pts | Schedule discipline, two open server slots |
| Prime cost % | 59.5% | 59.6% | +0.1 pts | Inside tolerance |
| Guest score | 4.5 | 4.6 | +0.1 | Steady |

**Food-cost root cause:** Two-thirds of the spike is commodity (beef +6% MoM on the CME index, butter +4% on Urner Barry). One-third is internal: shrink on the burrata station (over-portioning during the heirloom-tomato push) and three short-shipped fish deliveries that forced spot-buys at retail. Recommended actions: (1) re-portion-train the burrata station this week (Diego owns); (2) move one fish line to a backup distributor for May (Maria + Reyes own).

**Action items table:**

| Action | Owner | Due | Definition of done |
|---|---|---|---|
| Order walk-in shelving | Maria | 2026-04-28 | PO sent + ETA confirmed |
| Memorial Day LTO P&L model | Reyes | 2026-05-01 | Item-level cost + price + projected mix |
| Burrata portion retrain | Diego | 2026-04-29 | All AM and PM cooks pass spec check |
| Backup-fish-distributor onboarding | Maria + Reyes | 2026-05-15 | Trial PO landed; quality + price reviewed |
| Labor-market read for line-cook band | [cfo_name] + Maria | 2026-05-22 | 3-comp scrape + recommendation |

**Risks / blockers:**
- Beef commodity index trending up (Cattle Buyers Weekly futures); flag a $0.40 / lb absorption discussion if April mirrors March.
- One sous-chef out for two weeks in May (planned medical leave); Diego covers but no slack on a slammed Saturday.

**Open-items tracker (carry-forward):**

| Item | Status | Owner |
|---|---|---|
| Q2 LTO calendar | In progress | Reyes |
| Dishwasher repair (Feb open item) | Closed | Maria |
| Reputation-software vendor evaluation | Blocked (waiting on demos) | Maria |

**Manager-group version:** Same content, with the line-cook wage-band item removed entirely (confidentiality scrub). Distribute via private Drive folder, not the all-staff Slack.

---

### Example 3 — Vendor QBR (Sysco)

**Input:**
- Meeting type: vendor QBR
- Date: 2026-04-23, Q1 2026 review
- Attendees: Maria López (GM), Chef Reyes, Jordan Reyes (Sysco rep), Pat Singh (Sysco ops manager — joined for second half)
- Raw material: 60-minute transcript + the Q1 spend report
- Key numbers: Q1 spend $186K (vs. $192K forecast, –3%); fill rate 96.4% (vs. 98% SLA, –1.6 pts); on-time % 91% (vs. 95% SLA, –4 pts); 7 short-ships in Q1 (vs. 3 in Q4 2025); two temp-out-of-spec incidents
- Open items from last QBR: chicken-thigh contract price hold (Jordan — closed, held through 2026-06-30); produce-program trial (Pat — in progress)
- Audience: vendor-facing + internal manager copy
- Confidentiality flag: keep our backup-distributor onboarding plan out of the vendor-facing version

**Recap — Sysco Q1 QBR (vendor-facing version, 220 words; manager copy adds 80 words):**

**Spend vs. forecast:** $186K actual vs. $192K forecast (–3%, mostly menu-mix shift toward in-season produce). On track for FY plan.

**Service-level KPIs:**

| KPI | SLA | Q1 actual | Δ |
|---|---|---|---|
| Fill rate | 98% | 96.4% | –1.6 pts |
| On-time % | 95% | 91% | –4 pts |
| Short-ships | <2 / qtr | 7 | +5 |

**Quality incidents:** Two temp-out-of-spec deliveries in March (one chicken case, one pulled-pork case). Cold-chain handoff at the warehouse loading dock identified as the root cause; Sysco committed to a 5:00 AM gate-temp recheck starting 2026-05-01 (Pat owns).

**Asks (us → Sysco):**
- Hold chicken-thigh contract price through Q3 (currently locked through 2026-06-30 — extension request).
- Credit on PO 48231 (short-ship + temp out of spec) — confirmed for the 2026-04-25 statement.
- Quarterly cold-chain audit summary, sent 5 business days before each QBR.

**Asks (Sysco → us):**
- Extend the produce-program trial through Memorial Day to evaluate the in-season swap on tomato and stone fruit.
- Approve a 2026-04-29 product showcase visit at the unit (Reyes confirmed).

**Manager-internal copy adds (confidential, 80 words):** Backup-distributor evaluation continues per the March P&L review; hold this off the vendor-facing version. If Q2 fill rate stays below 97%, escalate to a written remediation plan and consider trialing the backup distributor on the fish line in June.

**Action items table:**

| Action | Owner | Due | Definition of done |
|---|---|---|---|
| Confirm chicken-thigh price extension | Jordan (Sysco) | 2026-05-15 | Written extension to 2026-09-30 |
| 5 AM gate-temp recheck go-live | Pat (Sysco) | 2026-05-01 | First weekly summary delivered |
| Credit on PO 48231 | Jordan (Sysco) | 2026-04-25 statement | Statement reflects credit |
| Q2 cold-chain audit summary | Pat (Sysco) | 5 days before next QBR | Summary in inbox |
| Produce-program trial extension | Reyes + Jordan | Memorial Day | Trial runs through holiday weekend |

---

### Example 4 — Health inspector debrief (post-inspection corrective-action meeting)

**Input:**
- Meeting type: health-inspector debrief
- Date / day-part / location: 2026-05-08, 4:30 PM post-inspection huddle, [Restaurant Name] — back office + BOH
- Attendees: Maria López (GM), Chef Reyes (Exec Chef), Diego (Sous), Priya (FOH manager); absent: Sam (Bar manager, day off)
- Raw material: shorthand notes from a 20-minute debrief immediately after the 2:00–3:45 PM inspection
- Key numbers: final score 88 (B); 2 violations cited (1 Risk Factor 3, corrected on site; 1 non-critical); re-inspection date 2026-05-18
- Open items from last meeting: allergen card reprint (Priya, previously in progress — now confirmed completed 2026-05-05)
- Audience: (a) internal manager recap, full; (b) staff distribution version, corrective actions only
- Confidentiality flag: Inspector name and badge number stay in GM file only; not in the staff distribution version

**Internal manager recap (debrief notes — retain in GM file, 380 words):**

**Meeting title:** Post-Inspection Debrief — 2026-05-08
**Purpose:** Close out the 2026-05-08 inspection, document the two cited violations, assign corrective-action owners and due dates, and prepare for the 2026-05-18 re-inspection.

**Inspection summary:**
- Score: 88 (B)
- Duration: 2:00–3:45 PM, unannounced
- Areas covered: FOH, BOH (hot and cold lines), pantry station, walk-in cooler (proteins), dry storage, hand-washing stations, dish pit, chemical storage, employee health records

**Violation log:**

| # | Code | Category | Description | Corrected on site? | Risk factor |
|---|---|---|---|---|---|
| 1 | CFR §2-301.12 | Employee health & hygiene | Pantry-station hand-wash sink blocked by speed rack | Yes — rack relocated during inspection | Risk Factor 3 |
| 2 | CFR §3-501.16(A) | Temperature control | Walk-in protein shelf reading 41.5°F (limit 41°F) | No — correction due 2026-05-18 | Non-critical |

**Immediate corrective actions taken during inspection:**
- Speed rack moved from in front of the pantry hand-wash station to dry-storage side (Diego, completed 3:15 PM).
- Walk-in thermostat setpoint adjusted –2°F; Reyes ordered replacement wire shelf liner with better airflow (estimated arrival 2026-05-12).

**Action items table:**

| Action | Owner | Due | Definition of done |
|---|---|---|---|
| Add pantry hand-wash station to daily pre-shift station-check | Maria | 2026-05-09 (tonight) | Item live on pre-shift checklist |
| Walk-in replacement shelf liner installed | Reyes | 2026-05-13 | Liner in place; walk-in reading ≤ 40.5°F |
| Walk-in temp log — twice daily readings through re-inspection | Diego (AM) + Priya (PM) | 2026-05-08–2026-05-18 | Log sheet in GM file; all readings ≤ 41°F |
| Prep staff on hand-wash station clearing protocol | Reyes + Diego | Pre-shift 2026-05-09 | All BOH staff verbally confirmed |
| Re-inspection prep walk (full BOH + FOH) | Maria + Reyes | 2026-05-17 PM | Walk-through checklist completed; all stations clear |

**Training implications:** Revisit hand-wash station access protocol in the next monthly food-safety training block. Consider a laminated "DO NOT BLOCK" placard at the pantry station.

**Owner / insurance notification:** Owner notified by text at 3:50 PM (acknowledged). No insurance notification required for a non-critical re-inspection event.

**Records retention:** Full inspection report, corrective-action log, and this recap retained in GM office per local 3-year records requirement.

**Risks / blockers:**
- Walk-in liner delivery slip (vendor out of stock — Reyes is sourcing a second vendor as backup).
- Re-inspection falls on Monday 2026-05-18; ensure the closing manager on Sunday 5/17 night runs the prep walk with Reyes.

**Open-items tracker:**

| Item | Status | Owner |
|---|---|---|
| Allergen card reprint | Closed 2026-05-05 | Priya |

---

**Staff distribution version (corrective actions only — 120 words, appropriate for a printed line brief):**

**Re-inspection: Monday, May 18. 10 days from today.**

We had a routine unannounced inspection today and scored an 88. Two things were cited — both are already being fixed.

**Fixed on the spot:**
- The speed rack was blocking the pantry hand-wash sink. It has a new home. Keep that sink clear, always.

**Fixed this week:**
- Walk-in was 0.5°F above the cold limit. Thermostat adjusted; replacement shelf liner arrives Tuesday. Diego and Priya are logging temps twice a day until the 18th.

**What this means for you:** Same standards as every shift. Pre-shift station-check now includes a hand-wash station clear confirmation at the pantry. No change to service flow.

**Questions: see Maria or Reyes.**

---

### Example 5 — NRA Show 2026 vendor-QBR debrief (multi-unit, consolidated cross-vendor stack)

**Input:**
- Meeting type: vendor QBR — post-trade-show consolidated debrief covering three vendor conversations
- Date / day-part / location: 2026-05-20, 09:00–11:00 AM, Brasa & Bahia corporate office (Atlanta), day after NRA Show 2026 closed (2026-05-19)
- Attendees: Maria Restrepo (Area-GM, 4-unit Brasa & Bahia), Owner Carla Bahia, Chef-Partner Renato Brasa, CFO consultant Tomas Vega; remote: Marc Cohen (R365 AI Solutions Architect — same SA who handled the Black Rock Coffee Bar Innovation Theater case on NRA Show closing day 2026-05-19), James Chen (Crunchtime AI Forecasting product manager), Aaliyah Stone (Leanpath solutions consultant); absent: none material
- Raw material: 90-minute structured debrief notes Maria took on the show floor on 2026-05-17 and 2026-05-19 plus Maria's vendor-by-vendor recap call sheets
- Key numbers referenced: 4-unit consolidated AUV $9.4M; R365 AI ↔ Sysco connector live since 2026-05-15 (5 days before this QBR); Marc Cohen on-site at Buckhead 2026-05-27 to 2026-05-28 for SKU-level item-master clean-up; World Cup 2026 kickoff 2026-06-11 (22 days from this QBR); the 2018 + 2022 World Cup cover data for the two ATL-area Brazilian-fan zip codes (Buckhead North + East Atlanta) are the overlay-validation reference set
- Open items from last meeting (the 2026-04-22 monthly owner review): backup-fish-distributor onboarding (Maria + Renato — in progress, trial PO landed 2026-05-15); Memorial Day LTO P&L model (Renato — closed, Memorial Day weekend covers 2026-05-24 came in at +33% vs. forecast)
- Audience: (a) internal owner-and-area-GM full version with R365 AI license tier in the confidential addendum; (b) chef-and-bar-team distribution version with vendor decisions only; (c) vendor-facing recap to Marc + James + Aaliyah with mutual asks only
- Confidentiality flag: R365 AI license tier kept in the owner-only addendum; the specific Sysco DSR contract pricing kept off all distribution versions; Marc Cohen's named handling of the Black Rock Coffee Bar Innovation Theater case is internally referenceable but stays out of the vendor-facing recap

**Recap — NRA Show 2026 Vendor-QBR Debrief, 2026-05-20 (owner + area-GM internal full version, ~520 words):**

**Meeting title:** NRA Show 2026 consolidated vendor-stack QBR debrief
**Purpose:** Lock the vendor-stack decisions Maria anchored across three booth conversations (R365 AI #6027, Crunchtime AI #4842, Leanpath #4842 same row) into a single 4-unit deployment plan ahead of the World Cup 2026 kickoff window (2026-06-11 to 2026-07-19), with named owners and a consolidated cross-vendor risk-log.

**Decisions table:**

| Decision | Rationale | Effective |
|---|---|---|
| Deploy R365 AI at all 4 Brasa & Bahia units by 2026-06-05 (Midtown, Buckhead, Decatur, East Atlanta) | Pre-World Cup readiness; Marc Cohen on-site at Buckhead 5/27–5/28 to lead the SKU-level item-master clean-up | 2026-06-05 |
| Schedule quarterly category-mapping audit between R365 AI + Sysco + Brasa & Bahia inventory ops | The 2026-05-15 connector go-live exposed three SKU mapping conflicts (see email-drafter Example 5 escalation pattern); a quarterly cadence prevents drift | 2026-Q3 audit on 2026-08-29 |
| 30-day Crunchtime AI Forecasting event-overlay model validation against 2018 + 2022 World Cup cover data for Buckhead North + East Atlanta zip codes | Per-unit match-day cover forecasting confidence-interval is the gating decision for the 4-unit consolidated surge staffing & ordering plan | Validation report due 2026-06-08 from James Chen |
| Leanpath waste-station scale install at Buckhead on 2026-05-27 (paired with the R365 AI Marc Cohen on-site) | Connector-level SKU over-portion attribution is the food-waste-reduction-planner Example 4 close-the-loop requirement; doing both vendor on-sites the same week reduces 4-unit ops disruption | 2026-05-27 install; 4-unit roll-out by 2026-06-15 |
| Consolidated 4-unit ACFB donation pickup route activated 2026-05-20 (already live) | Multi-unit surge waste-volume routing for the World Cup window | LIVE 2026-05-20 |
| Twice-weekly CompostNow per unit starting 2026-06-01 | Per-unit compost capacity ahead of surge waste-volume | 2026-06-01 |
| Cross-vendor single-point-of-failure contingency: all three vendors share a 2026-05-15 connector live-date — Brasa & Bahia retains a 14-day rollback to manual variance reporting if the consolidated dashboard goes down during the World Cup window | The Sinch May 2026 production-paradox study (74% rollback rate for live customer-comms AI agents) is the cautionary anchor — see new admin/ai-pilot-rollback-readiness-brief skill for governance framework | Contingency runbook owned by Maria + Marc Cohen by 2026-06-08 |

**Vendor-by-vendor — R365 AI (booth #6027, Solutions Architect Marc Cohen, Black Rock Coffee Bar 190+ location case study referenced):**

| KPI / item | Status | Δ vs. prior QBR |
|---|---|---|
| Connector live-date | 2026-05-15 ✓ | Originally scheduled 2026-04-30 (15 days slipped — Sysco-side catalog-mapping work) |
| 4-unit deployment timeline | 2026-06-05 target ✓ | New (this QBR) |
| On-site engagement (Buckhead 5/27–5/28) | Confirmed ✓ | New |
| Quarterly category-mapping audit | Anchored on the calendar at 2026-Q3 (2026-08-29) | New |
| Black Rock Coffee Bar case-study learnings applied | Maria flagged 3 takeaways: (1) name a single corporate owner per SKU class; (2) front-load the item-master clean-up before the first surge window; (3) treat the Sysco catalog-side updates as a separate stream from the operator-side updates | New |

**Asks (us → R365 AI):**
- 4-unit Buckhead on-site coverage (Marc Cohen 5/27–5/28; confirmed)
- Written commitment that Sysco catalog-side mapping changes flow through to R365 AI consumer-side in 48 hours (per the email-drafter Example 5 escalation pattern)
- Quarterly category-mapping audit calendar slot

**Asks (R365 AI → us):**
- A 4-unit case-study lookback at 2026-09-30 (post World Cup window) suitable for R365 AI use in the 2026-Q4 marketing cycle — Owner Carla holding sign-off pending the surge results
- Operator participation in the R365 AI 2026-Q4 customer advisory board (one quarterly call, 60 minutes) — Carla confirmed yes

**Vendor-by-vendor — Crunchtime AI Forecasting (booth #4842, PM James Chen):**

| KPI / item | Status | Δ vs. prior QBR |
|---|---|---|
| Event-overlay model validation | 30-day window through 2026-06-08 ✓ | New (this QBR) |
| Reference data set | 2018 + 2022 World Cup cover data for Buckhead North + East Atlanta zip codes; James Chen confirmed availability via the Crunchtime data partnerships team | New |
| Confidence-interval delivery | Written CI by 2026-06-08; gating decision for the consolidated surge staffing & ordering plan | New |
| Per-unit match-day cover forecasting | Will run for 6 days pre-kickoff (2026-06-05 onward) with daily updates | New |

**Asks (us → Crunchtime AI):**
- 30-day overlay model validation against the 2018 + 2022 reference set
- Daily per-unit forecasting through the World Cup window
- A post-window accuracy review with R365 AI consultant Marc Cohen joined (cross-vendor accuracy reconciliation)

**Asks (Crunchtime AI → us):**
- Per-unit POS feed access during the 6-day pre-kickoff window (already in scope under the standard data-sharing terms)
- A 2026-Q4 multi-unit Latin-Caribbean concept case-study contribution (Carla holding sign-off pending the surge results)

**Vendor-by-vendor — Leanpath (booth #4842, solutions consultant Aaliyah Stone):**

| KPI / item | Status | Δ vs. prior QBR |
|---|---|---|
| 2026-05-15 R365 AI connector (Leanpath ↔ R365 AI) | Live ✓ | New |
| Buckhead scale install date | 2026-05-27 (paired with the R365 AI Marc Cohen on-site) ✓ | New |
| 4-unit roll-out | By 2026-06-15 | New |
| SKU-level over-portion attribution via the connector | The Buckhead pão de queijo 5/19 pre-test is the diagnostic case feeding the 6/8 Monday corrective re-spec — per food-waste-reduction-planner Example 4 | New |
| Twice-weekly CompostNow per unit | 2026-06-01 start | New |

**Asks (us → Leanpath):**
- 4-unit scale install completion by 2026-06-15
- The SKU-level over-portion attribution data flowing to the R365 AI consumer side same 48-hour window the operator-side changes do

**Asks (Leanpath → us):**
- Operator participation in the Leanpath 2026-Q4 multi-unit case-study (Carla holding sign-off pending the surge results)

**Numbers table (consolidated cross-vendor dashboard state):**

| Metric | Target | Pre-QBR actual | Δ | Note |
|---|---|---|---|---|
| 4-unit prime-cost variance (R365 AI Dashboard) | ± 1.0 pt | + 0.6 pt (5/15–5/19 window) | Within tolerance | + 1.5 pt is the World Cup window re-review trigger per dynamic-menu-pricing-advisor Example 2 |
| Food cost % (4-unit blended) | 28.0% | 28.8% | + 0.8 pts | Picanha Marfrig AAA passthrough (+9.4%) is the May driver; addressed in the pricing review |
| Per-unit match-day cover forecast confidence | ± 8% | N/A (Crunchtime validation pending) | N/A | Confidence-interval delivery 2026-06-08 |
| Waste-station SKU attribution coverage | 100% by 6/15 | 0% (pre-install) | N/A | Buckhead 5/27 install kicks the clock |
| ACFB donation pickup route | 3×/week consolidated | LIVE | ✓ | Started 2026-05-20 |
| CompostNow per-unit | 2×/week | Pending 6/1 start | ✓ | All 4 units confirmed |

**Risk-log (consolidated cross-vendor, single-point-of-failure flagged):**

| Risk | Likelihood | Impact | Owner | Mitigation |
|---|---|---|---|---|
| Cross-vendor single-point-of-failure (all three vendors on the same 2026-05-15 connector live-date) | Low | High | Maria + Marc Cohen | 14-day rollback to manual variance reporting; contingency runbook by 2026-06-08; see new admin/ai-pilot-rollback-readiness-brief skill for governance framework |
| R365 AI ↔ Sysco category-mapping drift during the surge window | Medium | Medium | Maria + Marc + Pat Singh (Sysco) | Joint clean-up session scheduled per email-drafter Example 5; quarterly audit anchored at 2026-Q3 (2026-08-29) |
| Crunchtime AI Forecasting overlay model accuracy miss on the ATL Brazilian-fan zip codes | Medium | Medium | James Chen + Maria | 2026-06-08 written confidence-interval as the gating decision; per-unit ordering plan can revert to a manual 1.4× lift heuristic if CI > ± 12% |
| Leanpath 4-unit roll-out slip past 6/15 | Low | Low | Aaliyah Stone + Maria | The SKU-level attribution is the food-waste-reduction-planner Example 4 close-the-loop requirement, not a surge-blocker; East Atlanta and Decatur can run the World Cup window on the manual waste-station log if needed |
| Brazil exits group stage (Crunchtime overlay assumes Brazil knockouts) | Medium | Medium | James Chen | Per-unit forecasting model branches at 2026-07-03 group-stage close; mid-window re-staff per the world-cup-2026-surge-playbook |
| Leblon cachaça allocation cap from the distributor through 2026-09-30 | High | Low | Sam (bar manager) | Switch to Avuá at the unit-level if a unit runs allocation-out; no menu price change per the dynamic-menu-pricing-advisor Example 2 alcohol-policy hard-block |

**Open-items tracker (carry-forward):**

| Item | Status | Owner |
|---|---|---|
| Backup-fish-distributor onboarding | In progress (trial PO landed 2026-05-15; quality + price reviewed 2026-05-22; trial extended through Memorial Day weekend 2026-05-25 successfully) — promote to primary on the Bahia line by 2026-06-15 | Renato + Maria |
| Memorial Day LTO P&L model | Closed (Memorial Day weekend covers came in +33% vs. forecast; LTO contribution $ +$12,400 across 4 units; P&L model accurate within ± 4%) | Renato |
| Allergen card reprint (carried from 2026-04-25) | Closed 2026-05-05 | Beatriz (Buckhead) |

**Audience-tuned versions:**
- **Chef-and-bar-team distribution version** (200 words, vendor decisions only — no license-tier or contract-pricing detail; covers the deployment timeline, the Buckhead scale install date, the consolidated ACFB pickup, the twice-weekly CompostNow, and the alcohol-policy reinforcement)
- **Vendor-facing recap to Marc + James + Aaliyah** (180 words, mutual asks only — no cross-vendor risk-log, no single-point-of-failure language that could be misread as a contract-pull threat; emphasizes the 2026-Q4 case-study contribution conditionals)
- **Owner-only confidential addendum** (90 words, R365 AI license tier + specific Sysco DSR contract pricing + the operator's read on Marc Cohen's 5/19 Black Rock Coffee Bar Innovation Theater case as a future Brasa & Bahia case-study comparable)

**Pre-distribute review:**
- Read each version aloud
- Confirmed no license-tier or contract-pricing detail leaks to the team or vendor versions
- Verified all named individuals (Marc Cohen, James Chen, Aaliyah Stone, Pat Singh, Sam, Lucas, Beatriz, Andrea, Diego) match the operator's name conventions across the food-waste-reduction-planner Example 4, dynamic-menu-pricing-advisor Example 2, and email-drafter Examples 5 + 6
- The cross-vendor single-point-of-failure framing is internal-only; vendor-facing recap drops it
