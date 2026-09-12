Hello. This is a tester from my family. I imagine there's a serious connection between the coder and the data dynamics, which is good for teachers.

 The company is a little bit long, and it's a combination of work of the student, like the student docent, dental, and the volunteer, and also a couple of my colleagues. My name is Daniel Yu.

 I come from the University of Technology. I come from the School of Management.

 All right. So let's first—so first we try to do the forecast.

 The forecast problem definition is that just based on previous talk and all this talk of cryptocurrency, we have many, many cryptocurrencies and also each cryptocurrency has multiple features. And then at each time point you have a list of features, time point, and a lot of observations.

 You put everything together so that you can tensor. So the tensor is one you look at the time t, and then you write it down by the xt of, you know, to like the m cryptocurrency and features.

 And then if you actually collect our history from time one, you capture the key, and then you can tensor. All right.

 So our goal is that based on you know this information from 1 to t, and then I want to put that forward from the horizon 1 to up to l. So this is the problem we try to solve.

 So this problem happens in lots of finance and also in the medical. Medicare, for example, ECG, different patients, and then you try to look forward what will happen to the patient biologic science.

 I brought you some here. So here the time series is that you look at a few variables, you look three days forward.

 Now you look at cross-section. So what do you do?

 After cross-section you look into the time point. So there are a couple of methods to actually solve this.

 So you have this foundation model, like for example IMFM. And then they train on lots and lots of time series.

 But you look at all of the food. So these foundation models, you only look at actually all the different variables independently.

 So therefore the cross-correlation among these variables will not be preserved in the patient. That's number one.

 So number two, and then we also have this tensor task. Essentially you told this tensor by the CPD composition, one dimension time, and then you're just using the time factors to look forward.

 And then they also have some problems. First, usually your tensor time correctly is not that long to satisfy the cross-section information.

 Number two, and then you actually because the CPD, the graph is your limitation. So you actually encode all the dynamics into the time series on a limited number of the, like a random R, limited number of dimensions.

 And then you don't have enough coefficient or parameters to preserve on these dynamic features.

 So in order to solve these two problems, we still actually need to do tensor decompensation. We still do some sort of tensor time fm, combine these two with tensor time fm.

 So here is a little bit busy pictures and then about our architectures. And then you can think about this is the decoder architectures.

 And then you have a bunch of, like underneath, suppose you have all these factors, like factors, like the number of the cryptocurrencies, in the middle the factor about the variables you collected, and at the bottom is time factors. And then this is your architecture, I call this the median factor.

 So this median factors you put the decoder, and then you encode in our tensor. So that then once you look at backward, and the backward is actually you try to find the encoder in order to find our control configurations that you have the factors.

 So the beauty of these things, I just extract this latent factor in terms of time factors, and then we try to eliminate it. Because like we have lots of foundation model to do time series prediction.

 So all the time series you probably already have looked at that before. So you might have some sort of look at time bias.

 But for this hidden latent factors, you never actually solve the problem of any foundation model because this is dynamically reconstructed by the data. So that we eliminate some sort of, like this look at bias or some sort of already seen observations.

 It's not prediction, it's just memorization. So that's the architectures.

 And then so we can think about this, you can reconstruct these tensors, and then you have this during reconstruction you learn these time factors. Then the time factors and you throw them into time fm on the right-hand side, and then try to predict what the future looks like.

 So therefore in this one, and then you can sort of, you can look at the individual time factor, like a time factor in terms of columns. It's one single variable time series.

 And then you just chop that into pieces, and then into a token, and then this is essentially transformer architectures. And then you can look at what the future token looks like.

 That future looks, the tokens happen to encode into a time correlating l. All right.

 So now you have additional time correlation in the forward, and then that prediction became actually sort of reconstruction because you have preserved that with the static factors on the number of cross-sections, number of cryptocurrency factors, and then you just multiply with the time factors, and then you can reconstruct your future.

 So that's the entire architectures. And then let's look at a little bit of details here.

 So one observation is that this is a tensor decompensation, but we can call this we can all the algorithms are already inspired by stochastic reading descent. So for example, reading descent, we have to look into all the training data, and then you can sort of adjust the parameter.

 But stochastic reading descent is that I make observations in the tensor at vkkkjgt. And then I just sort of how much, how good fitting you are in terms of observations, and we can actually sort of the ground prediction values.

 And then you start into the reading descent, trying to actually figure out what's underneath, like u factor, b factor, w factor. So that's the stochastic reading descent.

 So that algorithm looks particularly reliable, and then that's also all the advantages of stochastic reading descent was actually sort of transferred into this architecture design. One big aspect is that we can deal with sparse data.

 For example, and then we don't have to have an entire cross-section observation full sheets. We have a few observations representing this mask, and then we just mask version of actually this really good tensor decompensation, and then we can figure out what's underneath you read the.

 Correct? So when we actually do a prediction on the time fm, we don't care about the observations, we care about the latent factors.

 So for the latent factors, always actually use a full data sheet. All right.

 And also we can actually sort of add this recommendation, for example, like a post-ordinal recommendation on the time factors. All the different columns are post-ordinal.

 So that's coming back to our previous observation of time fm. All these different columns can be reminded.

 But once we force that post-ordinal on the payment factors, and then we can use time factor, like time fm. So that's actually an algorithm design, and then that's part of the experimental section.

 So experiment making is three data. One is a learning forecast, different company in market, different fundamentals, and then you make observations about 160 quarters.

 And then you want to predict what the future looks like in the financial report, and that's EPS, earning forecast. You also have raw market sales data.

 This is one category that's different state, have different stores. Each stores have like different items.

 And then we try to actually predict each individual sales record for each individual item. All right.

 So this is also an action we have tried to have a tensor. Another one is rideshare, and then in the New York state, in the New York City, we have 400 to 500 months of observations on like a different location, 150 locations.

 And then we have each location, each record, we have 15 features. So that's we have like some partial observations on the EPS, internal observations on our online data, and also like half observation on rideshare.

 So we have so we try to compare like this foundation model for time fm and time graph, and also like this traditional model tensor task, and also that's not our internal data. So before we do the observations, we do some simulation.

 We simulate. We try to see how good our algorithms are, and then sort of we can sort of simulate like this underneath that have low rank and high rank.

 And then we have different data, like sort of data correlation. And then we can compare in-sample analysis with our algorithm is actually this standard tensor task.

 So 80% versus 78%. It's not a significantly bigger improvement, but once your ranking became really high, 71% on the, like in our samples, on like sort of CP standard method, it's 59.

 And then once we move out to our little example observations, and then we can see immediately this CP standard algorithms, the R-squared became negative.

 All right. So that's the EPS.

 I only talking about one EPS, and then go actually conclude my talk. So this EPS is like a sort of we have this sparsity of data, and then we will actually try to compare the tensor fm, our algorithms with like a standard time series time fm algorithm.

 You can also have the CP algorithm, and then you can instead of using like a sort of like a you can also couple the tensor like time fm with CP, and also tensor CRU, like all the different time series prediction algorithms. And our algorithms actually sort of 82% R-squared versus remaining.

 Okay. All right.

 So this 82% is first time actually we all perform a very simple model with consensus learning because you get all the analysis and you get estimation, you do the average, and then that R-squared is already actually sort of 86% above. So this is the first time actually we all perform on this sort of like a market analyst, like a consensus prediction.

 So that's actually how we can know like the future earnings price. All right.

 So that let me skip all this experiment part, and then talk into the oh yeah, one last thing, like sort of when we started to do the stress test, we just had to through lots of data, through 10% data, 20% data, up to 90% data. We can see actually sort of the tensor fm or standard algorithm, the performance is dropping, and then we can sort of see like our line R-squared doesn't maintain the same on our algorithms.

 So this is our algorithms. And then if we take home message, the first one, so it's a tensor decompensation, we transfer the like the prediction problem in the raw state into that latent state.

 Then eliminate look at bias, eliminate memorization. And then when we do the forecast problems, so we can use zero-shot or frozen time fm to forecast latent temporal columns instead of like a noisy incomplete fibers of like observations.

 And then evidence is giving us promise for the sparse data. But one second, sort of the algorithm actually lose a little bit of advantage once you have 100% of observations, and then less correlation only.

 Okay. All right.

 So that's the prediction message. And this is a very good, interesting look at the.

 Can I require just one question?

 Yes.

 One question.