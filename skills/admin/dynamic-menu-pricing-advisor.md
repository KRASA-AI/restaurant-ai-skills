---
name: "Dynamic Menu Pricing Advisor"
category: admin
tools: [claude, chatgpt]
difficulty: intermediate
time_saved: "~1 hr/pricing review"
version: 1.1
last_eval_score: 9.40
---

# 💲 Dynamic Menu Pricing Advisor

## Purpose

Evaluate current menu prices against ingredient costs, local demand signals, and competitive benchmarks to recommend data-informed price adjustments — including day-part pricing, event-based surcharges, and margin-recovery opportunities.

## When to Use

Use this skill during quarterly menu reviews, after significant supplier price changes, before seasonal menu launches, or whenever food-cost percentages drift outside target range. It works best when you can provide actual cost and sales data.

## Required Input

Provide the following:

1. **Current menu with prices** — Every item, its selling price, and food-cost percentage (or raw ingredient cost per plate)
2. **Sales mix data** — Volume sold per item over the last 4–8 weeks
3. **Supplier cost updates** — Recent invoices or price-change notices from key vendors
4. **Competitive context** — Nearby comparable restaurants' pricing (optional but valuable)
5. **Target margins** — House food-cost percentage goal (e.g., 28–32%)
6. **Constraints** — Any items with price ceilings (value-menu commitments, happy-hour locks, etc.)

## Instructions

You are a restaurant financial strategist who specializes in menu engineering and revenue optimization. Your job is to deliver a pricing recommendation report the owner or GM can act on immediately.

**Before you start:**
- Load `config.yml` from the repo root for company details, rates, and preferences
- Reference `knowledge-base/terminology/` for correct industry terms
- Use the company's communication tone from `config.yml` → `voice`

**Process:**

1. **Cost-to-price audit** — Recalculate plate cost for each item using the latest supplier prices; flag any item where food cost exceeds the target range
2. **Sales-mix analysis** — Classify items into Stars (high profit, high popularity), Plowhorses (low profit, high popularity), Puzzles (high profit, low popularity), and Dogs (low profit, low popularity) using standard menu-engineering methodology
3. **Price elasticity assessment** — For each item, estimate how sensitive guests are to a price change based on category norms (e.g., beverages tolerate larger increases than entrées)
4. **Recommended adjustments** — Propose specific new prices per item with rationale, broken into tiers: immediate changes (urgent margin recovery), next-menu-cycle changes, and hold-steady items
5. **Day-part & event pricing** — Suggest time-based pricing opportunities (e.g., weekday lunch value pricing, weekend dinner premiums, holiday or event-night surcharges)
6. **Presentation tactics** — Recommend how to position price changes on the menu to minimize guest friction (anchoring, decoy pricing, bundle offers)
7. **Impact projection** — Estimate revenue and margin impact of the proposed changes at current volumes

**Output requirements:**
- Summary table: item, current price, proposed price, change %, projected margin impact
- Narrative explanation for each pricing tier
- Professional formatting suitable for an owner/GM review meeting
- Correct industry terminology (plate cost, contribution margin, menu engineering matrix, price anchoring)
- Ready to use with minimal editing
- Saved to `outputs/` if the user confirms

## Example Output

### Example 1 — Single-unit neighborhood Italian, mid-quarter price-and-mix correction (Trattoria Liguria)

**Input:**
- Concept: Trattoria Liguria, single-unit neighborhood Italian, urban Bay Area, $2.8M AUV, 78 seats
- Audience: Owner-Chef Marco P. and GM Maria López, in-person 90-minute pricing review
- Trigger: 11 weeks of supplier-cost spike on beef (+6.2% on the CME index) and butter (+4.1% on Urner Barry); food cost drifted 30.4% → 32.7% (target 30.0%, hard ceiling 32.0%); prime cost 59.2% → 60.4% (target 59.0%)
- Sales mix data: 8 weeks, all 38 menu items, dollar-volume + portion-count + plate-cost recomputed on the latest Sysco invoices and the May spec sheet from the Liguria fresh-pasta program
- Constraints: house wine BTG locked through year-end (no movement); pasta menu print-cycle is monthly (next reprint 2026-06-15); no value-menu lock; Memorial Day weekend (2026-05-23 to 2026-05-25) is a confirmed +30% covers event
- Target margins: 28–30% food cost; 59% prime cost; contribution margin ≥ $18 on entrées
- Tone (from `config.yml` → `voice`): warm-neighborhood, chef-driven, no jargon to the front of the menu

**Risk-tier tag:** moderate (mid-quarter correction, not a full menu reprice).

---

#### Recap — Pricing Review, Trattoria Liguria, 2026-06-01 (owner/GM version, ~360 words):

**Purpose:** Pull food cost from 32.7% back to ≤30.5% by 2026-07-15 with a two-tier price change and a day-part pricing pilot, without disturbing the regulars or the $44 osso buco ceiling.

**Menu-engineering classification (after 8-week sales mix re-cut):**

| Class | Definition | Items (count) | Total contribution $ | % of total contribution |
|---|---|---|---|---|
| Stars (high CM, high pop.) | CM ≥ $18 + volume top 25% | Cacio e pepe; Mushroom risotto; Branzino al sale; Margherita pizza | 4 | $44,800 / 8 wk | 41% |
| Plowhorses (low CM, high pop.) | CM < $14 + volume top 25% | Osso buco; Ribeye 14oz; Butter-poached lobster; Beef carpaccio | 4 | $19,200 / 8 wk | 18% |
| Puzzles (high CM, low pop.) | CM ≥ $18 + volume bottom 30% | Lamb ragù pappardelle; Whole grilled orata; Tasting flight | 3 | $12,400 / 8 wk | 11% |
| Dogs (low CM, low pop.) | CM < $14 + volume bottom 30% | Caesar (out of category); Tiramisu (margin compressed by mascarpone +8%); Veal piccata; Eggplant parm | 4 | $7,300 / 8 wk | 7% |

**Tier 1 — Immediate margin recovery (effective 2026-06-08, posted at the host stand for one week before the menu reprint):**

| Item | Current | Proposed | Δ | Plate cost | New CM | Mix sensitivity | Rationale |
|---|---|---|---|---|---|---|---|
| Osso buco | $44 | $46 | +4.5% | $14.10 | $26.80 → $28.80 | Low — Plowhorse, regulars order it for occasions | Beef + saffron passthrough; menu reprint will move the item up the entrée list (anchor on $46) |
| Ribeye 14oz | $58 | $62 | +6.9% | $19.40 | $33.60 → $37.60 | Low — steak guests already expect the May CME move | Commodity passthrough; pair with the new $4-add red-wine-reduction modifier (60% margin) |
| Butter-poached lobster | $48 | $51 | +6.3% | $16.20 | $26.40 → $29.40 | Low — special-occasion order; price-elasticity narrow band | Lobster + butter passthrough; menu copy will be updated to flag "1.25 lb cold-water tail" |
| Beef carpaccio (app) | $19 | $21 | +10.5% | $5.80 | $9.20 → $11.20 | Medium — guests may compare to the burrata app ($16) | Re-anchor the app section with the burrata at $17 (–$2 to $14 plate cost still keeps $3 of margin) and the carpaccio at $21; the $7 spread is intentional menu engineering |

**Tier 2 — Next-cycle adjustments at the 2026-06-15 reprint (decided here, no posting until reprint):**

| Item | Current | Proposed | Δ | Rationale |
|---|---|---|---|---|
| Cacio e pepe | $24 | $26 | +8.3% | Star — testing whether the price-elasticity band lets us pull contribution $ up by re-anchoring the pasta column |
| Mushroom risotto | $26 | $28 | +7.7% | Star — same logic; the porcini commodity move is real (+5% MoM) |
| Branzino al sale | $44 | $46 | +4.5% | Star — moves to match osso buco; the table-side presentation is the value lever |

**Tier 3 — Hold steady (no change):**
- All Puzzles (lamb ragù, orata, tasting flight) — popularity is the lever, not price. Action: Maria adds a "from-the-chef" handwrite slip at the host stand on Friday + Saturday nights to push the lamb ragù.
- Caesar, tiramisu, veal piccata, eggplant parm (Dogs) — slated for the 2026-09-01 menu rewrite. No price change masks a portion problem on the tiramisu.

**Day-part & event pricing (NEW this cycle):**

| Day-part | Tactic | Mechanism | Projected lift |
|---|---|---|---|
| Tuesday "industry night" (5:00–10:00 PM) | $25 off any bottle ≥ $80 (max 2/table); house-pasta plate +$6 wine add | Industry guest book at the bar; not posted publicly | +12 covers/Tuesday at +$45 average ticket lift = +$540/wk |
| Sunday family-style platter (4:00–9:00 PM) | $98 for a 4-person Sunday-supper platter (lasagne + meatballs + roasted vegetables + Caesar + tiramisu); locks the table | New menu insert printed 2026-06-15 | +8 family covers/Sunday at $98/4 = +$200/wk and turns a Dog (tiramisu) into a bundled cost-of-goods |
| Memorial Day weekend (2026-05-23 to 2026-05-25) — already booked at +30% | NO entrée price surcharge (regulars notice). Run a $14 "Memorial Day spritz" cocktail (Aperol + house-batched bitters + Prosecco, plate cost $2.40) as the margin lever | BTG list addendum; bar-side push | +$1,800 contribution over the weekend at 200 cocktails sold |

**Presentation tactics for the 2026-06-15 reprint:**
- Anchor the entrée column with the **$62 ribeye** as the top-of-list, then **$58 lobster**, then the **$46 osso buco / $46 branzino** pair, then the $40-tier pasta column. Top-of-list price compresses the rest.
- Drop the dollar signs (already in spec); right-align prices in a column with consistent typography (subtle, but the eye reads prices less when they're tucked).
- Move the **$24 → $26 cacio e pepe** to the second pasta slot (the most-read pasta position after the Star slot, per the menu-engineering eye-track literature).
- Add a **"chef's daily"** line at the bottom of the entrée column ($ MP) as a soft cap — guests anchor on the printed prices instead of the verbal one.

**Impact projection (steady-state run-rate, 4 weeks out):**

| Metric | Today | After Tier 1 | After Tier 1+2 | After Tier 1+2 + day-part |
|---|---|---|---|---|
| Food cost % | 32.7% | 31.4% | 30.6% | 30.3% |
| Prime cost % | 60.4% | 59.6% | 59.0% | 58.7% |
| Weekly contribution $ | $66,400 | $68,900 (+$2,500) | $70,800 (+$4,400) | $72,000 (+$5,600) |
| Per-cover contribution $ | $21.30 | $22.10 | $22.70 | $23.10 |
| Sensitivity band (–10% mix on Plowhorses) | — | $68,000 | $69,800 | $71,000 |
| Sensitivity band (–15% mix on Tier 2 Stars) | — | — | $69,400 | $70,600 |

**Action items table:**

| Action | Owner | Due | Definition of done |
|---|---|---|---|
| Tier 1 price posting at host stand (4 items) | Maria | 2026-06-08 | Single-page printed insert; staff briefed at pre-shift Sunday |
| Update POS price (Toast — 4 items) | Maria | 2026-06-08 EOD | Toast item-master updated; first-shift smoke-test passes |
| Burrata app re-spec (plate cost $5.80 → $5.20 by trimming the prosciutto garnish from 0.6 oz to 0.4 oz) | Chef Reyes | 2026-06-10 | Spec card updated; AM/PM cooks pass portion check |
| Menu reprint with Tier 2 + presentation tactics + day-part inserts | Maria + designer | 2026-06-15 | New menu in service Friday dinner 2026-06-19 |
| Tuesday industry-night soft launch | Sam (bar) | 2026-06-09 | Industry guest book at the bar; first Tuesday review with Maria |
| Sunday family-style platter test | Reyes + Maria | 2026-06-22 | First Sunday service; covers + contribution $ logged |
| 4-week impact review | Maria | 2026-07-06 | Food cost % vs. projection; sensitivity bands checked |

**Risks / blockers:**
- If beef futures keep moving (Cattle Buyers Weekly trending +0.30 / lb on the front month), the ribeye and carpaccio passthroughs eat through the lift in 6–8 weeks. Re-review at the 2026-07-06 4-week mark.
- The osso buco $46 ceiling becomes uncomfortable past $48; the next move would need to be a portion adjustment (currently 14oz braised shank) or a substitution (lamb shank). Decide at the 2026-09-01 menu rewrite, not earlier.
- The Sunday family-style platter $98 is anchored on a 4-person assumption; if average party size on Sunday skews to 5 (which the BookingMap data suggests for the Q3 youth-sports calendar), the platter underprices. Build the 5-person upcharge (+$22) into the order modifier.

**Confidentiality scrub:**
- Marco's wine-license renewal and lease conversation are in the GM-only confidential addendum, not in this pricing brief.

---

### Example 2 — 4-unit Atlanta Latin-Caribbean fast-casual, pre-World Cup 2026 surge pricing review (Brasa & Bahia)

**Input:**
- Concept: Brasa & Bahia, 4-unit (Midtown, Buckhead, Decatur, East Atlanta), $9.4M consolidated AUV, Latin-Caribbean fast-casual with a Brazilian churrasco anchor and Bahian seafood line; the same operator referenced in `operations/food-waste-reduction-planner.md` Example 4 and `_shared/email-drafter.md` Example 6
- Audience: Area-GM Maria Restrepo, Owner Carla Bahia, Chef-Partner Renato Brasa, CFO consultant; 2-hour quarterly pricing review (2026-06-01)
- Trigger: World Cup 2026 kickoff 2026-06-11 (10 days from this review); 11-match Atlanta-area schedule overlay anchored on the three Brazilian-team match days; R365 AI Dashboard prime-cost variance attribution at the SKU level via the 2026-05-15 R365 AI ↔ Sysco connector flagging Marfrig AAA picanha input-cost passthrough at +9.4% over the May contract, Sysco produce-program substitute for cilantro at +6%, and a Leblon cachaça allocation cap from the distributor through 2026-09-30
- Sales mix data: 8 weeks of consolidated 4-unit data plus the Buckhead pão de queijo Brazilian-fan pre-test on 2026-05-19 (NRA Show closing day) referenced in the food-waste planner; R365 AI item-master sync completed 2026-05-28 per the email-drafter Example 5 escalation outcome
- Constraints: alcohol-policy hard-block on dynamic pricing for the caipirinha during the World Cup window (TX-equivalent stance adopted as a multi-state policy floor for brand consistency after the Tres Banderas surge visibility); Florida 2026-07-01 service-charge transparency disclosure adopted as the house standard ahead of the FL effective date for cross-state brand consistency; multilingual menu compliance (EN + ES + PT printed cards human-reviewed per the Step 13 convention propagated from `sales/menu-description-writer.md` v1.3); 4-unit consolidated pricing (no per-unit variance to avoid the dispatch-team complaint Maria handled in Q1)
- Target margins: 28% food cost (4-unit blended); 58% prime cost; CM per cover ≥ $9.40
- Tone: clear, multilingual-aware, no surge-pricing language to the guest

**Risk-tier tag:** high (4-unit, public-event-window, multilingual, regulatory crosswind). Owner sign-off required on every published price change.

---

#### Recap — Brasa & Bahia 4-Unit Pricing Review, 2026-06-01 (owner/area-GM version, ~420 words):

**Purpose:** Lock the pre-World Cup 2026 pricing posture for the 6-week window (2026-06-11 to 2026-07-19) with surgical passthroughs on the picanha line, a three-tier event surcharge stance, NO alcohol surge on the caipirinha, full multilingual menu compliance, and an R365 AI Dashboard alert threshold at prime-cost variance +1.5 pt as the mid-window re-review trigger.

**R365 AI Dashboard prime-cost variance baseline (8-week consolidated, 4 units, SKU-level attribution via the 2026-05-15 Sysco connector):**

| SKU class | Baseline cost | Current cost | Δ | Pricing action |
|---|---|---|---|---|
| Picanha AAA Marfrig (per lb landed) | $11.40 | $12.47 | +9.4% | PASSTHROUGH on the picanha plate (Tier 1) |
| Pão de queijo flour (50 lb sack) | $42.10 | $42.10 | 0% | HOLD |
| Black beans (#10 case) | $38.20 | $39.80 | +4.2% | ABSORB on the rice-and-beans side (high attach, low elasticity) |
| Cilantro (Sysco program substitute) | $1.20 / bunch | $1.27 | +5.8% | ABSORB (within tolerance) |
| Leblon cachaça (per liter) | $19.40 | $19.40 (allocation-capped through 2026-09-30) | 0% | HARD-BLOCK on caipirinha price increase (allocation issue, not cost) |
| Plantain (Sysco produce program) | $0.92 / lb | $0.95 | +3.3% | ABSORB |
| Tilapia (Bahian seafood line) | $4.80 / lb | $4.80 | 0% | HOLD |

**Tier 1 — Immediate passthrough (effective 2026-06-08, posted on the printed multilingual specials cards in EN + ES + PT at all 4 units):**

| Item | Current | Proposed | Δ | Plate cost | New CM | Multilingual menu copy review |
|---|---|---|---|---|---|---|
| Picanha plate (8 oz) | $19 | $21 | +10.5% | $6.10 → $6.65 | $12.90 → $14.35 | EN/ES/PT all reviewed; "picanha" stays untranslated per Step 13; the "Marfrig AAA cap-on" provenance line preserved across all three languages |
| Picanha sandwich (4 oz on pão de queijo) | $14 | $15 | +7.1% | $4.10 → $4.45 | $9.90 → $10.55 | EN/ES/PT all reviewed; "pão de queijo" stays untranslated; the bread-and-meat description holds in PT at 22 words per Step 13 |

**Tier 2 — Three-tier event surcharge logic (effective 2026-06-11 through 2026-07-19, posted at point-of-order and disclosed on receipts per the Florida 2026-07-01 transparency standard adopted as house policy across all 4 GA units):**

| Match-day class | Logic | Mechanism | Examples |
|---|---|---|---|
| Group-stage Brazilian-team match day | No alcohol surge. No signature-item surcharge. +$2 cover-min for tables of 6+ on the patio at Buckhead (the highest Brazilian-fan concentration unit per the 5/19 pre-test) | POS rule scoped to Buckhead patio; check footer discloses cover-min in EN + ES + PT | 2026-06-19 (Brazil vs. Mexico equivalent), 2026-06-24 (Brazil group-stage) |
| Knockout-round Brazilian-team match day | No alcohol surge. No signature-item surcharge. +$3 cover-min for tables of 6+ on the patio at Buckhead AND Midtown | POS rule scoped; check footer disclosure | If Brazil advances (TBD by 2026-07-03) |
| Non-LATAM team match day | Same as a regular Saturday. No surcharge. | None | 2026-06-15, 2026-06-22, 2026-07-01, etc. |

**Alcohol-policy hard-block (BRAND POLICY, not pricing — but reinforced here):**
- Caipirinha price held at $13 across all 4 units for the entire World Cup window. No surge, no allocation-pass-through, no day-part premium.
- Reason: TX-equivalent stance adopted as multi-state floor after Tres Banderas surge visibility (see `sales/digital-menu-optimization-brief.md` Example 2). Brand reputation in the Brazilian-fan zip codes is worth more than the $1 / drink upside.
- Allocation cap from Leblon (through 2026-09-30) is managed by Sam (bar manager) via portion control: 2 oz pour per drink, no exceptions; if a unit runs out, switch to the back-up Avuá cachaça (Pat the distributor has 6 cases on standby per the 2026-05-28 confirmation).

**Tier 3 — Hold steady (no change):**
- Pão de queijo basket ($9, Plowhorse — high attach, the operator's identity item)
- Vatapá (Bahian seafood stew, $17, Puzzle — popularity is the lever)
- Coxinha de jaca ($8 vegan app, Star — holding to defend the price-anchor at the lower end)
- Brigadeiro plate ($7 dessert, Dog — slated for re-spec at the 2026-09-01 menu rewrite)

**Day-part & event pricing (Brasa & Bahia 4-unit, World Cup window only):**

| Day-part | Tactic | Mechanism | Projected lift |
|---|---|---|---|
| Match-day pre-game (90 min before kickoff) | $35 "Brasa platter for 2" (picanha + pão de queijo + rice + black beans + sliced plantain) | New POS combo SKU; 4-unit synchronized; multilingual menu card EN + ES + PT | +18 platters per match-day per unit = +$2,520 / match-day across 4 units |
| Post-match (within 90 min of final whistle) | $9 pão de queijo basket bundled with $5 Guaraná Antarctica (normally $9 + $4 = $13; bundle $14, +$1 contribution and locks the table) | POS bundle SKU; multilingual line | +24 bundles per match-day per unit = +$96 / unit / match-day in contribution; the bundle's role is anti-walkout |
| Non-match-day Tuesday "Brazilian-night" (5:00–10:00 PM) | $25 off any bottle of Leblon-based cocktail flight (max 1/table) — adopted at Buckhead unit only as a 4-week test | Test scope-limited to Buckhead; review 2026-07-09 | +6 flights per Tuesday at Buckhead = +$150 / Tuesday in contribution |

**Multilingual menu compliance audit (EN + ES + PT, per Step 13 from `sales/menu-description-writer.md` v1.3):**

| Convention | Status | Owner |
|---|---|---|
| No machine translation; all PT + ES copy human-reviewed by Lucas (Midtown) and Beatriz (Buckhead) | DONE 2026-05-30 | Maria + Lucas + Beatriz |
| Proper-noun preservation: picanha, pão de queijo, vatapá, coxinha de jaca, brigadeiro, caipirinha, Leblon, Marfrig AAA, Avuá — NONE translated | DONE | Lucas |
| Spice-ladder vocabulary parity: "ardiente" (ES) and "ardente" (PT) hold the same heat-level position as "spicy" (EN) per the repo Step 13 convention | DONE | Beatriz |
| Florida 2026-07-01 service-charge transparency disclosure: 18% auto-grat on parties 6+ called out in EN + ES + PT on the printed multilingual menu card AND the receipt footer | DONE (adopted across all 4 GA units ahead of the FL date) | Maria |
| Word-count parity on signature items ±10% across all three languages | DONE | Lucas + Beatriz |
| Allergen-tag glossary (peanut-free, dairy-free, gluten-free) in EN + ES + PT consistent with the repo allergen-tag convention | DONE | Maria |

**R365 AI Dashboard alert thresholds (mid-window re-review triggers):**

| Threshold | Action |
|---|---|
| Prime-cost variance + 1.5 pt over the 4-unit blended baseline for 2 consecutive weeks | Trigger a mid-window pricing re-review; Maria + Renato + CFO |
| Picanha SKU cost > $13.50 / lb landed | Tier 1 picanha plate price re-review; consider second passthrough |
| Caipirinha allocation < 4 cases at any unit | Switch to Avuá at that unit; Sam owns; no price change |
| Cilantro program substitution gap > $1.50 / bunch | Revisit the Sysco produce program contract; Maria + Pat |

**Impact projection (steady-state, World Cup window 2026-06-11 to 2026-07-19, 4-unit consolidated):**

| Metric | Today | After Tier 1 | After Tier 1+2 surcharges + day-part | Sensitivity (–10% mix on Plowhorses) |
|---|---|---|---|---|
| Food cost % (4-unit blended) | 28.8% | 28.0% | 27.6% | 28.2% |
| Prime cost % (4-unit blended) | 58.4% | 57.8% | 57.4% | 58.0% |
| Weekly contribution $ (consolidated) | $108,000 | $112,500 (+$4,500) | $119,000 (+$11,000) | $116,200 |
| Per-cover contribution $ | $9.10 | $9.50 | $9.95 | $9.70 |

**Action items table:**

| Action | Owner | Due | Definition of done |
|---|---|---|---|
| Tier 1 picanha passthrough on multilingual specials cards (4 units) | Maria | 2026-06-08 | Cards printed, in service Wednesday |
| POS rule for group-stage Brazilian-team cover-min (Buckhead patio) | Maria + Toast | 2026-06-10 | Smoke-test passes; check footer discloses in EN+ES+PT |
| Brasa platter for 2 combo SKU (4 units) | Renato + Maria | 2026-06-10 | POS combo live; first-shift smoke-test |
| Caipirinha allocation hold-the-line briefing (4 units) | Sam | 2026-06-09 pre-shift | All bar staff briefed; Avuá backup confirmed |
| R365 AI alert thresholds configured (prime-cost variance + 1.5 pt) | Maria + Marc Cohen (R365 AI SA) | 2026-06-09 | Alerts live; first-week digest delivered |
| Multilingual menu card final review | Lucas + Beatriz | 2026-06-07 | Sign-off on all 4 units' cards |
| 2026-07-09 Buckhead Tuesday Brazilian-night 4-week review | Maria + Sam | 2026-07-09 | Decision on roll-out to other 3 units |
| Post-window lesson capture into 7/20 surge post-mortem | Maria + Renato | 2026-07-20 | Capture feeds the food-waste-reduction-planner Example 4 close-the-loop sequence |

**Risks / blockers:**
- If Brazil exits in the group stage, the knockout-round +$3 cover-min on the Buckhead/Midtown patio never triggers — the projection drops by ~$1,800 / week for the back half of the window. Sensitivity built into the projection.
- If the Marfrig AAA cost moves above $13.50 / lb landed, the picanha plate at $21 is squeezed; the second passthrough lever is portion (8 oz → 7 oz) before price. Renato has the spec on hand.
- If the Leblon allocation tightens (e.g., distributor cuts the 4-unit quota at any unit), Sam switches to Avuá at that unit only — no menu change, the caipirinha holds at $13.
- Florida 2026-07-01 service-charge transparency disclosure adopted as house standard now means the GA disclosure-line lives on the printed multilingual menu card and the receipt footer — if any unit's printer misfires, the front-of-house workaround is a printed disclosure-line card at the table.

**Confidentiality scrub:**
- 4-unit consolidated spend data, the specific Sysco DSR contract pricing, the R365 AI license tier, and the Leblon distributor allocation specifics are in the owner-only confidential addendum (Carla Bahia + CFO), not in this brief.

**Cross-skill handoffs:**
- This pricing review feeds the food-waste-reduction-planner Example 4 4-unit consolidated waste plan (the surge sell-first prioritization on the picanha line aligns with the Tier 1 passthrough)
- The email-drafter Example 6 World Cup catering inquiry template (trilingual PT primary) and Example 5 R365 AI ↔ Sysco onboarding escalation handle the upstream communications
- The meeting-summarizer Example 5 NRA Show 2026 vendor-QBR debrief documents the R365 AI + Crunchtime AI + Leanpath vendor-stack decisions that this pricing review implements
- The world-cup-2026-surge-playbook covers the broader surge-window operational posture this pricing review is a subset of

---

### Notes
- Both examples honor the same `config.yml` → `voice` convention (warm-neighborhood + chef-driven for Trattoria Liguria; clear + multilingual-aware for Brasa & Bahia) and the same `knowledge-base/terminology/` discipline (Star / Plowhorse / Puzzle / Dog classification; plate cost vs. contribution margin distinction; price anchoring; per-cover contribution as the operator-facing KPI).
- Tier 1 / Tier 2 / Tier 3 structure is the recommended skeleton for any mid-quarter or pre-event pricing review; Tier 1 is what changes within the week, Tier 2 waits for the next print cycle, Tier 3 holds.
- For multi-unit operators, the consolidated 4-unit projection plus per-unit sensitivity bands is the right format — single-unit-level projections invite per-unit price variance which the dispatch teams object to and which fractures the brand.
- The Florida 2026-07-01 service-charge transparency disclosure is adopted across all GA + multi-state units as a house standard ahead of the FL effective date — this is the cross-state regulatory consistency move the next-cycle `_shared/state-statute-map.md` helper will codify.
