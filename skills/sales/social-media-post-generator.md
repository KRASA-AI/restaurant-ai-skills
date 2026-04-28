---
name: "Social Media Post Generator"
category: sales
tools: [claude, chatgpt]
difficulty: beginner
time_saved: "~10 min/post"
version: 1.3
last_eval_score: 9.10
---

# 📸 Social Media Post Generator

## Purpose

Turn a content brief into a platform-native restaurant social post or short-form video script — Instagram (Feed, Reels, Stories, Broadcast Channels, Notes), TikTok (short-form + TikTok Shop / LIVE where eligible), YouTube Shorts, Facebook, Threads, Pinterest, LinkedIn — with tailored captions, hashtag strategy, CTAs, a 3-second visual hook, posting guidance aligned to 2026 algorithm behavior, compliant AI-disclosure and UGC-rights handling, and built-in A/B variants — all in the house voice, so the marketing lead, GM, or owner can post without rewriting.

## When to Use

Run this skill when building a weekly content calendar, promoting a menu launch or LTO, capturing a news-peg moment (award, press, James Beard nod), showcasing kitchen or staff culture, running an event / ticketed dinner / collab promotion, or capitalizing on a trending format (Reels with trending audio, TikTok narrative trend, Threads comment hook). Pair with AI Search Visibility Playbook (discovery through AI answer engines) and Menu Description Writer (canonical dish copy); this skill covers social discovery and conversion.

## Required Input

Provide the following:

1. **Content type and hook** — Dish feature, new menu or LTO drop, behind-the-scenes moment, staff spotlight, event or ticketed dinner, UGC repost, press or award, seasonal campaign, trending-format engagement (specific trend), news-peg (weather, local moment, holiday)
2. **Platform target** — Primary platform and secondary adaptations (IG Feed / Reels / Stories / Broadcast Channel / Notes, TikTok, TikTok Shop / LIVE, YouTube Shorts, Facebook, Threads, Pinterest, LinkedIn); note any platform the brand has explicitly deprioritized
3. **Subject details** — Exact dish name and canonical menu description, staff name/role and permission-to-post status, event date/time/price/ticket link, campaign theme, award or press citation with source link, LTO window
4. **Brand voice and positioning** — Warm-neighborhood, polished-upscale, chef-driven, playful-fast-casual, heritage / immigrant story, craft / natural-wine — pulled from `config.yml` → `voice`; aspirational vs. accessible posture
5. **Business context** — Restaurant name, cuisine, neighborhood, price tier, target audience, current follower tier (<10K, 10K–100K, 100K+), average engagement rate, whether the account is Meta Verified / TikTok Verified, whether the brand has LINK sticker / paid partnership label configured
6. **Visual assets** — Format (hero plated photo, casual phone photo, 9:16 short-form video, 1:1 square, 4:5 portrait, carousel), exact length for video (target 9–15s Reels, 15–30s TikTok narrative, 30–60s YouTube Short), lighting (natural / tungsten / mixed), audio availability (original vs. trending sound), talent release on any identifiable person
7. **Campaign goals** — Awareness, reservation bookings, online orders (with delivery-platform UTM or TikTok Shop link), retail / merch sales, event RSVP, follower growth, UGC collection, loyalty sign-up; specify the primary KPI so CTAs and asset choice align
8. **Posting timeline and context** — Desired posting day / time / frequency, seasonal calendar context, paired-post sequencing (teaser → reveal → UGC), blackout dates (e.g., food-safety-recall week for a peer), any sensitivity around recent news the post should not be read against
9. **Compliance and disclosure flags** — Whether any creative was AI-assisted (text, image, voice, or video generation), whether the post involves a paid partnership / creator payment / comped meal (required FTC / ASA paid-partnership label), whether alcohol is shown (platform and jurisdictional rules), whether a minor is on camera, whether any UGC is being reposted and the repost rights status (DM permission obtained, explicit hashtag license, on-site release signed)

## Instructions

You are a restaurant social media strategist who has shipped 10,000+ posts across Instagram, TikTok, and Threads for independent, multi-unit, and chain accounts, and who reads platform release notes weekly. Your captions sound native to the platform (not a press release), move reservations or orders (not just likes), and never embarrass the brand (no stolen audio, no undisclosed AI, no alcohol-to-minors risk).

**Before you start:**
- Load `config.yml` for brand voice, restricted phrases, locale, currency, menu canon, reservation link, delivery-platform UTMs, and the house signer for staff spotlights
- Reference `knowledge-base/terminology/` for dish names, cuisine vocabulary, and dietary-badge conventions; match the canonical copy from Menu Description Writer
- Pull the current platform landscape snapshot (Threads share of voice, IG Reels vs. Feed priority, TikTok Shop availability in the brand's country, YouTube Shorts monetization eligibility) — 2026 algorithm behavior drifts monthly
- Verify UGC rights status (hashtag license, DM permission screenshot, or talent release) before drafting a repost
- If the post involves AI-assisted creative, stage an explicit disclosure line compliant with the platform's AI-content label (IG / Facebook / TikTok all require it when applicable) and with FTC / ASA creator-endorsement rules

**Process:**

1. **Platform-native optimization** — Tailor every post to the platform's 2026 behavior: (a) Instagram — Reels-first for reach, carousels for save rate, Broadcast Channels for loyalty nurture, Notes for bar-seat / walk-in availability nudges, 3-5 hashtags in caption (hashtag volume no longer boosts reach); (b) TikTok — 3-second hook, trending sound (check the Creator Center daily), on-screen text, 15-30s narrative arcs outperform 60s, TikTok Shop product card if selling retail / gift cards in eligible markets; (c) YouTube Shorts — vertical, loop-closing ending, SEO-weighted title and description; (d) Facebook — event + community voice, longer captions, native video > YouTube link; (e) Threads — reply-bait / question format, 200-character sweet spot, light emoji, no hashtags except brand; (f) Pinterest — idea-pin or vertical image, SEO-weighted title; (g) LinkedIn — team / hiring / industry posts only.

2. **Hook strength evaluation** — Craft the 3-second visual + first-line hook that stops scroll: a contrarian hook ("Don't order our brisket"), a sensory verb ("Crack this open"), a number ("4am prep for one dish"), a news-peg ("Restaurant Week started — here's our five-course"), or a trend overlay. No generic "Check out our new dish." Test 2 hooks in the output so the marketer can pick.

3. **Dish feature posts** — Include plating visual direction, ingredient highlights with sourcing story (local farm, family recipe, technique), 2 flavor descriptors (umami, herbaceous, bright, smoky), price point and daypart, reservation or order CTA, and — if agentic-booking eligible — a schema-aligned caption so AI Search Visibility Playbook signals stay coherent with the post. Reuse the canonical dish description from Menu Description Writer.

4. **Behind-the-scenes content** — Show kitchen energy, prep ritual, supplier relationship, or menu development. Raw vertical video 9-15s with on-screen text. Talent release for any identifiable staff on camera. If a minor is in frame, mask or reshoot. Authentic > polished is the 2026 default, but authentic does not mean sloppy — steady-cam and readable text are non-negotiable.

5. **Staff spotlight strategy** — One spotlight per week per unit. Feature a role, name, tenure, signature dish, and one personal detail the staff member greenlit in writing. Signed release on file before posting. Use first person where possible (their words). This is the highest-retention content category for independents.

6. **Event promotion mechanics** — Announce with date/time/location, party size and price, booking mechanism (reservation platform deep link, Eventbrite, Resy Ticketed Events, OpenTable Experiences, Tock), attendee benefits, tier / sell-through urgency ("8 seats left"), and — if applicable — a Story countdown sticker + Broadcast Channel reminder. Post cadence: reveal → early-bird → final-call → thank-you.

7. **Hashtag strategy by platform (2026 reality)** — Instagram: 3–5 hashtags in caption (niche > popular; stop using 30 — it hasn't lifted reach since 2023 and now looks dated); TikTok: 3–5 hashtags, sound is the signal, not hashtags; Facebook: 0–2; Threads: 0, except one branded tag; LinkedIn: 3–5 industry tags; Pinterest: 5–10 SEO-weighted. Emphasize geo-tag over generic #foodporn.

8. **CTA phrasing and link strategy** — Platform-appropriate CTAs: IG — "Book in bio", "Save for Saturday", "Tag your brunch crew"; TikTok — "Link in bio" + a pinned comment with the link; Facebook — native event RSVP; Threads — reply-bait ("What's your order?"); YouTube Shorts — pinned comment with description link. Use UTMs on every link so reservation / order attribution flows back to Demand Forecast Briefing. Never bury a CTA past the fold.

9. **Timing and posting cadence** — Recommend optimal posting times by platform (e.g., IG Reels 5–7 PM local weekdays, TikTok 6–10 PM, Threads late-morning, LinkedIn Tue–Thu 7–9 AM) and frequency that respects each platform's native cadence (IG 3–5 posts/week, TikTok daily for growth, Threads 2–5/day is normal). Flag posting times that conflict with the brand's own dining rush (don't drop a Reel mid-Saturday-dinner — no one is watching and no one can answer a DM).

10. **Photo / video / short-form guidance** — Aspect ratios (9:16 Reels / TikTok / Shorts; 4:5 Feed; 1:1 legacy only), shot list (overhead hero, hands-in-frame, steam or pour moment, plating motion, reaction shot), lighting (natural window light for plated, tungsten for mood), audio direction (trending audio for TikTok with 5K–500K uses as the sweet spot — over-used sounds underperform), captioning for accessibility (87% of feed is sound-off).

11. **Caption copywriting (3 variants)** — Write 3 captions for A/B testing: (a) short snappy (50–90 characters, IG / Threads); (b) medium storytelling (90–220 characters, Facebook / IG Feed); (c) long-form narrative (300–600 characters when the story earns it, TikTok). Each variant has an explicit hook, one sensory line, one CTA. Emoji used sparingly — 1 or 2, never in place of words. Line breaks for readability on phone.

12. **Compliance, disclosure, and rights** — Add the required disclosure lines: AI-assisted creative ("Image generated with AI / Video edit AI-assisted") per platform label; paid partnership ("Paid partnership with @brand" triggers platform tag + FTC #ad); creator-meal disclosure (#ad / #gifted) if the post was comped; alcohol-shown posts follow platform alcohol rules (IG / TikTok age-gate, DRAM / ABC / ASA / ASA UK alcohol-ad codes); UGC repost only with documented rights (DM screenshot, hashtag license, on-site release). Flag any post that can't ship without owner or attorney sign-off.

13. **Performance metrics, attribution, and iteration** — Track by post: reach, saves (the 2026 ranking signal on IG), shares (the signal on TikTok), reply depth (Threads), link clicks, reservation / order conversions attributed by UTM, follower delta, comment sentiment. Set a kill-switch on hooks and formats that underperform 14-day baseline; rotate trending audio weekly. Feed reservation attribution back to Demand Forecast Briefing so marketing pulses on soft days are measurable.

**Output requirements:**
- Platform summary: primary platform, secondary adaptations, posting time with rationale, estimated engagement window
- 3 caption variants (short / medium / long) with hook, sensory line, CTA, emoji placement, line breaks
- Hashtag set tailored to 2026 norms (3–10 per platform as applicable), geo-tag, branded tag
- Visual / video direction: aspect ratio, shot list, lighting, audio choice with sound name, on-screen text, length
- CTA variants (2–3) for A/B testing with UTM-ready link template
- Posting guidance: day, time, frequency, cross-posting strategy, paired-post sequence
- Compliance disclosures: AI-assistance, paid partnership, comped, alcohol, UGC rights status
- Multi-platform adaptation with voice-consistent rewrites, not straight copies
- Content series suggestion: follow-up posts, Broadcast Channel / Story expansion, Threads reply thread
- KPI dashboard with reach, saves, shares, reply depth, link clicks, reservation / order conversions
- Kill-switch criteria for underperforming hooks and trending audios (14-day baseline rule)
- Ready-to-copy captions suitable for direct posting with minimal editing
- Correct terminology: Reels / Shorts / Stories / Broadcast / Notes, reach vs. impressions, saves as ranking signal, trending audio, UGC, paid partnership, hashtag license, geo-tag, CTA, UTM
- Saved to `outputs/` if the user confirms

## Related Skills

- `sales/ai-search-visibility-playbook.md` — Discovery through AI answer engines; social posts must signal the same brand facts the AI-search schema does
- `sales/menu-description-writer.md` — Canonical dish descriptions reused in dish-feature posts
- `sales/digital-menu-optimization-brief.md` — Aligns the dish-photo priority list with third-party-delivery storefront needs
- `operations/demand-forecast-briefing.md` — Consumes reservation / order attribution from UTM data; gets a marketing pulse on soft days
- `customer-service/review-response-drafter.md` — Handles the comment-section escalations a post occasionally surfaces

## Example Output

Three reference outputs spanning the platform / hook / disclosure spectrum — an Instagram-Reels-first dish-feature with three caption variants and A/B hooks, a TikTok event-promotion with TikTok Shop / Story countdown / multilingual layer, and a Threads + LinkedIn + Pinterest cross-platform award-press piece with FTC paid-partnership and AI-disclosure flags. Each is paste-ready into the brand's content calendar without further editing.

### Example 1 — Instagram Reels-first dish feature with A/B hooks

```markdown
## Post Brief — "Strawberry-Basil Lemonade" LTO Drop, Cedar & Vine
- **Content type:** Dish feature + LTO debut
- **Primary platform:** Instagram Reels (9:16, 12 sec)
- **Secondary adaptations:** IG Story (24h), TikTok (15s narrative), Threads (text bait), Facebook (event link)
- **Posting day / time:** Thursday 5:45 PM PT (Pacific dinner-rush teaser; pre-Friday peak)
- **Estimated engagement window:** 4–18 hr after post; Reels usually peaks at 14–24h on this account size

## Visual Direction
- **Format:** 9:16 Reels, 12 sec
- **Shot list:**
  1. (0–2s) Overhead pour shot: muddled basil + crushed ice, slow-mo stream of fresh-squeezed lemon juice hitting glass — HOOK FRAME
  2. (2–5s) Hands-in-frame: chef's hand placing strawberry coin on rim, light rotation
  3. (5–8s) Close-up condensation pull on glass, basil leaf floating, light catches the pink
  4. (8–11s) Customer reaction: 1.5s of someone sipping, eyes-close moment (talent release on file)
  5. (11–12s) Logo + brand-card: "$7 · This week only · Patio open"
- **Aspect ratio:** 9:16 (vertical, no letterboxing)
- **Lighting:** Natural window light, late-golden-hour 5:30 PM
- **Audio:** Trending IG audio "summer-hum-2026" (47K uses, sweet spot — over-used at >500K underperforms); muted dialogue, music-led
- **On-screen text:** "fresh-squeezed lemon · muddled basil · zero proof" (FDA-aligned terminology, NOT "mocktail" per house style)
- **Captioning for accessibility:** Hard-coded captions on the talent-reaction frame ("first sip energy")

## A/B Hook Test (2 variants — pick 1)
- **Hook A (sensory verb):** "Crack a basil leaf, then sip this." → 12-sec slow-pour
- **Hook B (contrarian):** "We don't make mocktails. We make this." → 12-sec slow-pour with same visuals

## Caption Variants (3 for A/B testing)
**Variant 1 — Short snappy (78 characters, IG Feed / Threads carry):**
> Strawberry-basil lemonade. $7. This week only. Book the patio. ✨🍓

**Variant 2 — Medium storytelling (188 characters, IG Feed default):**
> Fresh-squeezed lemon, muddled basil, ripe Driscoll's strawberries. Zero proof, all summer. Pouring this week only on the patio — bookable in bio. $7.
>
> 📍 218 N. Elm

**Variant 3 — Long narrative (412 characters, TikTok carry):**
> Sometimes the best drink on the menu is the one without alcohol. Fresh-squeezed lemon (we squeeze 80 lbs a week). Muddled basil from Maria's farm in Sebastopol. Driscoll's organic strawberries. A pinch of cane. Over crushed ice. $7. Zero proof. On the patio this week — bookable in bio.
>
> What's your order — Strawberry-Basil or the classic Lemonade?

## Hashtag Set (2026 norms — niche over popular)
- IG: #portlandeats #fortheloveofflemonade #patioseason #zeroproof #cedarandvine (5; geo + niche + branded)
- TikTok: #lemonade #patiovibes #pdxfood (3; sound is the signal)
- Threads: (no hashtags except #cedarandvine branded)

## CTA Variants (UTM-ready)
- "Book in bio" → resy.com/cedarvine?utm_source=ig&utm_medium=reels&utm_campaign=lemonade-lto
- "Save for Friday" (Reels save-rate is the 2026 ranking signal)
- Threads-specific: "What's your order — Strawberry-Basil or the classic?"

## Posting Cadence
- **Thursday 5:45 PM PT** — Reel A drops with Hook A
- **Friday 11:30 AM PT** — Story carry-forward (15-sec recut, Story-sticker poll: "Which one are you ordering tonight?")
- **Saturday 8:00 AM PT** — Reel B drops with Hook B (A/B test on hook only — same visuals, different first-line)
- **Monday** — Compile UGC reposts (only with DM permission screenshot on file) into a 3-frame carousel
- **Posting blackout:** Wednesday 6–9 PM (own dinner rush — no one's watching, no one can answer DMs)

## Compliance Disclosures
- **AI-assistance:** None. (No AI text or image generation used; native phone footage + chef's hands; if iPhone Cinematic-mode is used, no disclosure needed per Meta's 2026 guidance — that's hardware not generative AI)
- **Paid partnership:** None
- **Comped meal:** None
- **Alcohol shown:** None (zero-proof — no alcohol-rule trigger)
- **Talent release:** Customer reaction frame — release on file (signed 2026-04-22, retained 2 years)
- **UGC repost rights:** Monday carousel only after DM permission screenshot per repost

## Multi-Platform Adaptation
- **TikTok (15s narrative):** Same visuals + 3-second extra hook ("everyone's been asking about this drink"); use TikTok-native trending sound (different sound than IG); 3 hashtags; pinned-comment Resy link
- **Threads (200-char question hook):** "We're pouring strawberry-basil lemonade on the patio this week. What's your zero-proof order — fruit-led, herb-led, or just the classic lemonade?" → reply-bait works on Threads
- **YouTube Shorts:** Same vertical, +3 second loop-closing tail (basil-leaf drop into empty glass — invites the loop)
- **Facebook:** Native upload (do NOT cross-post YouTube link); medium-length caption; community voice

## Content Series Suggestion
- Tomorrow: Behind-the-scenes prep Reel — Maria's farm visit (build the supplier story)
- Next week: Customer's order video (UGC sourced)
- Mid-summer: 2nd LTO debut (Watermelon-Mint Cooler) — same template, refresh the trending audio

## KPI Dashboard (track 14 days post-post)
| Metric | Target | Baseline | Notes |
|---|---|---|---|
| Reach | 18K | 12K | Reel-first lift |
| Saves (2026 IG ranking signal) | 320 | 180 | Sensory hook drives saves |
| Shares | 90 | 50 | Friday DM-share spike |
| Reservations attributed (UTM) | 22 | 14 | Friday + Saturday peak |
| LTO sell-through | 40% of Strawberry-Basil pours by Sunday | n/a | Track in POS |
| Follower delta | +120 | +60 | Geo + niche hashtags |

## Kill-Switch (14-day baseline rule)
- If Hook A underperforms 14-day baseline reach by >30%, kill Hook A by Saturday 5 PM and switch the LTO promo to Hook B + a Story-poll redo
- If TikTok trending-audio underperforms by >40% in first 6 hr, swap to a different trending audio Saturday 12 AM
```

### Example 2 — TikTok event promotion with TikTok Shop, Story countdown, and multilingual layer

```markdown
## Post Brief — "World Cup Brazil-Match Watch Party" Ticketed Event, Cantina Verde Austin
- **Content type:** Event promotion (ticketed; 80 tickets at $35 incl. one bundle + drink)
- **Primary platform:** TikTok 25s narrative
- **Secondary adaptations:** IG Reels (15s), IG Story (countdown sticker), Resy Ticketed Events (deep link), Eventbrite (backup), TikTok LIVE (event night)
- **Posting day / time:** Wednesday 6:30 PM CT (Brazil-match Friday 8 PM CT — 50-hour runway)
- **Estimated engagement window:** Wednesday 7–11 PM peak; carry-forward Thursday morning Story

## Visual Direction
- **Format:** 9:16 vertical TikTok, 25 sec
- **Shot list:**
  1. (0–3s) Tight on plated chicken-wing tower with TV in background showing Brazil-team training b-roll (b-roll licensed via Storyblocks, NOT FIFA-rights footage — neutral footage only) — HOOK FRAME
  2. (3–7s) Quick-cut: 6 friends raising glasses, "BRASIL" written on a chalkboard above the marquee TV, server in canary-yellow polo
  3. (7–13s) Server (Lucas, PT-fluent) handing match-day bundle to a 4-top: "Aqui está, oito asas, dois pasteis, dois cervejas." (subtitles in English on-screen)
  4. (13–18s) Close-up bundle: 8 wings + 2 pasteis de queijo + 2 draft beers, $35 callout
  5. (18–22s) Crowd reaction at a goal moment (b-roll from prior watch party, talent release on file for the 3 identifiable faces)
  6. (22–25s) Card: "Friday 8 PM · 80 seats · Link in bio · #ad if applicable"
- **Aspect ratio:** 9:16
- **Lighting:** Mixed (TV glow + warm restaurant tungsten — intentional for the watch-party mood)
- **Audio:** Original audio (samba-inflected drum loop royalty-free; FIFA brand-protection rule = NEVER use the official FIFA anthem or any official tournament audio; check the Creator Center daily for compliant trending sounds — NEVER use a sound that could be tied to a FIFA/UEFA/CONMEBOL rights-holder)
- **On-screen text (EN + PT subtitles):** "Friday · 8 PM · Brazil-match watch · 80 seats · Reserva no link" (PT subtitle dated human-translated by Ana M., 2026-04-26 — file the dated translation log)

## Caption (TikTok long narrative, 480 chars)
> Friday 8 PM. We're pulling out 6 TVs to the patio for the Brazil match.
>
> 80 tickets. $35 = 8 wings + 2 pasteis + 2 drafts. Lucas (Brazilian, gente boa) is on the floor.
>
> Eu sei, you'd watch at home. Mas vem cá — a pasteis da nossa avó é melhor que tua avó (sorry). Brazilian fans get the marquee zone. Mexico fans get the patio. Everyone gets a seat.
>
> Link in bio · Reserva no link · 25% no-show charge so we know who's coming.
>
> #worldcupwatch #austin #pasteis (3 hashtags — sound is the signal on TikTok)

## CTA + Link Strategy
- TikTok: "Link in bio" + pinned comment with Resy Ticketed Events link
- Resy deep-link: resy.com/cantinaverde/events/wc-brazil-watch?utm_source=tiktok&utm_medium=video&utm_campaign=wc-brazil
- Backup: Eventbrite (if Resy hits the 80-cap, redirect)

## Multilingual Layer (per World Cup 2026 Surge Playbook precedent)
- **EN + PT** — primary
- **PT translation:** "Reserva no link · 25% taxa de não comparecimento · 80 lugares" — dated human-translator review by Ana M., translation log filed in `outputs/translations-log/2026-04-26-tiktok-wc-brasil.md`
- **Story carry-forward (next day):** ES version for Mexico-match watch-party Tuesday — same structure, same ES-translator flag

## Compliance Disclosures
- **AI-assistance:** None on visuals; the caption draft was AI-assisted (drafted by skill, edited by marketing lead) — Meta + TikTok 2026 rule does NOT require disclosure for human-edited AI-drafted text in non-creator-paid posts. Document the edit log in case challenged.
- **Paid partnership:** None — this is a brand-owned event
- **FIFA brand-protection:** Use neutral vocabulary ("the Tournament," "the Brazil match," "Big Match Friday") — NEVER use "FIFA," "World Cup official," or the official tournament logo / anthem. Franchise-counsel pre-cleared the caption 2026-04-26.
- **Alcohol shown:** Drafts visible — TikTok requires age-gate (set in the ad-account settings) AND no alcohol-to-minors framing (no minors visible in alcohol frames; double-checked the b-roll)
- **Service-charge transparency:** "25% no-show charge" is disclosed in the caption per FL service-charge transparency law analogue; TX is non-FL but we hold the same disclosure posture brand-wide (per the World Cup 2026 Surge Playbook posture)
- **Talent release:** 3 identifiable faces in the goal-celebration b-roll — releases on file (signed 2026-04-12, retained 2 years)

## Story Countdown Sticker
- Wednesday Story: countdown sticker set to "Friday 8 PM" — drives tap-throughs to the Resy link
- Daily reminder Story Thursday + Friday morning
- Friday 6 PM "60 minutes to kickoff" Story with "Final 12 seats" if applicable

## TikTok Shop / Live (event night)
- TikTok Shop product card on the post: "Cantina Verde · Brazil-Match Watch Party Ticket · $35" — only available in eligible markets (TX is eligible)
- TikTok LIVE Friday 8 PM: 30-min live stream from the patio at kickoff (FIFA brand-protection: do NOT live-stream the match feed itself — only the bar / crowd / food; the match is on the in-restaurant TVs, not on our live)

## Multi-Platform Adaptation
- **IG Reels (15s):** shorter cut of same footage, EN-only on-screen text, IG Feed primary; 5 hashtags including #austin and #futbol
- **IG Story (Wed–Fri):** countdown sticker + reservation link + daily progress shot
- **Threads:** "Brazil-match watch party Friday 8 PM. Who's bringing the chant book?" (200-char reply-bait)
- **Resy Ticketed Events:** event card with the bundle + pour list
- **Eventbrite (backup):** mirror Resy details

## KPI Dashboard
| Metric | Target | Baseline | Notes |
|---|---|---|---|
| Tickets sold (80 cap) | 80 | n/a | Sell-through is the headline KPI |
| TikTok views | 65K | 22K | Trending sample audio + multilingual hook |
| Resy clicks (UTM) | 480 | 150 | Friday peak |
| TikTok LIVE concurrent viewers | 800 peak | n/a | Match-night moment |
| Story carry-forward taps to Resy | 220 | 90 | Countdown sticker drives this |
| Multilingual reply-rate (PT comments) | 12% of comments in PT | <2% | Validates the multilingual layer |

## Kill-Switch
- If tickets sell <30 by Thursday 6 PM, drop a Friday-morning $25 happy-hour-bundle option (post a Story announcing the new tier) — protect the room fill
- If TikTok trending audio gets a takedown notice (rights-holder challenge), swap audio Friday 12 PM and re-cut

## Cross-handoff
- Lucas (PT-fluent server) is on Friday's pre-shift checklist (Shift Prep Checklist v1.2 Example 3) with PT auto-grat script
- Reservation grid configured per World Cup 2026 Surge Playbook (deposit on parties of 6+; 25% no-show charge)
- Post-event review post Saturday: highlight the 3-min crowd-reaction moment (UGC sourced + DM-permission)
```

### Example 3 — Cross-platform award-press post (Threads + LinkedIn + Pinterest + IG Broadcast Channel)

```markdown
## Post Brief — "James Beard Best Chef: West Semifinalist Nomination" Press Moment, Maison Sage
- **Content type:** Press / award news-peg
- **Primary platform:** Threads (text-native moment) + LinkedIn (industry recognition)
- **Secondary adaptations:** IG Story (24h hand-off) + IG Broadcast Channel (loyalty nurture) + Pinterest (SEO-weighted board pin)
- **Posting day / time:** Wednesday 7:15 AM PT (the morning the JBF list dropped — within 2 hr of announcement to ride the news cycle)
- **Estimated engagement window:** First 6 hr peak; LinkedIn carries through Thursday

## Threads Post (text-native, 196 characters, reply-bait)
> Chef Sage Liu was just named a James Beard Award Semifinalist for Best Chef: West.
>
> She'd want me to say this is a team award. So I'll say: thank you to every guest who pulled up a chair this year. 🌿
>
> Reservations live for May.

**Branded hashtag only:** #maisonsage (no other hashtags on Threads in 2026)
**Reply strategy:** Sage replies personally to first 30 comments; team logs which guest names appear (for VIP recognition)

## LinkedIn Post (industry voice, 612 characters)
> Maison Sage was named a 2026 James Beard Award Semifinalist for Best Chef: West this morning.
>
> Three things behind this:
>
> 1. A 14-person team that has not turned over in 14 months. Hospitality runs on retention.
> 2. A 4-farm produce-sourcing program (Cherry Lake Farms, Fifth Crow, Mountain Bounty, Swanton Berry) that gets a vote-of-the-week from the line cooks before the menu does.
> 3. A counter seat. The 6 counter seats at Maison Sage are the room's center of gravity. Every reservation is a conversation, not a transaction.
>
> The recognition belongs to every guest who pulled up a chair, every farmer who answered the 6 AM call, and every server who stayed on for one more pour.
>
> Reservations for May open Friday. Counter seats first.

**LinkedIn hashtags:** #jamesbeardfoundation #restaurantindustry #bayareadining #hospitality #cherrylakefarms (5 industry tags)

## Pinterest Pin (SEO-weighted, vertical 1000×1500)
- **Pin image:** Plated dish hero (signature beet-and-burrata course)
- **Pin title (SEO):** "James Beard Award Semifinalist 2026 — Maison Sage Berkeley | 4-farm tasting menu"
- **Pin description (SEO):** "Maison Sage in Berkeley CA was named a 2026 James Beard Award Semifinalist for Best Chef: West. 6 counter seats, 4-farm sourcing, 12-course tasting menu. Reservations for May open Friday at 10 AM PT. Berkeley fine dining."
- **Pinterest hashtags:** #berkeleyrestaurant #jamesbeardawards #finetastemenuU.S. #counterseating #beetburrata (5 SEO-weighted)
- **Board:** "Press & Recognition" (existing) and "Tasting Menu" (existing)

## IG Story (24-hour news-peg, 4 frames)
- Frame 1 (0–4s): JBF announcement screenshot with "We're a 2026 James Beard Best Chef West Semifinalist" overlay (LINK sticker → reservations)
- Frame 2 (4–10s): Sage in the kitchen, 8-sec hand-held, "Sage's first words: 'Tell the team.'" subtitle
- Frame 3 (10–17s): Team photo at lineup, 12 hands clinking water glasses (no alcohol per JBF release embargo discipline)
- Frame 4 (17–24s): "Reservations for May open Friday 10 AM PT" + Resy link sticker

## IG Broadcast Channel (loyalty nurture, 1 message to 4,200 channel members)
> Family —
>
> Sage was just named a 2026 James Beard Award Semifinalist for Best Chef: West. She wanted me to tell you this here first, before the public post.
>
> May reservations open to channel members 1 hour early — Friday 9 AM PT. Counter seats first.
>
> Thanks for everything you've done to put us on this list. — The team

## Compliance Disclosures
- **AI-assistance:** Caption was AI-assisted (drafted by skill, heavily edited by marketing lead + Sage personally) — no platform requires disclosure for human-edited AI-drafted text on non-creator-paid posts. Edit log retained.
- **Paid partnership:** None
- **Press / award accuracy:** JBF semifinalist list verified at jamesbeard.org/awards/semifinalists/2026 at 7:08 AM PT (announcement at 7:00 AM PT). Citation in the LinkedIn post.
- **Embargo:** JBF announcement embargo lifted at 7:00 AM PT — posting at 7:15 AM is within the announcement window
- **Talent release:** Sage's photo / quote — staff-spotlight release on file (signed at hire). Team photo — full-team release on file.
- **UGC repost rights:** None used in this post

## Posting Sequence
- 7:15 AM PT — Threads + LinkedIn drop simultaneously
- 7:25 AM PT — IG Story Frame 1 + IG Broadcast Channel message
- 11:00 AM PT — Pinterest Pin scheduled (peak Pinterest traffic)
- 12:30 PM PT — IG Story Frames 2–4 in sequence
- Friday 9:00 AM PT — Broadcast Channel "Reservations open in 1 hour" message
- Friday 10:00 AM PT — IG Story Frame: "Reservations live now" + Resy link
- Saturday — Reply digest (compile the reply-bait Threads + LinkedIn comments into a Sunday "thank you" post)

## Cross-handoff
- AI Search Visibility Playbook handoff: update brand schema on the website with the JBF semifinalist designation; submit to Google Knowledge Panel
- Review Response Drafter handoff: any review traffic next week should be flagged for a possible JBF-pegged thank-you reply; severity-gate stays normal
- Menu Description Writer handoff: signature beet-and-burrata course copy gets a "Featured by James Beard 2026" badge on the digital menu surfaces

## KPI Dashboard
| Metric | Target | Baseline | Notes |
|---|---|---|---|
| LinkedIn impressions | 24K | 6K | News-peg lift |
| LinkedIn comments | 80 | 18 | Industry-recognition tail |
| Threads replies | 200 | 35 | Sage's personal reply strategy |
| Pinterest saves | 140 | 40 | SEO long-tail value |
| IG Story link clicks (Resy) | 380 | 150 | LINK sticker on Frame 1 |
| Broadcast Channel open-rate | 78% | 65% | News-peg + family voice |
| May reservations booked Fri 9–11 AM PT | 80% of May counter-seat capacity | 60% | Loyalty-channel-first lift |
| Press inquiries (form submission) | 12 | 2 | News-peg amplifier |

## Kill-Switch
- If Threads thread devolves into a bad-faith comment wave (unlikely on award-news, but possible), Sage steps back from personal replies after 6 PM and the team responds with a single warm-thanks template
- If LinkedIn sees a rare bad-faith industry comment (e.g., a competitor sniping), no public response — log it, ignore, move on
```
