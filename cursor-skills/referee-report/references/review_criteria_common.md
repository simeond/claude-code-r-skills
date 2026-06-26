# Review criteria — common (shared across paper types)

Reference material for `~/.cursor/skills/referee-report/SKILL.md`. Read this file for every review, regardless of paper type.

---

## Review dimensions (deep prompts)

Use every heading that applies. Mark "N/A for this section" with a one-liner if genuinely inapplicable.

### 1. Argument structure

- Research question and mechanism early; intro leads with **stakes**, not methodology.
- Logical arc: question → context → method → results → implications.
- Contribution vs **closest** prior work — what **exactly** is new?
- Section scope: one job per section; anything overloaded or redundant?

### 2. Identification strategy

- For **structural papers**: see `review_criteria_structural.md`.
- For **reduced-form papers**: see `review_criteria_reduced_form.md`.
- Threats engaged: omitted variables, reverse causality, measurement error, selection.
- Robustness: **targeted** (addresses named threat) vs **theatre** (many unrelated specs)—call out theatre.

### 3. Econometric / empirical specification

- Model specification clearly stated; assumptions justified.
- SE clustering level and type; match to unit of analysis.
- Power / precision: CIs narrow enough for economic significance.
- Table discipline: magnitudes + uncertainty together; avoid significance-only reading.

### 4. Literature positioning

- Right benchmarks cited and **fairly characterised**.
- Contribution vs closest substitutes: reader sees the gap.
- Missing cites for mechanism or institutional claims.
- Overclaiming ("first", "only", "definitive") unsupported by the analysis.

### 5. Writing quality

- Concrete domain terms—not vague "entities" / "participants."
- Abstract packs question, method, headline quantitative finding, contribution.
- Signposting across long technical sections; jargon defined once.

### 6. Presentation

- Figures/tables standalone: labels, units, sample, notes, sources.
- Notation consistent; symbols not recycled with different meanings.
- Data description sufficient for sceptic to picture selection and setting.
- Typo / formatting issues undermining confidence.

---

## Devil's advocate (adversarial lane)

After completing dimensions and MCs, step back and adopt the **strongest adversary** perspective. Ask:

1. **Strongest counter-argument** (200–300 words) — If you were trying to *kill* the paper, what single line of attack would you pursue? Frame it as a complete objection, not a question.
2. **Ignored alternative explanations** — List 2–3 plausible mechanisms or data stories the paper does not rule out.
3. **Cherry-picking / confirmation bias** — Does the paper only show results that confirm the theory? Are negative or null findings buried?
4. **"So what?" test** — If the central estimate is correct, does it actually matter for welfare, firm behaviour, or policy? Is the magnitude large enough?

### CRITICAL severity rule

If the DA analysis identifies a concern that is **genuinely fatal** (would cause desk-reject at the target journal if noticed), mark it **CRITICAL** and state the rule:

> **Iron rule:** If any DA issue is marked CRITICAL and unresolved in the manuscript, the overall recommendation **cannot** be Accept or Strong Accept.

CRITICAL should be rare (≤1 per report typically). Most DA findings will map to existing MCs or ROs at MAJOR/MINOR level.

---

## Dimension ratings (1–5 anchors)

| Score | Meaning |
|-------|---------|
| **1** | Fatal or fundamentally incomplete for that dimension |
| **2** | Major weaknesses; would likely drive major revision |
| **3** | Competent; typical revise-and-resubmit gaps |
| **4** | Strong; minor gaps only |
| **5** | Outstanding; rare to give unless clearly earned |

**Overall** is a holistic paper-level judgment (not the arithmetic mean of six numbers unless you explicitly defend that).

---

## Revision roadmap

After all MCs, minor concerns, ROs, and DA findings, produce a **prioritised action table**. This translates the report into an actionable backlog.

| Priority | Label | Meaning |
|----------|-------|---------|
| **P0** | Must fix | Fatal or blocking for the decision; paper cannot advance without this |
| **P1** | Should fix | Major issues; addressing them shifts the decision by one notch |
| **P2** | Nice to fix | Minor polish; strengthens but not binding on decision |

Each row: priority, short title (link to MC/RO/DA number), section/table/equation, suggested verification.

---

## Anti-patterns (do NOT do these)

| # | Anti-pattern | Why it fails | Correct behaviour |
|---|-------------|-------------|-------------------|
| 1 | **Fabricated evidence** | Citing results, tables, or papers not in the manuscript | Every claim must trace to a specific section, equation, or table |
| 2 | **Vague criticism** | "The methodology could be stronger" without location or fix | Every MC/RO: what is wrong, where, and what would resolve it |
| 3 | **Copy-paste across journals** | Identical report with header swap when batching | Calibration, fit, emphasis must genuinely differ per outlet |
| 4 | **Editing the manuscript** | Rewriting paragraphs, modifying source files | Read-only; diagnose and point to the problem |
| 5 | **Contradicting sanity checks** | Giving a high ID score despite a FAIL on core assumption | Sanity-check FAILs are load-bearing; relevant dimension ≤3 |
| 6 | **Sycophantic inflation** | All scores 4–5 with no substance | If MCs are major, at least one dimension must be ≤3 |
| 7 | **Score without justification** | "Identification: 4" and nothing else | Every dimension row must have a one-line justification |
| 8 | **Inventing concerns for length** | Padding with generic issues | Be honest; if the paper is strong, say so and flag residual risks |
