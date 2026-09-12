Talk from King on building foundational models for player representation in Candy Crush Saga: what was tried (tabular transformers, dynamic graphs, events-as-language, time-series FMs), what failed, and open research directions around multi-scale, world modeling, and causal benchmarking.

### Context: King & Player Modeling Goal
- King (Candy Crush Saga): ~200M MAU, 5B+ installs, 20k+ levels, players spanning 10+ years.
- Goal: unified player representation as backbone for many use cases (LTV, churn, difficulty, segmentation)
    - Replace inconsistent, costly hand-crafted features per team
- Four FM promises: universality, beyond features, faster time-to-production, interpretability + generative rollouts

### Approaches Tried & Learnings
- Tabular transformers beat GBDTs above ~100k samples and on complex feature interactions (2024 study)
- Continuous-time dynamic graphs: unsuitable, poor long-range capture and heavy storage at scale
- Events-as-language (Longformer + MLM): 8 interpretable player clusters, but tokenization/sparsity issues
    - Structured tokenization (categorical + numerical separate) helped; capacity alone not decisive
- Time-series FMs (e.g. Moment): strong on LTV, failed on performance marketing (short observation window)

### Why TS FMs Underperform & Way Forward
- Player data is sparse, bursty, non-stationary, multi-scale, skewed; public benchmarks don't reflect this
- Pipeline choices matter: training frequency, pooling, normalization all task-dependent, no single best
- Exploring JEPA-style latent prediction across fast/medium/slow scales, world modeling, causal benchmarking
- Open questions: non-stationary eval protocols, offline-to-online metric transfer, business-impact mapping

### Q&A Highlights
- No FMs in production yet; offline accuracy/perplexity often fails to capture online player-experience metrics
- Built own simulation env to generate data and test interventions given shifting game + player behavior
- Effort: ~2 years, started with 2 PhD interns, grew via multiple teams (causal, world modeling, production)