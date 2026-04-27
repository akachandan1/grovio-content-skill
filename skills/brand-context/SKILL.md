---
name: brand-context
description: Project-scoped brand intelligence foundation. Creates and maintains a .claude/brand-context.md file that every other skill reads before executing. Use when setting up a new brand, updating brand context, or loading context into a session. Trigger words: "set up brand", "brand context", "update brand", "load brand", "my brand is", "about my product", "before we start", "project context".
metadata:
  author:
  version: 1.0.0
---
# Brand Context — Project-Scoped Brand Intelligence

You are the brand intelligence foundation of the Autonomous Content System. You create and maintain `.claude/brand-context.md` — a project-scoped file that every other skill reads before executing, so no session starts from scratch.

Unlike brand-memory (which saves to `~/.claude/brands/` on one machine), brand-context lives inside the project directory. It travels with the repo. Every collaborator inherits it. Every skill uses it.

---

## What You Handle

| Task | Output |
|---|---|
| Create brand context | Full `.claude/brand-context.md` from URL or conversation |
| Auto-draft from website | Crawl brand URL → draft all sections → user reviews |
| Update brand context | Refresh specific sections without rebuilding everything |
| Load brand context | Read and summarise current context for the session |
| Psychological profile | Map brand to 25 triggers — which does it own? which is unclaimed? |

---

## Invocation

```
/brand-context setup <brand_url>
/brand-context update
/brand-context load
/brand-context profile
```

**Examples:**
```
/brand-context setup https://grovio.ai
/brand-context setup https://zepto.com
/brand-context update
/brand-context load
/brand-context profile
```

---

## Workflow

### Step 1 — Check for Existing Context

First, check if `.claude/brand-context.md` exists in the current directory.

**If it exists:**
- Read it and summarise what's captured
- Ask which sections to update
- Only gather info for changed sections

**If it doesn't exist, proceed to Step 2.**

---

### Step 2 — Auto-Draft from Brand URL

Crawl the brand website (homepage, about, pricing, testimonials, case studies) and extract:

**Product Intelligence:**
- One-line positioning (what is it, for whom, to what end)
- Product category (how customers search for it)
- Business model and pricing tier
- Core differentiators (what makes it different from alternatives)
- Key features vs key benefits (features: what it does / benefits: what that means)

**Audience Intelligence:**
- Who the brand explicitly says they serve (job titles, company types, situations)
- Pain language (verbatim phrases from the site — these are customer words)
- Aspiration language (the promise — what life looks like after the product)
- Who appears in case studies and testimonials

**Voice Intelligence:**
- Tone (professional, casual, bold, empathetic, technical)
- Vocabulary the brand owns (specific terms, named frameworks, proprietary language)
- What the brand never says (avoid list)
- Brand voice vs founder voice distinction

**Competitive Intelligence:**
- Named competitors or alternatives on the site
- How the brand positions against them
- What they claim to do better

Present the draft and ask: "What needs correcting? What's missing?"

---

### Step 3 — Psychological Trigger Profile

This is what Corey's `product-marketing-context` doesn't have.

Map the brand to the 25 psychological triggers — identify:

**Owned triggers** (brand already uses these well):
- Which 3–5 triggers appear consistently in their existing copy?
- What's the evidence? (Quote specific copy)

**Underused triggers** (present but weak):
- Which triggers does the brand attempt but execute poorly?

**Unclaimed triggers** (competitors own these / nobody owns these):
- Which triggers are absent — and represent whitespace?
- Which triggers would resonate most with this audience?

Output format:
```
PSYCHOLOGICAL TRIGGER PROFILE
──────────────────────────────────────────────────
Owned (using well):
  - [Trigger]: "[verbatim copy example]"
  - [Trigger]: "[verbatim copy example]"

Underused (present but weak):
  - [Trigger]: current usage + what it should say instead

Unclaimed (opportunity):
  - [Trigger]: why this audience would respond + content angle to claim it

Recommended trigger stack for content:
  Primary:   [trigger] — use in hooks and headlines
  Secondary: [trigger] — use in body copy and proof points
  Tertiary:  [trigger] — use in CTAs
──────────────────────────────────────────────────
```

---

### Step 4 — Write the Context File

Save to `.claude/brand-context.md` in the current project directory.

---

## Output File Structure

```markdown
# Brand Context: [Brand Name]
Last updated: [date]
Source: [URL]

## Product Overview
One-line positioning: [outcome] for [audience] who want to [job]
Category: [how customers search for this]
Business model: [SaaS / marketplace / D2C / service]
Pricing: [free tier / starts at X / enterprise]

## Core Value Proposition
Primary benefit: [the #1 thing customers get]
Secondary benefits: [2-3 supporting benefits]
Key differentiator: [what makes this different from the obvious alternative]

## Target Audience
Primary ICP: [job title] at [company type] who [situation]
Pain language (verbatim): "[quote]", "[quote]", "[quote]"
Aspiration language (verbatim): "[quote]", "[quote]"
Jobs to be done:
  Functional: [what they're trying to accomplish]
  Emotional: [how they want to feel]
  Social: [how they want to be perceived]

## Brand Voice
Tone: [3 adjectives]
Vocabulary owned: [terms, frameworks, named concepts]
Never say: [avoid list]
Brand account voice: [characteristics]
Founder account voice: [characteristics]

## Competitive Landscape
Primary competitors: [names]
Positioning vs competitors: [how brand differentiates]
Competitor trigger stack: [what triggers they own]

## Psychological Trigger Profile
Owned triggers: [list with copy evidence]
Underused triggers: [list with improvement notes]
Unclaimed triggers: [list with content angles]
Recommended stack: Primary / Secondary / Tertiary

## Content Rules
- [Rule derived from brand voice — specific and actionable]
- [Rule derived from audience psychology]
- [Rule derived from trigger profile]

## Campaign Log
[Auto-updated by other skills when content is generated]
```

---

## Quality Gates

- [ ] Pain language is verbatim from the brand/customers — not paraphrased
- [ ] Trigger profile identifies at least 3 owned and 2 unclaimed triggers
- [ ] Voice section is specific enough that two different writers produce similar-sounding copy
- [ ] JTBD covers all three dimensions (functional, emotional, social)
- [ ] File saved to `.claude/brand-context.md` in current project directory

---

## How Other Skills Use This File

Every skill in the system checks for `.claude/brand-context.md` at Step 1. If it exists:
- Skip brand crawling and audience profiling
- Load positioning, voice, triggers, and ICP directly
- Apply the recommended trigger stack to content generation

If it doesn't exist, skills fall back to crawling the URL provided.

**Instruction for all other skills:** At the start of every run, check if `.claude/brand-context.md` exists. If yes, read it and use it as the brand intelligence layer — skip re-crawling.
