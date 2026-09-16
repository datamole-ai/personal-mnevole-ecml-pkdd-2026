### Speaker 1

Okay, uh, thank you. So good afternoon everyone. My name is Mahul, so I'm from the University of Manchester.

 I'm at the Department of Social Statistics, so I will present my paper, "Understanding the Technology of Quantum Data Synthesis: Starting Fast and Sampling." So, yeah.

 So, as I mentioned in the title, it was about sample and data, so basically this is sample and data. Basically it consists of, yeah, mixed variables.

 There are categoricals, there are also some more memorable, called. Usually we can call it as, uh, simplex or multiplex or continuous graphs.

 But the problem is more on the. So in individual level, in the sample and data usually, there are many demands on individual levels, so like institutions always, like, ask for demands.

 Like, okay, we want this data, but the problem is that sometimes the institutions don't want to share their data. Like, oh no, it's like private, sorry, we cannot share it with you.

 So, yeah, I think, like, one of the key obstacles to this problem is that, uh, sample and data synthesis, but one, one, I think one of the most recent techniques is the latent generative model. You can imagine like, uh, stable diffusion or flux, but it's done in sample and data.

 So basically this is about flow models, diffusion, flow matching. So the research is, uh, maybe it's like, has been published in many locals or some nationals, which basically said flow matching and diffusion are the same, right?

 So, yeah, basically they are a bit the same in theory. And also I think, like, what's more interesting is that it turns out instead of doing ODE in flow matching, usually in flow matching we just do the ODE, but also we can do stochastic dynamics.

 And basically this theorem says that the score and the velocity is actually interchangeable. So we can basically, uh, calculate velocity from the score and then calculate the score from velocity.

 So by that consequence is we can this is how basically you run, like, on the same flow match. I run on ODE and run on SDE.

 Basically they will turn, like, yeah, guarantee some, uh, marginal distributions and eventually, like, if you get the t equals to 1 and you get the original data. But the question is that, yeah, this is like a beautiful theory, I think, and I'm not going to call it a thing, but how it behaves, or how these configurations, like, behave in sample and data synthesis.

 I think that's, like, the big question. That's why it's an applied data science.

 So maybe I will introduce a bit about the model design in sample and data, the latent generative models. So it was introduced in about '24, uh, the TAPSIM.

 So basically it's, uh, like a sample and generative model, and the main component is just the VAE, which is, but the difference is that instead of, like, regular sample and VAE, we have which has ML, the MLP, but it uses, like, transformers on the encoder and decoder. And, yeah, the, for the, instead of, like, uh, propagate, uh, feeding this, the random normal distribution into the decoder directly, we just learn the latent distribution using, yeah, diffusion or formation.

 But in TAPSIM it was learned using diffusion. So basically I changed this part into, uh, flow models.

 So it can be, like, anything: diffusion, flow matching, correctional flow matching, whatever. So this is, like, uh, the model setup.

 The, yeah, it's kind of, it can be interpreted, like, in different things. So, like, in flow matching we call it velocity, in score matching we call it score, or sometimes it's scaled.

 In, I think, the denoising, score matching or denoising, diffusion model, the continuous correction, of course, not the DPM, it's also, like, matching the noise in continuous time. And also the last one is, like, the correctional flow matching.

 It basically, uh, yeah, matching the different things. One is velocity, one is the score, one is the, uh, at the beginning.

 So it's like the early point, the X0 or Z0, because it's latent variables. And the other one is, like, matching the endpoint.

 So the predicting, like, which correctional parameters it might be possible to represent the original data. And, yeah, and also here's the calculation of the velocity and the score for each component.

 So it depends on, uh, yeah, what training mechanism that you use. Uh, the calculation is quite difficult.

 But in flow matching basically you just, like, predict the velocity and the score also. But it's, I think in this implementation it's scaled because, like, if you just predict the score directly, usually when you matching the score, calculate the original score, it will be, it tends to be collapsed.

 So that's why I scaled it with, uh, sigma squared in the, uh, in the second step of the implementation. Okay, so, yeah, this is the algorithm.

 Basically it's almost just the same algorithm. Like, as we know, like, in diffu in, especially in flow matching.

 So we just, like, sample the t and then we just do interpolation. It can be, like, linear or maybe, like, using the diffusion interpolation, variance resurfacing.

 And also in the end we just predict the target, what we want: velocity, score, noise, the posterior name, and also calculate the loss and so on. So we just, like, basically this is the first step, and you can go, like, with this setup.

 It depends on, uh, what you want. Okay, so, yeah, this is, like, the experiment setup.

 Uh, I did it on seven data. Basically it's like, I tried to, instead of, like, using all the UCI dataset, I tried to, like, more real world.

 That's why I used the census data. Basically it tells about the, uh, profiles of, uh, individuals in some regions.

 So it's like a, like, more official statistics, uh, approach. Yeah, so these are the dimensions.

 So these are, like, try to compare, uh, target, path, sampling, solver, and the budget. And, yeah, this, uh, this is the, uh, evaluation.

 So the main evaluation is there are three, actually. The ratio of counts is just basically comparing the, uh, like, frequency tables for the cross-simulation between synthetic and real ones.

 And this is the confidence interval overlap. Instead of, like, using machine learning, I used the statistical inference.

 So basically I tried to compare the regression coefficients in when you do it, when you do it in synthetic data and compare it with the original one. So you compare the confidence interval and see how much it overlaps.

 And this is the risk. I basically, yeah, try to see the whether the synthetic sensitive data can reveal the sensitive attribute of an individual given the adversary or the, yeah, the bad person has some partial information about the original data.

 Yeah, and also, uh, some evaluations which I'm going to use in machine learning: F, trend, the matching score, and also some distribution distance. Okay, so let's go to the results.

 Basically the point is that, uh, yeah, flow matching and correctional flow matching, I think so far is, like, the best training settings that I saw. And another thing is, like, changing the linear interpolation of, usually we people call it OT, to the PP, to the diffusion, tends to reduce the utility.

 So you can see in here it's, like, kind of like the line tends to be, like, uh, go down. But it's, it's, like, exception for correctional flow matching.

 To be honest, like, it's not strange, but it's quite interesting. And noise matching and score matching, uh, it's quite, like, more risk, like, quite conservative in the risk.

 Uh, but the problem is that they need to reduce the utility of the data. And also, yeah, again, uh, the main point is that in practice, although, like, the theory is beautiful, the target choice has the large impact on the performance.

 Okay, the second result is basically says, uh, that the integration time. So the question is more, like, if we stop the integration at some point, like, not, like, until t equals to 1, how is the data quality?

 So it seems like it's, like, different trends between OT and PP. Probably it's because the OT is kind of, like, straight interpolation, but the PP is more, like, uh, it's like starting, like, with small, small value and then suddenly just exploding.

 So it's kind of, like, uh, different trends in here. That's why, like, in PP you might need, like, to fully integrate the data to get good results.

 But for the OT, it's kind of, like, a some kind of good trade-off between the utility and risk, which is, like, kind of, okay, I want to, like, more risk. Like, I'm risk averse.

 I don't want to have, like, wrong privacy risk. So, okay, just add it at some point.

 Usually, like, maybe 0.8. It's okay to do it.

 So that's, like, uh, I think, uh, that's what happened, like, in this result. The third one is more, like, on the steps.

 So if, if we because, like, basically as I mentioned, the, we used, like, uh, yeah, earlier the steps for the ODE and the midpoint. Basically what happened is that, uh, yeah, the best one here is the flow matching and correctional flow matching.

 But correctional, what's nice is that for flow matching it's, like, it's only good in the OT when you use the interpolation, but for the correctional flow matching it's good in both. It's like, as you can see in here, the pink line in here, it's like across, like, all your.

 And for these three steps, it will, it's will, it's better than the original flow matching. The correctional one is nice.

 Uh, yeah.

 And also, like, another thing that I want to note is that, so when, yeah, the, the risk, like, it's like, at some point it's kind of tends to, like, a bit converge, like, kind of flat. But the utility is still, like, kind of keep rising.

 It's just, like, yeah, uh, it's also, like, a good finding to, to see in practice. And this is the last finding.

 Basically, uh, yeah, just try to compare with, uh, some, yeah, common generative model the last state of the art. So I, I just, so I, I did not, like, put everything in there.

 I just, like, I just chose, like, the best configuration. So basically it's the, uh, for the flow matching, the optimal transport for the utility, uh, and PMF are the best choices.

 But basically, like, what the point is that, uh, they perform good, uh, especially compared to the TAPSIM, uh, which is, uh, the state of the art in latent generative models.

 Yeah, and, yeah, the last thing I wanted to say is that since, like, this is, like, five. And so there will be, like, of course, practical implications.

 So what I want to say is that maybe if you want to, like, share, like, synthetic data, especially using maybe this, uh, latent generative models, what we can do is, like, okay, we select the flow objective and the interpolant. Interpolant means that the, whether, like, it is straight or maybe, like, using the diffusion path.

 And then we train the flow models and then, and then after that we can do the sampling steps. We see, select solvers, uh, the steps, endpoint, and then we generate it, evaluate, and see if it meets the targets, what that we want.

 Depending on what institution, maybe you want more facility or maybe you want, uh, the risk. Like, okay, I don't want, like, to be, like, privacy to be, like, more private.

 It's okay. Depends on, uh, what you want.

 If it doesn't fit, then we can try, uh, different setups. Like, maybe, yeah, you can try from scratch again.

 Otherwise maybe you can just select, like, which, uh, type of parameters that, uh, you might try. But this is, like, a bit more heuristic.

 But maybe if someone want to continue with, like, maybe putting some, yeah, uh, outside approach at a lot, but it might be good. It's like, this is, like, a bit, like, a post-hoc step.

 So it's kind of, like, being nice if, like, there is, like, some automation to find the best setup based on, uh, the requirements. And, yeah, if it meets targets then we can, uh, we can obtain the candidate datasets and maybe some reports to document.

 Okay, for the closing, yeah, that's, yeah, I think I've said it multiple times. It's, uh, equivalent in practice.

 Uh, yeah, I don't know if it's really best of bad news or not, but I think it's quite common. Theoretical corrections don't always translate to identical empirical behavior, especially under finite compute because, like, we have, like, limited budget and compute.

 Uh, yeah, learning target and probability part, then determining the utility and risk. So, yeah, it, it, I think it, it has, like, quite a significant role in defining the what we will do.

 But so far I think what I can recommend is, if you want to, like, more higher, like, useful data, I think flow matching operational one is good. But maybe if you want to, like, quite risk averse, like, want a lower risk, maybe you can try the noise matching or score matching.

 And, yeah, uh, last one is sampling choices has the, uh, practical control. Yeah, many, many configurations that you can try post-hoc, yeah, in practice.

 So it's not, like, any kind of, like, maybe the, maybe generative model is favored. Just, okay, let's try one.

 Let's try one, one configuration and then we're done. Uh, yeah, so it's my presentation.

 Thank you. Terima kasih.

### Speaker 2

 So in this, uh, can you please give a summary of how you calculate the utility?

### Speaker 1

 Uh, yeah, so basically, yeah, the utility consists of, uh, yeah, I can think of them. Uh, so, uh, yeah, so the first one is ratio of counts. Basically it's just, like, so you can imagine, like, frequency table.

 So it's like, uh, maybe how many numbers of, uh, how many people there are, maybe high school graduate, how many people there are, uh, maybe, uh, college graduate, and so on. So you have the numbers on synthetic data, you have the numbers on real data.

 Basically just comparing, like, if you have, like, the maximum and the minimum values of this one, if it's similar, then it will be, like, similar. So it will be like, yeah, that's basically just coverage of the frequency table.

 And also both in not just single reference, but it can be cross-simulation. So with some maybe the education and competency level, I can say.

 So it's like, they compare it between the synthetic and the original one and see, like, how much it covers. And the second one is the, and the third, yeah, basically those are two, ratio of counts.

 And the third one is consistency of overlap. Basically it's just, you can imagine if, maybe if we, we mostly in machine learning do regression just for prediction, right?

 But we can extract the data and we can interpret the results. So what I did in here is, like, okay, I get the data, I get the confident interval of the data, and then I compare it in synthetic data and, uh, real data.

 I think, like, it's nice to do because, like, uh, especially in really because, like, I'm in social stats, so basically social, social sciences, mostly we do, like, inference, like, on the parameters. That's why I focus, like, on the utility on this instead of, like, doing some machine learning.

### Speaker 2

 Thank you.
