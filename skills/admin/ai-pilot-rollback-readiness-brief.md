---
name: "AI Pilot Rollback Readiness Brief"
category: admin
tools: [claude, chatgpt]
difficulty: advanced
time_saved: "~5-8 hr/pilot decision"
version: 1.0
last_eval_score: null
---

# AI Pilot Rollback Readiness Brief

## Purpose

Produce a CTO / COO / VP-Operations decision brief that prevents a multi-unit restaurant operator from shipping an AI pilot into the next failure-mode cycle. The brief tells the operator (a) whether the pilot is worth running at all given the vendor's published accuracy gap, (b) what success criteria and rollback triggers the operator must commit to before week one, (c) how to allocate accountability between corporate and franchisees on a mandatory-tech rollout, (d) how to validate the worker-workflow impact before claiming an efficiency gain, and (e) how to govern the third-party dependency layer (third-party delivery, payment processor, off-premise aggregator) when the AI changes how that layer behaves.

This skill is the **failure-mode counterpart** to the **Multi-Unit Restaurant Finance AI / xFP&A Selection Brief** (which selects the vendor) and the **Drive-Thru AI Rollout Playbook** (which gates each rollout wave). It is materially distinct from both. Vendor selection asks "which platform fits our stack." Wave rollout asks "is this lane ready." This brief asks "what happens when the pilot is wrong, who pays the bill, and how do we get out without a $100M lawsuit or a 11,000-store retreat in the trade press."

## When to Use

Run this skill when a multi-unit operator is at the decision gate for any of the following:

1. **A vendor-claim vs. measured-accuracy gap** is plausible — the vendor's marketing claims an accuracy number (95% / 99% / "near-perfect") that the operator's pilot data cannot yet replicate in the operator's own environment with the operator's own SKUs / lanes / dayparts / workers.
2. **The pilot will be mandatory for franchisees** — corporate is contemplating a system-wide rollout that franchisees will be required to adopt, with no opt-out, and the operator does not yet have a published rollback path.
3. **The AI changes the worker workflow** — the AI replaces, accelerates, or restructures a task workers already do; the operator has not yet validated that the new workflow is faster than the old one *including* the verification step workers will perform on every output until they trust it.
4. **The AI introduces a third-party feedback loop** — the AI changes how third-party delivery dispatchers, payment processors, KDS-connected aggregators, or off-premise marketplaces see the operator's orders, lanes, or SKUs (e.g., a delivery-routing AI that decides which orders the third-party delivery driver pool will see and accept first).
5. **An existing AI deployment is showing distress signals** — operator data is trending against the vendor's claim, manager NPS on the tool is decaying, franchisees are filing tickets, or a competitor has just publicly retired the same vendor.

Run this brief before signing a system-wide vendor contract, before mandating franchisee adoption, before sunsetting a competing legacy workflow, before issuing a corporate press release on the AI deployment, and after the first wave of operator data has come back with a clear vendor-claim gap.

Pairs with **Multi-Unit Restaurant Finance AI / xFP&A Selection Brief** (vendor selection precedes pilot governance), **Drive-Thru AI Rollout Playbook** (lane-level go / no-go gates feed the rollback decision), **Store Execution Audit Playbook** (in-store photo and checklist data is the operator's own ground truth against the vendor's claim), and **Staff Schedule Optimizer** (labor-forecast AI is a frequent rollback candidate; this brief governs the decision to keep or kill).

## Required Input

Provide the following:

1. **Pilot profile** — Vendor name, AI capability category (computer-vision inventory, voice-AI drive-thru, AI delivery routing, AI labor forecasting, AI menu personalization, AI photo audit, AI inventory replenishment, AI guest chatbot), unit count in the pilot scope, contract status (signed / under negotiation / RFP), and the named corporate executive sponsoring the pilot
2. **Vendor accuracy claim** — The specific accuracy / efficiency / ROI number the vendor publishes in marketing or contract language (e.g., "99% inventory accuracy," "8x faster than manual counts," "15% labor-forecast error reduction," "30-minute delivery times"), the data source the vendor cites (lab benchmark, single named operator, internal study, no source disclosed), and the comparable measurement the operator is currently making on the same workflow
3. **Operator's current workflow baseline** — How the task is performed today, how often (per shift, per day, per week), who performs it, how long it takes, and the operator's current error rate / cost / variance on the same task. If the operator has no internal baseline, flag this as a pilot-blocking gap.
4. **Worker workflow impact** — Who in the store touches the AI tool (barista, line cook, prep, server, manager, dispatcher), how often per shift, what the workflow looked like before, what it looks like with the AI, and whether the worker is expected to verify every output or only flagged ones
5. **Franchise vs. corporate posture** — Is the rollout mandatory for franchisees, optional, opt-in with corporate funding, or contingent on franchisee data-share consent? Does the franchise agreement allow corporate to mandate this technology? Has the franchisee advisory council reviewed?
6. **Third-party dependency map** — Which third parties does the AI talk to (third-party delivery aggregators, payment processors, POS partners, KDS partners, off-premise marketplaces, loyalty providers, kiosk operators), and how does the AI's behavior change the operator's standing with those third parties (order acceptance rates, dispatch priority, batch sizes, tipping incentives, fee structures)?
7. **Existing in-market failure-case references** — Which named restaurant operators have publicly retired, sunset, sued over, or rolled back a comparable AI deployment in the past 12 months? (See knowledge-base reference: Starbucks NomadGo Automated Counting retirement May 2026; Chaac Pizza Northeast / Pizza Hut Dragontail $100M lawsuit May 2026; Sinch May 2026 study showing 74% of enterprises rolled back a live AI customer-communications agent.) If a comparable failure has shipped, the operator inherits a pre-existing trade-press narrative that will frame any rollback decision.
8. **Pilot budget and timeline** — Total pilot budget, planned pilot duration, planned full-rollout duration, the budget at risk if the pilot terminates early, and the named C-suite executive who is on the hook for the ROI claim

## Instructions

You are a restaurant operations / technology risk advisor with experience designing AI pilots that have a published exit ramp. Your job is to produce a brief the CTO / COO / VP-Operations can present to the CEO and the board *before* the pilot ships — a brief that tells the operator what success looks like, what failure looks like, and exactly when to pull the cord.

**Before you start:**
- Load `config.yml` from the repo root for unit count, concept, AUV, franchise mix
- Reference `knowledge-base/terminology/` for failure-mode and pilot-governance terms (vendor accuracy claim, measured accuracy, governance gap, double-work anti-pattern, mandatory-tech franchise tension, third-party dependency loop, rollback trigger, sunset clause, exit ramp, parallel-run, ground-truth audit, opt-out provision)
- Reference `knowledge-base/case-studies/ai-pilot-failures.md` (or stand up the named-operator failure map inline if the file is missing): Starbucks NomadGo Automated Counting (11,000-store deployment, September 2025 → retired May 19, 2026; computer-vision inventory miscounted similar SKUs, missed scans, accuracy drift over time; baristas required to verify every output → double-work; trade-press cycle from Reuters Feb 2026 through Fortune May 28 2026 framed the retirement as a turnaround stumble for the CEO). Pizza Hut Dragontail AI Store Control System (~111-location franchisee Chaac Pizza Northeast lawsuit May 2026; mandatory-tech franchisee rollout; delivery times rose from sub-30 to 45+ minutes for half of orders; franchisee sales growth dropped from +10% YoY to -9.78%; lawsuit seeks $100M+ damages, court & attorney fees; root cause cited: Dragontail handed third-party delivery dispatchers selective order metadata including tip amount, payment type, and other-orders-at-the-same-store, which incentivized drivers to wait on bigger-tip orders and skip low-tip / no-cash orders; downstream effect: ready orders sat 15 minutes while drivers waited on oven-tier orders). Sinch 2026-05 production-paradox study (74% of enterprises rolled back a live customer-communications AI agent because the governance layer was retrofit after deployment rather than built day one).

**Process:**

1. **Vendor-claim diligence** — For the pilot's vendor accuracy / efficiency claim, write a single page that answers: (a) What is the claim? (b) What is the data source — lab benchmark, single named operator, vendor-internal study, no source? (c) Is the source reproducible in the operator's environment? (d) What is the operator's current measured baseline on the same metric? (e) What is the implied gap between the vendor claim and the operator's likely outcome? Score the claim High Confidence / Medium Confidence / Low Confidence. Flag any vendor claim that cites no named operator at the operator's scale tier as Low Confidence by default.

2. **Pilot success criteria** — Define explicit pass / fail criteria for the pilot, separated into three tiers:
   - **Operator-side ground-truth metric** — The single most-important operator-measured number that decides go / no-go. For computer-vision inventory: scan accuracy verified against a manual recount on N units, N≥10% of pilot stores, weekly. For voice-AI drive-thru: order accuracy verified against a kitchen-display ticket audit on N orders, N≥50/lane/day. For AI delivery routing: end-to-end delivery time from order-fired to delivered, vs. the prior-system baseline, on a control group of stores. For AI labor forecasting: labor-forecast error vs. the operator's prior-system MAPE, on a multi-week sample.
   - **Worker-experience gate** — A signed manager survey at 30 / 60 / 90 days asking: is the tool faster than the old workflow including verification? Manager NPS ≥ 40 = pass; 20–39 = caution; < 20 = fail. Worker-experience failure has retired more pilots than vendor-claim failure (e.g., Starbucks 9-month sunset turned on barista feedback as much as on accuracy data).
   - **Third-party-effect gate** — If the AI talks to a third party (third-party delivery, payment, kiosk operator), the operator must measure the third-party-side effect *separately* from the operator-side metric. For AI delivery routing: third-party driver order acceptance rate, batch sizes, tip distribution. Failure to measure the third-party effect is how the Pizza Hut Dragontail case happened.

3. **Rollback triggers (the exit ramp)** — Before the pilot ships, the operator must commit in writing to the specific data conditions that trigger an immediate pause and the specific data conditions that trigger an immediate sunset. Document four rollback triggers per pilot:
   - **Hard rollback** — Specific data threshold below which the pilot is sunset within 30 days. Example: measured inventory accuracy below 90% for three consecutive weekly recounts; measured delivery time above the prior-system baseline by more than 10% for two consecutive weeks; labor-forecast MAPE worse than the prior-system MAPE for four consecutive weeks.
   - **Soft pause** — Specific data threshold that pauses the pilot for vendor engineering review for 30–60 days. Example: manager NPS below 30; franchisee adoption rate below 50% in the opt-in tier; third-party-delivery acceptance rate down more than 5 points.
   - **Worker-experience pause** — Three consecutive manager surveys (any cadence) below the NPS-30 gate, regardless of operator-side metric performance. The Starbucks NomadGo precedent shows worker-experience failure is sufficient to retire a deployment even when vendor-side accuracy looks OK.
   - **Trade-press contagion pause** — If a comparable scale-tier operator publicly retires the same vendor or a same-category competitor's system, the operator pauses the pilot for 14 days for a board-level review.

4. **Worker workflow validation** — Before the pilot ships, validate that the new workflow is faster than the old workflow *including the verification step the worker will perform on every output until trust is built*. This is the **double-work anti-pattern audit**: if the AI's output must be verified by a human in every case, the AI has not eliminated the task — it has added a layer. A double-work workflow can still be worth shipping (the AI may be useful as a guide or a check), but it cannot be marketed internally as an "efficiency tool." Document the workflow comparison in three columns: pre-AI task steps, with-AI task steps including verification, time-to-complete for each. Require a manager-tier sign-off on the workflow comparison before pilot go-live.

5. **Mandatory-tech franchise tension audit** — If the rollout is mandatory for franchisees, write a section addressing: (a) Does the franchise agreement give corporate this authority? (b) Has the franchisee advisory council reviewed and what was the vote? (c) What is the franchisee opt-out provision and what penalties apply for non-compliance? (d) What is the franchisor's response posture if franchisee performance metrics decline post-rollout (does the franchisor accept liability or does the franchise agreement push it back to the franchisee)? (e) What is the litigation-risk posture and the named-counsel review status? The Chaac Pizza Northeast / Pizza Hut Dragontail $100M lawsuit is the on-the-table precedent — a mandatory-tech rollout that allegedly damaged franchisee sales and produced a published-damages claim that other franchisee networks will study.

6. **Third-party dependency loop governance** — If the AI changes how a third party sees the operator's orders, lanes, or SKUs, write a section addressing: (a) What data does the AI share with the third party? (b) How does that data shape the third party's behavior (driver acceptance, batch construction, dispatch priority, fee structure)? (c) Are there second-order incentives the AI creates that the operator did not intend (e.g., low-tip orders being skipped in favor of high-tip orders, leading to a service collapse on lower-priced concepts)? (d) What is the contract language with the third party that governs the AI's data sharing, and what is the operator's exit if the third party changes its dispatch logic in response? (e) Is the operator publishing the third-party-effect metric in the rollback-trigger dashboard?

7. **Governance infrastructure checklist** — The Sinch May 2026 production-paradox study found that 74% of enterprises rolled back a live customer-communications AI agent because the governance layer was retrofit after deployment rather than built day one. Before go-live, the operator must have in place: (a) Staging environment for model and policy changes before they hit production; (b) Documented rollback runbook (who to call, what to disable, what to communicate to stores); (c) Audit-trail logging for every AI decision the worker would have made manually; (d) Named owner per region / franchise tier for AI escalations; (e) A monthly executive review cadence with the four rollback-trigger dashboards on the agenda; (f) A pre-drafted internal communications pack for the "we are sunsetting this" announcement (the Starbucks NomadGo internal newsletter was a half-day prep, but the trade-press cycle that followed was 9 days of negative coverage — the operator needs the comms pack ready before the pilot ships, not after the sunset decision).

8. **Pilot scope and parallel-run plan** — Define the pilot scope: which stores, which dayparts, which SKUs / orders / shifts. Define the parallel-run period: how many weeks the AI and the legacy workflow run side-by-side with both data sets collected. The Starbucks NomadGo precedent suggests a minimum 8–12 weeks of parallel-run before sunsetting the legacy workflow, with a documented data-audit at week 4 and week 8 against the rollback triggers. Document the parallel-run team — who counts manually for the ground-truth audit, who reviews the AI outputs, who owns the discrepancy log.

9. **Decision recommendation** — Produce a single recommendation: (a) Ship the pilot as scoped with the rollback triggers committed; (b) Ship a smaller-scope pilot with tighter rollback triggers; (c) Run a 30-day parallel-run vendor-claim diligence before signing the contract; (d) Decline the pilot. Include the named executive accountable for the rollback decision and the date of the first executive review of the rollback-trigger dashboards.

**Output requirements:**
- One-page executive summary: pilot scope, vendor-claim confidence score, success criteria, rollback triggers, recommendation, named accountable executive
- Vendor-claim diligence one-pager
- Success criteria table (operator-side metric + worker-experience gate + third-party-effect gate)
- Rollback trigger table (hard rollback, soft pause, worker-experience pause, trade-press contagion pause)
- Worker workflow comparison table (pre-AI vs. with-AI including verification)
- Mandatory-tech franchise tension audit (if applicable)
- Third-party dependency loop governance (if applicable)
- Governance infrastructure checklist (six items)
- Pilot scope + parallel-run plan with named team
- Pre-drafted "we are sunsetting this" internal communications pack
- Saved to `outputs/` if the user confirms

## Example Output

### Example 1 — Regional coffee operator (340 units, $1.1B revenue, evaluating a computer-vision inventory pilot against a vendor claiming 99% accuracy)

```markdown
# AI Pilot Rollback Readiness Brief
## RoasteryNorth Group (340 units, 9 states, $1.1B revenue) — Computer-Vision Inventory Pilot
## Sponsor: CTO P. Okafor | Prepared 2026-05-29 | Pilot go / no-go 2026-06-22

## Executive Summary
- **Recommendation:** Run a 30-day vendor-claim diligence cycle in 4 pilot stores BEFORE signing the system-wide contract. Defer the 60-store wave-one rollout pending diligence results. Do not commit to a system-wide rollout in 2026 even with a successful diligence cycle — full-system commitment requires a 90-day pilot at the rollback triggers documented below
- **Vendor accuracy claim confidence:** LOW. Vendor cites a single 60-store pilot at a different concept (coffee + bakery + grab-and-go retail mix vs. RoasteryNorth's coffee-led menu), no published recount methodology, no third-party audit
- **Pre-existing in-market failure case:** Starbucks NomadGo Automated Counting retired May 19 2026 across 11,000 North American stores after 9 months. Comparable scale tier, identical capability category, root-cause cluster (similar-SKU confusion across milk variants, scan misses, accuracy drift over time, double-work for baristas, falling manager NPS). RoasteryNorth's pilot must demonstrate measurable improvement over the failure-mode pattern before any commitment beyond the diligence cycle
- **Hard rollback trigger:** Measured scan accuracy below 90% on a weekly manual recount of 10% of pilot SKUs for three consecutive weeks → sunset the pilot, decommission the hardware, retain the historical scan data for the case-study record
- **Worker-experience pause:** Barista NPS on the tool below 30 at the 30-day mark → pause for vendor engineering review, do not expand
- **Third-party-effect gate:** N/A for this capability category
- **Accountable executive for rollback decision:** CTO P. Okafor; weekly review with COO M. Bauer; monthly board review

## Vendor-Claim Diligence
| Dimension | Vendor Claim | Operator Reality | Confidence |
|---|---|---|---|
| Scan accuracy | 99% | Pilot store baseline (manual counts): 96.4% over the past 12 weekly cycles | LOW |
| Scan time | 8x faster than manual | Manual count time RoasteryNorth average: 22 min/store; vendor claim implies sub-3-min | LOW |
| Verification overhead | Implied minimal | Barista will need to verify any similar-SKU output until trust is built — at least the first 90 days; this is double-work | LOW |
| Named-operator reference | One 60-store pilot, different concept | Not at RoasteryNorth scale or concept; not third-party-audited | LOW |
| Pre-existing in-market failure | Vendor does not disclose | Starbucks NomadGo retirement May 19 2026 at the same capability category and scale tier; trade-press cycle is fresh | HIGH (against vendor) |

## Success Criteria
| Tier | Metric | Pass | Caution | Fail |
|---|---|---|---|---|
| Operator-side ground truth | Scan accuracy on weekly manual recount, 10% of SKUs | ≥ 95% for 3 consecutive weeks | 90–94% | < 90% for 3 consecutive weeks |
| Worker experience | Barista NPS on the tool at 30 / 60 / 90 days | ≥ 40 | 20–39 | < 20 |
| Workflow time | Total scan + verification time per store per shift, vs. manual baseline | ≤ 18 min (better than manual) | 19–22 min (parity) | > 22 min (worse than manual) |
| Trade-press contagion | New named-operator retirement in the same capability category | None | One announcement | Two or more within 30 days |

## Rollback Trigger Table
| Trigger Class | Condition | Action | Timeline |
|---|---|---|---|
| Hard rollback | Scan accuracy < 90% for 3 consecutive weeks | Sunset, decommission, archive data | 30 days |
| Soft pause | Manager NPS 20–39 OR vendor accuracy claim revised | 60-day vendor engineering review, no expansion | 60 days |
| Worker-experience pause | Barista NPS < 30 at any review | Pause expansion, vendor on-site engagement | Indefinite until NPS recovers |
| Trade-press contagion pause | New comparable-operator retirement | 14-day board review, all-stop on expansion | 14 days |

## Worker Workflow Comparison
| Step | Pre-AI (manual) | With-AI (including verification) |
|---|---|---|
| Scan / count | 22 min manual count | 3 min device scan |
| Similar-SKU verification (oat / whole / 2% / nonfat milk) | None | 6 min barista verification |
| Mis-scan reconciliation (camera missed an item) | None | 4 min barista correction |
| Reorder validation | 4 min manager review of reorder list | 4 min manager review of reorder list (unchanged) |
| **Total per store per shift** | **26 min** | **17 min — IF verification stays at 6 min as trust builds** |
| Risk: verification stays at 10+ min (low-trust state) | — | **17 min becomes 21 min — parity with manual** |

## Governance Infrastructure Checklist
- [ ] Staging environment for any vendor model update before deployment to pilot stores
- [ ] Documented rollback runbook (CTO, COO, comms, store ops, IT decommission, hardware return)
- [ ] Audit-trail logging: every scan output, every verification correction, every reorder triggered
- [ ] Named owner per region for AI escalations: NW (Director K. Park), SW (Director D. Chen), Central (Director A. Reyes)
- [ ] Monthly CTO + COO + CFO review cadence with the four rollback-trigger dashboards
- [ ] Pre-drafted "we are sunsetting this" internal newsletter — drafted 2026-06-15, two paragraphs, blame-free, parallel-count workflow restoration steps

## Pilot Scope + Parallel-Run Plan
- 4 pilot stores: NW-128, SW-091, Central-205, NW-019 (mix of high / low scan complexity, urban / suburban)
- 30 days diligence cycle: weekly manual recount of 10% of SKUs per store; barista survey at day 14 and day 30
- 60 additional days conditional on diligence pass: 12 stores expansion, weekly recount, manager NPS at day 60 and day 90
- Parallel-run owner: Inventory Operations Manager S. Liang
- Manual recount audit team: 2 RoasteryNorth corporate inventory analysts per store per week
- Discrepancy log review: weekly with CTO + vendor engineering

## Pre-Drafted Sunset Communications Pack
Draft attached separately. Two-paragraph internal newsletter for managers. One-paragraph external statement for trade-press if asked. One-paragraph franchisee-facing memo with parallel-count workflow restoration steps.
```

### Example 2 — Multi-state pizza franchisee (110 units, $180M revenue, reviewing whether to comply with a corporate mandate to adopt a third-party-delivery routing AI)

```markdown
# AI Pilot Rollback Readiness Brief
## SliceCo Northeast LLC (110 units, 5 states, $180M revenue) — Corporate-Mandated AI Delivery Routing System
## Sponsor: COO L. Marchetti | Prepared 2026-05-30 | Compliance deadline 2026-09-01

## Executive Summary
- **Recommendation:** Decline the corporate-mandated rollout in its current form. Request a 90-day SliceCo-led pilot in 12 stores with the rollback triggers documented below, the parallel-run measurement plan, and the third-party-delivery-effect gate measured separately from corporate-side metrics. If corporate refuses the pilot framework, escalate to the franchisee advisory council and named-counsel review under the franchise agreement
- **Vendor accuracy claim confidence:** LOW. Corporate cites a 20-store internal test; no franchisee-operated stores in the test; no published third-party-delivery-effect data
- **Pre-existing in-market failure case:** Chaac Pizza Northeast vs. Pizza Hut $100M Dragontail lawsuit filed May 2026 alleges delivery times rose from sub-30 to 45+ minutes for half of orders post-rollout, sales growth dropped from +10% YoY to -9.78%, and root cause was Dragontail's data-sharing with DoorDash dispatchers (tip amount, payment type, other-orders-at-the-same-store) that incentivized drivers to wait on high-tip orders and skip low-tip / no-cash orders. This is the EXACT failure-mode pattern SliceCo must measure against
- **Mandatory-tech franchise tension:** Franchise agreement Section 8.2 allows corporate-mandated tech IF "reasonable opportunity to test" and "no material adverse effect on franchisee operations" — both clauses give SliceCo standing to require a measured pilot. Named-counsel review COMPLETE 2026-05-28: SliceCo has cause to require pilot framework
- **Third-party-effect gate:** End-to-end delivery time AND third-party-driver acceptance rate AND tip distribution by order tier, measured for 90 days against a control group of 12 SliceCo stores not yet on the AI
- **Accountable executive for rollback decision:** COO L. Marchetti; biweekly review with franchisee advisory council

## Vendor-Claim Diligence
| Dimension | Corporate Claim | SliceCo Reality | Confidence |
|---|---|---|---|
| Delivery time reduction | "15% faster delivery times" | SliceCo current avg 28 min order-to-door; "15% faster" implies sub-24 min; the Chaac precedent saw delivery times INCREASE 50% under the same system | LOW |
| Driver acceptance rate | Not disclosed | Corporate has not measured the third-party-driver-side effect | LOW |
| Tip distribution shift | Not disclosed | Corporate has not measured tip-tier effects on driver acceptance | LOW |
| Pre-existing in-market failure | Corporate does not disclose | Chaac vs. Pizza Hut $100M lawsuit May 2026, alleging EXACT capability category | HIGH (against corporate) |

## Success Criteria
| Tier | Metric | Pass | Caution | Fail |
|---|---|---|---|---|
| Operator-side: delivery time | Order-to-door average vs. baseline | Equal to or better than baseline | 5–10% worse | > 10% worse for 2 consecutive weeks |
| Operator-side: sales growth | Same-store sales YoY in pilot vs. control | Equal to or better than control | 2–4% gap | > 4% gap for 4 consecutive weeks |
| Worker experience | Store manager NPS at 30 / 60 / 90 days | ≥ 40 | 20–39 | < 20 |
| Third-party-effect gate | Driver acceptance rate, tip distribution by order tier | Equal to or better than baseline | 5-point drop | 5-point drop sustained 2+ weeks |
| Trade-press contagion | New comparable franchisee lawsuit | None | One announcement | Two or more within 60 days |

## Rollback Trigger Table
| Trigger Class | Condition | Action | Timeline |
|---|---|---|---|
| Hard rollback | Delivery time > 10% worse for 2 consecutive weeks OR same-store sales gap > 4% for 4 consecutive weeks | Sunset in SliceCo, escalate corporate counsel | Immediate |
| Soft pause | Manager NPS 20–39 OR driver-acceptance 5-point drop | 30-day measured review, no expansion | 30 days |
| Worker-experience pause | Manager NPS < 30 | Pause expansion | Indefinite |
| Trade-press contagion pause | New franchisee lawsuit against same vendor | 14-day council review | 14 days |

## Mandatory-Tech Franchise Tension Audit
- Franchise agreement Section 8.2: corporate may mandate "reasonable" tech with "reasonable opportunity to test"; SliceCo has standing to require pilot
- Franchisee advisory council vote: 14 of 22 franchisees support requesting pilot framework; 5 prefer outright decline; 3 already compliance-committed
- Named-counsel review status: COMPLETE 2026-05-28, opinion attached
- Litigation-risk posture: SliceCo will not accept liability for franchisee-attributable sales declines that the rollout produces; will require corporate make-whole provisions in the rollout agreement
- Opt-out provision: SliceCo requests opt-out with no penalty for the first 12 months of any rollout

## Third-Party Dependency Loop Governance
- Data shared with DoorDash / Uber / Grubhub dispatchers under the system: order ID, store ID, ready-time estimate, tip amount, payment type
- Operator concern: tip amount + payment type sharing creates the same incentive distortion alleged in the Chaac case
- Contract language with each third party: review attached separately
- Operator request: corporate must disable tip-amount and payment-type sharing with third-party dispatchers as a condition of SliceCo compliance, OR provide measured 90-day evidence that disclosure does not produce driver-side selectivity at SliceCo's order-mix profile

## Governance Infrastructure Checklist
- [ ] Staging environment for any corporate model update before deployment to SliceCo stores
- [ ] Documented rollback runbook (COO, IT, store ops, franchisee-counsel, comms)
- [ ] Audit-trail logging: every order, every dispatcher decision, every driver acceptance, every tip-distribution outcome
- [ ] Named owner per region for AI escalations: NY (Director T. Hassan), NJ/PA (Director R. Vargas), MD/DC (Director J. Singh)
- [ ] Biweekly franchisee advisory council review with the rollback-trigger dashboards
- [ ] Pre-drafted franchisee-facing internal communications pack — drafted 2026-08-15 in time for the 2026-09-01 deadline

## Pilot Scope + Parallel-Run Plan
- 12 SliceCo pilot stores: matched-pair against 12 SliceCo control stores by AUV, urban / suburban, delivery / carry-out mix
- 90-day pilot window with weekly delivery-time + driver-acceptance + tip-distribution measurement
- Parallel-run owner: SliceCo Director of Off-Premise Operations N. Bianchi
- Control-group integrity owner: SliceCo BI Director K. Antonelli
- Discrepancy log review: biweekly with COO + franchisee advisory council subcommittee
```

## Notes
- The brief is the operator's pre-pilot commitment document, not the vendor's pitch deck. The operator owns the rollback triggers; the vendor does not.
- Worker-experience failure has retired more pilots than vendor-claim failure. A passing accuracy number with a failing manager NPS is still a sunset.
- The pre-drafted sunset communications pack is the most under-built item in restaurant-vertical AI rollouts. The Starbucks NomadGo trade-press cycle ran nine days; the operator that drafts the comms pack before the pilot ships controls the narrative when the sunset comes.
- For computer-vision inventory pilots in 2026 specifically, the Starbucks NomadGo precedent is the in-category failure-mode anchor. For mandatory-tech franchise AI rollouts in 2026 specifically, the Chaac / Pizza Hut Dragontail lawsuit is the in-category franchisee-defense anchor. Both will be cited in vendor RFP responses through at least the end of 2027.
- This skill ships v1.0 in 2026-06-01 ahead of the FIFA World Cup 2026 surge window (June 11 – July 19, 2026). World Cup is the wrong window to ship an untested AI pilot into mandatory-tech rollout. If an operator is sponsoring a new AI pilot in the May-June 2026 window, this brief should run before any pilot ships across host-city stores.

## Related Skills
- `admin/multi-unit-finance-ai-selection-brief.md` — selects the vendor before this brief governs the pilot
- `customer-service/drive-thru-ai-rollout-playbook.md` — lane-level wave gates feed the rollback decision
- `operations/store-execution-audit-playbook.md` — ground-truth photo audit data tests the vendor accuracy claim
- `operations/world-cup-2026-surge-playbook.md` — World Cup is the wrong window for an unproven AI pilot
- `admin/staff-schedule-optimizer.md` — labor-forecast AI is a frequent rollback candidate
