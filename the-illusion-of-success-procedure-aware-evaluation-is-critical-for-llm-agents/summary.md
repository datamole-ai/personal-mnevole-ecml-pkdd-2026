Miro Kahl (Amadeus) presented PAE, a procedure-aware evaluation framework for AI agents, showing that 27-78% of reported successes are "corrupt" — correct outcome, violated procedure.

### Corrupt Success Problem
- Flight rebooking case: correct $890 charge, but agent quoted $320, skipped cancellation consent, hallucinated flight time
- 6 violations hidden behind a successful outcome; outcome metrics cannot surface them
- Review of ~2,000 agent-eval papers: >95% purely outcome-focused, almost none propose procedure metrics

### PAE Framework & Results
- 4 dimensions: utility, efficiency, interaction quality, procedure integrity (policy compliance, execution consistency, data fidelity)
- Tested on airline + retail with GPT-5, Mistral, Claude-class agent; ~90% LLM-judge accuracy vs human spot checks
- Tradeoffs: GPT-5 highest success, Mistral ~5x faster, Claude least verbose; GPT-5 weaker on airline execution consistency
- 27-78% of reported successes are corrupt; error signatures differ per model, so mitigation must be model-specific

### Framing & Q&A
- Wells Fargo (2011-2016) cited as human analogue: KPI-driven fake accounts, $185M + $3B fines, fixed by shifting to long-term customer satisfaction
- Q on subjectivity: <@speaker:4> argues integrity checks are objective fact-checks against policy/data, not subjective judgments

### Next Steps
- Try the open-sourced Agent Theory Discovery tool to auto-generate error taxonomies from agent logs
- Catch Miro Kahl's 4 follow-up papers at October conferences