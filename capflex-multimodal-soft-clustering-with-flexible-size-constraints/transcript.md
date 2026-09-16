### Speaker 1

Let's say the paper was more or less a glossary of the opposite of science and history.

 Glossaries are widely used to uncover techniques in machine learning, to uncover the instructor in data. However, many more applications require glossaries that also specify operational constraints, such as workload balance, or capacity limits, or requirement effect of balance.

 The classical algorithms in glossary ignore cluster size, such as k-means or k-values. On the other hand, another group of algorithms with glossary with size constraints encourage quotas that limit structure.

 Our goal in this paper was to enable glossary with flexible control over cluster size while preserving structure quality.

 In our case, CAPFLEX works as an input and ideal cluster size vector that is the cluster size of each group that you need to cluster, and one tolerance parameter delta. And the optimization strategy had 3 steps.

 The first one was to generate feasible capacity profiles using Random Search. The second one is to tune this tolerance parameter delta with simulated analytic methods.

 In this case, it's because in some large datasets the space of search is very large. And then we solved the instance assignment exactly with a mixed integral linear programming.

 The evaluation of the algorithm was in 2 steps. The first one is the measure of the structural quality throughout the silhouette coefficient.

 And in the other hand, we need to search how many instances are in different clusters that differ to the ideal cluster size vector. We used 3 metrics in this case: I, L, VC, CLC, ECS, and the I for the state-of-the-art metrics.

 Then, finally, we used the pareto format to expose the trade-off between glossary quality and cardinality complaints. This is a figure of the complete diagram of the algorithm and the process.

 And in general way, CAPFLEX supports different types of data: tabular data, image, text, and also embeddings. Embeddings, in our case, are generated with GLIF from OpenAI for multimodal representation.

 And then the algorithm explores the similarity cardinality trade-off in this case. For the implementation and the development, we used a microservice architecture.

 The backend service implemented with Python using FastAPI, embedding service using GLIF, cluster service using the CAPFLEX algorithm, and for the frontend, React-based frontend. This is a figure about the interactive interface and the architecture of the system.

 And I'm going to show a little video about the definition.

 Then you can upload different types of data: tabular, base text, or embeddings. For example, for tabular data, you can upload the file and then select the features, select also if you need the ground truth, and select the cluster size.

 It's not necessarily equal size; you can put another size and define the delta tolerance parameter. Then explore the solutions and find the better solution, that in this case is 78, 72, that not is equal to 75, 75, that is better the solution than the cluster with size constraints.

 For image, you can also upload the image. In the first case, we transform this image for embeddings and then process with the same process.

 And it's possible to download the image. It's possible to download the embeddings.

 And also, you can save this embedding for using another application if you like.

 So.

 Finally, in this case, the goal of CAPFLEX is bridging the gap between constrained clustering research and practical decision support tools. If you need more details about the implementations, you can find our repository in GitHub and have the code about the application, and also more details about the paper that contains the algorithm.

 Thank you.

### Speaker 2

 Any questions?

 We can move to the next slide. A general output platform for end-to-end experimental workflow management and multimodal data acquisition.

 The speaker is Andrea.
