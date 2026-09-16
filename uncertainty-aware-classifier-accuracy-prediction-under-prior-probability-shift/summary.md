Conference-style talk presenting three uncertainty-aware methods (SPSH, SPSS, and a Bayesian "beta" method) for classifier accuracy prediction under prior probability shift, with SPSH giving the best overall balance.

### Problem & Motivation
- Under prior probability shift, cross-validated accuracy is biased; bias tied to diagonal of conditional rate matrix and prevalence gap
- Goal: move beyond point estimates to uncertainty-aware accuracy prediction, evaluating both point quality and interval quality

### Proposed Methods
- SPSH (hard prevalence matching): sample validation set matching quantifier-predicted target prevalence
- SPSS (soft prevalence matching): split validation, train quantifier on half, nearest-neighbor match on prevalence to absorb quantifier error
- Beta: Bayesian model of source/target prevalence and conditional rates, MCMC-sampled posterior; inherently uncertainty-aware, supports priors

### Experiments & Results
- 15 UCI datasets, 5 classifiers, 3 SOTA CAP baselines; metrics: accuracy error and window score
    - Baselines made uncertainty-aware via bootstrap for fair comparison
- SPSH best overall; baselines competitive on point estimate, SPSS and beta competitive on interval quality
- Coverage vs amplitude plots: SPSH dominates favorable top-left region across classifier/dataset combinations

### Future Work
- Explore other shift types; deeper study of beta with informative priors and posterior uncertainty calibration