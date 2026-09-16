`<speaker>` presented research on whether statistical benchmark-contamination detectors for LLMs hold up outside academic settings, finding all tested methods degrade significantly under realistic post-training conditions.

### Benchmark Contamination & Detection Methods
- Contamination: public benchmarks leaking into training data, making eval scores untrustworthy
- Reviewed three detectors: MIA, LLM dataset inference, post hoc dataset inference, plus CDD
- MIA alone near random-guessing on LLMs; dataset inference aggregates weak signals via meta-classifier + statistical test

### Stress-Test Findings
- Evaluated on Olmo 2 (open training data as ground truth) and industrial models (Gemma, Qwen, Llama)
- All methods degrade under limited reference data, benchmark-scale sets, and specialized post-training (e.g. Polish medical QA)
    - LLM dataset inference may just detect train/test distribution shift
    - Post hoc inference fails when generator can't be trained on limited data
- Comparative outlier signal: Gemma flagged as likely not trained on GSM8K vs peers

### Practical Guidance & Q&A
- No single reliable tool; use LLM dataset inference with IID reference, post hoc on large corpora, CDD as comparative
- Methods applicable to gray-box API models exposing token probabilities; useful as a hint, not a guarantee