# Review criteria — reduced-form papers

Sanity checks and guidance specific to **reduced-form empirical papers** (DiD, event study, RDD, IV, etc.). Use alongside `review_criteria_common.md`.

---

## Reduced-form sanity checks

Run **before** scoring. Answer PASS / FAIL / N/A with one line of cited evidence. **FAIL on a load-bearing item** that the manuscript does not acknowledge → must appear as a **Major concern** with **What would change my mind**.

| Check | What to verify |
|-------|----------------|
| **Design validity** | Treatment and control clearly defined; timing of treatment unambiguous; no contamination of control. |
| **Parallel trends** (DiD) | Pre-treatment trends examined; evidence presented (visual or formal test); limitations acknowledged if imperfect. |
| **SUTVA** | No spillovers between treatment and control; no anticipation effects; treatment does not affect control outcomes. |
| **Event timing** | Event/treatment dates correctly identified; staggered adoption handled appropriately; event windows justified. |
| **First stage** (IV) | Instrument relevance demonstrated; F-statistic or equivalent reported; weak IV concerns addressed. |
| **Exclusion restriction** (IV) | Instrument affects outcome only through endogenous variable; plausibility argued and defended. |
| **Running variable** (RDD) | Running variable manipulation tested; bandwidth selection justified; functional form of running variable appropriate. |
| **Clustering** | Standard errors clustered at appropriate level; clustering matches unit of treatment assignment. |
| **Magnitudes** | Effect sizes reported in economically meaningful units; benchmarked against context or priors. |
| **Heterogeneity** | Subgroup analyses credible; multiple testing addressed or acknowledged; heterogeneity interpretable. |
| **External validity** | Sample representativeness discussed; period/setting relevance for generalisation acknowledged. |

---

## Identification in reduced-form designs

### Difference-in-Differences (DiD)

Key assumptions:
1. **Parallel trends:** Absent treatment, outcomes would have evolved similarly.
2. **No anticipation:** Treatment effect does not occur before treatment.
3. **SUTVA:** Treatment of one unit does not affect outcomes of other units.

What to look for:
- Pre-trend tests (formal and visual)
- Event study plots with pre-period coefficients
- Discussion of what would violate parallel trends
- Placebo tests using pre-treatment "fake" events

Recent literature to engage:
- Goodman-Bacon (2021) on TWFE decomposition
- Callaway and Sant'Anna (2021) on heterogeneous effects
- Sun and Abraham (2021) on event studies
- de Chaisemartin and d'Haultfoeuille (2020) on staggered treatment
- Rambachan and Roth (2023) on sensitivity to parallel trends violations

### Instrumental Variables (IV)

Key assumptions:
1. **Relevance:** Instrument predicts endogenous variable.
2. **Exclusion:** Instrument affects outcome only through endogenous variable.
3. **Independence:** Instrument is as-good-as-randomly assigned.

What to look for:
- First-stage F-statistic (rule of thumb: F > 10)
- Argument for exclusion restriction
- Discussion of LATE vs ATE
- Weak IV robust inference if F is borderline

### Regression Discontinuity (RDD)

Key assumptions:
1. **Continuity:** Potential outcomes are continuous at the cutoff.
2. **No manipulation:** Units cannot precisely manipulate the running variable.

What to look for:
- McCrary density test for manipulation
- Bandwidth selection (optimal vs robust)
- Sensitivity to polynomial order and bandwidth
- Covariate balance at the cutoff

---

## Common reduced-form paper concerns

Typical concerns that referees raise:

- "The pre-trends look noisy. How do I know parallel trends holds?"
- "This is a null result—is it a power issue?"
- "60-day windows may miss longer-run adjustment."
- "What is the mechanism? You document an effect but don't explain it."
- "The exclusion restriction is not convincing."
- "Your sample is not representative. Do results generalise?"
- "You don't engage the recent DiD literature on staggered treatment."
- "What about equilibrium effects? Partial equilibrium may miss important responses."
- "The heterogeneity analysis involves multiple testing."
