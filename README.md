# Grovio Content Skill

> **The world's most psychologically advanced brand content engine for Claude Code.**
> Combines consumer psychology, behavioral economics, persuasion science, and neuromarketing to generate content that engineers behavior — not just publishes words.

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
8. **Score every variant on 6 dimensions** — composite score out of 60
9. **Produce a ranked output package** — #1 Publish / #2 A/B / #3 Reserve + optimization notes

**The output is not content. It's behavior-engineered content with a full psychological audit.**

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

## Architecture: Path B — Master Orchestrator + Specialist Sub-Skills

Version 2 introduces a **routing architecture**. The master skill detects your content type and activates the right specialist engine — each with deep, format-native knowledge.

```
/grovio-content  ←── Master Orchestrator
    │                 Brand intelligence + auto-routing
    │
    ├── /grovio-social   ←── Social posts, threads, carousels
    │                        LinkedIn · Twitter/X · Instagram · Threads
    │                        Brand voice vs Founder voice distinction
    │
    ├── /grovio-ads      ←── Paid advertising copy
    │                        Google Search · Meta · LinkedIn Ads · YouTube
    │                        TOF / MOF / BOF / Retargeting logic
    │                        Platform character limits enforced
    │
    ├── /grovio-email    ←── Email & newsletter content
    │                        Cold outreach · Nurture sequences · Newsletters
    │                        Welcome · Re-engagement · Conversion emails
    │
    ├── /grovio-video    ←── Video scripts
    │                        Reels · TikTok · YouTube Shorts · LinkedIn Video
    │                        YouTube long-form · Pre-roll
    │                        Timestamp-by-timestamp format
    │
    └── /grovio-meme     ←── Memes & viral content
                             Classic format library (Drake, Expanding Brain, etc.)
                             Text-only viral posts · Trend-jacking framework
                             Brand-meme voice calibration
```

---

## Quick Start

### Step 1 — Install Claude Code

Claude Code is Anthropic's official CLI. It runs in your terminal and is what powers these skills.

```bash
# Install via npm
npm install -g @anthropic-ai/claude-code

# Verify installation
claude --version
```

> **New to Claude Code?** Full setup guide at [claude.ai/code](https://claude.ai/code)

---

### Step 2 — Install the Skills

```bash
# Clone this repo
git clone https://github.com/akachandan1/grovio-content-skill.git

# Copy all 6 skills to your Claude skills directory
cp -r grovio-content-skill/skills/. ~/.claude/skills/
```

That's it. No configuration, no API keys beyond your Claude Code session, no package installs.

**Verify the skills are installed:**
```bash
ls ~/.claude/skills/ | grep grovio
# Should show: grovio-content  grovio-social  grovio-ads  grovio-email  grovio-video  grovio-meme
```

---

### Step 3 — Open Claude Code

```bash
# Navigate to your project directory (or anywhere)
cd ~/your-project

# Launch Claude Code
claude
```

You'll see the Claude Code prompt. Skills are automatically available — no additional setup needed.

---

### Step 4 — Run Your First Command

Type a slash command directly in the Claude Code prompt:

```
/grovio-content https://stripe.com linkedin thought-leadership
```

Claude will:
1. Detect the content type (LinkedIn post → routes to `grovio-social`)
2. Crawl the Stripe website and extract brand intelligence
3. Pull their Twitter/social history and audit past content
4. Map competitor whitespace
5. Generate 5 LinkedIn variants with full psychological scoring
6. Output a ranked package: #1 Publish / #2 A/B / #3 Reserve

---

### How Skills Work in Claude Code

Claude Code skills are **prompt files** stored in `~/.claude/skills/`. When you type `/skill-name`, Claude Code loads that skill's instructions and executes them in the conversation.

```
~/.claude/skills/
└── grovio-content/
    └── SKILL.md    ← Claude reads this when you type /grovio-content
```

**Key things to know:**
- Skills activate automatically — just type the slash command
- No separate servers or processes to run
- Skills can call web tools (fetch URLs, search the web) during execution
- Output appears directly in your Claude Code session
- You can type follow-up messages to refine or iterate on any output

---

### Usage

#### Option A — Master Orchestrator (recommended for new users)

The master skill auto-detects your content type and routes to the right specialist:

```
/grovio-content <brand_url> <platform_or_type> <goal> [--voice brand|founder]
```

```
/grovio-content https://stripe.com linkedin thought-leadership
/grovio-content https://notion.so twitter product-launch --voice founder
/grovio-content https://linear.app newsletter onboarding-sequence
/grovio-content https://grovio.ai meta-ads free-trial-campaign
/grovio-content https://figma.com meme design-culture
/grovio-content https://vercel.com reels product-demo --voice founder
```

**What `--voice` does:** Switches between brand account voice (formal, social-proof heavy) and founder personal account voice (story-driven, first-person, 3-5x more organic reach on LinkedIn/Twitter).

#### Option B — Invoke a Specialist Directly

If you already know what you need, skip routing:

```
/grovio-social <url> <platform> <goal> [--voice brand|founder]
/grovio-ads    <url> <platform> <goal>
/grovio-email  <url> <type>     <goal>
/grovio-video  <url> <platform> <goal>
/grovio-meme   <url> <platform> <topic>
```

**Examples:**
```
/grovio-social https://linear.app linkedin thought-leadership --voice founder
/grovio-ads https://grovio.ai google-ad free-trial-campaign
/grovio-email https://notion.so newsletter weekly-digest
/grovio-video https://figma.com reels product-demo
/grovio-meme https://vercel.com twitter devtools-culture
```

---

### Iterating on Output

After a skill runs, you can keep the conversation going:

```
# Ask for a specific variant
"Give me variant 3 rewritten with a stronger hook"

# Change the angle
"Redo this as a founder confession instead of a data drop"

# Adapt to another platform
"Now adapt the #1 variant for Twitter as a 7-tweet thread"

# Request more content
"Generate 3 more variants focused on the fear trigger"
```

Claude remembers all the brand intelligence from the skill run — follow-up prompts are instant, no re-crawling needed.

---

## Routing Table

| Platform / Type | Goal Signals | Specialist Activated |
|---|---|---|
| `linkedin`, `twitter`, `instagram`, `threads` | post, thread, carousel, thought-leadership | **grovio-social** |
| `linkedin-ad`, `meta-ad`, `google-ad`, `youtube-ad`, `paid` | ad copy, campaign, CPC, conversion | **grovio-ads** |
| `email`, `newsletter`, `nurture`, `sequence`, `drip` | email, newsletter, onboarding, re-engagement | **grovio-email** |
| `reels`, `tiktok`, `youtube-shorts`, `video` | video, script, reel, short-form | **grovio-video** |
| `meme`, `viral`, `meme-content` | meme, viral, humor, trending format | **grovio-meme** |

**Goal keyword auto-detection:** The master skill also reads your goal text — "ad copy", "newsletter", "video script", "meme" — and routes correctly even if the platform argument is ambiguous.

---

## The `--voice` Flag (Social Content)

One of the most important distinctions in social content:

| Flag | When to Use | Trigger Stack | Reach |
|---|---|---|---|
| `--voice brand` | Company page, product news, formal announcements | Social Proof, Authority, Bandwagon | Standard |
| `--voice founder` | Thought leadership, building-in-public, stories, opinions | Liking, Reciprocity, Identity Signaling | 3-5x higher organic reach on LinkedIn/Twitter |

**Auto-detect rule:** Goals containing "thought-leadership", "opinion", "building-in-public", or "story" default to founder voice unless overridden.

---

## Specialist Capabilities

### `/grovio-social` — Social Content
- **Platforms:** LinkedIn · Twitter/X · Instagram · Threads
- **Formats:** Single post · Thread · Carousel (slide-by-slide) · Story caption
- **Voice:** Brand account vs Founder personal account (separate logic)
- **Frameworks:** Contrarian · Data Drop · Founder Story · Framework Post · Prediction
- **Posting guide:** Best days, times, and format bias per platform

### `/grovio-ads` — Ad Copy
- **Google Search:** Enforces 30-char headline / 90-char description limits, A/B variants per position
- **Meta (Facebook/Instagram):** 125-char primary text hook, headline, description, CTA button text
- **LinkedIn Ads:** Sponsored content + Message Ads (InMail), role-specific personalization
- **YouTube:** Pre-roll (15-30 sec) and bumper (6 sec non-skippable) scripts
- **Funnel logic:** TOF · MOF · BOF · Retargeting — each with different trigger stacks
- **Always outputs:** 3 primary variants + retargeting variant + objection-handling variant

### `/grovio-email` — Email & Newsletter
- **Email vs Newsletter distinction:** Treated as fundamentally different products with different logic
- **Email types:** Cold outreach · Welcome · Nurture sequence (5-7 emails) · Conversion · Re-engagement (3-step)
- **Newsletter:** Digest format with Big Idea + Curated Links + Resource + Personal close
- **Subject lines:** Always provides A/B variant (curiosity-gap vs benefit-forward)
- **Sequence architecture:** Day-by-day map with job + CTA per email

### `/grovio-video` — Video Scripts
- **Short-form:** Reels, TikTok, YouTube Shorts, LinkedIn Video — timestamp-by-timestamp
- **Format:** `[SECOND X-Y] VISUAL: / SPOKEN: / ON-SCREEN TEXT:` — writes for audio-off first
- **YouTube long-form:** Full script with open loop hook, retention checkpoints, pattern interrupt notes
- **Outputs:** Primary script + 2-3 hook A/B variants + thumbnail concepts + production notes
- **Retention strategy:** Re-hook moments, pattern interrupts, completion rate optimization

### `/grovio-meme` — Memes & Viral Content
- **Format library:** Drake · Expanding Brain · Distracted Boyfriend · This Is Fine · Surprised Pikachu · Two Buttons · Expectation vs Reality · and more
- **Text-only viral:** Progression posts, "Nobody:" format, "The thing everyone feels but nobody says"
- **Trend-jacking:** Evaluation framework (velocity + brand fit + risk + execution time)
- **Brand-meme calibration:** Maps voice archetype to appropriate meme styles
- **Universal rule:** If you have to explain the meme, it failed. Start over.

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

→ Full reference: [`docs/psychology-framework.md`](docs/psychology-framework.md)

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

## Quality Gates (All Specialists)

Before finalizing any output, every specialist runs these checks:

- **3-Brain Test:** Emotional + Social + Rational brain all activated?
- **Hook Test:** First line stops scroll without context?
- **Identity Signal Test:** "Sharing this tells the world I am ___" — completable?
- **Fogg Test:** Motivation + Ability + Trigger all present?
- **Brand Fidelity Test:** Remove brand name — still sounds like them?
- **Format Test:** Native to the channel, not just resized?

---

## Repository Structure

```
grovio-content-skill/
├── README.md
├── LICENSE                              ← MIT
│
├── skills/                              ← Install these to ~/.claude/skills/
│   ├── grovio-content/
│   │   └── SKILL.md                     ← Master orchestrator (brand intelligence + routing)
│   ├── grovio-social/
│   │   └── SKILL.md                     ← Social posts, threads, carousels
│   ├── grovio-ads/
│   │   └── SKILL.md                     ← Ad copy (Google, Meta, LinkedIn, YouTube)
│   ├── grovio-email/
│   │   └── SKILL.md                     ← Email sequences + newsletters
│   ├── grovio-video/
│   │   └── SKILL.md                     ← Video scripts (Reels, TikTok, YouTube)
│   └── grovio-meme/
│       └── SKILL.md                     ← Memes + viral content
│
├── docs/
│   ├── psychology-framework.md          ← Full 25 triggers + all frameworks reference
│   └── platform-guide.md               ← Platform-specific content rules
│
└── examples/
    └── maruti-suzuki-linkedin/
        ├── README.md                    ← Context and walkthrough
        └── output.md                   ← Full generated output (49/60)
```

---

## Example Output

**Maruti Suzuki → LinkedIn Thought Leadership** (49/60):

> *India will not electrify the way the headlines say it will.*
>
> *That's not pessimism. That's what you learn when 29 million Indian families trust you with their first car.*
>
> *→ 72% of India's EV sales happen in just 10 cities*
> *→ CNG outsells EVs in India 4:1*
> *→ Public charging covers less than 12% of India's districts...*

**Grovio AI → LinkedIn Thought Leadership** (52/60 — highest ever produced):

> *Most companies are using AI to do old marketing faster.*
>
> *That's the wrong race.*

→ Full outputs: [`examples/maruti-suzuki-linkedin/output.md`](examples/maruti-suzuki-linkedin/output.md)

---

## Built On

- **Claude Code** (Anthropic) — AI execution engine
- **XPOZ MCP Connector** — social media data (Twitter, Instagram)
- **WebFetch** — website crawling
- **WebSearch** — real-time trend intelligence

Psychology framework built on research from: Kahneman, Cialdini, Tversky, Fogg, Deci & Ryan, Petty & Cacioppo, and the broader behavioral economics + neuromarketing literature.

---

## License

MIT License — free to use, modify, and distribute. See [`LICENSE`](LICENSE).

---

## Made by Grovio

[Grovio](https://grovio.ai) is an AI-native marketing operating system for startups and brands.

> "We don't just write content. We engineer behavior."

---

*If this skill helped you — star the repo. If it generated something exceptional — share the output and tag us.*
