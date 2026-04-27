---
name: nuromark
description: >
  NuroMark — neuroscience-based content scoring engine. Applies TRIBE v2 research
  findings (Meta FAIR, arXiv:2507.22229) to score content variants by predicted
  cortical engagement across 5 brain dimensions. Use when you want to score any
  content before publishing, compare variants using brain-aligned metrics, or add
  a neurological layer to your content scoring. Invoked automatically by all
  content skills, or directly via /nuromark. Trigger words: "neuro score",
  "brain score", "nuromark", "neurological", "cortical", "fMRI score", "TRIBE".
metadata:
  author:
  version: 2.0.0
  science: TRIBE v2 — Meta FAIR (d'Ascoli et al., arXiv:2507.22229)
  repo: https://github.com/facebookresearch/tribev2
  weights: https://huggingface.co/facebook/tribev2
---

# NuroMark — Neuroscience Content Scoring Engine

## What This Is (and Isn't)

The NeuroScore is a **framework-based scoring system** derived from published neuroscience findings — primarily TRIBE v2 (d'Ascoli et al., Meta FAIR, arXiv:2507.22229) and the broader cognitive neuroscience literature it builds on. It does not run live fMRI inference. It operationalises what researchers discovered about how specific content properties activate specific brain regions, and translates those findings into scorable content dimensions.

This is the difference between **using the map** and running the territory. The map is derived from the territory. It is useful.

---

## Scientific Foundation

### TRIBE v2 — Primary Source

**Paper:** d'Ascoli et al., "TRIBE: TRImodal Brain Encoder for whole-brain fMRI response prediction" (arXiv:2507.22229, Meta FAIR, 2026)

**What the research did:**
- Trained on 700+ healthy volunteers exposed to video, audio, and text stimuli
- Built the first deep neural network predicting brain responses across multiple modalities, cortical areas, and individuals simultaneously
- Won Algonauts 2025 brain encoding competition with a significant margin over competitors
- Achieved ~20,000-vertex cortical surface predictions (high-resolution whole-brain maps)

**Key verified findings from TRIBE v2:**

| Finding | Source | Marketing Implication |
|---|---|---|
| Multimodal models significantly outperform unimodal models in high-level associative cortices | TRIBE v2 paper (confirmed) | Content that combines text + visual + audio encodes deeper than any single format |
| Unimodal models reliably predict only their corresponding sensory network | TRIBE v2 paper | Text-only content only activates language regions — misses emotional and social cortex |
| Temporal-parietal-occipital (TPO) junction shows the strongest gains from multimodal combinations | TRIBE v2 architecture analysis | Audio+visual synchrony is the highest-value content pairing for sustained attention |
| High-level associative cortices (TPJ, MTG, DMN) require multimodal input to activate strongly | TRIBE v2 paper | Emotional resonance and shareability require more than text alone |

### Supporting Neuroscience Literature

TRIBE v2 is built on decades of prior fMRI and cognitive neuroscience research. These findings are incorporated into the NeuroScore:

| Finding | Source | Marketing Rule |
|---|---|---|
| Default Mode Network (DMN) activates for narrative comprehension and episodic memory | Hasson et al. (2008); Zacks et al. (2007) | Story-driven content has higher recall than list-driven content |
| Temporoparietal Junction (TPJ) activates for social cognition, theory of mind, emotional content | Saxe & Kanwisher (2003); Decety & Lamm (2007) | Content that describes others' mental states or emotions increases shareability |
| Sentence-level simplicity → faster limbic/emotional processing | Ferreira & Henderson (1990); cognitive load research | Short sentences in hooks/CTAs trigger faster emotional response |
| Syntactically complex sentences → prefrontal/analytical engagement | Just & Carpenter (1992); Broca's area research | Complex body copy builds the rational case better than simple assertions |
| Fusiform Face Area (FFA) reliably activates for human faces — even in text descriptions | Kanwisher et al. (1997); face recognition literature | Copy referencing human faces or describing facial expressions activates visual cortex |
| Curiosity / information gap → nucleus accumbens + anterior cingulate activation (dopaminergic) | Loewenstein (1994); Gruber et al. (2014) | Curiosity gap hooks trigger dopamine anticipation — reader is neurologically compelled to resolve the gap |
| Loss framing → stronger amygdala activation than gain framing | Kahneman & Tversky (1979); Canessa et al. (2013) | "Stop losing X" outperforms "gain X" neurologically for attention capture |
| Social conformity cues → anterior insula + ventral striatum | Klucharev et al. (2009); Berns et al. (2010) | Social proof copy activates reward circuits — not just persuasion, but neurological compliance |
| Pattern interrupts → orienting response in superior colliculus + thalamic gating | Sokolov (1963); Corbetta & Shulman (2002) | Unexpected content at the opening activates the orienting reflex — attention is neurologically mandatory |
| Concrete nouns (faces, places, objects) → stronger parahippocampal activation than abstract nouns | Paivio's dual-coding theory (1971); neuroimaging confirmations | "3 marketing hires" encodes stronger than "significant resources" |
| Narrative tension (setup→conflict→resolution) → sustained DMN engagement | Mar (2011); Zacks et al. (2007) | Content with unresolved tension holds attention longer than resolved linear content |

---

## The 5 NeuroScore Dimensions (50 Points)

Score each content variant across 5 neurological dimensions, 0–10 each.

---

### Dimension 1 — Cortical Coverage (0–10)

**Brain regions targeted:** Visual cortex, auditory cortex, language network (STG/MTG/IFG), emotional network (TPJ/amygdala), memory network (hippocampus/parahippocampal)

**What it measures:** How many distinct brain regions does this content engage? More regions = more encoded, more recalled, more shared.

**TRIBE v2 finding:** Unimodal content predicts only the corresponding sensory cortex. To reach associative cortex (where emotion, social cognition, and meaning-making happen), multiple modalities or modality-simulating language are required.

**Scoring rubric:**

| Score | Signal | Brain basis |
|---|---|---|
| 9–10 | Engages visual, auditory, emotional, and language regions simultaneously | True multimodal input or vivid multimodal language |
| 7–8 | Hits 2–3 regions strongly (visual + language, or emotional + narrative) | Strong sensory language or multimodal format |
| 5–6 | Single modality but high-intensity (e.g. video with strong motion cues) | Visual cortex dominates, minimal associative cortex |
| 3–4 | Single modality, minimal sensory richness | Language network only, low activation depth |
| 0–2 | Abstract text, no sensory anchors, no narrative, no emotional language | Minimal cortical coverage — forgettable |

**Scoring guide — check each:**
- [ ] Concrete nouns present? (people, places, objects, numbers) → +parahippocampal/visual cortex
- [ ] Emotional language present? (fear, pride, loss, belonging) → +amygdala/TPJ
- [ ] Narrative structure present? (sequence, tension, resolution) → +DMN
- [ ] Sensory description present? (visual scene, sound reference) → +auditory/visual cortex
- [ ] Social reference present? (others' thoughts, reactions, identity) → +TPJ/social cognition network

---

### Dimension 2 — Multimodal Synergy (0–10)

**Brain region targeted:** Temporal-parietal-occipital (TPO) junction — the brain's multisensory integration hub

**What it measures:** Do the content's modalities reinforce each other to create cortical gain? TRIBE v2 confirmed the TPO junction shows the strongest gains from audio+visual combinations specifically.

**Key finding:** Multimodal gain is not additive — it is synergistic. Text + matching visual + matching audio creates a cortical response that exceeds the sum of parts. The reverse is also true: mismatched modalities suppress each other (cognitive dissonance at the cortical level).

**Scoring rubric:**

| Score | Signal |
|---|---|
| 9–10 | Video/audio content where visual, voiceover, and text are semantically locked — saying the same thing three ways |
| 7–8 | Two modalities paired with matching semantic content (image + caption that extend each other, not repeat) |
| 5–6 | Single modality with strong multimodal language (copy that describes sounds, visuals, or motion) |
| 3–4 | Single modality, no cross-modal reference |
| 0–2 | Modalities contradict each other (text says one thing, visual says another) — negative synergy |

**Scoring guide:**
- For video: Do audio and visuals describe the same thing at the same moment? (synchrony = gain)
- For social posts with images: Does caption extend the visual or just repeat it? (extend = gain, repeat = neutral)
- For emails: Does the subject line prime the sensory tone of the body? (priming = gain)
- For text-only: Is there language that simulates a second sense? ("Imagine hearing...", "Picture this...")

---

### Dimension 3 — Emotional-Rational Calibration (0–10)

**Brain regions:** TPJ/amygdala (emotional) vs. prefrontal cortex + Broca's area (rational)

**What it measures:** Is the emotional vs. rational language ratio calibrated to the goal? TRIBE v2 isolates which brain regions activate for which linguistic properties — emotional language fires TPJ/amygdala, complex syntax and evidential language fires prefrontal/Broca's.

**Calibration targets by funnel stage:**

| Stage | Ideal E:R Ratio | Brain Target | Why |
|---|---|---|---|
| Awareness / brand | 80% emotional, 20% rational | TPJ, amygdala, DMN | Cold audience — emotion creates memory trace |
| Engagement / social | 70% emotional, 30% rational | DMN, TPJ, social cortex | Emotion drives sharing; some rational for identity signal |
| Lead generation / consideration | 50/50 | Mixed | Warm audience needs both trust and desire |
| Conversion / decision | 30% emotional, 70% rational | Prefrontal, Broca's, ACC | Analytical processing needed to justify the decision |
| Retention / loyalty | 60% emotional, 40% rational | DMN, TPJ | Reinforce identity and belonging, sustain relationship |

**Scoring rubric:**

| Score | Signal |
|---|---|
| 9–10 | Ratio matches target within 10 percentage points |
| 7–8 | Mostly correct, minor imbalance (within 20 points) |
| 5–6 | Noticeable mismatch — will underperform for the stated goal |
| 3–4 | Significant mismatch — conversion copy that's 80% emotional, or awareness copy with no emotion |
| 0–2 | Extreme mismatch — no emotional content at all, or pure emotion with zero rational substance |

**Scoring guide:**
- Count emotionally charged words: fear, lose, proud, imagine, belong, win, ashamed, excited, trust
- Count rational/evidential words: because, data, proven, specifically, results, which means, compared to, since
- Calculate ratio. Compare to target for goal. Score accordingly.
- **Loss aversion bonus:** If content uses loss framing ("stop losing", "you're missing"), add +1 to score — amygdala activation is stronger for loss than equivalent gain

---

### Dimension 4 — Linguistic Complexity Calibration (0–10)

**Brain regions:** Broca's area + left hemisphere (complex syntax) vs. limbic system (simple sentences)

**What it measures:** Is sentence complexity matched to the cognitive moment? Short, simple sentences trigger fast limbic processing (emotional, impulsive). Complex multi-clause sentences engage prefrontal cortex (deliberate, trust-building). Neither is better — the placement matters.

**Neurological arc for content:**

| Placement | Target complexity | Word count | Rationale |
|---|---|---|---|
| Hook / headline / subject line | Simple — active voice imperative or single declarative | ≤10 words | Trigger limbic fast-response before rational gating engages |
| Opening paragraph / setup | Moderate — 1 main clause + 1 dependent | 12–25 words | Engage without overloading working memory |
| Body / value prop / evidence | Complex — multi-clause, causal connectors | 20–40 words | Build rational case via prefrontal engagement |
| CTA | Simple — single imperative verb + benefit | ≤8 words | Return to limbic for impulsive action |

**Power causal connectors** (add to body to activate prefrontal/Broca's):
- "which means", "because", "resulting in", "since", "therefore", "specifically"

**Scoring rubric:**

| Score | Signal |
|---|---|
| 9–10 | Hook simple (≤10 words), body complex (causal connectors present), CTA simple — neurological arc complete |
| 7–8 | 2 of 3 placements correctly calibrated |
| 5–6 | Uniform complexity throughout — all simple (weakly persuasive) or all complex (loses attention) |
| 3–4 | Hook is complex (kills attention before engagement) or CTA is complex (kills impulse) |
| 0–2 | Opposite of optimal — dense academic hook, no rational body, vague CTA |

**Scoring guide:**
- Count words in hook/headline: >12 = penalise D4
- Does the body contain at least 2 causal connectors? No = penalise D4
- Is the CTA a clean imperative verb with a specific benefit? No verb = penalise D4

---

### Dimension 5 — Attention Integration Score (0–10)

**Brain region:** Temporal-parietal-occipital (TPO) junction + superior colliculus (orienting reflex) + anterior cingulate cortex (conflict monitoring)

**What it measures:** Does the content activate the brain's attention integration system? TRIBE v2 shows the TPO junction — the multisensory hub — sees the largest gains from unexpected or surprising input combinations. The superior colliculus triggers an involuntary orienting response when the brain detects something novel or unexpected. Content that exploits this is neurologically impossible to ignore at the moment of exposure.

**Neurological attention triggers:**

| Trigger | Brain mechanism | Content application |
|---|---|---|
| Pattern interrupt at opening | Superior colliculus orienting reflex | Open with something that violates expectation — wrong prediction = mandatory attention |
| Information gap / curiosity | Nucleus accumbens dopamine + ACC | Create an incomplete information state. Brain is compelled to resolve it. |
| Perspective shift | TPO reorientation | "Imagine you are..." — forces model-building in the reader's brain |
| Cross-modal surprise | TPO multisensory integration | Describing a sound in visual terms, or a visual in tactile terms |
| Narrative tension (unresolved) | DMN sustained engagement | Setup a conflict. Don't resolve it too fast. Brain holds tension to maintain narrative model. |
| Spatial / motion language | TPO + motor cortex simulation | "Step into", "move from X to Y", "swipe", "scroll past" — motor cortex partially activates |
| Concrete unexpected specificity | Hippocampal novelty detection | "47.3%" not "about half". Unexpected precision triggers novelty signal. |

**Scoring rubric:**

| Score | Signal |
|---|---|
| 9–10 | 3+ attention triggers present — pattern interrupt, information gap, narrative tension |
| 7–8 | 2 triggers present |
| 5–6 | 1 trigger present |
| 3–4 | Predictable, linear, no expectation violation |
| 0–2 | Completely expected from first word — zero surprise, zero tension, zero novelty |

**Scoring guide:**
- Does the first line violate a common expectation or belief? (pattern interrupt)
- Is there something the reader doesn't know yet but wants to? (information gap)
- Is there unresolved tension at the end of the hook? (narrative tension)
- Is there a specific unexpected number or claim? (novelty detection)
- Is there motion, perspective shift, or spatial language? (TPO + motor)

---

## Content Rules from Neuroscience

These are the writing rules that fall directly from the research — specific enough to apply immediately:

### Rules for hooks / headlines / subject lines
1. **≤10 words.** More words = more cognitive load = limbic gating reduced.
2. **Concrete nouns beat abstract ones.** "3 engineers" > "significant team". Hippocampal encoding is stronger for concrete.
3. **Loss framing outperforms gain framing.** "Stop losing pipeline" > "gain more pipeline". Amygdala activation is ~2.5x stronger for loss (Kahneman & Tversky, confirmed in neuroimaging).
4. **Information gap > complete statement.** "What nobody tells you about..." > "Here's the truth about...". Dopamine loop requires incompletion.
5. **Never start with abstract context.** "In today's world..." delays concrete activation. Brain needs a noun or a conflict in the first 3 words.

### Rules for body copy
1. **Causal connectors are cognitive load reducers.** "Because", "which means", "resulting in" — these reduce the cognitive effort of making connections, making your argument feel more obvious. Use them.
2. **Vary sentence length.** Short sentence. Then a longer sentence that builds on the short one, adding evidence and causal structure to what you just stated. Then short again. This rhythm mirrors natural speech prosody and maintains attention.
3. **Concrete specifics over vague claims.** "Reduced CAC by 34% in 90 days" encodes in hippocampus as an episodic memory. "Significantly reduced costs" encodes weakly.
4. **Social proof is neurological, not rhetorical.** When you write "10,000 teams use this", the reader's anterior insula + ventral striatum activate for social conformity. This is not persuasion — it's compliance circuitry. Use it early.
5. **Describe human faces or reactions.** Even in text, describing a facial expression or a person's reaction activates the reader's fusiform face area and mirror neuron system — increasing emotional resonance.

### Rules for CTAs
1. **Single imperative verb.** "Start / Get / Join / See / Try." No compound CTAs. Multiple verbs split motor planning.
2. **Benefit in the same line.** "Start your free trial" > "Click here." Benefit activates reward anticipation in nucleus accumbens.
3. **Remove friction language.** "No credit card required", "Cancel anytime" — these deactivate amygdala risk response at the moment of decision. Place them adjacent to CTAs, not in a footnote.

### Rules for video / audio content
1. **Voice and visual must match semantically at the same moment.** When audio says "three steps" and the visual shows a numbered list at that exact moment — TPO gain is maximised.
2. **Human face in first frame.** Fusiform face area activates in <150ms. Establishes connection before any rational processing begins.
3. **Music tempo should match content pace.** Fast-tempo music during fast-cut visuals = TPO synchrony. Mismatch = suppression.
4. **State the highest-value claim in the first 3 seconds.** Superior colliculus orienting reflex is at maximum attention intensity in the opening window. Most valuable content goes here, not at the end.

---

## NeuroScore Output Format

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
NEUROSCORE — [Content name / variant]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
D1 Cortical Coverage         [ X / 10 ]
   Regions hit: [visual / auditory / emotional / narrative / social]

D2 Multimodal Synergy        [ X / 10 ]
   Modality pairs: [text+image / video+audio / text-only / etc.]

D3 Emotional-Rational Cal.   [ X / 10 ]
   E:R ratio: [%E / %R] | Target for goal: [target] | Match: [yes/close/off]

D4 Linguistic Complexity     [ X / 10 ]
   Hook: [simple/complex] | Body: [causal connectors: yes/no] | CTA: [clean/compound]

D5 Attention Integration     [ X / 10 ]
   Triggers: [list active triggers from the 7 above]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
NEUROSCORE                   [ X / 50 ]
PSYCH SCORE (from skill)     [ X / 60 ]
COMBINED SCORE               [ X / 110 ]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Weakest dimension: D[n] — [specific 1-line fix]
Strongest signal:  D[n] — [what's working and why]
Brain regions targeted: [list]
Recommendation: Publish / A/B Test / Optimize / Rewrite
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Combined Score Thresholds

| Combined /110 | Recommendation |
|---|---|
| 90–110 | Publish immediately — neurologically and psychologically optimised |
| 75–89 | A/B test — strong signal, validate with real audience data |
| 60–74 | Optimize before publishing — identify and fix lowest dimension |
| Below 60 | Mandatory rewrite — fails both neurological and psychological thresholds |

---

## Per-Skill Integration Notes

###-social
- LinkedIn: Prioritise D5 (pattern interrupt hook) + D3 (70% emotional for engagement)
- Twitter/X: D4 critical — hook must score 9+. Twitter is 280 chars = entire D4 test is the hook.
- Carousel: D2 gets a score even for text-only carousels (visual+text pairing = partial multimodal)

###-ads
- Conversion ads: D3 must be 30% emotional / 70% rational — penalise any conversion ad scored >50% emotional
- Video ads: D2 (Multimodal Synergy) weighted most heavily — no video ad should ship with D2 <7
- Retargeting: D5 "pattern interrupt" must acknowledge prior exposure — "Still thinking about X?" is a pattern interrupt for warm audiences

###-video
- Score D4 at three checkpoints: 0–3s hook, 3–30s body, final 5s CTA
- Flag any timestamp where D4 drops — that's where viewers drop off
- D2 score: if audio and visual aren't semantically locked at every moment, flag for edit

###-email
- Subject line: score D4 only — must score 8+. If not, rewrite before sending.
- Preview text: treat as part of D5 — it's the second line of the hook, should extend tension
- Body: D3 calibration is the most important dimension here — match E:R ratio to email type (cold = 50/50, nurture = 60/40, re-engagement = 70/30)
- CTA: D4 — clean imperative + benefit + friction removal adjacent

###-landing
- Hero H1: D4 + D5 — simple + pattern interrupt
- Subheadline: D3 — introduce emotional stakes
- Feature/benefit section: D1 + D3 — cortical coverage via concrete language + rational calibration
- Social proof section: D3 emotional weight increases here (anterior insula social compliance)
- CTA section: D4 — simple imperative + friction removal language

###-gtm
- Launch day content: D5 must score 9+ (launch is the highest-stakes pattern interrupt of the year)
- Product Hunt post: D2 score — tagline + description + founder comment should function as a multimodal unit
- Countdown content: D3 should be 70% emotional — urgency is limbic, not rational

###-analyze
- Retroactively apply NeuroScore to top and bottom performing content
- Correlate D-scores with engagement rate to identify which dimensions predict performance for this specific brand
- Goal: build brand-specific D-profile ("this audience responds to high D5 + high D3 emotional content")
- Output: "Winning NeuroProfile" that guides future scoring thresholds

---

## Scientific Honesty Note

The NeuroScore is a practitioner framework derived from peer-reviewed neuroscience research. It is not:
- A live fMRI measurement of actual brain responses to your content
- A guarantee of performance

It is a disciplined translation of what researchers found about how content properties activate brain regions, applied as a pre-publication checklist. The underlying findings are real. The scores are proxies. Use them to catch obvious failures and rank variants — not as precision instruments.

For live inference: model weights at `facebook/tribev2` on HuggingFace, code at the GitHub repo above.
