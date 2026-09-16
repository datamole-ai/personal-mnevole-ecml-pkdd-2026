### Speaker 1

So that's the introduction: we set up the word "green" and we pass it on to our models. They're called Carbons and Energy DevOps, and that's all I know besides presenter is Elliot from Wispr.

### Speaker 2

 Thank you. Hello everyone. Well, tomorrow we'll be assessing our development of a benchmark in terms of performance and some trade-offs, and also a meta-learning approach.

 I'm Marek Věrta-Sarastwa from University of Tartu, Estonia.

 Okay, that's a quick agenda here: introduction, climate statement, data results, and conclusion. That's what I'm going to talk about.

 Uh, well, so class, today I hope we are all pretty much familiar with this topic here. So basically, a computer scientist can write specific algorithms to find underlying relationships between data observations.

 So we can, um, come up with a specific classroom algorithm and have specific, um, relations in a later space. But what if we need to test multiple classroom algorithms and hyperparameters?

 So here it goes: automated machine learning for classroom tasks, and which is focused in a search space with different types of classroom algorithms and hyperparameters. And also, AutoML, AutoML, tried to more or less simplify this search space by focusing on a specific, uh, initiation strategy that may be, for example, warm starting using a data survey model.

 So we can more or less, uh, have a less or more constrained space to focus on and invest all of our hardware power to find a better and the best algorithm with specific hyperparameters. But, okay, this search, this is still high, uh, computationally intensive, and also we may have high energy consumption.

 We may have high energy consumption. So for here, this is, uh, our focus on how we can improve this and make it more efficient.

 And so this is where this benchmark is about: trying to more or less compare different frameworks that try to perform different strategies of search space, utilization, search, and finally also an assembly. We may have more than one algorithm.

 So we can assemble this and maybe appro uh, aggregate at the end stage, uh, using maybe the average or the majority votes, for example. And we are going to have finally again our clustering, or our clusters, um, in a, you know, more accurate clusters.

 And also, in this case, more efficient. We focus on this other parameter.

 So this is the execution of the AutoML, uh, framework. And once we know the, the best algorithm with its, its hyperparameters, we can cluster-assign new observations.

 So the cluster-assignment is, uh, inferencing of things of clustering. Okay?

 All right. So the, the question we are trying to answer here is that we know that there are so many frameworks for clustering in the AutoML domain, but these are only focused on ARI, not the, which is the accuracy for clustering.

 So this is, uh, here we find a gap: how much energy they are, you know, spending when running the, the search stage, or when running the search stage of the AutoML process. And also, is this scalable, or how, uh, is, is this well-characterized?

 So this is something that we are trying to explore in this, um, benchmark. So the method simply is how, um, we can run the frameworks using Code Carbon, which is the library will make it possible to get the measurements of energy and also CO2 emissions.

 Next, just perform an ETL to, uh, get our charts and compare results. And finally, with all of these runs, we can gather a big deal of data.

 So we can do something with this. We can train some meta-learners to, uh, more or less have a prediction of what are the best algorithms without running the frameworks itself.

 So this meta-learning approach will help us to save more money and cost and time. And infrastructure, we just try to use a local environment using a mini computer, a mini PC, and also a, uh, HPC.

 Both, uh, will make it possible to compare as well with a mini PC connected to a power meter and say, "Okay, this carbon code library is somehow accurate and correlates with real assurance of energy consumption." Something that we cannot do on the HPC because it's a big deal, has a lot of components, and getting this electrical, real electrical solution is really, really a challenge.

 Uh, the, the quick, uh, setup here, okay, we consider these four frameworks that are the state-of-the-art in the field of, uh, automated, uh, machine learning for clustering. This is, these are open source.

 And we've got the AutoCluster, AutoMapperClass, CSMARC, MET, and ML2DAC. Everyone has a specific number of algorithms and a specific initialization strategy.

 So mine is with warm starting. Also, the other is just a random selection of the algorithm.

 And for the search stage, some of them are using baseline optimization, others just random search or baseline optimization and hypergam. And the CSMARC, the third one, is using an evolutionary algorithm.

 The, the, the last one, ML2DAC, is baseline optimization again. That's the only one that is working in a, in a ensemble.

 It's the, the first one, AutoCluster, which is performing majority voting, uh, against three, uh, algorithms. Okay?

 And the datasets here, when we, uh, perform the benchmark using 100 synthetic datasets that, um, in terms of clustering, ranges from 2 to 30. In terms of dimensions, it ranges from, uh, 200 to more or less 100 dimensions.

 And in terms of instances, it ranges from more or less, uh, 200 and 6,000 instances. So we can see more or less, uh, the distribution.

 We also included 19 real-world datasets from UCI.

 Okay, results. The first, uh, uh, what we wanted to first analyze was the core execution and cluster instance and energy consumption.

 So on the, on the left chart, we got the results for six budget times: 10, 30, 1 minute, 5 minutes, 10 minutes, and 30 minutes. Here we see that AutoMapperClass is running the most accurate when concerning with 10, 30, and 1 minute.

 And ML2DAC follows in the line here. Um, that, that's more or less from 5 minutes onward.

 We can see that it's more accurate. And it's pretty similar in terms of energy consumption.

 We can see here this, these two, two bars. Okay?

 So, okay, the other ones, the CSMARC, ML2DAC, and AutoCluster are lagging behind because the AutoCluster is, uh, way more, uh, energy consuming, as we had to run three, uh, uh, or somehow end up having three algorithms. So it had to run three times.

 And the CSMARC, ML2DAC, the complexity of the machine learning algorithms requires iterations and a population of, uh, specific, uh, childs, let's say. So it had to run more and more, more, uh, it required more computation.

 So this is a reason it's consuming more energy. And, but unfortunately, what we can see here is less, uh, accurate.

 So this is for the execution of the framework. But on the right side, we got here for the cluster assignment.

 That is, when we got the result of execution, we got the best algorithm and the hyperparameters. Here it is trying to, um, cluster new observations of different datasets and see, uh, real-time more or less how it goes.

 So AutoMapperClass is still the best here, but it's not the, the most efficient, as we can observe here.

 All right. So we wanted to run a statistical test.

 So we used a Friedman test and with an energy Poisson test and, uh, using this kind of diagrams, critical distance. So both AutoMapperClass and ML2DAC are the best ones.

 Uh, according to the execution, the first two ones on the top and on the bottom, the last two ones is for the cluster assignment. And, um, also, uh, how come about running 1 million cluster assignments?

 So here, the AutoMapperClass is somehow more efficient than the other ones. And we can see that ML2DAC, the CSMARC, ML2DAC, and the AutoCluster are kind of have a tipping point on the top because they run out of budget time, which, uh, the hard budget time, which is, uh, was 72 hours.

 So it didn't run all the, the, the, the cluster, 1 million cluster assignments we tried to, to run here.

 And this is an interesting test, a Bradley-Terry tree, which makes it possible to, uh, find, um, the best, uh, in terms of a specific variable, the best one, which is in this case accuracy, considering the specific features. So the features we consider here are the complexity of the datasets, which can be, uh, dimensions or the inst the number of instances or the number of clusters.

 So the Rangeley-Terry tree, uh, with depth of 5, made it possible to more or less get this chart and say, "Okay, I've got my dataset here. I, I have, I don't know, 100 dimensions, 2,000 instances, and more or less I can map my, uh, constraints to these, uh, trees and understand which one of the frameworks are going to be the most accurate in this case."

 I also run this for energy consumption. So this is something, uh, that we have, uh, opportunity to more or less analyze more for other characteristics or parameters we want to evaluate or benchmark here.

 And, okay, according to the geometry of the clusters, so the clusters have a specific geometry as well. It can be center-based, as we can see here.

 Uh, we consider this center-based a more or less circular clustering and in which, uh, maybe the k-means are one of the most interesting ones. And AutoMapperClass is using four types of k-means algorithms.

 So that's the reason here we can, we can see the blue, the blue, uh, shape or figure is, uh, towards the right side, right? Because this is the, the most accurate in terms of ARI.

 In terms of energy consumption, it's maybe the same as the other ones, but in terms of ARI, we can see that it is the more, the most accurate, the AutoCluster, the AutoMapperClass, followed by the ML2DAC. And this is another type of geometry when we are talking about clusters that overlap each other.

 Here, the AutoMapperClass, it is not the best one. So I mean, the k-means type clustering algorithms do not work properly when we are dealing with this kind of clusters that overlap each other.

 So in this case, the ML2DAC is the most accurate, which is the green shape, uh, the green icon there, uh, is the most accurate because the ML2DAC, apart from partitioning-based, I mean, the k-means clustering types algorithms, use a lot of other ones like density-based or hierarchical clustering. So this is a, are two valid different kind of algorithms for clustering.

 So made it, uh, a bit, uh, more robust and it's more, uh, appealing to work with these overlapped clusters. And here we've got the density-based.

 We have this density-based, we consider this kind of clusters. And surprisingly, k-means-based, uh, AutoMapperClass framework is working almost the same as the ML2DAC that include different types of clustering algorithms.

 So it's okay here. In terms of ARI, it's more the, the same.

 And finally, here we've got these pretty well-separated clusters in which a k-means is a king of performing properly. So that's the reason AutoMapperClass is here and we got the more, uh, the most ARI, the most accurate results.

 All right. So in terms of energy, uh, CO2 emissions and cost at scale, uh, we consider here 1 trillion cluster instances, more or less estimated these values, uh, after, uh, performing our, uh, experiments.

 So for these four clusters, AutoCluster is, uh, performing majority voting with three clusters at the end in, in semestage is way more cons, uh, energy consuming. So this is the red one.

 Uh, this is the, the guys we don't like to work with right now, unfortunately. It consumes just 1 trillion cluster assignments, more or less, uh, 6,000 kilograms of CO2 equivalents, and which is more or less 3,000, 3,000 euros according to, uh, the cost of energy in Estonia.

 So compared to the AutoMapperClass, which is the greenest, uh, is just costing 100 euros and is, uh, you know, a, a small proportion compared to the other one. And here we have the actual execution time, you know, the budget time.

 I'm asking for 10 seconds, 30 seconds until 30 minutes, but not all the frameworks respect this. Others are, uh, wasting or spending more time.

 So the, uh, Auto, uh, AutoCluster, which is the, or AutoMapperClass, is almost the same. You can see what, uh, 11 seconds when I asked for 10 seconds.

 So this is more, more or less accurate while, um, whereas AutoCluster is running three times. So it's taking, you know, three times the time budget to get the results.

 So this is the reason as well this is the most energy consuming and the most expensive framework. Okay?

 And here we've got as well, but we wanted to ensure that code carbon is actually correlating with the real, uh, real energy consumption. We can see here that it's almost the same when running the mini Pixie Bowl.

 And code carbon and the real energy consumption are almost the same. And also we compare this with the HPC.

 As HPC is included in other components in, uh, the operating system should run more services on the background. So that's the reason it's consuming more energy compared to the little guy FME PC that, that is the operating system is lightweight.

 So, okay, we finally run our, our train, train our meta-learners using our results. And we run finally a for the three stages: initialization, energy consumption, search energy consumption, and, uh, and sample energy consumption.

 So we got all of this data. We run our tests after training our meta-learners using FLAMML, which is another AutoMap framework, in this case for supervised learning.

 Um, and we got interesting results that runs from, you know, in terms of an error from, uh, 14% to 17%. So we more or less can recommend users what are the, uh, uh, the frameworks and algorithms with hyperparameters according to the input data.

 So they do not need to run the frameworks all over again. So this is the interesting part of the meta-learners.

 Okay. So the conclusions, we presented, uh, the intake energy-aware benchmark for our baseline, which is, uh, our clustering algorithms frameworks.

 And across all analysis, AutoMapperClass and ML2DAC consistently offer the best results and also the best trade-offs, energy and accuracy. Um, whereas AutoCluster and CSMARC kind of lag behind because they were, uh, more complex or running three times and finding the three more, uh, accurate algorithms.

 Finally, as well, performance and energy patterns were strongly influenced by dataset characteristics. You know, the complexity of datasets, dimensions, instances, number of clusters on one side, and on the other side, about the geometry of the cluster is also, uh, impacts the performance and energy consumption.

 And our meta-learning approach also further enabled energy-aware configuration selection with, uh, specific condition errors. So that's it.

 Uh, thank you for your attention. If you have questions, you have to.

### Speaker 1

 So we have time for one quick question.

### Speaker 2

 Yes.

### Speaker 3

 Regarding the data, uh, you mentioned the issues with, like, uh, accessibility features. Are you comparing the quality on the clustering results?

### Speaker 2

 Um, you mean if I run different benchmarks with the synthetic and the real-world data separately?

### Speaker 3

 No, because, uh, the complexity you mentioned.

### Speaker 2

 Mm-hmm.

### Speaker 3

 The number of instances.

### Speaker 2

 Yeah.

### Speaker 3

 Clusters and dimensions.

### Speaker 2

 Right.

### Speaker 3

 Uh, but for a real case study, for instance, we don't know the number of clusters.

### Speaker 2

 Oh, that's true. Yes.

### Speaker 3

 Beforehand, so.

### Speaker 2

 Yes.

### Speaker 3

 Would you mention?

### Speaker 2

 Exactly. And that's a little you said good catch. It's a good catch.

 Yeah. For example, this one, we are including the clusters.

 It's just for the end of our understanding during experiments. But in the practice, the clusters are going to be removed.

 It just we can consider the dimensions and the instances. That's the idea.

 Just working with dimensions and instances, and the clusters is unknown, uh, the first, uh, the first, uh, the first stage, the first part. We don't know that's reliable.

 So this is only for experiment, experiment purposes. But yeah, in real life, just dimensions and, uh, number of instances is the, the, the thing we are really required.

 That's something we consider for our meta-learners, just this, uh, information, dimensions and number of, um, number of, uh, instances to train our, our learners and have those results.

### Speaker 3

 I think you ran the brain dry. I don't know if you already did your work, but, uh, did you, did you solve the different shapes of clusters to map into different results?

### Speaker 2

 Right.

### Speaker 3

 Maybe you can take out some information of the mechanicals beforehand. Maybe you can find links or, uh, a specific shape.

### Speaker 2

 Mm-hmm.

### Speaker 3

 That will give you some indicators on the.

### Speaker 2

 Oh, right. I consider this for training as well, for training all the meta-learners.

### Speaker 3

 Yeah. Like a feature for those.

### Speaker 2

 Yes. As a meta feature, right. That's interesting.

 Thank you.

### Speaker 1

 Thank you.
