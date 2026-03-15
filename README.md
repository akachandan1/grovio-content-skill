# Grovio Content Skill

> **The world's most psychologically advanced brand content engine for Claude Code.**
> Combines consumer psychology, behavioral economics, persuasion science, and neuromarketing to generate content that engineers behavior — not just publishes words.

---

## What This Is

A Claude Code skill that transforms any brand URL into a full content intelligence system.

Give it a brand website + platform + goal. It will:

1. **Crawl the brand's website** — extract positioning, voice, vocabulary, values
2. **Pull their social media history** — audit what's worked, what hasn't, what triggers they're missing
3. **Map competitor whitespace** — find angles nobody is owning
4. **Build an audience psychology profile** — ELM involvement, Fogg model, top triggers
5. **Gather real-time trend intelligence** — trending angles, saturation alerts, data points
6. **Select the optimal strategy** — funnel stage + emotion + 3-trigger stack + narrative framework
7. **Generate 5 content variants** — each using a different psychological entry point
8. **Score every variant on 6 dimensions** — composite score out of 60
9. **Produce a ranked output package** — #1 Publish / #2 A/B Test / #3 Reserve + optimization notes

**The output is not content. It's behavior-engineered content with a full psychological audit.**

---

## The Operating Principle

Every piece of content must simultaneously hit three brain systems:

| Brain System | Needs | Content Layer |
|---|---|---|
| Emotional brain | Feeling, story, identity | Narrative + emotional trigger |
| Social brain | Belonging, proof, norms | Social trigger + tribe signal |
| Rational brain | Logic, value, evidence | Utility + credibility |

Content that hits one or two of these is mediocre. Content that hits all three spreads.

---

## Quick Start

### Prerequisites

- [Claude Code](https://claude.ai/code) installed
- Skills directory at `~/.claude/skills/`

### Installation

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/grovio-content-skill.git

# Copy skill to your Claude skills directory
cp -r grovio-content-skill/skill ~/.claude/skills/grovio-content
```

### Usage

Open Claude Code and run:

```
/grovio-content <brand_website_url> <platform> <topic_or_goal>
```

**Examples:**
```
/grovio-content https://stripe.com linkedin thought-leadership
/grovio-content https://notion.so twitter product-launch
/grovio-content https://linear.app email nurture-sequence
/grovio-content https://figma.com instagram brand-awareness
/grovio-content https://hubspot.com blog seo-content
/grovio-content https://yourcompany.com all campaign-launch
```

**Supported platforms:** `linkedin` | `twitter` | `instagram` | `email` | `blog` | `all`

**Output:** Saved automatically to `GROVIO-CONTENT-[BRAND]-[DATE].md` in your working directory.

---

## Repository Structure

```
grovio-content-skill/
├── README.md                        ← You are here
├── LICENSE                          ← MIT
├── skill/
│   └── SKILL.md                     ← The Claude Code skill file
├── docs/
│   ├── psychology-framework.md      ← Full 25 triggers + all frameworks reference
│   └── platform-guide.md            ← Platform-specific content rules
└── examples/
    └── maruti-suzuki-linkedin/
        ├── README.md                ← Context and walkthrough
        └── output.md                ← Full generated output
```

---

## The 8-Phase Pipeline

```
Phase 1: Brand Intelligence Gathering
  ├── Website crawl (7 key pages via Firecrawler)
  ├── Social media audit (via XPOZ connector — Twitter, Instagram, LinkedIn)
  └── Competitor content mapping + whitespace detection

Phase 2: Brand Voice DNA Profile
  ├── Voice archetype identification
  ├── Tone spectrum mapping (formal↔casual, safe↔bold, etc.)
  ├── Vocabulary fingerprint extraction
  └── Identity signal analysis

Phase 3: Audience Psychology Map
  ├── ELM involvement level (high/medium/low → content format routing)
  ├── Fogg Behavior Model assessment (Motivation × Ability × Trigger)
  ├── Top 5 psychological triggers for this audience
  └── SDT needs mapping (Autonomy, Competence, Relatedness)

Phase 4: Content Intelligence
  ├── Real-time trend scoring (rising/peak/declining)
  ├── Saturation alerts (what to avoid)
  ├── Contrarian angles (unpopular truths)
  └── Fresh data points for authority content

Phase 5: Content Strategy Selection
  ├── Funnel stage detection (Awareness → Loyalty)
  ├── Primary + secondary emotion selection
  ├── 3-trigger stack selection (from 25 triggers library)
  └── Narrative framework selection (AIDA / PAS / StoryBrand / Contrarian / Data Drop / etc.)

Phase 6: Content Generation Engine
  ├── 5 variants minimum per platform
  ├── Platform-native formatting (LinkedIn / Twitter / Instagram / Email / Blog)
  ├── Hook-first construction
  └── Fogg completion check per variant

Phase 7: Psychological Scoring Engine
  ├── Trigger Potency (0-10)
  ├── Emotional Resonance (0-10)
  ├── Brand Voice Fidelity (0-10)
  ├── Originality (0-10)
  ├── Utility (0-10)
  └── Virality Potential (0-10) → Composite /60

Phase 8: Final Output Package
  ├── #1 PUBLISH (highest scored variant + rationale)
  ├── #2 A/B TEST (variant to split test)
  ├── #3 RESERVE (scenario-specific usage)
  ├── Full scoring matrix
  ├── Optimization notes
  └── Next 5 content angle suggestions
```

---

## The Psychology Engine

This skill is built on a research-backed framework combining:

### Core Theories
| Theory | How It's Used |
|---|---|
| **Elaboration Likelihood Model (ELM)** | Routes content format based on audience involvement level |
| **Fogg Behavior Model** | Validates every variant has Motivation + Ability + Trigger |
| **Self-Determination Theory (SDT)** | Maps Autonomy / Competence / Relatedness needs |
| **Theory of Reasoned Action** | Ensures content shapes beliefs + social norms simultaneously |
| **Relationship Marketing Theory** | Designs for loyalty + emotional brand bonding |

### The 25 Psychological Triggers
The core of the scoring engine. Five categories:

**Social Triggers:** Social Proof · Authority · Liking · Unity · Bandwagon Effect

**Scarcity & Urgency:** Scarcity · Urgency · FOMO · Exclusivity

**Cognitive Bias:** Loss Aversion · Anchoring · Framing Effect · Availability Bias · Confirmation Bias · Cognitive Fluency

**Emotional:** Curiosity Gap · Surprise · Awe · Fear · Belonging

**Motivation:** Reciprocity · Commitment & Consistency · Progress Effect · Personalization · Identity Signaling

→ Full reference: [`docs/psychology-framework.md`](docs/psychology-framework.md)

### Narrative Frameworks
| Framework | Best For |
|---|---|
| AIDA | Short posts, ads, email subjects |
| PAS | Landing pages, product content |
| StoryBrand | Brand narrative, launch content |
| The Contrarian | Thought leadership, viral posts |
| The Data Drop | Authority content |
| Before/After/Bridge | Transformation content |
| The Confession | Trust-building content |

---

## 6-Dimension Scoring Rubric

Every generated variant is scored across:

| Dimension | What It Measures |
|---|---|
| **Trigger Potency** | How powerfully are psychological triggers embedded? |
| **Emotional Resonance** | How strongly does it create an emotional response? |
| **Brand Voice Fidelity** | Does it sound unmistakably like this brand? |
| **Originality** | How fresh and differentiated is the angle? |
| **Utility** | How much practical value does the reader get? |
| **Virality Potential** | How likely is it to be shared, saved, or quoted? |

**Composite score: X/60**

Scores below 35/60 are flagged as "do not publish without significant revision."

---

## Quality Gates

Every variant must pass 5 gates before inclusion in the output:

**3-Brain Test**
- [ ] Emotional brain: Does it make the reader *feel* something specific?
- [ ] Social brain: Does it reference others, norms, or tribe signals?
- [ ] Rational brain: Does it give the reader something real and useful?

**Hook Test**
- [ ] Does the first line stop scroll without context?
- [ ] Would someone screenshot just the first line?
- [ ] Does it create a curiosity gap or deliver a surprise?

**Identity Signal Test**
- [ ] Can you complete: "Sharing this tells the world I am ___"?
- [ ] Is that identity signal something the audience *wants* to project?

**Fogg Completeness Test**
- [ ] Motivation present?
- [ ] Ability present? (CTA is simple + frictionless)
- [ ] Trigger present? (reason to act NOW)

**Brand Fidelity Test**
- [ ] Remove the brand name — would you still know who wrote this?
- [ ] Does it use their vocabulary fingerprint?
- [ ] Does it avoid their off-limits language?

---

## Example Output

See a real run on **Maruti Suzuki → LinkedIn Thought Leadership**:

- [`examples/maruti-suzuki-linkedin/output.md`](examples/maruti-suzuki-linkedin/output.md)

Includes full brand intelligence brief, audience psychology map, 5 variants, scoring matrix, and next content angle pipeline.

**Top scoring variant (49/60):**

> *India will not electrify the way the headlines say it will.*
>
> *That's not pessimism. That's what you learn when 29 million Indian families trust you with their first car.*
>
> *→ 72% of India's EV sales happen in just 10 cities*
> *→ CNG outsells EVs in India 4:1*
> *→ Public charging covers less than 12% of India's districts...*

---

## Platform Coverage

| Platform | Hook Rules | Length | Best Formats |
|---|---|---|---|
| LinkedIn | Scroll-stopping first line, no "excited to share" | 800-1300 chars | Contrarian, Data Drop, Story |
| Twitter/X | Hook = entire post | 240 chars / threads | Prediction, Contradiction, Number |
| Instagram | First line before "more" | 125-500 chars | Story, Visual-forward, Save-worthy |
| Email | Trigger in subject line (6-8 words) | 150-600 words | PAS, curiosity gap, single CTA |
| Blog | Keyword + power word + promise | 1,500-2,500 words | Ultimate guide, Data-driven, How-to |

→ Full rules: [`docs/platform-guide.md`](docs/platform-guide.md)

---

## Built On

This skill is powered by:
- **Claude Code** (Anthropic) — AI execution engine
- **XPOZ MCP Connector** — social media data (Twitter, Instagram)
- **Firecrawler API** — website crawling
- **WebSearch** — real-time trend intelligence

The psychology framework is built on research from:
Kahneman, Cialdini, Tversky, Fogg, Deci & Ryan, Petty & Cacioppo, and the broader behavioral economics + neuromarketing literature.

---

## License

MIT License — free to use, modify, and distribute. See [`LICENSE`](LICENSE).

---

## Made by Grovio

[Grovio](https://grovio.ai) is an AI-powered marketing execution platform for startups and brands.

> "We don't just write content. We engineer behavior."

---

*If this skill helped you — star the repo. If it generated something exceptional — share the output and tag us.*
