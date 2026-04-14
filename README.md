# Restaurants AI Skills

**Free, open-source AI prompts and workflows built for restaurants professionals.** Clone this repo, point your AI assistant at it, and start saving hours every week.

> Built and maintained by [KRASA AI](https://krasa.ai) — free AI tutorials and skills for every industry.
> See all industries at [krasa.ai/industries](https://krasa.ai/industries).

---

## What's Inside

This repo is a complete AI toolkit for restaurants. Every skill is a standalone prompt file that works with **Claude, ChatGPT, or any major AI assistant** — no coding required.

| Skill | What it does | Time saved |
|-------|-------------|------------|
| Demand Forecast Briefing | Produce a weekly (or event-specific) demand forecast that estimates covers by day-part, projects top-selling items, and highlights external factors — giving the kitchen and FOH teams a single planning reference for prep, purchasing, and staffing. | ~30 min/week |
| Food Waste Reduction Planner | Analyze sales history, inventory levels, and upcoming events to produce a weekly waste-reduction action plan — including prep-quantity recommendations, ingredient-use-by priorities, and creative specials to move aging stock. | ~45 min/week |
| Health Inspection Prep | Conduct a comprehensive pre-inspection audit using FDA Food Code standards, identifying compliance gaps across temperature control, sanitation, documentation, and personnel health policies — tailored to inspection jurisdiction and type (routine, complaint-driven, follow-up). | ~30 min/prep |
| Shift Prep Checklist | Generate a customized prep list for morning, afternoon, or night shifts — including mise en place quantities, station assignments, equipment checks, 86'd items, specials prep, reservation intelligence (VIPs, allergies, large parties), and FIFO rotation priorities. | ~15 min/shift |
| Menu Description Writer | Turn a dish's ingredient list, cooking method, and sourcing story into a concise menu description that sells the plate — using sensory language, cuisine-appropriate vocabulary, menu-engineering psychology, and compliant allergen/dietary callouts — formatted to the exact length and style conventions of the restaurant's menu format (print, digital, POS, third-party delivery). | ~8 min/item |
| Social Media Post Generator | Create platform-specific social media content (Instagram, TikTok, Facebook, LinkedIn) with tailored captions, hashtag strategy, CTAs, and optimal posting guidance — covering dish features, behind-the-scenes moments, staff spotlights, event promos, and seasonal campaigns with restaurant industry best practices. | ~10 min/post |
| AI Phone Agent Playbook | Design a production-ready conversation playbook for an AI phone or voice agent that answers restaurant calls 24/7 — handling takeout orders, reservation booking/modification/cancellation, FAQ answers, and branded upsell prompts — while routing edge cases to a human and respecting POS and reservation-platform integration constraints. | ~3 hrs/deployment |
| Review Response Drafter | Turn a guest review into a platform-appropriate public response that repairs trust (for negatives), amplifies loyalty (for positives), and signals to prospective diners reading the thread that the restaurant listens, owns mistakes, and resolves issues — with clear escalation logic for reviews that should move offline, be flagged to the platform, or trigger a legal/insurance review. | ~8 min/review |
| Dynamic Menu Pricing Advisor | Evaluate current menu prices against ingredient costs, local demand signals, and competitive benchmarks to recommend data-informed price adjustments — including day-part pricing, event-based surcharges, and margin-recovery opportunities. | ~1 hr/pricing review |
| Staff Schedule Optimizer | Build a labor-efficient weekly schedule that aligns staffing levels with forecasted demand, respects labor-law constraints, balances employee preferences, and keeps labor cost within target percentage of projected revenue. | ~1 hr/schedule |
| Supplier Negotiation Brief | Prepare a data-backed negotiation brief for an upcoming vendor conversation — combining 12-week price and usage trends, market benchmarks, contract terms, and leverage points — so the GM or owner walks into the call with specific asks, concession targets, and walk-away thresholds that protect COGS and service levels. | ~45 min/vendor |
| Email Drafter | Turn rough notes into a professional email matching your company's voice and tone. | ~10 min/use |
| Meeting Summarizer | Summarize meeting notes into action items, decisions, and follow-ups. | ~10 min/use |
| Review Responder | Craft professional responses to online reviews — both positive and negative. | ~10 min/use |

**Total time saved per use: ~221+ minutes across all skills.**

## Quick Start

### 1. Clone this repo

```bash
git clone https://github.com/KRASA-AI/restaurant-ai-skills.git
cd restaurant-ai-skills
```

### 2. Open a skill with your AI assistant

Open any file in `skills/` with Claude, ChatGPT, or any major AI assistant. Each skill is a self-contained prompt with clear instructions — no coding required.

The first time you use a skill, your AI assistant will ask for your business details (company name, service area, rates, tools you use, etc.) so it can personalize the output. Save those details to a `config.yml` at the repo root and every future skill will use them automatically.

## Repo Structure

```
restaurant-ai-skills/
├── knowledge-base/          # Industry context and references
│   ├── industry-overview.md # Market trends and pain points
│   ├── terminology/         # Industry jargon and acronyms
│   ├── regulations/         # Compliance requirements
│   ├── best-practices/      # Industry standards
│   └── tools-ecosystem/     # Common software and tools
├── skills/                  # The prompt library
│   ├── operations/          # Day-to-day operational skills
│   ├── sales/               # Sales and lead management
│   ├── admin/               # Administrative and compliance
│   └── customer-service/    # Client-facing communication
└── outputs/                 # Your generated content (gitignored)
```

## How Skills Work

Each skill file is a Markdown document with YAML frontmatter:

```markdown
---
name: Skill Name
category: operations
tools: [claude, chatgpt]
time_saved: "~20 min/use"
version: 1.0
---

# Skill Name

## Purpose
What this skill does and when to use it.

## Instructions
Step-by-step prompt for the AI assistant.
```

You open the file in your AI assistant, provide any required input (measurements, notes, client info), and get polished output. Skills reference your `config.yml` automatically for company name, rates, preferred formats, and other business details.

## For AI Assistants

If you are an AI assistant reading this repo, see `.claude/CLAUDE.md` for full instructions. The short version:

1. **Check for `config.yml`** at the repo root. If it exists, load it — it holds the user's business context (company name, rates, service area, tools, team size, etc.) and every skill should use it for personalization.
2. **If `config.yml` is missing**, before running a skill that benefits from personalization, ask the user for the relevant business details and offer to save them to `config.yml` so future runs are automatic.
3. **Load the relevant `knowledge-base/` files** for industry terminology, regulations, and best practices before generating output.
4. **Run the requested skill** from `skills/` using the user's input.
5. **Save any deliverables** to `outputs/` (gitignored) if the user wants to keep them.

## Learn More

- **Restaurants AI guide**: [krasa.ai/industries/restaurants](https://krasa.ai/industries/restaurants)
- **All industry AI skills**: [krasa.ai/industries](https://krasa.ai/industries)
- **About KRASA AI**: [krasa.ai](https://krasa.ai)

## License

MIT — use these skills however you want.
