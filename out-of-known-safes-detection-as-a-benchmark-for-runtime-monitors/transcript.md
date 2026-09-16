### Speaker 1

Good afternoon. Thank you for witnessing tonight at the SafeGrid Summit. We'll be talking about the handheld, flexible microgrids, and wearable AI systems.

 Um, one of the core solutions for this is what we call real-time monitors. So, real-time monitoring assesses load activations and outputs for each input, and based on this it decides whether to accept the prediction from its model or reject it and say, we'll do the same thing for the rest of the system.

 Um, and here we have this popularity of this technology in the industry. Also, in this field you've seen quite a bit of difference in other techniques, as we will also see through this presentation comparing those that are currently in use.

 Um, and this can also be easily best practiced in all these techniques, which we just used, which techniques we just used, and how we are doing it for a while in the first place. Um, and this is another thing: the role of a real-time monitoring benchmark where you also have to post quite a lot of information.

 So, the goal of a monitoring benchmark is to evaluate and attack monitoring techniques relative to some kind of IoT or monitoring decisions. So, in essence, this goal is helpful for you to maintain a good, safe updated tool for better data performance, and then it's very related to safety.

 Um, this is actually just why we're talking about it. We want to accept all the examples that we don't use for safe scenarios, but for safe scenarios, and reject all others.

 So, in essence, this tells you why this goal meets. Um, and as you will see in the next few slides, when we compare different monitoring strategies or monitoring benchmarking strategies, we'll see that there's quite a lot that is new in terms of, okay, what are we doing in our toolset in real-world monitoring benchmark, and how do we map them to the successful and the checksum value.

 Um, so first of all, let's first go through the common grounds in terms of which types of samples can be seen here in the room. Uh, especially in the vision datasets that I'm working with, and the vision datasets out of the street food vision datasets, there's mainly five different types of, uh, sample scenarios that we can encounter.

 So, here, for example, we're taking some kind of an autonomous sleigh. Um, you get a dataset containing, uh, road-occupancy data, for example, like cars, bicycles, pedestrians.

 Um, and this is then within the street food datasets. So you have the dataset that we use for, uh, development.

 Note that we're eventually going to collect and save prediction cities in the street food datasets, and also when it goes more the early stage predictions. So even in our development datasets, we'll know what kind of data it takes.

 Um, and then there are two types of shifts, or strategy shifts. Um, the most normal one basically where we indicate some classification and how do we do the loss.

 So scenarios. So, for example, could be hours that are managed that you didn't encounter, or, uh, you didn't take into consideration.

 We then also have a development shift, and development shift is slightly different in the sense that we still have the same losses, but now a different and feature distribution. So it could be the occurrence of codex losses in regions where we have like a certain value of, you know, failed threats, and you select it on the threats that you're looking at.

 Um, but note, we have the same losses, so we can still make a corrected prediction, but also in the case of a block, we need a longer prediction on the same prediction. Um, so here are these five sample cases.

 We can take a quick look at some of the detailed frameworks for, uh, benchmarking real-time monitors. Um, I won't really go into too much detail to the effect.

 Um, but as you see, not everyone accounts for, uh, the same types of sample scenarios. So, for example, out of distribution, mainly in vision and these samples, uh, these samples, they usually don't really account for the development shift.

 Some of our strategies do, like full spectrum out of distribution detection on VO2, they account for it, but as you can see, they don't really include the vision now or the sample or the checksum. Um, but also focus mainly on this on the right of the table, where we have four categories: one for safe detection, out proposal, and another one that's more specific about distribution detection, um, which we consider the most competitive.

 As you can see, we're largely agreeing with the same kind of mapping of sample threads, but there's one big difference, and that's that we deliberately ignore the likelihood that there's a cooperation in samples and how we collect those reports. Um, and as you can see on the slide, we've got a cooperation in the sample.

 But let's first introduce you to the cooperation that happens. So what is now doing this corrected predicted cooperation in samples.

 Um, there are three most, most things you can do with them. So first of all, you can check them.

 Based on the moderation that's working there outside, there are 34 examinators, so you should filter them out. Um, which is similar to what you do with this.

 Uh, we can accept them. So closest in the name of competitive is kind of okay.

 So based on the moderation that we put, model and the predict setup should be able to generalize. Um, then one less approach, well, less consistent approach is ignore them.

 Please take it. There's a few better from a safety perspective for very large classes.

 We're really focused on how well this works in certain safe predictions. Well, you do have to account for that availability, but it's mainly looking at the dangerous situations that you want to photograph.

 Um, but what you'll see is however forcing and reject and accept that. Biases to monitor selection.

 Um, which will produce, uh, a new class. So instead of forcing the value available on these negative cooperation examples, we're going to predict it on the different samples.

 One of us deliberately tries to do examples from the exclude them from the benchmark scoring. So in these two examples, I'll try to convince you of this idea and also demonstrate that absolutely all the cooperation examples are motivated by ignoring when we predicted cooperation examples might be the best case or the best forecast, but mostly in the benchmark.

 So we'll start with UX units. So we'll do a vision experiment and a vision analysis for that.

 So in this vision experiment, so a small-scale experiment where we display two monitoring scores. So a monitoring score will usually output a continuous score for, for example, PLM groups and distance and features based on the fitted samples to the distribution samples, the samples to, um, the sample we see at the moment.

 Um, so this will output a continuous distance. Um, so we display two monitoring outputs for this event, for the same distribution samples.

 So both correct and incorrect, and one for strong cooperation examples. So both sorts of correct and incorrect.

 So we'll end up with two posteriors. One will see 14, and one will have a bad sequence in C samples, and one will see 14 and one with strong sequence in C samples.

 So just to visualize the analysis of the experiment, so we have a bad scenario where we see a little bit of blurred, and we have a strong scenario where we see a lot of blurred. So it's just one of the different examples of the experiments.

 And based on all these distributions, these four scale feedbacks of samples, we can try to calculate the optimal threshold to separate the accept and reject samples according to the different values we just introduced to accept the reject or ignore them. Um, and these are the results.

 So in blue, we have, um, in blue, we have the scores here for the samples that's, um, follow the safe predictions. So in dark blue, we have the scores here for the samples that are in the distribution as safe.

 In light blue, we have the value check and testing. In dark red, we have the industry which is unsafe, and in light red, the industry which is, uh, relatively cooperative and unsafe.

 And if we look at the left here, the mild cooperative prediction, you'll see that it's, um, we're going to try to force what we already do is the rejection of all cooperative examples. We will see that, yeah, this would mean we have to accept this, this distribution samples here, which is, yeah, so we've followed that and moved our threshold all the way to the left.

 And as you see, it's very much aligned with the correct indicated industry examples, which, of course, you want to pass through because you want strong availability of our monitoring models. Um, so now we're going to.

 It's the process of the results that we're putting into our acceptance threshold, so we know the benefits. Um, goal was to pursue for the, um, strong cooperative example.

 So as I mentioned over the east coast, we should accept this corrected predicted cooperative examples. So we in this distribution.

 This would mean we would have to accept these scores. This would move our threshold all the way to the right, which means that, yeah, it's also accept all these bad samples that are within this, uh, distribution.

 So this is not really something we want, especially from a real-time monitoring, but just really focus on rejecting these dangerous situations. Um, so our business model here, this is the main slide in the presentation to get an intuition about these ideas.

 Um, the next experiment, it's a bit larger scale. So it's a vision analysis experiment where we're looking to, uh, larger scale, so more datasets, more cooperative scenarios.

 And then it's consistent of two main examples. So in the first one, the main question is, when developing local models, this is a different detail of these cooperative examples with different test outputs.

 So as we say, we have different languages, and we have different ways to accept and ignore them. This includes two different languages of our, uh, monitoring models.

 And as we see here, `<speaker>` and I hope, um, we do actually have different languages. So, for example, in the case of C14, um, we're going to apply this to, uh, the ocean here as corrected cooperative shift.

 We see that happens over the years, so we're accepting these kind of samples. Results in, um, being connected as the best monitoring techniques.

 And then, um, yeah, then it's being chosen by VO2 inputs for this example scenario. So it just actually leads to different languages of the best monitoring techniques.

 So it's important to account for this. Um, in the next subset, we then look at.

 Okay, we have different languages of the best monitoring techniques. Here we see some general plans and which kind of, uh, which kind of techniques we, uh, yeah, visualize as best monitoring techniques.

 Um, and here you can see some plans, um, especially forcing, by forcing examples of these corrected predicted cooperative examples. So as, as okay it is.

 As we will see, it favors high availabilities at the cost of lower, um, at the cost of high availabilities. So as you see here in yellow, the technique being preferred by us is okay.

 This has a huge impact on availability rates. So high availability, which is super forceful.

 But there are good failing rates. So the number of samples that should be rejected, but are actually passed through.

 We also see a lot of high failing rates, which is so forcefully in the green ones. And this is in line with what we expected.

 It's in the right. It's no case that it's failures going to be the threshold for cooperative techniques.

 Um, and then looking at the opposite force, we check in all cooperative examples.

 Um, this is not actually the case where you've got, you don't see real data, so it's mainly for future projects. So since I'm running out of time, key takeaways.

 So I'll summarize them in one sentence. Um, so current frameworks, forced, accept, and reject, only correct validated examples of corrected predicted cooperative examples.

 As you see, it's basically possible to do without artificially distorting some optimal monitoring thresholds managed. And what we're still actually getting into here is ignoring then this best-case approach.

 Um, and this will choose work, uh, where we're trying to accent small analysis and analyze to better differentiate what really came over into the better case by VO2. This is hopefully a better point.

 Um, that's it, I think. So that's about it for this presentation.

 Thank you.
