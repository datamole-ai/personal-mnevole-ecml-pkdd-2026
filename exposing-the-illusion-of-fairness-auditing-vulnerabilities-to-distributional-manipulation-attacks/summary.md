Conference-style presentation on auditing fairness in binary classification models, showing how auditees can "fair-wash" samples to hide disparate impact and how statistical tests can detect such manipulation.

### Problem Setup
- Auditee holds full dataset + binary classifier; auditor computes disparate impact on a sample; supervisor has full access.
- Core question: can auditee submit a sample that passes audit yet stays close enough to original to evade supervisor detection?

### Fair-Washing Methods & Detection
- Manipulation minimizes distributional distance (Wasserstein, etc.) subject to raising fairness metric above threshold.
- Detection uses 7 statistical tests, incl. Kolmogorov-Smirnov-style and 3 distance-based tests (Wasserstein, TV, additive).
- Clear trade-off: larger fairness gain → larger distributional distance → higher detection probability.

### Results & Takeaways
- Undetected fairness gains vary widely by dataset: ENC 0.67→0.93, POC only 0.72→0.75.
- Combining complementary tests and using larger audit samples materially improves detection.
    - Wasserstein-based test computationally heavy at ~10^7 points.

### Q&A
- <@speaker:2> asked about non-distributional dataset characteristics; <@speaker:1>: low outcome mean (e.g. ENF anomaly detection) makes small manipulations shift fairn