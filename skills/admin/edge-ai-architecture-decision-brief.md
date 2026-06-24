---
name: "Edge-AI Architecture Decision Brief"
category: admin
tools: [claude, chatgpt]
difficulty: advanced
time_saved: "~8 hr/architecture evaluation"
version: 1.0
last_eval_score: 9.30
---

# 🧠 Edge-AI Architecture Decision Brief

## Purpose

Produce a CTO / CIO / VP-Technology decision brief that tells a multi-unit restaurant operator **where the AI should run** — at the store edge (on-premise inference hardware in each location), in the cloud, or in a hybrid split — and **how tightly to couple** the brand's drive-thru voice, computer vision, and manager-facing "store brain" capabilities into one platform versus a set of point solutions. The brief converts a vendor's "intelligent edge platform" pitch into an operator-side architecture decision with named tradeoffs: latency and connectivity-resilience requirements, build-vs-buy, the unified-platform-vs-best-of-breed integration stance, hardware capex and refresh cadence, vendor and silicon lock-in, data-residency and on-device-inference privacy posture, and a staged rollout plan with rollback gates.

This skill is materially distinct from the **Drive-Thru AI Rollout Playbook** (which deploys one voice surface in the lane), the **AI Phone Agent Playbook** (front-of-house voice), the **Automated Kiosk Deployment Brief** (one customer-facing ordering device), and the **Multi-Unit Finance AI / xFP&A Selection Brief** (the finance decision layer). Those skills choose and ship individual AI *capabilities*. This brief decides the **infrastructure layer underneath all of them** — the compute topology and platform-coupling stance that determines whether those capabilities run fast, stay up when the internet drops, and can be governed as one estate across hundreds or thousands of stores.

## When to Use

Run this brief when an operator is at one of these inflection points:

- A platform vendor has pitched an "edge AI," "intelligent commerce," "store intelligence," or "in-store brain" platform that bundles voice ordering, computer vision, equipment monitoring, and manager analytics, and the operator must decide whether to standardize on it.
- A cloud or silicon partner is offering to install on-premise inference hardware (edge appliances, GPU/NPU blades, vision cameras) across the fleet ahead of a wider AI rollout, and the operator must underwrite the capex, the refresh cycle, and the lock-in.
- The operator is running two or more AI point solutions (a voice-AI vendor, a separate vision-analytics vendor, a separate labor/forecast tool) and is deciding whether to consolidate onto one edge platform or keep best-of-breed.
- Drive-thru or kitchen latency, or AI uptime during ISP/cloud outages, has become an operational complaint and the operator needs an architecture answer, not another point tool.
- A flagship competitor has announced an at-the-edge "master brain" deployment and leadership wants a position paper on whether to match the architecture, on what timeline, and at what cost.

Pairs with: **AI Pilot Rollback Readiness Brief** (the governance gate every pilot in this brief must pass before scaling), **Multi-Unit Finance AI / xFP&A Selection Brief** (capex/opex modeling for the hardware estate), **Drive-Thru AI Rollout Playbook** and **AI Phone Agent Playbook** (the voice capabilities this architecture hosts), **Automated Kiosk Deployment Brief** (a sibling edge device), and **Demand Forecast Briefing** (a workload that can run edge or cloud).

## Required Input

Provide the following:

1. **Operator profile** — Concept (QSR / fast-casual / coffee / pizza / casual-dining), unit count (current + 24-month plan), company-operated vs. franchised split, drive-thru vs. in-store vs. delivery mix, average unit volume, US-only vs. multi-country footprint, and the number of distinct store formats (free-standing drive-thru, mall/inline, kiosk-only, ghost/virtual).
2. **Connectivity reality** — Per-store internet profile (single ISP vs. redundant/failover, fiber vs. cable vs. cellular-backup, typical and worst-case uptime), how often stores currently lose connectivity, and what breaks operationally when they do (POS offline mode, payment, ordering).
3. **AI workloads in scope** — Which capabilities are on the table: drive-thru/lane voice ordering, phone/reservation voice, computer-vision (order accuracy, drive-thru car/lane analytics, food-quality/portion, safety, inventory shelf-counting), equipment/IoT monitoring, demand/prep forecasting, manager-alerting "store brain," labor/scheduling. Mark each as live / piloting / planned.
4. **Latency tolerance per workload** — Real-time hard limits (a voice agent must respond in well under a second to feel natural; a vision order-accuracy check must flag before the bag is handed off) vs. near-real-time (forecasting, end-of-day analytics) vs. batch (overnight roll-ups).
5. **Current tech stack** — POS (Toast, Square, PAR Brink, NCR Voyix, Qu, Revel, Clover), drive-thru hardware/headset system, existing camera/NVR install, network/SD-WAN vendor, identity, and any existing cloud (AWS/GCP/Azure) commitments or co-sell relationships.
6. **Vendor / platform options under evaluation** — Any named edge-AI platform, cloud-AI stack, silicon/appliance partner, or best-of-breed point vendors already in the RFP, plus whether a corporate-mandated platform is being pushed onto franchisees.
7. **Capex / opex envelope** — Per-store hardware budget ceiling, expected hardware-refresh horizon (3-year / 5-year), opex tolerance (per-store monthly platform + connectivity), and who owns the capex in a franchised system (corporate, franchisee, shared).
8. **Data-residency and privacy posture** — Whether voice recordings, drive-thru/lobby video, license-plate or face data, and per-guest order data may leave the store; biometric-law exposure by state; retention limits; and what must be processed and discarded on-device.
9. **Governance and franchise constraints** — Who signs off (CTO, COO, CIO, franchise advisory council), whether franchisees can opt in/out of an edge-hardware mandate, brand-standards liability, and the operator's public posture on automation.
10. **Decision and rollout horizon** — The decision deadline, the pilot-store count and regions available, and the date by which leadership wants a fleet-wide go/no-go.

## Instructions

You are a restaurant technology architect who has shipped store-systems estates across hundreds-to-thousands of units and who has lived through both the "everything to the cloud" and the "intelligence at the edge" cycles. Your job is to produce an operator-side architecture decision brief — not a vendor's platform brochure and not a generic "edge vs. cloud" explainer. Every recommendation must be tied to this operator's connectivity reality, workload latency limits, capex envelope, and franchise structure.

**Before you start:**
- Load `config.yml` from the repo root for concept, unit count, format mix, and brand voice.
- Reference `knowledge-base/terminology/` for restaurant + store-systems terms (drive-thru lane, OEPE/order-to-departure, throughput, 86'd, NVR, SD-WAN, edge appliance, inference, NPU/GPU, offline mode, prime cost, AUV).
- Reference `knowledge-base/tools-ecosystem/` (or stand up an inline vendor-map snapshot if the file is empty) for the current named edge-AI / store-intelligence platforms, cloud-AI restaurant stacks, and silicon/appliance options.
- Reuse any prior **AI Pilot Rollback Readiness Brief** output for this operator — every pilot proposed here must inherit that brief's rollback triggers, worker-experience gate, and third-party-dependency governance.
- Pull the most current public precedent before writing: which flagship operators have committed to at-the-edge AI architectures, what compute partner they chose, what they put on-device vs. cloud, and any measured throughput/accuracy/uptime claims — vendor and operator announcements in this category move monthly.

**Process:**

1. **Workload-to-topology map** — For each in-scope AI workload, classify the *correct* compute location from first principles before any vendor preference: edge-only (hard real-time + must survive a connectivity drop — e.g., lane voice ordering, order-accuracy vision at handoff, payment-adjacent flows), cloud-only (heavy training, cross-fleet analytics, model updates), or hybrid (inference at the edge, aggregation/learning in the cloud — the common pattern for forecasting and a manager "store brain"). Produce a table: workload, latency limit, connectivity-survival requirement, data-sensitivity, recommended topology, and the one-line reason. This map is the spine of the brief — it constrains every vendor choice that follows.

2. **Connectivity-resilience stress test** — Translate the operator's per-store connectivity reality into an architecture requirement. If stores lose internet even occasionally during peak, any revenue-critical AI workload (voice ordering, accuracy check) that lives in the cloud becomes a peak-hour outage. Specify, per workload, the required degraded-mode behavior (fail-open to a human, fall back to a cached local model, queue-and-sync) and the network investment (SD-WAN, cellular failover) that the chosen topology assumes. Flag any vendor pitch that quietly assumes always-on connectivity the operator does not actually have.

3. **Unified-platform vs. best-of-breed stance** — Decide how tightly to couple the capabilities. Lay out the genuine tradeoff: a single "store brain" platform (one vendor, one edge appliance, voice + vision + monitoring + manager alerts integrated, one throat to choke, simpler ops) vs. best-of-breed point solutions (best voice vendor + best vision vendor + best forecast vendor, lower switching cost per capability, more integration burden, more vendors to govern). Score against this operator's integration maturity, IT-team size, switching-cost tolerance, and risk appetite. State a recommended coupling stance and the conditions that would flip it (e.g., "consolidate only after two capabilities have each cleared a 12-week pilot; do not buy the bundle before the voice layer is proven").

4. **Capex, silicon, and refresh-cadence model** — Build the per-store and fleet-wide hardware math: edge-appliance/blade unit cost, camera/sensor adds, install labor, the network upgrade, plus the platform opex per store per month. Model the refresh horizon honestly — on-device AI silicon ages on a roughly 3-year curve and a model upgrade can outgrow the installed hardware, so the operator is underwriting a recurring capex cycle, not a one-time buy. Compare against a cloud-heavy alternative's opex curve. For a franchised system, make the capex-ownership question explicit (who buys the blades — corporate, franchisee, or shared) because a corporate-mandated edge-hardware install is a known franchise-tension flashpoint and must route through the mandatory-tech tension audit in the Rollback Readiness Brief.

5. **Lock-in and exit audit** — Identify every lock-in vector the architecture creates: silicon/appliance lock-in (proprietary edge hardware you can't repurpose), cloud-partner lock-in (the platform is co-built with one hyperscaler), model lock-in (you can't swap the underlying model), data-gravity lock-in (your fleet's training data lives in the vendor's cloud), and contract lock-in. Rate each High/Medium/Low and specify the exit cost. Recommend the contractual and architectural hedges (data-portability clause, model-swap rights, hardware-reuse rights, no-exclusivity to one cloud) that keep the operator from being trapped if the vendor's economics or roadmap turn.

6. **Data-residency and on-device-privacy posture** — Map each workload's data against residency limits. Voice recordings, drive-thru/lobby video, and any license-plate, face, or biometric signal carry state-law exposure and brand risk; the architecture's strongest privacy argument is that edge inference lets sensitive media be processed and discarded on-device without ever leaving the store. Specify, per workload, what must stay on-device, what may be aggregated to the cloud (and in what de-identified form), retention limits, and the disclosure/consent posture. Flag biometric-heavy workloads (face/plate) for named-counsel review before any pilot.

7. **Precedent and vendor-map** — Catalog the current named precedents at the operator's altitude: which flagship operators have publicly committed to at-the-edge AI architecture, the compute/cloud partner each chose, what they run on-device vs. cloud (voice ordering, vision, manager "brain"), the fleet scale, and any measured throughput/accuracy/uptime claim — restating each as a generic precedent, not a copied vendor spec. Note where a flagship previously *retired* an AI deployment, because the prior-failure pattern is part of the diligence (vendor-claim vs. operator-measured accuracy is the central trap; see the Rollback Readiness Brief). Map each evaluated vendor against the workload-to-topology table from Step 1 and flag any capability the vendor over-promises at the edge.

8. **Staged rollout plan with rollback gates** — Convert the decision into a sequence, never a big-bang. Stage it: single-capability pilot at a small named store cluster → measure operator-side ground-truth metrics (not vendor-published numbers) → add the second capability only after the first clears → regional expansion → fleet-wide go/no-go. For each stage, specify the success metric, the worker-experience gate, the rollback trigger, and the named owner. Tie every gate back to the **AI Pilot Rollback Readiness Brief**. The deliverable ends in a single named recommendation: the recommended topology per workload, the coupling stance, the pilot scope, the capex envelope, and the date of the fleet-wide go/no-go.

**Output requirements:**

- Structured brief with numbered sections matching the process above.
- A one-page CTO/COO summary at the top: recommended compute topology per workload, unified-vs-best-of-breed stance, pilot scope and store cluster, capex envelope and refresh horizon, top three lock-in/risk items, and the fleet-wide go/no-go date.
- The Step 1 workload-to-topology table and the Step 4 capex model formatted to paste directly into a board deck.
- Correct restaurant + store-systems terminology throughout (lane, throughput, OEPE, offline mode, edge appliance, inference, NPU, SD-WAN, capex/opex, AUV, prime cost).
- Every proposed pilot explicitly inherits the Rollback Readiness Brief gates.
- Saved to `outputs/` if the user confirms.

## Related Skills

- `admin/ai-pilot-rollback-readiness-brief.md` — The governance gate every pilot in this brief must pass; supplies rollback triggers, worker-experience gate, mandatory-tech franchise-tension audit
- `admin/multi-unit-finance-ai-selection-brief.md` — Capex/opex modeling and finance sign-off for the hardware estate
- `customer-service/drive-thru-ai-rollout-playbook.md` — The lane-voice capability this architecture hosts at the edge
- `customer-service/ai-phone-agent-playbook.md` — Front-of-house voice capability sharing the same compute decision
- `operations/automated-kiosk-deployment-brief.md` — Sibling edge device with overlapping hardware/capex governance
- `operations/demand-forecast-briefing.md` — A workload that can run edge-inference or cloud, decided by this brief

## Example Output

### Example 1 — 1,200-unit QSR deciding whether to standardize on a corporate edge-AI "store brain" platform

**Input (CTO-level brief request, board deadline in 10 days):**
- Operator: Coastline Burger Co., 1,200-unit QSR (US-only); 70% franchised / 30% company-operated; 85% of units have a drive-thru; format mix is mostly free-standing drive-thru plus ~180 inline/mall units; AUV ~$2.9M; one dominant store format plus the inline subset.
- Connectivity reality: ~78% of stores on a single ISP with no failover; cable-modem primary; measured worst-case is 1–2 short outages per week, more during regional weather; today a connectivity drop forces POS into offline mode and kills any cloud-dependent ordering aid.
- Workloads in scope: drive-thru lane voice (piloting, 40 units), order-accuracy vision at bag-handoff (planned), drive-thru lane/car analytics (planned), demand/prep forecasting (live, cloud), manager-alert "store brain" (planned), equipment/IoT monitoring (planned).
- Latency tolerance: lane voice and accuracy-vision are hard real-time (sub-second, must survive an outage); forecasting and the manager brain are near-real-time/batch.
- Stack: PAR Brink POS, existing headset drive-thru system, partial camera/NVR install in ~300 units, SD-WAN pilot in company stores only, existing GCP analytics footprint.
- Vendor options: one bundled "intelligent store platform" (edge appliance + voice + vision + manager brain, co-built with a hyperscaler, corporate wants to mandate it fleet-wide), vs. keeping a best-of-breed voice vendor + a separate vision vendor + the existing cloud forecast tool.
- Capex envelope: ≤ $6,500/store hardware ceiling; 5-year refresh assumption from finance (IT thinks 3 is realistic); opex tolerance ~$300/store/mo; capex ownership unresolved for franchisees.
- Data-residency: drive-thru video + voice may NOT leave the store without de-identification; no plate/face retention; biometric-law exposure in several states.
- Governance: CTO + COO sign; franchise advisory council must bless any hardware mandate; public posture is "team-member-assist, not replacement."
- Horizon: pilot now, fleet-wide go/no-go target in two quarters.

**Output — 1-page CTO/COO summary (top of brief):**

> **Recommendation:** Adopt a **hybrid edge-first topology**, but **do NOT mandate the bundled platform fleet-wide yet.** Run **edge inference for the two hard-real-time, outage-critical workloads** (lane voice, order-accuracy vision) and **keep forecasting + the manager "brain" cloud-hybrid** (edge signals, cloud aggregation). Ship as **best-of-breed for the first two quarters**, with a defined consolidation trigger — do not buy the bundle before the voice layer has cleared a 12-week operator-measured pilot.
>
> **Why edge-first for voice + accuracy-vision:** 78% of stores have no failover and lose connectivity weekly. Any revenue-critical AI that lives only in the cloud becomes a peak-hour outage in those stores. Lane voice and bag-handoff accuracy must run on-device and degrade gracefully to a team member, not to a spinning cursor.
>
> **Coupling stance:** Best-of-breed for now. The bundle's single-throat-to-choke simplicity is real but is not worth pre-committing $6,500/store of proprietary silicon before a single capability is proven at our measured accuracy (not the vendor's published number). Consolidation trigger: voice clears 12-week pilot at operator-measured ≥ target accuracy AND vision clears its own pilot — then re-bid the bundle from a position of proof.
>
> **Capex reality:** Underwrite a **3-year**, not 5-year, silicon-refresh cycle — on-device AI hardware ages on a ~3-year curve and a model upgrade can outgrow the installed appliance. Finance's 5-year assumption understates lifetime cost; the brief re-models both.
>
> **Top 3 risks:** (1) Connectivity-assumption mismatch — the bundled vendor's demo assumes always-on internet we don't have; mitigation: contractually require validated offline-mode behavior per workload. (2) Franchise capex-mandate tension — a corporate edge-hardware mandate on 840 franchised units is a flashpoint; route through the Rollback Readiness Brief mandatory-tech tension audit with named counsel before any mandate. (3) Silicon + cloud lock-in — proprietary appliance + single-hyperscaler co-build; mitigation: data-portability + hardware-reuse + no-cloud-exclusivity clauses before signature.
>
> **Fleet-wide go/no-go:** end of Q+2, gated on the staged pilot results below.

**Section 1 — Workload-to-topology map:**

| Workload | Latency limit | Must survive outage? | Data sensitivity | Recommended topology | Reason |
|---|---|---|---|---|---|
| Drive-thru lane voice | Sub-second | Yes (revenue-critical) | Voice (de-id before cloud) | **Edge-only inference** | Outage = lost orders; latency must feel natural |
| Order-accuracy vision (handoff) | Real-time (<1–2s) | Yes | Video (must not leave store) | **Edge-only inference** | Must flag before bag leaves; video can't egress |
| Drive-thru lane/car analytics | Near-real-time | Partial | Plate/car (biometric risk) | **Edge inference + cloud aggregate (de-id)** | Counsel review; discard raw media on-device |
| Demand/prep forecasting | Near-real-time/batch | No | Sales data | **Cloud-hybrid** | Cross-fleet learning belongs in cloud |
| Manager-alert "store brain" | Near-real-time | Partial | Ops data | **Cloud-hybrid (edge signals)** | Alerts can tolerate brief lag; learning is fleet-wide |
| Equipment/IoT monitoring | Near-real-time | Partial | Telemetry | **Edge collect + cloud analyze** | Local capture, central trend analysis |

**Section 2 — Connectivity-resilience stress test (abbreviated):**

| Workload | Degraded-mode requirement | Network investment assumed |
|---|---|---|
| Lane voice | Fail-open to team member instantly; local cached model handles common orders offline | Edge appliance + cellular failover in single-ISP stores |
| Accuracy vision | Continue on-device; queue results, sync when back online | Edge appliance (no cloud dependency) |
| Forecasting | Last-known forecast cached locally; resync on reconnect | None beyond current |

Any vendor pitch that assumes always-on connectivity is flagged: 78% of the fleet cannot honor that assumption today.

**Section 3 — Coupling stance:** Best-of-breed for two quarters; consolidate only on the dual-pilot trigger above. Full scoring table in the brief body.

**Section 4 — Capex model (per-store + fleet, abbreviated):**

| Line | Edge-first (recommended) | Cloud-heavy alternative |
|---|---|---|
| Edge appliance / blade | ~$3,800 | $0 |
| Camera/sensor adds | ~$1,400 | ~$1,400 |
| Install + network (failover) | ~$1,100 | ~$500 |
| Per-store capex | **~$6,300 (under ceiling)** | ~$1,900 |
| Platform opex/store/mo | ~$280 | ~$340 (cloud inference + egress) |
| Refresh horizon | **3 yr (IT-realistic)** | 4–5 yr |

Franchise capex-ownership decision routed to the mandatory-tech tension audit before any mandate.

**Section 5 — Lock-in audit:** Silicon: High (proprietary appliance) → require hardware-reuse rights. Cloud-partner: High (single-hyperscaler co-build) → require no-exclusivity. Model: Medium → require model-swap rights. Data-gravity: High → require data-portability clause. Contract: Medium.

**Section 6 — Data-residency posture:** Lane video + voice processed and discarded on-device; only de-identified aggregates egress; no plate/face retention; biometric-heavy lane analytics flagged for named-counsel review before pilot.

**Section 7 — Precedent map:** Anchored on the current flagship at-the-edge "store brain" precedents — large QSRs installing on-premise inference hardware fleet-wide with a hyperscaler partner, running voice + vision + manager alerting on-device with cloud aggregation, citing high autonomous-completion rates in small pilots — restated generically, with the central diligence caveat that vendor-published completion/accuracy rates must be re-measured operator-side, and that at least one flagship has previously retired an AI deployment after accuracy drift (the prior-failure pattern from the Rollback Readiness Brief).

**Section 8 — Staged rollout with rollback gates:**

| Stage | Scope | Success metric (operator-measured) | Rollback trigger | Owner |
|---|---|---|---|---|
| 1 | Lane voice, 40→80 units, 12 wk | Order-accuracy + throughput hold; team-member-experience gate green | Accuracy below floor OR crew NPS drop | VP Drive-Thru |
| 2 | Accuracy-vision, same cluster | Catch-rate vs. ground truth; no double-work | Double-work anti-pattern detected | Ops Tech Dir. |
| 3 | Consolidation re-bid | Both pilots green → re-bid bundle | Either pilot red → stay best-of-breed | CTO |
| 4 | Regional → fleet | Regional metrics hold | Trade-press contagion / franchise revolt | CTO + COO |

Fleet-wide go/no-go: end of Q+2, contingent on Stages 1–2 green and the franchise tension audit cleared.

---

This brief is paste-ready for the CTO's board pack. Section 1 (workload-to-topology), Section 4 (capex model), and Section 8 (staged rollout) typically copy directly into the board slides; the connectivity stress test and lock-in audit copy into the vendor SOW and the IT risk register.
