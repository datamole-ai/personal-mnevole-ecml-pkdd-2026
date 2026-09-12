So, good morning everybody. Uh, I am Antonio Pelitan from the University of Bari, and today I'm going to present our work on dynamic distance weighting for line learning in multidisciplinary price and trend forecasting. So, uh, before starting, let me explain the problem that we have developed with this method.

 Basically, one of the markets that, uh, grew at an incredible speed in the last few years issued in the cryptocurrency market. This market went from a capitalization of more or less 3 billion in 2014 to more than 3.7 billion in the last year, and actually sits at 2.6 billion.

 As you may imagine, the role of this kind of market has been very unstable because it is characterized by an isolated market. And this can also be seen by looking at this graph here that represents the closing price of the Bitcoin over the last 12 months.

 As you can see, there are a lot of swings happening every week. Uh, if we look at this problem from the point of view of a stakeholder, basically the stakeholders are very interested in forecasting these swings, because if they are able to correctly forecast these swings, they are also able to, somehow, maximize their gain or minimize their loss.

 Furthermore, stakeholders are also interested in reasoning on forecasting that are made by considering the latest information available for the market, and not by, um, forecasting that are made by models, uh, that have been trained on data gathered maybe days, weeks, or months ago. So, basically, what we need is a middle that is both incremental, uh, on argue, but that also is able to correctly weight these kind of swings in the market, these extreme values.

 But if we look at the state of the art, we immediately notice that many middles fail on one or the other requirement, because they are batched, so the usual training in which we train our model just once on historical data, and then we use this model to predict something in the market in this case. If there is a shift or a change in the market, these kind of models start to show lower performances.

 Another problem of the other existing middles is that they consider each cryptocurrency in isolation, and it has been proved that if we are able to correctly, somehow, characterize the factor that influences multiple cryptocurrencies, we can, somehow, improve the performance of our model. And then the third factor, but this is mainly most related to general middle that's operating in cryptocurrencies, is that these kind of middle are not used to apply by themselves.

 And this is, I mean, a, a, a desired feature in many fields, but here, I mean, the fields of cryptocurrency, and more in general the three financial fields, as I said, these kind of outlier are the signal that we want to predict, so we must not smooth out these outliers. So for this reason we propose Lemmon.

 This is the general framework that we are proposing, the framework of the model that we are proposing. It is composed by three parts.

 We first perform a temporal clustering in order to group the cryptocurrencies that are, somehow, influenced by similar factors, and then for each instance of the stream we perform a non-instance with increase and a non-imprediction of the increase. Now I will explain in detail each of these phases.

 Let's start from the first one, that, as I said, is the temporal clustering. Here, as I said, our goal, our aim, is to group the cryptocurrencies, the time series of the closing prices of the cryptocurrencies, based on, uh, this kind of hidden factor that are influencing multiple cryptocurrencies.

 So what do we do here? We first calculate a kind of similarity between these time series, and we do this by applying the well-known dynamic trend of cryptocurrency W, and then on the resulting similarity matrix we apply a clustering algorithm, specifically the K-Middles algorithm.

 But we must pay attention because as the market is something that is evolving in time, this kind of factor that are influencing the multiple cryptocurrencies may change. So for this reason we choose to re-execute the clustering after a certain number of instances has been analyzed.

 So basically during the training over, the cluster may change. So after calculating the cluster, we move to the second part, which is also the most important one middle, that is the non-instance weights factor.

 Uh, here, basically, we want to tell to the learner that these extreme values are important even if they may be real. Uh, usually what we do is to apply distance-based weighting.

 So basically we define some boundaries and then we weight each instance, instances based on the distance from these boundaries. However, in this specific scenario we have two problems.

 The first one is that if we want to define these boundaries we must have a kind of, uh, knowledge of the domain that we do not always have. And the second problem is that, as I said, the market is something that evolves in time, and so if we define static boundaries, maybe they will be, they will become not useful in time.

 So what we do is to lengthen the data to define this boundary, and we do this by, basically, applying the well-known runtime adjusted decay box law. So basically we define three boundaries on our stream.

 We have the lower boundary, the bottom, that is separating the lower, the lower extreme values from the usual one. We have the p-middle, that is basically the median of the distribution of our stream.

 And finally we have a p-top that separates the high extreme value from the normal, uh, the normal values. And again, these boundaries are calculated on the stream.

 So as the stream evolves, this boundary will change. I will show you the reasoning example.

 Uh, then after calculating these three boundaries, so p-top, p-middle, and, sorry, p-bottom, p-middle, p-top, we apply these rules to weights for each instance. So the first rule is that we fix a, a weight for each boundary, and we follow the rule that the weights for the extreme boundary must be higher than the weights for the normal, uh, for the medial boundary.

 This is because we want to give more importance to the extreme values. Then for each, for each instance that falls between our boundary we apply the rigid interpolation.

 And we apply this interpolation because it allows us to have, uh, a monotonically decreasing function between p-bottom and p-middle, and a monotonically increasing function between p-middle and p-top. The remaining values are those that are higher than p-top or lower than p-top, and these are the extreme values, so we assign them the higher weight.

 Uh, on these slides we can see how this weighting schema evolves. So here we have our weighting schema calculated after 100 instances, and here we have our weighting schema calculated after 1,000 instances.

 As you can see, even if the shape is still a new shape function, the boundaries are moving. So basically our weighting schema is, is evolving, as the, the, the stream evolves.

 Uh, finally we move to the online prediction training phase where we train one multi-target regression tree for each of the optimized clusters. This is a, a piece more of the model, so this regression tree is an isometric tree, this is an incremental regression tree.

 And, uh, apart from this we also have to aggregate the weights that we have calculated because we basically aggregate the instances in each cluster that have the same timestamp. In order to do this we apply the max domain of the sum strategy.

 We will see this in the, in the results. So moving to the experimental part, uh, we evaluated this system on a real data set that was given from the on-premise.

 This data set has 16 cryptocurrencies, with the interval spanning from January 2020 to December 2022. Uh, each cryptocurrency has hourly observation with 55 features.

 Uh, six of these are related to the price, like the opening price, the closing price, and so on. The remaining one are mostly, uh, technical indicators, like moving averages or volume bands, and so on.

 And finally we have also assessment meters. We evaluated this system on two machine learning tasks.

 The first one is a regression task where basically we want to predict the hourly closing price variation, and the second one is a classification task where we want to predict the trend of the market in two to three classes, so up, stable, and, and down. Uh, in order to choose the optimal, like, parameter we perform the sensitivity analysis.

 Here, I will just show the best result we obtained with this parameter here. So basically we use three modes of training to calculate each kind of TW.

 Uh, we calculated five clusters, and we set the parameter T_update, that is the one controlling how often we have to perform the clustering phase, to five points. So every five points we recalculate the cluster.

 And finally, as regard the, the weights assigned to the boundary, this was the best solution, so 10 for the extreme values and 1 for the median. Uh, we compared our system to two state-of-the-art models.

 The first one is ScarBot, which is a multi-target LSTM that also performs temporal clustering. So this model is also able to consider this kind of factor that are influencing multiple cryptocurrencies.

 The second one is just a single-target LSTM trained for each cryptocurrency. So for this comparator we don't have the temporal clustering.

 Uh, we trained this comparator in a purely batch fashion, and then in order to perform fair comparison we also trained them online by performing the frequential evaluation. And then we have also an online pre-trained batch in which we performed pre-training on the previous batch used for the previous clustering phase.

 As regard the level we have just the online batch and the online pre-trained batch. So on this table you can see, uh, the results obtained, for example, on the regression.

 Uh, on the, on my right, on the right side we have, uh, sorry, on the left side, your left, we have Lemmon with all the weighting aggregation function, and we also have an ablation version on this one in the first column. On this side we have the comparator with all the training settings.

 Uh, as you can see, uh, first of all we can immediately notice that Lemmon in its pre-trained batch is able to overcome the competitor in almost every, uh, cryptocurrency. Uh, but what is interesting to look is that, uh, the weighting schema is beneficial because if we do not use the benefici- the weighting schema, the results here are higher.

 So here we are talking about mean square error. Uh, another, uh, another thing that we can immediately notice is that the best weighting schema allows us to assign higher weights to extreme values, so the max values are.

 Here there is a recap of these results. This is the average rank, and as you can see Lemmon is steadily ranked in the first position.

 The same situation happened when we moved to the classification. So here I show you the F1 score, and effectively for every cryptocurrency evaluation, evaluated, sorry, Lemmon has the best, the best result.

 Again we can, uh, uh, do similar conclusion also for the use of weighting schema because without weighting schema the F1 score is lower, and also for specific, uh, weighting schema that we are using. And these are the, the, basically the, the ranks.

 Again Lemmon in its pre-trained batch ranks steadily in the first position. Another evaluation that we did is the one on the physics, because since this is an incremental middle we must also, uh, be able to provide forecasting in a very small time.

 And, uh, here, thanks to our base learning, which is a supreme, which is optimized for online learning, as you can see, uh, we have very, very small time for prediction, but we have also, we also have a very small memory pool schema. So to conclude, we propose Lemmon, which is a method for real-time, uh, forecasting of prices of cryptocurrency in the market.

 Lemmon is, is based on three ideas. So the first one is the use of temporal clustering to group these cryptocurrencies based on the factor that are influencing multiple, uh, multiple cryptocurrencies.

 Then we also be, we must be able to correctly weight each instance based on how, uh, on how the value that is represented is extreme. And finally for each of the clustering identified we must be able to train a multi-target model in order to fully explore the relationship between the cryptocurrencies.

 As regard the future work, uh, we have a limitation, if you notice, that is basically the parameter T_update. Basically we are somehow fixing the frequencies of re-clustering every five months in our experiment.

 This is not always good. So our idea is to introduce, for example, a drift detector that will automatically trigger the re-clustering phase, so that that will be better.

 Also another, another problem is that we do not perform the economic utility evaluation, so we plan to perform also this kind of evaluation. Thank you for your attention.

 Any questions anyone? Yes or no?

 Yeah. And I think, uh, I think it's a very interesting model.

 But my personal thinking is more about the domain because I have worked with finance most of the time the information that affects the entry and exit of the clients, yes. So perhaps using a similar.

 Okay. Classic Kalimat plus the previous value plus unknown values.

 Yeah, yeah. Maybe similar.

 I don't know if it's correct. Okay.

 This is true. Our idea was that basically even if you distribute, I don't know, information that are outside the tax series because it's parameterized in the tax series, but this kind of factor is reflecting the closing price of the tax series.

 So basically this kind of cryptocurrency moves together. So for example if Bitcoin, the price of Bitcoin is increasing maybe also the price of other cryptocurrencies may increase.

 And so it depends on the score of this kind of relationship. Performing the clustering phase and we want the closing price.

 But yeah, also the idea of improving marketing and selling information is good. Is it allowed to do anything more complicated?

 Like how time is dependent on it. Ah, so time.

 Okay.

 Uh, we did, we did not apply this problematic also. Okay.

 Can we add something? I have a call.

 The features will also have the same effect which is protected. Yeah, also.

 Yes.

 So I'm a little bit confused about the priority. So it's clear for me when you do classification that you want to weigh more your priors because you have less priors.

 But you also did a regression task there, and in regression your prior are like naturally weighed much more because if you use a mean square error or a mean absolute error they are much further away than the definition usually. So they are already huge.

 So that's usually I would say that you need to downscale your priors when you do regression because they will destroy basically all the rest of the. Okay.

 But yeah, that's something to somehow downscale your prior. You want to move just the signal because you want to, uh, you want to predict more accurately this kind of prior, not the normal prior.

 Because if we can predict accurately your prior we can predict accurately when the market will go up or will go down under the point of view of the closing price, for example. But if you minimize the mean square error your prior by itself will be, will be incredibly.

 Yes, but, uh, but since they are outlier, I mean they are, they are less, uh, less likely. So we put much attention on the normal value when we minimize the mean square error.

 Because we want to minimize the error also that. Percentage.

 Yeah, yeah, yeah. How, how, how?

 Yeah. Did you also consider other kinds of metrics like time weighted, volume weighted.

 Yes, yes, yes. We did.

 We started to do one last year. Yeah.

 We can call it. Uh, we don't know because we are still, uh, I don't know.

 Because now we are providing the, the, the pattern we are also following on other kind of models. We are going to, uh, move back and forth.