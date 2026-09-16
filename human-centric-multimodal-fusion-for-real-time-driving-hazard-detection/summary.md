Research talk presenting a three-modal driving-assistance system (ARWS, EWAT, convolutional routing) that fuses road context with driver reaction, with benchmark results showing higher accuracy and lower latency than a tuning baseline.

### Motivation & Approach
- Central question: combine broader road context with human driver reaction
- Three-modal system using radio and incoming audio, testing on guesses
- Driver attentiveness (sleepy vs. focused) modulates system response to road

### System Components
- ARWS: multi-leg deep web deployments, ~15% load reduction vs standard
- EWAT: expands/replaces standard combination, ~30% latency improvement
- Convolutional routing: splits road features into three verticals by needed computation

### Benchmark & Results
- Cross-modal benchmark combining road datasets with driver reaction datasets
- 6-second switching standard, MSM features, 2024 commission setup
- Model: ~12M parameters, 170 FPS, higher accuracy than tuning baseline
- Flow information specific to 66%; VLM around 50 FPS by comparison