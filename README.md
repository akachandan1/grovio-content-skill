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

## Architecture: Master Orchestrator + 13 Specialist Sub-Skills

The master skill detects your content type and activates the right specialist engine — each with deep, format-native knowledge.

```
/grovio-content  ←── Master Orchestrator
    │                 Brand intelligence + brand memory + auto-routing
    │
    ├── /grovio-social        ←── Social posts, threads, carousels
    │                              LinkedIn · Twitter/X · Instagram · Threads
    │                              Brand voice vs Founder voice distinction
    │
    ├── /grovio-ads           ←── Paid advertising copy
    │                              Google Search · Meta · LinkedIn Ads · YouTube
    │                              TOF / MOF / BOF / Retargeting logic
    │
    ├── /grovio-email         ←── Email & newsletter content
    │                              Cold outreach · Nurture sequences · Newsletters
    │                              Welcome · Re-engagement · Conversion emails
    │
    ├── /grovio-video         ←── Video scripts
    │                              Reels · TikTok · YouTube Shorts · LinkedIn Video
    │                              YouTube long-form · Pre-roll (timestamp format)
    │
    ├── /grovio-meme          ←── Memes & viral content
    │                              Classic format library · Text-only viral
    │                              Trend-jacking · Brand-meme voice calibration
    │
    ├── /grovio-seo           ←── Blog, pillar pages & GEO content
    │                              Blog posts · Pillar pages · Comparison posts
    │                              GEO optimization for AI search citation
    │
    ├── /grovio-landing       ←── Landing page & conversion copy
    │                              Hero sections · Full landing pages
    │                              CTA hierarchy · Pricing page psychology
    │
    ├── /grovio-repurpose     ←── Cross-channel content adaptation
    │                              Blog → 8 formats · Video → clips
    │                              Content multiplier without copy-paste
    │
    ├── /grovio-messaging     ←── WhatsApp, SMS & push notifications
    │                              WhatsApp Business sequences · SMS (160 char)
    │                              Push notifications · In-app messages
    │
    ├── /grovio-community     ←── Reddit, Discord, Product Hunt & community
    │                              Reddit posts (anti-promo rules enforced)
    │                              Product Hunt launch playbook · Discord format
    │
    ├── /grovio-analyze       ←── Content performance intelligence
    │                              Engagement pattern analysis · Hook audit
    │                              Trigger effectiveness map · Feedback loop
    │
    ├── /grovio-pr            ←── Press releases & earned media
    │                              Press releases · Media pitch emails
    │                              Byline pitches · Podcast pitches
    │
    ├── /grovio-brand-memory  ←── Persistent brand intelligence
    │                              Save/load brand profiles across sessions
    │                              Skip re-crawling · Brand history log
    │
    ├── /grovio-voc           ←── Voice of Customer intelligence
    │                              Mine G2/Capterra/Reddit/reviews for customer language
    │                              Pain language → outcome language → objection language
    │                              40-70% conversion lift from customer-derived copy
    │
    ├── /grovio-campaign      ←── Multi-channel campaign orchestration
    │                              Ignition → Activation → Close phases
    │                              Channel sequencing logic (PR first, organic before paid)
    │                              Full asset production list + metrics dashboard
    │
    └── /grovio-strategy      ←── Content strategy & 90-day roadmap
                                   Content pillar map (3–5 owned topics)
                                   Category Entry Point matrix (Byron Sharp)
                                   Competitor whitespace · Channel strategy by stage
                                   Week-by-week 90-day roadmap + priority stack
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
| `blog`, `seo`, `pillar`, `article`, `geo` | blog, SEO, GEO, long-form, pillar page | **grovio-seo** |
| `landing`, `hero`, `cta`, `conversion` | landing page, hero copy, CTA, pricing | **grovio-landing** |
| `repurpose`, `adapt`, `remix` | repurpose, adapt, transform, reformat | **grovio-repurpose** |
| `whatsapp`, `sms`, `push`, `messaging` | WhatsApp, SMS, push notification | **grovio-messaging** |
| `reddit`, `discord`, `producthunt`, `community` | Reddit, Discord, Product Hunt, community | **grovio-community** |
| `analyze`, `audit`, `performance` | content audit, performance, what's working | **grovio-analyze** |
| `pr`, `press`, `media`, `pitch` | press release, media pitch, byline | **grovio-pr** |
| `brand-memory`, `memory` | save brand, load brand, brand profile | **grovio-brand-memory** |
| `voc`, `voice-of-customer`, `reviews` | customer language, review mining, VoC | **grovio-voc** |
| `campaign`, `launch`, `multi-channel` | product launch, campaign orchestration | **grovio-campaign** |
| `strategy`, `roadmap`, `pillars` | content strategy, 90-day roadmap | **grovio-strategy** |

**Goal keyword auto-detection:** The master skill reads your goal text and routes correctly even if the platform argument is ambiguous.

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

### `/grovio-seo` — Blog, Pillar Pages & GEO Content
- **Formats:** Blog post (1,200-2,500w) · Pillar page (2,500-5,000w) · Comparison post · Listicle · FAQ/glossary
- **GEO optimization:** Answer-first structure for AI citation (ChatGPT, Perplexity, Google AI Overviews)
- **Keyword brief:** Volume, difficulty, SERP intent, gap to exploit, secondary keywords
- **Content cluster strategy:** Pillar + 5-8 cluster posts with internal linking map
- **SEO checklist:** Per-article verification of keyword placement, schema, links

### `/grovio-landing` — Landing Page & Conversion Copy
- **Assets:** Hero section · Full landing page · Pricing page · Feature page · Coming soon/waitlist
- **Hero formula:** H1 (outcome) + Sub-headline + Primary CTA + Secondary CTA + Social proof signal
- **CTA psychology:** First-person possessive, verb-forward, friction reduction
- **Pricing psychology:** Decoy pricing, anchoring, annual/monthly toggle, risk removal placement
- **A/B test recommendations:** Top 2 elements to split test per page

### `/grovio-repurpose` — Cross-Channel Content Adaptation
- **Source formats:** Blog post, video, podcast, newsletter, Twitter thread, case study, data/research
- **Output formats:** LinkedIn post, Twitter thread, newsletter section, video script, carousel, TikTok, email story, FAQ
- **Content multiplier:** 1 blog post → 8 pieces of content (social + email + video + evergreen)
- **Platform-native rules:** Rewrite logic per platform, not resize logic

### `/grovio-messaging` — WhatsApp, SMS & Push Notifications
- **WhatsApp:** Promotional, transactional, conversational sequences (1,024 char)
- **SMS:** Marketing and transactional (160 char — character count enforced)
- **Push notifications:** Title (50 char) + Body (100 char) with CTR-optimized formulas
- **In-app messages:** Banner and modal formats with "help not marketing" principle
- **Sequence architecture:** WhatsApp onboarding (5-message sequence with day/trigger map)

### `/grovio-community` — Reddit, Discord & Product Hunt
- **Reddit:** Anti-promotional rules enforced · Community-native post types · Subreddit selection guide
- **Product Hunt:** Launch day playbook · Tagline (60 char) · Maker first comment · Supporter outreach
- **Discord:** Announcement format with Discord markdown · Channel strategy
- **Indie Hackers / Hacker News:** Transparency-first formats · Building-in-public post structure
- **Comment strategy:** Building authority through comments, not just posts

### `/grovio-analyze` — Content Performance Intelligence
- **Engagement pattern analysis:** Top 20% vs bottom 20% performer extraction
- **Hook effectiveness audit:** Which hook types convert per platform
- **Trigger effectiveness map:** Which psychological triggers are actually working
- **Email performance audit:** Subject line patterns, CTR analysis, unsubscribe triggers
- **Feedback loop protocol:** Collect → Sort → Pattern → Insight → Test → Feed forward

### `/grovio-pr` — Press Releases & Earned Media
- **News hook tiers:** Tier 1 (data) → Tier 4 (milestone) — tier assessment before writing
- **Press release:** Lead paragraph structure, quote rules, embargo strategy
- **Media pitch email:** 5-7 sentences, personalized line 1, journalist-first angle
- **Contributed article / byline pitch:** Outline format for trade publication pitches
- **Podcast pitch:** Guest pitch email with 3 episode title options
- **Coverage likelihood scoring:** Per asset, per publication

### `/grovio-brand-memory` — Persistent Brand Intelligence
- **Save:** Store complete brand profile to `~/.claude/brands/[slug]/brand-memory.md`
- **Load:** Retrieve profile in future sessions — skip web re-crawl
- **Staleness detection:** Flags profiles >90 days old for refresh
- **Campaign log:** Automatic history of all content generated through the system
- **Compare:** Side-by-side brand DNA comparison for competitive positioning

### `/grovio-voc` — Voice of Customer Intelligence
- **Sources:** G2, Capterra, Trustpilot, Reddit, App Store, Product Hunt, support tickets
- **5 language layers:** Pain language → Desired outcome → Switching reasons → Objection language → Recommendation language
- **Deliverables:** Ready-to-use headline candidates, CTA candidates, objection copy blocks, competitor differentiation angles
- **Brand language audit:** Side-by-side table of what the brand says vs what customers say — with recommended swaps
- **Research backing:** Joanna Wiebe / Copy Hackers — customer language verbatim produces 40–70% conversion lift
- **Persistent storage:** Saved to `~/.claude/brands/[slug]/voc-dictionary.md` for reuse across sessions

### `/grovio-campaign` — Multi-Channel Campaign Orchestration
- **Campaign types:** Product launch · Feature launch · Awareness · Lead gen · Event · Re-engagement · Content series
- **3-phase architecture:** Ignition (PR first → organic social → warm email) → Activation (landing page → paid → nurture → retargeting) → Close (urgency posts → final email → hard retargeting)
- **Channel sequencing logic:** Why PR fires first, organic before paid, warm list before cold — each with strategic rationale
- **Full asset production list:** Priority 1–4 assets with the correct `/grovio-*` skill to invoke for each
- **Messaging evolution:** How the core message must shift across each phase as audience awareness level changes
- **Metrics dashboard:** Per-phase KPIs and minimum viable result definition

### `/grovio-strategy` — Content Strategy & 90-Day Roadmap
- **Content pillar map:** 3–5 owned topic areas with audience relevance, business link, whitespace, SEO opportunity
- **Category Entry Point matrix:** All situations/moments where audience enters the category (Byron Sharp)
- **Competitor whitespace analysis:** What competitors own vs what's unclaimed — per named competitor
- **JTBD alignment:** Functional + emotional + social job dimensions mapped to content types
- **Channel strategy by stage:** Early / Growth / Scale — Tier 1/2/3 channels with cadence and upgrade conditions
- **90-day roadmap:** Week-by-week plan with priority stack ("If you could only do 5 things, do these")
- **Brand/activation balance check:** Flags over-indexing on activation content (Binet & Field 60/40 rule)
- **Content → revenue logic map:** Every content type mapped to funnel role, leading metric, and lagging metric

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
│   ├── grovio-meme/
│   │   └── SKILL.md                     ← Memes + viral content
│   ├── grovio-seo/
│   │   └── SKILL.md                     ← Blog, pillar pages, GEO optimization
│   ├── grovio-landing/
│   │   └── SKILL.md                     ← Landing pages, hero copy, CTA hierarchy
│   ├── grovio-repurpose/
│   │   └── SKILL.md                     ← Cross-channel content adaptation
│   ├── grovio-messaging/
│   │   └── SKILL.md                     ← WhatsApp, SMS, push notifications
│   ├── grovio-community/
│   │   └── SKILL.md                     ← Reddit, Discord, Product Hunt
│   ├── grovio-analyze/
│   │   └── SKILL.md                     ← Content performance intelligence
│   ├── grovio-pr/
│   │   └── SKILL.md                     ← Press releases, media pitches
│   ├── grovio-brand-memory/
│   │   └── SKILL.md                     ← Persistent brand intelligence across sessions
│   ├── grovio-voc/
│   │   └── SKILL.md                     ← Voice of Customer mining (reviews → customer language)
│   ├── grovio-campaign/
│   │   └── SKILL.md                     ← Multi-channel campaign orchestration
│   └── grovio-strategy/
│       └── SKILL.md                     ← Content strategy, pillars, 90-day roadmap
│
├── docs/
│   ├── psychology-framework.md          ← Full 25 triggers + all frameworks reference
│   └── platform-guide.md               ← Platform-specific content rules
│
└── examples/
    └── duolingo-twitter/
        ├── README.md                    ← Context and walkthrough
        └── output.md                   ← Full generated output (55/60)
```

---

## Example Output

**Duolingo → Twitter Viral Content** (55/60 — 23/26 triggers fired):

> *you've been saying "i'll start tomorrow" for 47 days*
>
> *duo has been watching*
>
> *duo is patient*
>
> *duo is also keeping count*

**Cultural Hijack Template** (reusable engine discovered):

> *you watched 14 episodes of [K-drama] this week*
>
> *you have not done one duolingo lesson*
>
> *the main character would be so disappointed in you*

**Grovio AI → LinkedIn Thought Leadership** (54/60 — full psychology stack test):

> *I wasted 800 hours last year doing "marketing."*
>
> *None of it was actually marketing. It was coordination.*

→ Full output with all 5 variants + annotations: [`examples/duolingo-twitter/output.md`](examples/duolingo-twitter/output.md)

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
