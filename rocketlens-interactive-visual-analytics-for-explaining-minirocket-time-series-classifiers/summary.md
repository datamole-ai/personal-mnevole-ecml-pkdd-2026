Presentation of RocketLens (Rocket next), a tool for opening the Rocket time-series classifier black box by back-propagating important features to observations. Followed by audience Q&A on methods and use.

### RocketLens Motivation & Approach
- Rocket family: fast convolutional time-series classifiers, powerful but black box
- Applied in cognitive load prediction from drawing traces, and posture prediction from paddle temperature
- RocketLens back-propagates important classifier features to time-series observations to produce heat maps
- Modular re importance scoring: works with white-box classifiers or SHAP/LIME-style attribution

### Tool Capabilities & Q&A
- Panels expose top features, pooling thresholds, dilation schemes, frequency stats
- Can back-propagate a single feature or a group (e.g. top 10) to surface broader patterns
- Only qualitative analysis so far: PPV detectors, valley detectors, dilation-related patterns
- Next research stage: extract interpretable features (e.g. shapes) from grouped back-propagation

### Next Steps
- (<@speaker:1>) Demo the improved local RocketLens version to interested attendees
- (<@speaker:1>) Run quantitative analysis of feature importance patterns
- (<@speaker:1>) Develop extraction of interpretable features (e.g. shapes) from grouped feature back-propagation