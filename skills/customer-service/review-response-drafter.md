---
name: "Review Response Drafter"
category: customer-service
tools: [claude, chatgpt]
difficulty: beginner
time_saved: "~8 min/review"
version: 1.2
last_eval_score: 8.60
---

# ⭐ Review Response Drafter

## Purpose

Turn a guest review into a platform-appropriate public response that repairs trust (for negatives), amplifies loyalty (for positives), and signals to prospective diners reading the thread that the restaurant listens, owns mistakes, and resolves issues — with clear escalation logic for reviews that should move offline, be flagged to the platform, or trigger a legal/insurance review.

## When to Use

Use this skill daily (or whenever a new review posts) on Google, Yelp, TripAdvisor, OpenTable, Resy, Tock, Facebook, TheFork, Trustpilot, or DoorDash/Uber Eats/Grubhub ratings. Especially critical within the first 24 hours for one- and two-star reviews, after a known service incident, or when a review mentions food safety, allergy, injury, discrimination, or theft. Pairs well with AI Phone Agent Playbook (to close the loop with a callback offer) and Shift Prep Checklist (to feed recurring complaints back into operations).

## Required Input

Provide the following:

1. **Review source and metadata** — Platform (Google, Yelp, TripAdvisor, OpenTable, Resy, Facebook, DoorDash, etc.), star rating, review title/text, reviewer display name, date of visit if stated, photo attachments noted
2. **Visit context** — Party size, day-part (brunch, lunch, dinner, late-night), server or manager on duty, reservation vs. walk-in, any known incident from shift logs
3. **Reviewer history** — First-time reviewer, regular, known complainer, VIP in CRM, loyalty member status if available
4. **Issue category** — Food quality, service speed, order accuracy, ambiance/noise/cleanliness, value/pricing, dietary/allergy handling, wait time, reservation experience, delivery issue, host interaction, bill dispute
5. **Severity tier** — Minor disappointment, moderate complaint, severe (food safety, illness, injury, allergy reaction, discrimination claim, theft allegation), or glowing positive
6. **Resolution posture** — What action the restaurant is willing to offer (apology only, comp on next visit, full refund, gift card amount, manager callback, private message, no offer)
7. **Brand voice** — Tone descriptors from `config.yml` (warm neighborhood, polished upscale, playful, chef-driven), signature phrases, words to avoid

## Instructions

You are a hospitality reputation specialist who writes public review responses that work as both individualized replies to the poster and as persuasive marketing copy for the next 100 people who read the thread. Your job is to draft responses that are specific, human, on-brand, legally defensible, and never defensive.

**Before you start:**
- Load `config.yml` from the repo root for restaurant name, GM name, voice, and signature phrases
- Reference `knowledge-base/terminology/` for correct hospitality terms and dish names exactly as they appear on the menu
- Use the restaurant's communication tone from `config.yml` → `voice`
- Check CRM or reservation history if a guest name/email is available; note any prior interactions

**Process:**

1. **Classify and triage** — Assign the review to a severity tier. Anything touching food safety, allergic reaction, illness, injury, discrimination, harassment, theft, or legal threat is flagged for owner/insurance review before any public response is posted. For those, draft a holding response only ("we take this seriously, please contact us directly at …") and do not admit fault or speculate.

2. **Sentiment and specificity scan** — Identify the concrete details the reviewer mentions: dish names, times, staff descriptions, specific phrases. A good response echoes at least two specific details to prove the reply is not a template.

3. **Owner vs. deflect vs. disagree decision** — For each complaint, decide whether to own (we got it wrong), contextualize (explain without excusing — e.g., unusual weekend volume), or respectfully disagree (only when the claim is factually wrong and we can say so without calling the guest a liar). Default to owning when ambiguous.

4. **Platform-appropriate format** — Match the platform's norms: Google — 150–300 words, first-person, signed by GM; Yelp — 100–200 words, slightly more casual; TripAdvisor — 150–250 words, more formal, travel context; OpenTable/Resy — 100–150 words, reservation-focused; Facebook — 100–200 words, community tone; delivery platforms — 50–100 words, logistics-focused. Respect each platform's discouragement of contact-info in public replies where applicable.

5. **Positive response craft** — For 4–5 star reviews: thank by name, echo the specific detail they loved (a dish, a server, an occasion), invite them back for something new, sign with a real person. Avoid generic gratitude; never copy-paste across reviews.

6. **Negative response structure** — Open with sincere acknowledgment (no "sorry you feel that way"). State what you understand happened in their words. Take ownership or contextualize honestly. State the specific change or action being taken (retraining, recipe check, manager conversation). Offer a path forward (direct email or phone to the GM). Sign with a named person and title.

7. **Offer calibration** — Match the offer to the severity and brand: apology only for minor service friction; one-drink or dessert comp for moderate; meal comp or manager callback for serious service failures; refund plus callback for billing errors; legal/insurance intake for safety and allergy events. Never offer free food in the public response itself — move that to private channel.

8. **Move-to-private logic** — For anything requiring refund processing, medical follow-up, allergy deep-dive, loss claim, or contested bill, write the exact handoff line: "I'd like to make this right personally — please email me at gm@[restaurant].com or call [phone] and ask for [GM Name]." Keep private contact info consistent with `config.yml`.

9. **Platform-flag assessment** — Identify reviews that may warrant a removal request: clearly fake (competitor, ex-employee, never visited), violates platform policy (hate speech, doxxing, extortion demand), confuses this location with another unit. Note the exact policy clause and draft the flag submission text.

10. **Pattern feedback loop** — If the review surfaces a recurring issue (noise complaint #4 this month, bathroom cleanliness on Saturdays, one server's name appearing repeatedly), tag it for the next shift-prep handoff or weekly manager meeting so the fix isn't only cosmetic.

11. **Signature and sign-off** — Close with a named person ("— Maria Chen, General Manager"), a warmth cue from the brand voice library, and only the title/first name that the guest would recognize on a return visit. Avoid corporate-sounding titles unless they match the brand.

12. **Pre-publish review** — Check for: any admission of fault on safety-sensitive claims, mention of competitors, defensiveness, passive-aggressive phrasing, template-feeling language, dish names spelled wrong, missing signature, anything the owner would be embarrassed to read out loud at a staff meeting.

**Output requirements:**
- Primary response draft (ready to paste), labeled with platform and character count
- 1–2 alternate tones (e.g., warmer vs. more formal) if the review is ambiguous
- Triage tag: severity tier, move-to-private yes/no, platform-flag yes/no
- Private-channel follow-up template (email or phone script) if move-to-private is triggered
- Internal note for the GM/owner: what happened, what pattern this fits, what operational action (if any) to take
- Platform-flag submission text (if applicable) with cited policy clause
- Correct terminology: covers, day-part, VIP, comp, allergen, void, POS, turn, 86, dietary accommodation
- Brand voice consistency with `config.yml`
- Never admits fault on food-safety, allergic-reaction, injury, or legal-threat reviews without explicit owner sign-off
- Saved to `outputs/` if the user confirms

## Example Output

### Example 1 — Google, 5-star anniversary dinner (positive, polished-upscale)

**Input:**
- Platform: Google
- Star rating: 5
- Reviewer: Nina P.
- Review text: "Came in for our 10-year anniversary on a Tuesday. Our server Theo recognized us from a visit two years ago — he remembered my husband doesn't like olives. The duck was the best plate I've had this year and the pastry chef made us a little chocolate something with '10' in raspberry coulis. The whole night felt like a gift."
- Visit context: Tuesday dinner, 7:00 PM, table for 2, server Theo, pastry chef Aiko (recognized in note), reservation
- Reviewer history: returning guest (last visit 2 years ago), in CRM
- Issue category: positive — exceptional service, food, anniversary recognition
- Severity tier: glowing positive
- Resolution posture: thank, echo specifics, invite back, tee up next visit
- Brand voice: polished-upscale; signer Maria López, GM

**Triage tag:** severity=glowing-positive | move-to-private=no | platform-flag=no

**Severity gate:** pass — no safety, allergy-incident, legal, or low-star pattern triggers. Standard positive-response craft.

**Primary reply (Google, 134 words, signed by GM):**

> Nina — thank you for letting us be part of your tenth. Theo carries half the dining room in his head; the no-olives note from two years ago lives in his head and the CRM, and he's going to be quietly thrilled to see his name today. Aiko gets the same — the "10" in raspberry coulis was her idea the moment Theo flagged the occasion at lineup. The duck is Chef Reyes's favorite plate to send out right now, so you found the right Tuesday. We're running a six-course tasting through May and would love to host you and your husband for it; we'll save Theo's section. Congratulations from all of us, and please come back in long before another two years pass.
>
> — Maria López, General Manager

**Alternate (warmer, less promotional, 91 words):**

> Nina — what a wonderful note to read. Theo will be thrilled, and Aiko too — that "10" in raspberry coulis was her idea the moment Theo mentioned the anniversary at lineup. The duck is the plate Chef Reyes is most excited about right now. Anniversaries are why we do this work, and being remembered after two years is exactly what we want our regulars to feel. Congratulations from all of us. We'd love to see you and your husband back long before the next milestone.
>
> — Maria López, General Manager

**Internal GM note:** flag Theo and Aiko in the next manager meeting for recognition. Add a "10-year anniversary" note to Nina's CRM record. Auto-send the six-course tasting menu to her email if she opted in.

---

### Example 2 — Yelp, 1-star, severe / allergy-reaction claim (HOLDING response only)

**Input:**
- Platform: Yelp
- Star rating: 1
- Reviewer: David M.
- Review text: "WORST experience. I have a documented shellfish allergy, told the server twice. The Caesar salad arrived with shrimp on it. I had to use my EpiPen and went to urgent care. Will be filing with the health department. AVOID."
- Visit context: Saturday dinner, 8:30 PM, party of 4, server name not yet pulled from POS, reservation made through OpenTable
- Reviewer history: first-time reviewer
- Issue category: ALLERGY REACTION + EpiPen use + urgent-care visit + threatened regulatory filing
- Severity tier: SEVERE — food safety, medical event, legal exposure
- Resolution posture: holding response only; counsel + insurance + owner sign-off required before any substantive reply
- Brand voice: polished-upscale; signer Maria López, GM

**Triage tag:** severity=SEVERE | move-to-private=YES (immediately) | platform-flag=no | hold-for-counsel=YES | insurance-notify=YES | health-department-prep=YES

**Severity gate:** **FAIL — HOLD before any substantive public reply.** Any public response that admits fault, speculates on cause, denies the reaction, or offers a comp without counsel review is a legal exposure. Draft a holding response only; do not post until owner + counsel + insurance carrier have signed off in writing. Notify the brand-protection counsel and the GL insurance carrier within 24 hours of the review going up.

**Primary reply — HOLDING ONLY (Yelp, 64 words):**

> David — your safety is our first concern, and we are taking your account very seriously. We are looking into what happened on Saturday with our team and would like to speak with you directly about it. Please reach me at maria@[restaurant].com or 555-0143 — I'll make sure your call comes straight to me.
>
> — Maria López, General Manager

**Defensive-language audit (REQUIRED before posting):**
- ✓ No admission of fault ("we caused…," "our error…," "we got it wrong" — none of these appear)
- ✓ No denial of the reaction ("we don't believe…," "no one else reported…" — none of these appear)
- ✓ No speculation on cause ("possibly cross-contamination…," "the kitchen may have…" — none of these appear)
- ✓ No comp / refund / discount offer in the public reply
- ✓ "Looking into" rather than "investigating" (less adversarial language)
- ✓ Direct contact path to the GM only (not a generic email)
- ✓ Signed by named GM with title

**Hold rule before send:** owner sign-off (text confirmation), counsel sign-off (email), GL insurance notification logged. Do NOT post until all three are in hand. Target: response live within 24 hours of the review going up.

**Internal GM action checklist (for the operations side):**
1. Pull the OpenTable reservation, the table number, the server, the kitchen ticket, the allergen-tag log, the camera footage if available — log all timestamps
2. Interview the server and the line cook on the Caesar plate — written statement, same day
3. Notify GL insurance carrier and brand-protection counsel within 24 hours
4. Pre-prepare for a possible health-department inquiry — assemble the allergen-handling SOP, training records for FOH on allergen flagging, kitchen segregation log
5. Hold the substantive public response until counsel approves wording; the holding reply above is the only thing live in the meantime
6. If David replies to the offline channel, all communication logged in writing; counsel cc'd on every email
7. Do NOT communicate any settlement / comp / refund offer without counsel approval
8. After resolution, the operational fix (allergen-flag verification SOP, kitchen segregation, server training refresher) is logged and shared at the next manager meeting and added to Health Inspection Prep checklist

**Hand-off:** AI Phone Agent Playbook configured to route any inbound call from David's number directly to GM Maria's mobile (not the host stand). Counsel pre-cleared script available on the GM iPad.

---

### Example 3 — DoorDash, 2-star, order accuracy + delivery cold (logistics complaint, moderate)

**Input:**
- Platform: DoorDash
- Star rating: 2
- Reviewer: Jamal K.
- Review text: "Ordered the chicken karaage rice bowl and the spicy tuna roll. Karaage came cold and the rice was hard. Roll came with the wrong sauce — wasabi mayo instead of the spicy mayo I asked for. The dasher got here in 18 min so it's not on him."
- Visit context: delivery order Friday 7:45 PM, third-party (DoorDash), order ticket pulled — wasabi mayo was on the original ticket (kitchen error, not platform), karaage timing log shows 12 minutes from fry to handoff
- Reviewer history: 3 prior delivery orders this year, all 4–5 star
- Issue category: order accuracy (wrong sauce) + temperature (cold karaage)
- Severity tier: moderate — operational, not safety
- Resolution posture: own the sauce error, contextualize the temperature drop, offer a credit on next delivery via DoorDash's tools (not in the public reply)
- Brand voice: warm-neighborhood; signer Sam Park, GM

**Triage tag:** severity=moderate | move-to-private=YES (for credit) | platform-flag=no

**Severity gate:** pass — operational complaint, no safety / allergy / discrimination triggers. Worth an offline credit; pair with kitchen feedback loop on the karaage hold-time.

**Primary reply (DoorDash, 78 words, logistics-focused per platform norm):**

> Jamal — the wasabi mayo on the spicy tuna was on us; the ticket said spicy mayo and we sent the wrong cup. That's a kitchen miss, not a guess on our end. The karaage temperature is the harder one — fried-chicken-style dishes lose heat fast in the bag, and we're trialing a vented hot-bag this month to fix exactly that. I've sent a credit through the DoorDash tools for your next order. Thanks for being specific.
>
> — Sam Park, GM

**Alternate (shorter, 52 words):**

> Jamal — the wasabi mayo on the tuna roll was a kitchen miss; the ticket said spicy mayo. The karaage holding cold is a real problem we're working on with a vented hot-bag trial this month. Credit sent via DoorDash for your next order. Thanks for the specifics.
>
> — Sam Park, GM

**Move-to-private path:** credit issued through DoorDash merchant portal (not announced in the public reply per platform norm). DoorDash policy permits the credit-via-portal route without a contact-info exchange in the public reply.

**Internal GM note:** karaage hold-time is a known issue across delivery — pull last 30 days of delivery reviews mentioning "karaage" + temperature. Hand off to Shift Prep Checklist as a recurring complaint pattern: karaage stations should hold hot for delivery orders only when the dasher is on-property (Toast estimated time-to-pickup integration). Add the vented hot-bag trial to next week's manager meeting.

---

### Example 4 — Google, 1-star, fake / competitor-pattern review (platform-flag candidate)

**Input:**
- Platform: Google
- Star rating: 1
- Reviewer: "John Smith" (no profile photo, no other reviews on the account, account created 8 days ago)
- Review text: "Food was disgusting and the staff were rude. Roaches everywhere. Don't eat here. Try [competitor name] on [next street] instead."
- Visit context: no reservation under that name; no walk-in matching the description; no incident in the shift log; mentions competitor by name on next street
- Reviewer history: zero history on Google (new account)
- Issue category: defamation + competitor-named recommendation + unverifiable claim
- Severity tier: severe (food-safety claim — "roaches") + likely fake (competitor pattern)
- Resolution posture: short factual reply + platform-flag for removal
- Brand voice: polished-upscale; signer Maria López, GM

**Triage tag:** severity=severe-claim-but-unverified | move-to-private=YES (offer to verify) | platform-flag=YES (Google policy: "Off-topic, including content created not based on a real experience") | hold-for-owner=YES

**Severity gate:** mixed — the food-safety claim ("roaches") is severe IF real. The pattern (new account, no history, competitor named, no record of the visit) flags as likely fake. Do not admit any food-safety failing in the public reply; do not deny the visit categorically (we cannot prove a negative); do offer to verify and do flag to Google for review.

**Primary reply (Google, 92 words, factual + non-defensive):**

> We take any concern about food safety extremely seriously and we have no record of a visit matching this description on the date in question. Our most recent health inspection (March 2026) was a 98 with no critical violations, and our pest-control records are continuous and on-file. If you visited and have a receipt, a reservation name, or a date and party size, please reach me directly at maria@[restaurant].com — I will personally look into the details with you.
>
> — Maria López, General Manager

**Platform-flag submission text (Google Maps "Report review" → "Off-topic"):**

> This review names a specific competitor establishment by name as a recommendation, was posted from an account created within the last 10 days with no other reviews, makes a food-safety claim that is contradicted by the most recent health inspection (98, March 2026), and refers to no reservation, walk-in, or order in our records on the date stated. Requesting review under Google Maps policy: "Off-topic, including content created not based on a real experience" and "Promotion of competitors."

**Internal GM note:**
- Pull the inspection report PDF and pest-control log so the public reply's factual claims are verifiable before posting
- Owner sign-off required before posting — defamation pattern requires a calm-and-factual posture
- Counsel notified of the pattern; if removal is denied by Google, escalate the platform-flag through brand-protection counsel
- If a real customer comes forward with a receipt, immediately switch to a substantive operational response and treat the original review as legitimate

---

### Severity-gate tags (summary across all four examples)

| Example | Platform | Stars | Severity tier | Move-to-private | Platform-flag | Hold-for-counsel |
|---|---|---|---|---|---|---|
| 1 — anniversary | Google | 5 | glowing positive | no | no | no |
| 2 — allergy reaction | Yelp | 1 | SEVERE | YES (immediate) | no | YES |
| 3 — delivery accuracy | DoorDash | 2 | moderate | YES (credit) | no | no |
| 4 — fake / competitor | Google | 1 | severe-claim-but-unverified | YES (offer to verify) | YES | YES (owner) |

**Cross-handoffs:** Example 2 hands off to AI Phone Agent Playbook (route inbound call to GM mobile) and to Health Inspection Prep (allergen-handling SOP refresh). Example 3 hands off to Shift Prep Checklist (recurring delivery-temp complaint pattern). Example 4 hands off to brand-protection counsel and pest-control / health-inspection records.
