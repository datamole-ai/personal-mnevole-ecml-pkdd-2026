Conference presentation of Caliber, a web-based tool for benchmarking the environmental cost (energy, CO2, latency) of LLM-generated SQL queries across DBMS engines, plus a "green SQL" workflow to regenerate cheaper queries.

### Motivation
- LLMs write correct SQL but at variable energy/cost; same result can be produced far cheaper
- Existing tools fall short: Spider benchmarks correctness only, green trackers miss query-level cost, DB profilers miss the LLM pipeline

### Caliber Design
- Web app: NL request → candidate SQL → execute on DBMS → record latency, energy, CO2, efficiency
- Three layers: UI (hub, dashboard, benchmark, synthetic, green query builder), backend adapters, engines
    - DB adapter: Postgres, MySQL, SQL Server
    - LLM adapter: Hugging Face, Llama, LM Studio
- Two workflows: standard NLQ→SQL (blue) and green SQL (green) that regenerates a cheaper equivalent query

### Capabilities & Outlook
- Benchmarks LLM×DBMS combinations and picks a winner; supports synthetic data generation
- Next: broaden LLM and DBMS coverage; exact LLM performance measurement remains hard