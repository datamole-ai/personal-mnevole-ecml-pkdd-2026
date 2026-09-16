Presentation on a context-aware anomaly detection framework using an LLM to label data and distill logic groups, followed by Q&A on contextual inputs and baselines.

### Method Overview
- Problem: incorporating business/geometric context into anomaly detection backbones is hard and unstable
- Three-stage framework: LLM labels dataset, LLM refines logic into metric groups, then continuous access for richer context
- Stage 2 uses feedback loop akin to gradient descent, borrowing ML tricks (data scaling, early stopping) to reduce overfitting

### Results
- Compared vs prior production (random forest + business context), pure consistent learning, and direct LLM baselines
    - Consistent learning: good recall, low precision — misses business context
    - Direct LLM: strong results but high cost/latency
- Distilled logic groups match LLM performance while being efficient and scalable

### Q&A
- <@speaker:3> asked about adding contextual info (docs, component status) readable by the LLM
- <@speaker:3> asked for clarification on the underlying dataset and problem in the results comparison