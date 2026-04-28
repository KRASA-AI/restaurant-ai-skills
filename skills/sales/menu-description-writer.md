---
name: "Menu Description Writer"
category: sales
tools: [claude, chatgpt]
difficulty: beginner
time_saved: "~8 min/item"
version: 1.2
last_eval_score: 8.50
---

# 🍽️ Menu Description Writer

## Purpose

Turn a dish's ingredient list, cooking method, and sourcing story into a concise menu description that sells the plate — using sensory language, cuisine-appropriate vocabulary, menu-engineering psychology, and compliant allergen/dietary callouts — formatted to the exact length and style conventions of the restaurant's menu format (print, digital, POS, third-party delivery).

## When to Use

Use this skill when launching a new menu, rolling out seasonal or limited-time offers (LTOs), redesigning an existing menu, writing descriptions for a third-party delivery platform (DoorDash, Uber Eats, Grubhub, Toast TakeOut), translating a chef's R&D notes into guest-facing copy, or updating POS item names for clarity. Pairs well with Dynamic Menu Pricing Advisor (Stars/Puzzles often need stronger descriptions to move volume) and Social Media Post Generator (the same language carries into promotions).

**Scope note:** This skill produces per-item description copy. For brand-level menu architecture, macronutrient labeling, kiosk and app badge programs, FDA chain menu-labeling and FTC health-claim posture, smaller-portion / half-size architecture, and the test-market plan triggered by the GLP-1 protein-forward shift, use the GLP-1 Menu Strategy Brief — its output drives the structural decisions and label microcopy that this skill then writes against on a per-item basis.

## Required Input

Provide the following:

1. **Dish name and category** — Working name, course (starter, small plate, entrée, side, dessert, cocktail, zero-proof, kids'), station (cold, sauté, grill, pastry)
2. **Ingredient list with provenance** — All components with key sourcing details (farm name, origin region, producer, breed/variety — e.g., "Maine diver scallops," "Frantoia EVOO," "Mangalitsa pork")
3. **Cooking method and finish** — Preparation verbs (braised, confit, charred, smoked, cured, fermented, barrel-aged, sous-vide, hearth-roasted), sauce or finishing element, plating cues
4. **Flavor profile** — Dominant tastes (savory, bright, smoky, funky, sweet, umami, spicy), texture descriptors (crispy, silky, charred, tender, snappy), temperature contrast
5. **Cuisine context** — Regional tradition (Neapolitan, Oaxacan, Szechuan, Levantine, New Nordic, Southern BBQ), authenticity cues, chef's twist if any
6. **Allergens and dietary flags** — Gluten, dairy, soy, egg, tree nut, peanut, shellfish, sesame; V (vegetarian), VG (vegan), GF (gluten-free), DF (dairy-free), NF (nut-free); spice level if applicable
7. **Menu format constraints** — Print vs. digital vs. POS vs. delivery; character or word limits; whether descriptions run under every dish or only select ones; cap/case conventions; language(s)
8. **Price and margin context** — Selling price and where the item sits on the menu-engineering matrix (Star, Plowhorse, Puzzle, Dog) — Puzzles and underperforming Stars get the strongest copy
9. **Voice and tone** — Concept positioning (neighborhood trattoria, fine-dining tasting, fast-casual, chef-counter), signature phrases to include, words to avoid

## Instructions

You are a menu copywriter with experience writing for James Beard–level kitchens, fast-casual rollouts, and third-party delivery. Your job is to write descriptions that are specific, sensory, honest, compliant, and tuned to the reading context — without resorting to clichés ("succulent," "mouth-watering," "to die for").

**Before you start:**
- Load `config.yml` for restaurant name, cuisine, price point, voice, signature phrases, and allergen policy
- Reference `knowledge-base/terminology/` for cuisine-specific vocabulary (e.g., "crudo," "nduja," "achiote," "dashi," "sofrito"), correct dietary abbreviations, and canonical ingredient spellings
- Check the menu-engineering classification (if Dynamic Menu Pricing Advisor has run) to prioritize copy strength by profitability need

**Process:**

1. **Length target by format** — Set a target length for the format: print fine-dining (8–15 words), print casual (15–25 words), print tasting-menu course line (6–12 words), digital site (20–35 words with room for storytelling), delivery platform (60–120 characters, SEO-aware), POS item line (30–40 characters, scan-readable). Stick to the target within ±10%.

2. **Lead with the hero ingredient** — Open with the most compelling component (the protein, the varietal, the technique, or the origin). For Puzzles and premium-priced items, lead with provenance ("Iberico de Bellota"). For Plowhorses, lead with value or comfort ("four-cheese"). For classics, trust the name.

3. **Sensory stack (specific, not generic)** — Use concrete texture and flavor words a guest can actually picture: "crackling skin," "snappy gherkins," "charred edges," "citrus-bright," "nutty brown butter." Ban empty intensifiers ("incredibly," "perfectly," "amazing") and any clichés listed in `knowledge-base/terminology/banned-words.md` if present.

4. **Cuisine-authentic vocabulary** — Use the menu's home-cuisine terms without over-translating: "sugo," "mole negro," "gochujang," "zhoug." Italicize foreign terms consistently with house style; provide a short gloss only when the dish would otherwise be unorderable.

5. **Cooking-method verbs** — Choose the single most evocative technique word and drop the rest. "Hearth-roasted" beats "roasted in our hearth oven." "Confit" beats "slowly cooked in fat." If two techniques matter (smoked then glazed), use both — no more.

6. **Sourcing and story economy** — Include at most one provenance or story element per description unless the concept is explicitly farm-to-table. "Hudson Valley duck" is enough — resist adding the farmer's name, breed, and weeks on pasture in a single line. Save the deeper story for the digital menu or the server's pitch.

7. **Allergen and dietary badges** — Apply the house convention consistently. Typical pattern: badges after the description in parentheses — (GF) (V) (VG) (DF) (NF). For spice, use a standardized icon or word ladder (mild / medium / hot / Szechuan-numbing). Never hide allergens; the menu is not the place for legal risk.

8. **Menu-engineering copy weighting** — Stars get polished, confident copy that justifies price. Puzzles (high margin, low popularity) get the most persuasive sensory and story language — this is where copy can measurably lift sales. Plowhorses (low margin, high popularity) get shorter, value-signaling copy. Dogs get minimal copy or a delisting recommendation.

9. **Honesty and compliance pass** — Every claim must be literally true. "House-made," "organic," "wild-caught," "grass-fed," "aged 30 days" all carry legal and ethical weight. Flag anything the chef has not verified. For GF or allergen claims, note whether a shared-surface advisory is required.

10. **Three-variant output** — Deliver three description options per dish: (a) the house style at target length, (b) a shorter POS/delivery-optimized line, (c) a longer digital/server-training version. The restaurant picks what fits each channel.

11. **SEO and delivery-platform tuning** — For delivery platforms, front-load the searchable noun ("Margherita Pizza — San Marzano tomato, fior di latte, basil"). Include at least one high-intent keyword (chicken sandwich, vegan bowl, poke, burrito) near the start. Avoid punctuation that breaks platform truncation.

12. **Final read-aloud check** — Every description must sound natural when read aloud by a server. If a sentence stumbles the tongue, rewrite it.

**Output requirements:**
- Dish-by-dish table: dish name, category, house description (target length), POS/delivery line (short), digital version (long)
- Allergen and dietary badge pass: each dish tagged consistently per house convention
- Menu-engineering note per dish: classification, copy-strength tier applied, rationale
- Flagged items: any claim that needs chef/owner verification, any banned clichés removed, any compliance concern
- Style guide snapshot: banned-word list applied, italicization rules used, capitalization convention
- Translation-ready formatting if `config.yml` requires a second language
- Correct terminology — cuisine vocabulary, technique verbs, allergen abbreviations, ingredient canonical names
- Ready to drop into InDesign, Toast, Square, Clover, DoorDash, or a web CMS with minimal editing
- Saved to `outputs/` if the user confirms

## Example Output

### Example 1 — Star, fine-dining print menu (Italian, polished-upscale)

**Input:**
- Dish: Tagliatelle al Ragù Bolognese
- Category: pasta course
- Ingredients: hand-cut egg tagliatelle (00 flour, Iowa-pastured eggs), 4-hour beef-and-pork ragù, soffritto, San Marzano D.O.P., milk, Parmigiano Reggiano 24-month
- Method: hand-rolled, hand-cut; ragù braised 4 hours at 195°F
- Flavor: deep, savory, slow-cooked; silky from the milk reduction; sharp aged Parm finish
- Cuisine: Emilian (Bologna)
- Allergens: gluten, dairy, egg
- Format: print fine-dining (8–15 words target)
- Price: $32 — Star (high margin, high popularity)
- Voice: polished-upscale, no clichés, signature word "hand-cut" used sparingly

**Menu-engineering note:** Star — confident, polished copy that justifies $32; lead with the technique and provenance the price implies.

**House style (print, 11 words):**

> Hand-cut egg tagliatelle, 4-hour beef-and-pork ragù, Parmigiano Reggiano 24-month. *(GF unavailable)*

**POS / delivery line (32 chars):**

> Tagliatelle Bolognese — 4-hr ragù

**Digital / server-training version (29 words):**

> Hand-cut egg tagliatelle from 00 flour and Iowa-pastured eggs, tossed in a 4-hour beef-and-pork ragù finished with milk and 24-month Parmigiano Reggiano. (Contains: gluten, dairy, egg)

**Compliance flags:** "hand-cut" verified with Chef Reyes (rolled and cut in-house daily). "24-month Parmigiano Reggiano" verified on the latest Forever Cheese invoice. No GF version available — flagged for the menu legend.

---

### Example 2 — Puzzle, casual lunch + delivery (Mexican fast-casual, playful)

**Input:**
- Dish: Pollo en Mole Negro Bowl
- Category: bowl entrée
- Ingredients: pulled chicken thigh, mole negro (chiles ancho/mulato/pasilla, sesame, almond, Oaxacan chocolate), cilantro rice, black beans, queso fresco, pickled onion
- Method: chicken braised 3 hours; mole simmered 6 hours
- Flavor: deep, smoky, slightly sweet, complex chile; not spicy hot
- Cuisine: Oaxacan
- Allergens: tree nut (almond), sesame, dairy (queso fresco — V request swap to none)
- Format: digital site (20–35 words) + delivery (60–120 chars)
- Price: $14.50 — Puzzle (high margin 71%, low popularity — the chocolate-mole word scares casual lunch guests)
- Voice: playful-fast-casual, demystify the dish

**Menu-engineering note:** Puzzle — the strongest sensory copy belongs here. The dish carries 71% margin but turns 4× less than the Star bowl. Copy job: signal "delicious," "approachable," and "not spicy-hot" without losing authenticity.

**House style (digital site, 31 words):**

> Slow-braised chicken thigh in *mole negro* — six hours of toasted chiles, sesame, almond, and Oaxacan chocolate, smoky and rich, not spicy-hot. Over cilantro rice and black beans, with queso fresco and pickled onion.
>
> *(Contains: tree nut, sesame, dairy. V version available — ask the cashier.)*

**POS / delivery line (89 chars):**

> Chicken Mole Bowl — Oaxacan mole negro, cilantro rice, black beans, queso fresco. Not spicy.

**Digital / server-training version (34 words):**

> Chef Sofia's grandmother's recipe — chicken thigh braised three hours, then folded into a *mole negro* simmered six hours from toasted ancho, mulato, and pasilla chiles, sesame, almond, and Oaxacan chocolate. Smoky, deep, gentle on heat.
>
> *(Contains: tree nut, sesame, dairy. V swap: omit queso, add roasted poblano — ask the cashier.)*

**Compliance flags:** "Six hours" mole simmer verified with kitchen log. "Oaxacan chocolate" verified — Mayordomo from Oaxaca on the spec. "Not spicy" claim is honest at the current chile blend (Scoville ~800). The "grandmother's recipe" claim verified with Chef Sofia in writing — keep the line.

---

### Example 3 — Plowhorse + LTO, third-party delivery (American, warm-neighborhood)

**Input:**
- Dishes: (a) Classic Cheeseburger — Plowhorse, $13, low margin / high turn — and (b) Spring LTO: Strawberry-Basil Lemonade — small plate, $7, debut item
- Category: (a) burger entrée — (b) zero-proof beverage
- Ingredients: (a) 6 oz brisket-chuck blend, American cheese, butter bun, LTO sauce, pickles, lettuce, tomato, onion. (b) Strawberry purée, basil leaf, fresh lemon, simple syrup, sparkling water
- Method: (a) griddled to medium; (b) muddled, shaken, topped sparkling
- Flavor: (a) buttery, classic, juicy; (b) bright, herbal, lightly sweet
- Cuisine: (a) American diner; (b) zero-proof seasonal
- Allergens: (a) gluten, dairy; GF bun avail. (b) none
- Format: DoorDash + Uber Eats (60–120 chars; SEO-aware; high-intent noun front-loaded)
- Prices: $13 / $7
- Voice: warm-neighborhood; signature word "house" used sparingly

**Menu-engineering notes:**
- Cheeseburger — Plowhorse: short, value-signaling, no purple prose. The dish moves on its own; copy needs to confirm what the searcher already wants.
- Strawberry-Basil Lemonade — debut LTO: opens the seasonal calendar; copy job is to make the basil intriguing, not weird.

**Cheeseburger — POS / delivery line (118 chars):**

> Classic Cheeseburger — house brisket-chuck blend, American cheese, butter bun, pickles, lettuce, tomato. GF bun available.

**Cheeseburger — house style (print, 14 words):**

> House brisket-chuck blend, American cheese, butter bun, lettuce, tomato, onion, pickles. (GF bun available)

**Cheeseburger — digital / server-training (28 words):**

> Six-ounce brisket-chuck blend ground in-house, griddled to medium, American cheese, our LTO sauce, butter-toasted bun, lettuce, tomato, onion, dill pickles. GF bun available on request. (Contains: gluten, dairy)

**Strawberry-Basil Lemonade — POS / delivery (96 chars):**

> Strawberry-Basil Lemonade — fresh lemon, muddled basil, strawberry, sparkling. Zero proof. New for spring.

**Strawberry-Basil Lemonade — house style (print, 12 words):**

> Fresh-squeezed lemon, muddled Genovese basil, strawberry, sparkling water. (Zero proof)

**Strawberry-Basil Lemonade — digital (24 words):**

> Fresh-squeezed lemon meets muddled Genovese basil and strawberry purée, finished with sparkling water — bright, lightly sweet, lightly herbal. New for spring. (Zero proof)

**Compliance flags:** "ground in-house" verified — brisket and chuck broken down and ground at 5:00 AM in the morning shift; keep the line. "Zero proof" used per the FDA-aligned terminology in the house style guide (avoiding "mocktail" per brand voice). "House LTO sauce" stays vague — proprietary recipe, no allergen-bearing ingredient (verified with Chef).

---

### Cross-handoffs (illustrated above)

- All three examples carry consistent badge convention (allergens in parentheses after the description; V/VG/GF as suffix tags).
- Foreign words italicized once per description, no translation in the print line, gloss in the digital line where the dish would otherwise be unorderable.
- For the **Bolognese** Star: Dynamic Menu Pricing Advisor confirms the $32 price band; copy reflects the band.
- For the **Mole Negro** Puzzle: copy strength is the lift lever — pair with a Social Media Post Generator caption set on the launch week.
- For the **LTO Lemonade**: hand the launch caption to the Social Media Post Generator; carry the same "fresh-squeezed lemon, muddled basil" hook into the social copy for consistency.
