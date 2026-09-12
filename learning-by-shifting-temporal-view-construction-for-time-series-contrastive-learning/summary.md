Presentation of a new self-supervised contrastive learning paper for time series, proposing deterministic window shifting as the view construction, which outperformed baselines across six datasets while running faster.

### Motivation
- Labeled time-series data is scarce; supervised labeling is costly and caps generalization to what humans know
- Prior contrastive methods import CV-style augmentations (jitter, scaling, masking), ignoring temporal dynamics and needing domain tuning

### Proposed Method
- Given one instance (assumed single underlying class), take a window and a shifted window as the two contrastive views
- Preserves data maximally, minimal domain assumptions, uses SimCLR-style shared encoder + NT-Xent loss

### Results & Findings
- Beats baselines on KNN zero-shot, clustering (ARI/NMI), and linear probe across 6 large datasets plus UCR/UEA archives
- Faster than SimCLR-style baselines using the same NT-Xent loss, since shifted views use fewer timestamps
- Projection layer helps; linear vs non-linear doesn't matter; batch size gains plateau past 256
- Embeddings form compact clusters and disentangle seemingly tight ones; shift invariance may be 'all you need'