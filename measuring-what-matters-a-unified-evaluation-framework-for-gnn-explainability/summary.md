Conference talk presenting a unified evaluation framework for graph neural network explainers on transaction data, benchmarking 8 explainers across stability, faithfulness, compactness, and time.

### Motivation & Problem
- Bank transaction graphs need explainable ML under AI Act, but no ground truth for comparing explainers
- Goal: compare explainers via metrics (stability, faithfulness/pertinence, compactness, time)

### Method & Setup
- Filtered 50 explainers to 8 via license + edge-feature + link-task compliance
- Benchmarks: Cora, Pickup, Shapes for classification; semi-synthetic for regression; GCN and GAT models
- Early stopping added to handle high computational cost on large graph explanations

### Findings
- Input×gradient gave best pertinence/time tradeoff; integral gradients consistent but slower
- GNNExplainer and graph mask notably slow; graph mask unstable on edge explanations
- Metrics vary between node features and edges; no explainer unifies both mechanisms

### Q&A
- Pertinence measured by deletion curve vs random perturbation, using background graph values
- Full unification of feature vs edge explanations impossible; handled via Pareto tiers