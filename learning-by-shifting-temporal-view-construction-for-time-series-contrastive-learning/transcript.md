### Speaker 1

Okay, it's 15:57, and we're in Norwegian University of Science and Technology. Today I'm going to be presenting one of our most recent works, which is the new flash sheet paper. Um, fairly for most of the talks today, we've seen that answer is difficult ever.

 One of the major challenges when you are touring data centers is that meaningful data becomes very, very scarce and difficult to obtain. And traditionally, in a supervised learning, which we all know, and which the first speaker, `<speaker>`, has talked about, you need to create this segment where you treat these time-series incidents as high ID.

 So what this entails is that you need data for every single incident that you treat. And we can see that this actually would rely on large labor brackets and requires a tremendous amount of time and resources to have humans undertake this.

 And one thing which is not very clear also is that when you have humans ask for this, not only do you make these models to not generalize nicely, they're limited to what the humans know about this data. So you would not be able to uncover some unknown dynamics from this data.

 So ideally, what we want is to have supervised learning. What we want to do is find some way to learn directly from the data itself, without data whatsoever.

 And the good thing with this is that it's scalable, because on data of this size abundance, it's natural. And also, we want to use this embeddings that we learn from this data completely unsupervised to transfer to some downstream tasks.

 It could be classification, it could be anomaly detection, or forecasting. For this work, most of the focus is on classification and, uh, somewhat clustering.

 Okay, so I will skip this slide. But what this slide is talking about is the previous computer vision techniques.

 What they do is they design some very generic data stacks and try to make sure that models sort of jiggle because you're trying to do reconstruction. But this is problematic because it mostly overfits to the upstream task.

 And that brings us to contrastive learning. So the previous talk, which is about CLR, has talked about contrastive learning, and I would mainly talk about the view construction in contrastive learning.

 Because contrastive learning in itself is a very powerful set of device learning techniques. But one reason it has proven so efficacious and very successful in the future is the ability to design these views.

 And since CLR here has done that quite nicely, where they take a picture and they show that by creating this location, or introducing jitter, or polarization by taking risky and making these views to be very close in the embedding space, by pushing them out with similar views, good learning very rich feature embeddings that inference to so many noise that are natural within an image. However, what we notice is that researchers in time series learning have started to bring these views construction directly into time series, where they

 apply masking and so many things on the data. And, like, you can see here, some of these time series signals are also scaled. One of the problems we've seen here is that they're picking this view construction directly from computer vision.

 They're not thinking about the temporal dynamics of this data. And for computer vision, the pixel, the static pixel, are where the rich information sits.

 But for time series, we argue in this work that we probably need to take some backtrack and look at the temporal dimension. And that's exactly what we did.

 So the, like I said, the consequence of this is that it's unprotected. So when you get a dataset, for example, from human activity, and you get a dataset on sleep, you have to go into this data and look what kind of noise does this data desire.

 So we're back to the problem that we started with. We started with saying that this dataset are very enormous, and we don't want to spend too much time having humans go look into this data.

 So what we need, ideally, is some very intuitive augmentation or less domain assumptions, where we don't go and look into this data. And of course, we want to improve accuracy and generalization.

 Um, this could come as a bonus. We want to also reduce training time, or at least maintain the same training time as the method we're trying to improve upon.

 And most importantly, if you're learning very good feature space or representation or classification, clusters are very important. Because clusters can tell you how your model can perform zero-shot.

 So we did this, and one of the reasons why view construction is not trivial is because we're trying to optimize for competing objectives. So the first thing is, we want these views to have mutual information that we're presenting to the views.

 At the same time, we want the view not to be so far away from the data we're trying to predict. So a view should have enough information to say that this class, for sure, when you give it to a human, that this class is a time series of someone walking.

 And what we've seen is that if you apply perturbation, which is simply just applying jitter and scaling, it actually distorts the view significantly, especially if you're not looking into the data. Because you don't know what scale of jitter is ideal.

 The second thing we've noticed, and subsequently we've used by a very famous set-supervised learning method in time series, is the subsequent base view, which is take a time series, dump some codex or just select some sequence, then apply masking to it. It also actually is a tremendous chunk of the data, and this is not very efficient.

 So what we should also propose is, given a time series instance, and remember I said that mainly what we're working on at this segment level, so this is not looking at this data from a streaming perspective. So we know for sure that a single instance actually preserves an underlying class information.

 So we know that every single signal in this instance actually is telling us about one class. So it has to be probably a signal of someone walking.

 It can't be a signal of someone walking and running at the same time. So there's no change point in this instance.

 So given this instance, can we take this instance, take a particular window, then shift this window a bit and try to see if contrasting this shifted view is sufficient? Surprisingly, we realize that this is actually significantly sufficient.

 One of the major things it does is that it preserves the data maximally. It also reduces the stigmatic features.

 Because right now we have an overlap, say, in this case between the sweeping percent of most of our training. And that actually tells the model that these two windows are actually from the same underlying dynamics.

 And the pathway doesn't overlap. It's actually discriminating that that's what contrastive learning needs.

 And also, it requires minimal domain assumption. We don't need to scale this.

 So we just take any time series instance that we know represents the same underlying dynamics, and we shift it. And the architecture is simple.

 This is the famous architecture pattern in the CCLR paper. When you take this time series, you create these views, you parse them through this set of encoders.

 So the weights are shared between these two encoders. And we use the perception time in this paper.

 And then the feature space, we just project it using a linear or simple NLP to some low-er representation space, and you apply the ntz loss, which is the famous contrastive loss. So we tried this on six large datasets for just the six large datasets, each of them have at least 20 instances each.

 And what we did to actually really prove that this is very generalizable, aside from this large dataset, we also tried it on the UCR and the UE archive. And the results we got are shown on the slide.

 So the first thing to notice here is we tried different range of downstream tasks, ranging from the KNN, which is zero-shot on the large, we tried the clustering performance, which is on the ARI and NMI metrics. We also tried the linear, because one way to know if your representations are very useful is to apply the linear code to this representation space.

 So at a downstream evaluation, you only tune the linear layer where the backbone is frozen. And remarkably, our method, which is just a simple shift, deterministic shift for the large number, is able to outperform every method we compared against in this entire suite of downstream tasks.

 And what's also remarkable is that it's also able to do this faster than most methods. And one thing to note here is to see the difference between our method and the CCLR.

 And why this result is particularly interesting is that CCLR and our method use the same ntz loss. So in other words, by using the same loss, which looks like it has been optimized to be parsed, just by creating some views, our method is able to use less of this time series timestamps compared to CCLR by using the same window and duplicating this twice.

 So that's some speed up we got for free. So given that we've seen this, yes, contrastive learning actually does work, and it works in a very simplistic manner in time series.

 We try to go further, and this is trying to see if most of the things that we thought worked on computer vision, does it scale to time series, or does it also work in time series. And one of the things we tried is to see projection and, sort of, the MLB we talked about in the previous part.

 The argument for it is that if you have this representation space, you need an MLB that will create some of the noise that the model learns when it's overfitting to, say, the upstream tasks. So by removing this MLB and just probing on the representation space directly, does it make sense?

 And indeed, it does make sense. Overall, we see that using a projection layer helps, because the gray structure there is already going into the projection layer to train your model.

 And using the projection layer overall helps as well. Another thing we realized is that, unlike the computer vision case, using the non-linear or linear projection layer doesn't really matter much.

 So you can still just do the simple linear projection. And now this is very significant, because contrastive learning, one of the major reasons we've seen this massive break where people don't use contrastive learning much in the background for computer vision is because the assumption that contrastive learning—lots of assumptions we've actually proven, and including in the same CCLR paper—that it requires tremendous amounts of batch size.

 So increasing batch sizes actually helps this model to learn better discriminative features. So we tried to investigate that for time series.

 And we noticed that batch size, so at least 10,000, helped much. So what we got here is, on the average, the second batch cycle to wait for 256 is helpful, but going further doesn't give you so much information.

 So I think this is an argument for time series that possibly you've not extracted the power of contrastive learning to its maximum potential here. Maybe time series doesn't have so much noise as the image domain when it comes to contrastive learning.

 But finally, we tried to see if this embedding space actually clusters the way we thought. So far we've gotten good on KNN classification, which is zero-shot.

 So we know that there's some notion of cluster. And what really surprised us in this is some MIV property.

 So by just creating this deterministic jittered views, our model is able to not only learn compounds clusters, as you can see on this sheet, it's also able to disentangle some seemingly tight clusters. And you can see that because our model is already measured across everything in order that it's able to clearly separate the gray and the gray parts.

 And one major take-home from this, or something I would like to leave you with as presentation, is that shifted invariants might almost be all the least when we're trying to cluster this view through time series contrastive learning. Thank you.

 If you want to read more about this work, you can go to this page at the info to drop by and have a look.
