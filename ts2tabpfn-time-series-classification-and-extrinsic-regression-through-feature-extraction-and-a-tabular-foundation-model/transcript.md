Ready. So, uh, the first motivation—the first motivation for the paper—is probably the same for many of you: that the time series are becoming more and more difficult in many different applications. There are some examples here because in my lab we're more into health, machine learning for health, so we have some stuff in physiological signals, like monitoring patients, providing some diagnoses, or something from physiological signals like electrocardiograms.

 But we have so many applications. So, in this paper, we're interested in two main tests that are time series classification and experience regression.

 So, classification: we all know there are some examples here. Given a physiological signal, we provide a probable diagnosis for the patient, so it's a discrete label.

 And for experience regression, we provide some scalar value; it's a continuous value. And the same example of the physiological signal: instead of giving a diagnosis, I provide some root cause estimation, body fat percentage estimation, or something like that.

 In this domain, we can represent the algorithms in at least three categories, and I have three here. The first one is deep learning.

 We have some architectures that, if they're trained from scratch, their TTL—their accuracy—for instance, for classification. One example there is the exceptional time in the family, how to do exceptional time, etc.

 We also have some feature-based methods, so we extract features from the time series and then provide them to, sorry, some model. We train the model from scratch and use them as features.

 Some examples are the DRC—I'll talk about this later—and rocket techniques, where we extract features from random kernels that we convolve the time series, then extract features from the result of this convolution. And we also have ensembles in general, mainly many ensembles, like IFOS 2.0 is an example of ensembles of ensembles that are the best.

 These are the best models considering accuracy, but they're really costly. So, our proposal explores some gaps in those fields.

 So, for instance, IFOS 2.0 is the best algorithm for classification, considering benchmarks at least, but it's really, really, really costly. So we need something more efficient.

 Nowadays we have some tabular foundation models, like TAPFM. They're pretty good models, usually they use transformers, and they use also context learning, which means that I don't need to train them from scratch.

 I need some training dataset just for context, and then I can provide labels or whatever to new examples. So, we use all those ideas to bring to here this proposal, which is the S2 TAPFM, that refers to extract features from the time series.

 We use three different sets. CATCH-22 is a suite of reduced suite of features, well-known features, a little bit interpretable, quite of a best to extract.

 We also use TSFRESH, which is very well-known to extract a lot of features from the frequency domain, from autocorrelation, and so on and so forth. And we also use the MOOC rocket, as I said, random kernel convolutions, and then we extract some features, five features for each convolution from the time series.

 So, doing that, we make a feature table, a tabular data from the time series, and then we provide it to TAPFM. We provide the train the test together.

 As I said, it's a new context learning, okay? So, and then we have the result for classification, the result for experience regression.

 We test them on both. So, our experiments: as I said, we used three different suites, CATCH-22, TSFRESH, and MOOC rocket, and we evaluated them separately.

 Also, we used 10334 datasets for classification from UEA user archives, and 55 datasets for experience regression. Those are the algorithms that we had results to compare.

 And for classification, we compared accuracy. For the experience regression, we compared the mean squared root mean squared error.

 We also compared the efficiency of the method, considering runtime and also power consumption, okay? And we did 30% goals for each experiment.

 So, before going into the comparison against the other algorithms, we first tried the different feature sets separately and compared our proposal against our proposal using different feature sets. So, this is a critical difference diagram.

 And for classification, considering CATCH-22, TSFRESH, and MOOC rocket features, the MOOC rocket stands out, okay? So there's statistical difference from the other ones to the other ones.

 And then we promoted MOOC rocket PFM to a new comparison, a new experiment against the other methods. In the paper, we have more detailed results against several other methods, but those were in the top three, okay?

 So, this matrix here, it's saying that IFOS 2.0 here is the best method in average, okay, the best average accuracy in our experiments. However, the MOOC rocket TAPFM is the second one, and there's no statistical difference against it here.

 No statistical difference against IFOS 2.0, okay? And it's better than rocket with statistical difference.

 When we consider the efficiency, we used five datasets with different sizes, okay? So, in the first column here, we have the speed up in total, considering training and test.

 But because we don't have training, it's a pre-trained model, the main difference is in the inference time, okay? But even so, in the total, the speed ups are from 2 to almost 100 times faster than the other methods.

 And if you consider just the inference time, just the test set, when you have longer test sets, a lot of segments to classify, like in this case here, using—sorry, this case here using ECG, it's 200 times faster than IFOS 2.0, okay? If you consider power consumption, we only use around 2% of the power in IFOS 2.0, maybe 50% in smaller datasets.

 If we go to—sorry—if we go to time series experience regression, the results are quite similar. However, the TSFRESH performed better in experience regression for some reason, we don't know, than MOOC rocket.

 So we promoted this version of our proposal. And in this case, we had the best results.

 So we have a recent, kind of recent paper showing the DRC was the best for time series experience regression that we had in some tools. But now we win against the DRC with statistical difference significance.

 And once again, if you look to the efficiency, we consume around 5% to 40% of the energy compared to DRC. We are, in total time, 100, up to 100 times faster.

 If you consider just the inference, 700 times faster than DRC.

 Yeah, but however, we have some limitations. We have a problem with TAPFM that it's really memory-consuming.

 We were using a GPU with 12 gigabytes of VRAM, and we couldn't use every single dataset we had in the benchmarks because of the—when you have a large training set for the context, it exceeds the memory limitations. So we don't have some datasets of the benchmarks here in our paper.

 We decided to remove, like, twice as late variables. So instead of discussing how to deal with that, we just removed it from our experiments.

 But we're already writing a paper on how to avoid those limitations, okay? So, yeah.

 So, in conclusion, with a simple strategy that is extracting features and then using a pre-trained model for tabular data, we achieved a state-of-the-art—at least for benchmark datasets—for classification and experience regression using way less power and time than the other methods that we compared with. So, yeah, this is it.

 Thank you.

 Can you say something about potential data leakage? Because that paper has been examples of that.

 Yeah. He's asking me about the data leakage. But the TAPFM wasn't trained with real datasets, just synthetic datasets.

 So it's pre-trained, but it never sees the datasets that are used in this case. They used millions and millions of synthetic datasets.

 Probably they have some that matches the distributions, but they're not there.

 Okay.

 If you check the performance on the testing time depend on the raw time series, how it goes?

 Exactly. The raw time series, the time series are segmented. The event is there, etc.

 Is there extraction just in raw series?

 Yeah, it's in the raw—ah, I need it. I got it. I tried it.

 It's not good.

 Why?

 I don't know why. That's why the experiments are not good, because we couldn't explain, we couldn't understand it well. There is a paper from both FAISS and TAPFM to insert the raw time series directly, but it's not the TAPFM that we have, the general TAPFM.

 It's a multiplication of that. Probably they had the same problem.

 They tried to put the raw time series directly and then it failed.

 Just to ask a simple question. So MOOC rocket transforms the series into random convolutions that can execute the first one and execute 2,000 features.

 Yes.

 So how is it relevant in this case? Have you tested any approaches to, like, learn a convolutional pair through context learning that we did that?

 Okay. We're doing this right now. He's asking me about the random kernel convolutions.

 Yes, we used the regular MOOC rocket that we had in the EU toolbox. And we just sped it in 5,000 features because it's the limitation for TAPFM, because MOOC rocket has way more features than that.

 And we're not using any customized or trained kernels for now.

 Any follow-up question? Any other thoughts? Yes?

 Okay.

 I have a question.

 I have a question. Do you also look into multiple tabular features as needed?

 Like, complement the features of the—

 Sorry.

 Have you looked into multiple tabular features? Like, do you need to compile features or things like that to enrich your features and to help for understanding?

 Yeah, that's actually a good idea. We didn't try that. Any extracted features use a multiple scoring then to the features on the motifs or something like that?

 Yeah, we didn't try that yet. But that's a good, actually a good idea, and probably that could be used in certain time series not segmented, because we're using the segments, right? So, yeah, probably from the motifs we can extend this for screen time series, long time kind of monitoring, something like that.

 Good idea. Any other questions?

 Sorry to interrupt. This is good for the poster section.

 Okay.

 Thank you.