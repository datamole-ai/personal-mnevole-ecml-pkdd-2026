Conference talk by <@speaker:1> (Roman Yanis, Spirit DNS) on benchmarking compact 1-8B LLMs as RAG generators for Russian, showing Qwen3-4B hits a strong quality/latency tradeoff near GPT-5 mini.

### Setup & Benchmark
- Practical constraints: on-device (no data leakage), CPU-only, ~16GB RAM, 1-8B params, Russian output
- 500-sample benchmark: 4 open-source datasets (100 each) + 100 proprietary IT-conference lecture-note QAs
- LLM-as-judge with 3 judges selected across families: GPT-5 mini, Qwen3 8B, GLM 4.7
- Metrics: correctness, answer relevance, faithfulness; 17 models tested in GGUF via llama.cpp

### Results
- Qwen3-4B (instruct, Q5_K_M quant) chosen for best quality/latency tradeoff, close to GPT-5 mini baseline
    - Qwen3-8B slightly higher quality but much slower
- Context clearly helps vs no-context runs; older families (Llama 2, Mistral 7B, older Qwen) sometimes switch script to Latin/Chinese
- Limitations: generation-only, retrieval frozen; judges not human-validated; tokens/sec not reported

### Incident
- Audience member objected to a Russian presenter; <@speaker:3> (session chair) defended the accepted paper and asked to raise it at community meeting

### Next Steps
- (<@speaker:3>) Raise the presenter-objection incident at the community meeting