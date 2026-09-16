Conference-style presentation of CAPFLEX, a clustering algorithm and tool that balances cluster size constraints with structural quality across tabular, image, text, and embedding data.

### CAPFLEX Algorithm
- Goal: clustering with flexible cluster-size control while preserving structural quality
- Inputs: ideal cluster size vector + tolerance parameter delta
- 3-step optimization: random search for capacity profiles, simulated annealing to tune delta, MILP for assignment
- Evaluated via silhouette coefficient and cardinality metrics (ILVC, CLC, ECS); Pareto front shows quality vs. cardinality trade-off

### System & Demo
- Supports tabular, image, text, and embedding inputs; embeddings via CLIP from OpenAI
- Microservice architecture: FastAPI backend, embedding + clustering services, React frontend
- Demo: upload data, set cluster sizes and delta, explore solutions (e.g. 78/72 beat forced 75/75)
- Code and paper details available in the GitHub repository