Presentation of a multi-agent framework for generating synthetic multi-party conversational datasets, covering cognitive/structural/facilitator layers, a 1,100-conversation release, and evaluation vs. a baseline called demo.

### Problem & Motivation
- Real multi-party conversation data is scarce, expensive, and compliance-heavy; existing meeting datasets are old.
- LLM-generated dialogue is shallow: no theory of mind, rigid agree/disagree, no dynamic turn-taking.

### Framework Design
- Three stages: scenario/world generation, simulation with turn-taking, termination when discussion runs its course.
- Cognitive layer: each agent holds a mental picture of others (stance, firmness, trust, expected next move), updated per turn.
- Structural layer: urgency score picks next speaker; subtopic tracker moves from untouched to exhausted.
- Facilitator/judges monitor definites, progress, group dynamics; can continue, inject fact, redirect, or close.
    - Setup uses Qwen 2.5 72B as orchestrator.

### Dataset & Evaluation
- Released 1,100 conversations, 11 domains, 4 participants, 20 to 50 turns, with per-turn cognitive annotations.
- Beats demo baseline on 4 dimensions; largest gaps in measurements and interaction dynamics (>2 points on 5-scale).
- Ablation: cognitive module boosts engagement, not topic content; facilitator reduces repetition and improves definites.
- Downstream utility shown by training small models on synthetic data and testing on real interactions.