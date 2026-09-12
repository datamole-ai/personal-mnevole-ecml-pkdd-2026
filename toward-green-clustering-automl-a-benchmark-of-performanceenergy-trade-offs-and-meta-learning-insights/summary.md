Conference talk presenting an energy-aware benchmark of four AutoML clustering frameworks, plus a meta-learning approach to recommend configurations without re-running searches.

### Benchmark Setup
- Compared four AutoML clustering frameworks: AutoCluster, AutoMapperClass, CSMARC, ML2DAC
- 100 synthetic datasets (2-30 clusters, up to ~100 dims, 200-6000 instances) plus 19 UCI real-world datasets
- Energy measured via Code Carbon on mini PC (validated with power meter) and HPC

### Key Results
- AutoMapperClass and ML2DAC give best accuracy/energy trade-off; AutoCluster and CSMARC lag
    - AutoCluster runs 3 algorithms for majority voting, ~3x time and energy
- Cluster geometry matters: k-means-based AutoMapperClass wins on center-based/separated; ML2DAC better on overlapping
- At 1T cluster assignments: AutoCluster ~6000 kg CO2 / ~3000 EUR vs AutoMapperClass ~100 EUR
- Meta-learners trained with FLAML predict best config from dims/instances with 14-17% error

### Q&A
- <@speaker:3> noted real-world data lacks known cluster count; <@speaker:2> confirmed meta-learners use only dims and instances
- <@speaker:3> suggested extracting cluster shape as a meta-feature; <@speaker:2> found it interesting