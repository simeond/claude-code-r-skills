---
name: referee-report
description: >-
  Journal-calibrated referee report for academic papers. Auto-detects paper type
  (structural vs reduced-form) and applies appropriate sanity checks. Supports
  full (3.5–5.5k words), quick (800–1200 words), and re-review modes. Accepts
  any paper path and journal short name(s). Writes timestamped markdown to the
  paper's assets/referee_report/ directory.
globs:
  - "**/*.qmd"
  - "**/*.Rmd"
  - "**/papers/**"
---

# Referee Report (journal-calibrated, general)

Produce a referee report on any academic paper, calibrated to a named outlet. Auto-detects paper type and applies appropriate review criteria.

## What you must not do

- **Do not** edit manuscript chapters, appendices, or analysis code.
- **Only** create/update files under the paper's **`assets/referee_report/`** directory.
- See **Anti-patterns** in `references/review_criteria_common.md`—violations are skill failures.

---

## Inputs (required)

1. **Paper path** — Root directory of the paper (e.g., `_project/papers/draft_pmp_paper/`). If not provided, infer from context or ask.
2. **Target journal(s)** — One or more **short names** from `references/journal-profiles.md` (e.g. `MKTSC`, `RAND`, `AEJMICRO`, `AER`, `QJE`). If ambiguous or missing, ask once.

## Inputs (optional)

3. **Paper type** — `structural` or `reduced-form`. If not specified, auto-detect from manuscript content.
4. **Scope** — Full paper (default) or named chapter(s)/section(s).
5. **Mode** — `full` (default), `quick`, or `re-review`.
6. **Prior report** (re-review only) — Path to an existing referee report.

---

## Modes

| Mode | Trigger phrases | Word target | Template |
|------|----------------|-------------|----------|
| **`full`** (default) | "referee report", "full review" | 3,500–5,500 (full paper) / 1,500–2,500 (chapter) | `templates/report_template.md` § Full |
| **`quick`** | "quick review", "quick report" | 800–1,200 | `templates/report_template.md` § Quick |
| **`re-review`** | "re-review", "check revisions", "verify against [prior]" | 1,000–2,000 | `templates/report_template.md` § Re-review |

---

## Auto-detection of paper type

If paper type is not specified, detect from manuscript content:

### Structural indicators (use `review_criteria_structural.md`)
- Keywords: "structural model", "counterfactual", "welfare", "elasticity", "selection correction", "Mills ratio", "dynamic factor", "estimation", "identification assumption"
- File patterns: Julia/Stan/MATLAB code, simulation files
- Methodology: mentions of MLE, GMM, Bayesian estimation, Heckman correction

### Reduced-form indicators (use `review_criteria_reduced_form.md`)
- Keywords: "difference-in-differences", "DiD", "event study", "parallel trends", "SUTVA", "regression discontinuity", "instrumental variable", "natural experiment"
- Methodology: TWFE, treatment effects, ATT/ATE

If unclear, ask the user: "Is this a structural or reduced-form paper?"

---

## Output path and filename

- **Directory:** `{paper_path}/assets/referee_report/`
- **Create** the directory if it does not exist.
- **Pattern:** `YYYYMMDDhhmm_{JOURNAL}.md`
  - `YYYYMMDD` calendar date; `hhmm` 24-hour local time.
  - `{JOURNAL}` uppercase short name.
  - Example: `202606261200_MKTSC.md`.
- **Quick mode:** append `_QUICK` → `202606261200_MKTSC_QUICK.md`.
- **Re-review:** append `_RR` → `202606261200_MKTSC_RR.md`.

---

## Workflow — full mode (default)

For one journal run 1–12; for several, run **1–3** once then repeat **4–12** per journal.

1. **Identify paper path** — Confirm or infer from context.
2. **Read manuscript files** — All `.qmd` or `.Rmd` files in scope. Identify:
   - Title, authors, abstract
   - Research question and contribution
   - Methodology (structural vs reduced-form)
   - Key quantitative findings
   - Stated limitations
3. **Detect paper type** — Structural or reduced-form (or ask if unclear).
4. **Read journal profile** from `references/journal-profiles.md`.
5. **Read review criteria** — Load the appropriate file:
   - `references/review_criteria_structural.md` for structural papers
   - `references/review_criteria_reduced_form.md` for reduced-form papers
   - `references/review_criteria_common.md` for shared guidance
6. **Complete sanity checks** — Every load-bearing FAIL → MC with **What would change my mind**.
7. **Work through all six dimensions** (Argument, Identification, Specification, Literature, Writing, Presentation).
8. **Journal fit:** judge against **Focus** and **Bar** from the profile.
9. **Weave in ≥3** of the profile's **Typical concerns**.
10. **Major concerns** (≥3 for full paper); **Referee objections** (4–5); **Devil's advocate** section with severity.
11. **Dimension ratings** 1–5 with justification; **overall** holistic.
12. **Revision roadmap** — prioritised P0/P1/P2 table.
13. Write the report using `templates/report_template.md`.

### Multiple journals

When the user requests several outlets at once:
1. Read the manuscript **once**.
2. For **each** journal, produce a **fresh** report — calibration, fit, emphasis may **legitimately differ**.
3. Use **one shared timestamp** for the batch.
4. One file per journal.
5. List all written paths in chat.

---

## Workflow — quick mode

1. Read manuscript in scope.
2. Read journal profile + review criteria.
3. Run sanity checks (abbreviated: PASS/FAIL only).
4. Identify **top 3 issues** (each with What would change my mind).
5. **2 key strengths**.
6. **Recommendation** + 1-paragraph justification.
7. **Dimension snapshot** (1–5, no justification).
8. Write using Quick mode template.

---

## Workflow — re-review mode

1. Read **prior report** (must be in `assets/referee_report/`).
2. Read **current** manuscript.
3. Read journal profile.
4. For each prior MC, RO, DA finding, classify: **RESOLVED / PARTIAL / NOT ADDRESSED**.
5. Flag **new issues** introduced by revision.
6. **Updated recommendation** and **dimension ratings** (prior → current).
7. **Residual revision roadmap**.
8. Write using Re-review mode template.

---

## Thoroughness contract (full mode)

- **Full paper:** 3,500–5,500 words; **chapter:** 1,500–2,500.
- **≥2** genuine strengths; **≥3** major concerns.
- **4–5** referee objections (3–4 for chapter).
- **Devil's advocate** section with severity.
- **Revision roadmap** mapping all actionable items.
- **No fabricated** evidence, tables, or citations.
- **Do not** rewrite paragraphs; diagnose and point to fixes.

---

## File map (this skill)

| File | Role |
|------|------|
| `SKILL.md` | Orchestration, modes, workflow |
| `references/journal-profiles.md` | Outlet calibration data |
| `references/review_criteria_common.md` | Shared dimensions, DA framework, anti-patterns |
| `references/review_criteria_structural.md` | Sanity checks for structural papers |
| `references/review_criteria_reduced_form.md` | Sanity checks for reduced-form papers |
| `templates/report_template.md` | Output templates for all modes |

---

## Principles

- Constructive: every MC has an actionable path.
- Specific: cite sections, equations, tables, phrases.
- Decisive: distinguish fatal from polish.
- Paper-type appropriate: use correct sanity checks.
- Apply the **iron rule** on DA CRITICAL findings.
