### Speaker 1

All right, uh, hello everyone. I'm `<speaker>`, and I'll be presenting our diagram option, which is a two-stage framework for dynamic pitch generation in agent-assisted sales conversations, and this work has been done by me and my colleagues, `<speaker>` and `<speaker>`, in collaboration with our other teammates. Add into it, uh, some context: Intuit is one of America's largest tax and accounting SaaS companies, and we work with experts who do your taxes for you, who do your accounting for you, and this solution doesn't serve as a

 cost of expense to make them more efficient and, um, more effective at their work. So, starting with the problem. Um, our program contact center handles thousands of successful, uh, or inbound support calls every single year, and by solving the customers' problems, they are encouraged to sell a solution, uh, or a complementary product to their customer.

 This might be connected to the solution; oftentimes you need to upgrade to, like, a higher SKU of the product to solve the issue that you have, and sometimes it's a complementary product which can enhance your experience while using the other capabilities of the product. Um, and on, on analyzing the data, we find that top-performing experts who sell have a high conversion rate; they convert at several times the median rate, and we wanted to analyze why that is.

 And what we found is that they sent when to switch from the support, uh, interaction to the sales part very well. They asked targeted probing questions to understand the customer's pain points, connect that to actual product features to make it relevant to the customer, and also handle objections to the company, like, uh, objections about the price or the target decision maker.

 They have specific scripts which they use, which are very effective at that. And most other agents, like the medium agent, they're skilled at support, but they're not sellers, so they fall short at converting at a high rate.

 So our goal was to identify this honeymoon, this of intuition of when to switch and what to say, which we want to pick up from the top experts and democratize it and, uh, allow all experts to utilize that option. Um, and yeah, some brief statistics about our data.

 This is a proprietary dataset added to it, which we, uh, gathered from successful, uh, converting experts. Um, like, around 4,000 calls in the last, uh, quarter, half a year period, um, on the agent services, and 70 to 80 percent of the conversations are basically that you should not be pitching, because these are cases where they're promoting support activity, greetings, etc., where if you suggest an agent pitch there, that can be great for the customer experience.

 So, yeah, there were three main concerns when we were designing this problem. We had an existing solution built by our team, which were like static scripts, which didn't, which were not, like, customized to the conversation that you're trying to attack to the customer's problem, and hence were not very effective.

 Secondly, just using a general-purpose helper every single term and asking it to predict, uh, should I be pitching at this point. It didn't have an understanding of what made successful experts really good, and we wanted a model to actually ingest that and then hand it to `<speaker>` and utilize that information to improve the performance.

 And finally, uh, the frontier models were the IMD or product-super-hire agencies, and hence we wanted, like, a two-stage solution, like a deeper solution where timing, like when to pitch and what phase of the conversation we are in, is, like, a cheap classification problem. So we trained a simple classifier to identify this, which is trained on successful expert conversations, and the generation is an extensive solution, which is needed to get the quality, and which is also fine-tuned on successful expert pitches.

 So, talking about the phases of the conversation which we've identified from analyzing successful transcripts. So, mainly four phases of the pitch cycle, and one which is the moment where we should not be pitching at this point.

 The first one is the probing question, where you ask targeted questions to understand the customer's pain points. Secondly, soft feature explanations, which were when you connect the product benefits to a customer pain point, like, if they are saying that, "Hi, my, um, I'm, I'm, I'm making like 100 invoices," and you want to connect that to a specific product feature.

 Um, then pricing discussions, like, once the customer is kind of sold on the, on the product, then you want to start discussing more pricing, how can that, um, you know, offer some discounts to improve conversion. And finally, objection handling, if there are specific objections about price or, uh, if they want to be a decision maker of, "I don't really need this," how to handle that, how to say the right thing at the right time.

 Um, so yeah, coming to the solution, starting with the data annotation process. So we look at all the successful converting transcripts, and we want to do a two-stage pass through an LLM to identify the different phases of the conversation and, one, to train the sheet classifier, which, which is identify the phase of the conversation.

 And once we have those phases, we pass it through the LLM again, and at this point, the LLM extracts the what the expert said, and these are the successful pitches which have actually converted for that phase of the conversation. And in the second phase, we also pass in a bunch of product features, which we have aligned on with the business, and also the pricing information, etc., which is, which kind of grounds the LLM.

 I'm not going to say prices or, like, um, often in the training data you see how you can do this because these are historical transcripts. So the LLM needs to be able to figure out, like, these are the updated prices and we should, we should use those instead of the outdated product features and pricing.

 We've got to provide all that context in and create our full training dataset, which we validated with a few experts and, and product, uh, leads, and made sure it's, like, high quality. Once we have the dataset, um, we're going to start training our two models.

 The first one, we did a ton of experiments with different types of SLMs, like BERT, model BERT, etc. We chose model BERT because it has a very high context length, like, around 8 gig of SLM, and that was used to classify both those four phases and, and, and, uh, and the no-pitch class.

 Um, and finally, we had the deep train the LLaMA 3.1, 8 billion instructor, uh, model with SFT using QLoRA, um, which is the generator, which is trained on actually successful expert pitches. So we give it, as context, the customer utterances, product features, pricing information done on product context, and ask it to generate a pitch, which is in my philosophy, what the expert actually said on the call, which is all focused on the clean end, made in a way to, uh, uh, ready to train for it.

 Finally, during inference, during the live call, we run a sliding window of every five utterances. You would call the classifier with the, uh, speaker utterances, give it a ton of context, and based on those utterances, you identify the phase of the conversation we are talking about.

 And if the model, stage one model identifies that this is the time to pitch and the stage of the conversation that we are in, are there other improving questions? Are we in, like, do we have improving answers and do we want to kind of get rid of the pitch explanations, etc., or do we see an objection and we want to handle that.

 Then it goes to the stage two, which is the generator, which is the LLaMA model, and that generates the pitch text, giving all the context and pricing details. And finally, uh, for offline evaluation, we use the GPT-4.1 GRC and analyze, uh, two main metrics, which we align on with the business precision, which measures how closely it measures, uh, the generated pitch, uh, ranks up to what the expert actually said.

 And second is helpfulness, which is, like, a qualitative, uh, metric on how helpful the metric, uh, on how helpful the pitch is, uh, in terms of some qualitative measures which we validate throughout. And we also do a manual evaluation with, uh, a few experts and product folks to, um, uh, accompany the administrative tasks.

 Um, some brief, uh, further context into how the two cases work. So for the stage one, which is the time we classify and phase, uh, phase classifier, we have a sliding window, as I said, of five utterances, which end at the anchor, and at the anchor.

 Provide the last 20 utterances, and also the product prefix, which product you want to predict for. For every single product, we, uh, build, uh, uh, what, what is, what, what are the phases of the conversation that we're in.

 And also we give the previous windows label, because what we found by the analysis of the patterns in expert conversations is that phases usually have a cycle, and you would, like, switch directly from menu or push directly from to, like, a pricing or something like that. There is usually a pattern, so we provide this historical what, what's, what was predicted before as an operating asset signal to keep the model in check and so that it learns these patterns on its own, uh, without, like, us having to

 hard-code any, uh, rules on top of it. And it learns all of these patterns, uh, by itself. And also, class analysis is a real problem because, as I said, 70 to 80 percent of the conversation you will not be pitching.

 So no pitch actually dominates by a lot. So we do downsampling of that in the GRC so that we, uh, keep it in, in line with other, other classes.

 Also, even in the other classes, there's a ton of imbalance which we solve by classes.

 Um, and inside stage two, we have a ton of customer context. We have a system from and doc.

 We give the customer context, the utterances, the type of product, and the other recommendations we're making, the recent end transfer utterances, uh, product features, pricing, and the break phase label. So we condition the generator to only generate a pitch for this, for that specific, um, phase label.

 Um, and yeah, we fine-tune it, uh, to generate the pitch text, uh, directly as, as part of the LLaMA model. And then the annotator results.

 So for the classifier, um, here are some of the metrics and some of the experiments we've done. We're exhausted just for the label, but, uh, essentially what we found is giving more context to all this.

 Okay, yeah. Uh, and yeah, we see pretty good recall numbers across the board.

 We prioritize recall because, uh, that's kind of the metric we were going for, because that's not, not harm in, in just, uh, having to reach out there for the expert. So we prioritize precision as much.

 And here are some metrics, um, on the, the qualitative side where LLaMA 3.1, uh, got one for, one bar at GPT-5 and slightly better than a GPT-5 mini, which is a comparable model in terms of scale, um, compared to a retrieval-based language as, uh, just like retrieving the doc, um, uh, pitch from the historical set from our training set based on the conversation and similarity. And there was a bit of no-pitch evaluations, which, uh, which were really good as well.

 And, uh, so this was a slightly different set of examples, um, which are also in the paper, so I'll just skip through this. Um, yeah, pretty, yeah, um, in the fusion, we have, like, a two-stage pipeline which, uh, was really effective in controlling latency and cost and quality as well.

 And we've done maybe tests for more and more of the metrics compared to this time of the season. Uh, we have still done, uh, some of the backend metrics, but, uh, yeah, uh, this was, this was really successful.

 Uh, what we want to do from now on is, now that we have this live, we want to add some more data to the ORA in the future, more, uh, reference mapping and stuff like that, uh, reference searching, and also learn from clear calls. If you've heard of the ODs and SQL calls, uh, sometimes these clear calls have important signals, uh, which we would like to capture in the future.

 Um, yeah, uh, uh, in future experiments. Thank you so much for your attention.

 Um, it is about the rules. And it sometimes, often, the last minute resource is the future.

 So can you kind of see that spanning the window or making the window larger and larger? Uh, this is something that explains what is called.

 No, I, I don't remember how it is built, but you are at some moment and then you are remembering more and more and more of the past. So we consider this option which is more expensive, but, uh, would allow you to capture some pieces.

 Um, yeah, I mean, there are, there are options I could switch to summarization of the previous context and include that in. Um, latency was a big concern for us, so we wanted the classifier to be really fast because the generator was already taking, like, 11 seconds to improve the generation.

 So yeah, that's something we're using the, the basic metrics to get a good enough response in the future. Final questions?

 No final questions? Okay.

 Thank you.
