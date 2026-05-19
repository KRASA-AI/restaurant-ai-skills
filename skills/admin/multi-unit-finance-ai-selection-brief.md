---
name: "Multi-Unit Restaurant Finance AI / xFP&A Selection Brief"
category: admin
tools: [claude, chatgpt]
difficulty: advanced
time_saved: "~6 hr/vendor evaluation"
version: 1.0
last_eval_score: null
---

# 📊 Multi-Unit Restaurant Finance AI / xFP&A Selection Brief

## Purpose

Produce a CFO-grade selection brief for restaurant-vertical Financial Planning & Analysis (xFP&A) AI platforms — covering the full restaurant P&L (prime cost, labor, COGS, variance, same-store sales, scheduling, menu engineering). The brief tells a multi-unit operator's finance team which vendor to underwrite, on what integration path against the existing ERP + POS + labor stack, with which named-operator case studies as proof points, and which measured ROI levers (labor-forecast error, prime-cost variance, AP automation, inventory shrink) to track in the first 12 months.

This skill is materially distinct from the **Embedded Multi-Unit AI Ops Copilot Brief** (operations decision partner — sales, inventory, labor, marketing, execution) and **Dynamic Menu Pricing Advisor** (item-level pricing) and **Supplier Negotiation Brief** (vendor-side margin defense). The xFP&A AI layer is a **finance / FP&A decision partner** — the layer above operations, the layer below the GL. It sits between the operator's accounting / ERP system (NetSuite, Sage Intacct, R365, QuickBooks Enterprise, Acumatica, Microsoft Dynamics 365) and the operator's POS + labor systems (Toast, Square, Olo, PAR, HotSchedules, 7shifts), and produces real-time variance analysis, same-store-sales analytics, prime-cost forecasting, labor-sensitivity modeling, and menu-engineering / margin-management actions.

## When to Use

Use this skill when a multi-unit operator's CFO or VP of Finance is at the inflection point of (a) evaluating whether to ship a restaurant-vertical xFP&A AI platform, (b) selecting a vendor among the three current named platforms (Restaurant365 / R365 AI, Solver Restaurant on the Solver xFP&A platform, Crunchtime AI Analyst + AI Forecasting), (c) deciding between a restaurant-vertical xFP&A vendor and a horizontal xFP&A vendor (Workday Adaptive, Anaplan, Vena, Planful, OneStream) with custom restaurant templates, or (d) building the integration path against the operator's existing ERP + POS + labor stack with measurable first-year ROI targets.

Run this skill before a CFO board-of-directors recommendation, before an annual technology-stack budget allocation, or after a vendor RFP has surfaced two or more credible finalists. Pairs well with **Dynamic Menu Pricing Advisor** (item-level pricing decisions inform the menu-engineering module of any xFP&A platform), **Supplier Negotiation Brief** (vendor COGS context for prime-cost variance modeling), and **Staff Schedule Optimizer** (labor-sensitivity modeling tie-in).

## Required Input

Provide the following:

1. **Operator profile** — Concept (QSR / fast-casual / casual-dining / fine-dining / coffee / multi-brand), unit count (current + 24-month plan), average unit volume (AUV), total annual revenue, US-only vs. international footprint, franchise vs. company-operated split, corporate-only vs. franchisee-included financial reporting
2. **Existing tech stack** — Accounting / ERP (NetSuite, Sage Intacct, Acumatica, Microsoft Dynamics 365, R365, QuickBooks Enterprise), POS (Toast, Square, Olo Pay, PAR, Lightspeed, Revel, Clover), labor / scheduling (HotSchedules, 7shifts, Crunchtime Labor, Workday HCM), inventory / back-office (R365 Inventory, MarketMan, Crunchtime, PAR Brink), BI tooling (Tableau, Power BI, Looker, Sigma)
3. **Current FP&A operating model** — In-house finance team size, FP&A cycle (monthly close timeline, weekly variance review cadence, 13-week-forward forecast frequency), current pain points (manual roll-ups, spreadsheet sprawl, prime-cost variance latency, labor-forecast error percentage)
4. **Financial decision triggers** — Specific decisions the xFP&A layer must drive: prime-cost variance investigation, labor-sensitivity scenario modeling, same-store-sales attribution, menu-engineering margin recovery, P&L scenario planning by unit / region / brand
5. **Budget and timeline** — Annual license budget range, implementation budget range, target go-live timeline (Q-target), change-management runway (how many weeks of finance-team training), and the named ROI levers the CFO will report against in the first 12 months
6. **Vendor finalists** — Any vendor RFP shortlist already in flight; if none, request a market scan
7. **Operator constraints** — Data residency (US-only, EU GDPR), security posture (SOC 2 Type II requirement, single-sign-on integration), audit / compliance posture (PCAOB inspection, SOX-controls scope if public), and any vendor-blacklist exclusions

## Instructions

You are a restaurant CFO advisor and xFP&A vendor-selection specialist with deep experience in multi-unit operator finance teams, restaurant-vertical AI platforms, and ERP / POS / labor integrations. Your job is to produce a selection brief the CFO can present to the board, the CEO, and the operations leadership team — with named vendor recommendations, integration paths, measured ROI targets, and a change-management plan that respects the finance team's current operating model.

**Before you start:**
- Load `config.yml` from the repo root for unit count, concept, AUV, and brand voice
- Reference `knowledge-base/terminology/` for restaurant finance terms (prime cost, labor cost %, theoretical vs. actual variance, T-vs-A, COGS, prime-cost-variance attribution, weekly P&L, same-store-sales / SSS, average unit volume / AUV, four-wall EBITDA, contribution margin, menu-mix-adjusted margin, labor-forecast error / LFE, scheduled-vs-actual hours, sales-per-labor-hour / SPLH, scheduling-efficiency index / SEI)
- Reference `knowledge-base/vendor-map/xfp-a-vendors.md` (or stand up the vendor-map snapshot inline if the file is missing) for the current named platforms in the restaurant-vertical xFP&A AI category
- Reference any prior **Embedded Multi-Unit AI Ops Copilot Brief** outputs the operator has run — the operations-copilot and xFP&A platforms overlap on data sources (POS, labor, inventory) but are distinct on decision-surface

**Process:**

1. **Operator-profile fit** — Map the operator's profile (concept, AUV, unit count, US-only vs. international, franchise mix, corporate-only vs. franchisee reporting) against the three current named restaurant-vertical xFP&A AI platforms (R365 AI / Restaurant365, Solver Restaurant on Solver xFP&A, Crunchtime AI Analyst + AI Forecasting) and the horizontal xFP&A platforms with restaurant-vertical templates (Workday Adaptive Restaurant, Anaplan Restaurant, Vena Restaurant, Planful Restaurant, OneStream Restaurant). Flag the natural-fit subset.

2. **Integration-path audit** — For each finalist vendor, map the integration to the operator's existing ERP + POS + labor stack: pre-built connectors, certified integration partners, custom-build effort estimate (weeks), data-residency / security / SSO posture, and any vendor lock-in risk (e.g., R365 AI assumes the operator is on R365 accounting; Solver Restaurant assumes the operator is on one of NetSuite / Sage Intacct / Acumatica / Microsoft Dynamics 365; Crunchtime AI is most natural for an operator already running Crunchtime Inventory + Labor). Score integration risk High / Medium / Low per vendor.

3. **AI capability mapping** — For each finalist, enumerate the specific AI capabilities that map to the operator's named financial decision triggers:
   - **R365 AI (Restaurant365)** — AI Dashboards + Labor Management Suite (generally available); AI Advisor, AI Scheduling, Secure Data Share (early access via R365 Chef's Table). Built on unified financial + operational data (accounting + inventory + labor + scheduling + POS in one system). Reference ROI: 15% reduction in labor-forecast error → ~$100K annual savings per 10 locations (Black Rock Coffee Bar named-operator case study, 190+ locations).
   - **Solver Restaurant (Solver Global)** — Solver Copilot AI experience layer on the Solver xFP&A platform; ships with 70+ marketplace templates including Same-Store Sales (SSS) Dashboard, Prime Cost Variance Report, Menu Engineering Report, Labor Sensitivity & Scheduling Report. Integrates with NetSuite, Sage Intacct, Acumatica, Microsoft Dynamics 365, and POS / labor systems via a published connector library. Pre-built templates lift implementation runway vs. a custom Anaplan / Workday Adaptive model.
   - **Crunchtime AI Analyst + AI Forecasting** — Natural-language ad-hoc analytics (AI Analyst), 99% sales-forecast accuracy claim (AI Forecasting), AI Actions for form-driven execution audits, Voice-Based Inventory, Photo Intelligence (early access from May 13 2026 Live Launch). Strongest fit when the operator is already on Crunchtime for inventory + labor; xFP&A is one capability layer in a broader operations + finance stack.
   - **Horizontal xFP&A with restaurant templates** — Workday Adaptive, Anaplan, Vena, Planful, OneStream — most often selected by enterprise multi-brand operators with non-restaurant business segments (lodging, retail, manufacturing) where one xFP&A platform must serve all segments. Higher implementation cost; longer time-to-value; deeper modeling flexibility.

4. **Named-operator deployment-playbook map** — Catalog the named-operator case studies for each finalist:
   - **R365 AI** — Black Rock Coffee Bar (190+ locations, weekly inventory through R365 has improved accuracy / visibility / buying behavior; Innovation Theater session with Solutions Architect Marc Cohen and BI Senior Manager Jaclyn Nesemann at NRA Show 2026 May 16–19). The Restaurant People (8 new locations launched + 20% savings).
   - **Solver Restaurant** — Solver Global blog references on multi-unit restaurant operators; specific named-operator case study cadence is still building post-2026-04-14 launch.
   - **Crunchtime** — 600,000+ restaurant locations served (industry footprint claim from Crunchtime); CEO John Raguin cites 99% AI Forecasting accuracy as the baseline ROI proof point; named operator references include Five Guys, Chipotle's franchisee deployments, Cava, Wahlburgers, Wendy's franchisee deployments (operator names vary by capability module).
   - **Horizontal vendors** — Reference deployments at enterprise multi-brand operators (Yum! Brands, Restaurant Brands International, Inspire Brands have used a mix of horizontal xFP&A platforms with custom restaurant templates).

5. **ROI lever model** — Quantify the first-12-month measurable ROI for each finalist against the operator's named financial decision triggers. Standard ROI levers to model:
   - **Labor-forecast error reduction** — Baseline LFE for the operator (industry mid-market baseline 8–15% LFE; enterprise-tier 5–10%); target reduction with each vendor; dollar impact = (LFE delta) × (weekly labor spend) × 52 weeks
   - **Prime-cost variance reduction** — Baseline variance (industry benchmark T-vs-A on COGS = 50–150 bps; on labor = 150–300 bps); target reduction; dollar impact = (variance delta in bps) × (annual revenue per unit) × (unit count)
   - **Same-store-sales lift attribution** — Menu-engineering and dynamic-pricing levers attributable to xFP&A insights; quantify with a margin-recovery-per-unit number not a top-line lift (top-line attribution is hard)
   - **Finance-team productivity** — Hours per close, days to weekly P&L, hours to FP&A re-forecast cycle; convert to FTE equivalents at fully-loaded cost
   - **Inventory shrink / waste reduction** — Theoretical-vs-actual COGS attribution that drives operational corrective action; dollar impact attribution requires honest attribution discipline

6. **Total cost of ownership (TCO)** — Build a 3-year TCO table per finalist: annual license cost, implementation cost, integration / connector cost, change-management training cost, ongoing analyst / FP&A coverage cost. Express as a percentage of annual revenue for benchmark.

7. **Vendor lock-in and exit risk** — For each finalist, audit the data-portability posture: does the vendor export historical data on contract termination? does the operator retain ownership of all derived models, dashboards, and forecast logic? what is the runway to migrate to a successor platform? what is the vendor's M&A / private-equity exposure (Restaurant365 PE-backed; Solver Global PE-backed; Crunchtime PE-backed; horizontal vendors public-equity or PE) — and how does that affect product-roadmap continuity?

8. **Change-management plan** — For the selected finalist, build a 16-week change-management runway: week 1-2 (vendor SoW signed, integration kickoff), week 3-6 (data-mapping + connector build), week 7-10 (parallel-run with current FP&A operating model), week 11-12 (finance-team training cycles, 2 cycles), week 13-14 (operations-leadership training, dashboard rollout), week 15-16 (single-platform cutover, decommission of legacy spreadsheet sprawl). Identify the finance-team-side change-management owner (typically the VP of Finance or FP&A Director).

9. **Decision recommendation** — Produce a single named-vendor recommendation with explicit rationale tying the operator's profile, existing tech stack, financial decision triggers, ROI levers, and change-management runway. Include a backup-vendor recommendation as a hedge. Include a 12-month milestone plan: (a) months 1-3 implementation and parallel-run, (b) months 4-6 first-cycle variance reporting at the new fidelity, (c) months 7-9 menu-engineering / labor-sensitivity model adoption, (d) months 10-12 first measurable-ROI report-out to the board.

**Output requirements:**
- One-page CFO executive summary at the top: named-vendor recommendation, integration path, 12-month measurable ROI target, change-management runway
- Vendor comparison matrix (3-5 vendors × 12-15 criteria): operator-profile fit, integration risk, AI capability coverage, named-operator case studies, 3-year TCO, vendor lock-in risk
- Integration-path diagram (text-based): operator's ERP + POS + labor stack → vendor connectors → xFP&A AI layer → finance team / operations leadership consumption surfaces
- ROI lever model: baseline → target → dollar impact per lever per year, for the recommended vendor
- 3-year TCO table: license + implementation + integration + change-management + ongoing analyst coverage, expressed as a percentage of annual revenue
- Vendor lock-in / exit-risk audit table
- 16-week change-management runway with named owner per phase
- 12-month milestone plan with quarterly board report-out cadence
- Correct terminology: prime cost, labor cost %, T-vs-A, prime-cost variance, SSS, AUV, four-wall EBITDA, contribution margin, LFE, SPLH, SEI, menu-mix-adjusted margin
- Saved to `outputs/` if the user confirms

## Example Output

### Example 1 — Mid-market fast-casual (38 units, $52M revenue, on R365 accounting, evaluating R365 AI vs. Solver Restaurant)

```markdown
# Multi-Unit Restaurant Finance AI / xFP&A Selection Brief
## CucinaPiccola Group (38 units, 6 states, $52M revenue) — R365 AI vs. Solver Restaurant
## CFO: M. Alvarez | Prepared 2026-05-18 | Board recommendation 2026-06-09

## CFO Executive Summary
- **Recommendation:** Underwrite **R365 AI (Restaurant365)** for an 18-month exclusive xFP&A AI ship. CucinaPiccola is already on R365 accounting + inventory; the integration runway is 10–12 weeks rather than 18–24 with Solver Restaurant; the named-operator deployment-playbook is anchored by Black Rock Coffee Bar (190+ locations, comparable unit count + concept proximity); the AI Dashboards + Labor Management Suite is generally available now (no early-access dependency for the primary FP&A use case)
- **Integration path:** R365 AI sits on top of CucinaPiccola's existing R365 accounting + R365 Inventory + R365 Labor stack; POS data flows from Toast via the existing R365 connector; HotSchedules → R365 Labor connector live since 2025; no net-new connector build required
- **Named operator deployment playbook anchor:** Black Rock Coffee Bar (190+ locations) — 15% reduction in average labor-forecast error → ~$100K annual savings per 10 locations (per Restaurant365 2026-05-12 launch announcement). CucinaPiccola at 38 units models to $380K annual labor-forecast savings at the same delta
- **12-month measurable ROI target:** $410K annual savings (= $380K labor-forecast error reduction + ~$30K finance-team productivity gain by collapsing the weekly variance-roll-up cycle from 3 days to same-day)
- **Change-management runway:** 12 weeks (shorter than 16-week standard because the data stack is already R365-native)
- **Backup vendor (hedge):** Solver Restaurant — selected if R365 AI's AI Advisor + AI Scheduling early-access modules slip beyond GA Q3 2026 and the CFO needs scenario-modeling depth that R365 AI Dashboards do not yet ship

## Vendor Comparison Matrix
| Criterion | R365 AI | Solver Restaurant | Crunchtime AI | Workday Adaptive + Restaurant Templates |
|---|---|---|---|---|
| Operator-profile fit (38u fast-casual, $52M rev, on R365) | **Excellent** | Good | Fair (Crunchtime requires migration off R365 Inventory) | Over-engineered for single-segment 38u operator |
| Integration risk against current stack | **LOW** (native R365) | MEDIUM (Solver connector to R365 published Q4 2025; certified) | HIGH (requires Crunchtime Inventory + Labor migration) | HIGH (custom build) |
| Implementation runway (weeks) | **10–12** | 18–24 | 24–32 | 36–52 |
| AI capabilities GA (vs. early access) | AI Dashboards + Labor Mgmt Suite GA; AI Advisor + AI Scheduling early access | Solver Copilot GA; 70+ marketplace templates GA | AI Analyst + AI Forecasting GA; Photo Intelligence early access | Adaptive Insights GA; restaurant templates custom build |
| Named multi-unit operator case study | **Black Rock Coffee Bar 190+u + The Restaurant People 8u + 20% savings** | Solver Global blog refs; case-study cadence building | Five Guys, Cava, Wahlburgers, Wendy's franchisees (operations-side anchors) | Yum! Brands, RBI references (enterprise multi-brand) |
| Measured ROI on labor-forecast error | **15% LFE reduction = ~$100K/10u** (R365 published) | Implied from Solver templates; not yet quantified at named-operator altitude | 99% AI Forecasting accuracy claim (vendor altitude) | Custom; no published restaurant-vertical altitude |
| Annual license cost (38u tier) | ~$95K | ~$140K | ~$210K (full Crunchtime suite) | ~$320K (Workday Adaptive enterprise tier) |
| 3-year TCO including implementation + change mgmt | **~$340K** | ~$520K | ~$840K | ~$1.45M |
| Vendor lock-in risk | MEDIUM (R365 already deep in stack; lock-in is real but already paid) | LOW (Solver runs on operator's existing ERP, lighter lock-in) | HIGH (Crunchtime is full-stack inventory + labor + AI) | LOW-MEDIUM |
| Vendor M&A / PE roadmap risk | PE-backed (KKR); roadmap continuity strong | PE-backed (Marlin Equity); roadmap continuity strong | PE-backed (Battery Ventures); roadmap continuity strong | Public (WDAY); roadmap continuity strong |
| Time-to-first-board-report-out | **Month 4** | Month 6 | Month 8 | Month 12 |

## Integration-Path Diagram (text)
```
CucinaPiccola operator stack:
  Toast POS (38 units)
    ↓ (existing R365 connector, live since 2024)
  R365 Accounting + R365 Inventory + R365 Labor
    ↓ (R365 AI native data plane)
  R365 AI: AI Dashboards (GA) + Labor Mgmt Suite (GA)
    + AI Advisor (early access via Chef's Table)
    + AI Scheduling (early access via Chef's Table)
    ↓
  Finance team consumption: CFO Dashboard (4-wall EBITDA, prime-cost variance, LFE)
  Operations consumption: GM Dashboard (T-vs-A by unit, SPLH, SEI, menu-mix-adjusted margin)
```

## ROI Lever Model (12-month, R365 AI shipped at month 0)
| Lever | Baseline | Target | $ Impact / Year | Confidence |
|---|---|---|---|---|
| Labor-forecast error | 11% LFE (trailing 12-mo) | 9.5% (15% reduction matching Black Rock published) | **$380K** (weekly labor spend ~$485K × 38u × 1.5% delta × 52 wks) | HIGH (Black Rock named-operator anchor) |
| Prime-cost variance on COGS | 180 bps T-vs-A | 130 bps T-vs-A | $260K (52u-rev × 50 bps) — separate from labor | MEDIUM (depends on operations-side adoption of variance alerts) |
| Same-store-sales menu-engineering attribution | n/a | +50 bps margin on top-quartile menu items | $90K conservative (margin-recovery, not top-line lift) | MEDIUM-LOW (attribution hard) |
| Finance-team productivity (weekly variance close cycle) | 3 days (sprawled across team) | Same-day (auto-roll-up) | $30K (0.4 FTE saved at $75K fully-loaded) | HIGH |
| Inventory shrink reduction | 2.1% of COGS | 1.7% of COGS | $48K (COGS ~$15M × 40 bps) | MEDIUM |
| **Total** | | | **$808K gross / ~$410K conservative attribution (year 1)** | |

## 3-Year TCO (R365 AI, 38 units, expressed as % of annual revenue)
| Year | License | Implementation | Integration / Connector | Change Mgmt | Ongoing Analyst Coverage | Total | % of $52M Rev |
|---|---|---|---|---|---|---|---|
| Y1 | $95K | $60K | $0 (R365-native) | $35K (FP&A training) | $40K (0.5 FTE) | **$230K** | 0.44% |
| Y2 | $98K | n/a | $0 | $5K (refresher) | $40K | **$143K** | 0.27% |
| Y3 | $102K | n/a | $0 | $5K | $40K | **$147K** | 0.28% |
| **3-yr total** | | | | | | **$520K** | 0.33% blended |

## Vendor Lock-in / Exit Risk Audit
| Risk | R365 AI Posture |
|---|---|
| Data portability on contract termination | R365 exports all historical accounting, inventory, labor, and AI-derived dashboards via standard export tooling |
| Ownership of derived models | Operator retains all dashboards and report definitions; AI-trained models reside with vendor (industry-standard posture) |
| Successor-platform migration runway | 12–18 weeks to migrate to Solver Restaurant or Crunchtime (POS / labor data is stack-portable; menu-engineering and dashboard logic is rebuild work) |
| Vendor PE M&A exposure | KKR investment 2022; growth-stage trajectory; product-roadmap continuity strong; secondary M&A risk low through 2027 |
| SOC 2 / data residency | SOC 2 Type II current; US data residency; SSO via SAML 2.0 standard |

## 12-Week Change-Management Runway
| Week | Phase | Owner | Deliverable |
|---|---|---|---|
| 1 | SoW signed; integration kickoff | CFO + R365 PM | SoW execution; kickoff call |
| 2-3 | Data mapping (POS → accounting → labor) | R365 implementation lead + CucinaPiccola IT | Data-mapping document |
| 4-5 | Parallel-run on AI Dashboards (1 region, 6 units) | VP Finance | First parallel dashboard report |
| 6-7 | Labor Mgmt Suite parallel-run (1 region) | VP Operations + VP Finance | LFE comparison report |
| 8-9 | Finance-team training (2 cycles, 4 hrs each) | VP Finance | Finance-team certification |
| 10 | Operations-leadership training (GM cohort, 2 hrs) | VP Operations | GM-cohort certification |
| 11 | Full 38u cutover; legacy spreadsheet sprawl deprecated | VP Finance | Production cutover memo |
| 12 | First single-platform weekly variance close at same-day cycle | VP Finance | First board-altitude weekly P&L |

## 12-Month Milestone Plan
- **Month 0:** SoW signed (R365 AI 18-month exclusive)
- **Month 3:** Production cutover; first single-platform weekly close
- **Month 4:** First board report-out — baseline LFE vs. target LFE, first variance-trend chart
- **Month 6:** First quarterly board report — measured LFE reduction, first attribution on prime-cost variance
- **Month 9:** Menu-engineering / labor-sensitivity model adoption — operator-led menu re-engineering on bottom-quartile items
- **Month 12:** Year-1 ROI report — measured savings against $410K target; recommendation on AI Advisor + AI Scheduling GA rollout from early-access; vendor renewal decision

## Backup-Vendor Hedge: Solver Restaurant
Triggered if (a) R365 AI's AI Advisor + AI Scheduling slip past GA Q3 2026 and the CFO needs scenario-modeling depth, (b) CucinaPiccola acquires a non-restaurant operating segment (lodging, retail) that R365 does not serve, or (c) M&A / PE roadmap risk materializes post-Q3. Solver Restaurant runs on top of NetSuite or Sage Intacct (migration off R365 required), 70+ marketplace templates lift implementation runway from a Workday Adaptive baseline, certified connector library, PE-backed with strong roadmap continuity.
```

### Example 2 — Enterprise multi-brand operator (4 brands, 380 units, $720M revenue, evaluating restaurant-vertical vs. horizontal xFP&A)

```markdown
# Multi-Unit Restaurant Finance AI / xFP&A Selection Brief
## ParkAvenue Hospitality Group (4 brands, 380 units, $720M revenue) — Restaurant-vertical vs. Workday Adaptive Restaurant
## CFO: D. Tanaka | Prepared 2026-05-18 | Board recommendation 2026-07-14

## CFO Executive Summary
- **Recommendation:** Underwrite a **two-vendor architecture**: (1) **Workday Adaptive Restaurant + custom templates** for enterprise-altitude consolidated FP&A across all 4 brands (this is the layer the CFO and the board consume), AND (2) **R365 AI for the 2 brands already on R365 accounting** (60 units of the 380) and **Crunchtime AI for the 1 brand on Crunchtime Inventory + Labor** (190 units) — vertical-AI consumption at the operations-leadership altitude within those brands. The 4th brand (130 units on a custom NetSuite implementation) ships **Solver Restaurant** as the vertical-AI layer on top of NetSuite
- **Rationale:** A single-vendor restaurant-vertical xFP&A AI cannot serve 4 brands on 3 different accounting / inventory stacks at the enterprise altitude without 18+ months of normalization work. The horizontal layer (Workday Adaptive) is the consolidated FP&A truth table for the board. The vertical-AI layers are brand-local consumption surfaces for the operations leadership
- **12-month measurable ROI target:** $4.2M annual savings (= $2.1M blended labor-forecast-error reduction across 380 units + $1.4M prime-cost variance reduction at the brand-portfolio level + $0.7M finance-team productivity gain by collapsing the brand-by-brand variance roll-up cycle into a single Workday Adaptive consolidated cycle)
- **Change-management runway:** 36 weeks (longer than mid-market norm because 4 brands × 3 stacks × 2 vendor architectures)
- **3-year TCO target:** ~$5.8M (=$2.1M Workday Adaptive Restaurant + $1.4M R365 AI 2-brand + $1.6M Crunchtime AI 1-brand + $0.7M Solver Restaurant 1-brand), or 0.27% of cumulative 3-year revenue — within enterprise benchmark

## Vendor Architecture Diagram (text)
```
ParkAvenue Hospitality Group enterprise stack:

Brand A (Coastal Grill, 60u, on R365):     Toast → R365 Accounting → R365 AI
Brand B (Hearth Pizza, 60u, on R365):      Toast → R365 Accounting → R365 AI
Brand C (Bowls & Co, 190u, on Crunchtime): PAR Brink → Crunchtime → Crunchtime AI
Brand D (Park Steakhouse, 70u, on NetSuite + Solver): Square → NetSuite → Solver Restaurant
                                                ↓
                                                Workday Adaptive Restaurant (consolidated FP&A)
                                                ↓
                                            CFO Dashboard | Board Dashboard | Quarterly Investor Pack
```

## ROI Lever Model (12-month)
| Lever | Baseline | Target | $ Impact / Year |
|---|---|---|---|
| Blended labor-forecast error reduction (380u) | 9.5% LFE | 8.0% LFE (16% reduction) | **$2.1M** (weekly labor $2.7M × 1.5% × 52 wks) |
| Prime-cost variance reduction (portfolio) | 160 bps | 110 bps | **$1.4M** ($720M rev × 20 bps weighted) |
| Finance-team productivity (consolidated brand close) | 7 days (4 brand-by-brand cycles) | Same-day enterprise close | **$0.7M** (5 FTE consolidated to 1 FTE coordinator) |
| Same-store-sales menu-engineering attribution | n/a | Conservative attribution | $0.4M |
| Inventory shrink reduction | 2.4% blended | 1.9% blended | $1.0M (blended-COGS-weighted) |
| **Total gross** | | | **~$5.6M** |
| **Conservative attribution (year 1)** | | | **~$4.2M** |

## 3-Year TCO Per Architecture Component
| Component | Year 1 | Year 2 | Year 3 | 3-yr Total |
|---|---|---|---|---|
| Workday Adaptive Restaurant + custom templates | $850K | $600K | $620K | $2.07M |
| R365 AI (2 brands × 60u + 60u = 120u) | $480K | $290K | $300K | $1.07M (lower-tier vs. Example 1 because R365 is mature in this stack) |
| Crunchtime AI (1 brand × 190u) | $620K | $480K | $500K | $1.60M |
| Solver Restaurant (1 brand × 70u) | $280K | $190K | $200K | $0.67M |
| Cross-stack integration / data warehouse / Workday-feeder ETL | $250K | $60K | $60K | $0.37M |
| **Total** | **$2.48M** | **$1.62M** | **$1.68M** | **$5.78M** |

## 36-Week Change-Management Runway (high-level)
- Weeks 1-8: Workday Adaptive Restaurant SoW, custom-template build, Brand A + B + C + D data-feeder ETL design
- Weeks 9-16: Brand A + B R365 AI implementation (R365-native, 8-week runway each)
- Weeks 17-24: Brand C Crunchtime AI implementation (Crunchtime-native, 8-week runway)
- Weeks 25-30: Brand D Solver Restaurant implementation (NetSuite-native, 6-week runway)
- Weeks 31-34: Workday Adaptive Restaurant data-feeder cutover from all 4 brands
- Weeks 35-36: First enterprise-altitude consolidated weekly close + board-altitude dashboard live
```

## Operator-Decision-Window Note

The 2026 cycle is the **first cycle with three named restaurant-vertical xFP&A AI vendors and a published named-operator deployment playbook with measured ROI**. The Solver Restaurant launch (2026-04-14) established the category; the R365 AI launch (2026-05-12, NRA Show 2026 booth #6027 May 16–19) shipped the second vendor with a named-operator case study at the 190+-location altitude; Crunchtime AI Analyst + AI Forecasting has been in market since 2024 and continues to be the most natural fit for an operator already on Crunchtime Inventory + Labor. The horizontal-xFP&A category (Workday Adaptive, Anaplan, Vena, Planful, OneStream) is most relevant for enterprise multi-brand operators with non-restaurant segments. Operators evaluating a vendor in 2026-Q2 should expect a 10–18-week implementation runway for restaurant-vertical and a 36–52-week runway for horizontal-vendor-with-custom-templates.

The next-cycle promotion triggers for this skill are: (a) a fourth named restaurant-vertical xFP&A AI vendor ship (e.g., a Toast-native or Square-native xFP&A AI layer, or an Anaplan / Workday Adaptive published restaurant-template pack with vertical AI assistant), (b) a third named-operator deployment playbook from any current finalist with measured first-year ROI, and (c) a published franchisor-side mandate from a top-50 chain that all franchisees adopt one specified xFP&A AI vendor.
