### Speaker 1

So, hello everyone. Uh, so actually, Gonzalo Mendez couldn't— couldn't be here, so I will give you the presentation instead. My name is Luis Galardaga, and this is, uh, RocketMan— so it's a student work with Gonzalo Mendez from the Polytechnic University of Valencia, Spain.

 He came from SPOLE, Escuela Superior Politécnica del Litoral in Guayaquil, Ecuador, and all the other from England. Alright, so this is about time-series specification, which is a very, uh, it's a very important task.

 So we know that time-series is just a time-indexed sequence of measurements, and I'm going to classify or categorize such sequences of observation as, uh, codefined specification in many settings in the team where I work. Um, so we have a project where we are trying to predict the cognitive load of a particular task, so a primary task, which you'll be seeing in the left.

 Um, and, uh, we use a signal, so the traces that the participants draw while doing the task. And we use those traces, uh, to distinguish whether the task imposes a high cognitive load on the participant.

 Um, we have also other projects where we have, uh, time-series of the temperature of some of the paddles to try to predict postures. So, uh, and I'm sure that you already have probably many other applications.

 So, being such an important, uh, useful task, there is, uh, really a vast menu of, uh, of methods to do time-series specification, going from distant-based methods to shape-based that are more transparent. But there are also other methods that are more, more black box, like deep learning.

 Um, so some of the methods are methods based on convolutional features, which are the ones that we care about in this presentation, in particular Rocket. Um, and so even though they are not the most, uh, probably the most powerful methods nowadays, they are still very relevant because they are fast, and they can be used also, they are proved to be quite useful in other methods.

 So, um, regarding the Rocket family of methods, the principle is very simple. So, um, we will extract, that is, we will map our time-series to a latest base, and those latest bases are based on features, and those features are obtained by just applying convolutional mass on the original series.

 And a convolution is just, so a mass that is centered on an observation in my time-series, I do a selector on a paddle, this will give me a result. And if I do this on, uh, centered on all the observations of my time-series, I obtain a convolved series.

 And this convolved series is then pooled. So I have a pooling operation, uh, that can be max pooling or PPV pooling, that is something in Rocket, which, uh, just applies a threshold that tells me what is the proportion of values that are above a particular threshold.

 If I do this for many masses, uh, usually drawn randomly, uh, with many dilation schemes and different padding, uh, settings, so I can actually obtain a large number of these features, which then I can use. So there are these are very diverse features that then I can use to, uh, to a classifier, and the classifier does the design, which those features are discriminative for the, uh, classification task I want to, uh, uh, carry out.

 There are many derivatives of Rocket, like in Rocket in particular, we are using in Rocket because it restrains the space of, uh, bundle mass that are used. And, uh, has been shown to be way faster.

 So the problem with Rocket is that even though it's quite powerful, it's a black box. So because the classifier's response depends on many non-interpretable signals.

 Um, so we asked ourselves, so for this application that we had, we needed to look inside, uh, the black box. And so we said, what if we look really inside the black box?

 So that's, that's the motivation of Rocket next. Um, so we started the analysis from the observation that actually the classifier itself doesn't know anything about the transformation process.

 So the classifier sees the features that were computed with minimal effort. Those features are non-interpretable, unfortunately.

 So, but we know that those features depend on the time-series observation. So they are computed using, uh, convolutional pooling.

 So we said, what if we identify the features that are important by the, uh, in the classification, and then we, we back-propagate the importance of those features to the, uh, observations in the time-series so that we can see what the, what those features are computing. So we can do this in several ways.

 So if we, uh, if my classifier is a white box, then I can know which are the important features. If it's a black box, I can always use constant explainability to get a feature attribution map and just back-propagate the features that are important.

 And so that's what we do. So we, we distinguish which are the important features that are in the classification process, and then we back-propagate those through the, uh, important transformation function to obtain a set of, of heat maps.

 But this heat map can be very, uh, very precise. I can do just back-propagation on one particular feature so that I can see what this feature is computing for in my time-series.

 So with Rocket next, we can extend that, that process. So we have, uh, some panels that allow me to know which are the most important features to define the classifier.

 The thresholds that were used in the pooling process, the dilation schemes of, of the shape of the mass that, uh, that it's using to do the convolution, and some other statistics about, uh, frequencies and thresholds in the features. So, uh, we can go further.

 So you can actually pick a feature. For example, here is this particular feature, which is, which here is depicted, uh, this way.

 So this is the mass that I wanted to compute, the convolution, and we can see actually how this, this mass is actually, uh, applied to the time-series. We can see the convolutional response.

 So the, what we obtained by doing the convolution, we can see the threshold also that was used for this particular feature. And, uh, we can see here the heat map, uh, that tells me which are the features that are important for a particular task.

 So here we are in local explainability, so we, we can see this for a particular instance and a particular classifier. Alright, um, so if you are interested in looking inside the Rocket or even having a ride in the Rocket, so just please come to my demo.

 So I will be thrilled to, uh, to show it to you. And so here you have also a link to the walkthrough video and, of course, the tour is included, um, online.

 But I have a version, uh, with some improvements in my computer, so you can come and look. I'll be, I'll be very happy.

 Thank you very much.

 No, we, we classify the whole series, yes.

### Speaker 2

 Yes. And another question is, what is the meaning of the objects that every clean and other interrupt are like sharp or blind or?

### Speaker 1

 Well, so, uh, the thing is that, um, as I said here, our tool is, uh, it's modular in the sense that it doesn't really care of the important scores that you, you, you obtain here. Yeah. So that means that technically you, you could use sharp, blind, clear, so you apply sharp to the classifier to get an importance ranking of those features.

 And then once you, you identify the important features, you can decide to split those. Yeah, but this could be also if you, if you model it as a linear model, you can just run by, by this one.

 So we can do sharp, but it's more like a modular tool. Yeah.

 So I saw another question.

### Speaker 2

 Thank you very much for your presentation. I'm sorry to interrupt. You basically now spoke to the sample-wise language.

### Speaker 1

 Yes.

### Speaker 2

 Can you find, can you find, uh, for instance, there is any convolution that is basically, can you find consistent with something which are much more important than the others? Or maybe that some others are actually not very meaningful.

### Speaker 1

 Yeah. Well, we, we haven't done to be honest, I haven't done a quantitative analysis. We are working on that, and that's actually what, what, what actually motivated us.

 We have done more qualitative analysis. Like, we have taken for different instances which are the features that are more important.

 And, but even if you look at the mass, this doesn't tell you much. Actually, you see what the mass is computing when you apply the convolution, and you see the activation patterns.

 And so there are some convolutions that are, for example, there are convolutions that are PPV detectors, for example, or valley detectors, or, but something that we will see in the demo is that, um, so sharp and blind methods like this, they, they compute the distribution values with respect to a reference, uh, value. So you have to see how the reference value behaves in that particular observation to understand the pattern.

 So we haven't done a quantitative analysis, but you can, by using the tool, already surface a few patterns, like PPV detectors, valley detectors. Um, also there are, there is dilation.

 So you can see, you can see also, like, some patterns related to dilation.

### Speaker 2

 Thanks again.

### Speaker 3

 One more question. You're on, uh, you're looking at, uh, features one by one. Is it like, like, instantly?

 And, and will, will it use some form of.

### Speaker 1

 Yeah. So that's, that's a really good question. So, um, uh, yeah, so far with the tool, well, with the tool, actually you have the, the power to back-propagate either one, uh, feature or a group of features.

 For example, you can back-propagate the top 10. And so that's powerful because then you can see, um, you can see patterns that go beyond, like, you know, scatter points.

 Um, so then the next stage of this research is actually to see how to extract interpretable features from that. And so we are actually working on, on that.

 So once we've identified the group of features, we can, for example, extract shapes. But yeah, but with the tool, you can, you can actually, uh, you can be as finely as you want.

### Speaker 2

 Thanks again.

### Speaker 1

 So we can move to the next presentation, streaming inside the Wispr explanation slide. A pilot on toolkits for concept drift, detection, and explanation.

### Speaker 2

 Speaker.

### Speaker 4

 What's the Wispr FLW specifically? So what do you want to get out of the demo?

 Because I think the Wispr model is.

 Okay. So.
