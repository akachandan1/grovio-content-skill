# Psychology Framework Reference

> The complete research foundation behind the Grovio Content Skill scoring and generation engine.

This document covers everything the skill uses to generate and evaluate content. Understanding this framework will help you interpret scores, improve outputs, and adapt the skill to your use case.

---

## The Three-Brain Model

Every piece of content must hit three neurological systems simultaneously:

| Brain System | Scientific Basis | What It Needs | Content Layer |
|---|---|---|---|
| **Emotional brain** (Limbic) | Emotional memory, fast response | Feeling, story, personal relevance | Narrative + emotional trigger |
| **Social brain** (Prefrontal cortex) | Social cognition, norm processing | Belonging, proof, what others think | Social trigger + tribe signal |
| **Rational brain** (Neocortex) | Analytical processing, logic | Evidence, value, usefulness | Data + utility |

**The rule:** Hit 1 = ignored. Hit 2 = engaged. Hit all 3 = shared.

---

## Part 1: Core Psychological Theories

### 1. Elaboration Likelihood Model (ELM)
*Petty & Cacioppo, 1986*

Two routes of persuasion depending on audience involvement:

| Route | When It Activates | What Persuades | Content That Works |
|---|---|---|---|
| **Central processing** | High interest, high involvement | Quality of arguments, logic, evidence | Research reports, whitepapers, long-form |
| **Peripheral processing** | Low attention, impulse mode | Credibility cues, attractiveness, emotion | Memes, visuals, influencer content, hooks |

**Skill application:** The audience profiling phase determines ELM level. High-involvement audiences require data-backed arguments. Low-involvement audiences need emotional/visual hooks. Getting this wrong is the #1 reason good content fails.

---

### 2. Fogg Behavior Model
*BJ Fogg, Stanford*

```
Behavior = Motivation × Ability × Trigger
```

All three must be present simultaneously. If any is missing — the behavior (engagement, share, click) does not happen.

| Factor | Content Application | Example |
|---|---|---|
| **Motivation** | Emotional resonance, relevance to desires/fears | "This affects your career/revenue/status" |
| **Ability** | Simple CTA, low friction, clear next step | Single clear action, not 3 options |
| **Trigger** | Urgency, timeliness, event-based reason to act now | "New data dropped today" / "Everyone is talking about this" |

**The Fogg gate** is checked on every generated variant. Variants missing a trigger element are flagged.

---

### 3. Self-Determination Theory (SDT)
*Deci & Ryan, 1985*

People engage when content satisfies three core psychological needs:

| Need | Description | Content That Activates It |
|---|---|---|
| **Autonomy** | Feeling of control, independence, self-direction | "Here's what I figured out" / "Decide for yourself" |
| **Competence** | Mastery, skill, knowing more than others | Educational content, insider knowledge, data insights |
| **Relatedness** | Belonging, connection, being understood | Community content, "us vs them", tribe signals |

**Skill application:** The audience psychology map identifies which SDT need is dominant for the target audience, which then informs tone and content structure.

---

### 4. Theory of Reasoned Action
*Fishbein & Ajzen, 1975*

```
Behavior = Attitude + Social Norms
```

People act based on:
1. What they personally believe
2. What they perceive others (their reference group) think

**Content implication:** Every piece of content should influence either beliefs (direct argument) or perceived social norms (social proof, testimonials, bandwagon signals). Testimonials are powerful because they update both simultaneously.

---

### 5. Relationship Marketing Theory

Long-term brand loyalty comes from emotional bonds — not just transactions.

Content types that build bonds:
- Behind-the-scenes (humanizes the brand)
- Community building (shared identity)
- Consistent storytelling over time (narrative continuity)
- Creator/founder voice (personal relationship at scale)

**Skill application:** The brand voice DNA profile specifically looks for emotional bond signals. Brands that over-index on product/achievement content and under-index on relationship content are flagged.

---

## Part 2: The 25 Psychological Triggers

The complete trigger library used in the scoring engine. Each variant is evaluated against all 25.

### Category 1: Social Triggers
*Humans are tribal — these triggers activate social cognition*

**1. Social Proof**
People trust what others already trust. One of the strongest persuasion forces in marketing.
- Content examples: testimonials, reviews, "10,000 founders use this", user counts
- LinkedIn execution: mention numbers, customer logos, real user quotes
- Power level: ★★★★★

**2. Authority**
People defer to perceived experts.
- Content examples: research reports, expert interviews, founder insights, data studies
- LinkedIn execution: cite sources, use credentials, reference research
- Power level: ★★★★★

**3. Liking**
People buy from people they like. Liking is triggered by similarity, humor, and genuine personality.
- Content examples: relatable stories, humor, personal vulnerability
- LinkedIn execution: first-person founder posts, honest admissions
- Power level: ★★★★☆

**4. Unity**
People support brands that feel like their tribe. Stronger than liking — it's identity-level belonging.
- Content examples: "Built for creators", "This is for the founders who...", in-group language
- LinkedIn execution: specific audience callouts, exclusive vocabulary
- Power level: ★★★★☆

**5. Bandwagon Effect**
If the crowd is moving in a direction — it feels correct.
- Content examples: trending topics, "everyone is switching to X", momentum signals
- LinkedIn execution: use "growing number of", "more and more teams are", trend data
- Power level: ★★★☆☆

---

### Category 2: Scarcity & Urgency Triggers

**6. Scarcity**
Limited availability increases perceived value. Works because of loss aversion.
- Content examples: "Only 100 spots", "Limited edition", "Closing applications"
- Warning: Must be genuine. Fake scarcity destroys trust when exposed.
- Power level: ★★★★☆

**7. Urgency**
Time pressure forces decision. Removes the "I'll do it later" default.
- Content examples: "Offer ends tonight", "Last day to apply", countdown
- Power level: ★★★★☆

**8. FOMO (Fear of Missing Out)**
Fear of being left behind while others move forward.
- Content examples: "Everyone is building AI agents right now", "Your competitors are already doing this"
- LinkedIn execution: industry shift content, trend urgency
- Power level: ★★★★★

**9. Exclusivity**
People want what others cannot access. Inverse scarcity — not less of it, but gated access.
- Content examples: invite-only, private beta, insider knowledge, "only for premium members"
- Power level: ★★★☆☆

---

### Category 3: Cognitive Bias Triggers
*From behavioral economics — how the brain shortcuts decisions*

**10. Loss Aversion**
*Kahneman & Tversky, 1979* — losses feel ~2x more painful than equivalent gains.
- Content examples: "Don't lose customers to competitors", "You're leaving revenue on the table"
- LinkedIn execution: frame inaction as loss, not action as gain
- Power level: ★★★★★

**11. Anchoring**
The first number seen influences all subsequent perception.
- Content examples: "$999 → $199", show the full value before the price
- LinkedIn execution: state the full cost/time/effort before revealing the shortcut
- Power level: ★★★★☆

**12. Framing Effect**
The same information presented differently produces different responses.
- "90% success rate" vs "10% failure rate" — same data, opposite emotional responses
- LinkedIn execution: always choose the frame that maximizes perceived value
- Power level: ★★★★★

**13. Availability Bias**
People believe what they see most frequently. Repetition creates perceived truth.
- Content implication: consistent message repetition across posts
- LinkedIn execution: repeat your core thesis in different formats over time
- Power level: ★★★☆☆

**14. Confirmation Bias**
People prefer content that confirms existing beliefs.
- Content examples: content that validates founder pain, pre-existing frustrations
- LinkedIn execution: open with "If you've ever felt X" to activate confirmation
- Power level: ★★★★☆

**15. Cognitive Fluency**
Easy-to-understand content feels more trustworthy and more true.
- Content implications: short sentences, clear structure, no jargon, white space
- LinkedIn execution: one idea per paragraph, bullet points, bold key lines
- Power level: ★★★★☆

---

### Category 4: Emotional Triggers
*Emotion drives sharing, memory, and action more than logic*

**16. Curiosity Gap**
Create a knowledge gap the reader feels compelled to close.
- Content examples: "You're making this growth mistake", "The thing nobody tells you about X"
- LinkedIn execution: hook creates the gap, body closes it — but only after earning the read
- Power level: ★★★★★

**17. Surprise**
Unexpected information captures attention and resets assumptions.
- Content examples: "Startup raised $5M without a product", counterintuitive data
- LinkedIn execution: open with the most surprising stat or claim you have
- Power level: ★★★★★

**18. Awe**
Big ideas, massive scale, paradigm shifts trigger inspiration and sharing.
- Content examples: AI breakthroughs, India's EV transformation scale, civilization-level changes
- LinkedIn execution: zoom out to the biggest possible frame first
- Power level: ★★★★☆

**19. Fear**
Specific, credible threat to something the reader values — career, revenue, status, safety.
- Content examples: "Your data is not safe", "You're losing market share to this"
- Warning: Must be specific and credible. Vague fear = ignored. Fear-baiting = distrust.
- Power level: ★★★★★

**20. Belonging**
People want identity groups. Content that reflects their tribe gets shared as identity expression.
- Content examples: "If you're a founder who...", "This is for the builders", crypto/AI/startup culture
- LinkedIn execution: name the tribe explicitly, use their language
- Power level: ★★★★☆

---

### Category 5: Motivation Triggers
*These convert attention into action*

**21. Reciprocity**
*Cialdini's Influence* — if you give value, people feel obligated to return.
- Content examples: free guides, original research, actionable frameworks
- LinkedIn execution: give the entire insight for free in the post — don't gate it
- Power level: ★★★★★

**22. Commitment & Consistency**
*Cialdini* — people behave consistently with prior commitments and self-image.
- Content examples: small agreeable statements that lead to larger commitments
- LinkedIn execution: "If you believe X (easy yes) → then you need to do Y"
- Power level: ★★★★☆

**23. Progress Effect**
People complete things when progress is visible. Showing momentum creates desire to continue.
- Content examples: progress bars, "from X to Y" transformations, milestones
- LinkedIn execution: before/after stories, journey posts
- Power level: ★★★☆☆

**24. Personalization**
People engage more with content tailored to them. ~71% of consumers expect personalization.
- Content examples: "If you're a [specific role]...", tailored pain points
- LinkedIn execution: hyper-specific audience callouts, role-specific language
- Power level: ★★★★☆

**25. Identity Signaling**
People share content that reflects who they are or who they want to be.
- Content examples: "builders", "founders", "AI nerds", "India-first thinkers"
- LinkedIn execution: ask "does sharing this make the person look/feel a specific way they want?"
- This is the single most important trigger for organic reach
- Power level: ★★★★★

---

## Part 3: Narrative Frameworks

### AIDA
**Best for:** Short posts, ads, email subjects, LinkedIn single posts
```
Attention  → Hook that stops scroll (1-2 lines)
Interest   → Problem or context that is personally relevant
Desire     → The outcome/benefit clearly stated
Action     → Single, specific CTA
```

### PAS (Problem → Agitate → Solution)
**Best for:** Landing pages, product launches, email campaigns, conversion content
```
Problem    → Name the exact pain
Agitate    → Make the cost of the problem visceral and real
Solution   → Present your answer as the only logical response
```

### StoryBrand
**Best for:** Brand narrative, about pages, founder stories, launch content
```
Hero       → The customer (not the brand) is the hero
Problem    → External + internal problem they face
Guide      → The brand as the wise guide (not the hero)
Plan       → Clear 3-step path to success
Success    → The specific transformation they will experience
```

### The Contrarian
**Best for:** Thought leadership, viral LinkedIn posts, industry debate content
```
Common belief  → State the consensus view (that you'll challenge)
The challenge  → Your data/evidence/argument against it
Better truth   → The more nuanced or accurate view
Stakes         → Why this matters if you're right
```

### The Data Drop
**Best for:** Authority content, credibility building, research-backed posts
```
Surprising stat   → Most unexpected data point first
Why it matters    → Connect to the reader's reality
Implication       → What this means for how they should act
```

### Before/After/Bridge
**Best for:** Transformation content, testimonials, milestone posts
```
Before  → The painful current state (be specific)
After   → The desired end state (be vivid)
Bridge  → Your specific mechanism/product/approach that connects them
```

### The Confession
**Best for:** Trust building, relatability, humanizing brand voice
```
Mistake/failure  → Honest admission of something that went wrong
The lesson       → What it actually taught you
New approach     → The better behavior that followed
```

---

## Part 4: The Viral Content Formula

The secret combination used by the highest-performing content:

```
Emotion + Cognitive Bias + Utility = Content That Spreads
```

### Examples

| Content Type | Psychology | Why It Works |
|---|---|---|
| Case study | Social proof + authority | Activates social brain + rational brain simultaneously |
| Research report | Authority + reciprocity | Gives genuine value + establishes expertise |
| Meme | Dopamine + identity signaling | Fast reward + tribal belonging |
| Tutorial | Competence + reciprocity | Builds the reader up + creates obligation |
| Community post | Belonging + unity | Pure social brain activation |
| Comparison article | Framing effect + rational evaluation | Helps decide + anchors perceived value |

### The 3-Trigger Rule
The best content stacks 3 triggers simultaneously. Example:

> *"10 AI tools every startup founder is using right now"*
- **Curiosity gap** (#16) — "10 tools" implies I might be missing some
- **Social proof** (#1) — "every founder is using" = normative pressure
- **FOMO** (#8) — "right now" = I'm already behind

### The Brain System Test
Before publishing any content, confirm it hits all three:

```
Emotional brain:  Does it make the reader FEEL something?
Social brain:     Does it reference OTHERS or NORMS?
Rational brain:   Does it give REAL, USEFUL information?
```

---

## Part 5: Platform Psychology

Different platforms activate different psychological modes:

| Platform | Dominant Psychology | Primary Trigger | Sharing Motivation |
|---|---|---|---|
| LinkedIn | Professional identity, career status | Authority + Identity Signaling | "I am a serious professional" |
| Twitter/X | Real-time discourse, wit, hot takes | Curiosity Gap + Surprise | "I am in the know / have opinions" |
| Instagram | Aspiration, aesthetics, lifestyle | Belonging + Awe | "This reflects my lifestyle/values" |
| Email | Personal relationship, trusted advisor | Reciprocity + Personalization | N/A (private channel) |
| Blog | Research, expertise, depth | Authority + Utility | SEO discovery + reference sharing |

---

## Research Sources

This framework draws from:

- Kahneman, D. (2011). *Thinking, Fast and Slow*
- Cialdini, R. (1984). *Influence: The Psychology of Persuasion*
- Fogg, B.J. (2020). *Tiny Habits*
- Petty, R.E. & Cacioppo, J.T. (1986). Elaboration Likelihood Model
- Deci, E.L. & Ryan, R.M. (1985). Self-Determination Theory
- Fishbein, M. & Ajzen, I. (1975). Theory of Reasoned Action
- Tversky, A. & Kahneman, D. (1979). Prospect Theory
- Godin, S. (2018). *This Is Marketing*
- Holiday, R. (2014). *Growth Hacker Marketing*
- Heath, C. & Heath, D. (2007). *Made to Stick*
