Final class presentation on Pixel Ring, an AI framework predicting EV energy consumption via Bayesian fusion of a pretrip and in-trip model. TFT chosen as pretrip model with 8.8% trip-level MAPE.

### Context & Framework
- Project: predict EV energy consumption for Dutch fleet logistics to support routing/charging decisions.
- Pixel Ring combines a pretrip model and an in-trip model, fused via Bayesian fusion for a shrinking uncertainty interval.
- Route-to-file generator derives plan features (time, geometry, road type); sensor data used only for in-trip model training.

### Models & Results
- Pretrip candidates: XLSTM, TimesNet, TFT; TFT best (handles categorical + static features, decoder positions).
- Trip-level: TFT MAPE 8.8%, calibration ~80% at α=0.05, ~90% at α=0.01.
- Fused interval beats in-trip-only early; in-trip surpasses fusion near end, sometimes past the decision cutoff.

### Explainability & Q&A
- Key features: elevation, temperature, speed limit, trip distance; driver-vs-planned speed guides early predictions.
- Q on XLSTM uncertainty: computed as std deviation of the mean across many trips/variations.

### Decisions Made
- Temporal Fusion Transformer chosen as the pretrip model for the Pixel Ring framework.
- Diffusion model selected for the in-trip stage due to dynamic segmentation and long decoder horizon.