Conference presentation of TVS-LimeLite, a unified multivariate time-series classification model using triple-view sparse routing (channel, frequency, interaction), followed by brief Q&A on domain-knowledge integration.

### TVS-LimeLite Model
- Dense transformer backbone with sparse branch: channel selection, Fourier-based structure selection, patch-wise expert routing
- Bridge gate controls sparse branch contribution per layer; three selectors are input-dependent

### Results
- Evaluated on 28 datasets (UEA, PMS, HAR) vs 70 baselines; average rank 2.12 vs ITransformer 3.84
- Ablation: triple-view combination adds 2.83 points, larger than any single sparsity gain
- Few-shot transfer with 20% labels: best across three source-target pairs, avg 16.07%

### Q&A
- <@speaker:2> questioned whether model can incorporate domain knowledge (e.g., spatial-temporal layout for traffic)
- <@speaker:4> acknowledged the point, noted use of standard benchmark