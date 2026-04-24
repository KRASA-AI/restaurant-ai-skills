---
name: "AI Search Visibility Playbook"
category: sales
tools: [claude, chatgpt]
difficulty: intermediate
time_saved: "~3-4 hr/location/quarter"
version: 1.0
last_eval_score: null
---

# 🔎 AI Search Visibility Playbook

## Purpose

Produce a location-specific playbook that makes a restaurant surfaceable, citable, and bookable by AI answer engines and agentic booking layers — Google AI Mode, ChatGPT Search, Gemini, Perplexity, Copilot, and reservation-partner agents (OpenTable, SevenRooms, TheFork, ResDiary, Resy, Mozrest, DesignMyNight, Foodhub, Dojo) — so the concept shows up as a recommended answer when a nearby guest asks an AI assistant for "a dog-friendly Italian spot in Shoreditch, Saturday at 7 for two" rather than relying on organic Google 10-blue-link traffic that is decaying. This is Generative Engine Optimization (GEO) / Answer Engine Optimization (AEO) tailored for restaurants.

## When to Use

Run this playbook when opening a new location, relaunching the website, noticing a drop in direct reservations, rolling out a new reservation partner, being asked "why don't we show up when I ask ChatGPT for brunch near me," before a major holiday booking window (Valentine's, Mother's Day, Restaurant Week), or any time the concept's positioning (cuisine, daypart, vibe, dietary specialty) materially changes. Pairs with Digital Menu Optimization Brief (which covers third-party delivery storefronts) and Social Media Post Generator (which covers social discovery); this skill covers AI-driven discovery and agentic booking flows.

**Scope note:** This playbook covers discovery, citation, and reservation-capture through AI answer engines. If the brand is shipping a first-party ordering app inside ChatGPT, Gemini, Claude, or Perplexity — or evaluating whether to allow a direct-ordering aggregator (e.g., Bites) to fulfill orders inside the assistant — use the Agentic Ordering App Readiness Brief instead. The two skills are complementary: this one gets the guest to ask for the restaurant; that one handles what happens when the guest asks to order.

## Required Input

Provide the following:

1. **Concept profile** — Cuisine, price tier, dayparts served, neighborhood, dietary specialties (gluten-free, halal, vegan), seating modes (bar, counter, patio, private dining), reservation policy (reservations vs. walk-in vs. hybrid), distinguishing features (wood fire, dog-friendly, live music, family-friendly, chef's counter)
2. **Reservation stack** — Booking provider(s) in use, whether they participate in Google AI Mode's 2026 restaurant-booking partners list (OpenTable, TheFork, SevenRooms, ResDiary, Mozrest, DesignMyNight, Foodhub, Dojo), inventory feed completeness (table types, party size ranges, special-event slots)
3. **Current web presence** — Website URL, CMS, menu format (HTML vs. PDF vs. image), Google Business Profile URL and completeness, Yelp/TripAdvisor/Zomato profiles, chef bio pages, press mentions, FAQ coverage
4. **Target questions** — Ten to thirty natural-language questions a guest would ask an AI assistant to end up at this restaurant (e.g., "best ramen in West Loop open late," "where can I take a vegan date in Austin under $60," "Italian restaurant with a private room for eight")
5. **Competitor set** — Two to five nearby restaurants already surfacing well in AI answers for the concept's key questions
6. **Content inventory** — Existing blog posts, event pages, tasting-menu write-ups, press features, awards, certifications (James Beard, Michelin, Bib Gourmand, Slow Food, SQF, MSC), and photography licensing status
7. **Market and locale** — Primary country and city, languages to support, currency, distance units, whether the concept serves multiple locations that should be disambiguated
8. **Objective for this run** — One of: lift share of AI-answer mentions for a target question set, capture reservations through Google AI Mode and partner agents, defend against a new competitor, recover from a branded-search decline, support a new location launch

## Instructions

You are an AI-search strategist who has published restaurant content that gets cited by ChatGPT, Gemini, Perplexity, and Google AI Overviews, and who understands how agentic booking layers read reservation inventory. Your job is to produce a concrete playbook for this one concept — not a generic "AI SEO tips" article.

**Before you start:**
- Load `config.yml` for brand voice, locale, concept rules, and banned claims
- Reference `knowledge-base/terminology/` for cuisine vocabulary and dietary-badge conventions
- If `Digital Menu Optimization Brief` has been run, reuse its per-channel menu structure so structured menu data stays consistent between delivery storefronts and the website
- If `Menu Description Writer` has been run, reuse its house-voice descriptions for the canonical menu source of truth
- Pull the target question list and competitor set before writing anything — do not default to "top 10 SEO tips"

**Process:**

1. **Audit AI answer share for the target question set** — For each of the guest's target questions, note who is currently being cited by ChatGPT, Gemini, Google AI Mode, and Perplexity (the named restaurants, the surfaces they were pulled from, and the phrases used). Capture whether the restaurant is mentioned at all, mentioned but not as the top pick, or missing. This is the baseline the rest of the plan closes.

2. **Reservation-feed readiness** — Confirm the concept is on at least one Google AI Mode partner (OpenTable, TheFork, SevenRooms, ResDiary, Mozrest, DesignMyNight, Foodhub, Dojo) and that the inventory feed exposes table types, party-size ranges, and special-event slots. Flag any partner whose feed is incomplete, stale, or missing the pricing or cuisine tags an AI agent would filter on. Recommend which partner to prioritize based on the concept's market coverage.

3. **Structured data and schema plan** — Specify the Restaurant, Menu, MenuItem, MenuSection, FAQPage, LocalBusiness, Event, and OpeningHoursSpecification schemas to add or fix. For each schema, name the fields that must be populated (cuisine, priceRange, acceptsReservations, servesCuisine, hasMenu, menuAddOn for modifiers, suitableForDiet, paymentAccepted). Highlight where the website currently uses PDF or image menus and must be converted to HTML for AI crawlers to parse.

4. **Canonical menu source of truth** — Require that one HTML page is the canonical menu, with category → item → description → dietary tags → price. Every third-party surface (delivery platforms, reservation platforms, GBP, aggregator profiles) must reconcile to this source. Cite the risk of AI-answer hallucinations when menus diverge across surfaces.

5. **FAQ and "answer-ready" content** — Draft 12 to 20 FAQ entries from the target question list, each written as a direct answer in 40 to 90 words with the concept's name, neighborhood, cuisine descriptor, and one differentiating fact in the first sentence. Publish with FAQPage schema. Separately, commission or outline three to five long-form answer pages for high-intent questions (private dining, dietary accommodation, late-night availability, tasting-menu booking, accessibility). Each page must open with a short extractive summary, then expand.

6. **Google Business Profile and map surfaces** — Prescribe the GBP fields that matter to AI answers: categories (primary and secondary), attributes (reservations, dog-friendly, outdoor seating, dietary options), service-area polygons, Q&A seeding with the target question set, weekly post cadence, menu URL, booking URL pointing to the agent-friendly partner. Mirror the critical fields on Yelp, TripAdvisor, Apple Maps Business Connect, Bing Places, and any locale-relevant aggregators.

7. **Citation-building content plan** — Identify three to five publications, podcasts, or list-style posts that AI answer engines repeatedly cite for this concept's question set (local food blogs, city-specific best-of lists, Eater maps, Michelin guide, Resy Hit List, Time Out, cuisine-specific publications). Prescribe the pitch angles, the assets to send (photos, chef bio, quote-worthy claim), and the target timeline. Distinguish earned citations from directory listings — agents weight them differently.

8. **Competitor-gap exploits** — For each target question where a competitor is currently cited and this concept is not, identify the specific asset that gets the competitor cited (a blog post, a Reddit thread, a Time Out mention, a structured menu). Name the counter-asset to produce — not to copy, but to provide the next-best answer to that question from this concept's angle.

9. **Agent-safe booking flow** — Confirm the booking path an AI agent can traverse end-to-end: deep link from AI answer → partner reservation widget → party-size + date + time prompt → confirmation email with structured data. Flag any booking friction an agent will abandon: mandatory account creation, captchas, multi-step upsells, unclear pricing, closed-loop "request" flows. Recommend the minimum-friction configuration.

10. **Measurement and reading plan** — Define the four metrics that close the loop: share of AI-answer mentions on the target question set (sample monthly), reservation volume attributed to AI answer engines and Google AI Mode deep links, share of website traffic flagged as AI-crawler or AI-referrer in the last 30 days, and branded-search volume trend. Specify the review cadence (monthly for the first quarter, quarterly afterward) and the owner.

## Output Format

A single playbook, ready to hand to marketing and web teams:

1. Executive summary — concept, target question set, baseline AI-answer share, objective
2. Reservation-feed readiness scorecard (by partner)
3. Structured data and schema plan (with field-level requirements)
4. Canonical menu source-of-truth specification and reconciliation targets
5. FAQ set (12–20 entries, answer-ready) plus long-form answer page outlines
6. Google Business Profile and map-surface checklist
7. Citation-building plan (target publications, angles, assets, timeline)
8. Competitor-gap exploits with counter-asset specs
9. Agent-safe booking flow audit with friction fixes
10. Measurement plan, review cadence, and owner

## Quality Checks

Before delivering, verify:
- Every recommendation ties to a named target question or a named AI answer surface
- The canonical HTML menu is named; PDF and image menus are flagged for conversion
- FAQ answers open with concept name, neighborhood, and cuisine in the first sentence
- Schema fields are enumerated at the attribute level, not just "add schema"
- At least one reservation partner on Google AI Mode's 2026 partner list is confirmed live with a clean feed
- Citation targets distinguish earned editorial mentions from paid directory listings
- Competitor-gap counter-assets are defensibly differentiated, not paraphrases
- Booking-flow audit names each friction point an AI agent would abandon on
- Measurement plan names both AI-answer share and reservation attribution — not just traffic
- No recommendation relies on keyword stuffing, cloaked content, or schema misuse (AI engines demote these faster than Google ever did)

## Related Skills

- `sales/digital-menu-optimization-brief.md` — Covers third-party delivery/marketplace menus; this skill covers AI-search and agentic booking; together they cover the digital surface end-to-end
- `sales/menu-description-writer.md` — Supplies canonical item copy that must match across surfaces
- `sales/social-media-post-generator.md` — Covers social discovery; complementary, not substitutable, because AI answer engines rarely cite social posts as primary answers
- `customer-service/ai-phone-agent-playbook.md` — Agent-safe booking flow integrates with the phone agent so AI-initiated inquiries can bounce between voice, web, and reservation-partner surfaces

## Notes on the 2026 AI Search Landscape

Google triggered AI Overviews on an increasing share of queries through 2025 and 2026; Google AI Mode expanded restaurant booking into multiple countries in April 2026 with OpenTable, TheFork, SevenRooms, ResDiary, Mozrest, DesignMyNight, Foodhub, and Dojo as reservation partners. An estimated one in five diners now uses an AI assistant (ChatGPT, Gemini, Perplexity, Copilot) to find a restaurant at least occasionally. Agents prefer structured, extractive answers to unstructured marketing copy. This skill treats the restaurant's web presence as an API for AI agents rather than a brochure for human readers — the human-facing design can and should still be beautiful, but the underlying data must be machine-parseable and reconciled across every surface the agents read.
