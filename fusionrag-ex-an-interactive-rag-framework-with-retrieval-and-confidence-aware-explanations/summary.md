`<name>` presented an interactive RAG framework for evaluating whether retrieved documents are truly relevant, combining perturbation, similarity, and confidence-drop scoring across multiple retrievers and models.

### Motivation & Objective
- Existing RAG propagation ignores whether retrieved docs are actually relevant, yielding ungrounded, low-confidence answers
- Goal: interactive framework to assess doc relevance across retrievers and compare propagation strategies

### Framework Components
- Three tabs: Retrieval Explorer, Explain RAG (propagation-based explanations), Comparative Analysis
- Configurable retrievers (fast/dense/hybrid), models (LLaMA, Gemma), datasets (benchmark + custom)
- Explanation levels: word, sentence, paragraph, with multiple perturbation strategies

### Scoring Strategies
- Perturbation+similarity, perturbation+retrieval scores, and confidence-drop
    - Agreement across all three on a unit signals the model genuinely relied on it

### Next Steps
- (Unknown) Join the interactive lab to explore the framework further