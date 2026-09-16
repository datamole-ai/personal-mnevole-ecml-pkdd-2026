### Speaker 1

We've already had a lot of presentations talking about what quantification is, and I'll skip the introduction a little bit. But in this talk we're going to be assuming environmental intelligence, and we're going to be treating quantification as a two-stage practice. So we have a classifier that gives us scores on each instance of that spec, and then we're giving that sort of score to a reference reference.

 So the signatures have in recent evaluations been shown to perform relatively poorly compared to other classifiers. Base classifiers were performing quantification.

 In 2013, we had also introduced a couple of different criteria specifically for those decision trees that might be well on quantification tests, but we took those splitting criteria off some of those decision trees and performed poorly. In addition, this decision trees are commonly miscalibrated, and several quantification algorithms that are sensitive to calibration.

 So this work, we want to see if we can improve quantification using decision trees as base classifiers by changing the aggregation method. We're going to propose a medium which uses the decision tree views as a kind of discrete partitioning of feature space, and then we're going to apply interphase and autofilling to the leaf counts in order to recover our roughness after estimating.

 We're going to have ECHO, Schumann, and ROSE protocol for evaluating classifiers. So we rely a lot on the task of unfolding.

 Unfolding is, I think, usually the physics business. Whereby we measure a distribution of effects, and the goal is to recover the distribution of the problems.

 Interphase and unfolding is one such method for query folding, for recovering that distribution of problems, and it recovers the maximum likelihood estimate for a plus distribution. In addition to that, in the field of unfolding, treatments have been shown to provide component evidence for unfolding problems, and in 2022, LISA showed that we can unify the tasks of quantification and unfolding under a compound term.

 So how do we use all these tools in one method? So we're going to start by generating a classification tree on some labeled training data after separating out some estimation set.

 We're going to treat each one of these five samples on that five samples per leaf as evaluated from that estimation set. And the reason why we do that is because we're going to estimate the class conditions for the number of leaf on leaf, so each leaf in your class on that estimation set, and then we're going to regularize it for plus two leaves.

 So for our method, we're actually going to use the posteriors. So we don't really care about calibration, but we do have a place in that.

 Require good estimates of the class conditions for how well we're performing per leaf in the class. So the choice of criteria we'll evaluate today are G, which is classification split criteria, classification error balancing, which was developed for the task of quantification, which is generally motivated by the idea that you have false positives and false negatives that cancel out on your aggregates through well quantification.

 And then a hybrid classification quantification balancing, which does the balancing thing but additionally analyzes classification or misclassification correctly. All right, so we have our classification distributions shown here, and in blue and orange, for just a very simple example, we have a two-dimensional feature space and a binary classification task.

 We observe the histogram of the unlabeled instances in the test bag. So basically, without going too deep, watching for the details of interphase and unfolding, we apply the subject rule until we converse to the maximum likelihood estimate of observing the data.

 Or I shouldn't say the data, I should say the leaf counts, observing the leaf counts. Okay, so we're going to evaluate this very similarly to Schumann-Ross protocol for each dataset for split training tests.

 All of the quantifiers we're going to evaluate need some sort of estimation from some held-out data, so we're going to further split between the set and the tree training held out. We'll stick it in our test bag and see the relevance of whether it's calculated error.

 And then what we're going to be reporting is the rates across the datasets of each of the classifiers, so the mean rate across all the different trials for each of the classifiers. So something you'll notice when developing this protocol and running these experiments, there were several cases where we ended up with basically these degenerate treats, which is going to end up being a little bit of a weakness of the study.

 But basically, there are cases where the CPD and CQE treats do take a single split, and then pruning also occasionally pruned back all the way to the root because of basically having a small treatment set or having very rough treatment set. So we looked at those separately, basically with the idea of what we're going to be interpreting our results for datasets where there's sufficient data on how to approach classifying things.

 So we compared a number of quantifiers, and I won't go too much into the details here, except for I want to point out that we compared a couple of other maximum likelihood methods, including KDE, YML, and SLV. And just to contrast what we're doing compared to those, we're all maximizing the same likelihood function, except we're coming up with different estimates of the positive additional densities using different properties.

 So SLV uses the posteriors of the classifier in order to estimate the class conditional distribution. Right?

 KDE, YML, fits kernel density estimate to the classifier scores, the class conditional classifier scores. And yeah, so we obviously are looking at the distribution across the leaves.

 Okay, so looking first at binary quantification, this is the mean rate chart, so the best methods are going to be towards the right on the number line here and towards, at least on the right side, towards the top. And we see that SLV and LEPM have performed the best towards the top there.

 SLV performs the best on CPD trees, and LEPM performs the best on GE trees. The overperformance of SLV on CPD and CDE trees is somewhat interesting.

 We need to do the analysis on this, so if you could hypothesize that since you're not directly optimizing for classification, you might end up with a decision tree that is better calibrated if you're using CDE or CPD. Additionally, another important thing to point out, ACC performs a little worse, and that was with the only quantifier applied to quantification force, Schumann-Ross.

 So it does seem that we can actually that maybe those results don't necessarily represent how well decision trees do in terms of these classifiers.

 Oh, sorry, one more. So LEPM performs quite poorly, actually, on CPD and CDE trees.

 Multi-class quantification, we actually see a fairly different story, although SLV still performs one of the best. LEPM performs relatively poorly compared to how it performs on the binary quantification task.

 So I won't go too much into this, but there were some incremental variations in trials with degenerative treats, so I think that would be about 30%. So that's a pretty serious limitation of the experiment, something that we can basically develop some heuristics to improve.

 But in terms of these results, we have to see them as basically an interpretation of trials where we don't have such adverse dataset splits. So that brings us to the limitations.

 We also didn't do hyperparameters using the micro-dependence. Now, the quantification method, with several of them, obviously have hyperparameters that we can tweak and really kind of predict their best performance as what we have to do.

 I used temperature scaling, but I think that that was probably a huge negative to our calibration of decision trees, and I should have added some other methods for calibration of future probabilities to improve the accepted method. And evaluating single trees, just to kind of focus on the issue of quantification using decision trees rather than force.

 So again, Schumann-Ross used force of quantifiers, and we could evaluate these single trees and then compare what's going on with the results of those. All right, so in conclusion, we're introducing the.

 Showed that it performs well in binary quantification tests. We showed that ACC does not perform particularly well compared to other quantifiers using a decision tree as a base classifier.

 And additionally, we showed degenerative treatments, at least compared to my implementation of this protocol. Sorry, I can't say for sure, but it does seem that that may have also played a role in the performance gap in the Schumann-Ross study.

 Okay, so LEPM, KDE, YML share actually very similar representations of the class conditional distributions, and they seem to perform somewhat similarly. So as the kernel bandwidth of the kernel density representation approaches zero, the KDE, YML, when applied to a decision tree, actually starts to look very, very similar to CCD's class distribution.

 On multi-class tests, LEPM performed really poorly. I'll tie this again to the KDE, YML paper.

 Essentially, we're coming up with these discrete bins to represent the class conditionals.

 Part of the motivation behind that paper was that as you start proving if you try to discretize, class conditionals as the number of classes grows, you run into a lot of issues.

 That's effectively what we're doing. All right, so the picture worked.

 So there's a lot still left to do in this direction. So ensembles, there's a really elitive way to do ensembles.

 You can sort of basically read this held-out estimation set, so we can build force very easily, and then improve the calibration.

 Come up with a couple of heuristics to resolve the degenerative trees, increase the number of datasets and preference scenarios, and. And hyperparameters.

 So thank you.
