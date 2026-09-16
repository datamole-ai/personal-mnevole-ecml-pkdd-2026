Conference-style presentation of EXENSAIC, an end-to-end interactive platform for explainable unsupervised learning, developed to help clinicians cluster and interpret systemic sclerosis patient profiles.

### EXENSAIC Overview & Motivation
- Built at University of Vilnius, motivated by systemic sclerosis, a rare heterogeneous autoimmune disease needing patient subgrouping
- Goal: integrate clustering + explainability into one workflow accessible to non-expert clinicians

### Workflow & Modules
- 8-module Streamlit web app: UI, preprocessing, clustering, 3 explainability modules, visualization, LLM layer
- Clustering: 10 families from traditional to deep methods
    - Comparison table via silhouette, plus Calinski-Harabasz and Davies-Bouldin indices
- Explainability: global (decision tree, permutation), local (SHAP, LIME, GMM), counterfactual with user-defined immutable features
- LLM (external API or local) generates reports describing technical outputs; clinician retains interpretation control

### Future Work
- Cluster stability analysis and knowledge-guided LLM to improve clinical evaluation beyond the general LLM in release