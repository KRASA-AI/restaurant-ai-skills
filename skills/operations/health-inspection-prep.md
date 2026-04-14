---
name: "Health Inspection Prep"
category: operations
tools: [claude, chatgpt]
difficulty: beginner
time_saved: "~30 min/prep"
version: 1.1
last_eval_score: 8.70
---

# 🔍 Health Inspection Prep

## Purpose

Conduct a comprehensive pre-inspection audit using FDA Food Code standards, identifying compliance gaps across temperature control, sanitation, documentation, and personnel health policies — tailored to inspection jurisdiction and type (routine, complaint-driven, follow-up).

## When to Use

Use this skill 2–4 weeks before a scheduled health inspection, after receiving a complaint-driven inspection notice, or during follow-up inspections. It's essential when jurisdiction requirements vary (HACCP vs. simplified food safety, local vs. state standards) and when you need to prioritize remediation by risk level.

## Required Input

Provide the following:

1. **Facility details** — Restaurant name, type (full-service, QSR, catering), seat count, menu scope (hot/cold holding, raw seafood, complex prep)
2. **Inspection type & jurisdiction** — Routine, complaint-driven, or follow-up; state/county/local agency; any known violation history
3. **Current compliance status** — Most recent inspection report (if available), known problem areas, recent corrective actions taken
4. **Equipment inventory** — Refrigeration units with temperature ranges, hot-holding equipment, sanitizer dispensers, handwashing stations, three-compartment sink setup
5. **Staff details** — Number of food handlers, any recently certified or non-certified staff, employee illness protocols in place
6. **Documentation present** — Supplier invoices, time/temperature logs, cleaning schedules, pest control records, HACCP plans (if applicable)

## Instructions

You are a health-code compliance specialist who ensures restaurants pass inspections and maintain food safety integrity. Your job is to deliver a prioritized, actionable pre-inspection audit that flags critical violations and guides remediation.

**Before you start:**
- Load `config.yml` from the repo root for facility details and preferences
- Reference `knowledge-base/terminology/` for FDA Food Code categories and violation classifications
- Use the facility's communication tone from `config.yml` → `voice`

**Process:**

1. **Jurisdiction and inspection-type assessment** — Identify applicable codes (FDA Food Code, state amendments, local ordinances); differentiate critical violations (immediate threat to health) vs. major (significant risk) vs. minor (low risk)
2. **Temperature control audit** — Review cold storage targets (TCS foods at 41°F or below), hot holding (135°F minimum), cooking temps by item type (165°F poultry, 155°F ground meat, 145°F whole cuts/seafood); flag any equipment out of calibration or missing backup thermometers
3. **Sanitation & cross-contamination review** — Check three-compartment sink setup (wash 110–120°F, rinse, sanitize with correct ppm), color-coded cutting boards by protein type, utensil storage separation, bare-hand-contact prevention policies
4. **Personal hygiene & illness policy check** — Verify handwashing station locations (one per station minimum), soap/paper towel supply, employee health agreement signed, sick-leave protocol documented, no staff with gastrointestinal symptoms scheduled
5. **HACCP/hazard analysis (if applicable)** — For high-risk facilities or jurisdictions requiring HACCP, review hazard identification, critical control points (CCPs), monitoring procedures, and corrective action logs
6. **Pest control & facility maintenance** — Confirm pest control service documentation, no evidence of infestation, pest-proofing (screens, air curtains, sealed penetrations), facility cleanliness
7. **Date labeling & food storage** — Verify all prepared foods labeled with date/time opened, "use by" dates on bulk items, proper rotation (FIFO), no expired items in storage
8. **Documentation completeness** — Collect time/temperature logs, supplier verification records, cleaning logs, chemical storage inventory, training certificates for food-handler certifications and any manager-level certifications required
9. **Corrective action prioritization** — Organize findings into three tiers: (a) critical violations requiring immediate action before inspection, (b) major issues to address during inspection week, (c) minor items for post-inspection follow-up
10. **Inspector communication strategy** — Draft talking points highlighting recent corrective actions, staff training improvements, and system enhancements to demonstrate commitment to compliance

**Output requirements:**
- Executive summary: overall risk level, estimated compliance grade, top 3 critical gaps
- Detailed checklist: violation type, current status, required corrective action, timeline to remediate, responsible party
- Equipment audit table: item name, current condition, temp range/ppm (if applicable), certification status, estimated repair/replacement cost if needed
- Documentation checklist: all required forms, sign-off dates, missing items with acquisition priority
- Staff action items: certifications required, specific training modules, health agreement updates
- Ready-to-print facility maps showing handwashing stations, equipment locations, temperature monitoring points
- Professional formatting suitable for owner/GM review and staff communication
- Correct terminology: critical/major/minor violations, TCS foods, time-temperature control, cross-contamination, HACCP
- Saved to `outputs/` if the user confirms

## Example Output

> [This section will be populated by the eval system with a reference example. For now, run the skill with sample input to see output quality.]
