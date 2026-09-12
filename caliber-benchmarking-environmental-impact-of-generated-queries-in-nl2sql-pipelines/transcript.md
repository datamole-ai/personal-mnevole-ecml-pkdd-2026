Benchmarking environmental impact of generated queries in NLQ SQL pipelines.

 So, hi everyone, I'm Jonah Larch, I'm from Wispr. Sorry. And today I will present Caliber, benchmarking the environmental impact of generated queries in NLQ SQL pipelines.

 So, as you already know, LLMs demonstrate enough probability in several regions. So, an example can be the LLMs that have seen better performance expected in a specific domain.

 In particular, we can ask an LLM to write an SQL query even with a model unrelated to the question. In particular, the LLMs generate queries that can be pretty correct, but not for free as products.

 So the result can be the same, but the energy consumption and the cost of that query can be reduced. Today we'll look at Caliber, we won't see it, and the weight performance of the natural language to SQL system data.

 And in particular, we want to evaluate the cost of the query on a single factor: what is the cost of running a query on a specific DPPNS engine. In particular, the environmental cost of a query is determined when users write queries.

 So in this case, we want to make the cost of a query from 2D4 to P4. In the state of the art, we have a lot of tools that can evaluate the environmental cost of a query, both the pipeline that generates and the use of query on a DPPNS engine.

 In particular, we have SpyderSim that is standard benchmark for NLQ SQL queries. And in particular, in case you have a query.

 Is correct, but it does not provide information on the cost of that query. Then we have the green arrows.

 In particular, these applications quantify the carbon footprint of the computational cost, but it does not take into account all the very fundamental use of a query. Then we have the DPDUs.

 In particular, this application measures the energy consumption of a query on several DPPNS. So Caliber stands from.

 For carbon-aware LLM benchmarking and data training and pipeline for natural language to SQL queries. In particular, it's an interactive web-based application based on simulated data quality.

 And in particular, it can generate from natural language requests a query. In particular, a user gives a request for an environment, and it can generate a simple query.

 Then it can measure latency and energy consumption, CO2 emission, and net efficiency per cycle. Then, if you want, the user can verify the query.

 So the user asks an LLM to generate from a previous query, and you query that can cost less. Then we can use Caliber also to benchmark different combinations of LLM and DPPNS.

 So we have that Caliber. In particular, there are three layers.

 On the top, we have the interface. So we have a hub in which the user can load or create data.

 There's a different site in which the user can see site-based pipeline data. Echo benchmark, in which the user can benchmark different combinations of LLM and DPPNS.

 Synthetic clocking, in which the user can see the generated synthetic data. And then the green query builder, in which the user can generate the first query or can verify the query.

 So in the middle, we have the backend that tags two adapters, one is adapter and the other one is adapters. So the first one connects the interface to Postgres, MySQL, MySQL servers.

 And then we have the LLM adapter that connects the interface to Wasm Face, Llama, and LLM Studio. As we can see, we have two workflows, the green one and the blue one.

 So the blue one is the simple NLQ SQL workflow. In particular, as I said, first the user asks a question to a large language model.

 Then the adapter generates a candidate SQL. Then Caliber executes the query on the DPPNS, and then we record the result, roughly in the buckets, and this is an evidence chain.

 Then the green one is the green SQL workflow, in which the user asks one LLM to, based on the different building metrics, to regenerate that query and to evaluate the experience of that query.

 So in this page, we can see the green query in the hub, in which the user can write the natural language request with the simple query. And then we have the real-time data dashboard, in which the user can see the scenarios and metrics.

 In this page, we can see the benchmarking, the actual benchmarking result, in which the user can benchmark different combinations of LLM and DPPNS. In particular, we have the green AI case, in which the LLMs can be benchmarked in a case.

 And then we show the winner, if it's like in terms of validation, etc. Then we have the NLQ SQL benchmark, in which we can benchmark the pipeline from natural language to SQL to distribution.

 And then we have the synthetic clock, in which the user can generate data. So in conclusion, we have developed Caliber that tries to make the least cost possible running a query on a specific database and with a least cost.

 In particular, we know that evaluating and measuring the exact performance of LLMs to get the results is a very complex problem. So in this region, we would like to try to solve this problem, and then we want to have more LLMs and DPPNS better.

 Thank you very much.

 Thanks for the presentation. Any questions from the audience?

 So I remember you that at 15:00 in the afternoon will be a special session, an open-day interaction session.