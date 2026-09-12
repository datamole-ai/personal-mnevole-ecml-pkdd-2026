So, last presentation. Uh, so what's your definition? There are two particularly different conceptions: incorporation, and—

 Wait, can you repeat that?

 So we've heard about, uh, estimating the actual functionality of a class using an AI-powered Pixel Ring framework that we're about to introduce.

 To give a short introduction, so the focus of the work is, uh, the focus of exactly this class project. This is a project in the Netherlands where many companies and organizations and universities are working together, and they want to create exactly statements and promote electric mobility.

 As you know, electric vehicles, they can help by contributing to transitioning to sustainable transportation. They can help in reducing greenhouse gas emissions, and also, um, contribute to increasing the cost of fuels.

 Electric cars, in a couple of years, are expected— the number is expected to increase, and that is due to regulations expected to lower lower total cost of forging. And this adoption in the context of logistics operations can introduce an extra operational complexity, and also introduce new challenges for fleet managers, for managers that, uh, are managing fleets of electric cars.

 In that case, predicting models can be very useful. They can serve as whole discussions, and we know energy consumption of cars, and we can do better decision-making so the managers can stop, uh, order the truck to stop at the exact station or assign a different vehicle, or send it, um, through another route.

 The related work surrounding the topic is concentrated into two categories. The first one is the physics-based approaches.

 So here they try to model the energy consumption. This can be done through the power train efficiency or the power of the generated vehicle.

 Then another category is the data-driven methods, where they're taking classical physical methods and also machine learning. For sequence-to-sequence tasks, RNN search can be popular, also transform train models, and lately, for time-sync tasks, also foundational models such as time-syncing.

 This is the framework. It's called the Grid Energy.

 And so the main block consists of two deployed models. One is the first one is the printing model, the other one is the input-output model.

 So the printing model runs on inferential only once, and this is before it starts working. And then the inferential model provides uncertainty interval estimations throughout the trip at the different prediction points.

 And the two uncertainty intervals from the two models are combined through Bayesian fusion to provide the final estimate. This estimate is expected to freeze during the trip, or where the estimate is given.

 Also, the models communicate with everything surrounding, so the data, the decision-making side, and also the track. And in order to process the data, we use also the route-to-file generator.

 The route-to-file generator produces the features that we can see on the right. These are the plan features.

 So if we input to the route-to-file generator two coordinates, for example, the point of starting to the trip and the point of ending of the trip, it can produce route information. So for example, at this position, what is the date, what is the day of the week, what is the time, minutes, seconds.

 Also, geometry about position, for example, how much is the angle of the road, how much is the elevation, the height. And then also it provides information about the type of road, if it is a highway or a narrow road.

 Then on the left, you can see also measurement sensor data. It's an extracted sampling during the trip from sensors that are embedded on the tracks.

 The target for both models is generally energy. But both models estimate both the power at this position and also the time elapsed.

 The time elapsed, what we mean by time elapsed is the time since the previous position. So if we multiply those power and the time elapsed, we get the energy.

 So the reason we used these two values instead of just predicting the energy is that we could see in more detail where the errors accumulate. Is it on power?

 Is it on the time elapsed? And the time elapsed as well is useful in that case.

 So it was useful in that case.

 Also, to note that the measurement sensor data, because they are sampled throughout the trip, the printing model cannot take them into account. So it is trained only on the plan features.

 Therefore, the measurement sensor data are only used for training the in-car trip model.

 Then we can see how segment the trips, mainly in the printing stage, so for the printing model. We split the trips in a slightly different fashion.

 Therefore, they go from the printing stage to five positions. Each position is ten meters away from the trip from the next one.

 We introduced three temporal changing scenarios. So in the first one, the time fits.

 They recover sequences at the same position as they recover the sequence. Then in the second scenario, they are partially overlapping.

 In the third scenario, they are not overlapping at all. This was done to investigate where the temporal dependence between the inputs and the output.

 So for example, if the electric car suddenly the driver suddenly decides to stop, is the energy consumption of the current position affected, or is the energy consumption of the previous position affected?

 This is a schema of our comparison for the printing model. So for the printing model, we compare three models: an XLSTM, the time-sync P, and also the temporal fusion transformer.

 The XLSTM cannot take into account categorical features. So time-sync P and the temporal fusion transformer is the potentially inherent advantages.

 The advantage of the temporal fusion transformer is also that it can take into account the differentiating between static features and also taking into account positions of the decoder for the input.

 Here is the flow of a Pixel Ring. This is an example, let's say, of how it is behaving during a trip.

 We can see on the bottom the time axis. So on the left, we have the printing stage, where the trip hasn't started yet.

 The track hasn't started yet. And during these stages, we train the models online based on the sensor data we received from the previous trip.

 And then we use the route-to-file generator to extract the outcome of the trip from the coordinates. And in that case, the printing model infers that outcome of the trip.

 Then we have the printing time-second interval on the left. Then when the track begins the trip and we are in the in-car trip stage, we use the in-car trip model to provide the results every six time elapsed.

 So for example, if we take an example value of y equals 30 seconds, then the first 30 seconds, the in-car trip model runs inference on the already traveled trip. It has some sensor data now and provides an uncertainty interval, which is then fused with Bayesian fusion to give the uncertainty interval of the printing model.

 Then as the trip goes on, the in-car trip model collects more information from the sensors and the final uncertainty interval. So the interval after Bayesian fusion becomes smaller and smaller.

 So we are more certain about the final energy consumption. The choice of the in-car trip model was a difficult, difficult model.

 This is a diffusion model. And the reason for that is because during the trip, the segmentation of the points in the trip is dynamic.

 So the first 30 seconds, we have an inverter size of the position below the first 30 seconds, and then the decoder is the rest of the trip. And that is a very big horizon.

 Here we can see the results for the time-sync scenario. That was the best performing for all models.

 So we can produce here the results only for the time-sync scenario. And we can see that the temporal fusion transformer out of all the printing models performed the best.

 We have an invalid percentage error of 100%, and this is because we are still evaluating the second error. So small outliers can have a very big effect on the energy consumption of a small segment.

 But this is expected to cancel out when we evaluate on the trip level. And we can also see through the median absolute percentage error, but it is only 10 parts.

 So it is indeed outliers that increase the median absolute percentage error.

 For the evaluation on the trip level, the best performing model was the temporal fusion transformer. And so this is the model we went with in the end for the Pixel Ring.

 We can see the median absolute percentage error of 8.8%. Also, the calibration, the uncertainty interval is 80% on alpha 0.05 and almost 90% on 0.01.

 The other models also do not perform as close, but the temporal fusion transformer performed the best. And lastly, we can see an example of the trip on the top right.

 So on the blue interval, you can see the fused energy interval. So this is the Bayesian fusion of the in-car trip and the printing models together.

 We can see that it shrinks over time. In the beginning, it's smaller than the in-car trip interval, which is expected, since the in-car trip interval at the beginning of the trip has the least information about the trip throughout.

 So it's only a couple of seconds elapsed. And so we reach a point that at this point we make the intersection point where the in-car trip model actually performs better than the fusion of the printing and the in-car trip together.

 And that is because the in-car trip model has experienced almost the entire trip. At this point, though, we have also a decision cutoff.

 Sometimes the intersection point goes even further than the decision cutoff, which means that there is no more decision to be taken by the printing managers. So the value of the printing model of the Pixel Ring is already inhabited.

 There is no more decision that can affect the trip, since we are too close to the decision. On the left, we can see the numbers also.

 The calibration, so the interval shrinks, also is due to more of the actual values as the trip goes on. And the median absolute percentage error also comes very small.

 And in the bottom right, we can also see how the Pixel Ring will behave if we include it only in one model, the in-car trip model. We can see that at the very first seconds of the trip, the uncertainty interval for the final energy consumption will be extremely high.

 And so we need the printing model and the Bayesian fusion controller to control that uncertainty at the earlier stages of the trip.

 For explainability, we can see that positions in the earlier part of the segment, in the encoder sequence, do not affect that much the energy consumption.

 This increases as we go further away in the sequence in the encoder. And on the right, we can see an analysis of improvised fusion.

 This is the driver behavior feature. So there is a difference between the actual speed of the trip and the driver's speed and the planned speed.

 And that means that this is the input of the driver. This is the behavior of the driver.

 And we can see that at earlier stages in the trip, the model originally learns from this feature. This is what is guiding any difference that might be with the planned speed.

 Concluding, we see that the temporal fusion transformer improves the printing scenario. And then the Pixel Ring framework as a whole improves the in-car trip uncertainty.

 And the XLSTM median analysis also show this is again included in the presentation. You can find it in the paper also.

 Elevation, temperature, the speed limit, and trip distance are also important features for the Pixel Ring model. Thank you very much for your time.

 No more questions from the presenter?

 Yes. I'm curious about the XLSTM model. Can you ask me the same question?

 This one or the previous one?

 Yeah, this one.

 How do you calculate the uncertainty? I usually guess it's the mean.

 Usually? Sorry?

 I usually guess it's the mean.

 I mean here.

 This mean?

 Yeah, yeah.

 Is it like why is it like the uncertainty is like?

 Yes. So this is a global calculation. So the light blue and the actually green blue is all the values of many trips and many, yeah, many variations.

 And so this will pose the standard deviation of the mean.

 So is that from the multiple line side in the calculating the uncertainty?

 Yes. And also, I see now that here there is a gray area. It's not much visible here.

 So there is also a zone here, but it's not much visible.

 Thank you. Any other questions?

 So thank you.

 Thank you as well.