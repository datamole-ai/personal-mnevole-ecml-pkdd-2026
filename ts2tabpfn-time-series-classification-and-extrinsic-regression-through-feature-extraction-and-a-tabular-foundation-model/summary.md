Conference presentation of S2-TabPFN: extract time-series features (Catch-22, TSFresh, MultiRocket) and feed them to TabPFN for classification and extrinsic regression, matching state-of-the-art at a fraction of the compute.

### Proposal: S2-TabPFN
- Targets time series classification and extrinsic regression, motivated by health signals (e.g. ECG).
- Extracts features via Catch-22, TSFresh, or MultiRocket, then feeds tabular data to pre-trained TabPFN via in-context learning.

### Results
- Classification: MultiRocket+TabPFN best of the three feature sets; ties HIVE-COTE 2.0, beats Rocket with statistical significance.
    - 128 UCR/UEA datasets used; 30 runs each.
- Regression: TSFresh+TabPFN wins, beating FreshPRINCE with statistical significance on 55 datasets.
- Efficiency: 2-100x faster total, up to 700x on inference; 2-40% of the energy of HIVE-COTE 2.0 / FreshPRINCE.

### Limitations & Q&A
- TabPFN memory-heavy on 12GB VRAM; some benchmark datasets dropped rather than handled.
- Raw time series fed directly to TabPFN performed poorly; reason unclear.
- No data leakage: TabPFN pre-trained only on synthetic datasets.
- MultiRocket capped at 5,000 features (TabPFN limit); no learned/custom kernels yet.

### Next Steps
- (<@speaker:1>) Continue follow-up paper on handling TabPFN memory limits for larger datasets.
- (<@speaker:1>) Explore enriching features with motif-based / multi-scale tabular features, potentially for non-segmented long time series.