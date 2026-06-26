# Review criteria — structural papers

Sanity checks and guidance specific to **structural empirical papers**. Use alongside `review_criteria_common.md`.

---

## Structural sanity checks

Run **before** scoring. Answer PASS / FAIL / N/A with one line of cited evidence. **FAIL on a load-bearing item** that the manuscript does not acknowledge → must appear as a **Major concern** with **What would change my mind**.

| Check | What to verify |
|-------|----------------|
| **Structural ID story** | Clear what varies, what is normalised, what identifies key parameters—not slogans. Identification strategy explained, not just asserted. |
| **Selection / Mills** | If selection correction used: motivation for selection, exclusion restrictions or timing, not only "following Heckman." |
| **Model primitives** | Payoffs, timing, information structure clearly specified. Primitives consistent across text and notation. |
| **Functional forms** | Distributional and functional form choices justified or acknowledged as ad hoc. Sensitivity to alternatives discussed. |
| **Estimation method** | MLE, GMM, Bayesian, simulation—appropriate for the model. Moments or likelihood clearly specified. |
| **Fit / validation** | In-sample fit reported. Out-of-sample validation if possible. Model predicts held-out moments or patterns. |
| **Elasticities & magnitudes** | Economically interpretable units and scale; not stars-only. Parameters have economic meaning. |
| **Counterfactual support** | Counterfactuals inside support or extrapolation explicitly flagged. Partial vs general equilibrium clear. |
| **Dependence / clustering** | SE clustering matches the stated unit of dependence (firm, market, time). Bootstrap or analytical SEs appropriate for model. |
| **Computational details** | Optimisation algorithm, starting values, convergence criteria documented. Multiple starts if non-convex. |

---

## Identification in structural models

Key questions to address:

1. **What parameters are identified?** Which primitives can be recovered from the data vs which require normalisation?

2. **What variation identifies them?** Cross-sectional, time-series, within-unit? Is the variation credibly exogenous?

3. **What assumptions are maintained?** Functional forms, distributional assumptions, equilibrium concepts. Which are testable vs untestable?

4. **Robustness to assumptions:** How sensitive are key estimates to alternative functional forms, distributions, or timing assumptions?

5. **External validation:** Can any structural estimates be compared to reduced-form evidence or external benchmarks?

---

## Counterfactual analysis

Evaluate counterfactuals against:

1. **Support:** Are counterfactual scenarios within the support of observed data, or do they require extrapolation?

2. **Equilibrium concept:** Are counterfactuals partial equilibrium (holding some margins fixed) or general equilibrium (allowing all margins to adjust)?

3. **Mechanism consistency:** Do counterfactuals change only the intended margin, or do they inadvertently change other model primitives?

4. **Magnitude plausibility:** Are counterfactual effects plausible relative to observed variation and industry/market benchmarks?

---

## Common structural paper concerns

Typical concerns that referees raise for structural papers:

- "What exactly identifies the key parameters? I don't see credible exogenous variation."
- "The functional form seems to drive the results. What happens with alternatives?"
- "The counterfactuals are extrapolation, not interpolation."
- "Where are the standard errors? How precise are these estimates?"
- "The model doesn't fit well in sample. Why should I trust counterfactuals?"
- "This could be done with reduced-form methods. What does the structure buy?"
- "The equilibrium concept is unclear. What adjusts and what doesn't?"
