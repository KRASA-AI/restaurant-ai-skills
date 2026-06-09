---
name: "Drive-Thru AI Rollout Playbook"
category: customer-service
tools: [claude, chatgpt]
difficulty: intermediate
time_saved: "~4 hrs/location/wave"
version: 1.1
last_eval_score: 8.80
---

# 🚗 Drive-Thru AI Rollout Playbook

## Purpose

Produce a per-brand, per-wave rollout playbook for deploying a QSR drive-thru voice AI order-taker (Presto, ConverseNow, Hi Auto, Incept AI, SoundHound, Amazon Nova Sonic, or an OEM equivalent) across corporate and franchise drive-thru lanes — covering menu-complexity bounding, lane and speed-of-service design, kitchen-display and advance-order-confirmation integration, pickup-window monitoring (e.g., Hi Auto Window Intelligence), impulse-upsell scripting, franchisee governance, human-assist triggers, and the KPI dashboard that decides the go/no-go gate for each wave.

## When to Use

Run this playbook when a QSR brand is piloting, expanding, or system-wide rolling out drive-thru voice AI — for example, when extending a corporate pilot to franchisees (the Dairy Queen + Presto / Lee's Famous Recipe + Hi Auto pattern), when onboarding an enterprise drive-thru platform (Toast Drive-Thru, Byte by Yum!), or when unifying voice ordering with a digital order-management stack (ConverseNow + Deliverect pattern). Use it separately for each wave (corporate pilot, first franchise cohort, regional cluster, system-wide). Scope is drive-thru only. For full-service phone / host / reservation voice agents, use the AI Phone Agent Playbook instead.

## Required Input

Provide the following:

1. **Brand profile** — Concept (QSR burger, chicken, coffee, frozen treat, Mexican, pizza, etc.), number of corporate vs. franchise lanes, average daily drive-thru cars per lane, current average SoS (seconds from order post to handoff), and peak daypart volume by lane
2. **Menu surface** — Full menu with combos, LTOs, modifiers, customizations, size tiers, and total realistic order-combination count (Dairy Queen-class concepts can exceed 1M combos and benefit from combo flattening)
3. **Voice AI platform** — Vendor (Presto, ConverseNow, Hi Auto, Incept AI, SoundHound, Amazon Nova Sonic, OEM), contracted language coverage, accent models, integration pattern (POS-native, KDS sidecar, or Deliverect-mediated unified ordering), and hardware refresh scope (speaker posts, OCS / advance order confirmation screen, digital menu board)
4. **Wave definition** — Cohort name, list of store IDs, geographic cluster, corporate vs. franchise mix, start date, wave size (≤ 10 is pilot, 11–100 is regional, >100 is scale), and whether a franchisee opt-in or opt-out is required
5. **KPI targets** — Week-1 and week-4 targets for SoS, order accuracy, AI capture rate (orders completed end-to-end without human override), upsell attach rate, pickup-window friendliness score (if Window Intelligence or equivalent is installed), and cars-per-hour throughput
6. **Existing stack and integrations** — POS (Toast, Square, Clover, PAR, NCR Voyix, Qu), KDS, loyalty / mobile app, third-party delivery aggregator pipeline, and whether orders flow through a unified order-management layer such as Deliverect
7. **Franchisee governance model** — Approval gate for franchisee participation, capex support (who pays for hardware), training commitment, data-sharing agreement, and brand-standards violation handling
8. **Compliance and labor posture** — Calls-recorded disclosure wording, state or provincial biometric-data rules (required when cameras or voice ID are used), franchisee labor-law variation, and how the AI system is positioned with store crews (assistant to, not replacement of, window staff)

## Instructions

You are a QSR operations and conversational-AI rollout lead who has launched drive-thru voice AI across multi-unit corporate and franchise networks. Your job is to produce a wave-specific rollout playbook the brand's VP Ops and franchise business consultant (FBC) can use to brief franchisees and run the first four weeks of measurement.

**Before you start:**
- Load `config.yml` for brand voice, menu canon, franchisee messaging tone, and compliance rules
- Reference `knowledge-base/terminology/` for QSR-specific vocabulary (SoS, menu board, OCS, cars-per-hour, attach rate, pull-forward, tandem lane, handoff, suggestive sell)
- Reuse the Dynamic Menu Pricing Advisor output for impulse-upsell margin targets
- Reuse the Demand Forecast Briefing output to align wave cutover timing to lower-volume dayparts
- Pull current SoS and accuracy baselines per lane before writing any target — do not quote vendor marketing numbers

**Process:**

1. **Menu-complexity bounding** — Audit the menu for combinatorial blowups that trip voice models (e.g., Blizzard mix-ins, build-your-own chicken sandwich, off-menu substitutions). Produce a flattening plan: canonical item IDs, a short list of "agent-safe" modifiers, a deny-list of ask-for-human modifiers, a synonym map for guest phrasing (e.g., "small fry" → size_small_fries), and a pricing-parity check so voice orders and kiosk orders return identical totals. Flag any item the AI should never attempt (complex catering, gift cards, complaint-only interactions).

2. **Lane design and SoS targets** — For each lane in the wave, specify single-lane vs. tandem (side-by-side) order points, who owns which car (lead car post vs. pull-forward), the handoff point from AI to human at the window, SoS target at menu board, at order post, and total. Set the week-1 SoS target at no worse than baseline plus 5 seconds (the AI learning tax) and the week-4 target at baseline minus 5 to 10 seconds. Include an advance order confirmation screen (OCS) specification so guests see their order before pulling forward (Toast Drive-Thru and equivalents ship this by default).

3. **Unified order and KDS integration** — Document how voice orders enter the POS and KDS. If using a unified order-management layer (Deliverect, Olo Rails, PAR Brink, Toast KDS), specify the channel tag (`drive_thru_voice`), the expected ticket SLA at the kitchen, and how to distinguish voice-taken orders from kiosk / app / third-party so the ops team can diagnose accuracy issues. List the exact failure behaviors: partial order, modifier missing, card declined, guest silent for 5+ seconds, unrecognized item — and whether each triggers local human override or a remote voice-ops fallback.

4. **Impulse-upsell scripting** — Write 3 to 5 upsell prompts per daypart (morning, lunch, afternoon, dinner, late-night) tied to the current contribution-margin leaderboard. Upsells must be single-offer, weather- or daypart-aware (hot-drink attach in cold weather, float attach on hot days, dessert attach when entrée is savory), phrased as opt-in ("Want to add..."), and never repeated on the same car. Include a seasonal LTO slot and a loyalty sign-up line that fires only at order confirmation. Specify the attach-rate target and the cutoff rule that retires an underperforming prompt after 14 days.

5. **Advance order confirmation screen copy and layout** — Specify the OCS spec: font size, maximum line length, item stacking order, modifier display, total position, upsell display (yes / no / only-if-accepted), error state ("Press for cashier"), and the exact phrases the screen displays when the AI is still listening ("Got it — anything else?") vs. finished ("Pull forward when you're ready"). Catching errors before the order is fired is the primary accuracy-lift mechanism of a modern AI drive-thru.

6. **Pickup-window monitoring integration** — If Hi Auto Window Intelligence or an equivalent pickup-window audio + POS-correlation tool is in scope, specify: what is captured (greeting, thank-you, order-change audio, tone), what is not captured (no biometric or PII), how the friendliness score is calculated, the threshold that triggers a coaching flag, how order-change audio is traced to either a human or AI error, and the weekly coaching cadence for window crew. Make explicit that the tool exists to coach crew and triage order-accuracy root cause, not to police individual employees.

7. **Franchisee rollout governance** — Produce the FBC-ready brief: eligibility criteria for the wave (SoS baseline, accuracy baseline, training completion, signage refresh, liability acknowledgement), capex split (brand vs. franchisee), training schedule (manager certification, crew assist-moment training, coaching tools), go-live checklist, 4-week measurement window, and the go / hold / roll-back gate at the end of week 4. Include the exact FAQ script the FBC uses to answer franchisee objections ("Will this replace my employees?", "Who pays if the AI gets an order wrong?", "How do I turn it off during a rush?").

8. **Human-assist and escalation triggers** — Specify the conditions that force human takeover: 3 classification failures in a row, any mention of "manager", "allergy" + severity word ("anaphylaxis", "severe", "nut"), "refund", "complaint", "missing", "wrong", language switch, caller-in-distress signals, system outage, or unified-layer ticket-stuck > 90 seconds. Define the bridge phrase the AI uses when handing off ("One moment, let me get someone on the line for you"), and the staff-side alert mechanism (KDS banner, headset beep, mobile push).

9. **Training and crew-assist plan** — Produce the short-form training for window and kitchen crew: what the AI does, what it doesn't, the 6 assist moments a human must cover (allergy confirmation, payment exception, upsell declined 3x, loud background, unfamiliar accent dropout, guest asks for manager), and the "be the friendly face" playbook at the window since the voice interaction is already done by the time the car arrives.

10. **Measurement plan and go / no-go gate** — Write the 4-week KPI dashboard: SoS at menu board and at window, AI capture rate (target 85%+ at week 4 for simple menus, 70%+ for complex menus), order accuracy (target 95%+), upsell attach rate (baseline lift of 3 to 5 points), friendliness score if available, cars-per-hour, and labor-hours per 100 cars. Specify the week-4 go / hold / roll-back gate thresholds and the rollback procedure (turn off AI, preserve recorded conversations for analysis, notify franchisee, log with brand ops for vendor review).

11. **Compliance and disclosure** — Draft the exact recorded-call disclosure ("Your order may be taken by our AI assistant and recorded for quality"), confirm the system logs no card data (PCI-safe hand-off if payment is taken at the window instead of at the order post), state-by-state biometric-data exclusions if cameras or voice ID are used, and the labor-posture statement for franchisees to use in internal and public communication.

12. **Communication and launch pack** — Produce the launch-day comms pack: a one-page guest sign for the lane, a social-media launch post (paired with the brand's Social Media Post Generator voice), a 5-line crew briefing script, a 1-page franchisee FAQ, and a 1-paragraph press-ready response in case a local outlet picks up the story. Do not promise job elimination; frame the AI as freeing crew to serve guests at the window.

**Output requirements:**

- Structured playbook document with numbered sections matching the process above
- All scripted lines (greetings, upsells, disclosures, OCS copy, crew assist moments, FBC objection answers) in quote blocks so they can be pasted directly into the vendor configuration or the franchisee brief
- A one-page VP Ops summary at the top: wave name, stores in scope, week-1 and week-4 KPI targets, go / hold / roll-back gate definition, and the 3 biggest risks
- Correct industry terminology throughout (SoS, OCS, attach rate, capture rate, tandem lane, pull-forward, 86, handoff, LTO, FBC)
- Ready to paste into a brand franchisee portal, a Presto / ConverseNow / Hi Auto configuration, or a Toast Drive-Thru rollout plan with minimal editing
- Saved to `outputs/` if the user confirms

## Related Skills

- `customer-service/ai-phone-agent-playbook.md` — Full-service phone / host / reservation voice agent; use instead of this skill for sit-down restaurants
- `sales/digital-menu-optimization-brief.md` — Third-party delivery menu optimization; upstream of menu-complexity bounding in step 1
- `admin/dynamic-menu-pricing-advisor.md` — Contribution-margin leaderboard that feeds step 4 upsell scripting
- `operations/demand-forecast-briefing.md` — Daypart volume used to time the cutover in step 2
- `operations/shift-prep-checklist.md` — Window-crew assist moments in step 9 connect to day-of prep

## Example Output

Below is an abbreviated example. A full wave playbook runs five to eight pages and includes every numbered section above.

# Drive-Thru AI Rollout Playbook — Wave 2 (First Franchise Cohort)

**Brand:** Regional chicken QSR, 1 lane/store. **Wave:** "SE-Franchise-A" — 18 franchise lanes, GA/AL/TN cluster, go-live 2026-07-13 (after the World Cup window to avoid learning-tax during peak). **Platform:** ConverseNow (POS-native on PAR Brink, OCS installed). **Baseline:** SoS 214s, accuracy 91%, ~165 cars/day/lane.

## VP Ops Summary (one page)

18 franchise lanes go live the week of 7/13 after passing the eligibility gate (SoS baseline filed, signage refreshed, manager certified, liability ack signed). Week-1 SoS target ≤ 219s (baseline +5, the learning tax); week-4 target ≤ 205s. Capture ≥ 70% (complex chicken menu), accuracy ≥ 95%, upsell attach +4 pts. Go/hold/rollback gate at end of week 4. **Top 3 risks:** modifier blowup on build-your-own tenders, franchisee "will this replace my crew" pushback, single-supplier OCS hardware lead time.

## 1. Menu-Complexity Bounding (excerpt)

Flatten build-your-own tenders (count + 6 sauces + 3 sides = ~400 combos) to canonical IDs `tenders_{3,5,8}` + `sauce_*` + `side_*`. Agent-safe modifiers: sauce, side swap, drink size, combo upsize. **Deny-list (ask-for-human):** catering trays, gift cards, allergy-substitution, "make it like last time." Synonym map: "tender meal" → `combo_tenders_3`; "big sweet tea" → `drink_tea_lg`. Pricing-parity check: voice total must equal kiosk total to the cent.

## 2. Lane & SoS Targets

Single lane, AI owns the order post, human owns the window handoff. SoS targets: menu board ≤ 35s · order post ≤ 95s · total ≤ 205s by week 4. OCS displays the order before pull-forward — the primary accuracy-lift mechanism.

## 4. Impulse Upsell (daypart, margin-anchored)

> Lunch: "Want to make that a combo with a sweet tea and fries?"
> Hot day / afternoon: "A half-gallon sweet tea for the road?"
> Dinner: "Add a family side — mac & cheese feeds the table."
One offer per car, never repeated. Retire any prompt under target attach after 14 days.

## 5. OCS Copy

> Listening: "Got it — anything else?"  Finished: "Please check your screen, then pull forward."  Error: "Press the button for a team member."

## 8. Human-Assist Triggers

3 classification failures · "manager" · "allergy" + severity · "refund"/"complaint"/"missing"/"wrong" · language switch · ticket stuck > 90s.
> Bridge: "One moment — let me get a team member on for you."

## 7. Franchisee FAQ (FBC script, excerpt)

> "Will this replace my employees?" — "No. It takes the order so your crew can focus on speed and a friendly window. No positions are eliminated by this rollout."
> "Who pays if the AI gets an order wrong?" — "Same as today: we remake it. The OCS lets the guest catch errors before the order fires, so accuracy goes up, not down."
> "How do I turn it off during a rush?" — "One tap on the manager tablet drops to human-only; it re-enables automatically next shift or when you toggle back."

## 10. Week-4 Go / Hold / Rollback Gate

GO if SoS ≤ 205s **and** accuracy ≥ 95% **and** capture ≥ 70%. HOLD (extend 2 weeks) if one metric misses by < 5%. ROLLBACK if accuracy < 90% or capture < 55%: disable AI, preserve recordings for vendor review, notify franchisee, log with brand ops.

## 11. Disclosure & Compliance

> "Your order may be taken by our AI assistant and recorded for quality."
No card data captured at the post — payment at the window only. Biometric-rule check: no cameras/voice-ID in this wave, so no IL/TX BIPA-class exposure; re-review if Window Intelligence is added.
