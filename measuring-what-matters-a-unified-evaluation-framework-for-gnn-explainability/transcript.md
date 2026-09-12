So the first presentation is "Measures that Matter": a unified evaluation framework for genuine explainability, from Francesco Paolini to Tom Sapienti.

 Hello everybody. I'm Stefan Pasquale Marini, I'm from Sapienti University, and this is our roundtable with people at Wispr Flow, which is a bank, and since we're in live at Wispr, I'm going to start with a bank example: a machine learning task, which is based on transaction actors. Transaction actors: nodes are bank users, bank accounts, which exchange money, monetary transactions with one another, and we might be interested in many possible machine learning tasks from this kind of data, such as, for example, a node classification task where we

 want to understand if some of the users have some high risk or default or something similar.

 We might want to do similar things to badges and classify them according if they may be fraudulent or not, and we might want to do other regression tasks on both nodes and links in order to understand if they—yeah, some regression tasks as well. But—and there's a huge but—we have a strong regulatory role which is given by the AI Act, which mandates that high-risk systems must be explained.

 So with that, we also need some human analyzing of these machine learning models. We need to be able to understand why a model gave a certain decision for general regulatory issues in this sense.

 The other part of this presentation is that there are many, many possible explainers on platform metrics, and we have the need to understand why which one is better, why it's better, and what are the pros and cons of each one of them. The only problem is that we're in a context where we have a clear lacking behavioral proof, where the data may change day by day as a new transaction arrives, and therefore we might need to adapt and to check our explainer in various contexts.

 So the main question that we're tackling is: how to compare different explainers in the absence of a clear ground truth, which is the common way to do this. Has been more traditional than that.

 The good thing is that we already worked on this topic in the past, and we already developed a set of metrics which describe qualities which are interesting for these kinds of applications, and therefore we started by trying to analyze how to apply those metrics in the context of graph regression tasks. The first metric is stability, which is basically a regression for deterministic and reproducibility of the behavior of an explainer.

 We want the explainer to have some decision that can be replicated easily and that does not change too much on aleatory markers. The second metric that we define is faithfulness, which is a faithful metric.

 We want the explanation to be faithful to the model, and therefore we check if the ranking that the explanation does on the features of the input reflects the importance that the features have for the model. Then we have a practical partners, which basically starts always from the same ranking, but try to determine how many of these attributes we need to flip, we need to change, in order to curtail the model.

 This is the metric that wants to measure how reliable the—like, if the attention of a human has to focus on it on the first main elements of the explanation, is enough to understand the decision or not. And finally, time, which is obviously important depending on the kind of application we need.

 If we need a real-time application, of course, we cannot have an explainer which takes 10 minutes every time that we need to generate an explanation. The main problem of adapting all of these metrics to the graph context are two, which is, first, most of the explainers in the graph literature produce explanation on features of the nodes and the edges separately, and therefore we need to measure these properties separately, independently for features and edges.

 And the second problem is that often explanation is over a huge portion of the graph, and therefore if—especially for faithfulness and stability—we need to compare the whole explanation with the very conditional impossible, and therefore the main application we had to use was to implement early stopping practices in the computation of these metrics in order to be able to do that quickly and effectively. The second problem that we had was the selection of explainers.

 We looked at the literature, we identified 50 possible explainers which might be interesting, and that required two main filters. The first one was the report that we were maintained, there must have been a companion publication, and finally the license must have been—must be useful for—must be a commercially used license.

 The second filter required that since in transaction methods we expect transaction and edges were features, we need an explainer which also was a compliant of edge features, which is not trivial, and also compliant of linked tasks, which also are trivial, and finally which produces features and edge explanations since we might be interested in both. Doing these two filters basically gives from 50 explainers to only 8, and if you have any experience with stability you can see that they're all pretty well-known explainers and that both in

 the general field and outside of the graphs. Finally, since we wanted to first benchmark these explainers and to have an idea of how these metrics vary—vary from vary—for graph for different graph tasks, we had to add some comparison methods, which is also a huge problem in the graph domain, and we considered three classification benchmarks: Cora, Pickup, and Shapes, defining tasks on both node and edge level. For regression tasks, we didn't have many possible choices for the benchmark, and so we relied on semi-synthetic and

 synthetic analysis. Finally, for each of these—for each of these—sorry, for each of the tasks we need, we trained on two different models, a TCM and a GAT. We ensured that the accuracy was high enough, and so we had to train on both tasks at the time, and then we tested it to produce explanation, computerized metrics, and finally to compare them with explainer results that we obtained.

 First of all, we considered the time. Here, with the evaluation, we can see we see that most of the explainers are quite fast, with the exception of repetition explainers, such as PNN explainer and graph mask, and integral gradients, which can take up to a total of 1 to 2.

 Longer than the rest of the explainers. Then we considered stability, and also here nothing is highly stable, so that most explainers were pretty stable.

 The explainers we used were considered out of time, and with the exception of graph mask, which sometimes, especially on the edge explanation, were kind of fluctuating. Then we continued with analyzing the pertinence on both features and edges separately.

 Pertinence, as I was saying before, is the faithfulness of the explanation to the model, and we suggest that depending on the task and the object of the explanation, we have different results. Genetic explainers, for example, were very good for features, and in classification tasks, the conclusion we had about correlation were pretty good on explanation for edges, and in general we observed that both input experience and integral gradients were reliably consistently pertinent with respect to the model.

 For effective compartments, we had similar results. The two metrics are kind of—both look at a ranking under different points of view.

 Here, lower is better because we want a compact explanation which can be advised by a human user. We observed that in edge regression the results are pretty noisy, which may be a result of the fact that we used a pretty synthetic setup for these tasks, and we also see pretty similar results with pertinence, so also here the explainer and integral gradients were the most reliably low.

 Finally, we started performing comparational cost metrics, performing looking at Pareto and tiers for each of the different tasks, and here we observed that while looking at all of these metrics, typically input experience is the one with the best dependency graph between pertinence and computational time, and we also—you can imagine that we're doing the whole list always. Often a little bit worse than in the integral gradients, but with our money too fast, there are less compliance.

 And this pattern was pretty much similar across all the different tasks, both on nodes and on edge, but simply on the edge tasks.

 To summarize, we did produce some operational guidance to indicate the particular values that we observed on the datasets, and values that we think that they are effective or as a solution for any given explainer on any given task.

 And to summarize our findings, first of all, as I just said, input experience showed the best results. Other explainers showed good compromise depending on the task per diem, depending on the object of explanation.

 Secondly, we observed that the metrics we defined should be really transferable across tasks and be able to be examined across a lengthy time. Explainer had similar results for node cases for these two metrics.

 But especially for pertinence and compactness, we observed that these metrics varied depending on the explainer node features and edges. And lastly, we observed that we have a strong limitation in explainer availability.

 A lot of these explainers are state-of-the-art, but also pretty old. First of all, because we observed that the vast majority of the features were currently focused upon graph-level tasks and node-level tasks, with greater explainers capable of explaining linked tasks on graph.

 We also observed a general lack of standard implementation and lack of full continuity throughout the years, so the need to sort of often implement things by hand. And finally, we observed that there are very few explainers of the recent methods that focus on both features and edges, and there is basically no method to try to integrate between the two, but often they only do one side or another of the graph components.

 As future work, we are thinking of trying to expand these results on explanation beyond attribution. We're trying to think of a counterfactual prototypes, which may also be interesting.

 We're also likely to create some new metrics that integrate human-to-mind knowledge with evaluation of the explanation, something that also can, of course, provide a viable benchmark.

 And finally, we wish to leverage this benchmark in the secondary function of the benchmark and analyze the experience in the literature to develop new explainers as well. That was all.

 Thank you for your attention, and if you have any questions— Thank you for your time.

 I'm sorry for the addition. Do we have time for two minutes for questions?

 Thanks for the nice talk. Could you explain what corresponds to graph neural networks, how we measure perception, from what I get to how that metric reflects the graph experience? How do you measure that, how trustworthy is that metric?

 Yeah. The word metric, or first of all, what is the explanation of the metric?

 I don't know how to graph perception. How do you measure it?

 What we did was based on. Studies for that, and still go harder, but I don't know how much there could be understood easily, but I think that's good. Basically what we did was we compared the ranking produced by the explanation to what the ranking produced by a random explanation, so just a perturbation, a random perturbation, yeah, a random perturbation of the explanation, the order.

 We perform a deletion curve where we substitute features with a corresponding value that we extract from a background, from the background graph, basically, and we see how much the model reacts to this substitution following the order given by the explanation versus the order given by the random explanation. So in a sense, pertinence measured how much good is the explanation in giving information to perturb the model with respect to random explanations.

 And this is why early stopping helps, because then we can just iterate on an explanation until we reach convergence on the value of the metric.

 Okay. That gives me some information. Thanks.

 Okay.

 Questions?

 I have a question. Since this is a work trying to unify different edges and depending observations on graphs, are there any challenges in unifying these metrics since they are different from the edges, and also that helps the experiments that we're trying to use?

 Well, first of all, there was a problem that, of course, these metrics were defined on a region in the current domain, so they needed to be translated, and as I was saying before, we had some problem with the computational cost of these metrics. So trying to understand what kind of early stopping would work and were effective in estimating these measures.

 And secondly, the fact that given the fact that a full unification in this case is impossible, because in the end, the mechanism producing the features explanation, the edge explanation, are completely independent. So having to handle also the complexity of two independent mechanisms was also something to handle, and we tried to do that through the operator of the tiers for the evaluation across different aspects of the same explainer.

 Thank you.

 Okay.

 Let's have the speaker again.