`<name>` presented ASPER, a training-free method that teaches LLMs to close financial-reasoning knowledge gaps via an auto-generated agent-skills library, showing up to 17% accuracy uplift on the Farmer benchmark.

### ASPER Motivation & Approach
- Goal: adapt LLMs without fine-tuning; failures traced to financial domain knowledge gaps
- Baselines capped at 38-45% on Farmer; prompt optimizers (Keeper, ACE) add only 0-3.3 pts
- Skills stored as markdown files (common + subfield folders) indexed by top-level skills.md

### Pipeline
- Warm-up: teacher classifies student failures, clusters them into a skills library
- Iterative refinement: coverage + safety passes, verified before acceptance, with retry threshold
- Inference: skills.md retrieves relevant skills, injected into student prompt

### Results & Findings
- Haiku 3.5: +17% on arithmetic, +5.95% non-arithmetic after 2 epochs; Haiku 4.5: ~6%
- Same-model teacher/student recovers 73-75% of gain; generation ~162M tokens, no fine-tuning
    - Skills are model-specific and must be regenerated per model
- Limitations: single benchmark/model; OCR noise triggers unwanted heuristic skills

### Q&A
- Ground truth: numeric answers for arithmetic; Claude-as-judge for open text, matches original GPT-4.0 results
- Gains shrink on stronger baselines like Opus 5 due to capacity ceiling
- Future work already shows transfer to healthcare and legal domains