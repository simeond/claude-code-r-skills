---
name: viva-qa
description: >-
  Generate PhD viva preparation Q&A from existing referee reports. Synthesises
  Major Concerns, Referee Objections, and DA findings across multiple journal
  calibrations into exam-style questions with best answers. Works for any paper
  with referee reports in the standard format. Auto-detects paper type
  (structural vs reduced-form) to generate appropriate questions.
globs:
  - "**/referee_report/*.md"
  - "**/reviews/*.md"
---

# Viva Q&A Generator

Synthesise referee reports into a comprehensive viva preparation document. The output helps candidates prepare for oral examination by converting referee concerns into question-answer pairs with strategic guidance.

## Trigger phrases

- "generate viva questions", "viva prep", "prepare for viva"
- "create Q&A from referee reports"
- "viva preparation", "oral exam prep"

## What you must not do

- **Do not** edit manuscript chapters, appendices, or analysis code.
- **Do not** modify existing referee reports.
- **Only** create/update files in the designated output directory.

---

## Inputs

1. **Paper path** — Root directory of the paper. If not specified, infer from context or ask.
2. **Referee report directory** — Typically `assets/referee_report/` or `reviews/`. Auto-detect if not specified.
3. **Paper type** — `structural` or `reduced-form`. Auto-detect from referee reports if not specified.
4. **Target word count** — Default 8,000–12,000 words. Can be adjusted.
5. **Specific focus** (optional) — Particular topics or concerns to emphasise.

---

## Output path and filename

- **Directory:** `{paper_path}/assets/referee_report/` or `{paper_path}/assets/viva/`
- **Pattern:** `{NN}_{paper_short}_viva_QA.md`
  - `{NN}` — sequential number (e.g., `01`, `02`)
  - `{paper_short}` — short paper identifier derived from paper directory name
  - Example: `01_itp_viva_QA.md`, `03_pmp_viva_QA.md`

---

## Workflow

### Phase 1: Gather inputs

1. **Locate referee reports** — Read all `*.md` files in the referee report directory that match:
   - Timestamped pattern (`YYYYMMDD*.md`)
   - Contain "referee" in the filename
   - Are in `reviews/` directory
2. **Read the manuscript** — Skim key sections to understand:
   - The research question and main contribution
   - The empirical/structural approach
   - Key quantitative findings
   - Stated limitations
3. **Detect paper type** — From referee reports (sanity check table type) or manuscript content.

### Phase 2: Extract and tabulate concerns

1. **Parse each referee report** for:
   - **Major Concerns (MCs)** — extract title, dimension, issue, severity
   - **Referee Objections (ROs)** — extract question and why it matters
   - **Devil's Advocate (DA)** — extract strongest counter-argument, severity
   - **Dimension ratings** — overall scores per journal
   - **Journal name** — for cross-tabulation

2. **Build concern frequency table** — Identify concerns that appear across multiple reports. Recurring concerns are high-priority viva topics.

3. **Identify unique concerns** — Journal-specific issues that only one outlet flagged.

### Phase 3: Generate Q&A structure

Follow the template in `templates/viva_template.md`. Create questions that:

1. **Map directly to referee concerns** — Every MC and RO should generate at least one question.
2. **Anticipate follow-ups** — For each major question, include likely follow-up probes.
3. **Provide strategic answers** — Include:
   - **Best Answer** — What to say
   - **Why this works** — Strategic reasoning
   - **Follow-up to anticipate** — Next question and response

### Phase 4: Organise into parts

| Part | Content | Source |
|------|---------|--------|
| Summary table | Concern × Journal matrix | All reports |
| Part 1: Big Picture | Contribution, importance, "why care?" | MCs on argument, fit |
| Part 2: Method/Model | Identification, assumptions, specification | MCs on ID, specification |
| Part 3: Results | Magnitudes, interpretation, robustness | MCs on results, ROs |
| Part 4: Tough Questions | Limitations, alternatives, extensions | DA section, ROs |
| Part 5: Quick-Fire | Table of challenges and responses | All concerns |
| Key Takeaways | Strategic advice | Synthesis |
| Numbers to Memorise | Key statistics from manuscript | Manuscript scan |

### Phase 5: Write and save

1. Generate the full document using the template.
2. Ensure word count is within target range.
3. Save to the output directory.
4. Report the file path to the user.

---

## Question types by paper type

### Big Picture Questions (all papers)
- "In one sentence, what is your thesis about?"
- "What is the single most important contribution?"
- "Why should economists outside [field] care?"

### Method Questions — Structural papers
- "Walk me through the identification strategy. What identifies [key parameter]?"
- "How are [parameters] identified separately from [other parameters]?"
- "Why this functional form? What if you used alternatives?"
- "Explain the counterfactual exercise. Is it within support?"
- "What is identified vs what is normalised?"

### Method Questions — Reduced-form papers
- "What variation identifies your effect?"
- "Defend your parallel trends assumption."
- "What would violate SUTVA in your setting?"
- "Why this event window? Could you miss longer-run effects?"
- "How do you address the recent staggered DiD literature?"

### Results Questions (all papers)
- "Your [estimate] seems [large/small]. Is that plausible?"
- "What drives [pattern] over time / across groups?"
- "How robust is [finding] to [alternative]?"
- "Why is [heterogeneity pattern] observed?"

### Tough Questions (all papers)
- "Convince me the [approach] is necessary. Couldn't you use [simpler method]?"
- "Your model ignores [factor]. How can you trust the results?"
- "What is the policy implication?"
- "What would you do differently if starting today?"

### Quick-Fire Challenges (all papers)
- "Your sample ends in [year]—isn't it outdated?"
- "You only have one data source."
- "[Methodological choice] is arbitrary."
- "No [welfare/mechanism] analysis."
- "Why [software/language] for estimation?"

---

## Thoroughness contract

- **Minimum questions:** 20 substantive Q&A pairs for full paper
- **Coverage:** Every MC and RO should map to at least one question
- **Numbers table:** Extract and list 10–15 key statistics from the manuscript
- **Strategic guidance:** Each major question includes "Why this works" explanation
- **Honest limitations:** Acknowledge gaps directly; provide concrete plans to address

---

## File map (this skill)

| File | Role |
|------|------|
| `SKILL.md` | Orchestration, workflow, question types |
| `templates/viva_template.md` | Output structure and formatting |

---

## Principles

- **Anticipate, don't just report** — The goal is to prepare the candidate, not summarise reports.
- **Strategic honesty** — Teach when to acknowledge limitations directly.
- **Concrete answers** — Avoid vague responses; include specific numbers and citations.
- **Follow-up chains** — Major topics should include anticipated follow-up exchanges.
- **Examiner psychology** — Examiners respect candidates who understand their own work's limits.
- **Paper-type appropriate** — Use question templates appropriate for structural vs reduced-form.
