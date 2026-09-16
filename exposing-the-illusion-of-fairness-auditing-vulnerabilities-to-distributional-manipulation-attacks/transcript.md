### Speaker 1

Thanks a lot. So, the main issue I would like is Wispr Flow, and then. In municipality, a lot, and cutting the distance, not necessary for in terms of economic recommendation, but is additive actually possible?

 Is there a problem with additive? First, we present the setting of the edits.

 There's an additive which has a full or minimal dataset, and it's a part of the dataset. The two is audit.

 There are two approaches. Approach one would be to compute the joint estimation.

 The final metric is what produces this price impact. But the auditing shouldn't be the successful way to eliminate anything we can't fix.

 That's why, for those regulators, for juristical reasons, a very efficient additive auditing process, this can happen. What does the verification entails?

 There's an article in the verification which will verify what the article does, what we do, and there's the actual representativeness of this report. Does this report provide it, basically, representative of the entire dataset?

 That's the question we need to answer properly. And so, to summarize, there's an additive which has a full dataset and a model.

 It will be a binary classification model. And the auditor will simply compute the disparate impact.

 There's the definition of fraud with I act, which is the outcome. So, for instance, whether the note has an L for the first one and there's S, which is a sensitive variable, the gender ethnicity.

 Finally, there's a supervisory authority which will have access to the entire dataset and the sample. The question we ask ourselves is, can the auditing provide a sample which is fair enough to pass this audit and fair enough to the original data to be made supervisory protection?

 First of all, if the auditing has a fair entire dataset, then absolutely yes, there's an additional risk. It's only a breaking for additions only.

 We'll try to not eliminate the entire dataset. This question formalizes and produces optimization problems.

 Basically, the goal for an additive auditing will be to minimize the distributional distance between the newly manipulated distribution and its original distribution. This might be fair.

 So there will be adding a finance budget above this distribution. For the disparate impacts, it's above zero basically.

 This is a card amount again, meaning that it will be an additional auditing trying to make detection by the supervisory authority. And it has to be known that the auditing has an idea of what the supervisory authority will actually try to see to verify whether the sample is manipulated or not.

 And the main goal of the paper is to actually understand what's going on first, and then also find cues, find solutions, find advice as to what the supervisory authority wanted them actually to do. First, we take a look at the impact.

 So there's a bias entire dataset which will be fair watched, meaning that the fairness metric will be increased in the manipulated dataset while trying to minimize the distributional distance. It will be a pullback angle and that's a fair distance for the distributional distances.

 We will give an intuition about what is the method to do. Let's say we have China, which in a known context.

 White auditing gender. Let's say we have `<speaker>`, who is a woman of gender, gender woman.

 And let's say we have `<speaker>`, who is also a woman, but gender woman. Those two together, we have a pullback angle will give more weights towards `<speaker>`, gender woman, and less towards `<speaker>`.

 The previous transitional collection will remove the attributes of `<speaker>`, taking towards the weight of the network to minimize the transition distance, and to make it so that these attributes will get close enough. So at the end, she gets a longer modifying of providers.

 And the distribution transitional collection is more straightforward. First, the replace will simply say, "Look, `<speaker>` did get a long add-on," and the automator will give those attributes to `<speaker>`, which was too heavy for her.

 These are the type of manipulation which can be done in order to fool an automator. Third, we take a look at how to detect those attacks.

 There's two main strategies. There's the direct testing with a distributional AF.

 So the one we use is a homomorphic synagogue test as done in the Fukushima hall, which is one of the most related papers to us. And there's another thing we should try.

 If overall we want to see what was the sample, could that be original? Could that be strong to original dataset?

 So from the original dataset, we try more people to sample from this distribution. We look at the distribution of the sample.

 What is our goal? We look at the distance between the source samples and the original distribution.

 This gives us an idea of our acceptance region at lower confidence interval. And we look at whether the manipulated samples within this acceptable region or not.

 If it's all within, we consider that pullbacking sample from the original distribution. If not, we consider that this is an accurate sample.

 And there's a key point here is that. Already take into account the sample size, and for that reason, the test is more robust.

 We are now going to open the window so we can, first of all, see the rotation line and the measurement here. Basically, what we want to understand here is that we can increase the disparate impact continuously, and that the more we increase the disparate impact, the higher the repercussion in the distributional distance.

 So there's a trade-off between fairness and detection with the higher distributional distance, the higher the chance of being detected. And with this, we also have an idea of which one are the best methods for fair watching.

 But what interests us is not how can we cheat an audit, but more so how can we detect manipulation. These are the seven statistical tests we use with the paper.

 So there's a homomorphic synagogue I talked about, and there's three statistical tests, each based on one distributional distance. So pullback angle, transitional distance, and additive.

 This paper is a little bit complicated. There's basically the different manipulation fair watching method.

 Here, there are the seven datasets we tried the methods on, and each one here, if it's a straight line, then the statistical test will not detect the manipulation. If there is one sample, it detected it if the sample size was 10%, and if there are two samples here, it detected for both 10 and 20%.

 The takeaways here are that different tests kind of combine, so using multiple tests is more useful. And the other one is that the sample size is very important.

 The higher percentage of the entire dataset the audit is on, the harder it is to manipulate. The easier it is to detect.

 There's a big table in the paper, but we have the visual here. This is the highest undetected fairness increase.

 Undetected means that neither of the seven statistical tests before consider the sample provided as manipulated. This is the result for each dataset.

 Basically, there's a big diversity between the results. For instance, if you look at the ENC dataset, the original disparate impact was 0.67, and it was possible to increase without being detected up to 0.93.

 So from unfair to fair. But another dataset, for instance, the POC one, the increase was really small, very low, from 0.72 to 0.75.

 The takeaway of this is that, first, an audit is not just an adding effect, but it is important to use complementary statistical tests to combine them. It is also important to have a large enough sample the higher the better.

 But it is just finishing I will say so. Basically, we have shown that some datasets can be increased a lot from unfair fair, which is a problem.

 There's also a little computational problem with the transitional distance. When we have to use 107 levels during millions and start doing fair watch model, so the goal is not to make manipulation in the first four lines, it is to make undetectable fair watching problem.

 Thank you. I really thank you very much.

 Thank you. We have questions.

### Speaker 2

 Hi. Thank you for the presentation. Did you guys get to understand the characteristics of your dataset or more in line on the changes that you've noticed?

### Speaker 1

 Yeah. I mean, I wish distributional distance was more compact for the training.

### Speaker 2

 Yeah. But beyond that, you are away from so you are assuming that the data sample is good enough, is representative of the original context only by the distributional only by distribution. Have you looked into other characteristics of that data?

 Because you might have the same distribution, but not sometimes maybe the same decision boundary and so on. So did you notice anything special about the difference in the datasets that probably caused the difference on the impact on the results?

### Speaker 1

 Yeah. Thanks for the great question. There's two answers to that.

 The first one is that what we do is absolutely great impact management, meaning that it might be possible for an expert to actually have a look at the manipulated dataset and in themselves that, oh, no, this individual should not happen. This is impossible.

 So it could have been possible, but it's not treated fair. Secondly, for instance, we have the ENF dataset, on which the increase of fairness metric was partially not visible.

 And the reason why is because it's basically an anomaly detection dataset in a dimension of certainty. And because of that, the mean of the outcome is very low.

 And for that reason, not a lot of manipulation are actually necessary to change the fairness metric value. And so this characteristic of the sensitive value and the outcome decision definitely have an impact on the results.

### Speaker 3

 More questions?

### Speaker 1

 So let's.
