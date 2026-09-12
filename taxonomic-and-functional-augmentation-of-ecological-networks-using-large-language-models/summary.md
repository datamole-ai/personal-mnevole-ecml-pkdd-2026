Research talk on using LLMs to standardize marine food-web taxonomies from PicoBase, with follow-up Q&A on generalizing the approach to other knowledge graphs.

### Problem & Setup
- Standardizing common species names to scientific taxonomy across ~230 food webs (avg ~35 nodes) from PicoBase
- Nodes range from single species to broad groups; not all resolvable to species level
- Four LLMs prompted as marine scientists to fill 7-rank taxonomy; ~1/10 dataset manually annotated by biologists, cross-checked vs World Register of Marine Speci

### Findings
- Direct prompting: Gemini best, least prone to overspecification
- Main LLM error is hallucinating detail where rank should be 'missing'; taxonomy drift also causes class/order errors
- Two-step prompt (ask appropriate rank first, then trim) recovers accuracy; ensembles competitive after fix
- LLMs can also generate functional trait tables (lifespan, feeding, etc.) that improve downstream graph prediction

### Q&A
- Approach transfers to other knowledge graphs, aided here by taxonomy being long-standardized and well represented in LLM training data
- Medical knowledge graphs would need far more rigorous validation given clinician quality standards

### Next Steps
- (<@speaker:1>) Follow-up study on generating and validating ecological functional features with more structure