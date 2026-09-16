### Speaker 1

Hello everyone, I'm `<speaker>` and— Okay, so, um, suppose that we have a number of devices that are pretty great to, uh, detect people, meals, and so on, and the first issue is able to tell us, say, what our investigation level was, or whatever was the level.

 Then imagine that it's called Stripes, and we're trying to calculate your chips, and the best parameter values, uh, goes to chip. So in this case, uh, the best parameter that was considered to be the best before the pandemic is now most probably, uh, suboptimal.

 And to classify accuracy prediction or to have, um, studies on the chips, how we can estimate the accuracy of these test devices. In this paper, we also ask an additional question, which is: how certain are we about these predictions?

 So the first, uh, driving factor of our work was, uh, the type of chips that we are excited to address, which is private property chip. In this kind of chip, we have, uh, a difference between the test distribution with the source environment, uh, while the test conditional density is being stationary, uh, and the stationarity also helps us to identify predictions.

 Now, under a high-probability chip, we have the cross-validation is biased, and to see this, uh, we formulated, um, um, we accept the formulation for the bias of cross-validated accuracy under the TS, and this value depends on the diagonal of the matrix of test conditional classification rates and on the difference between the test prevalence vectors between, uh, source and target. Since this di- this difference, uh, is non-zero because of the third probability shift as we saw, also the value of the bias is non-

zero, and so, uh, the validation, um, is biased under these conditions. Another driving factor of our work was to try to, uh, move from a point estimation, uh, of accuracy, which is what's mo- most. Uh, classification accuracy prediction methods, for sure, uh, uncertainty were, uh, estimation.

 So, um, intervals of estimated accuracy, uh, on which we can, uh, uh, then extract from which we can extract about the estimation and, uh, uh, repeat that test in that meaning. And this gives us two different valuation targets.

 The first possess the quality of the point estimation itself, and the second one possess the quality of the intervals. Our contribution amounts to three methods that are able to target both, uh, evaluation targets.

 The first two methods fall inside the group that we call circuit and pipeline sampling, and this, um, group of methods starts from the ideas that we saw, uh, just now, so we know that the accuracy bias is non-zero because of the private probability chip and because of the difference between the test prevalence values of the source environment. And so our goal is to estimate, uh, the accuracy on a sample of data which has the same prevalence of the, uh, target sample.

 Now, uh, to do this, we used multiplication. So we estimate the target prevalence through a multiplier, which we use as a survey model.

 Then we, uh, sample, uh, uh, sigma, which is a validation sample, from the validation set V, which comes from the source distribution. And we do this in, uh, a way such that this validation sample matches, uh, the prevalence predicted for the target sample.

 The way the accuracy that we compute for the classifier on this validation sample is anomaly estimate of, uh, the accuracy of the classifier on the target set, and this brings the bias of estimated accuracy close to zero because the difference between the two, uh, test prevalence vectors is also, uh, close to zero. Now, uh, for the two variants of, uh, this group of methods, the first one is SPSH, where H stands for high-prevalence matching, and in this, uh, what differentiates the two variants is the sampling

 criteria, basically. And in this case, we trust the estimate of the multipliers. So we directly draw, uh, a number of samples from the validation set, uh, such that their prevalence values, uh, match the one predicted for the, uh, for, um, the target set, assuming that we can trust this prediction of the, uh, test prevalence.

 And then the, uh, estimated accuracy from accuracy is computed on these, uh, validation samples are, uh, form an interval of estimated accuracy from which, as I said before, we can extract a point estimate through the mean and also an interval estimate, uh, from the point estimate, and we get a bias. The second method of this group, which is, uh, called SPSS, where S stands for soft prevalence matching, using, uh, different criteria that ca that accounts for the error in the, uh, compliance estimate.

 And so the idea here is to inject the same error on both sides. So here we split our validation set into halves, we train the multiplier on the first half, and then we draw n sets, a number of sets of, of validation samples from the second validation, uh, half.

 And, um, these, uh, sets are, uh, drawn using, um, test prevalences that are, um, uh, distributed, uh, randomically, uh, and, um, uniformly over the probability subjects. And at this point, we use the multiplier to estimate, uh, both the target, uh, test prevalence and the test prevalence of all the extracted, uh, validation samples.

 Then we use anomaly matching to find the n-closest, um, validation samples to the target set with respect to their, uh, test prevalence vectors, and then we use the selected ones to, uh, compute our, uh, interval of estimated accuracy. In this case, uh, I expect we before we have a trade-off because we have more clear and matching, but we have less data available for training the multiplier.

 The last method that we propose is a different one. Um, we propose beta, which is a method that does not model the accuracy directly, um, as to before, but uses, uh, a variation process to model the related quantities, uh, such as the source prevalence, the target prevalence, and the best conditional classification rate matrix.

 And, uh, modeling these quantities, it is able to model the posterior, uh, distribution of the variant model. And then operationally, we can sample from this posterior distribution using MCMC with dots.

 And at each iteration, we have, uh, the posterior growth of the target, uh, prevalence and of the classi um, classification rates and test conditional matrix, from which, uh, from which forward we can obtain the drop of the accuracy estimate. Now, uh, the fact is that, uh, this method, uh, gives an output which is, uh, uncertainty away from, uh, given the nature of this, uh, uh, of the variation process that we adopt here, which is inherent in.

 And, um, the growth of the accuracy estimates across all iterations, uh, form in the end, um, an uncertainty interval, just like for the methods that we saw before. And, uh, it also has some advantages since it is a method that is method agnostic and that can also incorporate prior knowledge, uh, inside the posterior distribution model.

 For the experimental setup, we, uh, used a 15 dataset from UCI, um, repository and five target classifiers, used only the accuracy as our target metric. And, uh, for the baselines, we used three state-of-the-art, uh, CAP methods.

 One which is based on regression, and other two which are quantitative that are based on quantification. None of these baselines, uh, are literally, uh, uncertainty away, but we, uh, obtain uncertainty intervals through full extraction for them, uh, compared with, uh, our proposed methods.

 Uh, we used two different target scores. One is accuracy error, which is the absolute error of the, uh, estimated accuracy to assess the quality of the point estimate of the methods, and one is the window scores that, uh, combines, um, the, um, amplitude and coverage of the intervals to assess how, uh, the predicted intervals are.

 And we record, um, average next to summarize many classified dataset, uh, combinations of the results. So here we have, uh, in the top, uh, the accuracy error, um, and in the bottom the window score.

 Uh, the results are aggregated by classifier intervals, and we can see that SPSH is overall the best-performing method. And, uh, the interesting fact is that while for the point estimate, so for the accuracy error, the, uh, two, um, uh, most competitive methods aside from the best are, uh, two of the baselines, while for, uh, the, uh, quality of the interval, so for the window score, uh, the two most competitive methods aside from SPSH are the other two, uh, methods that we proposed that are, uh, that,

 that were both the, uh, uncertainty away basically. We also explored, uh, the, uh, relation between the coverage and the amplitude, uh, regarding the interval, uh, output by the methods. And, uh, we will show, uh, uh, some plots that, uh, are, um, um, have the amplitude on the x-axis and the coverage on the y-axis.

 The, um, favorable areas in the plot are the one highlighted in green, and a single dot in the plot represents a classified dataset combination. And, um, as we can see, uh, SPSH also in this case shows to have the best, um, uh, quality types of intervals since most of the dataset classifier combinations fall in the top left area, which is the most favorable one.

 And, uh, to conclude okay. Uh, so, uh, to conclude, we saw that, uh, under-probability chip, cross-planetary accuracy is biased, and, uh, to have a reliable accuracy estimation using both a point estimate and an uncertainty, uh, evaluation measure.

 And we presented two methods, uh, uh, for, um, quantification based sampling and one method for variation posterior sampling, all of them, uh, literally uncertainty away. And overall, SPSH offers the best, uh, balance between the two target quality scores.

 For future work, we, um, want to look on other types of chip and to explore more in depth, for example, the work of beta with informative priors of or posterior uncertainty calculation through, uh, comparative experiments. Uh, thank you for your attention.

 We.
