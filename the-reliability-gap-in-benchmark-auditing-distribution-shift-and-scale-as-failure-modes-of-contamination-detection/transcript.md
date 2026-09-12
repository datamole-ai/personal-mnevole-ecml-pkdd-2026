So, hello everyone. My name is Wojciech Brzezinski, and I would love to tell you about my work about the learning gap in benchmark auditing. With Jan Dubinski and Sebastian Cygert, we wanted to find out whether statistical tools which are designed to detect whether a model was trained on a given dataset work in the real-world regime, not only in the academic tests.

 So let me begin with the introduction of our tail, the benchmark contamination. It is a case when a public benchmark—want you evaluate your favorite element, like GSMK 8 or something like that—leaks into the training data.

 So after you evaluate a model on such a benchmark, you may have to play a score, because the model might either 1) generalize and be so great that it answers correctly, but on the other hand it might memorize the training data so that evaluations are no longer trustworthy. And that's the challenge of benchmark contamination.

 And I will go quickly through a set of techniques which might be used to detect such benchmark contamination. So the first, most fundamental technique is membership inference attacks, abbreviated as MIA.

 It relies on a—its objective is to find whether a given training sample was a member of a training set of model we want to evaluate. And it relies on an observation that machine learning models in general have lower loss function for the samples seen during the training.

 And you can apply it also for large language models, or use more sophisticated measures of performance, like perplexity or perplexity on the hardest tokens. And the samples we evaluate have that metric much different than the reference samples which weren't used for training.

 We can conclude that the samples were used for training. However, large language models are much bigger and much more capable than small image classifiers that these attacks were initially designed from.

 And this work suggests that, unfortunately, MIA for language models is close to random guessing. So authors propose partitioning another approach, which is LLM dataset inference.

 The idea is to aggregate that weak signal from an entire dataset to have a more confident predictor. And here we need to suspect set you want to evaluate your model, that you want to check, and held out set the samples which weren't used for training, aiming as a reference set.

 Then you run a bunch of MIE attacks and collect just raw scores from it, and we use it as the features for our meta-classifier. And finally, probabilities from that meta-classifiers are used to perform a statistical test whether the scores of that meta-classifier are significantly higher than held out set.

 If yes, we can reject the hypothesis which says that the model was not trained on the suspect set. So we can conclude that the model was trained on our suspect test after such procedure.

 However, it also has one practical limitation, that it requires that held out set, which needs to be identical, identically distributed, and independent. And it's hard to get one sometimes in practice.

 So another method proposed, post hoc data set inference, uses—proposes to generate such held out set. But we now change a little bit the objective of our task.

 We split text we want to evaluate into prefixes and suffixes, and we fine-tune another LLM to generate artificial suffixes. And now our auxiliary objective is to distinguish artificial from original suffixes.

 And we train two classifiers: first the vertex classifier, and second the meta-classifier, which takes text classifier as a score and MIA features. And we check, in similar manner, via statistical text, whether the additional MIA features help in that classification task.

 If yes, we can then conclude that this suspect set was used for training or for model evaluation. And the third method is a codec.

 It relies on an observation that large language models can—their performance can be easily improved via in-context learning. However, in-context learning is only useful for the actual knowledge for the task that model didn't learn yet.

 So we can design a score which aggregates whether in-context learning helped for a given sample in dataset or not, and have a dataset-wide metric. And I will come back to our main question.

 These methods were evaluated in the academic setup when they were trained only for during pre-training and only on pre-training dataset, while most of the model—large language models—undergo long and really meticulous post-training with multiple stages and multiple smaller datasets. And we want to check out whether that promises from the simplified setup still hold.

 And we designed a few tasks, which I will go through one by one. The first one is limited reference data.

 Benchmarks are much smaller than pre-trained corpus, so we simply cut the pre-trained corpus which previously methods were evaluated on and check whether the metrics reported by the authors of the paper holds in the same setup. Unfortunately, only the one of the methods more or less holds its performance.

 Another task was even more strict. We not only cut the limit amount of data, but we used the benchmark itself.

 And to do that, we found a model called Olmo 2. It is a model which undergoes multi-stage post-training.

 However, it releases all its training data and all its training procedure, so we've got access to a ground truth on which sets of benchmarks it was trained and on which not. And in that more rigorous setup, every of the evaluated approaches have much degraded performance.

 The third task goes to specialized post-training datasets. For instance, we case study it on the medical question answering.

 And since that work was conducted in the Polish Institute on the LLM payloads for the Polish language and Polish culture, and it turned out that the domain shift and small splits of datasets were even bigger challenges for these methods, and performance was even more degraded.

 Finally, we used the best-performing methods to compare as a comparative output for the industrial models like Gemma, Qwen, or Llama. And our motivation was that if we got some outlier, the only model which is not pointed out by these metrics.

 Then we have a premise that that one model was trained or wasn't trained as uncomposite with the other models as a comparative signal. For example, we can see on one of the benchmarks on GSMA 8, the Google model Gemma was the only one not indicated by two methods.

 So we can suppose that it was probably one which wasn't trained on train speed for GSMA 3. And finally, we propose a diagnosis: why these detectors fail in that stress test indevided.

 So let's start with LLM dataset inference. We can see the different performance in the first and in the second task.

 In the first task, when we— The drop is when moving the benchmarks, which may have some distribution shift between train and test set. So this method might just detect the difference between train and test set, not the inference membership signal.

 Post hoc dataset inference didn't work well on neither of the tasks. However, if we increase the data size to the full corpus, its performance was regenerated.

 So our suspection is that the generator used for generation of artificial suffixes wasn't—it wasn't possible to train one on the limited data. While a codec gives rather the corps score, not a precise speed level indication.

 So to wrap it up with some practical limitations, unfortunately, we do not have one single bullet which will work in the wild. And we call for the data, open data provenance, but we still got some kind of useful tools, but we need to know how to use them.

 LLM dataset inference is good if we are quite sure about our preference set, which is IAE. We can use post hoc dataset inference if we got large corpus of text, and we can strengthen this prediction with codec as a comparative indicator.

 And that was also from my side. Thank you for your attention, and I'm happy to answer your questions.

 So I have one. So the—that's a very interesting topic for research, because benchmarking is the kind of the war right now of information models that are running on. And trying to find the various contamination on these models is an interesting task to do.

 So I see that you worked mostly with commercial models, but with open dataset. Do you think it can be applied also for API models?

 Towards the commercial models, but this methodology is—should it be explored more also in these development models?

 So we work on the models also really used by the commercial companies. However, the key finding is the access to that model, whether it is a white box when you've got access to parameters and everything, or the black box when you do not have access to the nothing except from the output tokens, or you've got that gray box setup, which is most popular in that field, that you do not have access to the model weights, to the gradient, but you've got access to the token probabilities. And

 most of the current work is rather realistic in that gray box setup. So even though the model is shared via APIs, some APIs share block proxy probabilities for different tokens, these methods are applicable. And I think it's also applicable to further research to extend that evaluation to that gray box model, especially with the huge development of popularity of API solutions.

 Any other questions? Speaker? Yes.

 Do you think it could be used in the environment, like to actually detect open and private models to depend on certain datasets?

 I think yes. I think so, for sure you can use it as a white. However, it's rather an premise than a guarantee.

 Like, we've got some hint if you've got an outlier in that matrix combined, you can hide your kind of quite big suspections about that it might shift a little bit by training on a one benchmark. However, with current state of the work, it's just like you've got that hint for an outlier, but you do not have that guarantee that you're sure about it.

 So thank you.