---
name: grovio-neuro
description: >
  NeuroScore engine for the Grovio Content System. Applies TRIBE v2 neuroscience
  principles (Meta FAIR, 2026) to score content variants by predicted cortical
  engagement. Use when you want to neuro-score any content before publishing,
  compare variants using brain-aligned metrics, or upgrade the standard 6-dimension
  scoring with a neurological layer. Invoked automatically by grovio-content,
  grovio-ads, grovio-video, and grovio-social, or directly via /grovio-neuro.
metadata:
  author: Grovio
  version: 1.0.0
  science: TRIBE v2 — Meta FAIR (d'Ascoli et al., 2026)
  weights: https://huggingface.co/facebook/tribev2
---

# Grovio NeuroScore Engine

## Scientific Foundation

This skill operationalises findings from **TRIBE v2**, Meta FAIR's tri-modal
foundation model trained on 1,000+ hours of fMRI across 720 subjects. TRIBE v2
predicts high-resolution whole-brain responses to video, audio, and language
inputs, enabling _in silico_ hypothesis testing without running live experiments.

Key findings encoded into this skill:

| Finding | Marketing Implication |
|---|---|
| Multimodal (text+audio+video) encodes up to 50% better than any single modality | Multimodal campaigns are neurologically superior |
| Simple sentences → limbic/emotional activation | Hooks and CTAs should be simple |
| Complex syntax → prefrontal/rational activation | Value props and specs need structure |
| TPJ + MTG activate for emotional content | Emotional copy drives shareability |
| Default Mode Network → narrative / meaning-making | Story-driven content has higher recall |
| Combining modalities yields the strongest gains at the temporal-parietal-occipital junction | Audio+visual synchrony is highest-value pairing |
| Broca's area + left hemisphere → syntactically rich language | Complex-sentence copy aids decision-making |
| Fusiform gyrus → face/object recognition | Human faces in visuals improve ad recall |

---

## Invocation

```
/grovio-neuro <content_variant_or_brief> [--format text|video|audio|multimodal] [--goal awareness|engagement|conversion]
```

Or pass content inline from another skill:

```
/grovio-social https://stripe.com linkedin thought-leadership | /grovio-neuro --goal engagement
```

---

## NeuroScore Framework (50 Points)

Score each content variant across 5 neurological dimensions. Each dimension is
scored 0–10. Total = NeuroScore /50. Append to or replace the standard /60 score.

---

### Dimension 1 — Cortical Coverage (0–10)

**What it measures:** How many distinct brain regions does this content engage?
More coverage = more memorable, more shareable.

**Scoring rubric:**

| Score | Signal |
|---|---|
| 9–10 | Activates visual + auditory + language + emotional regions simultaneously (true multimodal) |
| 7–8 | Hits 2–3 regions strongly (e.g. visual + language, or audio + emotional) |
| 5–6 | Single modality but high-intensity (e.g. pure video with strong motion cues) |
| 3–4 | Single modality, low stimulus richness |
| 0–2 | Generic text with no sensory anchors, no narrative, no imagery |

**Scoring guide:**
- Does the content contain imagery or visual description? (+visual cortex)
- Does it contain a sound reference, rhythm, or audio hook? (+auditory cortex)
- Does it tell a story or reference social situations? (+default mode network)
- Does it use emotionally loaded language? (+TPJ/MTG)
- Does it use concrete nouns (faces, places, objects)? (+fusiform/parahippocampal)

---

### Dimension 2 — Multimodal Synergy (0–10)

**What it measures:** Does the content pair modalities in a way that creates
cortical gain? TRIBE v2 shows the temporal-parietal-occipital junction responds
most strongly to audio+visual synchrony.

**Scoring rubric:**

| Score | Signal |
|---|---|
| 9–10 | Video + voiceover/music + on-screen text working in unison |
| 7–8 | Two modalities paired (e.g. image with spoken-word hook, or text with embedded audio reference) |
| 5–6 | Single modality with strong implicit multimodal cues (vivid sensory language) |
| 3–4 | Single modality, no cross-modal reference |
| 0–2 | Text-only with no sensory or auditory language whatsoever |

**Scoring guide:**
- For video content: are audio and visuals reinforcing the same message simultaneously?
- For social posts: does the copy reference what the visual shows (synchrony)?
- For emails: does the subject line prime the sensory experience of the body?
- For ads: is there motion, sound, and text working as a unit?

---

### Dimension 3 — Emotional-Rational Calibration (0–10)

**What it measures:** Is the balance of emotional vs. rational language calibrated
correctly for the funnel stage and goal? TRIBE v2 isolates TPJ/MTG (emotional)
vs. prefrontal/Broca's (rational) activation.

**Calibration targets by goal:**

| Goal | Ideal E:R Ratio | Brain Target |
|---|---|---|
| Awareness / brand | 80% emotional, 20% rational | TPJ, MTG, limbic |
| Engagement / social | 70% emotional, 30% rational | DMN, TPJ |
| Lead generation | 50/50 | Mixed |
| Conversion / decision | 30% emotional, 70% rational | Prefrontal, Broca's |
| Retention / loyalty | 60% emotional, 40% rational | DMN, TPJ |

**Scoring rubric:**

| Score | Signal |
|---|---|
| 9–10 | Near-perfect calibration for stated goal |
| 7–8 | Mostly correct, minor imbalance |
| 5–6 | Detectable mismatch (e.g. conversion copy that's too emotional) |
| 3–4 | Significant mismatch (pure emotional for conversion, or pure rational for awareness) |
| 0–2 | No emotional language at all, or no rational substance at all |

**Scoring guide:**
- Count emotionally loaded words (feel, imagine, fear, proud, lose, win, joy)
- Count rational/evidential words (because, data, proven, results, since, specifically)
- Check ratio against goal calibration target above

---

### Dimension 4 — Linguistic Complexity Calibration (0–10)

**What it measures:** Is sentence structure complexity matched to the cognitive
load the audience should experience at this funnel stage? TRIBE v2 shows:
- Simple sentences → limbic (emotional, fast, impulsive)
- Complex syntax → prefrontal (deliberate, analytical, trust-building)

**Complexity targets by placement:**

| Placement | Target | Rationale |
|---|---|---|
| Hook / headline / subject line | Simple (≤8 words, active voice) | Trigger limbic fast-response |
| Opening paragraph / first 3 seconds | Moderate (1–2 clauses) | Engage without losing |
| Body / value prop | Complex (multi-clause, causal structure) | Build rational case |
| CTA | Simple + action verb | Return to limbic for impulse |

**Scoring rubric:**

| Score | Signal |
|---|---|
| 9–10 | Hook simple, body complex, CTA simple — textbook neurological arc |
| 7–8 | 2 of 3 placements correctly calibrated |
| 5–6 | Uniform complexity throughout (all simple or all complex) |
| 3–4 | Hook is complex (kills attention), body is simple (fails to persuade) |
| 0–2 | Total mismatch — dense academic hook, no rational body |

**Scoring guide:**
- Count words in hook/headline. >12 words = penalise.
- Does the body contain "because", "which means", "resulting in", causal connectors?
- Is the CTA a clean imperative verb? (Start / Get / Join / See / Try)

---

### Dimension 5 — Attention Integration Score (0–10)

**What it measures:** Does the content activate the brain's attention integration
hub — the temporal-parietal-occipital (TPO) junction? TRIBE v2 shows this region
sees the biggest gains from multimodal combinations and is strongly linked to
sustained attention and memory encoding.

**TPO triggers:**
- Unexpected juxtapositions (pattern interrupts)
- Cross-modal surprises (a sound described visually, or vice versa)
- Perspective shifts ("imagine you are...")
- Spatial or motion language ("swipe", "step into", "move from X to Y")
- Narrative tension (setup → conflict → resolution structure)

**Scoring rubric:**

| Score | Signal |
|---|---|
| 9–10 | Contains 3+ TPO triggers — strong pattern interrupt, cross-modal reference, narrative arc |
| 7–8 | 2 TPO triggers present |
| 5–6 | 1 TPO trigger present |
| 3–4 | Content is predictable, no pattern interrupts |
| 0–2 | Flat, linear, zero surprise — attention will drop after first line |

**Scoring guide:**
- Does the hook violate a common expectation?
- Is there a sensory word that creates a mental image or sound?
- Does the content have a beginning, tension, and resolution?
- Is there movement or spatial language?

---

## NeuroScore Output Format

After scoring all 5 dimensions, output:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🧠 GROVIO NEUROSCORE — [Variant Name]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
D1 Cortical Coverage       [ X / 10 ]
D2 Multimodal Synergy      [ X / 10 ]
D3 Emotional-Rational Cal. [ X / 10 ]
D4 Linguistic Complexity   [ X / 10 ]
D5 Attention Integration   [ X / 10 ]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
NEUROSCORE TOTAL           [ X / 50 ]
PSYCH SCORE (existing)     [ X / 60 ]
COMBINED SCORE             [ X / 110 ]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

🔬 Weakest dimension: [D#] — [1-line fix]
⚡ Strongest signal:  [D#] — [what's working]
🎯 Brain regions targeted: [list]
🚀 Recommended action: Publish / A-B Test / Rewrite
```

---

## Combined Ranking Logic

When scoring multiple variants, rank by Combined Score (out of 110):

| Combined Score | Recommendation |
|---|---|
| 90–110 | #1 — Publish immediately |
| 75–89 | #2 — A/B test against #1 |
| 60–74 | #3 — Reserve / iterate |
| Below 60 | Rewrite — fails neurological and psychological thresholds |

---

## Per-Skill Integration Notes

### grovio-social
- Score each variant before ranking. Boost variants with high D5 (pattern interrupt) for LinkedIn.
- Twitter/Threads: prioritise D4 (simple hook) and D3 (emotional calibration).

### grovio-ads
- Pre-publication neural ranking: run NeuroScore before A/B test launch.
- Conversion ads: penalise any variant scoring <6 on D4 (if hook is too complex) or <6 on D3 (if emotional/rational ratio is wrong for conversion).
- Video ads: D2 (Multimodal Synergy) is weighted highest — down-rank any video without audio+visual lock.

### grovio-video
- Apply NeuroScore to script at three checkpoints: hook (0–3s), body (3–30s), CTA.
- Flag any section where D4 score drops below 6 — attention will fall at that timestamp.
- Recommend adding sound design cues where D2 is weak.

### grovio-email
- Subject line: score D4 only (must score 8+, must be simple imperative or curiosity gap).
- Body: score D3 and D1. Body should score 7+ on D3 for goal calibration.
- CTA: score D4 (must be clean action verb, score 8+).

### grovio-landing
- Hero headline: D4 + D5 (simple + pattern interrupt).
- Value prop section: D3 + D1 (rational calibration + cortical coverage via sensory language).
- Social proof section: D3 emotional weighting should rise here.

### grovio-analyze
- Add NeuroScore as a retroactive scoring dimension for historical content audits.
- Correlate NeuroScore with engagement rate to validate which dimensions predict performance for this specific brand/audience.
- Build a brand-specific "winning D-profile" over time (e.g. "this brand's audience responds to high D5 + D3 emotional content").

---

## Implementation Note

The NeuroScore rubrics above are operationalised from published TRIBE v2 findings
and do not require API access to the model weights. For teams wanting live
inference (actual fMRI prediction scores per content piece), the model weights
are available at:

- Weights: https://huggingface.co/facebook/tribev2
- Code: https://github.com/facebookresearch/tribev2
- Demo: https://aidemos.atmeta.com/tribev2

A production integration would pass each content variant through TRIBE v2's
language encoder (Llama 3.2) and return voxel-level activation scores, which
map directly to the 5 NeuroScore dimensions above.
