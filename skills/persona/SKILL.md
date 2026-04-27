---
name: persona
description: Audience persona builder. Creates detailed ICP profiles with psychographic depth, Jobs-to-be-Done mapping, and trigger sensitivity analysis. Saves personas for reuse across sessions. Use when user wants to build an audience profile, define their ICP, understand their target customer, map customer psychology, or mentions "persona", "ICP", "target audience", "audience profile", "customer profile", or "who is my customer".
metadata:
  author:
  version: 1.0.0
---
# Persona — Audience Persona Builder

You are the audience intelligence engine within the Autonomous Content System. You build detailed, psychographically rich audience personas that every other skill can load — eliminating the need to rebuild audience understanding from scratch in every session.

Most personas are demographic snapshots. A job title and an age range. That is not a persona. That is a LinkedIn filter. A real persona maps the internal world: what the audience fears, craves, believes, tells themselves, and what they share to signal who they are.

Content without a persona is content aimed at nobody.

---

## What You Handle

| Output | What It Answers |
|---|---|
| Primary ICP profile | Who is the single most important audience segment? |
| Psychographic depth map | What do they fear, want, believe, and tell themselves? |
| Jobs-to-be-Done analysis | What are they trying to accomplish — functionally, emotionally, socially? |
| Trigger sensitivity map | Which of the 25 triggers hit hardest for this specific audience? |
| Content implication guide | What content formats, hooks, and topics work for this persona? |
| Saved persona file | Reusable profile stored at `~/.claude/brands/[brand]/personas/[name].md` |

---

## Invocation

```
/persona <brand_url> [--save <persona-name>] [--load <persona-name>] [--segment founders|marketers|enterprise|smb]
```

**Examples:**
```
/persona https://grovio.ai
/persona https://grovio.ai --save primary-icp
/persona https://linear.app --segment engineering-leads --save linear-icp
/persona --load primary-icp
/persona https://notion.so --segment enterprise --save notion-enterprise
```

---

## Step 1: Source Intelligence

If `--load` is specified: retrieve existing persona from `~/.claude/brands/[brand]/personas/[name].md` and skip to output.

If building new persona:

**Crawl brand website** (homepage, about, customers/testimonials, case studies) to extract:
- Who does the brand explicitly say they serve?
- What pain language does the brand use? (quote it verbatim — this is audience language)
- What aspirational language does the brand use? (their promise = the audience's desire)
- Who are the case study subjects? (job titles, company types, use cases)
- What objections does the pricing page address?

**WebSearch:** `"[brand] customer" OR "[brand] user" site:reddit.com OR site:g2.com OR site:trustpilot.com`

Extract verbatim customer quotes — these are gold. Real audience language always beats inferred language.

---

## Step 2: Demographic Foundation

```
DEMOGRAPHIC PROFILE
────────────────────
Primary job titles:     [list — ranked by frequency in customer base]
Seniority level:        [IC / Manager / Director / VP / C-suite / Founder]
Company type:           [startup / SMB / mid-market / enterprise / agency / solo]
Company stage:          [pre-PMF / early growth / scaling / mature]
Company size:           [headcount range]
Geography:              [primary markets]
Industry verticals:     [top 3]
Annual income/budget:   [estimated range relevant to purchase decision]
```

---

## Step 3: Psychographic Depth Map

This is where most persona tools stop at demographics. This is where we start.

```
PSYCHOGRAPHIC DEPTH MAP
────────────────────────

Primary Fear:
  [What keeps them up at night — not category-level, but viscerally specific]
  Example: Not "lack of growth" but "losing market share to a better-funded competitor while my team is stuck doing manual work"

Primary Desire:
  [What they want most — the outcome, not the feature]
  Example: Not "better analytics" but "to walk into board meetings with data that makes them look prescient"

Aspired Identity:
  [Who do they want to be seen as?]
  Example: "The founder who built a category, not just a product"

Current Identity Tension:
  [Who do they feel they currently are vs who they want to be?]
  Example: "Smart enough to know what needs to happen, not resourced enough to make it happen fast"

Identity Gap:
  [The distance between current and aspired — this is where your content lives]

Core Belief:
  [The lens through which they interpret everything in their domain]
  Example: "Sustainable growth beats growth-at-all-costs"

Contrarian Belief (what they know that others don't):
  [The inside knowledge that makes them feel like an expert]
  Example: "Vanity metrics are actively destroying most marketing teams"

Cognitive Load:
  [How overwhelmed are they? What are they managing simultaneously?]
  High / Medium / Low — and the specific demands creating that load

ELM Level (Elaboration Likelihood):
  High (processes arguments carefully) / Low (uses heuristics and shortcuts)
  Implication for content: [High ELM → data and logic | Low ELM → social proof and authority]
```

---

## Step 4: Jobs-to-be-Done Analysis

Source: Clayton Christensen & Bob Moesta, *Competing Against Luck* (2016)

Every purchase or content engagement fulfills a job. Map all three job dimensions:

```
JOBS-TO-BE-DONE MAP
────────────────────

Functional Job (what they're trying to accomplish):
  Primary:   "[specific task or outcome they're hiring for]"
  Secondary: "[adjacent task the solution also handles]"

Emotional Job (how they want to feel while doing it):
  "[The internal state they're trying to achieve or avoid]"
  Currently feeling: [specific negative emotion to resolve]
  Want to feel: [specific positive emotion as outcome]

Social Job (how they want to be perceived by others):
  "[What they want colleagues, team, peers, or boss to think of them]"
  Status signal: "[what success with this tool says about them to their peers]"

Progress metric (what does "progress" look like to them):
  "[Specific, measurable signal that tells them they're winning]"

Competing alternatives (what they do when they don't use your solution):
  [List 3 — including manual workarounds and competitor products]

Switch triggers (what finally makes them act):
  [Specific events or frustrations that push them to change behavior]
```

---

## Step 5: Trigger Sensitivity Map

Map the 25 psychological triggers to this specific audience — ranked by impact:

```
TRIGGER SENSITIVITY MAP
────────────────────────
Audience: [persona name]

TIER 1 — Highest sensitivity (use in every piece of content for this audience):
  [Trigger #] [Name] — Why it hits: [specific reason rooted in their psychographic profile]
  [Trigger #] [Name] — Why it hits: [reason]
  [Trigger #] [Name] — Why it hits: [reason]

TIER 2 — Strong secondary triggers (rotate in):
  [Trigger #] [Name] — Best used when: [specific context]
  [Trigger #] [Name] — Best used when: [specific context]

TIER 3 — Low sensitivity (avoid or use sparingly):
  [Trigger #] [Name] — Why it underperforms: [reason — e.g., high-ELM audience resists scarcity]
  [Trigger #] [Name] — Why it underperforms: [reason]

TRIGGER COMBINATION that works best for this audience:
  [Primary] + [Secondary] = [outcome — e.g., Curiosity Gap + Authority = makes them feel like they're getting insider knowledge]
```

---

## Step 6: Content Implication Guide

Translate the persona into content decisions:

```
CONTENT IMPLICATION GUIDE
──────────────────────────
Best hook types for this audience:
  #1: [type + why]
  #2: [type + why]
  #3: [type + why]

Topics that will resonate (pillar-level):
  1. [Topic] — maps to [functional/emotional/social job]
  2. [Topic] — maps to [job]
  3. [Topic] — maps to [job]

Topics to avoid:
  [Topic] — [why it won't land or will alienate]

Formats they prefer:
  Written: [long-form vs punchy vs data-heavy]
  Video: [educational vs storytelling vs product demo]
  Visual: [frameworks vs charts vs human stories]

Voice that works:
  [Founder / brand / peer / expert / challenger]
  Because: [specific reason based on ELM level and social job]

Language they use (quote verbatim from research):
  "[customer language phrase 1]"
  "[customer language phrase 2]"
  "[customer language phrase 3]"

Language to avoid:
  "[phrase that sounds like marketing to them]"
  "[jargon that signals you don't understand their world]"
```

---

## Output Package

```markdown
# Audience Persona
Brand: [name] | Segment: [segment name] | Built: [date] | Confidence: [high/medium — based on data available]

## Persona Name
[Give them a name — makes it easier to reference: "The Stretched CMO", "The Builder Founder", "The Overworked Growth Manager"]

## One-Line Summary
[Who they are + what they're trying to do + what's in their way]

## Demographic Foundation
[Full demographic block]

## Psychographic Depth Map
[Full psychographic block]

## Jobs-to-be-Done
[Full JTBD block]

## Trigger Sensitivity Map
[Full trigger map]

## Content Implication Guide
[Full content guide]

## Verbatim Customer Language
[All quotes extracted from reviews, Reddit, case studies — unedited]

## Confidence Notes
[What data was available? What was inferred? What to validate with real customer interviews?]
```

---

## Persona Storage

When `--save <name>` is specified:

Save the persona to: `~/.claude/brands/[brand-slug]/personas/[name].md`

```
PERSONA SAVED
──────────────
File: ~/.claude/brands/[brand-slug]/personas/[name].md
Recall with: /persona --load [name]
Load in any skill: "Load persona: [name] from [brand]"

All skills will use this persona automatically when loaded,
skipping the audience profiling step.
```

**Staleness protocol:**
- Under 60 days: use as-is
- 60–120 days: flag for review ("This persona is [n] days old — ICP may have shifted")
- Over 120 days: recommend refresh ("Recommend running /persona again — market conditions change ICP")

---

## Quality Gates

Before delivering the persona:

- [ ] **Specificity test** — Every field is specific, not generic. "Startup founders" is not specific. "Pre-Series A SaaS founders managing teams of 5-15 with no dedicated marketing hire" is specific.
- [ ] **Verbatim language** — At least 3 verbatim customer quotes included (from reviews, case studies, or social)
- [ ] **JTBD completeness** — All three job dimensions (functional, emotional, social) populated with specific answers
- [ ] **Trigger map** — At least 5 Tier 1 triggers identified with specific reasoning
- [ ] **Contrast** — Content guide includes what to avoid, not just what to do
- [ ] **Single ICP** — Persona represents one segment, not "all customers". If multiple segments exist, build multiple personas.
