# Referee report — output templates

Templates for the saved `.md` files. Read this when writing the report.

---

## Full mode template

Used for default (`full`) reviews — both single-journal and batch.

```markdown
# Referee report: [paper title]

**Generated:** [YYYY-MM-DD HH:MM local]
**Journal:** [full name] (`SHORT`)
**Mode:** full
**Paper type:** [Structural / Reduced-form]
**Manuscript scope:** [paths]
**Output file:** [this filename]

## Journal calibration (from profile)

**Focus:** …
**Bar:** …
**Emphasis for this review:** [2–4 sentences: how referee-pool weights shape your lens for this paper type]
**Table / presentation note:** [from profile override, or "none specified"]

## Summary assessment

**Overall recommendation:** [Strong Accept / Accept / Revise & Resubmit / Major Revision / Reject]

[3–5 paragraphs: contribution, fit to *this* journal, main strengths, central risks, verdict]

## Fit for [SHORT]

[1–2 paragraphs: would readers and editors at this journal see this as on-bar? What is the main fit risk?]

## Sanity checks

[Use appropriate table based on paper type]

### For structural papers:

| Check | PASS / FAIL / N/A | Evidence (from text) |
|-------|-------------------|----------------------|
| Structural ID story | | |
| Selection / Mills | | |
| Model primitives | | |
| Functional forms | | |
| Estimation method | | |
| Fit / validation | | |
| Elasticities & magnitudes | | |
| Counterfactual support | | |
| Dependence / clustering | | |
| Computational details | | |

### For reduced-form papers:

| Check | PASS / FAIL / N/A | Evidence (from text) |
|-------|-------------------|----------------------|
| Design validity | | |
| Parallel trends | | |
| SUTVA | | |
| Event timing | | |
| Clustering | | |
| Magnitudes | | |
| Heterogeneity | | |
| External validity | | |

## Strengths

1. …
2. …
3. …

## Major concerns

### MC1: [title]
- **Dimension:** [Argument / Identification / Specification / Literature / Writing / Presentation]
- **Severity:** major
- **Issue:** [2–3 sentences]
- **Location:** [section / equation / table]
- **Suggestion:** [how to address]
- **What would change my mind:** [specific evidence or revision]

[repeat for each MC; minimum 3 for full-paper]

## Minor concerns

- [grouped bullets]

## Referee objections

### RO1: [adversarial question]
**Why it matters:** …
**How to address:** …

[4–5 for full paper]

## Devil's advocate

### Strongest counter-argument

[200–300 words: the single best line of attack on the paper's central claim]

### Ignored alternative explanations

1. …
2. …
3. …

### Cherry-picking / confirmation bias

[Does the paper only show confirming results? Are nulls buried?]

### "So what?" test

[If the estimate is correct, does it matter for welfare / decisions / policy?]

**DA severity:** [CRITICAL / MAJOR / MINOR]
**If CRITICAL:** Overall recommendation cannot be Accept (iron rule).

## Dimension ratings

| Dimension | 1–5 | Justification |
|-----------|-----|----------------|
| Argument structure | | |
| Identification | | |
| Econometric / structural spec | | |
| Literature positioning | | |
| Writing quality | | |
| Presentation | | |
| **Overall** | | |

## Revision roadmap

| Priority | Item | MC/RO/DA ref | Location | Verification |
|----------|------|-------------|----------|--------------|
| P0 | … | MC1 | §5, eq. 3 | [how to confirm it is fixed] |
| P1 | … | RO2 | §6, Table 4 | … |
| P2 | … | minor | §2 | … |

[All MCs should map to P0 or P1; all minors to P2; DA CRITICAL → P0]
```

---

## Quick mode template

Used when the user asks for `quick` / "quick review."

```markdown
# Quick referee report: [paper title]

**Generated:** [YYYY-MM-DD HH:MM local]
**Journal:** [full name] (`SHORT`)
**Mode:** quick
**Paper type:** [Structural / Reduced-form]
**Manuscript scope:** [paths]
**Output file:** [this filename]

## Sanity checks (abbreviated)

[Use appropriate table for paper type — PASS/FAIL/N/A only, no evidence column]

## Top 3 issues

### 1. [title]
- **Dimension:** …
- **Issue:** …
- **What would change my mind:** …

### 2. …

### 3. …

## Key strengths

1. …
2. …

## Recommendation

**Overall:** [Strong Accept / Accept / Revise & Resubmit / Major Revision / Reject]
[1 paragraph justification]

## Quick dimension snapshot

| Dimension | 1–5 |
|-----------|-----|
| Argument structure | |
| Identification | |
| Econometric / structural spec | |
| Literature positioning | |
| Writing quality | |
| Presentation | |
| **Overall** | |
```

---

## Re-review mode template

Used when the user provides a **prior report** and asks whether revisions addressed its concerns.

```markdown
# Re-review: [paper title]

**Generated:** [YYYY-MM-DD HH:MM local]
**Journal:** [full name] (`SHORT`)
**Mode:** re-review
**Prior report:** [filename of prior report]
**Manuscript scope:** [paths]
**Output file:** [this filename]

## Traceability matrix

| Prior ref | Prior concern | Status | Evidence in revision | Residual risk |
|-----------|--------------|--------|---------------------|---------------|
| MC1 | [short title] | RESOLVED / PARTIAL / NOT ADDRESSED | [cite section or change] | [remaining issue, if any] |
| MC2 | … | … | … | … |
| RO1 | … | … | … | … |
| DA (if CRITICAL) | … | … | … | … |

## New issues introduced by revision

[Only flag **new** problems the revision created; do NOT invent concerns that were not in scope]

### NEW1: [title]
- **Issue:** …
- **Location:** …
- **Suggestion:** …

## Updated recommendation

**Previous recommendation:** [from prior report]
**Current recommendation:** [Strong Accept / Accept / Revise & Resubmit / Major Revision / Reject]

[1–2 paragraphs: what shifted, what remains]

## Updated dimension ratings

| Dimension | Prior | Current | Change rationale |
|-----------|-------|---------|-----------------|
| Argument structure | | | |
| Identification | | | |
| Econometric / structural spec | | | |
| Literature positioning | | | |
| Writing quality | | | |
| Presentation | | | |
| **Overall** | | | |

## Residual revision roadmap

| Priority | Item | Status | Verification |
|----------|------|--------|--------------|
| P0 | … | NOT ADDRESSED | … |
| P1 | … | PARTIAL | … |
```
