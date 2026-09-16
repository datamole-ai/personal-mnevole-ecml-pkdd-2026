`<name>` presented EST, a method that mitigates semantic popularity bias in LLM-based recommenders by modeling item-to-item semantic influence via a multi-view graph before applying weighted SFT.

### Problem: Semantic Popularity Bias
- SFT amplifies popularity bias: top 20% items get ~16% of recommendations
- Bias diffuses along semantic neighbors, not just popular items themselves
    - Conventional item-wise IPS treats items as independent, missing LLM semantic diffusion

### EST Method
- Multi-view semantic graph combines LLM embeddings, TFIDF, and collaborative signals
- PageRank-style propagation yields semantic popularity score, balanced by lambda
- Self-normalized weighted SFT with double label smoothing to stabilize gradients

### Results
- Accuracy gains: 15.38% cities, 16% kingdom, 6% twice vs best baseline
- Redistributes exposure from G1 toward G2-G5 while preserving diversity
- Ablations confirm each semantic view (LLM, TFIDF, collaborative) contributes