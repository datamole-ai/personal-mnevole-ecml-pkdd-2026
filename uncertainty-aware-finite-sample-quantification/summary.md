Conference talk introducing finite-sample quantification: a Bayesian-scheme variant that estimates sample-level (not population-level) class prevalences, outperforming standard methods on small samples but not scaling to many classes.

### Motivation: Two Kinds of Quantification
- Standard quantification targets population-level Q(Y); typically assumes prior probability shift
- Some use cases (e.g. classroom vote among 20 students) need sample-level prevalence, not population estimate
- Framed as a discrete best-of-set problem vs. regression over a linear distribution space

### Proposed Method
- Variant of Bayesian scheme (originally from UCL) adapted to discrete sample-level prevalences
    - Replaces posterior target Q(Y) with discrete prevalence S
    - Uses adjusted-classifier-count style estimate from observed data
- Yields closed-form likelihood over all discrete prevalence vectors; scales exponentially with #classes

### Results & Limitations
- On binary UCI datasets, beats Bayesian scheme in MAE and coverage for small samples (<~50–100)
- Advantage disappears beyond ~100–1000 samples; standard quantifiers preferable there
- Tighter, better-calibrated 95% confidence intervals than Bayesian scheme
- Open questions: scalability to many classes; not applicable to differential-privacy settings (full feature access assumed)