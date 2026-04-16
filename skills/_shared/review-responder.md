---
name: "Review Responder (Quick Reply)"
category: _shared
tools: [claude, chatgpt]
difficulty: beginner
time_saved: "~3 min/review"
version: 1.1
last_eval_score: null
supersedes_note: "Use customer-service/review-response-drafter.md for severity-triaged, multi-platform, or high-risk reviews (allergy, injury, legal threat, 1-star patterns). This skill is intentionally the fast lane for the everyday majority."
---

# ⚡ Review Responder — Quick Reply

## Purpose

Draft a short, on-brand public reply to an everyday 3-to-5-star restaurant review in under three minutes — the fast lane for the 80% of reviews that are positive or mildly neutral — while explicitly routing anything sensitive (food safety, allergy, injury, discrimination, legal threat, repeat one-star, bill dispute, severe service failure) to the heavyweight `customer-service/review-response-drafter.md` skill instead.

## When to Use

Use this skill daily on the queue of incoming reviews from Google, Yelp, TripAdvisor, OpenTable, Resy, Tock, Facebook, Trustpilot, TheFork, and delivery platforms (DoorDash, Uber Eats, Grubhub) when the review is (a) 3 stars or above, (b) free of safety/legal/allergy content, and (c) not a repeat complaint from a known pattern. For anything else, stop and hand off to `customer-service/review-response-drafter.md` — do not shortcut severity triage.

## Required Input

Provide the following:

1. **Platform** — Google, Yelp, TripAdvisor, OpenTable, Resy, Facebook, delivery platform, or other
2. **Star rating** — 1 to 5
3. **Review text** — Full text the guest posted, plus reviewer display name and any photos they included
4. **Triage check** — Confirm the review is NOT about allergy, illness, injury, discrimination, harassment, theft, legal threat, or bill dispute. If ANY of those are present, stop and redirect to `customer-service/review-response-drafter.md`
5. **Specifics to echo** — Dish, server, occasion, or phrase from the review worth acknowledging
6. **Brand voice** — Warm-neighborhood, polished-upscale, chef-driven, playful — from `config.yml` → `voice`
7. **Signer** — Name and title of the person who will sign (typically GM or owner)

## Instructions

You are a hospitality reputation specialist writing fast, human, platform-appropriate replies. Speed matters, but never at the cost of sounding like a template. Every reply echoes at least one specific detail from the review, signs with a real person, and avoids clichés ("sorry you feel that way," "we strive for excellence," "thank you for your valuable feedback").

**Before you start:**
- Load `config.yml` for restaurant name, signer names, brand voice, signature phrases, and words to avoid
- Reference `knowledge-base/terminology/` for correct dish names, staff titles, and menu vocabulary

**Severity gate — do this first:**

Scan for any of these keywords or themes: allergy, allergic, reaction, ER, hospital, sick, illness, food poisoning, injury, fell, slipped, discrimination, racist, sexist, harassment, inappropriate, assault, theft, stolen, overcharged, fraud, lawsuit, attorney, lawyer, legal, report to health, sue. If ANY are present — or if the star rating is 1 or 2 and the review names a specific staff member or incident — STOP. Output a single line: "Severity gate triggered — redirect to `customer-service/review-response-drafter.md`." Do not draft a reply.

**Process (for qualifying reviews only):**

1. **Name, echo, thank** — Open with the reviewer's first name (if visible), echo one specific detail from the review (dish, server, occasion, phrase), and thank them in the voice of a real person, not a corporate account.

2. **Add warmth, not fluff** — One sentence that shows you read the review: a staff shout-out, a note about the dish's origin, a nod to the occasion (birthday, anniversary, first visit). No clichés, no superlatives, no "we strive."

3. **Invite them back with a specific hook** — Mention a new menu item, a seasonal LTO, brunch, a special night, or a dish they didn't try. Never offer a comp or discount in a public reply — that moves to private channel if needed.

4. **Sign with a person** — First name + title ("— Maria, GM"). Consistent with `config.yml` signer.

5. **Platform length targets** —
   - Google: 60–120 words
   - Yelp: 50–100 words (Yelp discourages contact info in public replies; omit email/phone)
   - TripAdvisor: 80–140 words (travel context — welcome them to the neighborhood)
   - OpenTable / Resy / Tock: 50–100 words (reservation-focused — mention next booking)
   - Facebook: 60–120 words (community-tone)
   - Delivery platforms: 30–70 words (logistics-focused — pickup window, packaging, next order)

6. **3-star nuance** — A 3-star review usually has one praise and one complaint. Acknowledge both honestly. If the complaint is minor (wait time on a Saturday, a loud table nearby), contextualize briefly without excusing. If the complaint is operational (order accuracy, temperature), move the specific follow-up offline with a single, short line pointing to gm@[restaurant].com.

7. **Pre-publish check** — Read aloud. Verify: reviewer's first name spelled right; dish names spelled exactly as on the menu; no "sorry you feel that way"; no generic gratitude; no comp or discount in public; no competitor mention; no defensiveness; one specific echo from the review; signed by a real person.

**Output requirements:**
- Primary reply (ready to paste), labeled with platform and word count
- 1 alternate tone (warmer or more concise) if the review is ambiguous
- Severity-gate tag: "pass" or "redirect to customer-service/review-response-drafter.md"
- If 3-star and the complaint deserves an offline follow-up, a short private-channel email draft (redirect to `_shared/email-drafter.md` for a longer version)
- Correct dish-name spelling and canonical staff titles
- Saved to `outputs/` if the user confirms

## Related Skills

- `customer-service/review-response-drafter.md` — Heavyweight drafter for severity-triaged, multi-platform, high-risk, and pattern reviews. Use this instead of the quick-reply path for anything flagged by the severity gate
- `customer-service/ai-phone-agent-playbook.md` — For converting an online review complaint into a callback handoff
- `_shared/email-drafter.md` — For the private-channel follow-up note to a 3-star reviewer whose issue needs offline resolution
- `operations/shift-prep-checklist.md` — When a review surfaces a recurring operational issue, route it here for the next pre-shift

## Example Output

> [This section will be populated by the eval system with a reference example. For now, run the skill with sample input to see output quality.]
