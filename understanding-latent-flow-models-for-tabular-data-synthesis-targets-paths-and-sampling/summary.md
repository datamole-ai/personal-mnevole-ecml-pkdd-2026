Conference-style talk on tabular data synthesis with latent generative flow models, showing that flow matching with optimal transport gives the best utility while noise/score matching is more privacy-conservative.

### Method & Setup
- Latent generative model based on TabSyn VAE with transformer encoder/decoder, swapping diffusion for flow models in the latent space
- Compared targets (velocity, score, noise, endpoint), interpolants (OT vs diffusion PP), solvers, steps, and integration endpoint
- Evaluated on census data using ratio of counts, confidence interval overlap for regression, and privacy risk

### Findings
- Flow matching and rectified flow matching gave best utility; switching linear OT interpolation to diffusion PP generally reduced utility
- Noise/score matching more privacy-conservative but at utility cost
- OT allows early-stop integration (~0.8) for utility/risk tradeoff; PP needs full integration
- Best configurations outperformed TabSyn state-of-the-art baseline

### Practical Guidance
- Recommended pipeline: pick flow objective and interpolant, train, then tune sampling (solver, steps, endpoint) post-hoc to hit utility/risk targets
- Open direction: automating configuration search based on institutional requirements