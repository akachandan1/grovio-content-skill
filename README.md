# NuroMark Skills

> **The world's most psychologically advanced brand content engine for Claude Code.**
> Combines consumer psychology, behavioral economics, persuasion science, and neuroscience research to generate content that engineers behavior — not just publishes words.

---

## What This Is

A Claude Code skill system that transforms any brand URL into a full content intelligence engine — across every content format and channel.

Give it a brand website + channel + goal. It will:

1. **Crawl the brand's website** — extract positioning, voice, vocabulary, differentiators
2. **Pull their social media history** — audit what worked, what didn't, which triggers they're missing
3. **Map competitor whitespace** — find angles nobody is owning
4. **Build an audience psychology profile** — ELM involvement, Fogg model, top 5 triggers
5. **Gather real-time trend intelligence** — trending angles, saturation alerts, data points
6. **Route to the right specialist engine** — social, ads, email, video, or meme
7. **Generate 5+ content variants** — each with a different psychological entry point
8. **Score every variant on 110 points** — 60 psychological + 50 neuroscience (NuroMark)
9. **Produce a ranked output package** — #1 Publish / #2 A/B / #3 Reserve + optimization notes

**The output is not content. It's behavior-engineered content with a full psychological and neuroscience audit.**

---

## The Operating Principle

Every piece of content must simultaneously hit three brain systems:

| Brain System | Needs | Content Layer |
|---|---|---|
| Emotional brain (Limbic) | Feeling, story, identity | Narrative + emotional trigger |
| Social brain (Prefrontal) | Belonging, proof, norms | Social trigger + tribe signal |
| Rational brain (Neocortex) | Logic, value, evidence | Utility + credibility |

Hit 1 = ignored. Hit 2 = engaged. Hit all 3 = shared.

---

## Architecture: Master Orchestrator + 22 Specialist Skills

```
/content  ←── Master Orchestrator
    │          Brand intelligence + brand memory + auto-routing
    │
    ├── /social        ←── Social posts, threads, carousels
    │                       LinkedIn · Twitter/X · Instagram · Threads
    │
    ├── /ads           ←── Paid advertising copy
    │                       Google Search · Meta · LinkedIn Ads · YouTube
    │
    ├── /email         ←── Email & newsletter content
    │                       Cold outreach · Nurture sequences · Newsletters
    │
    ├── /video         ←── Video scripts
    │                       Reels · TikTok · YouTube Shorts · YouTube long-form
    │
    ├── /meme          ←── Memes & viral content
    │                       Classic format library · Text-only viral · Trend-jacking
    │
    ├── /seo           ←── Blog, pillar pages & GEO content
    │                       Blog posts · Pillar pages · GEO optimization for AI search
    │
    ├── /landing       ←── Landing page & conversion copy
    │                       Hero sections · Full landing pages · Pricing psychology
    │
    ├── /repurpose     ←── Cross-channel content adaptation
    │                       1 piece → 8 formats · Platform-native rewrite logic
    │
    ├── /messaging     ←── WhatsApp, SMS & push notifications
    │                       WhatsApp Business · SMS (160 char) · Push · In-app
    │
    ├── /community     ←── Reddit, Discord, Product Hunt & community
    │                       Reddit (anti-promo rules enforced) · PH launch playbook
    │
    ├── /analyze       ←── Content performance intelligence
    │                       Engagement patterns · Hook audit · Trigger effectiveness
    │
    ├── /pr            ←── Press releases & earned media
    │                       Press releases · Media pitches · Podcast pitches
    │
    ├── /brand-memory  ←── Persistent brand intelligence across sessions
    │                       Save/load brand profiles · Skip re-crawling
    │
    ├── /voc           ←── Voice of Customer intelligence
    │                       Mine G2/Reddit/reviews · Customer language → copy
    │
    ├── /campaign      ←── Multi-channel campaign orchestration
    │                       Ignition → Activation → Close phases
    │
    ├── /strategy      ←── Content strategy & 90-day roadmap
    │                       Content pillars · CEP matrix · Channel strategy
    │
    ├── /hook          ←── Hook-first content specialist
    │                       10+ hook variants · Scored by type · Platform-fit ranked
    │
    ├── /persona       ←── Audience persona builder
    │                       ICP with psychographic depth · JTBD · Trigger sensitivity map
    │
    ├── /brief         ←── Content brief generator
    │                       Structured briefs for writers, agencies, or team handoff
    │
    ├── /ab-test       ←── A/B test design specialist
    │                       Experiment design · Hypothesis · Decision rules
    │
    ├── /gtm           ←── Go-to-market launch content
    │                       Full launch kit: Day -14 → Day 0 → Day +14
    │
    └── /nuromark      ←── Neuroscience scoring engine
                            TRIBE v2 research (Meta FAIR) · 50-pt NeuroScore
                            Auto-invokes on all content-generating skills
```

---

## Quick Start

### Step 1 — Install Claude Code

```bash
npm install -g @anthropic-ai/claude-code
claude --version
```

> Full setup guide at [claude.ai/code](https://claude.ai/code)

---

### Step 2 — Install the Skills

```bash
git clone https://github.com/akachandan1/nuromark-skills.git
cp -r nuromark-skills/skills/. ~/.claude/skills/
```

No configuration, no API keys beyond your Claude Code session, no package installs.

**Verify:**
```bash
ls ~/.claude/skills/
# Should show: content  social  ads  email  video  meme  seo  landing  repurpose
#              messaging  community  analyze  pr  brand-memory  voc  campaign
#              strategy  hook  persona  brief  ab-test  gtm  nuromark  system
```

---

### Step 3 — Run Your First Command

```bash
cd ~/your-project
claude
```

Then type a slash command:

```
/content https://stripe.com linkedin thought-leadership
```

Claude will crawl Stripe, audit their content history, map whitespace, generate 5 variants, and score every variant across 110 points.

---

### Usage

#### Master Orchestrator (recommended)

```
/content <brand_url> <platform_or_type> <goal> [--voice brand|founder]
```

```
/content https://stripe.com linkedin thought-leadership
/content https://notion.so twitter product-launch --voice founder
/content https://linear.app newsletter onboarding-sequence
/content https://grovio.ai meta-ads free-trial-campaign
/content https://figma.com meme design-culture
/content https://vercel.com reels product-demo --voice founder
```

**`--voice` flag:** Switches between brand account voice (formal, social-proof heavy) and founder personal account voice (story-driven, first-person, 3–5x more organic reach on LinkedIn/Twitter).

#### Invoke a Specialist Directly

```
/social    <url> <platform> <goal> [--voice brand|founder]
/ads       <url> <platform> <goal>
/email     <url> <type>     <goal>
/video     <url> <platform> <goal>
/hook      <topic> <platform> [--type data|contrarian|story|question|bold]
/persona   <brand_url> [--save <name>] [--load <name>]
/brief     <topic> <platform> <goal> [--format notion|doc|email]
/ab-test   <variant-A> <variant-B> [--metric engagement|clicks|conversions]
/gtm       <product_name> <launch_date> <brand_url> [--type feature|product|waitlist|beta]
/nuromark  <content> [--platform <platform>]
```

---

### Iterating on Output

After a skill runs, keep the conversation going:

```
"Give me variant 3 rewritten with a stronger hook"
"Redo this as a founder confession instead of a data drop"
"Now adapt the #1 variant for Twitter as a 7-tweet thread"
"Generate 3 more variants focused on the fear trigger"
```

Claude remembers all brand intelligence from the skill run — follow-up prompts are instant, no re-crawling needed.

---

## Routing Table

| Platform / Type | Goal Signals | Skill Activated |
|---|---|---|
| `linkedin`, `twitter`, `instagram`, `threads` | post, thread, carousel, thought-leadership | **/social** |
| `linkedin-ad`, `meta-ad`, `google-ad`, `youtube-ad`, `paid` | ad copy, campaign, CPC, conversion | **/ads** |
| `email`, `newsletter`, `nurture`, `sequence`, `drip` | email, newsletter, onboarding, re-engagement | **/email** |
| `reels`, `tiktok`, `youtube-shorts`, `video` | video, script, reel, short-form | **/video** |
| `meme`, `viral`, `meme-content` | meme, viral, humor, trending format | **/meme** |
| `blog`, `seo`, `pillar`, `article`, `geo` | blog, SEO, GEO, long-form, pillar page | **/seo** |
| `landing`, `hero`, `cta`, `conversion` | landing page, hero copy, CTA, pricing | **/landing** |
| `repurpose`, `adapt`, `remix` | repurpose, adapt, transform, reformat | **/repurpose** |
| `whatsapp`, `sms`, `push`, `messaging` | WhatsApp, SMS, push notification | **/messaging** |
| `reddit`, `discord`, `producthunt`, `community` | Reddit, Discord, Product Hunt, community | **/community** |
| `analyze`, `audit`, `performance` | content audit, performance, what's working | **/analyze** |
| `pr`, `press`, `media`, `pitch` | press release, media pitch, byline | **/pr** |
| `brand-memory`, `memory` | save brand, load brand, brand profile | **/brand-memory** |
| `voc`, `voice-of-customer`, `reviews` | customer language, review mining, VoC | **/voc** |
| `campaign`, `launch`, `multi-channel` | product launch, campaign orchestration | **/campaign** |
| `strategy`, `roadmap`, `pillars` | content strategy, 90-day roadmap | **/strategy** |
| `hook` | hook variants, first line, scroll-stop | **/hook** |
| `persona`, `icp`, `audience` | audience profile, psychographic, JTBD | **/persona** |
| `brief`, `handoff` | content brief, writer brief, agency brief | **/brief** |
| `ab-test`, `experiment`, `split-test` | A/B test design, hypothesis, experiment | **/ab-test** |
| `gtm`, `launch`, `product-launch` | go-to-market, launch kit, waitlist | **/gtm** |

---

## The 110-Point Scoring System

Every generated variant is scored on two layers:

### Layer 1 — Psychological Score (60 pts)

| Dimension | What It Measures |
|---|---|
| **Trigger Potency** | How powerfully are psychological triggers embedded? |
| **Emotional Resonance** | How strongly does it create an emotional response? |
| **Brand Voice Fidelity** | Does it sound unmistakably like this brand? |
| **Originality** | How fresh and differentiated is the angle? |
| **Utility** | How much practical value does the reader get? |
| **Virality Potential** | How likely is it to be shared, saved, or quoted? |

### Layer 2 — NeuroScore via NuroMark (50 pts)

Built on TRIBE v2 research (Meta FAIR, arXiv:2507.22229) — an fMRI brain encoding model trained on 700+ volunteers:

| Dimension | Brain Region | What It Measures |
|---|---|---|
| **D1 — Narrative Coherence** | Default Mode Network | Story structure activating episodic memory |
| **D2 — Emotional Valence** | Amygdala + Insula | Emotional charge + loss aversion weighting |
| **D3 — Social Salience** | TPJ + Anterior Insula | Social proof triggering conformity circuits |
| **D4 — Attention Architecture** | Prefrontal Cortex | Structural hooks sustaining attention |
| **D5 — Multimodal Alignment** | MTG + Associative Cortex | Text + visual concept coherence |

### Score Thresholds

| Combined Score | Decision |
|---|---|
| ≥90 / 110 | Publish |
| 75–89 / 110 | A/B test |
| 60–74 / 110 | Optimize |
| <60 / 110 | Mandatory rewrite |

NuroMark auto-invokes on all content-generating skills — no manual step needed.

---

## Quality Gates (All Skills)

Before finalizing any output, every skill runs these checks:

- **3-Brain Test:** Emotional + Social + Rational brain all activated?
- **Hook Test:** First line stops scroll without context?
- **Identity Signal Test:** "Sharing this tells the world I am ___" — completable?
- **Fogg Test:** Motivation + Ability + Trigger all present?
- **Brand Fidelity Test:** Remove brand name — still sounds like them?
- **Format Test:** Native to the channel, not just resized?

---

## New Skills (v2)

### `/hook` — Hook-First Content Specialist
Generates 10+ hook variants for any topic across 10 types: data drop, contrarian, confession, curiosity gap, bold claim, prediction, fear, identity signal, story opener, question. Each scored on a 40-point matrix (scroll-stop, trigger potency, tension, platform fit).

### `/persona` — Audience Persona Builder
Builds a full ICP with psychographic depth: Jobs-to-be-Done (functional/emotional/social), trigger sensitivity map (Tier 1/2/3), and content implication guide. Saves to `~/.claude/brands/[brand]/personas/[name].md` for reuse across all skills.

### `/brief` — Content Brief Generator
Creates structured content briefs for handoff to writers, agencies, or team members. 11-section output: goal, audience, angle, hook options, key messages, proof points, format spec, brand voice guardrails, references, success criteria. Formats: Notion, doc, email, Airtable.

### `/ab-test` — A/B Test Design Specialist
Three modes: (1) design a test from two variants, (2) recommend what to test for a content goal, (3) build a full experiment plan. Outputs: variable isolation, hypothesis, metric, sample size estimate, decision rule, learning log.

### `/gtm` — Go-to-Market Launch Content
Full launch kit from Day -14 to Day +14. Covers: teaser posts, waitlist email, countdown, LinkedIn announcement, Twitter thread, Product Hunt copy, press release hook, milestone post, social proof, re-engagement. Launch psychology: tease (curiosity) → reveal (FOMO + awe) → validate (social proof).

### `/nuromark` — Neuroscience Scoring Engine
Standalone neuroscience-based content scorer. Applies findings from TRIBE v2 (Meta FAIR, arXiv:2507.22229) + supporting literature (Hasson DMN, Klucharev social proof, Loewenstein curiosity, Kahneman loss aversion). Scores 0–50 across 5 brain dimensions. Auto-invokes on all content skills — or call it directly on any content piece.

---

## The Psychology Engine

### Core Theories

| Theory | How It's Used |
|---|---|
| **Elaboration Likelihood Model (ELM)** | Routes content format based on audience involvement level |
| **Fogg Behavior Model** | Validates every variant has Motivation + Ability + Trigger |
| **Self-Determination Theory (SDT)** | Maps Autonomy / Competence / Relatedness needs |
| **Theory of Reasoned Action** | Ensures content shapes beliefs + social norms simultaneously |
| **Relationship Marketing Theory** | Designs for loyalty + emotional brand bonding |

### The 25 Psychological Triggers

**Social:** Social Proof · Authority · Liking · Unity · Bandwagon Effect

**Scarcity & Urgency:** Scarcity · Urgency · FOMO · Exclusivity

**Cognitive Bias:** Loss Aversion · Anchoring · Framing Effect · Availability Bias · Confirmation Bias · Cognitive Fluency

**Emotional:** Curiosity Gap · Surprise · Awe · Fear · Belonging

**Motivation:** Reciprocity · Commitment & Consistency · Progress Effect · Personalization · Identity Signaling

Full reference: [`skills/system/SYSTEM.md`](skills/system/SYSTEM.md)

---

## Repository Structure

```
nuromark-skills/
├── README.md
├── LICENSE
│
├── skills/
│   ├── system/
│   │   └── SYSTEM.md          ← Shared foundation: triggers, scoring, quality gates
│   ├── content/SKILL.md       ← Master orchestrator
│   ├── social/SKILL.md
│   ├── ads/SKILL.md
│   ├── email/SKILL.md
│   ├── video/SKILL.md
│   ├── meme/SKILL.md
│   ├── seo/SKILL.md
│   ├── landing/SKILL.md
│   ├── repurpose/SKILL.md
│   ├── messaging/SKILL.md
│   ├── community/SKILL.md
│   ├── analyze/SKILL.md
│   ├── pr/SKILL.md
│   ├── brand-memory/SKILL.md
│   ├── voc/SKILL.md
│   ├── campaign/SKILL.md
│   ├── strategy/SKILL.md
│   ├── hook/SKILL.md          ← New v2
│   ├── persona/SKILL.md       ← New v2
│   ├── brief/SKILL.md         ← New v2
│   ├── ab-test/SKILL.md       ← New v2
│   ├── gtm/SKILL.md           ← New v2
│   └── nuromark/SKILL.md      ← New v2 — neuroscience scorer
│
├── docs/
│   ├── psychology-framework.md
│   └── platform-guide.md
│
└── examples/
    └── duolingo-twitter/
        ├── README.md
        └── output.md
```

---

## Example Output

**Duolingo → Twitter Viral Content** (55/60 psychological — full NuroMark: 94/110):

> *you've been saying "i'll start tomorrow" for 47 days*
>
> *duo has been watching*
>
> *duo is patient*
>
> *duo is also keeping count*

**Grovio AI → LinkedIn Thought Leadership** (54/60):

> *I wasted 800 hours last year doing "marketing."*
>
> *None of it was actually marketing. It was coordination.*

→ Full output with all 5 variants + annotations: [`examples/duolingo-twitter/output.md`](examples/duolingo-twitter/output.md)

---

## Built On

- **Claude Code** (Anthropic) — AI execution engine
- **TRIBE v2** (Meta FAIR, arXiv:2507.22229) — neuroscience scoring foundation
- **WebFetch** — website crawling
- **WebSearch** — real-time trend intelligence

Psychology framework built on research from: Kahneman, Cialdini, Tversky, Fogg, Deci & Ryan, Petty & Cacioppo, Hasson, Klucharev, Loewenstein, and the broader behavioral economics + neuromarketing literature.

---

## License

MIT License — free to use, modify, and distribute. See [`LICENSE`](LICENSE).

---

*If this skill helped you — star the repo. If it generated something exceptional — share the output.*
