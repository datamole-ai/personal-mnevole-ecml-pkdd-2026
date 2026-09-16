Presentation introducing Virgil Navigator, a router tool that helps users find explainability methods matching their needs for transformer language models, covering its architecture, use cases, and an illustrative sentiment classification example.

### Motivation
- Transformer LMs increasingly deployed in high-stakes domains (medicine, judicial) with risks: jailbreaks, hallucinations, emergent misalignment
- Explainability landscape hard to navigate for newcomers and practitioners without heavy NLP background

### Virgil Architecture
- Three pillars: knowledge base, retrieval engine, exploration engine
    - Knowledge base: manually curated method cards with metadata, capabilities, strengths, limitations, links
- Retrieval supports hard constraints (architecture, task) plus soft preferences and free-text queries for re-ranking
- Exploration engine lets users inspect, compare side-by-side, and run methods on custom examples

### Audience & Scope
- For newcomers, practitioners, researchers doing preliminary analysis, teaching, and collaborative teams
- Virgil is a router to matching methods, NOT a library for in-depth analysis on own models/data
- Preliminary user study (n=10): 7 found descriptions useful, 9 would recommend to a colleague