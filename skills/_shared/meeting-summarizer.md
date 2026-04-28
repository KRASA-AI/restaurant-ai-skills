---
name: "Meeting Summarizer"
category: _shared
tools: [claude, chatgpt]
difficulty: beginner
time_saved: "~15 min/meeting"
version: 1.2
last_eval_score: null
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

9. **Health-inspector / incident debrief structure** — For post-inspection or incident reviews: factual narrative, code citations or incident category, immediate corrective actions taken that shift, documented follow-up actions with owners and due dates, training implications, escalation path, owner/legal/insurance notification status, and retention plan for records.

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
