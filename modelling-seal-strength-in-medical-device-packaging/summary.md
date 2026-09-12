Presentation on using machine learning to predict seal strength in packaging validation per ISO 11607, showing boosting models perform best and identifying five key predictive variables.

### Validation Context & Process
- ISO 11607 validation flow: process development, OQ challenging limits, PQ demonstrating safety and quality properties
- Sealing process: heat/pressure melts polymer chains between paper and multi-layer film inside sealing tube
- Variables selected across four categories: process, tool, paper, film (weld time, pressure, thickness, temperature, etc.)

### Data & Modeling Approach
- ~4,500 in-tube peel test results from 2024-2025 production; mixed settings required group-based cross-validation
- Five models tested (XGBoost, LightGBM, Random Forest, MLP, etc.) on raw and group-mean levels using R², MAE

### Results & Takeaways
- Boosting models (XGBoost, LightGBM) achieved highest median group-level performance; Random Forest third
- Five key predictors: weld time, film thickness, sealing pressure, packaging paper thickness, temperature
    - Material variables matter alongside HMI panel settings
- Feature reduction preserved performance; approach can accelerate DOE/response-surface validation work
- Q&A: models show importance, not causality; physics-informed ML noted as potential extension