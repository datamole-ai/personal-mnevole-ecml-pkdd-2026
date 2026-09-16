`<speaker>` presented a two-stage framework for dynamic sales pitch generation in Intuit's contact center: a ModernBERT classifier for pitch timing/phase, plus a fine-tuned LLaMA 3.1 8B generator.

### Problem & Motivation
- Intuit contact center experts sell alongside support; top performers convert at several times median rate
- Goal: democratize top experts' intuition on when to pitch and what to say
- Prior static scripts weren't customized; general-purpose LLM lacked expert grounding

### Two-Stage Solution
- Four pitch phases identified: probing, feature explanation, pricing, objection handling, plus no-pitch
- Stage 1: ModernBERT classifier (~8K context) for phase/timing on 5-utterance sliding window
    - Uses last 20 utterances + product prefix + previous window label as signal
    - Downsampling handles 70-80% no-pitch class imbalance
- Stage 2: LLaMA 3.1 8B Instruct fine-tuned via QLoRA SFT on successful expert pitches
    - Conditioned on customer context, utterances, product features, pricing, phase label

### Evaluation & Results
- GPT-4.1 judge on precision and helpfulness; strong recall prioritized over precision
- LLaMA 3.1 on par with GPT-5, slightly better than GPT-5 mini and retrieval baseline

### Q&A and Future Work
- Expanding context window considered but latency is a concern (generator already ~11s)
- Future: add more RAG/reference retrieval, learn from unsuccessful calls