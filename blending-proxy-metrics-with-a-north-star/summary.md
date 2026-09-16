`<name>` presented Netflix's approach to A/B test decision-making: blending a sensitive proxy metric with a noisier North Star, with optimal weighting derived from signal, noise, and sample size.

### Problem Framing
- Netflix innovates via A/B tests, but retention (North Star) is too insensitive for subtle UI/algorithm changes.
- Teams use sensitive proxies (engagement, thumbs up, streaming time) alongside retention; the two can disagree.

### Optimal Metric Blending
- Formalized as weighted blend of noisy proxy P and true outcome Y, with weights chosen to maximize launch returns.
- Optimal weight is signal/noise-driven: large experiments lean on North Star, small/noisy ones lean on proxy.
    - Signal and noise covariance matrices learned directly from Netflix's large pool of experiments.
- Better proxies allow smaller experiments, enabling more concurrent tests (e.g. 30 → 300) and faster innovation.

### Empirical Application
- Clicks (proxy) vs plays (North Star) in a testing area: strong but imperfect correlation.
- At typical ~5M-member experiment, optimal blend is roughly 50/50; shifts with sample size.

### Q&A
- North Star is contextual, like a funnel: Netflix-wide it's long-term revenue/retention; smaller teams pick intermediate outcomes like plays.