### Speaker 1

Okay, um, hello—uh, my name is `<speaker>`. I'm here to comment on the data science of Netflix.

 I'll start by giving a bit of context. So, at a company like Netflix and maybe some of the companies in the box that you all work at, the main mechanism that we use to innovate on our product is through experiments that we might call "themed tests."

 So this is, you know, sometimes an idea can prove a recommendation algorithm, and how you prove the superiority of the idea is through an organized control channel. I think when we learn about "themed tests" in university contexts, for example, there's kind of always one outcome that we care about.

 Like, we want to measure—I don't know, I'm going to embarrass myself a bit because I don't really know what scientific explanation—but maybe we want to measure, you know, how an increase in chemical or something changes the composition of a number of food or something. But if you think about picking one metric for a company like Netflix, it's really unclear what that one needs to be.

 Of course, like, our business revolves around getting people to continue subscribing, but if you think about trying to optimize for that experiment, oftentimes that is a pretty insensitive metric. So we might be doing something pretty subtle, like how we present different titles on your homepage, and it takes us, you know, it would have to be really bad that our chunks for you—that we get the unsubscribe because we put, you know, a list of that in the description of the video.

 So we often use—so, you know, something like subscriber retention or a North Star, we often use more sensitive prompting metrics, like getting the kids to watch more movies or spend more time streaming from Netflix, or do more thumbs up for things that you watch, that sort of thing. So, you know, if we have this kind of dichotomy of, okay, we measure subscriber retention in the experiment, but we also measure a lot of prompting metrics like engagement, that sort of thing.

 So this works pretty well, again, because retention is pretty insensitive. But there are sometimes these awkward questions that arise, like when you measure both retention and engagement, and the two might disagree.

 You might find that engagement comes down, but maybe people like what they're watching more. So in these rare, you know, instances or very large experiments, you might actually see retention go up.

 And then intuitively, the kind of balance here should depend on how big the experiment is. If the experiment is very small, then it makes sense to look at the more sensitive metrics.

 But if you went, you know, for example, experiment out all frequently and the metrics numbers, then maybe you actually want to look at our answer. So this is kind of the questions that motivate the experiments, how you know to create these two types of outcomes.

 So, um, I'll show a little map of how this works. But this kind of formalizes it a little bit.

 Basically, imagine for every experiment there's a true treatment factor, and the proxy that's a capital P, and a true treatment factor of the outcome, and that's a capital Y. But what we observe is kind of a noisy realization of those two treatment factors.

 So we observe the thing on the right hand, but there's the true thing on the left. And then what we're going to think about in practice is a blend of what we observe.

 So this is like if we were only deciding on the proxy, for example, our weights, our blend would be 0, sorry, 0, 1. Sorry, 1, 0, because we were only putting a weight on the proxy, right?

 And conversely, if we decided to only optimize for the North Star, then we would have 0, 1, and 0 weights. But we're going to think about, you know, blend between the two.

 So how should we optimize? How do we combine the information that we're getting from both outputs?

 And then we're going to think about picking these weights to optimize what happens in practice, which is we observe a treatment factor that's blended of these two metrics. And we're going to say we're going to launch the treatment, which will realize the capital Y there.

 So it'll give us the true reward if we choose to launch, and it'll give us 0 if we don't choose to launch. So we're going to try to find the weight vector, or the kind of optimal way to balance between these two metrics, assuming this is our rule to try to optimize the returns that we get from this decision.

 Sorry, this is a lot. A little bit more math.

 It turns out that it's kind of like, yeah, there's three other green steps. But the only way to think about it is just this thing on the top.

 So the optimal weights are going to be something like a signal. And the way to think about this is, like, the maximum signal that you can have is just launching on the true North Star.

 That has an optimal signal. You're putting no weight on the proxy.

 But it'll get penalized by noise. So basically, for metrics that are very noisy or have high noise signal, that gets—that pulls the weight away from those metrics.

 But in a way, that shrinks as your sample size increases. So this kind of helps to give some kind of formal rationale for the situation that, if you have a really big experiment, then you should just go for what you actually want to optimize, which is the North Star.

 If you have a small and noisy experiment, then you should put much more weight on, like, then this company is really big, and you should put more weight on the more sensitive proxy. So that's pretty much the explanation of it.

 We have this kind of big problem ahead at Netflix that we have lots of experiments. So we can actually learn the kind of signal and the noise matrices directly.

 The way to think about this is, this is the covariance matrix over costs of the true proxy in North Star, and this is their sampling—this is the noise that is in the true sampling of this experiment.

 So I'll circle around a bit later. If you have the time, I may have a careful example of some real experiments at Netflix where we did this.

 But again, the story is, if you have a better proxy metric, meaning it has higher signal and lower noise, then you can run smaller experiments. And the reason why that's better for a company like Netflix is, we have around 300 million members, so every experiment needs, you know, 10 million users, and we can only run 30 experiments at a time.

 But if we can shrink that down to, like, 1 million, then we can run 300 experiments, and so on and so forth. And that's really good because it just lets us try more ideas and we can innovate more quickly.

 However, if you have worse proxy metrics, then you need to run bigger experiments and do really powerful North Star, and that means we have to run bigger experiments.

### Speaker 2

 Can I get a quick snack break?

### Speaker 1

 Okay, by the way, I've got time, so I'll kind of belabor the point a bit more. Here are some simulation results. So on the left-hand side there, these are the returns that arise from the decision rules that say, "Only launch on the proxy or launch on the North Star."

 The blue line is "Only launch on the North Star," and then at very small sample sizes, so all the way down there, you can see that launching on the North Star is a pretty bad idea. The returns are very low.

 The reason for that is it's somewhat powerful, but it's not launching very much. And when you do launch, you're not making very good decisions.

 The orange line above it is the proxy metric, and there you can see that the proxy metric is much better, because here you're actually having a more sensitive, kind of, leading indicator. But as the sample size grows, it's better to try to rely on your true North Star.

 But even better than both of those green lines is the optimal kind of blend that it separates between your proxy and North Star. And here this shows the optimal weight on both.

 So the blue is on the North Star, and again, this is just from the story that as the sample size grows, you put all of your weight on the North Star. But at small sizes, at small sample sizes, small experiments, you want to lean more on the proxy.

 Okay. So here I'll talk about an actual empirical application in Netflix.

 So here in this kind of testing area, the part of our business is trying to decide whether they want to optimize for clips, which is kind of very sensitive. So when we change our weight number, to, like, favor a certain type of content, then clips logs the increase.

 But plays might not, right? Plays are more of kind of a downflow of play, especially if we say, you know, 5-minute play or 10-minute play, so on and so forth.

 Those tend to be more representative of, you know, people's actual underlying preferences. So those are kind of the North Star for this testing area.

 But as I'm showing you this plot, so this is just showing on the x-axis the treatment effects on clips on the proxy, and on the y-axis is treatment effects on North Star versus plays. You can see that there's this very kind of strong correlation between the two.

 So clips are a pretty good proxy for plays, but they're not perfect, obviously. And, you know, it's also the case that in some experiments you have these very significant effects on plays.

 They can be seen on, in terms of the dispersion on the y-axis. And so it would be kind of unrealistic to tell the testing area you should just optimize for clips.

 You shouldn't look at plays, because obviously plays are not that sensitive. So the question is, like, what is the right blend between clips and plays that this testing is drawing a score?

 But you're also saying there's a trade-off here in terms of how often we're launching it, according to the systems in this case. So if we use clips, you have an answer at least, you know, 60% of the time.

 If you use plays, you'll get the answer tentatively, or according to the systems in this case, around 40%. So applying this framework, again, on the blue line is the optimal weight of a calculator for plays, and the orange line is the optimal weight of a calculator for clips.

 The dotted line in the middle there is a typical experiment that tries around 5 million members in it. You can see that the weights are pretty much 50-50, okay?

 But if the group wanted to run larger experiments, it has the trade-off that they would run fewer experiments, then they can afford to put more weight on plays, which is what they actually want to optimize for. If conversely they wanted to shrink it by half, then it could be that, but in that case, it's a very kind of low-signal clip noise stream, and they should just put their weights on a more sensitive metric for those clips.

 But we kind of find that they're in that happy middle, which is pretty good.

 Okay, so in conclusion, we often have this kind of dilemma in prior segmentation, at least at Netflix, where it's not clear what to optimize for. So in this paper, we argue that, you know, the answer is somewhere in the middle, and we just kind of weighted average.

 And then intuitively, the weight increases if you're able to run larger experiments, but that has the trade-off that you maybe slow down velocity when your experiment size is so forth. And so it's still worth investing in proxy metrics, which increase the range of sample sizes for choosing proxy metrics as optimal.

 And then we have an estimator in the paper that shows how to estimate what those rates would be if you have optimal experiments.

### Speaker 2

 Any questions from the audience?

 So I didn't ask the question. So you said North Star metric is something which helps in business development or business improvement.

 And then you said plays is a North Star metric, and a kick is a proxy. So how they are a play and a kick are different in business development and marketing levels?

### Speaker 1

 Yeah, it's maybe it's an oversimplification of my part of the discussion into layers of North Star and proxy. I think in practice maybe a better metaphor is like a ladder or a hierarchy or a funnel, if you will. So at the overall, like, Netflix business level, I think our ultimate North Star would be something like long-term revenue, for example.

 And then we go back by how many people continue to subscribe to Netflix, and that is pretty hard to measure in a, you know, 30-day experiment or a 15-day experiment, that sort of thing. And so we are always kind of looking for maybe not cross, like, maybe not just at the other side of the line of using clips, but kind of intermediate things like sales or engagement, or, like, positive, you know, signals like ones.

 In this example where we applied this metric, this is smaller than the Netflix-wide business group. It's much smaller, and they're just trying to grow, and so they didn't think it was realistic to just say, "We want to measure, like, revenue or retention."

 What they wanted was just plays with their content that would indicate that, like, you've reached a high value from this kind of area. So that's why it's smaller.

 But Netflix-wide, yeah, our North Star is more than 50%.

### Speaker 2

 Thank you. Any more kids? Okay, let's thank the speaker.
