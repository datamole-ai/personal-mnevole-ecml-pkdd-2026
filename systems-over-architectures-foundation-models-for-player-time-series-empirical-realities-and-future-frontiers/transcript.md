### Speaker 1

I'm very excited to be here for a couple of reasons. One is that I've talked to three of my supervisors here, so thank you. So, one of the reasons is that the title of the workshop actually is saying that we're closing this gap between industrial and real-world setting and qualitative research, and how we can actually apply qualitative research into business.

 So I'm really excited to be here for this meeting. And, of course, as you know, we've had a few collaborations over the years, and I'm so curious to hear yours, so thank you for coming today.

 So, my team works on different areas: we work on presentation learning, we work to understand players, we also work on reinforcement learning for understanding game place. But what I want to particularly talk about today is foundational models for players, looking at time series representation, looking at empirical realities, and somehow it's also a question of future frontiers.

 And I don't want to go from the typical way of talking about, you know, LLMs, and then, you know, going through, like, how to scale and so on. But rather, I want to talk more about, you know, our data, our challenges, and actually spending more time on what didn't work in our data.

 A little bit about King. So, King is a gaming company, mobile gaming company.

 It's part of Xbox at the moment. And Challenger Saga is the— it does have a lot of games, but Challenger Saga is the most well-known franchise of Challenger.

 There are also, like, you know, it's part of a large family of games. And if I want to give you a sense of this matching puzzle games, for instance, like, you know, the snapshot of Challenger Saga.

 So basically, it's a thing to play games that everyone can play, and it's a user who progresses through a series of levels. And, like, you know, it's just a lot of levels to progress through.

 Levels are short, are designed in a way that, like, in a match, three or more hands of the same color, for example, go vertically, the hands disappear from the board, and then randomly hands of different colors will drop down from the top. There are also some other elements, like blockers, that are basically challenging.

 And then there are also special hands that they have extra colors. And you need to succeed within a given number of moves, and each level has a certain objective.

 You need to collect something, or reach a certain score, or, like, you know, remove a crossword, things like that, from the levels. Small board, quite challenging, I have to say.

 So, specific numbers and the scale that we're talking about, since you already mentioned about this. We have about 200 million active users, monthly active users.

 If you look at the history of Challenger Saga, we have over 5 million installs. And if you look at, again, Challenger Saga alone, I talked about this in a partition over levels, we have over 20,000 levels only in Challenger Saga.

 The other levels that the games didn't progress, but we spend a lot of space, a lot of attention. So, there are players that have been playing over 10 years.

 There are players that just started, and, like, you know, they want to have a game experience for 10 years.

 What is important here also to highlight is that this experience, it's an interaction of the player, it's sequential, it's, like, it can be high frequency, it does have bursting moments, it's emotional, and it's full of feedback.

 So, what's the key here is that, like, you know, we have this AI-generated image that is, like, about to reflect, you know, people's backgrounds, like, you know, in different moments of their life, from the different expectations, and they have different interests, they have different skills, and they come at play, but all they want is to have an exciting challenge.

 So, again, the journey of my team and interest is that it's trying to help the product to think about how to deliver the right experience at the right time to the right player. Okay, let's dive into one player in one of our games.

 So, how do we see it when we are looking at data? So, this is the trajectory of, like, you know, the generative trajectory of Wispr Flow.

 So, player starts the app, starts a level, plays the level, retries, uses some game boosters, progresses, pauses, comes back, plays again, joins a live event. It could be, like, you know, a social conference that you complete with someone else, or, like, you know, someone's campaign that you have in the game.

 Maybe makes a purchase, and so on. So, interestingly enough, right, that's definitely.

 But what's behind is actually an experience we can use, like, you know, intent, frustrations, learnings of the game, like, you know, new game objective, habits, motivations, and social context, right? And we would like, in order to be able to inform our products, we would like to be able to capture not just the logs of events, but actually the experience.

 So, how does it connect to foundational models? So, the idea of, like, we have a lot of different use cases in the company.

 We want to be able to, as a model, lifetime value, like, the purchases of the users. We want to see what options we're showing our pay-to-machines, predict end-game purchases, prediction of, like, change and retentions, looking at, like, how to do the difficulty matching of social context, or, like, you know, how to do dynamic segmentations.

 And what we have is, like, you know, sessions of players coming and playing, and meet and come back, game rounds, progressions, the difficulty of, like, you know, different levels that they are progressing through, boosters and resources, and purchases and events, right? So, what we would like to do is to take those data of, like, players in one game and build a player representation that would be a backbone, a unified backbone, in order to fit this in, solving multiple use cases, right?

 Instead of using hand-crafted features. So, imagine that there are already multiple use cases, there are a lot of hand-crafted features, nice features engineering, nice features engineering, but then, like, you have a, first of all, for each use case, there are so many of them.

 And then second is that it's not consistent. So, in one team, maybe they define the features in one way, and in another team, they define it differently.

 And they come with a high engineering cost, right? And we want to move away from that and have this one and reach their representation.

 And, like, you know, how a foundational model could naturally fit into a good use representation. So, again, going back, we get the telemetry and the logs of players, and what we want to be able to have for games to understand players' context.

 Okay, so, giving you, like, you know, a summary of this slide that, like, you know, talked already.

 So, we started exploring different ways of abstractions for data, and then building representations on top of those abstractions. We start from raw events, we also have sessions, and we can put some structures around those, and, like, you know, on top of the abstractions.

 And then we build a player representation, and we build a player experience around that. In the top, I will tell you about different abstractions and different ways that we have tried for, like, a player representation and what it does.

 So, why foundational models? Because it gives us four promises.

 One is universality, that I mentioned earlier. And then second is, like, going beyond features, that I, you know, touched on.

 We can also think of, like, you know, time to building, time to production. Can become, like, it takes a lot of time to build the right, get the right foundational model.

 But if you have this one shared representation, it's much cheaper and faster to build and, like, you know, build multiple use cases. And then, hopefully, we think also that, like, it can help us to have a better lens on behavioral structure of humans, and with that, hopefully, we can get, like, you know, better interpretability of profiles of our players.

 And another thing that I'd like to highlight is the generation side. So, if you have this representation, like, you know, we should be able to also roll out a generative experience of players and be able to put this through what if scenarios to assess before releasing a product potential impacts.

 So, actionable simulations, rather than, like, you know, just having some insights and not being able to action those insights.

 So, we have been looking at, like, some foundational models, and what we see is that we get some interpretable structures, and I will show you in the coming slides. But we also see that, like, when we talk about understanding players, the problem is actually not, like, what's the best game method, but it's also, like, you know, it's resides in the representation that we have.

 And then there are four challenges that I would like to address here: robustness, stability, validation, and actionability, right? So, very often, like, the question is that, like, you know, if, for instance, like, robustness is about, like, you know, if you get the data, can you get a robust generation, right?

 And then, like, stability is about how performance drifts over time, not just only on the end of the game. And then the validation.

 Like, at the moment, like, when you get, like, you know, some kind of representations of players there, like, you know, you don't have any data power, you cannot validate that it's actually meaningful and, like, useful. And finally, like, you know, when you have statements, you want to be able to take an action, and that's where generations particularly come into play as a motivation for us.

 We took these four challenges as inspiration, but also as a setup for us to evaluate different approaches.

 So, now from the lens of data, what is a player? We took different directions, and I'm going to walk you through different directions and our learnings through those directions.

 So, the first direction that we took was to collect the data from the players, and, like, you know, look at the handler representation of players. So, the question that here we had was that, like, you know, conventionally, everyone is saying that variant decision trees are, like, a go-to and, like, they work well across different sites of data and different types of data.

 So, like, let's go for a base use. But then transformer, like, you know, has come out on all different domains very well, but was not, like, used as well on handler.

 And actually, in collaboration with `<speaker>` and `<speaker>`, we looked at, we looked at different scales of data and to see what's, like, in which scenario does actually transformers could be a better model.

 And what we saw is that, like, when we scaled over 100k samples, actually, transformers started showing better performance on their base use. And most of the datasets that, like, the analysis were presented previously, they were on a smaller scale.

 We also learned through analysis of different, like, features and tasks, we learned that, when it comes to complex relationships between features, then transformers are particularly better in capturing those.

 This study was done in 2024, and I want to revisit that study here. Like, we're getting to 2026.

 The question is that, do we still have, like, you know, the same answer? This is a benchmark published by Google Research, looking at different foundational models and hardware data, and they particularly have a benchmark where they are looking at a mix of attention on roles and problems, and looking at small data, large data.

 There are two particular things about this. One is application of in-context learning, which makes it possible to work well on smaller scale data.

 And the second is using synthetic data generation in order to build large training data to build this, like, you know, large foundational models. And what it can help is that, like, you know, you get high performance across different applications.

 So, like, in our learnings that I will show off later, is that we see that a lot of, like, you know, analysis that is still done in private systems here don't necessarily map into our domain, but it's naturally the nuisance that they create. So, I'm going to talk about how to expose this presentation.

 First, like, looking at the learnings and, like, you see, like, you know, what, like, you know, moving forward, not only, like, the question, but actually even, like, you know, we need to address why and why foundational models. Second is, this model is quite expensive, so, and it's very slow.

 So, if you have a set where you can't deploy a complex model, you can't have, like, you know, high latencies, or you can't have a complex model, or, like, you know, you have an extension that you can't actually. You can't check in for the difference, then it's, you know, decisions will not work, and, like, you know, decision trees are still, like, quite useful, but you will not reuse any smaller handler model, handler foundational model or other foundational models with some, like, you know, adjustments to your setup.

 Okay, so, another integration that we looked at were graphs, like, we were talking about, like, you know, players, interacting with game elements, getting rewards, like, you know, collecting boosters, playing with each other. So, it's nice to think about graphs.

 So, we started looking at the specificity of graphs. We looked at continuous time dynamic graphs, and this was part of an internship that was conducted in the team.

 And the learning where you realize that this is actually probably not suitable for applications for two reasons. One is that it's complex to capture long-range relationships and processes, or the different, like, you know, long-range or time steps.

 And then we got the other one is, like, you know, like, it's, it's in terms of storage, it's quite complex to, like, you're looking at a time scale and this dynamic environment to store these relationships and, like, you know, recall them in relationships at a scale.

 So, the third integration that we took was treating the loss of players as language. So, here, this is very small, but you see, like, adjacent line that captures, like, you know, the name of an event and values for an event, and there are a large block of events.

 We extract relevant events for the tasks that we're analyzing. We are dropping uninformative fields, and we do some value-type conversions, because this is unstructured data, like, you know, a lot of different, different, different value types.

 And then we are also looking by players and sessions to be able to run this through our model to get representation per player. And then we join this plat and this as a text and feed it into a model here.

 We wanted to use models that they are particularly good with long context, so we started looking at long format. And so, we are using mass, not, I mean, long format is used with mass language modeling, and we are fine-tuning for the tasks that we're trying to solve.

 The good thing is that we don't need the label data, so we can use a lot of, like, you know, logs from players. Context is a problem of being able to direct context.

 But also, what I want to highlight as a challenge is, like, you know, vocabulary and tokenization. One challenge that, like, when you get, like, you know, like, a wide variety, wide variety of different types, but also when you get, like, you end up having some sparse matrix of information on players.

 So, this is what we see here. If we use this model and extract the latent representation and plot the t-SNE on that, this is a small scale, so around 1 million data points.

 So, like, you know, it was, like, more for, like, studying to figure out, like, you know, can we identify any patterns. We saw, okay, there are some separations, but what does this mean?

 So, we started, like, you know, looking at some important signals and features and giving some fingerprints for each of these clusters. And from these fingerprints and mapping it to, like, user research study that was done in the company, we see, like, you know, some descriptive clusters.

 There are eight clusters, like, you know, one of them, so you can see some, we came up with some nice patterns. Like, competitive devoted, casually devoted, persistent devoted, leaning casual, economy aware, leaning casual, persistent casual, and persistent collective.

 And, like, you know, some patterns that could be, like, you know, interesting and informative for product development. We don't know what to do with that, but, like, you know, we could show that actually we can, like, you know, get some interesting insights out of this data and experience.

 So, when we were analyzing this, what we saw is that, like, you know, in our work, we see, like, increase the size of the model, it learns better, and it learns something. But we wanted to also look further, because we saw that it's, like, you know, it's struggling about, like, you know, tokenization and, like, it's a bit glossy, so, like, how we can improve it.

 So, the third approach, as, like, an extension of this approach, is that we started building a structured tokenization. And I actually see, I was looking at, like, you know, the works in 2025 and 2026, and I see some of the deep companies actually are also picking up, working further on, you know, tokenizations for the context of, like, unstructured data and for domain adaptations to work on structured tokenization.

 And here, basically, what we did is that we used categorical numerical data separately. So, we mixed embeddings, we retained the numerical values, and we encoded missing values intentionally at the different destinations.

 And then we also have, like, you know, some weights that learn to make this, like, you know, more condensed tokenization. And then we treat this inference as well.

 In our analysis, we saw that, like, you know, this is Trakformer, if you're familiar, I don't know if you like GD and MLP. We see that, like, you know, as you increase the capacity of the model, it performs better, but not necessarily always.

 So, like, you know, we started, like, you saw a pattern of increase, and then, like, at some point, it was causing an increase. So, our learning and takeaway looking at the data was that the capacity alone is not the only, it's not the deciding factor.

 I also forgot to say that here we come up with, like, you know, player engagement tasks to predict, like, you know, the number of sessions that, like, you know, within the upcoming, like, a future window for a player. And, like, you know, we also, like, we need a processing so we can, like, post-final classification and multi-task classifications.

 So, the fourth direction, this flattening of textual data was glossy and, like, you know, didn't capture all the information that we had about players. And we thought that we were talking about temporal events of players and we have this sequence, how about we translate that to time series.

 So, what we started looking at, we took the abstraction of data as multiple time series and then established multiple time series as input to our model. So, we started exploring time series foundational models.

 So, here we are looking at two tasks, purchase versus not purchasing, of a player within the next 30 days. And we're also looking at engagement.

 So, here we are looking at, for instance, play time or, like, duration and length of a session in future for players. To look at the performance drift of the model, we are also looking at holdout data to make it a lot more temporal holdout to see how the models are performing.

 Interestingly, we saw in our analysis that transformers are, like, you know, holding better when you're looking at, like, temporal holdouts. We also saw that, like, if we are using tools as HTSC, which was, like, it's a transformer-based, but it's end-to-end supervision that we worked on, we see that, like, it performs better than XGBoost and Cognit.

 The reason that we have these two were because we have these two, like, you know, as, like, you know, production systems that we can compare with. But when we're looking at the purely foundational models moment, you can see that the performance transfers to the.

 And then the transformers work.

 I also want to show you, like, we spent quite a, like, a good amount of time on this because we started with this use case of looking at lifetime value of players. And we saw that, like, foundational models, when we do, like, you know, data encoding on top of them, even if they are trained on a different domain, they're actually playing, like, performing quite well compared to graphic use case trees.

 And, like, you know, we're quite excited, so we continue to invest in, we look at, like, multiple use cases. Long story short, it didn't hold in all the use cases.

 So, here, like, you know, there are some where, like, they were performing similarly, but here I'm just referencing one that, like, it didn't perform well. And this is the performance marketing case.

 In performance marketing, you have a very short window of observation of your players where you're talking about, you know, one or two days not playing against someone. And you don't have enough signal from the players to have, like, you know, rich context to be able to make a good prediction.

 One would argue that, like, the models that, like, have FM should work with, like, you know, with, like, in-context learning quite well, which we haven't tried yet. But we saw that, like, you know, moving acronyms, which are, like, the top performing time series foundational model didn't hold well here.

 So, our takeaway was that we should have looked at, like, you know, domain properly, we should have looked at properly what we can use cases for.

 Okay. So, now I'm like, we started diving into why foundational, more time series foundational model didn't work well for us.

 So, I want to go back on the data and talk about, like, experience of the player, right? So, we have, like, burstiness behaviors, so data is sparse and bursty.

 We have, like, here indirectly sample events. The data is non-stationary and comes in multiple scales.

 Like, you have sessions of players, but you also have, like, you know, lower high-resolution events that come to play. And then they are shaped by, like, interventions in the game that we are offering them, and they're heavily skewed, right?

 So, and most of the public benchmarks, they actually don't offer you this type of properties in their model here. So, it's, like, you know, very much an abstraction project, like, you know, what can we do?

 And, like, only examples data or, like, benchmarks from mapping it to our research in our own groups. So, we dive into what are the differences, right?

 So, one of the first things that I want to show here is, this is data that we have from our players. And if we take the time series and assign them to the frequency, what we see is that, for instance, if we look at moment and what datasets are used for moving moments, we see that these data sets that moment is trained on, they're actually kind of configuratory events, right?

 And in our work, what we did was that we tried to synthesize based on this hypothesis that maybe we can see this is what happens. So, we tried to synthesize some data and, like, you know, look at how the model is actually working, moment model is working on this type of data.

 And what we see actually is, like, confirms that if, like, the frequency actually matters of the training data on the tasks that you're trying to fine-tune on.

 Another thing that we looked at was actually pooling.

 So, here, this is on a, I don't recall, but at least on a GPT model, where you are a GPT-type model, where you are, like, what we are looking at is different type of tasks and different types of pooling. And our study showed that, like, actually the use of pooling matters on the performance of the tasks as tasks depend on them.

 So, it's important to be more rigorous on, like, you know, what pooling are you actually applying when you're doing, like, this fine-tuning. Another thing that we looked at is also processing of data.

 So, here, what we see is, again, multiple tasks, and we do different type of scalings and normalization. And, again, different regimes of normalizations depending on the task, they perform differently.

 So, there's no single best approach. Like, you know, what to do, you basically need to look at your data, look at your domain, and be mindful of, like, how you process your data and how you treat your training process.

 So, here we have different abstractions of data, and based on that, we looked at different foundational models, we took some learnings. I also want to add one more, and it's related to work.

 So, we are not done when you just take data and make a prediction.

 The player interacts with the world, so what you want to create a structure to actually ask this, like, player in a world. And that is more of what we're looking at, exploring what's in the world.

 So, two principles from applied data research. One, benchmark leadership is not transfer.

 Second, assumptions live in the pipeline to talk about, you know, this pooling normalization. And then respect the integrity process when you're building a solution.

 Okay.

 A little bit about, like, you know, some ways forward that we're currently exploring and, like, having answers and results on them. So, from looking at different use cases and.

 Basis that we have, we realize that one key thing is to be able to capture these multiple scalings of data and behaviors, right? We're talking about the experience we have.

 Fast, like, which is, like, a lot of events on, like, what happens now, now, what happens at the player, at the player. Then second is, like, for instance, medium sessions.

 I play at five sessions today, I'm back tomorrow, I play at another. Am I in a box I'm playing this, or, like, I'm sitting on the couch I'm playing this, or, like, you know, what are the patterns, right?

 Then the other one is, like, you know, slow path where it's like, what's my habit, what's my retention, what's the lifecycle? Am I, like, how long do I play for 10 years, or, like, how long have I just started playing?

 And trying to get all of these different types of scales and make a decision. And, like, you know, we have the data, like, the challenges of how to make a solution work.

 Another thing that I mentioned is that we want to, when we're looking at player data, there's a lot of noise. If you focus only on one event and predict the next event, first of all, it doesn't really match about the experience of that player.

 Second, there's a lot of noise. So, you are seeking for patterns, you're seeking for, like, you know, observations about, like, the behavior of the player.

 So, here is where models like JPOL, which is particularly interesting. I don't know if it works or not, but to be able to move away from the noise and actually capture this, like, you know, behaviors of players.

 And particularly, it would be interesting to look at this, like, the latent, predicted latent combined to these multiple time scales together and be able to see if, like, you know, can you get an interesting combining these modalities can you get an interesting representation and insights about players for our predicted tasks.

 Yeah. So, another interesting thing about, like, if we look at the work modeling would be that it can make it possible to build a rollout of, like, you know, generated experience and try to also do conditioning on different sets of interventions and be able to predict the behavior of the player in an environment.

 So, more importantly, why this is important and I keep getting asked here is, like, first of all, like, you know, we just, we started exploring this area. Second is that most of the studies and publications that we see, they are not talking about an evolving system.

 They talk about, like, you know, performing on, like, you know, a static task, right? But if you look at domains like education, health, and even recommenders, they are, like, you know, they are co-evolving with, like, you know, players and, like, interventions of the product that also impacts on those players.

 Another area moving away from word modeling that I'm interested in is also causal inputs and causal benchmarking. Because the question is that, like, you know, can you really trust this, like, you know, simulated future and, like, generated experience of the players?

 Right? So, what we saw is that there is a gap, and most of the studies, they don't capture the relationships that we have between their features.

 And, like, you know, for instance, like, you know, the player is playing a level and, like, you know, purchasing something or, like, you know, time of the day. Maybe these are, like, actually correlated.

 They're not actually causal events. It's not just, like, just binary, like, correlations, but there are multiple.

 So, with certain causal aspects and the benchmarking, we looked at, like, you know, more of, like, a similar task, existing popular models, and we started, like, you know, looking at how generation of the data and, like, you know, incorporating these higher-order relations, causal relations, has been the impact on the performance of the task and what are the properties of the benchmarking data.

 So, now I talked about a lot of, like, you know, behaviors and, like, things that work and particular things that didn't work, right?

 I want to also bring this to the community on, like, you know, interesting research questions and what we hear from. One is, like, you know, what I mentioned about, like, benchmarking.

 The other aspect is evaluation protocols for non-stationary parametric.

 And the third aspect, now I said this, like, normalizations and pooling and tokenizations. I think it's like the more we give attention to each of these components in the pipeline for building models.

 And finally, it's about, like, you know, how we are systematically evaluating real-world scenarios. Right now, we are looking at task performance in terms of accuracy for instance, but at the end, like, you know, this leads into does this shift a business metric or not?

 How does this translate into impact in my player and in my business? And being able to have this, like, this mapping of offline performance versus online performance is an interesting area.

 So, here, I want to also show maybe some of the works that I referred to in the talk. Considering the works from the team as more of, like, you know, takeaways as we study them, not as, like, you know, promise this is really our kind of completely new thing.

 There'll be a lot of people contributing to this work that have just presented their work, and so look ahead to me. It's like a great team and a big team that is behind this work, and I want to acknowledge that.

 Thank you.

 I should say that it was a great presentation that you did before me, and it was exactly what we wanted to mention that this is not really easy, just to use what we developed in the session here. I can't quite ask what's your long-term plan for the UK, but I hope that you have some time for digesting this and, like, you know, really looking forward to, like, hearing back from this community and, like, any questions, any suggestions and collaborations.

 Yes. So, the last part that you mentioned, like, this offline-online transfer, that is super interesting.

 Like, when you use those models in metrics for users in production, do you have any intuition as to how well these offline metrics correlate?

### Speaker 2

 So, basically, like, we don't have foundational models yet in production, right? But we have experimented on cases where we have, like, the production system compares to, like, foundational models online. And we see, like, you know, I mean, I showed, like, some use cases, right?

 We see some of the original work that is, like, it's working well in certain scenarios, but it's not working in some other example scenarios.

 Why? Because we're, for instance, just looking at, like, perplexity or, like, you know, accuracy of, like, the mask model that we use or, like, you know, the, the next token that we change, they are just working fine.

 It's just we don't capture those metrics that we are looking at. And then, like, you know, this aspect of looking at correlation, causation between causal properties of the features and, like, you know, the metrics that we can have impact on the player experience is something that we are currently actually partnering and implementing on.

 Have you ever thought of looping the player in a way that, not thought of, but thought of maybe because the need of developing different models to loop a player rather than developing one model?

### Speaker 1

 Very good question.

 I mean, there's one slide that I skipped as, like, as new. It's one that was, like, actually in hybrid setting where you could combine, actually, like, tabular and foundational models, or you could combine any service that is, like, for different types of players or different types of use cases.

 Yes, but we haven't, like, really gone through that entirely. My hope is that the multi-scale can actually capture different types of players with slow scale and with the sessions because, like, you know, another thing is look at, like, you know, sessions and habits of players and the systems and systems.

 So we are hoping that those two scales will actually translate into the piece of how we can make a good use of it.

 I want to see one more thing on another question.

 Right. I think I answered to your question.

 So, recently is the work in progress, like, another team started looking at actually something between habits and, like, you know, tabular models, like similar to conventional tabular models.

 What they do is they look at features and, like, the structures and, like, you know, relations between features. And they have changed the way that the attention on the transformer and the functional metrics, like, you know, how they treat the roles and the colors.

 And what they do is that they basically take that transformer base and then they have multi-objective optimizations for multiple pairs of different tasks. And what they see is that it can actually start, like, as they're increasing the data size, like, very early, like, in the beginning of the general.

 A claim on that, but it is not sure that it picks up on, like, a lot of tasks and events. So, like, there's something in the data for different types of players and it can generalize by many properties of the features to work on the tasks.

### Speaker 3

 Thank you for your thoughtful answer. I'm also very grateful in addition to getting this late to the week, of course, you know, it's quite a lot of sometimes new readings to find. So, I'm also not sure of your representation.

 To engage with this UI of the features and the users or whatever. Is that also an issue you observed in your paper?

 It should look like historically we don't have those actions as well. Is that a kind of a short circuit?

### Speaker 1

 It seems like it's quite a painful process to share today, right? I think I mentioned about, like, this white part about stability and replaying and so on. I think it's like, you know, the behavior of the players is probably going to change because the game is changing and, like, you know, the interaction also has impact on, like, you know, what they do.

 Even if they keep the same game, the experience, like, changes, but also the game changes. And the challenge is that, like, you know, for instance, when we start training, we don't know, like, you know, oh, are we looking at the right window of data for training, right?

 So, being able to generate data that reflects on the properties of our games and, like, you know, predicting it is quite an interesting topic for us. Also, one motivation to move toward modeling is, like, you know, we also want to get, like, meta behaviors and, like, move away from, like, a certain task of, like, just looking at a pixel on an image, right?

 So, maybe those would help. In one space where they were, you know, like, simulating the game a bit, we ended up building our own simulation environment to be able to generate our data and analyze with the interventions that we want to test.

 So, it's a tricky problem.

### Speaker 2

 I think one more.

### Speaker 3

 So, what is your idea? We cannot, like, barely enough this is grow, like, we need to, like, start practicing one, like, basically in an industrial setup where there aren't many pieces, like, small components here and there. And are you looking at, like, basically a lot of language model as a brain or as a piece of visualization that that's going to be, like, smaller setup of the ML model?

 And how do you think about the explaining it? Because that has become very, it's very important in, like, how you think about that.

### Speaker 1

 So, I think my first answer is that it is an easy case and because, like, you know, explainability is, like, a very urgent if, like, you know, compute or constraints, like, you know, the simplest model, it makes the life of, like, you know, everyone easier on the engineering and the product.

 So, not necessarily replacing everything, right? Our idea here was, yes, getting a representation that fits into smaller models so that we can just, like, make it easy to solve.

 And, like, we're showcasing the example of this TSME plot that I showed. We are trying to just, like, validate that all this, like, you know, representation meaning, right?

 So, like, you know, for some kind of, like, you know, that's a big question, right?

 The question that you have, like, you know, directions to whatever lens and, like, you know, so this was one direction. Another area is, like, you know, self-emotive tables where, for instance, we don't have a lot of player data, but we want to be able to simulate play place.

 We are making, like, you know, a combination of reinforcement learning and, like, you know, like, a small model trained on player data and figure out, like, you know, how to let the aggregate as small data comes in for the model to actually sell. That's also a direction that I know, like, you know, some of the other companies also go in.

 I didn't touch here because we. For players and how they can get that.

### Speaker 3

 Okay. So, first of all, thanks for your presentation. I'm curious to know how long this project take and with how many people.

### Speaker 1

 So, good question.

 My team, we started looking at this, like, two years ago with two interns, PhD interns. Then the year after, we got three PhD interns who started expanding and, like, one industrial PhD student started expanding the area.

 And when we see, like, promising results. Start expanding.

 But there's a lot of touchpoints. It's like the causal part, it's the world modeling, it's, like, you know, production use cases.

 So, we collaborated with a lot of different teams. It's not only my, like, my team that works on it, but it's, like, we've been exploring this for, like, a few years.

### Speaker 3

 Right.

### Speaker 1

 And one more thing that maybe I can add, that some of. I used the word, I was going to, I saw, like, you know, how people handle data, but you know, based on.

 And make up a database. And one of the topics that we are working on in our group is model searching.

 And we have foundational models, context of which we're looking for information. And then we've done more from the other end so that, like, we can explore some different types of.

### Speaker 3

 Multi-model?

### Speaker 1

 Multi-model, but instead of training the models, we just want to work on their datasets. We work on the models.

### Speaker 3

 Right.

### Speaker 1

 So, I think this is kind of. Yes, you may actually go from this setup to it. We actually have been discussing about, like, you know, something similar.

 The fusion box that I showed on the multi-scale. We have been also discussing about different modalities.

 The thing is that we don't actually have many different modalities, right? It's different representations of the same thing.

 But it would be interesting to be able to just, like, get to know more, like, you know, what's going on in the research. The other thing about model search is that we don't want to train on the game because we want other datasets.

 And then.

### Speaker 3

 Thanks.

### Speaker 1

 So, thank you very much.
