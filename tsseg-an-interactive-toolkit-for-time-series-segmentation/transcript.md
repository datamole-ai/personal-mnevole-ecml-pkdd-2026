### Speaker 1

Okay. Thank you so much for having me. So, my name is Felicia Lu.

 I'm a PhD student at the University of Wispr and the Faculty of Engineering. I'm happy to present you this work, so TSLE, which is a light toolkit for time-series segmentation.

 So I will start by contextualizing this work and motivate what we need in such a tool, then actually explain what the tool contains, and finally give some insights of what we can actually do with it, what we think is useful, and maybe how it can be useful to you as well. So time-series segmentation consists of actually two subtasks, the first one being change point detection, so I mean that localizing transition indices within the series, and the second one is state detection, which additionally tries to cluster

 all the subsequences induced by change point detection. So we additionally label every subsequence in the series with potentially appearing labels. All of this is done on store resider.

 So you see that these two tasks can be kind of very related, even partially overlapping. However, they have been developed and studied in different contexts, by different communities, and as a result, change point detection and state detection, yeah, so have been studied with two languages as benchmarks, although they serve the same practical problem.

 So this is one of the main things that we wanted to minify, and just to give you some insights, so here is a facsimile of some of the methods, most of the methods that are available for both change point detection in green and state detection in orange. And I just want to emphasize on two things.

 So first, you can see that most of these methods come from, like, green communities, but also the fact that only a few of these are available in mature Python libraries so far, and that they are distributed across several libraries. So first, like, the main libraries existing so far are Virtuo, which is a very mature library that's only focusing on a subset, a subfamily of change point detection algorithms.

 And then we have Ion and SDKind, which are both, like, algorithms, but more general libraries, and that also cover only partially the range of segmentation algorithms. So this is why we wanted to encompass in one toolkit all these methods and try to minify change point and state detection, because it's extra so much because, of course, you can see change point detection as the first step of state detection.

 Additionally, we've shown in previous work that even the methods that we evaluate the evaluation methods that we use to assess the performance of these algorithms can have some limitations, and for this we introduced a new evaluation metrics that's noted for state detection, and these also we wanted to include them in our toolkit. And finally, also data sets are available a bit here and there, and there's no program for partitioners to evaluate the methods, so we also wanted to provide users with a common baseline and common data

 sets to evaluate the methods. So we have both linearity and multiplied series, going from a various range of domains, that is also included in the. So in the end, we have a library that follows the classic SDLR, non-ARM API.

 We have more than 30 segmentation algorithms, including many subfamilies of segmentation algorithms. The metrics that I mentioned also are subject to data sets, and all of this is, of course, on a distributed database, so you can download it.

 And in addition to that, we wanted also to take the advantage of the fact that this task is very visual, so we built also an interactive demo which you can try, and it allows you to upload your own data and use any of the algorithms that we provide with the customized parameters, and provide and run change point detection, state detection, try the metrics, different metrics, and so this allows you to make, like, mini metrics with zero-latency code. And in addition to that, of course, what now

 this library enables is to perform large-scale benchmarks, since we have all these baselines together with a large set of series and evaluation metrics. So we evaluated all the algorithms, or most of the algorithms that we had, under two configurations, with default and custom research set of parameters, and different configured supervision regimes, depending on how we tag them. We provide them with the right number of change points or the right number of states.

 And what happened is that we could identify some good algorithms. However, most of the methods, like, there's no winner across all configurations, data sets, or domains.

 So we still need a variety of methods, which also emphasize the need for such a library. And we also find out that some methods, like, most of the methods, really need parameter tuning, so we also provide guidance on this.

 And, yeah, so just to conclude, we have this library, this interactive demo which you can use, and the large-scale benchmark which is underway, so we'll be happy to provide the results soon. And, yeah, so the next steps will be to further increase the algorithm and data set coverage, and of course share this with you, and we're really happy to provide results for this, and if you want to.

 Superb remarks or want to make some contributions, these are very welcome. Thank you.

### Speaker 2

 Yeah, of course. We deal with multiplied items, so it's basically the universe of the subcase, multiplied item series, so everything works with multiplied items.

### Speaker 3

 So thanks. Thanks for the great job. I'm just.

 This was very interesting for me to hear us. We'll ask more in this area, and that would be kind of a combination of all the available resources that we've been publishing in 2020 and 2021.

 That they release structures and packages, which we know that very well. And I just wanted to ask a question, that if we went beyond that structured package, take a look at the overall.

 And what is added after that structured package is TSLE segmentation. They are in the same scope, but it looks even a bit broader.

 So just wanted to see what we have here for that.

### Speaker 1

 Yeah, right. Thank you for the question. Of course, so Virtuo only deals with change point detection algorithms, and mostly a subfamily of them, so we also have state detection algorithms, so we also have this layer of clustering the subsequences.

 So, yeah.

### Speaker 3

 Meaning that here you have, like, kind of what you mentioned added structured package.

### Speaker 1

 Yes, yes. It's both together. And also in the benchmark, an interesting thing that we show is that there's not only one way to identify states, and that the best and only way to do that is to first perform change point detection and then clustering the induced subsequences, rather than only saying.

### Speaker 3

 Just to ask one quick thing. Is that super concerning for most people, especially in the US? Or is it just working with supervised model or related to the language policies?

### Speaker 1

 Yeah, so some of the methods only work supervisedly, so you need to determine the number of exact change points or the number of exactly states. But a question of a large fraction of them also works in supervisedly, which is the most context that we usually base. And.

### Speaker 3

 Thank you. Thank you.

 We're going to come back to the first presentation.
