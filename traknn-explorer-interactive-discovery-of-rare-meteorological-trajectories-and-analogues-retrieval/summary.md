Walkthrough of TRAKNN / Proclaim Explorer: a KNN-based exhaustive search over atmospheric phase-space trajectories to find rare patterns across 70 years of data, with an interactive Streamlit demo.

### Motivation & Approach
- Goal: interactively find and explain unusual atmospheric evolution across ~70 years of data
- Moves beyond snapshot analogs by scoring multi-day phase-space trajectories, capturing circulation over 3-5 day patterns
- Enables event attribution: compare pressure configurations to assess climate change role

### Algorithm & Performance
- KNN over sliding windows of spatial delays; score = distance to nearest neighbors, exhaustive for exact interpretable scores
- Optimizations: HPC distance routines, recurrent distance computation, trajectory-length-independent cost, CPU/GPU execution
    - Runs ~70 years of daily data over 50,000 routes in 2-3 minutes

### Streamlit Demo
- User inputs neighbor count, spatial/temporal filters, optional seasonal removal, dim reduction, cosine standardization
- Four modes: score distribution, anomaly explorer, clustering of regimes, and analog search for query dates
- Demo focused on atmospheric data (European heatwave example), but algorithm generalizes to any phase-space trajectory data