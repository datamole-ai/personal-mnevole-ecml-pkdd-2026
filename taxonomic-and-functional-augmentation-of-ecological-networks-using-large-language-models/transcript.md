### Speaker 1

Actually, it's busy all three times slot in Japan, Mark. And Anika Klose, the interim SLA, and Janelle and Ursula are marine biologists, so we've got computer science and some neurology.

 Okay, and marine biologists for progression. And we're investigating through webs.

 Through webs are graphs, weighted graphs, which show how biomass transverses through the ecosystem. So it shows the different relations to the ecosystems.

 Each node represents either a single species or a group of species. A single species such as, let's say, a killer whale, or a group of species which could be, let's say, sea birds, or mammals, or tiger ducker.

 Yeah, so these are the different resolution parts. And we are investigating 230 foot webs which are collected in the so-called picobase.

 That's the ecologists are collecting them, of course, to work. Typically they've got something on average about 35 nodes in this group.

 And the objective that we are putting here is to augment these databases by standardizing the common names of the network. So we know, such as here we've got a herring cage, but the herring is known as herring, sea herring, seal, common herring, sardines, herring.

 It comes under different names. And to facilitate meta-analysis across the two webs, and also to connect with reference sources from different databases, we wanted to standardize it.

 And we use LLMs as a kind of way to standardize from the common name into the scientific name. So we find the location in a taxonomy tree that she arrived, we find the appropriate terms.

 So here we've got an example where the herring is a species, but we can also define it on the level of genus family, order, class, and so on. Notably, not all nodes can be defined up to the species level.

 If you have such a node such as, let's say, mammals, then we've got kingdom animalia, filum cordata, plus mammalia. And that's it.

 The rest is not applicable. That's because this could be different mammals.

 This could be walrus; this could be seals, for instance.

 So we are using four different LLMs and prompted them to imagine they're a marine scientist who has these networks from this datation. And it's a metadata that we gave it, and we will reference it in the source application.

 And we wanted for each node to provide its taxonomy hierarchy in those seven categories, seven branches. To evaluate it, we employed marine biologists to evaluate and manually annotate about one tenth of the dataset.

 So this was our reference. It was also accompanied by the World Register of Marine Species World, so a taxonomy authority database that was supporting our or regularizing our study.

 And we're back up to prompting, or using some samples of those LLMs to compare which prompting strategy turns to be most efficient. And the evaluation methods are concerned, here we've got the error matrix together.

 And we can see that the baseline arrived, and we provided for missing. Provided means that it's given missing.

 It's just like with those mammals, and we cannot get down to the individual species because they are non-unity. So if it's provided, the LLM can either give the same correct answer, it can give different answers, so incorrect, saying it didn't show the different species.

 Or it can be under-specified, so basically the LLM says, "I don't know," yes, and tell me where the should be answer. On the other hand, and this was much more common, when the human said that the rank is missing or it's not uniquely defined, but LLMs still provided it.

 It was seen for overspecification, so it basically helped us make it more detailed information that it should be given. Or it could be truly missing, and then they agree.

 So the basic accuracy is by using some of correct and true missing, so the two LLMs divided by the sum of all. And also we've got the accuracy only for the not-missing LLMs, so it's all in the first row, which is subtle and our secondary outcome measurement.

 So for the overall accuracy, we see that when we compare different models, here we've got direct prompting. In the direct prompting, Gemini works best.

 And we can also see that the left columns we've got models regularized by the main databases, which improves the results a little bit. And samples are, let's say, median.

 However, what's interesting is when we look at the error rate of the chunk sources of errors. In the top column B, you can see that in those medium ranks of longer ranked tasks, we've got errors, but their source is actually that those taxonomies keep evolving and changing, especially on the class and order level.

 For instance, so-called classes becoming an infra-class now. So the reference actually keeps changing.

 Whereas the problem that we had with LLMs was that they tended to overspecify or hallucinate answers where they should stop and say, "I didn't know." And Gemini was the best because it was less prompt to overspecify.

 If we counted the no-missing accuracy, so the cases when we removed all of those, we used to write it from this accuracy, those overspecified cases, or tending to speed to overspecification. We can see that the results become much better, and then even the samples actually improve upon them.

 The one outlier, so two very poor results of the model was actually their misformatting of the curve, rather than its inability to provide results. Other than that, the different problems became similar.

 Yes, we used en-samples because we wanted to have to be flexible architectures so that we can switch and change to other models with the right methods. However, how can we get into the second better results from the proper model?

 So we run a separate prompt, and that's more than a separate prompt, in which we ask only for all of those nodes to provide which level is most appropriate for this. And then we drop the previous results to this level.

 So here we could say that for mammalia, only the class level is appropriate. So then we drop the rest of the results, meaning the LLM overspecified, and it says that those mammals must be killer whales and not euthanas.

 At least those alone.

 And we wanted to do more about this, apart from the taxonomy. Actually, we wanted to see whether the LLMs are capable of generating heavier data, which will augment the data with the nodes with other information, such as lifespan, buoyancy, bone design, feeding strategies, skin covering.

 You can see these are normal features which are quite detailed. And actually, the LLMs are capable of creating such tables, which is nice.

 Their modification and validation, especially from the ecological perspective, remains a challenge. So this will be done in a follow-up study for more, let's say, ecologically related sentences.

 And basically it needs more structure from the core. But actually, this was our initial motivation.

 We just wanted to do some learning on this graph and to learn or train some nice embeddings to control features. So that's possible.

 And what we can see here, especially in the top row, we can see that in some prediction tasks, actually addition of those additional features actually helps. Includes gives a few more presentation weeks.

 So there is information content in it for you. So to summarize, here I wanted to show that those LLMs are promising tools for obtaining and standardizing taxonomy, which is useful for basically working with meta-analysis and comparing with other reference data sources.

 However, they tend to overspecify the results, yes, which we can counter by asking a separate prompt to basically asking them to where to stop and then drop the previous results. And what's the most promising is that we can also extract information about functional features, yes.

 But this will require much more in-particular structure and much more validation. So we started from taxonomy as the taxonomy is the most.

 It's well established. We've got the tree of life.

 There is a unique world behind us where there's more functional features, those functions and the application that depend a little bit on perspective, or we can say depend on the specific. Thank you for your question.

### Speaker 2

 Thank you so much. I hope that we both were really useful in time. Other questions?

 So how do you think, how well does this approach apply to all kinds of knowledge graphs that are quite so structured as taxonomies?

### Speaker 1

 Well, here what's useful is that if you look for example Wikipedia for pages about different species, yes, they basically since the taxonomies can be right for 150 years, and they are so well standardized and established that this knowledge is already incorporated into the kind of into the base of LLMs, which basically have the whole internet kind of compressed. Or they can even do that search if you fill out the ground with reference data. So here this problem is somewhat easier, but I think this should also work

 in other cases. However, the question about validation—

### Speaker 2

 I'm kind of wondering, for example, about medical knowledge graphs and then organizing the LLM knowledge of those.

### Speaker 1

 Well, medical knowledge, I'm afraid that the first perception of medical would be that medical or physical doctors require. Much that they qualify standards of the quality of data. So here, if we even misrepresented some snails as some kind of other animals as a kind of, let's say, crab, then it wouldn't be too much of a problem would be done, yes.

 Whereas for medical knowledge, this would be much more I think they have much higher standards. So it's common when we call a computer scientist laboratory with medical doctors is that we are not only seeking computer scientists, we are happy that it works here and there, yes.

 And they are very interested in a much more well-established knowledge, yes. So hypothesis, risk-taking, and testing, yes.

 They want to check whether it will work for each and every patient rather than only that it works here and there. So I think that's the problem, that over-the-counter validation would have to be much more thorough and effective.

### Speaker 2

 Other questions?

 Would be so good, like to thank our focus.
