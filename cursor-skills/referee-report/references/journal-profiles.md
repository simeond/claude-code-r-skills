# Journal profiles (general)

Calibration data for **journal-calibrated referee reports**. Use with the `referee-report` skill.

**How this file is used.** When generating a referee report with a named target outlet, read the matching profile first. It sets referee disposition weights, typical concerns, and calibration guidance.

**Short names** are the tags you pass in chat (e.g., "calibrate to `MKTSC`").

---

## Schema

Every profile has these fields:

- **Short name** — the string you pass when asking for calibration (e.g., `MKTSC`, `RAND`).
- **Focus** — what the journal publishes; what it does not.
- **Bar** — what it takes to clear the desk; typical readership expectations.
- **Domain-referee adjustments** — how the substantive referee should re-weight dimensions.
- **Methods-referee adjustments** — how the methods referee should re-weight (by paper type: structural vs reduced-form).
- **Typical concerns** — questions a referee at this journal is likely to ask.
- **Referee-pool weights** — weights over dispositions (STRUCTURAL / CREDIBILITY / MEASUREMENT / POLICY / THEORY / SKEPTIC). Weights sum to 1.0.
- **Table format override** (optional) — stars, decimals, notes.

---

## Field journals

### Marketing Science (`MKTSC`)

**Short name:** `MKTSC`

**Focus.** Quantitative marketing: structural models, empirical IO applied to marketing, advertising markets, and firm behaviour. Expect tight link between model, institutional setting, and managerial or welfare implications. Less pure reduced-form unless identification is exceptional.

**Bar.** Contribution must speak to marketing/advertising audiences and cite the right marketing and empirical-IO literature. Structural work must show parameter plausibility, fit, and interpretable counterfactuals.

**Domain-referee adjustments.**
- Contribution & novelty 30% → 32%
- Literature positioning 25% → 27% (marketing + adjacent IO must be fair)
- Fit for target journal 10% → 11%

**Methods-referee adjustments.**
- If **Structural**: parameter identification 30% → 32%, fit / validation 15% → 18%.
- If **Reduced-form**: identification 35% → 38%; expect exceptional design.
- Replication 5% → 8% (expect clean appendix and replication-friendly code narrative).

**Typical concerns.**
- "Does the paper speak to the marketing literature, not only to generic IO papers?"
- "Are parameters/estimates interpretable for practitioners?"
- "Is the identification strategy convincing for this market setting?"
- "Do counterfactuals stay within support, and are magnitudes plausible?"
- "Are institutional details accurate enough that a practitioner would trust the setting?"

**Referee-pool weights.**
- STRUCTURAL: 0.28
- CREDIBILITY: 0.18
- MEASUREMENT: 0.18
- POLICY: 0.12
- THEORY: 0.12
- SKEPTIC: 0.12

**Table format override.** Follow journal author guidelines.

---

### RAND Journal of Economics (`RAND`)

**Short name:** `RAND`

**Focus.** Industrial organisation: theory and empirics, auctions, contracts, firm strategy. Strong appetite for structural work when identification and institutional detail are serious.

**Bar.** IO referees will push on economic mechanism, equilibrium logic, and robustness of supply- and demand-side modelling.

**Domain-referee adjustments.**
- Substantive arguments 20% → 25%
- External validity / scope 15% → 18%

**Methods-referee adjustments.**
- If **Structural**: model specification 20% → 22%, parameter identification 30% → 32%, counterfactuals 15% → 17%.
- If **Reduced-form**: mechanism identification expected; pure documentation less valued.

**Typical concerns.**
- "What is the precise economic mechanism being identified or estimated?"
- "How does this paper relate to the IO literature?"
- "Are assumptions on behaviour, information, or market structure defended—not just asserted?"
- "Would the main results survive reasonable alternative specifications?"

**Referee-pool weights.**
- STRUCTURAL: 0.30
- THEORY: 0.20
- SKEPTIC: 0.18
- CREDIBILITY: 0.12
- MEASUREMENT: 0.12
- POLICY: 0.08

**Table format override.** Follow RAND author instructions.

---

### International Journal of Industrial Organization (`IJIO`)

**Short name:** `IJIO`

**Focus.** Applied IO and competition; receptive to careful structural and reduced-form work on markets with strategic firms. Slightly more tolerance for niche settings if contribution is clear.

**Bar.** Clear IO question, honest about limitations, credible econometrics. Less demand for "general interest" framing than top-5.

**Domain-referee adjustments.**
- Fit for target journal 10% → 8% (journal is broad within IO)
- Literature positioning 25% → 27%

**Methods-referee adjustments.**
- If **Structural**: balance identification 30% and fit 15%; expect transparent estimation.
- If **Reduced-form**: standard credibility checks.

**Typical concerns.**
- "What do we learn about market power, selection, or conduct that we did not know?"
- "Is the model identified conditional on the data?"
- "Are standard errors and clustering credible?"

**Referee-pool weights.**
- STRUCTURAL: 0.22
- CREDIBILITY: 0.22
- SKEPTIC: 0.18
- MEASUREMENT: 0.15
- THEORY: 0.13
- POLICY: 0.10

---

### Management Science (`MS`)

**Short name:** `MS`

**Focus.** Operations, marketing, analytics, and economics-oriented decision problems; structural and empirical methods are welcome when decision-relevant.

**Bar.** Methods should connect to **decisions or welfare** managers, platforms, or policymakers care about. Story must be accessible to a broad OR/MS audience.

**Domain-referee adjustments.**
- External validity / scope 15% → 20%
- Contribution 30% → 28% (policy and decision framing matter)

**Methods-referee adjustments.**
- If **Structural**: counterfactuals 15% → 18%; emphasise clarity of implications.
- If **Reduced-form**: policy relevance weighted heavily.

**Typical concerns.**
- "So what should a firm or platform **do** with these estimates?"
- "Is the exercise transparent enough for non-specialists?"
- "Are data and institutional features described for replication?"

**Referee-pool weights.**
- STRUCTURAL: 0.22
- POLICY: 0.22
- CREDIBILITY: 0.18
- MEASUREMENT: 0.15
- THEORY: 0.12
- SKEPTIC: 0.11

**Table format override.** Follow INFORMS / Management Science table guidance.

---

### American Economic Journal: Microeconomics (`AEJMICRO`)

**Short name:** `AEJMICRO`

**Focus.** High-quality applied micro and IO; structural and reduced-form both publish, with emphasis on **credible claims** and clear contribution to microeconomics.

**Bar.** Tighter writing and higher identification scrutiny than field journals; contribution must be legible to general applied-micro readers.

**Domain-referee adjustments.**
- Contribution 30% → 32%
- External validity 15% → 18%

**Methods-referee adjustments.**
- If **Structural**: parameter identification 30% → 34%; credibility-style checks weighted heavily.
- If **Reduced-form**: identification 35% → 40%.
- Replication 5% → 10%.

**Typical concerns.**
- "Is the identifying variation or assumption convincing?"
- "Does the paper overclaim relative to what the data support?"
- "Are magnitudes and economic significance front and centre?"

**Referee-pool weights.**
- CREDIBILITY: 0.28
- STRUCTURAL: 0.22
- SKEPTIC: 0.16
- MEASUREMENT: 0.14
- POLICY: 0.12
- THEORY: 0.08

**Table format override.** AEJ journals: no significance stars in main tables (SE in parentheses).

---

## General economics flagships

### American Economic Review (`AER`)

**Short name:** `AER`

**Focus.** General-interest economics. Strong bar for importance, credible identification, interpretable magnitudes.

**Bar.** Topic must matter beyond specialists; contribution crisp in one paragraph.

**Domain-referee adjustments.**
- Contribution 30% → 35%
- External validity 15% → 20%
- Fit 10% → 5%

**Methods-referee adjustments.**
- If **Structural**: model must be essential; pure structural less common.
- If **Reduced-form**: identification 35% → 40%.
- Replication 5% → 10%

**Typical concerns.**
- "Is the question important enough for a general-interest journal?"
- "Is identification credible to a skeptical non-specialist?"
- "Does the magnitude tell us something new?"

**Referee-pool weights.** CREDIBILITY 0.30, POLICY 0.25, STRUCTURAL 0.15, MEASUREMENT 0.15, THEORY 0.05, SKEPTIC 0.10.

**Table format override.** No significance stars (AEA policy); SE in parentheses.

---

### Quarterly Journal of Economics (`QJE`)

**Short name:** `QJE`

**Focus.** Identification-first empirical work and sharp theory.

**Bar.** Near-airtight identification; narrow setting acceptable if design is exceptional.

**Domain-referee adjustments.** Substance 20% → 25%.

**Methods-referee adjustments.**
- If **Structural**: must have exceptional identification story.
- If **Reduced-form**: identification 35% → 45%; robustness 15% → 10%.

**Typical concerns.** Clever design vs "another DiD"; teaching value of identification; one-sentence economic insight.

**Referee-pool weights.** CREDIBILITY 0.40, STRUCTURAL 0.20, MEASUREMENT 0.15, POLICY 0.10, THEORY 0.10, SKEPTIC 0.05.

**Table format override.** Three-decimal point estimates common; SE in parentheses.

---

### Journal of Political Economy (`JPE`)

**Short name:** `JPE`

**Focus.** Theory and empirics tied to mechanism and markets.

**Domain-referee adjustments.** Substance 20% → 30%.

**Methods-referee adjustments.**
- If theory+empirics: Model 20% → 30%, prediction sharpness 25% → 30%.
- If reduced-form: identification 35% → 30% with explicit theoretical framing expected.

**Typical concerns.** What theory predicts; magnitudes vs model; specificity of alternative mechanisms.

**Referee-pool weights.** THEORY 0.30, STRUCTURAL 0.25, CREDIBILITY 0.15, MEASUREMENT 0.10, POLICY 0.10, SKEPTIC 0.10.

---

### Econometrica (`ECMA`)

**Short name:** `ECMA`

**Focus.** Econometric theory, structural estimation, formal theory.

**Methods-referee adjustments.**
- If **Structural**: model spec 20% → 30%, parameter ID 30% → 35%.
- If **Reduced-form**: identification 35% → 40%; methodological contribution expected.
- Replication 5% → 10%.

**Typical concerns.** Methodological contribution; formal assumptions; what is new for econometricians.

**Referee-pool weights.** STRUCTURAL 0.30, THEORY 0.25, MEASUREMENT 0.20, CREDIBILITY 0.15, POLICY 0.05, SKEPTIC 0.05.

---

### Review of Economic Studies (`ReStud`)

**Short name:** `ReStud`

**Focus.** Ambitious theory, empirical, and macro; careful reasoning.

**Domain-referee adjustments.** Contribution 30% → 35%; substance 20% → 25%.

**Methods-referee adjustments.** Honesty (theory+empirics) 15% → 20%.

**Typical concerns.** Intellectual arc; honest limitations; generalisability.

**Referee-pool weights.** STRUCTURAL 0.20, CREDIBILITY 0.20, THEORY 0.20, POLICY 0.15, MEASUREMENT 0.15, SKEPTIC 0.10.

---

## Adding new outlets

To add an outlet: copy a full `###` block above, change the short name, and fill every schema field using recent ToCs and desk letters for that journal.
