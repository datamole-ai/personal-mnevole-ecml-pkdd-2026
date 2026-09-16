Walkthrough of tdhook, a library for composing deep neural network interpretability methods on PyTorch modules, with example notebooks and a roadmap for stabilization and integrations.

### Motivation & Approach
- Modern interpretability has shifted from single attribution maps to orchestrated multi-step pipelines
- tdhook wraps a PyTorch module so inputs/outputs across tensors are easily accessible and composable
- Auto-registers hooks for storing activations, computing attributions, or making interventions

### Methods & Workflow
- Library covers attribution, representation (latent space), and weight-intervention methods, with more planned
- Example workflow: store activations → dimension estimation/clustering → LRP attributions → activation patching
    - Artifacts from each step are retrievable by other methods
- Notebooks demonstrate the flow on OthelloGPT and on circuit analysis / feature clustering

### Roadmap
- Stabilize library, improve method compatibility, add user-friendly interfaces
- Expand method catalog (auto-interpretability, explanations) and invite contributions
- Integrate with NNsight, TransformerLens, Inseq and similar libraries