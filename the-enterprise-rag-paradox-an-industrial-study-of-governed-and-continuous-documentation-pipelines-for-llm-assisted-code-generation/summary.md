Dane (<@speaker:1>) presented Wispr's experiment on closing the salient knowledge gap between LLMs and evolving library versions, comparing "context first" vs "context serving" approaches, and proposed a routing mechanism since neither wins universally.

### Problem Framing
- Salient gap: LLM knowledge lags rapidly-changing library/framework versions (TypeScript, Java, Python), yielding conveniently wrong code.
- Two proposed approaches: context first (curated down-selected docs) vs context serving (system continuously ingests/vectorizes new versions).

### Experiment & Findings
- Tested 10 packages, 16 implementations, version migration prompts; GPT-4.1 for generation, Claude 2.6 as vision/judge, 15% manual sampling.
- Context serving stronger on context quality (accuracy, clarity); context first lagged code quality by ~3.2% mean.
- No single winner: context quality does not equal code quality; OpenAI/PyTV-style common tasks still favored context first.

### Proposal & Limitations
- Proposed routing mechanism: classify task, select context approach, then generate, based on package type and release cadence.
- Limits: small sample (~30), fixed architectures, LLM-as-judge on 15% sample, packages evolve over time.