### Speaker 1

And I can introduce you to Frith, a new software to analyze, detect, and explain concept drift. Okay, so first, as an introduction: what is concept drift? Concept drift is a change of relationship between the input and output data.

 So how does it influence our models? This causes the models to decay, and, kind of, there's a need to retrain or adapt the model.

 So most of current research focuses on when a drift happens. However, we introduce a way to guess where and how this drift occurs.

 Okay, so we have a three-layer architecture. First, we have the data layer, where we have just the data distribution changes.

 We also have a model layer, where we focus on the model decay and how the model performance drops. And also an explanation layer, where we have some XAI methods adapted to our concept drift.

 Okay, so about the methods used: we have the data layer. There, we have some descriptive statistic, we have some statistical tests, and we have axial clustering.

 In the model layer, we adapted DDM and its extensions. And in the explanation layer, we have decision boundary analysis, we have future importance analysis, and also prototype-based explanations.

 Our takeaway message is that although these methods were already in the literature, we applied them from a new research perspective here. We had some adaptations, we had some creative extensions, in order to give the user a comprehensive view of this concept drift.

 Okay, now about the software. The software is in Python.

 We used some very well-known libraries and packages, like scikit-learn, Pandas, Reburst, Streamlit, Seaborn, and SmartbotLib for visualization. We also used a very well-known system controller, GitHub.

 Okay, so here is the system workflow. So first, we have some data stream.

 We divide it into blocks. Somewhere in this data stream, there might be this concept drift.

 So the user is presented with this struct. We have data layer, we have this model layer, and the explanation layer.

 So the user is able to see, out of each of these perspectives, how the data changes, how the model decays in performance, and why this happened. The role of this user is to connect the dots, not only from one point of view, but also from the other.

 These methods are very useful on their own. However, the main takeaway is that the user has to connect the dots between these layers and get the when, the how, and the where of this concept drift.

 Okay, now about the user interface. So here you can see our dashboard.

 There is a way to choose the dataset, the block size. There you can see the stats menu.

 They are not visible from above, but still. So we have this drift detection tab, we have this XAI methods like decision boundary analysis, future importance analysis, and prototype analysis.

 And also, you can see there, there is this window selection. So if you detect the drift with this DDM, then you can switch to this explanation layer and try to explain why this happened.

 Okay, now onto the importance stuff. We have a case study.

 So here, we will present the hyperplane dataset. This is a very simple two-dimensional dataset.

 However, we perform experiments on more dimensions where our software performed pretty well. So there, you can see this DDM analysis, and you can see that the performance and the error rate dropped significantly.

 There, then the user can move on to this data layer. So here, you can see that while the class distribution didn't change nearly at all, the feature space changed significantly.

 Next, we can see the future importance analysis. So here, you can see that x2, before the drift, wasn't useful at all.

 However, after the drift, when this decision boundary rotated from completely vertical to kind of diagonal, then x2 rose in significance even over x1. So we can see there is some interaction between these layers, and the role of the user is to detect it and connect the dots.

 Okay, onto the summary. So our takeaway is that all these methods are very useful.

 However, they are most powerful when they are used together. Stride proved to be helpful not only for detecting, as previously mentioned in other works, but also explaining and, kind of, giving the user a more comprehensive view of this drift.

 And it is easily expanded with new algorithms, so it's pretty powerful now. However, in the future, we can make it even better.

 So I would like to invite you to our stand. If you feel that this is interesting for you, you can scan the QR code.

 This is our website. And I invite you to visit us at the live session.

 And if you have any questions, I will be very happy to answer them. Thank you.

### Speaker 2

 Thank you for your invitation.

### Speaker 1

 Yes.

### Speaker 2

 Is there any kind of modulation method? How does it affect the size of blocks?

### Speaker 1

 How does it affect, generally? No, we don't have such a tool. Kind of, right now, we experimented with a couple block types.

 For example, I can say, from my perspective, this decision boundary analysis has to have at least, as far as I remember, 500 data samples. So some methods may be not very useful when the block size diminishes.

 That's the only experiment I can give you for now.

### Speaker 2

 Also, when you look at the importability layer, there's false positive. What kind of layers are false positive?

### Speaker 1

 So false positive in terms of the drift detection. Okay, so here, I'd say that this may be the way where these layers interact. So you can see that if a prototype analysis tells you, "Okay, there is a drift here," then you can see that the decision boundary rotates.

 Then you can see that the future importance changes significantly. However, DDM tells you nothing.

 So it tells you that there is no drift. Then you can kind of suspect that there might be something there, right?

 So this is this interaction that I was talking to you about.

### Speaker 2

 But how is it affected by?

### Speaker 1

 Well, DDM is not perfect, as we know. We kind of want to extend it with also APIs. As far as you know, this is kind of the guide to beat right now.

 But as I've mentioned, these are, like, if there was one perfect drift detector, we would just use it, right? So that's why we kind of want to give you this software to have a couple ways to detect this drift and to try to explain it.

 Yes.

### Speaker 2

 What are some of the work you have in the future?

### Speaker 1

 Okay, so if the because these are consecutive. So we are analyzing, like, consecutive or next to each other, basically, blocks. So I guess you could experiment, right?

 Because you can see, "Okay, I want to have this block size, I want to have this amount of blocks," right? So if the block size is too big, you could actually decrease it, and then you could catch the drift there, right?

 Because I guess your question is, what if we set the block size too high, and then the drift is, like, in between the blocks, and then you don't detect it. So then we would have to experiment with those.

### Speaker 2

 Is there a slight way to adjust for example 400, 100, 200, or 100, or maybe you can see the?

### Speaker 1

 Okay, I guess that's also an interesting idea. Yeah. Thank you.

 Yep.

### Speaker 2

 And just a quick question.

 We know that there are a couple of drift detection tools right now that are available, like the NDS one. How do you compare the work with them, and in which aspect you are special, more special than the.

### Speaker 1

 Okay, I don't know the drift detection tool. Maybe Professor `<speaker>` knows this one.

### Speaker 2

 Okay, I will ask a quick question as a follow-up. Also, drift detection is not the main message from the software. We are focusing on explaining risks of the drift.

 This is our key idea. And, of course, we need some drift detectors to know where.

 But the software is more around finding hypotheses and facts. What has changed in the data and model behavior?

 So we are around it, not inside drift detectors.

### Speaker 1

 Yes. I don't know where, but.

### Speaker 3

 I just had a I work on this project, and I had a comment to that question. Because I worked on drift I was responsible for drift detection, and there was a question of what if the blocks are in the right size and the drift doesn't get detected, right? So we have except for DDM, we also have a second drift detection that describes every window.

 So we would see that difference with the prototype methods. If one fails, the other would one would succeed.

### Speaker 1

 So thank you for a very interesting discussion, and I welcome you to visit our stand and continue the discussion. Thank you.

### Speaker 2

 Also, much breath for further discussion this evening. Okay, now we can move to the next presentation.
