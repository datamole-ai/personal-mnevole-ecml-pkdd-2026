`<name>` presented PyClad, a modular library and framework for continual anomaly detection, covering motivation, core abstractions (dataset, scenario, strategy, model, callbacks), a code example, and the roadmap toward vision, time series, and video modalities.

### Motivation
- Static models flag new normals as anomalies; online models adapt but forget recurring concepts.
- Gap in tooling: continual learning libs (mostly RL/education) and anomaly detection libs (PyOD, Anomalib, PySAD) don't intersect.
- PyClad targets this intersection with scenarios, strategies, and a modular library.

### Framework Design
- Four core concepts: dataset (stream of task concepts), scenario (what model knows about task changes), strategy, and model.
- Callbacks and metrics follow PyTorch-style pattern for monitoring time, metrics, transfer, retention.
- Example uses autoencoder + EWC (Elastic Weight Consolidation) strategy in a concept-incremental scenario.
- Forgetting shown via performance heatmap: task 1 drops from 0.94 to 0.59 after learning task 3.

### Roadmap & Ecosystem
- Started with tabular; adding vision now, time series and video on roadmap.
- Publishing real-world benchmark datasets (cybersecurity, industrial, sensor) pre-split into concepts, importable as one-liner via Hugging Face.
- Second edition of workshop at ICDM in November; will stream and post on LinkedIn.