Conference presentation of Lemmon, an incremental multi-target framework for cryptocurrency price and trend forecasting, followed by Q&A on domain features, outlier weighting in regression, and alternative metrics.

### Problem & Motivation
- Crypto market highly volatile; stakeholders need swing forecasts from up-to-date models
- Existing models fail on 3 fronts: batch-only, treat coins in isolation, smooth out outliers

### Lemmon Framework
- Temporal clustering of coins via DTW + K-Medoids, re-run every T_update instances
- Dynamic distance-based instance weighting using stream-adaptive boundaries (p-bottom, p-middle, p-top)
    - Cubic interpolation between boundaries; extremes get highest weight (10 vs 1)
- Per-cluster incremental multi-target Hoeffding regression tree; weights aggregated via max

### Experiments & Results
- 16 cryptocurrencies, hourly data Jan 2020–Dec 2022, 55 features; regression + 3-class trend tasks
- Lemmon pre-trained batch beats ScarBot and single-target LSTM baselines on MSE and F1, ranks first
- Ablation confirms weighting schema and extreme-value emphasis both improve results

### Q&A Discussion
- Debate on weighting outliers in regression: MSE already penalizes them, may destroy fit on normal values
- Suggestions raised: incorporate marketing/selling info, time dependence, volume/time-weighted metrics

### Next Steps
- (<@speaker:1>) Introduce a drift detector to trigger re-clustering automatically instead of fixed T_update
- (<@speaker:1>) Add economic utility evaluation to the assessment