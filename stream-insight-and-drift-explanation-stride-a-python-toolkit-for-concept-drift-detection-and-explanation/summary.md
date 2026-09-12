Presentation of STRIDE (referred to as Frith/Stride), a Python tool for detecting and explaining concept drift across data, model, and explanation layers, followed by Q&A on block sizing, false positives, and comparison to other detectors.

### STRIDE Overview
- Three-layer architecture: data (distribution changes), model (decay via DDM), explanation (XAI methods)
- Methods: descriptive stats, statistical tests, axial clustering, decision boundary, feature importance, prototype-based explanations
- Built in Python using scikit-learn, Pandas, Streamlit, Seaborn; user connects dots across layers for when/how/where of drift

### Case Study & Demo
- Hyperplane dataset: DDM showed error rate drop; feature space changed while class distribution did not
    - Post-drift, x2 rose in importance over x1 as decision boundary rotated diagonal

### Q&A
- Block size matters: decision boundary analysis needs ~500 samples; too-large blocks may miss drift between them
- False positives handled via layer interaction, e.g. prototype signals drift while DDM does not
- Positioning vs other tools: focus is explaining drift, not just detecting it

### Next Steps
- (<@speaker:1>) Invite audience to visit the stand and live session for continued discussion