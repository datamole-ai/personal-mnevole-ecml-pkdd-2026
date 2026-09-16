### Speaker 1

It's—uh—So thank you for coming to my talk. I'll get into a bit about uncertainty now, but from a scientific perspective, the focus—my main thing—is mostly on this final sample work.

 So even though we already heard a little bit this morning about this idea of classification and classification, maybe a brief rundown for the motivation of this topic.

 As you know, in this classification the idea is that we're given some estimated data points, which we assume are sampled from some distributional P of instances and matrix. And usually in this classification setting, our goal is to get some idea about the instance-distribution matrix, either via some hard or soft classifier algorithm, and this is, yeah, kind of the information we want to learn or generalize from based on our sample.

 Whereas in quantification, we assume there are two distributions. One distribution, again, gives us some native samples, and then secondly, we have the distribution of Q from which we obtain some unnated samples.

 And our goal in quantification usually is to get an idea about the true distribution of the labels over that unlabeled sample, where we don't actually care about the individual instances but over, well, the entire distribution Q. Now, the core, yeah, idea of this presentation is to kind of question this target, whether this Q of Y is actually what you're interested in.

 Yeah. But first of all, we need to specify the quantification problem for the four.

 As you heard quite a lot already this morning, to make the solve problem practically even, we need to assume some kind of distribution shift. There are a bunch of different shifts we can derive shifts from.

 Without any assumptions about the shift, the problem is not what we are practically. And, yeah, as many of you have noticed before, here for simplicity, I'm also focusing on this idea of a prior probability shift, where we assume that the clustering of the distributed distributions don't change.

 We can get Q so that we have some way to kind of, yeah, infer information from our labeled sample P to the unlabeled sample from Q of X. Okay.

 So, um, I'm just—I'm spacing, but I hope it's still understandable. In quantification, usually what is, yeah, commonly done is that we assume that we initially have access to some classifier, which we train from based on samples from the distribution P.

 And if we now have access to such a classifier, it's usually trick in a sense to solve this problem. It's basically to say, okay, we first of all—thank you for taking this—so usually what is commonly done, for example, in the adjusted classifier—in the adjusted classifier in the common approach—is to say, okay, I can use now my classifier to get an idea about the distribution of the labels in the distribution of the prediction that my classifier will make for this unlabeled sample.

 Then we compose it like this, where I can use my PBS assumption to get an estimate about the classical predicted distribution than here on the graph. I don't know how much you want.

 Sorry. Yeah.

 So and then here we have the actual target, which gives us then basically the linear system equation, so we can solve for the Q of Y. And I really want to focus now on this Q of Y, because the specific meaning of this Q of Y is actually maybe a bit more subtle than is usually explicitly communicated in literature.

 Maybe, let's say, I just have a very small unlabeled sample with, you know, five instances where the ground truth for three of them is that they are blue and the two are red. They are in a sample-level proportion of the prevalence of the red class of the fifth, of course.

 However, in quantification, this fifth proportion is not actually what we formerly usually estimated. Most existing quantification approaches formerly care about, on the population level, the class prevalences.

 So, for example, we have a ground truth prevalence in the Q of number that does happen to sample five of them, where two of, yeah, two of my five instances are red. There's probably a mismatch.

 And the question is really what do I actually want to sample. As I just said, this population adjustment is quite commonly what we then formerly tried to sample.

 But I would argue that in some situations, actually, there's also some, yeah, relevance to some sample-level estimate. For example, let's assume you maybe have a classroom and you want to know, okay, which, in your opinion, among 20 students, is the most prevalent.

 I don't know. You want to vote which team party you want to go to, and then the question is, among—I don't know—two choices, which is more popular.

 Then I actually don't really care about what happens if I maybe sample a random set of students from some underlying distribution of the students. What I really care about is the specific sample.

 And in this case, standardized quantification approaches are actually, at least theoretically, not that well suited to this kind of question. And also, yeah, from a, yeah, more from a more theoretical perspective, we can kind of put these two questions even in separate bins of problems to answer, where population-level questions, which are probably considered, are kind of looking to regression.

 So in standard quantification setting, we basically want to estimate the distribution from a linear space of distribution. Whereas in the sample-level case, we actually just have a set of potential answers we can give, and we basically want to pick one best answer, maybe even a set of best answers, from the set.

 So in this sense, actually, the sample-level quantification problem is more in the best distribution.

 And the motivating idea for our contribution is essentially to say, actually, how about we then take standard approaches from classification and apply them to quantification, where we explicitly try to estimate a posterior distribution over the whole set of, yeah, candidate discrete prevalence factors that we could get for a given unnated sample. And to do that specifically, we take some ideas coming back to standard regression-like quantification, namely this Bayesian classifier component, which was, I think, proposed a few years ago at UCL as well, which is foundationally

 actually quite simple and elegant. Because the core idea behind this Bayesian classifier component is basically to say, let's model this problem where the P of Y is like we care about as Bayesian network, and then, yeah, define a likelihood over a posterior likelihood for a particular function. I don't want to really go into the details here, but the core idea is to say we make some observations, namely some observations about how we classify versus some classifier we train on P on the unnated samples.

 And then we also, of course, yeah, make some predictions for the labeled samples. And then based on these observations, we define a likelihood, a posterior likelihood, which we can then solve using similar to actually the last talk, using probably a more power approaches, then that allows us to try to actually estimate, yeah, this Q of Y, which has the advantage that we then not only get a point estimate, but actually, yeah, some density over the entire space.

 This is formerly still in the discontinuous case, where we still care about population-level estimates. However, the nice thing is that it's now, from this perspective, quite, yeah, intuitive how we could basically discretize it, namely by essentially just replacing this posterior target from the Q of Y to, yeah, our discrete prevalence, what we call, yeah, S.

 Of course, we kind of actually have to change our likelihoods then. The main change, which is relevant to achieve this, is essentially to say, okay, we replace here our estimate P, Y, and Y, so the density of predicted interpolated, giving some function of label with a predicted density, which we derive based on our observed samples.

 Simplicity, again, we see has been used here a lot, where while in PCC we have independence of P, Y, S, and Y both on the labeled and the unlabeled data, here we have the approach much more in to actually standard adjusted classifier count, where this estimate is solely based on our observed data. The details are in the paper, but the core idea here is, by doing this, what we obtain is essentially a closer form to a likelihood, which is quite important because since in this right setup

 here we are in a discrete setting, standard with only one power approaches actually wouldn't really work that well, especially in hubs. For example, it can't be applied since we don't have the, yeah, luxury in to use variable groups here. So, yeah, this hub simplification actually makes this problem then practical because we can essentially pick the closest form, three of three of what has to fit this.

 Yeah. And this then allows us to ascribe some likelihood, some probability to all possible discrete prevalence factors.

 There's one side barrier here, and that is that unfortunately for large numbers of classes, this does not really scale better because even though we have a closer conclusion, it blows up exponentially, unfortunately, with the number of classes. So this really only works for a smaller number of classes.

 For larger numbers, we would like to basically approximate this and flip to some extent, which is, yeah, more of a barrier for this approach. But as a proof of concept, that essentially has been done, it already works quite well.

 For this reason, in our evaluation, we have only focused on binary setting because there it's really, yeah, it's linear compute time we need to do this. And what you see here is this comparison between, yeah, the standardized Bayesian scheme, which estimates the population prevalences, and our proposed kind of sample approach, which really cares about the sample prevalences.

 What you see here on the X-axis is the test sample size, so the number of our sample from Q. And here we, yeah, synthetically use some different classifiers with different true positive or positive rates.

 What you see here quite nicely is basically a nice gradient from left to right, which basically both with respect to the MAE, which is commonly used to evaluate the performance of a quantifier and Kavity, we see that for small sample sizes, the final sample approach clearly outperforms Bayesian scheme. Whereas the larger our sample size grows, this S, this, yeah, advantage more and more disappears, and we can turn slightly towards the other side at around somewhere between 50 and 100 samples, which is quite interesting because this really

 highlights that we need, I guess also makes sense, if we have a small sample size, it's there's quite a big difference in the estimates we get with such a minor sample versus a continuous approach. However, once you are beyond the top of 100, the top of maybe 1,000 samples, there's really not much to gain anymore by dealing with this kind of minor sample approach. So for these larger sample settings, existing quantification approaches are perfectly suited and they do better.

 So this is more like a maybe-ish problem to tackle, but if, yeah, one lesson from them where actually the specific sample matters more than the whole population, I think it's worthwhile to consider some alternative approaches that are currently commonly used in quantification. We also have different angle on this verification of comparison.

 This approach, mainly focusing on the confidence intervals we get, because we don't only look at point estimates, but we look at the distribution over all potential prevalence factors. And here, if we look at the 95% intervals, we see that the final sample approach both has a lower coverage gap, so it's closer to the target 95% than the Bayesian scheme.

 That holds for large samples. And secondly, the confidence interval size is also in general closer to a smaller.

 So the qualitative uncertainty, at least with respect to this, is also a bit better for this final sample question. And that also causes some real-world invariation, where we just apply the standard APP protocol on, yeah, on the standard UCI datasets which are commonly used in literature, which is why we stayed down mainly with the core message.

 It's essentially the following: that our finalized sample approach, yeah, works for very probably a super-classified classifier and classifier count, brings the most of the high-speedness performance across all these approaches. But I want to highlight here that this is really only the case, again, for small sample sizes.

 We also ran some experiments with large sample sizes, and there to apply APP, but with sample size of 100 or more, this advantage also mostly disappears. It then also doesn't operate on these datasets, but, yeah, these advantages are quite marginal.

 So this again also in the future datasets highlights, yeah, that this is actually really mostly matters in the small sample approach. And also here our results are a bit nicer in the longer intervals.

 Now, to, yeah, basically summarize on this, when we are in the small sample setting, then this final sample where I just said to include into my key takeaways, I think the main thing I really want to make clear from this talk is that there are actually two types of quantification problems which were not that, yeah, commonly discussed so far in literature at least population-level and sample-level problems. Secondly, that, yeah, we propose this very simple variation of the Bayesian scheme approach, which is a little bit

 of a solvers problem at least for a small number of classes. But, yeah, scalability is still basically proved, so that's maybe one area for future work. Thank you.

### Speaker 2

 I think the case that, I mean, provided that, yeah, we have some specific methods to. All over the one question mark number, right? We can find a number of classifications depending on the sample size, and it works for large samples.

 In the case that we do, I mean, my issue is that if one of these systems in order to discover information from individuals, replicate in variants, how do we do this for adversarial differential analysis? So if you modify the sample invariably, would it be the case that then these kind of methods are quite unusual?

### Speaker 1

 You mean the quantification setting in the small sample case in general, or.

### Speaker 2

 Yes.

### Speaker 1

 About the. That is a good question.

 I think, I guess, yeah, so in the paper we really didn't discuss this in such a detail, but in general, of course, we do assume that we have full access to every computer application for the workspeace that we're given. So I think this is not directly at least the way we can apply to this differential privacy idea, because while we, of course, care about the accurate metric at the end, we still assume that we have a regular classifier with full access to all the features.

 So while the output is, of course, an aggregate, yeah, there's not really any, yeah, kind of privacy takeaways or as I discussed. Yeah, I guess this is more something for.

### Speaker 2

 Yeah, it's.

### Speaker 1

 Aggregate of computers.
