Conference talk presenting Relief 100K, a 100K+ cell retired-battery dataset, a unified benchmark of 11 time-series models, and KPCLR, a lightweight contrastive-learning model achieving 1.83% MAPE.

### Motivation & Challenges
- Retired EV batteries need accurate remaining-capacity estimation for safe reuse, fair pricing, and avoiding waste.
- Three gaps: small public datasets, inconsistent protocols, and large models unsuitable for BMS/edge deployment.

### Relief 100K Dataset
- 100K+ cells across 8 nominal capacities (15.5–105 Ah); vs Battery Life's 990 cells.
    - Each cell contributes one full charge-discharge cycle, emphasizing inter-battery variability.
- Charge-to-estimate: predicts FCC from charging-phase voltage/current only, no full discharge needed.

### Benchmark & KPCLR Model
- Unified benchmark of 11 time-series models (MLP-LSTM, PCN, CNN, Time Snags, HTST, SparseTSF, Time Mixer, etc.), curves downsampled to 512 points.
- KPCLR: 1D-CNN encoder with contrastive pre-training + 3-layer MLP regressor; 1.68M params (~1/11 of Time Snags).

### Results & Next Directions
- KPCLR best avg MAPE 1.83%; Time Snags 1.91%; HTST 4.73%. Removing contrastive pre-training raises MAPE to 4.38%.
- Future: multi-cycle temporal degradation, new battery types, cross-chemistry transfer learning. Dataset and code on GitHub.