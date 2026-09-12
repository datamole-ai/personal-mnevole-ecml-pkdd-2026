Conference-style talk proposing a decision-tree quantification method (LEPM) that treats leaves as a discrete partition and applies iterative Bayesian unfolding. It performs well on binary tasks but poorly on multi-class.

### Motivation & Method
- Decision trees underperform as base classifiers for quantification and are often miscalibrated
- Proposed LEPM: treat tree leaves as discrete feature-space partition, apply iterative Bayesian unfolding to leaf counts
- Evaluated split criteria: Gini, CEB (quantification-oriented), and hybrid CQE balancing

### Experimental Results
- Binary: SLV best on CPD/CDE trees; LEPM best on Gini trees; ACC underperforms
- Multi-class: LEPM performs poorly, echoing KDEyML findings on discretizing class conditionals as classes grow
- ~30% of trials produced degenerate trees (single split or pruned to root), a key limitation

### Limitations & Future Work
- No hyperparameter tuning; temperature scaling likely hurt calibration, try alternatives
- Next: ensembles via held-out estimation set, heuristics for degenerate trees, more datasets, hyperparameter sweeps