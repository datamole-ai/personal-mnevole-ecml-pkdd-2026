Conference presentation introducing DSW, a subsequence-to-subsequence alternative to DTW that trades a small accuracy cost for more interpretable, noise-tolerant time series alignment. Q&A covered multivariate handling and computational complexity.

### Motivation & Background
- Goal: interpretable matching of time series that captures similar patterns plus timing/speed differences
- DTW context: flexible point-to-point alignment via lowest-cost warping path in cost grid
    - Point-to-point gets messy on long series; one-to-many mappings can overfit noise

### DSW Method
- Replaces point-to-point with subsequence-to-subsequence: piecewise linear approximation of the warping path
- Inspired by Ramer-Douglas-Peucker, but splits in cost space, not spatial
    - Split-accept controlled by relative tolerance delta_rel and absolute tolerance delta_x for noise
- Split point chosen by largest value/cost difference, not spatial distance

### Results & Q&A
- Examples: washing cycles, paused machine restart, multivariate motion capture (pen speed-up)
- DSW distance correlates highly with DTW; similar 1-NN classification accuracy
- Multivariate uses dependent alignment: one shared path across all channels
- Complexity: DTW is n^2, DSW is log-linear; lab also offers a fast C-based DTW implementation