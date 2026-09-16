### Speaker 1

Good morning, everyone. I'm Sia, and I'm from the Career Learn, and today I'm happy to introduce our paper, "Walking and Catching Subtitles Between Time Series." So, what is a flow?

 We're interested in making the relationship between time series more interpretable, or more specifically, we want to find— we want to match the similar patterns between time series while still capturing the differences in their starting time or their running speed. For example, this here: we have two washing cycles that start at different times, so we're able to capture this difference.

 And also here, not only the starting time is different, but also the running speed is different, so you can see the sine wave is compressed in the second time series compared to that of the first time series. Those timing differences could be interesting and useful for the downstream tasks, such as clustering and classification, and so on.

 Before we dive into our method, let's see what is this. So, actually, we have already point-to-point matching.

 There is Rigid 1, where the point-to-point alignment only occurs at time points at the same time index. There's also Flexible 1, which means that one time point in one time series could be mapped to multiple time points in the other time series.

 Normally, the Flexible 1 is more popular and more practical because in the real-world examples— for example, here— there are 3 different types of normal heartbeats, but their speeds are different. And the Rigid 1 is not able to capture this, but the Flexible 1 is able to capture this.

 And one of the very popular Flexible point-to-point matching is the Dynamic Time Warping, also called DTW. Before we dive into the DTW, let's first check the point-to-point alignment in the code space.

 So, actually, here, every green line corresponds to a point-to-point matching, and under that alignment there is a code, which is the difference between the value of the aligned time points. And there are multiple possible alignments, so here, on this code space for the grid, each value corresponds to each possible point-to-point alignment.

 And a walking path is a list of the point-to-point alignments. For example, this one corresponds to that.

 The one in pink corresponds to the list of green alignments there, and it connects the two time series from their starting points and also their ending points. And each walking path corresponds to a sub of course.

 And Dynamic Time Warping finds the path that has the least sub of course.

 And like earlier, that is a simple example. The time series only have a few time points, but in real life, normally you have longer time series.

 For example, here, it could be very messy if you still use the point-to-point mapping. So our contribution is to substitute this point-to-point mapping with a subsequent-to-subsequent mapping so that the similar patterns are captured and also the timing difference is captured.

 If we look at this transformation in the code space, it is like this. So the original point-to-point mapping, it is here.

 And our contribution, it is here in the code space. So actually, we are going to approximate this path to a linear piecewise path there.

 Actually, our method is inspired by this Raman-Dobles-Peier algorithm, which tried to simplify a curve to a piecewise linear path while still preserving their geometric shape. And what they do is try to approximate the whole curve with a straight line, and if the approximation is not good enough, then they find the point that is furthest away from a straight line and split the curve on that point and do the simplification attempt again of there.

 But remember that, actually, under every curve there is a code space, and our goal is not to preserve the geometric shape. Instead, we try to preserve the code.

 So we want to minimize the code difference instead of the visual distance between the simplified path and the original path. So when and where to do the split in our method, yes, W is different.

 When to split? So we're interested in the code space or the value difference.

 So we compare the original sum of costs on the original path, or the sentiment, and also the cost in the approximation line. And if their difference is small enough, then we will accept the simplification or the approximation.

 Here, the comparison is controlled by two parameters, the delta real and delta x. The delta real is relatively easy to understand, but the delta x is because sometimes the c, the original cost, might be small due to the overfitting to the noise.

 Then it becomes really strict. So we also have an absolute tolerance here, the delta x, to make the approximation more tolerant.

 And when to split? If we decide to split, the original RDP algorithm, they always find the point that is furthest away from the approximated straight line because they're interested in the spatial distance.

 But like I said, we're interested in the code space. So we are using the point that is furthest away in terms of the value differences.

 So actually, this formula is similar, but one is from the spatial distance and the other is from the value distance. Next, I will show 3 examples of our method.

 The first one is the one I previously showed in the beginning. This is about the washing machine cycles.

 You can see that the original point-to-point mapping here, and here is our subsequent-subsequent mapping. And also, we compare the two paths in the code space.

 You can see that there are— if we zoom in, you can see that some of the red curve, which corresponds to the point-to-point alignment, actually, it is— there are some similarity problems, which is one too many mapping. But we can find that, okay, actually, we can just simplify using the straight line because the gain of the extreme walking is not that much.

 So we can just simplify it using the red segment— sorry, the green segment. And when we talk about those extreme one-to-manual walking, actually, there's also some variants of the dynamic time walking to do with this problem.

 For example, we have the— there is the window constraint, DTW, which only allows the walking paths to go through a region that is close to the diagonal. And also, there is a nice dynamic time walking that adds a penalty in each step of the walking path.

 Both of them, actually, they favor the walking paths to go through the diagonal area, but it also means they're difficult to accommodate the compression or the expansion. And also, while they can avoid the similarity— one-to-many mapping— but they also struggle to distinguish the similarity that is caused by noise, or those that are actually meaningful and should be preserved.

 The next example we will show. For example, in this dataset, there is a pause.

 Like, imagine your machine just shut down and then restart again. So there's a pause in the second time series.

 Such— in this case, actually, extreme walking is not allowed in the window constraint, DTW, or the nice DTW. But the SW is able to capture those alignments.

 And last, we also support the multivariate time series. Here, there is a motion capture dataset.

 You can see that the collecting pen— the user's collecting pen— and apparently, in the second time series, it speeds up the collecting, and we are able to capture it. Yes, we also evaluate the DSW, our method, as a distance compared to the DTW.

 And we have 2 important findings. First, when DSW is viewed as a distance, they correlate highly with the DTW.

 And also, because of this, they have very similar accurate classification accuracy with the runway's neighbor. And due to the time limit, I cannot cover everything here.

 So we also— apart from the splitting, we also have to find— we call it a merging phase. And also, for the evaluation of our method, we also evaluate sensitivity to the parameters in our paper.

 So yeah, you're welcome to come to our poster and also check our paper to explore more. So the takeaway of this presentation is that our method, DSW, is a valuable alternative to the DTW when you want some explainability.

 We provide a simpler visualization, and also we are less sensitive to noise. And also, DSW, instead of DTW, could be used in the downstream tasks, and we have more explanation ability and a small cost of accuracy.

 And also, it is useful for other types of downstream tasks, such as normal detection, or describing the variability within a time series cluster. And we also have another paper that we are going to present in the SDM for that form.

 And lastly, and most importantly, our method is open source, so you're very welcome to scan this QR code and have a check and download our package and to use it, and to share your feedback and help us improve our method. Thank you very much for your time, and welcome to the press conference.

 Any questions for us? Yes, go ahead.

### Speaker 2

 And in the case of the window component, the time series, how do you do the alignment? What do you do to find those variations? Do you consider the integration between the different variables for the time series, or how do you handle those variations?

### Speaker 1

 So in the— you mean in the multivariate time series. So in the multivariate time series, we use the dependence alignment. So it means that there's one— also one path, actually, for all the channels.

 So one single alignment for all the channels.

### Speaker 2

 Okay. So you combine all the measures for one type of test there. All the measures for the same test.

### Speaker 1

 Sorry.

### Speaker 2

 You combine all the variables as a given time set to create just one alignment for all the measures.

### Speaker 1

 Yes.

### Speaker 2

 And they share the same alignment. Okay.

### Speaker 3

 So I just have a quick question.

 Reminder, do you know that DTW is very, very expensive? It's complex.

### Speaker 1

 Yes.

### Speaker 3

 Then in the negative one, we have multiple points. So let's say there are a couple of points we try to optimize them for some classification. So now we're trying to do a few kinds of segments by segment of values.

 And it means that we have kind of a different way to do the classification. Just curious, how would you handle those kinds of classifications, mostly in computational integrity?

### Speaker 2

 So you can actually discuss DTW is already quite expensive.

 So if I understand your question correctly, you mean that DTW is already quite expensive in terms of the storage and also the computing. And our method adds extra computation to it, and how do we handle this?

 So actually, it's not our goal to handle this one because our goal— initial goal— is to provide more interpretable matching between the time series. Yes.

 But our lab, also under the same project, also have a very vast C-based implementation of the DTW and also the pull version of it. And you're also welcome to try that.

### Speaker 3

 And how do you do the— what are the same store comparable efficiency and cost efficiency and—

### Speaker 2

 So can you tell me that there are some C-explorable barriers of execution by sort of different processes?

### Speaker 3

 And maybe explain DTW, how much of it is DSW change.

### Speaker 2

 Ah, yes. So the efficient—

### Speaker 3

 Yeah, I mean, it's expensive for the— why?

### Speaker 2

 Yes. DTW is the capacity is n squared. But our is log-linear.

 Our method is log-linear, the capacity. Yeah.

### Speaker 3

 Okay. Anyone have one more question?

### Speaker 2

 Everyone is hungry. Thank you very much for your time. Thank you very much.
