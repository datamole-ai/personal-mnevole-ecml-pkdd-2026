Presentation of a RAG chatbot over European Parliament data, built on a modular architecture to run experiments on how transparency, retrieval bias, and follow-up prompts shape citizen engagement.

### Problem & Motivation
- EU Parliament publishes ~40 hrs/week of video across 24 languages; citizens overwhelmed and disengaged
    - Only ~33% of EU citizens trust the Parliament (2023); ~50% voted in EP elections
- Goal: make already-public information accessible via natural-language chatbot to improve transparency and engagement

### Platform Architecture
- Modular RAG graph: retrieval → generation → post-processing → UI, with swappable tools at each step
- Admin UI lets social scientists click-and-drag to define user groups and configure experiments

### Experimentation
- Between-group treatments vary data access or presentation; injected problems (e.g. biased retrieval) run across groups
    - Studying effect on perceived political efficacy and understanding of the institution
- Example experiment: follow-up prompts that diversify vs. reaffirm the user's exposure

### Q&A
- <@speaker:2> pressed on added value for a time-constrained citizen; <@speaker:1>: synthesized natural-language answers with source exploration

### Next Steps
- (<@speaker:1>) Roll out experiments over the next ~year, primarily in higher-education contexts