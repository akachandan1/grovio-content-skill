# grovio-content Orchestrator Patch — NeuroScore Integration

Add the following block to your existing `skills/grovio-content/SKILL.md` to
wire the NeuroScore engine into the master orchestrator pipeline.

---

## Where to add it

In your current `grovio-content` SKILL.md, Step 5 is "Sub-Skill Activation".
Insert a new **Step 5b** immediately after variant generation and before final
ranked output:

---

## Step 5b — NeuroScore Pass (insert after variant generation)

Before presenting the final ranked output, run each generated variant through
the NeuroScore engine:

```
For each content variant produced by the active sub-skill:
  1. Apply /grovio-neuro scoring rubric inline (no separate invocation needed)
  2. Compute NeuroScore /50 across all 5 dimensions
  3. Add to existing Psych Score /60 → Combined Score /110
  4. Re-rank variants by Combined Score
  5. Flag the single weakest NeuroScore dimension per variant with a 1-line fix
```

---

## Updated Output Format

Replace the current ranked output block with this Combined Score format:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🥇 #1 PUBLISH — [Variant Title]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[Content]

📊 Psych Score:    XX / 60
🧠 NeuroScore:     XX / 50
🏆 Combined:       XX / 110

Brain regions targeted: [visual cortex / TPJ / DMN / ...]
Weakest dimension: D# — [1-line fix suggestion]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🥈 #2 A/B TEST — [Variant Title]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[Content]

📊 Psych Score:    XX / 60
🧠 NeuroScore:     XX / 50
🏆 Combined:       XX / 110

Brain regions targeted: [...]
Weakest dimension: D# — [1-line fix suggestion]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🥉 #3 RESERVE — [Variant Title]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[Content]

📊 Psych Score:    XX / 60
🧠 NeuroScore:     XX / 50
🏆 Combined:       XX / 110

Weakest dimension: D# — [1-line fix suggestion]
```

---

## Goal-Aware NeuroScore Weighting

When a goal flag is detected, weight NeuroScore dimensions accordingly:

| Goal | Highest-weight Dimensions |
|---|---|
| `awareness` | D1 Cortical Coverage, D5 Attention Integration |
| `engagement` / `thought-leadership` | D3 Emotional Calibration, D5 Attention Integration |
| `conversion` | D3 Rational Calibration, D4 Linguistic Complexity |
| `retention` / `loyalty` | D3 Emotional Calibration, D1 Cortical Coverage |
| `ads` | D2 Multimodal Synergy, D4 Linguistic Complexity |
| `video` | D2 Multimodal Synergy, D5 Attention Integration |

---

## Voice Flag Integration

| Voice | NeuroScore adjustment |
|---|---|
| `--voice founder` | Boost D3 emotional weighting. Personal story = higher TPJ activation. Penalise variants scoring <7 on D3. |
| `--voice brand` | Boost D4 linguistic complexity weighting. Brand accounts need rational credibility. Penalise variants scoring <6 on D4 body section. |

---

## Routing Table Update

Add `neuro` as a valid route in the master routing table:

```
| Platform/Goal      | Routes to                        |
|--------------------|----------------------------------|
| neuro / neuroscore | /grovio-neuro (standalone audit) |
| any                | [existing skill] + grovio-neuro  |
```

---

## Installation

```bash
# 1. Copy the new skill into your skills directory
cp -r grovio-neuro ~/.claude/skills/

# 2. The master orchestrator patch is editorial — 
#    manually insert Step 5b into your grovio-content SKILL.md
#    following the instructions above.

# 3. Test with:
/grovio-content https://grovio.ai linkedin thought-leadership --voice founder
```

The orchestrator will now automatically NeuroScore all variants before ranking.
