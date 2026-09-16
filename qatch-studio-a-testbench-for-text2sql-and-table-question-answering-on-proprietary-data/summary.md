Demo of QATCH Studio, a framework that dynamically generates text-to-SQL and tabular-response benchmarks from any tabular data, then executes and evaluates models on it.

### Problem & Motivation
- Top-ranked text-to-SQL models (Spider, BIRD) hit 80-90% accuracy but break on real company data
- Key failure modes: unfamiliar schemas, domain jargon, and users needing answers not raw SQL

### QATCH Studio Framework
- Dynamic benchmark generator over any tabular input (DB or CSV), works for text-to-SQL and tabular QA
- Three stages: generation (template engine from prior QATCH work), execution, evaluation
- Local model execution for privacy; data need not leave the company
    - Demo uses APIs, production intent is local models
- Dashboard ranks models on user's own data and drills into which query parts fail