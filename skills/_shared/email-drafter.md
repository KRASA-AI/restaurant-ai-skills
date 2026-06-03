---
name: "Email Drafter"
category: _shared
tools: [claude, chatgpt]
difficulty: beginner
time_saved: "~10 min/email"
version: 1.4
last_eval_score: 9.20
---

# ✉️ Email Drafter (Restaurant)

## Purpose

Turn a few notes into a polished, on-brand restaurant email — vendor escalation, reservation handling, guest complaint follow-up, private-event proposal, staff memo, landlord/insurance letter, or media/PR outreach — matched to the recipient, the stakes, and the house voice, so the GM or owner can send without rewriting.

## When to Use

Use this skill for any outbound email that carries money, reputation, or operational risk: short-ship or quality credits with Sysco / US Foods / PFG / Shamrock / a specialty produce house; reservation move/cancel/large-party waivers via OpenTable, Resy, SevenRooms, or Tock; post-review private follow-ups moved off Google/Yelp/TripAdvisor; staff policy or schedule-change announcements; private-event proposals and BEO confirmations; landlord grease-trap and repair notices; insurance or health-department correspondence; influencer and press outreach; catering lead responses.

## Required Input

Provide the following:

1. **Scenario** — One of: vendor dispute, vendor QBR follow-up, reservation change/cancellation, VIP outreach, complaint follow-up (moved from review), staff memo, staff-discipline notice or performance action, landlord/property notice, insurance/claim letter, health-department correspondence, health-inspection corrective-action follow-up, private-event proposal, BEO confirmation, catering quote, PR/influencer outreach, press response, gift-card resolution, lost-and-found, bill dispute, collections on a house account
2. **Recipient** — Name, role (rep, guest, team, landlord, adjuster, inspector, reporter, influencer), relationship history (new, long-standing, rocky)
3. **Context / facts** — Dates, dollar amounts, invoice or reservation numbers, SKUs, guest names, dish or service specifics, what has already been said or offered
4. **Desired outcome** — Specific ask (credit dollar amount, policy waiver, meeting slot, written response, apology, silence with legal review, booking confirmation)
5. **Tone** — Warm-neighborhood, polished-upscale, chef-driven, playful-fast-casual, or legal-tight — pulled from `config.yml` → `voice` when available
6. **Constraints** — Platform length limits (OpenTable/Resy guest messaging caps), legal must-nots (no admission of fault on allergy/illness claims), confidentiality, who needs to be CC'd (owner, GM, attorney, broker, PR)
7. **Attachments and next-step** — Files to reference (invoice PDF, BEO, menu), deadline, follow-up if no reply

## Instructions

You are a restaurant GM's executive writer. You write like a hospitality operator, not a customer-service bot. Every email is specific, human, short enough to be read on a phone between shifts, and impossible to screenshot into a scandal.

**Before you start:**
- Load `config.yml` for restaurant name, GM and owner names, address, phone, email signatures, and brand voice
- Reference `knowledge-base/terminology/` for correct hospitality terms (cover, day-part, 86, VIP, comp, BEO, BOH, FOH, turn, service) and the canonical dish names exactly as printed on the menu
- If the email is downstream of another skill (Review Response Drafter handoff, Supplier Negotiation Brief action item, Shift Prep Checklist fallout), reference that output explicitly so the recipient sees we tracked it
- Never request sensitive personal data (CVV, SSN, full card numbers) by email

**Process:**

1. **Classify and route** — Identify the scenario type and its risk tier: routine (vendor thank-you, reservation move, lost-and-found), moderate (vendor credit, complaint follow-up, staff policy), high (allergy/illness, injury, legal threat, regulatory, press). High-tier drafts are holding-language only and must be flagged for owner/insurance/legal sign-off before send.

2. **Pick the frame** — One-line subject that tells the recipient exactly what the email is ("Credit request — PO 48231, short-ship 2026-04-09"; "Confirming your party of 8, 4/20 7:30"; "Following up on your Saturday visit"). Avoid vague subjects ("Quick question") on high-stakes emails.

3. **Open with the human** — First line acknowledges the recipient by name, references the shared context (last delivery, last visit, last conversation), and signals this is personal, not a template.

4. **State the ask in paragraph two** — Specific, quantified, actionable: dollar amount, dates, quantities, names. No buried leads. The recipient should know by line three what you want them to do.

5. **Give the minimum supporting detail** — Two or three facts that justify the ask: invoice numbers, time stamps, reservation IDs, photo references, POS receipt numbers. Attach evidence instead of transcribing it.

6. **Handle the emotional register** — For complaint follow-ups and staff messages, own the issue without over-apologizing; for vendor disputes, be firm without being hostile; for media/influencer notes, sound like a chef, not a press release; for legal/insurance, use defensive language ("to the best of our records," "we are continuing to investigate") and avoid admissions of fault.

7. **Compliance guardrails** — No admission of fault on allergy/illness/injury/discrimination issues without owner-or-attorney sign-off. No rate card, discount, or compensation offer in writing on a contested bill without GM approval. No confidential guest or staff PII beyond what is strictly necessary.

8. **Close with a specific next step** — A proposed call time, a confirmation deadline, an expected response window ("I'll plan on hearing back by Friday; otherwise I'll follow up Monday"). Never end with "let me know what you think."

9. **Signature block discipline** — Named sender with title, restaurant name, direct phone, address, and — only when appropriate — a warmth cue from brand voice. Never expose a personal mobile number on a legal or press email.

10. **Length target by scenario** —
    - Vendor dispute / quality complaint: 120–180 words
    - Reservation change / VIP confirm: 60–120 words
    - Complaint follow-up: 150–220 words
    - Staff memo: 120–200 words (one action, one deadline)
    - Private-event proposal: 220–350 words with a separate BEO attached
    - Press / influencer: 80–140 words — short, respectful, pitch the story not the deal
    - Legal / insurance: 100–150 words, neutral tone, attorney review flagged

11. **Non-English correspondence** — When the recipient's primary language is not English (common cases: a Spanish-speaking DSR or produce vendor, a Portuguese-speaking media contact, a French-speaking inspector in a bilingual jurisdiction):
    - Draft in the recipient's language. Keep dish names, menu terms, and the restaurant's brand name in their canonical form (do not translate brand names).
    - Short vendor and reservation emails (Scenarios 1 and 3): apply the same word-count targets; shorter is still better.
    - High-risk emails (allergy, legal, inspector): draft in both English AND the recipient's language; flag both for owner/counsel sign-off. The English version is the legal record.
    - Compliance note: if the email is a staff memo, check whether your state or city requires written notices in the employee's primary language (California, Illinois, New York City, and Washington require Spanish/bilingual notices for certain wage and safety notices).
    - For the World Cup 2026 surge period (June–July 2026), venues near host cities should prepare a short Spanish-language VIP outreach template for large reservation inquiries arriving via WhatsApp or Google Business Messages.

12. **Pre-send review** — Read aloud. Remove any sentence the owner would not want screenshotted. Remove hedges, remove thank-yous that sound hollow, spell-check every dish and vendor name, verify dollar amounts match the invoice, and verify the subject line still matches the final body.

**Output requirements:**
- Primary draft ready to send, with subject line, opener, ask, supporting facts, next step, and signature
- 1 alternate tone (warmer or firmer) when the scenario is ambiguous
- Recommended CC list with one-line rationale per addition
- Attachment checklist (invoice PDF, BEO, menu, photos) with file-name suggestion
- Risk-tier tag (routine / moderate / high) and sign-off requirement if high
- Follow-up reminder language if no reply within the stated window
- Private-channel handoff template when the email is replacing a public review reply
- Correct terminology consistent with `knowledge-base/terminology/`
- Saved to `outputs/` if the user confirms

### Example 4 — Health-inspection corrective-action staff memo (moderate risk)

**Input:**
- Scenario: staff memo — health-inspection corrective-action follow-up
- Recipient: all FOH and BOH staff at [Restaurant Name]
- Context: Routine unannounced inspection on 2026-05-08. Inspector cited two violations: (1) hand-washing station in the pantry station blocked by a speed rack — Risk Factor 3 (employee health and hygiene, corrected on site during inspection); (2) walk-in shelving unit holding cooked proteins at 41.5°F vs. 41°F hard limit — non-critical, requires correction within 10 days. No critical violations. Score: 88 (B). Re-inspection scheduled for 2026-05-18.
- Desired outcome: inform the full team of findings, confirm corrective actions taken, state the re-inspection date and expectations
- Tone: professional, direct, no alarm — this is a routine B score with minor findings
- Constraints: do not include the inspector's name or badge number in a distribution email; do not promise a score on re-inspection; CC owner and GM; this memo should be appropriate for a printed line-team version too
- Attachments: none — detailed report retained in GM office per house records policy

**Risk-tier tag:** moderate. GM may send. Owner CC required per house policy on all inspection communications.

**Subject:** Health inspection 5/8 — findings, corrective actions, re-inspection 5/18

**Primary draft (172 words):**

> Team,
>
> We had an unannounced health inspection on Thursday, May 8. Here's exactly what happened and what we've already fixed.
>
> **What was cited:**
>
> 1. **Hand-wash station blocked (pantry station)** — A speed rack was in front of the hand-wash sink. Fixed on the spot during inspection; the rack has a permanent new home on the dry-storage side of the station as of Thursday PM. This one lives on our pre-shift checklist starting tonight.
>
> 2. **Walk-in protein shelf temperature — 41.5°F vs. 41°F** — Non-critical. Reyes has ordered a replacement shelf liner and adjusted the thermostat setpoint; walk-in is reading 40.2°F as of this morning. We have 10 days to close this; it's already done.
>
> **Score: 88 (B).** Re-inspection: May 18.
>
> The standard for May 18 is exactly what it was before May 8: clean stations, clear sinks, and cold product in spec. Nothing changed — just a reminder that the inspectors can walk in any day.
>
> Maria López, GM

**Risk-tier tag:** moderate — no owner/attorney sign-off needed; GM may send.

**CC list:**
- Owner ([owner_name]) — required per house policy on all inspection communications
- Chef Reyes — named owner of the walk-in fix

**Compliance flags applied:**
- Inspector's name and badge number kept out of the distribution email (included only in the GM's confidential file copy)
- No score promise made for the re-inspection
- Corrective action language is factual and non-defensive

**Follow-up reminder:** "Team — re-inspection is Monday the 18th. Pre-shift station-check protocol goes out Sunday PM." (send as a brief verbal pre-shift reminder, not a second full email)

---

## Related Skills

- `customer-service/review-response-drafter.md` — Drafts the public reply this email often follows up on
- `admin/supplier-negotiation-brief.md` — Drives vendor-dispute, QBR, and contract emails
- `operations/shift-prep-checklist.md` — Source of context for staff memos and post-incident follow-ups

## Example Output

### Example 1 — Vendor short-ship credit request (moderate risk)

**Input:**
- Scenario: vendor dispute — short-ship + temperature-out-of-spec
- Recipient: Jordan Reyes, Sysco rep, 3-year relationship, generally responsive
- Context: PO 48231 delivered 2026-04-22 09:14. Ordered 4 cases #2 chicken thighs (40 lbs ea); received 3 cases. Pulled-pork case temp logged 47°F at receiving. Photos and temp log attached. Manager Chris Lee accepted under protest.
- Desired outcome: full credit on the missing chicken case (~$148.20 at contract price) and credit + replacement on the pulled-pork case (~$92.40); commitment to a fix on cold-chain handoff
- Tone: polished, firm, not hostile (long-standing relationship)
- Constraints: CC owner; do not threaten contract pull (that's the QBR conversation, not this email); attach invoice + temp log
- Attachments: PO_48231_invoice.pdf, temp_log_2026-04-22.csv, chicken_count_photo.jpg

**Risk-tier tag:** moderate. No owner / attorney sign-off needed; GM may send.

**Subject:** Credit + replacement — PO 48231 (short-ship + temp out of spec, 2026-04-22)

**Primary draft (152 words):**

> Jordan,
>
> Following up on this morning's delivery against PO 48231. Two issues we need to close out:
>
> 1. **Short-ship.** Ordered 4 cases of #2 chicken thighs (40 lb), received 3. Photo of the count and signed BOL attached. Requesting a full credit at contract price ($148.20).
> 2. **Temp out of spec.** The pulled-pork case logged 47°F at the back door at 09:14 (receiving log attached). Chris accepted under protest; we'll pull and discard per our HACCP plan. Requesting credit and a replacement case on tomorrow's truck ($92.40).
>
> No drama on either — I know the truck and the warehouse can have a rough morning — but I do want both line items resolved on this week's statement and a quick read on what shifted on the cold-chain handoff so we don't see it again.
>
> Plan on hearing back by Friday; otherwise I'll follow up Monday.
>
> Maria López
> General Manager, [Restaurant Name]
> Direct: 555-0142 | maria@[restaurant].com

**Alternate (firmer, 138 words):** Same structure with an explicit reference to last quarter's two short-ships and a request that Jordan loop in his ops manager on the cold-chain reply. Use this version if the soft ask doesn't land within 48 hours.

**CC list:**
- Owner ([owner_name]) — keep informed on temperature-out-of-spec incidents per house policy
- Chris Lee, Receiving Manager — he signed the BOL and will close the loop on the discard log

**Follow-up reminder:** "Jordan — circling back on PO 48231 credits. Statement closes Friday — can you confirm both line items will be on it?" (send Monday AM if no reply by Friday EOD)

---

### Example 2 — Allergy-incident follow-up (HIGH risk — holding language only)

**Input:**
- Scenario: complaint follow-up — guest reports allergic reaction after Saturday dinner; emailed the GM directly Monday morning
- Recipient: Sarah Khan, guest, party of 2, reservation 2026-04-19 19:30 (held under "Khan, 2")
- Context: Guest emailed at 09:14 saying she had a "severe peanut reaction" requiring an ER visit after eating the pad thai. Server ticket shows "no peanuts" was annotated. Kitchen ticket confirms no-peanut prep. Cross-contact possible — fryer, peanut oil-finish on the satay app at the next station, shared wok rotation.
- Desired outcome: open a documented investigation; do not admit fault; secure her contact info; route to insurance + attorney
- Tone: warm, concerned, careful — no admission of fault, no offer of compensation
- Constraints: HIGH risk — requires owner + insurance + counsel sign-off before send. Holding language only. CC counsel and owner. Do not offer compensation.

**Risk-tier tag:** HIGH — DO NOT SEND until counsel and the owner have reviewed and signed off. Insurance carrier (Cincinnati Insurance, claims line on file) must be notified before this goes out.

**Subject:** Following up on your Saturday visit — Sarah Khan

**Holding draft (128 words — for sign-off review only):**

> Sarah,
>
> Thank you for reaching out — I'm sorry to hear you weren't well after Saturday. Your safety and the safety of every guest who tells us about a food allergy is something we take seriously, and I want to make sure we look into your visit carefully.
>
> Could you share the time of your reservation, what you ordered, and the contact information for any medical care you received? I'm also asking our kitchen to walk back through the prep on every dish that left our line that night.
>
> I'd like to come back to you with what we find. To the best of our records right now, we are continuing to investigate.
>
> Maria López
> General Manager, [Restaurant Name]
> maria@[restaurant].com

**Compliance flags applied:**
- No admission of fault ("we are sorry this happened to you" — never; "I'm sorry to hear you weren't well" — acceptable)
- No medical claim or contradiction of her medical experience
- No comp / refund / gift card offer in writing pre-investigation
- "To the best of our records" + "continuing to investigate" defensive language
- Information request is fact-finding, not fault-disputing

**CC list:**
- Owner ([owner_name]) — required for any allergy / illness / injury communication
- Counsel ([counsel_name]) — required before send
- Insurance contact ([insurance_contact]) — notify of potential claim per policy

**Attachment checklist:** None — do not attach internal kitchen ticket or HACCP log to a guest in a potential-claim posture.

**Hold rule:** Do not send until (a) counsel approves the language, (b) the owner approves the send, and (c) the insurance carrier has been notified. Phone Sarah only with counsel's approval and only on a recorded line per house policy.

---

### Example 3 — Reservation move (routine)

**Input:**
- Scenario: reservation change — VIP regular needs to move party of 6 from Friday 7:00 to Saturday 7:30; current booking is patio (preferred); Saturday patio is fully booked at 7:30
- Recipient: David Chen, guest, 4-year regular, runs the wine club
- Tone: warm-neighborhood
- Constraints: Resy guest-message length cap (~500 chars); do not promise a patio table we can't deliver

**Risk-tier tag:** routine.

**Subject:** Saturday party of 6 — confirmed, with one note

**Primary draft (98 words):**

> David —
>
> Got you down for a party of 6 on Saturday at 7:30. Quick honest read: the patio is full at that time. Two options on our end:
>
> 1. **Patio at 8:00** — we can hold the corner four-top for you exactly as we usually do.
> 2. **Window two-top extension at 7:30** — same room, same view of the kitchen, slightly tighter footprint.
>
> Tell me which works and I'll lock it. Either way, see you Saturday.
>
> — Maria, GM

---

### Example 5 — R365 AI ↔ Sysco onboarding-conflict escalation (multi-unit, moderate risk)

**Input:**
- Scenario: vendor escalation — multi-unit operator (Brasa & Bahia, 4-unit Atlanta Latin-Caribbean fast-casual; the same operator referenced in `operations/food-waste-reduction-planner.md` Example 4) flagging a category-mapping conflict on three high-velocity SKUs between the R365 AI item master and the Sysco product catalog, ten business days after the 2026-05-15 R365 AI ↔ Sysco connector went live
- Recipient: Jordan Reyes, Sysco DSR, 3-year relationship (escalating the operator's CC list with R365 AI Solutions Architect Marc Cohen and Sysco ops manager Pat Singh)
- Context: 4-unit consolidated R365 AI Dashboard now reads from the Sysco connector; three SKUs are mis-mapping in a way that breaks SKU-level prime-cost variance attribution and downstream the food-waste-planner waste-station integration: (1) whole milk #2 — Sysco shows `WMILK-2GAL-PFG-1234` but the R365 AI item master expects the gallon-level mapping; (2) chicken breast jumbo — Sysco mapping rolls up two pack-sizes (4/5 lb + 8/10 lb) under the same parent SKU which collapses the cost-per-portion calc; (3) San Marzano D.O.P. tomato cases — Sysco product catalog rolled "San Marzano-style" cases into the same parent as the true D.O.P. case, so the operator's premium-protected SKU now misclassifies on the variance dashboard
- Desired outcome: joint clean-up session within 5 business days, named owners on both sides (Marc Cohen for R365 AI; Pat Singh for Sysco ops), written commitment that Sysco catalog-side mapping changes flow through to R365 AI consumer-side in the same 48-hour window the operator-side changes do, and a 2026-Q3 quarterly category-mapping audit schedule
- Tone: polished, firm, partnership-protective (long-standing Sysco relationship; do not push this to a contract-pull conversation in writing — that is the September QBR conversation)
- Constraints: CC Owner (Carla Bahia) + R365 AI SA (Marc Cohen) + Sysco ops manager (Pat Singh); do not name the operator's R365 AI license tier in the body (confidential); attach the three SKU-mapping screenshots; reference the 2026-05-28 R365 AI item-master sync that Marc Cohen ran on-site at Buckhead

**Risk-tier tag:** moderate. GM/area-GM may send with the CC list. No owner / attorney sign-off needed; the operator's R365 AI license tier stays in the owner-only confidential addendum, not in the email body.

**Subject:** R365 AI ↔ Sysco category-mapping clean-up — 3 SKUs, joint session this week (post 2026-05-15 connector)

**Primary draft (188 words):**

> Jordan, Pat, Marc —
>
> Quick coordination ask. Ten business days into the R365 AI ↔ Sysco connector live (2026-05-15) and our 4-unit dashboard is reading cleanly with one exception: three high-velocity SKUs are mis-mapping in a way that breaks the SKU-level prime-cost variance attribution we built the integration to deliver.
>
> The three SKUs:
>
> 1. **Whole milk #2** — Sysco SKU `WMILK-2GAL-PFG-1234` is rolling up under the gallon parent on the R365 AI side; we need the 2-gallon child mapping preserved so the per-portion cost calc holds on the coffee program at the Midtown unit.
> 2. **Chicken breast jumbo** — Sysco's parent SKU collapses the 4/5 lb and 8/10 lb pack-sizes under the same child; this breaks the cost-per-portion roll-up on the picanha-substitute item at the East Atlanta unit (where we run the smaller pack).
> 3. **San Marzano D.O.P. tomato cases** — the Sysco product catalog rolled the "San Marzano-style" case under the same parent as the true D.O.P. case. We need the D.O.P. case as a distinct child SKU; the variance dashboard currently misclassifies the premium-protected line.
>
> Two specific asks:
>
> (a) **Joint clean-up session this week** — 60 minutes, all four of us (Marc has the R365 AI side; Pat has the Sysco catalog side); Wednesday or Thursday afternoon works for me at Buckhead, or fully remote.
>
> (b) **Pipeline commitment in writing** — when Pat ships a Sysco catalog-side mapping change, the R365 AI consumer-side mapping flows through in the same 48-hour window the operator-side changes do. Marc's 2026-05-28 on-site sync at Buckhead handled the operator-side push but the Sysco catalog-to-R365 AI consumer-pull side is what is loose right now.
>
> I'd also like to anchor a 2026-Q3 quarterly category-mapping audit on the calendar (the R365 AI + Sysco product team + Brasa & Bahia inventory ops) — three weeks of lead time from now puts the first audit at the end of August. Plan on hearing back by Wednesday EOD; otherwise I'll follow up Thursday.
>
> Maria Restrepo
> Area General Manager, Brasa & Bahia (4 units, Atlanta)
> Direct: 678-555-0142 | maria@brasaandbahia.com

**Alternate (firmer, 162 words):** Same structure with an explicit reference that this is the second category-mapping incident since the 2026-05-15 go-live (first one was caught on the R365 AI side during Marc Cohen's 2026-05-27 on-site at Buckhead) and a request that Pat loop in his Sysco data-integrations product manager. Use this version if the soft ask doesn't land within 48 hours. Do NOT name the Brasa & Bahia R365 AI license tier in the firmer version either.

**CC list:**
- Owner Carla Bahia — required per house policy on any vendor escalation that names the integration partner
- R365 AI Solutions Architect Marc Cohen — joint clean-up requires him on the call; his 2026-05-28 on-site sync at Buckhead is the operator-side baseline
- Sysco ops manager Pat Singh — Pat owns the catalog-side mapping fix per the 2024 carryover from the Q4 2025 QBR

**Attachments:**
- `sysco_r365ai_mapping_3sku_screenshots_2026-05-31.pdf` (3 screenshots, one per SKU, showing the parent-child mis-mapping on each side)
- `brasa_bahia_4unit_sku_master_excerpt_2026-05-28.csv` (operator-side item master excerpt for the three SKUs)

**Compliance flags applied:**
- No naming of the operator's R365 AI license tier in the body
- No threat to pull the Sysco contract (escalation language reserved for the September QBR)
- The 4-unit consolidated dashboard data is not attached (confidential); only the 3-SKU excerpt
- The 2026-Q3 quarterly audit ask is positioned as preventive, not punitive
- Marc Cohen and Pat Singh are CC'd with explicit context, not blind-cc'd

**Follow-up reminder:** "Jordan / Pat — circling back on the 3-SKU clean-up. Can we lock Wednesday or Thursday for the joint session?" (send Thursday AM if no reply by Wednesday EOD)

---

### Example 6 — World Cup 2026 host-city catering inquiry, trilingual reply (HIGH-VALUE catering inquiry, moderate risk)

**Input:**
- Scenario: catering inquiry — large-party Brazilian-team match-day catering ask via WhatsApp on 2026-06-04
- Recipient: Beatriz Andrade (President, Brazilian-American Business Association of South Florida) writing on behalf of a 35-person business association watch-party for the Brazil group-stage match (equivalent 2026-06-19 evening)
- Restaurant: Tres Banderas, Miami/Wynwood premium-casual sports bar (same operator referenced in `sales/digital-menu-optimization-brief.md` Example 2) — 8 minutes from the Wynwood riverfront watch-party district, 6-week multilingual EN + ES + PT digital surge already live per the Step 13 convention
- Context: inquiry arrived in Portuguese ("Olá, gostaria de saber se podem nos receber para um almoço executivo de 35 pessoas no dia 19/06 às 14h, antes do jogo do Brasil..."); the operator's WhatsApp Business number is the multilingual intake channel; Beatriz's network of guests is largely PT-dominant with some ES + EN code-switchers; the BABA has booked Tres Banderas for three prior business lunches and is a 2-year relationship; the operator's caipirinha alcohol-policy hard-block (TX-equivalent stance adopted as multi-state floor — see `admin/dynamic-menu-pricing-advisor.md` Example 2) means caipirinha service via table-side cart only, no bottle-service
- Desired outcome: trilingual reply (PT primary, ES alternate, EN summary) that locks the 14:00 reservation, recommends on-site service over catering-pickup for the 25+ cover-count, clarifies the alcohol-policy stance up-front to avoid an awkward day-of conversation, attaches the catering menu PDFs in all three languages and the BEO draft, and discloses the Florida 2026-07-01 service-charge transparency convention (20% auto-grat) in all three languages
- Tone: warm, multilingual, hospitality-first; no machine translation; honor the operator's prior history with BABA
- Constraints: WhatsApp message-length convention (PT primary, then ES, then EN — keep each language readable as a single message rather than scrolled); attach the BEO and the catering menu in PT + ES + EN as PDFs; CC the Owner + Bar Manager Sam (who will brief the alcohol-policy on the 6/19 service team) + Lucas (PT-fluent server who will run point on the table) on the internal-confirmation email that follows the WhatsApp; no admission that the operator turned anyone else away for the slot

**Risk-tier tag:** moderate. Maria López (GM) may send the WhatsApp reply with the CC list on the internal-confirmation email; Owner Patrícia M. is CC'd per house policy on any catering inquiry > $2,500.

**WhatsApp reply (PT primary, 145 words):**

> Beatriz, que bom ter notícias suas! Sim, podemos receber a BABA para um almoço executivo no dia 19/06 às 14h — é antes do jogo do Brasil e o nosso espaço se encaixa perfeitamente para um grupo de 35.
>
> Para um grupo desse tamanho recomendamos serviço presencial (no salão privativo Mezzanine — Tres Banderas tem 38 lugares no Mezzanine, com TV para o jogo após o almoço), em vez de pedido para retirada. O Lucas — que você já conhece — vai cuidar do atendimento.
>
> Sobre a caipirinha: ela é feita à la carte com carrinho à mesa, dois oz por copo (Leblon premium); não trabalhamos com serviço de garrafa. As caipirinhas custam $13 cada e podem ser pedidas durante o almoço.
>
> Vou enviar o cardápio de catering em PT + ES + EN e o pré-BEO por e-mail em uma hora.
>
> Aviso de transparência: gorjeta automática de 20% se aplica para grupos de 6+ (padrão da casa adotado em todas as nossas unidades).
>
> Confirma o 19/06 às 14h para 35 e eu travo o Mezzanine.

**WhatsApp alternate (ES, 132 words) — sent as a follow-up message in the same thread for code-switching guests:**

> Beatriz, encantada de saber de ti. Sí, podemos recibir a la BABA para un almuerzo ejecutivo el 19/06 a las 14:00 — antes del partido de Brasil y nuestro espacio funciona perfectamente para 35 personas.
>
> Para un grupo de este tamaño recomendamos servicio en sala (en el Mezzanine privado de Tres Banderas, 38 cubiertos, con TV para el partido después del almuerzo) en lugar de catering para retirar. Lucas — a quien ya conoces — estará en la mesa.
>
> Sobre la caipirinha: la servimos a la carta con carrito de mesa, dos onzas por copa (Leblon premium); no trabajamos con servicio de botella. Las caipirinhas cuestan $13 cada una y se pueden pedir durante el almuerzo.
>
> Envío el menú de catering en PT + ES + EN y el pre-BEO por correo en una hora.
>
> Aviso de transparencia: propina automática del 20% aplica para grupos de 6+ (estándar de la casa adoptado en todas nuestras unidades).
>
> ¿Confirmas 19/06 a las 14:00 para 35 y bloqueo el Mezzanine?

**WhatsApp short EN summary (98 words) — sent as third message for the EN-dominant guests on the thread:**

> Beatriz — confirming for the EN folks on the thread: yes to a 35-person executive lunch Friday 6/19 at 2:00 PM, before the Brazil group-stage match. We recommend on-site service in our 38-seat private Mezzanine (TVs for the match after lunch) over catering pickup at this party size. Lucas will be your server. Caipirinhas are à-la-carte tableside via the cart at $13 / drink — no bottle service. 20% auto-grat on parties of 6+ per house policy. Sending the catering menu (PT/ES/EN) and the pre-BEO by email in an hour. Confirm and I'll lock the Mezzanine.

**Compliance flags applied:**
- No machine translation; PT primary version drafted by Lucas (PT-fluent server) review-pass against the operator's Step 13 multilingual convention; ES version reviewed by Andrea (ES-fluent floor staff at the Wynwood unit)
- Proper-noun preservation: "caipirinha," "Leblon," "Tres Banderas," "Mezzanine," "BABA" all kept untranslated across all three languages
- Word-count parity: PT 145 / ES 132 / EN 98 — within the ±15% target-language convention for a WhatsApp-length intake
- Alcohol-policy hard-block stated proactively in all three languages (cart-only, 2 oz, $13, no bottle-service) — Sam (bar manager) on the 6/19 service team gets the same script pre-shift
- Florida 2026-07-01 service-charge transparency disclosure (20% auto-grat on 6+) called out in all three languages — adopted as house standard ahead of the FL effective date for cross-unit brand consistency
- No mention that the operator turned anyone else away for the slot; no exclusivity language; no compensation offer for the booking

**Internal-confirmation email (sent immediately after the WhatsApp lock, EN-only for ops handoff, ~210 words):**

> Subject: BABA Mezzanine lock 6/19 14:00 — 35-cover Brazilian match-day lunch (multilingual service)
>
> Team —
>
> Locking the Mezzanine for the BABA 6/19 14:00 — 35 covers, 2-year relationship, Beatriz Andrade as primary contact. Service runs through approximately 16:00 (the match kickoff is 17:00 local).
>
> **Coverage:**
> - Lucas runs point at the table (PT-fluent; Beatriz's prior 3 bookings)
> - Andrea on floor backup (ES-fluent for the code-switch guests)
> - Sam at the bar (caipirinha cart service, 2 oz Leblon pours, allocation-conscious; if we run low, switch to Avuá — see Maria's 5/28 confirmation with Pat the distributor)
> - Pastry handles the after-lunch coffee + brigadeiro service for the match watch-party window
>
> **Policy disclosures already in the WhatsApp thread (sent 6/4):**
> - Caipirinha policy: cart-only, 2 oz, $13, no bottle-service
> - 20% auto-grat on parties 6+ per house standard
>
> **Attachments going out by email in the next hour:**
> - `tres_banderas_catering_menu_pt_2026-06.pdf`
> - `tres_banderas_catering_menu_es_2026-06.pdf`
> - `tres_banderas_catering_menu_en_2026-06.pdf`
> - `beo_baba_2026-06-19_v1_draft.pdf`
> - `alcohol_service_policy_one_pager_pt_es_en.pdf`
>
> **Internal cross-skill handoff:**
> - The 35-cover Brazil group-stage booking feeds the `operations/world-cup-2026-surge-playbook` Mezzanine surge protocol
> - The trilingual menu compliance follows `sales/menu-description-writer.md` Step 13
> - The Florida 2026-07-01 transparency convention adopted here matches the standard set in `admin/dynamic-menu-pricing-advisor.md` Example 2 and `sales/digital-menu-optimization-brief.md` Example 2
>
> Patrícia (Owner) is CC'd per house policy on the $2,500+ catering threshold.
>
> Maria López
> GM, Tres Banderas

**CC list on the internal-confirmation email:**
- Owner Patrícia M. — required per house policy on catering inquiries > $2,500
- Bar Manager Sam — alcohol-policy briefing for the 6/19 service team
- Lucas (PT-fluent server) — running point on the table
- Andrea (ES-fluent floor backup) — multilingual coverage
- Pastry lead — after-lunch coffee + brigadeiro service for the match watch-party window

**Follow-up reminder:** "Beatriz — confirming the menu PDFs and BEO landed in your inbox; let me know if there's anything to adjust before I send the calendar invite for the 19th." (send 2 hours after the WhatsApp lock if no reply)
