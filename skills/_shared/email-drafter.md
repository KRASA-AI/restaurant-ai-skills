---
name: "Email Drafter"
category: _shared
tools: [claude, chatgpt]
difficulty: beginner
time_saved: "~10 min/email"
version: 1.2
last_eval_score: null
---

# ✉️ Email Drafter (Restaurant)

## Purpose

Turn a few notes into a polished, on-brand restaurant email — vendor escalation, reservation handling, guest complaint follow-up, private-event proposal, staff memo, landlord/insurance letter, or media/PR outreach — matched to the recipient, the stakes, and the house voice, so the GM or owner can send without rewriting.

## When to Use

Use this skill for any outbound email that carries money, reputation, or operational risk: short-ship or quality credits with Sysco / US Foods / PFG / Shamrock / a specialty produce house; reservation move/cancel/large-party waivers via OpenTable, Resy, SevenRooms, or Tock; post-review private follow-ups moved off Google/Yelp/TripAdvisor; staff policy or schedule-change announcements; private-event proposals and BEO confirmations; landlord grease-trap and repair notices; insurance or health-department correspondence; influencer and press outreach; catering lead responses.

## Required Input

Provide the following:

1. **Scenario** — One of: vendor dispute, vendor QBR follow-up, reservation change/cancellation, VIP outreach, complaint follow-up (moved from review), staff memo, landlord/property notice, insurance/claim letter, health-department correspondence, private-event proposal, BEO confirmation, catering quote, PR/influencer outreach, press response, gift-card resolution, lost-and-found, bill dispute, collections on a house account
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

11. **Pre-send review** — Read aloud. Remove any sentence the owner would not want screenshotted. Remove hedges, remove thank-yous that sound hollow, spell-check every dish and vendor name, verify dollar amounts match the invoice, and verify the subject line still matches the final body.

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
