### Speaker 1

We are a context process, non-context process. This is what we have to do when we're doing a clean process: we validate it, then we can sell it based on the market. And the second context is the cross-validation, which is what we are more familiar with.

 So the ISO 11607 says that you have to go through some steps to pass the validation procedure. Here you can see the simplified view of it.

 I didn't put the IPSO installation code in the case here because it's not important from the perspective of this board. So first you have to do the process development chase, where you find the variables that you have to control during the whole validation procedure.

 Then, during operational qualification, you have to challenge those process limits, including upper and lower levels. And then during PQ, so performance qualification, you have to demonstrate that your process is safe, and you have to establish quality properties that you check.

 And for ceiling process, CO2 is one of those quality properties. And I have to briefly talk about the process that we are working in.

 The ceiling process is performed inside of the ceiling tube, where you take your packaging paper, preferably multi-layer film, you put it inside of the tube. During the process, the tube closes, the pressure steps and traps the packaging paper and preferably multi-layer film between each surface area and the ceiling seal.

 And after some time, the tube closes and you have your packaged seal. But what happens inside?

 Inside, you exceed pressure and time to volumes reconnect. So they touch each other, they melt, the polymer chain re-concludes, and after some time you have your seal.

 You use not enough heat or pressure, you have insufficient contact or melt. You use too much temperature and pressure, you may cause a squeeze-up or deviation.

 And one thing that is not so helpful: the level machine setting is not the same as the physical condition that you're sitting in the face. So it makes things much more difficult if you want to do this in a multiple volume of seal.

 And when you look at the temperature, you can find a lot of variables that affect your ceiling process. But for this board, we choose the ones that are quite easy to measure for the process that we are working on, and we selected four categories: process, tool, paper, film; and for the process, weld time, ceiling pressure, ceiling process delay, tool opening delay, and the parameters from the HMI, so human, human machine interface.

 Ceiling bar temperature was measured by the thermocouples. PPO sterilization, samples can go through the process, because it's a test data.

 For the tool, hot bar surface area, rest position was measured. And for the paper and film, film thickness, paper thickness were measured.

 The rest was taken from the specification of the board.

### Speaker 2

 Can you check for anything?

 I will go back to a lot of this is incoming from the audience.

### Speaker 1

 Yes.

### Speaker 2

 No problem.

### Speaker 1

 It's easier. Okay, so when we got the data, that was made in 2024, 2025, on the day of production condition from the packaging machines, or let's summarize, we saw that we had 4,500 in the tube in the wheel test results.

 But unfortunately, on the implemented database, we mixed process settings. Sometimes it was high risk that during the validation procedure, if we used the validation procedure, but if we used the single setting, some points that went to the train test were set to go also to the test.

 So with all that destruction, looking at the data points, looking at the data points behind the whole process of the validation, we use the machine learning term, whereas we need a group-by-system cross-validation. So the outer validation procedure mostly tests the data on sealing settings, and the internal one for the tuning of the model.

 We have some ropes because we want the model to train on general data, every single data. All replicates of one setting stay together.

 The outer test was never used for the model selection, but the outer five models received the same outer traits. And in the experimental part, we wanted to ask ourselves three questions.

 First, can the seal strength be predicted? What can seal process settings with this procedure?

 Which variables can be predicted information? Is it treasure boundless?

 And can we retain performance with fewer variables? We used five models.

 Easy tools like GBM, Random Forest, and things like Reception, and the ordinary Risk Squared, Reuseful Metrics, S Squared, and the Mean Absolute Error. And we tested them on a single measurement level, so the raw level, and on the group level, so the mean of the values.

 After that, selection of the best parameter was done. We performed additional out-of-fold treasure, to also would be able to check variability across the splits, and do the replication feature importance as a question.

 Based on the feature ranking from the treasure, we could remove some features, but then we performed correlation with the control before that. And after the features were removed, we retrained each of these models and evaluated the data once in our test.

 And here are the results. As we can see, the boosting models achieved the highest median group level performance.

 XGBoost and IGBM almost the same. The third one, Random Forest, 2026.

 Multi-layer Reception on tabular test data was also good. All the criteria are satisfied, but it's not there.

 And the ordinary Risk Squared, all these measures, all for incidents experienced. What is important is that on the individual set of level, data is low, but the mean absolute error value shows us that it is similar to the distribution where you can see even now data that exists.

 In the outer code treasure, based on values, we see that the prediction is concentrated around the five variables.

 So the weld time, field thickness, sealing pressure, packaging paper thickness, and temperature. So what is important is that not only the HMI panel settings are important, but also some variables connected to the material.

 So the packaging paper thickness and the film thickness. PFI was almost the same, I think, for the top right, and it still changed places.

 And that is not really important, but it's something that we removed.

 And when we removed some features, that is interesting that we found features performance was essentially preserved when we looked at the delta R squared and delta mean absolute error. And we find features looking on this no median loss, but we have three features with a weird degeneration.

 And what's to say from this perspective and that structure? We removed the branches, but you can form pipelines using these branches.

 You can see that you can predict the mean of them if you replicate the measurements you used. Predicting set of individual tests, if you have mean value and you train the data on it, you can miss some important information.

 Because normally you always are interested in your process capability. So knowing that the individual set of mean value more than your mean value is very important when you want to select your parameters.

 And thirdly, is this analysis. You can use it for code review.

 Because normally you go, you test no more procedure will tell you that. You go for screening experiment, rest and service method, when you get your optimal setting.

 Of course, if you don't, then you do the additional repetition of theories. Unfortunately, a lot of times you have to do.

 But with machine learning, the approach we did with the rest and service method, it's quite a fast process.

 And that's it. If you have any questions, please.

### Speaker 3

 And I will start with the question. I might have missed it. So you had a list of explanation characteristics.

 And you also mentioned causality. How much.

### Speaker 1

 You cannot say that you're a causal. This is only for the treasure. Now we can look at the distribution, right?

 These two parameters are always the most important. You cannot create a physical explanation of this process.

 So it's quite easy to say that this is important. But ultimately, you have to compare it experimentally.

 This is the same. So you cannot say that this is causal.

### Speaker 3

 But do you know what is the cause of that? For example, if you use those mean values.

### Speaker 1

 You can make a physical model out of that. Because film thickness, because with weld time, sealing pressure, temperature, it's more or less known what is happening, right?

 Because you close the tube, you put some heat inside. So the film thickness is important because heat has to go through the top layer of paper, right, and go to the film.

 So film thickness also has to be taken into account, but also the packaging paper thickness. So more or less, you can create something.

### Speaker 3

 Have you heard a lot of you saying some sort of physically informed machine learning? That is, because you have the equation with compliance, that's maybe something that is not accurate.

### Speaker 1

 It's in the.

### Speaker 3

 In the project. Okay, good.

 Any questions?

 Thank you.

### Speaker 1

 Thank you.

### Speaker 3

 We expect one presentation to give you a layer. And then they go back for 30 minutes for one more presentation and then fine. Thank you.
